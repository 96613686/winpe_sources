# DownstreamTransport::DownloadFileAsync(_FRS_RDC_FILEINFO const *,uchar *,ulong,ulong,int,AllocateFileSizeWriter &,int const volatile &,void * *)

- ea: `0x1401a68ec`
- end: `0x1401a6c6c`
- name: `?DownloadFileAsync@DownstreamTransport@@QEAAPEAVFrsStatus@@PEBU_FRS_RDC_FILEINFO@@PEAEKKHAEAVAllocateFileSizeWriter@@AEDHPEAPEAX@Z`
- size: `896`
- prototype: `struct FrsStatus *__fastcall(DownstreamTransport *__hidden this, const struct _FRS_RDC_FILEINFO *, unsigned __int8 *, unsigned int, unsigned int, int, struct AllocateFileSizeWriter *, const volatile int *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1401a6450`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x140012440`
- `0x1400391c4`
- `0x1401a68ec`
- `0x1401a82ac`
- `0x1401ac200`
- `0x1401ad1a8`
- `0x1401ae578`
- `0x1401af668`
- `0x1401b3140`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401a697b`
- `KERNEL32!GetCurrentThreadId` at `0x1401a69d2`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6a88`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6b8a`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6bf7`
- `KERNEL32!GetCurrentThreadId` at `0x1401a697b`
- `KERNEL32!GetCurrentThreadId` at `0x1401a69d2`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6a88`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6b8a`
- `KERNEL32!GetCurrentThreadId` at `0x1401a6bf7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1401a6a7a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1401a6a7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall DownstreamTransport::DownloadFileAsync(
        DownstreamTransport *this,
        const struct _FRS_RDC_FILEINFO *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        struct AllocateFileSizeWriter *a7,
        volatile int *a8,
        void **a9)
{
  __int64 v12; // rsi
  RPCNOTIFICATION_ROUTINE *v13; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  struct FrsStatus *v16; // rdi
  DWORD v17; // eax
  __int64 v18; // rcx
  unsigned __int8 *v19; // r14
  RPC_STATUS v20; // edi
  DWORD v21; // eax
  int v22; // r8d
  RPCNOTIFICATION_ROUTINE *EventOrDie; // rax
  DownstreamTransport *v24; // r12
  int FileDataAsync; // ebx
  DWORD v26; // eax
  int v27; // r8d
  DWORD v28; // eax
  __int64 v29; // rcx
  int v31; // [rsp+30h] [rbp-D0h]
  DownstreamTransport *p_pAsync; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v33; // [rsp+58h] [rbp-A8h]
  RPCNOTIFICATION_ROUTINE *v34; // [rsp+60h] [rbp-A0h] BYREF
  void **v35; // [rsp+68h] [rbp-98h]
  volatile int *v36; // [rsp+70h] [rbp-90h]
  const wchar_t *v37; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v40; // [rsp+88h] [rbp-78h]
  _OWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-50h] BYREF

  v33 = a3;
  p_pAsync = this;
  v36 = a8;
  v35 = a9;
  memset_0(&pAsync, 0, sizeof(pAsync));
  memset(v41, 0, sizeof(v41));
  v12 = 0;
  v13 = 0;
  v34 = 0;
  if ( *((_DWORD *)this + 137) < 0x50001u
    && (CurrentThreadId = GetCurrentThreadId(),
        (v16 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v15,
                                     9050,
                                     0,
                                     3,
                                     "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                     "DownstreamTransport::DownloadFileAsync",
                                     6345,
                                     CurrentThreadId,
                                     0)) != 0)
    || a5 > a4
    && (v17 = GetCurrentThreadId(),
        (v16 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v18,
                                     13,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                     "DownstreamTransport::DownloadFileAsync",
                                     6349,
                                     v17,
                                     0)) != 0)
    || (v16 = (struct FrsStatus *)(*(__int64 (__fastcall **)(struct AllocateFileSizeWriter *, _QWORD, _QWORD))(*(_QWORD *)a7 + 40LL))(
                                    a7,
                                    *(_QWORD *)a2,
                                    *((_QWORD *)a2 + 1))) != 0 )
  {
    v19 = v33;
  }
  else
  {
    v19 = v33;
    v16 = (struct FrsStatus *)WriteBack(a7, v33);
  }
  if ( !a6 )
  {
    if ( v16
      || (v20 = RpcAsyncInitializeHandle(&pAsync, 0x70u),
          v21 = GetCurrentThreadId(),
          (v16 = (struct FrsStatus *)LogTranslatedRemoteError(
                                       v20,
                                       v20 == 1237,
                                       v22,
                                       (unsigned int)"DownstreamTransport::DownloadFileAsync",
                                       6367,
                                       v21,
                                       v31,
                                       0)) != 0) )
    {
      v24 = p_pAsync;
    }
    else
    {
      EventOrDie = (RPCNOTIFICATION_ROUTINE *)CreateEventOrDie(0, 0);
      if ( EventOrDie )
        v13 = EventOrDie;
      v34 = v13;
      v24 = p_pAsync;
      v16 = BandwidthThrottler::ThrottleBytes((DownstreamTransport *)((char *)p_pAsync + 176), 0x78u, 0, 0);
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v37 = L"DownstreamTransport::DownloadFileAsync";
      v38 = 6380;
      v39 = 5;
      v40 = L"DOWN";
      p_pAsync = (DownstreamTransport *)&pAsync;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v37, L"rpcAsyncState:%p", &p_pAsync);
    }
    if ( v16 )
      goto LABEL_23;
    pAsync.UserInfo = 0;
    pAsync.NotificationType = RpcNotificationTypeEvent;
    pAsync.u.APC.NotificationRoutine = v13;
    FileDataAsync = RpcRawGetFileDataAsync(&pAsync, *v35, v41);
    v26 = GetCurrentThreadId();
    v16 = (struct FrsStatus *)LogTranslatedRemoteError(
                                FileDataAsync,
                                FileDataAsync == 1237,
                                v27,
                                (unsigned int)"DownstreamTransport::DownloadFileAsync",
                                6390,
                                v26,
                                v31,
                                0);
    if ( v16 )
      goto LABEL_23;
    v16 = DownstreamTransport::RpcAsyncPipeDownload(v24, &pAsync, (struct ASYNC_pipe_BYTE_PIPE *)v41, v19, a4, a7, v36);
  }
  if ( v16 )
  {
LABEL_23:
    v28 = GetCurrentThreadId();
    v12 = FrsStatusList::PushNewError(
            v29,
            *((unsigned int *)v16 + 1),
            *((unsigned int *)v16 + 2),
            *(unsigned int *)v16,
            "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
            "DownstreamTransport::DownloadFileAsync",
            6408,
            v28,
            v16);
  }
  scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&int CloseHandle(void *)>,null_t,4>(&v34);
  return (struct FrsStatus *)v12;
}

