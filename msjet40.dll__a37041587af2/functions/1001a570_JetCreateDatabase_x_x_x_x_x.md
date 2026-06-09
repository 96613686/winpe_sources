# JetCreateDatabase(x,x,x,x,x)

- ea: `0x1001a570`
- end: `0x1001a833`
- name: `_JetCreateDatabase@20`
- size: `707`
- prototype: `int __stdcall(int, void *Src, int, int, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation`

## callees

- `0x10017820`
- `0x100179a0`
- `0x1001a2c0`
- `0x1001a570`
- `0x1002a700`
- `0x1003a420`
- `0x1003a840`
- `0x1003e9b0`
- `0x1003ea00`
- `0x1003f080`
- `0x10042b60`
- `0x10043060`
- `0x1004650c`
- `0x1004923e`
- `0x10117340`
- `0x10121d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a788`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1001a788`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a5bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a62f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a797`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a5bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a62f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a797`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001a820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001a58d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001a58d`

## pseudocode

```c
int __stdcall JetCreateDatabase(Session *a1, void *Src, void *a3, int *a4, int a5)
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
    v5 = dword_1016EB88[v6];
    if ( v5 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  if ( Src && wcslen((const unsigned __int16 *)Src) <= 0x104 )
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
0x1001a570  mov     edi, edi
0x1001a572  push    ebp
0x1001a573  mov     ebp, esp
0x1001a575  sub     esp, 18h
0x1001a578  push    esi
0x1001a579  mov     esi, [ebp+arg_8]
0x1001a57c  push    edi
0x1001a57d  push    _critJet; lpCriticalSection
0x1001a583  mov     [ebp+var_4], 0
0x1001a58a  mov     [ebp+Block], esi
0x1001a58d  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001a593  mov     eax, _isibHead
0x1001a598  cmp     eax, 0FFFFFFFFh
0x1001a59b  jz      short loc_1001A5B6
0x1001a59d  mov     edi, [ebp+arg_0]
0x1001a5a0  imul    eax, 68h ; 'h'
0x1001a5a3  cmp     _rgsib[eax], edi
0x1001a5a9  jz      short loc_1001A5CF
0x1001a5ab  mov     eax, dword_1016EB88[eax]
0x1001a5b1  cmp     eax, 0FFFFFFFFh
0x1001a5b4  jnz     short loc_1001A5A0
0x1001a5b6  push    _critJet; lpCriticalSection
0x1001a5bc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a5c2  pop     edi
0x1001a5c3  mov     eax, 0FFFFFBB0h
0x1001a5c8  pop     esi
0x1001a5c9  mov     esp, ebp
0x1001a5cb  pop     ebp
0x1001a5cc  retn    14h
0x1001a5cf  push    edi
0x1001a5d0  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001a5d5  mov     eax, [ebp+Src]
0x1001a5d8  test    eax, eax
0x1001a5da  jz      loc_1001A81A
0x1001a5e0  mov     ecx, eax
0x1001a5e2  lea     edx, [ecx+2]
0x1001a5e5  mov     ax, [ecx]
0x1001a5e8  add     ecx, 2
0x1001a5eb  test    ax, ax
0x1001a5ee  jnz     short loc_1001A5E5
0x1001a5f0  sub     ecx, edx
0x1001a5f2  sar     ecx, 1
0x1001a5f4  cmp     ecx, 104h
0x1001a5fa  ja      loc_1001A81A
0x1001a600  push    ebx
0x1001a601  mov     ebx, [ebp+arg_10]
0x1001a604  test    ebx, 226h
0x1001a60a  jz      short loc_1001A65D
0x1001a60c  test    ebx, 200h
0x1001a612  jz      short loc_1001A620
0x1001a614  test    bl, 26h
0x1001a617  jnz     short loc_1001A629
0x1001a619  mov     edx, offset aJet3X; "Jet 3.x"
0x1001a61e  jmp     short loc_1001A648
0x1001a620  mov     eax, ebx
0x1001a622  and     eax, 24h
0x1001a625  cmp     al, 24h ; '$'
0x1001a627  jnz     short loc_1001A643
0x1001a629  push    _critJet; lpCriticalSection
0x1001a62f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a635  pop     ebx
0x1001a636  pop     edi
0x1001a637  mov     eax, 0FFFFFC15h
0x1001a63c  pop     esi
0x1001a63d  mov     esp, ebp
0x1001a63f  pop     ebp
0x1001a640  retn    14h
0x1001a643  mov     edx, offset aJet2X; "Jet 2.x"
0x1001a648  lea     eax, [ebp+Block]
0x1001a64b  mov     ecx, esi
0x1001a64d  push    eax
0x1001a64e  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001a653  mov     esi, eax
0x1001a655  test    esi, esi
0x1001a657  js      loc_1001A791
0x1001a65d  mov     edx, [ebp+Block]
0x1001a660  lea     eax, [ebp+var_14]
0x1001a663  push    eax
0x1001a664  lea     eax, [ebp+var_10]
0x1001a667  mov     ecx, edi
0x1001a669  push    eax
0x1001a66a  lea     eax, [ebp+var_18]
0x1001a66d  push    eax
0x1001a66e  lea     eax, [ebp+var_C]
0x1001a671  push    eax
0x1001a672  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x1001a677  mov     esi, eax
0x1001a679  test    esi, esi
0x1001a67b  js      loc_1001A77B
0x1001a681  mov     ecx, [ebp+var_10]
0x1001a684  mov     eax, [ebp+var_C]
0x1001a687  cmp     ecx, 0FFFFFFFFh
0x1001a68a  jz      short loc_1001A6F0
0x1001a68c  cmp     eax, 0FFFFh
0x1001a691  jz      short loc_1001A6A3
0x1001a693  test    byte ptr [ebp+var_14], 2
0x1001a697  jnz     short loc_1001A6A3
0x1001a699  mov     esi, 0FFFFFC17h
0x1001a69e  jmp     loc_1001A77B
0x1001a6a3  push    0
0x1001a6a5  lea     eax, [ebp+var_14]
0x1001a6a8  push    eax
0x1001a6a9  push    0
0x1001a6ab  push    0
0x1001a6ad  push    0
0x1001a6af  push    0F000002h
0x1001a6b4  push    ecx
0x1001a6b5  push    edi
0x1001a6b6  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1001a6bb  mov     esi, eax
0x1001a6bd  test    esi, esi
0x1001a6bf  js      loc_1001A77B
0x1001a6c5  test    byte ptr [ebp+var_14], 1
0x1001a6c9  jnz     short loc_1001A6ED
0x1001a6cb  push    0; int
0x1001a6cd  push    0; int
0x1001a6cf  push    0; int
0x1001a6d1  push    0FFFFE016h; int
0x1001a6d6  push    0; void *
0x1001a6d8  push    0; void *
0x1001a6da  push    [ebp+Src]; Src
0x1001a6dd  push    edi; int
0x1001a6de  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001a6e3  mov     esi, 0FFFFF88Dh
0x1001a6e8  jmp     loc_1001A77B
0x1001a6ed  mov     eax, [ebp+var_C]
0x1001a6f0  push    ebx; int
0x1001a6f1  cmp     eax, 0FFFFh
0x1001a6f6  lea     eax, [ebp+var_4]
0x1001a6f9  push    eax; int
0x1001a6fa  push    [ebp+Block]; int
0x1001a6fd  jnz     short loc_1001A70B
0x1001a6ff  mov     edx, [ebp+Src]
0x1001a702  mov     ecx, edi; int
0x1001a704  call    _ErrIsamCreateDatabase@20; ErrIsamCreateDatabase(x,x,x,x,x)
0x1001a709  jmp     short loc_1001A714
0x1001a70b  push    [ebp+Src]
0x1001a70e  push    edi
0x1001a70f  call    _ErrCreateDatabase@20; ErrCreateDatabase(x,x,x,x,x)
0x1001a714  mov     esi, eax
0x1001a716  test    esi, esi
0x1001a718  js      short loc_1001A77B
0x1001a71a  mov     ecx, [ebp+var_4]
0x1001a71d  mov     eax, [ebp+var_18]
0x1001a720  push    12h
0x1001a722  push    4
0x1001a724  mov     _mpdbidiiscb[ecx*4], eax
0x1001a72b  lea     eax, [ebp+var_10]
0x1001a72e  push    eax
0x1001a72f  push    ecx
0x1001a730  push    edi
0x1001a731  call    _ErrDispGetDatabaseInfo@20; ErrDispGetDatabaseInfo(x,x,x,x,x)
0x1001a736  mov     esi, eax
0x1001a738  test    esi, esi
0x1001a73a  js      short loc_1001A759
0x1001a73c  lea     eax, [ebp+var_10]
0x1001a73f  push    eax
0x1001a740  push    edi
0x1001a741  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x1001a746  mov     edx, [ebp+var_10]
0x1001a749  mov     ecx, eax
0x1001a74b  call    _ErrSetCollateSeqC@12; ErrSetCollateSeqC(x,x,x)
0x1001a750  test    eax, eax
0x1001a752  jz      short loc_1001A7A8
0x1001a754  mov     esi, 0FFFFEC5Eh
0x1001a759  push    0
0x1001a75b  push    [ebp+var_4]
0x1001a75e  push    edi
0x1001a75f  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a764  test    eax, eax
0x1001a766  jns     short loc_1001A773
0x1001a768  push    1
0x1001a76a  push    [ebp+var_4]
0x1001a76d  push    edi
0x1001a76e  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a773  mov     ecx, [ebp+Src]
0x1001a776  call    _ErrUtilDeleteFile@4; ErrUtilDeleteFile(x)
0x1001a77b  mov     eax, [ebp+Block]
0x1001a77e  cmp     eax, [ebp+arg_8]
0x1001a781  jz      short loc_1001A791
0x1001a783  test    eax, eax
0x1001a785  jz      short loc_1001A791
0x1001a787  push    eax; Block
0x1001a788  call    ds:__imp__free
0x1001a78e  add     esp, 4
0x1001a791  push    _critJet; lpCriticalSection
0x1001a797  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a79d  pop     ebx
0x1001a79e  pop     edi
0x1001a79f  mov     eax, esi
0x1001a7a1  pop     esi
0x1001a7a2  mov     esp, ebp
0x1001a7a4  pop     ebp
0x1001a7a5  retn    14h
0x1001a7a8  cmp     [ebp+var_C], 0FFFFh
0x1001a7af  jnz     short loc_1001A7D9
0x1001a7b1  mov     eax, ebx
0x1001a7b3  and     eax, 1
0x1001a7b6  push    eax
0x1001a7b7  push    0FFFFh
0x1001a7bc  push    ebx
0x1001a7bd  push    [ebp+var_4]
0x1001a7c0  push    edi
0x1001a7c1  call    _ErrREPOpenDatabase@20; ErrREPOpenDatabase(x,x,x,x,x)
0x1001a7c6  mov     esi, eax
0x1001a7c8  test    esi, esi
0x1001a7ca  jns     short loc_1001A7D9
0x1001a7cc  push    0
0x1001a7ce  push    [ebp+var_4]
0x1001a7d1  push    edi
0x1001a7d2  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x1001a7d7  jmp     short loc_1001A77B
0x1001a7d9  push    0
0x1001a7db  push    0
0x1001a7dd  push    10000000h
0x1001a7e2  push    [ebp+var_4]
0x1001a7e5  push    edi
0x1001a7e6  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x1001a7eb  mov     esi, eax
0x1001a7ed  test    esi, esi
0x1001a7ef  js      loc_1001A759
0x1001a7f5  push    0
0x1001a7f7  push    [ebp+var_4]
0x1001a7fa  push    [ebp+Block]
0x1001a7fd  push    edi
0x1001a7fe  call    _ErrSecGiveDefPermissions@16; ErrSecGiveDefPermissions(x,x,x,x)
0x1001a803  mov     esi, eax
0x1001a805  test    esi, esi
0x1001a807  js      loc_1001A759
0x1001a80d  mov     ecx, [ebp+arg_C]
0x1001a810  mov     eax, [ebp+var_4]
0x1001a813  mov     [ecx], eax
0x1001a815  jmp     loc_1001A77B
0x1001a81a  push    _critJet; lpCriticalSection
0x1001a820  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a826  pop     edi
0x1001a827  mov     eax, 0FFFFFC15h
0x1001a82c  pop     esi
0x1001a82d  mov     esp, ebp
0x1001a82f  pop     ebp
0x1001a830  retn    14h
```
