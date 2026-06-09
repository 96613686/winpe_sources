# Pku2uSealMessage

- ea: `0x140029690`
- end: `0x140029775`
- name: `Pku2uSealMessage`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140007008`
- `0x140029690`
- `0x140029d94`
- `0x140029f3c`
- `0x14002a4d8`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400296d1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400296d1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400296fd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400296fd`

## string_xrefs

- `0x140029736`: `Invalid handle supplied for GetContextToken(0x%x)\n`

## pseudocode

```c
__int64 __fastcall Pku2uSealMessage(__int64 a1, int a2, __int64 a3, char a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  void *v10; // rdi

  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uSealMessage Called\n");
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
      v8 = WSTSealMessage(v9, a2, a3, a4);
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
0x140029690  push    rbx
0x140029692  push    rbp
0x140029693  push    rsi
0x140029694  push    rdi
0x140029695  push    r14
0x140029697  sub     rsp, 20h
0x14002969b  cmp     cs:KsecInfoLevel, 0
0x1400296a2  mov     esi, r9d
0x1400296a5  mov     rbp, r8
0x1400296a8  mov     r14d, edx
0x1400296ab  mov     rbx, rcx
0x1400296ae  jz      short loc_1400296C1
0x1400296b0  lea     rdx, aPku2usealmessa; "Pku2uSealMessage Called\n"
0x1400296b7  mov     ecx, 4
0x1400296bc  call    KsecDebugOut
0x1400296c1  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400296c8  jnz     short loc_140029719
0x1400296ca  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400296d1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400296d8  nop     dword ptr [rax+rax+00h]
0x1400296dd  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x1400296e4  jnz     short loc_1400296F6
0x1400296e6  call    LibAttach
0x1400296eb  test    eax, eax
0x1400296ed  jz      short loc_1400296F6
0x1400296ef  mov     cs:?Pku2uCryptInitialized@@3EA, 1; uchar Pku2uCryptInitialized
0x1400296f6  lea     rcx, ?Pku2uGlobalResource@@3U_ERESOURCE@@A; Resource
0x1400296fd  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140029704  nop     dword ptr [rax+rax+00h]
0x140029709  cmp     cs:?Pku2uCryptInitialized@@3EA, 0; uchar Pku2uCryptInitialized
0x140029710  jnz     short loc_140029719
0x140029712  mov     ebx, 0C000009Ah
0x140029717  jmp     short loc_140029767
0x140029719  xor     edx, edx
0x14002971b  mov     rcx, rbx
0x14002971e  call    Pku2uReferenceContext
0x140029723  mov     rdi, rax
0x140029726  test    rax, rax
0x140029729  jnz     short loc_14002974C
0x14002972b  cmp     cs:KsecInfoLevel, eax
0x140029731  jz      short loc_140029745
0x140029733  mov     r8, rbx
0x140029736  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x14002973d  lea     ecx, [rax+1]
0x140029740  call    KsecDebugOut
0x140029745  mov     ebx, 0C0000008h
0x14002974a  jmp     short loc_140029767
0x14002974c  mov     r9d, esi
0x14002974f  mov     r8, rbp
0x140029752  mov     edx, r14d
0x140029755  mov     rcx, rdi
0x140029758  call    WSTSealMessage
0x14002975d  mov     ebx, eax
0x14002975f  mov     rcx, rdi; P
0x140029762  call    Pku2uDereferenceContext
0x140029767  mov     eax, ebx
0x140029769  add     rsp, 20h
0x14002976d  pop     r14
0x14002976f  pop     rdi
0x140029770  pop     rsi
0x140029771  pop     rbp
0x140029772  pop     rbx
0x140029773  retn
```
