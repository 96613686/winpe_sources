# CDirectMusicSynthPort::QueryInterface(_GUID const &,void * *)

- ea: `0x180011dd0`
- end: `0x180011ee3`
- name: `?QueryInterface@CDirectMusicSynthPort@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `275`
- prototype: `__int64 __fastcall(CDirectMusicSynthPort *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ef0`
- `0x180011f10`
- `0x180011f30`
- `0x180011f50`

## callees

- `0x180011dd0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort::QueryInterface(
        CDirectMusicSynthPort *this,
        const struct _GUID *a2,
        CDirectMusicSynthPort **a3)
{
  unsigned __int64 v4; // rcx
  CDirectMusicSynthPort *v5; // rdx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPort.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPort.Data4 )
  {
    v4 = (unsigned __int64)this + 376;
LABEL_20:
    v5 = (CDirectMusicSynthPort *)(v4 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    goto LABEL_21;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPortP.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPortP.Data4 )
  {
    v4 = (unsigned __int64)this + 384;
    goto LABEL_20;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPortDownload.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPortDownload.Data4 )
  {
    v5 = this;
LABEL_21:
    *a3 = v5;
    (*(void (__fastcall **)(CDirectMusicSynthPort *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicPortPrivate.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicPortPrivate.Data4 )
  {
    v4 = (unsigned __int64)this + 392;
    goto LABEL_20;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IKsControl.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IKsControl.Data4 )
  {
    v4 = (unsigned __int64)this + 400;
    goto LABEL_20;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180011dd0  sub     rsp, 28h
0x180011dd4  mov     r9, rcx
0x180011dd7  test    r8, r8
0x180011dda  jz      loc_180011ED9
0x180011de0  mov     qword ptr [r8], 0
0x180011de7  test    rdx, rdx
0x180011dea  jz      loc_180011ED9
0x180011df0  mov     rax, [rdx]
0x180011df3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180011dfa  jnz     short loc_180011E09
0x180011dfc  mov     rax, [rdx+8]
0x180011e00  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180011e07  jz      short loc_180011E22
0x180011e09  mov     rax, [rdx]
0x180011e0c  cmp     rax, qword ptr cs:IID_IDirectMusicPort.Data1
0x180011e13  jnz     short loc_180011E2E
0x180011e15  mov     rax, [rdx+8]
0x180011e19  cmp     rax, qword ptr cs:IID_IDirectMusicPort.Data4
0x180011e20  jnz     short loc_180011E2E
0x180011e22  add     rcx, 178h
0x180011e29  jmp     loc_180011EB0
0x180011e2e  mov     rax, [rdx]
0x180011e31  cmp     rax, qword ptr cs:IID_IDirectMusicPortP.Data1
0x180011e38  jnz     short loc_180011E50
0x180011e3a  mov     rax, [rdx+8]
0x180011e3e  cmp     rax, qword ptr cs:IID_IDirectMusicPortP.Data4
0x180011e45  jnz     short loc_180011E50
0x180011e47  add     rcx, 180h
0x180011e4e  jmp     short loc_180011EB0
0x180011e50  mov     rax, [rdx]
0x180011e53  cmp     rax, qword ptr cs:IID_IDirectMusicPortDownload.Data1
0x180011e5a  jnz     short loc_180011E6E
0x180011e5c  mov     rax, [rdx+8]
0x180011e60  cmp     rax, qword ptr cs:IID_IDirectMusicPortDownload.Data4
0x180011e67  jnz     short loc_180011E6E
0x180011e69  mov     rdx, r9
0x180011e6c  jmp     short loc_180011EBC
0x180011e6e  mov     rax, [rdx]
0x180011e71  cmp     rax, qword ptr cs:IID_IDirectMusicPortPrivate.Data1
0x180011e78  jnz     short loc_180011E90
0x180011e7a  mov     rax, [rdx+8]
0x180011e7e  cmp     rax, qword ptr cs:IID_IDirectMusicPortPrivate.Data4
0x180011e85  jnz     short loc_180011E90
0x180011e87  add     rcx, 188h
0x180011e8e  jmp     short loc_180011EB0
0x180011e90  mov     rax, [rdx]
0x180011e93  cmp     rax, qword ptr cs:IID_IKsControl.Data1
0x180011e9a  jnz     short loc_180011ED2
0x180011e9c  mov     rax, [rdx+8]
0x180011ea0  cmp     rax, qword ptr cs:IID_IKsControl.Data4
0x180011ea7  jnz     short loc_180011ED2
0x180011ea9  add     rcx, 190h
0x180011eb0  mov     rax, r9
0x180011eb3  neg     rax
0x180011eb6  sbb     rdx, rdx
0x180011eb9  and     rdx, rcx
0x180011ebc  mov     [r8], rdx
0x180011ebf  mov     rcx, r9
0x180011ec2  mov     rax, [r9]
0x180011ec5  mov     rax, [rax+8]
0x180011ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ece  xor     eax, eax
0x180011ed0  jmp     short loc_180011EDE
0x180011ed2  mov     eax, 80004002h
0x180011ed7  jmp     short loc_180011EDE
0x180011ed9  mov     eax, 80004003h
0x180011ede  add     rsp, 28h
0x180011ee2  retn
```
