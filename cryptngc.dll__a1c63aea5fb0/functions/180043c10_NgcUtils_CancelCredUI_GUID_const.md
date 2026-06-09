# NgcUtils::CancelCredUI(_GUID const &)

- ea: `0x180043c10`
- end: `0x180043ceb`
- name: `?CancelCredUI@NgcUtils@@YAJAEBU_GUID@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800350e8`

## callees

- `0x180008ee4`
- `0x18000edb0`
- `0x1800158e0`
- `0x180029aec`
- `0x180043c10`
- `0x180043cf4`
- `0x180043e40`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180043c60`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180043c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::CancelCredUI(NgcUtils *this, const struct _GUID *a2)
{
  __int64 v2; // r8
  signed int CancellationEventName; // ebx
  const WCHAR *v4; // r8
  wil::details *v5; // rax
  void *v6; // rdx
  DWORD LastError; // eax
  DWORD v9; // [rsp+30h] [rbp-48h] BYREF
  wil::details *v10; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpName[4]; // [rsp+40h] [rbp-38h] BYREF

  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(lpName);
  CancellationEventName = NgcUtils::Detail::GetCancellationEventName(v2, lpName);
  if ( CancellationEventName >= 0 )
  {
    v4 = (const WCHAR *)lpName;
    if ( lpName[3] > (LPCWSTR)7 )
      v4 = lpName[0];
    v5 = (wil::details *)OpenEventW(2u, 0, v4);
    v10 = v5;
    if ( v5 )
    {
      wil::details::SetEvent(v5, v6);
    }
    else
    {
      LastError = GetLastError();
      CancellationEventName = LastError;
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v9 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)byte_18006386D,
          0,
          0,
          (__int64)&v9);
      }
      if ( CancellationEventName > 0 )
        CancellationEventName = (unsigned __int16)CancellationEventName | 0x80070000;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v10);
  }
  std::wstring::~wstring(lpName);
  return (unsigned int)CancellationEventName;
}

```

## disassembly

```asm
0x180043c10  push    rbx
0x180043c12  sub     rsp, 70h
0x180043c16  mov     rax, cs:__security_cookie
0x180043c1d  xor     rax, rsp
0x180043c20  mov     [rsp+78h+var_18], rax
0x180043c25  mov     r8, rcx
0x180043c28  lea     rcx, [rsp+78h+lpName]
0x180043c2d  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180043c32  nop
0x180043c33  lea     rdx, [rsp+78h+lpName]
0x180043c38  mov     rcx, r8
0x180043c3b  call    ?GetCancellationEventName@Detail@NgcUtils@@YAJAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::Detail::GetCancellationEventName(_GUID const &,std::wstring *)
0x180043c40  mov     ebx, eax
0x180043c42  test    eax, eax
0x180043c44  js      loc_180043CCC
0x180043c4a  lea     r8, [rsp+78h+lpName]
0x180043c4f  cmp     [rsp+78h+var_20], 7
0x180043c55  cmova   r8, [rsp+78h+lpName]; lpName
0x180043c5b  xor     edx, edx; bInheritHandle
0x180043c5d  lea     ecx, [rdx+2]; dwDesiredAccess
0x180043c60  call    cs:__imp_OpenEventW
0x180043c66  mov     [rsp+78h+var_40], rax
0x180043c6b  test    rax, rax
0x180043c6e  jnz     short loc_180043CB9
0x180043c70  call    cs:__imp_GetLastError
0x180043c76  mov     ebx, eax
0x180043c78  mov     ecx, cs:dword_18006E000
0x180043c7e  cmp     ecx, 2
0x180043c81  jbe     short loc_180043CAA
0x180043c83  mov     [rsp+78h+var_48], eax
0x180043c87  lea     rax, [rsp+78h+var_48]
0x180043c8c  mov     [rsp+78h+var_58], rax
0x180043c91  xor     r9d, r9d
0x180043c94  xor     r8d, r8d
0x180043c97  lea     rdx, byte_18006386D
0x180043c9e  lea     rcx, dword_18006E000
0x180043ca5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180043caa  test    ebx, ebx
0x180043cac  jle     short loc_180043CC1
0x180043cae  movzx   ebx, bx
0x180043cb1  or      ebx, 80070000h
0x180043cb7  jmp     short loc_180043CC1
0x180043cb9  mov     rcx, rax; this
0x180043cbc  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180043cc1  lea     rcx, [rsp+78h+var_40]
0x180043cc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180043ccb  nop
0x180043ccc  lea     rcx, [rsp+78h+lpName]
0x180043cd1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043cd6  mov     eax, ebx
0x180043cd8  mov     rcx, [rsp+78h+var_18]
0x180043cdd  xor     rcx, rsp; StackCookie
0x180043ce0  call    __security_check_cookie
0x180043ce5  add     rsp, 70h
0x180043ce9  pop     rbx
0x180043cea  retn
```
