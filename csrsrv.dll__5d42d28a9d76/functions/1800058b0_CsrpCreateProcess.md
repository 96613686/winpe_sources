# CsrpCreateProcess

- ea: `0x1800058b0`
- end: `0x180006266`
- name: `CsrpCreateProcess`
- size: `2486`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, _DWORD *, __int64, __int16, int *, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800030a0`
- `0x180005870`
- `0x180005880`

## callees

- `0x180002a00`
- `0x1800058b0`
- `0x18000ab55`
- `0x18000ab61`
- `0x18000ab80`
- `0x18000b010`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180005a1c`
- `ntdll!NtOpenProcessToken` at `0x180005a1c`
- `ntdll!RtlAllocateHeap` at `0x180005971`
- `ntdll!RtlAllocateHeap` at `0x180005bf4`
- `ntdll!RtlAllocateHeap` at `0x180005971`
- `ntdll!RtlAllocateHeap` at `0x180005bf4`
- `ntdll!NtQueryInformationToken` at `0x180005a4e`
- `ntdll!NtQueryInformationToken` at `0x180005a4e`
- `ntdll!NtClose` at `0x180005a61`
- `ntdll!NtClose` at `0x180006240`
- `ntdll!NtClose` at `0x180005a61`
- `ntdll!NtClose` at `0x180006240`
- `ntdll!RtlFreeHeap` at `0x180006095`
- `ntdll!RtlFreeHeap` at `0x1800060fb`
- `ntdll!RtlFreeHeap` at `0x180006113`
- `ntdll!RtlFreeHeap` at `0x180006203`
- `ntdll!RtlFreeHeap` at `0x180006095`
- `ntdll!RtlFreeHeap` at `0x1800060fb`
- `ntdll!RtlFreeHeap` at `0x180006113`
- `ntdll!RtlFreeHeap` at `0x180006203`
- `ntdll!RtlEnterCriticalSection` at `0x180005909`
- `ntdll!RtlEnterCriticalSection` at `0x180005909`
- `ntdll!NtSetInformationProcess` at `0x180005b63`
- `ntdll!NtSetInformationProcess` at `0x180005f93`
- `ntdll!NtSetInformationProcess` at `0x180006063`
- `ntdll!NtSetInformationProcess` at `0x180005b63`
- `ntdll!NtSetInformationProcess` at `0x180005f93`
- `ntdll!NtSetInformationProcess` at `0x180006063`
- `ntdll!NtQueryInformationThread` at `0x180005bc5`
- `ntdll!NtQueryInformationThread` at `0x180005c60`
- `ntdll!NtQueryInformationThread` at `0x180005bc5`
- `ntdll!NtQueryInformationThread` at `0x180005c60`
- `ntdll!RtlLeaveCriticalSection` at `0x180005dec`
- `ntdll!RtlLeaveCriticalSection` at `0x180006004`
- `ntdll!RtlLeaveCriticalSection` at `0x1800060a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006126`
- `ntdll!RtlLeaveCriticalSection` at `0x180006216`
- `ntdll!RtlLeaveCriticalSection` at `0x180006253`
- `ntdll!RtlLeaveCriticalSection` at `0x180005dec`
- `ntdll!RtlLeaveCriticalSection` at `0x180006004`
- `ntdll!RtlLeaveCriticalSection` at `0x1800060a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006126`
- `ntdll!RtlLeaveCriticalSection` at `0x180006216`
- `ntdll!RtlLeaveCriticalSection` at `0x180006253`
- `ntdll!NtOpenThreadToken` at `0x18000614e`
- `ntdll!NtOpenThreadToken` at `0x18000614e`

## pseudocode

