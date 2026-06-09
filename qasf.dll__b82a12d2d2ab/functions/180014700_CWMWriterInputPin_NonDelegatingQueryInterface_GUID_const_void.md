# CWMWriterInputPin::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x180014700`
- end: `0x1800147be`
- name: `?NonDelegatingQueryInterface@CWMWriterInputPin@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `190`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005530`
- `0x180014700`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::NonDelegatingQueryInterface(
        CWMWriterInputPin *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx
  void *v4; // rcx
  void (*v5)(void); // rax
  unsigned __int64 v7; // rax
  void *v8; // rcx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAMStreamConfig.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAMStreamConfig.Data4 )
  {
    v3 = 0;
    v4 = (void *)(((unsigned __int64)this + 304) & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v4;
    v5 = *(void (**)(void))(*(_QWORD *)v4 + 8LL);
LABEL_6:
    v5();
    return v3;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAMWMBufferPass.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAMWMBufferPass.Data4 )
  {
    v7 = (unsigned __int64)this + 312;
LABEL_15:
    v3 = 0;
    v8 = (void *)(v7 & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v8;
    v5 = *(void (**)(void))(*(_QWORD *)v8 + 8LL);
    goto LABEL_6;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IReferenceClock.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IReferenceClock.Data4 )
  {
    v7 = (unsigned __int64)this + 320;
    goto LABEL_15;
  }
  return CBaseInputPin::NonDelegatingQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x180014700  push    rbx
0x180014702  sub     rsp, 20h
0x180014706  mov     rax, [rdx]
0x180014709  cmp     rax, qword ptr cs:IID_IAMStreamConfig.Data1
0x180014710  jnz     short loc_180014754
0x180014712  mov     rax, [rdx+8]
0x180014716  cmp     rax, qword ptr cs:IID_IAMStreamConfig.Data4
0x18001471d  jnz     short loc_180014754
0x18001471f  lea     rax, [rcx+130h]
0x180014726  neg     rcx
0x180014729  sbb     rcx, rcx
0x18001472c  xor     ebx, ebx
0x18001472e  and     rcx, rax
0x180014731  test    r8, r8
0x180014734  jnz     short loc_18001473D
0x180014736  mov     ebx, 80004003h
0x18001473b  jmp     short loc_18001474C
0x18001473d  mov     [r8], rcx
0x180014740  mov     rdx, [rcx]
0x180014743  mov     rax, [rdx+8]
0x180014747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001474c  mov     eax, ebx
0x18001474e  add     rsp, 20h
0x180014752  pop     rbx
0x180014753  retn
0x180014754  mov     rax, [rdx]
0x180014757  cmp     rax, qword ptr cs:IID_IAMWMBufferPass.Data1
0x18001475e  jnz     short loc_180014782
0x180014760  mov     rax, [rdx+8]
0x180014764  cmp     rax, qword ptr cs:IID_IAMWMBufferPass.Data4
0x18001476b  jnz     short loc_180014782
0x18001476d  lea     rax, [rcx+138h]
0x180014774  jmp     short loc_1800147A2
0x180014776  mov     [r8], rcx
0x180014779  mov     rax, [rcx]
0x18001477c  mov     rax, [rax+8]
0x180014780  jmp     short loc_180014747
0x180014782  mov     rax, [rdx]
0x180014785  cmp     rax, qword ptr cs:IID_IReferenceClock.Data1
0x18001478c  jnz     short loc_1800147B4
0x18001478e  mov     rax, [rdx+8]
0x180014792  cmp     rax, qword ptr cs:IID_IReferenceClock.Data4
0x180014799  jnz     short loc_1800147B4
0x18001479b  lea     rax, [rcx+140h]
0x1800147a2  neg     rcx
0x1800147a5  sbb     rcx, rcx
0x1800147a8  xor     ebx, ebx
0x1800147aa  and     rcx, rax; this
0x1800147ad  test    r8, r8
0x1800147b0  jnz     short loc_180014776
0x1800147b2  jmp     short loc_180014736
0x1800147b4  add     rsp, 20h
0x1800147b8  pop     rbx
0x1800147b9  jmp     ?NonDelegatingQueryInterface@CBaseInputPin@@UEAAJAEBU_GUID@@PEAPEAX@Z; CBaseInputPin::NonDelegatingQueryInterface(_GUID const &,void * *)
```
