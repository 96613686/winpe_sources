# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000cbe9`
- end: `0x18000cc09`
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
0x18000cbe9  push    rbp
0x18000cbeb  sub     rsp, 20h
0x18000cbef  mov     rbp, rdx
0x18000cbf2  mov     rax, [rcx]
0x18000cbf5  xor     ecx, ecx
0x18000cbf7  cmp     dword ptr [rax], 0C0000017h
0x18000cbfd  setz    cl
0x18000cc00  mov     eax, ecx
0x18000cc02  add     rsp, 20h
0x18000cc06  pop     rbp
0x18000cc07  retn
```
