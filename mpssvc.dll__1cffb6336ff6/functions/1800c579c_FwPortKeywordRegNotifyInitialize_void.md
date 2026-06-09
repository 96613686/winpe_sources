# FwPortKeywordRegNotifyInitialize(void)

- ea: `0x1800c579c`
- end: `0x1800c5a39`
- name: `?FwPortKeywordRegNotifyInitialize@@YAJXZ`
- size: `669`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800c6110`

## callees

- `0x18000af3c`
- `0x18005c020`
- `0x18006f520`
- `0x1800c579c`
- `0x1800e6010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800c5834`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5834`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c5965`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c5965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5977`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800c57c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800c57c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c57d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c57d6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800c59d1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800c59d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c589f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c58f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c589f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c58f8`
- `fwbase!FwCloseHandle` at `0x1800c5a1a`
- `fwbase!FwCloseHandle` at `0x1800c5a1a`

## string_xrefs

- `0x1800c57b8`: `ntdll.dll`

## pseudocode

```c
__int64 FwPortKeywordRegNotifyInitialize(void)
{
  void *v0; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rsi
  int i; // ebx
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  signed int v8; // eax
  HANDLE EventW; // rax
  signed int v10; // eax
  HANDLE Thread; // rax
  signed int v12; // eax
  unsigned int j; // ebx
  HANDLE Handles[2]; // [rsp+40h] [rbp-48h] BYREF

  *(_OWORD *)Handles = 0;
  v0 = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    for ( i = 0; i < 9; ++i )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, wchar_t *, _QWORD, wchar_t *, int, _QWORD))ProcAddress)(
        *(&PortCollection + 74 * i + 72),
        0,
        &aSystemCurrentc_3[296 * i],
        0,
        &aSystemCurrentc_3[296 * i],
        520,
        0);
      if ( RtlNtStatusToDosError(0) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 37;
          goto LABEL_11;
        }
        goto LABEL_37;
      }
    }
  }
  qword_180131768 = CreateEventW(0, 0, 0, 0);
  if ( qword_180131768 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v0 = EventW;
    if ( EventW )
    {
      Thread = CreateThread(0, 0, FwPortKeywordRegNotifyThread, EventW, 0, 0);
      qword_18012A010 = Thread;
      if ( Thread )
      {
        Handles[0] = Thread;
        Handles[1] = v0;
        if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
        {
          for ( j = 0; j < 9; ++j )
            FwRefreshPortCollectionType(j, 0);
          v5 = 0;
        }
        else
        {
          v5 = -2147418113;
          v6 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v7 = 41;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v12 = GetLastError();
        v5 = v12;
        if ( v12 > 0 )
          v5 = (unsigned __int16)v12 | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 40;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 39;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 38;
LABEL_11:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids, v5);
    }
  }
LABEL_37:
  FwCloseHandle(v0);
  return v5;
}

