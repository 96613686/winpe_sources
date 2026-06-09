# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x18000289c`
- end: `0x180002b3d`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `673`
- prototype: `__int64(__int64, char, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180004820`

## callees

- `0x1800026d0`
- `0x18000289c`
- `0x180002b44`
- `0x180006160`
- `0x180006d14`
- `0x180007a88`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002983`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002983`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a95`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800028d3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800028d3`

## string_xrefs

- `0x1800028ed`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000292d`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000299a`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800029f6`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002a51`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002aac`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180002b0e`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        ...)
{
  Windows::Internal::ServiceModuleBase *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  int v14; // eax
  HRESULT Instance; // eax
  int v16; // eax
  int ppv; // [rsp+20h] [rbp-68h]
  int ppva; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID v20; // [rsp+90h] [rbp+8h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (Windows::Internal::ServiceModuleBase *)*wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                                  (__int64 *)va,
                                                  a1);
  v8 = RoInitialize(1);
  v9 = v8;
  *(_DWORD *)(a1 + 16) = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v8,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  if ( a2 )
  {
    v11 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>();
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v11,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    v20 = 0;
    Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(&v20);
    v12 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v20);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v12,
        ppv);
      Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(&v20);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v20 + 24LL))(v20, 1, 2);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v13,
        ppv);
      Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(&v20);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(&v20);
  }
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v14,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(a1 + 24);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)(a1 + 24));
  v9 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), __int64, GUID *))(**(_QWORD **)(a1 + 24) + 24LL))(
          *(_QWORD *)(a1 + 24),
          Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
          a1,
          &IID_IContextCallback);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v16,
      5);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18000289c  mov     rax, rsp
