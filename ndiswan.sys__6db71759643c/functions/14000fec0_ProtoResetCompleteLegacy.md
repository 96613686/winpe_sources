# ProtoResetCompleteLegacy

- ea: `0x14000fec0`
- end: `0x14000ff69`
- name: `ProtoResetCompleteLegacy`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x14000fec0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ff1e`
- `ntoskrnl!KeSetEvent` at `0x14000ff1e`

## pseudocode

```c
LONG __fastcall ProtoResetCompleteLegacy(__int64 a1, int a2)
{
  LONG result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, a1);
  }
  *(_DWORD *)(a1 + 160) = a2;
  result = KeSetEvent((PRKEVENT)(a1 + 136), 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000fec0  mov     [rsp+arg_0], rbx
0x14000fec5  mov     [rsp+arg_8], rsi
0x14000feca  push    rdi
0x14000fecb  sub     rsp, 20h
0x14000fecf  mov     edi, edx
0x14000fed1  mov     rbx, rcx
0x14000fed4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fedb  lea     rsi, WPP_GLOBAL_Control
0x14000fee2  cmp     rcx, rsi
0x14000fee5  jz      short loc_14000FF0C
0x14000fee7  mov     eax, [rcx+2Ch]
0x14000feea  test    al, 4
0x14000feec  jz      short loc_14000FF0C
0x14000feee  cmp     byte ptr [rcx+29h], 5
0x14000fef2  jb      short loc_14000FF0C
0x14000fef4  mov     rcx, [rcx+18h]
0x14000fef8  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000feff  mov     edx, 12h
0x14000ff04  mov     r9, rbx
0x14000ff07  call    WPP_SF_q
0x14000ff0c  lea     rcx, [rbx+88h]; Event
0x14000ff13  mov     [rbx+0A0h], edi
0x14000ff19  xor     r8d, r8d; Wait
0x14000ff1c  xor     edx, edx; Increment
0x14000ff1e  call    cs:__imp_KeSetEvent
0x14000ff25  nop     dword ptr [rax+rax+00h]
0x14000ff2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff31  cmp     rcx, rsi
0x14000ff34  jz      short loc_14000FF58
0x14000ff36  mov     eax, [rcx+2Ch]
0x14000ff39  test    al, 4
0x14000ff3b  jz      short loc_14000FF58
0x14000ff3d  cmp     byte ptr [rcx+29h], 5
0x14000ff41  jb      short loc_14000FF58
0x14000ff43  mov     rcx, [rcx+18h]
0x14000ff47  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000ff4e  mov     edx, 13h
0x14000ff53  call    WPP_SF_
0x14000ff58  mov     rbx, [rsp+28h+arg_0]
0x14000ff5d  mov     rsi, [rsp+28h+arg_8]
0x14000ff62  add     rsp, 20h
0x14000ff66  pop     rdi
0x14000ff67  retn
```
