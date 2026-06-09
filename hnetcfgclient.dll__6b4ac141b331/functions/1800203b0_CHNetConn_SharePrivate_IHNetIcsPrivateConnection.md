# CHNetConn::SharePrivate(IHNetIcsPrivateConnection * *)

- ea: `0x1800203b0`
- end: `0x180020921`
- name: `?SharePrivate@CHNetConn@@UEAAJPEAPEAUIHNetIcsPrivateConnection@@@Z`
- size: `1393`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct IHNetIcsPrivateConnection **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000fc28`
- `0x180018560`
- `0x18001b1e8`
- `0x18001e004`
- `0x18001e130`
- `0x18001e7f0`
- `0x18001e954`
- `0x18001ee3c`
- `0x18001fe80`
- `0x1800203b0`
- `0x180021458`
- `0x180029c80`
- `0x18002a61c`
- `0x18002ab30`
- `0x18002ae2c`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800206e4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800206e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206f2`

## pseudocode

```c
__int64 __fastcall CHNetConn::SharePrivate(CHNetConn *this, struct IHNetIcsPrivateConnection **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  int updated; // eax
  PVOID *v9; // rcx
  unsigned int v11; // ecx
  int ConnectionPropertiesObject; // eax
  int Properties; // eax
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HANDLE v17; // rax
  int v18; // eax
  CHNetConn *v19; // rsi
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  struct IWbemClassObject *v22; // [rsp+30h] [rbp-40h] BYREF
  struct _GUID v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+58h] [rbp-18h]

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 8) == 0 || *((_BYTE *)v4 + 25) < 2u )
      goto LABEL_12;
    v6 = 133;
    goto LABEL_10;
  }
  v5 = 0;
  *a2 = 0;
  if ( CHNetConn::ProhibitedByPolicy(this, 0x32u) )
  {
    v5 = -2147024891;
    v11 = (unsigned int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147942405LL);
    }
  }
  if ( IsRoutingProtocolInstalled(v11) )
  {
    v5 = -2147024114;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v6 = 135;
LABEL_10:
    v7 = v5;
LABEL_11:
    WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
LABEL_12:
    CHNetConn::RestoreIpConfiguration(this);
    goto LABEL_13;
  }
  if ( v5 )
    goto LABEL_12;
  ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject(this, &v22);
  v5 = ConnectionPropertiesObject;
  if ( ConnectionPropertiesObject < 0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v6 = 136;
    v7 = (unsigned int)ConnectionPropertiesObject;
    goto LABEL_11;
  }
  if ( ConnectionPropertiesObject )
    goto LABEL_12;
  Properties = CHNetConn::InternalGetProperties(this, v22, (struct tagHNET_CONN_PROPERTIES *)&v24);
  v5 = Properties;
  if ( Properties < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      137,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)Properties);
  }
  UpdatePropertiesWithNetcon2(this, (struct tagHNET_CONN_PROPERTIES *)&v24);
  if ( v5 )
    goto LABEL_83;
  if ( !BYTE1(v25) || BYTE3(v24) == 1 )
  {
    v5 = -2147418113;
    goto LABEL_83;
  }
  v14 = CHNetConn::BackupIpConfiguration(this);
  v5 = v14;
  if ( v14 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 138;
LABEL_79:
      WPP_SF_d(v15[2], v16, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v14);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( v14 )
    goto LABEL_83;
  v17 = OpenEventW(2u, 0, L"IcsUpgradeEventName_");
  if ( v17 )
  {
    CloseHandle(v17);
    goto LABEL_68;
  }
  v14 = CHNetConn::SetupConnectionAsPrivateLan(this);
  v5 = v14;
  if ( v14 >= 0 )
  {
    if ( v14 )
      goto LABEL_83;
LABEL_68:
    v14 = SetBooleanValue(v22, L"IsIcsPrivate", 1u);
    v5 = v14;
    if ( v14 >= 0 )
    {
      if ( v14 )
        goto LABEL_83;
      v14 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64))(**((_QWORD **)this + 8) + 112LL))(
              *((_QWORD *)this + 8),
              v22,
              1);
      v5 = v14;
      if ( v14 >= 0 )
      {
        if ( !v14 )
          CHNetConn::UpdateNetman(this);
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 141;
          goto LABEL_79;
        }
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 140;
        goto LABEL_79;
      }
    }
    goto LABEL_83;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 139;
    goto LABEL_79;
  }
LABEL_83:
  ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
  if ( v5 )
    goto LABEL_12;
  *(_QWORD *)&v23.Data1 = 0;
  v18 = ATL::CComObject<CHNIcsPrivateConn>::CreateInstance(&v23);
  v5 = v18;
  if ( v18 >= 0 )
  {
    v19 = *(CHNetConn **)&v23.Data1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v23.Data1 + 8LL))(*(_QWORD *)&v23.Data1);
    v5 = CHNetConn::InitializeFull(
           v19,
           *((struct IWbemServices **)this + 8),
           *((unsigned __int16 **)this + 9),
           *((unsigned __int16 **)this + 10),
           *((_BYTE *)this + 96));
    if ( (v5 & 0x80000000) == 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(CHNetConn *, GUID *, struct IHNetIcsPrivateConnection **))v19)(
             v19,
             &GUID_85d18b74_3032_11d4_9348_00c04f8eeb71,
             a2);
      if ( (v5 & 0x80000000) == 0 )
        goto LABEL_100;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v21 = 144;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v21 = 143;
    }
    WPP_SF_d(v20[2], v21, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
LABEL_100:
    (*(void (__fastcall **)(CHNetConn *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_13:
    if ( !v5 )
    {
      v23 = *(struct _GUID *)*((_QWORD *)this + 13);
      updated = UpdateSharingSettingsFromStorage(&v23, 0);
      v5 = updated;
      if ( updated > 0 )
        v5 = (unsigned __int16)updated | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 24LL))(*a2);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
        *a2 = 0;
      }
      CHNetConn::RefreshNetConnectionsUI(this, 0);
    }
    goto LABEL_23;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      142,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)v18);
LABEL_23:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 146, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800203b0  mov     [rsp-28h+arg_10], rbx
0x1800203b5  mov     [rsp-28h+arg_18], rsi
0x1800203ba  push    rbp
0x1800203bb  push    rdi
0x1800203bc  push    r12
0x1800203be  push    r13
0x1800203c0  push    r14
0x1800203c2  mov     rbp, rsp
0x1800203c5  sub     rsp, 70h
0x1800203c9  mov     rax, cs:__security_cookie
0x1800203d0  xor     rax, rsp
0x1800203d3  mov     [rbp+var_10], rax
0x1800203d7  mov     r14, rdx
0x1800203da  mov     rdi, rcx
0x1800203dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203e4  lea     rsi, WPP_GLOBAL_Control
0x1800203eb  mov     r13b, 8
0x1800203ee  cmp     rcx, rsi
0x1800203f1  jz      short loc_18002041B
0x1800203f3  test    [rcx+1Ch], r13b
0x1800203f7  jz      short loc_18002041B
0x1800203f9  cmp     byte ptr [rcx+19h], 6
0x1800203fd  jb      short loc_18002041B
0x1800203ff  mov     rcx, [rcx+10h]
0x180020403  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002040a  mov     edx, 84h
0x18002040f  call    WPP_SF_
0x180020414  mov     rcx, cs:WPP_GLOBAL_Control
0x18002041b  xor     eax, eax
0x18002041d  mov     [rbp+var_20], rax
0x180020421  mov     [rbp+var_18], eax
0x180020424  mov     [rbp+var_40], rax
0x180020428  lea     r12d, [rax+2]
0x18002042c  test    r14, r14
0x18002042f  jnz     loc_180020553
0x180020435  mov     ebx, 80004003h
0x18002043a  cmp     rcx, rsi
0x18002043d  jz      short loc_180020463
0x18002043f  test    [rcx+1Ch], r13b
0x180020443  jz      short loc_180020463
0x180020445  cmp     [rcx+19h], r12b
0x180020449  jb      short loc_180020463
0x18002044b  mov     edx, 85h
0x180020450  mov     r9d, ebx
0x180020453  mov     rcx, [rcx+10h]
0x180020457  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002045e  call    WPP_SF_d
0x180020463  mov     rcx, rdi; this
0x180020466  call    ?RestoreIpConfiguration@CHNetConn@@IEAAJXZ; CHNetConn::RestoreIpConfiguration(void)
0x18002046b  test    ebx, ebx
0x18002046d  jnz     loc_1800204FC
0x180020473  mov     rax, [rdi+68h]
0x180020477  lea     rcx, [rbp+var_30]; struct _GUID
0x18002047b  xor     edx, edx; bool
0x18002047d  movups  xmm0, xmmword ptr [rax]
0x180020480  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x180020485  call    ?UpdateSharingSettingsFromStorage@@YAKU_GUID@@_N@Z; UpdateSharingSettingsFromStorage(_GUID,bool)
0x18002048a  mov     ebx, eax
0x18002048c  test    eax, eax
0x18002048e  jle     short loc_180020499
0x180020490  movzx   ebx, ax
0x180020493  or      ebx, 80070000h
0x180020499  test    ebx, ebx
0x18002049b  jns     short loc_1800204F2
0x18002049d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204a4  cmp     rcx, rsi
0x1800204a7  jz      short loc_1800204CD
0x1800204a9  test    [rcx+1Ch], r13b
0x1800204ad  jz      short loc_1800204CD
0x1800204af  cmp     [rcx+19h], r12b
0x1800204b3  jb      short loc_1800204CD
0x1800204b5  mov     rcx, [rcx+10h]
0x1800204b9  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x1800204c0  mov     edx, 91h
0x1800204c5  mov     r9d, ebx
0x1800204c8  call    WPP_SF_d
0x1800204cd  mov     rcx, [r14]
0x1800204d0  mov     rax, [rcx]
0x1800204d3  mov     rax, [rax+18h]
0x1800204d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204dc  mov     rcx, [r14]
0x1800204df  mov     rax, [rcx]
0x1800204e2  mov     rax, [rax+10h]
0x1800204e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204eb  mov     qword ptr [r14], 0
0x1800204f2  xor     edx, edx; int
0x1800204f4  mov     rcx, rdi; this
0x1800204f7  call    ?RefreshNetConnectionsUI@CHNetConn@@IEAAJH@Z; CHNetConn::RefreshNetConnectionsUI(int)
0x1800204fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020503  cmp     rcx, rsi
0x180020506  jz      short loc_18002052C
0x180020508  test    [rcx+1Ch], r13b
0x18002050c  jz      short loc_18002052C
0x18002050e  cmp     byte ptr [rcx+19h], 6
0x180020512  jb      short loc_18002052C
0x180020514  mov     rcx, [rcx+10h]
0x180020518  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002051f  mov     edx, 92h
0x180020524  mov     r9d, ebx
0x180020527  call    WPP_SF_d
0x18002052c  mov     eax, ebx
0x18002052e  mov     rcx, [rbp+var_10]
0x180020532  xor     rcx, rsp; StackCookie
0x180020535  call    __security_check_cookie
0x18002053a  lea     r11, [rsp+70h+var_s0]
0x18002053f  mov     rbx, [r11+40h]
0x180020543  mov     rsi, [r11+48h]
0x180020547  mov     rsp, r11
0x18002054a  pop     r14
0x18002054c  pop     r13
0x18002054e  pop     r12
0x180020550  pop     rdi
0x180020551  pop     rbp
0x180020552  retn
0x180020553  xor     ebx, ebx
0x180020555  mov     [r14], rax
0x180020558  mov     rcx, rdi; this
0x18002055b  lea     edx, [rbx+32h]; unsigned int
0x18002055e  call    ?ProhibitedByPolicy@CHNetConn@@IEAAEK@Z; CHNetConn::ProhibitedByPolicy(ulong)
0x180020563  test    al, al
0x180020565  jz      short loc_18002059C
0x180020567  mov     ebx, 80070005h
0x18002056c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020573  cmp     rcx, rsi
0x180020576  jz      short loc_18002059C
0x180020578  test    [rcx+1Ch], r13b
0x18002057c  jz      short loc_18002059C
0x18002057e  cmp     [rcx+19h], r12b
0x180020582  jb      short loc_18002059C
0x180020584  mov     rcx, [rcx+10h]
0x180020588  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002058f  mov     edx, 86h
0x180020594  mov     r9d, ebx
0x180020597  call    WPP_SF_d
0x18002059c  call    ?IsRoutingProtocolInstalled@@YAEK@Z; IsRoutingProtocolInstalled(ulong)
0x1800205a1  test    al, al
0x1800205a3  jz      short loc_1800205D8
0x1800205a5  mov     ebx, 8007030Eh
0x1800205aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205b1  cmp     rcx, rsi
0x1800205b4  jz      loc_180020463
0x1800205ba  test    [rcx+1Ch], r13b
0x1800205be  jz      loc_180020463
0x1800205c4  cmp     [rcx+19h], r12b
0x1800205c8  jb      loc_180020463
0x1800205ce  mov     edx, 87h
0x1800205d3  jmp     loc_180020450
0x1800205d8  test    ebx, ebx
0x1800205da  jnz     loc_180020463
0x1800205e0  lea     rdx, [rbp+var_40]; struct IWbemClassObject **
0x1800205e4  mov     rcx, rdi; this
0x1800205e7  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x1800205ec  mov     ebx, eax
0x1800205ee  test    eax, eax
0x1800205f0  jns     short loc_180020623
0x1800205f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205f9  cmp     rcx, rsi
0x1800205fc  jz      loc_180020463
0x180020602  test    [rcx+1Ch], r13b
0x180020606  jz      loc_180020463
0x18002060c  cmp     [rcx+19h], r12b
0x180020610  jb      loc_180020463
0x180020616  mov     edx, 88h
0x18002061b  mov     r9d, eax
0x18002061e  jmp     loc_180020453
0x180020623  jnz     loc_180020463
0x180020629  mov     rdx, [rbp+var_40]; struct IWbemClassObject *
0x18002062d  lea     r8, [rbp+var_20]; struct tagHNET_CONN_PROPERTIES *
0x180020631  mov     rcx, rdi; this
0x180020634  call    ?InternalGetProperties@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_CONN_PROPERTIES@@@Z; CHNetConn::InternalGetProperties(IWbemClassObject *,tagHNET_CONN_PROPERTIES *)
0x180020639  mov     ebx, eax
0x18002063b  test    eax, eax
0x18002063d  jns     short loc_18002066F
0x18002063f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020646  cmp     rcx, rsi
0x180020649  jz      short loc_18002066F
0x18002064b  test    [rcx+1Ch], r13b
0x18002064f  jz      short loc_18002066F
0x180020651  cmp     [rcx+19h], r12b
0x180020655  jb      short loc_18002066F
0x180020657  mov     rcx, [rcx+10h]
0x18002065b  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020662  mov     edx, 89h
0x180020667  mov     r9d, eax
0x18002066a  call    WPP_SF_d
0x18002066f  lea     rdx, [rbp+var_20]; struct tagHNET_CONN_PROPERTIES *
0x180020673  mov     rcx, rdi; struct IHNetConnection *
0x180020676  call    ?UpdatePropertiesWithNetcon2@@YAJPEAUIHNetConnection@@PEAUtagHNET_CONN_PROPERTIES@@@Z; UpdatePropertiesWithNetcon2(IHNetConnection *,tagHNET_CONN_PROPERTIES *)
0x18002067b  test    ebx, ebx
0x18002067d  jnz     loc_1800207E7
0x180020683  cmp     byte ptr [rbp+var_18+1], bl
0x180020686  jz      loc_1800207E2
0x18002068c  cmp     byte ptr [rbp+var_20+3], 1
0x180020690  jz      loc_1800207E2
0x180020696  mov     rcx, rdi; this
0x180020699  call    ?BackupIpConfiguration@CHNetConn@@IEAAJXZ; CHNetConn::BackupIpConfiguration(void)
0x18002069e  mov     ebx, eax
0x1800206a0  test    eax, eax
0x1800206a2  jns     short loc_1800206D2
0x1800206a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206ab  cmp     rcx, rsi
0x1800206ae  jz      loc_1800207E7
0x1800206b4  test    [rcx+1Ch], r13b
0x1800206b8  jz      loc_1800207E7
0x1800206be  cmp     [rcx+19h], r12b
0x1800206c2  jb      loc_1800207E7
0x1800206c8  mov     edx, 8Ah
0x1800206cd  jmp     loc_1800207C1
0x1800206d2  jnz     loc_1800207E7
0x1800206d8  lea     r8, ?c_wszIcsUpgradeEventName@@3QBGB; "IcsUpgradeEventName_"
0x1800206df  xor     edx, edx; bInheritHandle
0x1800206e1  mov     ecx, r12d; dwDesiredAccess
0x1800206e4  call    cs:__imp_OpenEventW
0x1800206ea  test    rax, rax
0x1800206ed  jz      short loc_1800206FA
0x1800206ef  mov     rcx, rax; hObject
0x1800206f2  call    cs:__imp_CloseHandle
0x1800206f8  jmp     short loc_18002073C
0x1800206fa  mov     rcx, rdi; this
0x1800206fd  call    ?SetupConnectionAsPrivateLan@CHNetConn@@IEAAJXZ; CHNetConn::SetupConnectionAsPrivateLan(void)
0x180020702  mov     ebx, eax
0x180020704  test    eax, eax
0x180020706  jns     short loc_180020736
0x180020708  mov     rcx, cs:WPP_GLOBAL_Control
0x18002070f  cmp     rcx, rsi
0x180020712  jz      loc_1800207E7
0x180020718  test    [rcx+1Ch], r13b
0x18002071c  jz      loc_1800207E7
0x180020722  cmp     [rcx+19h], r12b
0x180020726  jb      loc_1800207E7
0x18002072c  mov     edx, 8Bh
0x180020731  jmp     loc_1800207C1
0x180020736  jnz     loc_1800207E7
0x18002073c  mov     rcx, [rbp+var_40]; struct IWbemClassObject *
0x180020740  lea     rdx, ?c_wszIsIcsPrivate@@3QBGB; "IsIcsPrivate"
0x180020747  mov     r8b, 1; unsigned __int8
0x18002074a  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x18002074f  mov     ebx, eax
0x180020751  test    eax, eax
0x180020753  jns     short loc_180020778
0x180020755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002075c  cmp     rcx, rsi
0x18002075f  jz      loc_1800207E7
0x180020765  test    [rcx+1Ch], r13b
0x180020769  jz      short loc_1800207E7
0x18002076b  cmp     [rcx+19h], r12b
0x18002076f  jb      short loc_1800207E7
0x180020771  mov     edx, 8Ch
0x180020776  jmp     short loc_1800207C1
0x180020778  jnz     short loc_1800207E7
0x18002077a  mov     rcx, [rdi+40h]
0x18002077e  xor     r9d, r9d
0x180020781  mov     rdx, [rbp+var_40]
0x180020785  mov     qword ptr [rsp+70h+var_50], 0
0x18002078e  mov     rax, [rcx]
0x180020791  lea     r8d, [r9+1]
0x180020795  mov     rax, [rax+70h]
0x180020799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002079e  mov     ebx, eax
0x1800207a0  test    eax, eax
0x1800207a2  jns     short loc_1800207D6
0x1800207a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207ab  cmp     rcx, rsi
0x1800207ae  jz      short loc_1800207E7
0x1800207b0  test    [rcx+1Ch], r13b
0x1800207b4  jz      short loc_1800207E7
0x1800207b6  cmp     [rcx+19h], r12b
0x1800207ba  jb      short loc_1800207E7
0x1800207bc  mov     edx, 8Dh
0x1800207c1  mov     rcx, [rcx+10h]
0x1800207c5  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x1800207cc  mov     r9d, eax
0x1800207cf  call    WPP_SF_d
0x1800207d4  jmp     short loc_1800207E7
0x1800207d6  jnz     short loc_1800207E7
0x1800207d8  mov     rcx, rdi; this
0x1800207db  call    ?UpdateNetman@CHNetConn@@IEAAJXZ; CHNetConn::UpdateNetman(void)
0x1800207e0  jmp     short loc_1800207E7
0x1800207e2  mov     ebx, 8000FFFFh
0x1800207e7  mov     rcx, [rbp+var_40]
0x1800207eb  mov     rax, [rcx]
0x1800207ee  mov     rax, [rax+10h]
0x1800207f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207f7  test    ebx, ebx
0x1800207f9  jnz     loc_180020463
0x1800207ff  lea     rcx, [rbp+var_30]
0x180020803  mov     qword ptr [rbp+var_30.Data1], 0
0x18002080b  call    ?CreateInstance@?$CComObject@VCHNIcsPrivateConn@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNIcsPrivateConn>::CreateInstance(ATL::CComObject<CHNIcsPrivateConn> * *)
0x180020810  mov     ebx, eax
0x180020812  test    eax, eax
0x180020814  jns     short loc_180020857
0x180020816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002081d  cmp     rcx, rsi
0x180020820  jz      loc_18002052C
0x180020826  test    [rcx+1Ch], r13b
0x18002082a  jz      loc_180020503
0x180020830  cmp     [rcx+19h], r12b
0x180020834  jb      loc_180020503
0x18002083a  mov     rcx, [rcx+10h]
0x18002083e  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
  ... truncated ...
```
