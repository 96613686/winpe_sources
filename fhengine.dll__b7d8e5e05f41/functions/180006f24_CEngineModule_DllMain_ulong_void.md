# CEngineModule::DllMain(ulong,void *)

- ea: `0x180006f24`
- end: `0x1800070bb`
- name: `?DllMain@CEngineModule@@QEAAHKPEAX@Z`
- size: `407`
- prototype: `__int64 __fastcall(CEngineModule *this, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180007544`

## callees

- `0x180006f24`
- `0x18000732c`
- `0x180007788`
- `0x1800077c0`
- `0x1800077f0`
- `0x1800078e8`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180007014`
- `ADVAPI32!UnregisterTraceGuids` at `0x180007014`
- `KERNEL32!RaiseException` at `0x1800070b4`
- `KERNEL32!RaiseException` at `0x1800070b4`
- `KERNEL32!DeleteCriticalSection` at `0x180007084`
- `KERNEL32!DeleteCriticalSection` at `0x180007084`
- `USER32!UnregisterClassW` at `0x180007061`
- `USER32!UnregisterClassW` at `0x180007061`

## pseudocode

```c
__int64 __fastcall CEngineModule::DllMain(CEngineModule *this, __int64 a2, void *a3)
{
  PVOID *v4; // rdi
  int v5; // edi
  HINSTANCE i; // rsi

  if ( (_DWORD)a2 == 1 )
  {
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
    McGenEventRegister_EventRegister(this, a2, a3);
    qword_180040AA0 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    qword_180040AA8 = 1;
    WppInitUm();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids);
  }
  else if ( !(_DWORD)a2 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control )
      {
        while ( v4 )
        {
          this = (CEngineModule *)v4[1];
          if ( this )
          {
            UnregisterTraceGuids((TRACEHANDLE)this);
            v4[1] = 0;
          }
          v4 = (PVOID *)*v4;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    McGenEventUnregister_EventUnregister(this, a2, a3);
    if ( ATL::_AtlWinModule == 72 )
    {
      v5 = 0;
      for ( i = hInstance; v5 < dword_1800403A0; ++v5 )
      {
        if ( v5 < 0 )
        {
          RaiseException(0xC000008C, 1u, 0, 0);
          JUMPOUT(0x1800070BALL);
        }
        UnregisterClassW((LPCWSTR)*(unsigned __int16 *)(qword_180040398 + 2LL * v5), i);
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&qword_180040398);
      DeleteCriticalSection(&CriticalSection);
      ATL::_AtlWinModule = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180006f24  mov     [rsp+arg_0], rbx
0x180006f29  mov     [rsp+arg_8], rsi
0x180006f2e  push    rdi
0x180006f2f  sub     rsp, 20h
0x180006f33  xor     ebx, ebx
0x180006f35  cmp     edx, 1
0x180006f38  jnz     loc_180006FC7
0x180006f3e  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, bl; bool ATL::CAtlBaseModule::m_bInitFailed
0x180006f44  jz      short loc_180006F4D
0x180006f46  xor     eax, eax
0x180006f48  jmp     loc_180007095
0x180006f4d  call    McGenEventRegister_EventRegister
0x180006f52  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180006f59  mov     cs:qword_180040AA0, rbx
0x180006f60  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180006f67  lea     rax, WPP_MAIN_CB
0x180006f6e  mov     cs:WPP_GLOBAL_Control, rax
0x180006f75  mov     cs:WPP_MAIN_CB, rbx
0x180006f7c  mov     cs:qword_180040AA8, 1
0x180006f87  call    WppInitUm
0x180006f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f93  lea     rsi, WPP_GLOBAL_Control
0x180006f9a  cmp     rcx, rsi
0x180006f9d  jz      loc_180007090
0x180006fa3  test    byte ptr [rcx+1Ch], 10h
0x180006fa7  jz      loc_180007090
0x180006fad  mov     rcx, [rcx+10h]
0x180006fb1  lea     r8, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids
0x180006fb8  mov     edx, 0Ah
0x180006fbd  call    WPP_SF_
0x180006fc2  jmp     loc_180007090
0x180006fc7  test    edx, edx
0x180006fc9  jnz     loc_180007090
0x180006fcf  mov     rdi, cs:WPP_GLOBAL_Control
0x180006fd6  lea     rsi, WPP_GLOBAL_Control
0x180006fdd  cmp     rdi, rsi
0x180006fe0  jz      short loc_18000702D
0x180006fe2  test    byte ptr [rdi+1Ch], 10h
0x180006fe6  jz      short loc_180007004
0x180006fe8  mov     rcx, [rdi+10h]
0x180006fec  lea     r8, WPP_96e2a10888f0373d27c6534814b7f9a0_Traceguids
0x180006ff3  mov     edx, 0Bh
0x180006ff8  call    WPP_SF_
0x180006ffd  mov     rdi, cs:WPP_GLOBAL_Control
0x180007004  cmp     rdi, rsi
0x180007007  jz      short loc_18000702D
0x180007009  jmp     short loc_180007021
0x18000700b  mov     rcx, [rdi+8]; RegistrationHandle
0x18000700f  test    rcx, rcx
0x180007012  jz      short loc_18000701E
0x180007014  call    cs:__imp_UnregisterTraceGuids
0x18000701a  mov     [rdi+8], rbx
0x18000701e  mov     rdi, [rdi]
0x180007021  test    rdi, rdi
0x180007024  jnz     short loc_18000700B
0x180007026  mov     cs:WPP_GLOBAL_Control, rsi
0x18000702d  call    McGenEventUnregister_EventUnregister
0x180007032  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x180007039  jnz     short loc_180007090
0x18000703b  cmp     cs:dword_1800403A0, ebx
0x180007041  mov     edi, ebx
0x180007043  mov     rsi, cs:hInstance
0x18000704a  jle     short loc_180007071
0x18000704c  test    edi, edi
0x18000704e  js      short loc_1800070A5
0x180007050  mov     rax, cs:qword_180040398
0x180007057  mov     rdx, rsi; hInstance
0x18000705a  movsxd  rcx, edi
0x18000705d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180007061  call    cs:__imp_UnregisterClassW
0x180007067  inc     edi
0x180007069  cmp     edi, cs:dword_1800403A0
0x18000706f  jl      short loc_18000704C
0x180007071  lea     rcx, qword_180040398
0x180007078  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000707d  lea     rcx, CriticalSection; lpCriticalSection
0x180007084  call    cs:__imp_DeleteCriticalSection
0x18000708a  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, ebx; ATL::CAtlWinModule ATL::_AtlWinModule
0x180007090  mov     eax, 1
0x180007095  mov     rbx, [rsp+28h+arg_0]
0x18000709a  mov     rsi, [rsp+28h+arg_8]
0x18000709f  add     rsp, 20h
0x1800070a3  pop     rdi
0x1800070a4  retn
0x1800070a5  xor     r9d, r9d; lpArguments
0x1800070a8  xor     r8d, r8d; nNumberOfArguments
0x1800070ab  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800070b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800070b4  call    cs:__imp_RaiseException
```
