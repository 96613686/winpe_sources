# IsolationAwareLoadLibraryW

- ea: `0x1800e3b40`
- end: `0x1800e3bee`
- name: `IsolationAwareLoadLibraryW`
- size: `174`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800e3b40`
- `0x1800e3db4`
- `0x18018c224`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e3bc4`
- `KERNEL32!GetLastError` at `0x1800e3bc4`
- `KERNEL32!SetLastError` at `0x1800e3be3`
- `KERNEL32!SetLastError` at `0x1800e3be3`
- `KERNEL32!DeactivateActCtx` at `0x1800e3bd7`
- `KERNEL32!DeactivateActCtx` at `0x1800e3bd7`
- `KERNEL32!LoadLibraryW` at `0x1800e3b97`
- `KERNEL32!LoadLibraryW` at `0x1800e3b97`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  BOOL v5; // edi
  DWORD LastError; // esi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v4 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    v5 = LibraryW == 0;
    if ( LibraryW )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x1800e3b40  mov     rax, rsp
0x1800e3b43  mov     [rax+8], rbx
0x1800e3b47  mov     [rax+18h], rsi
0x1800e3b4b  push    rdi
0x1800e3b4c  sub     rsp, 30h
0x1800e3b50  mov     rbx, rcx
0x1800e3b53  mov     qword ptr [rax-18h], 0
0x1800e3b5b  mov     qword ptr [rax+10h], 0
0x1800e3b63  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800e3b6a  jnz     short loc_1800E3B94
0x1800e3b6c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800e3b73  jnz     short loc_1800E3B94
0x1800e3b75  lea     rcx, [rax+10h]; lpCookie
0x1800e3b79  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800e3b7e  test    eax, eax
0x1800e3b80  jnz     short loc_1800E3B94
0x1800e3b82  xor     eax, eax
0x1800e3b84  mov     rbx, [rsp+38h+arg_0]
0x1800e3b89  mov     rsi, [rsp+38h+arg_10]
0x1800e3b8e  add     rsp, 30h
0x1800e3b92  pop     rdi
0x1800e3b93  retn
0x1800e3b94  mov     rcx, rbx; lpLibFileName
0x1800e3b97  call    cs:__imp_LoadLibraryW
0x1800e3b9d  mov     rbx, rax
0x1800e3ba0  mov     [rsp+38h+var_18], rax
0x1800e3ba5  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800e3bac  jz      short loc_1800E3BB7
0x1800e3bae  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800e3bb5  jnz     short loc_1800E3BE9
0x1800e3bb7  xor     edi, edi
0x1800e3bb9  test    rbx, rbx
0x1800e3bbc  setz    dil
0x1800e3bc0  test    edi, edi
0x1800e3bc2  jz      short loc_1800E3BCE
0x1800e3bc4  call    cs:__imp_GetLastError
0x1800e3bca  mov     esi, eax
0x1800e3bcc  jmp     short loc_1800E3BD0
0x1800e3bce  xor     esi, esi
0x1800e3bd0  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800e3bd5  xor     ecx, ecx; dwFlags
0x1800e3bd7  call    cs:__imp_DeactivateActCtx
0x1800e3bdd  test    edi, edi
0x1800e3bdf  jz      short loc_1800E3BE9
0x1800e3be1  mov     ecx, esi; dwErrCode
0x1800e3be3  call    cs:__imp_SetLastError
0x1800e3be9  mov     rax, rbx
0x1800e3bec  jmp     short loc_1800E3B84
0x1801a821c  push    rbx
0x1801a821e  push    rbp
0x1801a821f  push    rdi
0x1801a8220  sub     rsp, 20h
0x1801a8224  mov     rbp, rdx
0x1801a8227  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1801a822e  jz      short loc_1801A8239
0x1801a8230  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1801a8237  jnz     short loc_1801A826B
0x1801a8239  xor     ebx, ebx
0x1801a823b  cmp     [rbp+20h], rbx
0x1801a823f  setz    bl
0x1801a8242  test    ebx, ebx
0x1801a8244  jz      short loc_1801A8250
0x1801a8246  call    cs:__imp_GetLastError
0x1801a824c  mov     edi, eax
0x1801a824e  jmp     short loc_1801A8252
0x1801a8250  xor     edi, edi
0x1801a8252  mov     rdx, [rbp+48h]; ulCookie
0x1801a8256  xor     ecx, ecx; dwFlags
0x1801a8258  call    cs:__imp_DeactivateActCtx
0x1801a825e  test    ebx, ebx
0x1801a8260  jz      short loc_1801A826B
0x1801a8262  mov     ecx, edi; dwErrCode
0x1801a8264  call    cs:__imp_SetLastError
0x1801a826a  nop
0x1801a826b  add     rsp, 20h
0x1801a826f  pop     rdi
0x1801a8270  pop     rbp
0x1801a8271  pop     rbx
0x1801a8272  retn
```
