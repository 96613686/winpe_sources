# FF_DumpProcess_MD(ushort *)

- ea: `0x1400037ac`
- end: `0x140003a4e`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400036d0`

## callees

- `0x1400019cf`
- `0x1400028f4`
- `0x1400037ac`
- `0x140003a54`
- `0x140003c50`
- `0x140003e74`
- `0x140006ed6`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400038a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400038a7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000388c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000388c`
- `msvcrt!_waccess` at `0x140003a18`
- `msvcrt!_waccess` at `0x140003a18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400039e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400039e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14000393e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14000393e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400039dc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1400039dc`

## string_xrefs

- `0x1400039f2`: `RunDll32 comsvcs.dll,MiniDump`

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
      local_unwind_0(v21, &loc_140003912);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v16);
    GetLocalTime(&SystemTime);
    word_140010528 = 0;
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
  local_unwind_0(v21, &loc_1400038E4);
  return v15;
}

```

## disassembly

```asm
0x1400037ac  push    rbx
0x1400037ae  sub     rsp, 310h
0x1400037b5  mov     rax, cs:__security_cookie
0x1400037bc  xor     rax, rsp
0x1400037bf  mov     [rsp+318h+var_18], rax
0x1400037c7  mov     [rsp+318h+var_290], rsp
0x1400037cf  xor     edx, edx; Val
0x1400037d1  lea     r8d, [rdx+50h]; Size
0x1400037d5  lea     rcx, [rsp+318h+sz]; void *
0x1400037dd  call    memset_0
0x1400037e2  xor     edx, edx; Val
0x1400037e4  mov     r8d, 20Ah; Size
0x1400037ea  lea     rcx, [rsp+318h+Dst]; void *
0x1400037f2  call    memset_0
0x1400037f7  mov     [rsp+318h+lpSrc], 0
0x140003800  xorps   xmm0, xmm0
0x140003803  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x14000380b  mov     [rsp+318h+var_2AC], 0Ah
0x140003813  mov     [rsp+318h+var_2B4], 1
0x14000381b  mov     [rsp+318h+rguid], 0
0x140003824  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x140003829  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x14000382e  lea     rdx, [rsp+318h+var_2B4]; int *
0x140003833  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x140003838  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x14000383d  mov     ebx, eax
0x14000383f  mov     [rsp+318h+var_2B8], eax
0x140003843  test    eax, eax
0x140003845  jnz     loc_140003A2C
0x14000384b  cmp     [rsp+318h+var_2B4], eax
0x14000384f  jnz     short loc_14000385B
0x140003851  mov     ebx, 1
0x140003856  jmp     loc_140003A28
0x14000385b  mov     rcx, [rsp+318h+rguid]; rguid
0x140003860  test    rcx, rcx
0x140003863  jz      short loc_14000387E
0x140003865  mov     rax, [rcx]
0x140003868  cmp     rax, cs:APPLID_SystemApplication
0x14000386f  jnz     short loc_14000387E
0x140003871  mov     rax, [rcx+8]
0x140003875  cmp     rax, cs:qword_14000ADC8
0x14000387c  jz      short loc_140003851
0x14000387e  mov     r8d, 28h ; '('; cchMax
0x140003884  lea     rdx, [rsp+318h+sz]; lpsz
0x14000388c  call    cs:__imp_StringFromGUID2
0x140003892  mov     ebx, 104h
0x140003897  mov     r8d, ebx; nSize
0x14000389a  lea     rdx, [rsp+318h+Dst]; lpDst
0x1400038a2  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x1400038a7  call    cs:__imp_ExpandEnvironmentStringsW
0x1400038ad  test    eax, eax
0x1400038af  jnz     short loc_1400038ED
0x1400038b1  call    cs:__imp_GetLastError
0x1400038b7  test    eax, eax
0x1400038b9  jle     short loc_1400038C3
0x1400038bb  movzx   eax, ax
0x1400038be  or      eax, 80070000h
0x1400038c3  mov     [rsp+318h+var_2B0], eax
0x1400038c7  mov     [rsp+318h+var_298], eax
0x1400038ce  lea     rdx, loc_1400038E4
0x1400038d5  mov     rcx, [rsp+318h+var_290]
0x1400038dd  call    _local_unwind_0
0x1400038e2  nop
0x1400038e3  nop
0x1400038e4  mov     eax, [rsp+318h+var_2B0]
0x1400038e8  jmp     loc_140003A35
0x1400038ed  cmp     eax, ebx
0x1400038ef  jbe     short loc_14000391C
0x1400038f1  mov     [rsp+318h+var_294], 8007006Fh
0x1400038fc  lea     rdx, loc_140003912
0x140003903  mov     rcx, [rsp+318h+var_290]
0x14000390b  call    _local_unwind_0
0x140003910  nop
0x140003911  nop
0x140003912  mov     eax, 8007006Fh
0x140003917  jmp     loc_140003A35
0x14000391c  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x140003921  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x140003929  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x140003931  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x140003936  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x14000393e  call    cs:__imp_GetLocalTime
0x140003944  xor     eax, eax
0x140003946  mov     cs:word_140010528, ax
0x14000394d  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x140003955  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x14000395d  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x140003966  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x14000396f  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x140003978  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x140003981  mov     dword ptr [rsp+318h+var_2C8], eax
0x140003985  mov     dword ptr [rsp+318h+var_2D0], ecx
0x140003989  mov     dword ptr [rsp+318h+var_2D8], r8d
0x14000398e  mov     dword ptr [rsp+318h+var_2E0], r9d
0x140003993  mov     dword ptr [rsp+318h+var_2E8], r10d
0x140003998  mov     dword ptr [rsp+318h+var_2F0], r11d
0x14000399d  lea     rax, [rsp+318h+sz]
0x1400039a5  mov     [rsp+318h+var_2F8], rax
0x1400039aa  lea     r9, [rsp+318h+Dst]
0x1400039b2  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x1400039b9  mov     rdx, rbx; unsigned __int64
0x1400039bc  lea     rcx, FileName; unsigned __int16 *
0x1400039c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400039c8  mov     ebx, eax
0x1400039ca  mov     [rsp+318h+var_2B8], eax
0x1400039ce  test    eax, eax
0x1400039d0  js      short loc_140003A2C
0x1400039d2  xor     edx, edx; lpSecurityAttributes
0x1400039d4  lea     rcx, [rsp+318h+Dst]; lpPathName
0x1400039dc  call    cs:__imp_CreateDirectoryW
0x1400039e2  call    cs:__imp_GetCurrentProcessId
0x1400039e8  mov     r8d, eax
0x1400039eb  lea     r9, FileName
0x1400039f2  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x1400039f9  lea     rcx, aSDSFull; "%s %d %s full"
0x140003a00  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x140003a05  mov     ebx, eax
0x140003a07  mov     [rsp+318h+var_2B8], eax
0x140003a0b  test    eax, eax
0x140003a0d  js      short loc_140003A2C
0x140003a0f  xor     edx, edx; AccessMode
0x140003a11  lea     rcx, FileName; FileName
0x140003a18  call    cs:__imp__waccess
0x140003a1e  mov     ecx, 80004005h
0x140003a23  test    eax, eax
0x140003a25  cmovnz  ebx, ecx
0x140003a28  mov     [rsp+318h+var_2B8], ebx
0x140003a2c  jmp     short loc_140003A33
0x140003a2e  mov     ebx, 8000FFFFh
0x140003a33  mov     eax, ebx
0x140003a35  mov     rcx, [rsp+318h+var_18]
0x140003a3d  xor     rcx, rsp; StackCookie
0x140003a40  call    __security_check_cookie
0x140003a45  add     rsp, 310h
0x140003a4c  pop     rbx
0x140003a4d  retn
0x140007097  push    rbp
0x140007099  sub     rsp, 60h
0x14000709d  mov     rbp, rdx
0x1400070a0  add     rsp, 60h
0x1400070a4  pop     rbp
0x1400070a5  retn
```
