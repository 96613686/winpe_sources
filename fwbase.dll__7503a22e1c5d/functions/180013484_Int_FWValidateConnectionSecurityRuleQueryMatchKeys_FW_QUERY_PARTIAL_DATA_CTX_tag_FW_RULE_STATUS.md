# Int_FWValidateConnectionSecurityRuleQueryMatchKeys(_FW_QUERY_PARTIAL_DATA_CTX *,_tag_FW_RULE_STATUS *)

- ea: `0x180013484`
- end: `0x18001357f`
- name: `?Int_FWValidateConnectionSecurityRuleQueryMatchKeys@@YAKPEAU_FW_QUERY_PARTIAL_DATA_CTX@@PEAW4_tag_FW_RULE_STATUS@@@Z`
- size: `251`
- prototype: `unsigned int __fastcall(struct _FW_QUERY_PARTIAL_DATA_CTX *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d6e4`
- `0x18002e2d4`

## callees

- `0x18000ccd4`
- `0x180013484`

## pseudocode

```c
__int64 __fastcall Int_FWValidateConnectionSecurityRuleQueryMatchKeys(
        struct _FW_QUERY_PARTIAL_DATA_CTX *a1,
        enum _tag_FW_RULE_STATUS *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  v2 = *(_DWORD *)a1;
  if ( (*(_DWORD *)a1 & 0x10) != 0 )
  {
    *(_DWORD *)a2 = 0x100000;
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 209;
LABEL_17:
      WPP_SF_d(v4[2], v5, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    }
  }
  else if ( (v2 & 0x200) != 0 )
  {
    *(_DWORD *)a2 = 0x100000;
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 210;
      goto LABEL_17;
    }
  }
  else if ( (v2 & 0x800) != 0 )
  {
    *(_DWORD *)a2 = 0x100000;
    v3 = 87;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 211;
      goto LABEL_17;
    }
  }
  else
  {
    v3 = 0;
    if ( (v2 & 0x1000) != 0 )
    {
      *(_DWORD *)a2 = 0x100000;
      v3 = 87;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 212;
        goto LABEL_17;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180013484  push    rbx
0x180013486  sub     rsp, 20h
0x18001348a  mov     eax, [rcx]
0x18001348c  test    al, 10h
0x18001348e  jz      short loc_1800134C9
0x180013490  mov     r9d, 57h ; 'W'
0x180013496  mov     dword ptr [rdx], 100000h
0x18001349c  mov     ebx, r9d
0x18001349f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134a6  lea     rax, WPP_GLOBAL_Control
0x1800134ad  cmp     rcx, rax
0x1800134b0  jz      loc_180013577
0x1800134b6  test    byte ptr [rcx+1Ch], 1
0x1800134ba  jz      loc_180013577
0x1800134c0  lea     edx, [r9+7Ah]
0x1800134c4  jmp     loc_180013567
0x1800134c9  bt      eax, 9
0x1800134cd  jnb     short loc_180013501
0x1800134cf  mov     r9d, 57h ; 'W'
0x1800134d5  mov     dword ptr [rdx], 100000h
0x1800134db  mov     ebx, r9d
0x1800134de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134e5  lea     rax, WPP_GLOBAL_Control
0x1800134ec  cmp     rcx, rax
0x1800134ef  jz      loc_180013577
0x1800134f5  test    byte ptr [rcx+1Ch], 1
0x1800134f9  jz      short loc_180013577
0x1800134fb  lea     edx, [r9+7Bh]
0x1800134ff  jmp     short loc_180013567
0x180013501  bt      eax, 0Bh
0x180013505  jnb     short loc_180013535
0x180013507  mov     r9d, 57h ; 'W'
0x18001350d  mov     dword ptr [rdx], 100000h
0x180013513  mov     ebx, r9d
0x180013516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001351d  lea     rax, WPP_GLOBAL_Control
0x180013524  cmp     rcx, rax
0x180013527  jz      short loc_180013577
0x180013529  test    byte ptr [rcx+1Ch], 1
0x18001352d  jz      short loc_180013577
0x18001352f  lea     edx, [r9+7Ch]
0x180013533  jmp     short loc_180013567
0x180013535  xor     ebx, ebx
0x180013537  bt      eax, 0Ch
0x18001353b  jnb     short loc_180013577
0x18001353d  lea     r9d, [rbx+57h]
0x180013541  mov     dword ptr [rdx], 100000h
0x180013547  mov     ebx, r9d
0x18001354a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013551  lea     rax, WPP_GLOBAL_Control
0x180013558  cmp     rcx, rax
0x18001355b  jz      short loc_180013577
0x18001355d  test    byte ptr [rcx+1Ch], 1
0x180013561  jz      short loc_180013577
0x180013563  lea     edx, [r9+7Dh]
0x180013567  mov     rcx, [rcx+10h]
0x18001356b  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180013572  call    WPP_SF_d
0x180013577  mov     eax, ebx
0x180013579  add     rsp, 20h
0x18001357d  pop     rbx
0x18001357e  retn
```
