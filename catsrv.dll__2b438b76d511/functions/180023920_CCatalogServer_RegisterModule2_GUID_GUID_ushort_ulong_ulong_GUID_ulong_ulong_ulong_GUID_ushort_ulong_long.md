# CCatalogServer::RegisterModule2(_GUID,_GUID,ushort * *,ulong,ulong,_GUID *,ulong,ulong * *,ulong *,_GUID * *,ushort * * *,ulong * *,long * *)

- ea: `0x180023920`
- end: `0x1800240ee`
- name: `?RegisterModule2@CCatalogServer@@UEAAJU_GUID@@0PEAPEAGKKPEAU2@KPEAPEAKPEAKPEAPEAU2@PEAPEAPEAG3PEAPEAJ@Z`
- size: `1998`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, struct _GUID *, struct _GUID *, unsigned __int16 **, unsigned int, unsigned int, struct _GUID *, unsigned int, unsigned int **, unsigned int *, struct _GUID **, unsigned __int16 ***, unsigned int **, int **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18001ece0`
- `0x18002117c`
- `0x180021238`
- `0x1800212f4`
- `0x180023920`
- `0x18002967c`
- `0x180029c14`
- `0x18002f158`
- `0x180031b4c`
- `0x180031cdc`
- `0x1800554f6`
- `0x18005551a`
- `0x180055550`
- `0x180055610`
- `0x180058010`

## import_xrefs

- `comsvcs!GetObjectContext` at `0x180024013`
- `comsvcs!GetObjectContext` at `0x1800566ed`
- `comsvcs!GetObjectContext` at `0x180024013`
- `comsvcs!GetObjectContext` at `0x1800566ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002408a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002409e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005673b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005674f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056779`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002408a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002409e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005673b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005674f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056779`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023f55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023bb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023d3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023bb5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023d3f`

## pseudocode

```c
__int64 __fastcall CCatalogServer::RegisterModule2(
        CCatalogServer *this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 **a4,
        unsigned int a5,
        unsigned int a6,
        struct _GUID *a7,
        unsigned int a8,
        unsigned int **a9,
        unsigned int *a10,
        struct _GUID **a11,
        unsigned __int16 ***a12,
        unsigned int **a13,
        const void **a14)
{
  __int64 *v15; // r14
  unsigned int v16; // edi
  SIZE_T v17; // r12
  __int64 v18; // rax
  void *v19; // rsp
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  unsigned __int16 **v25; // r8
  unsigned int v26; // r14d
  unsigned int v27; // ecx
  unsigned __int16 **v28; // r9
  int *v29; // r10
  unsigned __int16 *v30; // rdx
  LPVOID *ppv; // rax
  LPVOID v32; // rcx
  __int64 v33; // rax
  unsigned __int64 v34; // rdi
  unsigned int *v35; // rax
  unsigned int v36; // r8d
  unsigned int v37; // r9d
  unsigned int v38; // edx
  _DWORD *v39; // rcx
  __int64 v40; // rax
  int v41; // edi
  int ObjectContext; // eax
  unsigned int j; // esi
  __int64 v44; // [rsp+0h] [rbp-80h] BYREF
  int Instance; // [rsp+80h] [rbp+0h] BYREF
  unsigned int v46; // [rsp+84h] [rbp+4h] BYREF
  int v47; // [rsp+88h] [rbp+8h] BYREF
  __int64 *v48; // [rsp+90h] [rbp+10h]
  __int64 v49; // [rsp+98h] [rbp+18h] BYREF
  LPVOID v50; // [rsp+A0h] [rbp+20h] BYREF
  int v51; // [rsp+A8h] [rbp+28h]
  unsigned int v52[2]; // [rsp+B0h] [rbp+30h] BYREF
  CCatalogServer *v53; // [rsp+B8h] [rbp+38h]
  LPVOID pv; // [rsp+C0h] [rbp+40h] BYREF
  LPVOID v55; // [rsp+C8h] [rbp+48h] BYREF
  LPVOID v56; // [rsp+D0h] [rbp+50h] BYREF
  LPVOID v57; // [rsp+D8h] [rbp+58h] BYREF
  LPVOID v58; // [rsp+E0h] [rbp+60h] BYREF
  unsigned int v59; // [rsp+E8h] [rbp+68h]
  unsigned int v60; // [rsp+ECh] [rbp+6Ch]
  unsigned int v61; // [rsp+F0h] [rbp+70h]
  unsigned int v62; // [rsp+F4h] [rbp+74h]
  unsigned int v63; // [rsp+F8h] [rbp+78h]
  unsigned int i; // [rsp+FCh] [rbp+7Ch]
  unsigned int v65; // [rsp+100h] [rbp+80h]
  unsigned int v66; // [rsp+104h] [rbp+84h]
  unsigned int v67; // [rsp+108h] [rbp+88h]
  unsigned int v68; // [rsp+10Ch] [rbp+8Ch]
  unsigned int v69; // [rsp+110h] [rbp+90h]
  unsigned int v70; // [rsp+114h] [rbp+94h]
  unsigned int v71; // [rsp+118h] [rbp+98h]
  unsigned int v72; // [rsp+11Ch] [rbp+9Ch]
  unsigned int v73; // [rsp+120h] [rbp+A0h]
  unsigned __int16 **v74; // [rsp+128h] [rbp+A8h]
  int *v75; // [rsp+130h] [rbp+B0h]
  LPVOID v76; // [rsp+138h] [rbp+B8h]
  __int128 v77; // [rsp+140h] [rbp+C0h] BYREF
  __int128 v78; // [rsp+150h] [rbp+D0h] BYREF
  int v79; // [rsp+160h] [rbp+E0h]
  int v80; // [rsp+164h] [rbp+E4h]
  int v81[4]; // [rsp+170h] [rbp+F0h] BYREF
  int v82[4]; // [rsp+180h] [rbp+100h] BYREF

  v48 = &v44;
  v74 = a4;
  *(_QWORD *)&v77 = a3;
  *(_QWORD *)&v78 = a2;
  v53 = this;
  Instance = 0;
  v49 = 0;
  if ( !*((_DWORD *)this + 26) )
    return 2148598828LL;
  v51 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a11 )
    *a11 = 0;
  if ( a12 )
    *a12 = 0;
  v15 = (__int64 *)a13;
  if ( a13 )
    *a13 = 0;
  if ( a14 )
    *a14 = 0;
  v46 = 0;
  v56 = 0;
  v50 = 0;
  v57 = 0;
  v58 = 0;
  v47 = 0;
  v16 = a5;
  pv = 0;
  v55 = 0;
  v76 = 0;
  v17 = 4LL * a5;
  v18 = v17 + 15;
  if ( v17 + 15 < v17 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  v75 = &Instance;
  v52[0] = 0;
  Instance = CheckForManagedModules(v74, &Instance, a5, v52);
  if ( Instance < 0 )
  {
    v65 = Instance;
    local_unwind_0(v48, &loc_180023A9F);
    return v65;
  }
  if ( v52[0] )
  {
    if ( a8 )
    {
      v79 = -2147467231;
      local_unwind_0(v48, &loc_180023AD8);
      return 2147500065LL;
    }
    v20 = 8LL * v52[0];
    v21 = v20 + 15;
    if ( v20 + 15 < v20 )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
    v23 = alloca(v22);
    v24 = alloca(v22);
    v25 = (unsigned __int16 **)&Instance;
    *(_QWORD *)v52 = &Instance;
    v26 = 0;
    v66 = 0;
    v16 = 0;
    v67 = 0;
    v27 = 0;
    v68 = 0;
    v28 = v74;
    v29 = v75;
    while ( v27 < a5 )
    {
      v30 = v28[v27];
      if ( v29[v27] )
      {
        *((_QWORD *)&Instance + v26++) = v30;
        v66 = v26;
      }
      else
      {
        v28[v16++] = v30;
        v67 = v16;
      }
      v68 = ++v27;
    }
    if ( (a6 & 0x20) != 0 && !*((_QWORD *)v53 + 18) )
    {
      Instance = CoCreateInstance(&CLSID_COMComponentRegistrar, 0, 3u, &IID_IRegister2, (LPVOID *)v53 + 18);
      if ( Instance < 0 )
      {
        v69 = Instance;
        local_unwind_0(v48, &loc_180023BDF);
        return v69;
      }
      v25 = *(unsigned __int16 ***)v52;
    }
    *(_OWORD *)v81 = *(_OWORD *)v77;
    *(_OWORD *)v82 = *(_OWORD *)v78;
    Instance = AttemptToInstallManagedAssemblies(
                 (int)v82,
                 (int)v81,
                 (int)&v47,
                 a6,
                 v26,
                 v25,
                 *((_QWORD *)v53 + 18),
                 (__int64)a10,
                 (__int64)&pv,
                 (__int64)a11,
                 (__int64)a12,
                 (__int64)a13,
                 (__int64)a14);
    if ( Instance < 0 )
    {
      v70 = Instance;
      local_unwind_0(v48, &loc_180023CA5);
      return v70;
    }
    v15 = (__int64 *)a13;
  }
  if ( v16 )
  {
    Instance = TxInitialize();
    if ( Instance < 0 )
    {
      v71 = Instance;
      local_unwind_0(v48, &loc_180023CF5);
      return v71;
    }
    UTSemReadWrite::LockWrite((UTSemReadWrite *)&g_semRW);
    v51 = 1;
    ppv = (LPVOID *)((char *)v53 + 144);
    v53 = (CCatalogServer *)ppv;
    if ( !*ppv )
    {
      Instance = CoCreateInstance(&CLSID_COMComponentRegistrar, 0, 3u, &IID_IRegister2, ppv);
      if ( Instance < 0 )
      {
        v72 = Instance;
        local_unwind_0(v48, &loc_180023D69);
        return v72;
      }
      ppv = (LPVOID *)v53;
    }
    v32 = *ppv;
    v33 = *(_QWORD *)*ppv;
    v77 = *(_OWORD *)v77;
    v78 = *(_OWORD *)v78;
    v52[0] = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, unsigned __int16 **, unsigned int, unsigned int, struct _GUID *, unsigned int, LPVOID *, unsigned int *, LPVOID *, LPVOID *, LPVOID *, LPVOID *))(v33 + 64))(
               v32,
               &v78,
               &v77,
               v74,
               v16,
               a6,
               a7,
               a8,
               &v55,
               &v46,
               &v56,
               &v50,
               &v57,
               &v58);
    v34 = (unsigned int)v47;
    Instance = AppendInstallArrays<_GUID>(
                 (__int64)*a11,
                 (const void **)&v56,
                 (unsigned int)v47,
                 v46,
                 (const void **)a11);
    if ( Instance < 0 )
    {
      v73 = Instance;
      local_unwind_0(v48, &loc_180023E63);
      return v73;
    }
    Instance = AppendInstallArrays<unsigned short *>((__int64)*a12, (const void **)&v50, v34, v46, (const void **)a12);
    if ( Instance < 0 )
    {
      v59 = Instance;
      local_unwind_0(v48, &loc_180023EA8);
      return v59;
    }
    Instance = AppendInstallArrays<long>(*v15, (const void **)&v57, v34, v46, (const void **)v15);
    if ( Instance < 0 )
    {
      v60 = Instance;
      local_unwind_0(v48, &loc_180023EE9);
      return v60;
    }
    Instance = AppendInstallArrays<long>((__int64)*a14, (const void **)&v58, v34, v46, a14);
    if ( Instance < 0 )
    {
      v61 = Instance;
      local_unwind_0(v48, &loc_180023F31);
      return v61;
    }
    if ( a10 )
      *a10 += v46;
    Instance = v52[0];
  }
  if ( a9 )
  {
    v35 = (unsigned int *)CoTaskMemAlloc(v17);
    *a9 = v35;
    if ( !v35 )
    {
      v80 = -2147024882;
      local_unwind_0(v48, &loc_180023F7E);
      return 2147942414LL;
    }
    memset_0(v35, 0, v17);
    v36 = 0;
    v62 = 0;
    v37 = 0;
    v63 = 0;
    v38 = 0;
    for ( i = 0; v38 < a5; i = v38 )
    {
      if ( v75[v38] )
      {
        v39 = pv;
        if ( !pv )
          goto LABEL_67;
        v40 = v36++;
        v62 = v36;
      }
      else
      {
        v39 = v55;
        if ( !v55 )
          goto LABEL_67;
        v40 = v37++;
        v63 = v37;
      }
      (*a9)[v38] = v39[v40];
LABEL_67:
      ++v38;
    }
  }
  if ( v51 )
    UTSemReadWrite::UnlockWrite((UTSemReadWrite *)&g_semRW);
  v41 = Instance;
  ObjectContext = GetObjectContext(&v49);
  if ( v41 < 0 )
  {
    if ( ObjectContext < 0 )
    {
      if ( ObjectContext == -2147164156 )
        ObjectContext = 0;
    }
    else
    {
      ObjectContext = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
    }
    if ( ObjectContext < 0 )
      v41 = ObjectContext;
  }
  else
  {
    v41 = ObjectContext;
    if ( ObjectContext < 0 )
    {
      if ( ObjectContext == -2147164156 )
        v41 = 0;
    }
    else
    {
      v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
    }
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v55);
  CoTaskMemFree(v76);
  CoTaskMemFree(v56);
  CoTaskMemFree(v57);
  CoTaskMemFree(v58);
  if ( v50 )
  {
    for ( j = 0; j < v47; ++j )
      CoTaskMemFree(*((LPVOID *)v50 + j));
    CoTaskMemFree(v50);
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x180023920  push    rbp
0x180023922  push    rbx
0x180023923  push    rsi
0x180023924  push    rdi
0x180023925  push    r12
0x180023927  push    r13
0x180023929  push    r14
0x18002392b  push    r15
0x18002392d  sub     rsp, 1A8h
0x180023934  lea     rbp, [rsp+80h]
0x18002393c  mov     rax, cs:__security_cookie
0x180023943  xor     rax, rbp
0x180023946  mov     [rbp+160h+var_50], rax
0x18002394d  mov     [rbp+160h+var_150], rsp
0x180023951  mov     [rbp+160h+var_B8], r9
0x180023958  mov     qword ptr [rbp+160h+var_A0], r8
0x18002395f  mov     qword ptr [rbp+160h+var_90], rdx
0x180023966  mov     [rbp+160h+var_128], rcx
0x18002396a  xor     ebx, ebx
0x18002396c  mov     dword ptr [rbp+160h+var_160], ebx
0x18002396f  mov     [rbp+160h+var_148], rbx
0x180023973  cmp     [rcx+68h], ebx
0x180023976  jnz     short loc_1800239A0
0x180023978  mov     eax, 8011042Ch
0x18002397d  mov     rcx, [rbp+160h+var_50]
0x180023984  xor     rcx, rbp; StackCookie
0x180023987  call    __security_check_cookie
0x18002398c  lea     rsp, [rbp+128h]
0x180023993  pop     r15
0x180023995  pop     r14
0x180023997  pop     r13
0x180023999  pop     r12
0x18002399b  pop     rdi
0x18002399c  pop     rsi
0x18002399d  pop     rbx
0x18002399e  pop     rbp
0x18002399f  retn
0x1800239a0  mov     [rbp+160h+var_138], ebx
0x1800239a3  mov     r15, [rbp+160h+arg_40]
0x1800239aa  test    r15, r15
0x1800239ad  jz      short loc_1800239B2
0x1800239af  mov     [r15], rbx
0x1800239b2  mov     rsi, [rbp+160h+arg_48]
0x1800239b9  test    rsi, rsi
0x1800239bc  jz      short loc_1800239C0
0x1800239be  mov     [rsi], ebx
0x1800239c0  mov     rax, [rbp+160h+arg_50]
0x1800239c7  test    rax, rax
0x1800239ca  jz      short loc_1800239CF
0x1800239cc  mov     [rax], rbx
0x1800239cf  mov     r13, [rbp+160h+arg_58]
0x1800239d6  test    r13, r13
0x1800239d9  jz      short loc_1800239DF
0x1800239db  mov     [r13+0], rbx
0x1800239df  mov     r14, [rbp+160h+arg_60]
0x1800239e6  test    r14, r14
0x1800239e9  jz      short loc_1800239EE
0x1800239eb  mov     [r14], rbx
0x1800239ee  mov     rax, [rbp+160h+arg_68]
0x1800239f5  test    rax, rax
0x1800239f8  jz      short loc_1800239FD
0x1800239fa  mov     [rax], rbx
0x1800239fd  mov     dword ptr [rbp+160h+var_160+4], ebx
0x180023a00  mov     [rbp+160h+var_110], rbx
0x180023a04  mov     [rbp+160h+var_140], rbx
0x180023a08  mov     [rbp+160h+var_108], rbx
0x180023a0c  mov     [rbp+160h+var_100], rbx
0x180023a10  mov     [rbp+160h+var_158], ebx
0x180023a13  mov     edi, [rbp+160h+arg_20]
0x180023a19  mov     [rbp+160h+pv], rbx
0x180023a1d  mov     [rbp+160h+var_118], rbx
0x180023a21  mov     [rbp+160h+var_A8], rbx
0x180023a28  mov     r12d, edi
0x180023a2b  shl     r12, 2
0x180023a2f  lea     rax, [r12+0Fh]
0x180023a34  cmp     rax, r12
0x180023a37  ja      short loc_180023A43
0x180023a39  mov     rax, 0FFFFFFFFFFFFFF0h
0x180023a43  and     rax, 0FFFFFFFFFFFFFFF0h
0x180023a47  call    _alloca_probe
0x180023a4c  sub     rsp, rax
0x180023a4f  lea     rax, [rsp+1E0h+var_160]
0x180023a57  mov     [rbp+160h+var_B0], rax
0x180023a5e  mov     [rbp+160h+var_130], ebx
0x180023a61  lea     r9, [rbp+160h+var_130]; unsigned int *
0x180023a65  mov     r8d, [rbp+160h+arg_20]; unsigned int
0x180023a6c  mov     rdx, rax; int *
0x180023a6f  mov     rcx, [rbp+160h+var_B8]; unsigned __int16 **
0x180023a76  call    ?CheckForManagedModules@@YAJPEAPEAGPEAHKPEAK@Z; CheckForManagedModules(ushort * *,int *,ulong,ulong *)
0x180023a7b  mov     dword ptr [rbp+160h+var_160], eax
0x180023a7e  mov     eax, dword ptr [rbp+160h+var_160]
0x180023a81  test    eax, eax
0x180023a83  jns     short loc_180023AAA
0x180023a85  mov     eax, dword ptr [rbp+160h+var_160]
0x180023a88  mov     [rbp+160h+var_E0], eax
0x180023a8e  lea     rdx, loc_180023A9F
0x180023a95  mov     rcx, [rbp+160h+var_150]
0x180023a99  call    _local_unwind_0
0x180023a9e  nop
0x180023a9f  mov     eax, [rbp+160h+var_E0]
0x180023aa5  jmp     loc_18002397D
0x180023aaa  mov     eax, [rbp+160h+var_130]
0x180023aad  test    eax, eax
0x180023aaf  jz      loc_180023CB7
0x180023ab5  cmp     [rbp+160h+arg_38], ebx
0x180023abb  jz      short loc_180023AE2
0x180023abd  mov     [rbp+160h+var_80], 80004021h
0x180023ac7  lea     rdx, loc_180023AD8
0x180023ace  mov     rcx, [rbp+160h+var_150]
0x180023ad2  call    _local_unwind_0
0x180023ad7  nop
0x180023ad8  mov     eax, 80004021h
0x180023add  jmp     loc_18002397D
0x180023ae2  test    eax, eax
0x180023ae4  jz      loc_180023CB7
0x180023aea  shl     rax, 3
0x180023aee  lea     rcx, [rax+0Fh]
0x180023af2  cmp     rcx, rax
0x180023af5  ja      short loc_180023B01
0x180023af7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180023b01  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180023b05  mov     rax, rcx
0x180023b08  call    _alloca_probe
0x180023b0d  sub     rsp, rcx
0x180023b10  lea     r8, [rsp+1E0h+var_160]
0x180023b18  mov     qword ptr [rbp+160h+var_130], r8
0x180023b1c  mov     r14d, ebx
0x180023b1f  mov     [rbp+160h+var_DC], ebx
0x180023b25  mov     edi, ebx
0x180023b27  mov     [rbp+160h+var_D8], ebx
0x180023b2d  mov     ecx, ebx
0x180023b2f  mov     [rbp+160h+var_D4], ebx
0x180023b35  mov     r9, [rbp+160h+var_B8]
0x180023b3c  mov     r10, [rbp+160h+var_B0]
0x180023b43  cmp     ecx, [rbp+160h+arg_20]
0x180023b49  jnb     short loc_180023B84
0x180023b4b  mov     eax, ecx
0x180023b4d  mov     rdx, [r9+rax*8]
0x180023b51  mov     eax, ecx
0x180023b53  cmp     [r10+rax*4], ebx
0x180023b57  jz      short loc_180023B6C
0x180023b59  mov     eax, r14d
0x180023b5c  mov     [r8+rax*8], rdx
0x180023b60  inc     r14d
0x180023b63  mov     [rbp+160h+var_DC], r14d
0x180023b6a  jmp     short loc_180023B7A
0x180023b6c  mov     eax, edi
0x180023b6e  mov     [r9+rax*8], rdx
0x180023b72  inc     edi
0x180023b74  mov     [rbp+160h+var_D8], edi
0x180023b7a  inc     ecx
0x180023b7c  mov     [rbp+160h+var_D4], ecx
0x180023b82  jmp     short loc_180023B43
0x180023b84  test    byte ptr [rbp+160h+arg_28], 20h
0x180023b8b  jz      short loc_180023BEE
0x180023b8d  mov     rax, [rbp+160h+var_128]
0x180023b91  add     rax, 90h
0x180023b97  cmp     [rax], rbx
0x180023b9a  jnz     short loc_180023BEE
0x180023b9c  mov     [rsp+1E0h+ppv], rax; ppv
0x180023ba1  lea     r9, IID_IRegister2; riid
0x180023ba8  xor     edx, edx; pUnkOuter
0x180023baa  lea     r8d, [rdx+3]; dwClsContext
0x180023bae  lea     rcx, CLSID_COMComponentRegistrar; rclsid
0x180023bb5  call    cs:__imp_CoCreateInstance
0x180023bbb  mov     dword ptr [rbp+160h+var_160], eax
0x180023bbe  mov     eax, dword ptr [rbp+160h+var_160]
0x180023bc1  test    eax, eax
0x180023bc3  jns     short loc_180023BEA
0x180023bc5  mov     eax, dword ptr [rbp+160h+var_160]
0x180023bc8  mov     [rbp+160h+var_D0], eax
0x180023bce  lea     rdx, loc_180023BDF
0x180023bd5  mov     rcx, [rbp+160h+var_150]
0x180023bd9  call    _local_unwind_0
0x180023bde  nop
0x180023bdf  mov     eax, [rbp+160h+var_D0]
0x180023be5  jmp     loc_18002397D
0x180023bea  mov     r8, qword ptr [rbp+160h+var_130]
0x180023bee  mov     rax, qword ptr [rbp+160h+var_A0]
0x180023bf5  movups  xmm0, xmmword ptr [rax]
0x180023bf8  movdqu  xmmword ptr [rbp+160h+var_70], xmm0
0x180023c00  mov     rax, qword ptr [rbp+160h+var_90]
0x180023c07  movups  xmm1, xmmword ptr [rax]
0x180023c0a  movdqu  xmmword ptr [rbp+160h+var_60], xmm1
0x180023c12  mov     rax, [rbp+160h+arg_68]
0x180023c19  mov     [rsp+1E0h+var_180], rax; __int64
0x180023c1e  mov     rax, [rbp+160h+arg_60]
0x180023c25  mov     [rsp+1E0h+var_188], rax; __int64
0x180023c2a  mov     [rsp+1E0h+var_190], r13; __int64
0x180023c2f  mov     rax, [rbp+160h+arg_50]
0x180023c36  mov     [rsp+1E0h+var_198], rax; __int64
0x180023c3b  lea     rax, [rbp+160h+pv]
0x180023c3f  mov     [rsp+1E0h+var_1A0], rax; __int64
0x180023c44  mov     [rsp+1E0h+var_1A8], rsi; __int64
0x180023c49  mov     rax, [rbp+160h+var_128]
0x180023c4d  mov     rax, [rax+90h]
0x180023c54  mov     [rsp+1E0h+var_1B0], rax; __int64
0x180023c59  mov     [rsp+1E0h+var_1B8], r8; unsigned __int16 **
0x180023c5e  mov     dword ptr [rsp+1E0h+ppv], r14d; unsigned int
0x180023c63  mov     r9d, [rbp+160h+arg_28]; int
0x180023c6a  lea     r8, [rbp+160h+var_158]; int
0x180023c6e  lea     rdx, [rbp+160h+var_70]; int
0x180023c75  lea     rcx, [rbp+160h+var_60]; int
0x180023c7c  call    AttemptToInstallManagedAssemblies
0x180023c81  mov     dword ptr [rbp+160h+var_160], eax
0x180023c84  mov     eax, dword ptr [rbp+160h+var_160]
0x180023c87  test    eax, eax
0x180023c89  jns     short loc_180023CB0
0x180023c8b  mov     eax, dword ptr [rbp+160h+var_160]
0x180023c8e  mov     [rbp+160h+var_CC], eax
0x180023c94  lea     rdx, loc_180023CA5
0x180023c9b  mov     rcx, [rbp+160h+var_150]
0x180023c9f  call    _local_unwind_0
0x180023ca4  nop
0x180023ca5  mov     eax, [rbp+160h+var_CC]
0x180023cab  jmp     loc_18002397D
0x180023cb0  mov     r14, [rbp+160h+arg_60]
0x180023cb7  test    edi, edi
0x180023cb9  jz      loc_180023F49
0x180023cbf  call    ?TxInitialize@@YAJXZ; TxInitialize(void)
0x180023cc4  mov     dword ptr [rbp+160h+var_160], eax
0x180023cc7  mov     eax, dword ptr [rbp+160h+var_160]
0x180023cca  test    eax, eax
0x180023ccc  jns     short loc_180023D00
0x180023cce  mov     eax, dword ptr [rbp+160h+var_160]
0x180023cd1  cmp     eax, 8007000Eh
0x180023cd6  jz      short loc_180023CDB
0x180023cd8  mov     eax, dword ptr [rbp+160h+var_160]
0x180023cdb  mov     eax, dword ptr [rbp+160h+var_160]
0x180023cde  mov     [rbp+160h+var_C8], eax
0x180023ce4  lea     rdx, loc_180023CF5
0x180023ceb  mov     rcx, [rbp+160h+var_150]
0x180023cef  call    _local_unwind_0
0x180023cf4  nop
0x180023cf5  mov     eax, [rbp+160h+var_C8]
0x180023cfb  jmp     loc_18002397D
0x180023d00  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x180023d07  call    ?LockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockWrite(void)
0x180023d0c  mov     [rbp+160h+var_138], 1
0x180023d13  mov     rax, [rbp+160h+var_128]
0x180023d17  add     rax, 90h
0x180023d1d  mov     [rbp+160h+var_128], rax
0x180023d21  cmp     [rax], rbx
0x180023d24  jnz     short loc_180023D78
0x180023d26  mov     [rsp+1E0h+ppv], rax; ppv
0x180023d2b  lea     r9, IID_IRegister2; riid
0x180023d32  xor     edx, edx; pUnkOuter
0x180023d34  lea     r8d, [rdx+3]; dwClsContext
0x180023d38  lea     rcx, CLSID_COMComponentRegistrar; rclsid
0x180023d3f  call    cs:__imp_CoCreateInstance
0x180023d45  mov     dword ptr [rbp+160h+var_160], eax
0x180023d48  mov     eax, dword ptr [rbp+160h+var_160]
0x180023d4b  test    eax, eax
0x180023d4d  jns     short loc_180023D74
0x180023d4f  mov     eax, dword ptr [rbp+160h+var_160]
0x180023d52  mov     [rbp+160h+var_C4], eax
0x180023d58  lea     rdx, loc_180023D69
0x180023d5f  mov     rcx, [rbp+160h+var_150]
0x180023d63  call    _local_unwind_0
0x180023d68  nop
0x180023d69  mov     eax, [rbp+160h+var_C4]
0x180023d6f  jmp     loc_18002397D
0x180023d74  mov     rax, [rbp+160h+var_128]
0x180023d78  mov     rcx, [rax]
0x180023d7b  mov     rax, [rcx]
0x180023d7e  mov     rdx, qword ptr [rbp+160h+var_A0]
0x180023d85  movups  xmm0, xmmword ptr [rdx]
0x180023d88  movdqu  [rbp+160h+var_A0], xmm0
0x180023d90  mov     rdx, qword ptr [rbp+160h+var_90]
0x180023d97  movups  xmm1, xmmword ptr [rdx]
0x180023d9a  movdqu  [rbp+160h+var_90], xmm1
0x180023da2  lea     rdx, [rbp+160h+var_100]
0x180023da6  mov     [rsp+1E0h+var_178], rdx
0x180023dab  lea     rdx, [rbp+160h+var_108]
0x180023daf  mov     [rsp+1E0h+var_180], rdx
0x180023db4  lea     rdx, [rbp+160h+var_140]
0x180023db8  mov     [rsp+1E0h+var_188], rdx
0x180023dbd  lea     rdx, [rbp+160h+var_110]
0x180023dc1  mov     [rsp+1E0h+var_190], rdx
0x180023dc6  lea     rdx, [rbp+160h+var_160+4]
0x180023dca  mov     [rsp+1E0h+var_198], rdx
0x180023dcf  lea     rdx, [rbp+160h+var_118]
0x180023dd3  mov     [rsp+1E0h+var_1A0], rdx
0x180023dd8  mov     edx, [rbp+160h+arg_38]
0x180023dde  mov     dword ptr [rsp+1E0h+var_1A8], edx
0x180023de2  mov     rdx, [rbp+160h+arg_30]
0x180023de9  mov     [rsp+1E0h+var_1B0], rdx
0x180023dee  mov     edx, [rbp+160h+arg_28]
0x180023df4  mov     dword ptr [rsp+1E0h+var_1B8], edx
0x180023df8  mov     dword ptr [rsp+1E0h+ppv], edi
0x180023dfc  mov     r9, [rbp+160h+var_B8]
0x180023e03  lea     r8, [rbp+160h+var_A0]
0x180023e0a  lea     rdx, [rbp+160h+var_90]
0x180023e11  mov     rax, [rax+40h]
0x180023e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1a  mov     [rbp+160h+var_130], eax
0x180023e1d  mov     edi, [rbp+160h+var_158]
0x180023e20  mov     r9d, dword ptr [rbp+160h+var_160+4]
0x180023e24  mov     rax, [rbp+160h+arg_50]
0x180023e2b  mov     [rsp+1E0h+ppv], rax
  ... truncated ...
```
