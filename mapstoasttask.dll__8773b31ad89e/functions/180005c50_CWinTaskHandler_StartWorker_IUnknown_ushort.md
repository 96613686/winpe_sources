# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180005c50`
- end: `0x180005ca0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800033ec`
- `0x180005c50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180005c74`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180005c74`

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
0x180005c50  mov     [rsp+arg_0], rbx
0x180005c55  push    rdi
0x180005c56  sub     rsp, 20h
0x180005c5a  mov     rdi, rdx
0x180005c5d  mov     rbx, rcx
0x180005c60  test    rdx, rdx
0x180005c63  jnz     short loc_180005C6C
0x180005c65  mov     eax, 80070057h
0x180005c6a  jmp     short loc_180005C95
0x180005c6c  test    r8, r8
0x180005c6f  jz      short loc_180005C8A
0x180005c71  mov     rcx, r8
0x180005c74  call    cs:__imp__o__wcsdup
0x180005c7a  mov     [rbx+8], rax
0x180005c7e  test    rax, rax
0x180005c81  jnz     short loc_180005C8A
0x180005c83  mov     eax, 8007000Eh
0x180005c88  jmp     short loc_180005C95
0x180005c8a  mov     rdx, rdi; struct IUnknown *
0x180005c8d  mov     rcx, rbx; this
0x180005c90  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180005c95  mov     rbx, [rsp+28h+arg_0]
0x180005c9a  add     rsp, 20h
0x180005c9e  pop     rdi
0x180005c9f  retn
```
