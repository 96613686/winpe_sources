# LdrpFindOrPrepareLoadingModule

- ea: `0x180051f50`
- end: `0x1800526de`
- name: `LdrpFindOrPrepareLoadingModule`
- size: `1934`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, service_task`

## callers

- `0x1800249a0`
- `0x180119f5c`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001861c`
- `0x18001b530`
- `0x18001b984`
- `0x18001eb80`
- `0x1800296e0`
- `0x18002dae0`
- `0x18004cef8`
- `0x180051314`
- `0x180051f50`
- `0x1800526f0`
- `0x180052720`
- `0x180053150`
- `0x180053dd0`
- `0x180053e34`
- `0x180053f30`
- `0x18006895c`
- `0x1800bf2ac`
- `0x1800e3320`
- `0x1800fda2c`
- `0x18012c830`
- `0x180163a80`

## string_xrefs

- `0x180052070`: `Found circular dependent DLL: "%wZ" that failed to load previously, ModuleState: %d\n`

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
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)v49, 0, a3, (_DWORD)a6, v50);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v51);
      v12 = 0;
      v72 = 0;
    }
    else
    {
      v12 = *(_DWORD *)(*(_QWORD *)(*a6 + 152) + 56LL);
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v51);
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
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((unsigned int)v70, (_DWORD)v11, a3, (_DWORD)a6, v13);
    if ( LoadedDllByNameLockHeld >= 0 )
      v12 = *(_DWORD *)(*(_QWORD *)(*a6 + 152) + 56LL);
    RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v14);
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
          SchedulerSharedDataSlot[i] = &LdrpModuleDatatableLock;
          break;
        }
      }
    }
    if ( _interlockedbittestandset64((volatile signed __int32 *)&LdrpModuleDatatableLock, 0) )
      RtlpAcquireSRWLockExclusiveContended(&LdrpModuleDatatableLock, SchedulerSharedDataSlot);
    v43 = *(_QWORD *)(v25 + 152);
    v44 = *(_DWORD *)(v43 + 24);
    if ( v44 != -1 )
    {
      if ( v44 )
      {
        *(_DWORD *)(v43 + 24) = v44 + 1;
        RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
        return (unsigned int)LoadedDllByNameLockHeld;
      }
      if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
        ++*(_DWORD *)(v43 + 28);
    }
    RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
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
      RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
      v47 = *(_QWORD *)(v26 + 160);
      if ( *(_QWORD *)(v47 + 8) != v26 + 160 || (v48 = *(_QWORD **)(v26 + 168), *v48 != v26 + 160) )
        __fastfail(3u);
      *v48 = v47;
      *(_QWORD *)(v47 + 8) = v48;
      v65 = *(_QWORD **)(v26 + 152);
      v66 = (_QWORD *)*v65;
      RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
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
0x180051f50  mov     [rsp+arg_0], rbx
0x180051f55  mov     [rsp+arg_8], rdx
0x180051f5a  push    rbp
0x180051f5b  push    rsi
0x180051f5c  push    rdi
0x180051f5d  push    r12
0x180051f5f  push    r13
0x180051f61  push    r14
0x180051f63  push    r15
0x180051f65  sub     rsp, 60h
0x180051f69  mov     rdi, [rsp+98h+arg_28]
0x180051f71  xorps   xmm0, xmm0
0x180051f74  mov     r15d, r9d
0x180051f77  mov     esi, r8d
0x180051f7a  mov     rbp, rdx
0x180051f7d  mov     r14, rcx
0x180051f80  movups  [rsp+98h+var_58], xmm0
0x180051f85  mov     qword ptr [rdi], 0
0x180051f8c  cmp     r9d, 9
0x180051f90  jz      loc_180052551
0x180051f96  test    sil, 20h
0x180051f9a  jnz     loc_180052344
0x180051fa0  bt      r8d, 9
0x180051fa5  jnb     loc_1800520D5
0x180051fab  lea     rdx, [rsp+98h+var_48]
0x180051fb0  xor     r12d, r12d
0x180051fb3  movups  [rsp+98h+var_48], xmm0
0x180051fb8  call    LdrpGetBaseNameFromFullName
0x180051fbd  lea     rcx, [rsp+98h+var_48]
0x180051fc2  call    LdrpHashUnicodeString
0x180051fc7  lea     rbp, LdrpModuleDatatableLock
0x180051fce  mov     ebx, eax
0x180051fd0  mov     rcx, rbp
0x180051fd3  call    RtlAcquireSRWLockShared
0x180051fd8  mov     r9, rdi
0x180051fdb  mov     dword ptr [rsp+98h+Format], ebx
0x180051fdf  mov     r8d, esi
0x180051fe2  lea     rcx, [rsp+98h+var_48]
0x180051fe7  mov     rdx, r14
0x180051fea  call    LdrpFindLoadedDllByNameLockHeld
0x180051fef  mov     ebx, eax
0x180051ff1  test    eax, eax
0x180051ff3  js      short loc_180052003
0x180051ff5  mov     rax, [rdi]
0x180051ff8  mov     rcx, [rax+98h]
0x180051fff  mov     r12d, [rcx+38h]
0x180052003  mov     rcx, rbp
0x180052006  call    RtlReleaseSRWLockShared
0x18005200b  mov     r13d, 3
0x180052011  call    RtlGetCurrentServiceSessionId
0x180052016  mov     ecx, 7FFE0384h
0x18005201b  test    r14, r14
0x18005201e  jz      loc_180052265
0x180052024  test    eax, eax
0x180052026  jnz     loc_1800524F9
0x18005202c  cmp     byte ptr [rcx], 0
0x18005202f  jz      short loc_180052047
0x180052031  mov     rax, gs:60h
0x18005203a  test    byte ptr [rax+378h], 4
0x180052041  jnz     loc_18005244D
0x180052047  cmp     ebx, 0C0000135h
0x18005204d  jz      short loc_1800520CD
0x18005204f  mov     rsi, [rdi]
0x180052052  test    r12d, r12d
0x180052055  jns     loc_180052209
0x18005205b  lea     rax, [rsi+48h]
0x18005205f  mov     [rsp+98h+var_68], r12d
0x180052064  mov     qword ptr [rsp+98h+ArgList], rax; ArgList
0x180052069  lea     r8, aLdrpfindorprep; "LdrpFindOrPrepareLoadingModule"
0x180052070  lea     rax, aFoundCircularD; "Found circular dependent DLL: \"%wZ\" t"...
0x180052077  xor     r9d, r9d; int
0x18005207a  mov     edx, 0DC2h; int
0x18005207f  mov     [rsp+98h+Format], rax; Format
0x180052084  lea     rcx, aMinkernelLdrLd_0; "minkernel\\ldr\\ldrmap.c"
0x18005208b  call    LdrpLogInternal
0x180052090  mov     rbx, [rdi]
0x180052093  mov     rcx, [rbx+98h]
0x18005209a  mov     eax, [rcx+18h]
0x18005209d  cmp     eax, 0FFFFFFFFh
0x1800520a0  jnz     loc_1800522D9
0x1800520a6  mov     ebx, 0C00000E5h
0x1800520ab  mov     qword ptr [rdi], 0
0x1800520b2  mov     eax, ebx
0x1800520b4  mov     rbx, [rsp+98h+arg_0]
0x1800520bc  add     rsp, 60h
0x1800520c0  pop     r15
0x1800520c2  pop     r14
0x1800520c4  pop     r13
0x1800520c6  pop     r12
0x1800520c8  pop     rdi
0x1800520c9  pop     rsi
0x1800520ca  pop     rbp
0x1800520cb  retn
0x1800520cd  mov     rbp, [rsp+98h+arg_8]
0x1800520d5  mov     edx, cs:NtdllBaseTag
0x1800520db  mov     r12d, 7FFE0384h
0x1800520e1  mov     rcx, cs:LdrpHeap
0x1800520e8  add     edx, 40000h
0x1800520ee  mov     qword ptr [rdi], 0
0x1800520f5  or      edx, 8
0x1800520f8  movzx   r8d, word ptr [r14]
0x1800520fc  add     r8, 0D2h
0x180052103  call    RtlAllocateHeap_0
0x180052108  mov     rbx, rax
0x18005210b  test    rax, rax
0x18005210e  jz      loc_1800521E5
0x180052114  mov     rcx, [rsp+98h+arg_30]
0x18005211c  bts     esi, 0Fh
0x180052120  mov     [rax+28h], rcx
0x180052124  mov     rcx, [rsp+98h+arg_20]
0x18005212c  mov     [rax+30h], rcx
0x180052130  lea     rcx, [rbx+0D0h]; void *
0x180052137  mov     [rax+20h], esi
0x18005213a  mov     [rax+10h], rbp
0x18005213e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180052145  mov     [rbx+0B8h], rax
0x18005214c  mov     [rbx+8], rcx
0x180052150  movzx   eax, word ptr [r14]
0x180052154  mov     [rbx], ax
0x180052157  movzx   eax, word ptr [r14]
0x18005215b  add     ax, 2
0x18005215f  mov     [rbx+2], ax
0x180052163  movzx   r8d, word ptr [r14]; Size
0x180052167  mov     rdx, [r14+8]; Src
0x18005216b  call    memmove
0x180052170  movzx   edx, word ptr [r14]
0x180052174  xor     eax, eax
0x180052176  mov     rcx, [rbx+8]
0x18005217a  shr     rdx, 1
0x18005217d  mov     [rcx+rdx*2], ax
0x180052181  mov     rcx, rbx
0x180052184  call    LdrpAllocateModuleEntry
0x180052189  mov     [rdi], rax
0x18005218c  test    rax, rax
0x18005218f  jz      loc_1800524E3
0x180052195  mov     [rax+10Ch], r15d
0x18005219c  cmp     r15d, 9
0x1800521a0  jnz     short loc_1800521AF
0x1800521a2  mov     rax, [rdi]
0x1800521a5  mov     dword ptr [rax+130h], 1
0x1800521af  mov     rax, gs:60h
0x1800521b8  mov     rcx, [rax+90h]
0x1800521bf  test    rcx, rcx
0x1800521c2  jnz     loc_18005252C
0x1800521c8  cmp     byte ptr [r12], 0
0x1800521cd  jz      short loc_1800521E5
0x1800521cf  mov     rax, gs:60h
0x1800521d8  test    byte ptr [rax+378h], 4
0x1800521df  jnz     loc_180052594
0x1800521e5  mov     rcx, [rdi]
0x1800521e8  xor     ebx, ebx
0x1800521ea  test    rcx, rcx
0x1800521ed  mov     eax, 0C0000017h
0x1800521f2  cmovz   ebx, eax
0x1800521f5  cmp     r15d, 9
0x1800521f9  jnz     loc_1800524C7
0x1800521ff  mov     ebx, 0C0000135h
0x180052204  jmp     loc_1800520B2
0x180052209  mov     rax, gs:30h
0x180052212  mov     rdx, [rax+1850h]
0x180052219  test    rdx, rdx
0x18005221c  jz      short loc_180052225
0x18005221e  xor     ecx, ecx
0x180052220  cmp     ecx, 8
0x180052223  jb      short loc_180052252
0x180052225  lock bts qword ptr [rbp+0], 0
0x18005222c  jb      loc_18005251F
0x180052232  mov     rcx, [rsi+98h]
0x180052239  mov     eax, [rcx+18h]
0x18005223c  cmp     eax, 0FFFFFFFFh
0x18005223f  jnz     loc_18005232A
0x180052245  mov     rcx, rbp
0x180052248  call    RtlReleaseSRWLockExclusive
0x18005224d  jmp     loc_1800520B2
0x180052252  cmp     qword ptr [rdx+rcx*8], 0
0x180052257  lea     r8, [rdx+rcx*8]
0x18005225b  jz      loc_1800524A4
0x180052261  inc     ecx
0x180052263  jmp     short loc_180052220
0x180052265  test    eax, eax
0x180052267  jnz     loc_1800525E5
0x18005226d  cmp     byte ptr [rcx], 0
0x180052270  jz      loc_180052047
0x180052276  mov     rax, gs:60h
0x18005227f  test    byte ptr [rax+378h], 4
0x180052286  jz      loc_180052047
0x18005228c  call    RtlGetCurrentServiceSessionId
0x180052291  test    eax, eax
0x180052293  jz      loc_180052624
0x180052299  mov     rax, gs:60h
0x1800522a2  mov     rax, [rax+90h]
0x1800522a9  add     rax, 22Bh
0x1800522af  test    byte ptr [rax], 20h
0x1800522b2  jz      loc_180052047
0x1800522b8  xor     r9d, r9d
0x1800522bb  mov     qword ptr [rsp+98h+ArgList], 0
0x1800522c4  test    ebx, ebx
0x1800522c6  lea     rax, [rsp+98h+var_48]
0x1800522cb  mov     [rsp+98h+Format], rax
0x1800522d0  cmovs   r9d, r13d
0x1800522d4  jmp     loc_180052490
0x1800522d9  mov     rax, [rcx]
0x1800522dc  mov     ecx, [rax-38h]
0x1800522df  test    cl, 20h
0x1800522e2  jnz     loc_1800520A6
0x1800522e8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800522ef  lock xadd [rbx+114h], eax
0x1800522f7  cmp     eax, 1
0x1800522fa  jnz     loc_1800520A6
0x180052300  mov     rcx, rbp
0x180052303  call    RtlAcquireSRWLockExclusive
0x180052308  lea     rax, [rbx+0A0h]
0x18005230f  mov     rdx, [rax]
0x180052312  cmp     [rdx+8], rax
0x180052316  jnz     short loc_180052325
0x180052318  mov     rcx, [rax+8]
0x18005231c  cmp     [rcx], rax
0x18005231f  jz      loc_18005265B
0x180052325  mov     rcx, r13
0x180052328  int     29h; Win8: RtlFailFast(ecx)
0x18005232a  test    eax, eax
0x18005232c  jz      loc_180052601
0x180052332  inc     eax
0x180052334  mov     [rcx+18h], eax
0x180052337  mov     rcx, rbp
0x18005233a  call    RtlReleaseSRWLockExclusive
0x18005233f  jmp     loc_1800520B2
0x180052344  movups  [rsp+98h+var_48], xmm0
0x180052349  test    r14, r14
0x18005234c  jnz     loc_18005258C
0x180052352  lea     rdx, [rsp+98h+var_48]
0x180052357  xor     ecx, ecx
0x180052359  call    LdrpGetBaseNameFromFullName
0x18005235e  lea     r12, [rsp+98h+var_48]
0x180052363  mov     rcx, r12
0x180052366  mov     [rsp+98h+arg_28], r12
0x18005236e  call    LdrpHashUnicodeString
0x180052373  lea     rbp, LdrpModuleDatatableLock
0x18005237a  mov     ebx, eax
0x18005237c  mov     rcx, rbp
0x18005237f  call    RtlAcquireSRWLockShared
0x180052384  mov     r9, rdi
0x180052387  mov     dword ptr [rsp+98h+Format], ebx
0x18005238b  mov     r8d, esi
0x18005238e  xor     edx, edx
0x180052390  mov     rcx, r12
0x180052393  call    LdrpFindLoadedDllByNameLockHeld
0x180052398  mov     ebx, eax
0x18005239a  test    eax, eax
0x18005239c  js      loc_1800524AC
0x1800523a2  mov     rax, [rdi]
0x1800523a5  mov     rcx, [rax+98h]
0x1800523ac  mov     r12d, [rcx+38h]
0x1800523b0  mov     rcx, rbp
0x1800523b3  call    RtlReleaseSRWLockShared
0x1800523b8  mov     [rsp+98h+arg_18], 1
0x1800523c3  call    RtlGetCurrentServiceSessionId
0x1800523c8  test    eax, eax
0x1800523ca  jnz     loc_180052635
0x1800523d0  mov     ecx, 7FFE0384h
0x1800523d5  cmp     byte ptr [rcx], 0
0x1800523d8  mov     r13d, 3
0x1800523de  jz      loc_180052047
0x1800523e4  mov     rax, gs:60h
0x1800523ed  test    byte ptr [rax+378h], 4
0x1800523f4  jz      loc_180052047
0x1800523fa  call    RtlGetCurrentServiceSessionId
0x1800523ff  test    eax, eax
0x180052401  jz      loc_180052651
0x180052407  mov     rax, gs:60h
0x180052410  mov     rax, [rax+90h]
0x180052417  add     rax, 22Bh
0x18005241d  test    byte ptr [rax], 20h
0x180052420  jz      loc_180052047
0x180052426  mov     rax, [rsp+98h+arg_28]
0x18005242e  xor     r9d, r9d
0x180052431  cmp     [rsp+98h+arg_18], r9d
0x180052439  mov     qword ptr [rsp+98h+ArgList], 0
0x180052442  cmovz   r9d, r13d
0x180052446  mov     [rsp+98h+Format], rax
0x18005244b  jmp     short loc_180052490
0x18005244d  call    RtlGetCurrentServiceSessionId
0x180052452  test    eax, eax
0x180052454  jz      loc_180052515
0x18005245a  mov     rax, gs:60h
0x180052463  mov     rax, [rax+90h]
0x18005246a  add     rax, 22Bh
0x180052470  test    byte ptr [rax], 20h
0x180052473  jz      loc_180052047
0x180052479  xor     r9d, r9d
0x18005247c  mov     qword ptr [rsp+98h+ArgList], 0
0x180052485  test    ebx, ebx
0x180052487  mov     [rsp+98h+Format], r14
0x18005248c  cmovs   r9d, r13d
0x180052490  xor     r8d, r8d
0x180052493  xor     edx, edx
0x180052495  mov     ecx, 14A0h
0x18005249a  call    LdrpLogEtwEvent
0x18005249f  jmp     loc_180052047
0x1800524a4  mov     [r8], rbp
  ... truncated ...
```
