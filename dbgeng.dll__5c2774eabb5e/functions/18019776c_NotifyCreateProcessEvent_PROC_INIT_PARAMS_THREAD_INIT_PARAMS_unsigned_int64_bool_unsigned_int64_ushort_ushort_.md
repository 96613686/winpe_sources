# NotifyCreateProcessEvent(PROC_INIT_PARAMS *,THREAD_INIT_PARAMS *,unsigned __int64,bool,unsigned __int64,ushort *,ushort *,IMAGE_HEADER_INFO *,unsigned __int64,int,int)

- ea: `0x18019776c`
- end: `0x180197db9`
- name: `?NotifyCreateProcessEvent@@YAKPEAUPROC_INIT_PARAMS@@PEAUTHREAD_INIT_PARAMS@@_K_N2PEAG4PEAUIMAGE_HEADER_INFO@@2HH@Z`
- size: `1613`
- prototype: `unsigned int(struct PROC_INIT_PARAMS *, struct THREAD_INIT_PARAMS *, unsigned __int64, bool, unsigned __int64, unsigned __int16 *, unsigned __int16 *, struct IMAGE_HEADER_INFO *, unsigned __int64, int, int)`
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18023a610`
- `0x18023be00`

## callees

- `0x180071a60`
- `0x1800793cc`
- `0x18007ac6c`
- `0x18007cf9c`
- `0x18007d14c`
- `0x18007d92c`
- `0x18007daa4`
- `0x18007e420`
- `0x180080870`
- `0x180081918`
- `0x18008d550`
- `0x18008fe74`
- `0x1800911ac`
- `0x18009cda0`
- `0x1800b717c`
- `0x1800b94c4`
- `0x1800bd580`
- `0x1800c12b8`
- `0x1800cca3c`
- `0x1800cfed0`
- `0x1800d9e8c`
- `0x1800f0f40`
- `0x1800f16fc`
- `0x18018ef88`
- `0x1801956bc`
- `0x180195bac`
- `0x180196b28`
- `0x18019776c`
- `0x1802394dc`
- `0x180285fd8`
- `0x1802d644c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180197b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180197b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180197b05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180197b14`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180197b46`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180197b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180197cbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180197cbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801979dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197d71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801979dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180197d71`

## string_xrefs

- `0x18019781b`: `IDebugEventCallbacks::CreateProcess`
- `0x180197849`: `*** Create process %x\n`
- `0x1801978db`: `WARNING: Duplicate process create event for %x\n`
- `0x180197d44`: `Unable to allocate process record for create process event\n`
- `0x180197d87`: `Can't create process `
- `0x180197d26`: `Create process unable to locate process or thread %x:%x\n`
- `0x1801979a5`: `Process created: %lx.%lx\n`
- `0x1801979f7`: `Create process `

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NotifyCreateProcessEvent(
        struct PROC_INIT_PARAMS *a1,
        struct THREAD_INIT_PARAMS *a2,
        HANDLE a3,
        int a4,
        unsigned __int64 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        struct IMAGE_HEADER_INFO *a8,
        unsigned __int64 a9,
        __int16 a10,
        int a11)
{
  struct IMAGE_HEADER_INFO *v14; // r15
  int v15; // r9d
  struct ImageInfo *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  ProcessInfo *ProcessBySystemId; // rax
  struct ProcessInfo *v22; // rbx
  struct ThreadInfo *ThreadByHandle; // rax
  unsigned int v24; // edx
  __int64 i; // rcx
  unsigned int v26; // ebx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // r12
  HANDLE v30; // rdi
  bool v31; // si
  const unsigned __int16 *v32; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE v34; // rax
  BOOL v35; // eax
  struct ImageInfo *ImageByOffset; // rax
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  struct DebugClient *v39; // rdx
  unsigned int v40; // ebx
  char v42; // [rsp+58h] [rbp-B0h] BYREF
  char v43; // [rsp+59h] [rbp-AFh]
  unsigned __int16 *v44; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+68h] [rbp-A0h]
  HANDLE TargetHandle; // [rsp+70h] [rbp-98h] BYREF
  struct PROC_INIT_PARAMS *v47; // [rsp+78h] [rbp-90h]
  void **v48; // [rsp+88h] [rbp-80h] BYREF
  int v49; // [rsp+90h] [rbp-78h]
  const wchar_t *v50; // [rsp+98h] [rbp-70h]
  HANDLE v51; // [rsp+A0h] [rbp-68h]
  __int64 v52; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v53; // [rsp+B0h] [rbp-58h]
  int v54; // [rsp+B8h] [rbp-50h]
  unsigned __int16 *v55; // [rsp+C0h] [rbp-48h]
  const unsigned __int16 *v56; // [rsp+C8h] [rbp-40h]
  int v57; // [rsp+D0h] [rbp-38h]
  int v58; // [rsp+D4h] [rbp-34h]
  __int64 v59; // [rsp+D8h] [rbp-30h]
  __int64 v60; // [rsp+E0h] [rbp-28h]
  __int64 v61; // [rsp+E8h] [rbp-20h]
  __int64 v62; // [rsp+F8h] [rbp-10h]
  _BYTE v63[160]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v64[3]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v65; // [rsp+1C0h] [rbp+B8h] BYREF
  const unsigned __int16 *v66; // [rsp+218h] [rbp+110h] BYREF
  unsigned int v67; // [rsp+224h] [rbp+11Ch]
  char v68; // [rsp+230h] [rbp+128h] BYREF

  v62 = -2;
  v43 = a4;
  v47 = a1;
  v45 = a5;
  v14 = a8;
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>((unsigned int)&v66, (unsigned int)&v68, 200, a4, 1);
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>((unsigned int)v64, (unsigned int)&v65, 40, v15, 1);
  IMAGE_HEADER_INFO::IMAGE_HEADER_INFO((IMAGE_HEADER_INFO *)v63);
  v49 = 16;
  v50 = L"IDebugEventCallbacks::CreateProcess";
  v48 = &CreateProcessEventApcData::`vftable';
  v16 = 0;
  TargetHandle = 0;
  StartOutLine(8u, 1u);
  VerbOut(L"*** Create process %x\n", g_EventProcessSysId);
  if ( !a11 )
  {
    for ( i = *((_QWORD *)g_EventTarget + 7); i; i = *(_QWORD *)(i + 96) )
    {
      if ( ((*(_DWORD *)(i + 424) & 4) != 0 || *(_QWORD *)(i + 416) == *((_QWORD *)a1 + 2))
        && *(_DWORD *)(i + 388) == g_EventProcessSysId )
      {
        if ( (*(_DWORD *)(i + 424) & 4) == 0 )
          WarnOut(L"WARNING: Duplicate process create event for %x\n", g_EventProcessSysId);
        v26 = 9;
        goto LABEL_56;
      }
    }
    *(_DWORD *)a1 = g_EventProcessSysId;
    v27 = (unsigned __int16 *)operator new(0x680u, (const struct std::nothrow_t *)&std::nothrow);
    v44 = v27;
    if ( v27 )
      v22 = ProcessInfo::ProcessInfo((ProcessInfo *)v27, g_EventTarget, a1, 0);
    else
      v22 = 0;
    if ( v22 )
    {
      *(_DWORD *)a2 = g_EventThreadSysId;
      v28 = (unsigned __int16 *)operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
      v44 = v28;
      if ( v28 )
        ThreadByHandle = ThreadInfo::ThreadInfo((ThreadInfo *)v28, v22, a2, 0);
      else
        ThreadByHandle = 0;
      goto LABEL_22;
    }
    goto LABEL_60;
  }
  if ( !a8 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
  ProcessBySystemId = TargetInfo::FindProcessBySystemId(g_EventTarget, g_EventProcessSysId);
  v22 = ProcessBySystemId;
  if ( !ProcessBySystemId )
  {
LABEL_60:
    ErrOut(L"Unable to allocate process record for create process event\n");
    ErrOut(L"Process %x will be lost\n", g_EventProcessSysId);
    if ( !g_EngNotify )
    {
      GetSystemTimeAsFileTime(&g_LastEventTime);
      g_LastEventType = 16;
      DbsDynamicString<unsigned short>::CopyStr(&g_LastEventDesc, L"Can't create process ", 0xFFFFFFFFLL);
      DbsDynamicString<unsigned short>::AppendHexNumber((DbsDynamicBuffer *)&g_LastEventDesc, 0);
    }
    goto LABEL_58;
  }
  ThreadByHandle = ProcessInfo::FindThreadByHandle(ProcessBySystemId, *((_QWORD *)a2 + 3));
LABEL_22:
  if ( !ThreadByHandle )
  {
    ProcessInfo::`scalar deleting destructor'(v22, v24);
    goto LABEL_60;
  }
  FindEventProcessThread();
  if ( g_EventProcess && g_EventThread )
  {
    VerbOut(L"Process created: %lx.%lx\n", g_EventProcessSysId, g_EventThreadSysId);
    if ( g_EngNotify )
    {
      *((_BYTE *)g_EventTarget + 42) = 1;
      v26 = 0;
      goto LABEL_56;
    }
    v29 = 0;
    v44 = 0;
    v30 = a3;
    GetSystemTimeAsFileTime(&g_LastEventTime);
    g_LastEventType = 16;
    DbsDynamicString<unsigned short>::CopyStr(&g_LastEventDesc, L"Create process ", 0xFFFFFFFFLL);
    DbsDynamicString<unsigned short>::AppendIntNumber(&g_LastEventDesc, *((unsigned int *)g_EventProcess + 96), 0);
    DbsDynamicString<unsigned short>::AppendChar((DbsDynamicBuffer *)&g_LastEventDesc);
    DbsDynamicString<unsigned short>::AppendHexNumber((DbsDynamicBuffer *)&g_LastEventDesc, 0);
    ThreadChangedForBreakpoints();
    if ( !a11 )
    {
      ++g_EngNotify;
      v31 = 1;
      v42 = 1;
      if ( !a8 )
      {
        GetModuleImageName((__int64)&v66, a3, v45, a9, a10, (DbsDynamicBuffer *)&v66, &v42);
        IMAGE_HEADER_INFO::Read((IMAGE_HEADER_INFO *)v63, g_EventProcess, v45, 0, 11775);
        v14 = (struct IMAGE_HEADER_INFO *)v63;
        v32 = 0;
        if ( v67 >= 2 )
          v32 = v66;
        CreateModuleNameFromPath(v32, v64);
        v29 = v66;
        v44 = (unsigned __int16 *)v64[0];
        v31 = v42;
      }
      if ( a3 )
      {
        CurrentProcess = GetCurrentProcess();
        v34 = GetCurrentProcess();
        if ( DuplicateHandle(v34, a3, CurrentProcess, &TargetHandle, 0, 1, 2u) )
          v30 = TargetHandle;
      }
      v35 = g_EventTarget && (unsigned int)(*((_DWORD *)g_EventTarget + 1026) - 2) <= 1;
      NotifyLoadModuleEvent((unsigned __int64)v30, 0, v45, v44, v29, v31, v14, v35, 0);
      ImageByOffset = ProcessInfo::FindImageByOffset(g_EventProcess, v45, 0, 0);
      v16 = ImageByOffset;
      if ( ImageByOffset )
        *((_QWORD *)g_EventProcess + 37) = ImageByOffset;
      --g_EngNotify;
    }
    if ( HIDWORD((*off_180799B80)[1]) < 2 )
      v37 = 0;
    else
      v37 = (const unsigned __int16 *)(*off_180799B80)[0];
    v38 = BreakOnThisImageTail(v29, v37);
    if ( (unsigned int)dword_180799B44 <= 1 && v38 )
    {
      v40 = 6;
    }
    else
    {
      v40 = 9;
      if ( !v38 )
      {
LABEL_50:
        *((_BYTE *)g_EventTarget + 42) = 1;
        v51 = v30;
        v52 = *((_QWORD *)v47 + 2);
        v53 = v45;
        v54 = *((_DWORD *)v14 + 5);
        v55 = v44;
        v56 = v29;
        v57 = *((_DWORD *)v14 + 3);
        v58 = *((_DWORD *)v14 + 4);
        v59 = *((_QWORD *)a2 + 3);
        v60 = *((_QWORD *)a2 + 2);
        v61 = *((_QWORD *)a2 + 4);
        v26 = SendEvent((struct AnyApcData *)&v48, v40);
        if ( v16 && *((HANDLE *)v16 + 3) != v30 && v30 != a3 )
          goto LABEL_56;
        goto LABEL_53;
      }
    }
    v40 = ExecuteEventCommand(v40, v39, dword_180799B60, qword_180799B68);
    goto LABEL_50;
  }
  ErrOut(L"Create process unable to locate process or thread %x:%x\n", g_EventProcessSysId, g_EventThreadSysId);
