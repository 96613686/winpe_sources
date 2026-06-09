# GetLocalV4Addrs(_SOCKET_ADDRESS_LIST * *)

- ea: `0x140037a88`
- end: `0x140037c86`
- name: `?GetLocalV4Addrs@@YAJPEAPEAU_SOCKET_ADDRESS_LIST@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(struct _SOCKET_ADDRESS_LIST **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140037868`

## callees

- `0x140034ce4`
- `0x140037a88`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140037c55`
- `KERNEL32!HeapFree` at `0x140037c55`
- `KERNEL32!GetProcessHeap` at `0x140037b71`
- `KERNEL32!GetProcessHeap` at `0x140037c41`
- `KERNEL32!GetProcessHeap` at `0x140037b71`
- `KERNEL32!GetProcessHeap` at `0x140037c41`
- `KERNEL32!HeapAlloc` at `0x140037b88`
- `KERNEL32!HeapAlloc` at `0x140037b88`
- `WS2_32!WSASocketW` at `0x140037aae`
- `WS2_32!WSASocketW` at `0x140037aae`
- `WS2_32!WSAIoctl` at `0x140037b24`
- `WS2_32!WSAIoctl` at `0x140037c08`
- `WS2_32!WSAIoctl` at `0x140037b24`
- `WS2_32!WSAIoctl` at `0x140037c08`
- `WS2_32!__imp_closesocket` at `0x140037c6e`
- `WS2_32!__imp_closesocket` at `0x140037c6e`

## string_xrefs

- `0x140037ad9`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140037b51`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140037bb6`: `base\diagnosis\ra\racommon\src\rasqm.cpp`
- `0x140037c2e`: `base\diagnosis\ra\racommon\src\rasqm.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalV4Addrs(struct _SOCKET_ADDRESS_LIST **a1)
{
  CEventLogger *v2; // rcx
  SOCKET v3; // rdi
  unsigned int v4; // ebx
  CEventLogger *v5; // rcx
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  CEventLogger *v8; // rcx
  struct _SOCKET_ADDRESS_LIST *lpvOutBuffer; // rbx
  CEventLogger *v10; // rcx
  HANDLE v11; // rax
  DWORD cbBytesReturned; // [rsp+88h] [rbp+10h] BYREF

  cbBytesReturned = 0;
  v3 = WSASocketW(2, 1, 6, 0, 0, 0);
  if ( v3 != -1 )
  {
    WSAIoctl(v3, 0x48000016u, 0, 0, 0, 0, &cbBytesReturned, 0, 0);
    if ( cbBytesReturned )
    {
      v6 = cbBytesReturned;
      ProcessHeap = GetProcessHeap();
      lpvOutBuffer = (struct _SOCKET_ADDRESS_LIST *)HeapAlloc(ProcessHeap, 8u, v6);
      if ( !lpvOutBuffer )
      {
        v4 = -2147024882;
        CEventLogger::LogError(
          v8,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
          0x481u,
          L"GetLocalV4Addrs",
          0x8007000E);
        goto LABEL_11;
      }
      if ( !WSAIoctl(v3, 0x48000016u, 0, 0, lpvOutBuffer, cbBytesReturned, &cbBytesReturned, 0, 0) )
      {
        *a1 = lpvOutBuffer;
        v4 = 0;
        goto LABEL_11;
      }
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
        0x491u,
        L"GetLocalV4Addrs",
        0);
      v11 = GetProcessHeap();
      HeapFree(v11, 0, lpvOutBuffer);
    }
    else
    {
      CEventLogger::LogError(
        v5,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
        0x47Eu,
        L"GetLocalV4Addrs",
        0);
    }
    v4 = -2147467259;
LABEL_11:
    closesocket(v3);
    return v4;
  }
  CEventLogger::LogError(
    v2,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\racommon\\src\\rasqm.cpp",
    0x470u,
    L"GetLocalV4Addrs",
    0);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x140037a88  mov     rax, rsp
