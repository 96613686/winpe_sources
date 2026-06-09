# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180002ad0`
- end: `0x180002b20`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001c94`
- `0x180002ad0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180002af4`
- `msvcrt!_wcsdup` at `0x180002af4`

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
0x180002ad0  mov     [rsp+arg_0], rbx
0x180002ad5  push    rdi
0x180002ad6  sub     rsp, 20h
0x180002ada  mov     rdi, rdx
0x180002add  mov     rbx, rcx
0x180002ae0  test    rdx, rdx
0x180002ae3  jnz     short loc_180002AEC
0x180002ae5  mov     eax, 80070057h
0x180002aea  jmp     short loc_180002B15
0x180002aec  test    r8, r8
0x180002aef  jz      short loc_180002B0A
0x180002af1  mov     rcx, r8; String
0x180002af4  call    cs:__imp__wcsdup
0x180002afa  mov     [rbx+8], rax
0x180002afe  test    rax, rax
0x180002b01  jnz     short loc_180002B0A
0x180002b03  mov     eax, 8007000Eh
0x180002b08  jmp     short loc_180002B15
0x180002b0a  mov     rdx, rdi; struct IUnknown *
0x180002b0d  mov     rcx, rbx; this
0x180002b10  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002b15  mov     rbx, [rsp+28h+arg_0]
0x180002b1a  add     rsp, 20h
0x180002b1e  pop     rdi
0x180002b1f  retn
```
