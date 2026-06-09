# InitializeAsyncKsec

- ea: `0x14000508c`
- end: `0x1400051b8`
- name: `InitializeAsyncKsec`
- size: `300`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140003094`

## callees

- `0x140004ed8`
- `0x140004fbc`
- `0x14000508c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400050d6`
- `ntdll!NtOpenFile` at `0x1400050d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051a7`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14000509d`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14000509d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14000518c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14000518c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140005110`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140005110`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400050ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400050ec`

## pseudocode

```c
NTSTATUS __fastcall InitializeAsyncKsec(POBJECT_ATTRIBUTES ObjectAttributes)
{
  NTSTATUS result; // eax
  DWORD MaxAsyncWorkerThreads; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  dwTlsIndex = TlsAlloc();
  if ( dwTlsIndex == -1 )
    goto LABEL_6;
  result = NtOpenFile(&fl, 0xC0000000, ObjectAttributes, &IoStatusBlock, 3u, 0);
  if ( fl == (HANDLE)-1LL )
    return result;
  ptpp = CreateThreadpool(0);
  if ( !ptpp )
    goto LABEL_6;
  MaxAsyncWorkerThreads = GetMaxAsyncWorkerThreads();
  SetThreadpoolThreadMaximum(ptpp, MaxAsyncWorkerThreads);
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.Pool = ptpp;
  pcbe.Version = 3;
  pcbe.CleanupGroup = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  pio = CreateThreadpoolIo(fl, (PTP_WIN32_IO_CALLBACK)AsyncWorkReadyCallback, 0, 0);
  if ( pio )
  {
    SendRequestForNextAsyncKsecddCall();
    return 0;
  }
  else
  {
LABEL_6:
    GetLastError();
    return -1073741670;
  }
}

```

## disassembly

```asm
0x14000508c  push    rbx
0x14000508e  sub     rsp, 40h
0x140005092  xorps   xmm0, xmm0
0x140005095  mov     rbx, rcx
0x140005098  movups  xmmword ptr [rsp+48h+IoStatusBlock], xmm0
0x14000509d  call    cs:__imp_TlsAlloc
0x1400050a3  mov     cs:dwTlsIndex, eax
0x1400050a9  cmp     eax, 0FFFFFFFFh
0x1400050ac  jz      loc_1400051A7
0x1400050b2  mov     [rsp+48h+OpenOptions], 0; OpenOptions
0x1400050ba  lea     r9, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x1400050bf  mov     r8, rbx; ObjectAttributes
0x1400050c2  mov     [rsp+48h+ShareAccess], 3; ShareAccess
0x1400050ca  mov     edx, 0C0000000h; DesiredAccess
0x1400050cf  lea     rcx, fl; FileHandle
0x1400050d6  call    cs:__imp_NtOpenFile
0x1400050dc  cmp     cs:fl, 0FFFFFFFFFFFFFFFFh
0x1400050e4  jz      loc_1400051B2
0x1400050ea  xor     ecx, ecx; reserved
0x1400050ec  call    cs:__imp_CreateThreadpool
0x1400050f2  mov     cs:ptpp, rax
0x1400050f9  test    rax, rax
0x1400050fc  jz      loc_1400051A7
0x140005102  call    GetMaxAsyncWorkerThreads
0x140005107  mov     rcx, cs:ptpp; ptpp
0x14000510e  mov     edx, eax; cthrdMost
0x140005110  call    cs:__imp_SetThreadpoolThreadMaximum
0x140005116  mov     rax, cs:ptpp
0x14000511d  lea     rdx, AsyncWorkReadyCallback; pfnio
0x140005124  mov     rcx, cs:fl; fl
0x14000512b  xorps   xmm0, xmm0
0x14000512e  xor     r9d, r9d; pcbe
0x140005131  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm0
0x140005139  xor     r8d, r8d; pv
0x14000513c  mov     cs:pcbe.Pool, rax
0x140005143  mov     cs:pcbe.Version, 3
0x14000514d  mov     cs:pcbe.CleanupGroup, 0
0x140005158  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x140005163  mov     cs:pcbe.FinalizationCallback, 0
0x14000516e  mov     dword ptr cs:pcbe.u, 0
0x140005178  mov     cs:pcbe.CallbackPriority, 1
0x140005182  mov     cs:pcbe.Size, 48h ; 'H'
0x14000518c  call    cs:__imp_CreateThreadpoolIo
0x140005192  mov     cs:pio, rax
0x140005199  test    rax, rax
0x14000519c  jz      short loc_1400051A7
0x14000519e  call    SendRequestForNextAsyncKsecddCall
0x1400051a3  xor     eax, eax
0x1400051a5  jmp     short loc_1400051B2
0x1400051a7  call    cs:__imp_GetLastError
0x1400051ad  mov     eax, 0C000009Ah
0x1400051b2  add     rsp, 40h
0x1400051b6  pop     rbx
0x1400051b7  retn
```
