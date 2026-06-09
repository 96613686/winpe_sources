# container::RegistryProvider::SetupHivestack(Schema::Containers::Definition::RegistryHiveStack const &,void *,void *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x180029bc0`
- end: `0x18002a388`
- name: `?SetupHivestack@RegistryProvider@container@@YAXAEBURegistryHiveStack@Definition@Containers@Schema@@PEAX1AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1992`
- prototype: `__int64 __fastcall(void **, __int64, void *, __int64 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180029a1c`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180002ee4`
- `0x180004c40`
- `0x1800051b0`
- `0x18000d668`
- `0x180012b10`
- `0x180012b30`
- `0x180021b68`
- `0x180022044`
- `0x180022094`
- `0x180022b54`
- `0x180022eac`
- `0x180023bdc`
- `0x180023e44`
- `0x180027610`
- `0x1800277a8`
- `0x1800279c4`
- `0x18002841c`
- `0x1800286cc`
- `0x180028878`
- `0x180028a70`
- `0x180028d8c`
- `0x180029268`
- `0x1800295f0`
- `0x180029888`
- `0x180029bc0`
- `0x18002a390`
- `0x18002b464`
- `0x18002c500`
- `0x180034010`

## import_xrefs

- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002a0bf`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002a0bf`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002a0cf`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002a0cf`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002a13a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2d4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029f2d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029f2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a28a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a28a`

## string_xrefs

