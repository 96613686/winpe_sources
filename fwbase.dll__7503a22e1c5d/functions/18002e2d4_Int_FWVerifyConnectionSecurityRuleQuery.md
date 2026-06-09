# Int_FWVerifyConnectionSecurityRuleQuery

- ea: `0x18002e2d4`
- end: `0x18002e371`
- name: `Int_FWVerifyConnectionSecurityRuleQuery`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c840`

## callees

- `0x18000c25c`
- `0x18000ccd4`
- `0x180013484`
- `0x18002e2d4`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyConnectionSecurityRuleQuery(
        __int64 a1,
        struct _tag_FW_QUERY *a2,
        enum _tag_FW_RULE_STATUS *a3)
{
  unsigned int Generics; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  Generics = Int_FWValidateQueryGenerics(a2, (struct _FW_QUERY_PARTIAL_DATA_CTX *)&v8, a3);
  if ( Generics )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 213;
LABEL_9:
      WPP_SF_d(v5[2], v6, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, Generics);
    }
  }
  else
  {
    Generics = Int_FWValidateConnectionSecurityRuleQueryMatchKeys((struct _FW_QUERY_PARTIAL_DATA_CTX *)&v8, a3);
    if ( Generics )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 214;
        goto LABEL_9;
      }
    }
  }
  return Generics;
}

```

## disassembly

```asm
0x18002e2d4  mov     rax, rsp
0x18002e2d7  mov     [rax+10h], rbx
0x18002e2db  mov     [rax+8], cx
0x18002e2df  push    rdi
0x18002e2e0  sub     rsp, 20h
0x18002e2e4  mov     rcx, rdx; struct _tag_FW_QUERY *
0x18002e2e7  mov     dword ptr [rax+8], 0
0x18002e2ee  lea     rdx, [rax+8]; struct _FW_QUERY_PARTIAL_DATA_CTX *
0x18002e2f2  mov     rdi, r8
0x18002e2f5  call    ?Int_FWValidateQueryGenerics@@YAKPEAU_tag_FW_QUERY@@PEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FWValidateQueryGenerics(_tag_FW_QUERY *,_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)
0x18002e2fa  mov     ebx, eax
0x18002e2fc  test    eax, eax
0x18002e2fe  jz      short loc_18002E320
0x18002e300  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e307  lea     rax, WPP_GLOBAL_Control
0x18002e30e  cmp     rcx, rax
0x18002e311  jz      short loc_18002E364
0x18002e313  test    byte ptr [rcx+1Ch], 1
0x18002e317  jz      short loc_18002E364
0x18002e319  mov     edx, 0D5h
0x18002e31e  jmp     short loc_18002E351
0x18002e320  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x18002e323  lea     rcx, [rsp+28h+arg_0]; struct _FW_QUERY_PARTIAL_DATA_CTX *
0x18002e328  call    ?Int_FWValidateConnectionSecurityRuleQueryMatchKeys@@YAKPEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FWValidateConnectionSecurityRuleQueryMatchKeys(_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)
0x18002e32d  mov     ebx, eax
0x18002e32f  test    eax, eax
0x18002e331  jz      short loc_18002E364
0x18002e333  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e33a  lea     rax, WPP_GLOBAL_Control
0x18002e341  cmp     rcx, rax
0x18002e344  jz      short loc_18002E364
0x18002e346  test    byte ptr [rcx+1Ch], 1
0x18002e34a  jz      short loc_18002E364
0x18002e34c  mov     edx, 0D6h
0x18002e351  mov     rcx, [rcx+10h]
0x18002e355  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002e35c  mov     r9d, ebx
0x18002e35f  call    WPP_SF_d
0x18002e364  mov     eax, ebx
0x18002e366  mov     rbx, [rsp+28h+arg_8]
0x18002e36b  add     rsp, 20h
0x18002e36f  pop     rdi
0x18002e370  retn
```
