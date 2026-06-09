# getInnerConnectionPropertiesXml(_PEAP_CONN_PROPERTIES *,IXMLDOMNode * *,IXMLDOMDocument2 * *,ulong)

- ea: `0x180013720`
- end: `0x180013e9e`
- name: `?getInnerConnectionPropertiesXml@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument2@@K@Z`
- size: `1918`
- prototype: `unsigned int __fastcall(struct _PEAP_CONN_PROPERTIES *, struct IXMLDOMNode **, struct IXMLDOMDocument2 **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006960`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180013720`
- `0x180038270`
- `0x180038e64`
- `0x180038ee8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013c1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013c1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013c63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013c63`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013e38`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001387e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013abd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ba9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001387e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013abd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013adc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013adc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013aeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013afc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013aa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b65`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013b8f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013bdc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013b8f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180013bdc`

## string_xrefs

- `0x180013a92`: `ConfigUIPath`
- `0x180013b56`: `ConfigUIPath`
- `0x1800138ec`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x180013c59`: `RasEapCreateConnectionPropertiesXml`

## pseudocode

```c
__int64 __fastcall getInnerConnectionPropertiesXml(
        struct _PEAP_CONN_PROPERTIES *a1,
        struct IXMLDOMNode **a2,
        struct IXMLDOMDocument2 **a3,
        unsigned int a4)
{
  WCHAR *v6; // rsi
  BYTE *v7; // rdi
  WCHAR *v8; // r15
  char *v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // r13
  DWORD LastError; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  SIZE_T v17; // rbx
  WCHAR *v18; // rax
  WCHAR *v19; // r12
  unsigned __int64 v20; // rbx
  __int64 v21; // r10
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  unsigned __int64 v24; // rdx
  WCHAR *v25; // rcx
  WCHAR *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  const unsigned __int16 *v29; // r8
  __int64 v30; // rcx
  WCHAR *v31; // rax
  unsigned __int64 v32; // r9
  WCHAR *v33; // rcx
  unsigned __int64 v34; // rcx
  WCHAR *v35; // rax
  unsigned __int64 v36; // rdx
  wchar_t *v37; // rcx
  WCHAR *v38; // rax
  unsigned __int64 i; // rbx
  WCHAR *v40; // rcx
  HKEY v41; // r15
  struct _EAPTLS_CONTROL_BLOCK *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  DWORD v45; // eax
  HMODULE Library; // rax
  DWORD v47; // eax
  FARPROC ProcAddress; // r10
  int v49; // r9d
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  DWORD v53; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR *v56; // [rsp+38h] [rbp-C8h]
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v58; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v59; // [rsp+50h] [rbp-B0h]
  unsigned int v60; // [rsp+54h] [rbp-ACh]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *v62; // [rsp+60h] [rbp-A0h]
  struct IXMLDOMNode **v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  wchar_t Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  v63 = a2;
  v59 = a4;
  memset_0(Buffer, 0, sizeof(Buffer));
  v57 = 0;
  v58 = 0;
  v64 = 0;
  if ( !a1 )
    return 160;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v62 = 0;
  if ( *((_DWORD *)a1 + 2) )
  {
    v9 = (char *)a1 + 24 * *((unsigned int *)a1 + 7);
    v10 = -1;
    v11 = -1;
    do
      v12 = *(_WORD *)&v9[2 * v11++ + 34] == 0;
    while ( !v12 );
    v13 = (__int64)&v9[2 * v11 + 34];
    if ( v13 )
    {
      v60 = *(_DWORD *)(v13 + 8);
      if ( swprintf_s(Buffer, 0x100u, L"%d", v60) == -1 )
      {
        LastError = GetLastError();
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_88;
        v16 = 226;
LABEL_80:
        WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        goto LABEL_88;
      }
      hKey = 0;
      do
        v12 = Buffer[++v10] == 0;
      while ( !v12 );
      v17 = 2 * (int)v10 + 102;
      v18 = (WCHAR *)LocalAlloc(0x40u, v17);
      v19 = v18;
      if ( !v18 )
      {
        LastError = 14;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_88;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        goto LABEL_56;
      }
      v20 = v17 >> 1;
      v21 = 2147483646;
      if ( !v20 )
        goto LABEL_35;
      if ( v20 > 0x7FFFFFFF )
      {
        *v18 = 0;
        goto LABEL_47;
      }
      v22 = 2147483646;
      v23 = L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP";
      v24 = v20;
      do
      {
        if ( !v22 )
          break;
        if ( !*v23 )
          break;
        *v18++ = *v23++;
        --v22;
        --v24;
      }
      while ( v24 );
      v25 = v18 - 1;
      if ( v24 )
        v25 = v18;
      v26 = v19;
      *v25 = 0;
      v27 = v20;
      do
      {
        if ( !*v26 )
          break;
        ++v26;
        --v27;
      }
      while ( v27 );
      v28 = v20 - v27;
      if ( v27 )
      {
        v29 = L"\\";
        v30 = 2147483646;
        v31 = &v19[v28];
        v32 = v20 - v28;
        if ( v20 != v28 )
        {
          do
          {
            if ( !v30 )
              break;
            if ( !*v29 )
              break;
            *v31++ = *v29++;
            --v30;
            --v32;
          }
          while ( v32 );
        }
        v33 = v31 - 1;
        if ( v32 )
          v33 = v31;
        *v33 = 0;
        v34 = v20;
      }
      else
      {
LABEL_35:
        v34 = v20;
        if ( !v20 )
          goto LABEL_47;
      }
      v35 = v19;
      do
      {
        if ( !*v35 )
          break;
        ++v35;
        --v34;
      }
      while ( v34 );
      v36 = v20 - v34;
      if ( v34 )
      {
        v37 = Buffer;
        v38 = &v19[v36];
        for ( i = v20 - v36; i; --i )
        {
          if ( !v21 )
            break;
          if ( !*v37 )
            break;
          *v38++ = *v37++;
          --v21;
        }
        v40 = v38 - 1;
        if ( i )
          v40 = v38;
        *v40 = 0;
      }
LABEL_47:
      LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v19);
        goto LABEL_55;
      }
      v41 = hKey;
      Type = 0;
      cbData = 0;
      v56 = 0;
      LastError = RegQueryValueExW(hKey, L"ConfigUIPath", 0, &Type, 0, &cbData);
      if ( !LastError )
      {
        v7 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v7 )
        {
          LastError = RegQueryValueExW(v41, L"ConfigUIPath", 0, &Type, v7, &cbData);
          if ( !LastError )
          {
            *(_WORD *)&v7[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
            cbData = ExpandEnvironmentStringsW((LPCWSTR)v7, 0, 0);
            v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * cbData);
            if ( v6 )
            {
              *v6 = 0;
              cbData = ExpandEnvironmentStringsW((LPCWSTR)v7, v6, cbData);
              if ( cbData )
              {
                v8 = v6;
                v6 = 0;
              }
              else
              {
                v45 = GetLastError();
                v8 = v56;
                LastError = v45;
              }
            }
            else
            {
              v8 = v56;
              LastError = 14;
            }
            goto LABEL_54;
          }
        }
        else
        {
          LastError = 14;
        }
      }
      v8 = 0;
