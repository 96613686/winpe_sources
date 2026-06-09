# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800025c0`
- end: `0x180002610`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002028`
- `0x1800025c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800025e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800025e4`

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
0x1800025c0  mov     [rsp+arg_0], rbx
0x1800025c5  push    rdi
0x1800025c6  sub     rsp, 20h
0x1800025ca  mov     rdi, rdx
0x1800025cd  mov     rbx, rcx
0x1800025d0  test    rdx, rdx
0x1800025d3  jnz     short loc_1800025DC
0x1800025d5  mov     eax, 80070057h
0x1800025da  jmp     short loc_180002605
0x1800025dc  test    r8, r8
0x1800025df  jz      short loc_1800025FA
0x1800025e1  mov     rcx, r8
0x1800025e4  call    cs:__imp__o__wcsdup
0x1800025ea  mov     [rbx+8], rax
0x1800025ee  test    rax, rax
0x1800025f1  jnz     short loc_1800025FA
0x1800025f3  mov     eax, 8007000Eh
0x1800025f8  jmp     short loc_180002605
0x1800025fa  mov     rdx, rdi; struct IUnknown *
0x1800025fd  mov     rcx, rbx; this
0x180002600  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002605  mov     rbx, [rsp+28h+arg_0]
0x18000260a  add     rsp, 20h
0x18000260e  pop     rdi
0x18000260f  retn
```
