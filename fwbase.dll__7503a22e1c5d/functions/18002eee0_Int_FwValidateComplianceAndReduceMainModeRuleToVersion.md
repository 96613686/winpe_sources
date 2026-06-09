# Int_FwValidateComplianceAndReduceMainModeRuleToVersion

- ea: `0x18002eee0`
- end: `0x18002eff1`
- name: `Int_FwValidateComplianceAndReduceMainModeRuleToVersion`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002e7c0`

## callees

- `0x18000ccd4`
- `0x180017d1c`
- `0x18002eee0`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceMainModeRuleToVersion(__int64 a1, _DWORD *a2, unsigned __int16 a3)
{
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 v9; // ax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 353, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v6 = 0;
  if ( a3 >= 0x208u )
  {
    if ( a3 >= 0x218u )
      return v6;
  }
  else
  {
    if ( a2 )
    {
      *a2 = 0x40000;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 354;
LABEL_9:
        WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
        return v6;
      }
      return v6;
    }
    *(_DWORD *)(a1 + 256) = 0x40000;
  }
  v9 = *(_WORD *)(a1 + 208);
  if ( v9 >= 0x100u )
  {
    if ( !a2 )
    {
      *(_DWORD *)(a1 + 256) = 0x20000;
      *(_WORD *)(a1 + 208) = (unsigned __int8)v9;
      return v6;
    }
    if ( (v9 & 0x100) != 0 )
    {
      *a2 = 1049881;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 355;
        goto LABEL_9;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002eee0  push    rbx
0x18002eee2  push    rbp
0x18002eee3  push    rsi
0x18002eee4  push    rdi
0x18002eee5  push    r14
0x18002eee7  sub     rsp, 20h
0x18002eeeb  movzx   ebp, r8w
0x18002eeef  mov     rbx, rdx
0x18002eef2  mov     rdi, rcx
0x18002eef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eefc  lea     r14, WPP_GLOBAL_Control
0x18002ef03  cmp     rcx, r14
0x18002ef06  jz      short loc_18002EF23
0x18002ef08  test    byte ptr [rcx+1Ch], 8
0x18002ef0c  jz      short loc_18002EF23
0x18002ef0e  mov     rcx, [rcx+10h]
0x18002ef12  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002ef19  mov     edx, 161h
0x18002ef1e  call    WPP_SF_
0x18002ef23  xor     esi, esi
0x18002ef25  mov     eax, 208h
0x18002ef2a  cmp     bp, ax
0x18002ef2d  jnb     short loc_18002EF7E
0x18002ef2f  test    rbx, rbx
0x18002ef32  jz      short loc_18002EF72
0x18002ef34  lea     r9d, [rsi+57h]
0x18002ef38  mov     dword ptr [rbx], 40000h
0x18002ef3e  mov     esi, r9d
0x18002ef41  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef48  cmp     rcx, r14
0x18002ef4b  jz      loc_18002EFE4
0x18002ef51  test    byte ptr [rcx+1Ch], 1
0x18002ef55  jz      loc_18002EFE4
0x18002ef5b  mov     edx, 162h
0x18002ef60  mov     rcx, [rcx+10h]
0x18002ef64  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002ef6b  call    WPP_SF_d
0x18002ef70  jmp     short loc_18002EFE4
0x18002ef72  mov     dword ptr [rdi+100h], 40000h
0x18002ef7c  jmp     short loc_18002EF88
0x18002ef7e  mov     eax, 218h
0x18002ef83  cmp     bp, ax
0x18002ef86  jnb     short loc_18002EFE4
0x18002ef88  movzx   eax, word ptr [rdi+0D0h]
0x18002ef8f  mov     ecx, 100h
0x18002ef94  cmp     ax, cx
0x18002ef97  jb      short loc_18002EFE4
0x18002ef99  test    rbx, rbx
0x18002ef9c  jz      short loc_18002EFCB
0x18002ef9e  test    cx, ax
0x18002efa1  jz      short loc_18002EFE4
0x18002efa3  mov     r9d, 57h ; 'W'
0x18002efa9  mov     dword ptr [rbx], 100519h
0x18002efaf  mov     esi, r9d
0x18002efb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efb9  cmp     rcx, r14
0x18002efbc  jz      short loc_18002EFE4
0x18002efbe  test    byte ptr [rcx+1Ch], 1
0x18002efc2  jz      short loc_18002EFE4
0x18002efc4  mov     edx, 163h
0x18002efc9  jmp     short loc_18002EF60
0x18002efcb  mov     ecx, 0FFh
0x18002efd0  mov     dword ptr [rdi+100h], 20000h
0x18002efda  and     ax, cx
0x18002efdd  mov     [rdi+0D0h], ax
0x18002efe4  mov     eax, esi
0x18002efe6  add     rsp, 20h
0x18002efea  pop     r14
0x18002efec  pop     rdi
0x18002efed  pop     rsi
0x18002efee  pop     rbp
0x18002efef  pop     rbx
0x18002eff0  retn
```
