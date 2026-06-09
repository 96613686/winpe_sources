# JetRenameColumn(x,x,x,x)

- ea: `0x1001ca10`
- end: `0x1001cd69`
- name: `_JetRenameColumn@16`
- size: `857`
- prototype: `int __stdcall(JET_SESID sesid, int, void *Src, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10012940`
- `0x100149f0`
- `0x10014be0`
- `0x10014d60`
- `0x1001ca10`
- `0x1002d1d0`
- `0x1002f1f0`
- `0x10031dd0`
- `0x100352b0`
- `0x1003e650`
- `0x1003e870`
- `0x10044250`
- `0x100447a0`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ca58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cabf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cd4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ca58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cabf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cd4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ca3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001ca3f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cbd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cc89`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cbd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cc89`

## pseudocode

```c
JET_ERR __stdcall JetRenameColumn(Session *sesid, unsigned int a2, void *Src, void *a4)
{
  int v5; // ebx
  JET_ERR TableInfo; // esi
  unsigned int i; // ebx
  JET_ERR v8; // eax
  void *v9; // edx
  unsigned int k; // ebx
  int v11; // eax
  int j; // eax
  int v13; // eax
  int v14; // [esp+8h] [ebp-2A4h] BYREF
  _BYTE v15[4]; // [esp+10h] [ebp-29Ch] BYREF
  unsigned int v16; // [esp+14h] [ebp-298h]
  int v17; // [esp+18h] [ebp-294h] BYREF
  void *v18; // [esp+1Ch] [ebp-290h]
  void *v19; // [esp+20h] [ebp-28Ch]
  _WORD v20[256]; // [esp+24h] [ebp-288h] BYREF
  int v21[33]; // [esp+224h] [ebp-88h] BYREF

  v18 = Src;
  v19 = a4;
  EnterCriticalSection(critJet);
  if ( !FValidSesid((int)sesid) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  v5 = a2;
  if ( a2 < 0x800
    && a2 >= tableidInit
    && (char *)dword_1016362C[4 * a2] != &vtfndefInvalidTableid
    && (dword_10163628[4 * a2] & 8) == 0 )
  {
    UtilSetErrorInfoReal((int)sesid, (const unsigned __int16 *)Src, 0, 0, -8170, 0, 0, 0);
    LeaveCriticalSection(critJet);
    return -1907;
  }
  TableInfo = ErrDispGetTableInfo(sesid, a2, v21, 130, 1);
  if ( TableInfo >= 0 )
  {
    TableInfo = ErrDispGetTableInfo(sesid, a2, &v14, 8, 2);
    if ( TableInfo >= 0 )
    {
      TableInfo = JetBeginTransaction((JET_SESID)sesid);
      if ( TableInfo >= 0 )
      {
        TableInfo = ErrDispRenameColumn(sesid, a2, v18, v19);
        if ( TableInfo >= 0 )
        {
          v17 = 0;
          v16 = dword_10131530[25 * a2];
          if ( (*((_BYTE *)*(&rgrepdbinfo + v16) + 228) & 0x20) != 0 )
          {
LABEL_37:
            TableInfo = ErrRefreshSubObjectProperties((int)sesid, -1, v5, (int)L"Tables", 0, v18, v19, 0);
            if ( TableInfo >= 0 )
            {
              TableInfo = ErrRelationshipUpdateNames(sesid, v14, (int)v21, 0, (int)v18, (const unsigned __int16 *)v19);
              if ( TableInfo >= 0 )
              {
                TableInfo = JetCommitTransaction((JET_SESID)sesid, 0);
                if ( TableInfo >= 0 )
                  goto LABEL_41;
              }
            }
            goto LABEL_40;
          }
          for ( i = 0; i < 0x78; ++i )
          {
            v8 = JetIRetrieveTableProperty(sesid, a2, 0, L"ColIsGuid", v20, 510, &v17, v15, 128, 0);
            TableInfo = v8;
            if ( v8 != -1106 && v8 != -1105 && v8 != -1102 )
              break;
            Sleep(0x1F4u);
          }
          if ( TableInfo < 0 )
          {
            if ( TableInfo == -3602 || TableInfo == -3600 )
            {
              for ( j = isibHead; j != -1; j = dword_1016EAE8[26 * j] )
              {
                if ( (Session *)rgsib[26 * j] == sesid )
                  break;
              }
              v13 = 26 * j;
              if ( !dword_1016EACC[v13] )
                dword_1016EAB0[v13] = 1055;
              TableInfo = 0;
            }
          }
          else if ( v17 )
          {
            v9 = v18;
            *(_WORD *)((char *)v20 + v17) = 0;
            if ( WCSICMP(v20, v9) )
            {
LABEL_36:
              v5 = a2;
              goto LABEL_37;
            }
            for ( k = 0; k < 0x78; ++k )
            {
              v11 = JetISetProperty(
                      sesid,
                      v16,
                      (int)L"Tables",
                      (int)v21,
                      0,
                      L"ColIsGuid",
                      v19,
                      2 * wcslen((const unsigned __int16 *)v19),
                      10,
                      128);
              TableInfo = v11;
              if ( v11 != -1106 && v11 != -1105 && v11 != -1102 )
                break;
              Sleep(0x1F4u);
            }
          }
          if ( TableInfo >= 0 )
            goto LABEL_36;
        }
LABEL_40:
        ErrRollback(sesid, 0);
      }
    }
  }
LABEL_41:
  LeaveCriticalSection(critJet);
  return TableInfo;
}

```

