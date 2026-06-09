# TeredoRioCreateWorkerThreads

- ea: `0x1800571b0`
- end: `0x180057590`
- name: `TeredoRioCreateWorkerThreads`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800562a0`
- `0x180056c38`

## callees

- `0x180008210`
- `0x180009010`
- `0x1800190f0`
- `0x180024250`
- `0x180046d9c`
- `0x18004b5f0`
- `0x1800571b0`
- `0x180057f08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057269`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005754d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005754d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005727d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005746d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005727d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005746d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574d5`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18005722c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800572b1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18005722c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800572b1`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180057435`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180057435`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180057532`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180057532`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005740b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005740b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180057308`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180057308`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800574a6`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800574a6`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x180057340`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x180057340`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x18005745d`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x18005745d`

## string_xrefs

- `0x1800571fa`: `TeredoRioCreateWorkerThreads`
- `0x180057559`: `TeredoRioCreateWorkerThreads`
- `0x18005723c`: `Failed InitializeProcThreadAttributeList.`
- `0x1800572cf`: `Failed InitializeProcThreadAttributeList %d`
- `0x180057326`: `Failed UpdateProcThreadAttribute %d`
- `0x1800573db`: `Creating TeredoServerPrimaryCompletionQueueHandler.`
- `0x1800574fa`: `Failed to create worker thread. Error (%d)`
- `0x180057479`: `Failed to group affinitize worker thread. Error (%d)`
- `0x1800574c3`: `Failed to affinitize worker thread. Error (%d)`

## pseudocode

```c
__int64 __fastcall TeredoRioCreateWorkerThreads(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rbx
  __int64 v7; // rbx
  __int64 LastError; // rdi
  struct _PROC_THREAD_ATTRIBUTE_LIST *v9; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v10; // rsi
  __int64 v11; // rdx
  int v12; // r15d
  DWORD v13; // eax
  __int64 i; // rbp
  __int64 v15; // rax
  void *v16; // r12
  ULONG (__stdcall *v17)(PVOID); // rbx
  HANDLE CurrentProcess; // rax
  HANDLE RemoteThread; // rax
  void *v20; // rbx
  DWORD v21; // eax
  const wchar_t *v22; // rdx
  ULONG_PTR Size; // [rsp+48h] [rbp-60h] BYREF
  __int64 v27; // [rsp+50h] [rbp-58h]
  _GROUP_AFFINITY ProcessorMask; // [rsp+58h] [rbp-50h] BYREF

  v4 = a3;
  Size = 0;
  ProcessorMask = 0;
  EventWriteEnterEx(0x100000, L"TeredoRioCreateWorkerThreads");
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 2904LL) + 8 * v4);
  v27 = v7;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) )
  {
    v9 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(*(HANDLE *)(*(_QWORD *)a1 + 2576LL), 8u, Size);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      EventWriteError0(0x100000, L"Failed HeapAlloc %d", LastError);
      goto LABEL_30;
    }
    if ( !InitializeProcThreadAttributeList(v9, 1u, 0, &Size) )
    {
      LastError = GetLastError();
      EventWriteError0(0x100000, L"Failed InitializeProcThreadAttributeList %d", LastError);
LABEL_29:
      DeleteProcThreadAttributeList(v10);
      HeapFree(*(HANDLE *)(*(_QWORD *)a1 + 2576LL), 0, v10);
      goto LABEL_30;
    }
    if ( !UpdateProcThreadAttribute(v10, 0, 0x30005u, (PVOID)(v7 + 20), 4u, 0, 0) )
    {
      LastError = GetLastError();
      EventWriteError0(0x100000, L"Failed UpdateProcThreadAttribute %d", LastError);
      goto LABEL_29;
    }
    LODWORD(LastError) = 0;
    if ( GetNumaNodeProcessorMaskEx(*(_WORD *)(v7 + 24), &ProcessorMask) )
    {
      v12 = 1;
    }
    else
    {
      v12 = 0;
      v13 = GetLastError();
      EventWriteError0(0x100000, L"Failed GetNumaNodeProcessorMaskEx %d", v13);
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *(_DWORD *)(*(_QWORD *)a1 + 2888LL) )
        goto LABEL_29;
      if ( !(unsigned __int8)TeredoRioReferenceEx(a1 + 144, v11, 6183) )
      {
        LODWORD(LastError) = 21;
        EventWriteError0(0x100000, L"Failed TeredoRioReference %d", 21);
        goto LABEL_29;
      }
      v15 = 16LL * (unsigned int)i;
      v16 = (void *)(v15 + a2 + 176);
      *(_DWORD *)(v15 + a2 + 188) = i;
      *(_DWORD *)(v15 + a2 + 184) = a3;
      *(_QWORD *)(a2 + 16 * (i + 11)) = a1;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_IO,
          L"Creating TeredoServerPrimaryCompletionQueueHandler.");
      v17 = (ULONG (__stdcall *)(PVOID))TeredoRioServerPrimaryCompletionQueueHandler;
      if ( !a4 )
        v17 = TeredoRioServerSecondaryCompletionQueueHandler;
      CurrentProcess = GetCurrentProcess();
      RemoteThread = CreateRemoteThreadEx(CurrentProcess, 0, 0, v17, v16, 0, v10, 0);
      v20 = RemoteThread;
      if ( !RemoteThread )
      {
        LastError = GetLastError();
        EventWriteError0(0x100000, L"Failed to create worker thread. Error (%d)", LastError);
        TeredoRioDereferenceHelper(a1);
        goto LABEL_29;
      }
      if ( v12 )
      {
        if ( !SetThreadGroupAffinity(RemoteThread, &ProcessorMask, 0) )
        {
          v21 = GetLastError();
          v22 = L"Failed to group affinitize worker thread. Error (%d)";
LABEL_23:
          EventWriteError0(0x100000, v22, v21);
          goto LABEL_26;
        }
        if ( !SetThreadAffinityMask(v20, 1LL << *(_BYTE *)(v27 + 22)) )
        {
          v21 = GetLastError();
          v22 = L"Failed to affinitize worker thread. Error (%d)";
          goto LABEL_23;
        }
      }
