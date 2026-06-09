# CEfsMutexLock::Lock(void)

- ea: `0x18001fa4c`
- end: `0x18001fad7`
- name: `?Lock@CEfsMutexLock@@QEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(CEfsMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001fb44`

## callees

- `0x18000f4d8`
- `0x18000f604`
- `0x18001fa4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001fa6d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001fa6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fa9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fa9a`

## string_xrefs

- `0x18001fa5f`: `Local\WindowsSearchService_EfsRegKeysMutex`

## pseudocode

```c
__int64 __fastcall CEfsMutexLock::Lock(CEfsMutexLock *this)
{
  HANDLE v2; // rax
  wil::details *v3; // rcx
  unsigned int LastErrorFailHr; // ebx
  DWORD v5; // eax

  if ( *((_DWORD *)this + 2) )
    return (unsigned int)-2147467259;
  v2 = OpenMutexW(0x100000u, 0, L"Local\\WindowsSearchService_EfsRegKeysMutex");
  if ( v2 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      v2);
    LastErrorFailHr = 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
    if ( (LastErrorFailHr & 0x80000000) != 0 )
      return LastErrorFailHr;
  }
  v5 = WaitForSingleObject(*(HANDLE *)this, 0x7530u);
  if ( !v5 || v5 == 128 )
  {
    *((_DWORD *)this + 2) = 1;
    return LastErrorFailHr;
  }
  if ( v5 == 258 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      0);
    return (unsigned int)-2147467259;
  }
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001fa4c  mov     [rsp+arg_0], rbx
0x18001fa51  push    rdi
0x18001fa52  sub     rsp, 20h
0x18001fa56  cmp     dword ptr [rcx+8], 0
0x18001fa5a  mov     rdi, rcx
0x18001fa5d  jnz     short loc_18001FABC
0x18001fa5f  lea     r8, Name; "Local\\WindowsSearchService_EfsRegKeysM"...
0x18001fa66  xor     edx, edx; bInheritHandle
0x18001fa68  mov     ecx, 100000h; dwDesiredAccess
0x18001fa6d  call    cs:__imp_OpenMutexW
0x18001fa73  test    rax, rax
0x18001fa76  jz      short loc_18001FA87
0x18001fa78  mov     rdx, rax
0x18001fa7b  mov     rcx, rdi
0x18001fa7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fa83  xor     ebx, ebx
0x18001fa85  jmp     short loc_18001FA92
0x18001fa87  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001fa8c  mov     ebx, eax
0x18001fa8e  test    eax, eax
0x18001fa90  js      short loc_18001FACA
0x18001fa92  mov     rcx, [rdi]; hHandle
0x18001fa95  mov     edx, 7530h; dwMilliseconds
0x18001fa9a  call    cs:__imp_WaitForSingleObject
0x18001faa0  test    eax, eax
0x18001faa2  jz      short loc_18001FAC3
0x18001faa4  cmp     eax, 80h
0x18001faa9  jz      short loc_18001FAC3
0x18001faab  cmp     eax, 102h
0x18001fab0  jnz     short loc_18001FACA
0x18001fab2  xor     edx, edx
0x18001fab4  mov     rcx, rdi
0x18001fab7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fabc  mov     ebx, 80004005h
0x18001fac1  jmp     short loc_18001FACA
0x18001fac3  mov     dword ptr [rdi+8], 1
0x18001faca  mov     eax, ebx
0x18001facc  mov     rbx, [rsp+28h+arg_0]
0x18001fad1  add     rsp, 20h
0x18001fad5  pop     rdi
0x18001fad6  retn
```
