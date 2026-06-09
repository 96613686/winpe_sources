# Pku2uVerifySignature

- ea: `0x140029870`
- end: `0x140029955`
- name: `Pku2uVerifySignature`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140007008`
- `0x140029870`
- `0x140029d94`
- `0x140029f3c`
- `0x14002bc00`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400298b1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400298b1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400298dd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400298dd`

## string_xrefs

- `0x140029916`: `Invalid handle supplied for GetContextToken(0x%x)\n`

## pseudocode

```c
__int64 __fastcall Pku2uVerifySignature(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  void *v10; // rdi

  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uVerifySignature Called\n");
  if ( Pku2uCryptInitialized )
    goto LABEL_8;
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Pku2uGlobalResource);
  if ( !Pku2uCryptInitialized )
    Pku2uCryptInitialized = (unsigned int)LibAttach() != 0;
  ExReleaseResourceAndLeaveCriticalRegion(&Pku2uGlobalResource);
  if ( Pku2uCryptInitialized )
  {
LABEL_8:
    v9 = Pku2uReferenceContext(a1, 0);
    v10 = (void *)v9;
    if ( v9 )
    {
      v8 = WSTVerifySignature(v9, a2, a3, a4);
      Pku2uDereferenceContext(v10);
    }
    else
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "Invalid handle supplied for GetContextToken(0x%x)\n", a1);
      return (unsigned int)-1073741816;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x140029870  push    rbx
0x140029872  push    rbp
0x140029873  push    rsi
0x140029874  push    rdi
0x140029875  push    r14
0x140029877  sub     rsp, 20h
0x14002987b  cmp     cs:KsecInfoLevel, 0
0x140029882  mov     rsi, r9
0x140029885  mov     ebp, r8d
0x140029888  mov     r14, rdx
0x14002988b  mov     rbx, rcx
0x14002988e  jz      short loc_1400298A1
0x140029890  lea     rdx, aPku2uverifysig; "Pku2uVerifySignature Called\n"
0x140029897  mov     ecx, 4
0x14002989c  call    KsecDebugOut
0x1400298a1  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400298a8  jnz     short loc_1400298F9
0x1400298aa  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400298b1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400298b8  nop     dword ptr [rax+rax+00h]
0x1400298bd  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400298c4  jnz     short loc_1400298D6
0x1400298c6  call    LibAttach
0x1400298cb  test    eax, eax
0x1400298cd  jz      short loc_1400298D6
0x1400298cf  mov     cs:?Pku2uCryptInitialized@@3EA, 1; uchar Pku2uCryptInitialized
0x1400298d6  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400298dd  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400298e4  nop     dword ptr [rax+rax+00h]
0x1400298e9  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400298f0  jnz     short loc_1400298F9
0x1400298f2  mov     ebx, 0C000009Ah
0x1400298f7  jmp     short loc_140029947
0x1400298f9  xor     edx, edx
0x1400298fb  mov     rcx, rbx
0x1400298fe  call    Pku2uReferenceContext
0x140029903  mov     rdi, rax
0x140029906  test    rax, rax
0x140029909  jnz     short loc_14002992C
0x14002990b  cmp     cs:KsecInfoLevel, eax
0x140029911  jz      short loc_140029925
0x140029913  mov     r8, rbx
0x140029916  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x14002991d  lea     ecx, [rax+1]
0x140029920  call    KsecDebugOut
0x140029925  mov     ebx, 0C0000008h
0x14002992a  jmp     short loc_140029947
0x14002992c  mov     r9, rsi
0x14002992f  mov     r8d, ebp
0x140029932  mov     rdx, r14
0x140029935  mov     rcx, rdi
0x140029938  call    WSTVerifySignature
0x14002993d  mov     ebx, eax
0x14002993f  mov     rcx, rdi; P
0x140029942  call    Pku2uDereferenceContext
0x140029947  mov     eax, ebx
0x140029949  add     rsp, 20h
0x14002994d  pop     r14
0x14002994f  pop     rdi
0x140029950  pop     rsi
0x140029951  pop     rbp
0x140029952  pop     rbx
0x140029953  retn
```
