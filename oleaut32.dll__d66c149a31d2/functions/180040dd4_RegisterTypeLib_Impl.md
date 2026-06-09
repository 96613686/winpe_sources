# RegisterTypeLib_Impl

- ea: `0x180040dd4`
- end: `0x180041619`
- name: `RegisterTypeLib_Impl`
- size: `2117`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040d20`
- `0x1800591f0`

## callees

- `0x18001a97c`
- `0x180021dc0`
- `0x1800228e0`
- `0x180038078`
- `0x1800381e8`
- `0x1800383a4`
- `0x1800384ec`
- `0x18003e788`
- `0x180040dd4`
- `0x18004d900`
- `0x18004e530`
- `0x180054790`
- `0x180068074`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180041029`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18004106e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180041199`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800411f4`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180041029`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18004106e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180041199`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800411f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040ef1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040ef1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800411d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041325`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004158e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800411d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041325`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004158e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041598`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800415ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800412a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800412a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180040fe6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041415`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041467`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180040fe6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041415`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180041467`

## pseudocode

```c
__int64 __fastcall RegisterTypeLib_Impl(HKEY hKey, __int64 *a2, WCHAR *a3, wchar_t *a4)
{
  int v7; // ebx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // r8
  int v10; // ecx
  int v11; // ecx
  const WCHAR *v12; // r14
  unsigned int (__fastcall **v13)(__int64 *, GUID *, __int64 *); // rax
  __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r8
  BSTR v17; // rax
  unsigned int v18; // ecx
  __int64 v19; // rcx
  const BYTE *v20; // r9
  __int64 v21; // r8
  __int64 v22; // rax
  wchar_t *v23; // rdx
  _WORD *PathEnd; // rax
  unsigned int v25; // edi
  unsigned __int16 v26; // ax
  unsigned int v27; // r12d
  __int64 v28; // rax
  _QWORD *v29; // rcx
  __int16 v30; // r14
  wchar_t *v31; // rax
  __int64 v32; // rax
  GUID *rguid; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v36; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v37; // [rsp+58h] [rbp-A8h]
  _QWORD *v38; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v39; // [rsp+68h] [rbp-98h] BYREF
  GenericTypeLibOLE *v40; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKeya; // [rsp+90h] [rbp-70h] BYREF
  HKEY v45; // [rsp+98h] [rbp-68h] BYREF
  HKEY v46; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v47; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v48; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v49; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v50; // [rsp+C0h] [rbp-40h] BYREF
  HKEY v51; // [rsp+C8h] [rbp-38h]
  _QWORD v52[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v53; // [rsp+E0h] [rbp-20h]
  wchar_t *v54; // [rsp+E8h] [rbp-18h]
  int v55; // [rsp+F0h] [rbp-10h]
  OLECHAR *v56; // [rsp+F8h] [rbp-8h]
  int v57; // [rsp+100h] [rbp+0h]
  WCHAR *v58; // [rsp+108h] [rbp+8h]
  int v59; // [rsp+110h] [rbp+10h]
  GUID v60; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v61[4]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v62; // [rsp+138h] [rbp+38h]
  WCHAR SubKey[8]; // [rsp+140h] [rbp+40h] BYREF
  int v64; // [rsp+150h] [rbp+50h]
  WCHAR v65[8]; // [rsp+158h] [rbp+58h] BYREF
  __int16 v66; // [rsp+168h] [rbp+68h]
  OLECHAR sz[40]; // [rsp+170h] [rbp+70h] BYREF
  OLECHAR v68[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t Str[264]; // [rsp+210h] [rbp+110h] BYREF

  v37 = a4;
  v51 = hKey;
  rguid = 0;
  v49 = 0;
  v48 = 0;
  v36 = 0;
  v46 = 0;
  v45 = 0;
  phkResult = 0;
  hKeya = 0;
  v64 = 0;
  v66 = 0;
  *(_QWORD *)v61 = 0;
  v62 = 0;
  v39 = 0;
  v47 = 0;
  bstrString = 0;
  v40 = 0;
  v42 = 0;
  v35 = 0;
  *(_OWORD *)SubKey = 0;
  *(_OWORD *)v65 = 0;
  if ( a2 && a3 )
  {
    v50 = 0;
    v7 = ConvertPathToUNC(a3, &v50);
    if ( v7 < 0 )
    {
LABEL_96:
      MemFree(v50);
      return (unsigned int)v7;
    }
    v8 = -1;
    if ( v50 )
    {
      do
        ++v8;
      while ( v50[v8] );
      if ( v8 >= 0x104 )
      {
LABEL_7:
        v7 = -2147024809;
        goto LABEL_96;
      }
      v9 = v50;
    }
    else
    {
      do
        ++v8;
      while ( a3[v8] );
      if ( v8 >= 0x104 )
        goto LABEL_7;
      v9 = a3;
    }
    _o_wcscpy_s(Str, 260, v9);
    v7 = (*(__int64 (__fastcall **)(__int64 *, GUID **))(*a2 + 56))(a2, &rguid);
    if ( v7 < 0 )
      goto LABEL_96;
    v10 = *(_DWORD *)&rguid[1].Data2;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 2 )
        {
          v7 = -2147319779;
LABEL_95:
          (*(void (__fastcall **)(__int64 *))(*a2 + 96))(a2);
          goto LABEL_96;
        }
        v12 = L"win64";
      }
      else
      {
        v12 = L"win32";
      }
    }
    else
    {
      v12 = L"win16";
    }
    v13 = (unsigned int (__fastcall **)(__int64 *, GUID *, __int64 *))*a2;
    v40 = 0;
    v42 = 0;
    if ( (*v13)(a2, &IID_CTypeLib2, &v42) )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64 *, GUID *, GenericTypeLibOLE **))*a2)(
              a2,
              &IID_IGenericTypeLibOLE,
              &v40) )
        GenericTypeLibOLE::Release(v40);
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    if ( FastRegCreateKey(hKey, L"TypeLib", &v49, 0x2000000u) )
    {
      v7 = -2147319780;
      goto LABEL_95;
    }
    StringFromGUID2(rguid, sz, 39);
    if ( FastRegCreateKey(v49, sz, &v48, 0x2000000u) )
    {
      v7 = -2147319780;
LABEL_94:
      RegCloseKey(v49);
      goto LABEL_95;
    }
    _o__ultow_s(*(unsigned __int16 *)rguid[1].Data4, SubKey, 10, 16);
    v14 = -1;
    do
      ++v14;
    while ( SubKey[v14] );
    SubKey[v14] = 46;
    _o__ultow_s(*(unsigned __int16 *)&rguid[1].Data4[2], &SubKey[v14 + 1], 10 - ((2 * v14 + 2) >> 1), 16);
    v15 = -1;
    do
      ++v15;
    while ( SubKey[v15] );
    if ( FastRegCreateKey(v48, SubKey, &v36, 0x2000000u) )
    {
      v7 = -2147319780;
LABEL_93:
      RegCloseKey(v48);
      goto LABEL_94;
    }
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, BSTR *, _QWORD, BSTR *))(*a2 + 72))(
           a2,
           0xFFFFFFFFLL,
           0,
           &v39,
           0,
           &v47);
    if ( v7 >= 0 )
    {
      v17 = v39;
      if ( v39 )
        goto LABEL_39;
      v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, BSTR *, _QWORD, _QWORD, _QWORD))(*a2 + 72))(
             a2,
             0xFFFFFFFFLL,
             &v39,
             0,
             0,
             0);
      if ( v7 >= 0 )
      {
        v17 = v39;
        if ( !v39 )
        {
          v18 = 1;
LABEL_42:
          v20 = (const BYTE *)&psz;
          if ( v17 )
            v20 = (const BYTE *)v17;
          if ( (unsigned int)FastRegSetValueEx(v36, 0, v16, v20, v18)
            || FastRegCreateKey(v36, L"FLAGS", &hKeya, 0x2000000u) )
          {
            v7 = -2147319780;
LABEL_91:
            SysFreeString(v39);
            SysFreeString(v47);
            goto LABEL_92;
          }
          _o__ultow_s(*(_WORD *)&rguid[1].Data4[4] & 0xFFF7, v61, 5, 16);
          v22 = -1;
          do
            ++v22;
          while ( v61[v22] );
          if ( (unsigned int)FastRegSetValueEx(hKeya, 0, v21, (const BYTE *)v61, (int)v22 + 1) )
            v7 = -2147319780;
          RegCloseKey(hKeya);
          if ( v7 )
            goto LABEL_91;
          _o__ultow_s(rguid[1].Data1, v65, 9, 16);
          if ( FastRegCreateKey(v36, v65, &v46, 0x2000000u) )
          {
            v7 = -2147319780;
            goto LABEL_91;
          }
          if ( FastRegCreateKey(v46, v12, &v45, 0x2000000u) )
          {
            v7 = -2147319780;
LABEL_90:
            RegCloseKey(v46);
            goto LABEL_91;
          }
          v7 = RegisterPathAndAlias(v45, Str);
          if ( v7 < 0 )
          {
LABEL_89:
            RegCloseKey(v45);
            goto LABEL_90;
          }
          if ( v37 || RegOpenKeyExW(v36, L"HELPDIR", 0, 0x2000000u, &phkResult) )
          {
            if ( FastRegCreateKey(v36, L"HELPDIR", &phkResult, 0x2000000u) )
            {
              v7 = -2147319780;
              goto LABEL_89;
            }
            v23 = v37;
            if ( !v37 )
            {
              v37 = Str;
              PathEnd = (_WORD *)GetPathEnd(Str);
              v23 = v37;
              if ( PathEnd )
                *PathEnd = 0;
              else
                Str[0] = 0;
            }
            v7 = RegisterPathAndAlias(phkResult, v23);
          }
          RegCloseKey(phkResult);
          memset_0(v52, 0, 0x48u);
          v57 = 39;
          v52[0] = v68;
          v56 = sz;
          v25 = 0;
          v58 = SubKey;
          v59 = v15 + 1;
          v26 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
          v27 = v26;
          if ( !v26 )
            goto LABEL_89;
          while ( 1 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(*a2 + 40))(a2, v25, &v35);
            if ( v7 < 0 )
              goto LABEL_89;
            if ( (unsigned int)(v35 - 3) <= 1 )
            {
              v28 = *a2;
              v38 = 0;
              v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD **))(v28 + 32))(a2, v25, &v38);
              if ( v7 < 0 )
                goto LABEL_89;
              if ( v40 )
              {
                v60 = 0;
                v60 = *(GUID *)(*((_QWORD *)v40 + 4) + 80LL * (unsigned __int16)v25 + 56);
                StringFromGUID2(&v60, v68, 39);
                v29 = v38;
                v30 = *(_WORD *)(v38[7] + 132LL) >> 3;
              }
              else
              {
                *(_QWORD *)&v60.Data1 = 0;
                v7 = (*(__int64 (__fastcall **)(_QWORD *, GUID *))(*v38 + 24LL))(v38, &v60);
                if ( v7 < 0 )
                {
                  (*(void (__fastcall **)(_QWORD *))(*v38 + 16LL))(v38);
                  goto LABEL_89;
                }
                StringFromGUID2(*(const GUID *const *)&v60.Data1, v68, 39);
                v30 = *(_WORD *)(*(_QWORD *)&v60.Data1 + 58LL);
                (*(void (__fastcall **)(_QWORD *))(*v38 + 152LL))(v38);
                v29 = v38;
              }
              (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
              if ( (v30 & 0x140) != 0 )
              {
                v31 = a00020424000000_0;
              }
              else
              {
                if ( v35 == 3 )
                  goto LABEL_85;
                v31 = a00020420000000_0;
              }
              v55 = 39;
              v54 = v31;
              if ( (v30 & 0x4000) != 0 )
              {
                v54 = 0;
                v55 = 0;
              }
              v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))(*a2 + 72))(
                     a2,
                     v25,
                     &bstrString,
                     0,
                     0,
                     0);
              if ( v7 < 0 )
                goto LABEL_89;
              v32 = -1;
              v52[1] = bstrString;
              do
                ++v32;
              while ( bstrString[v32] );
              v53 = v32 + 1;
              v7 = RegisterInterface(v51, (__int64)v52);
              if ( v7 < 0 )
              {
                SysFreeString(bstrString);
                goto LABEL_89;
              }
              SysFreeString(bstrString);
              bstrString = 0;
              TraceTypeLibRegister(a3, v37, v47, v39);
            }
