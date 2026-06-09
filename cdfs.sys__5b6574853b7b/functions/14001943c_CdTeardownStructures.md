# CdTeardownStructures

- ea: `0x14001943c`
- end: `0x1400198c8`
- name: `CdTeardownStructures`
- size: `1164`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bcf8`
- `0x14000c248`
- `0x14000c8b4`
- `0x14001a900`
- `0x14001a9a0`

## callees

- `0x14000bc18`
- `0x1400181a4`
- `0x14001943c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400194f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400194f5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019530`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400196f7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140019530`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400196f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001954c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019892`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001be94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001954c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019892`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001be94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019647`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019731`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019765`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001978b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400197ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019846`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019647`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019731`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019765`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001978b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400197ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019846`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001974f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001974f`
- `ntoskrnl!RtlDelete` at `0x140019586`
- `ntoskrnl!RtlDelete` at `0x1400195b2`
- `ntoskrnl!RtlDelete` at `0x1400195e8`
- `ntoskrnl!RtlDelete` at `0x140019613`
- `ntoskrnl!RtlDelete` at `0x140019586`
- `ntoskrnl!RtlDelete` at `0x1400195b2`
- `ntoskrnl!RtlDelete` at `0x1400195e8`
- `ntoskrnl!RtlDelete` at `0x140019613`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400196d2`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400196d2`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14001970e`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x14001970e`
- `ntoskrnl!FsRtlFreeFileLock` at `0x1400197e0`
- `ntoskrnl!FsRtlFreeFileLock` at `0x1400197e0`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1400197f0`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1400197f0`

## pseudocode

```c
char __fastcall CdTeardownStructures(__int64 a1, __int16 *a2, bool *a3)
{
  __int64 v4; // r13
  struct _FAST_MUTEX *v5; // r15
  __int64 v6; // r9
  int v7; // eax
  __int16 *v8; // rdi
  char v9; // bl
  __int16 *v10; // r14
  __int16 *v11; // rsi
  struct _FAST_MUTEX *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int16 *v19; // rcx
  __int64 v20; // rdx
  __int16 **v21; // rcx
  volatile signed __int32 *v22; // rbx
  void *v23; // rcx
  __int64 v24; // rsi
  __int16 *v25; // rcx
  void *v26; // rcx
  FILE_LOCK *v27; // rcx
  volatile signed __int32 *v28; // rax
  __int128 Buffer[5]; // [rsp+38h] [rbp-50h] BYREF
  struct _FAST_MUTEX *v31; // [rsp+98h] [rbp+10h]

  v4 = a1;
  v5 = (struct _FAST_MUTEX *)*((_QWORD *)a2 + 15);
  v31 = v5;
  *a3 = 0;
  v6 = *(_QWORD *)(a1 + 56);
  v7 = *(_DWORD *)(v6 + 32);
  if ( (v7 & 0x80u) != 0 )
    return v7;
  v8 = a2;
  v9 = 0;
  *(_DWORD *)(v6 + 32) = v7 | 0x80;
  do
  {
    if ( *v8 != 773 && !*((_DWORD *)v8 + 42) && *((_QWORD *)v8 + 59) )
      CdDeleteInternalStream(a1, v8);
    if ( *((_DWORD *)v8 + 41) )
      break;
    v10 = (__int16 *)*((_QWORD *)v8 + 16);
    v11 = v10 + 100;
    if ( v10 )
      CdAcquireResource(v4, *(_QWORD *)v11 + 32LL, 0, 0);
    v12 = v5 + 6;
    ExAcquireFastMutex(v12);
    *(_QWORD *)&v31[7].Count = KeGetCurrentThread();
    if ( *((_DWORD *)v8 + 41) )
    {
      *(_QWORD *)&v31[7].Count = 0;
      ExReleaseFastMutex(v12);
      if ( v10 )
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v11 + 32LL));
      break;
    }
    if ( v10 )
    {
      v13 = *((_QWORD *)v8 + 37);
      if ( v13 )
      {
        if ( (*(_DWORD *)(v13 + 8) & 2) != 0 )
        {
          v14 = *((_QWORD *)v8 + 16);
          *(_QWORD *)(v14 + 528) = RtlDelete((PRTL_SPLAY_LINKS)(v13 + 56));
        }
        v15 = *((_QWORD *)v8 + 37);
        if ( (*(_DWORD *)(v15 + 8) & 1) != 0 )
        {
          v16 = *((_QWORD *)v8 + 16);
          *(_QWORD *)(v16 + 520) = RtlDelete((PRTL_SPLAY_LINKS)(v15 + 16));
        }
        *(_DWORD *)(*((_QWORD *)v8 + 37) + 8LL) &= 0xFFFFFFFC;
      }
      if ( (*((_DWORD *)v8 + 78) & 2) != 0 )
      {
        v17 = *((_QWORD *)v8 + 16);
        *(_QWORD *)(v17 + 528) = RtlDelete((PRTL_SPLAY_LINKS)v8 + 15);
      }
      if ( (*((_DWORD *)v8 + 78) & 1) != 0 )
      {
        v18 = *((_QWORD *)v8 + 16);
        *(_QWORD *)(v18 + 520) = RtlDelete((PRTL_SPLAY_LINKS)(v8 + 160));
      }
      *((_DWORD *)v8 + 78) &= 0xFFFFFFFC;
      v19 = (__int16 *)*((_QWORD *)v8 + 44);
      if ( v19 != v8 + 200 && v19 )
      {
        ExFreePoolWithTag(v19, 0);
        *((_QWORD *)v8 + 44) = 0;
      }
      v20 = *((_QWORD *)v8 + 17);
      if ( *(__int16 **)(v20 + 8) != v8 + 68 || (v21 = (__int16 **)*((_QWORD *)v8 + 18), *v21 != v8 + 68) )
        __fastfail(3u);
      *v21 = (__int16 *)v20;
      *(_QWORD *)(v20 + 8) = v21;
      --*((_DWORD *)v10 + 41);
      --*((_DWORD *)v10 + 42);
      --*(_DWORD *)(*((_QWORD *)v10 + 15) + 60LL);
      --*(_DWORD *)(*((_QWORD *)v10 + 15) + 64LL);
    }
    if ( (*((_DWORD *)v8 + 43) & 2) != 0 )
    {
      Buffer[0] = 0;
      *(_QWORD *)&Buffer[0] = *((_QWORD *)v8 + 19);
      RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)(*((_QWORD *)v8 + 15) + 448LL), Buffer);
      *((_DWORD *)v8 + 43) &= ~2u;
    }
    *(_QWORD *)&v31[7].Count = 0;
    ExReleaseFastMutex(v12);
    v22 = 0;
    FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)v8);
    if ( *((_DWORD *)v8 + 70) > 1u )
    {
      v23 = (void *)*((_QWORD *)v8 + 36);
      if ( v23 )
      {
        ExFreePoolWithTag(v23, 0);
        *((_QWORD *)v8 + 36) = 0;
      }
    }
    v24 = *((_QWORD *)v8 + 25);
    ExDeleteResourceLite((PERESOURCE)(v24 + 32));
    if ( v24 )
      ExFreePoolWithTag((PVOID)v24, 0);
    v25 = (__int16 *)*((_QWORD *)v8 + 44);
    if ( v25 != v8 + 200 && v25 )
    {
      ExFreePoolWithTag(v25, 0);
      *((_QWORD *)v8 + 44) = 0;
    }
    v26 = (void *)*((_QWORD *)v8 + 37);
    if ( v26 )
    {
      ExFreePoolWithTag(v26, 0);
      *((_QWORD *)v8 + 37) = 0;
    }
    if ( *v8 == 771 || (a1 = (unsigned int)(*v8 - 772), *v8 == 772) )
    {
      v28 = (volatile signed __int32 *)*((_QWORD *)v8 + 15);
      if ( v8 == *((__int16 **)v28 + 10) )
      {
        *((_QWORD *)v28 + 10) = 0;
        goto LABEL_54;
      }
      if ( v8 == *((__int16 **)v28 + 11) )
      {
        *((_QWORD *)v28 + 11) = 0;
LABEL_54:
        v22 = v28;
      }
LABEL_55:
      ExFreePoolWithTag(v8, 0);
      goto LABEL_56;
    }
    if ( *v8 == 773 )
    {
      v27 = (FILE_LOCK *)*((_QWORD *)v8 + 59);
      if ( v27 )
        FsRtlFreeFileLock(v27);
      FsRtlUninitializeOplock((POPLOCK)v8 + 11);
      v28 = (volatile signed __int32 *)*((_QWORD *)v8 + 15);
      if ( v8 == *((__int16 **)v28 + 9) )
      {
        *((_QWORD *)v28 + 9) = 0;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
LABEL_56:
    if ( v22 )
    {
      _InterlockedDecrement(v22 + 15);
      _InterlockedDecrement(v22 + 16);
    }
    v8 = v10;
    v9 = 1;
    v5 = v31;
  }
  while ( v10 );
  if ( v9 && v8 )
    ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)v8 + 25) + 32LL));
  *(_DWORD *)(*(_QWORD *)(v4 + 56) + 32LL) &= ~0x80u;
  LOBYTE(v7) = v8 != a2;
  *a3 = v8 != a2;
  return v7;
}

