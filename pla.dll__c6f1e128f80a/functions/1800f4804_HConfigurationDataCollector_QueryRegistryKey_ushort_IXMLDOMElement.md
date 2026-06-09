# HConfigurationDataCollector::QueryRegistryKey(ushort *,IXMLDOMElement *)

- ea: `0x1800f4804`
- end: `0x1800f502d`
- name: `?QueryRegistryKey@HConfigurationDataCollector@@AEAAJPEAGPEAUIXMLDOMElement@@@Z`
- size: `2089`
- prototype: `int(HConfigurationDataCollector *__hidden this, unsigned __int16 *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800ab454`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x1800198b0`
- `0x18001e000`
- `0x18001e8e4`
- `0x18001ef94`
- `0x18002b3a0`
- `0x180039e30`
- `0x18003f23c`
- `0x180056190`
- `0x1800f4804`
- `0x180114a94`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f4e57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f4e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f4ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f5004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f4ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f5004`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800f4c6b`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800f4c6b`

## string_xrefs

- `0x1800f4f90`: `HConfigurationDataCollector::QueryRegistryKey`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::QueryRegistryKey(
        HConfigurationDataCollector *this,
        unsigned __int16 *a2,
        struct IXMLDOMElement *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  void *p_hKey; // rcx
  void *v9; // r9
  __int64 v10; // rax
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rax
  const WCHAR *v14; // rdi
  wchar_t *v15; // rsi
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int IsLocalServer; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rax
  LSTATUS v25; // eax
  int v26; // eax
  __int64 v27; // rax
  HKEY v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  LSTATUS v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v39; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  HKEY v44; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Buffer[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpMachineName[2]; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpValueName[2]; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v52[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v53[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v54[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v55[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v56[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v57[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v58[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v59[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v60[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v61[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v62[64]; // [rsp+600h] [rbp+500h] BYREF

  v41 = 0;
  hKey = 0;
  v48 = 0;
  phkResult = 0;
  v44 = 0;
  *(_OWORD *)Buffer = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  *(_OWORD *)lpMachineName = 0;
  *(_OWORD *)lpSubKey = 0;
  *(_OWORD *)lpValueName = 0;
  v5 = ParsePath(a2, (struct _QUERY_PATH *)lpMachineName);
  v6 = v5;
  if ( v5 >= 0 )
  {
    Buffer[0] = (wchar_t *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v39);
    if ( !Buffer[0] )
    {
      v6 = -2147024882;
      v41 = -2147024882;
      LODWORD(hKey) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_89;
      }
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v53[v10] );
      goto LABEL_87;
    }
    v11 = *((_DWORD *)this + 57);
    v12 = 50;
    *((_QWORD *)&v47 + 1) = a3;
    *(_QWORD *)&v47 = *((_QWORD *)this + 32);
    v13 = *((_QWORD *)this + 9);
    if ( (unsigned int)(v11 - 1) <= 0x31 )
      v12 = v11;
    v14 = lpSubKey[1];
    LODWORD(v46[1]) = v12;
    v46[0] = 1024;
    v48 = *(_QWORD *)(*(_QWORD *)(v13 + 56) + 16LL);
    if ( lpSubKey[1] && *lpSubKey[1] )
    {
      v15 = (wchar_t *)lpSubKey[0];
      v16 = StringCchPrintfExW(Buffer[0], 0x400u, &Buffer[1], v46, 0, L"%s\\%s", lpSubKey[0], lpSubKey[1]);
      v6 = v16;
      if ( v16 < 0 )
      {
        LODWORD(hKey) = 0;
        v41 = v16;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v54, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v54[v17] );
        goto LABEL_87;
      }
    }
    else
    {
      v15 = (wchar_t *)lpSubKey[0];
      v18 = StringCchCopyExW(Buffer[0], 0x400u, lpSubKey[0], &Buffer[1], v46, v40);
      v6 = v18;
      if ( v18 < 0 )
      {
        LODWORD(hKey) = 0;
        v41 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v55, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v55[v19] );
        goto LABEL_87;
      }
    }
    IsLocalServer = PlaiIsLocalServer((wchar_t *)lpMachineName[1], &v41);
    v6 = IsLocalServer;
    if ( IsLocalServer < 0 )
    {
      LODWORD(hKey) = 0;
      v41 = IsLocalServer;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_89;
      }
      PlaiWhoAmI(v56, 0x4000000000000800uLL);
      v21 = -1;
      do
        ++v21;
      while ( v56[v21] );
      goto LABEL_87;
    }
    v22 = PlaiStringToRegKey(v15, &hKey);
    v6 = v22;
    if ( v22 < 0 )
    {
      LODWORD(hKey) = 0;
      v41 = v22;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_89;
      }
      PlaiWhoAmI(v57, 0x4000000000000800uLL);
      v24 = -1;
      do
        ++v24;
      while ( v57[v24] );
      goto LABEL_87;
    }
    if ( v41 )
    {
      v28 = hKey;
    }
    else
    {
      v25 = RegConnectRegistryW(lpMachineName[1], hKey, &phkResult);
      v26 = PlaiHResultFromWin32(v25);
      v6 = v26;
      if ( v26 < 0 )
      {
        LODWORD(hKey) = 0;
        v41 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v58, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v58[v27] );
        goto LABEL_87;
      }
      v28 = phkResult;
    }
    if ( LODWORD(lpValueName[1]) )
    {
      if ( LODWORD(lpValueName[1]) == 1 )
      {
        v31 = PlaiForEachRegKey<_PLA_REGISTRY_CONTEXT *,long (*)(HKEY__ *,unsigned short const *,_PLA_REGISTRY_CONTEXT *)>(
                v28,
                v14,
                0,
                v23,
                (struct _PLA_REGISTRY_CONTEXT *)Buffer);
        v6 = v31;
        if ( v31 >= 0 )
          goto LABEL_89;
        LODWORD(hKey) = 0;
        v41 = v31;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v60, 0x4000000000000800uLL);
        v32 = -1;
        do
          ++v32;
        while ( v60[v32] );
      }
      else
      {
        if ( LODWORD(lpValueName[1]) != 2 )
          goto LABEL_89;
        v29 = PlaiForEachRegKey<_PLA_REGISTRY_CONTEXT *,long (*)(HKEY__ *,unsigned short const *,_PLA_REGISTRY_CONTEXT *)>(
                v28,
                v14,
                (__int64 (__fastcall *)(HKEY, LPWSTR, struct _PLA_REGISTRY_CONTEXT *))PlaiRegRecursiveKey,
                v23,
                (struct _PLA_REGISTRY_CONTEXT *)Buffer);
        v6 = v29;
        if ( v29 >= 0 )
          goto LABEL_89;
        LODWORD(hKey) = 0;
        v41 = v29;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v59[v30] );
      }
    }
    else
    {
      v33 = RegOpenKeyExW(v28, v14, 0, 0x20019u, &v44);
      v34 = PlaiHResultFromWin32(v33);
      v6 = v34;
      if ( v34 >= 0 )
      {
        v36 = PlaiRegSaveValue(v44, lpValueName[0], (struct _PLA_REGISTRY_CONTEXT *)Buffer);
        v6 = v36;
        if ( v36 >= 0 )
          goto LABEL_89;
        LODWORD(hKey) = 0;
        v41 = v36;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v62, 0x4000000000000800uLL);
        v37 = -1;
        do
          ++v37;
        while ( v62[v37] );
      }
      else
      {
        LODWORD(hKey) = 0;
        v41 = v34;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v61, 0x4000000000000800uLL);
        v35 = -1;
        do
          ++v35;
        while ( v61[v35] );
      }
    }
LABEL_87:
    v9 = &v41;
    p_hKey = &hKey;
LABEL_88:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      v9,
      4,
      qword_180147320,
      1,
      p_hKey,
      4,
      "HConfigurationDataCollector::QueryRegistryKey",
      46);
    goto LABEL_89;
  }
  v41 = 0;
  LODWORD(hKey) = v5;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v52, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v52[v7] );
    p_hKey = &v41;
    v9 = &hKey;
    goto LABEL_88;
  }
