# FlushCpuCache(CDDPDEV *,CddBitmapStagingApertureMem *,uint,tagRECT const *,uchar)

- ea: `0x14002fbd4`
- end: `0x14002fe65`
- name: `?FlushCpuCache@@YAXPEAUCDDPDEV@@PEAVCddBitmapStagingApertureMem@@IPEBUtagRECT@@E@Z`
- size: `657`
- prototype: `void __usercall(struct CDDPDEV *@<rcx>, struct CddBitmapStagingApertureMem *this@<rdx>, unsigned int@<r8d>, const struct tagRECT *@<r9>, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000c730`
- `0x14000cb44`

## callees

- `0x140002470`
- `0x140004600`
- `0x1400160c8`
- `0x14002fbd4`
- `0x140030070`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14002fd72`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14002fdf6`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14002fd72`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x14002fdf6`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002fe3b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002fe3b`
- `watchdog!WdLogSingleEntry1` at `0x14002fca3`
- `watchdog!WdLogSingleEntry1` at `0x14002fca3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002fcba`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002fcba`

## pseudocode

```c
void __fastcall FlushCpuCache(
        struct CDDPDEV *a1,
        struct CddBitmapStagingApertureMem *this,
        unsigned int a3,
        const struct tagRECT *a4)
{
  LONG left; // r13d
  LONG right; // ebx
  LONG bottom; // edi
  __int64 v8; // r12
  unsigned __int64 v9; // r8
  LONG top; // eax
  __int64 v11; // rcx
  LONG v12; // r10d
  LONG v14; // eax
  char *v15; // rsi
  _QWORD *v16; // rax
  unsigned int v17; // edi
  int v18; // ebx
  ULONG v19; // edi
  int v20; // r8d
  ULONG v21; // ebx
  unsigned int i; // r15d
  __int64 v23; // [rsp+30h] [rbp-51h] BYREF
  int v24; // [rsp+38h] [rbp-49h]
  _BYTE v25[16]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v26; // [rsp+50h] [rbp-31h]
  int v27; // [rsp+58h] [rbp-29h]
  __int128 v28; // [rsp+60h] [rbp-21h] BYREF
  __int128 v29; // [rsp+70h] [rbp-11h]
  __int128 v30; // [rsp+80h] [rbp-1h]
  int v31; // [rsp+E8h] [rbp+67h]
  LONG v33; // [rsp+100h] [rbp+7Fh]

  left = 0;
  right = a4->right;
  bottom = a4->bottom;
  if ( a4->left >= 0 )
    left = a4->left;
  v8 = a3;
  v9 = *((_QWORD *)this + 16);
  if ( right >= *((_DWORD *)this + 4) )
    right = *((_DWORD *)this + 4);
  v27 = 1;
  top = a4->top;
  v11 = (unsigned int)(4 * left);
  v12 = 0;
  v26 = 0;
  v28 = 0;
  if ( top >= 0 )
    v12 = top;
  v14 = *((_DWORD *)this + 5);
  v33 = v12;
  v29 = 0;
  if ( bottom >= v14 )
    bottom = v14;
  v30 = 0;
  v15 = (char *)((v11 + v9 + (unsigned int)(v8 * v12)) & ~(unsigned __int64)g_CPUCacheLineMaskBytes);
  v31 = v11 + v9 + v8 * v12;
  if ( (unsigned __int64)v15 >= v9 && bottom > v12 && right > left )
  {
    if ( CddBitmapStagingApertureMem::GetMdl(this, (__int64)this, v9) )
    {
      v17 = bottom - v33;
      v18 = 4 * (right - left);
      if ( *((_BYTE *)a1 + 2751) )
      {
        v19 = ~g_CPUCacheLineMaskBytes & (g_CPUCacheLineMaskBytes + v31 + v18 + v8 * (v17 - 1) - (_DWORD)v15);
        if ( (*((unsigned int (**)(void))a1 + 10))() )
        {
          v28 = 0;
          LODWORD(v28) = v19;
          v29 = 0;
          v30 = 0;
          CDDETWPROFILER::Init((CDDETWPROFILER *)v25, a1, 0xBEDu, (struct _DXGKETW_PARAMS *)&v28, 0);
        }
        if ( (unsigned __int64)&v15[v19] <= *((_QWORD *)this + 17) )
          KeInvalidateRangeAllCaches(v15, v19);
      }
      else
      {
        v21 = ~g_CPUCacheLineMaskBytes & (g_CPUCacheLineMaskBytes + v31 + v18 - (_DWORD)v15);
        if ( (*((unsigned int (**)(void))a1 + 10))() )
        {
          v28 = 0;
          v29 = 0;
          LODWORD(v28) = v17 * v21;
          v30 = 0;
          CDDETWPROFILER::Init((CDDETWPROFILER *)v25, a1, 0xBEDu, (struct _DXGKETW_PARAMS *)&v28, 0);
        }
        if ( (unsigned __int64)&v15[(unsigned int)v8 * (v17 - 1) + v21] <= *((_QWORD *)this + 17) )
        {
          for ( i = 0; i < v17; ++i )
          {
            KeInvalidateRangeAllCaches(v15, v21);
            v15 += v8;
          }
        }
      }
      if ( *((_QWORD *)this + 22) )
      {
        CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v23, *(struct CDDMUTEX **)(*((_QWORD *)this + 1) + 2904LL), v20);
        --*((_DWORD *)this + 50);
        if ( v24 )
          ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v23);
      }
    }
    else
    {
      WdLogSingleEntry1(2, a1);
      WdLogGlobalForLineNumber = 3231;
      v16 = (_QWORD *)WdLogNewEntry5_WdError();
      v16[3] = gCddImageInfo;
      v16[4] = (unsigned int)dword_14003E570;
      v16[5] = 215857758;
      WdLogGlobalForLineNumber = 3231;
    }
  }
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v25);
}

```

