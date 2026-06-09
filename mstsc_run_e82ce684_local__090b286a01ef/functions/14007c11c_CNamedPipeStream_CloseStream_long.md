# CNamedPipeStream::CloseStream(long)

- ea: `0x14007c11c`
- end: `0x14007c239`
- name: `?CloseStream@CNamedPipeStream@@AEAAJJ@Z`
- size: `285`
- prototype: `__int64 __fastcall(PVOID pv, int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14007c0c0`
- `0x14007c240`
- `0x14007c564`
- `0x14007d340`
- `0x14007dc60`

## callees

- `0x140001940`
- `0x14005b6d8`
- `0x14005bc74`
- `0x14007c11c`
- `0x140114010`

## import_xrefs

- `KERNEL32!CloseThreadpoolWork` at `0x14007c1bf`
- `KERNEL32!CloseThreadpoolWork` at `0x14007c1bf`
- `KERNEL32!SubmitThreadpoolWork` at `0x14007c1b6`
- `KERNEL32!SubmitThreadpoolWork` at `0x14007c1b6`
- `KERNEL32!CreateThreadpoolWork` at `0x14007c1a5`
- `KERNEL32!CreateThreadpoolWork` at `0x14007c1a5`
- `KERNEL32!DisconnectNamedPipe` at `0x14007c15b`
- `KERNEL32!DisconnectNamedPipe` at `0x14007c15b`
- `KERNEL32!CloseHandle` at `0x14007c165`
- `KERNEL32!CloseHandle` at `0x14007c165`
- `KERNEL32!GetLastError` at `0x14007c1c7`
- `KERNEL32!GetLastError` at `0x14007c1c7`

## string_xrefs

- `0x14007c1e7`: `CreateThreadpoolWork failed`

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
      if ( (unsigned int)dword_140152118 > 3 )
      {
        LODWORD(v14) = v12;
        v15 = "CreateThreadpoolWork failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_140141601,
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
0x14007c11c  mov     [rsp+arg_8], rbx
0x14007c121  mov     [rsp+arg_18], rsi
0x14007c126  push    rdi
0x14007c127  sub     rsp, 30h
0x14007c12b  mov     rbx, rcx
0x14007c12e  mov     esi, edx
0x14007c130  add     rcx, 50h ; 'P'; this
0x14007c134  xor     edi, edi
0x14007c136  mov     [rsp+38h+arg_0], rcx
0x14007c13b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14007c140  cmp     [rbx+60h], edi
0x14007c143  jz      short loc_14007C151
0x14007c145  mov     edi, 1
0x14007c14a  mov     dword ptr [rbx+60h], 0
0x14007c151  mov     rcx, [rbx+38h]; hNamedPipe
0x14007c155  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14007c159  jz      short loc_14007C173
0x14007c15b  call    cs:__imp_DisconnectNamedPipe
0x14007c161  mov     rcx, [rbx+38h]; hObject
0x14007c165  call    cs:__imp_CloseHandle
0x14007c16b  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x14007c173  lea     rcx, [rsp+38h+arg_0]; this
0x14007c178  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14007c17d  test    edi, edi
0x14007c17f  jz      loc_14007C227
0x14007c185  mov     rcx, [rbx+28h]
0x14007c189  mov     [rbx+64h], esi
0x14007c18c  mov     rax, [rcx]
0x14007c18f  mov     rax, [rax+8]
0x14007c193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c198  xor     r8d, r8d; pcbe
0x14007c19b  lea     rcx, ?STATIC_OnCloseCallbackThreadProc@CNamedPipeStream@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007c1a2  mov     rdx, rbx; pv
0x14007c1a5  call    cs:__imp_CreateThreadpoolWork
0x14007c1ab  mov     rdi, rax
0x14007c1ae  test    rax, rax
0x14007c1b1  jz      short loc_14007C1C7
0x14007c1b3  mov     rcx, rax; pwk
0x14007c1b6  call    cs:__imp_SubmitThreadpoolWork
0x14007c1bc  mov     rcx, rdi; pwk
0x14007c1bf  call    cs:__imp_CloseThreadpoolWork
0x14007c1c5  jmp     short loc_14007C227
0x14007c1c7  call    cs:__imp_GetLastError
0x14007c1cd  mov     ecx, eax
0x14007c1cf  test    eax, eax
0x14007c1d1  jle     short loc_14007C1DC
0x14007c1d3  movzx   ecx, ax
0x14007c1d6  or      ecx, 80070000h
0x14007c1dc  mov     eax, cs:dword_140152118
0x14007c1e2  cmp     eax, 3
0x14007c1e5  jbe     short loc_14007C217
0x14007c1e7  lea     rax, aCreatethreadpo; "CreateThreadpoolWork failed"
0x14007c1ee  mov     dword ptr [rsp+38h+arg_0], ecx
0x14007c1f2  mov     [rsp+38h+arg_10], rax
0x14007c1f7  lea     rdx, byte_140141601
0x14007c1fe  lea     rax, [rsp+38h+arg_0]
0x14007c203  mov     [rsp+38h+var_10], rax
0x14007c208  lea     rax, [rsp+38h+arg_10]
0x14007c20d  mov     [rsp+38h+var_18], rax
0x14007c212  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14007c217  mov     rcx, [rbx+28h]
0x14007c21b  mov     rax, [rcx]
0x14007c21e  mov     rax, [rax+10h]
0x14007c222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c227  mov     rbx, [rsp+38h+arg_8]
0x14007c22c  xor     eax, eax
0x14007c22e  mov     rsi, [rsp+38h+arg_18]
0x14007c233  add     rsp, 30h
0x14007c237  pop     rdi
0x14007c238  retn
```
