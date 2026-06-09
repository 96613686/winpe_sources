# EventDispatcher_RegisterEventSink(tagOFFLINEFILES_EVENTS,IUnknown *,_GUID const &,ushort const *,tagOFFLINEFILES_PATHFILTER_MATCH,ulong,ulong,ulong,_LUID,void *,void *)

- ea: `0x18000cf58`
- end: `0x18000d442`
- name: `?EventDispatcher_RegisterEventSink@@YAJW4tagOFFLINEFILES_EVENTS@@PEAUIUnknown@@AEBU_GUID@@PEBGW4tagOFFLINEFILES_PATHFILTER_MATCH@@KKKU_LUID@@PEAX6@Z`
- size: `1258`
- prototype: `__int64 __fastcall(enum tagOFFLINEFILES_EVENTS, struct IUnknown *, const struct _GUID *, const unsigned __int16 *, tagOFFLINEFILES_PATHFILTER_MATCH, unsigned int, unsigned int, unsigned int, struct _LUID, HANDLE hSourceHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003365c`

## callees

- `0x18000cf58`
- `0x18000d640`
- `0x18000d698`
- `0x18001be00`
- `0x18002edac`
- `0x18002f10c`
- `0x180030250`
- `0x180030a30`
- `0x1800325f0`
- `0x180036394`
- `0x18004e5f0`
- `0x18004f2e8`
- `0x18004fbfc`
- `0x18004fd00`
- `0x18004fda4`
- `0x18004fef4`
- `0x18004ff34`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d16d`
- `ntdll!RtlNtStatusToDosError` at `0x18000d16d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d078`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d339`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000d055`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000d055`
- `KERNEL32!DuplicateHandle` at `0x18000cfef`
- `KERNEL32!DuplicateHandle` at `0x18000cfef`
- `KERNEL32!GetCurrentProcess` at `0x18000cfbd`
- `KERNEL32!GetCurrentProcess` at `0x18000cfc6`
- `KERNEL32!GetCurrentProcess` at `0x18000cfbd`
- `KERNEL32!GetCurrentProcess` at `0x18000cfc6`
- `ADVAPI32!GetLengthSid` at `0x18000d0c0`
- `ADVAPI32!GetLengthSid` at `0x18000d0c0`
- `ADVAPI32!CopySid` at `0x18000d0ec`
- `ADVAPI32!CopySid` at `0x18000d0ec`

## pseudocode

