# DhcpCreateV6LeaseTable

- ea: `0x1800121ec`
- end: `0x18001262e`
- name: `DhcpCreateV6LeaseTable`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013550`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x18000f144`
- `0x1800121ec`
- `0x180015588`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetCreateIndex` at `0x180012437`
- `ESENT!JetCreateIndex` at `0x1800124fb`
- `ESENT!JetCreateIndex` at `0x1800125a4`
- `ESENT!JetCreateIndex` at `0x180012437`
- `ESENT!JetCreateIndex` at `0x1800124fb`
- `ESENT!JetCreateIndex` at `0x1800125a4`
- `ESENT!JetCreateTable` at `0x180012288`
- `ESENT!JetCreateTable` at `0x180012288`
- `ESENT!JetAddColumn` at `0x18001239c`
- `ESENT!JetAddColumn` at `0x18001239c`

## string_xrefs

- `0x180012296`: `DhcpCreateV6LeaseTable:JetCreateTable`
- `0x1800123aa`: `DhcpCreateV6LeaseTable:JetAddColumn`
- `0x180012443`: `DhcpCreateV6LeaseTable:JetCreateIndex`

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
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids, v2);
      return v3;
    }
    v4 = &off_1800F6090;
    DhcpGlobalClientTableV6 = (__int64)&off_1800F6090;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids);
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
          &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
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
          (unsigned int)&WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
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
          &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
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
            (unsigned int)&WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
            v13,
            (__int64)"ClientDUID");
        return v3;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
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
            &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids,
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids);
  return 1627;
}

```

## disassembly

