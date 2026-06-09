# WSTVerifySignatureToken

- ea: `0x180034534`
- end: `0x180034934`
- name: `WSTVerifySignatureToken`
- size: `1024`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800332b0`
- `0x180034194`

## callees

- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x1800321d8`
- `0x180034534`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x18003470a`
- `cryptdll!CDLocateCSystem` at `0x18003470a`

## pseudocode

```c
__int64 __fastcall WSTVerifySignatureToken(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int64 a4,
        unsigned __int8 **a5,
        _DWORD *a6,
        int *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  unsigned int v10; // r15d
  unsigned int v11; // r8d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int8 *v14; // rsi
  unsigned __int8 *v15; // rsi
  int v16; // edx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // ebx
  __int64 v20; // r9
  int v21; // ecx
  unsigned int v22; // r14d
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  __int64 *v26; // r14
  unsigned __int64 v27; // rcx
  char v28; // ah
  char v29; // r8
  __int64 i; // rdx
  unsigned __int8 v31; // cl
  char v32; // al
  __int64 v34; // [rsp+30h] [rbp-30h]
  __int64 v35; // [rsp+38h] [rbp-28h] BYREF
  __int64 v36; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *v37; // [rsp+48h] [rbp-18h]
  unsigned __int8 **v38; // [rsp+50h] [rbp-10h]

  v38 = a5;
  v10 = a3;
  v11 = *(_DWORD *)a2;
  v37 = a9;
  v36 = a4;
  v35 = 0;
  if ( v11 < 0x1C )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893048;
    v13 = 13;
LABEL_64:
    WPP_SF_(v12[2], v13, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
    return (unsigned int)-2146893048;
  }
  v14 = *(unsigned __int8 **)(a2 + 8);
  if ( *v14 != ((_BYTE)v10 != 0) + 4 || v14[1] != 4 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893048;
    v13 = 14;
    goto LABEL_64;
  }
  v15 = v14 + 2;
  if ( (_BYTE)v10 )
  {
    v16 = v15[3] + (v15[2] << 8);
    if ( (*v15 & 2) != 0 )
    {
      if ( v11 < v16 + 60 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)-2146893048;
        v13 = 15;
        goto LABEL_64;
      }
    }
    else if ( v16 != 12 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)-2146893041;
      v18 = 16;
      goto LABEL_17;
    }
  }
  if ( v15[1] != 0xFF || !(_BYTE)v10 && *(_DWORD *)(v15 + 2) != -1 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893041;
    v18 = 17;
    goto LABEL_17;
  }
  v20 = *(unsigned int *)(a1 + 40);
  v21 = *(_DWORD *)(a1 + 40) - 17;
  if ( *(_DWORD *)(a1 + 40) == 17 )
  {
    v22 = -148;
    v23 = (*v15 & 2) != 0 ? -150 : 15;
  }
  else
  {
    if ( v21 != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, v20);
      return (unsigned int)-2146893054;
    }
    v22 = -149;
    v23 = (*v15 & 2) != 0 ? -151 : 16;
  }
  *a7 = v23;
  v24 = CDLocateCSystem(v22, &v35);
  v19 = v24;
  if ( v24 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, v22, v24);
    return v19;
  }
  if ( (_BYTE)v10 && (*v15 & 2) == 0 )
    *a6 = -2147483647;
  v25 = *(_DWORD *)(a1 + 84);
  if ( (v25 & 0x400) != 0 || (v26 = (__int64 *)(a1 + 72), (v25 & 0x1000C) == 0x10000) )
    v26 = &v36;
  v27 = HIDWORD(*v26);
  BYTE3(v34) = BYTE4(*v26);
  LOBYTE(v34) = BYTE3(v27);
  BYTE1(v34) = BYTE2(v27);
  v28 = BYTE1(v27);
  LODWORD(v27) = *(_DWORD *)v26;
  BYTE2(v34) = v28;
  BYTE4(v34) = BYTE3(v27);
  BYTE5(v34) = BYTE2(v27);
  BYTE6(v34) = BYTE1(v27);
  HIBYTE(v34) = v27;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_dii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
      v10,
      v34,
      *(_QWORD *)(v15 + 6));
  if ( (*(_BYTE *)(a1 + 84) & 0xC) != 0 )
  {
    v29 = 0;
    for ( i = 0; i != 8; ++i )
    {
      v31 = v15[i + 6];
      v32 = *((_BYTE *)&v34 + i);
      v29 |= v32 ^ v31;
    }
    if ( v29 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
      return (unsigned int)-2146893040;
    }
  }
  *v37 = *(_QWORD *)(v15 + 6);
  if ( ((unsigned __int8)~*v15 & ((*(_BYTE *)(a1 + 80) & 2) != 0)) != 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)-2146893041;
    v18 = 22;
