# ACCreateTransaction

- ea: `0x140005cec`
- end: `0x140005e15`
- name: `ACCreateTransaction`
- size: `297`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x140003d84`
- `0x140005cec`
- `0x14001efe0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140005d10`
- `ntoskrnl!ProbeForRead` at `0x140005d10`

## pseudocode

```c
__int64 __fastcall ACCreateTransaction(struct _DEVICE_OBJECT *a1, __int64 a2, __int128 *a3)
{
  CTransaction *v6; // rax
  CTransaction *v7; // rbx
  __int128 v9; // [rsp+20h] [rbp-18h] BYREF

  ProbeForRead(a3, 0x10u, 1u);
  v9 = *a3;
  v6 = (CTransaction *)operator new(0x88u, 0x40u, 0x5441514Du, LowPoolPriority);
  if ( v6 )
    v7 = CTransaction::CTransaction(v6, a1, (const struct BOID *)&v9);
  else
    v7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 201, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v7);
  }
  if ( v7 )
  {
    *(_QWORD *)(a2 + 24) = v7;
    *(_DWORD *)(*(_QWORD *)(a2 + 32) + 20LL) |= 1u;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 202, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140005cec  mov     [rsp+arg_0], rbx
0x140005cf1  mov     [rsp+arg_8], rsi
0x140005cf6  push    rdi
0x140005cf7  sub     rsp, 30h
0x140005cfb  mov     rbx, r8
0x140005cfe  mov     rdi, rdx
0x140005d01  mov     rsi, rcx
0x140005d04  mov     edx, 10h; Length
0x140005d09  lea     r8d, [rdx-0Fh]; Alignment
0x140005d0d  mov     rcx, rbx; Address
0x140005d10  call    cs:__imp_ProbeForRead
0x140005d17  nop     dword ptr [rax+rax+00h]
0x140005d1c  movups  xmm0, xmmword ptr [rbx]
0x140005d1f  movdqu  [rsp+38h+var_18], xmm0
0x140005d25  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x140005d28  lea     edx, [r9+40h]; unsigned __int64
0x140005d2c  mov     r8d, 5441514Dh; unsigned int
0x140005d32  lea     ecx, [rdx+48h]; unsigned __int64
0x140005d35  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140005d3a  test    rax, rax
0x140005d3d  jz      short loc_140005D54
0x140005d3f  lea     r8, [rsp+38h+var_18]; struct BOID *
0x140005d44  mov     rdx, rsi; struct _DEVICE_OBJECT *
0x140005d47  mov     rcx, rax; this
0x140005d4a  call    ??0CTransaction@@QEAA@PEAU_DEVICE_OBJECT@@PEBUBOID@@@Z; CTransaction::CTransaction(_DEVICE_OBJECT *,BOID const *)
0x140005d4f  mov     rbx, rax
0x140005d52  jmp     short loc_140005D56
0x140005d54  xor     ebx, ebx
0x140005d56  lea     rsi, WPP_GLOBAL_Control
0x140005d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d64  cmp     rcx, rsi
0x140005d67  jz      short loc_140005D88
0x140005d69  mov     eax, [rcx+6Ch]
0x140005d6c  test    al, 4
0x140005d6e  jz      short loc_140005D88
0x140005d70  mov     edx, 0C9h
0x140005d75  mov     r9, rbx
0x140005d78  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005d7f  mov     rcx, [rcx+58h]
0x140005d83  call    WPP_SF_q
0x140005d88  test    rbx, rbx
0x140005d8b  jnz     short loc_140005DBC
0x140005d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d94  cmp     rcx, rsi
0x140005d97  jz      short loc_140005DB5
0x140005d99  mov     eax, [rcx+6Ch]
0x140005d9c  test    al, 1
0x140005d9e  jz      short loc_140005DB5
0x140005da0  mov     edx, 0CAh
0x140005da5  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005dac  mov     rcx, [rcx+58h]
0x140005db0  call    WPP_SF_
0x140005db5  mov     eax, 0C000009Ah
0x140005dba  jmp     short loc_140005E04
0x140005dbc  mov     [rdi+18h], rbx
0x140005dc0  mov     rax, [rdi+20h]
0x140005dc4  or      dword ptr [rax+14h], 1
0x140005dc8  xor     eax, eax
0x140005dca  jmp     short loc_140005E04
0x140005dcc  lea     rdx, WPP_GLOBAL_Control
0x140005dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140005dda  cmp     rcx, rdx
0x140005ddd  jz      short loc_140005DFF
0x140005ddf  mov     edx, [rcx+6Ch]
0x140005de2  test    dl, 1
0x140005de5  jz      short loc_140005DFF
0x140005de7  mov     r9d, eax
0x140005dea  mov     edx, 0C8h
0x140005def  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005df6  mov     rcx, [rcx+58h]
0x140005dfa  call    WPP_SF_d
0x140005dff  mov     eax, 0C000000Dh
0x140005e04  mov     rbx, [rsp+38h+arg_0]
0x140005e09  mov     rsi, [rsp+38h+arg_8]
0x140005e0e  add     rsp, 30h
0x140005e12  pop     rdi
0x140005e13  retn
```
