# lldpAdjustRxPacketFilters

- ea: `0x140011cac`
- end: `0x140011e1f`
- name: `lldpAdjustRxPacketFilters`
- size: `371`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010150`
- `0x1400114d0`
- `0x140011aa0`

## callees

- `0x140004320`
- `0x140004340`
- `0x140005a6c`
- `0x14000f9b4`
- `0x140011cac`
- `0x140012568`
- `0x14001280c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140011d69`
- `ntoskrnl!KeDelayExecutionThread` at `0x140011d69`

## pseudocode

```c
__int64 __fastcall lldpAdjustRxPacketFilters(__int64 a1)
{
  int Config; // eax
  __int64 v3; // rcx
  int v4; // eax
  __int64 result; // rax
  struct _KTHREAD *CurrentThread; // rsi
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp+10h] BYREF

  Config = lldpGetConfig(a1, 0);
  if ( Config && (v4 = Config - 1) != 0 && (unsigned int)(v4 - 1) <= 1 )
  {
    result = (unsigned int)_InterlockedExchange((volatile __int32 *)(v3 + 856), 1);
    if ( (_DWORD)result )
      return result;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids,
        *(unsigned __int16 *)(a1 + 126),
        (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF);
    CurrentThread = KeGetCurrentThread();
    Interval.QuadPart = -10000;
    while ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 16), (signed __int64)CurrentThread, 0) )
    {
      KeDelayExecutionThread(0, 0, &Interval);
      if ( Interval.QuadPart > -10000000 )
        Interval.QuadPart *= 2LL;
    }
    if ( *(_QWORD *)(a1 + 24) )
      lldpBindingReferenceRxPacketFilter();
  }
  else
  {
    result = (unsigned int)_InterlockedExchange((volatile __int32 *)(v3 + 856), 0);
    if ( !(_DWORD)result )
      return result;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids,
        *(unsigned __int16 *)(a1 + 126),
        (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF);
    lldpAcquireInterLock(a1 + 8, 0);
    if ( *(_QWORD *)(a1 + 24) )
      lldpBindingDereferenceRxPacketFilter();
  }
  return lldpReleaseInterLock(a1 + 8);
}

```

## disassembly

```asm
0x140011cac  mov     [rsp+arg_0], rbx
0x140011cb1  mov     [rsp+arg_18], rsi
0x140011cb6  push    rdi
0x140011cb7  sub     rsp, 30h
0x140011cbb  xor     edx, edx
0x140011cbd  mov     rbx, rcx
0x140011cc0  call    lldpGetConfig
0x140011cc5  test    eax, eax
0x140011cc7  jz      loc_140011D9C
0x140011ccd  sub     eax, 1
0x140011cd0  jz      loc_140011D9C
0x140011cd6  sub     eax, 1
0x140011cd9  jz      short loc_140011CE4
0x140011cdb  cmp     eax, 1
0x140011cde  jnz     loc_140011D9C
0x140011ce4  mov     eax, 1
0x140011ce9  xchg    eax, [rcx+358h]
0x140011cef  test    eax, eax
0x140011cf1  jnz     loc_140011E0E
0x140011cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cfe  lea     rax, WPP_GLOBAL_Control
0x140011d05  cmp     rcx, rax
0x140011d08  jz      short loc_140011D3B
0x140011d0a  cmp     byte ptr [rcx+29h], 4
0x140011d0e  jb      short loc_140011D3B
0x140011d10  mov     rax, [rbx+78h]
0x140011d14  lea     r8, WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids
0x140011d1b  movzx   r9d, word ptr [rbx+7Eh]
0x140011d20  mov     edx, 1Ah
0x140011d25  mov     rcx, [rcx+18h]
0x140011d29  shr     rax, 18h
0x140011d2d  and     eax, 0FFFFFFh
0x140011d32  mov     [rsp+38h+var_18], eax
0x140011d36  call    WPP_SF_DD
0x140011d3b  mov     qword ptr [rsp+38h+Interval], 0
0x140011d44  mov     rsi, gs:188h
0x140011d4d  mov     qword ptr [rsp+38h+Interval], 0FFFFFFFFFFFFD8F0h
0x140011d56  xor     eax, eax
0x140011d58  lock cmpxchg [rbx+10h], rsi
0x140011d5e  jz      short loc_140011D8C
0x140011d60  lea     r8, [rsp+38h+Interval]; Interval
0x140011d65  xor     edx, edx; Alertable
0x140011d67  xor     ecx, ecx; WaitMode
0x140011d69  call    cs:__imp_KeDelayExecutionThread
0x140011d70  nop     dword ptr [rax+rax+00h]
0x140011d75  mov     rax, qword ptr [rsp+38h+Interval]
0x140011d7a  cmp     rax, 0FFFFFFFFFF676980h
0x140011d80  jle     short loc_140011D56
0x140011d82  add     rax, rax
0x140011d85  mov     qword ptr [rsp+38h+Interval], rax
0x140011d8a  jmp     short loc_140011D56
0x140011d8c  mov     rcx, [rbx+18h]
0x140011d90  test    rcx, rcx
0x140011d93  jz      short loc_140011E05
0x140011d95  call    lldpBindingReferenceRxPacketFilter
0x140011d9a  jmp     short loc_140011E05
0x140011d9c  xor     eax, eax
0x140011d9e  xchg    eax, [rcx+358h]
0x140011da4  test    eax, eax
0x140011da6  jz      short loc_140011E0E
0x140011da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140011daf  lea     rax, WPP_GLOBAL_Control
0x140011db6  cmp     rcx, rax
0x140011db9  jz      short loc_140011DEC
0x140011dbb  cmp     byte ptr [rcx+29h], 4
0x140011dbf  jb      short loc_140011DEC
0x140011dc1  mov     rax, [rbx+78h]
0x140011dc5  lea     r8, WPP_dc65fd90403c30e5e64868c1e34e4ed6_Traceguids
0x140011dcc  movzx   r9d, word ptr [rbx+7Eh]
0x140011dd1  mov     edx, 1Bh
0x140011dd6  mov     rcx, [rcx+18h]
0x140011dda  shr     rax, 18h
0x140011dde  and     eax, 0FFFFFFh
0x140011de3  mov     [rsp+38h+var_18], eax
0x140011de7  call    WPP_SF_DD
0x140011dec  xor     edx, edx
0x140011dee  lea     rcx, [rbx+8]
0x140011df2  call    lldpAcquireInterLock
0x140011df7  mov     rcx, [rbx+18h]
0x140011dfb  test    rcx, rcx
0x140011dfe  jz      short loc_140011E05
0x140011e00  call    lldpBindingDereferenceRxPacketFilter
0x140011e05  lea     rcx, [rbx+8]
0x140011e09  call    lldpReleaseInterLock
0x140011e0e  mov     rbx, [rsp+38h+arg_0]
0x140011e13  mov     rsi, [rsp+38h+arg_18]
0x140011e18  add     rsp, 30h
0x140011e1c  pop     rdi
0x140011e1d  retn
```
