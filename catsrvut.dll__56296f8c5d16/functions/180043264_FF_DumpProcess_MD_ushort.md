# FF_DumpProcess_MD(ushort *)

- ea: `0x180043264`
- end: `0x180043509`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043188`

## callees

- `0x18000717c`
- `0x180043264`
- `0x180043510`
- `0x18004370c`
- `0x1800438fc`
- `0x180055816`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `msvcrt!_waccess` at `0x1800434d3`
- `msvcrt!_waccess` at `0x1800434d3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043347`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004336c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004336c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800433f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800433f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004349d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004349d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043497`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180043497`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043362`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043362`

## string_xrefs

- `0x1800434ad`: `RunDll32 comsvcs.dll,MiniDump`

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
      local_unwind_0(v22, &loc_1800433CD);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v17);
    GetLocalTime(&SystemTime);
    word_180075298 = 0;
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
  local_unwind_0(v22, &loc_18004339F);
  return v16;
}

```

## disassembly

```asm
0x180043264  push    rbx
0x180043266  sub     rsp, 310h
0x18004326d  mov     rax, cs:__security_cookie
0x180043274  xor     rax, rsp
0x180043277  mov     [rsp+318h+var_18], rax
0x18004327f  mov     [rsp+318h+var_290], rsp
0x180043287  xor     edx, edx; Val
0x180043289  lea     r8d, [rdx+50h]; Size
0x18004328d  lea     rcx, [rsp+318h+sz]; void *
0x180043295  call    memset_0
0x18004329a  xor     edx, edx; Val
0x18004329c  mov     r8d, 20Ah; Size
0x1800432a2  lea     rcx, [rsp+318h+Dst]; void *
0x1800432aa  call    memset_0
0x1800432af  mov     [rsp+318h+lpSrc], 0
0x1800432b8  xorps   xmm0, xmm0
0x1800432bb  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x1800432c3  mov     [rsp+318h+var_2AC], 0Ah
0x1800432cb  mov     [rsp+318h+var_2B4], 1
0x1800432d3  mov     [rsp+318h+rguid], 0
0x1800432dc  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x1800432e1  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x1800432e6  lea     rdx, [rsp+318h+var_2B4]; int *
0x1800432eb  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x1800432f0  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x1800432f5  mov     ebx, eax
0x1800432f7  mov     [rsp+318h+var_2B8], eax
0x1800432fb  test    eax, eax
0x1800432fd  jnz     loc_1800434E7
0x180043303  cmp     [rsp+318h+var_2B4], eax
0x180043307  jnz     short loc_180043313
0x180043309  mov     ebx, 1
0x18004330e  jmp     loc_1800434E3
0x180043313  mov     rcx, [rsp+318h+rguid]; rguid
0x180043318  test    rcx, rcx
0x18004331b  jz      short loc_180043339
0x18004331d  mov     rax, [rcx]
0x180043320  sub     rax, cs:APPLID_SystemApplication
0x180043327  jnz     short loc_180043334
0x180043329  mov     rax, [rcx+8]
0x18004332d  sub     rax, cs:qword_180065FC8
0x180043334  test    rax, rax
0x180043337  jz      short loc_180043309
0x180043339  mov     r8d, 28h ; '('; cchMax
0x18004333f  lea     rdx, [rsp+318h+sz]; lpsz
0x180043347  call    cs:__imp_StringFromGUID2
0x18004334d  mov     ebx, 104h
0x180043352  mov     r8d, ebx; nSize
0x180043355  lea     rdx, [rsp+318h+Dst]; lpDst
0x18004335d  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x180043362  call    cs:__imp_ExpandEnvironmentStringsW
0x180043368  test    eax, eax
0x18004336a  jnz     short loc_1800433A8
0x18004336c  call    cs:__imp_GetLastError
0x180043372  test    eax, eax
0x180043374  jle     short loc_18004337E
0x180043376  movzx   eax, ax
0x180043379  or      eax, 80070000h
0x18004337e  mov     [rsp+318h+var_2B0], eax
0x180043382  mov     [rsp+318h+var_298], eax
0x180043389  lea     rdx, loc_18004339F
0x180043390  mov     rcx, [rsp+318h+var_290]
0x180043398  call    _local_unwind_0
0x18004339d  nop
0x18004339e  nop
0x18004339f  mov     eax, [rsp+318h+var_2B0]
0x1800433a3  jmp     loc_1800434F0
0x1800433a8  cmp     eax, ebx
0x1800433aa  jbe     short loc_1800433D7
0x1800433ac  mov     [rsp+318h+var_294], 8007006Fh
0x1800433b7  lea     rdx, loc_1800433CD
0x1800433be  mov     rcx, [rsp+318h+var_290]
0x1800433c6  call    _local_unwind_0
0x1800433cb  nop
0x1800433cc  nop
0x1800433cd  mov     eax, 8007006Fh
0x1800433d2  jmp     loc_1800434F0
0x1800433d7  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x1800433dc  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x1800433e4  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x1800433ec  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x1800433f1  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x1800433f9  call    cs:__imp_GetLocalTime
0x1800433ff  xor     eax, eax
0x180043401  mov     cs:word_180075298, ax
0x180043408  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x180043410  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x180043418  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x180043421  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x18004342a  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x180043433  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x18004343c  mov     dword ptr [rsp+318h+var_2C8], eax
0x180043440  mov     dword ptr [rsp+318h+var_2D0], ecx
0x180043444  mov     dword ptr [rsp+318h+var_2D8], r8d
0x180043449  mov     dword ptr [rsp+318h+var_2E0], r9d
0x18004344e  mov     dword ptr [rsp+318h+var_2E8], r10d
0x180043453  mov     dword ptr [rsp+318h+var_2F0], r11d
0x180043458  lea     rax, [rsp+318h+sz]
0x180043460  mov     [rsp+318h+var_2F8], rax
0x180043465  lea     r9, [rsp+318h+Dst]
0x18004346d  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x180043474  mov     rdx, rbx; unsigned __int64
0x180043477  lea     rcx, FileName; unsigned __int16 *
0x18004347e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043483  mov     ebx, eax
0x180043485  mov     [rsp+318h+var_2B8], eax
0x180043489  test    eax, eax
0x18004348b  js      short loc_1800434E7
0x18004348d  xor     edx, edx; lpSecurityAttributes
0x18004348f  lea     rcx, [rsp+318h+Dst]; lpPathName
0x180043497  call    cs:__imp_CreateDirectoryW
0x18004349d  call    cs:__imp_GetCurrentProcessId
0x1800434a3  mov     r8d, eax
0x1800434a6  lea     r9, FileName
0x1800434ad  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x1800434b4  lea     rcx, aSDSFull; "%s %d %s full"
0x1800434bb  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x1800434c0  mov     ebx, eax
0x1800434c2  mov     [rsp+318h+var_2B8], eax
0x1800434c6  test    eax, eax
0x1800434c8  js      short loc_1800434E7
0x1800434ca  xor     edx, edx; AccessMode
0x1800434cc  lea     rcx, FileName; FileName
0x1800434d3  call    cs:__imp__waccess
0x1800434d9  mov     ecx, 80004005h
0x1800434de  test    eax, eax
0x1800434e0  cmovnz  ebx, ecx
0x1800434e3  mov     [rsp+318h+var_2B8], ebx
0x1800434e7  jmp     short loc_1800434EE
0x1800434e9  mov     ebx, 8000FFFFh
0x1800434ee  mov     eax, ebx
0x1800434f0  mov     rcx, [rsp+318h+var_18]
0x1800434f8  xor     rcx, rsp; StackCookie
0x1800434fb  call    __security_check_cookie
0x180043500  add     rsp, 310h
0x180043507  pop     rbx
0x180043508  retn
0x180056532  push    rbp
0x180056534  sub     rsp, 60h
0x180056538  mov     rbp, rdx
0x18005653b  add     rsp, 60h
0x18005653f  pop     rbp
0x180056540  retn
```
