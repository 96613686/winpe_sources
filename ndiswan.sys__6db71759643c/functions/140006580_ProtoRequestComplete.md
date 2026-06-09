# ProtoRequestComplete

- ea: `0x140006580`
- end: `0x140006639`
- name: `ProtoRequestComplete`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006580`
- `0x14000a290`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400065ca`
- `ntoskrnl!KeSetEvent` at `0x1400065ca`

## pseudocode

```c
LONG __fastcall ProtoRequestComplete(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rbx
  bool v5; // zf
  LONG result; // eax

  v4 = a2 - 48;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    result = WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, v4);
  }
  v5 = *(_DWORD *)(v4 + 20) == 0;
  *(_DWORD *)(v4 + 296) = a3;
  if ( v5 )
    result = KeSetEvent((PRKEVENT)(v4 + 304), 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140006580  mov     [rsp+arg_0], rbx
0x140006585  mov     [rsp+arg_8], rbp
0x14000658a  push    rdi
0x14000658b  sub     rsp, 20h
0x14000658f  mov     edi, r8d
0x140006592  lea     rbx, [rdx-30h]
0x140006596  mov     rcx, cs:WPP_GLOBAL_Control
0x14000659d  lea     rbp, WPP_GLOBAL_Control
0x1400065a4  cmp     rcx, rbp
0x1400065a7  jz      short loc_1400065B2
0x1400065a9  test    dword ptr [rcx+2Ch], 80000h
0x1400065b0  jnz     short loc_1400065FC
0x1400065b2  cmp     dword ptr [rbx+14h], 0
0x1400065b6  mov     [rbx+128h], edi
0x1400065bc  jnz     short loc_1400065D6
0x1400065be  lea     rcx, [rbx+130h]; Event
0x1400065c5  xor     r8d, r8d; Wait
0x1400065c8  xor     edx, edx; Increment
0x1400065ca  call    cs:__imp_KeSetEvent
0x1400065d1  nop     dword ptr [rax+rax+00h]
0x1400065d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065dd  cmp     rcx, rbp
0x1400065e0  jz      short loc_1400065EB
0x1400065e2  test    dword ptr [rcx+2Ch], 80000h
0x1400065e9  jnz     short loc_14000661C
0x1400065eb  mov     rbx, [rsp+28h+arg_0]
0x1400065f0  mov     rbp, [rsp+28h+arg_8]
0x1400065f5  add     rsp, 20h
0x1400065f9  pop     rdi
0x1400065fa  retn
0x1400065fc  cmp     byte ptr [rcx+29h], 6
0x140006600  jb      short loc_1400065B2
0x140006602  mov     rcx, [rcx+18h]
0x140006606  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000660d  mov     edx, 15h
0x140006612  mov     r9, rbx
0x140006615  call    WPP_SF_q
0x14000661a  jmp     short loc_1400065B2
0x14000661c  cmp     byte ptr [rcx+29h], 6
0x140006620  jb      short loc_1400065EB
0x140006622  mov     rcx, [rcx+18h]
0x140006626  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000662d  mov     edx, 16h
0x140006632  call    WPP_SF_
0x140006637  jmp     short loc_1400065EB
```