- `0x18002a376`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
__int64 __fastcall container::RegistryProvider::SetupHivestack(void **a1, __int64 a2, void *a3, __int64 *a4)
{
  __int64 *v6; // r15
  void *v7; // rax
  unsigned int v8; // r14d
  __int64 i; // rdx
  __int64 v10; // rsi
  int v11; // ebx
  int v12; // eax
  _QWORD *v13; // rax
  __int64 v14; // rax
  _DWORD *v15; // r12
  int v16; // eax
  int v17; // ecx
  unsigned __int64 v18; // rdx
  const struct Schema::Containers::Definition::RegistryMakeKey *v19; // rbx
  void *v20; // r8
  container::RegistryProvider *v21; // r14
  container::RegistryProvider *j; // rsi
  _QWORD *v23; // rsi
  _QWORD *v24; // r14
  __int128 *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // rax
  wchar_t **v30; // r14
  wchar_t **v31; // rcx
  wchar_t **v32; // rdi
  wchar_t **v33; // rsi
  __int64 inserted; // rdi
  const wchar_t *v35; // rdx
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // r14
  const wchar_t *v38; // rcx
  size_t v39; // r8
  int v40; // eax
  __int64 v41; // rdi
  _OWORD *v42; // rax
  signed int LastError; // eax
  unsigned int v45; // ebx
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  int lpOverlapped; // [rsp+38h] [rbp-C8h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+54h] [rbp-ACh] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v51; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD nInBufferSize[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h]
  LPVOID lpInBuffer; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hDevice; // [rsp+90h] [rbp-70h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v59[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v61[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v62[120]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v63[104]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *S1[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v65; // [rsp+1C0h] [rbp+C0h]
  __int128 v66; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v67; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v68; // [rsp+1E8h] [rbp+E8h]
  __int128 v69; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v70; // [rsp+200h] [rbp+100h]
  __int64 v71; // [rsp+208h] [rbp+108h]
  _BYTE v72[16]; // [rsp+210h] [rbp+110h] BYREF
  __int16 v73; // [rsp+220h] [rbp+120h]
  _BYTE v74[16]; // [rsp+230h] [rbp+130h] BYREF
  __int16 v75; // [rsp+240h] [rbp+140h]
  _BYTE v76[32]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  hDevice = a3;
  v56 = a2;
  v51 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 7;
  LOWORD(v66) = 0;
  v48 = 0;
  v49 = ((_BYTE *)a1[11] - (_BYTE *)a1[10]) >> 5;
  nInBufferSize[0] = -286331153 * (((_BYTE *)a1[8] - (_BYTE *)a1[7]) >> 3);
  v6 = (__int64 *)(a1 + 4);
  BytesReturned = -1431655765 * (((_BYTE *)a1[5] - (_BYTE *)a1[4]) >> 5);
  if ( (unsigned __int64)a1[3] <= 7 )
    v7 = a1;
  else
    v7 = *a1;
  lpInBuffer = v7;
  ContainerProvider::CreateRegHivestack<unsigned short const *,unsigned int,unsigned int,unsigned int>(
    &lpInBuffer,
    &BytesReturned,
    nInBufferSize,
    &v49);
  v8 = 0;
  for ( i = *v6; v8 < 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)a1[5] - (_BYTE *)a1[4]) >> 5); i = *v6 )
  {
    v10 = i + 96LL * v8;
    if ( *(_QWORD *)(v10 + 16) )
    {
      v48 = 1;
      std::wstring::operator=(&v66, i + 96LL * v8);
    }
    else
    {
      v11 = 256;
      v49 = 256;
      v12 = 256;
      if ( *(_BYTE *)(v10 + 80) )
      {
        v11 = 8448;
        v49 = 8448;
        v12 = 8448;
      }
      if ( *(_BYTE *)(v10 + 81) )
      {
        v11 = v12 | 0x4000;
        v49 = v12 | 0x4000;
      }
      std::wstring::wstring(v74, v10 + 32);
      v69 = 0;
      v70 = 0;
      v71 = 7;
      LOWORD(v69) = 0;
      if ( v8 )
      {
        std::wstring::operator=(&v69, &v66);
      }
      else
      {
        v70 = 0;
        LOWORD(v69) = 0;
      }
      *(_QWORD *)&v58 = v10 + 64;
      v13 = (_QWORD *)windows_wrappers::StringFromGuid(v76, v10 + 64);
      container::RegistryProvider::GetRootPath((__int64)v72, v13, (__int64)a1);
      std::wstring::~wstring(v76);
      v53 = 0;
      v54 = 0;
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v53, 0, v72);
      if ( *((_QWORD *)&v53 + 1) == v54 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v53, *((_QWORD *)&v53 + 1), v74);
        v14 = *((_QWORD *)&v53 + 1);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v53 + 1), v74);
        v14 = *((_QWORD *)&v53 + 1) + 32LL;
        *((_QWORD *)&v53 + 1) += 32LL;
      }
      if ( v14 == v54 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v53, v14, &v69);
      }
      else
      {
        std::wstring::wstring(v14, &v69);
        *((_QWORD *)&v53 + 1) += 32LL;
      }
      *(_QWORD *)nInBufferSize = 0;
      lpInBuffer = 0;
      container::RegistryProvider::BuildTightlyPackgedStringBuffer(0x28u);
      v15 = lpInBuffer;
      *(_QWORD *)lpInBuffer = v56;
      v15[2] = v48;
      v16 = v15[3] ^ (v15[3] ^ *(unsigned __int8 *)(v10 + 82)) & 1;
      v15[3] = v16;
      v17 = v16 ^ ((unsigned __int8)v16 ^ (unsigned __int8)(4 * *(_BYTE *)(v10 + 83))) & 4;
      v15[3] = v17;
      v15[3] = v17 ^ ((unsigned __int8)v17 ^ (unsigned __int8)(2 * *(_BYTE *)(v10 + 84))) & 2;
      *((_QWORD *)v15 + 4) = *(_QWORD *)(v10 + 88);
      v15[4] = v11;
      *((_WORD *)v15 + 10) = 2 * v73;
      *((_WORD *)v15 + 11) = 2 * v75;
      *((_WORD *)v15 + 12) = 2 * v70;
      BytesReturned = 0;
      if ( !DeviceIoControl(hDevice, 0x220008u, v15, nInBufferSize[0], 0, 0, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        v45 = LastError;
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        nInBufferSize[0] = LastError;
        v48 = std::vector<Schema::Containers::Definition::RegistryLayer>::size(a1 + 4);
        v51 = v8;
        hDevice = (HANDLE)std::wstring::c_str(v72);
        v56 = std::wstring::c_str(a1);
        v59[0] = std::wstring::c_str(v74);
        ContainerProvider::RegistryHiveLoadFailureDetailed<unsigned short const *,unsigned short const *,unsigned short const *,_GUID const &,unsigned int,unsigned int,long,unsigned short const (&)[57],unsigned long &>(
          (unsigned int)v59,
          (unsigned int)&v56,
          (unsigned int)&hDevice,
          v58,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)nInBufferSize,
          lpOverlapped,
          (__int64)&v49);
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
          (const char *)v45,
          lpOutBuffer);
      }
      v48 = 0;
      std::wstring::operator=(&v66, v72);
      if ( v15 )
        operator delete(v15, v18);
      std::vector<std::wstring>::_Tidy(&v53);
      std::wstring::~wstring(v72);
      std::wstring::~wstring(&v69);
      std::wstring::~wstring(v74);
    }
    ++v8;
  }
  v19 = (const struct Schema::Containers::Definition::RegistryMakeKey *)container::Registry::OpenKey(&v66, 131097);
  v59[0] = v19;
  v21 = (container::RegistryProvider *)a1[8];
  for ( j = (container::RegistryProvider *)a1[7]; j != v21; j = (container::RegistryProvider *)((char *)j + 120) )
    container::RegistryProvider::SetupMakeKey(j, v19, v20);
  v23 = a1[10];
  v24 = a1[11];
  while ( v23 != v24 )
  {
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v60);
    v25 = &v66;
    if ( v68 > 7 )
      v25 = (__int128 *)v66;
    v26 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(&v60, v25, v67);
    v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26);
    if ( v23[3] <= 7u )
      v28 = v23;
    else
      v28 = (_QWORD *)*v23;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v27, v28, v23[2]);
    v29 = std::basic_ostringstream<unsigned short>::str(&v60, v76);
    container::Registry::DeleteKeyAndSubkeys(v29);
    std::wstring::~wstring(v76);
    *(_QWORD *)&v61[*(int *)(v60 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
    *(_DWORD *)((char *)&v59[1] + *(int *)(v60 + 4) + 4) = *(_DWORD *)(v60 + 4) - 136;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v61);
    std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v62);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v63);
    v23 += 4;
  }
  std::wstring::wstring(S1, a1);
  v51 = 1;
  v30 = S1;
  if ( *((_QWORD *)&v65 + 1) > 7u )
    v30 = (wchar_t **)S1[0];
  v31 = S1;
  if ( *((_QWORD *)&v65 + 1) > 7u )
    v31 = (wchar_t **)S1[0];
  v32 = (wchar_t **)((char *)v31 + 2 * v65);
  v33 = S1;
  if ( *((_QWORD *)&v65 + 1) > 7u )
    v33 = (wchar_t **)S1[0];
  while ( v33 != v32 )
  {
    *(_WORD *)v30 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)v33);
    v30 = (wchar_t **)((char *)v30 + 2);
    v33 = (wchar_t **)((char *)v33 + 2);
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
    a4,
    &v53,
    S1);
  inserted = v54;
  if ( !*(_BYTE *)(v54 + 25) )
  {
    v35 = (const wchar_t *)(v54 + 32);
    v36 = *(_QWORD *)(v54 + 48);
    if ( *(_QWORD *)(v54 + 56) > 7u )
      v35 = *(const wchar_t **)v35;
    v37 = v65;
    v38 = (const wchar_t *)S1;
    if ( *((_QWORD *)&v65 + 1) > 7u )
      v38 = S1[0];
    v39 = v65;
    if ( v36 < (unsigned __int64)v65 )
      v39 = *(_QWORD *)(v54 + 48);
    v40 = wmemcmp(v38, v35, v39);
    if ( v40 )
    {
      if ( v40 >= 0 )
        goto LABEL_58;
    }
    else if ( v37 >= v36 )
    {
      goto LABEL_58;
    }
  }
  if ( a4[1] == 0x2AAAAAAAAAAAAAALL )
    std::_Throw_tree_length_error();
  v41 = *a4;
  v58 = (unsigned __int64)a4;
  v42 = operator new(0x60u);
  v42[2] = *(_OWORD *)S1;
  v42[3] = v65;
  *(_QWORD *)&v65 = 0;
  *((_QWORD *)&v65 + 1) = 7;
  LOWORD(S1[0]) = 0;
  v42[4] = 0;
  *((_QWORD *)v42 + 10) = 0;
  *((_QWORD *)v42 + 11) = 7;
  *((_WORD *)v42 + 32) = 0;
  *(_QWORD *)v42 = v41;
  *((_QWORD *)v42 + 1) = v41;
  *((_QWORD *)v42 + 2) = v41;
  *((_WORD *)v42 + 12) = 0;
  v58 = v53;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Insert_node(a4, &v58, v42);
