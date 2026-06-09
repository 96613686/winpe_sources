# EtwSession_Init

- ea: `0x18001ced0`
- end: `0x18001d06e`
- name: `EtwSession_Init`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180019770`

## callees

- `0x180006e64`
- `0x180006fa4`
- `0x180007c80`
- `0x18000abb8`
- `0x18000ac44`
- `0x18001ced0`
- `0x18001d074`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cfc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cfc2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cf7b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cf7b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001cf8b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001cf8b`

## string_xrefs

- `0x18001cfb7`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_Init(
        __int64 a1,
        ULONGLONG a2,
        void (__stdcall *a3)(PEVENT_TRACE pEvent),
        __int64 a4,
        void *a5)
{
  struct _EVENT_TRACE_PROPERTIES *v5; // rbx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r8
  __int64 result; // rax
  ULONG started; // eax
  ULONG v14; // esi
  HMODULE ModuleHandleA; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-20h] BYREF

  v5 = (struct _EVENT_TRACE_PROPERTIES *)(a1 + 48);
  memset_0((void *)(a1 + 48), 0, 0x78u);
  v10 = Wcslcpy(a1 + 368, a2, 100);
  if ( v10 >= v11 )
    return (unsigned int)(v11 - 73);
  v5->Wnode.BufferSize = 520;
  v5->Wnode.Flags = 0x20000;
  v5->Wnode.ClientContext = 1;
  v5->BufferSize = 256;
  v5->LogFileMode = 384;
  v5->FlushTimer = 1;
  v5->LoggerNameOffset = 120;
  ControlTraceW(0, (LPCWSTR)(a1 + 368), v5, 1u);
  started = StartTraceW((PTRACEHANDLE)(a1 + 40), (LPCWSTR)(a1 + 368), v5);
  v14 = started;
  if ( started )
  {
    *(_DWORD *)&EventDescriptor.Id = 4;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace1_int(&EventDescriptor, started);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2038, v14);
    LOBYTE(EventDescriptor.Keyword) = 1;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"ETW Normalizer", 0, 0);
    return 1;
  }
  else
  {
    result = EtwSession_InitCommon(a1, 0, a3, a4, a5);
    if ( !(_DWORD)result )
    {
      *(_DWORD *)&EventDescriptor.Id = 10003;
      EventDescriptor.Keyword = 1;
      *(_DWORD *)&EventDescriptor.Level = 4;
      Etw_Trace1_LPCWSTR(&EventDescriptor, a2);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ced0  mov     [rsp-38h+arg_18], rbx
0x18001ced5  push    rbp
0x18001ced6  push    rsi
0x18001ced7  push    rdi
0x18001ced8  push    r12
0x18001ceda  push    r13
0x18001cedc  push    r14
0x18001cede  push    r15
0x18001cee0  mov     rbp, rsp
0x18001cee3  sub     rsp, 50h
0x18001cee7  mov     rax, cs:__security_cookie
0x18001ceee  xor     rax, rsp
0x18001cef1  mov     [rbp+var_10], rax
0x18001cef5  mov     r13, [rbp+arg_20]
0x18001cef9  lea     rbx, [rcx+30h]
0x18001cefd  mov     r14, rdx
0x18001cf00  mov     r12, r8
0x18001cf03  xor     edx, edx; Val
0x18001cf05  mov     rdi, rcx
0x18001cf08  mov     rcx, rbx; void *
0x18001cf0b  mov     r15, r9
0x18001cf0e  lea     r8d, [rdx+78h]; Size
0x18001cf12  call    memset_0
0x18001cf17  lea     rsi, [rdi+170h]
0x18001cf1e  mov     r8d, 64h ; 'd'
0x18001cf24  mov     rcx, rsi
0x18001cf27  mov     rdx, r14
0x18001cf2a  call    Wcslcpy
0x18001cf2f  cmp     rax, r8
0x18001cf32  jb      short loc_18001CF3D
0x18001cf34  lea     eax, [r8-49h]
0x18001cf38  jmp     loc_18001D04A
0x18001cf3d  mov     r9d, 1; ControlCode
0x18001cf43  mov     dword ptr [rbx], 208h
0x18001cf49  mov     r8, rbx; Properties
0x18001cf4c  mov     dword ptr [rbx+2Ch], 20000h
0x18001cf53  mov     rdx, rsi; InstanceName
0x18001cf56  mov     dword ptr [rbx+28h], 1
0x18001cf5d  xor     ecx, ecx; TraceHandle
0x18001cf5f  mov     dword ptr [rbx+30h], 100h
0x18001cf66  mov     dword ptr [rbx+40h], 180h
0x18001cf6d  mov     dword ptr [rbx+44h], 1
0x18001cf74  mov     dword ptr [rbx+74h], 78h ; 'x'
0x18001cf7b  call    cs:__imp_ControlTraceW
0x18001cf81  lea     rcx, [rdi+28h]; TraceHandle
0x18001cf85  mov     r8, rbx; Properties
0x18001cf88  mov     rdx, rsi; InstanceName
0x18001cf8b  call    cs:__imp_StartTraceW
0x18001cf91  mov     esi, eax
0x18001cf93  test    eax, eax
0x18001cf95  jz      short loc_18001D00E
0x18001cf97  mov     ebx, 4
0x18001cf9c  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001cfa0  mov     edx, eax
0x18001cfa2  mov     dword ptr [rbp+EventDescriptor.Id], ebx
0x18001cfa5  mov     dword ptr [rbp+EventDescriptor.Level], ebx
0x18001cfa8  lea     edi, [rbx-3]
0x18001cfab  mov     [rbp+EventDescriptor.Keyword], rdi
0x18001cfaf  call    Etw_Trace1_int
0x18001cfb4  xorps   xmm0, xmm0
0x18001cfb7  lea     rcx, ModuleName; "mpunits.dll"
0x18001cfbe  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001cfc2  call    cs:__imp_GetModuleHandleA
0x18001cfc8  mov     r8d, esi
0x18001cfcb  mov     edx, 7F6h
0x18001cfd0  mov     rcx, rax
0x18001cfd3  call    _Intlstr_FormatString_FormatMessage
0x18001cfd8  xor     ecx, ecx
0x18001cfda  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001cfde  mov     [rsp+50h+var_28], rcx; __int64
0x18001cfe3  lea     r9, [rbp+EventDescriptor]
0x18001cfe7  mov     byte ptr [rbp+EventDescriptor.Keyword], dil
0x18001cfeb  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001cff2  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001cff6  mov     r8d, edi
0x18001cff9  mov     [rsp+50h+var_30], rcx; __int64
0x18001cffe  mov     ecx, ebx; int
0x18001d000  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001d005  call    MI_ReportErrorDetails_ForCustomError
0x18001d00a  mov     eax, edi
0x18001d00c  jmp     short loc_18001D04A
0x18001d00e  mov     r9, r15
0x18001d011  mov     [rsp+50h+var_30], r13
0x18001d016  mov     r8, r12
0x18001d019  xor     edx, edx
0x18001d01b  mov     rcx, rdi
0x18001d01e  call    EtwSession_InitCommon
0x18001d023  test    eax, eax
0x18001d025  jnz     short loc_18001D04A
0x18001d027  lea     edi, [rax+1]
0x18001d02a  mov     dword ptr [rbp+EventDescriptor.Id], 2713h
0x18001d031  mov     rdx, r14
0x18001d034  mov     [rbp+EventDescriptor.Keyword], rdi
0x18001d038  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001d03c  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001d043  call    Etw_Trace1_LPCWSTR
0x18001d048  xor     eax, eax
0x18001d04a  mov     rcx, [rbp+var_10]
0x18001d04e  xor     rcx, rsp; StackCookie
0x18001d051  call    __security_check_cookie
0x18001d056  mov     rbx, [rsp+50h+arg_18]
0x18001d05e  add     rsp, 50h
0x18001d062  pop     r15
0x18001d064  pop     r14
0x18001d066  pop     r13
0x18001d068  pop     r12
0x18001d06a  pop     rdi
0x18001d06b  pop     rsi
0x18001d06c  pop     rbp
0x18001d06d  retn
```
