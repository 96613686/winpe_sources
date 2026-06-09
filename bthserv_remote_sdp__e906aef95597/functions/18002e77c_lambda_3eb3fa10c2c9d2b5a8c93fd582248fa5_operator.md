# _lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()

- ea: `0x18002e77c`
- end: `0x18002ea41`
- name: `_lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18002dcd0`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x180012004`
- `0x1800120b8`
- `0x18002e13c`
- `0x18002e77c`
- `0x180030f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e7ed`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e7ed`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e8a5`
- `deviceassociation!DafCloseAssociationContext` at `0x18002e8a5`
- `deviceassociation!DafStartRemoveAssociation` at `0x18002e80c`
- `deviceassociation!DafStartRemoveAssociation` at `0x18002e80c`
- `deviceassociation!DafCreateAssociationContext` at `0x18002e7ba`
- `deviceassociation!DafCreateAssociationContext` at `0x18002e7ba`

## string_xrefs

- `0x18002e92f`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002e9af`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002ea2f`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_UNKNOWN **__fastcall lambda_3eb3fa10c2c9d2b5a8c93fd582248fa5_::operator()(int **a1)
{
  char v2; // bl
  int v3; // r8d
  int v4; // edx
  int v5; // edx
  int v6; // r8d
  int Event; // eax
  __int64 v8; // r8
  __int64 v9; // rdx
  _UNKNOWN **result; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-58h]
  __int64 *v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  char v17; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  v19 = 0;
  v15 = &v19;
  v16 = 0;
  v2 = 1;
  v17 = 1;
  **a1 = DafCreateAssociationContext(*(_QWORD *)a1[1], 0, 0, 0, &v16);
  wil::details::out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&long DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>(&v15);
  v4 = **a1;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = v2;
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v12 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x247,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v12,
      v14);
  }
  ResetEvent(*((HANDLE *)a1[2] + 256));
  v5 = DafStartRemoveAssociation(
         v19,
         Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_RemoveAssociationCallback,
         a1[2]);
  **a1 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v2;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v13 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v13,
      v14);
  }
  Event = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[2]);
  v9 = (unsigned int)Event;
  **a1 = Event;
  if ( Event < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v2;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v11 = wil::verify_hresult<long>((unsigned int)**a1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v11,
      v14);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v2 = 0;
  result = &WPP_RECORDER_INITIALIZED;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    result = (_UNKNOWN **)WPP_RECORDER_AND_TRACE_SF_s(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v2,
                            v8,
                            *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( v19 )
    return (_UNKNOWN **)DafCloseAssociationContext(v19, v9, v8);
  return result;
}

```

## disassembly

