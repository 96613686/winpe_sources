# SockSocket

- ea: `0x18000a6b0`
- end: `0x18000b395`
- name: `SockSocket`
- size: `3301`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2a0`
- `0x180025530`
- `0x180027140`

## callees

- `0x1800052a0`
- `0x180008250`
- `0x18000a6b0`
- `0x18000b3a0`
- `0x18000c1f0`
- `0x18000f4c8`
- `0x18000f9f0`
- `0x18000fa40`
- `0x18001be40`
- `0x18001ed78`
- `0x1800222f0`
- `0x180022bd2`
- `0x180037195`
- `0x180038118`
- `0x180053010`

## import_xrefs

- `ntdll!ShipAssert` at `0x18000b221`
- `ntdll!ShipAssert` at `0x18000b221`
- `ntdll!NtClose` at `0x18000b347`
- `ntdll!NtClose` at `0x18000b347`
- `ntdll!NtCreateFile` at `0x18000ac29`
- `ntdll!NtCreateFile` at `0x18000b08f`
- `ntdll!NtCreateFile` at `0x18000ac29`
- `ntdll!NtCreateFile` at `0x18000b08f`
- `ntdll!RtlInitUnicodeString` at `0x18000a7b0`
- `ntdll!RtlInitUnicodeString` at `0x18000ab35`
- `ntdll!RtlInitUnicodeString` at `0x18000a7b0`
- `ntdll!RtlInitUnicodeString` at `0x18000ab35`
- `ntdll!RtlFreeHeap` at `0x18000af9f`
- `ntdll!RtlFreeHeap` at `0x18000b02d`
- `ntdll!RtlFreeHeap` at `0x18000b0c8`
- `ntdll!RtlFreeHeap` at `0x18000af9f`
- `ntdll!RtlFreeHeap` at `0x18000b02d`
- `ntdll!RtlFreeHeap` at `0x18000b0c8`
- `ntdll!NtSetEvent` at `0x18000b0ab`
- `ntdll!NtSetEvent` at `0x18000b0ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b35f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b35f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a9eb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a9eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b30c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b30c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aca1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aead`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aca1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aead`
- `WS2_32!WahInsertHandleContext` at `0x18000acb7`
- `WS2_32!WahInsertHandleContext` at `0x18000acb7`

## string_xrefs

- `0x18000aa7d`: `AfdOpenPacketXX`

## pseudocode

