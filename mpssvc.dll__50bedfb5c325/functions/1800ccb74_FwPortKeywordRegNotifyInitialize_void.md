# FwPortKeywordRegNotifyInitialize(void)

- ea: `0x1800ccb74`
- end: `0x1800cce5a`
- name: `?FwPortKeywordRegNotifyInitialize@@YAJXZ`
- size: `742`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800cd610`

## callees

- `0x18000a710`
- `0x180060a88`
- `0x1800729c0`
- `0x1800ccb74`
- `0x1800ec010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ccc18`
- `ntdll!RtlNtStatusToDosError` at `0x1800ccc18`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ccd6d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ccd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccc2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ccd85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccbb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ccbb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ccb9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ccb9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ccc8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cccf4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ccc8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cccf4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800ccde5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800ccde5`
- `fwbase!FwCloseHandle` at `0x1800cce34`
- `fwbase!FwCloseHandle` at `0x1800cce34`

## string_xrefs

- `0x1800ccb90`: `ntdll.dll`

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
  qword_180137938 = CreateEventW(0, 0, 0, 0);
  if ( qword_180137938 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v0 = EventW;
    if ( EventW )
    {
      Thread = CreateThread(0, 0, FwPortKeywordRegNotifyThread, EventW, 0, 0);
      qword_180130100 = Thread;
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
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids, v5);
    }
  }
LABEL_37:
  FwCloseHandle(v0);
  return v5;
}

