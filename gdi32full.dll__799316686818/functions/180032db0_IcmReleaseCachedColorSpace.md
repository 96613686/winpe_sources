# IcmReleaseCachedColorSpace

- ea: `0x180032db0`
- end: `0x180032f50`
- name: `IcmReleaseCachedColorSpace`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180032694`

## callees

- `0x180032db0`
- `0x180034c50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032f3e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032f3e`
- `ntdll!RtlFreeHeap` at `0x180032e49`
- `ntdll!RtlFreeHeap` at `0x180032e6b`
- `ntdll!RtlFreeHeap` at `0x180032ebb`
- `ntdll!RtlFreeHeap` at `0x180032f28`
- `ntdll!RtlFreeHeap` at `0x180032e49`
- `ntdll!RtlFreeHeap` at `0x180032e6b`
- `ntdll!RtlFreeHeap` at `0x180032ebb`
- `ntdll!RtlFreeHeap` at `0x180032f28`
- `ntdll!RtlEnterCriticalSection` at `0x180032dc5`
- `ntdll!RtlEnterCriticalSection` at `0x180032df9`
- `ntdll!RtlEnterCriticalSection` at `0x180032dc5`
- `ntdll!RtlEnterCriticalSection` at `0x180032df9`
- `ntdll!RtlLeaveCriticalSection` at `0x180032ec8`
- `ntdll!RtlLeaveCriticalSection` at `0x180032ee1`
- `ntdll!RtlLeaveCriticalSection` at `0x180032ec8`
- `ntdll!RtlLeaveCriticalSection` at `0x180032ee1`

## pseudocode

```c
__int64 __fastcall IcmReleaseCachedColorSpace(PVOID a1)
{
  PVOID *v2; // rbx
  PVOID *v3; // rdi
  int v4; // eax
  bool v5; // zf
  PVOID v6; // r8
  PVOID v7; // r8
  PVOID *v8; // rax
  PVOID *v9; // rcx

  RtlEnterCriticalSection(&semColorSpaceCache);
  v2 = (PVOID *)ListCachedColorSpace;
  if ( ListCachedColorSpace != &ListCachedColorSpace )
  {
    while ( 1 )
    {
      v3 = (PVOID *)*v2;
      if ( v2[2] == a1 )
        break;
LABEL_20:
      v2 = v3;
      if ( v3 == &ListCachedColorSpace )
        goto LABEL_21;
    }
    RtlEnterCriticalSection(&semColorSpaceCache);
    v4 = --*((_DWORD *)v2 + 7);
    if ( ((_DWORD)v2[3] & 0x10000) != 0 )
    {
      v5 = v4 == 0;
    }
    else
    {
      if ( !v4 )
        goto LABEL_6;
      v5 = v2[2] == a1;
    }
    if ( !v5 )
    {
LABEL_19:
      RtlLeaveCriticalSection(&semColorSpaceCache);
      goto LABEL_20;
    }
LABEL_6:
    if ( v2[4] )
      IcmUnrealizeColorProfile(v2);
    if ( ((_DWORD)v2[3] & 0x40000) != 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2[7]);
      v2[7] = 0;
    }
    v6 = v2[9];
    if ( v6 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2[9] = 0;
    }
    v7 = v2[10];
    if ( v7 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      v2[10] = 0;
    }
    if ( ((_DWORD)v2[3] & 0x80000) != 0 )
      DeleteFileW((LPCWSTR)v2 + 78);
    v8 = (PVOID *)*v2;
    if ( *((PVOID **)*v2 + 1) != v2 || (v9 = (PVOID *)v2[1], *v9 != v2) )
      __fastfail(3u);
    --cCachedColorSpace;
    *v9 = v8;
    v8[1] = v9;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    goto LABEL_19;
  }
LABEL_21:
  RtlLeaveCriticalSection(&semColorSpaceCache);
  return 1;
}

