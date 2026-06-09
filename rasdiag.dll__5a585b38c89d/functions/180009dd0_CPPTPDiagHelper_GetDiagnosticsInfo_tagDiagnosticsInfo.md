# CPPTPDiagHelper::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180009dd0`
- end: `0x180009e54`
- name: `?GetDiagnosticsInfo@CPPTPDiagHelper@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(CPPTPDiagHelper *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x18000b864`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009df9`
- `KERNEL32!SetLastError` at `0x180009df9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009de5`

## pseudocode

```c
__int64 __fastcall CPPTPDiagHelper::GetDiagnosticsInfo(CPPTPDiagHelper *this, struct tagDiagnosticsInfo **a2)
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
    CRasLogger::Log((char *)this + 112, 2, 1, L"CRasDiagHelper", L"GetDiagnosticsInfo::Memory allocation failed");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180009dd0  mov     [rsp+arg_0], rbx
0x180009dd5  push    rdi
0x180009dd6  sub     rsp, 30h
0x180009dda  mov     rdi, rcx
0x180009ddd  mov     rbx, rdx
0x180009de0  mov     ecx, 8; cb
0x180009de5  call    cs:__imp_CoTaskMemAlloc
0x180009dec  nop     dword ptr [rax+rax+00h]
0x180009df1  test    rax, rax
0x180009df4  jnz     short loc_180009E36
0x180009df6  lea     ecx, [rax+8]; dwErrCode
0x180009df9  call    cs:__imp_SetLastError
0x180009e00  nop     dword ptr [rax+rax+00h]
0x180009e05  mov     edx, 1
0x180009e0a  lea     rax, aGetdiagnostics; "GetDiagnosticsInfo::Memory allocation f"...
0x180009e11  movsx   r8d, dx
0x180009e15  lea     rcx, [rdi+70h]
0x180009e19  mov     edx, 2
0x180009e1e  mov     [rsp+38h+var_18], rax
0x180009e23  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x180009e2a  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180009e2f  mov     eax, 8007000Eh
0x180009e34  jmp     short loc_180009E48
0x180009e36  mov     dword ptr [rax], 0
0x180009e3c  mov     dword ptr [rax+4], 80000000h
0x180009e43  mov     [rbx], rax
0x180009e46  xor     eax, eax
0x180009e48  mov     rbx, [rsp+38h+arg_0]
0x180009e4d  add     rsp, 30h
0x180009e51  pop     rdi
0x180009e52  retn
```
