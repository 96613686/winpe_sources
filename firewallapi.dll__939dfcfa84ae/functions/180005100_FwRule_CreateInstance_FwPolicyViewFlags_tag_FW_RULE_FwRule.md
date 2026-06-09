# FwRule::CreateInstance(FwPolicyViewFlags,_tag_FW_RULE *,FwRule * *)

- ea: `0x180005100`
- end: `0x18000529d`
- name: `?CreateInstance@FwRule@@SAJW4FwPolicyViewFlags@@PEAU_tag_FW_RULE@@PEAPEAV1@@Z`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004680`

## callees

- `0x180005100`
- `0x1800052b0`
- `0x18003336c`
- `0x180062010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x1800051cb`
- `fwbase!FwReportReturnError` at `0x1800051f9`
- `fwbase!FwReportReturnError` at `0x180005210`
- `fwbase!FwReportReturnError` at `0x180005239`
- `fwbase!FwReportReturnError` at `0x180005258`
- `fwbase!FwReportReturnError` at `0x1800051cb`
- `fwbase!FwReportReturnError` at `0x1800051f9`
- `fwbase!FwReportReturnError` at `0x180005210`
- `fwbase!FwReportReturnError` at `0x180005239`
- `fwbase!FwReportReturnError` at `0x180005258`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180005220`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180005220`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000518c`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000518c`

## string_xrefs

- `0x1800051c4`: `FwRule::CreateInstance`
- `0x1800051f2`: `FwRule::CreateInstance`
- `0x180005251`: `FwRule::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwRule::CreateInstance(int a1, __int64 a2, _QWORD *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rsi
  int v9; // eax
  int v11; // eax
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v12 = 0;
  *a3 = 0;
  v6 = ATL::CComObject<FwRule>::CreateInstance(&v12);
  v7 = v6;
  if ( v6 < 0 )
  {
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v6);
    v8 = v12;
  }
  else
  {
    v8 = v12;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
    *(_DWORD *)(v8 + 64) = a1;
    v9 = FwCopyRule(a2, v8 + 80);
    v7 = v9;
    if ( v9 >= 0 )
    {
      *(_DWORD *)(v8 + 88) = 1;
LABEL_10:
      *a3 = v8;
      return v7;
    }
    FwReportReturnError("FwRule::Initialize", (unsigned int)v9);
    FwFreeWFRule(*(_QWORD *)(v8 + 80));
    *(_QWORD *)(v8 + 80) = 0;
    v11 = FwReportReturnError("FwRule::Initialize", v7);
    v7 = v11;
    if ( v11 >= 0 )
      goto LABEL_10;
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v11);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return FwReportReturnError("FwRule::CreateInstance", v7);
}

```

## disassembly

```asm
0x180005100  mov     [rsp+arg_8], rbx
0x180005105  push    rbp
0x180005106  push    rdi
0x180005107  push    r12
0x180005109  push    r14
0x18000510b  push    r15
0x18000510d  sub     rsp, 20h
0x180005111  mov     rdi, r8
0x180005114  mov     rbp, rdx
0x180005117  mov     r14d, ecx
0x18000511a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005121  lea     r12, WPP_GLOBAL_Control
0x180005128  cmp     rcx, r12
0x18000512b  jz      short loc_180005137
0x18000512d  test    byte ptr [rcx+1Ch], 8
0x180005131  jnz     loc_180005269
0x180005137  xor     r15d, r15d
0x18000513a  mov     [rsp+48h+arg_0], rsi
0x18000513f  lea     rcx, [rsp+48h+arg_10]
0x180005144  mov     [rsp+48h+arg_10], r15
0x180005149  mov     [rdi], r15
0x18000514c  call    ?CreateInstance@?$CComObject@VFwRule@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRule>::CreateInstance(ATL::CComObject<FwRule> * *)
0x180005151  mov     ebx, eax
0x180005153  test    eax, eax
0x180005155  js      short loc_1800051C2
0x180005157  mov     rsi, [rsp+48h+arg_10]
0x18000515c  mov     rcx, rsi
0x18000515f  mov     rax, [rsi]
0x180005162  mov     rax, [rax+8]
0x180005166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005172  cmp     rcx, r12
0x180005175  jz      short loc_180005181
0x180005177  test    byte ptr [rcx+1Ch], 8
0x18000517b  jnz     loc_180005283
0x180005181  lea     rdx, [rsi+50h]
0x180005185  mov     [rsi+40h], r14d
0x180005189  mov     rcx, rbp
0x18000518c  call    cs:__imp_FwCopyRule
0x180005193  nop     dword ptr [rax+rax+00h]
0x180005198  mov     ebx, eax
0x18000519a  test    eax, eax
0x18000519c  js      short loc_180005207
0x18000519e  mov     dword ptr [rsi+58h], 1
0x1800051a5  mov     [rdi], rsi
0x1800051a8  mov     eax, ebx
0x1800051aa  mov     rsi, [rsp+48h+arg_0]
0x1800051af  mov     rbx, [rsp+48h+arg_8]
0x1800051b4  add     rsp, 20h
0x1800051b8  pop     r15
0x1800051ba  pop     r14
0x1800051bc  pop     r12
0x1800051be  pop     rdi
0x1800051bf  pop     rbp
0x1800051c0  retn
0x1800051c2  mov     edx, eax
0x1800051c4  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x1800051cb  call    cs:__imp_FwReportReturnError
0x1800051d2  nop     dword ptr [rax+rax+00h]
0x1800051d7  mov     rsi, [rsp+48h+arg_10]
0x1800051dc  test    rsi, rsi
0x1800051df  jz      short loc_1800051F0
0x1800051e1  mov     rax, [rsi]
0x1800051e4  mov     rcx, rsi
0x1800051e7  mov     rax, [rax+10h]
0x1800051eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f0  mov     edx, ebx
0x1800051f2  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x1800051f9  call    cs:__imp_FwReportReturnError
0x180005200  nop     dword ptr [rax+rax+00h]
0x180005205  jmp     short loc_1800051AA
0x180005207  mov     edx, ebx
0x180005209  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180005210  call    cs:__imp_FwReportReturnError
0x180005217  nop     dword ptr [rax+rax+00h]
0x18000521c  mov     rcx, [rsi+50h]
0x180005220  call    cs:__imp_FwFreeWFRule
0x180005227  nop     dword ptr [rax+rax+00h]
0x18000522c  mov     edx, ebx
0x18000522e  mov     [rsi+50h], r15
0x180005232  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180005239  call    cs:__imp_FwReportReturnError
0x180005240  nop     dword ptr [rax+rax+00h]
0x180005245  mov     ebx, eax
0x180005247  test    eax, eax
0x180005249  jns     loc_1800051A5
0x18000524f  mov     edx, eax
0x180005251  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180005258  call    cs:__imp_FwReportReturnError
0x18000525f  nop     dword ptr [rax+rax+00h]
0x180005264  jmp     loc_1800051DC
0x180005269  mov     rcx, [rcx+10h]
0x18000526d  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180005274  mov     edx, 55h ; 'U'
0x180005279  call    WPP_SF_
0x18000527e  jmp     loc_180005137
0x180005283  mov     rcx, [rcx+10h]
0x180005287  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18000528e  mov     edx, 5Ah ; 'Z'
0x180005293  call    WPP_SF_
0x180005298  jmp     loc_180005181
```
