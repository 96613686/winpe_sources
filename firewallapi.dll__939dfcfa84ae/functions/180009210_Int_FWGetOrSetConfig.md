# Int_FWGetOrSetConfig

- ea: `0x180009210`
- end: `0x180009773`
- name: `Int_FWGetOrSetConfig`
- size: `1379`
- prototype: ``
- caller_count: `14`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003424`
- `0x180006874`
- `0x180007070`
- `0x1800073f0`
- `0x1800076a0`
- `0x180007a00`
- `0x180007e30`
- `0x180008f80`
- `0x1800090d0`
- `0x18000af10`
- `0x18000bea0`
- `0x1800191e0`
- `0x18001a7a0`
- `0x180028eb0`

## callees

- `0x180005e0c`
- `0x180009210`
- `0x180009870`
- `0x180026c9c`
- `0x18003336c`
- `0x180054d58`
- `0x180054db8`
- `0x180055378`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005f9ce`
- `RPCRT4!RpcExceptionFilter` at `0x18005f9ce`
- `fwbase!FwHResultToWindowsError` at `0x180009666`
- `fwbase!FwHResultToWindowsError` at `0x1800096b3`
- `fwbase!FwHResultToWindowsError` at `0x180009666`
- `fwbase!FwHResultToWindowsError` at `0x1800096b3`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800096a5`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800096a5`
- `FWPolicyIOMgr!FwGetConfig` at `0x180009658`
- `FWPolicyIOMgr!FwGetConfig` at `0x180009658`

## pseudocode

```c
__int64 __fastcall Int_FWGetOrSetConfig(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int *a7)
{
  __int64 v10; // r8
  FwPolicy2 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  __int64 v15; // r11
  unsigned int v16; // eax
  unsigned int v17; // edi
  __int64 (__fastcall *v18)(int, int, int, int, __int64, int); // rax
  unsigned int v19; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  unsigned int Config; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax

  v10 = a1;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    v11 = WPP_GLOBAL_Control;
    v10 = a1;
  }
  v12 = 0;
  if ( a2 )
  {
    if ( a3 - 1 > 0x11 )
    {
      v17 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v21 = 279;
      goto LABEL_45;
    }
    if ( (a5 & 0xFFFFFFFE) != 0 )
    {
      v17 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v21 = 280;
      goto LABEL_45;
    }
    if ( !a7 )
    {
      v17 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v21 = 281;
      goto LABEL_45;
    }
    if ( !a6 && *a7 )
    {
      v17 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v21 = 282;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v11 + 2), v21, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 87);
      v11 = WPP_GLOBAL_Control;
LABEL_41:
      v12 = 0;
      goto LABEL_27;
    }
    v12 = a2;
    if ( *(_WORD *)(a2 + 2) >= 0x214u || (int)a3 < 18 )
    {
      v13 = *(unsigned int *)(a2 + 4);
      if ( (unsigned int)v13 > 1 )
      {
        if ( (_DWORD)v13 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v11, v13, v10);
        v24 = Int_FWOpenGPOPolicyStore(a2);
        v17 = v24;
        if ( v24 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_59;
          v22 = 288;
          v23 = v24;
          goto LABEL_57;
        }
        if ( !*(_QWORD *)(a2 + 56) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25, v27);
        if ( (a5 & 1) == 0 )
        {
          v28 = *(_QWORD *)(a2 + 56);
          if ( a1 )
          {
            Config = FwGetConfig(v28, a3, a4, a6, a7);
            v30 = FwHResultToWindowsError(Config);
            v17 = v30;
            if ( v30 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 290;
              v23 = v30;
              goto LABEL_57;
            }
          }
          else
          {
            v31 = FwSetConfig(v28, a3, a4, a6, *a7);
            v32 = FwHResultToWindowsError(v31);
            v17 = v32;
            if ( v32 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 291;
              v23 = v32;
              goto LABEL_57;
            }
          }
          v33 = Int_FWCloseGPOPolicyStore(a2, a1 == 0);
          v17 = v33;
          if ( !v33 )
            goto LABEL_58;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_59;
          v22 = 292;
          v23 = v33;
LABEL_57:
          WPP_SF_d(*((_QWORD *)v11 + 2), v22, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v23);
LABEL_58:
          v11 = WPP_GLOBAL_Control;
LABEL_59:
          v12 = a2;
          goto LABEL_27;
        }
        v17 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_59;
        v22 = 289;
LABEL_56:
        v23 = v17;
        goto LABEL_57;
      }
      v14 = *(_QWORD *)(a2 + 32);
      if ( v14 )
      {
        v15 = *(_QWORD *)(a2 + 40);
        if ( v15 )
        {
          if ( (_DWORD)v10 )
          {
            v16 = Int_FWCallRpcGetConfig(a2, a3, a4, a5, a6, (__int64)a7);
            v17 = v16;
            if ( v16 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 285, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v16);
                v11 = WPP_GLOBAL_Control;
              }
              v12 = a2;
              goto LABEL_27;
            }
          }
          else
          {
            v18 = RPC_FWSetConfig;
            if ( (_DWORD)v13 )
              v18 = RRPC_FWSetConfig;
            v19 = v18(v14, v15, a3, a4, a6, *a7);
            v17 = v19;
            if ( v19 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v19);
                v11 = WPP_GLOBAL_Control;
              }
              v12 = a2;
              goto LABEL_27;
            }
          }
          v11 = WPP_GLOBAL_Control;
          v12 = a2;
          goto LABEL_27;
        }
      }
      v17 = 87;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v22 = 284;
        goto LABEL_56;
      }
    }
    else
    {
      v17 = 50;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v22 = 283;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v17 = 87;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v21 = 278;
      goto LABEL_45;
    }
  }
LABEL_27:
  if ( v17 && v12 && *(_DWORD *)(v12 + 4) == 2 && *(_DWORD *)(v12 + 24) != 1 )
  {
    Int_FWCleanupGPOPolicyStore(v12);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v11 + 2), 293, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  return v17;
}

```

