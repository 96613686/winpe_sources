# JetDeleteRelationship(x,x,x)

- ea: `0x10033bb0`
- end: `0x10033eea`
- name: `_JetDeleteRelationship@12`
- size: `826`
- prototype: `int __stdcall(Session *, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10017150`
- `0x1002d380`
- `0x10033bb0`
- `0x10033ef0`
- `0x10035ed0`
- `0x1003e7e0`
- `0x10042b60`
- `0x100433f0`
- `0x1004d920`
- `0x1004d9c0`
- `0x1004da20`
- `0x101170a0`
- `0x1011b3e8`
- `0x1011d1f2`
- `0x10123110`
- `0x10123b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10033ecc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10033bd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10033bd9`

## pseudocode

```c
int __stdcall JetDeleteRelationship(Session *sesid, unsigned int a2, int a3)
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
    v4 = ErrParseRelationshipName(Src);
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
0x10033bb0  mov     edi, edi
0x10033bb2  push    ebp
0x10033bb3  mov     ebp, esp
0x10033bb5  sub     esp, 2F0h
0x10033bbb  mov     eax, ___security_cookie
0x10033bc0  xor     eax, ebp
0x10033bc2  mov     [ebp+var_4], eax
0x10033bc5  mov     eax, [ebp+arg_4]
0x10033bc8  push    ebx
0x10033bc9  mov     ebx, [ebp+arg_8]
0x10033bcc  push    edi
0x10033bcd  push    _critJet; lpCriticalSection
0x10033bd3  mov     [ebp+var_28C], eax
0x10033bd9  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10033bdf  mov     edi, [ebp+sesid]
0x10033be2  push    edi
0x10033be3  call    _FValidSesid@4; FValidSesid(x)
0x10033be8  test    eax, eax
0x10033bea  jnz     short loc_10033C0F
0x10033bec  push    _critJet; lpCriticalSection
0x10033bf2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033bf8  pop     edi
0x10033bf9  mov     eax, 0FFFFFBB0h
0x10033bfe  pop     ebx
0x10033bff  mov     ecx, [ebp+var_4]
0x10033c02  xor     ecx, ebp; StackCookie
0x10033c04  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033c09  mov     esp, ebp
0x10033c0b  pop     ebp
0x10033c0c  retn    0Ch
0x10033c0f  push    esi
0x10033c10  mov     esi, [ebp+var_28C]
0x10033c16  cmp     esi, _dbidInit
0x10033c1c  jb      loc_10033EC6
0x10033c22  cmp     esi, 100h
0x10033c28  jnb     loc_10033EC6
0x10033c2e  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefInvalidDbid
0x10033c39  jz      loc_10033EC6
0x10033c3f  lea     eax, [ebp+Src]
0x10033c45  mov     ecx, ebx
0x10033c47  push    eax; void *
0x10033c48  lea     edx, [ebp+var_288]
0x10033c4e  call    ErrParseRelationshipName
0x10033c53  mov     ebx, eax
0x10033c55  test    ebx, ebx
0x10033c57  jns     short loc_10033C7A
0x10033c59  push    _critJet; lpCriticalSection
0x10033c5f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033c65  pop     esi
0x10033c66  pop     edi
0x10033c67  mov     eax, ebx
0x10033c69  pop     ebx
0x10033c6a  mov     ecx, [ebp+var_4]
0x10033c6d  xor     ecx, ebp; StackCookie
0x10033c6f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033c74  mov     esp, ebp
0x10033c76  pop     ebp
0x10033c77  retn    0Ch
0x10033c7a  lea     eax, [ebp+var_290]
0x10033c80  push    eax
0x10033c81  push    offset _wszRcObject; "Relationships"
0x10033c86  push    0
0x10033c88  push    esi
0x10033c89  push    edi
0x10033c8a  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10033c8f  test    eax, eax
0x10033c91  jns     short loc_10033CB7
0x10033c93  push    _critJet; lpCriticalSection
0x10033c99  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033c9f  pop     esi
0x10033ca0  pop     edi
0x10033ca1  mov     eax, 0FFFFFBD5h
0x10033ca6  pop     ebx
0x10033ca7  mov     ecx, [ebp+var_4]
0x10033caa  xor     ecx, ebp; StackCookie
0x10033cac  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033cb1  mov     esp, ebp
0x10033cb3  pop     ebp
0x10033cb4  retn    0Ch
0x10033cb7  cmp     [ebp+var_288], 0
0x10033cbf  jz      short loc_10033D07
0x10033cc1  push    0
0x10033cc3  lea     eax, [ebp+var_28C]
0x10033cc9  push    eax
0x10033cca  push    0
0x10033ccc  lea     eax, [ebp+var_288]
0x10033cd2  push    eax
0x10033cd3  push    edi
0x10033cd4  call    _ErrOpenDatabase@20; ErrOpenDatabase(x,x,x,x,x)
0x10033cd9  mov     esi, eax
0x10033cdb  test    esi, esi
0x10033cdd  js      loc_10033DB8
0x10033ce3  lea     eax, [ebp+var_290]
0x10033ce9  push    eax
0x10033cea  push    offset _wszRcObject; "Relationships"
0x10033cef  push    0
0x10033cf1  push    [ebp+var_28C]
0x10033cf7  push    edi
0x10033cf8  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10033cfd  mov     esi, eax
0x10033cff  test    esi, esi
0x10033d01  js      loc_10033DA4
0x10033d07  push    edi
0x10033d08  call    _ErrIsamBeginTransaction@4; ErrIsamBeginTransaction(x)
0x10033d0d  mov     esi, eax
0x10033d0f  test    esi, esi
0x10033d11  js      loc_10033DA4
0x10033d17  mov     ebx, [ebp+var_28C]
0x10033d1d  mov     eax, _rgrepdbinfo[ebx*4]
0x10033d24  mov     eax, [eax+0E4h]
0x10033d2a  mov     [ebp+var_298], eax
0x10033d30  test    al, 1
0x10033d32  jz      loc_10033E8C
0x10033d38  test    al, 10h
0x10033d3a  jnz     loc_10033E8C
0x10033d40  lea     eax, [ebp+var_29C]
0x10033d46  mov     edx, ebx
0x10033d48  push    eax; int
0x10033d49  lea     eax, [ebp+var_294]
0x10033d4f  mov     ecx, edi
0x10033d51  push    eax; int
0x10033d52  lea     eax, [ebp+Src]
0x10033d58  push    eax; Src
0x10033d59  push    offset _wszRcObject; "Relationships"
0x10033d5e  call    _ErrFObjectReplicable2@24; ErrFObjectReplicable2(x,x,x,x,x,x)
0x10033d63  mov     esi, eax
0x10033d65  test    esi, esi
0x10033d67  js      short loc_10033D9C
0x10033d69  cmp     [ebp+var_294], 0
0x10033d70  jz      loc_10033E86
0x10033d76  mov     eax, _rgrepdbinfo[ebx*4]
0x10033d7d  test    dword ptr [eax+0CCh], 10000h
0x10033d87  jnz     loc_10033E86
0x10033d8d  mov     eax, [ebp+var_298]
0x10033d93  test    al, 2
0x10033d95  jnz     short loc_10033DD9
0x10033d97  mov     esi, 0FFFFB1DDh
0x10033d9c  push    0; char
0x10033d9e  push    edi; Session *
0x10033d9f  call    _ErrIsamRollback@8; ErrIsamRollback(x,x)
0x10033da4  mov     eax, [ebp+var_28C]
0x10033daa  cmp     eax, [ebp+arg_4]
0x10033dad  jz      short loc_10033DB8
0x10033daf  push    0
0x10033db1  push    eax
0x10033db2  push    edi
0x10033db3  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10033db8  push    _critJet; lpCriticalSection
0x10033dbe  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033dc4  mov     eax, esi
0x10033dc6  pop     esi
0x10033dc7  pop     edi
0x10033dc8  pop     ebx
0x10033dc9  mov     ecx, [ebp+var_4]
0x10033dcc  xor     ecx, ebp; StackCookie
0x10033dce  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033dd3  mov     esp, ebp
0x10033dd5  pop     ebp
0x10033dd6  retn    0Ch
0x10033dd9  test    eax, 80000h
0x10033dde  jz      short loc_10033DE7
0x10033de0  mov     esi, 0FFFFB0ABh
0x10033de5  jmp     short loc_10033D9C
0x10033de7  push    48h ; 'H'; Size
0x10033de9  lea     eax, [ebp+var_2E4]
0x10033def  push    0; Val
0x10033df1  push    eax; void *
0x10033df2  call    _memset
0x10033df7  lea     eax, [ebp+Src]
0x10033dfd  mov     [ebp+var_2F0], 15h
0x10033e07  mov     ecx, eax
0x10033e09  mov     [ebp+var_2EC], eax
0x10033e0f  add     esp, 0Ch
0x10033e12  lea     edx, [ecx+2]
0x10033e15  mov     ax, [ecx]
0x10033e18  add     ecx, 2
0x10033e1b  test    ax, ax
0x10033e1e  jnz     short loc_10033E15
0x10033e20  sub     ecx, edx
0x10033e22  sar     ecx, 1
0x10033e24  lea     eax, [ecx+ecx]
0x10033e27  mov     [ebp+var_2E8], eax
0x10033e2d  lea     eax, [ebp+var_2F0]
0x10033e33  push    eax
0x10033e34  push    ebx
0x10033e35  push    edi
0x10033e36  call    _ErrReplSchChangeInsert@12; ErrReplSchChangeInsert(x,x,x)
0x10033e3b  mov     esi, eax
0x10033e3d  test    esi, esi
0x10033e3f  js      loc_10033D9C
0x10033e45  push    ebx
0x10033e46  push    edi
0x10033e47  call    _ErrRepSetLastSchema@8; ErrRepSetLastSchema(x,x)
0x10033e4c  mov     esi, eax
0x10033e4e  test    esi, esi
0x10033e50  js      loc_10033D9C
0x10033e56  push    80h; int
0x10033e5b  push    0Ah; int
0x10033e5d  push    2; Size
0x10033e5f  push    offset aT; "T"
0x10033e64  push    offset _WZReorderTables; "ReorderTables"
0x10033e69  push    0; void *
0x10033e6b  push    offset _wszDbObject; "MSysDb"
0x10033e70  push    offset _wszDcObject; "Databases"
0x10033e75  push    ebx; unsigned int
0x10033e76  push    edi; Session *
0x10033e77  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x10033e7c  mov     esi, eax
0x10033e7e  test    esi, esi
0x10033e80  js      loc_10033D9C
0x10033e86  mov     ebx, [ebp+var_28C]
0x10033e8c  push    1; int
0x10033e8e  lea     eax, [ebp+Src]
0x10033e94  push    eax; int
0x10033e95  push    0FFFFFFFFh; int
0x10033e97  push    ebx; int
0x10033e98  push    edi; sesid
0x10033e99  call    _ErrDoDeleteRelationship@20; ErrDoDeleteRelationship(x,x,x,x,x)
0x10033e9e  mov     esi, eax
0x10033ea0  mov     ebx, esi
0x10033ea2  test    esi, esi
0x10033ea4  js      loc_10033D9C
0x10033eaa  push    0
0x10033eac  push    edi
0x10033ead  call    _ErrIsamCommitTransaction@8; ErrIsamCommitTransaction(x,x)
0x10033eb2  mov     esi, eax
0x10033eb4  test    esi, esi
0x10033eb6  js      loc_10033D9C
0x10033ebc  test    eax, eax
0x10033ebe  cmovz   esi, ebx
0x10033ec1  jmp     loc_10033DA4
0x10033ec6  push    _critJet; lpCriticalSection
0x10033ecc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033ed2  mov     ecx, [ebp+var_4]
0x10033ed5  mov     eax, 0FFFFFC0Eh
0x10033eda  pop     esi
0x10033edb  pop     edi
0x10033edc  xor     ecx, ebp; StackCookie
0x10033ede  pop     ebx
0x10033edf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033ee4  mov     esp, ebp
0x10033ee6  pop     ebp
0x10033ee7  retn    0Ch
```
