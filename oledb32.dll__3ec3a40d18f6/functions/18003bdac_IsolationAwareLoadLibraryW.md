# IsolationAwareLoadLibraryW

- ea: `0x18003bdac`
- end: `0x18003be5c`
- name: `IsolationAwareLoadLibraryW`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059e30`

## callees

- `0x18003bdac`
- `0x18003be64`
- `0x18004d950`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003be30`
- `KERNEL32!GetLastError` at `0x18003be30`
- `KERNEL32!SetLastError` at `0x18003be51`
- `KERNEL32!SetLastError` at `0x18003be51`
- `KERNEL32!DeactivateActCtx` at `0x18003be45`
- `KERNEL32!DeactivateActCtx` at `0x18003be45`
- `KERNEL32!LoadLibraryW` at `0x18003be08`
- `KERNEL32!LoadLibraryW` at `0x18003be08`

## string_xrefs

- `0x18003be01`: `COMCTL32`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryW()
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(L"COMCTL32");
  v2 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18003bdac  mov     rax, rsp
0x18003bdaf  mov     [rax+10h], rbx
0x18003bdb3  mov     [rax+18h], rsi
0x18003bdb7  mov     [rax+8], rcx
0x18003bdbb  push    rdi
0x18003bdbc  sub     rsp, 30h
0x18003bdc0  mov     qword ptr [rax-18h], 0
0x18003bdc8  mov     qword ptr [rax+8], 0
0x18003bdd0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003bdd7  jnz     short loc_18003BE01
0x18003bdd9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003bde0  jnz     short loc_18003BE01
0x18003bde2  lea     rcx, [rax+8]; lpCookie
0x18003bde6  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18003bdeb  test    eax, eax
0x18003bded  jnz     short loc_18003BE01
0x18003bdef  xor     eax, eax
0x18003bdf1  mov     rbx, [rsp+38h+arg_8]
0x18003bdf6  mov     rsi, [rsp+38h+arg_10]
0x18003bdfb  add     rsp, 30h
0x18003bdff  pop     rdi
0x18003be00  retn
0x18003be01  lea     rcx, LibFileName; "COMCTL32"
0x18003be08  call    cs:__imp_LoadLibraryW
0x18003be0e  mov     rbx, rax
0x18003be11  mov     [rsp+38h+var_18], rax
0x18003be16  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18003be1d  jz      short loc_18003BE28
0x18003be1f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003be26  jnz     short loc_18003BE57
0x18003be28  test    rbx, rbx
0x18003be2b  jnz     short loc_18003BE3A
0x18003be2d  lea     esi, [rbx+1]
0x18003be30  call    cs:__imp_GetLastError
0x18003be36  mov     edi, eax
0x18003be38  jmp     short loc_18003BE3E
0x18003be3a  xor     esi, esi
0x18003be3c  xor     edi, edi
0x18003be3e  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18003be43  xor     ecx, ecx; dwFlags
0x18003be45  call    cs:__imp_DeactivateActCtx
0x18003be4b  test    esi, esi
0x18003be4d  jz      short loc_18003BE57
0x18003be4f  mov     ecx, edi; dwErrCode
0x18003be51  call    cs:__imp_SetLastError
0x18003be57  mov     rax, rbx
0x18003be5a  jmp     short loc_18003BDF1
0x1800814a7  push    rbx
0x1800814a9  push    rbp
0x1800814aa  push    rdi
0x1800814ab  sub     rsp, 20h
0x1800814af  mov     rbp, rdx
0x1800814b2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800814b9  jz      short loc_1800814C4
0x1800814bb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800814c2  jnz     short loc_1800814F7
0x1800814c4  cmp     qword ptr [rbp+20h], 0
0x1800814c9  jnz     short loc_1800814DA
0x1800814cb  mov     edi, 1
0x1800814d0  call    cs:__imp_GetLastError
0x1800814d6  mov     ebx, eax
0x1800814d8  jmp     short loc_1800814DE
0x1800814da  xor     edi, edi
0x1800814dc  xor     ebx, ebx
0x1800814de  mov     rdx, [rbp+40h]; ulCookie
0x1800814e2  xor     ecx, ecx; dwFlags
0x1800814e4  call    cs:__imp_DeactivateActCtx
0x1800814ea  test    edi, edi
0x1800814ec  jz      short loc_1800814F7
0x1800814ee  mov     ecx, ebx; dwErrCode
0x1800814f0  call    cs:__imp_SetLastError
0x1800814f6  nop
0x1800814f7  add     rsp, 20h
0x1800814fb  pop     rdi
0x1800814fc  pop     rbp
0x1800814fd  pop     rbx
0x1800814fe  retn
```
