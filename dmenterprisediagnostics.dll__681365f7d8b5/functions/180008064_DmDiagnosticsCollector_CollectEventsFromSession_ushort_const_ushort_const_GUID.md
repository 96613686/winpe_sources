# DmDiagnosticsCollector::CollectEventsFromSession(ushort const *,ushort const *,_GUID)

- ea: `0x180008064`
- end: `0x1800081de`
- name: `?CollectEventsFromSession@DmDiagnosticsCollector@@SAJPEBG0U_GUID@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(LPCWSTR InstanceName, const unsigned __int16 *, struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x180001800`
- `0x1800029c9`
- `0x180005c14`
- `0x180005c3c`
- `0x180006c6c`
- `0x180008064`
- `0x1800081e4`
- `0x1800083a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081b2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800080ef`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800080ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
          *Buf1 = (struct _GUID)xmmword_18002ADE0;
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
0x180008064  push    rbp
0x180008066  push    rbx
0x180008067  push    rsi
0x180008068  push    rdi
0x180008069  push    r14
0x18000806b  lea     rbp, [rsp-770h]
0x180008073  sub     rsp, 870h
0x18000807a  mov     rax, cs:__security_cookie
0x180008081  xor     rax, rsp
0x180008084  mov     [rbp+790h+var_30], rax
0x18000808b  mov     rdi, r8
0x18000808e  mov     rsi, rdx
0x180008091  mov     r14, rcx
0x180008094  mov     [rsp+890h+Properties], 0; int
0x18000809d  lea     rdx, [rsp+890h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800080a2  mov     rcx, rsi; unsigned __int16 *
0x1800080a5  call    ?CreateSessionProperty@DmDiagnosticsCollector@@SAJPEBGAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; DmDiagnosticsCollector::CreateSessionProperty(ushort const *,_EVENT_TRACE_PROPERTIES * &)
0x1800080aa  mov     ebx, eax
0x1800080ac  test    eax, eax
0x1800080ae  jns     short loc_1800080D0
0x1800080b0  mov     rcx, [rbp+798h]; this
0x1800080b7  mov     r9d, eax; char *
0x1800080ba  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800080c1  mov     edx, 9Dh; void *
0x1800080c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080cb  jmp     loc_1800081BE
0x1800080d0  lea     rax, [rsp+890h+Properties]
0x1800080d5  mov     [rsp+890h+var_868], rax
0x1800080da  mov     [rsp+890h+var_860], 1
0x1800080df  mov     r9d, 3; ControlCode
0x1800080e5  mov     r8, [rsp+890h+Properties]; Properties
0x1800080ea  mov     rdx, r14; InstanceName
0x1800080ed  xor     ecx, ecx; TraceHandle
0x1800080ef  call    cs:__imp_ControlTraceW
0x1800080f6  nop     dword ptr [rax+rax+00h]
0x1800080fb  test    eax, eax
0x1800080fd  jz      short loc_180008121
0x1800080ff  mov     rcx, [rbp+798h]; this
0x180008106  mov     r9d, eax; char *
0x180008109  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180008110  mov     edx, 0A4h; void *
0x180008115  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000811a  mov     ebx, eax
0x18000811c  jmp     loc_1800081AD
0x180008121  mov     rax, [rsp+890h+Properties]
0x180008126  mov     r8d, [rax+70h]
0x18000812a  add     r8, rax; unsigned __int16 *
0x18000812d  mov     edx, 401h; unsigned __int64
0x180008132  lea     rcx, [rsp+890h+var_840]; unsigned __int16 *
0x180008137  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000813c  mov     ebx, eax
0x18000813e  test    eax, eax
0x180008140  jns     short loc_18000815F
0x180008142  mov     edx, 0A8h; void *
0x180008147  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000814e  mov     r9d, eax; char *
0x180008151  mov     rcx, [rbp+798h]; this
0x180008158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000815d  jmp     short loc_1800081AD
0x18000815f  mov     r8d, 10h; Size
0x180008165  lea     rdx, GUID_NULL; Buf2
0x18000816c  mov     rcx, rdi; Buf1
0x18000816f  call    memcmp_0
0x180008174  test    eax, eax
0x180008176  jnz     short loc_180008183
0x180008178  movups  xmm0, cs:xmmword_18002ADE0
0x18000817f  movdqu  xmmword ptr [rdi], xmm0
0x180008183  movaps  xmm0, xmmword ptr [rdi]
0x180008186  movdqa  xmmword ptr [rsp+890h+var_850.Data1], xmm0
0x18000818c  mov     r8, rsi; unsigned __int16 *
0x18000818f  lea     rdx, [rsp+890h+var_840]; unsigned __int16 *
0x180008194  lea     rcx, [rsp+890h+var_850]; struct _GUID
0x180008199  call    ?CreateLogFilteredByProviderId@DmDiagnosticsCollector@@SAJU_GUID@@PEBG1@Z; DmDiagnosticsCollector::CreateLogFilteredByProviderId(_GUID,ushort const *,ushort const *)
0x18000819e  mov     ebx, eax
0x1800081a0  test    eax, eax
0x1800081a2  jns     short loc_1800081AB
0x1800081a4  mov     edx, 0AFh
0x1800081a9  jmp     short loc_180008147
0x1800081ab  xor     ebx, ebx
0x1800081ad  mov     rcx, [rsp+890h+Properties]; pv
0x1800081b2  call    cs:__imp_CoTaskMemFree
0x1800081b9  nop     dword ptr [rax+rax+00h]
0x1800081be  mov     eax, ebx
0x1800081c0  mov     rcx, [rbp+790h+var_30]
0x1800081c7  xor     rcx, rsp; StackCookie
0x1800081ca  call    __security_check_cookie
0x1800081cf  add     rsp, 870h
0x1800081d6  pop     r14
0x1800081d8  pop     rdi
0x1800081d9  pop     rsi
0x1800081da  pop     rbx
0x1800081db  pop     rbp
0x1800081dc  retn
```
