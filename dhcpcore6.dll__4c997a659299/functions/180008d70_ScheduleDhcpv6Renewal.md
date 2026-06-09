# ScheduleDhcpv6Renewal

- ea: `0x180008d70`
- end: `0x180008e48`
- name: `ScheduleDhcpv6Renewal`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a70`
- `0x180014070`
- `0x180014590`
- `0x18001be30`
- `0x18001d258`
- `0x18001d4c4`
- `0x180020d50`
- `0x180021150`
- `0x180029360`
- `0x180029fe4`

## callees

- `0x180008d70`
- `0x180017368`
- `0x1800190c0`
- `0x180019194`
- `0x18001d62c`
- `0x180031628`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008e30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008e30`

## pseudocode

```c
int __fastcall ScheduleDhcpv6Renewal(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rdi
  unsigned int IsMachineInCs; // ebp
  __int64 v7; // rcx
  unsigned int IsMachineInDs; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // r14d
  int result; // eax
  time_t *v13; // rcx
  time_t v14; // rax

  v4 = a2;
  IsMachineInCs = Dhcpv6IsMachineInCs(a1);
  IsMachineInDs = Dhcpv6IsMachineInDs(v7);
  v11 = IsMachineInDs;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_DJll(v9, *(_QWORD *)(v9 + 24), v10, (unsigned int)v4, *(_QWORD *)(v9 + 24), IsMachineInCs, IsMachineInDs);
  result = DhcpStandbyCheckRenewalAllowed(a1 + 8936, IsMachineInCs, v11);
  if ( result )
  {
    if ( (_DWORD)v4 == -1 || (v14 = time(v13), *(_QWORD *)(a1 + 544) = v14 + v4, v14 + v4 < v14) )
      *(_QWORD *)(a1 + 544) = 0x7FFFFFFFFFFFFFFFLL;
    *(_DWORD *)(a1 + 600) = 1;
    if ( a3 )
      *(_QWORD *)(a1 + 576) = a3;
    return SetEvent(Dhcpv6GlobalRecomputeTimerEvent);
  }
  else if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    return WPP_SF_(1028, 11, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180008d70  push    rbx
0x180008d72  push    rbp
0x180008d73  push    rsi
0x180008d74  push    rdi
0x180008d75  push    r14
0x180008d77  sub     rsp, 40h
0x180008d7b  mov     rsi, r8
0x180008d7e  mov     edi, edx
0x180008d80  mov     rbx, rcx
0x180008d83  call    Dhcpv6IsMachineInCs
0x180008d88  mov     ebp, eax
0x180008d8a  call    Dhcpv6IsMachineInDs
0x180008d8f  mov     r14d, eax
0x180008d92  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008d99  jz      short loc_180008DB4
0x180008d9b  mov     rdx, [rcx+18h]
0x180008d9f  mov     r9d, edi
0x180008da2  mov     [rsp+68h+var_38], eax
0x180008da6  mov     [rsp+68h+var_40], ebp
0x180008daa  mov     [rsp+68h+var_48], rdx
0x180008daf  call    WPP_SF_DJll
0x180008db4  lea     rcx, [rbx+22E8h]
0x180008dbb  mov     r8d, r14d
0x180008dbe  mov     edx, ebp
0x180008dc0  call    DhcpStandbyCheckRenewalAllowed
0x180008dc5  test    eax, eax
0x180008dc7  jnz     short loc_180008DE8
0x180008dc9  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008dd0  jz      short loc_180008E3C
0x180008dd2  lea     edx, [rax+0Bh]
0x180008dd5  mov     ecx, 404h
0x180008dda  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180008de1  call    WPP_SF_
0x180008de6  jmp     short loc_180008E3C
0x180008de8  cmp     edi, 0FFFFFFFFh
0x180008deb  jz      short loc_180008E02
0x180008ded  call    time
0x180008df2  lea     rdx, [rax+rdi]
0x180008df6  mov     [rbx+220h], rdx
0x180008dfd  cmp     rdx, rax
0x180008e00  jge     short loc_180008E13
0x180008e02  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008e0c  mov     [rbx+220h], rax
0x180008e13  mov     dword ptr [rbx+258h], 1
0x180008e1d  test    rsi, rsi
0x180008e20  jz      short loc_180008E29
0x180008e22  mov     [rbx+240h], rsi
0x180008e29  mov     rcx, cs:Dhcpv6GlobalRecomputeTimerEvent; hEvent
0x180008e30  call    cs:__imp_SetEvent
0x180008e37  nop     dword ptr [rax+rax+00h]
0x180008e3c  add     rsp, 40h
0x180008e40  pop     r14
0x180008e42  pop     rdi
0x180008e43  pop     rsi
0x180008e44  pop     rbp
0x180008e45  pop     rbx
0x180008e46  retn
```
