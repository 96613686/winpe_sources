# FF_DumpProcess_MD(ushort *)

- ea: `0x18002c7ac`
- end: `0x18002ca51`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800419a4`

## callees

- `0x180006194`
- `0x18002c7ac`
- `0x180041a80`
- `0x180041c7c`
- `0x180041e6c`
- `0x180043496`
- `0x1800434c6`
- `0x180043510`

## import_xrefs

- `msvcrt!_waccess` at `0x18002ca1b`
- `msvcrt!_waccess` at `0x18002ca1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c9e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c9e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002c941`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002c941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8b4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c9df`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002c9df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c8aa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c8aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c88f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c88f`

## string_xrefs

- `0x18002c9f5`: `RunDll32 comsvcs.dll,MiniDump`

## pseudocode

```c
__int64 __fastcall FF_DumpProcess_MD(unsigned __int16 *a1)
{
  int DumpProperties; // ebx
  __int64 v2; // rax
  DWORD v3; // eax
  signed int LastError; // eax
  DWORD CurrentProcessId; // eax
  __int64 v7; // [rsp+0h] [rbp-318h] BYREF
  __int64 v8; // [rsp+28h] [rbp-2F0h]
  __int64 v9; // [rsp+30h] [rbp-2E8h]
  __int64 v10; // [rsp+38h] [rbp-2E0h]
  __int64 v11; // [rsp+40h] [rbp-2D8h]
  __int64 v12; // [rsp+48h] [rbp-2D0h]
  __int64 v13; // [rsp+50h] [rbp-2C8h]
  int v14; // [rsp+60h] [rbp-2B8h]
  int v15; // [rsp+64h] [rbp-2B4h] BYREF
  unsigned int v16; // [rsp+68h] [rbp-2B0h]
  unsigned int v17; // [rsp+6Ch] [rbp-2ACh] BYREF
  GUID *rguid; // [rsp+70h] [rbp-2A8h] BYREF
  LPCWSTR lpSrc; // [rsp+78h] [rbp-2A0h] BYREF
  signed int v20; // [rsp+80h] [rbp-298h]
  int v21; // [rsp+84h] [rbp-294h]
  __int64 *v22; // [rsp+88h] [rbp-290h]
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-278h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-228h] BYREF

  v22 = &v7;
  memset_0(sz, 0, sizeof(sz));
  memset_0(Dst, 0, 0x20Au);
  lpSrc = 0;
  SystemTime = 0;
  v17 = 10;
  v15 = 1;
  rguid = 0;
  DumpProperties = FF_GetDumpProperties(&rguid, &v15, (unsigned __int16 **)&lpSrc, &v17);
  v14 = DumpProperties;
  if ( DumpProperties )
    return (unsigned int)DumpProperties;
  if ( !v15 )
    goto LABEL_3;
  if ( rguid )
  {
    v2 = *(_QWORD *)&rguid->Data1 - APPLID_SystemApplication;
    if ( *(_QWORD *)&rguid->Data1 == APPLID_SystemApplication )
      v2 = *(_QWORD *)rguid->Data4 - 0x3592C75F80000D96LL;
    if ( !v2 )
    {
LABEL_3:
      DumpProperties = 1;
LABEL_18:
      v14 = DumpProperties;
      return (unsigned int)DumpProperties;
    }
  }
  StringFromGUID2(rguid, sz, 40);
  v3 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  if ( v3 )
  {
    if ( v3 > 0x104 )
    {
      v21 = -2147024785;
      local_unwind_0(v22, &loc_18002C915);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v17);
    GetLocalTime(&SystemTime);
    word_1800662D8 = 0;
    LODWORD(v13) = SystemTime.wSecond;
    LODWORD(v12) = SystemTime.wMinute;
    LODWORD(v11) = SystemTime.wHour;
    LODWORD(v10) = SystemTime.wDay;
    LODWORD(v9) = SystemTime.wMonth;
    LODWORD(v8) = SystemTime.wYear;
    DumpProperties = StringCchPrintfW(
                       &FileName,
                       0x104u,
                       L"%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dmp",
                       Dst,
                       sz,
                       v8,
                       v9,
                       v10,
                       v11,
                       v12,
                       v13);
    v14 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    CreateDirectoryW(Dst, 0);
    CurrentProcessId = GetCurrentProcessId();
    DumpProperties = FF_RunCmd(L"%s %d %s full", L"RunDll32 comsvcs.dll,MiniDump", CurrentProcessId, &FileName);
    v14 = DumpProperties;
    if ( DumpProperties < 0 )
      return (unsigned int)DumpProperties;
    if ( _waccess(&FileName, 0) )
      DumpProperties = -2147467259;
    goto LABEL_18;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v16 = LastError;
  v20 = LastError;
  local_unwind_0(v22, &loc_18002C8E7);
  return v16;
}

