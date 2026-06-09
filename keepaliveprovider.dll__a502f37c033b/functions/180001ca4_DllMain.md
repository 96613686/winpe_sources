# DllMain

- ea: `0x180001ca4`
- end: `0x180001e19`
- name: `DllMain`
- size: `373`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001ca4`
- `0x180001e20`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180001dec`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180001dec`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180001d57`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180001d57`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001cbf`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180001cbf`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v3; // rbx
  const GUID **v4; // rdi
  const GUID *v5; // r8
  _UNKNOWN **v6; // rbx
  TRACEHANDLE v7; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_180007170 = 0;
      v3 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_KAProvider;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_180007178 = 1;
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5c6b75a707523eac674c9f4bda73fb2f_Traceguids);
      }
    }
  }
  else
  {
    v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5c6b75a707523eac674c9f4bda73fb2f_Traceguids);
        v6 = (_UNKNOWN **)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control )
      {
        while ( v6 )
        {
          v7 = (TRACEHANDLE)v6[1];
          if ( v7 )
          {
            UnregisterTraceGuids(v7);
            v6[1] = 0;
          }
          v6 = (_UNKNOWN **)*v6;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001ca4  mov     [rsp+arg_0], rbx
0x180001ca9  push    rdi
0x180001caa  sub     rsp, 50h
0x180001cae  test    edx, edx
0x180001cb0  jz      loc_180001DA1
0x180001cb6  cmp     edx, 1
0x180001cb9  jnz     loc_180001E09
0x180001cbf  call    cs:__imp_DisableThreadLibraryCalls
0x180001cc5  lea     rax, WPP_ThisDir_CTLGUID_KAProvider
0x180001ccc  mov     cs:qword_180007170, 0
0x180001cd7  lea     rbx, WPP_MAIN_CB
0x180001cde  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180001ce5  mov     cs:WPP_GLOBAL_Control, rbx
0x180001cec  lea     rdi, WPP_REGISTRATION_GUIDS
0x180001cf3  mov     cs:WPP_MAIN_CB, 0
0x180001cfe  mov     cs:qword_180007178, 1
0x180001d09  mov     r8, [rdi]; ControlGuid
0x180001d0c  lea     rax, [rbx+8]
0x180001d10  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180001d15  lea     rcx, WppControlCallback; RequestAddress
0x180001d1c  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180001d25  lea     rax, [rsp+58h+var_18]
0x180001d2a  mov     [rsp+58h+var_18.Guid], r8
0x180001d2f  lea     rdi, [rdi+8]
0x180001d33  mov     [rsp+58h+var_18.RegHandle], 0
0x180001d3c  mov     r9d, 1; GuidCount
0x180001d42  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180001d4b  mov     rdx, rbx; RequestContext
0x180001d4e  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180001d53  mov     [rbx+20h], r8
0x180001d57  call    cs:__imp_RegisterTraceGuidsW
0x180001d5d  mov     rbx, [rbx]
0x180001d60  test    rbx, rbx
0x180001d63  jnz     short loc_180001D09
0x180001d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d6c  lea     rdi, WPP_GLOBAL_Control
0x180001d73  cmp     rcx, rdi
0x180001d76  jz      loc_180001E09
0x180001d7c  test    byte ptr [rcx+1Ch], 1
0x180001d80  jz      loc_180001E09
0x180001d86  cmp     byte ptr [rcx+19h], 5
0x180001d8a  jb      short loc_180001E09
0x180001d8c  mov     rcx, [rcx+10h]
0x180001d90  lea     edx, [rbx+0Ah]
0x180001d93  lea     r8, WPP_5c6b75a707523eac674c9f4bda73fb2f_Traceguids
0x180001d9a  call    WPP_SF_
0x180001d9f  jmp     short loc_180001E09
0x180001da1  mov     rbx, cs:WPP_GLOBAL_Control
0x180001da8  lea     rdi, WPP_GLOBAL_Control
0x180001daf  cmp     rbx, rdi
0x180001db2  jz      short loc_180001E09
0x180001db4  test    byte ptr [rbx+1Ch], 1
0x180001db8  jz      short loc_180001DDC
0x180001dba  cmp     byte ptr [rbx+19h], 5
0x180001dbe  jb      short loc_180001DDC
0x180001dc0  mov     rcx, [rbx+10h]
0x180001dc4  lea     r8, WPP_5c6b75a707523eac674c9f4bda73fb2f_Traceguids
0x180001dcb  mov     edx, 0Bh
0x180001dd0  call    WPP_SF_
0x180001dd5  mov     rbx, cs:WPP_GLOBAL_Control
0x180001ddc  cmp     rbx, rdi
0x180001ddf  jz      short loc_180001E09
0x180001de1  jmp     short loc_180001DFD
0x180001de3  mov     rcx, [rbx+8]; RegistrationHandle
0x180001de7  test    rcx, rcx
0x180001dea  jz      short loc_180001DFA
0x180001dec  call    cs:__imp_UnregisterTraceGuids
0x180001df2  mov     qword ptr [rbx+8], 0
0x180001dfa  mov     rbx, [rbx]
0x180001dfd  test    rbx, rbx
0x180001e00  jnz     short loc_180001DE3
0x180001e02  mov     cs:WPP_GLOBAL_Control, rdi
0x180001e09  mov     rbx, [rsp+58h+arg_0]
0x180001e0e  mov     eax, 1
0x180001e13  add     rsp, 50h
0x180001e17  pop     rdi
0x180001e18  retn
```
