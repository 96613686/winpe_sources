# CCSDirectTransaction::RealUninstallComponent(CComponentAccessor const &,bool &)

- ea: `0x1800c81d0`
- end: `0x1800c87b0`
- name: `?RealUninstallComponent@CCSDirectTransaction@@IEAAJAEBVCComponentAccessor@@AEA_N@Z`
- size: `1504`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, const struct CComponentAccessor *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d49e0`

## callees

- `0x180012b1c`
- `0x1800172e0`
- `0x180017400`
- `0x180017514`
- `0x180017530`
- `0x18001e9b0`
- `0x18001fc6c`
- `0x180040020`
- `0x18004f2dc`
- `0x180051630`
- `0x1800be06c`
- `0x1800c81d0`
- `0x1800cbb68`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c82e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8756`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c82e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8756`

## string_xrefs

- `0x1800c8292`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c8634`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c8703`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::RealUninstallComponent(
        CCSDirectTransaction *this,
        const struct CComponentAccessor *a2,
        bool *a3)
{
  __int64 v6; // rdx
  __int64 *v7; // r12
  __int64 v8; // r14
  __int64 v9; // rcx
  int SystemIsolatedFilesystem; // ebx
  __int64 v11; // r10
  unsigned int *v12; // r11
  signed int v13; // ecx
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  const struct _LUNICODE_STRING *v17; // r9
  __int128 v18; // xmm0
  __int64 v19; // xmm1_8
  __int128 v20; // xmm0
  __int64 v21; // xmm1_8
  void *v22; // rcx
  void *v23; // rcx
  __int64 v24; // r10
  unsigned int *v25; // r11
  signed int v26; // ecx
  __int64 v28; // [rsp+20h] [rbp-E0h] BYREF
  const char *v29; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+30h] [rbp-D0h]
  void *lpMem; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  const wchar_t *v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+58h] [rbp-A8h]
  _QWORD v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h]
  __int64 *v43; // [rsp+A8h] [rbp-58h]
  int v44; // [rsp+B0h] [rbp-50h]
  __int128 v45; // [rsp+B8h] [rbp-48h]
  _QWORD v46[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int64 v48; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v50[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+100h] [rbp+0h]
  __int128 v52; // [rsp+108h] [rbp+8h]
  const wchar_t *v53; // [rsp+118h] [rbp+18h]
  __int128 v54; // [rsp+120h] [rbp+20h]
  __int64 v55; // [rsp+130h] [rbp+30h]
  __m128i si128; // [rsp+140h] [rbp+40h] BYREF

  *a3 = 1;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v36);
  v6 = *((_QWORD *)this + 96);
  v7 = &g_LUNICODE_STRING__empty_;
  v46[1] = &si128;
  v41 = 48;
  v8 = 0;
  v47 = 0;
  v42 = 0;
  v43 = &g_LUNICODE_STRING__empty_;
  v44 = 64;
  v45 = 0;
  v46[0] = 4;
  si128 = _mm_load_si128((const __m128i *)&_xmm_c000003ac0000034c0000043c0000022);
  v28 = 0;
  SystemIsolatedFilesystem = RtlGetSystemIsolatedFilesystem(v9, v6, &v28);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  v14 = (_QWORD *)((char *)a2 + 8);
  v33 = (const wchar_t *)*((_QWORD *)a2 + 3);
  v34 = *((_QWORD *)a2 + 1) >> 1;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v36,
                               &v33);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  v33 = L".manifest";
  v34 = 9;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v36,
                               &v33);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  v41 = 48;
  v38 = 2 * v37;
  v39 = 2 * v37;
  v40 = v36[0];
  v42 = *((_QWORD *)this + 98);
  v43 = &v38;
  v44 = 64;
  v45 = 0;
  LODWORD(v47) = 0;
  SystemIsolatedFilesystem = RtlIsolatedFilesystemDeleteFile(v28, &v41, v46);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  if ( (_DWORD)v47 == -1073741757 || (_DWORD)v47 == -1073741790 )
    *a3 = 0;
  v33 = (const wchar_t *)*((_QWORD *)a2 + 3);
  v34 = *v14 >> 1;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v36,
                               &v33);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  v33 = L".cdf-ms";
  v34 = 7;
  SystemIsolatedFilesystem = BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<unsigned short,unsigned __int64>>(
                               v36,
                               &v33);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  v41 = 48;
  v38 = 2 * v37;
  v39 = 2 * v37;
  v40 = v36[0];
  v42 = *((_QWORD *)this + 98);
  v43 = &v38;
  v44 = 64;
  v45 = 0;
  LODWORD(v47) = 0;
  SystemIsolatedFilesystem = RtlIsolatedFilesystemDeleteFile(v28, &v41, v46);
  if ( SystemIsolatedFilesystem < 0 )
  {
LABEL_2:
    if ( !v28 )
      goto LABEL_52;
    ++g_nRtlCloseIsolatedFilesystemHandle;
    LODWORD(lpMem) = -1073741595;
    v29 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v28) )
    {
      LODWORD(v30) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v29);
      v13 = (int)lpMem;
      goto LABEL_6;
    }
LABEL_5:
    (*((void (__fastcall **)(_QWORD, __int64))v12 + 4))(*v12, v11);
    v13 = 0;
LABEL_6:
    if ( v13 < 0 )
      RaiseException(v13, 1u, 0, 0);
    v28 = 0;
    goto LABEL_52;
  }
  if ( (_DWORD)v47 == -1073741757 || (_DWORD)v47 == -1073741790 )
    *a3 = 0;
  v29 = (const char *)*((_QWORD *)this + 103);
  v30 = *((_QWORD *)this + 101);
  lpMem = (void *)*((_QWORD *)this + 102);
  v32 = *((_QWORD *)this + 104);
  do
  {
    SystemIsolatedFilesystem = Windows::Isolation::HierLib::Rtl::DeleteChildHierarchyRecursivelyByName(
                                 v15,
                                 (&v29)[v8],
                                 (char *)a2 + 8,
                                 0);
    if ( SystemIsolatedFilesystem < 0 )
    {
      if ( v28 )
      {
        ++g_nRtlCloseIsolatedFilesystemHandle;
        LODWORD(lpMem) = -1073741595;
        v29 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v28) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v25 + 4))(*v25, v24);
          v26 = 0;
        }
        else
        {
          LODWORD(v30) = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v29);
          v26 = (int)lpMem;
        }
        if ( v26 < 0 )
          RaiseException(v26, 1u, 0, 0);
        v28 = 0;
      }
      goto LABEL_52;
    }
    ++v8;
  }
  while ( v8 != 4 );
  v16 = *((_QWORD *)this + 99);
  v48 = 16;
  v49 = 0;
  v41 = 48;
  v42 = v16;
  if ( a2 != (const struct CComponentAccessor *)-8LL )
    v7 = (__int64 *)((char *)a2 + 8);
  v44 = 64;
  v43 = v7;
  v45 = 0;
  SystemIsolatedFilesystem = Windows::Isolation::Implementation::Rtl::DeleteDirectoryRecursively(0, v28, &v41, &v48);
  if ( SystemIsolatedFilesystem < 0 )
    goto LABEL_2;
  if ( (_DWORD)v49 == 3 )
    *a3 = 0;
  if ( !*((_QWORD *)this + 89) )
    goto LABEL_44;
  v18 = *((_OWORD *)this + 45);
  v33 = 0;
  v19 = *((_QWORD *)this + 92);
  *(_OWORD *)v50 = v18;
  v30 = 0;
  v51 = v19;
  v52 = g_LUNICODE_STRING__bslash_;
  v29 = 0;
  v20 = *(_OWORD *)v14;
  lpMem = 0;
  v53 = L"\\";
  v21 = *((_QWORD *)a2 + 3);
  v54 = v20;
  v55 = v21;
  SystemIsolatedFilesystem = Windows::Rtl::Concatenate(
                               (Windows::Rtl *)&v29,
                               (struct _LUNICODE_STRING *)3,
                               (unsigned __int64)v50,
                               v17);
  if ( SystemIsolatedFilesystem >= 0 )
  {
    SystemIsolatedFilesystem = CCSDirectTransaction::GetComponentManifest(
                                 this,
                                 a2,
                                 (struct Windows::Cdf::Rtl::_CDF *)&v33);
    if ( SystemIsolatedFilesystem >= 0 )
    {
      if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(v33)
        || (SystemIsolatedFilesystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const char **))(**((_QWORD **)this + 89) + 24LL))(
                                         *((_QWORD *)this + 89),
                                         v33,
                                         &v29),
            SystemIsolatedFilesystem >= 0) )
      {
        v23 = lpMem;
        if ( lpMem )
        {
          v30 = 0;
          v29 = 0;
          lpMem = 0;
          IsolationFreeStringRoutine(v23);
        }
LABEL_44:
        SystemIsolatedFilesystem = 0;
        goto LABEL_2;
      }
    }
  }
  v22 = lpMem;
  if ( lpMem )
  {
    v30 = 0;
    v29 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v22);
  }
  if ( v28 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v35 = -1073741595;
    v33 = (const wchar_t *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      || !(unsigned __int8)RtlIsTypeSafeHandleValid(v28) )
    {
      LODWORD(v34) = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v33);
      v13 = v35;
      goto LABEL_6;
    }
    goto LABEL_5;
  }
LABEL_52:
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v36);
  return (unsigned int)SystemIsolatedFilesystem;
}

```

