# SockSanImportSocket

- ea: `0x18004d924`
- end: `0x18004e4b4`
- name: `SockSanImportSocket`
- size: `2960`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d000`
- `0x18003b114`
- `0x1800411a8`
- `0x180047cb0`
- `0x18004d844`

## callees

- `0x1800052a0`
- `0x180006d00`
- `0x180008250`
- `0x1800222f0`
- `0x180022bd2`
- `0x180023f14`
- `0x180038104`
- `0x180038118`
- `0x180038ea4`
- `0x18003ae8c`
- `0x18003aefc`
- `0x180041d50`
- `0x180042128`
- `0x180042970`
- `0x180042b50`
- `0x180049768`
- `0x1800497d4`
- `0x18004cf28`
- `0x18004d924`
- `0x1800507fc`
- `0x18005284c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004d985`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004d985`
- `ntdll!RtlFreeHeap` at `0x18004dcab`
- `ntdll!RtlFreeHeap` at `0x18004e0ff`
- `ntdll!RtlFreeHeap` at `0x18004e225`
- `ntdll!RtlFreeHeap` at `0x18004e484`
- `ntdll!RtlFreeHeap` at `0x18004e49c`
- `ntdll!RtlFreeHeap` at `0x18004dcab`
- `ntdll!RtlFreeHeap` at `0x18004e0ff`
- `ntdll!RtlFreeHeap` at `0x18004e225`
- `ntdll!RtlFreeHeap` at `0x18004e484`
- `ntdll!RtlFreeHeap` at `0x18004e49c`
- `ntdll!NtDeviceIoControlFile` at `0x18004dbd1`
- `ntdll!NtDeviceIoControlFile` at `0x18004dbd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004e400`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004e400`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e3f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004db32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e3f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dcd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dfb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e13b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e38a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004db11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dcd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dfb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e13b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e38a`

## pseudocode

