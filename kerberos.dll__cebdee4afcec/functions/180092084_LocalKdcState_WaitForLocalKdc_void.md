# LocalKdcState::WaitForLocalKdc(void)

- ea: `0x180092084`
- end: `0x1800921fa`
- name: `?WaitForLocalKdc@LocalKdcState@@YAJXZ`
- size: `374`
- prototype: `__int64 __fastcall(LocalKdcState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x18005d250`

## callees

- `0x180066628`
- `0x180075444`
- `0x180091a68`
- `0x180092084`
- `0x180092200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18009211f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180092140`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18009211f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180092140`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18009215a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18009218f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18009215a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18009218f`
- `ntdll!NtOpenEvent` at `0x180092103`
- `ntdll!NtOpenEvent` at `0x180092103`

## string_xrefs

- `0x1800921d5`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800920b3`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
__int64 __fastcall LocalKdcState::WaitForLocalKdc(LocalKdcState *this)
{
  NTSTATUS v2; // edi
  void *v3; // rbx
  DWORD v4; // eax
  const char *v5; // r9
  unsigned __int64 v6; // rcx
  _QWORD v7[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *EventHandle; // [rsp+80h] [rbp+20h] BYREF
  unsigned __int64 v11; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+90h] [rbp+30h] BYREF

  if ( dword_18014670C )
    return 0;
  if ( !LocalKdcState::IsLocalKdcSupported(this) )
    return 3221225659LL;
  v7[0] = 2752552;
  v7[1] = L"\\SAM_SERVICE_STARTED";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v7;
  memset(&ObjectAttributes.Attributes, 0, 24);
  EventHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  v2 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    v3 = EventHandle;
    v4 = WaitForSingleObjectEx(EventHandle, 0, 0);
    if ( v4 != 258 )
    {
      if ( v4 || WaitForSingleObjectEx(v3, 0, 0) )
        wil::details::in1diag3::FailFast_Unexpected(
          retaddr,
          (void *)0xB07,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v5);
      UnbiasedTime = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v6 = 0;
      while ( !dword_18014670C )
      {
        if ( v6 >= 0x7530 || !(unsigned __int8)wil::slim_event_t<1>::WaitForSignal(v6, (unsigned int)(30000 - v6)) )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
          return 258;
        }
        v11 = 0;
        QueryUnbiasedInterruptTime(&v11);
        v6 = (v11 - UnbiasedTime) / 0x2710;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
      return 0;
    }
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180092084  push    rbp
0x180092086  push    rbx
0x180092087  push    rdi
0x180092088  mov     rbp, rsp
0x18009208b  sub     rsp, 60h
0x18009208f  mov     eax, cs:dword_18014670C
0x180092095  test    eax, eax
0x180092097  jz      short loc_1800920A0
0x180092099  xor     eax, eax
0x18009209b  jmp     loc_1800921F2
0x1800920a0  call    ?IsLocalKdcSupported@LocalKdcState@@YA_NXZ; LocalKdcState::IsLocalKdcSupported(void)
0x1800920a5  test    al, al
0x1800920a7  jnz     short loc_1800920B3
0x1800920a9  mov     eax, 0C00000BBh
0x1800920ae  jmp     loc_1800921F2
0x1800920b3  lea     rax, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x1800920ba  mov     [rbp+var_40], 2A0028h
0x1800920c2  mov     [rbp+var_38], rax
0x1800920c6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800920ca  lea     rax, [rbp+var_40]
0x1800920ce  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800920d6  xorps   xmm0, xmm0
0x1800920d9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800920dd  mov     edx, 100000h; DesiredAccess
0x1800920e2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x1800920ea  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800920ee  mov     [rbp+EventHandle], 0
0x1800920f6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800920fe  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180092103  call    cs:__imp_NtOpenEvent
0x180092109  mov     edi, eax
0x18009210b  test    eax, eax
0x18009210d  js      loc_1800921E7
0x180092113  mov     rbx, [rbp+EventHandle]
0x180092117  xor     r8d, r8d; bAlertable
0x18009211a  mov     rcx, rbx; hHandle
0x18009211d  xor     edx, edx; dwMilliseconds
0x18009211f  call    cs:__imp_WaitForSingleObjectEx
0x180092125  cmp     eax, 102h
0x18009212a  jz      loc_1800921E7
0x180092130  test    eax, eax
0x180092132  jnz     loc_1800921D1
0x180092138  xor     r8d, r8d; bAlertable
0x18009213b  xor     edx, edx; dwMilliseconds
0x18009213d  mov     rcx, rbx; hHandle
0x180092140  call    cs:__imp_WaitForSingleObjectEx
0x180092146  test    eax, eax
0x180092148  jnz     loc_1800921D1
0x18009214e  lea     rcx, [rbp+UnbiasedTime]; UnbiasedTime
0x180092152  mov     [rbp+UnbiasedTime], 0
0x18009215a  call    cs:__imp_QueryUnbiasedInterruptTime
0x180092160  xor     ecx, ecx
0x180092162  mov     ebx, 7530h
0x180092167  mov     eax, cs:dword_18014670C
0x18009216d  test    eax, eax
0x18009216f  jnz     short loc_1800921C3
0x180092171  cmp     rcx, rbx
0x180092174  jnb     short loc_1800921B3
0x180092176  mov     edx, ebx
0x180092178  sub     edx, ecx
0x18009217a  call    ?WaitForSignal@?$slim_event_t@$00@wil@@AEAA_NK@Z; wil::slim_event_t<1>::WaitForSignal(ulong)
0x18009217f  test    al, al
0x180092181  jz      short loc_1800921B3
0x180092183  lea     rcx, [rbp+arg_8]; UnbiasedTime
0x180092187  mov     [rbp+arg_8], 0
0x18009218f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180092195  mov     rcx, [rbp+arg_8]
0x180092199  mov     rax, 346DC5D63886594Bh
0x1800921a3  sub     rcx, [rbp+UnbiasedTime]
0x1800921a7  mul     rcx
0x1800921aa  mov     rcx, rdx
0x1800921ad  shr     rcx, 0Bh
0x1800921b1  jmp     short loc_180092167
0x1800921b3  lea     rcx, [rbp+EventHandle]
0x1800921b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800921bc  mov     eax, 102h
0x1800921c1  jmp     short loc_1800921F2
0x1800921c3  lea     rcx, [rbp+EventHandle]
0x1800921c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800921cc  jmp     loc_180092099
0x1800921d1  mov     rcx, [rbp+18h]; this
0x1800921d5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800921dc  mov     edx, 0B07h; void *
0x1800921e1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800921e7  lea     rcx, [rbp+EventHandle]
0x1800921eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800921f0  mov     eax, edi
0x1800921f2  add     rsp, 60h
0x1800921f6  pop     rdi
0x1800921f7  pop     rbx
0x1800921f8  pop     rbp
0x1800921f9  retn
```
