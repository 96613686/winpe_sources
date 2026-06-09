# IsolationAwareLoadLibraryW

- ea: `0x18004f6e0`
- end: `0x18004f78b`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004f184`

## callees

- `0x180002b18`
- `0x18004f6e0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18004f737`
- `KERNEL32!LoadLibraryW` at `0x18004f737`
- `KERNEL32!GetLastError` at `0x18004f75f`
- `KERNEL32!GetLastError` at `0x18007614f`
- `KERNEL32!GetLastError` at `0x18004f75f`
- `KERNEL32!GetLastError` at `0x18007614f`
- `KERNEL32!DeactivateActCtx` at `0x18004f774`
- `KERNEL32!DeactivateActCtx` at `0x180076163`
- `KERNEL32!DeactivateActCtx` at `0x18004f774`
- `KERNEL32!DeactivateActCtx` at `0x180076163`
- `KERNEL32!SetLastError` at `0x18004f780`
- `KERNEL32!SetLastError` at `0x18007616f`
- `KERNEL32!SetLastError` at `0x18004f780`
- `KERNEL32!SetLastError` at `0x18007616f`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  HMODULE LibraryW; // rax
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
  LibraryW = LoadLibraryW(lpLibFileName);
  v4 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
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
0x18004f6e0  mov     rax, rsp
0x18004f6e3  mov     [rax+8], rbx
0x18004f6e7  mov     [rax+18h], rsi
0x18004f6eb  push    rdi
0x18004f6ec  sub     rsp, 30h
0x18004f6f0  mov     rbx, rcx
0x18004f6f3  mov     qword ptr [rax-18h], 0
0x18004f6fb  mov     qword ptr [rax+10h], 0
0x18004f703  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18004f70a  jnz     short loc_18004F734
0x18004f70c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18004f713  jnz     short loc_18004F734
0x18004f715  lea     rcx, [rax+10h]; lpCookie
0x18004f719  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18004f71e  test    eax, eax
0x18004f720  jnz     short loc_18004F734
0x18004f722  xor     eax, eax
0x18004f724  mov     rbx, [rsp+38h+arg_0]
0x18004f729  mov     rsi, [rsp+38h+arg_10]
0x18004f72e  add     rsp, 30h
0x18004f732  pop     rdi
0x18004f733  retn
0x18004f734  mov     rcx, rbx; lpLibFileName
0x18004f737  call    cs:__imp_LoadLibraryW
0x18004f73d  mov     rbx, rax
0x18004f740  mov     [rsp+38h+var_18], rax
0x18004f745  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18004f74c  jz      short loc_18004F757
0x18004f74e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18004f755  jnz     short loc_18004F786
0x18004f757  test    rbx, rbx
0x18004f75a  jnz     short loc_18004F769
0x18004f75c  lea     esi, [rbx+1]
0x18004f75f  call    cs:__imp_GetLastError
0x18004f765  mov     edi, eax
0x18004f767  jmp     short loc_18004F76D
0x18004f769  xor     esi, esi
0x18004f76b  xor     edi, edi
0x18004f76d  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18004f772  xor     ecx, ecx; dwFlags
0x18004f774  call    cs:__imp_DeactivateActCtx
0x18004f77a  test    esi, esi
0x18004f77c  jz      short loc_18004F786
0x18004f77e  mov     ecx, edi; dwErrCode
0x18004f780  call    cs:__imp_SetLastError
0x18004f786  mov     rax, rbx
0x18004f789  jmp     short loc_18004F724
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
