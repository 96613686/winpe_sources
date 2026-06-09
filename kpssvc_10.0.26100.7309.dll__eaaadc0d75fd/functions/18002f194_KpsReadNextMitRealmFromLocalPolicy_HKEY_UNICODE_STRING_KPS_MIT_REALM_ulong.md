# KpsReadNextMitRealmFromLocalPolicy(HKEY__ *,_UNICODE_STRING *,_KPS_MIT_REALM *,ulong *)

- ea: `0x18002f194`
- end: `0x18002f69d`
- name: `?KpsReadNextMitRealmFromLocalPolicy@@YAKPEAUHKEY__@@PEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@PEAK@Z`
- size: `1289`
- prototype: `__int64 __fastcall(HKEY hKey, struct _UNICODE_STRING *, struct _KPS_MIT_REALM *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18002eb50`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18002dbb8`
- `0x18002e7f8`
- `0x18002f194`
- `0x18002f6a4`
- `0x18002f738`
- `0x18003012c`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f641`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f641`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f378`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f334`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f401`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f334`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f401`
- `ntdll!RtlDuplicateUnicodeString` at `0x18002f441`
- `ntdll!RtlDuplicateUnicodeString` at `0x18002f441`
- `ntdll!RtlInitUnicodeString` at `0x18002f42a`
- `ntdll!RtlInitUnicodeString` at `0x18002f42a`
- `ntdll!RtlFreeUnicodeString` at `0x18002f62b`
- `ntdll!RtlFreeUnicodeString` at `0x18002f62b`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18002f498`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18002f498`

## pseudocode

