# CCertThumbprintsAndSidsMapping::ReadThumb2SidsFromRegistry(int)

- ea: `0x18001fb44`
- end: `0x18001fe33`
- name: `?ReadThumb2SidsFromRegistry@CCertThumbprintsAndSidsMapping@@QEAAJH@Z`
- size: `751`
- prototype: `__int64 __fastcall(CCertThumbprintsAndSidsMapping *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800219a0`

## callees

- `0x18000a100`
- `0x18000f3a0`
- `0x18000fcd0`
- `0x18001022c`
- `0x180010b2c`
- `0x1800121a8`
- `0x18001f218`
- `0x18001f35c`
- `0x18001f3b4`
- `0x18001f730`
- `0x18001f9f8`
- `0x18001fa4c`
- `0x18001fb44`
- `0x18001febc`
- `0x180024dc0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHEnumValueW` at `0x18001fd84`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumValueW` at `0x18001fd84`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18001fc4d`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18001fc4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertThumbprintsAndSidsMapping::ReadThumb2SidsFromRegistry(CCertThumbprintsAndSidsMapping *this)
{
  const wchar_t *v2; // rcx
  signed int inited; // ebx
  unsigned int v4; // r9d
  int v5; // eax
  DWORD v6; // r14d
  LSTATUS v7; // eax
  CHashValueStringList *v8; // rax
  const wchar_t *v9; // rcx
  unsigned int v10; // r9d
  CHashValueStringList *v11; // rdi
  unsigned int v12; // edx
  int v13; // eax
  DWORD v14; // esi
  LSTATUS v15; // eax
  int v16; // eax
  void *v17; // rdx
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v20; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pdwType; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchValueName[2]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details *v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  WCHAR pszName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[510]; // [rsp+82h] [rbp-7Eh] BYREF
  WCHAR pszValueName; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v30[32766]; // [rsp+282h] [rbp+182h] BYREF

  v25 = 0;
  v26 = 0;
  inited = CEfsMutexLock::Lock((CEfsMutexLock *)&v25);
  if ( inited >= 0 )
  {
    CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::DestroyAll(this);
    CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::DestroyAll((char *)this + 24);
  }
  hkey = 0;
  if ( inited >= 0 )
  {
    hkey = 0;
    v5 = WSearchRegOpenKeyEx(v2, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search\\EFS", v4, 0x20019u, &hkey);
    if ( v5 == 2 )
    {
      inited = CEfsMutexLock::Unlock((CEfsMutexLock *)&v25);
      goto LABEL_43;
    }
    if ( v5 )
    {
      if ( v5 > 0 )
        inited = (unsigned __int16)v5 | 0x80070000;
      else
        inited = v5;
    }
    if ( inited >= 0 )
    {
      v6 = 0;
      pszName = 0;
      memset_0(v28, 0, sizeof(v28));
      if ( !inited )
      {
        while ( 1 )
        {
          pcchName = 256;
          v7 = SHEnumKeyExW(hkey, v6, &pszName, &pcchName);
          inited = v7;
          if ( v7 == 259 )
            goto LABEL_39;
          if ( v7 )
          {
            if ( v7 <= 0 )
              goto LABEL_40;
            inited = (unsigned __int16)v7 | 0x80070000;
            break;
          }
          v8 = (CHashValueStringList *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
          v11 = v8;
          *(_QWORD *)pcchValueName = v8;
          if ( v8 )
          {
            *(_QWORD *)v8 = 0;
            *((_QWORD *)v8 + 1) = 0;
            *((_DWORD *)v8 + 4) = 0;
            *((_QWORD *)v8 + 3) = 0;
            *((_DWORD *)v8 + 8) = 0;
            *((_QWORD *)v8 + 5) = 0;
            *((_QWORD *)v8 + 6) = 0;
            inited = CHashValueStringList::InitKeyCopy(v8, &pszName);
            if ( inited < 0 )
              CHashValueStringList::`scalar deleting destructor'(v11, v12);
            else
              CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Insert((char *)this + 24, v11, v11);
          }
          else
          {
            v11 = 0;
            inited = -2147024882;
          }
          v20 = 0;
          if ( inited >= 0 )
          {
            v20 = 0;
            v13 = WSearchRegOpenKeyEx(v9, hkey, &pszName, v10, 0x20019u, &v20);
            if ( v13 )
            {
              if ( v13 > 0 )
                inited = (unsigned __int16)v13 | 0x80070000;
              else
                inited = v13;
            }
            if ( inited >= 0 )
            {
              pszValueName = 0;
              memset_0(v30, 0, sizeof(v30));
              v14 = 0;
              if ( inited )
              {
LABEL_32:
                if ( inited != 1 )
                  goto LABEL_34;
              }
              else
              {
                while ( 1 )
                {
                  pcchValueName[0] = 0x4000;
                  pdwType = 0;
                  pcbData = 0;
                  v15 = SHEnumValueW(v20, v14, &pszValueName, pcchValueName, &pdwType, 0, &pcbData);
                  inited = v15;
                  if ( v15 == 259 )
                    break;
                  if ( v15 )
                  {
                    if ( v15 <= 0 )
                      goto LABEL_34;
                    inited = (unsigned __int16)v15 | 0x80070000;
                    goto LABEL_32;
                  }
                  inited = CHashValueStringList::AddStringCopyToList(v11, &pszValueName);
                  if ( inited )
                    goto LABEL_32;
                  ++v14;
                }
              }
              inited = 0;
            }
          }
LABEL_34:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
          if ( inited )
            break;
          ++v6;
        }
      }
      if ( inited == 1 )
LABEL_39:
        inited = 0;
    }
  }
LABEL_40:
  v16 = CEfsMutexLock::Unlock((CEfsMutexLock *)&v25);
  if ( inited >= 0 && v16 < 0 )
    inited = v16;
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v17);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001fb44  push    rbp
0x18001fb46  push    rbx
0x18001fb47  push    rsi
0x18001fb48  push    rdi
0x18001fb49  push    r12
0x18001fb4b  push    r13
0x18001fb4d  push    r14
0x18001fb4f  push    r15
0x18001fb51  lea     rbp, [rsp-8198h]
0x18001fb59  mov     eax, 8298h
0x18001fb5e  call    _alloca_probe
0x18001fb63  sub     rsp, rax
0x18001fb66  mov     rax, cs:__security_cookie
0x18001fb6d  xor     rax, rsp
0x18001fb70  mov     [rbp+81D0h+var_50], rax
0x18001fb77  mov     r15, rcx
0x18001fb7a  xor     r12d, r12d
0x18001fb7d  mov     [rsp+82D0h+var_8268], r12
0x18001fb82  mov     [rsp+82D0h+var_8260], r12d
0x18001fb87  lea     rcx, [rsp+82D0h+var_8268]; this
0x18001fb8c  call    ?Lock@CEfsMutexLock@@QEAAJXZ; CEfsMutexLock::Lock(void)
0x18001fb91  mov     ebx, eax
0x18001fb93  test    eax, eax
0x18001fb95  js      short loc_18001FBA8
0x18001fb97  mov     rcx, r15
0x18001fb9a  call    ?DestroyAll@?$CTKPLiteHashMapContainer@VCStringHashKey@@VCHashValueStringList@@@@QEAAXXZ; CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::DestroyAll(void)
0x18001fb9f  lea     rcx, [r15+18h]
0x18001fba3  call    ?DestroyAll@?$CTKPLiteHashMapContainer@VCStringHashKey@@VCHashValueStringList@@@@QEAAXXZ; CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::DestroyAll(void)
0x18001fba8  mov     [rsp+82D0h+hkey], r12
0x18001fbad  test    ebx, ebx
0x18001fbaf  js      loc_18001FDE6
0x18001fbb5  mov     [rsp+82D0h+hkey], r12
0x18001fbba  lea     rax, [rsp+82D0h+hkey]
0x18001fbbf  mov     [rsp+82D0h+pvData], rax; HKEY *
0x18001fbc4  mov     dword ptr [rsp+82D0h+pdwType], 20019h; unsigned int
0x18001fbcc  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Search\\EF"...
0x18001fbd3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001fbda  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18001fbdf  cmp     eax, 2
0x18001fbe2  jnz     short loc_18001FBF5
0x18001fbe4  lea     rcx, [rsp+82D0h+var_8268]; this
0x18001fbe9  call    ?Unlock@CEfsMutexLock@@QEAAJXZ; CEfsMutexLock::Unlock(void)
0x18001fbee  mov     ebx, eax
0x18001fbf0  jmp     loc_18001FDF9
0x18001fbf5  mov     r13d, 80070000h
0x18001fbfb  test    eax, eax
0x18001fbfd  jz      short loc_18001FC0B
0x18001fbff  jg      short loc_18001FC05
0x18001fc01  mov     ebx, eax
0x18001fc03  jmp     short loc_18001FC0B
0x18001fc05  movzx   ebx, ax
0x18001fc08  or      ebx, r13d
0x18001fc0b  test    ebx, ebx
0x18001fc0d  js      loc_18001FDE6
0x18001fc13  mov     r14d, r12d
0x18001fc16  mov     [rbp+81D0h+pszName], r12w
0x18001fc1b  xor     edx, edx; Val
0x18001fc1d  mov     r8d, 1FEh; Size
0x18001fc23  lea     rcx, [rbp+81D0h+var_824E]; void *
0x18001fc27  call    memset_0
0x18001fc2c  test    ebx, ebx
0x18001fc2e  jnz     loc_18001FDDE
0x18001fc34  mov     [rsp+82D0h+pcchName], 100h
0x18001fc3c  lea     r9, [rsp+82D0h+pcchName]; pcchName
0x18001fc41  lea     r8, [rbp+81D0h+pszName]; pszName
0x18001fc45  mov     edx, r14d; dwIndex
0x18001fc48  mov     rcx, [rsp+82D0h+hkey]; hkey
0x18001fc4d  call    cs:__imp_SHEnumKeyExW
0x18001fc53  mov     ebx, eax
0x18001fc55  cmp     eax, 103h
0x18001fc5a  jz      loc_18001FDE3
0x18001fc60  test    eax, eax
0x18001fc62  jnz     loc_18001FDD6
0x18001fc68  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc6f  lea     ecx, [rax+38h]; unsigned __int64
0x18001fc72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fc77  mov     rdi, rax
0x18001fc7a  mov     qword ptr [rsp+82D0h+pcchValueName], rax
0x18001fc7f  test    rax, rax
0x18001fc82  jz      short loc_18001FCD1
0x18001fc84  mov     [rax], r12
0x18001fc87  mov     [rax+8], r12
0x18001fc8b  mov     [rax+10h], r12d
0x18001fc8f  mov     [rax+18h], r12
0x18001fc93  mov     [rax+20h], r12d
0x18001fc97  mov     [rax+28h], r12
0x18001fc9b  mov     [rax+30h], r12
0x18001fc9f  test    rax, rax
0x18001fca2  jz      short loc_18001FCD4
0x18001fca4  lea     rdx, [rbp+81D0h+pszName]; wchar_t *
0x18001fca8  mov     rcx, rax; this
0x18001fcab  call    ?InitKeyCopy@CHashValueStringList@@QEAAJPEB_W@Z; CHashValueStringList::InitKeyCopy(wchar_t const *)
0x18001fcb0  mov     ebx, eax
0x18001fcb2  test    eax, eax
0x18001fcb4  js      short loc_18001FCC7
0x18001fcb6  lea     rcx, [r15+18h]
0x18001fcba  mov     r8, rdi
0x18001fcbd  mov     rdx, rdi
0x18001fcc0  call    ?Insert@?$CTKPLiteHashMap@VCStringHashKey@@VCHashValueStringList@@@@QEAAXPEAVCHashValueStringList@@PEAV?$CTPLiteLink@VCHashValueStringList@@@@@Z; CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Insert(CHashValueStringList *,CTPLiteLink<CHashValueStringList> *)
0x18001fcc5  jmp     short loc_18001FCD9
0x18001fcc7  mov     rcx, rdi; this
0x18001fcca  call    ??_GCHashValueStringList@@QEAAPEAXI@Z; CHashValueStringList::`scalar deleting destructor'(uint)
0x18001fccf  jmp     short loc_18001FCD9
0x18001fcd1  mov     rdi, r12
0x18001fcd4  mov     ebx, 8007000Eh
0x18001fcd9  mov     [rsp+82D0h+var_8288], r12
0x18001fcde  test    ebx, ebx
0x18001fce0  js      loc_18001FDC0
0x18001fce6  mov     [rsp+82D0h+var_8288], r12
0x18001fceb  lea     rax, [rsp+82D0h+var_8288]
0x18001fcf0  mov     [rsp+82D0h+pvData], rax; HKEY *
0x18001fcf5  mov     dword ptr [rsp+82D0h+pdwType], 20019h; unsigned int
0x18001fcfd  lea     r8, [rbp+81D0h+pszName]; wchar_t *
0x18001fd01  mov     rdx, [rsp+82D0h+hkey]; HKEY
0x18001fd06  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18001fd0b  test    eax, eax
0x18001fd0d  jz      short loc_18001FD1B
0x18001fd0f  jg      short loc_18001FD15
0x18001fd11  mov     ebx, eax
0x18001fd13  jmp     short loc_18001FD1B
0x18001fd15  movzx   ebx, ax
0x18001fd18  or      ebx, r13d
0x18001fd1b  test    ebx, ebx
0x18001fd1d  js      loc_18001FDC0
0x18001fd23  mov     [rbp+81D0h+pszValueName], r12w
0x18001fd2b  xor     edx, edx; Val
0x18001fd2d  mov     r8d, 7FFEh; Size
0x18001fd33  lea     rcx, [rbp+81D0h+var_804E]; void *
0x18001fd3a  call    memset_0
0x18001fd3f  mov     esi, r12d
0x18001fd42  test    ebx, ebx
0x18001fd44  jnz     short loc_18001FDB8
0x18001fd46  mov     [rsp+82D0h+pcchValueName], 4000h
0x18001fd4e  mov     [rsp+82D0h+var_8278], r12d
0x18001fd53  mov     [rsp+82D0h+var_827C], r12d
0x18001fd58  lea     rax, [rsp+82D0h+var_827C]
0x18001fd5d  mov     [rsp+82D0h+pcbData], rax; pcbData
0x18001fd62  mov     [rsp+82D0h+pvData], r12; pvData
0x18001fd67  lea     rax, [rsp+82D0h+var_8278]
0x18001fd6c  mov     [rsp+82D0h+pdwType], rax; pdwType
0x18001fd71  lea     r9, [rsp+82D0h+pcchValueName]; pcchValueName
0x18001fd76  lea     r8, [rbp+81D0h+pszValueName]; pszValueName
0x18001fd7d  mov     edx, esi; dwIndex
0x18001fd7f  mov     rcx, [rsp+82D0h+var_8288]; hkey
0x18001fd84  call    cs:__imp_SHEnumValueW
0x18001fd8a  mov     ebx, eax
0x18001fd8c  cmp     eax, 103h
0x18001fd91  jz      short loc_18001FDBD
0x18001fd93  test    eax, eax
0x18001fd95  jnz     short loc_18001FDB0
0x18001fd97  lea     rdx, [rbp+81D0h+pszValueName]; wchar_t *
0x18001fd9e  mov     rcx, rdi; this
0x18001fda1  call    ?AddStringCopyToList@CHashValueStringList@@QEAAJPEB_W@Z; CHashValueStringList::AddStringCopyToList(wchar_t const *)
0x18001fda6  mov     ebx, eax
0x18001fda8  test    eax, eax
0x18001fdaa  jnz     short loc_18001FDB8
0x18001fdac  inc     esi
0x18001fdae  jmp     short loc_18001FD46
0x18001fdb0  jle     short loc_18001FDC0
0x18001fdb2  movzx   ebx, ax
0x18001fdb5  or      ebx, r13d
0x18001fdb8  cmp     ebx, 1
0x18001fdbb  jnz     short loc_18001FDC0
0x18001fdbd  mov     ebx, r12d
0x18001fdc0  lea     rcx, [rsp+82D0h+var_8288]
0x18001fdc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fdca  test    ebx, ebx
0x18001fdcc  jnz     short loc_18001FDDE
0x18001fdce  inc     r14d
0x18001fdd1  jmp     loc_18001FC34
0x18001fdd6  jle     short loc_18001FDE6
0x18001fdd8  movzx   ebx, ax
0x18001fddb  or      ebx, r13d
0x18001fdde  cmp     ebx, 1
0x18001fde1  jnz     short loc_18001FDE6
0x18001fde3  mov     ebx, r12d
0x18001fde6  lea     rcx, [rsp+82D0h+var_8268]; this
0x18001fdeb  call    ?Unlock@CEfsMutexLock@@QEAAJXZ; CEfsMutexLock::Unlock(void)
0x18001fdf0  test    ebx, ebx
0x18001fdf2  js      short loc_18001FDF9
0x18001fdf4  test    eax, eax
0x18001fdf6  cmovs   ebx, eax
0x18001fdf9  lea     rcx, [rsp+82D0h+hkey]
0x18001fdfe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fe03  nop
0x18001fe04  lea     rcx, [rsp+82D0h+var_8268]
0x18001fe09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fe0e  mov     eax, ebx
0x18001fe10  mov     rcx, [rbp+81D0h+var_50]
0x18001fe17  xor     rcx, rsp; StackCookie
0x18001fe1a  call    __security_check_cookie
0x18001fe1f  add     rsp, 8298h
0x18001fe26  pop     r15
0x18001fe28  pop     r14
0x18001fe2a  pop     r13
0x18001fe2c  pop     r12
0x18001fe2e  pop     rdi
0x18001fe2f  pop     rsi
0x18001fe30  pop     rbx
0x18001fe31  pop     rbp
0x18001fe32  retn
```