## disassembly

```asm
0x14002fbd4  push    rbp
0x14002fbd6  push    rbx
0x14002fbd7  push    rsi
0x14002fbd8  push    rdi
0x14002fbd9  push    r12
0x14002fbdb  push    r13
0x14002fbdd  push    r14
0x14002fbdf  push    r15
0x14002fbe1  lea     rbp, [rsp-17h]
0x14002fbe6  sub     rsp, 98h
0x14002fbed  mov     eax, [r9]
0x14002fbf0  xor     r13d, r13d
0x14002fbf3  mov     ebx, [r9+8]
0x14002fbf7  test    eax, eax
0x14002fbf9  mov     edi, [r9+0Ch]
0x14002fbfd  xorps   xmm0, xmm0
0x14002fc00  mov     esi, cs:?g_CPUCacheLineMaskBytes@@3IA; uint g_CPUCacheLineMaskBytes
0x14002fc06  cmovns  r13d, eax
0x14002fc0a  mov     eax, [rdx+10h]
0x14002fc0d  mov     r15, rcx
0x14002fc10  cmp     ebx, eax
0x14002fc12  mov     r12d, r8d
0x14002fc15  mov     r8, [rdx+80h]
0x14002fc1c  not     rsi
0x14002fc1f  cmovge  ebx, eax
0x14002fc22  mov     [rbp+4Fh+var_78], 1
0x14002fc29  mov     eax, [r9+4]
0x14002fc2d  lea     ecx, ds:0[r13*4]
0x14002fc35  xor     r10d, r10d
0x14002fc38  mov     [rbp+4Fh+var_80], 0
0x14002fc40  test    eax, eax
0x14002fc42  mov     r14, rdx
0x14002fc45  movups  [rbp+4Fh+var_70], xmm0
0x14002fc49  cmovns  r10d, eax
0x14002fc4d  mov     eax, [rdx+14h]
0x14002fc50  cmp     edi, eax
0x14002fc52  mov     dword ptr [rbp+4Fh+arg_20], r10d
0x14002fc56  movups  [rbp+4Fh+var_60], xmm0
0x14002fc5a  cmovge  edi, eax
0x14002fc5d  mov     eax, r10d
0x14002fc60  imul    eax, r12d
0x14002fc64  movups  [rbp+4Fh+var_50], xmm0
0x14002fc68  add     rax, r8
0x14002fc6b  add     rax, rcx
0x14002fc6e  and     rsi, rax
0x14002fc71  mov     [rbp+4Fh+arg_8], rax
0x14002fc75  cmp     rsi, r8
0x14002fc78  jb      loc_14002FE47
0x14002fc7e  cmp     edi, r10d
0x14002fc81  jle     loc_14002FE47
0x14002fc87  cmp     ebx, r13d
0x14002fc8a  jle     loc_14002FE47
0x14002fc90  mov     rcx, rdx; this
0x14002fc93  call    ?GetMdl@CddBitmapStagingApertureMem@@QEAAPEAU_MDL@@XZ; CddBitmapStagingApertureMem::GetMdl(void)
0x14002fc98  test    rax, rax
0x14002fc9b  jnz     short loc_14002FCEE
0x14002fc9d  mov     rdx, r15
0x14002fca0  lea     ecx, [rax+2]
0x14002fca3  call    cs:__imp_WdLogSingleEntry1
0x14002fcaa  nop     dword ptr [rax+rax+00h]
0x14002fcaf  mov     ebx, 0C9Fh
0x14002fcb4  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002fcba  call    cs:__imp_WdLogNewEntry5_WdError
0x14002fcc1  nop     dword ptr [rax+rax+00h]
0x14002fcc6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002fccd  mov     [rax+18h], rcx
0x14002fcd1  mov     ecx, cs:dword_14003E570
0x14002fcd7  mov     [rax+20h], rcx
0x14002fcdb  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002fce3  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002fce9  jmp     loc_14002FE47
0x14002fcee  mov     al, [r15+0ABFh]
0x14002fcf5  sub     ebx, r13d
0x14002fcf8  sub     edi, dword ptr [rbp+4Fh+arg_20]
0x14002fcfb  xor     r13d, r13d
0x14002fcfe  mov     rdx, [r15+50h]
0x14002fd02  shl     ebx, 2
0x14002fd05  test    al, al
0x14002fd07  jz      short loc_14002FD83
0x14002fd09  mov     eax, cs:?g_CPUCacheLineMaskBytes@@3IA; uint g_CPUCacheLineMaskBytes
0x14002fd0f  dec     edi
0x14002fd11  imul    edi, r12d
0x14002fd15  sub     edi, esi
0x14002fd17  add     edi, ebx
0x14002fd19  add     edi, dword ptr [rbp+4Fh+arg_8]
0x14002fd1c  add     edi, eax
0x14002fd1e  not     eax
0x14002fd20  and     edi, eax
0x14002fd22  mov     rax, rdx
0x14002fd25  call    _guard_dispatch_icall
0x14002fd2a  test    eax, eax
0x14002fd2c  jz      short loc_14002FD5B
0x14002fd2e  xorps   xmm0, xmm0
0x14002fd31  mov     [rsp+0D0h+var_B0], r13b; bool
0x14002fd36  movups  [rbp+4Fh+var_70], xmm0
0x14002fd3a  lea     r9, [rbp+4Fh+var_70]; struct _DXGKETW_PARAMS *
0x14002fd3e  mov     dword ptr [rbp+4Fh+var_70], edi
0x14002fd41  mov     r8d, 0BEDh; unsigned int
0x14002fd47  lea     rcx, [rbp+4Fh+var_90]; this
0x14002fd4b  mov     rdx, r15; struct CDDPDEV *
0x14002fd4e  movups  [rbp+4Fh+var_60], xmm0
0x14002fd52  movups  [rbp+4Fh+var_50], xmm0
0x14002fd56  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14002fd5b  mov     eax, edi
0x14002fd5d  add     rax, rsi
0x14002fd60  cmp     rax, [r14+88h]
0x14002fd67  ja      loc_14002FE0D
0x14002fd6d  mov     edx, edi; Length
0x14002fd6f  mov     rcx, rsi; BaseAddress
0x14002fd72  call    cs:__imp_KeInvalidateRangeAllCaches
0x14002fd79  nop     dword ptr [rax+rax+00h]
0x14002fd7e  jmp     loc_14002FE0D
0x14002fd83  mov     ecx, cs:?g_CPUCacheLineMaskBytes@@3IA; uint g_CPUCacheLineMaskBytes
0x14002fd89  sub     ebx, esi
0x14002fd8b  add     ebx, dword ptr [rbp+4Fh+arg_8]
0x14002fd8e  mov     rax, rdx
0x14002fd91  add     ebx, ecx
0x14002fd93  not     ecx
0x14002fd95  and     ebx, ecx
0x14002fd97  call    _guard_dispatch_icall
0x14002fd9c  test    eax, eax
0x14002fd9e  jz      short loc_14002FDD2
0x14002fda0  xorps   xmm0, xmm0
0x14002fda3  mov     [rsp+0D0h+var_B0], r13b; bool
0x14002fda8  mov     eax, ebx
0x14002fdaa  lea     r9, [rbp+4Fh+var_70]; struct _DXGKETW_PARAMS *
0x14002fdae  imul    eax, edi
0x14002fdb1  lea     rcx, [rbp+4Fh+var_90]; this
0x14002fdb5  movups  [rbp+4Fh+var_70], xmm0
0x14002fdb9  mov     r8d, 0BEDh; unsigned int
0x14002fdbf  mov     rdx, r15; struct CDDPDEV *
0x14002fdc2  movups  [rbp+4Fh+var_60], xmm0
0x14002fdc6  mov     dword ptr [rbp+4Fh+var_70], eax
0x14002fdc9  movups  [rbp+4Fh+var_50], xmm0
0x14002fdcd  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14002fdd2  lea     eax, [rdi-1]
0x14002fdd5  mov     edx, ebx
0x14002fdd7  imul    eax, r12d
0x14002fddb  add     rax, rsi
0x14002fdde  add     rdx, rax
0x14002fde1  cmp     rdx, [r14+88h]
0x14002fde8  ja      short loc_14002FE0D
0x14002fdea  mov     r15d, r13d
0x14002fded  test    edi, edi
0x14002fdef  jz      short loc_14002FE0D
0x14002fdf1  mov     edx, ebx; Length
0x14002fdf3  mov     rcx, rsi; BaseAddress
0x14002fdf6  call    cs:__imp_KeInvalidateRangeAllCaches
0x14002fdfd  nop     dword ptr [rax+rax+00h]
0x14002fe02  add     rsi, r12
0x14002fe05  inc     r15d
0x14002fe08  cmp     r15d, edi
0x14002fe0b  jb      short loc_14002FDF1
0x14002fe0d  cmp     [r14+0B0h], r13
0x14002fe14  jz      short loc_14002FE47
0x14002fe16  mov     rdx, [r14+8]
0x14002fe1a  lea     rcx, [rbp+4Fh+var_A0]; this
0x14002fe1e  mov     rdx, [rdx+0B58h]; struct CDDMUTEX *
0x14002fe25  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x14002fe2a  dec     dword ptr [r14+0C8h]
0x14002fe31  cmp     [rbp+4Fh+var_98], r13d
0x14002fe35  jz      short loc_14002FE47
0x14002fe37  mov     rcx, [rbp+4Fh+var_A0]
0x14002fe3b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14002fe42  nop     dword ptr [rax+rax+00h]
0x14002fe47  lea     rcx, [rbp+4Fh+var_90]; this
0x14002fe4b  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x14002fe50  add     rsp, 98h
0x14002fe57  pop     r15
0x14002fe59  pop     r14
0x14002fe5b  pop     r13
0x14002fe5d  pop     r12
0x14002fe5f  pop     rdi
0x14002fe60  pop     rsi
0x14002fe61  pop     rbx
0x14002fe62  pop     rbp
0x14002fe63  retn
```
