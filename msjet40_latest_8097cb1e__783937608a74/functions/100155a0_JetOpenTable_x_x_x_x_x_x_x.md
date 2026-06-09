# JetOpenTable(x,x,x,x,x,x,x)

- ea: `0x100155a0`
- end: `0x10015b5e`
- name: `_JetOpenTable@28`
- size: `1470`
- prototype: ``
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation`

## callers

- `0x10095158`
- `0x100a06c5`
- `0x100cf93d`
- `0x100cfb84`

## callees

- `0x10012af0`
- `0x10015150`
- `0x10015480`
- `0x100155a0`
- `0x1003a840`
- `0x1003e7e0`
- `0x1003e860`
- `0x1003e930`
- `0x1003e9b0`
- `0x1003ea00`
- `0x10043140`
- `0x10043220`
- `0x100433f0`
- `0x100439d0`
- `0x10043f30`
- `0x100443d0`
- `0x10045370`
- `0x100453b0`
- `0x1009c421`
- `0x100a0040`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x100156bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x100156bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100158b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015a7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015b35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100158b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015a7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10015b35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100155fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001589c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100155fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001589c`

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
    v23 = ErrOpenVtQo(a1, v20, (int)&v31, Src, v37, a5, v8, 0, 0);
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
    if ( dword_1016EB50[26 * UtilGetIsibOfSesidIscb(a1)] == 1055 )
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
0x100155a0  mov     edi, edi
0x100155a2  push    ebp
0x100155a3  mov     ebp, esp
0x100155a5  and     esp, 0FFFFFFF8h
0x100155a8  sub     esp, 6Ch
0x100155ab  mov     eax, ___security_cookie
0x100155b0  xor     eax, esp
0x100155b2  mov     [esp+6Ch+var_4], eax
0x100155b6  mov     eax, [ebp+arg_8]
0x100155b9  mov     ecx, [ebp+arg_4]
0x100155bc  push    ebx
0x100155bd  push    esi
0x100155be  mov     [esp+74h+Src], eax
0x100155c2  mov     eax, [ebp+arg_C]
0x100155c5  push    edi
0x100155c6  push    _critJet; lpCriticalSection
0x100155cc  mov     edi, [ebp+arg_18]
0x100155cf  mov     [esp+7Ch+var_50], eax
0x100155d3  xor     eax, eax
0x100155d5  mov     [esp+7Ch+var_60], ecx
0x100155d9  mov     [esp+7Ch+var_58], edi
0x100155dd  mov     [esp+7Ch+var_5C], 0F00FEh
0x100155e5  mov     [esp+7Ch+var_68], 0FFFFFFFFh
0x100155ed  mov     [esp+7Ch+var_44], 0
0x100155f5  mov     [esp+7Ch+var_4C], ax
0x100155fa  mov     [esp+7Ch+var_64], eax
0x100155fe  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10015604  test    edi, edi
0x10015606  jz      short loc_1001560E
0x10015608  mov     dword ptr [edi], 0FFFFFFFFh
0x1001560e  mov     esi, [ebp+arg_0]
0x10015611  push    esi
0x10015612  call    _FValidSesid@4; FValidSesid(x)
0x10015617  test    eax, eax
0x10015619  jnz     short loc_10015625
0x1001561b  mov     edi, 0FFFFFBB0h
0x10015620  jmp     loc_10015B2F
0x10015625  mov     ebx, [ebp+arg_14]
0x10015628  test    ebx, 0F0000000h
0x1001562e  jz      short loc_1001563A
0x10015630  mov     edi, 0FFFFFC15h
0x10015635  jmp     loc_10015B2F
0x1001563a  mov     ecx, [esp+78h+var_60]
0x1001563e  and     ebx, 7FFFFFFFh
0x10015644  mov     [esp+78h+var_48], ebx
0x10015648  cmp     ecx, _dbidInit
0x1001564e  jb      short loc_1001566F
0x10015650  cmp     ecx, 100h
0x10015656  jnb     short loc_1001566F
0x10015658  lea     eax, ds:0[ecx*4]
0x1001565f  cmp     _mpdbidpvdbfndef[eax], offset _vdbfndefInvalidDbid
0x10015669  mov     [esp+78h+var_54], eax
0x1001566d  jnz     short loc_10015689
0x1001566f  lea     eax, ds:0[ecx*4]
0x10015676  mov     [esp+78h+var_54], eax
0x1001567a  cmp     ecx, 0FFFFFFFFh
0x1001567d  jz      short loc_10015689
0x1001567f  mov     edi, 0FFFFFC0Eh
0x10015684  jmp     loc_10015B2F
0x10015689  mov     ecx, [esp+78h+Src]
0x1001568d  lea     eax, [esp+78h+var_4C]
0x10015691  test    ecx, ecx
0x10015693  mov     edx, offset _wszCursorNamePrefix; ".MU."
0x10015698  push    4
0x1001569a  cmovnz  eax, ecx
0x1001569d  mov     ecx, eax
0x1001569f  mov     [esp+7Ch+Src], eax
0x100156a3  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100156a8  test    eax, eax
0x100156aa  jnz     loc_1001573E
0x100156b0  push    0Ah; Radix
0x100156b2  push    eax; EndPtr
0x100156b3  mov     eax, [esp+80h+Src]
0x100156b7  add     eax, 8
0x100156ba  push    eax; String
0x100156bb  call    ds:__imp__wcstol
0x100156c1  mov     ecx, eax
0x100156c3  add     esp, 0Ch
0x100156c6  lea     ebx, ds:0[ecx*4]
0x100156cd  imul    eax, _mptableidisib[ebx], 68h ; 'h'
0x100156d4  cmp     esi, _rgsib[eax]
0x100156da  jnz     loc_1001561B
0x100156e0  push    0
0x100156e2  lea     eax, [esp+7Ch+var_68]
0x100156e6  push    eax
0x100156e7  push    ecx
0x100156e8  push    esi
0x100156e9  call    _ErrDispDupCursor@16; ErrDispDupCursor(x,x,x,x)
0x100156ee  mov     edi, eax
0x100156f0  test    edi, edi
0x100156f2  js      short loc_10015724
0x100156f4  mov     esi, [esp+78h+var_68]
0x100156f8  mov     edx, esi
0x100156fa  call    _AcmDispGetACM@8; AcmDispGetACM(x,x)
0x100156ff  push    eax
0x10015700  push    ecx
0x10015701  mov     edx, esi
0x10015703  call    _ErrSetAcmTableid@16; ErrSetAcmTableid(x,x,x,x)
0x10015708  mov     ecx, _rgvtdefname
0x1001570e  mov     eax, [ebx+ecx]
0x10015711  mov     [ecx+esi*4], eax
0x10015714  mov     ecx, [esp+78h+var_58]
0x10015718  test    ecx, ecx
0x1001571a  jz      short loc_10015722
0x1001571c  mov     eax, [esp+78h+var_68]
0x10015720  mov     [ecx], eax
0x10015722  test    edi, edi
0x10015724  jnz     loc_10015B22
0x1001572a  mov     eax, [esp+78h+var_64]
0x1001572e  cmp     eax, 0EE3h
0x10015733  jz      loc_10015B2D
0x10015739  jmp     loc_10015B26
0x1001573e  test    ebx, 800h
0x10015744  jz      loc_100157F9
0x1001574a  mov     ecx, [esp+78h+var_60]
0x1001574e  cmp     ecx, 0FFFFFFFFh
0x10015751  jz      loc_10015630
0x10015757  mov     edx, [esp+78h+var_54]
0x1001575b  cmp     _mpdbidpvdbfndef[edx], offset _vdbfndefRdb
0x10015765  jnz     loc_10015630
0x1001576b  mov     eax, ebx
0x1001576d  mov     [esp+78h+var_5C], 0
0x10015775  shr     eax, 0Ch
0x10015778  and     eax, 1
0x1001577b  test    edi, edi
0x1001577d  push    eax
0x1001577e  push    0
0x10015780  push    0
0x10015782  push    0
0x10015784  push    0
0x10015786  push    0FFFFFFFFh
0x10015788  push    0
0x1001578a  lea     eax, [esp+94h+var_5C]
0x1001578e  cmovnz  eax, edi
0x10015791  or      edx, 0FFFFFFFFh
0x10015794  push    eax
0x10015795  mov     eax, [esp+98h+Src]
0x10015799  push    eax
0x1001579a  push    0
0x1001579c  push    ecx
0x1001579d  mov     ecx, esi
0x1001579f  call    _ErrRmtOpenPassThrough@52; ErrRmtOpenPassThrough(x,x,x,x,x,x,x,x,x,x,x,x,x)
0x100157a4  mov     ecx, [esp+78h+var_58]
0x100157a8  mov     edi, eax
0x100157aa  mov     eax, [esp+78h+var_5C]
0x100157ae  cmp     eax, 0FFFFFFFFh
0x100157b1  jz      short loc_100157CA
0x100157b3  test    ecx, ecx
0x100157b5  jz      short loc_100157BF
0x100157b7  mov     eax, [ecx]
0x100157b9  mov     [esp+78h+var_68], eax
0x100157bd  jmp     short loc_100157CA
0x100157bf  push    eax
0x100157c0  push    esi
0x100157c1  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100157c6  mov     ecx, [esp+78h+var_58]
0x100157ca  test    edi, edi
0x100157cc  jnz     loc_10015B2F
0x100157d2  test    ebx, 1000h
0x100157d8  jz      loc_10015B2F
0x100157de  test    ecx, ecx
0x100157e0  jz      loc_10015B2F
0x100157e6  cmp     dword ptr [ecx], 0FFFFFFFFh
0x100157e9  jnz     loc_10015B2F
0x100157ef  mov     edi, 0BF5h
0x100157f4  jmp     loc_10015B2F
0x100157f9  test    ebx, 4100h
0x100157ff  jz      short loc_10015804
0x10015801  and     ebx, 0FFFFFFFBh
0x10015804  mov     edi, [esp+78h+var_60]
0x10015808  cmp     edi, 0FFFFFFFFh
0x1001580b  jz      short loc_10015858
0x1001580d  mov     edx, edi
0x1001580f  mov     ecx, esi
0x10015811  call    _IsJetIsam@8; IsJetIsam(x,x)
0x10015816  test    eax, eax
0x10015818  jnz     loc_100158C9
0x1001581e  mov     edx, [esp+78h+var_54]
0x10015822  mov     eax, _mpdbidiiscb[edx]
0x10015828  lea     eax, [eax+eax*4]
0x1001582b  cmp     Src[eax*4], 0
0x10015833  jz      short loc_10015845
0x10015835  cmp     _mpdbidpvdbfndef[edx], offset _vdbfndefRdb
0x1001583f  jnz     loc_100158C9
0x10015845  mov     ecx, [esp+78h+Src]
0x10015849  call    FLikelySQLString
0x1001584e  xor     ecx, ecx
0x10015850  test    eax, eax
0x10015852  jz      loc_1001591C
0x10015858  push    esi
0x10015859  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001585e  lea     eax, [esp+78h+var_68]
0x10015862  push    eax
0x10015863  push    0
0x10015865  push    ebx
0x10015866  push    [ebp+arg_10]
0x10015869  push    [esp+88h+var_50]
0x1001586d  push    [esp+8Ch+Src]
0x10015871  push    edi
0x10015872  push    esi
0x10015873  call    _ErrTrySQLString@32; ErrTrySQLString(x,x,x,x,x,x,x,x)
0x10015878  mov     edi, eax
0x1001587a  test    edi, edi
0x1001587c  jnz     loc_10015AB6
0x10015882  test    ebx, 0C00000h
0x10015888  jz      loc_10015AB8
0x1001588e  mov     eax, [esp+78h+var_68]
0x10015892  push    _critJet; lpCriticalSection
0x10015898  mov     [esp+7Ch+var_50], eax
0x1001589c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100158a2  push    esi
0x100158a3  call    _FValidSesid@4; FValidSesid(x)
0x100158a8  test    eax, eax
0x100158aa  jnz     loc_10015A61
0x100158b0  push    _critJet; lpCriticalSection
0x100158b6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100158bc  mov     [esp+78h+var_64], 0FFFFFBB0h
0x100158c4  jmp     loc_10015AB8
0x100158c9  push    5
0x100158cb  lea     eax, [esp+7Ch+var_2C]
0x100158cf  mov     [esp+7Ch+var_3C], 28h ; '('
0x100158d7  mov     [esp+7Ch+var_30], eax
0x100158db  lea     eax, [esp+7Ch+var_3C]
0x100158df  push    eax
0x100158e0  mov     eax, [esp+80h+Src]
0x100158e4  push    eax
0x100158e5  push    offset _wszTcObject; "Tables"
0x100158ea  push    0
0x100158ec  push    edi
0x100158ed  push    esi
0x100158ee  call    _ErrDispGetObjectInfo@28; ErrDispGetObjectInfo(x,x,x,x,x,x,x)
0x100158f3  test    eax, eax
0x100158f5  js      loc_10015858
0x100158fb  lea     eax, [esp+78h+var_44]
0x100158ff  push    eax
0x10015900  push    [esp+7Ch+Src]
0x10015904  push    offset _wszTcObject; "Tables"
0x10015909  push    edi
0x1001590a  push    esi
0x1001590b  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10015910  test    eax, eax
0x10015912  jns     short loc_1001594A
0x10015914  push    esi
0x10015915  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001591a  xor     ecx, ecx
0x1001591c  test    ebx, 100h
0x10015922  jz      short loc_10015927
0x10015924  and     ebx, 0FFFFFFBFh
0x10015927  test    bl, 40h
0x1001592a  jnz     loc_10015A40
0x10015930  test    ecx, ecx
0x10015932  jnz     loc_10015A40
0x10015938  test    ebx, 100h
0x1001593e  jz      short loc_10015958
0x10015940  mov     edi, 0FFFFF433h
0x10015945  jmp     loc_10015B2F
0x1001594a  cmp     [esp+78h+var_28], 5
0x1001594f  jnz     short loc_1001591A
0x10015951  mov     ecx, 1
0x10015956  jmp     short loc_1001591C
0x10015958  mov     eax, [esp+78h+var_54]
0x1001595c  cmp     _mpdbidpvdbfndef[eax], offset _vdbfndefRdb
0x10015966  jz      loc_10015630
0x1001596c  mov     eax, _mpdbidiiscb[eax]
0x10015972  lea     eax, [eax+eax*4]
0x10015975  cmp     Src[eax*4], 0
0x1001597d  jz      short loc_100159F2
0x1001597f  push    0
0x10015981  lea     eax, [esp+7Ch+var_5C]
0x10015985  push    eax
0x10015986  push    0
0x10015988  push    0
0x1001598a  push    0
0x1001598c  push    [esp+8Ch+var_44]
0x10015990  push    edi
0x10015991  push    esi
0x10015992  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x10015997  mov     edi, eax
0x10015999  test    edi, edi
0x1001599b  js      loc_10015724
0x100159a1  mov     eax, [esp+78h+var_5C]
0x100159a5  test    al, 0F8h
0x100159a7  jnz     short loc_100159CC
0x100159a9  push    0; int
0x100159ab  push    0; int
0x100159ad  push    0; int
0x100159af  push    0FFFFE049h; int
0x100159b4  push    0; void *
0x100159b6  push    0; void *
0x100159b8  push    [esp+90h+Src]; Src
0x100159bc  push    esi; int
0x100159bd  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100159c2  mov     edi, 0FFFFF88Dh
0x100159c7  jmp     loc_10015B2F
0x100159cc  mov     edx, [esp+78h+var_48]
0x100159d0  test    al, 0D0h
0x100159d2  jnz     short loc_100159D7
0x100159d4  or      edx, 8
0x100159d7  mov     edi, [esp+78h+var_60]
0x100159db  mov     ecx, edx
  ... truncated ...
```
