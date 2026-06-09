# RepoMan::Schema::CleanupScripts(void)

- ea: `0x180008120`
- end: `0x180008571`
- name: `?CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ`
- size: `1105`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180008120`
- `0x180008574`
- `0x180008654`
- `0x18019a840`
- `0x18019a89c`
- `0x18019a908`
- `0x18019a984`
- `0x18019ada4`

## string_xrefs

- `0x1800081bc`: `delete from PackagesToPaths where PackagesToPaths.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x1800081e5`: `delete from PackagesToApps where PackagesToApps.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x18000820d`: `delete from AppsToSKUs where AppsToSKUs.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x180008236`: `delete from SKUs where SKUs.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x180008259`: `delete from Apps where Apps.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x18000827d`: `delete from Packages where Packages.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x1800082a1`: `delete from Patches where Patches.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x1800082c5`: `delete from BlockSource where BlockSource.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x1800082e9`: `delete from Blocks where Blocks.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x180008311`: `delete from Files where Files.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x180008337`: `delete from Media where Media.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n    where Operations.build_id is null\n);`
- `0x180008363`: `delete from Builds where Builds.build_id in (\n    select Builds.build_id from Builds\n        left outer join Operations on\n            Operations.build_id == Builds.build_id\n        left outer join FileTasks on\n            FileTasks.build_id == Builds.build_id\n        where\n            Operations.build_id is null and\n            FileTasks.build_id is null\n);`
- `0x180008392`: `delete from Paths where Paths.path_id in (\n    select paths.path_id from Paths\n        left outer join PackagesToPaths on\n            PackagesToPaths.path_id == Paths.path_id\n        left outer join patches on\n            patches.path_id == Paths.path_id\n        left outer join files as a on\n            a.source_path == Paths.path_id\n        left outer join files as b on\n            b.target_path == paths.path_id\n        left outer join FileTasks on\n            FileTasks.path_id == pa`
- `0x1800083c1`: `delete from Hashes where Hashes.hash_id in (\n    select Hashes.hash_id from Hashes\n        left outer join Files on\n            Files.hash_id == Hashes.hash_id\n        left outer join Patches on\n            Patches.hash_id == Hashes.hash_id\n        left outer join Blocks on\n            Blocks.hash_id == Hashes.hash_id\n        left outer join FileTasks on\n            FileTasks.hash_id == Hashes.hash_id\n        left outer join BlockSource on\n            BlockSource.hash_id == Hashes.has`
- `0x1800083f0`: `delete from Cultures where Cultures.culture_id in (\n    select Cultures.culture_id from Cultures\n        left outer join Packages on\n            Packages.culture_id == Cultures.culture_id\n        left outer join SKUs on\n            SKUs.culture_id == Cultures.culture_id\n    where\n        Packages.culture_id is null and\n        SKUs.culture_id is null\n);`
- `0x18000841d`: `delete from Algorithms where Algorithms.algorithm_id in (\n    select Algorithms.algorithm_id from Algorithms\n    left outer join Hashes on\n        Hashes.algorithm_id == Algorithms.algorithm_id\n    where Hashes.algorithm_id is null\n);`
- `0x18000844a`: `delete from Digests where Digests.digest_id in (\n    select Digests.digest_id from Digests\n    left outer join Hashes on\n        Hashes.digest_id == Digests.digest_id\n    where Hashes.digest_id is null\n);`
- `0x180008477`: `delete from directories where Directories.directory_id in (\n    select directories.directory_id from directories\n    left outer join paths on\n        paths.directory_id == Directories.directory_id\n    where Paths.path_id is null\n);`
- `0x1800084a4`: `delete from Families where Families.family_id in (\n    select Families.family_id from Families\n    left outer join Builds on\n        builds.family_id == Families.family_id\n    where\n        Builds.family_id is null\n);`
- `0x1800084d1`: `delete from Architectures where Architectures.arch_id in (\n    select Architectures.arch_id from Architectures\n    left outer join Builds on\n        Builds.arch_id == Architectures.arch_id\n    where\n        Builds.arch_id is null\n);`
- `0x1800084fd`: `delete from Flavors where Flavors.flavor_id in (\n    select Flavors.flavor_id from Flavors\n    left outer join Builds on\n        Builds.flavor_id == Flavors.flavor_id\n    where\n        Builds.flavor_id is null\n);`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int128 *RepoMan::Schema::CleanupScripts()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v2[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v3[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v4[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v5[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v6[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v7[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v8[2]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v9[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v10[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v11[2]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v12[2]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v13[2]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v14[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v15[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v16[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v17[2]; // [rsp+210h] [rbp+110h] BYREF
  _OWORD v18[2]; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v19[2]; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v20[2]; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v21[2]; // [rsp+290h] [rbp+190h] BYREF
  _OWORD v22[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v23; // [rsp+2D0h] [rbp+1D0h] BYREF

  if ( __TSS0__1__CleanupScripts_Schema_RepoMan__MEBAAEBV__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__std__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__CleanupScripts_Schema_RepoMan__MEBAAEBV__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__std__XZ_4HA);
    if ( __TSS0__1__CleanupScripts_Schema_RepoMan__MEBAAEBV__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__std__XZ_4HA == -1 )
    {
      memset(v2, 0, sizeof(v2));
      std::string::_Construct<1,char const *>(
        v2,
        "delete from PackagesToPaths where PackagesToPaths.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xE8u);
      memset(v3, 0, sizeof(v3));
      std::string::_Construct<1,char const *>(
        v3,
        "delete from PackagesToApps where PackagesToApps.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xE6u);
      memset(v4, 0, sizeof(v4));
      std::string::_Construct<1,char const *>(
        v4,
        "delete from AppsToSKUs where AppsToSKUs.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xDEu);
      memset(v5, 0, sizeof(v5));
      std::string::_Construct<1,char const *>(
        v5,
        "delete from SKUs where SKUs.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD2u);
      memset(v6, 0, sizeof(v6));
      std::string::_Construct<1,char const *>(
        v6,
        "delete from Apps where Apps.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD2u);
      memset(v7, 0, sizeof(v7));
      std::string::_Construct<1,char const *>(
        v7,
        "delete from Packages where Packages.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xDAu);
      memset(v8, 0, sizeof(v8));
      std::string::_Construct<1,char const *>(
        v8,
        "delete from Patches where Patches.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD8u);
      memset(v9, 0, sizeof(v9));
      std::string::_Construct<1,char const *>(
        v9,
        "delete from BlockSource where BlockSource.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xE0u);
      memset(v10, 0, sizeof(v10));
      std::string::_Construct<1,char const *>(
        v10,
        "delete from Blocks where Blocks.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD6u);
      memset(v11, 0, sizeof(v11));
      std::string::_Construct<1,char const *>(
        v11,
        "delete from Files where Files.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD4u);
      memset(v12, 0, sizeof(v12));
      std::string::_Construct<1,char const *>(
        v12,
        "delete from Media where Media.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "    where Operations.build_id is null\n"
        ");",
        0xD4u);
      memset(v13, 0, sizeof(v13));
      std::string::_Construct<1,char const *>(
        v13,
        "delete from Builds where Builds.build_id in (\n"
        "    select Builds.build_id from Builds\n"
        "        left outer join Operations on\n"
        "            Operations.build_id == Builds.build_id\n"
        "        left outer join FileTasks on\n"
        "            FileTasks.build_id == Builds.build_id\n"
        "        where\n"
        "            Operations.build_id is null and\n"
        "            FileTasks.build_id is null\n"
        ");",
        0x168u);
      memset(v14, 0, sizeof(v14));
      std::string::_Construct<1,char const *>(
        v14,
        "delete from Paths where Paths.path_id in (\n"
        "    select paths.path_id from Paths\n"
        "        left outer join PackagesToPaths on\n"
        "            PackagesToPaths.path_id == Paths.path_id\n"
        "        left outer join patches on\n"
        "            patches.path_id == Paths.path_id\n"
        "        left outer join files as a on\n"
        "            a.source_path == Paths.path_id\n"
        "        left outer join files as b on\n"
        "            b.target_path == paths.path_id\n"
        "        left outer join FileTasks on\n"
        "            FileTasks.path_id == paths.path_id\n"
        "    where\n"
        "        PackagesToPaths.id is null and\n"
        "        patches.rowid is null and\n"
        "        a.file_id is null and\n"
        "        b.file_id is null and\n"
        "        FileTasks.path_id is null\n"
        ");",
        0x2A8u);
      memset(v15, 0, sizeof(v15));
      std::string::_Construct<1,char const *>(
        v15,
        "delete from Hashes where Hashes.hash_id in (\n"
        "    select Hashes.hash_id from Hashes\n"
        "        left outer join Files on\n"
        "            Files.hash_id == Hashes.hash_id\n"
        "        left outer join Patches on\n"
        "            Patches.hash_id == Hashes.hash_id\n"
        "        left outer join Blocks on\n"
        "            Blocks.hash_id == Hashes.hash_id\n"
        "        left outer join FileTasks on\n"
        "            FileTasks.hash_id == Hashes.hash_id\n"
        "        left outer join BlockSource on\n"
        "            BlockSource.hash_id == Hashes.hash_id\n"
        "    where\n"
        "        Files.hash_id is null and\n"
        "        Patches.hash_id is null and\n"
        "        Blocks.hash_id is null and\n"
        "        FileTasks.hash_id is null and\n"
        "        BlockSource.hash_id is null\n"
        ");",
        0x2ADu);
      memset(v16, 0, sizeof(v16));
      std::string::_Construct<1,char const *>(
        v16,
        "delete from Cultures where Cultures.culture_id in (\n"
        "    select Cultures.culture_id from Cultures\n"
        "        left outer join Packages on\n"
        "            Packages.culture_id == Cultures.culture_id\n"
        "        left outer join SKUs on\n"
        "            SKUs.culture_id == Cultures.culture_id\n"
        "    where\n"
        "        Packages.culture_id is null and\n"
        "        SKUs.culture_id is null\n"
        ");",
        0x163u);
      memset(v17, 0, sizeof(v17));
      std::string::_Construct<1,char const *>(
        v17,
        "delete from Algorithms where Algorithms.algorithm_id in (\n"
        "    select Algorithms.algorithm_id from Algorithms\n"
        "    left outer join Hashes on\n"
        "        Hashes.algorithm_id == Algorithms.algorithm_id\n"
        "    where Hashes.algorithm_id is null\n"
        ");",
        0xEAu);
      memset(v18, 0, sizeof(v18));
      std::string::_Construct<1,char const *>(
        v18,
        "delete from Digests where Digests.digest_id in (\n"
        "    select Digests.digest_id from Digests\n"
        "    left outer join Hashes on\n"
        "        Hashes.digest_id == Digests.digest_id\n"
        "    where Hashes.digest_id is null\n"
        ");",
        0xCCu);
      memset(v19, 0, sizeof(v19));
      std::string::_Construct<1,char const *>(
        v19,
        "delete from directories where Directories.directory_id in (\n"
        "    select directories.directory_id from directories\n"
        "    left outer join paths on\n"
        "        paths.directory_id == Directories.directory_id\n"
        "    where Paths.path_id is null\n"
        ");",
        0xE7u);
      memset(v20, 0, sizeof(v20));
      std::string::_Construct<1,char const *>(
        v20,
        "delete from Families where Families.family_id in (\n"
        "    select Families.family_id from Families\n"
        "    left outer join Builds on\n"
        "        builds.family_id == Families.family_id\n"
        "    where\n"
        "        Builds.family_id is null\n"
        ");",
        0xD9u);
      memset(v21, 0, sizeof(v21));
      std::string::_Construct<1,char const *>(
        v21,
        "delete from Architectures where Architectures.arch_id in (\n"
        "    select Architectures.arch_id from Architectures\n"
        "    left outer join Builds on\n"
        "        Builds.arch_id == Architectures.arch_id\n"
        "    where\n"
        "        Builds.arch_id is null\n"
        ");",
        0xE8u);
      memset(v22, 0, sizeof(v22));
      std::string::_Construct<1,char const *>(
        v22,
        "delete from Flavors where Flavors.flavor_id in (\n"
        "    select Flavors.flavor_id from Flavors\n"
        "    left outer join Builds on\n"
        "        Builds.flavor_id == Flavors.flavor_id\n"
        "    where\n"
        "        Builds.flavor_id is null\n"
        ");",
        0xD4u);
      v1[0] = v2;
      v1[1] = &v23;
      std::vector<std::string>::vector<std::string>(&`RepoMan::Schema::CleanupScripts'::`2'::script, v1);
      `eh vector destructor iterator'(
        v2,
        0x20u,
        0x15u,
        RepoMan::Meta::RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>::~RowType<RepoMan::Meta::Column<RepoMan::Meta::Key<RepoMan::Meta::Text::Directory_Id,RepoMan::Meta::Types::Int,RepoMan::Meta::Constraints::NotNull,RepoMan::Meta::Text::Directories,RepoMan::Meta::Alias::None>,__int64>,RepoMan::Meta::Column<RepoMan::Meta::Value<RepoMan::Meta::Text::Name,RepoMan::Meta::Types::String,RepoMan::Meta::Constraints::CaseInsensitive>,std::string>>);
      atexit(`RepoMan::Schema::CleanupScripts'::`2'::`dynamic atexit destructor for 'script'');
      Init_thread_footer(&__TSS0__1__CleanupScripts_Schema_RepoMan__MEBAAEBV__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__std__XZ_4HA);
    }
  }
  return &`RepoMan::Schema::CleanupScripts'::`2'::script;
}

