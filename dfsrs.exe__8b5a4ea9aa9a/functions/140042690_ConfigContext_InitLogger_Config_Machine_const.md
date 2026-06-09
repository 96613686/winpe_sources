# ConfigContext::InitLogger(Config::Machine const *)

- ea: `0x140042690`
- end: `0x140042d40`
- name: `?InitLogger@ConfigContext@@QEAAXPEBVMachine@Config@@@Z`
- size: `1712`
- prototype: `void __fastcall(ConfigContext *__hidden this, const struct Config::Machine *)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14000fad0`
- `0x140045da0`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000cb00`
- `0x14000cd1c`
- `0x14000cdc0`
- `0x14000dd10`
- `0x14000e34c`
- `0x140014df4`
- `0x140019358`
- `0x14001a584`
- `0x14001a87c`
- `0x1400249f4`
- `0x14002c2f4`
- `0x140035304`
- `0x14003cd40`
- `0x14003f654`
- `0x140042690`
- `0x140042db8`
- `0x14004485c`
- `0x140045c88`
- `0x140047c58`
- `0x140047cf0`
- `0x140047e14`
- `0x1401af7c0`
- `0x1401b7cc8`
- `0x1401b8e5c`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401bd29c`
- `0x1401befb8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400427ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400428df`
- `KERNEL32!GetCurrentThreadId` at `0x1400429d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400427ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400428df`
- `KERNEL32!GetCurrentThreadId` at `0x1400429d7`

## string_xrefs

