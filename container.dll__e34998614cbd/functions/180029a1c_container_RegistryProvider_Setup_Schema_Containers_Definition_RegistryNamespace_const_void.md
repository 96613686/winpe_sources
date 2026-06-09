# container::RegistryProvider::Setup(Schema::Containers::Definition::RegistryNamespace const &,void *)

- ea: `0x180029a1c`
- end: `0x180029bb9`
- name: `?Setup@RegistryProvider@container@@YAXAEBURegistryNamespace@Definition@Containers@Schema@@PEAX@Z`
- size: `413`
- prototype: `void __fastcall(container::RegistryProvider **this, const struct Schema::Containers::Definition::RegistryNamespace *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, installer_update`

## callers

- `0x1800063f0`

## callees

- `0x180002af4`
- `0x18000bdec`
- `0x180028a00`
- `0x18002993c`
- `0x180029a1c`
- `0x180029bc0`
- `0x18002a78c`
- `0x18002abc0`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029acc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b8d`

## string_xrefs

- `0x180029ba7`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
void __fastcall container::RegistryProvider::Setup(
        container::RegistryProvider **this,
        const struct Schema::Containers::Definition::RegistryNamespace *a2,
        void *a3)
{
  char *v4; // rbx
  _QWORD *v5; // rax
  const struct Schema::Containers::Definition::RegistrySymlink *v6; // rdx
  const char *v7; // r9
  container::RegistryProvider *v8; // rsi
  container::RegistryProvider *v9; // r14
  container::RegistryProvider *v10; // rsi
  container::RegistryProvider *v11; // r14
  container::RegistryProvider *v12; // rsi
  container::RegistryProvider *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // edx
  _BYTE v22[32]; // [rsp+0h] [rbp-B8h] BYREF
  int ErrorCode; // [rsp+40h] [rbp-78h]
  int v24; // [rsp+44h] [rbp-74h]
  __int64 v25; // [rsp+48h] [rbp-70h]
  char *v26; // [rsp+50h] [rbp-68h]
  const std::exception *v27; // [rsp+58h] [rbp-60h] BYREF
  const wil::ResultException *v28; // [rsp+60h] [rbp-58h] BYREF
  _QWORD v29[3]; // [rsp+68h] [rbp-50h] BYREF
  char v30; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  const struct Schema::Containers::Definition::RegistryNamespace *v33; // [rsp+C8h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+D0h] [rbp+18h] BYREF
  const struct Schema::Containers::Definition::RegistryNamespace *InBuffer; // [rsp+D8h] [rbp+20h] BYREF

  v33 = a2;
  v4 = (char *)container::RegistryProvider::OpenRegistryDriver((container::RegistryProvider *)this);
  v26 = v4;
  v29[1] = 0;
  v5 = operator new(0x60u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  v29[0] = v5;
  BytesReturned = 0;
  InBuffer = v33;
  if ( !DeviceIoControl(v4, 0x220004u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v7);
  v29[2] = &v33;
  v30 = 1;
  v8 = this[6];
  v9 = this[7];
  try
  {
    while ( v8 != v9 )
    {
      container::RegistryProvider::SetupHivestack(v8, v33, v4, v29);
      v8 = (container::RegistryProvider *)((char *)v8 + 104);
    }
    v10 = this[3];
    v11 = this[4];
    while ( v10 != v11 )
    {
      container::RegistryProvider::SetupRedirectionNode(v10, v33, v4, v29);
      v10 = (container::RegistryProvider *)((char *)v10 + 104);
    }
    v12 = *this;
    v13 = this[1];
    while ( v12 != v13 )
    {
      container::RegistryProvider::SetupSymlink(v12, v6);
      v12 = (container::RegistryProvider *)((char *)v12 + 64);
    }
    v30 = 0;
  }
  catch ( const wil::ResultException *v28 )
  {
    BytesReturned = std::vector<Schema::Containers::Definition::RegistrySymlink>::size(this);
    LODWORD(InBuffer) = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v19 + 24);
    v24 = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v20 + 48);
    ErrorCode = wil::ResultException::GetErrorCode(v28);
    ContainerProvider::RegistryNamespaceSetupFailure<long,char const (&)[21],unsigned int,unsigned int,unsigned int>(
      (unsigned int)v22 + 64,
      v21,
      (unsigned int)v22 + 68,
      (unsigned int)v22 + 216,
      (__int64)&BytesReturned);
    throw;
  }
  catch ( const std::exception *v27 )
  {
    BytesReturned = std::vector<Schema::Containers::Definition::RegistrySymlink>::size(this);
    LODWORD(InBuffer) = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v17 + 24);
    v24 = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v18 + 48);
    v25 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v27 + 8LL))(v27);
    ErrorCode = -2147418113;
    ContainerProvider::RegistryNamespaceSetupFailure<long,char const *,unsigned int,unsigned int,unsigned int>(
      (unsigned int)v22 + 64,
      (unsigned int)v22 + 72,
      (unsigned int)v22 + 68,
      (unsigned int)v22 + 216,
      (__int64)&BytesReturned);
    throw;
  }
  catch ( ... )
  {
    BytesReturned = std::vector<Schema::Containers::Definition::RegistrySymlink>::size(this);
    LODWORD(InBuffer) = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v14 + 24);
    ErrorCode = std::vector<Schema::Containers::Definition::RegistryHiveStack>::size(v15 + 48);
    v24 = -2147418113;
    ContainerProvider::RegistryNamespaceSetupFailure<long,char const (&)[18],unsigned int,unsigned int,unsigned int>(
      (unsigned int)v22 + 68,
      v16,
      (unsigned int)v22 + 64,
      (unsigned int)v22 + 216,
      (__int64)&BytesReturned);
    throw;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v29);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x180029a1c  mov     [rsp+arg_8], rdx
0x180029a21  mov     [rsp+arg_0], rcx
0x180029a26  push    rbx
0x180029a27  push    rsi
0x180029a28  push    rdi
0x180029a29  push    r14
0x180029a2b  sub     rsp, 98h
0x180029a32  mov     rdi, rcx
0x180029a35  call    ?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ; container::RegistryProvider::OpenRegistryDriver(void)
0x180029a3a  mov     rbx, rax
0x180029a3d  mov     [rsp+0B8h+var_68], rax
0x180029a42  mov     [rsp+0B8h+var_50], 0
0x180029a4b  mov     [rsp+0B8h+var_48], 0
0x180029a54  mov     ecx, 60h ; '`'; Size
0x180029a59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029a5e  mov     [rax], rax
0x180029a61  mov     [rax+8], rax
0x180029a65  mov     [rax+10h], rax
0x180029a69  mov     word ptr [rax+18h], 101h
0x180029a6f  mov     [rsp+0B8h+var_50], rax
0x180029a74  mov     [rsp+0B8h+BytesReturned], 0
0x180029a7f  mov     rax, [rsp+0B8h+arg_8]
0x180029a87  mov     [rsp+0B8h+InBuffer], rax
0x180029a8f  mov     [rsp+0B8h+lpOverlapped], 0; lpOverlapped
0x180029a98  lea     rax, [rsp+0B8h+BytesReturned]
0x180029aa0  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180029aa5  mov     [rsp+0B8h+nOutBufferSize], 0; nOutBufferSize
0x180029aad  mov     [rsp+0B8h+lpOutBuffer], 0; lpOutBuffer
0x180029ab6  mov     r9d, 8; nInBufferSize
0x180029abc  lea     r8, [rsp+0B8h+InBuffer]; lpInBuffer
0x180029ac4  mov     edx, 220004h; dwIoControlCode
0x180029ac9  mov     rcx, rbx; hDevice
0x180029acc  call    cs:__imp_DeviceIoControl
0x180029ad3  nop     dword ptr [rax+rax+00h]
0x180029ad8  mov     rcx, [rsp+0B8h]; this
0x180029ae0  test    eax, eax
0x180029ae2  jz      loc_180029BA7
0x180029ae8  lea     rax, [rsp+0B8h+arg_8]
0x180029af0  mov     [rsp+0B8h+var_40], rax
0x180029af5  mov     [rsp+0B8h+var_38], 1
0x180029afd  mov     rsi, [rdi+30h]
0x180029b01  mov     r14, [rdi+38h]
0x180029b05  cmp     rsi, r14
0x180029b08  jz      short loc_180029B28
0x180029b0a  lea     r9, [rsp+0B8h+var_50]
0x180029b0f  mov     r8, rbx
0x180029b12  mov     rdx, [rsp+0B8h+arg_8]
0x180029b1a  mov     rcx, rsi
0x180029b1d  call    ?SetupHivestack@RegistryProvider@container@@YAXAEBURegistryHiveStack@Definition@Containers@Schema@@PEAX1AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; container::RegistryProvider::SetupHivestack(Schema::Containers::Definition::RegistryHiveStack const &,void *,void *,std::map<std::wstring,std::wstring> &)
0x180029b22  add     rsi, 68h ; 'h'
0x180029b26  jmp     short loc_180029B05
0x180029b28  mov     rsi, [rdi+18h]
0x180029b2c  mov     r14, [rdi+20h]
0x180029b30  cmp     rsi, r14
0x180029b33  jz      short loc_180029B53
0x180029b35  lea     r9, [rsp+0B8h+var_50]
0x180029b3a  mov     r8, rbx
0x180029b3d  mov     rdx, [rsp+0B8h+arg_8]
0x180029b45  mov     rcx, rsi
0x180029b48  call    ?SetupRedirectionNode@RegistryProvider@container@@YAXAEBURegistryRedirectionNode@Definition@Containers@Schema@@PEAX1AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; container::RegistryProvider::SetupRedirectionNode(Schema::Containers::Definition::RegistryRedirectionNode const &,void *,void *,std::map<std::wstring,std::wstring> const &)
0x180029b4d  add     rsi, 68h ; 'h'
0x180029b51  jmp     short loc_180029B30
0x180029b53  mov     rsi, [rdi]
0x180029b56  mov     rdi, [rdi+8]
0x180029b5a  cmp     rsi, rdi
0x180029b5d  jz      short loc_180029B6D
0x180029b5f  mov     rcx, rsi; this
0x180029b62  call    ?SetupSymlink@RegistryProvider@container@@YAXAEBURegistrySymlink@Definition@Containers@Schema@@@Z; container::RegistryProvider::SetupSymlink(Schema::Containers::Definition::RegistrySymlink const &)
0x180029b67  add     rsi, 40h ; '@'
0x180029b6b  jmp     short loc_180029B5A
0x180029b6d  mov     [rsp+0B8h+var_38], 0
0x180029b75  lea     rcx, [rsp+0B8h+var_50]
0x180029b7a  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180029b7f  nop
0x180029b80  lea     rax, [rbx-1]
0x180029b84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029b88  ja      short loc_180029B99
0x180029b8a  mov     rcx, rbx; hObject
0x180029b8d  call    cs:__imp_CloseHandle
0x180029b94  nop     dword ptr [rax+rax+00h]
0x180029b99  add     rsp, 98h
0x180029ba0  pop     r14
0x180029ba2  pop     rdi
0x180029ba3  pop     rsi
0x180029ba4  pop     rbx
0x180029ba5  retn
0x180029ba7  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029bae  mov     edx, 152h; void *
0x180029bb3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