```

## disassembly

```asm
0x1800ccb74  push    rbx
0x1800ccb76  push    rsi
0x1800ccb77  push    rdi
0x1800ccb78  push    r15
0x1800ccb7a  sub     rsp, 68h
0x1800ccb7e  mov     rax, cs:__security_cookie
0x1800ccb85  xor     rax, rsp
0x1800ccb88  mov     [rsp+88h+var_38], rax
0x1800ccb8d  xorps   xmm0, xmm0
0x1800ccb90  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800ccb97  movups  xmmword ptr [rsp+88h+Handles], xmm0
0x1800ccb9c  xor     edi, edi
0x1800ccb9e  call    cs:__imp_GetModuleHandleW
0x1800ccba5  nop     dword ptr [rax+rax+00h]
0x1800ccbaa  mov     rcx, rax; hModule
0x1800ccbad  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x1800ccbb4  call    cs:__imp_GetProcAddress
0x1800ccbbb  nop     dword ptr [rax+rax+00h]
0x1800ccbc0  mov     rsi, rax
0x1800ccbc3  test    rax, rax
0x1800ccbc6  jz      loc_1800CCC85
0x1800ccbcc  xor     ebx, ebx
0x1800ccbce  lea     r15, ?PortCollection@@3PAU_tag_FW_RESRC_PORT_COLLECTION@@A; _tag_FW_RESRC_PORT_COLLECTION near * PortCollection
0x1800ccbd5  cmp     ebx, 9
0x1800ccbd8  jge     loc_1800CCC85
0x1800ccbde  movsxd  rax, ebx
0x1800ccbe1  lea     r8, [r15+38h]
0x1800ccbe5  imul    rcx, rax, 250h
0x1800ccbec  mov     [rsp+88h+var_58], rdi
0x1800ccbf1  xor     r9d, r9d
0x1800ccbf4  add     r8, rcx
0x1800ccbf7  mov     dword ptr [rsp+88h+lpThreadId], 208h
0x1800ccbff  xor     edx, edx
0x1800ccc01  mov     qword ptr [rsp+88h+dwCreationFlags], r8
0x1800ccc06  mov     rax, rsi
0x1800ccc09  mov     rcx, [rcx+r15+240h]
0x1800ccc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccc16  xor     ecx, ecx; Status
0x1800ccc18  call    cs:__imp_RtlNtStatusToDosError
0x1800ccc1f  nop     dword ptr [rax+rax+00h]
0x1800ccc24  test    eax, eax
0x1800ccc26  jnz     short loc_1800CCC2C
0x1800ccc28  inc     ebx
0x1800ccc2a  jmp     short loc_1800CCBD5
0x1800ccc2c  call    cs:__imp_GetLastError
0x1800ccc33  nop     dword ptr [rax+rax+00h]
0x1800ccc38  mov     ebx, eax
0x1800ccc3a  test    eax, eax
0x1800ccc3c  jle     short loc_1800CCC47
0x1800ccc3e  movzx   ebx, ax
0x1800ccc41  or      ebx, 80070000h
0x1800ccc47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ccc4e  lea     rax, WPP_GLOBAL_Control
0x1800ccc55  cmp     rcx, rax
0x1800ccc58  jz      loc_1800CCE31
0x1800ccc5e  test    byte ptr [rcx+1Ch], 1
0x1800ccc62  jz      loc_1800CCE31
0x1800ccc68  mov     edx, 25h ; '%'
0x1800ccc6d  mov     rcx, [rcx+10h]
0x1800ccc71  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x1800ccc78  mov     r9d, ebx
0x1800ccc7b  call    WPP_SF_d
0x1800ccc80  jmp     loc_1800CCE31
0x1800ccc85  xor     r9d, r9d; lpName
0x1800ccc88  xor     r8d, r8d; bInitialState
0x1800ccc8b  xor     edx, edx; bManualReset
0x1800ccc8d  xor     ecx, ecx; lpEventAttributes
0x1800ccc8f  call    cs:__imp_CreateEventW
0x1800ccc96  nop     dword ptr [rax+rax+00h]
0x1800ccc9b  mov     cs:qword_180137938, rax
0x1800ccca2  test    rax, rax
0x1800ccca5  jnz     short loc_1800CCCEA
0x1800ccca7  call    cs:__imp_GetLastError
0x1800cccae  nop     dword ptr [rax+rax+00h]
0x1800cccb3  mov     ebx, eax
0x1800cccb5  test    eax, eax
0x1800cccb7  jle     short loc_1800CCCC2
0x1800cccb9  movzx   ebx, ax
0x1800cccbc  or      ebx, 80070000h
0x1800cccc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cccc9  lea     rax, WPP_GLOBAL_Control
0x1800cccd0  cmp     rcx, rax
0x1800cccd3  jz      loc_1800CCE31
0x1800cccd9  test    byte ptr [rcx+1Ch], 1
0x1800cccdd  jz      loc_1800CCE31
0x1800ccce3  mov     edx, 26h ; '&'
0x1800ccce8  jmp     short loc_1800CCC6D
0x1800cccea  xor     r9d, r9d; lpName
0x1800ccced  xor     r8d, r8d; bInitialState
0x1800cccf0  xor     edx, edx; bManualReset
0x1800cccf2  xor     ecx, ecx; lpEventAttributes
0x1800cccf4  call    cs:__imp_CreateEventW
0x1800cccfb  nop     dword ptr [rax+rax+00h]
0x1800ccd00  mov     rdi, rax
0x1800ccd03  test    rax, rax
0x1800ccd06  jnz     short loc_1800CCD4E
0x1800ccd08  call    cs:__imp_GetLastError
0x1800ccd0f  nop     dword ptr [rax+rax+00h]
0x1800ccd14  mov     ebx, eax
0x1800ccd16  test    eax, eax
0x1800ccd18  jle     short loc_1800CCD23
0x1800ccd1a  movzx   ebx, ax
0x1800ccd1d  or      ebx, 80070000h
0x1800ccd23  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ccd2a  lea     rax, WPP_GLOBAL_Control
0x1800ccd31  cmp     rcx, rax
0x1800ccd34  jz      loc_1800CCE31
0x1800ccd3a  test    byte ptr [rcx+1Ch], 1
0x1800ccd3e  jz      loc_1800CCE31
0x1800ccd44  mov     edx, 27h ; '''
0x1800ccd49  jmp     loc_1800CCC6D
0x1800ccd4e  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x1800ccd57  lea     r8, ?FwPortKeywordRegNotifyThread@@YAKPEAX@Z; lpStartAddress
0x1800ccd5e  mov     r9, rdi; lpParameter
0x1800ccd61  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x1800ccd69  xor     edx, edx; dwStackSize
0x1800ccd6b  xor     ecx, ecx; lpThreadAttributes
0x1800ccd6d  call    cs:__imp_CreateThread
0x1800ccd74  nop     dword ptr [rax+rax+00h]
0x1800ccd79  mov     cs:qword_180130100, rax
0x1800ccd80  test    rax, rax
0x1800ccd83  jnz     short loc_1800CCDC3
0x1800ccd85  call    cs:__imp_GetLastError
0x1800ccd8c  nop     dword ptr [rax+rax+00h]
0x1800ccd91  mov     ebx, eax
0x1800ccd93  test    eax, eax
0x1800ccd95  jle     short loc_1800CCDA0
0x1800ccd97  movzx   ebx, ax
0x1800ccd9a  or      ebx, 80070000h
0x1800ccda0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ccda7  lea     rax, WPP_GLOBAL_Control
0x1800ccdae  cmp     rcx, rax
0x1800ccdb1  jz      short loc_1800CCE31
0x1800ccdb3  test    byte ptr [rcx+1Ch], 1
0x1800ccdb7  jz      short loc_1800CCE31
0x1800ccdb9  mov     edx, 28h ; '('
0x1800ccdbe  jmp     loc_1800CCC6D
0x1800ccdc3  xor     r8d, r8d; bWaitAll
0x1800ccdc6  mov     [rsp+88h+Handles], rax
0x1800ccdcb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800ccdcf  mov     [rsp+88h+Handles+8], rdi
0x1800ccdd4  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800ccdd9  mov     [rsp+88h+dwCreationFlags], 0; bAlertable
0x1800ccde1  lea     ecx, [r8+2]; nCount
0x1800ccde5  call    cs:__imp_WaitForMultipleObjectsEx
0x1800ccdec  nop     dword ptr [rax+rax+00h]
0x1800ccdf1  test    eax, eax
0x1800ccdf3  jnz     short loc_1800CCE1D
0x1800ccdf5  mov     ebx, 8000FFFFh
0x1800ccdfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cce01  lea     rax, WPP_GLOBAL_Control
0x1800cce08  cmp     rcx, rax
0x1800cce0b  jz      short loc_1800CCE31
0x1800cce0d  test    byte ptr [rcx+1Ch], 1
0x1800cce11  jz      short loc_1800CCE31
0x1800cce13  mov     edx, 29h ; ')'
0x1800cce18  jmp     loc_1800CCC6D
0x1800cce1d  xor     ebx, ebx
0x1800cce1f  xor     edx, edx
0x1800cce21  mov     ecx, ebx
0x1800cce23  call    ?FwRefreshPortCollectionType@@YAJW4_tag_FW_PORT_COLLECTION_TYPE@@PEAH@Z; FwRefreshPortCollectionType(_tag_FW_PORT_COLLECTION_TYPE,int *)
0x1800cce28  inc     ebx
0x1800cce2a  cmp     ebx, 9
0x1800cce2d  jb      short loc_1800CCE1F
0x1800cce2f  xor     ebx, ebx
0x1800cce31  mov     rcx, rdi
0x1800cce34  call    cs:__imp_FwCloseHandle
0x1800cce3b  nop     dword ptr [rax+rax+00h]
0x1800cce40  mov     eax, ebx
0x1800cce42  mov     rcx, [rsp+88h+var_38]
0x1800cce47  xor     rcx, rsp; StackCookie
0x1800cce4a  call    __security_check_cookie
0x1800cce4f  add     rsp, 68h
0x1800cce53  pop     r15
0x1800cce55  pop     rdi
0x1800cce56  pop     rsi
0x1800cce57  pop     rbx
0x1800cce58  retn
```