## disassembly

```asm
0x180009210  mov     [rsp+arg_18], r9d
0x180009215  mov     [rsp+arg_0], ecx
0x180009219  push    rbx
0x18000921a  push    rsi
0x18000921b  push    rdi
0x18000921c  push    r12
0x18000921e  push    r13
0x180009220  push    r14
0x180009222  push    r15
0x180009224  sub     rsp, 50h
0x180009228  mov     edi, r9d
0x18000922b  mov     r13d, r8d
0x18000922e  mov     rbx, rdx
0x180009231  mov     r8d, ecx
0x180009234  lea     r12, WPP_GLOBAL_Control
0x18000923b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009242  cmp     rcx, r12
0x180009245  jz      short loc_180009251
0x180009247  test    byte ptr [rcx+1Ch], 8
0x18000924b  jnz     loc_1800094D5
0x180009251  xor     eax, eax
0x180009253  mov     [rsp+88h+arg_8], rax
0x18000925b  test    rbx, rbx
0x18000925e  jz      loc_1800094FE
0x180009264  lea     eax, [r13-1]
0x180009268  cmp     eax, 11h
0x18000926b  ja      loc_1800094BA
0x180009271  mov     r15d, [rsp+88h+arg_20]
0x180009279  test    r15d, 0FFFFFFFEh
0x180009280  jnz     loc_18000953E
0x180009286  mov     rsi, [rsp+88h+arg_30]
0x18000928e  test    rsi, rsi
0x180009291  jz      loc_180009559
0x180009297  mov     r14, [rsp+88h+arg_28]
0x18000929f  test    r14, r14
0x1800092a2  jz      loc_180009475
0x1800092a8  mov     rax, rbx
0x1800092ab  mov     [rsp+88h+arg_8], rbx
0x1800092b3  mov     [rsp+88h+arg_38], rbx
0x1800092bb  mov     edx, 214h
0x1800092c0  cmp     [rbx+2], dx
0x1800092c4  jb      loc_180009578
0x1800092ca  mov     edx, [rbx+4]
0x1800092cd  cmp     edx, 1
0x1800092d0  ja      loc_1800095D2
0x1800092d6  mov     r10, [rbx+20h]
0x1800092da  test    r10, r10
0x1800092dd  jz      loc_180009728
0x1800092e3  mov     r11, [rbx+28h]
0x1800092e7  test    r11, r11
0x1800092ea  jz      loc_180009728
0x1800092f0  test    r8d, r8d
0x1800092f3  jz      short loc_18000935E
0x1800092f5  mov     [rsp+88h+var_60], rsi
0x1800092fa  mov     [rsp+88h+var_68], r14
0x1800092ff  mov     r9d, r15d
0x180009302  mov     r8d, edi
0x180009305  mov     edx, r13d
0x180009308  mov     rcx, rbx
0x18000930b  call    Int_FWCallRpcGetConfig
0x180009310  mov     edi, eax
0x180009312  mov     [rsp+88h+var_48], eax
0x180009316  test    eax, eax
0x180009318  jz      loc_1800093D5
0x18000931e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009325  cmp     rcx, r12
0x180009328  jz      short loc_180009330
0x18000932a  test    byte ptr [rcx+1Ch], 1
0x18000932e  jnz     short loc_18000933D
0x180009330  mov     rax, [rsp+88h+arg_8]
0x180009338  jmp     loc_18000944F
0x18000933d  mov     edx, 11Dh
0x180009342  mov     r9d, eax
0x180009345  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000934c  mov     rcx, [rcx+10h]
0x180009350  call    WPP_SF_d
0x180009355  mov     rcx, cs:WPP_GLOBAL_Control
0x18000935c  jmp     short loc_180009330
0x18000935e  lea     rax, RPC_FWSetConfig
0x180009365  lea     rcx, RRPC_FWSetConfig
0x18000936c  test    edx, edx
0x18000936e  cmovnz  rax, rcx
0x180009372  mov     r8d, [rsi]
0x180009375  mov     dword ptr [rsp+88h+var_60], r8d
0x18000937a  mov     [rsp+88h+var_68], r14
0x18000937f  mov     r9d, edi
0x180009382  mov     r8d, r13d
0x180009385  mov     rdx, r11
0x180009388  mov     rcx, r10
0x18000938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009390  mov     edi, eax
0x180009392  mov     [rsp+88h+var_48], eax
0x180009396  test    eax, eax
0x180009398  jz      short loc_1800093D5
0x18000939a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093a1  cmp     rcx, r12
0x1800093a4  jz      short loc_1800093CB
0x1800093a6  test    byte ptr [rcx+1Ch], 1
0x1800093aa  jz      short loc_1800093CB
0x1800093ac  mov     edx, 11Eh
0x1800093b1  mov     r9d, eax
0x1800093b4  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800093bb  mov     rcx, [rcx+10h]
0x1800093bf  call    WPP_SF_d
0x1800093c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093cb  mov     rax, [rsp+88h+arg_8]
0x1800093d3  jmp     short loc_18000944F
0x1800093d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093dc  mov     rax, [rsp+88h+arg_8]
0x1800093e4  jmp     short loc_18000944F
0x1800093e6  mov     edi, eax
0x1800093e8  mov     [rsp+88h+var_48], eax
0x1800093ec  test    eax, eax
0x1800093ee  jz      short loc_180009439
0x1800093f0  lea     rax, WPP_GLOBAL_Control
0x1800093f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093fe  cmp     rcx, rax
0x180009401  jz      short loc_180009428
0x180009403  test    byte ptr [rcx+1Ch], 1
0x180009407  jz      short loc_180009428
0x180009409  mov     edx, 11Fh
0x18000940e  mov     r9d, edi
0x180009411  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180009418  mov     rcx, [rcx+10h]
0x18000941c  call    WPP_SF_d
0x180009421  mov     rcx, cs:WPP_GLOBAL_Control
0x180009428  lea     r12, WPP_GLOBAL_Control
0x18000942f  mov     rax, [rsp+88h+arg_38]
0x180009437  jmp     short loc_18000944F
0x180009439  lea     r12, WPP_GLOBAL_Control
0x180009440  mov     rax, [rsp+88h+arg_38]
0x180009448  mov     rcx, cs:WPP_GLOBAL_Control
0x18000944f  test    edi, edi
0x180009451  jnz     short loc_180009498
0x180009453  cmp     rcx, r12
0x180009456  jz      short loc_180009462
0x180009458  test    byte ptr [rcx+1Ch], 8
0x18000945c  jnz     loc_180009759
0x180009462  mov     eax, edi
0x180009464  add     rsp, 50h
0x180009468  pop     r15
0x18000946a  pop     r14
0x18000946c  pop     r13
0x18000946e  pop     r12
0x180009470  pop     rdi
0x180009471  pop     rsi
0x180009472  pop     rbx
0x180009473  retn
0x180009475  cmp     dword ptr [rsi], 0
0x180009478  jz      loc_1800092A8
0x18000947e  mov     edi, 57h ; 'W'
0x180009483  cmp     rcx, r12
0x180009486  jz      short loc_1800094C8
0x180009488  test    byte ptr [rcx+1Ch], 1
0x18000948c  jz      short loc_1800094C8
0x18000948e  mov     edx, 11Ah
0x180009493  jmp     loc_180009522
0x180009498  test    rax, rax
0x18000949b  jz      short loc_180009453
0x18000949d  cmp     dword ptr [rax+4], 2
0x1800094a1  jnz     short loc_180009453
0x1800094a3  cmp     dword ptr [rax+18h], 1
0x1800094a7  jz      short loc_180009453
0x1800094a9  mov     rcx, rax
0x1800094ac  call    Int_FWCleanupGPOPolicyStore
0x1800094b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094b8  jmp     short loc_180009453
0x1800094ba  mov     edi, 57h ; 'W'
0x1800094bf  cmp     rcx, r12
0x1800094c2  jnz     loc_18000974A
0x1800094c8  mov     rax, [rsp+88h+arg_8]
0x1800094d0  jmp     loc_18000944F
0x1800094d5  mov     edx, 115h
0x1800094da  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800094e1  mov     rcx, [rcx+10h]
0x1800094e5  call    WPP_SF_
0x1800094ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094f1  mov     r8d, [rsp+88h+arg_0]
0x1800094f9  jmp     loc_180009251
0x1800094fe  mov     edi, 57h ; 'W'
0x180009503  cmp     rcx, r12
0x180009506  jz      loc_18000944F
0x18000950c  test    byte ptr [rcx+1Ch], 1
0x180009510  jz      loc_18000944F
0x180009516  mov     edx, 116h
0x18000951b  jmp     short loc_180009522
0x18000951d  mov     edx, 117h
0x180009522  mov     r9d, edi
0x180009525  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000952c  mov     rcx, [rcx+10h]
0x180009530  call    WPP_SF_d
0x180009535  mov     rcx, cs:WPP_GLOBAL_Control
0x18000953c  jmp     short loc_1800094C8
0x18000953e  mov     edi, 57h ; 'W'
0x180009543  cmp     rcx, r12
0x180009546  jz      short loc_1800094C8
0x180009548  test    byte ptr [rcx+1Ch], 1
0x18000954c  jz      loc_1800094C8
0x180009552  mov     edx, 118h
0x180009557  jmp     short loc_180009522
0x180009559  mov     edi, 57h ; 'W'
0x18000955e  cmp     rcx, r12
0x180009561  jz      loc_1800094C8
0x180009567  test    byte ptr [rcx+1Ch], 1
0x18000956b  jz      loc_1800094C8
0x180009571  mov     edx, 119h
0x180009576  jmp     short loc_180009522
0x180009578  cmp     r13d, 12h
0x18000957c  jl      loc_1800092CA
0x180009582  mov     edi, 32h ; '2'
0x180009587  cmp     rcx, r12
0x18000958a  jz      loc_18000944F
0x180009590  test    byte ptr [rcx+1Ch], 1
0x180009594  jz      loc_18000944F
0x18000959a  mov     edx, 11Bh
0x18000959f  jmp     short loc_1800095A6
0x1800095a1  mov     edx, 121h
0x1800095a6  mov     r9d, edi
0x1800095a9  jmp     short loc_1800095B3
0x1800095ab  mov     edx, 124h
0x1800095b0  mov     r9d, eax
0x1800095b3  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800095ba  mov     rcx, [rcx+10h]
0x1800095be  call    WPP_SF_d
0x1800095c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ca  mov     rax, rbx
0x1800095cd  jmp     loc_18000944F
0x1800095d2  cmp     edx, 2
0x1800095d5  jz      short loc_1800095DC
0x1800095d7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->HandleType == FWINT_CLIENT_HANDLE_GPO")
0x1800095dc  mov     rcx, rbx
0x1800095df  call    Int_FWOpenGPOPolicyStore
0x1800095e4  mov     edi, eax
0x1800095e6  test    eax, eax
0x1800095e8  jz      short loc_180009606
0x1800095ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095f1  cmp     rcx, r12
0x1800095f4  jz      short loc_1800095CA
0x1800095f6  test    byte ptr [rcx+1Ch], 1
0x1800095fa  jz      short loc_1800095CA
0x1800095fc  mov     edx, 120h
0x180009601  mov     r9d, eax
0x180009604  jmp     short loc_1800095B3
0x180009606  cmp     qword ptr [rbx+38h], 0
0x18000960b  jnz     short loc_180009612
0x18000960d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClient->PolicyHandle != NULL")
0x180009612  test    r15b, 1
0x180009616  jz      short loc_180009634
0x180009618  mov     edi, 57h ; 'W'
0x18000961d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009624  cmp     rcx, r12
0x180009627  jz      short loc_1800095CA
0x180009629  test    byte ptr [rcx+1Ch], 1
0x18000962d  jz      short loc_1800095CA
0x18000962f  jmp     loc_1800095A1
0x180009634  mov     r15d, [rsp+88h+arg_0]
0x18000963c  mov     r9, r14
0x18000963f  mov     r8d, [rsp+88h+arg_18]
0x180009647  mov     edx, r13d
0x18000964a  mov     rcx, [rbx+38h]
0x18000964e  test    r15d, r15d
0x180009651  jz      short loc_18000969F
0x180009653  mov     [rsp+88h+var_68], rsi
0x180009658  call    cs:__imp_FwGetConfig
0x18000965f  nop     dword ptr [rax+rax+00h]
0x180009664  mov     ecx, eax
0x180009666  call    cs:__imp_FwHResultToWindowsError
0x18000966d  nop     dword ptr [rax+rax+00h]
0x180009672  mov     edi, eax
0x180009674  test    eax, eax
0x180009676  jz      short loc_1800096EC
0x180009678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000967f  cmp     rcx, r12
0x180009682  jz      loc_1800095CA
0x180009688  test    byte ptr [rcx+1Ch], 1
0x18000968c  jz      loc_1800095CA
0x180009692  mov     edx, 122h
0x180009697  mov     r9d, eax
0x18000969a  jmp     loc_1800095B3
0x18000969f  mov     eax, [rsi]
0x1800096a1  mov     dword ptr [rsp+88h+var_68], eax
0x1800096a5  call    cs:__imp_FwSetConfig
0x1800096ac  nop     dword ptr [rax+rax+00h]
0x1800096b1  mov     ecx, eax
0x1800096b3  call    cs:__imp_FwHResultToWindowsError
0x1800096ba  nop     dword ptr [rax+rax+00h]
0x1800096bf  mov     edi, eax
0x1800096c1  test    eax, eax
0x1800096c3  jz      short loc_1800096EC
0x1800096c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096cc  cmp     rcx, r12
0x1800096cf  jz      loc_1800095CA
0x1800096d5  test    byte ptr [rcx+1Ch], 1
0x1800096d9  jz      loc_1800095CA
0x1800096df  mov     edx, 123h
0x1800096e4  mov     r9d, eax
0x1800096e7  jmp     loc_1800095B3
0x1800096ec  xor     edx, edx
0x1800096ee  test    r15d, r15d
0x1800096f1  setz    dl
  ... truncated ...
```
