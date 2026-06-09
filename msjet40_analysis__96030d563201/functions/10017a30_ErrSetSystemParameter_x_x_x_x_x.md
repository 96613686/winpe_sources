# ErrSetSystemParameter(x,x,x,x,x)

- ea: `0x10017a30`
- end: `0x10018237`
- name: `_ErrSetSystemParameter@20`
- size: `2055`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10026c70`
- `0x101187f2`

## callees

- `0x10017a30`
- `0x1003e650`
- `0x1003e6a0`
- `0x1003e820`
- `0x10043440`
- `0x1004d91f`
- `0x10050000`
- `0x10121f97`
- `0x101229da`
- `0x101248d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthread` at `0x10018175`
- `api-ms-win-crt-private-l1-1-0!_o__beginthread` at `0x10018175`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x100180e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x100180e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100180fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10018114`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100180fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10018114`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1001818b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1001818b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018131`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018144`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018131`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10018144`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018154`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10018154`

## string_xrefs

- `0x100180e0`: `ole32.dll`

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
      dword_1016EAA8[26 * IsibOfSesid] = a4;
      return 0;
    case 4:
      v10 = UtilGetIsibOfSesid(a2);
      if ( v10 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EADC[26 * v10] = a4;
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
      dword_1016EAE4[26 * v24] = dword_1016EAE4[26 * v24] & 0xFFFFFFFE | (a4 != 0);
      return result;
    case 39:
      v11 = UtilGetIsibOfSesid(a2);
      if ( v11 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EAE0[26 * v11] = a4 != 0;
      return 0;
    case 48:
      v25 = UtilGetIsibOfSesid(a2);
      if ( v25 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      dword_1016EAFC[26 * v25] = a4;
      return 0;
    case 49:
      v26 = UtilGetIsibOfSesid(a2);
      if ( v26 == -1 )
        return -1104;
      ClearErrorInfo(a2);
      result = 0;
      dword_1016EAE4[26 * v26] = dword_1016EAE4[26 * v26] & 0xFFFFFFFD | (a4 != 0 ? 2 : 0);
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
        dword_10130454 = (int)ErrGenUniqueId;
        dword_10130458 = (int)NotifyUpdateUserFunctions;
        dword_1013045C = (int)JetStringCompare;
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
              if ( dword_101310C8 )
              {
                v20 = *v18;
                v45 = 0;
                v21 = *v20;
                v44 = v20;
                (*(void (__thiscall **)(_DWORD, int *, unsigned int, char *, int *))(v21 + 72))(
                  *(_DWORD *)(v21 + 72),
                  v20,
                  dword_101310C8,
                  v43,
                  &v45);
                if ( dword_101310BC )
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
                      dword_101310BC);
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
      dword_1016EB00[26 * v28] = a4;
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
      dword_1016EAE4[26 * v27] = dword_1016EAE4[26 * v27] & 0xFFFFFFFB | (a4 != 0 ? 4 : 0);
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
        dword_101310BC = a4;
        return 0;
      }
    case 74:
      if ( dword_101310D8 )
        return 0;
      Library = LoadLibraryExA("ole32.dll", 0, 8u);
      hLibModule = Library;
      if ( !Library )
        return -5001;
      CoUninitialize = (void (__stdcall *)())GetProcAddress(Library, "CoUninitialize");
      CoInitializeEx = (HRESULT (__stdcall *)(LPVOID, DWORD))GetProcAddress(hLibModule, "CoInitializeEx");
      dword_10130F48 = 1000;
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
0x10017a30  mov     edi, edi
0x10017a32  push    ebp
0x10017a33  mov     ebp, esp
0x10017a35  sub     esp, 10h
0x10017a38  push    ebx
0x10017a39  mov     ebx, [ebp+arg_0]
0x10017a3c  push    esi
0x10017a3d  mov     esi, edx
0x10017a3f  push    edi; unsigned int
0x10017a40  mov     edi, ecx
0x10017a42  cmp     ebx, 4Ah; switch 75 cases
0x10017a45  ja      def_10017A52; jumptable 10017A52 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017a4b  movzx   eax, ds:byte_1001829C[ebx]
0x10017a52  jmp     ds:jpt_10017A52[eax*4]; switch jump
0x10017a59  mov     eax, _rgtib; jumptable 10017A52 cases 6,8,57-63,65,66,70
0x10017a5e  imul    ecx, edi, 90Ch
0x10017a64  cmp     dword ptr [ecx+eax+41Ch], 0
0x10017a6c  jz      loc_10017FFD
0x10017a72  mov     ecx, esi
0x10017a74  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017a79  cmp     eax, 0FFFFFFFFh
0x10017a7c  jz      loc_10017F3B
0x10017a82  push    esi
0x10017a83  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017a88  push    ecx
0x10017a89  push    [ebp+arg_4]
0x10017a8c  mov     edx, ebx
0x10017a8e  mov     ecx, esi
0x10017a90  call    _ErrIsamSetSystemParameter@16; ErrIsamSetSystemParameter(x,x,x,x)
0x10017a95  pop     edi
0x10017a96  pop     esi
0x10017a97  pop     ebx
0x10017a98  mov     esp, ebp
0x10017a9a  pop     ebp
0x10017a9b  retn    0Ch
0x10017a9e  mov     ecx, esi; jumptable 10017A52 case 2
0x10017aa0  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017aa5  mov     edi, eax
0x10017aa7  cmp     edi, 0FFFFFFFFh
0x10017aaa  jz      loc_10017F3B
0x10017ab0  push    esi
0x10017ab1  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017ab6  mov     eax, [ebp+arg_4]
0x10017ab9  imul    ecx, edi, 68h ; 'h'
0x10017abc  mov     dword_1016EAA8[ecx], eax
0x10017ac2  xor     eax, eax
0x10017ac4  pop     edi
0x10017ac5  pop     esi
0x10017ac6  pop     ebx
0x10017ac7  mov     esp, ebp
0x10017ac9  pop     ebp
0x10017aca  retn    0Ch
0x10017acd  mov     ecx, esi; jumptable 10017A52 case 4
0x10017acf  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017ad4  mov     edi, eax
0x10017ad6  cmp     edi, 0FFFFFFFFh
0x10017ad9  jz      loc_10017F3B
0x10017adf  push    esi
0x10017ae0  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017ae5  mov     eax, [ebp+arg_4]
0x10017ae8  imul    ecx, edi, 68h ; 'h'
0x10017aeb  mov     dword_1016EADC[ecx], eax
0x10017af1  xor     eax, eax
0x10017af3  pop     edi
0x10017af4  pop     esi
0x10017af5  pop     ebx
0x10017af6  mov     esp, ebp
0x10017af8  pop     ebp
0x10017af9  retn    0Ch
0x10017afc  mov     ecx, esi; jumptable 10017A52 case 39
0x10017afe  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017b03  mov     edi, eax
0x10017b05  cmp     edi, 0FFFFFFFFh
0x10017b08  jz      loc_10017F3B
0x10017b0e  push    esi
0x10017b0f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017b14  xor     ecx, ecx
0x10017b16  cmp     [ebp+arg_4], ecx
0x10017b19  setnz   cl
0x10017b1c  imul    eax, edi, 68h ; 'h'
0x10017b1f  mov     dword_1016EAE0[eax], ecx
0x10017b25  xor     eax, eax
0x10017b27  pop     edi
0x10017b28  pop     esi
0x10017b29  pop     ebx
0x10017b2a  mov     esp, ebp
0x10017b2c  pop     ebp
0x10017b2d  retn    0Ch
0x10017b30  push    esi; jumptable 10017A52 case 7
0x10017b31  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017b36  mov     eax, [ebp+arg_4]
0x10017b39  mov     _wQueryTimeout, eax
0x10017b3e  xor     eax, eax
0x10017b40  pop     edi
0x10017b41  pop     esi
0x10017b42  pop     ebx
0x10017b43  mov     esp, ebp
0x10017b45  pop     ebp
0x10017b46  retn    0Ch
0x10017b49  push    esi; jumptable 10017A52 case 25
0x10017b4a  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017b4f  mov     eax, [ebp+arg_4]
0x10017b52  mov     _wLoginTimeout, eax
0x10017b57  xor     eax, eax
0x10017b59  pop     edi
0x10017b5a  pop     esi
0x10017b5b  pop     ebx
0x10017b5c  mov     esp, ebp
0x10017b5e  pop     ebp
0x10017b5f  retn    0Ch
0x10017b62  push    esi; jumptable 10017A52 case 29
0x10017b63  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017b68  mov     eax, [ebp+arg_4]
0x10017b6b  mov     _wSQLTrace, eax
0x10017b70  xor     eax, eax
0x10017b72  pop     edi
0x10017b73  pop     esi
0x10017b74  pop     ebx
0x10017b75  mov     esp, ebp
0x10017b77  pop     ebp
0x10017b78  retn    0Ch
0x10017b7b  mov     edx, [ebp+Source]; jumptable 10017A52 case 0
0x10017b7e  test    edx, edx
0x10017b80  jz      def_10017A52; jumptable 10017A52 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017b86  mov     ecx, edx
0x10017b88  lea     esi, [ecx+2]
0x10017b8b  nop     dword ptr [eax+eax+00h]
0x10017b90  mov     ax, [ecx]
0x10017b93  add     ecx, 2
0x10017b96  test    ax, ax
0x10017b99  jnz     short loc_10017B90
0x10017b9b  sub     ecx, esi
0x10017b9d  sar     ecx, 1
0x10017b9f  cmp     ecx, 104h
0x10017ba5  jnb     def_10017A52; jumptable 10017A52 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017bab  lea     eax, [ecx+1]
0x10017bae  push    eax; Count
0x10017baf  imul    eax, edi, 90Ch
0x10017bb5  push    edx; Source
0x10017bb6  add     eax, _rgtib
0x10017bbc  push    eax; Destination
0x10017bbd  call    _wcsncpy
0x10017bc2  add     esp, 0Ch
0x10017bc5  xor     eax, eax
0x10017bc7  pop     edi
0x10017bc8  pop     esi
0x10017bc9  pop     ebx
0x10017bca  mov     esp, ebp
0x10017bcc  pop     ebp
0x10017bcd  retn    0Ch
0x10017bd0  mov     ebx, [ebp+Source]; jumptable 10017A52 case 55
0x10017bd3  test    ebx, ebx
0x10017bd5  jz      def_10017A52; jumptable 10017A52 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017bdb  mov     edx, ebx
0x10017bdd  lea     ecx, [edx+2]
0x10017be0  mov     ax, [edx]
0x10017be3  add     edx, 2
0x10017be6  test    ax, ax
0x10017be9  jnz     short loc_10017BE0
0x10017beb  sub     edx, ecx
0x10017bed  sar     edx, 1
0x10017bef  cmp     edx, 104h
0x10017bf5  jnb     def_10017A52; jumptable 10017A52 default case, cases 1,3,5,9-24,27,30-37,40-47,50,53,54,56
0x10017bfb  imul    esi, edi, 90Ch
0x10017c01  lea     eax, [edx+1]
0x10017c04  push    eax; Count
0x10017c05  push    ebx; Source
0x10017c06  add     esi, _rgtib
0x10017c0c  lea     eax, [esi+208h]
0x10017c12  push    eax; Destination
0x10017c13  call    _wcsncpy
0x10017c18  mov     eax, [ebp+arg_4]
0x10017c1b  add     esp, 0Ch
0x10017c1e  mov     [esi+410h], eax
0x10017c24  xor     eax, eax
0x10017c26  pop     edi
0x10017c27  pop     esi
0x10017c28  pop     ebx
0x10017c29  mov     esp, ebp
0x10017c2b  pop     ebp
0x10017c2c  retn    0Ch
0x10017c2f  xor     ebx, ebx; jumptable 10017A52 case 68
0x10017c31  xor     eax, eax
0x10017c33  mov     edx, 80004005h
0x10017c38  cmp     edi, 40h ; '@'
0x10017c3b  jge     loc_10017DC9
0x10017c41  imul    ebx, edi, 90Ch
0x10017c47  add     ebx, _rgtib
0x10017c4d  jz      loc_10017DC9
0x10017c53  cmp     [ebx+8F8h], eax
0x10017c59  lea     edi, [ebx+8F8h]
0x10017c5f  jnz     loc_10017DC7
0x10017c65  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017c6b  mov     [ebp+var_4], eax
0x10017c6e  test    ecx, ecx
0x10017c70  jnz     loc_10017D12
0x10017c76  movups  xmm0, xmmword ptr _IID_IJetES.Data1
0x10017c7d  push    63h ; 'c'
0x10017c7f  push    offset ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017c84  push    1
0x10017c86  sub     esp, 10h
0x10017c89  mov     eax, esp
0x10017c8b  push    ecx
0x10017c8c  push    3
0x10017c8e  push    1
0x10017c90  push    ecx
0x10017c91  push    1
0x10017c93  sub     esp, 10h
0x10017c96  movups  xmmword ptr [eax], xmm0
0x10017c99  mov     eax, esp
0x10017c9b  movups  xmm0, xmmword ptr _CLSID_JETES.Data1
0x10017ca2  push    ecx
0x10017ca3  push    1
0x10017ca5  movups  xmmword ptr [eax], xmm0
0x10017ca8  call    ?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ; PostCOMCallThreadRequest(etCOMCall,...)
0x10017cad  add     esp, 48h
0x10017cb0  test    eax, eax
0x10017cb2  js      loc_10017DC2
0x10017cb8  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017cbe  mov     ?g_QJetCallbacks@@3UtagQJETEXPRSRVC_CALLBACK@@A, offset _VltFromHSelect@8; VltFromHSelect(x,x)
0x10017cc8  mov     dword_10130454, offset _ErrGenUniqueId@4; ErrGenUniqueId(x) ...
0x10017cd2  mov     dword_10130458, offset _NotifyUpdateUserFunctions@4; NotifyUpdateUserFunctions(x) ...
0x10017cdc  mov     dword_1013045C, offset _JetStringCompare@24; JetStringCompare(x,x,x,x,x,x) ...
0x10017ce6  mov     eax, [ecx]
0x10017ce8  push    10h
0x10017cea  push    offset ?g_QJetCallbacks@@3UtagQJETEXPRSRVC_CALLBACK@@A; unsigned int
0x10017cef  push    ecx; void *
0x10017cf0  mov     esi, [eax+1Ch]
0x10017cf3  mov     ecx, esi
0x10017cf5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017cfb  call    esi
0x10017cfd  test    eax, eax
0x10017cff  js      loc_10017DC2
0x10017d05  mov     ecx, ?g_pIJetES@@3PAUIJetES@@A; IJetES * g_pIJetES
0x10017d0b  mov     [ebp+var_4], 1
0x10017d12  mov     eax, [ecx]
0x10017d14  push    edi; unsigned int
0x10017d15  push    ecx; void *
0x10017d16  mov     esi, [eax+20h]
0x10017d19  mov     ecx, esi
0x10017d1b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017d21  call    esi
0x10017d23  test    eax, eax
0x10017d25  js      loc_10017DC2
0x10017d2b  cmp     [ebp+var_4], 0
0x10017d2f  jz      loc_10017DC2
0x10017d35  mov     eax, dword_101310C8
0x10017d3a  test    eax, eax
0x10017d3c  jz      loc_10017DC2
0x10017d42  mov     ecx, [edi]
0x10017d44  lea     edx, [ebp+var_8]
0x10017d47  push    edx
0x10017d48  lea     edx, [ebp+var_10]
0x10017d4b  mov     [ebp+var_8], 0
0x10017d52  push    edx
0x10017d53  mov     esi, [ecx]
0x10017d55  push    eax; unsigned int
0x10017d56  mov     [ebp+var_C], ecx
0x10017d59  push    ecx; void *
0x10017d5a  mov     esi, [esi+48h]
0x10017d5d  mov     ecx, esi
0x10017d5f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017d65  call    esi
0x10017d67  cmp     dword_101310BC, 0
0x10017d6e  jz      short loc_10017DC2
0x10017d70  mov     ecx, [ebp+var_C]
0x10017d73  mov     [ebp+var_4], 0
0x10017d7a  mov     eax, [ecx]
0x10017d7c  mov     esi, [eax]
0x10017d7e  lea     eax, [ebp+var_4]
0x10017d81  push    eax
0x10017d82  push    offset _IID_IJetESInstance2; unsigned int
0x10017d87  push    ecx; void *
0x10017d88  mov     ecx, esi
0x10017d8a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017d90  call    esi
0x10017d92  test    eax, eax
0x10017d94  js      short loc_10017DC2
0x10017d96  mov     eax, [ebp+var_4]
0x10017d99  push    dword_101310BC; unsigned int
0x10017d9f  push    eax; void *
0x10017da0  mov     ecx, [eax]
0x10017da2  mov     esi, [ecx+50h]
0x10017da5  mov     ecx, esi
0x10017da7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017dad  call    esi
0x10017daf  mov     eax, [ebp+var_4]
0x10017db2  push    eax; void *
0x10017db3  mov     ecx, [eax]
0x10017db5  mov     esi, [ecx+8]
0x10017db8  mov     ecx, esi
0x10017dba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10017dc0  call    esi
0x10017dc2  mov     edx, 80004005h
0x10017dc7  mov     eax, [edi]
0x10017dc9  xor     ecx, ecx
0x10017dcb  test    ebx, ebx
0x10017dcd  cmovnz  ecx, eax
0x10017dd0  test    ecx, ecx
0x10017dd2  jz      short loc_10017DE9
  ... truncated ...
```
