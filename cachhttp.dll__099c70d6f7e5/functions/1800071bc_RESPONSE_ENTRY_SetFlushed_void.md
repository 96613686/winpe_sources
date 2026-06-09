# RESPONSE_ENTRY::SetFlushed(void)

- ea: `0x1800071bc`
- end: `0x180007212`
- name: `?SetFlushed@RESPONSE_ENTRY@@QEAAXXZ`
- size: `86`
- prototype: `void __fastcall(RESPONSE_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064bc`
- `0x1800064fc`

## callees

- `0x180009010`

## pseudocode

```c
void __fastcall RESPONSE_ENTRY::SetFlushed(RESPONSE_ENTRY *this)
{
  void (__fastcall ***v1)(_QWORD, __int64, __int64); // rbx

  *((_DWORD *)this + 3) = 1;
  v1 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
  (**v1)(v1, 22, 1);
  (**v1)(v1, 21, 1);
}

```

## disassembly

```asm
0x1800071bc  push    rbx
0x1800071be  sub     rsp, 20h
0x1800071c2  mov     dword ptr [rcx+0Ch], 1
0x1800071c9  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800071d0  mov     rax, [rcx]
0x1800071d3  mov     rax, [rax+60h]
0x1800071d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071dc  mov     rbx, rax
0x1800071df  mov     edx, 16h
0x1800071e4  mov     rcx, [rax]
0x1800071e7  lea     r8d, [rdx-15h]
0x1800071eb  mov     rax, [rcx]
0x1800071ee  mov     rcx, rbx
0x1800071f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071f6  mov     rcx, [rbx]
0x1800071f9  mov     edx, 15h
0x1800071fe  mov     rax, [rcx]
0x180007201  lea     r8d, [rdx-14h]
0x180007205  mov     rcx, rbx
0x180007208  add     rsp, 20h
0x18000720c  pop     rbx
0x18000720d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
