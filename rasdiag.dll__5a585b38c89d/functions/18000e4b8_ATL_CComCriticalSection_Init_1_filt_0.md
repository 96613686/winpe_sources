# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000e4b8`
- end: `0x18000e4d8`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: `_BOOL8 __fastcall(_DWORD **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall ATL::CComCriticalSection::Init_::_1_::filt_0(_DWORD **a1)
{
  return **a1 == -1073741801;
}

```

## disassembly

```asm
0x18000e4b8  push    rbp
0x18000e4ba  sub     rsp, 20h
0x18000e4be  mov     rbp, rdx
0x18000e4c1  mov     rax, [rcx]
0x18000e4c4  xor     ecx, ecx
0x18000e4c6  cmp     dword ptr [rax], 0C0000017h
0x18000e4cc  setz    cl
0x18000e4cf  mov     eax, ecx
0x18000e4d1  add     rsp, 20h
0x18000e4d5  pop     rbp
0x18000e4d6  retn
```
