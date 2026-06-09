# ATL::CComObject<CTaskHandler>::`vector deleting destructor'(uint)

- ea: `0x180002560`
- end: `0x180002590`
- name: `??_E?$CComObject@VCTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022e4`
- `0x180002560`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000257c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000257c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CTaskHandler>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CTaskHandler>::~CComObject<CTaskHandler>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002560  mov     [rsp+arg_0], rbx
0x180002565  push    rdi
0x180002566  sub     rsp, 20h
0x18000256a  mov     ebx, edx
0x18000256c  mov     rdi, rcx
0x18000256f  call    ??1?$CComObject@VCTaskHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CTaskHandler>::~CComObject<CTaskHandler>(void)
0x180002574  test    bl, 1
0x180002577  jz      short loc_180002582
0x180002579  mov     rcx, rdi
0x18000257c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002582  mov     rbx, [rsp+28h+arg_0]
0x180002587  mov     rax, rdi
0x18000258a  add     rsp, 20h
0x18000258e  pop     rdi
0x18000258f  retn
```