LABEL_89:
  if ( Buffer[0] )
  {
    PlaiFree(Buffer[0], 1);
    Buffer[0] = 0;
  }
  PlaiFreeString((BSTR)lpMachineName[0]);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v44 )
    RegCloseKey(v44);
  return v6;
}

```

## disassembly

```asm
0x1800f4804  push    rbp
0x1800f4806  push    rbx
0x1800f4807  push    rsi
0x1800f4808  push    rdi
0x1800f4809  push    r12
0x1800f480b  push    r14
0x1800f480d  push    r15
0x1800f480f  lea     rbp, [rsp-590h]
0x1800f4817  sub     rsp, 690h
0x1800f481e  mov     rax, cs:__security_cookie
0x1800f4825  xor     rax, rsp
0x1800f4828  mov     [rbp+5C0h+var_40], rax
0x1800f482f  xorps   xmm0, xmm0
0x1800f4832  xor     r15d, r15d
0x1800f4835  mov     rdi, rcx
0x1800f4838  mov     [rsp+6C0h+var_650], r15d
0x1800f483d  xor     ecx, ecx
0x1800f483f  mov     [rsp+6C0h+hKey], r15
0x1800f4844  mov     rax, rdx
0x1800f4847  mov     [rbp+5C0h+var_600], rcx
0x1800f484b  mov     rcx, rax; unsigned __int16 *
0x1800f484e  mov     [rbp+5C0h+phkResult], r15
0x1800f4852  lea     rdx, [rbp+5C0h+lpMachineName]; struct _QUERY_PATH *
0x1800f4856  mov     [rbp+5C0h+var_638], r15
0x1800f485a  mov     rsi, r8
0x1800f485d  movups  xmmword ptr [rbp+5C0h+Buffer], xmm0
0x1800f4861  movups  xmmword ptr [rbp+5C0h+var_620], xmm0
0x1800f4865  movups  [rbp+5C0h+var_610], xmm0
0x1800f4869  movups  xmmword ptr [rbp+5C0h+lpMachineName], xmm0
0x1800f486d  movups  xmmword ptr [rbp+5C0h+lpSubKey], xmm0
0x1800f4871  movups  xmmword ptr [rbp+5C0h+lpValueName], xmm0
0x1800f4875  call    ?ParsePath@@YAJPEAGPEAU_QUERY_PATH@@@Z; ParsePath(ushort *,_QUERY_PATH *)
0x1800f487a  lea     r12d, [r15+1]
0x1800f487e  mov     ebx, eax
0x1800f4880  test    eax, eax
0x1800f4882  jns     loc_1800F490D
0x1800f4888  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f488f  mov     [rsp+6C0h+var_650], r15d
0x1800f4894  mov     dword ptr [rsp+6C0h+hKey], eax
0x1800f4898  jz      loc_1800F4FCA
0x1800f489e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f48a8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f48af  jz      loc_1800F4FCA
0x1800f48b5  mov     rax, cs:qword_180169748
0x1800f48bc  and     rax, rdx
0x1800f48bf  cmp     cs:qword_180169748, rax
0x1800f48c6  jnz     loc_1800F4FCA
0x1800f48cc  lea     rcx, [rbp+5C0h+var_5C0]; unsigned __int16 *
0x1800f48d0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f48d5  lea     rcx, [rbp+5C0h+var_5C0]
0x1800f48d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f48dd  inc     rax
0x1800f48e0  cmp     [rcx+rax*2], r15w
0x1800f48e5  jnz     short loc_1800F48DD
0x1800f48e7  lea     ecx, [rax+rax]
0x1800f48ea  add     rcx, 2
0x1800f48ee  lea     rax, [rbp+5C0h+var_5C0]
0x1800f48f2  mov     [rsp+6C0h+var_660], rcx
0x1800f48f7  lea     r14, qword_180147320
0x1800f48fe  lea     rcx, [rsp+6C0h+var_650]
0x1800f4903  lea     r9, [rsp+6C0h+hKey]
0x1800f4908  jmp     loc_1800F4F7B
0x1800f490d  lea     r14, qword_180147320
0x1800f4914  xor     r8d, r8d; int
0x1800f4917  mov     r9, r14; char *
0x1800f491a  mov     edx, r12d; int
0x1800f491d  mov     ecx, 800h; dwBytes
0x1800f4922  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800f4927  mov     [rbp+5C0h+Buffer], rax
0x1800f492b  test    rax, rax
0x1800f492e  jnz     short loc_1800F49A9
0x1800f4930  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4937  mov     ebx, 8007000Eh
0x1800f493c  mov     [rsp+6C0h+var_650], ebx
0x1800f4940  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4945  jz      loc_1800F4FCA
0x1800f494b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4955  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f495c  jz      loc_1800F4FCA
0x1800f4962  mov     rax, cs:qword_180169748
0x1800f4969  and     rax, rdx
0x1800f496c  cmp     cs:qword_180169748, rax
0x1800f4973  jnz     loc_1800F4FCA
0x1800f4979  lea     rcx, [rbp+5C0h+var_540]; unsigned __int16 *
0x1800f4980  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4985  lea     rcx, [rbp+5C0h+var_540]
0x1800f498c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4990  inc     rax
0x1800f4993  cmp     [rcx+rax*2], r15w
0x1800f4998  jnz     short loc_1800F4990
0x1800f499a  lea     ecx, [rax+rax]
0x1800f499d  lea     rax, [rbp+5C0h+var_540]
0x1800f49a4  jmp     loc_1800F4F68
0x1800f49a9  mov     edx, [rdi+0E4h]
0x1800f49af  mov     ecx, 32h ; '2'
0x1800f49b4  mov     qword ptr [rbp+5C0h+var_610+8], rsi
0x1800f49b8  lea     eax, [rdx-1]
0x1800f49bb  cmp     eax, 31h ; '1'
0x1800f49be  mov     rax, [rdi+100h]
0x1800f49c5  mov     qword ptr [rbp+5C0h+var_610], rax
0x1800f49c9  mov     rax, [rdi+48h]
0x1800f49cd  cmovbe  ecx, edx
0x1800f49d0  mov     rdi, [rbp+5C0h+lpSubKey+8]
0x1800f49d4  mov     edx, 400h; unsigned __int64
0x1800f49d9  mov     dword ptr [rbp+5C0h+var_620+8], ecx
0x1800f49dc  mov     [rbp+5C0h+var_620], rdx
0x1800f49e0  mov     rcx, [rax+38h]
0x1800f49e4  mov     rax, [rcx+10h]
0x1800f49e8  mov     [rbp+5C0h+var_600], rax
0x1800f49ec  test    rdi, rdi
0x1800f49ef  jz      loc_1800F4AAD
0x1800f49f5  cmp     r15w, [rdi]
0x1800f49f9  jz      loc_1800F4AAD
0x1800f49ff  mov     rsi, [rbp+5C0h+lpSubKey]
0x1800f4a03  lea     rax, aSS_0; "%s\\%s"
0x1800f4a0a  mov     rcx, [rbp+5C0h+Buffer]; Buffer
0x1800f4a0e  lea     r9, [rbp+5C0h+var_620]; unsigned __int64 *
0x1800f4a12  mov     [rsp+6C0h+var_688], rdi
0x1800f4a17  lea     r8, [rbp+5C0h+Buffer+8]; unsigned __int16 **
0x1800f4a1b  mov     [rsp+6C0h+var_690], rsi
0x1800f4a20  mov     [rsp+6C0h+var_698], rax; unsigned __int16 *
0x1800f4a25  mov     [rsp+6C0h+var_6A0], r15; unsigned int
0x1800f4a2a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800f4a2f  mov     ebx, eax
0x1800f4a31  test    eax, eax
0x1800f4a33  jns     loc_1800F4B44
0x1800f4a39  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4a40  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4a45  mov     [rsp+6C0h+var_650], eax
0x1800f4a49  jz      loc_1800F4FCA
0x1800f4a4f  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4a59  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4a60  jz      loc_1800F4FCA
0x1800f4a66  mov     rax, cs:qword_180169748
0x1800f4a6d  and     rax, rdx
0x1800f4a70  cmp     cs:qword_180169748, rax
0x1800f4a77  jnz     loc_1800F4FCA
0x1800f4a7d  lea     rcx, [rbp+5C0h+var_4C0]; unsigned __int16 *
0x1800f4a84  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4a89  lea     rcx, [rbp+5C0h+var_4C0]
0x1800f4a90  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4a94  inc     rax
0x1800f4a97  cmp     [rcx+rax*2], r15w
0x1800f4a9c  jnz     short loc_1800F4A94
0x1800f4a9e  lea     ecx, [rax+rax]
0x1800f4aa1  lea     rax, [rbp+5C0h+var_4C0]
0x1800f4aa8  jmp     loc_1800F4F68
0x1800f4aad  mov     rsi, [rbp+5C0h+lpSubKey]
0x1800f4ab1  lea     rax, [rbp+5C0h+var_620]
0x1800f4ab5  mov     rcx, [rbp+5C0h+Buffer]; unsigned __int16 *
0x1800f4ab9  lea     r9, [rbp+5C0h+Buffer+8]; unsigned __int16 **
0x1800f4abd  mov     r8, rsi; unsigned __int16 *
0x1800f4ac0  mov     [rsp+6C0h+var_6A0], rax; unsigned __int64 *
0x1800f4ac5  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800f4aca  mov     ebx, eax
0x1800f4acc  test    eax, eax
0x1800f4ace  jns     short loc_1800F4B44
0x1800f4ad0  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4ad7  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4adc  mov     [rsp+6C0h+var_650], eax
0x1800f4ae0  jz      loc_1800F4FCA
0x1800f4ae6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4af0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4af7  jz      loc_1800F4FCA
0x1800f4afd  mov     rax, cs:qword_180169748
0x1800f4b04  and     rax, rdx
0x1800f4b07  cmp     cs:qword_180169748, rax
0x1800f4b0e  jnz     loc_1800F4FCA
0x1800f4b14  lea     rcx, [rbp+5C0h+var_440]; unsigned __int16 *
0x1800f4b1b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4b20  lea     rcx, [rbp+5C0h+var_440]
0x1800f4b27  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4b2b  inc     rax
0x1800f4b2e  cmp     [rcx+rax*2], r15w
0x1800f4b33  jnz     short loc_1800F4B2B
0x1800f4b35  lea     ecx, [rax+rax]
0x1800f4b38  lea     rax, [rbp+5C0h+var_440]
0x1800f4b3f  jmp     loc_1800F4F68
0x1800f4b44  mov     rcx, [rbp+5C0h+lpMachineName+8]; String2
0x1800f4b48  lea     rdx, [rsp+6C0h+var_650]; int *
0x1800f4b4d  call    ?PlaiIsLocalServer@@YAJPEBGPEAH@Z; PlaiIsLocalServer(ushort const *,int *)
0x1800f4b52  mov     ebx, eax
0x1800f4b54  test    eax, eax
0x1800f4b56  jns     short loc_1800F4BCC
0x1800f4b58  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4b5f  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4b64  mov     [rsp+6C0h+var_650], eax
0x1800f4b68  jz      loc_1800F4FCA
0x1800f4b6e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4b78  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4b7f  jz      loc_1800F4FCA
0x1800f4b85  mov     rax, cs:qword_180169748
0x1800f4b8c  and     rax, rdx
0x1800f4b8f  cmp     cs:qword_180169748, rax
0x1800f4b96  jnz     loc_1800F4FCA
0x1800f4b9c  lea     rcx, [rbp+5C0h+var_3C0]; unsigned __int16 *
0x1800f4ba3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4ba8  lea     rcx, [rbp+5C0h+var_3C0]
0x1800f4baf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4bb3  inc     rax
0x1800f4bb6  cmp     [rcx+rax*2], r15w
0x1800f4bbb  jnz     short loc_1800F4BB3
0x1800f4bbd  lea     ecx, [rax+rax]
0x1800f4bc0  lea     rax, [rbp+5C0h+var_3C0]
0x1800f4bc7  jmp     loc_1800F4F68
0x1800f4bcc  lea     rdx, [rsp+6C0h+hKey]; HKEY *
0x1800f4bd1  mov     rcx, rsi; String1
0x1800f4bd4  call    ?PlaiStringToRegKey@@YAJPEBGPEAPEAUHKEY__@@@Z; PlaiStringToRegKey(ushort const *,HKEY__ * *)
0x1800f4bd9  mov     ebx, eax
0x1800f4bdb  test    eax, eax
0x1800f4bdd  jns     short loc_1800F4C53
0x1800f4bdf  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4be6  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4beb  mov     [rsp+6C0h+var_650], eax
0x1800f4bef  jz      loc_1800F4FCA
0x1800f4bf5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4bff  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4c06  jz      loc_1800F4FCA
0x1800f4c0c  mov     rax, cs:qword_180169748
0x1800f4c13  and     rax, rdx
0x1800f4c16  cmp     cs:qword_180169748, rax
0x1800f4c1d  jnz     loc_1800F4FCA
0x1800f4c23  lea     rcx, [rbp+5C0h+var_340]; unsigned __int16 *
0x1800f4c2a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4c2f  lea     rcx, [rbp+5C0h+var_340]
0x1800f4c36  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4c3a  inc     rax
0x1800f4c3d  cmp     [rcx+rax*2], r15w
0x1800f4c42  jnz     short loc_1800F4C3A
0x1800f4c44  lea     ecx, [rax+rax]
0x1800f4c47  lea     rax, [rbp+5C0h+var_340]
0x1800f4c4e  jmp     loc_1800F4F68
0x1800f4c53  cmp     [rsp+6C0h+var_650], r15d
0x1800f4c58  jnz     loc_1800F4CF8
0x1800f4c5e  mov     rdx, [rsp+6C0h+hKey]; hKey
0x1800f4c63  lea     r8, [rbp+5C0h+phkResult]; phkResult
0x1800f4c67  mov     rcx, [rbp+5C0h+lpMachineName+8]; lpMachineName
0x1800f4c6b  call    cs:__imp_RegConnectRegistryW
0x1800f4c71  mov     ecx, eax; unsigned int
0x1800f4c73  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f4c78  mov     ebx, eax
0x1800f4c7a  test    eax, eax
0x1800f4c7c  jns     short loc_1800F4CF2
0x1800f4c7e  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4c85  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4c8a  mov     [rsp+6C0h+var_650], eax
0x1800f4c8e  jz      loc_1800F4FCA
0x1800f4c94  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4c9e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4ca5  jz      loc_1800F4FCA
0x1800f4cab  mov     rax, cs:qword_180169748
0x1800f4cb2  and     rax, rdx
0x1800f4cb5  cmp     cs:qword_180169748, rax
0x1800f4cbc  jnz     loc_1800F4FCA
0x1800f4cc2  lea     rcx, [rbp+5C0h+var_2C0]; unsigned __int16 *
0x1800f4cc9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4cce  lea     rcx, [rbp+5C0h+var_2C0]
0x1800f4cd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4cd9  inc     rax
0x1800f4cdc  cmp     [rcx+rax*2], r15w
0x1800f4ce1  jnz     short loc_1800F4CD9
0x1800f4ce3  lea     ecx, [rax+rax]
0x1800f4ce6  lea     rax, [rbp+5C0h+var_2C0]
0x1800f4ced  jmp     loc_1800F4F68
0x1800f4cf2  mov     rcx, [rbp+5C0h+phkResult]
0x1800f4cf6  jmp     short loc_1800F4CFD
0x1800f4cf8  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800f4cfd  mov     edx, dword ptr [rbp+5C0h+lpValueName+8]
0x1800f4d00  test    edx, edx
0x1800f4d02  jz      loc_1800F4E42
0x1800f4d08  sub     edx, r12d
0x1800f4d0b  jz      loc_1800F4DB0
0x1800f4d11  cmp     edx, r12d
0x1800f4d14  jnz     loc_1800F4FCA
0x1800f4d1a  lea     rax, [rbp+5C0h+Buffer]
0x1800f4d1e  mov     rdx, rdi
0x1800f4d21  lea     r8, ?PlaiRegRecursiveKey@@YAJPEAUHKEY__@@PEBGPEAU_PLA_REGISTRY_CONTEXT@@@Z; PlaiRegRecursiveKey(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *)
0x1800f4d28  mov     [rsp+6C0h+var_6A0], rax
0x1800f4d2d  call    ??$PlaiForEachRegKey@PEAU_PLA_REGISTRY_CONTEXT@@P6AJPEAUHKEY__@@PEBGPEAU1@@Z@@YAJPEAUHKEY__@@PEBGP6AJ01PEAU_PLA_REGISTRY_CONTEXT@@@Z32@Z; PlaiForEachRegKey<_PLA_REGISTRY_CONTEXT *,long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *)>(HKEY__ *,ushort const *,long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *),long (*)(HKEY__ *,ushort const *,_PLA_REGISTRY_CONTEXT *),_PLA_REGISTRY_CONTEXT *)
0x1800f4d32  mov     ebx, eax
0x1800f4d34  test    eax, eax
0x1800f4d36  jns     loc_1800F4FCA
0x1800f4d3c  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f4d43  mov     dword ptr [rsp+6C0h+hKey], r15d
0x1800f4d48  mov     [rsp+6C0h+var_650], eax
0x1800f4d4c  jz      loc_1800F4FCA
0x1800f4d52  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f4d5c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f4d63  jz      loc_1800F4FCA
0x1800f4d69  mov     rax, cs:qword_180169748
0x1800f4d70  and     rax, rdx
0x1800f4d73  cmp     cs:qword_180169748, rax
0x1800f4d7a  jnz     loc_1800F4FCA
0x1800f4d80  lea     rcx, [rbp+5C0h+var_240]; unsigned __int16 *
0x1800f4d87  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f4d8c  lea     rcx, [rbp+5C0h+var_240]
0x1800f4d93  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f4d97  inc     rax
0x1800f4d9a  cmp     [rcx+rax*2], r15w
0x1800f4d9f  jnz     short loc_1800F4D97
  ... truncated ...
```
