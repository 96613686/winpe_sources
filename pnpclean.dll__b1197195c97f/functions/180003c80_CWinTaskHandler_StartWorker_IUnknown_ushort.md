# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180003c80`
- end: `0x180003cd0`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003a30`
- `0x180003c80`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180003ca4`
- `msvcrt!_wcsdup` at `0x180003ca4`

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
0x180003c80  mov     [rsp+arg_0], rbx
0x180003c85  push    rdi
0x180003c86  sub     rsp, 20h
0x180003c8a  mov     rdi, rdx
0x180003c8d  mov     rbx, rcx
0x180003c90  test    rdx, rdx
0x180003c93  jnz     short loc_180003C9C
0x180003c95  mov     eax, 80070057h
0x180003c9a  jmp     short loc_180003CC5
0x180003c9c  test    r8, r8
0x180003c9f  jz      short loc_180003CBA
0x180003ca1  mov     rcx, r8; String
0x180003ca4  call    cs:__imp__wcsdup
0x180003caa  mov     [rbx+8], rax
0x180003cae  test    rax, rax
0x180003cb1  jnz     short loc_180003CBA
0x180003cb3  mov     eax, 8007000Eh
0x180003cb8  jmp     short loc_180003CC5
0x180003cba  mov     rdx, rdi; struct IUnknown *
0x180003cbd  mov     rcx, rbx; this
0x180003cc0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180003cc5  mov     rbx, [rsp+28h+arg_0]
0x180003cca  add     rsp, 20h
0x180003cce  pop     rdi
0x180003ccf  retn
```
