# ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog(void)

- ea: `0x18000946c`
- end: `0x180009849`
- name: `??0CLauncherMainTaskDialog@ux@@QEAA@XZ`
- size: `989`
- prototype: `unsigned __int64 __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008e20`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008ac8`
- `0x180008c40`
- `0x18000946c`
- `0x180009c58`
- `0x180009f4c`
- `0x18000ad08`
- `0x18000b180`
- `0x18000fdd6`
- `0x180011010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000951d`
- `ole32!CoCreateInstance` at `0x18000951d`

## string_xrefs

- `0x18000973a`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`
- `0x1800097b6`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`
- `0x180009815`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
unsigned __int64 __fastcall ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog(unsigned __int64 this)
{
  HRESULT v2; // eax
  int v3; // r14d
  int v4; // eax
  int v5; // r14d
  bool v6; // si
  _QWORD *v7; // r15
  void *v8; // rcx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // r14
  __int64 v11; // r13
  _QWORD *v12; // rdx
  int v13; // ecx
  _QWORD *v14; // rcx
  const char *v15; // rax
  unsigned __int64 pExceptionObject; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+78h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+50h] BYREF

  pExceptionObject = this;
  memset_0((void *)(this + 12), 0, 0x9Cu);
  *(_DWORD *)(this + 8) = 160;
  *(_QWORD *)(this + 20) = off_180019130;
  *(_QWORD *)(this + 168) = 0;
  *(_QWORD *)(this + 12) = 0;
  *(_QWORD *)(this + 148) = &WTL::CTaskDialogImpl<ux::CLauncherMainTaskDialog>::TaskDialogCallback;
  *(_QWORD *)(this + 156) = this & -(__int64)(this != -8);
  *(_QWORD *)this = &ux::CLauncherMainTaskDialog::`vftable';
  *(_DWORD *)(this + 176) = 0;
  ppv = 0;
  LODWORD(v18) = 0;
  v2 = CoCreateInstance(&CLSID_PortableWorkspaceLauncher, 0, 0x17u, &GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f, &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        150,
        v2);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v3);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        151,
        v4);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v5);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v6 = (_DWORD)v18 != 0;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  *(_BYTE *)(this + 180) = v6;
  *(_BYTE *)(this + 181) = (unsigned int)gp::CLauncherGroupPolicy::GetPolicy() - 2 <= 1;
  v7 = (_QWORD *)(this + 184);
  *(_QWORD *)(this + 184) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  *(_DWORD *)(this + 28) |= 1u;
  *(_QWORD *)(this + 36) = 202;
  *(_DWORD *)(this + 28) &= ~2u;
  *(_QWORD *)(this + 44) = 1001;
  *(_QWORD *)(this + 52) = 203;
  v9 = *(_QWORD *)ux::CLauncherMainTaskDialog::GetContentText(v8, &v18);
  v10 = (volatile signed __int32 *)(*v7 - 24LL);
  if ( (volatile signed __int32 *)(v9 - 24) != v10 )
  {
    if ( *((int *)v10 + 4) >= 0 && *(_QWORD *)(v9 - 24) == *(_QWORD *)v10 )
    {
      v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      if ( _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10, v10);
      *v7 = v11 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(this + 184, v9, *(unsigned int *)(v9 - 16));
    }
  }
  v12 = (_QWORD *)(v18 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  *(_QWORD *)(this + 60) = *v7;
  *(_DWORD *)(this + 164) = 270;
  *(_QWORD *)(this + 72) = &ux::CLauncherMainTaskDialog::LAUNCHER_MAIN_TASK_DIALOG_BUTTONS;
  *(_DWORD *)(this + 68) = 1;
  *(_DWORD *)(this + 80) = 101;
  *(_DWORD *)(this + 32) = 8;
  v13 = 103 - (*(_BYTE *)(this + 180) != 0);
  *(_QWORD *)(this + 88) = L"f";
  *(_DWORD *)(this + 84) = 2;
  *(_DWORD *)(this + 96) = v13;
  if ( *(_BYTE *)(this + 181) )
  {
    *(_DWORD *)(this + 28) &= ~4u;
    *(_QWORD *)(this + 132) = 0xFFFF;
    *(_QWORD *)(this + 140) = 211;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v15 = "Yes";
      if ( !*(_BYTE *)(this + 180) )
        v15 = "No";
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        114,
        (__int64)v15);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_(v14[2], 12, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x18000946c  mov     [rsp-38h+pExceptionObject], rcx
0x180009471  push    rbp
0x180009472  push    rbx
0x180009473  push    rsi
0x180009474  push    rdi
0x180009475  push    r13
0x180009477  push    r14
0x180009479  push    r15
0x18000947b  mov     rbp, rsp
0x18000947e  sub     rsp, 30h
0x180009482  mov     rdi, rcx
0x180009485  add     rcx, 0Ch; void *
0x180009489  xor     edx, edx; Val
0x18000948b  mov     r8d, 9Ch; Size
0x180009491  call    memset_0
0x180009496  mov     dword ptr [rdi+8], 0A0h
0x18000949d  mov     rax, cs:off_180019130
0x1800094a4  mov     [rdi+14h], rax
0x1800094a8  mov     qword ptr [rdi+0A8h], 0
0x1800094b3  mov     qword ptr [rdi+0Ch], 0
0x1800094bb  lea     rax, ?TaskDialogCallback@?$CTaskDialogImpl@VCLauncherMainTaskDialog@ux@@@WTL@@SAJPEAUHWND__@@I_K_J2@Z; WTL::CTaskDialogImpl<ux::CLauncherMainTaskDialog>::TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x1800094c2  mov     [rdi+94h], rax
0x1800094c9  lea     rax, [rdi+8]
0x1800094cd  neg     rax
0x1800094d0  sbb     rcx, rcx
0x1800094d3  and     rcx, rdi
0x1800094d6  mov     [rdi+9Ch], rcx
0x1800094dd  lea     rax, ??_7CLauncherMainTaskDialog@ux@@6B@; const ux::CLauncherMainTaskDialog::`vftable'
0x1800094e4  mov     [rdi], rax
0x1800094e7  mov     dword ptr [rdi+0B0h], 0
0x1800094f1  mov     [rbp+arg_10], 0
0x1800094f9  mov     dword ptr [rbp+arg_8], 0
0x180009500  lea     rax, [rbp+arg_10]
0x180009504  mov     [rsp+30h+ppv], rax; ppv
0x180009509  lea     r9, _GUID_ad6b3b23_c74a_4b2c_839f_c1149cb42e7f; riid
0x180009510  xor     edx, edx; pUnkOuter
0x180009512  lea     r8d, [rdx+17h]; dwClsContext
0x180009516  lea     rcx, CLSID_PortableWorkspaceLauncher; rclsid
0x18000951d  call    cs:__imp_CoCreateInstance
0x180009523  mov     r14d, eax
0x180009526  test    eax, eax
0x180009528  js      loc_1800097EA
0x18000952e  mov     rcx, [rbp+arg_10]
0x180009532  mov     rax, [rcx]
0x180009535  lea     rdx, [rbp+arg_8]
0x180009539  mov     rax, [rax+18h]
0x18000953d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009542  mov     r14d, eax
0x180009545  test    eax, eax
0x180009547  js      loc_18000978B
0x18000954d  cmp     dword ptr [rbp+arg_8], 0
0x180009551  setnz   sil
0x180009555  mov     rcx, [rbp+arg_10]
0x180009559  test    rcx, rcx
0x18000955c  jz      short loc_18000956B
0x18000955e  mov     rax, [rcx]
0x180009561  mov     rax, [rax+10h]
0x180009565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956a  nop
0x18000956b  mov     [rdi+0B4h], sil
0x180009572  call    ?GetPolicy@CLauncherGroupPolicy@gp@@SA?AW4LauncherGroupPolicyState@2@XZ; gp::CLauncherGroupPolicy::GetPolicy(void)
0x180009577  add     eax, 0FFFFFFFEh
0x18000957a  cmp     eax, 1
0x18000957d  setbe   al
0x180009580  mov     [rdi+0B5h], al
0x180009586  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000958d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009594  mov     rax, [rax+18h]
0x180009598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000959d  lea     r15, [rdi+0B8h]
0x1800095a4  add     rax, 18h
0x1800095a8  mov     [r15], rax
0x1800095ab  lea     rsi, WPP_GLOBAL_Control
0x1800095b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095b9  cmp     rcx, rsi
0x1800095bc  jz      short loc_1800095D9
0x1800095be  test    byte ptr [rcx+1Ch], 8
0x1800095c2  jz      short loc_1800095D9
0x1800095c4  mov     edx, 0Ah
0x1800095c9  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x1800095d0  mov     rcx, [rcx+10h]
0x1800095d4  call    WPP_SF_
0x1800095d9  or      dword ptr [rdi+1Ch], 1
0x1800095dd  mov     qword ptr [rdi+24h], 0CAh
0x1800095e5  and     dword ptr [rdi+1Ch], 0FFFFFFFDh
0x1800095e9  mov     qword ptr [rdi+2Ch], 3E9h
0x1800095f1  mov     qword ptr [rdi+34h], 0CBh
0x1800095f9  lea     rdx, [rbp+arg_8]
0x1800095fd  call    ?GetContentText@CLauncherMainTaskDialog@ux@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; ux::CLauncherMainTaskDialog::GetContentText(void)
0x180009602  nop
0x180009603  mov     rdx, [rax]
0x180009606  lea     rcx, [rdx-18h]
0x18000960a  mov     r14, [r15]
0x18000960d  add     r14, 0FFFFFFFFFFFFFFE8h
0x180009611  cmp     rcx, r14
0x180009614  jz      short loc_180009663
0x180009616  cmp     dword ptr [r14+10h], 0
0x18000961b  jl      short loc_180009656
0x18000961d  mov     rax, [r14]
0x180009620  cmp     [rcx], rax
0x180009623  jnz     short loc_180009656
0x180009625  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000962a  mov     r13, rax
0x18000962d  or      ecx, 0FFFFFFFFh
0x180009630  lock xadd [r14+10h], ecx
0x180009636  sub     ecx, 1
0x180009639  jg      short loc_18000964D
0x18000963b  mov     rcx, [r14]
0x18000963e  mov     r8, [rcx]
0x180009641  mov     rdx, r14
0x180009644  mov     rax, [r8+8]
0x180009648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964d  lea     rax, [r13+18h]
0x180009651  mov     [r15], rax
0x180009654  jmp     short loc_180009663
0x180009656  mov     r8d, [rdx-10h]
0x18000965a  mov     rcx, r15
0x18000965d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009662  nop
0x180009663  mov     rdx, [rbp+arg_8]
0x180009667  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000966b  or      eax, 0FFFFFFFFh
0x18000966e  lock xadd [rdx+10h], eax
0x180009673  sub     eax, 1
0x180009676  jg      short loc_180009687
0x180009678  mov     rcx, [rdx]
0x18000967b  mov     rax, [rcx]
0x18000967e  mov     rax, [rax+8]
0x180009682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009687  mov     rax, [r15]
0x18000968a  mov     [rdi+3Ch], rax
0x18000968e  mov     dword ptr [rdi+0A4h], 10Eh
0x180009698  lea     rax, ?LAUNCHER_MAIN_TASK_DIALOG_BUTTONS@CLauncherMainTaskDialog@ux@@0QBU_TASKDIALOG_BUTTON@@B; _TASKDIALOG_BUTTON const near * const ux::CLauncherMainTaskDialog::LAUNCHER_MAIN_TASK_DIALOG_BUTTONS
0x18000969f  mov     [rdi+48h], rax
0x1800096a3  mov     dword ptr [rdi+44h], 1
0x1800096aa  mov     dword ptr [rdi+50h], 65h ; 'e'
0x1800096b1  mov     dword ptr [rdi+20h], 8
0x1800096b8  mov     al, [rdi+0B4h]
0x1800096be  neg     al
0x1800096c0  sbb     ecx, ecx
0x1800096c2  add     ecx, 67h ; 'g'
0x1800096c5  lea     rax, ?LAUNCHER_MAIN_TASK_DIALOG_RADIO_BUTTONS@CLauncherMainTaskDialog@ux@@0QBU_TASKDIALOG_BUTTON@@B; "f"
0x1800096cc  mov     [rdi+58h], rax
0x1800096d0  mov     dword ptr [rdi+54h], 2
0x1800096d7  mov     [rdi+60h], ecx
0x1800096da  cmp     byte ptr [rdi+0B5h], 0
0x1800096e1  jz      short loc_1800096FD
0x1800096e3  and     dword ptr [rdi+1Ch], 0FFFFFFFBh
0x1800096e7  mov     qword ptr [rdi+84h], 0FFFFh
0x1800096f2  mov     qword ptr [rdi+8Ch], 0D3h
0x1800096fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009704  cmp     rcx, rsi
0x180009707  jz      short loc_180009779
0x180009709  test    byte ptr [rcx+1Ch], 4
0x18000970d  jz      short loc_180009758
0x18000970f  lea     rdx, aNo; "No"
0x180009716  lea     rax, aYes_0; "Yes"
0x18000971d  cmp     byte ptr [rdi+0B4h], 0
0x180009724  cmovz   rax, rdx
0x180009728  mov     edx, 0Bh
0x18000972d  mov     [rsp+30h+var_8], rax
0x180009732  mov     dword ptr [rsp+30h+ppv], 72h ; 'r'
0x18000973a  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x180009741  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x180009748  mov     rcx, [rcx+10h]
0x18000974c  call    WPP_SF_sds
0x180009751  mov     rcx, cs:WPP_GLOBAL_Control
0x180009758  cmp     rcx, rsi
0x18000975b  jz      short loc_180009779
0x18000975d  test    byte ptr [rcx+1Ch], 8
0x180009761  jz      short loc_180009779
0x180009763  mov     edx, 0Ch
0x180009768  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000976f  mov     rcx, [rcx+10h]
0x180009773  call    WPP_SF_
0x180009778  nop
0x180009779  mov     rax, rdi
0x18000977c  add     rsp, 30h
0x180009780  pop     r15
0x180009782  pop     r14
0x180009784  pop     r13
0x180009786  pop     rdi
0x180009787  pop     rsi
0x180009788  pop     rbx
0x180009789  pop     rbp
0x18000978a  retn
0x18000978b  lea     rsi, WPP_GLOBAL_Control
0x180009792  mov     rcx, cs:WPP_GLOBAL_Control
0x180009799  cmp     rcx, rsi
0x18000979c  jz      short loc_1800097CD
0x18000979e  test    byte ptr [rcx+1Ch], 1
0x1800097a2  jz      short loc_1800097CD
0x1800097a4  mov     edx, 21h ; '!'
0x1800097a9  mov     dword ptr [rsp+30h+var_8], r14d
0x1800097ae  mov     dword ptr [rsp+30h+ppv], 197h
0x1800097b6  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x1800097bd  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x1800097c4  mov     rcx, [rcx+10h]
0x1800097c8  call    WPP_SF_sdD
0x1800097cd  mov     edx, r14d; int
0x1800097d0  lea     rcx, [rbp+pExceptionObject]; this
0x1800097d4  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800097d9  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800097e0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800097e4  call    _CxxThrowException_0
0x1800097ea  lea     rsi, WPP_GLOBAL_Control
0x1800097f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097f8  cmp     rcx, rsi
0x1800097fb  jz      short loc_18000982C
0x1800097fd  test    byte ptr [rcx+1Ch], 1
0x180009801  jz      short loc_18000982C
0x180009803  mov     edx, 20h ; ' '
0x180009808  mov     dword ptr [rsp+30h+var_8], r14d
0x18000980d  mov     dword ptr [rsp+30h+ppv], 196h
0x180009815  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000981c  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x180009823  mov     rcx, [rcx+10h]
0x180009827  call    WPP_SF_sdD
0x18000982c  mov     edx, r14d; int
0x18000982f  lea     rcx, [rbp+pExceptionObject]; this
0x180009833  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180009838  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000983f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180009843  call    _CxxThrowException_0
```
