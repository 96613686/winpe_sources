# CSurfaceQueue::Initialize(SURFACE_QUEUE_DESC *,IUnknown *,CSurfaceQueue *)

- ea: `0x1800c26c4`
- end: `0x1800c2918`
- name: `?Initialize@CSurfaceQueue@@QEAAJPEAUSURFACE_QUEUE_DESC@@PEAUIUnknown@@PEAV1@@Z`
- size: `596`
- prototype: `__int64 __fastcall(CSurfaceQueue *__hidden this, struct SURFACE_QUEUE_DESC *, struct IUnknown *, struct CSurfaceQueue *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800c17f0`
- `0x1800c2f5c`

## callees

- `0x18004b740`
- `0x180073d0c`
- `0x180074a06`
- `0x1800c17b8`
- `0x1800c1938`
- `0x1800c1a78`
- `0x1800c26c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c28ea`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c28ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c2711`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800c2711`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800c28b1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800c28b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c28c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c28c6`

## pseudocode

```c
__int64 __fastcall CSurfaceQueue::Initialize(
        CSurfaceQueue *this,
        struct SURFACE_QUEUE_DESC *a2,
        struct IUnknown *a3,
        struct CSurfaceQueue *a4)
{
  char v8; // al
  unsigned int v9; // ebp
  void *v10; // rax
  void *v11; // rbx
  int DeviceWrapper; // ebx
  void *v13; // rax
  void *v14; // rax
  volatile signed __int32 *v15; // rax
  int v16; // eax
  __int64 i; // r8
  unsigned int j; // ebx
  void *v19; // rax
  __int64 v20; // rdx
  LONG v21; // edx
  HANDLE Semaphore; // rax
  signed int LastError; // eax
  int v24; // eax