```c
__int64 __fastcall SockSocket(
        int a1,
        int a2,
        int a3,
        _OWORD *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        volatile signed __int32 **a10)
{
  int v10; // r14d
  int v11; // r12d
  int v12; // r13d
  _BYTE *EaBuffer; // rsi
  __int64 v14; // rdx
  unsigned int TdiName; // ebx
  __int64 v16; // r8
  unsigned int v17; // ebx
  volatile signed __int32 *v18; // rax
  volatile signed __int32 *v19; // rdi
  unsigned __int64 v20; // rdx
  char v21; // cl
  char v22; // cl
  char v23; // cl
  char v24; // al
  char v25; // cl
  int v26; // ebx
  int v27; // eax
  ULONG v28; // eax
  bool v29; // zf
  ULONG CreateOptions; // r12d
  ACCESS_MASK v31; // r13d
  int v32; // edx
  signed __int32 v33; // ebx
  signed __int32 v34; // ecx
  signed __int32 v35; // r14d
  ULONG v36; // r14d
  NTSTATUS v37; // ebx
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  volatile signed __int32 *inserted; // rbx
  int v41; // eax
  int v42; // edx
  char v43; // r14
  void *v45; // rcx
  char v46; // [rsp+61h] [rbp-187h]
  int v47; // [rsp+68h] [rbp-180h] BYREF
  char v48; // [rsp+70h] [rbp-178h]
  int v49; // [rsp+78h] [rbp-170h] BYREF
  __int64 v50; // [rsp+80h] [rbp-168h] BYREF
  int v51; // [rsp+88h] [rbp-160h] BYREF
  int v52; // [rsp+90h] [rbp-158h]
  unsigned int v53; // [rsp+94h] [rbp-154h]
  int v54; // [rsp+98h] [rbp-150h] BYREF
  unsigned int v55; // [rsp+9Ch] [rbp-14Ch]
  ULONG EaLength[2]; // [rsp+A0h] [rbp-148h]
  __int64 v57; // [rsp+A8h] [rbp-140h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-138h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp-128h] BYREF
  _OWORD *v60; // [rsp+C8h] [rbp-120h]
  PVOID P; // [rsp+D0h] [rbp-118h]
  _OWORD *v62; // [rsp+D8h] [rbp-110h]
  volatile signed __int32 **v63; // [rsp+E0h] [rbp-108h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-100h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-F0h] BYREF
  struct _UNICODE_STRING v66; // [rsp+128h] [rbp-C0h] BYREF
  _BYTE v67[96]; // [rsp+140h] [rbp-A8h] BYREF

  v60 = a4;
  v51 = a1;
  v47 = a2;
  v49 = a3;
  v62 = a4;
  v63 = a10;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v66 = 0;
  v57 = 0;
  v54 = 0;
  v48 = 0;
  v53 = 0;
  v10 = 0;
  v52 = 0;
  v11 = a6;
  v12 = a5;
  while ( 1 )
  {
    v50 = 0;
    EaBuffer = 0;
    *(_QWORD *)EaLength = 0;
    FileHandle = (void *)-1LL;
    v46 = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    TdiName = SockGetTdiName(
                (unsigned int)&v51,
                (unsigned int)&v47,
                (unsigned int)&v49,
                (_DWORD)v60,
                v12,
                v11 & 0xFFFFFE3F,
                (__int64)&DestinationString,
                (__int64)&v57,
                (__int64)&v50,
                (__int64)&v54);
    v55 = TdiName;
    if ( TdiName )
    {
      v43 = 0;
      v19 = 0;
      goto LABEL_55;
    }
    switch ( v47 )
    {
      case 1:
        v53 = 0x80000000;
        v10 = 1;
LABEL_5:
        v52 = v10;
        break;
      case 2:
        v53 = 0x40000000;
        v10 = 2;
        goto LABEL_5;
      case 3:
        v53 = 0x20000000;
        v10 = 4;
        goto LABEL_5;
    }
    v17 = 2 * ((*(_DWORD *)(v50 + 36) + 7) & 0xFFFFFFF8) + 280;
    v18 = (volatile signed __int32 *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                                       SockPrivateHeap,
                                       0,
                                       v17);
    v19 = v18;
    P = (PVOID)v18;
    if ( v18 )
    {
      memset_0((void *)v18, 0, v17);
      *v19 = 2;
      *((_QWORD *)v19 + 1) = -1;
      *((_DWORD *)v19 + 6) = -1;
      *((_DWORD *)v19 + 7) = v51;
      *((_DWORD *)v19 + 8) = v47;
      *((_DWORD *)v19 + 9) = v49;
      *((_OWORD *)v19 + 8) = *v60;
      *((_QWORD *)v19 + 20) = v57;
      *((_QWORD *)v19 + 19) = v50;
      *((_DWORD *)v19 + 36) = v54;
      v20 = ((unsigned __int64)v19 + 287) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_QWORD *)v19 + 21) = v20;
      *((_DWORD *)v19 + 10) = *(_DWORD *)(v50 + 36);
      *((_QWORD *)v19 + 22) = (v20 + *(int *)(v50 + 36) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_DWORD *)v19 + 11) = *(_DWORD *)(v50 + 36);
      v21 = 0;
      if ( *(int *)(v50 + 48) > 0 )
        v21 = 4;
      v22 = *((_BYTE *)v19 + 69) & 0xFB | v21;
      *((_DWORD *)v19 + 18) = v11;
      *((_DWORD *)v19 + 19) = a9;
      *((_DWORD *)v19 + 20) = a8;
      *((_DWORD *)v19 + 21) = a7;
      *((_DWORD *)v19 + 22) = v12;
      *((_DWORD *)v19 + 23) = 0;
      *((_QWORD *)v19 + 33) = 0;
      *((_QWORD *)v19 + 34) = 0;
      v23 = v22 & 0xF7;
      *((_BYTE *)v19 + 69) = v23;
      v24 = 0;
      v14 = 16;
      if ( !DestinationString.Length )
        v24 = 16;
      v25 = v24 & 0xDF | v23 & 0xCF;
      *((_BYTE *)v19 + 69) = v25;
      if ( (v11 & 0x100) != 0 )
      {
        if ( (v47 != 2 || v49 != 17) && (v47 != 1 || v49 != 6) || v51 != 2 && v51 != 23 )
        {
LABEL_105:
          TdiName = 10022;
          v43 = 0;
          goto LABEL_55;
        }
        *((_BYTE *)v19 + 69) = v25 | 0x20;
        *((_BYTE *)v19 + 68) |= 2u;
      }
      InitializeCriticalSection((LPCRITICAL_SECTION)(v19 + 56));
      v46 = 1;
      v26 = (unsigned __int16)(DestinationString.Length + 30);
      EaLength[0] = v26 + 27;
      if ( (unsigned int)(v26 + 27) > 0x60 )
      {
        EaBuffer = (_BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                              SockPrivateHeap,
                              0,
                              (unsigned int)(v26 + 27));
        if ( !EaBuffer )
        {
          TdiName = 10055;
          v43 = 0;
          goto LABEL_55;
        }
      }
      else
      {
        EaBuffer = v67;
      }
      *(_DWORD *)EaBuffer = 0;
      *((_WORD *)EaBuffer + 2) = 3840;
      strcpy(EaBuffer + 8, "AfdOpenPacketXX");
      *((_WORD *)EaBuffer + 3) = v26;
      *((_DWORD *)EaBuffer + 11) = DestinationString.Length;
      if ( (*((_BYTE *)v19 + 69) & 0x10) == 0 )
        memcpy_0(EaBuffer + 48, DestinationString.Buffer, DestinationString.Length + 2LL);
      *((_DWORD *)EaBuffer + 8) = v51;
      *((_DWORD *)EaBuffer + 9) = v47;
      *((_DWORD *)EaBuffer + 10) = v49;
      *((_DWORD *)EaBuffer + 6) = 0;
      if ( (*((_BYTE *)v19 + 69) & 0x20) != 0 )
        EaBuffer[27] = 16;
      if ( (v19[20] & 1) != 0 )
      {
        if ( (unsigned int)(v47 - 2) > 1 )
        {
          TdiName = 10022;
          v43 = 0;
          goto LABEL_55;
        }
        EaBuffer[24] |= 1u;
      }
      v27 = *((_DWORD *)v19 + 20);
      if ( (v27 & 8) != 0 )
      {
        if ( v47 == 1 )
        {
          if ( (v27 & 0x10) == 0 )
          {
            TdiName = 10022;
            v43 = 0;
            goto LABEL_55;
          }
        }
        else
        {
          if ( (unsigned int)(v47 - 2) > 3 )
          {
            TdiName = 10022;
            v43 = 0;
            goto LABEL_55;
          }
          EaBuffer[24] |= 0x10u;
        }
      }
      if ( v47 == 3 )
        EaBuffer[25] |= 1u;
      if ( (v11 & 0x1E) != 0 )
      {
        if ( (v19[20] & 0x400) == 0 )
        {
          TdiName = 10022;
          v43 = 0;
          goto LABEL_55;
        }
        EaBuffer[25] |= 0x10u;
        if ( (v11 & 2) != 0 )
        {
          if ( (v19[20] & 0x800) == 0 || (v11 & 4) != 0 )
            goto LABEL_105;
          EaBuffer[26] |= 1u;
        }
        if ( (v11 & 8) != 0 )
        {
          if ( (v19[20] & 0x1000) == 0 || (v11 & 0x10) != 0 )
            goto LABEL_105;
          EaBuffer[26] |= 0x10u;
        }
      }
      if ( (v10 & *(_DWORD *)(v50 + 52)) != 0
        || (*((_BYTE *)v19 + 69) & 0x10) != 0 && SockTLNPIListenerCount > 0 && v47 == 1
        || (unsigned __int8)IsAppContainer() )
      {
        EaBuffer[27] |= 1u;
      }
      *((_DWORD *)EaBuffer + 7) = v12;
      RtlInitUnicodeString(&v66, L"\\Device\\Afd\\Endpoint");
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      v28 = 66;
      if ( (v11 & 0x180) != 0 )
        v28 = 64;
      ObjectAttributes.Attributes = v28;
      ObjectAttributes.ObjectName = &v66;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v29 = (v11 & 0x101) == 0;
      CreateOptions = 32;
      if ( !v29 )
        CreateOptions = 0;
      v31 = -1072431104;
      if ( (a6 & 0x40) != 0 )
        v31 = -1055653888;
      v32 = 0;
      do
      {
        v33 = SocketGlobalLock;
        if ( SocketGlobalLock < 0 )
        {
          EnterCriticalSection(&CriticalSection);
          v32 = 1;
          v33 = SocketGlobalLock;
          v34 = ((SocketGlobalLock >> 31) & 0xFFFFFFFE) + SocketGlobalLock + 1;
        }
        else
        {
          v34 = SocketGlobalLock + 1;
        }
        v35 = _InterlockedCompareExchange(&SocketGlobalLock, v34, v33);
        if ( v32 )
        {
          LeaveCriticalSection(&CriticalSection);
          v32 = 0;
        }
      }
      while ( v35 != v33 );
      v36 = EaLength[0];
      v37 = NtCreateFile(
              &FileHandle,
              v31,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              3u,
              3u,
              CreateOptions,
              EaBuffer,
              EaLength[0]);
      v38 = (unsigned int)(v37 + 1073741810);
      if ( (unsigned int)v38 <= 0x2C )
      {
        v39 = 0x104000000001LL;
        if ( _bittest64(&v39, v38) )
        {
          if ( !(unsigned int)SockDemandStartAfd() )
            v37 = NtCreateFile(
                    &FileHandle,
                    v31,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    3u,
                    3u,
                    CreateOptions,
                    EaBuffer,
                    v36);
        }
      }
      if ( v37 < 0 )
      {
        SockReleaseRwLockShared();
        if ( !v48 && v37 == -2147483620 && IoStatusBlock.Information == -2147483620 )
        {
          v43 = 1;
          v48 = 1;
          ShipAssert(55298, (unsigned __int8)v49 | (((unsigned __int8)v47 | ((unsigned __int8)v51 << 8)) << 8));
        }
        else
        {
          v43 = 0;
        }
        TdiName = NtStatusToSocketError((unsigned int)v37);
        v11 = a6;
        v12 = a5;
      }
      else
      {
        *((_QWORD *)v19 + 1) = FileHandle;
        v12 = a5;
        if ( a5 )
        {
          *(_QWORD *)EaLength = 0;
          TdiName = SockGetInformation(v19, 10, 0, 0);
          v55 = TdiName;
          if ( TdiName )
          {
            SockReleaseRwLockShared();
            v43 = 0;
            v11 = a6;
            goto LABEL_55;
          }
          *((_DWORD *)v19 + 22) = EaLength[0];
          *((_DWORD *)v19 + 23) = EaLength[1];
        }
        if ( !SockSendBufferWindow )
        {
          SockGetInformation(v19, 7, 0, 0);
          SockGetInformation(v19, 6, 0, 0);
        }
        *((_DWORD *)v19 + 15) = SockReceiveBufferWindow;
        *((_DWORD *)v19 + 16) = SockSendBufferWindow;
        EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 56));
        inserted = (volatile signed __int32 *)WahInsertHandleContext(SockContextTable, v19);
        v16 = 1;
        do
        {
          v41 = SocketGlobalLock;
          v42 = -1;
          if ( SocketGlobalLock <= 0 )
            v42 = 1;
          v14 = (unsigned int)(SocketGlobalLock + v42);
        }
        while ( v41 != _InterlockedCompareExchange(&SocketGlobalLock, v14, SocketGlobalLock) );
        if ( (_DWORD)v14 == -1 )
          NtSetEvent(Handle, 0);
        if ( inserted != v19 )
        {
          if ( !inserted )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 56));
            TdiName = 10055;
            v43 = 0;
            v11 = a6;
            goto LABEL_55;
          }
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_q(1025, 18, WPP_0fa42c8809bf3117963d5a958f6beeb2_Traceguids, *((_QWORD *)v19 + 1));
          if ( _InterlockedExchangeAdd(inserted, 0xFFFFFFFF) == 1 )
            SockDestroySocket(inserted);
        }
        v43 = 0;
        v11 = a6;
        TdiName = v55;
      }
    }
    else
    {
      if ( (v54 & 0x80u) != 0 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(v50 + 104))(v57, -1, 0, 0, 128);
      TdiName = 10055;
      v43 = 0;
    }
LABEL_55:
    if ( v47 == 3 && DestinationString.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    if ( EaBuffer && EaBuffer != v67 )
      RtlFreeHeap(SockPrivateHeap, 0, EaBuffer);
    if ( !TdiName )
      break;
    if ( v19 )
    {
      if ( v43
        && ((v53 & v54) == 0
         || (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int))(v50 + 104))(
              v57,
              -1,
              0,
              0,
              v53)) )
      {
        *(_DWORD *)(v50 + 52) |= v52;
      }
      SockNotifyHelperDll(v19, 128, v16);
      v45 = (void *)*((_QWORD *)v19 + 1);
      if ( v45 != (void *)-1LL )
        NtClose(v45);
      if ( v46 )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v19 + 56));
      RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v19);
    }
    if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)(v50 + 16), 0xFFFFFFFF) == 1 )
      SockFreeHelperDll(v50, v14, v16);
    v29 = v43 == 0;
    v10 = v52;
    if ( v29 )
      return TdiName;
  }
  *v63 = v19;
  return TdiName;
}

```

