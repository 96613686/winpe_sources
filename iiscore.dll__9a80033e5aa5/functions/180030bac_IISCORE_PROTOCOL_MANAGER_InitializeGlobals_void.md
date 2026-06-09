# IISCORE_PROTOCOL_MANAGER::InitializeGlobals(void)

- ea: `0x180030bac`
- end: `0x180030e3c`
- name: `?InitializeGlobals@IISCORE_PROTOCOL_MANAGER@@QEAAJXZ`
- size: `656`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180030f90`
- `0x1800313a0`

## callees

- `0x180013690`
- `0x180019558`
- `0x18001a414`
- `0x18001e7f0`
- `0x180030848`
- `0x180030bac`
- `0x18003106c`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030cf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d36`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180030cef`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180030cef`
- `SspiCli!GetUserNameExW` at `0x180030d29`
- `SspiCli!GetUserNameExW` at `0x180030d70`
- `SspiCli!GetUserNameExW` at `0x180030d29`
- `SspiCli!GetUserNameExW` at `0x180030d70`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180030d0b`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x180030d0b`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180030c16`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180030c16`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180030bf0`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180030bf0`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180030c3d`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180030c3d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180030da7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180030da7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d16`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d5d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d82`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d16`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d5d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030d82`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180030d4e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180030d4e`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180030c57`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180030c57`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180030ce1`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180030ce1`

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
0x180030bac  mov     [rsp-8+arg_8], rbx
0x180030bb1  mov     [rsp-8+arg_10], rdi
0x180030bb6  push    rbp
0x180030bb7  lea     rbp, [rsp-190h]
0x180030bbf  sub     rsp, 290h
0x180030bc6  mov     rax, cs:__security_cookie
0x180030bcd  xor     rax, rsp
0x180030bd0  mov     [rbp+190h+var_10], rax
0x180030bd7  mov     rdi, rcx
0x180030bda  mov     ecx, 40h ; '@'; Size
0x180030bdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030be4  test    rax, rax
0x180030be7  jz      loc_180030DDB
0x180030bed  mov     rcx, rax
0x180030bf0  call    cs:__imp_??0CEtwTracer@@QEAA@XZ; CEtwTracer::CEtwTracer(void)
0x180030bf6  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, rax; CEtwTracer * g_pEtwGlobalTracer
0x180030bfd  test    rax, rax
0x180030c00  jz      loc_180030DE6
0x180030c06  xor     r9d, r9d
0x180030c09  lea     rdx, GUID_IIS_WWW_GLOBAL_TRACE_PROVIDER
0x180030c10  xor     r8d, r8d
0x180030c13  mov     rcx, rax
0x180030c16  call    cs:__imp_?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z; CEtwTracer::Register(_GUID const *,ushort *,ushort *)
0x180030c1c  mov     ebx, eax
0x180030c1e  test    eax, eax
0x180030c20  jz      short loc_180030C5D
0x180030c22  cmp     dword ptr [rdi+60h], 0
0x180030c26  lea     rax, aW3svcWp; "W3SVC-WP"
0x180030c2d  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180030c34  cmovz   rdx, rax
0x180030c38  lea     rcx, [rsp+290h+nSize]
0x180030c3d  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180030c43  xor     r8d, r8d
0x180030c46  mov     dword ptr [rsp+290h+var_270], ebx
0x180030c4a  xor     r9d, r9d
0x180030c4d  lea     rcx, [rsp+290h+nSize]
0x180030c52  mov     edx, 800008E3h
0x180030c57  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180030c5d  mov     ecx, 6A0h; Size
0x180030c62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030c67  test    rax, rax
0x180030c6a  jz      loc_180030DCE
0x180030c70  mov     edx, [rdi+60h]; int
0x180030c73  mov     rcx, rax; this
0x180030c76  call    ??0W3_SERVER@@QEAA@H@Z; W3_SERVER::W3_SERVER(int)
0x180030c7b  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, rax; W3_SERVER * g_pW3Server
0x180030c82  test    rax, rax
0x180030c85  jz      loc_180030DE6
0x180030c8b  mov     rax, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180030c92  cmp     dword ptr [rax+8], 0
0x180030c96  jz      loc_180030DAD
0x180030c9c  test    byte ptr [rax+28h], 1
0x180030ca0  jz      loc_180030DAD
0x180030ca6  cmp     dword ptr [rax+2Ch], 4
0x180030caa  jb      loc_180030DAD
0x180030cb0  mov     ebx, 200h
0x180030cb5  mov     [rsp+290h+ProcessAffinityMask], 0
0x180030cbe  mov     r8d, ebx; Size
0x180030cc1  mov     [rsp+290h+SystemAffinityMask], 0
0x180030cca  xor     edx, edx; Val
0x180030ccc  lea     rcx, [rbp+190h+var_210]; void *
0x180030cd0  call    memset_0
0x180030cd5  mov     r8d, ebx
0x180030cd8  lea     rdx, [rbp+190h+var_210]
0x180030cdc  lea     rcx, [rsp+290h+var_248]
0x180030ce1  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180030ce7  mov     [rsp+290h+nSize], 100h
0x180030cef  call    cs:__imp_GetCommandLineW
0x180030cf5  mov     rbx, rax
0x180030cf8  call    cs:__imp_GetCurrentProcess
0x180030cfe  mov     rcx, rax; hProcess
0x180030d01  lea     r8, [rsp+290h+SystemAffinityMask]; lpSystemAffinityMask
0x180030d06  lea     rdx, [rsp+290h+ProcessAffinityMask]; lpProcessAffinityMask
0x180030d0b  call    cs:__imp_GetProcessAffinityMask
0x180030d11  lea     rcx, [rsp+290h+var_248]
0x180030d16  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180030d1c  lea     r8, [rsp+290h+nSize]; nSize
0x180030d21  mov     ecx, 10002h; NameFormat
0x180030d26  mov     rdx, rax; lpNameBuffer
0x180030d29  call    cs:__imp_GetUserNameExW
0x180030d2f  movzx   ecx, al
0x180030d32  test    al, al
0x180030d34  jnz     short loc_180030D79
0x180030d36  call    cs:__imp_GetLastError
0x180030d3c  cmp     eax, 0EAh
0x180030d41  jnz     short loc_180030DA2
0x180030d43  mov     edx, [rsp+290h+nSize]
0x180030d47  lea     rcx, [rsp+290h+var_248]
0x180030d4c  add     edx, edx
0x180030d4e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180030d54  test    al, al
0x180030d56  jz      short loc_180030DA2
0x180030d58  lea     rcx, [rsp+290h+var_248]
0x180030d5d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180030d63  lea     r8, [rsp+290h+nSize]; nSize
0x180030d68  mov     ecx, 10002h; NameFormat
0x180030d6d  mov     rdx, rax; lpNameBuffer
0x180030d70  call    cs:__imp_GetUserNameExW
0x180030d76  movzx   ecx, al
0x180030d79  test    ecx, ecx
0x180030d7b  jz      short loc_180030DA2
0x180030d7d  lea     rcx, [rsp+290h+var_248]
0x180030d82  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180030d88  mov     ecx, dword ptr [rsp+290h+ProcessAffinityMask]
0x180030d8c  mov     rdx, rbx; unsigned __int16 *
0x180030d8f  mov     dword ptr [rsp+290h+var_270], ecx; char
0x180030d93  mov     r9, rax; unsigned __int16 *
0x180030d96  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; struct CEtwTracer *
0x180030d9d  call    ?RaiseEvent@GLOBAL_PROCESS_START_INFO@IISStartupEvents@@SAJPEAVCEtwTracer@@PEBGH1K@Z; IISStartupEvents::GLOBAL_PROCESS_START_INFO::RaiseEvent(CEtwTracer *,ushort const *,int,ushort const *,ulong)
0x180030da2  lea     rcx, [rsp+290h+var_248]
0x180030da7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180030dad  mov     rdx, [rdi+40h]; struct IWorkerProcessFramework *
0x180030db1  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180030db8  call    ?Initialize@W3_SERVER@@QEAAJPEAVIWorkerProcessFramework@@@Z; W3_SERVER::Initialize(IWorkerProcessFramework *)
0x180030dbd  mov     ebx, eax
0x180030dbf  test    eax, eax
0x180030dc1  js      short loc_180030DEB
0x180030dc3  mov     dword ptr [rdi+64h], 1
0x180030dca  xor     ebx, ebx
0x180030dcc  jmp     short loc_180030E16
0x180030dce  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180030dd9  jmp     short loc_180030DE6
0x180030ddb  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, 0; CEtwTracer * g_pEtwGlobalTracer
0x180030de6  mov     ebx, 80070008h
0x180030deb  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180030df3  jz      short loc_180030E16
0x180030df5  call    ?Terminate@W3_SERVER@@QEAAXXZ; W3_SERVER::Terminate(void)
0x180030dfa  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x180030e01  test    rcx, rcx
0x180030e04  jz      short loc_180030E0B
0x180030e06  call    ??_GW3_SERVER@@QEAAPEAXI@Z; W3_SERVER::`scalar deleting destructor'(uint)
0x180030e0b  mov     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180030e16  mov     eax, ebx
0x180030e18  mov     rcx, [rbp+190h+var_10]
0x180030e1f  xor     rcx, rsp; StackCookie
0x180030e22  call    __security_check_cookie
0x180030e27  lea     r11, [rsp+290h+var_s0]
0x180030e2f  mov     rbx, [r11+18h]
0x180030e33  mov     rdi, [r11+20h]
0x180030e37  mov     rsp, r11
0x180030e3a  pop     rbp
0x180030e3b  retn
```
