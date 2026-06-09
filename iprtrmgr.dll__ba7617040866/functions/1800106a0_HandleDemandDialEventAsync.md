# HandleDemandDialEventAsync

- ea: `0x1800106a0`
- end: `0x180010b77`
- name: `HandleDemandDialEventAsync`
- size: `1239`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050e40`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x1800106a0`
- `0x180011914`
- `0x18005281c`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001094e`
- `ntdll!RtlReleaseResource` at `0x180010996`
- `ntdll!RtlReleaseResource` at `0x18001094e`
- `ntdll!RtlReleaseResource` at `0x180010996`
- `ntdll!RtlAcquireResourceShared` at `0x180010905`
- `ntdll!RtlAcquireResourceShared` at `0x180010905`
- `KERNEL32!GetOverlappedResult` at `0x180010766`
- `KERNEL32!GetOverlappedResult` at `0x180010766`
- `KERNEL32!GetLastError` at `0x180010a8f`
- `KERNEL32!GetLastError` at `0x180010a8f`
- `KERNEL32!HeapFree` at `0x180010a0f`
- `KERNEL32!HeapFree` at `0x180010a21`
- `KERNEL32!HeapFree` at `0x180010a0f`
- `KERNEL32!HeapFree` at `0x180010a21`
- `KERNEL32!HeapAlloc` at `0x180010817`
- `KERNEL32!HeapAlloc` at `0x180010889`
- `KERNEL32!HeapAlloc` at `0x180010817`
- `KERNEL32!HeapAlloc` at `0x180010889`
- `KERNEL32!LeaveCriticalSection` at `0x1800107f1`
- `KERNEL32!LeaveCriticalSection` at `0x180010804`
- `KERNEL32!LeaveCriticalSection` at `0x180010941`
- `KERNEL32!LeaveCriticalSection` at `0x1800107f1`
- `KERNEL32!LeaveCriticalSection` at `0x180010804`
- `KERNEL32!LeaveCriticalSection` at `0x180010941`
- `KERNEL32!EnterCriticalSection` at `0x180010797`
- `KERNEL32!EnterCriticalSection` at `0x180010929`
- `KERNEL32!EnterCriticalSection` at `0x180010797`
- `KERNEL32!EnterCriticalSection` at `0x180010929`

## string_xrefs

- `0x180010b1e`: `Leaving HandleDemandDialEventAsync. Error in completed IRP:%d`
- `0x180010979`: `HandleDemandDialEventAsync: QueueWorkItemInThreadPool failed with error %d`

## pseudocode

```c
__int64 __fastcall HandleDemandDialEventAsync(unsigned int a1)
{
  HANDLE v1; // rdi
  struct _OVERLAPPED *v3; // rbx
  int v4; // r14d
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  unsigned int v8; // ebx
  HANDLE v9; // rcx
  void *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r8
  struct _RTL_CRITICAL_SECTION *v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  void *v20; // r8
  const wchar_t *v21; // r8
  __int64 *v22; // rdx
  DWORD LastError; // eax
  char v24; // cl
  DWORD NumberOfBytesTransferred[4]; // [rsp+20h] [rbp-858h] BYREF
  int v26; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v27[2044]; // [rsp+34h] [rbp-844h] BYREF

  v1 = (HANDLE)g_hWanarpWriteV6;
  NumberOfBytesTransferred[0] = 0;
  v3 = (struct _OVERLAPPED *)g_V4NotificationWrapper;
  if ( a1 )
    v1 = g_hWanarpWrite;
  else
    v3 = &g_V6NotificationWrapper;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"Entered: %ws", L"HandleDemandDialEventAsync");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v26);
  }
  if ( !GetOverlappedResult(v1, v3, NumberOfBytesTransferred, 0) )
  {
    LastError = GetLastError();
    v24 = Microsoft_Windows_RRASEnableBits;
    v8 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"HandleDemandDialEventAsync::GetOVerlappedResult fails with 0x%x", LastError);
      v24 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v26);
        v24 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v8 == 995 )
    {
      PostIoctlForDemandDialNotification(a1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v21 = L"Leaving: HandleDemandDialEventAsync";
LABEL_56:
        v22 = RasRtrmgrTraceInfo;
LABEL_63:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v22, v21);
      }
    }
    else
    {
      if ( v8 != 2 )
      {
        if ( (v24 & 0x40) == 0 )
          return v8;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"Leaving HandleDemandDialEventAsync. Error in completed IRP:%d", v8);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          return v8;
        v21 = (const wchar_t *)&v26;
        v22 = RasRtrMgrTraceError;
        goto LABEL_63;
      }
      if ( v24 < 0 )
      {
        v21 = L"HandleDemandDialEventAsync. IRP cancelled. Wanarp device closed";
        goto LABEL_56;
      }
    }
    return v8;
  }
  if ( NumberOfBytesTransferred[0] >= 0x620 )
  {
    v4 = 1;
    EnterCriticalSection(&RouterStateLock);
    if ( (_DWORD)RouterState )
    {
      if ( LODWORD(v3[1].Internal) != 2 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, L"ProcessDemandDialEvent: Shutting down. Ignoring event %d");
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v26);
        }
        LeaveCriticalSection(&RouterStateLock);
        return 0;
      }
      v4 = 0;
    }
    LeaveCriticalSection(&RouterStateLock);
    v6 = HeapAlloc(IPRouterHeap, 0, 0x10u);
    v7 = v6;
    if ( !v6 )
    {
      v8 = 8;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(
          &v26,
          L"HandleDemandDialEventAsync. Not enough memory to allocate %d bytes for DEMAND_DIAL_AYNC_CONTEXT (Error:%d) ",
          16,
          8,
          *(_QWORD *)NumberOfBytesTransferred);
        goto LABEL_19;
      }
