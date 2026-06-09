# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000e226`
- end: `0x18000e246`
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
0x18000e226  push    rbp
0x18000e228  sub     rsp, 20h
0x18000e22c  mov     rbp, rdx
0x18000e22f  mov     rax, [rcx]
0x18000e232  xor     ecx, ecx
0x18000e234  cmp     dword ptr [rax], 0C0000017h
0x18000e23a  setz    cl
0x18000e23d  mov     eax, ecx
0x18000e23f  add     rsp, 20h
0x18000e243  pop     rbp
0x18000e244  retn
```
