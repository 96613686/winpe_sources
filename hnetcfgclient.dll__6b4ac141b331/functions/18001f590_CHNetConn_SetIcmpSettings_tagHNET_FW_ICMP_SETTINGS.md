# CHNetConn::SetIcmpSettings(tagHNET_FW_ICMP_SETTINGS *)

- ea: `0x18001f590`
- end: `0x18001fb82`
- name: `?SetIcmpSettings@CHNetConn@@UEAAJPEAUtagHNET_FW_ICMP_SETTINGS@@@Z`
- size: `1522`
- prototype: `__int64 __fastcall(struct IWbemServices **this, struct tagHNET_FW_ICMP_SETTINGS *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180018ff4`
- `0x180019318`
- `0x18001c61c`
- `0x18001f590`
- `0x180027fc4`
- `0x180028210`
- `0x180028c48`
- `0x18002a7d4`
- `0x18002ac5c`
- `0x18002ae64`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa04`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001fa04`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f933`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb77`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f933`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb77`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7d1`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7d1`

## pseudocode

```c
__int64 __fastcall CHNetConn::SetIcmpSettings(struct IWbemServices **this, struct tagHNET_FW_ICMP_SETTINGS *a2)
{
  CHNetConn *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  int IcmpSettingsInstance; // eax
  int v9; // eax
  BSTR bstrVal; // rax
  char v12; // di
  int v13; // ecx
  int v14; // r8d
  bool v15; // zf
  struct IWbemServices *v16; // rcx
  int v17; // eax
  const unsigned __int16 *v18; // r8
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  int v22; // ebx
  struct IWbemServices *v23; // rcx
  struct IWbemServices *v24; // rdx
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  int IcmpSettingsAssociation; // eax
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  BSTR v31; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v33; // [rsp+B8h] [rbp+48h] BYREF
  struct IWbemClassObject *v34; // [rsp+C0h] [rbp+50h] BYREF
  struct IEnumWbemClassObject *v35; // [rsp+C8h] [rbp+58h] BYREF

  v4 = (CHNetConn *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (CHNetConn *)WPP_GLOBAL_Control;
  }
  v35 = 0;
  v34 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( a2 )
  {
    IcmpSettingsInstance = CHNetConn::GetIcmpSettingsInstance((CHNetConn *)this, &v34);
    v5 = IcmpSettingsInstance;
    if ( IcmpSettingsInstance < 0 )
    {
      v4 = (CHNetConn *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 177;
LABEL_16:
        v7 = (unsigned int)IcmpSettingsInstance;
        goto LABEL_10;
      }
LABEL_28:
      if ( v34 )
      {
        ((void (__fastcall *)(struct IWbemClassObject *))v34->lpVtbl->Release)(v34);
        v4 = (CHNetConn *)WPP_GLOBAL_Control;
      }
      goto LABEL_30;
    }
    if ( !IcmpSettingsInstance )
    {
      v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v34->lpVtbl->Get)(
             v34,
             L"Name",
             0,
             &pvarg,
             0,
             0);
      v5 = v9;
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            178,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v9);
        }
        goto LABEL_23;
      }
      if ( v9 )
      {
LABEL_23:
        ((void (__fastcall *)(struct IWbemClassObject *))v34->lpVtbl->Release)(v34);
        v34 = 0;
LABEL_24:
        v4 = (CHNetConn *)WPP_GLOBAL_Control;
LABEL_25:
        if ( (v5 & 0x80000000) != 0 )
          goto LABEL_28;
        goto LABEL_26;
      }
      bstrVal = pvarg.bstrVal;
      v12 = 0;
      do
      {
        v13 = *(unsigned __int16 *)((char *)L"Default" + (_QWORD)bstrVal - pvarg.llVal);
        v14 = *bstrVal - v13;
        if ( v14 )
          break;
        ++bstrVal;
      }
      while ( v13 );
      if ( !v14 )
      {
        v12 = 1;
        ((void (__fastcall *)(struct IWbemClassObject *))v34->lpVtbl->Release)(v34);
        v34 = 0;
      }
      VariantClear(&pvarg);
      if ( v12 == 1 )
      {
        IcmpSettingsInstance = SpawnNewInstance(this[8], L"HNet_FwIcmpSettings", &v34);
        v4 = (CHNetConn *)WPP_GLOBAL_Control;
        v5 = IcmpSettingsInstance;
        v15 = IcmpSettingsInstance == 0;
        if ( IcmpSettingsInstance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = 179;
            goto LABEL_16;
          }
          v15 = IcmpSettingsInstance == 0;
        }
        if ( !v15 )
          goto LABEL_25;
      }
      IcmpSettingsInstance = CHNetConn::CopyStructToIcmpSettingsInstance(v4, a2, v34);
      v5 = IcmpSettingsInstance;
      if ( IcmpSettingsInstance < 0 )
      {
        v4 = (CHNetConn *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 180;
          goto LABEL_16;
        }
        goto LABEL_28;
      }
      if ( !IcmpSettingsInstance )
      {
        v16 = this[8];
        v33 = 0;
        IcmpSettingsInstance = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemClassObject *, __int64))v16->lpVtbl->PutInstance)(
                                 v16,
                                 v34,
                                 16);
        v5 = IcmpSettingsInstance;
        if ( IcmpSettingsInstance < 0 )
        {
          v4 = (CHNetConn *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = 181;
            goto LABEL_16;
          }
          goto LABEL_28;
        }
        if ( !IcmpSettingsInstance )
        {
          v17 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, BSTR *))(*(_QWORD *)v33 + 32LL))(
                  v33,
                  0xFFFFFFFFLL,
                  &bstrString);
          v5 = v17;
          if ( v17 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              182,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)v17);
          }
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v33 + 16LL))(v33);
          if ( !v12 )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( v5 )
            goto LABEL_24;
          if ( v12 == 1 )
          {
            v18 = (const unsigned __int16 *)this[9];
            v31 = 0;
            v33 = 0;
            v19 = BuildEscapedQuotedEqualsString(&v33, L"Connection", v18);
            if ( v19 >= 0 )
            {
              if ( !v19 )
              {
                v21 = BuildSelectQueryBstr(&v31, v20, L"HNet_ConnectionIcmpSetting", v33);
                v22 = v21;
                if ( v21 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    184,
                    WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                    (unsigned int)v21);
                }
                operator delete[](v33);
                if ( !v22 )
                {
                  v23 = this[8];
                  v24 = this[15];
                  v35 = 0;
                  v25 = ((__int64 (__fastcall *)(struct IWbemServices *, struct IWbemServices *, BSTR, __int64, _QWORD, struct IEnumWbemClassObject **))v23->lpVtbl->ExecQuery)(
                          v23,
                          v24,
                          v31,
                          48,
                          0,
                          &v35);
                  v26 = v25;
                  if ( v25 < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      185,
                      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                      (unsigned int)v25);
                  }
                  SysFreeString(v31);
                  if ( !v26 )
                  {
                    LODWORD(v33) = 0;
                    v31 = 0;
                    v27 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, BSTR *, unsigned __int16 **))v35->lpVtbl->Next)(
                            v35,
                            0xFFFFFFFFLL,
                            1,
                            &v31,
                            &v33);
                    v28 = v27;
                    if ( v27 < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        186,
                        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                        (unsigned int)v27);
                    }
                    ValidateFinishedWCOEnum(this[8], v35);
                    ((void (__fastcall *)(struct IEnumWbemClassObject *))v35->lpVtbl->Release)(v35);
                    if ( v28 >= 0 && (_DWORD)v33 == 1 )
                    {
                      DeleteWmiInstance(this[8], (struct IWbemClassObject *)v31);
                      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                  }
                }
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                183,
                WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                (unsigned int)v19);
            }
            IcmpSettingsAssociation = CHNetConn::CreateIcmpSettingsAssociation((CHNetConn *)this, bstrString);
            v5 = IcmpSettingsAssociation;
            if ( IcmpSettingsAssociation < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                187,
                WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                (unsigned int)IcmpSettingsAssociation);
            }
            SysFreeString(bstrString);
            goto LABEL_24;
          }
        }
      }
    }
LABEL_26:
    UpdateService(0x81u);
    goto LABEL_27;
  }
  v5 = -2147024809;
  if ( v4 == (CHNetConn *)&WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v6 = 176;
    v7 = 2147942487LL;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v4 + 2), v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
LABEL_27:
    v4 = (CHNetConn *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
LABEL_30:
  if ( v4 != (CHNetConn *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v4 + 2), 188, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001f590  mov     [rsp-38h+arg_0], rbx
0x18001f595  push    rbp
0x18001f596  push    rsi
0x18001f597  push    rdi
0x18001f598  push    r12
0x18001f59a  push    r13
0x18001f59c  push    r14
0x18001f59e  push    r15
0x18001f5a0  mov     rbp, rsp
0x18001f5a3  sub     rsp, 70h
0x18001f5a7  mov     r14, rdx
0x18001f5aa  mov     rsi, rcx
0x18001f5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5b4  lea     r13, WPP_GLOBAL_Control
0x18001f5bb  mov     r12b, 8
0x18001f5be  cmp     rcx, r13
0x18001f5c1  jz      short loc_18001F5EB
0x18001f5c3  test    [rcx+1Ch], r12b
0x18001f5c7  jz      short loc_18001F5EB
0x18001f5c9  cmp     byte ptr [rcx+19h], 6
0x18001f5cd  jb      short loc_18001F5EB
0x18001f5cf  mov     rcx, [rcx+10h]
0x18001f5d3  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f5da  mov     edx, 0AFh
0x18001f5df  call    WPP_SF_
0x18001f5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5eb  xor     r15d, r15d
0x18001f5ee  xor     eax, eax
0x18001f5f0  mov     qword ptr [rbp+pvarg+10h], rax
0x18001f5f4  xorps   xmm0, xmm0
0x18001f5f7  mov     [rbp+arg_18], r15
0x18001f5fb  mov     [rbp+arg_10], r15
0x18001f5ff  mov     [rbp+bstrString], r15
0x18001f603  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001f607  test    r14, r14
0x18001f60a  jnz     short loc_18001F64B
0x18001f60c  mov     ebx, 80070057h
0x18001f611  cmp     rcx, r13
0x18001f614  jz      loc_18001F76B
0x18001f61a  test    [rcx+1Ch], r12b
0x18001f61e  jz      loc_18001F742
0x18001f624  cmp     byte ptr [rcx+19h], 2
0x18001f628  jb      loc_18001F742
0x18001f62e  mov     edx, 0B0h
0x18001f633  mov     r9d, ebx
0x18001f636  mov     rcx, [rcx+10h]
0x18001f63a  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f641  call    WPP_SF_d
0x18001f646  jmp     loc_18001F71C
0x18001f64b  lea     rdx, [rbp+arg_10]; struct IWbemClassObject **
0x18001f64f  mov     rcx, rsi; this
0x18001f652  call    ?GetIcmpSettingsInstance@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetIcmpSettingsInstance(IWbemClassObject * *)
0x18001f657  mov     ebx, eax
0x18001f659  test    eax, eax
0x18001f65b  jns     short loc_18001F68B
0x18001f65d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f664  cmp     rcx, r13
0x18001f667  jz      loc_18001F723
0x18001f66d  test    [rcx+1Ch], r12b
0x18001f671  jz      loc_18001F723
0x18001f677  cmp     byte ptr [rcx+19h], 2
0x18001f67b  jb      loc_18001F723
0x18001f681  mov     edx, 0B1h
0x18001f686  mov     r9d, eax
0x18001f689  jmp     short loc_18001F636
0x18001f68b  jnz     loc_18001F712
0x18001f691  mov     rcx, [rbp+arg_10]
0x18001f695  lea     r9, [rbp+pvarg]
0x18001f699  mov     [rsp+70h+var_48], r15
0x18001f69e  lea     rdx, ?c_wszName@@3QBGB; "Name"
0x18001f6a5  xor     r8d, r8d
0x18001f6a8  mov     [rsp+70h+var_50], r15
0x18001f6ad  mov     rax, [rcx]
0x18001f6b0  mov     rax, [rax+20h]
0x18001f6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6b9  mov     ebx, eax
0x18001f6bb  test    eax, eax
0x18001f6bd  jns     loc_18001F785
0x18001f6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6ca  cmp     rcx, r13
0x18001f6cd  jz      short loc_18001F6F3
0x18001f6cf  test    [rcx+1Ch], r12b
0x18001f6d3  jz      short loc_18001F6F3
0x18001f6d5  cmp     byte ptr [rcx+19h], 2
0x18001f6d9  jb      short loc_18001F6F3
0x18001f6db  mov     rcx, [rcx+10h]
0x18001f6df  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f6e6  mov     edx, 0B2h
0x18001f6eb  mov     r9d, eax
0x18001f6ee  call    WPP_SF_d
0x18001f6f3  mov     rcx, [rbp+arg_10]
0x18001f6f7  mov     rax, [rcx]
0x18001f6fa  mov     rax, [rax+10h]
0x18001f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f703  mov     [rbp+arg_10], r15
0x18001f707  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f70e  test    ebx, ebx
0x18001f710  js      short loc_18001F723
0x18001f712  mov     ecx, 81h; dwControl
0x18001f717  call    ?UpdateService@@YAXK@Z; UpdateService(ulong)
0x18001f71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f723  mov     rdx, [rbp+arg_10]
0x18001f727  test    rdx, rdx
0x18001f72a  jz      short loc_18001F742
0x18001f72c  mov     rax, [rdx]
0x18001f72f  mov     rcx, rdx
0x18001f732  mov     rax, [rax+10h]
0x18001f736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f73b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f742  cmp     rcx, r13
0x18001f745  jz      short loc_18001F76B
0x18001f747  test    [rcx+1Ch], r12b
0x18001f74b  jz      short loc_18001F76B
0x18001f74d  cmp     byte ptr [rcx+19h], 6
0x18001f751  jb      short loc_18001F76B
0x18001f753  mov     rcx, [rcx+10h]
0x18001f757  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f75e  mov     edx, 0BCh
0x18001f763  mov     r9d, ebx
0x18001f766  call    WPP_SF_d
0x18001f76b  mov     eax, ebx
0x18001f76d  mov     rbx, [rsp+70h+arg_0]
0x18001f775  add     rsp, 70h
0x18001f779  pop     r15
0x18001f77b  pop     r14
0x18001f77d  pop     r13
0x18001f77f  pop     r12
0x18001f781  pop     rdi
0x18001f782  pop     rsi
0x18001f783  pop     rbp
0x18001f784  retn
0x18001f785  jnz     loc_18001F6F3
0x18001f78b  mov     rax, qword ptr [rbp+pvarg+8]
0x18001f78f  lea     rdx, ?c_wszDefault@@3QBGB; "Default"
0x18001f796  sub     rdx, rax
0x18001f799  mov     dil, r15b
0x18001f79c  movzx   r8d, word ptr [rax]
0x18001f7a0  movzx   ecx, word ptr [rax+rdx]
0x18001f7a4  sub     r8d, ecx
0x18001f7a7  jnz     short loc_18001F7B1
0x18001f7a9  add     rax, 2
0x18001f7ad  test    ecx, ecx
0x18001f7af  jnz     short loc_18001F79C
0x18001f7b1  test    r8d, r8d
0x18001f7b4  jnz     short loc_18001F7CD
0x18001f7b6  mov     rcx, [rbp+arg_10]
0x18001f7ba  mov     dil, 1
0x18001f7bd  mov     rax, [rcx]
0x18001f7c0  mov     rax, [rax+10h]
0x18001f7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7c9  mov     [rbp+arg_10], r15
0x18001f7cd  lea     rcx, [rbp+pvarg]; pvarg
0x18001f7d1  call    cs:__imp_VariantClear
0x18001f7d7  cmp     dil, 1
0x18001f7db  jnz     short loc_18001F821
0x18001f7dd  mov     rcx, [rsi+40h]; struct IWbemServices *
0x18001f7e1  lea     r8, [rbp+arg_10]; struct IWbemClassObject **
0x18001f7e5  lea     rdx, ?c_wszHnetFwIcmpSettings@@3QBGB; "HNet_FwIcmpSettings"
0x18001f7ec  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x18001f7f1  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18001f7f8  mov     ebx, eax
0x18001f7fa  test    eax, eax
0x18001f7fc  jns     short loc_18001F81B
0x18001f7fe  cmp     rcx, r13
0x18001f801  jz      short loc_18001F819
0x18001f803  test    [rcx+1Ch], r12b
0x18001f807  jz      short loc_18001F819
0x18001f809  cmp     byte ptr [rcx+19h], 2
0x18001f80d  jb      short loc_18001F819
0x18001f80f  mov     edx, 0B3h
0x18001f814  jmp     loc_18001F686
0x18001f819  test    eax, eax
0x18001f81b  jnz     loc_18001F70E
0x18001f821  mov     r8, [rbp+arg_10]; struct IWbemClassObject *
0x18001f825  mov     rdx, r14; struct tagHNET_FW_ICMP_SETTINGS *
0x18001f828  call    ?CopyStructToIcmpSettingsInstance@CHNetConn@@IEAAJPEAUtagHNET_FW_ICMP_SETTINGS@@PEAUIWbemClassObject@@@Z; CHNetConn::CopyStructToIcmpSettingsInstance(tagHNET_FW_ICMP_SETTINGS *,IWbemClassObject *)
0x18001f82d  mov     ebx, eax
0x18001f82f  test    eax, eax
0x18001f831  jns     short loc_18001F861
0x18001f833  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f83a  cmp     rcx, r13
0x18001f83d  jz      loc_18001F723
0x18001f843  test    [rcx+1Ch], r12b
0x18001f847  jz      loc_18001F723
0x18001f84d  cmp     byte ptr [rcx+19h], 2
0x18001f851  jb      loc_18001F723
0x18001f857  mov     edx, 0B4h
0x18001f85c  jmp     loc_18001F686
0x18001f861  jnz     loc_18001F712
0x18001f867  mov     rcx, [rsi+40h]
0x18001f86b  lea     rdx, [rbp+arg_8]
0x18001f86f  mov     [rbp+arg_8], r15
0x18001f873  xor     r9d, r9d
0x18001f876  mov     [rsp+70h+var_50], rdx
0x18001f87b  mov     rdx, [rbp+arg_10]
0x18001f87f  mov     rax, [rcx]
0x18001f882  lea     r8d, [r9+10h]
0x18001f886  mov     rax, [rax+70h]
0x18001f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f88f  mov     ebx, eax
0x18001f891  test    eax, eax
0x18001f893  jns     short loc_18001F8C3
0x18001f895  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f89c  cmp     rcx, r13
0x18001f89f  jz      loc_18001F723
0x18001f8a5  test    [rcx+1Ch], r12b
0x18001f8a9  jz      loc_18001F723
0x18001f8af  cmp     byte ptr [rcx+19h], 2
0x18001f8b3  jb      loc_18001F723
0x18001f8b9  mov     edx, 0B5h
0x18001f8be  jmp     loc_18001F686
0x18001f8c3  jnz     loc_18001F712
0x18001f8c9  mov     rcx, [rbp+arg_8]
0x18001f8cd  lea     r8, [rbp+bstrString]
0x18001f8d1  or      r14d, 0FFFFFFFFh
0x18001f8d5  mov     edx, r14d
0x18001f8d8  mov     rax, [rcx]
0x18001f8db  mov     rax, [rax+20h]
0x18001f8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8e4  mov     ebx, eax
0x18001f8e6  test    eax, eax
0x18001f8e8  jns     short loc_18001F91A
0x18001f8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8f1  cmp     rcx, r13
0x18001f8f4  jz      short loc_18001F91A
0x18001f8f6  test    [rcx+1Ch], r12b
0x18001f8fa  jz      short loc_18001F91A
0x18001f8fc  cmp     byte ptr [rcx+19h], 2
0x18001f900  jb      short loc_18001F91A
0x18001f902  mov     rcx, [rcx+10h]
0x18001f906  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f90d  mov     edx, 0B6h
0x18001f912  mov     r9d, eax
0x18001f915  call    WPP_SF_d
0x18001f91a  mov     rcx, [rbp+arg_8]
0x18001f91e  mov     rax, [rcx]
0x18001f921  mov     rax, [rax+10h]
0x18001f925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f92a  test    dil, dil
0x18001f92d  jnz     short loc_18001F93D
0x18001f92f  mov     rcx, [rbp+bstrString]; bstrString
0x18001f933  call    cs:__imp_SysFreeString
0x18001f939  mov     [rbp+bstrString], r15
0x18001f93d  test    ebx, ebx
0x18001f93f  jnz     loc_18001F707
0x18001f945  cmp     dil, 1
0x18001f949  jnz     loc_18001F712
0x18001f94f  mov     r8, [rsi+48h]; unsigned __int16 *
0x18001f953  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x18001f95a  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x18001f95e  mov     [rbp+var_28], r15
0x18001f962  mov     [rbp+arg_8], r15
0x18001f966  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x18001f96b  test    eax, eax
0x18001f96d  jns     short loc_18001F9B0
0x18001f96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f976  cmp     rcx, r13
0x18001f979  jz      loc_18001FB31
0x18001f97f  test    [rcx+1Ch], r12b
0x18001f983  jz      loc_18001FB31
0x18001f989  cmp     byte ptr [rcx+19h], 2
0x18001f98d  jb      loc_18001FB31
0x18001f993  mov     rcx, [rcx+10h]
0x18001f997  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f99e  mov     edx, 0B7h
0x18001f9a3  mov     r9d, eax
0x18001f9a6  call    WPP_SF_d
0x18001f9ab  jmp     loc_18001FB31
0x18001f9b0  jnz     loc_18001FB31
0x18001f9b6  mov     r9, [rbp+arg_8]; unsigned __int16 *
0x18001f9ba  lea     r8, ?c_wszHnetConnectionIcmpSetting@@3QBGB; "HNet_ConnectionIcmpSetting"
0x18001f9c1  lea     rcx, [rbp+var_28]; unsigned __int16 **
0x18001f9c5  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x18001f9ca  mov     ebx, eax
0x18001f9cc  test    eax, eax
0x18001f9ce  jns     short loc_18001FA00
0x18001f9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9d7  cmp     rcx, r13
0x18001f9da  jz      short loc_18001FA00
0x18001f9dc  test    [rcx+1Ch], r12b
0x18001f9e0  jz      short loc_18001FA00
0x18001f9e2  cmp     byte ptr [rcx+19h], 2
0x18001f9e6  jb      short loc_18001FA00
0x18001f9e8  mov     rcx, [rcx+10h]
0x18001f9ec  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001f9f3  mov     edx, 0B8h
0x18001f9f8  mov     r9d, eax
0x18001f9fb  call    WPP_SF_d
0x18001fa00  mov     rcx, [rbp+arg_8]
0x18001fa04  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001fa0a  test    ebx, ebx
0x18001fa0c  jnz     loc_18001FB31
0x18001fa12  mov     rcx, [rsi+40h]
0x18001fa16  lea     rdx, [rbp+arg_18]
0x18001fa1a  mov     r8, [rbp+var_28]
0x18001fa1e  lea     r9d, [rbx+30h]
0x18001fa22  mov     [rsp+70h+var_48], rdx
0x18001fa27  mov     rdx, [rsi+78h]
0x18001fa2b  mov     [rbp+arg_18], r15
0x18001fa2f  mov     rax, [rcx]
  ... truncated ...
```
