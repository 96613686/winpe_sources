# DCGetReflectedProperties

- ea: `0x140057788`
- end: `0x140057e0c`
- name: `DCGetReflectedProperties`
- size: `1668`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140058a5c`

## callees

- `0x140005820`
- `0x14000598a`
- `0x14000b0f4`
- `0x1400194c8`
- `0x14001971c`
- `0x140055f80`
- `0x14005607c`
- `0x140056390`
- `0x140057788`
- `0x14005d968`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400577d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400577d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400579f7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400579f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057dc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057b72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057d69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057dc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057df9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140057899`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140057899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140057806`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140057825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140057825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057cee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140057cee`

## string_xrefs

- `0x140057abf`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\ObjectModel\lib\DeclaredConfigurationCommon.h`
- `0x140057d10`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\ObjectModel\lib\DeclaredConfigurationCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DCGetReflectedProperties(HKEY a1, __int64 **a2)
{
  LSTATUS v3; // eax
  LSTATUS v4; // r12d
  LPBYTE v5; // r15
  LPBYTE v6; // rsi
  HKEY v7; // r14
  DWORD LastError; // ebx
  char *v9; // rsi
  __int64 *v10; // rdx
  DWORD i; // r14d
  LPWSTR v12; // rbx
  DWORD v13; // ecx
  __int64 v14; // r8
  char *v15; // r14
  void **v16; // r15
  _QWORD *v17; // r12
  __int64 result; // rax
  unsigned __int64 v19; // rdx
  char *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // r8
  LPBYTE v23; // r9
  unsigned __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rcx
  void ***v27; // rdx
  int phkResult; // [rsp+20h] [rbp-D8h]
  int phkResulta; // [rsp+20h] [rbp-D8h]
  HKEY hKey; // [rsp+60h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-90h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-8Ch] BYREF
  DWORD v33; // [rsp+70h] [rbp-88h]
  LPBYTE lpData[2]; // [rsp+78h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-70h]
  DWORD cbData; // [rsp+90h] [rbp-68h] BYREF
  DWORD cchValueName; // [rsp+94h] [rbp-64h] BYREF
  LPWSTR lpValueName; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 *v39; // [rsp+A0h] [rbp-58h]
  __int128 v40; // [rsp+A8h] [rbp-50h] BYREF
  char *v41; // [rsp+B8h] [rbp-40h]
  char *v42; // [rsp+C0h] [rbp-38h] BYREF
  char *v43; // [rsp+C8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  DWORD cbMaxValueLen; // [rsp+110h] [rbp+18h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+118h] [rbp+20h] BYREF

  hKey = 0;
  lpData[0] = (LPBYTE)&hKey;
  lpData[1] = 0;
  LOBYTE(v35) = 1;
  v3 = RegOpenKeyExW(a1, L"ReflectedProperties", 0, 0x20119u, (PHKEY)&lpData[1]);
  v4 = v3;
  if ( (_BYTE)v35 )
  {
    v5 = lpData[1];
    v6 = lpData[0];
    v7 = *(HKEY *)lpData[0];
    if ( *(_QWORD *)lpData[0] )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    *(_QWORD *)v6 = v5;
  }
  try
  {
    if ( !v4 )
    {
      cValues = 0;
      cbMaxValueNameLen = 0;
      cbMaxValueLen = 0;
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
      {
        v9 = (char *)operator new(0x28u);
        *((_DWORD *)v9 + 2) = 1;
        *((_DWORD *)v9 + 3) = 1;
        *(_QWORD *)v9 = &std::_Ref_count_obj2<DCReflectedProperties>::`vftable';
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 3) = 0;
        *((_QWORD *)v9 + 4) = 0;
        v42 = v9 + 16;
        v43 = v9;
        v10 = a2[1];
        if ( v10 == a2[2] )
        {
          std::vector<std::shared_ptr<DCReflectedProperty>>::_Emplace_reallocate<std::shared_ptr<DCReflectedProperty> const &>(
            a2,
            v10,
            &v42);
          v9 = v43;
        }
        else
        {
          *v10 = 0;
          v10[1] = 0;
          if ( v9 )
            _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
          *v10 = (__int64)(v9 + 16);
          v10[1] = (__int64)v9;
          a2[1] += 2;
        }
        for ( i = 0; ; ++i )
        {
          v33 = i;
          if ( i >= cValues )
            break;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &lpValueName,
            0,
            cbMaxValueNameLen + 1);
          v12 = lpValueName;
          if ( !lpValueName )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x49B,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\ObjectModel\\lib\\DeclaredConfigurationCommon.h",
              (const char *)0x8007000ELL,
              phkResulta);
            if ( v9 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(void *))v9)(v9);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
              }
            }
            if ( hKey )
              RegCloseKey(hKey);
            return 2147942414LL;
          }
          *(_OWORD *)lpData = 0;
          v35 = 0;
          v13 = cbMaxValueLen;
          if ( cbMaxValueLen != -1 )
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpData, cbMaxValueLen + 1);
            v13 = cbMaxValueLen;
          }
          Type = 0;
          cchValueName = cbMaxValueNameLen + 1;
          cbData = v13 + 1;
          if ( !RegEnumValueW(hKey, i, v12, &cchValueName, 0, &Type, lpData[0], &cbData) )
          {
            std::vector<unsigned char>::shrink_to_fit(lpData);
            if ( Type == 1 )
            {
              v40 = 0;
              v15 = (char *)operator new(0x58u);
              *((_DWORD *)v15 + 2) = 1;
              *((_DWORD *)v15 + 3) = 1;
              *(_QWORD *)v15 = &std::_Ref_count_obj2<DCReflectedProperty>::`vftable';
              v16 = (void **)(v15 + 16);
              *((_OWORD *)v15 + 1) = 0;
              *((_QWORD *)v15 + 4) = 0;
              *((_QWORD *)v15 + 5) = 7;
              *((_WORD *)v15 + 8) = 0;
              v17 = v15 + 48;
              *((_OWORD *)v15 + 3) = 0;
              v39 = (unsigned __int64 *)(v15 + 64);
              *((_QWORD *)v15 + 8) = 0;
              *((_QWORD *)v15 + 9) = 7;
              *((_WORD *)v15 + 24) = 0;
              *((_DWORD *)v15 + 20) = 1;
              *(_QWORD *)&v40 = v15 + 16;
              *((_QWORD *)&v40 + 1) = v15;
              if ( v15 == (char *)-16LL )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4B7,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\ObjectModel\\lib\\DeclaredConf"
                                "igurationCommon.h",
                  (const char *)0x8007000ELL,
                  phkResulta);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFF8LL, 0xFFFFFFFF) == 1 )
                {
                  ((void (__fastcall *)(__int64))*MEMORY[0xFFFFFFFFFFFFFFF0])(-16);
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)0xFFFFFFFFFFFFFFFCLL, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(__int64))(MEMORY[0xFFFFFFFFFFFFFFF0] + 8LL))(-16);
                }
                std::vector<unsigned char>::~vector<unsigned char>(lpData);
                LocalFree(v12);
                if ( v9 )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(void *))v9)(v9);
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
                  }
                }
                if ( hKey )
                  RegCloseKey(hKey);
                return 2147942414LL;
              }
              v19 = -1;
              do
                ++v19;
              while ( v12[v19] );
              if ( v19 > *((_QWORD *)v15 + 5) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v16,
                  v19,
                  v14,
                  v12);
              }
              else
              {
                if ( *((_QWORD *)v15 + 5) <= 7u )
                  v20 = v15 + 16;
                else
                  v20 = (char *)*v16;
                v41 = v20;
                *((_QWORD *)v15 + 4) = v19;
                v21 = 2 * v19;
                memmove_0(v20, lpValueName, 2 * v19);
                *(_WORD *)&v41[v21] = 0;
              }
              v23 = lpData[0];
              v24 = -1;
              do
                ++v24;
              while ( *(_WORD *)&lpData[0][2 * v24] );
              if ( v24 > *((_QWORD *)v15 + 9) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  v17,
                  v24,
                  v22,
                  lpData[0]);
              }
              else
              {
                if ( *((_QWORD *)v15 + 9) > 7u )
                  v17 = (_QWORD *)*v17;
                *v39 = v24;
                v25 = 2 * v24;
                memmove_0(v17, v23, 2 * v24);
                *(_WORD *)((char *)v17 + v25) = 0;
              }
              *((_DWORD *)v15 + 20) = 1;
              v26 = **a2;
              v27 = *(void ****)(v26 + 8);
              if ( v27 == *(void ****)(v26 + 16) )
              {
                std::vector<std::shared_ptr<DCReflectedProperty>>::_Emplace_reallocate<std::shared_ptr<DCReflectedProperty> const &>(
                  v26,
                  v27,
                  &v40);
                v15 = (char *)*((_QWORD *)&v40 + 1);
              }
              else
              {
                *v27 = 0;
                v27[1] = 0;
                if ( v15 )
                  _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
                *v27 = v16;
                v27[1] = (void **)v15;
                *(_QWORD *)(v26 + 8) += 16LL;
              }
              v40 = 0u;
              if ( v15 )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(void *))v15)(v15);
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
                }
              }
              v12 = lpValueName;
              i = v33;
            }
          }
          std::vector<unsigned char>::~vector<unsigned char>(lpData);
          LocalFree(v12);
        }
        if ( v9 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(void *))v9)(v9);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\ObjectModel\\lib\\DeclaredConfigurationCommon.h",
      (const char *)0x8007000ELL,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x140057788  mov     r11, rsp
0x14005778b  mov     [r11+8], rbx
0x14005778f  mov     [r11+10h], rsi
0x140057793  push    rdi
0x140057794  push    r12
0x140057796  push    r13
0x140057798  push    r14
0x14005779a  push    r15
0x14005779c  sub     rsp, 0D0h
0x1400577a3  mov     r13, rdx
0x1400577a6  xor     edi, edi
0x1400577a8  mov     [rsp+0F8h+hKey], rdi
0x1400577ad  lea     rax, [rsp+0F8h+hKey]
0x1400577b2  mov     [r11-80h], rax
0x1400577b6  mov     [r11-78h], rdi
0x1400577ba  mov     byte ptr [r11-70h], 1
0x1400577bf  lea     rax, [r11-78h]
0x1400577c3  mov     [rsp+0F8h+phkResult], rax; phkResult
0x1400577c8  mov     r9d, 20119h; samDesired
0x1400577ce  xor     r8d, r8d; ulOptions
0x1400577d1  lea     rdx, aReflectedprope; "ReflectedProperties"
0x1400577d8  call    cs:__imp_RegOpenKeyExW
0x1400577df  nop     dword ptr [rax+rax+00h]
0x1400577e4  mov     r12d, eax
0x1400577e7  cmp     byte ptr [rsp+0F8h+var_70], dil
0x1400577ef  jz      short loc_140057834
0x1400577f1  mov     r15, [rsp+0F8h+lpData+8]
0x1400577f9  mov     rsi, [rsp+0F8h+lpData]
0x1400577fe  mov     r14, [rsi]
0x140057801  test    r14, r14
0x140057804  jz      short loc_140057831
0x140057806  call    cs:__imp_GetLastError
0x14005780d  nop     dword ptr [rax+rax+00h]
0x140057812  mov     ebx, eax
0x140057814  mov     rcx, r14; hKey
0x140057817  call    cs:__imp_RegCloseKey
0x14005781e  nop     dword ptr [rax+rax+00h]
0x140057823  mov     ecx, ebx; dwErrCode
0x140057825  call    cs:__imp_SetLastError
0x14005782c  nop     dword ptr [rax+rax+00h]
0x140057831  mov     [rsi], r15
0x140057834  test    r12d, r12d
0x140057837  jnz     loc_140057DB9
0x14005783d  mov     [rsp+0F8h+cValues], edi
0x140057841  mov     [rsp+0F8h+cbMaxValueNameLen], edi
0x140057848  mov     [rsp+0F8h+cbMaxValueLen], edi
0x14005784f  mov     [rsp+0F8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x140057854  mov     [rsp+0F8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x140057859  lea     rax, [rsp+0F8h+cbMaxValueLen]
0x140057861  mov     [rsp+0F8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140057866  lea     rax, [rsp+0F8h+cbMaxValueNameLen]
0x14005786e  mov     [rsp+0F8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140057873  lea     rax, [rsp+0F8h+cValues]
0x140057878  mov     [rsp+0F8h+lpcValues], rax; lpcValues
0x14005787d  mov     [rsp+0F8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x140057882  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x140057887  mov     [rsp+0F8h+phkResult], rdi; int
0x14005788c  xor     r9d, r9d; lpReserved
0x14005788f  xor     r8d, r8d; lpcchClass
0x140057892  xor     edx, edx; lpClass
0x140057894  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140057899  call    cs:__imp_RegQueryInfoKeyW
0x1400578a0  nop     dword ptr [rax+rax+00h]
0x1400578a5  test    eax, eax
0x1400578a7  jnz     loc_140057DB9
0x1400578ad  lea     ecx, [rax+28h]; Size
0x1400578b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400578b5  mov     rsi, rax
0x1400578b8  mov     dword ptr [rax+8], 1
0x1400578bf  mov     dword ptr [rax+0Ch], 1
0x1400578c6  lea     rax, ??_7?$_Ref_count_obj2@VDCReflectedProperties@@@std@@6B@; const std::_Ref_count_obj2<DCReflectedProperties>::`vftable'
0x1400578cd  mov     [rsi], rax
0x1400578d0  lea     rax, [rsi+10h]
0x1400578d4  mov     [rax], rdi
0x1400578d7  mov     [rax+8], rdi
0x1400578db  mov     [rax+10h], rdi
0x1400578df  mov     [rsp+0F8h+var_38], rax
0x1400578e7  mov     [rsp+0F8h+var_30], rsi
0x1400578ef  mov     rdx, [r13+8]
0x1400578f3  cmp     rdx, [r13+10h]
0x1400578f7  jz      short loc_140057917
0x1400578f9  mov     [rdx], rdi
0x1400578fc  mov     [rdx+8], rdi
0x140057900  test    rsi, rsi
0x140057903  jz      short loc_140057909
0x140057905  lock inc dword ptr [rsi+8]
0x140057909  mov     [rdx], rax
0x14005790c  mov     [rdx+8], rsi
0x140057910  add     qword ptr [r13+8], 10h
0x140057915  jmp     short loc_14005792F
0x140057917  lea     r8, [rsp+0F8h+var_38]
0x14005791f  mov     rcx, r13
0x140057922  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDCReflectedProperty@@@std@@@?$vector@V?$shared_ptr@VDCReflectedProperty@@@std@@V?$allocator@V?$shared_ptr@VDCReflectedProperty@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDCReflectedProperty@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<DCReflectedProperty>>::_Emplace_reallocate<std::shared_ptr<DCReflectedProperty> const &>(std::shared_ptr<DCReflectedProperty> * const,std::shared_ptr<DCReflectedProperty> const &)
0x140057927  mov     rsi, [rsp+0F8h+var_30]
0x14005792f  mov     r14d, edi
0x140057932  mov     [rsp+0F8h+var_88], r14d
0x140057937  cmp     r14d, [rsp+0F8h+cValues]
0x14005793c  jnb     loc_140057D7C
0x140057942  mov     r8d, [rsp+0F8h+cbMaxValueNameLen]
0x14005794a  inc     r8d
0x14005794d  xor     edx, edx
0x14005794f  lea     rcx, [rsp+0F8h+lpValueName]
0x140057957  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14005795c  nop
0x14005795d  mov     rbx, [rsp+0F8h+lpValueName]
0x140057965  test    rbx, rbx
0x140057968  jz      loc_140057D02
0x14005796e  xorps   xmm0, xmm0
0x140057971  movdqu  xmmword ptr [rsp+0F8h+lpData], xmm0
0x140057977  mov     [rsp+0F8h+var_70], rdi
0x14005797f  mov     ecx, [rsp+0F8h+cbMaxValueLen]
0x140057986  lea     eax, [rcx+1]
0x140057989  mov     edx, eax
0x14005798b  test    eax, eax
0x14005798d  jz      short loc_1400579A0
0x14005798f  lea     rcx, [rsp+0F8h+lpData]
0x140057994  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140057999  mov     ecx, [rsp+0F8h+cbMaxValueLen]
0x1400579a0  mov     [rsp+0F8h+Type], edi
0x1400579a4  mov     eax, [rsp+0F8h+cbMaxValueNameLen]
0x1400579ab  inc     eax
0x1400579ad  mov     [rsp+0F8h+cchValueName], eax
0x1400579b4  lea     eax, [rcx+1]
0x1400579b7  mov     [rsp+0F8h+cbData], eax
0x1400579be  mov     rax, [rsp+0F8h+lpData]
0x1400579c3  lea     rcx, [rsp+0F8h+cbData]
0x1400579cb  mov     [rsp+0F8h+lpcValues], rcx; lpcbData
0x1400579d0  mov     [rsp+0F8h+lpcbMaxClassLen], rax; lpData
0x1400579d5  lea     rax, [rsp+0F8h+Type]
0x1400579da  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpType
0x1400579df  mov     [rsp+0F8h+phkResult], rdi; int
0x1400579e4  lea     r9, [rsp+0F8h+cchValueName]; lpcchValueName
0x1400579ec  mov     r8, rbx; lpValueName
0x1400579ef  mov     edx, r14d; dwIndex
0x1400579f2  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1400579f7  call    cs:__imp_RegEnumValueW
0x1400579fe  nop     dword ptr [rax+rax+00h]
0x140057a03  test    eax, eax
0x140057a05  jnz     loc_140057CE0
0x140057a0b  lea     rcx, [rsp+0F8h+lpData]
0x140057a10  call    ?shrink_to_fit@?$vector@EV?$allocator@E@std@@@std@@QEAAXXZ; std::vector<uchar>::shrink_to_fit(void)
0x140057a15  cmp     [rsp+0F8h+Type], 1
0x140057a1a  jnz     loc_140057CE0
0x140057a20  xorps   xmm0, xmm0
0x140057a23  movdqu  [rsp+0F8h+var_50], xmm0
0x140057a2c  mov     ecx, 58h ; 'X'; Size
0x140057a31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057a36  mov     r14, rax
0x140057a39  mov     dword ptr [rax+8], 1
0x140057a40  mov     dword ptr [rax+0Ch], 1
0x140057a47  lea     rax, ??_7?$_Ref_count_obj2@VDCReflectedProperty@@@std@@6B@; const std::_Ref_count_obj2<DCReflectedProperty>::`vftable'
0x140057a4e  mov     [r14], rax
0x140057a51  lea     r15, [r14+10h]
0x140057a55  xorps   xmm0, xmm0
0x140057a58  movups  xmmword ptr [r15], xmm0
0x140057a5c  mov     [r15+10h], rdi
0x140057a60  mov     ecx, 7
0x140057a65  mov     [r15+18h], rcx
0x140057a69  mov     [r15], di
0x140057a6d  lea     r12, [r15+20h]
0x140057a71  movups  xmmword ptr [r12], xmm0
0x140057a76  lea     rax, [r12+10h]
0x140057a7b  mov     [rsp+0F8h+var_58], rax
0x140057a83  mov     [rax], rdi
0x140057a86  mov     [r12+18h], rcx
0x140057a8b  mov     [r12], di
0x140057a90  mov     dword ptr [r15+40h], 1
0x140057a98  mov     qword ptr [rsp+0F8h+var_50], r15
0x140057aa0  mov     qword ptr [rsp+0F8h+var_50+8], r14
0x140057aa8  test    r15, r15
0x140057aab  jnz     loc_140057B88
0x140057ab1  mov     rcx, [rsp+0F8h]; this
0x140057ab9  mov     r9d, 8007000Eh; char *
0x140057abf  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x140057ac6  mov     edx, 4B7h; void *
0x140057acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057ad0  nop
0x140057ad1  test    r14, r14
0x140057ad4  jz      short loc_140057B10
0x140057ad6  or      eax, 0FFFFFFFFh
0x140057ad9  lock xadd [r14+8], eax
0x140057adf  cmp     eax, 1
0x140057ae2  jnz     short loc_140057B10
0x140057ae4  mov     rax, [r14]
0x140057ae7  mov     rcx, r14
0x140057aea  mov     rax, [rax]
0x140057aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057af2  or      eax, 0FFFFFFFFh
0x140057af5  lock xadd [r14+0Ch], eax
0x140057afb  cmp     eax, 1
0x140057afe  jnz     short loc_140057B10
0x140057b00  mov     rax, [r14]
0x140057b03  mov     rcx, r14
0x140057b06  mov     rax, [rax+8]
0x140057b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057b0f  nop
0x140057b10  lea     rcx, [rsp+0F8h+lpData]
0x140057b15  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140057b1a  nop
0x140057b1b  mov     rcx, rbx; hMem
0x140057b1e  call    cs:__imp_LocalFree
0x140057b25  nop     dword ptr [rax+rax+00h]
0x140057b2a  nop
0x140057b2b  test    rsi, rsi
0x140057b2e  jz      short loc_140057B68
0x140057b30  or      eax, 0FFFFFFFFh
0x140057b33  lock xadd [rsi+8], eax
0x140057b38  cmp     eax, 1
0x140057b3b  jnz     short loc_140057B68
0x140057b3d  mov     rax, [rsi]
0x140057b40  mov     rcx, rsi
0x140057b43  mov     rax, [rax]
0x140057b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057b4b  or      eax, 0FFFFFFFFh
0x140057b4e  lock xadd [rsi+0Ch], eax
0x140057b53  cmp     eax, 1
0x140057b56  jnz     short loc_140057B68
0x140057b58  mov     rax, [rsi]
0x140057b5b  mov     rcx, rsi
0x140057b5e  mov     rax, [rax+8]
0x140057b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057b67  nop
0x140057b68  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140057b6d  test    rcx, rcx
0x140057b70  jz      short loc_140057B7E
0x140057b72  call    cs:__imp_RegCloseKey
0x140057b79  nop     dword ptr [rax+rax+00h]
0x140057b7e  mov     eax, 8007000Eh
0x140057b83  jmp     loc_140057DD1
0x140057b88  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140057b8c  inc     rdx
0x140057b8f  cmp     [rbx+rdx*2], di
0x140057b93  jnz     short loc_140057B8C
0x140057b95  cmp     rdx, [r15+18h]
0x140057b99  ja      short loc_140057BDA
0x140057b9b  cmp     [r15+18h], rcx
0x140057b9f  jbe     short loc_140057BA6
0x140057ba1  mov     rax, [r15]
0x140057ba4  jmp     short loc_140057BA9
0x140057ba6  mov     rax, r15
0x140057ba9  mov     [rsp+0F8h+var_40], rax
0x140057bb1  mov     [r15+10h], rdx
0x140057bb5  lea     rbx, [rdx+rdx]
0x140057bb9  mov     r8, rbx; Size
0x140057bbc  mov     rdx, [rsp+0F8h+lpValueName]; Src
0x140057bc4  mov     rcx, rax; void *
0x140057bc7  call    memmove_0
0x140057bcc  mov     rax, [rsp+0F8h+var_40]
0x140057bd4  mov     [rbx+rax], di
0x140057bd8  jmp     short loc_140057BE5
0x140057bda  mov     r9, rbx
0x140057bdd  mov     rcx, r15
0x140057be0  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140057be5  mov     r9, [rsp+0F8h+lpData]
0x140057bea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140057bee  inc     rdx
0x140057bf1  cmp     [r9+rdx*2], di
0x140057bf6  jnz     short loc_140057BEE
0x140057bf8  cmp     rdx, [r12+18h]
0x140057bfd  ja      short loc_140057C2F
0x140057bff  cmp     qword ptr [r12+18h], 7
0x140057c05  jbe     short loc_140057C0B
0x140057c07  mov     r12, [r12]
0x140057c0b  mov     rax, [rsp+0F8h+var_58]
0x140057c13  mov     [rax], rdx
0x140057c16  lea     rbx, [rdx+rdx]
0x140057c1a  mov     r8, rbx; Size
0x140057c1d  mov     rdx, r9; Src
0x140057c20  mov     rcx, r12; void *
0x140057c23  call    memmove_0
0x140057c28  mov     [rbx+r12], di
0x140057c2d  jmp     short loc_140057C37
0x140057c2f  mov     rcx, r12
0x140057c32  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140057c37  mov     dword ptr [r15+40h], 1
0x140057c3f  mov     rax, [r13+0]
0x140057c43  mov     rcx, [rax]
0x140057c46  mov     rdx, [rcx+8]
0x140057c4a  cmp     rdx, [rcx+10h]
0x140057c4e  jz      short loc_140057C6F
0x140057c50  mov     [rdx], rdi
0x140057c53  mov     [rdx+8], rdi
0x140057c57  test    r14, r14
0x140057c5a  jz      short loc_140057C61
0x140057c5c  lock inc dword ptr [r14+8]
0x140057c61  mov     [rdx], r15
0x140057c64  mov     [rdx+8], r14
0x140057c68  add     qword ptr [rcx+8], 10h
0x140057c6d  jmp     short loc_140057C84
0x140057c6f  lea     r8, [rsp+0F8h+var_50]
0x140057c77  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDCReflectedProperty@@@std@@@?$vector@V?$shared_ptr@VDCReflectedProperty@@@std@@V?$allocator@V?$shared_ptr@VDCReflectedProperty@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VDCReflectedProperty@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<DCReflectedProperty>>::_Emplace_reallocate<std::shared_ptr<DCReflectedProperty> const &>(std::shared_ptr<DCReflectedProperty> * const,std::shared_ptr<DCReflectedProperty> const &)
0x140057c7c  mov     r14, qword ptr [rsp+0F8h+var_50+8]
0x140057c84  mov     qword ptr [rsp+0F8h+var_50], rdi
0x140057c8c  mov     qword ptr [rsp+0F8h+var_50+8], rdi
0x140057c94  test    r14, r14
0x140057c97  jz      short loc_140057CD3
0x140057c99  or      eax, 0FFFFFFFFh
0x140057c9c  lock xadd [r14+8], eax
0x140057ca2  cmp     eax, 1
0x140057ca5  jnz     short loc_140057CD3
  ... truncated ...
```
