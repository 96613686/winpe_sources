# JetGetSystemParameter(x,x,x,x,x,x)

- ea: `0x100182f0`
- end: `0x100189df`
- name: `_JetGetSystemParameter@24`
- size: `1775`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x10029050`
- `0x100a8a8d`
- `0x101187f2`

## callees

- `0x100182f0`
- `0x1003e6a0`
- `0x1003e820`
- `0x10050000`
- `0x101248d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001831a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1001831a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018339`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001850a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018550`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100185cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018674`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100186c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018706`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001882d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018859`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001887f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001896e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018424`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001850a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018550`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100185cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018643`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018674`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100186c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018706`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100187f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001882d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10018859`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001887f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100188cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001896e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100189cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10018348`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10018348`

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
      *a4 = dword_1016EAA8[26 * IsibOfSesid];
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
      *a4 = dword_1016EADC[26 * v23];
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
          v10 = 4 * dword_101304AC;
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
      *a4 = dword_1016EAEC[26 * v21];
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
      *a4 = dword_1016EAE4[26 * v27] << 31 >> 31;
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
      *a4 = dword_1016EAE0[26 * v25];
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
      *a4 = dword_1016EAFC[26 * v29];
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
      *a4 = (dword_1016EAE4[26 * v31] & 2u) >> 1;
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
      *a4 = dword_1016EB00[26 * v35];
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
        *a4 = (dword_1016EAE4[26 * v33] & 4u) >> 2;
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
          *a4 = dword_101310BC;
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
0x100182f0  mov     edi, edi
0x100182f2  push    ebp
0x100182f3  mov     ebp, esp
0x100182f5  sub     esp, 8
0x100182f8  push    esi
0x100182f9  mov     esi, [ebp+arg_0]
0x100182fc  add     esi, 0FFFFFF70h
0x10018302  cmp     esi, 0FFFFFFFFh
0x10018305  jle     short loc_1001830C
0x10018307  cmp     esi, 40h ; '@'
0x1001830a  jl      short loc_1001830F
0x1001830c  or      esi, 0FFFFFFFFh
0x1001830f  mov     eax, _critJet
0x10018314  test    eax, eax
0x10018316  jnz     short loc_10018347
0x10018318  push    18h; Size
0x1001831a  call    ds:__imp__malloc
0x10018320  add     esp, 4
0x10018323  mov     _critJet, eax
0x10018328  test    eax, eax
0x1001832a  jnz     short loc_10018338
0x1001832c  mov     eax, 0FFFFFC0Dh
0x10018331  pop     esi
0x10018332  mov     esp, ebp
0x10018334  pop     ebp
0x10018335  retn    18h
0x10018338  push    eax; lpCriticalSection
0x10018339  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x1001833f  push    _critJet
0x10018345  jmp     short loc_10018348
0x10018347  push    eax; lpCriticalSection
0x10018348  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001834e  push    ebx
0x1001834f  push    edi; unsigned int
0x10018350  mov     edi, [ebp+arg_8]
0x10018353  cmp     edi, 49h; switch 74 cases
0x10018356  ja      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x1001835c  movzx   eax, ds:byte_10018A2C[edi]
0x10018363  jmp     ds:jpt_10018363[eax*4]; switch jump
0x1001836a  cmp     esi, 0FFFFFFFFh; jumptable 10018363 cases 6,8,57-63,65,66,70
0x1001836d  jz      loc_10018853
0x10018373  mov     eax, _rgtib
0x10018378  imul    ecx, esi, 90Ch
0x1001837e  cmp     dword ptr [ecx+eax+41Ch], 0
0x10018386  jz      loc_10018853
0x1001838c  mov     esi, [ebp+arg_4]
0x1001838f  mov     ecx, esi
0x10018391  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10018396  cmp     eax, 0FFFFFFFFh
0x10018399  jz      loc_100187B9
0x1001839f  push    esi
0x100183a0  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100183a5  cmp     [ebp+arg_14], 4
0x100183a9  jb      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x100183af  mov     edx, [esi]
0x100183b1  add     edi, 0FFFFFFFAh; switch 65 cases
0x100183b4  cmp     edi, 40h
0x100183b7  ja      short def_100183C0; jumptable 100183C0 default case, cases 7,9-56,64,67-69
0x100183b9  movzx   eax, ds:byte_10018AAC[edi]
0x100183c0  jmp     ds:jpt_100183C0[eax*4]; switch jump
0x100183c7  mov     ecx, [edx+34h]; jumptable 100183C0 case 6
0x100183ca  jmp     short loc_10018419
0x100183cc  mov     eax, dword_101304AC; jumptable 100183C0 case 8
0x100183d1  lea     ecx, ds:0[eax*4]
0x100183d8  jmp     short loc_10018419
0x100183da  mov     ecx, [edx+38h]; jumptable 100183C0 case 57
0x100183dd  jmp     short loc_10018419
0x100183df  xor     ecx, ecx; jumptable 100183C0 case 58
0x100183e1  cmp     [edx+44h], ecx
0x100183e4  setz    cl
0x100183e7  jmp     short loc_10018419
0x100183e9  xor     ecx, ecx; jumptable 100183C0 case 59
0x100183eb  cmp     [edx+48h], ecx
0x100183ee  setz    cl
0x100183f1  jmp     short loc_10018419
0x100183f3  mov     ecx, [edx+4Ch]; jumptable 100183C0 case 60
0x100183f6  jmp     short loc_10018419
0x100183f8  mov     ecx, [edx+50h]; jumptable 100183C0 case 61
0x100183fb  jmp     short loc_10018419
0x100183fd  mov     ecx, [edx+54h]; jumptable 100183C0 case 66
0x10018400  jmp     short loc_10018419
0x10018402  mov     ecx, [edx+58h]; jumptable 100183C0 case 62
0x10018405  jmp     short loc_10018419
0x10018407  mov     ecx, [edx+5Ch]; jumptable 100183C0 case 63
0x1001840a  jmp     short loc_10018419
0x1001840c  xor     ecx, ecx; jumptable 100183C0 case 65
0x1001840e  cmp     [edx+60h], ecx
0x10018411  setnz   cl
0x10018414  jmp     short loc_10018419
0x10018416  mov     ecx, [edx+64h]; jumptable 100183C0 case 70
0x10018419  mov     eax, [ebp+arg_C]
0x1001841c  mov     [eax], ecx
0x1001841e  push    _critJet; jumptable 100183C0 default case, cases 7,9-56,64,67-69
0x10018424  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001842a  pop     edi
0x1001842b  pop     ebx
0x1001842c  xor     eax, eax
0x1001842e  pop     esi
0x1001842f  mov     esp, ebp
0x10018431  pop     ebp
0x10018432  retn    18h
0x10018435  cmp     esi, 0FFFFFFFFh; jumptable 10018363 case 0
0x10018438  jz      loc_10018853
0x1001843e  imul    edx, esi, 90Ch
0x10018444  add     edx, _rgtib
0x1001844a  mov     ecx, edx
0x1001844c  lea     esi, [ecx+2]
0x1001844f  nop
0x10018450  mov     ax, [ecx]
0x10018453  add     ecx, 2
0x10018456  test    ax, ax
0x10018459  jnz     short loc_10018450
0x1001845b  mov     edi, [ebp+arg_14]
0x1001845e  sub     ecx, esi
0x10018460  mov     esi, [ebp+Destination]
0x10018463  sar     ecx, 1
0x10018465  shr     edi, 1
0x10018467  lea     eax, [ecx+1]
0x1001846a  cmp     eax, edi
0x1001846c  cmovbe  edi, eax
0x1001846f  push    edi; Count
0x10018470  push    edx; Source
0x10018471  push    esi; Destination
0x10018472  call    _wcsncpy
0x10018477  add     esp, 0Ch
0x1001847a  xor     eax, eax
0x1001847c  mov     [esi+edi*2-2], ax
0x10018481  push    _critJet; lpCriticalSection
0x10018487  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001848d  pop     edi
0x1001848e  pop     ebx
0x1001848f  xor     eax, eax
0x10018491  pop     esi
0x10018492  mov     esp, ebp
0x10018494  pop     ebp
0x10018495  retn    18h
0x10018498  cmp     esi, 0FFFFFFFFh; jumptable 10018363 case 55
0x1001849b  jz      loc_10018853
0x100184a1  imul    ebx, esi, 90Ch
0x100184a7  add     ebx, _rgtib
0x100184ad  lea     edx, [ebx+208h]
0x100184b3  mov     ecx, edx
0x100184b5  lea     esi, [ecx+2]
0x100184b8  nop     dword ptr [eax+eax+00000000h]
0x100184c0  mov     ax, [ecx]
0x100184c3  add     ecx, 2
0x100184c6  test    ax, ax
0x100184c9  jnz     short loc_100184C0
0x100184cb  mov     edi, [ebp+arg_14]
0x100184ce  sub     ecx, esi
0x100184d0  mov     esi, [ebp+Destination]
0x100184d3  sar     ecx, 1
0x100184d5  shr     edi, 1
0x100184d7  lea     eax, [ecx+1]
0x100184da  cmp     eax, edi
0x100184dc  cmovbe  edi, eax
0x100184df  push    edi; Count
0x100184e0  push    edx; Source
0x100184e1  push    esi; Destination
0x100184e2  call    _wcsncpy
0x100184e7  mov     ecx, [ebp+arg_C]
0x100184ea  xor     eax, eax
0x100184ec  add     esp, 0Ch
0x100184ef  mov     [esi+edi*2-2], ax
0x100184f4  test    ecx, ecx
0x100184f6  jz      loc_10018968
0x100184fc  mov     eax, [ebx+410h]
0x10018502  mov     [ecx], eax
0x10018504  push    _critJet; lpCriticalSection
0x1001850a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018510  pop     edi
0x10018511  pop     ebx
0x10018512  xor     eax, eax
0x10018514  pop     esi
0x10018515  mov     esp, ebp
0x10018517  pop     ebp
0x10018518  retn    18h
0x1001851b  mov     ecx, [ebp+arg_4]; jumptable 10018363 case 2
0x1001851e  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10018523  mov     esi, eax
0x10018525  cmp     esi, 0FFFFFFFFh
0x10018528  jz      loc_100187B9
0x1001852e  push    ecx
0x1001852f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10018534  mov     ecx, [ebp+arg_C]
0x10018537  test    ecx, ecx
0x10018539  jz      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x1001853f  imul    eax, esi, 68h ; 'h'
0x10018542  mov     eax, dword_1016EAA8[eax]
0x10018548  mov     [ecx], eax
0x1001854a  push    _critJet; lpCriticalSection
0x10018550  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018556  pop     edi
0x10018557  pop     ebx
0x10018558  xor     eax, eax
0x1001855a  pop     esi
0x1001855b  mov     esp, ebp
0x1001855d  pop     ebp
0x1001855e  retn    18h
0x10018561  mov     ecx, [ebp+arg_4]; jumptable 10018363 case 32
0x10018564  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10018569  cmp     eax, 0FFFFFFFFh
0x1001856c  jz      loc_100187B9
0x10018572  imul    eax, 68h ; 'h'
0x10018575  mov     ecx, dword_1016EAEC[eax]
0x1001857b  mov     eax, [ebp+arg_C]
0x1001857e  mov     [eax], ecx
0x10018580  push    _critJet; lpCriticalSection
0x10018586  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001858c  pop     edi
0x1001858d  pop     ebx
0x1001858e  xor     eax, eax
0x10018590  pop     esi
0x10018591  mov     esp, ebp
0x10018593  pop     ebp
0x10018594  retn    18h
0x10018597  mov     ecx, [ebp+arg_4]; jumptable 10018363 case 4
0x1001859a  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1001859f  mov     esi, eax
0x100185a1  cmp     esi, 0FFFFFFFFh
0x100185a4  jz      loc_100187B9
0x100185aa  push    ecx
0x100185ab  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100185b0  mov     ecx, [ebp+arg_C]
0x100185b3  test    ecx, ecx
0x100185b5  jz      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x100185bb  imul    eax, esi, 68h ; 'h'
0x100185be  mov     eax, dword_1016EADC[eax]
0x100185c4  mov     [ecx], eax
0x100185c6  push    _critJet; lpCriticalSection
0x100185cc  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100185d2  pop     edi
0x100185d3  pop     ebx
0x100185d4  xor     eax, eax
0x100185d6  pop     esi
0x100185d7  mov     esp, ebp
0x100185d9  pop     ebp
0x100185da  retn    18h
0x100185dd  mov     ecx, [ebp+arg_4]; jumptable 10018363 case 39
0x100185e0  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100185e5  mov     esi, eax
0x100185e7  cmp     esi, 0FFFFFFFFh
0x100185ea  jz      loc_100187B9
0x100185f0  push    ecx
0x100185f1  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x100185f6  mov     ecx, [ebp+arg_C]
0x100185f9  test    ecx, ecx
0x100185fb  jz      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x10018601  imul    eax, esi, 68h ; 'h'
0x10018604  mov     eax, dword_1016EAE0[eax]
0x1001860a  mov     [ecx], eax
0x1001860c  push    _critJet; lpCriticalSection
0x10018612  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018618  pop     edi
0x10018619  pop     ebx
0x1001861a  xor     eax, eax
0x1001861c  pop     esi
0x1001861d  mov     esp, ebp
0x1001861f  pop     ebp
0x10018620  retn    18h
0x10018623  push    [ebp+arg_4]; jumptable 10018363 case 7
0x10018626  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001862b  mov     ecx, [ebp+arg_C]
0x1001862e  test    ecx, ecx
0x10018630  jz      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x10018636  mov     eax, _wQueryTimeout
0x1001863b  mov     [ecx], eax
0x1001863d  push    _critJet; lpCriticalSection
0x10018643  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10018649  pop     edi
0x1001864a  pop     ebx
0x1001864b  xor     eax, eax
0x1001864d  pop     esi
0x1001864e  mov     esp, ebp
0x10018650  pop     ebp
0x10018651  retn    18h
0x10018654  push    [ebp+arg_4]; jumptable 10018363 case 25
0x10018657  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001865c  mov     ecx, [ebp+arg_C]
0x1001865f  test    ecx, ecx
0x10018661  jz      def_10018363; jumptable 10018363 default case, cases 1,3,5,9-24,26-31,33-37,40-47,50,51,53,54,56,68,71
0x10018667  mov     eax, _wLoginTimeout
0x1001866c  mov     [ecx], eax
0x1001866e  push    _critJet; lpCriticalSection
0x10018674  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001867a  pop     edi
0x1001867b  pop     ebx
0x1001867c  xor     eax, eax
0x1001867e  pop     esi
0x1001867f  mov     esp, ebp
0x10018681  pop     ebp
0x10018682  retn    18h
0x10018685  mov     ecx, [ebp+arg_4]; jumptable 10018363 case 38
0x10018688  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x1001868d  mov     esi, eax
0x1001868f  cmp     esi, 0FFFFFFFFh
0x10018692  jz      loc_100187B9
0x10018698  push    ecx
0x10018699  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001869e  mov     ecx, [ebp+arg_C]
  ... truncated ...
```
