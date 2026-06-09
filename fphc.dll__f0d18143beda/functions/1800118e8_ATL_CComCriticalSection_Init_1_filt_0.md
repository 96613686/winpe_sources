# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x1800118e8`
- end: `0x180011908`
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
0x1800118e8  push    rbp
0x1800118ea  sub     rsp, 20h
0x1800118ee  mov     rbp, rdx
0x1800118f1  mov     rax, [rcx]
0x1800118f4  xor     ecx, ecx
0x1800118f6  cmp     dword ptr [rax], 0C0000017h
0x1800118fc  setz    cl
0x1800118ff  mov     eax, ecx
0x180011901  add     rsp, 20h
0x180011905  pop     rbp
0x180011906  retn
```
