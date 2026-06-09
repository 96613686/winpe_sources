# IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)

- ea: `0x1800338ac`
- end: `0x180033b9d`
- name: `?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ`
- size: `753`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180033d10`
- `0x180034190`

## callees

- `0x1800147d0`
- `0x18001ab30`
- `0x18001ba38`
- `0x1800202bc`
- `0x180033514`
- `0x1800338ac`
- `0x180033e24`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033a1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a72`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180033a0d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180033a0d`
- `SspiCli!GetUserNameExW` at `0x180033a5f`
- `SspiCli!GetUserNameExW` at `0x180033abe`
- `SspiCli!GetUserNameExW` at `0x180033a5f`
- `SspiCli!GetUserNameExW` at `0x180033abe`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180033a35`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180033a35`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x18003391c`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x18003391c`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x1800338f0`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x1800338f0`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180033949`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180033949`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180033b01`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180033b01`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033a46`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033aa5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033ad6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033a46`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033aa5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180033ad6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180033a90`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180033a90`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180033969`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180033969`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800339f9`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800339f9`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::InitializeGlobals(IISCORE_PROTOCOL_MANAGER *this)
{
  CEtwTracer *v2; // rax
  W3_SERVER *v3; // rcx
  struct CEtwTracer *v4; // rax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rdx
  W3_SERVER *v7; // rax
  const unsigned __int16 *CommandLineW; // rbx
  HANDLE CurrentProcess; // rax
  WCHAR *Ptr; // rax
  BOOLEAN UserName; // al
  int v12; // ecx
  WCHAR *v13; // rax
  const unsigned __int16 *v14; // rax
  int v15; // r8d
  int v16; // ebx
  unsigned int v17; // edx
  ULONG nSize; // [rsp+30h] [rbp-D0h] BYREF
  ULONG_PTR ProcessAffinityMask; // [rsp+38h] [rbp-C8h] BYREF
  ULONG_PTR SystemAffinityMask; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[56]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v23[512]; // [rsp+80h] [rbp-80h] BYREF

  v2 = (CEtwTracer *)operator new(0x40u);
  if ( !v2 )
  {
    g_pEtwGlobalTracer = 0;
    goto LABEL_23;
  }
  v4 = CEtwTracer::CEtwTracer(v2);
  g_pEtwGlobalTracer = v4;
  if ( !v4 )
    goto LABEL_23;
  v5 = CEtwTracer::Register(v4, &GUID_IIS_WWW_GLOBAL_TRACE_PROVIDER, 0, 0);
  if ( v5 )
  {
    v6 = L"HostableWebCore";
    if ( !*((_DWORD *)this + 24) )
      v6 = L"W3SVC-WP";
    EVENT_LOG::EVENT_LOG((EVENT_LOG *)&nSize, v6);
    EVENT_LOG::LogEvent((EVENT_LOG *)&nSize, 0x800008E3, 0, 0, v5);
  }
  v7 = (W3_SERVER *)operator new(0x6A0u);
  if ( !v7 )
  {
    g_pW3Server = 0;
    goto LABEL_23;
  }
  g_pW3Server = W3_SERVER::W3_SERVER(v7, *((_DWORD *)this + 24));
  if ( !g_pW3Server )
  {
LABEL_23:
    v16 = -2147024888;
    goto LABEL_24;
  }
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
  {
    ProcessAffinityMask = 0;
    SystemAffinityMask = 0;
    memset_0(v23, 0, sizeof(v23));
    BUFFER::BUFFER((BUFFER *)v22, v23, 0x200u);
    nSize = 256;
    CommandLineW = GetCommandLineW();
    CurrentProcess = GetCurrentProcess();
    GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask);
    Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v22);
    UserName = GetUserNameExW((EXTENDED_NAME_FORMAT)65538, Ptr, &nSize);
    v12 = UserName;
    if ( !UserName )
    {
      if ( GetLastError() != 234 || !BUFFER::Resize((BUFFER *)v22, 2 * nSize) )
      {
LABEL_18:
        BUFFER::~BUFFER((BUFFER *)v22);
        goto LABEL_19;
      }
      v13 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v22);
      v12 = GetUserNameExW((EXTENDED_NAME_FORMAT)65538, v13, &nSize);
    }
    if ( v12 )
    {
      v14 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v22);
      IISStartupEvents::GLOBAL_PROCESS_START_INFO::RaiseEvent(
        g_pEtwGlobalTracer,
        CommandLineW,
        v15,
        v14,
        ProcessAffinityMask);
    }
    goto LABEL_18;
  }
LABEL_19:
  v16 = W3_SERVER::Initialize(g_pW3Server, *((struct IWorkerProcessFramework **)this + 8));
  if ( v16 >= 0 )
  {
    *((_DWORD *)this + 25) = 1;
    return 0;
  }
LABEL_24:
  if ( g_pW3Server )
  {
    W3_SERVER::Terminate(v3);
    if ( g_pW3Server )
      W3_SERVER::`scalar deleting destructor'(g_pW3Server, v17);
    g_pW3Server = 0;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800338ac  mov     [rsp-8+arg_8], rbx
