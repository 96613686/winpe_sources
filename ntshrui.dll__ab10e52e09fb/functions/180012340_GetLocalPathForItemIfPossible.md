# GetLocalPathForItemIfPossible

- ea: `0x180012340`
- end: `0x180012672`
- name: `GetLocalPathForItemIfPossible`
- size: `818`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180010a84`
- `0x180012160`
- `0x18001d370`
- `0x180034560`
- `0x1800509c8`
- `0x180055bf0`
- `0x1800589c8`
- `0x180058ae4`
- `0x18005b080`
- `0x18005b274`
- `0x18006d410`

## callees

- `0x180012340`
- `0x18001d2d0`
- `0x1800254e0`
- `0x18002a960`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800124e0`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800124e0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001265d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001265d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012552`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001246e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001246e`
- `SHCORE!SHStrDupW` at `0x180012545`
- `SHCORE!SHStrDupW` at `0x180012545`
- `SHLWAPI!StrChrW` at `0x1800125de`
- `SHLWAPI!StrChrW` at `0x180012606`
- `SHLWAPI!StrChrW` at `0x1800125de`
- `SHLWAPI!StrChrW` at `0x180012606`
- `SHLWAPI!PathRemoveBackslashW` at `0x180012533`
- `SHLWAPI!PathRemoveBackslashW` at `0x180012533`

## pseudocode

```c
__int64 __fastcall GetLocalPathForItemIfPossible(_QWORD *a1, LPWSTR *a2)
{
  __int64 (__fastcall **v2)(_QWORD *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(_QWORD *, GUID *, __int64 *); // rax
  int v6; // r12d
  int v7; // edi
  WCHAR *v8; // rdi
  __int64 v9; // rbx
  WCHAR *v10; // r9
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r8
  WCHAR *v14; // rdx
  WCHAR *v15; // rcx
  WCHAR *v16; // rdx
  WCHAR *v17; // rcx
  HRESULT v18; // ebx
  unsigned int v19; // ebx
  __int64 result; // rax
  const WCHAR *v21; // r15
  PWSTR v22; // rax
  const unsigned __int16 *v23; // r14
  const WCHAR *v24; // rbx
  PWSTR v25; // rax
  const WCHAR *v26; // rax
  CShareCache *v27; // rcx
  PCWSTR ppszServer; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR psz[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  *a2 = 0;
  v2 = (__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*a1;
  pv = 0;
  v29 = 0;
  v5 = v2[3];
  ppszServer = 0;
  if ( ((int (__fastcall *)(_QWORD *, _QWORD, const GUID *, GUID *, PCWSTR *))v5)(
         a1,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         &ppszServer) >= 0 )
  {
    v31 = 0;
    v7 = (*(__int64 (__fastcall **)(PCWSTR, __int64 *))(*(_QWORD *)ppszServer + 32LL))(ppszServer, &v31);
    if ( v7 >= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v31)(
             v31,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &v29);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)ppszServer + 16LL))(ppszServer);
    if ( v7 >= 0 )
      goto LABEL_7;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*a1)(
         a1,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v29);
  if ( v6 >= 0 )
  {
LABEL_7:
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v29 + 40LL))(v29, 2147844096LL, &pv);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( v6 < 0 )
    return (unsigned int)v6;
  v8 = (WCHAR *)pv;
  psz[0] = 0;
  InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
  v9 = 2147483646;
  v10 = pszPath;
  v11 = 260;
  v12 = 2147483646;
  v13 = 260;
  v14 = v8;
  do
  {
    if ( !v12 )
      break;
    if ( !*v14 )
      break;
    *v10++ = *v14++;
    --v12;
    --v13;
  }
  while ( v13 );
  v15 = v10 - 1;
  if ( v13 )
    v15 = v10;
  *v15 = 0;
  if ( v13 )
  {
    ppszServer = 0;
    if ( !PathIsUNCEx(pszPath, &ppszServer)
      || (v21 = ppszServer, (v22 = StrChrW(ppszServer, 0x5Cu)) == 0)
      || (*v22 = 0, v23 = v22 + 1, !v22[1]) )
    {
      v16 = psz;
      do
      {
        if ( !v9 )
          break;
        if ( !*v8 )
          break;
        *v16++ = *v8++;
        --v9;
        --v11;
      }
      while ( v11 );
      v17 = v16 - 1;
      v18 = -2147024774;
      if ( v11 )
      {
        v17 = v16;
        v18 = 0;
      }
      *v17 = 0;
      if ( v11 )
        PathRemoveBackslashW(psz);
      goto LABEL_25;
    }
    v24 = 0;
    v25 = StrChrW(v22 + 1, 0x5Cu);
    if ( v25 )
    {
      *v25 = 0;
      v26 = v25 + 1;
      if ( *v26 )
        v24 = v26;
    }
    if ( (unsigned int)SHIsThisComputerByNameOnly(v21) && CShareCache::IsExistingShare(v27, v23, psz, 260) )
    {
      if ( !v24 )
        goto LABEL_26;
      v18 = PathCchAppend(psz, 0x104u, v24);
LABEL_25:
      if ( !v18 )
      {
LABEL_26:
        v19 = SHStrDupW(psz, a2);
        CoTaskMemFree(pv);
        return v19;
      }
    }
  }
  result = (unsigned int)v6;
  *a2 = (LPWSTR)pv;
  return result;
}

```

