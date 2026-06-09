# ProtoReceiveCompleteLegacy

- ea: `0x14000fd80`
- end: `0x14000fdf3`
- name: `ProtoReceiveCompleteLegacy`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a648`
- `0x14000fd80`

## pseudocode

```c
__int64 __fastcall ProtoReceiveCompleteLegacy(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000fd80  push    rbx
0x14000fd82  sub     rsp, 20h
0x14000fd86  mov     r9, rcx
0x14000fd89  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd90  lea     rbx, WPP_GLOBAL_Control
0x14000fd97  cmp     rcx, rbx
0x14000fd9a  jz      short loc_14000FDEC
0x14000fd9c  mov     eax, [rcx+2Ch]
0x14000fd9f  test    al, 10h
0x14000fda1  jz      short loc_14000FDBE
0x14000fda3  cmp     byte ptr [rcx+29h], 5
0x14000fda7  jb      short loc_14000FDBE
0x14000fda9  mov     rcx, [rcx+18h]
0x14000fdad  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fdb4  mov     edx, 14h
0x14000fdb9  call    WPP_SF_q
0x14000fdbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdc5  cmp     rcx, rbx
0x14000fdc8  jz      short loc_14000FDEC
0x14000fdca  mov     eax, [rcx+2Ch]
0x14000fdcd  test    al, 10h
0x14000fdcf  jz      short loc_14000FDEC
0x14000fdd1  cmp     byte ptr [rcx+29h], 5
0x14000fdd5  jb      short loc_14000FDEC
0x14000fdd7  mov     rcx, [rcx+18h]
0x14000fddb  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fde2  mov     edx, 15h
0x14000fde7  call    WPP_SF_
0x14000fdec  add     rsp, 20h
0x14000fdf0  pop     rbx
0x14000fdf1  retn
```
