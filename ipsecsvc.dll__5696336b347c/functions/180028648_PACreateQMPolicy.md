# PACreateQMPolicy

- ea: `0x180028648`
- end: `0x18002887c`
- name: `PACreateQMPolicy`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009174`
- `0x18000cd90`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x18001cc18`
- `0x18002791c`
- `0x1800284c8`
- `0x180028648`

## pseudocode

```c
__int64 __fastcall PACreateQMPolicy(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r14
  _OWORD *v7; // rax
  _OWORD *v8; // rbx
  __int64 v9; // r9
  unsigned int v10; // edi
  _BYTE *v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 result; // rax
  int v17; // eax

  v3 = *(_QWORD *)(a1 + 104);
  if ( (*(_BYTE *)(a1 + 76) & 3) != 0
    && *(_DWORD *)(a2 + 56)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_23b1f3110213325002571ebd730d21df_Traceguids, 87);
  }
  v7 = IpsecAllocMem(0x30u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 8;
    v10 = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_33:
      *a3 = 0;
      return v10;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_28;
    v12 = 17;
    goto LABEL_27;
  }
  *v7 = *(_OWORD *)v3;
  v13 = IpsecAllocStr(*(unsigned __int16 **)(a2 + 16));
  *((_QWORD *)v8 + 2) = v13;
  if ( !v13 )
  {
    v9 = 8;
    v10 = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_28;
      v12 = 18;
      goto LABEL_27;
    }
    goto LABEL_32;
  }
  v14 = PACreateQMOffers(*(_DWORD *)(v3 + 48), *(_QWORD *)(v3 + 56), a2, (int)v8 + 32, (__int64)v8 + 40);
  v10 = v14;
  if ( v14 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_28;
      v12 = 19;
      v9 = v14;
      goto LABEL_27;
    }
    goto LABEL_32;
  }
  *((_DWORD *)v8 + 6) = 0;
  v15 = *(_QWORD *)(v3 + 32) - 0x11D16C3762F49E13LL;
  if ( *(_QWORD *)(v3 + 32) == 0x11D16C3762F49E13LL )
    v15 = *(_QWORD *)(v3 + 40) - 2736016518LL;
  if ( !v15 )
  {
    *((_DWORD *)v8 + 6) = 2;
    v10 = 50;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_23b1f3110213325002571ebd730d21df_Traceguids, 50);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (_BYTE *)&WPP_GLOBAL_Control )
      {
        if ( (v11[28] & 0x10) == 0 )
          goto LABEL_28;
        v12 = 21;
        v9 = 50;
LABEL_27:
        WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v9);
        v11 = WPP_GLOBAL_Control;
LABEL_28:
        if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[28] & 0x10) != 0 )
          WPP_SF__guid_(*((_QWORD *)v11 + 2), 22, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v3);
        if ( !v8 )
          goto LABEL_33;
      }
    }
LABEL_32:
    PAFreeQMPolicy(v8);
    goto LABEL_33;
  }
  v17 = 0;
  if ( (*(_BYTE *)(a1 + 76) & 3) != 0 )
  {
    v17 = 1;
    *((_DWORD *)v8 + 6) = 1;
  }
  if ( *(_DWORD *)(a2 + 56) )
    *((_DWORD *)v8 + 6) = v17 | 4;
  *((_DWORD *)v8 + 7) = 0;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180028648  push    rbx
0x18002864a  push    rbp
0x18002864b  push    rsi
0x18002864c  push    rdi
0x18002864d  push    r14
0x18002864f  push    r15
0x180028651  sub     rsp, 38h
0x180028655  test    byte ptr [rcx+4Ch], 3
0x180028659  lea     rax, WPP_GLOBAL_Control
0x180028660  mov     r14, [rcx+68h]
0x180028664  mov     r15, r8
0x180028667  mov     rsi, rdx
0x18002866a  mov     rbp, rcx
0x18002866d  jz      short loc_1800286A0
0x18002866f  cmp     dword ptr [rdx+38h], 0
0x180028673  jz      short loc_1800286A0
0x180028675  mov     rcx, cs:WPP_GLOBAL_Control
0x18002867c  cmp     rcx, rax
0x18002867f  jz      short loc_1800286A0
0x180028681  test    byte ptr [rcx+1Ch], 10h
0x180028685  jz      short loc_1800286A0
0x180028687  mov     rcx, [rcx+10h]
0x18002868b  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x180028692  mov     edx, 10h
0x180028697  lea     r9d, [rdx+47h]
0x18002869b  call    WPP_SF_d
0x1800286a0  mov     ecx, 30h ; '0'
0x1800286a5  call    IpsecAllocMem
0x1800286aa  mov     rbx, rax
0x1800286ad  test    rax, rax
0x1800286b0  jnz     short loc_1800286E2
0x1800286b2  lea     r9d, [rax+8]
0x1800286b6  mov     edi, r9d
0x1800286b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286c0  lea     rsi, WPP_GLOBAL_Control
0x1800286c7  cmp     rcx, rsi
0x1800286ca  jz      loc_18002883C
0x1800286d0  test    byte ptr [rcx+1Ch], 10h
0x1800286d4  jz      loc_18002880C
0x1800286da  lea     edx, [rax+11h]
0x1800286dd  jmp     loc_1800287F5
0x1800286e2  movups  xmm0, xmmword ptr [r14]
0x1800286e6  movdqu  xmmword ptr [rax], xmm0
0x1800286ea  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800286ee  call    IpsecAllocStr
0x1800286f3  mov     [rbx+10h], rax
0x1800286f7  test    rax, rax
0x1800286fa  jnz     short loc_18002872C
0x1800286fc  lea     r9d, [rax+8]
0x180028700  mov     edi, r9d
0x180028703  mov     rcx, cs:WPP_GLOBAL_Control
0x18002870a  lea     rsi, WPP_GLOBAL_Control
0x180028711  cmp     rcx, rsi
0x180028714  jz      loc_180028834
0x18002871a  test    byte ptr [rcx+1Ch], 10h
0x18002871e  jz      loc_18002880C
0x180028724  lea     edx, [rax+12h]
0x180028727  jmp     loc_1800287F5
0x18002872c  mov     rdx, [r14+38h]
0x180028730  lea     rax, [rbx+28h]
0x180028734  mov     ecx, [r14+30h]
0x180028738  lea     r9, [rbx+20h]
0x18002873c  mov     r8, rsi
0x18002873f  mov     [rsp+68h+var_48], rax
0x180028744  call    PACreateQMOffers
0x180028749  mov     edi, eax
0x18002874b  test    eax, eax
0x18002874d  jz      short loc_18002877A
0x18002874f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028756  lea     rsi, WPP_GLOBAL_Control
0x18002875d  cmp     rcx, rsi
0x180028760  jz      loc_180028834
0x180028766  test    byte ptr [rcx+1Ch], 10h
0x18002876a  jz      loc_18002880C
0x180028770  mov     edx, 13h
0x180028775  mov     r9d, eax
0x180028778  jmp     short loc_1800287F5
0x18002877a  mov     dword ptr [rbx+18h], 0
0x180028781  mov     rax, [r14+20h]
0x180028785  sub     rax, cs:qword_180059F78
0x18002878c  jnz     short loc_180028799
0x18002878e  mov     rax, [r14+28h]
0x180028792  sub     rax, cs:qword_180059F80
0x180028799  test    rax, rax
0x18002879c  jnz     loc_180028847
0x1800287a2  mov     dword ptr [rbx+18h], 2
0x1800287a9  lea     edi, [rax+32h]
0x1800287ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287b3  lea     rsi, WPP_GLOBAL_Control
0x1800287ba  cmp     rcx, rsi
0x1800287bd  jz      short loc_180028834
0x1800287bf  test    byte ptr [rcx+1Ch], 10h
0x1800287c3  jz      short loc_1800287E2
0x1800287c5  mov     rcx, [rcx+10h]
0x1800287c9  lea     edx, [rax+14h]
0x1800287cc  mov     r9d, edi
0x1800287cf  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x1800287d6  call    WPP_SF_d
0x1800287db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287e2  cmp     rcx, rsi
0x1800287e5  jz      short loc_180028834
0x1800287e7  test    byte ptr [rcx+1Ch], 10h
0x1800287eb  jz      short loc_18002880C
0x1800287ed  mov     edx, 15h
0x1800287f2  mov     r9d, edi
0x1800287f5  mov     rcx, [rcx+10h]
0x1800287f9  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x180028800  call    WPP_SF_d
0x180028805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002880c  cmp     rcx, rsi
0x18002880f  jz      short loc_18002882F
0x180028811  test    byte ptr [rcx+1Ch], 10h
0x180028815  jz      short loc_18002882F
0x180028817  mov     rcx, [rcx+10h]
0x18002881b  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x180028822  mov     edx, 16h
0x180028827  mov     r9, r14
0x18002882a  call    WPP_SF__guid_
0x18002882f  test    rbx, rbx
0x180028832  jz      short loc_18002883C
0x180028834  mov     rcx, rbx; lpMem
0x180028837  call    PAFreeQMPolicy
0x18002883c  mov     qword ptr [r15], 0
0x180028843  mov     eax, edi
0x180028845  jmp     short loc_18002886F
0x180028847  xor     eax, eax
0x180028849  test    byte ptr [rbp+4Ch], 3
0x18002884d  jz      short loc_180028857
0x18002884f  mov     eax, 1
0x180028854  mov     [rbx+18h], eax
0x180028857  cmp     dword ptr [rsi+38h], 0
0x18002885b  jz      short loc_180028863
0x18002885d  or      eax, 4
0x180028860  mov     [rbx+18h], eax
0x180028863  mov     dword ptr [rbx+1Ch], 0
0x18002886a  xor     eax, eax
0x18002886c  mov     [r15], rbx
0x18002886f  add     rsp, 38h
0x180028873  pop     r15
0x180028875  pop     r14
0x180028877  pop     rdi
0x180028878  pop     rsi
0x180028879  pop     rbp
0x18002887a  pop     rbx
0x18002887b  retn
```
