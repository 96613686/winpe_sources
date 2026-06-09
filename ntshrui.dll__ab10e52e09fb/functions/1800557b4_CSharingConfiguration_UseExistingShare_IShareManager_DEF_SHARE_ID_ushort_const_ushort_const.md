# CSharingConfiguration::_UseExistingShare(IShareManager *,DEF_SHARE_ID,ushort const *,ushort const *)

- ea: `0x1800557b4`
- end: `0x18005598b`
- name: `?_UseExistingShare@CSharingConfiguration@@AEAAJPEAUIShareManager@@W4DEF_SHARE_ID@@PEBG2@Z`
- size: `471`
- prototype: `int(CSharingConfiguration *__hidden this, struct IShareManager *, enum DEF_SHARE_ID, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800541d0`

## callees

- `0x18001a1a4`
- `0x180023e68`
- `0x1800557b4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800558af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055951`
- `SHLWAPI!PathFindFileNameW` at `0x1800557eb`
- `SHLWAPI!PathFindFileNameW` at `0x1800557eb`
- `SHLWAPI!__imp_StrCmpICW` at `0x18005588e`
- `SHLWAPI!__imp_StrCmpICW` at `0x18005588e`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::_UseExistingShare(
        CSharingConfiguration *this,
        struct IShareManager *a2,
        enum DEF_SHARE_ID a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const WCHAR *v5; // r14
  const WCHAR *v6; // rsi
  const WCHAR *FileNameW; // r15
  int v11; // ebx
  __int64 v12; // rax
  int v13; // ebx
  CSharingConfiguration *v14; // rcx
  LPCWSTR pszStr1; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  const WCHAR *v18; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+30h] BYREF
  const WCHAR *v20; // [rsp+88h] [rbp+38h] BYREF

  pv = this;
  v5 = 0;
  v6 = 0;
  v18 = 0;
  pszStr1 = 0;
  v17 = 0;
  FileNameW = PathFindFileNameW(a4);
  if ( (*(int (__fastcall **)(struct IShareManager *, const unsigned __int16 *, __int64, __int64 *))(*(_QWORD *)a2 + 56LL))(
         a2,
         a4,
         1,
         &v17) < 0 )
    goto LABEL_18;
  LODWORD(pv) = 0;
  v20 = 0;
  do
  {
    if ( v6
      || (*(unsigned int (__fastcall **)(__int64, __int64, const WCHAR **, LPVOID *))(*(_QWORD *)v17 + 24LL))(
           v17,
           1,
           &v20,
           &pv) )
    {
      break;
    }
    if ( !v5 )
    {
      v5 = v20;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v20 + 8LL))(v20);
    }
    pszStr1 = 0;
    v11 = (*(__int64 (__fastcall **)(const WCHAR *, LPCWSTR *))(*(_QWORD *)v20 + 32LL))(v20, &pszStr1);
    if ( v11 >= 0 )
    {
      if ( !StrCmpICW(pszStr1, FileNameW) )
      {
        v6 = v20;
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v20 + 8LL))(v20);
      }
      CoTaskMemFree((LPVOID)pszStr1);
    }
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  while ( v11 >= 0 );
  pszStr1 = v6;
  v18 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v6 )
    goto LABEL_15;
  if ( !v5 )
  {
LABEL_18:
    v13 = -2147024894;
    goto LABEL_19;
  }
  v12 = *(_QWORD *)v5;
  v6 = v5;
  pszStr1 = v5;
  (*(void (__fastcall **)(const WCHAR *))(v12 + 8))(v5);