## disassembly

```asm
0x18000a6b0  push    rbx
0x18000a6b2  push    rsi
0x18000a6b3  push    rdi
0x18000a6b4  push    r12
0x18000a6b6  push    r13
0x18000a6b8  push    r14
0x18000a6ba  push    r15
0x18000a6bc  sub     rsp, 1B0h
0x18000a6c3  mov     rax, cs:__security_cookie
0x18000a6ca  xor     rax, rsp
0x18000a6cd  mov     [rsp+1E8h+var_48], rax
0x18000a6d5  mov     rax, r9
0x18000a6d8  mov     [rsp+1E8h+var_120], rax
0x18000a6e0  mov     [rsp+1E8h+var_160], ecx
0x18000a6e7  mov     [rsp+1E8h+var_180], edx
0x18000a6eb  mov     [rsp+1E8h+var_170], r8d
0x18000a6f0  mov     [rsp+1E8h+var_110], rax
0x18000a6f8  mov     rax, [rsp+1E8h+arg_48]
0x18000a700  mov     [rsp+1E8h+var_108], rax
0x18000a708  xorps   xmm0, xmm0
0x18000a70b  movups  xmmword ptr [rsp+1E8h+DestinationString.Length], xmm0
0x18000a713  xor     eax, eax
0x18000a715  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.Length], xmm0
0x18000a71d  movups  xmmword ptr [rsp+1E8h+ObjectAttributes.ObjectName], xmm0
0x18000a725  movups  xmmword ptr [rsp+1E8h+ObjectAttributes+1Ch], xmm0
0x18000a72d  movups  xmmword ptr [rsp+1E8h+IoStatusBlock], xmm0
0x18000a735  xorps   xmm1, xmm1
0x18000a738  movups  xmmword ptr [rsp+1E8h+var_C0.Length], xmm1
0x18000a740  xor     r15d, r15d
0x18000a743  mov     [rsp+1E8h+var_140], r15
0x18000a74b  mov     [rsp+1E8h+var_150], r15d
0x18000a753  xor     edi, edi
0x18000a755  mov     [rsp+1E8h+var_188], dil
0x18000a75a  mov     [rsp+1E8h+var_178], al
0x18000a75e  mov     [rsp+1E8h+var_154], r15d
0x18000a766  mov     r14d, r15d
0x18000a769  mov     [rsp+1E8h+var_158], r15d
0x18000a771  mov     r12d, [rsp+1E8h+arg_28]
0x18000a779  mov     r13d, [rsp+1E8h+arg_20]
0x18000a781  mov     [rsp+1E8h+var_168], r15
0x18000a789  mov     rsi, r15
0x18000a78c  mov     qword ptr [rsp+1E8h+var_148], r15
0x18000a794  mov     [rsp+1E8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000a7a0  xor     al, al
0x18000a7a2  mov     [rsp+1E8h+var_187], al
0x18000a7a6  xor     edx, edx; SourceString
0x18000a7a8  lea     rcx, [rsp+1E8h+DestinationString]; DestinationString
0x18000a7b0  call    cs:__imp_RtlInitUnicodeString
0x18000a7b7  nop     dword ptr [rax+rax+00h]
0x18000a7bc  mov     eax, r12d
0x18000a7bf  and     eax, 0FFFFFE3Fh
0x18000a7c4  lea     rcx, [rsp+1E8h+var_150]
0x18000a7cc  mov     [rsp+1E8h+EaBuffer], rcx
0x18000a7d1  lea     rcx, [rsp+1E8h+var_168]
0x18000a7d9  mov     qword ptr [rsp+1E8h+CreateOptions], rcx
0x18000a7de  lea     rcx, [rsp+1E8h+var_140]
0x18000a7e6  mov     qword ptr [rsp+1E8h+CreateDisposition], rcx
0x18000a7eb  lea     rcx, [rsp+1E8h+DestinationString]
0x18000a7f3  mov     qword ptr [rsp+1E8h+ShareAccess], rcx
0x18000a7f8  mov     [rsp+1E8h+FileAttributes], eax
0x18000a7fc  mov     dword ptr [rsp+1E8h+AllocationSize], r13d
0x18000a801  mov     r9, [rsp+1E8h+var_120]
0x18000a809  lea     r8, [rsp+1E8h+var_170]
0x18000a80e  lea     rdx, [rsp+1E8h+var_180]
0x18000a813  lea     rcx, [rsp+1E8h+var_160]
0x18000a81b  call    SockGetTdiName
0x18000a820  mov     ebx, eax
0x18000a822  mov     [rsp+1E8h+var_14C], eax
0x18000a829  test    eax, eax
0x18000a82b  jnz     loc_18000ADD2
0x18000a831  mov     eax, [rsp+1E8h+var_180]
0x18000a835  cmp     eax, 1
0x18000a838  jnz     loc_18000ADB6
0x18000a83e  mov     [rsp+1E8h+var_154], 80000000h
0x18000a849  mov     r14d, eax
0x18000a84c  mov     [rsp+1E8h+var_158], r14d
0x18000a854  mov     rax, [rsp+1E8h+var_168]
0x18000a85c  mov     eax, [rax+24h]
0x18000a85f  add     eax, 7
0x18000a862  and     eax, 0FFFFFFF8h
0x18000a865  lea     eax, ds:118h[rax*2]
0x18000a86c  mov     ebx, eax
0x18000a86e  mov     r8d, eax
0x18000a871  xor     edx, edx
0x18000a873  mov     rcx, cs:SockPrivateHeap
0x18000a87a  mov     rax, cs:SockAllocateHeapRoutine
0x18000a881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a886  mov     rdi, rax
0x18000a889  mov     [rsp+1E8h+P], rax
0x18000a891  test    rax, rax
0x18000a894  jz      loc_18000AD98
0x18000a89a  mov     r8d, ebx; Size
0x18000a89d  xor     edx, edx; Val
0x18000a89f  mov     rcx, rax; void *
0x18000a8a2  call    memset_0
0x18000a8a7  mov     dword ptr [rdi], 2
0x18000a8ad  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18000a8b5  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x18000a8bc  mov     eax, [rsp+1E8h+var_160]
0x18000a8c3  mov     [rdi+1Ch], eax
0x18000a8c6  mov     eax, [rsp+1E8h+var_180]
0x18000a8ca  mov     [rdi+20h], eax
0x18000a8cd  mov     eax, [rsp+1E8h+var_170]
0x18000a8d1  mov     [rdi+24h], eax
0x18000a8d4  mov     rax, [rsp+1E8h+var_120]
0x18000a8dc  movups  xmm0, xmmword ptr [rax]
0x18000a8df  movups  xmmword ptr [rdi+80h], xmm0
0x18000a8e6  mov     rax, [rsp+1E8h+var_140]
0x18000a8ee  mov     [rdi+0A0h], rax
0x18000a8f5  mov     rax, [rsp+1E8h+var_168]
0x18000a8fd  mov     [rdi+98h], rax
0x18000a904  mov     eax, [rsp+1E8h+var_150]
0x18000a90b  mov     [rdi+90h], eax
0x18000a911  lea     rdx, [rdi+11Fh]
0x18000a918  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000a91c  mov     [rdi+0A8h], rdx
0x18000a923  mov     rax, [rsp+1E8h+var_168]
0x18000a92b  mov     ecx, [rax+24h]
0x18000a92e  mov     [rdi+28h], ecx
0x18000a931  mov     rax, [rsp+1E8h+var_168]
0x18000a939  movsxd  rax, dword ptr [rax+24h]
0x18000a93d  add     rax, 7
0x18000a941  add     rax, rdx
0x18000a944  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000a948  mov     [rdi+0B0h], rax
0x18000a94f  mov     rax, [rsp+1E8h+var_168]
0x18000a957  mov     ecx, [rax+24h]
0x18000a95a  mov     [rdi+2Ch], ecx
0x18000a95d  mov     ecx, r15d
0x18000a960  mov     rax, [rsp+1E8h+var_168]
0x18000a968  cmp     dword ptr [rax+30h], 0
0x18000a96c  mov     eax, 4
0x18000a971  cmovg   ecx, eax
0x18000a974  movzx   eax, byte ptr [rdi+45h]
0x18000a978  and     al, 0FBh
0x18000a97a  or      cl, al
0x18000a97c  mov     [rdi+48h], r12d
0x18000a980  mov     eax, [rsp+1E8h+arg_40]
0x18000a987  mov     [rdi+4Ch], eax
0x18000a98a  mov     eax, [rsp+1E8h+arg_38]
0x18000a991  mov     [rdi+50h], eax
0x18000a994  mov     eax, [rsp+1E8h+arg_30]
0x18000a99b  mov     [rdi+54h], eax
0x18000a99e  mov     [rdi+58h], r13d
0x18000a9a2  mov     [rdi+5Ch], r15d
0x18000a9a6  mov     [rdi+108h], r15
0x18000a9ad  mov     [rdi+110h], r15
0x18000a9b4  and     cl, 0F7h
0x18000a9b7  mov     [rdi+45h], cl
0x18000a9ba  mov     eax, r15d
0x18000a9bd  cmp     [rsp+1E8h+DestinationString.Length], 0
0x18000a9c6  mov     edx, 10h
0x18000a9cb  cmovz   eax, edx
0x18000a9ce  and     cl, 0EFh
0x18000a9d1  or      cl, al
0x18000a9d3  and     cl, 0DFh
0x18000a9d6  mov     [rdi+45h], cl
0x18000a9d9  bt      r12d, 8
0x18000a9de  jb      loc_18000B10C
0x18000a9e4  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x18000a9eb  call    cs:__imp_InitializeCriticalSection
0x18000a9f2  nop     dword ptr [rax+rax+00h]
0x18000a9f7  jmp     short loc_18000AA45
0x18000a9f9  mov     ecx, eax
0x18000a9fb  call    NtStatusToSocketError
0x18000aa00  mov     ebx, eax
0x18000aa02  movzx   r14d, [rsp+1E8h+var_188]
0x18000aa08  xor     r15d, r15d
0x18000aa0b  mov     rsi, qword ptr [rsp+1E8h+var_148]
0x18000aa13  mov     [rsp+1E8h+var_187], r14b
0x18000aa18  mov     rdi, [rsp+1E8h+P]
0x18000aa20  mov     rax, [rsp+1E8h+var_110]
0x18000aa28  mov     [rsp+1E8h+var_120], rax
0x18000aa30  mov     r12d, [rsp+1E8h+arg_28]
0x18000aa38  mov     r13d, [rsp+1E8h+arg_20]
0x18000aa40  jmp     loc_18000AD10
0x18000aa45  mov     [rsp+1E8h+var_187], 1
0x18000aa4a  movzx   eax, [rsp+1E8h+DestinationString.Length]
0x18000aa52  add     ax, 1Eh
0x18000aa56  movzx   ebx, ax
0x18000aa59  lea     eax, [rbx+1Bh]
0x18000aa5c  mov     [rsp+1E8h+var_148], eax
0x18000aa63  cmp     eax, 60h ; '`'
0x18000aa66  ja      loc_18000AF26
0x18000aa6c  lea     rsi, [rsp+1E8h+var_A8]
0x18000aa74  mov     [rsi], r15d
0x18000aa77  mov     word ptr [rsi+4], 0F00h
0x18000aa7d  movups  xmm0, xmmword ptr cs:aAfdopenpacketx; "AfdOpenPacketXX"
0x18000aa84  movups  xmmword ptr [rsi+8], xmm0
0x18000aa88  mov     [rsi+6], bx
0x18000aa8c  movzx   eax, [rsp+1E8h+DestinationString.Length]
0x18000aa94  mov     [rsi+2Ch], eax
0x18000aa97  test    byte ptr [rdi+45h], 10h
0x18000aa9b  jz      loc_18000AE36
0x18000aaa1  mov     eax, [rsp+1E8h+var_160]
0x18000aaa8  mov     [rsi+20h], eax
0x18000aaab  mov     eax, [rsp+1E8h+var_180]
0x18000aaaf  mov     [rsi+24h], eax
0x18000aab2  mov     eax, [rsp+1E8h+var_170]
0x18000aab6  mov     [rsi+28h], eax
0x18000aab9  mov     [rsi+18h], r15d
0x18000aabd  test    byte ptr [rdi+45h], 20h
0x18000aac1  jnz     loc_18000B158
0x18000aac7  test    byte ptr [rdi+50h], 1
0x18000aacb  jnz     loc_18000ADDE
0x18000aad1  mov     eax, [rdi+50h]
0x18000aad4  test    al, 8
0x18000aad6  jnz     loc_18000ADF7
0x18000aadc  cmp     [rsp+1E8h+var_180], 3
0x18000aae1  jz      loc_18000AF1D
0x18000aae7  test    r12b, 1Eh
0x18000aaeb  jnz     loc_18000AED6
0x18000aaf1  mov     rax, [rsp+1E8h+var_168]
0x18000aaf9  test    [rax+34h], r14d
0x18000aafd  jnz     short loc_18000AB1E
0x18000aaff  test    byte ptr [rdi+45h], 10h
0x18000ab03  jz      short loc_18000AB15
0x18000ab05  cmp     cs:SockTLNPIListenerCount, 0
0x18000ab0c  jle     short loc_18000AB15
0x18000ab0e  cmp     [rsp+1E8h+var_180], 1
0x18000ab13  jz      short loc_18000AB1E
0x18000ab15  call    IsAppContainer
0x18000ab1a  test    al, al
0x18000ab1c  jz      short loc_18000AB22
0x18000ab1e  or      byte ptr [rsi+1Bh], 1
0x18000ab22  mov     [rsi+1Ch], r13d
0x18000ab26  lea     rdx, aDeviceAfdEndpo; "\\Device\\Afd\\Endpoint"
0x18000ab2d  lea     rcx, [rsp+1E8h+var_C0]; DestinationString
0x18000ab35  call    cs:__imp_RtlInitUnicodeString
0x18000ab3c  nop     dword ptr [rax+rax+00h]
0x18000ab41  mov     [rsp+1E8h+ObjectAttributes.Length], 30h ; '0'
0x18000ab4c  mov     [rsp+1E8h+ObjectAttributes.RootDirectory], r15
0x18000ab54  test    r12d, 180h
0x18000ab5b  mov     eax, 42h ; 'B'
0x18000ab60  mov     ecx, 40h ; '@'
0x18000ab65  cmovnz  eax, ecx
0x18000ab68  mov     [rsp+1E8h+ObjectAttributes.Attributes], eax
0x18000ab6f  lea     rax, [rsp+1E8h+var_C0]
0x18000ab77  mov     [rsp+1E8h+ObjectAttributes.ObjectName], rax
0x18000ab7f  xorps   xmm0, xmm0
0x18000ab82  movdqu  xmmword ptr [rsp+1E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ab8b  test    r12d, 101h
0x18000ab92  mov     r12d, 20h ; ' '
0x18000ab98  cmovnz  r12d, r15d
0x18000ab9c  mov     r13d, 0C0140000h
0x18000aba2  test    byte ptr [rsp+1E8h+arg_28], cl
0x18000aba9  jnz     loc_18000B1CB
0x18000abaf  mov     edx, r15d
0x18000abb2  mov     ebx, cs:SocketGlobalLock
0x18000abb8  test    ebx, ebx
0x18000abba  js      loc_18000AEA6
0x18000abc0  lea     ecx, [rbx+1]
0x18000abc3  mov     eax, ebx
0x18000abc5  lock cmpxchg cs:SocketGlobalLock, ecx
0x18000abcd  mov     r14d, eax
0x18000abd0  test    edx, edx
0x18000abd2  jnz     loc_18000AE1B
0x18000abd8  cmp     r14d, ebx
0x18000abdb  jnz     short loc_18000ABB2
0x18000abdd  mov     r14d, [rsp+1E8h+var_148]
0x18000abe5  mov     [rsp+1E8h+EaLength], r14d; EaLength
0x18000abea  mov     [rsp+1E8h+EaBuffer], rsi; EaBuffer
0x18000abef  mov     [rsp+1E8h+CreateOptions], r12d; CreateOptions
0x18000abf4  mov     [rsp+1E8h+CreateDisposition], 3; CreateDisposition
0x18000abfc  mov     [rsp+1E8h+ShareAccess], 3; ShareAccess
0x18000ac04  mov     [rsp+1E8h+FileAttributes], r15d; FileAttributes
0x18000ac09  mov     [rsp+1E8h+AllocationSize], r15; AllocationSize
0x18000ac0e  lea     r9, [rsp+1E8h+IoStatusBlock]; IoStatusBlock
0x18000ac16  lea     r8, [rsp+1E8h+ObjectAttributes]; ObjectAttributes
0x18000ac1e  mov     edx, r13d; DesiredAccess
0x18000ac21  lea     rcx, [rsp+1E8h+FileHandle]; FileHandle
0x18000ac29  call    cs:__imp_NtCreateFile
0x18000ac30  nop     dword ptr [rax+rax+00h]
0x18000ac35  mov     ebx, eax
0x18000ac37  lea     ecx, [rax+3FFFFFF2h]
0x18000ac3d  cmp     ecx, 2Ch ; ','
0x18000ac40  ja      short loc_18000AC56
0x18000ac42  mov     rax, 104000000001h
0x18000ac4c  bt      rax, rcx
0x18000ac50  jb      loc_18000B03E
0x18000ac56  test    ebx, ebx
0x18000ac58  js      loc_18000B1D6
0x18000ac5e  mov     rax, [rsp+1E8h+FileHandle]
0x18000ac66  mov     [rdi+8], rax
0x18000ac6a  mov     r13d, [rsp+1E8h+arg_20]
0x18000ac72  test    r13d, r13d
0x18000ac75  jnz     loc_18000B253
0x18000ac7b  cmp     cs:SockSendBufferWindow, 0
0x18000ac82  jz      loc_18000AE59
0x18000ac88  mov     eax, cs:SockReceiveBufferWindow
0x18000ac8e  mov     [rdi+3Ch], eax
0x18000ac91  mov     eax, cs:SockSendBufferWindow
0x18000ac97  mov     [rdi+40h], eax
0x18000ac9a  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x18000aca1  call    cs:__imp_EnterCriticalSection
0x18000aca8  nop     dword ptr [rax+rax+00h]
0x18000acad  mov     rdx, rdi
0x18000acb0  mov     rcx, cs:SockContextTable
0x18000acb7  call    cs:__imp_WahInsertHandleContext
0x18000acbe  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
