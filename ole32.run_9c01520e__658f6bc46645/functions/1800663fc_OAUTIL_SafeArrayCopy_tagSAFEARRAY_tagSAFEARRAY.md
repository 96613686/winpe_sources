# OAUTIL::SafeArrayCopy(tagSAFEARRAY *,tagSAFEARRAY * *)

- ea: `0x1800663fc`
- end: `0x1800665a9`
- name: `?SafeArrayCopy@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@PEAPEAU2@@Z`
- size: `429`
- prototype: `HRESULT __fastcall(OAUTIL *this, tagSAFEARRAY *psa, tagSAFEARRAY **ppsaOut)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180066b74`
- `0x180067884`
- `0x180069010`

## callees

- `0x1800663fc`
- `0x1800665b0`
- `0x1800668ac`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1800664e9`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1800664e9`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006654c`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006654c`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x180066457`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x1800664a0`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x1800664d4`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x180066457`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x1800664a0`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x1800664d4`

## pseudocode

```c
__int64 __fastcall OAUTIL::SafeArrayCopy(OAUTIL *this, tagSAFEARRAY *psa, tagSAFEARRAY **ppsaOut)
{
  unsigned int v3; // ebx
  unsigned __int16 fFeatures; // ax
  tagSAFEARRAYBOUND v8; // rcx
  HRESULT v9; // eax
  tagSAFEARRAY *v10; // rdx
  tagSAFEARRAY *psaNew; // [rsp+50h] [rbp+30h] BYREF

  v3 = 0;
  psaNew = 0;
  if ( !ppsaOut )
    return (unsigned int)-2147024809;
  *ppsaOut = 0;
  if ( !psa )
    return v3;
  fFeatures = psa->fFeatures;
  if ( (fFeatures & 0xE0) == 0 )
  {
    v9 = SafeArrayAllocDescriptor(psa->cDims, &psaNew);
LABEL_15:
    v3 = v9;
    if ( v9 )
      goto LABEL_19;
    goto LABEL_16;
  }
  if ( (fFeatures & 0x20) != 0 )
  {
    v3 = SafeArrayAllocDescriptorEx(0x24u, psa->cDims, &psaNew);
    if ( v3 )
      goto LABEL_19;
    psaNew[-1].rgsabound[0] = psa[-1].rgsabound[0];
    v8 = psa[-1].rgsabound[0];
    if ( v8 )
      (*(void (__fastcall **)(tagSAFEARRAYBOUND))(**(_QWORD **)&v8 + 8LL))(v8);
    goto LABEL_16;
  }
  if ( (fFeatures & 0x40) != 0 )
  {
    v3 = SafeArrayAllocDescriptorEx(0xDu, psa->cDims, &psaNew);
    if ( v3 )
      goto LABEL_19;
    *(_OWORD *)&psaNew[-1].pvData = *(_OWORD *)&psa[-1].pvData;
    goto LABEL_16;
  }
  if ( (fFeatures & 0x80u) != 0 )
  {
    v9 = SafeArrayAllocDescriptorEx(psa[-1].rgsabound[0].lLbound, psa->cDims, &psaNew);
    goto LABEL_15;
  }
LABEL_16:
  psaNew->cLocks = 0;
  psaNew->cDims = psa->cDims;
  psaNew->fFeatures = psa->fFeatures & 0xEFE8;
  psaNew->cbElements = psa->cbElements;
  memcpy_0(psaNew->rgsabound, psa->rgsabound, 8LL * psa->cDims);
  v3 = SafeArrayAllocData(psaNew);
  if ( !v3 )
  {
    v3 = OAUTIL::SafeArrayCopyData(this, psa, psaNew);
    if ( !v3 )
    {
      v10 = 0;
      *ppsaOut = psaNew;
      psaNew = 0;
      goto LABEL_20;
    }
  }
LABEL_19:
  v10 = psaNew;
LABEL_20:
  if ( v10 )
    OAUTIL::SafeArrayDestroy(this, v10);
  return v3;
}

```

## disassembly

