# CMVEngine::SessionInitialize(std::vector<ProvSource *,std::allocator<ProvSource *>> const &)

- ea: `0x18001eeec`
- end: `0x18001f61d`
- name: `?SessionInitialize@CMVEngine@@AEAAJAEBV?$vector@PEAVProvSource@@V?$allocator@PEAVProvSource@@@std@@@std@@@Z`
- size: `1841`
- prototype: `__int64 __fastcall(CMVEngine *, const struct ProvSource ***)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180015740`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x18000f288`
- `0x1800112a8`
- `0x180016cc8`
- `0x18001eeec`
- `0x180035fb0`
- `0x18003a990`
- `0x18003ac5c`
- `0x18003b120`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001f616`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001f616`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f305`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f336`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f56d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f59e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f5cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f600`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f305`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f336`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f56d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f59e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f5cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f600`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ef7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f520`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f520`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f530`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f4f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f4f4`

## pseudocode

```c
__int64 __fastcall CMVEngine::SessionInitialize(CMVEngine *a1, const struct ProvSource ***a2)
{
  int v3; // r13d
  const struct ProvSource **v4; // rbx
  const struct ProvSource **v5; // rdi
  const struct ProvSource *v7; // r15
  __int64 v8; // r10
  __int64 *v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  __int64 *v12; // r9
  __int64 v13; // r8
  int v14; // r8d
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  const struct IProvSource *v21; // rdx
  CMVEngine *v22; // r15
  const struct ProvSource *v23; // rcx
  const struct ProvSource *v24; // rax
  const struct ProvSource *v25; // rdx
  const struct ProvSource **v26; // r15
  int pdwType; // [rsp+20h] [rbp-1F8h]
  BYTE Data[8]; // [rsp+50h] [rbp-1C8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1C0h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-1B8h] BYREF
  CMVEngine *v31; // [rsp+68h] [rbp-1B0h]
  const struct ProvSource **v32; // [rsp+70h] [rbp-1A8h]
  const struct ProvSource *v33; // [rsp+78h] [rbp-1A0h]
  const struct ProvSource **v34; // [rsp+80h] [rbp-198h]
  CMVEngine *v35; // [rsp+88h] [rbp-190h]
  const wil::ResultException *v36; // [rsp+90h] [rbp-188h] BYREF
  void *v37[2]; // [rsp+98h] [rbp-180h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-170h]
  unsigned __int64 v39; // [rsp+B0h] [rbp-168h]
  void *v40[2]; // [rsp+B8h] [rbp-160h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-150h]
  unsigned __int64 v42; // [rsp+D0h] [rbp-148h]
  void *v43[2]; // [rsp+D8h] [rbp-140h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-130h]
  unsigned __int64 v45; // [rsp+F0h] [rbp-128h]
  void *v46[3]; // [rsp+F8h] [rbp-120h] BYREF
  unsigned __int64 v47; // [rsp+110h] [rbp-108h]
  int v48; // [rsp+118h] [rbp-100h]
  char v49; // [rsp+11Ch] [rbp-FCh]
  _BYTE v50[32]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v51[32]; // [rsp+140h] [rbp-D8h] BYREF
  HKEY *v52; // [rsp+160h] [rbp-B8h]
  __int64 v53; // [rsp+168h] [rbp-B0h]
  char v54[32]; // [rsp+170h] [rbp-A8h] BYREF
  __int64 *v55; // [rsp+190h] [rbp-88h]
  int v56; // [rsp+198h] [rbp-80h]
  int v57; // [rsp+19Ch] [rbp-7Ch]
  __int64 *v58; // [rsp+1A0h] [rbp-78h]
  int v59; // [rsp+1A8h] [rbp-70h]
  int v60; // [rsp+1ACh] [rbp-6Ch]
  __int64 *v61; // [rsp+1B0h] [rbp-68h]
  int v62; // [rsp+1B8h] [rbp-60h]
  int v63; // [rsp+1BCh] [rbp-5Ch]
  __int64 *v64; // [rsp+1C0h] [rbp-58h]
  int v65; // [rsp+1C8h] [rbp-50h]
  int v66; // [rsp+1CCh] [rbp-4Ch]
  HKEY *p_hKey; // [rsp+1D0h] [rbp-48h]
  __int64 v68; // [rsp+1D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v31 = a1;
  v35 = a1;
  v3 = 0;
  *(_DWORD *)Data = 0;
  pcbData = 4;
  v48 = 0;
  v49 = 0;
  RegGetValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\", L"UserPackages", 0x10u, 0, Data, &pcbData);
  v4 = *a2;
  v5 = a2[1];
  v34 = v5;
  while ( 1 )
  {
    v32 = v4;
    if ( v4 == v5 )
    {
      if ( v48 == 1 )
      {
        v48 = 2;
        _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, v50);
      }
      return 0;
    }
    v7 = *v4;
    v33 = v7;
    hKey = (HKEY)*((_QWORD *)ProvStateContext::CreatePackageContext(*((ProvStateContext **)v31 + 26), v7) + 1);
    (**(void (__fastcall ***)(const struct ProvSource *, void **))v7)(v7, v46);
    (*(void (__fastcall **)(const struct ProvSource *, void **))(*(_QWORD *)v7 + 16LL))(v7, v43);
    (*(void (__fastcall **)(const struct ProvSource *, void **))(*(_QWORD *)v7 + 24LL))(v7, v40);
    (*(void (__fastcall **)(const struct ProvSource *, void **))(*(_QWORD *)v7 + 32LL))(v7, v37);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      PackageEnroller::Enroll((PackageEnroller *)hKey);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v36) )
      {
        LODWORD(hKey) = *((_DWORD *)v36 + 8);
        v3 = (int)hKey;
        v4 = v32;
        v5 = v34;
        v7 = v33;
        v31 = v35;
        __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18001F087);
      }
    }
    v8 = -1;
    if ( (unsigned int)dword_18005A000 > 4 )
    {
      LODWORD(hKey) = v3;
      v9 = (__int64 *)v37;
      if ( v39 >= 8 )
        goto LABEL_9;
      goto LABEL_10;
    }
