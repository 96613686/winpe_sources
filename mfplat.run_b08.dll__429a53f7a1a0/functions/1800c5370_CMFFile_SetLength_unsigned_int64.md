# CMFFile::SetLength(unsigned __int64)

- ea: `0x1800c5370`
- end: `0x1800c56da`
- name: `?SetLength@CMFFile@@UEAAJ_K@Z`
- size: `874`
- prototype: `__int64 __fastcall(CMFFile *__hidden this, LONG lDistanceToMove)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18007deb8`
- `0x180099ff0`
- `0x1800c5370`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c538d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c538d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c56be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c56be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c54a4`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800c5429`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800c55cd`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800c5429`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800c55cd`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c555d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c555d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c547e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c547e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5587`

## pseudocode

```c
__int64 __fastcall CMFFile::SetLength(CMFFile *this, unsigned __int64 lDistanceToMove)
{
  signed int v4; // ebx
  int v5; // r8d
  __int64 FileFromAppW; // rsi
  signed int v7; // eax
  signed int LastError; // eax
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  HANDLE v12; // rax
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackScopeTrace v16; // [rsp+60h] [rbp+8h] BYREF
  LONG DistanceToMoveHigh; // [rsp+70h] [rbp+18h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_QWORD *)this + 20) == -1 )
    goto LABEL_2;
  if ( (*((_DWORD *)this + 46) & 0x40000000) == 0 )
  {
    v4 = -2147467259;
    goto LABEL_48;
  }
  v5 = *((_DWORD *)this + 49);
  FileFromAppW = -1;
  if ( (v5 & 0x20000000) != 0 && lDistanceToMove % *((unsigned int *)this + 56) )
  {
    if ( (*((_DWORD *)this + 47) & 2) == 0 )
    {
      if ( (v5 & 0x100) != 0 )
      {
LABEL_2:
        v4 = -2147418113;
        goto LABEL_48;
      }
      CMFFile::UnjoinWorkQueueAndClose(this);
    }
    FileFromAppW = (__int64)CreateFileFromAppW(*((LPCWSTR *)this + 19), 0x40000000u, 2u, 0, 3u, 0, 0);
    if ( FileFromAppW == -1 )
      goto LABEL_11;
  }
  v4 = 0;
  if ( FileFromAppW == -1 )
    FileFromAppW = *((_QWORD *)this + 20);
  DistanceToMoveHigh = HIDWORD(lDistanceToMove);
  if ( SetFilePointer((HANDLE)FileFromAppW, lDistanceToMove, &DistanceToMoveHigh, 0) == -1 )
  {
    CallStackScopeTrace::CallStackScopeTrace(&v16, "CMFFile::SetLength", 1286);
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v9->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
        if ( ThreadRelativeContext->m_result != v4 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFFile::SetLength", 1286, v4);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_47;
      v11 = 57;
LABEL_46:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, this, v4);
LABEL_47:
      CallStackScopeTrace::~CallStackScopeTrace(&v16);
      goto LABEL_48;
    }
    CallStackScopeTrace::~CallStackScopeTrace(&v16);
  }
  if ( !SetEndOfFile((HANDLE)FileFromAppW) )
  {
LABEL_11:
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_48;
  }
  if ( *((_QWORD *)this + 30) > lDistanceToMove )
    *((_QWORD *)this + 30) = lDistanceToMove;
  if ( FileFromAppW != *((_QWORD *)this + 20) )
    CloseHandle((HANDLE)FileFromAppW);
  if ( *((_QWORD *)this + 20) == -1 )
  {
    v12 = CreateFileFromAppW(
            *((LPCWSTR *)this + 19),
            *((_DWORD *)this + 46),
            *((_DWORD *)this + 47),
            0,
            3u,
            *((_DWORD *)this + 49),
            0);
    *((_QWORD *)this + 20) = v12;
    if ( v12 != (HANDLE)-1LL )
    {
      CallStackScopeTrace::CallStackScopeTrace(&v16, "CMFFile::SetLength", 1331);
      v4 = CMFFile::JoinWorkQueue(this);
      if ( v4 >= 0 )
        goto LABEL_47;
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v13->m_fEnabled )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( v14->m_result != v4 )
          CallStackContext::TraceFailure(v14, "CMFFile::SetLength", 1331, v4);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_47;
      v11 = 58;
      goto LABEL_46;
    }
    goto LABEL_11;
  }
LABEL_48:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c5370  mov     [rsp+arg_8], rbx
0x1800c5375  mov     [rsp+arg_18], rsi
0x1800c537a  push    rdi
0x1800c537b  push    r14
0x1800c537d  push    r15
0x1800c537f  sub     rsp, 40h
0x1800c5383  mov     rdi, rcx
0x1800c5386  mov     r14, rdx
0x1800c5389  add     rcx, 70h ; 'p'; lpCriticalSection
0x1800c538d  call    cs:__imp_EnterCriticalSection
0x1800c5393  cmp     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x1800c539b  jnz     short loc_1800C53A7
0x1800c539d  mov     ebx, 8000FFFFh
0x1800c53a2  jmp     loc_1800C56BA
0x1800c53a7  mov     ebx, 40000000h
0x1800c53ac  test    [rdi+0B8h], ebx
0x1800c53b2  jnz     short loc_1800C53BE
0x1800c53b4  mov     ebx, 80004005h
0x1800c53b9  jmp     loc_1800C56BA
0x1800c53be  mov     r8d, [rdi+0C4h]
0x1800c53c5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c53c9  bt      r8d, 1Dh
0x1800c53ce  jnb     loc_1800C5456
0x1800c53d4  mov     ecx, [rdi+0E0h]
0x1800c53da  xor     edx, edx
0x1800c53dc  mov     rax, r14
0x1800c53df  div     rcx
0x1800c53e2  test    rdx, rdx
0x1800c53e5  jz      short loc_1800C5456
0x1800c53e7  mov     eax, [rdi+0BCh]
0x1800c53ed  test    al, 2
0x1800c53ef  jnz     short loc_1800C5400
0x1800c53f1  bt      r8d, 8
0x1800c53f6  jb      short loc_1800C539D
0x1800c53f8  mov     rcx, rdi; this
0x1800c53fb  call    ?UnjoinWorkQueueAndClose@CMFFile@@AEAAJXZ; CMFFile::UnjoinWorkQueueAndClose(void)
0x1800c5400  mov     rcx, [rdi+98h]; lpFileName
0x1800c5407  xor     r9d, r9d; lpSecurityAttributes
0x1800c540a  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800c5413  mov     edx, ebx; dwDesiredAccess
0x1800c5415  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c541d  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c5425  lea     r8d, [r9+2]; dwShareMode
0x1800c5429  call    cs:__imp_CreateFileFromAppW
0x1800c542f  mov     rsi, rax
0x1800c5432  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c5436  jnz     short loc_1800C5456
0x1800c5438  call    cs:__imp_GetLastError
0x1800c543e  mov     ebx, eax
0x1800c5440  test    eax, eax
0x1800c5442  jle     loc_1800C56BA
0x1800c5448  movzx   ebx, ax
0x1800c544b  or      ebx, 80070000h
0x1800c5451  jmp     loc_1800C56BA
0x1800c5456  xor     ebx, ebx
0x1800c5458  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800c545c  jnz     short loc_1800C5465
0x1800c545e  mov     rsi, [rdi+0A0h]
0x1800c5465  mov     rax, r14
0x1800c5468  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800c546d  shr     rax, 20h
0x1800c5471  mov     edx, r14d; lDistanceToMove
0x1800c5474  xor     r9d, r9d; dwMoveMethod
0x1800c5477  mov     [rsp+58h+DistanceToMoveHigh], eax
0x1800c547b  mov     rcx, rsi; hFile
0x1800c547e  call    cs:__imp_SetFilePointer
0x1800c5484  cmp     eax, 0FFFFFFFFh
0x1800c5487  jnz     loc_1800C555A
0x1800c548d  mov     r8d, 506h; int
0x1800c5493  lea     rdx, aCmffileSetleng; "CMFFile::SetLength"
0x1800c549a  lea     rcx, [rsp+58h+arg_0]; this
0x1800c549f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c54a4  call    cs:__imp_GetLastError
0x1800c54aa  mov     ebx, eax
0x1800c54ac  test    eax, eax
0x1800c54ae  jle     short loc_1800C54B9
0x1800c54b0  movzx   ebx, ax
0x1800c54b3  or      ebx, 80070000h
0x1800c54b9  test    ebx, ebx
0x1800c54bb  jns     loc_1800C5550
0x1800c54c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c54c8  test    rcx, rcx
0x1800c54cb  jnz     short loc_1800C550E
0x1800c54cd  mov     rax, cs:stru_1801FC290.__vftable
0x1800c54d4  lea     r8, stru_1801FC290
0x1800c54db  mov     edx, 7F0h
0x1800c54e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c54e7  mov     rcx, r8
0x1800c54ea  mov     rax, [rax+8]
0x1800c54ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c54f3  test    eax, eax
0x1800c54f5  jnz     short loc_1800C5507
0x1800c54f7  lea     rcx, stru_1801F8A30
0x1800c54fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5505  jmp     short loc_1800C550E
0x1800c5507  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c550e  cmp     byte ptr [rcx+8], 0
0x1800c5512  jz      short loc_1800C5539
0x1800c5514  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c5519  cmp     [rax+7CCh], ebx
0x1800c551f  jz      short loc_1800C5539
0x1800c5521  mov     r9d, ebx; int
0x1800c5524  lea     rdx, aCmffileSetleng; "CMFFile::SetLength"
0x1800c552b  mov     r8d, 506h; int
0x1800c5531  mov     rcx, rax; this
0x1800c5534  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c5539  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5540  jb      loc_1800C56B0
0x1800c5546  mov     edx, 39h ; '9'
0x1800c554b  jmp     loc_1800C5692
0x1800c5550  lea     rcx, [rsp+58h+arg_0]; this
0x1800c5555  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800c555a  mov     rcx, rsi; hFile
0x1800c555d  call    cs:__imp_SetEndOfFile
0x1800c5563  test    eax, eax
0x1800c5565  jz      loc_1800C5438
0x1800c556b  cmp     [rdi+0F0h], r14
0x1800c5572  jbe     short loc_1800C557B
0x1800c5574  mov     [rdi+0F0h], r14
0x1800c557b  cmp     rsi, [rdi+0A0h]
0x1800c5582  jz      short loc_1800C558D
0x1800c5584  mov     rcx, rsi; hObject
0x1800c5587  call    cs:__imp_CloseHandle
0x1800c558d  cmp     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x1800c5595  jnz     loc_1800C56BA
0x1800c559b  mov     eax, [rdi+0C4h]
0x1800c55a1  xor     r9d, r9d; lpSecurityAttributes
0x1800c55a4  mov     r8d, [rdi+0BCh]; dwShareMode
0x1800c55ab  mov     edx, [rdi+0B8h]; dwDesiredAccess
0x1800c55b1  mov     rcx, [rdi+98h]; lpFileName
0x1800c55b8  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800c55c1  mov     [rsp+58h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800c55c5  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c55cd  call    cs:__imp_CreateFileFromAppW
0x1800c55d3  mov     [rdi+0A0h], rax
0x1800c55da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c55de  jz      loc_1800C5438
0x1800c55e4  mov     esi, 533h
0x1800c55e9  lea     rdx, aCmffileSetleng; "CMFFile::SetLength"
0x1800c55f0  mov     r8d, esi; int
0x1800c55f3  lea     rcx, [rsp+58h+arg_0]; this
0x1800c55f8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c55fd  mov     rcx, rdi; this
0x1800c5600  call    ?JoinWorkQueue@CMFFile@@AEAAJXZ; CMFFile::JoinWorkQueue(void)
0x1800c5605  mov     ebx, eax
0x1800c5607  test    eax, eax
0x1800c5609  jns     loc_1800C56B0
0x1800c560f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5616  test    rcx, rcx
0x1800c5619  jnz     short loc_1800C565C
0x1800c561b  mov     rcx, cs:stru_1801FC290.__vftable
0x1800c5622  lea     r8, stru_1801FC290
0x1800c5629  mov     edx, 7F0h
0x1800c562e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5635  mov     rax, [rcx+8]
0x1800c5639  mov     rcx, r8
0x1800c563c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5641  test    eax, eax
0x1800c5643  jnz     short loc_1800C5655
0x1800c5645  lea     rcx, stru_1801F8A30
0x1800c564c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5653  jmp     short loc_1800C565C
0x1800c5655  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c565c  cmp     byte ptr [rcx+8], 0
0x1800c5660  jz      short loc_1800C5684
0x1800c5662  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c5667  cmp     [rax+7CCh], ebx
0x1800c566d  jz      short loc_1800C5684
0x1800c566f  mov     r9d, ebx; int
0x1800c5672  lea     rdx, aCmffileSetleng; "CMFFile::SetLength"
0x1800c5679  mov     r8d, esi; int
0x1800c567c  mov     rcx, rax; this
0x1800c567f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c5684  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c568b  jb      short loc_1800C56B0
0x1800c568d  mov     edx, 3Ah ; ':'
0x1800c5692  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5699  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x1800c56a0  mov     r9, rdi
0x1800c56a3  mov     [rsp+58h+dwCreationDisposition], ebx
0x1800c56a7  mov     rcx, [rcx+10h]
0x1800c56ab  call    WPP_SF_qD
0x1800c56b0  lea     rcx, [rsp+58h+arg_0]; this
0x1800c56b5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800c56ba  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800c56be  call    cs:__imp_LeaveCriticalSection
0x1800c56c4  mov     rsi, [rsp+58h+arg_18]
0x1800c56c9  mov     eax, ebx
0x1800c56cb  mov     rbx, [rsp+58h+arg_8]
0x1800c56d0  add     rsp, 40h
0x1800c56d4  pop     r15
0x1800c56d6  pop     r14
0x1800c56d8  pop     rdi
0x1800c56d9  retn
```
