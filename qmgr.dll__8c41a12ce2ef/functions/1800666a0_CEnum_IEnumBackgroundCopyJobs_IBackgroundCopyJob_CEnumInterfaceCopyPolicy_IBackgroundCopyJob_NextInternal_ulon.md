# CEnum<IEnumBackgroundCopyJobs,IBackgroundCopyJob *,CEnumInterfaceCopyPolicy<IBackgroundCopyJob>>::NextInternal(ulong,IBackgroundCopyJob * * const,ulong *)

- ea: `0x1800666a0`
- end: `0x180066934`
- name: `?NextInternal@?$CEnum@UIEnumBackgroundCopyJobs@@PEAUIBackgroundCopyJob@@V?$CEnumInterfaceCopyPolicy@UIBackgroundCopyJob@@@@@@QEAAJKQEAPEAUIBackgroundCopyJob@@PEAK@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800665f0`

## callees

- `0x1800666a0`
- `0x180097318`
- `0x180098fa4`
- `0x18009d024`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800666f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800666f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066732`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006670e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006670e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066903`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066903`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066726`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066726`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CEnum<IEnumBackgroundCopyJobs,IBackgroundCopyJob *,CEnumInterfaceCopyPolicy<IBackgroundCopyJob>>::NextInternal(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int *a4)
{
  int *v4; // rsi
  __int64 v6; // rbx
  _QWORD *v7; // r14
  __int64 v8; // rdi
  __int64 v9; // r8
  int v10; // r13d
  int v11; // r15d
  int v12; // r12d
  __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  BOOL v17; // edi
  void *v18; // rdx
  int v21; // [rsp+50h] [rbp-138h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-130h]
  int v23; // [rsp+60h] [rbp-128h]
  void **pExceptionObject; // [rsp+80h] [rbp-108h] BYREF
  __int128 v28; // [rsp+88h] [rbp-100h]
  int v29; // [rsp+98h] [rbp-F0h]
  int v30; // [rsp+9Ch] [rbp-ECh]
  int v31; // [rsp+A0h] [rbp-E8h]
  void **v32; // [rsp+E0h] [rbp-A8h] BYREF
  _DWORD v33[22]; // [rsp+E8h] [rbp-A0h] BYREF

  v4 = a4;
  v6 = a2;
  v7 = (_QWORD *)a1;
  v8 = a1 + 56;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 56);
  if ( *(_DWORD *)(a1 + 112) == GetCurrentThreadId() )
  {
    v10 = 0;
    v23 = 0;
    v11 = 1;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v8);
    ++*(_DWORD *)(v8 + 52);
    while ( *(_DWORD *)(v8 + 48) )
      WaitForSingleObject(*(HANDLE *)(v8 + 40), 0xFFFFFFFF);
    *(_DWORD *)(v8 + 56) = GetCurrentThreadId();
    v11 = 1;
    v10 = 1;
    v23 = 1;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_qDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids,
      v7,
      v6,
      a3,
      v4);
  v12 = 0;
  if ( (_DWORD)v6 )
    memset_0(a3, 0, 8 * v6);
  try
  {
    if ( !v4 && (_DWORD)v6 != 1 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids);
      v28 = 0;
      pExceptionObject = &ComError::`vftable';
      v29 = -2147024809;
      v30 = 0;
      v31 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v13 = 0;
    while ( (unsigned int)v13 < (unsigned int)v6 )
    {
      v14 = v7[15];
      v15 = v7[18];
      if ( v15 >= (v7[16] - v14) >> 3 )
        break;
      v16 = *(_QWORD *)(v14 + 8 * v15);
      *((_QWORD *)a3 + v13) = v16;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      ++v12;
      v13 = (unsigned int)(v13 + 1);
      ++v7[18];
    }
    if ( v4 )
      *v4 = v12;
    v17 = v12 != v6;
  }
  catch ( ComError v32 )
  {
    v21 = v33[4];
    v32 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(v33);
    v11 = 1;
    LODWORD(v6) = a2;
    v17 = v21;
    v10 = v23;
    v7 = (_QWORD *)a1;
    v18 = a3;
    v4 = a4;
    goto LABEL_25;
  }
  v18 = a3;