```

## disassembly

```asm
0x18002c7ac  push    rbx
0x18002c7ae  sub     rsp, 310h
0x18002c7b5  mov     rax, cs:__security_cookie
0x18002c7bc  xor     rax, rsp
0x18002c7bf  mov     [rsp+318h+var_18], rax
0x18002c7c7  mov     [rsp+318h+var_290], rsp
0x18002c7cf  xor     edx, edx; Val
0x18002c7d1  lea     r8d, [rdx+50h]; Size
0x18002c7d5  lea     rcx, [rsp+318h+sz]; void *
0x18002c7dd  call    memset_0
0x18002c7e2  xor     edx, edx; Val
0x18002c7e4  mov     r8d, 20Ah; Size
0x18002c7ea  lea     rcx, [rsp+318h+Dst]; void *
0x18002c7f2  call    memset_0
0x18002c7f7  mov     [rsp+318h+lpSrc], 0
0x18002c800  xorps   xmm0, xmm0
0x18002c803  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x18002c80b  mov     [rsp+318h+var_2AC], 0Ah
0x18002c813  mov     [rsp+318h+var_2B4], 1
0x18002c81b  mov     [rsp+318h+rguid], 0
0x18002c824  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x18002c829  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x18002c82e  lea     rdx, [rsp+318h+var_2B4]; int *
0x18002c833  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x18002c838  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x18002c83d  mov     ebx, eax
0x18002c83f  mov     [rsp+318h+var_2B8], eax
0x18002c843  test    eax, eax
0x18002c845  jnz     loc_18002CA2F
0x18002c84b  cmp     [rsp+318h+var_2B4], eax
0x18002c84f  jnz     short loc_18002C85B
0x18002c851  mov     ebx, 1
0x18002c856  jmp     loc_18002CA2B
0x18002c85b  mov     rcx, [rsp+318h+rguid]; rguid
0x18002c860  test    rcx, rcx
0x18002c863  jz      short loc_18002C881
0x18002c865  mov     rax, [rcx]
0x18002c868  sub     rax, cs:APPLID_SystemApplication
0x18002c86f  jnz     short loc_18002C87C
0x18002c871  mov     rax, [rcx+8]
0x18002c875  sub     rax, cs:qword_1800547E8
0x18002c87c  test    rax, rax
0x18002c87f  jz      short loc_18002C851
0x18002c881  mov     r8d, 28h ; '('; cchMax
0x18002c887  lea     rdx, [rsp+318h+sz]; lpsz
0x18002c88f  call    cs:__imp_StringFromGUID2
0x18002c895  mov     ebx, 104h
0x18002c89a  mov     r8d, ebx; nSize
0x18002c89d  lea     rdx, [rsp+318h+Dst]; lpDst
0x18002c8a5  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x18002c8aa  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c8b0  test    eax, eax
0x18002c8b2  jnz     short loc_18002C8F0
0x18002c8b4  call    cs:__imp_GetLastError
0x18002c8ba  test    eax, eax
0x18002c8bc  jle     short loc_18002C8C6
0x18002c8be  movzx   eax, ax
0x18002c8c1  or      eax, 80070000h
0x18002c8c6  mov     [rsp+318h+var_2B0], eax
0x18002c8ca  mov     [rsp+318h+var_298], eax
0x18002c8d1  lea     rdx, loc_18002C8E7
0x18002c8d8  mov     rcx, [rsp+318h+var_290]
0x18002c8e0  call    _local_unwind_0
0x18002c8e5  nop
0x18002c8e6  nop
0x18002c8e7  mov     eax, [rsp+318h+var_2B0]
0x18002c8eb  jmp     loc_18002CA38
0x18002c8f0  cmp     eax, ebx
0x18002c8f2  jbe     short loc_18002C91F
0x18002c8f4  mov     [rsp+318h+var_294], 8007006Fh
0x18002c8ff  lea     rdx, loc_18002C915
0x18002c906  mov     rcx, [rsp+318h+var_290]
0x18002c90e  call    _local_unwind_0
0x18002c913  nop
0x18002c914  nop
0x18002c915  mov     eax, 8007006Fh
0x18002c91a  jmp     loc_18002CA38
0x18002c91f  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x18002c924  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x18002c92c  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x18002c934  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x18002c939  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x18002c941  call    cs:__imp_GetLocalTime
0x18002c947  xor     eax, eax
0x18002c949  mov     cs:word_1800662D8, ax
0x18002c950  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x18002c958  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x18002c960  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x18002c969  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x18002c972  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x18002c97b  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x18002c984  mov     dword ptr [rsp+318h+var_2C8], eax
0x18002c988  mov     dword ptr [rsp+318h+var_2D0], ecx
0x18002c98c  mov     dword ptr [rsp+318h+var_2D8], r8d
0x18002c991  mov     dword ptr [rsp+318h+var_2E0], r9d
0x18002c996  mov     dword ptr [rsp+318h+var_2E8], r10d
0x18002c99b  mov     dword ptr [rsp+318h+var_2F0], r11d
0x18002c9a0  lea     rax, [rsp+318h+sz]
0x18002c9a8  mov     [rsp+318h+var_2F8], rax
0x18002c9ad  lea     r9, [rsp+318h+Dst]
0x18002c9b5  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x18002c9bc  mov     rdx, rbx; unsigned __int64
0x18002c9bf  lea     rcx, FileName; unsigned __int16 *
0x18002c9c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c9cb  mov     ebx, eax
0x18002c9cd  mov     [rsp+318h+var_2B8], eax
0x18002c9d1  test    eax, eax
0x18002c9d3  js      short loc_18002CA2F
0x18002c9d5  xor     edx, edx; lpSecurityAttributes
0x18002c9d7  lea     rcx, [rsp+318h+Dst]; lpPathName
0x18002c9df  call    cs:__imp_CreateDirectoryW
0x18002c9e5  call    cs:__imp_GetCurrentProcessId
0x18002c9eb  mov     r8d, eax
0x18002c9ee  lea     r9, FileName
0x18002c9f5  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x18002c9fc  lea     rcx, aSDSFull; "%s %d %s full"
0x18002ca03  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x18002ca08  mov     ebx, eax
0x18002ca0a  mov     [rsp+318h+var_2B8], eax
0x18002ca0e  test    eax, eax
0x18002ca10  js      short loc_18002CA2F
0x18002ca12  xor     edx, edx; AccessMode
0x18002ca14  lea     rcx, FileName; FileName
0x18002ca1b  call    cs:__imp__waccess
0x18002ca21  mov     ecx, 80004005h
0x18002ca26  test    eax, eax
0x18002ca28  cmovnz  ebx, ecx
0x18002ca2b  mov     [rsp+318h+var_2B8], ebx
0x18002ca2f  jmp     short loc_18002CA36
0x18002ca31  mov     ebx, 8000FFFFh
0x18002ca36  mov     eax, ebx
0x18002ca38  mov     rcx, [rsp+318h+var_18]
0x18002ca40  xor     rcx, rsp; StackCookie
0x18002ca43  call    __security_check_cookie
0x18002ca48  add     rsp, 310h
0x18002ca4f  pop     rbx
0x18002ca50  retn
0x1800453b8  push    rbp
0x1800453ba  sub     rsp, 60h
0x1800453be  mov     rbp, rdx
0x1800453c1  add     rsp, 60h
0x1800453c5  pop     rbp
0x1800453c6  retn
```
