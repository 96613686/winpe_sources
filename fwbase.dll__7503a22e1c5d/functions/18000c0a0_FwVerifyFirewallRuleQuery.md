# FwVerifyFirewallRuleQuery

- ea: `0x18000c0a0`
- end: `0x18000c256`
- name: `FwVerifyFirewallRuleQuery`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000c0a0`
- `0x18000c25c`
- `0x18000ccd4`
- `0x180017d1c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c15d`
- `ntdll!EtwEventWrite` at `0x18000c24b`
- `ntdll!EtwEventWrite` at `0x18000c15d`
- `ntdll!EtwEventWrite` at `0x18000c24b`

## pseudocode

```c
__int64 __fastcall FwVerifyFirewallRuleQuery(__int16 a1, __int64 a2)
{
  _BYTE *v4; // rcx
  unsigned int Generics; // eax
  unsigned int v6; // edi
  unsigned int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_VerifyFirewallRuleQuery, 0, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v7 = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_11;
    v9 = 15;
    v10 = 87;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v4 + 2), v9, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids, v10);
    goto LABEL_11;
  }
  if ( (unsigned __int16)(a1 - 512) > 0x21u )
  {
    v10 = 1306;
    v7 = 1306;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_11;
    v9 = 16;
    goto LABEL_29;
  }
  if ( *(_WORD *)a2 < 0x20Au )
  {
    v10 = 1306;
    v7 = 1306;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_11;
    v9 = 17;
    goto LABEL_29;
  }
  Generics = Int_FWValidateQueryGenerics((struct _tag_FW_QUERY *)a2, 0, (enum _tag_FW_RULE_STATUS *)(a2 + 16));
  v4 = WPP_GLOBAL_Control;
  v6 = Generics;
  if ( Generics
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, Generics);
    v4 = WPP_GLOBAL_Control;
    v7 = v6;
  }
  else
  {
    v7 = Generics;
    if ( !Generics )
      goto LABEL_11;
  }
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
  {
    v9 = 18;
    v10 = v6;
    goto LABEL_29;
  }
LABEL_11:
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_VerifyFirewallRuleQuery, 0, 0);
  return v7;
}

