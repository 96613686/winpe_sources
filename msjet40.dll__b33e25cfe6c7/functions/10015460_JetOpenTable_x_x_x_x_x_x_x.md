# JetOpenTable(x,x,x,x,x,x,x)

- ea: `0x10015460`
- end: `0x10015a1e`
- name: `_JetOpenTable@28`
- size: `1470`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x10094fc8`
- `0x100a0535`
- `0x100cf7ad`
- `0x100cf9f4`

## callees

- `0x100129b0`
- `0x10015010`
- `0x10015340`
- `0x10015460`
- `0x1003a6c0`
- `0x1003e650`
- `0x1003e6d0`
- `0x1003e7a0`
- `0x1003e820`
- `0x1003e870`
- `0x10042fb0`
- `0x10043090`
- `0x10043260`
- `0x10043840`
- `0x10043da0`
- `0x10044250`
- `0x100451f0`
- `0x10045230`
- `0x1009c291`
- `0x1009feb0`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1001557b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1001557b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001593e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100159f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001593e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100159f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100154be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001575c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100154be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001575c`

## pseudocode

```c
int __stdcall JetOpenTable(Session *a1, int a2, wchar_t *a3, int a4, int a5, int a6, int *a7)
{
  int Access; // edi
  unsigned int v8; // ebx
  wchar_t *v9; // eax
  int v10; // ecx
  int v11; // ebx
  bool v12; // zf
  int v13; // esi
  int ACM; // eax
  int v15; // ecx
  int v16; // eax
  int *v17; // eax
  int v18; // eax
  int *v19; // ecx
  int v20; // edi
  BOOL v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  int v27; // eax
  int v28; // ecx
  wchar_t *Src; // [esp+Ch] [ebp-6Ch]
  int v31; // [esp+10h] [ebp-68h] BYREF
  int TableInfo; // [esp+14h] [ebp-64h]
  int v33; // [esp+18h] [ebp-60h]
  int v34; // [esp+1Ch] [ebp-5Ch] BYREF
  int *v35; // [esp+20h] [ebp-58h]
  unsigned int v36; // [esp+24h] [ebp-54h]
  int v37; // [esp+28h] [ebp-50h]
  __int16 v38; // [esp+2Ch] [ebp-4Ch] BYREF
  int v39; // [esp+30h] [ebp-48h]
  int v40; // [esp+34h] [ebp-44h] BYREF
  int v41; // [esp+38h] [ebp-40h] BYREF
  _DWORD v42[4]; // [esp+3Ch] [ebp-3Ch] BYREF
  char v43; // [esp+4Ch] [ebp-2Ch] BYREF
  int v44; // [esp+50h] [ebp-28h]

  v37 = a4;
  v33 = a2;
  v35 = a7;
  v34 = 983294;
  v31 = -1;
  v40 = 0;
  v38 = 0;
  TableInfo = 0;
  EnterCriticalSection(critJet);
  if ( a7 )
    *a7 = -1;
  if ( !FValidSesid(a1) )
    goto LABEL_4;
  if ( (a6 & 0xF0000000) != 0 )
  {
LABEL_6:
    Access = -1003;
    goto LABEL_99;
  }
  v8 = a6 & 0x7FFFFFFF;
  v39 = a6 & 0x7FFFFFFF;
  if ( v33 < (unsigned int)dbidInit
    || (unsigned int)v33 >= 0x100
    || (v12 = mpdbidpvdbfndef[v33] == (_DWORD)vdbfndefInvalidDbid, v36 = 4 * v33, v12) )
  {
    v36 = 4 * v33;
    if ( v33 != -1 )
    {
      Access = -1010;
      goto LABEL_99;
    }
  }
  v9 = (wchar_t *)&v38;
  if ( a3 )
    v9 = a3;
  Src = v9;
  if ( !WCSNICMP(4) )
  {
    v10 = _wcstol(Src + 4, 0, 10);
    v11 = 4 * v10;
    if ( a1 != (Session *)rgsib[26 * mptableidisib[v10]] )
    {
LABEL_4:
      Access = -1104;
      goto LABEL_99;
    }
    Access = ErrDispDupCursor(a1, v10, &v31, 0);
    v12 = Access == 0;
    if ( Access >= 0 )
    {
      v13 = v31;
      ACM = AcmDispGetACM();
      ErrSetAcmTableid(v15, ACM);
      *((_DWORD *)rgvtdefname + v13) = *(_DWORD *)((char *)rgvtdefname + v11);
      if ( v35 )
        *v35 = v31;
LABEL_19:
      v12 = Access == 0;
    }
LABEL_20:
    if ( v12 )
    {
      v16 = TableInfo;
      if ( TableInfo == 3811 )
        goto LABEL_98;
      goto LABEL_97;
    }
LABEL_96:
    v16 = TableInfo;
LABEL_97:
    if ( v16 != 3812 )
      goto LABEL_99;
LABEL_98:
    Access = v16;
    goto LABEL_99;
  }
  if ( (a6 & 0x800) == 0 )
  {
    if ( (a6 & 0x4100) != 0 )
      v8 = a6 & 0x7FFFFFFB;
    v20 = v33;
    if ( v33 == -1 )
      goto LABEL_44;
    if ( IsJetIsam(a1, v33) || *(&::Src + 5 * mpdbidiiscb[v36 / 4]) && (int *)mpdbidpvdbfndef[v36 / 4] != vdbfndefRdb )
    {
      v42[0] = 40;
      v42[3] = &v43;
      if ( (int)ErrDispGetObjectInfo(a1, v33, 0, L"Tables", Src, v42, 5) < 0 )
        goto LABEL_44;
      if ( (int)ErrDispGetObjidFromName(a1, v33, L"Tables", Src, &v40) >= 0 )
      {
        if ( v44 == 5 )
        {
          v22 = 1;
          goto LABEL_54;
        }
      }
      else
      {
        ClearErrorInfo(a1);
      }
      v22 = 0;
    }
    else
    {
      v21 = FLikelySQLString(Src);
      v22 = 0;
      if ( v21 )
      {
LABEL_44:
        ClearErrorInfo(a1);
        v23 = ErrTrySQLString(a1, v33, Src, v37, a5, v8, 0, &v31);
        goto LABEL_45;
      }
    }
LABEL_54:
    if ( (v8 & 0x100) != 0 )
      v8 &= ~0x40u;
    if ( (v8 & 0x40) == 0 && !v22 )
    {
      if ( (v8 & 0x100) != 0 )
      {
        Access = -3021;
        goto LABEL_99;
      }
      if ( (int *)mpdbidpvdbfndef[v36 / 4] == vdbfndefRdb )
        goto LABEL_6;
      if ( *(&::Src + 5 * mpdbidiiscb[v36 / 4]) )
      {
        Access = ErrSecGetAccess(a1, v33, v40, 0, 0, 0, &v34, 0);
        v12 = Access == 0;
        if ( Access < 0 )
          goto LABEL_20;
        if ( (v34 & 0xF8) == 0 )
        {
          UtilSetErrorInfoReal((int)a1, Src, 0, 0, -8119, 0, 0, 0);
          Access = -1907;
          goto LABEL_99;
        }
        v24 = v39;
        if ( (v34 & 0xD0) == 0 )
          v24 = v39 | 8;
        v20 = v33;
        v25 = v24 | 0x10000000;
        if ( (v34 & 0x100) == 0 )
          v25 = v24;
        v26 = v25;
      }
      else
      {
        v26 = v39;
      }
      v27 = ErrDispOpenTable(a1, v20, &v31, Src, v26);
      Access = v27;
      if ( v27 >= 0 )
      {
        ErrSetAcmTableid(v28, v34);
        goto LABEL_46;
      }
      if ( v27 != -1034 && v27 != -1052 && v27 != -1035 )
        goto LABEL_90;
      v20 = v33;
    }
    v23 = ErrOpenVtQo(a1, v20, &v31, Src, v37, a5, v8, 0, 0);
LABEL_45:
    Access = v23;
LABEL_46:
    if ( !Access )
    {
      if ( (v8 & 0xC00000) != 0 )
      {
        v37 = v31;
        EnterCriticalSection(critJet);
        if ( FValidSesid(a1) )
        {
          TableInfo = ErrDispGetTableInfo(a1, v37, &v41, 4, 11);
          LeaveCriticalSection(critJet);
          if ( !TableInfo )
          {
            if ( v41 )
            {
              if ( (v8 & 0x400000) != 0 )
                TableInfo = 3812;
            }
            else if ( (v8 & 0x800000) != 0 )
            {
              TableInfo = 3811;
            }
          }
        }
        else
        {
          LeaveCriticalSection(critJet);
          TableInfo = -1104;
        }
      }
      goto LABEL_87;
    }
    if ( Access >= 0 )
    {
LABEL_87:
      if ( v31 == -1 && (v8 & 0x100) == 0 )
        Access = 3061;
    }
LABEL_90:
    if ( v35 )
      *v35 = v31;
    if ( dword_1016EAB0[26 * UtilGetIsibOfSesidIscb(a1)] == 1055 )
    {
      if ( Access == -1305 )
      {
        UtilSetErrorInfoReal((int)a1, 0, Src, 0, -8003, 0, 0, 0);
        goto LABEL_96;
      }
      if ( Access == -1302 )
      {
        UtilSetErrorInfoReal((int)a1, 0, Src, 0, -8153, 0, 0, 0);
        goto LABEL_96;
      }
    }
    goto LABEL_19;
  }
  if ( v33 == -1 || (int *)mpdbidpvdbfndef[v36 / 4] != vdbfndefRdb )
    goto LABEL_6;
  v34 = 0;
  v17 = &v34;
  if ( a7 )
    v17 = a7;
  v18 = ErrRmtOpenPassThrough(a1, v33, 0, Src, v17, 0, -1, 0, 0, 0, 0, (v8 >> 12) & 1);
  v19 = v35;
  Access = v18;
  if ( v34 != -1 )
  {
    if ( v35 )
    {
      v31 = *v35;
    }
    else
    {
      ErrDispCloseTable(a1, v34);
      v19 = v35;
    }
  }
  if ( !Access && (a6 & 0x1000) != 0 && v19 && *v19 == -1 )
    Access = 3061;
LABEL_99:
  LeaveCriticalSection(critJet);
  return Access;
}

```

