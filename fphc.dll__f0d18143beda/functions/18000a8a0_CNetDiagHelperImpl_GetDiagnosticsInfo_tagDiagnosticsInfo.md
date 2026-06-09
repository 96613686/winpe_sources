# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x18000a8a0`
- end: `0x18000a8e5`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a8a0`
- `0x18000edb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a8b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a8b8`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetDiagnosticsInfo(CNetDiagHelperImpl *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v3; // rax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v3 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  *a2 = v3;
  if ( !v3 )
    return 2147942414LL;
  v3->cost = 0;
  (*a2)->flags = 0x40000000;
  return 0;
}

```

## disassembly

```asm
0x18000a8a0  push    rbx
0x18000a8a2  sub     rsp, 20h
0x18000a8a6  mov     rbx, rdx
0x18000a8a9  test    rdx, rdx
0x18000a8ac  jnz     short loc_18000A8B3
0x18000a8ae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a8b3  mov     ecx, 8; cb
0x18000a8b8  call    cs:__imp_CoTaskMemAlloc
0x18000a8be  mov     [rbx], rax
0x18000a8c1  test    rax, rax
0x18000a8c4  jnz     short loc_18000A8CD
0x18000a8c6  mov     eax, 8007000Eh
0x18000a8cb  jmp     short loc_18000A8DF
0x18000a8cd  mov     dword ptr [rax], 0
0x18000a8d3  mov     rax, [rbx]
0x18000a8d6  mov     dword ptr [rax+4], 40000000h
0x18000a8dd  xor     eax, eax
0x18000a8df  add     rsp, 20h
0x18000a8e3  pop     rbx
0x18000a8e4  retn
```
