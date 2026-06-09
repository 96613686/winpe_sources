# WBISAMInit(x)

- ea: `0x10006bd0`
- end: `0x10007075`
- name: `_WBISAMInit@4`
- size: `1189`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10006400`
- `0x100066d0`
- `0x10006bd0`
- `0x10019d40`
- `0x1001a480`
- `0x1001c2b0`
- `0x1001e690`
- `0x100249dd`
- `0x1002580a`
- `0x10025ab7`
- `0x1002efd4`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x10006dcf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x10006e9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x10006dcf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x10006e9d`
- `ole32!OleUninitialize` at `0x10006f6a`
- `ole32!OleUninitialize` at `0x10006f6a`
- `ole32!OleInitialize` at `0x10006f3c`
- `ole32!OleInitialize` at `0x10006f3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006fc1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10006ee1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10006ee1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10006eee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10006eee`

## pseudocode

```c
int __stdcall WBISAMInit(int a1)
{
  int v1; // eax
  const wchar_t *v2; // esi
  int v3; // edx
  wchar_t *v4; // ecx
  wchar_t *v5; // eax
  _DWORD *v6; // eax
  _DWORD *v7; // edi
  int *v8; // esi
  _WORD *v9; // edx
  int RegSpec; // ebx
  _DWORD *v11; // ecx
  _DWORD *v12; // esi
  int v13; // eax
  int v14; // ebx
  wchar_t *v15; // eax
  wchar_t *v16; // edx
  const wchar_t *v17; // eax
  wchar_t v18; // dx
  unsigned __int16 v19; // di
  __int16 v20; // dx
  int v21; // ebx
  unsigned __int16 v22; // di
  int v23; // edx
  int v24; // ebx
  int v25; // eax
  HGLOBAL v26; // eax
  HGLOBAL v27; // esi
  _DWORD *v28; // eax
  _DWORD *v29; // edi
  HRESULT v30; // eax
  int Settings; // eax
  int result; // eax
  DWORD CurrentProcessId; // eax
  _DWORD *v34; // ecx
  DWORD v35; // esi
  _DWORD *v36; // eax
  int v37; // eax
  wchar_t *v38; // [esp+10h] [ebp-220h]
  wchar_t *v39; // [esp+14h] [ebp-21Ch] BYREF
  int v40; // [esp+18h] [ebp-218h]
  wchar_t *i; // [esp+1Ch] [ebp-214h]
  _WORD v42[262]; // [esp+20h] [ebp-210h] BYREF

  v39 = 0;
  if ( !dword_1003A74C )
  {
    if ( (*(int (__thiscall **)(_DWORD, int, _DWORD, int, wchar_t **, _WORD *, int))(dword_1003A750 + 128))(
           *(_DWORD *)(dword_1003A750 + 128),
           a1,
           0,
           55,
           &v39,
           v42,
           522) )
    {
      v42[0] = 0;
    }
    ISAMDefaults = 8;
    v1 = 2147483646;
    dword_1003C2D8 = 1;
    v2 = L"!xls";
    dword_1003C2D4 = 1;
    v3 = 1026;
    dword_1003C2DC = 1;
    v4 = &DefaultSecureExtensions;
    do
    {
      if ( !v1 )
        break;
      if ( !*v2 )
        break;
      *v4++ = *v2++;
      --v1;
      --v3;
    }
    while ( v3 );
    v5 = v4 - 1;
    if ( v3 )
      v5 = v4;
    *v5 = 0;
    v6 = (_DWORD *)SetupConfigurationSpec();
    v7 = v6;
    if ( v6 )
    {
      v8 = (int *)*v6;
      for ( i = v39; v8; v8 = (int *)*v8 )
      {
        switch ( *((_BYTE *)v8 + 4) )
        {
          case 0:
            v9 = (_WORD *)v8[5];
            if ( v9 )
              WCSCPY2((_WORD *)v8[3], v9, v8[4]);
            else
              *(_WORD *)v8[3] = 0;
            break;
          case 1:
          case 2:
          case 3:
            *(_DWORD *)v8[3] = v8[4];
            break;
          default:
            continue;
        }
      }
      RegSpec = ReadRegSpec(L"Software\\Microsoft\\Jet\\4.0", v7);
      if ( !RegSpec )
        RegSpec = ReadRegSpec(v42, v7);
      v11 = (_DWORD *)*v7;
      if ( *v7 )
      {
        do
        {
          v12 = (_DWORD *)*v11;
          MemFree(v11);
          v11 = v12;
        }
        while ( v12 );
      }
      MemFree(v7);
      if ( RegSpec )
        return -5033;
    }
    if ( ISAMDefaults < 0 || (unsigned int)dword_1003C2D8 > 0x10 )
      return -5033;
    if ( !ISAMDefaults )
      ISAMDefaults = 0x4000;
    v13 = 0;
    dword_1003B29C = 0;
    dword_1003B2A0 = 0;
    if ( DefaultSecureExtensions == 33 )
    {
      dword_1003B2A0 = 1;
      v13 = 1;
    }
    v14 = 0;
    v40 = 0;
    memset32(SecureExtensions, v13, 0xFFu);
    v15 = _wcstok(&DefaultSecureExtensions + v13, L",", 0);
    i = v15;
    if ( v15 )
    {
      while ( 1 )
      {
        v16 = v15;
        v17 = L"None";
        v38 = v16;
        do
        {
          ++v17;
          v18 = *v16;
          v19 = v18 + 32;
          if ( (unsigned __int16)(v18 - 65) > 0x19u )
            v19 = v18;
          v20 = *(v17 - 1);
          v21 = v19;
          v22 = v20 + 32;
          if ( (unsigned __int16)(v20 - 65) > 0x19u )
            v22 = *(v17 - 1);
          v16 = ++v38;
        }
        while ( (_WORD)v21 && (_WORD)v21 == v22 );
        v23 = v21;
        v24 = v40;
        if ( v23 == v22 )
          break;
        if ( v40 < 255 )
        {
          v25 = i - &DefaultSecureExtensions;
          goto LABEL_41;
        }
LABEL_42:
        v14 = v24 + 1;
        v40 = v14;
        v15 = _wcstok(0, L",", 0);
        i = v15;
        if ( !v15 )
          goto LABEL_43;
      }
      v25 = i - &DefaultSecureExtensions + 4;
LABEL_41:
      SecureExtensions[v40] = v25;
      goto LABEL_42;
    }
LABEL_43:
    dword_1003B29C = v14;
    dword_1003AE68 = 0;
    dword_1003A660 = 1;
    if ( pExcelRecordBuffer )
      goto LABEL_47;
    v26 = GlobalAlloc(0x2002u, 0x202Cu);
    v27 = v26;
    if ( v26 && (v28 = GlobalLock(v26), (v29 = v28) != 0) )
    {
      v28[2] = v27;
      v28[1] = 8224;
      memset(v28 + 3, 0, 0x2020u);
      *v29 = 1;
      pExcelRecordBuffer = v29 + 3;
      if ( v29 != (_DWORD *)-12 )
      {
LABEL_47:
        g_cbCurrentSize = 8224;
        if ( !dword_1003A75C )
        {
          v30 = OleInitialize(0);
          if ( v30 != -2147417850 )
          {
            if ( v30 )
            {
              if ( v30 != 1 )
              {
                Settings = -19;
                goto LABEL_58;
              }
              OleUninitialize();
            }
            else
            {
              ++dword_1003A75C;
            }
          }
        }
        WorkbookSetupLocalizedInfo(&ControlPanelSettings);
        Settings = FMTControlPanelGetSettings();
        if ( !Settings )
        {
          Settings = ControlPanelBuildFormats();
          if ( !Settings )
          {
            NameLocalizer = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD))ExpandBuiltinName;
LABEL_61:
            WorkbookGetLimits();
            goto LABEL_62;
          }
        }
LABEL_58:
        result = TranslateEXErrorToJETError(Settings);
        if ( result )
          return result;
        goto LABEL_61;
      }
    }
    else
    {
      pExcelRecordBuffer = 0;
    }
    Settings = -2;
    goto LABEL_58;
  }
LABEL_62:
  CurrentProcessId = GetCurrentProcessId();
  v34 = (_DWORD *)dword_1003AE68;
  v35 = CurrentProcessId;
  if ( !dword_1003AE68 )
    goto LABEL_68;
  while ( v34[4] != CurrentProcessId )
  {
    v34 = (_DWORD *)*v34;
    if ( !v34 )
      goto LABEL_68;
  }
  if ( !v34 )
  {
LABEL_68:
    v36 = (_DWORD *)MemAllocate(36);
    v34 = v36;
    if ( !v36 )
      return -1011;
    *v36 = dword_1003AE68;
    v37 = dword_1003A750;
    v34[5] = 1;
    v34[6] = 1;
    v34[4] = v35;
    v34[7] = v37;
    dword_1003AE68 = (int)v34;
    v34[3] = 0;
    v34[8] = a1;
  }
  ++v34[3];
  result = 0;
  ++dword_1003A74C;
  return result;
}

```

