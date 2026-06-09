# SetPackagedActivateAttributes(IMFActivate *,MF_PLUGIN_CONTROL_POLICY,CodecPackInfo &)

- ea: `0x1801934b0`
- end: `0x180193c00`
- name: `?SetPackagedActivateAttributes@@YAJPEAUIMFActivate@@W4MF_PLUGIN_CONTROL_POLICY@@AEAUCodecPackInfo@@@Z`
- size: `1872`
- prototype: `__int64 __fastcall(struct IMFActivate *, enum MF_PLUGIN_CONTROL_POLICY, struct CodecPackInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180145550`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800aba9c`
- `0x1800b90c4`
- `0x180120030`
- `0x1801200d0`
- `0x1801934b0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801936d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18019370b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180193740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801936d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18019370b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180193740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019381d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019381d`

## string_xrefs

- `0x180193725`: `Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe`
- `0x1801936ec`: `Microsoft.HEVCVideoExtension_8wekyb3d8bbwe`
- `0x1801936b4`: `Microsoft.AVCEncoderVideoExtension_8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall SetPackagedActivateAttributes(struct IMFActivate *a1, enum MF_PLUGIN_CONTROL_POLICY a2, HSTRING *a3)
{
  int v6; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // r14
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  char *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  HRESULT (__stdcall *SetString)(IMFActivate *, const GUID *const, LPCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackScopeTrace v29; // [rsp+30h] [rbp-59h] BYREF
  INT32 result; // [rsp+34h] [rbp-55h] BYREF
  int v31; // [rsp+38h] [rbp-51h] BYREF
  int v32; // [rsp+3Ch] [rbp-4Dh] BYREF
  void *v33; // [rsp+40h] [rbp-49h] BYREF
  void *v34; // [rsp+48h] [rbp-41h] BYREF
  __int64 v35; // [rsp+50h] [rbp-39h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v36; // [rsp+58h] [rbp-31h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v37; // [rsp+78h] [rbp-11h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v38; // [rsp+98h] [rbp+Fh] BYREF

  v32 = 0;
  v31 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v29, "SetPackagedActivateAttributes", 1850);
  v6 = SetPackagedActivateAttributesCommon(a1, a2, (struct InprocMFTExtensionInfo *)a3);
  if ( v6 >= 0 )
  {
    v10 = a3 + 56;
    v6 = ((__int64 (__fastcall *)(struct IMFActivate *, const GUID *, HSTRING *))a1->lpVtbl->SetGUID)(
           a1,
           &MF_TRANSFORM_CATEGORY_Attribute,
           a3 + 56);
    if ( v6 >= 0 )
    {
      if ( *((_BYTE *)a3 + 33) )
      {
        v13 = (char *)(*v10 - *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1);
        if ( *v10 == *(_QWORD *)&MFT_CATEGORY_VIDEO_ENCODER.Data1 )
          v13 = (char *)a3[57] - *(_QWORD *)MFT_CATEGORY_VIDEO_ENCODER.Data4;
        if ( !v13 && ((_BYTE)a3[8] & 6) != 0 )
        {
          if ( (result = 0,
                v36.hstr_ = 0,
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &v36,
                  L"Microsoft.AVCEncoderVideoExtension_8wekyb3d8bbwe",
                  0x31u,
                  0x30u),
                WindowsCompareStringOrdinal(*a3, v36.hstr_, &result) >= 0)
            && !result
            || (v37.hstr_ = 0,
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &v37,
                  L"Microsoft.HEVCVideoExtension_8wekyb3d8bbwe",
                  0x2Bu,
                  0x2Au),
                WindowsCompareStringOrdinal(*a3, v37.hstr_, &result) >= 0)
            && !result
            || (v38.hstr_ = 0,
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &v38,
                  L"Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe",
                  0x31u,
                  0x30u),
                WindowsCompareStringOrdinal(*a3, v38.hstr_, &result) >= 0)
            && !result )
          {
            v6 = ((__int64 (__fastcall *)(struct IMFActivate *, __int64 *, const wchar_t *))a1->lpVtbl->SetString)(
                   a1,
                   MFT_ENUM_HARDWARE_VENDOR_ID_Attribute,
                   L"VEN_1414");
            if ( v6 < 0 )
            {
              v14 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v14 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v14 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v14->m_fEnabled )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
                if ( ThreadRelativeContext->m_result != v6 )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "SetPackagedActivateAttributes", 1865, v6);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v9 = 241;
                goto LABEL_92;
              }
              goto LABEL_93;
            }
            SetString = a1->lpVtbl->SetString;
            StringRawBuffer = WindowsGetStringRawBuffer(a3[3], 0);
            v6 = ((__int64 (__fastcall *)(struct IMFActivate *, const GUID *, PCWSTR))SetString)(
                   a1,
                   &MFT_ENUM_HARDWARE_URL_Attribute,
                   StringRawBuffer);
            if ( v6 < 0 )
            {
              v18 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v18 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v18 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v18->m_fEnabled )
              {
                v19 = CallStackTracing::GetThreadRelativeContext(v18);
                if ( v19->m_result != v6 )
                  CallStackContext::TraceFailure(v19, "SetPackagedActivateAttributes", 1866, v6);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v9 = 242;
                goto LABEL_92;
              }
              goto LABEL_93;
            }
          }
        }
      }
      v6 = AllocTypesAndPopulate(a3 + 58, a3 + 9, &v32, &v33);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IMFActivate *, const GUID *, void *, _QWORD))a1->lpVtbl->SetBlob)(
               a1,
               &MFT_INPUT_TYPES_Attributes,
               v33,
               (unsigned int)(32 * v32));
        if ( v6 >= 0 )
        {
          v6 = AllocTypesAndPopulate(a3 + 58, a3 + 60, &v31, &v34);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(struct IMFActivate *, const GUID *, void *, _QWORD))a1->lpVtbl->SetBlob)(
                   a1,
                   &MFT_OUTPUT_TYPES_Attributes,
                   v34,
                   (unsigned int)(32 * v31));
            if ( v6 < 0 )
            {
              v26 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v26 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v26 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v26->m_fEnabled )
              {
                v27 = CallStackTracing::GetThreadRelativeContext(v26);
                if ( v27->m_result != v6 )
                  CallStackContext::TraceFailure(v27, "SetPackagedActivateAttributes", 1881, v6);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v9 = 246;
                goto LABEL_92;
              }
            }
          }
          else
          {
            v24 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v24 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v24->m_fEnabled )
            {
              v25 = CallStackTracing::GetThreadRelativeContext(v24);
              if ( v25->m_result != v6 )
                CallStackContext::TraceFailure(v25, "SetPackagedActivateAttributes", 1876, v6);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v9 = 245;
              goto LABEL_92;
            }
          }
        }
        else
        {
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
            if ( v23->m_result != v6 )
              CallStackContext::TraceFailure(v23, "SetPackagedActivateAttributes", 1874, v6);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v9 = 244;
            goto LABEL_92;
          }
        }
      }
      else
      {
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v20 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v20->m_fEnabled )
        {
          v21 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( v21->m_result != v6 )
            CallStackContext::TraceFailure(v21, "SetPackagedActivateAttributes", 1869, v6);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v9 = 243;
          goto LABEL_92;
        }
      }
      goto LABEL_93;
    }
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
      if ( v12->m_result != v6 )
        CallStackContext::TraceFailure(v12, "SetPackagedActivateAttributes", 1852, v6);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 240;
      goto LABEL_92;
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v8->m_result != v6 )
        CallStackContext::TraceFailure(v8, "SetPackagedActivateAttributes", 1850, v6);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v9 = 239;
