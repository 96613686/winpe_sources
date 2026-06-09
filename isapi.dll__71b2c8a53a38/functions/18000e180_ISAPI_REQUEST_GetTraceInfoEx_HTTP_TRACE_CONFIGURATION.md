# ISAPI_REQUEST::GetTraceInfoEx(HTTP_TRACE_CONFIGURATION *)

- ea: `0x18000e180`
- end: `0x18000e1b5`
- name: `?GetTraceInfoEx@ISAPI_REQUEST@@UEAAJPEAUHTTP_TRACE_CONFIGURATION@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, struct HTTP_TRACE_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetTraceInfoEx(ISAPI_REQUEST *this, struct HTTP_TRACE_CONFIGURATION *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, struct HTTP_TRACE_CONFIGURATION *); // rax

  v3 = (__int64 (__fastcall ***)(_QWORD, struct HTTP_TRACE_CONFIGURATION *))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
  return (**v3)(v3, a2);
}

```

## disassembly

```asm
0x18000e180  push    rbx
0x18000e182  sub     rsp, 20h
0x18000e186  mov     rcx, [rcx+18h]
0x18000e18a  mov     rbx, rdx
0x18000e18d  mov     rax, [rcx]
0x18000e190  mov     rax, [rax+110h]
0x18000e197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19c  mov     r8, rax
0x18000e19f  mov     rdx, rbx
0x18000e1a2  mov     rcx, [rax]
0x18000e1a5  mov     rax, [rcx]
0x18000e1a8  mov     rcx, r8
0x18000e1ab  add     rsp, 20h
0x18000e1af  pop     rbx
0x18000e1b0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
