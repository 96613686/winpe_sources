# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180013290`
- end: `0x1800132e0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000a4c4`
- `0x180013290`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800132b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800132b4`

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
0x180013290  mov     [rsp+arg_0], rbx
0x180013295  push    rdi
0x180013296  sub     rsp, 20h
0x18001329a  mov     rdi, rdx
0x18001329d  mov     rbx, rcx
0x1800132a0  test    rdx, rdx
0x1800132a3  jnz     short loc_1800132AC
0x1800132a5  mov     eax, 80070057h
0x1800132aa  jmp     short loc_1800132D5
0x1800132ac  test    r8, r8
0x1800132af  jz      short loc_1800132CA
0x1800132b1  mov     rcx, r8
0x1800132b4  call    cs:__imp__o__wcsdup
0x1800132ba  mov     [rbx+8], rax
0x1800132be  test    rax, rax
0x1800132c1  jnz     short loc_1800132CA
0x1800132c3  mov     eax, 8007000Eh
0x1800132c8  jmp     short loc_1800132D5
0x1800132ca  mov     rdx, rdi; struct IUnknown *
0x1800132cd  mov     rcx, rbx; this
0x1800132d0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x1800132d5  mov     rbx, [rsp+28h+arg_0]
0x1800132da  add     rsp, 20h
0x1800132de  pop     rdi
0x1800132df  retn
```
