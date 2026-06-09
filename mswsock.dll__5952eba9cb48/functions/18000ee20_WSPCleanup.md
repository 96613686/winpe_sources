# WSPCleanup

- ea: `0x18000ee20`
- end: `0x18000f05f`
- name: `WSPCleanup`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c130`
- `0x18000ca20`
- `0x18000db30`
- `0x18000ee20`
- `0x18000f25c`
- `0x18000f2b8`
- `0x180038104`
- `0x18003ac78`
- `0x1800423ec`
- `0x180042eac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ee60`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ee60`
- `ntdll!RtlFreeHeap` at `0x18000eece`
- `ntdll!RtlFreeHeap` at `0x18000f00f`
- `ntdll!RtlFreeHeap` at `0x18000eece`
- `ntdll!RtlFreeHeap` at `0x18000f00f`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000ef68`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18000ef68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000efa0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000efa0`
- `WS2_32!WahEnumerateHandleContexts` at `0x18000ee9c`
- `WS2_32!WahEnumerateHandleContexts` at `0x18000ee9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ef52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ef8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ef52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ef8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efb8`

## string_xrefs

- `0x18000efb1`: `MSAFD: (cleanup) ... No APCs fired, keeping DLL ref count\n`
- `0x18000ef86`: `MSAFD: (cleanup) ... all APCs fired, lowering DLL ref count\n`

## pseudocode

