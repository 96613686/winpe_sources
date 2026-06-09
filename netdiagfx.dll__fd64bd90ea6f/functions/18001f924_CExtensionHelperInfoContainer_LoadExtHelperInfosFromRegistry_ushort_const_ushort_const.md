# CExtensionHelperInfoContainer::LoadExtHelperInfosFromRegistry(ushort const *,ushort const *)

- ea: `0x18001f924`
- end: `0x18001fe05`
- name: `?LoadExtHelperInfosFromRegistry@CExtensionHelperInfoContainer@@QEAAJPEBG0@Z`
- size: `1249`
- prototype: `__int64 __fastcall(CExtensionHelperInfoContainer *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f510`

## callees

- `0x180001ff4`
- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x18000821c`
- `0x180009e58`
- `0x180010368`
- `0x18001e980`
- `0x18001edc0`
- `0x18001f0a4`
- `0x18001f0d0`
- `0x18001f924`
- `0x18001fe0c`
- `0x180020abc`
- `0x180021094`
- `0x18002c840`

## string_xrefs

- `0x18001f9f4`: `\HostDLLs`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CExtensionHelperInfoContainer::LoadExtHelperInfosFromRegistry(
        CExtensionHelperInfoContainer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // r8
  __int64 v6; // r8
  LPCWSTR v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // r15d
  unsigned int v12; // r13d
  signed int v13; // eax
  __int64 v14; // r8
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // r12
  char *v17; // rax
  volatile signed __int32 *v18; // rsi
  int *v19; // rsi
  volatile signed __int32 *v20; // rbx
  CHostDLLInfo *v21; // rax
  ATL::CStringData *v22; // rax
  int PerDLLExtHelperInfosFromRegistry; // eax
  struct _FILETIME *v24; // [rsp+20h] [rbp-2F8h]
  unsigned int v25; // [rsp+34h] [rbp-2E4h]
  char *v26; // [rsp+38h] [rbp-2E0h] BYREF
  char *v27; // [rsp+40h] [rbp-2D8h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-2D0h] BYREF
  ATL::CStringData *v29; // [rsp+50h] [rbp-2C8h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-2C0h] BYREF
  volatile signed __int32 *v31; // [rsp+60h] [rbp-2B8h] BYREF
  CExtensionHelperInfoContainer *v32; // [rsp+68h] [rbp-2B0h]
  unsigned __int16 *v33; // [rsp+70h] [rbp-2A8h]
  ATL::CStringData *v34; // [rsp+78h] [rbp-2A0h]
  CExtensionHelperInfoContainer *v35; // [rsp+80h] [rbp-298h]
  unsigned __int16 *v36; // [rsp+90h] [rbp-288h]
  HKEY v37[4]; // [rsp+A0h] [rbp-278h] BYREF
  unsigned __int16 v38[264]; // [rsp+C0h] [rbp-258h] BYREF

  v33 = a2;
  v32 = this;
  v35 = this;
  v36 = a2;
  memset(v37, 0, 24);
  if ( a2 && a3 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpSubKey);
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&lpSubKey, a3, v5);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\", 1);
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a2, v6);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\HostDLLs", 9);
    v7 = lpSubKey;
    v8 = ATL::CRegKey::Open(v37, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
      ATL::CRegKey::Close(v37);
      return v9;
    }
    else
    {
      v11 = 0;
      v12 = 0;
      v25 = 0;
      while ( 1 )
      {
        v30 = 260;
        v13 = ATL::CRegKey::EnumKey((ATL::CRegKey *)v37, v12, v38, &v30, v24);
        if ( v13 )
          break;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v27);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v31,
          &lpSubKey);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v31, L"\\", 1);
        v14 = -1;
        do
          ++v14;
        while ( v38[v14] );
        ATL::CSimpleStringT<unsigned short,0>::Append(&v31, v38, v14);
        v15 = v31;
        v16 = v31 - 6;
        v34 = (ATL::CStringData *)(v31 - 6);
        v17 = v27 - 24;
        v29 = (ATL::CStringData *)(v27 - 24);
        if ( v31 - 6 != (volatile signed __int32 *)(v27 - 24) )
        {
          if ( *((int *)v17 + 4) >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
          {
            v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v31 - 6);
            ATL::CStringData::Release(v29);
            v27 = (char *)(v18 + 6);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, v31, *((_DWORD *)v31 - 4));
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::Append(&v27, L"\\DependentHelperClasses", 23);
        v19 = (int *)(v26 - 24);
        if ( v16 != (volatile signed __int32 *)(v26 - 24) )
        {
          if ( v19[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v19 )
          {
            v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
            ATL::CStringData::Release((ATL::CStringData *)v19);
            v26 = (char *)(v20 + 6);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v15, *((_DWORD *)v15 - 4));
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::Append(&v26, L"\\HelperClasses", 14);
        v21 = (CHostDLLInfo *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v37[3] = (HKEY)v21;
        if ( v21 )
          v22 = CHostDLLInfo::CHostDLLInfo(v21, v38, v33);
        else
          v22 = 0;
        v29 = v22;
        if ( v22 )
        {
          try
          {
            std::vector<CHostDLLInfo *>::push_back((char *)v32 + 24, &v29);
            CHostDLLInfo::LoadFromRegistry(v29, &v27);
          }
          catch ( exception )
          {
            ++v25;
            if ( v29 )
              CHostDLLInfo::`scalar deleting destructor'(v29);
            ATL::CStringData::Release(v34);
            ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
            ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
            v11 = -2147024882;
            v7 = lpSubKey;
            v12 = v25;
            v32 = v35;
            v33 = v36;
            continue;
          }
          PerDLLExtHelperInfosFromRegistry = CExtensionHelperInfoContainer::LoadPerDLLExtHelperInfosFromRegistry();
          v11 = 0;
          if ( PerDLLExtHelperInfosFromRegistry >= 0 )
            v11 = PerDLLExtHelperInfosFromRegistry;
          ATL::CStringData::Release((ATL::CStringData *)v16);
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
          v25 = ++v12;
        }
        else
        {
          if ( v11 >= 0 )
            v11 = -2147024882;
          v25 = ++v12;
          ATL::CStringData::Release((ATL::CStringData *)v16);
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
        }
      }
      if ( v13 != 259 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        if ( v11 >= 0 )
          v11 = v13;
      }
      ATL::CRegKey::Close(v37);
      ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
      ATL::CRegKey::Close(v37);
      return (unsigned int)v11;
    }
  }
  else
  {
    ATL::CRegKey::Close(v37);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001f924  push    rbx
0x18001f926  push    rsi
0x18001f927  push    rdi
0x18001f928  push    r12
0x18001f92a  push    r13
0x18001f92c  push    r14
0x18001f92e  push    r15
0x18001f930  sub     rsp, 2E0h
0x18001f937  mov     rax, cs:__security_cookie
0x18001f93e  xor     rax, rsp
0x18001f941  mov     [rsp+318h+var_48], rax
0x18001f949  mov     rbx, r8
0x18001f94c  mov     rsi, rdx
0x18001f94f  mov     [rsp+318h+var_2A8], rdx
0x18001f954  mov     [rsp+318h+var_2B0], rcx
0x18001f959  mov     [rsp+318h+var_298], rcx
0x18001f961  mov     [rsp+318h+var_288], rdx
0x18001f969  xor     r14d, r14d
0x18001f96c  mov     [rsp+318h+var_278], r14
0x18001f974  mov     [rsp+318h+var_270], r14
0x18001f97c  mov     [rsp+318h+var_268], r14
0x18001f984  test    rdx, rdx
0x18001f987  jz      loc_18001FDD0
0x18001f98d  test    rbx, rbx
0x18001f990  jz      loc_18001FDD0
0x18001f996  lea     rcx, [rsp+318h+lpSubKey]
0x18001f99b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001f9a0  nop
0x18001f9a1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f9a5  inc     r8
0x18001f9a8  cmp     [rbx+r8*2], r14w
0x18001f9ad  jnz     short loc_18001F9A5
0x18001f9af  mov     rdx, rbx
0x18001f9b2  lea     rcx, [rsp+318h+lpSubKey]
0x18001f9b7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f9bc  mov     r8d, 1
0x18001f9c2  lea     rdx, asc_180038274; "\\"
0x18001f9c9  lea     rcx, [rsp+318h+lpSubKey]
0x18001f9ce  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001f9d3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f9d7  inc     r8
0x18001f9da  cmp     [rsi+r8*2], r14w
0x18001f9df  jnz     short loc_18001F9D7
0x18001f9e1  mov     rdx, rsi
0x18001f9e4  lea     rcx, [rsp+318h+lpSubKey]
0x18001f9e9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001f9ee  mov     r8d, 9
0x18001f9f4  lea     rdx, aHostdlls; "\\HostDLLs"
0x18001f9fb  lea     rcx, [rsp+318h+lpSubKey]
0x18001fa00  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001fa05  mov     r9d, 20019h; unsigned int
0x18001fa0b  mov     rdi, [rsp+318h+lpSubKey]
0x18001fa10  mov     r8, rdi; lpSubKey
0x18001fa13  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001fa1a  lea     rcx, [rsp+318h+var_278]; this
0x18001fa22  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001fa27  mov     ebx, eax
0x18001fa29  test    eax, eax
0x18001fa2b  jz      short loc_18001FA56
0x18001fa2d  jle     short loc_18001FA38
0x18001fa2f  movzx   ebx, ax
0x18001fa32  or      ebx, 80070000h
0x18001fa38  lea     rcx, [rdi-18h]; this
0x18001fa3c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fa41  nop
0x18001fa42  lea     rcx, [rsp+318h+var_278]; this
0x18001fa4a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fa4f  mov     eax, ebx
0x18001fa51  jmp     loc_18001FDE2
0x18001fa56  mov     r15d, r14d
0x18001fa59  mov     [rsp+318h+var_2E8], r14d
0x18001fa5e  mov     r13d, r14d
0x18001fa61  mov     [rsp+318h+var_2E4], r14d
0x18001fa66  mov     [rsp+318h+var_2C0], 104h
0x18001fa6e  lea     r9, [rsp+318h+var_2C0]; unsigned int *
0x18001fa73  lea     r8, [rsp+318h+var_258]; unsigned __int16 *
0x18001fa7b  mov     edx, r13d; unsigned int
0x18001fa7e  lea     rcx, [rsp+318h+var_278]; this
0x18001fa86  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x18001fa8b  test    eax, eax
0x18001fa8d  jnz     loc_18001FD8C
0x18001fa93  lea     rcx, [rsp+318h+var_2D8]
0x18001fa98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001fa9d  nop
0x18001fa9e  lea     rcx, [rsp+318h+var_2E0]
0x18001faa3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001faa8  nop
0x18001faa9  lea     rdx, [rsp+318h+lpSubKey]
0x18001faae  lea     rcx, [rsp+318h+var_2B8]
0x18001fab3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001fab8  nop
0x18001fab9  mov     r8d, 1
0x18001fabf  lea     rdx, asc_180038274; "\\"
0x18001fac6  lea     rcx, [rsp+318h+var_2B8]
0x18001facb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001fad0  lea     rax, [rsp+318h+var_258]
0x18001fad8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fadc  inc     r8
0x18001fadf  cmp     [rax+r8*2], r14w
0x18001fae4  jnz     short loc_18001FADC
0x18001fae6  lea     rdx, [rsp+318h+var_258]
0x18001faee  lea     rcx, [rsp+318h+var_2B8]
0x18001faf3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001faf8  mov     rbx, [rsp+318h+var_2B8]
0x18001fafd  lea     r12, [rbx-18h]
0x18001fb01  mov     [rsp+318h+var_2A0], r12
0x18001fb06  mov     rax, [rsp+318h+var_2D8]
0x18001fb0b  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001fb0f  mov     [rsp+318h+var_2C8], rax
0x18001fb14  cmp     r12, rax
0x18001fb17  jz      short loc_18001FB59
0x18001fb19  cmp     [rax+10h], r14d
0x18001fb1d  jl      short loc_18001FB48
0x18001fb1f  mov     rax, [rax]
0x18001fb22  cmp     [r12], rax
0x18001fb26  jnz     short loc_18001FB48
0x18001fb28  mov     rcx, r12
0x18001fb2b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001fb30  mov     rsi, rax
0x18001fb33  mov     rcx, [rsp+318h+var_2C8]; this
0x18001fb38  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fb3d  lea     rax, [rsi+18h]
0x18001fb41  mov     [rsp+318h+var_2D8], rax
0x18001fb46  jmp     short loc_18001FB59
0x18001fb48  mov     r8d, [rbx-10h]
0x18001fb4c  mov     rdx, rbx
0x18001fb4f  lea     rcx, [rsp+318h+var_2D8]
0x18001fb54  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001fb59  mov     r8d, 17h
0x18001fb5f  lea     rdx, aDependenthelpe; "\\DependentHelperClasses"
0x18001fb66  lea     rcx, [rsp+318h+var_2D8]
0x18001fb6b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001fb70  mov     rsi, [rsp+318h+var_2E0]
0x18001fb75  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001fb79  cmp     r12, rsi
0x18001fb7c  jz      short loc_18001FBBC
0x18001fb7e  cmp     [rsi+10h], r14d
0x18001fb82  jl      short loc_18001FBAB
0x18001fb84  mov     rax, [rsi]
0x18001fb87  cmp     [r12], rax
0x18001fb8b  jnz     short loc_18001FBAB
0x18001fb8d  mov     rcx, r12
0x18001fb90  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001fb95  mov     rbx, rax
0x18001fb98  mov     rcx, rsi; this
0x18001fb9b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fba0  lea     rax, [rbx+18h]
0x18001fba4  mov     [rsp+318h+var_2E0], rax
0x18001fba9  jmp     short loc_18001FBBC
0x18001fbab  mov     r8d, [rbx-10h]
0x18001fbaf  mov     rdx, rbx
0x18001fbb2  lea     rcx, [rsp+318h+var_2E0]
0x18001fbb7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001fbbc  mov     r8d, 0Eh
0x18001fbc2  lea     rdx, aHelperclasses; "\\HelperClasses"
0x18001fbc9  lea     rcx, [rsp+318h+var_2E0]
0x18001fbce  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001fbd3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fbda  mov     ecx, 30h ; '0'; unsigned __int64
0x18001fbdf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fbe4  mov     [rsp+318h+var_260], rax
0x18001fbec  test    rax, rax
0x18001fbef  jz      short loc_18001FC08
0x18001fbf1  mov     r8, [rsp+318h+var_2A8]; unsigned __int16 *
0x18001fbf6  lea     rdx, [rsp+318h+var_258]; unsigned __int16 *
0x18001fbfe  mov     rcx, rax; this
0x18001fc01  call    ??0CHostDLLInfo@@QEAA@PEBG0@Z; CHostDLLInfo::CHostDLLInfo(ushort const *,ushort const *)
0x18001fc06  jmp     short loc_18001FC0B
0x18001fc08  mov     rax, r14
0x18001fc0b  mov     [rsp+318h+var_2C8], rax
0x18001fc10  test    rax, rax
0x18001fc13  jnz     short loc_18001FC59
0x18001fc15  mov     eax, 8007000Eh
0x18001fc1a  test    r15d, r15d
0x18001fc1d  cmovns  r15d, eax
0x18001fc21  mov     [rsp+318h+var_2E8], r15d
0x18001fc26  inc     r13d
0x18001fc29  mov     [rsp+318h+var_2E4], r13d
0x18001fc2e  mov     rcx, r12; this
0x18001fc31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fc36  nop
0x18001fc37  mov     rcx, [rsp+318h+var_2E0]
0x18001fc3c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fc40  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fc45  nop
0x18001fc46  mov     rcx, [rsp+318h+var_2D8]
0x18001fc4b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fc4f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fc54  jmp     loc_18001FA66
0x18001fc59  mov     rsi, [rsp+318h+var_2B0]
0x18001fc5e  lea     rcx, [rsi+18h]
0x18001fc62  lea     rdx, [rsp+318h+var_2C8]
0x18001fc67  call    ?push_back@?$vector@PEAVCHostDLLInfo@@V?$allocator@PEAVCHostDLLInfo@@@std@@@std@@QEAAXAEBQEAVCHostDLLInfo@@@Z; std::vector<CHostDLLInfo *>::push_back(CHostDLLInfo * const &)
0x18001fc6c  nop
0x18001fc6d  lea     rdx, [rsp+318h+var_2D8]
0x18001fc72  mov     rcx, [rsp+318h+var_2C8]
0x18001fc77  call    ?LoadFromRegistry@CHostDLLInfo@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CHostDLLInfo::LoadFromRegistry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001fc7c  test    eax, eax
0x18001fc7e  cmovs   eax, r14d
0x18001fc82  mov     [rsp+318h+var_2E8], eax
0x18001fc86  mov     r8, [rsp+318h+var_2C8]
0x18001fc8b  lea     rdx, [rsp+318h+var_2E0]
0x18001fc90  mov     rcx, rsi
0x18001fc93  call    ?LoadPerDLLExtHelperInfosFromRegistry@CExtensionHelperInfoContainer@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBVCHostDLLInfo@@@Z; CExtensionHelperInfoContainer::LoadPerDLLExtHelperInfosFromRegistry(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CHostDLLInfo const *)
0x18001fc98  nop
0x18001fc99  mov     r15d, r14d
0x18001fc9c  test    eax, eax
0x18001fc9e  cmovns  r15d, eax
0x18001fca2  mov     rcx, r12; this
0x18001fca5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fcaa  nop
0x18001fcab  mov     rcx, [rsp+318h+var_2E0]
0x18001fcb0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fcb4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fcb9  nop
0x18001fcba  mov     rcx, [rsp+318h+var_2D8]
0x18001fcbf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fcc3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fcc8  mov     [rsp+318h+var_2E8], r15d
0x18001fccd  inc     r13d
0x18001fcd0  mov     [rsp+318h+var_2E4], r13d
0x18001fcd5  jmp     loc_18001FA66
0x18001fcda  mov     rcx, [rsp+318h+var_2A0]; this
0x18001fcdf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fce4  nop
0x18001fce5  mov     rcx, [rsp+318h+var_2E0]
0x18001fcea  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fcee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fcf3  nop
0x18001fcf4  mov     rcx, [rsp+318h+var_2D8]
0x18001fcf9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fcfd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fd02  xor     r14d, r14d
0x18001fd05  mov     r15d, [rsp+318h+var_2E8]
0x18001fd0a  mov     rdi, [rsp+318h+lpSubKey]
0x18001fd0f  mov     r13d, [rsp+318h+var_2E4]
0x18001fd14  mov     rax, [rsp+318h+var_298]
0x18001fd1c  mov     [rsp+318h+var_2B0], rax
0x18001fd21  mov     rbx, [rsp+318h+var_288]
0x18001fd29  mov     [rsp+318h+var_2A8], rbx
0x18001fd2e  jmp     loc_18001FA66
0x18001fd33  mov     rcx, [rsp+318h+var_2A0]; this
0x18001fd38  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fd3d  nop
0x18001fd3e  mov     rcx, [rsp+318h+var_2E0]
0x18001fd43  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fd47  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fd4c  nop
0x18001fd4d  mov     rcx, [rsp+318h+var_2D8]
0x18001fd52  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001fd56  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fd5b  xor     r14d, r14d
0x18001fd5e  mov     r15d, [rsp+318h+var_2E8]
0x18001fd63  mov     rdi, [rsp+318h+lpSubKey]
0x18001fd68  mov     r13d, [rsp+318h+var_2E4]
0x18001fd6d  mov     rax, [rsp+318h+var_298]
0x18001fd75  mov     [rsp+318h+var_2B0], rax
0x18001fd7a  mov     rax, [rsp+318h+var_288]
0x18001fd82  mov     [rsp+318h+var_2A8], rax
0x18001fd87  jmp     loc_18001FA66
0x18001fd8c  cmp     eax, 103h
0x18001fd91  jz      short loc_18001FDA6
0x18001fd93  test    eax, eax
0x18001fd95  jle     short loc_18001FD9F
0x18001fd97  movzx   eax, ax
0x18001fd9a  or      eax, 80070000h
0x18001fd9f  test    r15d, r15d
0x18001fda2  cmovns  r15d, eax
0x18001fda6  lea     rcx, [rsp+318h+var_278]; this
0x18001fdae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fdb3  nop
0x18001fdb4  lea     rcx, [rdi-18h]; this
0x18001fdb8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001fdbd  nop
0x18001fdbe  lea     rcx, [rsp+318h+var_278]; this
0x18001fdc6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fdcb  mov     eax, r15d
0x18001fdce  jmp     short loc_18001FDE2
0x18001fdd0  lea     rcx, [rsp+318h+var_278]; this
0x18001fdd8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001fddd  mov     eax, 80070057h
0x18001fde2  mov     rcx, [rsp+318h+var_48]
0x18001fdea  xor     rcx, rsp; StackCookie
0x18001fded  call    __security_check_cookie
0x18001fdf2  add     rsp, 2E0h
0x18001fdf9  pop     r15
0x18001fdfb  pop     r14
0x18001fdfd  pop     r13
0x18001fdff  pop     r12
0x18001fe01  pop     rdi
0x18001fe02  pop     rsi
0x18001fe03  pop     rbx
0x18001fe04  retn
```