```asm
0x1800663fc  mov     [rsp-18h+arg_0], rbx
0x180066401  mov     [rsp-18h+arg_8], rsi
0x180066406  push    rbp
0x180066407  push    rdi
0x180066408  push    r14
0x18006640a  mov     rbp, rsp
0x18006640d  sub     rsp, 20h
0x180066411  xor     ebx, ebx
0x180066413  mov     rsi, ppsaOut
0x180066416  and     [rbp+psaNew], rbx
0x18006641a  mov     rdi, psa
0x18006641d  mov     r14, this
0x180066420  test    ppsaOut, ppsaOut
0x180066423  jnz     short loc_18006642F
0x180066425  mov     ebx, 80070057h
0x18006642a  jmp     loc_180066593
0x18006642f  and     [ppsaOut], rbx
0x180066432  test    rdi, rdi
0x180066435  jz      loc_180066593
0x18006643b  movzx   eax, word ptr [psa+2]
0x18006643f  test    al, 0E0h
0x180066441  jz      loc_1800664E2
0x180066447  test    al, 20h
0x180066449  jz      short loc_180066490
0x18006644b  movzx   edx, word ptr [psa]; cDims
0x18006644e  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x180066452  mov     ecx, 24h ; '$'; vt
0x180066457  call    cs:__imp_SafeArrayAllocDescriptorEx
0x18006645e  nop     dword ptr [rax+rax+00h]
0x180066463  mov     ebx, eax
0x180066465  test    eax, eax
0x180066467  jnz     loc_180066582
0x18006646d  mov     this, [rdi-8]
0x180066471  mov     rax, [rbp+psaNew]
0x180066475  mov     [rax-8], this
0x180066479  mov     this, [rdi-8]
0x18006647d  test    this, this
0x180066480  jz      short loc_1800664FF
0x180066482  mov     rax, [this]
0x180066485  mov     rax, [rax+8]
0x180066489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006648e  jmp     short loc_1800664FF
0x180066490  test    al, 40h
0x180066492  jz      short loc_1800664C5
0x180066494  movzx   edx, word ptr [psa]; cDims
0x180066497  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x18006649b  mov     ecx, 0Dh; vt
0x1800664a0  call    cs:__imp_SafeArrayAllocDescriptorEx
0x1800664a7  nop     dword ptr [rax+rax+00h]
0x1800664ac  mov     ebx, eax
0x1800664ae  test    eax, eax
0x1800664b0  jnz     loc_180066582
0x1800664b6  mov     rax, [rbp+psaNew]
0x1800664ba  movups  xmm0, xmmword ptr [rdi-10h]
0x1800664be  movdqu  xmmword ptr [rax-10h], xmm0
0x1800664c3  jmp     short loc_1800664FF
0x1800664c5  test    al, al
0x1800664c7  jns     short loc_1800664FF
0x1800664c9  movzx   edx, word ptr [psa]; cDims
0x1800664cc  lea     ppsaOut, [rbp+psaNew]; ppsaOut
0x1800664d0  movzx   ecx, word ptr [rdi-4]; vt
0x1800664d4  call    cs:__imp_SafeArrayAllocDescriptorEx
0x1800664db  nop     dword ptr [rax+rax+00h]
0x1800664e0  jmp     short loc_1800664F5
0x1800664e2  movzx   ecx, word ptr [psa]; cDims
0x1800664e5  lea     psa, [rbp+psaNew]; ppsaOut
0x1800664e9  call    cs:__imp_SafeArrayAllocDescriptor
0x1800664f0  nop     dword ptr [rax+rax+00h]
0x1800664f5  mov     ebx, eax
0x1800664f7  test    eax, eax
0x1800664f9  jnz     loc_180066582
0x1800664ff  mov     rax, [rbp+psaNew]
0x180066503  lea     psa, [rdi+18h]; Src
0x180066507  and     dword ptr [rax+8], 0
0x18006650b  movzx   ecx, word ptr [rdi]
0x18006650e  mov     rax, [rbp+psaNew]
0x180066512  mov     [rax], cx
0x180066515  mov     eax, 0EFE8h
0x18006651a  movzx   ecx, word ptr [rdi+2]
0x18006651e  and     cx, ax
0x180066521  mov     rax, [rbp+psaNew]
0x180066525  mov     [rax+2], cx
0x180066529  mov     ecx, [rdi+4]
0x18006652c  mov     rax, [rbp+psaNew]
0x180066530  mov     [rax+4], ecx
0x180066533  movzx   r8d, word ptr [rdi]
0x180066537  mov     this, [rbp+psaNew]
0x18006653b  shl     ppsaOut, 3; Size
0x18006653f  add     this, 18h; void *
0x180066543  call    memcpy_0
0x180066548  mov     this, [rbp+psaNew]; psa
0x18006654c  call    cs:__imp_SafeArrayAllocData
0x180066553  nop     dword ptr [rax+rax+00h]
0x180066558  mov     ebx, eax
0x18006655a  test    eax, eax
0x18006655c  jnz     short loc_180066582
0x18006655e  mov     ppsaOut, [rbp+psaNew]; psaTarget
0x180066562  mov     psa, rdi; psaSource
0x180066565  mov     this, r14; this
0x180066568  call    ?SafeArrayCopyData@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@0@Z; OAUTIL::SafeArrayCopyData(tagSAFEARRAY *,tagSAFEARRAY *)
0x18006656d  mov     ebx, eax
0x18006656f  test    eax, eax
0x180066571  jnz     short loc_180066582
0x180066573  mov     rax, [rbp+psaNew]
0x180066577  xor     edx, edx
0x180066579  mov     [rsi], rax
0x18006657c  mov     [rbp+psaNew], psa
0x180066580  jmp     short loc_180066586
0x180066582  mov     psa, [rbp+psaNew]; psa
0x180066586  test    psa, psa
0x180066589  jz      short loc_180066593
0x18006658b  mov     this, r14; this
0x18006658e  call    ?SafeArrayDestroy@OAUTIL@@QEAAJPEAUtagSAFEARRAY@@@Z; OAUTIL::SafeArrayDestroy(tagSAFEARRAY *)
0x180066593  mov     rsi, [rsp+20h+arg_8]
0x180066598  mov     eax, ebx
0x18006659a  mov     rbx, [rsp+20h+arg_0]
0x18006659f  add     rsp, 20h
0x1800665a3  pop     r14
0x1800665a5  pop     rdi
0x1800665a6  pop     rbp
0x1800665a7  retn
```
