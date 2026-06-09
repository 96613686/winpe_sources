# CMFFile::_ReadFile(CMFFileAsyncResult *)

- ea: `0x18000b10c`
- end: `0x18000b2bb`
- name: `?_ReadFile@CMFFile@@AEAAJPEAVCMFFileAsyncResult@@@Z`
- size: `431`
- prototype: `int(CMFFile *__hidden this, struct CMFFileAsyncResult *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000a830`
- `0x1800df04c`

## callees

- `0x18000b10c`
- `0x18000b2d0`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800de040`
- `0x180125154`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b268`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000b16d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000b16d`

## string_xrefs

- `0x18000b121`: `CMFFile::_ReadFile`
- `0x18000b249`: `CMFFile::_ReadFile`

## pseudocode

```c
__int64 __fastcall CMFFile::_ReadFile(CMFFile *this, struct CMFFileAsyncResult *a2)
{
  unsigned int v4; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  signed int LastError; // eax
  CallStackScopeTrace v9; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v9, "CMFFile::_ReadFile", 1712);
  if ( a2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 64);
    MFCallStackTracingTakeSnapshot((struct IMFAsyncResult *)a2);
    if ( ReadFile(*((HANDLE *)a2 + 20), *((LPVOID *)a2 + 16), *((_DWORD *)a2 + 34), 0, (LPOVERLAPPED)((char *)a2 + 8))
      || GetLastError() == 997 )
    {
      v4 = 0;
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
        WPP_SF_qqq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids,
          a2,
          a2,
          *((_QWORD *)a2 + 20));
    }
    else
    {
      MFCallStackTracingClearSnapshot((struct IMFAsyncResult *)a2);
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    v4 = -2147467261;
    if ( v6->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFFile::_ReadFile", 1714, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v9);
  return v4;
}

```

## disassembly

```asm
0x18000b10c  mov     [rsp+arg_0], rbx
0x18000b111  mov     [rsp+arg_10], rsi
0x18000b116  push    rdi
0x18000b117  sub     rsp, 30h
0x18000b11b  mov     rdi, rdx
0x18000b11e  mov     rsi, rcx
0x18000b121  lea     rdx, aCmffileReadfil; "CMFFile::_ReadFile"
0x18000b128  mov     r8d, 6B0h; int
0x18000b12e  lea     rcx, [rsp+38h+arg_8]; this
0x18000b133  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000b138  test    rdi, rdi
0x18000b13b  jz      short loc_18000B1B3
0x18000b13d  lock inc dword ptr [rsi+100h]
0x18000b144  mov     rcx, rdi; struct IMFAsyncResult *
0x18000b147  call    MFCallStackTracingTakeSnapshot
0x18000b14c  mov     r8d, [rdi+88h]; nNumberOfBytesToRead
0x18000b153  lea     rax, [rdi+8]
0x18000b157  mov     rdx, [rdi+80h]; lpBuffer
0x18000b15e  xor     r9d, r9d; lpNumberOfBytesRead
0x18000b161  mov     rcx, [rdi+0A0h]; hFile
0x18000b168  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18000b16d  call    cs:__imp_ReadFile
0x18000b173  test    eax, eax
0x18000b175  jnz     short loc_18000B188
0x18000b177  call    cs:__imp_GetLastError
0x18000b17d  cmp     eax, 3E5h
0x18000b182  jnz     loc_18000B260
0x18000b188  xor     ebx, ebx
0x18000b18a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18000b191  jnb     loc_18000B286
0x18000b197  lea     rcx, [rsp+38h+arg_8]; this
0x18000b19c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000b1a1  mov     rsi, [rsp+38h+arg_10]
0x18000b1a6  mov     eax, ebx
0x18000b1a8  mov     rbx, [rsp+38h+arg_0]
0x18000b1ad  add     rsp, 30h
0x18000b1b1  pop     rdi
0x18000b1b2  retn
0x18000b1b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1ba  test    rcx, rcx
0x18000b1bd  jnz     short loc_18000B1F4
0x18000b1bf  mov     rax, cs:stru_1801FC290.__vftable
0x18000b1c6  lea     rcx, stru_1801FC290
0x18000b1cd  mov     edx, 7F0h
0x18000b1d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1d9  mov     rax, [rax+8]
0x18000b1dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e2  test    eax, eax
0x18000b1e4  jnz     short loc_18000B230
0x18000b1e6  lea     rcx, stru_1801F8A30; this
0x18000b1ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b1f4  cmp     byte ptr [rcx+8], 0
0x18000b1f8  mov     ebx, 80004003h
0x18000b1fd  jnz     short loc_18000B239
0x18000b1ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000b206  jb      short loc_18000B197
0x18000b208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b20f  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x18000b216  mov     edx, 46h ; 'F'
0x18000b21b  mov     dword ptr [rsp+38h+lpOverlapped], ebx
0x18000b21f  mov     r9, rsi
0x18000b222  mov     rcx, [rcx+10h]
0x18000b226  call    WPP_SF_qD
0x18000b22b  jmp     loc_18000B197
0x18000b230  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b237  jmp     short loc_18000B1F4
0x18000b239  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000b23e  cmp     [rax+7CCh], ebx
0x18000b244  jz      short loc_18000B1FF
0x18000b246  mov     r9d, ebx; int
0x18000b249  lea     rdx, aCmffileReadfil; "CMFFile::_ReadFile"
0x18000b250  mov     r8d, 6B2h; int
0x18000b256  mov     rcx, rax; this
0x18000b259  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000b25e  jmp     short loc_18000B1FF
0x18000b260  mov     rcx, rdi; struct IMFAsyncResult *
0x18000b263  call    MFCallStackTracingClearSnapshot
0x18000b268  call    cs:__imp_GetLastError
0x18000b26e  mov     ebx, eax
0x18000b270  test    eax, eax
0x18000b272  jle     loc_18000B197
0x18000b278  movzx   ebx, ax
0x18000b27b  or      ebx, 80070000h
0x18000b281  jmp     loc_18000B197
0x18000b286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b28d  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x18000b294  mov     rax, [rdi+0A0h]
0x18000b29b  mov     edx, 47h ; 'G'
0x18000b2a0  mov     [rsp+38h+var_10], rax
0x18000b2a5  mov     r9, rdi
0x18000b2a8  mov     [rsp+38h+lpOverlapped], rdi
0x18000b2ad  mov     rcx, [rcx+10h]
0x18000b2b1  call    WPP_SF_qqq
0x18000b2b6  jmp     loc_18000B197
```
