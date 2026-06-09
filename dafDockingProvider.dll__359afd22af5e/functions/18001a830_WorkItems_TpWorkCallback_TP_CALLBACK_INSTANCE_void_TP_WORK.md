# WorkItems::TpWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18001a830`
- end: `0x18001a87b`
- name: `?TpWorkCallback@WorkItems@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `75`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001a857`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001a857`

## pseudocode

```c
void __fastcall WorkItems::TpWorkCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Context + 8LL))(Context);
  CloseThreadpoolWork(Work);
  (**(void (__fastcall ***)(PVOID, __int64))Context)(Context, 1);
}

```

## disassembly

```asm
0x18001a830  mov     [rsp+arg_0], rbx
0x18001a835  push    rdi
0x18001a836  sub     rsp, 20h
0x18001a83a  mov     rbx, r8
0x18001a83d  mov     rdi, rdx
0x18001a840  mov     [rsp+28h+arg_8], rdx
0x18001a845  mov     rax, [rdx]
0x18001a848  mov     rcx, rdx
0x18001a84b  mov     rax, [rax+8]
0x18001a84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a854  mov     rcx, rbx; pwk
0x18001a857  call    cs:__imp_CloseThreadpoolWork
0x18001a85d  nop
0x18001a85e  mov     rax, [rdi]
0x18001a861  mov     edx, 1
0x18001a866  mov     rcx, rdi
0x18001a869  mov     rax, [rax]
0x18001a86c  mov     rbx, [rsp+28h+arg_0]
0x18001a871  add     rsp, 20h
0x18001a875  pop     rdi
0x18001a876  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
