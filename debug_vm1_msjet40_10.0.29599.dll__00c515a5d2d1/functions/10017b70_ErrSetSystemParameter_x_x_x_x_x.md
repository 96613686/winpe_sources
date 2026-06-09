# ErrSetSystemParameter(x,x,x,x,x)

- ea: `0x10017b70`
- end: `0x10018377`
- name: `_ErrSetSystemParameter@20`
- size: `2055`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10026dd0`
- `0x101189a2`

## callees

- `0x10017b70`
- `0x1003e7e0`
- `0x1003e830`
- `0x1003e9b0`
- `0x100435d0`
- `0x1004daaf`
- `0x10050190`
- `0x10122147`
- `0x10122b8a`
- `0x10124a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthread` at `0x100182b5`
- `api-ms-win-crt-private-l1-1-0!_o__beginthread` at `0x100182b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10018225`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10018225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1001823e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10018254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1001823e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10018254`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100182cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100182cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018271`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018284`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018271`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018284`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018294`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018294`

## string_xrefs

- `0x10018220`: `ole32.dll`

## pseudocode

```c
unsigned int __fastcall ErrSetSystemParameter(int a1, int a2, int a3, unsigned int a4, wchar_t *Source)
{
  int v7; // ecx
  unsigned int result; // eax
  int IsibOfSesid; // edi
  int v10; // edi
  int v11; // edi
  unsigned int v12; // ecx
  unsigned int v13; // edx
  wchar_t *v14; // esi
  char *v15; // ebx
  int *v16; // eax
  int v17; // edx
  int **v18; // edi
  void *v19; // ecx
  int *v20; // ecx
  int v21; // esi
  int *v22; // ecx
  signed int v23; // edx
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // ebx
  int inited; // eax
  int v30; // ecx
  char *v31; // ecx
  char *v32; // ecx
  char *v33; // eax
  void *v34; // ecx
  char *v35; // ebx
  _DWORD **v36; // esi
  _DWORD *v37; // edi
  _DWORD **v38; // edx
  HMODULE Library; // eax
  int v40; // eax
  _DWORD *v41; // edi
  int v42; // ebx
  char v43[4]; // [esp+Ch] [ebp-10h] BYREF
  void *v44; // [esp+10h] [ebp-Ch]
  int v45; // [esp+14h] [ebp-8h] BYREF
  void *v46; // [esp+18h] [ebp-4h] BYREF

  switch ( a3 )
  {
    case 0:
      if ( !Source )
        return -1003;
      v12 = wcslen(Source);
      if ( v12 >= 0x104 )
        return -1003;
      wcsncpy((wchar_t *)rgtib + 1158 * a1, Source, v12 + 1);
      return 0;
    case 2:
      IsibOfSesid = UtilGetIsibOfSesid(a2);
      if ( IsibOfSesid == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EB48[26 * IsibOfSesid] = a4;
      return 0;
    case 4:
      v10 = UtilGetIsibOfSesid(a2);
      if ( v10 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EB7C[26 * v10] = a4;
      return 0;
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
      if ( !*((_DWORD *)rgtib + 579 * a1 + 263) )
        return -1029;
      if ( UtilGetIsibOfSesid(a2) == -1 )
        return -1104;
      ClearErrorInfo(a2);
      return ErrIsamSetSystemParameter(a4, v7);
    case 7:
      ClearErrorInfo(a2);
      *(_DWORD *)&wQueryTimeout = a4;
      return 0;
    case 25:
      ClearErrorInfo(a2);
      *(_DWORD *)&wLoginTimeout = a4;
      return 0;
    case 26:
      return 0;
    case 28:
      *((_DWORD *)rgtib + 579 * a1 + 565) = a4;
      return 0;
    case 29:
      ClearErrorInfo(a2);
      wSQLTrace = a4;
      return 0;
    case 38:
      v24 = UtilGetIsibOfSesid(a2);
      if ( v24 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      result = 0;
      dword_1016EB84[26 * v24] = dword_1016EB84[26 * v24] & 0xFFFFFFFE | (a4 != 0);
      return result;
    case 39:
      v11 = UtilGetIsibOfSesid(a2);
      if ( v11 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EB80[26 * v11] = a4 != 0;
      return 0;
    case 48:
      v25 = UtilGetIsibOfSesid(a2);
      if ( v25 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EB9C[26 * v25] = a4;
      return 0;
    case 49:
      v26 = UtilGetIsibOfSesid(a2);
      if ( v26 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      result = 0;
      dword_1016EB84[26 * v26] = dword_1016EB84[26 * v26] & 0xFFFFFFFD | (a4 != 0 ? 2 : 0);
      return result;
    case 51:
      inited = ErrExprServInitTypelib(a4, Source);
      v30 = 0;
      if ( inited < 0 )
        return inited;
      return v30;
    case 52:
      v41 = (char *)rgtib + 2316 * a1;
      if ( !FValidSesid(*(_DWORD *)Source) && *(_DWORD *)Source != -1 )
        return -1003;
      v42 = *((_DWORD *)Source + 1);
      if ( !FValidDbid(*(_DWORD *)Source, v42) && v42 != -1 )
        return -1003;
      if ( *((_DWORD *)Source + 2) > 2u )
        return -1003;
      v41[566] = *(_DWORD *)Source;
      v41[567] = *((_DWORD *)Source + 1);
      v41[568] = *((_DWORD *)Source + 2);
      return 0;
    case 55:
      if ( !Source )
        return -1003;
      v13 = wcslen(Source);
      if ( v13 >= 0x104 )
        return -1003;
      v14 = (wchar_t *)((char *)rgtib + 2316 * a1);
      wcsncpy(v14 + 260, Source, v13 + 1);
      *((_DWORD *)v14 + 260) = a4;
      return 0;
    case 64:
      v31 = (char *)rgtib + 2316 * a1;
      if ( !*((_DWORD *)v31 + 263) )
        return -1029;
      *((_DWORD *)v31 + 572) = a4;
      return 0;
    case 67:
      v32 = (char *)rgtib + 2316 * a1;
      if ( !*((_DWORD *)v32 + 263) )
        return -1029;
      *((_DWORD *)v32 + 573) = a4;
      return 0;
    case 68:
      v15 = 0;
      v16 = 0;
      v17 = -2147467259;
      if ( a1 >= 64 )
        goto LABEL_35;
      v15 = (char *)rgtib + 2316 * a1;
      if ( !v15 )
        goto LABEL_35;
      v18 = (int **)(v15 + 2296);
      if ( *((_DWORD *)v15 + 574) )
        goto LABEL_34;
      v19 = g_pIJetES;
      v46 = 0;
      if ( g_pIJetES )
        goto LABEL_27;
      if ( PostCOMCallThreadRequest(
             1,
             0,
             CLSID_JETES.Data1,
             *(_DWORD *)&CLSID_JETES.Data2,
             *(_DWORD *)CLSID_JETES.Data4,
             *(_DWORD *)&CLSID_JETES.Data4[4],
             1,
             0,
             1,
             3,
             0,
             IID_IJetES.Data1,
             *(_DWORD *)&IID_IJetES.Data2,
             *(_DWORD *)IID_IJetES.Data4,
             *(_DWORD *)&IID_IJetES.Data4[4],
             1,
             &g_pIJetES,
             99) >= 0 )
      {
        g_QJetCallbacks = VltFromHSelect;
        dword_101304E4 = (int)ErrGenUniqueId;
        dword_101304E8 = (int)NotifyUpdateUserFunctions;
        dword_101304EC = (int)JetStringCompare;
        if ( (*(int (__thiscall **)(_DWORD, void *, void *, int))(*(_DWORD *)g_pIJetES + 28))(
               *(_DWORD *)(*(_DWORD *)g_pIJetES + 28),
               g_pIJetES,
               &g_QJetCallbacks,
               16) >= 0 )
        {
          v19 = g_pIJetES;
          v46 = (void *)1;
LABEL_27:
          if ( (*(int (__thiscall **)(_DWORD, void *, char *))(*(_DWORD *)v19 + 32))(
                 *(_DWORD *)(*(_DWORD *)v19 + 32),
                 v19,
                 v15 + 2296) >= 0 )
          {
            if ( v46 )
            {
              if ( dword_10131178 )
              {
                v20 = *v18;
                v45 = 0;
                v21 = *v20;
                v44 = v20;
                (*(void (__thiscall **)(_DWORD, int *, unsigned int, char *, int *))(v21 + 72))(
                  *(_DWORD *)(v21 + 72),
                  v20,
                  dword_10131178,
                  v43,
                  &v45);
                if ( dword_1013116C )
                {
                  v46 = 0;
                  if ( (**(int (__thiscall ***)(_DWORD, void *, GUID *, void **))v44)(
                         **(_DWORD **)v44,
                         v44,
                         &IID_IJetESInstance2,
                         &v46) >= 0 )
                  {
                    (*(void (__thiscall **)(_DWORD, void *, unsigned int))(*(_DWORD *)v46 + 80))(
                      *(_DWORD *)(*(_DWORD *)v46 + 80),
                      v46,
                      dword_1013116C);
                    (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v46 + 8))(*(_DWORD *)(*(_DWORD *)v46 + 8), v46);
                  }
                }
              }
            }
          }
        }
      }
      v17 = -2147467259;
LABEL_34:
      v16 = *v18;
LABEL_35:
      v22 = 0;
      if ( v15 )
        v22 = v16;
      if ( v22 )
        v17 = (*(int (__thiscall **)(_DWORD, int *, unsigned int))(*v22 + 76))(*(_DWORD *)(*v22 + 76), v22, a4);
      v23 = v17 & 0x8000FFFF;
      result = 0;
      if ( v23 < 0 )
        return v23;
      return result;
    case 69:
      v28 = UtilGetIsibOfSesid(a2);
      if ( v28 == -1 )
        return -1104;
      if ( a4 >= 2 && a4 != 92 )
        return -1003;
      ClearErrorInfo(a2);
      dword_1016EBA0[26 * v28] = a4;
      return 0;
    case 71:
      *((_DWORD *)rgtib + 579 * a1 + 576) = a4 != 0;
      return 0;
    case 72:
      v27 = UtilGetIsibOfSesid(a2);
      if ( v27 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      result = 0;
      dword_1016EB84[26 * v27] = dword_1016EB84[26 * v27] & 0xFFFFFFFB | (a4 != 0 ? 4 : 0);
      return result;
    case 73:
      v33 = (char *)rgtib + 2316 * a1;
      if ( !*((_DWORD *)v33 + 263) )
        return -1029;
      v34 = 0;
      v46 = 0;
      if ( g_pIJetES )
      {
        v35 = 0;
        v36 = 0;
        if ( a1 < 64 )
        {
          v35 = (char *)rgtib + 2316 * a1;
          if ( v33 )
          {
            v37 = v33 + 2296;
            if ( !*((_DWORD *)v33 + 574) )
            {
              (*(void (__thiscall **)(_DWORD, void *, char *))(*(_DWORD *)g_pIJetES + 32))(
                *(_DWORD *)(*(_DWORD *)g_pIJetES + 32),
                g_pIJetES,
                v35 + 2296);
              v34 = v46;
            }
            v36 = (_DWORD **)*v37;
          }
        }
        v38 = 0;
        if ( v35 )
          v38 = v36;
        if ( v38 )
        {
          if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, void **))**v38)(**v38, v38, &IID_IJetESInstance2, &v46) >= 0 )
            (*(void (__thiscall **)(_DWORD, void *, unsigned int))(*(_DWORD *)v46 + 80))(
              *(_DWORD *)(*(_DWORD *)v46 + 80),
              v46,
              a4);
          v34 = v46;
        }
        if ( v34 )
          (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v34 + 8))(*(_DWORD *)(*(_DWORD *)v34 + 8), v34);
        return 0;
      }
      else
      {
        dword_1013116C = a4;
        return 0;
      }
    case 74:
      if ( dword_10131188 )
        return 0;
      Library = LoadLibraryExA("ole32.dll", 0, 8u);
      hLibModule = Library;
      if ( !Library )
        return -5001;
      CoUninitialize = (void (__stdcall *)())GetProcAddress(Library, "CoUninitialize");
      CoInitializeEx = (HRESULT (__stdcall *)(LPVOID, DWORD))GetProcAddress(hLibModule, "CoInitializeEx");
      dword_10130FF4 = 1000;
      hHandle = CreateEventA(0, 0, 0, 0);
      pHandles = CreateEventA(0, 0, 0, 0);
      InitializeCriticalSection(&CriticalSection);
      if ( !hHandle || !pHandles )
        return -5001;
      hObject = (HANDLE)__beginthread(COMCallThreadProc, 0, 0);
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      v40 = -2147467259;
      if ( hObject )
        v40 = 0;
      return v40 != 0 ? 0xFFFFEC77 : 0;
    default:
      return -1003;
  }
}

```

