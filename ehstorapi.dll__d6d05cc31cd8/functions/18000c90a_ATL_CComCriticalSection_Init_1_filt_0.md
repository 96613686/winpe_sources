# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000c90a`
- end: `0x18000c92a`
- name: `_ATL::CComCriticalSection::Init_::_1_::filt$0`
- size: `32`
- prototype: ``
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
0x18000c90a  push    rbp
0x18000c90c  sub     rsp, 20h
0x18000c910  mov     rbp, rdx
0x18000c913  mov     rax, [rcx]
0x18000c916  xor     ecx, ecx
0x18000c918  cmp     dword ptr [rax], 0C0000017h
0x18000c91e  setz    cl
0x18000c921  mov     eax, ecx
0x18000c923  add     rsp, 20h
0x18000c927  pop     rbp
0x18000c928  retn
```
