# CHNetConn::ShowAutoconfigBalloon(uchar *)

- ea: `0x180020ef0`
- end: `0x180021452`
- name: `?ShowAutoconfigBalloon@CHNetConn@@UEAAJPEAE@Z`
- size: `1378`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001b1e8`
- `0x18001e130`
- `0x180020ef0`
- `0x180027fc4`
- `0x180028210`
- `0x18002a7d4`
- `0x18002ae64`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002109b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002109b`
- `OLEAUT32!__imp_SysFreeString` at `0x180021114`
- `OLEAUT32!__imp_SysFreeString` at `0x180021114`

## string_xrefs

- `0x180021051`: `HNet_ConnectionAutoconfig`
- `0x1800211d3`: `HNet_ConnectionAutoconfig`

## pseudocode

```c
__int64 __fastcall CHNetConn::ShowAutoconfigBalloon(CHNetConn *this, unsigned __int8 *a2)
{
  PVOID *v4; // rcx
  unsigned int Properties; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int8 v14; // si
  int v15; // ebx
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int ConnectionPropertiesObject; // eax
  struct IWbemClassObject *v21; // [rsp+40h] [rbp-40h] BYREF
  struct IEnumWbemClassObject *v22; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-18h] BYREF
  int v25; // [rsp+70h] [rbp-10h]

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  bstrString = 0;
  v21 = 0;
  v22 = 0;
  if ( a2 )
  {
    Properties = 0;
    *a2 = 0;
LABEL_11:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  Properties = -2147467261;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_d(v4[2], 190, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147500035LL);
    goto LABEL_11;
  }
LABEL_12:
  if ( !*((_BYTE *)this + 96) )
  {
    Properties = -2147418113;
    if ( v4 == &WPP_GLOBAL_Control )
      return Properties;
    if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      v6 = 191;
      v7 = 2147549183LL;
LABEL_17:
      WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
LABEL_81:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  if ( Properties )
    goto LABEL_82;
  v8 = BuildEscapedQuotedEqualsString((unsigned __int16 **)&v21, L"Connection", *((const unsigned __int16 **)this + 9));
  Properties = v8;
  if ( v8 >= 0 )
  {
    if ( v8 )
      goto LABEL_81;
    v10 = BuildSelectQueryBstr(&bstrString, v9, L"HNet_ConnectionAutoconfig", (const unsigned __int16 *)v21);
    Properties = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v10);
    }
    operator delete[](v21);
    if ( Properties )
      goto LABEL_81;
    v11 = *((_QWORD *)this + 8);
    v12 = *((_QWORD *)this + 15);
    v22 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR, __int64, _QWORD, struct IEnumWbemClassObject **))(*(_QWORD *)v11 + 160LL))(
            v11,
            v12,
            bstrString,
            48,
            0,
            &v22);
    Properties = v13;
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v13);
    }
    SysFreeString(bstrString);
    if ( Properties )
      goto LABEL_81;
    LODWORD(bstrString) = 0;
    v14 = 1;
    v21 = 0;
    Properties = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, BSTR *))v22->lpVtbl->Next)(
                   v22,
                   0xFFFFFFFFLL,
                   1,
                   &v21,
                   &bstrString);
    if ( (Properties & 0x80000000) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, Properties);
    }
    ValidateFinishedWCOEnum(*((struct IWbemServices **)this + 8), v22);
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v22->lpVtbl->Release)(v22);
    if ( !Properties && (_DWORD)bstrString == 1 )
    {
      v14 = 0;
      ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->Release)(v21);
LABEL_80:
      *a2 = v14;
      goto LABEL_81;
    }
    v15 = SpawnNewInstance(*((struct IWbemServices **)this + 8), L"HNet_ConnectionAutoconfig", &v21);
    if ( v15 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        196,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v15);
    }
    if ( v15 )
    {
LABEL_64:
      v21 = 0;
      bstrString = 0;
      v25 = 0;
      ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject(this, &v21);
      Properties = ConnectionPropertiesObject;
      if ( ConnectionPropertiesObject < 0 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return Properties;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            199,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)ConnectionPropertiesObject);
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_82;
      }
      if ( ConnectionPropertiesObject )
        goto LABEL_81;
      Properties = CHNetConn::InternalGetProperties(this, v21, (struct tagHNET_CONN_PROPERTIES *)&bstrString);
      if ( (Properties & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, Properties);
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->Release)(v21);
      if ( Properties )
        goto LABEL_81;
      if ( *(_WORD *)((char *)&bstrString + 1)
        || __PAIR16__(BYTE3(bstrString), 0) != BYTE4(bstrString)
        || BYTE5(bstrString) )
      {
        v14 = 0;
      }
      goto LABEL_80;
    }
    v23[2] = 0;
    v23[1] = *((_QWORD *)this + 9);
    v23[0] = 8;
    v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, _QWORD *, _DWORD))v21->lpVtbl->Put)(
            v21,
            L"Connection",
            0,
            v23,
            0);
    if ( v16 >= 0 )
    {
      if ( v16 )
        goto LABEL_63;
      v16 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64))(**((_QWORD **)this + 8) + 112LL))(
              *((_QWORD *)this + 8),
              v21,
              2);
      if ( v16 >= 0 )
        goto LABEL_63;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v18 = 198;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v18 = 197;
    }
    WPP_SF_d(v17[2], v18, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v16);
LABEL_63:
    ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->Release)(v21);
    goto LABEL_64;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 192;
    v7 = (unsigned int)v8;
    goto LABEL_17;
  }
LABEL_82:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 201, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, Properties);
  return Properties;
}

```

