# IIS_REQMON_CONTEXT::IIS_REQMON_CONTEXT(IHttpContext *)

- ea: `0x180001a08`
- end: `0x180001ac1`
- name: `??0IIS_REQMON_CONTEXT@@QEAA@PEAVIHttpContext@@@Z`
- size: `185`
- prototype: `IIS_REQMON_CONTEXT *__fastcall(IIS_REQMON_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002858`

## callees

- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a2b`

## pseudocode

```c
IIS_REQMON_CONTEXT *__fastcall IIS_REQMON_CONTEXT::IIS_REQMON_CONTEXT(
        IIS_REQMON_CONTEXT *this,
        struct IHttpContext *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rdi
  IIS_REQMON_CONTEXT *result; // rax

  *((_QWORD *)this + 3) = a2;
  *(_QWORD *)this = &IIS_REQMON_CONTEXT::`vftable';
  *((_DWORD *)this + 11) = GetTickCount();
  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  *((_QWORD *)this + 4) = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4) + 88);
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  LOWORD(v5) = *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 68);
  LOWORD(v5) = *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 70) + v5;
  result = this;
  *((_WORD *)this + 20) = (unsigned __int16)v5 >> 1;
  return result;
}

```

## disassembly

```asm
0x180001a08  mov     [rsp+arg_0], rbx
0x180001a0d  mov     [rsp+arg_8], rsi
0x180001a12  push    rdi
0x180001a13  sub     rsp, 20h
0x180001a17  lea     rax, ??_7IIS_REQMON_CONTEXT@@6B@; const IIS_REQMON_CONTEXT::`vftable'
0x180001a1e  mov     [rcx+18h], rdx
0x180001a22  mov     [rcx], rax
0x180001a25  mov     rdi, rdx
0x180001a28  mov     rsi, rcx
0x180001a2b  call    cs:__imp_GetTickCount
0x180001a31  mov     [rsi+2Ch], eax
0x180001a34  mov     rcx, rdi
0x180001a37  mov     rax, [rdi]
0x180001a3a  mov     rax, [rax+18h]
0x180001a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a43  mov     rdx, rax
0x180001a46  mov     rcx, [rax]
0x180001a49  mov     rax, [rcx+8]
0x180001a4d  mov     rcx, rdx
0x180001a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a55  mov     rcx, [rax+58h]
0x180001a59  mov     [rsi+20h], rcx
0x180001a5d  mov     rcx, rdi
0x180001a60  mov     rax, [rdi]
0x180001a63  mov     rax, [rax+18h]
0x180001a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a6c  mov     rcx, [rdi]
0x180001a6f  mov     rbx, rax
0x180001a72  mov     rax, [rcx+18h]
0x180001a76  mov     rcx, rdi
0x180001a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a7e  mov     rcx, [rbx]
0x180001a81  mov     rdi, rax
0x180001a84  mov     rax, [rcx+8]
0x180001a88  mov     rcx, rbx
0x180001a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a90  mov     rcx, [rdi]
0x180001a93  movzx   ebx, word ptr [rax+44h]
0x180001a97  mov     rax, [rcx+8]
0x180001a9b  mov     rcx, rdi
0x180001a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aa3  add     bx, [rax+46h]
0x180001aa7  mov     rax, rsi
0x180001aaa  shr     bx, 1
0x180001aad  mov     [rsi+28h], bx
0x180001ab1  mov     rbx, [rsp+28h+arg_0]
0x180001ab6  mov     rsi, [rsp+28h+arg_8]
0x180001abb  add     rsp, 20h
0x180001abf  pop     rdi
0x180001ac0  retn
```
