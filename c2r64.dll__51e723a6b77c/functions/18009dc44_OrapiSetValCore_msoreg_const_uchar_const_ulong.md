# OrapiSetValCore(_msoreg const &,uchar const *,ulong)

- ea: `0x18009dc44`
- end: `0x18009e389`
- name: `?OrapiSetValCore@@YAJAEBU_msoreg@@PEBEK@Z`
- size: `1861`
- prototype: `__int64 __fastcall(const struct _msoreg *, BYTE *lpData, DWORD cbData)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098d60`
- `0x18009b040`
- `0x18009b064`
- `0x18009b098`

## callees

- `0x18000adf0`
- `0x18000c2dc`
- `0x180011340`
- `0x180011b70`
- `0x18001bae0`
- `0x1800267a8`
- `0x18003e690`
- `0x180052cd0`
- `0x18009bbf4`
- `0x18009bfb0`
- `0x18009c710`
- `0x18009ca08`
- `0x18009cf3c`
- `0x18009cf58`
- `0x18009cf74`
- `0x18009dc44`
- `0x18009e4b4`
- `0x180146090`
- `0x180146a70`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009e350`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18009e350`
- `ADVAPI32!RegSetValueExW` at `0x18009df5c`
- `ADVAPI32!RegSetValueExW` at `0x18009df5c`
- `ADVAPI32!RegQueryValueExW` at `0x18009dd97`
- `ADVAPI32!RegQueryValueExW` at `0x18009ddef`
- `ADVAPI32!RegQueryValueExW` at `0x18009dd97`
- `ADVAPI32!RegQueryValueExW` at `0x18009ddef`

## string_xrefs

