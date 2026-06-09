# QueryConnectionAndDisplayState(IUnknown *,IShellItemArray *,tagOFFLINEFILES_CONNECT_STATE *,tagOFFLINEFILES_OFFLINE_REASON *,int *)

- ea: `0x1800294f4`
- end: `0x180029712`
- name: `?QueryConnectionAndDisplayState@@YAJPEAUIUnknown@@PEAUIShellItemArray@@PEAW4tagOFFLINEFILES_CONNECT_STATE@@PEAW4tagOFFLINEFILES_OFFLINE_REASON@@PEAH@Z`
- size: `542`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *@<rcx>, struct IShellItemArray *@<rdx>, enum tagOFFLINEFILES_CONNECT_STATE *@<r8>, enum tagOFFLINEFILES_OFFLINE_REASON *@<r9>, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180029ad0`
- `0x18002bbc8`

## callees

- `0x180026a80`
- `0x180027ac8`
- `0x1800294f4`
- `0x180029718`
- `0x18002d034`
- `0x180048314`
- `0x180048340`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002954d`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002954d`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1800296a4`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x1800296a4`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18002967b`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18002968f`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18002967b`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18002968f`

## pseudocode

```c
__int64 __fastcall QueryConnectionAndDisplayState(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        enum tagOFFLINEFILES_CONNECT_STATE *a3,
        enum tagOFFLINEFILES_OFFLINE_REASON *a4,
        int *a5)
{
  int *v5; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // ebx
  int ContainedLocationsFromSite; // eax
  int v15; // edi
  unsigned int v16; // r15d
  struct IShellItem *v18[2]; // [rsp+40h] [rbp-10h] BYREF
  void *ppvOut; // [rsp+90h] [rbp+40h] BYREF
  struct IShellItemArray *v20; // [rsp+98h] [rbp+48h] BYREF

  v5 = a5;
  *a3 = OFFLINEFILES_CONNECT_STATE_UNKNOWN;
  *a4 = OFFLINEFILES_OFFLINE_REASON_UNKNOWN;
  ppvOut = 0;
  *v5 = 0;
  if ( IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_CommandsPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) >= 0 )
  {
    SHPropertyBag_ReadDWORDDef(ppvOut, L"CscConnectState", a3);
    SHPropertyBag_ReadDWORDDef(ppvOut, L"CscOfflineReason", a4);
    SHPropertyBag_ReadBOOLDef(ppvOut, v12, v5);
  }
  if ( *a3 == OFFLINEFILES_CONNECT_STATE_UNKNOWN || (v13 = 0, *a4 == OFFLINEFILES_OFFLINE_REASON_UNKNOWN) )
  {
    v20 = 0;
    if ( a2 )
      ContainedLocationsFromSite = ((__int64 (__fastcall *)(struct IShellItemArray *, GUID *, struct IShellItemArray **))a2->lpVtbl->QueryInterface)(
                                     a2,
                                     &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                     &v20);
    else
      ContainedLocationsFromSite = GetContainedLocationsFromSite(a1, &v20);
    v13 = ContainedLocationsFromSite;
    if ( ContainedLocationsFromSite >= 0 )
    {
      LODWORD(a5) = 0;
      v13 = ((__int64 (__fastcall *)(struct IShellItemArray *, int **))v20->lpVtbl->GetCount)(v20, &a5);
      if ( v13 >= 0 )
      {
        v15 = 1;
        v16 = 0;
        do
        {
          if ( v16 >= (unsigned int)a5 )
            break;
          v18[0] = 0;
          if ( ((int (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v20->lpVtbl->GetItemAt)(
                 v20,
                 v16,
                 v18) >= 0
            && (int)QueryConnectionAndDisplayStateFromItem(v18[0], a3, a4, v5) >= 0
            && *a3
            && *a4
            && *v5 == 1 )
          {
            v15 = 0;
          }
          ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(v18);
          ++v16;
        }
        while ( v15 );
        if ( ppvOut )
        {
          PSPropertyBag_WriteDWORD((IPropertyBag *)ppvOut, L"CscConnectState", *a3);
          PSPropertyBag_WriteDWORD((IPropertyBag *)ppvOut, L"CscOfflineReason", *a4);
          PSPropertyBag_WriteBOOL((IPropertyBag *)ppvOut, L"CscDisplayState", *v5);
        }
      }
    }
    ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(&v20);
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_dddD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *(unsigned int *)a3, *a4, *v5, v13);
  }
  ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(&ppvOut);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800294f4  mov     [rsp-28h+arg_0], rbx
0x1800294f9  mov     [rsp-28h+arg_8], rsi
0x1800294fe  push    rbp
0x1800294ff  push    rdi
0x180029500  push    r12
0x180029502  push    r14
0x180029504  push    r15
0x180029506  mov     rbp, rsp
0x180029509  sub     rsp, 50h
0x18002950d  mov     r12, [rbp+arg_20]
0x180029511  mov     r14, r9
0x180029514  mov     dword ptr [r8], 0
0x18002951b  mov     rsi, r8
0x18002951e  mov     dword ptr [r9], 0
0x180029525  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18002952c  mov     rdi, rdx
0x18002952f  mov     [rbp+ppvOut], 0
0x180029537  lea     r9, [rbp+ppvOut]; ppvOut
0x18002953b  mov     dword ptr [r12], 0
0x180029543  lea     rdx, SID_CommandsPropertyBag; guidService
0x18002954a  mov     r15, rcx
0x18002954d  call    cs:__imp_IUnknown_QueryService
0x180029553  test    eax, eax
0x180029555  js      short loc_180029589
0x180029557  mov     rcx, [rbp+ppvOut]
0x18002955b  lea     rdx, propName; "CscConnectState"
0x180029562  mov     r8, rsi
0x180029565  call    SHPropertyBag_ReadDWORDDef
0x18002956a  mov     rcx, [rbp+ppvOut]
0x18002956e  lea     rdx, aCscofflinereas; "CscOfflineReason"
0x180029575  mov     r8, r14
0x180029578  call    SHPropertyBag_ReadDWORDDef
0x18002957d  mov     rcx, [rbp+ppvOut]
0x180029581  mov     r8, r12
0x180029584  call    SHPropertyBag_ReadBOOLDef
0x180029589  cmp     dword ptr [rsi], 0
0x18002958c  jz      short loc_180029599
0x18002958e  xor     ebx, ebx
0x180029590  cmp     [r14], ebx
0x180029593  jnz     loc_1800296B3
0x180029599  mov     [rbp+arg_18], 0
0x1800295a1  test    rdi, rdi
0x1800295a4  jz      short loc_1800295C1
0x1800295a6  mov     rax, [rdi]
0x1800295a9  lea     r8, [rbp+arg_18]
0x1800295ad  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x1800295b4  mov     rcx, rdi
0x1800295b7  mov     rax, [rax]
0x1800295ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295bf  jmp     short loc_1800295CD
0x1800295c1  lea     rdx, [rbp+arg_18]; struct IShellItemArray **
0x1800295c5  mov     rcx, r15; struct IUnknown *
0x1800295c8  call    ?GetContainedLocationsFromSite@@YAJPEAUIUnknown@@PEAPEAUIShellItemArray@@@Z; GetContainedLocationsFromSite(IUnknown *,IShellItemArray * *)
0x1800295cd  mov     ebx, eax
0x1800295cf  test    eax, eax
0x1800295d1  js      loc_1800296AA
0x1800295d7  mov     rcx, [rbp+arg_18]
0x1800295db  lea     rdx, [rbp+arg_20]
0x1800295df  mov     dword ptr [rbp+arg_20], 0
0x1800295e6  mov     rax, [rcx]
0x1800295e9  mov     rax, [rax+38h]
0x1800295ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295f2  mov     ebx, eax
0x1800295f4  test    eax, eax
0x1800295f6  js      loc_1800296AA
0x1800295fc  mov     edi, 1
0x180029601  xor     r15d, r15d
0x180029604  cmp     r15d, dword ptr [rbp+arg_20]
0x180029608  jnb     short loc_180029668
0x18002960a  mov     rcx, [rbp+arg_18]
0x18002960e  lea     r8, [rbp+var_10]
0x180029612  mov     [rbp+var_10], 0
0x18002961a  mov     edx, r15d
0x18002961d  mov     rax, [rcx]
0x180029620  mov     rax, [rax+40h]
0x180029624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029629  test    eax, eax
0x18002962b  js      short loc_180029658
0x18002962d  mov     rcx, [rbp+var_10]; struct IShellItem *
0x180029631  mov     r9, r12; int *
0x180029634  mov     r8, r14; enum tagOFFLINEFILES_OFFLINE_REASON *
0x180029637  mov     rdx, rsi; enum tagOFFLINEFILES_CONNECT_STATE *
0x18002963a  call    ?QueryConnectionAndDisplayStateFromItem@@YAJPEAUIShellItem@@PEAW4tagOFFLINEFILES_CONNECT_STATE@@PEAW4tagOFFLINEFILES_OFFLINE_REASON@@PEAH@Z; QueryConnectionAndDisplayStateFromItem(IShellItem *,tagOFFLINEFILES_CONNECT_STATE *,tagOFFLINEFILES_OFFLINE_REASON *,int *)
0x18002963f  test    eax, eax
0x180029641  js      short loc_180029658
0x180029643  cmp     dword ptr [rsi], 0
0x180029646  jz      short loc_180029658
0x180029648  cmp     dword ptr [r14], 0
0x18002964c  jz      short loc_180029658
0x18002964e  xor     eax, eax
0x180029650  cmp     dword ptr [r12], 1
0x180029655  cmovz   edi, eax
0x180029658  lea     rcx, [rbp+var_10]
0x18002965c  call    ??1?$CComPtrBase@UIShellItemArray@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(void)
0x180029661  inc     r15d
0x180029664  test    edi, edi
0x180029666  jnz     short loc_180029604
0x180029668  mov     rcx, [rbp+ppvOut]; propBag
0x18002966c  test    rcx, rcx
0x18002966f  jz      short loc_1800296AA
0x180029671  mov     r8d, [rsi]; value
0x180029674  lea     rdx, propName; "CscConnectState"
0x18002967b  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180029681  mov     r8d, [r14]; value
0x180029684  lea     rdx, aCscofflinereas; "CscOfflineReason"
0x18002968b  mov     rcx, [rbp+ppvOut]; propBag
0x18002968f  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180029695  mov     r8d, [r12]; value
0x180029699  lea     rdx, aCscdisplaystat; "CscDisplayState"
0x1800296a0  mov     rcx, [rbp+ppvOut]; propBag
0x1800296a4  call    cs:__imp_PSPropertyBag_WriteBOOL
0x1800296aa  lea     rcx, [rbp+arg_18]
0x1800296ae  call    ??1?$CComPtrBase@UIShellItemArray@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(void)
0x1800296b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296ba  lea     rax, WPP_GLOBAL_Control
0x1800296c1  cmp     rcx, rax
0x1800296c4  jz      short loc_1800296EE
0x1800296c6  test    dword ptr [rcx+1Ch], 4000000h
0x1800296cd  jz      short loc_1800296EE
0x1800296cf  mov     eax, [r12]
0x1800296d3  mov     r9d, [rsi]
0x1800296d6  mov     rcx, [rcx+10h]
0x1800296da  mov     [rsp+50h+var_20], ebx
0x1800296de  mov     [rsp+50h+var_28], eax
0x1800296e2  mov     eax, [r14]
0x1800296e5  mov     [rsp+50h+var_30], eax
0x1800296e9  call    WPP_SF_dddD
0x1800296ee  lea     rcx, [rbp+ppvOut]
0x1800296f2  call    ??1?$CComPtrBase@UIShellItemArray@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellItemArray>::~CComPtrBase<IShellItemArray>(void)
0x1800296f7  lea     r11, [rsp+50h+var_s0]
0x1800296fc  mov     eax, ebx
0x1800296fe  mov     rbx, [r11+30h]
0x180029702  mov     rsi, [r11+38h]
0x180029706  mov     rsp, r11
0x180029709  pop     r15
0x18002970b  pop     r14
0x18002970d  pop     r12
0x18002970f  pop     rdi
0x180029710  pop     rbp
0x180029711  retn
```
