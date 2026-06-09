# RasRemoveNrptRules

- ea: `0x18005eb98`
- end: `0x18005ed85`
- name: `RasRemoveNrptRules`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004bd90`

## callees

- `0x180005e0c`
- `0x18002a194`
- `0x18005eb98`
- `0x18005ed8c`

## import_xrefs

- `DNSAPI!DnsRemoveNrptRule` at `0x18005eca9`
- `DNSAPI!DnsRemoveNrptRule` at `0x18005eca9`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x18005ed28`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x18005ed28`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x18005ec12`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x18005ec12`

## pseudocode

```c
__int64 __fastcall RasRemoveNrptRules(_QWORD *a1, __int64 a2, __int64 a3)
{
  FwPolicy2 *v4; // rcx
  unsigned int NrptRuleNamesList; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // edi
  _QWORD *v10; // rsi
  int i; // ebp
  const wchar_t *v12; // rcx
  size_t v13; // r8
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+18h] BYREF

  v16 = a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, a3, 1, 1);
    v4 = WPP_GLOBAL_Control;
  }
  v15 = 0;
  v16 = 0;
  if ( a1 )
  {
    NrptRuleNamesList = DnsGetNrptRuleNamesList(&v15, &v16);
    v6 = NrptRuleNamesList;
    if ( NrptRuleNamesList )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_33:
        if ( v15 )
        {
          DnsFreeNrptRuleNamesList(&v15, v16);
          v4 = WPP_GLOBAL_Control;
        }
        goto LABEL_35;
      }
      v7 = 39;
      v8 = NrptRuleNamesList;
      goto LABEL_31;
    }
    v9 = 0;
    while ( 2 )
    {
      if ( v9 >= v16 )
        goto LABEL_32;
      v10 = a1;
      for ( i = 0; ; i = 1 )
      {
        if ( !v10 || i )
          goto LABEL_21;
        v12 = (const wchar_t *)v10[6];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( !wcsnicmp(v12, *(const wchar_t **)(v15 + 8LL * v9), v13) )
          break;
        v10 = (_QWORD *)*v10;
      }
      v6 = DnsRemoveNrptRule(*(_QWORD *)(v15 + 8LL * v9));
      if ( !v6 )
      {
LABEL_21:
        ++v9;
        continue;
      }
      break;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v7 = 40;
LABEL_30:
    v8 = v6;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v4 + 2), v7, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v8);
