# VidSchiUpdatePresentParameters

- ea: `0x140017330`
- end: `0x140017749`
- name: `VidSchiUpdatePresentParameters`
- size: `1049`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000409c`

## callees

- `0x140017330`
- `0x140017750`
- `0x140030efc`
- `0x140043c5c`
- `0x140058f50`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400173bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400174bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400173bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400174bc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400173f4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140017565`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400173f4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140017565`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400176c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400176c8`
- `ntoskrnl!RtlCompareMemory` at `0x1400175eb`
- `ntoskrnl!RtlCompareMemory` at `0x14001760c`
- `ntoskrnl!RtlCompareMemory` at `0x1400175eb`
- `ntoskrnl!RtlCompareMemory` at `0x14001760c`
- `watchdog!WdLogSingleEntry5` at `0x1400176b2`
- `watchdog!WdLogSingleEntry5` at `0x1400176b2`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14001768b`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VidSchiUpdatePresentParameters(struct _VIDSCH_GLOBAL *a1, int *a2)
{
  int *v2; // rsi
  __int128 v3; // xmm0
  unsigned int v4; // ebx
  unsigned int v5; // r15d
  __int128 v6; // xmm1
  __int64 v7; // r12
  bool v9; // r13
  unsigned int v10; // ebx
  bool v11; // zf
  bool v12; // di
  int *v13; // rdx
  unsigned int v14; // eax
  int v15; // eax
  char v16; // cl
  int v17; // eax
  int v18; // eax
  char v19; // cl
  __int64 result; // rax
  unsigned int v21; // eax
  __int128 v22; // xmm6
  int v23; // edi
  __int128 v24; // xmm7
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  struct _KLOCK_QUEUE_HANDLE *v29; // rcx
  char v30; // cl
  int v31; // eax
  unsigned int i; // edx
  __int64 v33; // r8
  char v34; // cl
  unsigned int v35; // [rsp+30h] [rbp-A9h]
  unsigned int v36; // [rsp+34h] [rbp-A5h]
  struct _VIDSCH_GLOBAL *v37; // [rsp+40h] [rbp-99h] BYREF
  _QWORD v38[2]; // [rsp+48h] [rbp-91h] BYREF
  char v39; // [rsp+58h] [rbp-81h]
  int v40; // [rsp+5Ch] [rbp-7Dh]
  __int64 v41; // [rsp+60h] [rbp-79h]
  _QWORD *v42; // [rsp+68h] [rbp-71h]
  int *v43; // [rsp+70h] [rbp-69h]
  char *v44; // [rsp+78h] [rbp-61h]
  struct _KLOCK_QUEUE_HANDLE v45; // [rsp+80h] [rbp-59h] BYREF
  __int16 v46; // [rsp+98h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp-39h] BYREF
  __int128 Source2; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v49; // [rsp+C8h] [rbp-11h] BYREF

  v2 = a2;
  v3 = *(_OWORD *)(a2 + 109);
  v4 = *a2;
  v6 = *(_OWORD *)(a2 + 113);
  v36 = a2[29];
  LOBYTE(v5) = v36;
  v7 = *((_QWORD *)a1 + v36 + 441);
  v42 = (_QWORD *)((char *)a1 + 8 * v36 + 3528);
  Source2 = v3;
  v41 = v7;
  v9 = (v4 & 0x800000) != 0;
  v10 = v4 >> 31;
  v49 = v6;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &LockHandle);
  v11 = (_BYTE)v10 == *(_BYTE *)(v7 + 3200);
  *(_BYTE *)(v7 + 3200) = v10;
  v12 = !v11;
  if ( !(_BYTE)v10
    || RtlCompareMemory((const void *)(v7 + 3204), &Source2, 0x10u) == 16
    && RtlCompareMemory((const void *)(v7 + 3220), &v49, 0x10u) == 16 )
  {
    if ( !v12 )
    {
LABEL_3:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v13 = v2 + 150;
      v14 = v2[150];
      LODWORD(v2) = 0;
      v10 = v14 & 0x3FF;
      v15 = (v14 >> 10) & 0x3FF;
      v43 = v13;
      v16 = -1;
      LODWORD(v7) = 0;
      if ( *((_BYTE *)a1 + 164) )
        LODWORD(v2) = v15;
      v11 = !_BitScanForward((unsigned int *)&v17, v10);
      if ( !v11 )
        v16 = v17;
      v11 = !_BitScanForward((unsigned int *)&v18, (unsigned int)v2);
      v5 = v16;
      v19 = -1;
      if ( !v11 )
        v19 = v18;
      result = (unsigned int)v19;
      v35 = v19;
      goto LABEL_10;
    }
  }
  else
  {
    *(_OWORD *)(v7 + 3204) = Source2;
    *(_OWORD *)(v7 + 3220) = v49;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)a1 + 40) )
      goto LABEL_3;
    v33 = *(int *)(304LL * i + *((_QWORD *)a1 + v36 + 441) + 188);
    if ( (int)v33 > -1 && *(_DWORD *)(160 * v33 + *((_QWORD *)a1 + 457) + 112) == 2 )
      break;
  }
  g_DxgMmsBugcheckExportIndex = 1;
  WdLogSingleEntry5(0, 281, 0x100000, 0, v36, a1);
  WdLogGlobalForLineNumber = 926;
LABEL_31:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(v29);
LABEL_18:
  v13 = v43;
  v30 = -1;
  v10 &= ~(1 << v5);
  v11 = !_BitScanForward((unsigned int *)&v31, v10);
  if ( !v11 )
    v30 = v31;
  result = v35;
  v5 = v30;
  while ( 1 )
  {
    LODWORD(v7) = v7 + 1;
LABEL_10:
    if ( !v10 && !(_DWORD)v2 )
      return result;
    if ( v5 < (unsigned int)result )
    {
      v21 = 2 * v7 * (v13[2] + 28);
      v22 = *(_OWORD *)&v13[v21 + 42];
      v23 = v13[v21 + 50];
      v24 = *(_OWORD *)&v13[v21 + 46];
      v46 = 0;
      v44 = (char *)a1 + 2096;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &v45);
      LOBYTE(v46) = 1;
      v37 = a1;
      v38[1] = v38;
      v38[0] = v38;
      v39 = 0;
      v40 = 2;
      v25 = 304LL * v5;
      v26 = v41;
      *(_OWORD *)(v25 + v41 + 152) = v22;
      *(_OWORD *)(v25 + v26 + 168) = v24;
      *(_DWORD *)(v25 + v26 + 184) = v23;
      v27 = *(int *)(v25 + *v42 + 188);
      if ( (int)v27 > -1 )
      {
        v28 = *((_QWORD *)a1 + 457) + 160 * v27;
        if ( v28 )
        {
          if ( *(_DWORD *)(v28 + 112) == 1 )
          {
            *(_BYTE *)(v28 + 96) = 1;
            *(_BYTE *)(v28 + 108) = v9;
            if ( VidSchiCheckPlaneIndependentFlipCondition(a1, v36, v5) )
              VidSchiFlushPendingTokenList((struct HwQueueStagingList *)&v37, a1);
          }
        }
      }
      HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v37);
      if ( (_BYTE)v46 )
      {
        v29 = &v45;
        if ( HIBYTE(v46) )
          goto LABEL_31;
        KeReleaseInStackQueuedSpinLock(&v45);
      }
      goto LABEL_18;
    }
    v34 = -1;
    LODWORD(v2) = ~(1 << result) & (unsigned int)v2;
    v11 = !_BitScanForward((unsigned int *)&result, (unsigned int)v2);
    if ( !v11 )
      v34 = result;
    result = (unsigned int)v34;
    v35 = v34;
  }
}

```

