# CddBitmapHw::FlushCommandBufferAndIssueSyncObject(int,uint,tagRECT const *)

- ea: `0x14000e880`
- end: `0x14000ef6c`
- name: `?FlushCommandBufferAndIssueSyncObject@CddBitmapHw@@IEAAJHIPEBUtagRECT@@@Z`
- size: `1772`
- prototype: `__int64 __fastcall(CddBitmapHw *__hidden this, int, unsigned int, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000e580`
- `0x14001c630`
- `0x14001ff70`

## callees

- `0x14000e880`
- `0x14000fbb4`
- `0x1400106ec`
- `0x140010798`
- `0x140010850`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000e9cf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e9cf`
- `ntoskrnl!KeClearEvent` at `0x14000e9e2`
- `ntoskrnl!KeClearEvent` at `0x14000e9e2`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000ea2f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000ea2f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000e928`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ea72`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ea85`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb1a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb2d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb7a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ec4b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ed28`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000e928`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ea72`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ea85`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb1a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb2d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000eb7a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ec4b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000ed28`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e8d9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e8f1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e9fe`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eacb`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eade`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eb9d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000ece5`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000edc8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e8d9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e8f1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e9fe`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eacb`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eade`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000eb9d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000ece5`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000edc8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e94b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000eb5c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e94b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000eb5c`
- `ntoskrnl!KeSetEvent` at `0x14000e9af`
- `ntoskrnl!KeSetEvent` at `0x14000e9af`
- `ntoskrnl!DbgPrint` at `0x14000ef0c`
- `ntoskrnl!DbgPrint` at `0x14000ef0c`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000eef5`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000ef33`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000ef33`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000ee6a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000eebd`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000ee6a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000eebd`
- `watchdog!WdLogSingleEntry0` at `0x14000ee54`
- `watchdog!WdLogSingleEntry0` at `0x14000eea7`
- `watchdog!WdLogSingleEntry0` at `0x14000ef1d`
- `watchdog!WdLogSingleEntry0` at `0x14000ee54`
- `watchdog!WdLogSingleEntry0` at `0x14000eea7`
- `watchdog!WdLogSingleEntry0` at `0x14000ef1d`

## string_xrefs

- `0x14000ef05`: `CddIssueCommand: worker thread submission mutex is not held\n`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::FlushCommandBufferAndIssueSyncObject(
        CddBitmapHw *this,
        int a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  CDDPDEV **v4; // rdi
  int v7; // r15d
  char *v9; // rsi
  __int64 v10; // r14
  CDDPDEV *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _KTHREAD *CurrentThread; // rcx
  bool v15; // zf
  unsigned int v16; // ebx
  int (__fastcall *v18)(__int64, char *, __int64); // rdi
  __int64 CurrentProcess; // rax
  CDDPDEV *v20; // r14
  __int64 v21; // rcx
  int v22; // r13d
  CDDPDEV *v23; // rbx
  char v24; // r13
  char v25; // r12
  __int64 v26; // r14
  __int64 v27; // rbx
  __int64 v28; // rdx
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // rdi
  _QWORD *v32; // r14
  __int64 v33; // r15
  _QWORD *v34; // r9
  __int64 v35; // rcx
  unsigned int v36; // r9d
  char *v37; // rcx
  unsigned int v38; // r14d
  char *v39; // r10
  int v40; // r8d
  int v41; // ecx
  int v42; // ecx
  int v43; // edx
  int v44; // edx
  unsigned int v45; // r9d
  char *v46; // rcx
  unsigned int v47; // eax
  char *v48; // r10
  int v49; // ecx
  int v50; // edx
  int v51; // ecx
  int v52; // edx
  int v53; // ecx
  _QWORD *v54; // rax
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  unsigned int v57; // [rsp+30h] [rbp-78h]
  int *v58; // [rsp+38h] [rbp-70h]
  int v59; // [rsp+38h] [rbp-70h]
  unsigned int v60; // [rsp+38h] [rbp-70h]
  int v61; // [rsp+38h] [rbp-70h]
  _QWORD *v62; // [rsp+40h] [rbp-68h]
  char *v63; // [rsp+48h] [rbp-60h]
  char *v64; // [rsp+48h] [rbp-60h]
  __int64 v65; // [rsp+50h] [rbp-58h]
  int *v66; // [rsp+50h] [rbp-58h]
  CDDPDEV *v67; // [rsp+58h] [rbp-50h] BYREF
  __int16 v68; // [rsp+60h] [rbp-48h]
  char v69; // [rsp+62h] [rbp-46h]
  int v70; // [rsp+B0h] [rbp+8h]

  v4 = (CDDPDEV **)((char *)this + 8);
  v7 = a2;
  if ( (*((_DWORD *)this + 32) & 0x20) == 0 )
  {
    v20 = *v4;
    v67 = v20;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)v20 + 361));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)v20 + 362));
    v21 = *(unsigned int *)(*((_QWORD *)*v4 + 1588) + 8LL);
    if ( a3 )
    {
      v57 = 0;
      v29 = 0;
      v70 = 0;
      v22 = 0;
      v30 = 0;
      v31 = *(unsigned int *)(*((_QWORD *)*v4 + 1587) + 8LL);
      v32 = (_QWORD *)((char *)this + 1176);
      v33 = v21;
      do
      {
        v34 = v32;
        v35 = 16LL * v30;
        v62 = v32;
        v65 = v35;
        if ( *((_BYTE *)this + v31 + 44) )
        {
          v58 = (LONG *)((char *)&a4->left + v35);
          ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*v32);
          v36 = 0;
          v37 = (char *)this + 288 * v31 + 600;
          v63 = v37;
          v38 = *((_DWORD *)v37 + 64);
          while ( 1 )
          {
            if ( v36 >= v38 )
            {
              v59 = 0;
              goto LABEL_43;
            }
            v39 = &v37[16 * v36];
            v40 = *v58;
            v41 = v58[2];
            if ( *v58 <= *(_DWORD *)v39 )
              v40 = *(_DWORD *)v39;
            if ( v41 >= *((_DWORD *)v39 + 2) )
              v41 = *((_DWORD *)v39 + 2);
            if ( v40 < v41 )
            {
              v42 = v58[3];
              v43 = v58[1];
              if ( v42 >= *((_DWORD *)v39 + 3) )
                v42 = *((_DWORD *)v39 + 3);
              if ( v43 <= *((_DWORD *)v39 + 1) )
                v43 = *((_DWORD *)v39 + 1);
              if ( v43 < v42 )
                break;
            }
            v37 = v63;
            ++v36;
          }
          v59 = 1;
LABEL_43:
          ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*v62);
          v29 = v70;
          v35 = v65;
          v30 = v57;
          v44 = v59;
          v34 = v62;
        }
        else
        {
          v44 = 0;
        }
        v22 |= v44;
        if ( *((_BYTE *)this + v33 + 44) )
        {
          v32 = v34;
          v66 = (LONG *)((char *)&a4->left + v35);
          ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*v34);
          v45 = 0;
          v46 = (char *)this + 288 * v33 + 600;
          v64 = v46;
          v47 = *((_DWORD *)v46 + 64);
          v60 = v47;
          while ( 1 )
          {
            if ( v45 >= v47 )
            {
              v61 = 0;
              goto LABEL_59;
            }
            v48 = &v46[16 * v45];
            v49 = v66[2];
            v50 = *v66;
            if ( v49 >= *((_DWORD *)v48 + 2) )
              v49 = *((_DWORD *)v48 + 2);
            if ( v50 <= *(_DWORD *)v48 )
              v50 = *(_DWORD *)v48;
            if ( v50 < v49 )
            {
              v51 = v66[3];
              v52 = v66[1];
              if ( v51 >= *((_DWORD *)v48 + 3) )
                v51 = *((_DWORD *)v48 + 3);
              if ( v52 <= *((_DWORD *)v48 + 1) )
                v52 = *((_DWORD *)v48 + 1);
              if ( v52 < v51 )
                break;
            }
            v47 = v60;
            ++v45;
            v46 = v64;
          }
          v61 = 1;
LABEL_59:
          ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*v62);
          v29 = v70;
          v30 = v57;
          v53 = v61;
        }
        else
        {
          v53 = 0;
          v32 = (_QWORD *)((char *)this + 1176);
        }
        v29 |= v53;
        ++v30;
        v70 = v29;
        v57 = v30;
      }
      while ( v30 < a3 );
      v7 = a2;
      v4 = (CDDPDEV **)((char *)this + 8);
      v20 = v67;
    }
    else
    {
      v22 = *((unsigned __int8 *)this + *(unsigned int *)(*((_QWORD *)*v4 + 1587) + 8LL) + 44);
      v70 = *((unsigned __int8 *)this + v21 + 44);
    }
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)v20 + 362));
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)v20 + 361));
    if ( v22 || v70 )
      goto LABEL_20;
  }
  if ( (*((_DWORD *)this + 32) & 0x20) != 0 )
  {
LABEL_20:
    v23 = (CDDPDEV *)*((_QWORD *)this + 1);
    v4 = (CDDPDEV **)((char *)this + 8);
    v24 = 1;
    v67 = v23;
    v68 = 257;
    v25 = 1;
    v69 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)v23 + 361));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)v23 + 362));
    v26 = *((_QWORD *)this + 1);
    if ( KeGetCurrentThread() == *(struct _KTHREAD **)(v26 + 2568) )
    {
      CDDPDEV::FlushGdiOutput(*v4, 0);
    }
    else
    {
      CCommandBufferMutex::EnableWorkerThreadAccess((CCommandBufferMutex *)&v67);
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 785;
        v54 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v54[3] = gCddImageInfo;
        v54[4] = (unsigned int)dword_14003E570;
        v54[5] = 215857758;
        WdLogGlobalForLineNumber = 785;
      }
      v27 = *(_QWORD *)(v26 + 5488);
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v27);
      *(_DWORD *)(v26 + 3648) = 0;
      CddIssueCommand(v26, 13);
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v27);
      CCommandBufferMutex::DisableWorkerThreadAccess((CCommandBufferMutex *)&v67);
      v25 = HIBYTE(v68);
      v24 = v68;
      v23 = v67;
    }
    v28 = *(_QWORD *)(v26 + 12696);
    if ( *(_DWORD *)(v28 + 32) == *(_DWORD *)(v28 + 16) )
    {
      *(_DWORD *)(v28 + 2120) = 0;
      *(_BYTE *)(v28 + 2144) = 0;
    }
    if ( v25 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)v23 + 362));
    if ( v24 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)v23 + 361));
  }
  v9 = (char *)this + 208;
  if ( !*((_DWORD *)v9 + 1) )
    return 3221225473LL;
  v10 = *((_QWORD *)*v4 + 686);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v10);
  *((_DWORD *)*v4 + 912) = v7;
  *((_QWORD *)*v4 + 457) = v9;
  v11 = *v4;
  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2021;
    v55 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v55[3] = gCddImageInfo;
    v55[4] = (unsigned int)dword_14003E570;
    v55[5] = 215857758;
    WdLogGlobalForLineNumber = 2021;
  }
  CurrentThread = KeGetCurrentThread();
  if ( *(struct _KTHREAD **)(*((_QWORD *)v11 + 686) + 8LL) != CurrentThread && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("CddIssueCommand: worker thread submission mutex is not held\n");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 2025;
    v56 = (_QWORD *)WdLogNewEntry5_WdError();
    v56[3] = gCddImageInfo;
    CurrentThread = (struct _KTHREAD *)(unsigned int)dword_14003E570;
    v56[4] = (unsigned int)dword_14003E570;
    v56[5] = 215857758;
    WdLogGlobalForLineNumber = 2025;
    __debugbreak();
  }
  v15 = *((_BYTE *)v11 + 2719) == 0;
  *((_QWORD *)v11 + 322) = KeGetCurrentThread();
  *((_DWORD *)v11 + 900) = 18;
  *((_QWORD *)v11 + 452) = 0;
  if ( !v15 )
  {
    v18 = (int (__fastcall *)(__int64, char *, __int64))*((_QWORD *)v11 + 54);
    CurrentProcess = PsGetCurrentProcess(CurrentThread, v12, v13);
    if ( v18(CurrentProcess, (char *)v11 + 3624, 17) >= 0 )
      *((_QWORD *)v11 + 452) = (char *)v11 + 3624;
  }
  KeSetEvent(*((PRKEVENT *)v11 + 326), 0, 0);
  KeWaitForSingleObject(*((PVOID *)v11 + 329), Executive, 0, 0, 0);
  KeClearEvent(*((PRKEVENT *)v11 + 326));
  *((_QWORD *)v11 + 322) = 0;
  v16 = *((_DWORD *)v11 + 902);
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v10);
  return v16;
}

```