## disassembly

```asm
0x1800c81d0  mov     [rsp-8+arg_18], rbx
0x1800c81d5  push    rbp
0x1800c81d6  push    rsi
0x1800c81d7  push    rdi
0x1800c81d8  push    r12
0x1800c81da  push    r13
0x1800c81dc  push    r14
0x1800c81de  push    r15
0x1800c81e0  lea     rbp, [rsp-60h]
0x1800c81e5  sub     rsp, 160h
0x1800c81ec  mov     rax, cs:__security_cookie
0x1800c81f3  xor     rax, rsp
0x1800c81f6  mov     [rbp+90h+var_40], rax
0x1800c81fa  mov     rdi, rcx
0x1800c81fd  mov     byte ptr [r8], 1
0x1800c8201  lea     rcx, [rsp+190h+var_130]; this
0x1800c8206  mov     r15, r8
0x1800c8209  mov     r13, rdx
0x1800c820c  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800c8211  movdqa  xmm1, cs:__xmm@c000003ac0000034c0000043c0000022
0x1800c8219  lea     rax, [rbp+90h+var_50]
0x1800c821d  mov     rdx, [rdi+300h]
0x1800c8224  lea     r12, g_LUNICODE_STRING__empty_
0x1800c822b  mov     [rbp+90h+var_C0], rax
0x1800c822f  lea     r8, [rsp+190h+var_170]
0x1800c8234  xor     eax, eax
0x1800c8236  mov     [rbp+90h+var_F8], 30h ; '0'
0x1800c823e  xor     r14d, r14d
0x1800c8241  mov     [rbp+90h+var_B8], rax
0x1800c8245  xorps   xmm0, xmm0
0x1800c8248  mov     [rbp+90h+var_F0], r14
0x1800c824c  mov     [rbp+90h+var_E8], r12
0x1800c8250  mov     [rbp+90h+var_E0], 40h ; '@'
0x1800c8257  movdqu  [rbp+90h+var_D8], xmm0
0x1800c825c  mov     [rbp+90h+var_C8], 4
0x1800c8264  movdqu  [rbp+90h+var_50], xmm1
0x1800c8269  mov     [rsp+190h+var_170], r14
0x1800c826e  call    RtlGetSystemIsolatedFilesystem
0x1800c8273  mov     ebx, eax
0x1800c8275  test    eax, eax
0x1800c8277  jns     loc_1800C830E
0x1800c827d  mov     r10, [rsp+190h+var_170]
0x1800c8282  test    r10, r10
0x1800c8285  jz      loc_1800C8765
0x1800c828b  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c8292  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c8299  mov     dword ptr [rsp+190h+lpMem], 0C00000E5h
0x1800c82a1  mov     [rsp+190h+var_168], rax
0x1800c82a6  test    r10, r10
0x1800c82a9  jz      short loc_1800C82D5
0x1800c82ab  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c82b2  test    r11, r11
0x1800c82b5  jz      short loc_1800C82F6
0x1800c82b7  mov     rdx, r11
0x1800c82ba  mov     rcx, r10
0x1800c82bd  call    RtlIsTypeSafeHandleValid
0x1800c82c2  test    al, al
0x1800c82c4  jz      short loc_1800C82F6
0x1800c82c6  mov     ecx, [r11]
0x1800c82c9  mov     rdx, r10
0x1800c82cc  mov     rax, [r11+20h]
0x1800c82d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c82d5  mov     ecx, r14d; dwExceptionCode
0x1800c82d8  test    ecx, ecx
0x1800c82da  jns     short loc_1800C82EC
0x1800c82dc  xor     r9d, r9d; lpArguments
0x1800c82df  xor     r8d, r8d; nNumberOfArguments
0x1800c82e2  lea     edx, [r9+1]; dwExceptionFlags
0x1800c82e6  call    cs:__imp_RaiseException
0x1800c82ec  mov     [rsp+190h+var_170], r14
0x1800c82f1  jmp     loc_1800C8765
0x1800c82f6  mov     dword ptr [rsp+190h+var_160], 124h
0x1800c82fe  lea     rcx, [rsp+190h+var_168]
0x1800c8303  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c8308  mov     ecx, dword ptr [rsp+190h+lpMem]
0x1800c830c  jmp     short loc_1800C82D8
0x1800c830e  lea     rsi, [r13+8]
0x1800c8312  mov     rax, [rsi+10h]
0x1800c8316  lea     rdx, [rsp+190h+var_148]
0x1800c831b  mov     [rsp+190h+var_148], rax
0x1800c8320  lea     rcx, [rsp+190h+var_130]
0x1800c8325  mov     rax, [rsi]
0x1800c8328  shr     rax, 1
0x1800c832b  mov     [rsp+190h+var_140], rax
0x1800c8330  call    ??$public_Assign@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800c8335  mov     ebx, eax
0x1800c8337  test    eax, eax
0x1800c8339  js      loc_1800C827D
0x1800c833f  mov     rax, cs:off_180136F68; ".manifest"
0x1800c8346  lea     rdx, [rsp+190h+var_148]
0x1800c834b  lea     rcx, [rsp+190h+var_130]
0x1800c8350  mov     [rsp+190h+var_148], rax
0x1800c8355  mov     [rsp+190h+var_140], 9
0x1800c835e  call    ??$public_Append@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800c8363  mov     ebx, eax
0x1800c8365  test    eax, eax
0x1800c8367  js      loc_1800C827D
0x1800c836d  mov     rax, [rsp+190h+var_120]
0x1800c8372  lea     r8, [rbp+90h+var_C8]
0x1800c8376  mov     rcx, [rsp+190h+var_170]
0x1800c837b  lea     rdx, [rbp+90h+var_F8]
0x1800c837f  add     rax, rax
0x1800c8382  mov     [rbp+90h+var_F8], 30h ; '0'
0x1800c838a  mov     [rbp+90h+var_110], rax
0x1800c838e  xorps   xmm0, xmm0
0x1800c8391  mov     [rbp+90h+var_108], rax
0x1800c8395  mov     rax, [rsp+190h+var_130]
0x1800c839a  mov     [rbp+90h+var_100], rax
0x1800c839e  mov     rax, [rdi+310h]
0x1800c83a5  mov     [rbp+90h+var_F0], rax
0x1800c83a9  lea     rax, [rbp+90h+var_110]
0x1800c83ad  mov     [rbp+90h+var_E8], rax
0x1800c83b1  mov     [rbp+90h+var_E0], 40h ; '@'
0x1800c83b8  movdqu  [rbp+90h+var_D8], xmm0
0x1800c83bd  mov     dword ptr [rbp+90h+var_B8], r14d
0x1800c83c1  call    RtlIsolatedFilesystemDeleteFile
0x1800c83c6  mov     ebx, eax
0x1800c83c8  test    eax, eax
0x1800c83ca  js      loc_1800C827D
0x1800c83d0  cmp     dword ptr [rbp+90h+var_B8], 0C0000043h
0x1800c83d7  jz      short loc_1800C83E2
0x1800c83d9  cmp     dword ptr [rbp+90h+var_B8], 0C0000022h
0x1800c83e0  jnz     short loc_1800C83E5
0x1800c83e2  mov     [r15], r14b
0x1800c83e5  mov     rax, [rsi+10h]
0x1800c83e9  lea     rdx, [rsp+190h+var_148]
0x1800c83ee  mov     [rsp+190h+var_148], rax
0x1800c83f3  lea     rcx, [rsp+190h+var_130]
0x1800c83f8  mov     rax, [rsi]
0x1800c83fb  shr     rax, 1
0x1800c83fe  mov     [rsp+190h+var_140], rax
0x1800c8403  call    ??$public_Assign@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Assign<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800c8408  mov     ebx, eax
0x1800c840a  test    eax, eax
0x1800c840c  js      loc_1800C827D
0x1800c8412  mov     rax, cs:off_180136F20; ".cdf-ms"
0x1800c8419  lea     rdx, [rsp+190h+var_148]
0x1800c841e  lea     rcx, [rsp+190h+var_130]
0x1800c8423  mov     [rsp+190h+var_148], rax
0x1800c8428  mov     [rsp+190h+var_140], 7
0x1800c8431  call    ??$public_Append@V?$CConstantPointerAndCountPair@G_K@BCL@@@?$CPureString@VCUnicodeStringBufferTraits@Nt@BCL@@@BCL@@IEAAJAEBV?$CConstantPointerAndCountPair@G_K@1@@Z; BCL::CPureString<BCL::Nt::CUnicodeStringBufferTraits>::public_Append<BCL::CConstantPointerAndCountPair<ushort,unsigned __int64>>(BCL::CConstantPointerAndCountPair<ushort,unsigned __int64> const &)
0x1800c8436  mov     ebx, eax
0x1800c8438  test    eax, eax
0x1800c843a  js      loc_1800C827D
0x1800c8440  mov     rax, [rsp+190h+var_120]
0x1800c8445  lea     r8, [rbp+90h+var_C8]
0x1800c8449  mov     rcx, [rsp+190h+var_170]
0x1800c844e  lea     rdx, [rbp+90h+var_F8]
0x1800c8452  add     rax, rax
0x1800c8455  mov     [rbp+90h+var_F8], 30h ; '0'
0x1800c845d  mov     [rbp+90h+var_110], rax
0x1800c8461  xorps   xmm0, xmm0
0x1800c8464  mov     [rbp+90h+var_108], rax
0x1800c8468  mov     rax, [rsp+190h+var_130]
0x1800c846d  mov     [rbp+90h+var_100], rax
0x1800c8471  mov     rax, [rdi+310h]
0x1800c8478  mov     [rbp+90h+var_F0], rax
0x1800c847c  lea     rax, [rbp+90h+var_110]
0x1800c8480  mov     [rbp+90h+var_E8], rax
0x1800c8484  mov     [rbp+90h+var_E0], 40h ; '@'
0x1800c848b  movdqu  [rbp+90h+var_D8], xmm0
0x1800c8490  mov     dword ptr [rbp+90h+var_B8], r14d
0x1800c8494  call    RtlIsolatedFilesystemDeleteFile
0x1800c8499  mov     ebx, eax
0x1800c849b  test    eax, eax
0x1800c849d  js      loc_1800C827D
0x1800c84a3  cmp     dword ptr [rbp+90h+var_B8], 0C0000043h
0x1800c84aa  jz      short loc_1800C84B5
0x1800c84ac  cmp     dword ptr [rbp+90h+var_B8], 0C0000022h
0x1800c84b3  jnz     short loc_1800C84B8
0x1800c84b5  mov     [r15], r14b
0x1800c84b8  mov     rax, [rdi+338h]
0x1800c84bf  mov     [rsp+190h+var_168], rax
0x1800c84c4  mov     rax, [rdi+328h]
0x1800c84cb  mov     [rsp+190h+var_160], rax
0x1800c84d0  mov     rax, [rdi+330h]
0x1800c84d7  mov     [rsp+190h+lpMem], rax
0x1800c84dc  mov     rax, [rdi+340h]
0x1800c84e3  mov     [rsp+190h+var_150], rax
0x1800c84e8  mov     rdx, [rsp+r14*8+190h+var_168]
0x1800c84ed  xor     r9d, r9d
0x1800c84f0  mov     r8, rsi
0x1800c84f3  call    ?DeleteChildHierarchyRecursivelyByName@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@PEBU_LUNICODE_STRING@@PEAU_DELETE_CHILD_HIERARCHY_RECURSIVELY_BY_NAME_DISPOSITION@1234@@Z; Windows::Isolation::HierLib::Rtl::DeleteChildHierarchyRecursivelyByName(ulong,Windows::Isolation::Rtl::_HIERARCHY,_LUNICODE_STRING const *,Windows::Isolation::HierLib::Rtl::_DELETE_CHILD_HIERARCHY_RECURSIVELY_BY_NAME_DISPOSITION *)
0x1800c84f8  mov     ebx, eax
0x1800c84fa  test    eax, eax
0x1800c84fc  js      loc_1800C86F2
0x1800c8502  inc     r14
0x1800c8505  cmp     r14, 4
0x1800c8509  jnz     short loc_1800C84E8
0x1800c850b  mov     rax, [rdi+318h]
0x1800c8512  lea     r9, [rbp+90h+var_B0]
0x1800c8516  mov     rdx, [rsp+190h+var_170]
0x1800c851b  lea     r8, [rbp+90h+var_F8]
0x1800c851f  xor     r14d, r14d
0x1800c8522  mov     [rbp+90h+var_B0], 10h
0x1800c852a  xorps   xmm0, xmm0
0x1800c852d  mov     [rbp+90h+var_A8], r14
0x1800c8531  test    rsi, rsi
0x1800c8534  mov     [rbp+90h+var_F8], 30h ; '0'
0x1800c853c  mov     [rbp+90h+var_F0], rax
0x1800c8540  cmovnz  r12, rsi
0x1800c8544  mov     [rbp+90h+var_E0], 40h ; '@'
0x1800c854b  xor     ecx, ecx
0x1800c854d  mov     [rbp+90h+var_E8], r12
0x1800c8551  movdqu  [rbp+90h+var_D8], xmm0
0x1800c8556  call    ?DeleteDirectoryRecursively@Rtl@Implementation@Isolation@Windows@@YAJKU_ISOLATED_FILESYSTEM@134@PEBU_ISOLATED_OBJECT_ATTRIBUTES@134@PEAVCDeleteDirectoryRecursivelyDisposition@1234@@Z; Windows::Isolation::Implementation::Rtl::DeleteDirectoryRecursively(ulong,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,Windows::Isolation::Implementation::Rtl::CDeleteDirectoryRecursivelyDisposition *)
0x1800c855b  mov     ebx, eax
0x1800c855d  test    eax, eax
0x1800c855f  js      loc_1800C827D
0x1800c8565  lea     edx, [r14+3]; struct _LUNICODE_STRING *
0x1800c8569  cmp     dword ptr [rbp+90h+var_A8], edx
0x1800c856c  jnz     short loc_1800C8571
0x1800c856e  mov     [r15], r14b
0x1800c8571  cmp     [rdi+2C8h], r14
0x1800c8578  jz      loc_1800C86EA
0x1800c857e  movups  xmm0, xmmword ptr [rdi+2D0h]
0x1800c8585  lea     r8, [rbp+90h+var_A0]; unsigned __int64
0x1800c8589  mov     [rsp+190h+var_148], r14
0x1800c858e  movsd   xmm1, qword ptr [rdi+2E0h]
0x1800c8596  lea     rcx, [rsp+190h+var_168]; this
0x1800c859b  movaps  xmmword ptr [rbp+90h+var_A0], xmm0
0x1800c859f  movups  xmm0, cs:g_LUNICODE_STRING__bslash_
0x1800c85a6  mov     [rsp+190h+var_160], r14
0x1800c85ab  movsd   [rbp+90h+var_90], xmm1
0x1800c85b0  movsd   xmm1, cs:off_180136E30; "\\"
0x1800c85b8  movups  [rbp+90h+var_88], xmm0
0x1800c85bc  mov     [rsp+190h+var_168], r14
0x1800c85c1  movups  xmm0, xmmword ptr [rsi]
0x1800c85c4  mov     [rsp+190h+lpMem], r14
0x1800c85c9  movsd   [rbp+90h+var_78], xmm1
0x1800c85ce  movsd   xmm1, qword ptr [rsi+10h]
0x1800c85d3  movaps  [rbp+90h+var_70], xmm0
0x1800c85d7  movsd   [rbp+90h+var_60], xmm1
0x1800c85dc  call    ?Concatenate@Rtl@Windows@@YAJPEAU_LUNICODE_STRING@@_KQEBU3@@Z; Windows::Rtl::Concatenate(_LUNICODE_STRING *,unsigned __int64,_LUNICODE_STRING const * const)
0x1800c85e1  mov     ebx, eax
0x1800c85e3  test    eax, eax
0x1800c85e5  js      short loc_1800C8601
0x1800c85e7  lea     r8, [rsp+190h+var_148]; struct Windows::Cdf::Rtl::_CDF *
0x1800c85ec  mov     rdx, r13; struct CComponentAccessor *
0x1800c85ef  mov     rcx, rdi; this
0x1800c85f2  call    ?GetComponentManifest@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_CDF@Rtl@Cdf@Windows@@@Z; CCSDirectTransaction::GetComponentManifest(CComponentAccessor const &,Windows::Cdf::Rtl::_CDF &)
0x1800c85f7  mov     ebx, eax
0x1800c85f9  test    eax, eax
0x1800c85fb  jns     loc_1800C868B
0x1800c8601  mov     rcx, [rsp+190h+lpMem]; lpMem
0x1800c8606  test    rcx, rcx
0x1800c8609  jz      short loc_1800C861F
0x1800c860b  mov     [rsp+190h+var_160], r14
0x1800c8610  mov     [rsp+190h+var_168], r14
0x1800c8615  mov     [rsp+190h+lpMem], r14
0x1800c861a  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c861f  mov     r10, [rsp+190h+var_170]
0x1800c8624  test    r10, r10
0x1800c8627  jz      loc_1800C8765
0x1800c862d  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c8634  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c863b  mov     [rsp+190h+var_138], 0C00000E5h
0x1800c8643  mov     [rsp+190h+var_148], rax
0x1800c8648  test    r10, r10
0x1800c864b  jz      loc_1800C82D5
0x1800c8651  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c8658  test    r11, r11
0x1800c865b  jz      short loc_1800C8670
0x1800c865d  mov     rdx, r11
0x1800c8660  mov     rcx, r10
0x1800c8663  call    RtlIsTypeSafeHandleValid
0x1800c8668  test    al, al
0x1800c866a  jnz     loc_1800C82C6
0x1800c8670  mov     dword ptr [rsp+190h+var_140], 124h
0x1800c8678  lea     rcx, [rsp+190h+var_148]
0x1800c867d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c8682  mov     ecx, [rsp+190h+var_138]
0x1800c8686  jmp     loc_1800C82D8
0x1800c868b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x1800c8692  test    rdx, rdx
0x1800c8695  jz      short loc_1800C86CC
0x1800c8697  mov     rcx, [rsp+190h+var_148]
0x1800c869c  call    RtlIsTypeSafeHandleValid
0x1800c86a1  test    al, al
0x1800c86a3  jz      short loc_1800C86CC
0x1800c86a5  mov     rcx, [rdi+2C8h]
0x1800c86ac  lea     r8, [rsp+190h+var_168]
0x1800c86b1  mov     rdx, [rsp+190h+var_148]
0x1800c86b6  mov     rax, [rcx]
0x1800c86b9  mov     rax, [rax+18h]
0x1800c86bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c86c2  mov     ebx, eax
0x1800c86c4  test    eax, eax
0x1800c86c6  js      loc_1800C8601
0x1800c86cc  mov     rcx, [rsp+190h+lpMem]; lpMem
0x1800c86d1  test    rcx, rcx
0x1800c86d4  jz      short loc_1800C86EA
0x1800c86d6  mov     [rsp+190h+var_160], r14
0x1800c86db  mov     [rsp+190h+var_168], r14
0x1800c86e0  mov     [rsp+190h+lpMem], r14
0x1800c86e5  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c86ea  mov     ebx, r14d
0x1800c86ed  jmp     loc_1800C827D
0x1800c86f2  mov     r10, [rsp+190h+var_170]
0x1800c86f7  test    r10, r10
  ... truncated ...
```
