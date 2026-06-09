# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x18000d500`
- end: `0x18000d54c`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, struct tagDiagnosticsInfo **, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d500`
- `0x18000dd64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d518`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetDiagnosticsInfo(
        CNetDiagHelperImpl *this,
        struct tagDiagnosticsInfo **a2,
        __int64 a3,
        __int64 a4)
{
  struct tagDiagnosticsInfo *v5; // rax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3, a4);
  v5 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  v5->cost = 0;
  (*a2)->flags = 0x40000000;
  return 0;
}

```

## disassembly

```asm
0x18000d500  push    rbx
0x18000d502  sub     rsp, 20h
0x18000d506  mov     rbx, rdx
0x18000d509  test    rdx, rdx
0x18000d50c  jnz     short loc_18000D513
0x18000d50e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d513  mov     ecx, 8; cb
0x18000d518  call    cs:__imp_CoTaskMemAlloc
0x18000d51f  nop     dword ptr [rax+rax+00h]
0x18000d524  mov     [rbx], rax
0x18000d527  test    rax, rax
0x18000d52a  jnz     short loc_18000D533
0x18000d52c  mov     eax, 8007000Eh
0x18000d531  jmp     short loc_18000D545
0x18000d533  mov     dword ptr [rax], 0
0x18000d539  mov     rax, [rbx]
0x18000d53c  mov     dword ptr [rax+4], 40000000h
0x18000d543  xor     eax, eax
0x18000d545  add     rsp, 20h
0x18000d549  pop     rbx
0x18000d54a  retn
```
