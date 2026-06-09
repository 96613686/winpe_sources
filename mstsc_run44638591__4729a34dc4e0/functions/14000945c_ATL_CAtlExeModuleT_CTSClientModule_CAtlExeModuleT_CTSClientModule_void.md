# ATL::CAtlExeModuleT<CTSClientModule>::CAtlExeModuleT<CTSClientModule>(void)

- ea: `0x14000945c`
- end: `0x14000954f`
- name: `??0?$CAtlExeModuleT@VCTSClientModule@@@ATL@@QEAA@XZ`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400035b0`

## callees

- `0x14000945c`
- `0x14000aaf0`
- `0x14000ad1c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009524`
- `KERNEL32!GetModuleHandleW` at `0x140009524`
- `KERNEL32!GetCurrentThreadId` at `0x1400094d1`
- `KERNEL32!GetCurrentThreadId` at `0x1400094d1`
- `ole32!CoInitialize` at `0x14000950c`
- `ole32!CoInitialize` at `0x14000950c`

## string_xrefs

- `0x14000951d`: `Mscoree.dll`

## pseudocode

```c
__int64 *ATL::CAtlExeModuleT<CTSClientModule>::CAtlExeModuleT<CTSClientModule>()
{
  DWORD CurrentThreadId; // eax
  HRESULT v1; // eax
  ATL::CAtlComModule *v2; // rcx

  qword_140153A98 = 0;
  qword_140153A68 = 0;
  xmmword_140153A78 = 0;
  qword_140153A70 = 0;
  xmmword_140153A88 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_140153AA0 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_140153A78) >= 0 )
    LODWORD(qword_140153A68) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_MsRdpSessionManager;
  CurrentThreadId = GetCurrentThreadId();
  hObject = 0;
  dword_140153AA8 = CurrentThreadId;
  dword_140153AB8 = 5000;
  dwMilliseconds = 1000;
  byte_140153AC0 = 1;
  byte_140153AC2 = 0;
  v1 = CoInitialize(0);
  if ( v1 >= 0 )
  {
    byte_140153AC2 = 1;
LABEL_9:
    ATL::CAtlComModule::ExecuteObjectMain(v2, 1);
    return &_AtlModule;
  }
  if ( v1 == -2147417850 && GetModuleHandleW(L"Mscoree.dll") )
    goto LABEL_9;
  ATL::CAtlBaseModule::m_bInitFailed = 1;
  return &_AtlModule;
}

```

## disassembly

```asm
0x14000945c  push    rdi
0x14000945e  sub     rsp, 20h
0x140009462  xor     eax, eax
0x140009464  lea     rdi, ?_AtlModule@@3VCTSClientModule@@A; CTSClientModule _AtlModule
0x14000946b  xorps   xmm0, xmm0
0x14000946e  mov     cs:qword_140153A98, rax
0x140009475  lea     rcx, xmmword_140153A78; this
0x14000947c  mov     cs:qword_140153A68, rax
0x140009483  movups  cs:xmmword_140153A78, xmm0
0x14000948a  mov     cs:qword_140153A70, rax
0x140009491  movups  cs:xmmword_140153A88, xmm0
0x140009498  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x14000949f  mov     cs:qword_140153AA0, rax
0x1400094a6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400094ab  test    eax, eax
0x1400094ad  jns     short loc_1400094B8
0x1400094af  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400094b6  jmp     short loc_1400094C2
0x1400094b8  mov     dword ptr cs:qword_140153A68, 38h ; '8'
0x1400094c2  movups  xmm0, xmmword ptr cs:LIBID_MsRdpSessionManager.Data1
0x1400094c9  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x1400094d1  call    cs:__imp_GetCurrentThreadId
0x1400094d7  xor     ecx, ecx; pvReserved
0x1400094d9  mov     cs:hObject, 0
0x1400094e4  mov     cs:dword_140153AA8, eax
0x1400094ea  mov     cs:dword_140153AB8, 1388h
0x1400094f4  mov     cs:dwMilliseconds, 3E8h
0x1400094fe  mov     cs:byte_140153AC0, 1
0x140009505  mov     cs:byte_140153AC2, 0
0x14000950c  call    cs:__imp_CoInitialize
0x140009512  test    eax, eax
0x140009514  jns     short loc_140009538
0x140009516  cmp     eax, 80010106h
0x14000951b  jnz     short loc_14000952F
0x14000951d  lea     rcx, aMscoreeDll; "Mscoree.dll"
0x140009524  call    cs:__imp_GetModuleHandleW
0x14000952a  test    rax, rax
0x14000952d  jnz     short loc_14000953F
0x14000952f  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x140009536  jmp     short loc_140009546
0x140009538  mov     cs:byte_140153AC2, 1
0x14000953f  mov     dl, 1; bool
0x140009541  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x140009546  mov     rax, rdi
0x140009549  add     rsp, 20h
0x14000954d  pop     rdi
0x14000954e  retn
```
