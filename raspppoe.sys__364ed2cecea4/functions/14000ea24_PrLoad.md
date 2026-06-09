# PrLoad

- ea: `0x14000ea24`
- end: `0x14000ead2`
- name: `PrLoad`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004100`
- `0x14000ef78`

## callees

- `0x14000110c`
- `0x14000ea24`

## pseudocode

```c
__int64 PrLoad()
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      result = WPP_SF_(
                 (__int64)WPP_GLOBAL_Control->AttachedDevice,
                 0xCu,
                 (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  if ( gl_fProtocolUnloaded )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        result = WPP_SF_(
                   (__int64)WPP_GLOBAL_Control->AttachedDevice,
                   0xDu,
                   (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
    }
    gl_fProtocolUnloaded = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      return WPP_SF_(
               (__int64)WPP_GLOBAL_Control->AttachedDevice,
               0xEu,
               (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000ea24  push    rsi
0x14000ea26  sub     rsp, 20h
0x14000ea2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea31  lea     rsi, WPP_GLOBAL_Control
0x14000ea38  cmp     rcx, rsi
0x14000ea3b  jz      short loc_14000EA5F
0x14000ea3d  mov     eax, [rcx+2Ch]
0x14000ea40  test    al, 4
0x14000ea42  jz      short loc_14000EA5F
0x14000ea44  cmp     byte ptr [rcx+29h], 3
0x14000ea48  jb      short loc_14000EA5F
0x14000ea4a  mov     rcx, [rcx+18h]
0x14000ea4e  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ea55  mov     edx, 0Ch
0x14000ea5a  call    WPP_SF_
0x14000ea5f  cmp     cs:gl_fProtocolUnloaded, 0
0x14000ea66  jz      short loc_14000EA9D
0x14000ea68  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea6f  cmp     rcx, rsi
0x14000ea72  jz      short loc_14000EA96
0x14000ea74  mov     eax, [rcx+2Ch]
0x14000ea77  test    al, 4
0x14000ea79  jz      short loc_14000EA96
0x14000ea7b  cmp     byte ptr [rcx+29h], 3
0x14000ea7f  jb      short loc_14000EA96
0x14000ea81  mov     rcx, [rcx+18h]
0x14000ea85  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000ea8c  mov     edx, 0Dh
0x14000ea91  call    WPP_SF_
0x14000ea96  mov     cs:gl_fProtocolUnloaded, 0
0x14000ea9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eaa4  cmp     rcx, rsi
0x14000eaa7  jz      short loc_14000EACB
0x14000eaa9  mov     eax, [rcx+2Ch]
0x14000eaac  test    al, 4
0x14000eaae  jz      short loc_14000EACB
0x14000eab0  cmp     byte ptr [rcx+29h], 3
0x14000eab4  jb      short loc_14000EACB
0x14000eab6  mov     rcx, [rcx+18h]
0x14000eaba  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000eac1  mov     edx, 0Eh
0x14000eac6  call    WPP_SF_
0x14000eacb  add     rsp, 20h
0x14000eacf  pop     rsi
0x14000ead0  retn
```
