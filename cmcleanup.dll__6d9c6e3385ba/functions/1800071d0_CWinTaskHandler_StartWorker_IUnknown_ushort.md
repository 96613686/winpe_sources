# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800071d0`
- end: `0x180007220`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003c74`
- `0x1800071d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800071f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800071f4`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StartWorker(CWinTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  __int64 v6; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  v6 = _o__wcsdup(a3);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp+arg_0], rbx
0x1800071d5  push    rdi
0x1800071d6  sub     rsp, 20h
0x1800071da  mov     rdi, rdx
0x1800071dd  mov     rbx, rcx
0x1800071e0  test    rdx, rdx
0x1800071e3  jnz     short loc_1800071EC
0x1800071e5  mov     eax, 80070057h
0x1800071ea  jmp     short loc_180007215
0x1800071ec  test    r8, r8
0x1800071ef  jz      short loc_18000720A
0x1800071f1  mov     rcx, r8
0x1800071f4  call    cs:__imp__o__wcsdup
0x1800071fa  mov     [rbx+8], rax
0x1800071fe  test    rax, rax
0x180007201  jnz     short loc_18000720A
0x180007203  mov     eax, 8007000Eh
0x180007208  jmp     short loc_180007215
0x18000720a  mov     rdx, rdi; struct IUnknown *
0x18000720d  mov     rcx, rbx; this
0x180007210  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180007215  mov     rbx, [rsp+28h+arg_0]
0x18000721a  add     rsp, 20h
0x18000721e  pop     rdi
0x18000721f  retn
```
