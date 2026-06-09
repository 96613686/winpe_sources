# DllMain

- ea: `0x180002b4c`
- end: `0x180002c62`
- name: `DllMain`
- size: `278`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c74`

## callees

- `0x180002b4c`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x180002c35`
- `ADVAPI32!UnregisterTraceGuids` at `0x180002c35`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180002bf9`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180002bf9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v3; // rbx
  const GUID **v4; // rdi
  const GUID *v5; // r8
  _QWORD *v6; // rbx
  TRACEHANDLE v7; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_18000E780 = 0;
      v3 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_DFDCOMMON;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18000E788 = 1;
      do
      {
        v5 = *v4;
        TraceGuidReg.Guid = v5;
        ++v4;
        TraceGuidReg.RegHandle = 0;
        v3[4] = (ULONG64)v5;
        RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
        v3 = (ULONG64 *)*v3;
      }
      while ( v3 );
      pDfdTSSqm = 0;
      g_RegHandle = 0;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v6 )
      {
        v7 = v6[1];
        if ( v7 )
        {
          UnregisterTraceGuids(v7);
          v6[1] = 0;
        }
        v6 = (_QWORD *)*v6;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002b4c  mov     [rsp+arg_0], rbx
0x180002b51  push    rdi
0x180002b52  sub     rsp, 50h
0x180002b56  test    edx, edx
0x180002b58  jz      loc_180002C17
0x180002b5e  cmp     edx, 1
0x180002b61  jnz     loc_180002C52
0x180002b67  lea     rax, WPP_ThisDir_CTLGUID_DFDCOMMON
0x180002b6e  mov     cs:qword_18000E780, 0
0x180002b79  lea     rbx, WPP_MAIN_CB
0x180002b80  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180002b87  mov     cs:WPP_GLOBAL_Control, rbx
0x180002b8e  lea     rdi, WPP_REGISTRATION_GUIDS
0x180002b95  mov     cs:WPP_MAIN_CB, 0
0x180002ba0  mov     cs:qword_18000E788, 1
0x180002bab  mov     r8, [rdi]; ControlGuid
0x180002bae  lea     rax, [rbx+8]
0x180002bb2  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180002bb7  lea     rcx, WppControlCallback; RequestAddress
0x180002bbe  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180002bc7  lea     rax, [rsp+58h+var_18]
0x180002bcc  mov     [rsp+58h+var_18.Guid], r8
0x180002bd1  lea     rdi, [rdi+8]
0x180002bd5  mov     [rsp+58h+var_18.RegHandle], 0
0x180002bde  mov     r9d, 1; GuidCount
0x180002be4  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180002bed  mov     rdx, rbx; RequestContext
0x180002bf0  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180002bf5  mov     [rbx+20h], r8
0x180002bf9  call    cs:__imp_RegisterTraceGuidsW
0x180002bff  mov     rbx, [rbx]
0x180002c02  test    rbx, rbx
0x180002c05  jnz     short loc_180002BAB
0x180002c07  mov     cs:?pDfdTSSqm@@3PEAVDfdTSSqm@@EA, rbx; DfdTSSqm * pDfdTSSqm
0x180002c0e  mov     cs:?g_RegHandle@@3_KA, rbx; unsigned __int64 g_RegHandle
0x180002c15  jmp     short loc_180002C52
0x180002c17  mov     rbx, cs:WPP_GLOBAL_Control
0x180002c1e  lea     rdi, WPP_GLOBAL_Control
0x180002c25  cmp     rbx, rdi
0x180002c28  jz      short loc_180002C52
0x180002c2a  jmp     short loc_180002C46
0x180002c2c  mov     rcx, [rbx+8]; RegistrationHandle
0x180002c30  test    rcx, rcx
0x180002c33  jz      short loc_180002C43
0x180002c35  call    cs:__imp_UnregisterTraceGuids
0x180002c3b  mov     qword ptr [rbx+8], 0
0x180002c43  mov     rbx, [rbx]
0x180002c46  test    rbx, rbx
0x180002c49  jnz     short loc_180002C2C
0x180002c4b  mov     cs:WPP_GLOBAL_Control, rdi
0x180002c52  mov     rbx, [rsp+58h+arg_0]
0x180002c57  mov     eax, 1
0x180002c5c  add     rsp, 50h
0x180002c60  pop     rdi
0x180002c61  retn
```
