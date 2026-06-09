# _LoadServiceProfile(ushort const *)

- ea: `0x18000d23c`
- end: `0x18000d409`
- name: `?_LoadServiceProfile@@YAJPEBG@Z`
- size: `461`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180009f90`

## callees

- `0x180005b60`
- `0x180005b90`
- `0x180009c04`
- `0x180009d10`
- `0x18000a250`
- `0x18000caa0`
- `0x18000d23c`
- `0x1800166e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d371`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d371`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d311`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d311`

## pseudocode

```c
__int64 __fastcall _LoadServiceProfile(const unsigned __int16 *a1)
{
  int IsHiveLoaded; // eax
  unsigned int DirectoryAndCopyDefaultProfile; // ebx
  int ProfileAndHivePath; // eax
  __int64 v6; // rdx
  int v7; // ebx
  unsigned __int64 v8; // r9
  LPCWSTR lpFileName; // [rsp+20h] [rbp-30h] BYREF
  __int64 v10; // [rsp+28h] [rbp-28h]
  __int64 v11; // [rsp+30h] [rbp-20h]
  unsigned __int16 *v12; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h]
  __int64 v14; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  const unsigned __int16 *v16; // [rsp+60h] [rbp+10h] BYREF
  int v17; // [rsp+68h] [rbp+18h] BYREF

  v16 = a1;
  v17 = 0;
  IsHiveLoaded = _IsHiveLoaded(a1, &v17);
  DirectoryAndCopyDefaultProfile = IsHiveLoaded;
  if ( IsHiveLoaded < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)IsHiveLoaded,
      (int)lpFileName);
    return DirectoryAndCopyDefaultProfile;
  }
  if ( !v17 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    lpFileName = 0;
    v10 = 0;
    v11 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
    v10 = -1;
    v11 = -1;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
    v13 = -1;
    v14 = -1;
    ProfileAndHivePath = _GetProfileAndHivePath(a1, &v12, (unsigned __int16 **)&lpFileName);
    DirectoryAndCopyDefaultProfile = ProfileAndHivePath;
    if ( ProfileAndHivePath < 0 )
    {
      v6 = 495;
LABEL_19:
      v8 = (unsigned int)ProfileAndHivePath;
      goto LABEL_20;
    }
    v7 = 0;
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      DirectoryAndCopyDefaultProfile = _CreateDirectoryAndCopyDefaultProfile(a1, v12);
      v17 = DirectoryAndCopyDefaultProfile;
      if ( (DirectoryAndCopyDefaultProfile & 0x80000000) != 0 )
      {
        ProfAPITelemetry::LoadServiceProfileCopyDefaultFailed<long &,unsigned short const * &>(&v17, &v16);
        if ( DirectoryAndCopyDefaultProfile != -2147024891 )
        {
          v8 = DirectoryAndCopyDefaultProfile;
          v6 = 507;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v6,
            (unsigned int)"minio\\profapi\\load.cpp",
            (const char *)v8,
            (int)lpFileName);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
          return DirectoryAndCopyDefaultProfile;
        }
      }
      v7 = 1;
    }
    ProfileAndHivePath = _LoadHiveAndPerformFirstActions(a1, lpFileName, v7);
    DirectoryAndCopyDefaultProfile = ProfileAndHivePath;
    if ( ProfileAndHivePath == -2147023879 )
    {
      DeleteFileW(lpFileName);
      ProfileAndHivePath = _CreateDirectoryAndCopyDefaultProfile(a1, v12);
      DirectoryAndCopyDefaultProfile = ProfileAndHivePath;
      if ( ProfileAndHivePath < 0 )
      {
        v6 = 521;
        goto LABEL_19;
      }
      ProfileAndHivePath = _LoadHiveAndPerformFirstActions(a1, lpFileName, 1);
      DirectoryAndCopyDefaultProfile = ProfileAndHivePath;
      if ( ProfileAndHivePath < 0 )
      {
        v6 = 522;
        goto LABEL_19;
      }
    }
    else if ( ProfileAndHivePath < 0 )
    {
      v6 = 526;
      goto LABEL_19;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpFileName);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d23c  mov     [rsp-8+arg_10], rbx
0x18000d241  mov     [rsp-8+arg_18], rdi
0x18000d246  mov     [rsp-8+arg_0], rcx
0x18000d24b  push    rbp
0x18000d24c  mov     rbp, rsp
0x18000d24f  sub     rsp, 50h
0x18000d253  mov     rdi, rcx
0x18000d256  mov     [rbp+arg_8], 0
0x18000d25d  lea     rdx, [rbp+arg_8]; int *
0x18000d261  call    ?_IsHiveLoaded@@YAJPEBGPEAH@Z; _IsHiveLoaded(ushort const *,int *)
0x18000d266  mov     ebx, eax
0x18000d268  test    eax, eax
0x18000d26a  jns     short loc_18000D28B
0x18000d26c  mov     rcx, [rbp+8]; this
0x18000d270  mov     r9d, eax; char *
0x18000d273  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000d27a  mov     edx, 1EAh; void *
0x18000d27f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d284  mov     eax, ebx
0x18000d286  jmp     loc_18000D3F9
0x18000d28b  cmp     [rbp+arg_8], 0
0x18000d28f  jnz     loc_18000D3F7
0x18000d295  mov     [rbp+var_18], 0
0x18000d29d  mov     [rbp+var_10], 0
0x18000d2a5  mov     [rbp+var_8], 0
0x18000d2ad  mov     [rbp+lpFileName], 0
0x18000d2b5  mov     [rbp+var_28], 0
0x18000d2bd  mov     [rbp+var_20], 0
0x18000d2c5  lea     rcx, [rbp+lpFileName]
0x18000d2c9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d2ce  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d2d2  mov     [rbp+var_28], rbx
0x18000d2d6  mov     [rbp+var_20], rbx
0x18000d2da  lea     rcx, [rbp+var_18]
0x18000d2de  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d2e3  mov     [rbp+var_10], rbx
0x18000d2e7  mov     [rbp+var_8], rbx
0x18000d2eb  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x18000d2ef  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x18000d2f3  mov     rcx, rdi; unsigned __int16 *
0x18000d2f6  call    ?_GetProfileAndHivePath@@YAJPEBGPEAPEAG1@Z; _GetProfileAndHivePath(ushort const *,ushort * *,ushort * *)
0x18000d2fb  mov     ebx, eax
0x18000d2fd  test    eax, eax
0x18000d2ff  jns     short loc_18000D30B
0x18000d301  mov     edx, 1EFh
0x18000d306  jmp     loc_18000D3B8
0x18000d30b  xor     ebx, ebx
0x18000d30d  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000d311  call    cs:__imp_GetFileAttributesW
0x18000d317  cmp     eax, 0FFFFFFFFh
0x18000d31a  jnz     short loc_18000D355
0x18000d31c  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18000d320  mov     rcx, rdi; unsigned __int16 *
0x18000d323  call    ?_CreateDirectoryAndCopyDefaultProfile@@YAJPEBG0@Z; _CreateDirectoryAndCopyDefaultProfile(ushort const *,ushort const *)
0x18000d328  mov     ebx, eax
0x18000d32a  mov     [rbp+arg_8], eax
0x18000d32d  test    eax, eax
0x18000d32f  jns     short loc_18000D350
0x18000d331  lea     rdx, [rbp+arg_0]
0x18000d335  lea     rcx, [rbp+arg_8]
0x18000d339  call    ??$LoadServiceProfileCopyDefaultFailed@AEAJAEAPEBG@ProfAPITelemetry@@SAXAEAJAEAPEBG@Z; ProfAPITelemetry::LoadServiceProfileCopyDefaultFailed<long &,ushort const * &>(long &,ushort const * &)
0x18000d33e  cmp     ebx, 80070005h
0x18000d344  jz      short loc_18000D350
0x18000d346  mov     r9d, ebx
0x18000d349  mov     edx, 1FBh
0x18000d34e  jmp     short loc_18000D3BB
0x18000d350  mov     ebx, 1
0x18000d355  mov     r8d, ebx; int
0x18000d358  mov     rdx, [rbp+lpFileName]; unsigned __int16 *
0x18000d35c  mov     rcx, rdi; unsigned __int16 *
0x18000d35f  call    ?_LoadHiveAndPerformFirstActions@@YAJPEBG0H@Z; _LoadHiveAndPerformFirstActions(ushort const *,ushort const *,int)
0x18000d364  mov     ebx, eax
0x18000d366  cmp     eax, 800703F9h
0x18000d36b  jnz     short loc_18000D3AF
0x18000d36d  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000d371  call    cs:__imp_DeleteFileW
0x18000d377  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18000d37b  mov     rcx, rdi; unsigned __int16 *
0x18000d37e  call    ?_CreateDirectoryAndCopyDefaultProfile@@YAJPEBG0@Z; _CreateDirectoryAndCopyDefaultProfile(ushort const *,ushort const *)
0x18000d383  mov     ebx, eax
0x18000d385  test    eax, eax
0x18000d387  jns     short loc_18000D390
0x18000d389  mov     edx, 209h
0x18000d38e  jmp     short loc_18000D3B8
0x18000d390  mov     r8d, 1; int
0x18000d396  mov     rdx, [rbp+lpFileName]; unsigned __int16 *
0x18000d39a  mov     rcx, rdi; unsigned __int16 *
0x18000d39d  call    ?_LoadHiveAndPerformFirstActions@@YAJPEBG0H@Z; _LoadHiveAndPerformFirstActions(ushort const *,ushort const *,int)
0x18000d3a2  mov     ebx, eax
0x18000d3a4  test    eax, eax
0x18000d3a6  jns     short loc_18000D3E4
0x18000d3a8  mov     edx, 20Ah
0x18000d3ad  jmp     short loc_18000D3B8
0x18000d3af  test    eax, eax
0x18000d3b1  jns     short loc_18000D3E4
0x18000d3b3  mov     edx, 20Eh; void *
0x18000d3b8  mov     r9d, eax; char *
0x18000d3bb  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000d3c2  mov     rcx, [rbp+8]; this
0x18000d3c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3cb  nop
0x18000d3cc  lea     rcx, [rbp+lpFileName]
0x18000d3d0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d3d5  nop
0x18000d3d6  lea     rcx, [rbp+var_18]
0x18000d3da  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d3df  jmp     loc_18000D284
0x18000d3e4  lea     rcx, [rbp+lpFileName]
0x18000d3e8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d3ed  nop
0x18000d3ee  lea     rcx, [rbp+var_18]
0x18000d3f2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000d3f7  xor     eax, eax
0x18000d3f9  mov     rbx, [rsp+50h+arg_10]
0x18000d3fe  mov     rdi, [rsp+50h+arg_18]
0x18000d403  add     rsp, 50h
0x18000d407  pop     rbp
0x18000d408  retn
```
