# CRasDiagHelper::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180006a30`
- end: `0x180006ab7`
- name: `?GetDiagnosticsInfo@CRasDiagHelper@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(CRasDiagHelper *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a30`
- `0x18000b864`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006a59`
- `KERNEL32!SetLastError` at `0x180006a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a45`

## pseudocode

```c
__int64 __fastcall CRasDiagHelper::GetDiagnosticsInfo(CRasDiagHelper *this, struct tagDiagnosticsInfo **a2)
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
    CRasLogger::Log((char *)this + 1208, 2, 1, L"CRasDiagHelper", L"GetDiagnosticsInfo::Memory allocation failed");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180006a30  mov     [rsp+arg_0], rbx
0x180006a35  push    rdi
0x180006a36  sub     rsp, 30h
0x180006a3a  mov     rdi, rcx
0x180006a3d  mov     rbx, rdx
0x180006a40  mov     ecx, 8; cb
0x180006a45  call    cs:__imp_CoTaskMemAlloc
0x180006a4c  nop     dword ptr [rax+rax+00h]
0x180006a51  test    rax, rax
0x180006a54  jnz     short loc_180006A99
0x180006a56  lea     ecx, [rax+8]; dwErrCode
0x180006a59  call    cs:__imp_SetLastError
0x180006a60  nop     dword ptr [rax+rax+00h]
0x180006a65  mov     edx, 1
0x180006a6a  lea     rax, aGetdiagnostics; "GetDiagnosticsInfo::Memory allocation f"...
0x180006a71  movsx   r8d, dx
0x180006a75  lea     rcx, [rdi+4B8h]
0x180006a7c  mov     edx, 2
0x180006a81  mov     [rsp+38h+var_18], rax
0x180006a86  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x180006a8d  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180006a92  mov     eax, 8007000Eh
0x180006a97  jmp     short loc_180006AAB
0x180006a99  mov     dword ptr [rax], 0
0x180006a9f  mov     dword ptr [rax+4], 80000000h
0x180006aa6  mov     [rbx], rax
0x180006aa9  xor     eax, eax
0x180006aab  mov     rbx, [rsp+38h+arg_0]
0x180006ab0  add     rsp, 30h
0x180006ab4  pop     rdi
0x180006ab5  retn
```
