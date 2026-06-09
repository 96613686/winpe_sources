# CensusJson::Begin(ushort const *)

- ea: `0x18009f0fc`
- end: `0x18009f3ed`
- name: `?Begin@CensusJson@@QEAAJPEBG@Z`
- size: `753`
- prototype: `__int64 __fastcall(CensusJson *__hidden this, LPCWSTR pszFile)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x1800a2cd0`
- `0x1800a47e0`

## callees

- `0x180008dc0`
- `0x180009efc`
- `0x180009f14`
- `0x18009f0fc`
- `0x18009f3f4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009f21b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009f21b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f18c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f1aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f18c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009f1aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009f36f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009f36f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009f1c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009f1c0`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009f2ef`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009f2ef`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009f2dd`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009f3a3`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009f2dd`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009f3a3`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18009f324`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18009f324`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009f3ae`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009f3ae`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x18009f34d`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x18009f34d`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18009f1df`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18009f1df`

## pseudocode

```c
__int64 __fastcall CensusJson::Begin(CensusJson *this, LPCWSTR pszFile)
{
  ULONG64 v4; // rsi
  HRESULT v5; // edi
  HANDLE EventW; // rax
  HANDLE v7; // rax
  void *v8; // rax
  __int64 v9; // r8
  TRACEHANDLE v10; // rax
  HANDLE Thread; // rax
  ULONG64 TraceHandle[2]; // [rsp+30h] [rbp-D0h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-C0h] BYREF
  GUID ControlGuid; // [rsp+200h] [rbp+100h] BYREF

  ControlGuid.Data1 = 1135363387;
  *(_DWORD *)&ControlGuid.Data2 = 1263638477;
  *(_DWORD *)ControlGuid.Data4 = 2094757443;
  v4 = -1;
  *(_DWORD *)&ControlGuid.Data4[4] = -1402750565;
  TraceHandle[0] = -1;
  v5 = 0;
  memset_0(&Logfile, 0, sizeof(Logfile));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( !EventW )
    goto LABEL_13;
  v7 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
    goto LABEL_13;
  DeleteFileW(pszFile);
  v5 = SHCreateStreamOnFileEx(pszFile, 1u, 0x200000u, 1, 0, (IStream **)this);
  if ( v5 < 0 )
    goto LABEL_13;
  v5 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, _QWORD))(**(_QWORD **)this + 32LL))(
         *(_QWORD *)this,
         "{\r\n    \"Events\":[",
         17,
         0);
  if ( v5 < 0 )
    goto LABEL_13;
  v8 = malloc(0x478u);
  *((_QWORD *)this + 4) = v8;
  if ( !v8 )
    goto LABEL_13;
  memset_0(v8, 0, 0x478u);
  v9 = -1;
  do
    ++v9;
  while ( CensusJson::TraceSessionName[v9] );
  memcpy_0((void *)(*((_QWORD *)this + 4) + 120LL), CensusJson::TraceSessionName, 2 * v9);
  **((_DWORD **)this + 4) = 1144;
  *(GUID *)(*((_QWORD *)this + 4) + 24LL) = ControlGuid;
  *(_DWORD *)(*((_QWORD *)this + 4) + 40LL) = 1;
  *(_DWORD *)(*((_QWORD *)this + 4) + 44LL) = 0x20000;
  *(_DWORD *)(*((_QWORD *)this + 4) + 116LL) = 120;
  *(_DWORD *)(*((_QWORD *)this + 4) + 48LL) = 1024;
  *(_DWORD *)(*((_QWORD *)this + 4) + 52LL) = 64;
  *(_DWORD *)(*((_QWORD *)this + 4) + 56LL) = 84;
  *(_DWORD *)(*((_QWORD *)this + 4) + 64LL) = 256;
  *(_DWORD *)(*((_QWORD *)this + 4) + 68LL) = 1;
  ControlTraceW(0, CensusJson::TraceSessionName, *((PEVENT_TRACE_PROPERTIES *)this + 4), 1u);
  if ( StartTraceW(TraceHandle, CensusJson::TraceSessionName, *((PEVENT_TRACE_PROPERTIES *)this + 4)) )
    goto LABEL_13;
  Logfile.LogFileMode = 268435712;
  Logfile.EventCallback = (PEVENT_CALLBACK)CensusJson::ProcessEventRecord;
  Logfile.LoggerName = CensusJson::TraceSessionName;
  Logfile.Context = this;
  v10 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 6) = v10;
  if ( v10 == -1 )
    goto LABEL_13;
  if ( !EnableTrace(1u, 0, 5u, &ControlGuid, TraceHandle[0])
    && (Thread = CreateThread(0, 0, CensusJson::TracerThreadProc, this, 0, 0), (*((_QWORD *)this + 5) = Thread) != 0) )
  {
    TraceHandle[0] = -1;
    v5 = 0;
  }
  else
  {
LABEL_13:
    v4 = TraceHandle[0];
  }
  if ( v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ControlTraceW(v4, 0, *((PEVENT_TRACE_PROPERTIES *)this + 4), 1u);
    CloseTrace(TraceHandle[0]);
  }
  if ( v5 < 0 )
    CensusJson::CleanupMembers(this);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18009f0fc  mov     [rsp-8+arg_10], rbx
0x18009f101  mov     [rsp-8+arg_18], rsi
0x18009f106  push    rbp
0x18009f107  push    rdi
0x18009f108  push    r12
0x18009f10a  push    r14
0x18009f10c  push    r15
0x18009f10e  lea     rbp, [rsp-120h]
0x18009f116  sub     rsp, 220h
0x18009f11d  mov     rax, cs:__security_cookie
0x18009f124  xor     rax, rsp
0x18009f127  mov     [rbp+140h+var_30], rax
0x18009f12e  mov     r14, rdx
0x18009f131  mov     [rbp+140h+ControlGuid.Data1], 43AC453Bh
0x18009f13b  mov     rbx, rcx
0x18009f13e  mov     dword ptr [rbp+140h+ControlGuid.Data2], 4B5197CDh
0x18009f148  xor     r15d, r15d
0x18009f14b  mov     dword ptr [rbp+140h+ControlGuid.Data4], 7CDB7643h
0x18009f155  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009f159  mov     dword ptr [rbp+140h+ControlGuid.Data4+4], 0AC63B99Bh
0x18009f163  xor     edx, edx; Val
0x18009f165  mov     [rsp+240h+TraceHandle], rsi
0x18009f16a  lea     rcx, [rsp+240h+Logfile]; void *
0x18009f16f  mov     r8d, 1C0h; Size
0x18009f175  mov     edi, r15d
0x18009f178  call    memset_0
0x18009f17d  lea     r12d, [r15+1]
0x18009f181  xor     r9d, r9d; lpName
0x18009f184  mov     edx, r12d; bManualReset
0x18009f187  xor     r8d, r8d; bInitialState
0x18009f18a  xor     ecx, ecx; lpEventAttributes
0x18009f18c  call    cs:__imp_CreateEventW
0x18009f192  mov     [rbx+8], rax
0x18009f196  test    rax, rax
0x18009f199  jz      loc_18009F388
0x18009f19f  xor     r9d, r9d; lpName
0x18009f1a2  xor     r8d, r8d; bInitialState
0x18009f1a5  mov     edx, r12d; bManualReset
0x18009f1a8  xor     ecx, ecx; lpEventAttributes
0x18009f1aa  call    cs:__imp_CreateEventW
0x18009f1b0  mov     [rbx+10h], rax
0x18009f1b4  test    rax, rax
0x18009f1b7  jz      loc_18009F388
0x18009f1bd  mov     rcx, r14; lpFileName
0x18009f1c0  call    cs:__imp_DeleteFileW
0x18009f1c6  mov     r9d, r12d; fCreate
0x18009f1c9  mov     [rsp+240h+ppstm], rbx; ppstm
0x18009f1ce  mov     r8d, 200000h; dwAttributes
0x18009f1d4  mov     [rsp+240h+pstmTemplate], r15; pstmTemplate
0x18009f1d9  mov     edx, r12d; grfMode
0x18009f1dc  mov     rcx, r14; pszFile
0x18009f1df  call    cs:__imp_SHCreateStreamOnFileEx
0x18009f1e5  mov     edi, eax
0x18009f1e7  test    eax, eax
0x18009f1e9  js      loc_18009F388
0x18009f1ef  mov     rcx, [rbx]
0x18009f1f2  lea     r8d, [r15+11h]
0x18009f1f6  xor     r9d, r9d
0x18009f1f9  lea     rdx, aEvents; "{\r\n    \"Events\":["
0x18009f200  mov     rax, [rcx]
0x18009f203  mov     rax, [rax+20h]
0x18009f207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f20c  mov     edi, eax
0x18009f20e  test    eax, eax
0x18009f210  js      loc_18009F388
0x18009f216  mov     ecx, 478h; Size
0x18009f21b  call    cs:__imp_malloc
0x18009f221  mov     [rbx+20h], rax
0x18009f225  test    rax, rax
0x18009f228  jz      loc_18009F388
0x18009f22e  xor     edx, edx; Val
0x18009f230  mov     r8d, 478h; Size
0x18009f236  mov     rcx, rax; void *
0x18009f239  call    memset_0
0x18009f23e  mov     r8, rsi
0x18009f241  lea     r14, ?TraceSessionName@CensusJson@@0PAGA; "Census Listener"
0x18009f248  inc     r8
0x18009f24b  cmp     [r14+r8*2], r15w
0x18009f250  jnz     short loc_18009F248
0x18009f252  mov     rcx, [rbx+20h]
0x18009f256  add     r8, r8; Size
0x18009f259  add     rcx, 78h ; 'x'; void *
0x18009f25d  mov     rdx, r14; Src
0x18009f260  call    memcpy_0
0x18009f265  mov     rax, [rbx+20h]
0x18009f269  mov     r9d, r12d; ControlCode
0x18009f26c  mov     rdx, r14; InstanceName
0x18009f26f  xor     ecx, ecx; TraceHandle
0x18009f271  mov     dword ptr [rax], 478h
0x18009f277  mov     rax, [rbx+20h]
0x18009f27b  movups  xmm0, xmmword ptr [rbp+140h+ControlGuid.Data1]
0x18009f282  movdqu  xmmword ptr [rax+18h], xmm0
0x18009f287  mov     rax, [rbx+20h]
0x18009f28b  mov     [rax+28h], r12d
0x18009f28f  mov     rax, [rbx+20h]
0x18009f293  mov     dword ptr [rax+2Ch], 20000h
0x18009f29a  mov     rax, [rbx+20h]
0x18009f29e  mov     dword ptr [rax+74h], 78h ; 'x'
0x18009f2a5  mov     rax, [rbx+20h]
0x18009f2a9  mov     dword ptr [rax+30h], 400h
0x18009f2b0  mov     rax, [rbx+20h]
0x18009f2b4  mov     dword ptr [rax+34h], 40h ; '@'
0x18009f2bb  mov     rax, [rbx+20h]
0x18009f2bf  mov     dword ptr [rax+38h], 54h ; 'T'
0x18009f2c6  mov     rax, [rbx+20h]
0x18009f2ca  mov     dword ptr [rax+40h], 100h
0x18009f2d1  mov     rax, [rbx+20h]
0x18009f2d5  mov     [rax+44h], r12d
0x18009f2d9  mov     r8, [rbx+20h]; Properties
0x18009f2dd  call    cs:__imp_ControlTraceW
0x18009f2e3  mov     r8, [rbx+20h]; Properties
0x18009f2e7  lea     rcx, [rsp+240h+TraceHandle]; TraceHandle
0x18009f2ec  mov     rdx, r14; InstanceName
0x18009f2ef  call    cs:__imp_StartTraceW
0x18009f2f5  test    eax, eax
0x18009f2f7  jnz     loc_18009F388
0x18009f2fd  lea     rax, ?ProcessEventRecord@CensusJson@@CAXPEAU_EVENT_RECORD@@@Z; CensusJson::ProcessEventRecord(_EVENT_RECORD *)
0x18009f304  mov     dword ptr [rsp+240h+Logfile.1Ch], 10000100h
0x18009f30c  lea     rcx, [rsp+240h+Logfile]; Logfile
0x18009f311  mov     qword ptr [rbp+140h+Logfile.1A8h], rax
0x18009f318  mov     [rsp+240h+Logfile.LoggerName], r14
0x18009f31d  mov     [rbp+140h+Logfile.Context], rbx
0x18009f324  call    cs:__imp_OpenTraceW
0x18009f32a  mov     [rbx+30h], rax
0x18009f32e  cmp     rax, rsi
0x18009f331  jz      short loc_18009F388
0x18009f333  mov     rax, [rsp+240h+TraceHandle]
0x18009f338  lea     r9, [rbp+140h+ControlGuid]; ControlGuid
0x18009f33f  xor     edx, edx; EnableFlag
0x18009f341  mov     [rsp+240h+pstmTemplate], rax; TraceHandle
0x18009f346  mov     ecx, r12d; Enable
0x18009f349  lea     r8d, [rdx+5]; EnableLevel
0x18009f34d  call    cs:__imp_EnableTrace
0x18009f353  test    eax, eax
0x18009f355  jnz     short loc_18009F388
0x18009f357  mov     [rsp+240h+ppstm], r15; lpThreadId
0x18009f35c  lea     r8, ?TracerThreadProc@CensusJson@@CAKPEAX@Z; lpStartAddress
0x18009f363  mov     r9, rbx; lpParameter
0x18009f366  mov     dword ptr [rsp+240h+pstmTemplate], r15d; dwCreationFlags
0x18009f36b  xor     edx, edx; dwStackSize
0x18009f36d  xor     ecx, ecx; lpThreadAttributes
0x18009f36f  call    cs:__imp_CreateThread
0x18009f375  mov     [rbx+28h], rax
0x18009f379  test    rax, rax
0x18009f37c  jz      short loc_18009F388
0x18009f37e  mov     [rsp+240h+TraceHandle], rsi
0x18009f383  mov     edi, r15d
0x18009f386  jmp     short loc_18009F38D
0x18009f388  mov     rsi, [rsp+240h+TraceHandle]
0x18009f38d  lea     rax, [rsi-1]
0x18009f391  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009f395  ja      short loc_18009F3B4
0x18009f397  mov     r8, [rbx+20h]; Properties
0x18009f39b  mov     r9d, r12d; ControlCode
0x18009f39e  xor     edx, edx; InstanceName
0x18009f3a0  mov     rcx, rsi; TraceHandle
0x18009f3a3  call    cs:__imp_ControlTraceW
0x18009f3a9  mov     rcx, [rsp+240h+TraceHandle]; TraceHandle
0x18009f3ae  call    cs:__imp_CloseTrace
0x18009f3b4  test    edi, edi
0x18009f3b6  jns     short loc_18009F3C0
0x18009f3b8  mov     rcx, rbx; this
0x18009f3bb  call    ?CleanupMembers@CensusJson@@AEAAXXZ; CensusJson::CleanupMembers(void)
0x18009f3c0  mov     eax, edi
0x18009f3c2  mov     rcx, [rbp+140h+var_30]
0x18009f3c9  xor     rcx, rsp; StackCookie
0x18009f3cc  call    __security_check_cookie
0x18009f3d1  lea     r11, [rsp+240h+var_20]
0x18009f3d9  mov     rbx, [r11+40h]
0x18009f3dd  mov     rsi, [r11+48h]
0x18009f3e1  mov     rsp, r11
0x18009f3e4  pop     r15
0x18009f3e6  pop     r14
0x18009f3e8  pop     r12
0x18009f3ea  pop     rdi
0x18009f3eb  pop     rbp
0x18009f3ec  retn
```
