# FF_DumpProcess_MD(ushort *)

- ea: `0x18000ee14`
- end: `0x18000f0b6`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ed38`

## callees

- `0x18000e000`
- `0x18000ee14`
- `0x18000f0bc`
- `0x18000f2b8`
- `0x18000f4dc`
- `0x1800127e6`
- `0x18001280a`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eef4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000efa6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000efa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f04a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000f04a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f044`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000f044`
- `msvcrt!_waccess` at `0x18000f080`
- `msvcrt!_waccess` at `0x18000f080`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ef0f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ef0f`

## string_xrefs

- `0x18000f05a`: `RunDll32 comsvcs.dll,MiniDump`

## pseudocode

```c
__int64 __fastcall FF_DumpProcess_MD(unsigned __int16 *a1)
{
  int DumpProperties; // ebx
  DWORD v2; // eax
  signed int LastError; // eax
  DWORD CurrentProcessId; // eax
  __int64 v6; // [rsp+0h] [rbp-318h] BYREF
  __int64 v7; // [rsp+28h] [rbp-2F0h]
  __int64 v8; // [rsp+30h] [rbp-2E8h]
  __int64 v9; // [rsp+38h] [rbp-2E0h]
  __int64 v10; // [rsp+40h] [rbp-2D8h]
  __int64 v11; // [rsp+48h] [rbp-2D0h]
  __int64 v12; // [rsp+50h] [rbp-2C8h]
  int v13; // [rsp+60h] [rbp-2B8h]
  int v14; // [rsp+64h] [rbp-2B4h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-2B0h]
  unsigned int v16; // [rsp+6Ch] [rbp-2ACh] BYREF
  GUID *rguid; // [rsp+70h] [rbp-2A8h] BYREF
  LPCWSTR lpSrc; // [rsp+78h] [rbp-2A0h] BYREF
  signed int v19; // [rsp+80h] [rbp-298h]
  int v20; // [rsp+84h] [rbp-294h]
  __int64 *v21; // [rsp+88h] [rbp-290h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-278h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-228h] BYREF

  v21 = &v6;
  memset_0(sz, 0, sizeof(sz));
  memset_0(Dst, 0, 0x20Au);
  lpSrc = 0;
  SystemTime = 0;
  v16 = 10;
  v14 = 1;
  rguid = 0;
  DumpProperties = FF_GetDumpProperties(&rguid, &v14, (unsigned __int16 **)&lpSrc, &v16);
  v13 = DumpProperties;
  if ( DumpProperties )
    return (unsigned int)DumpProperties;
  if ( !v14
    || rguid && *(_QWORD *)&rguid->Data1 == APPLID_SystemApplication && *(_QWORD *)rguid->Data4 == 0x3592C75F80000D96LL )
  {
    DumpProperties = 1;
LABEL_17:
    v13 = DumpProperties;
    return (unsigned int)DumpProperties;
  }
  StringFromGUID2(rguid, sz, 40);
  v2 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  if ( v2 )
  {
    if ( v2 > 0x104 )
    {
      v20 = -2147024785;
      local_unwind_0(v21, &loc_18000EF7A);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v16);
    GetLocalTime(&SystemTime);
    word_1800216F8 = 0;
    LODWORD(v12) = SystemTime.wSecond;
    LODWORD(v11) = SystemTime.wMinute;
    LODWORD(v10) = SystemTime.wHour;
    LODWORD(v9) = SystemTime.wDay;
    LODWORD(v8) = SystemTime.wMonth;
    LODWORD(v7) = SystemTime.wYear;
    DumpProperties = StringCchPrintfW(
                       &FileName,
                       0x104u,
                       L"%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dmp",
                       Dst,
                       sz,
                       v7,
                       v8,
                       v9,
                       v10,
                       v11,
                       v12);
    v13 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    CreateDirectoryW(Dst, 0);
    CurrentProcessId = GetCurrentProcessId();
    DumpProperties = FF_RunCmd(
                       (wchar_t *)L"%s %d %s full",
                       L"RunDll32 comsvcs.dll,MiniDump",
                       CurrentProcessId,
                       &FileName);
    v13 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    if ( _waccess(&FileName, 0) )
      DumpProperties = -2147467259;
    goto LABEL_17;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v15 = LastError;
  v19 = LastError;
  local_unwind_0(v21, &loc_18000EF4C);
  return v15;
}

```

