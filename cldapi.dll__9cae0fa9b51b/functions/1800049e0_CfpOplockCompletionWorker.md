# CfpOplockCompletionWorker

- ea: `0x1800049e0`
- end: `0x180004d10`
- name: `CfpOplockCompletionWorker`
- size: `816`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000231e`
- `0x180004804`
- `0x1800049e0`
- `0x180012c28`
- `0x18001cba8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004abe`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004abe`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004ad5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004ad5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004c32`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004c32`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004b3c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004b3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c6a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004a58`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004a58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bb6`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180004a38`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180004a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b95`

## string_xrefs

- `0x180004a76`: ` >>>>>>>>>>  Dequeued completionContext from IOCP >>>>>`
- `0x180004bcd`: ` Found CompletionContext in OplockCompletionKeyTable, but not the one we are looking for `
- `0x180004b50`: ` >>>>>>>>>>  Freeing CompletionContext from IOCP >>>>>`
- `0x180004cc9`: `OplockCompletionPort HANDLE Closed`
- `0x180004bde`: `completionContext not found in OplockCompletionKeyTable`
- `0x180004c5f`: `GetQueuedCompletionStatus Failed`

## pseudocode

```c
__int64 __fastcall CfpOplockCompletionWorker(PVOID Parameter)
{
  __int64 v1; // rcx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  signed int v4; // eax
  LPOVERLAPPED Overlapped; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 CompletionKey; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v8[8]; // [rsp+50h] [rbp-19h] BYREF
  const wchar_t *v9; // [rsp+58h] [rbp-11h]
  const wchar_t *v10; // [rsp+60h] [rbp-9h]
  LPOVERLAPPED v11; // [rsp+68h] [rbp-1h]
  char *v12; // [rsp+70h] [rbp+7h]
  _QWORD *v13; // [rsp+78h] [rbp+Fh]
  __int64 v14; // [rsp+80h] [rbp+17h]
  int v15; // [rsp+88h] [rbp+1Fh]
  __int64 v16; // [rsp+90h] [rbp+27h]
  HANDLE *v17; // [rsp+98h] [rbp+2Fh]
  DWORD NumberOfBytesTransferred; // [rsp+D8h] [rbp+6Fh] BYREF
  HANDLE *Buffer; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+E8h] [rbp+7Fh] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Buffer = 0;
  Overlapped = 0;
  UnbiasedTime = 0;
  while ( dword_18002ABE8 )
  {
    if ( GetQueuedCompletionStatus(CompletionPort, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
    {
      Buffer = (HANDLE *)CompletionKey;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      memset_0(v8, 0, 0x58u);
      v10 = L" >>>>>>>>>>  Dequeued completionContext from IOCP >>>>>";
      v17 = Buffer;
      v11 = Overlapped;
      TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
      RtlAcquireSRWLockExclusive(&qword_18002AC88);
      if ( RtlLookupElementGenericTableAvl(&stru_18002AC20, &Buffer) )
      {
        v13 = *Buffer;
        v12 = (char *)(Buffer + 1);
        v16 = *(_QWORD *)*Buffer;
        v15 = *((_DWORD *)*Buffer + 6);
        v14 = *((_QWORD *)*Buffer + 2);
        if ( Overlapped == (LPOVERLAPPED)(Buffer + 1) )
        {
          if ( RtlDeleteElementGenericTableAvl(&stru_18002AC20, &Buffer) )
          {
            v10 = L" >>>>>>>>>>  Freeing CompletionContext from IOCP >>>>>";
            TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
            CfpDrainProtectedHandle(*Buffer);
            CloseHandle(Buffer[4]);
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, Buffer);
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredArgs(v1, 0);
          }
        }
        else
        {
          v10 = L" Found CompletionContext in OplockCompletionKeyTable, but not the one we are looking for ";
          TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
        }
      }
      else
      {
        v10 = L"completionContext not found in OplockCompletionKeyTable";
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, LastError);
      }
      RtlReleaseSRWLockExclusive(&qword_18002AC88);
    }
    else
    {
      if ( GetLastError() == 6 )
      {
        memset_0(v8, 0, 0x58u);
        v9 = L"OplockCompletionPort HANDLE Closed";
        TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, -2147024890);
        return 0;
      }
      memset_0(v8, 0, 0x58u);
      v9 = L"GetQueuedCompletionStatus Failed";
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800049e0  mov     [rsp-8+arg_0], rbx
0x1800049e5  push    rbp
0x1800049e6  push    rsi
0x1800049e7  push    rdi
0x1800049e8  lea     rbp, [rsp-47h]
0x1800049ed  sub     rsp, 0B0h
0x1800049f4  mov     eax, cs:dword_18002ABE8
0x1800049fa  xor     ebx, ebx
0x1800049fc  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x1800049ff  mov     [rbp+57h+CompletionKey], rbx
0x180004a03  mov     [rbp+57h+Buffer], rbx
0x180004a07  mov     [rbp+57h+Overlapped], rbx
0x180004a0b  mov     [rbp+57h+UnbiasedTime], rbx
0x180004a0f  test    eax, eax
0x180004a11  jz      loc_180004CFA
0x180004a17  lea     esi, [rbx+58h]
0x180004a1a  lea     edi, [rbx+23h]
0x180004a1d  mov     rcx, cs:CompletionPort; CompletionPort
0x180004a24  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x180004a28  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x180004a2c  mov     [rsp+0C0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180004a34  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180004a38  call    cs:__imp_GetQueuedCompletionStatus
0x180004a3f  nop     dword ptr [rax+rax+00h]
0x180004a44  test    eax, eax
0x180004a46  jz      loc_180004C40
0x180004a4c  mov     rax, [rbp+57h+CompletionKey]
0x180004a50  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x180004a54  mov     [rbp+57h+Buffer], rax
0x180004a58  call    cs:__imp_QueryUnbiasedInterruptTime
0x180004a5f  nop     dword ptr [rax+rax+00h]
0x180004a64  mov     r8, rsi; Size
0x180004a67  lea     rcx, [rbp+57h+var_70]; void *
0x180004a6b  xor     edx, edx; Val
0x180004a6d  call    memset_0
0x180004a72  mov     [rsp+0C0h+var_88], ebx
0x180004a76  lea     rax, aDequeuedComple; " >>>>>>>>>>  Dequeued completionContext"...
0x180004a7d  mov     [rbp+57h+var_60], rax
0x180004a81  mov     ecx, edi
0x180004a83  mov     rax, [rbp+57h+Buffer]
0x180004a87  xor     r9d, r9d
0x180004a8a  mov     [rbp+57h+var_28], rax
0x180004a8e  xor     r8d, r8d
0x180004a91  mov     rax, [rbp+57h+Overlapped]
0x180004a95  xor     edx, edx
0x180004a97  mov     [rbp+57h+var_58], rax
0x180004a9b  lea     rax, [rbp+57h+var_70]
0x180004a9f  mov     [rsp+0C0h+var_90], rax
0x180004aa4  mov     rax, [rbp+57h+UnbiasedTime]
0x180004aa8  mov     [rsp+0C0h+var_98], rax
0x180004aad  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004ab2  call    TlmLogApiReliability
0x180004ab7  lea     rcx, qword_18002AC88
0x180004abe  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004ac5  nop     dword ptr [rax+rax+00h]
0x180004aca  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180004ace  lea     rcx, stru_18002AC20; Table
0x180004ad5  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180004adc  nop     dword ptr [rax+rax+00h]
0x180004ae1  test    rax, rax
0x180004ae4  jz      loc_180004BDE
0x180004aea  mov     rdx, [rbp+57h+Buffer]
0x180004aee  mov     rax, [rdx]
0x180004af1  mov     [rbp+57h+var_48], rax
0x180004af5  lea     rax, [rdx+8]
0x180004af9  mov     [rbp+57h+var_50], rax
0x180004afd  mov     rax, [rdx]
0x180004b00  mov     rcx, [rax]
0x180004b03  mov     [rbp+57h+var_30], rcx
0x180004b07  mov     rax, [rdx]
0x180004b0a  mov     ecx, [rax+18h]
0x180004b0d  mov     rax, [rbp+57h+Buffer]
0x180004b11  mov     [rbp+57h+var_38], ecx
0x180004b14  mov     rcx, [rax]
0x180004b17  mov     rax, [rcx+10h]
0x180004b1b  mov     [rbp+57h+var_40], rax
0x180004b1f  mov     rax, [rbp+57h+Buffer]
0x180004b23  add     rax, 8
0x180004b27  cmp     [rbp+57h+Overlapped], rax
0x180004b2b  jnz     loc_180004BCD
0x180004b31  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180004b35  lea     rcx, stru_18002AC20; Table
0x180004b3c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180004b43  nop     dword ptr [rax+rax+00h]
0x180004b48  test    al, al
0x180004b4a  jz      short loc_180004BC4
0x180004b4c  mov     [rsp+0C0h+var_88], ebx
0x180004b50  lea     rax, aFreeingComplet; " >>>>>>>>>>  Freeing CompletionContext "...
0x180004b57  mov     [rbp+57h+var_60], rax
0x180004b5b  mov     ecx, edi
0x180004b5d  lea     rax, [rbp+57h+var_70]
0x180004b61  xor     r9d, r9d
0x180004b64  mov     [rsp+0C0h+var_90], rax
0x180004b69  xor     r8d, r8d
0x180004b6c  mov     rax, [rbp+57h+UnbiasedTime]
0x180004b70  xor     edx, edx
0x180004b72  mov     [rsp+0C0h+var_98], rax
0x180004b77  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004b7c  call    TlmLogApiReliability
0x180004b81  mov     rcx, [rbp+57h+Buffer]
0x180004b85  mov     rcx, [rcx]
0x180004b88  call    CfpDrainProtectedHandle
0x180004b8d  mov     rcx, [rbp+57h+Buffer]
0x180004b91  mov     rcx, [rcx+20h]; hObject
0x180004b95  call    cs:__imp_CloseHandle
0x180004b9c  nop     dword ptr [rax+rax+00h]
0x180004ba1  call    cs:__imp_GetProcessHeap
0x180004ba8  nop     dword ptr [rax+rax+00h]
0x180004bad  mov     r8, [rbp+57h+Buffer]; lpMem
0x180004bb1  xor     edx, edx; dwFlags
0x180004bb3  mov     rcx, rax; hHeap
0x180004bb6  call    cs:__imp_HeapFree
0x180004bbd  nop     dword ptr [rax+rax+00h]
0x180004bc2  jmp     short loc_180004C2B
0x180004bc4  xor     edx, edx
0x180004bc6  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004bcb  jmp     short loc_180004C2B
0x180004bcd  lea     rax, aFoundCompletio; " Found CompletionContext in OplockCompl"...
0x180004bd4  mov     [rsp+0C0h+var_88], ebx
0x180004bd8  mov     [rbp+57h+var_60], rax
0x180004bdc  jmp     short loc_180004C05
0x180004bde  lea     rax, aCompletioncont; "completionContext not found in OplockCo"...
0x180004be5  mov     [rbp+57h+var_60], rax
0x180004be9  call    cs:__imp_GetLastError
0x180004bf0  nop     dword ptr [rax+rax+00h]
0x180004bf5  test    eax, eax
0x180004bf7  jle     short loc_180004C01
0x180004bf9  movzx   eax, ax
0x180004bfc  or      eax, 80070000h
0x180004c01  mov     [rsp+0C0h+var_88], eax
0x180004c05  lea     rax, [rbp+57h+var_70]
0x180004c09  xor     r9d, r9d
0x180004c0c  mov     [rsp+0C0h+var_90], rax
0x180004c11  xor     r8d, r8d
0x180004c14  mov     rax, [rbp+57h+UnbiasedTime]
0x180004c18  xor     edx, edx
0x180004c1a  mov     [rsp+0C0h+var_98], rax
0x180004c1f  mov     ecx, edi
0x180004c21  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004c26  call    TlmLogApiReliability
0x180004c2b  lea     rcx, qword_18002AC88
0x180004c32  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004c39  nop     dword ptr [rax+rax+00h]
0x180004c3e  jmp     short loc_180004CAC
0x180004c40  call    cs:__imp_GetLastError
0x180004c47  nop     dword ptr [rax+rax+00h]
0x180004c4c  xor     edx, edx; Val
0x180004c4e  lea     rcx, [rbp+57h+var_70]; void *
0x180004c52  mov     r8, rsi; Size
0x180004c55  cmp     eax, 6
0x180004c58  jz      short loc_180004CBC
0x180004c5a  call    memset_0
0x180004c5f  lea     rax, aGetqueuedcompl; "GetQueuedCompletionStatus Failed"
0x180004c66  mov     [rbp+57h+var_68], rax
0x180004c6a  call    cs:__imp_GetLastError
0x180004c71  nop     dword ptr [rax+rax+00h]
0x180004c76  test    eax, eax
0x180004c78  jle     short loc_180004C82
0x180004c7a  movzx   eax, ax
0x180004c7d  or      eax, 80070000h
0x180004c82  mov     [rsp+0C0h+var_88], eax
0x180004c86  mov     ecx, edi
0x180004c88  lea     rax, [rbp+57h+var_70]
0x180004c8c  xor     r9d, r9d
0x180004c8f  mov     [rsp+0C0h+var_90], rax
0x180004c94  xor     r8d, r8d
0x180004c97  mov     rax, [rbp+57h+UnbiasedTime]
0x180004c9b  xor     edx, edx
0x180004c9d  mov     [rsp+0C0h+var_98], rax
0x180004ca2  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004ca7  call    TlmLogApiReliability
0x180004cac  mov     eax, cs:dword_18002ABE8
0x180004cb2  test    eax, eax
0x180004cb4  jnz     loc_180004A1D
0x180004cba  jmp     short loc_180004CFA
0x180004cbc  call    memset_0
0x180004cc1  mov     [rsp+0C0h+var_88], 80070006h
0x180004cc9  lea     rax, aOplockcompleti; "OplockCompletionPort HANDLE Closed"
0x180004cd0  mov     [rbp+57h+var_68], rax
0x180004cd4  mov     ecx, edi
0x180004cd6  lea     rax, [rbp+57h+var_70]
0x180004cda  xor     r9d, r9d
0x180004cdd  mov     [rsp+0C0h+var_90], rax
0x180004ce2  xor     r8d, r8d
0x180004ce5  mov     rax, [rbp+57h+UnbiasedTime]
0x180004ce9  xor     edx, edx
0x180004ceb  mov     [rsp+0C0h+var_98], rax
0x180004cf0  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004cf5  call    TlmLogApiReliability
0x180004cfa  mov     rbx, [rsp+0C0h+arg_0]
0x180004d02  xor     eax, eax
0x180004d04  add     rsp, 0B0h
0x180004d0b  pop     rdi
0x180004d0c  pop     rsi
0x180004d0d  pop     rbp
0x180004d0e  retn
```
