# ProtoUninstall

- ea: `0x14000ebd0`
- end: `0x14000ec40`
- name: `ProtoUninstall`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14000a290`
- `0x14000ebd0`

## pseudocode

```c
__int64 ProtoUninstall()
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ebd0  push    rbx
0x14000ebd2  sub     rsp, 20h
0x14000ebd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ebdd  lea     rbx, WPP_GLOBAL_Control
0x14000ebe4  cmp     rcx, rbx
0x14000ebe7  jz      short loc_14000EC39
0x14000ebe9  mov     eax, [rcx+2Ch]
0x14000ebec  test    al, 4
0x14000ebee  jz      short loc_14000EC0B
0x14000ebf0  cmp     byte ptr [rcx+29h], 5
0x14000ebf4  jb      short loc_14000EC0B
0x14000ebf6  mov     rcx, [rcx+18h]
0x14000ebfa  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000ec01  mov     edx, 21h ; '!'
0x14000ec06  call    WPP_SF_
0x14000ec0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec12  cmp     rcx, rbx
0x14000ec15  jz      short loc_14000EC39
0x14000ec17  mov     eax, [rcx+2Ch]
0x14000ec1a  test    al, 4
0x14000ec1c  jz      short loc_14000EC39
0x14000ec1e  cmp     byte ptr [rcx+29h], 5
0x14000ec22  jb      short loc_14000EC39
0x14000ec24  mov     rcx, [rcx+18h]
0x14000ec28  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000ec2f  mov     edx, 22h ; '"'
0x14000ec34  call    WPP_SF_
0x14000ec39  add     rsp, 20h
0x14000ec3d  pop     rbx
0x14000ec3e  retn
```
