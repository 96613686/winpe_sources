# WSPGetSockOpt

- ea: `0x180007080`
- end: `0x180008188`
- name: `WSPGetSockOpt`
- size: `4360`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052a0`
- `0x180005f78`
- `0x180006d00`
- `0x180007080`
- `0x180008190`
- `0x180008250`
- `0x18000ea70`
- `0x18000f844`
- `0x1800133cc`
- `0x1800143e8`
- `0x180018ea0`
- `0x18001be40`
- `0x180022bd2`
- `0x180037195`
- `0x180038104`
- `0x18003ac78`
- `0x18003ad20`
- `0x18003aefc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800074de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007505`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800074de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007505`
- `ntdll!NtRemoveIoCompletion` at `0x180007363`
- `ntdll!NtRemoveIoCompletion` at `0x180007363`
- `ntdll!NtSetIoCompletion` at `0x1800073db`
- `ntdll!NtSetIoCompletion` at `0x1800073db`
- `ntdll!RtlFreeHeap` at `0x1800080dc`
- `ntdll!RtlFreeHeap` at `0x1800080dc`
- `ntdll!NtDeviceIoControlFile` at `0x180007990`
- `ntdll!NtDeviceIoControlFile` at `0x180007990`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000712d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000739c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000712d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000739c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007889`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007889`

## pseudocode

