# SockAsyncThread

- ea: `0x180017810`
- end: `0x180017ac9`
- name: `SockAsyncThread`
- size: `697`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180017810`
- `0x180038104`
- `0x180038634`
- `0x18003aec4`
- `0x18003d540`
- `0x180042bc8`
- `0x18004abd0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001785b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001785b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001786f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001786f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180017885`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180017885`
- `ntdll!NtRemoveIoCompletion` at `0x1800178bc`
- `ntdll!NtRemoveIoCompletion` at `0x1800178bc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017a85`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017a85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800179c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800179c3`

## pseudocode

```c
__int64 __fastcall SockAsyncThread(_QWORD *Parameter)
{
  HMODULE v1; // rsi
  DWORD v3; // ecx
  HANDLE CurrentThread; // rax
  union _LARGE_INTEGER *Timeout; // rcx
  unsigned int v6; // edi
  __int64 result; // rax
  const char *v8; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-10h] BYREF
  PVOID CompletionKey; // [rsp+60h] [rbp+20h] BYREF
  PVOID CompletionContext; // [rsp+68h] [rbp+28h] BYREF

  v1 = (HMODULE)Parameter[3];
  IoStatusBlock = 0;
  CompletionContext = 0;
  CompletionKey = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 17, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids);
  v3 = MSAFD_SockTlsSlot;
  Parameter[3] = -1;
  if ( TlsSetValue(v3, Parameter) )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 1);
    while ( 1 )
    {
      while ( 1 )
      {
        Timeout = (union _LARGE_INTEGER *)&qword_180055818;
        if ( SockAsyncThreadReferenceCount > 1 )
          Timeout = 0;
        v6 = NtRemoveIoCompletion(SockAsyncQueuePort, &CompletionKey, &CompletionContext, &IoStatusBlock, Timeout);
        if ( !v6 )
          break;
        if ( v6 == 258 && (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 18, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids);
        if ( SockAsyncThreadReferenceCount > 1 && (v6 & 0xC0000000) == 0xC0000000 )
        {
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_l(3221225472LL, 19, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, v6);
          Sleep(0x3E8u);
        }
        if ( v6 != 258 )
          goto LABEL_12;
LABEL_27:
        if ( _InterlockedCompareExchange(&SockAsyncThreadReferenceCount, 0, 1) == 1 )
        {
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            if ( CompletionKey == (PVOID)-1LL || (v8 = "idle timeout", !SockWspStartupCount) )
              v8 = "cleanup";
            WPP_SF_s(0, 20, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids, v8);
          }
          FreeLibraryAndExitThread(v1, 0);
        }
      }
      if ( CompletionKey == (PVOID)-1LL )
      {
        _InterlockedDecrement(&SockAsyncThreadReferenceCount);
        goto LABEL_27;
      }
      if ( CompletionKey == SockAsyncConnectCompletion
        || CompletionKey == SockAsyncSelectCompletion
        || CompletionKey == SockProcessQueuedAsyncSelect
        || CompletionKey == SockSanAsyncFreeProvider
        || CompletionKey == SockSanDupSockCtrlMsg
        || CompletionKey == SockSanProviderChange
        || CompletionKey == SockSanResumeDuplicationStub )
      {
        ((void (__fastcall *)(PVOID, struct _IO_STATUS_BLOCK *))CompletionKey)(CompletionContext, &IoStatusBlock);
      }
      else if ( CompletionKey == SockSanCompletion )
      {
        if ( CompletionContext == &SockSanAddressNotifyContext )
          SockSanProviderAddressUpdate(CompletionContext);
        else
          SockSanCompletion(CompletionContext, &IoStatusBlock);
      }
      else
      {
        SockSanRedirectRequest(CompletionKey, CompletionContext, &IoStatusBlock);
      }
LABEL_12:
      if ( !SockWspStartupCount )
        goto LABEL_27;
    }
  }
  result = 1;
  MSAFD_SockTlsSlot = -1;
  _InterlockedDecrement(&SockAsyncThreadReferenceCount);
  return result;
}

