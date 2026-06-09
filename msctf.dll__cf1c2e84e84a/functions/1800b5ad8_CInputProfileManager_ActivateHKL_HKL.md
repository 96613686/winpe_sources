# CInputProfileManager::ActivateHKL(HKL__ *)

- ea: `0x1800b5ad8`
- end: `0x1800b5c67`
- name: `?ActivateHKL@CInputProfileManager@@AEAAHPEAUHKL__@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CInputProfileManager *__hidden this, HKL)`
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b15c`
- `0x180011e90`
- `0x18007f4e8`
- `0x1800b5c70`
- `0x1800b5f58`
- `0x1800b6298`
- `0x1800b7e80`

## callees

- `0x180001fb4`
- `0x18000bc34`
- `0x180011000`
- `0x18001e2c0`
- `0x180051194`
- `0x18005dbdc`
- `0x180080430`
- `0x1800b417c`
- `0x1800b5ad8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b5b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b5b75`
- `USER32!ActivateKeyboardLayout` at `0x1800b5be2`
- `USER32!ActivateKeyboardLayout` at `0x1800b5be2`
- `USER32!GetKeyboardLayout` at `0x1800b5b0c`
- `USER32!GetKeyboardLayout` at `0x1800b5c02`
- `USER32!GetKeyboardLayout` at `0x1800b5b0c`
- `USER32!GetKeyboardLayout` at `0x1800b5c02`
- `USER32!PostThreadMessageW` at `0x1800b5b86`
- `USER32!PostThreadMessageW` at `0x1800b5b86`

## pseudocode

```c
__int64 __fastcall CInputProfileManager::ActivateHKL(CInputProfileManager *this, HKL a2)
{
  unsigned int v4; // esi
  unsigned int v6; // ebp
  int v7; // esi
  char AppCompatFlags; // al
  UINT v9; // ebx
  DWORD CurrentThreadId; // eax
  int v11; // r8d
  int v12; // r9d
  HKL KeyboardLayout; // rdx
  CInputLanguage *v14; // rsi
  HKL ProfileHKL; // r14
  struct CInputProfile *ActiveProfile; // rax
  int v17; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(*((_QWORD *)this + 9) + 192LL);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl)
    && GetKeyboardLayout(0) == a2 )
  {
    return 0;
  }
  v6 = 0;
  v7 = (v4 >> 3) & 1;
  if ( !dword_180140FC8 )
  {
    AppCompatFlags = TF_GetAppCompatFlags();
    dword_180140FC8 = 1;
    if ( (AppCompatFlags & 2) != 0 )
      v7 = 1;
  }
  if ( (unsigned int)CanActivateKeyboardLayout(a2) )
  {
    if ( v7 )
    {
      *(_QWORD *)(*((_QWORD *)this + 9) + 152LL) = a2;
      v9 = g_msgPrivate;
      CurrentThreadId = GetCurrentThreadId();
      PostThreadMessageW(CurrentThreadId, v9, 0x1Cu, 0);
    }
    else
    {
      if ( (unsigned int)dword_18013D0D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D0D8, 34078720) )
      {
        v17 = (int)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18013D0D8,
          (unsigned int)byte_180128231,
          v11,
          v12,
          (__int64)&v17);
      }
      *(_QWORD *)(*((_QWORD *)this + 9) + 152LL) = 0;
      if ( !ActivateKeyboardLayout(a2, 0) )
        return v6;
      v6 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
      {
        KeyboardLayout = GetKeyboardLayout(0);
      }
      else
      {
        v14 = (CInputLanguage *)*((_QWORD *)this + 6);
        ProfileHKL = 0;
        if ( v14 )
        {
          ActiveProfile = CInputLanguage::GetActiveProfile(
                            *((CInputLanguage **)this + 6),
                            &GUID_NULL,
                            &GUID_TFCAT_TIP_KEYBOARD);
          if ( ActiveProfile )
            ProfileHKL = CInputLanguage::GetProfileHKL(v14, ActiveProfile);
        }
        if ( ProfileHKL == a2 )
          return v6;
        KeyboardLayout = a2;
      }
      CInputProfileManager::OnActiveKeyboardLayoutChange(this, KeyboardLayout);
    }
  }
  else
  {
    *(_QWORD *)(*((_QWORD *)this + 9) + 152LL) = a2;
  }
  return v6;
}

