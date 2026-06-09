# CDirectMusicVoice::StartVoiceServiceThread(IDirectMusicPort *)

- ea: `0x18001a2fc`
- end: `0x18001a475`
- name: `?StartVoiceServiceThread@CDirectMusicVoice@@SAJPEAUIDirectMusicPort@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(struct IDirectMusicPort *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180017694`

## callees

- `0x1800012c4`
- `0x18000236c`
- `0x180016184`
- `0x18001a2fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a31b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a31b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001a37a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001a37a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a462`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001a3cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001a3cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a409`

## pseudocode

```c
__int64 __fastcall CDirectMusicVoice::StartVoiceServiceThread(struct IDirectMusicPort *a1)
{
  struct AListItem *v2; // rax
  struct AListItem *v3; // rbx
  int v4; // ecx
  int v5; // edi
  HANDLE EventA; // rax
  unsigned __int64 v7; // rdx
  DWORD LastError; // eax
  DWORD v9; // eax
  void *v10; // rcx
  unsigned __int64 v11; // rdx

  EnterCriticalSection(&CDirectMusicVoice::m_csVST);
  v2 = (struct AListItem *)malloc(0x30u);
  v3 = v2;
  if ( !v2 )
  {
    v5 = -2147024882;
    goto LABEL_14;
  }
  v4 = CDirectMusicVoice::m_cRefVST + 1;
  *((_QWORD *)v2 + 1) = a1;
  v5 = 0;
  *(_QWORD *)v2 = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_DWORD *)v2 + 11) = 0;
  CDirectMusicVoice::m_cRefVST = v4;
  if ( v4 != 1 )
    goto LABEL_12;
  EventA = CreateEventA(0, 0, 0, 0);
  CDirectMusicVoice::m_hVSTWakeUp = EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    v5 = WIN32ERRORtoHRESULT(LastError);
    EventA = CDirectMusicVoice::m_hVSTWakeUp;
  }
  CDirectMusicVoice::m_fVSTStopping = 0;
  if ( v5 < 0 )
    goto LABEL_9;
  CDirectMusicVoice::m_hVSTThread = CreateThread(0, 0, VoiceServiceThreadThk, 0, 0, &CDirectMusicVoice::m_dwVSTThreadId);
  if ( CDirectMusicVoice::m_hVSTThread || (GetLastError(), v9 = GetLastError(), v5 = WIN32ERRORtoHRESULT(v9), v5 >= 0) )
  {
LABEL_12:
    AList::AddTail((AList *)&CDirectMusicVoice::m_ClientList, v3);
    goto LABEL_14;
  }
  EventA = CDirectMusicVoice::m_hVSTWakeUp;
LABEL_9:
  if ( EventA )
  {
    CloseHandle(EventA);
    CDirectMusicVoice::m_hVSTWakeUp = 0;
  }
  v10 = (void *)*((_QWORD *)v3 + 3);
  CDirectMusicVoice::m_cRefVST = 0;
  operator delete(v10, v7);
  operator delete(*((void **)v3 + 4), v11);
  operator delete(v3, 0x30u);
LABEL_14:
  LeaveCriticalSection(&CDirectMusicVoice::m_csVST);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a2fc  mov     [rsp+arg_0], rbx
