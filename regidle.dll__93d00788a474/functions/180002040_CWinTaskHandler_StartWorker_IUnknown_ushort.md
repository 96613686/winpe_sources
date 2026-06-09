# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180002040`
- end: `0x180002090`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001b48`
- `0x180002040`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180002064`
- `msvcrt!_wcsdup` at `0x180002064`

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
0x180002040  mov     [rsp+arg_0], rbx
0x180002045  push    rdi
0x180002046  sub     rsp, 20h
0x18000204a  mov     rdi, rdx
0x18000204d  mov     rbx, rcx
0x180002050  test    rdx, rdx
0x180002053  jnz     short loc_18000205C
0x180002055  mov     eax, 80070057h
0x18000205a  jmp     short loc_180002085
0x18000205c  test    r8, r8
0x18000205f  jz      short loc_18000207A
0x180002061  mov     rcx, r8; String
0x180002064  call    cs:__imp__wcsdup
0x18000206a  mov     [rbx+8], rax
0x18000206e  test    rax, rax
0x180002071  jnz     short loc_18000207A
0x180002073  mov     eax, 8007000Eh
0x180002078  jmp     short loc_180002085
0x18000207a  mov     rdx, rdi; struct IUnknown *
0x18000207d  mov     rcx, rbx; this
0x180002080  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002085  mov     rbx, [rsp+28h+arg_0]
0x18000208a  add     rsp, 20h
0x18000208e  pop     rdi
0x18000208f  retn
```
