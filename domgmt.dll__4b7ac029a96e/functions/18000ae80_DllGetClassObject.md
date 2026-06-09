# DllGetClassObject

- ea: `0x18000ae80`
- end: `0x18000b116`
- name: `DllGetClassObject`
- size: `662`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000214c`
- `0x1800021b4`
- `0x180005964`
- `0x180006dd8`
- `0x180009b84`
- `0x180009d10`
- `0x18000a548`
- `0x18000ae80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b109`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b109`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000aff7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000aff7`

## string_xrefs

- `0x18000aeac`: `onecore\enduser\deliveryoptimization\management\dllmain.cpp`
- `0x18000b102`: `DllGetClassObject`
- `0x18000af4d`: `SetServiceCallback`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT CacheEntry; // ebx
  __int64 v7; // rdx
  HMODULE v9; // rcx
  FARPROC v10; // rdi
  int v11; // eax
  void *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  const struct _GUID **v15; // rdi
  unsigned __int64 v16; // rdx
  const struct _GUID *v17; // r9
  _QWORD *v18; // rax
  HMODULE v19; // rcx
  FARPROC ProcAddress; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v22; // [rsp+60h] [rbp+30h] BYREF
  void *Ptr; // [rsp+68h] [rbp+38h] BYREF

  if ( !ppv )
  {
    CacheEntry = -2147467261;
    v7 = 22;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\enduser\\deliveryoptimization\\management\\dllmain.cpp",
      (const char *)(unsigned int)CacheEntry);
    return CacheEntry;
  }
  *ppv = 0;
  Ptr = 0;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&g_providerClassID )
  {
    if ( dword_1800188F0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_1800188F0);
      if ( dword_1800188F0 == -1 )
      {
        v19 = (HMODULE)*((_QWORD *)GetDllForwarder() + 1);
        if ( v19 )
          ProcAddress = GetProcAddress(v19, "DllGetClassObject");
        else
          ProcAddress = 0;
        qword_1800188F8 = (__int64)ProcAddress;
        Init_thread_footer(&dword_1800188F0);
      }
    }
    if ( !qword_1800188F8 )
    {
      CacheEntry = -2147221231;
      v7 = 28;
      goto LABEL_3;
    }
    if ( !g_fMiProviderLoaded )
    {
      v9 = (HMODULE)*((_QWORD *)GetDllForwarder() + 1);
      if ( v9 )
      {
        v10 = GetProcAddress(v9, "SetServiceCallback");
        if ( v10 )
        {
          v22 = 0;
          if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(&v22) >= 0 )
          {
            v11 = ((__int64 (__fastcall *)(__int64))v10)(v22);
            if ( v11 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v12, v13, (const char *)(unsigned int)v11);
          }
          v14 = v22;
          if ( v22 )
          {
            v22 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
      }
    }
    g_fMiProviderLoaded = 1;
    CacheEntry = ((__int64 (__fastcall *)(const IID *const, const IID *const, void **))qword_1800188F8)(
                   rclsid,
                   riid,
                   &Ptr);
    if ( CacheEntry < 0 )
    {
      v7 = 42;
      goto LABEL_3;
    }
  }
  else
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180018928 = 1;
    Ptr = 0;
    v15 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                    + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                                + 8);
    v16 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( (unsigned __int64)v15 >= v16 )
    {
LABEL_23:
      CacheEntry = -2147221231;
    }
    else
    {
      while ( 1 )
      {
        v17 = *v15;
        if ( *v15 )
        {
          v18 = *(_QWORD **)v17->Data4;
          if ( *v18 == *(_QWORD *)&rclsid->Data1 && v18[1] == *(_QWORD *)rclsid->Data4 )
            break;
        }
        if ( (unsigned __int64)++v15 >= v16 )
          goto LABEL_23;
      }
      LODWORD(v22) = 1;
      CacheEntry = Microsoft::WRL::Details::GetCacheEntry(
                     (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                     (struct Microsoft::WRL::Details::ModuleBase *)&v22,
                     &riid->Data1,
                     v17,
                     &Ptr);
    }
    if ( CacheEntry < 0 )
    {
      v7 = 46;
      goto LABEL_3;
    }
  }
  *ppv = Ptr;
  return 0;
}

```