0x1800338b1  mov     [rsp-8+arg_10], rdi
0x1800338b6  push    rbp
0x1800338b7  lea     rbp, [rsp-190h]
0x1800338bf  sub     rsp, 290h
0x1800338c6  mov     rax, cs:__security_cookie
0x1800338cd  xor     rax, rsp
0x1800338d0  mov     [rbp+190h+var_10], rax
0x1800338d7  mov     rdi, rcx
0x1800338da  mov     ecx, 40h ; '@'; Size
0x1800338df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800338e4  test    rax, rax
0x1800338e7  jz      loc_180033B3B
0x1800338ed  mov     rcx, rax
0x1800338f0  call    cs:__imp_??0CEtwTracer@@QEAA@XZ; CEtwTracer::CEtwTracer(void)
0x1800338f7  nop     dword ptr [rax+rax+00h]
0x1800338fc  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, rax; CEtwTracer * g_pEtwGlobalTracer
0x180033903  test    rax, rax
0x180033906  jz      loc_180033B46
0x18003390c  xor     r9d, r9d
0x18003390f  lea     rdx, GUID_IIS_WWW_GLOBAL_TRACE_PROVIDER
0x180033916  xor     r8d, r8d
0x180033919  mov     rcx, rax
0x18003391c  call    cs:__imp_?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z; CEtwTracer::Register(_GUID const *,ushort *,ushort *)
0x180033923  nop     dword ptr [rax+rax+00h]
0x180033928  mov     ebx, eax
0x18003392a  test    eax, eax
0x18003392c  jz      short loc_180033975
0x18003392e  cmp     dword ptr [rdi+60h], 0
0x180033932  lea     rax, aW3svcWp; "W3SVC-WP"
0x180033939  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180033940  cmovz   rdx, rax
0x180033944  lea     rcx, [rsp+290h+nSize]
0x180033949  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180033950  nop     dword ptr [rax+rax+00h]
0x180033955  xor     r8d, r8d
0x180033958  mov     dword ptr [rsp+290h+var_270], ebx
0x18003395c  xor     r9d, r9d
0x18003395f  lea     rcx, [rsp+290h+nSize]
0x180033964  mov     edx, 800008E3h
0x180033969  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180033970  nop     dword ptr [rax+rax+00h]
0x180033975  mov     ecx, 6A0h; Size
0x18003397a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003397f  test    rax, rax
0x180033982  jz      loc_180033B2E
0x180033988  mov     edx, [rdi+60h]; int
0x18003398b  mov     rcx, rax; this
0x18003398e  call    ??0W3_SERVER@@QEAA@H@Z; W3_SERVER::W3_SERVER(int)
0x180033993  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, rax; W3_SERVER * g_pW3Server
0x18003399a  test    rax, rax
0x18003399d  jz      loc_180033B46
0x1800339a3  mov     rax, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800339aa  cmp     dword ptr [rax+8], 0
0x1800339ae  jz      loc_180033B0D
0x1800339b4  test    byte ptr [rax+28h], 1
0x1800339b8  jz      loc_180033B0D
0x1800339be  cmp     dword ptr [rax+2Ch], 4
0x1800339c2  jb      loc_180033B0D
0x1800339c8  mov     ebx, 200h
0x1800339cd  mov     [rsp+290h+ProcessAffinityMask], 0
0x1800339d6  mov     r8d, ebx; Size
0x1800339d9  mov     [rsp+290h+SystemAffinityMask], 0
0x1800339e2  xor     edx, edx; Val
0x1800339e4  lea     rcx, [rbp+190h+var_210]; void *
0x1800339e8  call    memset_0
0x1800339ed  mov     r8d, ebx
0x1800339f0  lea     rdx, [rbp+190h+var_210]
0x1800339f4  lea     rcx, [rsp+290h+var_248]
0x1800339f9  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180033a00  nop     dword ptr [rax+rax+00h]
0x180033a05  mov     [rsp+290h+nSize], 100h
0x180033a0d  call    cs:__imp_GetCommandLineW
0x180033a14  nop     dword ptr [rax+rax+00h]
0x180033a19  mov     rbx, rax
0x180033a1c  call    cs:__imp_GetCurrentProcess
0x180033a23  nop     dword ptr [rax+rax+00h]
0x180033a28  mov     rcx, rax; hProcess
0x180033a2b  lea     r8, [rsp+290h+SystemAffinityMask]; lpSystemAffinityMask
0x180033a30  lea     rdx, [rsp+290h+ProcessAffinityMask]; lpProcessAffinityMask
0x180033a35  call    cs:__imp_GetProcessAffinityMask
0x180033a3c  nop     dword ptr [rax+rax+00h]
0x180033a41  lea     rcx, [rsp+290h+var_248]
0x180033a46  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180033a4d  nop     dword ptr [rax+rax+00h]
0x180033a52  lea     r8, [rsp+290h+nSize]; nSize
0x180033a57  mov     ecx, 10002h; NameFormat
0x180033a5c  mov     rdx, rax; lpNameBuffer
0x180033a5f  call    cs:__imp_GetUserNameExW
0x180033a66  nop     dword ptr [rax+rax+00h]
0x180033a6b  movzx   ecx, al
0x180033a6e  test    al, al
0x180033a70  jnz     short loc_180033ACD
0x180033a72  call    cs:__imp_GetLastError
0x180033a79  nop     dword ptr [rax+rax+00h]
0x180033a7e  cmp     eax, 0EAh
0x180033a83  jnz     short loc_180033AFC
0x180033a85  mov     edx, [rsp+290h+nSize]
0x180033a89  lea     rcx, [rsp+290h+var_248]
0x180033a8e  add     edx, edx
0x180033a90  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180033a97  nop     dword ptr [rax+rax+00h]
0x180033a9c  test    al, al
0x180033a9e  jz      short loc_180033AFC
0x180033aa0  lea     rcx, [rsp+290h+var_248]
0x180033aa5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180033aac  nop     dword ptr [rax+rax+00h]
0x180033ab1  lea     r8, [rsp+290h+nSize]; nSize
0x180033ab6  mov     ecx, 10002h; NameFormat
0x180033abb  mov     rdx, rax; lpNameBuffer
0x180033abe  call    cs:__imp_GetUserNameExW
0x180033ac5  nop     dword ptr [rax+rax+00h]
0x180033aca  movzx   ecx, al
0x180033acd  test    ecx, ecx
0x180033acf  jz      short loc_180033AFC
0x180033ad1  lea     rcx, [rsp+290h+var_248]
0x180033ad6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180033add  nop     dword ptr [rax+rax+00h]
0x180033ae2  mov     ecx, dword ptr [rsp+290h+ProcessAffinityMask]
0x180033ae6  mov     rdx, rbx; unsigned __int16 *
0x180033ae9  mov     dword ptr [rsp+290h+var_270], ecx; char
0x180033aed  mov     r9, rax; unsigned __int16 *
0x180033af0  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; struct CEtwTracer *
0x180033af7  call    ?RaiseEvent@GLOBAL_PROCESS_START_INFO@IISStartupEvents@@SAJPEAVCEtwTracer@@PEBGH1K@Z; IISStartupEvents::GLOBAL_PROCESS_START_INFO::RaiseEvent(CEtwTracer *,ushort const *,int,ushort const *,ulong)
0x180033afc  lea     rcx, [rsp+290h+var_248]
0x180033b01  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180033b08  nop     dword ptr [rax+rax+00h]
0x180033b0d  mov     rdx, [rdi+40h]; struct IWorkerProcessFramework *
0x180033b11  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180033b18  call    ?Initialize@W3_SERVER@@QEAAJPEAVIWorkerProcessFramework@@@Z; W3_SERVER::Initialize(IWorkerProcessFramework *)
0x180033b1d  mov     ebx, eax
0x180033b1f  test    eax, eax
0x180033b21  js      short loc_180033B4B
0x180033b23  mov     dword ptr [rdi+64h], 1
0x180033b2a  xor     ebx, ebx
0x180033b2c  jmp     short loc_180033B76
0x180033b2e  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180033b39  jmp     short loc_180033B46
0x180033b3b  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, 0; CEtwTracer * g_pEtwGlobalTracer
0x180033b46  mov     ebx, 80070008h
0x180033b4b  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180033b53  jz      short loc_180033B76
0x180033b55  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x180033b5a  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180033b61  test    rcx, rcx
0x180033b64  jz      short loc_180033B6B
0x180033b66  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x180033b6b  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180033b76  mov     eax, ebx
0x180033b78  mov     rcx, [rbp+190h+var_10]
0x180033b7f  xor     rcx, rsp; StackCookie
0x180033b82  call    __security_check_cookie
0x180033b87  lea     r11, [rsp+290h+var_s0]
0x180033b8f  mov     rbx, [r11+18h]
0x180033b93  mov     rdi, [r11+20h]
0x180033b97  mov     rsp, r11
0x180033b9a  pop     rbp
0x180033b9b  retn
```
