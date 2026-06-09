# EtwSession_GetDroppedEventCount

- ea: `0x18001cde0`
- end: `0x18001cec6`
- name: `EtwSession_GetDroppedEventCount`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000ac44`
- `0x18001cde0`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001ce4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001ce4f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001ce10`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001ce10`

## string_xrefs

- `0x18001ce44`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_GetDroppedEventCount(__int64 a1, _DWORD *a2)
{
  ULONG v4; // eax
  ULONG v5; // esi
  HMODULE ModuleHandleA; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-20h] BYREF

  v4 = ControlTraceW(*(_QWORD *)(a1 + 40), 0, (PEVENT_TRACE_PROPERTIES)(a1 + 48), 0);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 4;
    *(_DWORD *)&EventDescriptor.Id = 8;
    EventDescriptor.Keyword = 1;
    Etw_Trace1_int(&EventDescriptor, v4);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2040, v5);
    LOBYTE(EventDescriptor.Keyword) = 1;
    MI_ReportErrorDetails_ForCustomError(8, (int)L"ETW Normalizer", 0, 0);
    return 1;
  }
  else
  {
    *a2 = *(_DWORD *)(a1 + 136);
    return 0;
  }
}

```

## disassembly

```asm
0x18001cde0  mov     [rsp-18h+arg_10], rbx
0x18001cde5  push    rbp
0x18001cde6  push    rsi
0x18001cde7  push    rdi
0x18001cde8  mov     rbp, rsp
0x18001cdeb  sub     rsp, 50h
0x18001cdef  mov     rax, cs:__security_cookie
0x18001cdf6  xor     rax, rsp
0x18001cdf9  mov     [rbp+var_10], rax
0x18001cdfd  mov     rdi, rdx
0x18001ce00  lea     r8, [rcx+30h]; Properties
0x18001ce04  mov     rbx, rcx
0x18001ce07  xor     edx, edx; InstanceName
0x18001ce09  mov     rcx, [rcx+28h]; TraceHandle
0x18001ce0d  xor     r9d, r9d; ControlCode
0x18001ce10  call    cs:__imp_ControlTraceW
0x18001ce16  mov     esi, eax
0x18001ce18  test    eax, eax
0x18001ce1a  jz      loc_18001CEA0
0x18001ce20  mov     edi, 8
0x18001ce25  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001ce2c  mov     edx, eax
0x18001ce2e  mov     dword ptr [rbp+EventDescriptor.Id], edi
0x18001ce31  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001ce35  lea     ebx, [rdi-7]
0x18001ce38  mov     [rbp+EventDescriptor.Keyword], rbx
0x18001ce3c  call    Etw_Trace1_int
0x18001ce41  xorps   xmm0, xmm0
0x18001ce44  lea     rcx, ModuleName; "mpunits.dll"
0x18001ce4b  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001ce4f  call    cs:__imp_GetModuleHandleA
0x18001ce55  mov     r8d, esi
0x18001ce58  mov     edx, 7F8h
0x18001ce5d  mov     rcx, rax
0x18001ce60  call    _Intlstr_FormatString_FormatMessage
0x18001ce65  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001ce69  lea     r9, [rbp+EventDescriptor]
0x18001ce6d  mov     byte ptr [rbp+EventDescriptor.Keyword], bl
0x18001ce70  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001ce77  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001ce7b  xor     r8d, r8d
0x18001ce7e  mov     [rsp+50h+var_28], 0; __int64
0x18001ce87  mov     ecx, edi; int
0x18001ce89  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001ce8e  mov     [rsp+50h+var_30], 0; __int64
0x18001ce97  call    MI_ReportErrorDetails_ForCustomError
0x18001ce9c  mov     eax, ebx
0x18001ce9e  jmp     short loc_18001CEAA
0x18001cea0  mov     eax, [rbx+88h]
0x18001cea6  mov     [rdi], eax
0x18001cea8  xor     eax, eax
0x18001ceaa  mov     rcx, [rbp+var_10]
0x18001ceae  xor     rcx, rsp; StackCookie
0x18001ceb1  call    __security_check_cookie
0x18001ceb6  mov     rbx, [rsp+50h+arg_10]
0x18001cebe  add     rsp, 50h
0x18001cec2  pop     rdi
0x18001cec3  pop     rsi
0x18001cec4  pop     rbp
0x18001cec5  retn
```
