# Int_FWValidateQueryGenerics(_tag_FW_QUERY *,_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)

- ea: `0x18000c25c`
- end: `0x18000c358`
- name: `?Int_FWValidateQueryGenerics@@YAKPEAU_tag_FW_QUERY@@PEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z`
- size: `252`
- prototype: `unsigned int(struct _tag_FW_QUERY *, struct _FW_QUERY_PARTIAL_DATA_CTX *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c0a0`
- `0x18002e230`
- `0x18002e2d4`
- `0x18002e378`
- `0x18002ed24`

## callees

- `0x18000c25c`
- `0x18000c360`
- `0x18000ccd4`
- `0x18001e1d0`

## pseudocode

```c
__int64 __fastcall Int_FWValidateQueryGenerics(
        struct _tag_FW_QUERY *a1,
        struct _FW_QUERY_PARTIAL_DATA_CTX *a2,
        enum _tag_FW_RULE_STATUS *a3)
{
  _QWORD *v3; // rdi
  unsigned int Term; // ebx
  unsigned int i; // esi
  struct _tag_FW_QUERY_CONDITIONS *v9; // rcx
  _QWORD *v10; // rcx
  unsigned __int16 v12; // dx
  int v13; // [rsp+20h] [rbp-38h] BYREF

  v3 = (_QWORD *)((char *)a1 + 8);
  if ( *((_DWORD *)a1 + 1) )
  {
    if ( *v3 )
    {
      Term = 0;
      goto LABEL_4;
    }
LABEL_13:
    *(_DWORD *)a3 = 0x100000;
    Term = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 205;
LABEL_18:
      WPP_SF_d(v10[2], v12, (__int64)WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, Term);
    }
    return Term;
  }
  Term = 0;
  if ( *v3 )
    goto LABEL_13;
LABEL_4:
  for ( i = 0; i < *((_DWORD *)a1 + 1); ++i )
  {
    v9 = (struct _tag_FW_QUERY_CONDITIONS *)(*v3 + 16LL * i);
    v13 = 0;
    Term = Int_FWValidateQueryTerm(v9, (struct _FW_QUERY_PARTIAL_DATA_CTX *)&v13, a3);
    if ( Term )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 206;
        goto LABEL_18;
      }
      return Term;
    }
    if ( a2 )
      *(_DWORD *)a2 |= v13;
  }
  return Term;
}

```

## disassembly

```asm
0x18000c25c  mov     [rsp+arg_18], rbx
0x18000c261  push    rbp
0x18000c262  push    rsi
0x18000c263  push    rdi
0x18000c264  push    r14
0x18000c266  push    r15
0x18000c268  sub     rsp, 30h
0x18000c26c  mov     rax, cs:__security_cookie
0x18000c273  xor     rax, rsp
0x18000c276  mov     [rsp+58h+var_30], rax
0x18000c27b  cmp     dword ptr [rcx+4], 0
0x18000c27f  lea     rdi, [rcx+8]
0x18000c283  mov     r15, r8
0x18000c286  mov     rbp, rdx
0x18000c289  mov     r14, rcx
0x18000c28c  jz      short loc_18000C2FE
0x18000c28e  cmp     qword ptr [rdi], 0
0x18000c292  jz      short loc_18000C305
0x18000c294  xor     ebx, ebx
0x18000c296  xor     esi, esi
0x18000c298  cmp     esi, [r14+4]
0x18000c29c  jnb     short loc_18000C2DE
0x18000c29e  mov     ecx, esi
0x18000c2a0  lea     rdx, [rsp+58h+var_38]; struct _FW_QUERY_PARTIAL_DATA_CTX *
0x18000c2a5  shl     rcx, 4
0x18000c2a9  mov     r8, r15; enum _tag_FW_RULE_STATUS *
0x18000c2ac  add     rcx, [rdi]; struct _tag_FW_QUERY_CONDITIONS *
0x18000c2af  mov     [rsp+58h+var_38], 0
0x18000c2b7  call    ?Int_FWValidateQueryTerm@@YAKPEAU_tag_FW_QUERY_CONDITIONS@@PEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FWValidateQueryTerm(_tag_FW_QUERY_CONDITIONS *,_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)
0x18000c2bc  mov     ebx, eax
0x18000c2be  test    eax, eax
0x18000c2c0  jnz     short loc_18000C2CB
0x18000c2c2  test    rbp, rbp
0x18000c2c5  jnz     short loc_18000C32F
0x18000c2c7  inc     esi
0x18000c2c9  jmp     short loc_18000C298
0x18000c2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2d2  lea     rax, WPP_GLOBAL_Control
0x18000c2d9  cmp     rcx, rax
0x18000c2dc  jnz     short loc_18000C338
0x18000c2de  mov     eax, ebx
0x18000c2e0  mov     rcx, [rsp+58h+var_30]
0x18000c2e5  xor     rcx, rsp; StackCookie
0x18000c2e8  call    __security_check_cookie
0x18000c2ed  mov     rbx, [rsp+58h+arg_18]
0x18000c2f2  add     rsp, 30h
0x18000c2f6  pop     r15
0x18000c2f8  pop     r14
0x18000c2fa  pop     rdi
0x18000c2fb  pop     rsi
0x18000c2fc  pop     rbp
0x18000c2fd  retn
0x18000c2fe  xor     ebx, ebx
0x18000c300  cmp     [rdi], rbx
0x18000c303  jz      short loc_18000C296
0x18000c305  mov     dword ptr [r8], 100000h
0x18000c30c  mov     ebx, 57h ; 'W'
0x18000c311  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c318  lea     rax, WPP_GLOBAL_Control
0x18000c31f  cmp     rcx, rax
0x18000c322  jz      short loc_18000C2DE
0x18000c324  test    byte ptr [rcx+1Ch], 1
0x18000c328  jz      short loc_18000C2DE
0x18000c32a  lea     edx, [rbx+76h]
0x18000c32d  jmp     short loc_18000C343
0x18000c32f  mov     ecx, [rsp+58h+var_38]
0x18000c333  or      [rbp+0], ecx
0x18000c336  jmp     short loc_18000C2C7
0x18000c338  test    byte ptr [rcx+1Ch], 1
0x18000c33c  jz      short loc_18000C2DE
0x18000c33e  mov     edx, 0CEh
0x18000c343  mov     rcx, [rcx+10h]
0x18000c347  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000c34e  mov     r9d, ebx
0x18000c351  call    WPP_SF_d
0x18000c356  jmp     short loc_18000C2DE
```
