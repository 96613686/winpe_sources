# OneTimeInit

- ea: `0x180013e88`
- end: `0x1800140db`
- name: `OneTimeInit`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014458`

## callees

- `0x180001008`
- `0x1800022d6`
- `0x1800093d0`
- `0x18001305c`
- `0x1800138d4`
- `0x180013a1c`
- `0x180013af4`
- `0x180013e88`
- `0x1800140e4`
- `0x180014388`
- `0x180014b58`
- `0x18001522c`
- `0x180015e08`
- `0x1800160e4`
- `0x180021010`
- `0x1800212fc`
- `0x1800237d4`
- `0x18002395c`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180013f6c`
- `KERNEL32!GetCommandLineW` at `0x180013f6c`
- `mqsec!GetFalconKeyValue` at `0x180013ff1`
- `mqsec!GetFalconKeyValue` at `0x180013ff1`
- `mqsec!g_CancelRpc` at `0x180013f90`
- `mqsec!?Init@CCancelRpc@@QEAAXXZ` at `0x180013f97`
- `mqsec!?Init@CCancelRpc@@QEAAXXZ` at `0x180013f97`
- `mqsec!MSMQGetOperatingSystem` at `0x180013fa9`
- `mqsec!MSMQGetOperatingSystem` at `0x180013fa9`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x180014011`
- `mqsec!?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z` at `0x180014011`

## string_xrefs

- `0x18001405c`: `EnableCreateQueueThroughService`
- `0x180013fea`: `MachineCache\LongLiveTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 OneTimeInit()
{
  char *v0; // rax
  char *v1; // rbx
  wchar_t *CommandLineW; // rax
  signed int FalconSectionName; // eax
  HKEY v4; // rcx
  unsigned int v5; // r8d
  const wchar_t *v6; // rdx
  __int64 v7; // rdx
  unsigned int v9; // [rsp+38h] [rbp-39h] BYREF
  unsigned int v10; // [rsp+3Ch] [rbp-35h] BYREF
  char *v11; // [rsp+40h] [rbp-31h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-29h] BYREF
  const WCHAR *v13; // [rsp+50h] [rbp-21h]
  const wchar_t *v14; // [rsp+58h] [rbp-19h]
  int v15; // [rsp+60h] [rbp-11h]
  __int64 v16; // [rsp+68h] [rbp-9h]
  char v17[8]; // [rsp+70h] [rbp-1h] BYREF
  wchar_t *v18[3]; // [rsp+78h] [rbp+7h] BYREF
  unsigned __int64 v19; // [rsp+90h] [rbp+1Fh]

  if ( !g_pMSMQErrorLoggingTrace )
  {
    v0 = (char *)MmAllocate(0x90u);
    v1 = v0;
    v11 = v0;
    if ( v0 )
    {
      *(_DWORD *)v0 = 0;
      *((_QWORD *)v0 + 1) = 0;
      CCriticalSection::CCriticalSection((CCriticalSection *)(v0 + 16));
      *(_OWORD *)(v1 + 56) = xmmword_1800321E8;
      *(_OWORD *)(v1 + 72) = xmmword_1800321F8;
      v1[96] = 0;
      *((_DWORD *)v1 + 35) = 0;
      if ( (int)CMSMQTrace::RegisterGuid(v1) >= 0 )
        v1[96] = 1;
    }
    else
    {
      v1 = 0;
    }
    g_pMSMQErrorLoggingTrace = (CMSMQTrace *)v1;
  }
  if ( g_dwThreadEventIndex == -1 )
    g_dwThreadEventIndex = RtpTlsAlloc();
  InitRpcGlobals();
  if ( !byte_18003DD18 )
  {
    byte_18003DD18 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), CommandLineW);
    }
  }
  if ( !byte_18003DD1A )
  {
    CCancelRpc::Init(g_CancelRpc);
    byte_18003DD1A = 1;
  }
  RtpGetComputerName();
  MSMQGetOperatingSystem();
  OneTimeThreadInit();
  InitServiceName();
  InitQMId();
  v10 = g_dwTimeToReachQueueDefault;
  v9 = 4;
  LODWORD(v11) = 4;
  GetFalconKeyValue(
    L"MachineCache\\LongLiveTime",
    (unsigned int *)&v11,
    &g_dwTimeToReachQueueDefault,
    &v9,
    (const wchar_t *)&v10);
  v19 = 7;
  v18[2] = 0;
  LOWORD(v18[0]) = 0;
  FalconSectionName = GetFalconSectionName(v17);
  if ( FalconSectionName < 0 )
  {
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, FalconSectionName);
    throw (bad_hresult *)&pExceptionObject;
  }
  v6 = (const wchar_t *)v18;
  if ( v19 >= 8 )
    v6 = v18[0];
  CmInitialize(v4, v6, v5);
  pExceptionObject = 0;
  v13 = &Class;
  v14 = L"EnableCreateQueueThroughService";
  v15 = 1;
  v16 = 0;
  v9 = 1;
  QueryValueInternal((struct RegEntry *)&pExceptionObject);
  g_fOnFailureCallServiceToCreatePublicQueue = v9 != 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  InitACDriverName();
  LOBYTE(v7) = 1;
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v17, v7);
}

