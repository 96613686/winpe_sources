# CreateDhcpv6InfoRequest

- ea: `0x180013b6c`
- end: `0x180014064`
- name: `CreateDhcpv6InfoRequest`
- size: `1272`
- prototype: `__int64 __fastcall(char *, __int16 *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x180001d8c`
- `0x180002cac`
- `0x180002f80`
- `0x18000e1ec`
- `0x18000ed3c`
- `0x180013b6c`
- `0x180018678`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180027e20`
- `0x180030920`
- `0x18003098c`
- `0x1800337d0`
- `0x1800338c0`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6InfoRequest(char *a1, __int16 *a2, int *a3)
{
  __int64 v4; // rsi
  char *v5; // rbx
  __int16 v6; // ax
  __int64 v7; // rdx
  unsigned int appended; // edi
  int v9; // r9d
  int v10; // r14d
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  bool v16; // zf
  _QWORD *v17; // r15
  __int64 v18; // rdx
  int v19; // r8d
  _QWORD *i; // rcx
  _WORD *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  char *v24; // r13
  __int64 v25; // r8
  _QWORD *v26; // r14
  _BYTE *v27; // rcx
  int v28; // r11d
  __int16 v29; // r10
  __int64 v30; // rdx
  __int16 v31; // r10
  int v32; // r11d
  __int64 v33; // rdx
  __int16 v34; // r10
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  int Src; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  _QWORD *v42; // [rsp+60h] [rbp-A0h]
  int *v43; // [rsp+68h] [rbp-98h]
  _BYTE v44[208]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[208]; // [rsp+140h] [rbp+40h] BYREF
  char v46; // [rsp+210h] [rbp+110h] BYREF

  v43 = a3;
  v37 = 0;
  v4 = (__int64)a1;
  v40 = 0;
  Src = 0;
  if ( !a1 || !a2 || (v5 = a1 + 668, a1 == (char *)-668LL) || !a3 )
  {
    appended = 87;
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 59, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
    goto LABEL_59;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 60, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *((_QWORD *)a1 + 7));
  memset_0(v44, 0, 0xC8u);
  memset_0(v45, 0, 0xC8u);
  v6 = *a2;
  *v5 = 11;
  *(_WORD *)(v5 + 1) = v6;
  v5[3] = *((_BYTE *)a2 + 2);
  v38 = (__int64)(v5 + 4);
  v36 = 4;
  appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v36, &v38, v4 + 4763);
  if ( !appended )
  {
    AddToArray((__int64)v44, v7, &v37, 8);
    v10 = v9 - 7;
    if ( !*(_DWORD *)(v4 + 9032)
      || (!g_fVelocityDhcpv6ContextBitfieldUpdate
        ? (v11 = v10 & (*(_DWORD *)(v4 + 8860) >> 5))
        : (v11 = *(_DWORD *)(v4 + 8880)),
          !v11) )
    {
      appended = Dhcpv6AppendOption((void *)(v4 + 456), 0x10u, v10, &v36, &v38, v4 + 4763);
      if ( appended )
        goto LABEL_59;
      AddToArray((__int64)v44, v12, &v37, v10);
    }
    if ( !*(_DWORD *)(v4 + 9032) )
    {
      appended = Dhcpv6AppendDefaultVendorClassOption(&v36, (u_short **)&v38, v4 + 4763);
      if ( appended )
        goto LABEL_59;
      AddToArray((__int64)v44, v13, &v37, 16);
      a1 = *(char **)(v4 + 656);
      if ( a1 )
      {
        appended = Dhcpv6AppendUserClassOption(a1, *(unsigned __int8 *)(v4 + 664), v14, &v36, &v38, v4 + 4763);
        if ( appended )
          goto LABEL_59;
        AddToArray((__int64)v44, v15, &v37, 15);
      }
    }
    if ( !v38 || v4 == -4763 )
    {
      appended = 87;
    }
    else
    {
      v16 = *v5 == 11;
      v17 = (_QWORD *)(v4 + 616);
      v18 = *(_QWORD *)(v4 + 656);
      v19 = *(_DWORD *)(v4 + 664);
      v41 = v18;
      Src = v19;
      if ( v16 )
      {
        for ( i = (_QWORD *)*v17; i != v17; i = (_QWORD *)*i )
        {
          if ( *((_WORD *)i + 8) == 6 )
          {
            if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
            {
              v21 = (_WORD *)i[6];
              if ( !v21 || *((_DWORD *)i + 14) != 2 )
                continue;
            }
            else
            {
              if ( *((_DWORD *)i + 14) != 2 )
                continue;
              v21 = (_WORD *)i[6];
            }
            if ( *v21 == 15 )
            {
              v22 = Dhcpv6AppendParamUserClass(&v38, &v36, v4 + 4763);
              goto LABEL_35;
            }
          }
        }
      }
      v22 = Dhcpv6AppendParamRequestList(v4, (_QWORD **)(v4 + 616), v18, v19, &v38, &v36, v4 + 4763);
LABEL_35:
      appended = v22;
      if ( !v22 )
      {
        v24 = &v46;
        AddToArray((__int64)v44, v23, &v37, 6);
        v26 = (_QWORD *)*v17;
        if ( (_QWORD *)*v17 != v17 )
        {
          do
          {
            v27 = v45;
            v28 = *((_DWORD *)v26 + 5);
            v29 = *((_WORD *)v26 + 8);
            v42 = (_QWORD *)*v26;
            if ( !v28 )
              v27 = v44;
            if ( !(unsigned int)IsPresentInArray((__int64)v27, 0, v25, v29)
              && v31 != 6
              && (!*((_DWORD *)v26 + 8) || *((_DWORD *)v26 + 8) == Src && v26[3] == v41) )
            {
              if ( v32 )
              {
                if ( !(unsigned int)IsPresentInArray((__int64)v44, 0, v25, 17) )
                {
                  AddToArray((__int64)v45, v33, &v40, v34);
                  *(_WORD *)v24 = *((_WORD *)v26 + 8);
                  *((_WORD *)v24 + 1) = *((_WORD *)v26 + 28);
                  memcpy_0(v24 + 4, (const void *)v26[6], *((unsigned int *)v26 + 14));
                  v24 += *((unsigned int *)v26 + 14) + 4;
                }
              }
              else
              {
                AddToArray((__int64)v44, v30, &v37, v31);
                appended = Dhcpv6AppendOption(
                             (void *)v26[6],
                             *((_WORD *)v26 + 28),
                             *((_WORD *)v26 + 8),
                             &v36,
                             &v38,
                             v4 + 4763);
                if ( appended )
                  goto LABEL_53;
              }
            }
            v26 = v42;
          }
          while ( v42 != v17 );
          goto LABEL_56;
        }
        goto LABEL_55;
      }
    }
LABEL_53:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 34, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, appended);
LABEL_55:
    if ( !appended )
    {
LABEL_56:
      *v43 = v36;
      return appended;
    }
  }
LABEL_59:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorCreatingPacket, *(unsigned int *)(v4 + 48), appended);
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 61, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, appended);
  return appended;
}

```

