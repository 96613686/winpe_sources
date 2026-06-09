# PolicyChecker::CheckFilePermission(ushort const *,_DS_SHARE_PERMISSION,_DS_SHARE_MODE,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800125c4`
- end: `0x180012740`
- name: `?CheckFilePermission@PolicyChecker@@SAJPEBGW4_DS_SHARE_PERMISSION@@W4_DS_SHARE_MODE@@HHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@3@Z`
- size: `380`
- prototype: `__int64 __fastcall(DSUtils *this, unsigned int, unsigned int, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config`

## callers

- `0x18000ca4c`
- `0x18000f740`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c704`
- `0x18000dee8`
- `0x18000e674`
- `0x18000f1a0`
- `0x18000fcd4`
- `0x18000fd9c`
- `0x1800125c4`
- `0x18001a1e8`
- `0x18001a330`
- `0x18001a5e4`
- `0x18001a6f0`

## string_xrefs

- `0x18001268e`: `CheckFilePermission: Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x`
- `0x1800126d6`: `CheckFilePermission: Found remote filepath, invalid file path %s`

## pseudocode

```c
__int64 __fastcall PolicyChecker::CheckFilePermission(
        DSUtils *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  int FileIdFromHandle; // ebx
  unsigned int v11; // eax
  unsigned int v12; // esi
  int v13; // r14d
  void *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  HANDLE v17; // rcx
  DSLogger *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  DSLogger *v23; // rax
  void **v25; // [rsp+28h] [rbp-48h]
  void **v26; // [rsp+28h] [rbp-48h]
  int v27; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-1Ch] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-18h] BYREF
  HANDLE hFile[2]; // [rsp+60h] [rbp-10h] BYREF

  LODWORD(v29) = 0;
  v28 = 0;
  hFile[0] = (HANDLE)-1LL;
  FileIdFromHandle = ShareAccessControl::MapSharePermission(a2, &v29);
  if ( FileIdFromHandle >= 0 )
  {
    FileIdFromHandle = ShareAccessControl::MapShareMode(a3, &v28);
    if ( FileIdFromHandle >= 0 )
    {
      v27 = 0;
      if ( a4 && (FileIdFromHandle = AutoImpersonate<1>::ImpersonateClient(&v27), FileIdFromHandle < 0)
        || (v11 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),-1>(hFile),
            v12 = v28,
            v13 = (int)v29,
            FileIdFromHandle = DSUtils::OpenFile(this, (const unsigned __int16 *)(unsigned int)v29, v28, 0, v11, v25),
            FileIdFromHandle < 0) )
      {
        AutoImpersonate<1>::RevertToSelf(&v27);
      }
      else
      {
        AutoImpersonate<1>::RevertToSelf(&v27);
        v17 = hFile[0];
        if ( hFile[0] == (HANDLE)-1LL )
        {
          v18 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                              -1,
                              v14,
                              v15,
                              v16);
          LODWORD(v26) = v13;
          DSLogger::LogError(
            v18,
            L"PolicyChecker::CheckFilePermission",
            0x74u,
            L"CheckFilePermission: Failed to open file %s, with DesiredAccess=0x%x, ShareMode=0x%x, FlagsAndAttributes=0x%x, HR=0x%x",
            this,
            v26,
            v12,
            128,
            FileIdFromHandle);
        }
        else
        {
          if ( a5 )
          {
            if ( (unsigned int)DSUtils::IsRemoteFile(hFile[0], v14) )
            {
              v23 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                  v20,
                                  v19,
                                  v21,
                                  v22);
              DSLogger::LogError(
                v23,
                L"PolicyChecker::CheckFilePermission",
                0x7Fu,
                L"CheckFilePermission: Found remote filepath, invalid file path %s",
                this);
              FileIdFromHandle = -1055719416;
              goto LABEL_18;
            }
            v17 = hFile[0];
          }
          if ( a7 )
          {
            FileIdFromHandle = DSUtils::GetFileIdFromHandle(v17);
            if ( FileIdFromHandle < 0 )
              goto LABEL_18;
            v17 = hFile[0];
          }
          if ( a6 )
            FileIdFromHandle = DSUtils::GetFinalPathFromHandle(v17);
        }
      }
    }
  }
LABEL_18:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(hFile);
  return (unsigned int)FileIdFromHandle;
}

