# FWOpenPolicyStore

- ea: `0x18000d0f0`
- end: `0x18000d976`
- name: `FWOpenPolicyStore`
- size: `2182`
- prototype: `__int64 __fastcall(unsigned __int16, __int64, unsigned int, unsigned int, unsigned int, _QWORD *)`
- caller_count: `44`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001edc`
- `0x1800022c0`
- `0x18000283c`
- `0x180003080`
- `0x180003424`
- `0x180003704`
- `0x180003d20`
- `0x180004ae8`
- `0x180005f10`
- `0x180006874`
- `0x180006ec0`
- `0x180007070`
- `0x18000af10`
- `0x18000b4b0`
- `0x18000bb40`
- `0x18000be5c`
- `0x18000bea0`
- `0x18000c810`
- `0x18000c9e0`
- `0x180013fc4`
- `0x1800191e0`
- `0x18001aa14`
- `0x18001f140`
- `0x180021b60`
- `0x1800258dc`
- `0x180027370`
- `0x180028af4`
- `0x180028c60`
- `0x180030468`
- `0x180032d78`
- `0x180034fe0`
- `0x180035340`
- `0x180035500`
- `0x180035850`
- `0x180035c10`
- `0x180045af4`
- `0x180049ad8`
- `0x18004b014`
- `0x18004e080`
- `0x18004f530`
- `0x18004fed0`
- `0x180052c60`
- `0x180054570`
- `0x18005c844`

## callees

- `0x180005e0c`
- `0x18000d0f0`
- `0x18000e460`
- `0x18000e750`
- `0x18000ed70`
- `0x180026798`
- `0x180026c9c`
- `0x1800294b0`
- `0x18003336c`
- `0x18003987c`
- `0x180054d58`
- `0x18005b948`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fa7e`
- `RPCRT4!RpcExceptionFilter` at `0x18005faa0`
- `RPCRT4!RpcExceptionFilter` at `0x18005fa7e`
- `RPCRT4!RpcExceptionFilter` at `0x18005faa0`
- `RPCRT4!NdrClientCall3` at `0x18000d462`
- `RPCRT4!NdrClientCall3` at `0x18000d462`
- `RPCRT4!RpcBindingFree` at `0x18000d561`
- `RPCRT4!RpcBindingFree` at `0x18000d561`
- `ntdll!EtwEventWrite` at `0x18000d166`
- `ntdll!EtwEventWrite` at `0x18000d5d3`
- `ntdll!EtwEventWrite` at `0x18000d166`
- `ntdll!EtwEventWrite` at `0x18000d5d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d1aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d1aa`
- `fwbase!FwBaseAlloc` at `0x18000d33c`
- `fwbase!FwBaseAlloc` at `0x18000d33c`
- `fwbase!FwBaseFree` at `0x18000d581`
- `fwbase!FwBaseFree` at `0x18000d598`
- `fwbase!FwBaseFree` at `0x18000d581`
- `fwbase!FwBaseFree` at `0x18000d598`

## pseudocode

