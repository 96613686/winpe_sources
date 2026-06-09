# CDDPDEV::OpenResource(uint,void *,uint,_EPROCESS *,uint *,void * *,unsigned __int64 *,void * *)

- ea: `0x14001b6e8`
- end: `0x14001bff1`
- name: `?OpenResource@CDDPDEV@@QEAAIIPEAXIPEAU_EPROCESS@@PEAIPEAPEAXPEA_K3@Z`
- size: `2313`
- prototype: `unsigned int(CDDPDEV *__hidden this, unsigned int, void *, unsigned int, struct _EPROCESS *, unsigned int *, void **, unsigned __int64 *, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011510`
- `0x14001b170`
- `0x1400212b0`
- `0x140031d40`

## callees

- `0x14000fbb4`
- `0x14001b6e8`
- `0x14001bff8`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b762`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b762`
- `ntoskrnl!ObDuplicateObject` at `0x14001bcde`
- `ntoskrnl!ObDuplicateObject` at `0x14001bcde`
- `ntoskrnl!ObCloseHandle` at `0x14001bfc0`
- `ntoskrnl!ObCloseHandle` at `0x14001bfc0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bc49`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bcad`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bc49`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001bcad`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b86e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b86e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001b7d7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001b7d7`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001b85a`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14001b85a`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ba06`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ba75`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001bae9`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001bda0`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ba06`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ba75`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001bae9`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001bda0`
- `watchdog!WdLogSingleEntry1` at `0x14001b778`
- `watchdog!WdLogSingleEntry1` at `0x14001b93c`
- `watchdog!WdLogSingleEntry1` at `0x14001bbbd`
- `watchdog!WdLogSingleEntry1` at `0x14001bcf6`
- `watchdog!WdLogSingleEntry1` at `0x14001bd4a`
- `watchdog!WdLogSingleEntry1` at `0x14001bf2d`
- `watchdog!WdLogSingleEntry1` at `0x14001b778`
- `watchdog!WdLogSingleEntry1` at `0x14001b93c`
- `watchdog!WdLogSingleEntry1` at `0x14001bbbd`
- `watchdog!WdLogSingleEntry1` at `0x14001bcf6`
- `watchdog!WdLogSingleEntry1` at `0x14001bd4a`
- `watchdog!WdLogSingleEntry1` at `0x14001bf2d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001b8d3`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001bc16`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001bc81`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001b8d3`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001bc16`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001bc81`
- `watchdog!WdLogSingleEntry0` at `0x14001b8ba`
- `watchdog!WdLogSingleEntry0` at `0x14001b9ad`
- `watchdog!WdLogSingleEntry0` at `0x14001b9ef`
- `watchdog!WdLogSingleEntry0` at `0x14001ba5e`
- `watchdog!WdLogSingleEntry0` at `0x14001bad2`
- `watchdog!WdLogSingleEntry0` at `0x14001bbfd`
- `watchdog!WdLogSingleEntry0` at `0x14001bc68`
- `watchdog!WdLogSingleEntry0` at `0x14001bd89`
- `watchdog!WdLogSingleEntry0` at `0x14001bdfb`
- `watchdog!WdLogSingleEntry0` at `0x14001be38`
- `watchdog!WdLogSingleEntry0` at `0x14001be78`
- `watchdog!WdLogSingleEntry0` at `0x14001b8ba`
- `watchdog!WdLogSingleEntry0` at `0x14001b9ad`
- `watchdog!WdLogSingleEntry0` at `0x14001b9ef`
- `watchdog!WdLogSingleEntry0` at `0x14001ba5e`
- `watchdog!WdLogSingleEntry0` at `0x14001bad2`
- `watchdog!WdLogSingleEntry0` at `0x14001bbfd`
- `watchdog!WdLogSingleEntry0` at `0x14001bc68`
- `watchdog!WdLogSingleEntry0` at `0x14001bd89`
- `watchdog!WdLogSingleEntry0` at `0x14001bdfb`
- `watchdog!WdLogSingleEntry0` at `0x14001be38`
- `watchdog!WdLogSingleEntry0` at `0x14001be78`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b78f`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b953`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001bbd4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b78f`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b953`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001bbd4`
- `WIN32K!EngAllocMem` at `0x14001b9d6`
- `WIN32K!EngAllocMem` at `0x14001ba45`
- `WIN32K!EngAllocMem` at `0x14001bab6`
- `WIN32K!EngAllocMem` at `0x14001bde2`
- `WIN32K!EngAllocMem` at `0x14001be1f`
- `WIN32K!EngAllocMem` at `0x14001be5c`
- `WIN32K!EngAllocMem` at `0x14001b9d6`
- `WIN32K!EngAllocMem` at `0x14001ba45`
- `WIN32K!EngAllocMem` at `0x14001bab6`
- `WIN32K!EngAllocMem` at `0x14001bde2`
- `WIN32K!EngAllocMem` at `0x14001be1f`
- `WIN32K!EngAllocMem` at `0x14001be5c`
- `WIN32K!EngFreeMem` at `0x14001bf5a`
- `WIN32K!EngFreeMem` at `0x14001bf73`
- `WIN32K!EngFreeMem` at `0x14001bf8c`
- `WIN32K!EngFreeMem` at `0x14001bfa0`
- `WIN32K!EngFreeMem` at `0x14001bf5a`
- `WIN32K!EngFreeMem` at `0x14001bf73`
- `WIN32K!EngFreeMem` at `0x14001bf8c`
- `WIN32K!EngFreeMem` at `0x14001bfa0`