## disassembly

```asm
0x14000e880  mov     [rsp+arg_8], edx
0x14000e884  push    rbx
0x14000e885  push    rbp
0x14000e886  push    rsi
0x14000e887  push    rdi
0x14000e888  push    r14
0x14000e88a  push    r15
0x14000e88c  sub     rsp, 78h
0x14000e890  mov     eax, [rcx+80h]
0x14000e896  lea     rdi, [rcx+8]
0x14000e89a  mov     [rsp+0A8h+arg_10], r12
0x14000e8a2  mov     r12, r9
0x14000e8a5  mov     [rsp+0A8h+var_38], r13
0x14000e8aa  mov     ebx, r8d
0x14000e8ad  mov     r15d, edx
0x14000e8b0  mov     rsi, rcx
0x14000e8b3  test    al, 20h
0x14000e8b5  jz      loc_14000EA63
0x14000e8bb  xor     ebp, ebp
0x14000e8bd  mov     eax, [rsi+80h]
0x14000e8c3  test    al, 20h
0x14000e8c5  jnz     loc_14000EAF3
0x14000e8cb  jmp     short loc_14000E8FD
0x14000e8cd  test    r12b, r12b
0x14000e8d0  jz      short loc_14000E8E5
0x14000e8d2  mov     rcx, [rbx+0B50h]
0x14000e8d9  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000e8e0  nop     dword ptr [rax+rax+00h]
0x14000e8e5  test    r13b, r13b
0x14000e8e8  jz      short loc_14000E8FD
0x14000e8ea  mov     rcx, [rbx+0B48h]
0x14000e8f1  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000e8f8  nop     dword ptr [rax+rax+00h]
0x14000e8fd  mov     r13, [rsp+0A8h+var_38]
0x14000e902  add     rsi, 0D0h
0x14000e909  mov     r12, [rsp+0A8h+arg_10]
0x14000e911  cmp     dword ptr [rsi+4], 0
0x14000e915  jz      loc_14000EA1A
0x14000e91b  mov     rax, [rdi]
0x14000e91e  mov     r14, [rax+1570h]
0x14000e925  mov     rcx, r14
0x14000e928  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000e92f  nop     dword ptr [rax+rax+00h]
0x14000e934  mov     rax, [rdi]
0x14000e937  mov     [rax+0E40h], r15d
0x14000e93e  mov     rax, [rdi]
0x14000e941  mov     [rax+0E48h], rsi
0x14000e948  mov     rbx, [rdi]
0x14000e94b  call    cs:__imp_KeGetCurrentIrql
0x14000e952  nop     dword ptr [rax+rax+00h]
0x14000e957  test    al, al
0x14000e959  jnz     loc_14000EEA2
0x14000e95f  mov     rcx, gs:188h
0x14000e968  mov     rax, [rbx+1570h]
0x14000e96f  cmp     [rax+8], rcx
0x14000e973  jnz     loc_14000EEF5
0x14000e979  mov     rax, gs:188h
0x14000e982  cmp     byte ptr [rbx+0A9Fh], 0
0x14000e989  mov     [rbx+0A10h], rax
0x14000e990  mov     dword ptr [rbx+0E10h], 12h
0x14000e99a  mov     [rbx+0E20h], rbp
0x14000e9a1  jnz     short loc_14000EA21
0x14000e9a3  mov     rcx, [rbx+0A30h]; Event
0x14000e9aa  xor     r8d, r8d; Wait
0x14000e9ad  xor     edx, edx; Increment
0x14000e9af  call    cs:__imp_KeSetEvent
0x14000e9b6  nop     dword ptr [rax+rax+00h]
0x14000e9bb  mov     rcx, [rbx+0A48h]; Object
0x14000e9c2  xor     r9d, r9d; Alertable
0x14000e9c5  xor     r8d, r8d; WaitMode
0x14000e9c8  mov     [rsp+0A8h+Timeout], rbp; Timeout
0x14000e9cd  xor     edx, edx; WaitReason
0x14000e9cf  call    cs:__imp_KeWaitForSingleObject
0x14000e9d6  nop     dword ptr [rax+rax+00h]
0x14000e9db  mov     rcx, [rbx+0A30h]; Event
0x14000e9e2  call    cs:__imp_KeClearEvent
0x14000e9e9  nop     dword ptr [rax+rax+00h]
0x14000e9ee  mov     [rbx+0A10h], rbp
0x14000e9f5  mov     rcx, r14
0x14000e9f8  mov     ebx, [rbx+0E18h]
0x14000e9fe  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000ea05  nop     dword ptr [rax+rax+00h]
0x14000ea0a  mov     eax, ebx
0x14000ea0c  add     rsp, 78h
0x14000ea10  pop     r15
0x14000ea12  pop     r14
0x14000ea14  pop     rdi
0x14000ea15  pop     rsi
0x14000ea16  pop     rbp
0x14000ea17  pop     rbx
0x14000ea18  retn
0x14000ea1a  mov     eax, 0C0000001h
0x14000ea1f  jmp     short loc_14000EA0C
0x14000ea21  mov     rdi, [rbx+1B0h]
0x14000ea28  lea     rsi, [rbx+0E28h]
0x14000ea2f  call    cs:__imp_PsGetCurrentProcess
0x14000ea36  nop     dword ptr [rax+rax+00h]
0x14000ea3b  mov     r8d, 11h
0x14000ea41  mov     rdx, rsi
0x14000ea44  mov     rcx, rax
0x14000ea47  mov     rax, rdi
0x14000ea4a  call    _guard_dispatch_icall
0x14000ea4f  test    eax, eax
0x14000ea51  js      loc_14000E9A3
0x14000ea57  mov     [rbx+0E20h], rsi
0x14000ea5e  jmp     loc_14000E9A3
0x14000ea63  mov     r14, [rdi]
0x14000ea66  mov     [rsp+0A8h+var_50], r14
0x14000ea6b  mov     rcx, [r14+0B48h]
0x14000ea72  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000ea79  nop     dword ptr [rax+rax+00h]
0x14000ea7e  mov     rcx, [r14+0B50h]
0x14000ea85  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000ea8c  nop     dword ptr [rax+rax+00h]
0x14000ea91  mov     rcx, [rdi]
0x14000ea94  xor     ebp, ebp
0x14000ea96  mov     rax, [rcx+3198h]
0x14000ea9d  mov     edx, [rax+8]
0x14000eaa0  mov     rax, [rcx+31A0h]
0x14000eaa7  mov     ecx, [rax+8]
0x14000eaaa  test    ebx, ebx
0x14000eaac  jnz     loc_14000EBF5
0x14000eab2  movzx   eax, byte ptr [rcx+rsi+2Ch]
0x14000eab7  movzx   r13d, byte ptr [rdx+rsi+2Ch]
0x14000eabd  mov     [rsp+0A8h+arg_0], eax
0x14000eac4  mov     rcx, [r14+0B50h]
0x14000eacb  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000ead2  nop     dword ptr [rax+rax+00h]
0x14000ead7  mov     rcx, [r14+0B48h]
0x14000eade  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000eae5  nop     dword ptr [rax+rax+00h]
0x14000eaea  test    r13d, r13d
0x14000eaed  jz      loc_14000EE3D
0x14000eaf3  mov     rbx, [rsi+8]
0x14000eaf7  lea     rdi, [rsi+8]
0x14000eafb  mov     r13b, 1
0x14000eafe  mov     [rsp+0A8h+var_50], rbx
0x14000eb03  mov     [rsp+0A8h+var_48], 101h
0x14000eb0a  movzx   r12d, r13b
0x14000eb0e  mov     [rsp+0A8h+var_46], 0
0x14000eb13  mov     rcx, [rbx+0B48h]
0x14000eb1a  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000eb21  nop     dword ptr [rax+rax+00h]
0x14000eb26  mov     rcx, [rbx+0B50h]
0x14000eb2d  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000eb34  nop     dword ptr [rax+rax+00h]
0x14000eb39  mov     r14, [rdi]
0x14000eb3c  mov     rax, gs:188h
0x14000eb45  cmp     rax, [r14+0A08h]
0x14000eb4c  jz      loc_14000EBE9
0x14000eb52  lea     rcx, [rsp+0A8h+var_50]; this
0x14000eb57  call    ?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::EnableWorkerThreadAccess(void)
0x14000eb5c  call    cs:__imp_KeGetCurrentIrql
0x14000eb63  nop     dword ptr [rax+rax+00h]
0x14000eb68  test    al, al
0x14000eb6a  jnz     loc_14000EE4F
0x14000eb70  mov     rbx, [r14+1570h]
0x14000eb77  mov     rcx, rbx
0x14000eb7a  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000eb81  nop     dword ptr [rax+rax+00h]
0x14000eb86  mov     edx, 0Dh
0x14000eb8b  mov     [r14+0E40h], ebp
0x14000eb92  mov     rcx, r14
0x14000eb95  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000eb9a  mov     rcx, rbx
0x14000eb9d  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000eba4  nop     dword ptr [rax+rax+00h]
0x14000eba9  lea     rcx, [rsp+0A8h+var_50]; this
0x14000ebae  call    ?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::DisableWorkerThreadAccess(void)
0x14000ebb3  movzx   r12d, byte ptr [rsp+0A8h+var_48+1]
0x14000ebb9  movzx   r13d, byte ptr [rsp+0A8h+var_48]
0x14000ebbf  mov     rbx, [rsp+0A8h+var_50]
0x14000ebc4  mov     rdx, [r14+3198h]
0x14000ebcb  mov     ecx, [rdx+10h]
0x14000ebce  cmp     [rdx+20h], ecx
0x14000ebd1  jnz     loc_14000E8CD
0x14000ebd7  mov     [rdx+848h], ebp
0x14000ebdd  mov     byte ptr [rdx+860h], 0
0x14000ebe4  jmp     loc_14000E8CD
0x14000ebe9  xor     edx, edx; unsigned int
0x14000ebeb  mov     rcx, r14; this
0x14000ebee  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
0x14000ebf3  jmp     short loc_14000EBC4
0x14000ebf5  mov     [rsp+0A8h+var_78], ebp
0x14000ebf9  mov     eax, ebp
0x14000ebfb  mov     [rsp+0A8h+arg_0], eax
0x14000ec02  mov     r13d, ebp
0x14000ec05  mov     r8d, ebp
0x14000ec08  test    ebx, ebx
0x14000ec0a  jz      loc_14000EAC4
0x14000ec10  mov     rdi, rdx
0x14000ec13  lea     r14, [rsi+498h]
0x14000ec1a  mov     r15, rcx
0x14000ec1d  nop     dword ptr [rax]
0x14000ec20  mov     ecx, r8d
0x14000ec23  mov     r9, r14
0x14000ec26  shl     rcx, 4
0x14000ec2a  mov     [rsp+0A8h+var_68], r14
0x14000ec2f  mov     [rsp+0A8h+var_58], rcx
0x14000ec34  cmp     [rsi+rdi+2Ch], bpl
0x14000ec39  jz      loc_14000EE14
0x14000ec3f  lea     rax, [rcx+r12]
0x14000ec43  mov     rcx, [r14]
0x14000ec46  mov     [rsp+0A8h+var_70], rax
0x14000ec4b  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000ec52  nop     dword ptr [rax+rax+00h]
0x14000ec57  lea     rcx, [rdi+rdi*8]
0x14000ec5b  mov     r9d, ebp
0x14000ec5e  shl     rcx, 5
0x14000ec62  add     rcx, 258h
0x14000ec69  add     rcx, rsi
0x14000ec6c  mov     [rsp+0A8h+var_60], rcx
0x14000ec71  mov     r14d, [rcx+100h]
0x14000ec78  cmp     r9d, r14d
0x14000ec7b  jnb     short loc_14000ECD9
0x14000ec7d  mov     r11, [rsp+0A8h+var_70]
0x14000ec82  mov     r10d, r9d
0x14000ec85  shl     r10, 4
0x14000ec89  add     r10, rcx
0x14000ec8c  mov     r8d, [r11]
0x14000ec8f  mov     ecx, [r11+8]
0x14000ec93  mov     eax, [r10]
0x14000ec96  cmp     r8d, eax
0x14000ec99  mov     edx, [r10+8]
0x14000ec9d  cmovle  r8d, eax
0x14000eca1  cmp     ecx, edx
0x14000eca3  cmovge  ecx, edx
0x14000eca6  cmp     r8d, ecx
0x14000eca9  jge     short loc_14000ECCF
0x14000ecab  mov     eax, [r10+0Ch]
0x14000ecaf  mov     ecx, [r11+0Ch]
0x14000ecb3  cmp     ecx, eax
0x14000ecb5  mov     r8d, [r10+4]
0x14000ecb9  mov     edx, [r11+4]
0x14000ecbd  cmovge  ecx, eax
0x14000ecc0  cmp     edx, r8d
0x14000ecc3  cmovle  edx, r8d
0x14000ecc7  cmp     edx, ecx
0x14000ecc9  jl      loc_14000EE26
0x14000eccf  mov     rcx, [rsp+0A8h+var_60]
0x14000ecd4  inc     r9d
0x14000ecd7  jmp     short loc_14000EC78
0x14000ecd9  mov     dword ptr [rsp+0A8h+var_70], ebp
0x14000ecdd  mov     rcx, [rsp+0A8h+var_68]
0x14000ece2  mov     rcx, [rcx]
0x14000ece5  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000ecec  nop     dword ptr [rax+rax+00h]
0x14000ecf1  mov     eax, [rsp+0A8h+arg_0]
0x14000ecf8  mov     rcx, [rsp+0A8h+var_58]
0x14000ecfd  mov     r8d, [rsp+0A8h+var_78]
0x14000ed02  mov     edx, dword ptr [rsp+0A8h+var_70]
0x14000ed06  mov     r9, [rsp+0A8h+var_68]
0x14000ed0b  or      r13d, edx
0x14000ed0e  cmp     [r15+rsi+2Ch], bpl
0x14000ed13  jz      loc_14000EE1B
0x14000ed19  lea     rax, [rcx+r12]
0x14000ed1d  mov     r14, r9
0x14000ed20  mov     rcx, [r9]
0x14000ed23  mov     [rsp+0A8h+var_58], rax
0x14000ed28  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000ed2f  nop     dword ptr [rax+rax+00h]
0x14000ed34  lea     rcx, [r15+r15*8]
0x14000ed38  mov     r9d, ebp
0x14000ed3b  shl     rcx, 5
0x14000ed3f  add     rcx, 258h
0x14000ed46  add     rcx, rsi
0x14000ed49  mov     [rsp+0A8h+var_60], rcx
0x14000ed4e  mov     eax, [rcx+100h]
0x14000ed54  mov     dword ptr [rsp+0A8h+var_70], eax
0x14000ed58  cmp     r9d, eax
0x14000ed5b  jnb     short loc_14000EDBC
0x14000ed5d  mov     r11, [rsp+0A8h+var_58]
0x14000ed62  mov     r10d, r9d
0x14000ed65  shl     r10, 4
0x14000ed69  add     r10, rcx
0x14000ed6c  mov     ecx, [r11+8]
0x14000ed70  mov     edx, [r11]
0x14000ed73  mov     eax, [r10+8]
0x14000ed77  cmp     ecx, eax
0x14000ed79  mov     r8d, [r10]
0x14000ed7c  cmovge  ecx, eax
0x14000ed7f  cmp     edx, r8d
0x14000ed82  cmovle  edx, r8d
0x14000ed86  cmp     edx, ecx
0x14000ed88  jge     short loc_14000EDAE
0x14000ed8a  mov     eax, [r10+0Ch]
0x14000ed8e  mov     ecx, [r11+0Ch]
0x14000ed92  cmp     ecx, eax
0x14000ed94  mov     r8d, [r10+4]
0x14000ed98  mov     edx, [r11+4]
0x14000ed9c  cmovge  ecx, eax
0x14000ed9f  cmp     edx, r8d
0x14000eda2  cmovle  edx, r8d
0x14000eda6  cmp     edx, ecx
0x14000eda8  jl      loc_14000EE33
0x14000edae  mov     eax, dword ptr [rsp+0A8h+var_70]
0x14000edb2  inc     r9d
0x14000edb5  mov     rcx, [rsp+0A8h+var_60]
0x14000edba  jmp     short loc_14000ED58
0x14000edbc  mov     dword ptr [rsp+0A8h+var_70], ebp
  ... truncated ...
```
