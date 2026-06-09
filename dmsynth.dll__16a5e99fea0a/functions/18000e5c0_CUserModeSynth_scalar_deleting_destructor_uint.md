# CUserModeSynth::`scalar deleting destructor'(uint)

- ea: `0x18000e5c0`
- end: `0x18000e6c0`
- name: `??_GCUserModeSynth@@QEAAPEAXI@Z`
- size: `256`
- prototype: `void *__fastcall(CUserModeSynth *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e6f0`
- `0x180013020`

## callees

- `0x180001514`
- `0x180006030`
- `0x18000e5c0`
- `0x1800114b0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e698`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e68e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e68e`

## pseudocode

```c
CUserModeSynth *__fastcall CUserModeSynth::`scalar deleting destructor'(CUserModeSynth *this)
{
  bool v1; // zf
  CSynth *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  CSynth *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  v1 = *((_DWORD *)this + 16) == 0;
  *(_QWORD *)this = &CUserModeSynth::`vftable'{for `IDirectMusicSynth8'};
  *((_QWORD *)this + 1) = &CUserModeSynth::`vftable'{for `IDirectSoundSource'};
  *((_QWORD *)this + 2) = &CUserModeSynth::`vftable'{for `IKsControl'};
  if ( !v1 )
  {
    *((_DWORD *)this + 16) = 0;
    v3 = (CSynth *)*((_QWORD *)this + 7);
    if ( v3 )
      CSynth::AllNotesOff(v3);
    v4 = *((_QWORD *)this + 5);
    if ( v4 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, 0);
    v5 = *((_QWORD *)this + 6);
    if ( v5 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, 0);
  }
  if ( *((_DWORD *)this + 34) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v6 = (CSynth *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      CSynth::`scalar deleting destructor'(v6);
      *((_QWORD *)this + 7) = 0;
    }
    v7 = *((_QWORD *)this + 5);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = *((_QWORD *)this + 6);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  }
  _InterlockedDecrement(&g_cComponent);
  operator delete(this, 0x90u);
  return this;
}

```

## disassembly

```asm
0x18000e5c0  push    rbx
0x18000e5c2  sub     rsp, 20h
0x18000e5c6  cmp     dword ptr [rcx+40h], 0
0x18000e5ca  lea     rax, ??_7CUserModeSynth@@6BIDirectMusicSynth8@@@; const CUserModeSynth::`vftable'{for `IDirectMusicSynth8'}
0x18000e5d1  mov     [rcx], rax
0x18000e5d4  mov     rbx, rcx
0x18000e5d7  lea     rax, ??_7CUserModeSynth@@6BIDirectSoundSource@@@; const CUserModeSynth::`vftable'{for `IDirectSoundSource'}
0x18000e5de  mov     [rcx+8], rax
0x18000e5e2  lea     rax, ??_7CUserModeSynth@@6BIKsControl@@@; const CUserModeSynth::`vftable'{for `IKsControl'}
0x18000e5e9  mov     [rcx+10h], rax
0x18000e5ed  jz      short loc_18000E632
0x18000e5ef  mov     dword ptr [rcx+40h], 0
0x18000e5f6  mov     rcx, [rcx+38h]; this
0x18000e5fa  test    rcx, rcx
0x18000e5fd  jz      short loc_18000E604
0x18000e5ff  call    ?AllNotesOff@CSynth@@QEAAJXZ; CSynth::AllNotesOff(void)
0x18000e604  mov     rcx, [rbx+28h]
0x18000e608  test    rcx, rcx
0x18000e60b  jz      short loc_18000E61B
0x18000e60d  mov     rax, [rcx]
0x18000e610  xor     edx, edx
0x18000e612  mov     rax, [rax+30h]
0x18000e616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61b  mov     rcx, [rbx+30h]
0x18000e61f  test    rcx, rcx
0x18000e622  jz      short loc_18000E632
0x18000e624  mov     rax, [rcx]
0x18000e627  xor     edx, edx
0x18000e629  mov     rax, [rax+20h]
0x18000e62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e632  cmp     dword ptr [rbx+88h], 0
0x18000e639  jz      short loc_18000E6A3
0x18000e63b  lea     rcx, [rbx+60h]; lpCriticalSection
0x18000e63f  mov     [rsp+28h+arg_0], rdi
0x18000e644  call    cs:__imp_EnterCriticalSection
0x18000e64a  mov     rcx, [rbx+38h]; this
0x18000e64e  test    rcx, rcx
0x18000e651  jz      short loc_18000E660
0x18000e653  call    ??_GCSynth@@QEAAPEAXI@Z; CSynth::`scalar deleting destructor'(uint)
0x18000e658  mov     qword ptr [rbx+38h], 0
0x18000e660  mov     rcx, [rbx+28h]
0x18000e664  test    rcx, rcx
0x18000e667  jz      short loc_18000E675
0x18000e669  mov     rax, [rcx]
0x18000e66c  mov     rax, [rax+10h]
0x18000e670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e675  mov     rcx, [rbx+30h]
0x18000e679  test    rcx, rcx
0x18000e67c  jz      short loc_18000E68A
0x18000e67e  mov     rax, [rcx]
0x18000e681  mov     rax, [rax+10h]
0x18000e685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e68a  lea     rcx, [rbx+60h]; lpCriticalSection
0x18000e68e  call    cs:__imp_LeaveCriticalSection
0x18000e694  lea     rcx, [rbx+60h]; lpCriticalSection
0x18000e698  call    cs:__imp_DeleteCriticalSection
0x18000e69e  mov     rdi, [rsp+28h+arg_0]
0x18000e6a3  lock dec cs:?g_cComponent@@3JA; long g_cComponent
0x18000e6aa  mov     edx, 90h; unsigned __int64
0x18000e6af  mov     rcx, rbx; void *
0x18000e6b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e6b7  mov     rax, rbx
0x18000e6ba  add     rsp, 20h
0x18000e6be  pop     rbx
0x18000e6bf  retn
```
