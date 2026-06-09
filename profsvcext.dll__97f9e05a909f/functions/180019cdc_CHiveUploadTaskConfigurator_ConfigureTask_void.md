# CHiveUploadTaskConfigurator::_ConfigureTask(void)

- ea: `0x180019cdc`
- end: `0x180019dde`
- name: `?_ConfigureTask@CHiveUploadTaskConfigurator@@CAJXZ`
- size: `258`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`
- `0x18000f5f0`

## callees

- `0x180006a9c`
- `0x1800101f4`
- `0x180011534`
- `0x180019cdc`
- `0x180019de4`
- `0x180019e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019d6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019d6f`

## string_xrefs

- `0x180019dac`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 CHiveUploadTaskConfigurator::_ConfigureTask(void)
{
  int v0; // ebx
  __int64 v1; // rdx
  signed __int64 v2; // rbx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  LODWORD(v6) = 0;
  if ( (int)Profile::GetLocalSetting(14, &v6) < 0 )
    goto LABEL_4;
  if ( (_DWORD)v6 != 1 )
  {
    if ( (_DWORD)v6 == 2 )
    {
      LODWORD(v7) = 2;
      if ( (int)Profile::GetLocalSetting(15, (char *)&v7 + 4) >= 0 )
        goto LABEL_8;
    }
LABEL_4:
    v0 = CHiveUploadTaskConfigurator::_DisableTask();
    if ( v0 < 0 )
    {
      v1 = 341;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v1,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)v0,
        v4);
      return (unsigned int)v0;
    }
    return 0;
  }
  LODWORD(v7) = 1;
  if ( (int)Profile::GetLocalSetting(16, (char *)&v7 + 4) < 0 )
    goto LABEL_4;
LABEL_8:
  AcquireSRWLockShared(&g_RupUserList);
  v6 = &g_RupUserList;
  v2 = *(&xmmword_18002DF98 + 1) - xmmword_18002DF98;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  if ( v2 )
  {
    v0 = CHiveUploadTaskConfigurator::_EnableTask((struct CHiveUploadTaskSchedule *)&v7);
    if ( v0 < 0 )
    {
      v1 = 336;
      goto LABEL_11;
    }
  }
  else
  {
    v0 = CHiveUploadTaskConfigurator::_DisableTask();
    if ( v0 < 0 )
    {
      v1 = 332;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019cdc  push    rbx; int
0x180019cde  sub     rsp, 20h
0x180019ce2  lea     rdx, [rsp+28h+arg_0]
0x180019ce7  mov     [rsp+28h+arg_8], 0
0x180019cf0  mov     ecx, 0Eh
0x180019cf5  mov     dword ptr [rsp+28h+arg_0], 0
0x180019cfd  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180019d02  test    eax, eax
0x180019d04  js      short loc_180019D2D
0x180019d06  cmp     dword ptr [rsp+28h+arg_0], 1
0x180019d0b  jnz     short loc_180019D43
0x180019d0d  lea     rdx, [rsp+28h+arg_8+4]
0x180019d12  mov     dword ptr [rsp+28h+arg_8], 1
0x180019d1a  mov     ecx, 10h
0x180019d1f  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180019d24  not     eax
0x180019d26  shr     eax, 1Fh
0x180019d29  test    eax, eax
0x180019d2b  jnz     short loc_180019D65
0x180019d2d  call    ?_DisableTask@CHiveUploadTaskConfigurator@@CAJXZ; CHiveUploadTaskConfigurator::_DisableTask(void)
0x180019d32  mov     ebx, eax
0x180019d34  test    eax, eax
0x180019d36  jns     loc_180019DD6
0x180019d3c  mov     edx, 155h
0x180019d41  jmp     short loc_180019DA7
0x180019d43  cmp     dword ptr [rsp+28h+arg_0], 2
0x180019d48  jnz     short loc_180019D2D
0x180019d4a  lea     rdx, [rsp+28h+arg_8+4]
0x180019d4f  mov     dword ptr [rsp+28h+arg_8], 2
0x180019d57  mov     ecx, 0Fh
0x180019d5c  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEAKPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,ulong &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180019d61  test    eax, eax
0x180019d63  js      short loc_180019D2D
0x180019d65  lea     rbx, ?g_RupUserList@@3VCRupUserList@@A; CRupUserList g_RupUserList
0x180019d6c  mov     rcx, rbx; SRWLock
0x180019d6f  call    cs:__imp_AcquireSRWLockShared
0x180019d75  mov     [rsp+28h+arg_0], rbx
0x180019d7a  lea     rcx, [rsp+28h+arg_0]
0x180019d7f  mov     rbx, qword ptr cs:xmmword_18002DF98+8
0x180019d86  sub     rbx, qword ptr cs:xmmword_18002DF98
0x180019d8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019d92  test    rbx, rbx
0x180019d95  jnz     short loc_180019DBF
0x180019d97  call    ?_DisableTask@CHiveUploadTaskConfigurator@@CAJXZ; CHiveUploadTaskConfigurator::_DisableTask(void)
0x180019d9c  mov     ebx, eax
0x180019d9e  test    eax, eax
0x180019da0  jns     short loc_180019DD6
0x180019da2  mov     edx, 14Ch; void *
0x180019da7  mov     rcx, [rsp+28h]; this
0x180019dac  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019db3  mov     r9d, ebx; char *
0x180019db6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019dbb  mov     eax, ebx
0x180019dbd  jmp     short loc_180019DD8
0x180019dbf  lea     rcx, [rsp+28h+arg_8]; struct CHiveUploadTaskSchedule *
0x180019dc4  call    ?_EnableTask@CHiveUploadTaskConfigurator@@CAJAEAVCHiveUploadTaskSchedule@@@Z; CHiveUploadTaskConfigurator::_EnableTask(CHiveUploadTaskSchedule &)
0x180019dc9  mov     ebx, eax
0x180019dcb  test    eax, eax
0x180019dcd  jns     short loc_180019DD6
0x180019dcf  mov     edx, 150h
0x180019dd4  jmp     short loc_180019DA7
0x180019dd6  xor     eax, eax
0x180019dd8  add     rsp, 20h
0x180019ddc  pop     rbx
0x180019ddd  retn
```
