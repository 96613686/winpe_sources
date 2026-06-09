# CNamedPipeStream::CloseStream(long)

- ea: `0x18007261c`
- end: `0x180072739`
- name: `?CloseStream@CNamedPipeStream@@AEAAJJ@Z`
- size: `285`
- prototype: `__int64 __fastcall(PVOID pv, int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180066604`
- `0x180066928`
- `0x180066d60`
- `0x1800671e0`
- `0x180103d20`

## callees

- `0x180004a94`
- `0x180016ad0`
- `0x1800506ac`
- `0x18007261c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072665`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072665`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800726b6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800726b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800726bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800726bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800726a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800726a5`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18007265b`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18007265b`

## string_xrefs

- `0x1800726e7`: `CreateThreadpoolWork failed`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::CloseStream(char *pv, int a2)
{
  int v4; // edi
  void *v5; // rcx
  __int64 v6; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ecx
  char *v14; // [rsp+40h] [rbp+8h] BYREF
  const char *v15; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v14 = pv + 80;
  CTSCriticalSection::Lock((CTSCriticalSection *)(pv + 80));
  if ( *((_DWORD *)pv + 24) )
  {
    v4 = 1;
    *((_DWORD *)pv + 24) = 0;
  }
  v5 = (void *)*((_QWORD *)pv + 7);
  if ( v5 != (void *)-1LL )
  {
    DisconnectNamedPipe(v5);
    CloseHandle(*((HANDLE *)pv + 7));
    *((_QWORD *)pv + 7) = -1;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v14);
  if ( v4 )
  {
    v6 = *((_QWORD *)pv + 5);
    *((_DWORD *)pv + 25) = a2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    ThreadpoolWork = CreateThreadpoolWork(CNamedPipeStream::STATIC_OnCloseCallbackThreadProc, pv, 0);
    v8 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v8);
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v14) = v12;
        v15 = "CreateThreadpoolWork failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_1801C706B,
          v10,
          v11,
          (__int64)&v15,
          (__int64)&v14);
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + 5) + 16LL))(*((_QWORD *)pv + 5));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007261c  mov     [rsp+arg_8], rbx
0x180072621  mov     [rsp+arg_18], rsi
0x180072626  push    rdi
0x180072627  sub     rsp, 30h
0x18007262b  mov     rbx, rcx
0x18007262e  mov     esi, edx
0x180072630  add     rcx, 50h ; 'P'; this
0x180072634  xor     edi, edi
0x180072636  mov     [rsp+38h+arg_0], rcx
0x18007263b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180072640  cmp     [rbx+60h], edi
0x180072643  jz      short loc_180072651
0x180072645  mov     edi, 1
0x18007264a  mov     dword ptr [rbx+60h], 0
0x180072651  mov     rcx, [rbx+38h]; hNamedPipe
0x180072655  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180072659  jz      short loc_180072673
0x18007265b  call    cs:__imp_DisconnectNamedPipe
0x180072661  mov     rcx, [rbx+38h]; hObject
0x180072665  call    cs:__imp_CloseHandle
0x18007266b  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180072673  lea     rcx, [rsp+38h+arg_0]; this
0x180072678  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18007267d  test    edi, edi
0x18007267f  jz      loc_180072727
0x180072685  mov     rcx, [rbx+28h]
0x180072689  mov     [rbx+64h], esi
0x18007268c  mov     rax, [rcx]
0x18007268f  mov     rax, [rax+8]
0x180072693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072698  xor     r8d, r8d; pcbe
0x18007269b  lea     rcx, ?STATIC_OnCloseCallbackThreadProc@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800726a2  mov     rdx, rbx; pv
0x1800726a5  call    cs:__imp_CreateThreadpoolWork
0x1800726ab  mov     rdi, rax
0x1800726ae  test    rax, rax
0x1800726b1  jz      short loc_1800726C7
0x1800726b3  mov     rcx, rax; pwk
0x1800726b6  call    cs:__imp_SubmitThreadpoolWork
0x1800726bc  mov     rcx, rdi; pwk
0x1800726bf  call    cs:__imp_CloseThreadpoolWork
0x1800726c5  jmp     short loc_180072727
0x1800726c7  call    cs:__imp_GetLastError
0x1800726cd  mov     ecx, eax
0x1800726cf  test    eax, eax
0x1800726d1  jle     short loc_1800726DC
0x1800726d3  movzx   ecx, ax
0x1800726d6  or      ecx, 80070000h
0x1800726dc  mov     eax, cs:CallbackContext
0x1800726e2  cmp     eax, 3
0x1800726e5  jbe     short loc_180072717
0x1800726e7  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x1800726ee  mov     dword ptr [rsp+38h+arg_0], ecx
0x1800726f2  mov     [rsp+38h+arg_10], rax
0x1800726f7  lea     rdx, byte_1801C706B
0x1800726fe  lea     rax, [rsp+38h+arg_0]
0x180072703  mov     [rsp+38h+var_10], rax
0x180072708  lea     rax, [rsp+38h+arg_10]
0x18007270d  mov     [rsp+38h+var_18], rax
0x180072712  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180072717  mov     rcx, [rbx+28h]
0x18007271b  mov     rax, [rcx]
0x18007271e  mov     rax, [rax+10h]
0x180072722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072727  mov     rbx, [rsp+38h+arg_8]
0x18007272c  xor     eax, eax
0x18007272e  mov     rsi, [rsp+38h+arg_18]
0x180072733  add     rsp, 30h
0x180072737  pop     rdi
0x180072738  retn
```
