# DhcpPowerStateChangeNotification

- ea: `0x18000e644`
- end: `0x18000e6dc`
- name: `DhcpPowerStateChangeNotification`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bd50`

## callees

- `0x18000e644`
- `0x180019ad0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000e688`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000e688`

## pseudocode

```c
__int64 __fastcall DhcpPowerStateChangeNotification(int a1, _DWORD *a2)
{
  unsigned int v3; // edi
  int v4; // ecx
  GUID Source2; // [rsp+20h] [rbp-28h] BYREF

  Source2 = GUID_LOW_POWER_EPOCH;
  if ( a2 )
  {
    v3 = 0;
    if ( a1 == 32787 && RtlCompareMemory(a2, &Source2, 0x10u) == 16 && a2[4] == 4 )
    {
      v4 = a2[5];
      if ( v4 )
      {
        if ( v4 == 1 )
          Dhcpv6GlobalIsInCS = 1;
      }
      else
      {
        Dhcpv6GlobalIsInCS = 0;
      }
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18000e644  mov     [rsp+arg_0], rbx
0x18000e649  push    rdi
0x18000e64a  sub     rsp, 40h
0x18000e64e  mov     rax, cs:__security_cookie
0x18000e655  xor     rax, rsp
0x18000e658  mov     [rsp+48h+var_18], rax
0x18000e65d  mov     rbx, rdx
0x18000e660  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18000e667  movdqu  [rsp+48h+Source2], xmm0
0x18000e66d  test    rdx, rdx
0x18000e670  jz      short loc_18000E6D5
0x18000e672  xor     edi, edi
0x18000e674  cmp     ecx, 8013h
0x18000e67a  jnz     short loc_18000E6B2
0x18000e67c  lea     r8d, [rdi+10h]; Length
0x18000e680  mov     rcx, rbx; Source1
0x18000e683  lea     rdx, [rsp+48h+Source2]; Source2
0x18000e688  call    cs:__imp_RtlCompareMemory
0x18000e68f  nop     dword ptr [rax+rax+00h]
0x18000e694  cmp     rax, 10h
0x18000e698  jnz     short loc_18000E6B2
0x18000e69a  cmp     dword ptr [rbx+10h], 4
0x18000e69e  jnz     short loc_18000E6B2
0x18000e6a0  mov     ecx, [rbx+14h]
0x18000e6a3  test    ecx, ecx
0x18000e6a5  jz      short loc_18000E6CD
0x18000e6a7  cmp     ecx, 1
0x18000e6aa  jnz     short loc_18000E6B2
0x18000e6ac  mov     cs:Dhcpv6GlobalIsInCS, ecx
0x18000e6b2  mov     eax, edi
0x18000e6b4  mov     rcx, [rsp+48h+var_18]
0x18000e6b9  xor     rcx, rsp; StackCookie
0x18000e6bc  call    __security_check_cookie
0x18000e6c1  mov     rbx, [rsp+48h+arg_0]
0x18000e6c6  add     rsp, 40h
0x18000e6ca  pop     rdi
0x18000e6cb  retn
0x18000e6cd  mov     cs:Dhcpv6GlobalIsInCS, edi
0x18000e6d3  jmp     short loc_18000E6B2
0x18000e6d5  mov     edi, 57h ; 'W'
0x18000e6da  jmp     short loc_18000E6B2
```
