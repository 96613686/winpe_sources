# RESPONSE_ENTRY::~RESPONSE_ENTRY(void)

- ea: `0x180007b08`
- end: `0x180007d39`
- name: `??1RESPONSE_ENTRY@@AEAA@XZ`
- size: `561`
- prototype: `void __fastcall(RESPONSE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065c8`

## callees

- `0x180007b08`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ce4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ce4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cc2`

## pseudocode

```c
void __fastcall RESPONSE_ENTRY::~RESPONSE_ENTRY(RESPONSE_ENTRY *this)
{
  bool v1; // zf
  __int64 v3; // rbx
  __int64 v4; // rax
  volatile signed __int64 *v5; // rcx
  void *v6; // r8
  __int64 v7; // rbx
  unsigned int i; // esi
  void *v9; // r8
  void *v10; // r8
  void *v11; // r8
  __int64 j; // rbx
  void *v13; // r8
  __int64 v14; // rbx
  unsigned int k; // esi
  void *v16; // r8
  void *v17; // rcx
  void *v18; // r8
  void *v19; // r8

  v1 = *((_DWORD *)this + 3) == 0;
  *(_QWORD *)this = &RESPONSE_ENTRY::`vftable';
  if ( !v1 )
  {
    v3 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 21, 1);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 18, 1);
    v4 = *((unsigned int *)this + 146);
    v5 = (volatile signed __int64 *)g_pOutputCache;
    _InterlockedDecrement((volatile signed __int32 *)g_pOutputCache + 29);
    _InterlockedAdd64(v5 + 13, -v4);
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 8LL))(v3, 19, *((unsigned int *)this + 146));
  }
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = *((_QWORD *)this + 6);
  for ( i = 0; i < *((unsigned __int16 *)this + 20); ++i )
  {
    v9 = *(void **)(v7 + 8);
    if ( v9 )
    {
      HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v9);
      *(_QWORD *)(v7 + 8) = 0;
    }
    v10 = *(void **)(v7 + 16);
    if ( v10 )
    {
      HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v10);
      *(_QWORD *)(v7 + 16) = 0;
    }
    v7 += 24;
  }
  v11 = (void *)*((_QWORD *)this + 6);
  if ( v11 )
  {
    HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v11);
    *((_QWORD *)this + 6) = 0;
  }
  for ( j = 0; j != 30; ++j )
  {
    v13 = (void *)*((_QWORD *)this + 2 * j + 10);
    if ( v13 )
    {
      HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v13);
      *((_QWORD *)this + 2 * j + 10) = 0;
    }
  }
  v14 = *((_QWORD *)this + 70);
  for ( k = 0; k < *((unsigned __int16 *)this + 276); ++k )
  {
    if ( *(_DWORD *)v14 )
    {
      if ( *(_DWORD *)v14 == 1 )
      {
        v17 = *(void **)(v14 + 24);
        if ( v17 )
        {
          CloseHandle(v17);
          *(_QWORD *)(v14 + 24) = 0;
        }
      }
      else if ( *(_DWORD *)v14 == 2 )
      {
        v16 = *(void **)(v14 + 16);
        if ( v16 )
        {
          HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v16);
          *(_QWORD *)(v14 + 16) = 0;
        }
      }
    }
    else
    {
      v18 = *(void **)(v14 + 8);
      if ( v18 )
      {
        HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v18);
        *(_QWORD *)(v14 + 8) = 0;
      }
    }
    v14 += 32;
  }
  v19 = (void *)*((_QWORD *)this + 70);
  if ( v19 )
  {
    HeapFree(RESPONSE_ENTRY::sm_hHeap, 0, v19);
    *((_QWORD *)this + 70) = 0;
  }
}

```

## disassembly

```asm
0x180007b08  mov     [rsp+arg_0], rbx
0x180007b0d  mov     [rsp+arg_8], rsi
0x180007b12  push    rdi
0x180007b13  sub     rsp, 20h
0x180007b17  cmp     dword ptr [rcx+0Ch], 0
0x180007b1b  lea     rax, ??_7RESPONSE_ENTRY@@6B@; const RESPONSE_ENTRY::`vftable'
0x180007b22  mov     [rcx], rax
0x180007b25  mov     rdi, rcx
0x180007b28  jz      short loc_180007BA4
0x180007b2a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180007b31  mov     rax, [rcx]
0x180007b34  mov     rax, [rax+60h]
0x180007b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3d  mov     rbx, rax
0x180007b40  mov     edx, 15h
0x180007b45  mov     rcx, [rax]
0x180007b48  lea     r8d, [rdx-14h]
0x180007b4c  mov     rax, [rcx+8]
0x180007b50  mov     rcx, rbx
0x180007b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b58  mov     rcx, [rbx]
0x180007b5b  mov     edx, 12h
0x180007b60  mov     rax, [rcx+8]
0x180007b64  lea     r8d, [rdx-11h]
0x180007b68  mov     rcx, rbx
0x180007b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b70  mov     eax, [rdi+248h]
0x180007b76  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180007b7d  lock dec dword ptr [rcx+74h]
0x180007b81  neg     rax
0x180007b84  lock add [rcx+68h], rax
0x180007b89  mov     rax, [rbx]
0x180007b8c  mov     edx, 13h
0x180007b91  mov     r8d, [rdi+248h]
0x180007b98  mov     rcx, rbx
0x180007b9b  mov     rax, [rax+8]
0x180007b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba4  mov     r8, [rdi+20h]; lpMem
0x180007ba8  test    r8, r8
0x180007bab  jz      short loc_180007BC4
0x180007bad  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007bb4  xor     edx, edx; dwFlags
0x180007bb6  call    cs:__imp_HeapFree
0x180007bbc  mov     qword ptr [rdi+20h], 0
0x180007bc4  mov     rbx, [rdi+30h]
0x180007bc8  xor     esi, esi
0x180007bca  xor     eax, eax
0x180007bcc  cmp     ax, [rdi+28h]
0x180007bd0  jnb     short loc_180007C20
0x180007bd2  mov     r8, [rbx+8]; lpMem
0x180007bd6  test    r8, r8
0x180007bd9  jz      short loc_180007BF2
0x180007bdb  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007be2  xor     edx, edx; dwFlags
0x180007be4  call    cs:__imp_HeapFree
0x180007bea  mov     qword ptr [rbx+8], 0
0x180007bf2  mov     r8, [rbx+10h]; lpMem
0x180007bf6  test    r8, r8
0x180007bf9  jz      short loc_180007C12
0x180007bfb  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007c02  xor     edx, edx; dwFlags
0x180007c04  call    cs:__imp_HeapFree
0x180007c0a  mov     qword ptr [rbx+10h], 0
0x180007c12  movzx   eax, word ptr [rdi+28h]
0x180007c16  add     rbx, 18h
0x180007c1a  inc     esi
0x180007c1c  cmp     esi, eax
0x180007c1e  jb      short loc_180007BD2
0x180007c20  mov     r8, [rdi+30h]; lpMem
0x180007c24  test    r8, r8
0x180007c27  jz      short loc_180007C40
0x180007c29  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007c30  xor     edx, edx; dwFlags
0x180007c32  call    cs:__imp_HeapFree
0x180007c38  mov     qword ptr [rdi+30h], 0
0x180007c40  xor     ebx, ebx
0x180007c42  mov     rsi, rbx
0x180007c45  add     rsi, rsi
0x180007c48  mov     r8, [rdi+rsi*8+50h]; lpMem
0x180007c4d  test    r8, r8
0x180007c50  jz      short loc_180007C6A
0x180007c52  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007c59  xor     edx, edx; dwFlags
0x180007c5b  call    cs:__imp_HeapFree
0x180007c61  mov     qword ptr [rdi+rsi*8+50h], 0
0x180007c6a  inc     rbx
0x180007c6d  cmp     rbx, 1Eh
0x180007c71  jnz     short loc_180007C42
0x180007c73  mov     rbx, [rdi+230h]
0x180007c7a  xor     esi, esi
0x180007c7c  xor     eax, eax
0x180007c7e  cmp     ax, [rdi+228h]
0x180007c85  jnb     short loc_180007D03
0x180007c87  mov     ecx, [rbx]
0x180007c89  test    ecx, ecx
0x180007c8b  jz      short loc_180007CD2
0x180007c8d  sub     ecx, 1
0x180007c90  jz      short loc_180007CB9
0x180007c92  cmp     ecx, 1
0x180007c95  jnz     short loc_180007CF2
0x180007c97  mov     r8, [rbx+10h]; lpMem
0x180007c9b  test    r8, r8
0x180007c9e  jz      short loc_180007CF2
0x180007ca0  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007ca7  xor     edx, edx; dwFlags
0x180007ca9  call    cs:__imp_HeapFree
0x180007caf  mov     qword ptr [rbx+10h], 0
0x180007cb7  jmp     short loc_180007CF2
0x180007cb9  mov     rcx, [rbx+18h]; hObject
0x180007cbd  test    rcx, rcx
0x180007cc0  jz      short loc_180007CF2
0x180007cc2  call    cs:__imp_CloseHandle
0x180007cc8  mov     qword ptr [rbx+18h], 0
0x180007cd0  jmp     short loc_180007CF2
0x180007cd2  mov     r8, [rbx+8]; lpMem
0x180007cd6  test    r8, r8
0x180007cd9  jz      short loc_180007CF2
0x180007cdb  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007ce2  xor     edx, edx; dwFlags
0x180007ce4  call    cs:__imp_HeapFree
0x180007cea  mov     qword ptr [rbx+8], 0
0x180007cf2  movzx   eax, word ptr [rdi+228h]
0x180007cf9  add     rbx, 20h ; ' '
0x180007cfd  inc     esi
0x180007cff  cmp     esi, eax
0x180007d01  jb      short loc_180007C87
0x180007d03  mov     r8, [rdi+230h]; lpMem
0x180007d0a  test    r8, r8
0x180007d0d  jz      short loc_180007D29
0x180007d0f  mov     rcx, cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA; hHeap
0x180007d16  xor     edx, edx; dwFlags
0x180007d18  call    cs:__imp_HeapFree
0x180007d1e  mov     qword ptr [rdi+230h], 0
0x180007d29  mov     rbx, [rsp+28h+arg_0]
0x180007d2e  mov     rsi, [rsp+28h+arg_8]
0x180007d33  add     rsp, 20h
0x180007d37  pop     rdi
0x180007d38  retn
```
