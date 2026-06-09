# CFormatChangeHandler::KsCompleteIo(_KSSTREAM_SEGMENT *)

- ea: `0x180025cf0`
- end: `0x180025d5a`
- name: `?KsCompleteIo@CFormatChangeHandler@@UEAAJPEAU_KSSTREAM_SEGMENT@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(CFormatChangeHandler *this, struct _KSSTREAM_SEGMENT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f1c4`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180025d14`
- `ole32!CoTaskMemFree` at `0x180025d14`

## pseudocode

```c
__int64 __fastcall CFormatChangeHandler::KsCompleteIo(CFormatChangeHandler *this, struct _KSSTREAM_SEGMENT *a2)
{
  a2[1].KsInterfaceHandler->Release(a2[1].KsInterfaceHandler);
  CoTaskMemFree(*(LPVOID *)&a2[2].IoOperation);
  operator delete(a2);
  this->m_pUnknown->CUnknown::__vftable[4].Release(this->m_pUnknown);
  this->NonDelegatingRelease(this);
  return 0;
}

```

## disassembly

```asm
0x180025cf0  mov     [rsp+arg_0], rbx
0x180025cf5  push    rdi
0x180025cf6  sub     rsp, 20h
0x180025cfa  mov     rdi, rcx
0x180025cfd  mov     rbx, rdx
0x180025d00  mov     rcx, [rdx+20h]
0x180025d04  mov     rax, [rcx]
0x180025d07  mov     rax, [rax+10h]
0x180025d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d10  mov     rcx, [rbx+50h]; pv
0x180025d14  call    cs:__imp_CoTaskMemFree
0x180025d1b  nop     dword ptr [rax+rax+00h]
0x180025d20  mov     edx, 80h; unsigned __int64
0x180025d25  mov     rcx, rbx; void *
0x180025d28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025d2d  mov     rcx, [rdi+8]
0x180025d31  mov     rax, [rcx]
0x180025d34  mov     rax, [rax+70h]
0x180025d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d3d  mov     rax, [rdi]
0x180025d40  mov     rcx, rdi
0x180025d43  mov     rax, [rax+10h]
0x180025d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d4c  mov     rbx, [rsp+28h+arg_0]
0x180025d51  xor     eax, eax
0x180025d53  add     rsp, 20h
0x180025d57  pop     rdi
0x180025d58  retn
```
