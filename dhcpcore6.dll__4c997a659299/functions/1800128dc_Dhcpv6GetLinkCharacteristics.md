# Dhcpv6GetLinkCharacteristics

- ea: `0x1800128dc`
- end: `0x180012ede`
- name: `Dhcpv6GetLinkCharacteristics`
- size: `1538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800152b8`

## callees

- `0x180001ca4`
- `0x180004b30`
- `0x180007564`
- `0x18000c740`
- `0x18000dee0`
- `0x1800128dc`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001e81c`
- `0x18001eac0`
- `0x18003098c`
- `0x180031008`
- `0x180031c1c`
- `0x1800338c0`
- `0x180034ad8`

## pseudocode

```c
__int64 __fastcall Dhcpv6GetLinkCharacteristics(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  unsigned int AllParameters; // ebx
  unsigned int v8; // eax
  __int64 v9; // rcx
  size_t v10; // r12
  unsigned __int16 v11; // bx
  int v12; // eax
  _QWORD *v13; // rax
  char *p_Src; // rdx
  size_t v15; // r8
  int v16; // ecx
  bool v17; // zf
  __int64 v18; // rax
  int v19; // r8d
  unsigned int v20; // eax
  int v21; // edx
  __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+70h] [rbp-90h]
  LPVOID v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v29; // [rsp+90h] [rbp-70h]
  _BYTE v30[548]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v31; // [rsp+2C4h] [rbp+1C4h]
  char v32; // [rsp+2C6h] [rbp+1C6h] BYREF
  _BYTE v33[576]; // [rsp+330h] [rbp+230h] BYREF
  _OWORD v34[2]; // [rsp+570h] [rbp+470h] BYREF
  _DWORD v35[130]; // [rsp+590h] [rbp+490h] BYREF
  __int16 v36; // [rsp+798h] [rbp+698h]
  int v37; // [rsp+79Ch] [rbp+69Ch]
  int v38; // [rsp+7A0h] [rbp+6A0h]
  __int128 v39; // [rsp+7A8h] [rbp+6A8h]
  int v40; // [rsp+7C0h] [rbp+6C0h]
  int v41; // [rsp+7C4h] [rbp+6C4h]
  _BYTE v42[548]; // [rsp+7D0h] [rbp+6D0h] BYREF
  unsigned __int16 v43; // [rsp+9F4h] [rbp+8F4h]
  char Src; // [rsp+9F6h] [rbp+8F6h] BYREF
  int v45; // [rsp+A54h] [rbp+954h]

  v2 = *a1;
  v29 = a2;
  v28 = v2;
  v5 = 0;
  v26 = 0;
  memset_0(v35, 0, 0x238u);
  memset_0(v42, 0, 0x290u);
  memset_0(v33, 0, 0x238u);
  memset_0(v30, 0, 0x290u);
  v27 = 0;
  memset(v34, 0, sizeof(v34));
  if ( g_fVelocityDhcpnsiv6StyleUpdate )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_q(v6, 19, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, a1);
    if ( !a2 )
    {
      AllParameters = 87;
      goto LABEL_67;
    }
    *a2 = 0;
    AllParameters = GetAllParameters(
                      v6,
                      (unsigned int)&NPI_MS_NDIS_MODULEID,
                      1,
                      (unsigned int)&v28,
                      8,
                      0,
                      0,
                      (__int64)v42,
                      656,
                      (__int64)v35,
                      568);
    if ( AllParameters )
      goto LABEL_67;
  }
  else
  {
    *a2 = 0;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_J(1028, 20, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, *a1);
    v8 = GetAllParameters(
           v6,
           (unsigned int)&NPI_MS_NDIS_MODULEID,
           1,
           (unsigned int)&v28,
           8,
           0,
           0,
           (__int64)v42,
           656,
           (__int64)v35,
           568);
    AllParameters = v8;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 21, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v8);
    if ( AllParameters )
      goto LABEL_59;
  }
  v10 = v43;
  if ( v43 )
  {
    v11 = v31;
    v12 = v43;
    v25 = 0;
  }
  else
  {
    if ( g_fVelocityDhcpnsiv6StyleUpdate )
    {
      AllParameters = Dhcpv6EnumHardwareAddress(v33, v30);
      if ( AllParameters )
        goto LABEL_67;
    }
    else
    {
      AllParameters = Dhcpv6EnumHardwareAddress_Old(v33, v30);
      if ( AllParameters )
        goto LABEL_59;
    }
    v11 = v31;
    v12 = v31;
    v25 = 1;
  }
  v13 = (_QWORD *)DhcpAlloc(((v12 + 7) & 0xFFFFFFF8) + 80);
  v26 = v13;
  v5 = v13;
  if ( g_fVelocityDhcpnsiv6StyleUpdate )
  {
    if ( !v13 )
    {
      AllParameters = 8;
      goto LABEL_67;
    }
  }
  else if ( !v13 )
  {
    AllParameters = 8;
LABEL_60:
    if ( v5 )
      DhcpFree(&v26);
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 29, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, AllParameters);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v9, UnableToGetLinkCharacteristics, AllParameters);
    TraceLogErrorv6(0, AllParameters, 126);
    goto LABEL_67;
  }
  v13[8] = v13 + 10;
  *v13 = *a1;
  *((_DWORD *)v13 + 13) = v45 == 1;
  *((_DWORD *)v13 + 2) = v35[0];
  *((_DWORD *)v13 + 12) = v37;
  if ( v25 )
  {
    *((_WORD *)v13 + 28) = v11;
    p_Src = &v32;
    v15 = v11;
  }
  else
  {
    *((_WORD *)v13 + 28) = v10;
    p_Src = &Src;
    v15 = v10;
  }
  memcpy_0((void *)v13[8], p_Src, v15);
  *((_WORD *)v5 + 14) = v36;
  v17 = g_fVelocityDhcpnsiv6StyleUpdate == 0;
  *((_DWORD *)v5 + 8) = v38 != 0;
  *(_OWORD *)((char *)v5 + 12) = v39;
  *((_DWORD *)v5 + 10) = v40;
  *((_DWORD *)v5 + 11) = v41;
  v18 = *a1;
  v27 = *a1;
  if ( v17 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_J(1028, 22, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v18);
    v20 = GetAllParameters(
            v16,
            (unsigned int)&NPI_MS_IPV6_MODULEID,
            7,
            (unsigned int)&v27,
            8,
            0,
            0,
            0,
            0,
            (__int64)v34,
            32);
    AllParameters = v20;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 23, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v20);
    if ( AllParameters )
      goto LABEL_59;
  }
  else
  {
    AllParameters = GetAllParameters(
                      v16,
                      (unsigned int)&NPI_MS_IPV6_MODULEID,
                      7,
                      (unsigned int)&v27,
                      8,
                      0,
                      0,
                      0,
                      0,
                      (__int64)v34,
                      32);
    if ( AllParameters )
      goto LABEL_67;
  }
  *((_BYTE *)v5 + 72) = BYTE2(v34[0]);
  switch ( *((_WORD *)v5 + 14) )
  {
    case 1:
      *((_BYTE *)v5 + 36) = 7;
      goto LABEL_78;
    case 6:
      goto LABEL_50;
    case 9:
    case 0xF:
      *((_BYTE *)v5 + 36) = 6;
      goto LABEL_78;
    case 0x17:
      *((_BYTE *)v5 + 36) = 8;
      goto LABEL_78;
  }
  v9 = (unsigned int)*((unsigned __int16 *)v5 + 14) - 24;
  if ( *((_WORD *)v5 + 14) != 24 )
  {
    if ( *((_WORD *)v5 + 14) != 71 )
    {
      if ( *((_WORD *)v5 + 14) == 144 )
      {
        *((_BYTE *)v5 + 36) = 24;
        goto LABEL_78;
      }
      if ( g_fVelocityDhcpnsiv6StyleUpdate )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
        {
          v21 = 26;
LABEL_49:
          WPP_SF_ll_guid_(
            *((unsigned __int16 *)v5 + 14) - 71,
            v21,
            v19,
            *((unsigned __int16 *)v5 + 14),
            v24,
            (__int64)v5 + 12);
        }
      }
      else if ( (xmmword_1800423E0 & 2) != 0 )
      {
        v21 = 27;
        goto LABEL_49;
      }
    }
