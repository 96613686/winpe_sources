# EtwpQueryRealTimeTraceProperties(ushort *,_REALTIME_TRACE_PROPERTIES *,ulong *,ulong *)

- ea: `0x18000fe48`
- end: `0x18000ff1c`
- name: `?EtwpQueryRealTimeTraceProperties@@YAKPEAGPEAU_REALTIME_TRACE_PROPERTIES@@PEAK2@Z`
- size: `212`
- prototype: `unsigned int __fastcall(LPCWSTR InstanceName, PEVENT_TRACE_PROPERTIES Properties, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180006c60`
- `0x180007060`
- `0x180007500`

## callees

- `0x180001eb2`
- `0x18000a300`
- `0x18000d780`
- `0x18000fe48`

## pseudocode

```c
ULONG __fastcall EtwpQueryRealTimeTraceProperties(
        LPCWSTR InstanceName,
        PEVENT_TRACE_PROPERTIES Properties,
        unsigned int *a3,
        unsigned int *a4)
{
  ULONG result; // eax
  ULONG64 HistoricalContext; // rbx
  ULONG NumberOfProcessors; // ecx
  _DWORD v11[14]; // [rsp+30h] [rbp-38h] BYREF

  v11[0] = 0;
  memset_0(&Properties->Wnode.ProviderId, 0, 0x1074u);
  Properties->Wnode.BufferSize = 4216;
  result = ControlTraceW(0, InstanceName, Properties, 0);
  if ( !result )
  {
    if ( (Properties->LogFileMode & 0x100) != 0 )
    {
      HistoricalContext = Properties->Wnode.HistoricalContext;
      TraceQueryInformation(HistoricalContext, 23, v11);
      if ( (Properties->LogFileMode & 0x10000000) != 0 )
        NumberOfProcessors = 1;
      else
        NumberOfProcessors = NtCurrentPeb()->NumberOfProcessors;
      if ( a4 )
        *a4 = (unsigned __int16)HistoricalContext;
      if ( a3 )
        *a3 = NumberOfProcessors;
      return 0;
    }
    else
    {
      return 4201;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe48  push    rbx
0x18000fe4a  push    rsi
0x18000fe4b  push    rdi
0x18000fe4c  push    r14
0x18000fe4e  sub     rsp, 48h
0x18000fe52  mov     rbx, rcx
0x18000fe55  mov     [rsp+68h+var_38], 0
0x18000fe5d  lea     rcx, [rdx+4]; void *
0x18000fe61  mov     [rsp+68h+arg_8], 0
0x18000fe69  mov     rsi, r8
0x18000fe6c  mov     rdi, rdx
0x18000fe6f  xor     edx, edx; Val
0x18000fe71  mov     r8d, 1074h; Size
0x18000fe77  mov     r14, r9
0x18000fe7a  call    memset_0
0x18000fe7f  xor     r9d, r9d; ControlCode
0x18000fe82  mov     dword ptr [rdi], 1078h
0x18000fe88  mov     r8, rdi; Properties
0x18000fe8b  mov     rdx, rbx; InstanceName
0x18000fe8e  xor     ecx, ecx; TraceHandle
0x18000fe90  call    ControlTraceW
0x18000fe95  test    eax, eax
0x18000fe97  jnz     short loc_18000FF12
0x18000fe99  test    dword ptr [rdi+40h], 100h
0x18000fea0  jnz     short loc_18000FEA9
0x18000fea2  mov     eax, 1069h
0x18000fea7  jmp     short loc_18000FF12
0x18000fea9  mov     rbx, [rdi+8]
0x18000fead  lea     rax, [rsp+68h+arg_8]
0x18000feb2  mov     r9d, 4
0x18000feb8  mov     [rsp+68h+var_48], rax
0x18000febd  lea     r8, [rsp+68h+var_38]
0x18000fec2  mov     rcx, rbx
0x18000fec5  lea     edx, [r9+13h]
0x18000fec9  call    TraceQueryInformation
0x18000fece  test    eax, eax
0x18000fed0  jnz     short loc_18000FEDF
0x18000fed2  cmp     [rsp+68h+arg_8], 4
0x18000fed7  jnz     short loc_18000FEDF
0x18000fed9  mov     ecx, [rsp+68h+var_38]
0x18000fedd  jmp     short loc_18000FEFE
0x18000fedf  test    dword ptr [rdi+40h], 10000000h
0x18000fee6  jz      short loc_18000FEEF
0x18000fee8  mov     ecx, 1
0x18000feed  jmp     short loc_18000FEFE
0x18000feef  mov     rax, gs:60h
0x18000fef8  mov     ecx, [rax+0B8h]
0x18000fefe  test    r14, r14
0x18000ff01  jz      short loc_18000FF09
0x18000ff03  movzx   eax, bx
0x18000ff06  mov     [r14], eax
0x18000ff09  test    rsi, rsi
0x18000ff0c  jz      short loc_18000FF10
0x18000ff0e  mov     [rsi], ecx
0x18000ff10  xor     eax, eax
0x18000ff12  add     rsp, 48h
0x18000ff16  pop     r14
0x18000ff18  pop     rdi
0x18000ff19  pop     rsi
0x18000ff1a  pop     rbx
0x18000ff1b  retn
```
