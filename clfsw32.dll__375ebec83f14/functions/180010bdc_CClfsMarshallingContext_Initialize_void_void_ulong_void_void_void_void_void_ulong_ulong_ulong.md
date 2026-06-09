# CClfsMarshallingContext::Initialize(void *,void * (*)(ulong,void *),void (*)(void *,void *),void *,ulong,ulong,ulong)

- ea: `0x180010bdc`
- end: `0x180011254`
- name: `?Initialize@CClfsMarshallingContext@@QEAAKPEAXP6APEAXK0@ZP6AX00@Z0KKK@Z`
- size: `1656`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, HANDLE hSourceHandle@<rdx>, void *(*)(unsigned int, void *)@<r8>, void (*)(void *, void *)@<r9>, void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a7e0`
- `0x18000aec0`
- `0x18000d500`

## callees

- `0x1800018a4`
- `0x18000b940`
- `0x18000df4c`
- `0x18000e750`
- `0x18001031c`
- `0x180010bdc`
- `0x18001125c`
- `0x180014dce`
- `0x180014e00`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180010d5e`
- `ntdll!NtQueryInformationFile` at `0x180010d5e`
- `ntdll!RtlNtStatusToDosError` at `0x180010d6e`
- `ntdll!RtlNtStatusToDosError` at `0x180011145`
- `ntdll!RtlNtStatusToDosError` at `0x180010d6e`
- `ntdll!RtlNtStatusToDosError` at `0x180011145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010c6c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011164`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011164`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ecc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ecc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f11`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800110fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800110fe`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010e9e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010e9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010c38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010c38`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001106f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001106f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001112a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001112a`

## pseudocode

```c
ULONG __fastcall CClfsMarshallingContext::Initialize(
        CClfsMarshallingContext *this,
        HANDLE hSourceHandle,
        void *(*a3)(unsigned int, void *),
        void (*a4)(void *, void *),
        void *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  HANDLE CurrentProcess; // rbx
  ULONG result; // eax
  void *v14; // rcx
  ULONG SectorSize; // ecx
  unsigned int v16; // r15d
  void *v17; // rcx
  DWORD LastError; // ebx
  _OWORD *v19; // rax
  unsigned int v20; // r8d
  void *v21; // r9
  CLogIocb *v22; // rsi
  unsigned int v23; // r14d
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rax
  void *v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // r14
  int v29; // eax
  unsigned int v30; // esi
  struct CLogIocb *v31; // r13
  unsigned __int64 v32; // rsi
  unsigned __int64 EventA; // rax
  void *v34; // rcx
  int v35; // edx
  unsigned int v36; // ecx
  unsigned int v37; // r8d
  unsigned int v38; // ecx
  void *dwOptions; // [rsp+30h] [rbp-D0h]
  ULONG cbBuffer; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-98h] BYREF
  _QWORD InBuffer[7]; // [rsp+88h] [rbp-78h] BYREF
  ULONG v46; // [rsp+C0h] [rbp-40h]
  char v47; // [rsp+C4h] [rbp-3Ch]
  CLFS_INFORMATION pinfoBuffer; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  cbBuffer = 120;
  CurrentProcess = GetCurrentProcess();
  *((_DWORD *)this + 24) = GetCurrentProcessId();
  if ( !DuplicateHandle(CurrentProcess, hSourceHandle, CurrentProcess, (LPHANDLE)this + 6, 0, 1, 2u) )
    return GetLastError();
  v14 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 7) = hSourceHandle;
  cbBuffer = 120;
  if ( !GetLogFileInformation(v14, &pinfoBuffer, &cbBuffer) )
    return GetLastError();
  if ( !pinfoBuffer.TotalContainers )
    return 6635;
  SectorSize = pinfoBuffer.SectorSize;
  *((_QWORD *)this + 21) = pinfoBuffer.ContainerSize;
  *((_DWORD *)this + 26) = pinfoBuffer.Attributes;
  *((_QWORD *)this + 25) = pinfoBuffer.LastLsn.ullOffset;
  *((_QWORD *)this + 28) = pinfoBuffer.RestartLsn.ullOffset;
  *((_DWORD *)this + 34) = SectorSize;
  if ( SectorSize )
    v16 = -SectorSize & (SectorSize + a6 - 1);
  else
    v16 = 0;
  v17 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 11) = a5;
  *((_DWORD *)this + 30) = a7;
  *((_DWORD *)this + 31) = a8;
  *((_QWORD *)this + 9) = a3;
  *((_QWORD *)this + 10) = a4;
  *((_DWORD *)this + 32) = v16;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  NtQueryInformationFile(v17, &IoStatusBlock, (char *)this + 156, 4u, FileModeInformation);
  result = RtlNtStatusToDosError(IoStatusBlock.Status);
  if ( !result )
  {
    LastError = 8;
    while ( 1 )
    {
      v19 = HeapAlloc(g_hHeap, 8u, 0xE0u);
      v22 = (CLogIocb *)v19;
      if ( !v19 )
        goto LABEL_17;
      *((_DWORD *)v19 + 6) = 0;
      *((_WORD *)v19 + 14) = 0;
      *((_QWORD *)v19 + 8) = 0;
      *((_QWORD *)v19 + 9) = 0;
      *((_QWORD *)v19 + 10) = 0;
      *((_QWORD *)v19 + 13) = 0;
      *((_QWORD *)v19 + 14) = 0;
      *((_QWORD *)v19 + 15) = 0;
      *((_DWORD *)v19 + 32) = 0;
      *((CLFS_LSN *)v19 + 17) = CLFS_LSN_INVALID;
      *((CLFS_LSN *)v19 + 18) = CLFS_LSN_INVALID;
      *((CLFS_LSN *)v19 + 19) = CLFS_LSN_NULL;
      *((CLFS_LSN *)v19 + 20) = CLFS_LSN_NULL;
      *((CLFS_LSN *)v19 + 22) = CLFS_LSN_NULL;
      *((CLFS_LSN *)v19 + 23) = CLFS_LSN_INVALID;
      *((_QWORD *)v19 + 24) = 0;
      *((_QWORD *)v19 + 25) = 0;
      *((_QWORD *)v19 + 26) = 0;
      *((_QWORD *)v19 + 27) = 0;
      v19[2] = 0;
      hDevice = v19;
      v19[3] = 0;
      *(_OWORD *)((char *)v19 + 88) = 0;
      *v19 = 0;
      v23 = CLogIocb::Initialize(
              (CLogIocb *)v19,
              this,
              v20,
              v21,
              *((void *(**)(unsigned int, void *))this + 9),
              *((void (**)(void *, void *))this + 10),
              dwOptions);
      if ( v23 )
      {
        CLogIocb::~CLogIocb(v22);
        if ( !HeapFree(g_hHeap, 0, v22) )
          GetLastError();
        return v23;
      }
      if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 8) > *((_DWORD *)this + 9) )
        break;
      InterlockedPushEntrySList((PSLIST_HEADER)this + 1, (PSLIST_ENTRY)v22);
      _InterlockedIncrement((volatile signed __int32 *)this + 11);
    }
    _InterlockedAdd((volatile signed __int32 *)this + 8, 0xFFFFFFFF);
    CLogIocb::~CLogIocb(v22);
    if ( !HeapFree(g_hHeap, 0, v22) )
      GetLastError();
