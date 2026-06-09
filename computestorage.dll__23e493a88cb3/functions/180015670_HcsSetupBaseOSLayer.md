# HcsSetupBaseOSLayer

- ea: `0x180015670`
- end: `0x1800158fe`
- name: `HcsSetupBaseOSLayer`
- size: `654`
- prototype: `HRESULT __stdcall(PCWSTR layerPath, HANDLE vhdHandle, PCWSTR options)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002690`
- `0x180004bb4`
- `0x1800084b4`
- `0x180008fac`
- `0x180009a38`
- `0x1800127bc`
- `0x180012818`
- `0x1800137fc`
- `0x180015670`
- `0x18001ea88`
- `0x180028830`
- `0x180029b08`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001582e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001582e`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180015779`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180015779`

## string_xrefs

- `0x1800158b1`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x1800158d7`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x1800158eb`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcsSetupBaseOSLayer(PCWSTR layerPath, HANDLE vhdHandle, PCWSTR options)
{
  __int64 v5; // rax
  const struct Schema::Options::OsLayerOptions *v6; // r9
  const char *v7; // r9
  HRESULT result; // eax
  unsigned int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-308h]
  HANDLE hObject; // [rsp+80h] [rbp-2A8h]
  __int64 v12; // [rsp+88h] [rbp-2A0h]
  __int64 v13; // [rsp+90h] [rbp-298h] BYREF
  __int128 v14; // [rsp+98h] [rbp-290h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-280h]
  __int128 v16; // [rsp+B0h] [rbp-278h]
  WCHAR v17[8]; // [rsp+C0h] [rbp-268h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-258h]
  __int128 v19; // [rsp+E0h] [rbp-248h]
  __int128 v20; // [rsp+F0h] [rbp-238h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  *(_OWORD *)v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v17[0] = 0;
  v19 = 0;
  v20 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v5 = -1;
  do
    ++v5;
  while ( options[v5] );
  hObject = (HANDLE)options;
  v12 = v5;
  try
  {
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::Options::OsLayerOptions,>();
    if ( (char *)vhdHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v9 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)v9,
        v10);
    }
    OsImageUtilities::ProcessOsLayer(layerPath, v17, (const struct PartitionInfo *)&v13, v6);
    std::vector<Schema::Common::Resources::Layer>::_Tidy(&v14);
    std::wstring::~wstring(v17);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0xD7,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v7);
  }
  return result;
}

```

## disassembly

