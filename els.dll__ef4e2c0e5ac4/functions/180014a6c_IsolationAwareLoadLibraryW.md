# IsolationAwareLoadLibraryW

- ea: `0x180014a6c`
- end: `0x180014b17`
- name: `IsolationAwareLoadLibraryW`
- size: `171`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800141bc`
- `0x18001435c`

## callees

- `0x18000911c`
- `0x180014a6c`
- `0x180021224`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014aeb`
- `KERNEL32!GetLastError` at `0x180014aeb`
- `KERNEL32!SetLastError` at `0x180014b0c`
- `KERNEL32!SetLastError` at `0x180014b0c`
- `KERNEL32!DeactivateActCtx` at `0x180014b00`
- `KERNEL32!DeactivateActCtx` at `0x180014b00`
- `KERNEL32!LoadLibraryW` at `0x180014ac3`
- `KERNEL32!LoadLibraryW` at `0x180014ac3`

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
0x180014a6c  mov     rax, rsp
0x180014a6f  mov     [rax+8], rbx
0x180014a73  mov     [rax+18h], rsi
0x180014a77  push    rdi
0x180014a78  sub     rsp, 30h
0x180014a7c  mov     rbx, rcx
0x180014a7f  mov     qword ptr [rax-18h], 0
0x180014a87  mov     qword ptr [rax+10h], 0
0x180014a8f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180014a96  jnz     short loc_180014AC0
0x180014a98  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180014a9f  jnz     short loc_180014AC0
0x180014aa1  lea     rcx, [rax+10h]; lpCookie
0x180014aa5  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180014aaa  test    eax, eax
0x180014aac  jnz     short loc_180014AC0
0x180014aae  xor     eax, eax
0x180014ab0  mov     rbx, [rsp+38h+arg_0]
0x180014ab5  mov     rsi, [rsp+38h+arg_10]
0x180014aba  add     rsp, 30h
0x180014abe  pop     rdi
0x180014abf  retn
0x180014ac0  mov     rcx, rbx; lpLibFileName
0x180014ac3  call    cs:__imp_LoadLibraryW
0x180014ac9  mov     rbx, rax
0x180014acc  mov     [rsp+38h+var_18], rax
0x180014ad1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180014ad8  jz      short loc_180014AE3
0x180014ada  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180014ae1  jnz     short loc_180014B12
0x180014ae3  test    rbx, rbx
0x180014ae6  jnz     short loc_180014AF5
0x180014ae8  lea     esi, [rbx+1]
0x180014aeb  call    cs:__imp_GetLastError
0x180014af1  mov     edi, eax
0x180014af3  jmp     short loc_180014AF9
0x180014af5  xor     esi, esi
0x180014af7  xor     edi, edi
0x180014af9  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180014afe  xor     ecx, ecx; dwFlags
0x180014b00  call    cs:__imp_DeactivateActCtx
0x180014b06  test    esi, esi
0x180014b08  jz      short loc_180014B12
0x180014b0a  mov     ecx, edi; dwErrCode
0x180014b0c  call    cs:__imp_SetLastError
0x180014b12  mov     rax, rbx
0x180014b15  jmp     short loc_180014AB0
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
