# I_ReaderListCngPopulateCredsViaContainerEnumeration

- ea: `0x180009c00`
- end: `0x18000a043`
- name: `I_ReaderListCngPopulateCredsViaContainerEnumeration`
- size: `1091`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010d90`

## callees

- `0x180004600`
- `0x180006010`
- `0x180009c00`
- `0x18000a980`
- `0x18000b010`
- `0x18000b09c`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cab`
- `CRYPT32!CertOpenStore` at `0x180009c98`
- `CRYPT32!CertOpenStore` at `0x180009c98`
- `ncrypt!NCryptEnumKeys` at `0x180009eba`
- `ncrypt!NCryptEnumKeys` at `0x180009f27`
- `ncrypt!NCryptEnumKeys` at `0x180009eba`
- `ncrypt!NCryptEnumKeys` at `0x180009f27`
- `ncrypt!NCryptFreeBuffer` at `0x180009f02`
- `ncrypt!NCryptFreeBuffer` at `0x180009f9d`
- `ncrypt!NCryptFreeBuffer` at `0x180009fac`
- `ncrypt!NCryptFreeBuffer` at `0x180009f02`
- `ncrypt!NCryptFreeBuffer` at `0x180009f9d`
- `ncrypt!NCryptFreeBuffer` at `0x180009fac`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x180009e8b`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x180009e8b`

## pseudocode

