# Microsoft::IoT::ShellExtension::CCBT::operator=(Microsoft::IoT::ShellExtension::CCBT &)

- ea: `0x180015a2c`
- end: `0x180015be0`
- name: `??4CCBT@ShellExtension@IoT@Microsoft@@QEAAAEAV0123@AEAV0123@@Z`
- size: `436`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001533c`

## callees

- `0x18000a2ac`
- `0x18000ab5c`
- `0x18000c300`
- `0x18000d1cc`
- `0x180010980`
- `0x180015a2c`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBT::operator=(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 *v8; // rdx
  int v9; // ebx
  __int64 v10; // rdx
  __int64 *v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  __int64 *v14; // rdx
  char v15; // bl
  _BYTE v17[8]; // [rsp+20h] [rbp-10h] BYREF
  std::_Ref_count_base *v18; // [rsp+28h] [rbp-8h]
  __int64 v19; // [rsp+50h] [rbp+20h] BYREF
  char v20; // [rsp+58h] [rbp+28h] BYREF
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF

  LODWORD(v19) = 0;
  if ( a1 != a2 )
  {
    *(_QWORD *)a1 = *(_QWORD *)a2;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    v4 = (__int64 *)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      v17,
                      a2 + 16);
    v5 = *v4;
    *v4 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = v5;
    v6 = v4[1];
    v4[1] = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v6;
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    v7 = *(_QWORD *)(a2 + 40);
    if ( v7 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v20,
        v7);
      v8 = (__int64 *)&v20;
      v9 = 66;
    }
    else
    {
      v21 = 0;
      v8 = &v21;
      v9 = 1;
    }
    LODWORD(v19) = v9;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1 + 40,
      v8);
    if ( (v9 & 2) != 0 )
    {
      v9 &= ~2u;
      LODWORD(v19) = v9;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    }
    if ( (v9 & 1) != 0 )
    {
      v9 &= ~1u;
      LODWORD(v19) = v9;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    }
    v10 = *(_QWORD *)(a2 + 48);
    if ( v10 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v20,
        v10);
      v11 = (__int64 *)&v20;
      v12 = v9 | 0x108;
    }
    else
    {
      v21 = 0;
      v11 = &v21;
      v12 = v9 | 4;
    }
    LODWORD(v19) = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1 + 48,
      v11);
    if ( (v12 & 8) != 0 )
    {
      v12 &= ~8u;
      LODWORD(v19) = v12;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    }
    if ( (v12 & 4) != 0 )
    {
      v12 &= ~4u;
      LODWORD(v19) = v12;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    }
    v13 = *(_QWORD *)(a2 + 32);
    if ( v13 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v20,
        v13);
      v14 = (__int64 *)&v20;
      v15 = v12 | 0x20;
    }
    else
    {
      v19 = 0;
      v14 = &v19;
      v15 = v12 | 0x10;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1 + 32,
      v14);
    if ( (v15 & 0x20) != 0 )
    {
      v15 &= ~0x20u;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    }
    if ( (v15 & 0x10) != 0 )
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 56);
    *(_OWORD *)(a1 + 60) = *(_OWORD *)(a2 + 60);
    *(_BYTE *)(a1 + 78) = *(_BYTE *)(a2 + 78);
    *(_BYTE *)(a1 + 79) = *(_BYTE *)(a2 + 79);
    *(_BYTE *)(a1 + 80) = *(_BYTE *)(a2 + 80);
    *(_WORD *)(a1 + 76) = *(_WORD *)(a2 + 76);
  }
  return a1;
}

```

## disassembly

