# RpcSrvFirewallWcmSetFirewallRuleFlags

- ea: `0x180013240`
- end: `0x1800133c8`
- name: `RpcSrvFirewallWcmSetFirewallRuleFlags`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180013240`
- `0x1800133d0`
- `0x18001c080`
- `0x18002c020`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x18001331d`
- `FirewallAPI!FWQueryFirewallRules` at `0x18001331d`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800132a9`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800132a9`
- `FirewallAPI!FWSetFirewallRule` at `0x180013343`
- `FirewallAPI!FWSetFirewallRule` at `0x180013343`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001334e`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001334e`
- `FirewallAPI!FWClosePolicyStore` at `0x180013357`
- `FirewallAPI!FWClosePolicyStore` at `0x180013357`

## pseudocode

```c
unsigned int __fastcall RpcSrvFirewallWcmSetFirewallRuleFlags(__int64 a1, __int64 a2, __int16 a3)
{
  unsigned int v5; // eax
  unsigned int v6; // eax
  int v7; // ebx
  __int64 v8; // rsi
  unsigned int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  __int64 v12; // rdi
  unsigned int v14; // [rsp+20h] [rbp-49h]
  int v15; // [rsp+30h] [rbp-39h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h]
  unsigned int v17[2]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-21h] BYREF
  _DWORD v19[2]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  _QWORD v22[10]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  WINBOOL IsMember; // [rsp+E8h] [rbp+7Fh] BYREF

  IsMember = 0;
  v5 = IsCallerWcmSvc(&IsMember);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B0,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\sbrpc.cpp",
             (const char *)v5,
             v14);
  if ( !IsMember )
    return -2147024891;
  v16 = 0;
  v6 = FWOpenPolicyStore(545, 0, 8, 2);
  v7 = v6;
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xE8,
           (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
           (const char *)v6,
           0);
  }
  else
  {
    v8 = v16;
    v19[1] = 1;
    v18[1] = v22;
    v22[1] = 5;
    v20 = v18;
    v22[0] = 2;
    v22[2] = a2;
    v18[0] = 1;
    v19[0] = 545;
    v21 = 0x10000;
    *(_QWORD *)v17 = 0;
    v15 = 0;
    v9 = FWQueryFirewallRules(v16, v19, 0, &v15);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v10, v11, (const char *)v9, (unsigned int)v17);
    v12 = *(_QWORD *)v17;
    if ( *(_QWORD *)v17 )
    {
      *(_WORD *)(*(_QWORD *)v17 + 292LL) = a3;
      v7 = FWSetFirewallRule(v16, v12);
      FWFreeFirewallRules(v12);
    }
    FWClosePolicyStore(v8);
  }
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180013240  push    rbp
0x180013242  push    rbx
0x180013243  push    rsi
0x180013244  push    rdi
0x180013245  push    r13
0x180013247  push    r14
0x180013249  lea     rbp, [rsp-2Fh]
0x18001324e  sub     rsp, 98h
0x180013255  lea     rcx, [rbp+57h+IsMember]; IsMember
0x180013259  mov     [rbp+57h+IsMember], 0
0x180013260  movzx   r14d, r8w
0x180013264  mov     rdi, rdx
0x180013267  call    ?IsCallerWcmSvc@@YAKPEAH@Z; IsCallerWcmSvc(int *)
0x18001326c  test    eax, eax
0x18001326e  jnz     loc_180013373
0x180013274  cmp     [rbp+57h+IsMember], eax
0x180013277  jz      loc_1800133A9
0x18001327d  xor     edx, edx
0x18001327f  mov     [rbp+57h+var_88], 0
0x180013287  lea     rax, [rbp+57h+var_88]
0x18001328b  mov     r13d, 221h
0x180013291  mov     [rsp+0C0h+var_98], rax
0x180013296  mov     ecx, r13d
0x180013299  mov     [rsp+0C0h+var_A0], 0; unsigned int
0x1800132a1  lea     r9d, [rdx+2]
0x1800132a5  lea     r8d, [rdx+8]
0x1800132a9  call    cs:__imp_FWOpenPolicyStore
0x1800132af  mov     ebx, eax
0x1800132b1  test    eax, eax
0x1800132b3  jnz     loc_18001338D
0x1800132b9  mov     rsi, [rbp+57h+var_88]
0x1800132bd  lea     ecx, [rax+1]
0x1800132c0  lea     rax, [rbp+57h+var_50]
0x1800132c4  mov     [rbp+57h+var_64], ecx
0x1800132c7  mov     [rbp+57h+var_70], rax
0x1800132cb  lea     r9, [rbp+57h+var_90]
0x1800132cf  lea     rax, [rbp+57h+var_78]
0x1800132d3  mov     [rbp+57h+var_48], 5
0x1800132db  mov     [rbp+57h+var_60], rax
0x1800132df  lea     rdx, [rbp+57h+var_68]
0x1800132e3  lea     rax, [rbp+57h+var_80]
0x1800132e7  mov     [rbp+57h+var_50], 2
0x1800132ef  xor     r8d, r8d
0x1800132f2  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x1800132f7  mov     rcx, rsi
0x1800132fa  mov     [rbp+57h+var_40], rdi
0x1800132fe  mov     [rbp+57h+var_78], 1
0x180013306  mov     [rbp+57h+var_68], r13d
0x18001330a  mov     [rbp+57h+var_58], 10000h
0x180013312  mov     qword ptr [rbp+57h+var_80], 0
0x18001331a  mov     [rbp+57h+var_90], ebx
0x18001331d  call    cs:__imp_FWQueryFirewallRules
0x180013323  test    eax, eax
0x180013325  jnz     loc_1800133B0
0x18001332b  mov     rdi, qword ptr [rbp+57h+var_80]
0x18001332f  test    rdi, rdi
0x180013332  jz      short loc_180013354
0x180013334  mov     [rdi+124h], r14w
0x18001333c  mov     rdx, rdi
0x18001333f  mov     rcx, [rbp+57h+var_88]
0x180013343  call    cs:__imp_FWSetFirewallRule
0x180013349  mov     rcx, rdi
0x18001334c  mov     ebx, eax
0x18001334e  call    cs:__imp_FWFreeFirewallRules
0x180013354  mov     rcx, rsi
0x180013357  call    cs:__imp_FWClosePolicyStore
0x18001335d  test    ebx, ebx
0x18001335f  jg      short loc_1800133BD
0x180013361  mov     eax, ebx
0x180013363  add     rsp, 98h
0x18001336a  pop     r14
0x18001336c  pop     r13
0x18001336e  pop     rdi
0x18001336f  pop     rsi
0x180013370  pop     rbx
0x180013371  pop     rbp
0x180013372  retn
0x180013373  mov     rcx, [rbp+5Fh]; this
0x180013377  lea     r8, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18001337e  mov     r9d, eax; char *
0x180013381  mov     edx, 3B0h; void *
0x180013386  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001338b  jmp     short loc_180013363
0x18001338d  mov     rcx, [rbp+5Fh]; this
0x180013391  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x180013398  mov     r9d, eax; char *
0x18001339b  mov     edx, 0E8h; void *
0x1800133a0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800133a5  mov     ebx, eax
0x1800133a7  jmp     short loc_18001335D
0x1800133a9  mov     eax, 80070005h
0x1800133ae  jmp     short loc_180013363
0x1800133b0  mov     rcx, [rbp+5Fh]; this
0x1800133b4  mov     r9d, eax; char *
0x1800133b7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800133bd  movzx   ebx, bx
0x1800133c0  or      ebx, 80070000h
0x1800133c6  jmp     short loc_180013361
```
