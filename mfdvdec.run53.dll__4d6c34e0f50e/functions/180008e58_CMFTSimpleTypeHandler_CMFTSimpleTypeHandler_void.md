# CMFTSimpleTypeHandler::~CMFTSimpleTypeHandler(void)

- ea: `0x180008e58`
- end: `0x180008ec6`
- name: `??1CMFTSimpleTypeHandler@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(CMFTSimpleTypeHandler *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002130`
- `0x180004818`
- `0x180008f40`

## callees

- `0x180008e58`
- `0x180009404`
- `0x1800094b8`
- `0x18001e010`

## pseudocode

```c
void __fastcall CMFTSimpleTypeHandler::~CMFTSimpleTypeHandler(CMFTSimpleTypeHandler *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CMFTSimpleTypeHandler::`vftable';
  CMFTSimpleTypeHandler::InitAvailableInputTypeArray(this, 0);
  CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(this, 0);
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 10) = 0;
  }
  *(_QWORD *)this = &CMFTTypeHandler::`vftable';
}

```

## disassembly

```asm
0x180008e58  push    rbx
0x180008e5a  sub     rsp, 20h
0x180008e5e  lea     rax, ??_7CMFTSimpleTypeHandler@@6B@; const CMFTSimpleTypeHandler::`vftable'
0x180008e65  xor     edx, edx; unsigned int
0x180008e67  mov     [rcx], rax
0x180008e6a  mov     rbx, rcx
0x180008e6d  call    ?InitAvailableInputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableInputTypeArray(ulong)
0x180008e72  xor     edx, edx; unsigned int
0x180008e74  mov     rcx, rbx; this
0x180008e77  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x180008e7c  mov     rcx, [rbx+30h]
0x180008e80  test    rcx, rcx
0x180008e83  jz      short loc_180008E99
0x180008e85  mov     rax, [rcx]
0x180008e88  mov     rax, [rax+10h]
0x180008e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e91  mov     qword ptr [rbx+30h], 0
0x180008e99  mov     rcx, [rbx+50h]
0x180008e9d  test    rcx, rcx
0x180008ea0  jz      short loc_180008EB6
0x180008ea2  mov     rax, [rcx]
0x180008ea5  mov     rax, [rax+10h]
0x180008ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eae  mov     qword ptr [rbx+50h], 0
0x180008eb6  lea     rax, ??_7CMFTTypeHandler@@6B@; const CMFTTypeHandler::`vftable'
0x180008ebd  mov     [rbx], rax
0x180008ec0  add     rsp, 20h
0x180008ec4  pop     rbx
0x180008ec5  retn
```
