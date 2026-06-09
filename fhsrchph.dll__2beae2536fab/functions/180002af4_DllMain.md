# DllMain

- ea: `0x180002af4`
- end: `0x180002c69`
- name: `DllMain`
- size: `373`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800015c4`

## callees

- `0x180002af4`
- `0x180002de4`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180002c3a`
- `ADVAPI32!UnregisterTraceGuids` at `0x180002c3a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180002bae`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180002bae`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // esi
  ULONG64 *v4; // rbx
  const GUID **v5; // rdi
  const GUID *v6; // r8
  _UNKNOWN **v7; // rbx
  TRACEHANDLE v8; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_1800118F0 = 0;
      v4 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v5 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_1800118F8 = 1;
      do
      {
        v6 = *v5;
        TraceGuidReg.Guid = v6;
        ++v5;
        TraceGuidReg.RegHandle = 0;
        v4[4] = (ULONG64)v6;
        RegisterTraceGuidsW(WppControlCallback, v4, v6, 1u, &TraceGuidReg, 0, 0, v4 + 1);
        v4 = (ULONG64 *)*v4;
      }
      while ( v4 );
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cc7a6b0305ff3ed8dbcae38b87ac4095_Traceguids);
      if ( ATL::CAtlBaseModule::m_bInitFailed )
        return 0;
    }
  }
  else
  {
    v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_cc7a6b0305ff3ed8dbcae38b87ac4095_Traceguids);
        v7 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control )
      {
        while ( v7 )
        {
          v8 = (TRACEHANDLE)v7[1];
          if ( v8 )
          {
            UnregisterTraceGuids(v8);
            v7[1] = 0;
          }
          v7 = (_UNKNOWN **)*v7;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180002af4  mov     [rsp+arg_0], rbx
0x180002af9  mov     [rsp+arg_8], rsi
0x180002afe  push    rdi
0x180002aff  sub     rsp, 50h
0x180002b03  mov     eax, edx
0x180002b05  mov     esi, 1
0x180002b0a  test    edx, edx
0x180002b0c  jz      loc_180002BF5
0x180002b12  cmp     eax, esi
0x180002b14  jz      short loc_180002B23
0x180002b16  cmp     edx, esi
0x180002b18  jnz     loc_180002C57
0x180002b1e  jmp     loc_180002BE8
0x180002b23  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180002b2a  mov     cs:qword_1800118F0, 0
0x180002b35  lea     rbx, WPP_MAIN_CB
0x180002b3c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180002b43  mov     cs:WPP_GLOBAL_Control, rbx
0x180002b4a  lea     rdi, WPP_REGISTRATION_GUIDS
0x180002b51  mov     cs:WPP_MAIN_CB, 0
0x180002b5c  mov     cs:qword_1800118F8, rsi
0x180002b63  mov     r8, [rdi]; ControlGuid
0x180002b66  lea     rax, [rbx+8]
0x180002b6a  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180002b6f  lea     rcx, WppControlCallback; RequestAddress
0x180002b76  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180002b7f  lea     rax, [rsp+58h+var_18]
0x180002b84  mov     [rsp+58h+var_18.Guid], r8
0x180002b89  lea     rdi, [rdi+8]
0x180002b8d  mov     [rsp+58h+var_18.RegHandle], 0
0x180002b96  mov     r9d, esi; GuidCount
0x180002b99  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180002ba2  mov     rdx, rbx; RequestContext
0x180002ba5  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180002baa  mov     [rbx+20h], r8
0x180002bae  call    cs:__imp_RegisterTraceGuidsW
0x180002bb4  mov     rbx, [rbx]
0x180002bb7  test    rbx, rbx
0x180002bba  jnz     short loc_180002B63
0x180002bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bc3  lea     rdi, WPP_GLOBAL_Control
0x180002bca  cmp     rcx, rdi
0x180002bcd  jz      short loc_180002BE8
0x180002bcf  test    byte ptr [rcx+1Ch], 10h
0x180002bd3  jz      short loc_180002BE8
0x180002bd5  mov     rcx, [rcx+10h]
0x180002bd9  lea     edx, [rbx+0Ah]
0x180002bdc  lea     r8, WPP_cc7a6b0305ff3ed8dbcae38b87ac4095_Traceguids
0x180002be3  call    WPP_SF_
0x180002be8  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180002bef  jz      short loc_180002C57
0x180002bf1  xor     esi, esi
0x180002bf3  jmp     short loc_180002C57
0x180002bf5  mov     rbx, cs:WPP_GLOBAL_Control
0x180002bfc  lea     rdi, WPP_GLOBAL_Control
0x180002c03  cmp     rbx, rdi
0x180002c06  jz      short loc_180002C57
0x180002c08  test    byte ptr [rbx+1Ch], 10h
0x180002c0c  jz      short loc_180002C2A
0x180002c0e  mov     rcx, [rbx+10h]
0x180002c12  lea     r8, WPP_cc7a6b0305ff3ed8dbcae38b87ac4095_Traceguids
0x180002c19  mov     edx, 0Bh
0x180002c1e  call    WPP_SF_
0x180002c23  mov     rbx, cs:WPP_GLOBAL_Control
0x180002c2a  cmp     rbx, rdi
0x180002c2d  jz      short loc_180002C57
0x180002c2f  jmp     short loc_180002C4B
0x180002c31  mov     rcx, [rbx+8]; RegistrationHandle
0x180002c35  test    rcx, rcx
0x180002c38  jz      short loc_180002C48
0x180002c3a  call    cs:__imp_UnregisterTraceGuids
0x180002c40  mov     qword ptr [rbx+8], 0
0x180002c48  mov     rbx, [rbx]
0x180002c4b  test    rbx, rbx
0x180002c4e  jnz     short loc_180002C31
0x180002c50  mov     cs:WPP_GLOBAL_Control, rdi
0x180002c57  mov     rbx, [rsp+58h+arg_0]
0x180002c5c  mov     eax, esi
0x180002c5e  mov     rsi, [rsp+58h+arg_8]
0x180002c63  add     rsp, 50h
0x180002c67  pop     rdi
0x180002c68  retn
```
