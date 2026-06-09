# IsolationAwareLoadLibraryExA

- ea: `0x1800422cc`
- end: `0x180042380`
- name: `IsolationAwareLoadLibraryExA`
- size: `180`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003ff6c`

## callees

- `0x180002b18`
- `0x1800422cc`
- `0x18004f6e0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18004232c`
- `KERNEL32!LoadLibraryExA` at `0x18004232c`
- `KERNEL32!GetLastError` at `0x180042354`
- `KERNEL32!GetLastError` at `0x180042354`
- `KERNEL32!DeactivateActCtx` at `0x180042369`
- `KERNEL32!DeactivateActCtx` at `0x180042369`
- `KERNEL32!SetLastError` at `0x180042375`
- `KERNEL32!SetLastError` at `0x180042375`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExA(LPCSTR lpLibFileName)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  int v5; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExA(lpLibFileName, 0, 0);
  v4 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v5 = 0;
      LastError = 0;
    }
    else
    {
      v5 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v5 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x1800422cc  mov     rax, rsp
0x1800422cf  mov     [rax+8], rbx
0x1800422d3  mov     [rax+18h], rsi
0x1800422d7  mov     [rax+10h], rdx
0x1800422db  push    rdi
0x1800422dc  sub     rsp, 30h
0x1800422e0  mov     rbx, rcx
0x1800422e3  mov     qword ptr [rax-18h], 0
0x1800422eb  mov     qword ptr [rax+10h], 0
0x1800422f3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800422fa  jnz     short loc_180042324
0x1800422fc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180042303  jnz     short loc_180042324
0x180042305  lea     rcx, [rax+10h]; lpCookie
0x180042309  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18004230e  test    eax, eax
0x180042310  jnz     short loc_180042324
0x180042312  xor     eax, eax
0x180042314  mov     rbx, [rsp+38h+arg_0]
0x180042319  mov     rsi, [rsp+38h+arg_10]
0x18004231e  add     rsp, 30h
0x180042322  pop     rdi
0x180042323  retn
0x180042324  xor     r8d, r8d; dwFlags
0x180042327  xor     edx, edx; hFile
0x180042329  mov     rcx, rbx; lpLibFileName
0x18004232c  call    cs:__imp_LoadLibraryExA
0x180042332  mov     rbx, rax
0x180042335  mov     [rsp+38h+var_18], rax
0x18004233a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180042341  jz      short loc_18004234C
0x180042343  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18004234a  jnz     short loc_18004237B
0x18004234c  test    rbx, rbx
0x18004234f  jnz     short loc_18004235E
0x180042351  lea     esi, [rbx+1]
0x180042354  call    cs:__imp_GetLastError
0x18004235a  mov     edi, eax
0x18004235c  jmp     short loc_180042362
0x18004235e  xor     esi, esi
0x180042360  xor     edi, edi
0x180042362  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180042367  xor     ecx, ecx; dwFlags
0x180042369  call    cs:__imp_DeactivateActCtx
0x18004236f  test    esi, esi
0x180042371  jz      short loc_18004237B
0x180042373  mov     ecx, edi; dwErrCode
0x180042375  call    cs:__imp_SetLastError
0x18004237b  mov     rax, rbx
0x18004237e  jmp     short loc_180042314
0x180076126  push    rbx
0x180076128  push    rbp
0x180076129  push    rdi
0x18007612a  sub     rsp, 20h
0x18007612e  mov     rbp, rdx
0x180076131  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180076138  jz      short loc_180076143
0x18007613a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180076141  jnz     short loc_180076176
0x180076143  cmp     qword ptr [rbp+20h], 0
0x180076148  jnz     short loc_180076159
0x18007614a  mov     edi, 1
0x18007614f  call    cs:__imp_GetLastError
0x180076155  mov     ebx, eax
0x180076157  jmp     short loc_18007615D
0x180076159  xor     edi, edi
0x18007615b  xor     ebx, ebx
0x18007615d  mov     rdx, [rbp+48h]; ulCookie
0x180076161  xor     ecx, ecx; dwFlags
0x180076163  call    cs:__imp_DeactivateActCtx
0x180076169  test    edi, edi
0x18007616b  jz      short loc_180076176
0x18007616d  mov     ecx, ebx; dwErrCode
0x18007616f  call    cs:__imp_SetLastError
0x180076175  nop
0x180076176  add     rsp, 20h
0x18007617a  pop     rdi
0x18007617b  pop     rbp
0x18007617c  pop     rbx
0x18007617d  retn
```
