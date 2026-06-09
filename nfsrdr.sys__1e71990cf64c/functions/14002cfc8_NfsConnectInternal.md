# NfsConnectInternal

- ea: `0x14002cfc8`
- end: `0x14002d173`
- name: `NfsConnectInternal`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140001760`
- `0x14000b900`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x14002cfc8`
- `0x14002d17c`
- `0x14003aba0`

## import_xrefs

- `rpcxdr!OncRpcConnectionOpen` at `0x14002d0a0`
- `rpcxdr!OncRpcConnectionOpen` at `0x14002d0a0`

## pseudocode

```c
__int64 __fastcall NfsConnectInternal(__int64 a1)
{
  unsigned int v3; // ebx
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // [rsp+30h] [rbp-30h] BYREF
  __int128 v7; // [rsp+38h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-18h]

  v8 = 0;
  v7 = 0;
  if ( *(_DWORD *)(a1 + 8) != 6 )
    return 0;
  v3 = 0;
  if ( *(_WORD *)(a1 + 44) == 2 )
  {
    v6 = 2;
    *(_QWORD *)&v7 = 0;
  }
  else
  {
    v6 = 23;
    v7 = 0;
    v8 = 0;
  }
  v4 = a1 + 32;
  if ( !*(_QWORD *)(a1 + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, 6);
    v5 = HIDWORD(StartContext[1].DispatcherContext.pTearDownEvent) >> 10;
    LOBYTE(v5) = (HIDWORD(StartContext[1].DispatcherContext.pTearDownEvent) & 0x400) != 0;
    v3 = ((__int64 (__fastcall *)(__int64 *, __int64, __int64, _QWORD, _QWORD, __int64))OncRpcConnectionOpen)(
           &v6,
           v5,
           a1 + 44,
           0,
           0,
           v4);
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v3);
      if ( v3 == -1073741302 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids);
        v3 = -1073741670;
      }
      NfsDisconnectLockHeldExclusive(a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14002cfc8  mov     [rsp-28h+arg_8], rbx
0x14002cfcd  mov     [rsp-28h+arg_10], rsi
0x14002cfd2  push    rbp
0x14002cfd3  push    rdi
0x14002cfd4  push    r12
0x14002cfd6  push    r13
0x14002cfd8  push    r14
0x14002cfda  mov     rbp, rsp
0x14002cfdd  sub     rsp, 60h
0x14002cfe1  mov     rax, cs:__security_cookie
0x14002cfe8  xor     rax, rsp
0x14002cfeb  mov     [rbp+var_10], rax
0x14002cfef  mov     r9d, 6
0x14002cff5  mov     [rbp+var_18], 0
0x14002cffc  xorps   xmm0, xmm0
0x14002cfff  mov     rdi, rcx
0x14002d002  movdqu  [rbp+var_28], xmm0
0x14002d007  cmp     [rcx+8], r9d
0x14002d00b  jz      short loc_14002D014
0x14002d00d  xor     eax, eax
0x14002d00f  jmp     loc_14002D14D
0x14002d014  xor     ebx, ebx
0x14002d016  lea     r12d, [rbx+2]
0x14002d01a  cmp     [rcx+2Ch], r12w
0x14002d01f  jnz     short loc_14002D02D
0x14002d021  xor     eax, eax
0x14002d023  mov     [rbp+var_30], r12
0x14002d027  mov     qword ptr [rbp+var_28], rax
0x14002d02b  jmp     short loc_14002D03C
0x14002d02d  mov     [rbp+var_30], 17h
0x14002d035  movups  [rbp+var_28], xmm0
0x14002d039  mov     [rbp+var_18], ebx
0x14002d03c  lea     rsi, [rcx+20h]
0x14002d040  cmp     [rsi], rbx
0x14002d043  jnz     loc_14002D14B
0x14002d049  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d050  lea     r13, WPP_GLOBAL_Control
0x14002d057  cmp     rcx, r13
0x14002d05a  jz      short loc_14002D078
0x14002d05c  mov     eax, [rcx+2Ch]
0x14002d05f  test    al, 20h
0x14002d061  jz      short loc_14002D078
0x14002d063  mov     rcx, [rcx+18h]
0x14002d067  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d06e  mov     edx, 1Dh
0x14002d073  call    WPP_SF_d
0x14002d078  mov     rax, cs:StartContext
0x14002d07f  lea     r8, [rdi+2Ch]
0x14002d083  mov     [rsp+60h+var_38], rsi
0x14002d088  lea     rcx, [rbp+var_30]
0x14002d08c  xor     r9d, r9d
0x14002d08f  mov     [rsp+60h+var_40], rbx
0x14002d094  mov     edx, [rax+90Ch]
0x14002d09a  shr     edx, 0Ah
0x14002d09d  and     dl, 1
0x14002d0a0  call    cs:__imp_OncRpcConnectionOpen
0x14002d0a7  nop     dword ptr [rax+rax+00h]
0x14002d0ac  mov     ebx, eax
0x14002d0ae  test    eax, eax
0x14002d0b0  jns     loc_14002D14B
0x14002d0b6  mov     rax, cs:WPP_GLOBAL_Control
0x14002d0bd  cmp     rax, r13
0x14002d0c0  jz      short loc_14002D0E2
0x14002d0c2  mov     ecx, [rax+2Ch]
0x14002d0c5  test    r12b, cl
0x14002d0c8  jz      short loc_14002D0E2
0x14002d0ca  mov     rcx, [rax+18h]
0x14002d0ce  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d0d5  mov     edx, 1Eh
0x14002d0da  mov     r9d, ebx
0x14002d0dd  call    WPP_SF_d
0x14002d0e2  cmp     ebx, 0C000020Ah
0x14002d0e8  jnz     short loc_14002D117
0x14002d0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0f1  cmp     rcx, r13
0x14002d0f4  jz      short loc_14002D112
0x14002d0f6  mov     eax, [rcx+2Ch]
0x14002d0f9  test    al, 1
0x14002d0fb  jz      short loc_14002D112
0x14002d0fd  mov     rcx, [rcx+18h]
0x14002d101  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d108  mov     edx, 1Fh
0x14002d10d  call    WPP_SF_
0x14002d112  mov     ebx, 0C000009Ah
0x14002d117  mov     rcx, rdi
0x14002d11a  call    NfsDisconnectLockHeldExclusive
0x14002d11f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d126  cmp     rcx, r13
0x14002d129  jz      short loc_14002D14B
0x14002d12b  mov     eax, [rcx+2Ch]
0x14002d12e  test    r12b, al
0x14002d131  jz      short loc_14002D14B
0x14002d133  mov     rcx, [rcx+18h]
0x14002d137  lea     r8, WPP_3762e2d130df33c3d675733e5b9743e8_Traceguids
0x14002d13e  mov     edx, 20h ; ' '
0x14002d143  mov     r9d, ebx
0x14002d146  call    WPP_SF_d
0x14002d14b  mov     eax, ebx
0x14002d14d  mov     rcx, [rbp+var_10]
0x14002d151  xor     rcx, rsp; StackCookie
0x14002d154  call    __security_check_cookie
0x14002d159  lea     r11, [rsp+60h+var_s0]
0x14002d15e  mov     rbx, [r11+38h]
0x14002d162  mov     rsi, [r11+40h]
0x14002d166  mov     rsp, r11
0x14002d169  pop     r14
0x14002d16b  pop     r13
0x14002d16d  pop     r12
0x14002d16f  pop     rdi
0x14002d170  pop     rbp
0x14002d171  retn
```
