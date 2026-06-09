# I_CryptNetGetUserDsStoreUrl

- ea: `0x18001d970`
- end: `0x18001db5c`
- name: `I_CryptNetGetUserDsStoreUrl`
- size: `492`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003640`
- `0x180007c00`
- `0x18000a990`
- `0x180011e40`
- `0x18001d970`
- `0x1800265b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dafb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001db29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dafb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001db29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db04`
- `CRYPT32!CryptMemAlloc` at `0x18001daa6`
- `CRYPT32!CryptMemAlloc` at `0x18001daa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d9b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d9b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d9e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001db21`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001d9e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001db21`

## string_xrefs

- `0x18001d9a9`: `sspicli.dll`

## pseudocode

```c
__int64 __fastcall I_CryptNetGetUserDsStoreUrl(unsigned __int16 *a1, unsigned __int16 **a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbp
  FARPROC ProcAddress; // rax
  unsigned __int8 (__fastcall *v8)(_QWORD, _QWORD, _QWORD); // r14
  unsigned __int16 *v9; // rdi
  unsigned __int8 v10; // al
  __int64 v11; // rbx
  unsigned int v12; // esi
  unsigned __int16 *v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // r14
  DWORD LastError; // ebx
  _DWORD v19[4]; // [rsp+20h] [rbp-268h] BYREF
  unsigned __int16 hMem[264]; // [rsp+30h] [rbp-258h] BYREF

  v19[0] = 260;
  Library = LoadLibraryExW(L"sspicli.dll", 0, 0);
  v5 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "GetUserNameExW");
  v8 = (unsigned __int8 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
  {
    FreeLibrary(v5);
    return 0;
  }
  v9 = hMem;
  v10 = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, _DWORD *))ProcAddress)(1, hMem, v19);
  v11 = -1;
  v12 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 122 && GetLastError() != 234 )
      goto LABEL_23;
    v13 = (unsigned __int16 *)operator new(saturated_mul(v19[0], 2u));
    v9 = v13;
    if ( !v13 )
      goto LABEL_22;
    v12 = v8(1, v13, v19);
  }
  if ( v12 == 1 )
  {
    if ( v9 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v9[v14] );
    }
    else
    {
      LODWORD(v14) = 0;
    }
    if ( a1 )
    {
      do
        ++v11;
      while ( a1[v11] );
    }
    else
    {
      LODWORD(v11) = 0;
    }
    v15 = v14 + 10 + v11;
    v16 = (unsigned __int16 *)CryptMemAlloc(2 * v15);
    v17 = v16;
    if ( v16 )
    {
      StringCchCopyW(v16, v15, L"ldap:///");
      StringCchCatW(v17, v15, v9);
      StringCchCatW(v17, v15, L"?");
      StringCchCatW(v17, v15, a1);
      *a2 = v17;
      goto LABEL_23;
    }
LABEL_22:
    SetLastError(0x8007000E);
    v12 = 0;
  }
LABEL_23:
  LastError = GetLastError();
  if ( v9 != hMem )
    operator delete(v9);
  FreeLibrary(v5);
  SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x18001d970  mov     [rsp+arg_10], rbx
0x18001d975  push    rbp
0x18001d976  push    rsi
0x18001d977  push    rdi
0x18001d978  push    r12
0x18001d97a  push    r13
0x18001d97c  push    r14
0x18001d97e  push    r15
0x18001d980  sub     rsp, 250h
0x18001d987  mov     rax, cs:__security_cookie
0x18001d98e  xor     rax, rsp
0x18001d991  mov     [rsp+288h+var_48], rax
0x18001d999  mov     r12, rdx
0x18001d99c  mov     [rsp+288h+var_268], 104h
0x18001d9a4  mov     r15, rcx
0x18001d9a7  xor     edx, edx; hFile
0x18001d9a9  lea     rcx, aSspicliDll; "sspicli.dll"
0x18001d9b0  xor     r8d, r8d; dwFlags
0x18001d9b3  call    cs:__imp_LoadLibraryExW
0x18001d9b9  xor     r13d, r13d
0x18001d9bc  mov     rbp, rax
0x18001d9bf  test    rax, rax
0x18001d9c2  jnz     short loc_18001D9CB
0x18001d9c4  xor     eax, eax
0x18001d9c6  jmp     loc_18001DB31
0x18001d9cb  lea     rdx, ProcName; "GetUserNameExW"
0x18001d9d2  mov     rcx, rbp; hModule
0x18001d9d5  call    cs:__imp_GetProcAddress
0x18001d9db  mov     r14, rax
0x18001d9de  test    rax, rax
0x18001d9e1  jnz     short loc_18001D9EE
0x18001d9e3  mov     rcx, rbp; hLibModule
0x18001d9e6  call    cs:__imp_FreeLibrary
0x18001d9ec  jmp     short loc_18001D9C4
0x18001d9ee  lea     r8, [rsp+288h+var_268]
0x18001d9f3  mov     ecx, 1
0x18001d9f8  lea     rdx, [rsp+288h+hMem]
0x18001d9fd  lea     rdi, [rsp+288h+hMem]
0x18001da02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da07  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001da0b  movzx   esi, al
0x18001da0e  test    al, al
0x18001da10  jnz     short loc_18001DA6A
0x18001da12  call    cs:__imp_GetLastError
0x18001da18  cmp     eax, 7Ah ; 'z'
0x18001da1b  jz      short loc_18001DA2E
0x18001da1d  call    cs:__imp_GetLastError
0x18001da23  cmp     eax, 0EAh
0x18001da28  jnz     loc_18001DB04
0x18001da2e  mov     ecx, [rsp+288h+var_268]
0x18001da32  mov     eax, 2
0x18001da37  mul     rcx
0x18001da3a  cmovb   rax, rbx
0x18001da3e  mov     rcx, rax; uBytes
0x18001da41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001da46  mov     rdi, rax
0x18001da49  test    rax, rax
0x18001da4c  jz      loc_18001DAF6
0x18001da52  mov     rdx, rax
0x18001da55  lea     r8, [rsp+288h+var_268]
0x18001da5a  mov     rax, r14
0x18001da5d  mov     ecx, 1
0x18001da62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da67  movzx   esi, al
0x18001da6a  cmp     esi, 1
0x18001da6d  jnz     loc_18001DB04
0x18001da73  test    rdi, rdi
0x18001da76  jz      short loc_18001DA87
0x18001da78  mov     rax, rbx
0x18001da7b  inc     rax
0x18001da7e  cmp     [rdi+rax*2], r13w
0x18001da83  jnz     short loc_18001DA7B
0x18001da85  jmp     short loc_18001DA8A
0x18001da87  mov     eax, r13d
0x18001da8a  test    r15, r15
0x18001da8d  jz      short loc_18001DA9B
0x18001da8f  inc     rbx
0x18001da92  cmp     [r15+rbx*2], r13w
0x18001da97  jnz     short loc_18001DA8F
0x18001da99  jmp     short loc_18001DA9E
0x18001da9b  mov     ebx, r13d
0x18001da9e  add     eax, 0Ah
0x18001daa1  add     ebx, eax
0x18001daa3  lea     ecx, [rbx+rbx]; cbSize
0x18001daa6  call    cs:__imp_CryptMemAlloc
0x18001daac  mov     r14, rax
0x18001daaf  test    rax, rax
0x18001dab2  jz      short loc_18001DAF6
0x18001dab4  lea     r8, aLdap_2; "ldap:///"
0x18001dabb  mov     edx, ebx; unsigned __int64
0x18001dabd  mov     rcx, rax; unsigned __int16 *
0x18001dac0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001dac5  mov     r8, rdi; unsigned __int16 *
0x18001dac8  mov     edx, ebx; unsigned __int64
0x18001daca  mov     rcx, r14; unsigned __int16 *
0x18001dacd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dad2  lea     r8, asc_180029BF0; "?"
0x18001dad9  mov     edx, ebx; unsigned __int64
0x18001dadb  mov     rcx, r14; unsigned __int16 *
0x18001dade  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dae3  mov     r8, r15; unsigned __int16 *
0x18001dae6  mov     edx, ebx; unsigned __int64
0x18001dae8  mov     rcx, r14; unsigned __int16 *
0x18001daeb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001daf0  mov     [r12], r14
0x18001daf4  jmp     short loc_18001DB04
0x18001daf6  mov     ecx, 8007000Eh; dwErrCode
0x18001dafb  call    cs:__imp_SetLastError
0x18001db01  mov     esi, r13d
0x18001db04  call    cs:__imp_GetLastError
0x18001db0a  mov     ebx, eax
0x18001db0c  lea     rax, [rsp+288h+hMem]
0x18001db11  cmp     rdi, rax
0x18001db14  jz      short loc_18001DB1E
0x18001db16  mov     rcx, rdi; hMem
0x18001db19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001db1e  mov     rcx, rbp; hLibModule
0x18001db21  call    cs:__imp_FreeLibrary
0x18001db27  mov     ecx, ebx; dwErrCode
0x18001db29  call    cs:__imp_SetLastError
0x18001db2f  mov     eax, esi
0x18001db31  mov     rcx, [rsp+288h+var_48]
0x18001db39  xor     rcx, rsp; StackCookie
0x18001db3c  call    __security_check_cookie
0x18001db41  mov     rbx, [rsp+288h+arg_10]
0x18001db49  add     rsp, 250h
0x18001db50  pop     r15
0x18001db52  pop     r14
0x18001db54  pop     r13
0x18001db56  pop     r12
0x18001db58  pop     rdi
0x18001db59  pop     rsi
0x18001db5a  pop     rbp
0x18001db5b  retn
```
