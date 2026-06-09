# DmDiagnosticsCollector::CollectEventsFromSession(ushort const *,ushort const *,_GUID)

- ea: `0x180007ce4`
- end: `0x180007e51`
- name: `?CollectEventsFromSession@DmDiagnosticsCollector@@SAJPEBG0U_GUID@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, const unsigned __int16 *, struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800080f8`

## callees

- `0x1800017e0`
- `0x1800029a9`
- `0x180005a14`
- `0x180005a38`
- `0x1800069ec`
- `0x180007ce4`
- `0x180007e58`
- `0x180008000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e2c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180007d6f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180007d6f`

## pseudocode

```c
__int64 __fastcall DmDiagnosticsCollector::CollectEventsFromSession(
        LPCWSTR InstanceName,
        const unsigned __int16 *a2,
        struct _GUID *Buf1)
{
  int SessionProperty; // eax
  unsigned int v7; // ebx
  ULONG v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  PEVENT_TRACE_PROPERTIES Properties[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v13; // [rsp+30h] [rbp-D0h]
  struct _GUID v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[1032]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+898h] [rbp+798h]

  Properties[0] = 0;
  SessionProperty = DmDiagnosticsCollector::CreateSessionProperty(a2, Properties);
  v7 = SessionProperty;
  if ( SessionProperty >= 0 )
  {
    Properties[1] = (PEVENT_TRACE_PROPERTIES)Properties;
    v13 = 1;
    v8 = ControlTraceW(0, InstanceName, Properties[0], 3u);
    if ( v8 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA4,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
             (const char *)v8,
             (unsigned int)Properties[0]);
    }
    else
    {
      v9 = StringCchCopyW(
             v15,
             0x401u,
             (const unsigned __int16 *)((char *)Properties[0] + Properties[0]->LogFileNameOffset));
      v7 = v9;
      if ( v9 >= 0 )
      {
        if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
          *Buf1 = (struct _GUID)xmmword_180029DE0;
        v14 = *Buf1;
        v9 = DmDiagnosticsCollector::CreateLogFilteredByProviderId(&v14, v15, a2);
        v7 = v9;
        if ( v9 >= 0 )
        {
          v7 = 0;
          goto LABEL_13;
        }
        v10 = 175;
      }
      else
      {
        v10 = 168;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
        (const char *)(unsigned int)v9,
        (int)Properties[0]);
    }
LABEL_13:
    CoTaskMemFree(Properties[0]);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
    (const char *)(unsigned int)SessionProperty,
    (int)Properties[0]);
  return v7;
}

```

## disassembly

```asm
0x180007ce4  push    rbp
0x180007ce6  push    rbx
0x180007ce7  push    rsi
0x180007ce8  push    rdi
0x180007ce9  push    r14
0x180007ceb  lea     rbp, [rsp-770h]
0x180007cf3  sub     rsp, 870h
0x180007cfa  mov     rax, cs:__security_cookie
0x180007d01  xor     rax, rsp
0x180007d04  mov     [rbp+790h+var_30], rax
0x180007d0b  mov     rdi, r8
0x180007d0e  mov     rsi, rdx
0x180007d11  mov     r14, rcx
0x180007d14  mov     [rsp+890h+Properties], 0; int
0x180007d1d  lea     rdx, [rsp+890h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180007d22  mov     rcx, rsi; unsigned __int16 *
0x180007d25  call    ?CreateSessionProperty@DmDiagnosticsCollector@@SAJPEBGAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; DmDiagnosticsCollector::CreateSessionProperty(ushort const *,_EVENT_TRACE_PROPERTIES * &)
0x180007d2a  mov     ebx, eax
0x180007d2c  test    eax, eax
0x180007d2e  jns     short loc_180007D50
0x180007d30  mov     rcx, [rbp+798h]; this
0x180007d37  mov     r9d, eax; char *
0x180007d3a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180007d41  mov     edx, 9Dh; void *
0x180007d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d4b  jmp     loc_180007E32
0x180007d50  lea     rax, [rsp+890h+Properties]
0x180007d55  mov     [rsp+890h+var_868], rax
0x180007d5a  mov     [rsp+890h+var_860], 1
0x180007d5f  mov     r9d, 3; ControlCode
0x180007d65  mov     r8, [rsp+890h+Properties]; Properties
0x180007d6a  mov     rdx, r14; InstanceName
0x180007d6d  xor     ecx, ecx; TraceHandle
0x180007d6f  call    cs:__imp_ControlTraceW
0x180007d75  test    eax, eax
0x180007d77  jz      short loc_180007D9B
0x180007d79  mov     rcx, [rbp+798h]; this
0x180007d80  mov     r9d, eax; char *
0x180007d83  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180007d8a  mov     edx, 0A4h; void *
0x180007d8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007d94  mov     ebx, eax
0x180007d96  jmp     loc_180007E27
0x180007d9b  mov     rax, [rsp+890h+Properties]
0x180007da0  mov     r8d, [rax+70h]
0x180007da4  add     r8, rax; unsigned __int16 *
0x180007da7  mov     edx, 401h; unsigned __int64
0x180007dac  lea     rcx, [rsp+890h+var_840]; unsigned __int16 *
0x180007db1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007db6  mov     ebx, eax
0x180007db8  test    eax, eax
0x180007dba  jns     short loc_180007DD9
0x180007dbc  mov     edx, 0A8h; void *
0x180007dc1  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180007dc8  mov     r9d, eax; char *
0x180007dcb  mov     rcx, [rbp+798h]; this
0x180007dd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dd7  jmp     short loc_180007E27
0x180007dd9  mov     r8d, 10h; Size
0x180007ddf  lea     rdx, GUID_NULL; Buf2
0x180007de6  mov     rcx, rdi; Buf1
0x180007de9  call    memcmp_0
0x180007dee  test    eax, eax
0x180007df0  jnz     short loc_180007DFD
0x180007df2  movups  xmm0, cs:xmmword_180029DE0
0x180007df9  movdqu  xmmword ptr [rdi], xmm0
0x180007dfd  movaps  xmm0, xmmword ptr [rdi]
0x180007e00  movdqa  xmmword ptr [rsp+890h+var_850.Data1], xmm0
0x180007e06  mov     r8, rsi; unsigned __int16 *
0x180007e09  lea     rdx, [rsp+890h+var_840]; unsigned __int16 *
0x180007e0e  lea     rcx, [rsp+890h+var_850]; struct _GUID
0x180007e13  call    ?CreateLogFilteredByProviderId@DmDiagnosticsCollector@@SAJU_GUID@@PEBG1@Z; DmDiagnosticsCollector::CreateLogFilteredByProviderId(_GUID,ushort const *,ushort const *)
0x180007e18  mov     ebx, eax
0x180007e1a  test    eax, eax
0x180007e1c  jns     short loc_180007E25
0x180007e1e  mov     edx, 0AFh
0x180007e23  jmp     short loc_180007DC1
0x180007e25  xor     ebx, ebx
0x180007e27  mov     rcx, [rsp+890h+Properties]; pv
0x180007e2c  call    cs:__imp_CoTaskMemFree
0x180007e32  mov     eax, ebx
0x180007e34  mov     rcx, [rbp+790h+var_30]
0x180007e3b  xor     rcx, rsp; StackCookie
0x180007e3e  call    __security_check_cookie
0x180007e43  add     rsp, 870h
0x180007e4a  pop     r14
0x180007e4c  pop     rdi
0x180007e4d  pop     rsi
0x180007e4e  pop     rbx
0x180007e4f  pop     rbp
0x180007e50  retn
```