## disassembly

```asm
0x140017330  mov     [rsp-8+arg_10], rbx
0x140017335  push    rbp
0x140017336  push    rsi
0x140017337  push    rdi
0x140017338  push    r12
0x14001733a  push    r13
0x14001733c  push    r14
0x14001733e  push    r15
0x140017340  lea     rbp, [rsp-27h]
0x140017345  sub     rsp, 100h
0x14001734c  mov     rax, cs:__security_cookie
0x140017353  xor     rax, rsp
0x140017356  mov     [rbp+57h+var_58], rax
0x14001735a  mov     eax, [rdx+74h]
0x14001735d  mov     rsi, rdx
0x140017360  movups  xmm0, xmmword ptr [rdx+1B4h]
0x140017367  mov     ebx, [rdx]
0x140017369  mov     r15d, eax
0x14001736c  movups  xmm1, xmmword ptr [rdx+1C4h]
0x140017373  mov     [rsp+130h+var_FC], eax
0x140017377  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001737b  lea     rax, [rcx+0DC8h]
0x140017382  mov     r13d, ebx
0x140017385  mov     r12, [rax+r15*8]
0x140017389  lea     rax, [rax+r15*8]
0x14001738d  mov     [rbp+57h+var_C8], rax
0x140017391  mov     r14, rcx
0x140017394  movups  [rbp+57h+Source2], xmm0
0x140017398  xor     eax, eax
0x14001739a  shr     r13d, 17h
0x14001739e  xorps   xmm0, xmm0
0x1400173a1  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400173a5  add     rcx, 830h; SpinLock
0x1400173ac  mov     [rbp+57h+var_D0], r12
0x1400173b0  and     r13b, 1
0x1400173b4  shr     ebx, 1Fh
0x1400173b7  movups  [rbp+57h+var_68], xmm1
0x1400173bb  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400173bf  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400173c6  nop     dword ptr [rax+rax+00h]
0x1400173cb  cmp     bl, [r12+0C80h]
0x1400173d3  mov     [r12+0C80h], bl
0x1400173db  setnz   dil
0x1400173df  test    bl, bl
0x1400173e1  jnz     loc_1400175D9
0x1400173e7  test    dil, dil
0x1400173ea  jnz     loc_14001763C
0x1400173f0  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400173f4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400173fb  nop     dword ptr [rax+rax+00h]
0x140017400  xor     r8d, r8d
0x140017403  movaps  [rsp+130h+var_40], xmm6
0x14001740b  lea     rdx, [rsi+258h]
0x140017412  mov     [rsp+130h+var_100], r8d
0x140017417  mov     eax, [rdx]
0x140017419  mov     esi, r8d
0x14001741c  mov     ebx, eax
0x14001741e  mov     [rsp+130h+var_100], r8d
0x140017423  shr     eax, 0Ah
0x140017426  and     ebx, 3FFh
0x14001742c  and     eax, 3FFh
0x140017431  mov     [rbp+57h+var_C0], rdx
0x140017435  cmp     [r14+0A4h], r8b
0x14001743c  mov     ecx, 0FFFFFFFFh
0x140017441  mov     r12d, r8d
0x140017444  movaps  [rsp+130h+var_50], xmm7
0x14001744c  cmovnz  esi, eax
0x14001744f  bsf     eax, ebx
0x140017452  cmovnz  ecx, eax
0x140017455  bsf     eax, esi
0x140017458  movsx   r15d, cl
0x14001745c  mov     ecx, 0FFFFFFFFh
0x140017461  cmovnz  ecx, eax
0x140017464  movsx   eax, cl
0x140017467  mov     [rsp+130h+var_100], eax
0x14001746b  test    ebx, ebx
0x14001746d  jnz     short loc_140017477
0x14001746f  test    esi, esi
0x140017471  jz      loc_1400175A1
0x140017477  cmp     r15d, eax
0x14001747a  jnb     loc_14001771E
0x140017480  mov     eax, [rdx+8]
0x140017483  add     eax, 1Ch
0x140017486  imul    eax, r12d
0x14001748a  shl     eax, 3
0x14001748d  movups  xmm6, xmmword ptr [rax+rdx+0A8h]
0x140017495  mov     edi, [rax+rdx+0C8h]
0x14001749c  movups  xmm7, xmmword ptr [rax+rdx+0B8h]
0x1400174a4  lea     rax, [r14+830h]
0x1400174ab  mov     [rbp+57h+var_98], 0
0x1400174b1  mov     rcx, rax; SpinLock
0x1400174b4  mov     [rbp+57h+var_B8], rax
0x1400174b8  lea     rdx, [rbp+57h+var_B0]; LockHandle
0x1400174bc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400174c3  nop     dword ptr [rax+rax+00h]
0x1400174c8  mov     byte ptr [rbp+57h+var_98], 1
0x1400174cc  lea     rax, [rsp+130h+var_E8]
0x1400174d1  mov     [rsp+130h+var_F0], r14
0x1400174d6  xorps   xmm0, xmm0
0x1400174d9  movups  [rsp+130h+var_E8], xmm0
0x1400174de  mov     qword ptr [rsp+130h+var_E8+8], rax
0x1400174e3  lea     rax, [rsp+130h+var_E8]
0x1400174e8  mov     qword ptr [rsp+130h+var_E8], rax
0x1400174ed  mov     [rsp+130h+var_D8], 0
0x1400174f2  mov     [rbp+57h+var_D4], 2
0x1400174f9  mov     eax, r15d
0x1400174fc  imul    rcx, rax, 130h
0x140017503  mov     rax, [rbp+57h+var_D0]
0x140017507  movups  xmmword ptr [rcx+rax+98h], xmm6
0x14001750f  movups  xmmword ptr [rcx+rax+0A8h], xmm7
0x140017517  mov     [rcx+rax+0B8h], edi
0x14001751e  mov     rax, [rbp+57h+var_C8]
0x140017522  mov     rax, [rax]
0x140017525  movsxd  rdx, dword ptr [rcx+rax+0BCh]
0x14001752d  cmp     edx, 0FFFFFFFFh
0x140017530  jle     short loc_140017547
0x140017532  lea     rdx, [rdx+rdx*4]
0x140017536  shl     rdx, 5
0x14001753a  add     rdx, [r14+0E48h]
0x140017541  jnz     loc_1400176D9
0x140017547  lea     rcx, [rsp+130h+var_F0]; this
0x14001754c  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x140017551  cmp     byte ptr [rbp+57h+var_98], 0
0x140017555  jz      short loc_140017571
0x140017557  cmp     byte ptr [rbp+57h+var_98+1], 0
0x14001755b  lea     rcx, [rbp+57h+var_B0]; LockHandle
0x14001755f  jnz     loc_1400176C8
0x140017565  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001756c  nop     dword ptr [rax+rax+00h]
0x140017571  mov     rdx, [rbp+57h+var_C0]
0x140017575  mov     ecx, r15d
0x140017578  mov     eax, 1
0x14001757d  xor     r8d, r8d
0x140017580  shl     eax, cl
0x140017582  mov     ecx, 0FFFFFFFFh
0x140017587  not     eax
0x140017589  and     ebx, eax
0x14001758b  bsf     eax, ebx
0x14001758e  cmovnz  ecx, eax
0x140017591  mov     eax, [rsp+130h+var_100]
0x140017595  movsx   r15d, cl
0x140017599  inc     r12d
0x14001759c  jmp     loc_14001746B
0x1400175a1  movaps  xmm6, [rsp+130h+var_40]
0x1400175a9  movaps  xmm7, [rsp+130h+var_50]
0x1400175b1  mov     rcx, [rbp+57h+var_58]
0x1400175b5  xor     rcx, rsp; StackCookie
0x1400175b8  call    __security_check_cookie
0x1400175bd  mov     rbx, [rsp+130h+arg_10]
0x1400175c5  add     rsp, 100h
0x1400175cc  pop     r15
0x1400175ce  pop     r14
0x1400175d0  pop     r13
0x1400175d2  pop     r12
0x1400175d4  pop     rdi
0x1400175d5  pop     rsi
0x1400175d6  pop     rbp
0x1400175d7  retn
0x1400175d9  mov     r8d, 10h; Length
0x1400175df  lea     rdx, [rbp+57h+Source2]; Source2
0x1400175e3  lea     rcx, [r12+0C84h]; Source1
0x1400175eb  call    cs:__imp_RtlCompareMemory
0x1400175f2  nop     dword ptr [rax+rax+00h]
0x1400175f7  cmp     rax, 10h
0x1400175fb  jnz     short loc_140017622
0x1400175fd  mov     r8, rax; Length
0x140017600  lea     rdx, [rbp+57h+var_68]; Source2
0x140017604  lea     rcx, [r12+0C94h]; Source1
0x14001760c  call    cs:__imp_RtlCompareMemory
0x140017613  nop     dword ptr [rax+rax+00h]
0x140017618  cmp     rax, 10h
0x14001761c  jz      loc_1400173E7
0x140017622  movups  xmm0, [rbp+57h+Source2]
0x140017626  movups  xmmword ptr [r12+0C84h], xmm0
0x14001762f  movups  xmm1, [rbp+57h+var_68]
0x140017633  movups  xmmword ptr [r12+0C94h], xmm1
0x14001763c  mov     r9d, [r14+0A0h]
0x140017643  xor     edx, edx
0x140017645  cmp     edx, r9d
0x140017648  jnb     loc_1400173F0
0x14001764e  mov     eax, edx
0x140017650  imul    rcx, rax, 130h
0x140017657  mov     rax, [r14+r15*8+0DC8h]
0x14001765f  movsxd  r8, dword ptr [rcx+rax+0BCh]
0x140017667  cmp     r8d, 0FFFFFFFFh
0x14001766b  jle     loc_140017742
0x140017671  mov     rax, [r14+0E48h]
0x140017678  lea     rcx, [r8+r8*4]
0x14001767c  shl     rcx, 5
0x140017680  cmp     dword ptr [rcx+rax+70h], 2
0x140017685  jnz     loc_140017742
0x14001768b  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140017692  mov     dword ptr [rax], 1
0x140017698  mov     [rsp+130h+var_108], r14
0x14001769d  xor     r9d, r9d
0x1400176a0  mov     edx, 119h
0x1400176a5  mov     [rsp+130h+var_110], r15
0x1400176aa  xor     ecx, ecx
0x1400176ac  mov     r8d, 100000h
0x1400176b2  call    cs:__imp_WdLogSingleEntry5
0x1400176b9  nop     dword ptr [rax+rax+00h]
0x1400176be  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x1400176c8  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400176cf  nop     dword ptr [rax+rax+00h]
0x1400176d4  jmp     loc_140017571
0x1400176d9  cmp     dword ptr [rdx+70h], 1
0x1400176dd  jnz     loc_140017547
0x1400176e3  mov     r10d, [rsp+130h+var_FC]
0x1400176e8  mov     r8d, r15d; unsigned int
0x1400176eb  mov     byte ptr [rdx+60h], 1
0x1400176ef  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x1400176f2  mov     [rdx+6Ch], r13b
0x1400176f6  mov     edx, r10d; unsigned int
0x1400176f9  call    ?VidSchiCheckPlaneIndependentFlipCondition@@YA_NPEAU_VIDSCH_GLOBAL@@II@Z; VidSchiCheckPlaneIndependentFlipCondition(_VIDSCH_GLOBAL *,uint,uint)
0x1400176fe  test    al, al
0x140017700  jz      loc_140017547
0x140017706  mov     r9d, r15d
0x140017709  lea     rcx, [rsp+130h+var_F0]; struct HwQueueStagingList *
0x14001770e  mov     r8d, r10d
0x140017711  mov     rdx, r14; struct _VIDSCH_GLOBAL *
0x140017714  call    VidSchiFlushPendingTokenList
0x140017719  jmp     loc_140017547
0x14001771e  mov     ecx, eax
0x140017720  mov     eax, 1
0x140017725  shl     eax, cl
0x140017727  mov     ecx, 0FFFFFFFFh
0x14001772c  not     eax
0x14001772e  and     esi, eax
0x140017730  bsf     eax, esi
0x140017733  cmovnz  ecx, eax
0x140017736  movsx   eax, cl
0x140017739  mov     [rsp+130h+var_100], eax
0x14001773d  jmp     loc_140017599
0x140017742  inc     edx
0x140017744  jmp     loc_140017645
```
