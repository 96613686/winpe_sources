# ExpeditedUpdateUSOTask::RuntimeClassInitialize(INamedPropertyStore *)

- ea: `0x18007a698`
- end: `0x18007a831`
- name: `?RuntimeClassInitialize@ExpeditedUpdateUSOTask@@QEAAJPEAUINamedPropertyStore@@@Z`
- size: `409`
- prototype: `int(ExpeditedUpdateUSOTask *__hidden this, struct INamedPropertyStore *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f124`

## callees

- `0x180008544`
- `0x180008b54`
- `0x180038ac4`
- `0x180056408`
- `0x18007a698`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a74c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a76b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a78a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a74c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a76b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a78a`

## string_xrefs

- `0x18007a6b6`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007a6f4`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExpeditedUpdateUSOTask::RuntimeClassInitialize(
        ExpeditedUpdateUSOTask *this,
        struct INamedPropertyStore *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int v6; // eax
  __int64 v7; // r11
  unsigned int v8; // edi
  __int64 v9; // rdi
  HANDLE EventW; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 40;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)v3,
      v13);
    return v3;
  }
  v6 = StringCchCopyW((unsigned __int16 *)this + 12, 0x104u, L"OOBE NDUP");
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = *((_QWORD *)this + 80);
    *((_QWORD *)this + 80) = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    EventW = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 592,
      EventW);
    v11 = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 608,
      v11);
    v12 = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 624,
      v12);
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset((char *)this + 648);
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset((char *)this + 656);
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset((char *)this + 680);
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset((char *)this + 664);
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset((char *)this + 672);
    if ( !*((_QWORD *)this + 75) )
    {
      v3 = -2147418113;
      v4 = 52;
      goto LABEL_3;
    }
    if ( !*((_QWORD *)this + 77) )
    {
      v3 = -2147418113;
      v4 = 53;
      goto LABEL_3;
    }
    if ( !*((_QWORD *)this + 79) )
    {
      v3 = -2147418113;
      v4 = 54;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v6,
      v13);
    return v8;
  }
}

```

## disassembly

```asm
0x18007a698  mov     [rsp+arg_0], rbx
0x18007a69d  push    rdi; int
0x18007a69e  sub     rsp, 20h
0x18007a6a2  mov     r11, rdx
0x18007a6a5  mov     rbx, rcx
0x18007a6a8  test    rdx, rdx
0x18007a6ab  jnz     short loc_18007A6D1
0x18007a6ad  mov     ebx, 80070057h
0x18007a6b2  lea     edx, [r11+28h]; void *
0x18007a6b6  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a6bd  mov     r9d, ebx; char *
0x18007a6c0  mov     rcx, [rsp+28h]; this
0x18007a6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a6ca  mov     eax, ebx
0x18007a6cc  jmp     loc_18007A826
0x18007a6d1  add     rcx, 18h; unsigned __int16 *
0x18007a6d5  lea     r8, aOobeNdup; "OOBE NDUP"
0x18007a6dc  mov     edx, 104h; unsigned __int64
0x18007a6e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007a6e6  mov     edi, eax
0x18007a6e8  test    eax, eax
0x18007a6ea  jns     short loc_18007A70C
0x18007a6ec  mov     rcx, [rsp+28h]; this
0x18007a6f1  mov     r9d, eax; char *
0x18007a6f4  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007a6fb  mov     edx, 29h ; ')'; void *
0x18007a700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a705  mov     eax, edi
0x18007a707  jmp     loc_18007A826
0x18007a70c  mov     rdi, [rbx+280h]
0x18007a713  mov     [rbx+280h], r11
0x18007a71a  mov     rax, [r11]
0x18007a71d  mov     rcx, r11
0x18007a720  mov     rax, [rax+8]
0x18007a724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a729  test    rdi, rdi
0x18007a72c  jz      short loc_18007A73E
0x18007a72e  mov     rax, [rdi]
0x18007a731  mov     rcx, rdi
0x18007a734  mov     rax, [rax+10h]
0x18007a738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a73d  nop
0x18007a73e  xor     r9d, r9d; lpName
0x18007a741  xor     r8d, r8d; bInitialState
0x18007a744  lea     edi, [r9+1]
0x18007a748  mov     edx, edi; bManualReset
0x18007a74a  xor     ecx, ecx; lpEventAttributes
0x18007a74c  call    cs:__imp_CreateEventW
0x18007a752  mov     rdx, rax
0x18007a755  lea     rcx, [rbx+250h]
0x18007a75c  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18007a761  xor     r9d, r9d; lpName
0x18007a764  xor     r8d, r8d; bInitialState
0x18007a767  mov     edx, edi; bManualReset
0x18007a769  xor     ecx, ecx; lpEventAttributes
0x18007a76b  call    cs:__imp_CreateEventW
0x18007a771  mov     rdx, rax
0x18007a774  lea     rcx, [rbx+260h]
0x18007a77b  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18007a780  xor     r9d, r9d; lpName
0x18007a783  xor     r8d, r8d; bInitialState
0x18007a786  mov     edx, edi; bManualReset
0x18007a788  xor     ecx, ecx; lpEventAttributes
0x18007a78a  call    cs:__imp_CreateEventW
0x18007a790  mov     rdx, rax
0x18007a793  lea     rcx, [rbx+270h]
0x18007a79a  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x18007a79f  lea     rcx, [rbx+288h]
0x18007a7a6  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x18007a7ab  lea     rcx, [rbx+290h]
0x18007a7b2  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x18007a7b7  lea     rcx, [rbx+2A8h]
0x18007a7be  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x18007a7c3  lea     rcx, [rbx+298h]
0x18007a7ca  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x18007a7cf  lea     rcx, [rbx+2A0h]
0x18007a7d6  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x18007a7db  cmp     qword ptr [rbx+258h], 0
0x18007a7e3  jnz     short loc_18007A7F2
0x18007a7e5  mov     ebx, 8000FFFFh
0x18007a7ea  lea     edx, [rdi+33h]
0x18007a7ed  jmp     loc_18007A6B6
0x18007a7f2  cmp     qword ptr [rbx+268h], 0
0x18007a7fa  jnz     short loc_18007A80B
0x18007a7fc  mov     ebx, 8000FFFFh
0x18007a801  mov     edx, 35h ; '5'
0x18007a806  jmp     loc_18007A6B6
0x18007a80b  cmp     qword ptr [rbx+278h], 0
0x18007a813  jnz     short loc_18007A824
0x18007a815  mov     ebx, 8000FFFFh
0x18007a81a  mov     edx, 36h ; '6'
0x18007a81f  jmp     loc_18007A6B6
0x18007a824  xor     eax, eax
0x18007a826  mov     rbx, [rsp+28h+arg_0]
0x18007a82b  add     rsp, 20h
0x18007a82f  pop     rdi
0x18007a830  retn
```
