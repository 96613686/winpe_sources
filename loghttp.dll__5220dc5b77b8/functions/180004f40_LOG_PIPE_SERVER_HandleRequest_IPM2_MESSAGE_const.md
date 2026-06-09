# LOG_PIPE_SERVER::HandleRequest(IPM2_MESSAGE const *)

- ea: `0x180004f40`
- end: `0x1800051c1`
- name: `?HandleRequest@LOG_PIPE_SERVER@@AEAAJPEBVIPM2_MESSAGE@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(LOG_PIPE_SERVER *__hidden this, const struct IPM2_MESSAGE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004ce0`

## callees

- `0x180004550`
- `0x180004f40`
- `0x180005420`
- `0x180005720`
- `0x180006010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800050e3`
- `msvcrt!_ultow_s` at `0x180005103`
- `msvcrt!_ultow_s` at `0x1800050e3`
- `msvcrt!_ultow_s` at `0x180005103`
- `msvcrt!_strtoui64` at `0x18000503f`
- `msvcrt!_strtoui64` at `0x18000505e`
- `msvcrt!_strtoui64` at `0x18000503f`
- `msvcrt!_strtoui64` at `0x18000505e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005015`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005015`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800050c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004fef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004faf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000518b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004faf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000518b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005180`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005199`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005180`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005199`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000512d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000512d`

## pseudocode

