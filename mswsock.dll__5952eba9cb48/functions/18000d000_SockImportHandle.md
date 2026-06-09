# SockImportHandle

- ea: `0x18000d000`
- end: `0x18000db2a`
- name: `SockImportHandle`
- size: `2858`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008190`
- `0x18003d540`

## callees

- `0x1800052a0`
- `0x180006d00`
- `0x180008250`
- `0x18000b3a0`
- `0x18000c1f0`
- `0x18000ca20`
- `0x18000d000`
- `0x18000db30`
- `0x18000e428`
- `0x18000ea70`
- `0x18000f4c8`
- `0x18000fa40`
- `0x1800222f0`
- `0x180022bd2`
- `0x180037195`
- `0x180038118`
- `0x1800387e8`
- `0x180038874`
- `0x18003ae8c`
- `0x18004d924`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d08f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d08f`
- `ntdll!NtClose` at `0x18000da81`
- `ntdll!NtClose` at `0x18000da9f`
- `ntdll!NtClose` at `0x18000da81`
- `ntdll!NtClose` at `0x18000da9f`
- `ntdll!RtlInitUnicodeString` at `0x18000d0e4`
- `ntdll!RtlInitUnicodeString` at `0x18000d8cf`
- `ntdll!RtlInitUnicodeString` at `0x18000d0e4`
- `ntdll!RtlInitUnicodeString` at `0x18000d8cf`
- `ntdll!RtlFreeHeap` at `0x18000d8b9`
- `ntdll!RtlFreeHeap` at `0x18000da36`
- `ntdll!RtlFreeHeap` at `0x18000dab7`
- `ntdll!RtlFreeHeap` at `0x18000db19`
- `ntdll!RtlFreeHeap` at `0x18000d8b9`
- `ntdll!RtlFreeHeap` at `0x18000da36`
- `ntdll!RtlFreeHeap` at `0x18000dab7`
- `ntdll!RtlFreeHeap` at `0x18000db19`
- `ntdll!NtDeviceIoControlFile` at `0x18000d148`
- `ntdll!NtDeviceIoControlFile` at `0x18000d2f5`
- `ntdll!NtDeviceIoControlFile` at `0x18000d148`
- `ntdll!NtDeviceIoControlFile` at `0x18000d2f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da63`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d54e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d54e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1ae`
- `WS2_32!WahReferenceContextByHandle` at `0x18000d0b6`
- `WS2_32!WahReferenceContextByHandle` at `0x18000d729`
- `WS2_32!WahReferenceContextByHandle` at `0x18000d0b6`
- `WS2_32!WahReferenceContextByHandle` at `0x18000d729`
- `WS2_32!WahInsertHandleContext` at `0x18000d68d`
- `WS2_32!WahInsertHandleContext` at `0x18000d68d`

## pseudocode

```c
char *__fastcall SockImportHandle(HANDLE FileHandle, _DWORD *a2, char a3)
{
  HANDLE *Value; // r13
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // r12
  _BYTE *v12; // r15
  NTSTATUS Status; // eax
  const char *v14; // r14
  int v15; // ecx
  __int64 v16; // rdx
  int v17; // ecx
  __int64 v18; // r8
  int v20; // eax
  _BYTE *OutputBuffer; // rax
  __int64 v22; // rax
  int v23; // edx
  int v24; // r8d
  unsigned __int64 v25; // rdx
  size_t v26; // r8
  _BYTE *v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 inserted; // rax
  volatile signed __int32 *v31; // rdi
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r14
  unsigned int v38; // edx
  int v39; // r14d
  __int64 v40; // r10
  char v41; // r14
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // ecx
  const char *v45; // rax
  char *v46; // rcx
  char *v47; // rcx
  char v48; // [rsp+50h] [rbp-1A8h]
  char v49[7]; // [rsp+51h] [rbp-1A7h] BYREF
  __int64 v50; // [rsp+58h] [rbp-1A0h] BYREF
  int v51; // [rsp+60h] [rbp-198h] BYREF
  char v52; // [rsp+64h] [rbp-194h]
  int v53; // [rsp+68h] [rbp-190h] BYREF
  __int64 v54; // [rsp+70h] [rbp-188h] BYREF
  NTSTATUS v55; // [rsp+78h] [rbp-180h]
  int v56; // [rsp+7Ch] [rbp-17Ch] BYREF
  int v57; // [rsp+80h] [rbp-178h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-170h] BYREF
  _BYTE *v59; // [rsp+98h] [rbp-160h]
  __int64 v60; // [rsp+A0h] [rbp-158h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-150h] BYREF
  HANDLE v62; // [rsp+B8h] [rbp-140h]
  _BYTE P[256]; // [rsp+C0h] [rbp-138h] BYREF

  v52 = a3;
  v62 = FileHandle;
  IoStatusBlock = 0;
  DestinationString = 0;
  v54 = 0;
  v50 = 0;
  v51 = 0;
  v57 = 0;
  v53 = 0;
  v56 = 0;
  memset_0(P, 0, sizeof(P));
  Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
  if ( a2 )
    *a2 = 0;
  SockAcquireRwLockExclusive();
  v8 = WahReferenceContextByHandle(SockContextTable, FileHandle);
  if ( v8 )
  {
    SockReleaseRwLockExclusive(v7, v6, v9, v10);
    return (char *)v8;
  }
  v50 = 0;
  v11 = 0;
  v48 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v53 = 2;
  v12 = P;
  v59 = P;
  Status = NtDeviceIoControlFile(FileHandle, Value[2], 0, 0, &IoStatusBlock, 0x12043u, 0, 0, P, 0x100u);
  v55 = Status;
  if ( Status == 259 )
  {
    SockWaitForSingleObject(Value[2]);
    Status = IoStatusBlock.Status;
    v55 = IoStatusBlock.Status;
  }
  if ( Status == -2147483643 )
  {
    OutputBuffer = (_BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                              SockPrivateHeap,
                              0,
                              LODWORD(IoStatusBlock.Information));
    v12 = OutputBuffer;
    v59 = OutputBuffer;
    if ( !OutputBuffer )
      goto LABEL_9;
    Status = NtDeviceIoControlFile(
               FileHandle,
               Value[2],
               0,
               0,
               &IoStatusBlock,
               0x12043u,
               0,
               0,
               OutputBuffer,
               IoStatusBlock.Information);
    v55 = Status;
    if ( Status == 259 )
    {
      SockWaitForSingleObject(Value[2]);
      Status = IoStatusBlock.Status;
      v55 = IoStatusBlock.Status;
    }
  }
  if ( Status < 0 || IoStatusBlock.Information < 0x78 )
  {
    if ( a2 && Status == -1073741811 )
      *a2 = 1;
    goto LABEL_9;
  }
  v49[0] = 0;
  if ( !SockVerifyAndFixCatalogEntry((__int64)v12, (unsigned __int64)v49) )
    goto LABEL_9;
  if ( v49[0] )
  {
    v37 = WahReferenceContextByHandle(SockContextTable, FileHandle);
    if ( v37 )
    {
      SockReleaseRwLockExclusive(v34, v33, v35, v36);
      return (char *)v37;
    }
  }
  v57 = *((_DWORD *)v12 + 1);
  v53 = *((_DWORD *)v12 + 2);
  v56 = *((_DWORD *)v12 + 3);
  if ( (unsigned int)SockGetTdiName(
                       (unsigned int)&v57,
                       (unsigned int)&v53,
                       (unsigned int)&v56,
                       (int)v12 + 104,
                       0,
                       0,
                       (__int64)&DestinationString,
                       (__int64)&v54,
                       (__int64)&v50,
                       (__int64)&v51) )
    goto LABEL_9;
  if ( (v12[45] & 0x10) != 0 )
  {
    if ( !DestinationString.Length )
      goto LABEL_37;
LABEL_59:
    if ( (v51 & 0x80u) == 0 )
      goto LABEL_9;
    goto LABEL_58;
  }
  if ( !DestinationString.Length )
  {
    if ( IsAppContainer() )
      goto LABEL_59;
    switch ( v53 )
    {
      case 1:
        if ( SockTLNPIListenerCount > 0 )
          goto LABEL_59;
        v38 = 0x80000000;
        v39 = 1;
        break;
      case 2:
        v38 = 0x40000000;
        v39 = 2;
        break;
      case 3:
        v38 = 0x20000000;
        v39 = 4;
        break;
      default:
        v38 = 0;
        v39 = 0;
        break;
    }
    v40 = v50;
    if ( (v39 & *(_DWORD *)(v50 + 52)) == 0 && (v38 & v51) != 0 )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int))(v50 + 104))(
              v54,
              -1,
              0,
              0,
              v38) )
      {
        v41 = 0;
LABEL_76:
        if ( (v51 & 0x80u) != 0 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(v50 + 104))(v54, -1, 0, 0, 128);
        if ( DestinationString.Buffer && v53 == 3 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
        RtlInitUnicodeString(&DestinationString, 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v50 + 16), 0xFFFFFFFF) == 1 )
          SockFreeHelperDll(v50, v42, v43);
        v50 = 0;
        if ( v41
          || (unsigned int)SockGetTdiName(
                             (unsigned int)&v57,
                             (unsigned int)&v53,
                             (unsigned int)&v56,
                             (int)v12 + 104,
                             0,
                             0,
                             (__int64)&DestinationString,
                             (__int64)&v54,
                             (__int64)&v50,
                             (__int64)&v51) )
        {
          goto LABEL_9;
        }
        if ( !DestinationString.Length )
        {
LABEL_57:
          if ( (v51 & 0x80u) != 0 )
LABEL_58:
            (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(v50 + 104))(v54, -1, 0, 0, 128);
LABEL_9:
          v14 = "SOCK_DGRAM";
          goto LABEL_10;
        }
        goto LABEL_37;
      }
      v40 = v50;
    }
    *(_DWORD *)(v40 + 52) |= v39;
    v41 = 1;
    goto LABEL_76;
  }
