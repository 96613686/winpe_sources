# TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)

- ea: `0x180031d28`
- end: `0x180031dcb`
- name: `?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z`
- size: `163`
- prototype: `int __fastcall(TOKEN_ENTRY *this, void *, const unsigned __int16 *, const BYTE *, unsigned int, DWORD ReturnLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032994`

## callees

- `0x180031d28`
- `0x180031dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d93`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031d89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031d89`

## pseudocode

```c
int __fastcall TOKEN_ENTRY::Create(
        TOKEN_ENTRY *this,
        void *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        unsigned int a5,
        DWORD ReturnLength)
{
  int result; // eax

  if ( a5 == 3 || a5 == 8 )
  {
    *((_DWORD *)this + 65) |= 1u;
    *((_QWORD *)this + 2) = a2;
  }
  else
  {
    *((_DWORD *)this + 65) |= 2u;
    *((_QWORD *)this + 3) = a2;
  }
  ReturnLength = 84;
  if ( GetTokenInformation(a2, TokenUser, (char *)this + 32, 0x54u, &ReturnLength) )
    return TOKEN_KEY::CreateCacheKey((TOKEN_ENTRY *)((char *)this + 120), a3, a4, a5);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180031d28  mov     [rsp+arg_0], rbx
0x180031d2d  mov     [rsp+arg_8], rbp
0x180031d32  push    rsi
0x180031d33  sub     rsp, 30h
0x180031d37  cmp     [rsp+38h+arg_20], 3
0x180031d3c  mov     rax, rdx
0x180031d3f  mov     edx, 1; TokenInformationClass
0x180031d44  mov     rsi, r9
0x180031d47  mov     rbp, r8
0x180031d4a  mov     rbx, rcx
0x180031d4d  jz      short loc_180031D63
0x180031d4f  cmp     [rsp+38h+arg_20], 8
0x180031d54  jz      short loc_180031D63
0x180031d56  or      dword ptr [rcx+104h], 2
0x180031d5d  mov     [rcx+18h], rax
0x180031d61  jmp     short loc_180031D6D
0x180031d63  or      [rcx+104h], edx
0x180031d69  mov     [rcx+10h], rax
0x180031d6d  lea     r8, [rcx+20h]; TokenInformation
0x180031d71  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180031d77  lea     rcx, [rsp+38h+arg_28]
0x180031d7c  mov     [rsp+38h+arg_28], r9d
0x180031d81  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180031d86  mov     rcx, rax; TokenHandle
0x180031d89  call    cs:__imp_GetTokenInformation
0x180031d8f  test    eax, eax
0x180031d91  jnz     short loc_180031DA7
0x180031d93  call    cs:__imp_GetLastError
0x180031d99  test    eax, eax
0x180031d9b  jle     short loc_180031DBB
0x180031d9d  movzx   eax, ax
0x180031da0  or      eax, 80070000h
0x180031da5  jmp     short loc_180031DBB
0x180031da7  mov     r9d, [rsp+38h+arg_20]; unsigned int
0x180031dac  lea     rcx, [rbx+78h]; this
0x180031db0  mov     r8, rsi; unsigned __int16 *
0x180031db3  mov     rdx, rbp; unsigned __int16 *
0x180031db6  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180031dbb  mov     rbx, [rsp+38h+arg_0]
0x180031dc0  mov     rbp, [rsp+38h+arg_8]
0x180031dc5  add     rsp, 30h
0x180031dc9  pop     rsi
0x180031dca  retn
```