```c
__int64 __fastcall LOG_PIPE_SERVER::HandleRequest(LOG_PIPE_SERVER *this, const struct IPM2_MESSAGE *a2)
{
  __int64 v2; // rax
  const struct IPM2_MESSAGE *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rsi
  HANDLE v12; // rax
  _QWORD *v13; // r12
  unsigned int v14; // r13d
  const char *v15; // rbx
  __int64 v16; // rsi
  unsigned int *v17; // r14
  unsigned __int64 v18; // rax
  const char *v19; // rcx
  unsigned __int64 v20; // rbx
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // ecx
  void *v25; // rcx
  bool v26; // sf
  _QWORD *v27; // rax
  __int64 v28; // rdx
  DWORD CurrentProcessId; // eax
  __int64 i; // rdi
  void (__fastcall ***v31)(_QWORD, __int64); // rcx
  HANDLE v32; // rax
  HANDLE v33; // rax
  int v35; // [rsp+30h] [rbp-59h]
  struct MULTISZ *v36; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v37; // [rsp+40h] [rbp-49h]
  char *EndPtr; // [rsp+48h] [rbp-41h] BYREF
  const struct IPM2_MESSAGE *v39; // [rsp+50h] [rbp-39h]
  __int128 v40; // [rsp+58h] [rbp-31h] BYREF
  wchar_t Buffer[12]; // [rsp+68h] [rbp-21h] BYREF
  wchar_t v42[12]; // [rsp+80h] [rbp-9h] BYREF

  v2 = *(_QWORD *)a2;
  v3 = a2;
  v39 = a2;
  v4 = (*(__int64 (__fastcall **)(const struct IPM2_MESSAGE *))(v2 + 32))(a2);
  v5 = *(_QWORD *)v3;
  v6 = (unsigned int *)v4;
  v40 = 0;
  if ( (*(unsigned int (__fastcall **)(const struct IPM2_MESSAGE *))(v5 + 24))(v3) >= 0x22 )
  {
    v8 = *v6;
    v9 = 8LL * *v6;
    ProcessHeap = GetProcessHeap();
    v37 = HeapAlloc(ProcessHeap, 8u, v9);
    v11 = v37;
    if ( v37 )
    {
      v12 = GetProcessHeap();
      v13 = HeapAlloc(v12, 8u, v9);
      if ( v13 )
      {
        v14 = 0;
        v15 = (const char *)(v6 + 1);
        EnterCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
        v35 = 0;
        if ( v8 )
        {
          do
          {
            v16 = *(unsigned int *)v15;
            v17 = (unsigned int *)(v15 + 4);
            v36 = 0;
            v18 = _strtoui64(v15 + 4, 0, 16);
            v19 = v15 + 21;
            EndPtr = 0;
            v20 = v18;
            v21 = (void *)_strtoui64(v19, &EndPtr, 16);
            v22 = HTTP_LOG_HANDLER::QueryHttpCustomLog(v21, v20, &v36);
            v23 = v35;
            v24 = v14 + 1;
            v15 = (char *)v17 + v16;
            if ( v22 >= 0 )
              v24 = v14;
            v14 = v24;
            v13[v35] = v36;
            v25 = 0;
            v26 = v22 < 0;
            v27 = v37;
            if ( !v26 )
              v25 = v21;
            v37[v35++] = v25;
          }
          while ( v23 + 1 < v8 );
          v3 = v39;
          v11 = v27;
        }
        LeaveCriticalSection(&HTTP_LOG_HANDLER::sm_csLogDataListLock);
        if ( v14 )
        {
          _ultow_s(v14, Buffer, 0xBu, 10);
          *(_QWORD *)&v40 = Buffer;
          CurrentProcessId = GetCurrentProcessId();
          _ultow_s(CurrentProcessId, v42, 0xBu, 10);
          *((_QWORD *)&v40 + 1) = v42;
          EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, 0xC0000904, 2u, (const unsigned __int16 **const)&v40, 0);
        }
        v7 = LOG_PIPE_SERVER::RespondWithMultiString(v3, v28, v13, v8);
      }
      else
      {
        v7 = -2147024882;
      }
      for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
      {
        v31 = (void (__fastcall ***)(_QWORD, __int64))v11[i];
        if ( v31 )
        {
          (**v31)(v31, 1);
          v11[i] = 0;
        }
      }
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v11);
      if ( v13 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v13);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x180004f40  push    rbp
0x180004f42  push    rbx
0x180004f43  push    rsi
0x180004f44  push    rdi
0x180004f45  push    r12
0x180004f47  push    r13
0x180004f49  push    r14
0x180004f4b  push    r15
0x180004f4d  lea     rbp, [rsp-1Fh]
0x180004f52  sub     rsp, 0A8h
0x180004f59  mov     rax, cs:__security_cookie
0x180004f60  xor     rax, rsp
0x180004f63  mov     [rbp+57h+var_48], rax
0x180004f67  mov     rax, [rdx]
0x180004f6a  mov     rcx, rdx
0x180004f6d  mov     rdi, rdx
0x180004f70  mov     [rbp+57h+var_90], rdx
0x180004f74  mov     rax, [rax+20h]
0x180004f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7d  mov     rcx, [rdi]
0x180004f80  mov     r14, rax
0x180004f83  xorps   xmm0, xmm0
0x180004f86  movups  [rbp+57h+var_88], xmm0
0x180004f8a  mov     rax, [rcx+18h]
0x180004f8e  mov     rcx, rdi
0x180004f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f96  cmp     eax, 22h ; '"'
0x180004f99  jnb     short loc_180004FA5
0x180004f9b  mov     ebx, 80070057h
0x180004fa0  jmp     loc_18000519F
0x180004fa5  mov     r15d, [r14]
0x180004fa8  mov     ebx, r15d
0x180004fab  shl     rbx, 3
0x180004faf  call    cs:__imp_GetProcessHeap
0x180004fb5  mov     r12d, 8
0x180004fbb  mov     r8, rbx; dwBytes
0x180004fbe  mov     rcx, rax; hHeap
0x180004fc1  mov     edx, r12d; dwFlags
0x180004fc4  call    cs:__imp_HeapAlloc
0x180004fca  mov     [rbp+57h+var_A0], rax
0x180004fce  mov     rsi, rax
0x180004fd1  test    rax, rax
0x180004fd4  jnz     short loc_180004FE0
0x180004fd6  mov     ebx, 8007000Eh
0x180004fdb  jmp     loc_18000519F
0x180004fe0  call    cs:__imp_GetProcessHeap
0x180004fe6  mov     r8, rbx; dwBytes
0x180004fe9  mov     edx, r12d; dwFlags
0x180004fec  mov     rcx, rax; hHeap
0x180004fef  call    cs:__imp_HeapAlloc
0x180004ff5  mov     r12, rax
0x180004ff8  test    rax, rax
0x180004ffb  jnz     short loc_180005007
0x180004ffd  mov     ebx, 8007000Eh
0x180005002  jmp     loc_180005143
0x180005007  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000500e  xor     r13d, r13d
0x180005011  lea     rbx, [r14+4]
0x180005015  call    cs:__imp_EnterCriticalSection
0x18000501b  mov     [rbp+57h+var_B0], r13d
0x18000501f  test    r15d, r15d
0x180005022  jz      loc_1800050BA
0x180005028  mov     esi, [rbx]
0x18000502a  lea     r14, [rbx+4]
0x18000502e  xor     edx, edx; EndPtr
0x180005030  mov     [rbp+57h+var_A8], 0
0x180005038  mov     rcx, r14; String
0x18000503b  lea     r8d, [rdx+10h]; Radix
0x18000503f  call    cs:__imp__strtoui64
0x180005045  lea     rcx, [r14+11h]; String
0x180005049  mov     [rbp+57h+EndPtr], 0
0x180005051  mov     r8d, 10h; Radix
0x180005057  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x18000505b  mov     rbx, rax
0x18000505e  call    cs:__imp__strtoui64
0x180005064  lea     r8, [rbp+57h+var_A8]; struct MULTISZ **
0x180005068  mov     rdx, rbx; unsigned __int64
0x18000506b  mov     rcx, rax; void *
0x18000506e  mov     rdi, rax
0x180005071  call    ?QueryHttpCustomLog@HTTP_LOG_HANDLER@@SAJPEAX_KPEAPEAVMULTISZ@@@Z; HTTP_LOG_HANDLER::QueryHttpCustomLog(void *,unsigned __int64,MULTISZ * *)
0x180005076  mov     r8d, [rbp+57h+var_B0]
0x18000507a  lea     ecx, [r13+1]
0x18000507e  test    eax, eax
0x180005080  lea     rbx, [r14+rsi]
0x180005084  cmovns  ecx, r13d
0x180005088  mov     r13d, ecx
0x18000508b  mov     rcx, [rbp+57h+var_A8]
0x18000508f  mov     [r12+r8*8], rcx
0x180005093  xor     ecx, ecx
0x180005095  test    eax, eax
0x180005097  mov     rax, [rbp+57h+var_A0]
0x18000509b  cmovns  rcx, rdi
0x18000509f  mov     [rax+r8*8], rcx
0x1800050a3  inc     r8d
0x1800050a6  mov     [rbp+57h+var_B0], r8d
0x1800050aa  cmp     r8d, r15d
0x1800050ad  jb      loc_180005028
0x1800050b3  mov     rdi, [rbp+57h+var_90]
0x1800050b7  mov     rsi, rax
0x1800050ba  lea     rcx, ?sm_csLogDataListLock@HTTP_LOG_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800050c1  call    cs:__imp_LeaveCriticalSection
0x1800050c7  test    r13d, r13d
0x1800050ca  jz      short loc_180005133
0x1800050cc  mov     r14d, 0Ah
0x1800050d2  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800050d6  mov     r9d, r14d; Radix
0x1800050d9  mov     ecx, r13d; Value
0x1800050dc  lea     ebx, [r14+1]
0x1800050e0  mov     r8d, ebx; BufferCount
0x1800050e3  call    cs:__imp__ultow_s
0x1800050e9  lea     rax, [rbp+57h+Buffer]
0x1800050ed  mov     qword ptr [rbp+57h+var_88], rax
0x1800050f1  call    cs:__imp_GetCurrentProcessId
0x1800050f7  mov     r9d, r14d; Radix
0x1800050fa  lea     rdx, [rbp+57h+var_60]; Buffer
0x1800050fe  mov     ecx, eax; Value
0x180005100  mov     r8d, ebx; BufferCount
0x180005103  call    cs:__imp__ultow_s
0x180005109  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x180005110  lea     rax, [rbp+57h+var_60]
0x180005114  lea     r8d, [r14-8]
0x180005118  mov     qword ptr [rbp+57h+var_88+8], rax
0x18000511c  lea     r9, [rbp+57h+var_88]
0x180005120  mov     [rsp+0E0h+var_C0], 0
0x180005128  mov     edx, 0C0000904h
0x18000512d  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180005133  mov     r9d, r15d
0x180005136  mov     r8, r12
0x180005139  mov     rcx, rdi
0x18000513c  call    ?RespondWithMultiString@LOG_PIPE_SERVER@@CAJPEBVIPM2_MESSAGE@@W4IPM2_OPCODE@@PEAPEAVMULTISZ@@K@Z; LOG_PIPE_SERVER::RespondWithMultiString(IPM2_MESSAGE const *,IPM2_OPCODE,MULTISZ * *,ulong)
0x180005141  mov     ebx, eax
0x180005143  xor     edi, edi
0x180005145  test    r15d, r15d
0x180005148  jz      short loc_180005172
0x18000514a  mov     rcx, [rsi+rdi*8]
0x18000514e  test    rcx, rcx
0x180005151  jz      short loc_18000516B
0x180005153  mov     rax, [rcx]
0x180005156  mov     edx, 1
0x18000515b  mov     rax, [rax]
0x18000515e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005163  mov     qword ptr [rsi+rdi*8], 0
0x18000516b  inc     edi
0x18000516d  cmp     edi, r15d
0x180005170  jb      short loc_18000514A
0x180005172  call    cs:__imp_GetProcessHeap
0x180005178  mov     r8, rsi; lpMem
0x18000517b  xor     edx, edx; dwFlags
0x18000517d  mov     rcx, rax; hHeap
0x180005180  call    cs:__imp_HeapFree
0x180005186  test    r12, r12
0x180005189  jz      short loc_18000519F
0x18000518b  call    cs:__imp_GetProcessHeap
0x180005191  mov     r8, r12; lpMem
0x180005194  xor     edx, edx; dwFlags
0x180005196  mov     rcx, rax; hHeap
0x180005199  call    cs:__imp_HeapFree
0x18000519f  mov     eax, ebx
0x1800051a1  mov     rcx, [rbp+57h+var_48]
0x1800051a5  xor     rcx, rsp; StackCookie
0x1800051a8  call    __security_check_cookie
0x1800051ad  add     rsp, 0A8h
0x1800051b4  pop     r15
0x1800051b6  pop     r14
0x1800051b8  pop     r13
0x1800051ba  pop     r12
0x1800051bc  pop     rdi
0x1800051bd  pop     rsi
0x1800051be  pop     rbx
0x1800051bf  pop     rbp
0x1800051c0  retn
```
