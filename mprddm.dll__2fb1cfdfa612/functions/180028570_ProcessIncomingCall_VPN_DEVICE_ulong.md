# ProcessIncomingCall(_VPN_DEVICE *,ulong)

- ea: `0x180028570`
- end: `0x180028901`
- name: `?ProcessIncomingCall@@YAXPEAU_VPN_DEVICE@@K@Z`
- size: `913`
- prototype: `void __fastcall(struct _VPN_DEVICE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027da0`

## callees

- `0x180007b7c`
- `0x180026bf0`
- `0x180028570`
- `0x180071cec`
- `0x180085e4c`
- `0x18008625c`
- `0x1800864d8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!strstr` at `0x18002881a`
- `msvcrt!strstr` at `0x180028891`
- `msvcrt!strstr` at `0x18002881a`
- `msvcrt!strstr` at `0x180028891`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002884d`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800288c4`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002884d`
- `ntdll!RtlIpv6StringToAddressA` at `0x1800288c4`
- `WS2_32!__imp_inet_addr` at `0x180028830`
- `WS2_32!__imp_inet_addr` at `0x1800288a7`
- `WS2_32!__imp_inet_addr` at `0x180028830`
- `WS2_32!__imp_inet_addr` at `0x1800288a7`

## string_xrefs

- `0x180028610`: `IncomingCall for deviceId(%d)`
- `0x18002869a`: `Incoming call failed as server is offline`

## pseudocode

```c
void __fastcall ProcessIncomingCall(struct _VPN_DEVICE *a1, unsigned int a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rdx
  __int64 v11; // r8
  const CHAR *v12; // rbx
  unsigned int v13; // ecx
  const CHAR *v14; // rbx
  unsigned int v15; // ecx
  struct in6_addr Addr; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  PCSTR Terminator; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[24]; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+A8h] [rbp-58h]
  _DWORD v26[27]; // [rsp+B0h] [rbp-50h] BYREF
  char v27; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v28; // [rsp+124h] [rbp+24h]
  char v29; // [rsp+130h] [rbp+30h]
  unsigned int v30; // [rsp+138h] [rbp+38h]
  int v31; // [rsp+1D0h] [rbp+D0h]
  unsigned int v32; // [rsp+1D4h] [rbp+D4h]
  int v33; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v34[2044]; // [rsp+4B4h] [rbp+3B4h] BYREF

  v18 = 0;
  memset_0(v26, 0, 0x400u);
  Terminator = 0;
  v33 = 0;
  v17 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  Addr = 0;
  memset_0(v34, 0, sizeof(v34));
  v4 = -1;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v5 = *((unsigned int *)a1 + 4);
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IncomingCall for deviceId(%d)", v5);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&v34[2 * v7 - 4] );
      v25 = (unsigned int)(2 * v7 + 2);
      v24 = (const wchar_t *)&v33;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v6,
        2u,
        &v23);
    }
  }
  if ( (unsigned int)((__int64 (*)(void))qword_1800C86B0)() == 1 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
    {
LABEL_10:
      RasLineDrop(a2, v8, v9, 0, &v18);
      RasLineCloseCall(a2);
      return;
    }
    v25 = 84;
    v24 = L"Incoming call failed as server is offline";
    v10 = RasDdmTraceError;
LABEL_9:
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)v10,
      v9,
      2u,
      &v23);
    goto LABEL_10;
  }
  if ( !*((_DWORD *)a1 + 1) && !*((_DWORD *)a1 + 2) )
  {
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_10;
    v11 = *((unsigned int *)a1 + 4);
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"Ras or Routing is not enabled for deviceId(%d)", v11);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_10;
    do
      ++v4;
    while ( *(_WORD *)&v34[2 * v4 - 4] );
    v25 = (unsigned int)(2 * v4 + 2);
    v24 = (const wchar_t *)&v33;
