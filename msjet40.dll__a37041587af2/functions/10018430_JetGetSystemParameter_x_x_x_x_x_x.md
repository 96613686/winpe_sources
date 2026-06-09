# JetGetSystemParameter(x,x,x,x,x,x)

- ea: `0x10018430`
- end: `0x10018b1f`
- name: `_JetGetSystemParameter@24`
- size: `1775`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x10029220`
- `0x100a8c1d`
- `0x101189a2`

## callees

- `0x10018430`
- `0x1003e830`
- `0x1003e9b0`
- `0x10050190`
- `0x10124a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001845a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001845a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018479`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018564`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100185c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001864a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100186c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001870c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018752`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018800`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001896d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018a0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018aae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018af4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018b0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018564`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100185c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001864a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100186c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001870c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018752`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018800`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001896d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018a0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018aae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018af4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018b0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10018488`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10018488`

## pseudocode

```c
int __stdcall JetGetSystemParameter(int a1, _DWORD *a2, int a3, _DWORD *a4, wchar_t *Destination, unsigned int a6)
{
  int v6; // esi
  struct _RTL_CRITICAL_SECTION *v7; // eax
  int result; // eax
  _DWORD *v9; // edx
  int v10; // ecx
  const unsigned __int16 *v11; // edx
  unsigned int v12; // ecx
  size_t v13; // edi
  char *v14; // ebx
  char *v15; // ecx
  __int16 v16; // ax
  int v17; // ecx
  size_t v18; // edi
  int v19; // ecx
  int IsibOfSesid; // esi
  int v21; // eax
  int v22; // ecx
  int v23; // esi
  int v24; // ecx
  int v25; // esi
  int v26; // ecx
  int v27; // esi
  int v28; // ecx
  int v29; // esi
  int v30; // ecx
  int v31; // esi
  int v32; // ecx
  int v33; // esi
  int v34; // ecx
  int v35; // esi
  char *v36; // eax
  void *v37; // ecx
  char *v38; // edi
  _DWORD **v39; // eax
  _DWORD **v40; // edx
  _DWORD *v41; // edx
  void *v42; // [esp+8h] [ebp-4h] BYREF

  v6 = a1 - 144;
  if ( a1 - 144 <= -1 || v6 >= 64 )
    v6 = -1;
  if ( critJet )
  {
    EnterCriticalSection(critJet);
  }
  else
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)_malloc(0x18u);
    critJet = v7;
    if ( !v7 )
      return -1011;
    InitializeCriticalSection(v7);
    EnterCriticalSection(critJet);
  }
  switch ( a3 )
  {
    case 0:
      if ( v6 == -1 )
        goto LABEL_74;
      v11 = (const unsigned __int16 *)((char *)rgtib + 2316 * v6);
      v12 = wcslen(v11);
      v13 = a6 >> 1;
      if ( v12 + 1 <= a6 >> 1 )
        v13 = v12 + 1;
      wcsncpy(Destination, v11, v13);
      Destination[v13 - 1] = 0;
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 2:
      IsibOfSesid = UtilGetIsibOfSesid(a2);
      if ( IsibOfSesid == -1 )
        goto LABEL_68;
      ClearErrorInfo(v19);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EB48[26 * IsibOfSesid];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 4:
      v23 = UtilGetIsibOfSesid(a2);
      if ( v23 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v22);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EB7C[26 * v23];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 6:
    case 8:
    case 57:
    case 58:
    case 59:
    case 60:
    case 61:
    case 62:
    case 63:
    case 65:
    case 66:
    case 70:
      if ( v6 == -1 || !*((_DWORD *)rgtib + 579 * v6 + 263) )
        goto LABEL_74;
      if ( UtilGetIsibOfSesid(a2) == -1 )
        goto LABEL_68;
      ClearErrorInfo(a2);
      if ( a6 < 4 )
        goto LABEL_97;
      v9 = (_DWORD *)*a2;
      switch ( a3 )
      {
        case 6:
          v10 = v9[13];
          goto LABEL_27;
        case 8:
          v10 = 4 * dword_10130544;
          goto LABEL_27;
        case 57:
          v10 = v9[14];
          goto LABEL_27;
        case 58:
          v10 = v9[17] == 0;
          goto LABEL_27;
        case 59:
          v10 = v9[18] == 0;
          goto LABEL_27;
        case 60:
          v10 = v9[19];
          goto LABEL_27;
        case 61:
          v10 = v9[20];
          goto LABEL_27;
        case 62:
          v10 = v9[22];
          goto LABEL_27;
        case 63:
          v10 = v9[23];
          goto LABEL_27;
        case 65:
          v10 = v9[24] != 0;
          goto LABEL_27;
        case 66:
          v10 = v9[21];
          goto LABEL_27;
        case 70:
          v10 = v9[25];
LABEL_27:
          *a4 = v10;
          break;
        default:
          break;
      }
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 7:
      ClearErrorInfo(a2);
      if ( !a4 )
        goto LABEL_97;
      *a4 = *(_DWORD *)&wQueryTimeout;
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 25:
      ClearErrorInfo(a2);
      if ( !a4 )
        goto LABEL_97;
      *a4 = *(_DWORD *)&wLoginTimeout;
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 32:
      v21 = UtilGetIsibOfSesid(a2);
      if ( v21 == -1 )
        goto LABEL_68;
      *a4 = dword_1016EB8C[26 * v21];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 38:
      v27 = UtilGetIsibOfSesid(a2);
      if ( v27 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v26);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EB84[26 * v27] << 31 >> 31;
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 39:
      v25 = UtilGetIsibOfSesid(a2);
      if ( v25 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v24);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EB80[26 * v25];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 48:
      v29 = UtilGetIsibOfSesid(a2);
      if ( v29 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v28);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EB9C[26 * v29];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 49:
      v31 = UtilGetIsibOfSesid(a2);
      if ( v31 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v30);
      if ( !a4 )
        goto LABEL_97;
      *a4 = (dword_1016EB84[26 * v31] & 2u) >> 1;
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 52:
      if ( a6 < 0xC )
        goto LABEL_97;
      v41 = (char *)rgtib + 2316 * v6;
      *(_DWORD *)Destination = v41[566];
      *((_DWORD *)Destination + 1) = v41[567];
      *((_DWORD *)Destination + 2) = v41[568];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 55:
      if ( v6 == -1 )
        goto LABEL_74;
      v14 = (char *)rgtib + 2316 * v6;
      v15 = v14 + 520;
      do
      {
        v16 = *(_WORD *)v15;
        v15 += 2;
      }
      while ( v16 );
      v17 = (v15 - (v14 + 522)) >> 1;
      v18 = a6 >> 1;
      if ( v17 + 1 <= a6 >> 1 )
        v18 = v17 + 1;
      wcsncpy(Destination, (const wchar_t *)v14 + 260, v18);
      Destination[v18 - 1] = 0;
      if ( !a4 )
        goto LABEL_94;
      *a4 = *((_DWORD *)v14 + 260);
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 64:
      if ( !*((_DWORD *)rgtib + 579 * v6 + 263) )
        goto LABEL_74;
      *a4 = *((_DWORD *)rgtib + 579 * v6 + 572);
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 67:
      if ( !*((_DWORD *)rgtib + 579 * v6 + 263) )
      {
LABEL_74:
        LeaveCriticalSection(critJet);
        return -1029;
      }
      *a4 = *((_DWORD *)rgtib + 579 * v6 + 573);
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 69:
      v35 = UtilGetIsibOfSesid(a2);
      if ( v35 == -1 )
        goto LABEL_68;
      ClearErrorInfo(v34);
      if ( !a4 )
        goto LABEL_97;
      *a4 = dword_1016EBA0[26 * v35];
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    case 72:
      v33 = UtilGetIsibOfSesid(a2);
      if ( v33 == -1 )
      {
LABEL_68:
        LeaveCriticalSection(critJet);
        result = -1104;
      }
      else
      {
        ClearErrorInfo(v32);
        if ( !a4 )
          goto LABEL_97;
        *a4 = (dword_1016EB84[26 * v33] & 4u) >> 2;
        LeaveCriticalSection(critJet);
        result = 0;
      }
      break;
    case 73:
      v36 = (char *)rgtib + 2316 * v6;
      if ( !*((_DWORD *)v36 + 263) )
        return -1029;
      v37 = 0;
      v42 = 0;
      if ( a4 )
      {
        if ( !g_pIJetES )
        {
          *a4 = dword_1013116C;
          LeaveCriticalSection(critJet);
          return 0;
        }
        v38 = (char *)rgtib + 2316 * v6;
        if ( v38 )
        {
          if ( !*((_DWORD *)v38 + 574) )
          {
            (*(void (__thiscall **)(_DWORD, void *, char *))(*(_DWORD *)g_pIJetES + 32))(
              *(_DWORD *)(*(_DWORD *)g_pIJetES + 32),
              g_pIJetES,
              v36 + 2296);
            v37 = v42;
          }
          v39 = (_DWORD **)*((_DWORD *)v38 + 574);
        }
        else
        {
          v39 = 0;
        }
        v40 = 0;
        if ( v38 )
          v40 = v39;
        if ( v40 )
        {
          if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, void **))**v40)(**v40, v40, &IID_IJetESInstance2, &v42) >= 0 )
            (*(void (__thiscall **)(_DWORD, void *, _DWORD *))(*(_DWORD *)v42 + 84))(
              *(_DWORD *)(*(_DWORD *)v42 + 84),
              v42,
              a4);
          v37 = v42;
        }
        if ( v37 )
          (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v37 + 8))(*(_DWORD *)(*(_DWORD *)v37 + 8), v37);
      }