## pseudocode

```c
__int64 __fastcall CDDPDEV::OpenResource(
        CDDPDEV *this,
        int a2,
        void *a3,
        unsigned int a4,
        struct _EPROCESS *a5,
        unsigned int *a6,
        void **a7,
        unsigned __int64 *a8,
        void **a9)
{
  PVOID v13; // r14
  struct _OBJECT_TYPE *v14; // r8
  NTSTATUS v15; // eax
  _QWORD *v16; // rax
  __int64 result; // rax
  __int64 v18; // rbx
  unsigned int v19; // esi
  HANDLE *v20; // r14
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 (__fastcall *v24)(_DWORD *); // rax
  int v25; // eax
  int v26; // r15d
  int v27; // esi
  _QWORD *v28; // rax
  ULONG v29; // eax
  _DWORD *v30; // r13
  int v31; // edi
  int v32; // esi
  _QWORD *v33; // rax
  int v34; // ecx
  int v35; // esi
  _QWORD *v36; // rax
  ULONG v37; // edx
  PVOID v38; // r12
  int v39; // esi
  _QWORD *v40; // rax
  __int64 (__fastcall *v41)(int *, _QWORD, struct _EPROCESS *, unsigned int *, void **, unsigned __int64 *); // rax
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  _QWORD *v45; // rax
  struct _EPROCESS *v46; // r12
  __int64 v47; // rdx
  __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 CurrentProcess; // rax
  int v51; // eax
  __int64 (__fastcall *v52)(int *); // rax
  int v53; // eax
  ULONG v54; // eax
  _QWORD *v55; // rax
  PVOID v56; // r12
  __int64 (__fastcall *v57)(_QWORD *, _QWORD, struct _EPROCESS *, unsigned int *, void **, unsigned __int64 *); // rax
  int v58; // eax
  PVOID pv; // [rsp+48h] [rbp-C0h]
  PVOID v60; // [rsp+50h] [rbp-B8h]
  PVOID v61; // [rsp+58h] [rbp-B0h]
  _DWORD v62[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v63; // [rsp+68h] [rbp-A0h]
  __int64 v64; // [rsp+78h] [rbp-90h]
  int v65; // [rsp+88h] [rbp-80h] BYREF
  int v66; // [rsp+8Ch] [rbp-7Ch]
  HANDLE v67; // [rsp+90h] [rbp-78h]
  ULONG v68[4]; // [rsp+98h] [rbp-70h]
  ULONG v69[2]; // [rsp+A8h] [rbp-60h]
  PVOID v70; // [rsp+B0h] [rbp-58h]
  int v71; // [rsp+B8h] [rbp-50h]
  int v72; // [rsp+BCh] [rbp-4Ch]
  PVOID v73; // [rsp+C0h] [rbp-48h]
  int v74; // [rsp+C8h] [rbp-40h]
  int v75; // [rsp+CCh] [rbp-3Ch]
  _QWORD v76[20]; // [rsp+D8h] [rbp-30h] BYREF
  PVOID Object; // [rsp+188h] [rbp+80h] BYREF
  int v78; // [rsp+190h] [rbp+88h]
  unsigned int v79; // [rsp+1A0h] [rbp+98h]

  v79 = a4;
  v78 = a2;
  if ( KeGetCurrentThread() == *((struct _KTHREAD **)this + 321) )
  {
    v20 = a9;
    LODWORD(Object) = 0;
    v60 = 0;
    pv = 0;
    v61 = 0;
    if ( a2 )
    {
      if ( a3 || a9 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 127;
        v23 = (_QWORD *)WdLogNewEntry5_WdAssertion(v22, v21);
        v23[3] = gCddImageInfo;
        v23[4] = (unsigned int)dword_14003E570;
        v23[5] = 215857758;
        WdLogGlobalForLineNumber = 127;
      }
      v62[0] = *((_DWORD *)this + 630);
      v24 = (__int64 (__fastcall *)(_DWORD *))*((_QWORD *)this + 29);
      v63 = 0;
      v64 = 0;
      v62[1] = a2;
      v25 = v24(v62);
      v26 = v25;
      if ( v25 < 0 )
      {
        WdLogSingleEntry1(4, v25);
        v27 = 136;
LABEL_15:
        WdLogGlobalForLineNumber = v27;
        v28 = (_QWORD *)WdLogNewEntry5_WdEvent();
        v28[3] = gCddImageInfo;
        v28[4] = (unsigned int)dword_14003E570;
        v28[5] = 215857758;
        WdLogGlobalForLineNumber = v27;
LABEL_74:
        if ( v20 && *v20 )
        {
          ObCloseHandle(*v20, 0);
          *v20 = 0;
        }
        return (unsigned int)Object;
      }
      v29 = 80 * HIDWORD(v64);
      if ( !is_mul_ok(HIDWORD(v64), 0x50u) )
        v29 = -1;
      v30 = operator new(v29);
      if ( !v30 )
      {
        WdLogSingleEntry0(6);
        v31 = 143;
LABEL_53:
        WdLogGlobalForLineNumber = v31;
        v55 = (_QWORD *)WdLogNewEntry5_WdLowResource();
        v55[3] = gCddImageInfo;
        v55[4] = (unsigned int)dword_14003E570;
        v55[5] = 215857758;
        WdLogGlobalForLineNumber = v31;
        return (unsigned int)Object;
      }
      if ( HIDWORD(v63) )
      {
        v60 = EngAllocMem(0, HIDWORD(v63), 0x64646344u);
        if ( !v60 )
        {
          WdLogSingleEntry0(6);
          v32 = 152;
LABEL_23:
          WdLogGlobalForLineNumber = v32;
          v33 = (_QWORD *)WdLogNewEntry5_WdLowResource();
          v33[3] = gCddImageInfo;
          v33[4] = (unsigned int)dword_14003E570;
          v33[5] = 215857758;
          WdLogGlobalForLineNumber = v32;
          goto LABEL_73;
        }
      }
      v34 = v64;
      if ( (_DWORD)v64 )
      {
        pv = EngAllocMem(0, v64, 0x64646344u);
        if ( !pv )
        {
          WdLogSingleEntry0(6);
          v35 = 163;
LABEL_27:
          WdLogGlobalForLineNumber = v35;
          v36 = (_QWORD *)WdLogNewEntry5_WdLowResource();
          v36[3] = gCddImageInfo;
          v36[4] = (unsigned int)dword_14003E570;
          v36[5] = 215857758;
          WdLogGlobalForLineNumber = v35;
LABEL_69:
          if ( v60 )
            EngFreeMem(v60);
          if ( v61 )
            EngFreeMem(v61);
LABEL_73:
          EngFreeMem(v30);
          if ( v26 < 0 )
            goto LABEL_74;
          return (unsigned int)Object;
        }
        v34 = v64;
      }
      v37 = DWORD2(v63);
      if ( DWORD2(v63) )
      {
        v61 = EngAllocMem(0, DWORD2(v63), 0x64646344u);
        v38 = v61;
        if ( !v61 )
        {
          WdLogSingleEntry0(6);
          v39 = 174;
LABEL_32:
          WdLogGlobalForLineNumber = v39;
          v40 = (_QWORD *)WdLogNewEntry5_WdLowResource();
LABEL_33:
          v40[3] = gCddImageInfo;
          v40[4] = (unsigned int)dword_14003E570;
          v40[5] = 215857758;
          WdLogGlobalForLineNumber = v39;
          goto LABEL_67;
        }
        v34 = v64;
        v37 = DWORD2(v63);
      }
      else
      {
        v38 = 0;
      }
      v65 = *((_DWORD *)this + 630);
      v66 = v78;
      v67 = (HANDLE)HIDWORD(v64);
      v71 = v34;
      v73 = v60;
      v74 = HIDWORD(v63);
      v70 = pv;
      v41 = (__int64 (__fastcall *)(int *, _QWORD, struct _EPROCESS *, unsigned int *, void **, unsigned __int64 *))*((_QWORD *)this + 31);
      v69[0] = v37;
      v69[1] = 0;
      v72 = 0;
      v75 = 0;
      *(_QWORD *)v68 = v30;
      *(_QWORD *)&v68[2] = v38;
      v42 = v41(&v65, v79, a5, a6, a7, a8);
      v26 = v42;
      if ( v42 < 0 )
      {
        WdLogSingleEntry1(4, v42);
        v39 = 194;
LABEL_38:
        WdLogGlobalForLineNumber = v39;
        v40 = (_QWORD *)WdLogNewEntry5_WdEvent();
        goto LABEL_33;
      }
      LODWORD(Object) = *v30;
    }
    else
    {
      if ( !a9 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 205;
        v45 = (_QWORD *)WdLogNewEntry5_WdAssertion(v44, v43);
        v45[3] = gCddImageInfo;
        v45[4] = (unsigned int)dword_14003E570;
        v45[5] = 215857758;
        WdLogGlobalForLineNumber = 205;
      }
      v46 = (struct _EPROCESS *)*((_QWORD *)this + 94);
      if ( (struct _EPROCESS *)PsGetCurrentProcess() != v46 || a5 == v46 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 206;
        v49 = (_QWORD *)WdLogNewEntry5_WdAssertion(v48, v47);
        v49[3] = gCddImageInfo;
        v49[4] = (unsigned int)dword_14003E570;
        v49[5] = 215857758;
        WdLogGlobalForLineNumber = 206;
      }
      CurrentProcess = PsGetCurrentProcess();
      v51 = ObDuplicateObject(a5, a3, CurrentProcess, v20, 983041, 0, 0, 0);
      if ( v51 < 0 )
      {
        WdLogSingleEntry1(4, v51);
        v27 = 221;
        goto LABEL_15;
      }
      v65 = *((_DWORD *)this + 630);
      v67 = *v20;
      v52 = (__int64 (__fastcall *)(int *))*((_QWORD *)this + 30);
      v66 = 0;
      *(_OWORD *)v68 = 0;
      *(_QWORD *)v69 = 0;
      v53 = v52(&v65);
      v26 = v53;
      if ( v53 < 0 )
      {
        WdLogSingleEntry1(4, v53);
        v27 = 232;
        goto LABEL_15;
      }
      v54 = 80 * v69[1];
      if ( !is_mul_ok(v69[1], 0x50u) )
        v54 = -1;
      v30 = operator new(v54);
      if ( !v30 )
      {
        WdLogSingleEntry0(6);
        v31 = 239;
        goto LABEL_53;
      }
      if ( v68[3] )
      {
        v60 = EngAllocMem(0, v68[3], 0x64646344u);
        if ( !v60 )
        {
          WdLogSingleEntry0(6);
          v32 = 248;
          goto LABEL_23;
        }
      }
      if ( v69[0] )
      {
        pv = EngAllocMem(0, v69[0], 0x64646344u);
        if ( !pv )
        {
          WdLogSingleEntry0(6);
          v35 = 259;
          goto LABEL_27;
        }
      }
      if ( v68[2] )
      {
        v61 = EngAllocMem(0, v68[2], 0x64646344u);
        v56 = v61;
        if ( !v61 )
        {
          WdLogSingleEntry0(6);
          v39 = 270;
          goto LABEL_32;
        }
      }
      else
      {
        v56 = 0;
      }
      memset(v76, 0, 0x68u);
      LODWORD(v76[0]) = *((_DWORD *)this + 630);
      v76[1] = *v20;
      LODWORD(v76[2]) = v69[1];
      v76[9] = v60;
      LODWORD(v76[8]) = v68[3];
      v76[7] = pv;
      LODWORD(v76[6]) = v69[0];
      LODWORD(v76[4]) = v68[2];
      v57 = (__int64 (__fastcall *)(_QWORD *, _QWORD, struct _EPROCESS *, unsigned int *, void **, unsigned __int64 *))*((_QWORD *)this + 32);
      v76[3] = v30;
      v76[5] = v56;
      v58 = v57(v76, v79, a5, a6, a7, a8);
      v26 = v58;
      if ( v58 < 0 )
      {
        WdLogSingleEntry1(4, v58);
        v39 = 290;
        goto LABEL_38;
      }
      LODWORD(Object) = *v30;
    }
LABEL_67:
    if ( pv )
      EngFreeMem(pv);
    goto LABEL_69;
  }
  v13 = 0;
  if ( !a2 )
  {
    v14 = (struct _OBJECT_TYPE *)*((_QWORD *)this + 4);
    Object = 0;
    v15 = ObReferenceObjectByHandle(a3, 0x20000u, v14, 1, &Object, 0);
    if ( v15 < 0 )
    {
      WdLogSingleEntry1(4, v15);
      WdLogGlobalForLineNumber = a2 + 88;
      v16 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v16[3] = gCddImageInfo;
      v16[4] = (unsigned int)dword_14003E570;
      v16[5] = 215857758;
      result = 0;
      WdLogGlobalForLineNumber = a2 + 88;
      return result;
    }
    v13 = Object;
  }
  v18 = *((_QWORD *)this + 686);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v18);
  *((_QWORD *)this + 460) = a6;
  *((_QWORD *)this + 461) = a7;
  *((_QWORD *)this + 462) = a8;
  *((_QWORD *)this + 459) = a5;
  *((_QWORD *)this + 464) = a9;
  *((_DWORD *)this + 912) = a2;
  *((_QWORD *)this + 457) = a3;
  *((_DWORD *)this + 926) = 0;
  *((_DWORD *)this + 916) = a4;
  CddIssueCommand((__int64)this, 17);
  v19 = *((_DWORD *)this + 926);
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v18);
  if ( v13 )
    ObfDereferenceObject(v13);
  return v19;
}

```