```asm
0x18002e77c  mov     r11, rsp
0x18002e77f  mov     [r11+10h], rbx
0x18002e783  push    rdi
0x18002e784  sub     rsp, 70h
0x18002e788  mov     rdi, rcx
0x18002e78b  and     qword ptr [r11+8], 0
0x18002e790  lea     rax, [r11+8]
0x18002e794  mov     [r11-28h], rax
0x18002e798  and     qword ptr [r11-20h], 0
0x18002e79d  mov     bl, 1
0x18002e79f  mov     [rsp+78h+var_18], bl
0x18002e7a3  mov     rax, [rcx+8]
0x18002e7a7  lea     rcx, [r11-20h]
0x18002e7ab  mov     [r11-58h], rcx
0x18002e7af  xor     r9d, r9d
0x18002e7b2  xor     r8d, r8d
0x18002e7b5  xor     edx, edx
0x18002e7b7  mov     rcx, [rax]
0x18002e7ba  call    cs:__imp_DafCreateAssociationContext
0x18002e7c1  nop     dword ptr [rax+rax+00h]
0x18002e7c6  mov     rcx, [rdi]
0x18002e7c9  mov     [rcx], eax
0x18002e7cb  lea     rcx, [rsp+78h+var_28]
0x18002e7d0  call    ??1?$out_param_ptr_t@PEAPEAUDAF_ASSOCIATION_HANDLE__@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUDAF_ASSOCIATION_HANDLE__@@P6AJPEAU1@@Z$1?DafCloseAssociationContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>::~out_param_ptr_t<DAF_ASSOCIATION_HANDLE__ * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<DAF_ASSOCIATION_HANDLE__ *,long (*)(DAF_ASSOCIATION_HANDLE__ *),&DafCloseAssociationContext(DAF_ASSOCIATION_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,DAF_ASSOCIATION_HANDLE__ *,DAF_ASSOCIATION_HANDLE__ *,0,std::nullptr_t>>>>(void)
0x18002e7d5  mov     rax, [rdi]
0x18002e7d8  mov     edx, [rax]
0x18002e7da  test    edx, edx
0x18002e7dc  js      loc_18002E941
0x18002e7e2  mov     rcx, [rdi+10h]
0x18002e7e6  mov     rcx, [rcx+800h]; hEvent
0x18002e7ed  call    cs:__imp_ResetEvent
0x18002e7f4  nop     dword ptr [rax+rax+00h]
0x18002e7f9  mov     r8, [rdi+10h]
0x18002e7fd  lea     rdx, ?s_RemoveAssociationCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_RemoveAssociationCallback(void *,long)
0x18002e804  mov     rcx, [rsp+78h+arg_0]
0x18002e80c  call    cs:__imp_DafStartRemoveAssociation
0x18002e813  nop     dword ptr [rax+rax+00h]
0x18002e818  mov     edx, eax
0x18002e81a  mov     rcx, [rdi]
0x18002e81d  mov     [rcx], eax
0x18002e81f  test    eax, eax
0x18002e821  js      loc_18002E9C1
0x18002e827  mov     rcx, [rdi+10h]; this
0x18002e82b  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x18002e830  mov     edx, eax
0x18002e832  mov     rcx, [rdi]
0x18002e835  mov     [rcx], eax
0x18002e837  test    eax, eax
0x18002e839  js      loc_18002E8C1
0x18002e83f  lea     rax, WPP_GLOBAL_Control
0x18002e846  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e84d  cmp     rcx, rax
0x18002e850  jz      short loc_18002E858
0x18002e852  cmp     byte ptr [rcx+19h], 4
0x18002e856  jnb     short loc_18002E85A
0x18002e858  xor     bl, bl
0x18002e85a  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e861  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e868  setnz   r8b
0x18002e86c  test    bl, bl
0x18002e86e  jnz     short loc_18002E875
0x18002e870  test    r8b, r8b
0x18002e873  jz      short loc_18002E898
0x18002e875  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e87c  mov     [rsp+78h+var_40], rax
0x18002e881  mov     [rsp+78h+var_48], 3Eh ; '>'
0x18002e888  mov     r9, [rcx+28h]
0x18002e88c  mov     dl, bl
0x18002e88e  mov     rcx, [rcx+10h]
0x18002e892  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e897  nop
0x18002e898  mov     rcx, [rsp+78h+arg_0]
0x18002e8a0  test    rcx, rcx
0x18002e8a3  jz      short loc_18002E8B2
0x18002e8a5  call    cs:__imp_DafCloseAssociationContext
0x18002e8ac  nop     dword ptr [rax+rax+00h]
0x18002e8b1  nop
0x18002e8b2  mov     rbx, [rsp+78h+arg_8]
0x18002e8ba  add     rsp, 70h
0x18002e8be  pop     rdi
0x18002e8bf  retn
0x18002e8c1  lea     rax, WPP_GLOBAL_Control
0x18002e8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8cf  cmp     rcx, rax
0x18002e8d2  jz      short loc_18002E8DA
0x18002e8d4  cmp     byte ptr [rcx+19h], 2
0x18002e8d8  jnb     short loc_18002E8DC
0x18002e8da  xor     bl, bl
0x18002e8dc  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e8e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e8ea  setnz   r8b
0x18002e8ee  test    bl, bl
0x18002e8f0  jnz     short loc_18002E8F7
0x18002e8f2  test    r8b, r8b
0x18002e8f5  jz      short loc_18002E91D
0x18002e8f7  mov     [rsp+78h+var_30], edx
0x18002e8fb  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e902  mov     [rsp+78h+var_40], rax
0x18002e907  mov     [rsp+78h+var_48], 3Dh ; '='
0x18002e90e  mov     r9, [rcx+28h]
0x18002e912  mov     dl, bl
0x18002e914  mov     rcx, [rcx+10h]
0x18002e918  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002e91d  mov     rcx, [rdi]
0x18002e920  mov     ecx, [rcx]
0x18002e922  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e927  mov     r9d, eax; char *
0x18002e92a  mov     rcx, [rsp+78h]; this
0x18002e92f  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e936  mov     edx, 257h; void *
0x18002e93b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e941  lea     rax, WPP_GLOBAL_Control
0x18002e948  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e94f  cmp     rcx, rax
0x18002e952  jz      short loc_18002E95A
0x18002e954  cmp     byte ptr [rcx+19h], 2
0x18002e958  jnb     short loc_18002E95C
0x18002e95a  xor     bl, bl
0x18002e95c  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e963  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e96a  setnz   r8b
0x18002e96e  test    bl, bl
0x18002e970  jnz     short loc_18002E977
0x18002e972  test    r8b, r8b
0x18002e975  jz      short loc_18002E99D
0x18002e977  mov     [rsp+78h+var_30], edx
0x18002e97b  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e982  mov     [rsp+78h+var_40], rax
0x18002e987  mov     [rsp+78h+var_48], 3Bh ; ';'
0x18002e98e  mov     r9, [rcx+28h]
0x18002e992  mov     dl, bl
0x18002e994  mov     rcx, [rcx+10h]
0x18002e998  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002e99d  mov     rcx, [rdi]
0x18002e9a0  mov     ecx, [rcx]
0x18002e9a2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e9a7  mov     r9d, eax; char *
0x18002e9aa  mov     rcx, [rsp+78h]; this
0x18002e9af  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e9b6  mov     edx, 247h; void *
0x18002e9bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e9c1  lea     rax, WPP_GLOBAL_Control
0x18002e9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9cf  cmp     rcx, rax
0x18002e9d2  jz      short loc_18002E9DA
0x18002e9d4  cmp     byte ptr [rcx+19h], 2
0x18002e9d8  jnb     short loc_18002E9DC
0x18002e9da  xor     bl, bl
0x18002e9dc  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e9e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e9ea  setnz   r8b
0x18002e9ee  test    bl, bl
0x18002e9f0  jnz     short loc_18002E9F7
0x18002e9f2  test    r8b, r8b
0x18002e9f5  jz      short loc_18002EA1D
0x18002e9f7  mov     [rsp+78h+var_30], edx
0x18002e9fb  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ea02  mov     [rsp+78h+var_40], rax
0x18002ea07  mov     [rsp+78h+var_48], 3Ch ; '<'
0x18002ea0e  mov     r9, [rcx+28h]
0x18002ea12  mov     dl, bl
0x18002ea14  mov     rcx, [rcx+10h]
0x18002ea18  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002ea1d  mov     rcx, [rdi]
0x18002ea20  mov     ecx, [rcx]
0x18002ea22  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002ea27  mov     r9d, eax; char *
0x18002ea2a  mov     rcx, [rsp+78h]; this
0x18002ea2f  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002ea36  mov     edx, 250h; void *
0x18002ea3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
