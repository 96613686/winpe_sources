# CIDiagnosisText::get_Extensions(IDiagnosisParameterEnum * *)

- ea: `0x1800161d0`
- end: `0x180016242`
- name: `?get_Extensions@CIDiagnosisText@@UEAAJPEAPEAUIDiagnosisParameterEnum@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CIDiagnosisText *__hidden this, struct IDiagnosisParameterEnum **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012114`
- `0x180014e68`
- `0x1800161d0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CIDiagnosisText::get_Extensions(CIDiagnosisText *this, struct IDiagnosisParameterEnum **a2)
{
  int v4; // ebx
  CIDiagnosisParameterEnum *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v4 = ATL::CComCreator<ATL::CComObject<CIDiagnosisParameterEnum>>::CreateInstance((__int64)this, (__int64)a2, &v6);
  if ( v4 >= 0 )
  {
    v4 = CIDiagnosisParameterEnum::SetEntries(
           v6,
           *((struct DiagnosisTextParser::DiagnosisParameter **)this + 12),
           *((_DWORD *)this + 26));
    if ( v4 < 0 )
      (*(void (__fastcall **)(CIDiagnosisParameterEnum *))(*(_QWORD *)v6 + 16LL))(v6);
    else
      *a2 = v6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800161d0  mov     rax, rsp
0x1800161d3  mov     [rax+8], rbx
0x1800161d7  mov     [rax+10h], rsi
0x1800161db  push    rdi
0x1800161dc  sub     rsp, 20h
0x1800161e0  lea     r8, [rax+18h]
0x1800161e4  mov     qword ptr [rax+18h], 0
0x1800161ec  mov     rdi, rdx
0x1800161ef  mov     rsi, rcx
0x1800161f2  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosisParameterEnum@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosisParameterEnum>>::CreateInstance(void *,_GUID const &,void * *)
0x1800161f7  mov     ebx, eax
0x1800161f9  test    eax, eax
0x1800161fb  js      short loc_180016230
0x1800161fd  mov     r8d, [rsi+68h]; unsigned int
0x180016201  mov     rdx, [rsi+60h]; struct DiagnosisTextParser::DiagnosisParameter *
0x180016205  mov     rcx, [rsp+28h+arg_10]; this
0x18001620a  call    ?SetEntries@CIDiagnosisParameterEnum@@QEAAJPEAUDiagnosisParameter@DiagnosisTextParser@@K@Z; CIDiagnosisParameterEnum::SetEntries(DiagnosisTextParser::DiagnosisParameter *,ulong)
0x18001620f  mov     ebx, eax
0x180016211  test    eax, eax
0x180016213  js      short loc_18001621F
0x180016215  mov     rax, [rsp+28h+arg_10]
0x18001621a  mov     [rdi], rax
0x18001621d  jmp     short loc_180016230
0x18001621f  mov     rcx, [rsp+28h+arg_10]
0x180016224  mov     rax, [rcx]
0x180016227  mov     rax, [rax+10h]
0x18001622b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016230  mov     rsi, [rsp+28h+arg_8]
0x180016235  mov     eax, ebx
0x180016237  mov     rbx, [rsp+28h+arg_0]
0x18001623c  add     rsp, 20h
0x180016240  pop     rdi
0x180016241  retn
```
