# TraceNotSendCustomError(IHttpContext *,IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::enumReason)

- ea: `0x180005394`
- end: `0x1800053da`
- name: `?TraceNotSendCustomError@@YAXPEAVIHttpContext@@W4enumReason@GENERAL_NOT_SEND_CUSTOM_ERROR@IISGeneralEvents@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012c0`
- `0x18000471c`

## callees

- `0x180002b88`
- `0x1800043e0`
- `0x180005394`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall TraceNotSendCustomError(__int64 a1, unsigned int a2)
{
  struct IHttpTraceContext *v3; // rbx
  __int64 v4; // rdx
  __int64 result; // rax
  const struct _GUID *v6; // rdx

  v3 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 272LL))(a1);
  result = WWWServerTraceProvider::CheckTracingEnabled(v3, v4, 5);
  if ( (_DWORD)result )
    return IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::RaiseEvent(v3, v6, a2);
  return result;
}

```

## disassembly

```asm
0x180005394  mov     [rsp+arg_0], rbx
0x180005399  push    rdi
0x18000539a  sub     rsp, 20h
0x18000539e  mov     rax, [rcx]
0x1800053a1  mov     edi, edx
0x1800053a3  mov     rax, [rax+110h]
0x1800053aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053af  mov     r8d, 5
0x1800053b5  mov     rcx, rax
0x1800053b8  mov     rbx, rax
0x1800053bb  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800053c0  test    eax, eax
0x1800053c2  jz      short loc_1800053CF
0x1800053c4  mov     r8d, edi; unsigned int
0x1800053c7  mov     rcx, rbx; struct IHttpTraceContext *
0x1800053ca  call    ?RaiseEvent@GENERAL_NOT_SEND_CUSTOM_ERROR@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x1800053cf  mov     rbx, [rsp+28h+arg_0]
0x1800053d4  add     rsp, 20h
0x1800053d8  pop     rdi
0x1800053d9  retn
```
