# CClfsRequest::CreateReadCompletionElement(void)

- ea: `0x14000d460`
- end: `0x14000d527`
- name: `?CreateReadCompletionElement@CClfsRequest@@UEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000d460`
- `0x140017f20`
- `0x140018280`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000d474`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000d474`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14000d4f5`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14000d4f5`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d4c3`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d4c3`

## pseudocode

```c
__int64 __fastcall CClfsRequest::CreateReadCompletionElement(CClfsRequest *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  PIO_WORKITEM WorkItem; // rax

  v2 = ExAllocateFromNPagedLookasideList(&CClfsReadCompletionElt::m_laList);
  v3 = v2;
  if ( v2 )
  {
    v2[3] = this;
    *((_DWORD *)v2 + 26) = 0;
    *v2 = &CClfsReadCompletionElt::`vftable';
    memset(v2 + 4, 0, 0x48u);
    v3[8] = v3;
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)this + 6) + 184LL) + 40LL));
    v3[4] = WorkItem;
    if ( WorkItem )
    {
      v3[7] = CClfsRequest::AsyncReadIoCompletion;
      ExInterlockedInsertTailList((PLIST_ENTRY)this + 11, (PLIST_ENTRY)(v3 + 1), (PKSPIN_LOCK)this + 24);
      return 0;
    }
    (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000d460  mov     [rsp+arg_0], rbx
0x14000d465  push    rdi
0x14000d466  sub     rsp, 20h
0x14000d46a  mov     rdi, rcx
0x14000d46d  lea     rcx, ?m_laList@CClfsReadCompletionElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14000d474  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000d47b  nop     dword ptr [rax+rax+00h]
0x14000d480  mov     rbx, rax
0x14000d483  test    rax, rax
0x14000d486  jz      loc_14000D50F
0x14000d48c  xor     edx, edx; Val
0x14000d48e  mov     [rbx+18h], rdi
0x14000d492  lea     rax, ??_7CClfsReadCompletionElt@@6B@; const CClfsReadCompletionElt::`vftable'
0x14000d499  mov     dword ptr [rbx+68h], 0
0x14000d4a0  lea     rcx, [rbx+20h]; void *
0x14000d4a4  mov     [rbx], rax
0x14000d4a7  lea     r8d, [rdx+48h]; Size
0x14000d4ab  call    memset
0x14000d4b0  mov     [rbx+40h], rbx
0x14000d4b4  mov     rcx, [rdi+30h]
0x14000d4b8  mov     rcx, [rcx+0B8h]
0x14000d4bf  mov     rcx, [rcx+28h]; DeviceObject
0x14000d4c3  call    cs:__imp_IoAllocateWorkItem
0x14000d4ca  nop     dword ptr [rax+rax+00h]
0x14000d4cf  mov     [rbx+20h], rax
0x14000d4d3  test    rax, rax
0x14000d4d6  jz      short loc_14000D516
0x14000d4d8  lea     rax, ?AsyncReadIoCompletion@CClfsRequest@@SAXPEAXPEAU_IO_STATUS_BLOCK@@K@Z; CClfsRequest::AsyncReadIoCompletion(void *,_IO_STATUS_BLOCK *,ulong)
0x14000d4df  lea     r8, [rdi+0C0h]; Lock
0x14000d4e6  mov     [rbx+38h], rax
0x14000d4ea  lea     rdx, [rbx+8]; ListEntry
0x14000d4ee  lea     rcx, [rdi+0B0h]; ListHead
0x14000d4f5  call    cs:__imp_ExInterlockedInsertTailList
0x14000d4fc  nop     dword ptr [rax+rax+00h]
0x14000d501  xor     eax, eax
0x14000d503  mov     rbx, [rsp+28h+arg_0]
0x14000d508  add     rsp, 20h
0x14000d50c  pop     rdi
0x14000d50d  retn
0x14000d50f  mov     eax, 0C000009Ah
0x14000d514  jmp     short loc_14000D503
0x14000d516  mov     rax, [rbx]
0x14000d519  mov     rcx, rbx
0x14000d51c  mov     rax, [rax+8]
0x14000d520  call    _guard_dispatch_icall
0x14000d525  jmp     short loc_14000D50F
```