LABEL_37:
  v22 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
          SockPrivateHeap,
          0,
          2 * ((*(_DWORD *)(v50 + 36) + 7) & 0xFFFFFFF8) + 280);
  v11 = (char *)v22;
  v60 = v22;
  if ( !v22 )
    goto LABEL_57;
  *(_OWORD *)(v22 + 24) = *(_OWORD *)v12;
  *(_OWORD *)(v22 + 40) = *((_OWORD *)v12 + 1);
  *(_OWORD *)(v22 + 56) = *((_OWORD *)v12 + 2);
  *(_OWORD *)(v22 + 72) = *((_OWORD *)v12 + 3);
  *(_OWORD *)(v22 + 88) = *((_OWORD *)v12 + 4);
  *(_OWORD *)(v22 + 104) = *((_OWORD *)v12 + 5);
  *(_OWORD *)(v22 + 120) = *((_OWORD *)v12 + 6);
  *(_QWORD *)(v22 + 136) = *((_QWORD *)v12 + 14);
  v14 = "SOCK_DGRAM";
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    v44 = *(_DWORD *)(v22 + 32);
    if ( v44 == 2 )
    {
      v45 = "SOCK_DGRAM";
    }
    else
    {
      v45 = "SOCK_STREAM";
      if ( v44 != 1 )
        v45 = "SOCK_RAW";
    }
    WPP_SF_is(v44, v23, v24, *((_QWORD *)v11 + 1), (__int64)v45);
  }
  *((_QWORD *)v11 + 1) = FileHandle;
  *(_DWORD *)v11 = 2;
  *((_QWORD *)v11 + 20) = v54;
  *((_QWORD *)v11 + 19) = v50;
  *((_DWORD *)v11 + 36) = v51;
  v25 = (unsigned __int64)(v11 + 287) & 0xFFFFFFFFFFFFFFF8uLL;
  *((_QWORD *)v11 + 21) = v25;
  *((_QWORD *)v11 + 22) = (v25 + *(int *)(v50 + 36) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  *((_QWORD *)v11 + 23) = 0;
  *((_QWORD *)v11 + 24) = 0;
  *((_QWORD *)v11 + 25) = 0;
  *((_QWORD *)v11 + 26) = 0;
  *((_DWORD *)v11 + 54) = 0;
  *((_QWORD *)v11 + 33) = 0;
  *((_QWORD *)v11 + 34) = 0;
  *((_QWORD *)v11 + 2) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 224));
  v48 = 1;
  LODWORD(v59) = *((_DWORD *)v12 + 30);
  memcpy_0(*((void **)v11 + 21), v12 + 128, *(int *)(v50 + 36));
  v26 = *(int *)(v50 + 36);
  v27 = &v12[((v26 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 128];
  memcpy_0(*((void **)v11 + 22), v27, v26);
  LODWORD(v60) = *(_DWORD *)(v50 + 36);
  if ( !(unsigned int)SockGetTdiHandles(v11, v28, v29)
    && !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int, _BYTE *, _DWORD))(*((_QWORD *)v11 + 19)
                                                                                                  + 120LL))(
          *((_QWORD *)v11 + 20),
          *((_QWORD *)v11 + 1),
          *((_QWORD *)v11 + 23),
          *((_QWORD *)v11 + 24),
          65534,
          1,
          &v27[((int)v60 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL],
          (_DWORD)v59) )
  {
    if ( SockSanEnabled && v52 && v55 == 261 && (v32 = SockSanImportSocket((__int64)v11)) != 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 15, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, v32);
    }
    else
    {
      if ( (v11[68] & 1) != 0 && (v11[69] & 0x10) != 0 )
        _InterlockedIncrement(&SockTLNPIListenerCount);
      inserted = WahInsertHandleContext(SockContextTable, v11);
      v31 = (volatile signed __int32 *)inserted;
      if ( inserted )
      {
        if ( (char *)inserted != v11 )
        {
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_q(1025, 16, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, *((_QWORD *)v11 + 1));
          if ( _InterlockedExchangeAdd(v31, 0xFFFFFFFF) == 1 )
            SockDestroySocket(v31);
        }
        LOBYTE(v8) = 1;
        goto LABEL_10;
      }
      if ( (v11[68] & 1) != 0 && (v11[69] & 0x10) != 0 )
      {
        _InterlockedDecrement(&SockTLNPIListenerCount);
        LOBYTE(v8) = 0;
        goto LABEL_10;
      }
    }
  }
  LOBYTE(v8) = 0;
