# Dhcpv6CleanupRegistry

- ea: `0x18002a3a8`
- end: `0x18002a44d`
- name: `Dhcpv6CleanupRegistry`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b314`

## callees

- `0x18000c740`
- `0x18002a3a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a41c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a41c`

## pseudocode

```c
_QWORD *Dhcpv6CleanupRegistry()
{
  _QWORD *result; // rax
  __int64 v1; // rcx
  __int64 i; // rbx
  HKEY *v3; // rcx
  HKEY v4; // rcx
  LPVOID v5; // [rsp+30h] [rbp+8h] BYREF

  while ( 1 )
  {
    result = Dhcpv6GlobalOptionDefList;
    if ( Dhcpv6GlobalOptionDefList == (_UNKNOWN *)&Dhcpv6GlobalOptionDefList )
      break;
    if ( *((_UNKNOWN ***)Dhcpv6GlobalOptionDefList + 1) != &Dhcpv6GlobalOptionDefList
      || (v1 = *(_QWORD *)Dhcpv6GlobalOptionDefList,
          *(_UNKNOWN **)(*(_QWORD *)Dhcpv6GlobalOptionDefList + 8LL) != Dhcpv6GlobalOptionDefList) )
    {
      __fastfail(3u);
    }
    Dhcpv6GlobalOptionDefList = *(_UNKNOWN **)Dhcpv6GlobalOptionDefList;
    *(_QWORD *)(v1 + 8) = &Dhcpv6GlobalOptionDefList;
    v5 = result;
    DhcpFree(&v5);
  }
  for ( i = 0; i != 4; ++i )
  {
    v3 = (HKEY *)off_1800420B0[2 * i];
    if ( v3 )
    {
      v4 = *v3;
      if ( v4 )
      {
        RegCloseKey(v4);
        result = (_QWORD *)off_1800420B0[2 * i];
        *result = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a3a8  mov     [rsp+arg_8], rbx
0x18002a3ad  mov     [rsp+arg_10], rsi
0x18002a3b2  push    rdi
0x18002a3b3  sub     rsp, 20h
0x18002a3b7  lea     rbx, Dhcpv6GlobalOptionDefList
0x18002a3be  mov     rax, cs:Dhcpv6GlobalOptionDefList
0x18002a3c5  cmp     rax, rbx
0x18002a3c8  jz      short loc_18002A3FC
0x18002a3ca  cmp     [rax+8], rbx
0x18002a3ce  jnz     short loc_18002A3F5
0x18002a3d0  mov     rcx, [rax]
0x18002a3d3  cmp     [rcx+8], rax
0x18002a3d7  jnz     short loc_18002A3F5
0x18002a3d9  mov     cs:Dhcpv6GlobalOptionDefList, rcx
0x18002a3e0  mov     [rcx+8], rbx
0x18002a3e4  lea     rcx, [rsp+28h+arg_0]
0x18002a3e9  mov     [rsp+28h+arg_0], rax
0x18002a3ee  call    DhcpFree
0x18002a3f3  jmp     short loc_18002A3BE
0x18002a3f5  mov     ecx, 3
0x18002a3fa  int     29h; Win8: RtlFailFast(ecx)
0x18002a3fc  xor     ebx, ebx
0x18002a3fe  mov     rdi, rbx
0x18002a401  lea     rsi, off_1800420B0
0x18002a408  add     rdi, rdi
0x18002a40b  mov     rcx, [rsi+rdi*8]
0x18002a40f  test    rcx, rcx
0x18002a412  jz      short loc_18002A433
0x18002a414  mov     rcx, [rcx]; hKey
0x18002a417  test    rcx, rcx
0x18002a41a  jz      short loc_18002A433
0x18002a41c  call    cs:__imp_RegCloseKey
0x18002a423  nop     dword ptr [rax+rax+00h]
0x18002a428  mov     rax, [rsi+rdi*8]
0x18002a42c  mov     qword ptr [rax], 0
0x18002a433  inc     rbx
0x18002a436  cmp     rbx, 4
0x18002a43a  jnz     short loc_18002A3FE
0x18002a43c  mov     rbx, [rsp+28h+arg_8]
0x18002a441  mov     rsi, [rsp+28h+arg_10]
0x18002a446  add     rsp, 20h
0x18002a44a  pop     rdi
0x18002a44b  retn
```
