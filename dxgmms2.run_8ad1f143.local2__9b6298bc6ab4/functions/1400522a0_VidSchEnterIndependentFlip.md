# VidSchEnterIndependentFlip

- ea: `0x1400522a0`
- end: `0x1400526d9`
- name: `VidSchEnterIndependentFlip`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140037ee8`
- `0x14003c1d4`
- `0x1400522a0`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052316`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052316`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005261e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005261e`
- `ntoskrnl!RtlCopyLuid` at `0x1400522f2`
- `ntoskrnl!RtlCopyLuid` at `0x1400522f2`
- `watchdog!WdLogSingleEntry3` at `0x140052509`
- `watchdog!WdLogSingleEntry3` at `0x140052509`
- `watchdog!WdLogSingleEntry5` at `0x1400523ea`
- `watchdog!WdLogSingleEntry5` at `0x14005247c`
- `watchdog!WdLogSingleEntry5` at `0x1400523ea`
- `watchdog!WdLogSingleEntry5` at `0x14005247c`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400523c0`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14005244a`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
_UNKNOWN **__fastcall VidSchEnterIndependentFlip(
        __int64 a1,
        unsigned int a2,
        struct _LUID *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        _QWORD *a8)
{
  _UNKNOWN **result; // rax
  _QWORD *v9; // r12
  int v12; // r11d
  int v13; // r10d
  __int64 v14; // r9
  char v15; // r15
  __int64 v16; // rbx
  __int64 v17; // r14
  unsigned int i; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r14d
  __int64 v23; // r12
  __int64 v24; // r15
  __int64 v25; // r8
  __int64 v26; // r13
  __int64 v27; // rdi
  __int64 v28; // r14
  unsigned int v29; // r10d
  unsigned int v30; // r11d
  unsigned int v31; // r9d
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rcx
  bool v35; // zf
  int v36; // edx
  int v37; // r8d
  __int64 v38; // r14
  unsigned int v39; // edi
  char v40; // si
  unsigned int v41; // ebx
  struct _LUID DestinationLuid; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v44; // [rsp+74h] [rbp-2Dh]
  unsigned int v45; // [rsp+78h] [rbp-29h]
  __int64 v46; // [rsp+80h] [rbp-21h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+E0h] [rbp+3Fh] BYREF

