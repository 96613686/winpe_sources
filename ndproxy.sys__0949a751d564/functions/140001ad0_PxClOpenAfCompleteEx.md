# PxClOpenAfCompleteEx

- ea: `0x140001ad0`
- end: `0x140001b4c`
- name: `PxClOpenAfCompleteEx`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001ad0`
- `0x140001c0c`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140001b2f`
- `NDIS!NdisSetEvent` at `0x140001b2f`

## pseudocode

```c
void __fastcall PxClOpenAfCompleteEx(__int64 a1, __int64 a2, int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, a1, a3);
  *(_QWORD *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 176) = a3;
  NdisSetEvent((PNDIS_EVENT)(a1 + 152));
}

```

## disassembly

```asm
0x140001ad0  mov     [rsp+arg_0], rbx
0x140001ad5  mov     [rsp+arg_8], rsi
0x140001ada  push    rdi
0x140001adb  sub     rsp, 30h
0x140001adf  mov     edi, r8d
0x140001ae2  mov     rsi, rdx
0x140001ae5  mov     rbx, rcx
0x140001ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aef  lea     rax, WPP_GLOBAL_Control
0x140001af6  cmp     rcx, rax
0x140001af9  jz      short loc_140001B1E
0x140001afb  cmp     byte ptr [rcx+29h], 5
0x140001aff  jb      short loc_140001B1E
0x140001b01  mov     rcx, [rcx+18h]
0x140001b05  mov     edx, 15h
0x140001b0a  mov     [rsp+38h+var_18], r8d
0x140001b0f  mov     r9, rbx
0x140001b12  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x140001b19  call    WPP_SF_qD
0x140001b1e  lea     rcx, [rbx+98h]; Event
0x140001b25  mov     [rbx+18h], rsi
0x140001b29  mov     [rbx+0B0h], edi
0x140001b2f  call    cs:__imp_NdisSetEvent
0x140001b36  nop     dword ptr [rax+rax+00h]
0x140001b3b  mov     rbx, [rsp+38h+arg_0]
0x140001b40  mov     rsi, [rsp+38h+arg_8]
0x140001b45  add     rsp, 30h
0x140001b49  pop     rdi
0x140001b4a  retn
```