LABEL_85:
            if ( ++v25 >= v27 )
              goto LABEL_89;
          }
        }
LABEL_39:
        v19 = -1;
        do
          ++v19;
        while ( v17[v19] );
        v18 = v19 + 1;
        goto LABEL_42;
      }
    }
LABEL_92:
    RegCloseKey(v36);
    goto LABEL_93;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180040dd4  push    rbp
0x180040dd6  push    rbx
0x180040dd7  push    rsi
0x180040dd8  push    rdi
0x180040dd9  push    r12
0x180040ddb  push    r13
0x180040ddd  push    r14
0x180040ddf  push    r15
0x180040de1  lea     rbp, [rsp-338h]
0x180040de9  sub     rsp, 438h
0x180040df0  mov     rax, cs:__security_cookie
0x180040df7  xor     rax, rsp
0x180040dfa  mov     [rbp+370h+var_50], rax
0x180040e01  xor     r12d, r12d
0x180040e04  mov     [rsp+470h+var_418], r9
0x180040e09  xor     eax, eax
0x180040e0b  mov     [rbp+370h+var_3A8], rcx
0x180040e0f  mov     [rsp+470h+rguid], r12
0x180040e14  xorps   xmm0, xmm0
0x180040e17  mov     [rbp+370h+var_3B8], r12
0x180040e1b  xorps   xmm1, xmm1
0x180040e1e  mov     [rbp+370h+var_3C0], r12
0x180040e22  mov     r13, r8
0x180040e25  mov     [rsp+470h+var_420], r12
0x180040e2a  mov     rsi, rdx
0x180040e2d  mov     [rbp+370h+var_3D0], r12
0x180040e31  mov     rdi, rcx
0x180040e34  mov     [rbp+370h+var_3D8], r12
0x180040e38  mov     [rbp+370h+var_3E8], r12
0x180040e3c  mov     [rbp+370h+hKey], r12
0x180040e40  mov     [rbp+370h+var_320], eax
0x180040e43  mov     [rbp+370h+var_308], ax
0x180040e47  mov     qword ptr [rbp+370h+var_340], rax
0x180040e4b  mov     [rbp+370h+var_338], ax
0x180040e4f  mov     [rsp+470h+var_408], r12
0x180040e54  mov     [rbp+370h+var_3C8], r12
0x180040e58  mov     [rsp+470h+bstrString], r12
0x180040e5d  mov     [rsp+470h+var_400], r12
0x180040e62  mov     [rbp+370h+var_3F0], r12
0x180040e66  mov     [rsp+470h+var_428], r12d
0x180040e6b  movups  xmmword ptr [rbp+370h+SubKey], xmm0
0x180040e6f  movups  xmmword ptr [rbp+370h+var_318], xmm1
0x180040e73  test    rdx, rdx
0x180040e76  jz      loc_1800415F1
0x180040e7c  test    r8, r8
0x180040e7f  jz      loc_1800415F1
0x180040e85  lea     rdx, [rbp+370h+var_3B0]; unsigned __int16 **
0x180040e89  mov     [rbp+370h+var_3B0], r12
0x180040e8d  mov     rcx, r8; unsigned __int16 *
0x180040e90  call    ?ConvertPathToUNC@@YAJPEBGPEAPEAG@Z; ConvertPathToUNC(ushort const *,ushort * *)
0x180040e95  mov     ebx, eax
0x180040e97  test    eax, eax
0x180040e99  js      loc_1800415E4
0x180040e9f  mov     rbx, [rbp+370h+var_3B0]
0x180040ea3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180040ea7  mov     rax, r15
0x180040eaa  test    rbx, rbx
0x180040ead  jz      short loc_180040ED2
0x180040eaf  inc     rax
0x180040eb2  cmp     [rbx+rax*2], r12w
0x180040eb7  jnz     short loc_180040EAF
0x180040eb9  mov     edx, 104h
0x180040ebe  cmp     rax, rdx
0x180040ec1  jb      short loc_180040ECD
0x180040ec3  mov     ebx, 80070057h
0x180040ec8  jmp     loc_1800415E4
0x180040ecd  mov     r8, rbx
0x180040ed0  jmp     short loc_180040EEA
0x180040ed2  inc     rax
0x180040ed5  cmp     [r13+rax*2+0], r12w
0x180040edb  jnz     short loc_180040ED2
0x180040edd  mov     edx, 104h
0x180040ee2  cmp     rax, rdx
0x180040ee5  jnb     short loc_180040EC3
0x180040ee7  mov     r8, r13
0x180040eea  lea     rcx, [rbp+370h+Str]
0x180040ef1  call    cs:__imp__o_wcscpy_s
0x180040ef7  mov     rax, [rsi]
0x180040efa  lea     rdx, [rsp+470h+rguid]
0x180040eff  mov     rcx, rsi
0x180040f02  mov     rax, [rax+38h]
0x180040f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f0b  mov     ebx, eax
0x180040f0d  test    eax, eax
0x180040f0f  js      loc_1800415E4
0x180040f15  mov     rdx, [rsp+470h+rguid]
0x180040f1a  mov     ecx, [rdx+14h]
0x180040f1d  test    ecx, ecx
0x180040f1f  jz      short loc_180040F47
0x180040f21  sub     ecx, 1
0x180040f24  jz      short loc_180040F3E
0x180040f26  cmp     ecx, 2
0x180040f29  jz      short loc_180040F35
0x180040f2b  mov     ebx, 8002801Dh
0x180040f30  jmp     loc_1800415D5
0x180040f35  lea     r14, aWin64; "win64"
0x180040f3c  jmp     short loc_180040F4E
0x180040f3e  lea     r14, aWin32; "win32"
0x180040f45  jmp     short loc_180040F4E
0x180040f47  lea     r14, aWin16; "win16"
0x180040f4e  mov     rax, [rsi]
0x180040f51  lea     r8, [rbp+370h+var_3F0]
0x180040f55  lea     rdx, IID_CTypeLib2
0x180040f5c  mov     [rsp+470h+var_400], r12
0x180040f61  mov     rcx, rsi
0x180040f64  mov     [rbp+370h+var_3F0], r12
0x180040f68  mov     rax, [rax]
0x180040f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f70  test    eax, eax
0x180040f72  jnz     short loc_180040F86
0x180040f74  mov     rcx, [rbp+370h+var_3F0]
0x180040f78  mov     rax, [rcx]
0x180040f7b  mov     rax, [rax+10h]
0x180040f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f84  jmp     short loc_180040FAE
0x180040f86  mov     rax, [rsi]
0x180040f89  lea     r8, [rsp+470h+var_400]
0x180040f8e  lea     rdx, IID_IGenericTypeLibOLE
0x180040f95  mov     rcx, rsi
0x180040f98  mov     rax, [rax]
0x180040f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fa0  test    eax, eax
0x180040fa2  jnz     short loc_180040FAE
0x180040fa4  mov     rcx, [rsp+470h+var_400]; this
0x180040fa9  call    ?Release@GenericTypeLibOLE@@UEAAKXZ; GenericTypeLibOLE::Release(void)
0x180040fae  mov     ebx, 2000000h
0x180040fb3  lea     r8, [rbp+370h+var_3B8]; phkResult
0x180040fb7  mov     r9d, ebx; samDesired
0x180040fba  lea     rdx, ?TypeLib@Constants@Catalog@Com@@3QBGB; "TypeLib"
0x180040fc1  mov     rcx, rdi; hKey
0x180040fc4  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x180040fc9  test    eax, eax
0x180040fcb  jz      short loc_180040FD7
0x180040fcd  mov     ebx, 8002801Ch
0x180040fd2  jmp     loc_1800415D0
0x180040fd7  mov     rcx, [rsp+470h+rguid]; rguid
0x180040fdc  lea     rdx, [rbp+370h+sz]; lpsz
0x180040fe0  mov     r8d, 27h ; '''; cchMax
0x180040fe6  call    cs:__imp_StringFromGUID2
0x180040fec  mov     rcx, [rbp+370h+var_3B8]; hKey
0x180040ff0  lea     r8, [rbp+370h+var_3C0]; phkResult
0x180040ff4  mov     r9d, ebx; samDesired
0x180040ff7  lea     rdx, [rbp+370h+sz]; lpSubKey
0x180040ffb  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x180041000  test    eax, eax
0x180041002  jz      short loc_18004100E
0x180041004  mov     ebx, 8002801Ch
0x180041009  jmp     loc_1800415C6
0x18004100e  mov     rax, [rsp+470h+rguid]
0x180041013  lea     rdx, [rbp+370h+SubKey]
0x180041017  mov     edi, 10h
0x18004101c  mov     r9d, edi
0x18004101f  movzx   ecx, word ptr [rax+18h]
0x180041023  lea     ebx, [rdi-6]
0x180041026  mov     r8d, ebx
0x180041029  call    cs:__imp__o__ultow_s
0x18004102f  lea     rcx, [rbp+370h+SubKey]
0x180041033  mov     rax, r15
0x180041036  inc     rax
0x180041039  cmp     [rcx+rax*2], r12w
0x18004103e  jnz     short loc_180041036
0x180041040  lea     rdx, [rbp+rax*2+370h+SubKey+2]
0x180041045  mov     ecx, 2Eh ; '.'
0x18004104a  mov     [rbp+rax*2+370h+SubKey], cx
0x18004104f  mov     r9d, edi
0x180041052  lea     rcx, [rbp+370h+SubKey]
0x180041056  mov     rax, rdx
0x180041059  sub     rax, rcx
0x18004105c  sar     rax, 1
0x18004105f  sub     rbx, rax
0x180041062  mov     rax, [rsp+470h+rguid]
0x180041067  mov     r8, rbx
0x18004106a  movzx   ecx, word ptr [rax+1Ah]
0x18004106e  call    cs:__imp__o__ultow_s
0x180041074  lea     rax, [rbp+370h+SubKey]
0x180041078  xor     edi, edi
0x18004107a  mov     r12, r15
0x18004107d  inc     r12
0x180041080  cmp     [rax+r12*2], di
0x180041085  jnz     short loc_18004107D
0x180041087  mov     rcx, [rbp+370h+var_3C0]; hKey
0x18004108b  lea     r8, [rsp+470h+var_420]; phkResult
0x180041090  mov     r9d, 2000000h; samDesired
0x180041096  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x18004109a  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x18004109f  test    eax, eax
0x1800410a1  jz      short loc_1800410AD
0x1800410a3  mov     ebx, 8002801Ch
0x1800410a8  jmp     loc_1800415BC
0x1800410ad  mov     rax, [rsi]
0x1800410b0  lea     rcx, [rbp+370h+var_3C8]
0x1800410b4  mov     [rsp+470h+var_448], rcx
0x1800410b9  lea     r9, [rsp+470h+var_408]
0x1800410be  xor     r8d, r8d
0x1800410c1  mov     [rsp+470h+phkResult], rdi
0x1800410c6  mov     edx, r15d
0x1800410c9  mov     rcx, rsi
0x1800410cc  mov     rax, [rax+48h]
0x1800410d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410d5  mov     ebx, eax
0x1800410d7  test    eax, eax
0x1800410d9  js      loc_1800415B1
0x1800410df  mov     rax, [rsp+470h+var_408]
0x1800410e4  test    rax, rax
0x1800410e7  jnz     short loc_180041126
0x1800410e9  mov     rax, [rsi]
0x1800410ec  lea     r8, [rsp+470h+var_408]
0x1800410f1  mov     [rsp+470h+var_448], rdi
0x1800410f6  xor     r9d, r9d
0x1800410f9  mov     edx, r15d
0x1800410fc  mov     [rsp+470h+phkResult], rdi
0x180041101  mov     rcx, rsi
0x180041104  mov     rax, [rax+48h]
0x180041108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004110d  mov     ebx, eax
0x18004110f  test    eax, eax
0x180041111  js      loc_1800415B1
0x180041117  mov     rax, [rsp+470h+var_408]
0x18004111c  test    rax, rax
0x18004111f  jnz     short loc_180041126
0x180041121  lea     ecx, [rax+1]
0x180041124  jmp     short loc_180041134
0x180041126  mov     rcx, r15
0x180041129  inc     rcx
0x18004112c  cmp     [rax+rcx*2], di
0x180041130  jnz     short loc_180041129
0x180041132  inc     ecx
0x180041134  test    rax, rax
0x180041137  mov     dword ptr [rsp+470h+phkResult], ecx; unsigned int
0x18004113b  mov     rcx, [rsp+470h+var_420]; hKey
0x180041140  lea     r9, psz
0x180041147  cmovnz  r9, rax; unsigned __int16 *
0x18004114b  xor     edx, edx; lpValueName
0x18004114d  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x180041152  test    eax, eax
0x180041154  jz      short loc_180041160
0x180041156  mov     ebx, 8002801Ch
0x18004115b  jmp     loc_18004159E
0x180041160  mov     rcx, [rsp+470h+var_420]; hKey
0x180041165  lea     r8, [rbp+370h+hKey]; phkResult
0x180041169  mov     r9d, 2000000h; samDesired
0x18004116f  lea     rdx, ?FLAGS@Constants@Catalog@Com@@3QBGB; "FLAGS"
0x180041176  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x18004117b  test    eax, eax
0x18004117d  jnz     short loc_180041156
0x18004117f  mov     rax, [rsp+470h+rguid]
0x180041184  lea     rdx, [rbp+370h+var_340]
0x180041188  mov     r9d, 10h
0x18004118e  movzx   ecx, word ptr [rax+1Ch]
0x180041192  and     ecx, 0FFFFFFF7h
0x180041195  lea     r8d, [r9-0Bh]
0x180041199  call    cs:__imp__o__ultow_s
0x18004119f  lea     rcx, [rbp+370h+var_340]
0x1800411a3  mov     rax, r15
0x1800411a6  inc     rax
0x1800411a9  cmp     [rcx+rax*2], di
0x1800411ad  jnz     short loc_1800411A6
0x1800411af  mov     rcx, [rbp+370h+hKey]; hKey
0x1800411b3  lea     r9, [rbp+370h+var_340]; unsigned __int16 *
0x1800411b7  inc     eax
0x1800411b9  xor     edx, edx; lpValueName
0x1800411bb  mov     dword ptr [rsp+470h+phkResult], eax; unsigned int
0x1800411bf  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x1800411c4  mov     rcx, [rbp+370h+hKey]; hKey
0x1800411c8  test    eax, eax
0x1800411ca  mov     edi, 8002801Ch
0x1800411cf  cmovnz  ebx, edi
0x1800411d2  call    cs:__imp_RegCloseKey
0x1800411d8  test    ebx, ebx
0x1800411da  jnz     loc_18004159E
0x1800411e0  mov     rcx, [rsp+470h+rguid]
0x1800411e5  lea     r9d, [rbx+10h]
0x1800411e9  lea     r8d, [rbx+9]
0x1800411ed  lea     rdx, [rbp+370h+var_318]
0x1800411f1  mov     ecx, [rcx+10h]
0x1800411f4  call    cs:__imp__o__ultow_s
0x1800411fa  mov     rcx, [rsp+470h+var_420]; hKey
0x1800411ff  lea     r8, [rbp+370h+var_3D0]; phkResult
0x180041203  mov     ebx, 2000000h
0x180041208  lea     rdx, [rbp+370h+var_318]; lpSubKey
0x18004120c  mov     r9d, ebx; samDesired
0x18004120f  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x180041214  test    eax, eax
0x180041216  jz      short loc_18004121F
0x180041218  mov     ebx, edi
0x18004121a  jmp     loc_18004159E
0x18004121f  mov     rcx, [rbp+370h+var_3D0]; hKey
0x180041223  lea     r8, [rbp+370h+var_3D8]; phkResult
0x180041227  mov     r9d, ebx; samDesired
0x18004122a  mov     rdx, r14; lpSubKey
0x18004122d  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x180041232  test    eax, eax
0x180041234  jz      short loc_18004123D
0x180041236  mov     ebx, edi
0x180041238  jmp     loc_180041594
0x18004123d  mov     rax, [rbp+370h+var_3F0]
0x180041241  test    rax, rax
0x180041244  jz      short loc_180041258
0x180041246  movzx   r14d, word ptr [rax+194h]
0x18004124e  shr     r14d, 3
  ... truncated ...
```
