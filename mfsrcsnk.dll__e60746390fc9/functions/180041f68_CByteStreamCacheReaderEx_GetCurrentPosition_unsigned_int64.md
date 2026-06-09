# CByteStreamCacheReaderEx::GetCurrentPosition(unsigned __int64 *)

- ea: `0x180041f68`
- end: `0x180042187`
- name: `?GetCurrentPosition@CByteStreamCacheReaderEx@@QEAAJPEA_K@Z`
- size: `543`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, unsigned __int64 *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18004de24`
- `0x18007dfa8`
- `0x1800a2958`
- `0x1800e2c40`
- `0x18014ee74`
- `0x18014f8bc`
- `0x18016ada4`

## callees

- `0x180041f68`
- `0x180071a44`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004204c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041fb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004204c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004202d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004202d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004200f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004200f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041fef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041fef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004209f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004209f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041fa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042038`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041fa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180042038`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800420b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800420b8`

## string_xrefs

- `0x180041fcc`: `CByteStreamCacheReaderEx::GetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReaderEx::GetCurrentPosition(CByteStreamCacheReaderEx *this, unsigned __int64 *a2)
{
  wchar_t *v2; // rbx
  wchar_t *v5; // rdi
  DWORD LastError; // ebp
  wchar_t *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  CallStackTracing *v11; // rdi
  GUID *v12; // rbx
  DWORD v13; // esi
  GUID *v14; // rax
  int v15; // eax
  int v16; // eax
  CallStackTracing *v18; // rax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax

  v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = v2 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v19 = CallStackTracing::s_wpInstance;
      }
      v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
      if ( v20 )
        v5 = (wchar_t *)v20;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[4 * v9] = "CByteStreamCacheReaderEx::GetCurrentPosition";
      *(_DWORD *)&v5[4 * v9 + 4] = 439;
    }
    ++*((_DWORD *)v5 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v10 = *((_QWORD *)this + 64);
  if ( v10 == -1 )
    v10 = *((_QWORD *)this + 63);
  *a2 = v10;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v11 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v12 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v13 = GetLastError();
    v14 = (GUID *)TlsGetValue(*((_DWORD *)v11 + 3));
    if ( v14 )
    {
      v12 = v14;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v21 = CallStackTracing::s_wpInstance;
      }
      v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v22 )
        v12 = (GUID *)v22;
    }
    SetLastError(v13);
    v15 = *(_DWORD *)&v12[124].Data2;
    if ( v15 )
    {
      v16 = v15 - 1;
      *(_DWORD *)&v12[124].Data2 = v16;
      if ( !v16 )
      {
        *(_DWORD *)&v12[124].Data2 = 0;
        *(_QWORD *)&v12[126].Data1 = 0;
        *(_DWORD *)&v12[124].Data4[4] = 0;
        v12[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v12[126].Data4 = 0;
        v12[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180041f68  push    rbx
0x180041f6a  push    rbp
0x180041f6b  push    rsi
0x180041f6c  push    rdi
0x180041f6d  push    r14
0x180041f6f  sub     rsp, 20h
0x180041f73  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041f7a  mov     r14, rdx
0x180041f7d  mov     rsi, rcx
0x180041f80  test    rbx, rbx
0x180041f83  jz      loc_1800420B8
0x180041f89  cmp     byte ptr [rbx+8], 0
0x180041f8d  jz      short loc_180041FE5
0x180041f8f  lea     rdi, [rbx+0D0h]
0x180041f96  call    cs:__imp_GetLastError
0x180041f9c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180041f9f  mov     ebp, eax
0x180041fa1  call    cs:__imp_TlsGetValue
0x180041fa7  test    rax, rax
0x180041faa  jz      loc_1800420E4
0x180041fb0  mov     rdi, rax
0x180041fb3  mov     ecx, ebp; dwErrCode
0x180041fb5  call    cs:__imp_SetLastError
0x180041fbb  mov     eax, [rdi+7C4h]
0x180041fc1  cmp     eax, [rdi+7C8h]
0x180041fc7  jnb     short loc_180041FDF
0x180041fc9  add     rax, rax
0x180041fcc  lea     rcx, aCbytestreamcac_21; "CByteStreamCacheReaderEx::GetCurrentPos"...
0x180041fd3  mov     [rdi+rax*8], rcx
0x180041fd7  mov     dword ptr [rdi+rax*8+8], 1B7h
0x180041fdf  inc     dword ptr [rdi+7C4h]
0x180041fe5  lea     rbx, [rsi+238h]
0x180041fec  mov     rcx, rbx; lpCriticalSection
0x180041fef  call    cs:__imp_EnterCriticalSection
0x180041ff5  mov     rax, [rsi+200h]
0x180041ffc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042000  jnz     short loc_180042009
0x180042002  mov     rax, [rsi+1F8h]
0x180042009  mov     rcx, rbx; lpCriticalSection
0x18004200c  mov     [r14], rax
0x18004200f  call    cs:__imp_LeaveCriticalSection
0x180042015  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004201c  cmp     byte ptr [rdi+8], 0
0x180042020  jz      loc_1800420AB
0x180042026  lea     rbx, [rdi+0D0h]
0x18004202d  call    cs:__imp_GetLastError
0x180042033  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180042036  mov     esi, eax
0x180042038  call    cs:__imp_TlsGetValue
0x18004203e  test    rax, rax
0x180042041  jz      loc_180042115
0x180042047  mov     rbx, rax
0x18004204a  mov     ecx, esi; dwErrCode
0x18004204c  call    cs:__imp_SetLastError
0x180042052  mov     eax, [rbx+7C4h]
0x180042058  test    eax, eax
0x18004205a  jz      short loc_1800420AB
0x18004205c  sub     eax, 1
0x18004205f  mov     [rbx+7C4h], eax
0x180042065  jnz     short loc_1800420AB
0x180042067  mov     dword ptr [rbx+7C4h], 0
0x180042071  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180042078  mov     qword ptr [rbx+7E0h], 0
0x180042083  mov     dword ptr [rbx+7CCh], 0
0x18004208d  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x180042095  mov     dword ptr [rbx+7E8h], 0
0x18004209f  call    cs:__imp_GetCurrentThreadId
0x1800420a5  mov     [rbx+7C0h], eax
0x1800420ab  xor     eax, eax
0x1800420ad  add     rsp, 20h
0x1800420b1  pop     r14
0x1800420b3  pop     rdi
0x1800420b4  pop     rsi
0x1800420b5  pop     rbp
0x1800420b6  pop     rbx
0x1800420b7  retn
0x1800420b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800420be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800420c5  mov     rcx, rax
0x1800420c8  test    rax, rax
0x1800420cb  jnz     loc_180042162
0x1800420d1  lea     rbx, qword_1801B07E0
0x1800420d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800420df  jmp     loc_180041F89
0x1800420e4  call    cs:__imp_GetLastError
0x1800420ea  test    eax, eax
0x1800420ec  jnz     loc_180041FB3
0x1800420f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800420f9  test    rcx, rcx
0x1800420fc  jz      short loc_180042146
0x1800420fe  mov     rax, [rcx]
0x180042101  mov     rax, [rax]
0x180042104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042109  test    rax, rax
0x18004210c  cmovnz  rdi, rax
0x180042110  jmp     loc_180041FB3
0x180042115  call    cs:__imp_GetLastError
0x18004211b  test    eax, eax
0x18004211d  jnz     loc_18004204A
0x180042123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004212a  test    rcx, rcx
0x18004212d  jz      short loc_180042154
0x18004212f  mov     rax, [rcx]
0x180042132  mov     rax, [rax]
0x180042135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004213a  test    rax, rax
0x18004213d  cmovnz  rbx, rax
0x180042141  jmp     loc_18004204A
0x180042146  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004214b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042152  jmp     short loc_1800420FE
0x180042154  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180042159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042160  jmp     short loc_18004212F
0x180042162  mov     rax, [rax]
0x180042165  mov     edx, 7F0h
0x18004216a  mov     rax, [rax+8]
0x18004216e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042173  test    eax, eax
0x180042175  jz      loc_1800420D1
0x18004217b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042182  jmp     loc_180041F89
```