LABEL_26:
      CloseHandle(v20);
    }
  }
  EventWriteError0(0x100000, L"Failed InitializeProcThreadAttributeList.");
  LODWORD(LastError) = 30;
LABEL_30:
  EventWriteLeaveEx(0x100000, L"TeredoRioCreateWorkerThreads");
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800571b0  mov     [rsp+arg_18], rbx
0x1800571b5  push    rbp
0x1800571b6  push    rsi
0x1800571b7  push    rdi
0x1800571b8  push    r12
0x1800571ba  push    r13
0x1800571bc  push    r14
0x1800571be  push    r15
0x1800571c0  sub     rsp, 70h
0x1800571c4  mov     rax, cs:__security_cookie
0x1800571cb  xor     rax, rsp
0x1800571ce  mov     [rsp+0A8h+var_40], rax
0x1800571d3  mov     ebx, r8d
0x1800571d6  mov     r13, rdx
0x1800571d9  mov     r14, rcx
0x1800571dc  mov     [rsp+0A8h+var_64], r9d
0x1800571e1  xorps   xmm0, xmm0
0x1800571e4  mov     [rsp+0A8h+var_68], ebx
0x1800571e8  mov     r12d, 100000h
0x1800571ee  mov     [rsp+0A8h+Size], 0
0x1800571f7  mov     ecx, r12d
0x1800571fa  lea     rdx, aTeredoriocreat_1; "TeredoRioCreateWorkerThreads"
0x180057201  movups  xmmword ptr [rsp+0A8h+ProcessorMask.Mask], xmm0
0x180057206  call    EventWriteEnterEx
0x18005720b  mov     rax, [r14]
0x18005720e  lea     r9, [rsp+0A8h+Size]; lpSize
0x180057213  xor     r8d, r8d; dwFlags
0x180057216  mov     rcx, [rax+0B58h]
0x18005721d  lea     edx, [r8+1]; dwAttributeCount
0x180057221  mov     rbx, [rcx+rbx*8]
0x180057225  xor     ecx, ecx; lpAttributeList
0x180057227  mov     [rsp+0A8h+var_58], rbx
0x18005722c  call    cs:__imp_InitializeProcThreadAttributeList
0x180057233  nop     dword ptr [rax+rax+00h]
0x180057238  test    eax, eax
0x18005723a  jz      short loc_180057255
0x18005723c  lea     rdx, aFailedInitiali; "Failed InitializeProcThreadAttributeLis"...
0x180057243  mov     ecx, r12d
0x180057246  call    EventWriteError0
0x18005724b  mov     edi, 1Eh
0x180057250  jmp     loc_180057559
0x180057255  mov     rcx, [r14]
0x180057258  mov     edx, 8; dwFlags
0x18005725d  mov     r8, [rsp+0A8h+Size]; dwBytes
0x180057262  mov     rcx, [rcx+0A10h]; hHeap
0x180057269  call    cs:__imp_HeapAlloc
0x180057270  nop     dword ptr [rax+rax+00h]
0x180057275  mov     rsi, rax
0x180057278  test    rax, rax
0x18005727b  jnz     short loc_1800572A2
0x18005727d  call    cs:__imp_GetLastError
0x180057284  nop     dword ptr [rax+rax+00h]
0x180057289  lea     rdx, aFailedHeapallo; "Failed HeapAlloc %d"
0x180057290  mov     ecx, r12d
0x180057293  mov     r8d, eax
0x180057296  mov     edi, eax
0x180057298  call    EventWriteError0
0x18005729d  jmp     loc_180057559
0x1800572a2  xor     r8d, r8d; dwFlags
0x1800572a5  lea     r9, [rsp+0A8h+Size]; lpSize
0x1800572aa  mov     rcx, rsi; lpAttributeList
0x1800572ad  lea     edx, [r8+1]; dwAttributeCount
0x1800572b1  call    cs:__imp_InitializeProcThreadAttributeList
0x1800572b8  nop     dword ptr [rax+rax+00h]
0x1800572bd  test    eax, eax
0x1800572bf  jnz     short loc_1800572DE
0x1800572c1  call    cs:__imp_GetLastError
0x1800572c8  nop     dword ptr [rax+rax+00h]
0x1800572cd  mov     edi, eax
0x1800572cf  lea     rdx, aFailedInitiali_0; "Failed InitializeProcThreadAttributeLis"...
0x1800572d6  mov     r8d, eax
0x1800572d9  jmp     loc_180057527
0x1800572de  mov     [rsp+0A8h+lpReturnSize], 0; lpReturnSize
0x1800572e7  lea     r9, [rbx+14h]; lpValue
0x1800572eb  mov     [rsp+0A8h+lpPreviousValue], 0; lpPreviousValue
0x1800572f4  xor     edx, edx; dwFlags
0x1800572f6  mov     r8d, 30005h; Attribute
0x1800572fc  mov     [rsp+0A8h+cbSize], 4; cbSize
0x180057305  mov     rcx, rsi; lpAttributeList
0x180057308  call    cs:__imp_UpdateProcThreadAttribute
0x18005730f  nop     dword ptr [rax+rax+00h]
0x180057314  test    eax, eax
0x180057316  jnz     short loc_180057335
0x180057318  call    cs:__imp_GetLastError
0x18005731f  nop     dword ptr [rax+rax+00h]
0x180057324  mov     edi, eax
0x180057326  lea     rdx, aFailedUpdatepr; "Failed UpdateProcThreadAttribute %d"
0x18005732d  mov     r8d, eax
0x180057330  jmp     loc_180057527
0x180057335  movzx   ecx, word ptr [rbx+18h]; Node
0x180057339  lea     rdx, [rsp+0A8h+ProcessorMask]; ProcessorMask
0x18005733e  xor     edi, edi
0x180057340  call    cs:__imp_GetNumaNodeProcessorMaskEx
0x180057347  nop     dword ptr [rax+rax+00h]
0x18005734c  test    eax, eax
0x18005734e  jz      short loc_180057356
0x180057350  lea     r15d, [rdi+1]
0x180057354  jmp     short loc_180057377
0x180057356  xor     r15d, r15d
0x180057359  call    cs:__imp_GetLastError
0x180057360  nop     dword ptr [rax+rax+00h]
0x180057365  lea     rdx, aFailedGetnuman; "Failed GetNumaNodeProcessorMaskEx %d"
0x18005736c  mov     ecx, r12d
0x18005736f  mov     r8d, eax
0x180057372  call    EventWriteError0
0x180057377  xor     ebp, ebp
0x180057379  mov     rax, [r14]
0x18005737c  cmp     ebp, [rax+0B48h]
0x180057382  jnb     loc_18005752F
0x180057388  lea     rcx, [r14+90h]
0x18005738f  mov     r8d, 1827h
0x180057395  call    TeredoRioReferenceEx
0x18005739a  test    al, al
0x18005739c  jz      loc_180057518
0x1800573a2  mov     edx, [rsp+0A8h+var_68]
0x1800573a6  lea     r12, [r13+0B0h]
0x1800573ad  mov     eax, ebp
0x1800573af  shl     rax, 4
0x1800573b3  add     r12, rax
0x1800573b6  mov     [rax+r13+0BCh], ebp
0x1800573be  mov     [rax+r13+0B8h], edx
0x1800573c6  lea     rax, [rbp+0Bh]
0x1800573ca  add     rax, rax
0x1800573cd  mov     [r13+rax*8+0], r14
0x1800573d2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x1800573d9  jz      short loc_1800573F5
0x1800573db  lea     r8, aCreatingTeredo; "Creating TeredoServerPrimaryCompletionQ"...
0x1800573e2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x1800573e9  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800573f0  call    McTemplateU0z_EventWriteTransfer
0x1800573f5  cmp     [rsp+0A8h+var_64], edi
0x1800573f9  lea     rax, TeredoRioServerSecondaryCompletionQueueHandler
0x180057400  lea     rbx, TeredoRioServerPrimaryCompletionQueueHandler
0x180057407  cmovz   rbx, rax
0x18005740b  call    cs:__imp_GetCurrentProcess
0x180057412  nop     dword ptr [rax+rax+00h]
0x180057417  mov     [rsp+0A8h+lpThreadId], rdi; lpThreadId
0x18005741c  mov     r9, rbx; lpStartAddress
0x18005741f  mov     [rsp+0A8h+lpReturnSize], rsi; lpAttributeList
0x180057424  mov     rcx, rax; hProcess
0x180057427  mov     dword ptr [rsp+0A8h+lpPreviousValue], edi; dwCreationFlags
0x18005742b  xor     r8d, r8d; dwStackSize
0x18005742e  xor     edx, edx; lpThreadAttributes
0x180057430  mov     [rsp+0A8h+cbSize], r12; lpParameter
0x180057435  call    cs:__imp_CreateRemoteThreadEx
0x18005743c  nop     dword ptr [rax+rax+00h]
0x180057441  mov     rbx, rax
0x180057444  test    rax, rax
0x180057447  jz      loc_1800574E8
0x18005744d  test    r15d, r15d
0x180057450  jz      short loc_1800574CC
0x180057452  xor     r8d, r8d; PreviousGroupAffinity
0x180057455  lea     rdx, [rsp+0A8h+ProcessorMask]; GroupAffinity
0x18005745a  mov     rcx, rax; hThread
0x18005745d  call    cs:__imp_SetThreadGroupAffinity
0x180057464  nop     dword ptr [rax+rax+00h]
0x180057469  test    eax, eax
0x18005746b  jnz     short loc_180057493
0x18005746d  call    cs:__imp_GetLastError
0x180057474  nop     dword ptr [rax+rax+00h]
0x180057479  lea     rdx, aFailedToGroupA; "Failed to group affinitize worker threa"...
0x180057480  mov     r12d, 100000h
0x180057486  mov     r8d, eax
0x180057489  mov     ecx, r12d
0x18005748c  call    EventWriteError0
0x180057491  jmp     short loc_1800574D2
0x180057493  mov     rax, [rsp+0A8h+var_58]
0x180057498  mov     edx, 1
0x18005749d  mov     cl, [rax+16h]
0x1800574a0  shl     rdx, cl; dwThreadAffinityMask
0x1800574a3  mov     rcx, rbx; hThread
0x1800574a6  call    cs:__imp_SetThreadAffinityMask
0x1800574ad  nop     dword ptr [rax+rax+00h]
0x1800574b2  test    rax, rax
0x1800574b5  jnz     short loc_1800574CC
0x1800574b7  call    cs:__imp_GetLastError
0x1800574be  nop     dword ptr [rax+rax+00h]
0x1800574c3  lea     rdx, aFailedToAffini; "Failed to affinitize worker thread. Err"...
0x1800574ca  jmp     short loc_180057480
0x1800574cc  mov     r12d, 100000h
0x1800574d2  mov     rcx, rbx; hObject
0x1800574d5  call    cs:__imp_CloseHandle
0x1800574dc  nop     dword ptr [rax+rax+00h]
0x1800574e1  inc     ebp
0x1800574e3  jmp     loc_180057379
0x1800574e8  call    cs:__imp_GetLastError
0x1800574ef  nop     dword ptr [rax+rax+00h]
0x1800574f4  mov     r12d, 100000h
0x1800574fa  lea     rdx, aFailedToCreate_3; "Failed to create worker thread. Error ("...
0x180057501  mov     r8d, eax
0x180057504  mov     ecx, r12d
0x180057507  mov     edi, eax
0x180057509  call    EventWriteError0
0x18005750e  mov     rcx, r14
0x180057511  call    TeredoRioDereferenceHelper
0x180057516  jmp     short loc_18005752F
0x180057518  mov     edi, 15h
0x18005751d  lea     rdx, aFailedTeredori; "Failed TeredoRioReference %d"
0x180057524  mov     r8d, edi
0x180057527  mov     ecx, r12d
0x18005752a  call    EventWriteError0
0x18005752f  mov     rcx, rsi; lpAttributeList
0x180057532  call    cs:__imp_DeleteProcThreadAttributeList
0x180057539  nop     dword ptr [rax+rax+00h]
0x18005753e  mov     rcx, [r14]
0x180057541  mov     r8, rsi; lpMem
0x180057544  xor     edx, edx; dwFlags
0x180057546  mov     rcx, [rcx+0A10h]; hHeap
0x18005754d  call    cs:__imp_HeapFree
0x180057554  nop     dword ptr [rax+rax+00h]
0x180057559  lea     rdx, aTeredoriocreat_1; "TeredoRioCreateWorkerThreads"
0x180057560  mov     ecx, r12d
0x180057563  call    EventWriteLeaveEx
0x180057568  mov     eax, edi
0x18005756a  mov     rcx, [rsp+0A8h+var_40]
0x18005756f  xor     rcx, rsp; StackCookie
0x180057572  call    __security_check_cookie
0x180057577  mov     rbx, [rsp+0A8h+arg_18]
0x18005757f  add     rsp, 70h
0x180057583  pop     r15
0x180057585  pop     r14
0x180057587  pop     r13
0x180057589  pop     r12
0x18005758b  pop     rdi
0x18005758c  pop     rsi
0x18005758d  pop     rbp
0x18005758e  retn
```
