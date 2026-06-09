# BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(IBitsTokenOptions *)

- ea: `0x140011674`
- end: `0x1400117fb`
- name: `?SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking@BitsHelper@@AEAAJPEAUIBitsTokenOptions@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(BitsHelper *__hidden this, struct IBitsTokenOptions *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000fa90`
- `0x1400100e0`

## callees

- `0x140005cac`
- `0x14000a4bc`
- `0x14000fa44`
- `0x140011674`
- `0x14001a010`

## string_xrefs

- `0x1400116b4`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140011758`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
__int64 __fastcall BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(
        BitsHelper *this,
        struct IBitsTokenOptions *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdx
  unsigned int v9; // [rsp+50h] [rbp-20h] BYREF
  int v10[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-10h] BYREF
  __int64 v12; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  BitsHelper *v14; // [rsp+90h] [rbp+20h] BYREF
  int v15; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+A8h] [rbp+38h] BYREF

  v14 = this;
  v11 = 0;
  v3 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, GUID *, __int64 **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v11);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v9 = 0;
    v17 = 0;
    v16 = 0;
    v15 = 0;
    LODWORD(v14) = 0;
    v12 = 0;
    *(_QWORD *)v10 = 0;
    v5 = *v11;
    *(_QWORD *)v10 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, struct IBitsTokenOptions *, unsigned int *, unsigned int *, int *, int *, int *, __int64 *, BitsHelper **))(v5 + 24))(
           v11,
           a2,
           &v9,
           &v17,
           v10,
           &v16,
           &v15,
           &v12,
           &v14);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v15 = 3;
      LODWORD(v14) = (unsigned int)v14 | 0x40;
      v6 = (*(__int64 (__fastcall **)(__int64 *, struct IBitsTokenOptions *, _QWORD, _QWORD, _QWORD, int, int, __int64, _DWORD))(*v11 + 32))(
             v11,
             a2,
             v9,
             v17,
             *(_QWORD *)v10,
             v16,
             3,
             v12,
             (_DWORD)v14);
      v4 = v6;
      if ( v6 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v10);
        v4 = 0;
        goto LABEL_9;
      }
      v7 = 46;
    }
    else
    {
      v7 = 30;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v6);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD,
      (int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v3);
  }
LABEL_9:
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)&v11);
  return v4;
}

```

## disassembly

```asm
0x140011674  mov     [rsp-18h+arg_0], rcx
0x140011679  push    rbp
0x14001167a  push    rbx
0x14001167b  push    rdi
0x14001167c  mov     rbp, rsp
0x14001167f  sub     rsp, 70h
0x140011683  mov     rdi, rdx
0x140011686  mov     [rbp+var_10], 0
0x14001168e  mov     rax, [rdx]
0x140011691  lea     r8, [rbp+var_10]
0x140011695  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x14001169c  mov     rcx, rdi
0x14001169f  mov     rax, [rax]
0x1400116a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116a7  mov     ebx, eax
0x1400116a9  test    eax, eax
0x1400116ab  jns     short loc_1400116CA
0x1400116ad  mov     rcx, [rbp+18h]; this
0x1400116b1  mov     r9d, eax; char *
0x1400116b4  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x1400116bb  mov     edx, 0Dh; void *
0x1400116c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400116c5  jmp     loc_1400117E8
0x1400116ca  mov     [rbp+var_20], 0
0x1400116d1  mov     [rbp+arg_18], 0
0x1400116d8  mov     [rbp+arg_10], 0
0x1400116df  mov     [rbp+arg_8], 0
0x1400116e6  mov     dword ptr [rbp+arg_0], 0
0x1400116ed  mov     [rbp+var_8], 0
0x1400116f5  mov     qword ptr [rbp+var_18], 0
0x1400116fd  mov     rcx, [rbp+var_10]
0x140011701  mov     rax, [rcx]
0x140011704  mov     qword ptr [rbp+var_18], 0
0x14001170c  lea     rdx, [rbp+arg_0]
0x140011710  mov     [rsp+70h+var_30], rdx
0x140011715  lea     rdx, [rbp+var_8]
0x140011719  mov     [rsp+70h+var_38], rdx
0x14001171e  lea     rdx, [rbp+arg_8]
0x140011722  mov     [rsp+70h+var_40], rdx
0x140011727  lea     rdx, [rbp+arg_10]
0x14001172b  mov     [rsp+70h+var_48], rdx
0x140011730  lea     rdx, [rbp+var_18]
0x140011734  mov     qword ptr [rsp+70h+var_50], rdx; int
0x140011739  lea     r9, [rbp+arg_18]
0x14001173d  lea     r8, [rbp+var_20]
0x140011741  mov     rdx, rdi
0x140011744  mov     rax, [rax+18h]
0x140011748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001174d  mov     ebx, eax
0x14001174f  test    eax, eax
0x140011751  jns     short loc_140011777
0x140011753  mov     edx, 1Eh; void *
0x140011758  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001175f  mov     r9d, eax; char *
0x140011762  mov     rcx, [rbp+18h]; this
0x140011766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001176b  nop
0x14001176c  lea     rcx, [rbp+var_18]
0x140011770  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140011775  jmp     short loc_1400117E8
0x140011777  mov     r9d, 3
0x14001177d  mov     [rbp+arg_8], r9d
0x140011781  mov     r8d, dword ptr [rbp+arg_0]
0x140011785  or      r8d, 40h
0x140011789  mov     dword ptr [rbp+arg_0], r8d
0x14001178d  mov     rcx, [rbp+var_10]
0x140011791  mov     rdx, [rbp+var_8]
0x140011795  mov     r10d, [rbp+arg_10]
0x140011799  mov     r11, qword ptr [rbp+var_18]
0x14001179d  mov     rax, [rcx]
0x1400117a0  mov     dword ptr [rsp+70h+var_30], r8d
0x1400117a5  mov     [rsp+70h+var_38], rdx
0x1400117aa  mov     dword ptr [rsp+70h+var_40], r9d
0x1400117af  mov     dword ptr [rsp+70h+var_48], r10d
0x1400117b4  mov     qword ptr [rsp+70h+var_50], r11
0x1400117b9  mov     r9d, [rbp+arg_18]
0x1400117bd  mov     r8d, [rbp+var_20]
0x1400117c1  mov     rdx, rdi
0x1400117c4  mov     rax, [rax+20h]
0x1400117c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400117cd  mov     ebx, eax
0x1400117cf  test    eax, eax
0x1400117d1  jns     short loc_1400117DD
0x1400117d3  mov     edx, 2Eh ; '.'
0x1400117d8  jmp     loc_140011758
0x1400117dd  lea     rcx, [rbp+var_18]
0x1400117e1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400117e6  xor     ebx, ebx
0x1400117e8  lea     rcx, [rbp+var_10]
0x1400117ec  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400117f1  mov     eax, ebx
0x1400117f3  add     rsp, 70h
0x1400117f7  pop     rdi
0x1400117f8  pop     rbx
0x1400117f9  pop     rbp
0x1400117fa  retn
```
