# NetUser::processUser(IASTL::IASRequest &,ushort const *,ushort const *)

- ea: `0x1800241e0`
- end: `0x1800245ed`
- name: `?processUser@NetUser@@UEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@PEBG1@Z`
- size: `1037`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x180001c88`
- `0x18000a5a0`
- `0x18000a760`
- `0x18000b2a0`
- `0x18000b648`
- `0x18000be24`
- `0x18000c4a4`
- `0x18000c808`
- `0x18000d49c`
- `0x18000e754`
- `0x180016884`
- `0x18001b5bc`
- `0x180024068`
- `0x1800241b0`
- `0x1800241e0`
- `0x1800254a0`
- `0x1800276b0`
- `0x1800285c8`
- `0x180028660`
- `0x18002944c`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002434b`
- `KERNEL32!LocalFree` at `0x1800245b0`
- `KERNEL32!LocalFree` at `0x18002434b`
- `KERNEL32!LocalFree` at `0x1800245b0`
- `OLEAUT32!__imp_VariantInit` at `0x180024381`
- `OLEAUT32!__imp_VariantInit` at `0x180024381`
- `OLEAUT32!__imp_VariantClear` at `0x180024528`
- `OLEAUT32!__imp_VariantClear` at `0x180024528`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800244ed`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800244ed`

## string_xrefs

- `0x1800242f3`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NetUser::processUser(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  DWORD v7; // eax
  DWORD v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned __int64 v14; // rsi
  HLOCAL v15; // rbx
  __int64 v16; // rdi
  int v17; // eax
  VARTYPE vt; // cx
  int v19; // r9d
  struct _FILETIME *v20; // rax
  bool v21; // r8
  signed int i; // r14d
  struct _FILETIME *v23; // rax
  bool v24; // r8
  HRESULT v25; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  char *v31; // [rsp+70h] [rbp-90h] BYREF
  char *v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  char v34; // [rsp+84h] [rbp-7Ch]
  char v35[136]; // [rsp+88h] [rbp-78h] BYREF
  char Buffer[256]; // [rsp+110h] [rbp+10h] BYREF

  if ( ourRole == 2 || !(unsigned int)IASIsDomainLocal(a3) )
    return 3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Using NT5 local user parameters.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids, "NPSSVC");
  }
  hMem = 0;
  v7 = IASGetUserParameters(a4, a3, &hMem);
  v8 = v7;
  if ( v7 )
  {
    v9 = IASFormatSysErr(v7, Buffer);
    if ( v9 >= 0x100 )
      _report_rangecheckfailure(v10);
    Buffer[v9] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"IASGetUserParameters", (__int64)Buffer);
    }
    v11 = IASMapWin32Error(v8, 6);
    v12 = IASProcessFailure(*(_QWORD *)a2, v11);
    if ( hMem )
      LocalFree(hMem);
    return v12;
  }
  else
  {
    v31 = v35;
    v32 = v35;
    v33 = 8;
    v34 = 0;
    VariantInit(&pvarg);
    v14 = 0;
    v15 = hMem;
    while ( v14 < 9 )
    {
      v16 = 4 * v14;
      v17 = IASParmsQueryUserProperty(v15, (&off_180030830)[4 * v14], &pvarg);
      if ( v17 < 0 )
        _com_issue_error(v17);
      vt = pvarg.vt;
      if ( pvarg.vt )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Inserting attribute %S.");
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids,
            v19,
            (__int64)(&off_180030830)[v16]);
          vt = pvarg.vt;
        }
        if ( vt == 8204 )
        {
          CVariantVector<tagVARIANT>::CVariantVector<tagVARIANT>(&psa, &pvarg);
          IASTL::IASAttributeVector::reserve((IASTL::IASAttributeVector *)&v31, v29);
          for ( i = 0; i < (int)v29; ++i )
          {
            v23 = IASAttributeFromVariant(v30 + 24LL * i, *((_DWORD *)&off_180030830 + 2 * v16 + 3));
            v23[1].dwLowDateTime = *((_DWORD *)&off_180030830 + 2 * v16 + 2);
            v23->dwHighDateTime = (DWORD)(&off_180030830)[v16 + 1];
            IASTL::IASAttributeVector::push_back((IASTL::IASAttributeVector *)&v31, (struct _IASATTRIBUTE *)v23, v24);
          }
          SafeArrayUnaccessData(psa);
        }
        else
        {
          v20 = IASAttributeFromVariant((__int64)&pvarg, *((_DWORD *)&off_180030830 + 2 * v16 + 3));
          v20[1].dwLowDateTime = *((_DWORD *)&off_180030830 + 2 * v16 + 2);
          v20->dwHighDateTime = (DWORD)(&off_180030830)[v16 + 1];
          IASTL::IASAttributeVector::push_back((IASTL::IASAttributeVector *)&v31, (struct _IASATTRIBUTE *)v20, v21);
        }
        (*(void (__fastcall **)(struct IAttributesRaw *, struct _ATTRIBUTEPOSITION *, struct _ATTRIBUTEPOSITION *))((char *)&off_180030848 + v16 * 8))(
          *(struct IAttributesRaw **)(a2 + 8),
          (struct _ATTRIBUTEPOSITION *)v31,
          (struct _ATTRIBUTEPOSITION *)v32);
        IASTL::IASAttributeVector::clear((IASTL::IASAttributeVector *)&v31);
        v25 = VariantClear(&pvarg);
        if ( v25 < 0 )
          _com_issue_error(v25);
      }
      ++v14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Successfully retrieved per-user attributes.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids, "NPSSVC");
    }
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>((IASTL::IASAttributeVector *)&v31);
    if ( v15 )
      LocalFree(v15);
    return 2;
  }
}

