# DnssrvComplexOperationEx

- ea: `0x180029220`
- end: `0x1800295b7`
- name: `DnssrvComplexOperationEx`
- size: `919`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, int, __int64, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180027fd0`

## callees

- `0x1800237ac`
- `0x18002825c`
- `0x180029220`
- `0x180029a88`
- `0x180029c90`
- `0x180029cf4`
- `0x180029ea8`
- `0x18002a364`
- `0x18002a3e0`
- `0x18002a724`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002940c`
- `RPCRT4!NdrClientCall3` at `0x18002940c`

## pseudocode

```c
__int64 __fastcall DnssrvComplexOperationEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int *a9,
        _QWORD *a10)
{
  _QWORD *v10; // rcx
  _QWORD *v11; // r12
  int *v12; // r13
  RPC_BINDING_HANDLE v13; // rax
  int v14; // ebx
  int v15; // esi
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edx
  RPC_BINDING_HANDLE RPCBindingHandle; // rcx
  int v20; // r8d
  int v21; // r9d
  unsigned int Pointer; // eax
  __int64 v23; // r8
  unsigned int v24; // ebx
  _QWORD *v25; // rcx
  int v26; // edx
  int v28; // [rsp+20h] [rbp-78h]
  int v29; // [rsp+B0h] [rbp+18h]
  RPC_BINDING_HANDLE v30; // [rsp+B8h] [rbp+20h]

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DSssd(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)&WPP_GLOBAL_Control, a3, a4);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 4) == 0 || *((_BYTE *)v10 + 25) < 4u )
  {
LABEL_9:
    v11 = a10;
    v12 = a9;
  }
  else
  {
    v11 = a10;
    v12 = a9;
    v28 = (int)a10;
    WPP_SF_qqdq(v10[2], &WPP_GLOBAL_Control, a3, a9);
  }
  if ( !a6 || !v11 || !v12 )
    return 87;
  v13 = 0;
  v14 = 0;
  v29 = 0;
  v15 = 0;
  *v11 = 0;
  while ( 1 )
  {
    if ( v15 == 1 )
    {
      v14 |= 1u;
      v29 = v14;
    }
    Dnssrv_FreeRPCBindingHandle(v13);
    RPCBindingHandle = Dnssrv_CreateRPCBindingHandle(v17, v16, v14);
    v30 = RPCBindingHandle;
    if ( v15 )
    {
      v28 = 0;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, RPCBindingHandle).Pointer;
      v24 = Pointer;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v26 = 36;
        goto LABEL_26;
      }
    }
    else
    {
      Pointer = R_DnssrvComplexOperation2(
                  (_DWORD)RPCBindingHandle,
                  v18,
                  v20,
                  v21,
                  v28,
                  a6,
                  a7,
                  a8,
                  (__int64)v12,
                  (__int64)v11);
      v24 = Pointer;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v26 = 35;
LABEL_26:
        WPP_SF_d(v25[2], v26, (unsigned int)&WPP_37d584b9184134be2c2c41d914906a97_Traceguids, Pointer);
        v25 = WPP_GLOBAL_Control;
      }
    }
    if ( v24 == 1825 || v24 == 1722 || v24 == 1753 || !v15 && (!v24 || v24 - 1700 > 0x53) )
      v15 = 2;
    else
      ++v15;
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 && *((_BYTE *)v25 + 25) >= 4u )
    {
      v28 = *v12;
      WPP_SF_ddq(v25[2], &WPP_GLOBAL_Control, v23, v24);
    }
    v13 = v30;
    if ( v15 >= 2 )
      break;
    v14 = v29;
  }
  printExtendedRpcErrorInfo(v24);
  if ( !v24 )
    v24 = DnsRpc_ConvertToCurrent(v12, v11);
  Dnssrv_FreeRPCBindingHandle(v30);
  return v24;
}

```

## disassembly

