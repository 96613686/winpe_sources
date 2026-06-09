# NatRemoveGroupExceptionForICS(int,ushort *)

- ea: `0x180032330`
- end: `0x1800326cc`
- name: `?NatRemoveGroupExceptionForICS@@YAJHPEAG@Z`
- size: `924`
- prototype: `__int64 __fastcall(size_t MaxCount, wchar_t *String1)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180031d04`
- `0x180031e00`
- `0x1800321b8`
- `0x18004634c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180032330`
- `0x180083ab0`
- `0x180095b10`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x1800324e2`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800324e2`
- `FirewallAPI!FWClosePolicyStore` at `0x180032609`
- `FirewallAPI!FWClosePolicyStore` at `0x180032609`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800325ed`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800325ed`
- `FirewallAPI!FWOpenPolicyStore` at `0x180032417`
- `FirewallAPI!FWOpenPolicyStore` at `0x180032417`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180032663`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180032663`

## string_xrefs

- `0x180032485`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 __fastcall NatRemoveGroupExceptionForICS(size_t MaxCount, wchar_t *String1, int a3)
{
  unsigned int v3; // r12d
  unsigned int v5; // esi
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  PVOID *v9; // rbx
  __int64 v10; // rdx
  __int64 **v11; // rdi
  unsigned int v13; // eax
  int v14; // edi
  __int128 v15; // [rsp+38h] [rbp-19h] BYREF
  __int128 v16; // [rsp+48h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp+7h]
  __int128 v18; // [rsp+60h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+70h] [rbp+1Fh]
  unsigned int v20; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+C8h] [rbp+77h] BYREF
  __int64 **v22; // [rsp+D0h] [rbp+7Fh] BYREF

  v3 = MaxCount;
  if ( String1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, a3, MaxCount, (__int64)String1);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      &WPP_213010f39927376708ca656d45278473_Traceguids,
      (unsigned int)MaxCount);
  }
  v5 = 0;
  v17 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v16 = 0;
  v15 = 0;
  v18 = 0;
  v6 = FWOpenPolicyStore(545, 0, 5, 2, 0, &v21);
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 45;
LABEL_18:
      WPP_SF_d(v9[2], v10, &WPP_213010f39927376708ca656d45278473_Traceguids, (unsigned int)v6);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v17 = L"@ipnathlp.dll,-140";
    *((_QWORD *)&v15 + 1) = &v16;
    *(_QWORD *)&v16 = 0x100000008LL;
    *((_QWORD *)&v18 + 1) = &v15;
    DWORD2(v16) = 5;
    LODWORD(v15) = 1;
    DWORD1(v18) = 1;
    LODWORD(v19) = 0x10000;
    LOWORD(v18) = 545;
    v6 = FWQueryFirewallRules(v21, &v18, 0, &v20, &v22);
    if ( !v6 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_213010f39927376708ca656d45278473_Traceguids, v20);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = v22;
      if ( v22 )
      {
        while ( wcsncmp_0(String1, (const wchar_t *)v11[3], v3) )
        {
          v11 = (__int64 **)*v11;
          if ( !v11 )
            goto LABEL_34;
        }
        v13 = FWDeleteFirewallRule(v21, v11[2]);
        v14 = v13;
        if ( v13 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_213010f39927376708ca656d45278473_Traceguids, v13);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v14 > 0 )
            v5 = (unsigned __int16)v14 | 0x80070000;
          else
            v5 = v14;
          goto LABEL_39;
        }
      }
      else
      {
LABEL_34:
        if ( v9 == &WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x200) == 0 || *((_BYTE *)v9 + 25) < 3u )
          goto LABEL_39;
        WPP_SF_(v9[2], 49, &WPP_213010f39927376708ca656d45278473_Traceguids);
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_39;
    }
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 46;
      goto LABEL_18;
    }
  }
