# Pku2uUnsealMessage

- ea: `0x140029780`
- end: `0x140029865`
- name: `Pku2uUnsealMessage`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140007008`
- `0x140029780`
- `0x140029d94`
- `0x140029f3c`
- `0x14002ae10`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400297c1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400297c1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400297ed`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400297ed`

## string_xrefs

- `0x140029826`: `Invalid handle supplied for GetContextToken(0x%x)\n`

## pseudocode

```c
__int64 __fastcall Pku2uUnsealMessage(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  void *v10; // rdi

  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uUnsealMessage Called\n");
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
      v8 = WSTUnsealMessage(v9, a2, a3, a4);
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
0x140029780  push    rbx
0x140029782  push    rbp
0x140029783  push    rsi
0x140029784  push    rdi
0x140029785  push    r14
0x140029787  sub     rsp, 20h
0x14002978b  cmp     cs:KsecInfoLevel, 0
0x140029792  mov     rsi, r9
0x140029795  mov     ebp, r8d
0x140029798  mov     r14, rdx
0x14002979b  mov     rbx, rcx
0x14002979e  jz      short loc_1400297B1
0x1400297a0  lea     rdx, aPku2uunsealmes; "Pku2uUnsealMessage Called\n"
0x1400297a7  mov     ecx, 4
0x1400297ac  call    KsecDebugOut
0x1400297b1  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400297b8  jnz     short loc_140029809
0x1400297ba  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400297c1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400297c8  nop     dword ptr [rax+rax+00h]
0x1400297cd  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400297d4  jnz     short loc_1400297E6
0x1400297d6  call    LibAttach
0x1400297db  test    eax, eax
0x1400297dd  jz      short loc_1400297E6
0x1400297df  mov     cs:?Pku2uCryptInitialized@@3EA, 1; uchar Pku2uCryptInitialized
0x1400297e6  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400297ed  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400297f4  nop     dword ptr [rax+rax+00h]
0x1400297f9  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140029800  jnz     short loc_140029809
0x140029802  mov     ebx, 0C000009Ah
0x140029807  jmp     short loc_140029857
0x140029809  xor     edx, edx
0x14002980b  mov     rcx, rbx
0x14002980e  call    Pku2uReferenceContext
0x140029813  mov     rdi, rax
0x140029816  test    rax, rax
0x140029819  jnz     short loc_14002983C
0x14002981b  cmp     cs:KsecInfoLevel, eax
0x140029821  jz      short loc_140029835
0x140029823  mov     r8, rbx
0x140029826  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x14002982d  lea     ecx, [rax+1]
0x140029830  call    KsecDebugOut
0x140029835  mov     ebx, 0C0000008h
0x14002983a  jmp     short loc_140029857
0x14002983c  mov     r9, rsi
0x14002983f  mov     r8d, ebp
0x140029842  mov     rdx, r14
0x140029845  mov     rcx, rdi
0x140029848  call    WSTUnsealMessage
0x14002984d  mov     ebx, eax
0x14002984f  mov     rcx, rdi; P
0x140029852  call    Pku2uDereferenceContext
0x140029857  mov     eax, ebx
0x140029859  add     rsp, 20h
0x14002985d  pop     r14
0x14002985f  pop     rdi
0x140029860  pop     rsi
0x140029861  pop     rbp
0x140029862  pop     rbx
0x140029863  retn
```
