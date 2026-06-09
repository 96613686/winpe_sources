# SplLogPipelineEvent(_EVENT_DESCRIPTOR const *,long)

- ea: `0x140056e3c`
- end: `0x140056eea`
- name: `?SplLogPipelineEvent@@YAXPEBU_EVENT_DESCRIPTOR@@J@Z`
- size: `174`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007fb0`
- `0x140010630`
- `0x140010880`
- `0x140010d60`
- `0x140011ce0`

## callees

- `0x140002070`
- `0x140056e3c`
- `0x140056f40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x140056e78`
- `ntdll!EtwEventEnabled` at `0x140056e78`
- `ntdll!EtwEventWrite` at `0x140056ead`
- `ntdll!EtwEventWrite` at `0x140056ead`

## string_xrefs

- `0x140056eb8`: `Event: %u, hresult: %hr: 0x%x, EventWrite: %d`

## pseudocode

```c
void __fastcall SplLogPipelineEvent(const struct _EVENT_DESCRIPTOR *a1, unsigned int a2)
{
  unsigned int Id; // ebx
  int v4; // [rsp+20h] [rbp-38h]
  unsigned int v5; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v6[2]; // [rsp+38h] [rbp-20h] BYREF

  if ( a1 )
  {
    v5 = a2;
    if ( g_bTracingEnabled )
    {
      if ( (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) )
      {
        Id = a1->Id;
        v6[0] = &v5;
        v6[1] = 4;
        v4 = EtwEventWrite(g_splRegistrationHandle, a1, 1, v6);
        PerfLibTelemetry::WriteDbgTraceInfo(
          "SplLogPipelineEvent",
          L"Event: %u, hresult: %hr: 0x%x, EventWrite: %d",
          Id,
          v5,
          v4);
      }
    }
  }
}

```

## disassembly

```asm
0x140056e3c  test    rcx, rcx
0x140056e3f  jz      locret_140056EE9
0x140056e45  mov     [rsp+arg_10], rbx
0x140056e4a  push    rdi
0x140056e4b  sub     rsp, 50h
0x140056e4f  mov     rax, cs:__security_cookie
0x140056e56  xor     rax, rsp
0x140056e59  mov     [rsp+58h+var_10], rax
0x140056e5e  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x140056e65  mov     rdi, rcx
0x140056e68  mov     [rsp+58h+var_28], edx
0x140056e6c  jz      short loc_140056ED2
0x140056e6e  mov     rdx, rcx
0x140056e71  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x140056e78  call    cs:__imp_EtwEventEnabled
0x140056e7e  test    al, al
0x140056e80  jz      short loc_140056ED2
0x140056e82  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x140056e89  lea     rax, [rsp+58h+var_28]
0x140056e8e  movzx   ebx, word ptr [rdi]
0x140056e91  lea     r9, [rsp+58h+var_20]
0x140056e96  mov     r8d, 1
0x140056e9c  mov     [rsp+58h+var_20], rax
0x140056ea1  mov     rdx, rdi
0x140056ea4  mov     [rsp+58h+var_18], 4
0x140056ead  call    cs:__imp_EtwEventWrite
0x140056eb3  mov     r9d, [rsp+58h+var_28]
0x140056eb8  lea     rdx, aEventUHresultH; "Event: %u, hresult: %hr: 0x%x, EventWri"...
0x140056ebf  mov     r8d, ebx
0x140056ec2  mov     [rsp+58h+var_38], eax
0x140056ec6  lea     rcx, aSpllogpipeline; "SplLogPipelineEvent"
0x140056ecd  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140056ed2  mov     rcx, [rsp+58h+var_10]
0x140056ed7  xor     rcx, rsp; StackCookie
0x140056eda  call    __security_check_cookie
0x140056edf  mov     rbx, [rsp+58h+arg_10]
0x140056ee4  add     rsp, 50h
0x140056ee8  pop     rdi
0x140056ee9  retn
```
