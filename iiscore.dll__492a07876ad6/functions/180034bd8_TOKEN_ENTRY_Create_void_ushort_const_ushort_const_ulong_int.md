# TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)

- ea: `0x180034bd8`
- end: `0x180034c88`
- name: `?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z`
- size: `176`
- prototype: `int(TOKEN_ENTRY *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035a78`

## callees

- `0x180034bd8`
- `0x180034c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034c39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180034c39`

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
0x180034bd8  mov     [rsp+arg_0], rbx
0x180034bdd  mov     [rsp+arg_8], rbp
0x180034be2  push    rsi
0x180034be3  sub     rsp, 30h
0x180034be7  cmp     [rsp+38h+arg_20], 3
0x180034bec  mov     rax, rdx
0x180034bef  mov     edx, 1; TokenInformationClass
0x180034bf4  mov     rsi, r9
0x180034bf7  mov     rbp, r8
0x180034bfa  mov     rbx, rcx
0x180034bfd  jz      short loc_180034C13
0x180034bff  cmp     [rsp+38h+arg_20], 8
0x180034c04  jz      short loc_180034C13
0x180034c06  or      dword ptr [rcx+104h], 2
0x180034c0d  mov     [rcx+18h], rax
0x180034c11  jmp     short loc_180034C1D
0x180034c13  or      [rcx+104h], edx
0x180034c19  mov     [rcx+10h], rax
0x180034c1d  lea     r8, [rcx+20h]; TokenInformation
0x180034c21  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180034c27  lea     rcx, [rsp+38h+arg_28]
0x180034c2c  mov     [rsp+38h+arg_28], r9d
0x180034c31  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180034c36  mov     rcx, rax; TokenHandle
0x180034c39  call    cs:__imp_GetTokenInformation
0x180034c40  nop     dword ptr [rax+rax+00h]
0x180034c45  test    eax, eax
0x180034c47  jnz     short loc_180034C63
0x180034c49  call    cs:__imp_GetLastError
0x180034c50  nop     dword ptr [rax+rax+00h]
0x180034c55  test    eax, eax
0x180034c57  jle     short loc_180034C77
0x180034c59  movzx   eax, ax
0x180034c5c  or      eax, 80070000h
0x180034c61  jmp     short loc_180034C77
0x180034c63  mov     r9d, [rsp+38h+arg_20]; unsigned int
0x180034c68  lea     rcx, [rbx+78h]; this
0x180034c6c  mov     r8, rsi; unsigned __int16 *
0x180034c6f  mov     rdx, rbp; unsigned __int16 *
0x180034c72  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180034c77  mov     rbx, [rsp+38h+arg_0]
0x180034c7c  mov     rbp, [rsp+38h+arg_8]
0x180034c81  add     rsp, 30h
0x180034c85  pop     rsi
0x180034c86  retn
```
