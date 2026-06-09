# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180002b10`
- end: `0x180002b60`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002614`
- `0x180002b10`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180002b34`
- `msvcrt!_wcsdup` at `0x180002b34`

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
0x180002b10  mov     [rsp+arg_0], rbx
0x180002b15  push    rdi
0x180002b16  sub     rsp, 20h
0x180002b1a  mov     rdi, rdx
0x180002b1d  mov     rbx, rcx
0x180002b20  test    rdx, rdx
0x180002b23  jnz     short loc_180002B2C
0x180002b25  mov     eax, 80070057h
0x180002b2a  jmp     short loc_180002B55
0x180002b2c  test    r8, r8
0x180002b2f  jz      short loc_180002B4A
0x180002b31  mov     rcx, r8; String
0x180002b34  call    cs:__imp__wcsdup
0x180002b3a  mov     [rbx+8], rax
0x180002b3e  test    rax, rax
0x180002b41  jnz     short loc_180002B4A
0x180002b43  mov     eax, 8007000Eh
0x180002b48  jmp     short loc_180002B55
0x180002b4a  mov     rdx, rdi; struct IUnknown *
0x180002b4d  mov     rcx, rbx; this
0x180002b50  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002b55  mov     rbx, [rsp+28h+arg_0]
0x180002b5a  add     rsp, 20h
0x180002b5e  pop     rdi
0x180002b5f  retn
```
