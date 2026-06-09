# CDataIntegrityScanModule::DllMain(ulong,void *)

- ea: `0x1800072b0`
- end: `0x180007483`
- name: `?DllMain@CDataIntegrityScanModule@@QEAAHKPEAX@Z`
- size: `467`
- prototype: `__int64 __fastcall(CDataIntegrityScanModule *this, __int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007910`

## callees

- `0x1800015bc`
- `0x180006470`
- `0x1800072b0`
- `0x18000769c`
- `0x180007ab8`
- `0x180007adc`
- `0x180007bf8`
- `0x180010b20`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x1800073de`
- `ADVAPI32!UnregisterTraceGuids` at `0x1800073de`
- `USER32!UnregisterClassW` at `0x18000742a`
- `USER32!UnregisterClassW` at `0x18000742a`
- `KERNEL32!DeleteCriticalSection` at `0x18000744d`
- `KERNEL32!DeleteCriticalSection` at `0x18000744d`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1800072e2`
- `KERNEL32!DisableThreadLibraryCalls` at `0x1800072e2`
- `KERNEL32!RaiseException` at `0x18000747c`
- `KERNEL32!RaiseException` at `0x18000747c`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanModule::DllMain(CDataIntegrityScanModule *this, __int64 a2, void *a3)
{
  __int64 v4; // rdx
  PVOID *v5; // rbx
  TRACEHANDLE v6; // rcx
  HINSTANCE v7; // rdi
  int i; // ebx

  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
    {
      if ( ATL::CAtlBaseModule::m_bInitFailed )
        return 0;
      DisableThreadLibraryCalls(hInstance);
      qword_180048120 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WppTrace;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_180048128 = 1;
      WppInitUm();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b9009e9ed3da3c0b73e8125b1189cdb7_Traceguids);
      }
      McGenEventRegister_EventRegister(
        DISCAN_EVENT_PROVIDER,
        v4,
        DISCAN_EVENT_PROVIDER_Context,
        DISCAN_EVENT_PROVIDER_Context);
      TraceLoggingEventSetup();
    }
  }
  else
  {
    TraceLoggingUnregister_EventUnregister(this, a2, a3);
    McGenEventUnregister_EventUnregister(DISCAN_EVENT_PROVIDER_Context);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b9009e9ed3da3c0b73e8125b1189cdb7_Traceguids);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control )
      {
        while ( v5 )
        {
          v6 = (TRACEHANDLE)v5[1];
          if ( v6 )
          {
            UnregisterTraceGuids(v6);
            v5[1] = 0;
          }
          v5 = (PVOID *)*v5;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    if ( ATL::_AtlWinModule == 72 )
    {
      v7 = hInstance;
      for ( i = 0; i < dword_180047AA0; ++i )
      {
        if ( i < 0 )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          JUMPOUT(0x180007482LL);
        }
        UnregisterClassW((LPCWSTR)*(unsigned __int16 *)(qword_180047A98 + 2LL * i), v7);
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_180047A98);
      DeleteCriticalSection(&CriticalSection);
      ATL::_AtlWinModule = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800072b0  mov     [rsp+arg_0], rbx
0x1800072b5  push    rdi
0x1800072b6  sub     rsp, 20h
0x1800072ba  test    edx, edx
0x1800072bc  jz      loc_180007382
0x1800072c2  cmp     edx, 1
0x1800072c5  jnz     loc_18000745D
0x1800072cb  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x1800072d2  jz      short loc_1800072DB
0x1800072d4  xor     eax, eax
0x1800072d6  jmp     loc_180007462
0x1800072db  mov     rcx, cs:hInstance; hLibModule
0x1800072e2  call    cs:__imp_DisableThreadLibraryCalls
0x1800072e8  lea     rax, WPP_ThisDir_CTLGUID_WppTrace
0x1800072ef  mov     cs:qword_180048120, 0
0x1800072fa  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180007301  lea     rax, WPP_MAIN_CB
0x180007308  mov     cs:WPP_GLOBAL_Control, rax
0x18000730f  mov     cs:WPP_MAIN_CB, 0
0x18000731a  mov     cs:qword_180048128, 1
0x180007325  call    WppInitUm
0x18000732a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007331  lea     rdi, WPP_GLOBAL_Control
0x180007338  cmp     rcx, rdi
0x18000733b  jz      short loc_18000735E
0x18000733d  test    byte ptr [rcx+1Ch], 1
0x180007341  jz      short loc_18000735E
0x180007343  cmp     byte ptr [rcx+19h], 2
0x180007347  jb      short loc_18000735E
0x180007349  mov     rcx, [rcx+10h]
0x18000734d  lea     r8, WPP_b9009e9ed3da3c0b73e8125b1189cdb7_Traceguids
0x180007354  mov     edx, 0Ah
0x180007359  call    WPP_SF_
0x18000735e  lea     r9, DISCAN_EVENT_PROVIDER_Context
0x180007365  lea     r8, DISCAN_EVENT_PROVIDER_Context
0x18000736c  lea     rcx, DISCAN_EVENT_PROVIDER
0x180007373  call    McGenEventRegister_EventRegister
0x180007378  call    ?TraceLoggingEventSetup@@YAJXZ; TraceLoggingEventSetup(void)
0x18000737d  jmp     loc_18000745D
0x180007382  call    TraceLoggingUnregister_EventUnregister
0x180007387  lea     rcx, DISCAN_EVENT_PROVIDER_Context
0x18000738e  call    McGenEventUnregister_EventUnregister
0x180007393  mov     rbx, cs:WPP_GLOBAL_Control
0x18000739a  lea     rdi, WPP_GLOBAL_Control
0x1800073a1  cmp     rbx, rdi
0x1800073a4  jz      short loc_1800073FB
0x1800073a6  test    byte ptr [rbx+1Ch], 1
0x1800073aa  jz      short loc_1800073CE
0x1800073ac  cmp     byte ptr [rbx+19h], 2
0x1800073b0  jb      short loc_1800073CE
0x1800073b2  mov     rcx, [rbx+10h]
0x1800073b6  lea     r8, WPP_b9009e9ed3da3c0b73e8125b1189cdb7_Traceguids
0x1800073bd  mov     edx, 0Bh
0x1800073c2  call    WPP_SF_
0x1800073c7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800073ce  cmp     rbx, rdi
0x1800073d1  jz      short loc_1800073FB
0x1800073d3  jmp     short loc_1800073EF
0x1800073d5  mov     rcx, [rbx+8]; RegistrationHandle
0x1800073d9  test    rcx, rcx
0x1800073dc  jz      short loc_1800073EC
0x1800073de  call    cs:__imp_UnregisterTraceGuids
0x1800073e4  mov     qword ptr [rbx+8], 0
0x1800073ec  mov     rbx, [rbx]
0x1800073ef  test    rbx, rbx
0x1800073f2  jnz     short loc_1800073D5
0x1800073f4  mov     cs:WPP_GLOBAL_Control, rdi
0x1800073fb  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180007402  jnz     short loc_18000745D
0x180007404  mov     rdi, cs:hInstance
0x18000740b  xor     ebx, ebx
0x18000740d  cmp     cs:dword_180047AA0, ebx
0x180007413  jle     short loc_18000743A
0x180007415  test    ebx, ebx
0x180007417  js      short loc_18000746D
0x180007419  mov     rax, cs:qword_180047A98
0x180007420  mov     rdx, rdi; hInstance
0x180007423  movsxd  rcx, ebx
0x180007426  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000742a  call    cs:__imp_UnregisterClassW
0x180007430  inc     ebx
0x180007432  cmp     ebx, cs:dword_180047AA0
0x180007438  jl      short loc_180007415
0x18000743a  lea     rcx, qword_180047A98
0x180007441  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x180007446  lea     rcx, CriticalSection; lpCriticalSection
0x18000744d  call    cs:__imp_DeleteCriticalSection
0x180007453  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 0; ATL::CAtlWinModule ATL::_AtlWinModule
0x18000745d  mov     eax, 1
0x180007462  mov     rbx, [rsp+28h+arg_0]
0x180007467  add     rsp, 20h
0x18000746b  pop     rdi
0x18000746c  retn
0x18000746d  xor     r9d, r9d; lpArguments
0x180007470  xor     r8d, r8d; nNumberOfArguments
0x180007473  mov     ecx, 0C000008Ch; dwExceptionCode
0x180007478  lea     edx, [r9+1]; dwExceptionFlags
0x18000747c  call    cs:__imp_RaiseException
```