LABEL_58:
  v26 = 6;
LABEL_53:
  if ( v43 && a3 )
    CloseHandle(a3);
LABEL_56:
  IMAGE_HEADER_INFO::~IMAGE_HEADER_INFO((IMAGE_HEADER_INFO *)v63);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v64);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v66);
  return v26;
}

```

## disassembly

```asm
0x18019776c  mov     rax, rsp
0x18019776f  push    rbp
0x180197770  push    rsi
0x180197771  push    rdi
0x180197772  push    r12
0x180197774  push    r13
0x180197776  push    r14
0x180197778  push    r15
0x18019777a  lea     rbp, [rax-308h]
0x180197781  sub     rsp, 3D0h
0x180197788  mov     [rbp+300h+var_310], 0FFFFFFFFFFFFFFFEh
0x180197790  mov     [rax+20h], rbx
0x180197794  mov     rax, cs:__security_cookie
0x18019779b  xor     rax, rsp
0x18019779e  mov     [rbp+300h+var_40], rax
0x1801977a5  mov     byte ptr [rsp+400h+var_3B0+1], r9b
0x1801977aa  mov     r14, r8
0x1801977ad  mov     r13, rdx
0x1801977b0  mov     rbx, rcx
0x1801977b3  mov     [rsp+400h+var_390], rcx
0x1801977b8  mov     rax, [rbp+300h+arg_20]
0x1801977bf  mov     [rsp+400h+var_3A0], rax
0x1801977c4  mov     r15, [rbp+300h+arg_38]
0x1801977cb  mov     byte ptr [rsp+400h+dwDesiredAccess], 1
0x1801977d0  mov     r8d, 0C8h
0x1801977d6  lea     rdx, [rbp+300h+var_1D8]
0x1801977dd  lea     rcx, [rbp+300h+var_1F0]
0x1801977e4  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1801977e9  nop
0x1801977ea  mov     byte ptr [rsp+400h+dwDesiredAccess], 1
0x1801977ef  mov     r8d, 28h ; '('
0x1801977f5  lea     rdx, [rbp+300h+var_248]
0x1801977fc  lea     rcx, [rbp+300h+var_260]
0x180197803  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x180197808  nop
0x180197809  lea     rcx, [rbp+300h+var_300]; this
0x18019780d  call    ??0IMAGE_HEADER_INFO@@QEAA@XZ; IMAGE_HEADER_INFO::IMAGE_HEADER_INFO(void)
0x180197812  nop
0x180197813  mov     edi, 10h
0x180197818  mov     [rbp+300h+var_378], edi
0x18019781b  lea     rax, aIdebugeventcal_0; "IDebugEventCallbacks::CreateProcess"
0x180197822  mov     [rbp+300h+var_370], rax
0x180197826  lea     rax, ??_7CreateProcessEventApcData@@6B@; const CreateProcessEventApcData::`vftable'
0x18019782d  mov     [rbp+300h+var_380], rax
0x180197831  xor     esi, esi
0x180197833  mov     [rsp+400h+TargetHandle], rsi
0x180197838  lea     edx, [rdi-0Fh]; unsigned int
0x18019783b  lea     ecx, [rdi-8]; unsigned int
0x18019783e  call    ?StartOutLine@@YAXKK@Z; StartOutLine(ulong,ulong)
0x180197843  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197849  lea     rcx, aCreateProcessX; "*** Create process %x\n"
0x180197850  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180197855  cmp     [rbp+300h+arg_50], esi
0x18019785b  jz      short loc_180197896
0x18019785d  test    r15, r15
0x180197860  jnz     short loc_180197867
0x180197862  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180197867  mov     edx, cs:?g_EventProcessSysId@@3KA; unsigned int
0x18019786d  mov     rcx, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; this
0x180197874  call    ?FindProcessBySystemId@TargetInfo@@QEAAPEAVProcessInfo@@K@Z; TargetInfo::FindProcessBySystemId(ulong)
0x180197879  mov     rbx, rax
0x18019787c  test    rax, rax
0x18019787f  jz      loc_180197D44
0x180197885  mov     rdx, [r13+18h]; unsigned __int64
0x180197889  mov     rcx, rax; this
0x18019788c  call    ?FindThreadByHandle@ProcessInfo@@QEAAPEAVThreadInfo@@_K@Z; ProcessInfo::FindThreadByHandle(unsigned __int64)
0x180197891  jmp     loc_180197970
0x180197896  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x18019789d  mov     rcx, [rax+38h]
0x1801978a1  mov     r8d, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x1801978a8  test    rcx, rcx
0x1801978ab  jz      short loc_1801978F1
0x1801978ad  mov     edx, [rcx+1A8h]
0x1801978b3  and     edx, 4
0x1801978b6  jnz     short loc_1801978C5
0x1801978b8  mov     rax, [rbx+10h]
0x1801978bc  cmp     [rcx+1A0h], rax
0x1801978c3  jnz     short loc_1801978CE
0x1801978c5  cmp     [rcx+184h], r8d
0x1801978cc  jz      short loc_1801978D4
0x1801978ce  mov     rcx, [rcx+60h]
0x1801978d2  jmp     short loc_1801978A8
0x1801978d4  test    edx, edx
0x1801978d6  jnz     short loc_1801978E7
0x1801978d8  mov     edx, r8d
0x1801978db  lea     rcx, aWarningDuplica_0; "WARNING: Duplicate process create event"...
0x1801978e2  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1801978e7  mov     ebx, 9
0x1801978ec  jmp     loc_180197CC9
0x1801978f1  mov     [rbx], r8d
0x1801978f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801978fb  mov     ecx, 680h; unsigned __int64
0x180197900  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180197905  mov     [rsp+400h+var_3A8], rax
0x18019790a  test    rax, rax
0x18019790d  jz      short loc_180197929
0x18019790f  xor     r9d, r9d; struct ISvcProcess *
0x180197912  mov     r8, rbx; struct PROC_INIT_PARAMS *
0x180197915  mov     rdx, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; struct TargetInfo *
0x18019791c  mov     rcx, rax; this
0x18019791f  call    ??0ProcessInfo@@QEAA@PEAVTargetInfo@@PEAUPROC_INIT_PARAMS@@PEAUISvcProcess@@@Z; ProcessInfo::ProcessInfo(TargetInfo *,PROC_INIT_PARAMS *,ISvcProcess *)
0x180197924  mov     rbx, rax
0x180197927  jmp     short loc_18019792C
0x180197929  mov     rbx, rsi
0x18019792c  test    rbx, rbx
0x18019792f  jz      loc_180197D44
0x180197935  mov     eax, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x18019793b  mov     [r13+0], eax
0x18019793f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180197946  mov     ecx, 178h; unsigned __int64
0x18019794b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180197950  mov     [rsp+400h+var_3A8], rax
0x180197955  test    rax, rax
0x180197958  jz      short loc_18019796D
0x18019795a  xor     r9d, r9d; struct ISvcExecutionUnit *
0x18019795d  mov     r8, r13; struct THREAD_INIT_PARAMS *
0x180197960  mov     rdx, rbx; struct ProcessInfo *
0x180197963  mov     rcx, rax; this
0x180197966  call    ??0ThreadInfo@@QEAA@PEAVProcessInfo@@PEAUTHREAD_INIT_PARAMS@@PEAUISvcExecutionUnit@@@Z; ThreadInfo::ThreadInfo(ProcessInfo *,THREAD_INIT_PARAMS *,ISvcExecutionUnit *)
0x18019796b  jmp     short loc_180197970
0x18019796d  mov     rax, rsi
0x180197970  test    rax, rax
0x180197973  jz      loc_180197D3C
0x180197979  call    ?FindEventProcessThread@@YAXXZ; FindEventProcessThread(void)
0x18019797e  cmp     cs:?g_EventProcess@@3PEAVProcessInfo@@EA, rsi; ProcessInfo * g_EventProcess
0x180197985  jz      loc_180197D19
0x18019798b  cmp     cs:?g_EventThread@@3PEAVThreadInfo@@EA, rsi; ThreadInfo * g_EventThread
0x180197992  jz      loc_180197D19
0x180197998  mov     r8d, cs:?g_EventThreadSysId@@3KA; ulong g_EventThreadSysId
0x18019799f  mov     edx, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x1801979a5  lea     rcx, aProcessCreated; "Process created: %lx.%lx\n"
0x1801979ac  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1801979b1  cmp     cs:?g_EngNotify@@3KA, esi; ulong g_EngNotify
0x1801979b7  jbe     short loc_1801979CB
0x1801979b9  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x1801979c0  mov     byte ptr [rax+2Ah], 1
0x1801979c4  mov     ebx, esi
0x1801979c6  jmp     loc_180197CC9
0x1801979cb  mov     r12, rsi
0x1801979ce  mov     [rsp+400h+var_3A8], rsi
0x1801979d3  mov     rdi, r14
0x1801979d6  lea     rcx, ?g_LastEventTime@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x1801979dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1801979e4  nop     dword ptr [rax+rax+00h]
0x1801979e9  mov     cs:?g_LastEventType@@3KA, 10h; ulong g_LastEventType
0x1801979f3  or      r8d, 0FFFFFFFFh
0x1801979f7  lea     rdx, aCreateProcess_0; "Create process "
0x1801979fe  lea     rbx, ?g_LastEventDesc@@3V?$DbsDeclDynamicString@G$0MI@$00@@A; DbsDeclDynamicString<ushort,200,1> g_LastEventDesc
0x180197a05  mov     rcx, rbx
0x180197a08  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x180197a0d  mov     rax, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; ProcessInfo * g_EventProcess
0x180197a14  mov     edx, [rax+180h]
0x180197a1a  xor     r8d, r8d
0x180197a1d  mov     rcx, rbx
0x180197a20  call    ?AppendIntNumber@?$DbsDynamicString@G@@QEAAJ_KKK@Z; DbsDynamicString<ushort>::AppendIntNumber(unsigned __int64,ulong,ulong)
0x180197a25  mov     edx, 3Ah ; ':'
0x180197a2a  mov     rcx, rbx; this
0x180197a2d  call    ?AppendChar@?$DbsDynamicString@G@@QEAAJG@Z; DbsDynamicString<ushort>::AppendChar(ushort)
0x180197a32  mov     r8d, cs:?g_EventProcessSysId@@3KA; ulong g_EventProcessSysId
0x180197a39  mov     [rsp+400h+dwDesiredAccess], esi; int
0x180197a3d  xor     r9d, r9d
0x180197a40  mov     rcx, rbx; this
0x180197a43  call    ?AppendHexNumber@?$DbsDynamicString@G@@QEAAJPEBG_KKK@Z; DbsDynamicString<ushort>::AppendHexNumber(ushort const *,unsigned __int64,ulong,ulong)
0x180197a48  call    ?ThreadChangedForBreakpoints@@YAXXZ; ThreadChangedForBreakpoints(void)
0x180197a4d  cmp     [rbp+300h+arg_50], r12d
0x180197a54  jnz     loc_180197BDF
0x180197a5a  inc     cs:?g_EngNotify@@3KA; ulong g_EngNotify
0x180197a60  mov     sil, 1
0x180197a63  mov     byte ptr [rsp+400h+var_3B0], sil
0x180197a68  test    r15, r15
0x180197a6b  jnz     loc_180197B00
0x180197a71  movzx   eax, [rbp+300h+arg_48]
0x180197a78  lea     rcx, [rsp+400h+var_3B0]
0x180197a7d  mov     qword ptr [rsp+400h+dwOptions], rcx
0x180197a82  lea     rcx, [rbp+300h+var_1F0]
0x180197a89  mov     qword ptr [rsp+400h+bInheritHandle], rcx
0x180197a8e  mov     word ptr [rsp+400h+dwDesiredAccess], ax
0x180197a93  mov     r9, [rbp+300h+arg_40]
0x180197a9a  mov     r8, [rsp+400h+var_3A0]
0x180197a9f  mov     rdx, r14
0x180197aa2  call    ?GetModuleImageName@@YAXPEAVThreadInfo@@_K11GPEAV?$DbsDynamicString@G@@PEA_N@Z; GetModuleImageName(ThreadInfo *,unsigned __int64,unsigned __int64,unsigned __int64,ushort,DbsDynamicString<ushort> *,bool *)
0x180197aa7  mov     [rsp+400h+dwDesiredAccess], 2DFFh; unsigned int
0x180197aaf  xor     r9d, r9d; void *
0x180197ab2  mov     r8, [rsp+400h+var_3A0]; unsigned __int64
0x180197ab7  mov     rdx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; struct ProcessInfo *
0x180197abe  lea     rcx, [rbp+300h+var_300]; this
0x180197ac2  call    ?Read@IMAGE_HEADER_INFO@@QEAAKPEAVProcessInfo@@_KPEAXK@Z; IMAGE_HEADER_INFO::Read(ProcessInfo *,unsigned __int64,void *,ulong)
0x180197ac7  lea     r15, [rbp+300h+var_300]
0x180197acb  xor     ecx, ecx
0x180197acd  cmp     [rbp+300h+var_1E4], 2
0x180197ad4  cmovnb  rcx, [rbp+300h+var_1F0]
0x180197adc  lea     rdx, [rbp+300h+var_260]
0x180197ae3  call    ?CreateModuleNameFromPath@@YAJPEBGPEAV?$DbsDynamicString@G@@@Z; CreateModuleNameFromPath(ushort const *,DbsDynamicString<ushort> *)
0x180197ae8  mov     r12, [rbp+300h+var_1F0]
0x180197aef  mov     rax, [rbp+300h+var_260]
0x180197af6  mov     [rsp+400h+var_3A8], rax
0x180197afb  mov     sil, byte ptr [rsp+400h+var_3B0]
0x180197b00  test    r14, r14
0x180197b03  jz      short loc_180197B5A
0x180197b05  call    cs:__imp_GetCurrentProcess
0x180197b0c  nop     dword ptr [rax+rax+00h]
0x180197b11  mov     rbx, rax
0x180197b14  call    cs:__imp_GetCurrentProcess
0x180197b1b  nop     dword ptr [rax+rax+00h]
0x180197b20  mov     [rsp+400h+dwOptions], 2; dwOptions
0x180197b28  mov     [rsp+400h+bInheritHandle], 1; bInheritHandle
0x180197b30  mov     [rsp+400h+dwDesiredAccess], 0; dwDesiredAccess
0x180197b38  lea     r9, [rsp+400h+TargetHandle]; lpTargetHandle
0x180197b3d  mov     r8, rbx; hTargetProcessHandle
0x180197b40  mov     rdx, r14; hSourceHandle
0x180197b43  mov     rcx, rax; hSourceProcessHandle
0x180197b46  call    cs:__imp_DuplicateHandle
0x180197b4d  nop     dword ptr [rax+rax+00h]
0x180197b52  test    eax, eax
0x180197b54  cmovnz  rdi, [rsp+400h+TargetHandle]
0x180197b5a  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x180197b61  test    rax, rax
0x180197b64  jz      short loc_180197B7B
0x180197b66  mov     eax, [rax+1008h]
0x180197b6c  sub     eax, 2
0x180197b6f  cmp     eax, 1
0x180197b72  ja      short loc_180197B7B
0x180197b74  mov     eax, 1
0x180197b79  jmp     short loc_180197B7D
0x180197b7b  xor     eax, eax
0x180197b7d  mov     dword ptr [rsp+40h], 0; int
0x180197b85  mov     [rsp+400h+var_3C8], eax; int
0x180197b89  mov     qword ptr [rsp+400h+dwOptions], r15; struct IMAGE_HEADER_INFO *
0x180197b8e  mov     byte ptr [rsp+400h+bInheritHandle], sil; bool
0x180197b93  mov     qword ptr [rsp+400h+dwDesiredAccess], r12; unsigned __int16 *
0x180197b98  mov     r9, [rsp+400h+var_3A8]; unsigned __int16 *
0x180197b9d  mov     r8, [rsp+400h+var_3A0]; unsigned __int64
0x180197ba2  xor     edx, edx; bool
0x180197ba4  mov     rcx, rdi; unsigned __int64
0x180197ba7  call    ?NotifyLoadModuleEvent@@YAK_K_N0PEBG21PEAUIMAGE_HEADER_INFO@@HH@Z; NotifyLoadModuleEvent(unsigned __int64,bool,unsigned __int64,ushort const *,ushort const *,bool,IMAGE_HEADER_INFO *,int,int)
0x180197bac  xor     r9d, r9d; int
0x180197baf  xor     r8d, r8d; int
0x180197bb2  mov     rdx, [rsp+400h+var_3A0]; unsigned __int64
0x180197bb7  mov     rcx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; this
0x180197bbe  call    ?FindImageByOffset@ProcessInfo@@QEAAPEAVImageInfo@@_KHH@Z; ProcessInfo::FindImageByOffset(unsigned __int64,int,int)
0x180197bc3  mov     rsi, rax
0x180197bc6  test    rax, rax
0x180197bc9  jz      short loc_180197BD9
0x180197bcb  mov     rcx, cs:?g_EventProcess@@3PEAVProcessInfo@@EA; ProcessInfo * g_EventProcess
0x180197bd2  mov     [rcx+128h], rax
0x180197bd9  dec     cs:?g_EngNotify@@3KA; ulong g_EngNotify
0x180197bdf  mov     rax, cs:off_180799B80
0x180197be6  cmp     dword ptr [rax+0Ch], 2
0x180197bea  jb      short loc_180197BF1
0x180197bec  mov     rdx, [rax]
0x180197bef  jmp     short loc_180197BF3
0x180197bf1  xor     edx, edx; unsigned __int16 *
0x180197bf3  mov     rcx, r12; unsigned __int16 *
0x180197bf6  call    ?BreakOnThisImageTail@@YAHPEBG0@Z; BreakOnThisImageTail(ushort const *,ushort const *)
0x180197bfb  cmp     cs:dword_180799B44, 1
0x180197c02  ja      short loc_180197C0F
0x180197c04  test    eax, eax
0x180197c06  jz      short loc_180197C0F
0x180197c08  mov     ebx, 6
0x180197c0d  jmp     short loc_180197C18
0x180197c0f  mov     ebx, 9
0x180197c14  test    eax, eax
0x180197c16  jz      short loc_180197C2F
0x180197c18  mov     r9, cs:qword_180799B68; unsigned __int16 *
0x180197c1f  mov     r8d, cs:dword_180799B60; unsigned int
0x180197c26  mov     ecx, ebx; unsigned int
0x180197c28  call    ?ExecuteEventCommand@@YAKKPEAVDebugClient@@KPEBG@Z; ExecuteEventCommand(ulong,DebugClient *,ulong,ushort const *)
0x180197c2d  mov     ebx, eax
0x180197c2f  mov     rax, cs:?g_EventTarget@@3PEAVTargetInfo@@EA; TargetInfo * g_EventTarget
0x180197c36  mov     byte ptr [rax+2Ah], 1
0x180197c3a  mov     [rbp+300h+var_368], rdi
0x180197c3e  mov     rax, [rsp+400h+var_390]
0x180197c43  mov     rax, [rax+10h]
0x180197c47  mov     [rbp+300h+var_360], rax
0x180197c4b  mov     rax, [rsp+400h+var_3A0]
0x180197c50  mov     [rbp+300h+var_358], rax
0x180197c54  mov     eax, [r15+14h]
0x180197c58  mov     [rbp+300h+var_350], eax
0x180197c5b  mov     rax, [rsp+400h+var_3A8]
0x180197c60  mov     [rbp+300h+var_348], rax
0x180197c64  mov     [rbp+300h+var_340], r12
0x180197c68  mov     eax, [r15+0Ch]
0x180197c6c  mov     [rbp+300h+var_338], eax
0x180197c6f  mov     eax, [r15+10h]
0x180197c73  mov     [rbp+300h+var_334], eax
0x180197c76  mov     rax, [r13+18h]
0x180197c7a  mov     [rbp+300h+var_330], rax
0x180197c7e  mov     rax, [r13+10h]
0x180197c82  mov     [rbp+300h+var_328], rax
0x180197c86  mov     rax, [r13+20h]
0x180197c8a  mov     [rbp+300h+var_320], rax
0x180197c8e  mov     edx, ebx; unsigned int
0x180197c90  lea     rcx, [rbp+300h+var_380]; struct AnyApcData *
0x180197c94  call    ?SendEvent@@YAKPEAUAnyApcData@@K@Z; SendEvent(AnyApcData *,ulong)
0x180197c99  mov     ebx, eax
0x180197c9b  test    rsi, rsi
0x180197c9e  jz      short loc_180197CAB
0x180197ca0  cmp     [rsi+18h], rdi
0x180197ca4  jz      short loc_180197CAB
0x180197ca6  cmp     rdi, r14
  ... truncated ...
```