LABEL_37:
      if ( v4 )
        PostIoctlForDemandDialNotification(a1);
      if ( v8 && v7 )
      {
        v20 = (void *)*((_QWORD *)v7 + 1);
        if ( v20 )
          HeapFree(IPRouterHeap, 0, v20);
        HeapFree(IPRouterHeap, 0, v7);
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return v8;
      v21 = L"Leaving: HandleDemandDialEventAsync";
      v22 = RasRtrmgrTraceInfo;
      goto LABEL_63;
    }
    v9 = IPRouterHeap;
    *v6 = a1;
    v10 = HeapAlloc(v9, 0, 0x620u);
    *((_QWORD *)v7 + 1) = v10;
    if ( v10 )
    {
      memcpy_0(v10, &v3[1], 0x620u);
      if ( **((_DWORD **)v7 + 1) <= 2u )
      {
        RtlAcquireResourceShared(&Resource, 1u);
        v15 = (struct _RTL_CRITICAL_SECTION *)InterfaceLookupByICBSeqNumber(*(unsigned int *)(*((_QWORD *)v7 + 1) + 4LL));
        v16 = v15;
        if ( !v15 )
        {
          RtlReleaseResource(&Resource);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              &v26,
              L"HandleDemandDialEventAsync: InterfaceLookupByICBSeqNumber returned null for interface index %d",
              *(unsigned int *)(*((_QWORD *)v7 + 1) + 4LL));
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
          }
          v8 = 905;
          goto LABEL_37;
        }
        v17 = v15 + 18;
        EnterCriticalSection(v15 + 18);
        v7[1] = LODWORD(v16[19].DebugInfo)++;
        LeaveCriticalSection(v17);
        RtlReleaseResource(&Resource);
        v8 = QueueWorkItemInThreadPool(v19, v18, v7);
        if ( !v8 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_37;
        v14 = v8;
        LOWORD(v26) = 0;
      }
      else
      {
        v13 = QueueWorkItemInThreadPool(v12, v11, v7);
        v8 = v13;
        if ( !v13 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_37;
        v14 = v13;
        LOWORD(v26) = 0;
      }
      FormatRRASErrorString(&v26, L"HandleDemandDialEventAsync: QueueWorkItemInThreadPool failed with error %d", v14);
    }
    else
    {
      v8 = 8;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_37;
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"HandleDemandDialEventAsync. Not enough memory to allocate %d bytes for WANARP_NOTIFICATION (Error:%d) ",
        1568,
        8,
        *(_QWORD *)NumberOfBytesTransferred);
    }