LABEL_10:
  v15 = SocketGlobalLock++;
  if ( v15 == -2 )
    SocketGlobalLock = 0;
  LeaveCriticalSection(&CriticalSection);
  if ( DestinationString.Buffer && v53 == 3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( (_BYTE)v8 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v20 = *((_DWORD *)v11 + 8);
      if ( v20 != 2 )
      {
        v14 = "SOCK_STREAM";
        if ( v20 != 1 )
          v14 = "SOCK_RAW";
      }
      WPP_SF_iqs(
        v17,
        17,
        (unsigned int)WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids,
        *((_QWORD *)v11 + 1),
        (char)v11,
        (__int64)v14);
    }
  }
  else
  {
    if ( v11 )
    {
      SockNotifyHelperDll(v11, 128, v18);
      if ( v48 )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 224));
      v46 = (char *)*((_QWORD *)v11 + 23);
      if ( (unsigned __int64)(v46 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        NtClose(v46);
      v47 = (char *)*((_QWORD *)v11 + 24);
      if ( (unsigned __int64)(v47 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        NtClose(v47);
      RtlFreeHeap(SockPrivateHeap, 0, v11);
      v11 = 0;
    }
    if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)(v50 + 16), 0xFFFFFFFF) == 1 )
      SockFreeHelperDll(v50, v16, v18);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 18, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, FileHandle);
  }
  if ( v12 )
  {
    if ( v12 != P )
      RtlFreeHeap(SockPrivateHeap, 0, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x18000d000  mov     [rsp+arg_10], rbx
0x18000d005  mov     [rsp+arg_18], rsi
0x18000d00a  push    rdi
0x18000d00b  push    r12
0x18000d00d  push    r13
0x18000d00f  push    r14
0x18000d011  push    r15
0x18000d013  sub     rsp, 1D0h
0x18000d01a  mov     rax, cs:__security_cookie
0x18000d021  xor     rax, rsp
0x18000d024  mov     [rsp+1F8h+var_38], rax
0x18000d02c  mov     [rsp+1F8h+var_194], r8b
0x18000d031  mov     r14, rdx
0x18000d034  mov     rsi, rcx
0x18000d037  mov     [rsp+1F8h+var_140], rcx
0x18000d03f  xorps   xmm0, xmm0
0x18000d042  movups  xmmword ptr [rsp+1F8h+var_150], xmm0
0x18000d04a  xorps   xmm1, xmm1
0x18000d04d  movups  xmmword ptr [rsp+1F8h+DestinationString.Length], xmm1
0x18000d055  xor     ebx, ebx
0x18000d057  mov     [rsp+1F8h+var_188], rbx
0x18000d05c  mov     [rsp+1F8h+var_1A0], rbx
0x18000d061  mov     [rsp+1F8h+var_198], ebx
0x18000d065  mov     [rsp+1F8h+var_178], ebx
0x18000d06c  mov     [rsp+1F8h+var_190], ebx
0x18000d070  mov     [rsp+1F8h+var_17C], ebx
0x18000d074  xor     edx, edx; Val
0x18000d076  mov     r8d, 100h; Size
0x18000d07c  lea     rcx, [rsp+1F8h+P]; void *
0x18000d084  call    memset_0
0x18000d089  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000d08f  call    cs:__imp_TlsGetValue
0x18000d096  nop     dword ptr [rax+rax+00h]
0x18000d09b  mov     r13, rax
0x18000d09e  test    r14, r14
0x18000d0a1  jnz     loc_18000D782
0x18000d0a7  call    SockAcquireRwLockExclusive
0x18000d0ac  mov     rdx, rsi
0x18000d0af  mov     rcx, cs:SockContextTable
0x18000d0b6  call    cs:__imp_WahReferenceContextByHandle
0x18000d0bd  nop     dword ptr [rax+rax+00h]
0x18000d0c2  mov     rdi, rax
0x18000d0c5  test    rax, rax
0x18000d0c8  jnz     loc_18000D239
0x18000d0ce  mov     [rsp+1F8h+var_1A0], rbx
0x18000d0d3  mov     r12, rbx
0x18000d0d6  mov     [rsp+1F8h+var_1A8], al
0x18000d0da  xor     edx, edx; SourceString
0x18000d0dc  lea     rcx, [rsp+1F8h+DestinationString]; DestinationString
0x18000d0e4  call    cs:__imp_RtlInitUnicodeString
0x18000d0eb  nop     dword ptr [rax+rax+00h]
0x18000d0f0  mov     [rsp+1F8h+var_190], 2
0x18000d0f8  lea     r15, [rsp+1F8h+P]
0x18000d100  mov     [rsp+1F8h+var_160], r15
0x18000d108  mov     [rsp+1F8h+OutputBufferLength], 100h; OutputBufferLength
0x18000d110  lea     rax, [rsp+1F8h+P]
0x18000d118  mov     [rsp+1F8h+OutputBuffer], rax; OutputBuffer
0x18000d11d  mov     [rsp+1F8h+InputBufferLength], ebx; InputBufferLength
0x18000d121  mov     [rsp+1F8h+InputBuffer], rbx; InputBuffer
0x18000d126  mov     [rsp+1F8h+IoControlCode], 12043h; IoControlCode
0x18000d12e  lea     rax, [rsp+1F8h+var_150]
0x18000d136  mov     [rsp+1F8h+IoStatusBlock], rax; IoStatusBlock
0x18000d13b  xor     r9d, r9d; ApcContext
0x18000d13e  xor     r8d, r8d; ApcRoutine
0x18000d141  mov     rdx, [r13+10h]; Event
0x18000d145  mov     rcx, rsi; FileHandle
0x18000d148  call    cs:__imp_NtDeviceIoControlFile
0x18000d14f  nop     dword ptr [rax+rax+00h]
0x18000d154  mov     [rsp+1F8h+var_180], eax
0x18000d158  cmp     eax, 103h
0x18000d15d  jz      loc_18000D78A
0x18000d163  cmp     eax, 80000005h
0x18000d168  jz      loc_18000D289
0x18000d16e  test    eax, eax
0x18000d170  jns     loc_18000D338
0x18000d176  test    r14, r14
0x18000d179  jnz     loc_18000D9FD
0x18000d17f  lea     r13, aSockRaw; "SOCK_RAW"
0x18000d186  lea     r14, aSockDgram; "SOCK_DGRAM"
0x18000d18d  mov     ecx, cs:SocketGlobalLock
0x18000d193  lea     eax, [rcx+1]
0x18000d196  mov     cs:SocketGlobalLock, eax
0x18000d19c  cmp     ecx, 0FFFFFFFEh
0x18000d19f  jnz     short loc_18000D1A7
0x18000d1a1  mov     cs:SocketGlobalLock, ebx
0x18000d1a7  lea     rcx, CriticalSection; lpCriticalSection
0x18000d1ae  call    cs:__imp_LeaveCriticalSection
0x18000d1b5  nop     dword ptr [rax+rax+00h]
0x18000d1ba  cmp     [rsp+1F8h+DestinationString.Buffer], 0
0x18000d1c3  jnz     loc_18000DA14
0x18000d1c9  test    dil, dil
0x18000d1cc  jnz     short loc_18000D243
0x18000d1ce  test    r12, r12
0x18000d1d1  jnz     loc_18000DA47
0x18000d1d7  mov     rax, [rsp+1F8h+var_1A0]
0x18000d1dc  test    rax, rax
0x18000d1df  jnz     loc_18000DACB
0x18000d1e5  test    byte ptr cs:xmmword_180063D60, 2
0x18000d1ec  jnz     loc_18000DAEF
0x18000d1f2  test    r15, r15
0x18000d1f5  jz      short loc_18000D208
0x18000d1f7  lea     rax, [rsp+1F8h+P]
0x18000d1ff  cmp     r15, rax
0x18000d202  jnz     loc_18000DB0D
0x18000d208  mov     rax, r12
0x18000d20b  mov     rcx, [rsp+1F8h+var_38]
0x18000d213  xor     rcx, rsp; StackCookie
0x18000d216  call    __security_check_cookie
0x18000d21b  lea     r11, [rsp+1F8h+var_28]
0x18000d223  mov     rbx, [r11+40h]
0x18000d227  mov     rsi, [r11+48h]
0x18000d22b  mov     rsp, r11
0x18000d22e  pop     r15
0x18000d230  pop     r14
0x18000d232  pop     r13
0x18000d234  pop     r12
0x18000d236  pop     rdi
0x18000d237  retn
0x18000d239  call    SockReleaseRwLockExclusive
0x18000d23e  mov     rax, rdi
0x18000d241  jmp     short loc_18000D20B
0x18000d243  test    byte ptr cs:xmmword_180063D60, 2
0x18000d24a  jz      short loc_18000D1F2
0x18000d24c  mov     eax, [r12+20h]
0x18000d251  cmp     eax, 2
0x18000d254  jz      short loc_18000D264
0x18000d256  lea     r14, aSockStream; "SOCK_STREAM"
0x18000d25d  cmp     eax, 1
0x18000d260  cmovnz  r14, r13
0x18000d264  mov     edx, 11h
0x18000d269  mov     qword ptr [rsp+1F8h+IoControlCode], r14
0x18000d26e  mov     [rsp+1F8h+IoStatusBlock], r12
0x18000d273  mov     r9, [r12+8]
0x18000d278  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x18000d27f  call    WPP_SF_iqs
0x18000d284  jmp     loc_18000D1F2
0x18000d289  mov     r8d, dword ptr [rsp+1F8h+var_150.Information]
0x18000d291  xor     edx, edx
0x18000d293  mov     rcx, cs:SockPrivateHeap
0x18000d29a  mov     rax, cs:SockAllocateHeapRoutine
0x18000d2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2a6  mov     r15, rax
0x18000d2a9  mov     [rsp+1F8h+var_160], rax
0x18000d2b1  test    rax, rax
0x18000d2b4  jz      loc_18000D17F
0x18000d2ba  mov     ecx, dword ptr [rsp+1F8h+var_150.Information]
0x18000d2c1  mov     [rsp+1F8h+OutputBufferLength], ecx; OutputBufferLength
0x18000d2c5  mov     [rsp+1F8h+OutputBuffer], rax; OutputBuffer
0x18000d2ca  mov     [rsp+1F8h+InputBufferLength], ebx; InputBufferLength
0x18000d2ce  mov     [rsp+1F8h+InputBuffer], rbx; InputBuffer
0x18000d2d3  mov     [rsp+1F8h+IoControlCode], 12043h; IoControlCode
0x18000d2db  lea     rax, [rsp+1F8h+var_150]
0x18000d2e3  mov     [rsp+1F8h+IoStatusBlock], rax; IoStatusBlock
0x18000d2e8  xor     r9d, r9d; ApcContext
0x18000d2eb  xor     r8d, r8d; ApcRoutine
0x18000d2ee  mov     rdx, [r13+10h]; Event
0x18000d2f2  mov     rcx, rsi; FileHandle
0x18000d2f5  call    cs:__imp_NtDeviceIoControlFile
0x18000d2fc  nop     dword ptr [rax+rax+00h]
0x18000d301  mov     [rsp+1F8h+var_180], eax
0x18000d305  cmp     eax, 103h
0x18000d30a  jnz     loc_18000D16E
0x18000d310  mov     r9d, 4
0x18000d316  mov     r8d, 3
0x18000d31c  mov     rdx, rsi
0x18000d31f  mov     rcx, [r13+10h]; Handle
0x18000d323  call    SockWaitForSingleObject
0x18000d328  mov     eax, dword ptr [rsp+1F8h+var_150]
0x18000d32f  mov     [rsp+1F8h+var_180], eax
0x18000d333  jmp     loc_18000D16E
0x18000d338  cmp     [rsp+1F8h+var_150.Information], 78h ; 'x'
0x18000d341  jb      loc_18000D176
0x18000d347  mov     [rsp+1F8h+var_1A7], bl
0x18000d34b  lea     rdx, [rsp+1F8h+var_1A7]
0x18000d350  mov     rcx, r15
0x18000d353  call    SockVerifyAndFixCatalogEntry
0x18000d358  test    al, al
0x18000d35a  jz      loc_18000D17F
0x18000d360  cmp     [rsp+1F8h+var_1A7], bl
0x18000d364  jnz     loc_18000D71F
0x18000d36a  mov     eax, [r15+4]
0x18000d36e  mov     [rsp+1F8h+var_178], eax
0x18000d375  mov     eax, [r15+8]
0x18000d379  mov     [rsp+1F8h+var_190], eax
0x18000d37d  mov     eax, [r15+0Ch]
0x18000d381  mov     [rsp+1F8h+var_17C], eax
0x18000d385  lea     r9, [r15+68h]
0x18000d389  lea     rcx, [rsp+1F8h+var_198]
0x18000d38e  mov     qword ptr [rsp+1F8h+OutputBufferLength], rcx
0x18000d393  lea     rcx, [rsp+1F8h+var_1A0]
0x18000d398  mov     [rsp+1F8h+OutputBuffer], rcx
0x18000d39d  lea     rcx, [rsp+1F8h+var_188]
0x18000d3a2  mov     qword ptr [rsp+1F8h+InputBufferLength], rcx
0x18000d3a7  lea     rcx, [rsp+1F8h+DestinationString]
0x18000d3af  mov     [rsp+1F8h+InputBuffer], rcx
0x18000d3b4  mov     [rsp+1F8h+IoControlCode], ebx
0x18000d3b8  mov     dword ptr [rsp+1F8h+IoStatusBlock], ebx
0x18000d3bc  lea     r8, [rsp+1F8h+var_17C]
0x18000d3c1  lea     rdx, [rsp+1F8h+var_190]
0x18000d3c6  lea     rcx, [rsp+1F8h+var_178]
0x18000d3ce  call    SockGetTdiName
0x18000d3d3  test    eax, eax
0x18000d3d5  jnz     loc_18000D17F
0x18000d3db  cmp     [rsp+1F8h+DestinationString.Length], bx
0x18000d3e3  setz    al
0x18000d3e6  test    byte ptr [r15+2Dh], 10h
0x18000d3eb  jz      loc_18000D7C6
0x18000d3f1  test    al, al
0x18000d3f3  jz      loc_18000D7B2
0x18000d3f9  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000d400  mov     rax, [rsp+1F8h+var_1A0]
0x18000d405  mov     eax, [rax+24h]
0x18000d408  add     eax, 7
0x18000d40b  and     eax, 0FFFFFFF8h
0x18000d40e  lea     r8d, ds:118h[rax*2]
0x18000d416  xor     edx, edx
0x18000d418  mov     rcx, cs:SockPrivateHeap
0x18000d41f  mov     rax, cs:SockAllocateHeapRoutine
0x18000d426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d42b  mov     r12, rax
0x18000d42e  mov     [rsp+1F8h+var_158], rax
0x18000d436  test    rax, rax
0x18000d439  jz      loc_18000D74E
0x18000d43f  movups  xmm0, xmmword ptr [r15]
0x18000d443  movups  xmmword ptr [rax+18h], xmm0
0x18000d447  movups  xmm1, xmmword ptr [r15+10h]
0x18000d44c  movups  xmmword ptr [rax+28h], xmm1
0x18000d450  movups  xmm0, xmmword ptr [r15+20h]
0x18000d455  movups  xmmword ptr [rax+38h], xmm0
0x18000d459  movups  xmm1, xmmword ptr [r15+30h]
0x18000d45e  movups  xmmword ptr [rax+48h], xmm1
0x18000d462  movups  xmm0, xmmword ptr [r15+40h]
0x18000d467  movups  xmmword ptr [rax+58h], xmm0
0x18000d46b  movups  xmm1, xmmword ptr [r15+50h]
0x18000d470  movups  xmmword ptr [rax+68h], xmm1
0x18000d474  movups  xmm0, xmmword ptr [r15+60h]
0x18000d479  movups  xmmword ptr [rax+78h], xmm0
0x18000d47d  movsd   xmm1, qword ptr [r15+70h]
0x18000d483  movsd   qword ptr [rax+88h], xmm1
0x18000d48b  lea     r14, aSockDgram; "SOCK_DGRAM"
0x18000d492  lea     r13, aSockRaw; "SOCK_RAW"
0x18000d499  test    byte ptr cs:xmmword_180063D60, 2
0x18000d4a0  jnz     loc_18000D96E
0x18000d4a6  mov     [r12+8], rsi
0x18000d4ab  mov     dword ptr [r12], 2
0x18000d4b3  mov     rax, [rsp+1F8h+var_188]
0x18000d4b8  mov     [r12+0A0h], rax
0x18000d4c0  mov     rax, [rsp+1F8h+var_1A0]
0x18000d4c5  mov     [r12+98h], rax
0x18000d4cd  mov     eax, [rsp+1F8h+var_198]
0x18000d4d1  mov     [r12+90h], eax
0x18000d4d9  lea     rdx, [r12+11Fh]
0x18000d4e1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000d4e5  mov     [r12+0A8h], rdx
0x18000d4ed  mov     rax, [rsp+1F8h+var_1A0]
0x18000d4f2  movsxd  rax, dword ptr [rax+24h]
0x18000d4f6  add     rax, 7
0x18000d4fa  add     rax, rdx
0x18000d4fd  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d501  mov     [r12+0B0h], rax
0x18000d509  mov     [r12+0B8h], rbx
0x18000d511  mov     [r12+0C0h], rbx
0x18000d519  mov     [r12+0C8h], rbx
0x18000d521  mov     [r12+0D0h], rbx
0x18000d529  mov     [r12+0D8h], ebx
0x18000d531  mov     [r12+108h], rbx
0x18000d539  mov     [r12+110h], rbx
0x18000d541  mov     [r12+10h], rbx
0x18000d546  lea     rcx, [r12+0E0h]; lpCriticalSection
0x18000d54e  call    cs:__imp_InitializeCriticalSection
0x18000d555  nop     dword ptr [rax+rax+00h]
0x18000d55a  jmp     short loc_18000D597
0x18000d55c  mov     ecx, eax
0x18000d55e  call    NtStatusToSocketError
0x18000d563  xor     ebx, ebx
0x18000d565  lea     r14, aSockDgram; "SOCK_DGRAM"
0x18000d56c  lea     r13, aSockRaw; "SOCK_RAW"
0x18000d573  mov     r15, [rsp+1F8h+var_160]
0x18000d57b  mov     r12, [rsp+1F8h+var_158]
0x18000d583  movzx   edi, bl
0x18000d586  mov     [rsp+1F8h+var_1A8], bl
0x18000d58a  mov     rsi, [rsp+1F8h+var_140]
0x18000d592  jmp     loc_18000D18D
0x18000d597  mov     [rsp+1F8h+var_1A8], 1
0x18000d59c  mov     eax, [r15+78h]
0x18000d5a0  mov     dword ptr [rsp+1F8h+var_160], eax
0x18000d5a7  lea     rdi, [r15+80h]
0x18000d5ae  mov     rax, [rsp+1F8h+var_1A0]
0x18000d5b3  movsxd  r8, dword ptr [rax+24h]; Size
0x18000d5b7  mov     rdx, rdi; Src
0x18000d5ba  mov     rcx, [r12+0A8h]; void *
0x18000d5c2  call    memcpy_0
0x18000d5c7  mov     rax, [rsp+1F8h+var_1A0]
0x18000d5cc  movsxd  r8, dword ptr [rax+24h]; Size
0x18000d5d0  lea     rax, [r8+7]
0x18000d5d4  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d5d8  add     rdi, rax
0x18000d5db  mov     rdx, rdi; Src
0x18000d5de  mov     rcx, [r12+0B0h]; void *
0x18000d5e6  call    memcpy_0
  ... truncated ...
```
