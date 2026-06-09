# JetDeleteRelationship(x,x,x)

- ea: `0x10033a10`
- end: `0x10033d4a`
- name: `_JetDeleteRelationship@12`
- size: `826`
- prototype: `int __stdcall(Session *, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10017010`
- `0x1002d1d0`
- `0x10033a10`
- `0x10033d50`
- `0x10035d30`
- `0x1003e650`
- `0x100429d0`
- `0x10043260`
- `0x1004d790`
- `0x1004d830`
- `0x1004d890`
- `0x10116ef0`
- `0x1011b238`
- `0x1011d044`
- `0x10122f60`
- `0x1012398c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033d2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033d2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10033a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10033a39`

## pseudocode

```c
int __stdcall JetDeleteRelationship(Session *sesid, unsigned int a2, char *a3)
{
  int v4; // ebx
  int ObjidFromName; // esi
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  _DWORD v10[21]; // [esp+8h] [ebp-2F0h] BYREF
  int v11; // [esp+5Ch] [ebp-29Ch] BYREF
  int v12; // [esp+60h] [ebp-298h]
  int v13; // [esp+64h] [ebp-294h] BYREF
  _BYTE v14[4]; // [esp+68h] [ebp-290h] BYREF
  unsigned int v15; // [esp+6Ch] [ebp-28Ch] BYREF
  wchar_t v16[256]; // [esp+70h] [ebp-288h] BYREF
  unsigned __int16 Src[66]; // [esp+270h] [ebp-88h] BYREF

  v15 = a2;
  EnterCriticalSection(critJet);
  if ( !FValidSesid((int)sesid) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  if ( v15 >= dbidInit && v15 < 0x100 && (int *)mpdbidpvdbfndef[v15] != vdbfndefInvalidDbid )
  {
    v4 = ErrParseRelationshipName(a3, v16, Src);
    if ( v4 < 0 )
    {
      LeaveCriticalSection(critJet);
      return v4;
    }
    if ( (int)ErrDispGetObjidFromName(sesid, v15, 0, L"Relationships", v14) < 0 )
    {
      LeaveCriticalSection(critJet);
      return -1067;
    }
    if ( v16[0] )
    {
      ObjidFromName = ErrOpenDatabase((int)sesid, v16, 0, (int)&v15, 0);
      if ( ObjidFromName < 0 )
      {
LABEL_24:
        LeaveCriticalSection(critJet);
        return ObjidFromName;
      }
      ObjidFromName = ErrDispGetObjidFromName(sesid, v15, 0, L"Relationships", v14);
      if ( ObjidFromName < 0 )
        goto LABEL_22;
    }
    ObjidFromName = ErrIsamBeginTransaction(sesid);
    if ( ObjidFromName < 0 )
    {
LABEL_22:
      if ( v15 != a2 )
        ErrDispCloseDatabase(sesid, v15, 0);
      goto LABEL_24;
    }
    v6 = v15;
    v7 = *((_DWORD *)*(&rgrepdbinfo + v15) + 57);
    v12 = v7;
    if ( (v7 & 1) != 0 && (v7 & 0x10) == 0 )
    {
      ObjidFromName = ErrFObjectReplicable2((int)L"Relationships", Src, (int)&v13, (int)&v11);
      if ( ObjidFromName < 0 )
      {
LABEL_21:
        ErrIsamRollback(sesid, 0);
        goto LABEL_22;
      }
      if ( v13 && (*((_DWORD *)*(&rgrepdbinfo + v6) + 51) & 0x10000) == 0 )
      {
        if ( (v12 & 2) == 0 )
        {
          ObjidFromName = -20003;
          goto LABEL_21;
        }
        if ( (v12 & 0x80000) != 0 )
        {
          ObjidFromName = -20309;
          goto LABEL_21;
        }
        memset(&v10[3], 0, 0x48u);
        v10[0] = 21;
        v10[1] = Src;
        v10[2] = 2 * wcslen(Src);
        ObjidFromName = ErrReplSchChangeInsert(sesid, v6, v10);
        if ( ObjidFromName < 0 )
          goto LABEL_21;
        ObjidFromName = ErrRepSetLastSchema(sesid, v6);
        if ( ObjidFromName < 0 )
          goto LABEL_21;
        ObjidFromName = JetISetProperty(
                          sesid,
                          v6,
                          (int)L"Databases",
                          (int)L"MSysDb",
                          0,
                          L"ReorderTables",
                          L"T",
                          2u,
                          10,
                          128);
        if ( ObjidFromName < 0 )
          goto LABEL_21;
      }
      v6 = v15;
    }
    ObjidFromName = ErrDoDeleteRelationship(sesid, v6, -1, Src, 1);
    v8 = ObjidFromName;
    if ( ObjidFromName >= 0 )
    {
      v9 = ErrIsamCommitTransaction(sesid, 0);
      ObjidFromName = v9;
      if ( v9 >= 0 )
      {
        if ( !v9 )
          ObjidFromName = v8;
        goto LABEL_22;
      }
    }
    goto LABEL_21;
  }
  LeaveCriticalSection(critJet);
  return -1010;
}

```

