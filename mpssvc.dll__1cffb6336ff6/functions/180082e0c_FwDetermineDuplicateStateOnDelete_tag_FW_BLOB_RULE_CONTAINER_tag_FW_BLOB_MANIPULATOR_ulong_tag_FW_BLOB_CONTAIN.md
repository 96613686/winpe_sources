# FwDetermineDuplicateStateOnDelete(_tag_FW_BLOB_RULE_CONTAINER *,_tag_FW_BLOB_MANIPULATOR *,ulong,_tag_FW_BLOB_CONTAINER * *,_tag_FW_STORE *)

- ea: `0x180082e0c`
- end: `0x180082fc2`
- name: `?FwDetermineDuplicateStateOnDelete@@YAXPEAU_tag_FW_BLOB_RULE_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@KPEAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_STORE@@@Z`
- size: `438`
- prototype: `void __fastcall(struct _tag_FW_BLOB_RULE_CONTAINER *, struct _tag_FW_BLOB_MANIPULATOR *, unsigned int, struct _tag_FW_BLOB_CONTAINER **, struct _tag_FW_STORE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180025ed0`
- `0x180026e70`

## callees

- `0x18002a470`
- `0x18006f520`
- `0x180082e0c`
- `0x1800855c8`
- `0x1800873dc`
- `0x18008abb0`

## import_xrefs

- `fwbase!FwHashtableFind` at `0x180082f25`
- `fwbase!FwHashtableFind` at `0x180082f25`
- `fwbase!FwHashtableGetNext` at `0x180082f71`
- `fwbase!FwHashtableGetNext` at `0x180082f71`
- `fwbase!FwHashtableRemove` at `0x180082eeb`
- `fwbase!FwHashtableRemove` at `0x180082eeb`
- `fwbase!FwUpdateHash` at `0x180082ec0`
- `fwbase!FwUpdateHash` at `0x180082ec0`
- `fwbase!FwRestructureHashtable` at `0x180082f05`
- `fwbase!FwRestructureHashtable` at `0x180082f05`
- `fwbase!FwInitializeHashContext` at `0x180082eac`
- `fwbase!FwInitializeHashContext` at `0x180082eac`
- `fwbase!FwFinalHash` at `0x180082ecb`
- `fwbase!FwFinalHash` at `0x180082ecb`

## pseudocode