## disassembly

```asm
0x180020ef0  mov     [rsp-28h+arg_10], rbx
0x180020ef5  mov     [rsp-28h+arg_18], rsi
0x180020efa  push    rbp
0x180020efb  push    rdi
0x180020efc  push    r12
0x180020efe  push    r14
0x180020f00  push    r15
0x180020f02  mov     rbp, rsp
0x180020f05  sub     rsp, 80h
0x180020f0c  mov     rax, cs:__security_cookie
0x180020f13  xor     rax, rsp
0x180020f16  mov     [rbp+var_8], rax
0x180020f1a  mov     r14, rdx
0x180020f1d  mov     rdi, rcx
0x180020f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f27  lea     rsi, WPP_GLOBAL_Control
0x180020f2e  mov     r12d, 8
0x180020f34  cmp     rcx, rsi
0x180020f37  jz      short loc_180020F61
0x180020f39  test    [rcx+1Ch], r12b
0x180020f3d  jz      short loc_180020F61
0x180020f3f  cmp     byte ptr [rcx+19h], 6
0x180020f43  jb      short loc_180020F61
0x180020f45  mov     rcx, [rcx+10h]
0x180020f49  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020f50  mov     edx, 0BDh
0x180020f55  call    WPP_SF_
0x180020f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f61  xor     r15d, r15d
0x180020f64  mov     [rbp+bstrString], r15
0x180020f68  mov     [rbp+var_40], r15
0x180020f6c  mov     [rbp+var_38], r15
0x180020f70  test    r14, r14
0x180020f73  jz      short loc_180020F7D
0x180020f75  mov     ebx, r15d
0x180020f78  mov     [r14], r15b
0x180020f7b  jmp     short loc_180020FAB
0x180020f7d  mov     ebx, 80004003h
0x180020f82  cmp     rcx, rsi
0x180020f85  jz      short loc_180020FB2
0x180020f87  test    [rcx+1Ch], r12b
0x180020f8b  jz      short loc_180020FB2
0x180020f8d  cmp     byte ptr [rcx+19h], 2
0x180020f91  jb      short loc_180020FB2
0x180020f93  mov     rcx, [rcx+10h]
0x180020f97  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020f9e  mov     edx, 0BEh
0x180020fa3  mov     r9d, ebx
0x180020fa6  call    WPP_SF_d
0x180020fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb2  cmp     [rdi+60h], r15b
0x180020fb6  jnz     short loc_180020FF7
0x180020fb8  mov     ebx, 8000FFFFh
0x180020fbd  cmp     rcx, rsi
0x180020fc0  jz      loc_180021428
0x180020fc6  test    [rcx+1Ch], r12b
0x180020fca  jz      loc_1800213F8
0x180020fd0  cmp     byte ptr [rcx+19h], 2
0x180020fd4  jb      loc_1800213F8
0x180020fda  mov     edx, 0BFh
0x180020fdf  mov     r9d, ebx
0x180020fe2  mov     rcx, [rcx+10h]
0x180020fe6  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180020fed  call    WPP_SF_d
0x180020ff2  jmp     loc_1800213F1
0x180020ff7  test    ebx, ebx
0x180020ff9  jnz     loc_1800213F8
0x180020fff  mov     r8, [rdi+48h]; unsigned __int16 *
0x180021003  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x18002100a  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x18002100e  call    ?BuildEscapedQuotedEqualsString@@YAJPEAPEAGPEBG1@Z; BuildEscapedQuotedEqualsString(ushort * *,ushort const *,ushort const *)
0x180021013  mov     ebx, eax
0x180021015  test    eax, eax
0x180021017  jns     short loc_180021047
0x180021019  mov     rcx, cs:WPP_GLOBAL_Control
0x180021020  cmp     rcx, rsi
0x180021023  jz      loc_1800213F8
0x180021029  test    [rcx+1Ch], r12b
0x18002102d  jz      loc_1800213F8
0x180021033  cmp     byte ptr [rcx+19h], 2
0x180021037  jb      loc_1800213F8
0x18002103d  mov     edx, 0C0h
0x180021042  mov     r9d, eax
0x180021045  jmp     short loc_180020FE2
0x180021047  jnz     loc_1800213F1
0x18002104d  mov     r9, [rbp+var_40]; unsigned __int16 *
0x180021051  lea     r8, ?c_wszHnetConnectionAutoconfig@@3QBGB; "HNet_ConnectionAutoconfig"
0x180021058  lea     rcx, [rbp+bstrString]; unsigned __int16 **
0x18002105c  call    ?BuildSelectQueryBstr@@YAJPEAPEAGPEBG11@Z; BuildSelectQueryBstr(ushort * *,ushort const *,ushort const *,ushort const *)
0x180021061  mov     ebx, eax
0x180021063  test    eax, eax
0x180021065  jns     short loc_180021097
0x180021067  mov     rcx, cs:WPP_GLOBAL_Control
0x18002106e  cmp     rcx, rsi
0x180021071  jz      short loc_180021097
0x180021073  test    [rcx+1Ch], r12b
0x180021077  jz      short loc_180021097
0x180021079  cmp     byte ptr [rcx+19h], 2
0x18002107d  jb      short loc_180021097
0x18002107f  mov     rcx, [rcx+10h]
0x180021083  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002108a  mov     edx, 0C1h
0x18002108f  mov     r9d, eax
0x180021092  call    WPP_SF_d
0x180021097  mov     rcx, [rbp+var_40]
0x18002109b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800210a1  test    ebx, ebx
0x1800210a3  jnz     loc_1800213F1
0x1800210a9  mov     rcx, [rdi+40h]
0x1800210ad  lea     rdx, [rbp+var_38]
0x1800210b1  mov     r8, [rbp+bstrString]
0x1800210b5  lea     r9d, [rbx+30h]
0x1800210b9  mov     [rsp+80h+var_58], rdx
0x1800210be  mov     rdx, [rdi+78h]
0x1800210c2  mov     [rbp+var_38], r15
0x1800210c6  mov     rax, [rcx]
0x1800210c9  mov     [rsp+80h+var_60], r15
0x1800210ce  mov     rax, [rax+0A0h]
0x1800210d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210da  mov     ebx, eax
0x1800210dc  test    eax, eax
0x1800210de  jns     short loc_180021110
0x1800210e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210e7  cmp     rcx, rsi
0x1800210ea  jz      short loc_180021110
0x1800210ec  test    [rcx+1Ch], r12b
0x1800210f0  jz      short loc_180021110
0x1800210f2  cmp     byte ptr [rcx+19h], 2
0x1800210f6  jb      short loc_180021110
0x1800210f8  mov     rcx, [rcx+10h]
0x1800210fc  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180021103  mov     edx, 0C2h
0x180021108  mov     r9d, eax
0x18002110b  call    WPP_SF_d
0x180021110  mov     rcx, [rbp+bstrString]; bstrString
0x180021114  call    cs:__imp_SysFreeString
0x18002111a  test    ebx, ebx
0x18002111c  jnz     loc_1800213F1
0x180021122  mov     rcx, [rbp+var_38]
0x180021126  lea     rdx, [rbp+bstrString]
0x18002112a  mov     dword ptr [rbp+bstrString], r15d
0x18002112e  lea     esi, [rbx+1]
0x180021131  mov     [rbp+var_40], r15
0x180021135  lea     r9, [rbp+var_40]
0x180021139  mov     [rsp+80h+var_60], rdx
0x18002113e  mov     r8d, esi
0x180021141  mov     rax, [rcx]
0x180021144  or      edx, 0FFFFFFFFh
0x180021147  mov     rax, [rax+20h]
0x18002114b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021150  mov     ebx, eax
0x180021152  test    eax, eax
0x180021154  jns     short loc_18002118D
0x180021156  mov     rcx, cs:WPP_GLOBAL_Control
0x18002115d  lea     rax, WPP_GLOBAL_Control
0x180021164  cmp     rcx, rax
0x180021167  jz      short loc_18002118D
0x180021169  test    [rcx+1Ch], r12b
0x18002116d  jz      short loc_18002118D
0x18002116f  cmp     byte ptr [rcx+19h], 2
0x180021173  jb      short loc_18002118D
0x180021175  mov     rcx, [rcx+10h]
0x180021179  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180021180  mov     edx, 0C3h
0x180021185  mov     r9d, ebx
0x180021188  call    WPP_SF_d
0x18002118d  mov     rdx, [rbp+var_38]; struct IEnumWbemClassObject *
0x180021191  mov     rcx, [rdi+40h]; struct IWbemServices *
0x180021195  call    ?ValidateFinishedWCOEnum@@YAXPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; ValidateFinishedWCOEnum(IWbemServices *,IEnumWbemClassObject *)
0x18002119a  mov     rcx, [rbp+var_38]
0x18002119e  mov     rax, [rcx]
0x1800211a1  mov     rax, [rax+10h]
0x1800211a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211aa  test    ebx, ebx
0x1800211ac  jnz     short loc_1800211CB
0x1800211ae  cmp     dword ptr [rbp+bstrString], esi
0x1800211b1  jnz     short loc_1800211CB
0x1800211b3  mov     rcx, [rbp+var_40]
0x1800211b7  mov     sil, r15b
0x1800211ba  mov     rax, [rcx]
0x1800211bd  mov     rax, [rax+10h]
0x1800211c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211c6  jmp     loc_1800213EE
0x1800211cb  mov     rcx, [rdi+40h]; struct IWbemServices *
0x1800211cf  lea     r8, [rbp+var_40]; struct IWbemClassObject **
0x1800211d3  lea     rdx, ?c_wszHnetConnectionAutoconfig@@3QBGB; "HNet_ConnectionAutoconfig"
0x1800211da  call    ?SpawnNewInstance@@YAJPEAUIWbemServices@@PEBGPEAPEAUIWbemClassObject@@@Z; SpawnNewInstance(IWbemServices *,ushort const *,IWbemClassObject * *)
0x1800211df  mov     ebx, eax
0x1800211e1  test    eax, eax
0x1800211e3  jns     short loc_18002121C
0x1800211e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211ec  lea     rax, WPP_GLOBAL_Control
0x1800211f3  cmp     rcx, rax
0x1800211f6  jz      short loc_18002121C
0x1800211f8  test    [rcx+1Ch], r12b
0x1800211fc  jz      short loc_18002121C
0x1800211fe  cmp     byte ptr [rcx+19h], 2
0x180021202  jb      short loc_18002121C
0x180021204  mov     rcx, [rcx+10h]
0x180021208  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002120f  mov     edx, 0C4h
0x180021214  mov     r9d, ebx
0x180021217  call    WPP_SF_d
0x18002121c  test    ebx, ebx
0x18002121e  jnz     loc_1800212F8
0x180021224  mov     rcx, [rbp+var_40]
0x180021228  lea     r9, [rbp+var_30]
0x18002122c  xor     eax, eax
0x18002122e  mov     dword ptr [rsp+80h+var_60], r15d
0x180021233  mov     [rbp+var_20], rax
0x180021237  lea     rdx, ?c_wszConnection@@3QBGB; "Connection"
0x18002123e  mov     rax, [rdi+48h]
0x180021242  xorps   xmm0, xmm0
0x180021245  movups  [rbp+var_30], xmm0
0x180021249  mov     qword ptr [rbp+var_30+8], rax
0x18002124d  xor     r8d, r8d
0x180021250  mov     word ptr [rbp+var_30], r12w
0x180021255  mov     rax, [rcx]
0x180021258  mov     rax, [rax+28h]
0x18002125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021261  test    eax, eax
0x180021263  jns     short loc_18002128B
0x180021265  mov     rcx, cs:WPP_GLOBAL_Control
0x18002126c  lea     rdx, WPP_GLOBAL_Control
0x180021273  cmp     rcx, rdx
0x180021276  jz      short loc_1800212E8
0x180021278  test    [rcx+1Ch], r12b
0x18002127c  jz      short loc_1800212E8
0x18002127e  cmp     byte ptr [rcx+19h], 2
0x180021282  jb      short loc_1800212E8
0x180021284  mov     edx, 0C5h
0x180021289  jmp     short loc_1800212D5
0x18002128b  jnz     short loc_1800212E8
0x18002128d  mov     rcx, [rdi+40h]
0x180021291  xor     r9d, r9d
0x180021294  mov     rdx, [rbp+var_40]
0x180021298  mov     [rsp+80h+var_60], r15
0x18002129d  mov     rax, [rcx]
0x1800212a0  lea     r8d, [r9+2]
0x1800212a4  mov     rax, [rax+70h]
0x1800212a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ad  test    eax, eax
0x1800212af  jns     short loc_1800212E8
0x1800212b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212b8  lea     rdx, WPP_GLOBAL_Control
0x1800212bf  cmp     rcx, rdx
0x1800212c2  jz      short loc_1800212E8
0x1800212c4  test    [rcx+1Ch], r12b
0x1800212c8  jz      short loc_1800212E8
0x1800212ca  cmp     byte ptr [rcx+19h], 2
0x1800212ce  jb      short loc_1800212E8
0x1800212d0  mov     edx, 0C6h
0x1800212d5  mov     rcx, [rcx+10h]
0x1800212d9  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x1800212e0  mov     r9d, eax
0x1800212e3  call    WPP_SF_d
0x1800212e8  mov     rcx, [rbp+var_40]
0x1800212ec  mov     rax, [rcx]
0x1800212ef  mov     rax, [rax+10h]
0x1800212f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212f8  xor     eax, eax
0x1800212fa  mov     [rbp+var_40], r15
0x1800212fe  lea     rdx, [rbp+var_40]; struct IWbemClassObject **
0x180021302  mov     [rbp+bstrString], rax
0x180021306  mov     rcx, rdi; this
0x180021309  mov     [rbp+var_10], eax
0x18002130c  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x180021311  mov     ebx, eax
0x180021313  test    eax, eax
0x180021315  jns     short loc_180021366
0x180021317  mov     rcx, cs:WPP_GLOBAL_Control
0x18002131e  lea     rdi, WPP_GLOBAL_Control
0x180021325  cmp     rcx, rdi
0x180021328  jz      loc_180021428
0x18002132e  test    [rcx+1Ch], r12b
0x180021332  jz      loc_1800213FF
0x180021338  cmp     byte ptr [rcx+19h], 2
0x18002133c  jb      loc_1800213FF
0x180021342  mov     rcx, [rcx+10h]
0x180021346  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18002134d  mov     edx, 0C7h
0x180021352  mov     r9d, eax
0x180021355  call    WPP_SF_d
0x18002135a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021361  jmp     loc_1800213FF
0x180021366  jnz     loc_1800213F1
0x18002136c  mov     rdx, [rbp+var_40]; struct IWbemClassObject *
0x180021370  lea     r8, [rbp+bstrString]; struct tagHNET_CONN_PROPERTIES *
0x180021374  mov     rcx, rdi; this
0x180021377  call    ?InternalGetProperties@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_CONN_PROPERTIES@@@Z; CHNetConn::InternalGetProperties(IWbemClassObject *,tagHNET_CONN_PROPERTIES *)
0x18002137c  mov     ebx, eax
0x18002137e  test    eax, eax
0x180021380  jns     short loc_1800213B9
0x180021382  mov     rcx, cs:WPP_GLOBAL_Control
0x180021389  lea     rax, WPP_GLOBAL_Control
0x180021390  cmp     rcx, rax
0x180021393  jz      short loc_1800213B9
0x180021395  test    [rcx+1Ch], r12b
0x180021399  jz      short loc_1800213B9
0x18002139b  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
