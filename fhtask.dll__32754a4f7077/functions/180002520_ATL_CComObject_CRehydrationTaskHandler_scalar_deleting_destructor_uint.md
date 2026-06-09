# ATL::CComObject<CRehydrationTaskHandler>::`scalar deleting destructor'(uint)

- ea: `0x180002520`
- end: `0x180002550`
- name: `??_G?$CComObject@VCRehydrationTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002250`
- `0x180002520`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000253c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000253c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CRehydrationTaskHandler>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CRehydrationTaskHandler>::~CComObject<CRehydrationTaskHandler>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002520  mov     [rsp+arg_0], rbx
0x180002525  push    rdi
0x180002526  sub     rsp, 20h
0x18000252a  mov     ebx, edx
0x18000252c  mov     rdi, rcx
0x18000252f  call    ??1?$CComObject@VCRehydrationTaskHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CRehydrationTaskHandler>::~CComObject<CRehydrationTaskHandler>(void)
0x180002534  test    bl, 1
0x180002537  jz      short loc_180002542
0x180002539  mov     rcx, rdi
0x18000253c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002542  mov     rbx, [rsp+28h+arg_0]
0x180002547  mov     rax, rdi
0x18000254a  add     rsp, 20h
0x18000254e  pop     rdi
0x18000254f  retn
```
