# GmsapAddGMSA(ldap *,ushort const *,_UNICODE_STRING const *,_tagCredFetchInt)

- ea: `0x180002114`
- end: `0x180002378`
- name: `?GmsapAddGMSA@@YAJPEAUldap@@PEBGPEBU_UNICODE_STRING@@W4_tagCredFetchInt@@@Z`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005380`

## callees

- `0x180002114`
- `0x1800036c0`
- `0x180006280`
- `0x1800062b0`
- `0x180006f68`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180002211`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180002211`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000232a`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000232a`

## pseudocode

```c
__int64 __fastcall GmsapAddGMSA(LDAP *a1, __int64 a2, __int64 a3)
{
  _UNKNOWN **v5; // rcx
  __int64 v6; // rdx
  int SingleAttribute; // eax
  unsigned int v8; // ebx
  int v9; // eax
  USHORT v10; // dx
  int v11; // r9d
  int v13; // [rsp+A0h] [rbp+18h] BYREF

  v13 = 0;
  v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x66u, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( !a3 || (v6 = *(_QWORD *)(a3 + 8)) == 0 || *(_WORD *)(a3 + 2) <= 2u )
  {
    v8 = -1073741726;
    if ( v5 == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v5 + 28) & 4) == 0 )
      goto LABEL_24;
    v10 = 103;
    v11 = -1073741726;
LABEL_22:
    WPP_SF_D((TRACEHANDLE)v5[2], v10, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
    goto LABEL_23;
  }
  *(_WORD *)(v6 + 2 * ((unsigned __int64)*(unsigned __int16 *)(a3 + 2) >> 1) - 2) = 0;
  SingleAttribute = GmsapGetSingleAttribute(a1);
  v8 = SingleAttribute;
  if ( SingleAttribute >= 0 )
  {
    v9 = (*((__int64 (__fastcall **)(int *))&xmmword_18000B5C0 + 1))(&v13);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v8 = -1073740007;
      v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_24;
      v10 = 106;
      v11 = -1073740007;
    }
    else
    {
      v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_24;
      v10 = 105;
      v11 = v9;
    }
    goto LABEL_22;
  }
  v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x68u,
      &WPP_70b8577d707437755865c965214ce19a_Traceguids,
      SingleAttribute);
