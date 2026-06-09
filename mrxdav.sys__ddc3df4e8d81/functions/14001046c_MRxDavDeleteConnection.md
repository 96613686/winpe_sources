# MRxDavDeleteConnection

- ea: `0x14001046c`
- end: `0x14001054b`
- name: `MRxDavDeleteConnection`
- size: `223`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f120`

## callees

- `0x140001838`
- `0x14001046c`

## import_xrefs

- `rdbss!RxFinalizeConnection` at `0x140010526`
- `rdbss!RxFinalizeConnection` at `0x140010526`

## pseudocode

```c
NTSTATUS __fastcall MRxDavDeleteConnection(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // ebx
  __int64 v4; // rdi
  struct _NET_ROOT *v5; // r14
  __int64 v6; // rsi
  LOGICAL v7; // r8d

  v1 = *(_QWORD *)(a1 + 72);
  if ( !v1 )
    return -1073741808;
  if ( *(_DWORD *)(a1 + 568) < 4u )
    return -1073741789;
  v3 = **(_DWORD **)(a1 + 552);
  if ( v3 > 2 )
    return -1073741811;
  v4 = *(_QWORD *)(v1 + 40);
  v5 = *(struct _NET_ROOT **)(v4 + 32);
  if ( v4 && (v6 = *(_QWORD *)(v4 + 40)) != 0 && v3 == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 3), 55, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v4, v6, 2);
    v7 = 1;
    *(_DWORD *)(v6 + 108) = 1;
  }
  else
  {
    v7 = 1;
  }
  if ( v3 != 2 )
    v7 = (unsigned __int8)-(v3 != 0);
  return RxFinalizeConnection(v5, (PV_NET_ROOT)v4, v7);
}

```

## disassembly

```asm
0x14001046c  push    rbx
0x14001046e  push    rsi
0x14001046f  push    rdi
0x140010470  push    r14
0x140010472  sub     rsp, 38h
0x140010476  mov     rdi, [rcx+48h]
0x14001047a  mov     rbx, [rcx+228h]
0x140010481  mov     eax, [rcx+238h]
0x140010487  test    rdi, rdi
0x14001048a  jz      loc_14001053B
0x140010490  cmp     eax, 4
0x140010493  jnb     short loc_14001049F
0x140010495  mov     eax, 0C0000023h
0x14001049a  jmp     loc_140010540
0x14001049f  mov     ebx, [rbx]
0x1400104a1  cmp     ebx, 2
0x1400104a4  ja      loc_140010534
0x1400104aa  mov     rdi, [rdi+28h]
0x1400104ae  mov     r14, [rdi+20h]
0x1400104b2  test    rdi, rdi
0x1400104b5  jz      short loc_14001050C
0x1400104b7  mov     rsi, [rdi+28h]
0x1400104bb  test    rsi, rsi
0x1400104be  jz      short loc_14001050C
0x1400104c0  cmp     ebx, 2
0x1400104c3  jnz     short loc_14001050C
0x1400104c5  lea     rax, WPP_GLOBAL_Control
0x1400104cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104d3  cmp     rcx, rax
0x1400104d6  jz      short loc_140010500
0x1400104d8  test    dword ptr [rcx+2Ch], 4000h
0x1400104df  jz      short loc_140010500
0x1400104e1  lea     edx, [rbx+35h]
0x1400104e4  mov     [rsp+58h+var_30], ebx
0x1400104e8  mov     [rsp+58h+var_38], rsi
0x1400104ed  mov     r9, rdi
0x1400104f0  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x1400104f7  mov     rcx, [rcx+18h]
0x1400104fb  call    WPP_SF_qqD
0x140010500  mov     r8d, 1
0x140010506  mov     [rsi+6Ch], r8d
0x14001050a  jmp     short loc_140010512
0x14001050c  mov     r8d, 1
0x140010512  cmp     ebx, 2
0x140010515  jz      short loc_140010520
0x140010517  neg     ebx
0x140010519  sbb     r8d, r8d
0x14001051c  movzx   r8d, r8b; ForceFilesClosed
0x140010520  mov     rdx, rdi; VNetRoot
0x140010523  mov     rcx, r14; NetRoot
0x140010526  call    cs:__imp_RxFinalizeConnection
0x14001052d  nop     dword ptr [rax+rax+00h]
0x140010532  jmp     short loc_140010540
0x140010534  mov     eax, 0C000000Dh
0x140010539  jmp     short loc_140010540
0x14001053b  mov     eax, 0C0000010h
0x140010540  add     rsp, 38h
0x140010544  pop     r14
0x140010546  pop     rdi
0x140010547  pop     rsi
0x140010548  pop     rbx
0x140010549  retn
0x140028e76  push    rbp
0x140028e78  sub     rsp, 30h
0x140028e7c  mov     rbp, rdx
0x140028e7f  add     rsp, 30h
0x140028e83  pop     rbp
0x140028e84  retn
```
