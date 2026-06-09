# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(void)

- ea: `0x18002a124`
- end: `0x18002a164`
- name: `??1?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAA@XZ`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002a444`
- `0x18002a500`

## callees

- `0x1800018e4`
- `0x18002f508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a15d`

## pseudocode

```c
void __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::~CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>(
        __int64 a1)
{
  *(_QWORD *)a1 = &CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable';
  CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_DeleteAllItems();
  operator delete(*(void **)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x18002a124  push    rbx
0x18002a126  sub     rsp, 20h
0x18002a12a  lea     rax, ??_7?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@6B@; const CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::`vftable'
0x18002a131  mov     rbx, rcx
0x18002a134  mov     [rcx], rax
0x18002a137  call    ?_DeleteAllItems@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAJXZ; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_DeleteAllItems(void)
0x18002a13c  mov     rcx, [rbx+30h]; Block
0x18002a140  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a145  lea     rcx, [rbx+8]
0x18002a149  mov     qword ptr [rbx+30h], 0
0x18002a151  mov     dword ptr [rbx+38h], 0
0x18002a158  add     rsp, 20h
0x18002a15c  pop     rbx
0x18002a15d  jmp     cs:__imp_DeleteCriticalSection
```