```

## disassembly

```asm
0x180013e88  mov     rax, rsp
0x180013e8b  mov     [rax+8], rbx
0x180013e8f  push    rbp
0x180013e90  lea     rbp, [rax-5Fh]
0x180013e94  sub     rsp, 0C0h
0x180013e9b  movaps  xmmword ptr [rax-18h], xmm6
0x180013e9f  movaps  xmmword ptr [rax-28h], xmm7
0x180013ea3  mov     rax, cs:__security_cookie
0x180013eaa  xor     rax, rsp
0x180013ead  mov     [rbp+57h+var_30], rax
0x180013eb1  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180013eb9  jnz     short loc_180013F2A
0x180013ebb  mov     ecx, 90h; unsigned __int64
0x180013ec0  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180013ec5  mov     rbx, rax
0x180013ec8  mov     [rbp+57h+var_88], rax
0x180013ecc  test    rax, rax
0x180013ecf  jz      short loc_180013F21
0x180013ed1  movups  xmm7, cs:xmmword_1800321F8
0x180013ed8  movups  xmm6, cs:xmmword_1800321E8
0x180013edf  mov     dword ptr [rax], 0
0x180013ee5  mov     qword ptr [rax+8], 0
0x180013eed  lea     rcx, [rax+10h]; this
0x180013ef1  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x180013ef6  nop
0x180013ef7  movdqu  xmmword ptr [rbx+38h], xmm6
0x180013efc  movdqu  xmmword ptr [rbx+48h], xmm7
0x180013f01  mov     byte ptr [rbx+60h], 0
0x180013f05  mov     dword ptr [rbx+8Ch], 0
0x180013f0f  mov     rcx, rbx; RequestContext
0x180013f12  call    ?RegisterGuid@CMSMQTrace@@AEAAJXZ; CMSMQTrace::RegisterGuid(void)
0x180013f17  test    eax, eax
0x180013f19  js      short loc_180013F1F
0x180013f1b  mov     byte ptr [rbx+60h], 1
0x180013f1f  jmp     short loc_180013F23
0x180013f21  xor     ebx, ebx
0x180013f23  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180013f2a  cmp     cs:?g_dwThreadEventIndex@@3KA, 0FFFFFFFFh; ulong g_dwThreadEventIndex
0x180013f31  jnz     short loc_180013F3E
0x180013f33  call    ?RtpTlsAlloc@@YAKXZ; RtpTlsAlloc(void)
0x180013f38  mov     cs:?g_dwThreadEventIndex@@3KA, eax; ulong g_dwThreadEventIndex
0x180013f3e  call    ?InitRpcGlobals@@YAXXZ; InitRpcGlobals(void)
0x180013f43  cmp     cs:byte_18003DD18, 0
0x180013f4a  jnz     short loc_180013F87
0x180013f4c  mov     cs:byte_18003DD18, 1
0x180013f53  lea     rcx, WPP_GLOBAL_Control
0x180013f5a  mov     rax, cs:WPP_GLOBAL_Control
0x180013f61  cmp     rax, rcx
0x180013f64  jz      short loc_180013F87
0x180013f66  test    byte ptr [rax+1Ch], 1
0x180013f6a  jz      short loc_180013F87
0x180013f6c  call    cs:__imp_GetCommandLineW
0x180013f72  mov     [rsp+0C0h+var_A0], rax; wchar_t *
0x180013f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f7e  mov     rcx, [rcx+10h]; LoggerHandle
0x180013f82  call    WPP_SF_sS
0x180013f87  cmp     cs:byte_18003DD1A, 0
0x180013f8e  jnz     short loc_180013FA4
0x180013f90  mov     rcx, cs:__imp_?g_CancelRpc@@3VCCancelRpc@@A; CCancelRpc g_CancelRpc
0x180013f97  call    cs:__imp_?Init@CCancelRpc@@QEAAXXZ; CCancelRpc::Init(void)
0x180013f9d  mov     cs:byte_18003DD1A, 1
0x180013fa4  call    RtpGetComputerName
0x180013fa9  call    cs:__imp_MSMQGetOperatingSystem
0x180013faf  call    OneTimeThreadInit
0x180013fb4  call    InitServiceName
0x180013fb9  call    ?InitQMId@@YAXXZ; InitQMId(void)
0x180013fbe  mov     eax, cs:?g_dwTimeToReachQueueDefault@@3KA; ulong g_dwTimeToReachQueueDefault
0x180013fc4  mov     [rbp+57h+var_8C], eax
0x180013fc7  mov     ebx, 4
0x180013fcc  mov     [rbp+57h+var_90], ebx
0x180013fcf  mov     dword ptr [rbp+57h+var_88], ebx
0x180013fd2  lea     rax, [rbp+57h+var_8C]
0x180013fd6  mov     [rsp+0C0h+var_A0], rax
0x180013fdb  lea     r9, [rbp+57h+var_90]
0x180013fdf  lea     r8, ?g_dwTimeToReachQueueDefault@@3KA; ulong g_dwTimeToReachQueueDefault
0x180013fe6  lea     rdx, [rbp+57h+var_88]
0x180013fea  lea     rcx, aMachinecacheLo; "MachineCache\\LongLiveTime"
0x180013ff1  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180013ff7  mov     [rbp+57h+var_38], 7
0x180013fff  mov     [rbp+57h+var_40], 0
0x180014007  xor     eax, eax
0x180014009  mov     word ptr [rbp+57h+var_50], ax
0x18001400d  lea     rcx, [rbp+57h+var_58]
0x180014011  call    cs:__imp_?GetFalconSectionName@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; GetFalconSectionName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> &)
0x180014017  test    eax, eax
0x180014019  jns     short loc_180014037
0x18001401b  mov     edx, eax; unsigned int
0x18001401d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180014021  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180014026  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x18001402d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180014031  call    _CxxThrowException_0
0x180014037  lea     rdx, [rbp+57h+var_50]
0x18001403b  cmp     [rbp+57h+var_38], 8
0x180014040  cmovnb  rdx, [rbp+57h+var_50]; wchar_t *
0x180014045  call    ?CmInitialize@@YAXPEAUHKEY__@@PEB_WK@Z; CmInitialize(HKEY__ *,wchar_t const *,ulong)
0x18001404a  mov     [rbp+57h+pExceptionObject], 0
0x180014051  lea     rax, Class
0x180014058  mov     [rbp+57h+var_78], rax
0x18001405c  lea     rax, aEnablecreatequ; "EnableCreateQueueThroughService"
0x180014063  mov     [rbp+57h+var_70], rax
0x180014067  mov     [rbp+57h+var_68], 1
0x18001406e  mov     [rbp+57h+var_60], 0
0x180014076  mov     [rbp+57h+var_90], 1
0x18001407d  mov     r9d, ebx
0x180014080  lea     r8, [rbp+57h+var_90]
0x180014084  mov     edx, ebx
0x180014086  lea     rcx, [rbp+57h+pExceptionObject]; struct RegEntry *
0x18001408a  call    QueryValueInternal
0x18001408f  xor     eax, eax
0x180014091  cmp     [rbp+57h+var_90], eax
0x180014094  setnz   al
0x180014097  mov     cs:?g_fOnFailureCallServiceToCreatePublicQueue@@3HA, eax; int g_fOnFailureCallServiceToCreatePublicQueue
0x18001409d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800140a2  call    ?InitACDriverName@@YAXXZ; InitACDriverName(void)
0x1800140a7  nop
0x1800140a8  mov     dl, 1
0x1800140aa  lea     rcx, [rbp+57h+var_58]
0x1800140ae  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x1800140b3  nop
0x1800140b4  mov     rcx, [rbp+57h+var_30]
0x1800140b8  xor     rcx, rsp; StackCookie
0x1800140bb  call    __security_check_cookie
0x1800140c0  lea     r11, [rsp+0C0h+var_s0]
0x1800140c8  mov     rbx, [r11+10h]
0x1800140cc  movaps  xmm6, xmmword ptr [r11-10h]
0x1800140d1  movaps  xmm7, xmmword ptr [r11-20h]
0x1800140d6  mov     rsp, r11
0x1800140d9  pop     rbp
0x1800140da  retn
```
