# I_CertDllOpenSystemStoreProvW(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x18005acf0`
- end: `0x18005b0ad`
- name: `?I_CertDllOpenSystemStoreProvW@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(const char *, unsigned int, __int64, unsigned int, void *pvSystemStore, HCERTSTORE hCollectionStore, struct _CERT_STORE_PROV_INFO *ppvFuncAddr)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006db00`

## callees

- `0x18001a0d0`
- `0x180026220`
- `0x18005acf0`
- `0x18005be80`
- `0x18005cfc0`
- `0x18005d484`
- `0x180085660`
- `0x180086318`
- `0x1800c83b0`
- `0x1800c87c4`
- `0x1800c91fc`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ae9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005af07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b007`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ae9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005af07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b08d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b08d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ae94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ae94`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005aef9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005af98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afc4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005aef9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005af98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005afc4`

## pseudocode

```c
__int64 __fastcall I_CertDllOpenSystemStoreProvW(
        const char *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        void *pvSystemStore,
        HCERTSTORE hCollectionStore,
        struct _CERT_STORE_PROV_INFO *ppvFuncAddr)
{
  struct _CERT_STORE_PROV_INFO *v7; // rdi
  signed int v8; // ebx
  unsigned int v9; // eax
  DWORD dwStoreProvFlags; // r9d
  __int64 v14; // rcx
  char *v15; // rdx
  const WCHAR *v16; // r14
  unsigned int v17; // esi
  __int64 i; // rdi
  HLOCAL v19; // r14
  DWORD LastError; // ebx
  DWORD v22; // ecx
  HKEY v23; // rax
  HLOCAL hMem[2]; // [rsp+40h] [rbp-51h] BYREF
  __int128 v25; // [rsp+50h] [rbp-41h]
  __int64 v26; // [rsp+60h] [rbp-31h]
  __int128 v27; // [rsp+68h] [rbp-29h] BYREF
  __int128 v28; // [rsp+78h] [rbp-19h]
  __int128 v29; // [rsp+88h] [rbp-9h]