- `0x140042818`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x140042909`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x140042a01`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x14004272d`: `ConfigContext::InitLogger`
- `0x140042788`: `ConfigContext::InitLogger`
- `0x14004297d`: `ConfigContext::InitLogger`
- `0x140042a92`: `ConfigContext::InitLogger`
- `0x140042c07`: `ConfigContext::InitLogger`
- `0x140042771`: `Log file path: %ws`
- `0x140042b80`: `Log file path: %ws`
- `0x14004280c`: `ConfigContext::InitLogger`
- `0x1400428fd`: `ConfigContext::InitLogger`
- `0x1400429f5`: `ConfigContext::InitLogger`
- `0x1400429bd`: `(Ignored) New log path is in overlaps with %?, newLogPath:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConfigContext::InitLogger(ConfigContext *this, const struct Config::Machine *a2)
{
  struct FrsStatus *v3; // rbx
  Config::BoolParam *v4; // r15
  __int64 v5; // rdx
  Config::BoolParam *v6; // r12
  __int64 v7; // rdx
  Config::BoolParam *v8; // r13
  __int64 v9; // rdx
  _QWORD *v10; // r14
  LPCRITICAL_SECTION v11; // rax
  unsigned int DirectoryW; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  WorkPath *v15; // rdi
  struct FrsStatus *v16; // rax
  DWORD v17; // eax
  __int64 v18; // rcx
  struct WorkPath *v19; // rax
  DWORD v20; // eax
  __int64 v21; // rcx
  FrsLogger *v22; // rcx
  EventLog *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // esi
  FrsLogger *v26; // rcx
  LPCRITICAL_SECTION v27; // rax
  unsigned int *v28; // rdi
  LPCWSTR v29; // rbx
  Dword *v30; // rax
  __int64 DisplayPath; // rdi
  __int64 v32; // rbx
  Dword *v33; // rax
  struct FrsStatus *v34; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpPathName; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch]
  int v38; // [rsp+68h] [rbp-98h]
  int v39; // [rsp+6Ch] [rbp-94h]
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v44; // [rsp+88h] [rbp-78h]
  WorkPath *v45; // [rsp+90h] [rbp-70h] BYREF
  Config::BoolParam *v46; // [rsp+98h] [rbp-68h]
  _BYTE v47[144]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+130h] [rbp+30h]
  void *v49[2]; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v50; // [rsp+150h] [rbp+50h]
  const wchar_t *v51; // [rsp+158h] [rbp+58h] BYREF
  int v52; // [rsp+160h] [rbp+60h]
  int v53; // [rsp+164h] [rbp+64h]
  const wchar_t *v54; // [rsp+168h] [rbp+68h]
  _BYTE v55[56]; // [rsp+188h] [rbp+88h] BYREF

  v3 = 0;
  v34 = 0;
  v4 = (const struct Config::Machine *)((char *)a2 + 424);
  v39 = Config::BoolParam::Get((const struct Config::Machine *)((char *)a2 + 424));
  v6 = (Config::BoolParam *)(v5 + 552);
  v36 = Config::BoolParam::Get((Config::BoolParam *)(v5 + 552));
  v8 = (Config::BoolParam *)(v7 + 592);
  v37 = Config::BoolParam::Get((Config::BoolParam *)(v7 + 592));
  v10 = (_QWORD *)(v9 + 504);
  lpPathName = (LPCWSTR)(*(_QWORD *)(v9 + 504) + 18LL);
  v46 = (Config::BoolParam *)(v9 + 512);
  v38 = Config::BoolParam::Get((Config::BoolParam *)(v9 + 512));
  v11 = g_DebugLog;
  if ( g_DebugLog )
  {
    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v49[0] = L"ConfigContext::InitLogger";
      v49[1] = (void *)0x400000FCALL;
      v50 = L"CCTX";
      dbgobj::DbgPrint<unsigned short,unsigned short const *>(v49, L"Log file path: %ws", &lpPathName);
      v11 = g_DebugLog;
    }
    if ( v11 && LODWORD(v11[1].LockSemaphore) && SLODWORD(v11[1].OwningThread) >= 4 )
    {
      v49[0] = L"ConfigContext::InitLogger";
      v49[1] = (void *)0x400000FCBLL;
      v50 = L"CCTX";
      dbgobj::DbgPrint<unsigned short,unsigned int>(v49, L"Log severity : %d", &v36);
    }
  }
  if ( Config::PathParam::DoesDirectoryExist(lpPathName) )
  {
    DirectoryW = Config::PathParam::CreateDirectoryW(lpPathName);
    if ( DirectoryW )
    {
      CurrentThreadId = GetCurrentThreadId();
      v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v14,
                                 DirectoryW,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                                 "ConfigContext::InitLogger",
                                 4050,
                                 CurrentThreadId,
                                 0);
      v34 = v3;
    }
  }
  VolumeId::VolumeId((VolumeId *)v55);
  v45 = 0;
  v45 = (WorkPath *)operator new(0x78u);
  v15 = WorkPath::WorkPath(v45);
  v45 = v15;
  if ( v3 )
    goto LABEL_29;
  WorkPathTable::Delete((char *)this + 400);
  *(_OWORD *)v49 = 0;
  v16 = (struct FrsStatus *)WorkPath::Initialize(v15, *v10 + 18LL, v49, 3, 0, 1, v55, 0);
  v3 = v16;
  v34 = v16;
  if ( v16 )
  {
    if ( *((_DWORD *)v16 + 1) != 4390 )
      goto LABEL_29;
    CLEAR_ERROR(&v34);
    v17 = GetCurrentThreadId();
    v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v18,
                               50,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                               "ConfigContext::InitLogger",
                               4082,
                               v17,
                               0);
    v34 = v3;
    if ( v3 )
      goto LABEL_29;
  }
  Block = 0;
  v19 = WorkPathTable::Update((ConfigContext *)((char *)this + 400), v15);
  Block = v19;
  if ( v19 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v41 = L"ConfigContext::InitLogger";
      v42 = 4093;
      v43 = 3;
      v44 = L"CCTX";
      v49[0] = (void *)(*((_QWORD *)v15 + 5) + 18LL);
      v34 = (struct FrsStatus *)(*((_QWORD *)v19 + 5) + 18LL);
      dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned short *>(
        &v41,
        L"(Ignored) New log path is in overlaps with %?, newLogPath:%?",
        &v34,
        v49);
    }
    v20 = GetCurrentThreadId();
    v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v21,
                               148,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                               "ConfigContext::InitLogger",
                               4096,
                               v20,
                               0);
    v34 = v3;
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&Block);
  if ( v3 || (v3 = FrsLogger::Configure(v22, (const struct _LOGGER_CONFIG *)&lpPathName), (v34 = v3) != 0) )
  {
LABEL_29:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v41 = L"ConfigContext::InitLogger";
      v42 = 4107;
      v43 = 3;
      v44 = L"CCTX";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        &v41,
        L"(Ignored) Failed to initialize the logger, trying defaults. Error:%?",
        v3);
    }
    FrsStatusString::FrsStatusString((FrsStatusString *)v49, v3);
    v25 = *((_DWORD *)v3 + 1);
    CLEAR_ERROR(&v34);
    Config::MachineConfig::MachineConfig((Config::MachineConfig *)v47);
    v39 = Config::BoolParam::Get(v4);
    v36 = Config::BoolParam::Get(v6);
    v37 = Config::BoolParam::Get(v8);
    lpPathName = (LPCWSTR)(*(_QWORD *)(v48 + 504) + 18LL);
    v38 = Config::BoolParam::Get(v46);
    v27 = g_DebugLog;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v41 = L"ConfigContext::InitLogger";
        v42 = 4124;
        v43 = 4;
        v44 = L"CCTX";
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v41, L"Log file path: %ws", &lpPathName);
        v27 = g_DebugLog;
      }
      if ( v27 && LODWORD(v27[1].LockSemaphore) && SLODWORD(v27[1].OwningThread) >= 4 )
      {
        v51 = L"ConfigContext::InitLogger";
        v52 = 4125;
        v53 = 4;
        v54 = L"CCTX";
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v51, L"Log severity : %d", &v36);
      }
    }
    v28 = (unsigned int *)FrsLogger::Configure(v26, (const struct _LOGGER_CONFIG *)&lpPathName);
    v34 = (struct FrsStatus *)v28;
    if ( v28 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
      {
        v51 = L"ConfigContext::InitLogger";
        v52 = 4130;
        v53 = 3;
        v54 = L"CCTX";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(
          &v51,
          L"(Ignored) Failed to initialize the logger with defaults. Error:%?",
          v28);
      }
      FrsStatusString::FrsStatusString((FrsStatusString *)&Block, (const struct FrsStatus *)v28);
      v29 = L"<null>";
      if ( lpPathName )
        v29 = lpPathName;
      v30 = Dword::Dword((Dword *)&v51, v28[1], 10);
      FrsEvent::Log(3221226784LL, v30, Block, v29);
      CLEAR_ERROR(&v34);
      operator delete[](Block);
    }
    else
    {
      DisplayPath = FilePath::GetDisplayPath(v48 + 504);
      v32 = FilePath::GetDisplayPath(v10);
      v33 = Dword::Dword((Dword *)&v51, v25, 10);
      FrsEvent::Log(1073743134, v33, v49[0], v32, DisplayPath, 0);
    }
    Config::MachineConfig::~MachineConfig((Config::MachineConfig *)v47);
    operator delete[](v49[0]);
  }
  else
  {
    if ( FrsEvent::eventLog )
      EventLog::Reset(v23, 0xC0000520);
    v24 = FilePath::GetDisplayPath(v10);
    FrsEvent::Log(1073743138, v24);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v45);
  VolumeId::~VolumeId((VolumeId *)v55);
}

