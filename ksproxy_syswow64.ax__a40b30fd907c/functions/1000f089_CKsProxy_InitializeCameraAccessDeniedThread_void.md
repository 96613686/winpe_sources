# CKsProxy::InitializeCameraAccessDeniedThread(void)

- ea: `0x1000f089`
- end: `0x1000f143`
- name: `?InitializeCameraAccessDeniedThread@CKsProxy@@AAEJXZ`
- size: `186`
- prototype: `unsigned int __thiscall(CKsProxy *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1000cf60`

## callees

- `0x1000647a`
- `0x1000f089`
- `0x1000f693`
- `0x1000f6d4`
- `0x1000f70b`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000f0f9`
- `KERNEL32!GetLastError` at `0x1000f0f9`
- `KERNEL32!CreateThread` at `0x1000f0dd`
- `KERNEL32!CreateThread` at `0x1000f0dd`

## pseudocode

```c
unsigned int __thiscall CKsProxy::InitializeCameraAccessDeniedThread(CKsProxy *this)
{
  int v2; // eax
  int v3; // ebx
  HANDLE Thread; // eax
  signed int LastError; // eax
  unsigned int v7; // esi

  v2 = ((int (__thiscall *)(wil::unique_any_t<wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned int,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > *))_create___event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z)(&this->m_uhAccessDeniedEvent);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_SD(
        0x27u,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        this->m_pName,
        v2);
    return v3;
  }
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CKsProxy::AccessDeniedWaitThread, this, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall *)(void *),&int CloseHandle(void *)>>::reset(Thread);
  if ( this->m_uhAccessDeniedWaitThreadHandle.m_ptr && this->m_uhAccessDeniedWaitThreadHandle.m_ptr != (void *)-1 )
    return v3;
  LastError = GetLastError();
  v7 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v7 = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    WPP_SF_SD(
      0x28u,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      this->m_pName,
      v7);
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    &this->m_uhAccessDeniedEvent,
    0);
  return v7;
}

```

## disassembly

```asm
0x1000f089  mov     edi, edi
0x1000f08b  push    ebx
0x1000f08c  push    esi
0x1000f08d  push    edi
0x1000f08e  mov     edi, ecx
0x1000f090  sub     esp, 10h
0x1000f093  lea     ecx, [edi+17Ch]
0x1000f099  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJW4EventOptions@2@PBGPAU_SECURITY_ATTRIBUTES@@PA_N@Z
0x1000f09e  mov     ebx, eax
0x1000f0a0  test    ebx, ebx
0x1000f0a2  jns     short loc_1000F0CB
0x1000f0a4  mov     ecx, _WPP_GLOBAL_Control
0x1000f0aa  cmp     ecx, offset _WPP_GLOBAL_Control
0x1000f0b0  jz      short loc_1000F0F5
0x1000f0b2  push    ebx; char
0x1000f0b3  push    dword ptr [edi+3Ch]; int
0x1000f0b6  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000f0bb  push    dword ptr [ecx+14h]
0x1000f0be  push    dword ptr [ecx+10h]; LoggerHandle
0x1000f0c1  push    27h ; '''
0x1000f0c3  pop     ecx; MessageNumber
0x1000f0c4  call    _WPP_SF_SD@24; WPP_SF_SD(x,x,x,x,x,x)
0x1000f0c9  jmp     short loc_1000F0F5
0x1000f0cb  xor     eax, eax
0x1000f0cd  lea     esi, [edi+180h]
0x1000f0d3  push    eax; lpThreadId
0x1000f0d4  push    eax; dwCreationFlags
0x1000f0d5  push    edi; lpParameter
0x1000f0d6  push    offset ?AccessDeniedWaitThread@CKsProxy@@SGKPAV1@@Z; lpStartAddress
0x1000f0db  push    eax; dwStackSize
0x1000f0dc  push    eax; lpThreadAttributes
0x1000f0dd  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x1000f0e3  push    eax
0x1000f0e4  mov     ecx, esi
0x1000f0e6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6GHPAX@Z$1?CloseHandle@@YGH0@Z@details@wil@@@details@wil@@QAEXPAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1000f0eb  cmp     dword ptr [esi], 0
0x1000f0ee  jz      short loc_1000F0F9
0x1000f0f0  cmp     dword ptr [esi], 0FFFFFFFFh
0x1000f0f3  jz      short loc_1000F0F9
0x1000f0f5  mov     eax, ebx
0x1000f0f7  jmp     short loc_1000F13F
0x1000f0f9  call    ds:__imp__GetLastError@0; GetLastError()
0x1000f0ff  movzx   esi, ax
0x1000f102  or      esi, 80070000h
0x1000f108  test    eax, eax
0x1000f10a  cmovle  esi, eax
0x1000f10d  mov     eax, _WPP_GLOBAL_Control
0x1000f112  cmp     eax, offset _WPP_GLOBAL_Control
0x1000f117  jz      short loc_1000F130
0x1000f119  push    esi; char
0x1000f11a  push    dword ptr [edi+3Ch]; int
0x1000f11d  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000f122  push    dword ptr [eax+14h]
0x1000f125  push    dword ptr [eax+10h]; LoggerHandle
0x1000f128  push    28h ; '('
0x1000f12a  pop     ecx; MessageNumber
0x1000f12b  call    _WPP_SF_SD@24; WPP_SF_SD(x,x,x,x,x,x)
0x1000f130  push    0
0x1000f132  lea     ecx, [edi+17Ch]
0x1000f138  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1000f13d  mov     eax, esi
0x1000f13f  pop     edi
0x1000f140  pop     esi
0x1000f141  pop     ebx
0x1000f142  retn
```
