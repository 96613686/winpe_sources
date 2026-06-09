# CW32System::CoTaskMemFree(void *)

- ea: `0x18008fe00`
- end: `0x18008fe4c`
- name: `?CoTaskMemFree@CW32System@@SAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002327c`
- `0x180054a88`
- `0x180076438`
- `0x180080698`
- `0x18008e9e0`

## callees

- `0x1800427ac`
- `0x18008fe00`
- `0x1800931b0`
- `0x180095010`

## string_xrefs

- `0x18008fe1c`: `CoTaskMemFree`

## pseudocode

```c
void __fastcall CW32System::CoTaskMemFree(void *a1)
{
  struct COLE32_PROC *Ole32Procs; // rax
  void (__fastcall **v3)(void *); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v3 = (void (__fastcall **)(void *))((char *)Ole32Procs + 8);
  if ( !*((_QWORD *)Ole32Procs + 1) )
    SetProcAddr((FARPROC *)Ole32Procs + 1, 1, "CoTaskMemFree");
  if ( *v3 )
    (*v3)(a1);
}

```

## disassembly

```asm
0x18008fe00  mov     [rsp+arg_0], rbx
0x18008fe05  push    rdi
0x18008fe06  sub     rsp, 20h
0x18008fe0a  mov     rdi, rcx
0x18008fe0d  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008fe12  lea     rbx, [rax+8]
0x18008fe16  cmp     qword ptr [rbx], 0
0x18008fe1a  jnz     short loc_18008FE30
0x18008fe1c  lea     r8, aCotaskmemfree; "CoTaskMemFree"
0x18008fe23  mov     edx, 1
0x18008fe28  mov     rcx, rbx
0x18008fe2b  call    SetProcAddr
0x18008fe30  mov     rax, [rbx]
0x18008fe33  test    rax, rax
0x18008fe36  jz      short loc_18008FE40
0x18008fe38  mov     rcx, rdi
0x18008fe3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe40  mov     rbx, [rsp+28h+arg_0]
0x18008fe45  add     rsp, 20h
0x18008fe49  pop     rdi
0x18008fe4a  retn
```