## disassembly

```asm
0x1001ca10  mov     edi, edi
0x1001ca12  push    ebp
0x1001ca13  mov     ebp, esp
0x1001ca15  sub     esp, 2A4h
0x1001ca1b  mov     eax, ___security_cookie
0x1001ca20  xor     eax, ebp
0x1001ca22  mov     [ebp+var_4], eax
0x1001ca25  mov     eax, [ebp+arg_C]
0x1001ca28  push    esi
0x1001ca29  mov     esi, [ebp+Src]
0x1001ca2c  push    edi
0x1001ca2d  push    _critJet; lpCriticalSection
0x1001ca33  mov     [ebp+var_290], esi
0x1001ca39  mov     [ebp+var_28C], eax
0x1001ca3f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001ca45  mov     edi, [ebp+sesid]
0x1001ca48  push    edi
0x1001ca49  call    _FValidSesid@4; FValidSesid(x)
0x1001ca4e  test    eax, eax
0x1001ca50  jnz     short loc_1001CA75
0x1001ca52  push    _critJet; lpCriticalSection
0x1001ca58  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001ca5e  pop     edi
0x1001ca5f  mov     eax, 0FFFFFBB0h
0x1001ca64  pop     esi
0x1001ca65  mov     ecx, [ebp+var_4]
0x1001ca68  xor     ecx, ebp; StackCookie
0x1001ca6a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ca6f  mov     esp, ebp
0x1001ca71  pop     ebp
0x1001ca72  retn    10h
0x1001ca75  push    ebx
0x1001ca76  mov     ebx, [ebp+arg_4]
0x1001ca79  cmp     ebx, 800h
0x1001ca7f  jnb     short loc_1001CADD
0x1001ca81  cmp     ebx, _tableidInit
0x1001ca87  jb      short loc_1001CADD
0x1001ca89  mov     eax, ebx
0x1001ca8b  shl     eax, 4
0x1001ca8e  cmp     dword_1016362C[eax], offset _vtfndefInvalidTableid
0x1001ca98  jz      short loc_1001CADD
0x1001ca9a  test    byte ptr dword_10163628[eax], 8
0x1001caa1  jnz     short loc_1001CADD
0x1001caa3  push    0; int
0x1001caa5  push    0; int
0x1001caa7  push    0; int
0x1001caa9  push    0FFFFE016h; int
0x1001caae  push    0; void *
0x1001cab0  push    0; void *
0x1001cab2  push    esi; Src
0x1001cab3  push    edi; int
0x1001cab4  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001cab9  push    _critJet; lpCriticalSection
0x1001cabf  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cac5  pop     ebx
0x1001cac6  pop     edi
0x1001cac7  mov     eax, 0FFFFF88Dh
0x1001cacc  pop     esi
0x1001cacd  mov     ecx, [ebp+var_4]
0x1001cad0  xor     ecx, ebp; StackCookie
0x1001cad2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cad7  mov     esp, ebp
0x1001cad9  pop     ebp
0x1001cada  retn    10h
0x1001cadd  push    1
0x1001cadf  push    82h
0x1001cae4  lea     eax, [ebp+var_88]
0x1001caea  push    eax
0x1001caeb  push    ebx
0x1001caec  push    edi
0x1001caed  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x1001caf2  mov     esi, eax
0x1001caf4  test    esi, esi
0x1001caf6  js      loc_1001CD48
0x1001cafc  push    2
0x1001cafe  push    8
0x1001cb00  lea     eax, [ebp+var_2A4]
0x1001cb06  push    eax
0x1001cb07  push    ebx
0x1001cb08  push    edi
0x1001cb09  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x1001cb0e  mov     esi, eax
0x1001cb10  test    esi, esi
0x1001cb12  js      loc_1001CD48
0x1001cb18  push    edi; sesid
0x1001cb19  call    _JetBeginTransaction@4; JetBeginTransaction(x)
0x1001cb1e  mov     esi, eax
0x1001cb20  test    esi, esi
0x1001cb22  js      loc_1001CD48
0x1001cb28  push    [ebp+var_28C]
0x1001cb2e  push    [ebp+var_290]
0x1001cb34  push    ebx
0x1001cb35  push    edi
0x1001cb36  call    _ErrDispRenameColumn@16; ErrDispRenameColumn(x,x,x,x)
0x1001cb3b  mov     esi, eax
0x1001cb3d  test    esi, esi
0x1001cb3f  js      loc_1001CD3F
0x1001cb45  imul    eax, ebx, 64h ; 'd'
0x1001cb48  mov     [ebp+var_294], 0
0x1001cb52  mov     eax, dword_10131530[eax]
0x1001cb58  mov     [ebp+var_298], eax
0x1001cb5e  mov     eax, _rgrepdbinfo[eax*4]
0x1001cb65  test    byte ptr [eax+0E4h], 20h
0x1001cb6c  jnz     loc_1001CCE6
0x1001cb72  xor     ebx, ebx
0x1001cb74  nop     dword ptr [eax+00h]
0x1001cb78  nop     dword ptr [eax+eax+00000000h]
0x1001cb80  push    0
0x1001cb82  push    80h
0x1001cb87  lea     eax, [ebp+var_29C]
0x1001cb8d  push    eax
0x1001cb8e  lea     eax, [ebp+var_294]
0x1001cb94  push    eax
0x1001cb95  push    1FEh
0x1001cb9a  lea     eax, [ebp+var_288]
0x1001cba0  push    eax
0x1001cba1  push    offset _WZColIsGuid; "ColIsGuid"
0x1001cba6  push    0
0x1001cba8  push    [ebp+arg_4]
0x1001cbab  push    edi
0x1001cbac  call    _JetIRetrieveTableProperty@40; JetIRetrieveTableProperty(x,x,x,x,x,x,x,x,x,x)
0x1001cbb1  mov     esi, eax
0x1001cbb3  cmp     esi, 0FFFFFBAEh
0x1001cbb9  jz      short loc_1001CBCB
0x1001cbbb  cmp     esi, 0FFFFFBAFh
0x1001cbc1  jz      short loc_1001CBCB
0x1001cbc3  cmp     esi, 0FFFFFBB2h
0x1001cbc9  jnz     short loc_1001CBDC
0x1001cbcb  push    1F4h; dwMilliseconds
0x1001cbd0  call    ds:__imp__Sleep@4; Sleep(x)
0x1001cbd6  inc     ebx
0x1001cbd7  cmp     ebx, 78h ; 'x'
0x1001cbda  jb      short loc_1001CB80
0x1001cbdc  test    esi, esi
0x1001cbde  js      loc_1001CC97
0x1001cbe4  mov     eax, [ebp+var_294]
0x1001cbea  test    eax, eax
0x1001cbec  jz      loc_1001CCDF
0x1001cbf2  mov     edx, [ebp+var_290]
0x1001cbf8  xor     ecx, ecx
0x1001cbfa  mov     [ebp+eax+var_288], cx
0x1001cc02  lea     ecx, [ebp+var_288]
0x1001cc08  call    _WCSICMP@8; WCSICMP(x,x)
0x1001cc0d  test    eax, eax
0x1001cc0f  jnz     loc_1001CCE3
0x1001cc15  xor     ebx, ebx
0x1001cc17  nop     word ptr [eax+eax+00000000h]
0x1001cc20  mov     esi, [ebp+var_28C]
0x1001cc26  mov     ecx, esi
0x1001cc28  lea     edx, [ecx+2]
0x1001cc2b  nop     dword ptr [eax+eax+00h]
0x1001cc30  mov     ax, [ecx]
0x1001cc33  add     ecx, 2
0x1001cc36  test    ax, ax
0x1001cc39  jnz     short loc_1001CC30
0x1001cc3b  push    80h; int
0x1001cc40  sub     ecx, edx
0x1001cc42  push    0Ah; int
0x1001cc44  sar     ecx, 1
0x1001cc46  lea     eax, [ecx+ecx]
0x1001cc49  push    eax; Size
0x1001cc4a  push    esi; void *
0x1001cc4b  push    offset _WZColIsGuid; "ColIsGuid"
0x1001cc50  push    0; void *
0x1001cc52  lea     eax, [ebp+var_88]
0x1001cc58  push    eax; int
0x1001cc59  push    offset _wszTcObject; "Tables"
0x1001cc5e  push    [ebp+var_298]; unsigned int
0x1001cc64  push    edi; Session *
0x1001cc65  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x1001cc6a  mov     esi, eax
0x1001cc6c  cmp     esi, 0FFFFFBAEh
0x1001cc72  jz      short loc_1001CC84
0x1001cc74  cmp     esi, 0FFFFFBAFh
0x1001cc7a  jz      short loc_1001CC84
0x1001cc7c  cmp     esi, 0FFFFFBB2h
0x1001cc82  jnz     short loc_1001CCDF
0x1001cc84  push    1F4h; dwMilliseconds
0x1001cc89  call    ds:__imp__Sleep@4; Sleep(x)
0x1001cc8f  inc     ebx
0x1001cc90  cmp     ebx, 78h ; 'x'
0x1001cc93  jb      short loc_1001CC20
0x1001cc95  jmp     short loc_1001CCDF
0x1001cc97  cmp     esi, 0FFFFF1EEh
0x1001cc9d  jz      short loc_1001CCA7
0x1001cc9f  cmp     esi, 0FFFFF1F0h
0x1001cca5  jnz     short loc_1001CCDF
0x1001cca7  mov     eax, _isibHead
0x1001ccac  cmp     eax, 0FFFFFFFFh
0x1001ccaf  jz      short loc_1001CCC7
0x1001ccb1  imul    ecx, eax, 68h ; 'h'
0x1001ccb4  cmp     _rgsib[ecx], edi
0x1001ccba  jz      short loc_1001CCC7
0x1001ccbc  mov     eax, dword_1016EAE8[ecx]
0x1001ccc2  cmp     eax, 0FFFFFFFFh
0x1001ccc5  jnz     short loc_1001CCB1
0x1001ccc7  imul    eax, 68h ; 'h'
0x1001ccca  cmp     dword_1016EACC[eax], 0
0x1001ccd1  jnz     short loc_1001CCDD
0x1001ccd3  mov     dword_1016EAB0[eax], 41Fh
0x1001ccdd  xor     esi, esi
0x1001ccdf  test    esi, esi
0x1001cce1  js      short loc_1001CD3F
0x1001cce3  mov     ebx, [ebp+arg_4]
0x1001cce6  push    0; int
0x1001cce8  push    [ebp+var_28C]; Src
0x1001ccee  push    [ebp+var_290]; void *
0x1001ccf4  push    0; int
0x1001ccf6  push    offset _wszTcObject; "Tables"
0x1001ccfb  push    ebx; int
0x1001ccfc  push    0FFFFFFFFh; int
0x1001ccfe  push    edi; int
0x1001ccff  call    _ErrRefreshSubObjectProperties@32; ErrRefreshSubObjectProperties(x,x,x,x,x,x,x,x)
0x1001cd04  mov     esi, eax
0x1001cd06  test    esi, esi
0x1001cd08  js      short loc_1001CD3F
0x1001cd0a  push    [ebp+var_28C]; int
0x1001cd10  lea     eax, [ebp+var_88]
0x1001cd16  push    [ebp+var_290]; int
0x1001cd1c  push    0; int
0x1001cd1e  push    eax; int
0x1001cd1f  push    [ebp+var_2A4]; int
0x1001cd25  push    edi; sesid
0x1001cd26  call    _ErrRelationshipUpdateNames@24; ErrRelationshipUpdateNames(x,x,x,x,x,x)
0x1001cd2b  mov     esi, eax
0x1001cd2d  test    esi, esi
0x1001cd2f  js      short loc_1001CD3F
0x1001cd31  push    0; grbit
0x1001cd33  push    edi; sesid
0x1001cd34  call    _JetCommitTransaction@8; JetCommitTransaction(x,x)
0x1001cd39  mov     esi, eax
0x1001cd3b  test    esi, esi
0x1001cd3d  jns     short loc_1001CD48
0x1001cd3f  xor     edx, edx; char
0x1001cd41  mov     ecx, edi; Session *
0x1001cd43  call    _ErrRollback@8; ErrRollback(x,x)
0x1001cd48  push    _critJet; lpCriticalSection
0x1001cd4e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cd54  mov     ecx, [ebp+var_4]
0x1001cd57  mov     eax, esi
0x1001cd59  pop     ebx
0x1001cd5a  pop     edi
0x1001cd5b  xor     ecx, ebp; StackCookie
0x1001cd5d  pop     esi
0x1001cd5e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cd63  mov     esp, ebp
0x1001cd65  pop     ebp
0x1001cd66  retn    10h
```
