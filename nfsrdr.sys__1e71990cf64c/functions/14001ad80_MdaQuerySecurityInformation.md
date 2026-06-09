# MdaQuerySecurityInformation

- ea: `0x14001ad80`
- end: `0x14001adc9`
- name: `MdaQuerySecurityInformation`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400159cc`
- `0x14001ad80`

## pseudocode

```c
__int64 __fastcall MdaQuerySecurityInformation(__int64 a1)
{
  *(_QWORD *)(a1 + 184) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  return 3221225488LL;
}

```

## disassembly

```asm
0x14001ad80  sub     rsp, 28h
0x14001ad84  mov     qword ptr [rcx+0B8h], 0
0x14001ad8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad96  lea     rax, WPP_GLOBAL_Control
0x14001ad9d  cmp     rcx, rax
0x14001ada0  jz      short loc_14001ADBE
0x14001ada2  mov     eax, [rcx+2Ch]
0x14001ada5  test    al, 8
0x14001ada7  jz      short loc_14001ADBE
0x14001ada9  mov     rcx, [rcx+18h]
0x14001adad  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001adb4  mov     edx, 3Fh ; '?'
0x14001adb9  call    WPP_SF_
0x14001adbe  mov     eax, 0C0000010h
0x14001adc3  add     rsp, 28h
0x14001adc7  retn
```
