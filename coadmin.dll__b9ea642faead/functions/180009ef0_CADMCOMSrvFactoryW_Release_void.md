# CADMCOMSrvFactoryW::Release(void)

- ea: `0x180009ef0`
- end: `0x180009f26`
- name: `?Release@CADMCOMSrvFactoryW@@UEAAKXZ`
- size: `54`
- prototype: `unsigned int __fastcall(CADMCOMSrvFactoryW *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010a4`
- `0x180009ef0`

## pseudocode

```c
__int64 __fastcall CADMCOMSrvFactoryW::Release(CADMCOMSrvFactoryW *this)
{
  signed __int32 v1; // ebx
  unsigned __int32 v2; // ebx

  v1 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
  _InterlockedDecrement((volatile signed __int32 *)&g_dwRefCount);
  v2 = v1 - 1;
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CADMCOMSrvFactoryW::`vftable';
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180009ef0  push    rbx
0x180009ef2  sub     rsp, 20h
0x180009ef6  or      ebx, 0FFFFFFFFh
0x180009ef9  lock xadd [rcx+8], ebx
0x180009efe  lock dec cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180009f05  sub     ebx, 1
0x180009f08  jnz     short loc_180009F1E
0x180009f0a  test    rcx, rcx
0x180009f0d  jz      short loc_180009F1E
0x180009f0f  lea     rax, ??_7CADMCOMSrvFactoryW@@6B@; const CADMCOMSrvFactoryW::`vftable'
0x180009f16  mov     [rcx], rax
0x180009f19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f1e  mov     eax, ebx
0x180009f20  add     rsp, 20h
0x180009f24  pop     rbx
0x180009f25  retn
```
