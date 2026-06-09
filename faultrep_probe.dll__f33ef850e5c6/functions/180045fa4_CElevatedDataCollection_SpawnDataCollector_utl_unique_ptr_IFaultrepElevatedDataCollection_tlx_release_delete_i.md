# CElevatedDataCollection::SpawnDataCollector(utl::unique_ptr<IFaultrepElevatedDataCollection,tlx::release_delete> *,int,ushort)

- ea: `0x180045fa4`
- end: `0x1800466dc`
- name: `?SpawnDataCollector@CElevatedDataCollection@@IEAAJPEAV?$unique_ptr@UIFaultrepElevatedDataCollection@@Urelease_delete@tlx@@@utl@@HG@Z`
- size: `1848`
- prototype: `__int64 __fastcall(__int64, LPVOID *, int, __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045a18`

## callees

- `0x180002890`
- `0x1800028ec`
- `0x180003474`
- `0x180004e9f`
- `0x180004eab`
- `0x180004ef9`
- `0x180009f00`
- `0x180009f40`
- `0x18000ca34`
- `0x18003e5a8`
- `0x180045fa4`
- `0x180048e2c`
- `0x180049280`
- `0x180049304`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004637b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800460c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004637b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464d2`
- `ntdll!RtlNtStatusToDosError` at `0x18004624d`
- `ntdll!RtlNtStatusToDosError` at `0x18004624d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046642`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046642`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046183`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046183`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004667a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800466a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004667a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800466a9`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18004658c`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18004658c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180046300`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180046300`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046688`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046696`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046688`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046696`

## string_xrefs

