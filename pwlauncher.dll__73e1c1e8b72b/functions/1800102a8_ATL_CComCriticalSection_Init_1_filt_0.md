# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x1800102a8`
- end: `0x1800102c8`
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
0x1800102a8  push    rbp
0x1800102aa  sub     rsp, 20h
0x1800102ae  mov     rbp, rdx
0x1800102b1  mov     rax, [rcx]
0x1800102b4  xor     ecx, ecx
0x1800102b6  cmp     dword ptr [rax], 0C0000017h
0x1800102bc  setz    cl
0x1800102bf  mov     eax, ecx
0x1800102c1  add     rsp, 20h
0x1800102c5  pop     rbp
0x1800102c6  retn
```