```c
__int64 __fastcall WSPGetSockOpt(void *a1, int a2, int a3, _DWORD *a4, ULONG *a5, int *a6)
{
  _DWORD *OutputBuffer; // r13
  HANDLE *Value; // rdi
  char v10; // r10
  char v11; // al
  int Information; // esi
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rdx
  size_t v16; // r8
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // ecx
  __int64 v20; // rax
  NTSTATUS v21; // edi
  __int64 v22; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdi
  int v27; // edi
  int LowPart; // eax
  _QWORD *v29; // r13
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rcx
  char *v44; // rcx
  int v45; // eax
  union _LARGE_INTEGER v46; // rax
  unsigned __int16 *QuadPart; // rdi
  ULONG IoControlCode[2]; // [rsp+28h] [rbp-C0h]
  PVOID InputBuffer; // [rsp+30h] [rbp-B8h]
  union _LARGE_INTEGER Timeout[2]; // [rsp+68h] [rbp-80h] BYREF
  PVOID CompletionKey; // [rsp+78h] [rbp-70h] BYREF
  PVOID CompletionContext; // [rsp+80h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-58h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-48h]
  int v56; // [rsp+B0h] [rbp-38h]

  OutputBuffer = a4;
  Value = 0;
  v10 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_sqqqq(
      (_DWORD)a1,
      10,
      (unsigned int)WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids,
      (unsigned int)"WSPGetSockOpt",
      (char)a1,
      a2,
      a3,
      (char)a4);
    v10 = xmmword_180063D60;
  }
  v11 = SockProcessTerminating;
  if ( SockProcessTerminating )
    goto LABEL_69;
  if ( SockWspStartupCount )
  {
    Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
    if ( Value )
    {
      Information = 0;
      goto LABEL_7;
    }
    v10 = xmmword_180063D60;
    v11 = SockProcessTerminating;
  }
  if ( v11 )
  {
LABEL_69:
    if ( (v10 & 2) == 0 )
    {
LABEL_70:
      Information = 10093;
      goto LABEL_78;
    }
    v34 = 20;
LABEL_177:
    WPP_SF_(1025, v34, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids);
    goto LABEL_70;
  }
  if ( !SockWspStartupCount )
  {
    if ( (v10 & 2) == 0 )
      goto LABEL_70;
    v34 = 21;
    goto LABEL_177;
  }
  Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
  if ( Value )
  {
LABEL_77:
    Information = 0;
    goto LABEL_78;
  }
  if ( (unsigned int)MSAFD_SockThreadInitialize() )
  {
    Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
    goto LABEL_77;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 22, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids);
  Information = 10055;
LABEL_78:
  if ( Information )
  {
LABEL_67:
    *a6 = Information;
    return 0xFFFFFFFFLL;
  }
LABEL_7:
  v13 = SockFindAndReferenceSocket(a1);
  v14 = v13;
  if ( v13 )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)(v13 + 224);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 224));
    if ( *(_DWORD *)(v14 + 24) == 4 )
    {
      Information = 10038;
      goto LABEL_59;
    }
    if ( !OutputBuffer || !a5 || (v16 = (int)*a5, (int)*a5 <= 0) )
    {
      Information = 10014;
      goto LABEL_59;
    }
    if ( a2 == 65534 )
      goto LABEL_27;
    if ( a2 != 0xFFFF )
      goto LABEL_43;
    if ( a3 > 256 )
    {
      if ( a3 == 8196 )
        goto LABEL_27;
      goto LABEL_20;
    }
    if ( a3 != 256 )
    {
      if ( a3 > 8 )
      {
        if ( a3 == 16 )
          goto LABEL_20;
        if ( a3 == 32 )
        {
          if ( (*(_BYTE *)(v14 + 80) & 1) == 0 )
            goto LABEL_27;
          goto LABEL_20;
        }
        if ( a3 != 128 )
          goto LABEL_20;
      }
      else if ( a3 != 8 && a3 != 2 && a3 != -129 )
      {
        goto LABEL_20;
      }
    }
    if ( (*(_BYTE *)(v14 + 80) & 1) != 0 )
    {
LABEL_27:
      Information = 10042;
      goto LABEL_59;
    }
LABEL_20:
    v17 = (unsigned int)(a3 + 5);
    if ( (unsigned int)v17 <= 0x25 && (v18 = 0x20000002C1LL, _bittest64(&v18, v17))
      || a3 == 256
      || a3 == 128
      || (unsigned int)(a3 - 4097) <= 7 && (v19 = 195, _bittest(&v19, a3 - 4097))
      || a3 == -129
      || a3 == 12290 )
    {
      memset_0(OutputBuffer, 0, v16);
    }
LABEL_43:
    if ( a2 == 0xFFFF )
    {
      if ( a3 == 4103 )
      {
        if ( *a5 < 4 )
        {
          Information = 10014;
        }
        else
        {
          Timeout[0].QuadPart = 0;
          CompletionContext = 0;
          CompletionKey = 0;
          IoStatusBlock = 0;
          while ( 1 )
          {
            v20 = *(_QWORD *)(v14 + 200);
            if ( !v20 || *(_DWORD *)(v20 + 16) == 259 )
              break;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 224));
            v21 = NtRemoveIoCompletion(SockAsyncQueuePort, &CompletionKey, &CompletionContext, &IoStatusBlock, Timeout);
            if ( !v21 )
            {
              if ( CompletionKey == (PVOID)-1LL )
              {
                NtSetIoCompletion(SockAsyncQueuePort, (PVOID)0xFFFFFFFFFFFFFFFFLL, (PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0);
                EnterCriticalSection(lpCriticalSection);
                break;
              }
              SockHandleAsyncIndication(CompletionKey, CompletionContext, &IoStatusBlock);
            }
            EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 224));
            if ( v21 == 258 )
              Timeout[0].QuadPart = -100000;
          }
          *OutputBuffer = *(_DWORD *)(v14 + 100);
          *a5 = 4;
        }
        goto LABEL_59;
      }
      if ( a3 <= 4097 )
      {
        if ( a3 == 4097 )
        {
          if ( *a5 < 4 )
          {
            Information = 10014;
          }
          else if ( (*(_BYTE *)(v14 + 80) & 1) != 0
                 || *(_DWORD *)(v14 + 24) != 3
                 || SockSanEnabled
                 && (v25 = *(_QWORD *)(v14 + 264)) != 0
                 && (*(_BYTE *)(v14 + 69) & 8) != 0
                 && *(_DWORD *)(v25 + 152) == 1 )
          {
            *OutputBuffer = *(_DWORD *)(v14 + 64);
            *a5 = 4;
            Information = 0;
            *a5 = 4;
          }
          else
          {
            InputBuffer = 0;
            *(_QWORD *)IoControlCode = OutputBuffer;
            Information = SockGetInformation(v14, 7, 0, 0);
            if ( !Information )
              *a5 = 4;
          }
          goto LABEL_59;
        }
        if ( a3 <= 4 )
        {
          switch ( a3 )
          {
            case 4:
              *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 68) & 0x10) != 0;
              v38 = 1;
              if ( *a5 >= 4 )
                v38 = 4;
              *a5 = v38;
              goto LABEL_59;
            case -129:
              *(_BYTE *)OutputBuffer = *(_WORD *)(v14 + 48) == 0;
              v37 = 1;
              if ( *a5 >= 4 )
                v37 = 4;
              *a5 = v37;
              goto LABEL_59;
            case -5:
              *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 68) & 0x20) != 0;
              v36 = 1;
              if ( *a5 >= 4 )
                v36 = 4;
              *a5 = v36;
              goto LABEL_59;
            case 1:
              *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 68) & 4) != 0;
              v35 = 1;
              if ( *a5 >= 4 )
                v35 = 4;
              *a5 = v35;
              goto LABEL_59;
            case 2:
              *(_BYTE *)OutputBuffer = *(_BYTE *)(v14 + 68) & 1;
              v33 = 1;
              if ( *a5 >= 4 )
                v33 = 4;
              *a5 = v33;
              goto LABEL_59;
          }
        }
        else
        {
          switch ( a3 )
          {
            case 32:
              *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 68) & 2) != 0;
              v40 = 1;
              if ( *a5 >= 4 )
                v40 = 4;
              *a5 = v40;
              goto LABEL_59;
            case 128:
              if ( *a5 >= 4 )
              {
                *OutputBuffer = *(_DWORD *)(v14 + 48);
                *a5 = 4;
              }
              else
              {
                Information = 10014;
              }
              goto LABEL_59;
            case 256:
              *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 68) & 8) != 0;
              v39 = 1;
              if ( *a5 >= 4 )
                v39 = 4;
              *a5 = v39;
              goto LABEL_59;
          }
        }
      }
      else if ( a3 <= 8193 )
      {
        switch ( a3 )
        {
          case 8193:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 88);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 4098:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 60);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 4101:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 52);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 4102:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 56);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 4104:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 32);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 4105:
            v41 = *(int *)(v14 + 40);
            if ( (int)v41 < 0
              || (v42 = *(int *)(v14 + 44), (int)v42 < 0)
              || (v43 = *a5, (unsigned int)v43 < 0x28)
              || (unsigned int)v43 < (unsigned __int64)(v43 - v42 - v41 - 40) )
            {
              Information = 10014;
            }
            else
            {
              OutputBuffer[8] = *(_DWORD *)(v14 + 32);
              OutputBuffer[9] = *(_DWORD *)(v14 + 36);
              if ( (unsigned int)(*(_DWORD *)(v14 + 24) - 1) <= 2 )
              {
                *(_QWORD *)OutputBuffer = OutputBuffer + 10;
                OutputBuffer[2] = *(_DWORD *)(v14 + 40);
                memcpy_0(OutputBuffer + 10, *(const void **)(v14 + 168), *(int *)(v14 + 40));
              }
              else
              {
                *(_QWORD *)OutputBuffer = 0;
                OutputBuffer[2] = 0;
              }
              if ( *(_DWORD *)(v14 + 24) == 3 )
              {
                v44 = (char *)OutputBuffer + *(int *)(v14 + 40) + 40;
                *((_QWORD *)OutputBuffer + 2) = v44;
                OutputBuffer[6] = *(_DWORD *)(v14 + 44);
                memcpy_0(v44, *(const void **)(v14 + 176), *(int *)(v14 + 44));
              }
              else
              {
                *((_QWORD *)OutputBuffer + 2) = 0;
                OutputBuffer[6] = 0;
              }
            }
            goto LABEL_59;
        }
      }
      else
      {
        if ( a3 == 28672 )
        {
          Information = SockGetConnectData(v14, 73819, OutputBuffer, *a5, a5);
          goto LABEL_59;
        }
        if ( a3 > 28672 )
        {
          switch ( a3 )
          {
            case 28673:
              Information = SockGetConnectData(v14, 73823, OutputBuffer, *a5, a5);
              break;
            case 28674:
              Information = SockGetConnectData(v14, 73827, OutputBuffer, *a5, a5);
              break;
            case 28675:
              Information = SockGetConnectData(v14, 73831, OutputBuffer, *a5, a5);
              break;
            case 28681:
              goto LABEL_171;
            case 28682:
              v46.QuadPart = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                               SockPrivateHeap,
                               0,
                               *(int *)(*(_QWORD *)(v14 + 152) + 44LL));
              QuadPart = (unsigned __int16 *)v46.QuadPart;
              Timeout[0] = v46;
              if ( v46.QuadPart )
              {
                if ( *a5 >= 4 )
                {
                  ((void (__fastcall *)(_QWORD, _QWORD))SockBuildTdiAddress)(
                    (union _LARGE_INTEGER)v46.QuadPart,
                    OutputBuffer);
                  InputBuffer = 0;
                  *(_QWORD *)IoControlCode = OutputBuffer;
                  Information = SockGetInformation(v14, 5, QuadPart, QuadPart[2]);
                  if ( !Information )
                    *a5 = 4;
                }
                else
                {
                  Information = 10014;
                }
                RtlFreeHeap(SockPrivateHeap, 0, QuadPart);
              }
              else
              {
                Information = 10055;
              }
              break;
            case 28684:
              if ( *a5 < 4 )
              {
                Information = 10014;
              }
              else if ( SockSanEnabled
                     && (v26 = *(_QWORD *)(v14 + 264)) != 0
                     && (*(_BYTE *)(v14 + 69) & 8) != 0
                     && *(_DWORD *)(v26 + 152) == 1 )
              {
                v27 = *(_DWORD *)(v26 + 156);
                *OutputBuffer = GetTickCount() - v27;
                *a5 = 4;
                Information = 0;
              }
              else
              {
                InputBuffer = 0;
                *(_QWORD *)IoControlCode = OutputBuffer;
                Information = SockGetInformation(v14, 8, 0, 0);
                if ( !Information )
                  *a5 = 4;
              }
              break;
            default:
              goto LABEL_136;
          }
          goto LABEL_59;
        }
        switch ( a3 )
        {
          case 8194:
            if ( *a5 >= 4 )
            {
              *OutputBuffer = *(_DWORD *)(v14 + 96);
              *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 8195:
LABEL_171:
            if ( *a5 >= 4 )
            {
              InputBuffer = 0;
              *(_QWORD *)IoControlCode = OutputBuffer;
              Information = SockGetInformation(v14, 3, 0, 0);
              if ( !Information )
                *a5 = 4;
            }
            else
            {
              Information = 10014;
            }
            goto LABEL_59;
          case 8197:
            if ( *a5 >= 0x274 )
            {
              LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 224));
              Information = SockBuildProtocolInfoForSocket(v14, OutputBuffer);
              if ( SockSanEnabled )
              {
                v24 = *(_QWORD *)(v14 + 264);
                if ( v24 )
                {
                  if ( (*(_BYTE *)(v14 + 69) & 8) != 0 && *(_DWORD *)(v24 + 152) == 1 )
                    *OutputBuffer &= ~0x20000u;
                }
              }
              *a5 = 628;
LABEL_60:
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) == 1 )
                SockDestroySocket(v14);
              if ( Information )
              {
                if ( (xmmword_180063D60 & 2) != 0 )
                {
                  IoControlCode[0] = Information;
                  WPP_SF_iql(
                    v22,
                    11,
                    WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids,
                    a1,
                    v14,
                    *(_QWORD *)IoControlCode,
                    InputBuffer);
                }
              }
              else if ( (xmmword_180063D60 & 2) != 0 )
              {
                WPP_SF_qq(
                  1025,
                  12,
                  WPP_06ddd0886b683faf63d5feb5db1037b5_Traceguids,
                  a1,
                  v14,
                  *(_QWORD *)IoControlCode,
                  InputBuffer);
              }
              if ( !Information )
                return 0;
              goto LABEL_67;
            }
            Information = 10014;
LABEL_59:
            LeaveCriticalSection(lpCriticalSection);
            goto LABEL_60;
          case 12290:
            *(_BYTE *)OutputBuffer = (*(_BYTE *)(v14 + 69) & 4) != 0;
            v45 = 1;
            if ( *a5 >= 4 )
              v45 = 4;
            *a5 = v45;
            goto LABEL_59;
        }
      }
    }
LABEL_136:
    if ( (*(_BYTE *)(v14 + 69) & 0x10) == 0 )
    {
      v29 = (_QWORD *)(v14 + 192);
      if ( *(_QWORD *)(v14 + 184) != -1 || *v29 != -1 )
      {
        if ( (unsigned int)SockGetTdiHandles(v14, v15, v16)
          || *(_QWORD *)(v14 + 184) != -1
          || (v29 = (_QWORD *)(v14 + 192), *(_QWORD *)(v14 + 192) != -1) )
        {
          Information = SockGetTdiHandles(v14, v30, v31);
          if ( Information )
            goto LABEL_59;
          v32 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, int, int, _DWORD *, ULONG *))(*(_QWORD *)(v14 + 152) + 112LL))(
                  *(_QWORD *)(v14 + 160),
                  a1,
                  *(_QWORD *)(v14 + 184),
                  *v29,
                  a2,
                  a3,
                  a4,
                  a5);
          goto LABEL_236;
        }
      }
      OutputBuffer = a4;
    }
    *(_OWORD *)&Timeout[0].LowPart = 0;
    v55 = 0;
    IoStatusBlock.Status = 2;
    HIDWORD(IoStatusBlock.Pointer) = a2;
    IoStatusBlock.Information = (unsigned int)a3 | 0x100000000LL;
    LowPart = NtDeviceIoControlFile(
                a1,
                Value[2],
                0,
                0,
                (PIO_STATUS_BLOCK)Timeout,
                0x120BFu,
                &IoStatusBlock,
                0x20u,
                OutputBuffer,
                *a5);
    v56 = LowPart;
    if ( LowPart == 259 )
    {
      SockWaitForSingleObject(Value[2]);
      LowPart = Timeout[0].LowPart;
    }
    if ( Timeout[1].QuadPart > 0xFFFFFFFFuLL )
    {
      *a5 = 0;
      Information = 10014;
      goto LABEL_59;
    }
    *a5 = Timeout[1].LowPart;
    if ( LowPart >= 0 )
      goto LABEL_59;
    if ( LowPart == -1073741637 )
    {
      Information = 10042;
      goto LABEL_59;
    }
    v32 = NtStatusToSocketError((unsigned int)LowPart);
LABEL_236:
    Information = v32;
    goto LABEL_59;
  }
  *a6 = 10038;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180007080  mov     [rsp+arg_8], rbx
0x180007085  mov     [rsp+arg_10], rsi
0x18000708a  mov     [rsp+arg_18], r9
0x18000708f  mov     [rsp+FileHandle], rcx
0x180007094  push    rdi
0x180007095  push    r12
0x180007097  push    r13
0x180007099  push    r14
0x18000709b  push    r15
0x18000709d  sub     rsp, 0C0h
0x1800070a4  mov     r13, r9
0x1800070a7  movsxd  r14, r8d
0x1800070aa  movsxd  r12, edx
0x1800070ad  xor     edi, edi
0x1800070af  movzx   r10d, byte ptr cs:xmmword_180063D60
0x1800070b7  test    r10b, 2
0x1800070bb  jnz     loc_1800077B3
0x1800070c1  movzx   eax, cs:SockProcessTerminating
0x1800070c8  test    al, al
0x1800070ca  jnz     loc_1800074A7
0x1800070d0  cmp     cs:SockWspStartupCount, edi
0x1800070d6  jbe     loc_1800074C7
0x1800070dc  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x1800070e2  call    cs:__imp_TlsGetValue
0x1800070e9  nop     dword ptr [rax+rax+00h]
0x1800070ee  mov     rdi, rax
0x1800070f1  test    rax, rax
0x1800070f4  jz      loc_1800074B8
0x1800070fa  xor     esi, esi
0x1800070fc  mov     dl, 1
0x1800070fe  mov     rcx, [rsp+0E8h+FileHandle]
0x180007106  call    SockFindAndReferenceSocket
0x18000710b  mov     rbx, rax
0x18000710e  mov     [rsp+0E8h+var_90], rax
0x180007113  test    rax, rax
0x180007116  jz      loc_180007492
0x18000711c  add     rax, 0E0h
0x180007122  mov     [rsp+0E8h+lpCriticalSection], rax
0x18000712a  mov     rcx, rax; lpCriticalSection
0x18000712d  call    cs:__imp_EnterCriticalSection
0x180007134  nop     dword ptr [rax+rax+00h]
0x180007139  cmp     dword ptr [rbx+18h], 4
0x18000713d  jz      loc_180007B84
0x180007143  test    r13, r13
0x180007146  jz      loc_180007294
0x18000714c  mov     r15, [rsp+0E8h+arg_20]
0x180007154  test    r15, r15
0x180007157  jz      loc_180007294
0x18000715d  movsxd  rax, dword ptr [r15]
0x180007160  mov     r8, rax; Size
0x180007163  cmp     rax, 1
0x180007167  jb      loc_180007294
0x18000716d  test    eax, eax
0x18000716f  js      loc_180007294
0x180007175  cmp     r12d, 0FFFEh
0x18000717c  jz      loc_180007203
0x180007182  cmp     r12d, 0FFFFh
0x180007189  jnz     short loc_1800071D9
0x18000718b  cmp     r14d, 100h
0x180007192  jg      short loc_1800071DE
0x180007194  jz      short loc_1800071FD
0x180007196  cmp     r14d, 8
0x18000719a  jg      short loc_180007211
0x18000719c  jz      short loc_1800071FD
0x18000719e  cmp     r14d, 2
0x1800071a2  jz      short loc_1800071FD
0x1800071a4  cmp     r14d, 0FFFFFF7Fh
0x1800071ab  jz      short loc_1800071FD
0x1800071ad  cmp     r12d, 0FFFFh
0x1800071b4  jnz     short loc_1800071D9
0x1800071b6  lea     eax, [r14+5]
0x1800071ba  cmp     eax, 25h ; '%'
0x1800071bd  ja      short loc_180007226
0x1800071bf  mov     rcx, 20000002C1h
0x1800071c9  bt      rcx, rax
0x1800071cd  jnb     short loc_180007226
0x1800071cf  xor     edx, edx; Val
0x1800071d1  mov     rcx, r13; void *
0x1800071d4  call    memset_0
0x1800071d9  jmp     loc_1800072B5
0x1800071de  cmp     r14d, 2001h
0x1800071e5  jle     loc_180007277
0x1800071eb  mov     ecx, r14d
0x1800071ee  sub     ecx, 2002h
0x1800071f4  jz      short loc_1800071AD
0x1800071f6  cmp     ecx, 2
0x1800071f9  jnz     short loc_1800071AD
0x1800071fb  jmp     short loc_180007203
0x1800071fd  test    byte ptr [rbx+50h], 1
0x180007201  jz      short loc_1800071AD
0x180007203  mov     esi, 273Ah
0x180007208  mov     [rsp+0E8h+var_98], esi
0x18000720c  jmp     loc_18000741E
0x180007211  mov     ecx, r14d
0x180007214  sub     ecx, 10h
0x180007217  jz      short loc_1800071AD
0x180007219  sub     ecx, 10h
0x18000721c  jnz     short loc_18000726D
0x18000721e  test    byte ptr [rbx+50h], 1
0x180007222  jz      short loc_180007203
0x180007224  jmp     short loc_1800071AD
0x180007226  cmp     r14d, 100h
0x18000722d  jz      short loc_1800071CF
0x18000722f  cmp     r14d, 80h
0x180007236  jz      short loc_1800071CF
0x180007238  lea     eax, [r14-1001h]
0x18000723f  cmp     eax, 7
0x180007242  ja      short loc_18000724E
0x180007244  mov     ecx, 0C3h
0x180007249  bt      ecx, eax
0x18000724c  jb      short loc_1800071CF
0x18000724e  cmp     r14d, 0FFFFFF7Fh
0x180007255  jz      loc_1800071CF
0x18000725b  cmp     r14d, 3002h
0x180007262  jnz     loc_1800071D9
0x180007268  jmp     loc_1800071CF
0x18000726d  cmp     ecx, 60h ; '`'
0x180007270  jz      short loc_1800071FD
0x180007272  jmp     loc_1800071AD
0x180007277  jz      loc_1800071AD
0x18000727d  mov     ecx, r14d
0x180007280  sub     ecx, 1001h
0x180007286  jz      loc_1800071AD
0x18000728c  sub     ecx, 1
0x18000728f  jmp     loc_1800071AD
0x180007294  mov     esi, 271Eh
0x180007299  mov     [rsp+0E8h+var_98], esi
0x18000729d  jmp     loc_18000741E
0x1800072a2  mov     esi, 271Eh
0x1800072a7  mov     [rsp+0E8h+var_98], esi
0x1800072ab  mov     rbx, [rsp+0E8h+var_90]
0x1800072b0  jmp     loc_18000741E
0x1800072b5  cmp     r12d, 0FFFFh
0x1800072bc  jnz     def_18000780F; jumptable 000000018000780F default case, cases 28676-28680,28683
0x1800072c2  cmp     r14d, 1007h
0x1800072c9  jnz     loc_180007523
0x1800072cf  cmp     dword ptr [r15], 4
0x1800072d3  jb      short loc_18000730F
0x1800072d5  mov     qword ptr [rsp+0E8h+var_80], 0
0x1800072de  mov     [rsp+0E8h+CompletionContext], 0
0x1800072ea  mov     [rsp+0E8h+CompletionKey], 0
0x1800072f3  xorps   xmm0, xmm0
0x1800072f6  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x1800072fe  mov     rax, [rbx+0C8h]
0x180007305  test    rax, rax
0x180007308  jnz     short loc_18000731D
0x18000730a  jmp     loc_1800073FB
0x18000730f  mov     esi, 271Eh
0x180007314  mov     [rsp+0E8h+var_98], esi
0x180007318  jmp     loc_18000741E
0x18000731d  cmp     dword ptr [rax+10h], 103h
0x180007324  jz      loc_1800073FB
0x18000732a  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180007331  call    cs:__imp_LeaveCriticalSection
0x180007338  nop     dword ptr [rax+rax+00h]
0x18000733d  lea     rax, [rsp+0E8h+var_80]
0x180007342  mov     [rsp+0E8h+Timeout], rax; Timeout
0x180007347  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x18000734f  lea     r8, [rsp+0E8h+CompletionContext]; CompletionContext
0x180007357  lea     rdx, [rsp+0E8h+CompletionKey]; CompletionKey
0x18000735c  mov     rcx, cs:SockAsyncQueuePort; IoCompletionHandle
0x180007363  call    cs:__imp_NtRemoveIoCompletion
0x18000736a  nop     dword ptr [rax+rax+00h]
0x18000736f  mov     edi, eax
0x180007371  test    eax, eax
0x180007373  jnz     short loc_180007395
0x180007375  mov     rcx, [rsp+0E8h+CompletionKey]
0x18000737a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000737e  jz      short loc_1800073BE
0x180007380  lea     r8, [rsp+0E8h+IoStatusBlock]
0x180007388  mov     rdx, [rsp+0E8h+CompletionContext]
0x180007390  call    SockHandleAsyncIndication
0x180007395  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18000739c  call    cs:__imp_EnterCriticalSection
0x1800073a3  nop     dword ptr [rax+rax+00h]
0x1800073a8  cmp     edi, 102h
0x1800073ae  jnz     short loc_1800073B9
0x1800073b0  mov     qword ptr [rsp+0E8h+var_80], 0FFFFFFFFFFFE7960h
0x1800073b9  jmp     loc_1800072FE
0x1800073be  mov     [rsp+0E8h+Timeout], 0; CompletionInformation
0x1800073c7  xor     r9d, r9d; CompletionStatus
0x1800073ca  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionKey
0x1800073d1  mov     r8, rdx; CompletionContext
0x1800073d4  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x1800073db  call    cs:__imp_NtSetIoCompletion
0x1800073e2  nop     dword ptr [rax+rax+00h]
0x1800073e7  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x1800073ef  call    cs:__imp_EnterCriticalSection
0x1800073f6  nop     dword ptr [rax+rax+00h]
0x1800073fb  mov     eax, [rbx+18h]
0x1800073fe  mov     eax, [rbx+64h]
0x180007401  mov     [r13+0], eax
0x180007405  mov     r9d, 4
0x18000740b  mov     [r15], r9d
0x18000740e  jmp     short loc_18000741E
0x180007410  mov     esi, 271Eh
0x180007415  mov     [rsp+0E8h+var_98], esi
0x180007419  mov     rbx, [rsp+0E8h+var_90]
0x18000741e  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x180007426  call    cs:__imp_LeaveCriticalSection
0x18000742d  nop     dword ptr [rax+rax+00h]
0x180007432  mov     eax, 0FFFFFFFFh
0x180007437  lock xadd [rbx], eax
0x18000743b  cmp     eax, 1
0x18000743e  jnz     short loc_180007448
0x180007440  mov     rcx, rbx
0x180007443  call    SockDestroySocket
0x180007448  test    esi, esi
0x18000744a  jnz     loc_180007A73
0x180007450  test    byte ptr cs:xmmword_180063D60, 2
0x180007457  jnz     loc_18000812E
0x18000745d  test    esi, esi
0x18000745f  jnz     short loc_180007481
0x180007461  xor     eax, eax
0x180007463  lea     r11, [rsp+0E8h+var_28]
0x18000746b  mov     rbx, [r11+38h]
0x18000746f  mov     rsi, [r11+40h]
0x180007473  mov     rsp, r11
0x180007476  pop     r15
0x180007478  pop     r14
0x18000747a  pop     r13
0x18000747c  pop     r12
0x18000747e  pop     rdi
0x18000747f  retn
0x180007481  mov     rax, [rsp+0E8h+arg_28]
0x180007489  mov     [rax], esi
0x18000748b  mov     eax, 0FFFFFFFFh
0x180007490  jmp     short loc_180007463
0x180007492  mov     rax, [rsp+0E8h+arg_28]
0x18000749a  mov     dword ptr [rax], 2736h
0x1800074a0  mov     eax, 0FFFFFFFFh
0x1800074a5  jmp     short loc_180007463
0x1800074a7  test    r10b, 2
0x1800074ab  jnz     loc_180007C52
0x1800074b1  mov     esi, 276Dh
0x1800074b6  jmp     short loc_180007516
0x1800074b8  movzx   r10d, byte ptr cs:xmmword_180063D60
0x1800074c0  movzx   eax, cs:SockProcessTerminating
0x1800074c7  test    al, al
0x1800074c9  jnz     short loc_1800074A7
0x1800074cb  cmp     cs:SockWspStartupCount, 0
0x1800074d2  jbe     loc_180007C74
0x1800074d8  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x1800074de  call    cs:__imp_TlsGetValue
0x1800074e5  nop     dword ptr [rax+rax+00h]
0x1800074ea  mov     rdi, rax
0x1800074ed  test    rax, rax
0x1800074f0  jnz     short loc_180007514
0x1800074f2  call    MSAFD_SockThreadInitialize
0x1800074f7  test    eax, eax
0x1800074f9  jz      loc_180007C80
0x1800074ff  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180007505  call    cs:__imp_TlsGetValue
0x18000750c  nop     dword ptr [rax+rax+00h]
0x180007511  mov     rdi, rax
0x180007514  xor     esi, esi
0x180007516  test    esi, esi
0x180007518  jz      loc_1800070FC
0x18000751e  jmp     loc_180007481
0x180007523  cmp     r14d, 1001h
0x18000752a  jle     loc_180007688
0x180007530  cmp     r14d, 2001h
0x180007537  jle     loc_18000761C
0x18000753d  cmp     r14d, 7000h
0x180007544  jz      loc_180007741
0x18000754a  jg      loc_1800077EC
0x180007550  mov     ecx, r14d
0x180007553  sub     ecx, 2002h
0x180007559  jz      loc_180007F51
0x18000755f  sub     ecx, 1
0x180007562  jz      loc_180007BF2; jumptable 000000018000780F case 28681
0x180007568  sub     ecx, 2
0x18000756b  jnz     loc_180007F0F
0x180007571  mov     [rsp+0E8h+var_88], cl
0x180007575  cmp     dword ptr [r15], 274h
0x18000757c  jb      short loc_1800075BE
0x18000757e  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180007585  call    cs:__imp_LeaveCriticalSection
0x18000758c  nop     dword ptr [rax+rax+00h]
0x180007591  mov     [rsp+0E8h+var_88], 1
0x180007596  mov     rdx, r13
0x180007599  mov     rcx, rbx
0x18000759c  call    SockBuildProtocolInfoForSocket
0x1800075a1  mov     esi, eax
0x1800075a3  mov     [rsp+0E8h+var_98], eax
0x1800075a7  cmp     cs:SockSanEnabled, 0
0x1800075ae  jz      short loc_1800075E3
0x1800075b0  mov     rax, [rbx+108h]
0x1800075b7  test    rax, rax
0x1800075ba  jnz     short loc_1800075CC
0x1800075bc  jmp     short loc_1800075E3
0x1800075be  mov     esi, 271Eh
0x1800075c3  mov     [rsp+0E8h+var_98], esi
0x1800075c7  jmp     loc_18000741E
0x1800075cc  test    byte ptr [rbx+45h], 8
0x1800075d0  jz      short loc_1800075E3
0x1800075d2  cmp     dword ptr [rax+98h], 1
0x1800075d9  jnz     short loc_1800075E3
0x1800075db  and     dword ptr [r13+0], 0FFFDFFFFh
0x1800075e3  mov     dword ptr [r15], 274h
  ... truncated ...
```
