# DWriteRenderingParams::CreateRenderingParamsFromDeviceName(wchar_t const *)

- ea: `0x1801300e4`
- end: `0x180130732`
- name: `?CreateRenderingParamsFromDeviceName@DWriteRenderingParams@@CA?AV?$ComPtr@VDWriteRenderingParams@@@@PEB_W@Z`
- size: `1614`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012eaec`
- `0x18012ffd0`

## callees

- `0x18012f4bc`
- `0x18012f504`
- `0x18012f598`
- `0x1801300e4`
- `0x180130738`
- `0x1801309f4`
- `0x180130a20`
- `0x180130ad0`
- `0x180131118`
- `0x180212490`
- `0x180212f4c`
- `0x18021deb8`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801301a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801301cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801301a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801301cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013051b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013052b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130510`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013051b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013052b`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130337`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180130337`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18013024c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18013024c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall DWriteRenderingParams::CreateRenderingParamsFromDeviceName(_QWORD *a1, const wchar_t *a2)
{
  _QWORD *v3; // rdi
  char v4; // r15
  char v5; // r12
  bool v6; // si
  HKEY v7; // rbx
  HKEY v8; // rdi
  DWORD i; // esi
  signed __int64 v10; // r8
  WCHAR *j; // rsi
  _DWORD *v12; // rbx
  __int64 v14; // rax
  const wchar_t *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const wchar_t *v18; // rax
  int v19; // ecx
  int v20; // edx
  __int64 v21; // rax
  bool v22[8]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY pvParam; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v26; // [rsp+78h] [rbp-90h] BYREF
  HKEY v27; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v28; // [rsp+88h] [rbp-80h]
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+98h] [rbp-70h] BYREF

  v3 = a1;
  v28 = a1;
  v26 = a1;
  v4 = 0;
  v5 = 1;
  if ( GlyphRenderingParams::overrideSystemRenderingParams_ )
    goto LABEL_37;
  v6 = 0;
  v22[0] = 0;
  phkResult = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &phkResult);
  hKey = 0;
  RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey);
  if ( phkResult || hKey )
  {
    v7 = 0;
    v27 = 0;
    v8 = 0;
    pvParam = 0;
    if ( a2 )
    {
      v15 = SkipDeviceNamePrefix(a2);
      a2 = v15;
      if ( phkResult )
      {
        v17 = RegistryKey::RegistryKey(&v26, &phkResult, v15);
        RegistryKey::operator=(&pvParam, v17);
        RegistryKey::Close((RegistryKey *)&v26);
        v8 = pvParam;
      }
      if ( hKey )
      {
        v16 = RegistryKey::RegistryKey(&v26, &hKey, a2);
        RegistryKey::operator=(&v27, v16);
        RegistryKey::Close((RegistryKey *)&v26);
        v7 = v27;
      }
    }
    if ( !phkResult || v8 )
      v5 = 0;
    if ( hKey && !v7 )
      v4 = 1;
    if ( v5 || v4 )
    {
      memset_0(DisplayDevice.DeviceName, 0, 0x344u);
      DisplayDevice.cb = 840;
      for ( i = 0; ; ++i )
      {
        if ( !EnumDisplayDevicesW(0, i, &DisplayDevice, 0) )
          goto LABEL_51;
        if ( (DisplayDevice.StateFlags & 4) != 0 )
          break;
      }
      for ( j = DisplayDevice.DeviceName; ; j = (WCHAR *)((char *)j + v14) )
      {
        if ( *j == 92 )
        {
          v14 = 2;
        }
        else
        {
          if ( *j != 46 || j[1] != 92 )
          {
            if ( !a2 )
              goto LABEL_21;
            v18 = a2;
            v10 = (char *)j - (char *)a2;
            do
            {
              v19 = *(const wchar_t *)((char *)v18 + v10);
              v20 = *v18 - v19;
              if ( v20 )
                break;
              ++v18;
            }
            while ( v19 );
            if ( v20 )
            {
LABEL_21:
              if ( v5 )
              {
                v21 = RegistryKey::RegistryKey(&v26, &phkResult, j);
                RegistryKey::operator=(&pvParam, v21);
                RegistryKey::Close((RegistryKey *)&v26);
                v8 = pvParam;
              }
              if ( v4 )
              {
                pvParam = 0;
                if ( hKey )
                  OpenKey(hKey, j, v10, &pvParam);
                RegistryKey::Close((RegistryKey *)&v27);
                v7 = pvParam;
                v6 = v22[0];
                break;
              }
            }
LABEL_51:
            v6 = v22[0];
            break;
          }
          v14 = 4;
        }
      }
    }
    if ( v7 )
    {
      LODWORD(pvParam) = 0;
      if ( !(unsigned int)GetNumber(v7, L"GammaLevel", (unsigned int *)&pvParam) )
      {
LABEL_44:
        if ( (v7 && !(unsigned int)GetNumber(v7, L"PixelStructure", (unsigned int *)&pvParam)
           || v8 && !(unsigned int)GetNumber(v8, L"PixelStructure", (unsigned int *)&pvParam))
          && (unsigned int)pvParam <= 2 )
        {
          v6 = 1;
        }
        if ( v7 )
        {
          LODWORD(pvParam) = 0;
          GetNumber(v7, L"ClearTypeLevel", (unsigned int *)&pvParam);
          GetNumber(v7, L"EnhancedContrastLevel", (unsigned int *)&pvParam);
          GetNumber(v7, L"GrayscaleEnhancedContrastLevel", (unsigned int *)&pvParam);
        }
        if ( v8 )
          RegCloseKey(v8);
        goto LABEL_27;
      }
    }
    else
    {
      if ( !v8 )
      {
LABEL_27:
        if ( v7 )
          RegCloseKey(v7);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        v3 = v28;
        goto LABEL_32;
      }
      LODWORD(pvParam) = 0;
    }
    if ( v8 )
      GetNumber(v8, L"GammaLevel", (unsigned int *)&pvParam);
    goto LABEL_44;
  }
LABEL_32:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( !v6 && !GlyphRenderingParams::overrideSystemRenderingParams_ )
  {
    LODWORD(pvParam) = 0;
    SystemParametersInfoW(0x2012u, 0, &pvParam, 0);
    v22[0] = 0;
    DWriteRenderingParams::GetMonitorInvertedFromDeviceName(a2, v22);
  }
LABEL_37:
  v12 = operator new(0x50u);
  v26 = v12;
  DWriteRenderingParams::DWriteRenderingParams(v12);
  *(_QWORD *)v12 = &ComObject<DWriteRenderingParams,DeleteOnZeroReference>::`vftable';
  v12[19] = 0;
  *v3 = v12;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 8LL))(v12);
  return v3;
}

