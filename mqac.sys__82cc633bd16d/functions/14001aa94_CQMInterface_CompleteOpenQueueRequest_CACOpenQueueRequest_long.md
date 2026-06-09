# CQMInterface::CompleteOpenQueueRequest(CACOpenQueueRequest *,long)

- ea: `0x14001aa94`
- end: `0x14001aaef`
- name: `?CompleteOpenQueueRequest@CQMInterface@@QEAAJPEAVCACOpenQueueRequest@@J@Z`
- size: `91`
- prototype: `int(CQMInterface *__hidden this, struct CACOpenQueueRequest *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140004314`
- `0x140004d64`

## callees

- `0x1400010a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001aacd`
- `ntoskrnl!IofCompleteRequest` at `0x14001aacd`

## pseudocode

```c
__int64 __fastcall CQMInterface::CompleteOpenQueueRequest(
        CQMInterface *this,
        struct CACOpenQueueRequest *a2,
        unsigned int a3)
{
  **(_QWORD **)(*((_QWORD *)a2 + 3) + 32LL) = 0;
  *(_QWORD *)(*((_QWORD *)a2 + 2) + 56LL) = 0;
  *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL) = a3;
  IofCompleteRequest(*((PIRP *)a2 + 2), 0);
  operator delete(a2);
  return a3;
}

```

## disassembly

```asm
0x14001aa94  mov     [rsp+arg_0], rbx
0x14001aa99  push    rdi
0x14001aa9a  sub     rsp, 20h
0x14001aa9e  mov     rax, [rdx+18h]
0x14001aaa2  mov     rbx, rdx
0x14001aaa5  mov     edi, r8d
0x14001aaa8  mov     rcx, [rax+20h]
0x14001aaac  mov     qword ptr [rcx], 0
0x14001aab3  mov     rax, [rdx+10h]
0x14001aab7  mov     qword ptr [rax+38h], 0
0x14001aabf  mov     rax, [rdx+10h]
0x14001aac3  xor     edx, edx; PriorityBoost
0x14001aac5  mov     [rax+30h], r8d
0x14001aac9  mov     rcx, [rbx+10h]; Irp
0x14001aacd  call    cs:__imp_IofCompleteRequest
0x14001aad4  nop     dword ptr [rax+rax+00h]
0x14001aad9  mov     rcx, rbx; void *
0x14001aadc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001aae1  mov     rbx, [rsp+28h+arg_0]
0x14001aae6  mov     eax, edi
0x14001aae8  add     rsp, 20h
0x14001aaec  pop     rdi
0x14001aaed  retn
```
