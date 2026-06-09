# EtwSession_Flush

- ea: `0x18001cb40`
- end: `0x18001cbda`
- name: `EtwSession_Flush`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800194c0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000b258`
- `0x18001cb40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cb76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cb76`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cb54`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cb54`

## string_xrefs

- `0x18001cb6a`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_Flush(__int64 a1)
{
  ULONG v1; // eax
  ULONG v2; // ebx
  HMODULE ModuleHandleA; // rax

  v1 = ControlTraceW(*(_QWORD *)(a1 + 40), 0, (PEVENT_TRACE_PROPERTIES)(a1 + 48), 3u);
  v2 = v1;
  if ( !v1 )
    return 0;
  trace_ETW_FlushFail(v1);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2041, v2);
  MI_ReportErrorDetails_ForCustomError(9, (int)L"ETW Normalizer", 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18001cb40  push    rbx
0x18001cb42  sub     rsp, 40h
0x18001cb46  xor     edx, edx; InstanceName
0x18001cb48  lea     r8, [rcx+30h]; Properties
0x18001cb4c  mov     rcx, [rcx+28h]; TraceHandle
0x18001cb50  lea     r9d, [rdx+3]; ControlCode
0x18001cb54  call    cs:__imp_ControlTraceW
0x18001cb5a  mov     ebx, eax
0x18001cb5c  test    eax, eax
0x18001cb5e  jz      short loc_18001CBD2
0x18001cb60  mov     ecx, eax
0x18001cb62  call    trace_ETW_FlushFail
0x18001cb67  xorps   xmm0, xmm0
0x18001cb6a  lea     rcx, ModuleName; "mpunits.dll"
0x18001cb71  movups  [rsp+48h+var_18], xmm0
0x18001cb76  call    cs:__imp_GetModuleHandleA
0x18001cb7c  mov     r8d, ebx
0x18001cb7f  mov     edx, 7F9h
0x18001cb84  mov     rcx, rax
0x18001cb87  call    _Intlstr_FormatString_FormatMessage
0x18001cb8c  mov     qword ptr [rsp+48h+var_18], rax
0x18001cb91  lea     r9, [rsp+48h+var_18]
0x18001cb96  mov     byte ptr [rsp+48h+var_18+8], 1
0x18001cb9b  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001cba2  movaps  xmm0, [rsp+48h+var_18]
0x18001cba7  xor     r8d, r8d
0x18001cbaa  mov     [rsp+48h+var_20], 0; __int64
0x18001cbb3  movdqa  [rsp+48h+var_18], xmm0
0x18001cbb9  mov     [rsp+48h+var_28], 0; __int64
0x18001cbc2  lea     ecx, [r8+9]; int
0x18001cbc6  call    MI_ReportErrorDetails_ForCustomError
0x18001cbcb  mov     eax, 1
0x18001cbd0  jmp     short loc_18001CBD4
0x18001cbd2  xor     eax, eax
0x18001cbd4  add     rsp, 40h
0x18001cbd8  pop     rbx
0x18001cbd9  retn
```
