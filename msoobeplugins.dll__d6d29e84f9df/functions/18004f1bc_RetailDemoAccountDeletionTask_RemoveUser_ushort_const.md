# RetailDemoAccountDeletionTask::RemoveUser(ushort const *)

- ea: `0x18004f1bc`
- end: `0x18004f29b`
- name: `?RemoveUser@RetailDemoAccountDeletionTask@@AEAAXPEBG@Z`
- size: `223`
- prototype: `void(RetailDemoAccountDeletionTask *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18004f2b0`

## callees

- `0x180018a04`
- `0x18001e9a4`
- `0x180023574`
- `0x18004efbc`
- `0x18004f128`
- `0x18004f170`
- `0x1800b8834`
- `0x1800bd2a8`

## import_xrefs

- `USERENV!DeleteProfileW` at `0x18004f214`
- `USERENV!DeleteProfileW` at `0x18004f214`
- `samcli!NetUserDel` at `0x18004f24f`
- `samcli!NetUserDel` at `0x18004f24f`

## string_xrefs

- `0x18004f229`: `Failed to delete retail demo user profile <%ws>`
- `0x18004f239`: `shell\oobe\machine\plugins\retaildemo\retaildemotasks.cpp`
- `0x18004f279`: `shell\oobe\machine\plugins\retaildemo\retaildemotasks.cpp`
- `0x18004f26a`: `Failed to remove retail demo account <%ws>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RetailDemoAccountDeletionTask::RemoveUser(
        RetailDemoAccountDeletionTask *this,
        const unsigned __int16 *a2)
{
  RetailDemoAccountDeletionTask *v3; // rcx
  BOOL v4; // eax
  DWORD v5; // eax
  int v6; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSidString; // [rsp+40h] [rbp+8h] BYREF

  lpSidString = 0;
  try
  {
    OOBEStartService(L"profsvc", 1);
    UnattendLogW(0, L"Removing previous retail demo user account %s", a2);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSidString,
      0);
    RetailDemoAccountDeletionTask::GetUserSidString(v3, a2, (unsigned __int16 **)&lpSidString);
    v4 = DeleteProfileW(lpSidString, 0, 0);
    wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x30,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
      (const char *)v4,
      (bool)"Failed to delete retail demo user profile <%ws>",
      (const char *)a2);
    v5 = NetUserDel(0, a2);
    v6 = NetpApiStatusToNtStatus(v5);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x31,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
      (const char *)(v6 | 0x10000000u),
      (int)"Failed to remove retail demo account <%ws>",
      (const char *)a2);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x32,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemotasks.cpp",
      v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSidString);
}

```

## disassembly

```asm
0x18004f1bc  mov     [rsp+lpSidString], rcx
0x18004f1c1  push    rbx
0x18004f1c2  sub     rsp, 30h
0x18004f1c6  mov     rbx, rdx
0x18004f1c9  mov     [rsp+38h+lpSidString], 0
0x18004f1d2  mov     dl, 1; bool
0x18004f1d4  lea     rcx, aProfsvc; "profsvc"
0x18004f1db  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x18004f1e0  mov     r8, rbx
0x18004f1e3  lea     rdx, aRemovingPrevio; "Removing previous retail demo user acco"...
0x18004f1ea  xor     ecx, ecx
0x18004f1ec  call    UnattendLogW
0x18004f1f1  xor     edx, edx
0x18004f1f3  lea     rcx, [rsp+38h+lpSidString]
0x18004f1f8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004f1fd  lea     r8, [rsp+38h+lpSidString]; unsigned __int16 **
0x18004f202  mov     rdx, rbx; unsigned __int16 *
0x18004f205  call    ?GetUserSidString@RetailDemoAccountDeletionTask@@AEAAXPEBGPEAPEAG@Z; RetailDemoAccountDeletionTask::GetUserSidString(ushort const *,ushort * *)
0x18004f20a  xor     r8d, r8d; lpComputerName
0x18004f20d  xor     edx, edx; lpProfilePath
0x18004f20f  mov     rcx, [rsp+38h+lpSidString]; lpSidString
0x18004f214  call    cs:__imp_DeleteProfileW
0x18004f21a  test    eax, eax
0x18004f21c  setnz   al
0x18004f21f  mov     rcx, [rsp+38h]; this
0x18004f224  mov     [rsp+38h+var_10], rbx; char *
0x18004f229  lea     rdx, aFailedToDelete_0; "Failed to delete retail demo user profi"...
0x18004f230  mov     qword ptr [rsp+38h+var_18], rdx; bool
0x18004f235  movzx   r9d, al; char *
0x18004f239  lea     r8, aShellOobeMachi_40; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004f240  mov     edx, 30h ; '0'; void *
0x18004f245  call    ?Log_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18004f24a  mov     rdx, rbx; username
0x18004f24d  xor     ecx, ecx; servername
0x18004f24f  call    cs:__imp_NetUserDel
0x18004f255  mov     ecx, eax
0x18004f257  call    NetpApiStatusToNtStatus
0x18004f25c  bts     eax, 1Ch
0x18004f260  mov     rcx, [rsp+38h]; this
0x18004f265  mov     [rsp+38h+var_10], rbx; char *
0x18004f26a  lea     rdx, aFailedToRemove_1; "Failed to remove retail demo account <%"...
0x18004f271  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18004f276  mov     r9d, eax; char *
0x18004f279  lea     r8, aShellOobeMachi_40; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004f280  mov     edx, 31h ; '1'; void *
0x18004f285  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004f28a  nop
0x18004f28b  lea     rcx, [rsp+38h+lpSidString]
0x18004f290  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f295  add     rsp, 30h
0x18004f299  pop     rbx
0x18004f29a  retn
```
