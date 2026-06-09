# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x18000af56`
- end: `0x18000af76`
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
0x18000af56  push    rbp
0x18000af58  sub     rsp, 20h
0x18000af5c  mov     rbp, rdx
0x18000af5f  mov     rax, [rcx]
0x18000af62  xor     ecx, ecx
0x18000af64  cmp     dword ptr [rax], 0C0000017h
0x18000af6a  setz    cl
0x18000af6d  mov     eax, ecx
0x18000af6f  add     rsp, 20h
0x18000af73  pop     rbp
0x18000af74  retn
```
