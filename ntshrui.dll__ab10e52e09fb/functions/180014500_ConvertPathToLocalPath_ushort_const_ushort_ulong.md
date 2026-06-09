# ConvertPathToLocalPath(ushort const *,ushort *,ulong)

- ea: `0x180014500`
- end: `0x18001472b`
- name: `?ConvertPathToLocalPath@@YAJPEBGPEAGK@Z`
- size: `555`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800144b0`
- `0x18005e9c0`

## callees

- `0x180014500`
- `0x18001d2d0`
- `0x1800254e0`
- `0x18002a960`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800145c3`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800145c3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800146f3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800146f3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014544`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014544`
- `SHLWAPI!StrChrW` at `0x18001467b`
- `SHLWAPI!StrChrW` at `0x1800146a6`
- `SHLWAPI!StrChrW` at `0x18001467b`
- `SHLWAPI!StrChrW` at `0x1800146a6`
- `SHLWAPI!PathRemoveBackslashW` at `0x180014631`
- `SHLWAPI!PathRemoveBackslashW` at `0x180014631`

## pseudocode

```c
HRESULT __fastcall ConvertPathToLocalPath(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  size_t v3; // r15
  __int64 v6; // rbx
  WCHAR *v7; // r9
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  int v12; // r14d
  int v13; // edx
  size_t v14; // rdx
  unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // rcx
  HRESULT result; // eax
  const WCHAR *v18; // rbp
  PWSTR v19; // rax
  const unsigned __int16 *v20; // rsi
  const WCHAR *v21; // rbx
  PWSTR v22; // rax
  const WCHAR *v23; // rax
  CShareCache *v24; // rcx
  PCWSTR ppszServer; // [rsp+20h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  v3 = a3;
  *a2 = 0;
  InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
  v6 = 2147483646;
  v7 = pszPath;
  v8 = 2147483646;
  v9 = a1;
  v10 = 260;
  do
  {
    if ( !v8 )
      break;
    if ( !*v9 )
      break;
    *v7++ = *v9++;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = v7 - 1;
  v12 = -2147024774;
  v13 = -2147024774;
  if ( v10 )
  {
    v11 = v7;
    v13 = 0;
  }
  *v11 = 0;
  if ( !v10 )
    return v13;
  ppszServer = 0;
  if ( !PathIsUNCEx(pszPath, &ppszServer)
    || (v18 = ppszServer, (v19 = StrChrW(ppszServer, 0x5Cu)) == 0)
    || (v20 = v19 + 1, *v19 = 0, !v19[1]) )
  {
    v14 = v3;
    if ( (_DWORD)v3 )
    {
      if ( v3 > 0x7FFFFFFF )
      {
        v12 = -2147024809;
        *a2 = 0;
        return v12;
      }
      v15 = a2;
      do
      {
        if ( !v6 )
          break;
        if ( !*a1 )
          break;
        *v15++ = *a1++;
        --v6;
        --v14;
      }
      while ( v14 );
      v16 = v15 - 1;
      if ( v14 )
      {
        v16 = v15;
        v12 = 0;
      }
      *v16 = 0;
    }
    else
    {
      v12 = -2147024809;
    }
    if ( v12 >= 0 )
      PathRemoveBackslashW(a2);
    return v12;
  }
  v21 = 0;
  v22 = StrChrW(v19 + 1, 0x5Cu);
  if ( v22 )
  {
    *v22 = 0;
    v23 = v22 + 1;
    if ( *v23 )
      v21 = v23;
  }
  if ( !(unsigned int)SHIsThisComputerByNameOnly(v18) || !CShareCache::IsExistingShare(v24, v20, a2, v3) )
    return 1;
  result = 0;
  if ( v21 )
    return PathCchAppend(a2, v3, v21);
  return result;
}

```

## disassembly