## disassembly

```asm
0x18000ee14  push    rbx
0x18000ee16  sub     rsp, 310h
0x18000ee1d  mov     rax, cs:__security_cookie
0x18000ee24  xor     rax, rsp
0x18000ee27  mov     [rsp+318h+var_18], rax
0x18000ee2f  mov     [rsp+318h+var_290], rsp
0x18000ee37  xor     edx, edx; Val
0x18000ee39  lea     r8d, [rdx+50h]; Size
0x18000ee3d  lea     rcx, [rsp+318h+sz]; void *
0x18000ee45  call    memset_0
0x18000ee4a  xor     edx, edx; Val
0x18000ee4c  mov     r8d, 20Ah; Size
0x18000ee52  lea     rcx, [rsp+318h+Dst]; void *
0x18000ee5a  call    memset_0
0x18000ee5f  mov     [rsp+318h+lpSrc], 0
0x18000ee68  xorps   xmm0, xmm0
0x18000ee6b  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x18000ee73  mov     [rsp+318h+var_2AC], 0Ah
0x18000ee7b  mov     [rsp+318h+var_2B4], 1
0x18000ee83  mov     [rsp+318h+rguid], 0
0x18000ee8c  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x18000ee91  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x18000ee96  lea     rdx, [rsp+318h+var_2B4]; int *
0x18000ee9b  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x18000eea0  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x18000eea5  mov     ebx, eax
0x18000eea7  mov     [rsp+318h+var_2B8], eax
0x18000eeab  test    eax, eax
0x18000eead  jnz     loc_18000F094
0x18000eeb3  cmp     [rsp+318h+var_2B4], eax
0x18000eeb7  jnz     short loc_18000EEC3
0x18000eeb9  mov     ebx, 1
0x18000eebe  jmp     loc_18000F090
0x18000eec3  mov     rcx, [rsp+318h+rguid]; rguid
0x18000eec8  test    rcx, rcx
0x18000eecb  jz      short loc_18000EEE6
0x18000eecd  mov     rax, [rcx]
0x18000eed0  cmp     rax, cs:APPLID_SystemApplication
0x18000eed7  jnz     short loc_18000EEE6
0x18000eed9  mov     rax, [rcx+8]
0x18000eedd  cmp     rax, cs:qword_180019798
0x18000eee4  jz      short loc_18000EEB9
0x18000eee6  mov     r8d, 28h ; '('; cchMax
0x18000eeec  lea     rdx, [rsp+318h+sz]; lpsz
0x18000eef4  call    cs:__imp_StringFromGUID2
0x18000eefa  mov     ebx, 104h
0x18000eeff  mov     r8d, ebx; nSize
0x18000ef02  lea     rdx, [rsp+318h+Dst]; lpDst
0x18000ef0a  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x18000ef0f  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ef15  test    eax, eax
0x18000ef17  jnz     short loc_18000EF55
0x18000ef19  call    cs:__imp_GetLastError
0x18000ef1f  test    eax, eax
0x18000ef21  jle     short loc_18000EF2B
0x18000ef23  movzx   eax, ax
0x18000ef26  or      eax, 80070000h
0x18000ef2b  mov     [rsp+318h+var_2B0], eax
0x18000ef2f  mov     [rsp+318h+var_298], eax
0x18000ef36  lea     rdx, loc_18000EF4C
0x18000ef3d  mov     rcx, [rsp+318h+var_290]
0x18000ef45  call    _local_unwind_0
0x18000ef4a  nop
0x18000ef4b  nop
0x18000ef4c  mov     eax, [rsp+318h+var_2B0]
0x18000ef50  jmp     loc_18000F09D
0x18000ef55  cmp     eax, ebx
0x18000ef57  jbe     short loc_18000EF84
0x18000ef59  mov     [rsp+318h+var_294], 8007006Fh
0x18000ef64  lea     rdx, loc_18000EF7A
0x18000ef6b  mov     rcx, [rsp+318h+var_290]
0x18000ef73  call    _local_unwind_0
0x18000ef78  nop
0x18000ef79  nop
0x18000ef7a  mov     eax, 8007006Fh
0x18000ef7f  jmp     loc_18000F09D
0x18000ef84  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x18000ef89  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x18000ef91  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x18000ef99  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x18000ef9e  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x18000efa6  call    cs:__imp_GetLocalTime
0x18000efac  xor     eax, eax
0x18000efae  mov     cs:word_1800216F8, ax
0x18000efb5  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x18000efbd  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x18000efc5  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x18000efce  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x18000efd7  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x18000efe0  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x18000efe9  mov     dword ptr [rsp+318h+var_2C8], eax
0x18000efed  mov     dword ptr [rsp+318h+var_2D0], ecx
0x18000eff1  mov     dword ptr [rsp+318h+var_2D8], r8d
0x18000eff6  mov     dword ptr [rsp+318h+var_2E0], r9d
0x18000effb  mov     dword ptr [rsp+318h+var_2E8], r10d
0x18000f000  mov     dword ptr [rsp+318h+var_2F0], r11d
0x18000f005  lea     rax, [rsp+318h+sz]
0x18000f00d  mov     [rsp+318h+var_2F8], rax
0x18000f012  lea     r9, [rsp+318h+Dst]
0x18000f01a  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x18000f021  mov     rdx, rbx; unsigned __int64
0x18000f024  lea     rcx, FileName; unsigned __int16 *
0x18000f02b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f030  mov     ebx, eax
0x18000f032  mov     [rsp+318h+var_2B8], eax
0x18000f036  test    eax, eax
0x18000f038  js      short loc_18000F094
0x18000f03a  xor     edx, edx; lpSecurityAttributes
0x18000f03c  lea     rcx, [rsp+318h+Dst]; lpPathName
0x18000f044  call    cs:__imp_CreateDirectoryW
0x18000f04a  call    cs:__imp_GetCurrentProcessId
0x18000f050  mov     r8d, eax
0x18000f053  lea     r9, FileName
0x18000f05a  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x18000f061  lea     rcx, aSDSFull; "%s %d %s full"
0x18000f068  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x18000f06d  mov     ebx, eax
0x18000f06f  mov     [rsp+318h+var_2B8], eax
0x18000f073  test    eax, eax
0x18000f075  js      short loc_18000F094
0x18000f077  xor     edx, edx; AccessMode
0x18000f079  lea     rcx, FileName; FileName
0x18000f080  call    cs:__imp__waccess
0x18000f086  mov     ecx, 80004005h
0x18000f08b  test    eax, eax
0x18000f08d  cmovnz  ebx, ecx
0x18000f090  mov     [rsp+318h+var_2B8], ebx
0x18000f094  jmp     short loc_18000F09B
0x18000f096  mov     ebx, 8000FFFFh
0x18000f09b  mov     eax, ebx
0x18000f09d  mov     rcx, [rsp+318h+var_18]
0x18000f0a5  xor     rcx, rsp; StackCookie
0x18000f0a8  call    __security_check_cookie
0x18000f0ad  add     rsp, 310h
0x18000f0b4  pop     rbx
0x18000f0b5  retn
0x18001431c  push    rbp
0x18001431e  sub     rsp, 60h
0x180014322  mov     rbp, rdx
0x180014325  add     rsp, 60h
0x180014329  pop     rbp
0x18001432a  retn
```