```

## disassembly

```asm
0x18000c0a0  push    rbx
0x18000c0a2  push    rbp
0x18000c0a3  push    rsi
0x18000c0a4  push    rdi
0x18000c0a5  sub     rsp, 28h
0x18000c0a9  movzx   edi, cx
0x18000c0ac  mov     rbx, rdx
0x18000c0af  mov     rcx, cs:g_Provider
0x18000c0b6  test    rcx, rcx
0x18000c0b9  jnz     loc_18000C150
0x18000c0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0c6  lea     rsi, WPP_GLOBAL_Control
0x18000c0cd  lea     rbp, WPP_d8cd17f01e9932754325234d8cff0119_Traceguids
0x18000c0d4  cmp     rcx, rsi
0x18000c0d7  jz      short loc_18000C0E3
0x18000c0d9  test    byte ptr [rcx+1Ch], 8
0x18000c0dd  jnz     loc_18000C168
0x18000c0e3  test    rbx, rbx
0x18000c0e6  jz      loc_18000C185
0x18000c0ec  mov     eax, 200h
0x18000c0f1  sub     di, ax
0x18000c0f4  cmp     di, 21h ; '!'
0x18000c0f8  ja      loc_18000C1A0
0x18000c0fe  mov     eax, 20Ah
0x18000c103  cmp     [rbx], ax
0x18000c106  jb      loc_18000C1BB
0x18000c10c  lea     r8, [rbx+10h]; enum _tag_FW_RULE_STATUS *
0x18000c110  xor     edx, edx; struct _FW_QUERY_PARTIAL_DATA_CTX *
0x18000c112  mov     rcx, rbx; struct _tag_FW_QUERY *
0x18000c115  call    ?Int_FWValidateQueryGenerics@@YAKPEAU_tag_FW_QUERY@@PEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FWValidateQueryGenerics(_tag_FW_QUERY *,_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)
0x18000c11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c121  mov     edi, eax
0x18000c123  test    eax, eax
0x18000c125  jnz     loc_18000C1DE
0x18000c12b  mov     ebx, edi
0x18000c12d  test    edi, edi
0x18000c12f  jnz     loc_18000C212
0x18000c135  mov     rcx, cs:g_Provider
0x18000c13c  test    rcx, rcx
0x18000c13f  jnz     loc_18000C23E
0x18000c145  mov     eax, ebx
0x18000c147  add     rsp, 28h
0x18000c14b  pop     rdi
0x18000c14c  pop     rsi
0x18000c14d  pop     rbp
0x18000c14e  pop     rbx
0x18000c14f  retn
0x18000c150  xor     r9d, r9d
0x18000c153  lea     rdx, MPS_CLNT_API_Enter_VerifyFirewallRuleQuery
0x18000c15a  xor     r8d, r8d
0x18000c15d  call    cs:__imp_EtwEventWrite
0x18000c163  jmp     loc_18000C0BF
0x18000c168  mov     rcx, [rcx+10h]
0x18000c16c  mov     edx, 0Eh
0x18000c171  mov     r8, rbp
0x18000c174  call    WPP_SF_
0x18000c179  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c180  jmp     loc_18000C0E3
0x18000c185  mov     ebx, 57h ; 'W'
0x18000c18a  cmp     rcx, rsi
0x18000c18d  jz      short loc_18000C135
0x18000c18f  test    byte ptr [rcx+1Ch], 1
0x18000c193  jz      short loc_18000C135
0x18000c195  lea     edx, [rbx-48h]
0x18000c198  mov     r9d, ebx
0x18000c19b  jmp     loc_18000C22D
0x18000c1a0  mov     r9d, 51Ah
0x18000c1a6  mov     ebx, r9d
0x18000c1a9  cmp     rcx, rsi
0x18000c1ac  jz      short loc_18000C135
0x18000c1ae  test    byte ptr [rcx+1Ch], 1
0x18000c1b2  jz      short loc_18000C135
0x18000c1b4  mov     edx, 10h
0x18000c1b9  jmp     short loc_18000C22D
0x18000c1bb  mov     r9d, 51Ah
0x18000c1c1  mov     ebx, r9d
0x18000c1c4  cmp     rcx, rsi
0x18000c1c7  jz      loc_18000C135
0x18000c1cd  test    byte ptr [rcx+1Ch], 1
0x18000c1d1  jz      loc_18000C135
0x18000c1d7  mov     edx, 11h
0x18000c1dc  jmp     short loc_18000C22D
0x18000c1de  cmp     rcx, rsi
0x18000c1e1  jz      loc_18000C12B
0x18000c1e7  test    byte ptr [rcx+1Ch], 1
0x18000c1eb  jz      loc_18000C12B
0x18000c1f1  mov     rcx, [rcx+10h]
0x18000c1f5  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000c1fc  mov     edx, 0D0h
0x18000c201  mov     r9d, edi
0x18000c204  call    WPP_SF_d
0x18000c209  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c210  mov     ebx, edi
0x18000c212  cmp     rcx, rsi
0x18000c215  jz      loc_18000C135
0x18000c21b  test    byte ptr [rcx+1Ch], 1
0x18000c21f  jz      loc_18000C135
0x18000c225  mov     edx, 12h
0x18000c22a  mov     r9d, edi
0x18000c22d  mov     rcx, [rcx+10h]
0x18000c231  mov     r8, rbp
0x18000c234  call    WPP_SF_d
0x18000c239  jmp     loc_18000C135
0x18000c23e  xor     r9d, r9d
0x18000c241  lea     rdx, MPS_CLNT_API_Exit_VerifyFirewallRuleQuery
0x18000c248  xor     r8d, r8d
0x18000c24b  call    cs:__imp_EtwEventWrite
0x18000c251  jmp     loc_18000C145
```
