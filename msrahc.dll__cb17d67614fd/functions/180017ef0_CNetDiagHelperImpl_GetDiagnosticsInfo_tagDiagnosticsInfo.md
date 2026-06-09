# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180017ef0`
- end: `0x180017f35`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, struct tagDiagnosticsInfo **, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017ef0`
- `0x18001a178`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017f08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetDiagHelperImpl::GetDiagnosticsInfo(
        CNetDiagHelperImpl *this,
        struct tagDiagnosticsInfo **a2,
        __int64 a3)
{
  struct tagDiagnosticsInfo *v4; // rax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  v4 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4->cost = 0;
  (*a2)->flags = 0x40000000;
  return 0;
}

```

## disassembly

```asm
0x180017ef0  push    rbx
0x180017ef2  sub     rsp, 20h
0x180017ef6  mov     rbx, rdx
0x180017ef9  test    rdx, rdx
0x180017efc  jnz     short loc_180017F03
0x180017efe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017f03  mov     ecx, 8; cb
0x180017f08  call    cs:__imp_CoTaskMemAlloc
0x180017f0e  mov     [rbx], rax
0x180017f11  test    rax, rax
0x180017f14  jnz     short loc_180017F1D
0x180017f16  mov     eax, 8007000Eh
0x180017f1b  jmp     short loc_180017F2F
0x180017f1d  mov     dword ptr [rax], 0
0x180017f23  mov     rax, [rbx]
0x180017f26  mov     dword ptr [rax+4], 40000000h
0x180017f2d  xor     eax, eax
0x180017f2f  add     rsp, 20h
0x180017f33  pop     rbx
0x180017f34  retn
```
