# DaConvertSidToString

- ea: `0x18000e000`
- end: `0x18000e190`
- name: `DaConvertSidToString`
- size: `400`
- prototype: `__int64 __fastcall(PSID pSid, wchar_t *Buffer, size_t BufferCount)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000c738`
- `0x18000d644`
- `0x18000da44`

## callees

- `0x18000e000`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000e074`
- `msvcrt!swprintf_s` at `0x18000e0d2`
- `msvcrt!swprintf_s` at `0x18000e122`
- `msvcrt!swprintf_s` at `0x18000e16a`
- `msvcrt!swprintf_s` at `0x18000e074`
- `msvcrt!swprintf_s` at `0x18000e0d2`
- `msvcrt!swprintf_s` at `0x18000e122`
- `msvcrt!swprintf_s` at `0x18000e16a`
- `KERNEL32!GetLastError` at `0x18000e02b`
- `KERNEL32!GetLastError` at `0x18000e02b`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18000e051`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18000e051`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18000e03f`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18000e03f`
- `ADVAPI32!IsValidSid` at `0x18000e018`
- `ADVAPI32!IsValidSid` at `0x18000e018`
- `ADVAPI32!GetSidSubAuthority` at `0x18000e149`
- `ADVAPI32!GetSidSubAuthority` at `0x18000e149`

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
0x18000e000  push    rbx
0x18000e002  push    rbp
0x18000e003  push    rsi
0x18000e004  push    rdi
0x18000e005  push    r12
0x18000e007  push    r14
0x18000e009  push    r15
0x18000e00b  sub     rsp, 50h
0x18000e00f  mov     r14d, r8d
0x18000e012  mov     rsi, rdx
0x18000e015  mov     rbp, rcx
0x18000e018  call    cs:__imp_IsValidSid
0x18000e01f  nop     dword ptr [rax+rax+00h]
0x18000e024  xor     r12d, r12d
0x18000e027  test    eax, eax
0x18000e029  jnz     short loc_18000E03C
0x18000e02b  call    cs:__imp_GetLastError
0x18000e032  nop     dword ptr [rax+rax+00h]
0x18000e037  jmp     loc_18000E180
0x18000e03c  mov     rcx, rbp; pSid
0x18000e03f  call    cs:__imp_GetSidIdentifierAuthority
0x18000e046  nop     dword ptr [rax+rax+00h]
0x18000e04b  mov     rcx, rbp; pSid
0x18000e04e  mov     rbx, rax
0x18000e051  call    cs:__imp_GetSidSubAuthorityCount
0x18000e058  nop     dword ptr [rax+rax+00h]
0x18000e05d  mov     rdx, r14; BufferCount
0x18000e060  lea     r8, aSLu; "S-%lu-"
0x18000e067  mov     r9d, 1
0x18000e06d  mov     rcx, rsi; Buffer
0x18000e070  movzx   r15d, byte ptr [rax]
0x18000e074  call    cs:__imp_swprintf_s
0x18000e07b  nop     dword ptr [rax+rax+00h]
0x18000e080  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e084  inc     rcx
0x18000e087  cmp     [rsi+rcx*2], r12w
0x18000e08c  jnz     short loc_18000E084
0x18000e08e  movzx   edx, byte ptr [rbx]
0x18000e091  lea     rax, [rbx+1]
0x18000e095  test    dl, dl
0x18000e097  jnz     short loc_18000E0E0
0x18000e099  cmp     [rax], r12b
0x18000e09c  jnz     short loc_18000E0E0
0x18000e09e  movzx   r9d, byte ptr [rbx+2]
0x18000e0a3  lea     r8, aLu_0; "%lu"
0x18000e0aa  movzx   eax, byte ptr [rbx+3]
0x18000e0ae  mov     edx, r14d
0x18000e0b1  shl     eax, 10h
0x18000e0b4  sub     edx, ecx; BufferCount
0x18000e0b6  shl     r9d, 18h
0x18000e0ba  lea     rcx, [rsi+rcx*2]; Buffer
0x18000e0be  add     r9d, eax
0x18000e0c1  movzx   eax, byte ptr [rbx+4]
0x18000e0c5  shl     eax, 8
0x18000e0c8  add     r9d, eax
0x18000e0cb  movzx   eax, byte ptr [rbx+5]
0x18000e0cf  add     r9d, eax
0x18000e0d2  call    cs:__imp_swprintf_s
0x18000e0d9  nop     dword ptr [rax+rax+00h]
0x18000e0de  jmp     short loc_18000E12E
0x18000e0e0  movzx   r8d, byte ptr [rbx+5]
0x18000e0e5  mov     r9d, edx
0x18000e0e8  movzx   edi, byte ptr [rax]
0x18000e0eb  mov     edx, r14d
0x18000e0ee  movzx   r10d, byte ptr [rbx+4]
0x18000e0f3  sub     edx, ecx; BufferCount
0x18000e0f5  movzx   r11d, byte ptr [rbx+3]
0x18000e0fa  movzx   ebx, byte ptr [rbx+2]
0x18000e0fe  mov     [rsp+88h+var_48], r8d
0x18000e103  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x18000e10a  mov     [rsp+88h+var_50], r10d
0x18000e10f  mov     [rsp+88h+var_58], r11d
0x18000e114  mov     eax, ecx
0x18000e116  mov     [rsp+88h+var_60], ebx
0x18000e11a  mov     [rsp+88h+var_68], edi
0x18000e11e  lea     rcx, [rsi+rax*2]; Buffer
0x18000e122  call    cs:__imp_swprintf_s
0x18000e129  nop     dword ptr [rax+rax+00h]
0x18000e12e  mov     edi, r12d
0x18000e131  test    r15d, r15d
0x18000e134  jz      short loc_18000E17D
0x18000e136  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e13a  inc     rbx
0x18000e13d  cmp     [rsi+rbx*2], r12w
0x18000e142  jnz     short loc_18000E13A
0x18000e144  mov     edx, edi; nSubAuthority
0x18000e146  mov     rcx, rbp; pSid
0x18000e149  call    cs:__imp_GetSidSubAuthority
0x18000e150  nop     dword ptr [rax+rax+00h]
0x18000e155  mov     edx, r14d
0x18000e158  mov     ecx, ebx
0x18000e15a  sub     edx, ebx; BufferCount
0x18000e15c  lea     r8, aLu; "-%lu"
0x18000e163  mov     r9d, [rax]
0x18000e166  lea     rcx, [rsi+rcx*2]; Buffer
0x18000e16a  call    cs:__imp_swprintf_s
0x18000e171  nop     dword ptr [rax+rax+00h]
0x18000e176  inc     edi
0x18000e178  cmp     edi, r15d
0x18000e17b  jb      short loc_18000E136
0x18000e17d  mov     eax, r12d
0x18000e180  add     rsp, 50h
0x18000e184  pop     r15
0x18000e186  pop     r14
0x18000e188  pop     r12
0x18000e18a  pop     rdi
0x18000e18b  pop     rsi
0x18000e18c  pop     rbp
0x18000e18d  pop     rbx
0x18000e18e  retn
```
