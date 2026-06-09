# JetCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x10032920`
- end: `0x10032d3f`
- name: `_JetCreateRelationship@44`
- size: `1055`
- prototype: `int __stdcall(Session *, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10012a80`
- `0x10017010`
- `0x10017150`
- `0x1001ebc0`
- `0x10032920`
- `0x100330a0`
- `0x100363d0`
- `0x1003e7e0`
- `0x1003e9b0`
- `0x10042b60`
- `0x100433f0`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x101166ea`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003299e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032cf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032d1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1003299e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032cf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10032d1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10032985`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10032985`

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
        WCSCPY2(v14 + 1, &v34, a9 - 1);
        WCSCAT2(v25, L"].", a9);
      }
      WCSCAT2(v25, (_WORD *)v23, a9);
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
      v19 = ErrREPCreateRelationship(sesid, v21, (__int16 *)v23, (void *)v28, (void *)v22);
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
0x10032920  mov     edi, edi
0x10032922  push    ebp
0x10032923  mov     ebp, esp
0x10032925  and     esp, 0FFFFFFF8h
0x10032928  sub     esp, 544h
0x1003292e  mov     eax, ___security_cookie
0x10032933  xor     eax, esp
0x10032935  mov     [esp+544h+var_4], eax
0x1003293c  mov     eax, [ebp+arg_8]
0x1003293f  mov     [esp+544h+var_53C], eax
0x10032943  mov     eax, [ebp+arg_10]
0x10032946  mov     [esp+544h+var_524], eax
0x1003294a  mov     eax, [ebp+arg_14]
0x1003294d  mov     [esp+544h+var_540], eax
0x10032951  mov     eax, [ebp+arg_18]
0x10032954  push    ebx
0x10032955  push    esi
0x10032956  mov     esi, [ebp+arg_C]
0x10032959  mov     [esp+54Ch+var_520], eax
0x1003295d  mov     eax, [ebp+arg_1C]
0x10032960  mov     [esp+54Ch+var_534], eax
0x10032964  mov     eax, [ebp+arg_24]
0x10032967  push    edi
0x10032968  push    _critJet; lpCriticalSection
0x1003296e  mov     [esp+554h+var_52C], eax
0x10032972  mov     eax, [ebp+arg_4]
0x10032975  mov     [esp+554h+var_528], esi
0x10032979  mov     [esp+554h+var_544], eax
0x1003297d  mov     [esp+554h+var_538], 0
0x10032985  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1003298b  mov     edi, [ebp+sesid]
0x1003298e  push    edi
0x1003298f  call    _FValidSesid@4; FValidSesid(x)
0x10032994  test    eax, eax
0x10032996  jnz     short loc_100329C0
0x10032998  push    _critJet; lpCriticalSection
0x1003299e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100329a4  mov     eax, 0FFFFFBB0h
0x100329a9  pop     edi
0x100329aa  pop     esi
0x100329ab  pop     ebx
0x100329ac  mov     ecx, [esp+544h+var_4]
0x100329b3  xor     ecx, esp; StackCookie
0x100329b5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100329ba  mov     esp, ebp
0x100329bc  pop     ebp
0x100329bd  retn    2Ch ; ','
0x100329c0  mov     eax, [esp+550h+var_544]
0x100329c4  cmp     eax, _dbidInit
0x100329ca  jb      loc_10032D17
0x100329d0  cmp     eax, 100h
0x100329d5  jnb     loc_10032D17
0x100329db  cmp     _mpdbidpvdbfndef[eax*4], offset _vdbfndefInvalidDbid
0x100329e6  jz      loc_10032D17
0x100329ec  mov     ebx, [ebp+arg_28]
0x100329ef  test    ebx, 0FF00h
0x100329f5  setnz   cl
0x100329f8  test    bl, 2
0x100329fb  setnz   al
0x100329fe  test    al, cl
0x10032a00  jz      short loc_10032A2A
0x10032a02  push    _critJet; lpCriticalSection
0x10032a08  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032a0e  mov     eax, 0FFFFFC15h
0x10032a13  pop     edi
0x10032a14  pop     esi
0x10032a15  pop     ebx
0x10032a16  mov     ecx, [esp+544h+var_4]
0x10032a1d  xor     ecx, esp; StackCookie
0x10032a1f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032a24  mov     esp, ebp
0x10032a26  pop     ebp
0x10032a27  retn    2Ch ; ','
0x10032a2a  test    bl, 4
0x10032a2d  jz      loc_10032B1D
0x10032a33  mov     edx, [esp+550h+var_544]
0x10032a37  lea     eax, [esp+550h+var_518]
0x10032a3b  push    eax
0x10032a3c  lea     eax, [esp+554h+var_408]
0x10032a43  mov     ecx, edi
0x10032a45  push    eax
0x10032a46  push    esi
0x10032a47  call    ErrRelGetLinkInfo
0x10032a4c  mov     esi, eax
0x10032a4e  test    esi, esi
0x10032a50  js      loc_10032CF2
0x10032a56  mov     edx, [esp+550h+var_544]
0x10032a5a  lea     eax, [esp+550h+var_490]
0x10032a61  push    eax
0x10032a62  lea     eax, [esp+554h+var_208]
0x10032a69  mov     ecx, edi
0x10032a6b  push    eax
0x10032a6c  push    [esp+558h+var_540]
0x10032a70  call    ErrRelGetLinkInfo
0x10032a75  mov     esi, eax
0x10032a77  test    esi, esi
0x10032a79  js      loc_10032CF2
0x10032a7f  lea     edx, [esp+550h+var_208]
0x10032a86  lea     ecx, [esp+550h+var_408]
0x10032a8d  call    _WCSICMP@8; WCSICMP(x,x)
0x10032a92  test    eax, eax
0x10032a94  jz      short loc_10032ABE
0x10032a96  push    _critJet; lpCriticalSection
0x10032a9c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032aa2  mov     eax, 0FFFFFBD6h
0x10032aa7  pop     edi
0x10032aa8  pop     esi
0x10032aa9  pop     ebx
0x10032aaa  mov     ecx, [esp+544h+var_4]
0x10032ab1  xor     ecx, esp; StackCookie
0x10032ab3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032ab8  mov     esp, ebp
0x10032aba  pop     ebp
0x10032abb  retn    2Ch ; ','
0x10032abe  push    0
0x10032ac0  lea     eax, [esp+554h+var_544]
0x10032ac4  push    eax
0x10032ac5  push    0
0x10032ac7  lea     eax, [esp+55Ch+var_408]
0x10032ace  push    eax
0x10032acf  push    edi
0x10032ad0  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x10032ad5  mov     esi, eax
0x10032ad7  test    esi, esi
0x10032ad9  js      loc_10032CF2
0x10032adf  lea     eax, [esp+550h+var_51C]
0x10032ae3  mov     [esp+550h+var_538], 1
0x10032aeb  push    eax
0x10032aec  push    offset _wszRcObject; "Relationships"
0x10032af1  push    0
0x10032af3  push    [esp+55Ch+var_544]
0x10032af7  push    edi
0x10032af8  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10032afd  mov     esi, eax
0x10032aff  test    esi, esi
0x10032b01  js      loc_10032CD5
0x10032b07  lea     eax, [esp+550h+var_518]
0x10032b0b  and     ebx, 0FFFFFFFBh
0x10032b0e  mov     [esp+550h+var_528], eax
0x10032b12  lea     eax, [esp+550h+var_490]
0x10032b19  mov     [esp+550h+var_540], eax
0x10032b1d  mov     edx, [esp+550h+var_534]
0x10032b21  test    edx, edx
0x10032b23  jz      loc_10032C08
0x10032b29  cmp     [esp+550h+var_52C], 0
0x10032b2e  jz      loc_10032A02
0x10032b34  mov     ecx, [esp+550h+var_53C]
0x10032b38  lea     esi, [ecx+2]
0x10032b3b  nop     dword ptr [eax+eax+00h]
0x10032b40  mov     ax, [ecx]
0x10032b43  add     ecx, 2
0x10032b46  test    ax, ax
0x10032b49  jnz     short loc_10032B40
0x10032b4b  mov     eax, [esp+550h+var_52C]
0x10032b4f  sub     ecx, esi
0x10032b51  sar     ecx, 1
0x10032b53  lea     esi, [ecx+1]
0x10032b56  mov     [eax], esi
0x10032b58  mov     eax, [esp+550h+var_538]
0x10032b5c  mov     [esp+550h+var_530], esi
0x10032b60  test    eax, eax
0x10032b62  jz      short loc_10032B96
0x10032b64  lea     ecx, [esp+550h+var_408]
0x10032b6b  lea     eax, [ecx+2]
0x10032b6e  mov     [esp+550h+var_530], eax
0x10032b72  mov     ax, [ecx]
0x10032b75  add     ecx, 2
0x10032b78  test    ax, ax
0x10032b7b  jnz     short loc_10032B72
0x10032b7d  sub     ecx, [esp+550h+var_530]
0x10032b81  add     esi, 4
0x10032b84  mov     eax, [esp+550h+var_52C]
0x10032b88  sar     ecx, 1
0x10032b8a  add     esi, ecx
0x10032b8c  mov     [esp+550h+var_530], esi
0x10032b90  mov     [eax], esi
0x10032b92  mov     eax, [esp+550h+var_538]
0x10032b96  mov     esi, [ebp+arg_20]
0x10032b99  cmp     [esp+550h+var_530], esi
0x10032b9d  jbe     short loc_10032BC7
0x10032b9f  push    _critJet; lpCriticalSection
0x10032ba5  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032bab  mov     eax, 0FFFFFBF2h
0x10032bb0  pop     edi
0x10032bb1  pop     esi
0x10032bb2  pop     ebx
0x10032bb3  mov     ecx, [esp+544h+var_4]
0x10032bba  xor     ecx, esp; StackCookie
0x10032bbc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032bc1  mov     esp, ebp
0x10032bc3  pop     ebp
0x10032bc4  retn    2Ch ; ','
0x10032bc7  xor     ecx, ecx
0x10032bc9  mov     [edx], cx
0x10032bcc  test    eax, eax
0x10032bce  jz      short loc_10032BFA
0x10032bd0  mov     eax, 5Bh ; '['
0x10032bd5  lea     ecx, [edx+2]
0x10032bd8  mov     [edx], ax
0x10032bdb  lea     eax, [esi-1]
0x10032bde  push    eax
0x10032bdf  lea     edx, [esp+554h+var_408]
0x10032be6  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10032beb  mov     ecx, [esp+550h+var_534]
0x10032bef  mov     edx, offset asc_10009938; "]."
0x10032bf4  push    esi
0x10032bf5  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10032bfa  mov     edx, [esp+550h+var_53C]
0x10032bfe  mov     ecx, [esp+550h+var_534]
0x10032c02  push    esi
0x10032c03  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10032c08  test    bl, 8
0x10032c0b  jz      short loc_10032C14
0x10032c0d  xor     esi, esi
0x10032c0f  jmp     loc_10032CCE
0x10032c14  push    edi
0x10032c15  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x10032c1a  mov     esi, eax
0x10032c1c  test    esi, esi
0x10032c1e  js      loc_10032CCE
0x10032c24  push    1; int
0x10032c26  push    1; int
0x10032c28  push    ebx; int
0x10032c29  push    [esp+55Ch+var_520]; int
0x10032c2d  push    [esp+560h+var_540]; int
0x10032c31  push    [esp+564h+var_524]; int
0x10032c35  push    [esp+568h+var_528]; int
0x10032c39  push    [esp+56Ch+var_53C]; int
0x10032c3d  push    0FFFFFFFFh; int
0x10032c3f  push    [esp+574h+var_544]; int
0x10032c43  push    edi; sesid
0x10032c44  call    _ErrDoCreateRelationship@44; ErrDoCreateRelationship(x,x,x,x,x,x,x,x,x,x,x)
0x10032c49  mov     esi, eax
0x10032c4b  mov     [esp+550h+var_524], esi
0x10032c4f  test    esi, esi
0x10032c51  js      short loc_10032C9D
0x10032c53  push    [esp+550h+var_540]; int
0x10032c57  mov     edx, [esp+554h+var_544]; unsigned int
0x10032c5b  mov     ecx, edi; Session *
0x10032c5d  push    [esp+554h+var_528]; int
0x10032c61  push    [esp+558h+var_53C]; int
0x10032c65  call    _ErrREPCreateRelationship@20; ErrREPCreateRelationship(x,x,x,x,x)
0x10032c6a  mov     esi, eax
0x10032c6c  test    bl, 2
0x10032c6f  jz      short loc_10032C89
0x10032c71  cmp     esi, 0FFFFB1D9h
0x10032c77  jz      short loc_10032C81
0x10032c79  cmp     esi, 0FFFFFAE7h
0x10032c7f  jnz     short loc_10032C89
0x10032c81  push    edi
0x10032c82  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10032c87  jmp     short loc_10032C8D
0x10032c89  test    esi, esi
0x10032c8b  js      short loc_10032CBF
0x10032c8d  push    0
0x10032c8f  push    edi
0x10032c90  call    _ErrIsamCommitTransaction@8; ErrIsamCommitTransaction(x,x)
0x10032c95  mov     esi, eax
0x10032c97  test    esi, esi
0x10032c99  jns     short loc_10032CC9
0x10032c9b  jmp     short loc_10032CBF
0x10032c9d  mov     eax, [esp+550h+var_544]
0x10032ca1  mov     eax, _rgrepdbinfo[eax*4]
0x10032ca8  mov     eax, [eax+0E4h]
0x10032cae  and     al, 3
0x10032cb0  cmp     al, 1
0x10032cb2  jnz     short loc_10032CBF
0x10032cb4  push    edi
0x10032cb5  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10032cba  mov     esi, 0FFFFB1DDh
0x10032cbf  push    0; char
0x10032cc1  push    edi; Session *
0x10032cc2  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10032cc7  test    esi, esi
0x10032cc9  cmovz   esi, [esp+550h+var_524]
0x10032cce  cmp     [esp+550h+var_538], 0
0x10032cd3  jz      short loc_10032CE1
0x10032cd5  push    0
0x10032cd7  push    [esp+554h+var_544]
0x10032cdb  push    edi
0x10032cdc  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10032ce1  test    esi, esi
0x10032ce3  jns     short loc_10032CF2
0x10032ce5  mov     eax, [esp+550h+var_534]
0x10032ce9  test    eax, eax
0x10032ceb  jz      short loc_10032CF2
0x10032ced  xor     ecx, ecx
0x10032cef  mov     [eax], cx
0x10032cf2  push    _critJet; lpCriticalSection
0x10032cf8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10032cfe  mov     eax, esi
0x10032d00  pop     edi
0x10032d01  pop     esi
0x10032d02  pop     ebx
0x10032d03  mov     ecx, [esp+544h+var_4]
0x10032d0a  xor     ecx, esp; StackCookie
0x10032d0c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032d11  mov     esp, ebp
0x10032d13  pop     ebp
0x10032d14  retn    2Ch ; ','
  ... truncated ...
```
