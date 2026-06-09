# CVPNDiagHelper::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180008620`
- end: `0x1800086a7`
- name: `?GetDiagnosticsInfo@CVPNDiagHelper@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(CVPNDiagHelper *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008620`
- `0x18000b864`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008649`
- `KERNEL32!SetLastError` at `0x180008649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008635`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::GetDiagnosticsInfo(CVPNDiagHelper *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v4; // rax

  v4 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  if ( v4 )
  {
    v4->cost = 0;
    v4->flags = 0x80000000;
    *a2 = v4;
    return 0;
  }
  else
  {
    SetLastError(8u);
    CRasLogger::Log((char *)this + 1416, 2, 1, L"CRasDiagHelper", L"GetDiagnosticsInfo::Memory allocation failed");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180008620  mov     [rsp+arg_0], rbx
0x180008625  push    rdi
0x180008626  sub     rsp, 30h
0x18000862a  mov     rdi, rcx
0x18000862d  mov     rbx, rdx
0x180008630  mov     ecx, 8; cb
0x180008635  call    cs:__imp_CoTaskMemAlloc
0x18000863c  nop     dword ptr [rax+rax+00h]
0x180008641  test    rax, rax
0x180008644  jnz     short loc_180008689
0x180008646  lea     ecx, [rax+8]; dwErrCode
0x180008649  call    cs:__imp_SetLastError
0x180008650  nop     dword ptr [rax+rax+00h]
0x180008655  mov     edx, 1
0x18000865a  lea     rax, aGetdiagnostics; "GetDiagnosticsInfo::Memory allocation f"...
0x180008661  movsx   r8d, dx
0x180008665  lea     rcx, [rdi+588h]
0x18000866c  mov     edx, 2
0x180008671  mov     [rsp+38h+var_18], rax
0x180008676  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x18000867d  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180008682  mov     eax, 8007000Eh
0x180008687  jmp     short loc_18000869B
0x180008689  mov     dword ptr [rax], 0
0x18000868f  mov     dword ptr [rax+4], 80000000h
0x180008696  mov     [rbx], rax
0x180008699  xor     eax, eax
0x18000869b  mov     rbx, [rsp+38h+arg_0]
0x1800086a0  add     rsp, 30h
0x1800086a4  pop     rdi
0x1800086a5  retn
```
