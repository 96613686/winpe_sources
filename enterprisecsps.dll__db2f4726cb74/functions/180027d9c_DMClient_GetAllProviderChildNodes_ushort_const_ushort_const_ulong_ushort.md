# DMClient::GetAllProviderChildNodes(ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x180027d9c`
- end: `0x18002812c`
- name: `?GetAllProviderChildNodes@DMClient@@YAJPEBG0PEAKPEAPEAPEAG@Z`
- size: `912`
- prototype: `__int64 __fastcall(DMClient *pszMore, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036360`

## callees

- `0x18002722c`
- `0x180027408`
- `0x180027d9c`
- `0x180028134`
- `0x18002985c`
- `0x18003a120`
- `0x1800fb85c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027ed6`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f2a`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f7e`
- `OLEAUT32!__imp_SysAllocString` at `0x180027fd2`
- `OLEAUT32!__imp_SysAllocString` at `0x180028019`
- `OLEAUT32!__imp_SysAllocString` at `0x180027ed6`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f2a`
- `OLEAUT32!__imp_SysAllocString` at `0x180027f7e`
- `OLEAUT32!__imp_SysAllocString` at `0x180027fd2`
- `OLEAUT32!__imp_SysAllocString` at `0x180028019`
- `OLEAUT32!__imp_SysFreeString` at `0x18002808c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002810c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002808c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800280f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002810c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180027fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180028003`

## string_xrefs

- `0x180027fc8`: `CommercialID`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DMClient::GetAllProviderChildNodes(
        DMClient *pszMore,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  HKEY v4; // r12
  unsigned int unused; // esi
  void *v7; // rdi
  int DoesPushExist; // ebx
  int *v10; // r9
  int *v11; // r8
  OLECHAR *v12; // r13
  OLECHAR *v13; // r15
  OLECHAR *v14; // r14
  int ProviderIdKey; // eax
  unsigned __int16 ***v16; // r9
  int AllValues; // eax
  BSTR v18; // rax
  __int64 v19; // rcx
  BSTR v20; // rax
  __int64 v21; // rcx
  BSTR v22; // rax
  __int64 v23; // rcx
  OLECHAR *v24; // rax
  __int64 v25; // rcx
  BSTR v26; // rax
  __int64 i; // r12
  OLECHAR *v28; // rcx
  struct HKEY__ v30; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 v31[2]; // [rsp+24h] [rbp-44h] BYREF
  unsigned __int16 v32[2]; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int16 v33[2]; // [rsp+2Ch] [rbp-3Ch] BYREF
  int CommercialID; // [rsp+30h] [rbp-38h]
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-28h]
  unsigned int v37[2]; // [rsp+48h] [rbp-20h] BYREF
  BSTR v38; // [rsp+50h] [rbp-18h] BYREF

  v4 = 0;
  *(_DWORD *)v33 = 0;
  *(_DWORD *)v32 = 0;
  unused = 0;
  *(_DWORD *)v31 = 0;
  v7 = 0;
  v30.unused = 0;
  *(_QWORD *)v37 = 0;
  v38 = 0;
  DoesPushExist = DMClient::DoesPushExist(pszMore, v33, (int *)a3);
  if ( DoesPushExist < 0 )
    return (unsigned int)DoesPushExist;
  DoesPushExist = DMClient::DoesPollExist(pszMore, a2, v32, v10);
  if ( DoesPushExist < 0 )
    return (unsigned int)DoesPushExist;
  DoesPushExist = FirstSync::StoragePathExists((PCWSTR)pszMore, v31, v11);
  if ( DoesPushExist < 0 )
    return (unsigned int)DoesPushExist;
  bstrString = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  CommercialID = GetCommercialID(&v38);
  hKey = 0;
  if ( a2 && pszMore )
  {
    ProviderIdKey = DMClient::GetProviderIdKey(pszMore, a2, (const unsigned __int16 *)&hKey, 0, v30.unused);
    v4 = hKey;
    DoesPushExist = ProviderIdKey;
    if ( ProviderIdKey >= 0 )
    {
      AllValues = DMClient::GetAllValues(hKey, &v30, v37, v16);
      unused = v30.unused;
      DoesPushExist = AllValues;
      v7 = *(void **)v37;
    }
  }
  else
  {
    DoesPushExist = -2147024809;
  }
  if ( v4 )
    RegCloseKey(v4);
  if ( DoesPushExist < 0 )
    goto LABEL_36;
  if ( *(_DWORD *)v31 )
  {
    v7 = CoTaskMemRealloc(v7, 8LL * (unused + 1));
    v18 = SysAllocString(L"FirstSyncStatus");
    v14 = v18;
    if ( !v7 || !v18 )
      goto LABEL_35;
    v19 = unused++;
    *((_QWORD *)v7 + v19) = v18;
  }
  if ( *(_DWORD *)v32 )
  {
    v7 = CoTaskMemRealloc(v7, 8LL * (unused + 1));
    v20 = SysAllocString(L"Poll");
    v13 = v20;
    if ( !v7 || !v20 )
    {
      v14 = 0;
      goto LABEL_35;
    }
    v21 = unused++;
    *((_QWORD *)v7 + v21) = v20;
  }
  if ( *(_DWORD *)v33 )
  {
    v7 = CoTaskMemRealloc(v7, 8LL * (unused + 1));
    v22 = SysAllocString(c_szEnrollmentsDBPush);
    v12 = v22;
    if ( !v7 || !v22 )
    {
      v14 = 0;
      v13 = 0;
      goto LABEL_35;
    }
    v23 = unused++;
    *((_QWORD *)v7 + v23) = v22;
  }
  if ( CommercialID >= 0 )
  {
    v7 = CoTaskMemRealloc(v7, 8LL * (unused + 1));
    v24 = SysAllocString(L"CommercialID");
    bstrString = v24;
    if ( v7 && v24 )
    {
      v25 = unused++;
      *((_QWORD *)v7 + v25) = v24;
      goto LABEL_28;
    }
    v14 = 0;
    v13 = 0;
    v12 = 0;
LABEL_35:
    DoesPushExist = -2147024882;
LABEL_36:
    if ( v7 )
    {
      for ( i = 0; (unsigned int)i < unused; i = (unsigned int)(i + 1) )
      {
        v28 = (OLECHAR *)*((_QWORD *)v7 + i);
        if ( v28 )
          SysFreeString(v28);
      }
      CoTaskMemFree(v7);
    }
    if ( v12 )
      SysFreeString(v12);
    if ( v13 )
      SysFreeString(v13);
    if ( bstrString )
      SysFreeString(bstrString);
    goto LABEL_48;
  }
LABEL_28:
  v7 = CoTaskMemRealloc(v7, 8LL * (unused + 1));
  v26 = SysAllocString(L"Recovery");
  if ( !v7 || !v26 )
  {
    v14 = 0;
    v13 = 0;
    v12 = 0;
    bstrString = 0;
    goto LABEL_35;
  }
  *((_QWORD *)v7 + unused) = v26;
  *(_DWORD *)a3 = unused + 1;
  v14 = 0;
  *(_QWORD *)a4 = v7;
LABEL_48:
  if ( v38 )
    SysFreeString(v38);
  if ( v14 )
    SysFreeString(v14);
  return (unsigned int)DoesPushExist;
}

```