## disassembly

```asm
0x10015460  mov     edi, edi
0x10015462  push    ebp
0x10015463  mov     ebp, esp
0x10015465  and     esp, 0FFFFFFF8h
0x10015468  sub     esp, 6Ch
0x1001546b  mov     eax, ___security_cookie
0x10015470  xor     eax, esp
0x10015472  mov     [esp+6Ch+var_4], eax
0x10015476  mov     eax, [ebp+arg_8]
0x10015479  mov     ecx, [ebp+arg_4]
0x1001547c  push    ebx
0x1001547d  push    esi
0x1001547e  mov     [esp+74h+Src], eax
0x10015482  mov     eax, [ebp+arg_C]
0x10015485  push    edi
0x10015486  push    _critJet; lpCriticalSection
0x1001548c  mov     edi, [ebp+arg_18]
0x1001548f  mov     [esp+7Ch+var_50], eax
0x10015493  xor     eax, eax
0x10015495  mov     [esp+7Ch+var_60], ecx
0x10015499  mov     [esp+7Ch+var_58], edi
0x1001549d  mov     [esp+7Ch+var_5C], 0F00FEh
0x100154a5  mov     [esp+7Ch+var_68], 0FFFFFFFFh
0x100154ad  mov     [esp+7Ch+var_44], 0
0x100154b5  mov     [esp+7Ch+var_4C], ax
0x100154ba  mov     [esp+7Ch+var_64], eax
0x100154be  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100154c4  test    edi, edi
0x100154c6  jz      short loc_100154CE
0x100154c8  mov     dword ptr [edi], 0FFFFFFFFh
0x100154ce  mov     esi, [ebp+arg_0]
0x100154d1  push    esi
0x100154d2  call    _FValidSesid@4; FValidSesid(x)
0x100154d7  test    eax, eax
0x100154d9  jnz     short loc_100154E5
0x100154db  mov     edi, 0FFFFFBB0h
0x100154e0  jmp     loc_100159EF
0x100154e5  mov     ebx, [ebp+arg_14]
0x100154e8  test    ebx, 0F0000000h
0x100154ee  jz      short loc_100154FA
0x100154f0  mov     edi, 0FFFFFC15h
0x100154f5  jmp     loc_100159EF
0x100154fa  mov     ecx, [esp+78h+var_60]
0x100154fe  and     ebx, 7FFFFFFFh
0x10015504  mov     [esp+78h+var_48], ebx
0x10015508  cmp     ecx, _dbidInit
0x1001550e  jb      short loc_1001552F
0x10015510  cmp     ecx, 100h
0x10015516  jnb     short loc_1001552F
0x10015518  lea     eax, ds:0[ecx*4]
0x1001551f  cmp     _mpdbidpvdbfndef[eax], offset _vdbfndefInvalidDbid
0x10015529  mov     [esp+78h+var_54], eax
0x1001552d  jnz     short loc_10015549
0x1001552f  lea     eax, ds:0[ecx*4]
0x10015536  mov     [esp+78h+var_54], eax
0x1001553a  cmp     ecx, 0FFFFFFFFh
0x1001553d  jz      short loc_10015549
0x1001553f  mov     edi, 0FFFFFC0Eh
0x10015544  jmp     loc_100159EF
0x10015549  mov     ecx, [esp+78h+Src]
0x1001554d  lea     eax, [esp+78h+var_4C]
0x10015551  test    ecx, ecx
0x10015553  mov     edx, offset _wszCursorNamePrefix; ".MU."
0x10015558  push    4
0x1001555a  cmovnz  eax, ecx
0x1001555d  mov     ecx, eax
0x1001555f  mov     [esp+7Ch+Src], eax
0x10015563  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10015568  test    eax, eax
0x1001556a  jnz     loc_100155FE
0x10015570  push    0Ah; Radix
0x10015572  push    eax; EndPtr
0x10015573  mov     eax, [esp+80h+Src]
0x10015577  add     eax, 8
0x1001557a  push    eax; String
0x1001557b  call    ds:__imp__wcstol
0x10015581  mov     ecx, eax
0x10015583  add     esp, 0Ch
0x10015586  lea     ebx, ds:0[ecx*4]
0x1001558d  imul    eax, _mptableidisib[ebx], 68h ; 'h'
0x10015594  cmp     esi, _rgsib[eax]
0x1001559a  jnz     loc_100154DB
0x100155a0  push    0
0x100155a2  lea     eax, [esp+7Ch+var_68]
0x100155a6  push    eax
0x100155a7  push    ecx
0x100155a8  push    esi
0x100155a9  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x100155ae  mov     edi, eax
0x100155b0  test    edi, edi
0x100155b2  js      short loc_100155E4
0x100155b4  mov     esi, [esp+78h+var_68]
0x100155b8  mov     edx, esi
0x100155ba  call    _AcmDispGetACM@8; AcmDispGetACM(x,x)
0x100155bf  push    eax
0x100155c0  push    ecx
0x100155c1  mov     edx, esi
0x100155c3  call    _ErrSetAcmTableid@16; ErrSetAcmTableid(x,x,x,x)
0x100155c8  mov     ecx, _rgvtdefname
0x100155ce  mov     eax, [ebx+ecx]
0x100155d1  mov     [ecx+esi*4], eax
0x100155d4  mov     ecx, [esp+78h+var_58]
0x100155d8  test    ecx, ecx
0x100155da  jz      short loc_100155E2
0x100155dc  mov     eax, [esp+78h+var_68]
0x100155e0  mov     [ecx], eax
0x100155e2  test    edi, edi
0x100155e4  jnz     loc_100159E2
0x100155ea  mov     eax, [esp+78h+var_64]
0x100155ee  cmp     eax, 0EE3h
0x100155f3  jz      loc_100159ED
0x100155f9  jmp     loc_100159E6
0x100155fe  test    ebx, 800h
0x10015604  jz      loc_100156B9
0x1001560a  mov     ecx, [esp+78h+var_60]
0x1001560e  cmp     ecx, 0FFFFFFFFh
0x10015611  jz      loc_100154F0
0x10015617  mov     edx, [esp+78h+var_54]
0x1001561b  cmp     _mpdbidpvdbfndef[edx], offset _vdbfndefRdb
0x10015625  jnz     loc_100154F0
0x1001562b  mov     eax, ebx
0x1001562d  mov     [esp+78h+var_5C], 0
0x10015635  shr     eax, 0Ch
0x10015638  and     eax, 1
0x1001563b  test    edi, edi
0x1001563d  push    eax
0x1001563e  push    0
0x10015640  push    0
0x10015642  push    0
0x10015644  push    0
0x10015646  push    0FFFFFFFFh
0x10015648  push    0
0x1001564a  lea     eax, [esp+94h+var_5C]
0x1001564e  cmovnz  eax, edi
0x10015651  or      edx, 0FFFFFFFFh
0x10015654  push    eax
0x10015655  mov     eax, [esp+98h+Src]
0x10015659  push    eax
0x1001565a  push    0
0x1001565c  push    ecx
0x1001565d  mov     ecx, esi
0x1001565f  call    _ErrRmtOpenPassThrough@52; ErrRmtOpenPassThrough(x,x,x,x,x,x,x,x,x,x,x,x,x)
0x10015664  mov     ecx, [esp+78h+var_58]
0x10015668  mov     edi, eax
0x1001566a  mov     eax, [esp+78h+var_5C]
0x1001566e  cmp     eax, 0FFFFFFFFh
0x10015671  jz      short loc_1001568A
0x10015673  test    ecx, ecx
0x10015675  jz      short loc_1001567F
0x10015677  mov     eax, [ecx]
0x10015679  mov     [esp+78h+var_68], eax
0x1001567d  jmp     short loc_1001568A
0x1001567f  push    eax
0x10015680  push    esi
0x10015681  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10015686  mov     ecx, [esp+78h+var_58]
0x1001568a  test    edi, edi
0x1001568c  jnz     loc_100159EF
0x10015692  test    ebx, 1000h
0x10015698  jz      loc_100159EF
0x1001569e  test    ecx, ecx
0x100156a0  jz      loc_100159EF
0x100156a6  cmp     dword ptr [ecx], 0FFFFFFFFh
0x100156a9  jnz     loc_100159EF
0x100156af  mov     edi, 0BF5h
0x100156b4  jmp     loc_100159EF
0x100156b9  test    ebx, 4100h
0x100156bf  jz      short loc_100156C4
0x100156c1  and     ebx, 0FFFFFFFBh
0x100156c4  mov     edi, [esp+78h+var_60]
0x100156c8  cmp     edi, 0FFFFFFFFh
0x100156cb  jz      short loc_10015718
0x100156cd  mov     edx, edi
0x100156cf  mov     ecx, esi
0x100156d1  call    _IsJetIsam@8; IsJetIsam(x,x)
0x100156d6  test    eax, eax
0x100156d8  jnz     loc_10015789
0x100156de  mov     edx, [esp+78h+var_54]
0x100156e2  mov     eax, _mpdbidiiscb[edx]
0x100156e8  lea     eax, [eax+eax*4]
0x100156eb  cmp     Src[eax*4], 0
0x100156f3  jz      short loc_10015705
0x100156f5  cmp     _mpdbidpvdbfndef[edx], offset _vdbfndefRdb
0x100156ff  jnz     loc_10015789
0x10015705  mov     ecx, [esp+78h+Src]
0x10015709  call    FLikelySQLString
0x1001570e  xor     ecx, ecx
0x10015710  test    eax, eax
0x10015712  jz      loc_100157DC
0x10015718  push    esi
0x10015719  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001571e  lea     eax, [esp+78h+var_68]
0x10015722  push    eax
0x10015723  push    0
0x10015725  push    ebx
0x10015726  push    [ebp+arg_10]
0x10015729  push    [esp+88h+var_50]
0x1001572d  push    [esp+8Ch+Src]
0x10015731  push    edi
0x10015732  push    esi
0x10015733  call    _ErrTrySQLString@32; ErrTrySQLString(x,x,x,x,x,x,x,x)
0x10015738  mov     edi, eax
0x1001573a  test    edi, edi
0x1001573c  jnz     loc_10015976
0x10015742  test    ebx, 0C00000h
0x10015748  jz      loc_10015978
0x1001574e  mov     eax, [esp+78h+var_68]
0x10015752  push    _critJet; lpCriticalSection
0x10015758  mov     [esp+7Ch+var_50], eax
0x1001575c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10015762  push    esi
0x10015763  call    _FValidSesid@4; FValidSesid(x)
0x10015768  test    eax, eax
0x1001576a  jnz     loc_10015921
0x10015770  push    _critJet; lpCriticalSection
0x10015776  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001577c  mov     [esp+78h+var_64], 0FFFFFBB0h
0x10015784  jmp     loc_10015978
0x10015789  push    5
0x1001578b  lea     eax, [esp+7Ch+var_2C]
0x1001578f  mov     [esp+7Ch+var_3C], 28h ; '('
0x10015797  mov     [esp+7Ch+var_30], eax
0x1001579b  lea     eax, [esp+7Ch+var_3C]
0x1001579f  push    eax
0x100157a0  mov     eax, [esp+80h+Src]
0x100157a4  push    eax
0x100157a5  push    offset _wszTcObject; "Tables"
0x100157aa  push    0
0x100157ac  push    edi
0x100157ad  push    esi
0x100157ae  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x100157b3  test    eax, eax
0x100157b5  js      loc_10015718
0x100157bb  lea     eax, [esp+78h+var_44]
0x100157bf  push    eax
0x100157c0  push    [esp+7Ch+Src]
0x100157c4  push    offset _wszTcObject; "Tables"
0x100157c9  push    edi
0x100157ca  push    esi
0x100157cb  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x100157d0  test    eax, eax
0x100157d2  jns     short loc_1001580A
0x100157d4  push    esi
0x100157d5  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100157da  xor     ecx, ecx
0x100157dc  test    ebx, 100h
0x100157e2  jz      short loc_100157E7
0x100157e4  and     ebx, 0FFFFFFBFh
0x100157e7  test    bl, 40h
0x100157ea  jnz     loc_10015900
0x100157f0  test    ecx, ecx
0x100157f2  jnz     loc_10015900
0x100157f8  test    ebx, 100h
0x100157fe  jz      short loc_10015818
0x10015800  mov     edi, 0FFFFF433h
0x10015805  jmp     loc_100159EF
0x1001580a  cmp     [esp+78h+var_28], 5
0x1001580f  jnz     short loc_100157DA
0x10015811  mov     ecx, 1
0x10015816  jmp     short loc_100157DC
0x10015818  mov     eax, [esp+78h+var_54]
0x1001581c  cmp     _mpdbidpvdbfndef[eax], offset _vdbfndefRdb
0x10015826  jz      loc_100154F0
0x1001582c  mov     eax, _mpdbidiiscb[eax]
0x10015832  lea     eax, [eax+eax*4]
0x10015835  cmp     Src[eax*4], 0
0x1001583d  jz      short loc_100158B2
0x1001583f  push    0
0x10015841  lea     eax, [esp+7Ch+var_5C]
0x10015845  push    eax
0x10015846  push    0
0x10015848  push    0
0x1001584a  push    0
0x1001584c  push    [esp+8Ch+var_44]
0x10015850  push    edi
0x10015851  push    esi
0x10015852  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x10015857  mov     edi, eax
0x10015859  test    edi, edi
0x1001585b  js      loc_100155E4
0x10015861  mov     eax, [esp+78h+var_5C]
0x10015865  test    al, 0F8h
0x10015867  jnz     short loc_1001588C
0x10015869  push    0; int
0x1001586b  push    0; int
0x1001586d  push    0; int
0x1001586f  push    0FFFFE049h; int
0x10015874  push    0; void *
0x10015876  push    0; void *
0x10015878  push    [esp+90h+Src]; Src
0x1001587c  push    esi; int
0x1001587d  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10015882  mov     edi, 0FFFFF88Dh
0x10015887  jmp     loc_100159EF
0x1001588c  mov     edx, [esp+78h+var_48]
0x10015890  test    al, 0D0h
0x10015892  jnz     short loc_10015897
0x10015894  or      edx, 8
0x10015897  mov     edi, [esp+78h+var_60]
0x1001589b  mov     ecx, edx
  ... truncated ...
```
