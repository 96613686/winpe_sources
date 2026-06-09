# Windows::UI::Composition::ImplicitAnimationCollection::TryPlayAnimation(Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::AnimationValueData const *,bool *)

- ea: `0x180074ab8`
- end: `0x180074dc9`
- name: `?TryPlayAnimation@ImplicitAnimationCollection@Composition@UI@Windows@@AEAAJPEAVCompositionObject@234@PEBUAnimationValueData@234@PEA_N@Z`
- size: `785`
- prototype: `int(Windows::UI::Composition::ImplicitAnimationCollection *__hidden this, struct Windows::UI::Composition::CompositionObject *, const struct Windows::UI::Composition::AnimationValueData *, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180074a10`

## callees

- `0x1800093f4`
- `0x18000bc00`
- `0x18000f810`
- `0x18001358c`
- `0x180048980`
- `0x180072668`
- `0x180073388`
- `0x180074480`
- `0x1800744bc`
- `0x180074ab8`
- `0x180074dd0`
- `0x1800755d8`
- `0x18013b0b8`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074ce1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074ce1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017f493`

## string_xrefs

- `0x180074c85`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtimplicitanimationcollection.cpp`
- `0x180074d44`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtimplicitanimationcollection.cpp`
- `0x180074d98`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtimplicitanimationcollection.cpp`
- `0x18017f476`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtimplicitanimationcollection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ImplicitAnimationCollection::TryPlayAnimation(
        Windows::UI::Composition::ImplicitAnimationCollection *this,
        struct Windows::UI::Composition::CompositionObject *a2,
        const struct Windows::UI::Composition::AnimationValueData *a3,
        bool *a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  struct IUnknown *v10; // rcx
  struct Microsoft::WRL2::ContextSession *v12; // rcx
  int v13; // eax
  Microsoft::WRL2::NestableRuntimeClass *v14; // rbx
  struct Microsoft::WRL2::ContextSession *v15; // rcx
  int v16; // eax
  Microsoft::WRL2::NestableRuntimeClass *v17; // rdi
  HSTRING v18; // r8
  int v19; // esi
  __int64 v20; // rdx
  struct IUnknown *v21; // rcx
  HSTRING v22; // rcx
  int v23; // eax
  unsigned int v24; // edi
  struct IUnknown *v25; // rcx
  struct IUnknown *v26; // rcx
  int v27; // [rsp+20h] [rbp-20h]
  int v28; // [rsp+20h] [rbp-20h]
  int v29; // [rsp+20h] [rbp-20h]
  char *v30; // [rsp+28h] [rbp-18h]
  _QWORD v31[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  Microsoft::WRL2::NestableRuntimeClass *v33; // [rsp+80h] [rbp+40h] BYREF
  struct IUnknown *v34; // [rsp+90h] [rbp+50h] BYREF
  HSTRING string; // [rsp+98h] [rbp+58h] BYREF

  v4 = *((_QWORD *)a3 + 3);
  *a4 = 0;
  v6 = *((_QWORD *)this + 22);
  v34 = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v34);
  if ( (int)Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Lookup(
              v6,
              v4,
              &v34) < 0
    || !v34 )
  {
LABEL_2:
    v10 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
    }
    return 0;
  }
  if ( *((_DWORD *)a3 + 24) != 18
    && *((_DWORD *)a3 + 24) != 35
    && *((_DWORD *)a3 + 24) != 52
    && *((_DWORD *)a3 + 24) != 69
    && (unsigned int)(*((_DWORD *)a3 + 24) - 70) > 1 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtimplicitanimationcollection.cpp",
      (const char *)0x80070057LL,
      (int)"Unsupported property type for implicit animations.",
      v30);
    v26 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
    }
    return 2147942487LL;
  }
  if ( !*((_BYTE *)a3 + 100) )
  {
    *a4 = 1;
    goto LABEL_2;
  }
  v31[0] = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v31);
  v12 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  v33 = 0;
  v13 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
          v12,
          v34,
          (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimationGroup::s_InterfaceType,
          &v33);
  v14 = v33;
  v31[0] = v33;
  if ( v13 >= 0 && v33 )
  {
    v23 = Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(
            (_DWORD)v33,
            (_DWORD)a2,
            (_DWORD)a3,
            2,
            (__int64)a4,
            0);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtimplicitanimationcollection.cpp",
        (const char *)(unsigned int)v23,
        v29);
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v14);
      v25 = v34;
      if ( v34 )
      {
        v34 = 0;
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
      }
      return v24;
    }
    goto LABEL_28;
  }
  v33 = 0;
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v33);
  v15 = (struct Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  v33 = 0;
  v16 = Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(
          v15,
          v34,
          (const struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *)&Windows::UI::Composition::CompositionAnimation::s_InterfaceType,
          &v33);
  v17 = v33;
  if ( v16 < 0 )
    goto LABEL_26;
  if ( !v33 )
  {
LABEL_28:
    if ( v14 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v14);
    goto LABEL_2;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  Windows::UI::Composition::CompositionAnimation::GetTarget(v17, &string);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                        (Microsoft::WRL::Wrappers::Details *)string,
                        0,
                        v18) )
  {
    Windows::UI::Composition::OriginateInvalidArgument(11);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtimplicitanimationcollection.cpp",
      (const char *)0x80070057LL,
      v27);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v33);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(v31);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v34);
    return 2147942487LL;
  }
  LOBYTE(v33) = 0;
  v19 = Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(
          (Windows::UI::Composition::AnimationHelper *)string,
          (HSTRING)a2,
          v17,
          a3,
          (const struct Windows::UI::Composition::AnimationValueData *)&v33,
          (bool *)v30);
  if ( v19 < 0 )
  {
    v20 = 193;
    goto LABEL_20;
  }
  *((_DWORD *)v17 + 78) = 2;
  v28 = 0;
  v19 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::CompositionObject *, HSTRING, Microsoft::WRL2::NestableRuntimeClass *, _QWORD))(*(_QWORD *)a2 + 152LL))(
          a2,
          string,
          v17,
          0);
  if ( v19 >= 0 )
  {
    v22 = string;
    *a4 = (char)v33;
    WindowsDeleteString(v22);
LABEL_26:
    if ( v17 )
      Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v17);
    goto LABEL_28;
  }
  v20 = 207;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtimplicitanimationcollection.cpp",
    (const char *)(unsigned int)v19,
    v28);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v17);
  if ( v14 )
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v14);
  v21 = v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180074ab8  mov     [rsp-38h+arg_8], rbx
