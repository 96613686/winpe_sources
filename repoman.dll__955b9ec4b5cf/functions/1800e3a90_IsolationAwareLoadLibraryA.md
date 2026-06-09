# IsolationAwareLoadLibraryA

- ea: `0x1800e3a90`
- end: `0x1800e3b3e`
- name: `IsolationAwareLoadLibraryA`
- size: `174`
- prototype: `HMODULE __fastcall(LPCSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800e3a90`
- `0x1800e3db4`
- `0x18018c224`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e3b14`
- `KERNEL32!GetLastError` at `0x1800e3b14`
- `KERNEL32!SetLastError` at `0x1800e3b33`
- `KERNEL32!SetLastError` at `0x1800e3b33`
- `KERNEL32!DeactivateActCtx` at `0x1800e3b27`
- `KERNEL32!DeactivateActCtx` at `0x1800e3b27`
- `KERNEL32!LoadLibraryA` at `0x1800e3ae7`
- `KERNEL32!LoadLibraryA` at `0x1800e3ae7`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryA(LPCSTR lpLibFileName)
{
  HMODULE LibraryA; // rax
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
  LibraryA = LoadLibraryA(lpLibFileName);
  v4 = LibraryA;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    v5 = LibraryA == 0;
    if ( LibraryA )
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
0x1800e3a90  mov     rax, rsp
0x1800e3a93  mov     [rax+8], rbx
0x1800e3a97  mov     [rax+18h], rsi
0x1800e3a9b  push    rdi
0x1800e3a9c  sub     rsp, 30h
0x1800e3aa0  mov     rbx, rcx
0x1800e3aa3  mov     qword ptr [rax-18h], 0
0x1800e3aab  mov     qword ptr [rax+10h], 0
0x1800e3ab3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800e3aba  jnz     short loc_1800E3AE4
0x1800e3abc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800e3ac3  jnz     short loc_1800E3AE4
0x1800e3ac5  lea     rcx, [rax+10h]; lpCookie
0x1800e3ac9  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800e3ace  test    eax, eax
0x1800e3ad0  jnz     short loc_1800E3AE4
0x1800e3ad2  xor     eax, eax
0x1800e3ad4  mov     rbx, [rsp+38h+arg_0]
0x1800e3ad9  mov     rsi, [rsp+38h+arg_10]
0x1800e3ade  add     rsp, 30h
0x1800e3ae2  pop     rdi
0x1800e3ae3  retn
0x1800e3ae4  mov     rcx, rbx; lpLibFileName
0x1800e3ae7  call    cs:__imp_LoadLibraryA
0x1800e3aed  mov     rbx, rax
0x1800e3af0  mov     [rsp+38h+var_18], rax
0x1800e3af5  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800e3afc  jz      short loc_1800E3B07
0x1800e3afe  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800e3b05  jnz     short loc_1800E3B39
0x1800e3b07  xor     edi, edi
0x1800e3b09  test    rbx, rbx
0x1800e3b0c  setz    dil
0x1800e3b10  test    edi, edi
0x1800e3b12  jz      short loc_1800E3B1E
0x1800e3b14  call    cs:__imp_GetLastError
0x1800e3b1a  mov     esi, eax
0x1800e3b1c  jmp     short loc_1800E3B20
0x1800e3b1e  xor     esi, esi
0x1800e3b20  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800e3b25  xor     ecx, ecx; dwFlags
0x1800e3b27  call    cs:__imp_DeactivateActCtx
0x1800e3b2d  test    edi, edi
0x1800e3b2f  jz      short loc_1800E3B39
0x1800e3b31  mov     ecx, esi; dwErrCode
0x1800e3b33  call    cs:__imp_SetLastError
0x1800e3b39  mov     rax, rbx
0x1800e3b3c  jmp     short loc_1800E3AD4
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