LABEL_17:
    hDevice = 0;
    if ( !*((_DWORD *)this + 8) )
      return LastError;
    v24 = *((unsigned int *)this + 31);
    if ( (_DWORD)v24 )
    {
      v25 = 16 * v24;
      if ( !is_mul_ok(v24, 0x10u) )
        v25 = -1;
      v26 = operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 30) = v26;
      if ( !v26 )
        return 14;
      *((_DWORD *)this + 59) = v24;
      memset_0(v26, 208, 16 * v24);
    }
    else
    {
      *((_DWORD *)this + 59) = 0;
    }
    v27 = v16 + 152;
    if ( v16 + 152 < v16 )
      goto LABEL_65;
    *((_DWORD *)this + 32) = v27;
    v28 = 0;
    if ( !*((_DWORD *)this + 31) )
      goto LABEL_54;
    v29 = *((_DWORD *)this + 34);
    if ( v29 )
      v30 = -v29 & (v27 + v29 + 983);
    else
      v30 = 0;
    result = CClfsMarshallingContext::AllocateIocbNaked(this, (struct CLogIocb **)&hDevice);
    if ( !result )
    {
      v28 = v30;
      BytesReturned = 0;
      memset(&Overlapped, 0, sizeof(Overlapped));
      memset_0(InBuffer, 0, 0x40u);
      v31 = (struct CLogIocb *)hDevice;
      IoStatusBlock.Pointer = (PVOID)CLFS_LSN_INVALID.ullOffset;
      if ( this == (CClfsMarshallingContext *)-192LL
        || this == (CClfsMarshallingContext *)-200LL
        || *((__int64 *)this + 24) < 0 )
      {
        LastError = 87;
      }
      else
      {
        v32 = *((_QWORD *)hDevice + 7);
        hDevice = (HANDLE)*((_QWORD *)this + 6);
        if ( v32 )
        {
          EventA = v32;
LABEL_41:
          InBuffer[2] = 0;
          Overlapped.hEvent = (HANDLE)(EventA | 1);
          v47 = 0;
          InBuffer[3] = (char *)this + 200;
          LastError = 0;
          InBuffer[0] = v28;
          InBuffer[4] = &IoStatusBlock;
          InBuffer[5] = CLFS_LSN_NULL.ullOffset;
          InBuffer[6] = &pinfoBuffer;
          v46 = cbBuffer;
          InBuffer[1] = (char *)this + 192;
          if ( !DeviceIoControl(hDevice, 0x8007A827, InBuffer, 0x40u, 0, 0, &BytesReturned, &Overlapped) )
          {
            LastError = GetLastError();
            if ( LastError == 997 )
            {
              if ( WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF) )
                LastError = 1117;
              else
                LastError = RtlNtStatusToDosError(Overlapped.Internal);
            }
          }
          v34 = (void *)((unsigned __int64)Overlapped.hEvent & 0xFFFFFFFFFFFFFFFEuLL);
          Overlapped.hEvent = (HANDLE)((unsigned __int64)Overlapped.hEvent & ~1uLL);
          if ( !v32 )
            CloseHandle(v34);
          if ( !LastError )
            cbBuffer = v46;
        }
        else
        {
          EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
          if ( EventA )
            goto LABEL_41;
        }
      }
      CClfsMarshallingContext::FreeIocbNaked(this, v31);
      if ( LastError )
      {
        v28 = 0;
        if ( LastError != 6628 && LastError != 5 )
          return LastError;
      }
