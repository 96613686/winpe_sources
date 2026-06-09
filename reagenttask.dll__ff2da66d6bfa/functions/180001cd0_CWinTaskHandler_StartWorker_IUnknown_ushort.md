# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180001cd0`
- end: `0x180001d27`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `87`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000199c`
- `0x180001cd0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180001cf4`
- `msvcrt!_wcsdup` at `0x180001cf4`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StartWorker(CWinTaskHandler *this, struct IUnknown *a2, wchar_t *String)
{
  wchar_t *v6; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( !String )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  v6 = _wcsdup(String);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180001cd0  mov     [rsp+arg_0], rbx
0x180001cd5  push    rdi
0x180001cd6  sub     rsp, 20h
0x180001cda  mov     rdi, rdx
0x180001cdd  mov     rbx, rcx
0x180001ce0  test    rdx, rdx
0x180001ce3  jnz     short loc_180001CEC
0x180001ce5  mov     eax, 80070057h
0x180001cea  jmp     short loc_180001D1B
0x180001cec  test    r8, r8
0x180001cef  jz      short loc_180001D10
0x180001cf1  mov     rcx, r8; String
0x180001cf4  call    cs:__imp__wcsdup
0x180001cfb  nop     dword ptr [rax+rax+00h]
0x180001d00  mov     [rbx+8], rax
0x180001d04  test    rax, rax
0x180001d07  jnz     short loc_180001D10
0x180001d09  mov     eax, 8007000Eh
0x180001d0e  jmp     short loc_180001D1B
0x180001d10  mov     rdx, rdi; struct IUnknown *
0x180001d13  mov     rcx, rbx; this
0x180001d16  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180001d1b  mov     rbx, [rsp+28h+arg_0]
0x180001d20  add     rsp, 20h
0x180001d24  pop     rdi
0x180001d25  retn
```