0x18001a301  push    rdi
0x18001a302  sub     rsp, 30h
0x18001a306  mov     rdi, rcx
0x18001a309  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a310  call    cs:__imp_EnterCriticalSection
0x18001a316  mov     ecx, 30h ; '0'; Size
0x18001a31b  call    cs:__imp_malloc
0x18001a321  mov     rbx, rax
0x18001a324  test    rax, rax
0x18001a327  jz      loc_18001A456
0x18001a32d  mov     ecx, cs:?m_cRefVST@CDirectMusicVoice@@0JA; long CDirectMusicVoice::m_cRefVST
0x18001a333  inc     ecx
0x18001a335  mov     [rax+8], rdi
0x18001a339  xor     edi, edi
0x18001a33b  mov     qword ptr [rax], 0
0x18001a342  mov     qword ptr [rax+10h], 0
0x18001a34a  mov     qword ptr [rax+18h], 0
0x18001a352  mov     qword ptr [rax+20h], 0
0x18001a35a  mov     dword ptr [rax+2Ch], 0
0x18001a361  mov     cs:?m_cRefVST@CDirectMusicVoice@@0JA, ecx; long CDirectMusicVoice::m_cRefVST
0x18001a367  cmp     ecx, 1
0x18001a36a  jnz     loc_18001A445
0x18001a370  xor     r9d, r9d; lpName
0x18001a373  xor     r8d, r8d; bInitialState
0x18001a376  xor     edx, edx; bManualReset
0x18001a378  xor     ecx, ecx; lpEventAttributes
0x18001a37a  call    cs:__imp_CreateEventA
0x18001a380  mov     cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA, rax; void * CDirectMusicVoice::m_hVSTWakeUp
0x18001a387  test    rax, rax
0x18001a38a  jnz     short loc_18001A3A2
0x18001a38c  call    cs:__imp_GetLastError
0x18001a392  mov     ecx, eax; unsigned int
0x18001a394  call    ?WIN32ERRORtoHRESULT@@YAJK@Z; WIN32ERRORtoHRESULT(ulong)
0x18001a399  mov     edi, eax
0x18001a39b  mov     rax, cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA; void * CDirectMusicVoice::m_hVSTWakeUp
0x18001a3a2  mov     cs:?m_fVSTStopping@CDirectMusicVoice@@0_NA, 0; bool CDirectMusicVoice::m_fVSTStopping
0x18001a3a9  test    edi, edi
0x18001a3ab  js      short loc_18001A401
0x18001a3ad  lea     rax, ?m_dwVSTThreadId@CDirectMusicVoice@@0KA; ulong CDirectMusicVoice::m_dwVSTThreadId
0x18001a3b4  xor     r9d, r9d; lpParameter
0x18001a3b7  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001a3bc  lea     r8, ?VoiceServiceThreadThk@@YAKPEAX@Z; lpStartAddress
0x18001a3c3  xor     edx, edx; dwStackSize
0x18001a3c5  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001a3cd  xor     ecx, ecx; lpThreadAttributes
0x18001a3cf  call    cs:__imp_CreateThread
0x18001a3d5  mov     cs:?m_hVSTThread@CDirectMusicVoice@@0PEAXEA, rax; void * CDirectMusicVoice::m_hVSTThread
0x18001a3dc  test    rax, rax
0x18001a3df  jnz     short loc_18001A445
0x18001a3e1  call    cs:__imp_GetLastError
0x18001a3e7  call    cs:__imp_GetLastError
0x18001a3ed  mov     ecx, eax; unsigned int
0x18001a3ef  call    ?WIN32ERRORtoHRESULT@@YAJK@Z; WIN32ERRORtoHRESULT(ulong)
0x18001a3f4  mov     edi, eax
0x18001a3f6  test    eax, eax
0x18001a3f8  jns     short loc_18001A445
0x18001a3fa  mov     rax, cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA; void * CDirectMusicVoice::m_hVSTWakeUp
0x18001a401  test    rax, rax
0x18001a404  jz      short loc_18001A41A
0x18001a406  mov     rcx, rax; hObject
0x18001a409  call    cs:__imp_CloseHandle
0x18001a40f  mov     cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA, 0; void * CDirectMusicVoice::m_hVSTWakeUp
0x18001a41a  mov     rcx, [rbx+18h]; void *
0x18001a41e  mov     cs:?m_cRefVST@CDirectMusicVoice@@0JA, 0; long CDirectMusicVoice::m_cRefVST
0x18001a428  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a42d  mov     rcx, [rbx+20h]; void *
0x18001a431  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a436  mov     edx, 30h ; '0'; unsigned __int64
0x18001a43b  mov     rcx, rbx; void *
0x18001a43e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a443  jmp     short loc_18001A45B
0x18001a445  mov     rdx, rbx; struct AListItem *
0x18001a448  lea     rcx, ?m_ClientList@CDirectMusicVoice@@0VCVSTClientList@@A; this
0x18001a44f  call    ?AddTail@AList@@QEAAXPEAVAListItem@@@Z; AList::AddTail(AListItem *)
0x18001a454  jmp     short loc_18001A45B
0x18001a456  mov     edi, 8007000Eh
0x18001a45b  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a462  call    cs:__imp_LeaveCriticalSection
0x18001a468  mov     rbx, [rsp+38h+arg_0]
0x18001a46d  mov     eax, edi
0x18001a46f  add     rsp, 30h
0x18001a473  pop     rdi
0x18001a474  retn
```
