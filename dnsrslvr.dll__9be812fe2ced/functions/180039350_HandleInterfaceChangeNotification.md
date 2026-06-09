# HandleInterfaceChangeNotification

- ea: `0x180039350`
- end: `0x18003954d`
- name: `HandleInterfaceChangeNotification`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x18002dc6c`
- `0x18002def4`
- `0x1800303fc`
- `0x1800309e8`
- `0x180030ad4`
- `0x180030b84`
- `0x18003508c`
- `0x180039350`
- `0x18005c70c`
- `0x18007a83c`
- `0x180086700`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `DNSAPI!DnsApiOnNetworkChange` at `0x180039528`
- `DNSAPI!DnsApiOnNetworkChange` at `0x180039528`
- `DNSAPI!DnsUpdateMachinePresence` at `0x1800394c1`
- `DNSAPI!DnsUpdateMachinePresence` at `0x1800394c1`
- `DNSAPI!DelaySortDAServerlist` at `0x18003951d`
- `DNSAPI!DelaySortDAServerlist` at `0x18003951d`

## pseudocode

```c
__int64 __fastcall HandleInterfaceChangeNotification(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned int v4; // r14d
  int v5; // ebp
  int v6; // r12d
  int v7; // ebx
  const NET_LUID **v9; // rsi
  __int64 v10; // r15
  __int64 v11; // r8
  int v12; // ebx
  int v13; // ebx
  int v14; // eax
  int updated; // eax
  unsigned int v16; // eax
  __int64 result; // rax

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = a4;
  v9 = (const NET_LUID **)a2;
  v10 = a1;
  if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    WPP_SF_d(1055, 27, WPP_71228760225f354854029c0844ed0efa_Traceguids, a4);
  v11 = 1;
  if ( !v7 )
  {
    if ( a3 )
    {
      if ( *a3 )
        goto LABEL_37;
      a2 = 0;
      a1 = (unsigned int)(a3[5] - 16);
      if ( a3[5] == 16 )
      {
        a2 = 1;
      }
      else
      {
        a1 = (unsigned int)(a3[5] - 165);
        if ( a3[5] == 165 )
        {
          v4 = 1;
          goto LABEL_27;
        }
        if ( a3[5] == 168 )
        {
          LOBYTE(a2) = v10 != 0;
          updated = UpdateInterfacePresence(*v9, a2, 1);
          if ( SBYTE3(xmmword_1800AB5A0) < 0 )
            WPP_SF_Id(a1, 30, v11, (*v9)->Value, updated);
          v4 = 1;
          goto LABEL_27;
        }
        a1 = (unsigned int)(a3[5] - 188);
        if ( a3[5] != 188 )
        {
          if ( a3[5] != 192 )
            goto LABEL_37;
          v6 = 1;
          goto LABEL_33;
        }
      }
      if ( !(_DWORD)a2 )
      {
LABEL_33:
        if ( *v9 )
          UpdateNetworkProperties(v10 != 0, *v9);
        if ( v6 )
          NS_Process();
        goto LABEL_37;
      }
    }
    v5 = 1;
    goto LABEL_27;
  }
  v12 = v7 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
        goto LABEL_37;
    }
    else
    {
      LOBYTE(a2) = v10 != 0;
      DeleteInterfaceListEntry(*v9, a2, 1);
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_q(1055, 29, WPP_71228760225f354854029c0844ed0efa_Traceguids, (*v9)->Value);
    }
  }
  else
  {
    LOBYTE(a2) = v10 != 0;
    v14 = AddInterfaceListEntry(*v9, a2, 0);
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_Id(a1, 28, v11, (*v9)->Value, v14);
  }
LABEL_27:
  if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1055, 31, WPP_71228760225f354854029c0844ed0efa_Traceguids);
  v16 = DnsUpdateMachinePresence(a1, a2, v11);
  if ( v16 && SBYTE3(xmmword_1800AB5A0) < 0 )
    WPP_SF_d(1055, 32, WPP_71228760225f354854029c0844ed0efa_Traceguids, v16);
  SetEffectiveMachinePresence(v4);
  if ( v5 )
    goto LABEL_33;
LABEL_37:
  UpdateNetInfoReachableServers();
  DelaySortDAServerlist();
  result = DnsApiOnNetworkChange(1);
  if ( g_fVelocityZtdnsProbing )
    return AlertOrStartZtProbeThread(0);
  return result;
}

