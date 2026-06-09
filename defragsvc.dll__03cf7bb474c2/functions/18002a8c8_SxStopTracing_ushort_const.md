# SxStopTracing(ushort const *)

- ea: `0x18002a8c8`
- end: `0x18002a9d0`
- name: `?SxStopTracing@@YAJPEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a86c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18002a8c8`
- `0x180038c3c`
- `0x180066dfc`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002a974`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002a98c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002a974`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18002a98c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a9b1`

## pseudocode

```c
__int64 __fastcall SxStopTracing(struct _EVENT_TRACE_PROPERTIES *a1)
{
  int v1; // eax
  struct _EVENT_TRACE_PROPERTIES *v2; // rbx
  bool v3; // sf
  __int16 v4; // ax
  signed int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+70h] [rbp+10h] BYREF

  Properties = a1;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxStopTracing", 685, 1);
  Properties = 0;
  v9 = 689;
  v8 = 0;
  v1 = SxAllocateEventTraceProp(&Properties);
  v2 = Properties;
  v3 = v1 < 0;
  v8 = v1;
  v4 = 691;
  if ( v3 )
    goto LABEL_5;
  v9 = 691;
  ControlTraceW(0, L"BuiltInDefragTracing", Properties, 3u);
  v5 = ControlTraceW(0, L"BuiltInDefragTracing", v2, 1u);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v8 = v5;
  v3 = v5 < 0;
  v4 = 695;
  if ( v3 )
LABEL_5:
    v10 = v4;
  else
    v9 = 695;
  CoTaskMemFree(v2);
  v6 = v8;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v6;
}

```

## disassembly

```asm
0x18002a8c8  mov     [rsp-8+arg_8], rbx
0x18002a8cd  mov     [rsp-8+Properties], rcx
0x18002a8d2  push    rbp
0x18002a8d3  mov     rbp, rsp
0x18002a8d6  sub     rsp, 60h
0x18002a8da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8e1  lea     rax, WPP_GLOBAL_Control
0x18002a8e8  cmp     rcx, rax
0x18002a8eb  jz      short loc_18002A90B
0x18002a8ed  test    dword ptr [rcx+1Ch], 20000000h
0x18002a8f4  jz      short loc_18002A90B
0x18002a8f6  mov     rcx, [rcx+10h]
0x18002a8fa  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x18002a901  mov     edx, 19h
0x18002a906  call    WPP_SF_
0x18002a90b  mov     r9d, 1; unsigned __int16
0x18002a911  lea     rdx, aSxstoptracing; "SxStopTracing"
0x18002a918  mov     r8d, 2ADh; unsigned __int16
0x18002a91e  lea     rcx, [rbp+var_40]; this
0x18002a922  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002a927  mov     eax, 2B1h
0x18002a92c  mov     [rbp+Properties], 0
0x18002a934  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x18002a938  mov     [rbp+var_3C], ax
0x18002a93c  mov     [rbp+var_40], 0
0x18002a943  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x18002a948  mov     rbx, [rbp+Properties]
0x18002a94c  test    eax, eax
0x18002a94e  mov     [rbp+var_40], eax
0x18002a951  mov     eax, 2B3h
0x18002a956  jns     short loc_18002A95E
0x18002a958  mov     [rbp+var_3A], ax
0x18002a95c  jmp     short loc_18002A9AE
0x18002a95e  mov     r9d, 3; ControlCode
0x18002a964  mov     [rbp+var_3C], ax
0x18002a968  mov     r8, rbx; Properties
0x18002a96b  lea     rdx, InstanceName; "BuiltInDefragTracing"
0x18002a972  xor     ecx, ecx; TraceHandle
0x18002a974  call    cs:__imp_ControlTraceW
0x18002a97a  mov     r9d, 1; ControlCode
0x18002a980  lea     rdx, InstanceName; "BuiltInDefragTracing"
0x18002a987  mov     r8, rbx; Properties
0x18002a98a  xor     ecx, ecx; TraceHandle
0x18002a98c  call    cs:__imp_ControlTraceW
0x18002a992  test    eax, eax
0x18002a994  jle     short loc_18002A99E
0x18002a996  movzx   eax, ax
0x18002a999  or      eax, 80070000h
0x18002a99e  mov     [rbp+var_40], eax
0x18002a9a1  test    eax, eax
0x18002a9a3  mov     eax, 2B7h
0x18002a9a8  js      short loc_18002A958
0x18002a9aa  mov     [rbp+var_3C], ax
0x18002a9ae  mov     rcx, rbx; pv
0x18002a9b1  call    cs:__imp_CoTaskMemFree
0x18002a9b7  mov     ebx, [rbp+var_40]
0x18002a9ba  lea     rcx, [rbp+var_40]; this
0x18002a9be  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a9c3  mov     eax, ebx
0x18002a9c5  mov     rbx, [rsp+60h+arg_8]
0x18002a9ca  add     rsp, 60h
0x18002a9ce  pop     rbp
0x18002a9cf  retn
```
