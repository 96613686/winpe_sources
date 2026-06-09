# CW32System::CoTaskMemFree(void *)

- ea: `0x18008d624`
- end: `0x18008d66f`
- name: `?CoTaskMemFree@CW32System@@SAXPEAX@Z`
- size: `75`
- prototype: `void __fastcall(void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800208d8`
- `0x18005361c`
- `0x180074458`
- `0x18007e258`
- `0x18008c2dc`

## callees

- `0x180041adc`
- `0x18008d624`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008d640`: `CoTaskMemFree`

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
0x18008d624  mov     [rsp+arg_0], rbx
0x18008d629  push    rdi
0x18008d62a  sub     rsp, 20h
0x18008d62e  mov     rdi, rcx
0x18008d631  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008d636  lea     rbx, [rax+8]
0x18008d63a  cmp     qword ptr [rbx], 0
0x18008d63e  jnz     short loc_18008D654
0x18008d640  lea     r8, aCotaskmemfree; "CoTaskMemFree"
0x18008d647  mov     edx, 1
0x18008d64c  mov     rcx, rbx
0x18008d64f  call    SetProcAddr
0x18008d654  mov     rax, [rbx]
0x18008d657  test    rax, rax
0x18008d65a  jz      short loc_18008D664
0x18008d65c  mov     rcx, rdi
0x18008d65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d664  mov     rbx, [rsp+28h+arg_0]
0x18008d669  add     rsp, 20h
0x18008d66d  pop     rdi
0x18008d66e  retn
```
