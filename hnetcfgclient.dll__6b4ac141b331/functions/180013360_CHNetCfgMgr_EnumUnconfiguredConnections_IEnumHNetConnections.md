# CHNetCfgMgr::EnumUnconfiguredConnections(IEnumHNetConnections * *)

- ea: `0x180013360`
- end: `0x1800136a1`
- name: `?EnumUnconfiguredConnections@CHNetCfgMgr@@UEAAJPEAPEAUIEnumHNetConnections@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this, struct IEnumHNetConnections **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000f3c0`
- `0x180013360`
- `0x180015b60`
- `0x180028210`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180013541`
- `OLEAUT32!__imp_SysFreeString` at `0x180013541`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::EnumUnconfiguredConnections(CHNetCfgMgr *this, struct IEnumHNetConnections **a2)
{
  PVOID *v4; // rcx
  bool v5; // zf
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  int Instance; // eax
  BSTR v15; // rdi
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)this + 12) == 0;
  v20 = 0;
  bstrString = 0;
  if ( v5 )
  {
    v6 = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 66, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v7 = 67;
LABEL_55:
        WPP_SF_d(v4[2], v7, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v6);
        return v6;
      }
    }
    return v6;
  }
  if ( a2 )
  {
    *a2 = 0;
    v10 = BuildSelectQueryBstr(
            &bstrString,
            (const unsigned __int16 *)a2,
            L"HNet_ConnectionProperties",
            L"IsFirewalled != TRUE AND IsIcsPublic != TRUE AND IsIcsPrivate != TRUE");
    v6 = v10;
    if ( v10 < 0 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v8 = 69;
      v9 = (unsigned int)v10;
      goto LABEL_19;
    }
    if ( v10 )
      goto LABEL_50;
    v11 = *((_QWORD *)this + 12);
    v12 = *((_QWORD *)this + 15);
    v20 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR, __int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 160LL))(
            v11,
            v12,
            bstrString,
            16,
            0,
            &v20);
    v6 = v13;
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v13);
    }
    SysFreeString(bstrString);
    if ( v6 )
      goto LABEL_50;
    bstrString = 0;
    Instance = ATL::CComObject<CHNCEnum<IEnumHNetConnections,IHNetConnection,CHNetConn>>::CreateInstance((volatile int **)&bstrString);
    v6 = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)Instance);
      }
      goto LABEL_49;
    }
    v15 = bstrString;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
    v16 = CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(
            v15,
            *((_QWORD *)this + 12),
            v20);
    v6 = v16;
    if ( v16 >= 0 )
    {
      v16 = (**(__int64 (__fastcall ***)(BSTR, GUID *, struct IEnumHNetConnections **))v15)(
              v15,
              &GUID_e48cb68f_7cf0_496d_b8f7_d2ef8b639e1b,
              a2);
      v6 = v16;
      if ( v16 >= 0 )
        goto LABEL_48;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v18 = 73;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v18 = 72;
    }
    WPP_SF_d(v17[2], v18, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v16);
LABEL_48:
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_49:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_50;
  }
  v6 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)v4 + 28) & 8) == 0 || *((_BYTE *)v4 + 25) < 2u )
    goto LABEL_51;
  v8 = 68;
  v9 = 2147500035LL;
LABEL_19:
  WPP_SF_d(v4[2], v8, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v9);
LABEL_50:
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v7 = 74;
    goto LABEL_55;
  }
  return v6;
}

```

## disassembly