```c
void __fastcall FwDetermineDuplicateStateOnDelete(
        struct _tag_FW_BLOB_RULE_CONTAINER *a1,
        struct _tag_FW_BLOB_MANIPULATOR *a2,
        unsigned int a3,
        struct _tag_FW_BLOB_CONTAINER **a4,
        struct _tag_FW_STORE *a5)
{
  const wchar_t *v6; // rcx
  int v9; // eax
  __int64 v10; // r9
  unsigned int v11; // esi
  __int64 v12; // rbp
  __int64 i; // rax
  struct _tag_FW_BLOB_CONTAINER *v14; // rdi
  unsigned __int16 *v15; // rax
  __int64 v16; // r8
  int v17; // edx
  int v18; // ecx
  __int64 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+28h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h]

  v6 = (const wchar_t *)*((_QWORD *)a1 + 37);
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v9 = wcsnlen_s(v6, 0x2710u);
  v10 = *((_QWORD *)a1 + 37);
  if ( v10 )
  {
    v11 = 2 * v9;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_e2321870bb8f37110138dfc56d389809_Traceguids, v10);
    FwInitializeHashContext(&v19);
    FwUpdateHash(*((_QWORD *)a1 + 37), v11, &v19);
    v12 = FwFinalHash(&v19);
    if ( *((_DWORD *)a1 + 84) )
      FwHashtableRemove((char *)a5 + 240, (char *)a1 + 312);
    *((_DWORD *)a1 + 84) = 0;
    FwRestructureHashtable((char *)a5 + 240);
    if ( (*((_BYTE *)a1 + 304) & 2) != 0 )
      --*((_DWORD *)a5 + 239);
    for ( i = FwHashtableFind((char *)a5 + 240, v12, &v20); i; i = FwHashtableGetNext((char *)a5 + 240, &v20) )
    {
      if ( *((_DWORD *)a1 + 76) == 6 )
      {
        v14 = (struct _tag_FW_BLOB_CONTAINER *)(i - 312);
        v15 = *(unsigned __int16 **)(i - 312 + 296);
        v16 = *((_QWORD *)a1 + 37) - (_QWORD)v15;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v15 + v16);
          v18 = *v15 - v17;
          if ( v18 )
            break;
          ++v15;
        }
        while ( v17 );
        if ( !v18 )
        {
          *((_DWORD *)v14 + 76) = 6;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
            FwRuleResolveNameAndDescription(*(_QWORD *)v14, a3);
          *a4 = v14;
          return;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180082e0c  mov     [rsp+arg_8], rbx
0x180082e11  push    rbp
0x180082e12  push    rsi
0x180082e13  push    rdi
0x180082e14  push    r14
0x180082e16  push    r15
0x180082e18  sub     rsp, 50h
0x180082e1c  mov     rax, cs:__security_cookie
0x180082e23  xor     rax, rsp
0x180082e26  mov     [rsp+78h+var_38], rax
0x180082e2b  mov     rdi, [rsp+78h+arg_20]
0x180082e33  mov     rbx, rcx
0x180082e36  mov     rcx, [rcx+128h]; Source
0x180082e3d  xorps   xmm0, xmm0
0x180082e40  xor     eax, eax
0x180082e42  mov     [rsp+78h+var_58], 0
0x180082e4b  mov     edx, 2710h; MaxCount
0x180082e50  mov     [rsp+78h+var_40], rax
0x180082e55  movups  [rsp+78h+var_50], xmm0
0x180082e5a  mov     r14, r9
0x180082e5d  mov     r15d, r8d
0x180082e60  call    wcsnlen_s
0x180082e65  mov     r9, [rbx+128h]
0x180082e6c  test    r9, r9
0x180082e6f  jz      loc_180082FA1
0x180082e75  lea     rsi, [rax+rax]
0x180082e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180082e80  lea     rax, WPP_GLOBAL_Control
0x180082e87  cmp     rcx, rax
0x180082e8a  jz      short loc_180082EA7
0x180082e8c  test    byte ptr [rcx+1Ch], 4
0x180082e90  jz      short loc_180082EA7
0x180082e92  mov     rcx, [rcx+10h]
0x180082e96  lea     r8, WPP_e2321870bb8f37110138dfc56d389809_Traceguids
0x180082e9d  mov     edx, 16h
0x180082ea2  call    WPP_SF_S
0x180082ea7  lea     rcx, [rsp+78h+var_58]
0x180082eac  call    cs:__imp_FwInitializeHashContext
0x180082eb2  mov     rcx, [rbx+128h]
0x180082eb9  lea     r8, [rsp+78h+var_58]
0x180082ebe  mov     edx, esi
0x180082ec0  call    cs:__imp_FwUpdateHash
0x180082ec6  lea     rcx, [rsp+78h+var_58]
0x180082ecb  call    cs:__imp_FwFinalHash
0x180082ed1  cmp     dword ptr [rbx+150h], 0
0x180082ed8  mov     rbp, rax
0x180082edb  jz      short loc_180082EF1
0x180082edd  lea     rdx, [rbx+138h]
0x180082ee4  lea     rcx, [rdi+0F0h]
0x180082eeb  call    cs:__imp_FwHashtableRemove
0x180082ef1  lea     rsi, [rdi+0F0h]
0x180082ef8  mov     dword ptr [rbx+150h], 0
0x180082f02  mov     rcx, rsi
0x180082f05  call    cs:__imp_FwRestructureHashtable
0x180082f0b  test    byte ptr [rbx+130h], 2
0x180082f12  jz      short loc_180082F1A
0x180082f14  dec     dword ptr [rdi+3BCh]
0x180082f1a  lea     r8, [rsp+78h+var_50]
0x180082f1f  mov     rdx, rbp
0x180082f22  mov     rcx, rsi
0x180082f25  call    cs:__imp_FwHashtableFind
0x180082f2b  test    rax, rax
0x180082f2e  jz      short loc_180082FA1
0x180082f30  cmp     dword ptr [rbx+130h], 6
0x180082f37  jnz     short loc_180082F69
0x180082f39  mov     r8, [rbx+128h]
0x180082f40  lea     rdi, [rax-138h]
0x180082f47  mov     rax, [rdi+128h]
0x180082f4e  sub     r8, rax
0x180082f51  movzx   ecx, word ptr [rax]
0x180082f54  movzx   edx, word ptr [rax+r8]
0x180082f59  sub     ecx, edx
0x180082f5b  jnz     short loc_180082F65
0x180082f5d  add     rax, 2
0x180082f61  test    edx, edx
0x180082f63  jnz     short loc_180082F51
0x180082f65  test    ecx, ecx
0x180082f67  jz      short loc_180082F79
0x180082f69  lea     rdx, [rsp+78h+var_50]
0x180082f6e  mov     rcx, rsi
0x180082f71  call    cs:__imp_FwHashtableGetNext
0x180082f77  jmp     short loc_180082F2B
0x180082f79  mov     dword ptr [rdi+130h], 6
0x180082f83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x180082f8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x180082f8f  test    al, al
0x180082f91  jz      short loc_180082F9E
0x180082f93  mov     rcx, [rdi]
0x180082f96  mov     edx, r15d
0x180082f99  call    ?FwRuleResolveNameAndDescription@@YAXPEAU_tag_FW_BLOB_RULE@@W4FW_RULE_TYPE@@@Z; FwRuleResolveNameAndDescription(_tag_FW_BLOB_RULE *,FW_RULE_TYPE)
0x180082f9e  mov     [r14], rdi
0x180082fa1  mov     rcx, [rsp+78h+var_38]
0x180082fa6  xor     rcx, rsp; StackCookie
0x180082fa9  call    __security_check_cookie
0x180082fae  mov     rbx, [rsp+78h+arg_8]
0x180082fb6  add     rsp, 50h
0x180082fba  pop     r15
0x180082fbc  pop     r14
0x180082fbe  pop     rdi
0x180082fbf  pop     rsi
0x180082fc0  pop     rbp
0x180082fc1  retn
```
