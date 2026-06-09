# CGlobalConfigManager::RefreshRemoteProvidersAsync(void *)

- ea: `0x1800d63dc`
- end: `0x1800d64d1`
- name: `?RefreshRemoteProvidersAsync@CGlobalConfigManager@@QEAAXPEAX@Z`
- size: `245`
- prototype: `void(CGlobalConfigManager *__hidden this, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d6038`
- `0x1800d6360`
- `0x1800e4034`
- `0x1800ef5d0`

## callees

- `0x1800a1ea4`
- `0x1800bdab8`
- `0x1800d63dc`
- `0x1800dbccc`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d64a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d64b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d64a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d64b8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800d6422`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800d6422`

## string_xrefs

- `0x1800d642d`: `DuplicateToken failed`
- `0x1800d6439`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\GlobalConfigManager.cpp`
- `0x1800d644d`: `Scheduling task to refresh Geo+KV`
- `0x1800d645a`: `CGlobalConfigManager::RefreshRemoteProvidersAsync`

## pseudocode

```c
void __fastcall CGlobalConfigManager::RefreshRemoteProvidersAsync(CGlobalConfigManager *this, void *a2)
{
  unsigned int v3; // eax
  const char *v4; // [rsp+28h] [rbp-30h]
  CGlobalConfigManager *v5; // [rsp+30h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-20h]
  HANDLE v7; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = 0;
  if ( a2 )
  {
    v3 = DuplicateTokenEx(a2, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &v7);
    wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x177,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
      (const char *)v3,
      (int)"DuplicateToken failed",
      v4);
  }
  LogMessage(5u, "CGlobalConfigManager::RefreshRemoteProvidersAsync", 0x17Bu, "Scheduling task to refresh Geo+KV");
  hObject = v7;
  v5 = this;
  v7 = 0;
  COrderedTaskExecutor::QueueTask__CGlobalConfigManager::RefreshRemoteProvidersAsync_::_2_::_lambda_1___(
    (char *)this + 576,
    &v5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)v7 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v7);
}

```

## disassembly

```asm
0x1800d63dc  mov     r11, rsp
0x1800d63df  push    rbx
0x1800d63e0  sub     rsp, 50h
0x1800d63e4  mov     rax, cs:__security_cookie
0x1800d63eb  xor     rax, rsp
0x1800d63ee  mov     [rsp+58h+var_10], rax
0x1800d63f3  mov     qword ptr [r11-18h], 0
0x1800d63fb  mov     rax, rdx
0x1800d63fe  mov     rbx, rcx
0x1800d6401  test    rdx, rdx
0x1800d6404  jz      short loc_1800D644D
0x1800d6406  mov     r9d, 2; ImpersonationLevel
0x1800d640c  lea     rcx, [r11-18h]
0x1800d6410  mov     [r11-30h], rcx
0x1800d6414  xor     r8d, r8d; lpTokenAttributes
0x1800d6417  mov     rcx, rax; hExistingToken
0x1800d641a  mov     [r11-38h], r9d
0x1800d641e  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800d6422  call    cs:__imp_DuplicateTokenEx
0x1800d6428  mov     rcx, [rsp+58h]; this
0x1800d642d  lea     rdx, aDuplicatetoken; "DuplicateToken failed"
0x1800d6434  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800d6439  lea     r8, aCW1SSrcDeliver_112; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800d6440  mov     edx, 177h; void *
0x1800d6445  mov     r9d, eax; char *
0x1800d6448  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800d644d  lea     r9, aSchedulingTask; "Scheduling task to refresh Geo+KV"
0x1800d6454  mov     r8d, 17Bh; unsigned int
0x1800d645a  lea     rdx, aCglobalconfigm_7; "CGlobalConfigManager::RefreshRemoteProv"...
0x1800d6461  mov     ecx, 5; unsigned __int8
0x1800d6466  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800d646b  mov     rax, [rsp+58h+var_18]
0x1800d6470  lea     rcx, [rbx+240h]
0x1800d6477  lea     rdx, [rsp+58h+var_28]
0x1800d647c  mov     [rsp+58h+hObject], rax
0x1800d6481  mov     [rsp+58h+var_28], rbx
0x1800d6486  mov     [rsp+58h+var_18], 0
0x1800d648f  call    COrderedTaskExecutor__QueueTask__CGlobalConfigManager__RefreshRemoteProvidersAsync____2____lambda_1___
0x1800d6494  mov     rcx, [rsp+58h+hObject]; hObject
0x1800d6499  lea     rax, [rcx-1]
0x1800d649d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d64a1  ja      short loc_1800D64A9
0x1800d64a3  call    cs:__imp_CloseHandle
0x1800d64a9  mov     rcx, [rsp+58h+var_18]; hObject
0x1800d64ae  lea     rax, [rcx-1]
0x1800d64b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d64b6  ja      short loc_1800D64BE
0x1800d64b8  call    cs:__imp_CloseHandle
0x1800d64be  mov     rcx, [rsp+58h+var_10]
0x1800d64c3  xor     rcx, rsp; StackCookie
0x1800d64c6  call    __security_check_cookie
0x1800d64cb  add     rsp, 50h
0x1800d64cf  pop     rbx
0x1800d64d0  retn
```
