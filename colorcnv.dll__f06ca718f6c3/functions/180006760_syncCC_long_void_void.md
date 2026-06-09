# syncCC(long *,void *,void *)

- ea: `0x180006760`
- end: `0x180006792`
- name: `?syncCC@@YAXPEAJPEAX1@Z`
- size: `50`
- prototype: `void(int *, void *, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064d0`
- `0x180006610`
- `0x180014a30`
- `0x180014b70`

## callees

- `0x180006760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000678a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000678a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006780`

## pseudocode

```c
void __fastcall syncCC(int *a1, void *a2, void *a3)
{
  if ( _InterlockedExchangeAdd(a1, 0xFFFFFFFF) == 1 )
    SetEvent(a2);
  WaitForSingleObject(a3, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180006760  push    rbx
0x180006762  sub     rsp, 20h
0x180006766  mov     rbx, r8
0x180006769  or      eax, 0FFFFFFFFh
0x18000676c  lock xadd [rcx], eax
0x180006770  cmp     eax, 1
0x180006773  jz      short loc_180006787
0x180006775  or      edx, 0FFFFFFFFh
0x180006778  mov     rcx, rbx
0x18000677b  add     rsp, 20h
0x18000677f  pop     rbx
0x180006780  jmp     cs:__imp_WaitForSingleObject
0x180006787  mov     rcx, rdx; hEvent
0x18000678a  call    cs:__imp_SetEvent
0x180006790  jmp     short loc_180006775
```
