# IsBuiltInRuleEnabled(int,int *)

- ea: `0x1800114d0`
- end: `0x18001186d`
- name: `?IsBuiltInRuleEnabled@@YAJHPEAH@Z`
- size: `925`
- prototype: `__int64 __fastcall(UINT uID, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ccd0`
- `0x18000cdf8`
- `0x18000da10`

## callees

- `0x1800114d0`
- `0x180014660`
- `0x1800148c4`
- `0x18001505c`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001167e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800117d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001167e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800117d1`
- `OLEAUT32!__imp_VariantInit` at `0x180011532`
- `OLEAUT32!__imp_VariantInit` at `0x180011532`
- `OLEAUT32!__imp_VariantClear` at `0x18001166b`
- `OLEAUT32!__imp_VariantClear` at `0x1800117a9`
- `OLEAUT32!__imp_VariantClear` at `0x18001166b`
- `OLEAUT32!__imp_VariantClear` at `0x1800117a9`
- `KERNEL32!CompareStringW` at `0x18001173a`
- `KERNEL32!CompareStringW` at `0x18001173a`
- `KERNEL32!GetProcessHeap` at `0x1800117b4`
- `KERNEL32!GetProcessHeap` at `0x1800117b4`
- `KERNEL32!HeapFree` at `0x1800117c2`
- `KERNEL32!HeapFree` at `0x1800117c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011597`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011597`

## pseudocode