LABEL_50:
    *((_BYTE *)v5 + 36) = 1;
LABEL_78:
    v17 = g_fVelocityDhcpnsiv6StyleUpdate == 0;
    *v29 = v5;
    if ( v17 )
      return AllParameters;
    v26 = 0;
LABEL_67:
    if ( !g_fVelocityDhcpnsiv6StyleUpdate )
      return AllParameters;
    goto LABEL_68;
  }
  if ( g_fVelocityDhcpnsiv6StyleUpdate )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_J(1028, 24, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, *a1);
    AllParameters = -1;
    goto LABEL_67;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_J(1028, 25, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, *a1);
  AllParameters = -1;
LABEL_59:
  if ( !g_fVelocityDhcpnsiv6StyleUpdate )
    goto LABEL_60;
LABEL_68:
  DhcpFree(&v26);
  if ( AllParameters )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 28, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, AllParameters);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v22, UnableToGetLinkCharacteristics, AllParameters);
    TraceLogErrorv6(0, AllParameters, 126);
  }
  return AllParameters;
}

```

## disassembly

```asm
0x1800128dc  mov     [rsp-8+arg_10], rbx
0x1800128e1  mov     [rsp-8+arg_18], rsi
0x1800128e6  push    rbp
0x1800128e7  push    rdi
0x1800128e8  push    r12
0x1800128ea  push    r13
0x1800128ec  push    r14
0x1800128ee  lea     rbp, [rsp-970h]
0x1800128f6  sub     rsp, 0A70h
0x1800128fd  mov     rax, cs:__security_cookie
0x180012904  xor     rax, rsp
0x180012907  mov     [rbp+990h+var_30], rax
0x18001290e  mov     rax, [rcx]
0x180012911  mov     rbx, rdx
0x180012914  mov     [rbp+990h+var_A00], rdx
0x180012918  mov     r13, rcx
0x18001291b  mov     esi, 238h
0x180012920  mov     [rbp+990h+var_A08], rax
0x180012924  xor     edi, edi
0x180012926  lea     rcx, [rbp+990h+var_500]; void *
0x18001292d  mov     r8d, esi; Size
0x180012930  mov     [rsp+0A90h+var_A18], rdi
0x180012935  xor     edx, edx; Val
0x180012937  call    memset_0
0x18001293c  lea     r14d, [rsi+58h]
0x180012940  xor     edx, edx; Val
0x180012942  mov     r8d, r14d; Size
0x180012945  lea     rcx, [rbp+990h+var_2C0]; void *
0x18001294c  call    memset_0
0x180012951  mov     r8d, esi; Size
0x180012954  lea     rcx, [rbp+990h+var_760]; void *
0x18001295b  xor     edx, edx; Val
0x18001295d  call    memset_0
0x180012962  mov     r8d, r14d; Size
0x180012965  lea     rcx, [rbp+990h+var_9F0]; void *
0x180012969  xor     edx, edx; Val
0x18001296b  call    memset_0
0x180012970  xor     edx, edx
0x180012972  lea     r12d, [rdi+1]
0x180012976  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, edx
0x18001297c  xorps   xmm0, xmm0
0x18001297f  mov     [rbp+990h+var_A10], rdx
0x180012983  movups  [rbp+990h+var_520], xmm0
0x18001298a  movups  [rbp+990h+var_510], xmm0
0x180012991  jz      loc_180012A27
0x180012997  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001299e  lea     r14, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x1800129a5  jz      short loc_1800129B7
0x1800129a7  lea     edx, [rdi+13h]
0x1800129aa  mov     r9, r13
0x1800129ad  mov     r8, r14
0x1800129b0  call    WPP_SF_q
0x1800129b5  xor     edx, edx
0x1800129b7  test    rbx, rbx
0x1800129ba  jz      short loc_180012A1D
0x1800129bc  mov     [rsp+0A90h+var_A30], edx
0x1800129c0  lea     rax, [rbp+990h+var_500]
0x1800129c7  mov     [rsp+0A90h+var_A40], esi
0x1800129cb  lea     r9, [rbp+990h+var_A08]
0x1800129cf  mov     [rsp+0A90h+var_A48], rax
0x1800129d4  mov     esi, 8
0x1800129d9  mov     [rsp+0A90h+var_A50], 290h
0x1800129e1  lea     rax, [rbp+990h+var_2C0]
0x1800129e8  mov     [rsp+0A90h+var_A58], rax
0x1800129ed  mov     r8d, r12d
0x1800129f0  mov     [rsp+0A90h+var_A60], edx
0x1800129f4  mov     [rsp+0A90h+var_A68], rdx
0x1800129f9  mov     [rbx], rdx
0x1800129fc  lea     rdx, NPI_MS_NDIS_MODULEID
0x180012a03  mov     [rsp+0A90h+var_A70], esi
0x180012a07  call    GetAllParameters
0x180012a0c  xor     edx, edx
0x180012a0e  mov     ebx, eax
0x180012a10  test    eax, eax
0x180012a12  jnz     loc_180012E2C
0x180012a18  jmp     loc_180012AC7
0x180012a1d  mov     ebx, 57h ; 'W'
0x180012a22  jmp     loc_180012E2C
0x180012a27  mov     [rbx], rdx
0x180012a2a  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012a31  lea     r14, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x180012a38  jz      short loc_180012A52
0x180012a3a  mov     r9, [r13+0]
0x180012a3e  mov     edx, 14h
0x180012a43  mov     ecx, 404h
0x180012a48  mov     r8, r14
0x180012a4b  call    WPP_SF_J
0x180012a50  xor     edx, edx
0x180012a52  mov     [rsp+0A90h+var_A30], edx
0x180012a56  lea     rax, [rbp+990h+var_500]
0x180012a5d  mov     [rsp+0A90h+var_A40], esi
0x180012a61  lea     r9, [rbp+990h+var_A08]
0x180012a65  mov     [rsp+0A90h+var_A48], rax
0x180012a6a  mov     esi, 8
0x180012a6f  mov     [rsp+0A90h+var_A50], 290h
0x180012a77  lea     rax, [rbp+990h+var_2C0]
0x180012a7e  mov     [rsp+0A90h+var_A58], rax
0x180012a83  mov     r8d, r12d
0x180012a86  mov     [rsp+0A90h+var_A60], edx
0x180012a8a  mov     [rsp+0A90h+var_A68], rdx
0x180012a8f  lea     rdx, NPI_MS_NDIS_MODULEID
0x180012a96  mov     [rsp+0A90h+var_A70], esi
0x180012a9a  call    GetAllParameters
0x180012a9f  mov     ebx, eax
0x180012aa1  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012aa8  jz      short loc_180012ABD
0x180012aaa  lea     edx, [rsi+0Dh]
0x180012aad  mov     ecx, 404h
0x180012ab2  mov     r9d, eax
0x180012ab5  mov     r8, r14
0x180012ab8  call    WPP_SF_D
0x180012abd  xor     edx, edx
0x180012abf  test    ebx, ebx
0x180012ac1  jnz     loc_180012DCE
0x180012ac7  movzx   r12d, [rbp+990h+var_9C]
0x180012acf  test    r12w, r12w
0x180012ad3  jnz     short loc_180012B1D
0x180012ad5  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, edx
0x180012adb  lea     rcx, [rbp+990h+var_760]; void *
0x180012ae2  lea     rdx, [rbp+990h+var_9F0]; void *
0x180012ae6  jz      short loc_180012AF9
0x180012ae8  call    Dhcpv6EnumHardwareAddress
0x180012aed  mov     ebx, eax
0x180012aef  test    eax, eax
0x180012af1  jnz     loc_180012E2C
0x180012af7  jmp     short loc_180012B0A
0x180012af9  call    Dhcpv6EnumHardwareAddress_Old
0x180012afe  xor     edx, edx
0x180012b00  mov     ebx, eax
0x180012b02  test    eax, eax
0x180012b04  jnz     loc_180012DCE
0x180012b0a  movzx   ebx, [rbp+990h+var_7CC]
0x180012b11  mov     eax, ebx
0x180012b13  mov     [rsp+0A90h+var_A20], 1
0x180012b1b  jmp     short loc_180012B2B
0x180012b1d  movzx   ebx, [rbp+990h+var_7CC]
0x180012b24  mov     eax, r12d
0x180012b27  mov     [rsp+0A90h+var_A20], edx
0x180012b2b  lea     ecx, [rax+7]
0x180012b2e  and     ecx, 0FFFFFFF8h
0x180012b31  add     ecx, 50h ; 'P'
0x180012b34  call    DhcpAlloc
0x180012b39  xor     edx, edx
0x180012b3b  mov     [rsp+0A90h+var_A18], rax
0x180012b40  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, edx
0x180012b46  mov     rdi, rax
0x180012b49  jz      short loc_180012B57
0x180012b4b  test    rax, rax
0x180012b4e  jnz     short loc_180012B63
0x180012b50  mov     ebx, esi
0x180012b52  jmp     loc_180012E2A
0x180012b57  test    rdi, rdi
0x180012b5a  jnz     short loc_180012B63
0x180012b5c  mov     ebx, esi
0x180012b5e  jmp     loc_180012DD6
0x180012b63  add     rax, 50h ; 'P'
0x180012b67  mov     [rdi+40h], rax
0x180012b6b  mov     rax, [r13+0]
0x180012b6f  mov     [rdi], rax
0x180012b72  mov     eax, edx
0x180012b74  cmp     [rbp+990h+var_3C], 1
0x180012b7b  setz    al
0x180012b7e  mov     [rdi+34h], eax
0x180012b81  mov     eax, [rbp+990h+var_500]
0x180012b87  mov     [rdi+8], eax
0x180012b8a  mov     eax, [rbp+990h+var_2F4]
0x180012b90  mov     [rdi+30h], eax
0x180012b93  cmp     [rsp+0A90h+var_A20], edx
0x180012b97  jz      short loc_180012BAA
0x180012b99  mov     [rdi+38h], bx
0x180012b9d  lea     rdx, [rbp+990h+var_7CA]
0x180012ba4  movzx   r8d, bx
0x180012ba8  jmp     short loc_180012BB9
0x180012baa  mov     [rdi+38h], r12w
0x180012baf  lea     rdx, [rbp+990h+Src]; Src
0x180012bb6  mov     r8, r12; Size
0x180012bb9  mov     rcx, [rdi+40h]; void *
0x180012bbd  call    memcpy_0
0x180012bc2  movzx   eax, [rbp+990h+var_2F8]
0x180012bc9  lea     r12, [rdi+0Ch]
0x180012bcd  mov     [rdi+1Ch], ax
0x180012bd1  xor     ebx, ebx
0x180012bd3  cmp     [rbp+990h+var_2F0], ebx
0x180012bd9  mov     eax, ebx
0x180012bdb  setnz   al
0x180012bde  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, ebx
0x180012be4  mov     [rdi+20h], eax
0x180012be7  movups  xmm0, [rbp+990h+var_2E8]
0x180012bee  movdqu  xmmword ptr [r12], xmm0
0x180012bf4  mov     eax, [rbp+990h+var_2D0]
0x180012bfa  mov     [rdi+28h], eax
0x180012bfd  mov     eax, [rbp+990h+var_2CC]
0x180012c03  mov     [rdi+2Ch], eax
0x180012c06  mov     rax, [r13+0]
0x180012c0a  mov     [rbp+990h+var_A10], rax
0x180012c0e  jz      short loc_180012C63
0x180012c10  mov     [rsp+0A90h+var_A30], ebx
0x180012c14  lea     rax, [rbp+990h+var_520]
0x180012c1b  mov     [rsp+0A90h+var_A40], 20h ; ' '
0x180012c23  lea     r9, [rbp+990h+var_A10]
0x180012c27  mov     [rsp+0A90h+var_A48], rax
0x180012c2c  lea     r8d, [rbx+7]
0x180012c30  mov     [rsp+0A90h+var_A50], ebx
0x180012c34  lea     rdx, NPI_MS_IPV6_MODULEID
0x180012c3b  mov     [rsp+0A90h+var_A58], rbx
0x180012c40  mov     [rsp+0A90h+var_A60], ebx
0x180012c44  mov     [rsp+0A90h+var_A68], rbx
0x180012c49  mov     [rsp+0A90h+var_A70], esi
0x180012c4d  call    GetAllParameters
0x180012c52  xor     edx, edx
0x180012c54  mov     ebx, eax
0x180012c56  test    eax, eax
0x180012c58  jz      loc_180012CEF
0x180012c5e  jmp     loc_180012E2A
0x180012c63  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012c6a  jz      short loc_180012C81
0x180012c6c  mov     edx, 16h
0x180012c71  mov     ecx, 404h
0x180012c76  mov     r9, rax
0x180012c79  mov     r8, r14
0x180012c7c  call    WPP_SF_J
0x180012c81  mov     [rsp+0A90h+var_A30], ebx
0x180012c85  lea     rax, [rbp+990h+var_520]
0x180012c8c  mov     [rsp+0A90h+var_A40], 20h ; ' '
0x180012c94  lea     r9, [rbp+990h+var_A10]
0x180012c98  mov     [rsp+0A90h+var_A48], rax
0x180012c9d  lea     rdx, NPI_MS_IPV6_MODULEID
0x180012ca4  mov     [rsp+0A90h+var_A50], ebx
0x180012ca8  mov     r8d, 7
0x180012cae  mov     [rsp+0A90h+var_A58], rbx
0x180012cb3  mov     [rsp+0A90h+var_A60], ebx
0x180012cb7  mov     [rsp+0A90h+var_A68], rbx
0x180012cbc  mov     [rsp+0A90h+var_A70], esi
0x180012cc0  call    GetAllParameters
0x180012cc5  mov     ebx, eax
0x180012cc7  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012cce  jz      short loc_180012CE5
0x180012cd0  mov     edx, 17h
0x180012cd5  mov     ecx, 404h
0x180012cda  mov     r9d, eax
0x180012cdd  mov     r8, r14
0x180012ce0  call    WPP_SF_D
0x180012ce5  xor     edx, edx
0x180012ce7  test    ebx, ebx
0x180012ce9  jnz     loc_180012DCE
0x180012cef  mov     al, byte ptr [rbp+990h+var_520+2]
0x180012cf5  mov     [rdi+48h], al
0x180012cf8  movzx   r9d, word ptr [rdi+1Ch]
0x180012cfd  mov     ecx, r9d
0x180012d00  sub     ecx, 1
0x180012d03  jz      loc_180012EC1
0x180012d09  sub     ecx, 5
0x180012d0c  jz      short loc_180012D69
0x180012d0e  sub     ecx, 3
0x180012d11  jz      loc_180012EBB
0x180012d17  sub     ecx, 6
0x180012d1a  jz      loc_180012EBB
0x180012d20  sub     ecx, esi
0x180012d22  jz      loc_180012EB5
0x180012d28  sub     ecx, 1
0x180012d2b  jz      short loc_180012D7B
0x180012d2d  sub     ecx, 2Fh ; '/'
0x180012d30  jz      short loc_180012D69
0x180012d32  cmp     ecx, 49h ; 'I'
0x180012d35  jz      short loc_180012D72
0x180012d37  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, edx
0x180012d3d  jz      short loc_180012D4F
0x180012d3f  test    byte ptr cs:xmmword_1800423E0, 2
0x180012d46  jz      short loc_180012D69
0x180012d48  mov     edx, 1Ah
0x180012d4d  jmp     short loc_180012D5D
0x180012d4f  test    byte ptr cs:xmmword_1800423E0, 2
0x180012d56  jz      short loc_180012D69
0x180012d58  mov     edx, 1Bh
0x180012d5d  mov     [rsp+0A90h+var_A68], r12
0x180012d62  call    WPP_SF_ll_guid_
0x180012d67  xor     edx, edx
0x180012d69  mov     byte ptr [rdi+24h], 1
0x180012d6d  jmp     loc_180012EC5
0x180012d72  mov     byte ptr [rdi+24h], 18h
0x180012d76  jmp     loc_180012EC5
0x180012d7b  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, edx
0x180012d81  jz      short loc_180012DAA
0x180012d83  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012d8a  jz      short loc_180012DA2
0x180012d8c  mov     r9, [r13+0]
0x180012d90  mov     edx, 18h
0x180012d95  mov     ecx, 404h
0x180012d9a  mov     r8, r14
0x180012d9d  call    WPP_SF_J
0x180012da2  or      ebx, 0FFFFFFFFh
0x180012da5  jmp     loc_180012E2A
0x180012daa  test    byte ptr cs:xmmword_1800423E0, 10h
0x180012db1  jz      short loc_180012DCB
0x180012db3  mov     r9, [r13+0]
0x180012db7  mov     edx, 19h
0x180012dbc  mov     ecx, 404h
0x180012dc1  mov     r8, r14
0x180012dc4  call    WPP_SF_J
0x180012dc9  xor     edx, edx
  ... truncated ...
```
