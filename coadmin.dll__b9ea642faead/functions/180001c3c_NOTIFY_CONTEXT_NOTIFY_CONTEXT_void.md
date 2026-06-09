# NOTIFY_CONTEXT::~NOTIFY_CONTEXT(void)

- ea: `0x180001c3c`
- end: `0x180001ce5`
- name: `??1NOTIFY_CONTEXT@@AEAA@XZ`
- size: `169`
- prototype: `void __fastcall(NOTIFY_CONTEXT *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003590`
- `0x180007c20`
- `0x1800084a0`
- `0x180008614`

## callees

- `0x180001c3c`
- `0x180009b4c`
- `0x180010010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c94`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c94`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c9c`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c9c`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c5d`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c5d`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180001c73`
- `IisRTL!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180001c73`

## pseudocode

```c
void __fastcall NOTIFY_CONTEXT::~NOTIFY_CONTEXT(NOTIFY_CONTEXT *this)
{
  __int64 v2; // rcx

  *(_DWORD *)this = 2018788174;
  *((_QWORD *)this + 6) = (char *)this + 40;
  *((_QWORD *)this + 5) = (char *)this + 40;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
  if ( this == NOTIFY_CONTEXT::s_pCurrentlyWorkingOn )
  {
    CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
    if ( this == NOTIFY_CONTEXT::s_pCurrentlyWorkingOn )
      NOTIFY_CONTEXT::s_pCurrentlyWorkingOn = 0;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
  }
  else
  {
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn);
  }
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_QWORD *)this + 3) )
    DeleteChangeObjectArray(*((unsigned int *)this + 4), (char *)this + 24);
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x180001c3c  push    rbx
0x180001c3e  sub     rsp, 20h
0x180001c42  lea     rax, [rcx+28h]
0x180001c46  mov     dword ptr [rcx], 7854434Eh
0x180001c4c  mov     rbx, rcx
0x180001c4f  mov     [rax+8], rax
0x180001c53  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x180001c5a  mov     [rax], rax
0x180001c5d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180001c63  cmp     rbx, cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x180001c6a  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x180001c71  jnz     short loc_180001C9C
0x180001c73  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180001c79  cmp     rbx, cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x180001c80  jnz     short loc_180001C8D
0x180001c82  mov     cs:?s_pCurrentlyWorkingOn@NOTIFY_CONTEXT@@0PEAV1@EA, 0; NOTIFY_CONTEXT * NOTIFY_CONTEXT::s_pCurrentlyWorkingOn
0x180001c8d  lea     rcx, ?s_LockCurrentlyWorkingOn@NOTIFY_CONTEXT@@0VCReaderWriterLock3@@A; CReaderWriterLock3 NOTIFY_CONTEXT::s_LockCurrentlyWorkingOn
0x180001c94  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001c9a  jmp     short loc_180001CA2
0x180001c9c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180001ca2  mov     rcx, [rbx+8]
0x180001ca6  test    rcx, rcx
0x180001ca9  jz      short loc_180001CBF
0x180001cab  mov     rax, [rcx]
0x180001cae  mov     rax, [rax+10h]
0x180001cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb7  mov     qword ptr [rbx+8], 0
0x180001cbf  lea     rdx, [rbx+18h]
0x180001cc3  cmp     qword ptr [rdx], 0
0x180001cc7  jz      short loc_180001CD1
0x180001cc9  mov     ecx, [rbx+10h]
0x180001ccc  call    _DeleteChangeObjectArray
0x180001cd1  mov     dword ptr [rbx+10h], 0
0x180001cd8  mov     dword ptr [rbx+20h], 0
0x180001cdf  add     rsp, 20h
0x180001ce3  pop     rbx
0x180001ce4  retn
```