0x180074abd  push    rbp
0x180074abe  push    rsi
0x180074abf  push    rdi
0x180074ac0  push    r12
0x180074ac2  push    r13
0x180074ac4  push    r14
0x180074ac6  push    r15
0x180074ac8  mov     rbp, rsp
0x180074acb  sub     rsp, 40h
0x180074acf  mov     rdi, [r8+18h]
0x180074ad3  xor     r13d, r13d
0x180074ad6  mov     [r9], r13b
0x180074ad9  mov     r15, rcx
0x180074adc  mov     rbx, [rcx+0B0h]
0x180074ae3  mov     r14, r9
0x180074ae6  lea     rcx, [rbp+arg_10]
0x180074aea  mov     [rbp+arg_10], r13
0x180074aee  mov     rsi, r8
0x180074af1  mov     r12, rdx
0x180074af4  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180074af9  lea     r8, [rbp+arg_10]
0x180074afd  mov     rdx, rdi
0x180074b00  mov     rcx, rbx
0x180074b03  call    ?Lookup@?$HashMap@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUICompositionAnimationBase@Composition@UI@5@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Lookup(HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase * *)
0x180074b08  test    eax, eax
0x180074b0a  jns     short loc_180074B3F
0x180074b0c  mov     rcx, [rbp+arg_10]
0x180074b10  test    rcx, rcx
0x180074b13  jz      short loc_180074B25
0x180074b15  mov     [rbp+arg_10], r13
0x180074b19  mov     rax, [rcx]
0x180074b1c  mov     rax, [rax+10h]
0x180074b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b25  xor     eax, eax
0x180074b27  mov     rbx, [rsp+40h+arg_8]
0x180074b2f  add     rsp, 40h
0x180074b33  pop     r15
0x180074b35  pop     r14
0x180074b37  pop     r13
0x180074b39  pop     r12
0x180074b3b  pop     rdi
0x180074b3c  pop     rsi
0x180074b3d  pop     rbp
0x180074b3e  retn
0x180074b3f  cmp     [rbp+arg_10], r13
0x180074b43  jz      short loc_180074B0C
0x180074b45  mov     ecx, [rsi+60h]
0x180074b48  sub     ecx, 12h
0x180074b4b  jz      short loc_180074B6A
0x180074b4d  sub     ecx, 11h
0x180074b50  jz      short loc_180074B6A
0x180074b52  sub     ecx, 11h
0x180074b55  jz      short loc_180074B6A
0x180074b57  sub     ecx, 11h
0x180074b5a  jz      short loc_180074B6A
0x180074b5c  sub     ecx, 1
0x180074b5f  jz      short loc_180074B6A
0x180074b61  cmp     ecx, 1
0x180074b64  jnz     loc_180074D80
0x180074b6a  cmp     [rsi+64h], r13b
0x180074b6e  jz      loc_180074D0A
0x180074b74  lea     rcx, [rbp+var_10]; void *
0x180074b78  mov     [rbp+var_10], r13
0x180074b7c  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180074b81  mov     rdx, [rbp+arg_10]; struct IUnknown *
0x180074b85  lea     r9, [rbp+arg_0]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180074b89  mov     rcx, [r15+18h]; struct Microsoft::WRL2::ContextSession *
0x180074b8d  lea     r8, ?s_InterfaceType@CompositionAnimationGroup@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180074b94  mov     [rbp+arg_0], r13
0x180074b98  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180074b9d  mov     rbx, [rbp+arg_0]
0x180074ba1  mov     [rbp+var_10], rbx
0x180074ba5  test    eax, eax
0x180074ba7  jns     loc_180074D13
0x180074bad  lea     rcx, [rbp+arg_0]; void *
0x180074bb1  mov     [rbp+arg_0], r13
0x180074bb5  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180074bba  mov     rdx, [rbp+arg_10]; struct IUnknown *
0x180074bbe  lea     r9, [rbp+arg_0]; struct Microsoft::WRL2::ContextRuntimeClass **
0x180074bc2  mov     rcx, [r15+18h]; struct Microsoft::WRL2::ContextSession *
0x180074bc6  lea     r8, ?s_InterfaceType@CompositionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; struct Microsoft::WRL2::NestableRuntimeClass::InterfaceType *
0x180074bcd  mov     [rbp+arg_0], r13
0x180074bd1  call    ?ValidateInterface@ContextRuntimeClass@WRL2@Microsoft@@KAJPEAVContextSession@23@PEAUIUnknown@@PEBUInterfaceType@NestableRuntimeClass@23@PEAPEAV123@@Z; Microsoft::WRL2::ContextRuntimeClass::ValidateInterface(Microsoft::WRL2::ContextSession *,IUnknown *,Microsoft::WRL2::NestableRuntimeClass::InterfaceType const *,Microsoft::WRL2::ContextRuntimeClass * *)
0x180074bd6  mov     rdi, [rbp+arg_0]
0x180074bda  mov     [rbp+arg_0], rdi
0x180074bde  test    eax, eax
0x180074be0  js      loc_180074CE7
0x180074be6  test    rdi, rdi
0x180074be9  jz      loc_180074CF4
0x180074bef  xor     ecx, ecx; string
0x180074bf1  mov     [rbp+string], r13
0x180074bf5  call    cs:__imp_WindowsDeleteString
0x180074bfb  lea     rdx, [rbp+string]; HSTRING *
0x180074bff  mov     [rbp+string], r13
0x180074c03  mov     rcx, rdi; this
0x180074c06  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x180074c0b  mov     rcx, [rbp+string]; this
0x180074c0f  xor     edx, edx; HSTRING
0x180074c11  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180074c16  test    eax, eax
0x180074c18  jz      loc_18017F468
0x180074c1e  mov     rcx, [rbp+string]; this
0x180074c22  lea     rax, [rbp+arg_0]
0x180074c26  mov     r9, rsi; struct Windows::UI::Composition::CompositionAnimation *
0x180074c29  mov     [rsp+40h+var_20], rax; int
0x180074c2e  mov     r8, rdi; struct Windows::UI::Composition::CompositionObject *
0x180074c31  mov     byte ptr [rbp+arg_0], r13b
0x180074c35  mov     rdx, r12; HSTRING
0x180074c38  call    ?SetFinalValueParameter@AnimationHelper@Composition@UI@Windows@@YAJPEAUHSTRING__@@PEAVCompositionObject@234@PEAVCompositionAnimation@234@PEBUAnimationValueData@234@PEA_N@Z; Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(HSTRING__ *,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::AnimationValueData const *,bool *)
0x180074c3d  mov     esi, eax
0x180074c3f  test    eax, eax
0x180074c41  js      short loc_180074C7C
0x180074c43  mov     dword ptr [rdi+138h], 2
0x180074c4d  xor     r9d, r9d
0x180074c50  mov     rax, [r12]
0x180074c54  mov     r8, rdi
0x180074c57  mov     rdx, [rbp+string]
0x180074c5b  mov     rcx, r12
0x180074c5e  mov     [rsp+40h+var_20], r13
0x180074c63  mov     rax, [rax+98h]
0x180074c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c6f  mov     esi, eax
0x180074c71  test    eax, eax
0x180074c73  jns     short loc_180074CD7
0x180074c75  mov     edx, 0CFh
0x180074c7a  jmp     short loc_180074C81
0x180074c7c  mov     edx, 0C1h; void *
0x180074c81  mov     rcx, [rbp+38h]; this
0x180074c85  lea     r8, aOnecoreuapWind_144; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180074c8c  mov     r9d, esi; char *
0x180074c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c94  mov     rcx, [rbp+string]; string
0x180074c98  call    cs:__imp_WindowsDeleteString
0x180074c9e  mov     rcx, rdi; this
0x180074ca1  mov     [rbp+string], r13
0x180074ca5  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180074caa  test    rbx, rbx
0x180074cad  jz      short loc_180074CB7
0x180074caf  mov     rcx, rbx; this
0x180074cb2  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180074cb7  mov     rcx, [rbp+arg_10]
0x180074cbb  test    rcx, rcx
0x180074cbe  jz      short loc_180074CD0
0x180074cc0  mov     [rbp+arg_10], r13
0x180074cc4  mov     rax, [rcx]
0x180074cc7  mov     rax, [rax+10h]
0x180074ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cd0  mov     eax, esi
0x180074cd2  jmp     loc_180074B27
0x180074cd7  mov     al, byte ptr [rbp+arg_0]
0x180074cda  mov     rcx, [rbp+string]; string
0x180074cde  mov     [r14], al
0x180074ce1  call    cs:__imp_WindowsDeleteString
0x180074ce7  test    rdi, rdi
0x180074cea  jz      short loc_180074CF4
0x180074cec  mov     rcx, rdi; this
0x180074cef  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180074cf4  test    rbx, rbx
0x180074cf7  jz      loc_180074B0C
0x180074cfd  mov     rcx, rbx; this
0x180074d00  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180074d05  jmp     loc_180074B0C
0x180074d0a  mov     byte ptr [r14], 1
0x180074d0e  jmp     loc_180074B0C
0x180074d13  test    rbx, rbx
0x180074d16  jz      loc_180074BAD
0x180074d1c  mov     [rsp+40h+var_18], r13
0x180074d21  mov     r9d, 2
0x180074d27  mov     r8, rsi
0x180074d2a  mov     [rsp+40h+var_20], r14; int
0x180074d2f  mov     rdx, r12
0x180074d32  mov     rcx, rbx
0x180074d35  call    ?PlayAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@PEBUAnimationValueData@234@W4AnimationValueSynchronizationBehavior@234@PEA_NPEAV?$vector@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@V?$allocator@PEAVCompositionPropertyAnimator@Composition@UI@Windows@@@std@@@std@@@Z; Windows::UI::Composition::CompositionAnimationGroup::PlayAnimations(Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::AnimationValueData const *,Windows::UI::Composition::AnimationValueSynchronizationBehavior,bool *,std::vector<Windows::UI::Composition::CompositionPropertyAnimator *> *)
0x180074d3a  mov     edi, eax
0x180074d3c  test    eax, eax
0x180074d3e  jns     short loc_180074CF4
0x180074d40  mov     rcx, [rbp+38h]; this
0x180074d44  lea     r8, aOnecoreuapWind_144; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180074d4b  mov     r9d, eax; char *
0x180074d4e  mov     edx, 99h; void *
0x180074d53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074d58  mov     rcx, rbx; this
0x180074d5b  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180074d60  mov     rcx, [rbp+arg_10]
0x180074d64  test    rcx, rcx
0x180074d67  jz      short loc_180074D79
0x180074d69  mov     [rbp+arg_10], r13
0x180074d6d  mov     rax, [rcx]
0x180074d70  mov     rax, [rax+10h]
0x180074d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074d79  mov     eax, edi
0x180074d7b  jmp     loc_180074B27
0x180074d80  mov     rcx, [rbp+38h]; this
0x180074d84  lea     rax, aUnsupportedPro; "Unsupported property type for implicit "...
0x180074d8b  mov     ebx, 80070057h
0x180074d90  mov     [rsp+40h+var_20], rax; int
0x180074d95  mov     r9d, ebx; char *
0x180074d98  lea     r8, aOnecoreuapWind_144; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180074d9f  mov     edx, 7Eh ; '~'; void *
0x180074da4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180074da9  mov     rcx, [rbp+arg_10]
0x180074dad  test    rcx, rcx
0x180074db0  jz      short loc_180074DC2
0x180074db2  mov     [rbp+arg_10], r13
0x180074db6  mov     rdx, [rcx]
0x180074db9  mov     rax, [rdx+10h]
0x180074dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074dc2  mov     eax, ebx
0x180074dc4  jmp     loc_180074B27
0x18017f468  mov     ecx, 0Bh
0x18017f46d  call    ?OriginateInvalidArgument@Composition@UI@Windows@@YAXW4ApiError@123@@Z; Windows::UI::Composition::OriginateInvalidArgument(Windows::UI::Composition::ApiError)
0x18017f472  mov     rcx, [rbp+38h]; this
0x18017f476  lea     r8, aOnecoreuapWind_144; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18017f47d  mov     ebx, 80070057h
0x18017f482  mov     edx, 0B8h; void *
0x18017f487  mov     r9d, ebx; char *
0x18017f48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017f48f  mov     rcx, [rbp+string]; string
0x18017f493  call    cs:__imp_WindowsDeleteString
0x18017f499  lea     rcx, [rbp+arg_0]; void *
0x18017f49d  mov     [rbp+string], r13
0x18017f4a1  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18017f4a6  lea     rcx, [rbp+var_10]; void *
0x18017f4aa  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18017f4af  lea     rcx, [rbp+arg_10]
0x18017f4b3  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18017f4b8  nop
0x18017f4b9  jmp     loc_180074DC2
```
