# DoStackCapture(long,uint,void *)

- ea: `0x180003380`
- end: `0x1800034ad`
- name: `?DoStackCapture@@YAXJIPEAX@Z`
- size: `301`
- prototype: `void __fastcall(int, unsigned int, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003370`
- `0x18000352c`
- `0x180005238`

## callees

- `0x180003380`
- `0x1800034c0`
- `0x180003504`
- `0x180003510`
- `0x18000d0a0`

## import_xrefs

- `ntdll!RtlCaptureStackBackTrace` at `0x180003437`
- `ntdll!RtlCaptureStackBackTrace` at `0x180003437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800033ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800033ee`

## pseudocode

```c
void __fastcall DoStackCapture(int a1, int a2, void *a3)
{
  volatile int v6; // r8d
  __int64 v7; // r9
  struct StackCaptureFrame near **v8; // rbx
  DWORD CurrentThreadId; // eax
  __m128i *v10; // rdi
  PVOID *v11; // rbx
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  __m128i si128; // xmm0
  PVOID BackTrace[2]; // [rsp+20h] [rbp-98h] BYREF
  __int128 v16; // [rsp+30h] [rbp-88h]
  __int128 v17; // [rsp+40h] [rbp-78h]
  __int128 v18; // [rsp+50h] [rbp-68h]
  __int128 v19; // [rsp+60h] [rbp-58h]
  __int64 v20; // [rsp+70h] [rbp-48h]

  EnsureStackCaptureRegisteredWithWER();
  do
  {
    v6 = g_nCurrentStackCaptureIndex;
    v7 = (unsigned __int8)(g_nCurrentStackCaptureIndex + 1);
  }
  while ( v6 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v7, g_nCurrentStackCaptureIndex) );
  v8 = &g_StackCaptureFrames + 6 * v7;
  *(_DWORD *)v8 = a1;
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)v8 + 2) = a2;
  *((_DWORD *)v8 + 1) = CurrentThreadId;
  QueryPerformanceCounter((LARGE_INTEGER *)v8 + 2);
  v10 = (__m128i *)(v8 + 3);
  v20 = 0;
  *(_OWORD *)(v8 + 3) = 0;
  v8[5] = 0;
  *(_OWORD *)BackTrace = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v11 = &BackTrace[RtlCaptureStackBackTrace(1u, 0xBu, BackTrace, 0)];
  v12 = std::_Find_vectorized<void *,void *>(BackTrace, v11, a3);
  v13 = ((__int64)v11 - v12) >> 3;
  if ( v13 > 3 )
  {
    v13 = 3;
LABEL_5:
    std::_Copy_memmove_n<void * *,void * *>(v12, v13, v10);
    return;
  }
  if ( v13 )
    goto LABEL_5;
  si128 = _mm_load_si128((const __m128i *)&_xmm_e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0);
  *v10 = si128;
  v10[1].m128i_i64[0] = si128.m128i_i64[0];
}

```

## disassembly

```asm
0x180003380  push    rbx
0x180003382  push    rbp
0x180003383  push    rsi
0x180003384  push    rdi
0x180003385  sub     rsp, 98h
0x18000338c  mov     rax, cs:__security_cookie
0x180003393  xor     rax, rsp
0x180003396  mov     [rsp+0B8h+var_38], rax
0x18000339e  mov     rbp, r8
0x1800033a1  mov     edi, edx
0x1800033a3  mov     esi, ecx
0x1800033a5  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x1800033aa  mov     r8d, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800033b1  lea     eax, [r8+1]
0x1800033b5  movzx   r9d, al
0x1800033b9  mov     eax, r8d
0x1800033bc  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, r9d; long volatile g_nCurrentStackCaptureIndex
0x1800033c5  cmp     r8d, eax
0x1800033c8  jnz     short loc_1800033AA
0x1800033ca  lea     rbx, [r9+r9*2]
0x1800033ce  lea     rax, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x1800033d5  shl     rbx, 4
0x1800033d9  add     rbx, rax
0x1800033dc  mov     [rbx], esi
0x1800033de  call    cs:__imp_GetCurrentThreadId
0x1800033e4  lea     rcx, [rbx+10h]; lpPerformanceCount
0x1800033e8  mov     [rbx+8], edi
0x1800033eb  mov     [rbx+4], eax
0x1800033ee  call    cs:__imp_QueryPerformanceCounter
0x1800033f4  xorps   xmm1, xmm1
0x1800033f7  lea     rdi, [rbx+18h]
0x1800033fb  xor     eax, eax
0x1800033fd  lea     r8, [rsp+0B8h+BackTrace]; BackTrace
0x180003402  xorps   xmm0, xmm0
0x180003405  mov     [rsp+0B8h+var_48], rax
0x18000340a  movups  xmmword ptr [rdi], xmm0
0x18000340d  xor     r9d, r9d; BackTraceHash
0x180003410  mov     [rdi+10h], rax
0x180003414  mov     edx, 0Bh; FramesToCapture
0x180003419  mov     ecx, 1; FramesToSkip
0x18000341e  movups  xmmword ptr [rsp+0B8h+BackTrace], xmm1
0x180003423  movups  [rsp+0B8h+var_88], xmm1
0x180003428  movups  [rsp+0B8h+var_78], xmm1
0x18000342d  movups  [rsp+0B8h+var_68], xmm1
0x180003432  movups  [rsp+0B8h+var_58], xmm1
0x180003437  call    cs:__imp_RtlCaptureStackBackTrace
0x18000343d  movzx   eax, ax
0x180003440  lea     rbx, [rsp+0B8h+BackTrace]
0x180003445  mov     r8, rbp
0x180003448  lea     rcx, [rsp+0B8h+BackTrace]
0x18000344d  lea     rbx, [rbx+rax*8]
0x180003451  mov     rdx, rbx
0x180003454  call    ??$_Find_vectorized@PEAXPEAX@std@@YAPEAPEAXQEAPEAX0QEAX@Z; std::_Find_vectorized<void *,void *>(void * * const,void * * const,void * const)
0x180003459  sub     rbx, rax
0x18000345c  sar     rbx, 3
0x180003460  cmp     rbx, 3
0x180003464  jbe     short loc_180003495
0x180003466  mov     ebx, 3
0x18000346b  mov     r8, rdi
0x18000346e  mov     rdx, rbx
0x180003471  mov     rcx, rax
0x180003474  call    ??$_Copy_memmove_n@PEAPEAXPEAPEAX@std@@YAPEAPEAXPEAPEAX_K0@Z; std::_Copy_memmove_n<void * *,void * *>(void * *,unsigned __int64,void * *)
0x180003479  mov     rcx, [rsp+0B8h+var_38]
0x180003481  xor     rcx, rsp; StackCookie
0x180003484  call    __security_check_cookie
0x180003489  add     rsp, 98h
0x180003490  pop     rdi
0x180003491  pop     rsi
0x180003492  pop     rbp
0x180003493  pop     rbx
0x180003494  retn
0x180003495  test    rbx, rbx
0x180003498  jnz     short loc_18000346B
0x18000349a  movdqa  xmm0, cs:__xmm@e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0e0
0x1800034a2  movups  xmmword ptr [rdi], xmm0
0x1800034a5  movq    qword ptr [rdi+10h], xmm0
0x1800034ab  jmp     short loc_180003479
```
