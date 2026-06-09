# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800069a0`
- end: `0x1800069f0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003eb4`
- `0x1800069a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800069c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800069c4`

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
0x1800069a0  mov     [rsp+arg_0], rbx
0x1800069a5  push    rdi
0x1800069a6  sub     rsp, 20h
0x1800069aa  mov     rdi, rdx
0x1800069ad  mov     rbx, rcx
0x1800069b0  test    rdx, rdx
0x1800069b3  jnz     short loc_1800069BC
0x1800069b5  mov     eax, 80070057h
0x1800069ba  jmp     short loc_1800069E5
0x1800069bc  test    r8, r8
0x1800069bf  jz      short loc_1800069DA
0x1800069c1  mov     rcx, r8
0x1800069c4  call    cs:__imp__o__wcsdup
0x1800069ca  mov     [rbx+8], rax
0x1800069ce  test    rax, rax
0x1800069d1  jnz     short loc_1800069DA
0x1800069d3  mov     eax, 8007000Eh
0x1800069d8  jmp     short loc_1800069E5
0x1800069da  mov     rdx, rdi; struct IUnknown *
0x1800069dd  mov     rcx, rbx; this
0x1800069e0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x1800069e5  mov     rbx, [rsp+28h+arg_0]
0x1800069ea  add     rsp, 20h
0x1800069ee  pop     rdi
0x1800069ef  retn
```
