# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800023b0`
- end: `0x180002400`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001b50`
- `0x1800023b0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x1800023d4`
- `msvcrt!_wcsdup` at `0x1800023d4`

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
0x1800023b0  mov     [rsp+arg_0], rbx
0x1800023b5  push    rdi
0x1800023b6  sub     rsp, 20h
0x1800023ba  mov     rdi, rdx
0x1800023bd  mov     rbx, rcx
0x1800023c0  test    rdx, rdx
0x1800023c3  jnz     short loc_1800023CC
0x1800023c5  mov     eax, 80070057h
0x1800023ca  jmp     short loc_1800023F5
0x1800023cc  test    r8, r8
0x1800023cf  jz      short loc_1800023EA
0x1800023d1  mov     rcx, r8; String
0x1800023d4  call    cs:__imp__wcsdup
0x1800023da  mov     [rbx+8], rax
0x1800023de  test    rax, rax
0x1800023e1  jnz     short loc_1800023EA
0x1800023e3  mov     eax, 8007000Eh
0x1800023e8  jmp     short loc_1800023F5
0x1800023ea  mov     rdx, rdi; struct IUnknown *
0x1800023ed  mov     rcx, rbx; this
0x1800023f0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x1800023f5  mov     rbx, [rsp+28h+arg_0]
0x1800023fa  add     rsp, 20h
0x1800023fe  pop     rdi
0x1800023ff  retn
```