```

## disassembly

```asm
0x1401a68ec  push    rbp
0x1401a68ee  push    rbx
0x1401a68ef  push    rsi
0x1401a68f0  push    rdi
0x1401a68f1  push    r12
0x1401a68f3  push    r13
0x1401a68f5  push    r14
0x1401a68f7  push    r15
0x1401a68f9  lea     rbp, [rsp-38h]
0x1401a68fe  sub     rsp, 138h
0x1401a6905  mov     rax, cs:__security_cookie
0x1401a690c  xor     rax, rsp
0x1401a690f  mov     [rbp+70h+var_50], rax
0x1401a6913  mov     r13d, r9d
0x1401a6916  mov     [rsp+170h+var_118], r8
0x1401a691b  mov     r12, rdx
0x1401a691e  mov     rdi, rcx
0x1401a6921  mov     [rsp+170h+var_120], rcx
0x1401a6926  mov     r14d, [rbp+70h+arg_20]
0x1401a692d  mov     r15, [rbp+70h+arg_30]
0x1401a6934  mov     rax, [rbp+70h+arg_38]
0x1401a693b  mov     [rsp+170h+var_100], rax
0x1401a6940  mov     rax, [rbp+70h+arg_40]
0x1401a6947  mov     [rsp+170h+var_108], rax
0x1401a694c  xor     edx, edx; Val
0x1401a694e  lea     r8d, [rdx+70h]; Size
0x1401a6952  lea     rcx, [rbp+70h+pAsync]; void *
0x1401a6956  call    memset_0
0x1401a695b  xorps   xmm0, xmm0
0x1401a695e  movups  [rbp+70h+var_E0], xmm0
0x1401a6962  movups  [rbp+70h+var_D0], xmm0
0x1401a6966  xor     esi, esi
0x1401a6968  mov     ebx, esi
0x1401a696a  mov     [rsp+170h+var_110], rbx
0x1401a696f  cmp     dword ptr [rdi+224h], 50001h
0x1401a6979  jnb     short loc_1401A69CD
0x1401a697b  call    cs:__imp_GetCurrentThreadId
0x1401a6982  nop     dword ptr [rax+rax+00h]
0x1401a6987  mov     [rsp+170h+var_130], rsi
0x1401a698c  mov     dword ptr [rsp+170h+var_138], eax
0x1401a6990  mov     dword ptr [rsp+170h+var_140], 18C9h
0x1401a6998  lea     rax, aDownstreamtran_18; "DownstreamTransport::DownloadFileAsync"
0x1401a699f  mov     [rsp+170h+var_148], rax
0x1401a69a4  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a69ab  mov     qword ptr [rsp+170h+var_150], rax
0x1401a69b0  lea     r9d, [rsi+3]
0x1401a69b4  xor     r8d, r8d
0x1401a69b7  mov     edx, 235Ah
0x1401a69bc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a69c1  mov     rdi, rax
0x1401a69c4  test    rax, rax
0x1401a69c7  jnz     loc_1401A6A59
0x1401a69cd  cmp     r14d, r13d
0x1401a69d0  jbe     short loc_1401A6A21
0x1401a69d2  call    cs:__imp_GetCurrentThreadId
0x1401a69d9  nop     dword ptr [rax+rax+00h]
0x1401a69de  mov     [rsp+170h+var_130], rsi
0x1401a69e3  mov     dword ptr [rsp+170h+var_138], eax
0x1401a69e7  mov     dword ptr [rsp+170h+var_140], 18CDh
0x1401a69ef  lea     rax, aDownstreamtran_18; "DownstreamTransport::DownloadFileAsync"
0x1401a69f6  mov     [rsp+170h+var_148], rax
0x1401a69fb  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a6a02  mov     qword ptr [rsp+170h+var_150], rax
0x1401a6a07  mov     r9d, 1
0x1401a6a0d  xor     r8d, r8d
0x1401a6a10  lea     edx, [r9+0Ch]
0x1401a6a14  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a6a19  mov     rdi, rax
0x1401a6a1c  test    rax, rax
0x1401a6a1f  jnz     short loc_1401A6A59
0x1401a6a21  mov     rax, [r15]
0x1401a6a24  mov     r8, [r12+8]
0x1401a6a29  mov     rdx, [r12]
0x1401a6a2d  mov     rcx, r15
0x1401a6a30  mov     rax, [rax+28h]
0x1401a6a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a6a39  mov     rdi, rax
0x1401a6a3c  test    rax, rax
0x1401a6a3f  jnz     short loc_1401A6A59
0x1401a6a41  mov     r8d, r14d
0x1401a6a44  mov     r14, [rsp+170h+var_118]
0x1401a6a49  mov     rdx, r14
0x1401a6a4c  mov     rcx, r15
0x1401a6a4f  call    WriteBack
0x1401a6a54  mov     rdi, rax
0x1401a6a57  jmp     short loc_1401A6A5E
0x1401a6a59  mov     r14, [rsp+170h+var_118]
0x1401a6a5e  cmp     [rbp+70h+arg_28], esi
0x1401a6a64  jnz     loc_1401A6BF2
0x1401a6a6a  test    rdi, rdi
0x1401a6a6d  jnz     loc_1401A6AFB
0x1401a6a73  lea     edx, [rdi+70h]; Size
0x1401a6a76  lea     rcx, [rbp+70h+pAsync]; pAsync
0x1401a6a7a  call    cs:__imp_RpcAsyncInitializeHandle
0x1401a6a81  nop     dword ptr [rax+rax+00h]
0x1401a6a86  mov     edi, eax
0x1401a6a88  call    cs:__imp_GetCurrentThreadId
0x1401a6a8f  nop     dword ptr [rax+rax+00h]
0x1401a6a94  mov     edx, esi
0x1401a6a96  cmp     edi, 4D5h
0x1401a6a9c  setz    dl
0x1401a6a9f  mov     [rsp+170h+var_138], rsi
0x1401a6aa4  mov     dword ptr [rsp+170h+var_148], eax
0x1401a6aa8  mov     [rsp+170h+var_150], 18DFh
0x1401a6ab0  lea     r9, aDownstreamtran_18; "DownstreamTransport::DownloadFileAsync"
0x1401a6ab7  mov     ecx, edi
0x1401a6ab9  call    LogTranslatedRemoteError
0x1401a6abe  mov     rdi, rax
0x1401a6ac1  test    rax, rax
0x1401a6ac4  jnz     short loc_1401A6AFB
0x1401a6ac6  xor     edx, edx; bInitialState
0x1401a6ac8  xor     ecx, ecx; bManualReset
0x1401a6aca  call    ?CreateEventOrDie@@YAPEAXHH@Z; CreateEventOrDie(int,int)
0x1401a6acf  test    rax, rax
0x1401a6ad2  cmovnz  rbx, rax
0x1401a6ad6  mov     [rsp+170h+var_110], rbx
0x1401a6adb  mov     r12, [rsp+170h+var_120]
0x1401a6ae0  lea     rcx, [r12+0B0h]; this
0x1401a6ae8  xor     r9d, r9d; int
0x1401a6aeb  xor     r8d, r8d; unsigned __int64
0x1401a6aee  lea     edx, [rdi+78h]; unsigned __int64
0x1401a6af1  call    ?ThrottleBytes@BandwidthThrottler@@QEAAPEAVFrsStatus@@_K0H@Z; BandwidthThrottler::ThrottleBytes(unsigned __int64,unsigned __int64,int)
0x1401a6af6  mov     rdi, rax
0x1401a6af9  jmp     short loc_1401A6B00
0x1401a6afb  mov     r12, [rsp+170h+var_120]
0x1401a6b00  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a6b07  test    rax, rax
0x1401a6b0a  jz      short loc_1401A6B5B
0x1401a6b0c  cmp     [rax+40h], esi
0x1401a6b0f  jz      short loc_1401A6B5B
0x1401a6b11  cmp     dword ptr [rax+38h], 5
0x1401a6b15  jl      short loc_1401A6B5B
0x1401a6b17  lea     rax, aDownstreamtran_43; "DownstreamTransport::DownloadFileAsync"
0x1401a6b1e  mov     [rsp+170h+var_F8], rax
0x1401a6b23  mov     [rbp+70h+var_F0], 18ECh
0x1401a6b2a  mov     [rbp+70h+var_EC], 5
0x1401a6b31  lea     rax, aDown; "DOWN"
0x1401a6b38  mov     [rbp+70h+var_E8], rax
0x1401a6b3c  lea     rax, [rbp+70h+pAsync]
0x1401a6b40  mov     [rsp+170h+var_120], rax
0x1401a6b45  lea     r8, [rsp+170h+var_120]
0x1401a6b4a  lea     rdx, aRpcasyncstateP; "rpcAsyncState:%p"
0x1401a6b51  lea     rcx, [rsp+170h+var_F8]
0x1401a6b56  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401a6b5b  test    rdi, rdi
0x1401a6b5e  jnz     loc_1401A6BF7
0x1401a6b64  mov     [rbp+70h+pAsync.UserInfo], rsi
0x1401a6b68  mov     [rbp+70h+pAsync.NotificationType], 1
0x1401a6b6f  mov     qword ptr [rbp+70h+pAsync.u], rbx
0x1401a6b73  lea     r8, [rbp+70h+var_E0]
0x1401a6b77  mov     rdx, [rsp+170h+var_108]
0x1401a6b7c  mov     rdx, [rdx]
0x1401a6b7f  lea     rcx, [rbp+70h+pAsync]
0x1401a6b83  call    RpcRawGetFileDataAsync
0x1401a6b88  mov     ebx, eax
0x1401a6b8a  call    cs:__imp_GetCurrentThreadId
0x1401a6b91  nop     dword ptr [rax+rax+00h]
0x1401a6b96  mov     edx, esi
0x1401a6b98  cmp     ebx, 4D5h
0x1401a6b9e  setz    dl
0x1401a6ba1  mov     [rsp+170h+var_138], rsi
0x1401a6ba6  mov     dword ptr [rsp+170h+var_148], eax
0x1401a6baa  mov     [rsp+170h+var_150], 18F6h
0x1401a6bb2  lea     r9, aDownstreamtran_18; "DownstreamTransport::DownloadFileAsync"
0x1401a6bb9  mov     ecx, ebx
0x1401a6bbb  call    LogTranslatedRemoteError
0x1401a6bc0  mov     rdi, rax
0x1401a6bc3  test    rax, rax
0x1401a6bc6  jnz     short loc_1401A6BF7
0x1401a6bc8  mov     rax, [rsp+170h+var_100]
0x1401a6bcd  mov     [rsp+170h+var_140], rax; volatile int *
0x1401a6bd2  mov     [rsp+170h+var_148], r15; struct Writer *
0x1401a6bd7  mov     [rsp+170h+var_150], r13d; unsigned int
0x1401a6bdc  mov     r9, r14; unsigned __int8 *
0x1401a6bdf  lea     r8, [rbp+70h+var_E0]; struct ASYNC_pipe_BYTE_PIPE *
0x1401a6be3  lea     rdx, [rbp+70h+pAsync]; struct _RPC_ASYNC_STATE *
0x1401a6be7  mov     rcx, r12; this
0x1401a6bea  call    ?RpcAsyncPipeDownload@DownstreamTransport@@IEAAPEAVFrsStatus@@AEAU_RPC_ASYNC_STATE@@AEAUASYNC_pipe_BYTE_PIPE@@PEAEKAEAVWriter@@AEDH@Z; DownstreamTransport::RpcAsyncPipeDownload(_RPC_ASYNC_STATE &,ASYNC_pipe_BYTE_PIPE &,uchar *,ulong,Writer &,int const volatile &)
0x1401a6bef  mov     rdi, rax
0x1401a6bf2  test    rdi, rdi
0x1401a6bf5  jz      short loc_1401A6C3E
0x1401a6bf7  call    cs:__imp_GetCurrentThreadId
0x1401a6bfe  nop     dword ptr [rax+rax+00h]
0x1401a6c03  mov     [rsp+170h+var_130], rdi
0x1401a6c08  mov     dword ptr [rsp+170h+var_138], eax
0x1401a6c0c  mov     dword ptr [rsp+170h+var_140], 1908h
0x1401a6c14  lea     rax, aDownstreamtran_18; "DownstreamTransport::DownloadFileAsync"
0x1401a6c1b  mov     [rsp+170h+var_148], rax
0x1401a6c20  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a6c27  mov     qword ptr [rsp+170h+var_150], rax
0x1401a6c2c  mov     r9d, [rdi]
0x1401a6c2f  mov     r8d, [rdi+8]
0x1401a6c33  mov     edx, [rdi+4]
0x1401a6c36  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a6c3b  mov     rsi, rax
0x1401a6c3e  lea     rcx, [rsp+170h+var_110]
0x1401a6c43  call    ??1?$scoped_any@PEAXU?$close_fun@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@Unull_t@@$03@@QEAA@XZ; scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>::~scoped_any<void *,close_fun<int (*)(void *),&CloseHandle(void *)>,null_t,4>(void)
0x1401a6c48  mov     rax, rsi
0x1401a6c4b  mov     rcx, [rbp+70h+var_50]
0x1401a6c4f  xor     rcx, rsp; StackCookie
0x1401a6c52  call    __security_check_cookie
0x1401a6c57  add     rsp, 138h
0x1401a6c5e  pop     r15
0x1401a6c60  pop     r14
0x1401a6c62  pop     r13
0x1401a6c64  pop     r12
0x1401a6c66  pop     rdi
0x1401a6c67  pop     rsi
0x1401a6c68  pop     rbx
0x1401a6c69  pop     rbp
0x1401a6c6a  retn
```