## disassembly

```asm
0x180013b6c  mov     [rsp-8+arg_8], rbx
0x180013b71  push    rbp
0x180013b72  push    rsi
0x180013b73  push    rdi
0x180013b74  push    r12
0x180013b76  push    r13
0x180013b78  push    r14
0x180013b7a  push    r15
0x180013b7c  lea     rbp, [rsp-1120h]
0x180013b84  mov     eax, 1220h
0x180013b89  call    _alloca_probe
0x180013b8e  sub     rsp, rax
0x180013b91  mov     rax, cs:__security_cookie
0x180013b98  xor     rax, rsp
0x180013b9b  mov     [rbp+1150h+var_40], rax
0x180013ba2  xor     r13d, r13d
0x180013ba5  mov     rax, r8
0x180013ba8  mov     [rsp+1250h+var_11E8], rax
0x180013bad  mov     rdi, rdx
0x180013bb0  mov     [rsp+1250h+var_120C], r13d
0x180013bb5  mov     rsi, rcx
0x180013bb8  mov     [rsp+1250h+var_11FC], r13d
0x180013bbd  mov     [rsp+1250h+Src], r13d
0x180013bc2  test    rcx, rcx
0x180013bc5  jz      loc_180013FD4
0x180013bcb  test    rdx, rdx
0x180013bce  jz      loc_180013FD4
0x180013bd4  lea     rbx, [rcx+29Ch]
0x180013bdb  test    rbx, rbx
0x180013bde  jz      loc_180013FD4
0x180013be4  test    rax, rax
0x180013be7  jz      loc_180013FD4
0x180013bed  lea     r15d, [r13+10h]
0x180013bf1  test    byte ptr cs:xmmword_1800423E0, r15b
0x180013bf8  jz      short loc_180013C13
0x180013bfa  mov     r9, [rsi+38h]
0x180013bfe  lea     edx, [r13+3Ch]
0x180013c02  mov     ecx, 404h
0x180013c07  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013c0e  call    WPP_SF_S
0x180013c13  mov     r14d, 0C8h
0x180013c19  lea     rcx, [rsp+1250h+var_11E0]; void *
0x180013c1e  mov     r8d, r14d; Size
0x180013c21  xor     edx, edx; Val
0x180013c23  call    memset_0
0x180013c28  mov     r8d, r14d; Size
0x180013c2b  lea     rcx, [rbp+1150h+var_1110]; void *
0x180013c2f  xor     edx, edx; Val
0x180013c31  call    memset_0
0x180013c36  movzx   eax, word ptr [rdi]
0x180013c39  lea     r12, [rsi+129Bh]
0x180013c40  mov     ecx, 4
0x180013c45  mov     byte ptr [rbx], 0Bh
0x180013c48  mov     [rbx+1], ax
0x180013c4c  lea     r9, [rsp+1250h+var_1210]
0x180013c51  mov     al, [rdi+2]
0x180013c54  mov     edx, ecx
0x180013c56  mov     [rbx+3], al
0x180013c59  lea     rax, [rbx+4]
0x180013c5d  lea     r14d, [rcx+4]
0x180013c61  mov     [rsp+1250h+var_1208], rax
0x180013c66  lea     rax, [rsp+1250h+var_1208]
0x180013c6b  mov     [rsp+1250h+var_1210], ecx
0x180013c6f  mov     r8d, r14d
0x180013c72  mov     [rsp+1250h+var_1228], r12; __int64
0x180013c77  lea     rcx, [rsp+1250h+Src]; Src
0x180013c7c  mov     [rsp+1250h+var_1230], rax; __int64
0x180013c81  call    Dhcpv6AppendOption
0x180013c86  mov     edi, eax
0x180013c88  test    eax, eax
0x180013c8a  jnz     loc_180013FF9
0x180013c90  mov     r9d, r14d
0x180013c93  lea     r8, [rsp+1250h+var_120C]
0x180013c98  lea     rcx, [rsp+1250h+var_11E0]
0x180013c9d  call    AddToArray
0x180013ca2  lea     r14d, [r9-7]
0x180013ca6  cmp     [rsi+2348h], r13d
0x180013cad  jz      short loc_180013CD0
0x180013caf  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r13d
0x180013cb6  jz      short loc_180013CC0
0x180013cb8  mov     eax, [rsi+22B0h]
0x180013cbe  jmp     short loc_180013CCC
0x180013cc0  mov     eax, [rsi+229Ch]
0x180013cc6  shr     eax, 5
0x180013cc9  and     eax, r14d
0x180013ccc  test    eax, eax
0x180013cce  jnz     short loc_180013D12
0x180013cd0  lea     rax, [rsp+1250h+var_1208]
0x180013cd5  mov     [rsp+1250h+var_1228], r12; __int64
0x180013cda  mov     r8d, r14d
0x180013cdd  mov     [rsp+1250h+var_1230], rax; __int64
0x180013ce2  mov     edx, r15d
0x180013ce5  lea     rcx, [rsi+1C8h]; Src
0x180013cec  lea     r9, [rsp+1250h+var_1210]
0x180013cf1  call    Dhcpv6AppendOption
0x180013cf6  mov     edi, eax
0x180013cf8  test    eax, eax
0x180013cfa  jnz     loc_180013FF9
0x180013d00  mov     r9d, r14d
0x180013d03  lea     r8, [rsp+1250h+var_120C]
0x180013d08  lea     rcx, [rsp+1250h+var_11E0]
0x180013d0d  call    AddToArray
0x180013d12  mov     r14d, 0Fh
0x180013d18  cmp     [rsi+2348h], r13d
0x180013d1f  jnz     short loc_180013D97
0x180013d21  mov     r8, r12
0x180013d24  lea     rdx, [rsp+1250h+var_1208]
0x180013d29  lea     rcx, [rsp+1250h+var_1210]
0x180013d2e  call    Dhcpv6AppendDefaultVendorClassOption
0x180013d33  mov     edi, eax
0x180013d35  test    eax, eax
0x180013d37  jnz     loc_180013FF9
0x180013d3d  mov     r9d, r15d
0x180013d40  lea     r8, [rsp+1250h+var_120C]
0x180013d45  lea     rcx, [rsp+1250h+var_11E0]
0x180013d4a  call    AddToArray
0x180013d4f  mov     rcx, [rsi+290h]; Src
0x180013d56  test    rcx, rcx
0x180013d59  jz      short loc_180013D97
0x180013d5b  movzx   edx, byte ptr [rsi+298h]
0x180013d62  lea     rax, [rsp+1250h+var_1208]
0x180013d67  mov     [rsp+1250h+var_1228], r12; __int64
0x180013d6c  lea     r9, [rsp+1250h+var_1210]
0x180013d71  mov     [rsp+1250h+var_1230], rax; __int64
0x180013d76  call    Dhcpv6AppendUserClassOption
0x180013d7b  mov     edi, eax
0x180013d7d  test    eax, eax
0x180013d7f  jnz     loc_180013FF9
0x180013d85  mov     r9d, r14d
0x180013d88  lea     r8, [rsp+1250h+var_120C]
0x180013d8d  lea     rcx, [rsp+1250h+var_11E0]
0x180013d92  call    AddToArray
0x180013d97  cmp     [rsp+1250h+var_1208], r13
0x180013d9c  jz      loc_180013F9C
0x180013da2  test    r12, r12
0x180013da5  jz      loc_180013F9C
0x180013dab  cmp     byte ptr [rbx], 0Bh
0x180013dae  lea     r15, [rsi+268h]
0x180013db5  mov     rdx, [rsi+290h]
0x180013dbc  mov     eax, 6
0x180013dc1  mov     r8d, [rsi+298h]
0x180013dc8  mov     [rsp+1250h+var_11F8], rdx
0x180013dcd  mov     [rsp+1250h+Src], r8d
0x180013dd2  jnz     short loc_180013E1A
0x180013dd4  mov     rcx, [r15]
0x180013dd7  jmp     short loc_180013E15
0x180013dd9  cmp     ax, [rcx+10h]
0x180013ddd  jnz     short loc_180013E12
0x180013ddf  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, r13d
0x180013de6  jz      short loc_180013DF9
0x180013de8  mov     rax, [rcx+30h]
0x180013dec  test    rax, rax
0x180013def  jz      short loc_180013E0D
0x180013df1  cmp     dword ptr [rcx+38h], 2
0x180013df5  jnz     short loc_180013E0D
0x180013df7  jmp     short loc_180013E03
0x180013df9  cmp     dword ptr [rcx+38h], 2
0x180013dfd  jnz     short loc_180013E12
0x180013dff  mov     rax, [rcx+30h]
0x180013e03  cmp     [rax], r14w
0x180013e07  jz      loc_180013F20
0x180013e0d  mov     eax, 6
0x180013e12  mov     rcx, [rcx]
0x180013e15  cmp     rcx, r15
0x180013e18  jnz     short loc_180013DD9
0x180013e1a  lea     rax, [rsp+1250h+var_1210]
0x180013e1f  mov     [rsp+1250h+var_1220], r12
0x180013e24  mov     [rsp+1250h+var_1228], rax
0x180013e29  mov     r9d, r8d
0x180013e2c  lea     rax, [rsp+1250h+var_1208]
0x180013e31  mov     r8, rdx
0x180013e34  mov     rdx, r15
0x180013e37  mov     [rsp+1250h+var_1230], rax
0x180013e3c  mov     rcx, rsi
0x180013e3f  call    Dhcpv6AppendParamRequestList
0x180013e44  mov     edi, eax
0x180013e46  test    eax, eax
0x180013e48  jnz     loc_180013FA1
0x180013e4e  lea     ebx, [rax+6]
0x180013e51  mov     r9d, ebx
0x180013e54  lea     r8, [rsp+1250h+var_120C]
0x180013e59  lea     rcx, [rsp+1250h+var_11E0]
0x180013e5e  lea     r13, [rbp+1150h+var_1040]
0x180013e65  call    AddToArray
0x180013e6a  mov     r14, [r15]
0x180013e6d  cmp     r14, r15
0x180013e70  jz      loc_180013FC3
0x180013e76  mov     rax, [r14]
0x180013e79  lea     rcx, [rbp+1150h+var_1110]
0x180013e7d  mov     r11d, [r14+14h]
0x180013e81  xor     edx, edx
0x180013e83  movzx   r10d, word ptr [r14+10h]
0x180013e88  mov     [rsp+1250h+var_11F0], rax
0x180013e8d  movzx   r9d, r10w
0x180013e91  test    r11d, r11d
0x180013e94  jnz     short loc_180013E9B
0x180013e96  lea     rcx, [rsp+1250h+var_11E0]
0x180013e9b  call    IsPresentInArray
0x180013ea0  test    eax, eax
0x180013ea2  jnz     loc_180013F8C
0x180013ea8  cmp     r10w, bx
0x180013eac  jz      loc_180013F8C
0x180013eb2  cmp     [r14+20h], eax
0x180013eb6  jz      short loc_180013ED5
0x180013eb8  mov     eax, [rsp+1250h+Src]
0x180013ebc  cmp     [r14+20h], eax
0x180013ec0  jnz     loc_180013F8C
0x180013ec6  mov     rax, [rsp+1250h+var_11F8]
0x180013ecb  cmp     [r14+18h], rax
0x180013ecf  jnz     loc_180013F8C
0x180013ed5  lea     rcx, [rsp+1250h+var_11E0]
0x180013eda  test    r11d, r11d
0x180013edd  jnz     short loc_180013F37
0x180013edf  movzx   r9d, r10w
0x180013ee3  lea     r8, [rsp+1250h+var_120C]
0x180013ee8  call    AddToArray
0x180013eed  movzx   r8d, word ptr [r14+10h]
0x180013ef2  lea     rax, [rsp+1250h+var_1208]
0x180013ef7  movzx   edx, word ptr [r14+38h]
0x180013efc  lea     r9, [rsp+1250h+var_1210]
0x180013f01  mov     rcx, [r14+30h]; Src
0x180013f05  mov     [rsp+1250h+var_1228], r12; __int64
0x180013f0a  mov     [rsp+1250h+var_1230], rax; __int64
0x180013f0f  call    Dhcpv6AppendOption
0x180013f14  mov     edi, eax
0x180013f16  test    eax, eax
0x180013f18  jnz     loc_180013FA1
0x180013f1e  jmp     short loc_180013F8C
0x180013f20  mov     r8, r12
0x180013f23  lea     rdx, [rsp+1250h+var_1210]
0x180013f28  lea     rcx, [rsp+1250h+var_1208]
0x180013f2d  call    Dhcpv6AppendParamUserClass
0x180013f32  jmp     loc_180013E44
0x180013f37  xor     edx, edx
0x180013f39  lea     r9d, [rdx+11h]
0x180013f3d  call    IsPresentInArray
0x180013f42  test    eax, eax
0x180013f44  jnz     short loc_180013F8C
0x180013f46  movzx   r9d, r10w
0x180013f4a  lea     r8, [rsp+1250h+var_11FC]
0x180013f4f  lea     rcx, [rbp+1150h+var_1110]
0x180013f53  call    AddToArray
0x180013f58  movzx   ecx, word ptr [r14+10h]
0x180013f5d  lea     rbx, [r13+4]
0x180013f61  mov     [r13+0], cx
0x180013f66  mov     rcx, rbx; void *
0x180013f69  movzx   eax, word ptr [r14+38h]
0x180013f6e  mov     [r13+2], ax
0x180013f73  mov     r8d, [r14+38h]; Size
0x180013f77  mov     rdx, [r14+30h]; Src
0x180013f7b  call    memcpy_0
0x180013f80  mov     r13d, [r14+38h]
0x180013f84  add     r13, rbx
0x180013f87  mov     ebx, 6
0x180013f8c  mov     r14, [rsp+1250h+var_11F0]
0x180013f91  cmp     r14, r15
0x180013f94  jnz     loc_180013E76
0x180013f9a  jmp     short loc_180013FC7
0x180013f9c  mov     edi, 57h ; 'W'
0x180013fa1  test    byte ptr cs:xmmword_1800423E0, 2
0x180013fa8  jz      short loc_180013FC3
0x180013faa  mov     edx, 22h ; '"'
0x180013faf  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180013fb6  mov     ecx, 401h
0x180013fbb  mov     r9d, edi
0x180013fbe  call    WPP_SF_D
0x180013fc3  test    edi, edi
0x180013fc5  jnz     short loc_180013FF9
0x180013fc7  mov     rcx, [rsp+1250h+var_11E8]
0x180013fcc  mov     eax, [rsp+1250h+var_1210]
0x180013fd0  mov     [rcx], eax
0x180013fd2  jmp     short loc_180014037
0x180013fd4  mov     edi, 57h ; 'W'
0x180013fd9  test    byte ptr cs:xmmword_1800423E0, 2
0x180013fe0  jz      short loc_180013FF9
0x180013fe2  lea     edx, [rdi-1Ch]
0x180013fe5  mov     ecx, 401h
0x180013fea  mov     r9d, edi
0x180013fed  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180013ff4  call    WPP_SF_D
0x180013ff9  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180014000  jz      short loc_180014015
0x180014002  mov     r8d, [rsi+30h]
0x180014006  lea     rdx, ErrorCreatingPacket
0x18001400d  mov     r9d, edi
0x180014010  call    McTemplateU0qq_EtwEventWriteTransfer
0x180014015  test    byte ptr cs:xmmword_1800423E0, 2
0x18001401c  jz      short loc_180014037
0x18001401e  mov     edx, 3Dh ; '='
0x180014023  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001402a  mov     ecx, 401h
0x18001402f  mov     r9d, edi
0x180014032  call    WPP_SF_D
0x180014037  mov     eax, edi
0x180014039  mov     rcx, [rbp+1150h+var_40]
0x180014040  xor     rcx, rsp; StackCookie
0x180014043  call    __security_check_cookie
0x180014048  mov     rbx, [rsp+1250h+arg_8]
0x180014050  add     rsp, 1220h
0x180014057  pop     r15
  ... truncated ...
```
