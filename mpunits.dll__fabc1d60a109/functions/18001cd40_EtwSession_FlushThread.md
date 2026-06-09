# EtwSession_FlushThread

- ea: `0x18001cd40`
- end: `0x18001cdd1`
- name: `EtwSession_FlushThread`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000b258`
- `0x18001cd40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cd76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cd76`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cd54`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001cd54`

## string_xrefs

- `0x18001cd6a`: `mpunits.dll`

## pseudocode

```c
ULONG __fastcall EtwSession_FlushThread(__int64 a1)
{
  ULONG result; // eax
  ULONG v2; // ebx
  HMODULE ModuleHandleA; // rax

  result = ControlTraceW(*(_QWORD *)(a1 + 40), 0, (PEVENT_TRACE_PROPERTIES)(a1 + 48), 3u);
  v2 = result;
  if ( result )
  {
    trace_ETW_FlushFail(result);
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2041, v2);
    return MI_ReportErrorDetails_ForCustomError(9, (int)L"ETW Normalizer", 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18001cd40  push    rbx
0x18001cd42  sub     rsp, 40h
0x18001cd46  xor     edx, edx; InstanceName
0x18001cd48  lea     r8, [rcx+30h]; Properties
0x18001cd4c  mov     rcx, [rcx+28h]; TraceHandle
0x18001cd50  lea     r9d, [rdx+3]; ControlCode
0x18001cd54  call    cs:__imp_ControlTraceW
0x18001cd5a  mov     ebx, eax
0x18001cd5c  test    eax, eax
0x18001cd5e  jz      short loc_18001CDCB
0x18001cd60  mov     ecx, eax
0x18001cd62  call    trace_ETW_FlushFail
0x18001cd67  xorps   xmm0, xmm0
0x18001cd6a  lea     rcx, ModuleName; "mpunits.dll"
0x18001cd71  movups  [rsp+48h+var_18], xmm0
0x18001cd76  call    cs:__imp_GetModuleHandleA
0x18001cd7c  mov     r8d, ebx
0x18001cd7f  mov     edx, 7F9h
0x18001cd84  mov     rcx, rax
0x18001cd87  call    _Intlstr_FormatString_FormatMessage
0x18001cd8c  mov     qword ptr [rsp+48h+var_18], rax
0x18001cd91  lea     r9, [rsp+48h+var_18]
0x18001cd96  mov     byte ptr [rsp+48h+var_18+8], 1
0x18001cd9b  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001cda2  movaps  xmm0, [rsp+48h+var_18]
0x18001cda7  xor     r8d, r8d
0x18001cdaa  mov     [rsp+48h+var_20], 0; __int64
0x18001cdb3  movdqa  [rsp+48h+var_18], xmm0
0x18001cdb9  mov     [rsp+48h+var_28], 0; __int64
0x18001cdc2  lea     ecx, [r8+9]; int
0x18001cdc6  call    MI_ReportErrorDetails_ForCustomError
0x18001cdcb  add     rsp, 40h
0x18001cdcf  pop     rbx
0x18001cdd0  retn
```
