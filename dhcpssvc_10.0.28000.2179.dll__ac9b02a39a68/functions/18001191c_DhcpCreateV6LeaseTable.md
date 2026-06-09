# DhcpCreateV6LeaseTable

- ea: `0x18001191c`
- end: `0x180011d5e`
- name: `DhcpCreateV6LeaseTable`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012c90`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x18000e814`
- `0x18001191c`
- `0x180014cf8`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetCreateIndex` at `0x180011b67`
- `ESENT!JetCreateIndex` at `0x180011c2b`
- `ESENT!JetCreateIndex` at `0x180011cd4`
- `ESENT!JetCreateIndex` at `0x180011b67`
- `ESENT!JetCreateIndex` at `0x180011c2b`
- `ESENT!JetCreateIndex` at `0x180011cd4`
- `ESENT!JetCreateTable` at `0x1800119b8`
- `ESENT!JetCreateTable` at `0x1800119b8`
- `ESENT!JetAddColumn` at `0x180011acc`
- `ESENT!JetAddColumn` at `0x180011acc`

## string_xrefs

- `0x1800119c6`: `DhcpCreateV6LeaseTable:JetCreateTable`
- `0x180011ada`: `DhcpCreateV6LeaseTable:JetAddColumn`
- `0x180011b73`: `DhcpCreateV6LeaseTable:JetCreateIndex`

## pseudocode

```c
__int64 DhcpCreateV6LeaseTable()
{
  unsigned int Table; // eax
  unsigned int v2; // eax
  unsigned int v3; // ebp
  char **v4; // r8
  unsigned int v5; // r14d
  __int64 v6; // r15
  unsigned int v7; // eax
  unsigned int Index; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // [rsp+40h] [rbp-58h] BYREF
  int v16; // [rsp+48h] [rbp-50h]
  int v17; // [rsp+4Ch] [rbp-4Ch]
  __int64 v18; // [rsp+50h] [rbp-48h]
  int v19; // [rsp+58h] [rbp-40h]

  if ( DhcpGlobalDatabaseHandle )
  {
    Table = JetCreateTable(
              DhcpGlobalJetServerSession,
              DhcpGlobalDatabaseHandle,
              "LeaseTable",
              10,
              80,
              &DhcpGlobalClientTableV6Handle);
    v2 = DhcpMapJetError(Table, "DhcpCreateV6LeaseTable:JetCreateTable");
    v3 = v2;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_41653652a8cc332f218bba10df165c1f_Traceguids, v2);
      return v3;
    }
    v4 = &off_1800F8090;
    DhcpGlobalClientTableV6 = (__int64)&off_1800F8090;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_41653652a8cc332f218bba10df165c1f_Traceguids);
      v4 = (char **)DhcpGlobalClientTableV6;
    }
    v15 = 28;
    v17 = 67698689;
    v5 = 0;
    v18 = 1252;
    v6 = 0;
    do
    {
      v16 = HIDWORD(v4[v6 + 1]);
      v19 = 0;
      v7 = JetAddColumn(DhcpGlobalJetServerSession, DhcpGlobalClientTableV6Handle, v4[v6], &v15, 0, 0, &v4[2 * v5 + 1]);
      v3 = DhcpMapJetError(v7, "DhcpCreateV6LeaseTable:JetAddColumn");
      if ( v3 )
        return v3;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
          *(_QWORD *)(v6 * 8 + DhcpGlobalClientTableV6));
      v4 = (char **)DhcpGlobalClientTableV6;
      ++v5;
      v6 += 2;
    }
    while ( v5 < 0xD );
    Index = JetCreateIndex(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableV6Handle,
              *(_QWORD *)DhcpGlobalClientTableV6,
              3,
              "+Ipv6Address",
              14,
              50);
    v9 = DhcpMapJetError(Index, "DhcpCreateV6LeaseTable:JetCreateIndex");
    v3 = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v11 = 33;
LABEL_23:
        WPP_SF_ls(
          v10[2],
          v11,
          (unsigned int)&WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
          v9,
          (__int64)"Ipv6Address");
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          &WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
          "Ipv6Address");
      v12 = JetCreateIndex(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableV6Handle,
              *(_QWORD *)(DhcpGlobalClientTableV6 + 16),
              8,
              "+ClientDUID",
              13,
              50);
      v13 = DhcpMapJetError(v12, "DhcpCreateV6LeaseTable:JetCreateIndex");
      v3 = v13;
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_ls(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)&WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
            v13,
            (__int64)"ClientDUID");
        return v3;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
          "ClientDUID");
      v14 = JetCreateIndex(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableV6Handle,
              *(_QWORD *)(DhcpGlobalClientTableV6 + 96),
              0,
              "+State",
              8,
              50);
      v9 = DhcpMapJetError(v14, "DhcpCreateV6LeaseTable:JetCreateIndex");
      v3 = v9;
      if ( !v9 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_41653652a8cc332f218bba10df165c1f_Traceguids,
            "Ipv6Address");
        return v3;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        v11 = 37;
        goto LABEL_23;
      }
    }
    return v3;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_41653652a8cc332f218bba10df165c1f_Traceguids);
  return 1627;
}

