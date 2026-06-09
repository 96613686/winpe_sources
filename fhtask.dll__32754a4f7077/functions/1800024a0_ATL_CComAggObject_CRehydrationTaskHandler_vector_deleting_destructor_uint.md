# ATL::CComAggObject<CRehydrationTaskHandler>::`vector deleting destructor'(uint)

- ea: `0x1800024a0`
- end: `0x1800024d0`
- name: `??_E?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000214c`
- `0x1800024a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800024bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800024bc`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CRehydrationTaskHandler>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComAggObject<CRehydrationTaskHandler>::~CComAggObject<CRehydrationTaskHandler>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800024a0  mov     [rsp+arg_0], rbx
0x1800024a5  push    rdi
0x1800024a6  sub     rsp, 20h
0x1800024aa  mov     ebx, edx
0x1800024ac  mov     rdi, rcx
0x1800024af  call    ??1?$CComAggObject@VCRehydrationTaskHandler@@@ATL@@UEAA@XZ; ATL::CComAggObject<CRehydrationTaskHandler>::~CComAggObject<CRehydrationTaskHandler>(void)
0x1800024b4  test    bl, 1
0x1800024b7  jz      short loc_1800024C2
0x1800024b9  mov     rcx, rdi
0x1800024bc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800024c2  mov     rbx, [rsp+28h+arg_0]
0x1800024c7  mov     rax, rdi
0x1800024ca  add     rsp, 20h
0x1800024ce  pop     rdi
0x1800024cf  retn
```
