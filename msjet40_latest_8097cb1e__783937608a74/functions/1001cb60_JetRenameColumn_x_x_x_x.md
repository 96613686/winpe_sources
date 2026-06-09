# JetRenameColumn(x,x,x,x)

- ea: `0x1001cb60`
- end: `0x1001ceb9`
- name: `_JetRenameColumn@16`
- size: `857`
- prototype: `int __stdcall(JET_SESID sesid, int, void *Src, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x10012a80`
- `0x10014b30`
- `0x10014d20`
- `0x10014ea0`
- `0x1001cb60`
- `0x1002d380`
- `0x1002f390`
- `0x10031f70`
- `0x10035450`
- `0x1003e7e0`
- `0x1003ea00`
- `0x100443d0`
- `0x10044920`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cba8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cc0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ce9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cba8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001cc0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001ce9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001cb8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001cb8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cd20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cdd9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cd20`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1001cdd9`

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
  char v15[4]; // [esp+10h] [ebp-29Ch] BYREF
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
    && (char *)dword_101636CC[4 * a2] != &vtfndefInvalidTableid
    && (dword_101636C8[4 * a2] & 8) == 0 )
  {
    UtilSetErrorInfoReal((int)sesid, Src, 0, 0, -8170, 0, 0, 0);
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
          v16 = dword_101315D0[25 * a2];
          if ( (*((_BYTE *)*(&rgrepdbinfo + v16) + 228) & 0x20) != 0 )
          {
LABEL_37:
            TableInfo = ErrRefreshSubObjectProperties(
                          (int)sesid,
                          -1,
                          v5,
                          (int)L"Tables",
                          0,
                          v18,
                          (const unsigned __int16 *)v19,
                          0);
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
              for ( j = isibHead; j != -1; j = dword_1016EB88[26 * j] )
              {
                if ( (Session *)rgsib[26 * j] == sesid )
                  break;
              }
              v13 = 26 * j;
              if ( !dword_1016EB6C[v13] )
                dword_1016EB50[v13] = 1055;
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
0x1001cb60  mov     edi, edi
0x1001cb62  push    ebp
0x1001cb63  mov     ebp, esp
0x1001cb65  sub     esp, 2A4h
0x1001cb6b  mov     eax, ___security_cookie
0x1001cb70  xor     eax, ebp
0x1001cb72  mov     [ebp+var_4], eax
0x1001cb75  mov     eax, [ebp+arg_C]
0x1001cb78  push    esi
0x1001cb79  mov     esi, [ebp+Src]
0x1001cb7c  push    edi
0x1001cb7d  push    _critJet; lpCriticalSection
0x1001cb83  mov     [ebp+var_290], esi
0x1001cb89  mov     [ebp+var_28C], eax
0x1001cb8f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001cb95  mov     edi, [ebp+sesid]
0x1001cb98  push    edi
0x1001cb99  call    _FValidSesid@4; FValidSesid(x)
0x1001cb9e  test    eax, eax
0x1001cba0  jnz     short loc_1001CBC5
0x1001cba2  push    _critJet; lpCriticalSection
0x1001cba8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cbae  pop     edi
0x1001cbaf  mov     eax, 0FFFFFBB0h
0x1001cbb4  pop     esi
0x1001cbb5  mov     ecx, [ebp+var_4]
0x1001cbb8  xor     ecx, ebp; StackCookie
0x1001cbba  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cbbf  mov     esp, ebp
0x1001cbc1  pop     ebp
0x1001cbc2  retn    10h
0x1001cbc5  push    ebx
0x1001cbc6  mov     ebx, [ebp+arg_4]
0x1001cbc9  cmp     ebx, 800h
0x1001cbcf  jnb     short loc_1001CC2D
0x1001cbd1  cmp     ebx, _tableidInit
0x1001cbd7  jb      short loc_1001CC2D
0x1001cbd9  mov     eax, ebx
0x1001cbdb  shl     eax, 4
0x1001cbde  cmp     dword_101636CC[eax], offset _vtfndefInvalidTableid
0x1001cbe8  jz      short loc_1001CC2D
0x1001cbea  test    byte ptr dword_101636C8[eax], 8
0x1001cbf1  jnz     short loc_1001CC2D
0x1001cbf3  push    0; int
0x1001cbf5  push    0; int
0x1001cbf7  push    0; int
0x1001cbf9  push    0FFFFE016h; int
0x1001cbfe  push    0; void *
0x1001cc00  push    0; void *
0x1001cc02  push    esi; Src
0x1001cc03  push    edi; int
0x1001cc04  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001cc09  push    _critJet; lpCriticalSection
0x1001cc0f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cc15  pop     ebx
0x1001cc16  pop     edi
0x1001cc17  mov     eax, 0FFFFF88Dh
0x1001cc1c  pop     esi
0x1001cc1d  mov     ecx, [ebp+var_4]
0x1001cc20  xor     ecx, ebp; StackCookie
0x1001cc22  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001cc27  mov     esp, ebp
0x1001cc29  pop     ebp
0x1001cc2a  retn    10h
0x1001cc2d  push    1
0x1001cc2f  push    82h
0x1001cc34  lea     eax, [ebp+var_88]
0x1001cc3a  push    eax
0x1001cc3b  push    ebx
0x1001cc3c  push    edi
0x1001cc3d  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x1001cc42  mov     esi, eax
0x1001cc44  test    esi, esi
0x1001cc46  js      loc_1001CE98
0x1001cc4c  push    2
0x1001cc4e  push    8
0x1001cc50  lea     eax, [ebp+var_2A4]
0x1001cc56  push    eax
0x1001cc57  push    ebx
0x1001cc58  push    edi
0x1001cc59  call    _ErrDispGetTableInfo@20; ErrDispGetTableInfo(x,x,x,x,x)
0x1001cc5e  mov     esi, eax
0x1001cc60  test    esi, esi
0x1001cc62  js      loc_1001CE98
0x1001cc68  push    edi; sesid
0x1001cc69  call    _JetBeginTransaction@4; JetBeginTransaction(x)
0x1001cc6e  mov     esi, eax
0x1001cc70  test    esi, esi
0x1001cc72  js      loc_1001CE98
0x1001cc78  push    [ebp+var_28C]
0x1001cc7e  push    [ebp+var_290]
0x1001cc84  push    ebx
0x1001cc85  push    edi
0x1001cc86  call    _ErrDispRenameColumn@16; ErrDispRenameColumn(x,x,x,x)
0x1001cc8b  mov     esi, eax
0x1001cc8d  test    esi, esi
0x1001cc8f  js      loc_1001CE8F
0x1001cc95  imul    eax, ebx, 64h ; 'd'
0x1001cc98  mov     [ebp+var_294], 0
0x1001cca2  mov     eax, dword_101315D0[eax]
0x1001cca8  mov     [ebp+var_298], eax
0x1001ccae  mov     eax, _rgrepdbinfo[eax*4]
0x1001ccb5  test    byte ptr [eax+0E4h], 20h
0x1001ccbc  jnz     loc_1001CE36
0x1001ccc2  xor     ebx, ebx
0x1001ccc4  nop     dword ptr [eax+00h]
0x1001ccc8  nop     dword ptr [eax+eax+00000000h]
0x1001ccd0  push    0
0x1001ccd2  push    80h
0x1001ccd7  lea     eax, [ebp+var_29C]
0x1001ccdd  push    eax
0x1001ccde  lea     eax, [ebp+var_294]
0x1001cce4  push    eax
0x1001cce5  push    1FEh
0x1001ccea  lea     eax, [ebp+var_288]
0x1001ccf0  push    eax
0x1001ccf1  push    offset _WZColIsGuid; "ColIsGuid"
0x1001ccf6  push    0
0x1001ccf8  push    [ebp+arg_4]
0x1001ccfb  push    edi
0x1001ccfc  call    _JetIRetrieveTableProperty@40; JetIRetrieveTableProperty(x,x,x,x,x,x,x,x,x,x)
0x1001cd01  mov     esi, eax
0x1001cd03  cmp     esi, 0FFFFFBAEh
0x1001cd09  jz      short loc_1001CD1B
0x1001cd0b  cmp     esi, 0FFFFFBAFh
0x1001cd11  jz      short loc_1001CD1B
0x1001cd13  cmp     esi, 0FFFFFBB2h
0x1001cd19  jnz     short loc_1001CD2C
0x1001cd1b  push    1F4h; dwMilliseconds
0x1001cd20  call    ds:__imp__Sleep@4; Sleep(x)
0x1001cd26  inc     ebx
0x1001cd27  cmp     ebx, 78h ; 'x'
0x1001cd2a  jb      short loc_1001CCD0
0x1001cd2c  test    esi, esi
0x1001cd2e  js      loc_1001CDE7
0x1001cd34  mov     eax, [ebp+var_294]
0x1001cd3a  test    eax, eax
0x1001cd3c  jz      loc_1001CE2F
0x1001cd42  mov     edx, [ebp+var_290]
0x1001cd48  xor     ecx, ecx
0x1001cd4a  mov     [ebp+eax+var_288], cx
0x1001cd52  lea     ecx, [ebp+var_288]
0x1001cd58  call    _WCSICMP@8; WCSICMP(x,x)
0x1001cd5d  test    eax, eax
0x1001cd5f  jnz     loc_1001CE33
0x1001cd65  xor     ebx, ebx
0x1001cd67  nop     word ptr [eax+eax+00000000h]
0x1001cd70  mov     esi, [ebp+var_28C]
0x1001cd76  mov     ecx, esi
0x1001cd78  lea     edx, [ecx+2]
0x1001cd7b  nop     dword ptr [eax+eax+00h]
0x1001cd80  mov     ax, [ecx]
0x1001cd83  add     ecx, 2
0x1001cd86  test    ax, ax
0x1001cd89  jnz     short loc_1001CD80
0x1001cd8b  push    80h; int
0x1001cd90  sub     ecx, edx
0x1001cd92  push    0Ah; int
0x1001cd94  sar     ecx, 1
0x1001cd96  lea     eax, [ecx+ecx]
0x1001cd99  push    eax; Size
0x1001cd9a  push    esi; void *
0x1001cd9b  push    offset _WZColIsGuid; "ColIsGuid"
0x1001cda0  push    0; void *
0x1001cda2  lea     eax, [ebp+var_88]
0x1001cda8  push    eax; int
0x1001cda9  push    offset _wszTcObject; "Tables"
0x1001cdae  push    [ebp+var_298]; unsigned int
0x1001cdb4  push    edi; Session *
0x1001cdb5  call    _JetISetProperty@40; JetISetProperty(x,x,x,x,x,x,x,x,x,x)
0x1001cdba  mov     esi, eax
0x1001cdbc  cmp     esi, 0FFFFFBAEh
0x1001cdc2  jz      short loc_1001CDD4
0x1001cdc4  cmp     esi, 0FFFFFBAFh
0x1001cdca  jz      short loc_1001CDD4
0x1001cdcc  cmp     esi, 0FFFFFBB2h
0x1001cdd2  jnz     short loc_1001CE2F
0x1001cdd4  push    1F4h; dwMilliseconds
0x1001cdd9  call    ds:__imp__Sleep@4; Sleep(x)
0x1001cddf  inc     ebx
0x1001cde0  cmp     ebx, 78h ; 'x'
0x1001cde3  jb      short loc_1001CD70
0x1001cde5  jmp     short loc_1001CE2F
0x1001cde7  cmp     esi, 0FFFFF1EEh
0x1001cded  jz      short loc_1001CDF7
0x1001cdef  cmp     esi, 0FFFFF1F0h
0x1001cdf5  jnz     short loc_1001CE2F
0x1001cdf7  mov     eax, _isibHead
0x1001cdfc  cmp     eax, 0FFFFFFFFh
0x1001cdff  jz      short loc_1001CE17
0x1001ce01  imul    ecx, eax, 68h ; 'h'
0x1001ce04  cmp     _rgsib[ecx], edi
0x1001ce0a  jz      short loc_1001CE17
0x1001ce0c  mov     eax, dword_1016EB88[ecx]
0x1001ce12  cmp     eax, 0FFFFFFFFh
0x1001ce15  jnz     short loc_1001CE01
0x1001ce17  imul    eax, 68h ; 'h'
0x1001ce1a  cmp     dword_1016EB6C[eax], 0
0x1001ce21  jnz     short loc_1001CE2D
0x1001ce23  mov     dword_1016EB50[eax], 41Fh
0x1001ce2d  xor     esi, esi
0x1001ce2f  test    esi, esi
0x1001ce31  js      short loc_1001CE8F
0x1001ce33  mov     ebx, [ebp+arg_4]
0x1001ce36  push    0; int
0x1001ce38  push    [ebp+var_28C]; Src
0x1001ce3e  push    [ebp+var_290]; void *
0x1001ce44  push    0; int
0x1001ce46  push    offset _wszTcObject; "Tables"
0x1001ce4b  push    ebx; int
0x1001ce4c  push    0FFFFFFFFh; int
0x1001ce4e  push    edi; int
0x1001ce4f  call    _ErrRefreshSubObjectProperties@32; ErrRefreshSubObjectProperties(x,x,x,x,x,x,x,x)
0x1001ce54  mov     esi, eax
0x1001ce56  test    esi, esi
0x1001ce58  js      short loc_1001CE8F
0x1001ce5a  push    [ebp+var_28C]; int
0x1001ce60  lea     eax, [ebp+var_88]
0x1001ce66  push    [ebp+var_290]; int
0x1001ce6c  push    0; int
0x1001ce6e  push    eax; int
0x1001ce6f  push    [ebp+var_2A4]; int
0x1001ce75  push    edi; sesid
0x1001ce76  call    _ErrRelationshipUpdateNames@24; ErrRelationshipUpdateNames(x,x,x,x,x,x)
0x1001ce7b  mov     esi, eax
0x1001ce7d  test    esi, esi
0x1001ce7f  js      short loc_1001CE8F
0x1001ce81  push    0; grbit
0x1001ce83  push    edi; sesid
0x1001ce84  call    _JetCommitTransaction@8; JetCommitTransaction(x,x)
0x1001ce89  mov     esi, eax
0x1001ce8b  test    esi, esi
0x1001ce8d  jns     short loc_1001CE98
0x1001ce8f  xor     edx, edx; char
0x1001ce91  mov     ecx, edi; Session *
0x1001ce93  call    _ErrRollback@8; ErrRollback(x,x)
0x1001ce98  push    _critJet; lpCriticalSection
0x1001ce9e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001cea4  mov     ecx, [ebp+var_4]
0x1001cea7  mov     eax, esi
0x1001cea9  pop     ebx
0x1001ceaa  pop     edi
0x1001ceab  xor     ecx, ebp; StackCookie
0x1001cead  pop     esi
0x1001ceae  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ceb3  mov     esp, ebp
0x1001ceb5  pop     ebp
0x1001ceb6  retn    10h
```