```

## disassembly

```asm
0x18001191c  mov     [rsp+arg_0], rbx
0x180011921  mov     [rsp+arg_8], rbp
0x180011926  mov     [rsp+arg_10], rsi
0x18001192b  push    rdi
0x18001192c  push    r12
0x18001192e  push    r13
0x180011930  push    r14
0x180011932  push    r15
0x180011934  sub     rsp, 70h
0x180011938  mov     rax, cs:__security_cookie
0x18001193f  xor     rax, rsp
0x180011942  mov     [rsp+98h+var_38], rax
0x180011947  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18001194d  xor     r12d, r12d
0x180011950  test    edx, edx
0x180011952  jnz     short loc_180011990
0x180011954  mov     rcx, cs:WPP_GLOBAL_Control
0x18001195b  lea     rdi, WPP_GLOBAL_Control
0x180011962  cmp     rcx, rdi
0x180011965  jz      short loc_180011986
0x180011967  mov     ebx, 800h
0x18001196c  test    [rcx+1Ch], ebx
0x18001196f  jz      short loc_180011986
0x180011971  mov     rcx, [rcx+10h]
0x180011975  lea     edx, [r12+1Dh]
0x18001197a  lea     r8, WPP_41653652a8cc332f218bba10df165c1f_Traceguids
0x180011981  call    WPP_SF_
0x180011986  mov     eax, 65Bh
0x18001198b  jmp     loc_180011D32
0x180011990  mov     rcx, cs:DhcpGlobalJetServerSession
0x180011997  lea     rax, DhcpGlobalClientTableV6Handle
0x18001199e  mov     [rsp+98h+var_70], rax
0x1800119a3  lea     r8, aLeasetable; "LeaseTable"
0x1800119aa  mov     r9d, 0Ah
0x1800119b0  mov     dword ptr [rsp+98h+var_78], 50h ; 'P'
0x1800119b8  call    cs:__imp_JetCreateTable
0x1800119bf  nop     dword ptr [rax+rax+00h]
0x1800119c4  mov     ecx, eax
0x1800119c6  lea     rdx, aDhcpcreatev6le_0; "DhcpCreateV6LeaseTable:JetCreateTable"
0x1800119cd  call    DhcpMapJetError
0x1800119d2  mov     ebp, eax
0x1800119d4  test    eax, eax
0x1800119d6  jz      short loc_180011A1A
0x1800119d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119df  lea     rdi, WPP_GLOBAL_Control
0x1800119e6  cmp     rcx, rdi
0x1800119e9  jz      loc_180011D30
0x1800119ef  mov     ebx, 800h
0x1800119f4  test    [rcx+1Ch], ebx
0x1800119f7  jz      loc_180011D30
0x1800119fd  mov     rcx, [rcx+10h]
0x180011a01  lea     r8, WPP_41653652a8cc332f218bba10df165c1f_Traceguids
0x180011a08  mov     edx, 1Eh
0x180011a0d  mov     r9d, eax
0x180011a10  call    WPP_SF_D
0x180011a15  jmp     loc_180011D30
0x180011a1a  lea     r8, off_1800F8090; "Ipv6Address"
0x180011a21  mov     cs:DhcpGlobalClientTableV6, r8
0x180011a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a2f  lea     rdi, WPP_GLOBAL_Control
0x180011a36  lea     rsi, WPP_41653652a8cc332f218bba10df165c1f_Traceguids
0x180011a3d  mov     ebx, 800h
0x180011a42  cmp     rcx, rdi
0x180011a45  jz      short loc_180011A64
0x180011a47  test    [rcx+1Ch], ebx
0x180011a4a  jz      short loc_180011A64
0x180011a4c  mov     rcx, [rcx+10h]
0x180011a50  mov     edx, 1Fh
0x180011a55  mov     r8, rsi
0x180011a58  call    WPP_SF_
0x180011a5d  mov     r8, cs:DhcpGlobalClientTableV6
0x180011a64  mov     [rsp+98h+var_58], 1Ch
0x180011a6d  mov     r13d, 1
0x180011a73  mov     [rsp+98h+var_4C], 4090001h
0x180011a7b  mov     r14d, r12d
0x180011a7e  mov     [rsp+98h+var_48], 4E4h
0x180011a87  mov     r15, r12
0x180011a8a  mov     eax, [r15+r8+0Ch]
0x180011a8f  lea     r9, [rsp+98h+var_58]
0x180011a94  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180011a9b  mov     rcx, cs:DhcpGlobalJetServerSession
0x180011aa2  mov     [rsp+98h+var_50], eax
0x180011aa6  mov     [rsp+98h+var_40], r12d
0x180011aab  mov     eax, r14d
0x180011aae  shl     rax, 4
0x180011ab2  add     rax, 8
0x180011ab6  add     rax, r8
0x180011ab9  mov     r8, [r15+r8]
0x180011abd  mov     [rsp+98h+var_68], rax
0x180011ac2  mov     dword ptr [rsp+98h+var_70], r12d
0x180011ac7  mov     [rsp+98h+var_78], r12
0x180011acc  call    cs:__imp_JetAddColumn
0x180011ad3  nop     dword ptr [rax+rax+00h]
0x180011ad8  mov     ecx, eax
0x180011ada  lea     rdx, aDhcpcreatev6le_1; "DhcpCreateV6LeaseTable:JetAddColumn"
0x180011ae1  call    DhcpMapJetError
0x180011ae6  mov     ebp, eax
0x180011ae8  test    eax, eax
0x180011aea  jnz     loc_180011D30
0x180011af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011af7  cmp     rcx, rdi
0x180011afa  jz      short loc_180011B1B
0x180011afc  test    [rcx+1Ch], ebx
0x180011aff  jz      short loc_180011B1B
0x180011b01  mov     r9, cs:DhcpGlobalClientTableV6
0x180011b08  lea     edx, [rax+20h]
0x180011b0b  mov     rcx, [rcx+10h]
0x180011b0f  mov     r8, rsi
0x180011b12  mov     r9, [r15+r9]
0x180011b16  call    WPP_SF_s
0x180011b1b  mov     r8, cs:DhcpGlobalClientTableV6
0x180011b22  add     r14d, r13d
0x180011b25  add     r15, 10h
0x180011b29  cmp     r14d, 0Dh
0x180011b2d  jb      loc_180011A8A
0x180011b33  mov     r8, [r8]
0x180011b36  lea     rax, aIpv6address_0; "+Ipv6Address"
0x180011b3d  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180011b44  mov     r15d, 32h ; '2'
0x180011b4a  mov     rcx, cs:DhcpGlobalJetServerSession
0x180011b51  mov     dword ptr [rsp+98h+var_68], r15d
0x180011b56  mov     dword ptr [rsp+98h+var_70], 0Eh
0x180011b5e  lea     r9d, [r15-2Fh]
0x180011b62  mov     [rsp+98h+var_78], rax
0x180011b67  call    cs:__imp_JetCreateIndex
0x180011b6e  nop     dword ptr [rax+rax+00h]
0x180011b73  lea     r13, aDhcpcreatev6le; "DhcpCreateV6LeaseTable:JetCreateIndex"
0x180011b7a  mov     ecx, eax
0x180011b7c  mov     rdx, r13
0x180011b7f  call    DhcpMapJetError
0x180011b84  mov     ebp, eax
0x180011b86  test    eax, eax
0x180011b88  jz      short loc_180011BC7
0x180011b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b91  cmp     rcx, rdi
0x180011b94  jz      loc_180011D30
0x180011b9a  test    [rcx+1Ch], ebx
0x180011b9d  jz      loc_180011D30
0x180011ba3  lea     edx, [r15-11h]
0x180011ba7  lea     r14, aIpv6address; "Ipv6Address"
0x180011bae  mov     [rsp+98h+var_78], r14
0x180011bb3  mov     rcx, [rcx+10h]
0x180011bb7  mov     r9d, eax
0x180011bba  mov     r8, rsi
0x180011bbd  call    WPP_SF_ls
0x180011bc2  jmp     loc_180011D30
0x180011bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bce  lea     r14, aIpv6address; "Ipv6Address"
0x180011bd5  cmp     rcx, rdi
0x180011bd8  jz      short loc_180011BF3
0x180011bda  test    [rcx+1Ch], ebx
0x180011bdd  jz      short loc_180011BF3
0x180011bdf  mov     rcx, [rcx+10h]
0x180011be3  mov     edx, 22h ; '"'
0x180011be8  mov     r9, r14
0x180011beb  mov     r8, rsi
0x180011bee  call    WPP_SF_s
0x180011bf3  mov     r8, cs:DhcpGlobalClientTableV6
0x180011bfa  lea     rax, aClientduid; "+ClientDUID"
0x180011c01  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180011c08  mov     r9d, 8
0x180011c0e  mov     rcx, cs:DhcpGlobalJetServerSession
0x180011c15  mov     dword ptr [rsp+98h+var_68], r15d
0x180011c1a  mov     r8, [r8+10h]
0x180011c1e  mov     dword ptr [rsp+98h+var_70], 0Dh
0x180011c26  mov     [rsp+98h+var_78], rax
0x180011c2b  call    cs:__imp_JetCreateIndex
0x180011c32  nop     dword ptr [rax+rax+00h]
0x180011c37  mov     ecx, eax
0x180011c39  mov     rdx, r13
0x180011c3c  call    DhcpMapJetError
0x180011c41  mov     ebp, eax
0x180011c43  test    eax, eax
0x180011c45  jz      short loc_180011C76
0x180011c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c4e  cmp     rcx, rdi
0x180011c51  jz      loc_180011D30
0x180011c57  test    [rcx+1Ch], ebx
0x180011c5a  jz      loc_180011D30
0x180011c60  lea     r9, aClientduid_2; "ClientDUID"
0x180011c67  mov     edx, 23h ; '#'
0x180011c6c  mov     [rsp+98h+var_78], r9
0x180011c71  jmp     loc_180011BB3
0x180011c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c7d  cmp     rcx, rdi
0x180011c80  jz      short loc_180011C9F
0x180011c82  test    [rcx+1Ch], ebx
0x180011c85  jz      short loc_180011C9F
0x180011c87  mov     rcx, [rcx+10h]
0x180011c8b  lea     r9, aClientduid_2; "ClientDUID"
0x180011c92  mov     edx, 24h ; '$'
0x180011c97  mov     r8, rsi
0x180011c9a  call    WPP_SF_s
0x180011c9f  mov     r8, cs:DhcpGlobalClientTableV6
0x180011ca6  lea     rax, aState_0; "+State"
0x180011cad  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180011cb4  xor     r9d, r9d
0x180011cb7  mov     rcx, cs:DhcpGlobalJetServerSession
0x180011cbe  mov     dword ptr [rsp+98h+var_68], r15d
0x180011cc3  mov     r8, [r8+60h]
0x180011cc7  mov     dword ptr [rsp+98h+var_70], 8
0x180011ccf  mov     [rsp+98h+var_78], rax
0x180011cd4  call    cs:__imp_JetCreateIndex
0x180011cdb  nop     dword ptr [rax+rax+00h]
0x180011ce0  mov     ecx, eax
0x180011ce2  mov     rdx, r13
0x180011ce5  call    DhcpMapJetError
0x180011cea  mov     ebp, eax
0x180011cec  test    eax, eax
0x180011cee  jz      short loc_180011D0B
0x180011cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cf7  cmp     rcx, rdi
0x180011cfa  jz      short loc_180011D30
0x180011cfc  test    [rcx+1Ch], ebx
0x180011cff  jz      short loc_180011D30
0x180011d01  mov     edx, 25h ; '%'
0x180011d06  jmp     loc_180011BAE
0x180011d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d12  cmp     rcx, rdi
0x180011d15  jz      short loc_180011D30
0x180011d17  test    [rcx+1Ch], ebx
0x180011d1a  jz      short loc_180011D30
0x180011d1c  mov     rcx, [rcx+10h]
0x180011d20  mov     edx, 26h ; '&'
0x180011d25  mov     r9, r14
0x180011d28  mov     r8, rsi
0x180011d2b  call    WPP_SF_s
0x180011d30  mov     eax, ebp
0x180011d32  mov     rcx, [rsp+98h+var_38]
0x180011d37  xor     rcx, rsp; StackCookie
0x180011d3a  call    __security_check_cookie
0x180011d3f  lea     r11, [rsp+98h+var_28]
0x180011d44  mov     rbx, [r11+30h]
0x180011d48  mov     rbp, [r11+38h]
0x180011d4c  mov     rsi, [r11+40h]
0x180011d50  mov     rsp, r11
0x180011d53  pop     r15
0x180011d55  pop     r14
0x180011d57  pop     r13
0x180011d59  pop     r12
0x180011d5b  pop     rdi
0x180011d5c  retn
```
