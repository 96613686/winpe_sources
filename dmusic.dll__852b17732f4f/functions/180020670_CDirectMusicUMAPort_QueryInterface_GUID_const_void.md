# CDirectMusicUMAPort::QueryInterface(_GUID const &,void * *)

- ea: `0x180020670`
- end: `0x180020762`
- name: `?QueryInterface@CDirectMusicUMAPort@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `242`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180020770`
- `0x180020790`
- `0x1800207b0`
- `0x1800207d0`
- `0x1800207f0`

## callees

- `0x180020670`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::QueryInterface(CDirectMusicUMAPort *this, const struct _GUID *a2, void **a3)
{
  unsigned __int64 v4; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPort.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPort.Data4 )
  {
    v4 = (unsigned __int64)this + 384;
LABEL_17:
    *a3 = (void *)(v4 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    (*(void (__fastcall **)(CDirectMusicUMAPort *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPortPrivate.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPortPrivate.Data4 )
  {
    v4 = (unsigned __int64)this + 400;
    goto LABEL_17;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IKsControl.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IKsControl.Data4 )
  {
    v4 = (unsigned __int64)this + 408;
    goto LABEL_17;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicThru.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicThru.Data4 )
  {
    v4 = (unsigned __int64)this + 376;
    goto LABEL_17;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180020670  sub     rsp, 28h
0x180020674  mov     r9, rcx
0x180020677  test    r8, r8
0x18002067a  jz      loc_180020758
0x180020680  mov     qword ptr [r8], 0
0x180020687  test    rdx, rdx
0x18002068a  jz      loc_180020758
0x180020690  mov     rax, [rdx]
0x180020693  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18002069a  jnz     short loc_1800206A9
0x18002069c  mov     rax, [rdx+8]
0x1800206a0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800206a7  jz      short loc_1800206C2
0x1800206a9  mov     rax, [rdx]
0x1800206ac  cmp     rax, qword ptr cs:IID_IDirectMusicPort.Data1
0x1800206b3  jnz     short loc_1800206CB
0x1800206b5  mov     rax, [rdx+8]
0x1800206b9  cmp     rax, qword ptr cs:IID_IDirectMusicPort.Data4
0x1800206c0  jnz     short loc_1800206CB
0x1800206c2  add     rcx, 180h
0x1800206c9  jmp     short loc_18002072F
0x1800206cb  mov     rax, [rdx]
0x1800206ce  cmp     rax, qword ptr cs:IID_IDirectMusicPortPrivate.Data1
0x1800206d5  jnz     short loc_1800206ED
0x1800206d7  mov     rax, [rdx+8]
0x1800206db  cmp     rax, qword ptr cs:IID_IDirectMusicPortPrivate.Data4
0x1800206e2  jnz     short loc_1800206ED
0x1800206e4  add     rcx, 190h
0x1800206eb  jmp     short loc_18002072F
0x1800206ed  mov     rax, [rdx]
0x1800206f0  cmp     rax, qword ptr cs:IID_IKsControl.Data1
0x1800206f7  jnz     short loc_18002070F
0x1800206f9  mov     rax, [rdx+8]
0x1800206fd  cmp     rax, qword ptr cs:IID_IKsControl.Data4
0x180020704  jnz     short loc_18002070F
0x180020706  add     rcx, 198h
0x18002070d  jmp     short loc_18002072F
0x18002070f  mov     rax, [rdx]
0x180020712  cmp     rax, qword ptr cs:IID_IDirectMusicThru.Data1
0x180020719  jnz     short loc_180020751
0x18002071b  mov     rax, [rdx+8]
0x18002071f  cmp     rax, qword ptr cs:IID_IDirectMusicThru.Data4
0x180020726  jnz     short loc_180020751
0x180020728  add     rcx, 178h
0x18002072f  mov     rax, r9
0x180020732  neg     rax
0x180020735  sbb     rdx, rdx
0x180020738  and     rdx, rcx
0x18002073b  mov     rcx, r9
0x18002073e  mov     [r8], rdx
0x180020741  mov     rax, [r9]
0x180020744  mov     rax, [rax+8]
0x180020748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002074d  xor     eax, eax
0x18002074f  jmp     short loc_18002075D
0x180020751  mov     eax, 80004002h
0x180020756  jmp     short loc_18002075D
0x180020758  mov     eax, 80004003h
0x18002075d  add     rsp, 28h
0x180020761  retn
```