LABEL_37:
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87F,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)(unsigned int)v3,
        pdwType);
      goto LABEL_39;
    }
    v21 = v7;
    v22 = v31;
    v3 = CMVEngine::InitializeMasterDataStore(v31, v21);
    if ( v3 < 0 )
      break;
    if ( *(_DWORD *)Data )
      goto LABEL_73;
    ProvAgent::ProvAgent((ProvAgent *)v51);
    if ( (int)ProvAgent::GetCurrentTurn(v51) < 4 )
    {
      v23 = (const struct ProvSource *)*((_QWORD *)v22 + 36);
      v24 = (const struct ProvSource *)*((_QWORD *)v23 + 1);
      v7 = v23;
      if ( !*((_BYTE *)v24 + 25) )
      {
        v25 = v33;
        do
        {
          if ( *((_QWORD *)v24 + 4) >= (unsigned __int64)v33 )
          {
            v7 = v24;
            v24 = *(const struct ProvSource **)v24;
          }
          else
          {
            v24 = (const struct ProvSource *)*((_QWORD *)v24 + 2);
          }
        }
        while ( !*((_BYTE *)v24 + 25) );
        if ( v7 != v23 && (unsigned __int64)v33 >= *((_QWORD *)v7 + 4) )
        {
          v26 = (const struct ProvSource **)*((_QWORD *)v7 + 5);
          v32 = v26;
          if ( v26 )
          {
            (*((void (__fastcall **)(const struct ProvSource **, const struct ProvSource *))*v26 + 1))(v26, v33);
            if ( (*((int (__fastcall **)(const struct ProvSource **, __int64, BYTE *))*v26 + 4))(v26, 16, Data) >= 0 )
            {
              if ( *(_DWORD *)Data )
              {
                hKey = 0;
                if ( !RegCreateKeyExW(
                        HKEY_LOCAL_MACHINE,
                        L"SOFTWARE\\Microsoft\\Provisioning\\",
                        0,
                        0,
                        0,
                        2u,
                        0,
                        &hKey,
                        0) )
                  RegSetValueExW(hKey, L"UserPackages", 0, 4u, Data, 4u);
                if ( hKey )
                  RegCloseKey(hKey);
              }
            }
          }
          if ( v26 )
            (*((void (__fastcall **)(const struct ProvSource **, const struct ProvSource *))*v26 + 2))(v26, v25);
          goto LABEL_72;
        }
      }
      std::_Xout_of_range("invalid map<K, T> key");
LABEL_9:
      v9 = (__int64 *)v37[0];
LABEL_10:
      v10 = (__int64 *)v40;
      if ( v42 >= 8 )
        v10 = (__int64 *)v40[0];
      v11 = (__int64 *)v43;
      if ( v45 >= 8 )
        v11 = (__int64 *)v43[0];
      v12 = (__int64 *)v46;
      if ( v47 >= 8 )
        v12 = (__int64 *)v46[0];
      p_hKey = &hKey;
      v68 = 4;
      if ( v9 )
      {
        v13 = v8;
        do
          ++v13;
        while ( *((_WORD *)v9 + v13) );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v9 = &qword_180049F78;
        v14 = 2;
      }
      v64 = v9;
      v65 = v14;
      v66 = 0;
      if ( v10 )
      {
        v15 = v8;
        do
          ++v15;
        while ( *((_WORD *)v10 + v15) );
        v16 = 2 * v15 + 2;
      }
      else
      {
        v10 = &qword_180049F78;
        v16 = 2;
      }
      v61 = v10;
      v62 = v16;
      v63 = 0;
      if ( v11 )
      {
        v17 = v8;
        do
          ++v17;
        while ( *((_WORD *)v11 + v17) );
        v18 = 2 * v17 + 2;
      }
      else
      {
        v11 = &qword_180049F78;
        v18 = 2;
      }
      v58 = v11;
      v59 = v18;
      v60 = 0;
      if ( v12 )
      {
        v19 = v8;
        do
          ++v19;
        while ( *((_WORD *)v12 + v19) );
        v20 = 2 * v19 + 2;
      }
      else
      {
        v12 = &qword_180049F78;
        v20 = 2;
      }
      v55 = v12;
      v56 = v20;
      v57 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E79A, v50, 0, 7, v54);
      goto LABEL_37;
    }
