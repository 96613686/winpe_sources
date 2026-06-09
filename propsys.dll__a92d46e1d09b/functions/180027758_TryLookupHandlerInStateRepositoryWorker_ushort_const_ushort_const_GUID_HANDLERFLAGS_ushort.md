# TryLookupHandlerInStateRepositoryWorker(ushort const *,ushort const *,_GUID *,HANDLERFLAGS *,ushort * *)

- ea: `0x180027758`
- end: `0x180027bba`
- name: `?TryLookupHandlerInStateRepositoryWorker@@YAJPEBG0PEAU_GUID@@PEAW4HANDLERFLAGS@@PEAPEAG@Z`
- size: `1122`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, enum HANDLERFLAGS *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027710`

## callees

- `0x180003f94`
- `0x180025dd4`
- `0x180027758`
- `0x180027bc0`
- `0x180057ab4`
- `0x180057db4`
- `0x180057ea0`
- `0x1800605dc`
- `0x1800626f0`
- `0x180067ffc`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800279a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800279e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800279a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800279e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027aea`

## string_xrefs

- `0x1800279b0`: `@Clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall TryLookupHandlerInStateRepositoryWorker(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        enum HANDLERFLAGS *a4,
        unsigned __int16 **a5)
{
  int FileTypeAssocFromStateRepository; // eax
  unsigned int v10; // ebx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v11; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v13; // rbx
  __int64 (__fastcall *v14)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, __int64 *); // rdi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct IInspectable *v18; // rcx
  struct IInspectable *v19; // rcx
  struct IInspectable *v20; // rcx
  __int64 v21; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v22; // rcx
  __int64 v23; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v24; // rcx
  int v25; // eax
  struct IInspectable *v26; // rcx
  struct IInspectable *v27; // rcx
  struct IInspectable *v28; // rcx
  __int64 v29; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v30; // rcx
  struct IInspectable *v31; // rcx
  __int64 v32; // rcx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v33; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int HandlerFlags; // eax
  struct _GUID *v36; // rcx
  __int64 v37; // rdx
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v38; // [rsp+20h] [rbp-48h] BYREF
  HSTRING string; // [rsp+28h] [rbp-40h] BYREF
  __int64 v40; // [rsp+30h] [rbp-38h] BYREF
  struct IInspectable *v41; // [rsp+38h] [rbp-30h] BYREF
  struct IInspectable *v42; // [rsp+40h] [rbp-28h] BYREF
  struct IInspectable *v43; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  *a3 = GUID_NULL;
  if ( a5 )
    *a5 = 0;
  *(_DWORD *)a4 = 0;
  v38 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v38);
  FileTypeAssocFromStateRepository = TryGetFileTypeAssocFromStateRepository(a1, &v38);
  v10 = FileTypeAssocFromStateRepository;
  if ( FileTypeAssocFromStateRepository < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
      (const char *)(unsigned int)FileTypeAssocFromStateRepository,
      (int)v38);
    v11 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v10;
  }
  v13 = v38;
  if ( v38 )
  {
    v40 = 0;
    v14 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *, __int64 *))(*(_QWORD *)v38 + 96LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v40);
    v15 = v14(v13, &v40);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v15,
        (int)v38);
      v23 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v10;
    }
    v42 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v42);
    v16 = wil::get_sr_entity_propset<Windows::Internal::StateRepository::IApplicationExtension>(v40, &v42);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v16,
        (int)v38);
      v31 = v42;
      if ( v42 )
      {
        v42 = 0;
        ((void (__fastcall *)(struct IInspectable *))v31->lpVtbl->Release)(v31);
      }
      v32 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      return v10;
    }
    v43 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v43);
    v17 = LookupInPropertySet(v42, L"FileTypeAssociation", &v43);
    v10 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)v17,
        (int)v38);
    }
    else
    {
      v41 = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v41);
      if ( (int)LookupInPropertySet(v43, a2, &v41) < 0 )
      {
LABEL_13:
        v18 = v41;
        if ( v41 )
        {
          v41 = 0;
          ((void (__fastcall *)(struct IInspectable *))v18->lpVtbl->Release)(v18);
        }
        v19 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IInspectable *))v19->lpVtbl->Release)(v19);
        }
        v20 = v42;
        if ( v42 )
        {
          v42 = 0;
          ((void (__fastcall *)(struct IInspectable *))v20->lpVtbl->Release)(v20);
        }
        v21 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v22 + 16LL))(v22);
        }
        return 0;
      }
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v25 = LookupStringInPropertySet(v41, L"@Clsid", &string);
      v10 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
          (const char *)(unsigned int)v25,
          (int)v38);
        WindowsDeleteString(string);
        string = 0;
        v26 = v41;
        if ( v41 )
        {
          v41 = 0;
          ((void (__fastcall *)(struct IInspectable *))v26->lpVtbl->Release)(v26);
        }
        v27 = v43;
        if ( v43 )
        {
          v43 = 0;
          ((void (__fastcall *)(struct IInspectable *))v27->lpVtbl->Release)(v27);
        }
        v28 = v42;
        if ( v42 )
        {
          v42 = 0;
          ((void (__fastcall *)(struct IInspectable *))v28->lpVtbl->Release)(v28);
        }
        v29 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociation *))(*(_QWORD *)v30 + 16LL))(v30);
        }
        return v10;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      HandlerFlags = ParseCLSID(StringRawBuffer, a3);
      v10 = HandlerFlags;
      if ( HandlerFlags < 0 )
      {
        v37 = 353;
      }
      else
      {
        HandlerFlags = GetHandlerFlags(v41, a4);
        v10 = HandlerFlags;
        if ( HandlerFlags < 0 )
        {
          v37 = 354;
        }
        else
        {
          if ( !a5 || (HandlerFlags = LookupServerPath(v36, a5), v10 = HandlerFlags, HandlerFlags >= 0) )
          {
            WindowsDeleteString(string);
            goto LABEL_13;
          }
          v37 = 358;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecoreuap\\shell\\propsys\\getpropertystore.cpp",
        (const char *)(unsigned int)HandlerFlags,
        (int)v38);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v41);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v38);
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180027758  push    rbp
0x18002775a  push    rbx
0x18002775b  push    rsi
0x18002775c  push    rdi
0x18002775d  push    r12
0x18002775f  push    r13
0x180027761  push    r14
0x180027763  push    r15
0x180027765  mov     rbp, rsp
0x180027768  sub     rsp, 68h
0x18002776c  mov     rax, cs:__security_cookie
0x180027773  xor     rax, rsp
0x180027776  mov     [rbp+var_18], rax
0x18002777a  mov     r14, r9
0x18002777d  mov     r15, r8
0x180027780  mov     r12, rdx
0x180027783  mov     rbx, rcx
0x180027786  mov     rsi, [rbp+arg_20]
0x18002778a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180027791  movdqu  xmmword ptr [r8], xmm0
0x180027796  xor     r13d, r13d
0x180027799  test    rsi, rsi
0x18002779c  jz      short loc_1800277A1
0x18002779e  mov     [rsi], r13
0x1800277a1  mov     [r9], r13d
0x1800277a4  mov     [rbp+var_48], r13
0x1800277a8  lea     rcx, [rbp+var_48]
0x1800277ac  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800277b1  lea     rdx, [rbp+var_48]; struct Windows::Internal::StateRepository::IFileTypeAssociation **
0x1800277b5  mov     rcx, rbx; unsigned __int16 *
0x1800277b8  call    ?TryGetFileTypeAssocFromStateRepository@@YAJPEBGPEAPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z; TryGetFileTypeAssocFromStateRepository(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation * *)
0x1800277bd  mov     ebx, eax
0x1800277bf  test    eax, eax
0x1800277c1  jns     short loc_180027815
0x1800277c3  mov     rcx, [rbp+40h]; this
0x1800277c7  mov     r9d, eax; char *
0x1800277ca  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x1800277d1  mov     edx, 147h; void *
0x1800277d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277db  nop
0x1800277dc  mov     rcx, [rbp+var_48]
0x1800277e0  test    rcx, rcx
0x1800277e3  jz      short loc_1800277F6
0x1800277e5  mov     [rbp+var_48], r13
0x1800277e9  mov     rax, [rcx]
0x1800277ec  mov     rax, [rax+10h]
0x1800277f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277f5  nop
0x1800277f6  mov     eax, ebx
0x1800277f8  mov     rcx, [rbp+var_18]
0x1800277fc  xor     rcx, rsp; StackCookie
0x1800277ff  call    __security_check_cookie
0x180027804  add     rsp, 68h
0x180027808  pop     r15
0x18002780a  pop     r14
0x18002780c  pop     r13
0x18002780e  pop     r12
0x180027810  pop     rdi
0x180027811  pop     rsi
0x180027812  pop     rbx
0x180027813  pop     rbp
0x180027814  retn
0x180027815  mov     rbx, [rbp+var_48]
0x180027819  test    rbx, rbx
0x18002781c  jnz     short loc_180027822
0x18002781e  xor     eax, eax
0x180027820  jmp     short loc_1800277F8
0x180027822  mov     [rbp+var_38], r13
0x180027826  mov     rax, [rbx]
0x180027829  mov     rdi, [rax+60h]
0x18002782d  lea     rcx, [rbp+var_38]
0x180027831  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027836  lea     rdx, [rbp+var_38]
0x18002783a  mov     rcx, rbx
0x18002783d  mov     rax, rdi
0x180027840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027845  mov     ebx, eax
0x180027847  test    eax, eax
0x180027849  js      loc_18002794A
0x18002784f  mov     [rbp+var_28], r13
0x180027853  lea     rcx, [rbp+var_28]
0x180027857  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18002785c  lea     rdx, [rbp+var_28]
0x180027860  mov     rcx, [rbp+var_38]
0x180027864  call    ??$get_sr_entity_propset@UIApplicationExtension@StateRepository@Internal@Windows@@@wil@@YAJPEAUIApplicationExtension@StateRepository@Internal@Windows@@PEAPEAUIPropertySet@Collections@Foundation@4@@Z; wil::get_sr_entity_propset<Windows::Internal::StateRepository::IApplicationExtension>(Windows::Internal::StateRepository::IApplicationExtension *,Windows::Foundation::Collections::IPropertySet * *)
0x180027869  mov     ebx, eax
0x18002786b  test    eax, eax
0x18002786d  js      loc_180027A78
0x180027873  mov     [rbp+var_20], r13
0x180027877  lea     rcx, [rbp+var_20]
0x18002787b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027880  lea     r8, [rbp+var_20]; struct IInspectable **
0x180027884  lea     rdx, aFiletypeassoci; "FileTypeAssociation"
0x18002788b  mov     rcx, [rbp+var_28]; struct IInspectable *
0x18002788f  call    ?LookupInPropertySet@@YAJPEAUIInspectable@@PEBGPEAPEAU1@@Z; LookupInPropertySet(IInspectable *,ushort const *,IInspectable * *)
0x180027894  mov     ebx, eax
0x180027896  test    eax, eax
0x180027898  js      loc_180027B35
0x18002789e  mov     [rbp+var_30], r13
0x1800278a2  lea     rcx, [rbp+var_30]
0x1800278a6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800278ab  lea     r8, [rbp+var_30]; struct IInspectable **
0x1800278af  mov     rdx, r12; unsigned __int16 *
0x1800278b2  mov     rcx, [rbp+var_20]; struct IInspectable *
0x1800278b6  call    ?LookupInPropertySet@@YAJPEAUIInspectable@@PEBGPEAPEAU1@@Z; LookupInPropertySet(IInspectable *,ushort const *,IInspectable * *)
0x1800278bb  test    eax, eax
0x1800278bd  jns     loc_18002799C
0x1800278c3  mov     rcx, [rbp+var_30]
0x1800278c7  test    rcx, rcx
0x1800278ca  jz      short loc_1800278DD
0x1800278cc  mov     [rbp+var_30], r13
0x1800278d0  mov     rax, [rcx]
0x1800278d3  mov     rax, [rax+10h]
0x1800278d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278dc  nop
0x1800278dd  mov     rcx, [rbp+var_20]
0x1800278e1  test    rcx, rcx
0x1800278e4  jz      short loc_1800278F7
0x1800278e6  mov     [rbp+var_20], r13
0x1800278ea  mov     rax, [rcx]
0x1800278ed  mov     rax, [rax+10h]
0x1800278f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278f6  nop
0x1800278f7  mov     rcx, [rbp+var_28]
0x1800278fb  test    rcx, rcx
0x1800278fe  jz      short loc_180027911
0x180027900  mov     [rbp+var_28], r13
0x180027904  mov     rax, [rcx]
0x180027907  mov     rax, [rax+10h]
0x18002790b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027910  nop
0x180027911  mov     rcx, [rbp+var_38]
0x180027915  test    rcx, rcx
0x180027918  jz      short loc_18002792B
0x18002791a  mov     [rbp+var_38], r13
0x18002791e  mov     rax, [rcx]
0x180027921  mov     rax, [rax+10h]
0x180027925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002792a  nop
0x18002792b  mov     rcx, [rbp+var_48]
0x18002792f  test    rcx, rcx
0x180027932  jz      short loc_180027945
0x180027934  mov     [rbp+var_48], r13
0x180027938  mov     rax, [rcx]
0x18002793b  mov     rax, [rax+10h]
0x18002793f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027944  nop
0x180027945  jmp     loc_18002781E
0x18002794a  mov     rcx, [rbp+40h]; this
0x18002794e  mov     r9d, ebx; char *
0x180027951  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027958  mov     edx, 154h; void *
0x18002795d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027962  nop
0x180027963  mov     rcx, [rbp+var_38]
0x180027967  test    rcx, rcx
0x18002796a  jz      short loc_18002797D
0x18002796c  mov     [rbp+var_38], r13
0x180027970  mov     rax, [rcx]
0x180027973  mov     rax, [rax+10h]
0x180027977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002797c  nop
0x18002797d  mov     rcx, [rbp+var_48]
0x180027981  test    rcx, rcx
0x180027984  jz      short loc_180027997
0x180027986  mov     [rbp+var_48], r13
0x18002798a  mov     rax, [rcx]
0x18002798d  mov     rax, [rax+10h]
0x180027991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027996  nop
0x180027997  jmp     loc_1800277F6
0x18002799c  mov     [rbp+string], r13
0x1800279a0  xor     ecx, ecx; string
0x1800279a2  call    cs:__imp_WindowsDeleteString
0x1800279a8  mov     [rbp+string], r13
0x1800279ac  lea     r8, [rbp+string]; HSTRING *
0x1800279b0  lea     rdx, aClsid; "@Clsid"
0x1800279b7  mov     rcx, [rbp+var_30]; struct IInspectable *
0x1800279bb  call    ?LookupStringInPropertySet@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x1800279c0  mov     ebx, eax
0x1800279c2  test    eax, eax
0x1800279c4  jns     loc_180027AE4
0x1800279ca  mov     rcx, [rbp+40h]; this
0x1800279ce  mov     r9d, eax; char *
0x1800279d1  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x1800279d8  mov     edx, 160h; void *
0x1800279dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279e2  nop
0x1800279e3  mov     rcx, [rbp+string]; string
0x1800279e7  call    cs:__imp_WindowsDeleteString
0x1800279ed  mov     [rbp+string], r13
0x1800279f1  mov     rcx, [rbp+var_30]
0x1800279f5  test    rcx, rcx
0x1800279f8  jz      short loc_180027A0B
0x1800279fa  mov     [rbp+var_30], r13
0x1800279fe  mov     rax, [rcx]
0x180027a01  mov     rax, [rax+10h]
0x180027a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a0a  nop
0x180027a0b  mov     rcx, [rbp+var_20]
0x180027a0f  test    rcx, rcx
0x180027a12  jz      short loc_180027A25
0x180027a14  mov     [rbp+var_20], r13
0x180027a18  mov     rax, [rcx]
0x180027a1b  mov     rax, [rax+10h]
0x180027a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a24  nop
0x180027a25  mov     rcx, [rbp+var_28]
0x180027a29  test    rcx, rcx
0x180027a2c  jz      short loc_180027A3F
0x180027a2e  mov     [rbp+var_28], r13
0x180027a32  mov     rax, [rcx]
0x180027a35  mov     rax, [rax+10h]
0x180027a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a3e  nop
0x180027a3f  mov     rcx, [rbp+var_38]
0x180027a43  test    rcx, rcx
0x180027a46  jz      short loc_180027A59
0x180027a48  mov     [rbp+var_38], r13
0x180027a4c  mov     rax, [rcx]
0x180027a4f  mov     rax, [rax+10h]
0x180027a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a58  nop
0x180027a59  mov     rcx, [rbp+var_48]
0x180027a5d  test    rcx, rcx
0x180027a60  jz      short loc_180027A73
0x180027a62  mov     [rbp+var_48], r13
0x180027a66  mov     rax, [rcx]
0x180027a69  mov     rax, [rax+10h]
0x180027a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a72  nop
0x180027a73  jmp     loc_1800277F6
0x180027a78  mov     rcx, [rbp+40h]; this
0x180027a7c  mov     r9d, ebx; char *
0x180027a7f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027a86  mov     edx, 157h; void *
0x180027a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a90  nop
0x180027a91  mov     rcx, [rbp+var_28]
0x180027a95  test    rcx, rcx
0x180027a98  jz      short loc_180027AAB
0x180027a9a  mov     [rbp+var_28], r13
0x180027a9e  mov     rax, [rcx]
0x180027aa1  mov     rax, [rax+10h]
0x180027aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027aaa  nop
0x180027aab  mov     rcx, [rbp+var_38]
0x180027aaf  test    rcx, rcx
0x180027ab2  jz      short loc_180027AC5
0x180027ab4  mov     [rbp+var_38], r13
0x180027ab8  mov     rax, [rcx]
0x180027abb  mov     rax, [rax+10h]
0x180027abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ac4  nop
0x180027ac5  mov     rcx, [rbp+var_48]
0x180027ac9  test    rcx, rcx
0x180027acc  jz      short loc_180027ADF
0x180027ace  mov     [rbp+var_48], r13
0x180027ad2  mov     rax, [rcx]
0x180027ad5  mov     rax, [rax+10h]
0x180027ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ade  nop
0x180027adf  jmp     loc_1800277F6
0x180027ae4  xor     edx, edx; length
0x180027ae6  mov     rcx, [rbp+string]; string
0x180027aea  call    cs:__imp_WindowsGetStringRawBuffer
0x180027af0  mov     rdx, r15; struct _GUID *
0x180027af3  mov     rcx, rax; unsigned __int16 *
0x180027af6  call    ?ParseCLSID@@YAJPEBGPEAU_GUID@@@Z; ParseCLSID(ushort const *,_GUID *)
0x180027afb  mov     ebx, eax
0x180027afd  test    eax, eax
0x180027aff  js      short loc_180027B4F
0x180027b01  mov     rdx, r14; enum HANDLERFLAGS *
0x180027b04  mov     rcx, [rbp+var_30]; struct IInspectable *
0x180027b08  call    ?GetHandlerFlags@@YAJPEAUIInspectable@@PEAW4HANDLERFLAGS@@@Z; GetHandlerFlags(IInspectable *,HANDLERFLAGS *)
0x180027b0d  mov     ebx, eax
0x180027b0f  test    eax, eax
0x180027b11  js      short loc_180027B56
0x180027b13  test    rsi, rsi
0x180027b16  jz      short loc_180027B26
0x180027b18  mov     rdx, rsi; unsigned __int16 **
0x180027b1b  call    ?LookupServerPath@@YAJU_GUID@@PEAPEAG@Z; LookupServerPath(_GUID,ushort * *)
0x180027b20  mov     ebx, eax
0x180027b22  test    eax, eax
0x180027b24  js      short loc_180027B5D
0x180027b26  mov     rcx, [rbp+string]; string
0x180027b2a  call    cs:__imp_WindowsDeleteString
0x180027b30  jmp     loc_1800278C3
0x180027b35  mov     rcx, [rbp+40h]; this
0x180027b39  mov     r9d, eax; char *
0x180027b3c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\propsys\\getproperty"...
0x180027b43  mov     edx, 15Ah; void *
0x180027b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b4d  jmp     short loc_180027B8E
0x180027b4f  mov     edx, 161h
0x180027b54  jmp     short loc_180027B62
0x180027b56  mov     edx, 162h
0x180027b5b  jmp     short loc_180027B62
0x180027b5d  mov     edx, 166h; void *
0x180027b62  mov     r9d, eax; char *
  ... truncated ...
```
