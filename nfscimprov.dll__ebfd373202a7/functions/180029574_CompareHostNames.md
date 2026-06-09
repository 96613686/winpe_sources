# CompareHostNames

- ea: `0x180029574`
- end: `0x1800295ff`
- name: `CompareHostNames`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ad9c`

## callees

- `0x180001cde`
- `0x180029574`
- `0x180035b40`

## import_xrefs

- `KERNEL32!DnsHostnameToComputerNameW` at `0x1800295c9`
- `KERNEL32!DnsHostnameToComputerNameW` at `0x1800295c9`

## pseudocode

```c
int __fastcall CompareHostNames(WCHAR *a1, const wchar_t *a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rax
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR ComputerName[16]; // [rsp+28h] [rbp-30h] BYREF

  nSize = 16;
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 > 0xF )
    return wcsicmp_0(a1, a2);
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 <= 0xF )
    return wcsicmp_0(a1, a2);
  if ( DnsHostnameToComputerNameW(a1, ComputerName, &nSize) )
  {
    a1 = ComputerName;
    return wcsicmp_0(a1, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x180029574  mov     [rsp+arg_10], rbx
0x180029579  push    rdi
0x18002957a  sub     rsp, 50h
0x18002957e  mov     rax, cs:__security_cookie
0x180029585  xor     rax, rsp
0x180029588  mov     [rsp+58h+var_10], rax
0x18002958d  mov     rbx, rdx
0x180029590  mov     [rsp+58h+nSize], 10h
0x180029598  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002959c  mov     rax, rdx
0x18002959f  xor     edi, edi
0x1800295a1  inc     rax
0x1800295a4  cmp     [rbx+rax*2], di
0x1800295a8  jnz     short loc_1800295A1
0x1800295aa  cmp     rax, 0Fh
0x1800295ae  ja      short loc_1800295D8
0x1800295b0  inc     rdx
0x1800295b3  cmp     [rcx+rdx*2], di
0x1800295b7  jnz     short loc_1800295B0
0x1800295b9  cmp     rdx, 0Fh
0x1800295bd  jbe     short loc_1800295D8
0x1800295bf  lea     r8, [rsp+58h+nSize]; nSize
0x1800295c4  lea     rdx, [rsp+58h+ComputerName]; ComputerName
0x1800295c9  call    cs:__imp_DnsHostnameToComputerNameW
0x1800295cf  test    eax, eax
0x1800295d1  jz      short loc_1800295F8
0x1800295d3  lea     rcx, [rsp+58h+ComputerName]; String1
0x1800295d8  mov     rdx, rbx; String2
0x1800295db  call    _wcsicmp_0
0x1800295e0  mov     rcx, [rsp+58h+var_10]
0x1800295e5  xor     rcx, rsp; StackCookie
0x1800295e8  call    __security_check_cookie
0x1800295ed  mov     rbx, [rsp+58h+arg_10]
0x1800295f2  add     rsp, 50h
0x1800295f6  pop     rdi
0x1800295f7  retn
0x1800295f8  mov     eax, 1
0x1800295fd  jmp     short loc_1800295E0
```
