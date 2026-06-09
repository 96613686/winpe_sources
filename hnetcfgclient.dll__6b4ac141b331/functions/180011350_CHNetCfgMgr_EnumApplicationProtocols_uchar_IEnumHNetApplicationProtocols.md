# CHNetCfgMgr::EnumApplicationProtocols(uchar,IEnumHNetApplicationProtocols * *)

- ea: `0x180011350`
- end: `0x18001169d`
- name: `?EnumApplicationProtocols@CHNetCfgMgr@@UEAAJEPEAPEAUIEnumHNetApplicationProtocols@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, const unsigned __int16 *, struct IEnumHNetApplicationProtocols **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000f2b0`
- `0x180011350`
- `0x180015b60`
- `0x180028210`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001153d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001153d`

## string_xrefs

- `0x18001146e`: `HNet_ApplicationProtocol`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::EnumApplicationProtocols(
        CHNetCfgMgr *this,
        const unsigned __int16 *a2,
        struct IEnumHNetApplicationProtocols **a3)
{
  char v4; // bl
  PVOID *v6; // rcx
  bool v7; // zf
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int Instance; // eax
  BSTR v17; // rdi
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  v4 = (char)a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 8) == 0;
  v22 = 0;
  bstrString = 0;
  if ( v7 )
  {
    v8 = -2147467261;
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      {
        WPP_SF_d(v6[2], 233, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
      {
        v9 = 234;
LABEL_55:
        WPP_SF_d(v6[2], v9, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v8);
        return v8;
      }
    }
    return v8;
  }
  if ( a3 )
  {
    *a3 = 0;
    v12 = BuildSelectQueryBstr(
            &bstrString,
            a2,
            L"HNet_ApplicationProtocol",
            (const unsigned __int16 *)((unsigned __int64)L"Enabled != FALSE" & -(__int64)(v4 != 0)));
    v8 = v12;
    if ( v12 < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_51;
      v10 = 236;
      v11 = (unsigned int)v12;
      goto LABEL_19;
    }
    if ( v12 )
      goto LABEL_50;
    v13 = *((_QWORD *)this + 8);
    v14 = *((_QWORD *)this + 11);
    v22 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR, __int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 160LL))(
            v13,
            v14,
            bstrString,
            16,
            0,
            &v22);
    v8 = v15;
    if ( v15 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        237,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v15);
    }
    SysFreeString(bstrString);
    if ( v8 )
      goto LABEL_50;
    bstrString = 0;
    Instance = ATL::CComObject<CHNCEnum<IEnumHNetApplicationProtocols,IHNetApplicationProtocol,CHNetAppProtocol>>::CreateInstance((volatile int **)&bstrString);
    v8 = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          238,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)Instance);
      }
      goto LABEL_49;
    }
    v17 = bstrString;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
    v18 = CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(
            v17,
            *((_QWORD *)this + 8),
            v22);
    v8 = v18;
    if ( v18 >= 0 )
    {
      v18 = (**(__int64 (__fastcall ***)(BSTR, GUID *, struct IEnumHNetApplicationProtocols **))v17)(
              v17,
              &GUID_85d18b7b_3032_11d4_9348_00c04f8eeb71,
              a3);
      v8 = v18;
      if ( v18 >= 0 )
        goto LABEL_48;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v20 = 240;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_48;
      }
      v20 = 239;
    }
    WPP_SF_d(v19[2], v20, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v18);
LABEL_48:
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_49:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_50;
  }
  v8 = -2147467261;
  if ( v6 == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)v6 + 28) & 8) == 0 || *((_BYTE *)v6 + 25) < 2u )
    goto LABEL_51;
  v10 = 235;
  v11 = 2147500035LL;
LABEL_19:
  WPP_SF_d(v6[2], v10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v11);
LABEL_50:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_51:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v9 = 241;
    goto LABEL_55;
  }
  return v8;
}

```

## disassembly

