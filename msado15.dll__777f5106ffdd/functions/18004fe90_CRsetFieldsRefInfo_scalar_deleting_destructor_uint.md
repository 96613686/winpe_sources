# CRsetFieldsRefInfo::`scalar deleting destructor'(uint)

- ea: `0x18004fe90`
- end: `0x18004ff0a`
- name: `??_GCRsetFieldsRefInfo@@UEAAPEAXI@Z`
- size: `122`
- prototype: `void *__fastcall(CRsetFieldsRefInfo *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18004fe90`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18004feef`
- `MSDART!MpHeapFree` at `0x18004feef`
- `ole32!CoTaskMemFree` at `0x18004fec2`
- `ole32!CoTaskMemFree` at `0x18004fed2`
- `ole32!CoTaskMemFree` at `0x18004fec2`
- `ole32!CoTaskMemFree` at `0x18004fed2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRsetFieldsRefInfo *__fastcall CRsetFieldsRefInfo::`scalar deleting destructor'(CRsetFieldsRefInfo *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CRsetFieldsRefInfo::`vftable';
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 4));
  if ( (a2 & 1) != 0 )
    MpHeapFree(g_hHeapHandle, this);
  return this;
}

```

## disassembly

```asm
0x18004fe90  mov     [rsp+arg_0], rbx
0x18004fe95  push    rdi
0x18004fe96  sub     rsp, 20h
0x18004fe9a  mov     edi, edx
0x18004fe9c  mov     rbx, rcx
0x18004fe9f  lea     rax, ??_7CRsetFieldsRefInfo@@6B@; const CRsetFieldsRefInfo::`vftable'
0x18004fea6  mov     [rcx], rax
0x18004fea9  mov     rcx, [rcx+28h]
0x18004fead  test    rcx, rcx
0x18004feb0  jz      short loc_18004FEBE
0x18004feb2  mov     rax, [rcx]
0x18004feb5  mov     rax, [rax+10h]
0x18004feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004febe  mov     rcx, [rbx+18h]; pv
0x18004fec2  call    cs:__imp_CoTaskMemFree
0x18004fec9  nop     dword ptr [rax+rax+00h]
0x18004fece  mov     rcx, [rbx+20h]; pv
0x18004fed2  call    cs:__imp_CoTaskMemFree
0x18004fed9  nop     dword ptr [rax+rax+00h]
0x18004fede  nop
0x18004fedf  test    dil, 1
0x18004fee3  jz      short loc_18004FEFB
0x18004fee5  mov     rdx, rbx
0x18004fee8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004feef  call    cs:__imp_MpHeapFree
0x18004fef6  nop     dword ptr [rax+rax+00h]
0x18004fefb  mov     rax, rbx
0x18004fefe  mov     rbx, [rsp+28h+arg_0]
0x18004ff03  add     rsp, 20h
0x18004ff07  pop     rdi
0x18004ff08  retn
```
