# MSWSOCK_Initialize

- ea: `0x18000dbb0`
- end: `0x18000ddf3`
- name: `MSWSOCK_Initialize`
- size: `579`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000cc50`
- `0x18000ecc0`
- `0x180020d30`

## callees

- `0x18000dbb0`
- `0x18000e378`
- `0x18000e3dc`
- `0x18001e0e0`
- `0x18001e560`
- `0x180038104`
- `0x180038118`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000dcf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000dcf2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000dca3`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000dca3`
- `ntdll!RtlAllocateHeap` at `0x18000dbfe`
- `ntdll!RtlDestroyHeap` at `0x18000dd6e`
- `ntdll!RtlDestroyHeap` at `0x18000dd6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dd3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dc54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dc85`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dc54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dc85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcc7`

## pseudocode

```c
__int64 MSWSOCK_Initialize()
{
  int v1; // edi
  int v2; // esi
  __int64 v3; // rcx
  DWORD LastError; // eax
  __int64 v5; // rcx

  if ( SockAllocateHeapRoutine )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 10, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids);
    return 1;
  }
  v1 = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_q(1025, 11, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids, NtCurrentPeb());
  SockProcessTerminating = 0;
  SockAllocateHeapRoutine = (__int64)RtlAllocateHeap;
  SockPrivateHeap = NtCurrentPeb()->ProcessHeap;
  qword_180063E38 = (__int64)&SockHelperDllListHead;
  SockHelperDllListHead = (__int64)&SockHelperDllListHead;
  if ( (int)SockInitializeRwLockAndSpinCount(SockPrivateHeap) < 0 )
  {
    v2 = 0;
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 12, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids);
  }
  else
  {
    v1 = 1;
    v2 = 1;
    InitializeCriticalSection(&MSWSOCK_SocketLock);
    Rnr_ProcessInit(v3);
    qword_180064078 = (__int64)&WinsockTlsDataList;
    WinsockTlsDataList = &WinsockTlsDataList;
    InitializeCriticalSection(&WinsockTlsDataListLock);
    WinsockTlsDataListLock_initialized = 1;
    MSAFD_SockTlsSlot = TlsAlloc();
    if ( MSAFD_SockTlsSlot != -1 )
      return 1;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_l(v5, 13, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids, LastError);
    }
  }
  if ( MSAFD_SockTlsSlot != -1 )
  {
    TlsFree(MSAFD_SockTlsSlot);
    MSAFD_SockTlsSlot = -1;
  }
  Rnr_ProcessCleanup();
  if ( v1 )
    DeleteCriticalSection(&MSWSOCK_SocketLock);
  if ( v2 )
    SockDeleteRwLock();
  if ( WinsockTlsDataListLock_initialized )
  {
    DeleteCriticalSection(&WinsockTlsDataListLock);
    WinsockTlsDataListLock_initialized = 0;
  }
  if ( SockPrivateHeap != NtCurrentPeb()->ProcessHeap && SockPrivateHeap )
    RtlDestroyHeap(SockPrivateHeap);
  SockAllocateHeapRoutine = 0;
  return 0;
}

```

## disassembly