```c
__int64 __fastcall CsrpCreateProcess(HANDLE Handle, void *a2, _DWORD *a3, __int64 a4, __int16 a5, int *a6, _QWORD *a7)
{
  _QWORD *v10; // rax
  unsigned int v11; // ebx
  _OWORD *Heap; // rax
  _OWORD *v13; // rdi
  int v14; // eax
  _OWORD *v15; // r15
  int v16; // r12d
  __int64 v17; // rbx
  NTSTATUS v18; // ebx
  void *v19; // rbx
  __int64 v20; // r14
  __int64 v21; // rsi
  __int64 v22; // rsi
  __int64 v23; // rsi
  __int64 v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rax
  __int16 v27; // si
  NTSTATUS v28; // eax
  int v29; // eax
  HANDLE v30; // r14
  NTSTATUS InformationThread; // ebx
  char *v32; // rax
  char *v33; // rbx
  __int128 v34; // xmm0
  NTSTATUS v35; // r14d
  _QWORD *v36; // rcx
  __int64 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int128 v40; // xmm0
  _QWORD *v41; // r8
  __int64 v42; // rcx
  _QWORD *v43; // rdx
  __int64 v44; // rbx
  void (__fastcall *v45)(__int64, _OWORD *); // rax
  void (__fastcall *v46)(__int64, _OWORD *); // rax
  void (__fastcall *v47)(__int64, _OWORD *); // rax
  void (__fastcall *v48)(__int64, _OWORD *); // rax
  void (__fastcall *v49)(__int64, _OWORD *); // rax
  void (__fastcall *v50)(__int64, _OWORD *); // rax
  int v52; // ecx
  _OWORD *v53; // rax
  NTSTATUS v54; // eax
  int Thread; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-A1h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-99h] BYREF
  __int64 v58; // [rsp+40h] [rbp-91h]
  HANDLE ProcessHandle; // [rsp+48h] [rbp-89h]
  HANDLE ThreadHandle; // [rsp+50h] [rbp-81h]
  __int64 v61; // [rsp+58h] [rbp-79h]
  _QWORD *v62; // [rsp+60h] [rbp-71h]
  int *v63; // [rsp+68h] [rbp-69h]
  _OWORD ThreadInformation[2]; // [rsp+70h] [rbp-61h] BYREF
  _OWORD TokenInformation[3]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-11h]

  v63 = a6;
  ProcessHandle = Handle;
  v62 = a7;
  v61 = a4;
  ThreadHandle = a2;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  v10 = (_QWORD *)(CsrRootProcess + 16);
  while ( *(v10 - 2) != *(_QWORD *)a3 )
  {
    v10 = (_QWORD *)*v10;
    if ( v10 == (_QWORD *)(CsrRootProcess + 16) )
    {
      v11 = CsrTotalPerProcessDataLength + 192;
      Heap = RtlAllocateHeap(CsrHeap, CsrBaseTag + 786432, (unsigned int)(CsrTotalPerProcessDataLength + 192));
      v13 = Heap;
      if ( !Heap )
      {
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        return 3221225495LL;
      }
      memset_0(Heap, 0, v11);
      v14 = ProcessSequenceCount;
      *((_DWORD *)v13 + 22) = ProcessSequenceCount;
      ProcessSequenceCount = v14 + 1;
      if ( (unsigned int)(v14 + 1) < 5 )
        ProcessSequenceCount = 5;
      *((_DWORD *)v13 + 25) = 1;
      v15 = v13 + 2;
      v16 = 0;
      *((_QWORD *)v13 + 5) = v13 + 2;
      *((_QWORD *)v13 + 4) = v13 + 2;
      v17 = -1;
      v66 = 0;
      ReturnLength = 0;
      TokenHandle = (void *)-1LL;
      memset(TokenInformation, 0, sizeof(TokenInformation));
      if ( Handle )
      {
        v17 = (__int64)Handle;
        goto LABEL_9;
      }
      v54 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
      if ( v54 >= 0 )
      {
LABEL_10:
        v18 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
        NtClose(TokenHandle);
        if ( v18 < 0 )
          goto LABEL_85;
        *((_QWORD *)v13 + 16) = *((_QWORD *)&TokenInformation[0] + 1);
      }
      else
      {
        if ( v54 == -1073741700 )
        {
LABEL_9:
          if ( NtOpenProcessToken((HANDLE)v17, 8u, &TokenHandle) >= 0 )
            goto LABEL_10;
        }
LABEL_85:
        *((_QWORD *)v13 + 16) = 0;
      }
      v19 = (void *)(((unsigned __int64)v13 + 191) & 0xFFFFFFFFFFFFFFF8uLL);
      v20 = *((_QWORD *)KeGetPcr()->Unused1[1] + 7);
      _mm_lfence();
      v21 = CsrLoadedServerDll[0];
      if ( CsrLoadedServerDll[0] && *(_DWORD *)(CsrLoadedServerDll[0] + 64) )
      {
        *((_QWORD *)v13 + 17) = v19;
        memcpy_0(
          (void *)(((unsigned __int64)v13 + 191) & 0xFFFFFFFFFFFFFFF8uLL),
          *(const void **)(v20 + 136),
          *(unsigned int *)(v21 + 64));
        v19 = (void *)(((unsigned __int64)v19 + *(unsigned int *)(v21 + 64) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        *((_QWORD *)v13 + 17) = 0;
      }
      v22 = qword_180010368;
      if ( qword_180010368 && *(_DWORD *)(qword_180010368 + 64) )
      {
        *((_QWORD *)v13 + 18) = v19;
        memcpy_0(v19, *(const void **)(v20 + 144), *(unsigned int *)(v22 + 64));
        v19 = (void *)(((unsigned __int64)v19 + *(unsigned int *)(v22 + 64) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        *((_QWORD *)v13 + 18) = 0;
      }
      v23 = qword_180010370;
      if ( qword_180010370 && *(_DWORD *)(qword_180010370 + 64) )
      {
        *((_QWORD *)v13 + 19) = v19;
        memcpy_0(v19, *(const void **)(v20 + 152), *(unsigned int *)(v23 + 64));
        v19 = (void *)(((unsigned __int64)v19 + *(unsigned int *)(v23 + 64) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        *((_QWORD *)v13 + 19) = 0;
      }
      v24 = qword_180010378;
      if ( qword_180010378 && *(_DWORD *)(qword_180010378 + 64) )
      {
        *((_QWORD *)v13 + 20) = v19;
        memcpy_0(v19, *(const void **)(v20 + 160), *(unsigned int *)(v24 + 64));
        v19 = (void *)(((unsigned __int64)v19 + *(unsigned int *)(v24 + 64) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        *((_QWORD *)v13 + 20) = 0;
      }
      v25 = qword_180010380;
      if ( qword_180010380 && *(_DWORD *)(qword_180010380 + 64) )
      {
        *((_QWORD *)v13 + 21) = v19;
        memcpy_0(v19, *(const void **)(v20 + 168), *(unsigned int *)(v25 + 64));
        v19 = (void *)(((unsigned __int64)v19 + *(unsigned int *)(v25 + 64) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        *((_QWORD *)v13 + 21) = 0;
      }
      v26 = qword_180010388;
      if ( qword_180010388 && *(_DWORD *)(qword_180010388 + 64) )
      {
        *((_QWORD *)v13 + 22) = v19;
        memcpy_0(v19, *(const void **)(v20 + 176), *(unsigned int *)(v26 + 64));
      }
      else
      {
        *((_QWORD *)v13 + 22) = 0;
      }
      v27 = a5;
      v58 = 0;
      TokenHandle = CsrApiPort;
      if ( (a5 & 0x80u) == 0 )
      {
        if ( (a5 & 0x100) == 0 )
        {
          v28 = NtSetInformationProcess(ProcessHandle, ProcessExceptionPort, &CsrApiPort, 8u);
          goto LABEL_27;
        }
        if ( NtSetInformationProcess(ProcessHandle, ProcessExceptionPort, &TokenHandle, 0x10u) >= 0 )
        {
          *((_DWORD *)v13 + 23) |= 0x100u;
          if ( (v58 & 1) != 0 )
            v16 = 1;
          if ( (a5 & 0x800) != 0 || (v58 & 2) != 0 )
          {
            v16 |= 2u;
            if ( (v58 & 2) != 0 )
              v16 |= 8u;
          }
          else
          {
            v27 = a5 | 0x20;
          }
          if ( (v58 & 4) != 0 )
            v27 |= 4u;
          goto LABEL_28;
        }
LABEL_95:
        RtlFreeHeap(CsrHeap, 0, v13);
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        return 3221225495LL;
      }
      *((_DWORD *)v13 + 23) |= 0x80u;
      LODWORD(v58) = (a5 & 0x200) != 0;
      v52 = v58;
      if ( (a5 & 0x400) != 0 )
      {
        v52 = v58 | 2;
        LODWORD(v58) = v58 | 2;
      }
      if ( (a5 & 4) != 0 )
        LODWORD(v58) = v52 | 4;
      v28 = NtSetInformationProcess(ProcessHandle, ProcessExceptionPort, &TokenHandle, 0x10u);
LABEL_27:
      if ( v28 < 0 )
        goto LABEL_95;
LABEL_28:
      if ( (v27 & 4) != 0 )
      {
        *((_DWORD *)v13 + 26) = *a3;
        v29 = *((_DWORD *)v13 + 22);
      }
      else
      {
        *((_DWORD *)v13 + 26) = *(_DWORD *)(v20 + 104);
        v29 = *(_DWORD *)(v20 + 108);
      }
      *((_DWORD *)v13 + 27) = v29;
      if ( (v27 & 0x20) != 0 )
        *((_DWORD *)v13 + 23) |= 0x20u;
      if ( (v27 & 0x2000) != 0 )
        *((_DWORD *)v13 + 23) |= 0x2000u;
      v30 = ThreadHandle;
      InformationThread = NtQueryInformationThread(ThreadHandle, ThreadTimes, ThreadInformation, 0x20u, 0);
      if ( InformationThread < 0 )
      {
        RtlFreeHeap(CsrHeap, 0, v13);
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
        return (unsigned int)InformationThread;
      }
      v32 = (char *)RtlAllocateHeap(CsrHeap, CsrBaseTag + 0x100000, 0x58u);
      v33 = v32;
      if ( !v32 )
        goto LABEL_95;
      memset_0(v32, 0, 0x58u);
      *((_DWORD *)v33 + 19) = 1;
      _InterlockedIncrement((volatile signed __int32 *)v13 + 25);
      *((_QWORD *)v33 + 7) = v13;
      *(_QWORD *)v33 = *(_QWORD *)&ThreadInformation[0];
      v34 = *(_OWORD *)a3;
      *((_QWORD *)v33 + 8) = v30;
      *((_DWORD *)v33 + 18) = 0;
      *(_OWORD *)(v33 + 40) = v34;
      ReturnLength = 0;
      v35 = NtQueryInformationThread(v30, ThreadIsTerminated, &ReturnLength, 4u, 0);
      if ( v35 >= 0 )
      {
        if ( ReturnLength != 1 )
        {
          v36 = (_QWORD *)*((_QWORD *)v13 + 5);
          if ( (_OWORD *)*v36 != v15 )
            goto LABEL_76;
          *((_QWORD *)v33 + 2) = v36;
          *((_QWORD *)v33 + 1) = v15;
          *v36 = v33 + 8;
          *((_QWORD *)v13 + 5) = v33 + 8;
          v37 = &CsrThreadHashTable[2 * ((*((_DWORD *)v33 + 12) >> 2) & 0x3FF)];
          v38 = *v37;
          if ( *(__int64 **)(*v37 + 8) != v37 )
            goto LABEL_76;
          *((_QWORD *)v33 + 3) = v38;
          *((_QWORD *)v33 + 4) = v37;
          *(_QWORD *)(v38 + 8) = v33 + 24;
          *v37 = (__int64)(v33 + 24);
          v39 = v61;
          _InterlockedIncrement((volatile signed __int32 *)(v61 + 20));
          *((_QWORD *)v13 + 6) = v39;
          v40 = *(_OWORD *)a3;
          *((_QWORD *)v13 + 10) = ProcessHandle;
          *v13 = v40;
          *((_DWORD *)v13 + 30) = 640;
          v41 = KeGetPcr()->Unused1[1];
          v42 = CsrRootProcess + 16;
          v43 = *(_QWORD **)(CsrRootProcess + 24);
          if ( *v43 != CsrRootProcess + 16 )
LABEL_76:
            __fastfail(3u);
          v44 = v41[7];
          *((_QWORD *)v13 + 2) = v42;
          *((_QWORD *)v13 + 3) = v43;
          *v43 = v13 + 1;
          *(_QWORD *)(v42 + 8) = v13 + 1;
          if ( *((char *)v13 + 92) >= 0 )
          {
            _mm_lfence();
            if ( CsrLoadedServerDll[0] )
            {
              v45 = *(void (__fastcall **)(__int64, _OWORD *))(CsrLoadedServerDll[0] + 104);
              if ( v45 )
                v45(v44, v13);
            }
            if ( qword_180010368 )
            {
              v46 = *(void (__fastcall **)(__int64, _OWORD *))(qword_180010368 + 104);
              if ( v46 )
                v46(v44, v13);
            }
            if ( qword_180010370 )
            {
              v47 = *(void (__fastcall **)(__int64, _OWORD *))(qword_180010370 + 104);
              if ( v47 )
                v47(v44, v13);
            }
            if ( qword_180010378 )
            {
              v48 = *(void (__fastcall **)(__int64, _OWORD *))(qword_180010378 + 104);
              if ( v48 )
                v48(v44, v13);
            }
            if ( qword_180010380 )
            {
              v49 = *(void (__fastcall **)(__int64, _OWORD *))(qword_180010380 + 104);
              if ( v49 )
                v49(v44, v13);
            }
            if ( qword_180010388 )
            {
              v50 = *(void (__fastcall **)(__int64, _OWORD *))(qword_180010388 + 104);
              if ( v50 )
                v50(v44, v13);
            }
          }
          if ( v62 )
          {
            v53 = 0;
            if ( (v27 & 0x100) != 0 )
              v53 = v13;
            *v62 = v53;
          }
          RtlLeaveCriticalSection(&CsrProcessStructureLock);
          if ( v63 )
            *v63 = v16;
          return 0;
        }
        v35 = -1073741749;
      }
      RtlFreeHeap(CsrHeap, 0, v33);
      RtlFreeHeap(CsrHeap, 0, v13);
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
      return (unsigned int)v35;
    }
  }
  Thread = CsrCreateThread(v10 - 2, a2, a3, 0);
  if ( Thread >= 0 )
    NtClose(Handle);
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return (unsigned int)Thread;
}

```