```c
__int64 __fastcall SockSanImportSocket(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rbx
  __int64 SwitchSocket; // rax
  unsigned int v5; // esi
  char v6; // r13
  __int64 Provider; // r15
  char v8; // r14
  int v9; // r9d
  unsigned int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // r8d
  unsigned __int64 v13; // r10
  __int64 v14; // rax
  _DWORD *v15; // r12
  __int64 v16; // rax
  int v17; // ecx
  unsigned int v18; // edx
  ULONG OutputBufferLength; // ecx
  __int64 v20; // rdx
  __int64 v21; // rcx
  NTSTATUS Status; // esi
  volatile signed __int32 *v23; // rax
  __int64 v24; // r14
  char v25; // cl
  char v26; // al
  char v27; // cl
  _OWORD *v28; // rcx
  __int64 v29; // r13
  __int64 v30; // r8
  __int64 *v31; // rax
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  int v52; // eax
  _OWORD *v53; // rcx
  _OWORD *v54; // rax
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  int v68; // eax
  __int64 v69; // rax
  unsigned int v70; // r13d
  __int64 v71; // r14
  unsigned __int64 v72; // rax
  _QWORD *v73; // rcx
  char v74; // al
  unsigned int v75; // eax
  unsigned int v76; // esi
  __int64 *v77; // rax
  __int64 v78; // rdx
  HANDLE v79; // rcx
  __int64 v80; // rdx
  _QWORD *v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // r8
  _QWORD *v84; // rdx
  volatile signed __int32 *v85; // rcx
  __int64 IoControlCode; // [rsp+28h] [rbp-D8h]
  char v87; // [rsp+50h] [rbp-B0h]
  unsigned int v88; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v89; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int Information; // [rsp+68h] [rbp-98h]
  HANDLE *Value; // [rsp+70h] [rbp-90h]
  unsigned __int64 v92; // [rsp+78h] [rbp-88h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  _QWORD InputBuffer[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v95[640]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v96[112]; // [rsp+330h] [rbp+230h] BYREF
  int v97; // [rsp+3A0h] [rbp+2A0h]

  v88 = 0;
  memset_0(v96, 0, 0x274u);
  v89 = 0;
  IoStatusBlock = 0;
  Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
  if ( SBYTE2(xmmword_180063D60) < 0 )
    WPP_SF_q(1047, 59, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, *(_QWORD *)(a1 + 8));
  result = InitFlowAndConnectThreads();
  v88 = result;
  if ( !(_DWORD)result )
  {
    v3 = *(_QWORD *)(a1 + 264);
    if ( v3 )
    {
      Provider = *(_QWORD *)(v3 + 16);
      v6 = 0;
    }
    else
    {
      SwitchSocket = SockSanCreateSwitchSocket();
      v3 = SwitchSocket;
      if ( !SwitchSocket )
        return 8;
      if ( (*(_BYTE *)(a1 + 72) & 1) != 0 )
        *(_DWORD *)(SwitchSocket + 32) = 1;
      v6 = 1;
      Provider = SockSanFindProvider(*(_QWORD *)(a1 + 176), 0);
      _InterlockedAdd((volatile signed __int32 *)a1, 1u);
      _InterlockedAdd((volatile signed __int32 *)a1, 1u);
      *(_QWORD *)v3 = a1;
      *(_QWORD *)(v3 + 8) = a1;
      *(_QWORD *)(v3 + 16) = Provider;
    }
    v8 = 0;
    if ( !Provider )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 60, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, **(unsigned int **)(a1 + 176));
      v5 = 10091;
      goto LABEL_93;
    }
    v9 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 372LL);
    v10 = *(_DWORD *)(a1 + 60);
    v11 = v10 + 9216;
    v12 = v10 + 9216;
    if ( v10 + 9216 <= 9216 * v9 )
      v12 = 9216 * v9;
    if ( v11 < v10
      || v11 < 0x2400
      || (v13 = v12 + 104 * (v9 + 1), v92 = v13, v13 < 104 * (unsigned __int64)(unsigned int)(v9 + 1))
      || v12 + 104 * (v9 + 1) < v12
      || (v14 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                  SockPrivateHeap,
                  0,
                  (unsigned int)v13),
          (v15 = (_DWORD *)v14) == 0) )
    {
      v5 = 10055;
LABEL_93:
      if ( v3 )
      {
        *(_DWORD *)(v3 + 176) = 0;
        if ( !v8 && *(_QWORD *)(v3 + 104) != -1 )
          v88 = AbortSanConnection(v3);
      }
      if ( Provider )
      {
        if ( !v6 )
          return v5;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Provider + 16), 0xFFFFFFFF) == 1 )
          SockSanFreeProvider((PVOID)Provider);
      }
      else if ( !v6 )
      {
        return v5;
      }
      EnterCriticalSection(&SockSanListCritSec);
      v80 = *(_QWORD *)(v3 + 88);
      if ( *(_QWORD *)(v80 + 8) == v3 + 88 )
      {
        v81 = *(_QWORD **)(v3 + 96);
        if ( *v81 == v3 + 88 )
        {
          --NumOpenSanSocks;
          *v81 = v80;
          *(_QWORD *)(v80 + 8) = v81;
          v82 = *(_QWORD **)(v3 + 216);
          v83 = *v82;
          if ( *(_QWORD **)(*v82 + 8LL) == v82 )
          {
            v84 = (_QWORD *)v82[1];
            if ( (_QWORD *)*v84 == v82 )
            {
              *v84 = v83;
              *(_QWORD *)(v83 + 8) = v84;
              LeaveCriticalSection(&SockSanListCritSec);
              DeleteCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
              if ( *(_QWORD *)v3 && _InterlockedExchangeAdd(*(volatile signed __int32 **)v3, 0xFFFFFFFF) == 1 )
                SockDestroySocket(*(_QWORD *)v3);
              v85 = *(volatile signed __int32 **)(v3 + 8);
              if ( v85 )
              {
                if ( v8 && _InterlockedExchangeAdd(v85, 0xFFFFFFFF) == 1 )
                  SockDestroySocket(*(_QWORD *)(v3 + 8));
                if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(v3 + 8), 0xFFFFFFFF) == 1 )
                  SockDestroySocket(*(_QWORD *)(v3 + 8));
              }
              if ( !v8 )
                *(_QWORD *)(a1 + 264) = 0;
              RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(v3 + 216));
              RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v3);
              return v5;
            }
          }
        }
      }
LABEL_118:
      __fastfail(3u);
    }
    *(_QWORD *)(v14 + 96) = v14 + 104;
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    *(_DWORD *)(v3 + 176) = 4;
    *(_BYTE *)(v3 + 208) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    _InterlockedIncrement(*(volatile signed __int32 **)(v3 + 8));
    v16 = *(_QWORD *)(v3 + 16);
    InputBuffer[3] = 16;
    v17 = *(_DWORD *)(v16 + 372);
    InputBuffer[0] = *(_QWORD *)(a1 + 8);
    v18 = 9216 * v17;
    OutputBufferLength = *(_DWORD *)(a1 + 60) + 9216;
    InputBuffer[1] = *(_QWORD *)(v3 + 216) + 24LL;
    if ( OutputBufferLength <= v18 )
      OutputBufferLength = v18;
    InputBuffer[2] = &v89;
    Status = NtDeviceIoControlFile(
               SockSanHelperHandle,
               Value[2],
               0,
               0,
               &IoStatusBlock,
               0x120FBu,
               InputBuffer,
               0x20u,
               *((PVOID *)v15 + 12),
               OutputBufferLength);
    if ( Status == 259 )
    {
      SockWaitForSingleObject(Value[2]);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 61, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, (unsigned int)Status);
      v23 = *(volatile signed __int32 **)(v3 + 8);
      *(_DWORD *)(v3 + 176) = 2;
      if ( _InterlockedExchangeAdd(v23, 0xFFFFFFFF) == 1 )
        SockDestroySocket(*(_QWORD *)(v3 + 8));
      v5 = NtStatusToSocketError((unsigned int)Status);
      goto LABEL_38;
    }
    Information = IoStatusBlock.Information;
    if ( SBYTE2(xmmword_180063D60) < 0 )
      WPP_SF_dDd(v21, v20);
    if ( (BYTE10(v89) & 2) != 0 )
    {
      v5 = 0;
      *(_QWORD *)(a1 + 264) = v89;
      v8 = 1;
LABEL_38:
      RtlFreeHeap(SockPrivateHeap, 0, v15);
      goto LABEL_93;
    }
    v87 = 0;
    if ( (BYTE10(v89) & 1) != 0 )
      *(_DWORD *)(v3 + 168) = 2;
    _InterlockedIncrement((volatile signed __int32 *)(Provider + 16));
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    v24 = 4;
    *(_DWORD *)(v3 + 804) = (BYTE10(v89) >> 5) & 1;
    *(_DWORD *)(v3 + 136) = (BYTE10(v89) >> 4) & 1;
    v25 = *(_BYTE *)(v3 + 800) ^ (*(_BYTE *)(v3 + 800) ^ (BYTE10(v89) >> 1)) & 2;
    *(_BYTE *)(v3 + 800) = v25;
    *(_BYTE *)(v3 + 800) = v25 ^ (v25 ^ (BYTE10(v89) >> 1)) & 4;
    v26 = *(_BYTE *)(v3 + 801);
    v27 = v26 ^ (BYTE10(v89) >> 4);
    *(_DWORD *)(v3 + 832) = 0;
    *(_BYTE *)(v3 + 801) = v26 ^ v27 & 4;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
    if ( (BYTE10(v89) & 0x10) != 0 || (BYTE10(v89) & 8) != 0 )
    {
      if ( *(_QWORD *)(v3 + 104) != -1 )
        goto LABEL_67;
    }
    else
    {
      v28 = v95;
      v29 = *(_QWORD *)(v3 + 104);
      v30 = 4;
      if ( *(_DWORD *)(a1 + 28) == 2 )
      {
        v31 = SockTcpProviderInfo;
        do
        {
          v32 = *((_OWORD *)v31 + 1);
          *v28 = *(_OWORD *)v31;
          v33 = *((_OWORD *)v31 + 2);
          v28[1] = v32;
          v34 = *((_OWORD *)v31 + 3);
          v28[2] = v33;
          v35 = *((_OWORD *)v31 + 4);
          v28[3] = v34;
          v36 = *((_OWORD *)v31 + 5);
          v28[4] = v35;
          v37 = *((_OWORD *)v31 + 6);
          v28[5] = v36;
          v38 = *((_OWORD *)v31 + 7);
          v31 += 16;
          v28[6] = v37;
          v28[7] = v38;
          v28 += 8;
          --v30;
        }
        while ( v30 );
      }
      else
      {
        v31 = SockTcp6ProviderInfo;
        do
        {
          v39 = *((_OWORD *)v31 + 1);
          *v28 = *(_OWORD *)v31;
          v40 = *((_OWORD *)v31 + 2);
          v28[1] = v39;
          v41 = *((_OWORD *)v31 + 3);
          v28[2] = v40;
          v42 = *((_OWORD *)v31 + 4);
          v28[3] = v41;
          v43 = *((_OWORD *)v31 + 5);
          v28[4] = v42;
          v44 = *((_OWORD *)v31 + 6);
          v28[5] = v43;
          v45 = *((_OWORD *)v31 + 7);
          v31 += 16;
          v28[6] = v44;
          v28[7] = v45;
          v28 += 8;
          --v30;
        }
        while ( v30 );
      }
      v46 = *((_OWORD *)v31 + 1);
      *v28 = *(_OWORD *)v31;
      v47 = *((_OWORD *)v31 + 2);
      v28[1] = v46;
      v48 = *((_OWORD *)v31 + 3);
      v28[2] = v47;
      v49 = *((_OWORD *)v31 + 4);
      v28[3] = v48;
      v50 = *((_OWORD *)v31 + 5);
      v28[4] = v49;
      v51 = *((_OWORD *)v31 + 6);
      v52 = *((_DWORD *)v31 + 28);
      v28[5] = v50;
      v28[6] = v51;
      *((_DWORD *)v28 + 28) = v52;
      v53 = v96;
      v54 = v95;
      do
      {
        v55 = v54[1];
        *v53 = *v54;
        v56 = v54[2];
        v53[1] = v55;
        v57 = v54[3];
        v53[2] = v56;
        v58 = v54[4];
        v53[3] = v57;
        v59 = v54[5];
        v53[4] = v58;
        v60 = v54[6];
        v53[5] = v59;
        v61 = v54[7];
        v54 += 8;
        v53[6] = v60;
        v53[7] = v61;
        v53 += 8;
        --v24;
      }
      while ( v24 );
      v62 = v54[1];
      *v53 = *v54;
      v63 = v54[2];
      v53[1] = v62;
      v64 = v54[3];
      v53[2] = v63;
      v65 = v54[4];
      v53[3] = v64;
      v66 = v54[5];
      v53[4] = v65;
      v67 = v54[6];
      v68 = *((_DWORD *)v54 + 28);
      v53[5] = v66;
      v53[6] = v67;
      *((_DWORD *)v53 + 28) = v68;
      v97 = v89;
      Value[3] = (HANDLE)v3;
      LODWORD(IoControlCode) = *(_DWORD *)(a1 + 72) | 1;
      v69 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *, _DWORD))(Provider + 288))(
              *(unsigned int *)(a1 + 28),
              *(unsigned int *)(a1 + 32),
              *(unsigned int *)(a1 + 36),
              v96,
              *(_DWORD *)(a1 + 88));
      *(_QWORD *)(v3 + 104) = v69;
      if ( v69 == -1 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_d(1025, 63, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v88);
        v87 = 1;
        BYTE10(v89) |= 0x10u;
        *(_DWORD *)(v3 + 136) = 1;
        Information = 0;
      }
      if ( *(_QWORD *)(v3 + 104) != v29 && v29 != -1 )
      {
        if ( *(_QWORD *)(v3 + 104) != -1 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
          *(_BYTE *)(v3 + 802) |= 1u;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
        }
        if ( SBYTE2(xmmword_180063D60) < 0 )
          WPP_SF_qq(
            1047,
            64,
            WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids,
            v29,
            *(_QWORD *)(v3 + 104),
            IoControlCode,
            &v88);
        (*(void (__fastcall **)(__int64, unsigned int *))(Provider + 112))(v29, &v88);
LABEL_67:
        v70 = Information;
        v71 = v3 + 336;
        *(_QWORD *)(v3 + 344) = v3 + 336;
        *(_QWORD *)(v3 + 336) = v3 + 336;
        if ( v70 )
        {
          v72 = v92;
          *v15 = 286331153;
          *((_QWORD *)v15 + 7) = v3;
          *((_BYTE *)v15 + 87) = 0;
          v15[20] = 0;
          v15[22] = v70;
          v15[6] = 1;
          *(_QWORD *)(v3 + 712) = (char *)v15 + v72;
          *(_QWORD *)(v3 + 704) = v15;
          *(_QWORD *)(v3 + 728) = v15;
          *(_QWORD *)(v3 + 720) = *((_QWORD *)v15 + 12) + v70;
          *(_BYTE *)(v3 + 744) = 0;
          *(_QWORD *)(v3 + 736) = v15;
          *(_DWORD *)(v3 + 120) = v70;
          v73 = *(_QWORD **)(v3 + 344);
          if ( *v73 != v71 )
            goto LABEL_118;
          *((_QWORD *)v15 + 5) = v71;
          *((_QWORD *)v15 + 6) = v73;
          *v73 = v15 + 10;
          *(_QWORD *)(v3 + 344) = v15 + 10;
        }
        else
        {
          RtlFreeHeap(SockPrivateHeap, 0, v15);
        }
        v74 = BYTE10(v89);
        *(_QWORD *)(a1 + 264) = v3;
        if ( (v74 & 0x10) != 0 || (v74 & 8) != 0 )
        {
          v76 = 0;
          *(_QWORD *)(v3 + 312) = v3 + 304;
          *(_QWORD *)(v3 + 304) = v3 + 304;
          *(_QWORD *)(v3 + 328) = v3 + 320;
          *(_QWORD *)(v3 + 320) = v3 + 320;
          *(_QWORD *)(v3 + 360) = v3 + 352;
          *(_QWORD *)(v3 + 352) = v3 + 352;
          *(_QWORD *)(v3 + 376) = v3 + 368;
          *(_QWORD *)(v3 + 368) = v3 + 368;
          *(_QWORD *)(v3 + 392) = v3 + 384;
          *(_QWORD *)(v3 + 384) = v3 + 384;
          *(_QWORD *)(v3 + 408) = v3 + 400;
          *(_QWORD *)(v3 + 400) = v3 + 400;
          *(_QWORD *)(v3 + 424) = v3 + 416;
          *(_QWORD *)(v3 + 416) = v3 + 416;
          *(_DWORD *)(v3 + 448) = 0;
        }
        else
        {
          SockSanCleanupFlowControl(v3);
          SockSanDeallocateFCMemory(v3);
          EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
          *(_BYTE *)(v3 + 800) &= ~0x80u;
          *(_QWORD *)(v3 + 432) = 0;
          *(_QWORD *)(v3 + 444) = 0;
          *(_DWORD *)(v3 + 440) = 0;
          *(_DWORD *)(v3 + 912) = 0;
          if ( !v70 )
            *(_BYTE *)(v3 + 744) = 1;
          *(_QWORD *)(v3 + 452) = 0;
          *(_QWORD *)(v3 + 576) = 0;
          *(_DWORD *)(v3 + 584) = 0;
          *(_QWORD *)(v3 + 608) = 0;
          *(_DWORD *)(v3 + 616) = 0;
          *(_BYTE *)(*(_QWORD *)v3 + 69LL) |= 8u;
          *(_WORD *)(v3 + 840) = WORD4(v89);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
          v75 = InitializeFlowControl((PVOID)v3);
          v76 = v75;
          if ( v75 )
          {
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_d(1025, 68, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v75);
            if ( v70 )
            {
              v77 = *(__int64 **)v71;
              if ( *(_QWORD *)(*(_QWORD *)v71 + 8LL) != v71 )
                goto LABEL_118;
              v78 = *v77;
              if ( *(__int64 **)(*v77 + 8) != v77 )
                goto LABEL_118;
              v79 = SockPrivateHeap;
              *(_QWORD *)v71 = v78;
              *(_QWORD *)(v78 + 8) = v71;
              RtlFreeHeap(v79, 0, v15);
              *(_DWORD *)(v3 + 120) = 0;
            }
            SockSanCloseSocket(a1);
            *(_DWORD *)(v3 + 176) = 0;
            goto LABEL_85;
          }
        }
        *(_DWORD *)(v3 + 152) = 1;
        *(_DWORD *)(v3 + 176) = 0;
        if ( !v87 )
        {
LABEL_87:
          if ( SBYTE2(xmmword_180063D60) < 0 )
            WPP_SF_d(1047, 69, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, v76);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Provider + 16), 0xFFFFFFFF) == 1 )
            SockSanFreeProvider((PVOID)Provider);
          return 0;
        }
LABEL_85:
        if ( *(_BYTE *)(v3 + 208) )
          CheckForSocketDuplicationProtocol((PVOID)v3);
        goto LABEL_87;
      }
      if ( *(_QWORD *)(v3 + 104) != -1 )
        goto LABEL_67;
      if ( SBYTE2(xmmword_180063D60) < 0 )
        WPP_SF_(1047, 65, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
    }
    *(_QWORD *)(v3 + 112) = 4079088417LL;
    goto LABEL_67;
  }
  return result;
}

```