```

## disassembly

```asm
0x180017810  mov     [rsp-18h+arg_10], rbx
0x180017815  push    rbp
0x180017816  push    rsi
0x180017817  push    rdi
0x180017818  mov     rbp, rsp
0x18001781b  sub     rsp, 40h
0x18001781f  mov     rsi, [rcx+18h]
0x180017823  xorps   xmm0, xmm0
0x180017826  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001782a  mov     rbx, rcx
0x18001782d  mov     [rbp+CompletionContext], 0
0x180017835  mov     [rbp+CompletionKey], 0
0x18001783d  test    byte ptr cs:xmmword_180063D60, 2
0x180017844  jnz     loc_180017A15
0x18001784a  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180017850  mov     rdx, rbx; lpTlsValue
0x180017853  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18001785b  call    cs:__imp_TlsSetValue
0x180017862  nop     dword ptr [rax+rax+00h]
0x180017867  test    eax, eax
0x180017869  jz      loc_1800179F1
0x18001786f  call    cs:__imp_GetCurrentThread
0x180017876  nop     dword ptr [rax+rax+00h]
0x18001787b  mov     ebx, 1
0x180017880  mov     rcx, rax; hThread
0x180017883  mov     edx, ebx; nPriority
0x180017885  call    cs:__imp_SetThreadPriority
0x18001788c  nop     dword ptr [rax+rax+00h]
0x180017891  xor     eax, eax
0x180017893  lea     rcx, qword_180055818
0x18001789a  cmp     cs:SockAsyncThreadReferenceCount, ebx
0x1800178a0  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800178a4  lea     r8, [rbp+CompletionContext]; CompletionContext
0x1800178a8  cmovg   rcx, rax
0x1800178ac  lea     rdx, [rbp+CompletionKey]; CompletionKey
0x1800178b0  mov     [rsp+40h+Timeout], rcx; Timeout
0x1800178b5  mov     rcx, cs:SockAsyncQueuePort; IoCompletionHandle
0x1800178bc  call    cs:__imp_NtRemoveIoCompletion
0x1800178c3  nop     dword ptr [rax+rax+00h]
0x1800178c8  mov     edi, eax
0x1800178ca  test    eax, eax
0x1800178cc  jnz     loc_180017976
0x1800178d2  mov     rax, [rbp+CompletionKey]
0x1800178d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800178da  jz      loc_180017998
0x1800178e0  mov     rcx, [rbp+CompletionContext]
0x1800178e4  lea     rdx, SockAsyncConnectCompletion
0x1800178eb  cmp     rax, rdx
0x1800178ee  jz      short loc_1800178FC
0x1800178f0  lea     rdx, SockAsyncSelectCompletion
0x1800178f7  cmp     rax, rdx
0x1800178fa  jnz     short loc_180017913
0x1800178fc  lea     rdx, [rbp+IoStatusBlock]
0x180017900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017905  cmp     cs:SockWspStartupCount, 0
0x18001790c  ja      short loc_180017891
0x18001790e  jmp     loc_18001799F
0x180017913  lea     rdx, SockProcessQueuedAsyncSelect
0x18001791a  cmp     rax, rdx
0x18001791d  jz      short loc_1800178FC
0x18001791f  lea     rdx, SockSanAsyncFreeProvider
0x180017926  cmp     rax, rdx
0x180017929  jz      short loc_1800178FC
0x18001792b  lea     rdx, SockSanDupSockCtrlMsg
0x180017932  cmp     rax, rdx
0x180017935  jz      short loc_1800178FC
0x180017937  lea     rdx, SockSanProviderChange
0x18001793e  cmp     rax, rdx
0x180017941  jz      short loc_1800178FC
0x180017943  lea     rdx, SockSanResumeDuplicationStub
0x18001794a  cmp     rax, rdx
0x18001794d  jz      short loc_1800178FC
0x18001794f  lea     rdx, SockSanCompletion
0x180017956  cmp     rax, rdx
0x180017959  jnz     loc_180017A3E
0x18001795f  lea     rax, SockSanAddressNotifyContext
0x180017966  cmp     rcx, rax
0x180017969  jnz     loc_180017A30
0x18001796f  call    SockSanProviderAddressUpdate
0x180017974  jmp     short loc_180017905
0x180017976  cmp     edi, 102h
0x18001797c  jz      short loc_1800179D0
0x18001797e  cmp     cs:SockAsyncThreadReferenceCount, ebx
0x180017984  jg      loc_180017A52
0x18001798a  cmp     edi, 102h
0x180017990  jnz     loc_180017905
0x180017996  jmp     short loc_18001799F
0x180017998  lock dec cs:SockAsyncThreadReferenceCount
0x18001799f  xor     ecx, ecx
0x1800179a1  mov     eax, ebx
0x1800179a3  lock cmpxchg cs:SockAsyncThreadReferenceCount, ecx
0x1800179ab  jnz     loc_180017891
0x1800179b1  test    byte ptr cs:xmmword_180063D60, 2
0x1800179b8  jnz     loc_180017A96
0x1800179be  xor     edx, edx; dwExitCode
0x1800179c0  mov     rcx, rsi; hLibModule
0x1800179c3  call    cs:__imp_FreeLibraryAndExitThread
0x1800179ca  nop     dword ptr [rax+rax+00h]
0x1800179cf  int     3; Trap to Debugger
0x1800179d0  test    byte ptr cs:xmmword_180063D60, 2
0x1800179d7  jz      short loc_18001797E
0x1800179d9  mov     edx, 12h
0x1800179de  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x1800179e5  mov     ecx, 401h
0x1800179ea  call    WPP_SF_
0x1800179ef  jmp     short loc_18001797E
0x1800179f1  mov     rbx, [rsp+40h+arg_10]
0x1800179f6  mov     eax, 1
0x1800179fb  mov     cs:MSAFD_SockTlsSlot, 0FFFFFFFFh
0x180017a05  lock dec cs:SockAsyncThreadReferenceCount
0x180017a0c  add     rsp, 40h
0x180017a10  pop     rdi
0x180017a11  pop     rsi
0x180017a12  pop     rbp
0x180017a13  retn
0x180017a15  mov     edx, 11h
0x180017a1a  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x180017a21  mov     ecx, 401h
0x180017a26  call    WPP_SF_
0x180017a2b  jmp     loc_18001784A
0x180017a30  lea     rdx, [rbp+IoStatusBlock]
0x180017a34  call    SockSanCompletion
0x180017a39  jmp     loc_180017905
0x180017a3e  mov     rdx, rcx
0x180017a41  lea     r8, [rbp+IoStatusBlock]
0x180017a45  mov     rcx, rax
0x180017a48  call    SockSanRedirectRequest
0x180017a4d  jmp     loc_180017905
0x180017a52  mov     ecx, 0C0000000h
0x180017a57  mov     eax, edi
0x180017a59  and     eax, ecx
0x180017a5b  cmp     eax, ecx
0x180017a5d  jnz     loc_18001798A
0x180017a63  test    byte ptr cs:xmmword_180063D60, 2
0x180017a6a  jz      short loc_180017A80
0x180017a6c  mov     edx, 13h
0x180017a71  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x180017a78  mov     r9d, edi
0x180017a7b  call    WPP_SF_l
0x180017a80  mov     ecx, 3E8h; dwMilliseconds
0x180017a85  call    cs:__imp_Sleep
0x180017a8c  nop     dword ptr [rax+rax+00h]
0x180017a91  jmp     loc_18001798A
0x180017a96  cmp     [rbp+CompletionKey], 0FFFFFFFFFFFFFFFFh
0x180017a9b  jz      short loc_180017AAC
0x180017a9d  cmp     cs:SockWspStartupCount, ecx
0x180017aa3  lea     r9, aIdleTimeout; "idle timeout"
0x180017aaa  jnz     short loc_180017AB3
0x180017aac  lea     r9, aCleanup; "cleanup"
0x180017ab3  mov     edx, 14h
0x180017ab8  lea     r8, WPP_af4e820e49c9345cba0bf06efab8bbeb_Traceguids
0x180017abf  call    WPP_SF_s
0x180017ac4  jmp     loc_1800179BE
```