```c
__int64 __fastcall FWOpenPolicyStore(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        _QWORD *a6)
{
  char v6; // al
  int v8; // r8d
  _OWORD *v10; // rdi
  unsigned int v11; // r15d
  unsigned int started; // eax
  FwPolicy2 *v13; // rcx
  unsigned __int16 v14; // r13
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r9
  _OWORD *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // eax
  unsigned int Pointer; // eax
  _QWORD *v23; // rsi
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rcx
  unsigned __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // [rsp+20h] [rbp-B8h]
  __int64 v32; // [rsp+28h] [rbp-B0h]
  __int64 v33; // [rsp+30h] [rbp-A8h]
  int v36; // [rsp+90h] [rbp-48h] BYREF
  int v37; // [rsp+94h] [rbp-44h] BYREF

  v6 = a4;
  v8 = a2;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_OpenPolicyStore, 0, 0);
    v6 = a4;
    v8 = a2;
  }
  v10 = 0;
  v36 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
  {
    v11 = a5;
  }
  else
  {
    v11 = a5;
    WPP_SF_Sddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
      v8,
      a3,
      v6,
      a5);
  }
  GetTickCount64();
  started = Int_FwStartFirewallService();
  if ( !started )
    goto LABEL_9;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, started);
LABEL_9:
    v13 = WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    v15 = 87;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 18;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  v14 = 512;
  if ( (unsigned __int16)(a1 - 512) > 0x21u )
  {
    v15 = 1306;
    if ( v13 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
      goto LABEL_55;
    v16 = 19;
LABEL_34:
    v17 = v15;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v13 + 2), v16, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
LABEL_54:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  if ( a3 - 1 > 0xB )
  {
    v15 = 87;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 20;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  if ( a4 - 1 > 1 )
  {
    v15 = 87;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 21;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  if ( v11 >= 0x20 )
  {
    v15 = 87;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 22;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  if ( a3 == 1 && a4 != 1 )
  {
    v15 = 5;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 23;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  if ( a3 == 3 && a4 != 1 )
  {
    v15 = 5;
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    {
      v16 = 24;
      goto LABEL_34;
    }
    goto LABEL_55;
  }
  if ( a3 != 5 && (v11 & 1) != 0 )
  {
    v15 = 87;
    if ( v13 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
      goto LABEL_55;
    v16 = 25;
    goto LABEL_34;
  }
  if ( a3 != 6 )
  {
    if ( a2 )
    {
      v28 = -1;
      do
        ++v28;
      while ( *(_WORD *)(a2 + 2 * v28) );
      if ( v28 > 0xFF )
      {
        v15 = 87;
        if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        {
          v16 = 26;
          goto LABEL_34;
        }
        goto LABEL_55;
      }
    }
  }
  if ( (v11 & 0xE) != 0 && a3 != 6 )
  {
    v15 = 87;
    if ( v13 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 1) == 0 )
      goto LABEL_55;
    v16 = 27;
    goto LABEL_34;
  }
  *a6 = 0;
  v18 = (_OWORD *)FwBaseAlloc(80);
  v10 = v18;
  if ( v18 )
  {
    *v18 = 0;
    v18[1] = 0;
    v18[2] = 0;
    v18[3] = 0;
    v18[4] = 0;
    v19 = Int_FWCreateConnectionHandle(a1, a2, a3, a4, v11, v18);
    v15 = v19;
    if ( v19 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 29;
        v17 = v19;
        goto LABEL_35;
      }
      goto LABEL_55;
    }
    if ( a1 > 0x200u && *((_DWORD *)v10 + 1) <= 1u )
    {
      v36 = 4;
      v20 = FWGetGlobalConfig(512, a2, 5, 11, v19, (__int64)&v37, (__int64)&v36);
      v15 = v20;
      if ( v20 == 1783 || v20 == 87 )
      {
        v15 = 0;
        v37 = 512;
      }
      else
      {
        v14 = v37;
      }
      if ( v15 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 30;
          goto LABEL_34;
        }
        goto LABEL_55;
      }
      if ( a1 > v14 )
        a1 = v14;
    }
    *((_WORD *)v10 + 1) = a1;
    v21 = *((_DWORD *)v10 + 1);
    if ( v21 )
    {
      if ( v21 == 1 )
      {
        v29 = RRPC_FWOpenPolicyStore(*((_QWORD *)v10 + 4), a1, a3, a4, v11, (__int64)v10 + 40);
        v15 = v29;
        if ( v29 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v29);
            v13 = WPP_GLOBAL_Control;
          }
          goto LABEL_55;
        }
        v23 = a6;
        v36 = 4;
        v30 = FWGetGlobalConfig(a1, a2, 5, 1, 0, (__int64)(v10 + 3), (__int64)&v36);
        v15 = v30;
        if ( v30 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 35;
            v17 = v30;
            goto LABEL_35;
          }
          goto LABEL_55;
        }
      }
      else
      {
        v23 = a6;
      }
    }
    else
    {
      LODWORD(v33) = a4;
      LODWORD(v32) = a3;
      LODWORD(v31) = a1;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&FW_ProxyInfo,
                                0,
                                0,
                                *((_QWORD *)v10 + 4),
                                v31,
                                v32,
                                v33,
                                v11,
                                (char *)v10 + 40).Pointer;
      v15 = Pointer;
      if ( Pointer )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Pointer);
          v13 = WPP_GLOBAL_Control;
        }
        goto LABEL_55;
      }
      v23 = a6;
      *((_DWORD *)v10 + 12) = 545;
    }
    *v23 = v10;
    goto LABEL_54;
  }
  v15 = 14;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 28;
    goto LABEL_34;
  }
LABEL_55:
  if ( v15 )
  {
    if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 377, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    if ( v10 )
    {
      v24 = *((_DWORD *)v10 + 1);
      if ( v24 > 1 )
      {
        if ( v24 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        Int_FWCleanupGPOPolicyStore(v10);
      }
      else if ( *((_QWORD *)v10 + 4) )
      {
        v25 = RpcBindingFree((RPC_BINDING_HANDLE *)v10 + 4);
        if ( v25 )
          MicrosoftTelemetryAssertTriggeredArgs(v26, v25);
        *((_QWORD *)v10 + 4) = 0;
      }
      FwBaseFree(*((_QWORD *)v10 + 1));
      *((_QWORD *)v10 + 1) = 0;
    }
    FwBaseFree(v10);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v13 + 2), 36, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_OpenPolicyStore, 0, 0);
  return v15;
}

```

