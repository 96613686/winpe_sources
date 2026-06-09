# DpspLaunchSessionHostProcess(INSTANCEINFO *,__SESSIONHOSTINFO *)

- ea: `0x18000b484`
- end: `0x18000b662`
- name: `?DpspLaunchSessionHostProcess@@YAJPEAUINSTANCEINFO@@PEAU__SESSIONHOSTINFO@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, struct __SESSIONHOSTINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18000ba14`

## callees

- `0x180007500`
- `0x180008990`
- `0x180008ab8`
- `0x180009090`
- `0x18000b484`
- `0x180017040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b60b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b60b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b593`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b5f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b5f0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b5db`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b5db`
- `wdi!WdipLaunchLocalHost` at `0x18000b5bb`

## string_xrefs

- `0x18000b563`: `WDIServiceHost`

## pseudocode

```c
__int64 __fastcall DpspLaunchSessionHostProcess(struct INSTANCEINFO *a1, struct __SESSIONHOSTINFO *a2)
{
  int v4; // r8d
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  char *v10; // rbp
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( !a1 )
  {
    v4 = 346;
LABEL_3:
    v5 = -2147024809;
    LOBYTE(v6) = 87;
LABEL_33:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspLaunchSessionHostProcess",
      v4,
      (int)L"Error = %d",
      v6);
    *((_DWORD *)a1 + 33) = v5;
    DpspRaiseScenarioDPSFailedEvent(a1, WDI_DPS_EVENT_HOST_CREATE_FAILURE);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 347;
    goto LABEL_3;
  }
  v7 = *((_DWORD *)a2 + 30);
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          v5 = -2147467259;
          v4 = 426;
          LOBYTE(v6) = 5;
          goto LABEL_33;
        }
        if ( (*((_DWORD *)a1 + 26) & 0x20) != 0 )
        {
          v6 = DpspLaunchRunDLLUserHost((__int64)a1, (__int64)a2);
          v5 = v6;
          if ( v6 < 0 )
          {
            v4 = 408;
            goto LABEL_33;
          }
        }
        else
        {
          v6 = DpspLaunchTaskEngineUserHost(*((_DWORD *)a2 + 10), *((void **)a2 + 4));
          v5 = v6;
          if ( v6 < 0 )
          {
            v4 = 412;
            goto LABEL_33;
          }
          *((_DWORD *)a2 + 1) = 0;
        }
      }
      else
      {
        v6 = DpspRequestServiceStart((__int64)a2, L"WDISystemHost");
        v5 = v6;
        if ( v6 < 0 )
        {
          v4 = 384;
          goto LABEL_33;
        }
      }
    }
    else
    {
      v6 = DpspRequestServiceStart((__int64)a2, L"WDIServiceHost");
      v5 = v6;
      if ( v6 < 0 )
      {
        v4 = 393;
        goto LABEL_33;
      }
    }
  }
  else
  {
    if ( *(&g_WorkerThreadHandles + 1) )
    {
      WaitForSingleObject(*(&g_WorkerThreadHandles + 1), 0xFFFFFFFF);
      if ( (char *)*(&g_WorkerThreadHandles + 1) - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(*(&g_WorkerThreadHandles + 1));
        *(&g_WorkerThreadHandles + 1) = 0;
      }
    }
    v10 = (char *)CreateThread(0, 0, WdipLaunchLocalHost, 0, 0, &ThreadId);
    if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        v4 = 373;
        LOBYTE(v6) = v5;
        goto LABEL_33;
      }
    }
    else
    {
      v5 = 0;
    }
    *((_DWORD *)a2 + 1) = GetCurrentProcessId();
    *(&g_WorkerThreadHandles + 1) = v10;
  }
  return v5;
}

```

## disassembly

