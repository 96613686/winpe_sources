# FwDetermineDuplicateStateOnDelete(_tag_FW_BLOB_RULE_CONTAINER *,_tag_FW_BLOB_MANIPULATOR *,ulong,_tag_FW_BLOB_CONTAINER * *,_tag_FW_STORE *)

- ea: `0x18008704c`
- end: `0x18008722d`
- name: `?FwDetermineDuplicateStateOnDelete@@YAXPEAU_tag_FW_BLOB_RULE_CONTAINER@@PEAU_tag_FW_BLOB_MANIPULATOR@@KPEAPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_STORE@@@Z`
- size: `481`
- prototype: `void __fastcall(struct _tag_FW_BLOB_RULE_CONTAINER *, struct _tag_FW_BLOB_MANIPULATOR *, unsigned int, struct _tag_FW_BLOB_CONTAINER **, struct _tag_FW_STORE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180028474`
- `0x180029484`

## callees

- `0x18002dcc0`
- `0x1800729c0`
- `0x18008704c`
- `0x180089910`
- `0x18008ba34`
- `0x18008f3d0`

## import_xrefs

- `fwbase!FwHashtableFind` at `0x180087183`
- `fwbase!FwHashtableFind` at `0x180087183`
- `fwbase!FwHashtableGetNext` at `0x1800871d5`
- `fwbase!FwHashtableGetNext` at `0x1800871d5`
- `fwbase!FwHashtableRemove` at `0x18008713d`
- `fwbase!FwHashtableRemove` at `0x18008713d`
- `fwbase!FwUpdateHash` at `0x180087106`
- `fwbase!FwUpdateHash` at `0x180087106`
- `fwbase!FwRestructureHashtable` at `0x18008715d`
- `fwbase!FwRestructureHashtable` at `0x18008715d`
- `fwbase!FwInitializeHashContext` at `0x1800870ec`
- `fwbase!FwInitializeHashContext` at `0x1800870ec`
- `fwbase!FwFinalHash` at `0x180087117`
- `fwbase!FwFinalHash` at `0x180087117`

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
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids, v10);
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
0x18008704c  mov     [rsp+arg_8], rbx
0x180087051  push    rbp
0x180087052  push    rsi
0x180087053  push    rdi
0x180087054  push    r14
0x180087056  push    r15
0x180087058  sub     rsp, 50h
0x18008705c  mov     rax, cs:__security_cookie
0x180087063  xor     rax, rsp
0x180087066  mov     [rsp+78h+var_38], rax
0x18008706b  mov     rdi, [rsp+78h+arg_20]
0x180087073  mov     rbx, rcx
0x180087076  mov     rcx, [rcx+128h]; Source
0x18008707d  xorps   xmm0, xmm0
0x180087080  xor     eax, eax
0x180087082  mov     [rsp+78h+var_58], 0
0x18008708b  mov     edx, 2710h; MaxCount
0x180087090  mov     [rsp+78h+var_40], rax
0x180087095  movups  [rsp+78h+var_50], xmm0
0x18008709a  mov     r14, r9
0x18008709d  mov     r15d, r8d
0x1800870a0  call    wcsnlen_s
0x1800870a5  mov     r9, [rbx+128h]
0x1800870ac  test    r9, r9
0x1800870af  jz      loc_18008720B
0x1800870b5  lea     rsi, [rax+rax]
0x1800870b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800870c0  lea     rax, WPP_GLOBAL_Control
0x1800870c7  cmp     rcx, rax
0x1800870ca  jz      short loc_1800870E7
0x1800870cc  test    byte ptr [rcx+1Ch], 4
0x1800870d0  jz      short loc_1800870E7
0x1800870d2  mov     rcx, [rcx+10h]
0x1800870d6  lea     r8, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids
0x1800870dd  mov     edx, 16h
0x1800870e2  call    WPP_SF_S
0x1800870e7  lea     rcx, [rsp+78h+var_58]
0x1800870ec  call    cs:__imp_FwInitializeHashContext
0x1800870f3  nop     dword ptr [rax+rax+00h]
0x1800870f8  mov     rcx, [rbx+128h]
0x1800870ff  lea     r8, [rsp+78h+var_58]
0x180087104  mov     edx, esi
0x180087106  call    cs:__imp_FwUpdateHash
0x18008710d  nop     dword ptr [rax+rax+00h]
0x180087112  lea     rcx, [rsp+78h+var_58]
0x180087117  call    cs:__imp_FwFinalHash
0x18008711e  nop     dword ptr [rax+rax+00h]
0x180087123  cmp     dword ptr [rbx+150h], 0
0x18008712a  mov     rbp, rax
0x18008712d  jz      short loc_180087149
0x18008712f  lea     rdx, [rbx+138h]
0x180087136  lea     rcx, [rdi+0F0h]
0x18008713d  call    cs:__imp_FwHashtableRemove
0x180087144  nop     dword ptr [rax+rax+00h]
0x180087149  lea     rsi, [rdi+0F0h]
0x180087150  mov     dword ptr [rbx+150h], 0
0x18008715a  mov     rcx, rsi
0x18008715d  call    cs:__imp_FwRestructureHashtable
0x180087164  nop     dword ptr [rax+rax+00h]
0x180087169  test    byte ptr [rbx+130h], 2
0x180087170  jz      short loc_180087178
0x180087172  dec     dword ptr [rdi+3BCh]
0x180087178  lea     r8, [rsp+78h+var_50]
0x18008717d  mov     rdx, rbp
0x180087180  mov     rcx, rsi
0x180087183  call    cs:__imp_FwHashtableFind
0x18008718a  nop     dword ptr [rax+rax+00h]
0x18008718f  test    rax, rax
0x180087192  jz      short loc_18008720B
0x180087194  cmp     dword ptr [rbx+130h], 6
0x18008719b  jnz     short loc_1800871CD
0x18008719d  mov     r8, [rbx+128h]
0x1800871a4  lea     rdi, [rax-138h]
0x1800871ab  mov     rax, [rdi+128h]
0x1800871b2  sub     r8, rax
0x1800871b5  movzx   ecx, word ptr [rax]
0x1800871b8  movzx   edx, word ptr [rax+r8]
0x1800871bd  sub     ecx, edx
0x1800871bf  jnz     short loc_1800871C9
0x1800871c1  add     rax, 2
0x1800871c5  test    edx, edx
0x1800871c7  jnz     short loc_1800871B5
0x1800871c9  test    ecx, ecx
0x1800871cb  jz      short loc_1800871E3
0x1800871cd  lea     rdx, [rsp+78h+var_50]
0x1800871d2  mov     rcx, rsi
0x1800871d5  call    cs:__imp_FwHashtableGetNext
0x1800871dc  nop     dword ptr [rax+rax+00h]
0x1800871e1  jmp     short loc_18008718F
0x1800871e3  mov     dword ptr [rdi+130h], 6
0x1800871ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x1800871f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x1800871f9  test    al, al
0x1800871fb  jz      short loc_180087208
0x1800871fd  mov     rcx, [rdi]
0x180087200  mov     edx, r15d
0x180087203  call    ?FwRuleResolveNameAndDescription@@YAXPEAU_tag_FW_BLOB_RULE@@W4FW_RULE_TYPE@@@Z; FwRuleResolveNameAndDescription(_tag_FW_BLOB_RULE *,FW_RULE_TYPE)
0x180087208  mov     [r14], rdi
0x18008720b  mov     rcx, [rsp+78h+var_38]
0x180087210  xor     rcx, rsp; StackCookie
0x180087213  call    __security_check_cookie
0x180087218  mov     rbx, [rsp+78h+arg_8]
0x180087220  add     rsp, 50h
0x180087224  pop     r15
0x180087226  pop     r14
0x180087228  pop     rdi
0x180087229  pop     rsi
0x18008722a  pop     rbp
0x18008722b  retn
```
