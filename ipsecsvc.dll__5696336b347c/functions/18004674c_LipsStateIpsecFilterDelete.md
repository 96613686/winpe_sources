# LipsStateIpsecFilterDelete

- ea: `0x18004674c`
- end: `0x18004686c`
- name: `LipsStateIpsecFilterDelete`
- size: `288`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180044b5c`
- `0x180046bdc`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004674c`
- `0x180046b28`
- `0x180048478`
- `0x180048570`
- `0x1800486b0`

## string_xrefs

- `0x18004684a`: `LipsStateIpsecFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecFilterDelete(__int64 a1, unsigned int a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  if ( !a1 || !a2 )
    return 0;
  v4 = LipsBfeTransactionBegin();
  if ( !v4 )
  {
    v4 = LipsStateIpsecFilterEnum(a1, 0, a2, LipsStateIpsecFilterDeleteCb);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_16;
      v6 = 33;
    }
    else
    {
      v4 = LipsBfeTransactionCommit();
      if ( !v4 )
        goto LABEL_17;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_16;
      v6 = 34;
    }
    WPP_SF_d(v5[2], v6, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v4);
LABEL_16:
    LipsBfeTransactionAbort();
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v4);
LABEL_17:
  LipsStateIpsecFilterEnum(a1, 0, a2, LipsStateIpsecFilterDestroyLegacyCb);
  if ( v4 )
    return LipsReportError(v4, (int)"LipsStateIpsecFilterDelete");
  return 0;
}

```

## disassembly

```asm
0x18004674c  mov     [rsp+arg_0], rbx
0x180046751  mov     [rsp+arg_8], rsi
0x180046756  push    rdi
0x180046757  sub     rsp, 20h
0x18004675b  mov     edi, edx
0x18004675d  mov     rsi, rcx
0x180046760  test    rcx, rcx
0x180046763  jz      loc_18004685A
0x180046769  test    edx, edx
0x18004676b  jz      loc_18004685A
0x180046771  call    LipsBfeTransactionBegin
0x180046776  mov     ebx, eax
0x180046778  test    eax, eax
0x18004677a  jz      short loc_1800467B7
0x18004677c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046783  lea     rax, WPP_GLOBAL_Control
0x18004678a  cmp     rcx, rax
0x18004678d  jz      loc_180046832
0x180046793  test    byte ptr [rcx+1Ch], 10h
0x180046797  jz      loc_180046832
0x18004679d  mov     rcx, [rcx+10h]
0x1800467a1  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x1800467a8  mov     edx, 20h ; ' '
0x1800467ad  mov     r9d, ebx
0x1800467b0  call    WPP_SF_d
0x1800467b5  jmp     short loc_180046832
0x1800467b7  lea     r9, LipsStateIpsecFilterDeleteCb
0x1800467be  mov     r8d, edi
0x1800467c1  xor     edx, edx
0x1800467c3  mov     rcx, rsi
0x1800467c6  call    LipsStateIpsecFilterEnum
0x1800467cb  mov     ebx, eax
0x1800467cd  test    eax, eax
0x1800467cf  jz      short loc_1800467F1
0x1800467d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800467d8  lea     rax, WPP_GLOBAL_Control
0x1800467df  cmp     rcx, rax
0x1800467e2  jz      short loc_18004682D
0x1800467e4  test    byte ptr [rcx+1Ch], 10h
0x1800467e8  jz      short loc_18004682D
0x1800467ea  mov     edx, 21h ; '!'
0x1800467ef  jmp     short loc_18004681A
0x1800467f1  call    LipsBfeTransactionCommit
0x1800467f6  mov     ebx, eax
0x1800467f8  test    eax, eax
0x1800467fa  jz      short loc_180046832
0x1800467fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180046803  lea     rax, WPP_GLOBAL_Control
0x18004680a  cmp     rcx, rax
0x18004680d  jz      short loc_18004682D
0x18004680f  test    byte ptr [rcx+1Ch], 10h
0x180046813  jz      short loc_18004682D
0x180046815  mov     edx, 22h ; '"'
0x18004681a  mov     rcx, [rcx+10h]
0x18004681e  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046825  mov     r9d, ebx
0x180046828  call    WPP_SF_d
0x18004682d  call    LipsBfeTransactionAbort
0x180046832  lea     r9, LipsStateIpsecFilterDestroyLegacyCb
0x180046839  mov     r8d, edi
0x18004683c  xor     edx, edx
0x18004683e  mov     rcx, rsi
0x180046841  call    LipsStateIpsecFilterEnum
0x180046846  test    ebx, ebx
0x180046848  jz      short loc_18004685A
0x18004684a  lea     rdx, aLipsstateipsec; "LipsStateIpsecFilterDelete"
0x180046851  mov     ecx, ebx
0x180046853  call    LipsReportError
0x180046858  jmp     short loc_18004685C
0x18004685a  xor     eax, eax
0x18004685c  mov     rbx, [rsp+28h+arg_0]
0x180046861  mov     rsi, [rsp+28h+arg_8]
0x180046866  add     rsp, 20h
0x18004686a  pop     rdi
0x18004686b  retn
```
