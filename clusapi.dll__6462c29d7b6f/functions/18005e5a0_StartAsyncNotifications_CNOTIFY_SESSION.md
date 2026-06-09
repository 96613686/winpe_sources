# StartAsyncNotifications(_CNOTIFY_SESSION *)

- ea: `0x18005e5a0`
- end: `0x18005e79c`
- name: `?StartAsyncNotifications@@YAKPEAU_CNOTIFY_SESSION@@@Z`
- size: `508`
- prototype: `unsigned int __fastcall(struct _CNOTIFY_SESSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18005c114`

## callees

- `0x18005cce8`
- `0x18005e5a0`
- `0x18006f910`

## import_xrefs

- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005e6fc`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005e6fc`
- `RPCRT4!RpcAsyncCancelCall` at `0x18005e6ca`
- `RPCRT4!RpcAsyncCancelCall` at `0x18005e6ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e5f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e667`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e5f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e76f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e711`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e711`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005e726`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005e726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e6b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e6d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e6b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e6d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e738`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005e762`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005e762`

## string_xrefs

- `0x18005e61c`: `Could not construct notification message because failed to create event posting %d`
- `0x18005e682`: `Could not construct notification message because failed to create event posting %d`
- `0x18005e77b`: `Could not construct notification message because failed to register in threadpool posting %d`

## pseudocode

```c
__int64 __fastcall StartAsyncNotifications(struct _CNOTIFY_SESSION *a1)
{
  HANDLE *v1; // rdi
  DWORD LastError; // ebx
  HANDLE EventW; // rax
  char *v5; // rsi
  char v6; // r15
  HANDLE v7; // rax
  void *v8; // rcx
  HANDLE CurrentThread; // rax
  int v11; // ebx
  ULONG dwFlagsa; // [rsp+28h] [rbp-20h]
  ULONG dwFlagsb; // [rsp+28h] [rbp-20h]
  __int64 dwFlags; // [rsp+28h] [rbp-20h]
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  v1 = (HANDLE *)((char *)a1 + 72);
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 6) + 32LL) & 2) != 0 )
  {
    TraceMsg(1, 0, L"Clusapi", 0, L"not calling creating notification session due to dead cluster");
    LastError = 1722;
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *v1 = EventW;
    if ( EventW )
    {
      v5 = (char *)a1 + 104;
      *((_QWORD *)a1 + 13) = a1;
      *((_QWORD *)a1 + 14) = 0;
      *((_QWORD *)a1 + 19) = 0;
      *((_QWORD *)a1 + 18) = 0;
      v6 = 0;
      v7 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)a1 + 16) = v7;
      if ( v7 )
      {
        LastError = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)((char *)a1 + 160), 0x70u);
        if ( !LastError )
        {
          TokenHandle = (void *)-1LL;
          CurrentThread = GetCurrentThread();
          v11 = OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle) >= 0;
          CloseHandle(TokenHandle);
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)v5 + 4,
                 *((HANDLE *)v5 + 3),
                 AsyncNotificationCallback,
                 v5,
                 0xFFFFFFFF,
                 (v11 << 8) | 0x10) )
          {
            IssueAsyncNotification((struct _NotifyThreadContext *)v5);
            return 0;
          }
          v6 = 1;
          LastError = GetLastError();
          LODWORD(dwFlags) = LastError;
          TraceMsg(
            4,
            7,
            L"StartAsyncNotifications",
            1936,
            L"Could not construct notification message because failed to register in threadpool posting %d",
            dwFlags);
        }
      }
      else
      {
        LastError = GetLastError();
        dwFlagsb = LastError;
        TraceMsg(
          4,
          7,
          L"StartAsyncNotifications",
          1901,
          L"Could not construct notification message because failed to create event posting %d",
          dwFlagsb);
      }
      if ( v5 )
      {
        v8 = (void *)*((_QWORD *)v5 + 3);
        if ( v8 )
          CloseHandle(v8);
        if ( v6 )
          RpcAsyncCancelCall((PRPC_ASYNC_STATE)(v5 + 56), 1);
      }
    }
    else
    {
      dwFlagsa = GetLastError();
      LastError = dwFlagsa;
      TraceMsg(
        4,
        7,
        L"StartAsyncNotifications",
        1885,
        L"Could not construct notification message because failed to create event posting %d",
        dwFlagsa);
    }
  }
  if ( *v1 )
    CloseHandle(*v1);
  return LastError;
}

```

## disassembly

