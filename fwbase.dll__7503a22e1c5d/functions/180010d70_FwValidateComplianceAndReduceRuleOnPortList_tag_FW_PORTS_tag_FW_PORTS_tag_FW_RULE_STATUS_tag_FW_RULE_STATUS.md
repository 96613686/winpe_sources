# FwValidateComplianceAndReduceRuleOnPortList(_tag_FW_PORTS *,_tag_FW_PORTS *,_tag_FW_RULE_STATUS *,_tag_FW_RULE_STATUS *)

- ea: `0x180010d70`
- end: `0x180010e41`
- name: `?FwValidateComplianceAndReduceRuleOnPortList@@YAKPEAU_tag_FW_PORTS@@0PEAW4_tag_FW_RULE_STATUS@@1@Z`
- size: `209`
- prototype: `unsigned int __fastcall(struct _tag_FW_PORTS *, struct _tag_FW_PORTS *, enum _tag_FW_RULE_STATUS *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fdc0`
- `0x180013b60`

## callees

- `0x18000ccd4`
- `0x180010d70`
- `0x180010e48`
- `0x18002ce58`

## pseudocode

```c
__int64 __fastcall FwValidateComplianceAndReduceRuleOnPortList(
        struct _tag_FW_PORTS *a1,
        struct _tag_FW_PORTS *a2,
        enum _tag_FW_RULE_STATUS *a3,
        enum _tag_FW_RULE_STATUS *a4)
{
  unsigned int v8; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( a1 && a2 )
  {
    v8 = 0;
    if ( (unsigned int)FwHasRangesInPortList(a1) || (unsigned int)FwHasRangesInPortList(a2) )
    {
      if ( !a3 )
      {
        FwRemoveRangesFromPortList(a1);
        FwRemoveRangesFromPortList(a2);
        *(_DWORD *)a4 = 0x20000;
        return v8;
      }
      *(_DWORD *)a3 = 1048764;
      v8 = 87;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 302;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v8 = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 301;
LABEL_9:
      WPP_SF_d(v10[2], v11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180010d70  push    rbx
0x180010d72  push    rsi
0x180010d73  push    rdi
0x180010d74  push    r14
0x180010d76  push    r15
0x180010d78  sub     rsp, 20h
0x180010d7c  mov     r15, r9
0x180010d7f  mov     r14, r8
0x180010d82  mov     rdi, rdx
0x180010d85  mov     rsi, rcx
0x180010d88  test    rcx, rcx
0x180010d8b  jz      short loc_180010DB7
0x180010d8d  test    rdx, rdx
0x180010d90  jz      short loc_180010DB7
0x180010d92  xor     ebx, ebx
0x180010d94  call    ?FwHasRangesInPortList@@YAHPEBU_tag_FW_PORTS@@@Z; FwHasRangesInPortList(_tag_FW_PORTS const *)
0x180010d99  test    eax, eax
0x180010d9b  jnz     short loc_180010DF0
0x180010d9d  mov     rcx, rdi; struct _tag_FW_PORTS *
0x180010da0  call    ?FwHasRangesInPortList@@YAHPEBU_tag_FW_PORTS@@@Z; FwHasRangesInPortList(_tag_FW_PORTS const *)
0x180010da5  test    eax, eax
0x180010da7  jnz     short loc_180010DF0
0x180010da9  mov     eax, ebx
0x180010dab  add     rsp, 20h
0x180010daf  pop     r15
0x180010db1  pop     r14
0x180010db3  pop     rdi
0x180010db4  pop     rsi
0x180010db5  pop     rbx
0x180010db6  retn
0x180010db7  mov     r9d, 57h ; 'W'
0x180010dbd  mov     ebx, r9d
0x180010dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dc7  lea     rax, WPP_GLOBAL_Control
0x180010dce  cmp     rcx, rax
0x180010dd1  jz      short loc_180010DA9
0x180010dd3  test    byte ptr [rcx+1Ch], 1
0x180010dd7  jz      short loc_180010DA9
0x180010dd9  mov     edx, 12Dh
0x180010dde  mov     rcx, [rcx+10h]
0x180010de2  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180010de9  call    WPP_SF_d
0x180010dee  jmp     short loc_180010DA9
0x180010df0  test    r14, r14
0x180010df3  jz      short loc_180010E25
0x180010df5  mov     r9d, 57h ; 'W'
0x180010dfb  mov     dword ptr [r14], 1000BCh
0x180010e02  mov     ebx, r9d
0x180010e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e0c  lea     rax, WPP_GLOBAL_Control
0x180010e13  cmp     rcx, rax
0x180010e16  jz      short loc_180010DA9
0x180010e18  test    byte ptr [rcx+1Ch], 1
0x180010e1c  jz      short loc_180010DA9
0x180010e1e  mov     edx, 12Eh
0x180010e23  jmp     short loc_180010DDE
0x180010e25  mov     rcx, rsi; struct _tag_FW_PORTS *
0x180010e28  call    ?FwRemoveRangesFromPortList@@YAXPEAU_tag_FW_PORTS@@@Z; FwRemoveRangesFromPortList(_tag_FW_PORTS *)
0x180010e2d  mov     rcx, rdi; struct _tag_FW_PORTS *
0x180010e30  call    ?FwRemoveRangesFromPortList@@YAXPEAU_tag_FW_PORTS@@@Z; FwRemoveRangesFromPortList(_tag_FW_PORTS *)
0x180010e35  mov     dword ptr [r15], 20000h
0x180010e3c  jmp     loc_180010DA9
```