```asm
0x180013360  mov     [rsp+arg_8], rbx
0x180013365  push    rbp
0x180013366  push    rsi
0x180013367  push    rdi
0x180013368  push    r12
0x18001336a  push    r13
0x18001336c  sub     rsp, 40h
0x180013370  mov     rsi, rdx
0x180013373  mov     rbp, rcx
0x180013376  mov     rcx, cs:WPP_GLOBAL_Control
0x18001337d  lea     r12, WPP_GLOBAL_Control
0x180013384  lea     r13, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001338b  cmp     rcx, r12
0x18001338e  jz      short loc_1800133B4
0x180013390  test    byte ptr [rcx+1Ch], 8
0x180013394  jz      short loc_1800133B4
0x180013396  cmp     byte ptr [rcx+19h], 6
0x18001339a  jb      short loc_1800133B4
0x18001339c  mov     rcx, [rcx+10h]
0x1800133a0  mov     edx, 41h ; 'A'
0x1800133a5  mov     r8, r13
0x1800133a8  call    WPP_SF_
0x1800133ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133b4  cmp     qword ptr [rbp+60h], 0
0x1800133b9  mov     [rsp+68h+arg_0], 0
0x1800133c2  mov     [rsp+68h+bstrString], 0
0x1800133ce  jnz     short loc_18001342C
0x1800133d0  mov     ebx, 80004003h
0x1800133d5  cmp     rcx, r12
0x1800133d8  jz      loc_18001368E
0x1800133de  test    byte ptr [rcx+1Ch], 8
0x1800133e2  jz      short loc_180013405
0x1800133e4  cmp     byte ptr [rcx+19h], 2
0x1800133e8  jb      short loc_180013405
0x1800133ea  mov     rcx, [rcx+10h]
0x1800133ee  mov     edx, 42h ; 'B'
0x1800133f3  mov     r9d, ebx
0x1800133f6  mov     r8, r13
0x1800133f9  call    WPP_SF_d
0x1800133fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180013405  cmp     rcx, r12
0x180013408  jz      loc_18001368E
0x18001340e  test    byte ptr [rcx+1Ch], 8
0x180013412  jz      loc_18001368E
0x180013418  cmp     byte ptr [rcx+19h], 6
0x18001341c  jb      loc_18001368E
0x180013422  mov     edx, 43h ; 'C'
0x180013427  jmp     loc_18001367F
0x18001342c  test    rsi, rsi
0x18001342f  jnz     short loc_18001346A
0x180013431  mov     ebx, 80004003h
0x180013436  cmp     rcx, r12
0x180013439  jz      loc_18001368E
0x18001343f  test    byte ptr [rcx+1Ch], 8
0x180013443  jz      loc_180013669
0x180013449  cmp     byte ptr [rcx+19h], 2
0x18001344d  jb      loc_180013669
0x180013453  lea     edx, [rsi+44h]
0x180013456  mov     r9d, ebx
0x180013459  mov     rcx, [rcx+10h]
0x18001345d  mov     r8, r13
0x180013460  call    WPP_SF_d
0x180013465  jmp     loc_180013662
0x18001346a  lea     r9, aIsfirewalledTr; "IsFirewalled != TRUE AND IsIcsPublic !="...
0x180013471  mov     qword ptr [rsi], 0
0x180013478  lea     r8, ?c_wszHnetProperties@@3QBGB; "HNet_ConnectionProperties"
0x18001347f  lea     rcx, [rsp+68h+bstrString]; unsigned __int16 **
0x180013487  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x18001348c  mov     ebx, eax
0x18001348e  test    eax, eax
0x180013490  jns     short loc_1800134C0
0x180013492  mov     rcx, cs:WPP_GLOBAL_Control
0x180013499  cmp     rcx, r12
0x18001349c  jz      loc_18001368E
0x1800134a2  test    byte ptr [rcx+1Ch], 8
0x1800134a6  jz      loc_180013669
0x1800134ac  cmp     byte ptr [rcx+19h], 2
0x1800134b0  jb      loc_180013669
0x1800134b6  mov     edx, 45h ; 'E'
0x1800134bb  mov     r9d, eax
0x1800134be  jmp     short loc_180013459
0x1800134c0  jnz     loc_180013662
0x1800134c6  mov     rcx, [rbp+60h]
0x1800134ca  lea     rdx, [rsp+68h+arg_0]
0x1800134cf  mov     r8, [rsp+68h+bstrString]
0x1800134d7  mov     r9d, 10h
0x1800134dd  mov     [rsp+68h+var_40], rdx
0x1800134e2  mov     rdx, [rbp+78h]
0x1800134e6  mov     [rsp+68h+arg_0], 0
0x1800134ef  mov     rax, [rcx]
0x1800134f2  mov     [rsp+68h+var_48], 0
0x1800134fb  mov     rax, [rax+0A0h]
0x180013502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013507  mov     ebx, eax
0x180013509  test    eax, eax
0x18001350b  jns     short loc_180013539
0x18001350d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013514  cmp     rcx, r12
0x180013517  jz      short loc_180013539
0x180013519  test    byte ptr [rcx+1Ch], 8
0x18001351d  jz      short loc_180013539
0x18001351f  cmp     byte ptr [rcx+19h], 2
0x180013523  jb      short loc_180013539
0x180013525  mov     rcx, [rcx+10h]
0x180013529  mov     edx, 46h ; 'F'
0x18001352e  mov     r9d, eax
0x180013531  mov     r8, r13
0x180013534  call    WPP_SF_d
0x180013539  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180013541  call    cs:__imp_SysFreeString
0x180013547  test    ebx, ebx
0x180013549  jnz     loc_180013662
0x18001354f  lea     rcx, [rsp+68h+bstrString]
0x180013557  mov     [rsp+68h+bstrString], 0
0x180013563  call    ?CreateInstance@?$CComObject@V?$CHNCEnum@UIEnumHNetConnections@@UIHNetConnection@@VCHNetConn@@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNCEnum<IEnumHNetConnections,IHNetConnection,CHNetConn>>::CreateInstance(ATL::CComObject<CHNCEnum<IEnumHNetConnections,IHNetConnection,CHNetConn>> * *)
0x180013568  mov     ebx, eax
0x18001356a  test    eax, eax
0x18001356c  jns     short loc_1800135AB
0x18001356e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013575  cmp     rcx, r12
0x180013578  jz      loc_180013651
0x18001357e  test    byte ptr [rcx+1Ch], 8
0x180013582  jz      loc_180013651
0x180013588  cmp     byte ptr [rcx+19h], 2
0x18001358c  jb      loc_180013651
0x180013592  mov     rcx, [rcx+10h]
0x180013596  mov     edx, 47h ; 'G'
0x18001359b  mov     r9d, eax
0x18001359e  mov     r8, r13
0x1800135a1  call    WPP_SF_d
0x1800135a6  jmp     loc_180013651
0x1800135ab  mov     rdi, [rsp+68h+bstrString]
0x1800135b3  mov     rcx, rdi
0x1800135b6  mov     rax, [rdi]
0x1800135b9  mov     rax, [rax+8]
0x1800135bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135c2  mov     r8, [rsp+68h+arg_0]
0x1800135c7  mov     rcx, rdi
0x1800135ca  mov     rdx, [rbp+60h]
0x1800135ce  call    ?Initialize@?$CHNCEnum@UIEnumHNetPortMappingBindings@@UIHNetPortMappingBinding@@VCHNetPortMappingBinding@@@@QEAAJPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(IWbemServices *,IEnumWbemClassObject *)
0x1800135d3  mov     ebx, eax
0x1800135d5  test    eax, eax
0x1800135d7  jns     short loc_1800135F8
0x1800135d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135e0  cmp     rcx, r12
0x1800135e3  jz      short loc_180013642
0x1800135e5  test    byte ptr [rcx+1Ch], 8
0x1800135e9  jz      short loc_180013642
0x1800135eb  cmp     byte ptr [rcx+19h], 2
0x1800135ef  jb      short loc_180013642
0x1800135f1  mov     edx, 48h ; 'H'
0x1800135f6  jmp     short loc_180013633
0x1800135f8  mov     rax, [rdi]
0x1800135fb  lea     rdx, _GUID_e48cb68f_7cf0_496d_b8f7_d2ef8b639e1b
0x180013602  mov     r8, rsi
0x180013605  mov     rcx, rdi
0x180013608  mov     rax, [rax]
0x18001360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013610  mov     ebx, eax
0x180013612  test    eax, eax
0x180013614  jns     short loc_180013642
0x180013616  mov     rcx, cs:WPP_GLOBAL_Control
0x18001361d  cmp     rcx, r12
0x180013620  jz      short loc_180013642
0x180013622  test    byte ptr [rcx+1Ch], 8
0x180013626  jz      short loc_180013642
0x180013628  cmp     byte ptr [rcx+19h], 2
0x18001362c  jb      short loc_180013642
0x18001362e  mov     edx, 49h ; 'I'
0x180013633  mov     rcx, [rcx+10h]
0x180013637  mov     r9d, eax
0x18001363a  mov     r8, r13
0x18001363d  call    WPP_SF_d
0x180013642  mov     rax, [rdi]
0x180013645  mov     rcx, rdi
0x180013648  mov     rax, [rax+10h]
0x18001364c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013651  mov     rcx, [rsp+68h+arg_0]
0x180013656  mov     rax, [rcx]
0x180013659  mov     rax, [rax+10h]
0x18001365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013662  mov     rcx, cs:WPP_GLOBAL_Control
0x180013669  cmp     rcx, r12
0x18001366c  jz      short loc_18001368E
0x18001366e  test    byte ptr [rcx+1Ch], 8
0x180013672  jz      short loc_18001368E
0x180013674  cmp     byte ptr [rcx+19h], 6
0x180013678  jb      short loc_18001368E
0x18001367a  mov     edx, 4Ah ; 'J'
0x18001367f  mov     rcx, [rcx+10h]
0x180013683  mov     r9d, ebx
0x180013686  mov     r8, r13
0x180013689  call    WPP_SF_d
0x18001368e  mov     eax, ebx
0x180013690  mov     rbx, [rsp+68h+arg_8]
0x180013695  add     rsp, 40h
0x180013699  pop     r13
0x18001369b  pop     r12
0x18001369d  pop     rdi
0x18001369e  pop     rsi
0x18001369f  pop     rbp
0x1800136a0  retn
```
