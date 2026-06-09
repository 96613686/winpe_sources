# CreateRouterWorkerThread

- ea: `0x18001f228`
- end: `0x18001f372`
- name: `CreateRouterWorkerThread`
- size: `330`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002a4f0`

## callees

- `0x18000ac60`
- `0x18001f228`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18001f2cf`
- `KERNEL32!CreateThread` at `0x18001f2cf`
- `KERNEL32!CloseHandle` at `0x18001f32e`
- `KERNEL32!CloseHandle` at `0x18001f32e`
- `KERNEL32!GetLastError` at `0x18001f2da`
- `KERNEL32!GetLastError` at `0x18001f2da`

## string_xrefs

- `0x18001f271`: `CreateRouterWorkerThread`
- `0x18001f2ed`: `CreateRouterWorkerThread: CreateThread failed %d`
- `0x18001f33d`: `Leaving: CreateRouterWorkerThread`

## pseudocode

```c
__int64 __fastcall CreateRouterWorkerThread(LPVOID lpParameter)
{
  HANDLE Thread; // rax
  DWORD LastError; // eax
  DWORD v4; // ebx
  DWORD ThreadId[4]; // [rsp+30h] [rbp-828h] BYREF
  int v7; // [rsp+40h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+44h] [rbp-814h] BYREF

  ThreadId[0] = 0;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"Entered: %ws", L"CreateRouterWorkerThread");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v7);
  }
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)WorkerThread, lpParameter, 0, ThreadId);
  if ( Thread )
  {
    v4 = 0;
    CloseHandle(Thread);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v7) = 0;
      FormatRRASErrorString(&v7, L"CreateRouterWorkerThread: CreateThread failed %d", LastError);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v7);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: CreateRouterWorkerThread");
  return v4;
}

```

## disassembly

```asm
0x18001f228  push    rbx
0x18001f22a  sub     rsp, 850h
0x18001f231  mov     rax, cs:__security_cookie
0x18001f238  xor     rax, rsp
0x18001f23b  mov     [rsp+858h+var_18], rax
0x18001f243  mov     rbx, rcx
0x18001f246  mov     [rsp+858h+ThreadId], 0
0x18001f24e  xor     eax, eax
0x18001f250  lea     rcx, [rsp+858h+var_814]; void *
0x18001f255  xor     edx, edx; Val
0x18001f257  mov     [rsp+858h+var_818], eax
0x18001f25b  mov     r8d, 7FCh; Size
0x18001f261  call    memset_0
0x18001f266  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001f26d  jge     short loc_18001F2AF
0x18001f26f  xor     eax, eax
0x18001f271  lea     r8, aCreaterouterwo; "CreateRouterWorkerThread"
0x18001f278  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001f27f  mov     word ptr [rsp+858h+var_818], ax
0x18001f284  lea     rcx, [rsp+858h+var_818]
0x18001f289  call    FormatRRASErrorString
0x18001f28e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001f295  jge     short loc_18001F2AF
0x18001f297  lea     r8, [rsp+858h+var_818]
0x18001f29c  lea     rdx, RasRtrmgrTraceInfo
0x18001f2a3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f2aa  call    McTemplateU0z_EventWriteTransfer
0x18001f2af  lea     rax, [rsp+858h+ThreadId]
0x18001f2b4  mov     r9, rbx; lpParameter
0x18001f2b7  mov     [rsp+858h+lpThreadId], rax; lpThreadId
0x18001f2bc  lea     r8, WorkerThread; lpStartAddress
0x18001f2c3  xor     edx, edx; dwStackSize
0x18001f2c5  mov     [rsp+858h+dwCreationFlags], 0; dwCreationFlags
0x18001f2cd  xor     ecx, ecx; lpThreadAttributes
0x18001f2cf  call    cs:__imp_CreateThread
0x18001f2d5  test    rax, rax
0x18001f2d8  jnz     short loc_18001F329
0x18001f2da  call    cs:__imp_GetLastError
0x18001f2e0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001f2e7  mov     ebx, eax
0x18001f2e9  jge     short loc_18001F334
0x18001f2eb  xor     ecx, ecx
0x18001f2ed  lea     rdx, aCreaterouterwo_0; "CreateRouterWorkerThread: CreateThread "...
0x18001f2f4  mov     word ptr [rsp+858h+var_818], cx
0x18001f2f9  mov     r8d, eax
0x18001f2fc  lea     rcx, [rsp+858h+var_818]
0x18001f301  call    FormatRRASErrorString
0x18001f306  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001f30d  jge     short loc_18001F334
0x18001f30f  lea     r8, [rsp+858h+var_818]
0x18001f314  lea     rdx, RasRtrmgrTraceInfo
0x18001f31b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f322  call    McTemplateU0z_EventWriteTransfer
0x18001f327  jmp     short loc_18001F334
0x18001f329  xor     ebx, ebx
0x18001f32b  mov     rcx, rax; hObject
0x18001f32e  call    cs:__imp_CloseHandle
0x18001f334  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001f33b  jz      short loc_18001F357
0x18001f33d  lea     r8, aLeavingCreater; "Leaving: CreateRouterWorkerThread"
0x18001f344  lea     rdx, RasRtrmgrTraceInfo
0x18001f34b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f352  call    McTemplateU0z_EventWriteTransfer
0x18001f357  mov     eax, ebx
0x18001f359  mov     rcx, [rsp+858h+var_18]
0x18001f361  xor     rcx, rsp; StackCookie
0x18001f364  call    __security_check_cookie
0x18001f369  add     rsp, 850h
0x18001f370  pop     rbx
0x18001f371  retn
```
