# ATL::CComAggObject<CTaskHandler>::`scalar deleting destructor'(uint)

- ea: `0x1800024e0`
- end: `0x180002510`
- name: `??_G?$CComAggObject@VCTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800021e0`
- `0x1800024e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800024fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800024fc`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CTaskHandler>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CTaskHandler>::~CComAggObject<CTaskHandler>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800024e0  mov     [rsp+arg_0], rbx
0x1800024e5  push    rdi
0x1800024e6  sub     rsp, 20h
0x1800024ea  mov     ebx, edx
0x1800024ec  mov     rdi, rcx
0x1800024ef  call    ??1?$CComAggObject@VCTaskHandler@@@ATL@@UEAA@XZ; ATL::CComAggObject<CTaskHandler>::~CComAggObject<CTaskHandler>(void)
0x1800024f4  test    bl, 1
0x1800024f7  jz      short loc_180002502
0x1800024f9  mov     rcx, rdi
0x1800024fc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002502  mov     rbx, [rsp+28h+arg_0]
0x180002507  mov     rax, rdi
0x18000250a  add     rsp, 20h
0x18000250e  pop     rdi
0x18000250f  retn
```