## disassembly

```asm
0x10006bd0  mov     edi, edi
0x10006bd2  push    ebp
0x10006bd3  mov     ebp, esp
0x10006bd5  sub     esp, 224h
0x10006bdb  mov     eax, ___security_cookie
0x10006be0  xor     eax, ebp
0x10006be2  mov     [ebp+var_4], eax
0x10006be5  cmp     dword_1003A74C, 0
0x10006bec  push    ebx
0x10006bed  push    esi
0x10006bee  push    edi
0x10006bef  mov     [ebp+var_21C], 0
0x10006bf9  jnz     loc_10006FC1
0x10006bff  push    20Ah
0x10006c04  lea     eax, [ebp+var_210]
0x10006c0a  push    eax
0x10006c0b  lea     eax, [ebp+var_21C]
0x10006c11  push    eax
0x10006c12  mov     eax, dword_1003A750
0x10006c17  push    37h ; '7'
0x10006c19  push    0
0x10006c1b  push    [ebp+arg_0]
0x10006c1e  mov     esi, [eax+80h]
0x10006c24  mov     ecx, esi
0x10006c26  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10006c2c  call    esi
0x10006c2e  test    eax, eax
0x10006c30  jz      short loc_10006C3B
0x10006c32  xor     eax, eax
0x10006c34  mov     [ebp+var_210], ax
0x10006c3b  mov     _ISAMDefaults, 8
0x10006c45  mov     eax, 7FFFFFFEh
0x10006c4a  mov     dword_1003C2D8, 1
0x10006c54  mov     esi, offset aXls_0; "!xls"
0x10006c59  mov     dword_1003C2D4, 1
0x10006c63  mov     edx, 402h
0x10006c68  mov     dword_1003C2DC, 1
0x10006c72  mov     ecx, offset _DefaultSecureExtensions
0x10006c77  test    eax, eax
0x10006c79  jz      short loc_10006C92
0x10006c7b  movzx   edi, word ptr [esi]
0x10006c7e  test    di, di
0x10006c81  jz      short loc_10006C92
0x10006c83  mov     [ecx], di
0x10006c86  add     esi, 2
0x10006c89  add     ecx, 2
0x10006c8c  dec     eax
0x10006c8d  sub     edx, 1
0x10006c90  jnz     short loc_10006C77
0x10006c92  lea     eax, [ecx-2]
0x10006c95  test    edx, edx
0x10006c97  cmovnz  eax, ecx
0x10006c9a  xor     ecx, ecx
0x10006c9c  mov     [eax], cx
0x10006c9f  call    SetupConfigurationSpec
0x10006ca4  mov     edi, eax
0x10006ca6  test    edi, edi
0x10006ca8  jz      loc_10006D4C
0x10006cae  mov     esi, [edi]
0x10006cb0  mov     eax, [ebp+var_21C]
0x10006cb6  mov     [ebp+var_214], eax
0x10006cbc  test    esi, esi
0x10006cbe  jz      short loc_10006CFC
0x10006cc0  movzx   eax, byte ptr [esi+4]
0x10006cc4  cmp     eax, 3; switch 4 cases
0x10006cc7  ja      short def_10006CC9; jumptable 10006CC9 default case
0x10006cc9  jmp     ds:jpt_10006CC9[eax*4]; switch jump
0x10006cd0  mov     edx, [esi+14h]; jumptable 10006CC9 case 0
0x10006cd3  test    edx, edx
0x10006cd5  jz      short loc_10006CE4
0x10006cd7  push    dword ptr [esi+10h]
0x10006cda  mov     ecx, [esi+0Ch]
0x10006cdd  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10006ce2  jmp     short def_10006CC9; jumptable 10006CC9 default case
0x10006ce4  mov     eax, [esi+0Ch]
0x10006ce7  xor     ecx, ecx
0x10006ce9  mov     [eax], cx
0x10006cec  jmp     short def_10006CC9; jumptable 10006CC9 default case
0x10006cee  mov     ecx, [esi+0Ch]; jumptable 10006CC9 cases 1-3
0x10006cf1  mov     eax, [esi+10h]
0x10006cf4  mov     [ecx], eax
0x10006cf6  mov     esi, [esi]; jumptable 10006CC9 default case
0x10006cf8  test    esi, esi
0x10006cfa  jnz     short loc_10006CC0
0x10006cfc  push    edi
0x10006cfd  push    offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x10006d02  xor     edx, edx
0x10006d04  call    ReadRegSpec
0x10006d09  mov     ebx, eax
0x10006d0b  test    ebx, ebx
0x10006d0d  jnz     short loc_10006D24
0x10006d0f  mov     edx, [ebp+var_214]
0x10006d15  lea     eax, [ebp+var_210]
0x10006d1b  push    edi
0x10006d1c  push    eax
0x10006d1d  call    ReadRegSpec
0x10006d22  mov     ebx, eax
0x10006d24  mov     ecx, [edi]
0x10006d26  test    ecx, ecx
0x10006d28  jz      short loc_10006D3D
0x10006d2a  nop     word ptr [eax+eax+00h]
0x10006d30  mov     esi, [ecx]
0x10006d32  call    _MemFree@4; MemFree(x)
0x10006d37  mov     ecx, esi
0x10006d39  test    esi, esi
0x10006d3b  jnz     short loc_10006D30
0x10006d3d  mov     ecx, edi
0x10006d3f  call    _MemFree@4; MemFree(x)
0x10006d44  test    ebx, ebx
0x10006d46  jnz     loc_10006FE0
0x10006d4c  mov     eax, _ISAMDefaults
0x10006d51  test    eax, eax
0x10006d53  js      loc_10006FE0
0x10006d59  mov     ecx, dword_1003C2D8
0x10006d5f  test    ecx, ecx
0x10006d61  js      loc_10006FE0
0x10006d67  cmp     ecx, 10h
0x10006d6a  jg      loc_10006FE0
0x10006d70  test    eax, eax
0x10006d72  jnz     short loc_10006D7E
0x10006d74  mov     _ISAMDefaults, 4000h
0x10006d7e  xor     eax, eax
0x10006d80  mov     dword_1003B29C, 0
0x10006d8a  cmp     _DefaultSecureExtensions, 21h ; '!'
0x10006d92  mov     dword_1003B2A0, 0
0x10006d9c  jnz     short loc_10006DAD
0x10006d9e  mov     dword_1003B2A0, 1
0x10006da8  mov     eax, 1
0x10006dad  xor     ebx, ebx
0x10006daf  mov     ecx, 0FFh
0x10006db4  mov     edi, offset _SecureExtensions
0x10006db9  mov     [ebp+var_218], ebx
0x10006dbf  push    ebx; Context
0x10006dc0  rep stosd
0x10006dc2  lea     eax, _DefaultSecureExtensions[eax*2]
0x10006dc9  push    offset Delimiter; ","
0x10006dce  push    eax; String
0x10006dcf  call    ds:__imp__wcstok
0x10006dd5  add     esp, 0Ch
0x10006dd8  mov     [ebp+var_214], eax
0x10006dde  test    eax, eax
0x10006de0  jz      loc_10006EB4
0x10006de6  nop     word ptr [eax+eax+00000000h]
0x10006df0  mov     edx, eax
0x10006df2  mov     [ebp+var_224], offset aNone; "None"
0x10006dfc  mov     eax, [ebp+var_224]
0x10006e02  mov     [ebp+var_220], edx
0x10006e08  movzx   ecx, word ptr [edx]
0x10006e0b  lea     eax, [eax+2]
0x10006e0e  mov     edx, ecx
0x10006e10  lea     esi, [ecx-41h]
0x10006e13  lea     ecx, [edx+20h]
0x10006e16  cmp     si, 19h
0x10006e1a  movzx   edi, cx
0x10006e1d  mov     ecx, edx
0x10006e1f  cmova   edi, ecx
0x10006e22  movzx   ecx, word ptr [eax-2]
0x10006e26  mov     edx, ecx
0x10006e28  movzx   ebx, di
0x10006e2b  lea     esi, [ecx-41h]
0x10006e2e  lea     ecx, [edx+20h]
0x10006e31  cmp     si, 19h
0x10006e35  movzx   edi, cx
0x10006e38  mov     ecx, edx
0x10006e3a  mov     edx, [ebp+var_220]
0x10006e40  cmova   edi, ecx
0x10006e43  add     edx, 2
0x10006e46  movzx   ecx, di
0x10006e49  mov     [ebp+var_220], edx
0x10006e4f  test    bx, bx
0x10006e52  jz      short loc_10006E59
0x10006e54  cmp     bx, cx
0x10006e57  jz      short loc_10006E08
0x10006e59  mov     eax, [ebp+var_214]
0x10006e5f  mov     edx, ebx
0x10006e61  mov     ebx, [ebp+var_218]
0x10006e67  sub     edx, ecx
0x10006e69  jnz     short loc_10006E77
0x10006e6b  sub     eax, offset _DefaultSecureExtensions
0x10006e70  sar     eax, 1
0x10006e72  add     eax, 4
0x10006e75  jmp     short loc_10006E86
0x10006e77  cmp     ebx, 0FFh
0x10006e7d  jge     short loc_10006E8D
0x10006e7f  sub     eax, offset _DefaultSecureExtensions
0x10006e84  sar     eax, 1
0x10006e86  mov     _SecureExtensions[ebx*4], eax
0x10006e8d  push    0; Context
0x10006e8f  push    offset Delimiter; ","
0x10006e94  inc     ebx
0x10006e95  push    0; String
0x10006e97  mov     [ebp+var_218], ebx
0x10006e9d  call    ds:__imp__wcstok
0x10006ea3  add     esp, 0Ch
0x10006ea6  mov     [ebp+var_214], eax
0x10006eac  test    eax, eax
0x10006eae  jnz     loc_10006DF0
0x10006eb4  cmp     _pExcelRecordBuffer, 0
0x10006ebb  mov     dword_1003B29C, ebx
0x10006ec1  mov     dword_1003AE68, 0
0x10006ecb  mov     dword_1003A660, 1
0x10006ed5  jnz     short loc_10006F27
0x10006ed7  push    202Ch; dwBytes
0x10006edc  push    2002h; uFlags
0x10006ee1  call    ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x10006ee7  mov     esi, eax
0x10006ee9  test    esi, esi
0x10006eeb  jz      short loc_10006F59
0x10006eed  push    esi; hMem
0x10006eee  call    ds:__imp__GlobalLock@4; GlobalLock(x)
0x10006ef4  mov     edi, eax
0x10006ef6  test    edi, edi
0x10006ef8  jz      short loc_10006F59
0x10006efa  push    2020h; Size
0x10006eff  mov     [edi+8], esi
0x10006f02  lea     esi, [edi+0Ch]
0x10006f05  push    0; Val
0x10006f07  push    esi; void *
0x10006f08  mov     dword ptr [edi+4], 2020h
0x10006f0f  call    _memset
0x10006f14  add     esp, 0Ch
0x10006f17  mov     dword ptr [edi], 1
0x10006f1d  mov     _pExcelRecordBuffer, esi
0x10006f23  test    esi, esi
0x10006f25  jz      short loc_10006F63
0x10006f27  cmp     dword_1003A75C, 0
0x10006f2e  mov     _g_cbCurrentSize, 2020h
0x10006f38  jnz     short loc_10006F78
0x10006f3a  push    0; pvReserved
0x10006f3c  call    ds:__imp__OleInitialize@4; OleInitialize(x)
0x10006f42  cmp     eax, 80010106h
0x10006f47  jz      short loc_10006F78
0x10006f49  test    eax, eax
0x10006f4b  jz      short loc_10006F72
0x10006f4d  cmp     eax, 1
0x10006f50  jz      short loc_10006F6A
0x10006f52  mov     eax, 0FFFFFFEDh
0x10006f57  jmp     short loc_10006F94
0x10006f59  mov     _pExcelRecordBuffer, 0
0x10006f63  mov     eax, 0FFFFFFFEh
0x10006f68  jmp     short loc_10006F94
0x10006f6a  call    ds:__imp__OleUninitialize@0; OleUninitialize()
0x10006f70  jmp     short loc_10006F78
0x10006f72  inc     dword_1003A75C
0x10006f78  push    offset _ControlPanelSettings
0x10006f7d  call    _WorkbookSetupLocalizedInfo@4; WorkbookSetupLocalizedInfo(x)
0x10006f82  call    _FMTControlPanelGetSettings@4; FMTControlPanelGetSettings(x)
0x10006f87  test    eax, eax
0x10006f89  jnz     short loc_10006F94
0x10006f8b  call    _ControlPanelBuildFormats@8; ControlPanelBuildFormats(x,x)
0x10006f90  test    eax, eax
0x10006f92  jz      short loc_10006FB2
0x10006f94  mov     ecx, eax
0x10006f96  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x10006f9b  test    eax, eax
0x10006f9d  jz      short loc_10006FBC
0x10006f9f  pop     edi
0x10006fa0  pop     esi
0x10006fa1  pop     ebx
0x10006fa2  mov     ecx, [ebp+var_4]
0x10006fa5  xor     ecx, ebp; StackCookie
0x10006fa7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006fac  mov     esp, ebp
0x10006fae  pop     ebp
0x10006faf  retn    4
0x10006fb2  mov     _NameLocalizer, offset _ExpandBuiltinName@12; ExpandBuiltinName(x,x,x) ...
0x10006fbc  call    _WorkbookGetLimits@4; WorkbookGetLimits(x)
0x10006fc1  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10006fc7  mov     ecx, dword_1003AE68
0x10006fcd  mov     esi, eax
0x10006fcf  test    ecx, ecx
0x10006fd1  jz      short loc_10006FFC
0x10006fd3  cmp     [ecx+10h], esi
0x10006fd6  jz      short loc_10006FF8
0x10006fd8  mov     ecx, [ecx]
0x10006fda  test    ecx, ecx
0x10006fdc  jnz     short loc_10006FD3
0x10006fde  jmp     short loc_10006FFC
0x10006fe0  pop     edi
0x10006fe1  pop     esi
0x10006fe2  mov     eax, 0FFFFEC57h
0x10006fe7  pop     ebx
0x10006fe8  mov     ecx, [ebp+var_4]
0x10006feb  xor     ecx, ebp; StackCookie
0x10006fed  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10006ff2  mov     esp, ebp
0x10006ff4  pop     ebp
0x10006ff5  retn    4
0x10006ff8  test    ecx, ecx
0x10006ffa  jnz     short loc_10007057
0x10006ffc  mov     ecx, 24h ; '$'
0x10007001  call    _MemAllocate@4; MemAllocate(x)
0x10007006  mov     ecx, eax
0x10007008  test    ecx, ecx
0x1000700a  jnz     short loc_10007024
0x1000700c  pop     edi
0x1000700d  pop     esi
0x1000700e  mov     eax, 0FFFFFC0Dh
0x10007013  pop     ebx
0x10007014  mov     ecx, [ebp+var_4]
  ... truncated ...
```
