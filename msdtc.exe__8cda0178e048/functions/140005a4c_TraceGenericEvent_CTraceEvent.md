# TraceGenericEvent(CTraceEvent &)

- ea: `0x140005a4c`
- end: `0x140005d03`
- name: `?TraceGenericEvent@@YAXAEAVCTraceEvent@@@Z`
- size: `695`
- prototype: `void __fastcall(struct CTraceEvent *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1400056c0`

## callees

- `0x140001290`
- `0x1400012d0`
- `0x1400019cf`
- `0x140005a4c`
- `0x140006b68`
- `0x140006f10`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140005cae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140005cae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ad8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ae5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ad8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005aff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005af2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005af2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005c4e`

## pseudocode

```c
void __fastcall TraceGenericEvent(struct CTraceEvent *a1)
{
  int v2; // eax
  __int64 v3; // rsi
  void *v4; // rax
  _QWORD *v5; // rdi
  unsigned int v6; // r8d
  signed int v7; // ebp
  unsigned int i; // r14d
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 v10; // r12
  __int64 v11; // rdi
  unsigned int v12; // r8d
  _QWORD *v13; // r9
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  int v15; // eax
  LPCWSTR v16; // rdi
  char v17; // si
  __int64 v18; // rdx
  _QWORD *j; // rbx
  LPCWSTR lpOutputString[2]; // [rsp+20h] [rbp-448h] BYREF
  _BYTE v21[1024]; // [rsp+30h] [rbp-438h] BYREF

  if ( TraceOutputSettings::DebugOutEnabled )
  {
    EnterCriticalSection(&stru_1400106E8);
    lpOutputString[0] = (LPCWSTR)v21;
    v2 = (*(__int64 (__fastcall **)(struct CTraceEvent *, _BYTE *, __int64))(*(_QWORD *)a1 + 16LL))(a1, v21, 512);
    if ( v2 == -2147024774 )
      v2 = (*(__int64 (__fastcall **)(struct CTraceEvent *, LPCWSTR *))(*(_QWORD *)a1 + 8LL))(a1, lpOutputString);
    if ( v2 >= 0 )
    {
      OutputDebugStringW(lpOutputString[0]);
      OutputDebugStringW(L"\n");
    }
    LeaveCriticalSection(&stru_1400106E8);
  }
  EnterCriticalSection(&stru_140010758);
  v3 = TraceOutputSettings::MemoryBufferSize;
  if ( CTraceMemoryBuffer::cMemoryBuffer == TraceOutputSettings::MemoryBufferSize
    || (v4 = operator new(saturated_mul(TraceOutputSettings::MemoryBufferSize, 8u)), (v5 = v4) == 0) )
  {
    v5 = CTraceMemoryBuffer::MemoryBuffer;
  }
  else
  {
    memset_0(v4, 0, 8 * v3);
    v6 = CTraceMemoryBuffer::cMemoryBuffer;
    v7 = 0;
    for ( i = 0; i < v6; v7 = (v7 + 1) % (unsigned int)v3 )
    {
      v9 = (void (__fastcall ***)(_QWORD, __int64))v5[v7];
      v10 = (i + CTraceMemoryBuffer::iMemoryBuffer) % v6;
      if ( v9 )
      {
        (**v9)(v9, 1);
        v6 = CTraceMemoryBuffer::cMemoryBuffer;
      }
      ++i;
      v5[v7] = *((_QWORD *)CTraceMemoryBuffer::MemoryBuffer + v10);
    }
    operator delete(CTraceMemoryBuffer::MemoryBuffer);
    CTraceMemoryBuffer::MemoryBuffer = v5;
    CTraceMemoryBuffer::cMemoryBuffer = v3;
    CTraceMemoryBuffer::iMemoryBuffer = v7;
  }
  if ( v5 )
  {
    v11 = (*(__int64 (__fastcall **)(struct CTraceEvent *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( v11 )
    {
      v12 = CTraceMemoryBuffer::iMemoryBuffer;
      v13 = CTraceMemoryBuffer::MemoryBuffer;
      v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)CTraceMemoryBuffer::MemoryBuffer
                                                    + CTraceMemoryBuffer::iMemoryBuffer);
      if ( v14 )
      {
        (**v14)(v14, 1);
        v12 = CTraceMemoryBuffer::iMemoryBuffer;
        v13 = CTraceMemoryBuffer::MemoryBuffer;
      }
      v13[v12] = v11;
      CTraceMemoryBuffer::iMemoryBuffer = (v12 + 1) % CTraceMemoryBuffer::cMemoryBuffer;
    }
  }
  LeaveCriticalSection(&stru_140010758);
  TraceEventToFile(a1);
  lpOutputString[0] = (LPCWSTR)v21;
  v15 = (*(__int64 (__fastcall **)(struct CTraceEvent *, _BYTE *, __int64))(*(_QWORD *)a1 + 16LL))(a1, v21, 512);
  if ( v15 == -2147024774 )
    v15 = (*(__int64 (__fastcall **)(struct CTraceEvent *, LPCWSTR *))(*(_QWORD *)a1 + 8LL))(a1, lpOutputString);
  if ( v15 >= 0 )
  {
    v16 = lpOutputString[0];
    v17 = *((_BYTE *)a1 + 32);
    for ( j = TlsGetValue(g_TraceTls); j; j = (_QWORD *)j[2] )
    {
      LOBYTE(v18) = v17;
      ((void (__fastcall *)(_QWORD, __int64, LPCWSTR))*j)(j[1], v18, v16);
    }
  }
}

```

## disassembly

```asm
0x140005a4c  mov     [rsp+arg_8], rbx
0x140005a51  mov     [rsp+arg_10], rbp
0x140005a56  push    rsi
0x140005a57  push    rdi
0x140005a58  push    r12
0x140005a5a  push    r14
0x140005a5c  push    r15
0x140005a5e  sub     rsp, 440h
0x140005a65  mov     rax, cs:__security_cookie
0x140005a6c  xor     rax, rsp
0x140005a6f  mov     [rsp+468h+var_38], rax
0x140005a77  cmp     cs:?DebugOutEnabled@TraceOutputSettings@@2_NA, 0; bool TraceOutputSettings::DebugOutEnabled
0x140005a7e  mov     rbx, rcx
0x140005a81  jz      short loc_140005AF8
0x140005a83  lea     rcx, stru_1400106E8; lpCriticalSection
0x140005a8a  call    cs:__imp_EnterCriticalSection
0x140005a90  lea     rax, [rsp+468h+var_438]
0x140005a95  mov     r8d, 200h
0x140005a9b  mov     [rsp+468h+lpOutputString], rax
0x140005aa0  lea     rdx, [rsp+468h+var_438]
0x140005aa5  mov     rax, [rbx]
0x140005aa8  mov     rcx, rbx
0x140005aab  mov     rax, [rax+10h]
0x140005aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ab4  cmp     eax, 8007007Ah
0x140005ab9  jnz     short loc_140005ACF
0x140005abb  mov     rax, [rbx]
0x140005abe  lea     rdx, [rsp+468h+lpOutputString]
0x140005ac3  mov     rcx, rbx
0x140005ac6  mov     rax, [rax+8]
0x140005aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005acf  test    eax, eax
0x140005ad1  js      short loc_140005AEB
0x140005ad3  mov     rcx, [rsp+468h+lpOutputString]; lpOutputString
0x140005ad8  call    cs:__imp_OutputDebugStringW
0x140005ade  lea     rcx, asc_14000B4EC; "\n"
0x140005ae5  call    cs:__imp_OutputDebugStringW
0x140005aeb  lea     rcx, stru_1400106E8; lpCriticalSection
0x140005af2  call    cs:__imp_LeaveCriticalSection
0x140005af8  lea     rcx, stru_140010758; lpCriticalSection
0x140005aff  call    cs:__imp_EnterCriticalSection
0x140005b05  mov     esi, cs:?MemoryBufferSize@TraceOutputSettings@@2KA; ulong TraceOutputSettings::MemoryBufferSize
0x140005b0b  cmp     cs:?cMemoryBuffer@CTraceMemoryBuffer@@0KA, esi; ulong CTraceMemoryBuffer::cMemoryBuffer
0x140005b11  jz      loc_140005BD6
0x140005b17  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005b1e  mov     eax, 8
0x140005b23  mul     rsi
0x140005b26  cmovb   rax, rcx
0x140005b2a  mov     rcx, rax; Size
0x140005b2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005b32  mov     rdi, rax
0x140005b35  test    rax, rax
0x140005b38  jz      loc_140005BD6
0x140005b3e  lea     r8, ds:0[rsi*8]; Size
0x140005b46  xor     edx, edx; Val
0x140005b48  mov     rcx, rax; void *
0x140005b4b  call    memset_0
0x140005b50  mov     r8d, cs:?cMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::cMemoryBuffer
0x140005b57  xor     ebp, ebp
0x140005b59  xor     r14d, r14d
0x140005b5c  test    r8d, r8d
0x140005b5f  jz      short loc_140005BB5
0x140005b61  mov     eax, cs:?iMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::iMemoryBuffer
0x140005b67  xor     edx, edx
0x140005b69  add     eax, r14d
0x140005b6c  movsxd  r15, ebp
0x140005b6f  div     r8d
0x140005b72  mov     rcx, [rdi+r15*8]
0x140005b76  mov     r12d, edx
0x140005b79  test    rcx, rcx
0x140005b7c  jz      short loc_140005B95
0x140005b7e  mov     rax, [rcx]
0x140005b81  mov     edx, 1
0x140005b86  mov     rax, [rax]
0x140005b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b8e  mov     r8d, cs:?cMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::cMemoryBuffer
0x140005b95  mov     rax, cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA; CTraceEvent * * CTraceMemoryBuffer::MemoryBuffer
0x140005b9c  xor     edx, edx
0x140005b9e  inc     r14d
0x140005ba1  mov     rcx, [rax+r12*8]
0x140005ba5  lea     eax, [rbp+1]
0x140005ba8  div     esi
0x140005baa  mov     [rdi+r15*8], rcx
0x140005bae  mov     ebp, edx
0x140005bb0  cmp     r14d, r8d
0x140005bb3  jb      short loc_140005B61
0x140005bb5  mov     rcx, cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA; Block
0x140005bbc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140005bc1  mov     cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA, rdi; CTraceEvent * * CTraceMemoryBuffer::MemoryBuffer
0x140005bc8  mov     cs:?cMemoryBuffer@CTraceMemoryBuffer@@0KA, esi; ulong CTraceMemoryBuffer::cMemoryBuffer
0x140005bce  mov     cs:?iMemoryBuffer@CTraceMemoryBuffer@@0KA, ebp; ulong CTraceMemoryBuffer::iMemoryBuffer
0x140005bd4  jmp     short loc_140005BDD
0x140005bd6  mov     rdi, cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA; CTraceEvent * * CTraceMemoryBuffer::MemoryBuffer
0x140005bdd  test    rdi, rdi
0x140005be0  jz      short loc_140005C47
0x140005be2  mov     rax, [rbx]
0x140005be5  mov     rcx, rbx
0x140005be8  mov     rax, [rax+18h]
0x140005bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bf1  mov     rdi, rax
0x140005bf4  test    rax, rax
0x140005bf7  jz      short loc_140005C47
0x140005bf9  mov     r8d, cs:?iMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::iMemoryBuffer
0x140005c00  mov     r9, cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA; CTraceEvent * * CTraceMemoryBuffer::MemoryBuffer
0x140005c07  mov     rcx, [r9+r8*8]
0x140005c0b  test    rcx, rcx
0x140005c0e  jz      short loc_140005C2E
0x140005c10  mov     r8, [rcx]
0x140005c13  mov     edx, 1
0x140005c18  mov     rax, [r8]
0x140005c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c20  mov     r8d, cs:?iMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::iMemoryBuffer
0x140005c27  mov     r9, cs:?MemoryBuffer@CTraceMemoryBuffer@@0PEAPEAVCTraceEvent@@EA; CTraceEvent * * CTraceMemoryBuffer::MemoryBuffer
0x140005c2e  mov     eax, r8d
0x140005c31  xor     edx, edx
0x140005c33  mov     [r9+rax*8], rdi
0x140005c37  lea     eax, [r8+1]
0x140005c3b  div     cs:?cMemoryBuffer@CTraceMemoryBuffer@@0KA; ulong CTraceMemoryBuffer::cMemoryBuffer
0x140005c41  mov     cs:?iMemoryBuffer@CTraceMemoryBuffer@@0KA, edx; ulong CTraceMemoryBuffer::iMemoryBuffer
0x140005c47  lea     rcx, stru_140010758; lpCriticalSection
0x140005c4e  call    cs:__imp_LeaveCriticalSection
0x140005c54  mov     rcx, rbx; struct CTraceEvent *
0x140005c57  call    ?TraceEventToFile@@YAXAEAVCTraceEvent@@@Z; TraceEventToFile(CTraceEvent &)
0x140005c5c  lea     rax, [rsp+468h+var_438]
0x140005c61  mov     r8d, 200h
0x140005c67  mov     [rsp+468h+lpOutputString], rax
0x140005c6c  lea     rdx, [rsp+468h+var_438]
0x140005c71  mov     rax, [rbx]
0x140005c74  mov     rcx, rbx
0x140005c77  mov     rax, [rax+10h]
0x140005c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c80  cmp     eax, 8007007Ah
0x140005c85  jnz     short loc_140005C9B
0x140005c87  mov     rax, [rbx]
0x140005c8a  lea     rdx, [rsp+468h+lpOutputString]
0x140005c8f  mov     rcx, rbx
0x140005c92  mov     rax, [rax+8]
0x140005c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c9b  test    eax, eax
0x140005c9d  js      short loc_140005CD7
0x140005c9f  mov     ecx, cs:?g_TraceTls@@3VTraceTls@@A; dwTlsIndex
0x140005ca5  mov     rdi, [rsp+468h+lpOutputString]
0x140005caa  mov     sil, [rbx+20h]
0x140005cae  call    cs:__imp_TlsGetValue
0x140005cb4  mov     rbx, rax
0x140005cb7  test    rax, rax
0x140005cba  jz      short loc_140005CD7
0x140005cbc  mov     rcx, [rbx+8]
0x140005cc0  mov     r8, rdi
0x140005cc3  mov     rax, [rbx]
0x140005cc6  mov     dl, sil
0x140005cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cce  mov     rbx, [rbx+10h]
0x140005cd2  test    rbx, rbx
0x140005cd5  jnz     short loc_140005CBC
0x140005cd7  mov     rcx, [rsp+468h+var_38]
0x140005cdf  xor     rcx, rsp; StackCookie
0x140005ce2  call    __security_check_cookie
0x140005ce7  lea     r11, [rsp+468h+var_28]
0x140005cef  mov     rbx, [r11+38h]
0x140005cf3  mov     rbp, [r11+40h]
0x140005cf7  mov     rsp, r11
0x140005cfa  pop     r15
0x140005cfc  pop     r14
0x140005cfe  pop     r12
0x140005d00  pop     rdi
0x140005d01  pop     rsi
0x140005d02  retn
```
