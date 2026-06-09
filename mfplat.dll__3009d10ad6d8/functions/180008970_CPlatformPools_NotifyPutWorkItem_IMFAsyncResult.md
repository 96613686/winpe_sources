# CPlatformPools::NotifyPutWorkItem(IMFAsyncResult *)

- ea: `0x180008970`
- end: `0x180008e20`
- name: `?NotifyPutWorkItem@CPlatformPools@@UEAAJPEAUIMFAsyncResult@@@Z`
- size: `1200`
- prototype: `__int64 __fastcall(CPlatformPools *__hidden this, struct IMFAsyncResult *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180008428`
- `0x180008970`
- `0x18000a588`
- `0x18011fff0`
- `0x180120ecc`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800089a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008bc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008a3a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d0f`

## pseudocode

```c
__int64 __fastcall CPlatformPools::NotifyPutWorkItem(CPlatformPools *this, struct IMFAsyncResult *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rbp
  __int64 i; // rbp
  CallStackContextNode *v7; // rbp
  char *v8; // r14
  DWORD LastError; // edi
  char *Value; // rbx
  unsigned int v11; // edi
  unsigned int v12; // ecx
  __int64 v13; // rdx
  _DWORD *v15; // r12
  DWORD CurrentThreadId; // eax
  DWORD v17; // edi
  _QWORD *v18; // r8
  __int64 v19; // rdx
  DWORD v20; // eax
  CallStackTracing *v21; // rcx
  SIZE_T v22; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v24; // r9
  __int64 j; // r8
  __int64 v26; // rdx
  _QWORD *v27; // rdx
  unsigned int v28; // edx

  if ( *((_BYTE *)this + 480) && a2 )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 432);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
    if ( !*((_BYTE *)this + 2824) )
    {
LABEL_18:
      LeaveCriticalSection(v4);
      return 0;
    }
    v5 = *((_QWORD *)this + 363);
    if ( v5 )
    {
      for ( i = *(_QWORD *)(v5 + 8LL * ((unsigned int)a2 % (*((_DWORD *)this + 728) & 0x7FFFFFFFu)));
            i;
            i = *(_QWORD *)(i + 16) )
      {
        if ( *(struct IMFAsyncResult **)i == a2 )
        {
          v7 = *(CallStackContextNode **)(i + 8);
          if ( !v7 )
            goto LABEL_18;
          goto LABEL_9;
        }
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
    v7 = (CallStackContextNode *)*((_QWORD *)this + 361);
    if ( v7 )
    {
      v15 = (_DWORD *)((char *)this + 2896);
      *((_QWORD *)this + 361) = v7->m_pNext;
      v7->m_pNext = 0;
      --*((_DWORD *)this + 724);
      CurrentThreadId = GetCurrentThreadId();
      v7->m_dwMaxDepth = 124;
      v17 = CurrentThreadId;
      memset_0(v7, 0, 0x7C0u);
      v7->m_dwDepth = 0;
      *(_QWORD *)&v7->m_instanceId = 0;
      v7->m_result = 0;
      v7->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
      v7->m_dwErrorsInContext = 0;
      GetCurrentThreadId();
      v7->m_dwThreadID = v17;
      v7->m_pNext = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
    }
    else
    {
      ++*((_DWORD *)this + 725);
      v7 = (CallStackContextNode *)operator new(0x7F8u);
      if ( v7 )
      {
        v20 = GetCurrentThreadId();
        CallStackContext::CallStackContext(v7, v20, 0x7Cu);
        v7->m_pNext = 0;
      }
      else
      {
        v7 = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
      if ( !v7 )
        goto LABEL_18;
      v15 = (_DWORD *)((char *)this + 2896);
    }
    if ( !*((_QWORD *)this + 366) )
    {
      v22 = 24LL * (unsigned int)(*((_DWORD *)this + 736) - 1) + 32;
      ProcessHeap = GetProcessHeap();
      v24 = HeapAlloc(ProcessHeap, 0, v22);
      if ( !v24 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
        if ( *v15 >= *((_DWORD *)this + 710) )
        {
          --*((_DWORD *)this + 725);
          CallStackContextNode::`scalar deleting destructor'(v7, v28);
        }
        else
        {
          v7->m_pNext = (CallStackContextNode *)*((_QWORD *)this + 361);
          ++*v15;
          *((_QWORD *)this + 361) = v7;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
        goto LABEL_18;
      }
      for ( j = 0; (unsigned int)j < *((_DWORD *)this + 736); *((_QWORD *)this + 366) = v27 )
      {
        v26 = (unsigned int)j + 1LL + 2 * j;
        j = (unsigned int)(j + 1);
        v24[v26 + 2] = 0;
        v27 = &v24[v26];
        v27[2] = *((_QWORD *)this + 366);
      }
      *v24 = *((_QWORD *)this + 367);
      *((_QWORD *)this + 367) = v24;
    }
    v18 = (_QWORD *)*((_QWORD *)this + 366);
    *((_QWORD *)this + 366) = v18[2];
    v18[1] = v7;
    *v18 = a2;
    v19 = 8LL * ((unsigned int)a2 % (*((_DWORD *)this + 728) & 0x7FFFFFFFu));
    v18[2] = *(_QWORD *)(v19 + *((_QWORD *)this + 363));
    *(_QWORD *)(v19 + *((_QWORD *)this + 363)) = v18;
    ++*((_DWORD *)this + 729);
LABEL_9:
    v8 = (char *)this + 680;
    if ( *((_BYTE *)this + 480) )
    {
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)this + 121));
      if ( !Value )
      {
        if ( GetLastError() )
          goto LABEL_35;
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        Value = (char *)v21->AllocateNewContext(v21);
        if ( !Value )
LABEL_35:
          Value = v8;
      }
      SetLastError(LastError);
    }
    else
    {
      Value = (char *)this + 680;
    }
    if ( !*((_DWORD *)Value + 498) || !v7->m_dwMaxDepth )
      goto LABEL_18;
    v11 = *((_DWORD *)Value + 497);
    v12 = *((_DWORD *)Value + 506);
    if ( v11 >= 0x7C )
    {
      v11 = 124;
    }
    else if ( v11 <= 0xA )
    {
      v13 = 0;
LABEL_17:
      v7->m_dwErrorsInContext = v12;
      memcpy_0(v7, &Value[16 * v13], 16 * v11);
      v7->m_dwDepth = v11;
      v7->m_sessionId = (_GUID)*((_OWORD *)Value + 125);
      v7->m_instanceId = *((_DWORD *)Value + 504);
      v7->m_dwMark = *((_DWORD *)Value + 505);
      v7->m_result = *((_DWORD *)Value + 499);
      v7->m_dwThreadID = *((_DWORD *)Value + 496);
      goto LABEL_18;
    }
    v13 = v11 - 10;
    v11 = 10;
    if ( v12 >= (unsigned int)dword_1801FB400 >> 1 )
      v12 = (unsigned int)dword_1801FB400 >> 1;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x180008970  push    rbx
0x180008972  push    r14
0x180008974  sub     rsp, 38h
0x180008978  cmp     byte ptr [rcx+1E0h], 0
0x18000897f  mov     r14, rdx
0x180008982  mov     rbx, rcx
0x180008985  jz      loc_180008B16
0x18000898b  test    rdx, rdx
0x18000898e  jz      loc_180008B16
0x180008994  mov     [rsp+48h+arg_10], rsi
0x180008999  lea     rsi, [rcx+1B0h]
0x1800089a0  mov     rcx, rsi; lpCriticalSection
0x1800089a3  call    cs:__imp_EnterCriticalSection
0x1800089a9  cmp     byte ptr [rbx+0B08h], 0
0x1800089b0  jz      loc_180008B08
0x1800089b6  mov     [rsp+48h+arg_8], rbp
0x1800089bb  mov     rbp, [rbx+0B58h]
0x1800089c2  mov     [rsp+48h+var_20], r13
0x1800089c7  xor     r13d, r13d
0x1800089ca  mov     [rsp+48h+arg_18], rdi
0x1800089cf  mov     [rsp+48h+var_18], r12
0x1800089d4  mov     [rsp+48h+var_28], r15
0x1800089d9  test    rbp, rbp
0x1800089dc  jz      loc_180008B20
0x1800089e2  mov     ecx, [rbx+0B60h]
0x1800089e8  xor     edx, edx
0x1800089ea  btr     ecx, 1Fh
0x1800089ee  mov     eax, r14d
0x1800089f1  div     ecx
0x1800089f3  mov     rbp, [rbp+rdx*8+0]
0x1800089f8  test    rbp, rbp
0x1800089fb  jz      loc_180008B20
0x180008a01  cmp     [rbp+0], r14
0x180008a05  jnz     loc_180008C5B
0x180008a0b  mov     rbp, [rbp+8]
0x180008a0f  test    rbp, rbp
0x180008a12  jz      loc_180008AEF
0x180008a18  cmp     byte ptr [rbx+1E0h], 0
0x180008a1f  lea     r14, [rbx+2A8h]
0x180008a26  jz      loc_180008C34
0x180008a2c  call    cs:__imp_GetLastError
0x180008a32  mov     ecx, [rbx+1E4h]; dwTlsIndex
0x180008a38  mov     edi, eax
0x180008a3a  call    cs:__imp_TlsGetValue
0x180008a40  mov     rbx, rax
0x180008a43  test    rax, rax
0x180008a46  jz      loc_180008CBB
0x180008a4c  mov     ecx, edi; dwErrCode
0x180008a4e  call    cs:__imp_SetLastError
0x180008a54  cmp     dword ptr [rbx+7C8h], 0
0x180008a5b  jz      loc_180008AEF
0x180008a61  cmp     dword ptr [rbp+7C8h], 0
0x180008a68  jz      loc_180008AEF
0x180008a6e  mov     edi, [rbx+7C4h]
0x180008a74  mov     ecx, [rbx+7E8h]
0x180008a7a  cmp     edi, 7Ch ; '|'
0x180008a7d  jnb     loc_180008C3C
0x180008a83  cmp     edi, 0Ah
0x180008a86  ja      loc_180008C41
0x180008a8c  mov     edx, r13d
0x180008a8f  mov     r8d, edi
0x180008a92  shl     rdx, 4
0x180008a96  mov     [rbp+7E8h], ecx
0x180008a9c  add     rdx, rbx; Src
0x180008a9f  shl     r8d, 4; Size
0x180008aa3  mov     rcx, rbp; void *
0x180008aa6  call    memcpy_0
0x180008aab  mov     [rbp+7C4h], edi
0x180008ab1  movups  xmm0, xmmword ptr [rbx+7D0h]
0x180008ab8  movups  xmmword ptr [rbp+7D0h], xmm0
0x180008abf  mov     eax, [rbx+7E0h]
0x180008ac5  mov     [rbp+7E0h], eax
0x180008acb  mov     eax, [rbx+7E4h]
0x180008ad1  mov     [rbp+7E4h], eax
0x180008ad7  mov     eax, [rbx+7CCh]
0x180008add  mov     [rbp+7CCh], eax
0x180008ae3  mov     eax, [rbx+7C0h]
0x180008ae9  mov     [rbp+7C0h], eax
0x180008aef  mov     rdi, [rsp+48h+arg_18]
0x180008af4  mov     r12, [rsp+48h+var_18]
0x180008af9  mov     r15, [rsp+48h+var_28]
0x180008afe  mov     rbp, [rsp+48h+arg_8]
0x180008b03  mov     r13, [rsp+48h+var_20]
0x180008b08  mov     rcx, rsi; lpCriticalSection
0x180008b0b  call    cs:__imp_LeaveCriticalSection
0x180008b11  mov     rsi, [rsp+48h+arg_10]
0x180008b16  xor     eax, eax
0x180008b18  add     rsp, 38h
0x180008b1c  pop     r14
0x180008b1e  pop     rbx
0x180008b1f  retn
0x180008b20  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180008b27  call    cs:__imp_EnterCriticalSection
0x180008b2d  mov     rbp, [rbx+0B48h]
0x180008b34  test    rbp, rbp
0x180008b37  jz      loc_180008C64
0x180008b3d  mov     rax, [rbp+7F0h]
0x180008b44  lea     r12, [rbx+0B50h]
0x180008b4b  mov     [rbx+0B48h], rax
0x180008b52  mov     [rbp+7F0h], r13
0x180008b59  dec     dword ptr [r12]
0x180008b5d  call    cs:__imp_GetCurrentThreadId
0x180008b63  xor     edx, edx; Val
0x180008b65  mov     dword ptr [rbp+7C8h], 7Ch ; '|'
0x180008b6f  mov     r8d, 7C0h; Size
0x180008b75  mov     rcx, rbp; void *
0x180008b78  mov     edi, eax
0x180008b7a  call    memset_0
0x180008b7f  mov     [rbp+7C4h], r13d
0x180008b86  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180008b8d  mov     [rbp+7E0h], r13
0x180008b94  mov     [rbp+7CCh], r13d
0x180008b9b  movups  xmmword ptr [rbp+7D0h], xmm0
0x180008ba2  mov     [rbp+7E8h], r13d
0x180008ba9  call    cs:__imp_GetCurrentThreadId
0x180008baf  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180008bb6  mov     [rbp+7C0h], edi
0x180008bbc  mov     [rbp+7F0h], r13
0x180008bc3  call    cs:__imp_LeaveCriticalSection
0x180008bc9  cmp     qword ptr [rbx+0B70h], 0
0x180008bd1  mov     r13, rbp
0x180008bd4  jz      loc_180008CFB
0x180008bda  mov     r8, [rbx+0B70h]
0x180008be1  xor     edx, edx
0x180008be3  mov     rax, [r8+10h]
0x180008be7  mov     [rbx+0B70h], rax
0x180008bee  mov     eax, r14d
0x180008bf1  mov     [r8+8], r13
0x180008bf5  mov     [r8], r14
0x180008bf8  mov     ecx, [rbx+0B60h]
0x180008bfe  btr     ecx, 1Fh
0x180008c02  div     ecx
0x180008c04  mov     rax, [rbx+0B58h]
0x180008c0b  lea     rdx, ds:0[rdx*8]
0x180008c13  mov     rcx, [rdx+rax]
0x180008c17  mov     [r8+10h], rcx
0x180008c1b  mov     rax, [rbx+0B58h]
0x180008c22  mov     [rdx+rax], r8
0x180008c26  inc     dword ptr [rbx+0B64h]
0x180008c2c  xor     r13d, r13d
0x180008c2f  jmp     loc_180008A18
0x180008c34  mov     rbx, r14
0x180008c37  jmp     loc_180008A54
0x180008c3c  mov     edi, 7Ch ; '|'
0x180008c41  mov     eax, cs:dword_1801FB400
0x180008c47  lea     edx, [rdi-0Ah]
0x180008c4a  shr     eax, 1
0x180008c4c  mov     edi, 0Ah
0x180008c51  cmp     ecx, eax
0x180008c53  cmovnb  ecx, eax
0x180008c56  jmp     loc_180008A8F
0x180008c5b  mov     rbp, [rbp+10h]
0x180008c5f  jmp     loc_1800089F8
0x180008c64  inc     dword ptr [rbx+0B54h]
0x180008c6a  mov     ecx, 7F8h; Size
0x180008c6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c74  mov     rbp, rax
0x180008c77  test    rax, rax
0x180008c7a  jz      short loc_180008CCD
0x180008c7c  call    cs:__imp_GetCurrentThreadId
0x180008c82  mov     r8d, 7Ch ; '|'; unsigned int
0x180008c88  mov     rcx, rbp; this
0x180008c8b  mov     edx, eax; unsigned int
0x180008c8d  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180008c92  mov     [rbp+7F0h], r13
0x180008c99  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180008ca0  call    cs:__imp_LeaveCriticalSection
0x180008ca6  test    rbp, rbp
0x180008ca9  jz      loc_180008AEF
0x180008caf  lea     r12, [rbx+0B50h]
0x180008cb6  jmp     loc_180008BC9
0x180008cbb  call    cs:__imp_GetLastError
0x180008cc1  test    eax, eax
0x180008cc3  jz      short loc_180008CD2
0x180008cc5  mov     rbx, r14
0x180008cc8  jmp     loc_180008A4C
0x180008ccd  mov     rbp, r13
0x180008cd0  jmp     short loc_180008C99
0x180008cd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008cd9  test    rcx, rcx
0x180008cdc  jz      loc_180008D86
0x180008ce2  mov     rax, [rcx]
0x180008ce5  mov     rax, [rax]
0x180008ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ced  mov     rbx, rax
0x180008cf0  test    rax, rax
0x180008cf3  jnz     loc_180008A4C
0x180008cf9  jmp     short loc_180008CC5
0x180008cfb  mov     eax, [rbx+0B80h]
0x180008d01  dec     eax
0x180008d03  lea     rcx, [rax+rax*2]
0x180008d07  lea     rdi, ds:20h[rcx*8]
0x180008d0f  call    cs:__imp_GetProcessHeap
0x180008d15  mov     r8, rdi; dwBytes
0x180008d18  xor     edx, edx; dwFlags
0x180008d1a  mov     rcx, rax; hHeap
0x180008d1d  call    cs:__imp_HeapAlloc
0x180008d23  mov     r9, rax
0x180008d26  test    rax, rax
0x180008d29  jz      loc_180008DCC
0x180008d2f  xor     r8d, r8d
0x180008d32  cmp     [rbx+0B80h], r8d
0x180008d39  jbe     short loc_180008D70
0x180008d3b  mov     edx, r8d
0x180008d3e  inc     rdx
0x180008d41  lea     rdx, [rdx+r8*2]
0x180008d45  inc     r8d
0x180008d48  mov     qword ptr [r9+rdx*8+10h], 0
0x180008d51  lea     rdx, [r9+rdx*8]
0x180008d55  mov     rax, [rbx+0B70h]
0x180008d5c  mov     [rdx+10h], rax
0x180008d60  mov     [rbx+0B70h], rdx
0x180008d67  cmp     r8d, [rbx+0B80h]
0x180008d6e  jb      short loc_180008D3B
0x180008d70  mov     rax, [rbx+0B78h]
0x180008d77  mov     [r9], rax
0x180008d7a  mov     [rbx+0B78h], r9
0x180008d81  jmp     loc_180008BDA
0x180008d86  mov     rax, cs:stru_1801FC290.__vftable
0x180008d8d  lea     rcx, stru_1801FC290
0x180008d94  mov     edx, 7F0h
0x180008d99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008da0  mov     rax, [rax+8]
0x180008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da9  test    eax, eax
0x180008dab  jnz     short loc_180008DC0
0x180008dad  lea     rcx, stru_1801F8A30
0x180008db4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008dbb  jmp     loc_180008CE2
0x180008dc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008dc7  jmp     loc_180008CE2
0x180008dcc  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180008dd3  call    cs:__imp_EnterCriticalSection
0x180008dd9  mov     eax, [rbx+0B18h]
0x180008ddf  cmp     [r12], eax
0x180008de3  jge     short loc_180008E10
0x180008de5  mov     rax, [rbx+0B48h]
0x180008dec  mov     [r13+7F0h], rax
0x180008df3  inc     dword ptr [r12]
0x180008df7  mov     [rbx+0B48h], r13
0x180008dfe  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180008e05  call    cs:__imp_LeaveCriticalSection
0x180008e0b  jmp     loc_180008AEF
0x180008e10  dec     dword ptr [rbx+0B54h]
0x180008e16  mov     rcx, r13; this
0x180008e19  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x180008e1e  jmp     short loc_180008DFE
```
