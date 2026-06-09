# CMultistateFileRecordQuery::CMultistateFileRecordQuery(ATL::CComPtr<IFhCatalog>)

- ea: `0x1800079c0`
- end: `0x180007a14`
- name: `??0CMultistateFileRecordQuery@@QEAA@V?$CComPtr@UIFhCatalog@@@ATL@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cafc`
- `0x180012b44`
- `0x1800163cc`
- `0x18001789c`

## callees

- `0x1800031b0`
- `0x1800079c0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMultistateFileRecordQuery::CMultistateFileRecordQuery(__int64 a1, __int64 *a2)
{
  __int64 v4; // rcx

  v4 = *a2;
  *(_QWORD *)a1 = *a2;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = -1;
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(a2);
  return a1;
}

```

## disassembly

```asm
0x1800079c0  mov     [rsp+arg_0], rbx
0x1800079c5  push    rdi
0x1800079c6  sub     rsp, 20h
0x1800079ca  mov     rdi, rdx
0x1800079cd  mov     rbx, rcx
0x1800079d0  mov     rcx, [rdx]
0x1800079d3  mov     [rbx], rcx
0x1800079d6  test    rcx, rcx
0x1800079d9  jz      short loc_1800079E8
0x1800079db  mov     rax, [rcx]
0x1800079de  mov     rax, [rax+8]
0x1800079e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e7  nop
0x1800079e8  mov     dword ptr [rbx+8], 0
0x1800079ef  mov     qword ptr [rbx+10h], 0
0x1800079f7  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x1800079fe  mov     rcx, rdi
0x180007a01  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x180007a06  mov     rax, rbx
0x180007a09  mov     rbx, [rsp+28h+arg_0]
0x180007a0e  add     rsp, 20h
0x180007a12  pop     rdi
0x180007a13  retn
```