```c
__int64 __fastcall IsBuiltInRuleEnabled(UINT uID, int *a2)
{
  unsigned __int16 *v4; // rdx
  signed int StringResource; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  WCHAR *v8; // rdi
  HRESULT v9; // ebx
  unsigned int v10; // r9d
  CEventLogger *v11; // rcx
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v16; // [rsp+30h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-21h] BYREF
  int v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+58h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+7h] BYREF
  PCNZWCH lpString2; // [rsp+68h] [rbp+Fh] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+17h] BYREF
  __int16 v25; // [rsp+C8h] [rbp+6Fh] BYREF
  int v26; // [rsp+D0h] [rbp+77h] BYREF
  int v27; // [rsp+D8h] [rbp+7Fh] BYREF

  ppv = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v27 = 0;
  bstrString = 0;
  lpString2 = 0;
  v26 = 0;
  v18 = 0;
  v25 = -1;
  VariantInit(&pvarg);
  *a2 = 1;
  StringResource = LoadStringResource(uID, v4, (unsigned __int16 **)&lpString2);
  v8 = (WCHAR *)lpString2;
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 811;
LABEL_3:
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v10,
      L"IsBuiltInRuleEnabled",
      StringResource);
    goto LABEL_31;
  }
  v9 = CoCreateInstance(
         &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
         0,
         1u,
         &GUID_98325047_c671_4174_8d81_defcd3f03186,
         &ppv);
  if ( v9 < 0 )
  {
    CEventLogger::LogEvent(v11, &COM_Problem, L"9C4C6277-5027-441E-AFAE-CA1F542DA009");
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x338u,
      L"IsBuiltInRuleEnabled",
      v9);
    goto LABEL_31;
  }
  StringResource = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v18);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 829;
    goto LABEL_3;
  }
  StringResource = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 144LL))(ppv, &v21);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 831;
    goto LABEL_3;
  }
  StringResource = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 88LL))(v21, &v19);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 833;
    goto LABEL_3;
  }
  StringResource = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IEnumVARIANT, &v20);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 836;
    goto LABEL_3;
  }
  while ( !v9 )
  {
    VariantClear(&pvarg);
    v26 = 0;
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
    }
    v25 = -1;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v20 + 24LL))(
           v20,
           1,
           &pvarg,
           &v27);
    if ( v9 || v27 != 1 || pvarg.vt != 9 )
      break;
    v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_INetFwRule, &v16);
    if ( !v9 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 56LL))(v16, &bstrString);
      if ( !v9 && CompareStringW(0x7Fu, 0, bstrString, -1, v8, -1) == 2 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 296LL))(v16, &v26);
        if ( !v9 && (v18 & v26) != 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v16 + 264LL))(v16, &v25);
          if ( !v9 && !v25 )
          {
            *a2 = 0;
            break;
          }
        }
      }
    }
  }
LABEL_31:
  VariantClear(&pvarg);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800114d0  mov     [rsp-8+arg_0], rbx
0x1800114d5  push    rbp
0x1800114d6  push    rsi
0x1800114d7  push    rdi
0x1800114d8  push    r12
0x1800114da  push    r14
0x1800114dc  lea     rbp, [rsp-37h]
0x1800114e1  sub     rsp, 90h
0x1800114e8  xor     r14d, r14d
0x1800114eb  mov     ebx, ecx
0x1800114ed  xorps   xmm0, xmm0
0x1800114f0  mov     [rbp+57h+var_50], r14
0x1800114f4  xor     eax, eax
0x1800114f6  mov     [rbp+57h+var_58], r14
0x1800114fa  or      r12d, 0FFFFFFFFh
0x1800114fe  mov     [rbp+57h+var_68], r14
0x180011502  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011506  mov     [rbp+57h+var_60], r14
0x18001150a  mov     [rbp+57h+var_80], r14
0x18001150e  mov     rsi, rdx
0x180011511  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011515  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180011519  mov     [rbp+57h+arg_18], r14d
0x18001151d  mov     [rbp+57h+bstrString], r14
0x180011521  mov     [rbp+57h+lpString2], r14
0x180011525  mov     [rbp+57h+arg_10], r14d
0x180011529  mov     [rbp+57h+var_70], r14d
0x18001152d  mov     [rbp+57h+arg_8], r12w
0x180011532  call    cs:__imp_VariantInit
0x180011538  lea     r8, [rbp+57h+lpString2]; unsigned __int16 **
0x18001153c  mov     dword ptr [rsi], 1
0x180011542  mov     ecx, ebx; uID
0x180011544  call    ?LoadStringResource@@YAJHPEAGPEAPEAG@Z; LoadStringResource(int,ushort *,ushort * *)
0x180011549  mov     rdi, [rbp+57h+lpString2]
0x18001154d  mov     ebx, eax
0x18001154f  test    eax, eax
0x180011551  jns     short loc_18001157A
0x180011553  mov     r9d, 32Bh; unsigned int
0x180011559  mov     [rsp+0B0h+cchCount2], eax; unsigned int
0x18001155d  lea     rax, aIsbuiltinrulee; "IsBuiltInRuleEnabled"
0x180011564  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18001156b  mov     [rsp+0B0h+ppv], rax; unsigned __int16 *
0x180011570  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011575  jmp     loc_1800117A5
0x18001157a  xor     edx, edx; pUnkOuter
0x18001157c  lea     rax, [rbp+57h+var_50]
0x180011580  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180011587  mov     [rsp+0B0h+ppv], rax; ppv
0x18001158c  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180011593  lea     r8d, [rdx+1]; dwClsContext
0x180011597  call    cs:__imp_CoCreateInstance
0x18001159d  mov     ebx, eax
0x18001159f  test    eax, eax
0x1800115a1  jns     short loc_1800115C2
0x1800115a3  lea     r8, a9c4c6277502744; "9C4C6277-5027-441E-AFAE-CA1F542DA009"
0x1800115aa  lea     rdx, COM_Problem; struct _EVENT_DESCRIPTOR *
0x1800115b1  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x1800115b6  mov     r9d, 338h
0x1800115bc  mov     [rsp+0B0h+cchCount2], ebx
0x1800115c0  jmp     short loc_18001155D
0x1800115c2  mov     rcx, [rbp+57h+var_50]
0x1800115c6  lea     rdx, [rbp+57h+var_70]
0x1800115ca  mov     rax, [rcx]
0x1800115cd  mov     rax, [rax+38h]
0x1800115d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d6  mov     ebx, eax
0x1800115d8  test    eax, eax
0x1800115da  jns     short loc_1800115E7
0x1800115dc  mov     r9d, 33Dh
0x1800115e2  jmp     loc_180011559
0x1800115e7  mov     rcx, [rbp+57h+var_50]
0x1800115eb  lea     rdx, [rbp+57h+var_58]
0x1800115ef  mov     rax, [rcx]
0x1800115f2  mov     rax, [rax+90h]
0x1800115f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115fe  mov     ebx, eax
0x180011600  test    eax, eax
0x180011602  jns     short loc_18001160F
0x180011604  mov     r9d, 33Fh
0x18001160a  jmp     loc_180011559
0x18001160f  mov     rcx, [rbp+57h+var_58]
0x180011613  lea     rdx, [rbp+57h+var_68]
0x180011617  mov     rax, [rcx]
0x18001161a  mov     rax, [rax+58h]
0x18001161e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011623  mov     ebx, eax
0x180011625  test    eax, eax
0x180011627  jns     short loc_180011634
0x180011629  mov     r9d, 341h
0x18001162f  jmp     loc_180011559
0x180011634  mov     rcx, [rbp+57h+var_68]
0x180011638  lea     r8, [rbp+57h+var_60]
0x18001163c  lea     rdx, IID_IEnumVARIANT
0x180011643  mov     rax, [rcx]
0x180011646  mov     rax, [rax]
0x180011649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164e  mov     ebx, eax
0x180011650  test    eax, eax
0x180011652  jns     short loc_18001165F
0x180011654  mov     r9d, 344h
0x18001165a  jmp     loc_180011559
0x18001165f  test    ebx, ebx
0x180011661  jnz     loc_1800117A5
0x180011667  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001166b  call    cs:__imp_VariantClear
0x180011671  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180011675  mov     [rbp+57h+arg_10], r14d
0x180011679  test    rcx, rcx
0x18001167c  jz      short loc_180011688
0x18001167e  call    cs:__imp_SysFreeString
0x180011684  mov     [rbp+57h+bstrString], r14
0x180011688  mov     rcx, [rbp+57h+var_80]
0x18001168c  test    rcx, rcx
0x18001168f  jz      short loc_1800116A1
0x180011691  mov     rax, [rcx]
0x180011694  mov     rax, [rax+10h]
0x180011698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001169d  mov     [rbp+57h+var_80], r14
0x1800116a1  mov     rcx, [rbp+57h+var_60]
0x1800116a5  lea     r9, [rbp+57h+arg_18]
0x1800116a9  mov     [rbp+57h+arg_8], r12w
0x1800116ae  lea     r8, [rbp+57h+pvarg]
0x1800116b2  mov     edx, 1
0x1800116b7  mov     rax, [rcx]
0x1800116ba  mov     rax, [rax+18h]
0x1800116be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c3  mov     ebx, eax
0x1800116c5  test    eax, eax
0x1800116c7  jnz     loc_1800117A5
0x1800116cd  cmp     [rbp+57h+arg_18], 1
0x1800116d1  jnz     loc_1800117A5
0x1800116d7  cmp     word ptr [rbp+57h+pvarg], 9
0x1800116dc  jnz     loc_1800117A5
0x1800116e2  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x1800116e6  lea     r8, [rbp+57h+var_80]
0x1800116ea  lea     rdx, IID_INetFwRule
0x1800116f1  mov     rax, [rcx]
0x1800116f4  mov     rax, [rax]
0x1800116f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116fc  mov     ebx, eax
0x1800116fe  test    eax, eax
0x180011700  jnz     loc_18001165F
0x180011706  mov     rcx, [rbp+57h+var_80]
0x18001170a  lea     rdx, [rbp+57h+bstrString]
0x18001170e  mov     rax, [rcx]
0x180011711  mov     rax, [rax+38h]
0x180011715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001171a  mov     ebx, eax
0x18001171c  test    eax, eax
0x18001171e  jnz     loc_18001165F
0x180011724  mov     r8, [rbp+57h+bstrString]; lpString1
0x180011728  lea     ecx, [rax+7Fh]; Locale
0x18001172b  mov     [rsp+0B0h+cchCount2], r12d; cchCount2
0x180011730  mov     r9d, r12d; cchCount1
0x180011733  xor     edx, edx; dwCmpFlags
0x180011735  mov     [rsp+0B0h+ppv], rdi; lpString2
0x18001173a  call    cs:__imp_CompareStringW
0x180011740  cmp     eax, 2
0x180011743  jnz     loc_18001165F
0x180011749  mov     rcx, [rbp+57h+var_80]
0x18001174d  lea     rdx, [rbp+57h+arg_10]
0x180011751  mov     rax, [rcx]
0x180011754  mov     rax, [rax+128h]
0x18001175b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011760  mov     ebx, eax
0x180011762  test    eax, eax
0x180011764  jnz     loc_18001165F
0x18001176a  mov     eax, [rbp+57h+var_70]
0x18001176d  test    [rbp+57h+arg_10], eax
0x180011770  jz      loc_18001165F
0x180011776  mov     rcx, [rbp+57h+var_80]
0x18001177a  lea     rdx, [rbp+57h+arg_8]
0x18001177e  mov     rax, [rcx]
0x180011781  mov     rax, [rax+108h]
0x180011788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001178d  mov     ebx, eax
0x18001178f  test    eax, eax
0x180011791  jnz     loc_18001165F
0x180011797  cmp     r14w, [rbp+57h+arg_8]
0x18001179c  jnz     loc_18001165F
0x1800117a2  mov     [rsi], r14d
0x1800117a5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800117a9  call    cs:__imp_VariantClear
0x1800117af  test    rdi, rdi
0x1800117b2  jz      short loc_1800117C8
0x1800117b4  call    cs:__imp_GetProcessHeap
0x1800117ba  mov     r8, rdi; lpMem
0x1800117bd  xor     edx, edx; dwFlags
0x1800117bf  mov     rcx, rax; hHeap
0x1800117c2  call    cs:__imp_HeapFree
0x1800117c8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800117cc  test    rcx, rcx
0x1800117cf  jz      short loc_1800117DB
0x1800117d1  call    cs:__imp_SysFreeString
0x1800117d7  mov     [rbp+57h+bstrString], r14
0x1800117db  mov     rcx, [rbp+57h+var_68]
0x1800117df  test    rcx, rcx
0x1800117e2  jz      short loc_1800117F4
0x1800117e4  mov     rax, [rcx]
0x1800117e7  mov     rax, [rax+10h]
0x1800117eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117f0  mov     [rbp+57h+var_68], r14
0x1800117f4  mov     rcx, [rbp+57h+var_60]
0x1800117f8  test    rcx, rcx
0x1800117fb  jz      short loc_18001180D
0x1800117fd  mov     rax, [rcx]
0x180011800  mov     rax, [rax+10h]
0x180011804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011809  mov     [rbp+57h+var_60], r14
0x18001180d  mov     rcx, [rbp+57h+var_80]
0x180011811  test    rcx, rcx
0x180011814  jz      short loc_180011826
0x180011816  mov     rax, [rcx]
0x180011819  mov     rax, [rax+10h]
0x18001181d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011822  mov     [rbp+57h+var_80], r14
0x180011826  mov     rcx, [rbp+57h+var_58]
0x18001182a  test    rcx, rcx
0x18001182d  jz      short loc_18001183F
0x18001182f  mov     rax, [rcx]
0x180011832  mov     rax, [rax+10h]
0x180011836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001183b  mov     [rbp+57h+var_58], r14
0x18001183f  mov     rcx, [rbp+57h+var_50]
0x180011843  test    rcx, rcx
0x180011846  jz      short loc_180011854
0x180011848  mov     rax, [rcx]
0x18001184b  mov     rax, [rax+10h]
0x18001184f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011854  mov     eax, ebx
0x180011856  mov     rbx, [rsp+0B0h+arg_0]
0x18001185e  add     rsp, 90h
0x180011865  pop     r14
0x180011867  pop     r12
0x180011869  pop     rdi
0x18001186a  pop     rsi
0x18001186b  pop     rbp
0x18001186c  retn
```
