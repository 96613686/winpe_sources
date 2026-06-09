# SockAsyncConnectCompletion

- ea: `0x1800269e0`
- end: `0x180026d67`
- name: `SockAsyncConnectCompletion`
- size: `903`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052a0`
- `0x180008250`
- `0x18000f4c8`
- `0x18002161c`
- `0x1800216a8`
- `0x1800269e0`
- `0x1800381a0`
- `0x180039134`
- `0x1800391c4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180026d46`
- `ntdll!RtlFreeHeap` at `0x180026d46`
- `ntdll!NtDeviceIoControlFile` at `0x180026aa3`
- `ntdll!NtDeviceIoControlFile` at `0x180026aa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026aca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ae6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026b01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026b1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026aca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ae6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026b01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026b1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026ccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a1f`

## pseudocode

```c
void __fastcall SockAsyncConnectCompletion(struct _IO_STATUS_BLOCK *P)
{
  int v2; // ebp
  __int64 Information; // rbx
  __int64 Pointer; // rdi
  int Status; // esi
  unsigned int v6; // edx
  int v7; // ecx
  __int64 v8; // r8
  HANDLE v9; // rcx
  NTSTATUS v10; // eax
  int v11; // esi
  int v12; // eax
  const char *v13; // r9
  const char *v14; // r9
  int v15; // ecx
  bool v16; // zf
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  ULONG IoControlCode; // [rsp+28h] [rbp-60h]
  ULONG InputBufferLength; // [rsp+38h] [rbp-50h]

  v2 = 0;
  while ( 1 )
  {
    Information = P->Information;
    Pointer = (__int64)P->Pointer;
    Status = P[1].Status;
    if ( Information )
      EnterCriticalSection((LPCRITICAL_SECTION)(Information + 224));
    EnterCriticalSection((LPCRITICAL_SECTION)(Pointer + 224));
    if ( Status >= 0 )
      goto LABEL_15;
    if ( *(_DWORD *)(Pointer + 24) == 4 )
      goto LABEL_16;
    if ( Status != -1073741536 && (unsigned int)SockNotifyHelperDll(Pointer, 256, v8) != 11002 )
    {
LABEL_15:
      if ( *(_DWORD *)(Pointer + 24) == 4 )
      {
LABEL_16:
        v11 = 10038;
        goto LABEL_21;
      }
      if ( Status >= 0 )
        v12 = SockPostProcessConnect(Pointer);
      else
        v12 = NtStatusToSocketError((unsigned int)Status);
      v11 = v12;
      if ( v12 )
        goto LABEL_21;
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v14 = "WSPConnect";
        if ( HIDWORD(P[2].Pointer) != 73735 )
          v14 = "WSPJoinLeaf";
        WPP_SF_sqq(v7, v6, v8, (_DWORD)v14, *(_QWORD *)(Pointer + 8), Pointer);
      }
LABEL_29:
      *(_DWORD *)(Pointer + 100) = v11;
      *(_QWORD *)(Pointer + 200) = 0;
      if ( Information )
      {
        v16 = (*(_BYTE *)(Information + 120) & 0x10) == 0;
        *(_QWORD *)(Information + 200) = 0;
        if ( !v16 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(SockUpcallTable + 56))(
            *(_QWORD *)(Information + 104),
            *(unsigned int *)(Information + 116),
            *(_QWORD *)(Information + 8),
            ((unsigned __int16)v11 << 16) | 0x10);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v17,
              24,
              (unsigned int)WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids,
              *(_DWORD *)(Information + 116),
              *(_QWORD *)(Information + 104),
              *(_QWORD *)(Information + 8),
              (__int64)"FD_CONNECT",
              v11);
        }
      }
      else if ( (*(_BYTE *)(Pointer + 120) & 0x10) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(SockUpcallTable + 56))(
          *(_QWORD *)(Pointer + 104),
          *(unsigned int *)(Pointer + 116),
          *(_QWORD *)(Pointer + 8),
          ((unsigned __int16)v11 << 16) | 0x10);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_Lqisl(
            v15,
            23,
            (unsigned int)WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids,
            *(_DWORD *)(Pointer + 116),
            *(_QWORD *)(Pointer + 104),
            *(_QWORD *)(Pointer + 8),
            (__int64)"FD_CONNECT",
            v11);
      }
      if ( (*(_BYTE *)(Pointer + 120) & 3) != 0 )
        SockReenableAsyncSelectEvent(Pointer, 3, v8);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Pointer + 224));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Pointer, 0xFFFFFFFF) == 1 )
        SockDestroySocket(Pointer, v18, v19);
      if ( Information )
      {
        if ( !v11 && *(_DWORD *)(Information + 24) != 3 )
        {
          v16 = (*(_BYTE *)(Information + 120) & 2) == 0;
          *(_DWORD *)(Information + 24) = 3;
          if ( !v16 )
            SockReenableAsyncSelectEvent(Information, 2, v19);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(Information + 224));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Information, 0xFFFFFFFF) == 1 )
          SockDestroySocket(Information, v20, v21);
      }
      RtlFreeHeap(SockPrivateHeap, 0, P);
      _InterlockedAdd(&SockAsyncThreadReferenceCount, 0xFFFFFFFF);
      return;
    }
    InputBufferLength = P[2].Status;
    v9 = SockAsyncConnectHelperHandle;
    IoControlCode = HIDWORD(P[2].Pointer);
    P[1].Status = 259;
    v10 = NtDeviceIoControlFile(v9, 0, 0, P, P + 1, IoControlCode, &P[2].Information, InputBufferLength, &P[1], 0x10u);
    v7 = -1073741824;
    v6 = v10 & 0xC0000000;
    if ( (v10 & 0xC0000000) != 0xC0000000 )
      break;
    ++v2;
    P[1].Status = v10;
    if ( v2 == 2 )
    {
      v11 = 10060;
LABEL_21:
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v13 = "WSPConnect";
        if ( HIDWORD(P[2].Pointer) != 73735 )
          v13 = "WSPJoinLeaf";
        WPP_SF_sqql(v7, v6, v8, (_DWORD)v13, *(_QWORD *)(Pointer + 8), Pointer, v11);
      }
      goto LABEL_29;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Pointer + 224));
    if ( Information )
      LeaveCriticalSection((LPCRITICAL_SECTION)(Information + 224));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Pointer + 224));
  if ( Information )
    LeaveCriticalSection((LPCRITICAL_SECTION)(Information + 224));
}

