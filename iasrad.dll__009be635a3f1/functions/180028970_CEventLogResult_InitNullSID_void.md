# CEventLogResult::InitNullSID(void)

- ea: `0x180028970`
- end: `0x180028a0f`
- name: `?InitNullSID@CEventLogResult@@AEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CEventLogResult *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000b560`

## callees

- `0x18000e4e0`
- `0x180028970`

## import_xrefs

- `msvcrt!free` at `0x1800289ca`
- `msvcrt!free` at `0x1800289ca`
- `KERNEL32!GetLastError` at `0x180028997`
- `KERNEL32!GetLastError` at `0x1800289fa`
- `KERNEL32!GetLastError` at `0x180028997`
- `KERNEL32!GetLastError` at `0x1800289fa`
- `ADVAPI32!CreateWellKnownSid` at `0x180028991`
- `ADVAPI32!CreateWellKnownSid` at `0x1800289f0`
- `ADVAPI32!CreateWellKnownSid` at `0x180028991`
- `ADVAPI32!CreateWellKnownSid` at `0x1800289f0`

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
0x180028970  mov     [rsp+arg_0], rbx
0x180028975  push    rdi
0x180028976  sub     rsp, 20h
0x18002897a  mov     rdi, rcx
0x18002897d  mov     [rsp+28h+cbSid], 0
0x180028985  xor     ecx, ecx; WellKnownSidType
0x180028987  lea     r9, [rsp+28h+cbSid]; cbSid
0x18002898c  xor     r8d, r8d; pSid
0x18002898f  xor     edx, edx; DomainSid
0x180028991  call    cs:__imp_CreateWellKnownSid
0x180028997  call    cs:__imp_GetLastError
0x18002899d  cmp     eax, 7Ah ; 'z'
0x1800289a0  jz      short loc_1800289B0
0x1800289a2  test    eax, eax
0x1800289a4  jle     short loc_180028A04
0x1800289a6  movzx   eax, ax
0x1800289a9  or      eax, 80070000h
0x1800289ae  jmp     short loc_180028A04
0x1800289b0  mov     ecx, [rsp+28h+cbSid]; Size
0x1800289b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800289b9  mov     rbx, rax
0x1800289bc  cmp     rax, [rdi]
0x1800289bf  jz      short loc_1800289D5
0x1800289c1  cmp     qword ptr [rdi], 0
0x1800289c5  jz      short loc_1800289D0
0x1800289c7  mov     rcx, [rdi]; Block
0x1800289ca  call    cs:__imp_free
0x1800289d0  mov     [rdi], rbx
0x1800289d3  jmp     short loc_1800289D8
0x1800289d5  mov     rbx, [rdi]
0x1800289d8  test    rbx, rbx
0x1800289db  jnz     short loc_1800289E4
0x1800289dd  mov     eax, 8007000Eh
0x1800289e2  jmp     short loc_180028A04
0x1800289e4  lea     r9, [rsp+28h+cbSid]; cbSid
0x1800289e9  mov     r8, rbx; pSid
0x1800289ec  xor     edx, edx; DomainSid
0x1800289ee  xor     ecx, ecx; WellKnownSidType
0x1800289f0  call    cs:__imp_CreateWellKnownSid
0x1800289f6  test    eax, eax
0x1800289f8  jnz     short loc_180028A02
0x1800289fa  call    cs:__imp_GetLastError
0x180028a00  jmp     short loc_1800289A2
0x180028a02  xor     eax, eax
0x180028a04  mov     rbx, [rsp+28h+arg_0]
0x180028a09  add     rsp, 20h
0x180028a0d  pop     rdi
0x180028a0e  retn
```
