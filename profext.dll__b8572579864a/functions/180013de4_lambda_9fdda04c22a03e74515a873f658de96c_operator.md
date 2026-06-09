# _lambda_9fdda04c22a03e74515a873f658de96c_::operator()

- ea: `0x180013de4`
- end: `0x1800140b4`
- name: `_lambda_9fdda04c22a03e74515a873f658de96c_::operator()`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e270`

## callees

- `0x180001854`
- `0x180001cfc`
- `0x180001e98`
- `0x180001ef0`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x180004c80`
- `0x180006760`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000f6cc`
- `0x180013de4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180013fa2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180013fa2`

## string_xrefs

- `0x180013e4d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180014058`: `Name %ls Sid %ls type %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_9fdda04c22a03e74515a873f658de96c_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  const char *v3; // r9
  int v4; // eax
  int UserSid; // edi
  unsigned int LastErrorMsg; // ebx
  int v8; // [rsp+20h] [rbp-30h]
  char *v9; // [rsp+28h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  PSID Sid; // [rsp+80h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp+40h] BYREF

  Sid = 0;
  TokenHandle = 0;
  v2 = StringCchLengthW(**(const unsigned __int16 ***)a1, 0x41u, (unsigned __int64 *)&TokenHandle);
  v4 = wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0xC69,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
         (const char *)v2,
         (__int64)"Name %ls type %d",
         v3);
  UserSid = v4;
  if ( v4 == -2147024809 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v8);
LABEL_10:
    if ( Sid )
      ResultFromHeapFree(Sid);
    return 2147942487LL;
  }
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v4,
      v8);
LABEL_5:
    if ( Sid )
      ResultFromHeapFree(Sid);
    return (unsigned int)UserSid;
  }
  if ( !TokenHandle )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC6D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls type %d",
      **(const char ***)a1,
      **(_DWORD **)(a1 + 8));
    goto LABEL_10;
  }
  TokenHandle = 0;
  UserSid = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0xE, &TokenHandle);
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC73,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)UserSid,
      (int)"Name %ls type %d",
      **(const char ***)a1,
      **(_DWORD **)(a1 + 8));
LABEL_15:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_5;
  }
  UserSid = GetUserSid(TokenHandle, &Sid);
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC75,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)UserSid,
      (int)"Name %ls type %d",
      **(const char ***)a1,
      **(_DWORD **)(a1 + 8));
    goto LABEL_15;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    UserSid = AppContainerRegistrationHelper::IsAppContainerProfilePresent(
                **(const char ***)a1,
                StringSid,
                **(_DWORD **)(a1 + 8),
                (const struct _GUID *)(*(_QWORD *)(a1 + 24) + 8LL),
                **(int ***)(a1 + 16));
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xC81,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)UserSid,
        (int)"Name %ls Sid %ls type %d",
        **(const char ***)a1,
        StringSid,
        **(_DWORD **)(a1 + 8),
        &Sid,
        1);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( Sid )
      ResultFromHeapFree(Sid);
    return 0;
  }
  else
  {
    LODWORD(v9) = **(_DWORD **)(a1 + 8);
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0xC78,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                     "Name %ls type %d",
                     **(const char ***)a1,
                     v9);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( Sid )
      ResultFromHeapFree(Sid);
    return LastErrorMsg;
  }
}