  v7 = ppvFuncAddr;
  v26 = 0;
  v8 = a4;
  v9 = HIWORD(a4);
  ppvFuncAddr->dwStoreProvFlags |= 8u;
  dwStoreProvFlags = v7->dwStoreProvFlags;
  *(_OWORD *)hMem = 0;
  v25 = 0;
  v14 = 12LL * (unsigned __int8)v9;
  if ( (unsigned __int8)v9 >= 0xBu )
    goto LABEL_46;
  if ( (*(_DWORD *)&byte_180138E30[v14] & 8) == 0 )
  {
    if ( (unsigned __int8)v9 < 0xBu )
      goto LABEL_4;
LABEL_46:
    v15 = &byte_180138E30[v14];
    goto LABEL_5;
  }
  dwStoreProvFlags |= 0x10u;
  v7->dwStoreProvFlags = dwStoreProvFlags;
LABEL_4:
  v15 = &byte_180138E30[v14];
  if ( (*(_DWORD *)&byte_180138E30[v14] & 0x10) != 0 )
  {
    v7->dwStoreProvFlags = dwStoreProvFlags | 0x20;
    goto LABEL_6;
  }
LABEL_5:
  if ( (unsigned __int8)v9 >= 0xBu )
    goto LABEL_31;
LABEL_6:
  if ( (*(_DWORD *)v15 & 1) != 0 )
  {
LABEL_31:
    ppvFuncAddr = 0;
    if ( CryptGetOIDFunctionAddress(
           qword_1801582F0,
           0,
           (LPCSTR)BYTE2(v8),
           0,
           (void **)&ppvFuncAddr,
           &v7->hStoreProvFuncAddr2) )
    {
      return ((__int64 (__fastcall *)(const char *, _QWORD, __int64, _QWORD, void *, HCERTSTORE, struct _CERT_STORE_PROV_INFO *))ppvFuncAddr)(
               a1,
               a2,
               a3,
               (unsigned int)v8,
               pvSystemStore,
               hCollectionStore,
               v7);
    }
    return 0;
  }
  if ( (v8 & 0x20) == 0 )
    goto LABEL_8;
  if ( v8 < 0 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  v8 &= ~0x20u;
LABEL_8:
  if ( (unsigned int)ParseSystemStorePara(pvSystemStore, v8, 1u, (struct _SYSTEM_NAME_INFO *)hMem) )
  {
    if ( (v8 & 0x2C) != 0
      || (v16 = (const WCHAR *)hMem[1], (v8 & 0xFF0000) == 0x10000)
      && (unsigned int)I_CryptIsAppContainerToken(0)
      && (v8 < 0
       || (v8 & 0x10000000) != 0
       || CompareStringW(0x409u, 1u, v16, -1, L"SmartCardRoot", -1) == 2
       || CompareStringW(0x409u, 1u, v16, -1, L"SmartCardRootCtrl", -1) == 2) )
    {
      v22 = -2147024809;
      goto LABEL_29;
    }
    if ( (v8 & 0x800) != 0 )
      ILS_EnableBackupRestorePrivileges();
    if ( (v8 & 0x10) != 0 )
    {
      if ( !CertUnregisterSystemStore(pvSystemStore, v8 & 0xFFFF4810) )
        goto LABEL_30;
      v7->dwStoreProvFlags |= 2u;
      goto LABEL_20;
    }
    v27 = 0;
    v28 = 0;
    v29 = 0;
    if ( (v8 & 0x2000) != 0 )
    {
      v23 = OpenSystemStore(pvSystemStore, v8);
      if ( !v23 )
        goto LABEL_30;
      RegCloseKey(v23);
      v8 &= ~0x2000u;
    }
    *((_QWORD *)&v27 + 1) = *((_QWORD *)&v25 + 1);
    v28 = (unsigned __int64)v25;
    *(_QWORD *)&v29 = v26;
    *(_QWORD *)&v27 = hCollectionStore;
    *((_QWORD *)&v29 + 1) = v8 & 0xFFFFFFFD;
    if ( (unsigned int)EnumPhysicalStore(pvSystemStore, v8 & 0xFFFFD8C0, &v27, OpenPhysicalStoreCallback) )
    {
      if ( !HIDWORD(v29) )
      {
        if ( !(unsigned int)IsPredefinedSystemStore(v16, v8) && CompareStringW(0x409u, 1u, v16, -1, L"Request", -1) != 2 )
        {
          v22 = 2;
LABEL_29:
          SetLastError(v22);
          goto LABEL_30;
        }
        CertAddStoreToCollection(hCollectionStore, 0, 0, 0);
      }
      if ( (v8 & 2) != 0 )
        SetLocalizedNameStoreProperty(hCollectionStore, (struct _SYSTEM_NAME_INFO *)hMem);
LABEL_20:
      v17 = 1;
      goto LABEL_21;
    }
  }
LABEL_30:
  v17 = 0;
LABEL_21:
  for ( i = 0; i != 4; ++i )
  {
    v19 = hMem[i];
    if ( v19 )
    {
      LastError = GetLastError();
      LocalFree(v19);
      SetLastError(LastError);
      hMem[i] = 0;
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18005acf0  push    rbp
0x18005acf2  push    rbx
0x18005acf3  push    rsi
0x18005acf4  push    rdi
0x18005acf5  push    r14
0x18005acf7  push    r15
0x18005acf9  lea     rbp, [rsp-17h]
0x18005acfe  sub     rsp, 0A8h
0x18005ad05  mov     rdi, [rbp+3Fh+ppvFuncAddr]
0x18005ad09  xor     eax, eax
0x18005ad0b  mov     [rbp+3Fh+var_70], rax
0x18005ad0f  mov     ebx, r9d
0x18005ad12  mov     eax, ebx
0x18005ad14  xorps   xmm0, xmm0
0x18005ad17  shr     eax, 10h
0x18005ad1a  mov     rsi, r8
0x18005ad1d  or      dword ptr [rdi+18h], 8
0x18005ad21  mov     r14d, edx
0x18005ad24  mov     r9d, [rdi+18h]
0x18005ad28  lea     rdx, byte_180138E30
0x18005ad2f  movzx   r8d, al
0x18005ad33  mov     r15, rcx
0x18005ad36  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x18005ad3a  movups  [rbp+3Fh+var_80], xmm0
0x18005ad3e  lea     rax, [r8+r8*2]
0x18005ad42  lea     rcx, ds:0[rax*4]
0x18005ad4a  cmp     r8d, 0Bh
0x18005ad4e  jnb     loc_18005B05D
0x18005ad54  mov     eax, [rcx+rdx]
0x18005ad57  test    al, 8
0x18005ad59  jnz     loc_18005B043
0x18005ad5f  cmp     r8d, 0Bh
0x18005ad63  jnb     loc_18005B05D
0x18005ad69  add     rdx, rcx
0x18005ad6c  mov     eax, [rdx]
0x18005ad6e  test    al, 10h
0x18005ad70  jnz     loc_18005B050
0x18005ad76  cmp     r8d, 0Bh
0x18005ad7a  jnb     loc_18005AF14
0x18005ad80  mov     eax, [rdx]
0x18005ad82  test    al, 1
0x18005ad84  jnz     loc_18005AF14
0x18005ad8a  test    bl, 20h
0x18005ad8d  jnz     loc_18005AFFE
0x18005ad93  mov     rsi, [rbp+3Fh+pvSystemStore]
0x18005ad97  lea     r9, [rbp+3Fh+hMem]; struct _SYSTEM_NAME_INFO *
0x18005ad9b  mov     rcx, rsi; void *
0x18005ad9e  mov     r8d, 1; unsigned int
0x18005ada4  mov     edx, ebx; unsigned int
0x18005ada6  call    ?ParseSystemStorePara@@YAHPEBXKKPEAU_SYSTEM_NAME_INFO@@@Z; ParseSystemStorePara(void const *,ulong,ulong,_SYSTEM_NAME_INFO *)
0x18005adab  test    eax, eax
0x18005adad  jz      loc_18005AF0D
0x18005adb3  test    bl, 2Ch
0x18005adb6  jnz     loc_18005AFD3
0x18005adbc  mov     r14, [rbp+3Fh+hMem+8]
0x18005adc0  mov     eax, ebx
0x18005adc2  and     eax, 0FF0000h
0x18005adc7  mov     r15d, 2
0x18005adcd  cmp     eax, 10000h
0x18005add2  jnz     short loc_18005ADE3
0x18005add4  xor     ecx, ecx
0x18005add6  call    I_CryptIsAppContainerToken
0x18005addb  test    eax, eax
0x18005addd  jnz     loc_18005AF6D
0x18005ade3  bt      ebx, 0Bh
0x18005ade7  jb      loc_18005B06D
0x18005aded  test    bl, 10h
0x18005adf0  jnz     loc_18005AFDD
0x18005adf6  xorps   xmm0, xmm0
0x18005adf9  movups  [rbp+3Fh+var_68], xmm0
0x18005adfd  movups  [rbp+3Fh+var_58], xmm0
0x18005ae01  movups  [rbp+3Fh+var_48], xmm0
0x18005ae05  bt      ebx, 0Dh
0x18005ae09  jb      loc_18005B077
0x18005ae0f  mov     rax, qword ptr [rbp+3Fh+var_80+8]
0x18005ae13  lea     r9, ?OpenPhysicalStoreCallback@@YAHPEBXKPEBGPEAU_CERT_PHYSICAL_STORE_INFO@@PEAX3@Z; int (*)(const void *, unsigned int, const unsigned __int16 *, struct _CERT_PHYSICAL_STORE_INFO *, void *, void *)
0x18005ae1a  mov     rdi, [rbp+3Fh+hCollectionStore]
0x18005ae1e  lea     r8, [rbp+3Fh+var_68]; void *
0x18005ae22  mov     qword ptr [rbp+3Fh+var_68+8], rax
0x18005ae26  mov     edx, ebx
0x18005ae28  mov     rax, qword ptr [rbp+3Fh+var_80]
0x18005ae2c  and     edx, 0FFFFD8C0h; unsigned int
0x18005ae32  mov     qword ptr [rbp+3Fh+var_58], rax
0x18005ae36  mov     rcx, rsi; void *
0x18005ae39  mov     rax, [rbp+3Fh+var_70]
0x18005ae3d  mov     qword ptr [rbp+3Fh+var_48], rax
0x18005ae41  mov     eax, ebx
0x18005ae43  and     eax, 0FFFFFFFDh
0x18005ae46  mov     qword ptr [rbp+3Fh+var_68], rdi
0x18005ae4a  mov     dword ptr [rbp+3Fh+var_48+8], eax
0x18005ae4d  mov     qword ptr [rbp+3Fh+var_58+8], 0
0x18005ae55  mov     dword ptr [rbp+3Fh+var_48+0Ch], 0
0x18005ae5c  call    ?EnumPhysicalStore@@YAHPEBXKPEAXP6AH0KPEBGPEAU_CERT_PHYSICAL_STORE_INFO@@11@Z@Z; EnumPhysicalStore(void const *,ulong,void *,int (*)(void const *,ulong,ushort const *,_CERT_PHYSICAL_STORE_INFO *,void *,void *))
0x18005ae61  test    eax, eax
0x18005ae63  jz      loc_18005AF0D
0x18005ae69  cmp     dword ptr [rbp+3Fh+var_48+0Ch], 0
0x18005ae6d  jz      short loc_18005AEC6
0x18005ae6f  test    r15b, bl
0x18005ae72  jnz     loc_18005B09C
0x18005ae78  mov     esi, 1
0x18005ae7d  xor     edi, edi
0x18005ae7f  mov     r14, [rbp+rdi*8+3Fh+hMem]
0x18005ae84  test    r14, r14
0x18005ae87  jz      short loc_18005AEAB
0x18005ae89  call    cs:__imp_GetLastError
0x18005ae8f  mov     rcx, r14; hMem
0x18005ae92  mov     ebx, eax
0x18005ae94  call    cs:__imp_LocalFree
0x18005ae9a  mov     ecx, ebx; dwErrCode
0x18005ae9c  call    cs:__imp_SetLastError
0x18005aea2  mov     [rbp+rdi*8+3Fh+hMem], 0
0x18005aeab  inc     rdi
0x18005aeae  cmp     rdi, 4
0x18005aeb2  jnz     short loc_18005AE7F
0x18005aeb4  mov     eax, esi
0x18005aeb6  add     rsp, 0A8h
0x18005aebd  pop     r15
0x18005aebf  pop     r14
0x18005aec1  pop     rdi
0x18005aec2  pop     rsi
0x18005aec3  pop     rbx
0x18005aec4  pop     rbp
0x18005aec5  retn
0x18005aec6  mov     edx, ebx; unsigned int
0x18005aec8  mov     rcx, r14; lpString2
0x18005aecb  call    ?IsPredefinedSystemStore@@YAHPEBGK@Z; IsPredefinedSystemStore(ushort const *,ulong)
0x18005aed0  test    eax, eax
0x18005aed2  jnz     loc_18005AF58
0x18005aed8  or      ecx, 0FFFFFFFFh
0x18005aedb  lea     rax, aRequest; "Request"
0x18005aee2  mov     [rsp+0D0h+cchCount2], ecx; cchCount2
0x18005aee6  mov     r9d, ecx; cchCount1
0x18005aee9  mov     r8, r14; lpString1
0x18005aeec  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18005aef1  lea     edx, [rcx+2]; dwCmpFlags
0x18005aef4  mov     ecx, 409h; Locale
0x18005aef9  call    cs:__imp_CompareStringW
0x18005aeff  cmp     eax, r15d
0x18005af02  jz      short loc_18005AF58
0x18005af04  mov     ecx, r15d; dwErrCode
0x18005af07  call    cs:__imp_SetLastError
0x18005af0d  xor     esi, esi
0x18005af0f  jmp     loc_18005AE7D
0x18005af14  mov     rcx, cs:qword_1801582F0; hFuncSet
0x18005af1b  lea     rdx, [rdi+20h]
0x18005af1f  mov     qword ptr [rsp+0D0h+cchCount2], rdx; phFuncAddr
0x18005af24  mov     eax, ebx
0x18005af26  shr     rax, 10h
0x18005af2a  xor     r9d, r9d; dwFlags
0x18005af2d  movzx   r8d, al; pszOID
0x18005af31  xor     edx, edx; dwEncodingType
0x18005af33  lea     rax, [rbp+3Fh+ppvFuncAddr]
0x18005af37  mov     [rbp+3Fh+ppvFuncAddr], 0
0x18005af3f  mov     [rsp+0D0h+lpString2], rax; ppvFuncAddr
0x18005af44  call    CryptGetOIDFunctionAddress
0x18005af49  test    eax, eax
0x18005af4b  jnz     loc_18005B012
0x18005af51  xor     eax, eax
0x18005af53  jmp     loc_18005AEB6
0x18005af58  xor     r9d, r9d; dwPriority
0x18005af5b  xor     r8d, r8d; dwUpdateFlags
0x18005af5e  xor     edx, edx; hSiblingStore
0x18005af60  mov     rcx, rdi; hCollectionStore
0x18005af63  call    CertAddStoreToCollection
0x18005af68  jmp     loc_18005AE6F
0x18005af6d  test    ebx, ebx
0x18005af6f  js      short loc_18005AFD3
0x18005af71  bt      ebx, 1Ch
0x18005af75  jb      short loc_18005AFD3
0x18005af77  or      ecx, 0FFFFFFFFh
0x18005af7a  lea     rax, aSmartcardroot; "SmartCardRoot"
0x18005af81  mov     [rsp+0D0h+cchCount2], ecx; cchCount2
0x18005af85  mov     r9d, ecx; cchCount1
0x18005af88  mov     r8, r14; lpString1
0x18005af8b  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18005af90  lea     edx, [rcx+2]; dwCmpFlags
0x18005af93  mov     ecx, 409h; Locale
0x18005af98  call    cs:__imp_CompareStringW
0x18005af9e  cmp     eax, r15d
0x18005afa1  jz      short loc_18005AFD3
0x18005afa3  or      ecx, 0FFFFFFFFh
0x18005afa6  lea     rax, aSmartcardrootc; "SmartCardRootCtrl"
0x18005afad  mov     [rsp+0D0h+cchCount2], ecx; cchCount2
0x18005afb1  mov     r9d, ecx; cchCount1
0x18005afb4  mov     r8, r14; lpString1
0x18005afb7  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18005afbc  lea     edx, [rcx+2]; dwCmpFlags
0x18005afbf  mov     ecx, 409h; Locale
0x18005afc4  call    cs:__imp_CompareStringW
0x18005afca  cmp     eax, r15d
0x18005afcd  jnz     loc_18005ADE3
0x18005afd3  mov     ecx, 80070057h
0x18005afd8  jmp     loc_18005AF07
0x18005afdd  and     ebx, 0FFFF4810h
0x18005afe3  mov     rcx, rsi; pvSystemStore
0x18005afe6  mov     edx, ebx; dwFlags
0x18005afe8  call    CertUnregisterSystemStore
0x18005afed  test    eax, eax
0x18005afef  jz      loc_18005AF0D
0x18005aff5  or      [rdi+18h], r15d
0x18005aff9  jmp     loc_18005AE78
0x18005affe  test    ebx, ebx
0x18005b000  jns     short loc_18005B065
0x18005b002  mov     ecx, 80070057h; dwErrCode
0x18005b007  call    cs:__imp_SetLastError
0x18005b00d  jmp     loc_18005AF51
0x18005b012  mov     rcx, [rbp+3Fh+hCollectionStore]
0x18005b016  mov     r9d, ebx
0x18005b019  mov     rax, [rbp+3Fh+ppvFuncAddr]
0x18005b01d  mov     r8, rsi
0x18005b020  mov     [rsp+0D0h+var_A0], rdi
0x18005b025  mov     edx, r14d
0x18005b028  mov     qword ptr [rsp+0D0h+cchCount2], rcx
0x18005b02d  mov     rcx, [rbp+3Fh+pvSystemStore]
0x18005b031  mov     [rsp+0D0h+lpString2], rcx
0x18005b036  mov     rcx, r15
0x18005b039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b03e  jmp     loc_18005AEB6
0x18005b043  or      r9d, 10h
0x18005b047  mov     [rdi+18h], r9d
0x18005b04b  jmp     loc_18005AD69
0x18005b050  or      r9d, 20h
0x18005b054  mov     [rdi+18h], r9d
0x18005b058  jmp     loc_18005AD80
0x18005b05d  add     rdx, rcx
0x18005b060  jmp     loc_18005AD76
0x18005b065  and     ebx, 0FFFFFFDFh
0x18005b068  jmp     loc_18005AD93
0x18005b06d  call    ?ILS_EnableBackupRestorePrivileges@@YAXXZ; ILS_EnableBackupRestorePrivileges(void)
0x18005b072  jmp     loc_18005ADED
0x18005b077  mov     edx, ebx; unsigned int
0x18005b079  mov     rcx, rsi; void *
0x18005b07c  call    ?OpenSystemStore@@YAPEAUHKEY__@@PEBXK@Z; OpenSystemStore(void const *,ulong)
0x18005b081  test    rax, rax
0x18005b084  jz      loc_18005AF0D
0x18005b08a  mov     rcx, rax; hKey
0x18005b08d  call    cs:__imp_RegCloseKey
0x18005b093  btr     ebx, 0Dh
0x18005b097  jmp     loc_18005AE0F
0x18005b09c  lea     rdx, [rbp+3Fh+hMem]; struct _SYSTEM_NAME_INFO *
0x18005b0a0  mov     rcx, rdi; hCertStore
0x18005b0a3  call    ?SetLocalizedNameStoreProperty@@YAXPEAXPEAU_SYSTEM_NAME_INFO@@@Z; SetLocalizedNameStoreProperty(void *,_SYSTEM_NAME_INFO *)
0x18005b0a8  jmp     loc_18005AE78
```