LABEL_15:
  v13 = (*(__int64 (__fastcall **)(const WCHAR *, const unsigned __int16 *))(*(_QWORD *)v6 + 72LL))(v6, a5);
  if ( v13 >= 0 )
  {
    pv = 0;
    v13 = (*(__int64 (__fastcall **)(const WCHAR *, LPVOID *))(*(_QWORD *)v6 + 32LL))(v6, &pv);
    if ( v13 >= 0 )
    {
      v13 = CSharingConfiguration::_SetShareName(v14, a3, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
  }
LABEL_19:
  SafeRelease<IShellItemArray>(&v18);
  SafeRelease<IShellItemArray>(&pszStr1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800557b4  mov     [rsp-28h+arg_10], rbx
0x1800557b9  mov     [rsp-28h+arg_18], rsi
0x1800557be  mov     [rsp-28h+pv], rcx
0x1800557c3  push    rbp
0x1800557c4  push    rdi
0x1800557c5  push    r12
0x1800557c7  push    r14
0x1800557c9  push    r15
0x1800557cb  mov     rbp, rsp
0x1800557ce  sub     rsp, 50h
0x1800557d2  xor     r14d, r14d
0x1800557d5  xor     esi, esi
0x1800557d7  mov     rcx, r9; pszPath
0x1800557da  mov     [rbp+var_10], r14
0x1800557de  mov     [rbp+pszStr1], rsi
0x1800557e2  mov     rdi, r9
0x1800557e5  mov     r12d, r8d
0x1800557e8  mov     rbx, rdx
0x1800557eb  call    cs:__imp_PathFindFileNameW
0x1800557f1  lea     r9, [rbp+var_18]
0x1800557f5  mov     [rbp+var_18], rsi
0x1800557f9  mov     r15, rax
0x1800557fc  lea     r8d, [r14+1]
0x180055800  mov     rax, [rbx]
0x180055803  mov     rdx, rdi
0x180055806  mov     rcx, rbx
0x180055809  mov     rax, [rax+38h]
0x18005580d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055812  test    eax, eax
0x180055814  js      loc_180055959
0x18005581a  mov     dword ptr [rbp+pv], esi
0x18005581d  mov     [rbp+arg_8], rsi
0x180055821  test    rsi, rsi
0x180055824  jnz     loc_1800558CD
0x18005582a  mov     rcx, [rbp+var_18]
0x18005582e  lea     r9, [rbp+pv]
0x180055832  lea     r8, [rbp+arg_8]
0x180055836  lea     edx, [rsi+1]
0x180055839  mov     rax, [rcx]
0x18005583c  mov     rax, [rax+18h]
0x180055840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055845  test    eax, eax
0x180055847  jnz     loc_1800558CD
0x18005584d  test    r14, r14
0x180055850  jnz     short loc_180055865
0x180055852  mov     r14, [rbp+arg_8]
0x180055856  mov     rcx, r14
0x180055859  mov     rax, [r14]
0x18005585c  mov     rax, [rax+8]
0x180055860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055865  mov     rcx, [rbp+arg_8]
0x180055869  lea     rdx, [rbp+pszStr1]
0x18005586d  mov     [rbp+pszStr1], 0
0x180055875  mov     rax, [rcx]
0x180055878  mov     rax, [rax+20h]
0x18005587c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055881  mov     ebx, eax
0x180055883  test    eax, eax
0x180055885  js      short loc_1800558B5
0x180055887  mov     rcx, [rbp+pszStr1]; pszStr1
0x18005588b  mov     rdx, r15; pszStr2
0x18005588e  call    cs:__imp_StrCmpICW
0x180055894  test    eax, eax
0x180055896  jnz     short loc_1800558AB
0x180055898  mov     rsi, [rbp+arg_8]
0x18005589c  mov     rcx, [rsi]
0x18005589f  mov     rax, [rcx+8]
0x1800558a3  mov     rcx, rsi
0x1800558a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558ab  mov     rcx, [rbp+pszStr1]; pv
0x1800558af  call    cs:__imp_CoTaskMemFree
0x1800558b5  mov     rcx, [rbp+arg_8]
0x1800558b9  mov     rax, [rcx]
0x1800558bc  mov     rax, [rax+10h]
0x1800558c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558c5  test    ebx, ebx
0x1800558c7  jns     loc_180055821
0x1800558cd  mov     rcx, [rbp+var_18]
0x1800558d1  mov     [rbp+pszStr1], rsi
0x1800558d5  mov     [rbp+var_10], r14
0x1800558d9  mov     rax, [rcx]
0x1800558dc  mov     rax, [rax+10h]
0x1800558e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558e5  test    rsi, rsi
0x1800558e8  jnz     short loc_180055905
0x1800558ea  test    r14, r14
0x1800558ed  jz      short loc_180055959
0x1800558ef  mov     rax, [r14]
0x1800558f2  mov     rcx, r14
0x1800558f5  mov     rsi, r14
0x1800558f8  mov     [rbp+pszStr1], r14
0x1800558fc  mov     rax, [rax+8]
0x180055900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055905  mov     rax, [rsi]
0x180055908  mov     rcx, rsi
0x18005590b  mov     rdx, [rbp+arg_20]
0x18005590f  mov     rax, [rax+48h]
0x180055913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055918  mov     ebx, eax
0x18005591a  test    eax, eax
0x18005591c  js      short loc_18005595E
0x18005591e  mov     [rbp+pv], 0
0x180055926  lea     rdx, [rbp+pv]
0x18005592a  mov     rax, [rsi]
0x18005592d  mov     rcx, rsi
0x180055930  mov     rax, [rax+20h]
0x180055934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055939  mov     ebx, eax
0x18005593b  test    eax, eax
0x18005593d  js      short loc_18005595E
0x18005593f  mov     r8, [rbp+pv]; unsigned __int16 *
0x180055943  mov     edx, r12d; enum DEF_SHARE_ID
0x180055946  call    ?_SetShareName@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEBG@Z; CSharingConfiguration::_SetShareName(DEF_SHARE_ID,ushort const *)
0x18005594b  mov     rcx, [rbp+pv]; pv
0x18005594f  mov     ebx, eax
0x180055951  call    cs:__imp_CoTaskMemFree
0x180055957  jmp     short loc_18005595E
0x180055959  mov     ebx, 80070002h
0x18005595e  lea     rcx, [rbp+var_10]
0x180055962  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180055967  lea     rcx, [rbp+pszStr1]
0x18005596b  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180055970  lea     r11, [rsp+50h+var_s0]
0x180055975  mov     eax, ebx
0x180055977  mov     rbx, [r11+40h]
0x18005597b  mov     rsi, [r11+48h]
0x18005597f  mov     rsp, r11
0x180055982  pop     r15
0x180055984  pop     r14
0x180055986  pop     r12
0x180055988  pop     rdi
0x180055989  pop     rbp
0x18005598a  retn
```