```asm
0x1800121ec  mov     [rsp+arg_0], rbx
0x1800121f1  mov     [rsp+arg_8], rbp
0x1800121f6  mov     [rsp+arg_10], rsi
0x1800121fb  push    rdi
0x1800121fc  push    r12
0x1800121fe  push    r13
0x180012200  push    r14
0x180012202  push    r15
0x180012204  sub     rsp, 70h
0x180012208  mov     rax, cs:__security_cookie
0x18001220f  xor     rax, rsp
0x180012212  mov     [rsp+98h+var_38], rax
0x180012217  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18001221d  xor     r12d, r12d
0x180012220  test    edx, edx
0x180012222  jnz     short loc_180012260
0x180012224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001222b  lea     rdi, WPP_GLOBAL_Control
0x180012232  cmp     rcx, rdi
0x180012235  jz      short loc_180012256
0x180012237  mov     ebx, 800h
0x18001223c  test    [rcx+1Ch], ebx
0x18001223f  jz      short loc_180012256
0x180012241  mov     rcx, [rcx+10h]
0x180012245  lea     edx, [r12+1Dh]
0x18001224a  lea     r8, WPP_3c7468642838320b8afbb5ce47767e51_Traceguids
0x180012251  call    WPP_SF_
0x180012256  mov     eax, 65Bh
0x18001225b  jmp     loc_180012602
0x180012260  mov     rcx, cs:DhcpGlobalJetServerSession
0x180012267  lea     rax, DhcpGlobalClientTableV6Handle
0x18001226e  mov     [rsp+98h+var_70], rax
0x180012273  lea     r8, aLeasetable; "LeaseTable"
0x18001227a  mov     r9d, 0Ah
0x180012280  mov     dword ptr [rsp+98h+var_78], 50h ; 'P'
0x180012288  call    cs:__imp_JetCreateTable
0x18001228f  nop     dword ptr [rax+rax+00h]
0x180012294  mov     ecx, eax
0x180012296  lea     rdx, aDhcpcreatev6le_0; "DhcpCreateV6LeaseTable:JetCreateTable"
0x18001229d  call    DhcpMapJetError
0x1800122a2  mov     ebp, eax
0x1800122a4  test    eax, eax
0x1800122a6  jz      short loc_1800122EA
0x1800122a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122af  lea     rdi, WPP_GLOBAL_Control
0x1800122b6  cmp     rcx, rdi
0x1800122b9  jz      loc_180012600
0x1800122bf  mov     ebx, 800h
0x1800122c4  test    [rcx+1Ch], ebx
0x1800122c7  jz      loc_180012600
0x1800122cd  mov     rcx, [rcx+10h]
0x1800122d1  lea     r8, WPP_3c7468642838320b8afbb5ce47767e51_Traceguids
0x1800122d8  mov     edx, 1Eh
0x1800122dd  mov     r9d, eax
0x1800122e0  call    WPP_SF_D
0x1800122e5  jmp     loc_180012600
0x1800122ea  lea     r8, off_1800F6090; "Ipv6Address"
0x1800122f1  mov     cs:DhcpGlobalClientTableV6, r8
0x1800122f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122ff  lea     rdi, WPP_GLOBAL_Control
0x180012306  lea     rsi, WPP_3c7468642838320b8afbb5ce47767e51_Traceguids
0x18001230d  mov     ebx, 800h
0x180012312  cmp     rcx, rdi
0x180012315  jz      short loc_180012334
0x180012317  test    [rcx+1Ch], ebx
0x18001231a  jz      short loc_180012334
0x18001231c  mov     rcx, [rcx+10h]
0x180012320  mov     edx, 1Fh
0x180012325  mov     r8, rsi
0x180012328  call    WPP_SF_
0x18001232d  mov     r8, cs:DhcpGlobalClientTableV6
0x180012334  mov     [rsp+98h+var_58], 1Ch
0x18001233d  mov     r13d, 1
0x180012343  mov     [rsp+98h+var_4C], 4090001h
0x18001234b  mov     r14d, r12d
0x18001234e  mov     [rsp+98h+var_48], 4E4h
0x180012357  mov     r15, r12
0x18001235a  mov     eax, [r15+r8+0Ch]
0x18001235f  lea     r9, [rsp+98h+var_58]
0x180012364  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x18001236b  mov     rcx, cs:DhcpGlobalJetServerSession
0x180012372  mov     [rsp+98h+var_50], eax
0x180012376  mov     [rsp+98h+var_40], r12d
0x18001237b  mov     eax, r14d
0x18001237e  shl     rax, 4
0x180012382  add     rax, 8
0x180012386  add     rax, r8
0x180012389  mov     r8, [r15+r8]
0x18001238d  mov     [rsp+98h+var_68], rax
0x180012392  mov     dword ptr [rsp+98h+var_70], r12d
0x180012397  mov     [rsp+98h+var_78], r12
0x18001239c  call    cs:__imp_JetAddColumn
0x1800123a3  nop     dword ptr [rax+rax+00h]
0x1800123a8  mov     ecx, eax
0x1800123aa  lea     rdx, aDhcpcreatev6le_1; "DhcpCreateV6LeaseTable:JetAddColumn"
0x1800123b1  call    DhcpMapJetError
0x1800123b6  mov     ebp, eax
0x1800123b8  test    eax, eax
0x1800123ba  jnz     loc_180012600
0x1800123c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123c7  cmp     rcx, rdi
0x1800123ca  jz      short loc_1800123EB
0x1800123cc  test    [rcx+1Ch], ebx
0x1800123cf  jz      short loc_1800123EB
0x1800123d1  mov     r9, cs:DhcpGlobalClientTableV6
0x1800123d8  lea     edx, [rax+20h]
0x1800123db  mov     rcx, [rcx+10h]
0x1800123df  mov     r8, rsi
0x1800123e2  mov     r9, [r15+r9]
0x1800123e6  call    WPP_SF_s
0x1800123eb  mov     r8, cs:DhcpGlobalClientTableV6
0x1800123f2  add     r14d, r13d
0x1800123f5  add     r15, 10h
0x1800123f9  cmp     r14d, 0Dh
0x1800123fd  jb      loc_18001235A
0x180012403  mov     r8, [r8]
0x180012406  lea     rax, aIpv6address_0; "+Ipv6Address"
0x18001240d  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180012414  mov     r15d, 32h ; '2'
0x18001241a  mov     rcx, cs:DhcpGlobalJetServerSession
0x180012421  mov     dword ptr [rsp+98h+var_68], r15d
0x180012426  mov     dword ptr [rsp+98h+var_70], 0Eh
0x18001242e  lea     r9d, [r15-2Fh]
0x180012432  mov     [rsp+98h+var_78], rax
0x180012437  call    cs:__imp_JetCreateIndex
0x18001243e  nop     dword ptr [rax+rax+00h]
0x180012443  lea     r13, aDhcpcreatev6le; "DhcpCreateV6LeaseTable:JetCreateIndex"
0x18001244a  mov     ecx, eax
0x18001244c  mov     rdx, r13
0x18001244f  call    DhcpMapJetError
0x180012454  mov     ebp, eax
0x180012456  test    eax, eax
0x180012458  jz      short loc_180012497
0x18001245a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012461  cmp     rcx, rdi
0x180012464  jz      loc_180012600
0x18001246a  test    [rcx+1Ch], ebx
0x18001246d  jz      loc_180012600
0x180012473  lea     edx, [r15-11h]
0x180012477  lea     r14, aIpv6address; "Ipv6Address"
0x18001247e  mov     [rsp+98h+var_78], r14
0x180012483  mov     rcx, [rcx+10h]
0x180012487  mov     r9d, eax
0x18001248a  mov     r8, rsi
0x18001248d  call    WPP_SF_ls
0x180012492  jmp     loc_180012600
0x180012497  mov     rcx, cs:WPP_GLOBAL_Control
0x18001249e  lea     r14, aIpv6address; "Ipv6Address"
0x1800124a5  cmp     rcx, rdi
0x1800124a8  jz      short loc_1800124C3
0x1800124aa  test    [rcx+1Ch], ebx
0x1800124ad  jz      short loc_1800124C3
0x1800124af  mov     rcx, [rcx+10h]
0x1800124b3  mov     edx, 22h ; '"'
0x1800124b8  mov     r9, r14
0x1800124bb  mov     r8, rsi
0x1800124be  call    WPP_SF_s
0x1800124c3  mov     r8, cs:DhcpGlobalClientTableV6
0x1800124ca  lea     rax, aClientduid; "+ClientDUID"
0x1800124d1  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x1800124d8  mov     r9d, 8
0x1800124de  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800124e5  mov     dword ptr [rsp+98h+var_68], r15d
0x1800124ea  mov     r8, [r8+10h]
0x1800124ee  mov     dword ptr [rsp+98h+var_70], 0Dh
0x1800124f6  mov     [rsp+98h+var_78], rax
0x1800124fb  call    cs:__imp_JetCreateIndex
0x180012502  nop     dword ptr [rax+rax+00h]
0x180012507  mov     ecx, eax
0x180012509  mov     rdx, r13
0x18001250c  call    DhcpMapJetError
0x180012511  mov     ebp, eax
0x180012513  test    eax, eax
0x180012515  jz      short loc_180012546
0x180012517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001251e  cmp     rcx, rdi
0x180012521  jz      loc_180012600
0x180012527  test    [rcx+1Ch], ebx
0x18001252a  jz      loc_180012600
0x180012530  lea     r9, aClientduid_2; "ClientDUID"
0x180012537  mov     edx, 23h ; '#'
0x18001253c  mov     [rsp+98h+var_78], r9
0x180012541  jmp     loc_180012483
0x180012546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001254d  cmp     rcx, rdi
0x180012550  jz      short loc_18001256F
0x180012552  test    [rcx+1Ch], ebx
0x180012555  jz      short loc_18001256F
0x180012557  mov     rcx, [rcx+10h]
0x18001255b  lea     r9, aClientduid_2; "ClientDUID"
0x180012562  mov     edx, 24h ; '$'
0x180012567  mov     r8, rsi
0x18001256a  call    WPP_SF_s
0x18001256f  mov     r8, cs:DhcpGlobalClientTableV6
0x180012576  lea     rax, aState_0; "+State"
0x18001257d  mov     rdx, cs:DhcpGlobalClientTableV6Handle
0x180012584  xor     r9d, r9d
0x180012587  mov     rcx, cs:DhcpGlobalJetServerSession
0x18001258e  mov     dword ptr [rsp+98h+var_68], r15d
0x180012593  mov     r8, [r8+60h]
0x180012597  mov     dword ptr [rsp+98h+var_70], 8
0x18001259f  mov     [rsp+98h+var_78], rax
0x1800125a4  call    cs:__imp_JetCreateIndex
0x1800125ab  nop     dword ptr [rax+rax+00h]
0x1800125b0  mov     ecx, eax
0x1800125b2  mov     rdx, r13
0x1800125b5  call    DhcpMapJetError
0x1800125ba  mov     ebp, eax
0x1800125bc  test    eax, eax
0x1800125be  jz      short loc_1800125DB
0x1800125c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125c7  cmp     rcx, rdi
0x1800125ca  jz      short loc_180012600
0x1800125cc  test    [rcx+1Ch], ebx
0x1800125cf  jz      short loc_180012600
0x1800125d1  mov     edx, 25h ; '%'
0x1800125d6  jmp     loc_18001247E
0x1800125db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125e2  cmp     rcx, rdi
0x1800125e5  jz      short loc_180012600
0x1800125e7  test    [rcx+1Ch], ebx
0x1800125ea  jz      short loc_180012600
0x1800125ec  mov     rcx, [rcx+10h]
0x1800125f0  mov     edx, 26h ; '&'
0x1800125f5  mov     r9, r14
0x1800125f8  mov     r8, rsi
0x1800125fb  call    WPP_SF_s
0x180012600  mov     eax, ebp
0x180012602  mov     rcx, [rsp+98h+var_38]
0x180012607  xor     rcx, rsp; StackCookie
0x18001260a  call    __security_check_cookie
0x18001260f  lea     r11, [rsp+98h+var_28]
0x180012614  mov     rbx, [r11+30h]
0x180012618  mov     rbp, [r11+38h]
0x18001261c  mov     rsi, [r11+40h]
0x180012620  mov     rsp, r11
0x180012623  pop     r15
0x180012625  pop     r14
0x180012627  pop     r13
0x180012629  pop     r12
0x18001262b  pop     rdi
0x18001262c  retn
```
