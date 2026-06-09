# NdisWanResetProtocolInfoTable

- ea: `0x140006d9c`
- end: `0x140006e12`
- name: `NdisWanResetProtocolInfoTable`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000bb00`
- `0x14003aa1c`

## callees

- `0x140006e18`

## pseudocode

```c
void NdisWanResetProtocolInfoTable()
{
  PKSPIN_LOCK v0; // rax
  _DWORD v1[3]; // [rsp+20h] [rbp-20h] BYREF
  int v2; // [rsp+2Ch] [rbp-14h]
  int v3; // [rsp+30h] [rbp-10h]

  v0 = ProtocolInfoTable;
  v1[0] = 11250432;
  v3 = 0x20000;
  v1[1] = 1;
  *((_DWORD *)ProtocolInfoTable + 6) = 0;
  v0[4] = 0;
  v1[2] = 1500;
  v2 = 1500;
  SetProtocolInfo((__int64)v1);
  v1[0] = 2164736;
  v2 = 1400;
  SetProtocolInfo((__int64)v1);
  v1[0] = 5736157;
  SetProtocolInfo((__int64)v1);
}

```

## disassembly

```asm
0x140006d9c  push    rbp
0x140006d9e  mov     rbp, rsp
0x140006da1  sub     rsp, 40h
0x140006da5  mov     rax, cs:ProtocolInfoTable
0x140006dac  lea     rcx, [rbp+var_20]
0x140006db0  mov     [rbp+var_20], 0ABAB00h
0x140006db7  mov     [rbp+var_10], 20000h
0x140006dbe  mov     [rbp+var_1C], 1
0x140006dc5  mov     dword ptr [rax+18h], 0
0x140006dcc  mov     qword ptr [rax+20h], 0
0x140006dd4  mov     eax, 5DCh
0x140006dd9  mov     [rbp+var_18], eax
0x140006ddc  mov     [rbp+var_14], eax
0x140006ddf  call    SetProtocolInfo
0x140006de4  lea     rcx, [rbp+var_20]
0x140006de8  mov     [rbp+var_20], 210800h
0x140006def  mov     [rbp+var_14], 578h
0x140006df6  call    SetProtocolInfo
0x140006dfb  lea     rcx, [rbp+var_20]
0x140006dff  mov     [rbp+var_20], 5786DDh
0x140006e06  call    SetProtocolInfo
0x140006e0b  add     rsp, 40h
0x140006e0f  pop     rbp
0x140006e10  retn
```
