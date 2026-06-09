# getInnerConnectionPropertiesXml(_PEAP_CONN_PROPERTIES *,IXMLDOMNode * *,IXMLDOMDocument2 * *,ulong)

- ea: `0x1800124c0`
- end: `0x180012bc1`
- name: `?getInnerConnectionPropertiesXml@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAUIXMLDOMNode@@PEAPEAUIXMLDOMDocument2@@K@Z`
- size: `1793`
- prototype: `unsigned int __fastcall(struct _PEAP_CONN_PROPERTIES *, struct IXMLDOMNode **, struct IXMLDOMDocument2 **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180006400`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x1800124c0`
- `0x180035680`
- `0x180036254`
- `0x1800362d8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012962`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001299f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001299f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012b68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001293e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001293e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012612`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012841`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012903`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012612`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012841`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001285a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001287f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001285a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012863`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001287f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001286e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001286e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800127b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800127b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001282c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800128cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001282c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800128cb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800128ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012930`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800128ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012930`

## string_xrefs

- `0x18001281c`: `ConfigUIPath`
- `0x1800128bc`: `ConfigUIPath`
- `0x18001267a`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x180012995`: `RasEapCreateConnectionPropertiesXml`

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
0x1800124c0  push    rbp
0x1800124c2  push    rbx
0x1800124c3  push    r14
0x1800124c5  lea     rbp, [rsp-1B0h]
0x1800124cd  sub     rsp, 2B0h
0x1800124d4  mov     rax, cs:__security_cookie
0x1800124db  xor     rax, rsp
0x1800124de  mov     [rbp+1C0h+var_40], rax
0x1800124e5  mov     [rsp+2C0h+var_250], rdx
0x1800124ea  mov     rbx, rcx
0x1800124ed  xor     edx, edx; Val
0x1800124ef  mov     [rsp+2C0h+var_270], r9d
0x1800124f4  lea     rcx, [rbp+1C0h+Buffer]; void *
0x1800124f8  mov     r8d, 200h; Size
0x1800124fe  call    memset_0
0x180012503  xor     r14d, r14d
0x180012506  mov     [rsp+2C0h+var_280], r14
0x18001250b  mov     [rsp+2C0h+var_278], r14
0x180012510  mov     [rsp+2C0h+var_248], r14
0x180012515  test    rbx, rbx
0x180012518  jnz     short loc_180012524
0x18001251a  mov     eax, 0A0h
0x18001251f  jmp     loc_180012BA6
0x180012524  mov     [rsp+2C0h+arg_10], rsi
0x18001252c  mov     rsi, r14
0x18001252f  mov     [rsp+2C0h+var_18], rdi
0x180012537  mov     rdi, r14
0x18001253a  mov     [rsp+2C0h+var_20], r12
0x180012542  mov     [rsp+2C0h+var_28], r13
0x18001254a  mov     [rsp+2C0h+var_30], r15
0x180012552  mov     r15, r14
0x180012555  mov     [rsp+2C0h+var_260], r14
0x18001255a  cmp     [rbx+8], r14d
0x18001255e  jz      loc_180012ADC
0x180012564  mov     eax, [rbx+1Ch]
0x180012567  lea     rcx, [rax+rax*2]
0x18001256b  lea     rdx, [rbx+rcx*8]
0x18001256f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180012576  mov     rax, rbx
0x180012579  nop     dword ptr [rax+00000000h]
0x180012580  cmp     [rdx+rax*2+22h], r14w
0x180012586  lea     rax, [rax+1]
0x18001258a  jnz     short loc_180012580
0x18001258c  lea     r13, [rdx+22h]
0x180012590  lea     r13, [r13+rax*2+0]
0x180012595  test    r13, r13
0x180012598  jz      loc_180012ADC
0x18001259e  mov     eax, [r13+8]
0x1800125a2  lea     r8, aD; "%d"
0x1800125a9  mov     r9d, eax
0x1800125ac  mov     [rsp+2C0h+var_26C], eax
0x1800125b0  mov     edx, 100h; BufferCount
0x1800125b5  lea     rcx, [rbp+1C0h+Buffer]; Buffer
0x1800125b9  call    swprintf_s
0x1800125be  cmp     eax, ebx
0x1800125c0  jnz     short loc_1800125EB
0x1800125c2  call    cs:__imp_GetLastError
0x1800125c8  mov     ebx, eax
0x1800125ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125d1  lea     r14, WPP_GLOBAL_Control
0x1800125d8  cmp     rcx, r14
0x1800125db  jz      loc_180012B0E
0x1800125e1  mov     edx, 0E2h
0x1800125e6  jmp     loc_180012A79
0x1800125eb  mov     [rsp+2C0h+hKey], r14
0x1800125f0  lea     rax, [rbp+1C0h+Buffer]
0x1800125f4  cmp     [rax+rbx*2+2], r14w
0x1800125fa  lea     rbx, [rbx+1]
0x1800125fe  jnz     short loc_1800125F4
0x180012600  lea     eax, ds:66h[rbx*2]
0x180012607  mov     ecx, 40h ; '@'; uFlags
0x18001260c  movsxd  rbx, eax
0x18001260f  mov     rdx, rbx; uBytes
0x180012612  call    cs:__imp_LocalAlloc
0x180012618  mov     r12, rax
0x18001261b  test    rax, rax
0x18001261e  jnz     short loc_180012656
0x180012620  mov     ebx, 0Eh
0x180012625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001262c  lea     r14, WPP_GLOBAL_Control
0x180012633  cmp     rcx, r14
0x180012636  jz      loc_180012B0E
0x18001263c  mov     rcx, [rcx+10h]
0x180012640  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180012647  mov     edx, 0F8h
0x18001264c  call    WPP_SF_
0x180012651  jmp     loc_18001288D
0x180012656  shr     rbx, 1
0x180012659  mov     r10d, 7FFFFFFEh
0x18001265f  jz      loc_180012728
0x180012665  cmp     rbx, 7FFFFFFFh
0x18001266c  jbe     short loc_180012677
0x18001266e  mov     [rax], r14w
0x180012672  jmp     loc_18001279C
0x180012677  mov     rcx, r10
0x18001267a  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x180012681  mov     rdx, rbx
0x180012684  test    rcx, rcx
0x180012687  jz      short loc_1800126A8
0x180012689  movzx   r9d, word ptr [r8]
0x18001268d  test    r9w, r9w
0x180012691  jz      short loc_1800126A8
0x180012693  mov     [rax], r9w
0x180012697  add     r8, 2
0x18001269b  add     rax, 2
0x18001269f  dec     rcx
0x1800126a2  sub     rdx, 1
0x1800126a6  jnz     short loc_180012684
0x1800126a8  lea     rcx, [rax-2]
0x1800126ac  test    rdx, rdx
0x1800126af  mov     r9, rbx
0x1800126b2  cmovnz  rcx, rax
0x1800126b6  mov     rax, r12
0x1800126b9  mov     [rcx], r14w
0x1800126bd  mov     rcx, rbx
0x1800126c0  cmp     [rax], r14w
0x1800126c4  jz      short loc_1800126D0
0x1800126c6  add     rax, 2
0x1800126ca  sub     rcx, 1
0x1800126ce  jnz     short loc_1800126C0
0x1800126d0  mov     rdx, r9
0x1800126d3  sub     rdx, rcx
0x1800126d6  test    rcx, rcx
0x1800126d9  cmovz   rdx, r14
0x1800126dd  jz      short loc_180012728
0x1800126df  lea     r8, asc_180081834; "\\"
0x1800126e6  mov     rcx, r10
0x1800126e9  lea     rax, [r12+rdx*2]
0x1800126ed  sub     r9, rdx
0x1800126f0  jz      short loc_180012714
0x1800126f2  test    rcx, rcx
0x1800126f5  jz      short loc_180012714
0x1800126f7  movzx   edx, word ptr [r8]
0x1800126fb  test    dx, dx
0x1800126fe  jz      short loc_180012714
0x180012700  mov     [rax], dx
0x180012703  add     r8, 2
0x180012707  add     rax, 2
0x18001270b  dec     rcx
0x18001270e  sub     r9, 1
0x180012712  jnz     short loc_1800126F2
0x180012714  test    r9, r9
0x180012717  lea     rcx, [rax-2]
0x18001271b  cmovnz  rcx, rax
0x18001271f  mov     [rcx], r14w
0x180012723  mov     rcx, rbx
0x180012726  jmp     short loc_180012739
0x180012728  mov     rcx, rbx
0x18001272b  test    rbx, rbx
0x18001272e  jz      short loc_18001279C
0x180012730  cmp     rbx, 7FFFFFFFh
0x180012737  ja      short loc_18001279C
0x180012739  mov     rax, r12
0x18001273c  nop     dword ptr [rax+00h]
0x180012740  cmp     [rax], r14w
0x180012744  jz      short loc_180012750
0x180012746  add     rax, 2
0x18001274a  sub     rcx, 1
0x18001274e  jnz     short loc_180012740
0x180012750  mov     rdx, rbx
0x180012753  sub     rdx, rcx
0x180012756  test    rcx, rcx
0x180012759  cmovz   rdx, r14
0x18001275d  jz      short loc_18001279C
0x18001275f  lea     rcx, [rbp+1C0h+Buffer]
0x180012763  lea     rax, [r12+rdx*2]
0x180012767  sub     rbx, rdx
0x18001276a  jz      short loc_18001278D
0x18001276c  test    r10, r10
0x18001276f  jz      short loc_18001278D
0x180012771  movzx   edx, word ptr [rcx]
0x180012774  test    dx, dx
0x180012777  jz      short loc_18001278D
0x180012779  mov     [rax], dx
0x18001277c  add     rcx, 2
0x180012780  add     rax, 2
0x180012784  dec     r10
0x180012787  sub     rbx, 1
0x18001278b  jnz     short loc_18001276C
0x18001278d  test    rbx, rbx
0x180012790  lea     rcx, [rax-2]
0x180012794  cmovnz  rcx, rax
0x180012798  mov     [rcx], r14w
0x18001279c  lea     rax, [rsp+2C0h+hKey]
0x1800127a1  mov     r9d, 20019h; samDesired
0x1800127a7  xor     r8d, r8d; ulOptions
0x1800127aa  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800127af  mov     rdx, r12; lpSubKey
0x1800127b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800127b9  call    cs:__imp_RegOpenKeyExW
0x1800127bf  lea     r14, WPP_GLOBAL_Control
0x1800127c6  mov     ebx, eax
0x1800127c8  test    eax, eax
0x1800127ca  jz      short loc_1800127F9
0x1800127cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127d3  cmp     rcx, r14
0x1800127d6  jz      loc_18001287C
0x1800127dc  mov     rcx, [rcx+10h]
0x1800127e0  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800127e7  mov     edx, 0F9h
0x1800127ec  mov     r9, r12
0x1800127ef  call    WPP_SF_S
0x1800127f4  jmp     loc_18001287C
0x1800127f9  mov     r15, [rsp+2C0h+hKey]
0x1800127fe  lea     rax, [rsp+2C0h+cbData]
0x180012803  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180012808  lea     r9, [rsp+2C0h+Type]; lpType
0x18001280d  mov     rcx, r15; hKey
0x180012810  mov     [rsp+2C0h+phkResult], rdi; lpData
0x180012815  xor     r8d, r8d; lpReserved
0x180012818  mov     [rsp+2C0h+Type], edi
0x18001281c  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180012823  mov     [rsp+2C0h+cbData], edi
0x180012827  mov     [rsp+2C0h+var_288], rdi
0x18001282c  call    cs:__imp_RegQueryValueExW
0x180012832  mov     ebx, eax
0x180012834  test    eax, eax
0x180012836  jnz     short loc_180012854
0x180012838  mov     edx, [rsp+2C0h+cbData]; uBytes
0x18001283c  mov     ecx, 40h ; '@'; uFlags
0x180012841  call    cs:__imp_LocalAlloc
0x180012847  mov     rdi, rax
0x18001284a  test    rax, rax
0x18001284d  jnz     short loc_1800128AA
0x18001284f  mov     ebx, 0Eh
0x180012854  mov     r15, rsi
0x180012857  mov     rcx, rdi; hMem
0x18001285a  call    cs:__imp_LocalFree
0x180012860  mov     rcx, rsi; hMem
0x180012863  call    cs:__imp_LocalFree
0x180012869  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001286e  call    cs:__imp_RegCloseKey
0x180012874  mov     rdi, [rsp+2C0h+var_260]
0x180012879  mov     rsi, rdi
0x18001287c  mov     rcx, r12; hMem
0x18001287f  call    cs:__imp_LocalFree
0x180012885  test    ebx, ebx
0x180012887  jz      loc_18001295A
0x18001288d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012894  cmp     rcx, r14
0x180012897  jz      loc_180012B0E
0x18001289d  mov     edx, 0E3h
0x1800128a2  mov     r9d, ebx
0x1800128a5  jmp     loc_180012AFE
0x1800128aa  lea     rax, [rsp+2C0h+cbData]
0x1800128af  xor     r8d, r8d; lpReserved
0x1800128b2  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1800128b7  lea     r9, [rsp+2C0h+Type]; lpType
0x1800128bc  lea     rdx, aConfiguipath; "ConfigUIPath"
0x1800128c3  mov     [rsp+2C0h+phkResult], rdi; lpData
0x1800128c8  mov     rcx, r15; hKey
0x1800128cb  call    cs:__imp_RegQueryValueExW
0x1800128d1  mov     ebx, eax
0x1800128d3  test    eax, eax
0x1800128d5  jnz     loc_180012854
0x1800128db  mov     edx, [rsp+2C0h+cbData]
0x1800128df  xor     r8d, r8d; nSize
0x1800128e2  shr     rdx, 1
0x1800128e5  mov     rcx, rdi; lpSrc
0x1800128e8  mov     [rdi+rdx*2-2], ax
0x1800128ed  xor     edx, edx; lpDst
0x1800128ef  call    cs:__imp_ExpandEnvironmentStringsW
0x1800128f5  mov     edx, eax
0x1800128f7  mov     ecx, 40h ; '@'; uFlags
0x1800128fc  mov     [rsp+2C0h+cbData], edx
0x180012900  add     rdx, rdx; uBytes
0x180012903  call    cs:__imp_LocalAlloc
0x180012909  mov     rsi, rax
0x18001290c  test    rax, rax
0x18001290f  jnz     short loc_180012920
0x180012911  mov     r15, [rsp+2C0h+var_288]
0x180012916  mov     ebx, 0Eh
0x18001291b  jmp     loc_180012857
0x180012920  xor     eax, eax
0x180012922  mov     rdx, rsi; lpDst
0x180012925  mov     [rsi], ax
0x180012928  mov     rcx, rdi; lpSrc
0x18001292b  mov     r8d, [rsp+2C0h+cbData]; nSize
0x180012930  call    cs:__imp_ExpandEnvironmentStringsW
0x180012936  mov     [rsp+2C0h+cbData], eax
0x18001293a  test    eax, eax
0x18001293c  jnz     short loc_180012950
0x18001293e  call    cs:__imp_GetLastError
0x180012944  mov     r15, [rsp+2C0h+var_288]
0x180012949  mov     ebx, eax
0x18001294b  jmp     loc_180012857
0x180012950  mov     r15, rsi
0x180012953  xor     esi, esi
0x180012955  jmp     loc_180012857
0x18001295a  xor     r8d, r8d; dwFlags
0x18001295d  xor     edx, edx; hFile
0x18001295f  mov     rcx, r15; lpLibFileName
0x180012962  call    cs:__imp_LoadLibraryExW
0x180012968  mov     rsi, rax
0x18001296b  test    rax, rax
0x18001296e  jnz     short loc_180012995
0x180012970  call    cs:__imp_GetLastError
0x180012976  mov     ebx, eax
0x180012978  mov     rcx, cs:WPP_GLOBAL_Control
0x18001297f  cmp     rcx, r14
  ... truncated ...
```
