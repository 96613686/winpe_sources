# DaConvertSidToString

- ea: `0x18000d478`
- end: `0x18000d5d1`
- name: `DaConvertSidToString`
- size: `345`
- prototype: `__int64 __fastcall(PSID pSid, wchar_t *Buffer, size_t BufferCount)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000be24`
- `0x18000cbe0`
- `0x18000cf74`

## callees

- `0x18000d478`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000d4d4`
- `msvcrt!swprintf_s` at `0x18000d52c`
- `msvcrt!swprintf_s` at `0x18000d576`
- `msvcrt!swprintf_s` at `0x18000d5b2`
- `msvcrt!swprintf_s` at `0x18000d4d4`
- `msvcrt!swprintf_s` at `0x18000d52c`
- `msvcrt!swprintf_s` at `0x18000d576`
- `msvcrt!swprintf_s` at `0x18000d5b2`
- `KERNEL32!GetLastError` at `0x18000d49d`
- `KERNEL32!GetLastError` at `0x18000d49d`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18000d4b7`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18000d4b7`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18000d4ab`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18000d4ab`
- `ADVAPI32!IsValidSid` at `0x18000d490`
- `ADVAPI32!IsValidSid` at `0x18000d490`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d597`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d597`

## pseudocode

```c
DWORD __fastcall DaConvertSidToString(PSID pSid, wchar_t *Buffer, size_t BufferCount)
{
  size_t v3; // r14
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v8; // r15d
  __int64 v9; // rcx
  BYTE *v10; // rax
  DWORD i; // edi
  __int64 v12; // rbx
  PDWORD SidSubAuthority; // rax
  int v14; // [rsp+20h] [rbp-68h]
  int v15; // [rsp+28h] [rbp-60h]
  int v16; // [rsp+30h] [rbp-58h]
  int v17; // [rsp+38h] [rbp-50h]
  int v18; // [rsp+40h] [rbp-48h]

  v3 = (unsigned int)BufferCount;
  if ( !IsValidSid(pSid) )
    return GetLastError();
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  v8 = *GetSidSubAuthorityCount(pSid);
  swprintf_s(Buffer, v3, L"S-%lu-", 1);
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
  v10 = &SidIdentifierAuthority->Value[1];
  if ( SidIdentifierAuthority->Value[0] || *v10 )
  {
    v18 = SidIdentifierAuthority->Value[5];
    v17 = SidIdentifierAuthority->Value[4];
    v16 = SidIdentifierAuthority->Value[3];
    v15 = SidIdentifierAuthority->Value[2];
    v14 = *v10;
    swprintf_s(
      &Buffer[(unsigned int)v9],
      (unsigned int)(v3 - v9),
      L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
      SidIdentifierAuthority->Value[0],
      v14,
      v15,
      v16,
      v17,
      v18);
  }
  else
  {
    swprintf_s(
      &Buffer[v9],
      (unsigned int)(v3 - v9),
      L"%lu",
      SidIdentifierAuthority->Value[5]
    + (SidIdentifierAuthority->Value[4] << 8)
    + (SidIdentifierAuthority->Value[3] << 16)
    + (SidIdentifierAuthority->Value[2] << 24));
  }
  for ( i = 0; i < v8; ++i )
  {
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    SidSubAuthority = GetSidSubAuthority(pSid, i);
    swprintf_s(&Buffer[(unsigned int)v12], (unsigned int)(v3 - v12), L"-%lu", *SidSubAuthority);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d478  push    rbx
0x18000d47a  push    rbp
0x18000d47b  push    rsi
0x18000d47c  push    rdi
0x18000d47d  push    r12
0x18000d47f  push    r14
0x18000d481  push    r15
0x18000d483  sub     rsp, 50h
0x18000d487  mov     r14d, r8d
0x18000d48a  mov     rsi, rdx
0x18000d48d  mov     rbp, rcx
0x18000d490  call    cs:__imp_IsValidSid
0x18000d496  xor     r12d, r12d
0x18000d499  test    eax, eax
0x18000d49b  jnz     short loc_18000D4A8
0x18000d49d  call    cs:__imp_GetLastError
0x18000d4a3  jmp     loc_18000D5C2
0x18000d4a8  mov     rcx, rbp; pSid
0x18000d4ab  call    cs:__imp_GetSidIdentifierAuthority
0x18000d4b1  mov     rcx, rbp; pSid
0x18000d4b4  mov     rbx, rax
0x18000d4b7  call    cs:__imp_GetSidSubAuthorityCount
0x18000d4bd  mov     rdx, r14; BufferCount
0x18000d4c0  lea     r8, aSLu; "S-%lu-"
0x18000d4c7  mov     r9d, 1
0x18000d4cd  mov     rcx, rsi; Buffer
0x18000d4d0  movzx   r15d, byte ptr [rax]
0x18000d4d4  call    cs:__imp_swprintf_s
0x18000d4da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d4de  inc     rcx
0x18000d4e1  cmp     [rsi+rcx*2], r12w
0x18000d4e6  jnz     short loc_18000D4DE
0x18000d4e8  movzx   edx, byte ptr [rbx]
0x18000d4eb  lea     rax, [rbx+1]
0x18000d4ef  test    dl, dl
0x18000d4f1  jnz     short loc_18000D534
0x18000d4f3  cmp     [rax], r12b
0x18000d4f6  jnz     short loc_18000D534
0x18000d4f8  movzx   r9d, byte ptr [rbx+2]
0x18000d4fd  lea     r8, aLu_0; "%lu"
0x18000d504  movzx   eax, byte ptr [rbx+3]
0x18000d508  mov     edx, r14d
0x18000d50b  shl     eax, 10h
0x18000d50e  sub     edx, ecx; BufferCount
0x18000d510  shl     r9d, 18h
0x18000d514  lea     rcx, [rsi+rcx*2]; Buffer
0x18000d518  add     r9d, eax
0x18000d51b  movzx   eax, byte ptr [rbx+4]
0x18000d51f  shl     eax, 8
0x18000d522  add     r9d, eax
0x18000d525  movzx   eax, byte ptr [rbx+5]
0x18000d529  add     r9d, eax
0x18000d52c  call    cs:__imp_swprintf_s
0x18000d532  jmp     short loc_18000D57C
0x18000d534  movzx   r8d, byte ptr [rbx+5]
0x18000d539  mov     r9d, edx
0x18000d53c  movzx   edi, byte ptr [rax]
0x18000d53f  mov     edx, r14d
0x18000d542  movzx   r10d, byte ptr [rbx+4]
0x18000d547  sub     edx, ecx; BufferCount
0x18000d549  movzx   r11d, byte ptr [rbx+3]
0x18000d54e  movzx   ebx, byte ptr [rbx+2]
0x18000d552  mov     [rsp+88h+var_48], r8d
0x18000d557  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x18000d55e  mov     [rsp+88h+var_50], r10d
0x18000d563  mov     [rsp+88h+var_58], r11d
0x18000d568  mov     eax, ecx
0x18000d56a  mov     [rsp+88h+var_60], ebx
0x18000d56e  mov     [rsp+88h+var_68], edi
0x18000d572  lea     rcx, [rsi+rax*2]; Buffer
0x18000d576  call    cs:__imp_swprintf_s
0x18000d57c  mov     edi, r12d
0x18000d57f  test    r15d, r15d
0x18000d582  jz      short loc_18000D5BF
0x18000d584  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d588  inc     rbx
0x18000d58b  cmp     [rsi+rbx*2], r12w
0x18000d590  jnz     short loc_18000D588
0x18000d592  mov     edx, edi; nSubAuthority
0x18000d594  mov     rcx, rbp; pSid
0x18000d597  call    cs:__imp_GetSidSubAuthority
0x18000d59d  mov     edx, r14d
0x18000d5a0  mov     ecx, ebx
0x18000d5a2  sub     edx, ebx; BufferCount
0x18000d5a4  lea     r8, aLu; "-%lu"
0x18000d5ab  mov     r9d, [rax]
0x18000d5ae  lea     rcx, [rsi+rcx*2]; Buffer
0x18000d5b2  call    cs:__imp_swprintf_s
0x18000d5b8  inc     edi
0x18000d5ba  cmp     edi, r15d
0x18000d5bd  jb      short loc_18000D584
0x18000d5bf  mov     eax, r12d
0x18000d5c2  add     rsp, 50h
0x18000d5c6  pop     r15
0x18000d5c8  pop     r14
0x18000d5ca  pop     r12
0x18000d5cc  pop     rdi
0x18000d5cd  pop     rsi
0x18000d5ce  pop     rbp
0x18000d5cf  pop     rbx
0x18000d5d0  retn
```