LABEL_58:
  std::wstring::operator=(inserted + 64, &v66);
  std::wstring::~wstring(S1);
  if ( (unsigned __int64)v19 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v19);
  return std::wstring::~wstring(&v66);
}

```

## disassembly

```asm
0x180029bc0  mov     [rsp-8+arg_8], rbx
0x180029bc5  push    rbp
0x180029bc6  push    rsi
0x180029bc7  push    rdi
0x180029bc8  push    r12
0x180029bca  push    r13
0x180029bcc  push    r14
0x180029bce  push    r15
0x180029bd0  lea     rbp, [rsp-180h]
0x180029bd8  sub     rsp, 280h
0x180029bdf  mov     rax, cs:__security_cookie
0x180029be6  xor     rax, rsp
0x180029be9  mov     [rbp+1B0h+var_40], rax
0x180029bf0  mov     r13, r9
0x180029bf3  mov     [rbp+1B0h+hDevice], r8
0x180029bf7  mov     [rbp+1B0h+var_228], rdx
0x180029bfb  mov     rdi, rcx
0x180029bfe  xor     r12d, r12d
0x180029c01  mov     [rsp+2B0h+var_254], r12d
0x180029c06  xorps   xmm0, xmm0
0x180029c09  movups  [rbp+1B0h+var_E0], xmm0
0x180029c10  mov     [rbp+1B0h+var_D0], r12
0x180029c17  mov     [rbp+1B0h+var_C8], 7
0x180029c22  mov     word ptr [rbp+1B0h+var_E0], r12w
0x180029c2a  mov     [rsp+2B0h+var_260], r12d
0x180029c2f  mov     rax, [rcx+58h]
0x180029c33  sub     rax, [rcx+50h]
0x180029c37  sar     rax, 5
0x180029c3b  mov     [rsp+2B0h+var_25C], eax
0x180029c3f  mov     rax, [rcx+40h]
0x180029c43  sub     rax, [rcx+38h]
0x180029c47  sar     rax, 3
0x180029c4b  mov     rcx, 0EEEEEEEEEEEEEEEFh
0x180029c55  imul    rax, rcx
0x180029c59  mov     [rsp+2B0h+nInBufferSize], eax
0x180029c5d  lea     r15, [rdi+20h]
0x180029c61  mov     rax, [r15+8]
0x180029c65  sub     rax, [r15]
0x180029c68  sar     rax, 5
0x180029c6c  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180029c76  imul    rax, rbx
0x180029c7a  mov     [rsp+2B0h+BytesReturned], eax
0x180029c7e  cmp     qword ptr [rdi+18h], 7
0x180029c83  jbe     short loc_180029C8A
0x180029c85  mov     rax, [rdi]
0x180029c88  jmp     short loc_180029C8D
0x180029c8a  mov     rax, rdi
0x180029c8d  mov     [rbp+1B0h+lpInBuffer], rax
0x180029c91  lea     r9, [rsp+2B0h+var_25C]
0x180029c96  lea     r8, [rsp+2B0h+nInBufferSize]
0x180029c9b  lea     rdx, [rsp+2B0h+BytesReturned]
0x180029ca0  lea     rcx, [rbp+1B0h+lpInBuffer]
0x180029ca4  call    ??$CreateRegHivestack@PEBGIII@ContainerProvider@@SAX$$QEAPEBG$$QEAI11@Z; ContainerProvider::CreateRegHivestack<ushort const *,uint,uint,uint>(ushort const * &&,uint &&,uint &&,uint &&)
0x180029ca9  mov     r14d, r12d
0x180029cac  mov     rdx, [r15]
0x180029caf  mov     rax, [r15+8]
0x180029cb3  sub     rax, rdx
0x180029cb6  sar     rax, 5
0x180029cba  imul    rax, rbx
0x180029cbe  test    rax, rax
0x180029cc1  jz      loc_180029FC6
0x180029cc7  mov     eax, r14d
0x180029cca  lea     rsi, [rax+rax*2]
0x180029cce  shl     rsi, 5
0x180029cd2  add     rsi, rdx
0x180029cd5  cmp     [rsi+10h], r12
0x180029cd9  jz      short loc_180029CF7
0x180029cdb  mov     [rsp+2B0h+var_260], 1
0x180029ce3  mov     rdx, rsi
0x180029ce6  lea     rcx, [rbp+1B0h+var_E0]
0x180029ced  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180029cf2  jmp     loc_180029FA5
0x180029cf7  mov     ebx, 100h
0x180029cfc  mov     [rsp+2B0h+var_25C], ebx
0x180029d00  mov     eax, ebx
0x180029d02  cmp     [rsi+50h], r12b
0x180029d06  jz      short loc_180029D13
0x180029d08  mov     ebx, 2100h
0x180029d0d  mov     [rsp+2B0h+var_25C], ebx
0x180029d11  mov     eax, ebx
0x180029d13  cmp     [rsi+51h], r12b
0x180029d17  jz      short loc_180029D23
0x180029d19  mov     ebx, eax
0x180029d1b  bts     ebx, 0Eh
0x180029d1f  mov     [rsp+2B0h+var_25C], ebx
0x180029d23  lea     rdx, [rsi+20h]
0x180029d27  lea     rcx, [rbp+1B0h+var_80]
0x180029d2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180029d33  nop
0x180029d34  xorps   xmm0, xmm0
0x180029d37  movups  [rbp+1B0h+var_C0], xmm0
0x180029d3e  mov     [rbp+1B0h+var_B0], r12
0x180029d45  mov     [rbp+1B0h+var_A8], 7
0x180029d50  mov     word ptr [rbp+1B0h+var_C0], r12w
0x180029d58  test    r14d, r14d
0x180029d5b  jnz     short loc_180029D6E
0x180029d5d  mov     [rbp+1B0h+var_B0], r12
0x180029d64  mov     word ptr [rbp+1B0h+var_C0], r12w
0x180029d6c  jmp     short loc_180029D81
0x180029d6e  lea     rdx, [rbp+1B0h+var_E0]
0x180029d75  lea     rcx, [rbp+1B0h+var_C0]
0x180029d7c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180029d81  lea     rax, [rsi+40h]
0x180029d85  mov     qword ptr [rbp+1B0h+var_210], rax
0x180029d89  mov     rdx, rax
0x180029d8c  lea     rcx, [rbp+1B0h+var_60]
0x180029d93  call    ?StringFromGuid@windows_wrappers@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; windows_wrappers::StringFromGuid(_GUID const &)
0x180029d98  nop
0x180029d99  mov     r8, rdi
0x180029d9c  mov     rdx, rax
0x180029d9f  lea     rcx, [rbp+1B0h+var_A0]
0x180029da6  call    ?GetRootPath@RegistryProvider@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z; container::RegistryProvider::GetRootPath(std::wstring const &,std::wstring const &)
0x180029dab  nop
0x180029dac  lea     rcx, [rbp+1B0h+var_60]
0x180029db3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029db8  xorps   xmm0, xmm0
0x180029dbb  movdqu  [rsp+2B0h+var_248], xmm0
0x180029dc1  mov     [rsp+2B0h+var_238], r12
0x180029dc6  lea     r8, [rbp+1B0h+var_A0]
0x180029dcd  xor     edx, edx
0x180029dcf  lea     rcx, [rsp+2B0h+var_248]
0x180029dd4  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180029dd9  mov     rax, qword ptr [rsp+2B0h+var_248+8]
0x180029dde  cmp     rax, [rsp+2B0h+var_238]
0x180029de3  jz      short loc_180029E04
0x180029de5  lea     rdx, [rbp+1B0h+var_80]
0x180029dec  mov     rcx, rax
0x180029def  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180029df4  mov     rax, qword ptr [rsp+2B0h+var_248+8]
0x180029df9  add     rax, 20h ; ' '
0x180029dfd  mov     qword ptr [rsp+2B0h+var_248+8], rax
0x180029e02  jmp     short loc_180029E1D
0x180029e04  lea     r8, [rbp+1B0h+var_80]
0x180029e0b  mov     rdx, rax
0x180029e0e  lea     rcx, [rsp+2B0h+var_248]
0x180029e13  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180029e18  mov     rax, qword ptr [rsp+2B0h+var_248+8]
0x180029e1d  cmp     rax, [rsp+2B0h+var_238]
0x180029e22  jz      short loc_180029E3B
0x180029e24  lea     rdx, [rbp+1B0h+var_C0]
0x180029e2b  mov     rcx, rax
0x180029e2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180029e33  add     qword ptr [rsp+2B0h+var_248+8], 20h ; ' '
0x180029e39  jmp     short loc_180029E4F
0x180029e3b  lea     r8, [rbp+1B0h+var_C0]
0x180029e42  mov     rdx, rax
0x180029e45  lea     rcx, [rsp+2B0h+var_248]
0x180029e4a  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180029e4f  mov     qword ptr [rsp+2B0h+nInBufferSize], r12
0x180029e54  mov     [rbp+1B0h+lpInBuffer], r12
0x180029e58  lea     r9, [rsp+2B0h+nInBufferSize]
0x180029e5d  lea     r8, [rbp+1B0h+lpInBuffer]
0x180029e61  lea     rdx, [rsp+2B0h+var_248]
0x180029e66  mov     ecx, 28h ; '('; unsigned __int64
0x180029e6b  call    ?BuildTightlyPackgedStringBuffer@RegistryProvider@container@@YAX_KAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@4@PEA_K@Z; container::RegistryProvider::BuildTightlyPackgedStringBuffer(unsigned __int64,std::vector<std::wstring> const &,std::unique_ptr<uchar [0]> *,unsigned __int64 *)
0x180029e70  mov     r12, [rbp+1B0h+lpInBuffer]
0x180029e74  mov     rax, [rbp+1B0h+var_228]
0x180029e78  mov     [r12], rax
0x180029e7c  mov     eax, [rsp+2B0h+var_260]
0x180029e80  mov     [r12+8], eax
0x180029e85  movzx   eax, byte ptr [rsi+52h]
0x180029e89  xor     eax, [r12+0Ch]
0x180029e8e  and     eax, 1
0x180029e91  xor     eax, [r12+0Ch]
0x180029e96  mov     [r12+0Ch], eax
0x180029e9b  movzx   ecx, byte ptr [rsi+53h]
0x180029e9f  shl     ecx, 2
0x180029ea2  xor     ecx, eax
0x180029ea4  and     ecx, 4
0x180029ea7  xor     ecx, eax
0x180029ea9  mov     [r12+0Ch], ecx
0x180029eae  movzx   eax, byte ptr [rsi+54h]
0x180029eb2  add     eax, eax
0x180029eb4  xor     eax, ecx
0x180029eb6  and     eax, 2
0x180029eb9  xor     eax, ecx
0x180029ebb  mov     [r12+0Ch], eax
0x180029ec0  mov     rax, [rsi+58h]
0x180029ec4  mov     [r12+20h], rax
0x180029ec9  mov     [r12+10h], ebx
0x180029ece  movzx   eax, [rbp+1B0h+var_90]
0x180029ed5  add     ax, ax
0x180029ed8  mov     [r12+14h], ax
0x180029ede  movzx   eax, [rbp+1B0h+var_70]
0x180029ee5  add     ax, ax
0x180029ee8  mov     [r12+16h], ax
0x180029eee  movzx   eax, word ptr [rbp+1B0h+var_B0]
0x180029ef5  add     ax, ax
0x180029ef8  mov     [r12+18h], ax
0x180029efe  xor     esi, esi
0x180029f00  mov     [rsp+2B0h+BytesReturned], esi
0x180029f04  mov     [rsp+2B0h+lpOverlapped], rsi; lpOverlapped
0x180029f09  lea     rax, [rsp+2B0h+BytesReturned]
0x180029f0e  mov     [rsp+2B0h+lpBytesReturned], rax; lpBytesReturned
0x180029f13  mov     [rsp+2B0h+nOutBufferSize], esi; nOutBufferSize
0x180029f17  mov     [rsp+2B0h+lpOutBuffer], rsi; lpOutBuffer
0x180029f1c  mov     r9d, [rsp+2B0h+nInBufferSize]; nInBufferSize
0x180029f21  mov     r8, r12; lpInBuffer
0x180029f24  mov     edx, 220008h; dwIoControlCode
0x180029f29  mov     rcx, [rbp+1B0h+hDevice]; hDevice
0x180029f2d  call    cs:__imp_DeviceIoControl
0x180029f34  nop     dword ptr [rax+rax+00h]
0x180029f39  test    eax, eax
0x180029f3b  jz      loc_18002A2D4
0x180029f41  mov     [rsp+2B0h+var_260], esi
0x180029f45  lea     rdx, [rbp+1B0h+var_A0]
0x180029f4c  lea     rcx, [rbp+1B0h+var_E0]
0x180029f53  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180029f58  nop
0x180029f59  test    r12, r12
0x180029f5c  jz      short loc_180029F67
0x180029f5e  mov     rcx, r12; void *
0x180029f61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029f66  nop
0x180029f67  lea     rcx, [rsp+2B0h+var_248]
0x180029f6c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180029f71  nop
0x180029f72  lea     rcx, [rbp+1B0h+var_A0]
0x180029f79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029f7e  nop
0x180029f7f  lea     rcx, [rbp+1B0h+var_C0]
0x180029f86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029f8b  nop
0x180029f8c  lea     rcx, [rbp+1B0h+var_80]
0x180029f93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029f98  xor     r12d, r12d
0x180029f9b  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180029fa5  inc     r14d
0x180029fa8  mov     rdx, [r15]
0x180029fab  mov     rcx, [r15+8]
0x180029faf  sub     rcx, rdx
0x180029fb2  sar     rcx, 5
0x180029fb6  imul    rcx, rbx
0x180029fba  mov     eax, r14d
0x180029fbd  cmp     rax, rcx
0x180029fc0  jb      loc_180029CC7
0x180029fc6  mov     edx, 20019h
0x180029fcb  lea     rcx, [rbp+1B0h+var_E0]
0x180029fd2  call    ?OpenKey@Registry@container@@YAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; container::Registry::OpenKey(std::wstring const &,ulong)
0x180029fd7  mov     rbx, rax
0x180029fda  mov     [rbp+1B0h+var_200], rax
0x180029fde  mov     r14, [rdi+40h]
0x180029fe2  mov     rsi, [rdi+38h]
0x180029fe6  jmp     short loc_180029FF7
0x180029fe8  mov     rdx, rbx; struct Schema::Containers::Definition::RegistryMakeKey *
0x180029feb  mov     rcx, rsi; this
0x180029fee  call    ?SetupMakeKey@RegistryProvider@container@@YAXAEBURegistryMakeKey@Definition@Containers@Schema@@PEAX@Z; container::RegistryProvider::SetupMakeKey(Schema::Containers::Definition::RegistryMakeKey const &,void *)
0x180029ff3  add     rsi, 78h ; 'x'
0x180029ff7  cmp     rsi, r14
0x180029ffa  jnz     short loc_180029FE8
0x180029ffc  mov     rsi, [rdi+50h]
0x18002a000  mov     r14, [rdi+58h]
0x18002a004  mov     r15d, 7
0x18002a00a  cmp     rsi, r14
0x18002a00d  jz      loc_18002A0E4
0x18002a013  lea     rcx, [rbp+1B0h+var_1F0]
0x18002a017  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002a01c  nop
0x18002a01d  lea     rdx, [rbp+1B0h+var_E0]
0x18002a024  cmp     [rbp+1B0h+var_C8], r15
0x18002a02b  cmova   rdx, qword ptr [rbp+1B0h+var_E0]
0x18002a033  mov     r8, [rbp+1B0h+var_D0]
0x18002a03a  lea     rcx, [rbp+1B0h+var_1F0]
0x18002a03e  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002a043  mov     rcx, rax
0x18002a046  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002a04b  cmp     [rsi+18h], r15
0x18002a04f  jbe     short loc_18002A056
0x18002a051  mov     rdx, [rsi]
0x18002a054  jmp     short loc_18002A059
0x18002a056  mov     rdx, rsi
0x18002a059  mov     r8, [rsi+10h]
0x18002a05d  mov     rcx, rax
0x18002a060  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18002a065  lea     rdx, [rbp+1B0h+var_60]
0x18002a06c  lea     rcx, [rbp+1B0h+var_1F0]
0x18002a070  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x18002a075  nop
0x18002a076  mov     rcx, rax
0x18002a079  call    ?DeleteKeyAndSubkeys@Registry@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::Registry::DeleteKeyAndSubkeys(std::wstring const &)
0x18002a07e  nop
0x18002a07f  lea     rcx, [rbp+1B0h+var_60]
0x18002a086  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a08b  nop
0x18002a08c  mov     rax, [rbp+1B0h+var_1F0]
0x18002a090  movsxd  rcx, dword ptr [rax+4]
0x18002a094  lea     rax, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x18002a09b  mov     [rbp+rcx+1B0h+var_1F0], rax
0x18002a0a0  mov     rax, [rbp+1B0h+var_1F0]
0x18002a0a4  movsxd  rcx, dword ptr [rax+4]
0x18002a0a8  lea     edx, [rcx-88h]
0x18002a0ae  mov     [rbp+rcx+1B0h+var_1F4], edx
0x18002a0b2  lea     rcx, [rbp+1B0h+var_1E8]
0x18002a0b6  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18002a0bb  lea     rcx, [rbp+1B0h+var_1E0]
0x18002a0bf  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x18002a0c6  nop     dword ptr [rax+rax+00h]
0x18002a0cb  lea     rcx, [rbp+1B0h+var_168]
0x18002a0cf  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18002a0d6  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
