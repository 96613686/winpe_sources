# Marshal::Details::ReadXmlVoid<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>(Marshal::XmlReader &,void *,Marshal::UnmarshalContext const &)

- ea: `0x180014ba0`
- end: `0x180014cae`
- name: `??$ReadXmlVoid@U?$optional@UFilesystemNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Details@Marshal@@YA_NAEAUXmlReader@1@PEAXAEBVUnmarshalContext@1@@Z`
- size: `270`
- prototype: `__int64 __fastcall(Marshal::Details *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, registry_config`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x180014ba0`
- `0x18001f2e0`
- `0x18001ff3c`
- `0x18002161c`
- `0x18002186c`

## pseudocode

```c
char __fastcall Marshal::Details::ReadXmlVoid<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>(
        Marshal::Details *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v8[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v9[2]; // [rsp+50h] [rbp-39h] BYREF
  _OWORD v10[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v11; // [rsp+80h] [rbp-9h]
  __int64 v12; // [rsp+88h] [rbp-1h] BYREF
  __int128 v13; // [rsp+90h] [rbp+7h]
  __int128 v14; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+27h]

  v10[1] = _mm_load_si128((const __m128i *)&_xmm);
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v10[0] = 0;
  LOWORD(v10[0]) = 0;
  v13 = 0;
  v15 = 0;
  Schema::Containers::Definition::FilesystemNamespace::operator=(a2, v10);
  *(_BYTE *)(a2 + 88) = 1;
  std::vector<Schema::Containers::Definition::BatchedBinding>::_Tidy(&v14);
  std::vector<Schema::Containers::Definition::FilesystemLayer>::_Tidy(&v12);
  std::wstring::~wstring(v10);
  if ( !*(_BYTE *)(a2 + 88) )
    __fastfail(5u);
  v8[0] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  v8[1] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v9[0] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  v9[1] = (__int64)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::MountManagerNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NamedPipeNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::ObjectNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::RegistryNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NetworkNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::DeviceNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::HostFiles>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
  return Marshal::Details::ReadObjectXml(
           this,
           v6,
           a2,
           a3,
           (__int64)&Schema::Containers::Definition::FilesystemNamespace_ClassData,
           v9,
           v8);
}

```

## disassembly

```asm
0x180014ba0  mov     [rsp-8+arg_18], rbx
0x180014ba5  push    rbp
0x180014ba6  push    rsi
0x180014ba7  push    rdi
0x180014ba8  lea     rbp, [rsp-47h]
0x180014bad  sub     rsp, 0D0h
0x180014bb4  mov     rax, cs:__security_cookie
0x180014bbb  xor     rax, rsp
0x180014bbe  mov     [rbp+57h+var_20], rax
0x180014bc2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180014bca  xor     eax, eax
0x180014bcc  mov     rbx, rdx
0x180014bcf  movdqa  [rbp+57h+var_70], xmm1
0x180014bd4  xorps   xmm0, xmm0
0x180014bd7  mov     [rbp+57h+var_60], rax
0x180014bdb  xorps   xmm1, xmm1
0x180014bde  mov     [rbp+57h+var_58], rax
0x180014be2  mov     rdi, rcx
0x180014be5  movdqa  [rbp+57h+var_40], xmm1
0x180014bea  movups  [rbp+57h+var_80], xmm0
0x180014bee  lea     rdx, [rbp+57h+var_80]
0x180014bf2  mov     word ptr [rbp+57h+var_80], ax
0x180014bf6  mov     rcx, rbx
0x180014bf9  movdqa  [rbp+57h+var_50], xmm0
0x180014bfe  mov     rsi, r8
0x180014c01  mov     [rbp+57h+var_30], rax
0x180014c05  call    ??4FilesystemNamespace@Definition@Containers@Schema@@QEAAAEAU0123@$$QEAU0123@@Z; Schema::Containers::Definition::FilesystemNamespace::operator=(Schema::Containers::Definition::FilesystemNamespace &&)
0x180014c0a  lea     rcx, [rbp+57h+var_40]
0x180014c0e  mov     byte ptr [rbx+58h], 1
0x180014c12  call    ?_Tidy@?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::BatchedBinding>::_Tidy(void)
0x180014c17  lea     rcx, [rbp+57h+var_58]
0x180014c1b  call    ?_Tidy@?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::FilesystemLayer>::_Tidy(void)
0x180014c20  lea     rcx, [rbp+57h+var_80]
0x180014c24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014c29  cmp     byte ptr [rbx+58h], 0
0x180014c2d  jnz     short loc_180014C36
0x180014c2f  mov     ecx, 5
0x180014c34  int     29h; Win8: RtlFailFast(ecx)
0x180014c36  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::XmlTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180014c3d  mov     r9, rsi
0x180014c40  mov     [rbp+57h+var_A0], rax
0x180014c44  mov     r8, rbx
0x180014c47  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::NamedPipeSymlink>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180014c4e  mov     rcx, rdi; this
0x180014c51  mov     [rbp+57h+var_98], rax
0x180014c55  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x180014c5c  mov     [rbp+57h+var_90], rax
0x180014c60  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@U?$optional@UJobNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@U?$optional@UFilesystemNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UMountManagerNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UNamedPipeNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UObjectNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@URegistryNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UNetworkNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UDeviceNamespace@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@U?$optional@UHostFiles@Definition@Containers@Schema@@@vmstd@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$08@std@@A; std::array<Marshal::Details::XmlTypeData const *,9> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::JobNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::FilesystemNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::MountManagerNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NamedPipeNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::ObjectNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::RegistryNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::NetworkNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::DeviceNamespace>,Marshal::ModifierList<>>,Marshal::ModifiedType<vmstd::optional<Schema::Containers::Definition::HostFiles>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180014c67  mov     [rbp+57h+var_88], rax
0x180014c6b  lea     rax, [rbp+57h+var_A0]
0x180014c6f  mov     [rsp+0E0h+var_B0], rax; __int64
0x180014c74  lea     rax, [rbp+57h+var_90]
0x180014c78  mov     [rsp+0E0h+var_B8], rax; __int64
0x180014c7d  lea     rax, ?FilesystemNamespace_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::FilesystemNamespace_ClassData
0x180014c84  mov     [rsp+0E0h+var_C0], rax; __int64
0x180014c89  call    ?ReadObjectXml@Details@Marshal@@YA_NAEAUXmlReader@2@HPEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ReadObjectXml(Marshal::XmlReader &,int,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180014c8e  mov     rcx, [rbp+57h+var_20]
0x180014c92  xor     rcx, rsp; StackCookie
0x180014c95  call    __security_check_cookie
0x180014c9a  mov     rbx, [rsp+0E0h+arg_18]
0x180014ca2  add     rsp, 0D0h
0x180014ca9  pop     rdi
0x180014caa  pop     rsi
0x180014cab  pop     rbp
0x180014cac  retn
```