```

## disassembly

```asm
0x1800269e0  push    rbx
0x1800269e2  push    rbp
0x1800269e3  push    rsi
0x1800269e4  push    rdi
0x1800269e5  push    r14
0x1800269e7  push    r15
0x1800269e9  sub     rsp, 58h
0x1800269ed  mov     r14, rcx
0x1800269f0  xor     ebp, ebp
0x1800269f2  mov     rbx, [r14+8]
0x1800269f6  mov     rdi, [r14]
0x1800269f9  mov     esi, [r14+10h]
0x1800269fd  test    rbx, rbx
0x180026a00  jz      short loc_180026A15
0x180026a02  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180026a09  call    cs:__imp_EnterCriticalSection
0x180026a10  nop     dword ptr [rax+rax+00h]
0x180026a15  lea     r15, [rdi+0E0h]
0x180026a1c  mov     rcx, r15; lpCriticalSection
0x180026a1f  call    cs:__imp_EnterCriticalSection
0x180026a26  nop     dword ptr [rax+rax+00h]
0x180026a2b  test    esi, esi
0x180026a2d  jns     loc_180026B2E
0x180026a33  cmp     dword ptr [rdi+18h], 4
0x180026a37  jz      loc_180026B34
0x180026a3d  cmp     esi, 0C0000120h
0x180026a43  jz      short loc_180026A5D
0x180026a45  mov     edx, 100h
0x180026a4a  mov     rcx, rdi
0x180026a4d  call    SockNotifyHelperDll
0x180026a52  cmp     eax, 2AFAh
0x180026a57  jnz     loc_180026B2E
0x180026a5d  mov     eax, [r14+20h]
0x180026a61  lea     rdx, [r14+10h]
0x180026a65  mov     [rsp+88h+OutputBufferLength], 10h; OutputBufferLength
0x180026a6d  lea     rcx, [r14+28h]
0x180026a71  mov     [rsp+88h+OutputBuffer], rdx; OutputBuffer
0x180026a76  mov     r9, r14; ApcContext
0x180026a79  mov     [rsp+88h+InputBufferLength], eax; InputBufferLength
0x180026a7d  xor     r8d, r8d; ApcRoutine
0x180026a80  mov     eax, [r14+24h]
0x180026a84  mov     [rsp+88h+InputBuffer], rcx; InputBuffer
0x180026a89  mov     rcx, cs:SockAsyncConnectHelperHandle; FileHandle
0x180026a90  mov     [rsp+88h+IoControlCode], eax; IoControlCode
0x180026a94  mov     [rsp+88h+IoStatusBlock], rdx; IoStatusBlock
0x180026a99  xor     edx, edx; Event
0x180026a9b  mov     dword ptr [r14+10h], 103h
0x180026aa3  call    cs:__imp_NtDeviceIoControlFile
0x180026aaa  nop     dword ptr [rax+rax+00h]
0x180026aaf  mov     ecx, 0C0000000h
0x180026ab4  mov     edx, eax
0x180026ab6  and     edx, ecx
0x180026ab8  cmp     edx, ecx
0x180026aba  jnz     short loc_180026AFE
0x180026abc  inc     ebp
0x180026abe  mov     [r14+10h], eax
0x180026ac2  cmp     ebp, 2
0x180026ac5  jz      short loc_180026AF7
0x180026ac7  mov     rcx, r15; lpCriticalSection
0x180026aca  call    cs:__imp_LeaveCriticalSection
0x180026ad1  nop     dword ptr [rax+rax+00h]
0x180026ad6  test    rbx, rbx
0x180026ad9  jz      loc_1800269F2
0x180026adf  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180026ae6  call    cs:__imp_LeaveCriticalSection
0x180026aed  nop     dword ptr [rax+rax+00h]
0x180026af2  jmp     loc_1800269F2
0x180026af7  mov     esi, 274Ch
0x180026afc  jmp     short loc_180026B56
0x180026afe  mov     rcx, r15; lpCriticalSection
0x180026b01  call    cs:__imp_LeaveCriticalSection
0x180026b08  nop     dword ptr [rax+rax+00h]
0x180026b0d  test    rbx, rbx
0x180026b10  jz      loc_180026D59
0x180026b16  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180026b1d  call    cs:__imp_LeaveCriticalSection
0x180026b24  nop     dword ptr [rax+rax+00h]
0x180026b29  jmp     loc_180026D59
0x180026b2e  cmp     dword ptr [rdi+18h], 4
0x180026b32  jnz     short loc_180026B3B
0x180026b34  mov     esi, 2736h
0x180026b39  jmp     short loc_180026B56
0x180026b3b  test    esi, esi
0x180026b3d  jns     short loc_180026B48
0x180026b3f  mov     ecx, esi
0x180026b41  call    NtStatusToSocketError
0x180026b46  jmp     short loc_180026B50
0x180026b48  mov     rcx, rdi
0x180026b4b  call    SockPostProcessConnect
0x180026b50  mov     esi, eax
0x180026b52  test    eax, eax
0x180026b54  jz      short loc_180026B92
0x180026b56  test    byte ptr cs:xmmword_180063D60, 2
0x180026b5d  jz      short loc_180026BC8
0x180026b5f  cmp     dword ptr [r14+24h], 12007h
0x180026b67  lea     rax, aWspjoinleaf; "WSPJoinLeaf"
0x180026b6e  mov     dword ptr [rsp+88h+InputBuffer], esi
0x180026b72  lea     r9, aWspconnect; "WSPConnect"
0x180026b79  cmovnz  r9, rax
0x180026b7d  mov     qword ptr [rsp+88h+IoControlCode], rdi
0x180026b82  mov     rax, [rdi+8]
0x180026b86  mov     [rsp+88h+IoStatusBlock], rax
0x180026b8b  call    WPP_SF_sqql
0x180026b90  jmp     short loc_180026BC8
0x180026b92  test    byte ptr cs:xmmword_180063D60, 2
0x180026b99  jz      short loc_180026BC8
0x180026b9b  cmp     dword ptr [r14+24h], 12007h
0x180026ba3  lea     rax, aWspjoinleaf; "WSPJoinLeaf"
0x180026baa  lea     r9, aWspconnect; "WSPConnect"
0x180026bb1  mov     qword ptr [rsp+88h+IoControlCode], rdi
0x180026bb6  cmovnz  r9, rax
0x180026bba  mov     rax, [rdi+8]
0x180026bbe  mov     [rsp+88h+IoStatusBlock], rax
0x180026bc3  call    WPP_SF_sqq
0x180026bc8  mov     [rdi+64h], esi
0x180026bcb  mov     qword ptr [rdi+0C8h], 0
0x180026bd6  test    rbx, rbx
0x180026bd9  jnz     short loc_180026C3F
0x180026bdb  test    byte ptr [rdi+78h], 10h
0x180026bdf  jz      loc_180026CB7
0x180026be5  mov     r8, [rdi+8]
0x180026be9  mov     edx, [rdi+74h]
0x180026bec  mov     rcx, [rdi+68h]
0x180026bf0  movzx   eax, si
0x180026bf3  shl     eax, 10h
0x180026bf6  or      eax, 10h
0x180026bf9  movsxd  r9, eax
0x180026bfc  mov     rax, cs:SockUpcallTable
0x180026c03  mov     rax, [rax+38h]
0x180026c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c0c  test    byte ptr cs:xmmword_180063D60, 2
0x180026c13  jz      loc_180026CB7
0x180026c19  mov     r9d, [rdi+74h]
0x180026c1d  lea     rax, aFdConnect; "FD_CONNECT"
0x180026c24  mov     [rsp+88h+InputBufferLength], esi
0x180026c28  lea     edx, [rbx+17h]
0x180026c2b  mov     [rsp+88h+InputBuffer], rax
0x180026c30  mov     rax, [rdi+8]
0x180026c34  mov     qword ptr [rsp+88h+IoControlCode], rax
0x180026c39  mov     rax, [rdi+68h]
0x180026c3d  jmp     short loc_180026CA6
0x180026c3f  test    byte ptr [rbx+78h], 10h
0x180026c43  mov     qword ptr [rbx+0C8h], 0
0x180026c4e  jz      short loc_180026CB7
0x180026c50  mov     r8, [rbx+8]
0x180026c54  mov     edx, [rbx+74h]
0x180026c57  mov     rcx, [rbx+68h]
0x180026c5b  movzx   eax, si
0x180026c5e  shl     eax, 10h
0x180026c61  or      eax, 10h
0x180026c64  movsxd  r9, eax
0x180026c67  mov     rax, cs:SockUpcallTable
0x180026c6e  mov     rax, [rax+38h]
0x180026c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c77  test    byte ptr cs:xmmword_180063D60, 2
0x180026c7e  jz      short loc_180026CB7
0x180026c80  mov     r9d, [rbx+74h]
0x180026c84  lea     rax, aFdConnect; "FD_CONNECT"
0x180026c8b  mov     [rsp+88h+InputBufferLength], esi
0x180026c8f  mov     edx, 18h
0x180026c94  mov     [rsp+88h+InputBuffer], rax
0x180026c99  mov     rax, [rbx+8]
0x180026c9d  mov     qword ptr [rsp+88h+IoControlCode], rax
0x180026ca2  mov     rax, [rbx+68h]
0x180026ca6  lea     r8, WPP_9d0f94e574073b37d6c051efed79eb04_Traceguids
0x180026cad  mov     [rsp+88h+IoStatusBlock], rax
0x180026cb2  call    WPP_SF_Lqisl
0x180026cb7  test    byte ptr [rdi+78h], 3
0x180026cbb  jz      short loc_180026CCA
0x180026cbd  mov     edx, 3
0x180026cc2  mov     rcx, rdi
0x180026cc5  call    SockReenableAsyncSelectEvent
0x180026cca  mov     rcx, r15; lpCriticalSection
0x180026ccd  call    cs:__imp_LeaveCriticalSection
0x180026cd4  nop     dword ptr [rax+rax+00h]
0x180026cd9  or      ebp, 0FFFFFFFFh
0x180026cdc  mov     eax, ebp
0x180026cde  lock xadd [rdi], eax
0x180026ce2  add     eax, ebp
0x180026ce4  jnz     short loc_180026CEE
0x180026ce6  mov     rcx, rdi
0x180026ce9  call    SockDestroySocket
0x180026cee  test    rbx, rbx
0x180026cf1  jz      short loc_180026D3A
0x180026cf3  test    esi, esi
0x180026cf5  jnz     short loc_180026D15
0x180026cf7  cmp     dword ptr [rbx+18h], 3
0x180026cfb  jz      short loc_180026D15
0x180026cfd  test    byte ptr [rbx+78h], 2
0x180026d01  mov     dword ptr [rbx+18h], 3
0x180026d08  jz      short loc_180026D15
0x180026d0a  lea     edx, [rsi+2]
0x180026d0d  mov     rcx, rbx
0x180026d10  call    SockReenableAsyncSelectEvent
0x180026d15  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180026d1c  call    cs:__imp_LeaveCriticalSection
0x180026d23  nop     dword ptr [rax+rax+00h]
0x180026d28  mov     eax, ebp
0x180026d2a  lock xadd [rbx], eax
0x180026d2e  add     eax, ebp
0x180026d30  jnz     short loc_180026D3A
0x180026d32  mov     rcx, rbx
0x180026d35  call    SockDestroySocket
0x180026d3a  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180026d41  mov     r8, r14; P
0x180026d44  xor     edx, edx; Flags
0x180026d46  call    cs:__imp_RtlFreeHeap
0x180026d4d  nop     dword ptr [rax+rax+00h]
0x180026d52  lock add cs:SockAsyncThreadReferenceCount, ebp
0x180026d59  add     rsp, 58h
0x180026d5d  pop     r15
0x180026d5f  pop     r14
0x180026d61  pop     rdi
0x180026d62  pop     rsi
0x180026d63  pop     rbp
0x180026d64  pop     rbx
0x180026d65  retn
```
