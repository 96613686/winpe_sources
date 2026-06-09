# DllMain

- ea: `0x180005bb4`
- end: `0x180005d29`
- name: `DllMain`
- size: `373`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800015e4`

## callees

- `0x180005bb4`
- `0x180005ea4`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180005cfa`
- `ADVAPI32!UnregisterTraceGuids` at `0x180005cfa`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180005c6e`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180005c6e`

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
      qword_1800109D0 = 0;
      v4 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v5 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_1800109D8 = 1;
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_35472c39c4853d1c8beed7950ff08e30_Traceguids);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_35472c39c4853d1c8beed7950ff08e30_Traceguids);
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
0x180005bb4  mov     [rsp+arg_0], rbx
0x180005bb9  mov     [rsp+arg_8], rsi
0x180005bbe  push    rdi
0x180005bbf  sub     rsp, 50h
0x180005bc3  mov     eax, edx
0x180005bc5  mov     esi, 1
0x180005bca  test    edx, edx
0x180005bcc  jz      loc_180005CB5
0x180005bd2  cmp     eax, esi
0x180005bd4  jz      short loc_180005BE3
0x180005bd6  cmp     edx, esi
0x180005bd8  jnz     loc_180005D17
0x180005bde  jmp     loc_180005CA8
0x180005be3  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180005bea  mov     cs:qword_1800109D0, 0
0x180005bf5  lea     rbx, WPP_MAIN_CB
0x180005bfc  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180005c03  mov     cs:WPP_GLOBAL_Control, rbx
0x180005c0a  lea     rdi, WPP_REGISTRATION_GUIDS
0x180005c11  mov     cs:WPP_MAIN_CB, 0
0x180005c1c  mov     cs:qword_1800109D8, rsi
0x180005c23  mov     r8, [rdi]; ControlGuid
0x180005c26  lea     rax, [rbx+8]
0x180005c2a  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180005c2f  lea     rcx, WppControlCallback; RequestAddress
0x180005c36  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180005c3f  lea     rax, [rsp+58h+var_18]
0x180005c44  mov     [rsp+58h+var_18.Guid], r8
0x180005c49  lea     rdi, [rdi+8]
0x180005c4d  mov     [rsp+58h+var_18.RegHandle], 0
0x180005c56  mov     r9d, esi; GuidCount
0x180005c59  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180005c62  mov     rdx, rbx; RequestContext
0x180005c65  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180005c6a  mov     [rbx+20h], r8
0x180005c6e  call    cs:__imp_RegisterTraceGuidsW
0x180005c74  mov     rbx, [rbx]
0x180005c77  test    rbx, rbx
0x180005c7a  jnz     short loc_180005C23
0x180005c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c83  lea     rdi, WPP_GLOBAL_Control
0x180005c8a  cmp     rcx, rdi
0x180005c8d  jz      short loc_180005CA8
0x180005c8f  test    byte ptr [rcx+1Ch], 10h
0x180005c93  jz      short loc_180005CA8
0x180005c95  mov     rcx, [rcx+10h]
0x180005c99  lea     edx, [rbx+0Ah]
0x180005c9c  lea     r8, WPP_35472c39c4853d1c8beed7950ff08e30_Traceguids
0x180005ca3  call    WPP_SF_
0x180005ca8  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180005caf  jz      short loc_180005D17
0x180005cb1  xor     esi, esi
0x180005cb3  jmp     short loc_180005D17
0x180005cb5  mov     rbx, cs:WPP_GLOBAL_Control
0x180005cbc  lea     rdi, WPP_GLOBAL_Control
0x180005cc3  cmp     rbx, rdi
0x180005cc6  jz      short loc_180005D17
0x180005cc8  test    byte ptr [rbx+1Ch], 10h
0x180005ccc  jz      short loc_180005CEA
0x180005cce  mov     rcx, [rbx+10h]
0x180005cd2  lea     r8, WPP_35472c39c4853d1c8beed7950ff08e30_Traceguids
0x180005cd9  mov     edx, 0Bh
0x180005cde  call    WPP_SF_
0x180005ce3  mov     rbx, cs:WPP_GLOBAL_Control
0x180005cea  cmp     rbx, rdi
0x180005ced  jz      short loc_180005D17
0x180005cef  jmp     short loc_180005D0B
0x180005cf1  mov     rcx, [rbx+8]; RegistrationHandle
0x180005cf5  test    rcx, rcx
0x180005cf8  jz      short loc_180005D08
0x180005cfa  call    cs:__imp_UnregisterTraceGuids
0x180005d00  mov     qword ptr [rbx+8], 0
0x180005d08  mov     rbx, [rbx]
0x180005d0b  test    rbx, rbx
0x180005d0e  jnz     short loc_180005CF1
0x180005d10  mov     cs:WPP_GLOBAL_Control, rdi
0x180005d17  mov     rbx, [rsp+58h+arg_0]
0x180005d1c  mov     eax, esi
0x180005d1e  mov     rsi, [rsp+58h+arg_8]
0x180005d23  add     rsp, 50h
0x180005d27  pop     rdi
0x180005d28  retn
```
