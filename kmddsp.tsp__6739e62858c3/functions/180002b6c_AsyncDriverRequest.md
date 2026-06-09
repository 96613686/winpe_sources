# AsyncDriverRequest

- ea: `0x180002b6c`
- end: `0x180002d2f`
- name: `AsyncDriverRequest`
- size: `451`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, char *)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004310`
- `0x180004400`
- `0x1800049a0`
- `0x180004bc0`
- `0x180004d30`
- `0x1800063b0`
- `0x180006d40`
- `0x180006fb0`
- `0x1800071b0`

## callees

- `0x18000298c`
- `0x180002b6c`
- `0x180007df8`
- `0x180009010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002c8d`
- `KERNEL32!GetLastError` at `0x180002c8d`
- `KERNEL32!DeviceIoControl` at `0x180002c29`
- `KERNEL32!DeviceIoControl` at `0x180002c29`
- `KERNEL32!DeleteCriticalSection` at `0x180002c60`
- `KERNEL32!DeleteCriticalSection` at `0x180002cf6`
- `KERNEL32!DeleteCriticalSection` at `0x180002c60`
- `KERNEL32!DeleteCriticalSection` at `0x180002cf6`
- `KERNEL32!LeaveCriticalSection` at `0x180002bee`
- `KERNEL32!LeaveCriticalSection` at `0x180002c51`
- `KERNEL32!LeaveCriticalSection` at `0x180002c78`
- `KERNEL32!LeaveCriticalSection` at `0x180002ce7`
- `KERNEL32!LeaveCriticalSection` at `0x180002d0c`
- `KERNEL32!LeaveCriticalSection` at `0x180002bee`
- `KERNEL32!LeaveCriticalSection` at `0x180002c51`
- `KERNEL32!LeaveCriticalSection` at `0x180002c78`
- `KERNEL32!LeaveCriticalSection` at `0x180002ce7`
- `KERNEL32!LeaveCriticalSection` at `0x180002d0c`
- `KERNEL32!EnterCriticalSection` at `0x180002bdc`
- `KERNEL32!EnterCriticalSection` at `0x180002c3a`
- `KERNEL32!EnterCriticalSection` at `0x180002cd3`
- `KERNEL32!EnterCriticalSection` at `0x180002bdc`
- `KERNEL32!EnterCriticalSection` at `0x180002c3a`
- `KERNEL32!EnterCriticalSection` at `0x180002cd3`

## pseudocode

```c
__int64 __fastcall AsyncDriverRequest(DWORD dwIoControlCode, char *a2)
{
  int v3; // r9d
  char *lpOverlapped; // rsi
  int v5; // eax
  const char *v6; // r8
  unsigned int v7; // r14d
  DWORD v8; // ebx
  HANDLE v9; // rcx
  BOOL v10; // ebx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  bool v12; // zf
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  DWORD nOutBufferSize; // [rsp+28h] [rbp-30h]
  int lpBytesReturned; // [rsp+30h] [rbp-28h]
  DWORD BytesReturned; // [rsp+68h] [rbp+10h] BYREF

  v3 = *((_DWORD *)a2 + 28);
  lpBytesReturned = *((_DWORD *)a2 + 31);
  lpOverlapped = a2;
  nOutBufferSize = *((_DWORD *)a2 + 30);
  v5 = *((_DWORD *)a2 + 9);
  v6 = off_18000A000[*((_DWORD *)a2 + 27) - 117637377];
  BytesReturned = 0;
  TspLog(
    4,
    "AsyncDriverRequest: oid(%s), devID(%x), ReqID(%x), reqID(%x), hdCall(%x)",
    v6,
    v3,
    v5,
    nOutBufferSize,
    lpBytesReturned);
  v7 = *((_DWORD *)lpOverlapped + 9);
  v8 = *((_DWORD *)lpOverlapped + 29) + 19;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  ++*((_DWORD *)lpOverlapped + 22);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v9 = ghDriverAsync;
  *((_DWORD *)lpOverlapped - 4) = 1;
  v10 = DeviceIoControl(
          v9,
          dwIoControlCode,
          lpOverlapped + 104,
          v8,
          lpOverlapped + 104,
          v8,
          &BytesReturned,
          (LPOVERLAPPED)lpOverlapped);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v11 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
  v12 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
  if ( v12 )
  {
    LeaveCriticalSection(v11);
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
    FreeRequest(lpOverlapped);
    lpOverlapped = 0;
  }
  else
  {
    LeaveCriticalSection(v11);
  }
  if ( !v10 )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      TspLog(1, "AsyncDriverRequest: IoCtl(oid %x) failed(%d)", *((_DWORD *)lpOverlapped + 27), LastError);
      ((void (__fastcall *)(_QWORD, __int64))gpfnCompletionProc)(*((unsigned int *)lpOverlapped + 9), 2147483720LL);
      EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
      v12 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
      v14 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
      if ( v12 )
      {
        LeaveCriticalSection(v14);
        DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
        FreeRequest(lpOverlapped);
      }
      else
      {
        LeaveCriticalSection(v14);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002b6c  mov     [rsp+arg_0], rbx
0x180002b71  mov     [rsp+arg_18], rbp
0x180002b76  push    rsi
0x180002b77  push    rdi
0x180002b78  push    r14
0x180002b7a  sub     rsp, 40h
0x180002b7e  mov     r8d, [rdx+6Ch]
0x180002b82  mov     edi, ecx
0x180002b84  mov     eax, [rdx+7Ch]
0x180002b87  lea     rcx, off_18000A000; "Accept"
0x180002b8e  mov     r9d, [rdx+70h]
0x180002b92  sub     r8d, 7030101h
0x180002b99  mov     dword ptr [rsp+58h+lpBytesReturned], eax
0x180002b9d  mov     rsi, rdx
0x180002ba0  mov     eax, [rdx+78h]
0x180002ba3  mov     [rsp+58h+nOutBufferSize], eax
0x180002ba7  mov     eax, [rdx+24h]
0x180002baa  lea     rdx, aAsyncdriverreq; "AsyncDriverRequest: oid(%s), devID(%x),"...
0x180002bb1  mov     r8, [rcx+r8*8]
0x180002bb5  mov     ecx, 4
0x180002bba  mov     [rsp+58h+BytesReturned], 0
0x180002bc2  mov     dword ptr [rsp+58h+lpOutBuffer], eax
0x180002bc6  call    TspLog
0x180002bcb  mov     ebx, [rsi+74h]
0x180002bce  lea     rbp, [rsi+30h]
0x180002bd2  mov     r14d, [rsi+24h]
0x180002bd6  mov     rcx, rbp; lpCriticalSection
0x180002bd9  add     ebx, 13h
0x180002bdc  call    cs:__imp_EnterCriticalSection
0x180002be3  nop     dword ptr [rax+rax+00h]
0x180002be8  inc     dword ptr [rsi+58h]
0x180002beb  mov     rcx, rbp; lpCriticalSection
0x180002bee  call    cs:__imp_LeaveCriticalSection
0x180002bf5  nop     dword ptr [rax+rax+00h]
0x180002bfa  mov     rcx, cs:ghDriverAsync; hDevice
0x180002c01  lea     rax, [rsp+58h+BytesReturned]
0x180002c06  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x180002c0b  lea     r8, [rsi+68h]; lpInBuffer
0x180002c0f  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x180002c14  mov     r9d, ebx; nInBufferSize
0x180002c17  mov     [rsp+58h+nOutBufferSize], ebx; nOutBufferSize
0x180002c1b  mov     edx, edi; dwIoControlCode
0x180002c1d  mov     [rsp+58h+lpOutBuffer], r8; lpOutBuffer
0x180002c22  mov     dword ptr [rsi-10h], 1
0x180002c29  call    cs:__imp_DeviceIoControl
0x180002c30  nop     dword ptr [rax+rax+00h]
0x180002c35  mov     rcx, rbp; lpCriticalSection
0x180002c38  mov     ebx, eax
0x180002c3a  call    cs:__imp_EnterCriticalSection
0x180002c41  nop     dword ptr [rax+rax+00h]
0x180002c46  or      edi, 0FFFFFFFFh
0x180002c49  mov     rcx, rbp; lpCriticalSection
0x180002c4c  add     [rsi+58h], edi
0x180002c4f  jnz     short loc_180002C78
0x180002c51  call    cs:__imp_LeaveCriticalSection
0x180002c58  nop     dword ptr [rax+rax+00h]
0x180002c5d  mov     rcx, rbp; lpCriticalSection
0x180002c60  call    cs:__imp_DeleteCriticalSection
0x180002c67  nop     dword ptr [rax+rax+00h]
0x180002c6c  mov     rcx, rsi; void *
0x180002c6f  call    FreeRequest
0x180002c74  xor     esi, esi
0x180002c76  jmp     short loc_180002C84
0x180002c78  call    cs:__imp_LeaveCriticalSection
0x180002c7f  nop     dword ptr [rax+rax+00h]
0x180002c84  cmp     ebx, 1
0x180002c87  jz      loc_180002D18
0x180002c8d  call    cs:__imp_GetLastError
0x180002c94  nop     dword ptr [rax+rax+00h]
0x180002c99  cmp     eax, 3E5h
0x180002c9e  jz      short loc_180002D18
0x180002ca0  mov     r8d, [rsi+6Ch]
0x180002ca4  lea     rdx, aAsyncdriverreq_0; "AsyncDriverRequest: IoCtl(oid %x) faile"...
0x180002cab  mov     r9d, eax
0x180002cae  mov     ecx, 1
0x180002cb3  call    TspLog
0x180002cb8  mov     ecx, [rsi+24h]
0x180002cbb  mov     edx, 80000048h
0x180002cc0  mov     rax, cs:gpfnCompletionProc
0x180002cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccc  lea     rbx, [rsi+30h]
0x180002cd0  mov     rcx, rbx; lpCriticalSection
0x180002cd3  call    cs:__imp_EnterCriticalSection
0x180002cda  nop     dword ptr [rax+rax+00h]
0x180002cdf  add     [rsi+58h], edi
0x180002ce2  mov     rcx, rbx; lpCriticalSection
0x180002ce5  jnz     short loc_180002D0C
0x180002ce7  call    cs:__imp_LeaveCriticalSection
0x180002cee  nop     dword ptr [rax+rax+00h]
0x180002cf3  mov     rcx, rbx; lpCriticalSection
0x180002cf6  call    cs:__imp_DeleteCriticalSection
0x180002cfd  nop     dword ptr [rax+rax+00h]
0x180002d02  mov     rcx, rsi; void *
0x180002d05  call    FreeRequest
0x180002d0a  jmp     short loc_180002D18
0x180002d0c  call    cs:__imp_LeaveCriticalSection
0x180002d13  nop     dword ptr [rax+rax+00h]
0x180002d18  mov     rbx, [rsp+58h+arg_0]
0x180002d1d  mov     eax, r14d
0x180002d20  mov     rbp, [rsp+58h+arg_18]
0x180002d25  add     rsp, 40h
0x180002d29  pop     r14
0x180002d2b  pop     rdi
0x180002d2c  pop     rsi
0x180002d2d  retn
```
