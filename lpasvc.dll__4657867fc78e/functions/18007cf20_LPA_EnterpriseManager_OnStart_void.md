# LPA::EnterpriseManager::OnStart(void)

- ea: `0x18007cf20`
- end: `0x18007d077`
- name: `?OnStart@EnterpriseManager@LPA@@UEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(LPA::EnterpriseManager *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017c8`
- `0x18000df90`
- `0x18006ba8c`
- `0x18006d8d0`
- `0x180071650`
- `0x180071a34`
- `0x180076d0c`
- `0x180079c60`
- `0x18007ba00`
- `0x18007c304`
- `0x18007cf20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cf7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007cf7e`

## string_xrefs

- `0x18007cf5b`: `LpaServiceEnterpriseManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::EnterpriseManager::OnStart(LPA::EnterpriseManager *this)
{
  char *v2; // rsi
  int LastErrorToHResultAndForceFailure; // edi
  HANDLE EventW; // rax
  CommonUtil *v5; // rcx
  __int64 v6; // rdx
  int LpasvcPersistentSettingsKey; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // [rsp+40h] [rbp-19h] BYREF
  const char *v14; // [rsp+48h] [rbp-11h] BYREF
  const char *v15; // [rsp+50h] [rbp-9h] BYREF
  _OWORD v16[2]; // [rsp+58h] [rbp-1h] BYREF

  v2 = (char *)this + 40;
  if ( *((_DWORD *)this + 10) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    LastErrorToHResultAndForceFailure = 0;
    LPA::Util::SetRunningState((char *)this + 40, 1, "LpaServiceEnterpriseManager");
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 48,
      EventW);
    if ( *((_QWORD *)this + 6)
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v5),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      v16[0] = 0;
      v16[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v16[0]) = 0;
      LpasvcPersistentSettingsKey = CommonUtil::GetLpasvcPersistentSettingsKey((__int64)v5, (__int64)v16);
      if ( LpasvcPersistentSettingsKey < 0 )
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          v13 = LpasvcPersistentSettingsKey;
          v14 = "LPA::EnterpriseManager::OnStart";
          v15 = "LpaServiceEnterpriseManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            LpasvcPersistentSettingsKey,
            (unsigned int)byte_18012BD0B,
            v8,
            v9,
            (__int64)&v15,
            (__int64)&v14,
            (__int64)&v13);
        }
      }
      else
      {
        std::wstring::operator=((char *)this + 144, v16);
      }
      std::wstring::_Tidy_deallocate(v16);
      LPA::EnterpriseManager::LoadEsimDetailsFromRegistry(this);
      LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry(this, v10, v11);
      v6 = 2;
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 48,
        0);
      v6 = 0;
    }
    LPA::Util::SetRunningState(v2, v6, "LpaServiceEnterpriseManager");
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x18007cf20  push    rbp
0x18007cf22  push    rbx
0x18007cf23  push    rsi
0x18007cf24  push    rdi
0x18007cf25  push    r14
0x18007cf27  push    r15
0x18007cf29  lea     rbp, [rsp-2Fh]
0x18007cf2e  sub     rsp, 88h
0x18007cf35  mov     rax, cs:__security_cookie
0x18007cf3c  xor     rax, rsp
0x18007cf3f  mov     [rbp+57h+var_38], rax
0x18007cf43  mov     rbx, rcx
0x18007cf46  lea     rsi, [rcx+28h]
0x18007cf4a  cmp     dword ptr [rsi], 0
0x18007cf4d  jz      short loc_18007CF59
0x18007cf4f  mov     edi, 8007139Fh
0x18007cf54  jmp     loc_18007D059
0x18007cf59  xor     edi, edi
0x18007cf5b  lea     r15, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007cf62  mov     r8, r15
0x18007cf65  lea     edx, [rdi+1]
0x18007cf68  mov     rcx, rsi
0x18007cf6b  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x18007cf70  lea     r14, [rbx+30h]
0x18007cf74  xor     r9d, r9d; lpName
0x18007cf77  xor     r8d, r8d; bInitialState
0x18007cf7a  xor     edx, edx; bManualReset
0x18007cf7c  xor     ecx, ecx; lpEventAttributes
0x18007cf7e  call    cs:__imp_CreateEventW
0x18007cf84  mov     rdx, rax
0x18007cf87  mov     rcx, r14
0x18007cf8a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007cf8f  cmp     [r14], rdi
0x18007cf92  jnz     short loc_18007CFB0
0x18007cf94  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x18007cf99  mov     edi, eax
0x18007cf9b  test    eax, eax
0x18007cf9d  jns     short loc_18007CFB0
0x18007cf9f  xor     edx, edx
0x18007cfa1  mov     rcx, r14
0x18007cfa4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007cfa9  xor     edx, edx
0x18007cfab  jmp     loc_18007D04E
0x18007cfb0  xorps   xmm0, xmm0
0x18007cfb3  movups  [rbp+57h+var_58], xmm0
0x18007cfb7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007cfbf  movdqu  [rbp+57h+var_48], xmm1
0x18007cfc4  xor     eax, eax
0x18007cfc6  mov     word ptr [rbp+57h+var_58], ax
0x18007cfca  lea     rdx, [rbp+57h+var_58]
0x18007cfce  call    ?GetLpasvcPersistentSettingsKey@CommonUtil@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetLpasvcPersistentSettingsKey(ushort const *,std::wstring &)
0x18007cfd3  mov     ecx, eax
0x18007cfd5  test    eax, eax
0x18007cfd7  js      short loc_18007CFEB
0x18007cfd9  lea     rcx, [rbx+90h]
0x18007cfe0  lea     rdx, [rbp+57h+var_58]
0x18007cfe4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007cfe9  jmp     short loc_18007D030
0x18007cfeb  mov     eax, cs:CallbackContext
0x18007cff1  cmp     eax, 3
0x18007cff4  jbe     short loc_18007D030
0x18007cff6  mov     [rbp+57h+var_70], ecx
0x18007cff9  lea     rax, aLpaEnterprisem_4; "LPA::EnterpriseManager::OnStart"
0x18007d000  mov     [rbp+57h+var_68], rax
0x18007d004  mov     [rbp+57h+var_60], r15
0x18007d008  lea     rax, [rbp+57h+var_70]
0x18007d00c  mov     [rsp+0B0h+var_80], rax
0x18007d011  lea     rax, [rbp+57h+var_68]
0x18007d015  mov     [rsp+0B0h+var_88], rax
0x18007d01a  lea     rax, [rbp+57h+var_60]
0x18007d01e  mov     [rsp+0B0h+var_90], rax
0x18007d023  lea     rdx, byte_18012BD0B
0x18007d02a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007d02f  nop
0x18007d030  lea     rcx, [rbp+57h+var_58]
0x18007d034  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007d039  mov     rcx, rbx; this
0x18007d03c  call    ?LoadEsimDetailsFromRegistry@EnterpriseManager@LPA@@AEAAXXZ; LPA::EnterpriseManager::LoadEsimDetailsFromRegistry(void)
0x18007d041  mov     rcx, rbx; this
0x18007d044  call    ?LoadStagedEsimDetailsFromRegistry@EnterpriseManager@LPA@@AEAAXXZ; LPA::EnterpriseManager::LoadStagedEsimDetailsFromRegistry(void)
0x18007d049  mov     edx, 2
0x18007d04e  mov     r8, r15
0x18007d051  mov     rcx, rsi
0x18007d054  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x18007d059  mov     eax, edi
0x18007d05b  mov     rcx, [rbp+57h+var_38]
0x18007d05f  xor     rcx, rsp; StackCookie
0x18007d062  call    __security_check_cookie
0x18007d067  add     rsp, 88h
0x18007d06e  pop     r15
0x18007d070  pop     r14
0x18007d072  pop     rdi
0x18007d073  pop     rsi
0x18007d074  pop     rbx
0x18007d075  pop     rbp
0x18007d076  retn
```