LABEL_39:
  if ( v22 )
  {
    FWFreeFirewallRules(v22);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 )
  {
    FWClosePolicyStore(v21, v7, v8);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 50, &WPP_213010f39927376708ca656d45278473_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180032330  mov     rax, rsp
0x180032333  push    rbp
0x180032334  push    rbx
0x180032335  push    rsi
0x180032336  lea     rbp, [rax-5Fh]
0x18003233a  sub     rsp, 90h
0x180032341  mov     [rax-28h], r12
0x180032345  mov     r12d, ecx
0x180032348  mov     [rax-30h], r14
0x18003234c  mov     [rax-38h], r15
0x180032350  mov     r15, rdx
0x180032353  test    rdx, rdx
0x180032356  jz      short loc_180032392
0x180032358  mov     rcx, cs:WPP_GLOBAL_Control
0x18003235f  lea     r14, WPP_GLOBAL_Control
0x180032366  cmp     rcx, r14
0x180032369  jz      short loc_1800323CC
0x18003236b  test    dword ptr [rcx+1Ch], 200h
0x180032372  jz      short loc_1800323CC
0x180032374  cmp     byte ptr [rcx+19h], 6
0x180032378  jb      short loc_1800323CC
0x18003237a  mov     rcx, [rcx+10h]
0x18003237e  mov     edx, 2Bh ; '+'
0x180032383  mov     r9d, r12d
0x180032386  mov     [rsp+0A0h+var_80], r15
0x18003238b  call    WPP_SF_dS
0x180032390  jmp     short loc_1800323CC
0x180032392  mov     rcx, cs:WPP_GLOBAL_Control
0x180032399  lea     r14, WPP_GLOBAL_Control
0x1800323a0  cmp     rcx, r14
0x1800323a3  jz      short loc_1800323CC
0x1800323a5  test    dword ptr [rcx+1Ch], 200h
0x1800323ac  jz      short loc_1800323CC
0x1800323ae  cmp     byte ptr [rcx+19h], 6
0x1800323b2  jb      short loc_1800323CC
0x1800323b4  mov     rcx, [rcx+10h]
0x1800323b8  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x1800323bf  mov     edx, 2Ch ; ','
0x1800323c4  mov     r9d, r12d
0x1800323c7  call    WPP_SF_d
0x1800323cc  xor     eax, eax
0x1800323ce  xor     esi, esi
0x1800323d0  xorps   xmm0, xmm0
0x1800323d3  mov     [rbp+57h+var_50], rax
0x1800323d7  mov     [rbp+57h+var_38], rax
0x1800323db  xorps   xmm1, xmm1
0x1800323de  lea     rax, [rbp+57h+arg_10]
0x1800323e2  mov     [rbp+57h+arg_10], rsi
0x1800323e6  mov     [rsp+28h], rax
0x1800323eb  mov     ebx, 221h
0x1800323f0  mov     ecx, ebx
0x1800323f2  mov     dword ptr [rsp+0A0h+var_80], esi
0x1800323f6  xor     edx, edx
0x1800323f8  mov     [rbp+57h+arg_8], esi
0x1800323fb  mov     r9d, 2
0x180032401  mov     [rbp+57h+arg_18], rsi
0x180032405  mov     r8d, 5
0x18003240b  movups  [rbp+57h+var_60], xmm0
0x18003240f  movups  [rbp+57h+var_70], xmm0
0x180032413  movups  [rbp+57h+var_48], xmm1
0x180032417  call    cs:__imp_FWOpenPolicyStore
0x18003241e  nop     dword ptr [rax+rax+00h]
0x180032423  test    eax, eax
0x180032425  jz      short loc_180032481
0x180032427  jg      short loc_18003242D
0x180032429  mov     esi, eax
0x18003242b  jmp     short loc_180032436
0x18003242d  movzx   esi, ax
0x180032430  or      esi, 80070000h
0x180032436  mov     rbx, cs:WPP_GLOBAL_Control
0x18003243d  cmp     rbx, r14
0x180032440  jz      loc_1800325D7
0x180032446  test    dword ptr [rbx+1Ch], 200h
0x18003244d  jz      loc_1800325D7
0x180032453  cmp     byte ptr [rbx+19h], 2
0x180032457  jb      loc_1800325D7
0x18003245d  mov     edx, 2Dh ; '-'
0x180032462  mov     rcx, [rbx+10h]
0x180032466  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18003246d  mov     r9d, eax
0x180032470  call    WPP_SF_d
0x180032475  mov     rbx, cs:WPP_GLOBAL_Control
0x18003247c  jmp     loc_1800325D7
0x180032481  mov     rcx, [rbp+57h+arg_10]
0x180032485  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x18003248c  mov     [rbp+57h+var_50], rax
0x180032490  lea     r9, [rbp+57h+arg_8]
0x180032494  lea     rax, [rbp+57h+var_60]
0x180032498  mov     dword ptr [rbp+57h+var_60+4], 1
0x18003249f  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800324a3  lea     rdx, [rbp+57h+var_48]
0x1800324a7  lea     rax, [rbp+57h+var_70]
0x1800324ab  mov     dword ptr [rbp+57h+var_60], 8
0x1800324b2  mov     qword ptr [rbp+57h+var_48+8], rax
0x1800324b6  xor     r8d, r8d
0x1800324b9  lea     rax, [rbp+57h+arg_18]
0x1800324bd  mov     dword ptr [rbp+57h+var_60+8], 5
0x1800324c4  mov     [rsp+0A0h+var_80], rax
0x1800324c9  mov     dword ptr [rbp+57h+var_70], 1
0x1800324d0  mov     dword ptr [rbp+57h+var_48+4], 1
0x1800324d7  mov     dword ptr [rbp+57h+var_38], 10000h
0x1800324de  mov     word ptr [rbp+57h+var_48], bx
0x1800324e2  call    cs:__imp_FWQueryFirewallRules
0x1800324e9  nop     dword ptr [rax+rax+00h]
0x1800324ee  test    eax, eax
0x1800324f0  jz      short loc_180032532
0x1800324f2  jg      short loc_1800324F8
0x1800324f4  mov     esi, eax
0x1800324f6  jmp     short loc_180032501
0x1800324f8  movzx   esi, ax
0x1800324fb  or      esi, 80070000h
0x180032501  mov     rbx, cs:WPP_GLOBAL_Control
0x180032508  cmp     rbx, r14
0x18003250b  jz      loc_1800325D7
0x180032511  test    dword ptr [rbx+1Ch], 200h
0x180032518  jz      loc_1800325D7
0x18003251e  cmp     byte ptr [rbx+19h], 2
0x180032522  jb      loc_1800325D7
0x180032528  mov     edx, 2Eh ; '.'
0x18003252d  jmp     loc_180032462
0x180032532  mov     rbx, cs:WPP_GLOBAL_Control
0x180032539  mov     [rsp+88h], rdi
0x180032541  cmp     rbx, r14
0x180032544  jz      short loc_180032575
0x180032546  test    dword ptr [rbx+1Ch], 200h
0x18003254d  jz      short loc_180032575
0x18003254f  cmp     byte ptr [rbx+19h], 5
0x180032553  jb      short loc_180032575
0x180032555  mov     r9d, [rbp+57h+arg_8]
0x180032559  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180032560  mov     rcx, [rbx+10h]
0x180032564  mov     edx, 2Fh ; '/'
0x180032569  call    WPP_SF_d
0x18003256e  mov     rbx, cs:WPP_GLOBAL_Control
0x180032575  mov     rdi, [rbp+57h+arg_18]
0x180032579  test    rdi, rdi
0x18003257c  jz      short loc_18003259F
0x18003257e  xchg    ax, ax
0x180032580  mov     rdx, [rdi+18h]; String2
0x180032584  mov     r8d, r12d; MaxCount
0x180032587  mov     rcx, r15; String1
0x18003258a  call    wcsncmp_0
0x18003258f  test    eax, eax
0x180032591  jz      loc_18003265B
0x180032597  mov     rdi, [rdi]
0x18003259a  test    rdi, rdi
0x18003259d  jnz     short loc_180032580
0x18003259f  cmp     rbx, r14
0x1800325a2  jz      short loc_1800325CF
0x1800325a4  test    dword ptr [rbx+1Ch], 200h
0x1800325ab  jz      short loc_1800325CF
0x1800325ad  cmp     byte ptr [rbx+19h], 3
0x1800325b1  jb      short loc_1800325CF
0x1800325b3  mov     rcx, [rbx+10h]
0x1800325b7  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x1800325be  mov     edx, 31h ; '1'
0x1800325c3  call    WPP_SF_
0x1800325c8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800325cf  mov     rdi, [rsp+88h]
0x1800325d7  mov     rcx, [rbp+57h+arg_18]
0x1800325db  mov     r15, [rsp+0A0h+var_30]
0x1800325e0  mov     r12, [rsp+0A0h+var_20]
0x1800325e8  test    rcx, rcx
0x1800325eb  jz      short loc_180032600
0x1800325ed  call    cs:__imp_FWFreeFirewallRules
0x1800325f4  nop     dword ptr [rax+rax+00h]
0x1800325f9  mov     rbx, cs:WPP_GLOBAL_Control
0x180032600  mov     rcx, [rbp+57h+arg_10]
0x180032604  test    rcx, rcx
0x180032607  jz      short loc_18003261C
0x180032609  call    cs:__imp_FWClosePolicyStore
0x180032610  nop     dword ptr [rax+rax+00h]
0x180032615  mov     rbx, cs:WPP_GLOBAL_Control
0x18003261c  cmp     rbx, r14
0x18003261f  mov     r14, [rsp+0A0h+var_28]
0x180032624  jz      short loc_18003264D
0x180032626  test    dword ptr [rbx+1Ch], 200h
0x18003262d  jz      short loc_18003264D
0x18003262f  cmp     byte ptr [rbx+19h], 6
0x180032633  jb      short loc_18003264D
0x180032635  mov     rcx, [rbx+10h]
0x180032639  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180032640  mov     edx, 32h ; '2'
0x180032645  mov     r9d, esi
0x180032648  call    WPP_SF_d
0x18003264d  mov     eax, esi
0x18003264f  add     rsp, 90h
0x180032656  pop     rsi
0x180032657  pop     rbx
0x180032658  pop     rbp
0x180032659  retn
0x18003265b  mov     rdx, [rdi+10h]
0x18003265f  mov     rcx, [rbp+57h+arg_10]
0x180032663  call    cs:__imp_FWDeleteFirewallRule
0x18003266a  nop     dword ptr [rax+rax+00h]
0x18003266f  mov     edi, eax
0x180032671  test    eax, eax
0x180032673  jz      loc_1800325C8
0x180032679  mov     rbx, cs:WPP_GLOBAL_Control
0x180032680  cmp     rbx, r14
0x180032683  jz      short loc_1800326B3
0x180032685  test    dword ptr [rbx+1Ch], 200h
0x18003268c  jz      short loc_1800326B3
0x18003268e  cmp     byte ptr [rbx+19h], 2
0x180032692  jb      short loc_1800326B3
0x180032694  mov     rcx, [rbx+10h]
0x180032698  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18003269f  mov     edx, 30h ; '0'
0x1800326a4  mov     r9d, eax
0x1800326a7  call    WPP_SF_d
0x1800326ac  mov     rbx, cs:WPP_GLOBAL_Control
0x1800326b3  test    edi, edi
0x1800326b5  jg      short loc_1800326BE
0x1800326b7  mov     esi, edi
0x1800326b9  jmp     loc_1800325CF
0x1800326be  movzx   esi, di
0x1800326c1  or      esi, 80070000h
0x1800326c7  jmp     loc_1800325CF
```
