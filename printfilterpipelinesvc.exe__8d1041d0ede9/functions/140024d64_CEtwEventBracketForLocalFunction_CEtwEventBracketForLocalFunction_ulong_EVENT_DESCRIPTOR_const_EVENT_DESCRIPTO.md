# CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(ulong,_EVENT_DESCRIPTOR const &,_EVENT_DESCRIPTOR const &)

- ea: `0x140024d64`
- end: `0x140024dd3`
- name: `??0CEtwEventBracketForLocalFunction@@QEAA@KAEBU_EVENT_DESCRIPTOR@@0@Z`
- size: `111`
- prototype: `CEtwEventBracketForLocalFunction *__fastcall(CEtwEventBracketForLocalFunction *this, int, const struct _EVENT_DESCRIPTOR *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140025b48`
- `0x140025d5c`
- `0x140025ee4`

## callees

- `0x140024d64`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x140024d95`
- `ADVAPI32!EventEnabled` at `0x140024d95`
- `ADVAPI32!EventWrite` at `0x140024dba`
- `ADVAPI32!EventWrite` at `0x140024dba`

## pseudocode

```c
CEtwEventBracketForLocalFunction *__fastcall CEtwEventBracketForLocalFunction::CEtwEventBracketForLocalFunction(
        CEtwEventBracketForLocalFunction *this,
        int a2,
        const struct _EVENT_DESCRIPTOR *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  REGHANDLE v6; // rcx
  __int128 v7; // xmm0

  v6 = DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context;
  *(_QWORD *)this = DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context;
  v7 = (__int128)*a4;
  *((_DWORD *)this + 6) = a2;
  *(_OWORD *)((char *)this + 8) = v7;
  if ( EventEnabled(v6, a3) )
  {
    *((_QWORD *)this + 4) = (char *)this + 24;
    *((_QWORD *)this + 5) = 4;
    EventWrite(*(_QWORD *)this, a3, 1u, (PEVENT_DATA_DESCRIPTOR)this + 2);
  }
  return this;
}

```

## disassembly

```asm
0x140024d64  mov     [rsp+arg_0], rbx
0x140024d69  mov     [rsp+arg_8], rsi
0x140024d6e  push    rdi
0x140024d6f  sub     rsp, 20h
0x140024d73  mov     rbx, rcx
0x140024d76  mov     rdi, r8
0x140024d79  mov     rcx, cs:DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context; RegHandle
0x140024d80  mov     [rbx], rcx
0x140024d83  lea     rsi, [rbx+18h]
0x140024d87  movups  xmm0, xmmword ptr [r9]
0x140024d8b  mov     [rsi], edx
0x140024d8d  mov     rdx, r8; EventDescriptor
0x140024d90  movdqu  xmmword ptr [rbx+8], xmm0
0x140024d95  call    cs:__imp_EventEnabled
0x140024d9b  test    al, al
0x140024d9d  jz      short loc_140024DC0
0x140024d9f  lea     r9, [rbx+20h]; UserData
0x140024da3  mov     r8d, 1; UserDataCount
0x140024da9  mov     [r9], rsi
0x140024dac  mov     rdx, rdi; EventDescriptor
0x140024daf  mov     qword ptr [r9+8], 4
0x140024db7  mov     rcx, [rbx]; RegHandle
0x140024dba  call    cs:__imp_EventWrite
0x140024dc0  mov     rsi, [rsp+28h+arg_8]
0x140024dc5  mov     rax, rbx
0x140024dc8  mov     rbx, [rsp+28h+arg_0]
0x140024dcd  add     rsp, 20h
0x140024dd1  pop     rdi
0x140024dd2  retn
```
