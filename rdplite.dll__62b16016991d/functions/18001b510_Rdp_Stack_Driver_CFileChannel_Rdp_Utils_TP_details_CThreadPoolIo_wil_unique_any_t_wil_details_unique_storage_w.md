# Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________::Open__Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___

- ea: `0x18001b510`
- end: `0x18001b690`
- name: `Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________::Open__Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___`
- size: `384`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18001c230`

## callees

- `0x1800036f0`
- `0x180003714`
- `0x18000fcac`
- `0x18000ffd4`
- `0x180012104`
- `0x180012144`
- `0x180018834`
- `0x180018a0c`
- `0x18001b3a0`
- `0x18001b510`
- `0x18001b970`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b564`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b564`

## string_xrefs

- `0x18001b59b`: `Failed to open channel: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Driver::CFileChannel_Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________::Open__Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___(
        __int64 a1,
        const WCHAR *a2)
{
  void *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // eax
  void *dwCreationDisposition; // [rsp+20h] [rbp-61h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-59h]
  PVOID v11[3]; // [rsp+40h] [rbp-41h] BYREF
  int v12; // [rsp+58h] [rbp-29h]
  GUID v13; // [rsp+5Ch] [rbp-25h]
  __int64 v14; // [rsp+6Ch] [rbp-15h]
  __int64 v15; // [rsp+74h] [rbp-Dh]
  __int64 v16; // [rsp+7Ch] [rbp-5h]
  __int64 v17; // [rsp+84h] [rbp+3h]
  int v18; // [rsp+8Ch] [rbp+Bh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+37h]

  v11[0] = CreateFileW(a2, 0x10000000u, 3u, 0, 4u, 0x40800080u, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1,
    v11);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v11);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x125,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
    (const char *)(((*(_QWORD *)a1 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
    (bool)"Failed to open channel: %s",
    (const char *)a2);
  v4 = *(void **)a1;
  v11[0] = operator new(0x48u);
  v5 = Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_______::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___(
         v11[0],
         v4);
  v11[0] = 0;
  v6 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v5;
  if ( v6 )
    std::default_delete<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::operator()();
  std::unique_ptr<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::~unique_ptr<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>(v11);
  v11[2] = (PVOID)64;
  v16 = 0;
  v17 = 0;
  v12 = 8;
  v14 = 1;
  v13 = GUID_AvencFileIoChannelControl;
  v18 = 0;
  v15 = 10;
  v7 = Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalDeviceIoControl(
         *(HANDLE *)a1,
         dwCreationDisposition);
  return wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
           retaddr,
           (void *)0x142,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\inc\\FileChannel.h",
           (const char *)v7,
           (int)"Failed to start channel",
           dwFlagsAndAttributes);
}