```asm
0x180029220  mov     [rsp+arg_18], r9
0x180029225  mov     [rsp+arg_10], r8d
0x18002922a  push    rbx
0x18002922b  push    rsi
0x18002922c  push    rdi
0x18002922d  push    r12
0x18002922f  push    r13
0x180029231  sub     rsp, 70h
0x180029235  lea     rdx, WPP_GLOBAL_Control
0x18002923c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029243  cmp     rcx, rdx
0x180029246  jz      loc_1800292CC
0x18002924c  test    byte ptr [rcx+1Ch], 4
0x180029250  jz      short loc_180029287
0x180029252  cmp     byte ptr [rcx+19h], 4
0x180029256  jb      short loc_180029287
0x180029258  mov     eax, [rsp+98h+arg_30]
0x18002925f  mov     dword ptr [rsp+98h+var_60], eax
0x180029263  mov     rax, [rsp+98h+arg_28]
0x18002926b  mov     [rsp+98h+var_68], rax
0x180029270  mov     rcx, [rcx+10h]
0x180029274  call    WPP_SF_DSssd
0x180029279  mov     rcx, cs:WPP_GLOBAL_Control
0x180029280  lea     rdx, WPP_GLOBAL_Control
0x180029287  cmp     rcx, rdx
0x18002928a  jz      short loc_1800292CC
0x18002928c  test    byte ptr [rcx+1Ch], 4
0x180029290  jz      short loc_1800292CC
0x180029292  cmp     byte ptr [rcx+19h], 4
0x180029296  jb      short loc_1800292CC
0x180029298  mov     r12, [rsp+98h+arg_48]
0x1800292a0  mov     rax, [r12]
0x1800292a4  mov     [rsp+98h+var_68], rax
0x1800292a9  mov     r13, [rsp+98h+arg_40]
0x1800292b1  mov     eax, [r13+0]
0x1800292b5  mov     dword ptr [rsp+98h+var_70], eax
0x1800292b9  mov     [rsp+98h+var_78], r12
0x1800292be  mov     r9, r13
0x1800292c1  mov     rcx, [rcx+10h]
0x1800292c5  call    WPP_SF_qqdq
0x1800292ca  jmp     short loc_1800292DC
0x1800292cc  mov     r12, [rsp+98h+arg_48]
0x1800292d4  mov     r13, [rsp+98h+arg_40]
0x1800292dc  cmp     [rsp+98h+arg_28], 0
0x1800292e5  jz      loc_1800295A6
0x1800292eb  test    r12, r12
0x1800292ee  jz      loc_1800295A6
0x1800292f4  test    r13, r13
0x1800292f7  jz      loc_1800295A6
0x1800292fd  xor     eax, eax
0x1800292ff  xor     ebx, ebx
0x180029301  mov     [rsp+98h+arg_10], ebx
0x180029308  xor     esi, esi
0x18002930a  mov     [rsp+98h+var_38], esi
0x18002930e  mov     rdi, [rsp+98h+arg_38]
0x180029316  mov     [rsp+98h+arg_20], rdi
0x18002931e  mov     [r12], rax
0x180029322  jmp     short loc_18002932B
0x180029324  mov     ebx, [rsp+98h+arg_10]
0x18002932b  cmp     esi, 1
0x18002932e  jnz     short loc_180029339
0x180029330  or      ebx, esi
0x180029332  mov     [rsp+98h+arg_10], ebx
0x180029339  mov     rcx, rax
0x18002933c  call    Dnssrv_FreeRPCBindingHandle
0x180029341  mov     r8d, ebx
0x180029344  call    Dnssrv_CreateRPCBindingHandle
0x180029349  mov     rcx, rax
0x18002934c  mov     [rsp+98h+arg_18], rax
0x180029354  mov     eax, [rsp+98h+arg_30]
0x18002935b  test    esi, esi
0x18002935d  jnz     short loc_1800293BD
0x18002935f  mov     [rsp+98h+var_50], r12
0x180029364  mov     [rsp+98h+var_58], r13
0x180029369  mov     [rsp+98h+var_60], rdi
0x18002936e  mov     dword ptr [rsp+98h+var_68], eax
0x180029372  mov     rax, [rsp+98h+arg_28]
0x18002937a  mov     [rsp+98h+var_70], rax
0x18002937f  call    R_DnssrvComplexOperation2
0x180029384  mov     ebx, eax
0x180029386  mov     [rsp+98h+var_34], eax
0x18002938a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029391  lea     rdx, WPP_GLOBAL_Control
0x180029398  cmp     rcx, rdx
0x18002939b  jz      loc_180029466
0x1800293a1  test    byte ptr [rcx+1Ch], 4
0x1800293a5  jz      loc_180029466
0x1800293ab  cmp     byte ptr [rcx+19h], 4
0x1800293af  jb      loc_180029466
0x1800293b5  lea     edx, [rsi+23h]
0x1800293b8  jmp     loc_180029445
0x1800293bd  mov     [rsp+98h+arg_8], 0
0x1800293c9  mov     [rsp+98h+var_48], r12
0x1800293ce  mov     [rsp+98h+var_50], r13
0x1800293d3  mov     [rsp+98h+var_58], rdi
0x1800293d8  mov     dword ptr [rsp+98h+var_60], eax
0x1800293dc  mov     rax, [rsp+98h+arg_28]
0x1800293e4  mov     [rsp+98h+var_68], rax
0x1800293e9  mov     [rsp+98h+var_70], 0
0x1800293f2  mov     [rsp+98h+var_78], 0
0x1800293fb  mov     r9, rcx
0x1800293fe  xor     r8d, r8d; pReturnValue
0x180029401  lea     edx, [r8+2]; nProcNum
0x180029405  lea     rcx, pProxyInfo; pProxyInfo
0x18002940c  call    cs:__imp_NdrClientCall3
0x180029412  mov     rbx, rax
0x180029415  mov     [rsp+98h+arg_8], rax
0x18002941d  mov     [rsp+98h+var_34], eax
0x180029421  mov     rcx, cs:WPP_GLOBAL_Control
0x180029428  lea     rdx, WPP_GLOBAL_Control
0x18002942f  cmp     rcx, rdx
0x180029432  jz      short loc_180029466
0x180029434  test    byte ptr [rcx+1Ch], 4
0x180029438  jz      short loc_180029466
0x18002943a  cmp     byte ptr [rcx+19h], 4
0x18002943e  jb      short loc_180029466
0x180029440  mov     edx, 24h ; '$'
0x180029445  mov     r9d, eax
0x180029448  lea     r8, WPP_37d584b9184134be2c2c41d914906a97_Traceguids
0x18002944f  mov     rcx, [rcx+10h]
0x180029453  call    WPP_SF_d
0x180029458  lea     rdx, WPP_GLOBAL_Control
0x18002945f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029466  cmp     ebx, 721h
0x18002946c  jz      short loc_180029495
0x18002946e  cmp     ebx, 6BAh
0x180029474  jz      short loc_180029495
0x180029476  cmp     ebx, 6D9h
0x18002947c  jz      short loc_180029495
0x18002947e  test    esi, esi
0x180029480  jnz     short loc_180029491
0x180029482  test    ebx, ebx
0x180029484  jz      short loc_180029495
0x180029486  lea     eax, [rbx-6A4h]
0x18002948c  cmp     eax, 53h ; 'S'
0x18002948f  ja      short loc_180029495
0x180029491  inc     esi
0x180029493  jmp     short loc_18002949A
0x180029495  mov     esi, 2
0x18002949a  mov     [rsp+98h+var_38], esi
0x18002949e  cmp     rcx, rdx
0x1800294a1  jz      short loc_1800294CC
0x1800294a3  test    byte ptr [rcx+1Ch], 4
0x1800294a7  jz      short loc_1800294CC
0x1800294a9  cmp     byte ptr [rcx+19h], 4
0x1800294ad  jb      short loc_1800294CC
0x1800294af  mov     rax, [r12]
0x1800294b3  mov     [rsp+98h+var_70], rax
0x1800294b8  mov     eax, [r13+0]
0x1800294bc  mov     dword ptr [rsp+98h+var_78], eax
0x1800294c0  mov     r9d, ebx
0x1800294c3  mov     rcx, [rcx+10h]
0x1800294c7  call    WPP_SF_ddq
0x1800294cc  mov     rax, [rsp+98h+arg_18]
0x1800294d4  jmp     loc_180029574
0x1800294d9  mov     edi, eax
0x1800294db  mov     ebx, eax
0x1800294dd  mov     [rsp+98h+var_34], eax
0x1800294e1  lea     rax, WPP_GLOBAL_Control
0x1800294e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294ef  cmp     rcx, rax
0x1800294f2  jz      short loc_180029518
0x1800294f4  test    byte ptr [rcx+1Ch], 4
0x1800294f8  jz      short loc_180029518
0x1800294fa  cmp     byte ptr [rcx+19h], 4
0x1800294fe  jb      short loc_180029518
0x180029500  mov     edx, 26h ; '&'
0x180029505  mov     r9d, ebx
0x180029508  lea     r8, WPP_37d584b9184134be2c2c41d914906a97_Traceguids
0x18002950f  mov     rcx, [rcx+10h]
0x180029513  call    WPP_SF_d
0x180029518  cmp     edi, 721h
0x18002951e  jz      short loc_18002954B
0x180029520  cmp     edi, 6BAh
0x180029526  jz      short loc_18002954B
0x180029528  cmp     edi, 6D9h
0x18002952e  jz      short loc_18002954B
0x180029530  mov     esi, [rsp+98h+var_38]
0x180029534  test    esi, esi
0x180029536  jnz     short loc_180029547
0x180029538  test    edi, edi
0x18002953a  jz      short loc_18002954B
0x18002953c  lea     eax, [rdi-6A4h]
0x180029542  cmp     eax, 53h ; 'S'
0x180029545  ja      short loc_18002954B
0x180029547  inc     esi
0x180029549  jmp     short loc_180029550
0x18002954b  mov     esi, 2
0x180029550  mov     [rsp+98h+var_38], esi
0x180029554  mov     r12, [rsp+98h+arg_48]
0x18002955c  mov     r13, [rsp+98h+arg_40]
0x180029564  mov     rdi, [rsp+98h+arg_20]
0x18002956c  mov     rax, [rsp+98h+arg_18]
0x180029574  cmp     esi, 2
0x180029577  jl      loc_180029324
0x18002957d  mov     ecx, ebx
0x18002957f  call    printExtendedRpcErrorInfo
0x180029584  test    ebx, ebx
0x180029586  jnz     short loc_180029595
0x180029588  mov     rdx, r12
0x18002958b  mov     rcx, r13
0x18002958e  call    DnsRpc_ConvertToCurrent
0x180029593  mov     ebx, eax
0x180029595  mov     rcx, [rsp+98h+arg_18]
0x18002959d  call    Dnssrv_FreeRPCBindingHandle
0x1800295a2  mov     eax, ebx
0x1800295a4  jmp     short loc_1800295AB
0x1800295a6  mov     eax, 57h ; 'W'
0x1800295ab  add     rsp, 70h
0x1800295af  pop     r13
0x1800295b1  pop     r12
0x1800295b3  pop     rdi
0x1800295b4  pop     rsi
0x1800295b5  pop     rbx
0x1800295b6  retn
```
