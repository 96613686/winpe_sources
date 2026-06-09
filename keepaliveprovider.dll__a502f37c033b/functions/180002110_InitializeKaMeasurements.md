# InitializeKaMeasurements

- ea: `0x180002110`
- end: `0x180002482`
- name: `InitializeKaMeasurements`
- size: `882`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180001c7e`
- `0x180001e20`
- `0x180001ed8`
- `0x180002110`
- `0x1800032c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000232a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000232a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800023ba`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800023ba`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800021a7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800021a7`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180002318`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180002318`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002233`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002233`

## pseudocode

```c
__int64 __fastcall InitializeKaMeasurements(__int64 a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v10; // rax
  DWORD v11; // eax
  __int64 v12; // r8
  __int64 v13; // r8

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 45, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  memset_0((void *)(a1 + 24), 0, 0x70u);
  v3 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(a1 + 24), 0x70u);
  v5 = v3;
  if ( v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v4, v3);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v7 = 47;
LABEL_18:
        WPP_SF_D(v6[2], v7, v4, v5);
        v6 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    *(_DWORD *)(a1 + 68) = 1;
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 72) = EventW;
    if ( EventW )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v4, 0);
        v6 = WPP_GLOBAL_Control;
      }
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v4, LastError);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        {
          v7 = 49;
          goto LABEL_18;
        }
      }
    }
  }
  if ( v5 )
  {
    if ( v6 == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 2u )
    {
LABEL_46:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_D(v6[2], 38, v4, v5);
      return v5;
    }
    WPP_SF_D(v6[2], 34, v4, v5);
LABEL_45:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v10 = RegisterWaitForSingleObjectEx(*(_QWORD *)(a1 + 72), KapiReceiveKaUpdateRequestCompletion, a1, 0xFFFFFFFFLL, 16);
  *(_QWORD *)(a1 + 160) = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    v5 = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v12, v11);
    }
    CleanupRpcAsyncState(a1 + 24);
    goto LABEL_45;
  }
  *(_DWORD *)(a1 + 16) = 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
    3u,
    0,
    a1 + 24,
    *(_QWORD *)a1,
    *(_QWORD *)(a1 + 8),
    a1 + 136,
    a1 + 144,
    a1 + 152);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v13, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_10], rsi