```

## disassembly

```asm
0x1800125c4  push    rbp
0x1800125c6  push    rbx
0x1800125c7  push    rsi
0x1800125c8  push    rdi
0x1800125c9  push    r14
0x1800125cb  mov     rbp, rsp
0x1800125ce  sub     rsp, 70h
0x1800125d2  mov     eax, edx
0x1800125d4  mov     dword ptr [rbp+var_18], 0
0x1800125db  mov     rdi, rcx
0x1800125de  mov     [rbp+var_1C], 0
0x1800125e5  mov     ecx, eax
0x1800125e7  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800125ef  lea     rdx, [rbp+var_18]
0x1800125f3  mov     esi, r9d
0x1800125f6  mov     r14d, r8d
0x1800125f9  call    ?MapSharePermission@ShareAccessControl@@SAJW4_DS_SHARE_PERMISSION@@PEAK@Z; ShareAccessControl::MapSharePermission(_DS_SHARE_PERMISSION,ulong *)
0x1800125fe  mov     ebx, eax
0x180012600  test    eax, eax
0x180012602  js      loc_18001272A
0x180012608  lea     rdx, [rbp+var_1C]
0x18001260c  mov     ecx, r14d
0x18001260f  call    ?MapShareMode@ShareAccessControl@@SAJW4_DS_SHARE_MODE@@PEAK@Z; ShareAccessControl::MapShareMode(_DS_SHARE_MODE,ulong *)
0x180012614  mov     ebx, eax
0x180012616  test    eax, eax
0x180012618  js      loc_18001272A
0x18001261e  mov     [rbp+var_20], 0
0x180012625  test    esi, esi
0x180012627  jz      short loc_180012646
0x180012629  lea     rcx, [rbp+var_20]
0x18001262d  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x180012632  mov     ebx, eax
0x180012634  test    eax, eax
0x180012636  jns     short loc_180012646
0x180012638  lea     rcx, [rbp+var_20]
0x18001263c  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x180012641  jmp     loc_18001272A
0x180012646  lea     rcx, [rbp+hFile]
0x18001264a  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),-1>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1> &)
0x18001264f  mov     esi, [rbp+var_1C]
0x180012652  xor     r9d, r9d; unsigned int
0x180012655  mov     r14d, dword ptr [rbp+var_18]
0x180012659  mov     r8d, esi; unsigned int
0x18001265c  mov     edx, r14d; unsigned __int16 *
0x18001265f  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x180012664  mov     rcx, rdi; this
0x180012667  call    ?OpenFile@DSUtils@@YAJPEBGKKKPEAPEAX@Z; DSUtils::OpenFile(ushort const *,ulong,ulong,ulong,void * *)
0x18001266c  lea     rcx, [rbp+var_20]
0x180012670  mov     ebx, eax
0x180012672  test    eax, eax
0x180012674  js      short loc_18001263C
0x180012676  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18001267b  mov     rcx, [rbp+hFile]; hFile
0x18001267f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012683  jnz     short loc_1800126C2
0x180012685  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001268a  mov     [rsp+70h+var_30], ebx
0x18001268e  lea     r9, aCheckfilepermi; "CheckFilePermission: Failed to open fil"...
0x180012695  mov     [rsp+70h+var_38], 80h
0x18001269d  lea     rdx, aPolicycheckerC_0; "PolicyChecker::CheckFilePermission"
0x1800126a4  mov     [rsp+70h+var_40], esi
0x1800126a8  mov     r8d, 74h ; 't'; unsigned int
0x1800126ae  mov     dword ptr [rsp+70h+var_48], r14d
0x1800126b3  mov     rcx, rax; this
0x1800126b6  mov     qword ptr [rsp+70h+var_50], rdi
0x1800126bb  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800126c0  jmp     short loc_18001272A
0x1800126c2  cmp     [rbp+arg_20], 0
0x1800126c6  jz      short loc_180012702
0x1800126c8  call    ?IsRemoteFile@DSUtils@@YAHPEAX@Z; DSUtils::IsRemoteFile(void *)
0x1800126cd  test    eax, eax
0x1800126cf  jz      short loc_1800126FE
0x1800126d1  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800126d6  lea     r9, aCheckfilepermi_0; "CheckFilePermission: Found remote filep"...
0x1800126dd  mov     qword ptr [rsp+70h+var_50], rdi
0x1800126e2  mov     r8d, 7Fh; unsigned int
0x1800126e8  lea     rdx, aPolicycheckerC_0; "PolicyChecker::CheckFilePermission"
0x1800126ef  mov     rcx, rax; this
0x1800126f2  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800126f7  mov     ebx, 0C1130008h
0x1800126fc  jmp     short loc_18001272A
0x1800126fe  mov     rcx, [rbp+hFile]; hFile
0x180012702  mov     rdx, [rbp+arg_30]
0x180012706  test    rdx, rdx
0x180012709  jz      short loc_18001271A
0x18001270b  call    ?GetFileIdFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFileIdFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180012710  mov     ebx, eax
0x180012712  test    eax, eax
0x180012714  js      short loc_18001272A
0x180012716  mov     rcx, [rbp+hFile]; hFile
0x18001271a  mov     rdx, [rbp+arg_28]
0x18001271e  test    rdx, rdx
0x180012721  jz      short loc_18001272A
0x180012723  call    ?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180012728  mov     ebx, eax
0x18001272a  lea     rcx, [rbp+hFile]
0x18001272e  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x180012733  mov     eax, ebx
0x180012735  add     rsp, 70h
0x180012739  pop     r14
0x18001273b  pop     rdi
0x18001273c  pop     rsi
0x18001273d  pop     rbx
0x18001273e  pop     rbp
0x18001273f  retn
```
