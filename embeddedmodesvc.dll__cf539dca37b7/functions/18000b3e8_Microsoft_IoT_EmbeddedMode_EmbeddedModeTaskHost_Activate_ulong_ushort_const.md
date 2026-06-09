# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Activate(ulong,ushort const *)

- ea: `0x18000b3e8`
- end: `0x18000b589`
- name: `?Activate@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJKPEBG@Z`
- size: `417`
- prototype: `__int64 __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009690`

## callees

- `0x180005fc4`
- `0x180009f7c`
- `0x18000a060`
- `0x18000a2ac`
- `0x18000a68c`
- `0x18000a730`
- `0x18000aa70`
- `0x18000ab5c`
- `0x18000b3e8`
- `0x18000ba64`
- `0x18000bb44`
- `0x180011a1c`
- `0x180013284`
- `0x180014dfc`

## string_xrefs

- `0x18000b49c`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::Activate(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this,
        int a2,
        const unsigned __int16 *a3)
{
  int v3; // edi
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  Microsoft::IoT::ShellExtension::CCBT *v7; // rax
  Microsoft::IoT::ShellExtension::CCBT *v8; // rcx
  void *v10; // [rsp+20h] [rbp-30h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v11[2]; // [rsp+28h] [rbp-28h] BYREF
  Microsoft::IoT::ShellExtension::CCBT *v12[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  Microsoft::IoT::ShellExtension::CCBTLauncher *v15; // [rsp+78h] [rbp+28h] BYREF

  v15 = 0;
  v3 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession((__int64)this, a2, &v15);
  if ( v3 < 0 )
  {
LABEL_15:
    v5 = v3;
    goto LABEL_16;
  }
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(v12);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v10);
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
    v11,
    &v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  v4 = Microsoft::IoT::ShellExtension::CCBTLauncher::EnumEntryPoints(v11, v12);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 172;
    goto LABEL_9;
  }
  v7 = v12[0];
  v8 = v12[1];
  while ( v7 != v8 )
  {
    *(_WORD *)((char *)v7 + 79) = 1;
    v7 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v7 + 88);
  }
  v4 = Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 180;
    goto LABEL_9;
  }
  v4 = Microsoft::IoT::ShellExtension::CCBTLauncher::WaitForLaunchResults(v15);
  v5 = v4;
  if ( v4 >= 0 )
  {
    std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>((__int64)v11);
    if ( v12[0] )
    {
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v12[0], v12[1]);
      std::_Deallocate<16>((_QWORD *)v12[0], 8 * ((signed __int64)(v13 - (unsigned __int64)v12[0]) >> 3));
      *(_OWORD *)v12 = 0;
      v13 = 0;
    }
    goto LABEL_15;
  }
  v6 = 181;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
    (const char *)(unsigned int)v4,
    (int)v10);
  std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>((__int64)v11);
  if ( v12[0] )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v12[0], v12[1]);
    std::_Deallocate<16>((_QWORD *)v12[0], 8 * ((signed __int64)(v13 - (unsigned __int64)v12[0]) >> 3));
    *(_OWORD *)v12 = 0;
    v13 = 0;
  }
LABEL_16:
  Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(&v15);
  return v5;
}