  *(_OWORD *)((char *)this + 104) = *(_OWORD *)a2;
  *((_QWORD *)this + 15) = *((_QWORD *)a2 + 2);
  v8 = ~(unsigned __int8)(*((_DWORD *)this + 31) >> 1);
  *((_QWORD *)this + 3) = a4;
  *((_DWORD *)this + 3) = v8 & 1;
  CSurfaceQueue::AddQueueToNetwork(this);
  if ( *((_DWORD *)this + 3) )
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v9 = *((_DWORD *)a2 + 3);
  v10 = operator new(saturated_mul(v9, 0x20u));
  v11 = v10;
  if ( v10 )
    `vector constructor iterator'(
      v10,
      0x20u,
      v9,
      (void *(*)(void *))CSurfaceQueue::SharedSurfaceQueueEntry::SharedSurfaceQueueEntry);
  else
    v11 = 0;
  *((_QWORD *)this + 8) = v11;
  if ( !v11 )
    return (unsigned int)-2147024882;
  memset_0(v11, 0, 32LL * *((unsigned int *)a2 + 3));
  v13 = operator new(saturated_mul(*((unsigned int *)a2 + 3), 0x10u));
  if ( (*((_QWORD *)this + 10) = v13) == 0 )
    return (unsigned int)-2147024882;
  memset_0(v13, 0, 16LL * *((unsigned int *)a2 + 3));
  v14 = operator new(saturated_mul(*((unsigned int *)a2 + 3), 8u));
  if ( (*((_QWORD *)this + 11) = v14) == 0 )
    return (unsigned int)-2147024882;
  memset_0(v14, 0, 8LL * *((unsigned int *)a2 + 3));
  v15 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v15 == (volatile signed __int32 *)this )
  {
    DeviceWrapper = CreateDeviceWrapper(a3, (struct ISurfaceQueueDevice **)this + 7);
    if ( DeviceWrapper < 0 )
      return (unsigned int)DeviceWrapper;
    DeviceWrapper = CSurfaceQueue::CreateSurfaces(this);
    if ( DeviceWrapper < 0 )
      return (unsigned int)DeviceWrapper;
    v16 = *((_DWORD *)a2 + 3);
  }
  else
  {
    DeviceWrapper = 0;
    _InterlockedIncrement(v15 + 2);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 29); i = (unsigned int)(i + 1) )
      *(_QWORD *)(*((_QWORD *)this + 11) + 8 * i) = *(_QWORD *)(*((_QWORD *)a4 + 11) + 8 * i);
    v16 = 0;
  }
  *((_DWORD *)this + 19) = v16;
  if ( *((_DWORD *)this + 30) )
  {
    for ( j = 0; j < *((_DWORD *)this + 29); ++j )
    {
      v19 = operator new(*((unsigned int *)this + 30));
      v20 = 32LL * j;
      *(_QWORD *)(v20 + *((_QWORD *)this + 8) + 8) = v19;
      if ( !*(_QWORD *)(v20 + *((_QWORD *)this + 8) + 8) )
        return (unsigned int)-2147024882;
    }
    DeviceWrapper = 0;
  }
  if ( *((_DWORD *)this + 3) )
  {
    v21 = 0;
    if ( *((CSurfaceQueue **)this + 3) == this )
      v21 = *((_DWORD *)a2 + 3);
    Semaphore = CreateSemaphoreExW(0, v21, *((_DWORD *)a2 + 3), 0, 0, 0x1F0003u);
    *((_QWORD *)this + 2) = Semaphore;
    if ( Semaphore )
    {
      InitializeSRWLock((PSRWLOCK)this + 16);
    }
    else
    {
      LastError = GetLastError();
      DeviceWrapper = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    if ( *((CSurfaceQueue **)this + 3) == this )
      v24 = *((_DWORD *)a2 + 3);
    else
      v24 = 0;
    *((_DWORD *)this + 4) = v24;
  }
  return (unsigned int)DeviceWrapper;
}

```

## disassembly

```asm
0x1800c26c4  push    rbx
0x1800c26c6  push    rbp
0x1800c26c7  push    rsi
0x1800c26c8  push    rdi
0x1800c26c9  push    r14
0x1800c26cb  push    r15
0x1800c26cd  sub     rsp, 38h
0x1800c26d1  movups  xmm0, xmmword ptr [rdx]
0x1800c26d4  mov     r15, r9
0x1800c26d7  mov     r14, r8
0x1800c26da  mov     rsi, rdx
0x1800c26dd  mov     rdi, rcx
0x1800c26e0  movups  xmmword ptr [rcx+68h], xmm0
0x1800c26e4  movsd   xmm1, qword ptr [rdx+10h]
0x1800c26e9  movsd   qword ptr [rcx+78h], xmm1
0x1800c26ee  mov     eax, [rcx+7Ch]
0x1800c26f1  shr     eax, 1
0x1800c26f3  not     eax
0x1800c26f5  mov     [rcx+18h], r9
0x1800c26f9  and     eax, 1
0x1800c26fc  mov     [rcx+0Ch], eax
0x1800c26ff  call    ?AddQueueToNetwork@CSurfaceQueue@@AEAAIXZ; CSurfaceQueue::AddQueueToNetwork(void)
0x1800c2704  cmp     dword ptr [rdi+0Ch], 0
0x1800c2708  jz      short loc_1800C271D
0x1800c270a  lea     rcx, [rdi+88h]; lpCriticalSection
0x1800c2711  call    cs:__imp_InitializeCriticalSection
0x1800c2718  nop     dword ptr [rax+rax+00h]
0x1800c271d  mov     ebp, [rsi+0Ch]
0x1800c2720  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c2727  mov     eax, 20h ; ' '
0x1800c272c  mul     rbp
0x1800c272f  cmovb   rax, rcx
0x1800c2733  mov     rcx, rax; Size
0x1800c2736  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c273b  mov     rbx, rax
0x1800c273e  test    rax, rax
0x1800c2741  jz      short loc_1800C275C
0x1800c2743  lea     r9, ??0SharedSurfaceQueueEntry@CSurfaceQueue@@QEAA@XZ; void *(*)(void *)
0x1800c274a  mov     r8d, ebp; unsigned __int64
0x1800c274d  mov     edx, 20h ; ' '; unsigned __int64
0x1800c2752  mov     rcx, rax; void *
0x1800c2755  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800c275a  jmp     short loc_1800C275E
0x1800c275c  xor     ebx, ebx
0x1800c275e  mov     [rdi+40h], rbx
0x1800c2762  test    rbx, rbx
0x1800c2765  jnz     short loc_1800C2771
0x1800c2767  mov     ebx, 8007000Eh
0x1800c276c  jmp     loc_1800C2908
0x1800c2771  mov     r8d, [rsi+0Ch]
0x1800c2775  xor     edx, edx; Val
0x1800c2777  shl     r8, 5; Size
0x1800c277b  mov     rcx, rbx; void *
0x1800c277e  call    memset_0
0x1800c2783  mov     ecx, [rsi+0Ch]
0x1800c2786  mov     eax, 10h
0x1800c278b  mul     rcx
0x1800c278e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c2795  cmovb   rax, rbx
0x1800c2799  mov     rcx, rax; Size
0x1800c279c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c27a1  mov     [rdi+50h], rax
0x1800c27a5  test    rax, rax
0x1800c27a8  jz      short loc_1800C2767
0x1800c27aa  mov     r8d, [rsi+0Ch]
0x1800c27ae  xor     edx, edx; Val
0x1800c27b0  shl     r8, 4; Size
0x1800c27b4  mov     rcx, rax; void *
0x1800c27b7  call    memset_0
0x1800c27bc  mov     ecx, [rsi+0Ch]
0x1800c27bf  lea     eax, [rbx+9]
0x1800c27c2  mul     rcx
0x1800c27c5  cmovb   rax, rbx
0x1800c27c9  mov     rcx, rax; Size
0x1800c27cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c27d1  mov     [rdi+58h], rax
0x1800c27d5  test    rax, rax
0x1800c27d8  jz      short loc_1800C2767
0x1800c27da  mov     r8d, [rsi+0Ch]
0x1800c27de  xor     edx, edx; Val
0x1800c27e0  shl     r8, 3; Size
0x1800c27e4  mov     rcx, rax; void *
0x1800c27e7  call    memset_0
0x1800c27ec  mov     rax, [rdi+18h]
0x1800c27f0  cmp     rax, rdi
0x1800c27f3  jnz     short loc_1800C2822
0x1800c27f5  lea     rdx, [rdi+38h]; struct ISurfaceQueueDevice **
0x1800c27f9  mov     rcx, r14; struct IUnknown *
0x1800c27fc  call    ?CreateDeviceWrapper@@YAJPEAUIUnknown@@PEAPEAVISurfaceQueueDevice@@@Z; CreateDeviceWrapper(IUnknown *,ISurfaceQueueDevice * *)
0x1800c2801  mov     ebx, eax
0x1800c2803  test    eax, eax
0x1800c2805  js      loc_1800C2908
0x1800c280b  mov     rcx, rdi; this
0x1800c280e  call    ?CreateSurfaces@CSurfaceQueue@@AEAAJXZ; CSurfaceQueue::CreateSurfaces(void)
0x1800c2813  mov     ebx, eax
0x1800c2815  test    eax, eax
0x1800c2817  js      loc_1800C2908
0x1800c281d  mov     eax, [rsi+0Ch]
0x1800c2820  jmp     short loc_1800C284B
0x1800c2822  xor     ebx, ebx
0x1800c2824  lock inc dword ptr [rax+8]
0x1800c2828  xor     r8d, r8d
0x1800c282b  cmp     [rdi+74h], ebx
0x1800c282e  jbe     short loc_1800C2849
0x1800c2830  mov     rax, [r15+58h]
0x1800c2834  mov     rcx, [rdi+58h]
0x1800c2838  mov     rax, [rax+r8*8]
0x1800c283c  mov     [rcx+r8*8], rax
0x1800c2840  inc     r8d
0x1800c2843  cmp     r8d, [rdi+74h]
0x1800c2847  jb      short loc_1800C2830
0x1800c2849  xor     eax, eax
0x1800c284b  mov     [rdi+4Ch], eax
0x1800c284e  cmp     dword ptr [rdi+78h], 0
0x1800c2852  jz      short loc_1800C2888
0x1800c2854  xor     ebx, ebx
0x1800c2856  cmp     ebx, [rdi+74h]
0x1800c2859  jnb     short loc_1800C2886
0x1800c285b  mov     ecx, [rdi+78h]; Size
0x1800c285e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c2863  mov     rcx, [rdi+40h]
0x1800c2867  mov     edx, ebx
0x1800c2869  shl     rdx, 5
0x1800c286d  mov     [rdx+rcx+8], rax
0x1800c2872  mov     rax, [rdi+40h]
0x1800c2876  cmp     qword ptr [rdx+rax+8], 0
0x1800c287c  jz      loc_1800C2767
0x1800c2882  inc     ebx
0x1800c2884  jmp     short loc_1800C2856
0x1800c2886  xor     ebx, ebx
0x1800c2888  cmp     dword ptr [rdi+0Ch], 0
0x1800c288c  jz      short loc_1800C28F8
0x1800c288e  mov     r8d, [rsi+0Ch]; lMaximumCount
0x1800c2892  xor     edx, edx
0x1800c2894  cmp     [rdi+18h], rdi
0x1800c2898  mov     [rsp+68h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800c28a0  cmovz   edx, r8d; lInitialCount
0x1800c28a4  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800c28ac  xor     r9d, r9d; lpName
0x1800c28af  xor     ecx, ecx; lpSemaphoreAttributes
0x1800c28b1  call    cs:__imp_CreateSemaphoreExW
0x1800c28b8  nop     dword ptr [rax+rax+00h]
0x1800c28bd  mov     [rdi+10h], rax
0x1800c28c1  test    rax, rax
0x1800c28c4  jnz     short loc_1800C28E3
0x1800c28c6  call    cs:__imp_GetLastError
0x1800c28cd  nop     dword ptr [rax+rax+00h]
0x1800c28d2  mov     ebx, eax
0x1800c28d4  test    eax, eax
0x1800c28d6  jle     short loc_1800C2908
0x1800c28d8  movzx   ebx, ax
0x1800c28db  or      ebx, 80070000h
0x1800c28e1  jmp     short loc_1800C2908
0x1800c28e3  lea     rcx, [rdi+80h]; SRWLock
0x1800c28ea  call    cs:__imp_InitializeSRWLock
0x1800c28f1  nop     dword ptr [rax+rax+00h]
0x1800c28f6  jmp     short loc_1800C2908
0x1800c28f8  cmp     [rdi+18h], rdi
0x1800c28fc  jnz     short loc_1800C2903
0x1800c28fe  mov     eax, [rsi+0Ch]
0x1800c2901  jmp     short loc_1800C2905
0x1800c2903  xor     eax, eax
0x1800c2905  mov     [rdi+10h], eax
0x1800c2908  mov     eax, ebx
0x1800c290a  add     rsp, 38h
0x1800c290e  pop     r15
0x1800c2910  pop     r14
0x1800c2912  pop     rdi
0x1800c2913  pop     rsi
0x1800c2914  pop     rbp
0x1800c2915  pop     rbx
0x1800c2916  retn
```