0x18000289f  push    rbx
0x1800028a0  push    rbp
0x1800028a1  push    rsi
0x1800028a2  push    rdi
0x1800028a3  push    r14
0x1800028a5  push    r15
0x1800028a7  sub     rsp, 58h
0x1800028ab  mov     bpl, dl
0x1800028ae  mov     rsi, rcx
0x1800028b1  mov     rdx, rcx
0x1800028b4  lea     rcx, [rax+30h]
0x1800028b8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800028bd  mov     rbx, [rax]
0x1800028c0  mov     [rsp+88h+var_48], rbx
0x1800028c5  mov     r15d, 1
0x1800028cb  mov     [rsp+88h+var_40], r15b
0x1800028d0  mov     ecx, r15d
0x1800028d3  call    cs:__imp_RoInitialize
0x1800028d9  mov     edi, eax
0x1800028db  mov     [rsi+10h], eax
0x1800028de  test    eax, eax
0x1800028e0  jns     short loc_18000290E
0x1800028e2  mov     rcx, [rsp+88h]; this
0x1800028ea  mov     r9d, eax; char *
0x1800028ed  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800028f4  lea     edx, [r15+62h]; void *
0x1800028f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800028fd  nop
0x1800028fe  mov     rcx, rbx; this
0x180002901  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002906  nop
0x180002907  mov     eax, edi
0x180002909  jmp     loc_180002B30
0x18000290e  test    bpl, bpl
0x180002911  jz      loc_180002A31
0x180002917  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)
0x18000291c  mov     edi, eax
0x18000291e  test    eax, eax
0x180002920  jns     short loc_18000294A
0x180002922  mov     rcx, [rsp+88h]; this
0x18000292a  mov     r9d, eax; char *
0x18000292d  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002934  mov     edx, 6Ch ; 'l'; void *
0x180002939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000293e  nop
0x18000293f  mov     rcx, rbx; this
0x180002942  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002947  nop
0x180002948  jmp     short loc_180002907
0x18000294a  mov     [rsp+88h+arg_0], 0
0x180002956  lea     rcx, [rsp+88h+arg_0]
0x18000295e  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x180002963  lea     rax, [rsp+88h+arg_0]
0x18000296b  mov     [rsp+88h+ppv], rax; int
0x180002970  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180002977  mov     r8d, r15d; dwClsContext
0x18000297a  xor     edx, edx; pUnkOuter
0x18000297c  lea     rcx, CLSID_GlobalOptions; rclsid
0x180002983  call    cs:__imp_CoCreateInstance
0x180002989  mov     edi, eax
0x18000298b  test    eax, eax
0x18000298d  jns     short loc_1800029C8
0x18000298f  mov     rcx, [rsp+88h]; this
0x180002997  mov     r9d, eax; char *
0x18000299a  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800029a1  mov     edx, 73h ; 's'; void *
0x1800029a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800029ab  nop
0x1800029ac  lea     rcx, [rsp+88h+arg_0]
0x1800029b4  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x1800029b9  nop
0x1800029ba  mov     rcx, rbx; this
0x1800029bd  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800029c2  nop
0x1800029c3  jmp     loc_180002907
0x1800029c8  mov     rcx, [rsp+88h+arg_0]
0x1800029d0  mov     rax, [rcx]
0x1800029d3  mov     r8d, 2
0x1800029d9  mov     edx, r15d
0x1800029dc  mov     rax, [rax+18h]
0x1800029e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e5  mov     edi, eax
0x1800029e7  test    eax, eax
0x1800029e9  jns     short loc_180002A24
0x1800029eb  mov     rcx, [rsp+88h]; this
0x1800029f3  mov     r9d, eax; char *
0x1800029f6  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x1800029fd  mov     edx, 74h ; 't'; void *
0x180002a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a07  nop
0x180002a08  lea     rcx, [rsp+88h+arg_0]
0x180002a10  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x180002a15  nop
0x180002a16  mov     rcx, rbx; this
0x180002a19  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002a1e  nop
0x180002a1f  jmp     loc_180002907
0x180002a24  lea     rcx, [rsp+88h+arg_0]
0x180002a2c  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x180002a31  mov     rax, [rsi]
0x180002a34  mov     rcx, rsi
0x180002a37  mov     rax, [rax+20h]
0x180002a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a40  mov     edi, eax
0x180002a42  test    eax, eax
0x180002a44  jns     short loc_180002A71
0x180002a46  mov     rcx, [rsp+88h]; this
0x180002a4e  mov     r9d, eax; char *
0x180002a51  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002a58  mov     edx, 7Bh ; '{'; void *
0x180002a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a62  nop
0x180002a63  mov     rcx, rbx; this
0x180002a66  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002a6b  nop
0x180002a6c  jmp     loc_180002907
0x180002a71  lea     r14, [rsi+18h]
0x180002a75  mov     rcx, r14
0x180002a78  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x180002a7d  mov     [rsp+88h+ppv], r14; int
0x180002a82  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180002a89  mov     r8d, r15d; dwClsContext
0x180002a8c  xor     edx, edx; pUnkOuter
0x180002a8e  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180002a95  call    cs:__imp_CoCreateInstance
0x180002a9b  mov     edi, eax
0x180002a9d  test    eax, eax
0x180002a9f  jns     short loc_180002ACC
0x180002aa1  mov     rcx, [rsp+88h]; this
0x180002aa9  mov     r9d, eax; char *
0x180002aac  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002ab3  mov     edx, 8Dh; void *
0x180002ab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002abd  nop
0x180002abe  mov     rcx, rbx; this
0x180002ac1  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002ac6  nop
0x180002ac7  jmp     loc_180002907
0x180002acc  mov     rcx, [r14]
0x180002acf  mov     rax, [rcx]
0x180002ad2  mov     [rsp+88h+var_60], 0
0x180002adb  mov     dword ptr [rsp+88h+ppv], 5; int
0x180002ae3  lea     r9, IID_IContextCallback
0x180002aea  mov     r8, rsi
0x180002aed  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x180002af4  mov     rax, [rax+18h]
0x180002af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002afd  mov     edi, eax
0x180002aff  test    eax, eax
0x180002b01  jns     short loc_180002B2E
0x180002b03  mov     rcx, [rsp+88h]; this
0x180002b0b  mov     r9d, eax; char *
0x180002b0e  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180002b15  mov     edx, 90h; void *
0x180002b1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b1f  nop
0x180002b20  mov     rcx, rbx; this
0x180002b23  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180002b28  nop
0x180002b29  jmp     loc_180002907
0x180002b2e  xor     eax, eax
0x180002b30  add     rsp, 58h
0x180002b34  pop     r15
0x180002b36  pop     r14
0x180002b38  pop     rdi
0x180002b39  pop     rsi
0x180002b3a  pop     rbp
0x180002b3b  pop     rbx
0x180002b3c  retn
```