LABEL_25:
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( v4 )
      v11 = *v4;
    WPP_SF_qDDqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v9, v7, v17, v6, v18, v4, v11);
  }
  for ( ; v10; --v10 )
  {
    --lpCriticalSection[1].RecursionCount;
    LODWORD(lpCriticalSection[1].OwningThread) = 0;
    LeaveCriticalSection(lpCriticalSection);
  }
  return v17;
}

```

## disassembly

```asm
0x1800666a0  mov     [rsp+arg_8], edx
0x1800666a4  push    rbx
0x1800666a5  push    rsi
0x1800666a6  push    rdi
0x1800666a7  push    r12
0x1800666a9  push    r13
0x1800666ab  push    r14
0x1800666ad  push    r15
0x1800666af  sub     rsp, 150h
0x1800666b6  mov     rax, cs:__security_cookie
0x1800666bd  xor     rax, rsp
0x1800666c0  mov     [rsp+188h+var_48], rax
0x1800666c8  mov     rsi, r9
0x1800666cb  mov     r12, r8
0x1800666ce  mov     [rsp+188h+var_138], r8
0x1800666d3  mov     ebx, edx
0x1800666d5  mov     r14, rcx
0x1800666d8  mov     [rsp+188h+var_120], rcx
0x1800666dd  mov     [rsp+188h+var_118], r8
0x1800666e2  mov     [rsp+188h+var_110], r9
0x1800666e7  lea     rdi, [rcx+38h]
0x1800666eb  mov     [rsp+188h+lpCriticalSection], rdi
0x1800666f0  call    cs:__imp_GetCurrentThreadId
0x1800666f6  cmp     [rdi+38h], eax
0x1800666f9  jnz     short loc_18006670B
0x1800666fb  xor     r13d, r13d
0x1800666fe  mov     [rsp+188h+var_128], r13d
0x180066703  mov     r15d, 1
0x180066709  jmp     short loc_180066749
0x18006670b  mov     rcx, rdi; lpCriticalSection
0x18006670e  call    cs:__imp_EnterCriticalSection
0x180066714  inc     dword ptr [rdi+34h]
0x180066717  cmp     dword ptr [rdi+30h], 0
0x18006671b  jz      short loc_180066732
0x18006671d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180066722  mov     rcx, [rdi+28h]; hHandle
0x180066726  call    cs:__imp_WaitForSingleObject
0x18006672c  cmp     dword ptr [rdi+30h], 0
0x180066730  jnz     short loc_18006671D
0x180066732  call    cs:__imp_GetCurrentThreadId
0x180066738  mov     [rdi+38h], eax
0x18006673b  mov     r15d, 1
0x180066741  mov     r13d, r15d
0x180066744  mov     [rsp+188h+var_128], r15d
0x180066749  lea     rdi, WPP_GLOBAL_Control
0x180066750  mov     rcx, cs:WPP_GLOBAL_Control
0x180066757  cmp     rcx, rdi
0x18006675a  jz      short loc_180066788
0x18006675c  test    byte ptr [rcx+1Ch], 8
0x180066760  jz      short loc_180066788
0x180066762  mov     edx, 0Bh
0x180066767  mov     [rsp+188h+var_158], rsi
0x18006676c  mov     [rsp+188h+var_160], r12
0x180066771  mov     [rsp+188h+var_168], ebx
0x180066775  mov     r9, r14
0x180066778  lea     r8, WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids
0x18006677f  mov     rcx, [rcx+10h]
0x180066783  call    WPP_SF_qDqq
0x180066788  xor     r12d, r12d
0x18006678b  test    ebx, ebx
0x18006678d  jz      short loc_1800667A2
0x18006678f  mov     r8, rbx
0x180066792  shl     r8, 3; Size
0x180066796  xor     edx, edx; Val
0x180066798  mov     rcx, [rsp+188h+var_138]; void *
0x18006679d  call    memset_0
0x1800667a2  test    rsi, rsi
0x1800667a5  jnz     short loc_18006681F
0x1800667a7  cmp     ebx, 1
0x1800667aa  jz      short loc_18006681F
0x1800667ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800667b3  cmp     rcx, rdi
0x1800667b6  jz      short loc_1800667D3
0x1800667b8  test    byte ptr [rcx+1Ch], 2
0x1800667bc  jz      short loc_1800667D3
0x1800667be  mov     edx, 0Ch
0x1800667c3  lea     r8, WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids
0x1800667ca  mov     rcx, [rcx+10h]
0x1800667ce  call    WPP_SF_
0x1800667d3  xorps   xmm0, xmm0
0x1800667d6  movups  [rsp+188h+var_100], xmm0
0x1800667de  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800667e5  mov     [rsp+188h+pExceptionObject], rax
0x1800667ed  mov     [rsp+188h+var_F0], 80070057h
0x1800667f8  mov     [rsp+188h+var_EC], 0
0x180066803  mov     [rsp+188h+var_E8], r15d
0x18006680b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180066812  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18006681a  call    _CxxThrowException_0
0x18006681f  xor     edi, edi
0x180066821  cmp     edi, ebx
0x180066823  jnb     short loc_18006686A
0x180066825  mov     rcx, [r14+78h]
0x180066829  mov     rdx, [r14+90h]
0x180066830  mov     rax, [r14+80h]
0x180066837  sub     rax, rcx
0x18006683a  sar     rax, 3
0x18006683e  cmp     rdx, rax
0x180066841  jnb     short loc_18006686A
0x180066843  mov     rcx, [rcx+rdx*8]
0x180066847  mov     rdx, [rsp+188h+var_138]
0x18006684c  mov     [rdx+rdi*8], rcx
0x180066850  mov     rax, [rcx]
0x180066853  mov     rax, [rax+8]
0x180066857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006685c  inc     r12d
0x18006685f  inc     edi
0x180066861  inc     qword ptr [r14+90h]
0x180066868  jmp     short loc_180066821
0x18006686a  test    rsi, rsi
0x18006686d  jz      short loc_180066872
0x18006686f  mov     [rsi], r12d
0x180066872  xor     edi, edi
0x180066874  cmp     r12d, ebx
0x180066877  setnz   dil
0x18006687b  mov     rdx, [rsp+188h+var_138]
0x180066880  jmp     short loc_1800668A7
0x180066882  mov     r15d, 1
0x180066888  mov     ebx, [rsp+188h+arg_8]
0x18006688f  mov     edi, dword ptr [rsp+188h+var_138]
0x180066893  mov     r13d, [rsp+188h+var_128]
0x180066898  mov     r14, [rsp+188h+var_120]
0x18006689d  mov     rdx, [rsp+188h+var_118]
0x1800668a2  mov     rsi, [rsp+188h+var_110]
0x1800668a7  lea     rax, WPP_GLOBAL_Control
0x1800668ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800668b5  cmp     rcx, rax
0x1800668b8  jz      short loc_1800668EC
0x1800668ba  test    byte ptr [rcx+1Ch], 8
0x1800668be  jz      short loc_1800668EC
0x1800668c0  test    rsi, rsi
0x1800668c3  jz      short loc_1800668C8
0x1800668c5  mov     r15d, [rsi]
0x1800668c8  mov     [rsp+188h+var_148], r15d
0x1800668cd  mov     [rsp+188h+var_150], rsi
0x1800668d2  mov     [rsp+188h+var_158], rdx
0x1800668d7  mov     dword ptr [rsp+188h+var_160], ebx
0x1800668db  mov     [rsp+188h+var_168], edi
0x1800668df  mov     r9, r14
0x1800668e2  mov     rcx, [rcx+10h]
0x1800668e6  call    WPP_SF_qDDqqD
0x1800668eb  nop
0x1800668ec  test    r13d, r13d
0x1800668ef  jz      short loc_18006690F
0x1800668f1  mov     rbx, [rsp+188h+lpCriticalSection]
0x1800668f6  dec     dword ptr [rbx+34h]
0x1800668f9  mov     dword ptr [rbx+38h], 0
0x180066900  mov     rcx, rbx; lpCriticalSection
0x180066903  call    cs:__imp_LeaveCriticalSection
0x180066909  sub     r13d, 1
0x18006690d  jnz     short loc_1800668F6
0x18006690f  mov     eax, edi
0x180066911  mov     rcx, [rsp+188h+var_48]
0x180066919  xor     rcx, rsp; StackCookie
0x18006691c  call    __security_check_cookie
0x180066921  add     rsp, 150h
0x180066928  pop     r15
0x18006692a  pop     r14
0x18006692c  pop     r13
0x18006692e  pop     r12
0x180066930  pop     rdi
0x180066931  pop     rsi
0x180066932  pop     rbx
0x180066933  retn
```
