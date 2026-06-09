# LdrpFindOrPrepareLoadingModule

- ea: `0x18006e930`
- end: `0x18006f0be`
- name: `LdrpFindOrPrepareLoadingModule`
- size: `1934`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, service_task`

## callers

- `0x180024990`
- `0x18011aa4c`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001861c`
- `0x18001b530`
- `0x18001b984`
- `0x18001eb80`
- `0x1800295d0`
- `0x18002cde0`
- `0x180069af8`
- `0x18006dcf4`
- `0x18006e930`
- `0x18006f0d0`
- `0x18006f100`
- `0x18006fb30`
- `0x1800707b0`
- `0x180070814`
- `0x180070910`
- `0x18008533c`
- `0x1800c358c`
- `0x1800e36a0`
- `0x1800fe04c`
- `0x18012d320`
- `0x180164280`

## string_xrefs

- `0x18006ea50`: `Found circular dependent DLL: "%wZ" that failed to load previously, ModuleState: %d\n`

## pseudocode

```c
__int64 __fastcall LdrpFindOrPrepareLoadingModule(
        const void **a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 *a6,
        __int64 a7)
{
  __int64 v10; // rbp
  const void **v11; // r14
  int v12; // r12d
  int v13; // ebx
  __int64 v14; // rdx
  int LoadedDllByNameLockHeld; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int CurrentServiceSessionId; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v29; // r12
  __int64 v30; // rcx
  int v31; // edx
  __int64 Heap_0; // rax
  __int64 v33; // rbx
  __int64 ModuleEntry; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  _DWORD *SharedData; // rcx
  __int64 v39; // rcx
  _QWORD *SchedulerSharedDataSlot; // rdx
  __int64 i; // rcx
  __int64 v43; // rcx
  int v44; // eax
  char *v45; // rax
  int v46; // r9d
  __int64 v47; // rdx
  _QWORD *v48; // rcx
  const void **v49; // r12
  int v50; // ebx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rcx
  char *v60; // rax
  int v61; // r9d
  char *v62; // rax
  size_t v63; // rax
  char *v64; // rax
  _QWORD *v65; // rsi
  _QWORD *v66; // r14
  __int64 v67; // rcx
  char *Format; // [rsp+20h] [rbp-78h]
  __int128 v69; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v70[4]; // [rsp+50h] [rbp-48h] BYREF
  int v72; // [rsp+B8h] [rbp+20h]
  __int64 v73; // [rsp+C8h] [rbp+30h]

  v10 = a2;
  v11 = a1;
  v69 = 0;
  *a6 = 0;
  if ( a4 == 9 )
  {
    *((_QWORD *)&v69 + 1) = ModuleNamePlaceholderBuffer;
    v63 = 2 * wcslen(ModuleNamePlaceholderBuffer);
    v11 = (const void **)&v69;
    if ( v63 >= 0xFFFE )
      LOWORD(v63) = -4;
    LOWORD(v69) = v63;
    WORD1(v69) = v63 + 2;
    goto LABEL_17;
  }
  if ( (a3 & 0x20) != 0 )
  {
    v70[0] = 0;
    if ( a1 )
    {
      v49 = a1;
    }
    else
    {
      LdrpGetBaseNameFromFullName(0, v70);
      v49 = (const void **)v70;
    }
    v73 = (__int64)v49;
    v50 = LdrpHashUnicodeString(v49);
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)v49, 0, a3, (_DWORD)a6, v50);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v51);
      v12 = 0;
      v72 = 0;
    }
    else
    {
      v12 = *(_DWORD *)(*(_QWORD *)(*a6 + 152) + 56LL);
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v51);
      v72 = 1;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v53, v52, v54, v55) )
      v59 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v59 = 2147353476;
    if ( *(_BYTE *)v59 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v60 = (unsigned int)RtlGetCurrentServiceSessionId(v59, v56, v57, v58)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v60 & 0x20) != 0 )
      {
        v61 = 0;
        if ( !v72 )
          v61 = 3;
        LdrpLogEtwEvent(5280, 0, 0, v61, v73, 0);
      }
    }
  }
  else
  {
    if ( (a3 & 0x200) == 0 )
    {
LABEL_17:
      v29 = 2147353476;
      v30 = LdrpHeap;
      v31 = NtdllBaseTag + 0x40000;
      *a6 = 0;
      Heap_0 = RtlAllocateHeap_0(v30, v31 | 8u, *(unsigned __int16 *)v11 + 210LL);
      v33 = Heap_0;
      if ( Heap_0 )
      {
        *(_QWORD *)(Heap_0 + 40) = a7;
        *(_QWORD *)(Heap_0 + 48) = a5;
        *(_DWORD *)(Heap_0 + 32) = a3 | 0x8000;
        *(_QWORD *)(Heap_0 + 16) = v10;
        *(_QWORD *)(Heap_0 + 184) = -1;
        *(_QWORD *)(Heap_0 + 8) = Heap_0 + 208;
        *(_WORD *)Heap_0 = *(_WORD *)v11;
        *(_WORD *)(Heap_0 + 2) = *(_WORD *)v11 + 2;
        memmove((void *)(Heap_0 + 208), v11[1], *(unsigned __int16 *)v11);
        *(_WORD *)(*(_QWORD *)(v33 + 8) + 2 * ((unsigned __int64)*(unsigned __int16 *)v11 >> 1)) = 0;
        ModuleEntry = LdrpAllocateModuleEntry(v33);
        *a6 = ModuleEntry;
        if ( ModuleEntry )
        {
          *(_DWORD *)(ModuleEntry + 268) = a4;
          if ( a4 == 9 )
            *(_DWORD *)(*a6 + 304) = 1;
          SharedData = NtCurrentPeb()->SharedData;
          if ( SharedData && *SharedData )
            v29 = (__int64)NtCurrentPeb()->SharedData + 554;
          if ( *(_BYTE *)v29 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
          {
            v64 = (unsigned int)RtlGetCurrentServiceSessionId(SharedData, v35, v36, v37)
                ? (char *)NtCurrentPeb()->SharedData + 555
                : (char *)2147353477;
            if ( (*v64 & 0x20) != 0 )
              LdrpLogEtwEvent(5292, 0, 0, 0, v33, 0);
          }
        }
        else
        {
          RtlFreeHeap_0(LdrpHeap, 0, v33);
        }
      }
      v39 = *a6;
      LoadedDllByNameLockHeld = 0;
      if ( !*a6 )
        LoadedDllByNameLockHeld = -1073741801;
      if ( a4 == 9 )
      {
        return (unsigned int)-1073741515;
      }
      else if ( v39 )
      {
        return (unsigned int)LdrpLoadKnownDll(*(_QWORD *)(v39 + 176));
      }
      return (unsigned int)LoadedDllByNameLockHeld;
    }
    v12 = 0;
    v70[0] = 0;
    LdrpGetBaseNameFromFullName(a1, v70);
    v13 = LdrpHashUnicodeString(v70);
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((unsigned int)v70, (_DWORD)v11, a3, (_DWORD)a6, v13);
    if ( LoadedDllByNameLockHeld >= 0 )
      v12 = *(_DWORD *)(*(_QWORD *)(*a6 + 152) + 56LL);
    RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v14);
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v17, v16, v18, v19);
    v24 = 2147353476;
    if ( v11 )
    {
      if ( CurrentServiceSessionId )
        v24 = (__int64)NtCurrentPeb()->SharedData + 554;
      if ( *(_BYTE *)v24 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
      {
        v62 = (unsigned int)RtlGetCurrentServiceSessionId(v24, v21, v22, v23)
            ? (char *)NtCurrentPeb()->SharedData + 555
            : (char *)2147353477;
        if ( (*v62 & 0x20) != 0 )
        {
          v46 = 0;
          Format = (char *)v11;
          if ( LoadedDllByNameLockHeld < 0 )
            v46 = 3;
LABEL_73:
          LdrpLogEtwEvent(5280, 0, 0, v46, (__int64)Format, 0);
        }
      }
    }
    else
    {
      if ( CurrentServiceSessionId )
        v24 = (__int64)NtCurrentPeb()->SharedData + 554;
      if ( *(_BYTE *)v24 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
      {
        v45 = (unsigned int)RtlGetCurrentServiceSessionId(v24, v21, v22, v23)
            ? (char *)NtCurrentPeb()->SharedData + 555
            : (char *)2147353477;
        if ( (*v45 & 0x20) != 0 )
        {
          v46 = 0;
          Format = (char *)v70;
          if ( LoadedDllByNameLockHeld < 0 )
            v46 = 3;
          goto LABEL_73;
        }
      }
    }
  }
  if ( LoadedDllByNameLockHeld == -1073741515 )
  {
    v10 = a2;
    goto LABEL_17;
  }
  v25 = *a6;
  if ( v12 >= 0 )
  {
    SchedulerSharedDataSlot = NtCurrentTeb()->SchedulerSharedDataSlot;
    if ( SchedulerSharedDataSlot )
    {
      for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
      {
        if ( !SchedulerSharedDataSlot[i] )
        {
          SchedulerSharedDataSlot[i] = LdrpModuleDatatableLock;
          break;
        }
      }
    }
    if ( _interlockedbittestandset64((volatile signed __int32 *)LdrpModuleDatatableLock, 0) )
      RtlpAcquireSRWLockExclusiveContended(LdrpModuleDatatableLock);
    v43 = *(_QWORD *)(v25 + 152);
    v44 = *(_DWORD *)(v43 + 24);
    if ( v44 != -1 )
    {
      if ( v44 )
      {
        *(_DWORD *)(v43 + 24) = v44 + 1;
        RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
        return (unsigned int)LoadedDllByNameLockHeld;
      }
      if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
        ++*(_DWORD *)(v43 + 28);
    }
    RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
  }
  else
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrmap.c",
      3522,
      (int)"LdrpFindOrPrepareLoadingModule",
      0,
      "Found circular dependent DLL: \"%wZ\" that failed to load previously, ModuleState: %d\n",
      v25 + 72);
    v26 = *a6;
    v27 = *(_QWORD *)(*a6 + 152);
    if ( *(_DWORD *)(v27 + 24) != -1
      && (*(_DWORD *)(*(_QWORD *)v27 - 56LL) & 0x20) == 0
      && _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 276), 0xFFFFFFFF) == 1 )
    {
      RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
      v47 = *(_QWORD *)(v26 + 160);
      if ( *(_QWORD *)(v47 + 8) != v26 + 160 || (v48 = *(_QWORD **)(v26 + 168), *v48 != v26 + 160) )
        __fastfail(3u);
      *v48 = v47;
      *(_QWORD *)(v47 + 8) = v48;
      v65 = *(_QWORD **)(v26 + 152);
      v66 = (_QWORD *)*v65;
      RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
      if ( *(_WORD *)(v26 + 110) )
        LdrpReleaseTlsEntry(v26, 0);
      LdrpUnmapModule(v26);
      v67 = *(_QWORD *)(v26 + 136);
      if ( (unsigned __int64)(v67 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        RtlReleaseActivationContext(v67);
      if ( *(_QWORD *)(v26 + 80) )
        LdrpFreeUnicodeString(v26 + 72);
      RtlFreeHeap_0(LdrpHeap, 0, v26);
      if ( v66 == v65 )
        LdrpDestroyNode(v65);
    }
    LoadedDllByNameLockHeld = -1073741595;
    *a6 = 0;
  }
  return (unsigned int)LoadedDllByNameLockHeld;
}

```

