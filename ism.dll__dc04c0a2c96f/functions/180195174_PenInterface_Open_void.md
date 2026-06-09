# PenInterface::Open(void)

- ea: `0x180195174`
- end: `0x18019529a`
- name: `?Open@PenInterface@@QEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(PenInterface *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800cf258`
- `0x1800df054`

## callees

- `0x18007dc50`
- `0x180082780`
- `0x18008daac`
- `0x1800f08d8`
- `0x1800f0990`
- `0x180195174`
- `0x180195794`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801951c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801951c8`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180195242`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180195242`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18019524f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18019524f`

## pseudocode

```c
__int64 __fastcall PenInterface::Open(PenInterface *this)
{
  char *v2; // rcx
  HANDLE FileW; // rax
  const char *v4; // r9
  __int64 v5; // rbx
  CONFIGRET v7; // eax
  DWORD v8; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-1D8h]
  _DWORD v10[4]; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v2 = (char *)this + 16;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(char **)v2;
  FileW = CreateFileW((LPCWSTR)v2, 0xC0000000, 3u, 0, 3u, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 56,
    FileW);
  v5 = *((_QWORD *)this + 7);
  if ( v5 == -1 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x62,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\api\\server\\peninterface.cpp",
             v4);
  memset_0(v10, 0, 0x1A0u);
  v10[0] = 416;
  v10[2] = 1;
  v11 = v5;
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  v7 = CM_Register_Notification(v10, this, &PenInterface::s_NotifyDeviceChanged, (char *)this + 64);
  v8 = CM_MapCrToWin32Err(v7, 0x507u);
  if ( v8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6D,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\api\\server\\peninterface.cpp",
             (const char *)v8,
             dwCreationDisposition);
  else
    return 0;
}

```

## disassembly

```asm
0x180195174  mov     [rsp+arg_8], rbx
0x180195179  push    rdi
0x18019517a  sub     rsp, 1F0h
0x180195181  mov     rax, cs:__security_cookie
0x180195188  xor     rax, rsp
0x18019518b  mov     [rsp+1F8h+var_18], rax
0x180195193  mov     rdi, rcx
0x180195196  add     rcx, 10h
0x18019519a  cmp     qword ptr [rcx+18h], 7
0x18019519f  jbe     short loc_1801951A4
0x1801951a1  mov     rcx, [rcx]; lpFileName
0x1801951a4  mov     [rsp+1F8h+hTemplateFile], 0; hTemplateFile
0x1801951ad  mov     r8d, 3; dwShareMode
0x1801951b3  mov     [rsp+1F8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801951bb  xor     r9d, r9d; lpSecurityAttributes
0x1801951be  mov     edx, 0C0000000h; dwDesiredAccess
0x1801951c3  mov     [rsp+1F8h+dwCreationDisposition], r8d; unsigned int
0x1801951c8  call    cs:__imp_CreateFileW
0x1801951ce  mov     rdx, rax
0x1801951d1  lea     rcx, [rdi+38h]
0x1801951d5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801951da  mov     rbx, [rdi+38h]
0x1801951de  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801951e2  jnz     short loc_1801951FD
0x1801951e4  mov     rcx, [rsp+1F8h]; this
0x1801951ec  lea     r8, aOnecoreuapWind_130; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801951f3  lea     edx, [rbx+63h]; void *
0x1801951f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801951fb  jmp     short loc_180195279
0x1801951fd  xor     edx, edx; Val
0x1801951ff  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x180195204  mov     r8d, 1A0h; Size
0x18019520a  call    memset_0
0x18019520f  xor     edx, edx
0x180195211  mov     [rsp+1F8h+var_1B8], 1A0h
0x180195219  lea     rcx, [rdi+40h]
0x18019521d  mov     [rsp+1F8h+var_1B0], 1
0x180195225  mov     [rsp+1F8h+var_1A8], rbx
0x18019522a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x18019522f  lea     r9, [rdi+40h]
0x180195233  mov     rdx, rdi
0x180195236  lea     r8, ?s_NotifyDeviceChanged@PenInterface@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; PenInterface::s_NotifyDeviceChanged(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18019523d  lea     rcx, [rsp+1F8h+var_1B8]
0x180195242  call    cs:__imp_CM_Register_Notification
0x180195248  mov     ecx, eax; CmReturnCode
0x18019524a  mov     edx, 507h; DefaultErr
0x18019524f  call    cs:__imp_CM_MapCrToWin32Err
0x180195255  test    eax, eax
0x180195257  jz      short loc_180195277
0x180195259  mov     rcx, [rsp+1F8h]; this
0x180195261  lea     r8, aOnecoreuapWind_130; "onecoreuap\\windows\\moderncore\\inputv"...
0x180195268  mov     r9d, eax; char *
0x18019526b  mov     edx, 6Dh ; 'm'; void *
0x180195270  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180195275  jmp     short loc_180195279
0x180195277  xor     eax, eax
0x180195279  mov     rcx, [rsp+1F8h+var_18]
0x180195281  xor     rcx, rsp; StackCookie
0x180195284  call    __security_check_cookie
0x180195289  mov     rbx, [rsp+1F8h+arg_8]
0x180195291  add     rsp, 1F0h
0x180195298  pop     rdi
0x180195299  retn
```