```

## disassembly

```asm
0x140042690  mov     [rsp-8+arg_10], rbx
0x140042695  push    rbp
0x140042696  push    rsi
0x140042697  push    rdi
0x140042698  push    r12
0x14004269a  push    r13
0x14004269c  push    r14
0x14004269e  push    r15
0x1400426a0  lea     rbp, [rsp-0D0h]
0x1400426a8  sub     rsp, 1D0h
0x1400426af  mov     rax, cs:__security_cookie
0x1400426b6  xor     rax, rsp
0x1400426b9  mov     [rbp+100h+var_40], rax
0x1400426c0  mov     rsi, rcx
0x1400426c3  xor     ebx, ebx
0x1400426c5  mov     [rsp+200h+var_1B0], rbx
0x1400426ca  lea     r15, [rdx+1A8h]
0x1400426d1  mov     rcx, r15; this
0x1400426d4  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1400426d9  mov     [rsp+200h+var_194], eax
0x1400426dd  lea     r12, [rdx+228h]
0x1400426e4  mov     rcx, r12; this
0x1400426e7  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1400426ec  mov     [rsp+200h+var_1A0], eax
0x1400426f0  lea     r13, [rdx+250h]
0x1400426f7  mov     rcx, r13; this
0x1400426fa  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1400426ff  mov     [rsp+200h+var_19C], eax
0x140042703  lea     r14, [rdx+1F8h]
0x14004270a  mov     rax, [r14]
0x14004270d  add     rax, 12h
0x140042711  mov     [rsp+200h+lpPathName], rax
0x140042716  lea     rax, [rdx+200h]
0x14004271d  mov     [rbp+100h+var_168], rax
0x140042721  mov     rcx, rax; this
0x140042724  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140042729  mov     [rsp+200h+var_198], eax
0x14004272d  lea     rcx, aConfigcontextI; "ConfigContext::InitLogger"
0x140042734  lea     rdx, aCctx; "CCTX"
0x14004273b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042742  test    rax, rax
0x140042745  jz      loc_1400427D1
0x14004274b  cmp     [rax+40h], ebx
0x14004274e  jz      short loc_140042796
0x140042750  cmp     dword ptr [rax+38h], 4
0x140042754  jl      short loc_140042796
0x140042756  mov     [rbp+100h+var_C0], rcx
0x14004275a  mov     dword ptr [rbp+100h+var_C0+8], 0FCAh
0x140042761  mov     dword ptr [rbp+100h+var_C0+0Ch], 4
0x140042768  mov     [rbp+100h+var_B0], rdx
0x14004276c  lea     r8, [rsp+200h+lpPathName]
0x140042771  lea     rdx, aLogFilePathWs; "Log file path: %ws"
0x140042778  lea     rcx, [rbp+100h+var_C0]
0x14004277c  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140042781  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042788  lea     rcx, aConfigcontextI; "ConfigContext::InitLogger"
0x14004278f  lea     rdx, aCctx; "CCTX"
0x140042796  test    rax, rax
0x140042799  jz      short loc_1400427D1
0x14004279b  cmp     [rax+40h], ebx
0x14004279e  jz      short loc_1400427D1
0x1400427a0  cmp     dword ptr [rax+38h], 4
0x1400427a4  jl      short loc_1400427D1
0x1400427a6  mov     [rbp+100h+var_C0], rcx
0x1400427aa  mov     dword ptr [rbp+100h+var_C0+8], 0FCBh
0x1400427b1  mov     dword ptr [rbp+100h+var_C0+0Ch], 4
0x1400427b8  mov     [rbp+100h+var_B0], rdx
0x1400427bc  lea     r8, [rsp+200h+var_1A0]
0x1400427c1  lea     rdx, aLogSeverityD; "Log severity : %d"
0x1400427c8  lea     rcx, [rbp+100h+var_C0]
0x1400427cc  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1400427d1  mov     rcx, [rsp+200h+lpPathName]; unsigned __int16 *
0x1400427d6  call    ?DoesDirectoryExist@PathParam@Config@@SAKPEBG@Z; Config::PathParam::DoesDirectoryExist(ushort const *)
0x1400427db  test    eax, eax
0x1400427dd  jz      short loc_14004283C
0x1400427df  mov     rcx, [rsp+200h+lpPathName]; lpPathName
0x1400427e4  call    ?CreateDirectoryW@PathParam@Config@@SAKPEBG@Z; Config::PathParam::CreateDirectoryW(ushort const *)
0x1400427e9  mov     edi, eax
0x1400427eb  test    eax, eax
0x1400427ed  jz      short loc_14004283C
0x1400427ef  call    cs:__imp_GetCurrentThreadId
0x1400427f6  nop     dword ptr [rax+rax+00h]
0x1400427fb  and     [rsp+200h+var_1C0], rbx
0x140042800  mov     dword ptr [rsp+200h+var_1C8], eax
0x140042804  mov     dword ptr [rsp+200h+var_1D0], 0FD2h
0x14004280c  lea     rax, aConfigcontextI_0; "ConfigContext::InitLogger"
0x140042813  mov     [rsp+200h+var_1D8], rax
0x140042818  lea     rax, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x14004281f  mov     [rsp+200h+var_1E0], rax
0x140042824  mov     r9d, 1
0x14004282a  xor     r8d, r8d
0x14004282d  mov     edx, edi
0x14004282f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140042834  mov     rbx, rax
0x140042837  mov     [rsp+200h+var_1B0], rax
0x14004283c  lea     rcx, [rbp+100h+var_78]; this
0x140042843  call    ??0VolumeId@@QEAA@XZ; VolumeId::VolumeId(void)
0x140042848  nop
0x140042849  and     [rbp+100h+var_170], 0
0x14004284e  mov     ecx, 78h ; 'x'; Size
0x140042853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140042858  mov     [rbp+100h+var_170], rax
0x14004285c  mov     rcx, rax; this
0x14004285f  call    ??0WorkPath@@QEAA@XZ; WorkPath::WorkPath(void)
0x140042864  mov     rdi, rax
0x140042867  mov     [rbp+100h+var_170], rax
0x14004286b  test    rbx, rbx
0x14004286e  jnz     loc_140042A84
0x140042874  lea     rcx, [rsi+190h]
0x14004287b  call    ?Delete@WorkPathTable@@QEAAKW4PATH_TYPE@WorkPath@@@Z; WorkPathTable::Delete(WorkPath::PATH_TYPE)
0x140042880  xorps   xmm0, xmm0
0x140042883  movups  xmmword ptr [rbp+100h+var_C0], xmm0
0x140042887  mov     rdx, [r14]
0x14004288a  add     rdx, 12h
0x14004288e  and     [rsp+200h+var_1C8], rbx
0x140042893  lea     rax, [rbp+100h+var_78]
0x14004289a  mov     [rsp+200h+var_1D0], rax
0x14004289f  mov     dword ptr [rsp+200h+var_1D8], 1
0x1400428a7  and     dword ptr [rsp+200h+var_1E0], ebx
0x1400428ab  lea     r9d, [rbx+3]
0x1400428af  lea     r8, [rbp+100h+var_C0]
0x1400428b3  mov     rcx, rdi
0x1400428b6  call    ?Initialize@WorkPath@@QEAAPEAVFrsStatus@@PEBGAEBU_GUID@@W4PATH_TYPE@1@W4PATH_OWNER@1@HAEAVVolumeId@@0@Z; WorkPath::Initialize(ushort const *,_GUID const &,WorkPath::PATH_TYPE,WorkPath::PATH_OWNER,int,VolumeId &,ushort const *)
0x1400428bb  mov     rbx, rax
0x1400428be  mov     [rsp+200h+var_1B0], rax
0x1400428c3  test    rax, rax
0x1400428c6  jz      short loc_140042938
0x1400428c8  cmp     dword ptr [rax+4], 1126h
0x1400428cf  jnz     loc_140042A84
0x1400428d5  lea     rcx, [rsp+200h+var_1B0]; struct FrsStatus **
0x1400428da  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400428df  call    cs:__imp_GetCurrentThreadId
0x1400428e6  nop     dword ptr [rax+rax+00h]
0x1400428eb  and     [rsp+200h+var_1C0], 0
0x1400428f1  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400428f5  mov     dword ptr [rsp+200h+var_1D0], 0FF2h
0x1400428fd  lea     rax, aConfigcontextI_0; "ConfigContext::InitLogger"
0x140042904  mov     [rsp+200h+var_1D8], rax
0x140042909  lea     rax, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x140042910  mov     [rsp+200h+var_1E0], rax
0x140042915  mov     r9d, 1
0x14004291b  xor     r8d, r8d
0x14004291e  lea     edx, [r9+31h]
0x140042922  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140042927  mov     rbx, rax
0x14004292a  mov     [rsp+200h+var_1B0], rax
0x14004292f  test    rax, rax
0x140042932  jnz     loc_140042A84
0x140042938  and     [rsp+200h+Block], 0
0x14004293e  mov     rdx, rdi; struct WorkPath *
0x140042941  lea     rcx, [rsi+190h]; this
0x140042948  call    ?Update@WorkPathTable@@QEAAPEAVWorkPath@@PEAV2@@Z; WorkPathTable::Update(WorkPath *)
0x14004294d  mov     rdx, rax
0x140042950  mov     [rsp+200h+Block], rax
0x140042955  test    rax, rax
0x140042958  jz      loc_140042A2A
0x14004295e  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042965  test    rcx, rcx
0x140042968  jz      short loc_1400429D0
0x14004296a  cmp     dword ptr [rcx+40h], 0
0x14004296e  jz      short loc_1400429D0
0x140042970  lea     rsi, aCctx; "CCTX"
0x140042977  cmp     dword ptr [rcx+38h], 3
0x14004297b  jl      short loc_1400429D7
0x14004297d  lea     rax, aConfigcontextI; "ConfigContext::InitLogger"
0x140042984  mov     [rsp+200h+var_188], rax
0x140042989  mov     [rbp+100h+var_180], 0FFDh
0x140042990  mov     [rbp+100h+var_17C], 3
0x140042997  mov     [rbp+100h+var_178], rsi
0x14004299b  mov     rax, [rdi+28h]
0x14004299f  add     rax, 12h
0x1400429a3  mov     [rbp+100h+var_C0], rax
0x1400429a7  mov     rax, [rdx+28h]
0x1400429ab  add     rax, 12h
0x1400429af  mov     [rsp+200h+var_1B0], rax
0x1400429b4  lea     r9, [rbp+100h+var_C0]
0x1400429b8  lea     r8, [rsp+200h+var_1B0]
0x1400429bd  lea     rdx, aIgnoredNewLogP; "(Ignored) New log path is in overlaps w"...
0x1400429c4  lea     rcx, [rsp+200h+var_188]
0x1400429c9  call    ??$DbgPrint@GPEBGPEAG@dbgobj@@QEAA_KPEBGAEBQEBGAEBQEAG@Z; dbgobj::DbgPrint<ushort,ushort const *,ushort *>(ushort const *,ushort const * const &,ushort * const &)
0x1400429ce  jmp     short loc_1400429D7
0x1400429d0  lea     rsi, aCctx; "CCTX"
0x1400429d7  call    cs:__imp_GetCurrentThreadId
0x1400429de  nop     dword ptr [rax+rax+00h]
0x1400429e3  and     [rsp+200h+var_1C0], 0
0x1400429e9  mov     dword ptr [rsp+200h+var_1C8], eax
0x1400429ed  mov     dword ptr [rsp+200h+var_1D0], 1000h
0x1400429f5  lea     rax, aConfigcontextI_0; "ConfigContext::InitLogger"
0x1400429fc  mov     [rsp+200h+var_1D8], rax
0x140042a01  lea     rax, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x140042a08  mov     [rsp+200h+var_1E0], rax
0x140042a0d  mov     r9d, 1
0x140042a13  xor     r8d, r8d
0x140042a16  mov     edx, 94h
0x140042a1b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140042a20  mov     rbx, rax
0x140042a23  mov     [rsp+200h+var_1B0], rax
0x140042a28  jmp     short loc_140042A31
0x140042a2a  lea     rsi, aCctx; "CCTX"
0x140042a31  lea     rcx, [rsp+200h+Block]
0x140042a36  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x140042a3b  test    rbx, rbx
0x140042a3e  jnz     short loc_140042A8B
0x140042a40  lea     rdx, [rsp+200h+lpPathName]; struct _LOGGER_CONFIG *
0x140042a45  call    ?Configure@FrsLogger@@QEAAPEAVFrsStatus@@AEBU_LOGGER_CONFIG@@@Z; FrsLogger::Configure(_LOGGER_CONFIG const &)
0x140042a4a  mov     rbx, rax
0x140042a4d  mov     [rsp+200h+var_1B0], rax
0x140042a52  test    rax, rax
0x140042a55  jnz     short loc_140042A8B
0x140042a57  cmp     cs:?eventLog@FrsEvent@@0PEAVEventLog@@EA, rax; EventLog * FrsEvent::eventLog
0x140042a5e  jz      short loc_140042A6A
0x140042a60  mov     edx, 0C0000520h; unsigned int
0x140042a65  call    ?Reset@EventLog@@QEAAXK@Z; EventLog::Reset(ulong)
0x140042a6a  mov     rcx, r14
0x140042a6d  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x140042a72  mov     rdx, rax
0x140042a75  mov     ecx, 40000522h
0x140042a7a  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum1@@PEBG@Z; FrsEvent::Log(FrsEventsEnum1,ushort const *)
0x140042a7f  jmp     loc_140042CFF
0x140042a84  lea     rsi, aCctx; "CCTX"
0x140042a8b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042a92  lea     rdi, aConfigcontextI; "ConfigContext::InitLogger"
0x140042a99  test    rax, rax
0x140042a9c  jz      short loc_140042AD5
0x140042a9e  cmp     dword ptr [rax+40h], 0
0x140042aa2  jz      short loc_140042AD5
0x140042aa4  cmp     dword ptr [rax+38h], 3
0x140042aa8  jl      short loc_140042AD5
0x140042aaa  mov     [rsp+200h+var_188], rdi
0x140042aaf  mov     [rbp+100h+var_180], 100Bh
0x140042ab6  mov     [rbp+100h+var_17C], 3
0x140042abd  mov     [rbp+100h+var_178], rsi
0x140042ac1  mov     r8, rbx
0x140042ac4  lea     rdx, aIgnoredFailedT_52; "(Ignored) Failed to initialize the logg"...
0x140042acb  lea     rcx, [rsp+200h+var_188]
0x140042ad0  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x140042ad5  mov     rdx, rbx; struct FrsStatus *
0x140042ad8  lea     rcx, [rbp+100h+var_C0]; this
0x140042adc  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x140042ae1  nop
0x140042ae2  mov     esi, [rbx+4]
0x140042ae5  lea     rcx, [rsp+200h+var_1B0]; struct FrsStatus **
0x140042aea  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140042aef  lea     rcx, [rbp+100h+var_160]; this
0x140042af3  call    ??0MachineConfig@Config@@QEAA@XZ; Config::MachineConfig::MachineConfig(void)
0x140042af8  nop
0x140042af9  mov     rcx, r15; this
0x140042afc  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140042b01  mov     [rsp+200h+var_194], eax
0x140042b05  mov     rcx, r12; this
0x140042b08  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140042b0d  mov     [rsp+200h+var_1A0], eax
0x140042b11  mov     rcx, r13; this
0x140042b14  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140042b19  mov     [rsp+200h+var_19C], eax
0x140042b1d  mov     rax, [rbp+100h+var_D0]
0x140042b21  mov     rdx, [rax+1F8h]
0x140042b28  add     rdx, 12h
0x140042b2c  mov     [rsp+200h+lpPathName], rdx
0x140042b31  mov     rcx, [rbp+100h+var_168]; this
0x140042b35  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x140042b3a  mov     [rsp+200h+var_198], eax
0x140042b3e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042b45  xor     r15d, r15d
0x140042b48  test    rax, rax
0x140042b4b  jz      loc_140042BD4
0x140042b51  lea     rbx, aCctx; "CCTX"
0x140042b58  cmp     [rax+40h], r15d
0x140042b5c  jz      short loc_140042B98
0x140042b5e  cmp     dword ptr [rax+38h], 4
0x140042b62  jl      short loc_140042B98
0x140042b64  mov     [rsp+200h+var_188], rdi
0x140042b69  mov     [rbp+100h+var_180], 101Ch
0x140042b70  mov     [rbp+100h+var_17C], 4
0x140042b77  mov     [rbp+100h+var_178], rbx
0x140042b7b  lea     r8, [rsp+200h+lpPathName]
0x140042b80  lea     rdx, aLogFilePathWs; "Log file path: %ws"
0x140042b87  lea     rcx, [rsp+200h+var_188]
0x140042b8c  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140042b91  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140042b98  test    rax, rax
0x140042b9b  jz      short loc_140042BD4
0x140042b9d  cmp     [rax+40h], r15d
0x140042ba1  jz      short loc_140042BD4
0x140042ba3  cmp     dword ptr [rax+38h], 4
0x140042ba7  jl      short loc_140042BD4
0x140042ba9  mov     [rbp+100h+var_A8], rdi
0x140042bad  mov     [rbp+100h+var_A0], 101Dh
0x140042bb4  mov     [rbp+100h+var_9C], 4
0x140042bbb  mov     [rbp+100h+var_98], rbx
0x140042bbf  lea     r8, [rsp+200h+var_1A0]
0x140042bc4  lea     rdx, aLogSeverityD; "Log severity : %d"
0x140042bcb  lea     rcx, [rbp+100h+var_A8]
0x140042bcf  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140042bd4  lea     rdx, [rsp+200h+lpPathName]; struct _LOGGER_CONFIG *
0x140042bd9  call    ?Configure@FrsLogger@@QEAAPEAVFrsStatus@@AEBU_LOGGER_CONFIG@@@Z; FrsLogger::Configure(_LOGGER_CONFIG const &)
0x140042bde  mov     rdi, rax
0x140042be1  mov     [rsp+200h+var_1B0], rax
0x140042be6  test    rax, rax
0x140042be9  jz      loc_140042C9D
  ... truncated ...
```
