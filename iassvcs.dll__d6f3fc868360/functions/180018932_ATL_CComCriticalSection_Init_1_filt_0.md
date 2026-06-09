# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x180018932`
- end: `0x180018952`
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
0x180018932  push    rbp
0x180018934  sub     rsp, 20h
0x180018938  mov     rbp, rdx
0x18001893b  mov     rax, [rcx]
0x18001893e  xor     ecx, ecx
0x180018940  cmp     dword ptr [rax], 0C0000017h
0x180018946  setz    cl
0x180018949  mov     eax, ecx
0x18001894b  add     rsp, 20h
0x18001894f  pop     rbp
0x180018950  retn
```