LABEL_72:
    ProvAgent::~ProvAgent((ProvAgent *)v51);
LABEL_73:
    if ( v39 >= 8 )
      operator delete(v37[0]);
    v39 = 7;
    v38 = 0;
    LOWORD(v37[0]) = 0;
    if ( v42 >= 8 )
      operator delete(v40[0]);
    v42 = 7;
    v41 = 0;
    LOWORD(v40[0]) = 0;
    if ( v45 >= 8 )
      operator delete(v43[0]);
    v45 = 7;
    v44 = 0;
    LOWORD(v43[0]) = 0;
    if ( v47 >= 8 )
      operator delete(v46[0]);
    ++v4;
  }
  if ( (unsigned int)dword_18005A000 > 2 )
  {
    LODWORD(hKey) = v3;
    v52 = &hKey;
    v53 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E672, v50, 0, 3, v51);
  }
LABEL_39:
  if ( v39 >= 8 )
    operator delete(v37[0]);
  LOWORD(v37[0]) = 0;
  v38 = 0;
  v39 = 7;
  if ( v42 >= 8 )
    operator delete(v40[0]);
  LOWORD(v40[0]) = 0;
  v41 = 0;
  v42 = 7;
  if ( v45 >= 8 )
    operator delete(v43[0]);
  LOWORD(v43[0]) = 0;
  v44 = 0;
  v45 = 7;
  if ( v47 >= 8 )
    operator delete(v46[0]);
  v47 = 7;
  v46[2] = 0;
  LOWORD(v46[0]) = 0;
  if ( v48 == 1 )
  {
    v48 = 2;
    _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, v50);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001eeec  mov     [rsp+arg_8], rbx