- `0x18009e0aa`: `KeyPath`
- `0x18009e076`: `RegistryValueName`
- `0x18009e1cf`: `RegistryValueName`
- `0x18009e283`: `Failed to open registry key.`
- `0x18009e196`: `OrapiWriteFail: RegSetValueExW`
- `0x18009e12b`: `Failed to write registry value.`
- `0x18009e2ee`: `OrapiWriteFail: TryOpenKey in WriteValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OrapiSetValCore(const struct _msoreg *a1, BYTE *lpData, DWORD cbData)
{
  const BYTE *v4; // r14
  char v6; // si
  char v7; // cl
  LPBYTE v8; // rbx
  int v9; // esi
  char v10; // r15
  __int64 v11; // rax
  unsigned int *v12; // rcx
  unsigned int v13; // eax
  char v14; // al
  const struct _orkey *v15; // rdx
  Mso::Orapi::KeyCache *v16; // rcx
  int v17; // ecx
  bool v18; // zf
  LPBYTE v19; // rax
  char *v20; // rdx
  unsigned __int16 v21; // cx
  int v22; // eax
  int v23; // esi
  __m128i si128; // xmm6
  char v25; // r15
  __int64 v26; // rax
  unsigned int *v27; // rcx
  int v28; // ecx
  __int64 v29; // r8
  Mso::Orapi::KeyCache *v30; // rcx
  void *v31; // rdx
  int v32; // ecx
  unsigned __int64 v33; // r8
  const wchar_t *v34; // rax
  __int64 v35; // r8
  unsigned int v36; // edi
  __int64 v37; // rcx
  const wchar_t *lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int v40; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbDataa; // [rsp+34h] [rbp-CCh] BYREF
  char v42; // [rsp+38h] [rbp-C8h]
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  LPBYTE v45; // [rsp+48h] [rbp-B8h] BYREF
  void ***v46; // [rsp+50h] [rbp-B0h] BYREF
  void ***v47; // [rsp+58h] [rbp-A8h]
  void ****v48; // [rsp+60h] [rbp-A0h]
  void ***v49; // [rsp+68h] [rbp-98h] BYREF
  void ***v50; // [rsp+70h] [rbp-90h]
  void ****v51; // [rsp+78h] [rbp-88h]
  __int64 *v52; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v53; // [rsp+88h] [rbp-78h]
  __int64 *v54; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v55; // [rsp+98h] [rbp-68h]
  void **v56; // [rsp+A0h] [rbp-60h]
  void ****v57; // [rsp+A8h] [rbp-58h]
  void ****v58; // [rsp+B0h] [rbp-50h]
  void **v59; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  __int16 v62; // [rsp+D0h] [rbp-30h]
  void *Buf2; // [rsp+D8h] [rbp-28h]
  _BYTE v64[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v65; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v66; // [rsp+100h] [rbp+0h]
  void **v67; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v68; // [rsp+118h] [rbp+18h]
  __int128 v69; // [rsp+120h] [rbp+20h] BYREF
  __m128i v70; // [rsp+130h] [rbp+30h]
  __int16 v71; // [rsp+140h] [rbp+40h]

  v4 = lpData;
  Buf2 = lpData;
  v40 = 0;
  v6 = (unsigned __int8)*((_WORD *)a1 + 14) >> 7;
  if ( (unsigned __int8)sub_18009CF58() && (v7 & 0x30) != 0x20 || vfRunningRestricted || FRegValueExists(a1, 1) )
    return 0;
  v8 = 0;
  v45 = 0;
  cbDataa = 0;
  Type = 0;
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(
    v64,
    s_orapiCS);
  v44 = 0;
  if ( v6 )
    goto LABEL_33;
  v9 = 0;
  do
  {
    if ( v9 >= 4 )
      break;
    v10 = 0;
    LOBYTE(lpDataa) = *((_BYTE *)a1 + 24);
    v11 = sub_18009E4B4((unsigned int)&v54, *((_QWORD *)a1 + 2), 0, 0, lpDataa, 0);
    v52 = &v44;
    v53 = &v40;
    std::tuple<long &,Mso::TCntPtr<Mso::Registry::Key> &>::operator=<long,Mso::TCntPtr<Mso::Registry::Key>,0>(
      (__int64)&v52,
      v11);
    v12 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    if ( !v40 )
    {
      v13 = RegQueryValueExW(*(HKEY *)(v44 + 16), *(LPCWSTR *)a1, 0, &Type, 0, &cbDataa);
      v40 = v13;
      if ( !v13 )
      {
        v13 = 0;
        if ( cbDataa )
        {
          v14 = Mso::MemoryPtr<_TOKEN_GROUPS,0>::AllocBytes(&v45, cbDataa);
          v8 = v45;
          if ( v14 )
            v13 = RegQueryValueExW(*(HKEY *)(v44 + 16), *(LPCWSTR *)a1, 0, &Type, v45, &cbDataa);
          else
            v13 = 8;
          v40 = v13;
        }
      }
      if ( (unsigned int)sub_18009CF3C(v13) )
      {
        v16 = (Mso::Orapi::KeyCache *)*((_QWORD *)a1 + 2);
        *(&vrgPersistentKeys + 4 * (*((_WORD *)v16 + 5) & 0x1F)) = 0;
        Mso::Orapi::KeyCache::RemoveKey(v16, v15);
        v10 = 1;
      }
    }
    ++v9;
  }
  while ( v10 );
  v4 = (const BYTE *)Buf2;
  if ( v40 || !v8 )
  {
    v31 = (void *)*((_QWORD *)a1 + 1);
    if ( v31 != (void *)0xCCCCCCCCCCCCCCCCLL )
    {
      switch ( *((_WORD *)a1 + 14) & 0xF )
      {
        case 1:
        case 2:
          if ( cbData < 2 )
            CrashWithRecovery(0x59948Du, 0);
          if ( v31 != Buf2 )
            goto LABEL_33;
          goto LABEL_57;
        case 4:
          if ( cbData != 4 )
            CrashWithRecovery(0x59948Eu, 0);
          v18 = *(_DWORD *)Buf2 == *((_DWORD *)a1 + 2);
          break;
        case 11:
          if ( cbData != 8 )
            CrashWithRecovery(0x59948Fu, 0);
          v18 = *(_QWORD *)Buf2 == (_QWORD)v31;
          break;
        default:
          CrashWithRecovery(0x599491u, 0);
      }
LABEL_52:
      if ( !v18 )
        goto LABEL_33;
LABEL_57:
      v40 = 0;
      goto LABEL_68;
    }
  }
  else
  {
    v17 = *((_WORD *)a1 + 14) & 0xF;
    if ( Type == v17 )
    {
      if ( (unsigned int)(v17 - 1) < 2 )
      {
        if ( !*(_WORD *)&v8[2 * (cbDataa >> 1) - 2] )
        {
          v19 = v8;
          v20 = (char *)((_BYTE *)Buf2 - v8);
          while ( 1 )
          {
            v21 = *(_WORD *)v19;
            if ( *(_WORD *)v19 != *(_WORD *)&v20[(_QWORD)v19] )
              break;
            v19 += 2;
            if ( !v21 )
            {
              v22 = 0;
              goto LABEL_32;
            }
          }
          v22 = v21 < *(_WORD *)&v20[(_QWORD)v19] ? -1 : 1;
LABEL_32:
          if ( !v22 )
            goto LABEL_68;
        }
        goto LABEL_33;
      }
      if ( cbDataa == cbData )
      {
        v18 = memcmp(v8, Buf2, cbDataa) == 0;
        goto LABEL_52;
      }
    }
  }
LABEL_33:
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v23 < 4 )
  {
    v25 = 0;
    LOBYTE(lpDataa) = *((_BYTE *)a1 + 24);
    v26 = sub_18009E4B4((unsigned int)&v52, *((_QWORD *)a1 + 2), 0, 4, lpDataa, 0);
    v54 = &v44;
    v55 = &v40;
    std::tuple<long &,Mso::TCntPtr<Mso::Registry::Key> &>::operator=<long,Mso::TCntPtr<Mso::Registry::Key>,0>(
      (__int64)&v54,
      v26);
    v27 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v27 + 8LL))(v27);
    }
    if ( v40 )
    {
      v49 = (void ***)&Mso::Logging::StructuredErrorCode::`vftable';
      v50 = (void ***)L"Win32ErrorCode";
      LODWORD(v51) = v40;
      WORD2(v51) = 0;
      v59 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
      v60 = L"RegistryValueName";
      v61 = *(_QWORD *)a1;
      v62 = 0;
      std::wstring::wstring(&v65, **((_QWORD **)a1 + 2));
      v67 = &Mso::Logging::StructuredObject<std::wstring,0>::`vftable';
      v68 = L"KeyName";
      v69 = v65;
      v70 = v66;
      v66 = si128;
      LOWORD(v65) = 0;
      v71 = 0;
      if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(23668941, 935, 100) )
      {
        v46 = &v67;
        v47 = &v59;
        v48 = &v49;
        v56 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v57 = &v46;
        v58 = &v49;
        lpDataa = L"Failed to open registry key.";
        Mso::Logging::MsoSendStructuredTraceTag(23668941, 935, 100);
      }
      std::wstring::~wstring(&v69);
      std::wstring::~wstring(&v65);
      v32 = v40;
      v33 = (unsigned int)_InterlockedIncrement(&dword_18021C9C0) % 0x32uLL;
      v34 = L"OrapiWriteFail: TryOpenKey in WriteValue";
      goto LABEL_65;
    }
    v40 = RegSetValueExW(*(HKEY *)(v44 + 16), *(LPCWSTR *)a1, 0, *((_WORD *)a1 + 14) & 0xF, v4, cbData);
    if ( (unsigned int)sub_18009CF3C(v40) )
    {
      v30 = (Mso::Orapi::KeyCache *)*((_QWORD *)a1 + 2);
      *(&vrgPersistentKeys + 4 * (*((_WORD *)v30 + 5) & 0x1F)) = 0;
      Mso::Orapi::KeyCache::RemoveKey(v30, (const struct _orkey *)&_NULL_IMPORT_DESCRIPTOR);
      v25 = 1;
    }
    else if ( v28 )
    {
      v46 = (void ***)&Mso::Logging::StructuredErrorCode::`vftable';
      v47 = (void ***)L"Win32ErrorCode";
      LODWORD(v48) = v40;
      WORD2(v48) = 0;
      v59 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
      v60 = L"RegistryValueName";
      v61 = *(_QWORD *)a1;
      v62 = 0;
      LOBYTE(v29) = v42;
      sub_18009BFB0(&v65, *((_QWORD *)a1 + 2), v29);
      v67 = &Mso::Logging::StructuredObject<std::wstring,0>::`vftable';
      v68 = L"KeyPath";
      v69 = v65;
      v70 = v66;
      v66 = si128;
      LOWORD(v65) = 0;
      v71 = 0;
      if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(23668940, 935, 100) )
      {
        v49 = &v67;
        v50 = &v59;
        v51 = &v46;
        v56 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v57 = &v49;
        v58 = (void ****)&v52;
        lpDataa = L"Failed to write registry value.";
        Mso::Logging::MsoSendStructuredTraceTag(23668940, 935, 100);
      }
      std::wstring::~wstring(&v69);
      std::wstring::~wstring(&v65);
      v32 = v40;
      v33 = (unsigned int)_InterlockedIncrement(&dword_18021C9C0) % 0x32uLL;
      v34 = L"OrapiWriteFail: RegSetValueExW";
LABEL_65:
      v35 = 2 * v33;
      qword_18021C6A8[v35] = (__int64)v34;
      dword_18021C6A0[2 * v35] = v32;
    }
    ++v23;
    if ( !v25 )
      break;
  }
  v8 = v45;
LABEL_68:
  v36 = v40;
  v37 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
  }
  Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::~TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(v64);
  if ( v8 )
    free(v8);
  return v36;
}

```

