# SharedSocket::DuplicateSocketHelper(unsigned __int64,ulong,_SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION *)

- ea: `0x180014170`
- end: `0x1800142cd`
- name: `?DuplicateSocketHelper@SharedSocket@@SAK_KKPEAU_SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION@@@Z`
- size: `349`
- prototype: `unsigned int __fastcall(SOCKET s, DWORD dwProcessId, struct _SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013f04`
- `0x180026eb0`
- `0x18002758c`

## callees

- `0x18000a0a0`
- `0x180014170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001428b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001428b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800141ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800141ab`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800141d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800141d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014247`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014199`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180014199`
- `WS2_32!WSAIoctl` at `0x180014226`
- `WS2_32!WSAIoctl` at `0x180014226`
- `WS2_32!__imp_WSAGetLastError` at `0x1800142b6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800142b6`

## string_xrefs

- `0x18001427a`: `DuplicateSocketHelper: OpenProcess failed with`

## pseudocode

```c
__int64 __fastcall SharedSocket::DuplicateSocketHelper(
        SOCKET s,
        DWORD dwProcessId,
        struct _SOCKET_BROKER_RETRIEVE_SOCKET_INFORMATION *a3)
{
  DWORD v3; // edi
  HANDLE v6; // rsi
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int Error; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int vOutBuffer; // [rsp+80h] [rbp+18h] BYREF
  DWORD cbBytesReturned; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  vOutBuffer = 0;
  cbBytesReturned = 0;
  v6 = OpenProcess(0x40u, 0, dwProcessId);
  if ( !v6 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, v10, L"DuplicateSocketHelper: OpenProcess failed with", LastError);
  }
  CurrentProcess = GetCurrentProcess();
  if ( DuplicateHandle(CurrentProcess, (HANDLE)s, v6, (LPHANDLE)a3 + 3, 0, 1, 2u) )
  {
    if ( WSAIoctl(s, 0x9800012D, 0, 0, &vOutBuffer, 4u, &cbBytesReturned, 0, 0) == -1 )
    {
      Error = WSAGetLastError();
      v3 = Error;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v17,
          v16,
          L"DuplicateSocketHelper: SIO_SOCKET_TRANSFER_BEGIN failed with",
          Error);
    }
    else
    {
      *((_DWORD *)a3 + 4) = vOutBuffer;
    }
  }
  else
  {
    v12 = GetLastError();
    v3 = v12;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, L"DuplicateSocketHelper: DuplicateHandle failed with", v12);
  }
  if ( v6 )
    CloseHandle(v6);
  return v3;
}

```

## disassembly

```asm
0x180014170  mov     rax, rsp
0x180014173  mov     [rax+8], rbx
0x180014177  mov     [rax+10h], rbp
0x18001417b  push    rsi
0x18001417c  push    rdi
0x18001417d  push    r14
0x18001417f  sub     rsp, 50h
0x180014183  xor     edi, edi
0x180014185  mov     rbp, r8
0x180014188  mov     r14, rcx
0x18001418b  mov     [rax+18h], edi
0x18001418e  mov     r8d, edx; dwProcessId
0x180014191  mov     [rax+20h], edi
0x180014194  xor     edx, edx; bInheritHandle
0x180014196  lea     ecx, [rdi+40h]; dwDesiredAccess
0x180014199  call    cs:__imp_OpenProcess
0x18001419f  mov     rsi, rax
0x1800141a2  test    rax, rax
0x1800141a5  jz      loc_180014262
0x1800141ab  call    cs:__imp_GetCurrentProcess
0x1800141b1  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800141b9  lea     r9, [rbp+18h]; lpTargetHandle
0x1800141bd  mov     rcx, rax; hSourceProcessHandle
0x1800141c0  mov     [rsp+68h+bInheritHandle], 1; bInheritHandle
0x1800141c8  mov     r8, rsi; hTargetProcessHandle
0x1800141cb  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x1800141d3  mov     rdx, r14; hSourceHandle
0x1800141d6  call    cs:__imp_DuplicateHandle
0x1800141dc  test    eax, eax
0x1800141de  jz      loc_18001428B
0x1800141e4  mov     [rsp+68h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800141ed  lea     rax, [rsp+68h+cbBytesReturned]
0x1800141f5  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800141fe  xor     r9d, r9d; cbInBuffer
0x180014201  mov     qword ptr [rsp+68h+dwOptions], rax; lpcbBytesReturned
0x180014206  xor     r8d, r8d; lpvInBuffer
0x180014209  lea     rax, [rsp+68h+vOutBuffer]
0x180014211  mov     [rsp+68h+bInheritHandle], 4; cbOutBuffer
0x180014219  mov     edx, 9800012Dh; dwIoControlCode
0x18001421e  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpvOutBuffer
0x180014223  mov     rcx, r14; s
0x180014226  call    cs:__imp_WSAIoctl
0x18001422c  cmp     eax, 0FFFFFFFFh
0x18001422f  jz      loc_1800142B6
0x180014235  mov     eax, [rsp+68h+vOutBuffer]
0x18001423c  mov     [rbp+10h], eax
0x18001423f  test    rsi, rsi
0x180014242  jz      short loc_18001424D
0x180014244  mov     rcx, rsi; hObject
0x180014247  call    cs:__imp_CloseHandle
0x18001424d  mov     rbx, [rsp+68h+arg_0]
0x180014252  mov     eax, edi
0x180014254  mov     rbp, [rsp+68h+arg_8]
0x180014259  add     rsp, 50h
0x18001425d  pop     r14
0x18001425f  pop     rdi
0x180014260  pop     rsi
0x180014261  retn
0x180014262  call    cs:__imp_GetLastError
0x180014268  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001426f  mov     edi, eax
0x180014271  jz      loc_1800141AB
0x180014277  mov     r9d, eax
0x18001427a  lea     r8, aDuplicatesocke_0; "DuplicateSocketHelper: OpenProcess fail"...
0x180014281  call    McTemplateU0zq_EventWriteTransfer
0x180014286  jmp     loc_1800141AB
0x18001428b  call    cs:__imp_GetLastError
0x180014291  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180014298  mov     edi, eax
0x18001429a  jz      short loc_18001423F
0x18001429c  lea     r8, aDuplicatesocke_1; "DuplicateSocketHelper: DuplicateHandle "...
0x1800142a3  jmp     short loc_1800142AC
0x1800142a5  lea     r8, aDuplicatesocke; "DuplicateSocketHelper: SIO_SOCKET_TRANS"...
0x1800142ac  mov     r9d, eax
0x1800142af  call    McTemplateU0zq_EventWriteTransfer
0x1800142b4  jmp     short loc_18001423F
0x1800142b6  call    cs:__imp_WSAGetLastError
0x1800142bc  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800142c3  mov     edi, eax
0x1800142c5  jz      loc_18001423F
0x1800142cb  jmp     short loc_1800142A5
```
