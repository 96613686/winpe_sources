# ProtoOpenAdapterCompleteLegacy

- ea: `0x14000f910`
- end: `0x14000f9b9`
- name: `ProtoOpenAdapterCompleteLegacy`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x14000f910`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000f96e`
- `ntoskrnl!KeSetEvent` at `0x14000f96e`

## pseudocode

```c
LONG __fastcall ProtoOpenAdapterCompleteLegacy(__int64 a1, int a2)
{
  LONG result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, a1);
  }
  *(_DWORD *)(a1 + 160) = a2;
  result = KeSetEvent((PRKEVENT)(a1 + 136), 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000f910  mov     [rsp+arg_0], rbx
0x14000f915  mov     [rsp+arg_8], rsi
0x14000f91a  push    rdi
0x14000f91b  sub     rsp, 20h
0x14000f91f  mov     edi, edx
0x14000f921  mov     rbx, rcx
0x14000f924  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f92b  lea     rsi, WPP_GLOBAL_Control
0x14000f932  cmp     rcx, rsi
0x14000f935  jz      short loc_14000F95C
0x14000f937  mov     eax, [rcx+2Ch]
0x14000f93a  test    al, 4
0x14000f93c  jz      short loc_14000F95C
0x14000f93e  cmp     byte ptr [rcx+29h], 5
0x14000f942  jb      short loc_14000F95C
0x14000f944  mov     rcx, [rcx+18h]
0x14000f948  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f94f  mov     edx, 0Eh
0x14000f954  mov     r9, rbx
0x14000f957  call    WPP_SF_q
0x14000f95c  lea     rcx, [rbx+88h]; Event
0x14000f963  mov     [rbx+0A0h], edi
0x14000f969  xor     r8d, r8d; Wait
0x14000f96c  xor     edx, edx; Increment
0x14000f96e  call    cs:__imp_KeSetEvent
0x14000f975  nop     dword ptr [rax+rax+00h]
0x14000f97a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f981  cmp     rcx, rsi
0x14000f984  jz      short loc_14000F9A8
0x14000f986  mov     eax, [rcx+2Ch]
0x14000f989  test    al, 4
0x14000f98b  jz      short loc_14000F9A8
0x14000f98d  cmp     byte ptr [rcx+29h], 5
0x14000f991  jb      short loc_14000F9A8
0x14000f993  mov     rcx, [rcx+18h]
0x14000f997  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f99e  mov     edx, 0Fh
0x14000f9a3  call    WPP_SF_
0x14000f9a8  mov     rbx, [rsp+28h+arg_0]
0x14000f9ad  mov     rsi, [rsp+28h+arg_8]
0x14000f9b2  add     rsp, 20h
0x14000f9b6  pop     rdi
0x14000f9b7  retn
```
