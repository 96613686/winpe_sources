# CDynamicCountedObjectArray::~CDynamicCountedObjectArray(void)

- ea: `0x180005a58`
- end: `0x180005a95`
- name: `??1CDynamicCountedObjectArray@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CDynamicCountedObjectArray *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ae0`
- `0x180007a38`
- `0x180008314`
- `0x180008d54`

## callees

- `0x180005a18`
- `0x180005a58`
- `0x180005d40`

## pseudocode

```c
void __fastcall CDynamicCountedObjectArray::~CDynamicCountedObjectArray(CDynamicCountedObjectArray *this)
{
  bool v1; // zf
  void **v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CDynamicCountedObjectArray::`vftable';
  if ( !v1 )
  {
    v3 = &CReleaseCountedObjectCB::`vftable';
    CDynamicArray::Iterate(this, (struct CDynamicArrayCallback *)&v3);
  }
  CDynamicArray::~CDynamicArray(this);
}

```

## disassembly

```asm
0x180005a58  push    rbx
0x180005a5a  sub     rsp, 20h
0x180005a5e  cmp     qword ptr [rcx+18h], 0
0x180005a63  lea     rax, ??_7CDynamicCountedObjectArray@@6B@; const CDynamicCountedObjectArray::`vftable'
0x180005a6a  mov     [rcx], rax
0x180005a6d  mov     rbx, rcx
0x180005a70  jz      short loc_180005A88
0x180005a72  lea     rax, ??_7CReleaseCountedObjectCB@@6B@; const CReleaseCountedObjectCB::`vftable'
0x180005a79  lea     rdx, [rsp+28h+arg_0]; struct CDynamicArrayCallback *
0x180005a7e  mov     [rsp+28h+arg_0], rax
0x180005a83  call    ?Iterate@CDynamicArray@@QEAAHPEAVCDynamicArrayCallback@@@Z; CDynamicArray::Iterate(CDynamicArrayCallback *)
0x180005a88  mov     rcx, rbx; this
0x180005a8b  add     rsp, 20h
0x180005a8f  pop     rbx
0x180005a90  jmp     ??1CDynamicArray@@UEAA@XZ; CDynamicArray::~CDynamicArray(void)
```
