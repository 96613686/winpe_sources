# Microsoft::IoT::ShellExtension::CCBT::CCBT(Microsoft::IoT::ShellExtension::CCBT const &)

- ea: `0x180010100`
- end: `0x180010293`
- name: `??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@AEBV0123@@Z`
- size: `403`
- prototype: `Microsoft::IoT::ShellExtension::CCBT *__fastcall(Microsoft::IoT::ShellExtension::CCBT *this, const struct Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f9a4`
- `0x18000fd5c`
- `0x18000fe38`
- `0x180012c00`
- `0x180012f10`

## callees

- `0x18000a2ac`
- `0x18000ab5c`
- `0x18000d1cc`
- `0x180010100`

## pseudocode

```c
Microsoft::IoT::ShellExtension::CCBT *__fastcall Microsoft::IoT::ShellExtension::CCBT::CCBT(
        Microsoft::IoT::ShellExtension::CCBT *this,
        const struct Microsoft::IoT::ShellExtension::CCBT *a2)
{
  __int64 *v4; // rcx
  int v5; // ebx
  __int64 v6; // rax
  __int64 *v7; // rcx
  int v8; // ebx
  __int64 v9; // rax
  Microsoft::IoT::ShellExtension::CCBT **v10; // rcx
  char v11; // bl
  __int64 v12; // rax
  Microsoft::IoT::ShellExtension::CCBT *v14; // [rsp+50h] [rbp+28h] BYREF
  int v15; // [rsp+58h] [rbp+30h]
  __int64 v16; // [rsp+60h] [rbp+38h] BYREF
  __int64 v17; // [rsp+68h] [rbp+40h] BYREF

  v14 = this;
  v15 = 0;
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    (_QWORD *)this + 2,
    (_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 4) )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v16);
    v4 = &v16;
    v5 = 66;
    v6 = v16;
  }
  else
  {
    v17 = 0;
    v4 = &v17;
    v5 = 1;
    v6 = 0;
  }
  v15 = v5;
  *((_QWORD *)this + 4) = v6;
  *v4 = 0;
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    v15 = v5;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  }
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    v15 = v5;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  if ( *((_QWORD *)a2 + 5) )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v16);
    v7 = &v16;
    v8 = v5 | 0x108;
    v9 = v16;
  }
  else
  {
    v17 = 0;
    v7 = &v17;
    v8 = v5 | 4;
    v9 = 0;
  }
  v15 = v8;
  *((_QWORD *)this + 5) = v9;
  *v7 = 0;
  if ( (v8 & 8) != 0 )
  {
    v8 &= ~8u;
    v15 = v8;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  }
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    v15 = v8;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  if ( *((_QWORD *)a2 + 6) )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v16);
    v10 = (Microsoft::IoT::ShellExtension::CCBT **)&v16;
    v11 = v8 | 0x20;
    v12 = v16;
  }
  else
  {
    v14 = 0;
    v10 = &v14;
    v11 = v8 | 0x10;
    v12 = 0;
  }
  *((_QWORD *)this + 6) = v12;
  *v10 = 0;
  if ( (v11 & 0x20) != 0 )
  {
    v11 &= ~0x20u;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  }
  if ( (v11 & 0x10) != 0 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  *((_DWORD *)this + 14) = *((_DWORD *)a2 + 14);
  *(_OWORD *)((char *)this + 60) = *(_OWORD *)((char *)a2 + 60);
  *((_WORD *)this + 38) = *((_WORD *)a2 + 38);
  *((_BYTE *)this + 78) = *((_BYTE *)a2 + 78);
  *((_BYTE *)this + 79) = *((_BYTE *)a2 + 79);
  *((_BYTE *)this + 80) = *((_BYTE *)a2 + 80);
  return this;
}

```

## disassembly

