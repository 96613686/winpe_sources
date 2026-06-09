# CmIncomingCallComplete

- ea: `0x140025c00`
- end: `0x140025c74`
- name: `CmIncomingCallComplete`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x140025c00`

## pseudocode

```c
__int64 CmIncomingCallComplete()
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025c00  push    rdi
0x140025c02  sub     rsp, 20h
0x140025c06  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c0d  lea     rdi, WPP_GLOBAL_Control
0x140025c14  cmp     rcx, rdi
0x140025c17  jz      short loc_140025C6D
0x140025c19  test    dword ptr [rcx+2Ch], 10000h
0x140025c20  jz      short loc_140025C3D
0x140025c22  cmp     byte ptr [rcx+29h], 5
0x140025c26  jb      short loc_140025C3D
0x140025c28  mov     rcx, [rcx+18h]
0x140025c2c  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025c33  mov     edx, 22h ; '"'
0x140025c38  call    WPP_SF_
0x140025c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c44  cmp     rcx, rdi
0x140025c47  jz      short loc_140025C6D
0x140025c49  test    dword ptr [rcx+2Ch], 10000h
0x140025c50  jz      short loc_140025C6D
0x140025c52  cmp     byte ptr [rcx+29h], 5
0x140025c56  jb      short loc_140025C6D
0x140025c58  mov     rcx, [rcx+18h]
0x140025c5c  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025c63  mov     edx, 23h ; '#'
0x140025c68  call    WPP_SF_
0x140025c6d  add     rsp, 20h
0x140025c71  pop     rdi
0x140025c72  retn
```
