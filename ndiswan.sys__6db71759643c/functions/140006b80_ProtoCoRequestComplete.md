# ProtoCoRequestComplete

- ea: `0x140006b80`
- end: `0x140006c30`
- name: `ProtoCoRequestComplete`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006b80`
- `0x14000a290`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140006bc6`
- `ntoskrnl!KeSetEvent` at `0x140006bc6`

## pseudocode

```c
LONG __fastcall ProtoCoRequestComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4, LONG a5)
{
  __int64 v5; // rbx
  bool v6; // zf
  LONG result; // eax

  v5 = a4 - 48;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, a4 - 48);
  }
  v6 = *(_DWORD *)(v5 + 20) == 0;
  result = a5;
  *(_DWORD *)(v5 + 296) = a5;
  if ( v6 )
    result = KeSetEvent((PRKEVENT)(v5 + 304), 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140006b80  mov     [rsp+arg_0], rbx
0x140006b85  push    rsi
0x140006b86  sub     rsp, 20h
0x140006b8a  lea     rbx, [r9-30h]
0x140006b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b95  lea     rsi, WPP_GLOBAL_Control
0x140006b9c  cmp     rcx, rsi
0x140006b9f  jz      short loc_140006BAA
0x140006ba1  test    dword ptr [rcx+2Ch], 80000h
0x140006ba8  jnz     short loc_140006BF3
0x140006baa  cmp     dword ptr [rbx+14h], 0
0x140006bae  mov     eax, [rsp+28h+arg_20]
0x140006bb2  mov     [rbx+128h], eax
0x140006bb8  jnz     short loc_140006BD2
0x140006bba  lea     rcx, [rbx+130h]; Event
0x140006bc1  xor     r8d, r8d; Wait
0x140006bc4  xor     edx, edx; Increment
0x140006bc6  call    cs:__imp_KeSetEvent
0x140006bcd  nop     dword ptr [rax+rax+00h]
0x140006bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140006bd9  cmp     rcx, rsi
0x140006bdc  jz      short loc_140006BE7
0x140006bde  test    dword ptr [rcx+2Ch], 80000h
0x140006be5  jnz     short loc_140006C13
0x140006be7  mov     rbx, [rsp+28h+arg_0]
0x140006bec  add     rsp, 20h
0x140006bf0  pop     rsi
0x140006bf1  retn
0x140006bf3  cmp     byte ptr [rcx+29h], 5
0x140006bf7  jb      short loc_140006BAA
0x140006bf9  mov     rcx, [rcx+18h]
0x140006bfd  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140006c04  mov     edx, 37h ; '7'
0x140006c09  mov     r9, rbx
0x140006c0c  call    WPP_SF_q
0x140006c11  jmp     short loc_140006BAA
0x140006c13  cmp     byte ptr [rcx+29h], 5
0x140006c17  jb      short loc_140006BE7
0x140006c19  mov     rcx, [rcx+18h]
0x140006c1d  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140006c24  mov     edx, 38h ; '8'
0x140006c29  call    WPP_SF_
0x140006c2e  jmp     short loc_140006BE7
```
