# ATL::CAtlExeModuleT<HostExeModule>::CAtlExeModuleT<HostExeModule>(void)

- ea: `0x140004320`
- end: `0x140004406`
- name: `??0?$CAtlExeModuleT@VHostExeModule@@@ATL@@QEAA@XZ`
- size: `230`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400018e0`

## callees

- `0x140004320`
- `0x1400059c4`
- `0x140005d3c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004386`
- `KERNEL32!GetCurrentThreadId` at `0x140004386`
- `KERNEL32!GetModuleHandleW` at `0x1400043db`
- `KERNEL32!GetModuleHandleW` at `0x1400043db`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400043c3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400043c3`

## string_xrefs

- `0x1400043d4`: `Mscoree.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *ATL::CAtlExeModuleT<HostExeModule>::CAtlExeModuleT<HostExeModule>()
{
  HRESULT v0; // eax
  ATL::CAtlComModule *v1; // rcx

  xmmword_140080DF8 = 0;
  xmmword_140080E08 = 0;
  qword_140080E18 = 0;
  qword_140080DE8 = 0;
  qword_140080DF0 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_140080E20 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_140080DF8) >= 0 )
    LODWORD(qword_140080DE8) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  dword_140080E28 = GetCurrentThreadId();
  hEvent = 0;
  dwMilliseconds = 5000;
  dword_140080E3C = 1000;
  byte_140080E40 = 1;
  byte_140080E42 = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 >= 0 )
  {
    byte_140080E42 = 1;
LABEL_9:
    ATL::CAtlComModule::ExecuteObjectMain(v1, 1);
    return &_AtlModule;
  }
  if ( v0 == -2147417850 && GetModuleHandleW(L"Mscoree.dll") )
    goto LABEL_9;
  ATL::CAtlBaseModule::m_bInitFailed = 1;
  return &_AtlModule;
}

```

## disassembly

```asm
0x140004320  push    rdi
0x140004322  sub     rsp, 20h
0x140004326  xorps   xmm0, xmm0
0x140004329  xor     eax, eax
0x14000432b  movups  cs:xmmword_140080DF8, xmm0
0x140004332  movups  cs:xmmword_140080E08, xmm0
0x140004339  mov     cs:qword_140080E18, rax
0x140004340  mov     cs:qword_140080DE8, rax
0x140004347  mov     cs:qword_140080DF0, rax
0x14000434e  lea     rdi, ?_AtlModule@@3VHostExeModule@@A; HostExeModule _AtlModule
0x140004355  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rdi; ATL::CAtlModule * ATL::_pAtlModule
0x14000435c  mov     cs:qword_140080E20, rax
0x140004363  lea     rcx, xmmword_140080DF8; this
0x14000436a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000436f  test    eax, eax
0x140004371  jns     short loc_14000437C
0x140004373  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000437a  jmp     short loc_140004386
0x14000437c  mov     dword ptr cs:qword_140080DE8, 38h ; '8'
0x140004386  call    cs:__imp_GetCurrentThreadId
0x14000438c  mov     cs:dword_140080E28, eax
0x140004392  mov     cs:hEvent, 0
0x14000439d  mov     cs:dwMilliseconds, 1388h
0x1400043a7  mov     cs:dword_140080E3C, 3E8h
0x1400043b1  mov     cs:byte_140080E40, 1
0x1400043b8  mov     cs:byte_140080E42, 0
0x1400043bf  xor     edx, edx; dwCoInit
0x1400043c1  xor     ecx, ecx; pvReserved
0x1400043c3  call    cs:__imp_CoInitializeEx
0x1400043c9  test    eax, eax
0x1400043cb  jns     short loc_1400043EF
0x1400043cd  cmp     eax, 80010106h
0x1400043d2  jnz     short loc_1400043E6
0x1400043d4  lea     rcx, aMscoreeDll_0; "Mscoree.dll"
0x1400043db  call    cs:__imp_GetModuleHandleW
0x1400043e1  test    rax, rax
0x1400043e4  jnz     short loc_1400043F6
0x1400043e6  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x1400043ed  jmp     short loc_1400043FD
0x1400043ef  mov     cs:byte_140080E42, 1
0x1400043f6  mov     dl, 1; bool
0x1400043f8  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x1400043fd  mov     rax, rdi
0x140004400  add     rsp, 20h
0x140004404  pop     rdi
0x140004405  retn
```
