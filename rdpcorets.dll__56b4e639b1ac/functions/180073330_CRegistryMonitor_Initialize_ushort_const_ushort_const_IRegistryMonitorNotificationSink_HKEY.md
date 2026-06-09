# CRegistryMonitor::Initialize(ushort const *,ushort const *,IRegistryMonitorNotificationSink *,HKEY__ *)

- ea: `0x180073330`
- end: `0x180073709`
- name: `?Initialize@CRegistryMonitor@@QEAAJPEBG0PEAUIRegistryMonitorNotificationSink@@PEAUHKEY__@@@Z`
- size: `985`
- prototype: `__int64 __fastcall(CRegistryMonitor *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IRegistryMonitorNotificationSink *, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800422e0`

## callees

- `0x18000e420`
- `0x180059838`
- `0x180073330`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800735e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800735e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800733d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073439`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073470`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800733d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073439`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180073470`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073563`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073613`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073563`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007344d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007350b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800733e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007344d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007350b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800736b4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800734a1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800734a1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18007362d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18007362d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800734d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007364c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007367f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800736aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800734d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007364c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007367f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800736aa`

## pseudocode

```c
__int64 __fastcall CRegistryMonitor::Initialize(
        CRegistryMonitor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IRegistryMonitorNotificationSink *a4)
{
  signed int v5; // ebx
  __int64 v6; // r11
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HANDLE EventW; // rax
  signed int v11; // eax
  HANDLE v12; // rax
  signed int v13; // eax
  HANDLE *v14; // r14
  HANDLE v15; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  void *v18; // rcx
  signed int v19; // eax
  signed int v20; // eax
  DWORD v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  void *v26; // rcx
  signed int v27; // eax
  signed int v28; // eax
  DWORD ExitCode; // [rsp+70h] [rbp+18h] BYREF
  int v31; // [rsp+74h] [rbp+1Ch]

  v31 = HIDWORD(a3);
  ExitCode = 0;
  *((_QWORD *)this + 137) = -2147483646;
  v5 = StringCchCopyW(
         (unsigned __int16 *)this + 24,
         0x104u,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\RDP-Tcp");
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 11;
LABEL_6:
      v9 = (unsigned int)v5;
LABEL_7:
      WPP_SF_d(v7[2], v8, WPP_3f6ebc25c9733d74d8afc52d6fef8389_Traceguids, v9);
      return (unsigned int)v5;
    }
    return (unsigned int)v5;
  }
  *((_QWORD *)this + 136) = v6;
  *((_WORD *)this + 284) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( EventW )
  {
    v12 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = v12;
    if ( v12 )
    {
      v15 = CreateEventW(0, 1, 0, 0);
      v14 = (HANDLE *)((char *)this + 24);
      *((_QWORD *)this + 3) = v15;
      if ( v15 )
      {
        Thread = CreateThread(0, 0, CThread::staticThreadProc, this, 0, (LPDWORD)this + 8);
        *((_QWORD *)this + 1) = Thread;
        if ( Thread )
          goto LABEL_39;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      v14 = (HANDLE *)((char *)this + 24);
    }
    if ( v5 < 0 )
    {
      v18 = (void *)*((_QWORD *)this + 2);
      if ( v18 )
      {
        if ( !CloseHandle(v18) )
        {
          v19 = GetLastError();
          v5 = v19;
          if ( v19 > 0 )
            v5 = (unsigned __int16)v19 | 0x80070000;
        }
        *((_QWORD *)this + 2) = 0;
      }
      if ( *v14 )
      {
        if ( !CloseHandle(*v14) )
        {
          v20 = GetLastError();
          v5 = v20;
          if ( v20 > 0 )
            v5 = (unsigned __int16)v20 | 0x80070000;
        }
        *v14 = 0;
      }
      if ( v5 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 14;
          goto LABEL_6;
        }
        return (unsigned int)v5;
      }
    }
LABEL_39:
    v21 = WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
    if ( v21 )
    {
      if ( v21 == 258 )
      {
        v5 = -2147023436;
        goto LABEL_46;
      }
      v22 = GetLastError();
      v5 = v22;
      if ( v22 > 0 )
        v5 = (unsigned __int16)v22 | 0x80070000;
      if ( v5 < 0 )
      {
LABEL_46:
        v9 = (unsigned int)v5;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 15;
          goto LABEL_7;
        }
        return (unsigned int)v5;
      }
    }
    else
    {
      v5 = 0;
      if ( *((_BYTE *)this + 36) )
        return (unsigned int)v5;
    }
    v5 = 0;
    if ( *((_QWORD *)this + 1) )
    {
      if ( !SetEvent(*v14) )
      {
        v23 = GetLastError();
        v5 = v23;
        if ( v23 > 0 )
          v5 = (unsigned __int16)v23 | 0x80070000;
      }
      (*(void (__fastcall **)(CRegistryMonitor *))(*(_QWORD *)this + 32LL))(this);
      if ( WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF) )
      {
        v5 = -2147418113;
      }
      else if ( !GetExitCodeThread(*((HANDLE *)this + 1), &ExitCode) )
      {
        v24 = GetLastError();
        v5 = v24;
        if ( v24 > 0 )
          v5 = (unsigned __int16)v24 | 0x80070000;
      }
      if ( !CloseHandle(*((HANDLE *)this + 1)) )
      {
        v25 = GetLastError();
        v5 = v25;
        if ( v25 > 0 )
          v5 = (unsigned __int16)v25 | 0x80070000;
      }
      *((_QWORD *)this + 1) = 0;
      *((_DWORD *)this + 8) = 0;
    }
    v26 = (void *)*((_QWORD *)this + 2);
    if ( v26 )
    {
      if ( !CloseHandle(v26) )
      {
        v27 = GetLastError();
        v5 = v27;
        if ( v27 > 0 )
          v5 = (unsigned __int16)v27 | 0x80070000;
      }
      *((_QWORD *)this + 2) = 0;
    }
    if ( *v14 )
    {
      if ( !CloseHandle(*v14) )
      {
        v28 = GetLastError();
        v5 = v28;
        if ( v28 > 0 )
          v5 = (unsigned __int16)v28 | 0x80070000;
      }
      *v14 = 0;
    }
    if ( v5 >= 0 )
      return ExitCode;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 16;
      goto LABEL_6;
    }
    return (unsigned int)v5;
  }
  v11 = GetLastError();
  v5 = v11;
  if ( v11 > 0 )
    v5 = (unsigned __int16)v11 | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 13;
    goto LABEL_6;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180073330  mov     qword ptr [rsp+ExitCode], r8
0x180073335  push    rbx
0x180073336  push    rsi
0x180073337  push    rdi
0x180073338  push    r14
0x18007333a  sub     rsp, 38h
0x18007333e  mov     r11, r9
0x180073341  mov     [rsp+58h+ExitCode], 0
0x180073349  mov     rdi, rcx
0x18007334c  mov     qword ptr [rcx+448h], 0FFFFFFFF80000002h
0x180073357  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Ter"...
0x18007335e  add     rcx, 30h ; '0'; unsigned __int16 *
0x180073362  mov     edx, 104h; unsigned __int64
0x180073367  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007336c  mov     ebx, eax
0x18007336e  test    eax, eax
0x180073370  jns     short loc_1800733BA
0x180073372  mov     rcx, cs:WPP_GLOBAL_Control
0x180073379  lea     rax, WPP_GLOBAL_Control
0x180073380  cmp     rcx, rax
0x180073383  jz      loc_1800736FD
0x180073389  test    byte ptr [rcx+1Ch], 1
0x18007338d  jz      loc_1800736FD
0x180073393  cmp     byte ptr [rcx+19h], 2
0x180073397  jb      loc_1800736FD
0x18007339d  mov     edx, 0Bh
0x1800733a2  mov     r9d, ebx
0x1800733a5  mov     rcx, [rcx+10h]
0x1800733a9  lea     r8, WPP_3f6ebc25c9733d74d8afc52d6fef8389_Traceguids
0x1800733b0  call    WPP_SF_d
0x1800733b5  jmp     loc_1800736FD
0x1800733ba  xor     eax, eax
0x1800733bc  mov     [rdi+440h], r11
0x1800733c3  xor     r9d, r9d; lpName
0x1800733c6  mov     [rdi+238h], ax
0x1800733cd  xor     r8d, r8d; bInitialState
0x1800733d0  xor     edx, edx; bManualReset
0x1800733d2  xor     ecx, ecx; lpEventAttributes
0x1800733d4  call    cs:__imp_CreateEventW
0x1800733da  mov     [rdi+28h], rax
0x1800733de  test    rax, rax
0x1800733e1  jnz     short loc_18007342D
0x1800733e3  call    cs:__imp_GetLastError
0x1800733e9  mov     ebx, eax
0x1800733eb  test    eax, eax
0x1800733ed  jle     short loc_1800733F8
0x1800733ef  movzx   ebx, ax
0x1800733f2  or      ebx, 80070000h
0x1800733f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733ff  lea     rax, WPP_GLOBAL_Control
0x180073406  cmp     rcx, rax
0x180073409  jz      loc_1800736FD
0x18007340f  test    byte ptr [rcx+1Ch], 1
0x180073413  jz      loc_1800736FD
0x180073419  cmp     byte ptr [rcx+19h], 2
0x18007341d  jb      loc_1800736FD
0x180073423  mov     edx, 0Dh
0x180073428  jmp     loc_1800733A2
0x18007342d  xor     r9d, r9d; lpName
0x180073430  xor     r8d, r8d; bInitialState
0x180073433  xor     ecx, ecx; lpEventAttributes
0x180073435  lea     edx, [r9+1]; bManualReset
0x180073439  call    cs:__imp_CreateEventW
0x18007343f  mov     [rdi+10h], rax
0x180073443  mov     esi, 80070000h
0x180073448  test    rax, rax
0x18007344b  jnz     short loc_180073464
0x18007344d  call    cs:__imp_GetLastError
0x180073453  mov     ebx, eax
0x180073455  test    eax, eax
0x180073457  jle     short loc_18007345E
0x180073459  movzx   ebx, ax
0x18007345c  or      ebx, esi
0x18007345e  lea     r14, [rdi+18h]
0x180073462  jmp     short loc_1800734C5
0x180073464  xor     r9d, r9d; lpName
0x180073467  xor     r8d, r8d; bInitialState
0x18007346a  xor     ecx, ecx; lpEventAttributes
0x18007346c  lea     edx, [r9+1]; bManualReset
0x180073470  call    cs:__imp_CreateEventW
0x180073476  lea     r14, [rdi+18h]
0x18007347a  mov     [r14], rax
0x18007347d  test    rax, rax
0x180073480  jz      short loc_1800734B4
0x180073482  lea     rax, [rdi+20h]
0x180073486  mov     r9, rdi; lpParameter
0x180073489  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18007348e  lea     r8, ?staticThreadProc@CThread@@CAKPEAX@Z; lpStartAddress
0x180073495  xor     edx, edx; dwStackSize
0x180073497  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18007349f  xor     ecx, ecx; lpThreadAttributes
0x1800734a1  call    cs:__imp_CreateThread
0x1800734a7  mov     [rdi+8], rax
0x1800734ab  test    rax, rax
0x1800734ae  jnz     loc_18007355C
0x1800734b4  call    cs:__imp_GetLastError
0x1800734ba  mov     ebx, eax
0x1800734bc  test    eax, eax
0x1800734be  jle     short loc_1800734C5
0x1800734c0  movzx   ebx, ax
0x1800734c3  or      ebx, esi
0x1800734c5  test    ebx, ebx
0x1800734c7  jns     loc_18007355C
0x1800734cd  mov     rcx, [rdi+10h]; hObject
0x1800734d1  test    rcx, rcx
0x1800734d4  jz      short loc_1800734F9
0x1800734d6  call    cs:__imp_CloseHandle
0x1800734dc  test    eax, eax
0x1800734de  jnz     short loc_1800734F1
0x1800734e0  call    cs:__imp_GetLastError
0x1800734e6  mov     ebx, eax
0x1800734e8  test    eax, eax
0x1800734ea  jle     short loc_1800734F1
0x1800734ec  movzx   ebx, ax
0x1800734ef  or      ebx, esi
0x1800734f1  mov     qword ptr [rdi+10h], 0
0x1800734f9  mov     rcx, [r14]; hObject
0x1800734fc  test    rcx, rcx
0x1800734ff  jz      short loc_180073523
0x180073501  call    cs:__imp_CloseHandle
0x180073507  test    eax, eax
0x180073509  jnz     short loc_18007351C
0x18007350b  call    cs:__imp_GetLastError
0x180073511  mov     ebx, eax
0x180073513  test    eax, eax
0x180073515  jle     short loc_18007351C
0x180073517  movzx   ebx, ax
0x18007351a  or      ebx, esi
0x18007351c  mov     qword ptr [r14], 0
0x180073523  test    ebx, ebx
0x180073525  jns     short loc_18007355C
0x180073527  mov     rcx, cs:WPP_GLOBAL_Control
0x18007352e  lea     rax, WPP_GLOBAL_Control
0x180073535  cmp     rcx, rax
0x180073538  jz      loc_1800736FD
0x18007353e  test    byte ptr [rcx+1Ch], 1
0x180073542  jz      loc_1800736FD
0x180073548  cmp     byte ptr [rcx+19h], 2
0x18007354c  jb      loc_1800736FD
0x180073552  mov     edx, 0Eh
0x180073557  jmp     loc_1800733A2
0x18007355c  mov     rcx, [rdi+10h]; hHandle
0x180073560  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180073563  call    cs:__imp_WaitForSingleObject
0x180073569  test    eax, eax
0x18007356b  jz      short loc_1800735C8
0x18007356d  cmp     eax, 102h
0x180073572  jz      short loc_18007358B
0x180073574  call    cs:__imp_GetLastError
0x18007357a  mov     ebx, eax
0x18007357c  test    eax, eax
0x18007357e  jle     short loc_180073585
0x180073580  movzx   ebx, ax
0x180073583  or      ebx, esi
0x180073585  test    ebx, ebx
0x180073587  jns     short loc_1800735D3
0x180073589  jmp     short loc_180073590
0x18007358b  mov     ebx, 800705B4h
0x180073590  mov     r9d, ebx
0x180073593  mov     rcx, cs:WPP_GLOBAL_Control
0x18007359a  lea     rax, WPP_GLOBAL_Control
0x1800735a1  cmp     rcx, rax
0x1800735a4  jz      loc_1800736FD
0x1800735aa  test    byte ptr [rcx+1Ch], 1
0x1800735ae  jz      loc_1800736FD
0x1800735b4  cmp     byte ptr [rcx+19h], 2
0x1800735b8  jb      loc_1800736FD
0x1800735be  mov     edx, 0Fh
0x1800735c3  jmp     loc_1800733A5
0x1800735c8  xor     ebx, ebx
0x1800735ca  cmp     [rdi+24h], bl
0x1800735cd  jnz     loc_1800736FD
0x1800735d3  xor     ebx, ebx
0x1800735d5  cmp     [rdi+8], rbx
0x1800735d9  jz      loc_180073676
0x1800735df  mov     rcx, [r14]; hEvent
0x1800735e2  call    cs:__imp_SetEvent
0x1800735e8  test    eax, eax
0x1800735ea  jnz     short loc_1800735FD
0x1800735ec  call    cs:__imp_GetLastError
0x1800735f2  mov     ebx, eax
0x1800735f4  test    eax, eax
0x1800735f6  jle     short loc_1800735FD
0x1800735f8  movzx   ebx, ax
0x1800735fb  or      ebx, esi
0x1800735fd  mov     rax, [rdi]
0x180073600  mov     rcx, rdi
0x180073603  mov     rax, [rax+20h]
0x180073607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007360c  mov     rcx, [rdi+8]; hHandle
0x180073610  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180073613  call    cs:__imp_WaitForSingleObject
0x180073619  test    eax, eax
0x18007361b  jz      short loc_180073624
0x18007361d  mov     ebx, 8000FFFFh
0x180073622  jmp     short loc_180073648
0x180073624  mov     rcx, [rdi+8]; hThread
0x180073628  lea     rdx, [rsp+58h+ExitCode]; lpExitCode
0x18007362d  call    cs:__imp_GetExitCodeThread
0x180073633  test    eax, eax
0x180073635  jnz     short loc_180073648
0x180073637  call    cs:__imp_GetLastError
0x18007363d  mov     ebx, eax
0x18007363f  test    eax, eax
0x180073641  jle     short loc_180073648
0x180073643  movzx   ebx, ax
0x180073646  or      ebx, esi
0x180073648  mov     rcx, [rdi+8]; hObject
0x18007364c  call    cs:__imp_CloseHandle
0x180073652  test    eax, eax
0x180073654  jnz     short loc_180073667
0x180073656  call    cs:__imp_GetLastError
0x18007365c  mov     ebx, eax
0x18007365e  test    eax, eax
0x180073660  jle     short loc_180073667
0x180073662  movzx   ebx, ax
0x180073665  or      ebx, esi
0x180073667  mov     qword ptr [rdi+8], 0
0x18007366f  mov     dword ptr [rdi+20h], 0
0x180073676  mov     rcx, [rdi+10h]; hObject
0x18007367a  test    rcx, rcx
0x18007367d  jz      short loc_1800736A2
0x18007367f  call    cs:__imp_CloseHandle
0x180073685  test    eax, eax
0x180073687  jnz     short loc_18007369A
0x180073689  call    cs:__imp_GetLastError
0x18007368f  mov     ebx, eax
0x180073691  test    eax, eax
0x180073693  jle     short loc_18007369A
0x180073695  movzx   ebx, ax
0x180073698  or      ebx, esi
0x18007369a  mov     qword ptr [rdi+10h], 0
0x1800736a2  mov     rcx, [r14]; hObject
0x1800736a5  test    rcx, rcx
0x1800736a8  jz      short loc_1800736CC
0x1800736aa  call    cs:__imp_CloseHandle
0x1800736b0  test    eax, eax
0x1800736b2  jnz     short loc_1800736C5
0x1800736b4  call    cs:__imp_GetLastError
0x1800736ba  mov     ebx, eax
0x1800736bc  test    eax, eax
0x1800736be  jle     short loc_1800736C5
0x1800736c0  movzx   ebx, ax
0x1800736c3  or      ebx, esi
0x1800736c5  mov     qword ptr [r14], 0
0x1800736cc  test    ebx, ebx
0x1800736ce  jns     short loc_1800736F9
0x1800736d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736d7  lea     rax, WPP_GLOBAL_Control
0x1800736de  cmp     rcx, rax
0x1800736e1  jz      short loc_1800736FD
0x1800736e3  test    byte ptr [rcx+1Ch], 1
0x1800736e7  jz      short loc_1800736FD
0x1800736e9  cmp     byte ptr [rcx+19h], 2
0x1800736ed  jb      short loc_1800736FD
0x1800736ef  mov     edx, 10h
0x1800736f4  jmp     loc_1800733A2
0x1800736f9  mov     ebx, [rsp+58h+ExitCode]
0x1800736fd  mov     eax, ebx
0x1800736ff  add     rsp, 38h
0x180073703  pop     r14
0x180073705  pop     rdi
0x180073706  pop     rsi
0x180073707  pop     rbx
0x180073708  retn
```