LABEL_19:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
    goto LABEL_37;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"HandleDemandDialEventAsync. Error. Returned IRP small:%d");
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v26);
  }
  return 1003;
}

```

## disassembly

```asm
0x1800106a0  push    rbx
0x1800106a2  push    rsi
0x1800106a3  push    rdi
0x1800106a4  push    r13
0x1800106a6  push    r14
0x1800106a8  push    r15
0x1800106aa  sub     rsp, 848h
0x1800106b1  mov     rax, cs:__security_cookie
0x1800106b8  xor     rax, rsp
0x1800106bb  mov     [rsp+878h+var_48], rax
0x1800106c3  mov     rdi, cs:g_hWanarpWriteV6
0x1800106ca  lea     rax, g_V6NotificationWrapper
0x1800106d1  test    ecx, ecx
0x1800106d3  mov     [rsp+878h+NumberOfBytesTransferred], 0
0x1800106db  mov     r15d, ecx
0x1800106de  lea     rbx, g_V4NotificationWrapper
0x1800106e5  cmovnz  rdi, cs:g_hWanarpWrite
0x1800106ed  lea     rcx, [rsp+878h+var_844]; void *
0x1800106f2  cmovz   rbx, rax
0x1800106f6  mov     r8d, 7FCh; Size
0x1800106fc  xor     eax, eax
0x1800106fe  xor     edx, edx; Val
0x180010700  mov     [rsp+878h+var_848], eax
0x180010704  call    memset_0
0x180010709  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180010710  lea     rsi, RasRtrmgrTraceInfo
0x180010717  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001071e  jge     short loc_180010758
0x180010720  xor     eax, eax
0x180010722  lea     r8, aHandledemanddi_0; "HandleDemandDialEventAsync"
0x180010729  lea     rdx, aEnteredWs; "Entered: %ws"
0x180010730  mov     word ptr [rsp+878h+var_848], ax
0x180010735  lea     rcx, [rsp+878h+var_848]
0x18001073a  call    FormatRRASErrorString
0x18001073f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180010746  jge     short loc_180010758
0x180010748  lea     r8, [rsp+878h+var_848]
0x18001074d  mov     rdx, rsi
0x180010750  mov     rcx, r13
0x180010753  call    McTemplateU0z_EventWriteTransfer
0x180010758  xor     r9d, r9d; bWait
0x18001075b  lea     r8, [rsp+878h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180010760  mov     rdx, rbx; lpOverlapped
0x180010763  mov     rcx, rdi; hFile
0x180010766  call    cs:__imp_GetOverlappedResult
0x18001076c  test    eax, eax
0x18001076e  jz      loc_180010A8F
0x180010774  mov     r8d, [rsp+878h+NumberOfBytesTransferred]
0x180010779  mov     esi, 620h
0x18001077e  cmp     r8d, esi
0x180010781  jb      loc_180010A47
0x180010787  lea     rdi, RouterStateLock
0x18001078e  mov     r14d, 1
0x180010794  mov     rcx, rdi; lpCriticalSection
0x180010797  call    cs:__imp_EnterCriticalSection
0x18001079d  cmp     dword ptr cs:RouterState, 0
0x1800107a4  jz      short loc_180010801
0x1800107a6  mov     r8d, [rbx+20h]
0x1800107aa  cmp     r8d, 2
0x1800107ae  jz      short loc_1800107FE
0x1800107b0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800107b7  jge     short loc_1800107EE
0x1800107b9  xor     eax, eax
0x1800107bb  lea     rdx, aProcessdemandd; "ProcessDemandDialEvent: Shutting down. "...
0x1800107c2  lea     rcx, [rsp+878h+var_848]
0x1800107c7  mov     word ptr [rsp+878h+var_848], ax
0x1800107cc  call    FormatRRASErrorString
0x1800107d1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800107d8  jge     short loc_1800107EE
0x1800107da  lea     r8, [rsp+878h+var_848]
0x1800107df  mov     rcx, r13
0x1800107e2  lea     rdx, RasRtrmgrTraceInfo
0x1800107e9  call    McTemplateU0z_EventWriteTransfer
0x1800107ee  mov     rcx, rdi; lpCriticalSection
0x1800107f1  call    cs:__imp_LeaveCriticalSection
0x1800107f7  xor     eax, eax
0x1800107f9  jmp     loc_180010B56
0x1800107fe  xor     r14d, r14d
0x180010801  mov     rcx, rdi; lpCriticalSection
0x180010804  call    cs:__imp_LeaveCriticalSection
0x18001080a  mov     rcx, cs:IPRouterHeap; hHeap
0x180010811  xor     edx, edx; dwFlags
0x180010813  lea     r8d, [rdx+10h]; dwBytes
0x180010817  call    cs:__imp_HeapAlloc
0x18001081d  mov     rdi, rax
0x180010820  test    rax, rax
0x180010823  jnz     short loc_18001087A
0x180010825  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001082c  lea     ebx, [rax+8]
0x18001082f  jz      loc_1800109E7
0x180010835  xor     ecx, ecx
0x180010837  lea     r8d, [rax+10h]
0x18001083b  mov     word ptr [rsp+878h+var_848], cx
0x180010840  lea     rdx, aHandledemanddi_7; "HandleDemandDialEventAsync. Not enough "...
0x180010847  mov     r9d, ebx
0x18001084a  lea     rcx, [rsp+878h+var_848]
0x18001084f  call    FormatRRASErrorString
0x180010854  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001085b  jz      loc_1800109E7
0x180010861  lea     r8, [rsp+878h+var_848]
0x180010866  mov     rcx, r13
0x180010869  lea     rdx, RasRtrMgrTraceError
0x180010870  call    McTemplateU0z_EventWriteTransfer
0x180010875  jmp     loc_1800109E7
0x18001087a  mov     rcx, cs:IPRouterHeap; hHeap
0x180010881  mov     r8, rsi; dwBytes
0x180010884  xor     edx, edx; dwFlags
0x180010886  mov     [rax], r15d
0x180010889  call    cs:__imp_HeapAlloc
0x18001088f  mov     [rdi+8], rax
0x180010893  test    rax, rax
0x180010896  jnz     short loc_1800108B9
0x180010898  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001089f  lea     ebx, [rax+8]
0x1800108a2  jz      loc_1800109E7
0x1800108a8  mov     word ptr [rsp+878h+var_848], ax
0x1800108ad  lea     rdx, aHandledemanddi_11; "HandleDemandDialEventAsync. Not enough "...
0x1800108b4  mov     r8, rsi
0x1800108b7  jmp     short loc_180010847
0x1800108b9  mov     rcx, rax; void *
0x1800108bc  lea     rdx, [rbx+20h]; Src
0x1800108c0  mov     r8, rsi; Size
0x1800108c3  call    memcpy_0
0x1800108c8  mov     rax, [rdi+8]
0x1800108cc  cmp     dword ptr [rax], 2
0x1800108cf  jbe     short loc_1800108FC
0x1800108d1  mov     r8, rdi
0x1800108d4  call    QueueWorkItemInThreadPool
0x1800108d9  mov     ebx, eax
0x1800108db  test    eax, eax
0x1800108dd  jz      loc_1800109E7
0x1800108e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800108ea  jz      loc_1800109E7
0x1800108f0  xor     ecx, ecx
0x1800108f2  mov     r8d, eax
0x1800108f5  mov     word ptr [rsp+878h+var_848], cx
0x1800108fa  jmp     short loc_180010979
0x1800108fc  mov     dl, 1; Wait
0x1800108fe  lea     rcx, Resource; Resource
0x180010905  call    cs:__imp_RtlAcquireResourceShared
0x18001090b  mov     rcx, [rdi+8]
0x18001090f  mov     ecx, [rcx+4]
0x180010912  call    InterfaceLookupByICBSeqNumber
0x180010917  mov     rsi, rax
0x18001091a  test    rax, rax
0x18001091d  jz      short loc_18001098F
0x18001091f  lea     rbx, [rax+2D0h]
0x180010926  mov     rcx, rbx; lpCriticalSection
0x180010929  call    cs:__imp_EnterCriticalSection
0x18001092f  mov     ecx, [rsi+2F8h]
0x180010935  mov     [rdi+4], ecx
0x180010938  mov     rcx, rbx; lpCriticalSection
0x18001093b  inc     dword ptr [rsi+2F8h]
0x180010941  call    cs:__imp_LeaveCriticalSection
0x180010947  lea     rcx, Resource; Resource
0x18001094e  call    cs:__imp_RtlReleaseResource
0x180010954  mov     r8, rdi
0x180010957  call    QueueWorkItemInThreadPool
0x18001095c  mov     ebx, eax
0x18001095e  test    eax, eax
0x180010960  jz      loc_1800109E7
0x180010966  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001096d  jz      short loc_1800109E7
0x18001096f  xor     eax, eax
0x180010971  mov     r8d, ebx
0x180010974  mov     word ptr [rsp+878h+var_848], ax
0x180010979  lea     rdx, aHandledemanddi_10; "HandleDemandDialEventAsync: QueueWorkIt"...
0x180010980  lea     rcx, [rsp+878h+var_848]
0x180010985  call    FormatRRASErrorString
0x18001098a  jmp     loc_180010854
0x18001098f  lea     rcx, Resource; Resource
0x180010996  call    cs:__imp_RtlReleaseResource
0x18001099c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800109a3  jz      short loc_1800109E2
0x1800109a5  xor     eax, eax
0x1800109a7  lea     rdx, aHandledemanddi_6; "HandleDemandDialEventAsync: InterfaceLo"...
0x1800109ae  mov     word ptr [rsp+878h+var_848], ax
0x1800109b3  lea     rcx, [rsp+878h+var_848]
0x1800109b8  mov     r8, [rdi+8]
0x1800109bc  mov     r8d, [r8+4]
0x1800109c0  call    FormatRRASErrorString
0x1800109c5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800109cc  jz      short loc_1800109E2
0x1800109ce  lea     r8, [rsp+878h+var_848]
0x1800109d3  mov     rcx, r13
0x1800109d6  lea     rdx, RasRtrMgrTraceError
0x1800109dd  call    McTemplateU0z_EventWriteTransfer
0x1800109e2  mov     ebx, 389h
0x1800109e7  test    r14d, r14d
0x1800109ea  jz      short loc_1800109F4
0x1800109ec  mov     ecx, r15d
0x1800109ef  call    PostIoctlForDemandDialNotification
0x1800109f4  test    ebx, ebx
0x1800109f6  jz      short loc_180010A27
0x1800109f8  test    rdi, rdi
0x1800109fb  jz      short loc_180010A27
0x1800109fd  mov     r8, [rdi+8]; lpMem
0x180010a01  test    r8, r8
0x180010a04  jz      short loc_180010A15
0x180010a06  mov     rcx, cs:IPRouterHeap; hHeap
0x180010a0d  xor     edx, edx; dwFlags
0x180010a0f  call    cs:__imp_HeapFree
0x180010a15  mov     rcx, cs:IPRouterHeap; hHeap
0x180010a1c  mov     r8, rdi; lpMem
0x180010a1f  xor     edx, edx; dwFlags
0x180010a21  call    cs:__imp_HeapFree
0x180010a27  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180010a2e  jz      loc_180010B54
0x180010a34  lea     r8, aLeavingHandled_0; "Leaving: HandleDemandDialEventAsync"
0x180010a3b  lea     rdx, RasRtrmgrTraceInfo
0x180010a42  jmp     loc_180010B4C
0x180010a47  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180010a4e  jz      short loc_180010A85
0x180010a50  xor     eax, eax
0x180010a52  lea     rdx, aHandledemanddi_12; "HandleDemandDialEventAsync. Error. Retu"...
0x180010a59  lea     rcx, [rsp+878h+var_848]
0x180010a5e  mov     word ptr [rsp+878h+var_848], ax
0x180010a63  call    FormatRRASErrorString
0x180010a68  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180010a6f  jz      short loc_180010A85
0x180010a71  lea     r8, [rsp+878h+var_848]
0x180010a76  mov     rcx, r13
0x180010a79  lea     rdx, RasRtrMgrTraceError
0x180010a80  call    McTemplateU0z_EventWriteTransfer
0x180010a85  mov     eax, 3EBh
0x180010a8a  jmp     loc_180010B56
0x180010a8f  call    cs:__imp_GetLastError
0x180010a95  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180010a9c  mov     ebx, eax
0x180010a9e  test    cl, cl
0x180010aa0  jns     short loc_180010ADF
0x180010aa2  xor     ecx, ecx
0x180010aa4  lea     rdx, aHandledemanddi_2; "HandleDemandDialEventAsync::GetOVerlapp"...
0x180010aab  mov     word ptr [rsp+878h+var_848], cx
0x180010ab0  mov     r8d, eax
0x180010ab3  lea     rcx, [rsp+878h+var_848]
0x180010ab8  call    FormatRRASErrorString
0x180010abd  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180010ac4  test    cl, cl
0x180010ac6  jns     short loc_180010ADF
0x180010ac8  lea     r8, [rsp+878h+var_848]
0x180010acd  mov     rdx, rsi
0x180010ad0  mov     rcx, r13
0x180010ad3  call    McTemplateU0z_EventWriteTransfer
0x180010ad8  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180010adf  cmp     ebx, 3E3h
0x180010ae5  jnz     short loc_180010B04
0x180010ae7  mov     ecx, r15d
0x180010aea  call    PostIoctlForDemandDialNotification
0x180010aef  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180010af6  jz      short loc_180010B54
0x180010af8  lea     r8, aLeavingHandled_0; "Leaving: HandleDemandDialEventAsync"
0x180010aff  mov     rdx, rsi
0x180010b02  jmp     short loc_180010B4C
0x180010b04  cmp     ebx, 2
0x180010b07  jnz     short loc_180010B17
0x180010b09  test    cl, 80h
0x180010b0c  jz      short loc_180010B54
0x180010b0e  lea     r8, aHandledemanddi_8; "HandleDemandDialEventAsync. IRP cancell"...
0x180010b15  jmp     short loc_180010AFF
0x180010b17  test    cl, 40h
0x180010b1a  jz      short loc_180010B54
0x180010b1c  xor     eax, eax
0x180010b1e  lea     rdx, aLeavingHandled_1; "Leaving HandleDemandDialEventAsync. Err"...
0x180010b25  mov     r8d, ebx
0x180010b28  mov     word ptr [rsp+878h+var_848], ax
0x180010b2d  lea     rcx, [rsp+878h+var_848]
0x180010b32  call    FormatRRASErrorString
0x180010b37  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180010b3e  jz      short loc_180010B54
0x180010b40  lea     r8, [rsp+878h+var_848]
0x180010b45  lea     rdx, RasRtrMgrTraceError
0x180010b4c  mov     rcx, r13
0x180010b4f  call    McTemplateU0z_EventWriteTransfer
0x180010b54  mov     eax, ebx
0x180010b56  mov     rcx, [rsp+878h+var_48]
0x180010b5e  xor     rcx, rsp; StackCookie
0x180010b61  call    __security_check_cookie
0x180010b66  add     rsp, 848h
0x180010b6d  pop     r15
0x180010b6f  pop     r14
0x180010b71  pop     r13
0x180010b73  pop     rdi
0x180010b74  pop     rsi
0x180010b75  pop     rbx
0x180010b76  retn
```