LABEL_23:
    v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_D((TRACEHANDLE)v5[2], 0x6Cu, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180002114  mov     rax, rsp
0x180002117  mov     [rax+8], rbx
0x18000211b  mov     [rax+10h], rbp
0x18000211f  push    rsi
0x180002120  push    rdi
0x180002121  push    r12
0x180002123  push    r13
0x180002125  push    r14
0x180002127  sub     rsp, 60h
0x18000212b  xor     edi, edi
0x18000212d  mov     dword ptr [rax+18h], 0
0x180002134  mov     [rax-38h], rdi
0x180002138  mov     r14d, r9d
0x18000213b  mov     rbp, r8
0x18000213e  mov     rbx, rdx
0x180002141  mov     rsi, rcx
0x180002144  mov     rcx, cs:WPP_GLOBAL_Control
0x18000214b  lea     r12, WPP_GLOBAL_Control
0x180002152  lea     r13, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002159  cmp     rcx, r12
0x18000215c  jz      short loc_18000217A
0x18000215e  test    byte ptr [rcx+1Ch], 8
0x180002162  jz      short loc_18000217A
0x180002164  mov     rcx, [rcx+10h]
0x180002168  lea     edx, [rdi+66h]
0x18000216b  mov     r8, r13
0x18000216e  call    WPP_SF_
0x180002173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000217a  test    rbp, rbp
0x18000217d  jz      loc_1800022F4
0x180002183  mov     rdx, [rbp+8]
0x180002187  test    rdx, rdx
0x18000218a  jz      loc_1800022F4
0x180002190  mov     eax, 2
0x180002195  cmp     ax, [rbp+2]
0x180002199  jnb     loc_1800022F4
0x18000219f  movzx   ecx, word ptr [rbp+2]
0x1800021a3  lea     r9, [rsp+88h+vals]
0x1800021a8  shr     rcx, 1
0x1800021ab  xor     eax, eax
0x1800021ad  mov     [rdx+rcx*2-2], ax
0x1800021b2  mov     rdx, rbx
0x1800021b5  mov     rcx, rsi; ld
0x1800021b8  call    GmsapGetSingleAttribute
0x1800021bd  mov     ebx, eax
0x1800021bf  test    eax, eax
0x1800021c1  jns     short loc_1800021FD
0x1800021c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021ca  cmp     rcx, r12
0x1800021cd  jz      short loc_1800021F3
0x1800021cf  test    byte ptr [rcx+1Ch], 4
0x1800021d3  jz      short loc_1800021F3
0x1800021d5  mov     rcx, [rcx+10h]
0x1800021d9  mov     edx, 68h ; 'h'
0x1800021de  mov     r9d, eax
0x1800021e1  mov     r8, r13
0x1800021e4  call    WPP_SF_D
0x1800021e9  mov     rdi, [rsp+88h+vals]
0x1800021ee  jmp     loc_18000231B
0x1800021f3  mov     rdi, [rsp+88h+vals]
0x1800021f8  jmp     loc_180002322
0x1800021fd  mov     rdi, [rsp+88h+vals]
0x180002202  xor     esi, esi
0x180002204  test    rdi, rdi
0x180002207  jz      short loc_18000221F
0x180002209  mov     rcx, [rdi]
0x18000220c  test    rcx, rcx
0x18000220f  jz      short loc_18000221F
0x180002211  call    cs:__imp__o__wtoi
0x180002218  nop     dword ptr [rax+rax+00h]
0x18000221d  mov     esi, eax
0x18000221f  mov     rax, qword ptr cs:xmmword_18000B5C0+8
0x180002226  lea     rcx, [rsp+88h+arg_10]
0x18000222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002233  mov     ebx, eax
0x180002235  test    eax, eax
0x180002237  jns     short loc_180002260
0x180002239  mov     rcx, cs:WPP_GLOBAL_Control
0x180002240  cmp     rcx, r12
0x180002243  jz      loc_180002322
0x180002249  test    byte ptr [rcx+1Ch], 4
0x18000224d  jz      loc_180002322
0x180002253  mov     edx, 69h ; 'i'
0x180002258  mov     r9d, eax
0x18000225b  jmp     loc_18000230F
0x180002260  test    esi, esi
0x180002262  jz      short loc_1800022D0
0x180002264  mov     eax, [rsp+88h+arg_10]
0x18000226b  test    eax, eax
0x18000226d  jz      short loc_1800022D0
0x18000226f  and     eax, esi
0x180002271  cmp     eax, esi
0x180002273  jnz     short loc_1800022D0
0x180002275  mov     [rsp+88h+var_48], 0
0x18000227e  xor     r9d, r9d
0x180002281  mov     [rsp+88h+var_50], 0
0x18000228a  mov     r8, rbp
0x18000228d  mov     [rsp+88h+var_58], 0
0x180002296  xor     edx, edx
0x180002298  mov     [rsp+88h+var_60], 0
0x1800022a1  mov     ecx, r14d
0x1800022a4  mov     [rsp+88h+var_68], 0
0x1800022ac  call    GmsapGetGroupMSAPassword
0x1800022b1  mov     ebx, eax
0x1800022b3  test    eax, eax
0x1800022b5  jns     short loc_18000231B
0x1800022b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022be  cmp     rcx, r12
0x1800022c1  jz      short loc_180002322
0x1800022c3  test    byte ptr [rcx+1Ch], 4
0x1800022c7  jz      short loc_180002322
0x1800022c9  mov     edx, 6Bh ; 'k'
0x1800022ce  jmp     short loc_180002258
0x1800022d0  mov     ebx, 0C0000719h
0x1800022d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022dc  cmp     rcx, r12
0x1800022df  jz      short loc_180002322
0x1800022e1  test    byte ptr [rcx+1Ch], 4
0x1800022e5  jz      short loc_180002322
0x1800022e7  mov     edx, 6Ah ; 'j'
0x1800022ec  mov     r9d, 0C0000719h
0x1800022f2  jmp     short loc_18000230F
0x1800022f4  mov     ebx, 0C0000062h
0x1800022f9  cmp     rcx, r12
0x1800022fc  jz      short loc_18000235C
0x1800022fe  test    byte ptr [rcx+1Ch], 4
0x180002302  jz      short loc_18000233D
0x180002304  mov     edx, 67h ; 'g'
0x180002309  mov     r9d, 0C0000062h
0x18000230f  mov     rcx, [rcx+10h]
0x180002313  mov     r8, r13
0x180002316  call    WPP_SF_D
0x18000231b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002322  test    rdi, rdi
0x180002325  jz      short loc_18000233D
0x180002327  mov     rcx, rdi; vals
0x18000232a  call    cs:__imp_ldap_value_freeW
0x180002331  nop     dword ptr [rax+rax+00h]
0x180002336  mov     rcx, cs:WPP_GLOBAL_Control
0x18000233d  cmp     rcx, r12
0x180002340  jz      short loc_18000235C
0x180002342  test    byte ptr [rcx+1Ch], 8
0x180002346  jz      short loc_18000235C
0x180002348  mov     rcx, [rcx+10h]
0x18000234c  mov     edx, 6Ch ; 'l'
0x180002351  mov     r9d, ebx
0x180002354  mov     r8, r13
0x180002357  call    WPP_SF_D
0x18000235c  lea     r11, [rsp+88h+var_28]
0x180002361  mov     eax, ebx
0x180002363  mov     rbx, [r11+30h]
0x180002367  mov     rbp, [r11+38h]
0x18000236b  mov     rsp, r11
0x18000236e  pop     r14
0x180002370  pop     r13
0x180002372  pop     r12
0x180002374  pop     rdi
0x180002375  pop     rsi
0x180002376  retn
```