## disassembly

```asm
0x14001b6e8  mov     rax, rsp
0x14001b6eb  mov     [rax+18h], rbx
0x14001b6ef  mov     [rax+20h], r9d
0x14001b6f3  mov     [rax+10h], edx
0x14001b6f6  push    rbp
0x14001b6f7  push    rsi
0x14001b6f8  push    rdi
0x14001b6f9  push    r12
0x14001b6fb  push    r13
0x14001b6fd  push    r14
0x14001b6ff  push    r15
0x14001b701  lea     rbp, [rax-78h]
0x14001b705  sub     rsp, 140h
0x14001b70c  mov     rax, gs:188h
0x14001b715  xor     edi, edi
0x14001b717  mov     r13d, r9d
0x14001b71a  mov     r15, r8
0x14001b71d  mov     r12d, edx
0x14001b720  mov     rsi, rcx
0x14001b723  cmp     rax, [rcx+0A08h]
0x14001b72a  jz      loc_14001B881
0x14001b730  mov     r14d, edi
0x14001b733  test    edx, edx
0x14001b735  jnz     loc_14001B7CD
0x14001b73b  mov     r8, [rcx+20h]; ObjectType
0x14001b73f  lea     rax, [rbp+70h+arg_0]
0x14001b746  mov     rcx, r15; Handle
0x14001b749  mov     [rsp+170h+HandleInformation], rdi; HandleInformation
0x14001b74e  mov     r9b, 1; AccessMode
0x14001b751  mov     [rsp+170h+Object], rax; Object
0x14001b756  mov     edx, 20000h; DesiredAccess
0x14001b75b  mov     [rbp+70h+arg_0], rdi
0x14001b762  call    cs:__imp_ObReferenceObjectByHandle
0x14001b769  nop     dword ptr [rax+rax+00h]
0x14001b76e  test    eax, eax
0x14001b770  jns     short loc_14001B7C6
0x14001b772  movsxd  rdx, eax
0x14001b775  lea     ecx, [rdi+4]
0x14001b778  call    cs:__imp_WdLogSingleEntry1
0x14001b77f  nop     dword ptr [rax+rax+00h]
0x14001b784  lea     edi, [r12+58h]
0x14001b789  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b78f  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001b796  nop     dword ptr [rax+rax+00h]
0x14001b79b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b7a2  mov     ebx, 0CDDBA5Eh
0x14001b7a7  mov     [rax+18h], rcx
0x14001b7ab  mov     ecx, cs:dword_14003E570
0x14001b7b1  mov     [rax+20h], rcx
0x14001b7b5  mov     [rax+28h], rbx
0x14001b7b9  xor     eax, eax
0x14001b7bb  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b7c1  jmp     loc_14001BFD5
0x14001b7c6  mov     r14, [rbp+70h+arg_0]
0x14001b7cd  mov     rbx, [rsi+1570h]
0x14001b7d4  mov     rcx, rbx
0x14001b7d7  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001b7de  nop     dword ptr [rax+rax+00h]
0x14001b7e3  mov     rax, [rbp+70h+arg_28]
0x14001b7ea  mov     edx, 11h
0x14001b7ef  mov     [rsi+0E60h], rax
0x14001b7f6  mov     rcx, rsi
0x14001b7f9  mov     rax, [rbp+70h+arg_30]
0x14001b800  mov     [rsi+0E68h], rax
0x14001b807  mov     rax, [rbp+70h+arg_38]
0x14001b80e  mov     [rsi+0E70h], rax
0x14001b815  mov     rax, [rbp+70h+arg_20]
0x14001b81c  mov     [rsi+0E58h], rax
0x14001b823  mov     rax, [rbp+70h+arg_40]
0x14001b82a  mov     [rsi+0E80h], rax
0x14001b831  mov     [rsi+0E40h], r12d
0x14001b838  mov     [rsi+0E48h], r15
0x14001b83f  mov     [rsi+0E78h], edi
0x14001b845  mov     [rsi+0E50h], r13d
0x14001b84c  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14001b851  mov     esi, [rsi+0E78h]
0x14001b857  mov     rcx, rbx
0x14001b85a  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14001b861  nop     dword ptr [rax+rax+00h]
0x14001b866  test    r14, r14
0x14001b869  jz      short loc_14001B87A
0x14001b86b  mov     rcx, r14; Object
0x14001b86e  call    cs:__imp_ObfDereferenceObject
0x14001b875  nop     dword ptr [rax+rax+00h]
0x14001b87a  mov     eax, esi
0x14001b87c  jmp     loc_14001BFD5
0x14001b881  mov     r14, [rbp+70h+arg_40]
0x14001b888  mov     ebx, 0CDDBA5Eh
0x14001b88d  mov     dword ptr [rbp+70h+arg_0], edi
0x14001b893  mov     [rsp+170h+var_128], rdi
0x14001b898  mov     [rsp+170h+pv], rdi
0x14001b89d  mov     [rsp+170h+var_120], rdi
0x14001b8a2  test    r12d, r12d
0x14001b8a5  jz      loc_14001BBF4
0x14001b8ab  test    r15, r15
0x14001b8ae  jnz     short loc_14001B8B5
0x14001b8b0  test    r14, r14
0x14001b8b3  jz      short loc_14001B8FF
0x14001b8b5  mov     ecx, 1
0x14001b8ba  call    cs:__imp_WdLogSingleEntry0
0x14001b8c1  nop     dword ptr [rax+rax+00h]
0x14001b8c6  mov     r15d, 7Fh
0x14001b8cc  mov     cs:WdLogGlobalForLineNumber, r15d
0x14001b8d3  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001b8da  nop     dword ptr [rax+rax+00h]
0x14001b8df  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b8e6  mov     [rax+18h], rcx
0x14001b8ea  mov     ecx, cs:dword_14003E570
0x14001b8f0  mov     [rax+20h], rcx
0x14001b8f4  mov     [rax+28h], rbx
0x14001b8f8  mov     cs:WdLogGlobalForLineNumber, r15d
0x14001b8ff  mov     eax, [rsi+9D8h]
0x14001b905  lea     rcx, [rsp+170h+var_118]
0x14001b90a  mov     dword ptr [rsp+170h+var_118], eax
0x14001b90e  xorps   xmm0, xmm0
0x14001b911  mov     rax, [rsi+0E8h]
0x14001b918  movdqu  [rsp+170h+var_118+8], xmm0
0x14001b91e  mov     [rsp+170h+var_100], rdi
0x14001b923  mov     dword ptr [rsp+170h+var_118+4], r12d
0x14001b928  call    _guard_dispatch_icall
0x14001b92d  movsxd  r15, eax
0x14001b930  test    eax, eax
0x14001b932  jns     short loc_14001B983
0x14001b934  mov     rdx, r15
0x14001b937  mov     ecx, 4
0x14001b93c  call    cs:__imp_WdLogSingleEntry1
0x14001b943  nop     dword ptr [rax+rax+00h]
0x14001b948  mov     esi, 88h
0x14001b94d  mov     cs:WdLogGlobalForLineNumber, esi
0x14001b953  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001b95a  nop     dword ptr [rax+rax+00h]
0x14001b95f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b966  mov     [rax+18h], rcx
0x14001b96a  mov     ecx, cs:dword_14003E570
0x14001b970  mov     [rax+20h], rcx
0x14001b974  mov     [rax+28h], rbx
0x14001b978  mov     cs:WdLogGlobalForLineNumber, esi
0x14001b97e  jmp     loc_14001BFB1
0x14001b983  mov     ecx, dword ptr [rsp+170h+var_100+4]
0x14001b987  mov     eax, 50h ; 'P'
0x14001b98c  mul     rcx
0x14001b98f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14001b996  cmovb   rax, rcx
0x14001b99a  mov     rcx, rax; cjMemSize
0x14001b99d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b9a2  mov     r13, rax
0x14001b9a5  test    rax, rax
0x14001b9a8  jnz     short loc_14001B9C3
0x14001b9aa  lea     ecx, [rax+6]
0x14001b9ad  call    cs:__imp_WdLogSingleEntry0
0x14001b9b4  nop     dword ptr [rax+rax+00h]
0x14001b9b9  mov     edi, 8Fh
0x14001b9be  jmp     loc_14001BD9A
0x14001b9c3  mov     edx, [rsp+170h+cjMemSize+4]; cjMemSize
0x14001b9c7  mov     r12d, 64646344h
0x14001b9cd  test    edx, edx
0x14001b9cf  jz      short loc_14001BA36
0x14001b9d1  mov     r8d, r12d; ulTag
0x14001b9d4  xor     ecx, ecx; fl
0x14001b9d6  call    cs:__imp_EngAllocMem
0x14001b9dd  nop     dword ptr [rax+rax+00h]
0x14001b9e2  mov     [rsp+170h+var_128], rax
0x14001b9e7  test    rax, rax
0x14001b9ea  jnz     short loc_14001BA36
0x14001b9ec  lea     ecx, [rax+6]
0x14001b9ef  call    cs:__imp_WdLogSingleEntry0
0x14001b9f6  nop     dword ptr [rax+rax+00h]
0x14001b9fb  mov     esi, 98h
0x14001ba00  mov     cs:WdLogGlobalForLineNumber, esi
0x14001ba06  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001ba0d  nop     dword ptr [rax+rax+00h]
0x14001ba12  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001ba19  mov     [rax+18h], rcx
0x14001ba1d  mov     ecx, cs:dword_14003E570
0x14001ba23  mov     [rax+20h], rcx
0x14001ba27  mov     [rax+28h], rbx
0x14001ba2b  mov     cs:WdLogGlobalForLineNumber, esi
0x14001ba31  jmp     loc_14001BF9D
0x14001ba36  mov     ecx, dword ptr [rsp+170h+var_100]
0x14001ba3a  test    ecx, ecx
0x14001ba3c  jz      short loc_14001BAA9
0x14001ba3e  mov     edx, ecx; cjMemSize
0x14001ba40  mov     r8d, r12d; ulTag
0x14001ba43  xor     ecx, ecx; fl
0x14001ba45  call    cs:__imp_EngAllocMem
0x14001ba4c  nop     dword ptr [rax+rax+00h]
0x14001ba51  mov     [rsp+170h+pv], rax
0x14001ba56  test    rax, rax
0x14001ba59  jnz     short loc_14001BAA5
0x14001ba5b  lea     ecx, [rax+6]
0x14001ba5e  call    cs:__imp_WdLogSingleEntry0
0x14001ba65  nop     dword ptr [rax+rax+00h]
0x14001ba6a  mov     esi, 0A3h
0x14001ba6f  mov     cs:WdLogGlobalForLineNumber, esi
0x14001ba75  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001ba7c  nop     dword ptr [rax+rax+00h]
0x14001ba81  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001ba88  mov     [rax+18h], rcx
0x14001ba8c  mov     ecx, cs:dword_14003E570
0x14001ba92  mov     [rax+20h], rcx
0x14001ba96  mov     [rax+28h], rbx
0x14001ba9a  mov     cs:WdLogGlobalForLineNumber, esi
0x14001baa0  jmp     loc_14001BF66
0x14001baa5  mov     ecx, dword ptr [rsp+170h+var_100]
0x14001baa9  mov     edx, [rsp+170h+cjMemSize]; cjMemSize
0x14001baad  test    edx, edx
0x14001baaf  jz      short loc_14001BB23
0x14001bab1  mov     r8d, r12d; ulTag
0x14001bab4  xor     ecx, ecx; fl
0x14001bab6  call    cs:__imp_EngAllocMem
0x14001babd  nop     dword ptr [rax+rax+00h]
0x14001bac2  mov     [rsp+170h+var_120], rax
0x14001bac7  mov     r12, rax
0x14001baca  test    rax, rax
0x14001bacd  jnz     short loc_14001BB19
0x14001bacf  lea     ecx, [rax+6]
0x14001bad2  call    cs:__imp_WdLogSingleEntry0
0x14001bad9  nop     dword ptr [rax+rax+00h]
0x14001bade  mov     esi, 0AEh
0x14001bae3  mov     cs:WdLogGlobalForLineNumber, esi
0x14001bae9  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001baf0  nop     dword ptr [rax+rax+00h]
0x14001baf5  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001bafc  mov     [rax+18h], rcx
0x14001bb00  mov     ecx, cs:dword_14003E570
0x14001bb06  mov     [rax+20h], rcx
0x14001bb0a  mov     [rax+28h], rbx
0x14001bb0e  mov     cs:WdLogGlobalForLineNumber, esi
0x14001bb14  jmp     loc_14001BF4D
0x14001bb19  mov     ecx, dword ptr [rsp+170h+var_100]
0x14001bb1d  mov     edx, [rsp+170h+cjMemSize]
0x14001bb21  jmp     short loc_14001BB26
0x14001bb23  mov     r12, rdi
0x14001bb26  mov     eax, [rsi+9D8h]
0x14001bb2c  mov     r9, [rbp+70h+arg_28]
0x14001bb33  mov     r8, [rbp+70h+arg_20]
0x14001bb3a  mov     [rbp+70h+var_F0], eax
0x14001bb3d  mov     eax, [rbp+70h+arg_8]
0x14001bb43  mov     [rbp+70h+var_EC], eax
0x14001bb46  mov     eax, dword ptr [rsp+170h+var_100+4]
0x14001bb4a  mov     dword ptr [rbp+70h+var_E8], eax
0x14001bb4d  mov     rax, [rsp+170h+var_128]
0x14001bb52  mov     [rbp+70h+var_C0], ecx
0x14001bb55  mov     rcx, [rbp+70h+arg_38]
0x14001bb5c  mov     [rbp+70h+var_B8], rax
0x14001bb60  mov     eax, [rsp+170h+cjMemSize+4]
0x14001bb64  mov     [rsp+170h+HandleInformation], rcx
0x14001bb69  mov     rcx, [rbp+70h+arg_30]
0x14001bb70  mov     [rbp+70h+var_B0], eax
0x14001bb73  mov     rax, [rsp+170h+pv]
0x14001bb78  mov     [rbp+70h+var_C8], rax
0x14001bb7c  mov     rax, [rsi+0F8h]
0x14001bb83  mov     [rbp+70h+var_D0], edx
0x14001bb86  mov     edx, [rbp+70h+arg_18]
0x14001bb8c  mov     [rsp+170h+Object], rcx
0x14001bb91  lea     rcx, [rbp+70h+var_F0]
0x14001bb95  mov     dword ptr [rbp+70h+var_E8+4], edi
0x14001bb98  mov     [rbp+70h+var_D0+4], edi
0x14001bb9b  mov     [rbp+70h+var_BC], edi
0x14001bb9e  mov     [rbp+70h+var_AC], edi
0x14001bba1  mov     qword ptr [rbp+70h+var_E0], r13
0x14001bba5  mov     qword ptr [rbp+70h+var_E0+8], r12
0x14001bba9  call    _guard_dispatch_icall
0x14001bbae  movsxd  r15, eax
0x14001bbb1  test    eax, eax
0x14001bbb3  jns     short loc_14001BBE5
0x14001bbb5  mov     rdx, r15
0x14001bbb8  mov     ecx, 4
0x14001bbbd  call    cs:__imp_WdLogSingleEntry1
0x14001bbc4  nop     dword ptr [rax+rax+00h]
0x14001bbc9  mov     esi, 0C2h
0x14001bbce  mov     cs:WdLogGlobalForLineNumber, esi
0x14001bbd4  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001bbdb  nop     dword ptr [rax+rax+00h]
0x14001bbe0  jmp     loc_14001BAF5
0x14001bbe5  mov     ecx, [r13+0]
0x14001bbe9  mov     dword ptr [rbp+70h+arg_0], ecx
0x14001bbef  jmp     loc_14001BF4D
0x14001bbf4  test    r14, r14
0x14001bbf7  jnz     short loc_14001BC42
0x14001bbf9  lea     ecx, [r14+1]
0x14001bbfd  call    cs:__imp_WdLogSingleEntry0
0x14001bc04  nop     dword ptr [rax+rax+00h]
0x14001bc09  mov     r12d, 0CDh
0x14001bc0f  mov     cs:WdLogGlobalForLineNumber, r12d
0x14001bc16  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001bc1d  nop     dword ptr [rax+rax+00h]
0x14001bc22  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001bc29  mov     [rax+18h], rcx
0x14001bc2d  mov     ecx, cs:dword_14003E570
0x14001bc33  mov     [rax+20h], rcx
0x14001bc37  mov     [rax+28h], rbx
0x14001bc3b  mov     cs:WdLogGlobalForLineNumber, r12d
0x14001bc42  mov     r12, [rsi+2F0h]
0x14001bc49  call    cs:__imp_PsGetCurrentProcess
0x14001bc50  nop     dword ptr [rax+rax+00h]
0x14001bc55  cmp     rax, r12
0x14001bc58  jnz     short loc_14001BC63
0x14001bc5a  cmp     [rbp+70h+arg_20], r12
0x14001bc61  jnz     short loc_14001BCAD
  ... truncated ...
```