## disassembly

```asm
0x180027d9c  mov     rax, rsp
0x180027d9f  mov     [rax+20h], r9
0x180027da3  mov     [rax+18h], r8
0x180027da7  mov     [rax+10h], rdx
0x180027dab  mov     [rax+8], rcx
0x180027daf  push    rbp
0x180027db0  push    rbx
0x180027db1  push    rsi
0x180027db2  push    rdi
0x180027db3  push    r12
0x180027db5  push    r13
0x180027db7  push    r14
0x180027db9  push    r15
0x180027dbb  mov     rbp, rsp
0x180027dbe  sub     rsp, 68h
0x180027dc2  xor     r12d, r12d
0x180027dc5  mov     r15, rdx
0x180027dc8  lea     rdx, [rbp+var_3C]; unsigned __int16 *
0x180027dcc  mov     dword ptr [rbp+var_3C], r12d
0x180027dd0  mov     dword ptr [rbp+var_40], r12d
0x180027dd4  mov     esi, r12d
0x180027dd7  mov     dword ptr [rbp+var_44], r12d
0x180027ddb  mov     edi, r12d
0x180027dde  mov     [rbp+var_48.unused], r12d
0x180027de2  mov     r14, rcx
0x180027de5  mov     qword ptr [rbp+var_20], r12
0x180027de9  mov     [rbp+var_18], r12
0x180027ded  call    ?DoesPushExist@DMClient@@YAJPEBGPEAH@Z; DMClient::DoesPushExist(ushort const *,int *)
0x180027df2  mov     ebx, eax
0x180027df4  test    eax, eax
0x180027df6  js      loc_180028118
0x180027dfc  lea     r8, [rbp+var_40]; unsigned __int16 *
0x180027e00  mov     rdx, r15; unsigned __int16 *
0x180027e03  mov     rcx, r14; this
0x180027e06  call    ?DoesPollExist@DMClient@@YAJPEBG0PEAH@Z; DMClient::DoesPollExist(ushort const *,ushort const *,int *)
0x180027e0b  mov     ebx, eax
0x180027e0d  test    eax, eax
0x180027e0f  js      loc_180028118
0x180027e15  lea     rdx, [rbp+var_44]; unsigned __int16 *
0x180027e19  mov     rcx, r14; pszMore
0x180027e1c  call    ?StoragePathExists@FirstSync@@YAJPEBGPEAH@Z; FirstSync::StoragePathExists(ushort const *,int *)
0x180027e21  mov     ebx, eax
0x180027e23  test    eax, eax
0x180027e25  js      loc_180028118
0x180027e2b  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x180027e2f  mov     [rbp+bstrString], r12
0x180027e33  mov     r13d, r12d
0x180027e36  mov     r15d, r12d
0x180027e39  mov     r14d, r12d
0x180027e3c  call    ?GetCommercialID@@YAJPEAPEAG@Z; GetCommercialID(ushort * *)
0x180027e41  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180027e45  mov     [rbp+var_38], eax
0x180027e48  mov     [rbp+hKey], r12
0x180027e4c  test    rdx, rdx
0x180027e4f  jz      short loc_180027E8B
0x180027e51  mov     rcx, [rbp+arg_0]; this
0x180027e55  test    rcx, rcx
0x180027e58  jz      short loc_180027E8B
0x180027e5a  xor     r9d, r9d; HKEY *
0x180027e5d  lea     r8, [rbp+hKey]; unsigned __int16 *
0x180027e61  call    ?GetProviderIdKey@DMClient@@YAJPEBG0PEAPEAUHKEY__@@H@Z; DMClient::GetProviderIdKey(ushort const *,ushort const *,HKEY__ * *,int)
0x180027e66  mov     r12, [rbp+hKey]
0x180027e6a  mov     ebx, eax
0x180027e6c  test    eax, eax
0x180027e6e  js      short loc_180027E90
0x180027e70  lea     r8, [rbp+var_20]; unsigned int *
0x180027e74  mov     rcx, r12; hKey
0x180027e77  lea     rdx, [rbp+var_48]; HKEY
0x180027e7b  call    ?GetAllValues@DMClient@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; DMClient::GetAllValues(HKEY__ *,ulong *,ushort * * *)
0x180027e80  mov     esi, [rbp+var_48.unused]
0x180027e83  mov     ebx, eax
0x180027e85  mov     rdi, qword ptr [rbp+var_20]
0x180027e89  jmp     short loc_180027E90
0x180027e8b  mov     ebx, 80070057h
0x180027e90  test    r12, r12
0x180027e93  jz      short loc_180027EA4
0x180027e95  mov     rcx, r12; hKey
0x180027e98  call    cs:__imp_RegCloseKey
0x180027e9f  nop     dword ptr [rax+rax+00h]
0x180027ea4  test    ebx, ebx
0x180027ea6  js      loc_180028077
0x180027eac  cmp     dword ptr [rbp+var_44], r13d
0x180027eb0  jz      short loc_180027F00
0x180027eb2  lea     r12d, [rsi+1]
0x180027eb6  mov     rcx, rdi; pv
0x180027eb9  mov     edx, r12d
0x180027ebc  shl     rdx, 3; cb
0x180027ec0  call    cs:__imp_CoTaskMemRealloc
0x180027ec7  nop     dword ptr [rax+rax+00h]
0x180027ecc  lea     rcx, aFirstsyncstatu; "FirstSyncStatus"
0x180027ed3  mov     rdi, rax
0x180027ed6  call    cs:__imp_SysAllocString
0x180027edd  nop     dword ptr [rax+rax+00h]
0x180027ee2  mov     r14, rax
0x180027ee5  test    rdi, rdi
0x180027ee8  jz      loc_180028072
0x180027eee  test    rax, rax
0x180027ef1  jz      loc_180028072
0x180027ef7  mov     ecx, esi
0x180027ef9  mov     esi, r12d
0x180027efc  mov     [rdi+rcx*8], rax
0x180027f00  cmp     dword ptr [rbp+var_40], r13d
0x180027f04  jz      short loc_180027F54
0x180027f06  lea     r14d, [rsi+1]
0x180027f0a  mov     rcx, rdi; pv
0x180027f0d  mov     edx, r14d
0x180027f10  shl     rdx, 3; cb
0x180027f14  call    cs:__imp_CoTaskMemRealloc
0x180027f1b  nop     dword ptr [rax+rax+00h]
0x180027f20  lea     rcx, aPoll; "Poll"
0x180027f27  mov     rdi, rax
0x180027f2a  call    cs:__imp_SysAllocString
0x180027f31  nop     dword ptr [rax+rax+00h]
0x180027f36  mov     r15, rax
0x180027f39  test    rdi, rdi
0x180027f3c  jz      loc_18002804B
0x180027f42  test    rax, rax
0x180027f45  jz      loc_18002804B
0x180027f4b  mov     ecx, esi
0x180027f4d  mov     esi, r14d
0x180027f50  mov     [rdi+rcx*8], rax
0x180027f54  cmp     dword ptr [rbp+var_3C], r13d
0x180027f58  jz      short loc_180027FA8
0x180027f5a  lea     r14d, [rsi+1]
0x180027f5e  mov     rcx, rdi; pv
0x180027f61  mov     edx, r14d
0x180027f64  shl     rdx, 3; cb
0x180027f68  call    cs:__imp_CoTaskMemRealloc
0x180027f6f  nop     dword ptr [rax+rax+00h]
0x180027f74  lea     rcx, ?c_szEnrollmentsDBPush@@3PAGA; "Push"
0x180027f7b  mov     rdi, rax
0x180027f7e  call    cs:__imp_SysAllocString
0x180027f85  nop     dword ptr [rax+rax+00h]
0x180027f8a  mov     r13, rax
0x180027f8d  test    rdi, rdi
0x180027f90  jz      loc_180028050
0x180027f96  test    rax, rax
0x180027f99  jz      loc_180028050
0x180027f9f  mov     ecx, esi
0x180027fa1  mov     esi, r14d
0x180027fa4  mov     [rdi+rcx*8], rax
0x180027fa8  cmp     [rbp+var_38], 0
0x180027fac  jl      short loc_180027FF5
0x180027fae  lea     r14d, [rsi+1]
0x180027fb2  mov     rcx, rdi; pv
0x180027fb5  mov     edx, r14d
0x180027fb8  shl     rdx, 3; cb
0x180027fbc  call    cs:__imp_CoTaskMemRealloc
0x180027fc3  nop     dword ptr [rax+rax+00h]
0x180027fc8  lea     rcx, aCommercialid; "CommercialID"
0x180027fcf  mov     rdi, rax
0x180027fd2  call    cs:__imp_SysAllocString
0x180027fd9  nop     dword ptr [rax+rax+00h]
0x180027fde  mov     [rbp+bstrString], rax
0x180027fe2  test    rdi, rdi
0x180027fe5  jz      short loc_180028058
0x180027fe7  test    rax, rax
0x180027fea  jz      short loc_180028058
0x180027fec  mov     ecx, esi
0x180027fee  mov     esi, r14d
0x180027ff1  mov     [rdi+rcx*8], rax
0x180027ff5  lea     r14d, [rsi+1]
0x180027ff9  mov     rcx, rdi; pv
0x180027ffc  mov     edx, r14d
0x180027fff  shl     rdx, 3; cb
0x180028003  call    cs:__imp_CoTaskMemRealloc
0x18002800a  nop     dword ptr [rax+rax+00h]
0x18002800f  lea     rcx, aRecovery; "Recovery"
0x180028016  mov     rdi, rax
0x180028019  call    cs:__imp_SysAllocString
0x180028020  nop     dword ptr [rax+rax+00h]
0x180028025  test    rdi, rdi
0x180028028  jz      short loc_180028063
0x18002802a  test    rax, rax
0x18002802d  jz      short loc_180028063
0x18002802f  mov     ecx, esi
0x180028031  mov     [rdi+rcx*8], rax
0x180028035  mov     rax, [rbp+arg_10]
0x180028039  mov     [rax], r14d
0x18002803c  xor     r14d, r14d
0x18002803f  mov     rax, [rbp+arg_18]
0x180028043  mov     [rax], rdi
0x180028046  jmp     loc_1800280EF
0x18002804b  xor     r14d, r14d
0x18002804e  jmp     short loc_180028072
0x180028050  xor     r14d, r14d
0x180028053  xor     r15d, r15d
0x180028056  jmp     short loc_180028072
0x180028058  xor     r14d, r14d
0x18002805b  xor     r15d, r15d
0x18002805e  xor     r13d, r13d
0x180028061  jmp     short loc_180028072
0x180028063  xor     r14d, r14d
0x180028066  xor     r15d, r15d
0x180028069  xor     r13d, r13d
0x18002806c  xor     eax, eax
0x18002806e  mov     [rbp+bstrString], rax
0x180028072  mov     ebx, 8007000Eh
0x180028077  test    rdi, rdi
0x18002807a  jz      short loc_1800280AF
0x18002807c  xor     r12d, r12d
0x18002807f  test    esi, esi
0x180028081  jz      short loc_1800280A0
0x180028083  mov     rcx, [rdi+r12*8]; bstrString
0x180028087  test    rcx, rcx
0x18002808a  jz      short loc_180028098
0x18002808c  call    cs:__imp_SysFreeString
0x180028093  nop     dword ptr [rax+rax+00h]
0x180028098  inc     r12d
0x18002809b  cmp     r12d, esi
0x18002809e  jb      short loc_180028083
0x1800280a0  mov     rcx, rdi; pv
0x1800280a3  call    cs:__imp_CoTaskMemFree
0x1800280aa  nop     dword ptr [rax+rax+00h]
0x1800280af  test    r13, r13
0x1800280b2  jz      short loc_1800280C3
0x1800280b4  mov     rcx, r13; bstrString
0x1800280b7  call    cs:__imp_SysFreeString
0x1800280be  nop     dword ptr [rax+rax+00h]
0x1800280c3  test    r15, r15
0x1800280c6  jz      short loc_1800280D7
0x1800280c8  mov     rcx, r15; bstrString
0x1800280cb  call    cs:__imp_SysFreeString
0x1800280d2  nop     dword ptr [rax+rax+00h]
0x1800280d7  mov     rax, [rbp+bstrString]
0x1800280db  test    rax, rax
0x1800280de  jz      short loc_1800280EF
0x1800280e0  mov     rcx, rax; bstrString
0x1800280e3  call    cs:__imp_SysFreeString
0x1800280ea  nop     dword ptr [rax+rax+00h]
0x1800280ef  mov     rcx, [rbp+var_18]; bstrString
0x1800280f3  test    rcx, rcx
0x1800280f6  jz      short loc_180028104
0x1800280f8  call    cs:__imp_SysFreeString
0x1800280ff  nop     dword ptr [rax+rax+00h]
0x180028104  test    r14, r14
0x180028107  jz      short loc_180028118
0x180028109  mov     rcx, r14; bstrString
0x18002810c  call    cs:__imp_SysFreeString
0x180028113  nop     dword ptr [rax+rax+00h]
0x180028118  mov     eax, ebx
0x18002811a  add     rsp, 68h
0x18002811e  pop     r15
0x180028120  pop     r14
0x180028122  pop     r13
0x180028124  pop     r12
0x180028126  pop     rdi
0x180028127  pop     rsi
0x180028128  pop     rbx
0x180028129  pop     rbp
0x18002812a  retn
```
