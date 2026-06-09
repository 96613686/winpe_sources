# JetCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x10032780`
- end: `0x10032b9f`
- name: `_JetCreateRelationship@44`
- size: `1055`
- prototype: `int __stdcall(Session *, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10012940`
- `0x10016ed0`
- `0x10017010`
- `0x1001ea70`
- `0x10032780`
- `0x10032f00`
- `0x10036240`
- `0x1003e650`
- `0x1003e820`
- `0x100429d0`
- `0x10043260`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x1011653a`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100327fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032868`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100328fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032b7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100327fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032868`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100328fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100327e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100327e5`

## pseudocode

```c
int __stdcall JetCreateRelationship(
        Session *sesid,
        unsigned int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        _WORD *a8,
        unsigned int a9,
        __int16 **a10,
        unsigned int a11)
{
  unsigned int v12; // ebx
  int LinkInfo; // esi
  _WORD *v14; // edx
  unsigned int v15; // kr00_4
  int v16; // eax
  wchar_t *v17; // ecx
  int v19; // eax
  bool v20; // zf
  unsigned int v21; // [esp+Ch] [ebp-544h] BYREF
  int v22; // [esp+10h] [ebp-540h]
  int v23; // [esp+14h] [ebp-53Ch]
  int v24; // [esp+18h] [ebp-538h]
  _WORD *v25; // [esp+1Ch] [ebp-534h]
  __int16 *v26; // [esp+20h] [ebp-530h]
  __int16 **v27; // [esp+24h] [ebp-52Ch]
  int v28; // [esp+28h] [ebp-528h]
  int v29; // [esp+2Ch] [ebp-524h]
  int v30; // [esp+30h] [ebp-520h]
  _BYTE v31[4]; // [esp+34h] [ebp-51Ch] BYREF
  _BYTE v32[136]; // [esp+38h] [ebp-518h] BYREF
  _BYTE v33[136]; // [esp+C0h] [ebp-490h] BYREF
  wchar_t v34; // [esp+148h] [ebp-408h] BYREF
  __int16 v35; // [esp+14Ah] [ebp-406h] BYREF
  _BYTE v36[516]; // [esp+348h] [ebp-208h] BYREF

  v23 = a3;
  v29 = a5;
  v22 = a6;
  v30 = a7;
  v25 = a8;
  v27 = a10;
  v28 = a4;
  v21 = a2;
  v24 = 0;
  EnterCriticalSection(critJet);
  if ( !FValidSesid((int)sesid) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  if ( v21 >= dbidInit && v21 < 0x100 && (int *)mpdbidpvdbfndef[v21] != vdbfndefInvalidDbid )
  {
    v12 = a11;
    if ( (a11 & 0xFF00) != 0 && (a11 & 2) != 0 )
    {
LABEL_7:
      LeaveCriticalSection(critJet);
      return -1003;
    }
    if ( (a11 & 4) != 0 )
    {
      LinkInfo = ErrRelGetLinkInfo(a4, &v34, v32);
      if ( LinkInfo < 0 )
        goto LABEL_48;
      LinkInfo = ErrRelGetLinkInfo(v22, v36, v33);
      if ( LinkInfo < 0 )
        goto LABEL_48;
      if ( WCSICMP(&v34, v36) )
      {
        LeaveCriticalSection(critJet);
        return -1066;
      }
      LinkInfo = ErrOpenDatabase((int)sesid, &v34, 0, (int)&v21, 0);
      if ( LinkInfo < 0 )
        goto LABEL_48;
      v24 = 1;
      LinkInfo = ErrDispGetObjidFromName(sesid, v21, 0, L"Relationships", v31);
      if ( LinkInfo < 0 )
      {
LABEL_44:
        ErrDispCloseDatabase(sesid, v21, 0);
LABEL_45:
        if ( LinkInfo < 0 )
        {
          if ( v25 )
            *v25 = 0;
        }
LABEL_48:
        LeaveCriticalSection(critJet);
        return LinkInfo;
      }
      v12 = a11 & 0xFFFFFFFB;
      v28 = (int)v32;
      v22 = (int)v33;
    }
    v14 = v25;
    if ( v25 )
    {
      if ( !v27 )
        goto LABEL_7;
      v15 = wcslen((const unsigned __int16 *)v23);
      *v27 = (__int16 *)(v15 + 1);
      v16 = v24;
      v26 = (__int16 *)(v15 + 1);
      if ( v24 )
      {
        v17 = &v34;
        v26 = &v35;
        while ( *v17++ )
          ;
        v26 = (__int16 *)((((char *)v17 - (char *)v26) >> 1) + v15 + 5);
        *v27 = v26;
        v16 = v24;
      }
      if ( (unsigned int)v26 > a9 )
      {
        LeaveCriticalSection(critJet);
        return -1038;
      }
      *v14 = 0;
      if ( v16 )
      {
        *v14 = 91;
        WCSCPY2(a9 - 1);
        WCSCAT2(a9);
      }
      WCSCAT2(a9);
    }
    if ( (v12 & 8) != 0 )
    {
      LinkInfo = 0;
      goto LABEL_43;
    }
    LinkInfo = ErrIsamBeginTransaction(sesid);
    if ( LinkInfo < 0 )
    {
LABEL_43:
      if ( !v24 )
        goto LABEL_45;
      goto LABEL_44;
    }
    LinkInfo = ErrDoCreateRelationship(
                 sesid,
                 v21,
                 -1,
                 (const unsigned __int16 *)v23,
                 (void *)v28,
                 (const unsigned __int16 *)v29,
                 (void *)v22,
                 (_WORD *)v30,
                 v12,
                 1,
                 1);
    v29 = LinkInfo;
    if ( LinkInfo < 0 )
    {
      if ( (*((_DWORD *)*(&rgrepdbinfo + v21) + 57) & 3) == 1 )
      {
        ClearErrorInfo(sesid);
        LinkInfo = -20003;
      }
    }
    else
    {
      v19 = ErrREPCreateRelationship(sesid, v21, v23, v28, v22);
      LinkInfo = v19;
      if ( (v12 & 2) != 0 && (v19 == -20007 || v19 == -1305) )
      {
        ClearErrorInfo(sesid);
        goto LABEL_36;
      }
      if ( v19 >= 0 )
      {
LABEL_36:
        LinkInfo = ErrIsamCommitTransaction(sesid, 0);
        v20 = LinkInfo == 0;
        if ( LinkInfo >= 0 )
          goto LABEL_41;
      }
    }
    ErrIsamRollback(sesid, 0);
    v20 = LinkInfo == 0;
LABEL_41:
    if ( v20 )
      LinkInfo = v29;
    goto LABEL_43;
  }
  LeaveCriticalSection(critJet);
  return -1010;
}

```

