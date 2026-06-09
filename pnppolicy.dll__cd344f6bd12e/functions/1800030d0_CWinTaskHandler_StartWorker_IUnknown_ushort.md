# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800030d0`
- end: `0x180003120`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002db8`
- `0x1800030d0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x1800030f4`
- `msvcrt!_wcsdup` at `0x1800030f4`

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
0x1800030d0  mov     [rsp+arg_0], rbx
0x1800030d5  push    rdi
0x1800030d6  sub     rsp, 20h
0x1800030da  mov     rdi, rdx
0x1800030dd  mov     rbx, rcx
0x1800030e0  test    rdx, rdx
0x1800030e3  jnz     short loc_1800030EC
0x1800030e5  mov     eax, 80070057h
0x1800030ea  jmp     short loc_180003115
0x1800030ec  test    r8, r8
0x1800030ef  jz      short loc_18000310A
0x1800030f1  mov     rcx, r8; String
0x1800030f4  call    cs:__imp__wcsdup
0x1800030fa  mov     [rbx+8], rax
0x1800030fe  test    rax, rax
0x180003101  jnz     short loc_18000310A
0x180003103  mov     eax, 8007000Eh
0x180003108  jmp     short loc_180003115
0x18000310a  mov     rdx, rdi; struct IUnknown *
0x18000310d  mov     rcx, rbx; this
0x180003110  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180003115  mov     rbx, [rsp+28h+arg_0]
0x18000311a  add     rsp, 20h
0x18000311e  pop     rdi
0x18000311f  retn
```
