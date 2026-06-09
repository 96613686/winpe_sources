# ATL::CAutoVectorPtr<ushort>::~CAutoVectorPtr<ushort>(void)

- ea: `0x180002124`
- end: `0x180002143`
- name: `??1?$CAutoVectorPtr@G@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180009df6`
- `0x180009e08`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002130`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002130`

## pseudocode

```c
void __fastcall ATL::CAutoVectorPtr<unsigned short>::~CAutoVectorPtr<unsigned short>(void **a1)
{
  operator delete[](*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180002124  push    rbx
0x180002126  sub     rsp, 20h
0x18000212a  mov     rbx, rcx
0x18000212d  mov     rcx, [rcx]
0x180002130  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002136  mov     qword ptr [rbx], 0
0x18000213d  add     rsp, 20h
0x180002141  pop     rbx
0x180002142  retn
```
