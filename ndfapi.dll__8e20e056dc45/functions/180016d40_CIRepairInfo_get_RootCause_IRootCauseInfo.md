# CIRepairInfo::get_RootCause(IRootCauseInfo * *)

- ea: `0x180016d40`
- end: `0x180016dc1`
- name: `?get_RootCause@CIRepairInfo@@UEAAJPEAPEAUIRootCauseInfo@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(CIRepairInfo *__hidden this, struct IRootCauseInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001281c`
- `0x18001512c`
- `0x180016d40`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CIRepairInfo::get_RootCause(CIRepairInfo *this, struct IRootCauseInfo **a2)
{
  int v5; // ebx
  CIRootCauseInfo *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 10) )
    return 2147942421LL;
  v6 = 0;
  v5 = ATL::CComCreator<ATL::CComObject<CIRootCauseInfo>>::CreateInstance((__int64)this, (__int64)a2, &v6);
  if ( v5 >= 0 )
  {
    v5 = CIRootCauseInfo::SetRootCause(
           v6,
           *((const struct tagRootCauseInfo **)this + 9),
           *((struct INetworkDiagnostics **)this + 8));
    if ( v5 < 0 )
      (*(void (__fastcall **)(CIRootCauseInfo *))(*(_QWORD *)v6 + 16LL))(v6);
    else
      *a2 = v6;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016d40  mov     [rsp+arg_8], rbx
0x180016d45  mov     [rsp+arg_10], rsi
0x180016d4a  push    rdi
0x180016d4b  sub     rsp, 20h
0x180016d4f  cmp     qword ptr [rcx+50h], 0
0x180016d54  mov     rsi, rdx
0x180016d57  mov     rdi, rcx
0x180016d5a  jnz     short loc_180016D63
0x180016d5c  mov     eax, 80070015h
0x180016d61  jmp     short loc_180016DB1
0x180016d63  lea     r8, [rsp+28h+arg_0]
0x180016d68  mov     [rsp+28h+arg_0], 0
0x180016d71  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIRootCauseInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIRootCauseInfo>>::CreateInstance(void *,_GUID const &,void * *)
0x180016d76  mov     ebx, eax
0x180016d78  test    eax, eax
0x180016d7a  js      short loc_180016DAF
0x180016d7c  mov     r8, [rdi+40h]; struct INetworkDiagnostics *
0x180016d80  mov     rdx, [rdi+48h]; struct tagRootCauseInfo *
0x180016d84  mov     rcx, [rsp+28h+arg_0]; this
0x180016d89  call    ?SetRootCause@CIRootCauseInfo@@QEAAJPEBUtagRootCauseInfo@@PEAUINetworkDiagnostics@@@Z; CIRootCauseInfo::SetRootCause(tagRootCauseInfo const *,INetworkDiagnostics *)
0x180016d8e  mov     ebx, eax
0x180016d90  test    eax, eax
0x180016d92  js      short loc_180016D9E
0x180016d94  mov     rax, [rsp+28h+arg_0]
0x180016d99  mov     [rsi], rax
0x180016d9c  jmp     short loc_180016DAF
0x180016d9e  mov     rcx, [rsp+28h+arg_0]
0x180016da3  mov     rax, [rcx]
0x180016da6  mov     rax, [rax+10h]
0x180016daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016daf  mov     eax, ebx
0x180016db1  mov     rbx, [rsp+28h+arg_8]
0x180016db6  mov     rsi, [rsp+28h+arg_10]
0x180016dbb  add     rsp, 20h
0x180016dbf  pop     rdi
0x180016dc0  retn
```