0x18001eef1  mov     [rsp+arg_10], rsi
0x18001eef6  push    rdi
0x18001eef7  push    r12
0x18001eef9  push    r13
0x18001eefb  push    r14
0x18001eefd  push    r15
0x18001eeff  sub     rsp, 1F0h
0x18001ef06  mov     rax, cs:__security_cookie
0x18001ef0d  xor     rax, rsp
0x18001ef10  mov     [rsp+218h+var_38], rax
0x18001ef18  mov     rdi, rdx
0x18001ef1b  mov     [rsp+218h+var_1B0], rcx
0x18001ef20  mov     [rsp+218h+var_190], rcx
0x18001ef28  xor     esi, esi
0x18001ef2a  mov     r13d, esi
0x18001ef2d  mov     dword ptr [rsp+218h+Data], esi
0x18001ef31  mov     [rsp+218h+var_1B8], 4
0x18001ef39  mov     [rsp+218h+var_100], esi
0x18001ef40  mov     [rsp+218h+var_FC], sil
0x18001ef48  lea     rax, [rsp+218h+var_1B8]
0x18001ef4d  mov     [rsp+218h+pcbData], rax; pcbData
0x18001ef52  lea     rax, [rsp+218h+Data]
0x18001ef57  mov     [rsp+218h+pvData], rax; pvData
0x18001ef5c  mov     [rsp+218h+pdwType], rsi; pdwType
0x18001ef61  lea     r9d, [rsi+10h]; dwFlags
0x18001ef65  lea     r8, aUserpackages; "UserPackages"
0x18001ef6c  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Provisioning\\"
0x18001ef73  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ef7a  call    cs:__imp_RegGetValueW
0x18001ef80  mov     rbx, [rdi]
0x18001ef83  mov     rdi, [rdi+8]
0x18001ef87  mov     [rsp+218h+var_198], rdi
0x18001ef8f  lea     r12d, [rsi+2]
0x18001ef93  lea     r14d, [rsi+7]
0x18001ef97  mov     [rsp+218h+var_1A8], rbx
0x18001ef9c  cmp     rbx, rdi
0x18001ef9f  jnz     short loc_18001EFF6
0x18001efa1  cmp     [rsp+218h+var_100], 1
0x18001efa9  jnz     short loc_18001EFC7
0x18001efab  mov     [rsp+218h+var_100], r12d
0x18001efb3  lea     rdx, [rsp+218h+var_F8]
0x18001efbb  lea     rcx, dword_18005A000
0x18001efc2  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x18001efc7  xor     eax, eax
0x18001efc9  mov     rcx, [rsp+218h+var_38]
0x18001efd1  xor     rcx, rsp; StackCookie
0x18001efd4  call    __security_check_cookie
0x18001efd9  lea     r11, [rsp+218h+var_28]
0x18001efe1  mov     rbx, [r11+38h]
0x18001efe5  mov     rsi, [r11+40h]
0x18001efe9  mov     rsp, r11
0x18001efec  pop     r15
0x18001efee  pop     r14
0x18001eff0  pop     r13
0x18001eff2  pop     r12
0x18001eff4  pop     rdi
0x18001eff5  retn
0x18001eff6  mov     r15, [rbx]
0x18001eff9  mov     [rsp+218h+var_1A0], r15
0x18001effe  mov     rdx, r15; struct ProvSource *
0x18001f001  mov     rcx, [rsp+218h+var_1B0]
0x18001f006  mov     rcx, [rcx+0D0h]; this
0x18001f00d  call    ?CreatePackageContext@ProvStateContext@@QEAAAEAUPackageContext@@AEBVProvSource@@@Z; ProvStateContext::CreatePackageContext(ProvSource const &)
0x18001f012  mov     rax, [rax+8]
0x18001f016  mov     [rsp+218h+hKey], rax
0x18001f01b  mov     rax, [r15]
0x18001f01e  lea     rdx, [rsp+218h+var_120]
0x18001f026  mov     rcx, r15
0x18001f029  mov     rax, [rax]
0x18001f02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f031  nop
0x18001f032  mov     rax, [r15]
0x18001f035  lea     rdx, [rsp+218h+var_140]
0x18001f03d  mov     rcx, r15
0x18001f040  mov     rax, [rax+10h]
0x18001f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f049  nop
0x18001f04a  mov     rax, [r15]
0x18001f04d  lea     rdx, [rsp+218h+var_160]
0x18001f055  mov     rcx, r15
0x18001f058  mov     rax, [rax+18h]
0x18001f05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f061  nop
0x18001f062  mov     rax, [r15]
0x18001f065  lea     rdx, [rsp+218h+var_180]
0x18001f06d  mov     rcx, r15
0x18001f070  mov     rax, [rax+20h]
0x18001f074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f079  nop
0x18001f07a  mov     rcx, [rsp+218h+hKey]; this
0x18001f07f  call    ?Enroll@PackageEnroller@@QEAAXXZ; PackageEnroller::Enroll(void)
0x18001f084  nop
0x18001f085  jmp     short loc_18001F0B5
0x18001f087  xor     esi, esi
0x18001f089  lea     r12d, [rsi+2]
0x18001f08d  lea     r14d, [rsi+7]
0x18001f091  mov     r13d, dword ptr [rsp+218h+hKey]
0x18001f096  mov     rbx, [rsp+218h+var_1A8]
0x18001f09b  mov     rdi, [rsp+218h+var_198]
0x18001f0a3  mov     r15, [rsp+218h+var_1A0]
0x18001f0a8  mov     rcx, [rsp+218h+var_190]
0x18001f0b0  mov     [rsp+218h+var_1B0], rcx
0x18001f0b5  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001f0b9  mov     eax, cs:dword_18005A000
0x18001f0bf  cmp     eax, 4
0x18001f0c2  jbe     loc_18001F26A
0x18001f0c8  mov     dword ptr [rsp+218h+hKey], r13d
0x18001f0cd  lea     rax, [rsp+218h+var_180]
0x18001f0d5  cmp     [rsp+218h+var_168], 8
0x18001f0de  cmovnb  rax, [rsp+218h+var_180]
0x18001f0e7  lea     rcx, [rsp+218h+var_160]
0x18001f0ef  cmp     [rsp+218h+var_148], 8
0x18001f0f8  cmovnb  rcx, [rsp+218h+var_160]
0x18001f101  lea     rdx, [rsp+218h+var_140]
0x18001f109  cmp     [rsp+218h+var_128], 8
0x18001f112  cmovnb  rdx, [rsp+218h+var_140]
0x18001f11b  lea     r9, [rsp+218h+var_120]
0x18001f123  cmp     [rsp+218h+var_108], 8
0x18001f12c  cmovnb  r9, [rsp+218h+var_120]
0x18001f135  lea     r8, [rsp+218h+hKey]
0x18001f13a  mov     [rsp+218h+var_48], r8
0x18001f142  mov     [rsp+218h+var_40], 4
0x18001f14e  test    rax, rax
0x18001f151  jz      short loc_18001F16A
0x18001f153  mov     r8, r10
0x18001f156  inc     r8
0x18001f159  cmp     [rax+r8*2], si
0x18001f15e  jnz     short loc_18001F156
0x18001f160  lea     r8d, ds:2[r8*2]
0x18001f168  jmp     short loc_18001F174
0x18001f16a  lea     rax, qword_180049F78
0x18001f171  mov     r8d, r12d
0x18001f174  mov     [rsp+218h+var_58], rax
0x18001f17c  mov     [rsp+218h+var_50], r8d
0x18001f184  mov     [rsp+218h+var_4C], esi
0x18001f18b  test    rcx, rcx
0x18001f18e  jz      short loc_18001F1A5
0x18001f190  mov     rax, r10
0x18001f193  inc     rax
0x18001f196  cmp     [rcx+rax*2], si
0x18001f19a  jnz     short loc_18001F193
0x18001f19c  lea     eax, ds:2[rax*2]
0x18001f1a3  jmp     short loc_18001F1AF
0x18001f1a5  lea     rcx, qword_180049F78
0x18001f1ac  mov     eax, r12d
0x18001f1af  mov     [rsp+218h+var_68], rcx
0x18001f1b7  mov     [rsp+218h+var_60], eax
0x18001f1be  mov     [rsp+218h+var_5C], esi
0x18001f1c5  test    rdx, rdx
0x18001f1c8  jz      short loc_18001F1DF
0x18001f1ca  mov     rax, r10
0x18001f1cd  inc     rax
0x18001f1d0  cmp     [rdx+rax*2], si
0x18001f1d4  jnz     short loc_18001F1CD
0x18001f1d6  lea     eax, ds:2[rax*2]
0x18001f1dd  jmp     short loc_18001F1E9
0x18001f1df  lea     rdx, qword_180049F78
0x18001f1e6  mov     eax, r12d
0x18001f1e9  mov     [rsp+218h+var_78], rdx
0x18001f1f1  mov     [rsp+218h+var_70], eax
0x18001f1f8  mov     [rsp+218h+var_6C], esi
0x18001f1ff  test    r9, r9
0x18001f202  jz      short loc_18001F21A
0x18001f204  mov     rax, r10
0x18001f207  inc     rax
0x18001f20a  cmp     [r9+rax*2], si
0x18001f20f  jnz     short loc_18001F207
0x18001f211  lea     eax, ds:2[rax*2]
0x18001f218  jmp     short loc_18001F224
0x18001f21a  lea     r9, qword_180049F78
0x18001f221  mov     eax, r12d
0x18001f224  mov     [rsp+218h+var_88], r9
0x18001f22c  mov     [rsp+218h+var_80], eax
0x18001f233  mov     [rsp+218h+var_7C], esi
0x18001f23a  lea     rax, [rsp+218h+var_A8]
0x18001f242  mov     [rsp+218h+pvData], rax
0x18001f247  mov     dword ptr [rsp+218h+pdwType], r14d; int
0x18001f24c  xor     r9d, r9d
0x18001f24f  lea     r8, [rsp+218h+var_F8]
0x18001f257  lea     rdx, word_18004E79A
0x18001f25e  lea     rcx, dword_18005A000
0x18001f265  call    _tlgWriteTransfer_EventWriteTransfer
0x18001f26a  test    r13d, r13d
0x18001f26d  jns     loc_18001F382
0x18001f273  mov     rcx, [rsp+218h]; this
0x18001f27b  mov     r9d, r13d; char *
0x18001f27e  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001f285  mov     edx, 87Fh; void *
0x18001f28a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f28f  nop
0x18001f290  cmp     [rsp+218h+var_168], 8
0x18001f299  jb      short loc_18001F2A9
0x18001f29b  mov     rcx, [rsp+218h+var_180]
0x18001f2a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f2a9  mov     word ptr [rsp+218h+var_180], si
0x18001f2b1  mov     [rsp+218h+var_170], rsi
0x18001f2b9  mov     [rsp+218h+var_168], r14
0x18001f2c1  cmp     [rsp+218h+var_148], 8
0x18001f2ca  jb      short loc_18001F2DA
0x18001f2cc  mov     rcx, [rsp+218h+var_160]
0x18001f2d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f2da  mov     word ptr [rsp+218h+var_160], si
0x18001f2e2  mov     [rsp+218h+var_150], rsi
0x18001f2ea  mov     [rsp+218h+var_148], r14
0x18001f2f2  cmp     [rsp+218h+var_128], 8
0x18001f2fb  jb      short loc_18001F30B
0x18001f2fd  mov     rcx, [rsp+218h+var_140]
0x18001f305  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f30b  mov     word ptr [rsp+218h+var_140], si
0x18001f313  mov     [rsp+218h+var_130], rsi
0x18001f31b  mov     [rsp+218h+var_128], r14
0x18001f323  cmp     [rsp+218h+var_108], 8
0x18001f32c  jb      short loc_18001F33C
0x18001f32e  mov     rcx, [rsp+218h+var_120]
0x18001f336  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f33c  mov     [rsp+218h+var_108], r14
0x18001f344  mov     [rsp+218h+var_110], rsi
0x18001f34c  mov     word ptr [rsp+218h+var_120], si
0x18001f354  cmp     [rsp+218h+var_100], 1
0x18001f35c  jnz     short loc_18001F37A
0x18001f35e  mov     [rsp+218h+var_100], r12d
0x18001f366  lea     rdx, [rsp+218h+var_F8]
0x18001f36e  lea     rcx, dword_18005A000
0x18001f375  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x18001f37a  mov     eax, r13d
0x18001f37d  jmp     loc_18001EFC9
0x18001f382  mov     rdx, r15; struct IProvSource *
0x18001f385  mov     r15, [rsp+218h+var_1B0]
0x18001f38a  mov     rcx, r15; this
0x18001f38d  call    ?InitializeMasterDataStore@CMVEngine@@AEAAJPEBUIProvSource@@@Z; CMVEngine::InitializeMasterDataStore(IProvSource const *)
0x18001f392  mov     r13d, eax
0x18001f395  test    eax, eax
0x18001f397  jns     short loc_18001F3FE
0x18001f399  mov     eax, cs:dword_18005A000
0x18001f39f  cmp     eax, r12d
0x18001f3a2  jbe     loc_18001F290
0x18001f3a8  mov     dword ptr [rsp+218h+hKey], r13d
0x18001f3ad  lea     rax, [rsp+218h+hKey]
0x18001f3b2  mov     [rsp+218h+var_B8], rax
0x18001f3ba  mov     [rsp+218h+var_B0], 4
0x18001f3c6  lea     rax, [rsp+218h+var_D8]
0x18001f3ce  mov     [rsp+218h+pvData], rax
0x18001f3d3  mov     dword ptr [rsp+218h+pdwType], 3
0x18001f3db  xor     r9d, r9d
0x18001f3de  lea     r8, [rsp+218h+var_F8]
0x18001f3e6  lea     rdx, word_18004E672
0x18001f3ed  lea     rcx, dword_18005A000
0x18001f3f4  call    _tlgWriteTransfer_EventWriteTransfer
0x18001f3f9  jmp     loc_18001F290
0x18001f3fe  cmp     dword ptr [rsp+218h+Data], esi
0x18001f402  jnz     loc_18001F55A
0x18001f408  lea     rcx, [rsp+218h+var_D8]; this
0x18001f410  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x18001f415  nop
0x18001f416  lea     rcx, [rsp+218h+var_D8]
0x18001f41e  call    ?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ; ProvAgent::GetCurrentTurn(void)
0x18001f423  cmp     eax, 4
0x18001f426  jge     loc_18001F54C
0x18001f42c  mov     rcx, [r15+120h]
0x18001f433  mov     rax, [rcx+8]
0x18001f437  mov     r15, rcx
0x18001f43a  cmp     [rax+19h], sil
0x18001f43e  jnz     loc_18001F60F
0x18001f444  mov     rdx, [rsp+218h+var_1A0]
0x18001f449  cmp     [rax+20h], rdx
0x18001f44d  jnb     short loc_18001F455
0x18001f44f  mov     rax, [rax+10h]
0x18001f453  jmp     short loc_18001F45B
0x18001f455  mov     r15, rax
0x18001f458  mov     rax, [rax]
0x18001f45b  cmp     [rax+19h], sil
0x18001f45f  jz      short loc_18001F449
0x18001f461  cmp     r15, rcx
0x18001f464  jz      loc_18001F60F
0x18001f46a  cmp     rdx, [r15+20h]
0x18001f46e  jb      loc_18001F60F
0x18001f474  mov     r15, [r15+28h]
0x18001f478  mov     [rsp+218h+var_1A8], r15
0x18001f47d  test    r15, r15
0x18001f480  jz      short loc_18001F492
0x18001f482  mov     rax, [r15]
0x18001f485  mov     rcx, r15
0x18001f488  mov     rax, [rax+8]
0x18001f48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f491  nop
0x18001f492  test    r15, r15
0x18001f495  jz      loc_18001F537
0x18001f49b  mov     rax, [r15]
0x18001f49e  lea     r8, [rsp+218h+Data]
0x18001f4a3  mov     edx, 10h
0x18001f4a8  mov     rcx, r15
0x18001f4ab  mov     rax, [rax+20h]
0x18001f4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4b4  test    eax, eax
0x18001f4b6  js      short loc_18001F537
0x18001f4b8  cmp     dword ptr [rsp+218h+Data], esi
0x18001f4bc  jz      short loc_18001F537
0x18001f4be  mov     [rsp+218h+hKey], rsi
0x18001f4c3  mov     [rsp+218h+lpdwDisposition], rsi; lpdwDisposition
  ... truncated ...
```