```asm
0x180010100  mov     [rsp-20h+arg_0], rcx
0x180010105  push    rbp
0x180010106  push    rbx
0x180010107  push    rsi
0x180010108  push    rdi
0x180010109  mov     rbp, rsp
0x18001010c  sub     rsp, 28h
0x180010110  mov     rsi, rdx
0x180010113  mov     rdi, rcx
0x180010116  mov     [rbp+arg_8], 0
0x18001011d  mov     rax, [rdx]
0x180010120  mov     [rcx], rax
0x180010123  mov     rax, [rdx+8]
0x180010127  mov     [rcx+8], rax
0x18001012b  add     rdx, 10h
0x18001012f  add     rcx, 10h
0x180010133  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x180010138  nop
0x180010139  mov     rdx, [rsi+20h]
0x18001013d  test    rdx, rdx
0x180010140  jnz     short loc_180010151
0x180010142  mov     [rbp+arg_18], rdx
0x180010146  lea     rcx, [rbp+arg_18]
0x18001014a  lea     ebx, [rdx+1]
0x18001014d  xor     eax, eax
0x18001014f  jmp     short loc_180010167
0x180010151  lea     rcx, [rbp+arg_10]
0x180010155  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001015a  lea     rcx, [rbp+arg_10]
0x18001015e  mov     ebx, 42h ; 'B'
0x180010163  mov     rax, [rbp+arg_10]
0x180010167  mov     [rbp+arg_8], ebx
0x18001016a  mov     [rdi+20h], rax
0x18001016e  mov     qword ptr [rcx], 0
0x180010175  test    bl, 2
0x180010178  jz      short loc_18001018A
0x18001017a  and     ebx, 0FFFFFFFDh
0x18001017d  mov     [rbp+arg_8], ebx
0x180010180  lea     rcx, [rbp+arg_10]
0x180010184  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010189  nop
0x18001018a  test    bl, 1
0x18001018d  jz      short loc_18001019E
0x18001018f  and     ebx, 0FFFFFFFEh
0x180010192  mov     [rbp+arg_8], ebx
0x180010195  lea     rcx, [rbp+arg_18]
0x180010199  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001019e  mov     rdx, [rsi+28h]
0x1800101a2  test    rdx, rdx
0x1800101a5  jnz     short loc_1800101B6
0x1800101a7  mov     [rbp+arg_18], rdx
0x1800101ab  lea     rcx, [rbp+arg_18]
0x1800101af  or      ebx, 4
0x1800101b2  xor     eax, eax
0x1800101b4  jmp     short loc_1800101CD
0x1800101b6  lea     rcx, [rbp+arg_10]
0x1800101ba  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800101bf  lea     rcx, [rbp+arg_10]
0x1800101c3  or      ebx, 108h
0x1800101c9  mov     rax, [rbp+arg_10]
0x1800101cd  mov     [rbp+arg_8], ebx
0x1800101d0  mov     [rdi+28h], rax
0x1800101d4  mov     qword ptr [rcx], 0
0x1800101db  test    bl, 8
0x1800101de  jz      short loc_1800101F0
0x1800101e0  and     ebx, 0FFFFFFF7h
0x1800101e3  mov     [rbp+arg_8], ebx
0x1800101e6  lea     rcx, [rbp+arg_10]
0x1800101ea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800101ef  nop
0x1800101f0  test    bl, 4
0x1800101f3  jz      short loc_180010204
0x1800101f5  and     ebx, 0FFFFFFFBh
0x1800101f8  mov     [rbp+arg_8], ebx
0x1800101fb  lea     rcx, [rbp+arg_18]
0x1800101ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010204  mov     rdx, [rsi+30h]
0x180010208  test    rdx, rdx
0x18001020b  jnz     short loc_18001021C
0x18001020d  mov     [rbp+arg_0], rdx
0x180010211  lea     rcx, [rbp+arg_0]
0x180010215  or      ebx, 10h
0x180010218  xor     eax, eax
0x18001021a  jmp     short loc_180010233
0x18001021c  lea     rcx, [rbp+arg_10]
0x180010220  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180010225  lea     rcx, [rbp+arg_10]
0x180010229  or      ebx, 420h
0x18001022f  mov     rax, [rbp+arg_10]
0x180010233  mov     [rdi+30h], rax
0x180010237  mov     qword ptr [rcx], 0
0x18001023e  test    bl, 20h
0x180010241  jz      short loc_180010250
0x180010243  and     ebx, 0FFFFFFDFh
0x180010246  lea     rcx, [rbp+arg_10]
0x18001024a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001024f  nop
0x180010250  test    bl, 10h
0x180010253  jz      short loc_18001025E
0x180010255  lea     rcx, [rbp+arg_0]
0x180010259  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001025e  mov     eax, [rsi+38h]
0x180010261  mov     [rdi+38h], eax
0x180010264  movups  xmm0, xmmword ptr [rsi+3Ch]
0x180010268  movdqu  xmmword ptr [rdi+3Ch], xmm0
0x18001026d  movzx   eax, word ptr [rsi+4Ch]
0x180010271  mov     [rdi+4Ch], ax
0x180010275  mov     al, [rsi+4Eh]
0x180010278  mov     [rdi+4Eh], al
0x18001027b  mov     al, [rsi+4Fh]
0x18001027e  mov     [rdi+4Fh], al
0x180010281  mov     al, [rsi+50h]
0x180010284  mov     [rdi+50h], al
0x180010287  mov     rax, rdi
0x18001028a  add     rsp, 28h
0x18001028e  pop     rdi
0x18001028f  pop     rsi
0x180010290  pop     rbx
0x180010291  pop     rbp
0x180010292  retn
```