LABEL_17:
    v10 = RasDdmTraceInfo;
    goto LABEL_9;
  }
  v26[0] = 1024;
  if ( (unsigned int)RasLineGetCallInfo(a2, v26) )
    goto LABEL_10;
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)a1 + 76) > *((_DWORD *)a1 + 75) )
  {
    _InterlockedAdd((volatile signed __int32 *)a1 + 76, 0xFFFFFFFF);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_10;
    v25 = 54;
    v24 = L"Unable to find free ports.";
    goto LABEL_17;
  }
  LODWORD(v20) = *((_DWORD *)a1 + 77);
  DWORD1(v20) = v31;
  *((_QWORD *)&v20 + 1) = (char *)v26 + v32;
  if ( (v29 & 8) != 0 )
  {
    v12 = (char *)v26 + v30;
    if ( strstr(v12, ":") )
    {
      *(_DWORD *)Addr.u.Byte = 2;
      RtlIpv6StringToAddressA(v12, &Terminator, (struct in6_addr *)&Addr.u.Word[2]);
      v13 = *(_DWORD *)&Addr.u.Word[2];
    }
    else
    {
      *(_DWORD *)Addr.u.Byte = 1;
      v13 = inet_addr(v12);
      *(_DWORD *)&Addr.u.Word[2] = v13;
    }
    *(_QWORD *)&v21 = __PAIR64__(v13, *(unsigned int *)Addr.u.Byte);
    *(_DWORD *)v22 = v17;
    *((_QWORD *)&v21 + 1) = *(_QWORD *)&Addr.u.Word[4];
  }
  if ( (v27 & 8) != 0 )
  {
    v14 = (char *)v26 + v28;
    if ( strstr(v14, ":") )
    {
      *(_DWORD *)Addr.u.Byte = 2;
      RtlIpv6StringToAddressA(v14, &Terminator, (struct in6_addr *)&Addr.u.Word[2]);
      v15 = *(_DWORD *)&Addr.u.Word[2];
    }
    else
    {
      *(_DWORD *)Addr.u.Byte = 1;
      v15 = inet_addr(v14);
      *(_DWORD *)&Addr.u.Word[2] = v15;
    }
    *(_DWORD *)&v22[4] = *(_DWORD *)Addr.u.Byte;
    *(_DWORD *)&v22[20] = v17;
    *(_DWORD *)&v22[8] = v15;
    *(_QWORD *)&v22[12] = *(_QWORD *)&Addr.u.Word[4];
  }
  DdmNotifyCaller(0, a2, 2, &v20);
}

