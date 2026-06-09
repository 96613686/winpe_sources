# OobeZdpElevatedManagerCore::FilterUpdates(IUpdateCollection *,IUpdateCollection * *)

- ea: `0x18000ebd0`
- end: `0x18000ed4a`
- name: `?FilterUpdates@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateCollection@@PEAPEAU2@@Z`
- size: `378`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateCollection *, struct IUpdateCollection **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18000ebd0`
- `0x18000f5cc`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ec62`

## string_xrefs

- `0x18000ec25`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000ec75`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OobeZdpElevatedManagerCore::FilterUpdates(
        OobeZdpElevatedManagerCore *this,
        struct IUpdateCollection *a2,
        struct IUpdateCollection **a3)
{
  int v5; // eax
  unsigned int v6; // edi
  HRESULT v8; // eax
  int i; // edi
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  struct IUpdateCollection *v11; // rax
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  LPVOID v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  OobeZdpElevatedManagerCore *v17; // [rsp+60h] [rbp+20h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF

  v17 = this;
  *a3 = 0;
  if ( OobeZdpElevatedManagerCore::IsCurrentNetworkMetered(this) )
  {
    LODWORD(v17) = 0;
    v5 = ((__int64 (__fastcall *)(struct IUpdateCollection *, OobeZdpElevatedManagerCore **))a2->lpVtbl->get_Count)(
           a2,
           &v17);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      return v6;
    }
    v14 = 0;
    v8 = CoCreateInstance(
           &GUID_13639463_00db_4646_803d_528026140d88,
           0,
           1u,
           &GUID_07f7438c_7709_4ca5_b518_91279288134e,
           &v14);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
        (const char *)(unsigned int)v8,
        ppva);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v14);
      return v6;
    }
    for ( i = 0; i < (int)v17; ++i )
    {
      v18 = 0;
      lpVtbl = a2->lpVtbl;
      v15 = 0;
      if ( ((int (__fastcall *)(struct IUpdateCollection *, _QWORD, __int64 *))lpVtbl->get_Item)(
             a2,
             (unsigned int)i,
             &v15) >= 0
        && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 400LL))(v15, &v18) >= 0
        && v18 == 3 )
      {
        v19 = 0;
        (*(void (__fastcall **)(LPVOID, __int64, int *))(*(_QWORD *)v14 + 96LL))(v14, v15, &v19);
      }
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v15);
    }
    v11 = (struct IUpdateCollection *)v14;
    v14 = 0;
    *a3 = v11;
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v14);
  }
  else
  {
    *a3 = a2;
    ((void (__fastcall *)(struct IUpdateCollection *))a2->lpVtbl->AddRef)(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ebd0  mov     [rsp-18h+arg_8], rbx
0x18000ebd5  mov     [rsp-18h+arg_0], rcx
0x18000ebda  push    rbp
0x18000ebdb  push    rsi
0x18000ebdc  push    rdi
0x18000ebdd  mov     rbp, rsp
0x18000ebe0  sub     rsp, 40h
0x18000ebe4  mov     rsi, r8
0x18000ebe7  mov     rbx, rdx
0x18000ebea  mov     qword ptr [r8], 0
0x18000ebf1  call    ?IsCurrentNetworkMetered@OobeZdpElevatedManagerCore@@AEAA_NXZ; OobeZdpElevatedManagerCore::IsCurrentNetworkMetered(void)
0x18000ebf6  mov     rcx, rbx
0x18000ebf9  test    al, al
0x18000ebfb  jz      loc_18000ED2C
0x18000ec01  mov     dword ptr [rbp+arg_0], 0
0x18000ec08  mov     rax, [rbx]
0x18000ec0b  lea     rdx, [rbp+arg_0]
0x18000ec0f  mov     rax, [rax+50h]
0x18000ec13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec18  mov     edi, eax
0x18000ec1a  test    eax, eax
0x18000ec1c  jns     short loc_18000EC3D
0x18000ec1e  mov     rcx, [rbp+18h]; this
0x18000ec22  mov     r9d, eax; char *
0x18000ec25  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000ec2c  mov     edx, 0A8h; void *
0x18000ec31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec36  mov     eax, edi
0x18000ec38  jmp     loc_18000ED3D
0x18000ec3d  mov     [rbp+var_10], 0
0x18000ec45  lea     rax, [rbp+var_10]
0x18000ec49  mov     qword ptr [rsp+40h+ppv], rax; int
0x18000ec4e  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x18000ec55  xor     edx, edx; pUnkOuter
0x18000ec57  lea     r8d, [rdx+1]; dwClsContext
0x18000ec5b  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x18000ec62  call    cs:__imp_CoCreateInstance
0x18000ec68  mov     edi, eax
0x18000ec6a  test    eax, eax
0x18000ec6c  jns     short loc_18000EC92
0x18000ec6e  mov     rcx, [rbp+18h]; this
0x18000ec72  mov     r9d, eax; char *
0x18000ec75  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000ec7c  mov     edx, 0ABh; void *
0x18000ec81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ec86  nop
0x18000ec87  lea     rcx, [rbp+var_10]
0x18000ec8b  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000ec90  jmp     short loc_18000EC36
0x18000ec92  xor     edi, edi
0x18000ec94  cmp     dword ptr [rbp+arg_0], edi
0x18000ec97  jle     short loc_18000ED12
0x18000ec99  mov     [rbp+arg_10], 0
0x18000eca0  mov     rax, [rbx]
0x18000eca3  mov     [rbp+var_8], 0
0x18000ecab  lea     r8, [rbp+var_8]
0x18000ecaf  mov     edx, edi
0x18000ecb1  mov     rcx, rbx
0x18000ecb4  mov     rax, [rax+38h]
0x18000ecb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecbd  test    eax, eax
0x18000ecbf  js      short loc_18000ED02
0x18000ecc1  mov     rcx, [rbp+var_8]
0x18000ecc5  mov     rax, [rcx]
0x18000ecc8  lea     rdx, [rbp+arg_10]
0x18000eccc  mov     rax, [rax+190h]
0x18000ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd8  test    eax, eax
0x18000ecda  js      short loc_18000ED02
0x18000ecdc  cmp     [rbp+arg_10], 3
0x18000ece0  jnz     short loc_18000ED02
0x18000ece2  mov     [rbp+arg_18], 0
0x18000ece9  mov     rcx, [rbp+var_10]
0x18000eced  mov     rax, [rcx]
0x18000ecf0  lea     r8, [rbp+arg_18]
0x18000ecf4  mov     rdx, [rbp+var_8]
0x18000ecf8  mov     rax, [rax+60h]
0x18000ecfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed01  nop
0x18000ed02  lea     rcx, [rbp+var_8]
0x18000ed06  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000ed0b  inc     edi
0x18000ed0d  cmp     edi, dword ptr [rbp+arg_0]
0x18000ed10  jl      short loc_18000EC99
0x18000ed12  mov     rax, [rbp+var_10]
0x18000ed16  mov     [rbp+var_10], 0
0x18000ed1e  mov     [rsi], rax
0x18000ed21  lea     rcx, [rbp+var_10]
0x18000ed25  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000ed2a  jmp     short loc_18000ED3B
0x18000ed2c  mov     [rsi], rbx
0x18000ed2f  mov     rax, [rbx]
0x18000ed32  mov     rax, [rax+8]
0x18000ed36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed3b  xor     eax, eax
0x18000ed3d  mov     rbx, [rsp+40h+arg_8]
0x18000ed42  add     rsp, 40h
0x18000ed46  pop     rdi
0x18000ed47  pop     rsi
0x18000ed48  pop     rbp
0x18000ed49  retn
```
