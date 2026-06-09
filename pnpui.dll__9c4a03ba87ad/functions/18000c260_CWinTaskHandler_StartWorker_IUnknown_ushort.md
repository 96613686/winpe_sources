# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x18000c260`
- end: `0x18000c2b0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000b498`
- `0x18000c260`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18000c284`
- `msvcrt!_wcsdup` at `0x18000c284`

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
0x18000c260  mov     [rsp+arg_0], rbx
0x18000c265  push    rdi
0x18000c266  sub     rsp, 20h
0x18000c26a  mov     rdi, rdx
0x18000c26d  mov     rbx, rcx
0x18000c270  test    rdx, rdx
0x18000c273  jnz     short loc_18000C27C
0x18000c275  mov     eax, 80070057h
0x18000c27a  jmp     short loc_18000C2A5
0x18000c27c  test    r8, r8
0x18000c27f  jz      short loc_18000C29A
0x18000c281  mov     rcx, r8; String
0x18000c284  call    cs:__imp__wcsdup
0x18000c28a  mov     [rbx+8], rax
0x18000c28e  test    rax, rax
0x18000c291  jnz     short loc_18000C29A
0x18000c293  mov     eax, 8007000Eh
0x18000c298  jmp     short loc_18000C2A5
0x18000c29a  mov     rdx, rdi; struct IUnknown *
0x18000c29d  mov     rcx, rbx; this
0x18000c2a0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x18000c2a5  mov     rbx, [rsp+28h+arg_0]
0x18000c2aa  add     rsp, 20h
0x18000c2ae  pop     rdi
0x18000c2af  retn
```
