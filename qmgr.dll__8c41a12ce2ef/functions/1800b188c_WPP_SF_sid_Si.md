# WPP_SF__sid_Si

- ea: `0x1800b188c`
- end: `0x1800b1978`
- name: `WPP_SF__sid_Si`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d330`
- `0x180076344`
- `0x18007b438`

## callees

- `0x1800b188c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800b1961`
- `ntdll!EtwTraceMessage` at `0x1800b1961`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b18ed`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b1911`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b18ed`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b1911`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b18fa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b18fa`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_Si(__int64 a1, unsigned __int16 a2, __int64 a3, char *a4, const wchar_t *a5)
{
  const wchar_t *v5; // rdi
  unsigned int v6; // r15d
  char *v7; // rbx
  __int64 v10; // rax
  DWORD LengthSid; // esi

  v5 = a5;
  v6 = a2;
  v7 = a4;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v7);
  }
  else
  {
    LengthSid = 5;
    if ( !v7 )
    {
LABEL_11:
      v7 = "NULL";
      return EtwTraceMessage(a1, 43, a3, v6, v7, LengthSid, v5);
    }
  }
  if ( !IsValidSid(v7) )
    goto LABEL_11;
  return EtwTraceMessage(a1, 43, a3, v6, v7, LengthSid, v5);
}

```

## disassembly

```asm
0x1800b188c  push    rbx
0x1800b188e  push    rbp
0x1800b188f  push    rsi
0x1800b1890  push    rdi
0x1800b1891  push    r12
0x1800b1893  push    r13
0x1800b1895  push    r14
0x1800b1897  push    r15
0x1800b1899  sub     rsp, 68h
0x1800b189d  mov     rdi, [rsp+0A8h+arg_20]
0x1800b18a5  xor     r13d, r13d
0x1800b18a8  movzx   r15d, dx
0x1800b18ac  mov     rbx, r9
0x1800b18af  mov     r14, r8
0x1800b18b2  mov     r12, rcx
0x1800b18b5  test    rdi, rdi
0x1800b18b8  jz      short loc_1800B18D2
0x1800b18ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b18be  inc     rax
0x1800b18c1  cmp     [rdi+rax*2], r13w
0x1800b18c6  jnz     short loc_1800B18BE
0x1800b18c8  lea     rbp, ds:2[rax*2]
0x1800b18d0  jmp     short loc_1800B18D7
0x1800b18d2  mov     ebp, 0Ah
0x1800b18d7  test    rdi, rdi
0x1800b18da  lea     rax, aNull_1; "NULL"
0x1800b18e1  cmovz   rdi, rax
0x1800b18e5  test    rbx, rbx
0x1800b18e8  jz      short loc_1800B1904
0x1800b18ea  mov     rcx, rbx; pSid
0x1800b18ed  call    cs:__imp_IsValidSid
0x1800b18f3  test    eax, eax
0x1800b18f5  jz      short loc_1800B1904
0x1800b18f7  mov     rcx, rbx; pSid
0x1800b18fa  call    cs:__imp_GetLengthSid
0x1800b1900  mov     esi, eax
0x1800b1902  jmp     short loc_1800B190E
0x1800b1904  mov     esi, 5
0x1800b1909  test    rbx, rbx
0x1800b190c  jz      short loc_1800B191B
0x1800b190e  mov     rcx, rbx; pSid
0x1800b1911  call    cs:__imp_IsValidSid
0x1800b1917  test    eax, eax
0x1800b1919  jnz     short loc_1800B1922
0x1800b191b  lea     rbx, aNull; "NULL"
0x1800b1922  mov     [rsp+0A8h+var_58], r13
0x1800b1927  lea     rcx, [rsp+0A8h+arg_28]
0x1800b192f  mov     [rsp+0A8h+var_60], 8
0x1800b1938  mov     r9d, r15d
0x1800b193b  mov     [rsp+0A8h+var_68], rcx
0x1800b1940  mov     r8, r14
0x1800b1943  mov     [rsp+0A8h+var_70], rbp
0x1800b1948  mov     edx, 2Bh ; '+'
0x1800b194d  mov     eax, esi
0x1800b194f  mov     rcx, r12
0x1800b1952  mov     [rsp+0A8h+var_78], rdi
0x1800b1957  mov     [rsp+0A8h+var_80], rax
0x1800b195c  mov     [rsp+0A8h+var_88], rbx
0x1800b1961  call    cs:__imp_EtwTraceMessage
0x1800b1967  add     rsp, 68h
0x1800b196b  pop     r15
0x1800b196d  pop     r14
0x1800b196f  pop     r13
0x1800b1971  pop     r12
0x1800b1973  pop     rdi
0x1800b1974  pop     rsi
0x1800b1975  pop     rbp
0x1800b1976  pop     rbx
0x1800b1977  retn
```