```asm
0x180014500  push    rbx
0x180014502  push    rdi
0x180014503  push    r12
0x180014505  push    r14
0x180014507  push    r15
0x180014509  sub     rsp, 250h
0x180014510  mov     rax, cs:__security_cookie
0x180014517  xor     rax, rsp
0x18001451a  mov     [rsp+278h+var_38], rax
0x180014522  xor     eax, eax
0x180014524  mov     r15d, r8d
0x180014527  mov     [rdx], ax
0x18001452a  mov     r12, rdx
0x18001452d  mov     rdi, rcx
0x180014530  lea     rdx, _OneTimeInit; InitFn
0x180014537  xor     r9d, r9d; Context
0x18001453a  lea     rcx, InitOnce; InitOnce
0x180014541  xor     r8d, r8d; Parameter
0x180014544  call    cs:__imp_InitOnceExecuteOnce
0x18001454a  mov     ebx, 7FFFFFFEh
0x18001454f  lea     r9, [rsp+278h+pszPath]
0x180014554  mov     ecx, ebx
0x180014556  mov     rdx, rdi
0x180014559  mov     r8d, 104h
0x18001455f  nop
0x180014560  test    rcx, rcx
0x180014563  jz      short loc_180014582
0x180014565  movzx   eax, word ptr [rdx]
0x180014568  test    ax, ax
0x18001456b  jz      short loc_180014582
0x18001456d  mov     [r9], ax
0x180014571  add     rdx, 2
0x180014575  add     r9, 2
0x180014579  dec     rcx
0x18001457c  sub     r8, 1
0x180014580  jnz     short loc_180014560
0x180014582  xor     eax, eax
0x180014584  lea     rcx, [r9-2]
0x180014588  test    r8, r8
0x18001458b  mov     r14d, 8007007Ah
0x180014591  mov     edx, r14d
0x180014594  cmovnz  rcx, r9
0x180014598  cmovnz  edx, eax
0x18001459b  mov     [rcx], ax
0x18001459e  jz      loc_18001466A
0x1800145a4  mov     [rsp+278h+arg_0], rbp
0x1800145ac  lea     rdx, [rsp+278h+ppszServer]; ppszServer
0x1800145b1  lea     rcx, [rsp+278h+pszPath]; pszPath
0x1800145b6  mov     [rsp+278h+arg_18], rsi
0x1800145be  mov     [rsp+278h+ppszServer], rax
0x1800145c3  call    cs:__imp_PathIsUNCEx
0x1800145c9  test    eax, eax
0x1800145cb  jnz     loc_18001466E
0x1800145d1  mov     rdx, r15
0x1800145d4  test    r15d, r15d
0x1800145d7  jz      loc_180014710
0x1800145dd  cmp     rdx, 7FFFFFFFh
0x1800145e4  ja      loc_180014708
0x1800145ea  mov     r8, r12
0x1800145ed  nop     dword ptr [rax]
0x1800145f0  test    rbx, rbx
0x1800145f3  jz      short loc_180014612
0x1800145f5  movzx   eax, word ptr [rdi]
0x1800145f8  test    ax, ax
0x1800145fb  jz      short loc_180014612
0x1800145fd  mov     [r8], ax
0x180014601  add     rdi, 2
0x180014605  add     r8, 2
0x180014609  dec     rbx
0x18001460c  sub     rdx, 1
0x180014610  jnz     short loc_1800145F0
0x180014612  test    rdx, rdx
0x180014615  lea     rcx, [r8-2]
0x180014619  cmovnz  rcx, r8
0x18001461d  xor     eax, eax
0x18001461f  test    rdx, rdx
0x180014622  cmovnz  r14d, eax
0x180014626  mov     [rcx], ax
0x180014629  test    r14d, r14d
0x18001462c  js      short loc_180014637
0x18001462e  mov     rcx, r12; pszPath
0x180014631  call    cs:__imp_PathRemoveBackslashW
0x180014637  mov     eax, r14d
0x18001463a  mov     rbp, [rsp+278h+arg_0]
0x180014642  mov     rsi, [rsp+278h+arg_18]
0x18001464a  mov     rcx, [rsp+278h+var_38]
0x180014652  xor     rcx, rsp; StackCookie
0x180014655  call    __security_check_cookie
0x18001465a  add     rsp, 250h
0x180014661  pop     r15
0x180014663  pop     r14
0x180014665  pop     r12
0x180014667  pop     rdi
0x180014668  pop     rbx
0x180014669  retn
0x18001466a  mov     eax, edx
0x18001466c  jmp     short loc_18001464A
0x18001466e  mov     rbp, [rsp+278h+ppszServer]
0x180014673  mov     edx, 5Ch ; '\'; wMatch
0x180014678  mov     rcx, rbp; pszStart
0x18001467b  call    cs:__imp_StrChrW
0x180014681  test    rax, rax
0x180014684  jz      loc_1800145D1
0x18001468a  xor     ecx, ecx
0x18001468c  lea     rsi, [rax+2]
0x180014690  mov     [rax], cx
0x180014693  cmp     [rsi], cx
0x180014696  jz      loc_1800145D1
0x18001469c  mov     edx, 5Ch ; '\'; wMatch
0x1800146a1  mov     rcx, rsi; pszStart
0x1800146a4  xor     ebx, ebx
0x1800146a6  call    cs:__imp_StrChrW
0x1800146ac  test    rax, rax
0x1800146af  jz      short loc_1800146C1
0x1800146b1  xor     ecx, ecx
0x1800146b3  mov     [rax], cx
0x1800146b6  add     rax, 2
0x1800146ba  cmp     [rax], cx
0x1800146bd  cmovnz  rbx, rax
0x1800146c1  mov     rcx, rbp; pszStr2
0x1800146c4  call    ?SHIsThisComputerByNameOnly@@YAHPEBG@Z; SHIsThisComputerByNameOnly(ushort const *)
0x1800146c9  test    eax, eax
0x1800146cb  jz      short loc_1800146FE
0x1800146cd  mov     r9d, r15d; int
0x1800146d0  mov     r8, r12; unsigned __int16 *
0x1800146d3  mov     rdx, rsi; unsigned __int16 *
0x1800146d6  call    ?IsExistingShare@CShareCache@@QEAAHPEBGPEAGH@Z; CShareCache::IsExistingShare(ushort const *,ushort *,int)
0x1800146db  test    eax, eax
0x1800146dd  jz      short loc_1800146FE
0x1800146df  xor     eax, eax
0x1800146e1  test    rbx, rbx
0x1800146e4  jz      loc_18001463A
0x1800146ea  mov     rdx, r15; cchPath
0x1800146ed  mov     r8, rbx; pszMore
0x1800146f0  mov     rcx, r12; pszPath
0x1800146f3  call    cs:__imp_PathCchAppend
0x1800146f9  jmp     loc_18001463A
0x1800146fe  mov     eax, 1
0x180014703  jmp     loc_18001463A
0x180014708  mov     r14d, 80070057h
0x18001470e  jmp     short loc_18001471F
0x180014710  mov     r14d, 80070057h
0x180014716  test    r15d, r15d
0x180014719  jz      loc_180014629
0x18001471f  xor     eax, eax
0x180014721  mov     [r12], ax
0x180014726  jmp     loc_180014637
```
