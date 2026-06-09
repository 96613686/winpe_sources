# GetInstalledCodecs(uint *,ImageCodecInfo * *,uint)

- ea: `0x18014e460`
- end: `0x18014e6c0`
- name: `?GetInstalledCodecs@@YAJPEAIPEAPEAVImageCodecInfo@@I@Z`
- size: `608`
- prototype: `__int64 __fastcall(unsigned int *, struct ImageCodecInfo **, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180151c20`
- `0x180151c40`

## callees

- `0x18000cc00`
- `0x18000d2f0`
- `0x18014e460`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18014e48d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18014e48d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18014e692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18014e692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014e4ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014e4ef`

## pseudocode

```c
__int64 __fastcall GetInstalledCodecs(unsigned int *a1, struct ImageCodecInfo **a2, int a3)
{
  struct CachedCodecInfo *v6; // r9
  unsigned int v7; // esi
  unsigned int v8; // r10d
  unsigned int v9; // ebx
  struct ImageCodecInfo *v10; // rax
  const unsigned __int16 *v11; // rdx
  struct CachedCodecInfo *v12; // rbp
  char *v13; // rdi
  char *v14; // r14
  size_t v15; // rbx
  const unsigned __int16 *v16; // rdx
  char *v17; // rdi
  size_t v18; // rbx
  size_t v19; // rbx
  char *v20; // rdi
  const unsigned __int16 *v21; // rdx
  size_t v22; // rbx
  char *v23; // rdi
  const unsigned __int16 *v24; // rdx
  size_t v25; // rbx
  unsigned int v26; // eax
  __int64 v27; // rbx
  char *v28; // rdi

  EnterCriticalSection(&ImagingCritSec::critSec);
  ReloadCachedCodecInfo();
  v6 = CachedCodecs;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  while ( v6 )
  {
    if ( (a3 & *((_DWORD *)v6 + 18)) != 0 )
    {
      ++v9;
      if ( v8 + *((_DWORD *)v6 + 30) < v8 )
        goto LABEL_7;
      v8 += *((_DWORD *)v6 + 30);
    }
    v6 = (struct CachedCodecInfo *)*((_QWORD *)v6 + 13);
  }
  *a1 = 0;
  *a2 = 0;
  if ( v9 )
  {
    v10 = (struct ImageCodecInfo *)CoTaskMemAlloc(v8);
    if ( !v10 )
    {
LABEL_7:
      v7 = -2147024882;
      goto LABEL_20;
    }
    v12 = CachedCodecs;
    *a1 = v9;
    *a2 = v10;
    v13 = (char *)v10 + 104 * v9;
    if ( v12 )
    {
      v14 = (char *)v10 + 40;
      do
      {
        if ( (a3 & *((_DWORD *)v12 + 18)) != 0 )
        {
          *(_OWORD *)(v14 - 40) = *(_OWORD *)v12;
          *(_OWORD *)(v14 - 24) = *((_OWORD *)v12 + 1);
          *(_OWORD *)(v14 - 8) = *((_OWORD *)v12 + 2);
          *(_OWORD *)(v14 + 8) = *((_OWORD *)v12 + 3);
          *(_OWORD *)(v14 + 24) = *((_OWORD *)v12 + 4);
          *(_OWORD *)(v14 + 40) = *((_OWORD *)v12 + 5);
          *((_QWORD *)v14 + 7) = *((_QWORD *)v12 + 12);
          *((_QWORD *)v14 - 1) = v13;
          v15 = 2 * (unsigned int)GpRuntime::UnicodeStringLength(*((GpRuntime **)v12 + 4), v11) + 2;
          memcpy_0(v13, *((const void **)v12 + 4), v15);
          v17 = &v13[v15];
          if ( *((_QWORD *)v12 + 5) )
          {
            *(_QWORD *)v14 = v17;
            v18 = 2 * (unsigned int)GpRuntime::UnicodeStringLength(*((GpRuntime **)v12 + 5), v16) + 2;
            memcpy_0(v17, *((const void **)v12 + 5), v18);
            v17 += v18;
          }
          *((_QWORD *)v14 + 1) = v17;
          v19 = 2 * (unsigned int)GpRuntime::UnicodeStringLength(*((GpRuntime **)v12 + 6), v16) + 2;
          memcpy_0(v17, *((const void **)v12 + 6), v19);
          v20 = &v17[v19];
          *((_QWORD *)v14 + 2) = v20;
          v22 = 2 * (unsigned int)GpRuntime::UnicodeStringLength(*((GpRuntime **)v12 + 7), v21) + 2;
          memcpy_0(v20, *((const void **)v12 + 7), v22);
          v23 = &v20[v22];
          *((_QWORD *)v14 + 3) = v23;
          v25 = 2 * (unsigned int)GpRuntime::UnicodeStringLength(*((GpRuntime **)v12 + 8), v24) + 2;
          memcpy_0(v23, *((const void **)v12 + 8), v25);
          v13 = &v23[v25];
          v26 = *((_DWORD *)v12 + 20) * *((_DWORD *)v12 + 21);
          if ( v26 )
          {
            *((_QWORD *)v14 + 6) = v13;
            v27 = v26;
            memcpy_0(v13, *((const void **)v12 + 11), v26);
            v28 = &v13[v27];
            *((_QWORD *)v14 + 7) = v28;
            memcpy_0(v28, *((const void **)v12 + 12), (unsigned int)v27);
            v13 = &v28[v27];
          }
          v14 += 104;
        }
        v12 = (struct CachedCodecInfo *)*((_QWORD *)v12 + 13);
      }
      while ( v12 );
    }
  }
  else
  {
    v7 = -2005204986;
  }
LABEL_20:
  LeaveCriticalSection(&ImagingCritSec::critSec);
  return v7;
}

