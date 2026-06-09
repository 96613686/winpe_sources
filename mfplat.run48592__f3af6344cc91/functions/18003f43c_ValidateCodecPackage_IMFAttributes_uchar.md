# ValidateCodecPackage(IMFAttributes *,uchar *)

- ea: `0x18003f43c`
- end: `0x18003f9cd`
- name: `?ValidateCodecPackage@@YAJPEAUIMFAttributes@@PEAE@Z`
- size: `1425`
- prototype: `__int64 __fastcall(struct IMFAttributes *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d890`
- `0x1800b4ed0`
- `0x1800d4050`
- `0x1801584a4`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003f43c`
- `0x18008f78c`
- `0x1800b095c`
- `0x180117200`
- `0x1801200d0`
- `0x180125958`
- `0x180155aa8`
- `0x18015665c`
- `0x180158400`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f97c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f99e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f97c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f99e`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18003f5f0`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18003f5f0`

## pseudocode

```c
__int64 __fastcall ValidateCodecPackage(struct IMFAttributes *a1, unsigned __int8 *a2)
{
  int MediaExtensionCommunicationFactory; // ebx
  struct Microsoft::WRL::Details::Dummy v5; // r8
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rax
  PackageValidationCache *v9; // rcx
  int v10; // r8d
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  struct Microsoft::WRL::Details::Dummy v14; // r8
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64, unsigned __int8 *); // rdi
  __int64 v19; // rbx
  struct Microsoft::WRL::Details::Dummy v20; // r8
  __int64 v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  unsigned int v24; // edx
  const struct KnownPackageInfo near *const *v25; // r8
  unsigned __int16 *v26; // rax
  int v27; // r9d
  int v28; // ecx
  unsigned __int8 v29; // di
  __int64 v30; // rsi
  __int64 v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rax
  PackageValidationCache *v35; // rcx
  unsigned __int8 v37; // [rsp+30h] [rbp-49h] BYREF
  CallStackScopeTrace v38; // [rsp+31h] [rbp-48h] BYREF
  unsigned __int16 *v39; // [rsp+38h] [rbp-41h] BYREF
  __int64 v40; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v42; // [rsp+50h] [rbp-29h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v43; // [rsp+70h] [rbp-9h] BYREF

  v37 = 0;
  v39 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v38, "ValidateCodecPackage", 110);
  MediaExtensionCommunicationFactory = a1->GetAllocatedString(
                                         a1,
                                         (const _GUID *)MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME,
                                         &v39,
                                         0);
  if ( MediaExtensionCommunicationFactory < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v6->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( ThreadRelativeContext->m_result != MediaExtensionCommunicationFactory )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "ValidateCodecPackage",
          110,
          MediaExtensionCommunicationFactory);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids,
        0,
        MediaExtensionCommunicationFactory);
    goto LABEL_72;
  }
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v42, (const unsigned __int16 *const *)&v39, v5);
  if ( !PackageValidationCache::GetPackage(v9, *(HSTRING *)(v8 + 24), &v37) )
  {
    pv = 0;
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids, v39);
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    MediaExtensionCommunicationFactory = GetMediaExtensionCommunicationFactory(&v40);
    if ( MediaExtensionCommunicationFactory >= 0 )
    {
      MediaExtensionCommunicationFactory = a1->GetAllocatedString(
                                             a1,
                                             (const _GUID *)MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME,
                                             (wchar_t **)&pv,
                                             0);
      if ( MediaExtensionCommunicationFactory >= 0 )
      {
        v17 = v40;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int8 *))(*(_QWORD *)v40 + 64LL);
        v19 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &v42,
                            (const unsigned __int16 *const *)&v39,
                            v14)
                        + 24);
        v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &v43,
                (const unsigned __int16 *const *)&pv,
                v20);
        MediaExtensionCommunicationFactory = v18(v17, *(_QWORD *)(v21 + 24), v19, &v37);
        v43.hstr_ = 0;
        v42.hstr_ = 0;
        if ( MediaExtensionCommunicationFactory >= 0 )
        {
          v24 = 0;
          while ( 1 )
          {
            v25 = &g_KnownPackages + 13 * v24;
            v26 = (unsigned __int16 *)pv;
            do
            {
              v27 = *(unsigned __int16 *)((char *)v26 + *v25 - (const struct KnownPackageInfo near *const)pv);
              v28 = *v26 - v27;
              if ( v28 )
                break;
              ++v26;
            }
            while ( v27 );
            if ( !v28 )
              break;
            if ( ++v24 >= 0x10 )
            {
              v25 = 0;
              break;
            }
          }
          v29 = v37;
          if ( v37 )
          {
            if ( v25 )
            {
              v30 = *((_QWORD *)v25 + 12);
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)(v30 + 2 * v31) );
              if ( v31 )
              {
                if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    21,
                    &WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids,
                    *((_QWORD *)v25 + 12));
                v32 = MFCheckEnabledViaAppService(a1, v30, &v37);
                v33 = v32;
                if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    22,
                    &WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids,
                    v32,
                    v37);
                if ( v33 + 1072843856 > 1 )
                {
                  v29 = v37;
                }
                else
                {
                  v29 = 1;
                  v37 = 1;
                }
                MediaExtensionCommunicationFactory = 0;
              }
            }
          }
          if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
          {
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, (_DWORD)v25, (_DWORD)v39, v29);
            v29 = v37;
          }
          v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &v42,
                  (const unsigned __int16 *const *)&v39,
                  (struct Microsoft::WRL::Details::Dummy)v25);
          PackageValidationCache::AddPackage(v35, *(HSTRING *)(v34 + 24), v29);
          goto LABEL_71;
        }
        v22 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v22 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v22->m_fEnabled )
        {
          v23 = CallStackTracing::GetThreadRelativeContext(v22);
          if ( v23->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(v23, "ValidateCodecPackage", 130, MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
LABEL_71:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          CoTaskMemFree(pv);
          CoTaskMemFree(0);
          goto LABEL_72;
        }
        v13 = 20;
      }
      else
      {
        v15 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v15 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v15->m_fEnabled )
        {
          v16 = CallStackTracing::GetThreadRelativeContext(v15);
          if ( v16->m_result != MediaExtensionCommunicationFactory )
            CallStackContext::TraceFailure(v16, "ValidateCodecPackage", 126, MediaExtensionCommunicationFactory);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_71;
        v13 = 19;
      }
    }
    else
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v11->m_fEnabled )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( v12->m_result != MediaExtensionCommunicationFactory )
          CallStackContext::TraceFailure(v12, "ValidateCodecPackage", 124, MediaExtensionCommunicationFactory);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_71;
      v13 = 18;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids,
      0,
      MediaExtensionCommunicationFactory);
    goto LABEL_71;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x20u )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, v10, (_DWORD)v39, v37);
LABEL_72:
  *a2 = v37;
  CallStackScopeTrace::~CallStackScopeTrace(&v38);
  CoTaskMemFree(v39);
  return (unsigned int)MediaExtensionCommunicationFactory;
}

```