LABEL_32:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v6 = 87;
  if ( v4 == (FwPolicy2 *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v7 = 38;
    goto LABEL_30;
  }
LABEL_35:
  if ( v4 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v4 + 2), 41, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18005eb98  mov     rax, rsp
0x18005eb9b  mov     [rax+10h], rbx
0x18005eb9f  mov     [rax+20h], rbp
0x18005eba3  mov     [rax+18h], r8d
0x18005eba7  push    rsi
0x18005eba8  push    rdi
0x18005eba9  push    r12
0x18005ebab  push    r14
0x18005ebad  push    r15
0x18005ebaf  sub     rsp, 30h
0x18005ebb3  mov     r14, rcx
0x18005ebb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebbd  lea     rdi, WPP_GLOBAL_Control
0x18005ebc4  cmp     rcx, rdi
0x18005ebc7  jz      short loc_18005EBF2
0x18005ebc9  test    byte ptr [rcx+1Ch], 1
0x18005ebcd  jz      short loc_18005EBF2
0x18005ebcf  cmp     byte ptr [rcx+19h], 6
0x18005ebd3  jb      short loc_18005EBF2
0x18005ebd5  mov     rcx, [rcx+10h]
0x18005ebd9  mov     edx, 25h ; '%'
0x18005ebde  mov     byte ptr [rax-38h], 1
0x18005ebe2  lea     r9d, [rdx-24h]
0x18005ebe6  call    WPP_SF_dc
0x18005ebeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebf2  xor     r12d, r12d
0x18005ebf5  mov     [rsp+58h+arg_0], r12
0x18005ebfa  mov     [rsp+58h+arg_10], r12d
0x18005ebff  test    r14, r14
0x18005ec02  jz      loc_18005ECE5
0x18005ec08  lea     rdx, [rsp+58h+arg_10]
0x18005ec0d  lea     rcx, [rsp+58h+arg_0]
0x18005ec12  call    cs:__imp_DnsGetNrptRuleNamesList
0x18005ec19  nop     dword ptr [rax+rax+00h]
0x18005ec1e  mov     ebx, eax
0x18005ec20  test    eax, eax
0x18005ec22  jz      short loc_18005EC55
0x18005ec24  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec2b  cmp     rcx, rdi
0x18005ec2e  jz      loc_18005ED18
0x18005ec34  test    byte ptr [rcx+1Ch], 1
0x18005ec38  jz      loc_18005ED18
0x18005ec3e  cmp     byte ptr [rcx+19h], 2
0x18005ec42  jb      loc_18005ED18
0x18005ec48  lea     edx, [r12+27h]
0x18005ec4d  mov     r9d, eax
0x18005ec50  jmp     loc_18005ED01
0x18005ec55  mov     edi, r12d
0x18005ec58  cmp     edi, [rsp+58h+arg_10]
0x18005ec5c  jnb     loc_18005ED11
0x18005ec62  mov     rsi, r14
0x18005ec65  mov     ebp, r12d
0x18005ec68  test    rsi, rsi
0x18005ec6b  jz      short loc_18005ECBB
0x18005ec6d  cmp     ebp, 1
0x18005ec70  jnb     short loc_18005ECBB
0x18005ec72  mov     rcx, [rsi+30h]; String1
0x18005ec76  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005ec7a  mov     r15d, edi
0x18005ec7d  inc     r8; MaxCount
0x18005ec80  cmp     [rcx+r8*2], r12w
0x18005ec85  jnz     short loc_18005EC7D
0x18005ec87  mov     rdx, [rsp+58h+arg_0]
0x18005ec8c  mov     rdx, [rdx+r15*8]; String2
0x18005ec90  call    _wcsnicmp
0x18005ec95  test    eax, eax
0x18005ec97  jz      short loc_18005ECA0
0x18005ec99  mov     rsi, [rsi]
0x18005ec9c  inc     ebp
0x18005ec9e  jmp     short loc_18005EC68
0x18005eca0  mov     rcx, [rsp+58h+arg_0]
0x18005eca5  mov     rcx, [rcx+r15*8]
0x18005eca9  call    cs:__imp_DnsRemoveNrptRule
0x18005ecb0  nop     dword ptr [rax+rax+00h]
0x18005ecb5  mov     ebx, eax
0x18005ecb7  test    eax, eax
0x18005ecb9  jnz     short loc_18005ECBF
0x18005ecbb  inc     edi
0x18005ecbd  jmp     short loc_18005EC58
0x18005ecbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ecc6  lea     rax, WPP_GLOBAL_Control
0x18005eccd  cmp     rcx, rax
0x18005ecd0  jz      short loc_18005ED18
0x18005ecd2  test    byte ptr [rcx+1Ch], 1
0x18005ecd6  jz      short loc_18005ED18
0x18005ecd8  cmp     byte ptr [rcx+19h], 2
0x18005ecdc  jb      short loc_18005ED18
0x18005ecde  mov     edx, 28h ; '('
0x18005ece3  jmp     short loc_18005ECFE
0x18005ece5  mov     ebx, 57h ; 'W'
0x18005ecea  cmp     rcx, rdi
0x18005eced  jz      short loc_18005ED6B
0x18005ecef  test    byte ptr [rcx+1Ch], 1
0x18005ecf3  jz      short loc_18005ED42
0x18005ecf5  cmp     byte ptr [rcx+19h], 2
0x18005ecf9  jb      short loc_18005ED42
0x18005ecfb  lea     edx, [rbx-31h]
0x18005ecfe  mov     r9d, ebx
0x18005ed01  mov     rcx, [rcx+10h]
0x18005ed05  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x18005ed0c  call    WPP_SF_d
0x18005ed11  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed18  cmp     [rsp+58h+arg_0], r12
0x18005ed1d  jz      short loc_18005ED3B
0x18005ed1f  mov     edx, [rsp+58h+arg_10]
0x18005ed23  lea     rcx, [rsp+58h+arg_0]
0x18005ed28  call    cs:__imp_DnsFreeNrptRuleNamesList
0x18005ed2f  nop     dword ptr [rax+rax+00h]
0x18005ed34  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed3b  lea     rdi, WPP_GLOBAL_Control
0x18005ed42  cmp     rcx, rdi
0x18005ed45  jz      short loc_18005ED6B
0x18005ed47  test    byte ptr [rcx+1Ch], 1
0x18005ed4b  jz      short loc_18005ED6B
0x18005ed4d  cmp     byte ptr [rcx+19h], 6
0x18005ed51  jb      short loc_18005ED6B
0x18005ed53  mov     rcx, [rcx+10h]
0x18005ed57  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x18005ed5e  mov     edx, 29h ; ')'
0x18005ed63  mov     r9d, ebx
0x18005ed66  call    WPP_SF_d
0x18005ed6b  mov     rbp, [rsp+58h+arg_18]
0x18005ed70  mov     eax, ebx
0x18005ed72  mov     rbx, [rsp+58h+arg_8]
0x18005ed77  add     rsp, 30h
0x18005ed7b  pop     r15
0x18005ed7d  pop     r14
0x18005ed7f  pop     r12
0x18005ed81  pop     rdi
0x18005ed82  pop     rsi
0x18005ed83  retn
```
