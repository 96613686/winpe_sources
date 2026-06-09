# CDSLink::`scalar deleting destructor'(uint)

- ea: `0x18000e4d0`
- end: `0x18000e5ae`
- name: `??_GCDSLink@@QEAAPEAXI@Z`
- size: `222`
- prototype: `void *__fastcall(CDSLink *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e7c0`
- `0x180010100`
- `0x180010140`

## callees

- `0x180001514`
- `0x18000e4d0`
- `0x18000f650`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e507`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e507`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e586`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e531`

## pseudocode

```c
CDSLink *__fastcall CDSLink::`scalar deleting destructor'(CDSLink *this)
{
  bool v1; // zf
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v1 = *((_DWORD *)this + 44) == 0;
  *(_QWORD *)this = &CDSLink::`vftable'{for `IDirectMusicSynthSink'};
  *((_QWORD *)this + 1) = &CDSLink::`vftable'{for `IKsControl'};
  if ( !v1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    v3 = *((_QWORD *)this + 7);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *((_QWORD *)this + 7) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    CDSLink::Disconnect(this);
    v4 = *((_QWORD *)this + 16);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)this + 16) = 0;
    }
    v5 = *((_QWORD *)this + 13);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *((_QWORD *)this + 13) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  }
  _InterlockedDecrement(&g_cComponent);
  operator delete(this, 0xE8u);
  return this;
}

```

## disassembly

```asm
0x18000e4d0  push    rbx
0x18000e4d2  sub     rsp, 20h
0x18000e4d6  cmp     dword ptr [rcx+0B0h], 0
0x18000e4dd  lea     rax, ??_7CDSLink@@6BIDirectMusicSynthSink@@@; const CDSLink::`vftable'{for `IDirectMusicSynthSink'}
0x18000e4e4  mov     [rcx], rax
0x18000e4e7  mov     rbx, rcx
0x18000e4ea  lea     rax, ??_7CDSLink@@6BIKsControl@@@; const CDSLink::`vftable'{for `IKsControl'}
0x18000e4f1  mov     [rcx+8], rax
0x18000e4f5  jz      loc_18000E591
0x18000e4fb  add     rcx, 88h; lpCriticalSection
0x18000e502  mov     [rsp+28h+arg_0], rdi
0x18000e507  call    cs:__imp_EnterCriticalSection
0x18000e50d  mov     rcx, [rbx+38h]
0x18000e511  test    rcx, rcx
0x18000e514  jz      short loc_18000E52A
0x18000e516  mov     rax, [rcx]
0x18000e519  mov     rax, [rax+10h]
0x18000e51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e522  mov     qword ptr [rbx+38h], 0
0x18000e52a  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000e531  call    cs:__imp_LeaveCriticalSection
0x18000e537  mov     rcx, rbx; this
0x18000e53a  call    ?Disconnect@CDSLink@@AEAAJXZ; CDSLink::Disconnect(void)
0x18000e53f  mov     rcx, [rbx+80h]
0x18000e546  test    rcx, rcx
0x18000e549  jz      short loc_18000E562
0x18000e54b  mov     rax, [rcx]
0x18000e54e  mov     rax, [rax+10h]
0x18000e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e557  mov     qword ptr [rbx+80h], 0
0x18000e562  mov     rcx, [rbx+68h]
0x18000e566  test    rcx, rcx
0x18000e569  jz      short loc_18000E57F
0x18000e56b  mov     rax, [rcx]
0x18000e56e  mov     rax, [rax+10h]
0x18000e572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e577  mov     qword ptr [rbx+68h], 0
0x18000e57f  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000e586  call    cs:__imp_DeleteCriticalSection
0x18000e58c  mov     rdi, [rsp+28h+arg_0]
0x18000e591  lock dec cs:?g_cComponent@@3JA; long g_cComponent
0x18000e598  mov     edx, 0E8h; unsigned __int64
0x18000e59d  mov     rcx, rbx; void *
0x18000e5a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e5a5  mov     rax, rbx
0x18000e5a8  add     rsp, 20h
0x18000e5ac  pop     rbx
0x18000e5ad  retn
```