```

## disassembly

```asm
0x1800c579c  push    rbx
0x1800c579e  push    rsi
0x1800c579f  push    rdi
0x1800c57a0  push    r15
0x1800c57a2  sub     rsp, 68h
0x1800c57a6  mov     rax, cs:__security_cookie
0x1800c57ad  xor     rax, rsp
0x1800c57b0  mov     [rsp+88h+var_38], rax
0x1800c57b5  xorps   xmm0, xmm0
0x1800c57b8  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800c57bf  movups  xmmword ptr [rsp+88h+Handles], xmm0
0x1800c57c4  xor     edi, edi
0x1800c57c6  call    cs:__imp_GetModuleHandleW
0x1800c57cc  mov     rcx, rax; hModule
0x1800c57cf  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800c57d6  call    cs:__imp_GetProcAddress
0x1800c57dc  mov     rsi, rax
0x1800c57df  test    rax, rax
0x1800c57e2  jz      loc_1800C5895
0x1800c57e8  xor     ebx, ebx
0x1800c57ea  lea     r15, ?PortCollection@@3PAU_tag_FW_RESRC_PORT_COLLECTION@@A; _tag_FW_RESRC_PORT_COLLECTION near * PortCollection
0x1800c57f1  cmp     ebx, 9
0x1800c57f4  jge     loc_1800C5895
0x1800c57fa  movsxd  rax, ebx
0x1800c57fd  lea     r8, [r15+38h]
0x1800c5801  imul    rcx, rax, 250h
0x1800c5808  mov     [rsp+88h+var_58], rdi
0x1800c580d  xor     r9d, r9d
0x1800c5810  add     r8, rcx
0x1800c5813  mov     dword ptr [rsp+88h+lpThreadId], 208h
0x1800c581b  xor     edx, edx
0x1800c581d  mov     qword ptr [rsp+88h+dwCreationFlags], r8
0x1800c5822  mov     rax, rsi
0x1800c5825  mov     rcx, [rcx+r15+240h]
0x1800c582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5832  xor     ecx, ecx; Status
0x1800c5834  call    cs:__imp_RtlNtStatusToDosError
0x1800c583a  test    eax, eax
0x1800c583c  jnz     short loc_1800C5842
0x1800c583e  inc     ebx
0x1800c5840  jmp     short loc_1800C57F1
0x1800c5842  call    cs:__imp_GetLastError
0x1800c5848  mov     ebx, eax
0x1800c584a  test    eax, eax
0x1800c584c  jle     short loc_1800C5857
0x1800c584e  movzx   ebx, ax
0x1800c5851  or      ebx, 80070000h
0x1800c5857  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c585e  lea     rax, WPP_GLOBAL_Control
0x1800c5865  cmp     rcx, rax
0x1800c5868  jz      loc_1800C5A17
0x1800c586e  test    byte ptr [rcx+1Ch], 1
0x1800c5872  jz      loc_1800C5A17
0x1800c5878  mov     edx, 25h ; '%'
0x1800c587d  mov     rcx, [rcx+10h]
0x1800c5881  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x1800c5888  mov     r9d, ebx
0x1800c588b  call    WPP_SF_d
0x1800c5890  jmp     loc_1800C5A17
0x1800c5895  xor     r9d, r9d; lpName
0x1800c5898  xor     r8d, r8d; bInitialState
0x1800c589b  xor     edx, edx; bManualReset
0x1800c589d  xor     ecx, ecx; lpEventAttributes
0x1800c589f  call    cs:__imp_CreateEventW
0x1800c58a5  mov     cs:qword_180131768, rax
0x1800c58ac  test    rax, rax
0x1800c58af  jnz     short loc_1800C58EE
0x1800c58b1  call    cs:__imp_GetLastError
0x1800c58b7  mov     ebx, eax
0x1800c58b9  test    eax, eax
0x1800c58bb  jle     short loc_1800C58C6
0x1800c58bd  movzx   ebx, ax
0x1800c58c0  or      ebx, 80070000h
0x1800c58c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c58cd  lea     rax, WPP_GLOBAL_Control
0x1800c58d4  cmp     rcx, rax
0x1800c58d7  jz      loc_1800C5A17
0x1800c58dd  test    byte ptr [rcx+1Ch], 1
0x1800c58e1  jz      loc_1800C5A17
0x1800c58e7  mov     edx, 26h ; '&'
0x1800c58ec  jmp     short loc_1800C587D
0x1800c58ee  xor     r9d, r9d; lpName
0x1800c58f1  xor     r8d, r8d; bInitialState
0x1800c58f4  xor     edx, edx; bManualReset
0x1800c58f6  xor     ecx, ecx; lpEventAttributes
0x1800c58f8  call    cs:__imp_CreateEventW
0x1800c58fe  mov     rdi, rax
0x1800c5901  test    rax, rax
0x1800c5904  jnz     short loc_1800C5946
0x1800c5906  call    cs:__imp_GetLastError
0x1800c590c  mov     ebx, eax
0x1800c590e  test    eax, eax
0x1800c5910  jle     short loc_1800C591B
0x1800c5912  movzx   ebx, ax
0x1800c5915  or      ebx, 80070000h
0x1800c591b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5922  lea     rax, WPP_GLOBAL_Control
0x1800c5929  cmp     rcx, rax
0x1800c592c  jz      loc_1800C5A17
0x1800c5932  test    byte ptr [rcx+1Ch], 1
0x1800c5936  jz      loc_1800C5A17
0x1800c593c  mov     edx, 27h ; '''
0x1800c5941  jmp     loc_1800C587D
0x1800c5946  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x1800c594f  lea     r8, ?FwPortKeywordRegNotifyThread@@YAKPEAX@Z; lpStartAddress
0x1800c5956  mov     r9, rdi; lpParameter
0x1800c5959  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x1800c5961  xor     edx, edx; dwStackSize
0x1800c5963  xor     ecx, ecx; lpThreadAttributes
0x1800c5965  call    cs:__imp_CreateThread
0x1800c596b  mov     cs:qword_18012A010, rax
0x1800c5972  test    rax, rax
0x1800c5975  jnz     short loc_1800C59AF
0x1800c5977  call    cs:__imp_GetLastError
0x1800c597d  mov     ebx, eax
0x1800c597f  test    eax, eax
0x1800c5981  jle     short loc_1800C598C
0x1800c5983  movzx   ebx, ax
0x1800c5986  or      ebx, 80070000h
0x1800c598c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5993  lea     rax, WPP_GLOBAL_Control
0x1800c599a  cmp     rcx, rax
0x1800c599d  jz      short loc_1800C5A17
0x1800c599f  test    byte ptr [rcx+1Ch], 1
0x1800c59a3  jz      short loc_1800C5A17
0x1800c59a5  mov     edx, 28h ; '('
0x1800c59aa  jmp     loc_1800C587D
0x1800c59af  xor     r8d, r8d; bWaitAll
0x1800c59b2  mov     [rsp+88h+Handles], rax
0x1800c59b7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800c59bb  mov     [rsp+88h+Handles+8], rdi
0x1800c59c0  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800c59c5  mov     [rsp+88h+dwCreationFlags], 0; bAlertable
0x1800c59cd  lea     ecx, [r8+2]; nCount
0x1800c59d1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800c59d7  test    eax, eax
0x1800c59d9  jnz     short loc_1800C5A03
0x1800c59db  mov     ebx, 8000FFFFh
0x1800c59e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c59e7  lea     rax, WPP_GLOBAL_Control
0x1800c59ee  cmp     rcx, rax
0x1800c59f1  jz      short loc_1800C5A17
0x1800c59f3  test    byte ptr [rcx+1Ch], 1
0x1800c59f7  jz      short loc_1800C5A17
0x1800c59f9  mov     edx, 29h ; ')'
0x1800c59fe  jmp     loc_1800C587D
0x1800c5a03  xor     ebx, ebx
0x1800c5a05  xor     edx, edx
0x1800c5a07  mov     ecx, ebx
0x1800c5a09  call    ?FwRefreshPortCollectionType@@YAJW4_tag_FW_PORT_COLLECTION_TYPE@@PEAH@Z; FwRefreshPortCollectionType(_tag_FW_PORT_COLLECTION_TYPE,int *)
0x1800c5a0e  inc     ebx
0x1800c5a10  cmp     ebx, 9
0x1800c5a13  jb      short loc_1800C5A05
0x1800c5a15  xor     ebx, ebx
0x1800c5a17  mov     rcx, rdi
0x1800c5a1a  call    cs:__imp_FwCloseHandle
0x1800c5a20  mov     eax, ebx
0x1800c5a22  mov     rcx, [rsp+88h+var_38]
0x1800c5a27  xor     rcx, rsp; StackCookie
0x1800c5a2a  call    __security_check_cookie
0x1800c5a2f  add     rsp, 68h
0x1800c5a33  pop     r15
0x1800c5a35  pop     rdi
0x1800c5a36  pop     rsi
0x1800c5a37  pop     rbx
0x1800c5a38  retn
```
