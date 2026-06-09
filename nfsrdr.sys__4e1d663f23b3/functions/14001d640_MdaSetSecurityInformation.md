# MdaSetSecurityInformation

- ea: `0x14001d640`
- end: `0x14001d6a9`
- name: `MdaSetSecurityInformation`
- size: `105`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400159cc`
- `0x14001d640`

## pseudocode

```c
__int64 MdaSetSecurityInformation()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  }
  return 3221225488LL;
}

```

## disassembly

```asm
0x14001d640  push    rbx
0x14001d642  sub     rsp, 20h
0x14001d646  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d64d  lea     rbx, WPP_GLOBAL_Control
0x14001d654  cmp     rcx, rbx
0x14001d657  jz      short loc_14001D69D
0x14001d659  mov     eax, [rcx+2Ch]
0x14001d65c  test    al, 8
0x14001d65e  jz      short loc_14001D675
0x14001d660  mov     rcx, [rcx+18h]
0x14001d664  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001d66b  mov     edx, 40h ; '@'
0x14001d670  call    WPP_SF_
0x14001d675  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d67c  cmp     rcx, rbx
0x14001d67f  jz      short loc_14001D69D
0x14001d681  mov     eax, [rcx+2Ch]
0x14001d684  test    al, 8
0x14001d686  jz      short loc_14001D69D
0x14001d688  mov     rcx, [rcx+18h]
0x14001d68c  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001d693  mov     edx, 41h ; 'A'
0x14001d698  call    WPP_SF_
0x14001d69d  mov     eax, 0C0000010h
0x14001d6a2  add     rsp, 20h
0x14001d6a6  pop     rbx
0x14001d6a7  retn
```