```

## disassembly

```asm
0x180008120  mov     [rsp-8+arg_0], rbx
0x180008125  push    rbp
0x180008126  lea     rbp, [rsp-1E0h]
0x18000812e  sub     rsp, 2E0h
0x180008135  mov     rax, cs:__security_cookie
0x18000813c  xor     rax, rsp
0x18000813f  mov     [rbp+1E0h+var_10], rax
0x180008146  mov     ecx, cs:_tls_index
0x18000814c  mov     rax, gs:58h
0x180008155  mov     edx, 4
0x18000815a  mov     rax, [rax+rcx*8]
0x18000815e  mov     eax, [rdx+rax]
0x180008161  cmp     cs:?$TSS0@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4HA, eax
0x180008167  jg      short loc_180008190
0x180008169  lea     rax, ?script@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4V45@B; std::vector<std::string> const `RepoMan::Schema::CleanupScripts(void)'::`2'::script
0x180008170  mov     rcx, [rbp+1E0h+var_10]
0x180008177  xor     rcx, rsp; StackCookie
0x18000817a  call    __security_check_cookie
0x18000817f  mov     rbx, [rsp+2E0h+arg_0]
0x180008187  add     rsp, 2E0h
0x18000818e  pop     rbp
0x18000818f  retn
0x180008190  lea     rcx, ?$TSS0@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4HA
0x180008197  call    _Init_thread_header
0x18000819c  cmp     cs:?$TSS0@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4HA, 0FFFFFFFFh
0x1800081a3  jnz     short loc_180008169
0x1800081a5  xorps   xmm0, xmm0
0x1800081a8  movups  [rsp+2E0h+var_2B0], xmm0
0x1800081ad  xorps   xmm1, xmm1
0x1800081b0  movdqa  [rsp+2E0h+var_2A0], xmm1
0x1800081b6  mov     r8d, 0E8h
0x1800081bc  lea     rdx, aDeleteFromPack; "delete from PackagesToPaths where Packa"...
0x1800081c3  lea     rcx, [rsp+2E0h+var_2B0]
0x1800081c8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800081cd  nop
0x1800081ce  xorps   xmm0, xmm0
0x1800081d1  movups  [rsp+2E0h+var_290], xmm0
0x1800081d6  xorps   xmm1, xmm1
0x1800081d9  movdqa  [rsp+2E0h+var_280], xmm1
0x1800081df  mov     r8d, 0E6h
0x1800081e5  lea     rdx, aDeleteFromPack_1; "delete from PackagesToApps where Packag"...
0x1800081ec  lea     rcx, [rsp+2E0h+var_290]
0x1800081f1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800081f6  nop
0x1800081f7  xorps   xmm0, xmm0
0x1800081fa  movups  [rsp+2E0h+var_270], xmm0
0x1800081ff  xorps   xmm1, xmm1
0x180008202  movdqa  [rbp+1E0h+var_260], xmm1
0x180008207  mov     r8d, 0DEh
0x18000820d  lea     rdx, aDeleteFromApps; "delete from AppsToSKUs where AppsToSKUs"...
0x180008214  lea     rcx, [rsp+2E0h+var_270]
0x180008219  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000821e  nop
0x18000821f  xorps   xmm0, xmm0
0x180008222  movups  [rbp+1E0h+var_250], xmm0
0x180008226  xorps   xmm1, xmm1
0x180008229  movdqa  [rbp+1E0h+var_240], xmm1
0x18000822e  mov     ebx, 0D2h
0x180008233  mov     r8d, ebx
0x180008236  lea     rdx, aDeleteFromSkus; "delete from SKUs where SKUs.build_id in"...
0x18000823d  lea     rcx, [rbp+1E0h+var_250]
0x180008241  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008246  nop
0x180008247  xorps   xmm0, xmm0
0x18000824a  movups  [rbp+1E0h+var_230], xmm0
0x18000824e  xorps   xmm1, xmm1
0x180008251  movdqa  [rbp+1E0h+var_220], xmm1
0x180008256  mov     r8d, ebx
0x180008259  lea     rdx, aDeleteFromApps_0; "delete from Apps where Apps.build_id in"...
0x180008260  lea     rcx, [rbp+1E0h+var_230]
0x180008264  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008269  nop
0x18000826a  xorps   xmm0, xmm0
0x18000826d  movups  [rbp+1E0h+var_210], xmm0
0x180008271  xorps   xmm1, xmm1
0x180008274  movdqa  [rbp+1E0h+var_200], xmm1
0x180008279  lea     r8d, [rbx+8]
0x18000827d  lea     rdx, aDeleteFromPack_0; "delete from Packages where Packages.bui"...
0x180008284  lea     rcx, [rbp+1E0h+var_210]
0x180008288  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000828d  nop
0x18000828e  xorps   xmm0, xmm0
0x180008291  movups  [rbp+1E0h+var_1F0], xmm0
0x180008295  xorps   xmm1, xmm1
0x180008298  movdqa  [rbp+1E0h+var_1E0], xmm1
0x18000829d  lea     r8d, [rbx+6]
0x1800082a1  lea     rdx, aDeleteFromPatc; "delete from Patches where Patches.build"...
0x1800082a8  lea     rcx, [rbp+1E0h+var_1F0]
0x1800082ac  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800082b1  nop
0x1800082b2  xorps   xmm0, xmm0
0x1800082b5  movups  [rbp+1E0h+var_1D0], xmm0
0x1800082b9  xorps   xmm1, xmm1
0x1800082bc  movdqa  [rbp+1E0h+var_1C0], xmm1
0x1800082c1  lea     r8d, [rbx+0Eh]
0x1800082c5  lea     rdx, aDeleteFromBloc_0; "delete from BlockSource where BlockSour"...
0x1800082cc  lea     rcx, [rbp+1E0h+var_1D0]
0x1800082d0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800082d5  nop
0x1800082d6  xorps   xmm0, xmm0
0x1800082d9  movups  [rbp+1E0h+var_1B0], xmm0
0x1800082dd  xorps   xmm1, xmm1
0x1800082e0  movdqa  [rbp+1E0h+var_1A0], xmm1
0x1800082e5  lea     r8d, [rbx+4]
0x1800082e9  lea     rdx, aDeleteFromBloc; "delete from Blocks where Blocks.build_i"...
0x1800082f0  lea     rcx, [rbp+1E0h+var_1B0]
0x1800082f4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800082f9  nop
0x1800082fa  xorps   xmm0, xmm0
0x1800082fd  movups  [rbp+1E0h+var_190], xmm0
0x180008301  xorps   xmm1, xmm1
0x180008304  movdqa  [rbp+1E0h+var_180], xmm1
0x180008309  mov     ebx, 0D4h
0x18000830e  mov     r8d, ebx
0x180008311  lea     rdx, aDeleteFromFile_0; "delete from Files where Files.build_id "...
0x180008318  lea     rcx, [rbp+1E0h+var_190]
0x18000831c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008321  nop
0x180008322  xorps   xmm0, xmm0
0x180008325  movups  [rbp+1E0h+var_170], xmm0
0x180008329  xorps   xmm1, xmm1
0x18000832c  movdqa  [rbp+1E0h+var_160], xmm1
0x180008334  mov     r8d, ebx
0x180008337  lea     rdx, aDeleteFromMedi; "delete from Media where Media.build_id "...
0x18000833e  lea     rcx, [rbp+1E0h+var_170]
0x180008342  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008347  nop
0x180008348  xorps   xmm0, xmm0
0x18000834b  movups  [rbp+1E0h+var_150], xmm0
0x180008352  xorps   xmm1, xmm1
0x180008355  movdqa  [rbp+1E0h+var_140], xmm1
0x18000835d  mov     r8d, 168h
0x180008363  lea     rdx, aDeleteFromBuil; "delete from Builds where Builds.build_i"...
0x18000836a  lea     rcx, [rbp+1E0h+var_150]
0x180008371  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008376  nop
0x180008377  xorps   xmm0, xmm0
0x18000837a  movups  [rbp+1E0h+var_130], xmm0
0x180008381  xorps   xmm1, xmm1
0x180008384  movdqa  [rbp+1E0h+var_120], xmm1
0x18000838c  mov     r8d, 2A8h
0x180008392  lea     rdx, aDeleteFromPath; "delete from Paths where Paths.path_id i"...
0x180008399  lea     rcx, [rbp+1E0h+var_130]
0x1800083a0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800083a5  nop
0x1800083a6  xorps   xmm0, xmm0
0x1800083a9  movups  [rbp+1E0h+var_110], xmm0
0x1800083b0  xorps   xmm1, xmm1
0x1800083b3  movdqa  [rbp+1E0h+var_100], xmm1
0x1800083bb  mov     r8d, 2ADh
0x1800083c1  lea     rdx, aDeleteFromHash; "delete from Hashes where Hashes.hash_id"...
0x1800083c8  lea     rcx, [rbp+1E0h+var_110]
0x1800083cf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800083d4  nop
0x1800083d5  xorps   xmm0, xmm0
0x1800083d8  movups  [rbp+1E0h+var_F0], xmm0
0x1800083df  xorps   xmm1, xmm1
0x1800083e2  movdqa  [rbp+1E0h+var_E0], xmm1
0x1800083ea  mov     r8d, 163h
0x1800083f0  lea     rdx, aDeleteFromCult; "delete from Cultures where Cultures.cul"...
0x1800083f7  lea     rcx, [rbp+1E0h+var_F0]
0x1800083fe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008403  nop
0x180008404  xorps   xmm0, xmm0
0x180008407  movups  [rbp+1E0h+var_D0], xmm0
0x18000840e  xorps   xmm1, xmm1
0x180008411  movdqa  [rbp+1E0h+var_C0], xmm1
0x180008419  lea     r8d, [rbx+16h]
0x18000841d  lea     rdx, aDeleteFromAlgo; "delete from Algorithms where Algorithms"...
0x180008424  lea     rcx, [rbp+1E0h+var_D0]
0x18000842b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008430  nop
0x180008431  xorps   xmm0, xmm0
0x180008434  movups  [rbp+1E0h+var_B0], xmm0
0x18000843b  xorps   xmm1, xmm1
0x18000843e  movdqa  [rbp+1E0h+var_A0], xmm1
0x180008446  lea     r8d, [rbx-8]
0x18000844a  lea     rdx, aDeleteFromDige; "delete from Digests where Digests.diges"...
0x180008451  lea     rcx, [rbp+1E0h+var_B0]
0x180008458  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000845d  nop
0x18000845e  xorps   xmm0, xmm0
0x180008461  movups  [rbp+1E0h+var_90], xmm0
0x180008468  xorps   xmm1, xmm1
0x18000846b  movdqa  [rbp+1E0h+var_80], xmm1
0x180008473  lea     r8d, [rbx+13h]
0x180008477  lea     rdx, aDeleteFromDire; "delete from directories where Directori"...
0x18000847e  lea     rcx, [rbp+1E0h+var_90]
0x180008485  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000848a  nop
0x18000848b  xorps   xmm0, xmm0
0x18000848e  movups  [rbp+1E0h+var_70], xmm0
0x180008495  xorps   xmm1, xmm1
0x180008498  movdqa  [rbp+1E0h+var_60], xmm1
0x1800084a0  lea     r8d, [rbx+5]
0x1800084a4  lea     rdx, aDeleteFromFami; "delete from Families where Families.fam"...
0x1800084ab  lea     rcx, [rbp+1E0h+var_70]
0x1800084b2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800084b7  nop
0x1800084b8  xorps   xmm0, xmm0
0x1800084bb  movups  [rbp+1E0h+var_50], xmm0
0x1800084c2  xorps   xmm1, xmm1
0x1800084c5  movdqa  [rbp+1E0h+var_40], xmm1
0x1800084cd  lea     r8d, [rbx+14h]
0x1800084d1  lea     rdx, aDeleteFromArch; "delete from Architectures where Archite"...
0x1800084d8  lea     rcx, [rbp+1E0h+var_50]
0x1800084df  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800084e4  nop
0x1800084e5  xorps   xmm0, xmm0
0x1800084e8  movups  [rbp+1E0h+var_30], xmm0
0x1800084ef  xorps   xmm1, xmm1
0x1800084f2  movdqa  [rbp+1E0h+var_20], xmm1
0x1800084fa  mov     r8d, ebx
0x1800084fd  lea     rdx, aDeleteFromFlav; "delete from Flavors where Flavors.flavo"...
0x180008504  lea     rcx, [rbp+1E0h+var_30]
0x18000850b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180008510  nop
0x180008511  lea     rax, [rsp+2E0h+var_2B0]
0x180008516  mov     [rsp+2E0h+var_2C0], rax
0x18000851b  lea     rax, [rbp+1E0h+var_10]
0x180008522  mov     [rsp+2E0h+var_2B8], rax
0x180008527  lea     rdx, [rsp+2E0h+var_2C0]
0x18000852c  lea     rcx, ?script@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4V45@B; std::vector<std::string> const `RepoMan::Schema::CleanupScripts(void)'::`2'::script
0x180008533  call    ??0?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@AEBV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::vector<std::string>::vector<std::string>(std::initializer_list<std::string>,std::allocator<std::string> const &)
0x180008538  nop
0x180008539  lea     r9, ??1?$RowType@U?$Column@U?$Key@UDirectory_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UDirectories@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@QEAA@XZ; void (*)(void *)
0x180008540  mov     edx, 20h ; ' '; unsigned __int64
0x180008545  lea     r8d, [rdx-0Bh]; unsigned __int64
0x180008549  lea     rcx, [rsp+2E0h+var_2B0]; void *
0x18000854e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180008553  lea     rcx, ??__Fscript@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@YAXXZ; void (__cdecl *)()
0x18000855a  call    atexit
0x18000855f  nop
0x180008560  lea     rcx, ?$TSS0@?1??CleanupScripts@Schema@RepoMan@@MEBAAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ@4HA
0x180008567  call    _Init_thread_footer
0x18000856c  jmp     loc_180008169
```
