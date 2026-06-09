# FwSvcPortsEnum::CreateInstance(_tag_FW_PROFILE_TYPE,_tag_FW_RULE * const,ulong,ulong,IEnumVARIANT * *)

- ea: `0x18004b738`
- end: `0x18004b854`
- name: `?CreateInstance@FwSvcPortsEnum@@SAJW4_tag_FW_PROFILE_TYPE@@QEAU_tag_FW_RULE@@KKPEAPEAUIEnumVARIANT@@@Z`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b4f0`
- `0x18004b640`

## callees

- `0x18004b668`
- `0x18004b738`
- `0x180062010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004b7d1`
- `fwbase!FwReportReturnError` at `0x18004b7e6`
- `fwbase!FwReportReturnError` at `0x18004b801`
- `fwbase!FwReportReturnError` at `0x18004b82a`
- `fwbase!FwReportReturnError` at `0x18004b7d1`
- `fwbase!FwReportReturnError` at `0x18004b7e6`
- `fwbase!FwReportReturnError` at `0x18004b801`
- `fwbase!FwReportReturnError` at `0x18004b82a`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004b7ae`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004b7ae`

## string_xrefs

- `0x18004b7fa`: `FwSvcPortsEnum::CreateInstance`
- `0x18004b823`: `FwSvcPortsEnum::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwSvcPortsEnum::CreateInstance(int a1, _QWORD *a2, int a3, int a4, _QWORD *a5)
{
  int v9; // eax
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  _QWORD *v12; // r14
  int v13; // eax
  _DWORD *v15; // [rsp+20h] [rbp-58h] BYREF

  v15 = 0;
  *a5 = 0;
  v9 = ATL::CComObject<FwSvcPortsEnum>::CreateInstance(&v15);
  v10 = v15;
  v11 = v9;
  if ( v9 < 0 )
  {
LABEL_7:
    FwReportReturnError("FwSvcPortsEnum::CreateInstance", (unsigned int)v9);
    if ( v10 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)FwReportReturnError("FwSvcPortsEnum::CreateInstance", v11);
  }
  else
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 8LL))(v15);
    v11 = 0;
    v10[16] = a4;
    v12 = v10 + 20;
    v10[18] = a1;
    while ( 1 )
    {
      if ( !a2 )
      {
        v10[22] = a3;
        goto LABEL_11;
      }
      v13 = FwCopyRule(a2, v12);
      v11 = v13;
      if ( v13 < 0 )
        break;
      v12 = (_QWORD *)*v12;
      a2 = (_QWORD *)*a2;
    }
    FwReportReturnError("FwSvcPortsEnum::Initialize", (unsigned int)v13);
    v9 = FwReportReturnError("FwSvcPortsEnum::Initialize", v11);
    v11 = v9;
    if ( v9 < 0 )
      goto LABEL_7;
LABEL_11:
    *a5 = v10;
  }
  return v11;
}

```

## disassembly

```asm
0x18004b738  push    rbx
0x18004b73a  push    rbp
0x18004b73b  push    rsi
0x18004b73c  push    rdi
0x18004b73d  push    r12
0x18004b73f  push    r13
0x18004b741  push    r14
0x18004b743  push    r15
0x18004b745  sub     rsp, 38h
0x18004b749  mov     r15, [rsp+78h+arg_20]
0x18004b751  mov     r13d, ecx
0x18004b754  lea     rcx, [rsp+78h+var_58]
0x18004b759  mov     [rsp+78h+var_58], 0
0x18004b762  mov     r12d, r9d
0x18004b765  mov     ebp, r8d
0x18004b768  mov     rsi, rdx
0x18004b76b  mov     qword ptr [r15], 0
0x18004b772  call    ?CreateInstance@?$CComObject@VFwSvcPortsEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwSvcPortsEnum>::CreateInstance(ATL::CComObject<FwSvcPortsEnum> * *)
0x18004b777  mov     rdi, [rsp+78h+var_58]
0x18004b77c  mov     ebx, eax
0x18004b77e  test    eax, eax
0x18004b780  js      short loc_18004B7F8
0x18004b782  mov     rax, [rdi]
0x18004b785  mov     rcx, rdi
0x18004b788  mov     rax, [rax+8]
0x18004b78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b791  xor     ebx, ebx
0x18004b793  mov     [rdi+40h], r12d
0x18004b797  lea     r14, [rdi+50h]
0x18004b79b  mov     [rdi+48h], r13d
0x18004b79f  test    rsi, rsi
0x18004b7a2  jz      loc_18004B83A
0x18004b7a8  mov     rdx, r14
0x18004b7ab  mov     rcx, rsi
0x18004b7ae  call    cs:__imp_FwCopyRule
0x18004b7b5  nop     dword ptr [rax+rax+00h]
0x18004b7ba  mov     ebx, eax
0x18004b7bc  test    eax, eax
0x18004b7be  js      short loc_18004B7C8
0x18004b7c0  mov     r14, [r14]
0x18004b7c3  mov     rsi, [rsi]
0x18004b7c6  jmp     short loc_18004B79F
0x18004b7c8  mov     edx, ebx
0x18004b7ca  lea     rcx, aFwsvcportsenum_1; "FwSvcPortsEnum::Initialize"
0x18004b7d1  call    cs:__imp_FwReportReturnError
0x18004b7d8  nop     dword ptr [rax+rax+00h]
0x18004b7dd  mov     edx, ebx
0x18004b7df  lea     rcx, aFwsvcportsenum_1; "FwSvcPortsEnum::Initialize"
0x18004b7e6  call    cs:__imp_FwReportReturnError
0x18004b7ed  nop     dword ptr [rax+rax+00h]
0x18004b7f2  mov     ebx, eax
0x18004b7f4  test    eax, eax
0x18004b7f6  jns     short loc_18004B83D
0x18004b7f8  mov     edx, eax
0x18004b7fa  lea     rcx, aFwsvcportsenum_0; "FwSvcPortsEnum::CreateInstance"
0x18004b801  call    cs:__imp_FwReportReturnError
0x18004b808  nop     dword ptr [rax+rax+00h]
0x18004b80d  test    rdi, rdi
0x18004b810  jz      short loc_18004B821
0x18004b812  mov     rax, [rdi]
0x18004b815  mov     rcx, rdi
0x18004b818  mov     rax, [rax+10h]
0x18004b81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b821  mov     edx, ebx
0x18004b823  lea     rcx, aFwsvcportsenum_0; "FwSvcPortsEnum::CreateInstance"
0x18004b82a  call    cs:__imp_FwReportReturnError
0x18004b831  nop     dword ptr [rax+rax+00h]
0x18004b836  mov     ebx, eax
0x18004b838  jmp     short loc_18004B840
0x18004b83a  mov     [rdi+58h], ebp
0x18004b83d  mov     [r15], rdi
0x18004b840  mov     eax, ebx
0x18004b842  add     rsp, 38h
0x18004b846  pop     r15
0x18004b848  pop     r14
0x18004b84a  pop     r13
0x18004b84c  pop     r12
0x18004b84e  pop     rdi
0x18004b84f  pop     rsi
0x18004b850  pop     rbp
0x18004b851  pop     rbx
0x18004b852  retn
```