```

## disassembly

```asm
0x1800b5ad8  mov     [rsp+arg_8], rbx
0x1800b5add  mov     [rsp+arg_10], rbp
0x1800b5ae2  push    rsi
0x1800b5ae3  push    rdi
0x1800b5ae4  push    r14
0x1800b5ae6  sub     rsp, 30h
0x1800b5aea  mov     rax, [rcx+48h]
0x1800b5aee  mov     rbx, rdx
0x1800b5af1  mov     rdi, rcx
0x1800b5af4  mov     esi, [rax+0C0h]
0x1800b5afa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x1800b5b01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x1800b5b06  test    al, al
0x1800b5b08  jz      short loc_1800B5B1E
0x1800b5b0a  xor     ecx, ecx; idThread
0x1800b5b0c  call    cs:__imp_GetKeyboardLayout
0x1800b5b12  cmp     rax, rbx
0x1800b5b15  jnz     short loc_1800B5B1E
0x1800b5b17  xor     eax, eax
0x1800b5b19  jmp     loc_1800B5C54
0x1800b5b1e  xor     ebp, ebp
0x1800b5b20  shr     esi, 3
0x1800b5b23  lea     r14d, [rbp+1]
0x1800b5b27  and     esi, r14d
0x1800b5b2a  cmp     cs:dword_180140FC8, ebp
0x1800b5b30  jnz     short loc_1800B5B44
0x1800b5b32  call    TF_GetAppCompatFlags
0x1800b5b37  test    al, 2
0x1800b5b39  mov     cs:dword_180140FC8, r14d
0x1800b5b40  cmovnz  esi, r14d
0x1800b5b44  mov     rcx, rbx; HKL
0x1800b5b47  call    ?CanActivateKeyboardLayout@@YAHPEAUHKL__@@@Z; CanActivateKeyboardLayout(HKL__ *)
0x1800b5b4c  test    eax, eax
0x1800b5b4e  jnz     short loc_1800B5B60
0x1800b5b50  mov     rax, [rdi+48h]
0x1800b5b54  mov     [rax+98h], rbx
0x1800b5b5b  jmp     loc_1800B5C52
0x1800b5b60  test    esi, esi
0x1800b5b62  jz      short loc_1800B5B91
0x1800b5b64  mov     rax, [rdi+48h]
0x1800b5b68  mov     [rax+98h], rbx
0x1800b5b6f  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x1800b5b75  call    cs:__imp_GetCurrentThreadId
0x1800b5b7b  xor     r9d, r9d; lParam
0x1800b5b7e  mov     edx, ebx; Msg
0x1800b5b80  mov     ecx, eax; idThread
0x1800b5b82  lea     r8d, [r9+1Ch]; wParam
0x1800b5b86  call    cs:__imp_PostThreadMessageW
0x1800b5b8c  jmp     loc_1800B5C52
0x1800b5b91  mov     eax, cs:dword_18013D0D8
0x1800b5b97  cmp     eax, 5
0x1800b5b9a  jbe     short loc_1800B5BD2
0x1800b5b9c  mov     edx, 2080000h
0x1800b5ba1  lea     rcx, dword_18013D0D8
0x1800b5ba8  call    _tlgKeywordOn
0x1800b5bad  test    al, al
0x1800b5baf  jz      short loc_1800B5BD2
0x1800b5bb1  lea     rax, [rsp+48h+arg_0]
0x1800b5bb6  mov     [rsp+48h+arg_0], ebx
0x1800b5bba  lea     rdx, byte_180128231
0x1800b5bc1  mov     [rsp+48h+var_28], rax
0x1800b5bc6  lea     rcx, dword_18013D0D8
0x1800b5bcd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b5bd2  mov     rax, [rdi+48h]
0x1800b5bd6  xor     edx, edx; Flags
0x1800b5bd8  mov     rcx, rbx; hkl
0x1800b5bdb  mov     [rax+98h], rbp
0x1800b5be2  call    cs:__imp_ActivateKeyboardLayout
0x1800b5be8  test    rax, rax
0x1800b5beb  jz      short loc_1800B5C52
0x1800b5bed  mov     ebp, r14d
0x1800b5bf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x1800b5bf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x1800b5bfc  test    al, al
0x1800b5bfe  jz      short loc_1800B5C0D
0x1800b5c00  xor     ecx, ecx; idThread
0x1800b5c02  call    cs:__imp_GetKeyboardLayout
0x1800b5c08  mov     rdx, rax
0x1800b5c0b  jmp     short loc_1800B5C4A
0x1800b5c0d  mov     rsi, [rdi+30h]
0x1800b5c11  xor     r14d, r14d
0x1800b5c14  test    rsi, rsi
0x1800b5c17  jz      short loc_1800B5C42
0x1800b5c19  lea     r8, GUID_TFCAT_TIP_KEYBOARD; struct _GUID *
0x1800b5c20  mov     rcx, rsi; this
0x1800b5c23  lea     rdx, GUID_NULL; struct _GUID *
0x1800b5c2a  call    ?GetActiveProfile@CInputLanguage@@QEAAPEAUCInputProfile@@AEBU_GUID@@0@Z; CInputLanguage::GetActiveProfile(_GUID const &,_GUID const &)
0x1800b5c2f  test    rax, rax
0x1800b5c32  jz      short loc_1800B5C42
0x1800b5c34  mov     rdx, rax; struct CInputProfile *
0x1800b5c37  mov     rcx, rsi; this
0x1800b5c3a  call    ?GetProfileHKL@CInputLanguage@@QEAAPEAUHKL__@@PEAUCInputProfile@@@Z; CInputLanguage::GetProfileHKL(CInputProfile *)
0x1800b5c3f  mov     r14, rax
0x1800b5c42  cmp     r14, rbx
0x1800b5c45  jz      short loc_1800B5C52
0x1800b5c47  mov     rdx, rbx; HKL
0x1800b5c4a  mov     rcx, rdi; this
0x1800b5c4d  call    ?OnActiveKeyboardLayoutChange@CInputProfileManager@@QEAAXPEAUHKL__@@@Z; CInputProfileManager::OnActiveKeyboardLayoutChange(HKL__ *)
0x1800b5c52  mov     eax, ebp
0x1800b5c54  mov     rbx, [rsp+48h+arg_8]
0x1800b5c59  mov     rbp, [rsp+48h+arg_10]
0x1800b5c5e  add     rsp, 30h
0x1800b5c62  pop     r14
0x1800b5c64  pop     rdi
0x1800b5c65  pop     rsi
0x1800b5c66  retn
```
