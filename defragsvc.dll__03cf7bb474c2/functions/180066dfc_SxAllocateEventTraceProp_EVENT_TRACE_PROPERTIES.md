# SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)

- ea: `0x180066dfc`
- end: `0x180066f02`
- name: `?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a8c8`
- `0x1800677b4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180038c3c`
- `0x180066dfc`
- `0x180067b0a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ee1`

## pseudocode

```c
__int64 __fastcall SxAllocateEventTraceProp(struct _EVENT_TRACE_PROPERTIES **a1)
{
  __int16 v2; // ax
  struct _EVENT_TRACE_PROPERTIES *v3; // rbx
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-48h] BYREF
  __int16 v7; // [rsp+24h] [rbp-44h]
  __int16 v8; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "SxAllocateEventTraceProp", 34, 1);
  v2 = 41;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_9;
  }
  *a1 = 0;
  v6 = 0;
  v7 = 41;
  v3 = (struct _EVENT_TRACE_PROPERTIES *)CoTaskMemAlloc(0x488u);
  v2 = 45;
  if ( !v3 )
  {
    v6 = -2147024882;
LABEL_9:
    v8 = v2;
    goto LABEL_10;
  }
  v6 = 0;
  v7 = 45;
  memset_0(v3, 0, 0x488u);
  v3->Wnode.BufferSize = 1160;
  v3->Wnode.Flags = 0x20000;
  v3->LoggerNameOffset = 120;
  v3->LogFileNameOffset = 640;
  *a1 = v3;
LABEL_10:
  CoTaskMemFree(0);
  v4 = v6;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return v4;
}

```

## disassembly

```asm
0x180066dfc  mov     [rsp+arg_0], rbx
0x180066e01  push    rdi
0x180066e02  sub     rsp, 60h
0x180066e06  mov     rdi, rcx
0x180066e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e10  lea     rax, WPP_GLOBAL_Control
0x180066e17  cmp     rcx, rax
0x180066e1a  jz      short loc_180066E3A
0x180066e1c  test    dword ptr [rcx+1Ch], 20000000h
0x180066e23  jz      short loc_180066E3A
0x180066e25  mov     rcx, [rcx+10h]
0x180066e29  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x180066e30  mov     edx, 0Ah
0x180066e35  call    WPP_SF_
0x180066e3a  mov     r9d, 1; unsigned __int16
0x180066e40  lea     rdx, aSxallocateeven; "SxAllocateEventTraceProp"
0x180066e47  lea     rcx, [rsp+68h+var_48]; this
0x180066e4c  lea     r8d, [r9+21h]; unsigned __int16
0x180066e50  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180066e55  mov     eax, 29h ; ')'
0x180066e5a  test    rdi, rdi
0x180066e5d  jz      short loc_180066ED2
0x180066e5f  mov     ecx, 488h; cb
0x180066e64  mov     qword ptr [rdi], 0
0x180066e6b  mov     [rsp+68h+var_48], 0
0x180066e73  mov     [rsp+68h+var_44], ax
0x180066e78  call    cs:__imp_CoTaskMemAlloc
0x180066e7e  mov     rbx, rax
0x180066e81  test    rax, rax
0x180066e84  mov     eax, 2Dh ; '-'
0x180066e89  jnz     short loc_180066E95
0x180066e8b  mov     [rsp+68h+var_48], 8007000Eh
0x180066e93  jmp     short loc_180066EDA
0x180066e95  xor     edx, edx; Val
0x180066e97  mov     [rsp+68h+var_48], 0
0x180066e9f  mov     r8d, 488h; Size
0x180066ea5  mov     [rsp+68h+var_44], ax
0x180066eaa  mov     rcx, rbx; void *
0x180066ead  call    memset_0
0x180066eb2  mov     dword ptr [rbx], 488h
0x180066eb8  mov     dword ptr [rbx+2Ch], 20000h
0x180066ebf  mov     dword ptr [rbx+74h], 78h ; 'x'
0x180066ec6  mov     dword ptr [rbx+70h], 280h
0x180066ecd  mov     [rdi], rbx
0x180066ed0  jmp     short loc_180066EDF
0x180066ed2  mov     [rsp+68h+var_48], 80070057h
0x180066eda  mov     [rsp+68h+var_42], ax
0x180066edf  xor     ecx, ecx; pv
0x180066ee1  call    cs:__imp_CoTaskMemFree
0x180066ee7  mov     ebx, [rsp+68h+var_48]
0x180066eeb  lea     rcx, [rsp+68h+var_48]; this
0x180066ef0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180066ef5  mov     eax, ebx
0x180066ef7  mov     rbx, [rsp+68h+arg_0]
0x180066efc  add     rsp, 60h
0x180066f00  pop     rdi
0x180066f01  retn
```