```asm
0x180011350  mov     [rsp+arg_8], rbx
0x180011355  push    rbp
0x180011356  push    rsi
0x180011357  push    rdi
0x180011358  push    r12
0x18001135a  push    r13
0x18001135c  sub     rsp, 40h
0x180011360  mov     rsi, r8
0x180011363  mov     bl, dl
0x180011365  mov     rbp, rcx
0x180011368  mov     rcx, cs:WPP_GLOBAL_Control
0x18001136f  lea     r12, WPP_GLOBAL_Control
0x180011376  lea     r13, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001137d  cmp     rcx, r12
0x180011380  jz      short loc_1800113A6
0x180011382  test    byte ptr [rcx+1Ch], 8
0x180011386  jz      short loc_1800113A6
0x180011388  cmp     byte ptr [rcx+19h], 6
0x18001138c  jb      short loc_1800113A6
0x18001138e  mov     rcx, [rcx+10h]
0x180011392  mov     edx, 0E8h
0x180011397  mov     r8, r13
0x18001139a  call    WPP_SF_
0x18001139f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113a6  cmp     qword ptr [rbp+40h], 0
0x1800113ab  mov     [rsp+68h+arg_0], 0
0x1800113b4  mov     [rsp+68h+bstrString], 0
0x1800113c0  jnz     short loc_18001141E
0x1800113c2  mov     ebx, 80004003h
0x1800113c7  cmp     rcx, r12
0x1800113ca  jz      loc_18001168A
0x1800113d0  test    byte ptr [rcx+1Ch], 8
0x1800113d4  jz      short loc_1800113F7
0x1800113d6  cmp     byte ptr [rcx+19h], 2
0x1800113da  jb      short loc_1800113F7
0x1800113dc  mov     rcx, [rcx+10h]
0x1800113e0  mov     edx, 0E9h
0x1800113e5  mov     r9d, ebx
0x1800113e8  mov     r8, r13
0x1800113eb  call    WPP_SF_d
0x1800113f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113f7  cmp     rcx, r12
0x1800113fa  jz      loc_18001168A
0x180011400  test    byte ptr [rcx+1Ch], 8
0x180011404  jz      loc_18001168A
0x18001140a  cmp     byte ptr [rcx+19h], 6
0x18001140e  jb      loc_18001168A
0x180011414  mov     edx, 0EAh
0x180011419  jmp     loc_18001167B
0x18001141e  test    rsi, rsi
0x180011421  jnz     short loc_18001145E
0x180011423  mov     ebx, 80004003h
0x180011428  cmp     rcx, r12
0x18001142b  jz      loc_18001168A
0x180011431  test    byte ptr [rcx+1Ch], 8
0x180011435  jz      loc_180011665
0x18001143b  cmp     byte ptr [rcx+19h], 2
0x18001143f  jb      loc_180011665
0x180011445  mov     edx, 0EBh
0x18001144a  mov     r9d, ebx
0x18001144d  mov     rcx, [rcx+10h]
0x180011451  mov     r8, r13
0x180011454  call    WPP_SF_d
0x180011459  jmp     loc_18001165E
0x18001145e  lea     rax, aEnabledFalse; "Enabled != FALSE"
0x180011465  mov     qword ptr [rsi], 0
0x18001146c  neg     bl
0x18001146e  lea     r8, ?c_wszHnetApplicationProtocol@@3QBGB; "HNet_ApplicationProtocol"
0x180011475  lea     rcx, [rsp+68h+bstrString]; unsigned __int16 **
0x18001147d  sbb     r9, r9
0x180011480  and     r9, rax; unsigned __int16 *
0x180011483  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x180011488  mov     ebx, eax
0x18001148a  test    eax, eax
0x18001148c  jns     short loc_1800114BC
0x18001148e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011495  cmp     rcx, r12
0x180011498  jz      loc_18001168A
0x18001149e  test    byte ptr [rcx+1Ch], 8
0x1800114a2  jz      loc_180011665
0x1800114a8  cmp     byte ptr [rcx+19h], 2
0x1800114ac  jb      loc_180011665
0x1800114b2  mov     edx, 0ECh
0x1800114b7  mov     r9d, eax
0x1800114ba  jmp     short loc_18001144D
0x1800114bc  jnz     loc_18001165E
0x1800114c2  mov     rcx, [rbp+40h]
0x1800114c6  lea     rdx, [rsp+68h+arg_0]
0x1800114cb  mov     r8, [rsp+68h+bstrString]
0x1800114d3  mov     r9d, 10h
0x1800114d9  mov     [rsp+68h+var_40], rdx
0x1800114de  mov     rdx, [rbp+58h]
0x1800114e2  mov     [rsp+68h+arg_0], 0
0x1800114eb  mov     rax, [rcx]
0x1800114ee  mov     [rsp+68h+var_48], 0
0x1800114f7  mov     rax, [rax+0A0h]
0x1800114fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011503  mov     ebx, eax
0x180011505  test    eax, eax
0x180011507  jns     short loc_180011535
0x180011509  mov     rcx, cs:WPP_GLOBAL_Control
0x180011510  cmp     rcx, r12
0x180011513  jz      short loc_180011535
0x180011515  test    byte ptr [rcx+1Ch], 8
0x180011519  jz      short loc_180011535
0x18001151b  cmp     byte ptr [rcx+19h], 2
0x18001151f  jb      short loc_180011535
0x180011521  mov     rcx, [rcx+10h]
0x180011525  mov     edx, 0EDh
0x18001152a  mov     r9d, eax
0x18001152d  mov     r8, r13
0x180011530  call    WPP_SF_d
0x180011535  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18001153d  call    cs:__imp_SysFreeString
0x180011543  test    ebx, ebx
0x180011545  jnz     loc_18001165E
0x18001154b  lea     rcx, [rsp+68h+bstrString]
0x180011553  mov     [rsp+68h+bstrString], 0
0x18001155f  call    ?CreateInstance@?$CComObject@V?$CHNCEnum@UIEnumHNetApplicationProtocols@@UIHNetApplicationProtocol@@VCHNetAppProtocol@@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNCEnum<IEnumHNetApplicationProtocols,IHNetApplicationProtocol,CHNetAppProtocol>>::CreateInstance(ATL::CComObject<CHNCEnum<IEnumHNetApplicationProtocols,IHNetApplicationProtocol,CHNetAppProtocol>> * *)
0x180011564  mov     ebx, eax
0x180011566  test    eax, eax
0x180011568  jns     short loc_1800115A7
0x18001156a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011571  cmp     rcx, r12
0x180011574  jz      loc_18001164D
0x18001157a  test    byte ptr [rcx+1Ch], 8
0x18001157e  jz      loc_18001164D
0x180011584  cmp     byte ptr [rcx+19h], 2
0x180011588  jb      loc_18001164D
0x18001158e  mov     rcx, [rcx+10h]
0x180011592  mov     edx, 0EEh
0x180011597  mov     r9d, eax
0x18001159a  mov     r8, r13
0x18001159d  call    WPP_SF_d
0x1800115a2  jmp     loc_18001164D
0x1800115a7  mov     rdi, [rsp+68h+bstrString]
0x1800115af  mov     rcx, rdi
0x1800115b2  mov     rax, [rdi]
0x1800115b5  mov     rax, [rax+8]
0x1800115b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115be  mov     r8, [rsp+68h+arg_0]
0x1800115c3  mov     rcx, rdi
0x1800115c6  mov     rdx, [rbp+40h]
0x1800115ca  call    ?Initialize@?$CHNCEnum@UIEnumHNetPortMappingBindings@@UIHNetPortMappingBinding@@VCHNetPortMappingBinding@@@@QEAAJPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(IWbemServices *,IEnumWbemClassObject *)
0x1800115cf  mov     ebx, eax
0x1800115d1  test    eax, eax
0x1800115d3  jns     short loc_1800115F4
0x1800115d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115dc  cmp     rcx, r12
0x1800115df  jz      short loc_18001163E
0x1800115e1  test    byte ptr [rcx+1Ch], 8
0x1800115e5  jz      short loc_18001163E
0x1800115e7  cmp     byte ptr [rcx+19h], 2
0x1800115eb  jb      short loc_18001163E
0x1800115ed  mov     edx, 0EFh
0x1800115f2  jmp     short loc_18001162F
0x1800115f4  mov     rax, [rdi]
0x1800115f7  lea     rdx, _GUID_85d18b7b_3032_11d4_9348_00c04f8eeb71
0x1800115fe  mov     r8, rsi
0x180011601  mov     rcx, rdi
0x180011604  mov     rax, [rax]
0x180011607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160c  mov     ebx, eax
0x18001160e  test    eax, eax
0x180011610  jns     short loc_18001163E
0x180011612  mov     rcx, cs:WPP_GLOBAL_Control
0x180011619  cmp     rcx, r12
0x18001161c  jz      short loc_18001163E
0x18001161e  test    byte ptr [rcx+1Ch], 8
0x180011622  jz      short loc_18001163E
0x180011624  cmp     byte ptr [rcx+19h], 2
0x180011628  jb      short loc_18001163E
0x18001162a  mov     edx, 0F0h
0x18001162f  mov     rcx, [rcx+10h]
0x180011633  mov     r9d, eax
0x180011636  mov     r8, r13
0x180011639  call    WPP_SF_d
0x18001163e  mov     rax, [rdi]
0x180011641  mov     rcx, rdi
0x180011644  mov     rax, [rax+10h]
0x180011648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164d  mov     rcx, [rsp+68h+arg_0]
0x180011652  mov     rax, [rcx]
0x180011655  mov     rax, [rax+10h]
0x180011659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011665  cmp     rcx, r12
0x180011668  jz      short loc_18001168A
0x18001166a  test    byte ptr [rcx+1Ch], 8
0x18001166e  jz      short loc_18001168A
0x180011670  cmp     byte ptr [rcx+19h], 6
0x180011674  jb      short loc_18001168A
0x180011676  mov     edx, 0F1h
0x18001167b  mov     rcx, [rcx+10h]
0x18001167f  mov     r9d, ebx
0x180011682  mov     r8, r13
0x180011685  call    WPP_SF_d
0x18001168a  mov     eax, ebx
0x18001168c  mov     rbx, [rsp+68h+arg_8]
0x180011691  add     rsp, 40h
0x180011695  pop     r13
0x180011697  pop     r12
0x180011699  pop     rdi
0x18001169a  pop     rsi
0x18001169b  pop     rbp
0x18001169c  retn
```
