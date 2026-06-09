# Pku2uMakeSignature

- ea: `0x1400290b0`
- end: `0x140029195`
- name: `Pku2uMakeSignature`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140007008`
- `0x1400290b0`
- `0x140029d94`
- `0x140029f3c`
- `0x140029fe4`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400290f1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400290f1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14002911d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14002911d`

## string_xrefs

- `0x140029156`: `Invalid handle supplied for GetContextToken(0x%x)\n`

## pseudocode

```c
__int64 __fastcall Pku2uMakeSignature(__int64 a1, int a2, __int64 a3, char a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  void *v10; // rdi

  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uMakeSignature Called\n");
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
      v8 = WSTMakeSignature(v9, a2, a3, a4);
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
0x1400290b0  push    rbx
0x1400290b2  push    rbp
0x1400290b3  push    rsi
0x1400290b4  push    rdi
0x1400290b5  push    r14
0x1400290b7  sub     rsp, 20h
0x1400290bb  cmp     cs:KsecInfoLevel, 0
0x1400290c2  mov     esi, r9d
0x1400290c5  mov     rbp, r8
0x1400290c8  mov     r14d, edx
0x1400290cb  mov     rbx, rcx
0x1400290ce  jz      short loc_1400290E1
0x1400290d0  lea     rdx, aPku2umakesigna; "Pku2uMakeSignature Called\n"
0x1400290d7  mov     ecx, 4
0x1400290dc  call    KsecDebugOut
0x1400290e1  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400290e8  jnz     short loc_140029139
0x1400290ea  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400290f1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400290f8  nop     dword ptr [rax+rax+00h]
0x1400290fd  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140029104  jnz     short loc_140029116
0x140029106  call    LibAttach
0x14002910b  test    eax, eax
0x14002910d  jz      short loc_140029116
0x14002910f  mov     cs:?Pku2uCryptInitialized@@3EA, 1; uchar Pku2uCryptInitialized
0x140029116  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x14002911d  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140029124  nop     dword ptr [rax+rax+00h]
0x140029129  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140029130  jnz     short loc_140029139
0x140029132  mov     ebx, 0C000009Ah
0x140029137  jmp     short loc_140029187
0x140029139  xor     edx, edx
0x14002913b  mov     rcx, rbx
0x14002913e  call    Pku2uReferenceContext
0x140029143  mov     rdi, rax
0x140029146  test    rax, rax
0x140029149  jnz     short loc_14002916C
0x14002914b  cmp     cs:KsecInfoLevel, eax
0x140029151  jz      short loc_140029165
0x140029153  mov     r8, rbx
0x140029156  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x14002915d  lea     ecx, [rax+1]
0x140029160  call    KsecDebugOut
0x140029165  mov     ebx, 0C0000008h
0x14002916a  jmp     short loc_140029187
0x14002916c  mov     r9d, esi
0x14002916f  mov     r8, rbp
0x140029172  mov     edx, r14d
0x140029175  mov     rcx, rdi
0x140029178  call    WSTMakeSignature
0x14002917d  mov     ebx, eax
0x14002917f  mov     rcx, rdi; P
0x140029182  call    Pku2uDereferenceContext
0x140029187  mov     eax, ebx
0x140029189  add     rsp, 20h
0x14002918d  pop     r14
0x14002918f  pop     rdi
0x140029190  pop     rsi
0x140029191  pop     rbp
0x140029192  pop     rbx
0x140029193  retn
```