- `0x180046230`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CElevatedDataCollection::SpawnDataCollector(__int64 a1, LPVOID *a2, int a3, __int16 a4)
{
  LPVOID v7; // rcx
  IStream *v8; // rdi
  const void *v9; // rsi
  HANDLE v10; // r12
  const void *v11; // rbx
  signed int LastError; // eax
  int v13; // r14d
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  unsigned int v19; // r9d
  NTSTATUS v20; // eax
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  DWORD v24; // eax
  DWORD v25; // r12d
  signed int v26; // eax
  const void *v27; // rax
  signed int v28; // eax
  signed int v29; // eax
  int RegionSize; // r14d
  IStream *v31; // rax
  LPVOID v32; // rcx
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h]
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  HANDLE Handles[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A8h] [rbp-58h]
  _BYTE Src[1408]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v42; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v43[38]; // [rsp+642h] [rbp+542h] BYREF
  int v44; // [rsp+668h] [rbp+568h]
  int v45; // [rsp+66Ch] [rbp+56Ch]
  void *v46; // [rsp+680h] [rbp+580h]
  _DWORD v47[12]; // [rsp+BC0h] [rbp+AC0h] BYREF
  __int16 v48; // [rsp+BF0h] [rbp+AF0h]
  HANDLE v49; // [rsp+BF8h] [rbp+AF8h]

  LOWORD(v47[0]) = 0;
  *(_OWORD *)Handles = 0;
  memset_0((char *)v47 + 2, 0, 0x576u);
  v42 = 0;
  memset_0(v43, 0, 0x576u);
  v7 = *a2;
  *a2 = 0;
  v8 = 0;
  v9 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  memset(&Buffer, 0, sizeof(Buffer));
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  *(&FileMappingAttributes.bInheritHandle + 1) = 0;
  *(&FileMappingAttributes.nLength + 1) = 0;
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  FileMappingAttributes.bInheritHandle = 1;
  v10 = CreateFileMappingW_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x20u, 0);
  hObject = v10;
  v35 = (unsigned __int64)v10 + 1;
  if ( (unsigned __int64)v10 + 1 <= 1 )
  {
    v11 = 0;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 35;
LABEL_66:
      WPP_SF_d(v14[2], v15, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v16 = MapViewOfFile_0(v10, 2u, 0, 0, 0);
  v11 = v16;
  if ( !v16 )
  {
    v17 = GetLastError();
    v13 = v17;
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 36;
      goto LABEL_66;
    }
LABEL_67:
    if ( v13 >= 0 || !v11 )
      goto LABEL_88;
    goto LABEL_86;
  }
  *v16 = 0;
  v39 = 0;
  v40 = 0;
  v16[1] = 0;
  *(_QWORD *)v16 = CreateEventW(0, 1, 0, 0);
  if ( !*(_QWORD *)v11 )
  {
    v18 = GetLastError();
    v13 = v18;
    if ( v18 > 0 )
      v13 = (unsigned __int16)v18 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 37;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  *((_DWORD *)v11 + 2) = -2147467259;
  if ( !a3 )
  {
    v13 = -2147467263;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 40;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  memset_0(Src, 0, 0x578u);
  memcpy_0(v47, Src, 0x578u);
  v47[0] = 91751760;
  v47[10] = -805306366;
  v48 = a4;
  v49 = v10;
  v20 = WersvcSendMessage(
          L"\\WindowsErrorReportingServicePort",
          (struct _WERSVC_MSG *)v47,
          (struct _WERSVC_MSG *)&v42,
          v19);
  v21 = RtlNtStatusToDosError(v20);
  v13 = v21;
  if ( v21 > 0 )
    v13 = (unsigned __int16)v21 | 0x80070000;
  if ( v13 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 38;
LABEL_85:
      WPP_SF_d(v22[2], v23, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, (unsigned int)v13);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  if ( v44 != -805306368 )
  {
    v13 = v45 | 0x10000000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 39;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  Handles[0] = *(HANDLE *)v11;
  Handles[1] = v46;
  v24 = WaitForMultipleObjects(2u, Handles, 0, 0x2710u);
  v25 = v24;
  if ( v24 )
  {
    switch ( v24 )
    {
      case 1u:
        v13 = -2147023829;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 41;
          goto LABEL_85;
        }
        break;
      case 0x102u:
        v13 = -2147023843;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 42;
          goto LABEL_85;
        }
        break;
      case 0xFFFFFFFF:
        v26 = GetLastError();
        v13 = v26;
        if ( v26 > 0 )
          v13 = (unsigned __int16)v26 | 0x80070000;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 43;
          goto LABEL_66;
        }
        goto LABEL_67;
      default:
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v13 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
            v25,
            -2147467259);
        break;
    }
LABEL_86:
    if ( *((_QWORD *)v11 + 2) )
      SetEvent(*((HANDLE *)v11 + 2));
LABEL_88:
    if ( !v8 )
      goto LABEL_90;
    goto LABEL_89;
  }
  if ( *((int *)v11 + 2) < 0 )
  {
    v13 = *((_DWORD *)v11 + 2);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 45;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  v27 = MapViewOfFile_0(*((HANDLE *)v11 + 3), 4u, 0, 0, 0);
  v9 = v27;
  if ( !v27 )
  {
    v28 = GetLastError();
    v13 = v28;
    if ( v28 > 0 )
      v13 = (unsigned __int16)v28 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 46;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  memset(&Buffer, 0, sizeof(Buffer));
  if ( !VirtualQuery_0(v27, &Buffer, 0x30u) )
  {
    v29 = GetLastError();
    v13 = v29;
    if ( v29 > 0 )
      v13 = (unsigned __int16)v29 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 47;
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  RegionSize = Buffer.RegionSize;
  v31 = (IStream *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v31;
  if ( !v31 )
  {
    v13 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, 2147942414LL);
    v8 = 0;
    goto LABEL_86;
  }
  *((_QWORD *)v31 + 1) = v9;
  *(_QWORD *)v31 = &MEMORY_STREAM::`vftable';
  *((_DWORD *)v31 + 5) = 0;
  *((_WORD *)v31 + 12) = 0;
  *((_DWORD *)v31 + 4) = RegionSize;
  v32 = *a2;
  *a2 = 0;
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  v13 = CoUnmarshalInterface(v8, &GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935, a2);
  if ( v13 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 49;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  v13 = 0;
LABEL_89:
  MstmFree(v8);
LABEL_90:
  if ( v11 )
  {
    if ( *((_QWORD *)v11 + 2) )
      CloseHandle(*((HANDLE *)v11 + 2));
    if ( *((_QWORD *)v11 + 3) )
      CloseHandle(*((HANDLE *)v11 + 3));
  }
  if ( v9 )
    UnmapViewOfFile(v9);
  if ( v11 )
    UnmapViewOfFile(v11);
  if ( v35 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180045fa4  mov     [rsp-8+arg_0], rbx
0x180045fa9  push    rbp
0x180045faa  push    rsi
0x180045fab  push    rdi
0x180045fac  push    r12
0x180045fae  push    r13
0x180045fb0  push    r14
0x180045fb2  push    r15
0x180045fb4  lea     rbp, [rsp-1050h]
0x180045fbc  mov     eax, 1150h
0x180045fc1  call    _alloca_probe
0x180045fc6  sub     rsp, rax
0x180045fc9  mov     rax, cs:__security_cookie
0x180045fd0  xor     rax, rsp
0x180045fd3  mov     [rbp+1080h+var_40], rax
0x180045fda  mov     r14d, r8d
0x180045fdd  lea     rcx, [rbp+1080h+var_5C0+2]; void *
0x180045fe4  mov     r13, rdx
0x180045fe7  xorps   xmm0, xmm0
0x180045fea  mov     ebx, 576h
0x180045fef  xor     r12d, r12d
0x180045ff2  mov     r8d, ebx; Size
0x180045ff5  mov     word ptr [rbp+1080h+var_5C0], r12w
0x180045ffd  xor     edx, edx; Val
0x180045fff  movzx   r15d, r9w
0x180046003  movups  xmmword ptr [rsp+1180h+Handles], xmm0
0x180046008  call    memset_0
0x18004600d  mov     r8d, ebx; Size
0x180046010  mov     [rbp+1080h+var_B40], r12w
0x180046018  xor     edx, edx; Val
0x18004601a  lea     rcx, [rbp+1080h+var_B3E]; void *
0x180046021  call    memset_0
0x180046026  mov     rcx, [r13+0]
0x18004602a  xorps   xmm0, xmm0
0x18004602d  xor     eax, eax
0x18004602f  mov     [r13+0], r12
0x180046033  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x180046038  mov     edi, r12d
0x18004603b  mov     esi, r12d
0x18004603e  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x180046043  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x180046048  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x18004604d  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x180046051  test    rcx, rcx
0x180046054  jz      short loc_180046062
0x180046056  mov     rax, [rcx]
0x180046059  mov     rax, [rax+10h]
0x18004605d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046062  xor     eax, eax
0x180046064  mov     [rsp+1180h+lpName], r12; lpName
0x180046069  xorps   xmm0, xmm0
0x18004606c  mov     qword ptr [rsp+1180h+FileMappingAttributes.bInheritHandle], rax
0x180046071  movups  xmmword ptr [rsp+1180h+FileMappingAttributes.nLength], xmm0
0x180046076  xor     r9d, r9d; dwMaximumSizeHigh
0x180046079  mov     [rsp+1180h+FileMappingAttributes.nLength], 18h
0x180046081  lea     r8d, [rax+4]; flProtect
0x180046085  mov     [rsp+1180h+FileMappingAttributes.lpSecurityDescriptor], r12
0x18004608a  lea     rdx, [rsp+1180h+FileMappingAttributes]; lpFileMappingAttributes
0x18004608f  mov     [rsp+1180h+FileMappingAttributes.bInheritHandle], 1
0x180046097  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004609b  mov     [rsp+1180h+dwMaximumSizeLow], 20h ; ' '; dwMaximumSizeLow
0x1800460a3  call    CreateFileMappingW_0
0x1800460a8  mov     r12, rax
0x1800460ab  mov     [rsp+1180h+hObject], rax
0x1800460b0  inc     rax
0x1800460b3  mov     [rsp+1180h+var_1138], rax
0x1800460b8  cmp     rax, 1
0x1800460bc  ja      short loc_180046103
0x1800460be  xor     ebx, ebx
0x1800460c0  call    cs:__imp_GetLastError
0x1800460c6  mov     r14d, eax
0x1800460c9  test    eax, eax
0x1800460cb  jle     short loc_1800460D8
0x1800460cd  movzx   r14d, ax
0x1800460d1  or      r14d, 80070000h
0x1800460d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460df  lea     rax, WPP_GLOBAL_Control
0x1800460e6  cmp     rcx, rax
0x1800460e9  jz      loc_180046517
0x1800460ef  test    byte ptr [rcx+1Ch], 1
0x1800460f3  jz      loc_180046517
0x1800460f9  mov     edx, 23h ; '#'
0x1800460fe  jmp     loc_180046504
0x180046103  xor     r9d, r9d; dwFileOffsetLow
0x180046106  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x18004610b  xor     r8d, r8d; dwFileOffsetHigh
0x18004610e  mov     rcx, r12; hFileMappingObject
0x180046111  lea     edx, [r9+2]; dwDesiredAccess
0x180046115  call    MapViewOfFile_0
0x18004611a  mov     rbx, rax
0x18004611d  test    rax, rax
0x180046120  jnz     short loc_180046165
0x180046122  call    cs:__imp_GetLastError
0x180046128  mov     r14d, eax
0x18004612b  test    eax, eax
0x18004612d  jle     short loc_18004613A
0x18004612f  movzx   r14d, ax
0x180046133  or      r14d, 80070000h
0x18004613a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046141  lea     rax, WPP_GLOBAL_Control
0x180046148  cmp     rcx, rax
0x18004614b  jz      loc_180046517
0x180046151  test    byte ptr [rcx+1Ch], 1
0x180046155  jz      loc_180046517
0x18004615b  mov     edx, 24h ; '$'
0x180046160  jmp     loc_180046504
0x180046165  xorps   xmm0, xmm0
0x180046168  xor     r9d, r9d; lpName
0x18004616b  movups  xmmword ptr [rax], xmm0
0x18004616e  xor     r8d, r8d; bInitialState
0x180046171  xor     ecx, ecx; lpEventAttributes
0x180046173  movups  [rbp+1080h+var_10E8], xmm0
0x180046177  lea     edx, [r9+1]; bManualReset
0x18004617b  movups  [rbp+1080h+var_10D8], xmm0
0x18004617f  movups  xmmword ptr [rax+10h], xmm0
0x180046183  call    cs:__imp_CreateEventW
0x180046189  mov     [rbx], rax
0x18004618c  mov     rax, [rbx]
0x18004618f  test    rax, rax
0x180046192  jnz     short loc_1800461D7
0x180046194  call    cs:__imp_GetLastError
0x18004619a  mov     r14d, eax
0x18004619d  test    eax, eax
0x18004619f  jle     short loc_1800461AC
0x1800461a1  movzx   r14d, ax
0x1800461a5  or      r14d, 80070000h
0x1800461ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461b3  lea     rax, WPP_GLOBAL_Control
0x1800461ba  cmp     rcx, rax
0x1800461bd  jz      loc_180046517
0x1800461c3  test    byte ptr [rcx+1Ch], 1
0x1800461c7  jz      loc_180046517
0x1800461cd  mov     edx, 25h ; '%'
0x1800461d2  jmp     loc_180046504
0x1800461d7  mov     dword ptr [rbx+8], 80004005h
0x1800461de  test    r14d, r14d
0x1800461e1  jz      loc_1800465FE
0x1800461e7  mov     r14d, 578h
0x1800461ed  lea     rcx, [rbp+1080h+Src]; void *
0x1800461f1  mov     r8d, r14d; Size
0x1800461f4  xor     edx, edx; Val
0x1800461f6  call    memset_0
0x1800461fb  lea     rcx, [rbp+1080h+var_5C0]; void *
0x180046202  mov     r8d, r14d; Size
0x180046205  lea     rdx, [rbp+1080h+Src]; Src
0x180046209  call    memcpy_0
0x18004620e  lea     r8, [rbp+1080h+var_B40]; struct _WERSVC_MSG *
0x180046215  mov     [rbp+1080h+var_5C0], 5780550h
0x18004621f  lea     rdx, [rbp+1080h+var_5C0]; struct _WERSVC_MSG *
0x180046226  mov     [rbp+1080h+var_598], 0D0000002h
0x180046230  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x180046237  mov     [rbp+1080h+var_590], r15w
0x18004623f  mov     [rbp+1080h+var_588], r12
0x180046246  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18004624b  mov     ecx, eax; Status
0x18004624d  call    cs:__imp_RtlNtStatusToDosError
0x180046253  mov     r14d, eax
0x180046256  mov     r15d, 80070000h
0x18004625c  test    eax, eax
0x18004625e  jle     short loc_180046267
0x180046260  movzx   r14d, ax
0x180046264  or      r14d, r15d
0x180046267  test    r14d, r14d
0x18004626a  jns     short loc_180046297
0x18004626c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046273  lea     rax, WPP_GLOBAL_Control
0x18004627a  cmp     rcx, rax
0x18004627d  jz      loc_180046635
0x180046283  test    byte ptr [rcx+1Ch], 1
0x180046287  jz      loc_180046635
0x18004628d  mov     edx, 26h ; '&'
0x180046292  jmp     loc_180046622
0x180046297  cmp     [rbp+1080h+var_B18], 0D0000000h
0x1800462a1  jz      short loc_1800462DA
0x1800462a3  mov     r14d, [rbp+1080h+var_B14]
0x1800462aa  bts     r14d, 1Ch
0x1800462af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462b6  lea     rax, WPP_GLOBAL_Control
0x1800462bd  cmp     rcx, rax
0x1800462c0  jz      loc_180046517
0x1800462c6  test    byte ptr [rcx+1Ch], 1
0x1800462ca  jz      loc_180046517
0x1800462d0  mov     edx, 27h ; '''
0x1800462d5  jmp     loc_180046504
0x1800462da  mov     rax, [rbx]
0x1800462dd  lea     rdx, [rsp+1180h+Handles]; lpHandles
0x1800462e2  xor     r8d, r8d; bWaitAll
0x1800462e5  mov     [rsp+1180h+Handles], rax
0x1800462ea  mov     rax, [rbp+1080h+var_B00]
0x1800462f1  mov     r9d, 2710h; dwMilliseconds
0x1800462f7  mov     [rsp+1180h+Handles+8], rax
0x1800462fc  lea     ecx, [r8+2]; nCount
0x180046300  call    cs:__imp_WaitForMultipleObjects
0x180046306  mov     r12d, eax
0x180046309  test    eax, eax
0x18004630b  jz      loc_18004641C
0x180046311  cmp     eax, 1
0x180046314  jz      loc_1800463EB
0x18004631a  cmp     eax, 102h
0x18004631f  jz      loc_1800463BA
0x180046325  cmp     eax, 0FFFFFFFFh
0x180046328  jz      short loc_18004637B
0x18004632a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004632f  mov     r8d, 80004005h
0x180046335  mov     r14d, r8d
0x180046338  mov     rcx, cs:WPP_GLOBAL_Control
0x18004633f  lea     rax, WPP_GLOBAL_Control
0x180046346  cmp     rcx, rax
0x180046349  jz      loc_180046635
0x18004634f  test    byte ptr [rcx+1Ch], 1
0x180046353  jz      loc_180046635
0x180046359  mov     rcx, [rcx+10h]
0x18004635d  mov     edx, 2Ch ; ','
0x180046362  mov     [rsp+1180h+dwMaximumSizeLow], r8d
0x180046367  mov     r9d, r12d
0x18004636a  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x180046371  call    WPP_SF_Dd
0x180046376  jmp     loc_180046635
0x18004637b  call    cs:__imp_GetLastError
0x180046381  mov     r14d, eax
0x180046384  test    eax, eax
0x180046386  jle     short loc_18004638F
0x180046388  movzx   r14d, ax
0x18004638c  or      r14d, r15d
0x18004638f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046396  lea     rax, WPP_GLOBAL_Control
0x18004639d  cmp     rcx, rax
0x1800463a0  jz      loc_180046517
0x1800463a6  test    byte ptr [rcx+1Ch], 1
0x1800463aa  jz      loc_180046517
0x1800463b0  mov     edx, 2Bh ; '+'
0x1800463b5  jmp     loc_180046504
0x1800463ba  mov     r14d, 8007041Dh
0x1800463c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463c7  lea     rax, WPP_GLOBAL_Control
0x1800463ce  cmp     rcx, rax
0x1800463d1  jz      loc_180046635
0x1800463d7  test    byte ptr [rcx+1Ch], 1
0x1800463db  jz      loc_180046635
0x1800463e1  mov     edx, 2Ah ; '*'
0x1800463e6  jmp     loc_180046622
0x1800463eb  mov     r14d, 8007042Bh
0x1800463f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463f8  lea     rax, WPP_GLOBAL_Control
0x1800463ff  cmp     rcx, rax
0x180046402  jz      loc_180046635
0x180046408  test    byte ptr [rcx+1Ch], 1
0x18004640c  jz      loc_180046635
0x180046412  mov     edx, 29h ; ')'
0x180046417  jmp     loc_180046622
0x18004641c  mov     eax, [rbx+8]
0x18004641f  test    eax, eax
0x180046421  jns     short loc_180046452
0x180046423  mov     r14d, [rbx+8]
0x180046427  mov     rcx, cs:WPP_GLOBAL_Control
0x18004642e  lea     rax, WPP_GLOBAL_Control
0x180046435  cmp     rcx, rax
0x180046438  jz      loc_180046517
0x18004643e  test    byte ptr [rcx+1Ch], 1
0x180046442  jz      loc_180046517
0x180046448  mov     edx, 2Dh ; '-'
0x18004644d  jmp     loc_180046504
0x180046452  mov     rcx, [rbx+18h]; hFileMappingObject
0x180046456  xor     r9d, r9d; dwFileOffsetLow
0x180046459  xor     r8d, r8d; dwFileOffsetHigh
0x18004645c  mov     qword ptr [rsp+1180h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x180046461  lea     edx, [r9+4]; dwDesiredAccess
0x180046465  call    MapViewOfFile_0
0x18004646a  mov     rsi, rax
0x18004646d  test    rax, rax
0x180046470  jnz     short loc_1800464A6
0x180046472  call    cs:__imp_GetLastError
0x180046478  mov     r14d, eax
0x18004647b  test    eax, eax
0x18004647d  jle     short loc_180046486
0x18004647f  movzx   r14d, ax
0x180046483  or      r14d, r15d
0x180046486  mov     rcx, cs:WPP_GLOBAL_Control
0x18004648d  lea     rax, WPP_GLOBAL_Control
0x180046494  cmp     rcx, rax
0x180046497  jz      short loc_180046517
0x180046499  test    byte ptr [rcx+1Ch], 1
0x18004649d  jz      short loc_180046517
0x18004649f  mov     edx, 2Eh ; '.'
0x1800464a4  jmp     short loc_180046504
0x1800464a6  xorps   xmm0, xmm0
0x1800464a9  lea     rdx, [rsp+1180h+Buffer]; lpBuffer
0x1800464ae  mov     r12d, 30h ; '0'
0x1800464b4  mov     rcx, rsi; lpAddress
0x1800464b7  mov     r8d, r12d; dwLength
0x1800464ba  movups  xmmword ptr [rsp+1180h+Buffer.BaseAddress], xmm0
0x1800464bf  movups  xmmword ptr [rsp+1180h+Buffer.AllocationProtect], xmm0
0x1800464c4  movups  xmmword ptr [rbp+1080h+Buffer.State], xmm0
0x1800464c8  call    VirtualQuery_0
0x1800464cd  test    rax, rax
0x1800464d0  jnz     short loc_18004652E
0x1800464d2  call    cs:__imp_GetLastError
0x1800464d8  mov     r14d, eax
0x1800464db  test    eax, eax
0x1800464dd  jle     short loc_1800464E6
  ... truncated ...
```