## disassembly

```asm
0x18006e930  mov     [rsp+arg_0], rbx
0x18006e935  mov     [rsp+arg_8], rdx
0x18006e93a  push    rbp
0x18006e93b  push    rsi
0x18006e93c  push    rdi
0x18006e93d  push    r12
0x18006e93f  push    r13
0x18006e941  push    r14
0x18006e943  push    r15
0x18006e945  sub     rsp, 60h
0x18006e949  mov     rdi, [rsp+98h+arg_28]
0x18006e951  xorps   xmm0, xmm0
0x18006e954  mov     r15d, r9d
0x18006e957  mov     esi, r8d
0x18006e95a  mov     rbp, rdx
0x18006e95d  mov     r14, rcx
0x18006e960  movups  [rsp+98h+var_58], xmm0
0x18006e965  mov     qword ptr [rdi], 0
0x18006e96c  cmp     r9d, 9
0x18006e970  jz      loc_18006EF31
0x18006e976  test    sil, 20h
0x18006e97a  jnz     loc_18006ED24
0x18006e980  bt      r8d, 9
0x18006e985  jnb     loc_18006EAB5
0x18006e98b  lea     rdx, [rsp+98h+var_48]
0x18006e990  xor     r12d, r12d
0x18006e993  movups  [rsp+98h+var_48], xmm0
0x18006e998  call    LdrpGetBaseNameFromFullName
0x18006e99d  lea     rcx, [rsp+98h+var_48]
0x18006e9a2  call    LdrpHashUnicodeString
0x18006e9a7  lea     rbp, LdrpModuleDatatableLock
0x18006e9ae  mov     ebx, eax
0x18006e9b0  mov     rcx, rbp
0x18006e9b3  call    RtlAcquireSRWLockShared
0x18006e9b8  mov     r9, rdi
0x18006e9bb  mov     dword ptr [rsp+98h+Format], ebx
0x18006e9bf  mov     r8d, esi
0x18006e9c2  lea     rcx, [rsp+98h+var_48]
0x18006e9c7  mov     rdx, r14
0x18006e9ca  call    LdrpFindLoadedDllByNameLockHeld
0x18006e9cf  mov     ebx, eax
0x18006e9d1  test    eax, eax
0x18006e9d3  js      short loc_18006E9E3
0x18006e9d5  mov     rax, [rdi]
0x18006e9d8  mov     rcx, [rax+98h]
0x18006e9df  mov     r12d, [rcx+38h]
0x18006e9e3  mov     rcx, rbp
0x18006e9e6  call    RtlReleaseSRWLockShared
0x18006e9eb  mov     r13d, 3
0x18006e9f1  call    RtlGetCurrentServiceSessionId
0x18006e9f6  mov     ecx, 7FFE0384h
0x18006e9fb  test    r14, r14
0x18006e9fe  jz      loc_18006EC45
0x18006ea04  test    eax, eax
0x18006ea06  jnz     loc_18006EED9
0x18006ea0c  cmp     byte ptr [rcx], 0
0x18006ea0f  jz      short loc_18006EA27
0x18006ea11  mov     rax, gs:60h
0x18006ea1a  test    byte ptr [rax+378h], 4
0x18006ea21  jnz     loc_18006EE2D
0x18006ea27  cmp     ebx, 0C0000135h
0x18006ea2d  jz      short loc_18006EAAD
0x18006ea2f  mov     rsi, [rdi]
0x18006ea32  test    r12d, r12d
0x18006ea35  jns     loc_18006EBE9
0x18006ea3b  lea     rax, [rsi+48h]
0x18006ea3f  mov     [rsp+98h+var_68], r12d
0x18006ea44  mov     qword ptr [rsp+98h+ArgList], rax; ArgList
0x18006ea49  lea     r8, aLdrpfindorprep; "LdrpFindOrPrepareLoadingModule"
0x18006ea50  lea     rax, aFoundCircularD; "Found circular dependent DLL: \"%wZ\" t"...
0x18006ea57  xor     r9d, r9d; int
0x18006ea5a  mov     edx, 0DC2h; int
0x18006ea5f  mov     [rsp+98h+Format], rax; Format
0x18006ea64  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18006ea6b  call    LdrpLogInternal
0x18006ea70  mov     rbx, [rdi]
0x18006ea73  mov     rcx, [rbx+98h]
0x18006ea7a  mov     eax, [rcx+18h]
0x18006ea7d  cmp     eax, 0FFFFFFFFh
0x18006ea80  jnz     loc_18006ECB9
0x18006ea86  mov     ebx, 0C00000E5h
0x18006ea8b  mov     qword ptr [rdi], 0
0x18006ea92  mov     eax, ebx
0x18006ea94  mov     rbx, [rsp+98h+arg_0]
0x18006ea9c  add     rsp, 60h
0x18006eaa0  pop     r15
0x18006eaa2  pop     r14
0x18006eaa4  pop     r13
0x18006eaa6  pop     r12
0x18006eaa8  pop     rdi
0x18006eaa9  pop     rsi
0x18006eaaa  pop     rbp
0x18006eaab  retn
0x18006eaad  mov     rbp, [rsp+98h+arg_8]
0x18006eab5  mov     edx, cs:NtdllBaseTag
0x18006eabb  mov     r12d, 7FFE0384h
0x18006eac1  mov     rcx, cs:LdrpHeap
0x18006eac8  add     edx, 40000h
0x18006eace  mov     qword ptr [rdi], 0
0x18006ead5  or      edx, 8
0x18006ead8  movzx   r8d, word ptr [r14]
0x18006eadc  add     r8, 0D2h
0x18006eae3  call    RtlAllocateHeap_0
0x18006eae8  mov     rbx, rax
0x18006eaeb  test    rax, rax
0x18006eaee  jz      loc_18006EBC5
0x18006eaf4  mov     rcx, [rsp+98h+arg_30]
0x18006eafc  bts     esi, 0Fh
0x18006eb00  mov     [rax+28h], rcx
0x18006eb04  mov     rcx, [rsp+98h+arg_20]
0x18006eb0c  mov     [rax+30h], rcx
0x18006eb10  lea     rcx, [rbx+0D0h]; void *
0x18006eb17  mov     [rax+20h], esi
0x18006eb1a  mov     [rax+10h], rbp
0x18006eb1e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006eb25  mov     [rbx+0B8h], rax
0x18006eb2c  mov     [rbx+8], rcx
0x18006eb30  movzx   eax, word ptr [r14]
0x18006eb34  mov     [rbx], ax
0x18006eb37  movzx   eax, word ptr [r14]
0x18006eb3b  add     ax, 2
0x18006eb3f  mov     [rbx+2], ax
0x18006eb43  movzx   r8d, word ptr [r14]; Size
0x18006eb47  mov     rdx, [r14+8]; Src
0x18006eb4b  call    memmove
0x18006eb50  movzx   edx, word ptr [r14]
0x18006eb54  xor     eax, eax
0x18006eb56  mov     rcx, [rbx+8]
0x18006eb5a  shr     rdx, 1
0x18006eb5d  mov     [rcx+rdx*2], ax
0x18006eb61  mov     rcx, rbx
0x18006eb64  call    LdrpAllocateModuleEntry
0x18006eb69  mov     [rdi], rax
0x18006eb6c  test    rax, rax
0x18006eb6f  jz      loc_18006EEC3
0x18006eb75  mov     [rax+10Ch], r15d
0x18006eb7c  cmp     r15d, 9
0x18006eb80  jnz     short loc_18006EB8F
0x18006eb82  mov     rax, [rdi]
0x18006eb85  mov     dword ptr [rax+130h], 1
0x18006eb8f  mov     rax, gs:60h
0x18006eb98  mov     rcx, [rax+90h]
0x18006eb9f  test    rcx, rcx
0x18006eba2  jnz     loc_18006EF0C
0x18006eba8  cmp     byte ptr [r12], 0
0x18006ebad  jz      short loc_18006EBC5
0x18006ebaf  mov     rax, gs:60h
0x18006ebb8  test    byte ptr [rax+378h], 4
0x18006ebbf  jnz     loc_18006EF74
0x18006ebc5  mov     rcx, [rdi]
0x18006ebc8  xor     ebx, ebx
0x18006ebca  test    rcx, rcx
0x18006ebcd  mov     eax, 0C0000017h
0x18006ebd2  cmovz   ebx, eax
0x18006ebd5  cmp     r15d, 9
0x18006ebd9  jnz     loc_18006EEA7
0x18006ebdf  mov     ebx, 0C0000135h
0x18006ebe4  jmp     loc_18006EA92
0x18006ebe9  mov     rax, gs:30h
0x18006ebf2  mov     rdx, [rax+1850h]
0x18006ebf9  test    rdx, rdx
0x18006ebfc  jz      short loc_18006EC05
0x18006ebfe  xor     ecx, ecx
0x18006ec00  cmp     ecx, 8
0x18006ec03  jb      short loc_18006EC32
0x18006ec05  lock bts qword ptr [rbp+0], 0
0x18006ec0c  jb      loc_18006EEFF
0x18006ec12  mov     rcx, [rsi+98h]
0x18006ec19  mov     eax, [rcx+18h]
0x18006ec1c  cmp     eax, 0FFFFFFFFh
0x18006ec1f  jnz     loc_18006ED0A
0x18006ec25  mov     rcx, rbp
0x18006ec28  call    RtlReleaseSRWLockExclusive
0x18006ec2d  jmp     loc_18006EA92
0x18006ec32  cmp     qword ptr [rdx+rcx*8], 0
0x18006ec37  lea     r8, [rdx+rcx*8]
0x18006ec3b  jz      loc_18006EE84
0x18006ec41  inc     ecx
0x18006ec43  jmp     short loc_18006EC00
0x18006ec45  test    eax, eax
0x18006ec47  jnz     loc_18006EFC5
0x18006ec4d  cmp     byte ptr [rcx], 0
0x18006ec50  jz      loc_18006EA27
0x18006ec56  mov     rax, gs:60h
0x18006ec5f  test    byte ptr [rax+378h], 4
0x18006ec66  jz      loc_18006EA27
0x18006ec6c  call    RtlGetCurrentServiceSessionId
0x18006ec71  test    eax, eax
0x18006ec73  jz      loc_18006F004
0x18006ec79  mov     rax, gs:60h
0x18006ec82  mov     rax, [rax+90h]
0x18006ec89  add     rax, 22Bh
0x18006ec8f  test    byte ptr [rax], 20h
0x18006ec92  jz      loc_18006EA27
0x18006ec98  xor     r9d, r9d
0x18006ec9b  mov     qword ptr [rsp+98h+ArgList], 0
0x18006eca4  test    ebx, ebx
0x18006eca6  lea     rax, [rsp+98h+var_48]
0x18006ecab  mov     [rsp+98h+Format], rax
0x18006ecb0  cmovs   r9d, r13d
0x18006ecb4  jmp     loc_18006EE70
0x18006ecb9  mov     rax, [rcx]
0x18006ecbc  mov     ecx, [rax-38h]
0x18006ecbf  test    cl, 20h
0x18006ecc2  jnz     loc_18006EA86
0x18006ecc8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006eccf  lock xadd [rbx+114h], eax
0x18006ecd7  cmp     eax, 1
0x18006ecda  jnz     loc_18006EA86
0x18006ece0  mov     rcx, rbp
0x18006ece3  call    RtlAcquireSRWLockExclusive
0x18006ece8  lea     rax, [rbx+0A0h]
0x18006ecef  mov     rdx, [rax]
0x18006ecf2  cmp     [rdx+8], rax
0x18006ecf6  jnz     short loc_18006ED05
0x18006ecf8  mov     rcx, [rax+8]
0x18006ecfc  cmp     [rcx], rax
0x18006ecff  jz      loc_18006F03B
0x18006ed05  mov     rcx, r13
0x18006ed08  int     29h; Win8: RtlFailFast(ecx)
0x18006ed0a  test    eax, eax
0x18006ed0c  jz      loc_18006EFE1
0x18006ed12  inc     eax
0x18006ed14  mov     [rcx+18h], eax
0x18006ed17  mov     rcx, rbp
0x18006ed1a  call    RtlReleaseSRWLockExclusive
0x18006ed1f  jmp     loc_18006EA92
0x18006ed24  movups  [rsp+98h+var_48], xmm0
0x18006ed29  test    r14, r14
0x18006ed2c  jnz     loc_18006EF6C
0x18006ed32  lea     rdx, [rsp+98h+var_48]
0x18006ed37  xor     ecx, ecx
0x18006ed39  call    LdrpGetBaseNameFromFullName
0x18006ed3e  lea     r12, [rsp+98h+var_48]
0x18006ed43  mov     rcx, r12
0x18006ed46  mov     [rsp+98h+arg_28], r12
0x18006ed4e  call    LdrpHashUnicodeString
0x18006ed53  lea     rbp, LdrpModuleDatatableLock
0x18006ed5a  mov     ebx, eax
0x18006ed5c  mov     rcx, rbp
0x18006ed5f  call    RtlAcquireSRWLockShared
0x18006ed64  mov     r9, rdi
0x18006ed67  mov     dword ptr [rsp+98h+Format], ebx
0x18006ed6b  mov     r8d, esi
0x18006ed6e  xor     edx, edx
0x18006ed70  mov     rcx, r12
0x18006ed73  call    LdrpFindLoadedDllByNameLockHeld
0x18006ed78  mov     ebx, eax
0x18006ed7a  test    eax, eax
0x18006ed7c  js      loc_18006EE8C
0x18006ed82  mov     rax, [rdi]
0x18006ed85  mov     rcx, [rax+98h]
0x18006ed8c  mov     r12d, [rcx+38h]
0x18006ed90  mov     rcx, rbp
0x18006ed93  call    RtlReleaseSRWLockShared
0x18006ed98  mov     [rsp+98h+arg_18], 1
0x18006eda3  call    RtlGetCurrentServiceSessionId
0x18006eda8  test    eax, eax
0x18006edaa  jnz     loc_18006F015
0x18006edb0  mov     ecx, 7FFE0384h
0x18006edb5  cmp     byte ptr [rcx], 0
0x18006edb8  mov     r13d, 3
0x18006edbe  jz      loc_18006EA27
0x18006edc4  mov     rax, gs:60h
0x18006edcd  test    byte ptr [rax+378h], 4
0x18006edd4  jz      loc_18006EA27
0x18006edda  call    RtlGetCurrentServiceSessionId
0x18006eddf  test    eax, eax
0x18006ede1  jz      loc_18006F031
0x18006ede7  mov     rax, gs:60h
0x18006edf0  mov     rax, [rax+90h]
0x18006edf7  add     rax, 22Bh
0x18006edfd  test    byte ptr [rax], 20h
0x18006ee00  jz      loc_18006EA27
0x18006ee06  mov     rax, [rsp+98h+arg_28]
0x18006ee0e  xor     r9d, r9d
0x18006ee11  cmp     [rsp+98h+arg_18], r9d
0x18006ee19  mov     qword ptr [rsp+98h+ArgList], 0
0x18006ee22  cmovz   r9d, r13d
0x18006ee26  mov     [rsp+98h+Format], rax
0x18006ee2b  jmp     short loc_18006EE70
0x18006ee2d  call    RtlGetCurrentServiceSessionId
0x18006ee32  test    eax, eax
0x18006ee34  jz      loc_18006EEF5
0x18006ee3a  mov     rax, gs:60h
0x18006ee43  mov     rax, [rax+90h]
0x18006ee4a  add     rax, 22Bh
0x18006ee50  test    byte ptr [rax], 20h
0x18006ee53  jz      loc_18006EA27
0x18006ee59  xor     r9d, r9d
0x18006ee5c  mov     qword ptr [rsp+98h+ArgList], 0
0x18006ee65  test    ebx, ebx
0x18006ee67  mov     [rsp+98h+Format], r14
0x18006ee6c  cmovs   r9d, r13d
0x18006ee70  xor     r8d, r8d
0x18006ee73  xor     edx, edx
0x18006ee75  mov     ecx, 14A0h
0x18006ee7a  call    LdrpLogEtwEvent
0x18006ee7f  jmp     loc_18006EA27
0x18006ee84  mov     [r8], rbp
  ... truncated ...
```