## disassembly

```asm
0x18003f43c  mov     [rsp-8+arg_10], rbx
0x18003f441  push    rbp
0x18003f442  push    rsi
0x18003f443  push    rdi
0x18003f444  push    r12
0x18003f446  push    r13
0x18003f448  push    r14
0x18003f44a  push    r15
0x18003f44c  lea     rbp, [rsp-27h]
0x18003f451  sub     rsp, 0A0h
0x18003f458  mov     rax, cs:__security_cookie
0x18003f45f  xor     rax, rsp
0x18003f462  mov     [rbp+57h+var_40], rax
0x18003f466  xor     r13d, r13d
0x18003f469  lea     rdi, aValidatecodecp; "ValidateCodecPackage"
0x18003f470  mov     r12, rdx
0x18003f473  mov     [rbp+57h+var_A0], r13b
0x18003f477  mov     r15, rcx
0x18003f47a  mov     [rbp+57h+var_98], r13
0x18003f47e  mov     rdx, rdi; char *
0x18003f481  lea     rcx, [rbp+57h+var_9F]; this
0x18003f485  lea     esi, [r13+6Eh]
0x18003f489  mov     r8d, esi; int
0x18003f48c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003f491  mov     rax, [r15]
0x18003f494  lea     r8, [rbp+57h+var_98]
0x18003f498  xor     r9d, r9d
0x18003f49b  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME
0x18003f4a2  mov     rcx, r15
0x18003f4a5  mov     rax, [rax+68h]
0x18003f4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4ae  mov     ebx, eax
0x18003f4b0  test    eax, eax
0x18003f4b2  jns     loc_18003F55E
0x18003f4b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f4bf  test    rcx, rcx
0x18003f4c2  jnz     short loc_18003F505
0x18003f4c4  mov     rcx, cs:stru_1801FC290.__vftable
0x18003f4cb  lea     r8, stru_1801FC290
0x18003f4d2  mov     edx, 7F0h
0x18003f4d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f4de  mov     rax, [rcx+8]
0x18003f4e2  mov     rcx, r8
0x18003f4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4ea  test    eax, eax
0x18003f4ec  jnz     short loc_18003F4FE
0x18003f4ee  lea     rcx, stru_1801F8A30
0x18003f4f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f4fc  jmp     short loc_18003F505
0x18003f4fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003f505  cmp     [rcx+8], r13b
0x18003f509  jz      short loc_18003F529
0x18003f50b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f510  cmp     [rax+7CCh], ebx
0x18003f516  jz      short loc_18003F529
0x18003f518  mov     r9d, ebx; int
0x18003f51b  mov     r8d, esi; int
0x18003f51e  mov     rdx, rdi; char *
0x18003f521  mov     rcx, rax; this
0x18003f524  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f529  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003f530  jb      loc_18003F98A
0x18003f536  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f53d  lea     r8, WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids
0x18003f544  mov     edx, 0Fh
0x18003f549  mov     [rsp+0D0h+var_B0], ebx
0x18003f54d  xor     r9d, r9d
0x18003f550  mov     rcx, [rcx+10h]
0x18003f554  call    WPP_SF_qD
0x18003f559  jmp     loc_18003F98A
0x18003f55e  lea     rdx, [rbp+57h+var_98]; unsigned __int16 **
0x18003f562  lea     rcx, [rbp+57h+var_80]; this
0x18003f566  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f56b  lea     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x18003f56f  mov     rdx, [rax+18h]; HSTRING
0x18003f573  call    ?GetPackage@PackageValidationCache@@QEAA_NPEAUHSTRING__@@PEAE@Z; PackageValidationCache::GetPackage(HSTRING__ *,uchar *)
0x18003f578  test    al, al
0x18003f57a  jz      short loc_18003F5AF
0x18003f57c  cmp     cs:byte_1801FD289, 20h ; ' '
0x18003f583  jb      loc_18003F98A
0x18003f589  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f590  mov     edx, 10h
0x18003f595  movzx   eax, [rbp+57h+var_A0]
0x18003f599  mov     r9, [rbp+57h+var_98]
0x18003f59d  mov     [rsp+0D0h+var_B0], eax
0x18003f5a1  mov     rcx, [rcx+38h]
0x18003f5a5  call    WPP_SF_Sd
0x18003f5aa  jmp     loc_18003F98A
0x18003f5af  mov     [rbp+57h+pv], r13
0x18003f5b3  cmp     cs:byte_1801FD289, 10h
0x18003f5ba  lea     r14, WPP_07710672e97f3e38978d0ba9b4daf81b_Traceguids
0x18003f5c1  jb      short loc_18003F5DF
0x18003f5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5ca  mov     edx, 11h
0x18003f5cf  mov     r9, [rbp+57h+var_98]
0x18003f5d3  mov     r8, r14
0x18003f5d6  mov     rcx, [rcx+38h]
0x18003f5da  call    WPP_SF_S
0x18003f5df  lea     rcx, [rbp+57h+var_90]
0x18003f5e3  mov     [rbp+57h+var_90], r13
0x18003f5e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f5ec  lea     rcx, [rbp+57h+var_90]
0x18003f5f0  call    cs:__imp_GetMediaExtensionCommunicationFactory
0x18003f5f6  mov     ebx, eax
0x18003f5f8  test    eax, eax
0x18003f5fa  jns     loc_18003F6A5
0x18003f600  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f607  test    rcx, rcx
0x18003f60a  jnz     short loc_18003F64D
0x18003f60c  mov     rax, cs:stru_1801FC290.__vftable
0x18003f613  lea     r8, stru_1801FC290
0x18003f61a  mov     edx, 7F0h
0x18003f61f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f626  mov     rcx, r8
0x18003f629  mov     rax, [rax+8]
0x18003f62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f632  test    eax, eax
0x18003f634  jnz     short loc_18003F646
0x18003f636  lea     rcx, stru_1801F8A30
0x18003f63d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f644  jmp     short loc_18003F64D
0x18003f646  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003f64d  cmp     [rcx+8], r13b
0x18003f651  jz      short loc_18003F674
0x18003f653  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f658  cmp     [rax+7CCh], ebx
0x18003f65e  jz      short loc_18003F674
0x18003f660  mov     r9d, ebx; int
0x18003f663  mov     r8d, 7Ch ; '|'; int
0x18003f669  mov     rdx, rdi; char *
0x18003f66c  mov     rcx, rax; this
0x18003f66f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f674  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003f67b  jb      loc_18003F96F
0x18003f681  mov     edx, 12h
0x18003f686  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f68d  xor     r9d, r9d
0x18003f690  mov     r8, r14
0x18003f693  mov     [rsp+0D0h+var_B0], ebx
0x18003f697  mov     rcx, [rcx+10h]
0x18003f69b  call    WPP_SF_qD
0x18003f6a0  jmp     loc_18003F96F
0x18003f6a5  mov     rax, [r15]
0x18003f6a8  lea     r8, [rbp+57h+pv]
0x18003f6ac  xor     r9d, r9d
0x18003f6af  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME
0x18003f6b6  mov     rcx, r15
0x18003f6b9  mov     rax, [rax+68h]
0x18003f6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6c2  mov     ebx, eax
0x18003f6c4  test    eax, eax
0x18003f6c6  jns     loc_18003F757
0x18003f6cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f6d3  test    rcx, rcx
0x18003f6d6  jnz     short loc_18003F719
0x18003f6d8  mov     rax, cs:stru_1801FC290.__vftable
0x18003f6df  lea     r8, stru_1801FC290
0x18003f6e6  mov     edx, 7F0h
0x18003f6eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f6f2  mov     rcx, r8
0x18003f6f5  mov     rax, [rax+8]
0x18003f6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6fe  test    eax, eax
0x18003f700  jnz     short loc_18003F712
0x18003f702  lea     rcx, stru_1801F8A30
0x18003f709  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f710  jmp     short loc_18003F719
0x18003f712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003f719  cmp     [rcx+8], r13b
0x18003f71d  jz      short loc_18003F740
0x18003f71f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f724  cmp     [rax+7CCh], ebx
0x18003f72a  jz      short loc_18003F740
0x18003f72c  mov     r9d, ebx; int
0x18003f72f  mov     r8d, 7Eh ; '~'; int
0x18003f735  mov     rdx, rdi; char *
0x18003f738  mov     rcx, rax; this
0x18003f73b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f740  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003f747  jb      loc_18003F96F
0x18003f74d  mov     edx, 13h
0x18003f752  jmp     loc_18003F686
0x18003f757  mov     rsi, [rbp+57h+var_90]
0x18003f75b  lea     rdx, [rbp+57h+var_98]; unsigned __int16 **
0x18003f75f  lea     rcx, [rbp+57h+var_80]; this
0x18003f763  mov     rax, [rsi]
0x18003f766  mov     rdi, [rax+40h]
0x18003f76a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f76f  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18003f773  lea     rcx, [rbp+57h+var_60]; this
0x18003f777  mov     rbx, [rax+18h]
0x18003f77b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f780  lea     r9, [rbp+57h+var_A0]
0x18003f784  mov     r8, rbx
0x18003f787  mov     rcx, rsi
0x18003f78a  mov     rdx, [rax+18h]
0x18003f78e  mov     rax, rdi
0x18003f791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f796  mov     ebx, eax
0x18003f798  mov     [rbp+57h+var_60.hstr_], r13
0x18003f79c  shr     eax, 1Fh
0x18003f79f  mov     [rbp+57h+var_80.hstr_], r13
0x18003f7a3  test    al, al
0x18003f7a5  jz      loc_18003F83E
0x18003f7ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f7b2  test    rcx, rcx
0x18003f7b5  jnz     short loc_18003F7F8
0x18003f7b7  mov     rax, cs:stru_1801FC290.__vftable
0x18003f7be  lea     r8, stru_1801FC290
0x18003f7c5  mov     edx, 7F0h
0x18003f7ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f7d1  mov     rcx, r8
0x18003f7d4  mov     rax, [rax+8]
0x18003f7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7dd  test    eax, eax
0x18003f7df  jnz     short loc_18003F7F1
0x18003f7e1  lea     rcx, stru_1801F8A30
0x18003f7e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f7ef  jmp     short loc_18003F7F8
0x18003f7f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003f7f8  cmp     [rcx+8], r13b
0x18003f7fc  jz      short loc_18003F827
0x18003f7fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f803  test    ebx, ebx
0x18003f805  jns     short loc_18003F827
0x18003f807  cmp     [rax+7CCh], ebx
0x18003f80d  jz      short loc_18003F827
0x18003f80f  mov     r9d, ebx; int
0x18003f812  lea     rdx, aValidatecodecp; "ValidateCodecPackage"
0x18003f819  mov     r8d, 82h; int
0x18003f81f  mov     rcx, rax; this
0x18003f822  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f827  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003f82e  jb      loc_18003F96F
0x18003f834  mov     edx, 14h
0x18003f839  jmp     loc_18003F686
0x18003f83e  mov     edx, r13d
0x18003f841  mov     eax, edx
0x18003f843  imul    r8, rax, 68h ; 'h'
0x18003f847  lea     rax, ?g_KnownPackages@@3QBUKnownPackageInfo@@B; KnownPackageInfo const near * const g_KnownPackages
0x18003f84e  add     r8, rax
0x18003f851  mov     rax, [rbp+57h+pv]
0x18003f855  mov     r10, [r8]
0x18003f858  sub     r10, rax
0x18003f85b  movzx   ecx, word ptr [rax]
0x18003f85e  movzx   r9d, word ptr [rax+r10]
0x18003f863  sub     ecx, r9d
0x18003f866  jnz     short loc_18003F871
0x18003f868  add     rax, 2
0x18003f86c  test    r9d, r9d
0x18003f86f  jnz     short loc_18003F85B
0x18003f871  test    ecx, ecx
0x18003f873  jz      short loc_18003F87F
0x18003f875  inc     edx
0x18003f877  cmp     edx, 10h
0x18003f87a  jb      short loc_18003F841
0x18003f87c  mov     r8, r13
0x18003f87f  mov     dil, [rbp+57h+var_A0]
0x18003f883  test    dil, dil
0x18003f886  jz      loc_18003F928
0x18003f88c  test    r8, r8
0x18003f88f  jz      loc_18003F928
0x18003f895  mov     rsi, [r8+60h]
0x18003f899  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f89d  inc     rax
0x18003f8a0  cmp     [rsi+rax*2], r13w
0x18003f8a5  jnz     short loc_18003F89D
0x18003f8a7  test    rax, rax
0x18003f8aa  jz      short loc_18003F928
0x18003f8ac  cmp     cs:byte_1801FD289, 10h
0x18003f8b3  jb      short loc_18003F8D0
0x18003f8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8bc  mov     edx, 15h
0x18003f8c1  mov     r9, rsi
0x18003f8c4  mov     r8, r14
0x18003f8c7  mov     rcx, [rcx+38h]
0x18003f8cb  call    WPP_SF_S
0x18003f8d0  lea     r8, [rbp+57h+var_A0]
0x18003f8d4  mov     rdx, rsi
0x18003f8d7  mov     rcx, r15
0x18003f8da  call    MFCheckEnabledViaAppService
0x18003f8df  mov     ebx, eax
0x18003f8e1  cmp     cs:byte_1801FD289, 10h
0x18003f8e8  jb      short loc_18003F90D
0x18003f8ea  movzx   ecx, [rbp+57h+var_A0]
0x18003f8ee  mov     edx, 16h
0x18003f8f3  mov     [rsp+0D0h+var_B0], ecx
0x18003f8f7  mov     r9d, eax
0x18003f8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f901  mov     r8, r14
0x18003f904  mov     rcx, [rcx+38h]
0x18003f908  call    WPP_SF_Dd
0x18003f90d  lea     eax, [rbx+3FF24C50h]
0x18003f913  cmp     eax, 1
0x18003f916  ja      short loc_18003F921
0x18003f918  mov     dil, 1
0x18003f91b  mov     [rbp+57h+var_A0], dil
0x18003f91f  jmp     short loc_18003F925
0x18003f921  mov     dil, [rbp+57h+var_A0]
0x18003f925  mov     ebx, r13d
  ... truncated ...
```
