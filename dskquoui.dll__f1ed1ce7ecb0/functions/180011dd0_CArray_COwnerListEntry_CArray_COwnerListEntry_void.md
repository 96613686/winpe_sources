# CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)

- ea: `0x180011dd0`
- end: `0x180011df8`
- name: `??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e00`
- `0x180012120`
- `0x1800130ac`
- `0x180013b8c`
- `0x180014ca8`
- `0x180014e68`
- `0x18001ddf1`
- `0x18001de6f`
- `0x18001df49`
- `0x18001df5b`

## callees

- `0x180012ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011df1`

## pseudocode

```c
void __fastcall CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(__int64 a1)
{
  *(_QWORD *)a1 = &CArray<COwnerListEntry *>::`vftable';
  CArray<COwnerListEntry *>::Clear();
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
}

```

## disassembly

```asm
0x180011dd0  push    rbx
0x180011dd2  sub     rsp, 20h
0x180011dd6  lea     rax, ??_7?$CArray@PEAVCOwnerListEntry@@@@6B@; const CArray<COwnerListEntry *>::`vftable'
0x180011ddd  mov     rbx, rcx
0x180011de0  mov     [rcx], rax
0x180011de3  call    ?Clear@?$CArray@PEAVCOwnerListEntry@@@@QEAAXXZ; CArray<COwnerListEntry *>::Clear(void)
0x180011de8  lea     rcx, [rbx+20h]
0x180011dec  add     rsp, 20h
0x180011df0  pop     rbx
0x180011df1  jmp     cs:__imp_DeleteCriticalSection
```
