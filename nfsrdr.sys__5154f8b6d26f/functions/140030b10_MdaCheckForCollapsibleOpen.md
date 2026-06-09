# MdaCheckForCollapsibleOpen

- ea: `0x140030b10`
- end: `0x140030b54`
- name: `MdaCheckForCollapsibleOpen`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400159fc`
- `0x140030b10`

## pseudocode

```c
__int64 MdaCheckForCollapsibleOpen()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  return 3221226021LL;
}

```

## disassembly

```asm
0x140030b10  sub     rsp, 28h
0x140030b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b1b  lea     rax, WPP_GLOBAL_Control
0x140030b22  cmp     rcx, rax
0x140030b25  jz      short loc_140030B49
0x140030b27  mov     eax, [rcx+2Ch]
0x140030b2a  test    al, 8
0x140030b2c  jz      short loc_140030B49
0x140030b2e  mov     rcx, [rcx+18h]
0x140030b32  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030b39  mov     edx, 63h ; 'c'
0x140030b3e  mov     r9d, 0C0000225h
0x140030b44  call    WPP_SF_d
0x140030b49  mov     eax, 0C0000225h
0x140030b4e  add     rsp, 28h
0x140030b52  retn
```