```

## disassembly

```asm
0x18014e460  mov     rax, rsp
0x18014e463  mov     [rax+8], rbx
0x18014e467  mov     [rax+10h], rbp
0x18014e46b  mov     [rax+18h], rsi
0x18014e46f  mov     [rax+20h], rdi
0x18014e473  push    r12
0x18014e475  push    r14
0x18014e477  push    r15
0x18014e479  sub     rsp, 20h
0x18014e47d  mov     r15, rcx
0x18014e480  mov     r12d, r8d
0x18014e483  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18014e48a  mov     r14, rdx
0x18014e48d  call    cs:__imp_EnterCriticalSection
0x18014e494  nop     dword ptr [rax+rax+00h]
0x18014e499  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x18014e49e  mov     r9, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x18014e4a5  xor     esi, esi
0x18014e4a7  mov     r10d, esi
0x18014e4aa  mov     ebx, esi
0x18014e4ac  test    r9, r9
0x18014e4af  jz      short loc_18014E4D8
0x18014e4b1  test    [r9+48h], r12d
0x18014e4b5  jz      short loc_18014E4C8
0x18014e4b7  mov     ecx, [r9+78h]
0x18014e4bb  inc     ebx
0x18014e4bd  add     ecx, r10d
0x18014e4c0  cmp     ecx, r10d
0x18014e4c3  jb      short loc_18014E4CE
0x18014e4c5  mov     r10d, ecx
0x18014e4c8  mov     r9, [r9+68h]
0x18014e4cc  jmp     short loc_18014E4AC
0x18014e4ce  mov     esi, 8007000Eh
0x18014e4d3  jmp     loc_18014E68B
0x18014e4d8  mov     [r15], esi
0x18014e4db  mov     [r14], rsi
0x18014e4de  test    ebx, ebx
0x18014e4e0  jnz     short loc_18014E4EC
0x18014e4e2  mov     esi, 887B0006h
0x18014e4e7  jmp     loc_18014E68B
0x18014e4ec  mov     ecx, r10d; cb
0x18014e4ef  call    cs:__imp_CoTaskMemAlloc
0x18014e4f6  nop     dword ptr [rax+rax+00h]
0x18014e4fb  mov     rdi, rax
0x18014e4fe  test    rax, rax
0x18014e501  jz      short loc_18014E4CE
0x18014e503  mov     rbp, cs:?CachedCodecs@@3PEAUCachedCodecInfo@@EA; CachedCodecInfo * CachedCodecs
0x18014e50a  mov     [r15], ebx
0x18014e50d  mov     [r14], rax
0x18014e510  mov     r14, rax
0x18014e513  mov     eax, ebx
0x18014e515  imul    rcx, rax, 68h ; 'h'
0x18014e519  add     rdi, rcx
0x18014e51c  test    rbp, rbp
0x18014e51f  jz      loc_18014E68B
0x18014e525  add     r14, 28h ; '('
0x18014e529  test    [rbp+48h], r12d
0x18014e52d  jz      loc_18014E67E
0x18014e533  movups  xmm0, xmmword ptr [rbp+0]
0x18014e537  movups  xmmword ptr [r14-28h], xmm0
0x18014e53c  movups  xmm1, xmmword ptr [rbp+10h]
0x18014e540  movups  xmmword ptr [r14-18h], xmm1
0x18014e545  movups  xmm0, xmmword ptr [rbp+20h]
0x18014e549  movups  xmmword ptr [r14-8], xmm0
0x18014e54e  movups  xmm1, xmmword ptr [rbp+30h]
0x18014e552  movups  xmmword ptr [r14+8], xmm1
0x18014e557  movups  xmm0, xmmword ptr [rbp+40h]
0x18014e55b  movups  xmmword ptr [r14+18h], xmm0
0x18014e560  movups  xmm1, xmmword ptr [rbp+50h]
0x18014e564  movups  xmmword ptr [r14+28h], xmm1
0x18014e569  movsd   xmm0, qword ptr [rbp+60h]
0x18014e56e  movsd   qword ptr [r14+38h], xmm0
0x18014e574  mov     [r14-8], rdi
0x18014e578  mov     rcx, [rbp+20h]; this
0x18014e57c  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014e581  mov     rdx, [rbp+20h]; Src
0x18014e585  mov     rcx, rdi; void *
0x18014e588  lea     eax, ds:2[rax*2]
0x18014e58f  mov     r8d, eax; Size
0x18014e592  mov     ebx, eax
0x18014e594  call    memcpy_0
0x18014e599  add     rdi, rbx
0x18014e59c  cmp     [rbp+28h], rsi
0x18014e5a0  jz      short loc_18014E5C9
0x18014e5a2  mov     [r14], rdi
0x18014e5a5  mov     rcx, [rbp+28h]; this
0x18014e5a9  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014e5ae  mov     rdx, [rbp+28h]; Src
0x18014e5b2  mov     rcx, rdi; void *
0x18014e5b5  lea     eax, ds:2[rax*2]
0x18014e5bc  mov     r8d, eax; Size
0x18014e5bf  mov     ebx, eax
0x18014e5c1  call    memcpy_0
0x18014e5c6  add     rdi, rbx
0x18014e5c9  mov     [r14+8], rdi
0x18014e5cd  mov     rcx, [rbp+30h]; this
0x18014e5d1  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014e5d6  mov     rdx, [rbp+30h]; Src
0x18014e5da  mov     rcx, rdi; void *
0x18014e5dd  lea     eax, ds:2[rax*2]
0x18014e5e4  mov     r8d, eax; Size
0x18014e5e7  mov     ebx, eax
0x18014e5e9  call    memcpy_0
0x18014e5ee  add     rdi, rbx
0x18014e5f1  mov     [r14+10h], rdi
0x18014e5f5  mov     rcx, [rbp+38h]; this
0x18014e5f9  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014e5fe  mov     rdx, [rbp+38h]; Src
0x18014e602  mov     rcx, rdi; void *
0x18014e605  lea     eax, ds:2[rax*2]
0x18014e60c  mov     r8d, eax; Size
0x18014e60f  mov     ebx, eax
0x18014e611  call    memcpy_0
0x18014e616  add     rdi, rbx
0x18014e619  mov     [r14+18h], rdi
0x18014e61d  mov     rcx, [rbp+40h]; this
0x18014e621  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x18014e626  mov     rdx, [rbp+40h]; Src
0x18014e62a  mov     rcx, rdi; void *
0x18014e62d  lea     eax, ds:2[rax*2]
0x18014e634  mov     r8d, eax; Size
0x18014e637  mov     ebx, eax
0x18014e639  call    memcpy_0
0x18014e63e  mov     eax, [rbp+54h]
0x18014e641  add     rdi, rbx
0x18014e644  imul    eax, [rbp+50h]
0x18014e648  test    eax, eax
0x18014e64a  jz      short loc_18014E67A
0x18014e64c  mov     [r14+30h], rdi
0x18014e650  mov     rcx, rdi; void *
0x18014e653  mov     rdx, [rbp+58h]; Src
0x18014e657  mov     r8d, eax; Size
0x18014e65a  mov     ebx, eax
0x18014e65c  call    memcpy_0
0x18014e661  add     rdi, rbx
0x18014e664  mov     r8d, ebx; Size
0x18014e667  mov     [r14+38h], rdi
0x18014e66b  mov     rcx, rdi; void *
0x18014e66e  mov     rdx, [rbp+60h]; Src
0x18014e672  call    memcpy_0
0x18014e677  add     rdi, rbx
0x18014e67a  add     r14, 68h ; 'h'
0x18014e67e  mov     rbp, [rbp+68h]
0x18014e682  test    rbp, rbp
0x18014e685  jnz     loc_18014E529
0x18014e68b  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18014e692  call    cs:__imp_LeaveCriticalSection
0x18014e699  nop     dword ptr [rax+rax+00h]
0x18014e69e  mov     rbx, [rsp+38h+arg_0]
0x18014e6a3  mov     eax, esi
0x18014e6a5  mov     rsi, [rsp+38h+arg_10]
0x18014e6aa  mov     rbp, [rsp+38h+arg_8]
0x18014e6af  mov     rdi, [rsp+38h+arg_18]
0x18014e6b4  add     rsp, 20h
0x18014e6b8  pop     r15
0x18014e6ba  pop     r14
0x18014e6bc  pop     r12
0x18014e6be  retn
```