```asm
0x180015a2c  mov     [rsp-18h+arg_18], rbx
0x180015a31  push    rbp
0x180015a32  push    rsi
0x180015a33  push    rdi
0x180015a34  mov     rbp, rsp
0x180015a37  sub     rsp, 30h
0x180015a3b  mov     rsi, rdx
0x180015a3e  mov     rdi, rcx
0x180015a41  mov     dword ptr [rbp+arg_0], 0
0x180015a48  cmp     rcx, rdx
0x180015a4b  jz      loc_180015BD0
0x180015a51  mov     rax, [rdx]
0x180015a54  mov     [rcx], rax
0x180015a57  mov     rax, [rdx+8]
0x180015a5b  mov     [rcx+8], rax
0x180015a5f  add     rdx, 10h
0x180015a63  lea     rcx, [rbp+var_10]
0x180015a67  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x180015a6c  mov     rdx, [rax]
0x180015a6f  mov     rcx, [rdi+10h]
0x180015a73  mov     [rax], rcx
0x180015a76  mov     [rdi+10h], rdx
0x180015a7a  mov     rdx, [rax+8]
0x180015a7e  mov     rcx, [rdi+18h]
0x180015a82  mov     [rax+8], rcx
0x180015a86  mov     [rdi+18h], rdx
0x180015a8a  mov     rcx, [rbp+var_8]; this
0x180015a8e  test    rcx, rcx
0x180015a91  jz      short loc_180015A98
0x180015a93  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015a98  mov     rdx, [rsi+28h]
0x180015a9c  test    rdx, rdx
0x180015a9f  jnz     short loc_180015AB0
0x180015aa1  mov     [rbp+arg_10], rdx
0x180015aa5  lea     rdx, [rbp+arg_10]
0x180015aa9  mov     ebx, 1
0x180015aae  jmp     short loc_180015AC2
0x180015ab0  lea     rcx, [rbp+arg_8]
0x180015ab4  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180015ab9  lea     rdx, [rbp+arg_8]
0x180015abd  mov     ebx, 42h ; 'B'
0x180015ac2  mov     dword ptr [rbp+arg_0], ebx
0x180015ac5  lea     rcx, [rdi+28h]
0x180015ac9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015ace  test    bl, 2
0x180015ad1  jz      short loc_180015AE3
0x180015ad3  and     ebx, 0FFFFFFFDh
0x180015ad6  mov     dword ptr [rbp+arg_0], ebx
0x180015ad9  lea     rcx, [rbp+arg_8]
0x180015add  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015ae2  nop
0x180015ae3  test    bl, 1
0x180015ae6  jz      short loc_180015AF7
0x180015ae8  and     ebx, 0FFFFFFFEh
0x180015aeb  mov     dword ptr [rbp+arg_0], ebx
0x180015aee  lea     rcx, [rbp+arg_10]
0x180015af2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015af7  mov     rdx, [rsi+30h]
0x180015afb  test    rdx, rdx
0x180015afe  jnz     short loc_180015B0D
0x180015b00  mov     [rbp+arg_10], rdx
0x180015b04  lea     rdx, [rbp+arg_10]
0x180015b08  or      ebx, 4
0x180015b0b  jmp     short loc_180015B20
0x180015b0d  lea     rcx, [rbp+arg_8]
0x180015b11  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180015b16  lea     rdx, [rbp+arg_8]
0x180015b1a  or      ebx, 108h
0x180015b20  mov     dword ptr [rbp+arg_0], ebx
0x180015b23  lea     rcx, [rdi+30h]
0x180015b27  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015b2c  test    bl, 8
0x180015b2f  jz      short loc_180015B41
0x180015b31  and     ebx, 0FFFFFFF7h
0x180015b34  mov     dword ptr [rbp+arg_0], ebx
0x180015b37  lea     rcx, [rbp+arg_8]
0x180015b3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015b40  nop
0x180015b41  test    bl, 4
0x180015b44  jz      short loc_180015B55
0x180015b46  and     ebx, 0FFFFFFFBh
0x180015b49  mov     dword ptr [rbp+arg_0], ebx
0x180015b4c  lea     rcx, [rbp+arg_10]
0x180015b50  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015b55  mov     rdx, [rsi+20h]
0x180015b59  test    rdx, rdx
0x180015b5c  jnz     short loc_180015B6B
0x180015b5e  mov     [rbp+arg_0], rdx
0x180015b62  lea     rdx, [rbp+arg_0]
0x180015b66  or      ebx, 10h
0x180015b69  jmp     short loc_180015B7E
0x180015b6b  lea     rcx, [rbp+arg_8]
0x180015b6f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180015b74  lea     rdx, [rbp+arg_8]
0x180015b78  or      ebx, 420h
0x180015b7e  lea     rcx, [rdi+20h]
0x180015b82  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015b87  test    bl, 20h
0x180015b8a  jz      short loc_180015B99
0x180015b8c  and     ebx, 0FFFFFFDFh
0x180015b8f  lea     rcx, [rbp+arg_8]
0x180015b93  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015b98  nop
0x180015b99  test    bl, 10h
0x180015b9c  jz      short loc_180015BA7
0x180015b9e  lea     rcx, [rbp+arg_0]
0x180015ba2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015ba7  mov     eax, [rsi+38h]
0x180015baa  mov     [rdi+38h], eax
0x180015bad  movups  xmm0, xmmword ptr [rsi+3Ch]
0x180015bb1  movdqu  xmmword ptr [rdi+3Ch], xmm0
0x180015bb6  mov     al, [rsi+4Eh]
0x180015bb9  mov     [rdi+4Eh], al
0x180015bbc  mov     al, [rsi+4Fh]
0x180015bbf  mov     [rdi+4Fh], al
0x180015bc2  mov     al, [rsi+50h]
0x180015bc5  mov     [rdi+50h], al
0x180015bc8  movzx   eax, word ptr [rsi+4Ch]
0x180015bcc  mov     [rdi+4Ch], ax
0x180015bd0  mov     rax, rdi
0x180015bd3  mov     rbx, [rsp+30h+arg_18]
0x180015bd8  add     rsp, 30h
0x180015bdc  pop     rdi
0x180015bdd  pop     rsi
0x180015bde  pop     rbp
0x180015bdf  retn
```
