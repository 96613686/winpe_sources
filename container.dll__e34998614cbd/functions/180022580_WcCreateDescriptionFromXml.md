# WcCreateDescriptionFromXml

- ea: `0x180022580`
- end: `0x1800227b1`
- name: `WcCreateDescriptionFromXml`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180002ee4`
- `0x18000362c`
- `0x1800051b0`
- `0x18000ca10`
- `0x18000cf64`
- `0x18000d028`
- `0x18000dc48`
- `0x180010418`
- `0x180012b10`
- `0x180012b30`
- `0x1800130d8`
- `0x18001acbc`
- `0x18001e7bc`
- `0x180020bc4`
- `0x180022008`
- `0x180022014`
- `0x1800221bc`
- `0x1800224a0`
- `0x180022580`

## string_xrefs

- `0x180022618`: `ReadXmlString`
- `0x18002279e`: `onecore\base\gendrv\silos\container\description_xml.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WcCreateDescriptionFromXml(__int64 a1, Schema::Containers::Definition::Namespace **a2)
{
  void *v4; // r15
  Schema::Containers::Definition::Namespace *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  __int128 *v11; // rcx
  __int64 v12; // rdi
  __int64 i; // rbx
  const char *v14; // r9
  __int64 result; // rax
  unsigned int v16; // [rsp+20h] [rbp-1E8h]
  unsigned int v17; // [rsp+30h] [rbp-1D8h] BYREF
  Schema::Containers::Definition::Namespace *v18; // [rsp+38h] [rbp-1D0h]
  _QWORD v19[2]; // [rsp+40h] [rbp-1C8h] BYREF
  IXmlReaderInput v20; // [rsp+50h] [rbp-1B8h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-1B0h] BYREF
  __int128 v22; // [rsp+70h] [rbp-198h] BYREF
  __int64 v23; // [rsp+80h] [rbp-188h]
  unsigned __int64 v24; // [rsp+88h] [rbp-180h]
  _QWORD v25[42]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  try
  {
    *a2 = 0;
    v4 = operator new(0x258u);
    memset_0(v4, 0, 0x258u);
    v5 = (Schema::Containers::Definition::Namespace *)Schema::Containers::Definition::Container::Container((Schema::Containers::Definition::Container *)v4);
    v18 = v5;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a1 + 2 * v6) );
    std::wstring::_Construct<1,unsigned short const *>(&v22);
    wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v25,
      "ReadXmlString",
      v7,
      v8);
    v25[0] = &ContainerProvider::ReadXmlString::`vftable';
    ContainerProvider::ReadXmlString::StartActivity((ContainerProvider::ReadXmlString *)v25);
    v11 = &v22;
    if ( v24 > 7 )
      v11 = (__int128 *)v22;
    v19[0] = v11;
    v19[1] = v23;
    Marshal::FromXmlString<Schema::Containers::Definition::Container,>(&v20, (__int64)v19, v9, v10, (__int64)v5, 6);
    if ( !LOBYTE(v20.lpVtbl) )
    {
      v12 = std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Unchecked_end(v21);
      for ( i = std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Unchecked_begin(v21); i != v12; i += 40 )
      {
        v17 = *(_DWORD *)(i + 32);
        v19[0] = std::wstring::c_str(i);
        ContainerProvider::ReadXmlString::XmlParseFailure<unsigned short const *,unsigned long>(v25, v19, &v17);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\description_xml.cpp",
        (const char *)0x5B9,
        v16);
    }
    wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v25, 0);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>(v21);
    v25[0] = &ContainerProvider::ReadXmlString::`vftable';
    wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v25);
    wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v25);
    std::wstring::~wstring(&v22);
    v18 = 0;
    *a2 = v5;
    result = 0;
  }
  catch ( ... )
  {
    v17 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\container\\description_xml_i.cpp",
            v14);
    if ( v18 )
    {
      Schema::Containers::Definition::Namespace::~Namespace(v18);
      operator delete(v18, 0x258u);
    }
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x180022580  mov     [rsp+arg_10], rbx
0x180022585  mov     [rsp+arg_18], rsi
0x18002258a  push    rdi
0x18002258b  push    r14
0x18002258d  push    r15
0x18002258f  sub     rsp, 1F0h
0x180022596  mov     rax, cs:__security_cookie
0x18002259d  xor     rax, rsp
0x1800225a0  mov     [rsp+208h+var_28], rax
0x1800225a8  mov     r14, rdx
0x1800225ab  mov     rdi, rcx
0x1800225ae  xor     ebx, ebx
0x1800225b0  mov     [rsp+208h+var_1D0], rbx
0x1800225b5  mov     [rdx], rbx
0x1800225b8  mov     esi, 258h
0x1800225bd  mov     ecx, esi; Size
0x1800225bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800225c4  mov     r15, rax
0x1800225c7  mov     r8d, esi; Size
0x1800225ca  xor     edx, edx; Val
0x1800225cc  mov     rcx, rax; void *
0x1800225cf  call    memset_0
0x1800225d4  mov     rcx, r15; this
0x1800225d7  call    ??0Container@Definition@Containers@Schema@@QEAA@XZ; Schema::Containers::Definition::Container::Container(void)
0x1800225dc  mov     rsi, rax
0x1800225df  mov     [rsp+208h+var_1D0], rax
0x1800225e4  xorps   xmm0, xmm0
0x1800225e7  movups  [rsp+208h+var_198], xmm0
0x1800225ec  mov     [rsp+208h+var_188], rbx
0x1800225f4  mov     [rsp+208h+var_180], rbx
0x1800225fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022600  inc     r8
0x180022603  cmp     [rdi+r8*2], bx
0x180022608  jnz     short loc_180022600
0x18002260a  mov     rdx, rdi
0x18002260d  lea     rcx, [rsp+208h+var_198]
0x180022612  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022617  nop
0x180022618  lea     rdx, aReadxmlstring; "ReadXmlString"
0x18002261f  lea     rcx, [rsp+208h+var_178]
0x180022627  call    ??0?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002262c  lea     rdi, ??_7ReadXmlString@ContainerProvider@@6B@; const ContainerProvider::ReadXmlString::`vftable'
0x180022633  mov     [rsp+208h+var_178], rdi
0x18002263b  lea     rcx, [rsp+208h+var_178]; this
0x180022643  call    ?StartActivity@ReadXmlString@ContainerProvider@@QEAAXXZ; ContainerProvider::ReadXmlString::StartActivity(void)
0x180022648  nop
0x180022649  lea     rcx, [rsp+208h+var_198]
0x18002264e  cmp     [rsp+208h+var_180], 7
0x180022657  cmova   rcx, qword ptr [rsp+208h+var_198]
0x18002265d  mov     rax, [rsp+208h+var_188]
0x180022665  mov     [rsp+208h+var_1C8], rcx
0x18002266a  mov     [rsp+208h+var_1C0], rax
0x18002266f  mov     [rsp+208h+var_1E0], 6
0x180022677  mov     qword ptr [rsp+208h+var_1E8], rsi; unsigned int
0x18002267c  lea     rdx, [rsp+208h+var_1C8]
0x180022681  lea     rcx, [rsp+208h+var_1B8]
0x180022686  call    ??$FromXmlString@UContainer@Definition@Containers@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEBG_NPEAUContainer@Definition@Containers@Schema@@W4UnmarshalFlags@0@@Z; Marshal::FromXmlString<Schema::Containers::Definition::Container,>(std::basic_string_view<ushort>,ushort const *,bool,Schema::Containers::Definition::Container *,Marshal::UnmarshalFlags)
0x18002268b  nop
0x18002268c  cmp     byte ptr [rsp+208h+var_1B8], bl
0x180022690  jnz     short loc_1800226EF
0x180022692  lea     rcx, [rsp+208h+var_1B0]
0x180022697  call    ?_Unchecked_end@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@QEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@2@XZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Unchecked_end(void)
0x18002269c  mov     rdi, rax
0x18002269f  lea     rcx, [rsp+208h+var_1B0]
0x1800226a4  call    ?_Unchecked_begin@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@QEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@2@XZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Unchecked_begin(void)
0x1800226a9  mov     rbx, rax
0x1800226ac  cmp     rax, rdi
0x1800226af  jz      loc_180022790
0x1800226b5  mov     ecx, [rbx+20h]
0x1800226b8  mov     [rsp+208h+var_1D8], ecx
0x1800226bc  mov     rcx, rbx
0x1800226bf  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800226c4  mov     [rsp+208h+var_1C8], rax
0x1800226c9  lea     r8, [rsp+208h+var_1D8]
0x1800226ce  lea     rdx, [rsp+208h+var_1C8]
0x1800226d3  lea     rcx, [rsp+208h+var_178]
0x1800226db  call    ??$XmlParseFailure@PEBGK@ReadXmlString@ContainerProvider@@QEAAX$$QEAPEBG$$QEAK@Z; ContainerProvider::ReadXmlString::XmlParseFailure<ushort const *,ulong>(ushort const * &&,ulong &&)
0x1800226e0  add     rbx, 28h ; '('
0x1800226e4  cmp     rbx, rdi
0x1800226e7  jz      loc_180022790
0x1800226ed  jmp     short loc_1800226B5
0x1800226ef  xor     edx, edx
0x1800226f1  lea     rcx, [rsp+208h+var_178]
0x1800226f9  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800226fe  nop
0x1800226ff  lea     rcx, [rsp+208h+var_1B0]
0x180022704  call    ??1?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,Marshal::UnmarshalError>>(void)
0x180022709  nop
0x18002270a  mov     [rsp+208h+var_178], rdi
0x180022712  lea     rcx, [rsp+208h+var_178]
0x18002271a  call    ?Destroy@?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002271f  lea     rcx, [rsp+208h+var_178]
0x180022727  call    ??1?$ActivityBase@VContainerProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002272c  nop
0x18002272d  lea     rcx, [rsp+208h+var_198]
0x180022732  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022737  mov     [rsp+208h+var_1D0], rbx
0x18002273c  mov     [r14], rsi
0x18002273f  xor     eax, eax
0x180022741  jmp     short loc_180022766
0x180022743  mov     rdi, [rsp+208h+var_1D0]
0x180022748  test    rdi, rdi
0x18002274b  jz      short loc_180022762
0x18002274d  mov     rcx, rdi; this
0x180022750  call    ??1Namespace@Definition@Containers@Schema@@QEAA@XZ; Schema::Containers::Definition::Namespace::~Namespace(void)
0x180022755  mov     edx, 258h; unsigned __int64
0x18002275a  mov     rcx, rdi; void *
0x18002275d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022762  mov     eax, [rsp+208h+var_1D8]
0x180022766  mov     rcx, [rsp+208h+var_28]
0x18002276e  xor     rcx, rsp; StackCookie
0x180022771  call    __security_check_cookie
0x180022776  lea     r11, [rsp+208h+var_18]
0x18002277e  mov     rbx, [r11+30h]
0x180022782  mov     rsi, [r11+38h]
0x180022786  mov     rsp, r11
0x180022789  pop     r15
0x18002278b  pop     r14
0x18002278d  pop     rdi
0x18002278e  retn
0x180022790  mov     rcx, [rsp+208h]; this
0x180022798  mov     r9d, 5B9h; char *
0x18002279e  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\container"...
0x1800227a5  mov     edx, 37h ; '7'; void *
0x1800227aa  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
