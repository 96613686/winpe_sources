# IsolationAwareLoadLibraryExW

- ea: `0x180021224`
- end: `0x1800212d9`
- name: `IsolationAwareLoadLibraryExW`
- size: `181`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002134c`

## callees

- `0x18000911c`
- `0x180021224`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180021285`
- `KERNEL32!LoadLibraryExW` at `0x180021285`
- `KERNEL32!GetLastError` at `0x1800212ad`
- `KERNEL32!GetLastError` at `0x1800231a0`
- `KERNEL32!GetLastError` at `0x1800212ad`
- `KERNEL32!GetLastError` at `0x1800231a0`
- `KERNEL32!SetLastError` at `0x1800212ce`
- `KERNEL32!SetLastError` at `0x1800231c0`
- `KERNEL32!SetLastError` at `0x1800212ce`
- `KERNEL32!SetLastError` at `0x1800231c0`
- `KERNEL32!DeactivateActCtx` at `0x1800212c2`
- `KERNEL32!DeactivateActCtx` at `0x1800231b4`
- `KERNEL32!DeactivateActCtx` at `0x1800212c2`
- `KERNEL32!DeactivateActCtx` at `0x1800231b4`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName)
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
  Library = LoadLibraryExW(lpLibFileName, 0, 3u);
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
0x180021224  mov     rax, rsp
0x180021227  mov     [rax+8], rbx
0x18002122b  mov     [rax+18h], rsi
0x18002122f  mov     [rax+10h], rdx
0x180021233  push    rdi
0x180021234  sub     rsp, 30h
0x180021238  mov     rbx, rcx
0x18002123b  mov     qword ptr [rax-18h], 0
0x180021243  mov     qword ptr [rax+10h], 0
0x18002124b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180021252  jnz     short loc_18002127C
0x180021254  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002125b  jnz     short loc_18002127C
0x18002125d  lea     rcx, [rax+10h]; lpCookie
0x180021261  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180021266  test    eax, eax
0x180021268  jnz     short loc_18002127C
0x18002126a  xor     eax, eax
0x18002126c  mov     rbx, [rsp+38h+arg_0]
0x180021271  mov     rsi, [rsp+38h+arg_10]
0x180021276  add     rsp, 30h
0x18002127a  pop     rdi
0x18002127b  retn
0x18002127c  xor     edx, edx; hFile
0x18002127e  lea     r8d, [rdx+3]; dwFlags
0x180021282  mov     rcx, rbx; lpLibFileName
0x180021285  call    cs:__imp_LoadLibraryExW
0x18002128b  mov     rbx, rax
0x18002128e  mov     [rsp+38h+var_18], rax
0x180021293  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002129a  jz      short loc_1800212A5
0x18002129c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800212a3  jnz     short loc_1800212D4
0x1800212a5  test    rbx, rbx
0x1800212a8  jnz     short loc_1800212B7
0x1800212aa  lea     esi, [rbx+1]
0x1800212ad  call    cs:__imp_GetLastError
0x1800212b3  mov     edi, eax
0x1800212b5  jmp     short loc_1800212BB
0x1800212b7  xor     esi, esi
0x1800212b9  xor     edi, edi
0x1800212bb  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800212c0  xor     ecx, ecx; dwFlags
0x1800212c2  call    cs:__imp_DeactivateActCtx
0x1800212c8  test    esi, esi
0x1800212ca  jz      short loc_1800212D4
0x1800212cc  mov     ecx, edi; dwErrCode
0x1800212ce  call    cs:__imp_SetLastError
0x1800212d4  mov     rax, rbx
0x1800212d7  jmp     short loc_18002126C
0x180023177  push    rbx
0x180023179  push    rbp
0x18002317a  push    rdi
0x18002317b  sub     rsp, 20h
0x18002317f  mov     rbp, rdx
0x180023182  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180023189  jz      short loc_180023194
0x18002318b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180023192  jnz     short loc_1800231C7
0x180023194  cmp     qword ptr [rbp+20h], 0
0x180023199  jnz     short loc_1800231AA
0x18002319b  mov     edi, 1
0x1800231a0  call    cs:__imp_GetLastError
0x1800231a6  mov     ebx, eax
0x1800231a8  jmp     short loc_1800231AE
0x1800231aa  xor     edi, edi
0x1800231ac  xor     ebx, ebx
0x1800231ae  mov     rdx, [rbp+48h]; ulCookie
0x1800231b2  xor     ecx, ecx; dwFlags
0x1800231b4  call    cs:__imp_DeactivateActCtx
0x1800231ba  test    edi, edi
0x1800231bc  jz      short loc_1800231C7
0x1800231be  mov     ecx, ebx; dwErrCode
0x1800231c0  call    cs:__imp_SetLastError
0x1800231c6  nop
0x1800231c7  add     rsp, 20h
0x1800231cb  pop     rdi
0x1800231cc  pop     rbp
0x1800231cd  pop     rbx
0x1800231ce  retn
```
