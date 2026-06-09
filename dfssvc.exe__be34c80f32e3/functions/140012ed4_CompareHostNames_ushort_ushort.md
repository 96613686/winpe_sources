# CompareHostNames(ushort *,ushort *)

- ea: `0x140012ed4`
- end: `0x140012f6d`
- name: `?CompareHostNames@@YAKPEAG0@Z`
- size: `153`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001407c`

## callees

- `0x140012ed4`
- `0x14005ce70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140012f41`
- `msvcrt!_wcsicmp` at `0x140012f41`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x140012f29`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x140012f29`

## pseudocode

```c
unsigned int __fastcall CompareHostNames(unsigned __int16 *a1, unsigned __int16 *a2)
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
    return _wcsicmp(a1, a2);
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 <= 0xF )
    return _wcsicmp(a1, a2);
  if ( DnsHostnameToComputerNameW(a1, ComputerName, &nSize) )
  {
    a1 = ComputerName;
    return _wcsicmp(a1, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x140012ed4  mov     [rsp+arg_10], rbx
0x140012ed9  push    rdi
0x140012eda  sub     rsp, 50h
0x140012ede  mov     rax, cs:__security_cookie
0x140012ee5  xor     rax, rsp
0x140012ee8  mov     [rsp+58h+var_10], rax
0x140012eed  mov     rbx, rdx
0x140012ef0  mov     [rsp+58h+nSize], 10h
0x140012ef8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140012efc  mov     rax, rdx
0x140012eff  xor     edi, edi
0x140012f01  inc     rax
0x140012f04  cmp     [rbx+rax*2], di
0x140012f08  jnz     short loc_140012F01
0x140012f0a  cmp     rax, 0Fh
0x140012f0e  ja      short loc_140012F3E
0x140012f10  inc     rdx
0x140012f13  cmp     [rcx+rdx*2], di
0x140012f17  jnz     short loc_140012F10
0x140012f19  cmp     rdx, 0Fh
0x140012f1d  jbe     short loc_140012F3E
0x140012f1f  lea     r8, [rsp+58h+nSize]; nSize
0x140012f24  lea     rdx, [rsp+58h+ComputerName]; ComputerName
0x140012f29  call    cs:__imp_DnsHostnameToComputerNameW
0x140012f30  nop     dword ptr [rax+rax+00h]
0x140012f35  test    eax, eax
0x140012f37  jz      short loc_140012F66
0x140012f39  lea     rcx, [rsp+58h+ComputerName]; String1
0x140012f3e  mov     rdx, rbx; String2
0x140012f41  call    cs:__imp__wcsicmp
0x140012f48  nop     dword ptr [rax+rax+00h]
0x140012f4d  mov     rcx, [rsp+58h+var_10]
0x140012f52  xor     rcx, rsp; StackCookie
0x140012f55  call    __security_check_cookie
0x140012f5a  mov     rbx, [rsp+58h+arg_10]
0x140012f5f  add     rsp, 50h
0x140012f63  pop     rdi
0x140012f64  retn
0x140012f66  mov     eax, 1
0x140012f6b  jmp     short loc_140012F4D
```
