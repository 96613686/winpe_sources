# ProtoOpenAdapterComplete

- ea: `0x140038030`
- end: `0x1400380dd`
- name: `ProtoOpenAdapterComplete`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x140038030`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140038070`
- `ntoskrnl!KeSetEvent` at `0x140038070`

## pseudocode

```c
LONG __fastcall ProtoOpenAdapterComplete(__int64 a1, int a2)
{
  LONG result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, a1);
  }
  *(_DWORD *)(a1 + 160) = a2;
  result = KeSetEvent((PRKEVENT)(a1 + 136), 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140038030  mov     [rsp+arg_0], rbx
0x140038035  mov     [rsp+arg_8], rsi
0x14003803a  push    rdi
0x14003803b  sub     rsp, 20h
0x14003803f  mov     edi, edx
0x140038041  mov     rbx, rcx
0x140038044  mov     rcx, cs:WPP_GLOBAL_Control
0x14003804b  lea     rsi, WPP_GLOBAL_Control
0x140038052  cmp     rcx, rsi
0x140038055  jz      short loc_14003805E
0x140038057  mov     eax, [rcx+2Ch]
0x14003805a  test    al, 4
0x14003805c  jnz     short loc_1400380A0
0x14003805e  lea     rcx, [rbx+88h]; Event
0x140038065  mov     [rbx+0A0h], edi
0x14003806b  xor     r8d, r8d; Wait
0x14003806e  xor     edx, edx; Increment
0x140038070  call    cs:__imp_KeSetEvent
0x140038077  nop     dword ptr [rax+rax+00h]
0x14003807c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038083  cmp     rcx, rsi
0x140038086  jz      short loc_14003808F
0x140038088  mov     eax, [rcx+2Ch]
0x14003808b  test    al, 4
0x14003808d  jnz     short loc_1400380C0
0x14003808f  mov     rbx, [rsp+28h+arg_0]
0x140038094  mov     rsi, [rsp+28h+arg_8]
0x140038099  add     rsp, 20h
0x14003809d  pop     rdi
0x14003809e  retn
0x1400380a0  cmp     byte ptr [rcx+29h], 5
0x1400380a4  jb      short loc_14003805E
0x1400380a6  mov     rcx, [rcx+18h]
0x1400380aa  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x1400380b1  mov     edx, 0Eh
0x1400380b6  mov     r9, rbx
0x1400380b9  call    WPP_SF_q
0x1400380be  jmp     short loc_14003805E
0x1400380c0  cmp     byte ptr [rcx+29h], 5
0x1400380c4  jb      short loc_14003808F
0x1400380c6  mov     rcx, [rcx+18h]
0x1400380ca  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x1400380d1  mov     edx, 0Fh
0x1400380d6  call    WPP_SF_
0x1400380db  jmp     short loc_14003808F
```