```

## disassembly

```asm
0x180032db0  push    rbx
0x180032db2  push    rbp
0x180032db3  push    rsi
0x180032db4  push    rdi
0x180032db5  push    r14
0x180032db7  sub     rsp, 20h
0x180032dbb  mov     rsi, rcx
0x180032dbe  lea     rcx, semColorSpaceCache; CriticalSection
0x180032dc5  call    cs:__imp_RtlEnterCriticalSection
0x180032dcb  mov     rbx, cs:ListCachedColorSpace
0x180032dd2  lea     rbp, ListCachedColorSpace
0x180032dd9  cmp     rbx, rbp
0x180032ddc  jz      loc_180032EDA
0x180032de2  xor     r14d, r14d
0x180032de5  mov     rdi, [rbx]
0x180032de8  cmp     [rbx+10h], rsi
0x180032dec  jnz     loc_180032ECE
0x180032df2  lea     rcx, semColorSpaceCache; CriticalSection
0x180032df9  call    cs:__imp_RtlEnterCriticalSection
0x180032dff  dec     dword ptr [rbx+1Ch]
0x180032e02  test    dword ptr [rbx+18h], 10000h
0x180032e09  mov     eax, [rbx+1Ch]
0x180032e0c  jz      loc_180032EF7
0x180032e12  test    eax, eax
0x180032e14  jnz     loc_180032EC1
0x180032e1a  cmp     [rbx+20h], r14
0x180032e1e  jnz     loc_180032F08
0x180032e24  test    dword ptr [rbx+18h], 40000h
0x180032e2b  jnz     loc_180032F15
0x180032e31  mov     r8, [rbx+48h]; P
0x180032e35  test    r8, r8
0x180032e38  jz      short loc_180032E53
0x180032e3a  mov     rcx, gs:60h
0x180032e43  xor     edx, edx; Flags
0x180032e45  mov     rcx, [rcx+30h]; HeapHandle
0x180032e49  call    cs:__imp_RtlFreeHeap
0x180032e4f  mov     [rbx+48h], r14
0x180032e53  mov     r8, [rbx+50h]; P
0x180032e57  test    r8, r8
0x180032e5a  jz      short loc_180032E75
0x180032e5c  mov     rcx, gs:60h
0x180032e65  xor     edx, edx; Flags
0x180032e67  mov     rcx, [rcx+30h]; HeapHandle
0x180032e6b  call    cs:__imp_RtlFreeHeap
0x180032e71  mov     [rbx+50h], r14
0x180032e75  test    dword ptr [rbx+18h], 80000h
0x180032e7c  jnz     loc_180032F37
0x180032e82  mov     rax, [rbx]
0x180032e85  cmp     [rax+8], rbx
0x180032e89  jnz     loc_180032F49
0x180032e8f  mov     rcx, [rbx+8]
0x180032e93  cmp     [rcx], rbx
0x180032e96  jnz     loc_180032F49
0x180032e9c  dec     cs:?cCachedColorSpace@@3KA; ulong cCachedColorSpace
0x180032ea2  mov     r8, rbx; P
0x180032ea5  mov     [rcx], rax
0x180032ea8  xor     edx, edx; Flags
0x180032eaa  mov     [rax+8], rcx
0x180032eae  mov     rcx, gs:60h
0x180032eb7  mov     rcx, [rcx+30h]; HeapHandle
0x180032ebb  call    cs:__imp_RtlFreeHeap
0x180032ec1  lea     rcx, semColorSpaceCache; CriticalSection
0x180032ec8  call    cs:__imp_RtlLeaveCriticalSection
0x180032ece  mov     rbx, rdi
0x180032ed1  cmp     rdi, rbp
0x180032ed4  jnz     loc_180032DE5
0x180032eda  lea     rcx, semColorSpaceCache; CriticalSection
0x180032ee1  call    cs:__imp_RtlLeaveCriticalSection
0x180032ee7  mov     eax, 1
0x180032eec  add     rsp, 20h
0x180032ef0  pop     r14
0x180032ef2  pop     rdi
0x180032ef3  pop     rsi
0x180032ef4  pop     rbp
0x180032ef5  pop     rbx
0x180032ef6  retn
0x180032ef7  test    eax, eax
0x180032ef9  jz      loc_180032E1A
0x180032eff  cmp     [rbx+10h], rsi
0x180032f03  jmp     loc_180032E14
0x180032f08  mov     rcx, rbx
0x180032f0b  call    IcmUnrealizeColorProfile
0x180032f10  jmp     loc_180032E24
0x180032f15  mov     rcx, gs:60h
0x180032f1e  xor     edx, edx; Flags
0x180032f20  mov     r8, [rbx+38h]; P
0x180032f24  mov     rcx, [rcx+30h]; HeapHandle
0x180032f28  call    cs:__imp_RtlFreeHeap
0x180032f2e  mov     [rbx+38h], r14
0x180032f32  jmp     loc_180032E31
0x180032f37  lea     rcx, [rbx+9Ch]; lpFileName
0x180032f3e  call    cs:__imp_DeleteFileW
0x180032f44  jmp     loc_180032E82
0x180032f49  mov     ecx, 3
0x180032f4e  int     29h; Win8: RtlFailFast(ecx)
```
