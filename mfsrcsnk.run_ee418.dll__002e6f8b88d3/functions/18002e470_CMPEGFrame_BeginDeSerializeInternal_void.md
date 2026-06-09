# CMPEGFrame::BeginDeSerializeInternal(void)

- ea: `0x18002e470`
- end: `0x18002e6ff`
- name: `?BeginDeSerializeInternal@CMPEGFrame@@MEAAJXZ`
- size: `655`
- prototype: `__int64 __fastcall(CMPEGFrame *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18002e470`
- `0x18002e708`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e4c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e4c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e59a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e59a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e4b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e533`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e4b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e533`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e656`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e656`

## string_xrefs

- `0x18002e499`: `CMPEGFrame::BeginDeSerializeInternal`

## pseudocode

```c
__int64 __fastcall CMPEGFrame::BeginDeSerializeInternal(CMPEGFrame *this, __int64 a2, __int64 a3, struct IUnknown *a4)
{
  CallStackTracing *v4; // rdi
  char *v6; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // esi
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rbx
  wchar_t *v17; // rdi
  DWORD v18; // ebp
  wchar_t *v19; // rax
  int v20; // eax
  int v21; // eax
  CallStackTracing *v23; // rcx
  __int64 v24; // rax
  CallStackTracing *v25; // rcx
  __int64 v26; // rax
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v6 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v6 = Value;
    }
    else if ( !GetLastError() )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v23 = CallStackTracing::s_wpInstance;
      }
      v24 = (**(__int64 (__fastcall ***)(CallStackTracing *))v23)(v23);
      if ( v24 )
        v6 = (char *)v24;
    }
    SetLastError(LastError);
    v9 = *((unsigned int *)v6 + 497);
    if ( (unsigned int)v9 < *((_DWORD *)v6 + 498) )
    {
      v10 = 2 * v9;
      *(_QWORD *)&v6[8 * v10] = "CMPEGFrame::BeginDeSerializeInternal";
      *(_DWORD *)&v6[8 * v10 + 8] = 701;
    }
    ++*((_DWORD *)v6 + 497);
  }
  v13 = CByteStreamCacheReaderEx::BeginRead(
          *((CByteStreamCacheReaderEx **)this + 5),
          4,
          (struct IMFAsyncCallback *)this + 41,
          a4);
  if ( v13 >= 0 )
    goto LABEL_10;
  v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11, v14, v15);
    CallStackTracing::s_wpInstance = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "CMPEGFrame::BeginDeSerializeInternal", 708, v13);
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids, this, v13);
LABEL_10:
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v17 = v16 + 104;
    v18 = GetLastError();
    v19 = (wchar_t *)TlsGetValue(*((_DWORD *)v16 + 3));
    if ( v19 )
    {
      v17 = v19;
    }
    else if ( !GetLastError() )
    {
      v25 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v25 = CallStackTracing::s_wpInstance;
      }
      v26 = (**(__int64 (__fastcall ***)(CallStackTracing *))v25)(v25);
      if ( v26 )
        v17 = (wchar_t *)v26;
    }
    SetLastError(v18);
    v20 = *((_DWORD *)v17 + 497);
    if ( v20 )
    {
      v21 = v20 - 1;
      *((_DWORD *)v17 + 497) = v21;
      if ( !v21 )
      {
        *((_DWORD *)v17 + 497) = 0;
        *((_QWORD *)v17 + 252) = 0;
        *((_DWORD *)v17 + 499) = 0;
        *((GUID *)v17 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v17 + 506) = 0;
        *((_DWORD *)v17 + 496) = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002e470  mov     [rsp+arg_8], rbx
0x18002e475  mov     [rsp+arg_10], rbp
0x18002e47a  push    rsi
0x18002e47b  push    rdi
0x18002e47c  push    r15
0x18002e47e  sub     rsp, 30h
0x18002e482  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e489  mov     rbp, rcx
0x18002e48c  test    rdi, rdi
0x18002e48f  jz      loc_18002E5BB
0x18002e495  cmp     byte ptr [rdi+8], 0
0x18002e499  lea     r15, aCmpegframeBegi; "CMPEGFrame::BeginDeSerializeInternal"
0x18002e4a0  jz      short loc_18002E4F1
0x18002e4a2  lea     rbx, [rdi+0D0h]
0x18002e4a9  call    cs:__imp_GetLastError
0x18002e4af  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002e4b2  mov     esi, eax
0x18002e4b4  call    cs:__imp_TlsGetValue
0x18002e4ba  test    rax, rax
0x18002e4bd  jz      loc_18002E5CC
0x18002e4c3  mov     rbx, rax
0x18002e4c6  mov     ecx, esi; dwErrCode
0x18002e4c8  call    cs:__imp_SetLastError
0x18002e4ce  mov     eax, [rbx+7C4h]
0x18002e4d4  cmp     eax, [rbx+7C8h]
0x18002e4da  jnb     short loc_18002E4EB
0x18002e4dc  add     rax, rax
0x18002e4df  mov     [rbx+rax*8], r15
0x18002e4e3  mov     dword ptr [rbx+rax*8+8], 2BDh
0x18002e4eb  inc     dword ptr [rbx+7C4h]
0x18002e4f1  mov     rcx, [rbp+28h]; this
0x18002e4f5  lea     r8, [rbp+148h]; struct IMFAsyncCallback *
0x18002e4fc  mov     edx, 4; unsigned int
0x18002e501  call    ?BeginRead@CByteStreamCacheReaderEx@@QEAAJKPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z; CByteStreamCacheReaderEx::BeginRead(ulong,IMFAsyncCallback *,IUnknown *)
0x18002e506  mov     esi, eax
0x18002e508  test    eax, eax
0x18002e50a  js      loc_18002E64A
0x18002e510  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e517  cmp     byte ptr [rbx+8], 0
0x18002e51b  jz      loc_18002E5A6
0x18002e521  lea     rdi, [rbx+0D0h]
0x18002e528  call    cs:__imp_GetLastError
0x18002e52e  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002e531  mov     ebp, eax
0x18002e533  call    cs:__imp_TlsGetValue
0x18002e539  test    rax, rax
0x18002e53c  jz      loc_18002E5FD
0x18002e542  mov     rdi, rax
0x18002e545  mov     ecx, ebp; dwErrCode
0x18002e547  call    cs:__imp_SetLastError
0x18002e54d  mov     eax, [rdi+7C4h]
0x18002e553  test    eax, eax
0x18002e555  jz      short loc_18002E5A6
0x18002e557  sub     eax, 1
0x18002e55a  mov     [rdi+7C4h], eax
0x18002e560  jnz     short loc_18002E5A6
0x18002e562  mov     dword ptr [rdi+7C4h], 0
0x18002e56c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e573  mov     qword ptr [rdi+7E0h], 0
0x18002e57e  mov     dword ptr [rdi+7CCh], 0
0x18002e588  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18002e590  mov     dword ptr [rdi+7E8h], 0
0x18002e59a  call    cs:__imp_GetCurrentThreadId
0x18002e5a0  mov     [rdi+7C0h], eax
0x18002e5a6  mov     rbx, [rsp+48h+arg_8]
0x18002e5ab  mov     eax, esi
0x18002e5ad  mov     rbp, [rsp+48h+arg_10]
0x18002e5b2  add     rsp, 30h
0x18002e5b6  pop     r15
0x18002e5b8  pop     rdi
0x18002e5b9  pop     rsi
0x18002e5ba  retn
0x18002e5bb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e5c0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5c7  jmp     loc_18002E495
0x18002e5cc  call    cs:__imp_GetLastError
0x18002e5d2  test    eax, eax
0x18002e5d4  jnz     loc_18002E4C6
0x18002e5da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5e1  test    rcx, rcx
0x18002e5e4  jz      short loc_18002E62E
0x18002e5e6  mov     rax, [rcx]
0x18002e5e9  mov     rax, [rax]
0x18002e5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f1  test    rax, rax
0x18002e5f4  cmovnz  rbx, rax
0x18002e5f8  jmp     loc_18002E4C6
0x18002e5fd  call    cs:__imp_GetLastError
0x18002e603  test    eax, eax
0x18002e605  jnz     loc_18002E545
0x18002e60b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e612  test    rcx, rcx
0x18002e615  jz      short loc_18002E63C
0x18002e617  mov     rax, [rcx]
0x18002e61a  mov     rax, [rax]
0x18002e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e622  test    rax, rax
0x18002e625  cmovnz  rdi, rax
0x18002e629  jmp     loc_18002E545
0x18002e62e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e633  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e63a  jmp     short loc_18002E5E6
0x18002e63c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002e641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e648  jmp     short loc_18002E617
0x18002e64a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e651  test    rbx, rbx
0x18002e654  jnz     short loc_18002E6C4
0x18002e656  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e65c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e663  mov     rcx, rax
0x18002e666  test    rax, rax
0x18002e669  jnz     short loc_18002E6A8
0x18002e66b  lea     rbx, qword_1801B07E0
0x18002e672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e679  jmp     short loc_18002E6C4
0x18002e67b  mov     rcx, rbx; this
0x18002e67e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e683  cmp     [rax+7CCh], esi
0x18002e689  jz      short loc_18002E69F
0x18002e68b  mov     r9d, esi; int
0x18002e68e  mov     r8d, 2C4h; int
0x18002e694  mov     rdx, r15; char *
0x18002e697  mov     rcx, rax; this
0x18002e69a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e69f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6a6  jmp     short loc_18002E6CA
0x18002e6a8  mov     rax, [rax]
0x18002e6ab  mov     edx, 7F0h
0x18002e6b0  mov     rax, [rax+8]
0x18002e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6b9  test    eax, eax
0x18002e6bb  jz      short loc_18002E66B
0x18002e6bd  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6c4  cmp     byte ptr [rbx+8], 0
0x18002e6c8  jnz     short loc_18002E67B
0x18002e6ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e6d1  jb      loc_18002E517
0x18002e6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6de  lea     r8, WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids
0x18002e6e5  mov     edx, 33h ; '3'
0x18002e6ea  mov     [rsp+48h+var_28], esi
0x18002e6ee  mov     r9, rbp
0x18002e6f1  mov     rcx, [rcx+10h]
0x18002e6f5  call    WPP_SF_qD
0x18002e6fa  jmp     loc_18002E510
```