```

## disassembly

```asm
0x180013de4  push    rbp
0x180013de6  push    rbx
0x180013de7  push    rdi
0x180013de8  push    r12
0x180013dea  push    r14
0x180013dec  mov     rbp, rsp
0x180013def  sub     rsp, 50h
0x180013df3  mov     rbx, rcx
0x180013df6  mov     [rbp+Sid], 0
0x180013dfe  lea     rax, [rbp+Sid]
0x180013e02  mov     [rbp+var_10], rax
0x180013e06  mov     [rbp+var_8], 1
0x180013e0a  mov     [rbp+TokenHandle], 0
0x180013e12  mov     rax, [rcx+8]
0x180013e16  mov     r10d, [rax]
0x180013e19  mov     rax, [rcx]
0x180013e1c  mov     r9, [rax]
0x180013e1f  lea     r8, [rbp+TokenHandle]; unsigned __int64 *
0x180013e23  mov     edx, 41h ; 'A'; unsigned __int64
0x180013e28  mov     rcx, r9; unsigned __int16 *
0x180013e2b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180013e30  mov     rcx, [rbp+28h]; this
0x180013e34  mov     dword ptr [rsp+50h+var_20], r10d
0x180013e39  mov     [rsp+50h+var_28], r9; char *
0x180013e3e  lea     r12, aNameLsTypeD; "Name %ls type %d"
0x180013e45  mov     [rsp+50h+var_30], r12; int
0x180013e4a  mov     r9d, eax; char *
0x180013e4d  lea     r14, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013e54  mov     r8, r14; unsigned int
0x180013e57  mov     edx, 0C69h; void *
0x180013e5c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013e61  mov     edi, eax
0x180013e63  cmp     eax, 80070057h
0x180013e68  jnz     short loc_180013E80
0x180013e6a  mov     rcx, [rbp+28h]; this
0x180013e6e  mov     r9d, eax; char *
0x180013e71  mov     r8, r14; unsigned int
0x180013e74  mov     edx, 0C6Ah; void *
0x180013e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e7e  jmp     short loc_180013EE7
0x180013e80  test    edi, edi
0x180013e82  jns     short loc_180013EAE
0x180013e84  mov     rcx, [rbp+28h]; this
0x180013e88  mov     r9d, edi; char *
0x180013e8b  mov     r8, r14; unsigned int
0x180013e8e  mov     edx, 0C6Bh; void *
0x180013e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e98  nop
0x180013e99  mov     rcx, [rbp+Sid]; lpMem
0x180013e9d  test    rcx, rcx
0x180013ea0  jz      short loc_180013EA7
0x180013ea2  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180013ea7  mov     eax, edi
0x180013ea9  jmp     loc_1800140A7
0x180013eae  cmp     [rbp+TokenHandle], 0
0x180013eb3  jnz     short loc_180013EFF
0x180013eb5  mov     rax, [rbx+8]
0x180013eb9  mov     rdx, [rbx]
0x180013ebc  mov     rcx, [rbp+28h]; this
0x180013ec0  mov     eax, [rax]
0x180013ec2  mov     dword ptr [rsp+50h+var_20], eax
0x180013ec6  mov     rax, [rdx]
0x180013ec9  mov     [rsp+50h+var_28], rax; char *
0x180013ece  mov     [rsp+50h+var_30], r12; int
0x180013ed3  mov     r9d, 80070057h; char *
0x180013ed9  mov     r8, r14; unsigned int
0x180013edc  mov     edx, 0C6Dh; void *
0x180013ee1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013ee6  nop
0x180013ee7  mov     rcx, [rbp+Sid]; lpMem
0x180013eeb  test    rcx, rcx
0x180013eee  jz      short loc_180013EF5
0x180013ef0  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180013ef5  mov     eax, 80070057h
0x180013efa  jmp     loc_1800140A7
0x180013eff  mov     [rbp+TokenHandle], 0
0x180013f07  lea     rdx, [rbp+TokenHandle]; void **
0x180013f0b  mov     ecx, 0Eh; char *
0x180013f10  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x180013f15  mov     edi, eax
0x180013f17  test    eax, eax
0x180013f19  jns     short loc_180013F58
0x180013f1b  mov     rdx, [rbx+8]
0x180013f1f  mov     r8, [rbx]
0x180013f22  mov     edx, [rdx]
0x180013f24  mov     dword ptr [rsp+50h+var_20], edx
0x180013f28  mov     rdx, [r8]
0x180013f2b  mov     [rsp+50h+var_28], rdx; char *
0x180013f30  mov     edx, 0C73h; void *
0x180013f35  mov     r8, r14; unsigned int
0x180013f38  mov     r9d, edi; char *
0x180013f3b  mov     [rsp+50h+var_30], r12; int
0x180013f40  mov     rcx, [rbp+28h]; this
0x180013f44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013f49  nop
0x180013f4a  lea     rcx, [rbp+TokenHandle]
0x180013f4e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013f53  jmp     loc_180013E99
0x180013f58  lea     rdx, [rbp+Sid]; void **
0x180013f5c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180013f60  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180013f65  mov     edi, eax
0x180013f67  test    eax, eax
0x180013f69  jns     short loc_180013F87
0x180013f6b  mov     rdx, [rbx+8]
0x180013f6f  mov     r8, [rbx]
0x180013f72  mov     edx, [rdx]
0x180013f74  mov     dword ptr [rsp+50h+var_20], edx
0x180013f78  mov     rdx, [r8]
0x180013f7b  mov     [rsp+50h+var_28], rdx
0x180013f80  mov     edx, 0C75h
0x180013f85  jmp     short loc_180013F35
0x180013f87  mov     [rbp+StringSid], 0
0x180013f8f  xor     edx, edx
0x180013f91  lea     rcx, [rbp+StringSid]
0x180013f95  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013f9a  lea     rdx, [rbp+StringSid]; StringSid
0x180013f9e  mov     rcx, [rbp+Sid]; Sid
0x180013fa2  call    cs:__imp_ConvertSidToStringSidW
0x180013fa9  nop     dword ptr [rax+rax+00h]
0x180013fae  test    eax, eax
0x180013fb0  jnz     short loc_180014006
0x180013fb2  mov     rax, [rbx+8]
0x180013fb6  mov     rdx, [rbx]
0x180013fb9  mov     rcx, [rbp+28h]; this
0x180013fbd  mov     eax, [rax]
0x180013fbf  mov     dword ptr [rsp+50h+var_28], eax
0x180013fc3  mov     rax, [rdx]
0x180013fc6  mov     [rsp+50h+var_30], rax; char *
0x180013fcb  mov     r9, r12; char *
0x180013fce  mov     r8, r14; unsigned int
0x180013fd1  mov     edx, 0C78h; void *
0x180013fd6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180013fdb  mov     ebx, eax
0x180013fdd  lea     rcx, [rbp+StringSid]
0x180013fe1  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180013fe6  nop
0x180013fe7  lea     rcx, [rbp+TokenHandle]
0x180013feb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013ff0  nop
0x180013ff1  mov     rcx, [rbp+Sid]; lpMem
0x180013ff5  test    rcx, rcx
0x180013ff8  jz      short loc_180013FFF
0x180013ffa  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180013fff  mov     eax, ebx
0x180014001  jmp     loc_1800140A7
0x180014006  mov     rax, [rbx+10h]
0x18001400a  mov     r9, [rbx+18h]
0x18001400e  add     r9, 8
0x180014012  mov     r8, [rbx+8]
0x180014016  mov     rcx, [rbx]
0x180014019  mov     rax, [rax]
0x18001401c  mov     [rsp+50h+var_30], rax
0x180014021  mov     r8d, [r8]
0x180014024  mov     rdx, [rbp+StringSid]
0x180014028  mov     rcx, [rcx]
0x18001402b  call    ?IsAppContainerProfilePresent@AppContainerRegistrationHelper@@SAJPEBG0W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsAppContainerProfilePresent(ushort const *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *,int *)
0x180014030  mov     edi, eax
0x180014032  test    eax, eax
0x180014034  jns     short loc_180014083
0x180014036  mov     rdx, [rbx+8]
0x18001403a  mov     r8, [rbx]
0x18001403d  mov     rcx, [rbp+28h]; this
0x180014041  mov     edx, [rdx]
0x180014043  mov     [rsp+50h+var_18], edx
0x180014047  mov     rdx, [rbp+StringSid]
0x18001404b  mov     [rsp+50h+var_20], rdx
0x180014050  mov     rdx, [r8]
0x180014053  mov     [rsp+50h+var_28], rdx; char *
0x180014058  lea     rax, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x18001405f  mov     [rsp+50h+var_30], rax; int
0x180014064  mov     r9d, edi; char *
0x180014067  mov     r8, r14; unsigned int
0x18001406a  mov     edx, 0C81h; void *
0x18001406f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014074  nop
0x180014075  lea     rcx, [rbp+StringSid]
0x180014079  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001407e  jmp     loc_180013F4A
0x180014083  lea     rcx, [rbp+StringSid]
0x180014087  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001408c  nop
0x18001408d  lea     rcx, [rbp+TokenHandle]
0x180014091  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180014096  nop
0x180014097  mov     rcx, [rbp+Sid]; lpMem
0x18001409b  test    rcx, rcx
0x18001409e  jz      short loc_1800140A5
0x1800140a0  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800140a5  xor     eax, eax
0x1800140a7  add     rsp, 50h
0x1800140ab  pop     r14
0x1800140ad  pop     r12
0x1800140af  pop     rdi
0x1800140b0  pop     rbx
0x1800140b1  pop     rbp
0x1800140b2  retn
```
