# DllMain

- ea: `0x18000fcf0`
- end: `0x18000fe98`
- name: `DllMain`
- size: `424`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001544`

## callees

- `0x18000dd0c`
- `0x18000fcf0`
- `0x18000fedc`
- `0x1800100c0`
- `0x18001019c`
- `0x180010288`
- `0x180014054`
- `0x180014ae8`
- `0x180014bc4`
- `0x180014e4c`
- `0x180015778`

## import_xrefs

- `ATL!__imp_AtlModuleInit` at `0x18000fdd2`
- `ATL!__imp_AtlModuleInit` at `0x18000fdd2`
- `ATL!__imp_AtlModuleTerm` at `0x18000fe5b`
- `ATL!__imp_AtlModuleTerm` at `0x18000fe5b`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000fdf8`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000fdf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HINSTANCE v3; // rsi
  char *v4; // rax
  const wchar_t *v5; // rdx
  HKEY v6; // rcx
  char *v7; // rdi
  int v8; // eax
  HKEY v9; // rcx
  char TriggersServiceName; // al
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  wchar_t v18[16]; // [rsp+0h] [rbp-48h] BYREF

  v3 = hinstDLL;
  if ( !fdwReason )
  {
    WppCleanupUm(hinstDLL, fdwReason, lpvReserved);
    AtlModuleTerm(&_Module);
    if ( g_pMSMQErrorLoggingTrace )
    {
      CMSMQTrace::`scalar deleting destructor'(g_pMSMQErrorLoggingTrace, v16);
      g_pMSMQErrorLoggingTrace = 0;
    }
    return 1;
  }
  if ( fdwReason != 1 )
    return 1;
  v4 = (char *)MmAllocate(0x90u);
  v7 = v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    CCriticalSection::CCriticalSection((CCriticalSection *)(v4 + 16));
    *(_OWORD *)(v7 + 56) = xmmword_1800257D8;
    *(_OWORD *)(v7 + 72) = xmmword_1800257E8;
    v7[96] = 0;
    *((_DWORD *)v7 + 35) = 0;
    v8 = CMSMQTrace::RegisterGuid(v7);
    if ( v8 >= 0 )
      v7[96] = 1;
  }
  else
  {
    v7 = 0;
  }
  try
  {
    try
    {
      g_pMSMQErrorLoggingTrace = (CMSMQTrace *)v7;
      CmInitialize(v6, v5, 0xF003Fu);
    }
    catch ( exception )
    {
      CmInitialize(v9, v18, 0x20019u);
      v3 = hinstDLL;
    }
    qword_18002D098 = (__int64)&ATL::GUID_ATLVer30;
    _Module = 248;
    dword_18002D080 = 769;
    if ( (int)AtlModuleInit(&_Module, &off_18002C000, v3) >= 0 )
    {
      ATL::CComModule::m_libid = LIBID_MSMQTriggerObjects;
      dword_18002D0C0 = 1;
    }
    DisableThreadLibraryCalls(v3);
    WPP_INIT_CONTROL_ARRAY();
    WPP_INIT_GUID_ARRAY();
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    TriggersServiceName = FindTriggersServiceName();
  }
  catch ( exception )
  {
    WppCleanupUm(v12, v18, v13);
    if ( g_pMSMQErrorLoggingTrace )
    {
      CMSMQTrace::`scalar deleting destructor'(g_pMSMQErrorLoggingTrace, v17);
      g_pMSMQErrorLoggingTrace = 0;
    }
    return 0;
  }
  if ( TriggersServiceName )
    return 1;
  WppCleanupUm(v12, v11, v13);
  if ( g_pMSMQErrorLoggingTrace )
  {
    CMSMQTrace::`scalar deleting destructor'(g_pMSMQErrorLoggingTrace, v14);
    g_pMSMQErrorLoggingTrace = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000fcf0  mov     rax, rsp
0x18000fcf3  mov     [rax+10h], rsi
0x18000fcf7  mov     [rax+8], rcx
0x18000fcfb  push    rdi
0x18000fcfc  sub     rsp, 40h
0x18000fd00  movaps  xmmword ptr [rax-18h], xmm6
0x18000fd04  movaps  xmmword ptr [rax-28h], xmm7
0x18000fd08  mov     rsi, rcx
0x18000fd0b  test    edx, edx
0x18000fd0d  jz      loc_18000FE4F
0x18000fd13  cmp     edx, 1
0x18000fd16  jnz     loc_18000FE7D
0x18000fd1c  mov     ecx, 90h; unsigned __int64
0x18000fd21  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000fd26  mov     rdi, rax
0x18000fd29  mov     [rsp+48h+arg_18], rax
0x18000fd2e  test    rax, rax
0x18000fd31  jz      short loc_18000FD83
0x18000fd33  movups  xmm7, cs:xmmword_1800257E8
0x18000fd3a  movups  xmm6, cs:xmmword_1800257D8
0x18000fd41  mov     dword ptr [rax], 0
0x18000fd47  mov     qword ptr [rax+8], 0
0x18000fd4f  lea     rcx, [rax+10h]; this
0x18000fd53  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x18000fd58  nop
0x18000fd59  movdqu  xmmword ptr [rdi+38h], xmm6
0x18000fd5e  movdqu  xmmword ptr [rdi+48h], xmm7
0x18000fd63  mov     byte ptr [rdi+60h], 0
0x18000fd67  mov     dword ptr [rdi+8Ch], 0
0x18000fd71  mov     rcx, rdi; RequestContext
0x18000fd74  call    ?RegisterGuid@CMSMQTrace@@AEAAJXZ; CMSMQTrace::RegisterGuid(void)
0x18000fd79  test    eax, eax
0x18000fd7b  js      short loc_18000FD81
0x18000fd7d  mov     byte ptr [rdi+60h], 1
0x18000fd81  jmp     short loc_18000FD85
0x18000fd83  xor     edi, edi
0x18000fd85  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000fd8c  mov     r8d, 0F003Fh; unsigned int
0x18000fd92  call    ?CmInitialize@@YAXPEAUHKEY__@@PEB_WK@Z; CmInitialize(HKEY__ *,wchar_t const *,ulong)
0x18000fd97  nop
0x18000fd98  jmp     short loc_18000FD9F
0x18000fd9a  mov     rsi, [rsp+48h+arg_0]
0x18000fd9f  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x18000fda6  mov     cs:qword_18002D098, rax
0x18000fdad  mov     cs:?_Module@@3VCComModule@ATL@@A, 0F8h; ATL::CComModule _Module
0x18000fdb7  mov     cs:dword_18002D080, 301h
0x18000fdc1  mov     r8, rsi
0x18000fdc4  lea     rdx, off_18002C000
0x18000fdcb  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fdd2  call    cs:__imp_AtlModuleInit
0x18000fdd8  test    eax, eax
0x18000fdda  js      short loc_18000FDF5
0x18000fddc  movups  xmm0, xmmword ptr cs:LIBID_MSMQTriggerObjects.Data1
0x18000fde3  movdqu  xmmword ptr cs:?m_libid@CComModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CComModule::m_libid ...
0x18000fdeb  mov     cs:dword_18002D0C0, 1
0x18000fdf5  mov     rcx, rsi; hLibModule
0x18000fdf8  call    cs:__imp_DisableThreadLibraryCalls
0x18000fdfe  call    WPP_INIT_CONTROL_ARRAY
0x18000fe03  call    WPP_INIT_GUID_ARRAY
0x18000fe08  lea     rcx, WPP_MAIN_CB
0x18000fe0f  mov     cs:WPP_GLOBAL_Control, rcx
0x18000fe16  call    WppInitUm
0x18000fe1b  call    ?FindTriggersServiceName@@YA_NXZ; FindTriggersServiceName(void)
0x18000fe20  test    al, al
0x18000fe22  jnz     short loc_18000FE49
0x18000fe24  call    WppCleanupUm
0x18000fe29  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; this
0x18000fe30  test    rcx, rcx
0x18000fe33  jz      short loc_18000FE45
0x18000fe35  call    ??_GCMSMQTrace@@QEAAPEAXI@Z; CMSMQTrace::`scalar deleting destructor'(uint)
0x18000fe3a  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000fe45  xor     eax, eax
0x18000fe47  jmp     short loc_18000FE82
0x18000fe49  jmp     short loc_18000FE7D
0x18000fe4b  xor     eax, eax
0x18000fe4d  jmp     short loc_18000FE82
0x18000fe4f  call    WppCleanupUm
0x18000fe54  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000fe5b  call    cs:__imp_AtlModuleTerm
0x18000fe61  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; this
0x18000fe68  test    rcx, rcx
0x18000fe6b  jz      short loc_18000FE7D
0x18000fe6d  call    ??_GCMSMQTrace@@QEAAPEAXI@Z; CMSMQTrace::`scalar deleting destructor'(uint)
0x18000fe72  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000fe7d  mov     eax, 1
0x18000fe82  mov     rsi, [rsp+48h+arg_8]
0x18000fe87  movaps  xmm6, [rsp+48h+var_18]
0x18000fe8c  movaps  xmm7, [rsp+48h+var_28]
0x18000fe91  add     rsp, 40h
0x18000fe95  pop     rdi
0x18000fe96  retn
```
