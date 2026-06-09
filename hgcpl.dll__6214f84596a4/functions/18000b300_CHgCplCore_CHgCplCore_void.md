# CHgCplCore::~CHgCplCore(void)

- ea: `0x18000b300`
- end: `0x18000b39b`
- name: `??1CHgCplCore@@EEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CHgCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000b3b0`

## callees

- `0x18000b280`
- `0x18000b2e4`
- `0x18000b300`
- `0x18000bd88`
- `0x18001a010`

## import_xrefs

- `DUser!DeleteHandle` at `0x18000b344`
- `DUser!DeleteHandle` at `0x18000b344`

## pseudocode

```c
void __fastcall CHgCplCore::~CHgCplCore(CHgCplCore *this)
{
  __int64 v2; // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  char *v4; // rbx

  *(_QWORD *)this = &CHgCplCore::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, *((unsigned int *)this + 16));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7));
  }
  if ( *((_QWORD *)this + 9) )
  {
    DeleteHandle();
    *((_QWORD *)this + 9) = 0;
  }
  SafeRelease<IUnknown>((char *)this + 16);
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v3 )
    (**v3)(v3, 1);
  v4 = (char *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v4 + 8);
    operator delete(v4);
  }
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x18000b300  push    rbx
0x18000b302  sub     rsp, 20h
0x18000b306  lea     rax, ??_7CHgCplCore@@6B@; const CHgCplCore::`vftable'
0x18000b30d  mov     rbx, rcx
0x18000b310  mov     [rcx], rax
0x18000b313  mov     rcx, [rcx+38h]
0x18000b317  test    rcx, rcx
0x18000b31a  jz      short loc_18000B33B
0x18000b31c  mov     rax, [rcx]
0x18000b31f  mov     edx, [rbx+40h]
0x18000b322  mov     rax, [rax+20h]
0x18000b326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32b  mov     rcx, [rbx+38h]
0x18000b32f  mov     rax, [rcx]
0x18000b332  mov     rax, [rax+10h]
0x18000b336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33b  mov     rcx, [rbx+48h]
0x18000b33f  test    rcx, rcx
0x18000b342  jz      short loc_18000B352
0x18000b344  call    cs:__imp_DeleteHandle
0x18000b34a  mov     qword ptr [rbx+48h], 0
0x18000b352  lea     rcx, [rbx+10h]
0x18000b356  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18000b35b  mov     rcx, [rbx+20h]
0x18000b35f  test    rcx, rcx
0x18000b362  jz      short loc_18000B374
0x18000b364  mov     rax, [rcx]
0x18000b367  mov     edx, 1
0x18000b36c  mov     rax, [rax]
0x18000b36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b374  mov     rbx, [rbx+28h]
0x18000b378  test    rbx, rbx
0x18000b37b  jz      short loc_18000B38E
0x18000b37d  lea     rcx, [rbx+8]
0x18000b381  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000b386  mov     rcx, rbx; lpMem
0x18000b389  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b38e  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x18000b395  add     rsp, 20h
0x18000b399  pop     rbx
0x18000b39a  retn
```
