# CSSMappedStream::Close(long *)

- ea: `0x18003c5e0`
- end: `0x18003c631`
- name: `?Close@CSSMappedStream@@UEAAXPEAJ@Z`
- size: `81`
- prototype: `void __fastcall(CSSMappedStream *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003c638`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c5fb`

## pseudocode

```c
void __fastcall CSSMappedStream::Close(LPVOID *this, int *a2)
{
  *a2 = CSSMappedStream::Write((CSSMappedStream *)this);
  CoTaskMemFree(this[3]);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)this[2] + 16LL))(this[2]);
  this[2] = 0;
  this[3] = 0;
  this[4] = 0;
  this[5] = 0;
  *((_DWORD *)this + 12) = 0;
}

```

## disassembly

```asm
0x18003c5e0  mov     [rsp+arg_0], rbx
0x18003c5e5  push    rdi
0x18003c5e6  sub     rsp, 20h
0x18003c5ea  mov     rbx, rdx
0x18003c5ed  mov     rdi, rcx
0x18003c5f0  call    ?Write@CSSMappedStream@@IEAAJXZ; CSSMappedStream::Write(void)
0x18003c5f5  mov     [rbx], eax
0x18003c5f7  mov     rcx, [rdi+18h]; pv
0x18003c5fb  call    cs:__imp_CoTaskMemFree
0x18003c601  mov     rcx, [rdi+10h]
0x18003c605  mov     rax, [rcx]
0x18003c608  mov     rax, [rax+10h]
0x18003c60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c611  mov     rbx, [rsp+28h+arg_0]
0x18003c616  xor     eax, eax
0x18003c618  mov     [rdi+10h], rax
0x18003c61c  mov     [rdi+18h], rax
0x18003c620  mov     [rdi+20h], rax
0x18003c624  mov     [rdi+28h], rax
0x18003c628  mov     [rdi+30h], eax
0x18003c62b  add     rsp, 20h
0x18003c62f  pop     rdi
0x18003c630  retn
```
