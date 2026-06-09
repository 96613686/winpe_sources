# NatEnableGroupExceptionForICS(void)

- ea: `0x180044484`
- end: `0x1800447a8`
- name: `?NatEnableGroupExceptionForICS@@YAJXZ`
- size: `804`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180031e00`
- `0x18004634c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180037914`
- `0x18003a66c`
- `0x180044484`

## import_xrefs

- `FirewallAPI!FWSetFirewallRule` at `0x180044696`
- `FirewallAPI!FWSetFirewallRule` at `0x180044696`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800445e3`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800445e3`
- `FirewallAPI!FWClosePolicyStore` at `0x180044758`
- `FirewallAPI!FWClosePolicyStore` at `0x180044758`
- `FirewallAPI!FWFreeFirewallRules` at `0x180044739`
- `FirewallAPI!FWFreeFirewallRules` at `0x180044739`
- `FirewallAPI!FWOpenPolicyStore` at `0x180044526`
- `FirewallAPI!FWOpenPolicyStore` at `0x180044526`

## string_xrefs

- `0x180044595`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 NatEnableGroupExceptionForICS(void)
{
  int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rdi
  __int16 v7; // ax
  int v8; // eax
  __int128 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-20h]
  __int128 v13; // [rsp+58h] [rbp-18h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  unsigned int v15; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF
  __int64 *v17; // [rsp+B0h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_213010f39927376708ca656d45278473_Traceguids);
  }
  v16 = 0;
  v12 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v11 = 0;
  v10 = 0;
  v13 = 0;
  v0 = FWOpenPolicyStore(545, 0, 5, 2, 0, &v16);
  if ( v0 )
  {
    if ( v0 > 0 )
      v3 = (unsigned __int16)v0 | 0x80070000;
    else
      v3 = v0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 28;
LABEL_13:
      WPP_SF_d(v4[2], v5, &WPP_213010f39927376708ca656d45278473_Traceguids, (unsigned int)v0);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *(_QWORD *)&v11 = 0x100000008LL;
  v12 = L"@ipnathlp.dll,-140";
  LODWORD(v10) = 1;
  *((_QWORD *)&v10 + 1) = &v11;
  DWORD1(v13) = 1;
  *((_QWORD *)&v13 + 1) = &v10;
  DWORD2(v11) = 5;
  LODWORD(v14) = 0x10000;
  LOWORD(v13) = 545;
  v0 = FWQueryFirewallRules(v16, &v13, 0, &v15, &v17);
  if ( !v0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_213010f39927376708ca656d45278473_Traceguids, v15);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = v17;
    if ( !v17 )
      goto LABEL_44;
    v1 = 1;
    while ( 1 )
    {
      v7 = *((_WORD *)v6 + 146);
      if ( (v7 & 1) == 0 )
        break;
LABEL_43:
      v6 = (__int64 *)*v6;
      if ( !v6 )
        goto LABEL_44;
    }
    *((_WORD *)v6 + 146) = v7 | 1;
    v8 = FWSetFirewallRule(v16, v6);
    if ( v8 )
    {
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      else
        v3 = v8;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_213010f39927376708ca656d45278473_Traceguids,
        v6[2],
        v8);
    }
    else
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_42;
      }
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_213010f39927376708ca656d45278473_Traceguids, v6[2]);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_42:
    v1 = 1;
    goto LABEL_43;
  }
  if ( v0 > 0 )
    v3 = (unsigned __int16)v0 | 0x80070000;
  else
    v3 = v0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 29;
    goto LABEL_13;
  }
LABEL_44:
  if ( v17 )
  {
    FWFreeFirewallRules(v17);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    FWClosePolicyStore(v16, v1, v2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 33, &WPP_213010f39927376708ca656d45278473_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180044484  mov     [rsp-28h+arg_18], rbx
0x180044489  push    rbp
0x18004448a  push    rdi
0x18004448b  push    r12
0x18004448d  push    r14
0x18004448f  push    r15
0x180044491  mov     rbp, rsp
0x180044494  sub     rsp, 70h
0x180044498  mov     rcx, cs:WPP_GLOBAL_Control
0x18004449f  lea     r15, WPP_GLOBAL_Control
0x1800444a6  lea     r12, WPP_213010f39927376708ca656d45278473_Traceguids
0x1800444ad  mov     r14d, 200h
0x1800444b3  cmp     rcx, r15
0x1800444b6  jz      short loc_1800444D5
0x1800444b8  test    [rcx+1Ch], r14d
0x1800444bc  jz      short loc_1800444D5
0x1800444be  cmp     byte ptr [rcx+19h], 6
0x1800444c2  jb      short loc_1800444D5
0x1800444c4  mov     rcx, [rcx+10h]
0x1800444c8  mov     edx, 1Bh
0x1800444cd  mov     r8, r12
0x1800444d0  call    WPP_SF_
0x1800444d5  xor     eax, eax
0x1800444d7  mov     [rbp+arg_8], 0
0x1800444df  xor     edx, edx
0x1800444e1  mov     [rbp+var_20], rax
0x1800444e5  xorps   xmm0, xmm0
0x1800444e8  mov     [rbp+var_8], rax
0x1800444ec  mov     [rbp+arg_10], rax
0x1800444f0  xorps   xmm1, xmm1
0x1800444f3  lea     rax, [rbp+arg_8]
0x1800444f7  mov     [rbp+arg_0], 0
0x1800444fe  mov     [rsp+70h+var_48], rax
0x180044503  lea     r9d, [rdx+2]
0x180044507  mov     ebx, 221h
0x18004450c  mov     dword ptr [rsp+70h+var_50], 0
0x180044514  lea     r8d, [rdx+5]
0x180044518  mov     ecx, ebx
0x18004451a  movups  [rbp+var_30], xmm0
0x18004451e  movups  [rbp+var_40], xmm0
0x180044522  movups  [rbp+var_18], xmm1
0x180044526  call    cs:__imp_FWOpenPolicyStore
0x18004452d  nop     dword ptr [rax+rax+00h]
0x180044532  test    eax, eax
0x180044534  jz      short loc_180044589
0x180044536  jg      short loc_18004453C
0x180044538  mov     ebx, eax
0x18004453a  jmp     short loc_180044545
0x18004453c  movzx   ebx, ax
0x18004453f  or      ebx, 80070000h
0x180044545  mov     rcx, cs:WPP_GLOBAL_Control
0x18004454c  cmp     rcx, r15
0x18004454f  jz      loc_18004472D
0x180044555  test    [rcx+1Ch], r14d
0x180044559  jz      loc_18004472D
0x18004455f  cmp     byte ptr [rcx+19h], 2
0x180044563  jb      loc_18004472D
0x180044569  mov     edx, 1Ch
0x18004456e  mov     rcx, [rcx+10h]
0x180044572  mov     r9d, eax
0x180044575  mov     r8, r12
0x180044578  call    WPP_SF_d
0x18004457d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044584  jmp     loc_18004472D
0x180044589  mov     ecx, 1
0x18004458e  mov     dword ptr [rbp+var_30], 8
0x180044595  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x18004459c  mov     dword ptr [rbp+var_30+4], ecx
0x18004459f  mov     [rbp+var_20], rax
0x1800445a3  lea     r9, [rbp+arg_0]
0x1800445a7  lea     rax, [rbp+var_30]
0x1800445ab  mov     dword ptr [rbp+var_40], ecx
0x1800445ae  mov     qword ptr [rbp+var_40+8], rax
0x1800445b2  lea     rdx, [rbp+var_18]
0x1800445b6  lea     rax, [rbp+var_40]
0x1800445ba  mov     dword ptr [rbp+var_18+4], ecx
0x1800445bd  mov     rcx, [rbp+arg_8]
0x1800445c1  xor     r8d, r8d
0x1800445c4  mov     qword ptr [rbp+var_18+8], rax
0x1800445c8  lea     rax, [rbp+arg_10]
0x1800445cc  mov     [rsp+70h+var_50], rax
0x1800445d1  mov     dword ptr [rbp+var_30+8], 5
0x1800445d8  mov     dword ptr [rbp+var_8], 10000h
0x1800445df  mov     word ptr [rbp+var_18], bx
0x1800445e3  call    cs:__imp_FWQueryFirewallRules
0x1800445ea  nop     dword ptr [rax+rax+00h]
0x1800445ef  test    eax, eax
0x1800445f1  jz      short loc_180044630
0x1800445f3  jg      short loc_1800445F9
0x1800445f5  mov     ebx, eax
0x1800445f7  jmp     short loc_180044602
0x1800445f9  movzx   ebx, ax
0x1800445fc  or      ebx, 80070000h
0x180044602  mov     rcx, cs:WPP_GLOBAL_Control
0x180044609  cmp     rcx, r15
0x18004460c  jz      loc_18004472D
0x180044612  test    [rcx+1Ch], r14d
0x180044616  jz      loc_18004472D
0x18004461c  cmp     byte ptr [rcx+19h], 2
0x180044620  jb      loc_18004472D
0x180044626  mov     edx, 1Dh
0x18004462b  jmp     loc_18004456E
0x180044630  mov     rcx, cs:WPP_GLOBAL_Control
0x180044637  xor     ebx, ebx
0x180044639  cmp     rcx, r15
0x18004463c  jz      short loc_180044664
0x18004463e  test    [rcx+1Ch], r14d
0x180044642  jz      short loc_180044664
0x180044644  cmp     byte ptr [rcx+19h], 5
0x180044648  jb      short loc_180044664
0x18004464a  mov     r9d, [rbp+arg_0]
0x18004464e  lea     edx, [rbx+1Eh]
0x180044651  mov     rcx, [rcx+10h]
0x180044655  mov     r8, r12
0x180044658  call    WPP_SF_d
0x18004465d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044664  mov     rdi, [rbp+arg_10]
0x180044668  test    rdi, rdi
0x18004466b  jz      loc_18004472D
0x180044671  mov     edx, 1
0x180044676  movzx   eax, word ptr [rdi+124h]
0x18004467d  test    dl, al
0x18004467f  jnz     loc_180044721
0x180044685  or      ax, dx
0x180044688  mov     rdx, rdi
0x18004468b  mov     [rdi+124h], ax
0x180044692  mov     rcx, [rbp+arg_8]
0x180044696  call    cs:__imp_FWSetFirewallRule
0x18004469d  nop     dword ptr [rax+rax+00h]
0x1800446a2  test    eax, eax
0x1800446a4  jz      short loc_1800446E8
0x1800446a6  jg      short loc_1800446AC
0x1800446a8  mov     ebx, eax
0x1800446aa  jmp     short loc_1800446B5
0x1800446ac  movzx   ebx, ax
0x1800446af  or      ebx, 80070000h
0x1800446b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446bc  cmp     rcx, r15
0x1800446bf  jz      short loc_18004471C
0x1800446c1  test    [rcx+1Ch], r14d
0x1800446c5  jz      short loc_18004471C
0x1800446c7  cmp     byte ptr [rcx+19h], 2
0x1800446cb  jb      short loc_18004471C
0x1800446cd  mov     r9, [rdi+10h]
0x1800446d1  mov     edx, 1Fh
0x1800446d6  mov     rcx, [rcx+10h]
0x1800446da  mov     r8, r12
0x1800446dd  mov     dword ptr [rsp+70h+var_50], eax
0x1800446e1  call    WPP_SF_SD
0x1800446e6  jmp     short loc_180044715
0x1800446e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446ef  cmp     rcx, r15
0x1800446f2  jz      short loc_18004471C
0x1800446f4  test    [rcx+1Ch], r14d
0x1800446f8  jz      short loc_18004471C
0x1800446fa  cmp     byte ptr [rcx+19h], 5
0x1800446fe  jb      short loc_18004471C
0x180044700  mov     r9, [rdi+10h]
0x180044704  mov     edx, 20h ; ' '
0x180044709  mov     rcx, [rcx+10h]
0x18004470d  mov     r8, r12
0x180044710  call    WPP_SF_S
0x180044715  mov     rcx, cs:WPP_GLOBAL_Control
0x18004471c  mov     edx, 1
0x180044721  mov     rdi, [rdi]
0x180044724  test    rdi, rdi
0x180044727  jnz     loc_180044676
0x18004472d  mov     rax, [rbp+arg_10]
0x180044731  test    rax, rax
0x180044734  jz      short loc_18004474C
0x180044736  mov     rcx, rax
0x180044739  call    cs:__imp_FWFreeFirewallRules
0x180044740  nop     dword ptr [rax+rax+00h]
0x180044745  mov     rcx, cs:WPP_GLOBAL_Control
0x18004474c  mov     rax, [rbp+arg_8]
0x180044750  test    rax, rax
0x180044753  jz      short loc_18004476B
0x180044755  mov     rcx, rax
0x180044758  call    cs:__imp_FWClosePolicyStore
0x18004475f  nop     dword ptr [rax+rax+00h]
0x180044764  mov     rcx, cs:WPP_GLOBAL_Control
0x18004476b  cmp     rcx, r15
0x18004476e  jz      short loc_180044790
0x180044770  test    [rcx+1Ch], r14d
0x180044774  jz      short loc_180044790
0x180044776  cmp     byte ptr [rcx+19h], 6
0x18004477a  jb      short loc_180044790
0x18004477c  mov     rcx, [rcx+10h]
0x180044780  mov     edx, 21h ; '!'
0x180044785  mov     r9d, ebx
0x180044788  mov     r8, r12
0x18004478b  call    WPP_SF_d
0x180044790  mov     eax, ebx
0x180044792  mov     rbx, [rsp+70h+arg_18]
0x18004479a  add     rsp, 70h
0x18004479e  pop     r15
0x1800447a0  pop     r14
0x1800447a2  pop     r12
0x1800447a4  pop     rdi
0x1800447a5  pop     rbp
0x1800447a6  retn
```
