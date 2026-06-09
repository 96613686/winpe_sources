# tip2::details::CreateAggregateKeyLock

- ea: `0x180025718`
- end: `0x1800257aa`
- name: `tip2::details::CreateAggregateKeyLock`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007bbc4`

## callees

- `0x1800104b0`
- `0x180010ea4`
- `0x180016a38`
- `0x180025718`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002573a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002573a`

## string_xrefs

- `0x180025728`: `Microsoft.Windows.Health.TestInProduction.RegistryStore.AggregateResults`

## pseudocode

```c
_QWORD *__fastcall tip2::details::CreateAggregateKeyLock(_QWORD *a1, _QWORD *a2)
{
  HANDLE Mutex; // rax
  __int64 *v5; // rax
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rcx
  char v10; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+48h] [rbp+10h] BYREF

  Mutex = CreateMutexExW(0, L"Microsoft.Windows.Health.TestInProduction.RegistryStore.AggregateResults", 0, 0x100000u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a2,
    Mutex);
  if ( *a2 )
  {
    v5 = (__int64 *)_acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
                      a2,
                      &v11);
    v6 = 1;
    v7 = 0;
    v8 = *v5;
  }
  else
  {
    v8 = 0;
    v5 = (__int64 *)&v10;
    v6 = 0;
    v7 = 2;
  }
  *a1 = v8;
  *v5 = 0;
  if ( v7 )
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v10);
  if ( v6 )
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v11);
  return a1;
}

```

## disassembly

```asm
0x180025718  mov     [rsp+arg_10], rbx
0x18002571d  push    rdi
0x18002571e  sub     rsp, 30h
0x180025722  mov     rbx, rdx
0x180025725  mov     rdi, rcx
0x180025728  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Health.TestInProducti"...
0x18002572f  xor     ecx, ecx; lpMutexAttributes
0x180025731  mov     r9d, 100000h; dwDesiredAccess
0x180025737  xor     r8d, r8d; dwFlags
0x18002573a  call    cs:__imp_CreateMutexExW
0x180025740  mov     rdx, rax
0x180025743  mov     rcx, rbx
0x180025746  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002574b  cmp     qword ptr [rbx], 0
0x18002574f  jz      short loc_18002576A
0x180025751  lea     rdx, [rsp+38h+arg_8]
0x180025756  mov     rcx, rbx
0x180025759  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002575e  mov     ebx, 1
0x180025763  xor     edx, edx
0x180025765  mov     rcx, [rax]
0x180025768  jmp     short loc_180025776
0x18002576a  xor     ecx, ecx
0x18002576c  lea     rax, [rsp+38h+arg_0]
0x180025771  xor     ebx, ebx
0x180025773  lea     edx, [rcx+2]
0x180025776  mov     [rdi], rcx
0x180025779  mov     qword ptr [rax], 0
0x180025780  test    edx, edx
0x180025782  jz      short loc_18002578E
0x180025784  lea     rcx, [rsp+38h+arg_0]
0x180025789  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18002578e  test    ebx, ebx
0x180025790  jz      short loc_18002579C
0x180025792  lea     rcx, [rsp+38h+arg_8]
0x180025797  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18002579c  mov     rbx, [rsp+38h+arg_10]
0x1800257a1  mov     rax, rdi
0x1800257a4  add     rsp, 30h
0x1800257a8  pop     rdi
0x1800257a9  retn
```
