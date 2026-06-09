# ProtoRequestCompleteLegacy

- ea: `0x14000fe00`
- end: `0x14000feba`
- name: `ProtoRequestCompleteLegacy`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x14000fe00`
- `0x140010a1c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000fe73`
- `ntoskrnl!KeSetEvent` at `0x14000fe73`

## pseudocode

```c
void __fastcall ProtoRequestCompleteLegacy(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rbx
  bool v6; // zf

  v4 = a2 - 48;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, v4);
  }
  v6 = *(_DWORD *)(v4 + 20) == 0;
  *(_DWORD *)(v4 + 232) = a3;
  if ( v6 )
    KeSetEvent((PRKEVENT)(v4 + 240), 0, 0);
  else
    NdisWanTapiRequestComplete(a1, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
}

```

## disassembly

```asm
0x14000fe00  push    rbx
0x14000fe02  push    rsi
0x14000fe03  push    rdi
0x14000fe04  push    r14
0x14000fe06  sub     rsp, 28h
0x14000fe0a  mov     edi, r8d
0x14000fe0d  lea     rbx, [rdx-30h]
0x14000fe11  mov     rsi, rcx
0x14000fe14  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe1b  lea     r14, WPP_GLOBAL_Control
0x14000fe22  cmp     rcx, r14
0x14000fe25  jz      short loc_14000FE4E
0x14000fe27  test    dword ptr [rcx+2Ch], 80000h
0x14000fe2e  jz      short loc_14000FE4E
0x14000fe30  cmp     byte ptr [rcx+29h], 6
0x14000fe34  jb      short loc_14000FE4E
0x14000fe36  mov     rcx, [rcx+18h]
0x14000fe3a  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fe41  mov     edx, 1Fh
0x14000fe46  mov     r9, rbx
0x14000fe49  call    WPP_SF_q
0x14000fe4e  cmp     dword ptr [rbx+14h], 0
0x14000fe52  mov     [rbx+0E8h], edi
0x14000fe58  jz      short loc_14000FE67
0x14000fe5a  mov     rdx, rbx
0x14000fe5d  mov     rcx, rsi
0x14000fe60  call    NdisWanTapiRequestComplete
0x14000fe65  jmp     short loc_14000FE7F
0x14000fe67  lea     rcx, [rbx+0F0h]; Event
0x14000fe6e  xor     r8d, r8d; Wait
0x14000fe71  xor     edx, edx; Increment
0x14000fe73  call    cs:__imp_KeSetEvent
0x14000fe7a  nop     dword ptr [rax+rax+00h]
0x14000fe7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe86  cmp     rcx, r14
0x14000fe89  jz      short loc_14000FEAF
0x14000fe8b  test    dword ptr [rcx+2Ch], 80000h
0x14000fe92  jz      short loc_14000FEAF
0x14000fe94  cmp     byte ptr [rcx+29h], 6
0x14000fe98  jb      short loc_14000FEAF
0x14000fe9a  mov     rcx, [rcx+18h]
0x14000fe9e  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fea5  mov     edx, 20h ; ' '
0x14000feaa  call    WPP_SF_
0x14000feaf  add     rsp, 28h
0x14000feb3  pop     r14
0x14000feb5  pop     rdi
0x14000feb6  pop     rsi
0x14000feb7  pop     rbx
0x14000feb8  retn
```
