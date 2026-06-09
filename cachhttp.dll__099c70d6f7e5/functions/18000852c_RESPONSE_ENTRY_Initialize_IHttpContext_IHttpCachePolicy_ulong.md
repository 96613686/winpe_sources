# RESPONSE_ENTRY::Initialize(IHttpContext *,IHttpCachePolicy *,ulong)

- ea: `0x18000852c`
- end: `0x1800088d1`
- name: `?Initialize@RESPONSE_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIHttpCachePolicy@@K@Z`
- size: `933`
- prototype: `signed int __fastcall(RESPONSE_ENTRY *this, struct IHttpContext *, struct IHttpCachePolicy *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004220`

## callees

- `0x18000852c`
- `0x180008bb2`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000855f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000855f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000880f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000881c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000880f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000881c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000862b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000866d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008688`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008715`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000876e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000886a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000862b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000866d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008688`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008715`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000876e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000886a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008841`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008841`

## pseudocode

```c
signed int __fastcall RESPONSE_ENTRY::Initialize(
        RESPONSE_ENTRY *this,
        struct IHttpContext *a2,
        struct IHttpCachePolicy *a3,
        int a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbp
  void *v10; // rax
  char *v11; // rax
  char *v12; // rdi
  unsigned int v13; // r14d
  const void **v14; // rsi
  LPVOID v15; // rax
  HANDLE v16; // rcx
  LPVOID v17; // rax
  void *v18; // rcx
  unsigned __int16 v19; // ax
  unsigned int i; // esi
  void *v21; // rax
  HANDLE *v22; // rax
  HANDLE *v23; // r14
  unsigned int v24; // r15d
  int *v25; // rsi
  void *v26; // rax
  HANDLE CurrentProcess; // rax
  void *v28; // rdi
  void *v29; // rbx
  HANDLE v30; // rax
  void *v31; // rax
  int v32; // eax
  signed int result; // eax

  *((_DWORD *)this + 146) = a4;
  if ( *(_DWORD *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a3 + 16LL))(a3) == 2 )
  {
    *((_DWORD *)this + 147) = GetTickCount();
    v7 = (*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a3 + 16LL))(a3);
    if ( *(_DWORD *)(v7 + 4) < 0x418937u )
      *((_DWORD *)this + 148) = 1000 * *(_DWORD *)(v7 + 4);
  }
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  *((_DWORD *)this + 5) = *(_DWORD *)(v9 + 4);
  *((_WORD *)this + 12) = *(_WORD *)(v9 + 8);
  v10 = HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 0, *(unsigned __int16 *)(v9 + 10) + 1LL);
  *((_QWORD *)this + 4) = v10;
  if ( !v10 )
    return -2147024888;
  memcpy_0(v10, *(const void **)(v9 + 16), *(unsigned __int16 *)(v9 + 10) + 1LL);
  *((_WORD *)this + 13) = *(_WORD *)(v9 + 10);
  if ( *(_WORD *)(v9 + 24) )
  {
    v11 = (char *)HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 8u, 24LL * *(unsigned __int16 *)(v9 + 24));
    *((_QWORD *)this + 6) = v11;
    v12 = v11;
    if ( !v11 )
      return -2147024888;
    v13 = 0;
    *((_WORD *)this + 20) = *(_WORD *)(v9 + 24);
    v14 = *(const void ***)(v9 + 32);
    while ( v13 < *((unsigned __int16 *)this + 20) )
    {
      v15 = HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 0, *(unsigned __int16 *)v14 + 1LL);
      v16 = RESPONSE_ENTRY::sm_hHeap;
      *((_QWORD *)v12 + 1) = v15;
      v17 = HeapAlloc(v16, 0, *((unsigned __int16 *)v14 + 1) + 1LL);
      v18 = (void *)*((_QWORD *)v12 + 1);
      *((_QWORD *)v12 + 2) = v17;
      if ( !v18 || !v17 )
        return -2147024888;
      memcpy_0(v18, v14[1], *(unsigned __int16 *)v14 + 1LL);
      memcpy_0(*((void **)v12 + 2), v14[2], *((unsigned __int16 *)v14 + 1) + 1LL);
      *(_WORD *)v12 = *(_WORD *)v14;
      v19 = *((_WORD *)v14 + 1);
      v14 += 3;
      *((_WORD *)v12 + 1) = v19;
      v12 += 24;
      ++v13;
    }
  }
  for ( i = 0; i < 0x1E; ++i )
  {
    if ( *(_QWORD *)(v9 + 16 * (i + 2LL) + 32) )
    {
      v21 = HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 0, *(unsigned __int16 *)(v9 + 16 * (i + 2LL) + 24) + 1LL);
      *((_QWORD *)this + 2 * i + 10) = v21;
      if ( !v21 )
        return -2147024888;
      memcpy_0(v21, *(const void **)(v9 + 16 * (i + 2LL) + 32), *(unsigned __int16 *)(v9 + 16 * (i + 2LL) + 24) + 1LL);
      *((_WORD *)this + 8 * i + 36) = *(_WORD *)(v9 + 16 * (i + 2LL) + 24);
    }
  }
  if ( !*(_WORD *)(v9 + 536) )
    return 0;
  v22 = (HANDLE *)HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 8u, 32LL * *(unsigned __int16 *)(v9 + 536));
  *((_QWORD *)this + 70) = v22;
  v23 = v22;
  if ( v22 )
  {
    v24 = 0;
    *((_WORD *)this + 276) = *(_WORD *)(v9 + 536);
    v25 = *(int **)(v9 + 544);
    while ( v24 < *(unsigned __int16 *)(v9 + 536) )
    {
      if ( *v25 )
      {
        if ( *v25 == 1 )
        {
          CurrentProcess = GetCurrentProcess();
          v28 = (void *)*((_QWORD *)v25 + 3);
          v29 = CurrentProcess;
          v30 = GetCurrentProcess();
          if ( !DuplicateHandle(v30, v28, v29, v23 + 3, 0, 0, 2u) )
          {
            result = GetLastError();
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
            return result;
          }
          v23[1] = (HANDLE)*((_QWORD *)v25 + 1);
          v23[2] = (HANDLE)*((_QWORD *)v25 + 2);
        }
        else if ( *v25 == 2 )
        {
          v26 = HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 0, *((unsigned __int16 *)v25 + 4) + 2LL);
          v23[2] = v26;
          if ( !v26 )
            return -2147024888;
          memcpy_0(v26, *((const void **)v25 + 2), *((unsigned __int16 *)v25 + 4) + 2LL);
          *((_WORD *)v23 + 4) = *((_WORD *)v25 + 4);
        }
      }
      else
      {
        v31 = HeapAlloc(RESPONSE_ENTRY::sm_hHeap, 0, (unsigned int)v25[4]);
        v23[1] = v31;
        if ( !v31 )
          return -2147024888;
        memcpy_0(v31, *((const void **)v25 + 1), (unsigned int)v25[4]);
        *((_DWORD *)v23 + 4) = v25[4];
      }
      v32 = *v25;
      v25 += 8;
      *(_DWORD *)v23 = v32;
      v23 += 4;
      ++v24;
    }
    return 0;
  }
  return -2147024888;
}

```

