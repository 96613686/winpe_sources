# TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)

- ea: `0x180010b48`
- end: `0x180010beb`
- name: `?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z`
- size: `163`
- prototype: `int(TOKEN_ENTRY *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800117cc`

## callees

- `0x180010b48`
- `0x180010bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010bb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ba9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ba9`

## pseudocode

```c
int __fastcall TOKEN_ENTRY::Create(
        TOKEN_ENTRY *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
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
0x180010b48  mov     [rsp+arg_0], rbx
0x180010b4d  mov     [rsp+arg_8], rbp
0x180010b52  push    rsi
0x180010b53  sub     rsp, 30h
0x180010b57  cmp     [rsp+38h+arg_20], 3
0x180010b5c  mov     rax, rdx
0x180010b5f  mov     edx, 1; TokenInformationClass
0x180010b64  mov     rsi, r9
0x180010b67  mov     rbp, r8
0x180010b6a  mov     rbx, rcx
0x180010b6d  jz      short loc_180010B83
0x180010b6f  cmp     [rsp+38h+arg_20], 8
0x180010b74  jz      short loc_180010B83
0x180010b76  or      dword ptr [rcx+104h], 2
0x180010b7d  mov     [rcx+18h], rax
0x180010b81  jmp     short loc_180010B8D
0x180010b83  or      [rcx+104h], edx
0x180010b89  mov     [rcx+10h], rax
0x180010b8d  lea     r8, [rcx+20h]; TokenInformation
0x180010b91  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180010b97  lea     rcx, [rsp+38h+arg_28]
0x180010b9c  mov     [rsp+38h+arg_28], r9d
0x180010ba1  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180010ba6  mov     rcx, rax; TokenHandle
0x180010ba9  call    cs:__imp_GetTokenInformation
0x180010baf  test    eax, eax
0x180010bb1  jnz     short loc_180010BC7
0x180010bb3  call    cs:__imp_GetLastError
0x180010bb9  test    eax, eax
0x180010bbb  jle     short loc_180010BDB
0x180010bbd  movzx   eax, ax
0x180010bc0  or      eax, 80070000h
0x180010bc5  jmp     short loc_180010BDB
0x180010bc7  mov     r9d, [rsp+38h+arg_20]; unsigned int
0x180010bcc  lea     rcx, [rbx+78h]; this
0x180010bd0  mov     r8, rsi; unsigned __int16 *
0x180010bd3  mov     rdx, rbp; unsigned __int16 *
0x180010bd6  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180010bdb  mov     rbx, [rsp+38h+arg_0]
0x180010be0  mov     rbp, [rsp+38h+arg_8]
0x180010be5  add     rsp, 30h
0x180010be9  pop     rsi
0x180010bea  retn
```
