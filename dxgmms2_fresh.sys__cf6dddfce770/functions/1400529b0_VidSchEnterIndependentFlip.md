# VidSchEnterIndependentFlip

- ea: `0x1400529b0`
- end: `0x140052de9`
- name: `VidSchEnterIndependentFlip`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140036f48`
- `0x14003aee4`
- `0x1400529b0`
- `0x140059380`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052a26`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052a26`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052d2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052d2e`
- `ntoskrnl!RtlCopyLuid` at `0x140052a02`
- `ntoskrnl!RtlCopyLuid` at `0x140052a02`
- `watchdog!WdLogSingleEntry3` at `0x140052c19`
- `watchdog!WdLogSingleEntry3` at `0x140052c19`
- `watchdog!WdLogSingleEntry5` at `0x140052afa`
- `watchdog!WdLogSingleEntry5` at `0x140052b8c`
- `watchdog!WdLogSingleEntry5` at `0x140052afa`
- `watchdog!WdLogSingleEntry5` at `0x140052b8c`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140052ad0`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140052b5a`

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
  unsigned int v12; // r11d
  unsigned int v13; // r10d
  __int64 v14; // r9
  char v15; // r15
  __int64 v16; // rbx
  __int64 v17; // r14
  unsigned int i; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // eax
  int v22; // r14d
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // r12
  __int64 v26; // r15
  __int64 v27; // r8
  __int64 v28; // r13
  __int64 v29; // rdi
  __int64 v30; // r14
  unsigned int v31; // r10d
  unsigned int v32; // r11d
  unsigned int v33; // r9d
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  bool v37; // zf
  int v38; // edx
  int v39; // r8d
  __int64 v40; // r14
  unsigned int v41; // edi
  char v42; // si
  unsigned int v43; // ebx
  struct _LUID DestinationLuid; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v46; // [rsp+74h] [rbp-2Dh]
  unsigned int v47; // [rsp+78h] [rbp-29h]
  __int64 v48; // [rsp+80h] [rbp-21h]
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
      WdLogSingleEntry5(0, 281, 0x8000, v12, v13, a1);
      WdLogGlobalForLineNumber = 926;
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
      v23 = *(int *)(a1 + 3840);
      v24 = *(unsigned int *)(a1 + 3824);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 0x2000, v24, v23, a1);
      WdLogGlobalForLineNumber = 926;
    }
    if ( v15 )
    {
      v28 = a4;
    }
    else
    {
      *(_DWORD *)(v16 + 16) = a2;
      memset((void *)(v16 + 20), 0, 0x40u);
      v25 = 0;
      v26 = 0;
      if ( a2 )
      {
        do
        {
          if ( (a2 & 1) != 0 )
            break;
          v26 = (unsigned int)(v26 + 1);
          a2 >>= 1;
        }
        while ( a2 );
        while ( a2 )
        {
          *(_DWORD *)(v16 + 4 * v25 + 20) = *(_DWORD *)(a5 + 4 * v25);
          v27 = (unsigned int)v25;
          v25 = (unsigned int)(v25 + 1);
          *(_DWORD *)(*(_QWORD *)(a1 + 8 * v26 + 3528) + 304LL * *(unsigned int *)(a5 + 4 * v27) + 188) = v22;
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry3)(
            8,
            *a3,
            a4,
            *(unsigned int *)(a5 + 4 * v27));
          WdLogGlobalForLineNumber = 13777;
          while ( 1 )
          {
            a2 >>= 1;
            if ( !a2 || (a2 & 1) != 0 )
              break;
            v26 = (unsigned int)(v26 + 1);
          }
        }
      }
      v28 = a4;
      v9 = a8;
      *(_QWORD *)(v16 + 112) = 1;
      *(struct _LUID *)v16 = DestinationLuid;
      *(_QWORD *)(v16 + 8) = a4;
      *(_WORD *)(v16 + 96) = 0;
      *(_BYTE *)(v16 + 98) = 0;
    }
    *(_DWORD *)(v16 + 100) = a6;
    v29 = *(_QWORD *)(a1 + 3832);
    *(_QWORD *)(v16 + 88) = v29;
    VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(
      (VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR *)&v45,
      (struct _VIDSCH_INDEPENDENT_FLIP_STATE *)v16);
    v30 = v48;
    v31 = v47;
    v32 = v46;
    v33 = v45;
    while ( v33 )
    {
      v34 = 304LL * *(unsigned int *)(v30 + 4LL * v31) + 152 + *(_QWORD *)(a1 + 8LL * v32 + 3528);
      v35 = *(_QWORD *)(v16 + 88);
      v36 = 5LL * *(unsigned int *)(v34 + 216);
      *(_QWORD *)(v34 + 8 * v36 + 88) = MEMORY[0xFFFFF78000000320];
      *(_WORD *)(v34 + 8 * v36 + 56) = 257;
      *(struct _LUID *)(v34 + 8 * v36 + 60) = DestinationLuid;
      *(_QWORD *)(v34 + 8 * v36 + 72) = v28;
      *(_QWORD *)(v34 + 8 * v36 + 80) = v35;
      *(_DWORD *)(v34 + 216) = ((unsigned __int8)*(_DWORD *)(v34 + 216) + 1) & 3;
      while ( 1 )
      {
        v33 >>= 1;
        if ( !v33 || (v33 & 1) != 0 )
          break;
        ++v32;
      }
      ++v31;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v37 = bTracingEnabled == 0;
    *v9 = v29;
    if ( !v37 )
    {
      VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(
        (VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR *)&v45,
        (struct _VIDSCH_INDEPENDENT_FLIP_STATE *)v16);
      v40 = v48;
      v41 = v47;
      v42 = v46;
      v43 = v45;
      while ( v43 )
      {
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0txqqqtxtx_EtwWriteTransfer(
            v41,
            v38,
            v39,
            1,
            DestinationLuid.LowPart,
            v42,
            *(_DWORD *)(v40 + 4LL * v41),
            a6,
            0,
            v28,
            1,
            *v9);
        while ( 1 )
        {
          v43 >>= 1;
          if ( !v43 || (v43 & 1) != 0 )
            break;
          ++v42;
        }
        ++v41;
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
0x1400529b0  mov     rax, rsp
0x1400529b3  mov     [rax+10h], rbx
0x1400529b7  mov     [rax+20h], r9
0x1400529bb  mov     [rax+18h], r8
0x1400529bf  push    rbp
0x1400529c0  push    rsi
0x1400529c1  push    rdi
0x1400529c2  push    r12
0x1400529c4  push    r13
0x1400529c6  push    r14
0x1400529c8  push    r15
0x1400529ca  lea     rbp, [rax-3Fh]
0x1400529ce  sub     rsp, 0A0h
0x1400529d5  mov     r12, [rbp+37h+arg_38]
0x1400529d9  mov     rsi, rcx
0x1400529dc  mov     rcx, [rbp+37h+arg_30]
0x1400529e0  mov     edi, edx
0x1400529e2  xor     edx, edx
0x1400529e4  mov     [rcx], edx
0x1400529e6  mov     [r12], rdx
0x1400529ea  cmp     [rsi+37h], dl
0x1400529ed  jz      loc_140052DCD
0x1400529f3  mov     r13, [rbp+37h+arg_20]
0x1400529f7  lea     rcx, [rbp+37h+DestinationLuid]; DestinationLuid
0x1400529fb  mov     qword ptr [rbp+37h+DestinationLuid.LowPart], rdx
0x1400529ff  mov     rdx, r8; SourceLuid
0x140052a02  call    cs:__imp_RtlCopyLuid
0x140052a09  nop     dword ptr [rax+rax+00h]
0x140052a0e  xorps   xmm0, xmm0
0x140052a11  lea     rcx, [rsi+830h]; SpinLock
0x140052a18  xor     eax, eax
0x140052a1a  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x140052a1e  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140052a22  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140052a26  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140052a2d  nop     dword ptr [rax+rax+00h]
0x140052a32  xor     r11d, r11d
0x140052a35  xor     r10d, r10d
0x140052a38  xor     r9d, r9d
0x140052a3b  xor     r15b, r15b
0x140052a3e  xor     ebx, ebx
0x140052a40  xor     r14d, r14d
0x140052a43  mov     r8d, edi
0x140052a46  test    edi, edi
0x140052a48  jz      short loc_140052A58
0x140052a4a  test    r8b, 1
0x140052a4e  jnz     short loc_140052A58
0x140052a50  inc     r9d
0x140052a53  shr     r8d, 1
0x140052a56  jnz     short loc_140052A4A
0x140052a58  test    r8d, r8d
0x140052a5b  jz      short loc_140052AC6
0x140052a5d  mov     ecx, [r13+r14*4+0]
0x140052a62  imul    rdx, rcx, 130h
0x140052a69  mov     rcx, [rsi+r9*8+0DC8h]
0x140052a71  movsxd  rax, dword ptr [rdx+rcx+0BCh]
0x140052a79  cmp     eax, 0FFFFFFFFh
0x140052a7c  jle     short loc_140052A97
0x140052a7e  lea     rbx, [rax+rax*4]
0x140052a82  shl     rbx, 5
0x140052a86  add     rbx, [rsi+0E48h]
0x140052a8d  mov     rcx, rbx
0x140052a90  jz      short loc_140052A9B
0x140052a92  mov     r15b, 1
0x140052a95  jmp     short loc_140052A9B
0x140052a97  xor     ecx, ecx
0x140052a99  xor     ebx, ebx
0x140052a9b  test    rcx, rcx
0x140052a9e  lea     eax, [r10+1]
0x140052aa2  cmovz   r10d, eax
0x140052aa6  lea     eax, [r11+1]
0x140052aaa  cmovz   eax, r11d
0x140052aae  mov     r11d, eax
0x140052ab1  jmp     short loc_140052ABC
0x140052ab3  test    r8b, 1
0x140052ab7  jnz     short loc_140052AC1
0x140052ab9  inc     r9d
0x140052abc  shr     r8d, 1
0x140052abf  jnz     short loc_140052AB3
0x140052ac1  inc     r14d
0x140052ac4  jmp     short loc_140052A58
0x140052ac6  test    r10d, r10d
0x140052ac9  jz      short loc_140052B10
0x140052acb  test    r11d, r11d
0x140052ace  jz      short loc_140052B10
0x140052ad0  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140052ad7  mov     dword ptr [rax], 1
0x140052add  mov     eax, r10d
0x140052ae0  mov     edx, 119h
0x140052ae5  mov     r9d, r11d
0x140052ae8  xor     ecx, ecx
0x140052aea  mov     qword ptr [rsp+0D0h+var_A8], rsi
0x140052aef  mov     r8d, 8000h
0x140052af5  mov     [rsp+0D0h+var_B0], rax
0x140052afa  call    cs:__imp_WdLogSingleEntry5
0x140052b01  nop     dword ptr [rax+rax+00h]
0x140052b06  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x140052b10  xor     r14d, r14d
0x140052b13  test    r15b, r15b
0x140052b16  jnz     short loc_140052B55
0x140052b18  mov     r8d, [rsi+0EF0h]
0x140052b1f  cmp     r14d, r8d
0x140052b22  jge     short loc_140052B55
0x140052b24  movsxd  rax, r14d
0x140052b27  lea     rdx, [rax+rax*4]
0x140052b2b  shl     rdx, 5
0x140052b2f  add     rdx, [rsi+0E48h]
0x140052b36  mov     eax, [rdx+4]
0x140052b39  or      eax, [rdx]
0x140052b3b  jz      short loc_140052B42
0x140052b3d  inc     r14d
0x140052b40  jmp     short loc_140052B1F
0x140052b42  mov     rbx, rdx
0x140052b45  cmp     r14d, [rsi+0F00h]
0x140052b4c  jle     short loc_140052B55
0x140052b4e  mov     [rsi+0F00h], r14d
0x140052b55  test    rbx, rbx
0x140052b58  jnz     short loc_140052BA2
0x140052b5a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140052b61  movsxd  rcx, dword ptr [rsi+0F00h]
0x140052b68  mov     r9d, [rsi+0EF0h]
0x140052b6f  mov     dword ptr [rax], 1
0x140052b75  mov     qword ptr [rsp+0D0h+var_A8], rsi
0x140052b7a  mov     edx, 119h
0x140052b7f  mov     [rsp+0D0h+var_B0], rcx
0x140052b84  mov     r8d, 2000h
0x140052b8a  xor     ecx, ecx
0x140052b8c  call    cs:__imp_WdLogSingleEntry5
0x140052b93  nop     dword ptr [rax+rax+00h]
0x140052b98  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x140052ba2  test    r15b, r15b
0x140052ba5  jnz     loc_140052C67
0x140052bab  xor     edx, edx; Val
0x140052bad  mov     [rbx+10h], edi
0x140052bb0  lea     rcx, [rbx+14h]; void *
0x140052bb4  lea     r8d, [rdx+40h]; Size
0x140052bb8  call    memset
0x140052bbd  xor     r12d, r12d
0x140052bc0  xor     r15d, r15d
0x140052bc3  test    edi, edi
0x140052bc5  jz      short loc_140052C40
0x140052bc7  test    dil, 1
0x140052bcb  jnz     short loc_140052BD4
0x140052bcd  inc     r15d
0x140052bd0  shr     edi, 1
0x140052bd2  jnz     short loc_140052BC7
0x140052bd4  test    edi, edi
0x140052bd6  jz      short loc_140052C40
0x140052bd8  mov     eax, [r13+r12*4+0]
0x140052bdd  mov     [rbx+r12*4+14h], eax
0x140052be2  mov     r8d, r12d
0x140052be5  inc     r12d
0x140052be8  mov     eax, [r13+r8*4+0]
0x140052bed  imul    rcx, rax, 130h
0x140052bf4  mov     rax, [rsi+r15*8+0DC8h]
0x140052bfc  mov     [rax+rcx+0BCh], r14d
0x140052c04  mov     rax, [rbp+37h+arg_10]
0x140052c08  mov     ecx, 8
0x140052c0d  mov     r9d, [r13+r8*4+0]
0x140052c12  mov     r8, [rbp+37h+arg_18]
0x140052c16  mov     rdx, [rax]
0x140052c19  call    cs:__imp_WdLogSingleEntry3
0x140052c20  nop     dword ptr [rax+rax+00h]
0x140052c25  mov     cs:WdLogGlobalForLineNumber, 35D1h
0x140052c2f  jmp     short loc_140052C3A
0x140052c31  test    dil, 1
0x140052c35  jnz     short loc_140052BD4
0x140052c37  inc     r15d
0x140052c3a  shr     edi, 1
0x140052c3c  jnz     short loc_140052C31
0x140052c3e  jmp     short loc_140052BD4
0x140052c40  mov     r13, [rbp+37h+arg_18]
0x140052c44  mov     r12, [rbp+37h+arg_38]
0x140052c48  mov     qword ptr [rbx+70h], 1
0x140052c50  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x140052c54  mov     [rbx], rax
0x140052c57  mov     [rbx+8], r13
0x140052c5b  mov     word ptr [rbx+60h], 0
0x140052c61  mov     byte ptr [rbx+62h], 0
0x140052c65  jmp     short loc_140052C6B
0x140052c67  mov     r13, [rbp+37h+arg_18]
0x140052c6b  mov     r15d, [rbp+37h+arg_28]
0x140052c6f  lea     rcx, [rbp+37h+var_68]; this
0x140052c73  mov     [rbx+64h], r15d
0x140052c77  mov     rdx, rbx; struct _VIDSCH_INDEPENDENT_FLIP_STATE *
0x140052c7a  mov     rdi, [rsi+0EF8h]
0x140052c81  mov     [rbx+58h], rdi
0x140052c85  call    ??0VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR@@QEAA@PEAU_VIDSCH_INDEPENDENT_FLIP_STATE@@@Z; VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(_VIDSCH_INDEPENDENT_FLIP_STATE *)
0x140052c8a  mov     r14, [rbp+37h+var_58]
0x140052c8e  mov     r10d, [rbp+37h+var_60]
0x140052c92  mov     r11d, [rbp+37h+var_64]
0x140052c96  mov     r9d, [rbp+37h+var_68]
0x140052c9a  test    r9d, r9d
0x140052c9d  jz      loc_140052D2A
0x140052ca3  mov     eax, r10d
0x140052ca6  mov     ecx, [r14+rax*4]
0x140052caa  imul    rdx, rcx, 130h
0x140052cb1  mov     eax, r11d
0x140052cb4  add     rdx, 98h
0x140052cbb  mov     r8, [rsi+rax*8+0DC8h]
0x140052cc3  add     r8, rdx
0x140052cc6  mov     rdx, [rbx+58h]
0x140052cca  mov     eax, [r8+0D8h]
0x140052cd1  lea     rcx, [rax+rax*4]
0x140052cd5  mov     rax, ds:0FFFFF78000000320h
0x140052cdf  mov     [r8+rcx*8+58h], rax
0x140052ce4  mov     word ptr [r8+rcx*8+38h], 101h
0x140052cec  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x140052cf0  mov     [r8+rcx*8+3Ch], rax
0x140052cf5  mov     [r8+rcx*8+48h], r13
0x140052cfa  mov     [r8+rcx*8+50h], rdx
0x140052cff  mov     eax, [r8+0D8h]
0x140052d06  inc     eax
0x140052d08  and     eax, 3
0x140052d0b  mov     [r8+0D8h], eax
0x140052d12  jmp     short loc_140052D1D
0x140052d14  test    r9b, 1
0x140052d18  jnz     short loc_140052D22
0x140052d1a  inc     r11d
0x140052d1d  shr     r9d, 1
0x140052d20  jnz     short loc_140052D14
0x140052d22  inc     r10d
0x140052d25  jmp     loc_140052C9A
0x140052d2a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x140052d2e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140052d35  nop     dword ptr [rax+rax+00h]
0x140052d3a  cmp     cs:bTracingEnabled, 0
0x140052d41  mov     [r12], rdi
0x140052d45  jz      short loc_140052DC3
0x140052d47  mov     rdx, rbx; struct _VIDSCH_INDEPENDENT_FLIP_STATE *
0x140052d4a  lea     rcx, [rbp+37h+var_68]; this
0x140052d4e  call    ??0VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR@@QEAA@PEAU_VIDSCH_INDEPENDENT_FLIP_STATE@@@Z; VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR::VIDSCH_INDEPENDENT_FLIP_VIDPNSOURCE_ITERATOR(_VIDSCH_INDEPENDENT_FLIP_STATE *)
0x140052d53  mov     r14, [rbp+37h+var_58]
0x140052d57  mov     edi, [rbp+37h+var_60]
0x140052d5a  mov     esi, [rbp+37h+var_64]
0x140052d5d  mov     ebx, [rbp+37h+var_68]
0x140052d60  test    ebx, ebx
0x140052d62  jz      short loc_140052DC3
0x140052d64  test    cs:byte_140087201, 1
0x140052d6b  jz      short loc_140052DBB
0x140052d6d  mov     rax, [r12]
0x140052d71  mov     r9d, 1
0x140052d77  mov     [rsp+58h], rax
0x140052d7c  mov     dword ptr [rsp+0D0h+var_80], 1
0x140052d84  mov     qword ptr [rsp+0D0h+var_88], r13
0x140052d89  mov     dword ptr [rsp+0D0h+var_90], 0
0x140052d91  mov     [rsp+0D0h+var_98], r15d
0x140052d96  mov     ecx, edi
0x140052d98  mov     eax, [r14+rcx*4]
0x140052d9c  mov     [rsp+0D0h+var_A0], eax
0x140052da0  mov     rax, qword ptr [rbp+37h+DestinationLuid.LowPart]
0x140052da4  mov     [rsp+0D0h+var_A8], esi
0x140052da8  mov     [rsp+0D0h+var_B0], rax
0x140052dad  call    McTemplateK0txqqqtxtx_EtwWriteTransfer
0x140052db2  jmp     short loc_140052DBB
0x140052db4  test    bl, 1
0x140052db7  jnz     short loc_140052DBF
0x140052db9  inc     esi
0x140052dbb  shr     ebx, 1
0x140052dbd  jnz     short loc_140052DB4
0x140052dbf  inc     edi
0x140052dc1  jmp     short loc_140052D60
0x140052dc3  mov     rax, [rbp+37h+arg_30]
0x140052dc7  mov     dword ptr [rax], 1
0x140052dcd  mov     rbx, [rsp+0D0h+arg_8]
0x140052dd5  add     rsp, 0A0h
0x140052ddc  pop     r15
0x140052dde  pop     r14
0x140052de0  pop     r13
0x140052de2  pop     r12
0x140052de4  pop     rdi
0x140052de5  pop     rsi
0x140052de6  pop     rbp
0x140052de7  retn
```
