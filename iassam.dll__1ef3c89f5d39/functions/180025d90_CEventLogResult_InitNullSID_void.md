# CEventLogResult::InitNullSID(void)

- ea: `0x180025d90`
- end: `0x180025e2f`
- name: `?InitNullSID@CEventLogResult@@AEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CEventLogResult *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180025e38`

## callees

- `0x18000342c`
- `0x180025d90`

## import_xrefs

- `msvcrt!free` at `0x180025dea`
- `msvcrt!free` at `0x180025dea`
- `KERNEL32!GetLastError` at `0x180025db7`
- `KERNEL32!GetLastError` at `0x180025e1a`
- `KERNEL32!GetLastError` at `0x180025db7`
- `KERNEL32!GetLastError` at `0x180025e1a`
- `ADVAPI32!CreateWellKnownSid` at `0x180025db1`
- `ADVAPI32!CreateWellKnownSid` at `0x180025e10`
- `ADVAPI32!CreateWellKnownSid` at `0x180025db1`
- `ADVAPI32!CreateWellKnownSid` at `0x180025e10`

## pseudocode

```c
signed int __fastcall CEventLogResult::InitNullSID(void **this)
{
  signed int result; // eax
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rbx
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  cbSid = 0;
  CreateWellKnownSid(WinNullSid, 0, 0, &cbSid);
  result = GetLastError();
  if ( result == 122 )
  {
    v4 = operator new[](cbSid, v3);
    if ( v4 == *this )
    {
      v4 = *this;
    }
    else
    {
      if ( *this )
        free(*this);
      *this = v4;
    }
    if ( !v4 )
      return -2147024882;
    if ( CreateWellKnownSid(WinNullSid, 0, v4, &cbSid) )
      return 0;
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025d90  mov     [rsp+arg_0], rbx
0x180025d95  push    rdi
0x180025d96  sub     rsp, 20h
0x180025d9a  mov     rdi, rcx
0x180025d9d  mov     [rsp+28h+cbSid], 0
0x180025da5  xor     ecx, ecx; WellKnownSidType
0x180025da7  lea     r9, [rsp+28h+cbSid]; cbSid
0x180025dac  xor     r8d, r8d; pSid
0x180025daf  xor     edx, edx; DomainSid
0x180025db1  call    cs:__imp_CreateWellKnownSid
0x180025db7  call    cs:__imp_GetLastError
0x180025dbd  cmp     eax, 7Ah ; 'z'
0x180025dc0  jz      short loc_180025DD0
0x180025dc2  test    eax, eax
0x180025dc4  jle     short loc_180025E24
0x180025dc6  movzx   eax, ax
0x180025dc9  or      eax, 80070000h
0x180025dce  jmp     short loc_180025E24
0x180025dd0  mov     ecx, [rsp+28h+cbSid]; Size
0x180025dd4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180025dd9  mov     rbx, rax
0x180025ddc  cmp     rax, [rdi]
0x180025ddf  jz      short loc_180025DF5
0x180025de1  cmp     qword ptr [rdi], 0
0x180025de5  jz      short loc_180025DF0
0x180025de7  mov     rcx, [rdi]; Block
0x180025dea  call    cs:__imp_free
0x180025df0  mov     [rdi], rbx
0x180025df3  jmp     short loc_180025DF8
0x180025df5  mov     rbx, [rdi]
0x180025df8  test    rbx, rbx
0x180025dfb  jnz     short loc_180025E04
0x180025dfd  mov     eax, 8007000Eh
0x180025e02  jmp     short loc_180025E24
0x180025e04  lea     r9, [rsp+28h+cbSid]; cbSid
0x180025e09  mov     r8, rbx; pSid
0x180025e0c  xor     edx, edx; DomainSid
0x180025e0e  xor     ecx, ecx; WellKnownSidType
0x180025e10  call    cs:__imp_CreateWellKnownSid
0x180025e16  test    eax, eax
0x180025e18  jnz     short loc_180025E22
0x180025e1a  call    cs:__imp_GetLastError
0x180025e20  jmp     short loc_180025DC2
0x180025e22  xor     eax, eax
0x180025e24  mov     rbx, [rsp+28h+arg_0]
0x180025e29  add     rsp, 20h
0x180025e2d  pop     rdi
0x180025e2e  retn
```
