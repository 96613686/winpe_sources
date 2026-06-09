# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18001628c`
- end: `0x1800162ac`
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
0x18001628c  push    rbp
0x18001628e  sub     rsp, 20h
0x180016292  mov     rbp, rdx
0x180016295  mov     rax, [rcx]
0x180016298  xor     ecx, ecx
0x18001629a  cmp     dword ptr [rax], 0C0000017h
0x1800162a0  setz    cl
0x1800162a3  mov     eax, ecx
0x1800162a5  add     rsp, 20h
0x1800162a9  pop     rbp
0x1800162aa  retn
```