```

## disassembly

```asm
0x180028570  mov     [rsp-8+arg_10], rbx
0x180028575  push    rbp
0x180028576  push    rsi
0x180028577  push    rdi
0x180028578  push    r14
0x18002857a  push    r15
0x18002857c  lea     rbp, [rsp-0BC0h]
0x180028584  sub     rsp, 0CC0h
0x18002858b  mov     rax, cs:__security_cookie
0x180028592  xor     rax, rsp
0x180028595  mov     [rbp+0BE0h+var_30], rax
0x18002859c  mov     esi, edx
0x18002859e  mov     rbx, rcx
0x1800285a1  xor     r14d, r14d
0x1800285a4  lea     rcx, [rbp+0BE0h+var_C30]; void *
0x1800285a8  xor     edx, edx; Val
0x1800285aa  mov     [rsp+0CE0h+var_C98], r14d
0x1800285af  mov     r8d, 400h; Size
0x1800285b5  call    memset_0
0x1800285ba  xorps   xmm0, xmm0
0x1800285bd  mov     [rsp+0CE0h+Terminator], r14
0x1800285c2  xor     eax, eax
0x1800285c4  mov     [rbp+0BE0h+var_830], r14d
0x1800285cb  xor     edx, edx; Val
0x1800285cd  mov     [rbp+0BE0h+var_C58], rax
0x1800285d1  mov     r8d, 7FCh; Size
0x1800285d7  mov     [rsp+0CE0h+var_CA0], eax
0x1800285db  lea     rcx, [rbp+0BE0h+var_82C]; void *
0x1800285e2  movups  [rsp+0CE0h+var_C88], xmm0
0x1800285e7  movups  [rsp+0CE0h+var_C78], xmm0
0x1800285ec  movups  [rsp+0CE0h+var_C68], xmm0
0x1800285f1  movups  xmmword ptr [rsp+0CE0h+Addr.u], xmm0
0x1800285f6  call    memset_0
0x1800285fb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800285ff  lea     r15d, [r14+2]
0x180028603  test    cs:byte_1800C8404, 10h
0x18002860a  jz      short loc_180028680
0x18002860c  mov     r8d, [rbx+10h]
0x180028610  lea     rdx, aIncomingcallFo; "IncomingCall for deviceId(%d)"
0x180028617  lea     rcx, [rbp+0BE0h+var_830]
0x18002861e  mov     word ptr [rbp+0BE0h+var_830], r14w
0x180028626  call    FormatRRASErrorString
0x18002862b  test    cs:byte_1800C8404, 10h
0x180028632  jz      short loc_180028680
0x180028634  lea     rcx, [rbp+0BE0h+var_830]
0x18002863b  mov     rax, rdi
0x18002863e  inc     rax
0x180028641  cmp     [rcx+rax*2], r14w
0x180028646  jnz     short loc_18002863E
0x180028648  lea     eax, ds:2[rax*2]
0x18002864f  mov     dword ptr [rbp+0BE0h+var_C38+4], r14d
0x180028653  lea     rcx, [rbp+0BE0h+var_830]
0x18002865a  mov     dword ptr [rbp+0BE0h+var_C38], eax
0x18002865d  lea     rax, [rbp+0BE0h+var_C50]
0x180028661  mov     [rbp+0BE0h+var_C40], rcx
0x180028665  mov     r9d, r15d
0x180028668  mov     [rsp+0CE0h+var_CC0], rax
0x18002866d  lea     rdx, RasDdmTraceInfo
0x180028674  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002867b  call    McGenEventWrite_EventWriteTransfer
0x180028680  mov     rax, cs:qword_1800C86B0
0x180028687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868c  cmp     eax, 1
0x18002868f  jnz     short loc_18002870D
0x180028691  test    cs:byte_1800C8404, 8
0x180028698  jz      short loc_1800286CC
0x18002869a  lea     rax, aIncomingCallFa; "Incoming call failed as server is offli"...
0x1800286a1  mov     [rbp+0BE0h+var_C38], 54h ; 'T'
0x1800286a9  mov     [rbp+0BE0h+var_C40], rax
0x1800286ad  lea     rdx, RasDdmTraceError
0x1800286b4  lea     rax, [rbp+0BE0h+var_C50]
0x1800286b8  mov     r9d, r15d
0x1800286bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800286c2  mov     [rsp+0CE0h+var_CC0], rax
0x1800286c7  call    McGenEventWrite_EventWriteTransfer
0x1800286cc  lea     rax, [rsp+0CE0h+var_C98]
0x1800286d1  xor     r9d, r9d
0x1800286d4  mov     ecx, esi
0x1800286d6  mov     [rsp+0CE0h+var_CC0], rax
0x1800286db  call    RasLineDrop
0x1800286e0  mov     ecx, esi
0x1800286e2  call    RasLineCloseCall
0x1800286e7  mov     rcx, [rbp+0BE0h+var_30]
0x1800286ee  xor     rcx, rsp; StackCookie
0x1800286f1  call    __security_check_cookie
0x1800286f6  mov     rbx, [rsp+0CE0h+arg_10]
0x1800286fe  add     rsp, 0CC0h
0x180028705  pop     r15
0x180028707  pop     r14
0x180028709  pop     rdi
0x18002870a  pop     rsi
0x18002870b  pop     rbp
0x18002870c  retn
0x18002870d  cmp     [rbx+4], r14d
0x180028711  jnz     short loc_180028780
0x180028713  cmp     [rbx+8], r14d
0x180028717  jnz     short loc_180028780
0x180028719  test    cs:byte_1800C8404, 10h
0x180028720  jz      short loc_1800286CC
0x180028722  mov     r8d, [rbx+10h]
0x180028726  lea     rdx, aRasOrRoutingIs; "Ras or Routing is not enabled for devic"...
0x18002872d  lea     rcx, [rbp+0BE0h+var_830]
0x180028734  mov     word ptr [rbp+0BE0h+var_830], r14w
0x18002873c  call    FormatRRASErrorString
0x180028741  test    cs:byte_1800C8404, 10h
0x180028748  jz      short loc_1800286CC
0x18002874a  lea     rax, [rbp+0BE0h+var_830]
0x180028751  inc     rdi
0x180028754  cmp     [rax+rdi*2], r14w
0x180028759  jnz     short loc_180028751
0x18002875b  lea     eax, ds:2[rdi*2]
0x180028762  mov     dword ptr [rbp+0BE0h+var_C38+4], r14d
0x180028766  lea     rcx, [rbp+0BE0h+var_830]
0x18002876d  mov     dword ptr [rbp+0BE0h+var_C38], eax
0x180028770  mov     [rbp+0BE0h+var_C40], rcx
0x180028774  lea     rdx, RasDdmTraceInfo
0x18002877b  jmp     loc_1800286B4
0x180028780  lea     rdx, [rbp+0BE0h+var_C30]
0x180028784  mov     [rbp+0BE0h+var_C30], 400h
0x18002878b  mov     ecx, esi
0x18002878d  call    RasLineGetCallInfo
0x180028792  test    eax, eax
0x180028794  jnz     loc_1800286CC
0x18002879a  mov     eax, 1
0x18002879f  lock xadd [rbx+130h], eax
0x1800287a7  inc     eax
0x1800287a9  cmp     eax, [rbx+12Ch]
0x1800287af  jbe     short loc_1800287DA
0x1800287b1  lock add [rbx+130h], edi
0x1800287b8  test    cs:byte_1800C8404, 10h
0x1800287bf  jz      loc_1800286CC
0x1800287c5  lea     rax, aUnableToFindFr; "Unable to find free ports."
0x1800287cc  mov     [rbp+0BE0h+var_C38], 36h ; '6'
0x1800287d4  mov     [rbp+0BE0h+var_C40], rax
0x1800287d8  jmp     short loc_180028774
0x1800287da  mov     eax, [rbx+134h]
0x1800287e0  lea     rcx, [rbp+0BE0h+var_C30]
0x1800287e4  mov     dword ptr [rsp+0CE0h+var_C88], eax
0x1800287e8  mov     eax, [rbp+0BE0h+var_B10]
0x1800287ee  mov     dword ptr [rsp+0CE0h+var_C88+4], eax
0x1800287f2  mov     eax, [rbp+0BE0h+var_B0C]
0x1800287f8  add     rcx, rax
0x1800287fb  test    [rbp+0BE0h+var_BB0], 8
0x1800287ff  mov     qword ptr [rsp+0CE0h+var_C88+8], rcx
0x180028804  jz      short loc_180028877
0x180028806  mov     eax, [rbp+0BE0h+var_BA8]
0x180028809  lea     rbx, [rbp+0BE0h+var_C30]
0x18002880d  add     rbx, rax
0x180028810  lea     rdx, asc_18009DA50; ":"
0x180028817  mov     rcx, rbx; Str
0x18002881a  call    cs:__imp_strstr
0x180028820  mov     rcx, rbx; S
0x180028823  test    rax, rax
0x180028826  jnz     short loc_18002883E
0x180028828  mov     dword ptr [rsp+0CE0h+Addr.u], 1
0x180028830  call    cs:__imp_inet_addr
0x180028836  mov     ecx, eax
0x180028838  mov     dword ptr [rsp+0CE0h+Addr.u+4], eax
0x18002883c  jmp     short loc_180028857
0x18002883e  lea     r8, [rsp+0CE0h+Addr.u+4]; Addr
0x180028843  mov     dword ptr [rsp+0CE0h+Addr.u], r15d
0x180028848  lea     rdx, [rsp+0CE0h+Terminator]; Terminator
0x18002884d  call    cs:__imp_RtlIpv6StringToAddressA
0x180028853  mov     ecx, dword ptr [rsp+0CE0h+Addr.u+4]
0x180028857  mov     eax, dword ptr [rsp+0CE0h+Addr.u]
0x18002885b  movsd   xmm0, qword ptr [rsp+0CE0h+Addr.u+8]
0x180028861  mov     dword ptr [rsp+0CE0h+var_C78], eax
0x180028865  mov     eax, [rsp+0CE0h+var_CA0]
0x180028869  mov     dword ptr [rsp+0CE0h+var_C68], eax
0x18002886d  mov     dword ptr [rsp+0CE0h+var_C78+4], ecx
0x180028871  movsd   qword ptr [rsp+0CE0h+var_C78+8], xmm0
0x180028877  test    [rbp+0BE0h+var_BC4], 8
0x18002887b  jz      short loc_1800288EB
0x18002887d  mov     eax, [rbp+0BE0h+var_BBC]
0x180028880  lea     rbx, [rbp+0BE0h+var_C30]
0x180028884  add     rbx, rax
0x180028887  lea     rdx, asc_18009DA50; ":"
0x18002888e  mov     rcx, rbx; Str
0x180028891  call    cs:__imp_strstr
0x180028897  mov     rcx, rbx; S
0x18002889a  test    rax, rax
0x18002889d  jnz     short loc_1800288B5
0x18002889f  mov     dword ptr [rsp+0CE0h+Addr.u], 1
0x1800288a7  call    cs:__imp_inet_addr
0x1800288ad  mov     ecx, eax
0x1800288af  mov     dword ptr [rsp+0CE0h+Addr.u+4], eax
0x1800288b3  jmp     short loc_1800288CE
0x1800288b5  lea     r8, [rsp+0CE0h+Addr.u+4]; Addr
0x1800288ba  mov     dword ptr [rsp+0CE0h+Addr.u], r15d
0x1800288bf  lea     rdx, [rsp+0CE0h+Terminator]; Terminator
0x1800288c4  call    cs:__imp_RtlIpv6StringToAddressA
0x1800288ca  mov     ecx, dword ptr [rsp+0CE0h+Addr.u+4]
0x1800288ce  mov     eax, dword ptr [rsp+0CE0h+Addr.u]
0x1800288d2  movsd   xmm0, qword ptr [rsp+0CE0h+Addr.u+8]
0x1800288d8  mov     dword ptr [rsp+0CE0h+var_C68+4], eax
0x1800288dc  mov     eax, [rsp+0CE0h+var_CA0]
0x1800288e0  mov     dword ptr [rbp+0BE0h+var_C58+4], eax
0x1800288e3  mov     dword ptr [rbp+0BE0h+var_C68+8], ecx
0x1800288e6  movsd   qword ptr [rbp+0BE0h+var_C68+0Ch], xmm0
0x1800288eb  lea     r9, [rsp+0CE0h+var_C88]
0x1800288f0  mov     r8d, r15d
0x1800288f3  mov     edx, esi
0x1800288f5  xor     ecx, ecx
0x1800288f7  call    ?DdmNotifyCaller@@YAXPEAXKW4_DDM_DRIVER_NOTIFICATION_MSG_ID@@0@Z; DdmNotifyCaller(void *,ulong,_DDM_DRIVER_NOTIFICATION_MSG_ID,void *)
0x1800288fc  jmp     loc_1800286E7
```