```

## disassembly

```asm
0x14001943c  mov     [rsp+arg_10], r8
0x140019441  mov     [rsp+arg_0], rcx
0x140019446  push    rbx
0x140019447  push    rsi
0x140019448  push    rdi
0x140019449  push    r12
0x14001944b  push    r13
0x14001944d  push    r14
0x14001944f  push    r15
0x140019451  sub     rsp, 50h
0x140019455  mov     r12, rdx
0x140019458  mov     r13, rcx
0x14001945b  mov     r15, [rdx+78h]
0x14001945f  mov     [rsp+88h+arg_8], r15
0x140019467  mov     byte ptr [r8], 0
0x14001946b  mov     r9, [rcx+38h]
0x14001946f  mov     eax, [r9+20h]
0x140019473  test    al, al
0x140019475  js      loc_1400198B7
0x14001947b  mov     rdi, rdx
0x14001947e  mov     [rsp+88h+var_58], rdx
0x140019483  xor     bl, bl
0x140019485  mov     [rsp+88h+var_68], bl
0x140019489  bts     eax, 7
0x14001948d  mov     [r9+20h], eax
0x140019491  mov     eax, 305h
0x140019496  cmp     [rdi], ax
0x140019499  jz      short loc_1400194B6
0x14001949b  cmp     dword ptr [rdi+0A8h], 0
0x1400194a2  jnz     short loc_1400194B6
0x1400194a4  cmp     qword ptr [rdi+1D8h], 0
0x1400194ac  jz      short loc_1400194B6
0x1400194ae  mov     rdx, rdi
0x1400194b1  call    CdDeleteInternalStream
0x1400194b6  cmp     dword ptr [rdi+0A4h], 0
0x1400194bd  jnz     loc_14001987E
0x1400194c3  mov     r14, [rdi+80h]
0x1400194ca  lea     rsi, [r14+0C8h]
0x1400194d1  test    r14, r14
0x1400194d4  jz      short loc_1400194EB
0x1400194d6  mov     rdx, [rsi]
0x1400194d9  add     rdx, 20h ; ' '
0x1400194dd  xor     r9d, r9d
0x1400194e0  xor     r8d, r8d
0x1400194e3  mov     rcx, r13
0x1400194e6  call    CdAcquireResource
0x1400194eb  add     r15, 150h
0x1400194f2  mov     rcx, r15; FastMutex
0x1400194f5  call    cs:__imp_ExAcquireFastMutex
0x1400194fc  nop     dword ptr [rax+rax+00h]
0x140019501  mov     rax, gs:188h
0x14001950a  mov     rcx, [rsp+88h+arg_8]
0x140019512  mov     [rcx+188h], rax
0x140019519  cmp     dword ptr [rdi+0A4h], 0
0x140019520  jz      short loc_14001955D
0x140019522  mov     qword ptr [rcx+188h], 0
0x14001952d  mov     rcx, r15; FastMutex
0x140019530  call    cs:__imp_ExReleaseFastMutex
0x140019537  nop     dword ptr [rax+rax+00h]
0x14001953c  test    r14, r14
0x14001953f  jz      loc_14001987E
0x140019545  mov     rcx, [rsi]
0x140019548  add     rcx, 20h ; ' '; Resource
0x14001954c  call    cs:__imp_ExReleaseResourceLite
0x140019553  nop     dword ptr [rax+rax+00h]
0x140019558  jmp     loc_14001987E
0x14001955d  xor     esi, esi
0x14001955f  test    r14, r14
0x140019562  jz      loc_1400196A4
0x140019568  mov     rcx, [rdi+128h]
0x14001956f  test    rcx, rcx
0x140019572  jz      short loc_1400195D0
0x140019574  mov     eax, [rcx+8]
0x140019577  test    al, 2
0x140019579  jz      short loc_140019599
0x14001957b  mov     rbx, [rdi+80h]
0x140019582  add     rcx, 38h ; '8'; Links
0x140019586  call    cs:__imp_RtlDelete
0x14001958d  nop     dword ptr [rax+rax+00h]
0x140019592  mov     [rbx+210h], rax
0x140019599  mov     rcx, [rdi+128h]
0x1400195a0  mov     eax, [rcx+8]
0x1400195a3  test    al, 1
0x1400195a5  jz      short loc_1400195C5
0x1400195a7  mov     rbx, [rdi+80h]
0x1400195ae  add     rcx, 10h; Links
0x1400195b2  call    cs:__imp_RtlDelete
0x1400195b9  nop     dword ptr [rax+rax+00h]
0x1400195be  mov     [rbx+208h], rax
0x1400195c5  mov     rax, [rdi+128h]
0x1400195cc  and     dword ptr [rax+8], 0FFFFFFFCh
0x1400195d0  mov     eax, [rdi+138h]
0x1400195d6  test    al, 2
0x1400195d8  jz      short loc_1400195FB
0x1400195da  mov     rbx, [rdi+80h]
0x1400195e1  lea     rcx, [rdi+168h]; Links
0x1400195e8  call    cs:__imp_RtlDelete
0x1400195ef  nop     dword ptr [rax+rax+00h]
0x1400195f4  mov     [rbx+210h], rax
0x1400195fb  mov     eax, [rdi+138h]
0x140019601  test    al, 1
0x140019603  jz      short loc_140019626
0x140019605  mov     rbx, [rdi+80h]
0x14001960c  lea     rcx, [rdi+140h]; Links
0x140019613  call    cs:__imp_RtlDelete
0x14001961a  nop     dword ptr [rax+rax+00h]
0x14001961f  mov     [rbx+208h], rax
0x140019626  and     dword ptr [rdi+138h], 0FFFFFFFCh
0x14001962d  mov     rcx, [rdi+160h]; P
0x140019634  lea     rax, [rdi+190h]
0x14001963b  cmp     rcx, rax
0x14001963e  jz      short loc_14001965A
0x140019640  test    rcx, rcx
0x140019643  jz      short loc_14001965A
0x140019645  xor     edx, edx; Tag
0x140019647  call    cs:__imp_ExFreePoolWithTag
0x14001964e  nop     dword ptr [rax+rax+00h]
0x140019653  mov     [rdi+160h], rsi
0x14001965a  lea     rax, [rdi+88h]
0x140019661  mov     rdx, [rax]
0x140019664  cmp     [rdx+8], rax
0x140019668  jnz     loc_140019810
0x14001966e  mov     rcx, [rdi+90h]
0x140019675  cmp     [rcx], rax
0x140019678  jnz     loc_140019810
0x14001967e  mov     [rcx], rdx
0x140019681  mov     [rdx+8], rcx
0x140019685  or      ecx, 0FFFFFFFFh
0x140019688  add     [r14+0A4h], ecx
0x14001968f  add     [r14+0A8h], ecx
0x140019696  mov     rax, [r14+78h]
0x14001969a  add     [rax+3Ch], ecx
0x14001969d  mov     rax, [r14+78h]
0x1400196a1  add     [rax+40h], ecx
0x1400196a4  mov     eax, [rdi+0ACh]
0x1400196aa  test    al, 2
0x1400196ac  jz      short loc_1400196E5
0x1400196ae  xorps   xmm0, xmm0
0x1400196b1  movups  [rsp+88h+Buffer], xmm0
0x1400196b6  mov     rax, [rdi+98h]
0x1400196bd  mov     qword ptr [rsp+88h+Buffer], rax
0x1400196c2  mov     rcx, [rdi+78h]
0x1400196c6  add     rcx, 1C0h; Table
0x1400196cd  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1400196d2  call    cs:__imp_RtlDeleteElementGenericTable
0x1400196d9  nop     dword ptr [rax+rax+00h]
0x1400196de  and     dword ptr [rdi+0ACh], 0FFFFFFFDh
0x1400196e5  mov     rax, [rsp+88h+arg_8]
0x1400196ed  mov     [rax+188h], rsi
0x1400196f4  mov     rcx, r15; FastMutex
0x1400196f7  call    cs:__imp_ExReleaseFastMutex
0x1400196fe  nop     dword ptr [rax+rax+00h]
0x140019703  mov     rbx, rsi
0x140019706  mov     [rsp+88h+var_60], rbx
0x14001970b  mov     rcx, rdi; AdvancedHeader
0x14001970e  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140019715  nop     dword ptr [rax+rax+00h]
0x14001971a  cmp     dword ptr [rdi+118h], 1
0x140019721  jbe     short loc_140019744
0x140019723  mov     rcx, [rdi+120h]; P
0x14001972a  test    rcx, rcx
0x14001972d  jz      short loc_140019744
0x14001972f  xor     edx, edx; Tag
0x140019731  call    cs:__imp_ExFreePoolWithTag
0x140019738  nop     dword ptr [rax+rax+00h]
0x14001973d  mov     [rdi+120h], rsi
0x140019744  mov     rsi, [rdi+0C8h]
0x14001974b  lea     rcx, [rsi+20h]; Resource
0x14001974f  call    cs:__imp_ExDeleteResourceLite
0x140019756  nop     dword ptr [rax+rax+00h]
0x14001975b  test    rsi, rsi
0x14001975e  jz      short loc_140019771
0x140019760  xor     edx, edx; Tag
0x140019762  mov     rcx, rsi; P
0x140019765  call    cs:__imp_ExFreePoolWithTag
0x14001976c  nop     dword ptr [rax+rax+00h]
0x140019771  mov     rcx, [rdi+160h]; P
0x140019778  lea     rax, [rdi+190h]
0x14001977f  cmp     rcx, rax
0x140019782  jz      short loc_14001979E
0x140019784  test    rcx, rcx
0x140019787  jz      short loc_14001979E
0x140019789  xor     edx, edx; Tag
0x14001978b  call    cs:__imp_ExFreePoolWithTag
0x140019792  nop     dword ptr [rax+rax+00h]
0x140019797  mov     [rdi+160h], rbx
0x14001979e  mov     rcx, [rdi+128h]; P
0x1400197a5  test    rcx, rcx
0x1400197a8  jz      short loc_1400197BF
0x1400197aa  xor     edx, edx; Tag
0x1400197ac  call    cs:__imp_ExFreePoolWithTag
0x1400197b3  nop     dword ptr [rax+rax+00h]
0x1400197b8  mov     [rdi+128h], rbx
0x1400197bf  movsx   ecx, word ptr [rdi]
0x1400197c2  sub     ecx, 303h
0x1400197c8  jz      short loc_140019817
0x1400197ca  sub     ecx, 1
0x1400197cd  jz      short loc_140019817
0x1400197cf  cmp     ecx, 1
0x1400197d2  jnz     short loc_140019852
0x1400197d4  mov     rcx, [rdi+1D8h]; FileLock
0x1400197db  test    rcx, rcx
0x1400197de  jz      short loc_1400197EC
0x1400197e0  call    cs:__imp_FsRtlFreeFileLock
0x1400197e7  nop     dword ptr [rax+rax+00h]
0x1400197ec  lea     rcx, [rdi+58h]; Oplock
0x1400197f0  call    cs:__imp_FsRtlUninitializeOplock
0x1400197f7  nop     dword ptr [rax+rax+00h]
0x1400197fc  mov     rax, [rdi+78h]
0x140019800  cmp     rdi, [rax+48h]
0x140019804  jnz     short loc_140019841
0x140019806  mov     qword ptr [rax+48h], 0
0x14001980e  jmp     short loc_140019839
0x140019810  mov     ecx, 3
0x140019815  int     29h; Win8: RtlFailFast(ecx)
0x140019817  mov     rax, [rdi+78h]
0x14001981b  cmp     rdi, [rax+50h]
0x14001981f  jnz     short loc_14001982B
0x140019821  mov     qword ptr [rax+50h], 0
0x140019829  jmp     short loc_140019839
0x14001982b  cmp     rdi, [rax+58h]
0x14001982f  jnz     short loc_140019841
0x140019831  mov     qword ptr [rax+58h], 0
0x140019839  mov     [rsp+88h+var_60], rax
0x14001983e  mov     rbx, rax
0x140019841  xor     edx, edx; Tag
0x140019843  mov     rcx, rdi; P
0x140019846  call    cs:__imp_ExFreePoolWithTag
0x14001984d  nop     dword ptr [rax+rax+00h]
0x140019852  test    rbx, rbx
0x140019855  jz      short loc_14001985F
0x140019857  lock dec dword ptr [rbx+3Ch]
0x14001985b  lock dec dword ptr [rbx+40h]
0x14001985f  mov     rdi, r14
0x140019862  mov     [rsp+88h+var_58], r14
0x140019867  mov     bl, 1
0x140019869  mov     [rsp+88h+var_68], bl
0x14001986d  test    r14, r14
0x140019870  mov     r15, [rsp+88h+arg_8]
0x140019878  jnz     loc_140019491
0x14001987e  test    bl, bl
0x140019880  jz      short loc_14001989E
0x140019882  test    rdi, rdi
0x140019885  jz      short loc_14001989E
0x140019887  mov     rcx, [rdi+0C8h]
0x14001988e  add     rcx, 20h ; ' '; Resource
0x140019892  call    cs:__imp_ExReleaseResourceLite
0x140019899  nop     dword ptr [rax+rax+00h]
0x14001989e  mov     rax, [r13+38h]
0x1400198a2  btr     dword ptr [rax+20h], 7
0x1400198a7  cmp     rdi, r12
0x1400198aa  setnz   al
0x1400198ad  mov     rcx, [rsp+88h+arg_10]
0x1400198b5  mov     [rcx], al
0x1400198b7  add     rsp, 50h
0x1400198bb  pop     r15
0x1400198bd  pop     r14
0x1400198bf  pop     r13
0x1400198c1  pop     r12
0x1400198c3  pop     rdi
0x1400198c4  pop     rsi
0x1400198c5  pop     rbx
0x1400198c6  retn
0x14001be71  push    rbp
0x14001be73  sub     rsp, 20h
0x14001be77  mov     rbp, rdx
0x14001be7a  cmp     byte ptr [rbp+20h], 0
0x14001be7e  jz      short loc_14001BEA1
0x14001be80  mov     rcx, [rbp+30h]
0x14001be84  test    rcx, rcx
0x14001be87  jz      short loc_14001BEA1
0x14001be89  mov     rcx, [rcx+0C8h]
0x14001be90  add     rcx, 20h ; ' '; Resource
0x14001be94  call    cs:__imp_ExReleaseResourceLite
0x14001be9b  nop     dword ptr [rax+rax+00h]
0x14001bea0  nop
0x14001bea1  mov     rdx, [rbp+90h]
0x14001bea8  mov     rax, [rdx+38h]
0x14001beac  mov     ecx, [rax+20h]
0x14001beaf  btr     ecx, 7
0x14001beb3  mov     [rax+20h], ecx
0x14001beb6  add     rsp, 20h
0x14001beba  pop     rbp
0x14001bebb  retn
```