  result = &retaddr;
  v9 = a8;
  *a7 = 0;
  *a8 = 0;
  if ( *(_BYTE *)(a1 + 55) )
  {
    DestinationLuid = 0;
    RtlCopyLuid(&DestinationLuid, a3);
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 2096), &LockHandle);
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    for ( i = a2; i; i >>= 1 )
    {
      if ( (i & 1) != 0 )
        break;
      v14 = (unsigned int)(v14 + 1);
    }
    while ( i )
    {
      v19 = *(int *)(304LL * *(unsigned int *)(a5 + 4 * v17) + *(_QWORD *)(a1 + 8 * v14 + 3528) + 188);
      if ( (int)v19 <= -1 )
      {
        v20 = 0;
        v16 = 0;
      }
      else
      {
        v16 = *(_QWORD *)(a1 + 3656) + 160 * v19;
        v20 = v16;
        if ( v16 )
          v15 = 1;
      }
      if ( !v20 )
        ++v13;
      v21 = v12 + 1;
      if ( !v20 )
        v21 = v12;
      v12 = v21;
      while ( 1 )
      {
        i >>= 1;
        if ( !i || (i & 1) != 0 )
          break;
        v14 = (unsigned int)(v14 + 1);
      }
      v17 = (unsigned int)(v17 + 1);
    }
    if ( v13 && v12 )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 0x8000);
      WdLogGlobalForLineNumber = 921;
    }
    v22 = 0;
    if ( !v15 )
    {
      while ( v22 < *(_DWORD *)(a1 + 3824) )
      {
        if ( !*(_QWORD *)(*(_QWORD *)(a1 + 3656) + 160LL * v22) )
        {
          v16 = *(_QWORD *)(a1 + 3656) + 160LL * v22;
          if ( v22 > *(_DWORD *)(a1 + 3840) )
            *(_DWORD *)(a1 + 3840) = v22;
          break;
        }
        ++v22;
      }
    }
    if ( !v16 )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 0x2000);
      WdLogGlobalForLineNumber = 921;
    }
    if ( v15 )
    {
      v26 = a4;
    }
    else
    {
      *(_DWORD *)(v16 + 16) = a2;
      memset((void *)(v16 + 20), 0, 0x40u);
      v23 = 0;
      v24 = 0;
      if ( a2 )
      {
        do
        {
          if ( (a2 & 1) != 0 )
            break;
          v24 = (unsigned int)(v24 + 1);
          a2 >>= 1;
        }
        while ( a2 );
        while ( a2 )
        {
          *(_DWORD *)(v16 + 4 * v23 + 20) = *(_DWORD *)(a5 + 4 * v23);
          v25 = (unsigned int)v23;
          v23 = (unsigned int)(v23 + 1);
          *(_DWORD *)(*(_QWORD *)(a1 + 8 * v24 + 3528) + 304LL * *(unsigned int *)(a5 + 4 * v25) + 188) = v22;
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry3)(
            8,
            *a3,
            a4,
            *(unsigned int *)(a5 + 4 * v25));
          WdLogGlobalForLineNumber = 13748;
          while ( 1 )
          {
            a2 >>= 1;
            if ( !a2 || (a2 & 1) != 0 )
              break;
            v24 = (unsigned int)(v24 + 1);
          }
        }
      }
      v26 = a4;
      v9 = a8;
      *(_QWORD *)(v16 + 112) = 1;
      *(struct _LUID *)v16 = DestinationLuid;
      *(_QWORD *)(v16 + 8) = a4;
      *(_WORD *)(v16 + 96) = 0;
      *(_BYTE *)(v16 + 98) = 0;
    }
    *(_DWORD *)(v16 + 100) = a6;
    v27 = *(_QWORD *)(a1 + 3832);
    *(_QWORD *)(v16 + 88) = v27;
    VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(
      (VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR *)&v43,
      (struct _VIDSCH_INDEPENDENT_FLIP_STATE *)v16);
    v28 = v46;
    v29 = v45;
    v30 = v44;
    v31 = v43;
    while ( v31 )
    {
      v32 = 304LL * *(unsigned int *)(v28 + 4LL * v29) + 152 + *(_QWORD *)(a1 + 8LL * v30 + 3528);
      v33 = *(_QWORD *)(v16 + 88);
      v34 = 5LL * *(unsigned int *)(v32 + 216);
      *(_QWORD *)(v32 + 8 * v34 + 88) = MEMORY[0xFFFFF78000000320];
      *(_WORD *)(v32 + 8 * v34 + 56) = 257;
      *(struct _LUID *)(v32 + 8 * v34 + 60) = DestinationLuid;
      *(_QWORD *)(v32 + 8 * v34 + 72) = v26;
      *(_QWORD *)(v32 + 8 * v34 + 80) = v33;
      *(_DWORD *)(v32 + 216) = ((unsigned __int8)*(_DWORD *)(v32 + 216) + 1) & 3;
      while ( 1 )
      {
        v31 >>= 1;
        if ( !v31 || (v31 & 1) != 0 )
          break;
        ++v30;
      }
      ++v29;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v35 = bTracingEnabled == 0;
    *v9 = v27;
    if ( !v35 )
    {
      VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(
        (VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR *)&v43,
        (struct _VIDSCH_INDEPENDENT_FLIP_STATE *)v16);
      v38 = v46;
      v39 = v45;
      v40 = v44;
      v41 = v43;
      while ( v41 )
      {
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0txqqqtxtx_EtwWriteTransfer(
            v39,
            v36,
            v37,
            1,
            DestinationLuid.LowPart,
            v40,
            *(_DWORD *)(v38 + 4LL * v39),
            a6,
            0,
            v26,
            1,
            *v9);
        while ( 1 )
        {
          v41 >>= 1;
          if ( !v41 || (v41 & 1) != 0 )
            break;
          ++v40;
        }
        ++v39;
      }
    }
    result = (_UNKNOWN **)a7;
    *a7 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1400522a0  mov     rax, rsp
0x1400522a3  mov     [rax+10h], rbx
0x1400522a7  mov     [rax+20h], r9
0x1400522ab  mov     [rax+18h], r8
0x1400522af  push    rbp
0x1400522b0  push    rsi
0x1400522b1  push    rdi
0x1400522b2  push    r12
0x1400522b4  push    r13
0x1400522b6  push    r14
0x1400522b8  push    r15
0x1400522ba  lea     rbp, [rax-3Fh]
0x1400522be  sub     rsp, 0A0h
0x1400522c5  mov     r12, [rbp+37h+arg_38]
0x1400522c9  mov     rsi, rcx
0x1400522cc  mov     rcx, [rbp+37h+arg_30]
0x1400522d0  mov     edi, edx
0x1400522d2  xor     edx, edx
0x1400522d4  mov     [rcx], edx
0x1400522d6  mov     [r12], rdx
0x1400522da  cmp     [rsi+37h], dl
0x1400522dd  jz      loc_1400526BD
0x1400522e3  mov     r13, [rbp+37h+arg_20]
0x1400522e7  lea     rcx, [rbp+37h+DestinationLuid]; DestinationLuid
0x1400522eb  mov     qword ptr [rbp+37h+DestinationLuid.LowPart], rdx
0x1400522ef  mov     rdx, r8; SourceLuid
0x1400522f2  call    cs:__imp_RtlCopyLuid
0x1400522f9  nop     dword ptr [rax+rax+00h]
0x1400522fe  xorps   xmm0, xmm0
0x140052301  lea     rcx, [rsi+830h]; SpinLock
0x140052308  xor     eax, eax
0x14005230a  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005230e  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140052312  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140052316  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005231d  nop     dword ptr [rax+rax+00h]
0x140052322  xor     r11d, r11d
0x140052325  xor     r10d, r10d
0x140052328  xor     r9d, r9d
0x14005232b  xor     r15b, r15b
0x14005232e  xor     ebx, ebx
0x140052330  xor     r14d, r14d
0x140052333  mov     r8d, edi
0x140052336  test    edi, edi
0x140052338  jz      short loc_140052348
0x14005233a  test    r8b, 1
0x14005233e  jnz     short loc_140052348
0x140052340  inc     r9d
0x140052343  shr     r8d, 1
0x140052346  jnz     short loc_14005233A
0x140052348  test    r8d, r8d
0x14005234b  jz      short loc_1400523B6
0x14005234d  mov     ecx, [r13+r14*4+0]
0x140052352  imul    rdx, rcx, 130h
0x140052359  mov     rcx, [rsi+r9*8+0DC8h]
0x140052361  movsxd  rax, dword ptr [rdx+rcx+0BCh]
0x140052369  cmp     eax, 0FFFFFFFFh
0x14005236c  jle     short loc_140052387
0x14005236e  lea     rbx, [rax+rax*4]
0x140052372  shl     rbx, 5
0x140052376  add     rbx, [rsi+0E48h]
0x14005237d  mov     rcx, rbx
0x140052380  jz      short loc_14005238B
0x140052382  mov     r15b, 1
0x140052385  jmp     short loc_14005238B
0x140052387  xor     ecx, ecx
0x140052389  xor     ebx, ebx
0x14005238b  test    rcx, rcx
0x14005238e  lea     eax, [r10+1]
0x140052392  cmovz   r10d, eax
0x140052396  lea     eax, [r11+1]
0x14005239a  cmovz   eax, r11d
0x14005239e  mov     r11d, eax
0x1400523a1  jmp     short loc_1400523AC
0x1400523a3  test    r8b, 1
0x1400523a7  jnz     short loc_1400523B1
0x1400523a9  inc     r9d
0x1400523ac  shr     r8d, 1
0x1400523af  jnz     short loc_1400523A3
0x1400523b1  inc     r14d
0x1400523b4  jmp     short loc_140052348
0x1400523b6  test    r10d, r10d
0x1400523b9  jz      short loc_140052400
0x1400523bb  test    r11d, r11d
0x1400523be  jz      short loc_140052400
0x1400523c0  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400523c7  mov     dword ptr [rax], 1
0x1400523cd  mov     eax, r10d
0x1400523d0  mov     edx, 119h
0x1400523d5  mov     r9d, r11d
0x1400523d8  xor     ecx, ecx
0x1400523da  mov     qword ptr [rsp+0D0h+var_A8], rsi
0x1400523df  mov     r8d, 8000h
0x1400523e5  mov     [rsp+0D0h+var_B0], rax
0x1400523ea  call    cs:__imp_WdLogSingleEntry5
0x1400523f1  nop     dword ptr [rax+rax+00h]
0x1400523f6  mov     cs:WdLogGlobalForLineNumber, 399h
0x140052400  xor     r14d, r14d
0x140052403  test    r15b, r15b
0x140052406  jnz     short loc_140052445
0x140052408  mov     r8d, [rsi+0EF0h]
0x14005240f  cmp     r14d, r8d
0x140052412  jge     short loc_140052445
0x140052414  movsxd  rax, r14d
0x140052417  lea     rdx, [rax+rax*4]
0x14005241b  shl     rdx, 5
0x14005241f  add     rdx, [rsi+0E48h]
0x140052426  mov     eax, [rdx+4]
0x140052429  or      eax, [rdx]
0x14005242b  jz      short loc_140052432
0x14005242d  inc     r14d
0x140052430  jmp     short loc_14005240F
0x140052432  mov     rbx, rdx
0x140052435  cmp     r14d, [rsi+0F00h]
0x14005243c  jle     short loc_140052445
0x14005243e  mov     [rsi+0F00h], r14d
0x140052445  test    rbx, rbx
0x140052448  jnz     short loc_140052492
0x14005244a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140052451  movsxd  rcx, dword ptr [rsi+0F00h]
0x140052458  mov     r9d, [rsi+0EF0h]
0x14005245f  mov     dword ptr [rax], 1
0x140052465  mov     qword ptr [rsp+0D0h+var_A8], rsi
0x14005246a  mov     edx, 119h
0x14005246f  mov     [rsp+0D0h+var_B0], rcx
0x140052474  mov     r8d, 2000h
0x14005247a  xor     ecx, ecx
0x14005247c  call    cs:__imp_WdLogSingleEntry5
0x140052483  nop     dword ptr [rax+rax+00h]
0x140052488  mov     cs:WdLogGlobalForLineNumber, 399h
0x140052492  test    r15b, r15b
0x140052495  jnz     loc_140052557
0x14005249b  xor     edx, edx; Val
0x14005249d  mov     [rbx+10h], edi
0x1400524a0  lea     rcx, [rbx+14h]; void *
0x1400524a4  lea     r8d, [rdx+40h]; Size
0x1400524a8  call    memset
0x1400524ad  xor     r12d, r12d
0x1400524b0  xor     r15d, r15d
0x1400524b3  test    edi, edi
0x1400524b5  jz      short loc_140052530
0x1400524b7  test    dil, 1
0x1400524bb  jnz     short loc_1400524C4
0x1400524bd  inc     r15d
0x1400524c0  shr     edi, 1
0x1400524c2  jnz     short loc_1400524B7
0x1400524c4  test    edi, edi
0x1400524c6  jz      short loc_140052530
0x1400524c8  mov     eax, [r13+r12*4+0]
0x1400524cd  mov     [rbx+r12*4+14h], eax
0x1400524d2  mov     r8d, r12d
0x1400524d5  inc     r12d
0x1400524d8  mov     eax, [r13+r8*4+0]
0x1400524dd  imul    rcx, rax, 130h
0x1400524e4  mov     rax, [rsi+r15*8+0DC8h]
0x1400524ec  mov     [rax+rcx+0BCh], r14d
0x1400524f4  mov     rax, [rbp+37h+arg_10]
0x1400524f8  mov     ecx, 8
0x1400524fd  mov     r9d, [r13+r8*4+0]
0x140052502  mov     r8, [rbp+37h+arg_18]
0x140052506  mov     rdx, [rax]
0x140052509  call    cs:__imp_WdLogSingleEntry3
0x140052510  nop     dword ptr [rax+rax+00h]
0x140052515  mov     cs:WdLogGlobalForLineNumber, 35B4h
0x14005251f  jmp     short loc_14005252A
0x140052521  test    dil, 1
0x140052525  jnz     short loc_1400524C4
0x140052527  inc     r15d
0x14005252a  shr     edi, 1
0x14005252c  jnz     short loc_140052521
0x14005252e  jmp     short loc_1400524C4
0x140052530  mov     r13, [rbp+37h+arg_18]
0x140052534  mov     r12, [rbp+37h+arg_38]
0x140052538  mov     qword ptr [rbx+70h], 1
0x140052540  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x140052544  mov     [rbx], rax
0x140052547  mov     [rbx+8], r13
0x14005254b  mov     word ptr [rbx+60h], 0
0x140052551  mov     byte ptr [rbx+62h], 0
0x140052555  jmp     short loc_14005255B
0x140052557  mov     r13, [rbp+37h+arg_18]
0x14005255b  mov     r15d, [rbp+37h+arg_28]
0x14005255f  lea     rcx, [rbp+37h+var_68]; this
0x140052563  mov     [rbx+64h], r15d
0x140052567  mov     rdx, rbx; struct _VIDSCH_INDEPENDENT_FLIP_STATE *
0x14005256a  mov     rdi, [rsi+0EF8h]
0x140052571  mov     [rbx+58h], rdi
0x140052575  call    ??0VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR@@QEAA@PEAU_VIDSCH_INDEPENDENT_FLIP_STATE@@@Z; VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(_VIDSCH_INDEPENDENT_FLIP_STATE *)
0x14005257a  mov     r14, [rbp+37h+var_58]
0x14005257e  mov     r10d, [rbp+37h+var_60]
0x140052582  mov     r11d, [rbp+37h+var_64]
0x140052586  mov     r9d, [rbp+37h+var_68]
0x14005258a  test    r9d, r9d
0x14005258d  jz      loc_14005261A
0x140052593  mov     eax, r10d
0x140052596  mov     ecx, [r14+rax*4]
0x14005259a  imul    rdx, rcx, 130h
0x1400525a1  mov     eax, r11d
0x1400525a4  add     rdx, 98h
0x1400525ab  mov     r8, [rsi+rax*8+0DC8h]
0x1400525b3  add     r8, rdx
0x1400525b6  mov     rdx, [rbx+58h]
0x1400525ba  mov     eax, [r8+0D8h]
0x1400525c1  lea     rcx, [rax+rax*4]
0x1400525c5  mov     rax, ds:0FFFFF78000000320h
0x1400525cf  mov     [r8+rcx*8+58h], rax
0x1400525d4  mov     word ptr [r8+rcx*8+38h], 101h
0x1400525dc  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x1400525e0  mov     [r8+rcx*8+3Ch], rax
0x1400525e5  mov     [r8+rcx*8+48h], r13
0x1400525ea  mov     [r8+rcx*8+50h], rdx
0x1400525ef  mov     eax, [r8+0D8h]
0x1400525f6  inc     eax
0x1400525f8  and     eax, 3
0x1400525fb  mov     [r8+0D8h], eax
0x140052602  jmp     short loc_14005260D
0x140052604  test    r9b, 1
0x140052608  jnz     short loc_140052612
0x14005260a  inc     r11d
0x14005260d  shr     r9d, 1
0x140052610  jnz     short loc_140052604
0x140052612  inc     r10d
0x140052615  jmp     loc_14005258A
0x14005261a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005261e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052625  nop     dword ptr [rax+rax+00h]
0x14005262a  cmp     cs:bTracingEnabled, 0
0x140052631  mov     [r12], rdi
0x140052635  jz      short loc_1400526B3
0x140052637  mov     rdx, rbx; struct _VIDSCH_INDEPENDENT_FLIP_STATE *
0x14005263a  lea     rcx, [rbp+37h+var_68]; this
0x14005263e  call    ??0VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR@@QEAA@PEAU_VIDSCH_INDEPENDENT_FLIP_STATE@@@Z; VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(_VIDSCH_INDEPENDENT_FLIP_STATE *)
0x140052643  mov     r14, [rbp+37h+var_58]
0x140052647  mov     edi, [rbp+37h+var_60]
0x14005264a  mov     esi, [rbp+37h+var_64]
0x14005264d  mov     ebx, [rbp+37h+var_68]
0x140052650  test    ebx, ebx
0x140052652  jz      short loc_1400526B3
0x140052654  test    cs:byte_140086201, 1
0x14005265b  jz      short loc_1400526AB
0x14005265d  mov     rax, [r12]
0x140052661  mov     r9d, 1
0x140052667  mov     [rsp+58h], rax
0x14005266c  mov     dword ptr [rsp+0D0h+var_80], 1
0x140052674  mov     qword ptr [rsp+0D0h+var_88], r13
0x140052679  mov     dword ptr [rsp+0D0h+var_90], 0
0x140052681  mov     [rsp+0D0h+var_98], r15d
0x140052686  mov     ecx, edi
0x140052688  mov     eax, [r14+rcx*4]
0x14005268c  mov     [rsp+0D0h+var_A0], eax
0x140052690  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x140052694  mov     [rsp+0D0h+var_A8], esi
0x140052698  mov     [rsp+0D0h+var_B0], rax
0x14005269d  call    McTemplateK0txqqqtxtx_EtwWriteTransfer
0x1400526a2  jmp     short loc_1400526AB
0x1400526a4  test    bl, 1
0x1400526a7  jnz     short loc_1400526AF
0x1400526a9  inc     esi
0x1400526ab  shr     ebx, 1
0x1400526ad  jnz     short loc_1400526A4
0x1400526af  inc     edi
0x1400526b1  jmp     short loc_140052650
0x1400526b3  mov     rax, [rbp+37h+arg_30]
0x1400526b7  mov     dword ptr [rax], 1
0x1400526bd  mov     rbx, [rsp+0D0h+arg_8]
0x1400526c5  add     rsp, 0A0h
0x1400526cc  pop     r15
0x1400526ce  pop     r14
0x1400526d0  pop     r13
0x1400526d2  pop     r12
0x1400526d4  pop     rdi
0x1400526d5  pop     rsi
0x1400526d6  pop     rbp
0x1400526d7  retn
```
