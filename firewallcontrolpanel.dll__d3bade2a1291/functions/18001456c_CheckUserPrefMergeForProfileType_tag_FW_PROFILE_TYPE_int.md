# CheckUserPrefMergeForProfileType(_tag_FW_PROFILE_TYPE,int &)

- ea: `0x18001456c`
- end: `0x180014698`
- name: `?CheckUserPrefMergeForProfileType@@YAJW4_tag_FW_PROFILE_TYPE@@AEAH@Z`
- size: `300`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011678`

## callees

- `0x18001456c`

## import_xrefs

- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x1800145ac`
- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x1800145ac`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800145ea`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800145ea`
- `FirewallAPI!FWGetConfig` at `0x18001461b`
- `FirewallAPI!FWGetConfig` at `0x18001464f`
- `FirewallAPI!FWGetConfig` at `0x18001461b`
- `FirewallAPI!FWGetConfig` at `0x18001464f`
- `FirewallAPI!FWClosePolicyStore` at `0x18001467d`
- `FirewallAPI!FWClosePolicyStore` at `0x18001467d`

## pseudocode

```c
__int64 __fastcall CheckUserPrefMergeForProfileType(unsigned int a1, int *a2)
{
  signed int IsGroupPolicyEnforced; // ebx
  int v5; // edi
  int v6; // eax
  bool v7; // cc
  int v9; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+38h] [rbp-8h] BYREF
  int v11; // [rsp+70h] [rbp+30h] BYREF
  int v12; // [rsp+78h] [rbp+38h] BYREF

  v12 = 0;
  v10 = 0;
  v11 = 0;
  v9 = 4;
  IsGroupPolicyEnforced = FwIsGroupPolicyEnforced(0, a1, &v12);
  if ( IsGroupPolicyEnforced >= 0 )
  {
    v5 = 1;
    if ( v12 )
    {
      v6 = FWOpenPolicyStore(545, 0, 5, 1, 0, &v10);
      v7 = v6 <= 0;
      if ( v6 || (v6 = FWGetConfig(v10, 11, a1, 1, &v11, &v9), v7 = v6 <= 0, v6) )
      {
        if ( v7 )
        {
          IsGroupPolicyEnforced = v6;
          goto LABEL_15;
        }
LABEL_11:
        IsGroupPolicyEnforced = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_15;
      }
      if ( !v11 )
      {
        *a2 = 0;
        goto LABEL_15;
      }
      v6 = FWGetConfig(v10, 13, a1, 1, &v11, &v9);
      IsGroupPolicyEnforced = v6;
      if ( v6 )
      {
        if ( v6 <= 0 )
          goto LABEL_15;
        goto LABEL_11;
      }
      v5 = v11;
    }
    else
    {
      v11 = 1;
    }
    IsGroupPolicyEnforced = 0;
    *a2 = v5;
  }
LABEL_15:
  if ( v10 )
    FWClosePolicyStore();
  return (unsigned int)IsGroupPolicyEnforced;
}

```

## disassembly

```asm
0x18001456c  mov     [rsp-18h+arg_0], rbx
0x180014571  mov     [rsp-18h+arg_8], rsi
0x180014576  push    rbp
0x180014577  push    rdi
0x180014578  push    r14
0x18001457a  mov     rbp, rsp
0x18001457d  sub     rsp, 40h
0x180014581  mov     rsi, rdx
0x180014584  mov     [rbp+arg_18], 0
0x18001458b  mov     edx, ecx
0x18001458d  mov     [rbp+var_8], 0
0x180014595  mov     r14d, ecx
0x180014598  mov     [rbp+arg_10], 0
0x18001459f  xor     ecx, ecx
0x1800145a1  mov     [rbp+var_10], 4
0x1800145a8  lea     r8, [rbp+arg_18]
0x1800145ac  call    cs:__imp_FwIsGroupPolicyEnforced
0x1800145b2  mov     ebx, eax
0x1800145b4  test    eax, eax
0x1800145b6  js      loc_180014674
0x1800145bc  cmp     [rbp+arg_18], 0
0x1800145c0  mov     edi, 1
0x1800145c5  jz      loc_18001466D
0x1800145cb  lea     rax, [rbp+var_8]
0x1800145cf  mov     ecx, 221h
0x1800145d4  mov     [rsp+40h+var_18], rax
0x1800145d9  lea     r8d, [rdi+4]
0x1800145dd  mov     r9d, edi
0x1800145e0  mov     dword ptr [rsp+40h+var_20], 0
0x1800145e8  xor     edx, edx
0x1800145ea  call    cs:__imp_FWOpenPolicyStore
0x1800145f0  test    eax, eax
0x1800145f2  jz      short loc_1800145FA
0x1800145f4  jg      short loc_18001465D
0x1800145f6  mov     ebx, eax
0x1800145f8  jmp     short loc_180014674
0x1800145fa  mov     rcx, [rbp+var_8]
0x1800145fe  lea     rax, [rbp+var_10]
0x180014602  mov     [rsp+40h+var_18], rax
0x180014607  mov     r9d, edi
0x18001460a  lea     rax, [rbp+arg_10]
0x18001460e  mov     r8d, r14d
0x180014611  mov     edx, 0Bh
0x180014616  mov     [rsp+40h+var_20], rax
0x18001461b  call    cs:__imp_FWGetConfig
0x180014621  test    eax, eax
0x180014623  jnz     short loc_1800145F4
0x180014625  cmp     [rbp+arg_10], eax
0x180014628  jnz     short loc_18001462E
0x18001462a  mov     [rsi], eax
0x18001462c  jmp     short loc_180014674
0x18001462e  mov     rcx, [rbp+var_8]
0x180014632  lea     rax, [rbp+var_10]
0x180014636  mov     [rsp+40h+var_18], rax
0x18001463b  mov     r9d, edi
0x18001463e  lea     rax, [rbp+arg_10]
0x180014642  mov     r8d, r14d
0x180014645  mov     edx, 0Dh
0x18001464a  mov     [rsp+40h+var_20], rax
0x18001464f  call    cs:__imp_FWGetConfig
0x180014655  mov     ebx, eax
0x180014657  test    eax, eax
0x180014659  jz      short loc_180014668
0x18001465b  jle     short loc_180014674
0x18001465d  movzx   ebx, ax
0x180014660  or      ebx, 80070000h
0x180014666  jmp     short loc_180014674
0x180014668  mov     edi, [rbp+arg_10]
0x18001466b  jmp     short loc_180014670
0x18001466d  mov     [rbp+arg_10], edi
0x180014670  xor     ebx, ebx
0x180014672  mov     [rsi], edi
0x180014674  mov     rcx, [rbp+var_8]
0x180014678  test    rcx, rcx
0x18001467b  jz      short loc_180014683
0x18001467d  call    cs:__imp_FWClosePolicyStore
0x180014683  mov     rsi, [rsp+40h+arg_8]
0x180014688  mov     eax, ebx
0x18001468a  mov     rbx, [rsp+40h+arg_0]
0x18001468f  add     rsp, 40h
0x180014693  pop     r14
0x180014695  pop     rdi
0x180014696  pop     rbp
0x180014697  retn
```
