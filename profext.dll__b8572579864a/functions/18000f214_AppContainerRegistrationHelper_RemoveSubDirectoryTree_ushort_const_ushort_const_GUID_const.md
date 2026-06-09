# AppContainerRegistrationHelper::RemoveSubDirectoryTree(ushort const *,ushort const *,_GUID const *)

- ea: `0x18000f214`
- end: `0x18000f413`
- name: `?RemoveSubDirectoryTree@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180015fe0`

## callees

- `0x180004030`
- `0x1800044e0`
- `0x180006760`
- `0x180006938`
- `0x18000a540`
- `0x18000f214`
- `0x18000f41c`
- `0x18000f440`
- `0x18000f614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f2df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f2df`

## string_xrefs

- `0x18000f281`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000f320`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000f374`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000f3dc`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000f3cd`: `Path %ls`
- `0x18000f30c`: `Root %ls subPath %ls len %Iu`
- `0x18000f2bc`: `subPath %ls`
- `0x18000f365`: `Root %ls subPath %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::RemoveSubDirectoryTree(
        char *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  int v6; // ebx
  unsigned __int64 v7; // r9
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // r8d
  unsigned __int64 v16; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int64 v18; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 v19; // [rsp+68h] [rbp+10h] BYREF

  v19 = 0;
  v18 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v6 = StringCchLengthW((const unsigned __int16 *)a1, 0x7FFFFFFFu, &v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCA9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v6,
      (int)"Root %ls",
      a1);
    return (unsigned int)v6;
  }
  v6 = StringCchLengthW(a2, v7, &v18);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCAA,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v6,
      (int)"subPath %ls",
      (const char *)a2);
    return (unsigned int)v6;
  }
  v9 = v18 + 2 + v19;
  v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
  v11 = v10;
  v18 = (unsigned __int64)v10;
  if ( v10 )
  {
    v12 = StringCchPrintfW(v10, v9, L"%s\\%s", a1, a2);
    if ( v12 >= 0 )
    {
      v13 = RemoveDirectoryTree(v11);
      v14 = v13;
      if ( v13 )
      {
        if ( (unsigned int)(v13 - 2) > 1 )
        {
          if ( v13 > 0 )
            v15 = (unsigned __int16)v13 | 0x80070000;
          else
            v15 = v13;
          AppContainerRegistrationHelper::LogFailureWithContext(&AppModelAppContainerDeleteFolderFailure, v11, v15, a3);
        }
        v12 = wil::details::in1diag3::Return_Win32Msg(
                retaddr,
                (void *)0xCBC,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)v14,
                (unsigned int)"Path %ls",
                (const char *)v11);
      }
      else
      {
        v12 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xCB1,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v12,
        (int)"Root %ls subPath %ls",
        a1,
        a2);
    }
  }
  else
  {
    v16 = v9;
    v12 = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCAE,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x8007000ELL,
      (int)"Root %ls subPath %ls len %Iu",
      a1,
      a2,
      v16);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f214  mov     rax, rsp
0x18000f217  mov     [rax+18h], rbx
0x18000f21b  mov     [rax+20h], rbp
0x18000f21f  push    rsi
0x18000f220  push    rdi
0x18000f221  push    r14
0x18000f223  sub     rsp, 40h
0x18000f227  mov     r14, r8
0x18000f22a  mov     rsi, rdx
0x18000f22d  mov     rbp, rcx
0x18000f230  mov     qword ptr [rax+10h], 0
0x18000f238  mov     qword ptr [rax+8], 0
0x18000f240  test    rcx, rcx
0x18000f243  jnz     short loc_18000F24A
0x18000f245  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f24a  test    rsi, rsi
0x18000f24d  jnz     short loc_18000F254
0x18000f24f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f254  lea     r8, [rsp+58h+arg_8]; unsigned __int64 *
0x18000f259  mov     r9d, 7FFFFFFFh
0x18000f25f  mov     edx, r9d; unsigned __int64
0x18000f262  mov     rcx, rbp; unsigned __int16 *
0x18000f265  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f26a  mov     ebx, eax
0x18000f26c  test    eax, eax
0x18000f26e  jns     short loc_18000F2A1
0x18000f270  mov     [rsp+58h+var_30], rbp; char *
0x18000f275  lea     rax, aRootLs; "Root %ls"
0x18000f27c  mov     edx, 0CA9h; void *
0x18000f281  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000f288  mov     r9d, ebx; char *
0x18000f28b  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000f290  mov     rcx, [rsp+58h]; this
0x18000f295  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000f29a  mov     eax, ebx
0x18000f29c  jmp     loc_18000F3FF
0x18000f2a1  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x18000f2a6  mov     rdx, r9; unsigned __int64
0x18000f2a9  mov     rcx, rsi; unsigned __int16 *
0x18000f2ac  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f2b1  mov     ebx, eax
0x18000f2b3  test    eax, eax
0x18000f2b5  jns     short loc_18000F2CA
0x18000f2b7  mov     [rsp+58h+var_30], rsi
0x18000f2bc  lea     rax, aSubpathLs; "subPath %ls"
0x18000f2c3  mov     edx, 0CAAh
0x18000f2c8  jmp     short loc_18000F281
0x18000f2ca  mov     rcx, [rsp+58h+arg_0]
0x18000f2cf  mov     rdi, [rsp+58h+arg_8]
0x18000f2d4  add     rcx, 2
0x18000f2d8  add     rdi, rcx
0x18000f2db  lea     rcx, [rdi+rdi]; cb
0x18000f2df  call    cs:__imp_CoTaskMemAlloc
0x18000f2e6  nop     dword ptr [rax+rax+00h]
0x18000f2eb  mov     rbx, rax
0x18000f2ee  mov     [rsp+58h+arg_0], rax
0x18000f2f3  test    rax, rax
0x18000f2f6  jnz     short loc_18000F336
0x18000f2f8  mov     rcx, [rsp+58h]; this
0x18000f2fd  mov     [rsp+58h+var_20], rdi
0x18000f302  mov     [rsp+58h+var_28], rsi
0x18000f307  mov     [rsp+58h+var_30], rbp; char *
0x18000f30c  lea     rax, aRootLsSubpathL; "Root %ls subPath %ls len %Iu"
0x18000f313  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000f318  mov     edi, 8007000Eh
0x18000f31d  mov     r9d, edi; char *
0x18000f320  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000f327  mov     edx, 0CAEh; void *
0x18000f32c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000f331  jmp     loc_18000F3F3
0x18000f336  mov     qword ptr [rsp+58h+var_38], rsi
0x18000f33b  mov     r9, rbp
0x18000f33e  lea     r8, aSS; "%s\\%s"
0x18000f345  mov     rdx, rdi; unsigned __int64
0x18000f348  mov     rcx, rbx; unsigned __int16 *
0x18000f34b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f350  mov     edi, eax
0x18000f352  test    eax, eax
0x18000f354  jns     short loc_18000F387
0x18000f356  mov     rcx, [rsp+58h]; this
0x18000f35b  mov     [rsp+58h+var_28], rsi
0x18000f360  mov     [rsp+58h+var_30], rbp; char *
0x18000f365  lea     rax, aRootLsSubpathL_0; "Root %ls subPath %ls"
0x18000f36c  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000f371  mov     r9d, edi; char *
0x18000f374  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000f37b  mov     edx, 0CB1h; void *
0x18000f380  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000f385  jmp     short loc_18000F3F3
0x18000f387  mov     rcx, rbx; unsigned __int16 *
0x18000f38a  call    RemoveDirectoryTree
0x18000f38f  mov     edi, eax
0x18000f391  test    eax, eax
0x18000f393  jz      short loc_18000F3F1
0x18000f395  lea     ecx, [rax-2]
0x18000f398  cmp     ecx, 1
0x18000f39b  jbe     short loc_18000F3C3
0x18000f39d  test    eax, eax
0x18000f39f  jg      short loc_18000F3A6
0x18000f3a1  mov     r8d, eax
0x18000f3a4  jmp     short loc_18000F3B1
0x18000f3a6  movzx   r8d, di
0x18000f3aa  or      r8d, 80070000h; int
0x18000f3b1  mov     r9, r14; struct _GUID *
0x18000f3b4  mov     rdx, rbx; unsigned __int16 *
0x18000f3b7  lea     rcx, AppModelAppContainerDeleteFolderFailure; struct _EVENT_DESCRIPTOR *
0x18000f3be  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000f3c3  mov     rcx, [rsp+58h]; this
0x18000f3c8  mov     [rsp+58h+var_30], rbx; char *
0x18000f3cd  lea     rax, aPathLs_0; "Path %ls"
0x18000f3d4  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18000f3d9  mov     r9d, edi; char *
0x18000f3dc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000f3e3  mov     edx, 0CBCh; void *
0x18000f3e8  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000f3ed  mov     edi, eax
0x18000f3ef  jmp     short loc_18000F3F3
0x18000f3f1  xor     edi, edi
0x18000f3f3  lea     rcx, [rsp+58h+arg_0]
0x18000f3f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000f3fd  mov     eax, edi
0x18000f3ff  mov     rbx, [rsp+58h+arg_10]
0x18000f404  mov     rbp, [rsp+58h+arg_18]
0x18000f409  add     rsp, 40h
0x18000f40d  pop     r14
0x18000f40f  pop     rdi
0x18000f410  pop     rsi
0x18000f411  retn
```
