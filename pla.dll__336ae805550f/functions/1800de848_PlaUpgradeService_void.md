# PlaUpgradeService(void)

- ea: `0x1800de848`
- end: `0x1800df40d`
- name: `?PlaUpgradeService@@YAJXZ`
- size: `3013`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a8040`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x1800198b0`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x1800bb9f0`
- `0x1800de848`
- `0x18010c7a4`
- `0x18010e430`
- `0x18010ea30`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800de8c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800df0d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800df21b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800de8c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800df0d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800df21b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df0a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df1f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df3b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df0a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df1f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800df3b4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800df168`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800df2ad`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800df168`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800df2ad`

## string_xrefs

- `0x1800de8b3`: `System\CurrentControlSet\Services\SysmonLog`
- `0x1800df35b`: `PlaUpgradeService`
- `0x1800df0c9`: `System\CurrentControlSet\Services\SysMonLog`
- `0x1800df211`: `System\CurrentControlSet\Services`

## pseudocode

```c
__int64 PlaUpgradeService(void)
{
  __int64 Class; // r15
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  __int64 v4; // rax
  int *v5; // rcx
  int *v6; // r9
  __int64 v7; // rax
  const char *v8; // rdx
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 (__fastcall *v17)(__int64, struct tagVARIANT *, struct IDataCollectorSet **); // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  const char *v24; // rdx
  int v25; // r8d
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  unsigned int i; // eax
  __int64 (__fastcall *v30)(__int64, struct tagVARIANT *, struct IDataCollectorSet **); // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  LSTATUS v35; // eax
  int v36; // eax
  __int64 v37; // rax
  LSTATUS v38; // eax
  int v39; // eax
  __int64 v40; // rax
  LSTATUS v41; // eax
  int v42; // eax
  __int64 v43; // rax
  LSTATUS v44; // eax
  int v45; // eax
  __int64 v46; // rax
  int v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  struct IDataCollectorSet *v52; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v53; // [rsp+98h] [rbp-68h] BYREF
  struct tagVARIANT v54; // [rsp+A0h] [rbp-60h] BYREF
  struct tagVARIANT v55; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v56[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v57[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v58[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v59[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v60[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v61[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v62[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v63[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v64[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v65[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v66[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v67[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v68[64]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v69[64]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v70[64]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned __int16 v71[64]; // [rsp+860h] [rbp+760h] BYREF

  v53 = 0;
  bstrString = 0;
  hKey = 0;
  Class = 0;
  v52 = 0;
  memset(&v54, 0, sizeof(v54));
  PlaiVariantInit(&v54);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\SysmonLog", 0, 0xF003Fu, &hKey);
  if ( (int)PlaiHResultFromWin32(v1) < 0 )
  {
    v2 = 0;
    goto LABEL_132;
  }
  v3 = PlaiForEachRegKey<int,long (*)(HKEY__ *,unsigned short const *,int)>(hKey);
  v2 = v3;
  if ( v3 >= 0 )
  {
    Class = CreateClassObject<CDataCollectorSetCollection>((char *)byte_180147320, 0);
    if ( Class )
    {
      PlaiFreeString(bstrString);
      bstrString = PlaiAllocStringEx(L"legacy\\*", v8, v9);
      if ( bstrString )
      {
        v11 = Class + 8;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)(Class + 8) + 112LL))(
                Class + 8,
                0,
                bstrString);
        v2 = v12;
        if ( v12 >= 0 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 56LL))(Class + 8, &v53);
          v2 = v14;
          if ( v14 >= 0 )
          {
            v16 = 0;
            v54.vt = 19;
            while ( 1 )
            {
              v54.lVal = v16;
              if ( v16 >= v53 )
                break;
              if ( v52 )
              {
                ((void (__fastcall *)(struct IDataCollectorSet *))v52->lpVtbl->Release)(v52);
                v52 = 0;
              }
              v17 = *(__int64 (__fastcall **)(__int64, struct tagVARIANT *, struct IDataCollectorSet **))(*(_QWORD *)v11 + 64LL);
              v55 = v54;
              v18 = v17(Class + 8, &v55, &v52);
              v2 = v18;
              if ( v18 < 0 )
              {
                v49 = 0;
                v48 = v18;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v63, 0x4000000000000800uLL);
                  v23 = -1;
                  do
                    ++v23;
                  while ( v63[v23] );
                  goto LABEL_130;
                }
                goto LABEL_132;
              }
              PlaiFreeString(bstrString);
              bstrString = 0;
              v19 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))v52->lpVtbl->get_Name)(
                      v52,
                      &bstrString);
              v2 = v19;
              if ( v19 < 0 )
              {
                v49 = 0;
                v48 = v19;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v62, 0x4000000000000800uLL);
                  v22 = -1;
                  do
                    ++v22;
                  while ( v62[v22] );
                  goto LABEL_130;
                }
                goto LABEL_132;
              }
              if ( PlaiSetLegacyCreds(v52, bstrString) < 0
                || ((int (__fastcall *)(struct IDataCollectorSet *, BSTR, _QWORD, __int64, _QWORD))v52->lpVtbl->Commit)(
                     v52,
                     bstrString,
                     0,
                     1,
                     0) < 0 )
              {
                v20 = PlaDumpDataCollectorSetToFile(v52, bstrString);
                v2 = v20;
                if ( v20 < 0 )
                {
                  v49 = 0;
                  v48 = v20;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v61, 0x4000000000000800uLL);
                    v21 = -1;
                    do
                      ++v21;
                    while ( v61[v21] );
                    goto LABEL_130;
                  }
                  goto LABEL_132;
                }
              }
              v16 = v54.lVal + 1;
            }
            PlaiFreeString(bstrString);
            bstrString = 0;
            bstrString = PlaiAllocStringEx(L"legacy\\*", v24, v25);
            if ( bstrString )
            {
              v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)v11 + 112LL))(
                      Class + 8,
                      0,
                      bstrString);
              v2 = v27;
              if ( v27 >= 0 )
              {
                v54.vt = 19;
                for ( i = 0; ; i = v54.lVal + 1 )
                {
                  v54.lVal = i;
                  if ( i >= v53 )
                    break;
                  if ( v52 )
                  {
                    ((void (__fastcall *)(struct IDataCollectorSet *))v52->lpVtbl->Release)(v52);
                    v52 = 0;
                  }
                  v30 = *(__int64 (__fastcall **)(__int64, struct tagVARIANT *, struct IDataCollectorSet **))(*(_QWORD *)v11 + 64LL);
                  v55 = v54;
                  v31 = v30(Class + 8, &v55, &v52);
                  v2 = v31;
                  if ( v31 < 0 )
                  {
                    v49 = 0;
                    v48 = v31;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v67, 0x4000000000000800uLL);
                      v34 = -1;
                      do
                        ++v34;
                      while ( v67[v34] );
                      goto LABEL_130;
                    }
                    goto LABEL_132;
                  }
                  v32 = ((__int64 (__fastcall *)(struct IDataCollectorSet *))v52->lpVtbl->Delete)(v52);
                  v2 = v32;
                  if ( v32 < 0 )
                  {
                    v49 = 0;
                    v48 = v32;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v66, 0x4000000000000800uLL);
                      v33 = -1;
                      do
                        ++v33;
                      while ( v66[v33] );
                      goto LABEL_130;
                    }
                    goto LABEL_132;
                  }
                }
                if ( hKey )
                {
                  RegCloseKey(hKey);
                  hKey = 0;
                }
                v35 = RegOpenKeyExW(
                        HKEY_LOCAL_MACHINE,
                        L"System\\CurrentControlSet\\Services\\SysMonLog",
                        0,
                        0xF003Fu,
                        &hKey);
                v36 = PlaiHResultFromWin32(v35);
                v2 = v36;
                if ( v36 >= 0 )
                {
                  v38 = RegDeleteKeyW(hKey, L"Log Queries");
                  v39 = PlaiHResultFromWin32(v38);
                  v2 = v39;
                  if ( v39 >= 0 )
                  {
                    if ( hKey )
                    {
                      RegCloseKey(hKey);
                      hKey = 0;
                    }
                    v41 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0, 0xF003Fu, &hKey);
                    v42 = PlaiHResultFromWin32(v41);
                    v2 = v42;
                    if ( v42 >= 0 )
                    {
                      v44 = RegDeleteKeyW(hKey, L"SysMonLog");
                      v45 = PlaiHResultFromWin32(v44);
                      v2 = v45;
                      if ( v45 < 0 )
                      {
                        v49 = 0;
                        v48 = v45;
                        if ( (_DWORD)xmmword_180169738 )
                        {
                          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                          {
                            PlaiWhoAmI(v71, 0x4000000000000800uLL);
                            v46 = -1;
                            do
                              ++v46;
                            while ( v71[v46] );
                            goto LABEL_130;
                          }
                        }
                      }
                    }
                    else
                    {
                      v49 = 0;
                      v48 = v42;
                      if ( (_DWORD)xmmword_180169738
                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v70, 0x4000000000000800uLL);
                        v43 = -1;
                        do
                          ++v43;
                        while ( v70[v43] );
                        goto LABEL_130;
                      }
                    }
                  }
                  else
                  {
                    v49 = 0;
                    v48 = v39;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v69, 0x4000000000000800uLL);
                      v40 = -1;
                      do
                        ++v40;
                      while ( v69[v40] );
                      goto LABEL_130;
                    }
                  }
                }
                else
                {
                  v49 = 0;
                  v48 = v36;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v68, 0x4000000000000800uLL);
                    v37 = -1;
                    do
                      ++v37;
                    while ( v68[v37] );
                    goto LABEL_130;
                  }
                }
              }
              else
              {
                v49 = 0;
                v48 = v27;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v65, 0x4000000000000800uLL);
                  v28 = -1;
                  do
                    ++v28;
                  while ( v65[v28] );
                  goto LABEL_130;
                }
              }
            }
            else
            {
              v2 = -2147024882;
              v48 = -2147024882;
              v49 = 0;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v64, 0x4000000000000800uLL);
                v26 = -1;
                do
                  ++v26;
                while ( v64[v26] );
                goto LABEL_130;
              }
            }
            goto LABEL_132;
          }
          v49 = 0;
          v48 = v14;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_132;
          }
          PlaiWhoAmI(v60, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v60[v15] );
        }
        else
        {
          v49 = 0;
          v48 = v12;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_132;
          }
          PlaiWhoAmI(v59, 0x4000000000000800uLL);
          v13 = -1;
          do
            ++v13;
          while ( v59[v13] );
        }
      }
      else
      {
        v2 = -2147024882;
        v48 = -2147024882;
        v49 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v58, 0x4000000000000800uLL);
        v10 = -1;
        do
          ++v10;
        while ( v58[v10] );
      }
    }
    else
    {
      v2 = -2147024882;
      v48 = -2147024882;
      v49 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_132;
      }
      PlaiWhoAmI(v57, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v57[v7] );
    }