0x180002115  mov     [rsp+arg_0], rcx
0x18000211a  push    rdi
0x18000211b  push    r14
0x18000211d  push    r15
0x18000211f  sub     rsp, 50h
0x180002123  mov     r14, rcx
0x180002126  lea     rsi, WPP_GLOBAL_Control
0x18000212d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002134  cmp     rcx, rsi
0x180002137  jz      short loc_180002161
0x180002139  test    byte ptr [rcx+1Ch], 1
0x18000213d  jz      short loc_180002161
0x18000213f  cmp     byte ptr [rcx+19h], 6
0x180002143  jb      short loc_180002161
0x180002145  mov     edx, 21h ; '!'
0x18000214a  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002151  mov     rcx, [rcx+10h]
0x180002155  call    WPP_SF_
0x18000215a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002161  lea     r15, [r14+18h]
0x180002165  mov     [rsp+68h+arg_8], r15
0x18000216a  cmp     rcx, rsi
0x18000216d  jz      short loc_180002190
0x18000216f  test    byte ptr [rcx+1Ch], 1
0x180002173  jz      short loc_180002190
0x180002175  cmp     byte ptr [rcx+19h], 6
0x180002179  jb      short loc_180002190
0x18000217b  mov     edx, 2Dh ; '-'
0x180002180  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002187  mov     rcx, [rcx+10h]
0x18000218b  call    WPP_SF_
0x180002190  mov     edi, 70h ; 'p'
0x180002195  mov     r8d, edi; Size
0x180002198  xor     edx, edx; Val
0x18000219a  mov     rcx, r15; void *
0x18000219d  call    memset_0
0x1800021a2  mov     edx, edi; Size
0x1800021a4  mov     rcx, r15; pAsync
0x1800021a7  call    cs:__imp_RpcAsyncInitializeHandle
0x1800021ad  mov     edi, eax
0x1800021af  test    eax, eax
0x1800021b1  jz      short loc_180002221
0x1800021b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021ba  cmp     rcx, rsi
0x1800021bd  jz      loc_1800022C7
0x1800021c3  test    byte ptr [rcx+1Ch], 1
0x1800021c7  jz      short loc_1800021E7
0x1800021c9  cmp     byte ptr [rcx+19h], 2
0x1800021cd  jb      short loc_1800021E7
0x1800021cf  mov     edx, 2Eh ; '.'
0x1800021d4  mov     r9d, eax
0x1800021d7  mov     rcx, [rcx+10h]
0x1800021db  call    WPP_SF_D
0x1800021e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021e7  cmp     rcx, rsi
0x1800021ea  jz      loc_1800022C7
0x1800021f0  test    byte ptr [rcx+1Ch], 1
0x1800021f4  jz      loc_1800022C7
0x1800021fa  cmp     byte ptr [rcx+19h], 6
0x1800021fe  jb      loc_1800022C7
0x180002204  mov     edx, 2Fh ; '/'
0x180002209  mov     r9d, edi
0x18000220c  mov     rcx, [rcx+10h]
0x180002210  call    WPP_SF_D
0x180002215  mov     rcx, cs:WPP_GLOBAL_Control
0x18000221c  jmp     loc_1800022C7
0x180002221  mov     dword ptr [r15+2Ch], 1
0x180002229  xor     r9d, r9d; lpName
0x18000222c  xor     r8d, r8d; bInitialState
0x18000222f  xor     edx, edx; bManualReset
0x180002231  xor     ecx, ecx; lpEventAttributes
0x180002233  call    cs:__imp_CreateEventW
0x180002239  mov     [r15+30h], rax
0x18000223d  test    rax, rax
0x180002240  jnz     short loc_180002295
0x180002242  call    cs:__imp_GetLastError
0x180002248  mov     edi, eax
0x18000224a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002251  cmp     rcx, rsi
0x180002254  jz      short loc_1800022C7
0x180002256  test    byte ptr [rcx+1Ch], 1
0x18000225a  jz      short loc_18000227A
0x18000225c  cmp     byte ptr [rcx+19h], 2
0x180002260  jb      short loc_18000227A
0x180002262  mov     edx, 30h ; '0'
0x180002267  mov     r9d, eax
0x18000226a  mov     rcx, [rcx+10h]
0x18000226e  call    WPP_SF_D
0x180002273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000227a  cmp     rcx, rsi
0x18000227d  jz      short loc_1800022C7
0x18000227f  test    byte ptr [rcx+1Ch], 1
0x180002283  jz      short loc_1800022C7
0x180002285  cmp     byte ptr [rcx+19h], 6
0x180002289  jb      short loc_1800022C7
0x18000228b  mov     edx, 31h ; '1'
0x180002290  jmp     loc_180002209
0x180002295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000229c  cmp     rcx, rsi
0x18000229f  jz      short loc_1800022C5
0x1800022a1  test    byte ptr [rcx+1Ch], 1
0x1800022a5  jz      short loc_1800022C5
0x1800022a7  cmp     byte ptr [rcx+19h], 6
0x1800022ab  jb      short loc_1800022C5
0x1800022ad  mov     edx, 32h ; '2'
0x1800022b2  xor     r9d, r9d
0x1800022b5  mov     rcx, [rcx+10h]
0x1800022b9  call    WPP_SF_D
0x1800022be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022c5  xor     edi, edi
0x1800022c7  test    edi, edi
0x1800022c9  jz      short loc_1800022FE
0x1800022cb  cmp     rcx, rsi
0x1800022ce  jz      loc_180002441
0x1800022d4  test    byte ptr [rcx+1Ch], 1
0x1800022d8  jz      loc_18000241F
0x1800022de  cmp     byte ptr [rcx+19h], 2
0x1800022e2  jb      loc_18000241F
0x1800022e8  mov     edx, 22h ; '"'
0x1800022ed  mov     r9d, edi
0x1800022f0  mov     rcx, [rcx+10h]
0x1800022f4  call    WPP_SF_D
0x1800022f9  jmp     loc_180002418
0x1800022fe  mov     dword ptr [rsp+68h+var_48], 10h
0x180002306  or      r9d, 0FFFFFFFFh
0x18000230a  mov     r8, r14
0x18000230d  lea     rdx, KapiReceiveKaUpdateRequestCompletion
0x180002314  mov     rcx, [r14+48h]
0x180002318  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000231e  mov     [r14+0A0h], rax
0x180002325  test    rax, rax
0x180002328  jnz     short loc_18000236C
0x18000232a  call    cs:__imp_GetLastError
0x180002330  mov     edi, eax
0x180002332  mov     rcx, cs:WPP_GLOBAL_Control
0x180002339  cmp     rcx, rsi
0x18000233c  jz      loc_180002410
0x180002342  test    byte ptr [rcx+1Ch], 1
0x180002346  jz      loc_180002410
0x18000234c  cmp     byte ptr [rcx+19h], 2
0x180002350  jb      loc_180002410
0x180002356  mov     edx, 23h ; '#'
0x18000235b  mov     r9d, eax
0x18000235e  mov     rcx, [rcx+10h]
0x180002362  call    WPP_SF_D
0x180002367  jmp     loc_180002410
0x18000236c  mov     dword ptr [r14+10h], 1
0x180002374  lea     rax, [r14+98h]
0x18000237b  lea     rcx, [r14+90h]
0x180002382  lea     rdx, [r14+88h]
0x180002389  mov     [rsp+68h+var_28], rax
0x18000238e  mov     [rsp+68h+var_30], rcx
0x180002393  mov     [rsp+68h+var_38], rdx
0x180002398  mov     rax, [r14+8]
0x18000239c  mov     [rsp+68h+var_40], rax
0x1800023a1  mov     rax, [r14]
0x1800023a4  mov     [rsp+68h+var_48], rax
0x1800023a9  mov     r9, r15
0x1800023ac  xor     r8d, r8d; pReturnValue
0x1800023af  lea     edx, [r8+3]; nProcNum
0x1800023b3  lea     rcx, pProxyInfo; pProxyInfo
0x1800023ba  call    cs:__imp_Ndr64AsyncClientCall
0x1800023c0  jmp     short loc_18000240C
0x1800023c2  mov     edi, eax
0x1800023c4  lea     rax, WPP_GLOBAL_Control
0x1800023cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023d2  cmp     rcx, rax
0x1800023d5  jz      short loc_1800023F4
0x1800023d7  test    byte ptr [rcx+1Ch], 1
0x1800023db  jz      short loc_1800023F4
0x1800023dd  cmp     byte ptr [rcx+19h], 2
0x1800023e1  jb      short loc_1800023F4
0x1800023e3  mov     edx, 24h ; '$'
0x1800023e8  mov     r9d, edi
0x1800023eb  mov     rcx, [rcx+10h]
0x1800023ef  call    WPP_SF_D
0x1800023f4  mov     rax, [rsp+68h+arg_0]
0x1800023f9  mov     dword ptr [rax+10h], 0
0x180002400  lea     rsi, WPP_GLOBAL_Control
0x180002407  mov     r15, [rsp+68h+arg_8]
0x18000240c  test    edi, edi
0x18000240e  jz      short loc_180002445
0x180002410  mov     rcx, r15
0x180002413  call    CleanupRpcAsyncState
0x180002418  mov     rcx, cs:WPP_GLOBAL_Control
0x18000241f  cmp     rcx, rsi
0x180002422  jz      short loc_180002441
0x180002424  test    byte ptr [rcx+1Ch], 1
0x180002428  jz      short loc_180002441
0x18000242a  cmp     byte ptr [rcx+19h], 6
0x18000242e  jb      short loc_180002441
0x180002430  mov     edx, 26h ; '&'
0x180002435  mov     r9d, edi
0x180002438  mov     rcx, [rcx+10h]
0x18000243c  call    WPP_SF_D
0x180002441  mov     eax, edi
0x180002443  jmp     short loc_180002470
0x180002445  mov     rcx, cs:WPP_GLOBAL_Control
0x18000244c  cmp     rcx, rsi
0x18000244f  jz      short loc_18000246E
0x180002451  test    byte ptr [rcx+1Ch], 1
0x180002455  jz      short loc_18000246E
0x180002457  cmp     byte ptr [rcx+19h], 6
0x18000245b  jb      short loc_18000246E
0x18000245d  mov     edx, 25h ; '%'
0x180002462  xor     r9d, r9d
0x180002465  mov     rcx, [rcx+10h]
0x180002469  call    WPP_SF_D
0x18000246e  xor     eax, eax
0x180002470  mov     rsi, [rsp+68h+arg_10]
0x180002478  add     rsp, 50h
0x18000247c  pop     r15
0x18000247e  pop     r14
0x180002480  pop     rdi
0x180002481  retn
0x1800035d6  push    rbp
0x1800035d8  sub     rsp, 50h
0x1800035dc  mov     rbp, rdx
0x1800035df  mov     rax, [rcx]
0x1800035e2  mov     eax, [rax]
0x1800035e4  add     rsp, 50h
0x1800035e8  pop     rbp
0x1800035e9  retn
```
