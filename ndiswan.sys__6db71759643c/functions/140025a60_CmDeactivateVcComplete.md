# CmDeactivateVcComplete

- ea: `0x140025a60`
- end: `0x140025ad4`
- name: `CmDeactivateVcComplete`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x140025a60`

## pseudocode

```c
__int64 CmDeactivateVcComplete()
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025a60  push    rbx
0x140025a62  sub     rsp, 20h
0x140025a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a6d  lea     rbx, WPP_GLOBAL_Control
0x140025a74  cmp     rcx, rbx
0x140025a77  jz      short loc_140025ACD
0x140025a79  test    dword ptr [rcx+2Ch], 10000h
0x140025a80  jz      short loc_140025A9D
0x140025a82  cmp     byte ptr [rcx+29h], 5
0x140025a86  jb      short loc_140025A9D
0x140025a88  mov     rcx, [rcx+18h]
0x140025a8c  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025a93  mov     edx, 26h ; '&'
0x140025a98  call    WPP_SF_
0x140025a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025aa4  cmp     rcx, rbx
0x140025aa7  jz      short loc_140025ACD
0x140025aa9  test    dword ptr [rcx+2Ch], 10000h
0x140025ab0  jz      short loc_140025ACD
0x140025ab2  cmp     byte ptr [rcx+29h], 5
0x140025ab6  jb      short loc_140025ACD
0x140025ab8  mov     rcx, [rcx+18h]
0x140025abc  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025ac3  mov     edx, 27h ; '''
0x140025ac8  call    WPP_SF_
0x140025acd  add     rsp, 20h
0x140025ad1  pop     rbx
0x140025ad2  retn
```
