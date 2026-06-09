# PcpEtwWriteEventUlongPtr

- ea: `0x140011670`
- end: `0x1400116e3`
- name: `PcpEtwWriteEventUlongPtr`
- size: `115`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000287c`
- `0x14000d174`
- `0x14000fc40`
- `0x14000fcc0`
- `0x14000ffe0`
- `0x1400112e0`
- `0x1400113d0`

## callees

- `0x14001155c`
- `0x140011670`
- `0x140013110`

## pseudocode

```c
void __fastcall PcpEtwWriteEventUlongPtr(
        const EVENT_DESCRIPTOR *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5)
{
  GUID *p_ActivityId; // rdx
  const GUID *v7; // rax
  GUID ActivityId; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h] BYREF

  p_ActivityId = 0;
  v7 = 0;
  ActivityId = 0;
  v9 = 0;
  if ( a2 )
  {
    *(_QWORD *)&ActivityId.Data1 = a2;
    p_ActivityId = &ActivityId;
  }
  if ( a3 )
  {
    *(_QWORD *)&v9 = a3;
    v7 = (const GUID *)&v9;
  }
  PcpEtwWriteEvent(a1, p_ActivityId, v7, a4, &a5);
}

```

## disassembly

```asm
0x140011670  mov     [rsp+arg_18], r9w
0x140011676  sub     rsp, 68h
0x14001167a  mov     rax, cs:__security_cookie
0x140011681  xor     rax, rsp
0x140011684  mov     [rsp+68h+var_10], rax
0x140011689  mov     r10, rdx
0x14001168c  xorps   xmm0, xmm0
0x14001168f  xor     edx, edx
0x140011691  xor     eax, eax
0x140011693  movups  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x140011698  movups  [rsp+68h+var_20], xmm0
0x14001169d  test    r10, r10
0x1400116a0  jz      short loc_1400116AC
0x1400116a2  mov     qword ptr [rsp+68h+ActivityId.Data1], r10
0x1400116a7  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x1400116ac  test    r8, r8
0x1400116af  jz      short loc_1400116BB
0x1400116b1  mov     qword ptr [rsp+68h+var_20], r8
0x1400116b6  lea     rax, [rsp+68h+var_20]
0x1400116bb  lea     r8, [rsp+68h+arg_20]
0x1400116c3  mov     [rsp+68h+var_48], r8; __int64
0x1400116c8  mov     r8, rax; RelatedActivityId
0x1400116cb  call    PcpEtwWriteEvent
0x1400116d0  mov     rcx, [rsp+68h+var_10]
0x1400116d5  xor     rcx, rsp; StackCookie
0x1400116d8  call    __security_check_cookie
0x1400116dd  add     rsp, 68h
0x1400116e1  retn
```
