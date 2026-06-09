# CRupUserList::ForEachUserToken__lambda_aa0b0ee3689b7534866efe16f2ea56da___

- ea: `0x180017f4c`
- end: `0x180017fdc`
- name: `CRupUserList::ForEachUserToken__lambda_aa0b0ee3689b7534866efe16f2ea56da___`
- size: `144`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, CHiveUploadTaskHandler **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x1800077a0`
- `0x18000fca8`
- `0x180011534`
- `0x180017f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017f6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017f6d`

## string_xrefs

- `0x180017fa2`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CRupUserList::ForEachUserToken__lambda_aa0b0ee3689b7534866efe16f2ea56da___(
        RTL_SRWLOCK *a1,
        CHiveUploadTaskHandler **a2)
{
  void **v3; // rbx
  void **v4; // rdi
  int v5; // eax
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  AcquireSRWLockShared(&g_RupUserList);
  v10 = &g_RupUserList;
  v4 = (void **)*(&xmmword_18002DF98 + 1);
  v3 = (void **)xmmword_18002DF98;
  try
  {
    while ( v3 != v4 )
    {
      v5 = CHiveUploadTaskHandler::_UploadHive(*a2, *v3);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2A3,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
          (const char *)(unsigned int)v5);
      v3 += 3;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x7D, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180017f4c  mov     [rsp+arg_8], rbx
0x180017f51  mov     [rsp+arg_10], rsi
0x180017f56  mov     [rsp+arg_0], rcx
0x180017f5b  push    rdi; int
0x180017f5c  sub     rsp, 20h
0x180017f60  mov     rsi, rdx
0x180017f63  lea     rbx, ?g_RupUserList@@3VCRupUserList@@A; CRupUserList g_RupUserList
0x180017f6a  mov     rcx, rbx; SRWLock
0x180017f6d  call    cs:__imp_AcquireSRWLockShared
0x180017f73  mov     [rsp+28h+arg_0], rbx
0x180017f78  mov     rbx, qword ptr cs:xmmword_18002DF98
0x180017f7f  mov     rdi, qword ptr cs:xmmword_18002DF98+8
0x180017f86  cmp     rbx, rdi
0x180017f89  jz      short loc_180017FB9
0x180017f8b  mov     rdx, [rbx]; void *
0x180017f8e  mov     rcx, [rsi]; this
0x180017f91  call    ?_UploadHive@CHiveUploadTaskHandler@@AEAAJPEAX@Z; CHiveUploadTaskHandler::_UploadHive(void *)
0x180017f96  mov     rcx, [rsp+28h]; this
0x180017f9b  test    eax, eax
0x180017f9d  jns     short loc_180017FB3
0x180017f9f  mov     r9d, eax; char *
0x180017fa2  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180017fa9  mov     edx, 2A3h; void *
0x180017fae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017fb3  add     rbx, 18h
0x180017fb7  jmp     short loc_180017F86
0x180017fb9  lea     rcx, [rsp+28h+arg_0]
0x180017fbe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017fc3  xor     eax, eax
0x180017fc5  jmp     short loc_180017FCB
0x180017fc7  mov     eax, dword ptr [rsp+28h+arg_0]
0x180017fcb  mov     rbx, [rsp+28h+arg_8]
0x180017fd0  mov     rsi, [rsp+28h+arg_10]
0x180017fd5  add     rsp, 20h
0x180017fd9  pop     rdi
0x180017fda  retn
```
