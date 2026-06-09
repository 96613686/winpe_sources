# Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTLauncher,Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong &,bool &>(Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong &,bool &)

- ea: `0x18000f4dc`
- end: `0x18000f585`
- name: `??$Make@VCCBTLauncher@ShellExtension@IoT@Microsoft@@AEAPEAUILauncherControl@234@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@AEAKAEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@12@AEAPEAUILauncherControl@ShellExtension@IoT@2@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@AEAKAEA_N@Z`
- size: `169`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *, _QWORD *, int *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011290`

## callees

- `0x180002f60`
- `0x180007dd0`
- `0x18000a9f4`
- `0x18000f4dc`
- `0x18001029c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTLauncher,Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,unsigned long &,bool &>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3,
        int *a4,
        char *a5)
{
  void *v9; // rax
  __int64 v10; // rdi
  _QWORD v12[8]; // [rsp+38h] [rbp-40h] BYREF

  *a1 = 0;
  v9 = operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
  v12[0] = v9;
  v12[1] = v9;
  if ( v9 )
  {
    v12[2] = v9;
    v10 = Microsoft::IoT::ShellExtension::CCBTLauncher::CCBTLauncher((__int64)v9, *a2, a3, *a4, *a5);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(*a1);
    *a1 = v10;
    v12[0] = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(v12);
  return a1;
}

```

## disassembly

```asm
0x18000f4dc  mov     [rsp+arg_0], rcx
0x18000f4e1  push    rbx
0x18000f4e2  push    rsi
0x18000f4e3  push    rdi
0x18000f4e4  push    r14
0x18000f4e6  sub     rsp, 58h
0x18000f4ea  mov     rdi, r9
0x18000f4ed  mov     rsi, r8
0x18000f4f0  mov     r14, rdx
0x18000f4f3  mov     rbx, rcx
0x18000f4f6  mov     [rsp+78h+var_48], 0
0x18000f4fe  mov     qword ptr [rcx], 0
0x18000f505  mov     [rsp+78h+var_48], 1
0x18000f50d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f514  mov     ecx, 0D8h; unsigned __int64
0x18000f519  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f51e  mov     [rsp+78h+var_40], rax
0x18000f523  mov     [rsp+78h+var_38], rax
0x18000f528  test    rax, rax
0x18000f52b  jz      short loc_18000F56D
0x18000f52d  mov     [rsp+78h+var_30], rax
0x18000f532  mov     rcx, [rsp+78h+arg_20]
0x18000f53a  mov     dl, [rcx]
0x18000f53c  mov     [rsp+78h+var_58], dl
0x18000f540  mov     r9d, [rdi]
0x18000f543  mov     r8, rsi
0x18000f546  mov     rdx, [r14]
0x18000f549  mov     rcx, rax
0x18000f54c  call    ??0CCBTLauncher@ShellExtension@IoT@Microsoft@@QEAA@PEAUILauncherControl@123@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@K_N@Z; Microsoft::IoT::ShellExtension::CCBTLauncher::CCBTLauncher(Microsoft::IoT::ShellExtension::ILauncherControl *,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong,bool)
0x18000f551  mov     rdi, rax
0x18000f554  mov     rcx, [rbx]
0x18000f557  test    rcx, rcx
0x18000f55a  jz      short loc_18000F561
0x18000f55c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VFtmBase@23@UILauncherControl@ShellExtension@IoT@3@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,Microsoft::IoT::ShellExtension::ILauncherControl>::Release(void)
0x18000f561  mov     [rbx], rdi
0x18000f564  mov     [rsp+78h+var_40], 0
0x18000f56d  lea     rcx, [rsp+78h+var_40]
0x18000f572  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x18000f577  mov     rax, rbx
0x18000f57a  add     rsp, 58h
0x18000f57e  pop     r14
0x18000f580  pop     rdi
0x18000f581  pop     rsi
0x18000f582  pop     rbx
0x18000f583  retn
```
