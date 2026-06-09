# IsolationAwareLoadLibraryA

- ea: `0x180002a64`
- end: `0x180002b0f`
- name: `IsolationAwareLoadLibraryA`
- size: `171`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800027fc`
- `0x1800258c0`
- `0x180026860`
- `0x18002e640`
- `0x180042598`
- `0x180042954`
- `0x1800470d8`
- `0x18004eea0`
- `0x18004f184`
- `0x180068b60`
- `0x180069040`

## callees

- `0x180002a64`
- `0x180002b18`
- `0x18004f6e0`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x180002abb`
- `KERNEL32!LoadLibraryA` at `0x180002abb`
- `KERNEL32!GetLastError` at `0x180002ae3`
- `KERNEL32!GetLastError` at `0x180002ae3`
- `KERNEL32!DeactivateActCtx` at `0x180002af8`
- `KERNEL32!DeactivateActCtx` at `0x180002af8`
- `KERNEL32!SetLastError` at `0x180002b04`
- `KERNEL32!SetLastError` at `0x180002b04`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryA(LPCSTR lpLibFileName)
{
  HMODULE LibraryA; // rax
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
  LibraryA = LoadLibraryA(lpLibFileName);
  v4 = LibraryA;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryA )
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
0x180002a64  mov     rax, rsp
0x180002a67  mov     [rax+8], rbx
0x180002a6b  mov     [rax+18h], rsi
0x180002a6f  push    rdi
0x180002a70  sub     rsp, 30h
0x180002a74  mov     rbx, rcx
0x180002a77  mov     qword ptr [rax-18h], 0
0x180002a7f  mov     qword ptr [rax+10h], 0
0x180002a87  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180002a8e  jnz     short loc_180002AB8
0x180002a90  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002a97  jnz     short loc_180002AB8
0x180002a99  lea     rcx, [rax+10h]; lpCookie
0x180002a9d  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180002aa2  test    eax, eax
0x180002aa4  jnz     short loc_180002AB8
0x180002aa6  xor     eax, eax
0x180002aa8  mov     rbx, [rsp+38h+arg_0]
0x180002aad  mov     rsi, [rsp+38h+arg_10]
0x180002ab2  add     rsp, 30h
0x180002ab6  pop     rdi
0x180002ab7  retn
0x180002ab8  mov     rcx, rbx; lpLibFileName
0x180002abb  call    cs:__imp_LoadLibraryA
0x180002ac1  mov     rbx, rax
0x180002ac4  mov     [rsp+38h+var_18], rax
0x180002ac9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180002ad0  jz      short loc_180002ADB
0x180002ad2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002ad9  jnz     short loc_180002B0A
0x180002adb  test    rbx, rbx
0x180002ade  jnz     short loc_180002AED
0x180002ae0  lea     esi, [rbx+1]
0x180002ae3  call    cs:__imp_GetLastError
0x180002ae9  mov     edi, eax
0x180002aeb  jmp     short loc_180002AF1
0x180002aed  xor     esi, esi
0x180002aef  xor     edi, edi
0x180002af1  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180002af6  xor     ecx, ecx; dwFlags
0x180002af8  call    cs:__imp_DeactivateActCtx
0x180002afe  test    esi, esi
0x180002b00  jz      short loc_180002B0A
0x180002b02  mov     ecx, edi; dwErrCode
0x180002b04  call    cs:__imp_SetLastError
0x180002b0a  mov     rax, rbx
0x180002b0d  jmp     short loc_180002AA8
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