LABEL_17:
    WPP_SF_(v17[2], v18, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
    return (unsigned int)-2146893041;
  }
  ++*v26;
  if ( a8 )
    *a8 = v35;
  *v38 = v15;
  return v19;
}

```

## disassembly

```asm
0x180034534  mov     [rsp-38h+arg_8], rbx
0x180034539  push    rbp
0x18003453a  push    rsi
0x18003453b  push    rdi
0x18003453c  push    r12
0x18003453e  push    r13
0x180034540  push    r14
0x180034542  push    r15
0x180034544  mov     rbp, rsp
0x180034547  sub     rsp, 60h
0x18003454b  mov     rax, [rbp+arg_20]
0x18003454f  mov     r13, rcx
0x180034552  mov     rdi, [rbp+arg_28]
0x180034556  mov     r10, [rbp+arg_30]
0x18003455a  mov     r12, [rbp+arg_38]
0x18003455e  mov     [rbp+var_10], rax
0x180034562  mov     rax, [rbp+arg_40]
0x180034569  movzx   r15d, r8b
0x18003456d  mov     r8d, [rdx]
0x180034570  mov     [rbp+var_18], rax
0x180034574  mov     [rbp+var_20], r9
0x180034578  mov     [rbp+var_28], 0
0x180034580  cmp     r8d, 1Ch
0x180034584  jnb     short loc_1800345B1
0x180034586  mov     rcx, cs:WPP_GLOBAL_Control
0x18003458d  lea     rdi, WPP_GLOBAL_Control
0x180034594  cmp     rcx, rdi
0x180034597  jz      loc_180034915
0x18003459d  test    byte ptr [rcx+1Ch], 1
0x1800345a1  jz      loc_180034915
0x1800345a7  mov     edx, 0Dh
0x1800345ac  jmp     loc_180034905
0x1800345b1  mov     rsi, [rdx+8]
0x1800345b5  mov     al, r15b
0x1800345b8  neg     al
0x1800345ba  sbb     cx, cx
0x1800345bd  movzx   eax, byte ptr [rsi]
0x1800345c0  neg     cx
0x1800345c3  add     cx, 4
0x1800345c7  cmp     ax, cx
0x1800345ca  jnz     loc_1800348E7
0x1800345d0  cmp     byte ptr [rsi+1], 4
0x1800345d4  jnz     loc_1800348E7
0x1800345da  add     rsi, 2
0x1800345de  mov     r11b, 2
0x1800345e1  test    r15b, r15b
0x1800345e4  jz      loc_18003466C
0x1800345ea  movzx   edx, byte ptr [rsi+2]
0x1800345ee  movzx   eax, byte ptr [rsi+3]
0x1800345f2  shl     edx, 8
0x1800345f5  add     edx, eax
0x1800345f7  test    [rsi], r11b
0x1800345fa  jz      short loc_18003462F
0x1800345fc  lea     eax, [rdx+3Ch]
0x1800345ff  cmp     r8d, eax
0x180034602  jnb     short loc_18003466C
0x180034604  mov     rcx, cs:WPP_GLOBAL_Control
0x18003460b  lea     rdi, WPP_GLOBAL_Control
0x180034612  cmp     rcx, rdi
0x180034615  jz      loc_180034915
0x18003461b  test    byte ptr [rcx+1Ch], 1
0x18003461f  jz      loc_180034915
0x180034625  mov     edx, 0Fh
0x18003462a  jmp     loc_180034905
0x18003462f  cmp     edx, 0Ch
0x180034632  jz      short loc_18003466C
0x180034634  mov     rcx, cs:WPP_GLOBAL_Control
0x18003463b  lea     rdi, WPP_GLOBAL_Control
0x180034642  cmp     rcx, rdi
0x180034645  jz      short loc_180034662
0x180034647  test    byte ptr [rcx+1Ch], 1
0x18003464b  jz      short loc_180034662
0x18003464d  mov     edx, 10h
0x180034652  mov     rcx, [rcx+10h]
0x180034656  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003465d  call    WPP_SF_
0x180034662  mov     ebx, 8009030Fh
0x180034667  jmp     loc_18003491A
0x18003466c  cmp     byte ptr [rsi+1], 0FFh
0x180034670  jnz     loc_1800348BC
0x180034676  test    r15b, r15b
0x180034679  jnz     short loc_180034685
0x18003467b  cmp     dword ptr [rsi+2], 0FFFFFFFFh
0x18003467f  jnz     loc_1800348BC
0x180034685  mov     r9d, [r13+28h]
0x180034689  mov     ecx, r9d
0x18003468c  sub     ecx, 11h
0x18003468f  jz      short loc_1800346E8
0x180034691  cmp     ecx, 1
0x180034694  jz      short loc_1800346CE
0x180034696  mov     rcx, cs:WPP_GLOBAL_Control
0x18003469d  lea     rdi, WPP_GLOBAL_Control
0x1800346a4  cmp     rcx, rdi
0x1800346a7  jz      short loc_1800346C4
0x1800346a9  test    byte ptr [rcx+1Ch], 1
0x1800346ad  jz      short loc_1800346C4
0x1800346af  mov     rcx, [rcx+10h]
0x1800346b3  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800346ba  mov     edx, 12h
0x1800346bf  call    WPP_SF_d
0x1800346c4  mov     ebx, 80090302h
0x1800346c9  jmp     loc_18003491A
0x1800346ce  mov     al, [rsi]
0x1800346d0  mov     r14d, 0FFFFFF6Bh
0x1800346d6  and     al, r11b
0x1800346d9  neg     al
0x1800346db  sbb     ecx, ecx
0x1800346dd  and     ecx, 0FFFFFF59h
0x1800346e3  add     ecx, 10h
0x1800346e6  jmp     short loc_180034700
0x1800346e8  mov     al, [rsi]
0x1800346ea  mov     r14d, 0FFFFFF6Ch
0x1800346f0  and     al, r11b
0x1800346f3  neg     al
0x1800346f5  sbb     ecx, ecx
0x1800346f7  and     ecx, 0FFFFFF5Bh
0x1800346fd  add     ecx, 0Fh
0x180034700  mov     [r10], ecx
0x180034703  lea     rdx, [rbp+var_28]
0x180034707  mov     ecx, r14d
0x18003470a  call    cs:__imp_CDLocateCSystem
0x180034710  mov     ebx, eax
0x180034712  test    eax, eax
0x180034714  jns     short loc_180034758
0x180034716  mov     rcx, cs:WPP_GLOBAL_Control
0x18003471d  lea     rdi, WPP_GLOBAL_Control
0x180034724  cmp     rcx, rdi
0x180034727  jz      loc_18003491A
0x18003472d  test    byte ptr [rcx+1Ch], 1
0x180034731  jz      loc_18003491A
0x180034737  mov     rcx, [rcx+10h]
0x18003473b  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180034742  mov     edx, 13h
0x180034747  mov     dword ptr [rsp+60h+var_40], eax
0x18003474b  mov     r9d, r14d
0x18003474e  call    WPP_SF_dd
0x180034753  jmp     loc_18003491A
0x180034758  test    r15b, r15b
0x18003475b  jz      short loc_180034768
0x18003475d  test    byte ptr [rsi], 2
0x180034760  jnz     short loc_180034768
0x180034762  mov     dword ptr [rdi], 80000001h
0x180034768  mov     eax, [r13+54h]
0x18003476c  bt      eax, 0Ah
0x180034770  jb      short loc_180034782
0x180034772  and     eax, 1000Ch
0x180034777  lea     r14, [r13+48h]
0x18003477b  cmp     eax, 10000h
0x180034780  jnz     short loc_180034786
0x180034782  lea     r14, [rbp+var_20]
0x180034786  mov     rcx, [r14]
0x180034789  shr     rcx, 20h
0x18003478d  mov     eax, ecx
0x18003478f  mov     byte ptr [rbp+var_30+3], cl
0x180034792  shr     eax, 18h
0x180034795  mov     byte ptr [rbp+var_30], al
0x180034798  mov     eax, ecx
0x18003479a  shr     eax, 10h
0x18003479d  mov     byte ptr [rbp+var_30+1], al
0x1800347a0  mov     eax, ecx
0x1800347a2  mov     ecx, [r14]
0x1800347a5  shr     eax, 8
0x1800347a8  mov     byte ptr [rbp+var_30+2], al
0x1800347ab  mov     eax, ecx
0x1800347ad  shr     eax, 18h
0x1800347b0  mov     byte ptr [rbp+var_30+4], al
0x1800347b3  mov     eax, ecx
0x1800347b5  shr     eax, 10h
0x1800347b8  mov     byte ptr [rbp+var_30+5], al
0x1800347bb  mov     eax, ecx
0x1800347bd  shr     eax, 8
0x1800347c0  mov     byte ptr [rbp+var_30+6], al
0x1800347c3  mov     byte ptr [rbp+var_30+7], cl
0x1800347c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347cd  lea     rdi, WPP_GLOBAL_Control
0x1800347d4  cmp     rcx, rdi
0x1800347d7  jz      short loc_180034809
0x1800347d9  test    byte ptr [rcx+1Ch], 40h
0x1800347dd  jz      short loc_180034809
0x1800347df  mov     rax, [rsi+6]
0x1800347e3  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800347ea  mov     rcx, [rcx+10h]
0x1800347ee  mov     r9d, r15d
0x1800347f1  mov     [rsp+60h+var_38], rax
0x1800347f6  mov     edx, 14h
0x1800347fb  mov     rax, [rbp+var_30]
0x1800347ff  mov     [rsp+60h+var_40], rax
0x180034804  call    WPP_SF_dii
0x180034809  test    byte ptr [r13+54h], 0Ch
0x18003480e  jz      short loc_180034861
0x180034810  xor     r8b, r8b
0x180034813  xor     edx, edx
0x180034815  mov     cl, [rdx+rsi+6]
0x180034819  mov     al, byte ptr [rbp+rdx+var_30]
0x18003481d  inc     rdx
0x180034820  xor     cl, al
0x180034822  or      r8b, cl
0x180034825  cmp     rdx, 8
0x180034829  jnz     short loc_180034815
0x18003482b  test    r8b, r8b
0x18003482e  jz      short loc_180034861
0x180034830  mov     rcx, cs:WPP_GLOBAL_Control
0x180034837  cmp     rcx, rdi
0x18003483a  jz      short loc_180034857
0x18003483c  test    byte ptr [rcx+1Ch], 1
0x180034840  jz      short loc_180034857
0x180034842  mov     rcx, [rcx+10h]
0x180034846  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003484d  mov     edx, 15h
0x180034852  call    WPP_SF_
0x180034857  mov     ebx, 80090310h
0x18003485c  jmp     loc_18003491A
0x180034861  mov     rcx, [rbp+var_18]
0x180034865  mov     rax, [rsi+6]
0x180034869  mov     [rcx], rax
0x18003486c  test    byte ptr [r13+50h], 2
0x180034871  mov     al, [rsi]
0x180034873  setnz   cl
0x180034876  not     al
0x180034878  and     cl, al
0x18003487a  test    cl, 1
0x18003487d  jz      short loc_1800348A3
0x18003487f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034886  cmp     rcx, rdi
0x180034889  jz      loc_180034662
0x18003488f  test    byte ptr [rcx+1Ch], 1
0x180034893  jz      loc_180034662
0x180034899  mov     edx, 16h
0x18003489e  jmp     loc_180034652
0x1800348a3  inc     qword ptr [r14]
0x1800348a6  test    r12, r12
0x1800348a9  jz      short loc_1800348B3
0x1800348ab  mov     rax, [rbp+var_28]
0x1800348af  mov     [r12], rax
0x1800348b3  mov     rax, [rbp+var_10]
0x1800348b7  mov     [rax], rsi
0x1800348ba  jmp     short loc_18003491A
0x1800348bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348c3  lea     rdi, WPP_GLOBAL_Control
0x1800348ca  cmp     rcx, rdi
0x1800348cd  jz      loc_180034662
0x1800348d3  test    byte ptr [rcx+1Ch], 1
0x1800348d7  jz      loc_180034662
0x1800348dd  mov     edx, 11h
0x1800348e2  jmp     loc_180034652
0x1800348e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348ee  lea     rdi, WPP_GLOBAL_Control
0x1800348f5  cmp     rcx, rdi
0x1800348f8  jz      short loc_180034915
0x1800348fa  test    byte ptr [rcx+1Ch], 1
0x1800348fe  jz      short loc_180034915
0x180034900  mov     edx, 0Eh
0x180034905  mov     rcx, [rcx+10h]
0x180034909  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180034910  call    WPP_SF_
0x180034915  mov     ebx, 80090308h
0x18003491a  mov     eax, ebx
0x18003491c  mov     rbx, [rsp+60h+arg_8]
0x180034924  add     rsp, 60h
0x180034928  pop     r15
0x18003492a  pop     r14
0x18003492c  pop     r13
0x18003492e  pop     r12
0x180034930  pop     rdi
0x180034931  pop     rsi
0x180034932  pop     rbp
0x180034933  retn
```
