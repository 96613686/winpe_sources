# _ATL::CComCriticalSection::Init_::_1_::filt$0

- ea: `0x140009235`
- end: `0x140009255`
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
0x140009235  push    rbp
0x140009237  sub     rsp, 20h
0x14000923b  mov     rbp, rdx
0x14000923e  mov     rax, [rcx]
0x140009241  xor     ecx, ecx
0x140009243  cmp     dword ptr [rax], 0C0000017h
0x140009249  setz    cl
0x14000924c  mov     eax, ecx
0x14000924e  add     rsp, 20h
0x140009252  pop     rbp
0x140009253  retn
```