```asm
0x18000dbb0  mov     [rsp+arg_8], rsi
0x18000dbb5  push    rdi
0x18000dbb6  sub     rsp, 30h
0x18000dbba  cmp     cs:SockAllocateHeapRoutine, 0
0x18000dbc2  jz      short loc_18000DBE4
0x18000dbc4  test    byte ptr cs:xmmword_180063D60, 2
0x18000dbcb  jnz     loc_18000DD8C
0x18000dbd1  mov     edi, 1
0x18000dbd6  mov     eax, edi
0x18000dbd8  mov     rsi, [rsp+38h+arg_8]
0x18000dbdd  add     rsp, 30h
0x18000dbe1  pop     rdi
0x18000dbe2  retn
0x18000dbe4  xor     edi, edi
0x18000dbe6  mov     [rsp+38h+var_18], edi
0x18000dbea  test    byte ptr cs:xmmword_180063D60, 2
0x18000dbf1  jnz     loc_18000DDA7
0x18000dbf7  mov     cs:SockProcessTerminating, dil
0x18000dbfe  mov     rax, cs:__imp_RtlAllocateHeap
0x18000dc05  mov     cs:SockAllocateHeapRoutine, rax
0x18000dc0c  mov     rax, gs:60h
0x18000dc15  mov     rcx, [rax+30h]
0x18000dc19  mov     cs:SockPrivateHeap, rcx
0x18000dc20  lea     rax, SockHelperDllListHead
0x18000dc27  mov     cs:qword_180063E38, rax
0x18000dc2e  mov     cs:SockHelperDllListHead, rax
0x18000dc35  call    SockInitializeRwLockAndSpinCount
0x18000dc3a  test    eax, eax
0x18000dc3c  js      loc_18000DDCB
0x18000dc42  mov     edi, 1
0x18000dc47  mov     esi, edi
0x18000dc49  mov     [rsp+38h+arg_0], edi
0x18000dc4d  lea     rcx, MSWSOCK_SocketLock; lpCriticalSection
0x18000dc54  call    cs:__imp_InitializeCriticalSection
0x18000dc5b  nop     dword ptr [rax+rax+00h]
0x18000dc60  mov     [rsp+38h+var_18], edi
0x18000dc64  call    Rnr_ProcessInit
0x18000dc69  lea     rax, WinsockTlsDataList
0x18000dc70  mov     cs:qword_180064078, rax
0x18000dc77  mov     cs:WinsockTlsDataList, rax
0x18000dc7e  lea     rcx, WinsockTlsDataListLock; lpCriticalSection
0x18000dc85  call    cs:__imp_InitializeCriticalSection
0x18000dc8c  nop     dword ptr [rax+rax+00h]
0x18000dc91  mov     cs:WinsockTlsDataListLock_initialized, edi
0x18000dc97  jmp     short loc_18000DCA3
0x18000dc99  mov     esi, [rsp+38h+arg_0]
0x18000dc9d  mov     edi, [rsp+38h+var_18]
0x18000dca1  jmp     short loc_18000DCE7
0x18000dca3  call    cs:__imp_TlsAlloc
0x18000dcaa  nop     dword ptr [rax+rax+00h]
0x18000dcaf  mov     cs:MSAFD_SockTlsSlot, eax
0x18000dcb5  cmp     eax, 0FFFFFFFFh
0x18000dcb8  jnz     loc_18000DBD6
0x18000dcbe  test    byte ptr cs:xmmword_180063D60, 2
0x18000dcc5  jz      short loc_18000DCE7
0x18000dcc7  call    cs:__imp_GetLastError
0x18000dcce  nop     dword ptr [rax+rax+00h]
0x18000dcd3  mov     r9d, eax
0x18000dcd6  mov     edx, 0Dh
0x18000dcdb  lea     r8, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids
0x18000dce2  call    WPP_SF_l
0x18000dce7  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000dced  cmp     ecx, 0FFFFFFFFh
0x18000dcf0  jz      short loc_18000DD08
0x18000dcf2  call    cs:__imp_TlsFree
0x18000dcf9  nop     dword ptr [rax+rax+00h]
0x18000dcfe  mov     cs:MSAFD_SockTlsSlot, 0FFFFFFFFh
0x18000dd08  call    Rnr_ProcessCleanup
0x18000dd0d  test    edi, edi
0x18000dd0f  jz      short loc_18000DD24
0x18000dd11  lea     rcx, MSWSOCK_SocketLock; lpCriticalSection
0x18000dd18  call    cs:__imp_DeleteCriticalSection
0x18000dd1f  nop     dword ptr [rax+rax+00h]
0x18000dd24  test    esi, esi
0x18000dd26  jz      short loc_18000DD2D
0x18000dd28  call    SockDeleteRwLock
0x18000dd2d  cmp     cs:WinsockTlsDataListLock_initialized, 0
0x18000dd34  jz      short loc_18000DD53
0x18000dd36  lea     rcx, WinsockTlsDataListLock; lpCriticalSection
0x18000dd3d  call    cs:__imp_DeleteCriticalSection
0x18000dd44  nop     dword ptr [rax+rax+00h]
0x18000dd49  mov     cs:WinsockTlsDataListLock_initialized, 0
0x18000dd53  mov     rax, gs:60h
0x18000dd5c  mov     rcx, cs:SockPrivateHeap; Heap
0x18000dd63  cmp     rcx, [rax+30h]
0x18000dd67  jz      short loc_18000DD7A
0x18000dd69  test    rcx, rcx
0x18000dd6c  jz      short loc_18000DD7A
0x18000dd6e  call    cs:__imp_RtlDestroyHeap
0x18000dd75  nop     dword ptr [rax+rax+00h]
0x18000dd7a  mov     cs:SockAllocateHeapRoutine, 0
0x18000dd85  xor     eax, eax
0x18000dd87  jmp     loc_18000DBD8
0x18000dd8c  mov     edx, 0Ah
0x18000dd91  mov     ecx, 401h
0x18000dd96  lea     r8, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids
0x18000dd9d  call    WPP_SF_
0x18000dda2  jmp     loc_18000DBD1
0x18000dda7  mov     r9, gs:60h
0x18000ddb0  mov     edx, 0Bh
0x18000ddb5  mov     ecx, 401h
0x18000ddba  lea     r8, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids
0x18000ddc1  call    WPP_SF_q
0x18000ddc6  jmp     loc_18000DBF7
0x18000ddcb  xor     esi, esi
0x18000ddcd  test    byte ptr cs:xmmword_180063D60, 2
0x18000ddd4  jz      loc_18000DCE7
0x18000ddda  lea     edx, [rsi+0Ch]
0x18000dddd  mov     ecx, 401h
0x18000dde2  lea     r8, WPP_4e9f900f9f8f3d51b1f5b02a6d3546c1_Traceguids
0x18000dde9  call    WPP_SF_
0x18000ddee  jmp     loc_18000DCE7
```