```c
__int64 __fastcall WSPCleanup(_DWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v8; // eax
  LPVOID Value; // [rsp+58h] [rbp+10h] BYREF

  Value = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_sqqqq(
      (_DWORD)a1,
      11,
      (unsigned int)WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids,
      (unsigned int)"WSPCleanup",
      0,
      0,
      0,
      0);
  if ( !SockProcessTerminating && SockWspStartupCount && (Value = TlsGetValue(MSAFD_SockTlsSlot)) != 0
    || (v8 = SockEnterApiSlow(&Value)) == 0 )
  {
    v2 = 0;
    SockAcquireRwLockExclusive();
    if ( SockWspStartupCount == 1 )
    {
      WahEnumerateHandleContexts(SockContextTable, DeleteSockets, 0);
      SockFreeHelperDlls();
      if ( SockSanEnabled )
      {
        v2 = 1;
        SockSanCleanup();
      }
      if ( SockProtocolInfoArray )
      {
        RtlFreeHeap(SockPrivateHeap, 0, SockProtocolInfoArray);
        SockProtocolInfoArray = 0;
        SockProtocolInfoCount = 0;
      }
      if ( MswsockProtocolInfoArray )
      {
        RtlFreeHeap(SockPrivateHeap, 0, MswsockProtocolInfoArray);
        MswsockProtocolInfoArray = 0;
        MswsockProtocolInfoCount = 0;
      }
      SockTerminateAsyncThread();
      if ( SockProcessPendingAPCCount )
      {
        OutputDebugStringA("MSAFD: Pending APCs in cleanup! Waiting...\n");
        while ( SleepEx(0x3E8u, 1) && SockProcessPendingAPCCount )
          ;
        if ( SockProcessPendingAPCCount )
        {
          OutputDebugStringA("MSAFD: (cleanup) ... No APCs fired, keeping DLL ref count\n");
        }
        else
        {
          OutputDebugStringA("MSAFD: (cleanup) ... all APCs fired, lowering DLL ref count\n");
          FreeLibrary(SockModuleHandle);
        }
      }
    }
    --SockWspStartupCount;
    SockReleaseRwLockExclusive(v4, v3, v5, v6);
    if ( v2 )
      SockSanWaitForSockDupToComplete();
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 12, WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids);
    return 0;
  }
  else
  {
    *a1 = v8;
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18000ee20  mov     [rsp+arg_0], rbx
0x18000ee25  push    rdi
0x18000ee26  sub     rsp, 40h
0x18000ee2a  xor     edi, edi
0x18000ee2c  mov     rbx, rcx
0x18000ee2f  mov     [rsp+48h+arg_8], rdi
0x18000ee34  test    byte ptr cs:xmmword_180063D60, 2
0x18000ee3b  jnz     loc_18000EFC9
0x18000ee41  cmp     cs:SockProcessTerminating, dil
0x18000ee48  jnz     loc_18000EF32
0x18000ee4e  cmp     cs:SockWspStartupCount, edi
0x18000ee54  jbe     loc_18000EF32
0x18000ee5a  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000ee60  call    cs:__imp_TlsGetValue
0x18000ee67  nop     dword ptr [rax+rax+00h]
0x18000ee6c  mov     [rsp+48h+arg_8], rax
0x18000ee71  test    rax, rax
0x18000ee74  jz      loc_18000EF32
0x18000ee7a  mov     bl, dil
0x18000ee7d  call    SockAcquireRwLockExclusive
0x18000ee82  cmp     cs:SockWspStartupCount, 1
0x18000ee89  jnz     short loc_18000EF04
0x18000ee8b  mov     rcx, cs:SockContextTable
0x18000ee92  lea     rdx, DeleteSockets
0x18000ee99  xor     r8d, r8d
0x18000ee9c  call    cs:__imp_WahEnumerateHandleContexts
0x18000eea3  nop     dword ptr [rax+rax+00h]
0x18000eea8  call    SockFreeHelperDlls
0x18000eead  cmp     cs:SockSanEnabled, edi
0x18000eeb3  jnz     loc_18000EFFA
0x18000eeb9  mov     r8, cs:SockProtocolInfoArray; P
0x18000eec0  test    r8, r8
0x18000eec3  jz      short loc_18000EEE7
0x18000eec5  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000eecc  xor     edx, edx; Flags
0x18000eece  call    cs:__imp_RtlFreeHeap
0x18000eed5  nop     dword ptr [rax+rax+00h]
0x18000eeda  mov     cs:SockProtocolInfoArray, rdi
0x18000eee1  mov     cs:SockProtocolInfoCount, edi
0x18000eee7  mov     r8, cs:MswsockProtocolInfoArray; P
0x18000eeee  test    r8, r8
0x18000eef1  jnz     loc_18000F006
0x18000eef7  call    SockTerminateAsyncThread
0x18000eefc  cmp     cs:SockProcessPendingAPCCount, edi
0x18000ef02  jnz     short loc_18000EF4B
0x18000ef04  dec     cs:SockWspStartupCount
0x18000ef0a  call    SockReleaseRwLockExclusive
0x18000ef0f  test    bl, bl
0x18000ef11  jnz     loc_18000F03A
0x18000ef17  test    byte ptr cs:xmmword_180063D60, 2
0x18000ef1e  jnz     loc_18000F044
0x18000ef24  xor     eax, eax
0x18000ef26  mov     rbx, [rsp+48h+arg_0]
0x18000ef2b  add     rsp, 40h
0x18000ef2f  pop     rdi
0x18000ef30  retn
0x18000ef32  lea     rcx, [rsp+48h+arg_8]
0x18000ef37  call    SockEnterApiSlow
0x18000ef3c  test    eax, eax
0x18000ef3e  jz      loc_18000EE7A
0x18000ef44  mov     [rbx], eax
0x18000ef46  or      eax, 0FFFFFFFFh
0x18000ef49  jmp     short loc_18000EF26
0x18000ef4b  lea     rcx, OutputString; "MSAFD: Pending APCs in cleanup! Waiting"...
0x18000ef52  call    cs:__imp_OutputDebugStringA
0x18000ef59  nop     dword ptr [rax+rax+00h]
0x18000ef5e  mov     edx, 1; bAlertable
0x18000ef63  mov     ecx, 3E8h; dwMilliseconds
0x18000ef68  call    cs:__imp_SleepEx
0x18000ef6f  nop     dword ptr [rax+rax+00h]
0x18000ef74  mov     ecx, cs:SockProcessPendingAPCCount
0x18000ef7a  test    eax, eax
0x18000ef7c  jnz     loc_18000F02D
0x18000ef82  test    ecx, ecx
0x18000ef84  jnz     short loc_18000EFB1
0x18000ef86  lea     rcx, aMsafdCleanupAl; "MSAFD: (cleanup) ... all APCs fired, lo"...
0x18000ef8d  call    cs:__imp_OutputDebugStringA
0x18000ef94  nop     dword ptr [rax+rax+00h]
0x18000ef99  mov     rcx, cs:SockModuleHandle; hLibModule
0x18000efa0  call    cs:__imp_FreeLibrary
0x18000efa7  nop     dword ptr [rax+rax+00h]
0x18000efac  jmp     loc_18000EF04
0x18000efb1  lea     rcx, aMsafdCleanupNo; "MSAFD: (cleanup) ... No APCs fired, kee"...
0x18000efb8  call    cs:__imp_OutputDebugStringA
0x18000efbf  nop     dword ptr [rax+rax+00h]
0x18000efc4  jmp     loc_18000EF04
0x18000efc9  mov     [rsp+48h+var_10], rdi
0x18000efce  lea     r9, aWspcleanup; "WSPCleanup"
0x18000efd5  mov     [rsp+48h+var_18], rdi
0x18000efda  lea     r8, WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids
0x18000efe1  mov     [rsp+48h+var_20], rdi
0x18000efe6  mov     edx, 0Bh
0x18000efeb  mov     [rsp+48h+var_28], rdi
0x18000eff0  call    WPP_SF_sqqqq
0x18000eff5  jmp     loc_18000EE41
0x18000effa  mov     bl, 1
0x18000effc  call    SockSanCleanup
0x18000f001  jmp     loc_18000EEB9
0x18000f006  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000f00d  xor     edx, edx; Flags
0x18000f00f  call    cs:__imp_RtlFreeHeap
0x18000f016  nop     dword ptr [rax+rax+00h]
0x18000f01b  mov     cs:MswsockProtocolInfoArray, rdi
0x18000f022  mov     cs:MswsockProtocolInfoCount, edi
0x18000f028  jmp     loc_18000EEF7
0x18000f02d  test    ecx, ecx
0x18000f02f  jnz     loc_18000EF5E
0x18000f035  jmp     loc_18000EF82
0x18000f03a  call    SockSanWaitForSockDupToComplete
0x18000f03f  jmp     loc_18000EF17
0x18000f044  mov     edx, 0Ch
0x18000f049  lea     r8, WPP_89e6539435863adbd18cb3466bd38bc9_Traceguids
0x18000f050  mov     ecx, 401h
0x18000f055  call    WPP_SF_
0x18000f05a  jmp     loc_18000EF24
```
