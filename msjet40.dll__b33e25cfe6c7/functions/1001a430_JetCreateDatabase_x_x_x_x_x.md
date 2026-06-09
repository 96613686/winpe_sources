# JetCreateDatabase(x,x,x,x,x)

- ea: `0x1001a430`
- end: `0x1001a6f3`
- name: `_JetCreateDatabase@20`
- size: `707`
- prototype: `int __stdcall(int, void *Src, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation`

## callees

- `0x100176e0`
- `0x10017860`
- `0x1001a180`
- `0x1001a430`
- `0x1002a530`
- `0x1003a2a0`
- `0x1003a6c0`
- `0x1003e820`
- `0x1003e870`
- `0x1003eef0`
- `0x100429d0`
- `0x10042ed0`
- `0x1004638c`
- `0x100490be`
- `0x10117190`
- `0x10121bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a648`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a648`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a47c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a4ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a6e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a47c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a4ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a6e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001a44d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001a44d`

## pseudocode

```c
int __stdcall JetCreateDatabase(Session *a1, unsigned __int16 *Src, void *a3, int *a4, int a5)
{
  int v5; // eax
  int v6; // eax
  int started; // esi
  int v9; // eax
  int Database; // eax
  int v11; // ecx
  int ItibOfSesid; // eax
  int v13; // [esp+8h] [ebp-18h] BYREF
  int v14; // [esp+Ch] [ebp-14h] BYREF
  int v15; // [esp+10h] [ebp-10h] BYREF
  int v16; // [esp+14h] [ebp-Ch] BYREF
  void *Block; // [esp+18h] [ebp-8h] BYREF
  int v18; // [esp+1Ch] [ebp-4h] BYREF

  v18 = 0;
  Block = a3;
  EnterCriticalSection(critJet);
  v5 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_4:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  while ( 1 )
  {
    v6 = 26 * v5;
    if ( (Session *)rgsib[v6] == a1 )
      break;
    v5 = dword_1016EAE8[v6];
    if ( v5 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  if ( Src && wcslen(Src) <= 0x104 )
  {
    if ( (a5 & 0x226) == 0 )
      goto LABEL_14;
    if ( (a5 & 0x200) != 0 )
    {
      if ( (a5 & 0x26) == 0 )
      {
LABEL_13:
        started = ErrGenIISAMConnectString(&Block);
        if ( started < 0 )
        {
LABEL_36:
          LeaveCriticalSection(critJet);
          return started;
        }
LABEL_14:
        started = ErrStartIsam(&v16, &v13, &v15, &v14);
        if ( started < 0 )
          goto LABEL_33;
        v9 = v16;
        if ( v15 != -1 )
        {
          if ( v16 != 0xFFFF && (v14 & 2) == 0 )
          {
            started = -1001;
            goto LABEL_33;
          }
          started = ErrSecGetAccess((int)a1, v15, 251658242, 0, 0, 0, &v14, 0);
          if ( started < 0 )
            goto LABEL_33;
          if ( (v14 & 1) == 0 )
          {
            UtilSetErrorInfoReal((int)a1, Src, 0, 0, -8170, 0, 0, 0);
            started = -1907;
            goto LABEL_33;
          }
          v9 = v16;
        }
        if ( v9 == 0xFFFF )
          Database = ErrIsamCreateDatabase((int)a1, (int)Block, (int)&v18, a5);
        else
          Database = ErrCreateDatabase(a1, (unsigned int)Src, Block, &v18, a5);
        started = Database;
        if ( Database < 0 )
          goto LABEL_33;
        v11 = v18;
        mpdbidiiscb[v18] = v13;
        started = ErrDispGetDatabaseInfo(a1, v11, &v15, 4, 18);
        if ( started < 0 )
        {
LABEL_30:
          if ( (int)ErrDispCloseDatabase(a1, v18, 0) < 0 )
            ErrDispCloseDatabase(a1, v18, 1);
          ErrUtilDeleteFile(Src);
          goto LABEL_33;
        }
        ItibOfSesid = UtilGetItibOfSesid((int)a1);
        if ( ErrSetCollateSeqC(ItibOfSesid, v15, &v15) )
        {
          started = -5026;
          goto LABEL_30;
        }
        if ( v16 == 0xFFFF && (started = ErrREPOpenDatabase(a1, v18, a5, 0xFFFF, a5 & 1), started < 0) )
        {
          ErrDispCloseDatabase(a1, v18, 0);
        }
        else
        {
          started = ErrSecSetOwner(a1, v18, 0, 0, 0);
          if ( started < 0 )
            goto LABEL_30;
          started = ErrSecGiveDefPermissions(a1, Block, v18, 0);
          if ( started < 0 )
            goto LABEL_30;
          *a4 = v18;
        }
LABEL_33:
        if ( Block != a3 )
        {
          if ( Block )
            _free(Block);
        }
        goto LABEL_36;
      }
    }
    else if ( (a5 & 0x24) != 0x24 )
    {
      goto LABEL_13;
    }
    LeaveCriticalSection(critJet);
    return -1003;
  }
  LeaveCriticalSection(critJet);
  return -1003;
}

```

