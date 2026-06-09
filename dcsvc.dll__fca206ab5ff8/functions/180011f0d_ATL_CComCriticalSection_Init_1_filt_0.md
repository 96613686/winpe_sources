# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180011f0d`
- end: `0x180011f2d`
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
0x180011f0d  push    rbp
0x180011f0f  sub     rsp, 20h
0x180011f13  mov     rbp, rdx
0x180011f16  mov     rax, [rcx]
0x180011f19  xor     ecx, ecx
0x180011f1b  cmp     dword ptr [rax], 0C0000017h
0x180011f21  setz    cl
0x180011f24  mov     eax, ecx
0x180011f26  add     rsp, 20h
0x180011f2a  pop     rbp
0x180011f2b  retn
```
