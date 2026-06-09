# PipeManager::PipeManager(void)

- ea: `0x1800eb960`
- end: `0x1800ebab9`
- name: `??0PipeManager@@AEAA@XZ`
- size: `345`
- prototype: `PipeManager *__fastcall(PipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800ec988`

## callees

- `0x180001010`
- `0x1800017c8`
- `0x1800eb7f0`
- `0x1800eb960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eba00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eba14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eba00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eba14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eba4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eba4c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800eba3d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800eba3d`

## pseudocode

```c
PipeManager *__fastcall PipeManager::PipeManager(PipeManager *this)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ecx
  const char *v11; // [rsp+50h] [rbp+8h] BYREF
  const char *v12; // [rsp+58h] [rbp+10h] BYREF
  const char *v13; // [rsp+60h] [rbp+18h] BYREF

  v11 = (const char *)this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  DataStructureHelpers::UnorderedSetWithLock<PipeManager::PipeImplementation *>::UnorderedSetWithLock<PipeManager::PipeImplementation *>((char *)this + 40);
  *((_DWORD *)this + 38) = 1;
  *((_BYTE *)this + 156) = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v11 = "PipeManager::PipeManager";
    v12 = "LuiPipeManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v2,
      (unsigned int)&dword_1801350BC,
      v3,
      v4,
      (__int64)&v12,
      (__int64)&v11);
  }
  *((_QWORD *)this + 2) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = CreateEventW(0, 0, 0, 0);
  Thread = CreateThread(0, 0, PipeManager::WriteMessageThread, this, 0, 0);
  *((_QWORD *)this + 4) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v11) = v9;
      v13 = "LuiPipe";
      v12 = "PipeManager::PipeManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)qword_180135088,
        v7,
        v8,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800eb960  mov     [rsp+arg_18], rbx
0x1800eb965  mov     [rsp+arg_0], rcx
0x1800eb96a  push    rsi
0x1800eb96b  sub     rsp, 40h
0x1800eb96f  mov     rbx, rcx
0x1800eb972  mov     qword ptr [rcx], 0
0x1800eb979  mov     qword ptr [rcx+8], 0
0x1800eb981  mov     qword ptr [rcx+10h], 0
0x1800eb989  mov     qword ptr [rcx+18h], 0
0x1800eb991  mov     qword ptr [rcx+20h], 0
0x1800eb999  add     rcx, 28h ; '('
0x1800eb99d  call    ??0?$UnorderedSetWithLock@PEAVPipeImplementation@PipeManager@@@DataStructureHelpers@@QEAA@PEAVBasicLock@LockHelpers@@@Z; DataStructureHelpers::UnorderedSetWithLock<PipeManager::PipeImplementation *>::UnorderedSetWithLock<PipeManager::PipeImplementation *>(LockHelpers::BasicLock *)
0x1800eb9a2  mov     dword ptr [rbx+98h], 1
0x1800eb9ac  lea     rsi, aPipemanagerPip_3; "PipeManager::PipeManager"
0x1800eb9b3  mov     byte ptr [rbx+9Ch], 0
0x1800eb9ba  mov     eax, cs:CallbackContext
0x1800eb9c0  cmp     eax, 4
0x1800eb9c3  jbe     short loc_1800EB9F6
0x1800eb9c5  lea     rax, aLuipipemanager; "LuiPipeManager"
0x1800eb9cc  mov     [rsp+48h+arg_0], rsi
0x1800eb9d1  mov     [rsp+48h+arg_8], rax
0x1800eb9d6  lea     rdx, dword_1801350BC
0x1800eb9dd  lea     rax, [rsp+48h+arg_0]
0x1800eb9e2  mov     [rsp+48h+lpThreadId], rax
0x1800eb9e7  lea     rax, [rsp+48h+arg_8]
0x1800eb9ec  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x1800eb9f1  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800eb9f6  xor     r9d, r9d; lpName
0x1800eb9f9  xor     r8d, r8d; bInitialState
0x1800eb9fc  xor     edx, edx; bManualReset
0x1800eb9fe  xor     ecx, ecx; lpEventAttributes
0x1800eba00  call    cs:__imp_CreateEventW
0x1800eba06  xor     r9d, r9d; lpName
0x1800eba09  xor     r8d, r8d; bInitialState
0x1800eba0c  xor     edx, edx; bManualReset
0x1800eba0e  mov     [rbx+10h], rax
0x1800eba12  xor     ecx, ecx; lpEventAttributes
0x1800eba14  call    cs:__imp_CreateEventW
0x1800eba1a  mov     r9, rbx; lpParameter
0x1800eba1d  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800eba26  lea     r8, ?WriteMessageThread@PipeManager@@CAKPEAX@Z; lpStartAddress
0x1800eba2d  mov     [rbx+18h], rax
0x1800eba31  xor     edx, edx; dwStackSize
0x1800eba33  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800eba3b  xor     ecx, ecx; lpThreadAttributes
0x1800eba3d  call    cs:__imp_CreateThread
0x1800eba43  mov     [rbx+20h], rax
0x1800eba47  test    rax, rax
0x1800eba4a  jnz     short loc_1800EBAAB
0x1800eba4c  call    cs:__imp_GetLastError
0x1800eba52  mov     ecx, eax
0x1800eba54  test    eax, eax
0x1800eba56  jle     short loc_1800EBA61
0x1800eba58  movzx   ecx, ax
0x1800eba5b  or      ecx, 80070000h
0x1800eba61  mov     eax, cs:CallbackContext
0x1800eba67  cmp     eax, 4
0x1800eba6a  jbe     short loc_1800EBAAB
0x1800eba6c  lea     rax, aLuipipe; "LuiPipe"
0x1800eba73  mov     dword ptr [rsp+48h+arg_0], ecx
0x1800eba77  mov     [rsp+48h+arg_10], rax
0x1800eba7c  lea     rdx, qword_180135088
0x1800eba83  lea     rax, [rsp+48h+arg_0]
0x1800eba88  mov     [rsp+48h+arg_8], rsi
0x1800eba8d  mov     [rsp+48h+var_18], rax
0x1800eba92  lea     rax, [rsp+48h+arg_8]
0x1800eba97  mov     [rsp+48h+lpThreadId], rax
0x1800eba9c  lea     rax, [rsp+48h+arg_10]
0x1800ebaa1  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x1800ebaa6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ebaab  mov     rax, rbx
0x1800ebaae  mov     rbx, [rsp+48h+arg_18]
0x1800ebab3  add     rsp, 40h
0x1800ebab7  pop     rsi
0x1800ebab8  retn
```