```

## disassembly

```asm
0x18000b3e8  mov     [rsp-8+arg_0], rbx
0x18000b3ed  mov     [rsp-8+arg_8], rdi
0x18000b3f2  push    rbp
0x18000b3f3  mov     rbp, rsp
0x18000b3f6  sub     rsp, 50h
0x18000b3fa  mov     rbx, r8
0x18000b3fd  mov     [rbp+arg_18], 0
0x18000b405  lea     r8, [rbp+arg_18]
0x18000b409  call    ?LauncherFromSession@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@AEAAJKAEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@4@@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LauncherFromSession(ulong,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> &)
0x18000b40e  mov     edi, eax
0x18000b410  test    eax, eax
0x18000b412  js      loc_18000B56C
0x18000b418  lea     rcx, [rbp+var_18]
0x18000b41c  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000b421  nop
0x18000b422  mov     rdx, rbx
0x18000b425  lea     rcx, [rbp+var_30]
0x18000b429  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000b42e  nop
0x18000b42f  lea     rdx, [rbp+var_30]
0x18000b433  lea     rcx, [rbp+var_28]
0x18000b437  call    ??0?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000b43c  nop
0x18000b43d  lea     rcx, [rbp+var_30]
0x18000b441  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000b446  lea     rdx, [rbp+var_18]
0x18000b44a  lea     rcx, [rbp+var_28]
0x18000b44e  call    ?EnumEntryPoints@CCBTLauncher@ShellExtension@IoT@Microsoft@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::EnumEntryPoints(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,std::vector<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000b453  mov     ebx, eax
0x18000b455  test    eax, eax
0x18000b457  jns     short loc_18000B460
0x18000b459  mov     edx, 0ACh
0x18000b45e  jmp     short loc_18000B495
0x18000b460  mov     rax, [rbp+var_18]
0x18000b464  mov     rcx, [rbp+var_18+8]
0x18000b468  jmp     short loc_18000B474
0x18000b46a  mov     word ptr [rax+4Fh], 1
0x18000b470  add     rax, 58h ; 'X'
0x18000b474  cmp     rax, rcx
0x18000b477  jnz     short loc_18000B46A
0x18000b479  lea     r8, [rbp+var_28]
0x18000b47d  lea     rdx, [rbp+var_18]
0x18000b481  mov     rcx, [rbp+arg_18]; this
0x18000b485  call    ?Reactivate@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJAEBV?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::Reactivate(std::vector<Microsoft::IoT::ShellExtension::CCBT> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &)
0x18000b48a  mov     ebx, eax
0x18000b48c  test    eax, eax
0x18000b48e  jns     short loc_18000B501
0x18000b490  mov     edx, 0B4h; void *
0x18000b495  mov     rcx, [rbp+8]; this
0x18000b499  mov     r9d, eax; char *
0x18000b49c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4a8  nop
0x18000b4a9  lea     rcx, [rbp+var_28]
0x18000b4ad  call    ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
0x18000b4b2  nop
0x18000b4b3  mov     rcx, [rbp+var_18]; this
0x18000b4b7  test    rcx, rcx
0x18000b4ba  jz      loc_18000B56E
0x18000b4c0  mov     rdx, [rbp+var_18+8]
0x18000b4c4  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000b4c9  mov     rcx, [rbp+var_18]
0x18000b4cd  mov     rax, [rbp+var_8]
0x18000b4d1  sub     rax, rcx
0x18000b4d4  sar     rax, 3
0x18000b4d8  mov     rdx, 2E8BA2E8BA2E8BA3h
0x18000b4e2  imul    rax, rdx
0x18000b4e6  imul    rdx, rax, 58h ; 'X'
0x18000b4ea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b4ef  xorps   xmm0, xmm0
0x18000b4f2  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18000b4f7  mov     [rbp+var_8], 0
0x18000b4ff  jmp     short loc_18000B56E
0x18000b501  mov     rcx, [rbp+arg_18]; this
0x18000b505  call    ?WaitForLaunchResults@CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAAJXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::WaitForLaunchResults(void)
0x18000b50a  mov     ebx, eax
0x18000b50c  test    eax, eax
0x18000b50e  jns     short loc_18000B51A
0x18000b510  mov     edx, 0B5h
0x18000b515  jmp     loc_18000B495
0x18000b51a  lea     rcx, [rbp+var_28]
0x18000b51e  call    ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
0x18000b523  nop
0x18000b524  mov     rcx, [rbp+var_18]; this
0x18000b528  test    rcx, rcx
0x18000b52b  jz      short loc_18000B56C
0x18000b52d  mov     rdx, [rbp+var_18+8]
0x18000b531  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000b536  mov     rcx, [rbp+var_18]
0x18000b53a  mov     rax, [rbp+var_8]
0x18000b53e  sub     rax, rcx
0x18000b541  sar     rax, 3
0x18000b545  mov     rdx, 2E8BA2E8BA2E8BA3h
0x18000b54f  imul    rax, rdx
0x18000b553  imul    rdx, rax, 58h ; 'X'
0x18000b557  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000b55c  xorps   xmm0, xmm0
0x18000b55f  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18000b564  mov     [rbp+var_8], 0
0x18000b56c  mov     ebx, edi
0x18000b56e  lea     rcx, [rbp+arg_18]
0x18000b572  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x18000b577  mov     eax, ebx
0x18000b579  mov     rbx, [rsp+50h+arg_0]
0x18000b57e  mov     rdi, [rsp+50h+arg_8]
0x18000b583  add     rsp, 50h
0x18000b587  pop     rbp
0x18000b588  retn
```