LABEL_54:
      LocalFree(v7);
      LocalFree(v6);
      RegCloseKey(hKey);
      v7 = v62;
      v6 = (WCHAR *)v62;
LABEL_55:
      LocalFree(v19);
      if ( LastError )
      {
LABEL_56:
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_88;
        v43 = 227;
        v44 = LastError;
        goto LABEL_87;
      }
      Library = LoadLibraryExW(v8, 0, 0);
      v6 = (WCHAR *)Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "RasEapCreateConnectionPropertiesXml");
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v8);
          goto LABEL_88;
        }
        v49 = *(_DWORD *)(v13 + 4);
        v50 = v59;
        v51 = v13 + 12;
        v12 = v49 == 15;
        v52 = (unsigned int)(v49 - 15);
        if ( v12 )
          v51 = 0;
        LODWORD(v50) = v59 | 0x100;
        v53 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int64 *))ProcAddress)(
                v60,
                v50,
                v51,
                v52,
                &v57);
        LastError = v53;
        if ( !v53 )
        {
          if ( v57 )
          {
            if ( (*(unsigned int (__fastcall **)(__int64, BYTE **))(*(_QWORD *)v57 + 360LL))(v57, &v58) )
            {
              LastError = 1465;
              goto LABEL_88;
            }
            v7 = v58;
            if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BYTE *, __int64 *))(*v63)->lpVtbl->appendChild)(
                   *v63,
                   v58,
                   &v64) )
            {
              LastError = 1465;
              goto LABEL_88;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
LABEL_90:
              if ( v58 )
              {
                (*(void (__fastcall **)(BYTE *))(*(_QWORD *)v58 + 16LL))(v58);
                v58 = 0;
              }
              if ( v7 )
                (*(void (__fastcall **)(BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
              if ( v6 )
                FreeLibrary((HMODULE)v6);
              if ( v8 )
                LocalFree(v8);
              return LastError;
            }
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_88;
          v16 = 232;
          goto LABEL_80;
        }
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_88;
        v43 = 230;
        v44 = v53;
      }
      else
      {
        v47 = GetLastError();
        LastError = v47;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_88;
        v43 = 228;
        v44 = v47;
      }
LABEL_87:
      WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v44);