## disassembly

```asm
0x18000d0f0  push    rbx
0x18000d0f2  push    rsi
0x18000d0f3  push    rdi
0x18000d0f4  push    r12
0x18000d0f6  push    r13
0x18000d0f8  push    r14
0x18000d0fa  push    r15
0x18000d0fc  sub     rsp, 0A0h
0x18000d103  mov     rax, cs:__security_cookie
0x18000d10a  xor     rax, rsp
0x18000d10d  mov     [rsp+0D8h+var_40], rax
0x18000d115  mov     eax, r9d
0x18000d118  mov     [rsp+0D8h+var_80], eax
0x18000d11c  mov     esi, r8d
0x18000d11f  mov     r8, rdx
0x18000d122  mov     [rsp+0D8h+var_78], rdx
0x18000d127  movzx   r14d, cx
0x18000d12b  mov     [rsp+0D8h+var_88], cx
0x18000d130  mov     [rsp+0D8h+var_50], rdx
0x18000d138  mov     rbx, [rsp+0D8h+arg_28]
0x18000d140  mov     [rsp+0D8h+var_60], rbx
0x18000d145  mov     [rsp+0D8h+var_58], rbx
0x18000d14d  mov     rcx, cs:g_Provider
0x18000d154  test    rcx, rcx
0x18000d157  jz      short loc_18000D17B
0x18000d159  xor     r9d, r9d
0x18000d15c  xor     r8d, r8d
0x18000d15f  lea     rdx, MPS_CLNT_API_Enter_OpenPolicyStore
0x18000d166  call    cs:__imp_EtwEventWrite
0x18000d16d  nop     dword ptr [rax+rax+00h]
0x18000d172  mov     eax, [rsp+0D8h+var_80]
0x18000d176  mov     r8, [rsp+0D8h+var_78]
0x18000d17b  xor     edi, edi
0x18000d17d  mov     [rsp+0D8h+var_48], edi
0x18000d184  mov     [rsp+0D8h+var_44], edi
0x18000d18b  lea     r12, WPP_GLOBAL_Control
0x18000d192  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d199  cmp     rcx, r12
0x18000d19c  jnz     loc_18000D29A
0x18000d1a2  mov     r15d, [rsp+0D8h+arg_20]
0x18000d1aa  call    cs:__imp_GetTickCount64
0x18000d1b1  nop     dword ptr [rax+rax+00h]
0x18000d1b6  call    Int_FwStartFirewallService
0x18000d1bb  test    eax, eax
0x18000d1bd  jz      short loc_18000D1E9
0x18000d1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c6  cmp     rcx, r12
0x18000d1c9  jz      short loc_18000D1F0
0x18000d1cb  test    byte ptr [rcx+1Ch], 1
0x18000d1cf  jz      short loc_18000D1F0
0x18000d1d1  mov     edx, 11h
0x18000d1d6  mov     r9d, eax
0x18000d1d9  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d1e0  mov     rcx, [rcx+10h]
0x18000d1e4  call    WPP_SF_d
0x18000d1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f0  test    rbx, rbx
0x18000d1f3  jz      loc_18000D643
0x18000d1f9  mov     r13d, 200h
0x18000d1ff  movzx   eax, r14w
0x18000d203  sub     ax, r13w
0x18000d207  cmp     ax, 21h ; '!'
0x18000d20b  ja      loc_18000D2FF
0x18000d211  lea     eax, [rsi-1]
0x18000d214  cmp     eax, 0Bh
0x18000d217  ja      loc_18000D8FD
0x18000d21d  mov     edx, [rsp+0D8h+var_80]
0x18000d221  lea     eax, [rdx-1]
0x18000d224  cmp     eax, 1
0x18000d227  ja      loc_18000D8DB
0x18000d22d  cmp     r15d, 20h ; ' '
0x18000d231  jnb     loc_18000D665
0x18000d237  cmp     esi, 1
0x18000d23a  jz      loc_18000D618
0x18000d240  cmp     esi, 3
0x18000d243  jz      loc_18000D687
0x18000d249  cmp     esi, 5
0x18000d24c  jnz     loc_18000D2D6
0x18000d252  cmp     esi, 6
0x18000d255  jz      short loc_18000D265
0x18000d257  mov     rax, [rsp+0D8h+var_78]
0x18000d25c  test    rax, rax
0x18000d25f  jnz     loc_18000D6B2
0x18000d265  test    r15b, 0Eh
0x18000d269  jz      loc_18000D334
0x18000d26f  cmp     esi, 6
0x18000d272  jz      loc_18000D334
0x18000d278  mov     ebx, 57h ; 'W'
0x18000d27d  cmp     rcx, r12
0x18000d280  jz      loc_18000D532
0x18000d286  test    byte ptr [rcx+1Ch], 1
0x18000d28a  jz      loc_18000D532
0x18000d290  mov     edx, 1Bh
0x18000d295  jmp     loc_18000D31C
0x18000d29a  test    byte ptr [rcx+1Ch], 8
0x18000d29e  jz      loc_18000D1A2
0x18000d2a4  mov     edx, 10h
0x18000d2a9  mov     r15d, [rsp+0D8h+arg_20]
0x18000d2b1  mov     dword ptr [rsp+0D8h+var_A8], r15d
0x18000d2b6  mov     dword ptr [rsp+0D8h+var_B0], eax
0x18000d2ba  mov     dword ptr [rsp+0D8h+var_B8], esi
0x18000d2be  mov     r9, r8
0x18000d2c1  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d2c8  mov     rcx, [rcx+10h]
0x18000d2cc  call    WPP_SF_Sddd
0x18000d2d1  jmp     loc_18000D1AA
0x18000d2d6  test    r15b, 1
0x18000d2da  jz      loc_18000D252
0x18000d2e0  mov     ebx, 57h ; 'W'
0x18000d2e5  cmp     rcx, r12
0x18000d2e8  jz      loc_18000D532
0x18000d2ee  test    byte ptr [rcx+1Ch], 1
0x18000d2f2  jz      loc_18000D532
0x18000d2f8  mov     edx, 19h
0x18000d2fd  jmp     short loc_18000D31C
0x18000d2ff  mov     ebx, 51Ah
0x18000d304  cmp     rcx, r12
0x18000d307  jz      loc_18000D532
0x18000d30d  test    byte ptr [rcx+1Ch], 1
0x18000d311  jz      loc_18000D532
0x18000d317  mov     edx, 13h
0x18000d31c  mov     r9d, ebx
0x18000d31f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d326  mov     rcx, [rcx+10h]
0x18000d32a  call    WPP_SF_d
0x18000d32f  jmp     loc_18000D52B
0x18000d334  mov     [rbx], rdi
0x18000d337  mov     ecx, 50h ; 'P'
0x18000d33c  call    cs:__imp_FwBaseAlloc
0x18000d343  nop     dword ptr [rax+rax+00h]
0x18000d348  mov     rdi, rax
0x18000d34b  mov     [rsp+0D8h+var_68], rax
0x18000d350  test    rax, rax
0x18000d353  jz      loc_18000D6F1
0x18000d359  xorps   xmm0, xmm0
0x18000d35c  movups  xmmword ptr [rax], xmm0
0x18000d35f  movups  xmmword ptr [rax+10h], xmm0
0x18000d363  movups  xmmword ptr [rax+20h], xmm0
0x18000d367  movups  xmmword ptr [rax+30h], xmm0
0x18000d36b  movups  xmmword ptr [rax+40h], xmm0
0x18000d36f  mov     [rsp+0D8h+var_B0], rax
0x18000d374  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x18000d379  mov     r9d, [rsp+0D8h+var_80]
0x18000d37e  mov     r8d, esi
0x18000d381  mov     rdx, [rsp+0D8h+var_78]
0x18000d386  movzx   ecx, r14w
0x18000d38a  call    Int_FWCreateConnectionHandle
0x18000d38f  mov     ebx, eax
0x18000d391  test    eax, eax
0x18000d393  jnz     loc_18000D71A
0x18000d399  cmp     r14w, r13w
0x18000d39d  jbe     short loc_18000D417
0x18000d39f  cmp     dword ptr [rdi+4], 1
0x18000d3a3  ja      short loc_18000D417
0x18000d3a5  mov     [rsp+0D8h+var_48], 4
0x18000d3b0  mov     ecx, r13d
0x18000d3b3  lea     rax, [rsp+0D8h+var_48]
0x18000d3bb  mov     [rsp+0D8h+var_A8], rax
0x18000d3c0  lea     rax, [rsp+0D8h+var_44]
0x18000d3c8  mov     [rsp+0D8h+var_B0], rax
0x18000d3cd  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000d3d1  mov     r9d, 0Bh
0x18000d3d7  mov     r8d, 5
0x18000d3dd  mov     rdx, [rsp+0D8h+var_78]
0x18000d3e2  call    FWGetGlobalConfig
0x18000d3e7  mov     ebx, eax
0x18000d3e9  cmp     eax, 6F7h
0x18000d3ee  jz      loc_18000D741
0x18000d3f4  cmp     eax, 57h ; 'W'
0x18000d3f7  jz      loc_18000D741
0x18000d3fd  mov     r13d, [rsp+0D8h+var_44]
0x18000d405  test    ebx, ebx
0x18000d407  jnz     loc_18000D750
0x18000d40d  cmp     r14w, r13w
0x18000d411  ja      loc_18000D774
0x18000d417  mov     [rdi+2], r14w
0x18000d41c  mov     eax, [rdi+4]
0x18000d41f  test    eax, eax
0x18000d421  jnz     loc_18000D605
0x18000d427  mov     [rsp+0D8h+var_78], 0
0x18000d430  lea     rax, [rdi+28h]
0x18000d434  movzx   ecx, r14w
0x18000d438  mov     [rsp+0D8h+var_98], rax
0x18000d43d  mov     [rsp+0D8h+var_A0], r15d
0x18000d442  mov     eax, [rsp+0D8h+var_80]
0x18000d446  mov     dword ptr [rsp+0D8h+var_A8], eax
0x18000d44a  mov     dword ptr [rsp+0D8h+var_B0], esi
0x18000d44e  mov     dword ptr [rsp+0D8h+var_B8], ecx
0x18000d452  mov     r9, [rdi+20h]
0x18000d456  xor     r8d, r8d; pReturnValue
0x18000d459  xor     edx, edx; nProcNum
0x18000d45b  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000d462  call    cs:__imp_NdrClientCall3
0x18000d469  nop     dword ptr [rax+rax+00h]
0x18000d46e  mov     rbx, rax
0x18000d471  mov     [rsp+0D8h+var_78], rax
0x18000d476  mov     [rsp+0D8h+var_70], eax
0x18000d47a  test    eax, eax
0x18000d47c  jz      short loc_18000D4B6
0x18000d47e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d485  cmp     rcx, r12
0x18000d488  jnz     short loc_18000D48F
0x18000d48a  jmp     loc_18000D532
0x18000d48f  test    byte ptr [rcx+1Ch], 1
0x18000d493  jz      short loc_18000D48A
0x18000d495  mov     edx, 1Fh
0x18000d49a  mov     r9d, eax
0x18000d49d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d4a4  mov     rcx, [rcx+10h]
0x18000d4a8  call    WPP_SF_d
0x18000d4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4b4  jmp     short loc_18000D48A
0x18000d4b6  mov     rsi, [rsp+0D8h+var_60]
0x18000d4bb  jmp     short loc_18000D521
0x18000d4bd  mov     ebx, eax
0x18000d4bf  mov     [rsp+0D8h+var_70], eax
0x18000d4c3  test    eax, eax
0x18000d4c5  jz      short loc_18000D50D
0x18000d4c7  lea     rdx, WPP_GLOBAL_Control
0x18000d4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4d5  cmp     rcx, rdx
0x18000d4d8  jz      short loc_18000D4FF
0x18000d4da  test    byte ptr [rcx+1Ch], 1
0x18000d4de  jz      short loc_18000D4FF
0x18000d4e0  mov     edx, 20h ; ' '
0x18000d4e5  mov     r9d, eax
0x18000d4e8  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000d4ef  mov     rcx, [rcx+10h]
0x18000d4f3  call    WPP_SF_d
0x18000d4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4ff  lea     r12, WPP_GLOBAL_Control
0x18000d506  mov     rdi, [rsp+0D8h+var_68]
0x18000d50b  jmp     short loc_18000D532
0x18000d50d  lea     r12, WPP_GLOBAL_Control
0x18000d514  mov     rdi, [rsp+0D8h+var_68]
0x18000d519  mov     rsi, [rsp+0D8h+var_58]
0x18000d521  mov     dword ptr [rdi+30h], 221h
0x18000d528  mov     [rsi], rdi
0x18000d52b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d532  test    ebx, ebx
0x18000d534  jz      short loc_18000D5AB
0x18000d536  cmp     rcx, r12
0x18000d539  jz      short loc_18000D545
0x18000d53b  test    byte ptr [rcx+1Ch], 8
0x18000d53f  jnz     loc_18000D91F
0x18000d545  test    rdi, rdi
0x18000d548  jz      short loc_18000D595
0x18000d54a  mov     eax, [rdi+4]
0x18000d54d  cmp     eax, 1
0x18000d550  ja      loc_18000D939
0x18000d556  cmp     qword ptr [rdi+20h], 0
0x18000d55b  jz      short loc_18000D57D
0x18000d55d  lea     rcx, [rdi+20h]; Binding
0x18000d561  call    cs:__imp_RpcBindingFree
0x18000d568  nop     dword ptr [rax+rax+00h]
0x18000d56d  test    eax, eax
0x18000d56f  jnz     loc_18000D950
0x18000d575  mov     qword ptr [rdi+20h], 0
0x18000d57d  mov     rcx, [rdi+8]
0x18000d581  call    cs:__imp_FwBaseFree
0x18000d588  nop     dword ptr [rax+rax+00h]
0x18000d58d  mov     qword ptr [rdi+8], 0
0x18000d595  mov     rcx, rdi
0x18000d598  call    cs:__imp_FwBaseFree
0x18000d59f  nop     dword ptr [rax+rax+00h]
0x18000d5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5ab  cmp     rcx, r12
0x18000d5ae  jz      short loc_18000D5BA
0x18000d5b0  test    byte ptr [rcx+1Ch], 8
0x18000d5b4  jnz     loc_18000D95C
0x18000d5ba  mov     rcx, cs:g_Provider
0x18000d5c1  test    rcx, rcx
0x18000d5c4  jz      short loc_18000D5DF
0x18000d5c6  xor     r9d, r9d
0x18000d5c9  xor     r8d, r8d
0x18000d5cc  lea     rdx, MPS_CLNT_API_Exit_OpenPolicyStore
0x18000d5d3  call    cs:__imp_EtwEventWrite
0x18000d5da  nop     dword ptr [rax+rax+00h]
0x18000d5df  mov     eax, ebx
0x18000d5e1  mov     rcx, [rsp+0D8h+var_40]
0x18000d5e9  xor     rcx, rsp; StackCookie
0x18000d5ec  call    __security_check_cookie
0x18000d5f1  add     rsp, 0A0h
0x18000d5f8  pop     r15
0x18000d5fa  pop     r14
0x18000d5fc  pop     r13
0x18000d5fe  pop     r12
0x18000d600  pop     rdi
0x18000d601  pop     rsi
0x18000d602  pop     rbx
0x18000d603  retn
0x18000d605  cmp     eax, 1
0x18000d608  jz      loc_18000D783
0x18000d60e  mov     rsi, [rsp+0D8h+var_60]
0x18000d613  jmp     loc_18000D528
0x18000d618  cmp     edx, 1
0x18000d61b  jz      loc_18000D240
0x18000d621  mov     ebx, 5
0x18000d626  cmp     rcx, r12
0x18000d629  jz      loc_18000D532
  ... truncated ...
```