## disassembly

```asm
0x18000ae80  mov     [rsp-18h+arg_0], rbx
0x18000ae85  mov     [rsp-18h+arg_8], rsi
0x18000ae8a  push    rbp
0x18000ae8b  push    rdi
0x18000ae8c  push    r14
0x18000ae8e  mov     rbp, rsp
0x18000ae91  sub     rsp, 30h
0x18000ae95  mov     rsi, r8
0x18000ae98  mov     r14, rdx
0x18000ae9b  mov     rbx, rcx
0x18000ae9e  test    r8, r8
0x18000aea1  jnz     short loc_18000AEC6
0x18000aea3  mov     ebx, 80004003h
0x18000aea8  lea     edx, [r8+16h]; void *
0x18000aeac  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\deliveryoptimization"...
0x18000aeb3  mov     r9d, ebx; char *
0x18000aeb6  mov     rcx, [rbp+18h]; this
0x18000aeba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aebf  mov     eax, ebx
0x18000aec1  jmp     loc_18000B0B0
0x18000aec6  mov     qword ptr [r8], 0
0x18000aecd  mov     [rbp+arg_18], 0
0x18000aed5  mov     rax, [rcx]
0x18000aed8  cmp     rax, qword ptr cs:?g_providerClassID@@3U_GUID@@A.Data1; _GUID g_providerClassID ...
0x18000aedf  jnz     loc_18000AFE3
0x18000aee5  mov     rax, [rcx+8]
0x18000aee9  cmp     rax, qword ptr cs:?g_providerClassID@@3U_GUID@@A.Data4; _GUID g_providerClassID ...
0x18000aef0  jnz     loc_18000AFE3
0x18000aef6  mov     ecx, cs:_tls_index
0x18000aefc  mov     rax, gs:58h
0x18000af05  mov     edx, 4
0x18000af0a  mov     rax, [rax+rcx*8]
0x18000af0e  mov     eax, [rdx+rax]
0x18000af11  cmp     cs:dword_1800188F0, eax
0x18000af17  jg      loc_18000B0DB
0x18000af1d  cmp     cs:qword_1800188F8, 0
0x18000af25  jnz     short loc_18000AF36
0x18000af27  mov     ebx, 80040111h
0x18000af2c  mov     edx, 1Ch
0x18000af31  jmp     loc_18000AEAC
0x18000af36  cmp     cs:?g_fMiProviderLoaded@@3_NA, 0; bool g_fMiProviderLoaded
0x18000af3d  jnz     short loc_18000AFB2
0x18000af3f  call    ?GetDllForwarder@@YAAEAUDllForwarder@@XZ; GetDllForwarder(void)
0x18000af44  mov     rcx, [rax+8]; hModule
0x18000af48  test    rcx, rcx
0x18000af4b  jz      short loc_18000AFB2
0x18000af4d  lea     rdx, aSetservicecall; "SetServiceCallback"
0x18000af54  call    cs:__imp_GetProcAddress
0x18000af5a  mov     rdi, rax
0x18000af5d  test    rax, rax
0x18000af60  jz      short loc_18000AFB2
0x18000af62  mov     [rbp+arg_10], 0
0x18000af6a  lea     rcx, [rbp+arg_10]
0x18000af6e  call    ??$MakeAndInitialize@VCServiceCallback@@UIDOServiceCallback@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIDOServiceCallback@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CServiceCallback,IDOServiceCallback,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDOServiceCallback>>)
0x18000af73  test    eax, eax
0x18000af75  js      short loc_18000AF94
0x18000af77  mov     rcx, [rbp+arg_10]
0x18000af7b  mov     rax, rdi
0x18000af7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af83  mov     rcx, [rbp+18h]; this
0x18000af87  test    eax, eax
0x18000af89  jns     short loc_18000AF94
0x18000af8b  mov     r9d, eax; char *
0x18000af8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000af93  nop
0x18000af94  mov     rcx, [rbp+arg_10]
0x18000af98  test    rcx, rcx
0x18000af9b  jz      short loc_18000AFB2
0x18000af9d  mov     [rbp+arg_10], 0
0x18000afa5  mov     rax, [rcx]
0x18000afa8  mov     rax, [rax+10h]
0x18000afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb1  nop
0x18000afb2  mov     cs:?g_fMiProviderLoaded@@3_NA, 1; bool g_fMiProviderLoaded
0x18000afb9  lea     r8, [rbp+arg_18]
0x18000afbd  mov     rdx, r14
0x18000afc0  mov     rcx, rbx
0x18000afc3  mov     rax, cs:qword_1800188F8
0x18000afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcf  mov     ebx, eax
0x18000afd1  test    eax, eax
0x18000afd3  jns     loc_18000B0A7
0x18000afd9  mov     edx, 2Ah ; '*'
0x18000afde  jmp     loc_18000AEAC
0x18000afe3  xor     r9d, r9d; Context
0x18000afe6  xor     r8d, r8d; Parameter
0x18000afe9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000aff0  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000aff7  call    cs:__imp_InitOnceExecuteOnce
0x18000affd  mov     cs:byte_180018928, 1
0x18000b004  mov     [rbp+arg_18], 0
0x18000b00c  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b013  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b01a  mov     rax, [rax+20h]
0x18000b01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b023  lea     rdi, [rax+8]
0x18000b027  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b02e  mov     rax, [rcx+28h]
0x18000b032  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03e  mov     rdx, rax
0x18000b041  cmp     rdi, rax
0x18000b044  jnb     short loc_18000B06D
0x18000b046  mov     r9, [rdi]; struct _GUID *
0x18000b049  test    r9, r9
0x18000b04c  jz      short loc_18000B064
0x18000b04e  mov     rax, [r9+8]
0x18000b052  mov     rcx, [rax]
0x18000b055  cmp     rcx, [rbx]
0x18000b058  jnz     short loc_18000B064
0x18000b05a  mov     rax, [rax+8]
0x18000b05e  cmp     rax, [rbx+8]
0x18000b062  jz      short loc_18000B080
0x18000b064  add     rdi, 8
0x18000b068  cmp     rdi, rdx
0x18000b06b  jb      short loc_18000B046
0x18000b06d  mov     ebx, 80040111h
0x18000b072  test    ebx, ebx
0x18000b074  jns     short loc_18000B0A7
0x18000b076  mov     edx, 2Eh ; '.'
0x18000b07b  jmp     loc_18000AEAC
0x18000b080  mov     dword ptr [rbp+arg_10], 1
0x18000b087  lea     rax, [rbp+arg_18]
0x18000b08b  mov     [rsp+30h+Ptr], rax; Ptr
0x18000b090  mov     r8, r14; unsigned int *
0x18000b093  lea     rdx, [rbp+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000b097  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b09e  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000b0a3  mov     ebx, eax
0x18000b0a5  jmp     short loc_18000B072
0x18000b0a7  mov     rax, [rbp+arg_18]
0x18000b0ab  mov     [rsi], rax
0x18000b0ae  xor     eax, eax
0x18000b0b0  mov     rbx, [rsp+30h+arg_0]
0x18000b0b5  mov     rsi, [rsp+30h+arg_8]
0x18000b0ba  add     rsp, 30h
0x18000b0be  pop     r14
0x18000b0c0  pop     rdi
0x18000b0c1  pop     rbp
0x18000b0c2  retn
0x18000b0c3  mov     cs:qword_1800188F8, rax
0x18000b0ca  lea     rcx, dword_1800188F0
0x18000b0d1  call    _Init_thread_footer
0x18000b0d6  jmp     loc_18000AF1D
0x18000b0db  lea     rcx, dword_1800188F0
0x18000b0e2  call    _Init_thread_header
0x18000b0e7  cmp     cs:dword_1800188F0, 0FFFFFFFFh
0x18000b0ee  jnz     loc_18000AF1D
0x18000b0f4  call    ?GetDllForwarder@@YAAEAUDllForwarder@@XZ; GetDllForwarder(void)
0x18000b0f9  mov     rcx, [rax+8]; hModule
0x18000b0fd  test    rcx, rcx
0x18000b100  jz      short loc_18000B111
0x18000b102  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000b109  call    cs:__imp_GetProcAddress
0x18000b10f  jmp     short loc_18000B0C3
0x18000b111  xor     eax, eax
0x18000b113  jmp     short loc_18000B0C3
```