```asm
0x18000b484  push    rbx
0x18000b486  push    rbp
0x18000b487  push    rsi
0x18000b488  push    rdi
0x18000b489  sub     rsp, 38h
0x18000b48d  mov     [rsp+58h+ThreadId], 0
0x18000b495  mov     rdi, rdx
0x18000b498  mov     rsi, rcx
0x18000b49b  test    rcx, rcx
0x18000b49e  jnz     short loc_18000B4B5
0x18000b4a0  mov     r8d, 15Ah
0x18000b4a6  mov     ebx, 80070057h
0x18000b4ab  mov     eax, 57h ; 'W'
0x18000b4b0  jmp     loc_18000B62D
0x18000b4b5  test    rdi, rdi
0x18000b4b8  jnz     short loc_18000B4C2
0x18000b4ba  mov     r8d, 15Bh
0x18000b4c0  jmp     short loc_18000B4A6
0x18000b4c2  mov     ecx, [rdx+78h]
0x18000b4c5  test    ecx, ecx
0x18000b4c7  jz      loc_18000B584
0x18000b4cd  sub     ecx, 1
0x18000b4d0  jz      loc_18000B563
0x18000b4d6  sub     ecx, 1
0x18000b4d9  jz      short loc_18000B542
0x18000b4db  cmp     ecx, 1
0x18000b4de  jz      short loc_18000B4F5
0x18000b4e0  mov     ebx, 80004005h
0x18000b4e5  mov     r8d, 1AAh
0x18000b4eb  mov     eax, 4005h
0x18000b4f0  jmp     loc_18000B62D
0x18000b4f5  mov     eax, [rsi+68h]
0x18000b4f8  test    al, 20h
0x18000b4fa  jz      short loc_18000B51C
0x18000b4fc  mov     rcx, rsi
0x18000b4ff  call    DpspLaunchRunDLLUserHost
0x18000b504  mov     ebx, eax
0x18000b506  test    eax, eax
0x18000b508  jns     loc_18000B600
0x18000b50e  mov     r8d, 198h
0x18000b514  movzx   eax, ax
0x18000b517  jmp     loc_18000B62D
0x18000b51c  mov     rdx, [rdx+20h]; void *
0x18000b520  mov     ecx, [rdi+28h]; unsigned int
0x18000b523  call    DpspLaunchTaskEngineUserHost
0x18000b528  mov     ebx, eax
0x18000b52a  test    eax, eax
0x18000b52c  jns     short loc_18000B536
0x18000b52e  mov     r8d, 19Ch
0x18000b534  jmp     short loc_18000B514
0x18000b536  mov     dword ptr [rdi+4], 0
0x18000b53d  jmp     loc_18000B600
0x18000b542  lea     rdx, aWdisystemhost; "WDISystemHost"
0x18000b549  mov     rcx, rdi
0x18000b54c  call    DpspRequestServiceStart
0x18000b551  mov     ebx, eax
0x18000b553  test    eax, eax
0x18000b555  jns     loc_18000B600
0x18000b55b  mov     r8d, 180h
0x18000b561  jmp     short loc_18000B514
0x18000b563  lea     rdx, aWdiservicehost; "WDIServiceHost"
0x18000b56a  mov     rcx, rdi
0x18000b56d  call    DpspRequestServiceStart
0x18000b572  mov     ebx, eax
0x18000b574  test    eax, eax
0x18000b576  jns     loc_18000B600
0x18000b57c  mov     r8d, 189h
0x18000b582  jmp     short loc_18000B514
0x18000b584  mov     rcx, qword ptr cs:g_WorkerThreadHandles+8; hHandle
0x18000b58b  test    rcx, rcx
0x18000b58e  jz      short loc_18000B5BB
0x18000b590  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b593  call    cs:__imp_WaitForSingleObject
0x18000b599  mov     rcx, qword ptr cs:g_WorkerThreadHandles+8; hObject
0x18000b5a0  lea     rax, [rcx-1]
0x18000b5a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b5a8  ja      short loc_18000B5BB
0x18000b5aa  call    cs:__imp_CloseHandle
0x18000b5b0  mov     qword ptr cs:g_WorkerThreadHandles+8, 0
0x18000b5bb  mov     r8, cs:__imp_WdipLaunchLocalHost; lpStartAddress
0x18000b5c2  lea     rax, [rsp+58h+ThreadId]
0x18000b5c7  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000b5cc  xor     r9d, r9d; lpParameter
0x18000b5cf  xor     edx, edx; dwStackSize
0x18000b5d1  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000b5d9  xor     ecx, ecx; lpThreadAttributes
0x18000b5db  call    cs:__imp_CreateThread
0x18000b5e1  mov     rbp, rax
0x18000b5e4  lea     rcx, [rax-1]
0x18000b5e8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000b5ec  ja      short loc_18000B60B
0x18000b5ee  xor     ebx, ebx
0x18000b5f0  call    cs:__imp_GetCurrentProcessId
0x18000b5f6  mov     [rdi+4], eax
0x18000b5f9  mov     qword ptr cs:g_WorkerThreadHandles+8, rbp
0x18000b600  mov     eax, ebx
0x18000b602  add     rsp, 38h
0x18000b606  pop     rdi
0x18000b607  pop     rsi
0x18000b608  pop     rbp
0x18000b609  pop     rbx
0x18000b60a  retn
0x18000b60b  call    cs:__imp_GetLastError
0x18000b611  mov     ebx, eax
0x18000b613  test    eax, eax
0x18000b615  jle     short loc_18000B620
0x18000b617  movzx   ebx, ax
0x18000b61a  or      ebx, 80070000h
0x18000b620  test    ebx, ebx
0x18000b622  jns     short loc_18000B5F0
0x18000b624  mov     r8d, 175h; int
0x18000b62a  movzx   eax, bx
0x18000b62d  lea     r9, aErrorD; "Error = %d"
0x18000b634  mov     [rsp+58h+dwCreationFlags], eax; Args
0x18000b638  lea     rdx, aDpsplaunchsess; "DpspLaunchSessionHostProcess"
0x18000b63f  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b646  call    WdipTraceError
0x18000b64b  lea     rdx, WDI_DPS_EVENT_HOST_CREATE_FAILURE
0x18000b652  mov     [rsi+84h], ebx
0x18000b658  mov     rcx, rsi
0x18000b65b  call    DpspRaiseScenarioDPSFailedEvent
0x18000b660  jmp     short loc_18000B600
```
