# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180013d51`
- end: `0x180013d71`
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
0x180013d51  push    rbp
0x180013d53  sub     rsp, 20h
0x180013d57  mov     rbp, rdx
0x180013d5a  mov     rax, [rcx]
0x180013d5d  xor     ecx, ecx
0x180013d5f  cmp     dword ptr [rax], 0C0000017h
0x180013d65  setz    cl
0x180013d68  mov     eax, ecx
0x180013d6a  add     rsp, 20h
0x180013d6e  pop     rbp
0x180013d6f  retn
```