```c
__int64 __fastcall EventDispatcher_RegisterEventSink(
        enum tagOFFLINEFILES_EVENTS a1,
        struct IUnknown *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        tagOFFLINEFILES_PATHFILTER_MATCH a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        struct _LUID a9,
        HANDLE hSourceHandle,
        PSID pSid)
{
  enum tagOFFLINEFILES_EVENTS v13; // eax
  char v14; // di
  signed int Error; // ebx
  char v16; // r14
  HANDLE v17; // rsi
  int StringCopy; // eax
  void *v19; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v21; // rax
  DWORD LengthSid; // r14d
  void *v23; // r9
  PSID v24; // r15
  void *v25; // rdx
  NTSTATUS SidIndex; // ebx
  signed int v27; // eax
  void *v28; // rdx
  __int64 v29; // rcx
  unsigned int Offset; // eax
  __int64 v31; // rcx
  void **v32; // rdi
  unsigned int v33; // r14d
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  __int64 *v38; // rcx
  void ***v39; // rax
  unsigned int v40; // eax
  __int64 v41; // r10
  __int64 v42; // r8
  __int64 v43; // r9
  unsigned int v44; // eax
  __int64 v45; // r8
  unsigned __int16 v47; // [rsp+50h] [rbp-28h] BYREF
  HANDLE TargetHandle; // [rsp+58h] [rbp-20h] BYREF
  PSID pDestinationSid[3]; // [rsp+60h] [rbp-18h] BYREF

  v13 = a1;
  if ( (unsigned int)a1 > OFFLINEFILES_EVENT_PREFETCHCLOSEHANDLEEND )
  {
    v14 = a7;
    Error = -2147024809;
    v16 = a6;
    goto LABEL_56;
  }
  TargetHandle = 0;
  v17 = 0;
  if ( !a4
    || (StringCopy = CscUtil_CreateStringCopy(a4, (unsigned __int16 **)&TargetHandle),
        v17 = TargetHandle,
        Error = StringCopy,
        StringCopy >= 0) )
  {
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v21 = GetCurrentProcess();
    if ( DuplicateHandle(v21, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u)
      || (Error = ResultFromLastError(), Error >= 0) )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
          hSourceHandle,
          TargetHandle);
      pDestinationSid[0] = 0;
      if ( !IsValidSid(pSid) )
      {
        Error = -2147023559;
LABEL_13:
        v14 = a7;
        v16 = a6;
LABEL_14:
        if ( TargetHandle )
        {
          CloseHandle(TargetHandle);
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
              TargetHandle);
          }
        }
        goto LABEL_54;
      }
      LengthSid = GetLengthSid(pSid);
      Error = CscUtil_HeapAlloc(LengthSid, 1, pDestinationSid, v23);
      if ( Error < 0 )
        goto LABEL_13;
      v24 = pDestinationSid[0];
      if ( !CopySid(LengthSid, pDestinationSid[0], pSid) )
      {
        Error = ResultFromLastError();
        CscUtil_HeapFree(v24, v25);
        v24 = 0;
        if ( Error < 0 )
          goto LABEL_13;
      }
      v47 = 0;
      if ( CscUmpLibraryState )
      {
        SidIndex = CscDriverGetSidIndex(pSid, &v47);
        if ( SidIndex >= 0 )
          goto LABEL_27;
      }
      else
      {
        SidIndex = -1073741436;
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_640353d05de230bd321f309b7bf8540c_Traceguids,
          (unsigned int)SidIndex);
LABEL_27:
      v27 = RtlNtStatusToDosError(SidIndex);
      Error = v27;
      if ( v27 > 0 )
        Error = (unsigned __int16)v27 | 0x80070000;
      if ( Error >= 0 )
      {
        pDestinationSid[0] = 0;
        Error = CLinkPool<EVENT_CONNECTION>::_GetNextFreeEntry(v29, pDestinationSid);
        if ( Error >= 0 )
        {
          Error = -2147467259;
          Offset = EventSinkArray_GetOffset(a3);
          v32 = (void **)pDestinationSid[0];
          v33 = Offset;
          if ( Offset != -1 )
          {
            v34 = EventSinkArray_GetOffset(&IID_IOfflineFilesEvents);
            if ( v34 < 4 )
            {
              Error = EventDispatcher_QueryEventSinkInterface(a2, &IID_IOfflineFilesEvents, &v32[v34 + 5]);
              if ( Error >= 0 )
              {
                if ( !v33
                  || (v35 = EventSinkArray_GetOffset(&IID_IOfflineFilesEvents2), v35 >= 4)
                  || (Error = EventDispatcher_QueryEventSinkInterface(a2, &IID_IOfflineFilesEvents2, &v32[v35 + 5]),
                      Error >= 0) )
                {
                  if ( v33 < 2
                    || (v36 = EventSinkArray_GetOffset(&IID_IOfflineFilesEvents3), v36 >= 4)
                    || (Error = EventDispatcher_QueryEventSinkInterface(a2, &IID_IOfflineFilesEvents3, &v32[v36 + 5]),
                        Error >= 0) )
                  {
                    if ( v33 >= 3 )
                    {
                      v37 = EventSinkArray_GetOffset(&IID_IOfflineFilesEvents4);
                      if ( v37 < 4 )
                        Error = EventDispatcher_QueryEventSinkInterface(a2, &IID_IOfflineFilesEvents4, &v32[v37 + 5]);
                    }
                  }
                }
              }
            }
          }
          if ( Error >= 0 )
          {
            *((_DWORD *)v32 + 8) = a6;
            *((_DWORD *)v32 + 4) = a7;
            *((_DWORD *)v32 + 5) = a8;
            v32[3] = (void *)a9;
            v32[9] = v17;
            *((_DWORD *)v32 + 20) = a5;
            v32[11] = TargetHandle;
            v32[12] = v24;
            *((_WORD *)v32 + 52) = v47;
            ++LODWORD((&g_rgEvents)[7 * a1]);
            v38 = &qword_1800B6020[7 * a1];
            v39 = (void ***)v38[1];
            *v32 = v38;
            v32[1] = v39;
            *v39 = v32;
            v38[1] = (__int64)v32;
            EnterCriticalSection(&g_csEventDispatcherLock);
            if ( ++dword_1800B8268 > dword_1800B826C )
              dword_1800B826C = dword_1800B8268;
            LeaveCriticalSection(&g_csEventDispatcherLock);
            if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              v16 = a6;
              v14 = a7;
            }
            else
            {
              PathFilterMatchName(a5);
              v40 = (unsigned int)EventName(a1);
              v14 = a7;
              v16 = a6;
              WPP_SF_SddddSS(*(_QWORD *)(v41 + 16), v47, v42, v40, a6, a7, a8, v47, v43, v42);
            }
            v24 = 0;
            TargetHandle = 0;
            v17 = 0;
            goto LABEL_53;
          }
          CLinkPool<EVENT_CONNECTION>::_FreeEntry(v31, v32);
        }
      }
      v14 = a7;
      v16 = a6;
LABEL_53:
      CscUtil_HeapFree(v24, v28);
      goto LABEL_14;
    }
  }
  v14 = a7;
  v16 = a6;
LABEL_54:
  CscUtil_HeapFree(v17, v19);
  if ( Error >= 0 )
    return (unsigned int)Error;
  v13 = a1;
LABEL_56:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v44 = (unsigned int)EventName(v13);
    WPP_SF_SddD(*(_QWORD *)(v45 + 16), 27, v45, v44, v16, v14, Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000cf58  mov     [rsp-40h+arg_0], ecx
0x18000cf5c  push    rbp
0x18000cf5d  push    rbx
0x18000cf5e  push    rsi
0x18000cf5f  push    rdi
0x18000cf60  push    r12
0x18000cf62  push    r13
0x18000cf64  push    r14
0x18000cf66  push    r15
0x18000cf68  mov     rbp, rsp
0x18000cf6b  sub     rsp, 78h
0x18000cf6f  lea     r15, WPP_GLOBAL_Control
0x18000cf76  mov     r13, r8
0x18000cf79  mov     r12, rdx
0x18000cf7c  mov     eax, ecx
0x18000cf7e  cmp     ecx, 26h ; '&'
0x18000cf81  jbe     short loc_18000CF94
0x18000cf83  mov     edi, [rbp+arg_30]
0x18000cf86  mov     ebx, 80070057h
0x18000cf8b  mov     r14d, [rbp+arg_28]
0x18000cf8f  jmp     loc_18000D3F7
0x18000cf94  xor     r14d, r14d
0x18000cf97  mov     [rbp+TargetHandle], r14
0x18000cf9b  mov     esi, r14d
0x18000cf9e  test    r9, r9
0x18000cfa1  jz      short loc_18000CFB9
0x18000cfa3  lea     rdx, [rbp+TargetHandle]; unsigned __int16 **
0x18000cfa7  mov     rcx, r9; unsigned __int16 *
0x18000cfaa  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x18000cfaf  mov     rsi, [rbp+TargetHandle]
0x18000cfb3  mov     ebx, eax
0x18000cfb5  test    eax, eax
0x18000cfb7  js      short loc_18000D004
0x18000cfb9  mov     [rbp+TargetHandle], r14
0x18000cfbd  call    cs:__imp_GetCurrentProcess
0x18000cfc3  mov     rbx, rax
0x18000cfc6  call    cs:__imp_GetCurrentProcess
0x18000cfcc  mov     rdx, [rbp+hSourceHandle]; hSourceHandle
0x18000cfd3  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000cfd7  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18000cfdf  mov     rcx, rax; hSourceProcessHandle
0x18000cfe2  mov     [rsp+78h+bInheritHandle], r14d; bInheritHandle
0x18000cfe7  mov     r8, rbx; hTargetProcessHandle
0x18000cfea  mov     [rsp+78h+dwDesiredAccess], r14d; dwDesiredAccess
0x18000cfef  call    cs:__imp_DuplicateHandle
0x18000cff5  test    eax, eax
0x18000cff7  jnz     short loc_18000D010
0x18000cff9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000cffe  mov     ebx, eax
0x18000d000  test    eax, eax
0x18000d002  jns     short loc_18000D010
0x18000d004  mov     edi, [rbp+arg_30]
0x18000d007  mov     r14d, [rbp+arg_28]
0x18000d00b  jmp     loc_18000D3E8
0x18000d010  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d017  cmp     rcx, r15
0x18000d01a  jz      short loc_18000D047
0x18000d01c  test    byte ptr [rcx+1Ch], 8
0x18000d020  jz      short loc_18000D047
0x18000d022  mov     rax, [rbp+TargetHandle]
0x18000d026  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000d02d  mov     r9, [rbp+hSourceHandle]
0x18000d034  mov     edx, 18h
0x18000d039  mov     rcx, [rcx+10h]
0x18000d03d  mov     qword ptr [rsp+78h+dwDesiredAccess], rax
0x18000d042  call    WPP_SF_qq
0x18000d047  mov     rdi, [rbp+pSid]
0x18000d04e  mov     rcx, rdi; pSid
0x18000d051  mov     [rbp+pDestinationSid], r14
0x18000d055  call    cs:__imp_IsValidSid
0x18000d05b  test    eax, eax
0x18000d05d  jnz     short loc_18000D0BD
0x18000d05f  mov     ebx, 80070539h
0x18000d064  mov     edi, [rbp+arg_30]
0x18000d067  mov     r14d, [rbp+arg_28]
0x18000d06b  mov     rcx, [rbp+TargetHandle]; hObject
0x18000d06f  test    rcx, rcx
0x18000d072  jz      loc_18000D3E1
0x18000d078  call    cs:__imp_CloseHandle
0x18000d07e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d085  lea     r15, WPP_GLOBAL_Control
0x18000d08c  cmp     rcx, r15
0x18000d08f  jz      loc_18000D3E8
0x18000d095  test    byte ptr [rcx+1Ch], 8
0x18000d099  jz      loc_18000D3E8
0x18000d09f  mov     r9, [rbp+TargetHandle]
0x18000d0a3  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18000d0aa  mov     rcx, [rcx+10h]
0x18000d0ae  mov     edx, 1Ah
0x18000d0b3  call    WPP_SF_q
0x18000d0b8  jmp     loc_18000D3E8
0x18000d0bd  mov     rcx, rdi; pSid
0x18000d0c0  call    cs:__imp_GetLengthSid
0x18000d0c6  mov     ecx, eax; dwBytes
0x18000d0c8  lea     r8, [rbp+pDestinationSid]; void **
0x18000d0cc  mov     edx, 1; int
0x18000d0d1  mov     r14d, eax
0x18000d0d4  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18000d0d9  mov     ebx, eax
0x18000d0db  test    eax, eax
0x18000d0dd  js      short loc_18000D064
0x18000d0df  mov     r15, [rbp+pDestinationSid]
0x18000d0e3  mov     r8, rdi; pSourceSid
0x18000d0e6  mov     rdx, r15; pDestinationSid
0x18000d0e9  mov     ecx, r14d; nDestinationSidLength
0x18000d0ec  call    cs:__imp_CopySid
0x18000d0f2  xor     r14d, r14d
0x18000d0f5  test    eax, eax
0x18000d0f7  jnz     short loc_18000D113
0x18000d0f9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000d0fe  mov     rcx, r15; lpMem
0x18000d101  mov     ebx, eax
0x18000d103  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000d108  mov     r15d, r14d
0x18000d10b  test    ebx, ebx
0x18000d10d  js      loc_18000D064
0x18000d113  cmp     cs:CscUmpLibraryState, r14d
0x18000d11a  mov     [rbp+var_28], r14w
0x18000d11f  jnz     short loc_18000D128
0x18000d121  mov     ebx, 0C0000184h
0x18000d126  jmp     short loc_18000D13A
0x18000d128  lea     rdx, [rbp+var_28]; PVOID
0x18000d12c  mov     rcx, rdi; Src
0x18000d12f  call    CscDriverGetSidIndex
0x18000d134  mov     ebx, eax
0x18000d136  test    eax, eax
0x18000d138  jns     short loc_18000D16B
0x18000d13a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d141  lea     rax, WPP_GLOBAL_Control
0x18000d148  cmp     rcx, rax
0x18000d14b  jz      short loc_18000D16B
0x18000d14d  test    byte ptr [rcx+1Ch], 2
0x18000d151  jz      short loc_18000D16B
0x18000d153  mov     rcx, [rcx+10h]
0x18000d157  lea     r8, WPP_640353d05de230bd321f309b7bf8540c_Traceguids
0x18000d15e  mov     edx, 47h ; 'G'
0x18000d163  mov     r9d, ebx
0x18000d166  call    WPP_SF_d
0x18000d16b  mov     ecx, ebx; Status
0x18000d16d  call    cs:__imp_RtlNtStatusToDosError
0x18000d173  mov     ebx, eax
0x18000d175  test    eax, eax
0x18000d177  jle     short loc_18000D182
0x18000d179  movzx   ebx, ax
0x18000d17c  or      ebx, 80070000h
0x18000d182  test    ebx, ebx
0x18000d184  js      loc_18000D3CD
0x18000d18a  lea     rdx, [rbp+pDestinationSid]
0x18000d18e  mov     [rbp+pDestinationSid], r14
0x18000d192  call    ?_GetNextFreeEntry@?$CLinkPool@UEVENT_CONNECTION@@@@AEAAJPEAPEAUEVENT_CONNECTION@@@Z; CLinkPool<EVENT_CONNECTION>::_GetNextFreeEntry(EVENT_CONNECTION * *)
0x18000d197  mov     ebx, eax
0x18000d199  test    eax, eax
0x18000d19b  js      loc_18000D3CD
0x18000d1a1  mov     rcx, r13; struct _GUID *
0x18000d1a4  mov     ebx, 80004005h
0x18000d1a9  call    ?EventSinkArray_GetOffset@@YAKAEBU_GUID@@@Z; EventSinkArray_GetOffset(_GUID const &)
0x18000d1ae  mov     rdi, [rbp+pDestinationSid]
0x18000d1b2  mov     r14d, eax
0x18000d1b5  cmp     eax, 0FFFFFFFFh
0x18000d1b8  jz      loc_18000D294
0x18000d1be  lea     rcx, IID_IOfflineFilesEvents; struct _GUID *
0x18000d1c5  call    ?EventSinkArray_GetOffset@@YAKAEBU_GUID@@@Z; EventSinkArray_GetOffset(_GUID const &)
0x18000d1ca  cmp     eax, 4
0x18000d1cd  jnb     loc_18000D294
0x18000d1d3  mov     ecx, eax
0x18000d1d5  lea     rdx, IID_IOfflineFilesEvents; struct _GUID *
0x18000d1dc  add     rcx, 5
0x18000d1e0  lea     r8, [rdi+rcx*8]; void **
0x18000d1e4  mov     rcx, r12; struct IUnknown *
0x18000d1e7  call    ?EventDispatcher_QueryEventSinkInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; EventDispatcher_QueryEventSinkInterface(IUnknown *,_GUID const &,void * *)
0x18000d1ec  mov     ebx, eax
0x18000d1ee  test    eax, eax
0x18000d1f0  js      loc_18000D294
0x18000d1f6  cmp     r14d, 1
0x18000d1fa  jb      short loc_18000D22C
0x18000d1fc  lea     rcx, IID_IOfflineFilesEvents2; struct _GUID *
0x18000d203  call    ?EventSinkArray_GetOffset@@YAKAEBU_GUID@@@Z; EventSinkArray_GetOffset(_GUID const &)
0x18000d208  cmp     eax, 4
0x18000d20b  jnb     short loc_18000D22C
0x18000d20d  mov     eax, eax
0x18000d20f  lea     rdx, IID_IOfflineFilesEvents2; struct _GUID *
0x18000d216  add     rax, 5
0x18000d21a  mov     rcx, r12; struct IUnknown *
0x18000d21d  lea     r8, [rdi+rax*8]; void **
0x18000d221  call    ?EventDispatcher_QueryEventSinkInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; EventDispatcher_QueryEventSinkInterface(IUnknown *,_GUID const &,void * *)
0x18000d226  mov     ebx, eax
0x18000d228  test    eax, eax
0x18000d22a  js      short loc_18000D294
0x18000d22c  cmp     r14d, 2
0x18000d230  jb      short loc_18000D262
0x18000d232  lea     rcx, IID_IOfflineFilesEvents3; struct _GUID *
0x18000d239  call    ?EventSinkArray_GetOffset@@YAKAEBU_GUID@@@Z; EventSinkArray_GetOffset(_GUID const &)
0x18000d23e  cmp     eax, 4
0x18000d241  jnb     short loc_18000D262
0x18000d243  mov     eax, eax
0x18000d245  lea     rdx, IID_IOfflineFilesEvents3; struct _GUID *
0x18000d24c  add     rax, 5
0x18000d250  mov     rcx, r12; struct IUnknown *
0x18000d253  lea     r8, [rdi+rax*8]; void **
0x18000d257  call    ?EventDispatcher_QueryEventSinkInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; EventDispatcher_QueryEventSinkInterface(IUnknown *,_GUID const &,void * *)
0x18000d25c  mov     ebx, eax
0x18000d25e  test    eax, eax
0x18000d260  js      short loc_18000D294
0x18000d262  cmp     r14d, 3
0x18000d266  jb      short loc_18000D294
0x18000d268  lea     rcx, IID_IOfflineFilesEvents4; struct _GUID *
0x18000d26f  call    ?EventSinkArray_GetOffset@@YAKAEBU_GUID@@@Z; EventSinkArray_GetOffset(_GUID const &)
0x18000d274  cmp     eax, 4
0x18000d277  jnb     short loc_18000D294
0x18000d279  mov     eax, eax
0x18000d27b  lea     rdx, IID_IOfflineFilesEvents4; struct _GUID *
0x18000d282  add     rax, 5
0x18000d286  mov     rcx, r12; struct IUnknown *
0x18000d289  lea     r8, [rdi+rax*8]; void **
0x18000d28d  call    ?EventDispatcher_QueryEventSinkInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; EventDispatcher_QueryEventSinkInterface(IUnknown *,_GUID const &,void * *)
0x18000d292  mov     ebx, eax
0x18000d294  test    ebx, ebx
0x18000d296  js      loc_18000D3C5
0x18000d29c  mov     eax, [rbp+arg_28]
0x18000d29f  lea     rdx, ?g_rgEvents@@3PAUEVENT_MAP_ENTRY@@A; EVENT_MAP_ENTRY near * g_rgEvents
0x18000d2a6  movsxd  r13, [rbp+arg_0]
0x18000d2aa  mov     r14d, [rbp+arg_38]
0x18000d2b1  mov     r12d, [rbp+arg_20]
0x18000d2b5  mov     [rdi+20h], eax
0x18000d2b8  mov     eax, [rbp+arg_30]
0x18000d2bb  mov     [rdi+10h], eax
0x18000d2be  mov     rax, qword ptr [rbp+arg_40.LowPart]
0x18000d2c5  mov     [rdi+14h], r14d
0x18000d2c9  mov     [rdi+18h], rax
0x18000d2cd  mov     [rdi+48h], rsi
0x18000d2d1  mov     [rdi+50h], r12d
0x18000d2d5  mov     rax, [rbp+TargetHandle]
0x18000d2d9  mov     [rdi+58h], rax
0x18000d2dd  mov     [rdi+60h], r15
0x18000d2e1  movzx   eax, [rbp+var_28]
0x18000d2e5  mov     [rdi+68h], ax
0x18000d2e9  imul    rcx, r13, 38h ; '8'
0x18000d2ed  inc     dword ptr [rcx+rdx]
0x18000d2f0  add     rdx, 20h ; ' '
0x18000d2f4  add     rcx, rdx
0x18000d2f7  mov     rax, [rcx+8]
0x18000d2fb  mov     [rdi], rcx
0x18000d2fe  mov     [rdi+8], rax
0x18000d302  mov     [rax], rdi
0x18000d305  mov     [rcx+8], rdi
0x18000d309  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d310  call    cs:__imp_EnterCriticalSection
0x18000d316  mov     eax, cs:dword_1800B8268
0x18000d31c  inc     eax
0x18000d31e  cmp     eax, cs:dword_1800B826C
0x18000d324  mov     cs:dword_1800B8268, eax
0x18000d32a  jbe     short loc_18000D332
0x18000d32c  mov     cs:dword_1800B826C, eax
0x18000d332  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d339  call    cs:__imp_LeaveCriticalSection
0x18000d33f  mov     r10, cs:WPP_GLOBAL_Control
0x18000d346  lea     rax, WPP_GLOBAL_Control
0x18000d34d  cmp     r10, rax
0x18000d350  jz      short loc_18000D3AF
0x18000d352  test    byte ptr [r10+1Ch], 10h
0x18000d357  jz      short loc_18000D3AF
0x18000d359  mov     ecx, r12d; enum tagOFFLINEFILES_PATHFILTER_MATCH
0x18000d35c  call    ?PathFilterMatchName@@YAPEBGW4tagOFFLINEFILES_PATHFILTER_MATCH@@@Z; PathFilterMatchName(tagOFFLINEFILES_PATHFILTER_MATCH)
0x18000d361  test    rsi, rsi
0x18000d364  lea     r9, aNone; "<none>"
0x18000d36b  mov     ecx, r13d; enum tagOFFLINEFILES_EVENTS
0x18000d36e  mov     r8, rax
0x18000d371  cmovnz  r9, rsi
0x18000d375  call    ?EventName@@YAPEBGW4tagOFFLINEFILES_EVENTS@@@Z; EventName(tagOFFLINEFILES_EVENTS)
0x18000d37a  movzx   edx, [rbp+var_28]
0x18000d37e  mov     edi, [rbp+arg_30]
0x18000d381  mov     rcx, [r10+10h]
0x18000d385  mov     [rsp+78h+var_30], r8
0x18000d38a  mov     [rsp+78h+var_38], r9
0x18000d38f  mov     r9, rax
0x18000d392  mov     [rsp+78h+var_40], edx
0x18000d396  mov     [rsp+78h+dwOptions], r14d
0x18000d39b  mov     r14d, [rbp+arg_28]
0x18000d39f  mov     [rsp+78h+bInheritHandle], edi
0x18000d3a3  mov     [rsp+78h+dwDesiredAccess], r14d
0x18000d3a8  call    WPP_SF_SddddSS
0x18000d3ad  jmp     short loc_18000D3B6
0x18000d3af  mov     r14d, [rbp+arg_28]
0x18000d3b3  mov     edi, [rbp+arg_30]
0x18000d3b6  xor     r15d, r15d
0x18000d3b9  mov     [rbp+TargetHandle], 0
0x18000d3c1  xor     esi, esi
0x18000d3c3  jmp     short loc_18000D3D4
0x18000d3c5  mov     rdx, rdi
0x18000d3c8  call    ?_FreeEntry@?$CLinkPool@UEVENT_CONNECTION@@@@AEAAXPEAUEVENT_CONNECTION@@@Z; CLinkPool<EVENT_CONNECTION>::_FreeEntry(EVENT_CONNECTION *)
0x18000d3cd  mov     edi, [rbp+arg_30]
0x18000d3d0  mov     r14d, [rbp+arg_28]
0x18000d3d4  mov     rcx, r15; lpMem
0x18000d3d7  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000d3dc  jmp     loc_18000D06B
0x18000d3e1  lea     r15, WPP_GLOBAL_Control
0x18000d3e8  mov     rcx, rsi; lpMem
0x18000d3eb  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000d3f0  test    ebx, ebx
0x18000d3f2  jns     short loc_18000D42F
  ... truncated ...
```