```

## disassembly

```asm
0x1801300e4  mov     rax, rsp
0x1801300e7  mov     [rax+18h], rbx
0x1801300eb  push    rbp
0x1801300ec  push    rsi
0x1801300ed  push    rdi
0x1801300ee  push    r12
0x1801300f0  push    r13
0x1801300f2  push    r14
0x1801300f4  push    r15
0x1801300f6  lea     rbp, [rax-368h]
0x1801300fd  sub     rsp, 430h
0x180130104  movaps  xmmword ptr [rax-48h], xmm7
0x180130108  movaps  xmmword ptr [rax-58h], xmm8
0x18013010d  movaps  xmmword ptr [rax-68h], xmm9
0x180130112  movaps  xmmword ptr [rax-78h], xmm10
0x180130117  mov     rax, cs:__security_cookie
0x18013011e  xor     rax, rsp
0x180130121  mov     [rbp+360h+var_80], rax
0x180130128  mov     r13, rdx
0x18013012b  mov     rdi, rcx
0x18013012e  mov     [rbp+360h+var_3E0], rcx
0x180130132  mov     [rsp+460h+var_3F0], rcx
0x180130137  xor     r15d, r15d
0x18013013a  movss   xmm8, cs:__real@3fe66666
0x180130143  movss   xmm10, cs:__real@3f000000
0x18013014c  movss   xmm7, cs:__real@3f800000
0x180130154  movaps  xmm9, xmm7
0x180130158  lea     r12d, [r15+1]
0x18013015c  mov     r14d, r12d
0x18013015f  lea     ebx, [r15+2]
0x180130163  mov     al, cs:?overrideSystemRenderingParams_@GlyphRenderingParams@@0_NA; bool GlyphRenderingParams::overrideSystemRenderingParams_
0x180130169  test    al, al
0x18013016b  jnz     loc_180130364
0x180130171  mov     sil, r15b
0x180130174  mov     [rsp+460h+var_410], r15b
0x180130179  mov     [rsp+460h+var_3F8], r15
0x18013017e  lea     rax, [rsp+460h+var_3F8]
0x180130183  mov     [rsp+460h+phkResult], rax; phkResult
0x180130188  mov     ebx, 20019h
0x18013018d  mov     r9d, ebx; samDesired
0x180130190  xor     r8d, r8d; ulOptions
0x180130193  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Avalon.Graphics"
0x18013019a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801301a1  call    cs:__imp_RegOpenKeyExW
0x1801301a7  nop
0x1801301a8  mov     [rsp+460h+hKey], r15
0x1801301ad  lea     rax, [rsp+460h+hKey]
0x1801301b2  mov     [rsp+460h+phkResult], rax; phkResult
0x1801301b7  mov     r9d, ebx; samDesired
0x1801301ba  xor     r8d, r8d; ulOptions
0x1801301bd  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Avalon.Graphics"
0x1801301c4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801301cb  call    cs:__imp_RegOpenKeyExW
0x1801301d1  cmp     [rsp+460h+var_3F8], r15
0x1801301d6  jnz     short loc_1801301E3
0x1801301d8  cmp     [rsp+460h+hKey], r15
0x1801301dd  jz      loc_180130301
0x1801301e3  mov     rbx, r15
0x1801301e6  mov     [rsp+460h+var_3E8], rbx
0x1801301eb  mov     rdi, r15
0x1801301ee  mov     [rsp+460h+pvParam], r15
0x1801301f3  test    r13, r13
0x1801301f6  jnz     loc_18013060B
0x1801301fc  cmp     [rsp+460h+var_3F8], r15
0x180130201  jnz     loc_18013065B
0x180130207  mov     r12b, r15b
0x18013020a  cmp     [rsp+460h+hKey], r15
0x18013020f  jz      short loc_180130219
0x180130211  test    rbx, rbx
0x180130214  jnz     short loc_180130219
0x180130216  mov     r15b, 1
0x180130219  test    r12b, r12b
0x18013021c  jnz     short loc_180130227
0x18013021e  test    r15b, r15b
0x180130221  jz      loc_18013055C
0x180130227  xor     edx, edx; Val
0x180130229  mov     r8d, 344h; Size
0x18013022f  lea     rcx, [rbp+360h+DisplayDevice.DeviceName]; void *
0x180130233  call    memset_0
0x180130238  mov     [rbp+360h+DisplayDevice.cb], 348h
0x18013023f  xor     esi, esi
0x180130241  xor     r9d, r9d; dwFlags
0x180130244  lea     r8, [rbp+360h+DisplayDevice]; lpDisplayDevice
0x180130248  mov     edx, esi; iDevNum
0x18013024a  xor     ecx, ecx; lpDevice
0x18013024c  call    cs:__imp_EnumDisplayDevicesW
0x180130252  test    eax, eax
0x180130254  jz      loc_180130557
0x18013025a  test    byte ptr [rbp+360h+DisplayDevice.StateFlags], 4
0x180130261  jz      loc_180130604
0x180130267  lea     rsi, [rbp+360h+DisplayDevice.DeviceName]
0x18013026b  cmp     word ptr [rsi], 5Ch ; '\'
0x18013026f  jz      loc_180130406
0x180130275  cmp     word ptr [rsi], 2Eh ; '.'
0x180130279  jz      loc_180130413
0x18013027f  test    r13, r13
0x180130282  jnz     loc_180130699
0x180130288  test    r12b, r12b
0x18013028b  jnz     loc_1801306C3
0x180130291  test    r15b, r15b
0x180130294  jz      loc_180130557
0x18013029a  xor     r15d, r15d
0x18013029d  mov     [rsp+460h+pvParam], r15
0x1801302a2  mov     rcx, [rsp+460h+hKey]
0x1801302a7  test    rcx, rcx
0x1801302aa  jz      short loc_1801302BA
0x1801302ac  lea     r9, [rsp+460h+pvParam]
0x1801302b1  mov     rdx, rsi
0x1801302b4  call    ?OpenKey@@YAJPEAUHKEY__@@PEB_WW4Allow@RegistryKey@@PEAPEAU1@@Z; OpenKey(HKEY__ *,wchar_t const *,RegistryKey::Allow,HKEY__ * *)
0x1801302b9  nop
0x1801302ba  lea     rcx, [rsp+460h+var_3E8]; this
0x1801302bf  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x1801302c4  mov     rbx, [rsp+460h+pvParam]
0x1801302c9  mov     sil, [rsp+460h+var_410]
0x1801302ce  test    rbx, rbx
0x1801302d1  jnz     loc_180130425
0x1801302d7  test    rdi, rdi
0x1801302da  jnz     loc_1801306F6
0x1801302e0  test    rbx, rbx
0x1801302e3  jnz     loc_18013050D
0x1801302e9  mov     rcx, [rsp+460h+hKey]; hKey
0x1801302ee  test    rcx, rcx
0x1801302f1  jnz     loc_18013051B
0x1801302f7  mov     r12d, 1
0x1801302fd  mov     rdi, [rbp+360h+var_3E0]
0x180130301  mov     rcx, [rsp+460h+var_3F8]; hKey
0x180130306  test    rcx, rcx
0x180130309  jnz     loc_18013052B
0x18013030f  test    sil, sil
0x180130312  jnz     short loc_180130364
0x180130314  mov     al, cs:?overrideSystemRenderingParams_@GlyphRenderingParams@@0_NA; bool GlyphRenderingParams::overrideSystemRenderingParams_
0x18013031a  mov     ebx, 2
0x18013031f  test    al, al
0x180130321  jnz     short loc_180130364
0x180130323  mov     dword ptr [rsp+460h+pvParam], r15d
0x180130328  xor     r9d, r9d; fWinIni
0x18013032b  lea     r8, [rsp+460h+pvParam]; pvParam
0x180130330  xor     edx, edx; uiParam
0x180130332  mov     ecx, 2012h; uiAction
0x180130337  call    cs:__imp_SystemParametersInfoW
0x18013033d  test    eax, eax
0x18013033f  jz      short loc_18013034A
0x180130341  cmp     dword ptr [rsp+460h+pvParam], r15d
0x180130346  cmovz   r14d, ebx
0x18013034a  mov     [rsp+460h+var_410], r15b
0x18013034f  lea     rdx, [rsp+460h+var_410]; bool *
0x180130354  mov     rcx, r13; wchar_t *
0x180130357  call    ?GetMonitorInvertedFromDeviceName@DWriteRenderingParams@@CAJPEB_WPEA_N@Z; DWriteRenderingParams::GetMonitorInvertedFromDeviceName(wchar_t const *,bool *)
0x18013035c  test    eax, eax
0x18013035e  jns     loc_18013053B
0x180130364  mov     ecx, 50h ; 'P'; Size
0x180130369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013036e  mov     rbx, rax
0x180130371  mov     [rsp+460h+var_3F0], rax
0x180130376  mov     [rsp+460h+var_420], r15d
0x18013037b  mov     byte ptr [rsp+460h+var_428], r12b
0x180130380  mov     dword ptr [rsp+460h+var_430], r15d
0x180130385  mov     [rsp+460h+var_438], r14d
0x18013038a  movss   dword ptr [rsp+460h+phkResult], xmm9
0x180130391  movaps  xmm3, xmm7
0x180130394  movaps  xmm2, xmm10
0x180130398  movaps  xmm1, xmm8
0x18013039c  mov     rcx, rax
0x18013039f  call    ??0DWriteRenderingParams@@IEAA@MMMMW4DWRITE_PIXEL_GEOMETRY@@W4DWRITE_RENDERING_MODE1@@_NW4DWRITE_GRID_FIT_MODE@@@Z; DWriteRenderingParams::DWriteRenderingParams(float,float,float,float,DWRITE_PIXEL_GEOMETRY,DWRITE_RENDERING_MODE1,bool,DWRITE_GRID_FIT_MODE)
0x1801303a4  lea     rax, ??_7?$ComObject@VDWriteRenderingParams@@UDeleteOnZeroReference@@@@6B@; const ComObject<DWriteRenderingParams,DeleteOnZeroReference>::`vftable'
0x1801303ab  mov     [rbx], rax
0x1801303ae  mov     [rbx+4Ch], r15d
0x1801303b2  mov     [rdi], rbx
0x1801303b5  mov     rcx, [rbx]
0x1801303b8  mov     rax, [rcx+8]
0x1801303bc  mov     rcx, rbx
0x1801303bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801303c4  nop
0x1801303c5  mov     rax, rdi
0x1801303c8  mov     rcx, [rbp+360h+var_80]
0x1801303cf  xor     rcx, rsp; StackCookie
0x1801303d2  call    __security_check_cookie
0x1801303d7  lea     r11, [rsp+460h+var_30]
0x1801303df  mov     rbx, [r11+50h]
0x1801303e3  movaps  xmm7, xmmword ptr [r11-10h]
0x1801303e8  movaps  xmm8, xmmword ptr [r11-20h]
0x1801303ed  movaps  xmm9, xmmword ptr [r11-30h]
0x1801303f2  movaps  xmm10, xmmword ptr [r11-40h]
0x1801303f7  mov     rsp, r11
0x1801303fa  pop     r15
0x1801303fc  pop     r14
0x1801303fe  pop     r13
0x180130400  pop     r12
0x180130402  pop     rdi
0x180130403  pop     rsi
0x180130404  pop     rbp
0x180130405  retn
0x180130406  mov     eax, 2
0x18013040b  add     rsi, rax
0x18013040e  jmp     loc_18013026B
0x180130413  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180130418  jnz     loc_18013027F
0x18013041e  mov     eax, 4
0x180130423  jmp     short loc_18013040B
0x180130425  mov     dword ptr [rsp+460h+pvParam], r15d
0x18013042a  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x18013042f  lea     rdx, aGammalevel; "GammaLevel"
0x180130436  mov     rcx, rbx; HKEY
0x180130439  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x18013043e  test    eax, eax
0x180130440  jz      loc_1801305B4
0x180130446  test    rdi, rdi
0x180130449  jnz     loc_180130598
0x18013044f  test    rbx, rbx
0x180130452  jz      short loc_180130470
0x180130454  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x180130459  lea     rdx, aPixelstructure; "PixelStructure"
0x180130460  mov     rcx, rbx; HKEY
0x180130463  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x180130468  test    eax, eax
0x18013046a  jz      loc_180130580
0x180130470  test    rdi, rdi
0x180130473  jnz     loc_180130564
0x180130479  test    rbx, rbx
0x18013047c  jz      short loc_1801304F6
0x18013047e  mov     dword ptr [rsp+460h+pvParam], r15d
0x180130483  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x180130488  lea     rdx, aCleartypelevel; "ClearTypeLevel"
0x18013048f  mov     rcx, rbx; HKEY
0x180130492  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x180130497  test    eax, eax
0x180130499  jnz     short loc_1801304B8
0x18013049b  cmp     dword ptr [rsp+460h+pvParam], 64h ; 'd'
0x1801304a0  ja      short loc_1801304B8
0x1801304a2  mov     eax, dword ptr [rsp+460h+pvParam]
0x1801304a6  xorps   xmm9, xmm9
0x1801304aa  cvtsi2ss xmm9, rax
0x1801304af  mulss   xmm9, cs:__real@3c23d70a
0x1801304b8  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x1801304bd  lea     rdx, aEnhancedcontra; "EnhancedContrastLevel"
0x1801304c4  mov     rcx, rbx; HKEY
0x1801304c7  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x1801304cc  mov     r12d, 190h
0x1801304d2  test    eax, eax
0x1801304d4  jz      loc_180130700
0x1801304da  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x1801304df  lea     rdx, aGrayscaleenhan; "GrayscaleEnhancedContrastLevel"
0x1801304e6  mov     rcx, rbx; HKEY
0x1801304e9  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x1801304ee  test    eax, eax
0x1801304f0  jz      loc_1801305E0
0x1801304f6  test    rdi, rdi
0x1801304f9  jz      loc_1801302E0
0x1801304ff  mov     rcx, rdi; hKey
0x180130502  call    cs:__imp_RegCloseKey
0x180130508  jmp     loc_1801302E0
0x18013050d  mov     rcx, rbx; hKey
0x180130510  call    cs:__imp_RegCloseKey
0x180130516  jmp     loc_1801302E9
0x18013051b  call    cs:__imp_RegCloseKey
0x180130521  mov     [rsp+460h+hKey], r15
0x180130526  jmp     loc_1801302F7
0x18013052b  call    cs:__imp_RegCloseKey
0x180130531  mov     [rsp+460h+var_3F8], r15
0x180130536  jmp     loc_18013030F
0x18013053b  cmp     [rsp+460h+var_410], r15b
0x180130540  jz      loc_180130364
0x180130546  cmp     r14d, r12d
0x180130549  jnz     loc_180130726
0x18013054f  mov     r14d, ebx
0x180130552  jmp     loc_180130364
0x180130557  mov     sil, [rsp+460h+var_410]
0x18013055c  xor     r15d, r15d
0x18013055f  jmp     loc_1801302CE
0x180130564  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x180130569  lea     rdx, aPixelstructure; "PixelStructure"
0x180130570  mov     rcx, rdi; HKEY
0x180130573  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x180130578  test    eax, eax
0x18013057a  jnz     loc_180130479
0x180130580  cmp     dword ptr [rsp+460h+pvParam], 2
0x180130585  ja      loc_180130479
0x18013058b  mov     r14d, dword ptr [rsp+460h+pvParam]
0x180130590  mov     sil, 1
0x180130593  jmp     loc_180130479
0x180130598  lea     r8, [rsp+460h+pvParam]; unsigned int *
0x18013059d  lea     rdx, aGammalevel; "GammaLevel"
0x1801305a4  mov     rcx, rdi; HKEY
0x1801305a7  call    ?GetNumber@@YAJPEAUHKEY__@@PEB_WPEAI@Z; GetNumber(HKEY__ *,wchar_t const *,uint *)
0x1801305ac  test    eax, eax
0x1801305ae  jnz     loc_18013044F
0x1801305b4  mov     ecx, dword ptr [rsp+460h+pvParam]
0x1801305b8  lea     eax, [rcx-3E8h]
0x1801305be  cmp     eax, 4B0h
0x1801305c3  ja      loc_18013044F
0x1801305c9  xorps   xmm8, xmm8
0x1801305cd  cvtsi2ss xmm8, rcx
0x1801305d2  mulss   xmm8, cs:__real@3a83126f
0x1801305db  jmp     loc_18013044F
0x1801305e0  cmp     dword ptr [rsp+460h+pvParam], r12d
0x1801305e5  ja      loc_1801304F6
0x1801305eb  mov     eax, dword ptr [rsp+460h+pvParam]
0x1801305ef  xorps   xmm7, xmm7
0x1801305f2  cvtsi2ss xmm7, rax
0x1801305f7  mulss   xmm7, cs:__real@3c23d70a
  ... truncated ...
```
