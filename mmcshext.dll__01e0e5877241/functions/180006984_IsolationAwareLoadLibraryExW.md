# IsolationAwareLoadLibraryExW

- ea: `0x180006984`
- end: `0x180006a3b`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004008`
- `0x180004ed4`

## callees

- `0x180006984`
- `0x180006a44`
- `0x180007b88`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006a30`
- `KERNEL32!SetLastError` at `0x180006a30`
- `KERNEL32!DeactivateActCtx` at `0x180006a24`
- `KERNEL32!DeactivateActCtx` at `0x180006a24`
- `KERNEL32!GetLastError` at `0x180006a0f`
- `KERNEL32!GetLastError` at `0x180006a0f`
- `KERNEL32!LoadLibraryExW` at `0x1800069e7`
- `KERNEL32!LoadLibraryExW` at `0x1800069e7`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName, __int64 a2, DWORD a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  int v8; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, a3);
  v7 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      v8 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x180006984  mov     rax, rsp
0x180006987  mov     [rax+8], rbx
0x18000698b  mov     [rax+18h], rsi
0x18000698f  mov     [rax+10h], rdx
0x180006993  push    rdi
0x180006994  sub     rsp, 30h
0x180006998  mov     ebx, r8d
0x18000699b  mov     rdi, rcx
0x18000699e  mov     qword ptr [rax-18h], 0
0x1800069a6  mov     qword ptr [rax+10h], 0
0x1800069ae  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800069b5  jnz     short loc_1800069DF
0x1800069b7  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800069be  jnz     short loc_1800069DF
0x1800069c0  lea     rcx, [rax+10h]; lpCookie
0x1800069c4  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800069c9  test    eax, eax
0x1800069cb  jnz     short loc_1800069DF
0x1800069cd  xor     eax, eax
0x1800069cf  mov     rbx, [rsp+38h+arg_0]
0x1800069d4  mov     rsi, [rsp+38h+arg_10]
0x1800069d9  add     rsp, 30h
0x1800069dd  pop     rdi
0x1800069de  retn
0x1800069df  mov     r8d, ebx; dwFlags
0x1800069e2  xor     edx, edx; hFile
0x1800069e4  mov     rcx, rdi; lpLibFileName
0x1800069e7  call    cs:__imp_LoadLibraryExW
0x1800069ed  mov     rbx, rax
0x1800069f0  mov     [rsp+38h+var_18], rax
0x1800069f5  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800069fc  jz      short loc_180006A07
0x1800069fe  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006a05  jnz     short loc_180006A36
0x180006a07  test    rbx, rbx
0x180006a0a  jnz     short loc_180006A19
0x180006a0c  lea     esi, [rbx+1]
0x180006a0f  call    cs:__imp_GetLastError
0x180006a15  mov     edi, eax
0x180006a17  jmp     short loc_180006A1D
0x180006a19  xor     esi, esi
0x180006a1b  xor     edi, edi
0x180006a1d  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180006a22  xor     ecx, ecx; dwFlags
0x180006a24  call    cs:__imp_DeactivateActCtx
0x180006a2a  test    esi, esi
0x180006a2c  jz      short loc_180006A36
0x180006a2e  mov     ecx, edi; dwErrCode
0x180006a30  call    cs:__imp_SetLastError
0x180006a36  mov     rax, rbx
0x180006a39  jmp     short loc_1800069CF
0x18000abc1  push    rbx
0x18000abc3  push    rbp
0x18000abc4  push    rdi
0x18000abc5  sub     rsp, 20h
0x18000abc9  mov     rbp, rdx
0x18000abcc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000abd3  jz      short loc_18000ABDE
0x18000abd5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000abdc  jnz     short loc_18000AC11
0x18000abde  cmp     qword ptr [rbp+20h], 0
0x18000abe3  jnz     short loc_18000ABF4
0x18000abe5  mov     edi, 1
0x18000abea  call    cs:__imp_GetLastError
0x18000abf0  mov     ebx, eax
0x18000abf2  jmp     short loc_18000ABF8
0x18000abf4  xor     edi, edi
0x18000abf6  xor     ebx, ebx
0x18000abf8  mov     rdx, [rbp+48h]; ulCookie
0x18000abfc  xor     ecx, ecx; dwFlags
0x18000abfe  call    cs:__imp_DeactivateActCtx
0x18000ac04  test    edi, edi
0x18000ac06  jz      short loc_18000AC11
0x18000ac08  mov     ecx, ebx; dwErrCode
0x18000ac0a  call    cs:__imp_SetLastError
0x18000ac10  nop
0x18000ac11  add     rsp, 20h
0x18000ac15  pop     rdi
0x18000ac16  pop     rbp
0x18000ac17  pop     rbx
0x18000ac18  retn
```