LABEL_130:
    v6 = &v48;
    v5 = &v49;
LABEL_131:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v6, 4, byte_180147320, 1, v5, 4);
    goto LABEL_132;
  }
  v48 = 0;
  v49 = v3;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v4 = -1;
    do
      ++v4;
    while ( v56[v4] );
    v5 = &v48;
    v6 = &v49;
    goto LABEL_131;
  }
LABEL_132:
  PlaiVariantClear(&v54);
  PlaiFreeString(bstrString);
  bstrString = 0;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Class )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(Class + 8) + 16LL))(Class + 8);
  if ( v52 )
    ((void (__fastcall *)(struct IDataCollectorSet *))v52->lpVtbl->Release)(v52);
  return v2;
}

```

## disassembly

```asm
0x1800de848  push    rbp
0x1800de84a  push    rbx
0x1800de84b  push    rsi
0x1800de84c  push    rdi
0x1800de84d  push    r12
0x1800de84f  push    r13
0x1800de851  push    r14
0x1800de853  push    r15
0x1800de855  lea     rbp, [rsp-7F8h]
0x1800de85d  sub     rsp, 8F8h
0x1800de864  mov     rax, cs:__security_cookie
0x1800de86b  xor     rax, rsp
0x1800de86e  mov     [rbp+830h+var_50], rax
0x1800de875  xor     r12d, r12d
0x1800de878  lea     rcx, [rbp+830h+var_890]; struct tagVARIANT *
0x1800de87c  xorps   xmm0, xmm0
0x1800de87f  mov     [rbp+830h+var_898], r12d
0x1800de883  xor     eax, eax
0x1800de885  mov     [rbp+830h+bstrString], r12
0x1800de889  mov     [rbp+830h+hKey], r12
0x1800de88d  mov     r15d, r12d
0x1800de890  mov     [rbp+830h+var_8A0], r12
0x1800de894  movups  xmmword ptr [rbp+830h+var_890], xmm0
0x1800de898  mov     qword ptr [rbp+830h+var_890+10h], rax
0x1800de89c  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800de8a1  lea     rax, [rbp+830h+hKey]
0x1800de8a5  mov     r9d, 0F003Fh; samDesired
0x1800de8ab  xor     r8d, r8d; ulOptions
0x1800de8ae  mov     [rsp+930h+phkResult], rax; phkResult
0x1800de8b3  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sy"...
0x1800de8ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800de8c1  call    cs:__imp_RegOpenKeyExW
0x1800de8c7  mov     ecx, eax; unsigned int
0x1800de8c9  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800de8ce  test    eax, eax
0x1800de8d0  jns     short loc_1800DE8DA
0x1800de8d2  mov     ebx, r12d
0x1800de8d5  jmp     loc_1800DF395
0x1800de8da  mov     rcx, [rbp+830h+hKey]
0x1800de8de  call    ??$PlaiForEachRegKey@HP6AJPEAUHKEY__@@PEBGH@Z@@YAJPEAUHKEY__@@PEBGP6AJ01H@Z2H@Z; PlaiForEachRegKey<int,long (*)(HKEY__ *,ushort const *,int)>(HKEY__ *,ushort const *,long (*)(HKEY__ *,ushort const *,int),long (*)(HKEY__ *,ushort const *,int),int)
0x1800de8e3  mov     ebx, eax
0x1800de8e5  test    eax, eax
0x1800de8e7  jns     loc_1800DE977
0x1800de8ed  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800de8f4  mov     [rsp+930h+var_8C0], r12d
0x1800de8f9  mov     [rsp+930h+var_8B8], eax
0x1800de8fd  jz      loc_1800DF395
0x1800de903  mov     rdx, 4000000000000800h; unsigned __int64
0x1800de90d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800de914  jz      loc_1800DF395
0x1800de91a  mov     rax, cs:qword_180169748
0x1800de921  and     rax, rdx
0x1800de924  cmp     cs:qword_180169748, rax
0x1800de92b  jnz     loc_1800DF395
0x1800de931  lea     rcx, [rbp+830h+var_850]; unsigned __int16 *
0x1800de935  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800de93a  lea     rcx, [rbp+830h+var_850]
0x1800de93e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800de942  inc     rax
0x1800de945  cmp     [rcx+rax*2], r12w
0x1800de94a  jnz     short loc_1800DE942
0x1800de94c  lea     ecx, [rax+rax]
0x1800de94f  mov     esi, 1
0x1800de954  add     rcx, 2
0x1800de958  lea     rax, [rbp+830h+var_850]
0x1800de95c  mov     [rsp+930h+var_8D0], rcx
0x1800de961  lea     r14, byte_180147320
0x1800de968  lea     rcx, [rsp+930h+var_8C0]
0x1800de96d  lea     r9, [rsp+930h+var_8B8]
0x1800de972  jmp     loc_1800DF346
0x1800de977  lea     r14, byte_180147320
0x1800de97e  xor     edx, edx; int
0x1800de980  mov     rcx, r14; char *
0x1800de983  call    ??$CreateClassObject@VCDataCollectorSetCollection@@@@YAPEAVCDataCollectorSetCollection@@PEBDH@Z; CreateClassObject<CDataCollectorSetCollection>(char const *,int)
0x1800de988  mov     r15, rax
0x1800de98b  test    rax, rax
0x1800de98e  jnz     short loc_1800DEA07
0x1800de990  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800de997  mov     ecx, 8007000Eh
0x1800de99c  mov     ebx, ecx
0x1800de99e  mov     [rsp+930h+var_8C0], ecx
0x1800de9a2  mov     [rsp+930h+var_8B8], r12d
0x1800de9a7  jz      loc_1800DF395
0x1800de9ad  mov     rdx, 4000000000000800h; unsigned __int64
0x1800de9b7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800de9be  jz      loc_1800DF395
0x1800de9c4  mov     rax, cs:qword_180169748
0x1800de9cb  and     rax, rdx
0x1800de9ce  cmp     cs:qword_180169748, rax
0x1800de9d5  jnz     loc_1800DF395
0x1800de9db  lea     rcx, [rbp+830h+var_7D0]; unsigned __int16 *
0x1800de9df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800de9e4  lea     rcx, [rbp+830h+var_7D0]
0x1800de9e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800de9ec  inc     rax
0x1800de9ef  cmp     [rcx+rax*2], r12w
0x1800de9f4  jnz     short loc_1800DE9EC
0x1800de9f6  lea     ecx, [rax+rax]
0x1800de9f9  lea     rax, [rbp+830h+var_7D0]
0x1800de9fd  mov     esi, 1
0x1800dea02  jmp     loc_1800DF333
0x1800dea07  mov     rcx, [rbp+830h+bstrString]; bstrString
0x1800dea0b  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800dea10  lea     rcx, aLegacy_0; "legacy\\*"
0x1800dea17  mov     [rbp+830h+bstrString], r12
0x1800dea1b  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800dea20  mov     [rbp+830h+bstrString], rax
0x1800dea24  mov     r8, rax
0x1800dea27  test    rax, rax
0x1800dea2a  jnz     short loc_1800DEAA7
0x1800dea2c  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800dea33  mov     ecx, 8007000Eh
0x1800dea38  mov     ebx, ecx
0x1800dea3a  mov     [rsp+930h+var_8C0], ecx
0x1800dea3e  mov     [rsp+930h+var_8B8], r12d
0x1800dea43  jz      loc_1800DF395
0x1800dea49  mov     rdx, 4000000000000800h; unsigned __int64
0x1800dea53  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800dea5a  jz      loc_1800DF395
0x1800dea60  mov     rax, cs:qword_180169748
0x1800dea67  and     rax, rdx
0x1800dea6a  cmp     cs:qword_180169748, rax
0x1800dea71  jnz     loc_1800DF395
0x1800dea77  lea     rcx, [rbp+830h+var_750]; unsigned __int16 *
0x1800dea7e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800dea83  lea     rcx, [rbp+830h+var_750]
0x1800dea8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dea8e  inc     rax
0x1800dea91  cmp     [rcx+rax*2], r12w
0x1800dea96  jnz     short loc_1800DEA8E
0x1800dea98  lea     ecx, [rax+rax]
0x1800dea9b  lea     rax, [rbp+830h+var_750]
0x1800deaa2  jmp     loc_1800DE9FD
0x1800deaa7  lea     rdi, [r15+8]
0x1800deaab  xor     edx, edx
0x1800deaad  mov     rax, [rdi]
0x1800deab0  mov     rcx, rdi
0x1800deab3  mov     rax, [rax+70h]
0x1800deab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deabc  mov     ebx, eax
0x1800deabe  test    eax, eax
0x1800deac0  jns     short loc_1800DEB36
0x1800deac2  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800deac9  mov     [rsp+930h+var_8B8], r12d
0x1800deace  mov     [rsp+930h+var_8C0], eax
0x1800dead2  jz      loc_1800DF395
0x1800dead8  mov     rdx, 4000000000000800h; unsigned __int64
0x1800deae2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800deae9  jz      loc_1800DF395
0x1800deaef  mov     rax, cs:qword_180169748
0x1800deaf6  and     rax, rdx
0x1800deaf9  cmp     cs:qword_180169748, rax
0x1800deb00  jnz     loc_1800DF395
0x1800deb06  lea     rcx, [rbp+830h+var_6D0]; unsigned __int16 *
0x1800deb0d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800deb12  lea     rcx, [rbp+830h+var_6D0]
0x1800deb19  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800deb1d  inc     rax
0x1800deb20  cmp     [rcx+rax*2], r12w
0x1800deb25  jnz     short loc_1800DEB1D
0x1800deb27  lea     ecx, [rax+rax]
0x1800deb2a  lea     rax, [rbp+830h+var_6D0]
0x1800deb31  jmp     loc_1800DE9FD
0x1800deb36  mov     rax, [rdi]
0x1800deb39  lea     rdx, [rbp+830h+var_898]
0x1800deb3d  mov     rcx, rdi
0x1800deb40  mov     rax, [rax+38h]
0x1800deb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deb49  mov     ebx, eax
0x1800deb4b  test    eax, eax
0x1800deb4d  jns     short loc_1800DEBC3
0x1800deb4f  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800deb56  mov     [rsp+930h+var_8B8], r12d
0x1800deb5b  mov     [rsp+930h+var_8C0], eax
0x1800deb5f  jz      loc_1800DF395
0x1800deb65  mov     rdx, 4000000000000800h; unsigned __int64
0x1800deb6f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800deb76  jz      loc_1800DF395
0x1800deb7c  mov     rax, cs:qword_180169748
0x1800deb83  and     rax, rdx
0x1800deb86  cmp     cs:qword_180169748, rax
0x1800deb8d  jnz     loc_1800DF395
0x1800deb93  lea     rcx, [rbp+830h+var_650]; unsigned __int16 *
0x1800deb9a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800deb9f  lea     rcx, [rbp+830h+var_650]
0x1800deba6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800debaa  inc     rax
0x1800debad  cmp     [rcx+rax*2], r12w
0x1800debb2  jnz     short loc_1800DEBAA
0x1800debb4  lea     ecx, [rax+rax]
0x1800debb7  lea     rax, [rbp+830h+var_650]
0x1800debbe  jmp     loc_1800DE9FD
0x1800debc3  mov     r13d, 13h
0x1800debc9  mov     eax, r12d
0x1800debcc  mov     word ptr [rbp+830h+var_890], r13w
0x1800debd1  lea     esi, [r13-12h]
0x1800debd5  mov     dword ptr [rbp+830h+var_890+8], eax
0x1800debd8  cmp     eax, [rbp+830h+var_898]
0x1800debdb  jnb     loc_1800DEE0B
0x1800debe1  mov     rcx, [rbp+830h+var_8A0]
0x1800debe5  test    rcx, rcx
0x1800debe8  jz      short loc_1800DEBFA
0x1800debea  mov     rax, [rcx]
0x1800debed  mov     rax, [rax+10h]
0x1800debf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800debf6  mov     [rbp+830h+var_8A0], r12
0x1800debfa  mov     rax, [rdi]
0x1800debfd  lea     r8, [rbp+830h+var_8A0]
0x1800dec01  movups  xmm0, xmmword ptr [rbp+830h+var_890]
0x1800dec05  lea     rdx, [rbp+830h+var_870]
0x1800dec09  mov     rcx, rdi
0x1800dec0c  movsd   xmm1, qword ptr [rbp+830h+var_890+10h]
0x1800dec11  mov     rax, [rax+40h]
0x1800dec15  movaps  [rbp+830h+var_870], xmm0
0x1800dec19  movsd   [rbp+830h+var_860], xmm1
0x1800dec1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dec23  mov     ebx, eax
0x1800dec25  test    eax, eax
0x1800dec27  js      loc_1800DED97
0x1800dec2d  mov     rcx, [rbp+830h+bstrString]; bstrString
0x1800dec31  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800dec36  mov     rcx, [rbp+830h+var_8A0]
0x1800dec3a  lea     rdx, [rbp+830h+bstrString]
0x1800dec3e  mov     [rbp+830h+bstrString], r12
0x1800dec42  mov     rax, [rcx]
0x1800dec45  mov     rax, [rax+0A0h]
0x1800dec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dec51  mov     ebx, eax
0x1800dec53  test    eax, eax
0x1800dec55  js      loc_1800DED23
0x1800dec5b  mov     rdx, [rbp+830h+bstrString]; unsigned __int16 *
0x1800dec5f  mov     rcx, [rbp+830h+var_8A0]; struct IDataCollectorSet *
0x1800dec63  call    ?PlaiSetLegacyCreds@@YAJPEAUIDataCollectorSet@@PEAG@Z; PlaiSetLegacyCreds(IDataCollectorSet *,ushort *)
0x1800dec68  test    eax, eax
0x1800dec6a  js      short loc_1800DEC92
0x1800dec6c  mov     rcx, [rbp+830h+var_8A0]
0x1800dec70  mov     r9d, esi
0x1800dec73  mov     rdx, [rbp+830h+bstrString]
0x1800dec77  xor     r8d, r8d
0x1800dec7a  mov     [rsp+930h+phkResult], r12
0x1800dec7f  mov     rax, [rcx]
0x1800dec82  mov     rax, [rax+1E0h]
0x1800dec89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dec8e  test    eax, eax
0x1800dec90  jns     short loc_1800DECA5
0x1800dec92  mov     rdx, [rbp+830h+bstrString]; unsigned __int16 *
0x1800dec96  mov     rcx, [rbp+830h+var_8A0]; struct IDataCollectorSet *
0x1800dec9a  call    ?PlaDumpDataCollectorSetToFile@@YAJPEAUIDataCollectorSet@@PEAG@Z; PlaDumpDataCollectorSetToFile(IDataCollectorSet *,ushort *)
0x1800dec9f  mov     ebx, eax
0x1800deca1  test    eax, eax
0x1800deca3  js      short loc_1800DECAF
0x1800deca5  mov     eax, dword ptr [rbp+830h+var_890+8]
0x1800deca8  add     eax, esi
0x1800decaa  jmp     loc_1800DEBD5
0x1800decaf  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800decb6  mov     [rsp+930h+var_8B8], r12d
0x1800decbb  mov     [rsp+930h+var_8C0], eax
0x1800decbf  jz      loc_1800DF395
0x1800decc5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800deccf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800decd6  jz      loc_1800DF395
0x1800decdc  mov     rax, cs:qword_180169748
0x1800dece3  and     rax, rdx
0x1800dece6  cmp     cs:qword_180169748, rax
0x1800deced  jnz     loc_1800DF395
0x1800decf3  lea     rcx, [rbp+830h+var_5D0]; unsigned __int16 *
0x1800decfa  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800decff  lea     rcx, [rbp+830h+var_5D0]
0x1800ded06  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ded0a  inc     rax
0x1800ded0d  cmp     [rcx+rax*2], r12w
0x1800ded12  jnz     short loc_1800DED0A
0x1800ded14  lea     ecx, [rax+rax]
0x1800ded17  lea     rax, [rbp+830h+var_5D0]
0x1800ded1e  jmp     loc_1800DF333
0x1800ded23  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800ded2a  mov     [rsp+930h+var_8B8], r12d
0x1800ded2f  mov     [rsp+930h+var_8C0], eax
0x1800ded33  jz      loc_1800DF395
0x1800ded39  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ded43  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ded4a  jz      loc_1800DF395
0x1800ded50  mov     rax, cs:qword_180169748
0x1800ded57  and     rax, rdx
0x1800ded5a  cmp     cs:qword_180169748, rax
0x1800ded61  jnz     loc_1800DF395
0x1800ded67  lea     rcx, [rbp+830h+var_550]; unsigned __int16 *
0x1800ded6e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ded73  lea     rcx, [rbp+830h+var_550]
0x1800ded7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ded7e  inc     rax
0x1800ded81  cmp     [rcx+rax*2], r12w
0x1800ded86  jnz     short loc_1800DED7E
0x1800ded88  lea     ecx, [rax+rax]
0x1800ded8b  lea     rax, [rbp+830h+var_550]
0x1800ded92  jmp     loc_1800DF333
0x1800ded97  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800ded9e  mov     [rsp+930h+var_8B8], r12d
0x1800deda3  mov     [rsp+930h+var_8C0], eax
0x1800deda7  jz      loc_1800DF395
  ... truncated ...
```