## disassembly

```asm
0x1800058b0  push    rbp
0x1800058b2  push    rbx
0x1800058b3  push    rsi
0x1800058b4  push    r13
0x1800058b6  lea     rbp, [rsp-27h]
0x1800058bb  sub     rsp, 0F8h
0x1800058c2  mov     rax, cs:__security_cookie
0x1800058c9  xor     rax, rsp
0x1800058cc  mov     [rbp+3Fh+var_48], rax
0x1800058d0  mov     rax, [rbp+3Fh+arg_28]
0x1800058d4  xorps   xmm0, xmm0
0x1800058d7  mov     [rbp+3Fh+var_A8], rax
0x1800058db  mov     rsi, rcx
0x1800058de  mov     rax, [rbp+3Fh+arg_30]
0x1800058e2  mov     r13, r8
0x1800058e5  mov     [rsp+110h+ProcessHandle], rcx
0x1800058ea  mov     rbx, rdx
0x1800058ed  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800058f4  mov     [rbp+3Fh+var_B0], rax
0x1800058f8  mov     [rbp+3Fh+var_B8], r9
0x1800058fc  mov     [rsp+110h+ThreadHandle], rdx
0x180005901  movups  [rbp+3Fh+ThreadInformation], xmm0
0x180005905  movups  [rbp+3Fh+var_90], xmm0
0x180005909  call    cs:__imp_RtlEnterCriticalSection
0x180005910  nop     dword ptr [rax+rax+00h]
0x180005915  mov     rdx, cs:CsrRootProcess
0x18000591c  mov     r8, [r13+0]
0x180005920  add     rdx, 10h
0x180005924  mov     rax, rdx
0x180005927  nop     word ptr [rax+rax+00000000h]
0x180005930  cmp     [rax-10h], r8
0x180005934  lea     rcx, [rax-10h]
0x180005938  jz      loc_180006229
0x18000593e  mov     rax, [rax]
0x180005941  cmp     rax, rdx
0x180005944  jnz     short loc_180005930
0x180005946  mov     eax, cs:CsrTotalPerProcessDataLength
0x18000594c  mov     edx, cs:CsrBaseTag
0x180005952  add     eax, 0C0h
0x180005957  mov     rcx, cs:CsrHeap; HeapHandle
0x18000595e  add     edx, 0C0000h; Flags
0x180005964  mov     r8d, eax; Size
0x180005967  mov     [rsp+110h+var_20], rdi
0x18000596f  mov     ebx, eax
0x180005971  call    cs:__imp_RtlAllocateHeap
0x180005978  nop     dword ptr [rax+rax+00h]
0x18000597d  mov     rdi, rax
0x180005980  test    rax, rax
0x180005983  jz      loc_180005FFD
0x180005989  mov     [rsp+110h+var_28], r12
0x180005991  mov     r8d, ebx; Size
0x180005994  mov     [rsp+110h+var_30], r14
0x18000599c  xor     edx, edx; Val
0x18000599e  mov     rcx, rax; void *
0x1800059a1  mov     [rsp+110h+var_38], r15
0x1800059a9  call    memset_0
0x1800059ae  mov     eax, cs:ProcessSequenceCount
0x1800059b4  mov     [rdi+58h], eax
0x1800059b7  inc     eax
0x1800059b9  mov     cs:ProcessSequenceCount, eax
0x1800059bf  cmp     eax, 5
0x1800059c2  jb      loc_1800061D2
0x1800059c8  xorps   xmm0, xmm0
0x1800059cb  mov     dword ptr [rdi+64h], 1
0x1800059d2  xor     eax, eax
0x1800059d4  lea     r15, [rdi+20h]
0x1800059d8  xor     r12d, r12d
0x1800059db  mov     [r15+8], r15
0x1800059df  mov     [r15], r15
0x1800059e2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800059e9  mov     [rbp+3Fh+var_50], rax
0x1800059ed  mov     [rsp+110h+var_E0], r12d
0x1800059f2  mov     [rsp+110h+TokenHandle], rbx
0x1800059f7  movups  [rbp+3Fh+TokenInformation], xmm0
0x1800059fb  movups  [rbp+3Fh+var_70], xmm0
0x1800059ff  movups  [rbp+3Fh+var_60], xmm0
0x180005a03  test    rsi, rsi
0x180005a06  jz      loc_18000613A
0x180005a0c  mov     rbx, rsi
0x180005a0f  lea     r8, [rsp+110h+TokenHandle]; TokenHandle
0x180005a14  mov     edx, 8; DesiredAccess
0x180005a19  mov     rcx, rbx; ProcessHandle
0x180005a1c  call    cs:__imp_NtOpenProcessToken
0x180005a23  nop     dword ptr [rax+rax+00h]
0x180005a28  test    eax, eax
0x180005a2a  js      loc_180005FE5
0x180005a30  mov     rcx, [rsp+110h+TokenHandle]; TokenHandle
0x180005a35  lea     rax, [rsp+110h+var_E0]
0x180005a3a  mov     r9d, 38h ; '8'; TokenInformationLength
0x180005a40  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180005a45  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x180005a49  mov     edx, 0Ah; TokenInformationClass
0x180005a4e  call    cs:__imp_NtQueryInformationToken
0x180005a55  nop     dword ptr [rax+rax+00h]
0x180005a5a  mov     rcx, [rsp+110h+TokenHandle]; Handle
0x180005a5f  mov     ebx, eax
0x180005a61  call    cs:__imp_NtClose
0x180005a68  nop     dword ptr [rax+rax+00h]
0x180005a6d  test    ebx, ebx
0x180005a6f  js      loc_180005FE5
0x180005a75  mov     rax, qword ptr [rbp+3Fh+TokenInformation+8]
0x180005a79  mov     [rdi+80h], rax
0x180005a80  mov     rax, gs:70h
0x180005a89  lea     rbx, [rdi+0BFh]
0x180005a90  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180005a94  mov     r14, [rax+38h]
0x180005a98  lfence
0x180005a9b  mov     rsi, cs:CsrLoadedServerDll
0x180005aa2  test    rsi, rsi
0x180005aa5  jnz     loc_180005E40
0x180005aab  mov     [rdi+88h], r12
0x180005ab2  mov     rsi, cs:qword_180010368
0x180005ab9  test    rsi, rsi
0x180005abc  jnz     loc_180005E77
0x180005ac2  mov     [rdi+90h], r12
0x180005ac9  mov     rsi, cs:qword_180010370
0x180005ad0  test    rsi, rsi
0x180005ad3  jnz     loc_180005EAE
0x180005ad9  mov     [rdi+98h], r12
0x180005ae0  mov     rsi, cs:qword_180010378
0x180005ae7  test    rsi, rsi
0x180005aea  jnz     loc_180005EE5
0x180005af0  mov     [rdi+0A0h], r12
0x180005af7  mov     rsi, cs:qword_180010380
0x180005afe  test    rsi, rsi
0x180005b01  jnz     loc_180005F1C
0x180005b07  mov     [rdi+0A8h], r12
0x180005b0e  mov     rax, cs:qword_180010388
0x180005b15  test    rax, rax
0x180005b18  jnz     loc_180005F53
0x180005b1e  mov     [rdi+0B0h], r12
0x180005b25  mov     esi, dword ptr [rbp+3Fh+arg_20]
0x180005b28  xor     ecx, ecx
0x180005b2a  mov     rax, cs:CsrApiPort
0x180005b31  mov     [rsp+110h+var_D0], r12
0x180005b36  mov     [rsp+110h+TokenHandle], rax
0x180005b3b  test    sil, sil
0x180005b3e  js      loc_18000601A
0x180005b44  mov     rcx, [rsp+110h+ProcessHandle]; ProcessHandle
0x180005b49  bt      esi, 8
0x180005b4d  jb      loc_180005F83
0x180005b53  mov     r9d, 8; ProcessInformationLength
0x180005b59  lea     r8, CsrApiPort; ProcessInformation
0x180005b60  mov     edx, r9d; ProcessInformationClass
0x180005b63  call    cs:__imp_NtSetInformationProcess
0x180005b6a  nop     dword ptr [rax+rax+00h]
0x180005b6f  mov     ebx, 1
0x180005b74  test    eax, eax
0x180005b76  js      loc_180006089
0x180005b7c  test    sil, 4
0x180005b80  jnz     loc_1800060DA
0x180005b86  mov     eax, [r14+68h]
0x180005b8a  mov     [rdi+68h], eax
0x180005b8d  mov     eax, [r14+6Ch]
0x180005b91  mov     [rdi+6Ch], eax
0x180005b94  test    sil, 20h
0x180005b98  jz      short loc_180005B9E
0x180005b9a  or      dword ptr [rdi+5Ch], 20h
0x180005b9e  bt      esi, 0Dh
0x180005ba2  jb      loc_180005FF1
0x180005ba8  mov     r14, [rsp+110h+ThreadHandle]
0x180005bad  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x180005bb1  mov     rcx, r14; ThreadHandle
0x180005bb4  mov     [rsp+110h+ReturnLength], 0; ReturnLength
0x180005bbd  mov     r9d, 20h ; ' '; ThreadInformationLength
0x180005bc3  mov     edx, ebx; ThreadInformationClass
0x180005bc5  call    cs:__imp_NtQueryInformationThread
0x180005bcc  nop     dword ptr [rax+rax+00h]
0x180005bd1  mov     rcx, cs:CsrHeap; HeapHandle
0x180005bd8  mov     ebx, eax
0x180005bda  test    eax, eax
0x180005bdc  js      loc_1800061FE
0x180005be2  mov     edx, cs:CsrBaseTag
0x180005be8  mov     r8d, 58h ; 'X'; Size
0x180005bee  add     edx, 100000h; Flags
0x180005bf4  call    cs:__imp_RtlAllocateHeap
0x180005bfb  nop     dword ptr [rax+rax+00h]
0x180005c00  xor     edx, edx; Val
0x180005c02  mov     rbx, rax
0x180005c05  test    rax, rax
0x180005c08  jz      loc_18000608B
0x180005c0e  mov     r8d, 58h ; 'X'; Size
0x180005c14  mov     rcx, rax; void *
0x180005c17  call    memset_0
0x180005c1c  mov     dword ptr [rbx+4Ch], 1
0x180005c23  lock inc dword ptr [rdi+64h]
0x180005c27  mov     [rbx+38h], rdi
0x180005c2b  lea     r8, [rsp+110h+var_E0]; ThreadInformation
0x180005c30  mov     rax, qword ptr [rbp+3Fh+ThreadInformation]
0x180005c34  mov     r9d, 4; ThreadInformationLength
0x180005c3a  mov     [rbx], rax
0x180005c3d  mov     edx, 14h; ThreadInformationClass
0x180005c42  movups  xmm0, xmmword ptr [r13+0]
0x180005c47  xor     eax, eax
0x180005c49  mov     [rbx+40h], r14
0x180005c4d  mov     rcx, r14; ThreadHandle
0x180005c50  mov     [rbx+48h], eax
0x180005c53  movups  xmmword ptr [rbx+28h], xmm0
0x180005c57  mov     [rsp+110h+var_E0], eax
0x180005c5b  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180005c60  call    cs:__imp_NtQueryInformationThread
0x180005c67  nop     dword ptr [rax+rax+00h]
0x180005c6c  mov     r14d, eax
0x180005c6f  test    eax, eax
0x180005c71  js      loc_1800060EF
0x180005c77  cmp     [rsp+110h+var_E0], 1
0x180005c7c  jz      loc_1800060E9
0x180005c82  mov     rcx, [r15+8]
0x180005c86  cmp     [rcx], r15
0x180005c89  jnz     loc_180005F7C
0x180005c8f  mov     [rbx+10h], rcx
0x180005c93  lea     rax, [rbx+8]
0x180005c97  mov     [rax], r15
0x180005c9a  mov     [rcx], rax
0x180005c9d  lea     rcx, CsrThreadHashTable
0x180005ca4  mov     [r15+8], rax
0x180005ca8  mov     eax, [rbx+30h]
0x180005cab  shr     rax, 2
0x180005caf  and     eax, 3FFh
0x180005cb4  shl     rax, 4
0x180005cb8  add     rcx, rax
0x180005cbb  mov     rdx, [rcx]
0x180005cbe  cmp     [rdx+8], rcx
0x180005cc2  jnz     loc_180005F7C
0x180005cc8  lea     rax, [rbx+18h]
0x180005ccc  mov     [rax], rdx
0x180005ccf  mov     [rax+8], rcx
0x180005cd3  mov     [rdx+8], rax
0x180005cd7  mov     [rcx], rax
0x180005cda  mov     rax, [rbp+3Fh+var_B8]
0x180005cde  lock inc dword ptr [rax+14h]
0x180005ce2  mov     [rdi+30h], rax
0x180005ce6  movups  xmm0, xmmword ptr [r13+0]
0x180005ceb  mov     rax, [rsp+110h+ProcessHandle]
0x180005cf0  mov     [rdi+50h], rax
0x180005cf4  movups  xmmword ptr [rdi], xmm0
0x180005cf7  mov     dword ptr [rdi+78h], 280h
0x180005cfe  mov     r8, gs:70h
0x180005d07  mov     rcx, cs:CsrRootProcess
0x180005d0e  add     rcx, 10h
0x180005d12  mov     rdx, [rcx+8]
0x180005d16  cmp     [rdx], rcx
0x180005d19  jnz     loc_180005F7C
0x180005d1f  mov     rbx, [r8+38h]
0x180005d23  lea     rax, [rdi+10h]
0x180005d27  mov     [rax], rcx
0x180005d2a  mov     [rax+8], rdx
0x180005d2e  mov     [rdx], rax
0x180005d31  mov     [rcx+8], rax
0x180005d35  test    byte ptr [rdi+5Ch], 80h
0x180005d39  jnz     loc_180005DD8
0x180005d3f  lfence
0x180005d42  mov     rax, cs:CsrLoadedServerDll
0x180005d49  test    rax, rax
0x180005d4c  jz      short loc_180005D5B
0x180005d4e  mov     rax, [rax+68h]
0x180005d52  test    rax, rax
0x180005d55  jnz     loc_180006172
0x180005d5b  mov     rax, cs:qword_180010368
0x180005d62  test    rax, rax
0x180005d65  jz      short loc_180005D74
0x180005d67  mov     rax, [rax+68h]
0x180005d6b  test    rax, rax
0x180005d6e  jnz     loc_180006182
0x180005d74  mov     rax, cs:qword_180010370
0x180005d7b  test    rax, rax
0x180005d7e  jz      short loc_180005D8D
0x180005d80  mov     rax, [rax+68h]
0x180005d84  test    rax, rax
0x180005d87  jnz     loc_180006192
0x180005d8d  mov     rax, cs:qword_180010378
0x180005d94  test    rax, rax
0x180005d97  jz      short loc_180005DA6
0x180005d99  mov     rax, [rax+68h]
0x180005d9d  test    rax, rax
0x180005da0  jnz     loc_1800061A2
0x180005da6  mov     rax, cs:qword_180010380
0x180005dad  test    rax, rax
0x180005db0  jz      short loc_180005DBF
0x180005db2  mov     rax, [rax+68h]
0x180005db6  test    rax, rax
0x180005db9  jnz     loc_1800061B2
0x180005dbf  mov     rax, cs:qword_180010388
0x180005dc6  test    rax, rax
0x180005dc9  jz      short loc_180005DD8
0x180005dcb  mov     rax, [rax+68h]
0x180005dcf  test    rax, rax
0x180005dd2  jnz     loc_1800061C2
0x180005dd8  mov     rcx, [rbp+3Fh+var_B0]
0x180005ddc  test    rcx, rcx
0x180005ddf  jnz     loc_180006074
0x180005de5  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180005dec  call    cs:__imp_RtlLeaveCriticalSection
0x180005df3  nop     dword ptr [rax+rax+00h]
0x180005df8  mov     rax, [rbp+3Fh+var_A8]
0x180005dfc  test    rax, rax
0x180005dff  jz      short loc_180005E04
0x180005e01  mov     [rax], r12d
0x180005e04  xor     eax, eax
0x180005e06  mov     r14, [rsp+110h+var_30]
  ... truncated ...
```
