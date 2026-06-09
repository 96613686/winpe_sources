# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180009f18`
- end: `0x180009f38`
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
0x180009f18  push    rbp
0x180009f1a  sub     rsp, 20h
0x180009f1e  mov     rbp, rdx
0x180009f21  mov     rax, [rcx]
0x180009f24  xor     ecx, ecx
0x180009f26  cmp     dword ptr [rax], 0C0000017h
0x180009f2c  setz    cl
0x180009f2f  mov     eax, ecx
0x180009f31  add     rsp, 20h
0x180009f35  pop     rbp
0x180009f36  retn
```