## disassembly

```asm
0x180012340  push    rbp
0x180012342  push    rbx
0x180012343  push    rdi
0x180012344  push    r12
0x180012346  push    r13
0x180012348  push    r14
0x18001234a  lea     rbp, [rsp-388h]
0x180012352  sub     rsp, 488h
0x180012359  mov     rax, cs:__security_cookie
0x180012360  xor     rax, rsp
0x180012363  mov     [rbp+3B0h+var_40], rax
0x18001236a  xor     r14d, r14d
0x18001236d  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x180012374  mov     [rdx], r14
0x180012377  lea     r8, BHID_SFObject
0x18001237e  mov     rax, [rcx]
0x180012381  mov     rbx, rcx
0x180012384  lea     rcx, [rsp+4B0h+ppszServer]
0x180012389  mov     [rsp+4B0h+pv], r14
0x18001238e  mov     r13, rdx
0x180012391  mov     [rsp+4B0h+var_490], rcx
0x180012396  xor     edx, edx
0x180012398  mov     [rsp+4B0h+var_478], r14
0x18001239d  mov     rax, [rax+18h]
0x1800123a1  mov     rcx, rbx
0x1800123a4  mov     [rsp+4B0h+ppszServer], r14
0x1800123a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ae  test    eax, eax
0x1800123b0  jns     short loc_1800123D5
0x1800123b2  mov     rax, [rbx]
0x1800123b5  lea     r8, [rsp+4B0h+var_478]
0x1800123ba  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800123c1  mov     rcx, rbx
0x1800123c4  mov     rax, [rax]
0x1800123c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123cc  mov     r12d, eax
0x1800123cf  test    eax, eax
0x1800123d1  js      short loc_18001243E
0x1800123d3  jmp     short loc_18001240F
0x1800123d5  mov     rcx, [rsp+4B0h+ppszServer]
0x1800123da  lea     rdx, [rsp+4B0h+var_468]
0x1800123df  mov     [rsp+4B0h+var_468], r14
0x1800123e4  mov     rax, [rcx]
0x1800123e7  mov     rax, [rax+20h]
0x1800123eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123f0  mov     edi, eax
0x1800123f2  test    eax, eax
0x1800123f4  jns     loc_18001259D
0x1800123fa  mov     rcx, [rsp+4B0h+ppszServer]
0x1800123ff  mov     rax, [rcx]
0x180012402  mov     rax, [rax+10h]
0x180012406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240b  test    edi, edi
0x18001240d  js      short loc_1800123B2
0x18001240f  mov     rcx, [rsp+4B0h+var_478]
0x180012414  lea     r8, [rsp+4B0h+pv]
0x180012419  mov     edx, 80058000h
0x18001241e  mov     rax, [rcx]
0x180012421  mov     rax, [rax+28h]
0x180012425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001242a  mov     rcx, [rsp+4B0h+var_478]
0x18001242f  mov     r12d, eax
0x180012432  mov     rax, [rcx]
0x180012435  mov     rax, [rax+10h]
0x180012439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001243e  test    r12d, r12d
0x180012441  js      loc_18001258A
0x180012447  mov     rdi, [rsp+4B0h+pv]
0x18001244c  lea     rdx, _OneTimeInit; InitFn
0x180012453  xor     r9d, r9d; Context
0x180012456  mov     [rsp+4B0h+arg_10], rsi
0x18001245e  xor     r8d, r8d; Parameter
0x180012461  mov     [rsp+4B0h+psz], r14w
0x180012467  lea     rcx, InitOnce; InitOnce
0x18001246e  call    cs:__imp_InitOnceExecuteOnce
0x180012474  mov     ebx, 7FFFFFFEh
0x180012479  lea     r9, [rbp+3B0h+pszPath]
0x180012480  mov     esi, 104h
0x180012485  mov     ecx, ebx
0x180012487  mov     r8d, esi
0x18001248a  mov     rdx, rdi
0x18001248d  nop     dword ptr [rax]
0x180012490  test    rcx, rcx
0x180012493  jz      short loc_1800124B2
0x180012495  movzx   eax, word ptr [rdx]
0x180012498  test    ax, ax
0x18001249b  jz      short loc_1800124B2
0x18001249d  mov     [r9], ax
0x1800124a1  add     rdx, 2
0x1800124a5  add     r9, 2
0x1800124a9  dec     rcx
0x1800124ac  sub     r8, 1
0x1800124b0  jnz     short loc_180012490
0x1800124b2  test    r8, r8
0x1800124b5  mov     [rsp+4B0h+var_30], r15
0x1800124bd  lea     rcx, [r9-2]
0x1800124c1  cmovnz  rcx, r9
0x1800124c5  mov     [rcx], r14w
0x1800124c9  jz      loc_18001258F
0x1800124cf  lea     rdx, [rsp+4B0h+ppszServer]; ppszServer
0x1800124d4  mov     [rsp+4B0h+ppszServer], r14
0x1800124d9  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x1800124e0  call    cs:__imp_PathIsUNCEx
0x1800124e6  test    eax, eax
0x1800124e8  jnz     loc_1800125D1
0x1800124ee  lea     rdx, [rsp+4B0h+psz]
0x1800124f3  test    rbx, rbx
0x1800124f6  jz      short loc_180012514
0x1800124f8  movzx   eax, word ptr [rdi]
0x1800124fb  test    ax, ax
0x1800124fe  jz      short loc_180012514
0x180012500  mov     [rdx], ax
0x180012503  add     rdi, 2
0x180012507  add     rdx, 2
0x18001250b  dec     rbx
0x18001250e  sub     rsi, 1
0x180012512  jnz     short loc_1800124F3
0x180012514  test    rsi, rsi
0x180012517  lea     rcx, [rdx-2]
0x18001251b  mov     ebx, 8007007Ah
0x180012520  cmovnz  rcx, rdx
0x180012524  cmovnz  ebx, r14d
0x180012528  mov     [rcx], r14w
0x18001252c  jz      short loc_180012539
0x18001252e  lea     rcx, [rsp+4B0h+psz]; pszPath
0x180012533  call    cs:__imp_PathRemoveBackslashW
0x180012539  test    ebx, ebx
0x18001253b  jnz     short loc_18001258F
0x18001253d  mov     rdx, r13; ppwsz
0x180012540  lea     rcx, [rsp+4B0h+psz]; psz
0x180012545  call    cs:__imp_SHStrDupW
0x18001254b  mov     rcx, [rsp+4B0h+pv]; pv
0x180012550  mov     ebx, eax
0x180012552  call    cs:__imp_CoTaskMemFree
0x180012558  mov     eax, ebx
0x18001255a  mov     r15, [rsp+4B0h+var_30]
0x180012562  mov     rsi, [rsp+4B0h+arg_10]
0x18001256a  mov     rcx, [rbp+3B0h+var_40]
0x180012571  xor     rcx, rsp; StackCookie
0x180012574  call    __security_check_cookie
0x180012579  add     rsp, 488h
0x180012580  pop     r14
0x180012582  pop     r13
0x180012584  pop     r12
0x180012586  pop     rdi
0x180012587  pop     rbx
0x180012588  pop     rbp
0x180012589  retn
0x18001258a  mov     eax, r12d
0x18001258d  jmp     short loc_18001256A
0x18001258f  mov     rcx, [rsp+4B0h+pv]
0x180012594  mov     eax, r12d
0x180012597  mov     [r13+0], rcx
0x18001259b  jmp     short loc_18001255A
0x18001259d  mov     rcx, [rsp+4B0h+var_468]
0x1800125a2  lea     r8, [rsp+4B0h+var_478]
0x1800125a7  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800125ae  mov     rax, [rcx]
0x1800125b1  mov     rax, [rax]
0x1800125b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b9  mov     rcx, [rsp+4B0h+var_468]
0x1800125be  mov     edi, eax
0x1800125c0  mov     rax, [rcx]
0x1800125c3  mov     rax, [rax+10h]
0x1800125c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cc  jmp     loc_1800123FA
0x1800125d1  mov     r15, [rsp+4B0h+ppszServer]
0x1800125d6  mov     edx, 5Ch ; '\'; wMatch
0x1800125db  mov     rcx, r15; pszStart
0x1800125de  call    cs:__imp_StrChrW
0x1800125e4  test    rax, rax
0x1800125e7  jz      loc_1800124EE
0x1800125ed  mov     [rax], r14w
0x1800125f1  lea     r14, [rax+2]
0x1800125f5  cmp     word ptr [r14], 0
0x1800125fa  jz      short loc_18001266A
0x1800125fc  mov     edx, 5Ch ; '\'; wMatch
0x180012601  mov     rcx, r14; pszStart
0x180012604  xor     ebx, ebx
0x180012606  call    cs:__imp_StrChrW
0x18001260c  test    rax, rax
0x18001260f  jz      short loc_180012621
0x180012611  xor     edx, edx
0x180012613  mov     [rax], dx
0x180012616  add     rax, 2
0x18001261a  cmp     [rax], dx
0x18001261d  cmovnz  rbx, rax
0x180012621  mov     rcx, r15; pszStr2
0x180012624  call    ?SHIsThisComputerByNameOnly@@YAHPEBG@Z; SHIsThisComputerByNameOnly(ushort const *)
0x180012629  test    eax, eax
0x18001262b  jz      loc_18001258F
0x180012631  mov     r9d, esi; int
0x180012634  lea     r8, [rsp+4B0h+psz]; unsigned __int16 *
0x180012639  mov     rdx, r14; unsigned __int16 *
0x18001263c  call    ?IsExistingShare@CShareCache@@QEAAHPEBGPEAGH@Z; CShareCache::IsExistingShare(ushort const *,ushort *,int)
0x180012641  test    eax, eax
0x180012643  jz      loc_18001258F
0x180012649  test    rbx, rbx
0x18001264c  jz      loc_18001253D
0x180012652  mov     r8, rbx; pszMore
0x180012655  lea     rcx, [rsp+4B0h+psz]; pszPath
0x18001265a  mov     rdx, rsi; cchPath
0x18001265d  call    cs:__imp_PathCchAppend
0x180012663  mov     ebx, eax
0x180012665  jmp     loc_180012539
0x18001266a  xor     r14d, r14d
0x18001266d  jmp     loc_1800124EE
```
