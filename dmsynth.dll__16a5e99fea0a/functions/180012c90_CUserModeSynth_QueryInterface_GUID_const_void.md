# CUserModeSynth::QueryInterface(_GUID const &,void * *)

- ea: `0x180012c90`
- end: `0x180012d6d`
- name: `?QueryInterface@CUserModeSynth@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(CUserModeSynth *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e6f0`
- `0x180012d80`
- `0x180012d90`

## callees

- `0x180012c90`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CUserModeSynth::QueryInterface(CUserModeSynth *this, const struct _GUID *a2, void **a3)
{
  CUserModeSynth *v3; // r9

  v3 = this;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicSynth.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicSynth.Data4 )
  {
    goto LABEL_17;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IKsControl.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IKsControl.Data4 )
  {
    this = (CUserModeSynth *)((char *)this + 16);
    goto LABEL_15;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicSynth8.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicSynth8.Data4 )
  {
    goto LABEL_17;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectSoundSource.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectSoundSource.Data4 )
  {
    this = (CUserModeSynth *)((char *)this + 8);
LABEL_15:
    if ( !v3 )
      this = 0;
LABEL_17:
    *a3 = this;
    (*(void (__fastcall **)(CUserModeSynth *))(*(_QWORD *)v3 + 8LL))(v3);
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x180012c90  sub     rsp, 28h
0x180012c94  mov     r9, rcx
0x180012c97  test    r8, r8
0x180012c9a  jz      loc_180012D63
0x180012ca0  mov     qword ptr [r8], 0
0x180012ca7  test    rdx, rdx
0x180012caa  jz      loc_180012D63
0x180012cb0  mov     rax, [rdx]
0x180012cb3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180012cba  jnz     short loc_180012CC9
0x180012cbc  mov     rax, [rdx+8]
0x180012cc0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180012cc7  jz      short loc_180012D40
0x180012cc9  mov     rax, [rdx]
0x180012ccc  cmp     rax, qword ptr cs:IID_IDirectMusicSynth.Data1
0x180012cd3  jnz     short loc_180012CE2
0x180012cd5  mov     rax, [rdx+8]
0x180012cd9  cmp     rax, qword ptr cs:IID_IDirectMusicSynth.Data4
0x180012ce0  jz      short loc_180012D40
0x180012ce2  mov     rax, [rdx]
0x180012ce5  cmp     rax, qword ptr cs:IID_IKsControl.Data1
0x180012cec  jnz     short loc_180012D01
0x180012cee  mov     rax, [rdx+8]
0x180012cf2  cmp     rax, qword ptr cs:IID_IKsControl.Data4
0x180012cf9  jnz     short loc_180012D01
0x180012cfb  add     rcx, 10h
0x180012cff  jmp     short loc_180012D37
0x180012d01  mov     rax, [rdx]
0x180012d04  cmp     rax, qword ptr cs:IID_IDirectMusicSynth8.Data1
0x180012d0b  jnz     short loc_180012D1A
0x180012d0d  mov     rax, [rdx+8]
0x180012d11  cmp     rax, qword ptr cs:IID_IDirectMusicSynth8.Data4
0x180012d18  jz      short loc_180012D40
0x180012d1a  mov     rax, [rdx]
0x180012d1d  cmp     rax, qword ptr cs:IID_IDirectSoundSource.Data1
0x180012d24  jnz     short loc_180012D59
0x180012d26  mov     rax, [rdx+8]
0x180012d2a  cmp     rax, qword ptr cs:IID_IDirectSoundSource.Data4
0x180012d31  jnz     short loc_180012D59
0x180012d33  add     rcx, 8
0x180012d37  xor     eax, eax
0x180012d39  test    r9, r9
0x180012d3c  cmovz   rcx, rax
0x180012d40  mov     [r8], rcx
0x180012d43  mov     rcx, r9
0x180012d46  mov     rax, [r9]
0x180012d49  mov     rax, [rax+8]
0x180012d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d52  xor     eax, eax
0x180012d54  add     rsp, 28h
0x180012d58  retn
0x180012d59  mov     eax, 80004002h
0x180012d5e  add     rsp, 28h
0x180012d62  retn
0x180012d63  mov     eax, 80004003h
0x180012d68  add     rsp, 28h
0x180012d6c  retn
```