```

## disassembly

```asm
0x18001b510  mov     [rsp-8+arg_10], rbx
0x18001b515  push    rbp
0x18001b516  push    rsi
0x18001b517  push    rdi
0x18001b518  lea     rbp, [rsp-1Fh]
0x18001b51d  sub     rsp, 0A0h
0x18001b524  mov     rax, cs:__security_cookie
0x18001b52b  xor     rax, rsp
0x18001b52e  mov     [rbp+2Fh+var_20], rax
0x18001b532  mov     rbx, rdx
0x18001b535  mov     rsi, rcx
0x18001b538  mov     rdi, [rbp+2Fh+arg_40]
0x18001b53c  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18001b545  mov     [rsp+0B0h+dwFlagsAndAttributes], 40800080h; dwFlagsAndAttributes
0x18001b54d  mov     [rsp+0B0h+dwCreationDisposition], 4; dwCreationDisposition
0x18001b555  xor     r9d, r9d; lpSecurityAttributes
0x18001b558  mov     edx, 10000000h; dwDesiredAccess
0x18001b55d  lea     r8d, [r9+3]; dwShareMode
0x18001b561  mov     rcx, rbx; lpFileName
0x18001b564  call    cs:__imp_CreateFileW
0x18001b56a  mov     [rbp+2Fh+var_70], rax
0x18001b56e  lea     rdx, [rbp+2Fh+var_70]
0x18001b572  mov     rcx, rsi
0x18001b575  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18001b57a  lea     rcx, [rbp+2Fh+var_70]
0x18001b57e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b583  mov     rax, [rsi]
0x18001b586  inc     rax
0x18001b589  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b58f  setz    al
0x18001b592  mov     rcx, [rbp+37h]; this
0x18001b596  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rbx; char *
0x18001b59b  lea     rdx, Event; "Failed to open channel: %s"
0x18001b5a2  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; Event
0x18001b5a7  movzx   r9d, al; char *
0x18001b5ab  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b5b2  mov     edx, 125h; void *
0x18001b5b7  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001b5bc  mov     rbx, [rsi]
0x18001b5bf  mov     ecx, 48h ; 'H'; Size
0x18001b5c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b5c9  mov     [rbp+2Fh+var_70], rax
0x18001b5cd  mov     r8, rdi
0x18001b5d0  mov     rdx, rbx; fl
0x18001b5d3  mov     rcx, rax; pv
0x18001b5d6  call    Rdp__Utils__TP__details__CThreadPoolIo_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp__Utils__TP__details__DestroyThreadpoolIo_wistd__integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std__nullptr_t_________CThreadPoolIo_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp__Utils__TP__details__DestroyThreadpoolIo_wistd__integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std__nullptr_t_________Rdp__Stack__Shim__CCtrlChannel__StartFileIo____2____lambda_1___
0x18001b5db  nop
0x18001b5dc  mov     [rbp+2Fh+var_70], 0
0x18001b5e4  mov     rdx, [rsi+8]
0x18001b5e8  mov     [rsi+8], rax
0x18001b5ec  test    rdx, rdx
0x18001b5ef  jz      short loc_18001B5F6
0x18001b5f1  call    ??R?$default_delete@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@std@@QEBAXPEAV?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::operator()(Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>> *)
0x18001b5f6  lea     rcx, [rbp+2Fh+var_70]
0x18001b5fa  call    ??1?$unique_ptr@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@U?$default_delete@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::~unique_ptr<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>(void)
0x18001b5ff  mov     [rbp+2Fh+var_60], 40h ; '@'
0x18001b607  mov     [rbp+2Fh+var_34], 0
0x18001b60f  mov     [rbp+2Fh+var_2C], 0
0x18001b617  mov     [rbp+2Fh+var_58], 8
0x18001b61e  mov     [rbp+2Fh+var_44], 1
0x18001b626  movups  xmm0, xmmword ptr cs:GUID_AvencFileIoChannelControl.Data1
0x18001b62d  movdqu  [rbp+2Fh+var_54], xmm0
0x18001b632  mov     [rbp+2Fh+var_24], 0
0x18001b639  mov     [rbp+2Fh+var_3C], 0Ah
0x18001b641  lea     r8, [rbp+2Fh+var_60]
0x18001b645  mov     rcx, [rsi]; FileHandle
0x18001b648  call    ?InternalDeviceIoControl@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@CAHPEAXK0K0KPEAK@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::InternalDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001b64d  mov     rcx, [rbp+37h]; this
0x18001b651  lea     rdx, aFailedToStartC; "Failed to start channel"
0x18001b658  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdx; int
0x18001b65d  mov     r9d, eax; char *
0x18001b660  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b667  mov     edx, 142h; void *
0x18001b66c  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18001b671  mov     rcx, [rbp+2Fh+var_20]
0x18001b675  xor     rcx, rsp; StackCookie
0x18001b678  call    __security_check_cookie
0x18001b67d  mov     rbx, [rsp+0B0h+arg_10]
0x18001b685  add     rsp, 0A0h
0x18001b68c  pop     rdi
0x18001b68d  pop     rsi
0x18001b68e  pop     rbp
0x18001b68f  retn
```
