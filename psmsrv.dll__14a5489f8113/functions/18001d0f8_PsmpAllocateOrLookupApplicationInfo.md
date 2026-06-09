# PsmpAllocateOrLookupApplicationInfo

- ea: `0x18001d0f8`
- end: `0x18001d345`
- name: `PsmpAllocateOrLookupApplicationInfo`
- size: `589`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002b200`

## callees

- `0x1800017b0`
- `0x18000c310`
- `0x18000ce64`
- `0x180012b00`
- `0x1800133f0`
- `0x180013510`
- `0x18001b7e0`
- `0x18001d0f8`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001d30e`
- `ntdll!RtlFreeHeap` at `0x18001d30e`
- `ntdll!RtlCopySid` at `0x18001d274`
- `ntdll!RtlCopySid` at `0x18001d274`
- `ntdll!RtlAllocateHeap` at `0x18001d1dc`
- `ntdll!RtlAllocateHeap` at `0x18001d1dc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d2a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d2a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d2e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d2e7`

## pseudocode

```c
__int64 __fastcall PsmpAllocateOrLookupApplicationInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  _WORD *v5; // rsi
  unsigned int HashKey; // eax
  __int64 v8; // rcx
  __int64 v9; // r14
  __int64 HashEntry; // rax
  __int64 v11; // rdi
  char *Heap; // rax
  __int64 result; // rax
  char *v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // rax
  void *v18; // rbx
  unsigned int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // rsi
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h]
  _BYTE Src[576]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = *(_WORD **)(a4 + 8);
  v25 = a4;
  v24 = 0;
  LODWORD(Size) = 576;
  PsmpGetPsmKeyWithAppId(0, v5, Src, &Size);
  HashKey = PsmpGetHashKey(Src, &v24, 128);
  v8 = 2LL * HashKey + 1;
  v9 = a1 + 8 * (HashKey + v8);
  HashEntry = PsmpFindHashEntry(a1 + 8 * (HashKey + v8), a1, (unsigned int)Src, v24, 0);
  v11 = (HashEntry - 8) & -(__int64)(HashEntry != 0);
  if ( v11 )
  {
    PsmpDereferenceObjectEx(v11 + 8, 0);
  }
  else
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size + 592LL);
    v11 = (__int64)Heap;
    if ( !Heap )
      return 3221225626LL;
    v14 = Heap + 592;
    memcpy_0(Heap + 592, Src, (unsigned int)Size);
    v15 = v25;
    *(_QWORD *)(v11 + 24) = v24;
    *(_DWORD *)(v11 + 8) = 1;
    *(_QWORD *)(v11 + 16) = v14;
    *(_DWORD *)(v11 + 12) = ((int)v9 - (int)a1 - 8) / 24;
    *(_QWORD *)(v11 + 40) = v11 + 32;
    *(_QWORD *)(v11 + 32) = v11 + 32;
    v16 = *(_QWORD *)(v15 + 312);
    *(_DWORD *)(v11 + 116) = *(_DWORD *)(v16 + 4);
    RtlCopySid(0x44u, (PSID)(v11 + 48), *(PSID *)(v16 + 40));
    v17 = -1;
    v18 = 0;
    do
      ++v17;
    while ( v5[v17] );
    v19 = 2 * v17 + 2;
    *(_DWORD *)(v11 + 120) = v19;
    memcpy_0((void *)(v11 + 124), v5, v19);
    *(_QWORD *)v11 = a1;
    RtlAcquireSRWLockExclusive(v9 + 16);
    v21 = PsmpLookupHashEntry(v9, v20, (unsigned int)Src, (unsigned int)&Size, 0);
    v22 = v21;
    if ( v21 )
    {
      v18 = (void *)v11;
      v11 = v21 - 8;
    }
    else
    {
      PsmpInsertHashEntry(v9, v11 + 8);
    }
    RtlReleaseSRWLockExclusive(v9 + 16);
    if ( v18 )
    {
      PsmpDereferenceObjectEx(v22, 0);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
    }
  }
  result = 0;
  *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x18001d0f8  mov     [rsp-8+arg_8], rbx
0x18001d0fd  push    rbp
0x18001d0fe  push    rsi
0x18001d0ff  push    rdi
0x18001d100  push    r12
0x18001d102  push    r13
0x18001d104  push    r14
0x18001d106  push    r15
0x18001d108  lea     rbp, [rsp-1A0h]
0x18001d110  sub     rsp, 2A0h
0x18001d117  mov     rax, cs:__security_cookie
0x18001d11e  xor     rax, rsp
0x18001d121  mov     [rbp+1D0h+var_40], rax
0x18001d128  mov     rsi, [r9+8]
0x18001d12c  lea     r8, [rsp+2D0h+Src]
0x18001d131  mov     r13, [rbp+1D0h+arg_20]
0x18001d138  mov     r15, rcx
0x18001d13b  mov     [rsp+2D0h+var_290], r9
0x18001d140  xor     r12d, r12d
0x18001d143  mov     rdx, rsi
0x18001d146  mov     [rsp+2D0h+var_298], r12
0x18001d14b  lea     r9, [rsp+2D0h+Size]
0x18001d150  mov     dword ptr [rsp+2D0h+Size], 240h
0x18001d158  xor     ecx, ecx
0x18001d15a  call    PsmpGetPsmKeyWithAppId
0x18001d15f  mov     r8d, 80h
0x18001d165  lea     rdx, [rsp+2D0h+var_298]
0x18001d16a  lea     rcx, [rsp+2D0h+Src]
0x18001d16f  call    PsmpGetHashKey
0x18001d174  mov     r9, [rsp+2D0h+var_298]
0x18001d179  lea     r8, [rsp+2D0h+Src]
0x18001d17e  mov     eax, eax
0x18001d180  mov     rdx, r15
0x18001d183  mov     [rsp+2D0h+var_2B0], r12
0x18001d188  lea     rcx, ds:1[rax*2]
0x18001d190  add     rcx, rax
0x18001d193  lea     r14, [r15+rcx*8]
0x18001d197  mov     rcx, r14
0x18001d19a  call    PsmpFindHashEntry
0x18001d19f  lea     rcx, [rax-8]
0x18001d1a3  neg     rax
0x18001d1a6  sbb     rdi, rdi
0x18001d1a9  and     rdi, rcx
0x18001d1ac  jz      short loc_18001D1BE
0x18001d1ae  lea     rcx, [rdi+8]
0x18001d1b2  xor     edx, edx
0x18001d1b4  call    PsmpDereferenceObjectEx
0x18001d1b9  jmp     loc_18001D314
0x18001d1be  mov     rcx, gs:60h
0x18001d1c7  mov     edx, 8; Flags
0x18001d1cc  mov     r8d, dword ptr [rsp+2D0h+Size]
0x18001d1d1  add     r8, 250h; Size
0x18001d1d8  mov     rcx, [rcx+30h]; HeapHandle
0x18001d1dc  call    cs:__imp_RtlAllocateHeap
0x18001d1e2  mov     rdi, rax
0x18001d1e5  test    rax, rax
0x18001d1e8  jnz     short loc_18001D1F4
0x18001d1ea  mov     eax, 0C000009Ah
0x18001d1ef  jmp     loc_18001D31B
0x18001d1f4  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x18001d1f9  lea     rbx, [rax+250h]
0x18001d200  mov     rcx, rbx; void *
0x18001d203  lea     rdx, [rsp+2D0h+Src]; Src
0x18001d208  call    memcpy_0
0x18001d20d  mov     rax, [rsp+2D0h+var_298]
0x18001d212  mov     rcx, r14
0x18001d215  mov     r8, [rsp+2D0h+var_290]
0x18001d21a  sub     rcx, r15
0x18001d21d  mov     [rdi+18h], rax
0x18001d221  sub     rcx, 8
0x18001d225  mov     dword ptr [rdi+8], 1
0x18001d22c  mov     rax, 2AAAAAAAAAAAAAABh
0x18001d236  imul    rcx
0x18001d239  mov     [rdi+10h], rbx
0x18001d23d  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18001d242  sar     rdx, 2
0x18001d246  mov     rax, rdx
0x18001d249  shr     rax, 3Fh
0x18001d24d  add     rdx, rax
0x18001d250  lea     rax, [rdi+20h]
0x18001d254  mov     [rdi+0Ch], edx
0x18001d257  lea     rdx, [rdi+30h]; DestinationSid
0x18001d25b  mov     [rax+8], rax
0x18001d25f  mov     [rax], rax
0x18001d262  mov     r8, [r8+138h]
0x18001d269  mov     eax, [r8+4]
0x18001d26d  mov     [rdi+74h], eax
0x18001d270  mov     r8, [r8+28h]; SourceSid
0x18001d274  call    cs:__imp_RtlCopySid
0x18001d27a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d27e  xor     ebx, ebx
0x18001d280  inc     rax
0x18001d283  cmp     [rsi+rax*2], bx
0x18001d287  jnz     short loc_18001D280
0x18001d289  lea     eax, ds:2[rax*2]
0x18001d290  mov     rdx, rsi; Src
0x18001d293  mov     r8d, eax; Size
0x18001d296  lea     rcx, [rdi+7Ch]; void *
0x18001d29a  mov     [rdi+78h], eax
0x18001d29d  call    memcpy_0
0x18001d2a2  lea     rcx, [r14+10h]
0x18001d2a6  mov     [rdi], r15
0x18001d2a9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001d2af  lea     r9, [rsp+2D0h+Size]
0x18001d2b4  mov     [rsp+2D0h+var_2B0], rbx
0x18001d2b9  lea     r8, [rsp+2D0h+Src]
0x18001d2be  mov     rcx, r14
0x18001d2c1  call    PsmpLookupHashEntry
0x18001d2c6  mov     rsi, rax
0x18001d2c9  test    rax, rax
0x18001d2cc  jnz     short loc_18001D2DC
0x18001d2ce  lea     rdx, [rdi+8]
0x18001d2d2  mov     rcx, r14
0x18001d2d5  call    PsmpInsertHashEntry
0x18001d2da  jmp     short loc_18001D2E3
0x18001d2dc  mov     rbx, rdi
0x18001d2df  lea     rdi, [rax-8]
0x18001d2e3  lea     rcx, [r14+10h]
0x18001d2e7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d2ed  test    rbx, rbx
0x18001d2f0  jz      short loc_18001D314
0x18001d2f2  xor     edx, edx
0x18001d2f4  mov     rcx, rsi
0x18001d2f7  call    PsmpDereferenceObjectEx
0x18001d2fc  mov     rcx, gs:60h
0x18001d305  mov     r8, rbx; P
0x18001d308  xor     edx, edx; Flags
0x18001d30a  mov     rcx, [rcx+30h]; HeapHandle
0x18001d30e  call    cs:__imp_RtlFreeHeap
0x18001d314  mov     eax, r12d
0x18001d317  mov     [r13+0], rdi
0x18001d31b  mov     rcx, [rbp+1D0h+var_40]
0x18001d322  xor     rcx, rsp; StackCookie
0x18001d325  call    __security_check_cookie
0x18001d32a  mov     rbx, [rsp+2D0h+arg_8]
0x18001d332  add     rsp, 2A0h
0x18001d339  pop     r15
0x18001d33b  pop     r14
0x18001d33d  pop     r13
0x18001d33f  pop     r12
0x18001d341  pop     rdi
0x18001d342  pop     rsi
0x18001d343  pop     rbp
0x18001d344  retn
```
