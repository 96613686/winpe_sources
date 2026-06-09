# CFormatChangeHandler::KsCompleteIo(_KSSTREAM_SEGMENT *)

- ea: `0x10010590`
- end: `0x100105ee`
- name: `?KsCompleteIo@CFormatChangeHandler@@UAGJPAU_KSSTREAM_SEGMENT@@@Z`
- size: `94`
- prototype: `int __stdcall(CFormatChangeHandler *__hidden this, struct _KSSTREAM_SEGMENT *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1002d510`
- `0x1003af9d`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x100105b0`
- `ole32!CoTaskMemFree` at `0x100105b0`

## pseudocode

```c
int __stdcall CFormatChangeHandler::KsCompleteIo(CFormatChangeHandler *this, struct _KSSTREAM_SEGMENT *Block)
{
  ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsInterfaceHandler *))Block[1].KsInterfaceHandler->Release)(
    Block[1].KsInterfaceHandler->Release,
    Block[1].KsInterfaceHandler);
  CoTaskMemFree(Block[4].KsInterfaceHandler);
  operator delete(Block, 0x60u);
  ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *const))this->m_pUnknown->CUnknown::__vftable[4].Release)(
    this->m_pUnknown->CUnknown::__vftable[4].Release,
    this->m_pUnknown);
  ((void (__thiscall *)(unsigned int (__stdcall *)(struct CFormatChangeHandler *), CFormatChangeHandler *))this->NonDelegatingRelease)(
    this->NonDelegatingRelease,
    this);
  return 0;
}

```

## disassembly

```asm
0x10010590  mov     edi, edi
0x10010592  push    ebp
0x10010593  mov     ebp, esp
0x10010595  push    esi
0x10010596  push    edi
0x10010597  mov     edi, [ebp+Block]
0x1001059a  mov     eax, [edi+10h]
0x1001059d  push    eax
0x1001059e  mov     ecx, [eax]
0x100105a0  mov     esi, [ecx+8]
0x100105a3  mov     ecx, esi; this
0x100105a5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100105ab  call    esi
0x100105ad  push    dword ptr [edi+40h]; pv
0x100105b0  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100105b6  push    60h ; '`'; unsigned int
0x100105b8  push    edi; Block
0x100105b9  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100105be  mov     edi, [ebp+this]
0x100105c1  pop     ecx
0x100105c2  pop     ecx
0x100105c3  mov     eax, [edi+4]
0x100105c6  push    eax
0x100105c7  mov     ecx, [eax]
0x100105c9  mov     esi, [ecx+38h]
0x100105cc  mov     ecx, esi; this
0x100105ce  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100105d4  call    esi
0x100105d6  mov     eax, [edi]
0x100105d8  push    edi
0x100105d9  mov     esi, [eax+8]
0x100105dc  mov     ecx, esi; this
0x100105de  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100105e4  call    esi
0x100105e6  pop     edi
0x100105e7  xor     eax, eax
0x100105e9  pop     esi
0x100105ea  pop     ebp
0x100105eb  retn    8
```