## disassembly

```asm
0x18009dc44  mov     rax, rsp
0x18009dc47  mov     [rax+20h], rbx
0x18009dc4b  push    rbp
0x18009dc4c  push    rsi
0x18009dc4d  push    rdi
0x18009dc4e  push    r12
0x18009dc50  push    r13
0x18009dc52  push    r14
0x18009dc54  push    r15
0x18009dc56  lea     rbp, [rsp-60h]
0x18009dc5b  sub     rsp, 160h
0x18009dc62  movaps  xmmword ptr [rax-48h], xmm6
0x18009dc66  mov     rax, cs:__security_cookie
0x18009dc6d  xor     rax, rsp
0x18009dc70  mov     [rbp+90h+var_48], rax
0x18009dc74  mov     r12d, r8d
0x18009dc77  mov     r14, rdx
0x18009dc7a  mov     [rbp+90h+Buf2], rdx
0x18009dc7e  mov     rdi, rcx
0x18009dc81  xor     r13d, r13d
0x18009dc84  mov     [rsp+190h+var_160], r13d
0x18009dc89  movzx   ecx, word ptr [rcx+1Ch]
0x18009dc8d  mov     sil, cl
0x18009dc90  shr     sil, 7
0x18009dc94  and     sil, 1
0x18009dc98  call    sub_18009CF58
0x18009dc9d  test    al, al
0x18009dc9f  jz      short loc_18009DCAD
0x18009dca1  and     cl, 30h
0x18009dca4  cmp     cl, 20h ; ' '
0x18009dca7  jnz     loc_18009E35B
0x18009dcad  cmp     cs:?vfRunningRestricted@@3HA, r13d; int vfRunningRestricted
0x18009dcb4  jnz     loc_18009E35B
0x18009dcba  mov     dl, 1; bool
0x18009dcbc  mov     rcx, rdi; struct _msoreg *
0x18009dcbf  call    ?FRegValueExists@@YA_NPEBU_msoreg@@_N@Z; FRegValueExists(_msoreg const *,bool)
0x18009dcc4  test    al, al
0x18009dcc6  jnz     loc_18009E35B
0x18009dccc  mov     rbx, r13
0x18009dccf  mov     [rsp+190h+var_148], rbx
0x18009dcd4  mov     [rsp+190h+cbData], r13d
0x18009dcd9  mov     [rsp+190h+Type], r13d
0x18009dcde  lea     rdx, ?s_orapiCS@@3V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@A; Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> s_orapiCS
0x18009dce5  lea     rcx, [rbp+90h+var_B0]
0x18009dce9  call    ??0?$TLocker@V?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@Mso@@VZeroOrOneThreaded@2@@Mso@@QEAA@AEAV?$Lockable@V?$AlwaysInit@VCritSecBase@Mso@@@Mso@@VZeroOrOneThreaded@2@@1@@Z; Mso::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>::TLocker<Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded>,Mso::ZeroOrOneThreaded>(Mso::Lockable<Mso::AlwaysInit<Mso::CritSecBase>,Mso::ZeroOrOneThreaded> &)
0x18009dcee  mov     [rsp+190h+var_150], r13
0x18009dcf3  test    sil, sil
0x18009dcf6  jnz     loc_18009DEB6
0x18009dcfc  mov     esi, r13d
0x18009dcff  lea     r14, __NULL_IMPORT_DESCRIPTOR
0x18009dd06  cmp     esi, 4
0x18009dd09  jge     loc_18009DE2E
0x18009dd0f  mov     r15b, r13b
0x18009dd12  mov     [rsp+190h+lpcbData], r13
0x18009dd17  mov     al, [rdi+18h]
0x18009dd1a  mov     byte ptr [rsp+190h+lpData], al
0x18009dd1e  xor     r9d, r9d
0x18009dd21  xor     r8d, r8d
0x18009dd24  mov     rdx, [rdi+10h]
0x18009dd28  lea     rcx, [rbp+90h+var_100]
0x18009dd2c  call    sub_18009E4B4
0x18009dd31  lea     rcx, [rsp+190h+var_150]
0x18009dd36  mov     [rbp+90h+var_110], rcx
0x18009dd3a  lea     rcx, [rsp+190h+var_160]
0x18009dd3f  mov     [rbp+90h+var_108], rcx
0x18009dd43  mov     rdx, rax
0x18009dd46  lea     rcx, [rbp+90h+var_110]
0x18009dd4a  call    ??$?4JV?$TCntPtr@UKey@Registry@Mso@@@Mso@@$0A@@?$tuple@AEAJAEAV?$TCntPtr@UKey@Registry@Mso@@@Mso@@@std@@QEAAAEAV01@$$QEAU?$pair@JV?$TCntPtr@UKey@Registry@Mso@@@Mso@@@1@@Z; std::tuple<long &,Mso::TCntPtr<Mso::Registry::Key> &>::operator=<long,Mso::TCntPtr<Mso::Registry::Key>,0>(std::pair<long,Mso::TCntPtr<Mso::Registry::Key>> &&)
0x18009dd4f  mov     rcx, [rbp+90h+var_F8]
0x18009dd53  test    rcx, rcx
0x18009dd56  jz      short loc_18009DD69
0x18009dd58  mov     [rbp+90h+var_F8], r13
0x18009dd5c  mov     rax, [rcx]
0x18009dd5f  mov     rax, [rax+8]
0x18009dd63  call    cs:__guard_dispatch_icall_fptr
0x18009dd69  cmp     [rsp+190h+var_160], r13d
0x18009dd6e  jnz     loc_18009DE23
0x18009dd74  mov     rax, [rsp+190h+var_150]
0x18009dd79  lea     rcx, [rsp+190h+cbData]
0x18009dd7e  mov     [rsp+190h+lpcbData], rcx; lpcbData
0x18009dd83  mov     [rsp+190h+lpData], r13; lpData
0x18009dd88  lea     r9, [rsp+190h+Type]; lpType
0x18009dd8d  xor     r8d, r8d; lpReserved
0x18009dd90  mov     rdx, [rdi]; lpValueName
0x18009dd93  mov     rcx, [rax+10h]; hKey
0x18009dd97  call    cs:__imp_RegQueryValueExW
0x18009dd9d  mov     [rsp+190h+var_160], eax
0x18009dda1  test    eax, eax
0x18009dda3  jnz     short loc_18009DDF9
0x18009dda5  mov     eax, r13d
0x18009dda8  mov     ecx, [rsp+190h+cbData]
0x18009ddac  test    ecx, ecx
0x18009ddae  jz      short loc_18009DDF9
0x18009ddb0  mov     edx, ecx
0x18009ddb2  lea     rcx, [rsp+190h+var_148]
0x18009ddb7  call    ?AllocBytes@?$MemoryPtr@U_TOKEN_GROUPS@@$0A@@Mso@@QEAA_N_K@Z; Mso::MemoryPtr<_TOKEN_GROUPS,0>::AllocBytes(unsigned __int64)
0x18009ddbc  mov     rbx, [rsp+190h+var_148]
0x18009ddc1  test    al, al
0x18009ddc3  jnz     short loc_18009DDCC
0x18009ddc5  mov     eax, 8
0x18009ddca  jmp     short loc_18009DDF5
0x18009ddcc  mov     rax, [rsp+190h+var_150]
0x18009ddd1  lea     rcx, [rsp+190h+cbData]
0x18009ddd6  mov     [rsp+190h+lpcbData], rcx; lpcbData
0x18009dddb  mov     [rsp+190h+lpData], rbx; lpData
0x18009dde0  lea     r9, [rsp+190h+Type]; lpType
0x18009dde5  xor     r8d, r8d; lpReserved
0x18009dde8  mov     rdx, [rdi]; lpValueName
0x18009ddeb  mov     rcx, [rax+10h]; hKey
0x18009ddef  call    cs:__imp_RegQueryValueExW
0x18009ddf5  mov     [rsp+190h+var_160], eax
0x18009ddf9  mov     ecx, eax
0x18009ddfb  call    sub_18009CF3C
0x18009de00  test    eax, eax
0x18009de02  jz      short loc_18009DE23
0x18009de04  mov     rcx, [rdi+10h]; this
0x18009de08  movzx   eax, word ptr [rcx+0Ah]
0x18009de0c  and     eax, 1Fh
0x18009de0f  shl     rax, 5
0x18009de13  mov     [rax+r14+2145F0h], r13
0x18009de1b  call    ?RemoveKey@KeyCache@Orapi@Mso@@YAXAEBU_orkey@@@Z; Mso::Orapi::KeyCache::RemoveKey(_orkey const &)
0x18009de20  mov     r15b, 1
0x18009de23  inc     esi
0x18009de25  test    r15b, r15b
0x18009de28  jnz     loc_18009DD06
0x18009de2e  cmp     [rsp+190h+var_160], r13d
0x18009de33  mov     r14, [rbp+90h+Buf2]
0x18009de37  jnz     loc_18009DFA0
0x18009de3d  test    rbx, rbx
0x18009de40  jz      loc_18009DFA0
0x18009de46  movzx   ecx, word ptr [rdi+1Ch]
0x18009de4a  and     ecx, 0Fh
0x18009de4d  cmp     [rsp+190h+Type], ecx
0x18009de51  jnz     short loc_18009DEB6
0x18009de53  sub     ecx, 1
0x18009de56  jz      short loc_18009DE7B
0x18009de58  cmp     ecx, 1
0x18009de5b  jz      short loc_18009DE7B
0x18009de5d  mov     ecx, [rsp+190h+cbData]
0x18009de61  cmp     ecx, r12d
0x18009de64  jnz     short loc_18009DEB6
0x18009de66  mov     r8d, ecx; Size
0x18009de69  mov     rdx, r14; Buf2
0x18009de6c  mov     rcx, rbx; Buf1
0x18009de6f  call    memcmp
0x18009de74  test    eax, eax
0x18009de76  jmp     loc_18009E010
0x18009de7b  mov     eax, [rsp+190h+cbData]
0x18009de7f  shr     eax, 1
0x18009de81  cmp     [rbx+rax*2-2], r13w
0x18009de87  jnz     short loc_18009DEB6
0x18009de89  mov     rax, rbx
0x18009de8c  mov     rdx, r14
0x18009de8f  sub     rdx, rbx
0x18009de92  movzx   ecx, word ptr [rax]
0x18009de95  cmp     cx, [rax+rdx]
0x18009de99  jnz     short loc_18009DEA9
0x18009de9b  add     rax, 2
0x18009de9f  test    cx, cx
0x18009dea2  jnz     short loc_18009DE92
0x18009dea4  mov     eax, r13d
0x18009dea7  jmp     short loc_18009DEAE
0x18009dea9  sbb     eax, eax
0x18009deab  or      eax, 1
0x18009deae  test    eax, eax
0x18009deb0  jz      loc_18009E31F
0x18009deb6  mov     esi, r13d
0x18009deb9  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18009dec1  lea     rbx, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18009dec8  cmp     esi, 4
0x18009decb  jge     loc_18009E31A
0x18009ded1  mov     r15b, r13b
0x18009ded4  mov     [rsp+190h+lpcbData], r13
0x18009ded9  mov     al, [rdi+18h]
0x18009dedc  mov     byte ptr [rsp+190h+lpData], al
0x18009dee0  mov     r9d, 4
0x18009dee6  xor     r8d, r8d
0x18009dee9  mov     rdx, [rdi+10h]
0x18009deed  lea     rcx, [rbp+90h+var_110]
0x18009def1  call    sub_18009E4B4
0x18009def6  lea     rcx, [rsp+190h+var_150]
0x18009defb  mov     [rbp+90h+var_100], rcx
0x18009deff  lea     rcx, [rsp+190h+var_160]
0x18009df04  mov     [rbp+90h+var_F8], rcx
0x18009df08  mov     rdx, rax
0x18009df0b  lea     rcx, [rbp+90h+var_100]
0x18009df0f  call    ??$?4JV?$TCntPtr@UKey@Registry@Mso@@@Mso@@$0A@@?$tuple@AEAJAEAV?$TCntPtr@UKey@Registry@Mso@@@Mso@@@std@@QEAAAEAV01@$$QEAU?$pair@JV?$TCntPtr@UKey@Registry@Mso@@@Mso@@@1@@Z; std::tuple<long &,Mso::TCntPtr<Mso::Registry::Key> &>::operator=<long,Mso::TCntPtr<Mso::Registry::Key>,0>(std::pair<long,Mso::TCntPtr<Mso::Registry::Key>> &&)
0x18009df14  mov     rcx, [rbp+90h+var_108]
0x18009df18  test    rcx, rcx
0x18009df1b  jz      short loc_18009DF2E
0x18009df1d  mov     [rbp+90h+var_108], r13
0x18009df21  mov     rax, [rcx]
0x18009df24  mov     rax, [rax+8]
0x18009df28  call    cs:__guard_dispatch_icall_fptr
0x18009df2e  mov     eax, [rsp+190h+var_160]
0x18009df32  test    eax, eax
0x18009df34  jnz     loc_18009E1A2
0x18009df3a  movzx   r9d, word ptr [rdi+1Ch]
0x18009df3f  and     r9d, 0Fh; dwType
0x18009df43  mov     rax, [rsp+190h+var_150]
0x18009df48  mov     dword ptr [rsp+190h+lpcbData], r12d; cbData
0x18009df4d  mov     [rsp+190h+lpData], r14; lpData
0x18009df52  xor     r8d, r8d; Reserved
0x18009df55  mov     rdx, [rdi]; lpValueName
0x18009df58  mov     rcx, [rax+10h]; hKey
0x18009df5c  call    cs:__imp_RegSetValueExW
0x18009df62  mov     ecx, eax
0x18009df64  mov     [rsp+190h+var_160], eax
0x18009df68  call    sub_18009CF3C
0x18009df6d  test    eax, eax
0x18009df6f  jz      loc_18009E03D
0x18009df75  mov     rcx, [rdi+10h]; this
0x18009df79  movzx   eax, word ptr [rcx+0Ah]
0x18009df7d  and     eax, 1Fh
0x18009df80  shl     rax, 5
0x18009df84  lea     rdx, __NULL_IMPORT_DESCRIPTOR; struct _orkey *
0x18009df8b  mov     [rax+rdx+2145F0h], r13
0x18009df93  call    ?RemoveKey@KeyCache@Orapi@Mso@@YAXAEBU_orkey@@@Z; Mso::Orapi::KeyCache::RemoveKey(_orkey const &)
0x18009df98  mov     r15b, 1
0x18009df9b  jmp     loc_18009E30F
0x18009dfa0  mov     rdx, [rdi+8]
0x18009dfa4  mov     rax, 0CCCCCCCCCCCCCCCCh
0x18009dfae  cmp     rdx, rax
0x18009dfb1  jz      loc_18009DEB6
0x18009dfb7  movzx   ecx, word ptr [rdi+1Ch]
0x18009dfbb  and     ecx, 0Fh
0x18009dfbe  sub     ecx, 1
0x18009dfc1  jz      short loc_18009E017
0x18009dfc3  sub     ecx, 1
0x18009dfc6  jz      short loc_18009E017
0x18009dfc8  sub     ecx, 2
0x18009dfcb  jz      short loc_18009DFF7
0x18009dfcd  cmp     ecx, 7
0x18009dfd0  jz      short loc_18009DFDF
0x18009dfd2  xor     edx, edx; struct CrashContext *
0x18009dfd4  mov     ecx, 599491h; unsigned int
0x18009dfd9  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009dfdf  cmp     r12d, 8
0x18009dfe3  jz      short loc_18009DFF2
0x18009dfe5  xor     edx, edx; struct CrashContext *
0x18009dfe7  mov     ecx, 59948Fh; unsigned int
0x18009dfec  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009dff2  cmp     [r14], rdx
0x18009dff5  jmp     short loc_18009E010
0x18009dff7  cmp     r12d, 4
0x18009dffb  jz      short loc_18009E00A
0x18009dffd  xor     edx, edx; struct CrashContext *
0x18009dfff  mov     ecx, 59948Eh; unsigned int
0x18009e004  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009e00a  mov     eax, [rdi+8]
0x18009e00d  cmp     [r14], eax
0x18009e010  jz      short loc_18009E033
0x18009e012  jmp     loc_18009DEB6
0x18009e017  cmp     r12d, 2
0x18009e01b  jnb     short loc_18009E02A
0x18009e01d  xor     edx, edx; struct CrashContext *
0x18009e01f  mov     ecx, 59948Dh; unsigned int
0x18009e024  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18009e02a  cmp     rdx, r14
0x18009e02d  jnz     loc_18009DEB6
0x18009e033  mov     [rsp+190h+var_160], r13d
0x18009e038  jmp     loc_18009E31F
0x18009e03d  test    ecx, ecx
0x18009e03f  jz      loc_18009E30F
0x18009e045  lea     rax, ??_7StructuredErrorCode@Logging@Mso@@6B@; const Mso::Logging::StructuredErrorCode::`vftable'
0x18009e04c  mov     [rsp+190h+var_140], rax
0x18009e051  lea     rax, aWin32errorcode; "Win32ErrorCode"
0x18009e058  mov     [rsp+190h+var_138], rax
0x18009e05d  mov     eax, [rsp+190h+var_160]
0x18009e061  mov     dword ptr [rsp+190h+var_130], eax
0x18009e065  mov     word ptr [rsp+190h+var_130+4], r13w
0x18009e06b  lea     rax, ??_7?$StructuredObject@PEB_W$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable'
0x18009e072  mov     [rbp+90h+var_D8], rax
0x18009e076  lea     rax, aRegistryvaluen; "RegistryValueName"
0x18009e07d  mov     [rbp+90h+var_D0], rax
0x18009e081  mov     rax, [rdi]
0x18009e084  mov     [rbp+90h+var_C8], rax
0x18009e088  mov     [rbp+90h+var_C0], r13w
0x18009e08d  mov     r8b, [rsp+190h+var_158]
0x18009e092  mov     rdx, [rdi+10h]
0x18009e096  lea     rcx, [rbp+90h+var_A0]
0x18009e09a  call    sub_18009BFB0
0x18009e09f  lea     rax, ??_7?$StructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<std::wstring,0>::`vftable'
0x18009e0a6  mov     [rbp+90h+var_80], rax
0x18009e0aa  lea     rax, aKeypath; "KeyPath"
0x18009e0b1  mov     [rbp+90h+var_78], rax
0x18009e0b5  movups  xmm1, [rbp+90h+var_A0]
0x18009e0b9  movups  [rbp+90h+var_70], xmm1
0x18009e0bd  movups  xmm0, [rbp+90h+var_90]
0x18009e0c1  movups  [rbp+90h+var_60], xmm0
0x18009e0c5  movdqu  [rbp+90h+var_90], xmm6
0x18009e0ca  mov     word ptr [rbp+90h+var_A0], r13w
0x18009e0cf  mov     [rbp+90h+var_50], r13w
0x18009e0d4  xor     r9d, r9d
0x18009e0d7  mov     edx, 3A7h
0x18009e0dc  mov     ecx, 16928CCh
0x18009e0e1  lea     r8d, [r9+64h]
0x18009e0e5  call    ?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18009e0ea  test    al, al
0x18009e0ec  jz      short loc_18009E14A
  ... truncated ...
```
