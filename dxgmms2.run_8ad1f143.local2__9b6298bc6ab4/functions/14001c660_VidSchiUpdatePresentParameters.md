# VidSchiUpdatePresentParameters

- ea: `0x14001c660`
- end: `0x14001ca79`
- name: `VidSchiUpdatePresentParameters`
- size: `1049`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004420`

## callees

- `0x14001c660`
- `0x14001ca80`
- `0x14003308c`
- `0x140043aec`
- `0x140058680`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c6ef`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c7ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c6ef`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001c7ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c724`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c895`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c724`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001c895`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c9f8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001c9f8`
- `ntoskrnl!RtlCompareMemory` at `0x14001c91b`
- `ntoskrnl!RtlCompareMemory` at `0x14001c93c`
- `ntoskrnl!RtlCompareMemory` at `0x14001c91b`
- `ntoskrnl!RtlCompareMemory` at `0x14001c93c`
- `watchdog!WdLogSingleEntry5` at `0x14001c9e2`
- `watchdog!WdLogSingleEntry5` at `0x14001c9e2`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14001c9bb`

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
  WdLogSingleEntry5(0, 281, 0x100000);
  WdLogGlobalForLineNumber = 921;
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
0x14001c660  mov     [rsp-8+arg_10], rbx
0x14001c665  push    rbp
0x14001c666  push    rsi
0x14001c667  push    rdi
0x14001c668  push    r12
0x14001c66a  push    r13
0x14001c66c  push    r14
0x14001c66e  push    r15
0x14001c670  lea     rbp, [rsp-27h]
0x14001c675  sub     rsp, 100h
0x14001c67c  mov     rax, cs:__security_cookie
0x14001c683  xor     rax, rsp
0x14001c686  mov     [rbp+57h+var_58], rax
0x14001c68a  mov     eax, [rdx+74h]
0x14001c68d  mov     rsi, rdx
0x14001c690  movups  xmm0, xmmword ptr [rdx+1B4h]
0x14001c697  mov     ebx, [rdx]
0x14001c699  mov     r15d, eax
0x14001c69c  movups  xmm1, xmmword ptr [rdx+1C4h]
0x14001c6a3  mov     [rsp+130h+var_FC], eax
0x14001c6a7  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14001c6ab  lea     rax, [rcx+0DC8h]
0x14001c6b2  mov     r13d, ebx
0x14001c6b5  mov     r12, [rax+r15*8]
0x14001c6b9  lea     rax, [rax+r15*8]
0x14001c6bd  mov     [rbp+57h+var_C8], rax
0x14001c6c1  mov     r14, rcx
0x14001c6c4  movups  [rbp+57h+Source2], xmm0
0x14001c6c8  xor     eax, eax
0x14001c6ca  shr     r13d, 17h
0x14001c6ce  xorps   xmm0, xmm0
0x14001c6d1  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14001c6d5  add     rcx, 830h; SpinLock
0x14001c6dc  mov     [rbp+57h+var_D0], r12
0x14001c6e0  and     r13b, 1
0x14001c6e4  shr     ebx, 1Fh
0x14001c6e7  movups  [rbp+57h+var_68], xmm1
0x14001c6eb  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14001c6ef  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001c6f6  nop     dword ptr [rax+rax+00h]
0x14001c6fb  cmp     bl, [r12+0C80h]
0x14001c703  mov     [r12+0C80h], bl
0x14001c70b  setnz   dil
0x14001c70f  test    bl, bl
0x14001c711  jnz     loc_14001C909
0x14001c717  test    dil, dil
0x14001c71a  jnz     loc_14001C96C
0x14001c720  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14001c724  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001c72b  nop     dword ptr [rax+rax+00h]
0x14001c730  xor     r8d, r8d
0x14001c733  movaps  [rsp+130h+var_40], xmm6
0x14001c73b  lea     rdx, [rsi+258h]
0x14001c742  mov     [rsp+130h+var_100], r8d
0x14001c747  mov     eax, [rdx]
0x14001c749  mov     esi, r8d
0x14001c74c  mov     ebx, eax
0x14001c74e  mov     [rsp+130h+var_100], r8d
0x14001c753  shr     eax, 0Ah
0x14001c756  and     ebx, 3FFh
0x14001c75c  and     eax, 3FFh
0x14001c761  mov     [rbp+57h+var_C0], rdx
0x14001c765  cmp     [r14+0A4h], r8b
0x14001c76c  mov     ecx, 0FFFFFFFFh
0x14001c771  mov     r12d, r8d
0x14001c774  movaps  [rsp+130h+var_50], xmm7
0x14001c77c  cmovnz  esi, eax
0x14001c77f  bsf     eax, ebx
0x14001c782  cmovnz  ecx, eax
0x14001c785  bsf     eax, esi
0x14001c788  movsx   r15d, cl
0x14001c78c  mov     ecx, 0FFFFFFFFh
0x14001c791  cmovnz  ecx, eax
0x14001c794  movsx   eax, cl
0x14001c797  mov     [rsp+130h+var_100], eax
0x14001c79b  test    ebx, ebx
0x14001c79d  jnz     short loc_14001C7A7
0x14001c79f  test    esi, esi
0x14001c7a1  jz      loc_14001C8D1
0x14001c7a7  cmp     r15d, eax
0x14001c7aa  jnb     loc_14001CA4E
0x14001c7b0  mov     eax, [rdx+8]
0x14001c7b3  add     eax, 1Ch
0x14001c7b6  imul    eax, r12d
0x14001c7ba  shl     eax, 3
0x14001c7bd  movups  xmm6, xmmword ptr [rax+rdx+0A8h]
0x14001c7c5  mov     edi, [rax+rdx+0C8h]
0x14001c7cc  movups  xmm7, xmmword ptr [rax+rdx+0B8h]
0x14001c7d4  lea     rax, [r14+830h]
0x14001c7db  mov     [rbp+57h+var_98], 0
0x14001c7e1  mov     rcx, rax; SpinLock
0x14001c7e4  mov     [rbp+57h+var_B8], rax
0x14001c7e8  lea     rdx, [rbp+57h+var_B0]; LockHandle
0x14001c7ec  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001c7f3  nop     dword ptr [rax+rax+00h]
0x14001c7f8  mov     byte ptr [rbp+57h+var_98], 1
0x14001c7fc  lea     rax, [rsp+130h+var_E8]
0x14001c801  mov     [rsp+130h+var_F0], r14
0x14001c806  xorps   xmm0, xmm0
0x14001c809  movups  [rsp+130h+var_E8], xmm0
0x14001c80e  mov     qword ptr [rsp+130h+var_E8+8], rax
0x14001c813  lea     rax, [rsp+130h+var_E8]
0x14001c818  mov     qword ptr [rsp+130h+var_E8], rax
0x14001c81d  mov     [rsp+130h+var_D8], 0
0x14001c822  mov     [rbp+57h+var_D4], 2
0x14001c829  mov     eax, r15d
0x14001c82c  imul    rcx, rax, 130h
0x14001c833  mov     rax, [rbp+57h+var_D0]
0x14001c837  movups  xmmword ptr [rcx+rax+98h], xmm6
0x14001c83f  movups  xmmword ptr [rcx+rax+0A8h], xmm7
0x14001c847  mov     [rcx+rax+0B8h], edi
0x14001c84e  mov     rax, [rbp+57h+var_C8]
0x14001c852  mov     rax, [rax]
0x14001c855  movsxd  rdx, dword ptr [rcx+rax+0BCh]
0x14001c85d  cmp     edx, 0FFFFFFFFh
0x14001c860  jle     short loc_14001C877
0x14001c862  lea     rdx, [rdx+rdx*4]
0x14001c866  shl     rdx, 5
0x14001c86a  add     rdx, [r14+0E48h]
0x14001c871  jnz     loc_14001CA09
0x14001c877  lea     rcx, [rsp+130h+var_F0]; this
0x14001c87c  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x14001c881  cmp     byte ptr [rbp+57h+var_98], 0
0x14001c885  jz      short loc_14001C8A1
0x14001c887  cmp     byte ptr [rbp+57h+var_98+1], 0
0x14001c88b  lea     rcx, [rbp+57h+var_B0]; LockHandle
0x14001c88f  jnz     loc_14001C9F8
0x14001c895  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001c89c  nop     dword ptr [rax+rax+00h]
0x14001c8a1  mov     rdx, [rbp+57h+var_C0]
0x14001c8a5  mov     ecx, r15d
0x14001c8a8  mov     eax, 1
0x14001c8ad  xor     r8d, r8d
0x14001c8b0  shl     eax, cl
0x14001c8b2  mov     ecx, 0FFFFFFFFh
0x14001c8b7  not     eax
0x14001c8b9  and     ebx, eax
0x14001c8bb  bsf     eax, ebx
0x14001c8be  cmovnz  ecx, eax
0x14001c8c1  mov     eax, [rsp+130h+var_100]
0x14001c8c5  movsx   r15d, cl
0x14001c8c9  inc     r12d
0x14001c8cc  jmp     loc_14001C79B
0x14001c8d1  movaps  xmm6, [rsp+130h+var_40]
0x14001c8d9  movaps  xmm7, [rsp+130h+var_50]
0x14001c8e1  mov     rcx, [rbp+57h+var_58]
0x14001c8e5  xor     rcx, rsp; StackCookie
0x14001c8e8  call    __security_check_cookie
0x14001c8ed  mov     rbx, [rsp+130h+arg_10]
0x14001c8f5  add     rsp, 100h
0x14001c8fc  pop     r15
0x14001c8fe  pop     r14
0x14001c900  pop     r13
0x14001c902  pop     r12
0x14001c904  pop     rdi
0x14001c905  pop     rsi
0x14001c906  pop     rbp
0x14001c907  retn
0x14001c909  mov     r8d, 10h; Length
0x14001c90f  lea     rdx, [rbp+57h+Source2]; Source2
0x14001c913  lea     rcx, [r12+0C84h]; Source1
0x14001c91b  call    cs:__imp_RtlCompareMemory
0x14001c922  nop     dword ptr [rax+rax+00h]
0x14001c927  cmp     rax, 10h
0x14001c92b  jnz     short loc_14001C952
0x14001c92d  mov     r8, rax; Length
0x14001c930  lea     rdx, [rbp+57h+var_68]; Source2
0x14001c934  lea     rcx, [r12+0C94h]; Source1
0x14001c93c  call    cs:__imp_RtlCompareMemory
0x14001c943  nop     dword ptr [rax+rax+00h]
0x14001c948  cmp     rax, 10h
0x14001c94c  jz      loc_14001C717
0x14001c952  movups  xmm0, [rbp+57h+Source2]
0x14001c956  movups  xmmword ptr [r12+0C84h], xmm0
0x14001c95f  movups  xmm1, [rbp+57h+var_68]
0x14001c963  movups  xmmword ptr [r12+0C94h], xmm1
0x14001c96c  mov     r9d, [r14+0A0h]
0x14001c973  xor     edx, edx
0x14001c975  cmp     edx, r9d
0x14001c978  jnb     loc_14001C720
0x14001c97e  mov     eax, edx
0x14001c980  imul    rcx, rax, 130h
0x14001c987  mov     rax, [r14+r15*8+0DC8h]
0x14001c98f  movsxd  r8, dword ptr [rcx+rax+0BCh]
0x14001c997  cmp     r8d, 0FFFFFFFFh
0x14001c99b  jle     loc_14001CA72
0x14001c9a1  mov     rax, [r14+0E48h]
0x14001c9a8  lea     rcx, [r8+r8*4]
0x14001c9ac  shl     rcx, 5
0x14001c9b0  cmp     dword ptr [rcx+rax+70h], 2
0x14001c9b5  jnz     loc_14001CA72
0x14001c9bb  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14001c9c2  mov     dword ptr [rax], 1
0x14001c9c8  mov     [rsp+130h+var_108], r14
0x14001c9cd  xor     r9d, r9d
0x14001c9d0  mov     edx, 119h
0x14001c9d5  mov     [rsp+130h+var_110], r15
0x14001c9da  xor     ecx, ecx
0x14001c9dc  mov     r8d, 100000h
0x14001c9e2  call    cs:__imp_WdLogSingleEntry5
0x14001c9e9  nop     dword ptr [rax+rax+00h]
0x14001c9ee  mov     cs:WdLogGlobalForLineNumber, 399h
0x14001c9f8  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001c9ff  nop     dword ptr [rax+rax+00h]
0x14001ca04  jmp     loc_14001C8A1
0x14001ca09  cmp     dword ptr [rdx+70h], 1
0x14001ca0d  jnz     loc_14001C877
0x14001ca13  mov     r10d, [rsp+130h+var_FC]
0x14001ca18  mov     r8d, r15d; unsigned int
0x14001ca1b  mov     byte ptr [rdx+60h], 1
0x14001ca1f  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x14001ca22  mov     [rdx+6Ch], r13b
0x14001ca26  mov     edx, r10d; unsigned int
0x14001ca29  call    ?VidSchiCheckPlaneIndependentFlipCondition@@YA_NPEAU_VIDSCH_GLOBAL@@II@Z; VidSchiCheckPlaneIndependentFlipCondition(_VIDSCH_GLOBAL *,uint,uint)
0x14001ca2e  test    al, al
0x14001ca30  jz      loc_14001C877
0x14001ca36  mov     r9d, r15d
0x14001ca39  lea     rcx, [rsp+130h+var_F0]; struct HwQueueStagingList *
0x14001ca3e  mov     r8d, r10d
0x14001ca41  mov     rdx, r14; struct _VIDSCH_GLOBAL *
0x14001ca44  call    VidSchiFlushPendingTokenList
0x14001ca49  jmp     loc_14001C877
0x14001ca4e  mov     ecx, eax
0x14001ca50  mov     eax, 1
0x14001ca55  shl     eax, cl
0x14001ca57  mov     ecx, 0FFFFFFFFh
0x14001ca5c  not     eax
0x14001ca5e  and     esi, eax
0x14001ca60  bsf     eax, esi
0x14001ca63  cmovnz  ecx, eax
0x14001ca66  movsx   eax, cl
0x14001ca69  mov     [rsp+130h+var_100], eax
0x14001ca6d  jmp     loc_14001C8C9
0x14001ca72  inc     edx
0x14001ca74  jmp     loc_14001C975
```