LABEL_94:
      LeaveCriticalSection(critJet);
      result = 0;
      break;
    default:
LABEL_97:
      LeaveCriticalSection(critJet);
      result = -1003;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x10018430  mov     edi, edi
0x10018432  push    ebp
0x10018433  mov     ebp, esp
0x10018435  sub     esp, 8
0x10018438  push    esi
0x10018439  mov     esi, [ebp+arg_0]
0x1001843c  add     esi, 0FFFFFF70h
0x10018442  cmp     esi, 0FFFFFFFFh
0x10018445  jle     short loc_1001844C
0x10018447  cmp     esi, 40h ; '@'
0x1001844a  jl      short loc_1001844F
0x1001844c  or      esi, 0FFFFFFFFh
0x1001844f  mov     eax, _critJet
0x10018454  test    eax, eax
0x10018456  jnz     short loc_10018487
0x10018458  push    18h; Size
0x1001845a  call    ds:__imp__malloc
0x10018460  add     esp, 4
0x10018463  mov     _critJet, eax
0x10018468  test    eax, eax
0x1001846a  jnz     short loc_10018478
0x1001846c  mov     eax, 0FFFFFC0Dh
0x10018471  pop     esi
0x10018472  mov     esp, ebp
0x10018474  pop     ebp
0x10018475  retn    18h
0x10018478  push    eax; lpCriticalSection
0x10018479  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001847f  push    _critJet
0x10018485  jmp     short loc_10018488
0x10018487  push    eax; lpCriticalSection
0x10018488  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001848e  push    ebx
0x1001848f  push    edi; unsigned int
0x10018490  mov     edi, [ebp+arg_8]
0x10018493  cmp     edi, 49h; switch 74 cases
0x10018496  ja      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x1001849c  movzx   eax, ds:byte_10018B6C[edi]
0x100184a3  jmp     ds:jpt_100184A3[eax*4]; switch jump
0x100184aa  cmp     esi, 0FFFFFFFFh; jumptable 100184A3 cases 6,8,57-63,65,66,70
0x100184ad  jz      loc_10018993
0x100184b3  mov     eax, _rgtib
0x100184b8  imul    ecx, esi, 90Ch
0x100184be  cmp     dword ptr [ecx+eax+41Ch], 0
0x100184c6  jz      loc_10018993
0x100184cc  mov     esi, [ebp+arg_4]
0x100184cf  mov     ecx, esi
0x100184d1  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100184d6  cmp     eax, 0FFFFFFFFh
0x100184d9  jz      loc_100188F9
0x100184df  push    esi
0x100184e0  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100184e5  cmp     [ebp+arg_14], 4
0x100184e9  jb      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x100184ef  mov     edx, [esi]
0x100184f1  add     edi, 0FFFFFFFAh; switch 65 cases
0x100184f4  cmp     edi, 40h
0x100184f7  ja      short def_10018500; jumptable 10018500 default case, cases 7,9-56,64,67-69
0x100184f9  movzx   eax, ds:byte_10018BEC[edi]
0x10018500  jmp     ds:jpt_10018500[eax*4]; switch jump
0x10018507  mov     ecx, [edx+34h]; jumptable 10018500 case 6
0x1001850a  jmp     short loc_10018559
0x1001850c  mov     eax, dword_10130544; jumptable 10018500 case 8
0x10018511  lea     ecx, ds:0[eax*4]
0x10018518  jmp     short loc_10018559
0x1001851a  mov     ecx, [edx+38h]; jumptable 10018500 case 57
0x1001851d  jmp     short loc_10018559
0x1001851f  xor     ecx, ecx; jumptable 10018500 case 58
0x10018521  cmp     [edx+44h], ecx
0x10018524  setz    cl
0x10018527  jmp     short loc_10018559
0x10018529  xor     ecx, ecx; jumptable 10018500 case 59
0x1001852b  cmp     [edx+48h], ecx
0x1001852e  setz    cl
0x10018531  jmp     short loc_10018559
0x10018533  mov     ecx, [edx+4Ch]; jumptable 10018500 case 60
0x10018536  jmp     short loc_10018559
0x10018538  mov     ecx, [edx+50h]; jumptable 10018500 case 61
0x1001853b  jmp     short loc_10018559
0x1001853d  mov     ecx, [edx+54h]; jumptable 10018500 case 66
0x10018540  jmp     short loc_10018559
0x10018542  mov     ecx, [edx+58h]; jumptable 10018500 case 62
0x10018545  jmp     short loc_10018559
0x10018547  mov     ecx, [edx+5Ch]; jumptable 10018500 case 63
0x1001854a  jmp     short loc_10018559
0x1001854c  xor     ecx, ecx; jumptable 10018500 case 65
0x1001854e  cmp     [edx+60h], ecx
0x10018551  setnz   cl
0x10018554  jmp     short loc_10018559
0x10018556  mov     ecx, [edx+64h]; jumptable 10018500 case 70
0x10018559  mov     eax, [ebp+arg_C]
0x1001855c  mov     [eax], ecx
0x1001855e  push    _critJet; jumptable 10018500 default case, cases 7,9-56,64,67-69
0x10018564  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001856a  pop     edi
0x1001856b  pop     ebx
0x1001856c  xor     eax, eax
0x1001856e  pop     esi
0x1001856f  mov     esp, ebp
0x10018571  pop     ebp
0x10018572  retn    18h
0x10018575  cmp     esi, 0FFFFFFFFh; jumptable 100184A3 case 0
0x10018578  jz      loc_10018993
0x1001857e  imul    edx, esi, 90Ch
0x10018584  add     edx, _rgtib
0x1001858a  mov     ecx, edx
0x1001858c  lea     esi, [ecx+2]
0x1001858f  nop
0x10018590  mov     ax, [ecx]
0x10018593  add     ecx, 2
0x10018596  test    ax, ax
0x10018599  jnz     short loc_10018590
0x1001859b  mov     edi, [ebp+arg_14]
0x1001859e  sub     ecx, esi
0x100185a0  mov     esi, [ebp+Destination]
0x100185a3  sar     ecx, 1
0x100185a5  shr     edi, 1
0x100185a7  lea     eax, [ecx+1]
0x100185aa  cmp     eax, edi
0x100185ac  cmovbe  edi, eax
0x100185af  push    edi; Count
0x100185b0  push    edx; Source
0x100185b1  push    esi; Destination
0x100185b2  call    _wcsncpy
0x100185b7  add     esp, 0Ch
0x100185ba  xor     eax, eax
0x100185bc  mov     [esi+edi*2-2], ax
0x100185c1  push    _critJet; lpCriticalSection
0x100185c7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100185cd  pop     edi
0x100185ce  pop     ebx
0x100185cf  xor     eax, eax
0x100185d1  pop     esi
0x100185d2  mov     esp, ebp
0x100185d4  pop     ebp
0x100185d5  retn    18h
0x100185d8  cmp     esi, 0FFFFFFFFh; jumptable 100184A3 case 55
0x100185db  jz      loc_10018993
0x100185e1  imul    ebx, esi, 90Ch
0x100185e7  add     ebx, _rgtib
0x100185ed  lea     edx, [ebx+208h]
0x100185f3  mov     ecx, edx
0x100185f5  lea     esi, [ecx+2]
0x100185f8  nop     dword ptr [eax+eax+00000000h]
0x10018600  mov     ax, [ecx]
0x10018603  add     ecx, 2
0x10018606  test    ax, ax
0x10018609  jnz     short loc_10018600
0x1001860b  mov     edi, [ebp+arg_14]
0x1001860e  sub     ecx, esi
0x10018610  mov     esi, [ebp+Destination]
0x10018613  sar     ecx, 1
0x10018615  shr     edi, 1
0x10018617  lea     eax, [ecx+1]
0x1001861a  cmp     eax, edi
0x1001861c  cmovbe  edi, eax
0x1001861f  push    edi; Count
0x10018620  push    edx; Source
0x10018621  push    esi; Destination
0x10018622  call    _wcsncpy
0x10018627  mov     ecx, [ebp+arg_C]
0x1001862a  xor     eax, eax
0x1001862c  add     esp, 0Ch
0x1001862f  mov     [esi+edi*2-2], ax
0x10018634  test    ecx, ecx
0x10018636  jz      loc_10018AA8
0x1001863c  mov     eax, [ebx+410h]
0x10018642  mov     [ecx], eax
0x10018644  push    _critJet; lpCriticalSection
0x1001864a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018650  pop     edi
0x10018651  pop     ebx
0x10018652  xor     eax, eax
0x10018654  pop     esi
0x10018655  mov     esp, ebp
0x10018657  pop     ebp
0x10018658  retn    18h
0x1001865b  mov     ecx, [ebp+arg_4]; jumptable 100184A3 case 2
0x1001865e  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10018663  mov     esi, eax
0x10018665  cmp     esi, 0FFFFFFFFh
0x10018668  jz      loc_100188F9
0x1001866e  push    ecx
0x1001866f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10018674  mov     ecx, [ebp+arg_C]
0x10018677  test    ecx, ecx
0x10018679  jz      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x1001867f  imul    eax, esi, 68h ; 'h'
0x10018682  mov     eax, dword_1016EB48[eax]
0x10018688  mov     [ecx], eax
0x1001868a  push    _critJet; lpCriticalSection
0x10018690  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018696  pop     edi
0x10018697  pop     ebx
0x10018698  xor     eax, eax
0x1001869a  pop     esi
0x1001869b  mov     esp, ebp
0x1001869d  pop     ebp
0x1001869e  retn    18h
0x100186a1  mov     ecx, [ebp+arg_4]; jumptable 100184A3 case 32
0x100186a4  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100186a9  cmp     eax, 0FFFFFFFFh
0x100186ac  jz      loc_100188F9
0x100186b2  imul    eax, 68h ; 'h'
0x100186b5  mov     ecx, dword_1016EB8C[eax]
0x100186bb  mov     eax, [ebp+arg_C]
0x100186be  mov     [eax], ecx
0x100186c0  push    _critJet; lpCriticalSection
0x100186c6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100186cc  pop     edi
0x100186cd  pop     ebx
0x100186ce  xor     eax, eax
0x100186d0  pop     esi
0x100186d1  mov     esp, ebp
0x100186d3  pop     ebp
0x100186d4  retn    18h
0x100186d7  mov     ecx, [ebp+arg_4]; jumptable 100184A3 case 4
0x100186da  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100186df  mov     esi, eax
0x100186e1  cmp     esi, 0FFFFFFFFh
0x100186e4  jz      loc_100188F9
0x100186ea  push    ecx
0x100186eb  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100186f0  mov     ecx, [ebp+arg_C]
0x100186f3  test    ecx, ecx
0x100186f5  jz      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x100186fb  imul    eax, esi, 68h ; 'h'
0x100186fe  mov     eax, dword_1016EB7C[eax]
0x10018704  mov     [ecx], eax
0x10018706  push    _critJet; lpCriticalSection
0x1001870c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018712  pop     edi
0x10018713  pop     ebx
0x10018714  xor     eax, eax
0x10018716  pop     esi
0x10018717  mov     esp, ebp
0x10018719  pop     ebp
0x1001871a  retn    18h
0x1001871d  mov     ecx, [ebp+arg_4]; jumptable 100184A3 case 39
0x10018720  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10018725  mov     esi, eax
0x10018727  cmp     esi, 0FFFFFFFFh
0x1001872a  jz      loc_100188F9
0x10018730  push    ecx
0x10018731  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10018736  mov     ecx, [ebp+arg_C]
0x10018739  test    ecx, ecx
0x1001873b  jz      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x10018741  imul    eax, esi, 68h ; 'h'
0x10018744  mov     eax, dword_1016EB80[eax]
0x1001874a  mov     [ecx], eax
0x1001874c  push    _critJet; lpCriticalSection
0x10018752  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018758  pop     edi
0x10018759  pop     ebx
0x1001875a  xor     eax, eax
0x1001875c  pop     esi
0x1001875d  mov     esp, ebp
0x1001875f  pop     ebp
0x10018760  retn    18h
0x10018763  push    [ebp+arg_4]; jumptable 100184A3 case 7
0x10018766  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001876b  mov     ecx, [ebp+arg_C]
0x1001876e  test    ecx, ecx
0x10018770  jz      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x10018776  mov     eax, _wQueryTimeout
0x1001877b  mov     [ecx], eax
0x1001877d  push    _critJet; lpCriticalSection
0x10018783  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018789  pop     edi
0x1001878a  pop     ebx
0x1001878b  xor     eax, eax
0x1001878d  pop     esi
0x1001878e  mov     esp, ebp
0x10018790  pop     ebp
0x10018791  retn    18h
0x10018794  push    [ebp+arg_4]; jumptable 100184A3 case 25
0x10018797  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001879c  mov     ecx, [ebp+arg_C]
0x1001879f  test    ecx, ecx
0x100187a1  jz      def_100184A3; jumptable 100184A3 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x100187a7  mov     eax, _wLoginTimeout
0x100187ac  mov     [ecx], eax
0x100187ae  push    _critJet; lpCriticalSection
0x100187b4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100187ba  pop     edi
0x100187bb  pop     ebx
0x100187bc  xor     eax, eax
0x100187be  pop     esi
0x100187bf  mov     esp, ebp
0x100187c1  pop     ebp
0x100187c2  retn    18h
0x100187c5  mov     ecx, [ebp+arg_4]; jumptable 100184A3 case 38
0x100187c8  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100187cd  mov     esi, eax
0x100187cf  cmp     esi, 0FFFFFFFFh
0x100187d2  jz      loc_100188F9
0x100187d8  push    ecx
0x100187d9  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100187de  mov     ecx, [ebp+arg_C]
  ... truncated ...
```