## disassembly

```asm
0x1001a430  mov     edi, edi
0x1001a432  push    ebp
0x1001a433  mov     ebp, esp
0x1001a435  sub     esp, 18h
0x1001a438  push    esi
0x1001a439  mov     esi, [ebp+arg_8]
0x1001a43c  push    edi
0x1001a43d  push    _critJet; lpCriticalSection
0x1001a443  mov     [ebp+var_4], 0
0x1001a44a  mov     [ebp+Block], esi
0x1001a44d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001a453  mov     eax, _isibHead
0x1001a458  cmp     eax, 0FFFFFFFFh
0x1001a45b  jz      short loc_1001A476
0x1001a45d  mov     edi, [ebp+arg_0]
0x1001a460  imul    eax, 68h ; 'h'
0x1001a463  cmp     _rgsib[eax], edi
0x1001a469  jz      short loc_1001A48F
0x1001a46b  mov     eax, dword_1016EAE8[eax]
0x1001a471  cmp     eax, 0FFFFFFFFh
0x1001a474  jnz     short loc_1001A460
0x1001a476  push    _critJet; lpCriticalSection
0x1001a47c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a482  pop     edi
0x1001a483  mov     eax, 0FFFFFBB0h
0x1001a488  pop     esi
0x1001a489  mov     esp, ebp
0x1001a48b  pop     ebp
0x1001a48c  retn    14h
0x1001a48f  push    edi
0x1001a490  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001a495  mov     eax, [ebp+Src]
0x1001a498  test    eax, eax
0x1001a49a  jz      loc_1001A6DA
0x1001a4a0  mov     ecx, eax
0x1001a4a2  lea     edx, [ecx+2]
0x1001a4a5  mov     ax, [ecx]
0x1001a4a8  add     ecx, 2
0x1001a4ab  test    ax, ax
0x1001a4ae  jnz     short loc_1001A4A5
0x1001a4b0  sub     ecx, edx
0x1001a4b2  sar     ecx, 1
0x1001a4b4  cmp     ecx, 104h
0x1001a4ba  ja      loc_1001A6DA
0x1001a4c0  push    ebx
0x1001a4c1  mov     ebx, [ebp+arg_10]
0x1001a4c4  test    ebx, 226h
0x1001a4ca  jz      short loc_1001A51D
0x1001a4cc  test    ebx, 200h
0x1001a4d2  jz      short loc_1001A4E0
0x1001a4d4  test    bl, 26h
0x1001a4d7  jnz     short loc_1001A4E9
0x1001a4d9  mov     edx, offset aJet3X; "Jet 3.x"
0x1001a4de  jmp     short loc_1001A508
0x1001a4e0  mov     eax, ebx
0x1001a4e2  and     eax, 24h
0x1001a4e5  cmp     al, 24h ; '$'
0x1001a4e7  jnz     short loc_1001A503
0x1001a4e9  push    _critJet; lpCriticalSection
0x1001a4ef  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a4f5  pop     ebx
0x1001a4f6  pop     edi
0x1001a4f7  mov     eax, 0FFFFFC15h
0x1001a4fc  pop     esi
0x1001a4fd  mov     esp, ebp
0x1001a4ff  pop     ebp
0x1001a500  retn    14h
0x1001a503  mov     edx, offset aJet2X; "Jet 2.x"
0x1001a508  lea     eax, [ebp+Block]
0x1001a50b  mov     ecx, esi
0x1001a50d  push    eax
0x1001a50e  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001a513  mov     esi, eax
0x1001a515  test    esi, esi
0x1001a517  js      loc_1001A651
0x1001a51d  mov     edx, [ebp+Block]
0x1001a520  lea     eax, [ebp+var_14]
0x1001a523  push    eax
0x1001a524  lea     eax, [ebp+var_10]
0x1001a527  mov     ecx, edi
0x1001a529  push    eax
0x1001a52a  lea     eax, [ebp+var_18]
0x1001a52d  push    eax
0x1001a52e  lea     eax, [ebp+var_C]
0x1001a531  push    eax
0x1001a532  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x1001a537  mov     esi, eax
0x1001a539  test    esi, esi
0x1001a53b  js      loc_1001A63B
0x1001a541  mov     ecx, [ebp+var_10]
0x1001a544  mov     eax, [ebp+var_C]
0x1001a547  cmp     ecx, 0FFFFFFFFh
0x1001a54a  jz      short loc_1001A5B0
0x1001a54c  cmp     eax, 0FFFFh
0x1001a551  jz      short loc_1001A563
0x1001a553  test    byte ptr [ebp+var_14], 2
0x1001a557  jnz     short loc_1001A563
0x1001a559  mov     esi, 0FFFFFC17h
0x1001a55e  jmp     loc_1001A63B
0x1001a563  push    0
0x1001a565  lea     eax, [ebp+var_14]
0x1001a568  push    eax
0x1001a569  push    0
0x1001a56b  push    0
0x1001a56d  push    0
0x1001a56f  push    0F000002h
0x1001a574  push    ecx
0x1001a575  push    edi
0x1001a576  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1001a57b  mov     esi, eax
0x1001a57d  test    esi, esi
0x1001a57f  js      loc_1001A63B
0x1001a585  test    byte ptr [ebp+var_14], 1
0x1001a589  jnz     short loc_1001A5AD
0x1001a58b  push    0; int
0x1001a58d  push    0; int
0x1001a58f  push    0; int
0x1001a591  push    0FFFFE016h; int
0x1001a596  push    0; void *
0x1001a598  push    0; void *
0x1001a59a  push    [ebp+Src]; Src
0x1001a59d  push    edi; int
0x1001a59e  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001a5a3  mov     esi, 0FFFFF88Dh
0x1001a5a8  jmp     loc_1001A63B
0x1001a5ad  mov     eax, [ebp+var_C]
0x1001a5b0  push    ebx; int
0x1001a5b1  cmp     eax, 0FFFFh
0x1001a5b6  lea     eax, [ebp+var_4]
0x1001a5b9  push    eax; int
0x1001a5ba  push    [ebp+Block]; int
0x1001a5bd  jnz     short loc_1001A5CB
0x1001a5bf  mov     edx, [ebp+Src]
0x1001a5c2  mov     ecx, edi; int
0x1001a5c4  call    _ErrIsamCreateDatabase@20; ErrIsamCreateDatabase(x,x,x,x,x)
0x1001a5c9  jmp     short loc_1001A5D4
0x1001a5cb  push    [ebp+Src]
0x1001a5ce  push    edi
0x1001a5cf  call    _ErrCreateDatabase@20; ErrCreateDatabase(x,x,x,x,x)
0x1001a5d4  mov     esi, eax
0x1001a5d6  test    esi, esi
0x1001a5d8  js      short loc_1001A63B
0x1001a5da  mov     ecx, [ebp+var_4]
0x1001a5dd  mov     eax, [ebp+var_18]
0x1001a5e0  push    12h
0x1001a5e2  push    4
0x1001a5e4  mov     _mpdbidiiscb[ecx*4], eax
0x1001a5eb  lea     eax, [ebp+var_10]
0x1001a5ee  push    eax
0x1001a5ef  push    ecx
0x1001a5f0  push    edi
0x1001a5f1  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001a5f6  mov     esi, eax
0x1001a5f8  test    esi, esi
0x1001a5fa  js      short loc_1001A619
0x1001a5fc  lea     eax, [ebp+var_10]
0x1001a5ff  push    eax
0x1001a600  push    edi
0x1001a601  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x1001a606  mov     edx, [ebp+var_10]
0x1001a609  mov     ecx, eax
0x1001a60b  call    _ErrSetCollateSeqC@12; ErrSetCollateSeqC(x,x,x)
0x1001a610  test    eax, eax
0x1001a612  jz      short loc_1001A668
0x1001a614  mov     esi, 0FFFFEC5Eh
0x1001a619  push    0
0x1001a61b  push    [ebp+var_4]
0x1001a61e  push    edi
0x1001a61f  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a624  test    eax, eax
0x1001a626  jns     short loc_1001A633
0x1001a628  push    1
0x1001a62a  push    [ebp+var_4]
0x1001a62d  push    edi
0x1001a62e  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a633  mov     ecx, [ebp+Src]
0x1001a636  call    _ErrUtilDeleteFile@4; ErrUtilDeleteFile(x)
0x1001a63b  mov     eax, [ebp+Block]
0x1001a63e  cmp     eax, [ebp+arg_8]
0x1001a641  jz      short loc_1001A651
0x1001a643  test    eax, eax
0x1001a645  jz      short loc_1001A651
0x1001a647  push    eax; Block
0x1001a648  call    ds:__imp__free
0x1001a64e  add     esp, 4
0x1001a651  push    _critJet; lpCriticalSection
0x1001a657  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a65d  pop     ebx
0x1001a65e  pop     edi
0x1001a65f  mov     eax, esi
0x1001a661  pop     esi
0x1001a662  mov     esp, ebp
0x1001a664  pop     ebp
0x1001a665  retn    14h
0x1001a668  cmp     [ebp+var_C], 0FFFFh
0x1001a66f  jnz     short loc_1001A699
0x1001a671  mov     eax, ebx
0x1001a673  and     eax, 1
0x1001a676  push    eax
0x1001a677  push    0FFFFh
0x1001a67c  push    ebx
0x1001a67d  push    [ebp+var_4]
0x1001a680  push    edi
0x1001a681  call    _ErrREPOpenDatabase@20; ErrREPOpenDatabase(x,x,x,x,x)
0x1001a686  mov     esi, eax
0x1001a688  test    esi, esi
0x1001a68a  jns     short loc_1001A699
0x1001a68c  push    0
0x1001a68e  push    [ebp+var_4]
0x1001a691  push    edi
0x1001a692  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a697  jmp     short loc_1001A63B
0x1001a699  push    0
0x1001a69b  push    0
0x1001a69d  push    10000000h
0x1001a6a2  push    [ebp+var_4]
0x1001a6a5  push    edi
0x1001a6a6  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x1001a6ab  mov     esi, eax
0x1001a6ad  test    esi, esi
0x1001a6af  js      loc_1001A619
0x1001a6b5  push    0
0x1001a6b7  push    [ebp+var_4]
0x1001a6ba  push    [ebp+Block]
0x1001a6bd  push    edi
0x1001a6be  call    _ErrSecGiveDefPermissions@16; ErrSecGiveDefPermissions(x,x,x,x)
0x1001a6c3  mov     esi, eax
0x1001a6c5  test    esi, esi
0x1001a6c7  js      loc_1001A619
0x1001a6cd  mov     ecx, [ebp+arg_C]
0x1001a6d0  mov     eax, [ebp+var_4]
0x1001a6d3  mov     [ecx], eax
0x1001a6d5  jmp     loc_1001A63B
0x1001a6da  push    _critJet; lpCriticalSection
0x1001a6e0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a6e6  pop     edi
0x1001a6e7  mov     eax, 0FFFFFC15h
0x1001a6ec  pop     esi
0x1001a6ed  mov     esp, ebp
0x1001a6ef  pop     ebp
0x1001a6f0  retn    14h
```
