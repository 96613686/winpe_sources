# WfpExecuteInPersistentThread

- ea: `0x180004a88`
- end: `0x180004b9a`
- name: `WfpExecuteInPersistentThread`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004bdc`

## callees

- `0x1800034e0`
- `0x180004a88`
- `0x180007e38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004aaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004aaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b24`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004af0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004af0`

## string_xrefs

- `0x180004b6b`: `CreateEventW`
- `0x180004b89`: `WfpExecuteInPersistentThread`

## pseudocode

```c
__int64 __fastcall WfpExecuteInPersistentThread(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // rbx
  DWORD LastError; // eax
  __int64 v6; // rcx
  const char *v7; // rdx
  __int128 Context; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+30h] [rbp-18h]

  Context = 0;
  v9 = 0;
  *(_QWORD *)&Context = CreateEventW(0, 1, 0, 0);
  if ( (_QWORD)Context )
  {
    v9 = a2;
    *((_QWORD *)&Context + 1) = WfpRegNotifyRegisterForChanges;
    if ( QueueUserWorkItem(WfpPersistentThreadStartRoutine, &Context, 0x80u) )
    {
      if ( WaitForSingleObject((HANDLE)Context, 0xFFFFFFFF) != -1 )
      {
        v3 = *((_QWORD *)&v9 + 1);
        goto LABEL_5;
      }
      LastError = GetLastError();
      v7 = "WaitForSingleObject";
    }
    else
    {
      LastError = GetLastError();
      v7 = "QueueUserWorkItem";
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = "CreateEventW";
  }
  v3 = WfpReportSysErrorAsWinError(v6, v7, LastError);
LABEL_5:
  CloseHandle((HANDLE)Context);
  if ( v3 )
    WfpReportError(v3, "WfpExecuteInPersistentThread");
  return v3;
}

```

## disassembly

```asm
0x180004a88  push    rbx
0x180004a8a  sub     rsp, 40h
0x180004a8e  xorps   xmm0, xmm0
0x180004a91  xor     r9d, r9d; lpName
0x180004a94  mov     rbx, rdx
0x180004a97  xor     r8d, r8d; bInitialState
0x180004a9a  xor     ecx, ecx; lpEventAttributes
0x180004a9c  movups  [rsp+48h+Context], xmm0
0x180004aa1  lea     edx, [r9+1]; bManualReset
0x180004aa5  movups  [rsp+48h+var_18], xmm0
0x180004aaa  call    cs:__imp_CreateEventW
0x180004ab1  nop     dword ptr [rax+rax+00h]
0x180004ab6  mov     qword ptr [rsp+48h+Context], rax
0x180004abb  test    rax, rax
0x180004abe  jz      loc_180004B5F
0x180004ac4  lea     rax, WfpRegNotifyRegisterForChanges
0x180004acb  mov     qword ptr [rsp+48h+var_18], rbx
0x180004ad0  mov     r8d, 80h; Flags
0x180004ad6  mov     qword ptr [rsp+48h+Context+8], rax
0x180004adb  lea     rdx, [rsp+48h+Context]; Context
0x180004ae0  mov     qword ptr [rsp+48h+var_18+8], 0
0x180004ae9  lea     rcx, WfpPersistentThreadStartRoutine; Function
0x180004af0  call    cs:__imp_QueueUserWorkItem
0x180004af7  nop     dword ptr [rax+rax+00h]
0x180004afc  test    eax, eax
0x180004afe  jz      short loc_180004B74
0x180004b00  mov     rcx, qword ptr [rsp+48h+Context]; hHandle
0x180004b05  or      ebx, 0FFFFFFFFh
0x180004b08  mov     edx, ebx; dwMilliseconds
0x180004b0a  call    cs:__imp_WaitForSingleObject
0x180004b11  nop     dword ptr [rax+rax+00h]
0x180004b16  cmp     eax, ebx
0x180004b18  jz      short loc_180004B3F
0x180004b1a  mov     rbx, qword ptr [rsp+48h+var_18+8]
0x180004b1f  mov     rcx, qword ptr [rsp+48h+Context]; hObject
0x180004b24  call    cs:__imp_CloseHandle
0x180004b2b  nop     dword ptr [rax+rax+00h]
0x180004b30  test    rbx, rbx
0x180004b33  jnz     short loc_180004B89
0x180004b35  mov     rax, rbx
0x180004b38  add     rsp, 40h
0x180004b3c  pop     rbx
0x180004b3d  retn
0x180004b3f  call    cs:__imp_GetLastError
0x180004b46  nop     dword ptr [rax+rax+00h]
0x180004b4b  lea     rdx, aWaitforsingleo; "WaitForSingleObject"
0x180004b52  mov     r8d, eax
0x180004b55  call    WfpReportSysErrorAsWinError
0x180004b5a  mov     rbx, rax
0x180004b5d  jmp     short loc_180004B1F
0x180004b5f  call    cs:__imp_GetLastError
0x180004b66  nop     dword ptr [rax+rax+00h]
0x180004b6b  lea     rdx, aCreateeventw; "CreateEventW"
0x180004b72  jmp     short loc_180004B52
0x180004b74  call    cs:__imp_GetLastError
0x180004b7b  nop     dword ptr [rax+rax+00h]
0x180004b80  lea     rdx, aQueueuserworki; "QueueUserWorkItem"
0x180004b87  jmp     short loc_180004B52
0x180004b89  lea     rdx, aWfpexecuteinpe; "WfpExecuteInPersistentThread"
0x180004b90  mov     rcx, rbx
0x180004b93  call    WfpReportError
0x180004b98  jmp     short loc_180004B35
```