```asm
0x18005e5a0  mov     [rsp+arg_8], rbx
0x18005e5a5  mov     [rsp+arg_10], rbp
0x18005e5aa  push    rsi
0x18005e5ab  push    rdi
0x18005e5ac  push    r15
0x18005e5ae  sub     rsp, 30h
0x18005e5b2  mov     rax, [rcx+30h]
0x18005e5b6  lea     rdi, [rcx+48h]
0x18005e5ba  xor     r9d, r9d; lpName
0x18005e5bd  mov     rbx, rcx
0x18005e5c0  test    byte ptr [rax+20h], 2
0x18005e5c4  jz      short loc_18005E5ED
0x18005e5c6  xor     edx, edx
0x18005e5c8  lea     rax, aNotCallingCrea; "not calling creating notification sessi"...
0x18005e5cf  lea     r8, aClusapi; "Clusapi"
0x18005e5d6  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x18005e5db  lea     ecx, [rdx+1]
0x18005e5de  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e5e3  mov     ebx, 6BAh
0x18005e5e8  jmp     loc_18005E6D0
0x18005e5ed  xor     r8d, r8d; bInitialState
0x18005e5f0  xor     ecx, ecx; lpEventAttributes
0x18005e5f2  lea     edx, [r8+1]; bManualReset
0x18005e5f6  call    cs:__imp_CreateEventW
0x18005e5fc  mov     [rdi], rax
0x18005e5ff  test    rax, rax
0x18005e602  jnz     short loc_18005E63B
0x18005e604  call    cs:__imp_GetLastError
0x18005e60a  mov     dword ptr [rsp+48h+dwFlags], eax
0x18005e60e  mov     edx, 7
0x18005e613  mov     ebx, eax
0x18005e615  lea     r8, aStartasyncnoti; "StartAsyncNotifications"
0x18005e61c  lea     rax, aCouldNotConstr; "Could not construct notification messag"...
0x18005e623  mov     r9d, 75Dh
0x18005e629  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x18005e62e  lea     ecx, [rdx-3]
0x18005e631  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e636  jmp     loc_18005E6D0
0x18005e63b  lea     rsi, [rbx+68h]
0x18005e63f  xor     r9d, r9d; lpName
0x18005e642  xor     r8d, r8d; bInitialState
0x18005e645  mov     [rsi], rbx
0x18005e648  xor     edx, edx; bManualReset
0x18005e64a  mov     qword ptr [rsi+8], 0
0x18005e652  xor     ecx, ecx; lpEventAttributes
0x18005e654  mov     qword ptr [rsi+30h], 0
0x18005e65c  mov     qword ptr [rsi+28h], 0
0x18005e664  xor     r15b, r15b
0x18005e667  call    cs:__imp_CreateEventW
0x18005e66d  mov     [rsi+18h], rax
0x18005e671  test    rax, rax
0x18005e674  jnz     short loc_18005E6F3
0x18005e676  call    cs:__imp_GetLastError
0x18005e67c  mov     ebx, eax
0x18005e67e  mov     dword ptr [rsp+48h+dwFlags], eax
0x18005e682  lea     rax, aCouldNotConstr; "Could not construct notification messag"...
0x18005e689  mov     r9d, 76Dh
0x18005e68f  mov     edx, 7
0x18005e694  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x18005e699  lea     r8, aStartasyncnoti; "StartAsyncNotifications"
0x18005e6a0  lea     ecx, [rdx-3]
0x18005e6a3  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e6a8  test    rsi, rsi
0x18005e6ab  jz      short loc_18005E6D0
0x18005e6ad  mov     rcx, [rsi+18h]; hObject
0x18005e6b1  test    rcx, rcx
0x18005e6b4  jz      short loc_18005E6BC
0x18005e6b6  call    cs:__imp_CloseHandle
0x18005e6bc  test    r15b, r15b
0x18005e6bf  jz      short loc_18005E6D0
0x18005e6c1  mov     edx, 1; fAbort
0x18005e6c6  lea     rcx, [rsi+38h]; pAsync
0x18005e6ca  call    cs:__imp_RpcAsyncCancelCall
0x18005e6d0  mov     rcx, [rdi]; hObject
0x18005e6d3  test    rcx, rcx
0x18005e6d6  jz      short loc_18005E6DE
0x18005e6d8  call    cs:__imp_CloseHandle
0x18005e6de  mov     eax, ebx
0x18005e6e0  mov     rbx, [rsp+48h+arg_8]
0x18005e6e5  mov     rbp, [rsp+48h+arg_10]
0x18005e6ea  add     rsp, 30h
0x18005e6ee  pop     r15
0x18005e6f0  pop     rdi
0x18005e6f1  pop     rsi
0x18005e6f2  retn
0x18005e6f3  mov     edx, 70h ; 'p'; Size
0x18005e6f8  lea     rcx, [rsi+38h]; pAsync
0x18005e6fc  call    cs:__imp_RpcAsyncInitializeHandle
0x18005e702  mov     ebx, eax
0x18005e704  test    eax, eax
0x18005e706  jnz     short loc_18005E6A8
0x18005e708  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18005e711  call    cs:__imp_GetCurrentThread
0x18005e717  mov     rcx, rax; ThreadHandle
0x18005e71a  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18005e71f  lea     edx, [rbx+6]; DesiredAccess
0x18005e722  lea     r8d, [rbx+1]; OpenAsSelf
0x18005e726  call    cs:__imp_OpenThreadToken
0x18005e72c  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18005e731  mov     ebx, eax
0x18005e733  not     ebx
0x18005e735  shr     ebx, 1Fh
0x18005e738  call    cs:__imp_CloseHandle
0x18005e73e  mov     rdx, [rsi+18h]; hObject
0x18005e742  lea     rcx, [rsi+20h]; phNewWaitObject
0x18005e746  shl     ebx, 8
0x18005e749  lea     r8, ?AsyncNotificationCallback@@YAXPEAXE@Z; Callback
0x18005e750  or      ebx, 10h
0x18005e753  mov     r9, rsi; Context
0x18005e756  mov     dword ptr [rsp+48h+dwFlags], ebx; dwFlags
0x18005e75a  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18005e762  call    cs:__imp_RegisterWaitForSingleObject
0x18005e768  test    eax, eax
0x18005e76a  jnz     short loc_18005E78D
0x18005e76c  mov     r15b, 1
0x18005e76f  call    cs:__imp_GetLastError
0x18005e775  mov     ebx, eax
0x18005e777  mov     dword ptr [rsp+48h+dwFlags], eax
0x18005e77b  lea     rax, aCouldNotConstr_0; "Could not construct notification messag"...
0x18005e782  mov     r9d, 790h
0x18005e788  jmp     loc_18005E68F
0x18005e78d  mov     rcx, rsi; struct _NotifyThreadContext *
0x18005e790  call    ?IssueAsyncNotification@@YAXPEAU_NotifyThreadContext@@@Z; IssueAsyncNotification(_NotifyThreadContext *)
0x18005e795  xor     eax, eax
0x18005e797  jmp     loc_18005E6E0
```
