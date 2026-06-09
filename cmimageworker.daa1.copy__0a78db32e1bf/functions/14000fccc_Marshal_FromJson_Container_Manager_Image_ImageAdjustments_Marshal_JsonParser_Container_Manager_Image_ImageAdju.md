# Marshal::FromJson<Container::Manager::Image::ImageAdjustments,>(Marshal::JsonParser &,Container::Manager::Image::ImageAdjustments *,Marshal::UnmarshalFlags)

- ea: `0x14000fccc`
- end: `0x14000fe45`
- name: `??$FromJson@UImageAdjustments@Image@Manager@Container@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUImageAdjustments@Image@Manager@Container@@W4UnmarshalFlags@0@@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011750`

## callees

- `0x1400020b0`
- `0x140002d4e`
- `0x14000fccc`
- `0x14001a3c4`
- `0x14001fff4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_BYTE *__fastcall Marshal::FromJson<Container::Manager::Image::ImageAdjustments,>(
        __int64 a1,
        Marshal::JsonParser *a2,
        __int64 a3)
{
  char v5; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  _BYTE *result; // rax
  __int64 v10; // rbx
  __int64 *v11; // rdi
  _QWORD *v12; // rax
  void ***v13; // rdi
  unsigned __int64 v14; // rbx
  void **v15; // rbx
  __int64 v16; // rsi
  __int64 v17; // r14
  void **v18; // [rsp+38h] [rbp-C0h] BYREF
  __int128 *v19; // [rsp+40h] [rbp-B8h]
  __int64 *v20; // [rsp+48h] [rbp-B0h]
  __int64 v21[4]; // [rsp+50h] [rbp-A8h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-88h] BYREF
  _BYTE *v23; // [rsp+78h] [rbp-80h]
  __int128 v24; // [rsp+80h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-68h]
  int v26; // [rsp+98h] [rbp-60h]
  _QWORD v27[2]; // [rsp+A0h] [rbp-58h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-38h]
  __int64 v30; // [rsp+C8h] [rbp-30h]
  int v31; // [rsp+D0h] [rbp-28h]
  __int64 v32; // [rsp+D8h] [rbp-20h] BYREF

  v23 = (_BYTE *)a1;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v18 = &Marshal::UnmarshalContext::`vftable';
  v19 = &v24;
  v20 = 0;
  v27[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v27[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,enum Container::Manager::Image::FeatureOperation>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v21[0] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v21[1] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Container::Manager::Image::CommandType,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  try
  {
    v5 = Marshal::Details::ObjectFromJson(
           a2,
           a3,
           (__int64)&v18,
           (__int64 **)&Container::Manager::Image::ImageAdjustments_ClassData,
           v21,
           v27);
    if ( v5 && *((_QWORD *)a2 + 2) != *((_QWORD *)a2 + 1) )
    {
      pExceptionObject = 12;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v6 = v25;
    v25 = 0;
    v7 = *((_QWORD *)&v24 + 1);
    v8 = v24;
    v24 = 0u;
    *(_BYTE *)a1 = v5;
    v20 = 0;
    v19 = 0;
    v18 = 0;
    *(_QWORD *)(a1 + 8) = v8;
    *(_QWORD *)(a1 + 16) = v7;
    *(_QWORD *)(a1 + 24) = v6;
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v18);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v24);
    result = (_BYTE *)a1;
  }
  catch ( Marshal::JsonParser::ParseException )
  {
    v28 = 0;
    v29 = 0;
    v30 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v28, L"$", 1);
    v31 = 13;
    memset(v21, 0, 24);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v21, 1);
    v27[0] = v21;
    v10 = v21[0];
    v11 = (__int64 *)&v28;
    v18 = (void **)v21[0];
    v19 = (__int128 *)v21[0];
    v20 = v21;
    do
    {
      std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(v10, v11);
      v10 += 40;
      v19 = (__int128 *)v10;
      v11 += 5;
    }
    while ( v11 != &v32 );
    v21[1] = v10;
    v12 = v23;
    *v23 = 0;
    v13 = (void ***)(v12 + 1);
    v12[1] = 0;
    v12[2] = 0;
    v12[3] = 0;
    v14 = 0xCCCCCCCCCCCCCCCDuLL * ((v10 - v21[0]) >> 3);
    if ( v14 )
    {
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v13, v14);
      v27[0] = v13;
      v16 = v21[0];
      v17 = v21[1];
      v18 = *v13;
      v15 = v18;
      v19 = (__int128 *)v18;
      v20 = (__int64 *)v13;
      while ( v16 != v17 )
      {
        std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(v15, v16);
        v15 += 5;
        v19 = (__int128 *)v15;
        v16 += 40;
      }
      v13[1] = v15;
    }
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v21);
    `eh vector destructor iterator'(
      &v28,
      0x28u,
      1u,
      std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>);
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x14000fccc  mov     r11, rsp
0x14000fccf  push    rbx
0x14000fcd0  push    rsi
0x14000fcd1  push    rdi
0x14000fcd2  sub     rsp, 0E0h
0x14000fcd9  mov     rax, cs:__security_cookie
0x14000fce0  xor     rax, rsp
0x14000fce3  mov     [rsp+0F8h+var_20], rax
0x14000fceb  mov     rax, r8
0x14000fcee  mov     rdi, rdx
0x14000fcf1  mov     rbx, rcx
0x14000fcf4  mov     [r11-80h], rcx
0x14000fcf8  xor     esi, esi
0x14000fcfa  mov     [rsp+0F8h+var_C8], esi
0x14000fcfe  xorps   xmm0, xmm0
0x14000fd01  movdqu  xmmword ptr [r11-78h], xmm0
0x14000fd07  mov     [r11-68h], rsi
0x14000fd0b  mov     [r11-60h], esi
0x14000fd0f  lea     rcx, ??_7UnmarshalContext@Marshal@@6B@; const Marshal::UnmarshalContext::`vftable'
0x14000fd16  mov     [rsp+0F8h+var_C0], rcx
0x14000fd1b  lea     rcx, [r11-78h]
0x14000fd1f  mov     [rsp+0F8h+var_B8], rcx
0x14000fd24  mov     [rsp+0F8h+var_B0], rsi
0x14000fd29  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::JsonTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>,Marshal::ModifierList<>>>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x14000fd30  mov     [r11-58h], rcx
0x14000fd34  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4FeatureOperation@Image@Manager@Container@@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::JsonTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,Container::Manager::Image::FeatureOperation>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x14000fd3b  mov     [r11-50h], rcx
0x14000fd3f  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$03@std@@A; std::array<Marshal::Details::BaseTypeData const *,4> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>,Marshal::ModifierList<>>,Marshal::ModifiedType<utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x14000fd46  mov     [rsp+0F8h+var_A8], rcx
0x14000fd4b  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4CommandType@Image@Manager@Container@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::BaseTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Container::Manager::Image::CommandType,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x14000fd52  mov     [rsp+0F8h+var_A0], rcx
0x14000fd57  lea     rcx, [r11-58h]
0x14000fd5b  mov     [rsp+0F8h+var_D0], rcx; __int64
0x14000fd60  lea     rcx, [rsp+0F8h+var_A8]
0x14000fd65  mov     [rsp+0F8h+var_D8], rcx; __int64
0x14000fd6a  lea     r9, ?ImageAdjustments_ClassData@Image@Manager@Container@@3UClassData@Marshal@@B; Marshal::ClassData const Container::Manager::Image::ImageAdjustments_ClassData
0x14000fd71  lea     r8, [rsp+0F8h+var_C0]
0x14000fd76  mov     rdx, rax
0x14000fd79  mov     rcx, rdi; this
0x14000fd7c  call    ?ObjectFromJson@Details@Marshal@@YA_NAEAVJsonParser@2@PEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ObjectFromJson(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)
0x14000fd81  mov     r9b, al
0x14000fd84  test    al, al
0x14000fd86  jz      short loc_14000FD96
0x14000fd88  mov     rax, [rdi+8]
0x14000fd8c  cmp     [rdi+10h], rax
0x14000fd90  jnz     loc_14000FE2A
0x14000fd96  mov     r8, [rsp+0F8h+var_68]
0x14000fd9e  mov     [rsp+0F8h+var_68], rsi
0x14000fda6  mov     rdx, [rsp+0F8h+var_70]
0x14000fdae  mov     [rsp+0F8h+var_70], rsi
0x14000fdb6  mov     rcx, [rsp+0F8h+var_78]
0x14000fdbe  mov     [rsp+0F8h+var_78], rsi
0x14000fdc6  mov     [rbx], r9b
0x14000fdc9  mov     [rsp+0F8h+var_B0], rsi
0x14000fdce  mov     [rsp+0F8h+var_B8], rsi
0x14000fdd3  mov     [rsp+0F8h+var_C0], rsi
0x14000fdd8  mov     [rbx+8], rcx
0x14000fddc  mov     [rbx+10h], rdx
0x14000fde0  mov     [rbx+18h], r8
0x14000fde4  mov     [rsp+0F8h+var_C8], 1
0x14000fdec  lea     rcx, [rsp+0F8h+var_C0]
0x14000fdf1  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14000fdf6  nop
0x14000fdf7  lea     rcx, [rsp+0F8h+var_78]
0x14000fdff  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14000fe04  mov     rax, rbx
0x14000fe07  jmp     short loc_14000FE0E
0x14000fe09  mov     rax, [rsp+0F8h+var_80]
0x14000fe0e  mov     rcx, [rsp+0F8h+var_20]
0x14000fe16  xor     rcx, rsp; StackCookie
0x14000fe19  call    __security_check_cookie
0x14000fe1e  add     rsp, 0E0h
0x14000fe25  pop     rdi
0x14000fe26  pop     rsi
0x14000fe27  pop     rbx
0x14000fe28  retn
0x14000fe2a  mov     [rsp+0F8h+pExceptionObject], 0Ch
0x14000fe32  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000fe39  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x14000fe3e  call    _CxxThrowException_0
```
