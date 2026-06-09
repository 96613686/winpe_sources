# DhcpV6ComputeInitRetryInterval

- ea: `0x180020610`
- end: `0x1800206a4`
- name: `DhcpV6ComputeInitRetryInterval`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f0d8`

## callees

- `0x1800190c0`
- `0x18001e5c0`
- `0x180020610`
- `0x180033de4`

## pseudocode

```c
__int64 __fastcall DhcpV6ComputeInitRetryInterval(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // [rsp+38h] [rbp+10h] BYREF
  int v8; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v7 = 0;
  v8 = 0;
  result = Dhcpv6CheckDhcpv4Address(a1, &v8, &v7);
  if ( (_DWORD)result )
  {
    v5 = 43200;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      v6 = 209;
LABEL_9:
      result = WPP_SF_d(1028, v6, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v5);
    }
  }
  else
  {
    result = Dhcpv6IsMachineInCs(v4);
    if ( (_DWORD)result )
    {
      v5 = AddrAcquireRetryIntervalInCS;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v6 = 210;
        goto LABEL_9;
      }
    }
    else
    {
      v5 = AddrAcquireRetryInterval;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v6 = 211;
        goto LABEL_9;
      }
    }
  }
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180020610  mov     rax, rsp
0x180020613  mov     [rax+8], rbx
0x180020617  push    rdi
0x180020618  sub     rsp, 20h
0x18002061c  xor     ebx, ebx
0x18002061e  lea     r8, [rax+10h]
0x180020622  mov     [rdx], ebx
0x180020624  mov     rdi, rdx
0x180020627  lea     rdx, [rax+18h]
0x18002062b  mov     [rax+10h], ebx
0x18002062e  mov     [rax+18h], ebx
0x180020631  call    Dhcpv6CheckDhcpv4Address
0x180020636  test    eax, eax
0x180020638  jz      short loc_18002064F
0x18002063a  mov     ebx, 0A8C0h
0x18002063f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180020646  jz      short loc_180020696
0x180020648  mov     edx, 0D1h
0x18002064d  jmp     short loc_180020682
0x18002064f  call    Dhcpv6IsMachineInCs
0x180020654  test    eax, eax
0x180020656  jz      short loc_18002066E
0x180020658  mov     ebx, cs:AddrAcquireRetryIntervalInCS
0x18002065e  test    byte ptr cs:xmmword_1800423E0, 10h
0x180020665  jz      short loc_180020696
0x180020667  mov     edx, 0D2h
0x18002066c  jmp     short loc_180020682
0x18002066e  mov     ebx, cs:AddrAcquireRetryInterval
0x180020674  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002067b  jz      short loc_180020696
0x18002067d  mov     edx, 0D3h
0x180020682  mov     r9d, ebx
0x180020685  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18002068c  mov     ecx, 404h
0x180020691  call    WPP_SF_d
0x180020696  mov     [rdi], ebx
0x180020698  mov     rbx, [rsp+28h+arg_0]
0x18002069d  add     rsp, 20h
0x1800206a1  pop     rdi
0x1800206a2  retn
```