```c
__int64 __fastcall I_ReaderListCngPopulateCredsViaContainerEnumeration(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v4; // r15d
  NCryptKeyName **p_ppKeyName; // rdi
  HCERTSTORE v8; // rax
  DWORD CngKey; // r14d
  __int64 v10; // rcx
  STRSAFE_LPSTR v11; // rcx
  int v12; // edx
  __int64 v13; // rbx
  __int64 v14; // rax
  bool v15; // zf
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  _DWORD *v21; // rax
  int v22; // eax
  int v23; // ebx
  SECURITY_STATUS v24; // eax
  int v25; // esi
  __int64 v26; // rcx
  NCRYPT_PROV_HANDLE v27; // rcx
  unsigned int v28; // eax
  NCryptKeyName *v29; // rcx
  char v30; // al
  __int64 v32; // [rsp+0h] [rbp-30h] BYREF
  void *pvPara; // [rsp+20h] [rbp-10h]
  int v34; // [rsp+30h] [rbp+0h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+38h] [rbp+8h] BYREF
  int v36; // [rsp+40h] [rbp+10h] BYREF
  PVOID ppEnumState; // [rsp+48h] [rbp+18h] BYREF
  int v38; // [rsp+50h] [rbp+20h] BYREF
  __int64 v39; // [rsp+58h] [rbp+28h]
  __int64 v40; // [rsp+60h] [rbp+30h]

  v39 = a2;
  ppEnumState = 0;
  v4 = 0;
  ppKeyName = 0;
  p_ppKeyName = 0;
  v34 = 0;
  v40 = a1;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *(_QWORD *)(a3 + 168) = v8;
  if ( v8 )
  {
    CngKey = I_SetupNCryptStorageProvider(a3);
    if ( CngKey )
    {
      WppTraceIndent(v10, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v12 = 144;
        LODWORD(pvPara) = CngKey;
LABEL_12:
        WPP_SF_sD(
          *((_QWORD *)v11 + 2),
          v12,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          (char)pvPara);
      }
    }
    else
    {
      v13 = -1;
      v14 = -1;
      do
        v15 = *(_WORD *)(*(_QWORD *)a3 + 2 * v14++ + 2) == 0;
      while ( !v15 );
      v16 = 2 * v14 + 12;
      if ( 2 * v14 == -12
        || v16 > g_ulMaxStackAllocSize
        || v16 + g_ulAdditionalProbeSize + 8 < v16
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_23;
      }
      v17 = v16 + 23;
      if ( v16 + 23 <= v16 + 8 )
        v17 = 0xFFFFFFFFFFFFFF0LL;
      v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
      v19 = alloca(v18);
      v20 = alloca(v18);
      p_ppKeyName = (NCryptKeyName **)&v34;
      if ( &v32 == (__int64 *)-48LL || (v34 = 1801679955, (p_ppKeyName = &ppKeyName) == 0) )
      {
LABEL_23:
        v18 = v16 + 8;
        if ( v16 + 8 >= v16 )
        {
          v21 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_ppKeyName = (NCryptKeyName **)v21;
          if ( v21 )
          {
            *v21 = 1885431112;
            p_ppKeyName = (NCryptKeyName **)(v21 + 2);
          }
        }
      }
      if ( p_ppKeyName )
      {
        do
          v15 = *(_WORD *)(*(_QWORD *)a3 + 2 * v13++ + 2) == 0;
        while ( !v15 );
        if ( StringCchPrintfW((STRSAFE_LPWSTR)p_ppKeyName, v13 + 6, L"\\\\.\\%s\\") >= 0 )
        {
          v15 = *(_DWORD *)(a3 + 12) == 1024;
          v36 = 0;
          if ( v15 && (v38 = 0, v22 = NgcQueryEffectiveCertPolicy(0, &v36, &v38), v22 < 0) )
          {
            CngKey = v22;
          }
          else
          {
            v23 = 0;
            v24 = NCryptEnumKeys(*(_QWORD *)(a3 + 136), (LPCWSTR)p_ppKeyName, &ppKeyName, &ppEnumState, 0x40u);
            v25 = v39;
            v4 = v24;
            while ( 1 )
            {
              if ( v4 )
              {
                v28 = 0;
                *a4 = v23;
                if ( v4 != -2146893782 )
                  v28 = v4;
                v4 = v28;
                goto LABEL_49;
              }
              CngKey = I_ReaderListReadCngKey(v40, a3, (_DWORD)ppKeyName, v25, v36, (__int64)&v34);
              if ( CngKey == 8 )
                break;
              CngKey = 0;
              NCryptFreeBuffer(ppKeyName);
              v27 = *(_QWORD *)(a3 + 136);
              ppKeyName = 0;
              v4 = NCryptEnumKeys(v27, (LPCWSTR)p_ppKeyName, &ppKeyName, &ppEnumState, 0x40u);
              if ( v34 )
              {
                ++v23;
                v34 = 0;
              }
            }
            WppTraceIndent(v26, 2);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              v12 = 146;
              LODWORD(pvPara) = 8;
              goto LABEL_12;
            }
          }
        }
        else
        {
          CngKey = 122;
        }
      }
      else
      {
        WppTraceIndent(v18, 2);
        CngKey = 8;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        }
      }
    }
  }
  else
  {
    CngKey = GetLastError();
  }
LABEL_49:
  if ( ppEnumState )
    NCryptFreeBuffer(ppEnumState);
  v29 = ppKeyName;
  if ( ppKeyName )
    NCryptFreeBuffer(ppKeyName);
  if ( p_ppKeyName )
  {
    v29 = (NCryptKeyName *)(p_ppKeyName - 1);
    if ( *((_DWORD *)p_ppKeyName - 2) == 1885431112 )
      ((void (__fastcall *)(NCryptKeyName *))g_pfnFree)(v29);
  }
  WppTraceIndent(v29, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    v30 = CngKey;
    if ( !CngKey )
      v30 = v4;
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      147,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v30);
  }
  if ( !CngKey )
    return v4;
  return CngKey;
}

```

## disassembly

