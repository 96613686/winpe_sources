# Microsoft::IoT::ShellExtension::CCBT::operator=(Microsoft::IoT::ShellExtension::CCBT &&)

- ea: `0x1800109b8`
- end: `0x180010ac4`
- name: `??4CCBT@ShellExtension@IoT@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fc18`
- `0x180011134`

## callees

- `0x18000c300`
- `0x18000d1cc`
- `0x1800109b8`
- `0x1800150c0`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBT::operator=(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int128 v12; // xmm0
  char v13; // al
  char v14; // al
  char v15; // al
  __int16 v16; // ax
  std::_Ref_count_base *v18[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a1 != a2 )
  {
    *(_QWORD *)a1 = *(_QWORD *)a2;
    v4 = *(_QWORD *)(a2 + 8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a1 + 8) = v4;
    *(_QWORD *)(a2 + 8) = 0;
    v5 = std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           v18,
           (_QWORD *)(a2 + 16));
    v6 = *v5;
    *v5 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = v6;
    v7 = v5[1];
    v5[1] = *(_QWORD *)(a1 + 24);
    v8 = v18[1];
    *(_QWORD *)(a1 + 24) = v7;
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    v9 = *(_QWORD *)(a2 + 40);
    *(_QWORD *)(a2 + 40) = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 40,
      v9);
    v10 = *(_QWORD *)(a2 + 48);
    *(_QWORD *)(a2 + 48) = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 48,
      v10);
    v11 = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 32) = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 32,
      v11);
    *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 56);
    v12 = *(_OWORD *)(a2 + 60);
    *(_DWORD *)(a2 + 56) = -2147483638;
    *(_OWORD *)(a1 + 60) = v12;
    v13 = *(_BYTE *)(a2 + 78);
    *(GUID *)(a2 + 60) = GUID_NULL;
    *(_BYTE *)(a1 + 78) = v13;
    v14 = *(_BYTE *)(a2 + 79);
    *(_BYTE *)(a2 + 78) = 0;
    *(_BYTE *)(a1 + 79) = v14;
    v15 = *(_BYTE *)(a2 + 80);
    *(_BYTE *)(a2 + 79) = 0;
    *(_BYTE *)(a1 + 80) = v15;
    v16 = *(_WORD *)(a2 + 76);
    *(_BYTE *)(a2 + 80) = 1;
    *(_WORD *)(a1 + 76) = v16;
    *(_WORD *)(a2 + 76) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800109b8  mov     [rsp+arg_0], rbx
0x1800109bd  push    rdi
0x1800109be  sub     rsp, 30h
0x1800109c2  mov     rdi, rdx
0x1800109c5  mov     rbx, rcx
0x1800109c8  cmp     rcx, rdx
0x1800109cb  jz      loc_180010AB6
0x1800109d1  mov     rax, [rdx]
0x1800109d4  mov     [rcx], rax
0x1800109d7  mov     rax, [rdx+8]
0x1800109db  mov     qword ptr [rdx], 0
0x1800109e2  mov     [rcx+8], rax
0x1800109e6  lea     rcx, [rsp+38h+var_18]
0x1800109eb  mov     qword ptr [rdx+8], 0
0x1800109f3  add     rdx, 10h
0x1800109f7  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x1800109fc  mov     rcx, [rbx+10h]
0x180010a00  mov     rdx, [rax]
0x180010a03  mov     [rax], rcx
0x180010a06  mov     [rbx+10h], rdx
0x180010a0a  mov     rcx, [rbx+18h]
0x180010a0e  mov     rdx, [rax+8]
0x180010a12  mov     [rax+8], rcx
0x180010a16  mov     rcx, [rsp+38h+var_10]; this
0x180010a1b  mov     [rbx+18h], rdx
0x180010a1f  test    rcx, rcx
0x180010a22  jz      short loc_180010A29
0x180010a24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010a29  mov     rdx, [rdi+28h]
0x180010a2d  lea     rcx, [rbx+28h]
0x180010a31  mov     qword ptr [rdi+28h], 0
0x180010a39  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010a3e  mov     rdx, [rdi+30h]
0x180010a42  lea     rcx, [rbx+30h]
0x180010a46  mov     qword ptr [rdi+30h], 0
0x180010a4e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010a53  mov     rdx, [rdi+20h]
0x180010a57  lea     rcx, [rbx+20h]
0x180010a5b  mov     qword ptr [rdi+20h], 0
0x180010a63  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010a68  mov     eax, [rdi+38h]
0x180010a6b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180010a72  mov     [rbx+38h], eax
0x180010a75  movups  xmm0, xmmword ptr [rdi+3Ch]
0x180010a79  mov     dword ptr [rdi+38h], 8000000Ah
0x180010a80  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x180010a85  mov     al, [rdi+4Eh]
0x180010a88  movdqu  xmmword ptr [rdi+3Ch], xmm1
0x180010a8d  mov     [rbx+4Eh], al
0x180010a90  mov     al, [rdi+4Fh]
0x180010a93  mov     byte ptr [rdi+4Eh], 0
0x180010a97  mov     [rbx+4Fh], al
0x180010a9a  mov     al, [rdi+50h]
0x180010a9d  mov     byte ptr [rdi+4Fh], 0
0x180010aa1  mov     [rbx+50h], al
0x180010aa4  movzx   eax, word ptr [rdi+4Ch]
0x180010aa8  mov     byte ptr [rdi+50h], 1
0x180010aac  mov     [rbx+4Ch], ax
0x180010ab0  xor     eax, eax
0x180010ab2  mov     [rdi+4Ch], ax
0x180010ab6  mov     rax, rbx
0x180010ab9  mov     rbx, [rsp+38h+arg_0]
0x180010abe  add     rsp, 30h
0x180010ac2  pop     rdi
0x180010ac3  retn
```
