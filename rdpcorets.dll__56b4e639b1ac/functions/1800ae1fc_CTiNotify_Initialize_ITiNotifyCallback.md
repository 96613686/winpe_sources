# CTiNotify::Initialize(ITiNotifyCallback *)

- ea: `0x1800ae1fc`
- end: `0x1800ae47f`
- name: `?Initialize@CTiNotify@@QEAAJPEAUITiNotifyCallback@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(CTiNotify *__hidden this, struct ITiNotifyCallback *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800adf18`

## callees

- `0x1800071c0`
- `0x1800091a8`
- `0x18000bef4`
- `0x18002e600`
- `0x180032f60`
- `0x1800ae1fc`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ae36e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800ae36e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ae2f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ae2f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae3df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae3a2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae393`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae45f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae45f`

## string_xrefs

- `0x1800ae419`: `Msg thread failed`

## pseudocode

```c
__int64 __fastcall CTiNotify::Initialize(CTiNotify *this, struct ITiNotifyCallback *a2)
{
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // eax
  HANDLE EventW; // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  HANDLE Thread; // rax
  unsigned int v13; // eax
  void *v14; // rcx
  void *v15; // rcx
  LPDWORD lpThreadId; // [rsp+28h] [rbp-10h]

  if ( !a2 )
  {
    LastError = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"invalid callback supplied",
        -2147418113);
    }
    goto LABEL_34;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CTiNotify *)((char *)this + 72)) )
  {
    LastError = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids,
        v8,
        (__int64)"_lockPendingDevices init failed",
        -2147418113);
    }
    goto LABEL_34;
  }
  if ( a2 != *((struct ITiNotifyCallback **)this + 19) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 152, v6, v7);
    *((_QWORD *)this + 19) = a2;
    (*(void (__fastcall **)(struct ITiNotifyCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 13) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 16;
LABEL_18:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids, v10, LastError);
LABEL_19:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_34;
  }
  ResetEvent(EventW);
  Thread = CreateThread(0, 0, CTiNotify::staticThreadProc, this, 0, 0);
  *((_QWORD *)this + 12) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 17;
    goto LABEL_18;
  }
  WaitForSingleObject(*((HANDLE *)this + 13), 0xFFFFFFFF);
  LastError = *((_DWORD *)this + 28);
  if ( LastError >= 0 )
    goto LABEL_36;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(lpThreadId) = LastError;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids,
      v13,
      (__int64)"Msg thread failed",
      lpThreadId);
  }
LABEL_34:
  v14 = (void *)*((_QWORD *)this + 12);
  if ( v14 )
  {
    CloseHandle(v14);
    *((_QWORD *)this + 12) = 0;
  }
LABEL_36:
  v15 = (void *)*((_QWORD *)this + 13);
  if ( v15 )
  {
    CloseHandle(v15);
    *((_QWORD *)this + 13) = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800ae1fc  mov     [rsp+arg_0], rbx
0x1800ae201  mov     [rsp+arg_8], rsi
0x1800ae206  push    rdi
0x1800ae207  sub     rsp, 30h
0x1800ae20b  mov     rbx, rdx
0x1800ae20e  mov     rdi, rcx
0x1800ae211  test    rdx, rdx
0x1800ae214  jnz     short loc_1800AE264
0x1800ae216  mov     ebx, 8000FFFFh
0x1800ae21b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae222  lea     rax, WPP_GLOBAL_Control
0x1800ae229  cmp     rcx, rax
0x1800ae22c  jz      loc_1800AE43F
0x1800ae232  test    byte ptr [rcx+1Ch], 8
0x1800ae236  jz      loc_1800AE43F
0x1800ae23c  cmp     byte ptr [rcx+19h], 2
0x1800ae240  jb      loc_1800AE43F
0x1800ae246  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae24b  mov     edx, 0Eh
0x1800ae250  mov     dword ptr [rsp+38h+lpThreadId], 8000FFFFh
0x1800ae258  lea     rcx, aInvalidCallbac; "invalid callback supplied"
0x1800ae25f  jmp     loc_1800AE420
0x1800ae264  add     rcx, 48h ; 'H'; this
0x1800ae268  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800ae26d  test    eax, eax
0x1800ae26f  jnz     short loc_1800AE2BF
0x1800ae271  mov     ebx, 8000FFFFh
0x1800ae276  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae27d  lea     rax, WPP_GLOBAL_Control
0x1800ae284  cmp     rcx, rax
0x1800ae287  jz      loc_1800AE43F
0x1800ae28d  test    byte ptr [rcx+1Ch], 8
0x1800ae291  jz      loc_1800AE43F
0x1800ae297  cmp     byte ptr [rcx+19h], 2
0x1800ae29b  jb      loc_1800AE43F
0x1800ae2a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae2a6  mov     edx, 0Fh
0x1800ae2ab  mov     dword ptr [rsp+38h+lpThreadId], 8000FFFFh
0x1800ae2b3  lea     rcx, aLockpendingdev; "_lockPendingDevices init failed"
0x1800ae2ba  jmp     loc_1800AE420
0x1800ae2bf  lea     rsi, [rdi+98h]
0x1800ae2c6  cmp     rbx, [rsi]
0x1800ae2c9  jz      short loc_1800AE2E5
0x1800ae2cb  mov     rcx, rsi
0x1800ae2ce  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800ae2d3  mov     [rsi], rbx
0x1800ae2d6  mov     rcx, rbx
0x1800ae2d9  mov     rax, [rbx]
0x1800ae2dc  mov     rax, [rax+8]
0x1800ae2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae2e5  xor     r9d, r9d; lpName
0x1800ae2e8  xor     ecx, ecx; lpEventAttributes
0x1800ae2ea  lea     edx, [r9+1]; bManualReset
0x1800ae2ee  mov     r8d, edx; bInitialState
0x1800ae2f1  call    cs:__imp_CreateEventW
0x1800ae2f7  mov     [rdi+68h], rax
0x1800ae2fb  test    rax, rax
0x1800ae2fe  jnz     short loc_1800AE36B
0x1800ae300  call    cs:__imp_GetLastError
0x1800ae306  mov     ebx, eax
0x1800ae308  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae30f  lea     rax, WPP_GLOBAL_Control
0x1800ae316  cmp     rcx, rax
0x1800ae319  jz      short loc_1800AE34F
0x1800ae31b  test    byte ptr [rcx+1Ch], 8
0x1800ae31f  jz      short loc_1800AE34F
0x1800ae321  cmp     byte ptr [rcx+19h], 2
0x1800ae325  jb      short loc_1800AE34F
0x1800ae327  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae32c  mov     edx, 10h
0x1800ae331  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae338  lea     r8, WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids
0x1800ae33f  mov     r9d, eax
0x1800ae342  mov     [rsp+38h+dwCreationFlags], ebx
0x1800ae346  mov     rcx, [rcx+10h]
0x1800ae34a  call    WPP_SF_Dd
0x1800ae34f  test    ebx, ebx
0x1800ae351  jle     short loc_1800AE35C
0x1800ae353  movzx   ebx, bx
0x1800ae356  or      ebx, 80070000h
0x1800ae35c  test    ebx, ebx
0x1800ae35e  mov     eax, 80004005h
0x1800ae363  cmovns  ebx, eax
0x1800ae366  jmp     loc_1800AE43F
0x1800ae36b  mov     rcx, rax; hEvent
0x1800ae36e  call    cs:__imp_ResetEvent
0x1800ae374  mov     r9, rdi; lpParameter
0x1800ae377  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800ae380  lea     r8, ?staticThreadProc@CTiNotify@@CAKPEAX@Z; lpStartAddress
0x1800ae387  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800ae38f  xor     edx, edx; dwStackSize
0x1800ae391  xor     ecx, ecx; lpThreadAttributes
0x1800ae393  call    cs:__imp_CreateThread
0x1800ae399  mov     [rdi+60h], rax
0x1800ae39d  test    rax, rax
0x1800ae3a0  jnz     short loc_1800AE3D8
0x1800ae3a2  call    cs:__imp_GetLastError
0x1800ae3a8  mov     ebx, eax
0x1800ae3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae3b1  lea     rax, WPP_GLOBAL_Control
0x1800ae3b8  cmp     rcx, rax
0x1800ae3bb  jz      short loc_1800AE34F
0x1800ae3bd  test    byte ptr [rcx+1Ch], 8
0x1800ae3c1  jz      short loc_1800AE34F
0x1800ae3c3  cmp     byte ptr [rcx+19h], 2
0x1800ae3c7  jb      short loc_1800AE34F
0x1800ae3c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae3ce  mov     edx, 11h
0x1800ae3d3  jmp     loc_1800AE331
0x1800ae3d8  mov     rcx, [rdi+68h]; hHandle
0x1800ae3dc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800ae3df  call    cs:__imp_WaitForSingleObject
0x1800ae3e5  mov     ebx, [rdi+70h]
0x1800ae3e8  test    ebx, ebx
0x1800ae3ea  jns     short loc_1800AE456
0x1800ae3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae3f3  lea     rax, WPP_GLOBAL_Control
0x1800ae3fa  cmp     rcx, rax
0x1800ae3fd  jz      short loc_1800AE43F
0x1800ae3ff  test    byte ptr [rcx+1Ch], 8
0x1800ae403  jz      short loc_1800AE43F
0x1800ae405  cmp     byte ptr [rcx+19h], 2
0x1800ae409  jb      short loc_1800AE43F
0x1800ae40b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae410  mov     edx, 12h
0x1800ae415  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x1800ae419  lea     rcx, aMsgThreadFaile; "Msg thread failed"
0x1800ae420  mov     qword ptr [rsp+38h+dwCreationFlags], rcx
0x1800ae425  lea     r8, WPP_ffd2df68a2e73c5b734f99950d235b6e_Traceguids
0x1800ae42c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae433  mov     r9d, eax
0x1800ae436  mov     rcx, [rcx+10h]
0x1800ae43a  call    WPP_SF_DsD
0x1800ae43f  mov     rcx, [rdi+60h]; hObject
0x1800ae443  test    rcx, rcx
0x1800ae446  jz      short loc_1800AE456
0x1800ae448  call    cs:__imp_CloseHandle
0x1800ae44e  mov     qword ptr [rdi+60h], 0
0x1800ae456  mov     rcx, [rdi+68h]; hObject
0x1800ae45a  test    rcx, rcx
0x1800ae45d  jz      short loc_1800AE46D
0x1800ae45f  call    cs:__imp_CloseHandle
0x1800ae465  mov     qword ptr [rdi+68h], 0
0x1800ae46d  mov     rsi, [rsp+38h+arg_8]
0x1800ae472  mov     eax, ebx
0x1800ae474  mov     rbx, [rsp+38h+arg_0]
0x1800ae479  add     rsp, 30h
0x1800ae47d  pop     rdi
0x1800ae47e  retn
```