```

## disassembly

```asm
0x180039350  push    rbx
0x180039352  push    rbp
0x180039353  push    rsi
0x180039354  push    rdi
0x180039355  push    r12
0x180039357  push    r14
0x180039359  push    r15
0x18003935b  sub     rsp, 30h
0x18003935f  xor     r14d, r14d
0x180039362  xor     ebp, ebp
0x180039364  xor     r12d, r12d
0x180039367  mov     ebx, r9d
0x18003936a  mov     rdi, r8
0x18003936d  mov     rsi, rdx
0x180039370  mov     r15, rcx
0x180039373  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18003937a  jge     short loc_180039390
0x18003937c  lea     edx, [rbp+1Bh]
0x18003937f  mov     ecx, 41Fh
0x180039384  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x18003938b  call    WPP_SF_d
0x180039390  mov     r8d, 1
0x180039396  test    ebx, ebx
0x180039398  jz      loc_180039426
0x18003939e  sub     ebx, r8d
0x1800393a1  jz      short loc_1800393F2
0x1800393a3  sub     ebx, r8d
0x1800393a6  jz      short loc_1800393B6
0x1800393a8  cmp     ebx, r8d
0x1800393ab  jz      loc_1800394A2
0x1800393b1  jmp     loc_180039518
0x1800393b6  mov     rcx, [rsi]
0x1800393b9  test    r15, r15
0x1800393bc  setnz   dl
0x1800393bf  call    DeleteInterfaceListEntry
0x1800393c4  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x1800393cb  jge     loc_1800394A2
0x1800393d1  mov     r9, [rsi]
0x1800393d4  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x1800393db  mov     edx, 1Dh
0x1800393e0  mov     ecx, 41Fh
0x1800393e5  mov     r9, [r9]
0x1800393e8  call    WPP_SF_q
0x1800393ed  jmp     loc_1800394A2
0x1800393f2  mov     rcx, [rsi]
0x1800393f5  test    r15, r15
0x1800393f8  setnz   dl
0x1800393fb  xor     r8d, r8d
0x1800393fe  call    AddInterfaceListEntry
0x180039403  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18003940a  jge     loc_1800394A2
0x180039410  mov     r9, [rsi]
0x180039413  mov     edx, 1Ch
0x180039418  mov     [rsp+68h+var_48], eax
0x18003941c  mov     r9, [r9]
0x18003941f  call    WPP_SF_Id
0x180039424  jmp     short loc_1800394A2
0x180039426  test    rdi, rdi
0x180039429  jz      short loc_18003949F
0x18003942b  cmp     [rdi], ebp
0x18003942d  jnz     loc_180039518
0x180039433  mov     ecx, [rdi+14h]
0x180039436  xor     edx, edx
0x180039438  sub     ecx, 10h
0x18003943b  jz      short loc_180039498
0x18003943d  sub     ecx, 95h
0x180039443  jz      short loc_180039493
0x180039445  sub     ecx, 3
0x180039448  jz      short loc_180039460
0x18003944a  sub     ecx, 14h
0x18003944d  jz      short loc_18003949B
0x18003944f  cmp     ecx, 4
0x180039452  jnz     loc_180039518
0x180039458  mov     r12d, r8d
0x18003945b  jmp     loc_1800394F9
0x180039460  mov     rcx, [rsi]
0x180039463  test    r15, r15
0x180039466  setnz   dl
0x180039469  call    UpdateInterfacePresence
0x18003946e  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x180039475  jge     short loc_18003948B
0x180039477  mov     r9, [rsi]
0x18003947a  mov     edx, 1Eh
0x18003947f  mov     [rsp+68h+var_48], eax
0x180039483  mov     r9, [r9]
0x180039486  call    WPP_SF_Id
0x18003948b  mov     r14d, 1
0x180039491  jmp     short loc_1800394A2
0x180039493  mov     r14d, r8d
0x180039496  jmp     short loc_1800394A2
0x180039498  mov     edx, r8d
0x18003949b  test    edx, edx
0x18003949d  jz      short loc_1800394F9
0x18003949f  mov     ebp, r8d
0x1800394a2  cmp     byte ptr cs:xmmword_1800AB5A0+3, r12b
0x1800394a9  jge     short loc_1800394C1
0x1800394ab  mov     edx, 1Fh
0x1800394b0  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x1800394b7  mov     ecx, 41Fh
0x1800394bc  call    WPP_SF_
0x1800394c1  call    cs:__imp_DnsUpdateMachinePresence
0x1800394c7  test    eax, eax
0x1800394c9  jz      short loc_1800394ED
0x1800394cb  cmp     byte ptr cs:xmmword_1800AB5A0+3, r12b
0x1800394d2  jge     short loc_1800394ED
0x1800394d4  mov     edx, 20h ; ' '
0x1800394d9  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x1800394e0  mov     ecx, 41Fh
0x1800394e5  mov     r9d, eax
0x1800394e8  call    WPP_SF_d
0x1800394ed  mov     ecx, r14d
0x1800394f0  call    SetEffectiveMachinePresence
0x1800394f5  test    ebp, ebp
0x1800394f7  jz      short loc_180039518
0x1800394f9  mov     rdx, [rsi]
0x1800394fc  test    rdx, rdx
0x1800394ff  jz      short loc_18003950E
0x180039501  xor     ecx, ecx
0x180039503  test    r15, r15
0x180039506  setnz   cl
0x180039509  call    UpdateNetworkProperties
0x18003950e  test    r12d, r12d
0x180039511  jz      short loc_180039518
0x180039513  call    NS_Process
0x180039518  call    UpdateNetInfoReachableServers
0x18003951d  call    cs:__imp_DelaySortDAServerlist
0x180039523  mov     ecx, 1
0x180039528  call    cs:__imp_DnsApiOnNetworkChange
0x18003952e  cmp     cs:g_fVelocityZtdnsProbing, 0
0x180039535  jz      short loc_18003953E
0x180039537  xor     ecx, ecx
0x180039539  call    AlertOrStartZtProbeThread
0x18003953e  add     rsp, 30h
0x180039542  pop     r15
0x180039544  pop     r14
0x180039546  pop     r12
0x180039548  pop     rdi
0x180039549  pop     rsi
0x18003954a  pop     rbp
0x18003954b  pop     rbx
0x18003954c  retn
```