LABEL_88:
      if ( v57 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        v57 = 0;
      }
      goto LABEL_90;
    }
  }
  v42 = WPP_GLOBAL_Control;
  LastError = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v43 = 225;
    v44 = 0;
    goto LABEL_87;
  }
  return LastError;
}

```

## disassembly

```asm
0x180013720  push    rbp
0x180013722  push    rbx
0x180013723  push    r14
0x180013725  lea     rbp, [rsp-1B0h]
0x18001372d  sub     rsp, 2B0h
0x180013734  mov     rax, cs:__security_cookie
0x18001373b  xor     rax, rsp
0x18001373e  mov     [rbp+1C0h+var_40], rax
0x180013745  mov     [rsp+2C0h+var_250], rdx
0x18001374a  mov     rbx, rcx
0x18001374d  xor     edx, edx; Val
0x18001374f  mov     [rsp+2C0h+var_270], r9d
0x180013754  lea     rcx, [rbp+1C0h+Buffer]; void *
0x180013758  mov     r8d, 200h; Size
0x18001375e  call    memset_0
0x180013763  xor     r14d, r14d
0x180013766  mov     [rsp+2C0h+var_280], r14
0x18001376b  mov     [rsp+2C0h+var_278], r14
0x180013770  mov     [rsp+2C0h+var_248], r14
0x180013775  test    rbx, rbx
0x180013778  jnz     short loc_180013784
0x18001377a  mov     eax, 0A0h
0x18001377f  jmp     loc_180013E82
0x180013784  mov     [rsp+2C0h+arg_10], rsi
0x18001378c  mov     rsi, r14
0x18001378f  mov     [rsp+2C0h+var_18], rdi
0x180013797  mov     rdi, r14
0x18001379a  mov     [rsp+2C0h+var_20], r12
0x1800137a2  mov     [rsp+2C0h+var_28], r13
0x1800137aa  mov     [rsp+2C0h+var_30], r15
0x1800137b2  mov     r15, r14
0x1800137b5  mov     [rsp+2C0h+var_260], r14
0x1800137ba  cmp     [rbx+8], r14d
0x1800137be  jz      loc_180013DAC
0x1800137c4  mov     eax, [rbx+1Ch]
0x1800137c7  lea     rcx, [rax+rax*2]
0x1800137cb  lea     rdx, [rbx+rcx*8]
0x1800137cf  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800137d6  mov     rax, rbx
0x1800137d9  nop     dword ptr [rax+00000000h]
0x1800137e0  cmp     [rdx+rax*2+22h], r14w
0x1800137e6  lea     rax, [rax+1]
0x1800137ea  jnz     short loc_1800137E0
0x1800137ec  lea     r13, [rdx+22h]
0x1800137f0  lea     r13, [r13+rax*2+0]
0x1800137f5  test    r13, r13
0x1800137f8  jz      loc_180013DAC
0x1800137fe  mov     eax, [r13+8]
0x180013802  lea     r8, aD; "%d"
0x180013809  mov     r9d, eax
0x18001380c  mov     [rsp+2C0h+var_26C], eax
0x180013810  mov     edx, 100h; BufferCount
0x180013815  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x180013819  call    swprintf_s
0x18001381e  cmp     eax, ebx
0x180013820  jnz     short loc_180013851
0x180013822  call    cs:__imp_GetLastError
0x180013829  nop     dword ptr [rax+rax+00h]
0x18001382e  mov     ebx, eax
0x180013830  mov     rcx, cs:WPP_GLOBAL_Control
0x180013837  lea     r14, WPP_GLOBAL_Control
0x18001383e  cmp     rcx, r14
0x180013841  jz      loc_180013DDE
0x180013847  mov     edx, 0E2h
0x18001384c  jmp     loc_180013D49
0x180013851  mov     [rsp+2C0h+hKey], r14
0x180013856  lea     rax, [rbp+1C0h+Buffer]
0x18001385a  nop     word ptr [rax+rax+00h]
0x180013860  cmp     [rax+rbx*2+2], r14w
0x180013866  lea     rbx, [rbx+1]
0x18001386a  jnz     short loc_180013860
0x18001386c  lea     eax, ds:66h[rbx*2]
0x180013873  mov     ecx, 40h ; '@'; uFlags
0x180013878  movsxd  rbx, eax
0x18001387b  mov     rdx, rbx; uBytes
0x18001387e  call    cs:__imp_LocalAlloc
0x180013885  nop     dword ptr [rax+rax+00h]
0x18001388a  mov     r12, rax
0x18001388d  test    rax, rax
0x180013890  jnz     short loc_1800138C8
0x180013892  mov     ebx, 0Eh
0x180013897  mov     rcx, cs:WPP_GLOBAL_Control
0x18001389e  lea     r14, WPP_GLOBAL_Control
0x1800138a5  cmp     rcx, r14
0x1800138a8  jz      loc_180013DDE
0x1800138ae  mov     rcx, [rcx+10h]
0x1800138b2  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800138b9  mov     edx, 0F8h
0x1800138be  call    WPP_SF_
0x1800138c3  jmp     loc_180013B27
0x1800138c8  shr     rbx, 1
0x1800138cb  mov     r10d, 7FFFFFFEh
0x1800138d1  jz      loc_18001399A
0x1800138d7  cmp     rbx, 7FFFFFFFh
0x1800138de  jbe     short loc_1800138E9
0x1800138e0  mov     [rax], r14w
0x1800138e4  jmp     loc_180013A0C
0x1800138e9  mov     rcx, r10
0x1800138ec  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x1800138f3  mov     rdx, rbx
0x1800138f6  test    rcx, rcx
0x1800138f9  jz      short loc_18001391A
0x1800138fb  movzx   r9d, word ptr [r8]
0x1800138ff  test    r9w, r9w
0x180013903  jz      short loc_18001391A
0x180013905  mov     [rax], r9w
0x180013909  add     r8, 2
0x18001390d  add     rax, 2
0x180013911  dec     rcx
0x180013914  sub     rdx, 1
0x180013918  jnz     short loc_1800138F6
0x18001391a  lea     rcx, [rax-2]
0x18001391e  test    rdx, rdx
0x180013921  mov     r9, rbx
0x180013924  cmovnz  rcx, rax
0x180013928  mov     rax, r12
0x18001392b  mov     [rcx], r14w
0x18001392f  mov     rcx, rbx
0x180013932  cmp     [rax], r14w
0x180013936  jz      short loc_180013942
0x180013938  add     rax, 2
0x18001393c  sub     rcx, 1
0x180013940  jnz     short loc_180013932
0x180013942  mov     rdx, r9
0x180013945  sub     rdx, rcx
0x180013948  test    rcx, rcx
0x18001394b  cmovz   rdx, r14
0x18001394f  jz      short loc_18001399A
0x180013951  lea     r8, asc_180087834; "\\"
0x180013958  mov     rcx, r10
0x18001395b  lea     rax, [r12+rdx*2]
0x18001395f  sub     r9, rdx
0x180013962  jz      short loc_180013986
0x180013964  test    rcx, rcx
0x180013967  jz      short loc_180013986
0x180013969  movzx   edx, word ptr [r8]
0x18001396d  test    dx, dx
0x180013970  jz      short loc_180013986
0x180013972  mov     [rax], dx
0x180013975  add     r8, 2
0x180013979  add     rax, 2
0x18001397d  dec     rcx
0x180013980  sub     r9, 1
0x180013984  jnz     short loc_180013964
0x180013986  test    r9, r9
0x180013989  lea     rcx, [rax-2]
0x18001398d  cmovnz  rcx, rax
0x180013991  mov     [rcx], r14w
0x180013995  mov     rcx, rbx
0x180013998  jmp     short loc_1800139AB
0x18001399a  mov     rcx, rbx
0x18001399d  test    rbx, rbx
0x1800139a0  jz      short loc_180013A0C
0x1800139a2  cmp     rbx, 7FFFFFFFh
0x1800139a9  ja      short loc_180013A0C
0x1800139ab  mov     rax, r12
0x1800139ae  xchg    ax, ax
0x1800139b0  cmp     [rax], r14w
0x1800139b4  jz      short loc_1800139C0
0x1800139b6  add     rax, 2
0x1800139ba  sub     rcx, 1
0x1800139be  jnz     short loc_1800139B0
0x1800139c0  mov     rdx, rbx
0x1800139c3  sub     rdx, rcx
0x1800139c6  test    rcx, rcx
0x1800139c9  cmovz   rdx, r14
0x1800139cd  jz      short loc_180013A0C
0x1800139cf  lea     rcx, [rbp+1C0h+Buffer]
0x1800139d3  lea     rax, [r12+rdx*2]
0x1800139d7  sub     rbx, rdx
0x1800139da  jz      short loc_1800139FD
0x1800139dc  test    r10, r10
0x1800139df  jz      short loc_1800139FD
0x1800139e1  movzx   edx, word ptr [rcx]
0x1800139e4  test    dx, dx
0x1800139e7  jz      short loc_1800139FD
0x1800139e9  mov     [rax], dx
0x1800139ec  add     rcx, 2
0x1800139f0  add     rax, 2
0x1800139f4  dec     r10
0x1800139f7  sub     rbx, 1
0x1800139fb  jnz     short loc_1800139DC
0x1800139fd  test    rbx, rbx
0x180013a00  lea     rcx, [rax-2]
0x180013a04  cmovnz  rcx, rax
0x180013a08  mov     [rcx], r14w
0x180013a0c  lea     rax, [rsp+2C0h+hKey]
0x180013a11  mov     r9d, 20019h; samDesired
0x180013a17  xor     r8d, r8d; ulOptions
0x180013a1a  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180013a1f  mov     rdx, r12; lpSubKey
0x180013a22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013a29  call    cs:__imp_RegOpenKeyExW
0x180013a30  nop     dword ptr [rax+rax+00h]
0x180013a35  lea     r14, WPP_GLOBAL_Control
0x180013a3c  mov     ebx, eax
0x180013a3e  test    eax, eax
0x180013a40  jz      short loc_180013A6F
0x180013a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a49  cmp     rcx, r14
0x180013a4c  jz      loc_180013B10
0x180013a52  mov     rcx, [rcx+10h]
0x180013a56  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180013a5d  mov     edx, 0F9h
0x180013a62  mov     r9, r12
0x180013a65  call    WPP_SF_S
0x180013a6a  jmp     loc_180013B10
0x180013a6f  mov     r15, [rsp+2C0h+hKey]
0x180013a74  lea     rax, [rsp+2C0h+cbData]
0x180013a79  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180013a7e  lea     r9, [rsp+2C0h+Type]; lpType
0x180013a83  mov     rcx, r15; hKey
0x180013a86  mov     [rsp+2C0h+phkResult], rdi; lpData
0x180013a8b  xor     r8d, r8d; lpReserved
0x180013a8e  mov     [rsp+2C0h+Type], edi
0x180013a92  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180013a99  mov     [rsp+2C0h+cbData], edi
0x180013a9d  mov     [rsp+2C0h+var_288], rdi
0x180013aa2  call    cs:__imp_RegQueryValueExW
0x180013aa9  nop     dword ptr [rax+rax+00h]
0x180013aae  mov     ebx, eax
0x180013ab0  test    eax, eax
0x180013ab2  jnz     short loc_180013AD6
0x180013ab4  mov     edx, [rsp+2C0h+cbData]; uBytes
0x180013ab8  mov     ecx, 40h ; '@'; uFlags
0x180013abd  call    cs:__imp_LocalAlloc
0x180013ac4  nop     dword ptr [rax+rax+00h]
0x180013ac9  mov     rdi, rax
0x180013acc  test    rax, rax
0x180013acf  jnz     short loc_180013B44
0x180013ad1  mov     ebx, 0Eh
0x180013ad6  mov     r15, rsi
0x180013ad9  mov     rcx, rdi; hMem
0x180013adc  call    cs:__imp_LocalFree
0x180013ae3  nop     dword ptr [rax+rax+00h]
0x180013ae8  mov     rcx, rsi; hMem
0x180013aeb  call    cs:__imp_LocalFree
0x180013af2  nop     dword ptr [rax+rax+00h]
0x180013af7  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180013afc  call    cs:__imp_RegCloseKey
0x180013b03  nop     dword ptr [rax+rax+00h]
0x180013b08  mov     rdi, [rsp+2C0h+var_260]
0x180013b0d  mov     rsi, rdi
0x180013b10  mov     rcx, r12; hMem
0x180013b13  call    cs:__imp_LocalFree
0x180013b1a  nop     dword ptr [rax+rax+00h]
0x180013b1f  test    ebx, ebx
0x180013b21  jz      loc_180013C12
0x180013b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b2e  cmp     rcx, r14
0x180013b31  jz      loc_180013DDE
0x180013b37  mov     edx, 0E3h
0x180013b3c  mov     r9d, ebx
0x180013b3f  jmp     loc_180013DCE
0x180013b44  lea     rax, [rsp+2C0h+cbData]
0x180013b49  xor     r8d, r8d; lpReserved
0x180013b4c  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180013b51  lea     r9, [rsp+2C0h+Type]; lpType
0x180013b56  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180013b5d  mov     [rsp+2C0h+phkResult], rdi; lpData
0x180013b62  mov     rcx, r15; hKey
0x180013b65  call    cs:__imp_RegQueryValueExW
0x180013b6c  nop     dword ptr [rax+rax+00h]
0x180013b71  mov     ebx, eax
0x180013b73  test    eax, eax
0x180013b75  jnz     loc_180013AD6
0x180013b7b  mov     edx, [rsp+2C0h+cbData]
0x180013b7f  xor     r8d, r8d; nSize
0x180013b82  shr     rdx, 1
0x180013b85  mov     rcx, rdi; lpSrc
0x180013b88  mov     [rdi+rdx*2-2], ax
0x180013b8d  xor     edx, edx; lpDst
0x180013b8f  call    cs:__imp_ExpandEnvironmentStringsW
0x180013b96  nop     dword ptr [rax+rax+00h]
0x180013b9b  mov     edx, eax
0x180013b9d  mov     ecx, 40h ; '@'; uFlags
0x180013ba2  mov     [rsp+2C0h+cbData], edx
0x180013ba6  add     rdx, rdx; uBytes
0x180013ba9  call    cs:__imp_LocalAlloc
0x180013bb0  nop     dword ptr [rax+rax+00h]
0x180013bb5  mov     rsi, rax
0x180013bb8  test    rax, rax
0x180013bbb  jnz     short loc_180013BCC
0x180013bbd  mov     r15, [rsp+2C0h+var_288]
0x180013bc2  mov     ebx, 0Eh
0x180013bc7  jmp     loc_180013AD9
0x180013bcc  xor     eax, eax
0x180013bce  mov     rdx, rsi; lpDst
0x180013bd1  mov     [rsi], ax
0x180013bd4  mov     rcx, rdi; lpSrc
0x180013bd7  mov     r8d, [rsp+2C0h+cbData]; nSize
0x180013bdc  call    cs:__imp_ExpandEnvironmentStringsW
0x180013be3  nop     dword ptr [rax+rax+00h]
0x180013be8  mov     [rsp+2C0h+cbData], eax
0x180013bec  test    eax, eax
0x180013bee  jnz     short loc_180013C08
0x180013bf0  call    cs:__imp_GetLastError
0x180013bf7  nop     dword ptr [rax+rax+00h]
0x180013bfc  mov     r15, [rsp+2C0h+var_288]
0x180013c01  mov     ebx, eax
  ... truncated ...
```