LABEL_54:
      v35 = *((_DWORD *)this + 34);
      if ( v35 )
        v36 = -v35 & (v35 + *((_DWORD *)this + 32) - 1);
      else
        v36 = 0;
      if ( v36 >= *((_DWORD *)this + 32) )
      {
        v37 = v16 + 2 * ((v36 >> 9) + 76);
        if ( v37 < v16 )
          goto LABEL_65;
        *((_DWORD *)this + 32) = v37;
        v38 = v35 ? ~(v35 - 1) & (v35 - 1 + v37) : 0;
        if ( v38 >= v37 )
        {
          if ( v38 + 40 >= v38 )
          {
            *((_DWORD *)this + 32) = v38 + 40;
            result = 0;
            *((_DWORD *)this + 33) = v38;
            *((_QWORD *)this + 24) = v28;
            return result;
          }
LABEL_65:
          *((_DWORD *)this + 32) = -1;
        }
      }
      return 1784;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010bdc  mov     [rsp-8+arg_10], rbx
0x180010be1  push    rbp
0x180010be2  push    rsi
0x180010be3  push    rdi
0x180010be4  push    r12
0x180010be6  push    r13
0x180010be8  push    r14
0x180010bea  push    r15
0x180010bec  lea     rbp, [rsp-60h]
0x180010bf1  sub     rsp, 160h
0x180010bf8  mov     rax, cs:__security_cookie
0x180010bff  xor     rax, rsp
0x180010c02  mov     [rbp+90h+var_40], rax
0x180010c06  mov     r12, r8
0x180010c09  mov     rsi, rdx
0x180010c0c  mov     rdi, rcx
0x180010c0f  mov     ebx, 78h ; 'x'
0x180010c14  mov     r8d, ebx; Size
0x180010c17  lea     rcx, [rbp+90h+pinfoBuffer]; void *
0x180010c1b  xor     edx, edx; Val
0x180010c1d  mov     r14, r9
0x180010c20  call    memset_0
0x180010c25  mov     [rsp+190h+cbBuffer], ebx
0x180010c29  call    cs:__imp_GetCurrentProcess
0x180010c30  nop     dword ptr [rax+rax+00h]
0x180010c35  mov     rbx, rax
0x180010c38  call    cs:__imp_GetCurrentProcessId
0x180010c3f  nop     dword ptr [rax+rax+00h]
0x180010c44  mov     [rsp+190h+dwOptions], 2; void *
0x180010c4c  lea     r9, [rdi+30h]; lpTargetHandle
0x180010c50  xor     r13d, r13d
0x180010c53  mov     [rsp+190h+bInheritHandle], 1; bInheritHandle
0x180010c5b  mov     r8, rbx; hTargetProcessHandle
0x180010c5e  mov     [rdi+60h], eax
0x180010c61  mov     rdx, rsi; hSourceHandle
0x180010c64  mov     [rsp+190h+dwDesiredAccess], r13d; dwDesiredAccess
0x180010c69  mov     rcx, rbx; hSourceProcessHandle
0x180010c6c  call    cs:__imp_DuplicateHandle
0x180010c73  nop     dword ptr [rax+rax+00h]
0x180010c78  test    eax, eax
0x180010c7a  jnz     short loc_180010C8D
0x180010c7c  call    cs:__imp_GetLastError
0x180010c83  nop     dword ptr [rax+rax+00h]
0x180010c88  jmp     loc_18001122C
0x180010c8d  mov     rcx, [rdi+30h]; hLog
0x180010c91  lea     r8, [rsp+190h+cbBuffer]; cbBuffer
0x180010c96  lea     rdx, [rbp+90h+pinfoBuffer]; pinfoBuffer
0x180010c9a  mov     [rdi+38h], rsi
0x180010c9e  mov     [rsp+190h+cbBuffer], 78h ; 'x'
0x180010ca6  call    GetLogFileInformation
0x180010cab  test    eax, eax
0x180010cad  jz      short loc_180010C7C
0x180010caf  cmp     [rbp+90h+pinfoBuffer.TotalContainers], r13d
0x180010cb3  jnz     short loc_180010CBF
0x180010cb5  mov     eax, 19EBh
0x180010cba  jmp     loc_18001122C
0x180010cbf  mov     rax, [rbp+90h+pinfoBuffer.ContainerSize]
0x180010cc3  mov     ecx, [rbp+90h+pinfoBuffer.SectorSize]
0x180010cc6  mov     [rdi+0A8h], rax
0x180010ccd  mov     eax, [rbp+90h+pinfoBuffer.Attributes]
0x180010cd0  mov     [rdi+68h], eax
0x180010cd3  mov     rax, qword ptr [rbp+90h+pinfoBuffer.LastLsn]
0x180010cd7  mov     [rdi+0C8h], rax
0x180010cde  mov     rax, qword ptr [rbp+90h+pinfoBuffer.RestartLsn]
0x180010ce2  mov     [rdi+0E0h], rax
0x180010ce9  mov     [rdi+88h], ecx
0x180010cef  test    ecx, ecx
0x180010cf1  jnz     short loc_180010CF8
0x180010cf3  mov     r15d, r13d
0x180010cf6  jmp     short loc_180010D0A
0x180010cf8  mov     r15d, [rbp+90h+arg_28]
0x180010cff  dec     r15d
0x180010d02  add     r15d, ecx
0x180010d05  neg     ecx
0x180010d07  and     r15d, ecx
0x180010d0a  mov     rax, [rbp+90h+arg_20]
0x180010d11  lea     r8, [rdi+9Ch]; FileInformation
0x180010d18  mov     rcx, [rdi+38h]; FileHandle
0x180010d1c  lea     rdx, [rsp+190h+IoStatusBlock]; IoStatusBlock
0x180010d21  mov     [rdi+58h], rax
0x180010d25  mov     r9d, 4; Length
0x180010d2b  mov     eax, [rbp+90h+arg_30]
0x180010d31  mov     [rdi+78h], eax
0x180010d34  mov     eax, [rbp+90h+arg_38]
0x180010d3a  mov     [rdi+7Ch], eax
0x180010d3d  mov     [rdi+48h], r12
0x180010d41  mov     [rdi+50h], r14
0x180010d45  mov     [rdi+80h], r15d
0x180010d4c  mov     qword ptr [rsp+190h+IoStatusBlock], r13
0x180010d51  mov     [rsp+190h+IoStatusBlock.Information], r13
0x180010d56  mov     [rsp+190h+dwDesiredAccess], 10h; FileInformationClass
0x180010d5e  call    cs:__imp_NtQueryInformationFile
0x180010d65  nop     dword ptr [rax+rax+00h]
0x180010d6a  mov     ecx, dword ptr [rsp+190h+IoStatusBlock]; Status
0x180010d6e  call    cs:__imp_RtlNtStatusToDosError
0x180010d75  nop     dword ptr [rax+rax+00h]
0x180010d7a  test    eax, eax
0x180010d7c  jnz     loc_18001122C
0x180010d82  lea     ebx, [rax+8]
0x180010d85  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180010d8c  mov     r8d, 0E0h; dwBytes
0x180010d92  mov     edx, ebx; dwFlags
0x180010d94  call    cs:__imp_HeapAlloc
0x180010d9b  nop     dword ptr [rax+rax+00h]
0x180010da0  or      r12, 0FFFFFFFFFFFFFFFFh
0x180010da4  mov     rsi, rax
0x180010da7  test    rax, rax
0x180010daa  jz      loc_180010EE8
0x180010db0  mov     [rax+18h], r13d
0x180010db4  xorps   xmm0, xmm0
0x180010db7  mov     [rax+1Ch], r13w
0x180010dbc  xorps   xmm1, xmm1
0x180010dbf  mov     [rax+40h], r13
0x180010dc3  mov     rdx, rdi; struct CClfsMarshallingContext *
0x180010dc6  mov     [rax+48h], r13
0x180010dca  mov     rcx, rsi; this
0x180010dcd  mov     [rax+50h], r13
0x180010dd1  mov     [rax+68h], r13
0x180010dd5  mov     [rax+70h], r13
0x180010dd9  mov     [rax+78h], r13
0x180010ddd  mov     [rax+80h], r13d
0x180010de4  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180010deb  mov     [rsi+88h], rax
0x180010df2  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180010df9  mov     [rsi+90h], rax
0x180010e00  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180010e07  mov     [rsi+98h], rax
0x180010e0e  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180010e15  mov     [rsi+0A0h], rax
0x180010e1c  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180010e23  mov     [rsi+0B0h], rax
0x180010e2a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180010e31  mov     [rsi+0B8h], rax
0x180010e38  mov     [rsi+0C0h], r13
0x180010e3f  mov     [rsi+0C8h], r13
0x180010e46  mov     [rsi+0D0h], r13
0x180010e4d  mov     [rsi+0D8h], r13
0x180010e54  movups  xmmword ptr [rsi+20h], xmm0
0x180010e58  mov     [rsp+190h+hDevice], rsi
0x180010e5d  movups  xmmword ptr [rsi+30h], xmm0
0x180010e61  movups  xmmword ptr [rsi+58h], xmm0
0x180010e65  movups  xmmword ptr [rsi], xmm1
0x180010e68  mov     rax, [rdi+50h]
0x180010e6c  mov     qword ptr [rsp+190h+bInheritHandle], rax; void (*)(void *, void *)
0x180010e71  mov     rax, [rdi+48h]
0x180010e75  mov     qword ptr [rsp+190h+dwDesiredAccess], rax; void *(*)(unsigned int, void *)
0x180010e7a  call    ?Initialize@CLogIocb@@QEAAKQEAVCClfsMarshallingContext@@KPEAXP6APEAXK1@ZP6AX11@Z1@Z; CLogIocb::Initialize(CClfsMarshallingContext * const,ulong,void *,void * (*)(ulong,void *),void (*)(void *,void *),void *)
0x180010e7f  mov     r14d, eax
0x180010e82  test    eax, eax
0x180010e84  jnz     short loc_180010EFD
0x180010e86  lea     eax, [r12+2]
0x180010e8b  lock xadd [rdi+20h], eax
0x180010e90  inc     eax
0x180010e92  cmp     eax, [rdi+24h]
0x180010e95  ja      short loc_180010EB3
0x180010e97  mov     rdx, rsi; ListEntry
0x180010e9a  lea     rcx, [rdi+10h]; ListHead
0x180010e9e  call    cs:__imp_InterlockedPushEntrySList
0x180010ea5  nop     dword ptr [rax+rax+00h]
0x180010eaa  lock inc dword ptr [rdi+2Ch]
0x180010eae  jmp     loc_180010D85
0x180010eb3  lock add [rdi+20h], r12d
0x180010eb8  mov     rcx, rsi; this
0x180010ebb  call    ??1CLogIocb@@QEAA@XZ; CLogIocb::~CLogIocb(void)
0x180010ec0  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180010ec7  mov     r8, rsi; lpMem
0x180010eca  xor     edx, edx; dwFlags
0x180010ecc  call    cs:__imp_HeapFree
0x180010ed3  nop     dword ptr [rax+rax+00h]
0x180010ed8  test    eax, eax
0x180010eda  jnz     short loc_180010EE8
0x180010edc  call    cs:__imp_GetLastError
0x180010ee3  nop     dword ptr [rax+rax+00h]
0x180010ee8  mov     rax, r13
0x180010eeb  mov     [rsp+190h+hDevice], rax
0x180010ef0  cmp     [rdi+20h], r13d
0x180010ef4  jnz     short loc_180010F35
0x180010ef6  mov     eax, ebx
0x180010ef8  jmp     loc_18001122C
0x180010efd  mov     rcx, rsi; this
0x180010f00  call    ??1CLogIocb@@QEAA@XZ; CLogIocb::~CLogIocb(void)
0x180010f05  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180010f0c  mov     r8, rsi; lpMem
0x180010f0f  xor     edx, edx; dwFlags
0x180010f11  call    cs:__imp_HeapFree
0x180010f18  nop     dword ptr [rax+rax+00h]
0x180010f1d  test    eax, eax
0x180010f1f  jnz     short loc_180010F2D
0x180010f21  call    cs:__imp_GetLastError
0x180010f28  nop     dword ptr [rax+rax+00h]
0x180010f2d  mov     eax, r14d
0x180010f30  jmp     loc_18001122C
0x180010f35  mov     r14d, [rdi+7Ch]
0x180010f39  test    r14d, r14d
0x180010f3c  jnz     short loc_180010F47
0x180010f3e  mov     [rdi+0ECh], r13d
0x180010f45  jmp     short loc_180010F96
0x180010f47  mov     eax, 10h
0x180010f4c  mov     rsi, r14
0x180010f4f  mul     r14
0x180010f52  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010f59  cmovb   rax, r12
0x180010f5d  mov     rcx, rax; unsigned __int64
0x180010f60  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010f65  mov     [rdi+0F0h], rax
0x180010f6c  test    rax, rax
0x180010f6f  jnz     short loc_180010F7B
0x180010f71  mov     eax, 0Eh
0x180010f76  jmp     loc_18001122C
0x180010f7b  shl     rsi, 4
0x180010f7f  mov     edx, 0D0h; Val
0x180010f84  mov     r8, rsi; Size
0x180010f87  mov     [rdi+0ECh], r14d
0x180010f8e  mov     rcx, rax; void *
0x180010f91  call    memset_0
0x180010f96  lea     ecx, [r15+98h]
0x180010f9d  cmp     ecx, r15d
0x180010fa0  jb      loc_18001121D
0x180010fa6  mov     [rdi+80h], ecx
0x180010fac  mov     r14, r13
0x180010faf  cmp     [rdi+7Ch], r13d
0x180010fb3  jbe     loc_1800111A8
0x180010fb9  mov     eax, [rdi+88h]
0x180010fbf  test    eax, eax
0x180010fc1  jnz     short loc_180010FC8
0x180010fc3  mov     esi, r13d
0x180010fc6  jmp     short loc_180010FD4
0x180010fc8  lea     esi, [rax+3D7h]
0x180010fce  neg     eax
0x180010fd0  add     esi, ecx
0x180010fd2  and     esi, eax
0x180010fd4  lea     rdx, [rsp+190h+hDevice]; struct CLogIocb **
0x180010fd9  mov     rcx, rdi; this
0x180010fdc  call    ?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)
0x180010fe1  test    eax, eax
0x180010fe3  jnz     loc_18001122C
0x180010fe9  xor     edx, edx; Val
0x180010feb  mov     r14d, esi
0x180010fee  lea     r8d, [rax+40h]; Size
0x180010ff2  mov     [rsp+190h+BytesReturned], r13d
0x180010ff7  lea     rcx, [rbp+90h+InBuffer]; void *
0x180010ffb  mov     [rsp+190h+Overlapped.Internal], r13
0x180011000  mov     [rsp+190h+Overlapped.InternalHigh], r13
0x180011005  mov     qword ptr [rsp+190h+Overlapped.10h], r13
0x18001100a  mov     [rbp+90h+Overlapped.hEvent], r13
0x18001100e  call    memset_0
0x180011013  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001101a  lea     r12, [rdi+0C0h]
0x180011021  mov     r13, [rsp+190h+hDevice]
0x180011026  xor     ecx, ecx; lpEventAttributes
0x180011028  mov     qword ptr [rsp+190h+IoStatusBlock], rax
0x18001102d  test    r12, r12
0x180011030  jz      loc_18001117D
0x180011036  lea     rax, [rdi+0C8h]
0x18001103d  test    rax, rax
0x180011040  jz      loc_18001117D
0x180011046  cmp     [r12], rcx
0x18001104a  jl      loc_18001117D
0x180011050  mov     rsi, [r13+38h]
0x180011054  mov     rax, [rdi+30h]
0x180011058  mov     [rsp+190h+hDevice], rax
0x18001105d  test    rsi, rsi
0x180011060  jz      short loc_180011067
0x180011062  mov     rax, rsi
0x180011065  jmp     short loc_180011086
0x180011067  xor     r9d, r9d; lpName
0x18001106a  xor     r8d, r8d; bInitialState
0x18001106d  xor     edx, edx; bManualReset
0x18001106f  call    cs:__imp_CreateEventA
0x180011076  nop     dword ptr [rax+rax+00h]
0x18001107b  xor     ecx, ecx
0x18001107d  test    rax, rax
0x180011080  jz      loc_180011182
0x180011086  or      rax, 1
0x18001108a  mov     [rbp+90h+var_F8], rcx
0x18001108e  mov     [rbp+90h+Overlapped.hEvent], rax
0x180011092  lea     r8, [rbp+90h+InBuffer]; lpInBuffer
0x180011096  lea     rax, [rdi+0C8h]
0x18001109d  mov     [rbp+90h+var_CC], cl
0x1800110a0  mov     [rbp+90h+var_F0], rax
0x1800110a4  mov     ebx, ecx
0x1800110a6  lea     rax, [rsp+190h+IoStatusBlock]
0x1800110ab  mov     [rbp+90h+InBuffer], r14
0x1800110af  mov     [rbp+90h+var_E8], rax
0x1800110b3  mov     r9d, 40h ; '@'; nInBufferSize
0x1800110b9  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1800110c0  mov     edx, 8007A827h; dwIoControlCode
0x1800110c5  mov     [rbp+90h+var_E0], rax
0x1800110c9  lea     rax, [rbp+90h+pinfoBuffer]
0x1800110cd  mov     [rbp+90h+var_D8], rax
0x1800110d1  mov     eax, [rsp+190h+cbBuffer]
0x1800110d5  mov     [rbp+90h+var_D0], eax
0x1800110d8  lea     rax, [rsp+190h+Overlapped]
0x1800110dd  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x1800110e2  lea     rax, [rsp+190h+BytesReturned]
0x1800110e7  mov     qword ptr [rsp+190h+dwOptions], rax; lpBytesReturned
0x1800110ec  mov     [rsp+190h+bInheritHandle], ecx; nOutBufferSize
0x1800110f0  mov     qword ptr [rsp+190h+dwDesiredAccess], rcx; lpOutBuffer
0x1800110f5  mov     rcx, [rsp+190h+hDevice]; hDevice
0x1800110fa  mov     [rbp+90h+var_100], r12
  ... truncated ...
```