## disassembly

```asm
0x10033a10  mov     edi, edi
0x10033a12  push    ebp
0x10033a13  mov     ebp, esp
0x10033a15  sub     esp, 2F0h
0x10033a1b  mov     eax, ___security_cookie
0x10033a20  xor     eax, ebp
0x10033a22  mov     [ebp+var_4], eax
0x10033a25  mov     eax, [ebp+arg_4]
0x10033a28  push    ebx
0x10033a29  mov     ebx, [ebp+arg_8]
0x10033a2c  push    edi
0x10033a2d  push    _critJet; lpCriticalSection
0x10033a33  mov     [ebp+var_28C], eax
0x10033a39  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10033a3f  mov     edi, [ebp+sesid]
0x10033a42  push    edi
0x10033a43  call    _FValidSesid@4; FValidSesid(x)
0x10033a48  test    eax, eax
0x10033a4a  jnz     short loc_10033A6F
0x10033a4c  push    _critJet; lpCriticalSection
0x10033a52  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033a58  pop     edi
0x10033a59  mov     eax, 0FFFFFBB0h
0x10033a5e  pop     ebx
0x10033a5f  mov     ecx, [ebp+var_4]
0x10033a62  xor     ecx, ebp; StackCookie
0x10033a64  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033a69  mov     esp, ebp
0x10033a6b  pop     ebp
0x10033a6c  retn    0Ch
0x10033a6f  push    esi
0x10033a70  mov     esi, [ebp+var_28C]
0x10033a76  cmp     esi, _dbidInit
0x10033a7c  jb      loc_10033D26
0x10033a82  cmp     esi, 100h
0x10033a88  jnb     loc_10033D26
0x10033a8e  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefInvalidDbid
0x10033a99  jz      loc_10033D26
0x10033a9f  lea     eax, [ebp+Src]
0x10033aa5  mov     ecx, ebx
0x10033aa7  push    eax; void *
0x10033aa8  lea     edx, [ebp+var_288]
0x10033aae  call    ErrParseRelationshipName
0x10033ab3  mov     ebx, eax
0x10033ab5  test    ebx, ebx
0x10033ab7  jns     short loc_10033ADA
0x10033ab9  push    _critJet; lpCriticalSection
0x10033abf  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033ac5  pop     esi
0x10033ac6  pop     edi
0x10033ac7  mov     eax, ebx
0x10033ac9  pop     ebx
0x10033aca  mov     ecx, [ebp+var_4]
0x10033acd  xor     ecx, ebp; StackCookie
0x10033acf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033ad4  mov     esp, ebp
0x10033ad6  pop     ebp
0x10033ad7  retn    0Ch
0x10033ada  lea     eax, [ebp+var_290]
0x10033ae0  push    eax
0x10033ae1  push    offset _wszRcObject; "Relationships"
0x10033ae6  push    0
0x10033ae8  push    esi
0x10033ae9  push    edi
0x10033aea  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10033aef  test    eax, eax
0x10033af1  jns     short loc_10033B17
0x10033af3  push    _critJet; lpCriticalSection
0x10033af9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033aff  pop     esi
0x10033b00  pop     edi
0x10033b01  mov     eax, 0FFFFFBD5h
0x10033b06  pop     ebx
0x10033b07  mov     ecx, [ebp+var_4]
0x10033b0a  xor     ecx, ebp; StackCookie
0x10033b0c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033b11  mov     esp, ebp
0x10033b13  pop     ebp
0x10033b14  retn    0Ch
0x10033b17  cmp     [ebp+var_288], 0
0x10033b1f  jz      short loc_10033B67
0x10033b21  push    0
0x10033b23  lea     eax, [ebp+var_28C]
0x10033b29  push    eax
0x10033b2a  push    0
0x10033b2c  lea     eax, [ebp+var_288]
0x10033b32  push    eax
0x10033b33  push    edi
0x10033b34  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x10033b39  mov     esi, eax
0x10033b3b  test    esi, esi
0x10033b3d  js      loc_10033C18
0x10033b43  lea     eax, [ebp+var_290]
0x10033b49  push    eax
0x10033b4a  push    offset _wszRcObject; "Relationships"
0x10033b4f  push    0
0x10033b51  push    [ebp+var_28C]
0x10033b57  push    edi
0x10033b58  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10033b5d  mov     esi, eax
0x10033b5f  test    esi, esi
0x10033b61  js      loc_10033C04
0x10033b67  push    edi
0x10033b68  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x10033b6d  mov     esi, eax
0x10033b6f  test    esi, esi
0x10033b71  js      loc_10033C04
0x10033b77  mov     ebx, [ebp+var_28C]
0x10033b7d  mov     eax, _rgrepdbinfo[ebx*4]
0x10033b84  mov     eax, [eax+0E4h]
0x10033b8a  mov     [ebp+var_298], eax
0x10033b90  test    al, 1
0x10033b92  jz      loc_10033CEC
0x10033b98  test    al, 10h
0x10033b9a  jnz     loc_10033CEC
0x10033ba0  lea     eax, [ebp+var_29C]
0x10033ba6  mov     edx, ebx
0x10033ba8  push    eax; int
0x10033ba9  lea     eax, [ebp+var_294]
0x10033baf  mov     ecx, edi
0x10033bb1  push    eax; int
0x10033bb2  lea     eax, [ebp+Src]
0x10033bb8  push    eax; Src
0x10033bb9  push    offset _wszRcObject; "Relationships"
0x10033bbe  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10033bc3  mov     esi, eax
0x10033bc5  test    esi, esi
0x10033bc7  js      short loc_10033BFC
0x10033bc9  cmp     [ebp+var_294], 0
0x10033bd0  jz      loc_10033CE6
0x10033bd6  mov     eax, _rgrepdbinfo[ebx*4]
0x10033bdd  test    dword ptr [eax+0CCh], 10000h
0x10033be7  jnz     loc_10033CE6
0x10033bed  mov     eax, [ebp+var_298]
0x10033bf3  test    al, 2
0x10033bf5  jnz     short loc_10033C39
0x10033bf7  mov     esi, 0FFFFB1DDh
0x10033bfc  push    0; char
0x10033bfe  push    edi; Session *
0x10033bff  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10033c04  mov     eax, [ebp+var_28C]
0x10033c0a  cmp     eax, [ebp+arg_4]
0x10033c0d  jz      short loc_10033C18
0x10033c0f  push    0
0x10033c11  push    eax
0x10033c12  push    edi
0x10033c13  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10033c18  push    _critJet; lpCriticalSection
0x10033c1e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033c24  mov     eax, esi
0x10033c26  pop     esi
0x10033c27  pop     edi
0x10033c28  pop     ebx
0x10033c29  mov     ecx, [ebp+var_4]
0x10033c2c  xor     ecx, ebp; StackCookie
0x10033c2e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033c33  mov     esp, ebp
0x10033c35  pop     ebp
0x10033c36  retn    0Ch
0x10033c39  test    eax, 80000h
0x10033c3e  jz      short loc_10033C47
0x10033c40  mov     esi, 0FFFFB0ABh
0x10033c45  jmp     short loc_10033BFC
0x10033c47  push    48h ; 'H'; Size
0x10033c49  lea     eax, [ebp+var_2E4]
0x10033c4f  push    0; Val
0x10033c51  push    eax; void *
0x10033c52  call    _memset
0x10033c57  lea     eax, [ebp+Src]
0x10033c5d  mov     [ebp+var_2F0], 15h
0x10033c67  mov     ecx, eax
0x10033c69  mov     [ebp+var_2EC], eax
0x10033c6f  add     esp, 0Ch
0x10033c72  lea     edx, [ecx+2]
0x10033c75  mov     ax, [ecx]
0x10033c78  add     ecx, 2
0x10033c7b  test    ax, ax
0x10033c7e  jnz     short loc_10033C75
0x10033c80  sub     ecx, edx
0x10033c82  sar     ecx, 1
0x10033c84  lea     eax, [ecx+ecx]
0x10033c87  mov     [ebp+var_2E8], eax
0x10033c8d  lea     eax, [ebp+var_2F0]
0x10033c93  push    eax
0x10033c94  push    ebx
0x10033c95  push    edi
0x10033c96  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x10033c9b  mov     esi, eax
0x10033c9d  test    esi, esi
0x10033c9f  js      loc_10033BFC
0x10033ca5  push    ebx
0x10033ca6  push    edi
0x10033ca7  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x10033cac  mov     esi, eax
0x10033cae  test    esi, esi
0x10033cb0  js      loc_10033BFC
0x10033cb6  push    80h; int
0x10033cbb  push    0Ah; int
0x10033cbd  push    2; Size
0x10033cbf  push    offset aT; "T"
0x10033cc4  push    offset _WZReorderTables; "ReorderTables"
0x10033cc9  push    0; void *
0x10033ccb  push    offset _wszDbObject; "MSysDb"
0x10033cd0  push    offset _wszDcObject; "Databases"
0x10033cd5  push    ebx; unsigned int
0x10033cd6  push    edi; Session *
0x10033cd7  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x10033cdc  mov     esi, eax
0x10033cde  test    esi, esi
0x10033ce0  js      loc_10033BFC
0x10033ce6  mov     ebx, [ebp+var_28C]
0x10033cec  push    1; int
0x10033cee  lea     eax, [ebp+Src]
0x10033cf4  push    eax; int
0x10033cf5  push    0FFFFFFFFh; int
0x10033cf7  push    ebx; int
0x10033cf8  push    edi; sesid
0x10033cf9  call    _ErrDoDeleteRelationship@20; ErrDoDeleteRelationship(x,x,x,x,x)
0x10033cfe  mov     esi, eax
0x10033d00  mov     ebx, esi
0x10033d02  test    esi, esi
0x10033d04  js      loc_10033BFC
0x10033d0a  push    0
0x10033d0c  push    edi
0x10033d0d  call    _ErrIsamCommitTransaction@8; ErrIsamCommitTransaction(x,x)
0x10033d12  mov     esi, eax
0x10033d14  test    esi, esi
0x10033d16  js      loc_10033BFC
0x10033d1c  test    eax, eax
0x10033d1e  cmovz   esi, ebx
0x10033d21  jmp     loc_10033C04
0x10033d26  push    _critJet; lpCriticalSection
0x10033d2c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033d32  mov     ecx, [ebp+var_4]
0x10033d35  mov     eax, 0FFFFFC0Eh
0x10033d3a  pop     esi
0x10033d3b  pop     edi
0x10033d3c  xor     ecx, ebp; StackCookie
0x10033d3e  pop     ebx
0x10033d3f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033d44  mov     esp, ebp
0x10033d46  pop     ebp
0x10033d47  retn    0Ch
```