LABEL_92:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v6);
    }
  }
LABEL_93:
  operator delete(v33);
  operator delete(v34);
  CallStackScopeTrace::~CallStackScopeTrace(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801934b0  mov     [rsp-8+arg_8], rbx
0x1801934b5  mov     [rsp-8+arg_18], rsi
0x1801934ba  push    rbp
0x1801934bb  push    rdi
0x1801934bc  push    r12
0x1801934be  push    r14
0x1801934c0  push    r15
0x1801934c2  lea     rbp, [rsp-37h]
0x1801934c7  sub     rsp, 0C0h
0x1801934ce  mov     rax, cs:__security_cookie
0x1801934d5  xor     rax, rsp
0x1801934d8  mov     [rbp+57h+var_28], rax
0x1801934dc  xor     r15d, r15d
0x1801934df  lea     r12, aSetpackagedact; "SetPackagedActivateAttributes"
0x1801934e6  mov     rdi, r8
0x1801934e9  mov     [rbp+57h+var_A4], r15d
0x1801934ed  mov     ebx, edx
0x1801934ef  mov     [rbp+57h+var_A8], r15d
0x1801934f3  mov     rsi, rcx
0x1801934f6  mov     [rbp+57h+var_90], r15
0x1801934fa  mov     r14d, 73Ah
0x180193500  mov     [rbp+57h+var_A0], r15
0x180193504  mov     r8d, r14d; int
0x180193507  mov     [rbp+57h+var_98], r15
0x18019350b  mov     rdx, r12; char *
0x18019350e  lea     rcx, [rbp+57h+var_B0]; this
0x180193512  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180193517  mov     r8, rdi; struct InprocMFTExtensionInfo *
0x18019351a  mov     edx, ebx; enum MF_PLUGIN_CONTROL_POLICY
0x18019351c  mov     rcx, rsi; struct IMFActivate *
0x18019351f  call    ?SetPackagedActivateAttributesCommon@@YAJPEAUIMFActivate@@W4MF_PLUGIN_CONTROL_POLICY@@AEAUInprocMFTExtensionInfo@@@Z; SetPackagedActivateAttributesCommon(IMFActivate *,MF_PLUGIN_CONTROL_POLICY,InprocMFTExtensionInfo &)
0x180193524  mov     ebx, eax
0x180193526  test    eax, eax
0x180193528  jns     loc_1801935B6
0x18019352e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180193535  test    rcx, rcx
0x180193538  jnz     short loc_18019357B
0x18019353a  mov     rcx, cs:stru_1801FC290.__vftable
0x180193541  lea     r8, stru_1801FC290
0x180193548  mov     edx, 7F0h
0x18019354d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180193554  mov     rax, [rcx+8]
0x180193558  mov     rcx, r8
0x18019355b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193560  test    eax, eax
0x180193562  jnz     short loc_180193574
0x180193564  lea     rcx, stru_1801F8A30
0x18019356b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180193572  jmp     short loc_18019357B
0x180193574  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019357b  cmp     [rcx+8], r15b
0x18019357f  jz      short loc_18019359F
0x180193581  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180193586  cmp     [rax+7CCh], ebx
0x18019358c  jz      short loc_18019359F
0x18019358e  mov     r9d, ebx; int
0x180193591  mov     r8d, r14d; int
0x180193594  mov     rdx, r12; char *
0x180193597  mov     rcx, rax; this
0x18019359a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18019359f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801935a6  jb      loc_180193BB2
0x1801935ac  mov     edx, 0EFh
0x1801935b1  jmp     loc_180193B94
0x1801935b6  mov     rax, [rsi]
0x1801935b9  lea     r14, [rdi+1C0h]
0x1801935c0  mov     r8, r14
0x1801935c3  lea     rdx, MF_TRANSFORM_CATEGORY_Attribute
0x1801935ca  mov     rcx, rsi
0x1801935cd  mov     rax, [rax+0C0h]
0x1801935d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801935d9  mov     ebx, eax
0x1801935db  test    eax, eax
0x1801935dd  jns     loc_18019366E
0x1801935e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801935ea  test    rcx, rcx
0x1801935ed  jnz     short loc_180193630
0x1801935ef  mov     rax, cs:stru_1801FC290.__vftable
0x1801935f6  lea     r8, stru_1801FC290
0x1801935fd  mov     edx, 7F0h
0x180193602  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180193609  mov     rcx, r8
0x18019360c  mov     rax, [rax+8]
0x180193610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193615  test    eax, eax
0x180193617  jnz     short loc_180193629
0x180193619  lea     rcx, stru_1801F8A30
0x180193620  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180193627  jmp     short loc_180193630
0x180193629  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180193630  cmp     [rcx+8], r15b
0x180193634  jz      short loc_180193657
0x180193636  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019363b  cmp     [rax+7CCh], ebx
0x180193641  jz      short loc_180193657
0x180193643  mov     r9d, ebx; int
0x180193646  mov     r8d, 73Ch; int
0x18019364c  mov     rdx, r12; char *
0x18019364f  mov     rcx, rax; this
0x180193652  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180193657  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019365e  jb      loc_180193BB2
0x180193664  mov     edx, 0F0h
0x180193669  jmp     loc_180193B94
0x18019366e  cmp     [rdi+21h], r15b
0x180193672  jz      loc_1801938CD
0x180193678  mov     rax, [r14]
0x18019367b  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x180193682  jnz     short loc_18019368F
0x180193684  mov     rax, [r14+8]
0x180193688  sub     rax, qword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data4
0x18019368f  test    rax, rax
0x180193692  jnz     loc_1801938CD
0x180193698  test    byte ptr [rdi+40h], 6
0x18019369c  jz      loc_1801938CD
0x1801936a2  lea     ebx, [rax+30h]
0x1801936a5  mov     [rbp+57h+result], r15d
0x1801936a9  lea     r14d, [rax+31h]
0x1801936ad  mov     [rbp+57h+var_88.hstr_], r15
0x1801936b1  mov     r9d, ebx; unsigned int
0x1801936b4  lea     rdx, aMicrosoftAvcen; "Microsoft.AVCEncoderVideoExtension_8wek"...
0x1801936bb  mov     r8d, r14d; unsigned int
0x1801936be  lea     rcx, [rbp+57h+var_88]; this
0x1801936c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801936c7  mov     rdx, [rbp+57h+var_88.hstr_]; string2
0x1801936cb  lea     r8, [rbp+57h+result]; result
0x1801936cf  mov     rcx, [rdi]; string1
0x1801936d2  call    cs:__imp_WindowsCompareStringOrdinal
0x1801936d8  test    eax, eax
0x1801936da  js      short loc_1801936E2
0x1801936dc  cmp     [rbp+57h+result], r15d
0x1801936e0  jz      short loc_180193758
0x1801936e2  mov     r9d, 2Ah ; '*'; unsigned int
0x1801936e8  mov     [rbp+57h+var_68.hstr_], r15
0x1801936ec  lea     rdx, aMicrosoftHevcv_1; "Microsoft.HEVCVideoExtension_8wekyb3d8b"...
0x1801936f3  lea     rcx, [rbp+57h+var_68]; this
0x1801936f7  lea     r8d, [r9+1]; unsigned int
0x1801936fb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180193700  mov     rdx, [rbp+57h+var_68.hstr_]; string2
0x180193704  lea     r8, [rbp+57h+result]; result
0x180193708  mov     rcx, [rdi]; string1
0x18019370b  call    cs:__imp_WindowsCompareStringOrdinal
0x180193711  test    eax, eax
0x180193713  js      short loc_18019371B
0x180193715  cmp     [rbp+57h+result], r15d
0x180193719  jz      short loc_180193758
0x18019371b  mov     r9d, ebx; unsigned int
0x18019371e  mov     [rbp+57h+var_48.hstr_], r15
0x180193722  mov     r8d, r14d; unsigned int
0x180193725  lea     rdx, aMicrosoftAv1en; "Microsoft.AV1EncoderVideoExtension_8wek"...
0x18019372c  lea     rcx, [rbp+57h+var_48]; this
0x180193730  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180193735  mov     rdx, [rbp+57h+var_48.hstr_]; string2
0x180193739  lea     r8, [rbp+57h+result]; result
0x18019373d  mov     rcx, [rdi]; string1
0x180193740  call    cs:__imp_WindowsCompareStringOrdinal
0x180193746  test    eax, eax
0x180193748  js      loc_1801938CD
0x18019374e  cmp     [rbp+57h+result], r15d
0x180193752  jnz     loc_1801938CD
0x180193758  mov     rax, [rsi]
0x18019375b  lea     r8, aVen1414; "VEN_1414"
0x180193762  lea     rdx, MFT_ENUM_HARDWARE_VENDOR_ID_Attribute
0x180193769  mov     rcx, rsi
0x18019376c  mov     rax, [rax+0C8h]
0x180193773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193778  mov     ebx, eax
0x18019377a  test    eax, eax
0x18019377c  jns     loc_18019380D
0x180193782  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180193789  test    rcx, rcx
0x18019378c  jnz     short loc_1801937CF
0x18019378e  mov     rax, cs:stru_1801FC290.__vftable
0x180193795  lea     r8, stru_1801FC290
0x18019379c  mov     edx, 7F0h
0x1801937a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1801937a8  mov     rcx, r8
0x1801937ab  mov     rax, [rax+8]
0x1801937af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801937b4  test    eax, eax
0x1801937b6  jnz     short loc_1801937C8
0x1801937b8  lea     rcx, stru_1801F8A30
0x1801937bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801937c6  jmp     short loc_1801937CF
0x1801937c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801937cf  cmp     [rcx+8], r15b
0x1801937d3  jz      short loc_1801937F6
0x1801937d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801937da  cmp     [rax+7CCh], ebx
0x1801937e0  jz      short loc_1801937F6
0x1801937e2  mov     r9d, ebx; int
0x1801937e5  mov     r8d, 749h; int
0x1801937eb  mov     rdx, r12; char *
0x1801937ee  mov     rcx, rax; this
0x1801937f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801937f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801937fd  jb      loc_180193BB2
0x180193803  mov     edx, 0F1h
0x180193808  jmp     loc_180193B94
0x18019380d  mov     rax, [rsi]
0x180193810  xor     edx, edx; length
0x180193812  mov     rcx, [rdi+18h]; string
0x180193816  mov     rbx, [rax+0C8h]
0x18019381d  call    cs:__imp_WindowsGetStringRawBuffer
0x180193823  lea     rdx, MFT_ENUM_HARDWARE_URL_Attribute
0x18019382a  mov     rcx, rsi
0x18019382d  mov     r8, rax
0x180193830  mov     rax, rbx
0x180193833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193838  mov     ebx, eax
0x18019383a  test    eax, eax
0x18019383c  jns     loc_1801938CD
0x180193842  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180193849  test    rcx, rcx
0x18019384c  jnz     short loc_18019388F
0x18019384e  mov     rax, cs:stru_1801FC290.__vftable
0x180193855  lea     r8, stru_1801FC290
0x18019385c  mov     edx, 7F0h
0x180193861  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180193868  mov     rcx, r8
0x18019386b  mov     rax, [rax+8]
0x18019386f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193874  test    eax, eax
0x180193876  jnz     short loc_180193888
0x180193878  lea     rcx, stru_1801F8A30
0x18019387f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180193886  jmp     short loc_18019388F
0x180193888  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019388f  cmp     [rcx+8], r15b
0x180193893  jz      short loc_1801938B6
0x180193895  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019389a  cmp     [rax+7CCh], ebx
0x1801938a0  jz      short loc_1801938B6
0x1801938a2  mov     r9d, ebx; int
0x1801938a5  mov     r8d, 74Ah; int
0x1801938ab  mov     rdx, r12; char *
0x1801938ae  mov     rcx, rax; this
0x1801938b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801938b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801938bd  jb      loc_180193BB2
0x1801938c3  mov     edx, 0F2h
0x1801938c8  jmp     loc_180193B94
0x1801938cd  lea     r14, [rdi+1D0h]
0x1801938d4  mov     rcx, r14
0x1801938d7  lea     rdx, [rdi+48h]
0x1801938db  lea     r9, [rbp+57h+var_A0]
0x1801938df  lea     r8, [rbp+57h+var_A4]
0x1801938e3  call    ?AllocTypesAndPopulate@@YAJAEBU_GUID@@AEBV?$CTDynArray@U_GUID@@$0BE@@@PEAIPEAPEAU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@@Z; AllocTypesAndPopulate(_GUID const &,CTDynArray<_GUID,20> const &,uint *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 * *)
0x1801938e8  mov     ebx, eax
0x1801938ea  test    eax, eax
0x1801938ec  jns     loc_18019397D
0x1801938f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801938f9  test    rcx, rcx
0x1801938fc  jnz     short loc_18019393F
0x1801938fe  mov     rax, cs:stru_1801FC290.__vftable
0x180193905  lea     r8, stru_1801FC290
0x18019390c  mov     edx, 7F0h
0x180193911  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180193918  mov     rcx, r8
0x18019391b  mov     rax, [rax+8]
0x18019391f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193924  test    eax, eax
0x180193926  jnz     short loc_180193938
0x180193928  lea     rcx, stru_1801F8A30
0x18019392f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180193936  jmp     short loc_18019393F
0x180193938  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18019393f  cmp     [rcx+8], r15b
0x180193943  jz      short loc_180193966
0x180193945  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18019394a  cmp     [rax+7CCh], ebx
0x180193950  jz      short loc_180193966
0x180193952  mov     r9d, ebx; int
0x180193955  mov     r8d, 74Dh; int
0x18019395b  mov     rdx, r12; char *
0x18019395e  mov     rcx, rax; this
0x180193961  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180193966  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18019396d  jb      loc_180193BB2
0x180193973  mov     edx, 0F3h
0x180193978  jmp     loc_180193B94
0x18019397d  mov     rax, [rsi]
0x180193980  lea     rdx, MFT_INPUT_TYPES_Attributes
0x180193987  mov     r9d, [rbp+57h+var_A4]
0x18019398b  mov     rcx, rsi
0x18019398e  mov     r8, [rbp+57h+var_A0]
0x180193992  shl     r9d, 5
0x180193996  mov     rax, [rax+0D0h]
0x18019399d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801939a2  mov     ebx, eax
0x1801939a4  test    eax, eax
0x1801939a6  jns     loc_180193A37
0x1801939ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801939b3  test    rcx, rcx
0x1801939b6  jnz     short loc_1801939F9
0x1801939b8  mov     rax, cs:stru_1801FC290.__vftable
0x1801939bf  lea     r8, stru_1801FC290
0x1801939c6  mov     edx, 7F0h
0x1801939cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1801939d2  mov     rcx, r8
  ... truncated ...
```