## disassembly

```asm
0x18000852c  push    rbx
0x18000852e  push    rbp
0x18000852f  push    rsi
0x180008530  push    rdi
0x180008531  push    r12
0x180008533  push    r14
0x180008535  push    r15
0x180008537  sub     rsp, 40h
0x18000853b  mov     [rcx+248h], r9d
0x180008542  mov     rbx, rcx
0x180008545  mov     rax, [r8]
0x180008548  mov     rcx, r8
0x18000854b  mov     rdi, r8
0x18000854e  mov     rsi, rdx
0x180008551  mov     rax, [rax+10h]
0x180008555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000855a  cmp     dword ptr [rax], 2
0x18000855d  jnz     short loc_180008590
0x18000855f  call    cs:__imp_GetTickCount
0x180008565  mov     [rbx+24Ch], eax
0x18000856b  mov     rcx, rdi
0x18000856e  mov     rax, [rdi]
0x180008571  mov     rax, [rax+10h]
0x180008575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857a  cmp     dword ptr [rax+4], 418937h
0x180008581  jnb     short loc_180008590
0x180008583  imul    eax, [rax+4], 3E8h
0x18000858a  mov     [rbx+250h], eax
0x180008590  mov     rax, [rsi]
0x180008593  mov     rcx, rsi
0x180008596  mov     rax, [rax+20h]
0x18000859a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000859f  mov     rdx, rax
0x1800085a2  mov     rcx, [rax]
0x1800085a5  mov     rax, [rcx+8]
0x1800085a9  mov     rcx, rdx
0x1800085ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b1  xor     edx, edx; dwFlags
0x1800085b3  mov     rbp, rax
0x1800085b6  mov     ecx, [rax+4]
0x1800085b9  mov     [rbx+14h], ecx
0x1800085bc  movzx   ecx, word ptr [rax+8]
0x1800085c0  mov     [rbx+18h], cx
0x1800085c4  movzx   r8d, word ptr [rax+0Ah]
0x1800085c9  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x1800085d0  inc     r8; dwBytes
0x1800085d3  call    cs:__imp_HeapAlloc
0x1800085d9  xor     r12d, r12d
0x1800085dc  mov     [rbx+20h], rax
0x1800085e0  test    rax, rax
0x1800085e3  jz      loc_1800088BD
0x1800085e9  movzx   r8d, word ptr [rbp+0Ah]
0x1800085ee  mov     rcx, rax; void *
0x1800085f1  mov     rdx, [rbp+10h]; Src
0x1800085f5  inc     r8; Size
0x1800085f8  call    memcpy_0
0x1800085fd  movzx   eax, word ptr [rbp+0Ah]
0x180008601  lea     r15d, [r12+8]
0x180008606  mov     [rbx+1Ah], ax
0x18000860a  cmp     [rbp+18h], r12w
0x18000860f  jz      loc_1800086EB
0x180008615  movzx   eax, word ptr [rbp+18h]
0x180008619  mov     edx, r15d; dwFlags
0x18000861c  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180008623  lea     r8, [rax+rax*2]
0x180008627  shl     r8, 3; dwBytes
0x18000862b  call    cs:__imp_HeapAlloc
0x180008631  mov     [rbx+30h], rax
0x180008635  mov     rdi, rax
0x180008638  test    rax, rax
0x18000863b  jz      loc_1800088BD
0x180008641  movzx   ecx, word ptr [rbp+18h]
0x180008645  mov     r14d, r12d
0x180008648  mov     [rbx+28h], cx
0x18000864c  mov     rsi, [rbp+20h]
0x180008650  movzx   ecx, word ptr [rbx+28h]
0x180008654  cmp     r14d, ecx
0x180008657  jnb     loc_1800086EB
0x18000865d  movzx   r8d, word ptr [rsi]
0x180008661  xor     edx, edx; dwFlags
0x180008663  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x18000866a  inc     r8; dwBytes
0x18000866d  call    cs:__imp_HeapAlloc
0x180008673  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x18000867a  xor     edx, edx; dwFlags
0x18000867c  mov     [rdi+8], rax
0x180008680  movzx   r8d, word ptr [rsi+2]
0x180008685  inc     r8; dwBytes
0x180008688  call    cs:__imp_HeapAlloc
0x18000868e  mov     rcx, [rdi+8]; void *
0x180008692  mov     [rdi+10h], rax
0x180008696  test    rcx, rcx
0x180008699  jz      loc_1800088BD
0x18000869f  test    rax, rax
0x1800086a2  jz      loc_1800088BD
0x1800086a8  movzx   r8d, word ptr [rsi]
0x1800086ac  mov     rdx, [rsi+8]; Src
0x1800086b0  inc     r8; Size
0x1800086b3  call    memcpy_0
0x1800086b8  movzx   r8d, word ptr [rsi+2]
0x1800086bd  mov     rdx, [rsi+10h]; Src
0x1800086c1  inc     r8; Size
0x1800086c4  mov     rcx, [rdi+10h]; void *
0x1800086c8  call    memcpy_0
0x1800086cd  movzx   eax, word ptr [rsi]
0x1800086d0  mov     [rdi], ax
0x1800086d3  movzx   eax, word ptr [rsi+2]
0x1800086d7  add     rsi, 18h
0x1800086db  mov     [rdi+2], ax
0x1800086df  add     rdi, 18h
0x1800086e3  inc     r14d
0x1800086e6  jmp     loc_180008650
0x1800086eb  mov     esi, r12d
0x1800086ee  cmp     esi, 1Eh
0x1800086f1  jnb     short loc_18000874D
0x1800086f3  mov     edi, esi
0x1800086f5  add     rdi, 2
0x1800086f9  add     rdi, rdi
0x1800086fc  cmp     [rbp+rdi*8+20h], r12
0x180008701  jz      short loc_180008749
0x180008703  movzx   r8d, word ptr [rbp+rdi*8+18h]
0x180008709  xor     edx, edx; dwFlags
0x18000870b  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180008712  inc     r8; dwBytes
0x180008715  call    cs:__imp_HeapAlloc
0x18000871b  mov     [rbx+rdi*8+30h], rax
0x180008720  test    rax, rax
0x180008723  jz      loc_1800088BD
0x180008729  movzx   r8d, word ptr [rbp+rdi*8+18h]
0x18000872f  mov     rcx, rax; void *
0x180008732  mov     rdx, [rbp+rdi*8+20h]; Src
0x180008737  inc     r8; Size
0x18000873a  call    memcpy_0
0x18000873f  movzx   eax, word ptr [rbp+rdi*8+18h]
0x180008744  mov     [rbx+rdi*8+28h], ax
0x180008749  inc     esi
0x18000874b  jmp     short loc_1800086EE
0x18000874d  movzx   eax, word ptr [rbp+218h]
0x180008754  test    ax, ax
0x180008757  jz      loc_1800088B9
0x18000875d  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180008764  mov     r8d, eax
0x180008767  shl     r8, 5; dwBytes
0x18000876b  mov     edx, r15d; dwFlags
0x18000876e  call    cs:__imp_HeapAlloc
0x180008774  mov     [rbx+230h], rax
0x18000877b  mov     r14, rax
0x18000877e  test    rax, rax
0x180008781  jz      loc_1800088BD
0x180008787  movzx   ecx, word ptr [rbp+218h]
0x18000878e  mov     r15d, r12d
0x180008791  mov     [rbx+228h], cx
0x180008798  mov     rsi, [rbp+220h]
0x18000879f  movzx   eax, word ptr [rbp+218h]
0x1800087a6  cmp     r15d, eax
0x1800087a9  jnb     loc_1800088B9
0x1800087af  mov     ecx, [rsi]
0x1800087b1  test    ecx, ecx
0x1800087b3  jz      loc_18000885D
0x1800087b9  sub     ecx, 1
0x1800087bc  jz      short loc_18000880F
0x1800087be  cmp     ecx, 1
0x1800087c1  jnz     loc_180008890
0x1800087c7  movzx   r8d, word ptr [rsi+8]
0x1800087cc  xor     edx, edx; dwFlags
0x1800087ce  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x1800087d5  add     r8, 2; dwBytes
0x1800087d9  call    cs:__imp_HeapAlloc
0x1800087df  mov     [r14+10h], rax
0x1800087e3  test    rax, rax
0x1800087e6  jz      loc_1800088BD
0x1800087ec  movzx   r8d, word ptr [rsi+8]
0x1800087f1  mov     rcx, rax; void *
0x1800087f4  mov     rdx, [rsi+10h]; Src
0x1800087f8  add     r8, 2; Size
0x1800087fc  call    memcpy_0
0x180008801  movzx   eax, word ptr [rsi+8]
0x180008805  mov     [r14+8], ax
0x18000880a  jmp     loc_180008890
0x18000880f  call    cs:__imp_GetCurrentProcess
0x180008815  mov     rdi, [rsi+18h]
0x180008819  mov     rbx, rax
0x18000881c  call    cs:__imp_GetCurrentProcess
0x180008822  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18000882a  lea     r9, [r14+18h]; lpTargetHandle
0x18000882e  mov     rcx, rax; hSourceProcessHandle
0x180008831  mov     [rsp+78h+bInheritHandle], r12d; bInheritHandle
0x180008836  mov     r8, rbx; hTargetProcessHandle
0x180008839  mov     [rsp+78h+dwDesiredAccess], r12d; dwDesiredAccess
0x18000883e  mov     rdx, rdi; hSourceHandle
0x180008841  call    cs:__imp_DuplicateHandle
0x180008847  test    eax, eax
0x180008849  jz      short loc_1800088A5
0x18000884b  mov     rax, [rsi+8]
0x18000884f  mov     [r14+8], rax
0x180008853  mov     rax, [rsi+10h]
0x180008857  mov     [r14+10h], rax
0x18000885b  jmp     short loc_180008890
0x18000885d  mov     r8d, [rsi+10h]; dwBytes
0x180008861  xor     edx, edx; dwFlags
0x180008863  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x18000886a  call    cs:__imp_HeapAlloc
0x180008870  mov     [r14+8], rax
0x180008874  test    rax, rax
0x180008877  jz      short loc_1800088BD
0x180008879  mov     r8d, [rsi+10h]; Size
0x18000887d  mov     rcx, rax; void *
0x180008880  mov     rdx, [rsi+8]; Src
0x180008884  call    memcpy_0
0x180008889  mov     eax, [rsi+10h]
0x18000888c  mov     [r14+10h], eax
0x180008890  mov     eax, [rsi]
0x180008892  add     rsi, 20h ; ' '
0x180008896  mov     [r14], eax
0x180008899  add     r14, 20h ; ' '
0x18000889d  inc     r15d
0x1800088a0  jmp     loc_18000879F
0x1800088a5  call    cs:__imp_GetLastError
0x1800088ab  test    eax, eax
0x1800088ad  jle     short loc_1800088C2
0x1800088af  movzx   eax, ax
0x1800088b2  or      eax, 80070000h
0x1800088b7  jmp     short loc_1800088C2
0x1800088b9  xor     eax, eax
0x1800088bb  jmp     short loc_1800088C2
0x1800088bd  mov     eax, 80070008h
0x1800088c2  add     rsp, 40h
0x1800088c6  pop     r15
0x1800088c8  pop     r14
0x1800088ca  pop     r12
0x1800088cc  pop     rdi
0x1800088cd  pop     rsi
0x1800088ce  pop     rbp
0x1800088cf  pop     rbx
0x1800088d0  retn
```
