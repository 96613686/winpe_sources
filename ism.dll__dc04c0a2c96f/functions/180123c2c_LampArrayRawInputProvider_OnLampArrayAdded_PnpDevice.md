# LampArrayRawInputProvider::OnLampArrayAdded(PnpDevice *)

- ea: `0x180123c2c`
- end: `0x180123f98`
- name: `?OnLampArrayAdded@LampArrayRawInputProvider@@QEAAJPEAVPnpDevice@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(LampArrayRawInputProvider *__hidden this, struct PnpDevice *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ca58`
- `0x1801243d4`

## callees

- `0x180030260`
- `0x180055b40`
- `0x180068400`
- `0x18007cfd0`
- `0x180089a1c`
- `0x18008ad10`
- `0x18008e2b4`
- `0x18008ead4`
- `0x1800baa74`
- `0x1800e16a0`
- `0x1800f0990`
- `0x1800f2448`
- `0x1801233a4`
- `0x180123428`
- `0x180123454`
- `0x180123c2c`
- `0x180124920`
- `0x1801258bc`
- `0x180125ab0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123cd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123d15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123d97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123cd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123d15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180123d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123dab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123dab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180123e05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180123e05`

## pseudocode

```c
__int64 __fastcall LampArrayRawInputProvider::OnLampArrayAdded(LampArrayRawInputProvider *this, struct PnpDevice *a2)
{
  LampArrayDevice **v4; // rax
  LampArrayRawInputProvider *v5; // r14
  LampArrayDevice **v6; // r12
  LampArrayRawInputProvider **v7; // rcx
  __int64 *i; // rbx
  int active; // eax
  unsigned int v10; // r14d
  HSTRING *p_string; // rcx
  int InterfacePath; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 *v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-39h]
  int v23; // [rsp+20h] [rbp-39h]
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  LampArrayDevice **v25; // [rsp+38h] [rbp-21h] BYREF
  char *v26; // [rsp+40h] [rbp-19h] BYREF
  char v27[16]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h]
  _BYTE v29[32]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( *((_DWORD *)a2 + 30) == 65625 )
  {
    v4 = (LampArrayDevice **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = (LampArrayRawInputProvider *)v4;
    if ( v4 )
    {
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      v25 = v4;
      v6 = v4 + 2;
      if ( LampArrayDevice::CreateAndInitialize(a2, v4 + 2) < 0 )
      {
        std::unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>::~unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>(&v25);
        return 1;
      }
      AcquireSRWLockExclusive((PSRWLOCK)this + 20);
      v26 = (char *)this + 160;
      v7 = (LampArrayRawInputProvider **)*((_QWORD *)this + 10);
      if ( *v7 != (LampArrayRawInputProvider *)((char *)this + 72) )
        __fastfail(3u);
      *(_QWORD *)v5 = (char *)this + 72;
      *((_QWORD *)v5 + 1) = v7;
      *v7 = v5;
      *((_QWORD *)this + 10) = v5;
      ++*((_DWORD *)this + 22);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v26);
      AcquireSRWLockExclusive((PSRWLOCK)this + 18);
      string = (HSTRING)((char *)this + 144);
      for ( i = (__int64 *)*((_QWORD *)this + 12); i != (__int64 *)((char *)this + 96); i = (__int64 *)*i )
      {
        LampArrayDevice::AddViewClient(*v6, (struct LampArrayEndpoint *)(i + 2));
        if ( *((_DWORD *)i + 6) == *((_DWORD *)this + 16) )
        {
          active = LampArrayRawInputProvider::SetActiveViewClient(this, *v6, (struct LampArrayEndpoint *)(i + 2));
          v10 = active;
          if ( active < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC8,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparrayrawinputprovider.cpp",
              (const char *)(unsigned int)active,
              v22);
            p_string = &string;
LABEL_12:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(p_string);
            goto LABEL_24;
          }
        }
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&string);
      AcquireSRWLockExclusive((PSRWLOCK)this + 19);
      v26 = (char *)this + 152;
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      InterfacePath = PnpDevice::GetInterfacePath(a2, &string);
      v10 = InterfacePath;
      if ( InterfacePath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparrayrawinputprovider.cpp",
          (const char *)(unsigned int)InterfacePath,
          v22);
        WindowsDeleteString(string);
        string = 0;
        p_string = (HSTRING *)&v26;
        goto LABEL_12;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v14 = (__int64 *)((char *)this + 368);
      std::wstring::wstring(v29, StringRawBuffer);
      std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Find_lower_bound<std::wstring>(
        (char *)this + 368,
        v27,
        v29);
      v15 = v28;
      if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                               v16,
                               v28,
                               v29) )
        v15 = *v14;
      std::wstring::_Tidy_deallocate(v29);
      if ( v15 != *v14 )
      {
        LampArrayDevice::SetAmbientPids(
          *v6,
          *(struct Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs **)(v15 + 64));
        v17 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned int>>>::_Extract(
                (char *)this + 368,
                v15);
        std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *>>>(
          v18,
          v17);
      }
      WindowsDeleteString(string);
      string = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v26);
      if ( !*((_BYTE *)this + 320) )
      {
        (*(void (__fastcall **)(_QWORD, __int64 (__fastcall *)(), LampArrayRawInputProvider *, __int64))(**((_QWORD **)this + 7) + 152LL))(
          *((_QWORD *)this + 7),
          lambda_15d270ed647e652b2d70a0e99e327c3c_::_lambda_invoker_cdecl_,
          this,
          3);
        *((_BYTE *)this + 320) = 1;
      }
      v25 = 0;
      v10 = 0;
    }
    else
    {
      v25 = 0;
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparrayrawinputprovider.cpp",
        (const char *)0x8007000ELL,
        v22);
    }
LABEL_24:
    std::unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>::~unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>(&v25);
    return v10;
  }
  else if ( IsEdition(0x1820u)
         && (v20 = ConsumerControlManager::QueueAddRemoveDevice(*((ConsumerControlManager **)this + 43), a2, 1),
             v21 = v20,
             v20 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\consumercontrolmanager.cpp",
      (const char *)(unsigned int)v20,
      v22);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\lamparrayrawinputprovider.cpp",
      (const char *)v21,
      v23);
    return v21;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180123c2c  mov     [rsp-8+arg_10], rbx
0x180123c31  mov     [rsp-8+arg_18], rsi
0x180123c36  push    rbp
0x180123c37  push    r12
0x180123c39  push    r13
0x180123c3b  push    r14
0x180123c3d  push    r15
0x180123c3f  lea     rbp, [rsp-37h]
0x180123c44  sub     rsp, 90h
0x180123c4b  mov     rax, cs:__security_cookie
0x180123c52  xor     rax, rsp
0x180123c55  mov     [rbp+57h+var_30], rax
0x180123c59  mov     r15, rdx
0x180123c5c  mov     rsi, rcx
0x180123c5f  mov     r13d, 1
0x180123c65  cmp     word ptr [rdx+78h], 59h ; 'Y'
0x180123c6a  jnz     loc_180123F13
0x180123c70  cmp     [rdx+7Ah], r13w
0x180123c75  jnz     loc_180123F13
0x180123c7b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180123c82  lea     ecx, [r13+17h]; unsigned __int64
0x180123c86  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180123c8b  mov     r14, rax
0x180123c8e  test    rax, rax
0x180123c91  jz      loc_180123EDF
0x180123c97  mov     qword ptr [rax], 0
0x180123c9e  mov     qword ptr [rax+8], 0
0x180123ca6  mov     qword ptr [rax+10h], 0
0x180123cae  mov     [rbp+57h+var_78], rax
0x180123cb2  lea     r12, [rax+10h]
0x180123cb6  mov     rdx, r12; struct LampArrayDevice **
0x180123cb9  mov     rcx, r15; struct PnpDevice *
0x180123cbc  call    ?CreateAndInitialize@LampArrayDevice@@SAJPEAVPnpDevice@@PEAPEAV1@@Z; LampArrayDevice::CreateAndInitialize(PnpDevice *,LampArrayDevice * *)
0x180123cc1  test    eax, eax
0x180123cc3  js      loc_180123ECE
0x180123cc9  lea     rbx, [rsi+0A0h]
0x180123cd0  mov     rcx, rbx; SRWLock
0x180123cd3  call    cs:__imp_AcquireSRWLockExclusive
0x180123cd9  mov     [rbp+57h+var_70], rbx
0x180123cdd  lea     rax, [rsi+48h]
0x180123ce1  mov     rcx, [rax+8]
0x180123ce5  cmp     [rcx], rax
0x180123ce8  jz      short loc_180123CF0
0x180123cea  lea     ecx, [r13+2]
0x180123cee  int     29h; Win8: RtlFailFast(ecx)
0x180123cf0  mov     [r14], rax
0x180123cf3  mov     [r14+8], rcx
0x180123cf7  mov     [rcx], r14
0x180123cfa  mov     [rax+8], r14
0x180123cfe  add     [rax+10h], r13d
0x180123d02  lea     rcx, [rbp+57h+var_70]
0x180123d06  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180123d0b  lea     rbx, [rsi+90h]
0x180123d12  mov     rcx, rbx; SRWLock
0x180123d15  call    cs:__imp_AcquireSRWLockExclusive
0x180123d1b  mov     [rbp+57h+string], rbx
0x180123d1f  lea     r13, [rsi+60h]
0x180123d23  mov     rbx, [r13+0]
0x180123d27  cmp     rbx, r13
0x180123d2a  jz      short loc_180123D84
0x180123d2c  lea     rdx, [rbx+10h]; struct LampArrayEndpoint *
0x180123d30  mov     rcx, [r12]; this
0x180123d34  call    ?AddViewClient@LampArrayDevice@@QEAAJPEAULampArrayEndpoint@@@Z; LampArrayDevice::AddViewClient(LampArrayEndpoint *)
0x180123d39  mov     eax, [rsi+40h]
0x180123d3c  nop
0x180123d3d  cmp     [rbx+18h], eax
0x180123d40  jnz     short loc_180123D59
0x180123d42  lea     r8, [rbx+10h]; struct LampArrayEndpoint *
0x180123d46  mov     rdx, [r12]; struct LampArrayDevice *
0x180123d4a  mov     rcx, rsi; this
0x180123d4d  call    ?SetActiveViewClient@LampArrayRawInputProvider@@AEAAJPEAVLampArrayDevice@@PEAULampArrayEndpoint@@@Z; LampArrayRawInputProvider::SetActiveViewClient(LampArrayDevice *,LampArrayEndpoint *)
0x180123d52  mov     r14d, eax
0x180123d55  test    eax, eax
0x180123d57  js      short loc_180123D5E
0x180123d59  mov     rbx, [rbx]
0x180123d5c  jmp     short loc_180123D27
0x180123d5e  mov     rcx, [rbp+5Fh]; this
0x180123d62  mov     r9d, eax; char *
0x180123d65  lea     r8, aOnecoreuapWind_201; "onecoreuap\\windows\\moderncore\\inputv"...
0x180123d6c  mov     edx, 0C8h; void *
0x180123d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123d76  lea     rcx, [rbp+57h+string]
0x180123d7a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180123d7f  jmp     loc_180123F05
0x180123d84  lea     rcx, [rbp+57h+string]
0x180123d88  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180123d8d  lea     rbx, [rsi+98h]
0x180123d94  mov     rcx, rbx; SRWLock
0x180123d97  call    cs:__imp_AcquireSRWLockExclusive
0x180123d9d  mov     [rbp+57h+var_70], rbx
0x180123da1  mov     [rbp+57h+string], 0
0x180123da9  xor     ecx, ecx; string
0x180123dab  call    cs:__imp_WindowsDeleteString
0x180123db1  mov     [rbp+57h+string], 0
0x180123db9  lea     rdx, [rbp+57h+string]; HSTRING *
0x180123dbd  mov     rcx, r15; this
0x180123dc0  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x180123dc5  mov     r14d, eax
0x180123dc8  test    eax, eax
0x180123dca  jns     short loc_180123DFF
0x180123dcc  mov     rcx, [rbp+5Fh]; this
0x180123dd0  mov     r9d, eax; char *
0x180123dd3  lea     r8, aOnecoreuapWind_201; "onecoreuap\\windows\\moderncore\\inputv"...
0x180123dda  mov     edx, 0D2h; void *
0x180123ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123de4  mov     rcx, [rbp+57h+string]; string
0x180123de8  call    cs:__imp_WindowsDeleteString
0x180123dee  mov     [rbp+57h+string], 0
0x180123df6  lea     rcx, [rbp+57h+var_70]
0x180123dfa  jmp     loc_180123D7A
0x180123dff  xor     edx, edx; length
0x180123e01  mov     rcx, [rbp+57h+string]; string
0x180123e05  call    cs:__imp_WindowsGetStringRawBuffer
0x180123e0b  lea     r14, [rsi+170h]
0x180123e12  mov     rdx, rax
0x180123e15  lea     rcx, [rbp+57h+var_50]
0x180123e19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180123e1e  lea     r8, [rbp+57h+var_50]
0x180123e22  lea     rdx, [rbp+57h+var_68]
0x180123e26  mov     rcx, r14
0x180123e29  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180123e2e  lea     r8, [rbp+57h+var_50]
0x180123e32  mov     rbx, [rbp+57h+var_58]
0x180123e36  mov     rdx, rbx
0x180123e39  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *> * const,std::wstring const &)
0x180123e3e  test    al, al
0x180123e40  jnz     short loc_180123E45
0x180123e42  mov     rbx, [r14]
0x180123e45  lea     rcx, [rbp+57h+var_50]
0x180123e49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123e4e  cmp     rbx, [r14]
0x180123e51  jz      short loc_180123E73
0x180123e53  mov     rdx, [rbx+40h]; struct Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs *
0x180123e57  mov     rcx, [r12]; this
0x180123e5b  call    ?SetAmbientPids@LampArrayDevice@@QEAAXPEAUIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@@Z; LampArrayDevice::SetAmbientPids(Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs *)
0x180123e60  mov     rdx, rbx
0x180123e63  mov     rcx, r14
0x180123e66  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKI@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKI@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKI@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,uint>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,uint>>>,std::_Iterator_base0>)
0x180123e6b  mov     rdx, rax
0x180123e6e  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIAmbientDeviceMappingChangedEventArgs@Internal@Lights@Devices@Windows@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,wil::com_ptr_t<Windows::Devices::Lights::Internal::IAmbientDeviceMappingChangedEventArgs,wil::err_returncode_policy>>,void *> *)
0x180123e73  mov     rcx, [rbp+57h+string]; string
0x180123e77  call    cs:__imp_WindowsDeleteString
0x180123e7d  mov     [rbp+57h+string], 0
0x180123e85  lea     rcx, [rbp+57h+var_70]
0x180123e89  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180123e8e  cmp     byte ptr [rsi+140h], 0
0x180123e95  jnz     short loc_180123EC1
0x180123e97  mov     rcx, [rsi+38h]
0x180123e9b  mov     rax, [rcx]
0x180123e9e  mov     r9d, 3
0x180123ea4  mov     r8, rsi
0x180123ea7  lea     rdx, _lambda_15d270ed647e652b2d70a0e99e327c3c____lambda_invoker_cdecl_
0x180123eae  mov     rax, [rax+98h]
0x180123eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123eba  mov     byte ptr [rsi+140h], 1
0x180123ec1  mov     [rbp+57h+var_78], 0
0x180123ec9  xor     r14d, r14d
0x180123ecc  jmp     short loc_180123F05
0x180123ece  lea     rcx, [rbp+57h+var_78]
0x180123ed2  call    ??1?$unique_ptr@UConsumerControlNexusDeviceListEntry@ConsumerControlManager@@U?$default_delete@UConsumerControlNexusDeviceListEntry@ConsumerControlManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>::~unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>(void)
0x180123ed7  mov     eax, r13d
0x180123eda  jmp     loc_180123F6F
0x180123edf  mov     [rbp+57h+var_78], 0
0x180123ee7  mov     rcx, [rbp+5Fh]; this
0x180123eeb  mov     r14d, 8007000Eh
0x180123ef1  mov     r9d, r14d; char *
0x180123ef4  lea     r8, aOnecoreuapWind_201; "onecoreuap\\windows\\moderncore\\inputv"...
0x180123efb  mov     edx, 0B5h; void *
0x180123f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123f05  lea     rcx, [rbp+57h+var_78]
0x180123f09  call    ??1?$unique_ptr@UConsumerControlNexusDeviceListEntry@ConsumerControlManager@@U?$default_delete@UConsumerControlNexusDeviceListEntry@ConsumerControlManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>::~unique_ptr<ConsumerControlManager::ConsumerControlNexusDeviceListEntry>(void)
0x180123f0e  mov     eax, r14d
0x180123f11  jmp     short loc_180123F6F
0x180123f13  mov     ecx, 1820h; unsigned __int64
0x180123f18  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x180123f1d  test    al, al
0x180123f1f  jz      short loc_180123F6D
0x180123f21  mov     r8b, r13b; bool
0x180123f24  mov     rdx, r15; struct PnpDevice *
0x180123f27  mov     rcx, [rsi+158h]; this
0x180123f2e  call    ?QueueAddRemoveDevice@ConsumerControlManager@@AEAAJPEAVPnpDevice@@_N@Z; ConsumerControlManager::QueueAddRemoveDevice(PnpDevice *,bool)
0x180123f33  mov     ebx, eax
0x180123f35  test    eax, eax
0x180123f37  jns     short loc_180123F6D
0x180123f39  mov     rcx, [rbp+5Fh]; this
0x180123f3d  mov     r9d, eax; char *
0x180123f40  lea     r8, aOnecoreuapWind_51; "onecoreuap\\windows\\moderncore\\inputv"...
0x180123f47  mov     edx, 84h; void *
0x180123f4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123f51  mov     rcx, [rbp+5Fh]; this
0x180123f55  mov     r9d, ebx; char *
0x180123f58  lea     r8, aOnecoreuapWind_201; "onecoreuap\\windows\\moderncore\\inputv"...
0x180123f5f  mov     edx, 0FDh; void *
0x180123f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123f69  mov     eax, ebx
0x180123f6b  jmp     short loc_180123F6F
0x180123f6d  xor     eax, eax
0x180123f6f  mov     rcx, [rbp+57h+var_30]
0x180123f73  xor     rcx, rsp; StackCookie
0x180123f76  call    __security_check_cookie
0x180123f7b  lea     r11, [rsp+0B0h+var_20]
0x180123f83  mov     rbx, [r11+40h]
0x180123f87  mov     rsi, [r11+48h]
0x180123f8b  mov     rsp, r11
0x180123f8e  pop     r15
0x180123f90  pop     r14
0x180123f92  pop     r13
0x180123f94  pop     r12
0x180123f96  pop     rbp
0x180123f97  retn
```
