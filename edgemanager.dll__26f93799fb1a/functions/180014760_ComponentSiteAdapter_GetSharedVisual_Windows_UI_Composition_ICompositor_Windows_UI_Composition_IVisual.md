# ComponentSiteAdapter::GetSharedVisual(Windows::UI::Composition::ICompositor *,Windows::UI::Composition::IVisual * *)

- ea: `0x180014760`
- end: `0x180014b6b`
- name: `?GetSharedVisual@ComponentSiteAdapter@@UEAAJPEAUICompositor@Composition@UI@Windows@@PEAPEAUIVisual@345@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(ComponentSiteAdapter *__hidden this, struct Windows::UI::Composition::ICompositor *, struct Windows::UI::Composition::IVisual **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x180014760`
- `0x1800154cc`
- `0x180018b30`
- `0x180036418`
- `0x180036984`
- `0x180085010`

## import_xrefs

- `dcomp!__imp_DCompositionCreateTargetForHandle` at `0x180014999`
- `dcomp!__imp_DCompositionCreateTargetForHandle` at `0x180014999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ad2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ad2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001478f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001478f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a51`

## string_xrefs

- `0x1800147be`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x180014853`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x180014902`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x180014963`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x1800149ac`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x180014a9c`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`
- `0x180014b2a`: `onecoreuap\inetcore\edgemanager\webview\corewebview\componentsiteadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ComponentSiteAdapter::GetSharedVisual(
        ComponentSiteAdapter *this,
        __int64 (__fastcall ***a2)(struct Windows::UI::Composition::ICompositor *, GUID *, __int64 *),
        struct Windows::UI::Composition::IVisual **a3)
{
  struct Windows::UI::Composition::IVisual **v3; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  const char *v7; // r9
  char v8; // r15
  char v9; // al
  __int64 (__fastcall *v10)(struct Windows::UI::Composition::ICompositor *, GUID *, __int64 *); // rbx
  int v11; // eax
  int v12; // r13d
  __int64 (__fastcall *v13)(struct Windows::UI::Composition::ICompositor *, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rbx
  __int64 *v17; // r12
  __int64 *v18; // r15
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, GUID *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // rbx
  int v24; // eax
  int TargetForHandle; // eax
  __int64 v26; // rbx
  __int64 v27; // rbx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v32; // [rsp+20h] [rbp-20h] BYREF
  __int64 v33; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v34[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  __int64 v36; // [rsp+80h] [rbp+40h] BYREF
  struct Windows::UI::Composition::IVisual **v37; // [rsp+90h] [rbp+50h]
  __int64 v38; // [rsp+98h] [rbp+58h] BYREF

  v37 = a3;
  v3 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( *((_BYTE *)this + 228) )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( *((_DWORD *)this + 56) == 1 )
    {
      v9 = 1;
      goto LABEL_6;
    }
  }
  v9 = 0;
LABEL_6:
  if ( v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
      v7);
  if ( v6 )
    LeaveCriticalSection(v6);
  v32 = 0;
  v10 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v11 = v10((struct Windows::UI::Composition::ICompositor *)a2, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, &v32);
  v12 = v11;
  if ( v8 )
  {
    if ( !v11 )
    {
      v17 = (__int64 *)((char *)this + 96);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 96);
      v18 = (__int64 *)((char *)this + 88);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
      v36 = 0;
      v19 = v32;
      v20 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v32 + 216LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      v21 = v20(v19, &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85, &v36);
      v15 = v21;
      if ( v21 >= 0 )
      {
        v38 = 0;
        v22 = v32;
        v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v32 + 224LL);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v38,
          0);
        v24 = v23(v22, v36, &v38);
        v15 = v24;
        if ( v24 >= 0 )
        {
          v34[0] = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
          TargetForHandle = DCompositionCreateTargetForHandle(v38, v34);
          v15 = TargetForHandle;
          if ( TargetForHandle >= 0 )
          {
            v26 = v36;
            if ( *v18 != v36 )
            {
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
              v33 = *v18;
              *v18 = v26;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            }
            v27 = v34[0];
            if ( *v17 != v34[0] )
            {
              if ( v34[0] )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34[0] + 8LL))(v34[0]);
              v33 = *v17;
              *v17 = v27;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
            v3 = v37;
            goto LABEL_32;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
            (const char *)(unsigned int)TargetForHandle,
            v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
            (const char *)(unsigned int)v24,
            v32);
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
          (const char *)(unsigned int)v21,
          v32);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      goto LABEL_45;
    }
    v33 = 0;
    v13 = (__int64 (__fastcall *)(struct Windows::UI::Composition::ICompositor *, __int64 *))(*a2)[9];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v14 = v13((struct Windows::UI::Composition::ICompositor *)a2, &v33);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
        (const char *)(unsigned int)v14,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
LABEL_45:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      return v15;
    }
    v16 = v33;
    v36 = v33;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v36);
    v36 = *((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = v16;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  }
LABEL_32:
  EnterCriticalSection(v6);
  v34[1] = v6;
  if ( !*((_BYTE *)this + 229) && !*((_DWORD *)this + 56) )
  {
    v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 120LL))(
            *((_QWORD *)this + 10),
            *(_QWORD *)((char *)this + (v12 != 0 ? 0x18 : 0) + 96));
    v15 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
        (const char *)(unsigned int)v28,
        v32);
      if ( v6 )
        LeaveCriticalSection(v6);
      goto LABEL_45;
    }
  }
  *((_BYTE *)this + 228) = 1;
  if ( v6 )
    LeaveCriticalSection(v6);
  if ( v12 )
  {
    v29 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::UI::Composition::IVisual **))this + 15))(
            *((_QWORD *)this + 15),
            &GUID_117e202d_a859_4c89_873b_c2aa566788e3,
            v3);
    v15 = v29;
    if ( v29 < 0 )
    {
      v30 = 125;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\componentsiteadapter.cpp",
        (const char *)(unsigned int)v29,
        v32);
      goto LABEL_45;
    }
  }
  else
  {
    v29 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::UI::Composition::IVisual **))this + 11))(
            *((_QWORD *)this + 11),
            &GUID_117e202d_a859_4c89_873b_c2aa566788e3,
            v3);
    v15 = v29;
    if ( v29 < 0 )
    {
      v30 = 129;
      goto LABEL_44;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  return 0;
}

```