## disassembly

```asm
0x10032780  mov     edi, edi
0x10032782  push    ebp
0x10032783  mov     ebp, esp
0x10032785  and     esp, 0FFFFFFF8h
0x10032788  sub     esp, 544h
0x1003278e  mov     eax, ___security_cookie
0x10032793  xor     eax, esp
0x10032795  mov     [esp+544h+var_4], eax
0x1003279c  mov     eax, [ebp+arg_8]
0x1003279f  mov     [esp+544h+var_53C], eax
0x100327a3  mov     eax, [ebp+arg_10]
0x100327a6  mov     [esp+544h+var_524], eax
0x100327aa  mov     eax, [ebp+arg_14]
0x100327ad  mov     [esp+544h+var_540], eax
0x100327b1  mov     eax, [ebp+arg_18]
0x100327b4  push    ebx
0x100327b5  push    esi
0x100327b6  mov     esi, [ebp+arg_C]
0x100327b9  mov     [esp+54Ch+var_520], eax
0x100327bd  mov     eax, [ebp+arg_1C]
0x100327c0  mov     [esp+54Ch+var_534], eax
0x100327c4  mov     eax, [ebp+arg_24]
0x100327c7  push    edi
0x100327c8  push    _critJet; lpCriticalSection
0x100327ce  mov     [esp+554h+var_52C], eax
0x100327d2  mov     eax, [ebp+arg_4]
0x100327d5  mov     [esp+554h+var_528], esi
0x100327d9  mov     [esp+554h+var_544], eax
0x100327dd  mov     [esp+554h+var_538], 0
0x100327e5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100327eb  mov     edi, [ebp+sesid]
0x100327ee  push    edi
0x100327ef  call    _FValidSesid@4; FValidSesid(x)
0x100327f4  test    eax, eax
0x100327f6  jnz     short loc_10032820
0x100327f8  push    _critJet; lpCriticalSection
0x100327fe  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032804  mov     eax, 0FFFFFBB0h
0x10032809  pop     edi
0x1003280a  pop     esi
0x1003280b  pop     ebx
0x1003280c  mov     ecx, [esp+544h+var_4]
0x10032813  xor     ecx, esp; StackCookie
0x10032815  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003281a  mov     esp, ebp
0x1003281c  pop     ebp
0x1003281d  retn    2Ch ; ','
0x10032820  mov     eax, [esp+550h+var_544]
0x10032824  cmp     eax, _dbidInit
0x1003282a  jb      loc_10032B77
0x10032830  cmp     eax, 100h
0x10032835  jnb     loc_10032B77
0x1003283b  cmp     _mpdbidpvdbfndef[eax*4], offset _vdbfndefInvalidDbid
0x10032846  jz      loc_10032B77
0x1003284c  mov     ebx, [ebp+arg_28]
0x1003284f  test    ebx, 0FF00h
0x10032855  setnz   cl
0x10032858  test    bl, 2
0x1003285b  setnz   al
0x1003285e  test    al, cl
0x10032860  jz      short loc_1003288A
0x10032862  push    _critJet; lpCriticalSection
0x10032868  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003286e  mov     eax, 0FFFFFC15h
0x10032873  pop     edi
0x10032874  pop     esi
0x10032875  pop     ebx
0x10032876  mov     ecx, [esp+544h+var_4]
0x1003287d  xor     ecx, esp; StackCookie
0x1003287f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032884  mov     esp, ebp
0x10032886  pop     ebp
0x10032887  retn    2Ch ; ','
0x1003288a  test    bl, 4
0x1003288d  jz      loc_1003297D
0x10032893  mov     edx, [esp+550h+var_544]
0x10032897  lea     eax, [esp+550h+var_518]
0x1003289b  push    eax
0x1003289c  lea     eax, [esp+554h+var_408]
0x100328a3  mov     ecx, edi
0x100328a5  push    eax
0x100328a6  push    esi
0x100328a7  call    ErrRelGetLinkInfo
0x100328ac  mov     esi, eax
0x100328ae  test    esi, esi
0x100328b0  js      loc_10032B52
0x100328b6  mov     edx, [esp+550h+var_544]
0x100328ba  lea     eax, [esp+550h+var_490]
0x100328c1  push    eax
0x100328c2  lea     eax, [esp+554h+var_208]
0x100328c9  mov     ecx, edi
0x100328cb  push    eax
0x100328cc  push    [esp+558h+var_540]
0x100328d0  call    ErrRelGetLinkInfo
0x100328d5  mov     esi, eax
0x100328d7  test    esi, esi
0x100328d9  js      loc_10032B52
0x100328df  lea     edx, [esp+550h+var_208]
0x100328e6  lea     ecx, [esp+550h+var_408]
0x100328ed  call    _WCSICMP@8; WCSICMP(x,x)
0x100328f2  test    eax, eax
0x100328f4  jz      short loc_1003291E
0x100328f6  push    _critJet; lpCriticalSection
0x100328fc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032902  mov     eax, 0FFFFFBD6h
0x10032907  pop     edi
0x10032908  pop     esi
0x10032909  pop     ebx
0x1003290a  mov     ecx, [esp+544h+var_4]
0x10032911  xor     ecx, esp; StackCookie
0x10032913  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032918  mov     esp, ebp
0x1003291a  pop     ebp
0x1003291b  retn    2Ch ; ','
0x1003291e  push    0
0x10032920  lea     eax, [esp+554h+var_544]
0x10032924  push    eax
0x10032925  push    0
0x10032927  lea     eax, [esp+55Ch+var_408]
0x1003292e  push    eax
0x1003292f  push    edi
0x10032930  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x10032935  mov     esi, eax
0x10032937  test    esi, esi
0x10032939  js      loc_10032B52
0x1003293f  lea     eax, [esp+550h+var_51C]
0x10032943  mov     [esp+550h+var_538], 1
0x1003294b  push    eax
0x1003294c  push    offset _wszRcObject; "Relationships"
0x10032951  push    0
0x10032953  push    [esp+55Ch+var_544]
0x10032957  push    edi
0x10032958  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1003295d  mov     esi, eax
0x1003295f  test    esi, esi
0x10032961  js      loc_10032B35
0x10032967  lea     eax, [esp+550h+var_518]
0x1003296b  and     ebx, 0FFFFFFFBh
0x1003296e  mov     [esp+550h+var_528], eax
0x10032972  lea     eax, [esp+550h+var_490]
0x10032979  mov     [esp+550h+var_540], eax
0x1003297d  mov     edx, [esp+550h+var_534]
0x10032981  test    edx, edx
0x10032983  jz      loc_10032A68
0x10032989  cmp     [esp+550h+var_52C], 0
0x1003298e  jz      loc_10032862
0x10032994  mov     ecx, [esp+550h+var_53C]
0x10032998  lea     esi, [ecx+2]
0x1003299b  nop     dword ptr [eax+eax+00h]
0x100329a0  mov     ax, [ecx]
0x100329a3  add     ecx, 2
0x100329a6  test    ax, ax
0x100329a9  jnz     short loc_100329A0
0x100329ab  mov     eax, [esp+550h+var_52C]
0x100329af  sub     ecx, esi
0x100329b1  sar     ecx, 1
0x100329b3  lea     esi, [ecx+1]
0x100329b6  mov     [eax], esi
0x100329b8  mov     eax, [esp+550h+var_538]
0x100329bc  mov     [esp+550h+var_530], esi
0x100329c0  test    eax, eax
0x100329c2  jz      short loc_100329F6
0x100329c4  lea     ecx, [esp+550h+var_408]
0x100329cb  lea     eax, [ecx+2]
0x100329ce  mov     [esp+550h+var_530], eax
0x100329d2  mov     ax, [ecx]
0x100329d5  add     ecx, 2
0x100329d8  test    ax, ax
0x100329db  jnz     short loc_100329D2
0x100329dd  sub     ecx, [esp+550h+var_530]
0x100329e1  add     esi, 4
0x100329e4  mov     eax, [esp+550h+var_52C]
0x100329e8  sar     ecx, 1
0x100329ea  add     esi, ecx
0x100329ec  mov     [esp+550h+var_530], esi
0x100329f0  mov     [eax], esi
0x100329f2  mov     eax, [esp+550h+var_538]
0x100329f6  mov     esi, [ebp+arg_20]
0x100329f9  cmp     [esp+550h+var_530], esi
0x100329fd  jbe     short loc_10032A27
0x100329ff  push    _critJet; lpCriticalSection
0x10032a05  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032a0b  mov     eax, 0FFFFFBF2h
0x10032a10  pop     edi
0x10032a11  pop     esi
0x10032a12  pop     ebx
0x10032a13  mov     ecx, [esp+544h+var_4]
0x10032a1a  xor     ecx, esp; StackCookie
0x10032a1c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032a21  mov     esp, ebp
0x10032a23  pop     ebp
0x10032a24  retn    2Ch ; ','
0x10032a27  xor     ecx, ecx
0x10032a29  mov     [edx], cx
0x10032a2c  test    eax, eax
0x10032a2e  jz      short loc_10032A5A
0x10032a30  mov     eax, 5Bh ; '['
0x10032a35  lea     ecx, [edx+2]
0x10032a38  mov     [edx], ax
0x10032a3b  lea     eax, [esi-1]
0x10032a3e  push    eax
0x10032a3f  lea     edx, [esp+554h+var_408]
0x10032a46  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10032a4b  mov     ecx, [esp+550h+var_534]
0x10032a4f  mov     edx, offset asc_100098D0; "]."
0x10032a54  push    esi
0x10032a55  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10032a5a  mov     edx, [esp+550h+var_53C]
0x10032a5e  mov     ecx, [esp+550h+var_534]
0x10032a62  push    esi
0x10032a63  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10032a68  test    bl, 8
0x10032a6b  jz      short loc_10032A74
0x10032a6d  xor     esi, esi
0x10032a6f  jmp     loc_10032B2E
0x10032a74  push    edi
0x10032a75  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x10032a7a  mov     esi, eax
0x10032a7c  test    esi, esi
0x10032a7e  js      loc_10032B2E
0x10032a84  push    1; int
0x10032a86  push    1; int
0x10032a88  push    ebx; int
0x10032a89  push    [esp+55Ch+var_520]; int
0x10032a8d  push    [esp+560h+var_540]; int
0x10032a91  push    [esp+564h+var_524]; int
0x10032a95  push    [esp+568h+var_528]; int
0x10032a99  push    [esp+56Ch+var_53C]; int
0x10032a9d  push    0FFFFFFFFh; int
0x10032a9f  push    [esp+574h+var_544]; int
0x10032aa3  push    edi; sesid
0x10032aa4  call    _ErrDoCreateRelationship@44; ErrDoCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)
0x10032aa9  mov     esi, eax
0x10032aab  mov     [esp+550h+var_524], esi
0x10032aaf  test    esi, esi
0x10032ab1  js      short loc_10032AFD
0x10032ab3  push    [esp+550h+var_540]; int
0x10032ab7  mov     edx, [esp+554h+var_544]; unsigned int
0x10032abb  mov     ecx, edi; Session *
0x10032abd  push    [esp+554h+var_528]; int
0x10032ac1  push    [esp+558h+var_53C]; int
0x10032ac5  call    _ErrREPCreateRelationship@20; ErrREPCreateRelationship(x,x,x,x,x)
0x10032aca  mov     esi, eax
0x10032acc  test    bl, 2
0x10032acf  jz      short loc_10032AE9
0x10032ad1  cmp     esi, 0FFFFB1D9h
0x10032ad7  jz      short loc_10032AE1
0x10032ad9  cmp     esi, 0FFFFFAE7h
0x10032adf  jnz     short loc_10032AE9
0x10032ae1  push    edi
0x10032ae2  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10032ae7  jmp     short loc_10032AED
0x10032ae9  test    esi, esi
0x10032aeb  js      short loc_10032B1F
0x10032aed  push    0
0x10032aef  push    edi
0x10032af0  call    _ErrIsamCommitTransaction@8; ErrIsamCommitTransaction(x,x)
0x10032af5  mov     esi, eax
0x10032af7  test    esi, esi
0x10032af9  jns     short loc_10032B29
0x10032afb  jmp     short loc_10032B1F
0x10032afd  mov     eax, [esp+550h+var_544]
0x10032b01  mov     eax, _rgrepdbinfo[eax*4]
0x10032b08  mov     eax, [eax+0E4h]
0x10032b0e  and     al, 3
0x10032b10  cmp     al, 1
0x10032b12  jnz     short loc_10032B1F
0x10032b14  push    edi
0x10032b15  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10032b1a  mov     esi, 0FFFFB1DDh
0x10032b1f  push    0; char
0x10032b21  push    edi; Session *
0x10032b22  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10032b27  test    esi, esi
0x10032b29  cmovz   esi, [esp+550h+var_524]
0x10032b2e  cmp     [esp+550h+var_538], 0
0x10032b33  jz      short loc_10032B41
0x10032b35  push    0
0x10032b37  push    [esp+554h+var_544]
0x10032b3b  push    edi
0x10032b3c  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10032b41  test    esi, esi
0x10032b43  jns     short loc_10032B52
0x10032b45  mov     eax, [esp+550h+var_534]
0x10032b49  test    eax, eax
0x10032b4b  jz      short loc_10032B52
0x10032b4d  xor     ecx, ecx
0x10032b4f  mov     [eax], cx
0x10032b52  push    _critJet; lpCriticalSection
0x10032b58  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032b5e  mov     eax, esi
0x10032b60  pop     edi
0x10032b61  pop     esi
0x10032b62  pop     ebx
0x10032b63  mov     ecx, [esp+544h+var_4]
0x10032b6a  xor     ecx, esp; StackCookie
0x10032b6c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032b71  mov     esp, ebp
0x10032b73  pop     ebp
0x10032b74  retn    2Ch ; ','
  ... truncated ...
```