```asm
0x180015670  mov     r11, rsp
0x180015673  mov     [r11+18h], rbx
0x180015677  mov     [r11+20h], rsi
0x18001567b  push    rdi
0x18001567c  sub     rsp, 320h
0x180015683  mov     rax, cs:__security_cookie
0x18001568a  xor     rax, rsp
0x18001568d  mov     [rsp+328h+var_18], rax
0x180015695  mov     rbx, rdx
0x180015698  mov     rdi, rcx
0x18001569b  xorps   xmm0, xmm0
0x18001569e  movups  xmmword ptr [rsp+328h+var_268], xmm0
0x1800156a6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800156ae  movdqa  [rsp+328h+var_258], xmm1
0x1800156b7  xor     esi, esi
0x1800156b9  mov     [rsp+328h+var_268], si
0x1800156c1  movups  [rsp+328h+var_248], xmm0
0x1800156c9  movups  [rsp+328h+var_238], xmm0
0x1800156d1  mov     [r11-298h], rsi
0x1800156d8  movdqu  [rsp+328h+var_290], xmm0
0x1800156e1  mov     [r11-280h], rsi
0x1800156e8  movups  [rsp+328h+var_278], xmm0
0x1800156f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800156f4  inc     rax
0x1800156f7  cmp     [r8+rax*2], si
0x1800156fc  jnz     short loc_1800156F4
0x1800156fe  mov     [rsp+328h+hObject], r8
0x180015706  mov     [rsp+328h+var_2A0], rax
0x18001570e  lea     rdx, [rsp+328h+var_298]
0x180015716  lea     rcx, [rsp+328h+hObject]
0x18001571e  call    ??$FromJsonStrictThrow@UOsLayerOptions@Options@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUOsLayerOptions@Options@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::Options::OsLayerOptions,>(std::basic_string_view<ushort>,Schema::Options::OsLayerOptions *,Marshal::UnmarshalFlags)
0x180015723  mov     eax, dword ptr [rsp+328h+var_298]
0x18001572a  cmp     eax, 1
0x18001572d  jnz     short loc_180015741
0x18001572f  lea     rax, [rbx+1]
0x180015733  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015739  jz      loc_18001589C
0x18001573f  jmp     short loc_180015761
0x180015741  test    eax, eax
0x180015743  jnz     short loc_180015758
0x180015745  lea     rax, [rbx-1]
0x180015749  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001574d  jbe     loc_1800158C2
0x180015753  jmp     loc_18001583A
0x180015758  cmp     eax, 1
0x18001575b  jnz     loc_18001583A
0x180015761  mov     [rsp+328h+DiskPathSizeInBytes], 208h
0x180015769  lea     r8, [rsp+328h+DiskPath]; DiskPath
0x180015771  lea     rdx, [rsp+328h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180015776  mov     rcx, rbx; VirtualDiskHandle
0x180015779  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180015780  nop     dword ptr [rax+rax+00h]
0x180015785  mov     rcx, [rsp+328h]; this
0x18001578d  test    eax, eax
0x18001578f  jnz     loc_1800158E8
0x180015795  mov     [rsp+328h+hObject], rsi
0x18001579d  lea     rdx, [rsp+328h+DiskPath]
0x1800157a5  lea     rcx, [rsp+328h+hObject]
0x1800157ad  call    ?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z; OpenDisk(ushort const *,ulong)
0x1800157b2  nop
0x1800157b3  mov     rax, qword ptr [rsp+328h+var_278]
0x1800157bb  mov     [rsp+328h+var_308], rax
0x1800157c0  mov     rax, qword ptr [rsp+328h+var_278+8]
0x1800157c8  mov     [rsp+328h+var_300], rax
0x1800157cd  lea     r9, [rsp+328h+var_308]
0x1800157d2  mov     rdx, [rsp+328h+hObject]
0x1800157da  lea     rcx, [rsp+328h+var_2F8]
0x1800157df  call    ?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z; FormatDisk(void *,ushort const *,_GUID)
0x1800157e4  mov     rbx, rax
0x1800157e7  mov     rdx, rax
0x1800157ea  lea     rcx, [rsp+328h+var_268]
0x1800157f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800157f7  movups  xmm0, xmmword ptr [rbx+20h]
0x1800157fb  movdqu  [rsp+328h+var_248], xmm0
0x180015804  movups  xmm1, xmmword ptr [rbx+30h]
0x180015808  movdqu  [rsp+328h+var_238], xmm1
0x180015811  lea     rcx, [rsp+328h+var_2F8]
0x180015816  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001581b  nop
0x18001581c  mov     rcx, [rsp+328h+hObject]; hObject
0x180015824  lea     rax, [rcx-1]
0x180015828  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001582c  ja      short loc_18001583A
0x18001582e  call    cs:__imp_CloseHandle
0x180015835  nop     dword ptr [rax+rax+00h]
0x18001583a  lea     r8, [rsp+328h+var_298]; struct PartitionInfo *
0x180015842  lea     rdx, [rsp+328h+var_268]; PCWSTR
0x18001584a  mov     rcx, rdi; pszPathIn
0x18001584d  call    ?ProcessOsLayer@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@AEBUOsLayerOptions@Options@Schema@@@Z; OsImageUtilities::ProcessOsLayer(ushort const *,PartitionInfo const &,Schema::Options::OsLayerOptions const &)
0x180015852  nop
0x180015853  lea     rcx, [rsp+328h+var_290]
0x18001585b  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180015860  nop
0x180015861  lea     rcx, [rsp+328h+var_268]
0x180015869  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001586e  xor     eax, eax
0x180015870  jmp     short loc_180015876
0x180015872  mov     eax, [rsp+328h+DiskPathSizeInBytes]
0x180015876  mov     rcx, [rsp+328h+var_18]
0x18001587e  xor     rcx, rsp; StackCookie
0x180015881  call    __security_check_cookie
0x180015886  lea     r11, [rsp+328h+var_8]
0x18001588e  mov     rbx, [r11+20h]
0x180015892  mov     rsi, [r11+28h]
0x180015896  mov     rsp, r11
0x180015899  pop     rdi
0x18001589a  retn
0x18001589c  mov     ecx, 80070057h
0x1800158a1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800158a6  mov     r9d, eax; char *
0x1800158a9  mov     rcx, [rsp+328h]; this
0x1800158b1  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800158b8  mov     edx, 0C2h; void *
0x1800158bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800158c2  mov     ecx, 80070057h
0x1800158c7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800158cc  mov     r9d, eax; char *
0x1800158cf  mov     rcx, [rsp+328h]; this
0x1800158d7  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800158de  mov     edx, 0C8h; void *
0x1800158e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800158e8  mov     r9d, eax; char *
0x1800158eb  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800158f2  mov     edx, 0CFh; void *
0x1800158f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