0x140037a8b  push    rbx
0x140037a8c  push    rbp
0x140037a8d  push    rsi
0x140037a8e  push    rdi
0x140037a8f  sub     rsp, 58h
0x140037a93  xor     ebp, ebp
0x140037a95  mov     rsi, rcx
0x140037a98  mov     [rax-50h], ebp
0x140037a9b  xor     r9d, r9d; lpProtocolInfo
0x140037a9e  mov     [rax+10h], ebp
0x140037aa1  mov     [rax-58h], ebp
0x140037aa4  lea     edx, [rbp+1]; type
0x140037aa7  lea     ecx, [rbp+2]; af
0x140037aaa  lea     r8d, [rbp+6]; protocol
0x140037aae  call    cs:__imp_WSASocketW
0x140037ab5  nop     dword ptr [rax+rax+00h]
0x140037aba  mov     rdi, rax
0x140037abd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140037ac1  jnz     short loc_140037AF6
0x140037ac3  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037aca  mov     [rsp+78h+cbOutBuffer], ebp; unsigned int
0x140037ace  mov     r9d, 470h; unsigned int
0x140037ad4  mov     [rsp+78h+lpvOutBuffer], rax; unsigned __int16 *
0x140037ad9  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037ae0  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037ae7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037aec  mov     ebx, 80004005h
0x140037af1  jmp     loc_140037C7A
0x140037af6  mov     [rsp+78h+lpCompletionRoutine], rbp; lpCompletionRoutine
0x140037afb  lea     rax, [rsp+78h+cbBytesReturned]
0x140037b03  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x140037b08  xor     r9d, r9d; cbInBuffer
0x140037b0b  mov     [rsp+78h+lpcbBytesReturned], rax; lpcbBytesReturned
0x140037b10  xor     r8d, r8d; lpvInBuffer
0x140037b13  mov     [rsp+78h+cbOutBuffer], ebp; cbOutBuffer
0x140037b17  mov     edx, 48000016h; dwIoControlCode
0x140037b1c  mov     rcx, rdi; s
0x140037b1f  mov     [rsp+78h+lpvOutBuffer], rbp; lpvOutBuffer
0x140037b24  call    cs:__imp_WSAIoctl
0x140037b2b  nop     dword ptr [rax+rax+00h]
0x140037b30  mov     eax, [rsp+78h+cbBytesReturned]
0x140037b37  test    eax, eax
0x140037b39  jnz     short loc_140037B6E
0x140037b3b  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037b42  mov     [rsp+78h+cbOutBuffer], ebp; unsigned int
0x140037b46  mov     r9d, 47Eh; unsigned int
0x140037b4c  mov     [rsp+78h+lpvOutBuffer], rax; unsigned __int16 *
0x140037b51  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037b58  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037b5f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037b64  mov     ebx, 80004005h
0x140037b69  jmp     loc_140037C6B
0x140037b6e  mov     rbx, rax
0x140037b71  call    cs:__imp_GetProcessHeap
0x140037b78  nop     dword ptr [rax+rax+00h]
0x140037b7d  mov     r8, rbx; dwBytes
0x140037b80  mov     edx, 8; dwFlags
0x140037b85  mov     rcx, rax; hHeap
0x140037b88  call    cs:__imp_HeapAlloc
0x140037b8f  nop     dword ptr [rax+rax+00h]
0x140037b94  mov     rbx, rax
0x140037b97  test    rax, rax
0x140037b9a  jnz     short loc_140037BD3
0x140037b9c  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037ba3  mov     [rsp+78h+cbOutBuffer], 8007000Eh; unsigned int
0x140037bab  mov     r9d, 481h; unsigned int
0x140037bb1  mov     [rsp+78h+lpvOutBuffer], rax; unsigned __int16 *
0x140037bb6  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037bbd  mov     ebx, 8007000Eh
0x140037bc2  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037bc9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037bce  jmp     loc_140037C6B
0x140037bd3  mov     [rsp+78h+lpCompletionRoutine], rbp; lpCompletionRoutine
0x140037bd8  lea     rax, [rsp+78h+cbBytesReturned]
0x140037be0  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x140037be5  xor     r9d, r9d; cbInBuffer
0x140037be8  mov     [rsp+78h+lpcbBytesReturned], rax; lpcbBytesReturned
0x140037bed  xor     r8d, r8d; lpvInBuffer
0x140037bf0  mov     eax, [rsp+78h+cbBytesReturned]
0x140037bf7  mov     edx, 48000016h; dwIoControlCode
0x140037bfc  mov     [rsp+78h+cbOutBuffer], eax; cbOutBuffer
0x140037c00  mov     rcx, rdi; s
0x140037c03  mov     [rsp+78h+lpvOutBuffer], rbx; lpvOutBuffer
0x140037c08  call    cs:__imp_WSAIoctl
0x140037c0f  nop     dword ptr [rax+rax+00h]
0x140037c14  test    eax, eax
0x140037c16  jz      short loc_140037C66
0x140037c18  lea     rax, aGetlocalv4addr; "GetLocalV4Addrs"
0x140037c1f  mov     [rsp+78h+cbOutBuffer], ebp; unsigned int
0x140037c23  mov     r9d, 491h; unsigned int
0x140037c29  mov     [rsp+78h+lpvOutBuffer], rax; unsigned __int16 *
0x140037c2e  lea     r8, aBaseDiagnosisR_23; "base\\diagnosis\\ra\\racommon\\src\\ras"...
0x140037c35  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140037c3c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140037c41  call    cs:__imp_GetProcessHeap
0x140037c48  nop     dword ptr [rax+rax+00h]
0x140037c4d  mov     r8, rbx; lpMem
0x140037c50  xor     edx, edx; dwFlags
0x140037c52  mov     rcx, rax; hHeap
0x140037c55  call    cs:__imp_HeapFree
0x140037c5c  nop     dword ptr [rax+rax+00h]
0x140037c61  jmp     loc_140037B64
0x140037c66  mov     [rsi], rbx
0x140037c69  mov     ebx, ebp
0x140037c6b  mov     rcx, rdi; s
0x140037c6e  call    cs:__imp_closesocket
0x140037c75  nop     dword ptr [rax+rax+00h]
0x140037c7a  mov     eax, ebx
0x140037c7c  add     rsp, 58h
0x140037c80  pop     rdi
0x140037c81  pop     rsi
0x140037c82  pop     rbp
0x140037c83  pop     rbx
0x140037c84  retn
```
