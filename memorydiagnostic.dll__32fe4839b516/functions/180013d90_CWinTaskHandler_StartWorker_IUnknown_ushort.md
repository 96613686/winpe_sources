# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180013d90`
- end: `0x180013de7`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `87`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000a654`
- `0x180013d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180013db4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180013db4`

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
0x180013d90  mov     [rsp+arg_0], rbx
0x180013d95  push    rdi
0x180013d96  sub     rsp, 20h
0x180013d9a  mov     rdi, rdx
0x180013d9d  mov     rbx, rcx
0x180013da0  test    rdx, rdx
0x180013da3  jnz     short loc_180013DAC
0x180013da5  mov     eax, 80070057h
0x180013daa  jmp     short loc_180013DDB
0x180013dac  test    r8, r8
0x180013daf  jz      short loc_180013DD0
0x180013db1  mov     rcx, r8
0x180013db4  call    cs:__imp__o__wcsdup
0x180013dbb  nop     dword ptr [rax+rax+00h]
0x180013dc0  mov     [rbx+8], rax
0x180013dc4  test    rax, rax
0x180013dc7  jnz     short loc_180013DD0
0x180013dc9  mov     eax, 8007000Eh
0x180013dce  jmp     short loc_180013DDB
0x180013dd0  mov     rdx, rdi; struct IUnknown *
0x180013dd3  mov     rcx, rbx; this
0x180013dd6  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180013ddb  mov     rbx, [rsp+28h+arg_0]
0x180013de0  add     rsp, 20h
0x180013de4  pop     rdi
0x180013de5  retn
```