## disassembly

```asm
0x180014760  mov     [rsp-38h+arg_8], rbx
0x180014765  mov     [rsp-38h+arg_10], r8
0x18001476a  push    rbp
0x18001476b  push    rsi
0x18001476c  push    rdi
0x18001476d  push    r12
0x18001476f  push    r13
0x180014771  push    r14
0x180014773  push    r15
0x180014775  mov     rbp, rsp
0x180014778  sub     rsp, 40h
0x18001477c  mov     r12, r8
0x18001477f  mov     rsi, rdx
0x180014782  mov     r14, rcx
0x180014785  lea     rdi, [rcx+0B0h]
0x18001478c  mov     rcx, rdi; lpCriticalSection
0x18001478f  call    cs:__imp_EnterCriticalSection
0x180014795  cmp     byte ptr [r14+0E4h], 0
0x18001479d  jnz     short loc_1800147B1
0x18001479f  mov     r15b, 1
0x1800147a2  cmp     dword ptr [r14+0E0h], 1
0x1800147aa  jnz     short loc_1800147B4
0x1800147ac  mov     al, r15b
0x1800147af  jmp     short loc_1800147B6
0x1800147b1  xor     r15b, r15b
0x1800147b4  xor     al, al
0x1800147b6  mov     rcx, [rbp+38h]; this
0x1800147ba  test    al, al
0x1800147bc  jz      short loc_1800147D0
0x1800147be  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800147c5  mov     edx, 47h ; 'G'; void *
0x1800147ca  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800147d0  test    rdi, rdi
0x1800147d3  jz      short loc_1800147DE
0x1800147d5  mov     rcx, rdi; lpCriticalSection
0x1800147d8  call    cs:__imp_LeaveCriticalSection
0x1800147de  mov     [rbp+var_20], 0
0x1800147e6  mov     rax, [rsi]
0x1800147e9  mov     rbx, [rax]
0x1800147ec  lea     rcx, [rbp+var_20]
0x1800147f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800147f5  lea     r8, [rbp+var_20]
0x1800147f9  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180014800  mov     rcx, rsi
0x180014803  mov     rax, rbx
0x180014806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001480b  mov     r13d, eax
0x18001480e  test    r15b, r15b
0x180014811  jz      loc_180014A4E
0x180014817  test    eax, eax
0x180014819  jz      loc_1800148A8
0x18001481f  mov     [rbp+var_18], 0
0x180014827  mov     rcx, [rsi]
0x18001482a  mov     rbx, [rcx+48h]
0x18001482e  lea     rcx, [rbp+var_18]
0x180014832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014837  lea     rdx, [rbp+var_18]
0x18001483b  mov     rcx, rsi
0x18001483e  mov     rax, rbx
0x180014841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014846  mov     ebx, eax
0x180014848  test    eax, eax
0x18001484a  jns     short loc_180014873
0x18001484c  mov     rcx, [rbp+38h]; this
0x180014850  mov     r9d, eax; char *
0x180014853  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001485a  mov     edx, 53h ; 'S'; void *
0x18001485f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014864  nop
0x180014865  lea     rcx, [rbp+var_18]
0x180014869  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001486e  jmp     loc_180014B3B
0x180014873  mov     rbx, [rbp+var_18]
0x180014877  mov     [rbp+arg_0], rbx
0x18001487b  lea     rcx, [rbp+arg_0]
0x18001487f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180014884  mov     rax, [r14+78h]
0x180014888  mov     [rbp+arg_0], rax
0x18001488c  mov     [r14+78h], rbx
0x180014890  lea     rcx, [rbp+arg_0]
0x180014894  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014899  nop
0x18001489a  lea     rcx, [rbp+var_18]
0x18001489e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148a3  jmp     loc_180014A4E
0x1800148a8  lea     r12, [r14+60h]
0x1800148ac  mov     rcx, r12
0x1800148af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148b4  lea     r15, [r14+58h]
0x1800148b8  mov     rcx, r15
0x1800148bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148c0  mov     [rbp+arg_0], 0
0x1800148c8  mov     rsi, [rbp+var_20]
0x1800148cc  mov     rax, [rsi]
0x1800148cf  mov     rbx, [rax+0D8h]
0x1800148d6  lea     rcx, [rbp+arg_0]
0x1800148da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800148df  lea     r8, [rbp+arg_0]
0x1800148e3  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x1800148ea  mov     rcx, rsi
0x1800148ed  mov     rax, rbx
0x1800148f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148f5  mov     ebx, eax
0x1800148f7  test    eax, eax
0x1800148f9  jns     short loc_180014922
0x1800148fb  mov     rcx, [rbp+38h]; this
0x1800148ff  mov     r9d, eax; char *
0x180014902  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180014909  mov     edx, 5Ch ; '\'; void *
0x18001490e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014913  nop
0x180014914  lea     rcx, [rbp+arg_0]
0x180014918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001491d  jmp     loc_180014B3B
0x180014922  mov     [rbp+arg_18], 0
0x18001492a  mov     rsi, [rbp+var_20]
0x18001492e  mov     rax, [rsi]
0x180014931  mov     rbx, [rax+0E0h]
0x180014938  xor     edx, edx
0x18001493a  lea     rcx, [rbp+arg_18]
0x18001493e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180014943  lea     r8, [rbp+arg_18]
0x180014947  mov     rdx, [rbp+arg_0]
0x18001494b  mov     rcx, rsi
0x18001494e  mov     rax, rbx
0x180014951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014956  mov     ebx, eax
0x180014958  test    eax, eax
0x18001495a  jns     short loc_180014980
0x18001495c  mov     rcx, [rbp+38h]; this
0x180014960  mov     r9d, eax; char *
0x180014963  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001496a  mov     edx, 61h ; 'a'; void *
0x18001496f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014974  nop
0x180014975  lea     rcx, [rbp+arg_18]
0x180014979  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001497e  jmp     short loc_180014914
0x180014980  mov     [rbp+var_10], 0
0x180014988  lea     rcx, [rbp+var_10]
0x18001498c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014991  lea     rdx, [rbp+var_10]
0x180014995  mov     rcx, [rbp+arg_18]
0x180014999  call    cs:__imp_DCompositionCreateTargetForHandle
0x18001499f  mov     ebx, eax
0x1800149a1  test    eax, eax
0x1800149a3  jns     short loc_1800149C8
0x1800149a5  mov     rcx, [rbp+38h]; this
0x1800149a9  mov     r9d, eax; char *
0x1800149ac  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800149b3  mov     edx, 66h ; 'f'; void *
0x1800149b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149bd  lea     rcx, [rbp+var_10]
0x1800149c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800149c6  jmp     short loc_180014975
0x1800149c8  mov     rbx, [rbp+arg_0]
0x1800149cc  cmp     [r15], rbx
0x1800149cf  jz      short loc_1800149F9
0x1800149d1  test    rbx, rbx
0x1800149d4  jz      short loc_1800149E6
0x1800149d6  mov     rax, [rbx]
0x1800149d9  mov     rcx, rbx
0x1800149dc  mov     rax, [rax+8]
0x1800149e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e5  nop
0x1800149e6  mov     rax, [r15]
0x1800149e9  mov     [rbp+var_18], rax
0x1800149ed  mov     [r15], rbx
0x1800149f0  lea     rcx, [rbp+var_18]
0x1800149f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800149f9  mov     rbx, [rbp+var_10]
0x1800149fd  cmp     [r12], rbx
0x180014a01  jz      short loc_180014A2D
0x180014a03  test    rbx, rbx
0x180014a06  jz      short loc_180014A18
0x180014a08  mov     rax, [rbx]
0x180014a0b  mov     rcx, rbx
0x180014a0e  mov     rax, [rax+8]
0x180014a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a17  nop
0x180014a18  mov     rax, [r12]
0x180014a1c  mov     [rbp+var_18], rax
0x180014a20  mov     [r12], rbx
0x180014a24  lea     rcx, [rbp+var_18]
0x180014a28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a2d  lea     rcx, [rbp+var_10]
0x180014a31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a36  nop
0x180014a37  lea     rcx, [rbp+arg_18]
0x180014a3b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180014a40  nop
0x180014a41  lea     rcx, [rbp+arg_0]
0x180014a45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014a4a  mov     r12, [rbp+arg_10]
0x180014a4e  mov     rcx, rdi; lpCriticalSection
0x180014a51  call    cs:__imp_EnterCriticalSection
0x180014a57  mov     [rbp+var_8], rdi
0x180014a5b  cmp     byte ptr [r14+0E5h], 0
0x180014a63  jnz     short loc_180014AC2
0x180014a65  cmp     dword ptr [r14+0E0h], 0
0x180014a6d  jnz     short loc_180014AC2
0x180014a6f  mov     rcx, [r14+50h]
0x180014a73  mov     r8, [rcx]
0x180014a76  mov     eax, r13d
0x180014a79  neg     eax
0x180014a7b  sbb     rdx, rdx
0x180014a7e  and     edx, 18h
0x180014a81  mov     rdx, [rdx+r14+60h]
0x180014a86  mov     rax, [r8+78h]
0x180014a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8f  mov     ebx, eax
0x180014a91  test    eax, eax
0x180014a93  jns     short loc_180014AC2
0x180014a95  mov     rcx, [rbp+38h]; this
0x180014a99  mov     r9d, eax; char *
0x180014a9c  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180014aa3  mov     edx, 75h ; 'u'; void *
0x180014aa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014aad  nop
0x180014aae  test    rdi, rdi
0x180014ab1  jz      loc_180014B3B
0x180014ab7  mov     rcx, rdi; lpCriticalSection
0x180014aba  call    cs:__imp_LeaveCriticalSection
0x180014ac0  jmp     short loc_180014B3B
0x180014ac2  mov     byte ptr [r14+0E4h], 1
0x180014aca  test    rdi, rdi
0x180014acd  jz      short loc_180014AD8
0x180014acf  mov     rcx, rdi; lpCriticalSection
0x180014ad2  call    cs:__imp_LeaveCriticalSection
0x180014ad8  test    r13d, r13d
0x180014adb  jz      short loc_180014B03
0x180014add  mov     rcx, [r14+78h]
0x180014ae1  mov     rax, [rcx]
0x180014ae4  mov     r8, r12
0x180014ae7  lea     rdx, _GUID_117e202d_a859_4c89_873b_c2aa566788e3
0x180014aee  mov     rax, [rax]
0x180014af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014af6  mov     ebx, eax
0x180014af8  test    eax, eax
0x180014afa  jns     short loc_180014B48
0x180014afc  mov     edx, 7Dh ; '}'
0x180014b01  jmp     short loc_180014B27
0x180014b03  mov     rcx, [r14+58h]
0x180014b07  mov     rax, [rcx]
0x180014b0a  mov     r8, r12
0x180014b0d  lea     rdx, _GUID_117e202d_a859_4c89_873b_c2aa566788e3
0x180014b14  mov     rax, [rax]
0x180014b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b1c  mov     ebx, eax
0x180014b1e  test    eax, eax
0x180014b20  jns     short loc_180014B48
0x180014b22  mov     edx, 81h; void *
0x180014b27  mov     r9d, eax; char *
0x180014b2a  lea     r8, aOnecoreuapInet_21; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180014b31  mov     rcx, [rbp+38h]; this
0x180014b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b3a  nop
0x180014b3b  lea     rcx, [rbp+var_20]
0x180014b3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014b44  mov     eax, ebx
0x180014b46  jmp     short loc_180014B53
0x180014b48  lea     rcx, [rbp+var_20]
0x180014b4c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014b51  xor     eax, eax
0x180014b53  mov     rbx, [rsp+40h+arg_8]
0x180014b5b  add     rsp, 40h
0x180014b5f  pop     r15
0x180014b61  pop     r14
0x180014b63  pop     r13
0x180014b65  pop     r12
0x180014b67  pop     rdi
0x180014b68  pop     rsi
0x180014b69  pop     rbp
0x180014b6a  retn
```