## disassembly

```asm
0x18004d924  push    rbp
0x18004d926  push    rbx
0x18004d927  push    rsi
0x18004d928  push    rdi
0x18004d929  push    r12
0x18004d92b  push    r13
0x18004d92d  push    r14
0x18004d92f  push    r15
0x18004d931  lea     rbp, [rsp-4C8h]
0x18004d939  sub     rsp, 5C8h
0x18004d940  mov     rax, cs:__security_cookie
0x18004d947  xor     rax, rsp
0x18004d94a  mov     [rbp+500h+var_50], rax
0x18004d951  mov     rdi, rcx
0x18004d954  mov     [rsp+600h+var_5AC], 0
0x18004d95c  lea     rcx, [rbp+500h+var_2D0]; void *
0x18004d963  xor     edx, edx; Val
0x18004d965  mov     r8d, 274h; Size
0x18004d96b  call    memset_0
0x18004d970  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18004d976  xorps   xmm0, xmm0
0x18004d979  xorps   xmm1, xmm1
0x18004d97c  movups  [rsp+600h+var_5A8], xmm0
0x18004d981  movups  xmmword ptr [rbp+500h+var_580], xmm1
0x18004d985  call    cs:__imp_TlsGetValue
0x18004d98c  nop     dword ptr [rax+rax+00h]
0x18004d991  mov     [rsp+600h+var_590], rax
0x18004d996  cmp     byte ptr cs:xmmword_180063D60+2, 0
0x18004d99d  jge     short loc_18004D9B9
0x18004d99f  mov     r9, [rdi+8]
0x18004d9a3  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004d9aa  mov     edx, 3Bh ; ';'
0x18004d9af  mov     ecx, 417h
0x18004d9b4  call    WPP_SF_q
0x18004d9b9  call    InitFlowAndConnectThreads
0x18004d9be  mov     [rsp+600h+var_5AC], eax
0x18004d9c2  test    eax, eax
0x18004d9c4  jnz     short loc_18004D9E7
0x18004d9c6  mov     rbx, [rdi+108h]
0x18004d9cd  lea     esi, [rax+1]
0x18004d9d0  test    rbx, rbx
0x18004d9d3  jnz     short loc_18004DA3B
0x18004d9d5  call    SockSanCreateSwitchSocket
0x18004d9da  mov     rbx, rax
0x18004d9dd  test    rax, rax
0x18004d9e0  jnz     short loc_18004DA0B
0x18004d9e2  lea     esi, [rax+8]
0x18004d9e5  mov     eax, esi
0x18004d9e7  mov     rcx, [rbp+500h+var_50]
0x18004d9ee  xor     rcx, rsp; StackCookie
0x18004d9f1  call    __security_check_cookie
0x18004d9f6  add     rsp, 5C8h
0x18004d9fd  pop     r15
0x18004d9ff  pop     r14
0x18004da01  pop     r13
0x18004da03  pop     r12
0x18004da05  pop     rdi
0x18004da06  pop     rsi
0x18004da07  pop     rbx
0x18004da08  pop     rbp
0x18004da09  retn
0x18004da0b  test    [rdi+48h], sil
0x18004da0f  jz      short loc_18004DA14
0x18004da11  mov     [rax+20h], esi
0x18004da14  mov     rcx, [rdi+0B0h]
0x18004da1b  xor     edx, edx
0x18004da1d  mov     r13b, sil
0x18004da20  call    SockSanFindProvider
0x18004da25  mov     r15, rax
0x18004da28  lock add [rdi], esi
0x18004da2b  lock add [rdi], esi
0x18004da2e  mov     [rbx], rdi
0x18004da31  mov     [rbx+8], rdi
0x18004da35  mov     [rbx+10h], rax
0x18004da39  jmp     short loc_18004DA42
0x18004da3b  mov     r15, [rbx+10h]
0x18004da3f  xor     r13b, r13b
0x18004da42  xor     r14b, r14b
0x18004da45  test    r15, r15
0x18004da48  jnz     short loc_18004DA7C
0x18004da4a  test    byte ptr cs:xmmword_180063D60, 2
0x18004da51  jz      short loc_18004DA72
0x18004da53  mov     r9, [rdi+0B0h]
0x18004da5a  lea     edx, [r15+3Ch]
0x18004da5e  mov     ecx, 401h
0x18004da63  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004da6a  mov     r9d, [r9]
0x18004da6d  call    WPP_SF_d
0x18004da72  mov     esi, 276Bh
0x18004da77  jmp     loc_18004E32D
0x18004da7c  mov     rax, [rbx+10h]
0x18004da80  mov     r9d, [rax+174h]
0x18004da87  mov     eax, [rdi+3Ch]
0x18004da8a  lea     ecx, [r9+r9*8]
0x18004da8e  shl     ecx, 0Ah
0x18004da91  lea     edx, [rax+2400h]
0x18004da97  cmp     edx, ecx
0x18004da99  mov     r8d, edx
0x18004da9c  cmovbe  r8d, ecx
0x18004daa0  cmp     edx, eax
0x18004daa2  jb      loc_18004E328
0x18004daa8  cmp     edx, 2400h
0x18004daae  jb      loc_18004E328
0x18004dab4  lea     eax, [r9+1]
0x18004dab8  imul    edx, eax, 68h ; 'h'
0x18004dabb  lea     ecx, [r9+1]
0x18004dabf  imul    rax, rcx, 68h ; 'h'
0x18004dac3  add     edx, r8d
0x18004dac6  mov     r10d, edx
0x18004dac9  mov     [rsp+600h+var_588], r10
0x18004dace  cmp     r10, rax
0x18004dad1  jb      loc_18004E328
0x18004dad7  cmp     edx, r8d
0x18004dada  jb      loc_18004E328
0x18004dae0  mov     rcx, cs:SockPrivateHeap
0x18004dae7  mov     r8d, r10d
0x18004daea  mov     rax, cs:SockAllocateHeapRoutine
0x18004daf1  xor     edx, edx
0x18004daf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daf8  mov     r12, rax
0x18004dafb  test    rax, rax
0x18004dafe  jz      loc_18004E328
0x18004db04  add     rax, 68h ; 'h'
0x18004db08  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004db0c  mov     [r12+60h], rax
0x18004db11  call    cs:__imp_EnterCriticalSection
0x18004db18  nop     dword ptr [rax+rax+00h]
0x18004db1d  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004db21  mov     dword ptr [rbx+0B0h], 4
0x18004db2b  mov     [rbx+0D0h], r14b
0x18004db32  call    cs:__imp_LeaveCriticalSection
0x18004db39  nop     dword ptr [rax+rax+00h]
0x18004db3e  mov     rax, [rbx+8]
0x18004db42  lock inc dword ptr [rax]
0x18004db45  mov     rax, [rbx+10h]
0x18004db49  mov     [rbp+500h+var_558], 10h
0x18004db51  mov     ecx, [rax+174h]
0x18004db57  mov     rax, [rdi+8]
0x18004db5b  mov     [rbp+500h+var_570], rax
0x18004db5f  mov     rax, [rbx+0D8h]
0x18004db66  lea     edx, [rcx+rcx*8]
0x18004db69  add     rax, 18h
0x18004db6d  mov     ecx, [rdi+3Ch]
0x18004db70  shl     edx, 0Ah
0x18004db73  add     ecx, 2400h
0x18004db79  cmp     ecx, edx
0x18004db7b  mov     [rbp+500h+var_568], rax
0x18004db7f  lea     rax, [rsp+600h+var_5A8]
0x18004db84  cmovbe  ecx, edx
0x18004db87  mov     [rbp+500h+var_560], rax
0x18004db8b  mov     rax, [r12+60h]
0x18004db90  xor     r9d, r9d; ApcContext
0x18004db93  mov     rdx, [rsp+600h+var_590]
0x18004db98  xor     r8d, r8d; ApcRoutine
0x18004db9b  mov     [rsp+600h+OutputBufferLength], ecx; OutputBufferLength
0x18004db9f  mov     rcx, cs:SockSanHelperHandle; FileHandle
0x18004dba6  mov     [rsp+600h+OutputBuffer], rax; OutputBuffer
0x18004dbab  lea     rax, [rbp+500h+var_570]
0x18004dbaf  mov     rdx, [rdx+10h]; Event
0x18004dbb3  mov     [rsp+600h+InputBufferLength], 20h ; ' '; InputBufferLength
0x18004dbbb  mov     [rsp+600h+InputBuffer], rax; InputBuffer
0x18004dbc0  lea     rax, [rbp+500h+var_580]
0x18004dbc4  mov     dword ptr [rsp+600h+IoControlCode], 120FBh; IoControlCode
0x18004dbcc  mov     [rsp+600h+IoStatusBlock], rax; IoStatusBlock
0x18004dbd1  call    cs:__imp_NtDeviceIoControlFile
0x18004dbd8  nop     dword ptr [rax+rax+00h]
0x18004dbdd  mov     esi, eax
0x18004dbdf  cmp     eax, 103h
0x18004dbe4  jnz     short loc_18004DC05
0x18004dbe6  mov     rax, [rsp+600h+var_590]
0x18004dbeb  mov     r9d, 4
0x18004dbf1  mov     rdx, [rdi+8]
0x18004dbf5  mov     rcx, [rax+10h]; Handle
0x18004dbf9  lea     r8d, [r9-1]
0x18004dbfd  call    SockWaitForSingleObject
0x18004dc02  mov     esi, dword ptr [rbp+500h+var_580]
0x18004dc05  test    esi, esi
0x18004dc07  jns     short loc_18004DC59
0x18004dc09  test    byte ptr cs:xmmword_180063D60, 2
0x18004dc10  jz      short loc_18004DC2B
0x18004dc12  mov     edx, 3Dh ; '='
0x18004dc17  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004dc1e  mov     ecx, 401h
0x18004dc23  mov     r9d, esi
0x18004dc26  call    WPP_SF_d
0x18004dc2b  mov     rax, [rbx+8]
0x18004dc2f  or      ecx, 0FFFFFFFFh
0x18004dc32  mov     dword ptr [rbx+0B0h], 2
0x18004dc3c  lock xadd [rax], ecx
0x18004dc40  cmp     ecx, 1
0x18004dc43  jnz     short loc_18004DC4E
0x18004dc45  mov     rcx, [rbx+8]
0x18004dc49  call    SockDestroySocket
0x18004dc4e  mov     ecx, esi
0x18004dc50  call    NtStatusToSocketError
0x18004dc55  mov     esi, eax
0x18004dc57  jmp     short loc_18004DC9F
0x18004dc59  mov     r9d, dword ptr [rbp+500h+var_580.Information]
0x18004dc5d  mov     [rsp+600h+var_598], r9d
0x18004dc62  cmp     byte ptr cs:xmmword_180063D60+2, r14b
0x18004dc69  jge     short loc_18004DC86
0x18004dc6b  movzx   eax, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dc70  shr     eax, 1
0x18004dc72  and     eax, 1
0x18004dc75  mov     dword ptr [rsp+600h+IoControlCode], eax
0x18004dc79  mov     eax, dword ptr [rsp+600h+var_5A8]
0x18004dc7d  mov     dword ptr [rsp+600h+IoStatusBlock], eax
0x18004dc81  call    WPP_SF_dDd
0x18004dc86  mov     al, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dc8a  test    al, 2
0x18004dc8c  jz      short loc_18004DCBC
0x18004dc8e  mov     rax, qword ptr [rsp+600h+var_5A8]
0x18004dc93  xor     esi, esi
0x18004dc95  mov     [rdi+108h], rax
0x18004dc9c  mov     r14b, 1
0x18004dc9f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004dca6  mov     r8, r12; P
0x18004dca9  xor     edx, edx; Flags
0x18004dcab  call    cs:__imp_RtlFreeHeap
0x18004dcb2  nop     dword ptr [rax+rax+00h]
0x18004dcb7  jmp     loc_18004E32D
0x18004dcbc  mov     [rsp+600h+var_5B0], r14b
0x18004dcc1  test    al, 1
0x18004dcc3  jz      short loc_18004DCCF
0x18004dcc5  mov     dword ptr [rbx+0A8h], 2
0x18004dccf  lock inc dword ptr [r15+10h]
0x18004dcd4  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004dcd8  call    cs:__imp_EnterCriticalSection
0x18004dcdf  nop     dword ptr [rax+rax+00h]
0x18004dce4  movzx   eax, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dce9  mov     r14d, 4
0x18004dcef  shr     eax, 5
0x18004dcf2  and     eax, 1
0x18004dcf5  mov     [rbx+324h], eax
0x18004dcfb  movzx   eax, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dd00  shr     eax, 4
0x18004dd03  and     eax, 1
0x18004dd06  mov     [rbx+88h], eax
0x18004dd0c  mov     cl, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dd10  mov     al, [rbx+320h]
0x18004dd16  shr     cl, 1
0x18004dd18  xor     cl, al
0x18004dd1a  and     cl, 2
0x18004dd1d  xor     cl, al
0x18004dd1f  mov     [rbx+320h], cl
0x18004dd25  mov     al, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dd29  shr     al, 1
0x18004dd2b  xor     al, cl
0x18004dd2d  and     al, r14b
0x18004dd30  xor     al, cl
0x18004dd32  mov     [rbx+320h], al
0x18004dd38  mov     cl, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dd3c  mov     al, [rbx+321h]
0x18004dd42  shr     cl, 4
0x18004dd45  xor     cl, al
0x18004dd47  mov     dword ptr [rbx+340h], 0
0x18004dd51  and     cl, r14b
0x18004dd54  xor     cl, al
0x18004dd56  mov     [rbx+321h], cl
0x18004dd5c  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004dd60  call    cs:__imp_LeaveCriticalSection
0x18004dd67  nop     dword ptr [rax+rax+00h]
0x18004dd6c  mov     al, byte ptr [rsp+600h+var_5A8+0Ah]
0x18004dd70  lea     esi, [r14+4]
0x18004dd74  test    al, 10h
0x18004dd76  jnz     loc_18004E03D
0x18004dd7c  test    sil, al
0x18004dd7f  jnz     loc_18004E03D
0x18004dd85  cmp     dword ptr [rdi+1Ch], 2
0x18004dd89  lea     rcx, [rbp+500h+var_550]
0x18004dd8d  mov     r13, [rbx+68h]
0x18004dd91  lea     edx, [rsi+78h]
0x18004dd94  mov     r8d, r14d
0x18004dd97  jnz     short loc_18004DDEC
0x18004dd99  lea     rax, SockTcpProviderInfo
0x18004dda0  movups  xmm0, xmmword ptr [rax]
0x18004dda3  movups  xmm1, xmmword ptr [rax+10h]
0x18004dda7  movups  xmmword ptr [rcx], xmm0
0x18004ddaa  movups  xmm0, xmmword ptr [rax+20h]
0x18004ddae  movups  xmmword ptr [rcx+10h], xmm1
0x18004ddb2  movups  xmm1, xmmword ptr [rax+30h]
0x18004ddb6  movups  xmmword ptr [rcx+20h], xmm0
0x18004ddba  movups  xmm0, xmmword ptr [rax+40h]
0x18004ddbe  movups  xmmword ptr [rcx+30h], xmm1
0x18004ddc2  movups  xmm1, xmmword ptr [rax+50h]
0x18004ddc6  movups  xmmword ptr [rcx+40h], xmm0
0x18004ddca  movups  xmm0, xmmword ptr [rax+60h]
0x18004ddce  movups  xmmword ptr [rcx+50h], xmm1
0x18004ddd2  movups  xmm1, xmmword ptr [rax+70h]
0x18004ddd6  add     rax, rdx
0x18004ddd9  movups  xmmword ptr [rcx+60h], xmm0
0x18004dddd  movups  xmmword ptr [rcx+70h], xmm1
0x18004dde1  add     rcx, rdx
0x18004dde4  sub     r8, 1
0x18004dde8  jnz     short loc_18004DDA0
0x18004ddea  jmp     short loc_18004DE3D
0x18004ddec  lea     rax, SockTcp6ProviderInfo
0x18004ddf3  movups  xmm0, xmmword ptr [rax]
0x18004ddf6  movups  xmm1, xmmword ptr [rax+10h]
0x18004ddfa  movups  xmmword ptr [rcx], xmm0
  ... truncated ...
```
