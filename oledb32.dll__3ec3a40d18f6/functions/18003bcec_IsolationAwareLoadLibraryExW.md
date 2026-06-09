# IsolationAwareLoadLibraryExW

- ea: `0x18003bcec`
- end: `0x18003bda3`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800116dc`
- `0x18003b5fc`
- `0x1800532dc`

## callees

- `0x18003bcec`
- `0x18003be64`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003bd4f`
- `KERNEL32!LoadLibraryExW` at `0x18003bd4f`
- `KERNEL32!GetLastError` at `0x18003bd77`
- `KERNEL32!GetLastError` at `0x180081471`
- `KERNEL32!GetLastError` at `0x18003bd77`
- `KERNEL32!GetLastError` at `0x180081471`
- `KERNEL32!SetLastError` at `0x18003bd98`
- `KERNEL32!SetLastError` at `0x180081491`
- `KERNEL32!SetLastError` at `0x18003bd98`
- `KERNEL32!SetLastError` at `0x180081491`
- `KERNEL32!DeactivateActCtx` at `0x18003bd8c`
- `KERNEL32!DeactivateActCtx` at `0x180081485`
- `KERNEL32!DeactivateActCtx` at `0x18003bd8c`
- `KERNEL32!DeactivateActCtx` at `0x180081485`

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
0x18003bcec  mov     rax, rsp
0x18003bcef  mov     [rax+8], rbx
0x18003bcf3  mov     [rax+18h], rsi
0x18003bcf7  mov     [rax+10h], rdx
0x18003bcfb  push    rdi
0x18003bcfc  sub     rsp, 30h
0x18003bd00  mov     ebx, r8d
0x18003bd03  mov     rdi, rcx
0x18003bd06  mov     qword ptr [rax-18h], 0
0x18003bd0e  mov     qword ptr [rax+10h], 0
0x18003bd16  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003bd1d  jnz     short loc_18003BD47
0x18003bd1f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003bd26  jnz     short loc_18003BD47
0x18003bd28  lea     rcx, [rax+10h]; lpCookie
0x18003bd2c  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18003bd31  test    eax, eax
0x18003bd33  jnz     short loc_18003BD47
0x18003bd35  xor     eax, eax
0x18003bd37  mov     rbx, [rsp+38h+arg_0]
0x18003bd3c  mov     rsi, [rsp+38h+arg_10]
0x18003bd41  add     rsp, 30h
0x18003bd45  pop     rdi
0x18003bd46  retn
0x18003bd47  mov     r8d, ebx; dwFlags
0x18003bd4a  xor     edx, edx; hFile
0x18003bd4c  mov     rcx, rdi; lpLibFileName
0x18003bd4f  call    cs:__imp_LoadLibraryExW
0x18003bd55  mov     rbx, rax
0x18003bd58  mov     [rsp+38h+var_18], rax
0x18003bd5d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003bd64  jz      short loc_18003BD6F
0x18003bd66  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003bd6d  jnz     short loc_18003BD9E
0x18003bd6f  test    rbx, rbx
0x18003bd72  jnz     short loc_18003BD81
0x18003bd74  lea     esi, [rbx+1]
0x18003bd77  call    cs:__imp_GetLastError
0x18003bd7d  mov     edi, eax
0x18003bd7f  jmp     short loc_18003BD85
0x18003bd81  xor     esi, esi
0x18003bd83  xor     edi, edi
0x18003bd85  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18003bd8a  xor     ecx, ecx; dwFlags
0x18003bd8c  call    cs:__imp_DeactivateActCtx
0x18003bd92  test    esi, esi
0x18003bd94  jz      short loc_18003BD9E
0x18003bd96  mov     ecx, edi; dwErrCode
0x18003bd98  call    cs:__imp_SetLastError
0x18003bd9e  mov     rax, rbx
0x18003bda1  jmp     short loc_18003BD37
0x180081448  push    rbx
0x18008144a  push    rbp
0x18008144b  push    rdi
0x18008144c  sub     rsp, 20h
0x180081450  mov     rbp, rdx
0x180081453  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18008145a  jz      short loc_180081465
0x18008145c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180081463  jnz     short loc_180081498
0x180081465  cmp     qword ptr [rbp+20h], 0
0x18008146a  jnz     short loc_18008147B
0x18008146c  mov     edi, 1
0x180081471  call    cs:__imp_GetLastError
0x180081477  mov     ebx, eax
0x180081479  jmp     short loc_18008147F
0x18008147b  xor     edi, edi
0x18008147d  xor     ebx, ebx
0x18008147f  mov     rdx, [rbp+48h]; ulCookie
0x180081483  xor     ecx, ecx; dwFlags
0x180081485  call    cs:__imp_DeactivateActCtx
0x18008148b  test    edi, edi
0x18008148d  jz      short loc_180081498
0x18008148f  mov     ecx, ebx; dwErrCode
0x180081491  call    cs:__imp_SetLastError
0x180081497  nop
0x180081498  add     rsp, 20h
0x18008149c  pop     rdi
0x18008149d  pop     rbp
0x18008149e  pop     rbx
0x18008149f  retn
```
