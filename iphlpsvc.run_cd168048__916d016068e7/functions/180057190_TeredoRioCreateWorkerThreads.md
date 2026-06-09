# TeredoRioCreateWorkerThreads

- ea: `0x180057190`
- end: `0x180057570`
- name: `TeredoRioCreateWorkerThreads`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180056280`
- `0x180056c18`

## callees

- `0x180008200`
- `0x180009000`
- `0x1800190e0`
- `0x180024240`
- `0x180046ddc`
- `0x18004b630`
- `0x180057190`
- `0x180057ee8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057249`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057249`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005752d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005752d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005744d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005725d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005744d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800574c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574b5`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18005720c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180057291`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18005720c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180057291`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180057415`
- `api-ms-win-core-processthreads-l1-1-0!CreateRemoteThreadEx` at `0x180057415`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180057512`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180057512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800573eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800573eb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800572e8`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800572e8`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180057486`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x180057486`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x180057320`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x180057320`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x18005743d`
- `api-ms-win-core-processtopology-l1-1-0!SetThreadGroupAffinity` at `0x18005743d`

## string_xrefs

- `0x1800571da`: `TeredoRioCreateWorkerThreads`
- `0x180057539`: `TeredoRioCreateWorkerThreads`
- `0x18005721c`: `Failed InitializeProcThreadAttributeList.`
- `0x1800572af`: `Failed InitializeProcThreadAttributeList %d`
- `0x180057306`: `Failed UpdateProcThreadAttribute %d`
- `0x1800573bb`: `Creating TeredoServerPrimaryCompletionQueueHandler.`
- `0x1800574da`: `Failed to create worker thread. Error (%d)`
- `0x180057459`: `Failed to group affinitize worker thread. Error (%d)`
- `0x1800574a3`: `Failed to affinitize worker thread. Error (%d)`

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
0x180057190  mov     [rsp+arg_18], rbx
0x180057195  push    rbp
0x180057196  push    rsi
0x180057197  push    rdi
0x180057198  push    r12
0x18005719a  push    r13
0x18005719c  push    r14
0x18005719e  push    r15
0x1800571a0  sub     rsp, 70h
0x1800571a4  mov     rax, cs:__security_cookie
0x1800571ab  xor     rax, rsp
0x1800571ae  mov     [rsp+0A8h+var_40], rax
0x1800571b3  mov     ebx, r8d
0x1800571b6  mov     r13, rdx
0x1800571b9  mov     r14, rcx
0x1800571bc  mov     [rsp+0A8h+var_64], r9d
0x1800571c1  xorps   xmm0, xmm0
0x1800571c4  mov     [rsp+0A8h+var_68], ebx
0x1800571c8  mov     r12d, 100000h
0x1800571ce  mov     [rsp+0A8h+Size], 0
0x1800571d7  mov     ecx, r12d
0x1800571da  lea     rdx, aTeredoriocreat_1; "TeredoRioCreateWorkerThreads"
0x1800571e1  movups  xmmword ptr [rsp+0A8h+ProcessorMask.Mask], xmm0
0x1800571e6  call    EventWriteEnterEx
0x1800571eb  mov     rax, [r14]
0x1800571ee  lea     r9, [rsp+0A8h+Size]; lpSize
0x1800571f3  xor     r8d, r8d; dwFlags
0x1800571f6  mov     rcx, [rax+0B58h]
0x1800571fd  lea     edx, [r8+1]; dwAttributeCount
0x180057201  mov     rbx, [rcx+rbx*8]
0x180057205  xor     ecx, ecx; lpAttributeList
0x180057207  mov     [rsp+0A8h+var_58], rbx
0x18005720c  call    cs:__imp_InitializeProcThreadAttributeList
0x180057213  nop     dword ptr [rax+rax+00h]
0x180057218  test    eax, eax
0x18005721a  jz      short loc_180057235
0x18005721c  lea     rdx, aFailedInitiali; "Failed InitializeProcThreadAttributeLis"...
0x180057223  mov     ecx, r12d
0x180057226  call    EventWriteError0
0x18005722b  mov     edi, 1Eh
0x180057230  jmp     loc_180057539
0x180057235  mov     rcx, [r14]
0x180057238  mov     edx, 8; dwFlags
0x18005723d  mov     r8, [rsp+0A8h+Size]; dwBytes
0x180057242  mov     rcx, [rcx+0A10h]; hHeap
0x180057249  call    cs:__imp_HeapAlloc
0x180057250  nop     dword ptr [rax+rax+00h]
0x180057255  mov     rsi, rax
0x180057258  test    rax, rax
0x18005725b  jnz     short loc_180057282
0x18005725d  call    cs:__imp_GetLastError
0x180057264  nop     dword ptr [rax+rax+00h]
0x180057269  lea     rdx, aFailedHeapallo; "Failed HeapAlloc %d"
0x180057270  mov     ecx, r12d
0x180057273  mov     r8d, eax
0x180057276  mov     edi, eax
0x180057278  call    EventWriteError0
0x18005727d  jmp     loc_180057539
0x180057282  xor     r8d, r8d; dwFlags
0x180057285  lea     r9, [rsp+0A8h+Size]; lpSize
0x18005728a  mov     rcx, rsi; lpAttributeList
0x18005728d  lea     edx, [r8+1]; dwAttributeCount
0x180057291  call    cs:__imp_InitializeProcThreadAttributeList
0x180057298  nop     dword ptr [rax+rax+00h]
0x18005729d  test    eax, eax
0x18005729f  jnz     short loc_1800572BE
0x1800572a1  call    cs:__imp_GetLastError
0x1800572a8  nop     dword ptr [rax+rax+00h]
0x1800572ad  mov     edi, eax
0x1800572af  lea     rdx, aFailedInitiali_0; "Failed InitializeProcThreadAttributeLis"...
0x1800572b6  mov     r8d, eax
0x1800572b9  jmp     loc_180057507
0x1800572be  mov     [rsp+0A8h+lpReturnSize], 0; lpReturnSize
0x1800572c7  lea     r9, [rbx+14h]; lpValue
0x1800572cb  mov     [rsp+0A8h+lpPreviousValue], 0; lpPreviousValue
0x1800572d4  xor     edx, edx; dwFlags
0x1800572d6  mov     r8d, 30005h; Attribute
0x1800572dc  mov     [rsp+0A8h+cbSize], 4; cbSize
0x1800572e5  mov     rcx, rsi; lpAttributeList
0x1800572e8  call    cs:__imp_UpdateProcThreadAttribute
0x1800572ef  nop     dword ptr [rax+rax+00h]
0x1800572f4  test    eax, eax
0x1800572f6  jnz     short loc_180057315
0x1800572f8  call    cs:__imp_GetLastError
0x1800572ff  nop     dword ptr [rax+rax+00h]
0x180057304  mov     edi, eax
0x180057306  lea     rdx, aFailedUpdatepr; "Failed UpdateProcThreadAttribute %d"
0x18005730d  mov     r8d, eax
0x180057310  jmp     loc_180057507
0x180057315  movzx   ecx, word ptr [rbx+18h]; Node
0x180057319  lea     rdx, [rsp+0A8h+ProcessorMask]; ProcessorMask
0x18005731e  xor     edi, edi
0x180057320  call    cs:__imp_GetNumaNodeProcessorMaskEx
0x180057327  nop     dword ptr [rax+rax+00h]
0x18005732c  test    eax, eax
0x18005732e  jz      short loc_180057336
0x180057330  lea     r15d, [rdi+1]
0x180057334  jmp     short loc_180057357
0x180057336  xor     r15d, r15d
0x180057339  call    cs:__imp_GetLastError
0x180057340  nop     dword ptr [rax+rax+00h]
0x180057345  lea     rdx, aFailedGetnuman; "Failed GetNumaNodeProcessorMaskEx %d"
0x18005734c  mov     ecx, r12d
0x18005734f  mov     r8d, eax
0x180057352  call    EventWriteError0
0x180057357  xor     ebp, ebp
0x180057359  mov     rax, [r14]
0x18005735c  cmp     ebp, [rax+0B48h]
0x180057362  jnb     loc_18005750F
0x180057368  lea     rcx, [r14+90h]
0x18005736f  mov     r8d, 1827h
0x180057375  call    TeredoRioReferenceEx
0x18005737a  test    al, al
0x18005737c  jz      loc_1800574F8
0x180057382  mov     edx, [rsp+0A8h+var_68]
0x180057386  lea     r12, [r13+0B0h]
0x18005738d  mov     eax, ebp
0x18005738f  shl     rax, 4
0x180057393  add     r12, rax
0x180057396  mov     [rax+r13+0BCh], ebp
0x18005739e  mov     [rax+r13+0B8h], edx
0x1800573a6  lea     rax, [rbp+0Bh]
0x1800573aa  add     rax, rax
0x1800573ad  mov     [r13+rax*8+0], r14
0x1800573b2  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x1800573b9  jz      short loc_1800573D5
0x1800573bb  lea     r8, aCreatingTeredo; "Creating TeredoServerPrimaryCompletionQ"...
0x1800573c2  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_IO
0x1800573c9  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800573d0  call    McTemplateU0z_EventWriteTransfer
0x1800573d5  cmp     [rsp+0A8h+var_64], edi
0x1800573d9  lea     rax, TeredoRioServerSecondaryCompletionQueueHandler
0x1800573e0  lea     rbx, TeredoRioServerPrimaryCompletionQueueHandler
0x1800573e7  cmovz   rbx, rax
0x1800573eb  call    cs:__imp_GetCurrentProcess
0x1800573f2  nop     dword ptr [rax+rax+00h]
0x1800573f7  mov     [rsp+0A8h+lpThreadId], rdi; lpThreadId
0x1800573fc  mov     r9, rbx; lpStartAddress
0x1800573ff  mov     [rsp+0A8h+lpReturnSize], rsi; lpAttributeList
0x180057404  mov     rcx, rax; hProcess
0x180057407  mov     dword ptr [rsp+0A8h+lpPreviousValue], edi; dwCreationFlags
0x18005740b  xor     r8d, r8d; dwStackSize
0x18005740e  xor     edx, edx; lpThreadAttributes
0x180057410  mov     [rsp+0A8h+cbSize], r12; lpParameter
0x180057415  call    cs:__imp_CreateRemoteThreadEx
0x18005741c  nop     dword ptr [rax+rax+00h]
0x180057421  mov     rbx, rax
0x180057424  test    rax, rax
0x180057427  jz      loc_1800574C8
0x18005742d  test    r15d, r15d
0x180057430  jz      short loc_1800574AC
0x180057432  xor     r8d, r8d; PreviousGroupAffinity
0x180057435  lea     rdx, [rsp+0A8h+ProcessorMask]; GroupAffinity
0x18005743a  mov     rcx, rax; hThread
0x18005743d  call    cs:__imp_SetThreadGroupAffinity
0x180057444  nop     dword ptr [rax+rax+00h]
0x180057449  test    eax, eax
0x18005744b  jnz     short loc_180057473
0x18005744d  call    cs:__imp_GetLastError
0x180057454  nop     dword ptr [rax+rax+00h]
0x180057459  lea     rdx, aFailedToGroupA; "Failed to group affinitize worker threa"...
0x180057460  mov     r12d, 100000h
0x180057466  mov     r8d, eax
0x180057469  mov     ecx, r12d
0x18005746c  call    EventWriteError0
0x180057471  jmp     short loc_1800574B2
0x180057473  mov     rax, [rsp+0A8h+var_58]
0x180057478  mov     edx, 1
0x18005747d  mov     cl, [rax+16h]
0x180057480  shl     rdx, cl; dwThreadAffinityMask
0x180057483  mov     rcx, rbx; hThread
0x180057486  call    cs:__imp_SetThreadAffinityMask
0x18005748d  nop     dword ptr [rax+rax+00h]
0x180057492  test    rax, rax
0x180057495  jnz     short loc_1800574AC
0x180057497  call    cs:__imp_GetLastError
0x18005749e  nop     dword ptr [rax+rax+00h]
0x1800574a3  lea     rdx, aFailedToAffini; "Failed to affinitize worker thread. Err"...
0x1800574aa  jmp     short loc_180057460
0x1800574ac  mov     r12d, 100000h
0x1800574b2  mov     rcx, rbx; hObject
0x1800574b5  call    cs:__imp_CloseHandle
0x1800574bc  nop     dword ptr [rax+rax+00h]
0x1800574c1  inc     ebp
0x1800574c3  jmp     loc_180057359
0x1800574c8  call    cs:__imp_GetLastError
0x1800574cf  nop     dword ptr [rax+rax+00h]
0x1800574d4  mov     r12d, 100000h
0x1800574da  lea     rdx, aFailedToCreate_3; "Failed to create worker thread. Error ("...
0x1800574e1  mov     r8d, eax
0x1800574e4  mov     ecx, r12d
0x1800574e7  mov     edi, eax
0x1800574e9  call    EventWriteError0
0x1800574ee  mov     rcx, r14
0x1800574f1  call    TeredoRioDereferenceHelper
0x1800574f6  jmp     short loc_18005750F
0x1800574f8  mov     edi, 15h
0x1800574fd  lea     rdx, aFailedTeredori; "Failed TeredoRioReference %d"
0x180057504  mov     r8d, edi
0x180057507  mov     ecx, r12d
0x18005750a  call    EventWriteError0
0x18005750f  mov     rcx, rsi; lpAttributeList
0x180057512  call    cs:__imp_DeleteProcThreadAttributeList
0x180057519  nop     dword ptr [rax+rax+00h]
0x18005751e  mov     rcx, [r14]
0x180057521  mov     r8, rsi; lpMem
0x180057524  xor     edx, edx; dwFlags
0x180057526  mov     rcx, [rcx+0A10h]; hHeap
0x18005752d  call    cs:__imp_HeapFree
0x180057534  nop     dword ptr [rax+rax+00h]
0x180057539  lea     rdx, aTeredoriocreat_1; "TeredoRioCreateWorkerThreads"
0x180057540  mov     ecx, r12d
0x180057543  call    EventWriteLeaveEx
0x180057548  mov     eax, edi
0x18005754a  mov     rcx, [rsp+0A8h+var_40]
0x18005754f  xor     rcx, rsp; StackCookie
0x180057552  call    __security_check_cookie
0x180057557  mov     rbx, [rsp+0A8h+arg_18]
0x18005755f  add     rsp, 70h
0x180057563  pop     r15
0x180057565  pop     r14
0x180057567  pop     r13
0x180057569  pop     r12
0x18005756b  pop     rdi
0x18005756c  pop     rsi
0x18005756d  pop     rbp
0x18005756e  retn
```