```asm
0x180009c00  push    rbp
0x180009c02  push    rbx
0x180009c03  push    rsi
0x180009c04  push    rdi
0x180009c05  push    r12
0x180009c07  push    r13
0x180009c09  push    r14
0x180009c0b  push    r15
0x180009c0d  sub     rsp, 78h
0x180009c11  lea     rbp, [rsp+30h]
0x180009c16  mov     rax, cs:__security_cookie
0x180009c1d  xor     rax, rbp
0x180009c20  mov     [rbp+80h+var_48], rax
0x180009c24  xor     ebx, ebx
0x180009c26  mov     [rbp+80h+var_58], rdx
0x180009c2a  xor     edx, edx
0x180009c2c  mov     [rbp+80h+ppEnumState], rbx
0x180009c30  mov     r15d, ebx
0x180009c33  mov     [rbp+80h+ppKeyName], rbx
0x180009c37  mov     edi, ebx
0x180009c39  mov     [rbp+80h+var_80], ebx
0x180009c3c  mov     r13, r9
0x180009c3f  mov     [rbp+80h+var_50], rcx
0x180009c43  mov     r12, r8
0x180009c46  call    WppTraceIndent
0x180009c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c52  lea     rsi, WPP_GLOBAL_Control
0x180009c59  cmp     rcx, rsi
0x180009c5c  jz      short loc_180009C86
0x180009c5e  test    byte ptr [rcx+1Ch], 2
0x180009c62  jz      short loc_180009C86
0x180009c64  cmp     byte ptr [rcx+19h], 5
0x180009c68  jb      short loc_180009C86
0x180009c6a  mov     r9, cs:WPP_pszIndent
0x180009c71  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180009c78  mov     rcx, [rcx+10h]
0x180009c7c  mov     edx, 8Fh
0x180009c81  call    WPP_SF_s
0x180009c86  xor     r9d, r9d; dwFlags
0x180009c89  mov     [rsp+0B0h+pvPara], rbx; pvPara
0x180009c8e  xor     r8d, r8d; hCryptProv
0x180009c91  xor     edx, edx; dwEncodingType
0x180009c93  mov     ecx, 2; lpszStoreProvider
0x180009c98  call    cs:__imp_CertOpenStore
0x180009c9e  mov     [r12+0A8h], rax
0x180009ca6  test    rax, rax
0x180009ca9  jnz     short loc_180009CB9
0x180009cab  call    cs:__imp_GetLastError
0x180009cb1  mov     r14d, eax
0x180009cb4  jmp     loc_180009F94
0x180009cb9  mov     rcx, r12
0x180009cbc  call    I_SetupNCryptStorageProvider
0x180009cc1  mov     r14d, eax
0x180009cc4  test    eax, eax
0x180009cc6  jz      short loc_180009D1C
0x180009cc8  mov     edx, 2
0x180009ccd  call    WppTraceIndent
0x180009cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cd9  cmp     rcx, rsi
0x180009cdc  jz      loc_180009F94
0x180009ce2  test    byte ptr [rcx+1Ch], 1
0x180009ce6  jz      loc_180009F94
0x180009cec  cmp     byte ptr [rcx+19h], 2
0x180009cf0  jb      loc_180009F94
0x180009cf6  mov     edx, 90h
0x180009cfb  mov     dword ptr [rsp+0B0h+pvPara], r14d
0x180009d00  mov     r9, cs:WPP_pszIndent
0x180009d07  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180009d0e  mov     rcx, [rcx+10h]
0x180009d12  call    WPP_SF_sD
0x180009d17  jmp     loc_180009F94
0x180009d1c  mov     rcx, [r12]
0x180009d20  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009d27  mov     rax, rbx
0x180009d2a  nop     word ptr [rax+rax+00h]
0x180009d30  cmp     [rcx+rax*2+2], di
0x180009d35  lea     rax, [rax+1]
0x180009d39  jnz     short loc_180009D30
0x180009d3b  lea     rsi, ds:0Ch[rax*2]
0x180009d43  test    rsi, rsi
0x180009d46  jz      short loc_180009DA9
0x180009d48  cmp     rsi, cs:g_ulMaxStackAllocSize
0x180009d4f  ja      short loc_180009DA9
0x180009d51  mov     rcx, cs:g_ulAdditionalProbeSize
0x180009d58  add     rcx, 8
0x180009d5c  add     rcx, rsi
0x180009d5f  cmp     rcx, rsi
0x180009d62  jb      short loc_180009DA9
0x180009d64  call    VerifyStackAvailable
0x180009d69  test    eax, eax
0x180009d6b  jz      short loc_180009DA9
0x180009d6d  lea     rax, [rsi+8]
0x180009d71  lea     rcx, [rax+0Fh]
0x180009d75  cmp     rcx, rax
0x180009d78  ja      short loc_180009D84
0x180009d7a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180009d84  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009d88  mov     rax, rcx
0x180009d8b  call    _alloca_probe
0x180009d90  sub     rsp, rcx
0x180009d93  lea     rdi, [rsp+0B0h+var_80]
0x180009d98  test    rdi, rdi
0x180009d9b  jz      short loc_180009DA9
0x180009d9d  mov     dword ptr [rdi], 6B637453h
0x180009da3  add     rdi, 8
0x180009da7  jnz     short loc_180009DD0
0x180009da9  lea     rcx, [rsi+8]
0x180009dad  cmp     rcx, rsi
0x180009db0  jb      short loc_180009DD0
0x180009db2  mov     rax, cs:g_pfnAllocate
0x180009db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbe  mov     rdi, rax
0x180009dc1  test    rax, rax
0x180009dc4  jz      short loc_180009DD0
0x180009dc6  mov     dword ptr [rax], 70616548h
0x180009dcc  add     rdi, 8
0x180009dd0  test    rdi, rdi
0x180009dd3  jnz     short loc_180009E31
0x180009dd5  mov     edx, 2
0x180009dda  call    WppTraceIndent
0x180009ddf  mov     r14d, 8
0x180009de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dec  lea     rsi, WPP_GLOBAL_Control
0x180009df3  cmp     rcx, rsi
0x180009df6  jz      loc_180009F94
0x180009dfc  test    byte ptr [rcx+1Ch], 1
0x180009e00  jz      loc_180009F94
0x180009e06  cmp     byte ptr [rcx+19h], 2
0x180009e0a  jb      loc_180009F94
0x180009e10  mov     r9, cs:WPP_pszIndent
0x180009e17  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180009e1e  mov     rcx, [rcx+10h]
0x180009e22  mov     edx, 91h
0x180009e27  call    WPP_SF_s
0x180009e2c  jmp     loc_180009F94
0x180009e31  mov     r9, [r12]
0x180009e35  nop     word ptr [rax+rax+00000000h]
0x180009e40  cmp     [r9+rbx*2+2], r15w
0x180009e46  lea     rbx, [rbx+1]
0x180009e4a  jnz     short loc_180009E40
0x180009e4c  lea     rdx, [rbx+6]; cchDest
0x180009e50  mov     rcx, rdi; pszDest
0x180009e53  lea     r8, aS_0; "\\\\.\\%s\\"
0x180009e5a  call    StringCchPrintfW
0x180009e5f  test    eax, eax
0x180009e61  jns     short loc_180009E6E
0x180009e63  mov     r14d, 7Ah ; 'z'
0x180009e69  jmp     loc_180009F8D
0x180009e6e  cmp     dword ptr [r12+0Ch], 400h
0x180009e77  mov     [rbp+80h+var_70], r15d
0x180009e7b  jnz     short loc_180009E9D
0x180009e7d  lea     r8, [rbp+80h+var_60]
0x180009e81  mov     [rbp+80h+var_60], r15d
0x180009e85  lea     rdx, [rbp+80h+var_70]
0x180009e89  xor     ecx, ecx
0x180009e8b  call    cs:__imp_NgcQueryEffectiveCertPolicy
0x180009e91  test    eax, eax
0x180009e93  jns     short loc_180009E9D
0x180009e95  mov     r14d, eax
0x180009e98  jmp     loc_180009F8D
0x180009e9d  mov     rcx, [r12+88h]; hProvider
0x180009ea5  lea     r9, [rbp+80h+ppEnumState]; ppEnumState
0x180009ea9  xor     ebx, ebx
0x180009eab  mov     dword ptr [rsp+0B0h+pvPara], 40h ; '@'; dwFlags
0x180009eb3  lea     r8, [rbp+80h+ppKeyName]; ppKeyName
0x180009eb7  mov     rdx, rdi; pszScope
0x180009eba  call    cs:__imp_NCryptEnumKeys
0x180009ec0  mov     rsi, [rbp+80h+var_58]
0x180009ec4  mov     r15d, eax
0x180009ec7  test    r15d, r15d
0x180009eca  jnz     loc_180009F79
0x180009ed0  mov     ecx, [rbp+80h+var_70]
0x180009ed3  lea     rax, [rbp+80h+var_80]
0x180009ed7  mov     r8, [rbp+80h+ppKeyName]
0x180009edb  mov     r9, rsi
0x180009ede  mov     [rsp+0B0h+var_88], rax
0x180009ee3  mov     rdx, r12
0x180009ee6  mov     dword ptr [rsp+0B0h+pvPara], ecx
0x180009eea  mov     rcx, [rbp+80h+var_50]
0x180009eee  call    I_ReaderListReadCngKey
0x180009ef3  mov     r14d, eax
0x180009ef6  cmp     eax, 8
0x180009ef9  jz      short loc_180009F3E
0x180009efb  mov     rcx, [rbp+80h+ppKeyName]; pvInput
0x180009eff  xor     r14d, r14d
0x180009f02  call    cs:__imp_NCryptFreeBuffer
0x180009f08  mov     rcx, [r12+88h]; hProvider
0x180009f10  lea     r9, [rbp+80h+ppEnumState]; ppEnumState
0x180009f14  lea     r8, [rbp+80h+ppKeyName]; ppKeyName
0x180009f18  mov     [rbp+80h+ppKeyName], r14
0x180009f1c  mov     rdx, rdi; pszScope
0x180009f1f  mov     dword ptr [rsp+0B0h+pvPara], 40h ; '@'; dwFlags
0x180009f27  call    cs:__imp_NCryptEnumKeys
0x180009f2d  mov     r15d, eax
0x180009f30  cmp     [rbp+80h+var_80], r14d
0x180009f34  jz      short loc_180009EC7
0x180009f36  inc     ebx
0x180009f38  mov     [rbp+80h+var_80], r14d
0x180009f3c  jmp     short loc_180009EC7
0x180009f3e  mov     edx, 2
0x180009f43  call    WppTraceIndent
0x180009f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f4f  lea     rsi, WPP_GLOBAL_Control
0x180009f56  cmp     rcx, rsi
0x180009f59  jz      short loc_180009F94
0x180009f5b  test    byte ptr [rcx+1Ch], 1
0x180009f5f  jz      short loc_180009F94
0x180009f61  cmp     byte ptr [rcx+19h], 2
0x180009f65  jb      short loc_180009F94
0x180009f67  mov     edx, 92h
0x180009f6c  mov     dword ptr [rsp+0B0h+pvPara], 8
0x180009f74  jmp     loc_180009D00
0x180009f79  xor     eax, eax
0x180009f7b  mov     [r13+0], ebx
0x180009f7f  cmp     r15d, 8009002Ah
0x180009f86  cmovnz  eax, r15d
0x180009f8a  mov     r15d, eax
0x180009f8d  lea     rsi, WPP_GLOBAL_Control
0x180009f94  mov     rcx, [rbp+80h+ppEnumState]; pvInput
0x180009f98  test    rcx, rcx
0x180009f9b  jz      short loc_180009FA3
0x180009f9d  call    cs:__imp_NCryptFreeBuffer
0x180009fa3  mov     rcx, [rbp+80h+ppKeyName]; pvInput
0x180009fa7  test    rcx, rcx
0x180009faa  jz      short loc_180009FB2
0x180009fac  call    cs:__imp_NCryptFreeBuffer
0x180009fb2  test    rdi, rdi
0x180009fb5  jz      short loc_180009FD0
0x180009fb7  cmp     dword ptr [rdi-8], 70616548h
0x180009fbe  lea     rcx, [rdi-8]
0x180009fc2  jnz     short loc_180009FD0
0x180009fc4  mov     rax, cs:g_pfnFree
0x180009fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd0  mov     edx, 1
0x180009fd5  call    WppTraceIndent
0x180009fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fe1  cmp     rcx, rsi
0x180009fe4  jz      short loc_18000A01C
0x180009fe6  test    byte ptr [rcx+1Ch], 2
0x180009fea  jz      short loc_18000A01C
0x180009fec  cmp     byte ptr [rcx+19h], 5
0x180009ff0  jb      short loc_18000A01C
0x180009ff2  mov     r9, cs:WPP_pszIndent
0x180009ff9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000a000  mov     rcx, [rcx+10h]
0x18000a004  test    r14d, r14d
0x18000a007  mov     eax, r14d
0x18000a00a  mov     edx, 93h
0x18000a00f  cmovz   eax, r15d
0x18000a013  mov     dword ptr [rsp+0B0h+pvPara], eax
0x18000a017  call    WPP_SF_sD
0x18000a01c  test    r14d, r14d
0x18000a01f  cmovz   r14d, r15d
0x18000a023  mov     eax, r14d
0x18000a026  mov     rcx, [rbp+80h+var_48]
0x18000a02a  xor     rcx, rbp; StackCookie
0x18000a02d  call    __security_check_cookie
0x18000a032  lea     rsp, [rbp+48h]
0x18000a036  pop     r15
0x18000a038  pop     r14
0x18000a03a  pop     r13
0x18000a03c  pop     r12
0x18000a03e  pop     rdi
0x18000a03f  pop     rsi
0x18000a040  pop     rbx
0x18000a041  pop     rbp
0x18000a042  retn
```