```

## disassembly

```asm
0x1800241e0  mov     [rsp-8+arg_0], rbx
0x1800241e5  push    rbp
0x1800241e6  push    rsi
0x1800241e7  push    rdi
0x1800241e8  push    r12
0x1800241ea  push    r13
0x1800241ec  push    r14
0x1800241ee  push    r15
0x1800241f0  lea     rbp, [rsp-120h]
0x1800241f8  sub     rsp, 220h
0x1800241ff  mov     rax, cs:__security_cookie
0x180024206  xor     rax, rsp
0x180024209  mov     [rbp+150h+var_40], rax
0x180024210  mov     rdi, r9
0x180024213  mov     rbx, r8
0x180024216  mov     r15, rdx
0x180024219  cmp     cs:ourRole, 2
0x180024220  jz      loc_1800245BE
0x180024226  mov     rcx, rbx
0x180024229  call    IASIsDomainLocal
0x18002422e  xor     r12d, r12d
0x180024231  test    eax, eax
0x180024233  jz      loc_1800245BE
0x180024239  lea     r14, WPP_GLOBAL_Control
0x180024240  mov     r13b, 4
0x180024243  mov     rax, cs:WPP_GLOBAL_Control
0x18002424a  cmp     rax, r14
0x18002424d  jz      short loc_18002428A
0x18002424f  cmp     [rax+19h], r13b
0x180024253  jb      short loc_18002428A
0x180024255  test    [rax+1Ch], r13b
0x180024259  jz      short loc_18002428A
0x18002425b  lea     rcx, aUsingNt5LocalU; "Using NT5 local user parameters."
0x180024262  call    WppDbgPrint
0x180024267  lea     edx, [r12+0Ah]
0x18002426c  lea     r9, aNpssvc; "NPSSVC"
0x180024273  lea     r8, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids
0x18002427a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024281  mov     rcx, [rcx+10h]
0x180024285  call    WPP_SF_s
0x18002428a  mov     [rsp+250h+hMem], r12
0x18002428f  lea     r8, [rsp+250h+hMem]
0x180024294  mov     rdx, rbx
0x180024297  mov     rcx, rdi
0x18002429a  call    IASGetUserParameters
0x18002429f  mov     ebx, eax
0x1800242a1  test    eax, eax
0x1800242a3  jz      loc_18002435F
0x1800242a9  lea     rdx, [rbp+150h+Buffer]; Buffer
0x1800242ad  mov     ecx, eax; dwMessageId
0x1800242af  call    IASFormatSysErr
0x1800242b4  cmp     eax, 100h
0x1800242b9  jnb     loc_180024359
0x1800242bf  mov     eax, eax
0x1800242c1  mov     [rbp+rax+150h+Buffer], r12b
0x1800242c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800242cd  cmp     rax, r14
0x1800242d0  jz      short loc_180024329
0x1800242d2  cmp     byte ptr [rax+19h], 2
0x1800242d6  jb      short loc_180024329
0x1800242d8  test    [rax+1Ch], r13b
0x1800242dc  jz      short loc_180024329
0x1800242de  lea     r9, [rbp+150h+Buffer]
0x1800242e2  lea     rdi, aIasgetuserpara; "IASGetUserParameters"
0x1800242e9  mov     r8, rdi
0x1800242ec  lea     rdx, aNpssvc; "NPSSVC"
0x1800242f3  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800242fa  call    WppDbgPrint
0x1800242ff  mov     edx, 0Bh
0x180024304  lea     rax, [rbp+150h+Buffer]
0x180024308  mov     [rsp+250h+var_228], rax; __int64
0x18002430d  mov     [rsp+250h+var_230], rdi; __int64
0x180024312  lea     r8, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids
0x180024319  mov     rcx, cs:WPP_GLOBAL_Control
0x180024320  mov     rcx, [rcx+10h]; LoggerHandle
0x180024324  call    WPP_SF_sss
0x180024329  mov     edx, 6
0x18002432e  mov     ecx, ebx
0x180024330  call    IASMapWin32Error
0x180024335  mov     edx, eax
0x180024337  mov     rcx, [r15]
0x18002433a  call    ?IASProcessFailure@@YA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@J@Z; IASProcessFailure(IRequest *,long)
0x18002433f  mov     ebx, eax
0x180024341  mov     rcx, [rsp+250h+hMem]; hMem
0x180024346  test    rcx, rcx
0x180024349  jz      short loc_180024352
0x18002434b  call    cs:__imp_LocalFree
0x180024351  nop
0x180024352  mov     eax, ebx
0x180024354  jmp     loc_1800245C3
0x180024359  call    __report_rangecheckfailure
0x18002435f  lea     rax, [rbp+150h+var_1C8]
0x180024363  mov     [rsp+250h+var_1E0], rax
0x180024368  lea     rax, [rbp+150h+var_1C8]
0x18002436c  mov     [rsp+250h+var_1D8], rax
0x180024371  mov     [rbp+150h+var_1D0], 8
0x180024378  mov     [rbp+150h+var_1CC], r12b
0x18002437c  lea     rcx, [rsp+250h+pvarg]; pvarg
0x180024381  call    cs:__imp_VariantInit
0x180024387  nop
0x180024388  mov     rsi, r12
0x18002438b  mov     rbx, [rsp+250h+hMem]
0x180024390  lea     rax, off_180030830; "msNPAllowDialin"
0x180024397  cmp     rsi, 9
0x18002439b  jnb     loc_18002454A
0x1800243a1  mov     rdi, rsi
0x1800243a4  shl     rdi, 5
0x1800243a8  lea     r8, [rsp+250h+pvarg]
0x1800243ad  mov     rdx, [rdi+rax]
0x1800243b1  mov     rcx, rbx
0x1800243b4  call    IASParmsQueryUserProperty
0x1800243b9  test    eax, eax
0x1800243bb  js      loc_180024542
0x1800243c1  movzx   ecx, word ptr [rsp+250h+pvarg]
0x1800243c6  test    cx, cx
0x1800243c9  jz      loc_180024532
0x1800243cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800243d6  cmp     rax, r14
0x1800243d9  jz      short loc_18002442F
0x1800243db  cmp     [rax+19h], r13b
0x1800243df  jb      short loc_18002442F
0x1800243e1  test    [rax+1Ch], r13b
0x1800243e5  jz      short loc_18002442F
0x1800243e7  lea     rdx, off_180030830; "msNPAllowDialin"
0x1800243ee  mov     rdx, [rdi+rdx]
0x1800243f2  lea     rcx, aInsertingAttri; "Inserting attribute %S."
0x1800243f9  call    WppDbgPrint
0x1800243fe  mov     edx, 0Ch
0x180024403  lea     rax, off_180030830; "msNPAllowDialin"
0x18002440a  mov     rax, [rdi+rax]
0x18002440e  mov     [rsp+250h+var_230], rax
0x180024413  lea     r8, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids
0x18002441a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024421  mov     rcx, [rcx+10h]
0x180024425  call    WPP_SF_sS
0x18002442a  movzx   ecx, word ptr [rsp+250h+pvarg]
0x18002442f  mov     eax, 200Ch
0x180024434  cmp     cx, ax
0x180024437  jz      short loc_180024475
0x180024439  lea     rax, off_180030830; "msNPAllowDialin"
0x180024440  mov     edx, [rdi+rax+0Ch]
0x180024444  lea     rcx, [rsp+250h+pvarg]
0x180024449  call    ?IASAttributeFromVariant@@YAPEAU_IASATTRIBUTE@@PEAUtagVARIANT@@W4IASTYPEENUM@@@Z; IASAttributeFromVariant(tagVARIANT *,IASTYPEENUM)
0x18002444e  mov     rdx, rax; struct _IASATTRIBUTE *
0x180024451  lea     rcx, off_180030830; "msNPAllowDialin"
0x180024458  mov     eax, [rdi+rcx+8]
0x18002445c  mov     [rdx+8], eax
0x18002445f  mov     eax, [rdi+rcx+10h]
0x180024463  mov     [rdx+4], eax
0x180024466  lea     rcx, [rsp+250h+var_1E0]; this
0x18002446b  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x180024470  jmp     loc_1800244FB
0x180024475  lea     rdx, [rsp+250h+pvarg]
0x18002447a  lea     rcx, [rsp+250h+psa]
0x18002447f  call    ??0?$CVariantVector@UtagVARIANT@@@@QEAA@PEAUtagVARIANT@@@Z; CVariantVector<tagVARIANT>::CVariantVector<tagVARIANT>(tagVARIANT *)
0x180024484  nop
0x180024485  mov     edx, [rsp+250h+var_1F8]; unsigned int
0x180024489  lea     rcx, [rsp+250h+var_1E0]; this
0x18002448e  call    ?reserve@IASAttributeVector@IASTL@@QEAAXK@Z; IASTL::IASAttributeVector::reserve(ulong)
0x180024493  mov     r14d, r12d
0x180024496  cmp     [rsp+250h+var_1F8], r12d
0x18002449b  jle     short loc_1800244E8
0x18002449d  lea     r13, off_180030830; "msNPAllowDialin"
0x1800244a4  movsxd  rax, r14d
0x1800244a7  lea     rcx, [rax+rax*2]
0x1800244ab  mov     rax, [rsp+250h+var_1F0]
0x1800244b0  lea     rcx, [rax+rcx*8]
0x1800244b4  mov     edx, [rdi+r13+0Ch]
0x1800244b9  call    ?IASAttributeFromVariant@@YAPEAU_IASATTRIBUTE@@PEAUtagVARIANT@@W4IASTYPEENUM@@@Z; IASAttributeFromVariant(tagVARIANT *,IASTYPEENUM)
0x1800244be  mov     rdx, rax; struct _IASATTRIBUTE *
0x1800244c1  mov     eax, [rdi+r13+8]
0x1800244c6  mov     [rdx+8], eax
0x1800244c9  mov     eax, [rdi+r13+10h]
0x1800244ce  mov     [rdx+4], eax
0x1800244d1  lea     rcx, [rsp+250h+var_1E0]; this
0x1800244d6  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x1800244db  inc     r14d
0x1800244de  cmp     r14d, [rsp+250h+var_1F8]
0x1800244e3  jl      short loc_1800244A4
0x1800244e5  mov     r13b, 4
0x1800244e8  mov     rcx, [rsp+250h+psa]; psa
0x1800244ed  call    cs:__imp_SafeArrayUnaccessData
0x1800244f3  nop
0x1800244f4  lea     r14, WPP_GLOBAL_Control
0x1800244fb  lea     rax, off_180030848
0x180024502  mov     r8, [rsp+250h+var_1D8]
0x180024507  mov     rdx, [rsp+250h+var_1E0]
0x18002450c  mov     rcx, [r15+8]
0x180024510  mov     rax, [rdi+rax]
0x180024514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024519  lea     rcx, [rsp+250h+var_1E0]; this
0x18002451e  call    ?clear@IASAttributeVector@IASTL@@QEAAXXZ; IASTL::IASAttributeVector::clear(void)
0x180024523  lea     rcx, [rsp+250h+pvarg]; pvarg
0x180024528  call    cs:__imp_VariantClear
0x18002452e  test    eax, eax
0x180024530  js      short loc_18002453A
0x180024532  inc     rsi
0x180024535  jmp     loc_180024390
0x18002453a  mov     ecx, eax; int
0x18002453c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180024542  mov     ecx, eax; int
0x180024544  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002454a  mov     rax, cs:WPP_GLOBAL_Control
0x180024551  cmp     rax, r14
0x180024554  jz      short loc_180024592
0x180024556  cmp     [rax+19h], r13b
0x18002455a  jb      short loc_180024592
0x18002455c  test    [rax+1Ch], r13b
0x180024560  jz      short loc_180024592
0x180024562  lea     rcx, aSuccessfullyRe; "Successfully retrieved per-user attribu"...
0x180024569  call    WppDbgPrint
0x18002456e  mov     edx, 0Dh
0x180024573  lea     r9, aNpssvc; "NPSSVC"
0x18002457a  lea     r8, WPP_7e1549ceaeee3722a4ab53ec76e23710_Traceguids
0x180024581  mov     rcx, cs:WPP_GLOBAL_Control
0x180024588  mov     rcx, [rcx+10h]
0x18002458c  call    WPP_SF_s
0x180024591  nop
0x180024592  lea     rcx, [rsp+250h+pvarg]; this
0x180024597  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002459c  nop
0x18002459d  lea     rcx, [rsp+250h+var_1E0]; this
0x1800245a2  call    ??1?$IASAttributeVectorWithBuffer@$09@IASTL@@QEAA@XZ; IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>(void)
0x1800245a7  nop
0x1800245a8  test    rbx, rbx
0x1800245ab  jz      short loc_1800245B7
0x1800245ad  mov     rcx, rbx; hMem
0x1800245b0  call    cs:__imp_LocalFree
0x1800245b6  nop
0x1800245b7  mov     eax, 2
0x1800245bc  jmp     short loc_1800245C3
0x1800245be  mov     eax, 3
0x1800245c3  mov     rcx, [rbp+150h+var_40]
0x1800245ca  xor     rcx, rsp; StackCookie
0x1800245cd  call    __security_check_cookie
0x1800245d2  mov     rbx, [rsp+250h+arg_0]
0x1800245da  add     rsp, 220h
0x1800245e1  pop     r15
0x1800245e3  pop     r14
0x1800245e5  pop     r13
0x1800245e7  pop     r12
0x1800245e9  pop     rdi
0x1800245ea  pop     rsi
0x1800245eb  pop     rbp
0x1800245ec  retn
```