```c
__int64 __fastcall KpsReadNextMitRealmFromLocalPolicy(
        HKEY hKey,
        struct _UNICODE_STRING *a2,
        struct _KPS_MIT_REALM *a3,
        unsigned int *a4)
{
  DWORD v8; // edx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // r8d
  DWORD v12; // edx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // r8d
  _QWORD *v16; // rcx
  int v17; // edx
  void *v18; // rax
  int v19; // eax
  __int128 v20; // xmm1
  __int64 v21; // xmm0_8
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  void *lpMem[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v31; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__usercall *v34)@<rax>(wchar_t *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, void *); // [rsp+C0h] [rbp-40h] BYREF
  int v35; // [rsp+C8h] [rbp-38h]
  const wchar_t *v36; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING *v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+E0h] [rbp-20h]
  int *v39; // [rsp+E8h] [rbp-18h]
  int v40; // [rsp+F0h] [rbp-10h]
  __int64 (__usercall *v41)@<rax>(wchar_t *@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, void *); // [rsp+F8h] [rbp-8h]
  int v42; // [rsp+100h] [rbp+0h]
  const wchar_t *v43; // [rsp+108h] [rbp+8h]
  void **v44; // [rsp+110h] [rbp+10h]
  int v45; // [rsp+118h] [rbp+18h]
  int *v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+128h] [rbp+28h]
  __int64 v48; // [rsp+130h] [rbp+30h]
  int v49; // [rsp+138h] [rbp+38h]
  const wchar_t *v50; // [rsp+140h] [rbp+40h]
  int *v51; // [rsp+148h] [rbp+48h]
  int v52; // [rsp+150h] [rbp+50h]
  int *v53; // [rsp+158h] [rbp+58h]
  int v54; // [rsp+160h] [rbp+60h]
  __int128 v55; // [rsp+168h] [rbp+68h]
  __int128 v56; // [rsp+178h] [rbp+78h]
  __int128 v57; // [rsp+188h] [rbp+88h]
  __int64 v58; // [rsp+198h] [rbp+98h]
  WCHAR Name[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  v49 = 32;
  v29 = 0;
  phkResult = 0;
  v24 = 0;
  v36 = L"KdcNames";
  v25 = 0;
  v39 = &dword_18003492C;
  v37 = &v31;
  v46 = &dword_18003492C;
  v43 = L"KpasswdNames";
  v40 = 0;
  v38 = 7;
  v44 = lpMem;
  v45 = 7;
  v50 = L"RealmFlags";
  v47 = 0;
  v51 = &v24;
  v34 = KpsMitRealmQuery;
  v53 = &v25;
  v41 = KpsMitRealmQuery;
  v35 = 16;
  v58 = 0;
  DestinationString = 0;
  v42 = 16;
  UnicodeString = 0;
  v48 = 0;
  v31 = 0;
  v52 = 4;
  *(_OWORD *)lpMem = 0;
  v54 = 4;
  v27 = 0;
  v28 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids);
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 4) = 0;
  *a2 = 0;
  memset_0(Name, 0, 0x20Au);
  v8 = *a4;
  cchName = 261;
  v9 = RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, 0);
  if ( v9 == 259 )
    goto LABEL_38;
  while ( 1 )
  {
    if ( v9 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v14 = 46;
      goto LABEL_37;
    }
    v10 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
    if ( !v10 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)Name, v11, v10, (__int64)Name);
    ++*a4;
    memset_0(Name, 0, 0x20Au);
    v12 = *a4;
    cchName = 261;
    v9 = RegEnumKeyExW(hKey, v12, Name, &cchName, 0, 0, 0, 0);
    if ( v9 == 259 )
      goto LABEL_38;
  }
  RtlInitUnicodeString(&DestinationString, Name);
  v9 = RtlDuplicateUnicodeString(1u, &DestinationString, &UnicodeString);
  if ( !v9 )
  {
    v9 = RtlQueryRegistryValuesEx(0x40000000, phkResult, &v34, 0, 0);
    if ( !v9 )
    {
      v9 = KpsParseMitServerList(&v31, (struct _KPS_MIT_SERVER_LIST *)((char *)&v27 + 8));
      if ( v9 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_38;
        v17 = 50;
        v18 = &v31;
      }
      else
      {
        if ( !(_WORD)v28 )
          LODWORD(v27) = v27 | 0x80000000;
        v9 = KpsParseMitServerList((struct _UNICODE_STRING *)lpMem, (struct _KPS_MIT_SERVER_LIST *)((char *)&v28 + 8));
        if ( !v9 )
        {
          v19 = v27;
          if ( !(_WORD)v29 )
            v19 = v27 | 0x40000000;
          LODWORD(v27) = v24 | v19;
          *a2 = UnicodeString;
          UnicodeString = 0;
          v20 = v28;
          *(_OWORD *)a3 = v27;
          v21 = v29;
          *((_OWORD *)a3 + 1) = v20;
          v29 = 0;
          *((_QWORD *)a3 + 4) = v21;
          ++*a4;
          v27 = 0;
          v28 = 0;
          goto LABEL_38;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_38;
        v17 = 51;
        v18 = lpMem;
      }
      WPP_SF_DZ(v16[2], v17, v15, v9, (__int64)v18);
      goto LABEL_38;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    v14 = 49;
LABEL_37:
    WPP_SF_D(v13[2], v14, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, v9);
    goto LABEL_38;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 48;
    goto LABEL_37;
  }
LABEL_38:
  KpsFreeMitRealm((struct _KPS_MIT_REALM *)&v27);
  KpsFreeMem(lpMem[1]);
  KpsFreeMem(v31.Buffer);
  RtlFreeUnicodeString(&UnicodeString);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002f194  push    rbp
0x18002f196  push    rbx
0x18002f197  push    rsi
0x18002f198  push    rdi
0x18002f199  push    r12
0x18002f19b  push    r13
0x18002f19d  push    r14
0x18002f19f  push    r15
0x18002f1a1  lea     rbp, [rsp-2C8h]
0x18002f1a9  sub     rsp, 3C8h
0x18002f1b0  mov     rax, cs:__security_cookie
0x18002f1b7  xor     rax, rsp
0x18002f1ba  mov     [rbp+300h+var_50], rax
0x18002f1c1  xor     eax, eax
0x18002f1c3  mov     [rbp+300h+var_2C8], 20h ; ' '
0x18002f1ca  xor     r12d, r12d
0x18002f1cd  mov     [rsp+400h+var_388], rax
0x18002f1d2  xorps   xmm0, xmm0
0x18002f1d5  mov     [rsp+400h+phkResult], r12
0x18002f1da  lea     rax, aKdcnames; "KdcNames"
0x18002f1e1  mov     [rsp+400h+var_3BC], r12d
0x18002f1e6  mov     [rbp+300h+var_330], rax
0x18002f1ea  mov     r14, rcx
0x18002f1ed  lea     rcx, dword_18003492C
0x18002f1f4  mov     [rsp+400h+var_3B8], r12d
0x18002f1f9  lea     rax, [rbp+300h+var_370]
0x18002f1fd  mov     [rbp+300h+var_318], rcx
0x18002f201  mov     [rbp+300h+var_328], rax
0x18002f205  xorps   xmm1, xmm1
0x18002f208  lea     rax, aKpasswdnames; "KpasswdNames"
0x18002f20f  mov     [rbp+300h+var_2E0], rcx
0x18002f213  mov     [rbp+300h+var_2F8], rax
0x18002f217  mov     r15, rdx
0x18002f21a  lea     edx, [r12+7]
0x18002f21f  mov     [rbp+300h+var_310], r12d
0x18002f223  lea     rax, [rbp+300h+lpMem]
0x18002f227  mov     [rbp+300h+var_320], edx
0x18002f22a  mov     [rbp+300h+var_2F0], rax
0x18002f22e  lea     ecx, [rdx-3]
0x18002f231  lea     rax, aRealmflags; "RealmFlags"
0x18002f238  mov     [rbp+300h+var_2E8], edx
0x18002f23b  mov     [rbp+300h+var_2C0], rax
0x18002f23f  mov     rdi, r9
0x18002f242  lea     rax, [rsp+400h+var_3BC]
0x18002f247  mov     [rbp+300h+var_2D8], r12d
0x18002f24b  mov     [rbp+300h+var_2B8], rax
0x18002f24f  lea     r9, ?KpsMitRealmQuery@@YAJPEAGKPEAXK11@Z; KpsMitRealmQuery(ushort *,ulong,void *,ulong,void *,void *)
0x18002f256  lea     rax, [rsp+400h+var_3B8]
0x18002f25b  mov     [rbp+300h+var_340], r9
0x18002f25f  mov     [rbp+300h+var_2A8], rax
0x18002f263  mov     rsi, r8
0x18002f266  lea     r8d, [r12+10h]
0x18002f26b  mov     [rbp+300h+var_308], r9
0x18002f26f  xor     eax, eax
0x18002f271  mov     [rbp+300h+var_338], r8d
0x18002f275  mov     [rbp+300h+var_268], rax
0x18002f27c  movups  xmmword ptr [rbp+300h+DestinationString.Length], xmm0
0x18002f280  mov     [rbp+300h+var_300], r8d
0x18002f284  movups  xmmword ptr [rbp+300h+UnicodeString.Length], xmm1
0x18002f288  mov     [rbp+300h+var_2D0], r12
0x18002f28c  movups  xmmword ptr [rbp+300h+var_370.Length], xmm0
0x18002f290  mov     [rbp+300h+var_2B0], ecx
0x18002f293  movups  xmmword ptr [rbp+300h+lpMem], xmm1
0x18002f297  mov     [rbp+300h+var_2A0], ecx
0x18002f29a  movups  [rsp+400h+var_3A8], xmm0
0x18002f29f  movups  [rsp+400h+var_398], xmm0
0x18002f2a4  movups  [rbp+300h+var_298], xmm0
0x18002f2a8  movups  [rbp+300h+var_288], xmm0
0x18002f2ac  movups  [rbp+300h+var_278], xmm0
0x18002f2b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2ba  lea     r13, WPP_GLOBAL_Control
0x18002f2c1  cmp     rcx, r13
0x18002f2c4  jz      short loc_18002F2DF
0x18002f2c6  test    byte ptr [rcx+1Ch], 20h
0x18002f2ca  jz      short loc_18002F2DF
0x18002f2cc  mov     rcx, [rcx+10h]
0x18002f2d0  lea     edx, [rax+2Dh]
0x18002f2d3  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002f2da  call    WPP_SF_
0x18002f2df  xorps   xmm0, xmm0
0x18002f2e2  lea     rcx, [rbp+300h+Name]; void *
0x18002f2e9  movups  xmmword ptr [rsi], xmm0
0x18002f2ec  xor     eax, eax
0x18002f2ee  xor     edx, edx; Val
0x18002f2f0  movups  xmmword ptr [rsi+10h], xmm0
0x18002f2f4  mov     [rsi+20h], rax
0x18002f2f8  mov     r8d, 20Ah; Size
0x18002f2fe  movups  xmmword ptr [r15], xmm0
0x18002f302  call    memset_0
0x18002f307  mov     edx, [rdi]; dwIndex
0x18002f309  lea     r9, [rsp+400h+cchName]; lpcchName
0x18002f30e  mov     [rsp+400h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002f313  lea     r8, [rbp+300h+Name]; lpName
0x18002f31a  mov     [rsp+400h+lpcchClass], r12; lpcchClass
0x18002f31f  mov     rcx, r14; hKey
0x18002f322  mov     [rsp+400h+lpClass], r12; lpClass
0x18002f327  mov     [rsp+400h+lpReserved], r12; lpReserved
0x18002f32c  mov     [rsp+400h+cchName], 105h
0x18002f334  call    cs:__imp_RegEnumKeyExW
0x18002f33b  nop     dword ptr [rax+rax+00h]
0x18002f340  mov     ebx, eax
0x18002f342  cmp     eax, 103h
0x18002f347  jz      loc_18002F60B
0x18002f34d  mov     r13d, 1
0x18002f353  test    ebx, ebx
0x18002f355  jnz     loc_18002F5D3
0x18002f35b  lea     rax, [rsp+400h+phkResult]
0x18002f360  mov     r9d, 20019h; samDesired
0x18002f366  xor     r8d, r8d; ulOptions
0x18002f369  mov     [rsp+400h+lpReserved], rax; phkResult
0x18002f36e  lea     rdx, [rbp+300h+Name]; lpSubKey
0x18002f375  mov     rcx, r14; hKey
0x18002f378  call    cs:__imp_RegOpenKeyExW
0x18002f37f  nop     dword ptr [rax+rax+00h]
0x18002f384  test    eax, eax
0x18002f386  jz      loc_18002F41F
0x18002f38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f393  lea     rdx, WPP_GLOBAL_Control
0x18002f39a  cmp     rcx, rdx
0x18002f39d  jz      short loc_18002F3BD
0x18002f39f  test    byte ptr [rcx+1Ch], 2
0x18002f3a3  jz      short loc_18002F3BD
0x18002f3a5  mov     rcx, [rcx+10h]
0x18002f3a9  lea     rdx, [rbp+300h+Name]
0x18002f3b0  mov     r9d, eax
0x18002f3b3  mov     [rsp+400h+lpReserved], rdx
0x18002f3b8  call    WPP_SF_DS
0x18002f3bd  add     [rdi], r13d
0x18002f3c0  lea     rcx, [rbp+300h+Name]; void *
0x18002f3c7  xor     edx, edx; Val
0x18002f3c9  mov     r8d, 20Ah; Size
0x18002f3cf  call    memset_0
0x18002f3d4  mov     edx, [rdi]; dwIndex
0x18002f3d6  lea     r9, [rsp+400h+cchName]; lpcchName
0x18002f3db  mov     [rsp+400h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002f3e0  lea     r8, [rbp+300h+Name]; lpName
0x18002f3e7  mov     [rsp+400h+lpcchClass], r12; lpcchClass
0x18002f3ec  mov     rcx, r14; hKey
0x18002f3ef  mov     [rsp+400h+lpClass], r12; lpClass
0x18002f3f4  mov     [rsp+400h+lpReserved], r12; lpReserved
0x18002f3f9  mov     [rsp+400h+cchName], 105h
0x18002f401  call    cs:__imp_RegEnumKeyExW
0x18002f408  nop     dword ptr [rax+rax+00h]
0x18002f40d  mov     ebx, eax
0x18002f40f  cmp     eax, 103h
0x18002f414  jnz     loc_18002F353
0x18002f41a  jmp     loc_18002F604
0x18002f41f  lea     rdx, [rbp+300h+Name]; SourceString
0x18002f426  lea     rcx, [rbp+300h+DestinationString]; DestinationString
0x18002f42a  call    cs:__imp_RtlInitUnicodeString
0x18002f431  nop     dword ptr [rax+rax+00h]
0x18002f436  lea     r8, [rbp+300h+UnicodeString]; DestinationString
0x18002f43a  mov     ecx, r13d; Flags
0x18002f43d  lea     rdx, [rbp+300h+DestinationString]; SourceString
0x18002f441  call    cs:__imp_RtlDuplicateUnicodeString
0x18002f448  nop     dword ptr [rax+rax+00h]
0x18002f44d  mov     ebx, eax
0x18002f44f  test    eax, eax
0x18002f451  jz      short loc_18002F47E
0x18002f453  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f45a  lea     rax, WPP_GLOBAL_Control
0x18002f461  cmp     rcx, rax
0x18002f464  jz      loc_18002F604
0x18002f46a  test    [rcx+1Ch], r13b
0x18002f46e  jz      loc_18002F604
0x18002f474  mov     edx, 30h ; '0'
0x18002f479  jmp     loc_18002F5F1
0x18002f47e  mov     rdx, [rsp+400h+phkResult]
0x18002f483  lea     r8, [rbp+300h+var_340]
0x18002f487  mov     r14d, 40000000h
0x18002f48d  mov     [rsp+400h+lpReserved], r12
0x18002f492  mov     ecx, r14d
0x18002f495  xor     r9d, r9d
0x18002f498  call    cs:__imp_RtlQueryRegistryValuesEx
0x18002f49f  nop     dword ptr [rax+rax+00h]
0x18002f4a4  mov     ebx, eax
0x18002f4a6  test    eax, eax
0x18002f4a8  jz      short loc_18002F4D5
0x18002f4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4b1  lea     rax, WPP_GLOBAL_Control
0x18002f4b8  cmp     rcx, rax
0x18002f4bb  jz      loc_18002F604
0x18002f4c1  test    [rcx+1Ch], r13b
0x18002f4c5  jz      loc_18002F604
0x18002f4cb  mov     edx, 31h ; '1'
0x18002f4d0  jmp     loc_18002F5F1
0x18002f4d5  lea     rdx, [rsp+400h+var_3A8+8]; struct _KPS_MIT_SERVER_LIST *
0x18002f4da  lea     rcx, [rbp+300h+var_370]; struct _UNICODE_STRING *
0x18002f4de  call    ?KpsParseMitServerList@@YAKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_SERVER_LIST@@@Z; KpsParseMitServerList(_UNICODE_STRING *,_KPS_MIT_SERVER_LIST *)
0x18002f4e3  mov     ebx, eax
0x18002f4e5  test    eax, eax
0x18002f4e7  jz      short loc_18002F529
0x18002f4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4f0  lea     rax, WPP_GLOBAL_Control
0x18002f4f7  cmp     rcx, rax
0x18002f4fa  jz      loc_18002F604
0x18002f500  test    [rcx+1Ch], r13b
0x18002f504  jz      loc_18002F604
0x18002f50a  mov     edx, 32h ; '2'
0x18002f50f  lea     rax, [rbp+300h+var_370]
0x18002f513  mov     rcx, [rcx+10h]
0x18002f517  mov     r9d, ebx
0x18002f51a  mov     [rsp+400h+lpReserved], rax
0x18002f51f  call    WPP_SF_DZ
0x18002f524  jmp     loc_18002F604
0x18002f529  cmp     word ptr [rsp+400h+var_398], r12w
0x18002f52f  jnz     short loc_18002F537
0x18002f531  bts     dword ptr [rsp+400h+var_3A8], 1Fh
0x18002f537  lea     rdx, [rsp+400h+var_398+8]; struct _KPS_MIT_SERVER_LIST *
0x18002f53c  lea     rcx, [rbp+300h+lpMem]; struct _UNICODE_STRING *
0x18002f540  call    ?KpsParseMitServerList@@YAKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_SERVER_LIST@@@Z; KpsParseMitServerList(_UNICODE_STRING *,_KPS_MIT_SERVER_LIST *)
0x18002f545  mov     ebx, eax
0x18002f547  test    eax, eax
0x18002f549  jz      short loc_18002F577
0x18002f54b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f552  lea     rax, WPP_GLOBAL_Control
0x18002f559  cmp     rcx, rax
0x18002f55c  jz      loc_18002F604
0x18002f562  test    [rcx+1Ch], r13b
0x18002f566  jz      loc_18002F604
0x18002f56c  mov     edx, 33h ; '3'
0x18002f571  lea     rax, [rbp+300h+lpMem]
0x18002f575  jmp     short loc_18002F513
0x18002f577  mov     eax, dword ptr [rsp+400h+var_3A8]
0x18002f57b  cmp     word ptr [rsp+400h+var_388], r12w
0x18002f581  jnz     short loc_18002F586
0x18002f583  or      eax, r14d
0x18002f586  movups  xmm0, xmmword ptr [rbp+300h+UnicodeString.Length]
0x18002f58a  or      eax, [rsp+400h+var_3BC]
0x18002f58e  xorps   xmm1, xmm1
0x18002f591  mov     dword ptr [rsp+400h+var_3A8], eax
0x18002f595  movdqu  xmmword ptr [r15], xmm0
0x18002f59a  xor     eax, eax
0x18002f59c  movups  xmm0, [rsp+400h+var_3A8]
0x18002f5a1  movups  xmmword ptr [rbp+300h+UnicodeString.Length], xmm1
0x18002f5a5  movups  xmm1, [rsp+400h+var_398]
0x18002f5aa  movups  xmmword ptr [rsi], xmm0
0x18002f5ad  movsd   xmm0, [rsp+400h+var_388]
0x18002f5b3  movups  xmmword ptr [rsi+10h], xmm1
0x18002f5b7  mov     [rsp+400h+var_388], rax
0x18002f5bc  xorps   xmm1, xmm1
0x18002f5bf  movsd   qword ptr [rsi+20h], xmm0
0x18002f5c4  add     [rdi], r13d
0x18002f5c7  movups  [rsp+400h+var_3A8], xmm1
0x18002f5cc  movups  [rsp+400h+var_398], xmm1
0x18002f5d1  jmp     short loc_18002F604
0x18002f5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5da  lea     rax, WPP_GLOBAL_Control
0x18002f5e1  cmp     rcx, rax
0x18002f5e4  jz      short loc_18002F604
0x18002f5e6  test    [rcx+1Ch], r13b
0x18002f5ea  jz      short loc_18002F604
0x18002f5ec  mov     edx, 2Eh ; '.'
0x18002f5f1  mov     rcx, [rcx+10h]
0x18002f5f5  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002f5fc  mov     r9d, ebx
0x18002f5ff  call    WPP_SF_D
0x18002f604  lea     r13, WPP_GLOBAL_Control
0x18002f60b  lea     rcx, [rsp+400h+var_3A8]; struct _KPS_MIT_REALM *
0x18002f610  call    ?KpsFreeMitRealm@@YAXPEAU_KPS_MIT_REALM@@@Z; KpsFreeMitRealm(_KPS_MIT_REALM *)
0x18002f615  mov     rcx, [rbp+300h+lpMem+8]; lpMem
0x18002f619  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002f61e  mov     rcx, [rbp+300h+var_370.Buffer]; lpMem
0x18002f622  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002f627  lea     rcx, [rbp+300h+UnicodeString]; UnicodeString
0x18002f62b  call    cs:__imp_RtlFreeUnicodeString
0x18002f632  nop     dword ptr [rax+rax+00h]
0x18002f637  mov     rcx, [rsp+400h+phkResult]; hKey
0x18002f63c  test    rcx, rcx
0x18002f63f  jz      short loc_18002F64D
0x18002f641  call    cs:__imp_RegCloseKey
0x18002f648  nop     dword ptr [rax+rax+00h]
0x18002f64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f654  cmp     rcx, r13
0x18002f657  jz      short loc_18002F677
0x18002f659  test    byte ptr [rcx+1Ch], 20h
0x18002f65d  jz      short loc_18002F677
0x18002f65f  mov     rcx, [rcx+10h]
0x18002f663  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002f66a  mov     edx, 34h ; '4'
0x18002f66f  mov     r9d, ebx
0x18002f672  call    WPP_SF_D
0x18002f677  mov     eax, ebx
0x18002f679  mov     rcx, [rbp+300h+var_50]
0x18002f680  xor     rcx, rsp; StackCookie
0x18002f683  call    __security_check_cookie
0x18002f688  add     rsp, 3C8h
0x18002f68f  pop     r15
0x18002f691  pop     r14
0x18002f693  pop     r13
0x18002f695  pop     r12
0x18002f697  pop     rdi
0x18002f698  pop     rsi
0x18002f699  pop     rbx
0x18002f69a  pop     rbp
0x18002f69b  retn
```