## disassembly

```asm
0x10017b70  mov     edi, edi
0x10017b72  push    ebp
0x10017b73  mov     ebp, esp
0x10017b75  sub     esp, 10h
0x10017b78  push    ebx
0x10017b79  mov     ebx, [ebp+arg_0]
0x10017b7c  push    esi
0x10017b7d  mov     esi, edx
0x10017b7f  push    edi; unsigned int
0x10017b80  mov     edi, ecx
0x10017b82  cmp     ebx, 4Ah; switch 75 cases
0x10017b85  ja      def_10017B92; jumptable 10017B92 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017b8b  movzx   eax, ds:byte_100183DC[ebx]
0x10017b92  jmp     ds:jpt_10017B92[eax*4]; switch jump
0x10017b99  mov     eax, _rgtib; jumptable 10017B92 cases 6,8,57-63,65,66,70
0x10017b9e  imul    ecx, edi, 90Ch
0x10017ba4  cmp     dword ptr [ecx+eax+41Ch], 0
0x10017bac  jz      loc_1001813D
0x10017bb2  mov     ecx, esi
0x10017bb4  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017bb9  cmp     eax, 0FFFFFFFFh
0x10017bbc  jz      loc_1001807B
0x10017bc2  push    esi
0x10017bc3  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017bc8  push    ecx
0x10017bc9  push    [ebp+arg_4]
0x10017bcc  mov     edx, ebx
0x10017bce  mov     ecx, esi
0x10017bd0  call    _ErrIsamSetSystemParameter@16; ErrIsamSetSystemParameter(x,x,x,x)
0x10017bd5  pop     edi
0x10017bd6  pop     esi
0x10017bd7  pop     ebx
0x10017bd8  mov     esp, ebp
0x10017bda  pop     ebp
0x10017bdb  retn    0Ch
0x10017bde  mov     ecx, esi; jumptable 10017B92 case 2
0x10017be0  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017be5  mov     edi, eax
0x10017be7  cmp     edi, 0FFFFFFFFh
0x10017bea  jz      loc_1001807B
0x10017bf0  push    esi
0x10017bf1  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017bf6  mov     eax, [ebp+arg_4]
0x10017bf9  imul    ecx, edi, 68h ; 'h'
0x10017bfc  mov     dword_1016EB48[ecx], eax
0x10017c02  xor     eax, eax
0x10017c04  pop     edi
0x10017c05  pop     esi
0x10017c06  pop     ebx
0x10017c07  mov     esp, ebp
0x10017c09  pop     ebp
0x10017c0a  retn    0Ch
0x10017c0d  mov     ecx, esi; jumptable 10017B92 case 4
0x10017c0f  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017c14  mov     edi, eax
0x10017c16  cmp     edi, 0FFFFFFFFh
0x10017c19  jz      loc_1001807B
0x10017c1f  push    esi
0x10017c20  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017c25  mov     eax, [ebp+arg_4]
0x10017c28  imul    ecx, edi, 68h ; 'h'
0x10017c2b  mov     dword_1016EB7C[ecx], eax
0x10017c31  xor     eax, eax
0x10017c33  pop     edi
0x10017c34  pop     esi
0x10017c35  pop     ebx
0x10017c36  mov     esp, ebp
0x10017c38  pop     ebp
0x10017c39  retn    0Ch
0x10017c3c  mov     ecx, esi; jumptable 10017B92 case 39
0x10017c3e  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017c43  mov     edi, eax
0x10017c45  cmp     edi, 0FFFFFFFFh
0x10017c48  jz      loc_1001807B
0x10017c4e  push    esi
0x10017c4f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017c54  xor     ecx, ecx
0x10017c56  cmp     [ebp+arg_4], ecx
0x10017c59  setnz   cl
0x10017c5c  imul    eax, edi, 68h ; 'h'
0x10017c5f  mov     dword_1016EB80[eax], ecx
0x10017c65  xor     eax, eax
0x10017c67  pop     edi
0x10017c68  pop     esi
0x10017c69  pop     ebx
0x10017c6a  mov     esp, ebp
0x10017c6c  pop     ebp
0x10017c6d  retn    0Ch
0x10017c70  push    esi; jumptable 10017B92 case 7
0x10017c71  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017c76  mov     eax, [ebp+arg_4]
0x10017c79  mov     _wQueryTimeout, eax
0x10017c7e  xor     eax, eax
0x10017c80  pop     edi
0x10017c81  pop     esi
0x10017c82  pop     ebx
0x10017c83  mov     esp, ebp
0x10017c85  pop     ebp
0x10017c86  retn    0Ch
0x10017c89  push    esi; jumptable 10017B92 case 25
0x10017c8a  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017c8f  mov     eax, [ebp+arg_4]
0x10017c92  mov     _wLoginTimeout, eax
0x10017c97  xor     eax, eax
0x10017c99  pop     edi
0x10017c9a  pop     esi
0x10017c9b  pop     ebx
0x10017c9c  mov     esp, ebp
0x10017c9e  pop     ebp
0x10017c9f  retn    0Ch
0x10017ca2  push    esi; jumptable 10017B92 case 29
0x10017ca3  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017ca8  mov     eax, [ebp+arg_4]
0x10017cab  mov     _wSQLTrace, eax
0x10017cb0  xor     eax, eax
0x10017cb2  pop     edi
0x10017cb3  pop     esi
0x10017cb4  pop     ebx
0x10017cb5  mov     esp, ebp
0x10017cb7  pop     ebp
0x10017cb8  retn    0Ch
0x10017cbb  mov     edx, [ebp+Source]; jumptable 10017B92 case 0
0x10017cbe  test    edx, edx
0x10017cc0  jz      def_10017B92; jumptable 10017B92 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017cc6  mov     ecx, edx
0x10017cc8  lea     esi, [ecx+2]
0x10017ccb  nop     dword ptr [eax+eax+00h]
0x10017cd0  mov     ax, [ecx]
0x10017cd3  add     ecx, 2
0x10017cd6  test    ax, ax
0x10017cd9  jnz     short loc_10017CD0
0x10017cdb  sub     ecx, esi
0x10017cdd  sar     ecx, 1
0x10017cdf  cmp     ecx, 104h
0x10017ce5  jnb     def_10017B92; jumptable 10017B92 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017ceb  lea     eax, [ecx+1]
0x10017cee  push    eax; Count
0x10017cef  imul    eax, edi, 90Ch
0x10017cf5  push    edx; Source
0x10017cf6  add     eax, _rgtib
0x10017cfc  push    eax; Destination
0x10017cfd  call    _wcsncpy
0x10017d02  add     esp, 0Ch
0x10017d05  xor     eax, eax
0x10017d07  pop     edi
0x10017d08  pop     esi
0x10017d09  pop     ebx
0x10017d0a  mov     esp, ebp
0x10017d0c  pop     ebp
0x10017d0d  retn    0Ch
0x10017d10  mov     ebx, [ebp+Source]; jumptable 10017B92 case 55
0x10017d13  test    ebx, ebx
0x10017d15  jz      def_10017B92; jumptable 10017B92 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017d1b  mov     edx, ebx
0x10017d1d  lea     ecx, [edx+2]
0x10017d20  mov     ax, [edx]
0x10017d23  add     edx, 2
0x10017d26  test    ax, ax
0x10017d29  jnz     short loc_10017D20
0x10017d2b  sub     edx, ecx
0x10017d2d  sar     edx, 1
0x10017d2f  cmp     edx, 104h
0x10017d35  jnb     def_10017B92; jumptable 10017B92 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017d3b  imul    esi, edi, 90Ch
0x10017d41  lea     eax, [edx+1]
0x10017d44  push    eax; Count
0x10017d45  push    ebx; Source
0x10017d46  add     esi, _rgtib
0x10017d4c  lea     eax, [esi+208h]
0x10017d52  push    eax; Destination
0x10017d53  call    _wcsncpy
0x10017d58  mov     eax, [ebp+arg_4]
0x10017d5b  add     esp, 0Ch
0x10017d5e  mov     [esi+410h], eax
0x10017d64  xor     eax, eax
0x10017d66  pop     edi
0x10017d67  pop     esi
0x10017d68  pop     ebx
0x10017d69  mov     esp, ebp
0x10017d6b  pop     ebp
0x10017d6c  retn    0Ch
0x10017d6f  xor     ebx, ebx; jumptable 10017B92 case 68
0x10017d71  xor     eax, eax
0x10017d73  mov     edx, 80004005h
0x10017d78  cmp     edi, 40h ; '@'
0x10017d7b  jge     loc_10017F09
0x10017d81  imul    ebx, edi, 90Ch
0x10017d87  add     ebx, _rgtib
0x10017d8d  jz      loc_10017F09
0x10017d93  cmp     [ebx+8F8h], eax
0x10017d99  lea     edi, [ebx+8F8h]
0x10017d9f  jnz     loc_10017F07
0x10017da5  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017dab  mov     [ebp+var_4], eax
0x10017dae  test    ecx, ecx
0x10017db0  jnz     loc_10017E52
0x10017db6  movups  xmm0, xmmword ptr _IID_IJetES.Data1
0x10017dbd  push    63h ; 'c'
0x10017dbf  push    offset ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017dc4  push    1
0x10017dc6  sub     esp, 10h
0x10017dc9  mov     eax, esp
0x10017dcb  push    ecx
0x10017dcc  push    3
0x10017dce  push    1
0x10017dd0  push    ecx
0x10017dd1  push    1
0x10017dd3  sub     esp, 10h
0x10017dd6  movups  xmmword ptr [eax], xmm0
0x10017dd9  mov     eax, esp
0x10017ddb  movups  xmm0, xmmword ptr _CLSID_JETES.Data1
0x10017de2  push    ecx
0x10017de3  push    1
0x10017de5  movups  xmmword ptr [eax], xmm0
0x10017de8  call    ?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ; PostCOMCallThreadRequest(etCOMCall,...)
0x10017ded  add     esp, 48h
0x10017df0  test    eax, eax
0x10017df2  js      loc_10017F02
0x10017df8  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017dfe  mov     ?g_QJetCallbacks@@3UtagQJETEXPRSRVC_CALLBACK@@A, offset _VltFromHSelect@8; VltFromHSelect(x,x)
0x10017e08  mov     dword_101304E4, offset _ErrGenUniqueId@4; ErrGenUniqueId(x) ...
0x10017e12  mov     dword_101304E8, offset _NotifyUpdateUserFunctions@4; NotifyUpdateUserFunctions(x) ...
0x10017e1c  mov     dword_101304EC, offset _JetStringCompare@24; JetStringCompare(x,x,x,x,x,x) ...
0x10017e26  mov     eax, [ecx]
0x10017e28  push    10h
0x10017e2a  push    offset ?g_QJetCallbacks@@3UtagQJETEXPRSRVC_CALLBACK@@A; unsigned int
0x10017e2f  push    ecx; void *
0x10017e30  mov     esi, [eax+1Ch]
0x10017e33  mov     ecx, esi
0x10017e35  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017e3b  call    esi
0x10017e3d  test    eax, eax
0x10017e3f  js      loc_10017F02
0x10017e45  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017e4b  mov     [ebp+var_4], 1
0x10017e52  mov     eax, [ecx]
0x10017e54  push    edi; unsigned int
0x10017e55  push    ecx; void *
0x10017e56  mov     esi, [eax+20h]
0x10017e59  mov     ecx, esi
0x10017e5b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017e61  call    esi
0x10017e63  test    eax, eax
0x10017e65  js      loc_10017F02
0x10017e6b  cmp     [ebp+var_4], 0
0x10017e6f  jz      loc_10017F02
0x10017e75  mov     eax, dword_10131178
0x10017e7a  test    eax, eax
0x10017e7c  jz      loc_10017F02
0x10017e82  mov     ecx, [edi]
0x10017e84  lea     edx, [ebp+var_8]
0x10017e87  push    edx
0x10017e88  lea     edx, [ebp+var_10]
0x10017e8b  mov     [ebp+var_8], 0
0x10017e92  push    edx
0x10017e93  mov     esi, [ecx]
0x10017e95  push    eax; unsigned int
0x10017e96  mov     [ebp+var_C], ecx
0x10017e99  push    ecx; void *
0x10017e9a  mov     esi, [esi+48h]
0x10017e9d  mov     ecx, esi
0x10017e9f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017ea5  call    esi
0x10017ea7  cmp     dword_1013116C, 0
0x10017eae  jz      short loc_10017F02
0x10017eb0  mov     ecx, [ebp+var_C]
0x10017eb3  mov     [ebp+var_4], 0
0x10017eba  mov     eax, [ecx]
0x10017ebc  mov     esi, [eax]
0x10017ebe  lea     eax, [ebp+var_4]
0x10017ec1  push    eax
0x10017ec2  push    offset _IID_IJetESInstance2; unsigned int
0x10017ec7  push    ecx; void *
0x10017ec8  mov     ecx, esi
0x10017eca  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017ed0  call    esi
0x10017ed2  test    eax, eax
0x10017ed4  js      short loc_10017F02
0x10017ed6  mov     eax, [ebp+var_4]
0x10017ed9  push    dword_1013116C; unsigned int
0x10017edf  push    eax; void *
0x10017ee0  mov     ecx, [eax]
0x10017ee2  mov     esi, [ecx+50h]
0x10017ee5  mov     ecx, esi
0x10017ee7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017eed  call    esi
0x10017eef  mov     eax, [ebp+var_4]
0x10017ef2  push    eax; void *
0x10017ef3  mov     ecx, [eax]
0x10017ef5  mov     esi, [ecx+8]
0x10017ef8  mov     ecx, esi
0x10017efa  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017f00  call    esi
0x10017f02  mov     edx, 80004005h
0x10017f07  mov     eax, [edi]
0x10017f09  xor     ecx, ecx
0x10017f0b  test    ebx, ebx
0x10017f0d  cmovnz  ecx, eax
0x10017f10  test    ecx, ecx
0x10017f12  jz      short loc_10017F29
  ... truncated ...
```
