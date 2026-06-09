# FF_DumpProcess_MD(ushort *)

- ea: `0x1800320ac`
- end: `0x180032351`
- name: `?FF_DumpProcess_MD@@YAJPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031fd0`

## callees

- `0x180009ee0`
- `0x1800320ac`
- `0x180032358`
- `0x180032554`
- `0x180032744`
- `0x1800554f6`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!_waccess` at `0x18003231b`
- `msvcrt!_waccess` at `0x18003231b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180032241`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180032241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800322e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800322e5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800322df`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800322df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800321aa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800321aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003218f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003218f`

## string_xrefs

- `0x1800322f5`: `RunDll32 comsvcs.dll,MiniDump`

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
      local_unwind_0(v22, &loc_180032215);
      return 2147942511LL;
    }
    FF_RemoveLegacyDump(sz, Dst, v17);
    GetLocalTime(&SystemTime);
    word_180075438 = 0;
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
  local_unwind_0(v22, &loc_1800321E7);
  return v16;
}

```

## disassembly

```asm
0x1800320ac  push    rbx
0x1800320ae  sub     rsp, 310h
0x1800320b5  mov     rax, cs:__security_cookie
0x1800320bc  xor     rax, rsp
0x1800320bf  mov     [rsp+318h+var_18], rax
0x1800320c7  mov     [rsp+318h+var_290], rsp
0x1800320cf  xor     edx, edx; Val
0x1800320d1  lea     r8d, [rdx+50h]; Size
0x1800320d5  lea     rcx, [rsp+318h+sz]; void *
0x1800320dd  call    memset_0
0x1800320e2  xor     edx, edx; Val
0x1800320e4  mov     r8d, 20Ah; Size
0x1800320ea  lea     rcx, [rsp+318h+Dst]; void *
0x1800320f2  call    memset_0
0x1800320f7  mov     [rsp+318h+lpSrc], 0
0x180032100  xorps   xmm0, xmm0
0x180032103  movups  xmmword ptr [rsp+318h+SystemTime.wYear], xmm0
0x18003210b  mov     [rsp+318h+var_2AC], 0Ah
0x180032113  mov     [rsp+318h+var_2B4], 1
0x18003211b  mov     [rsp+318h+rguid], 0
0x180032124  lea     r9, [rsp+318h+var_2AC]; unsigned int *
0x180032129  lea     r8, [rsp+318h+lpSrc]; unsigned __int16 **
0x18003212e  lea     rdx, [rsp+318h+var_2B4]; int *
0x180032133  lea     rcx, [rsp+318h+rguid]; struct _GUID **
0x180032138  call    ?FF_GetDumpProperties@@YAJPEAPEAU_GUID@@PEAHPEAPEAGPEAK@Z; FF_GetDumpProperties(_GUID * *,int *,ushort * *,ulong *)
0x18003213d  mov     ebx, eax
0x18003213f  mov     [rsp+318h+var_2B8], eax
0x180032143  test    eax, eax
0x180032145  jnz     loc_18003232F
0x18003214b  cmp     [rsp+318h+var_2B4], eax
0x18003214f  jnz     short loc_18003215B
0x180032151  mov     ebx, 1
0x180032156  jmp     loc_18003232B
0x18003215b  mov     rcx, [rsp+318h+rguid]; rguid
0x180032160  test    rcx, rcx
0x180032163  jz      short loc_180032181
0x180032165  mov     rax, [rcx]
0x180032168  sub     rax, cs:APPLID_SystemApplication
0x18003216f  jnz     short loc_18003217C
0x180032171  mov     rax, [rcx+8]
0x180032175  sub     rax, cs:qword_180064328
0x18003217c  test    rax, rax
0x18003217f  jz      short loc_180032151
0x180032181  mov     r8d, 28h ; '('; cchMax
0x180032187  lea     rdx, [rsp+318h+sz]; lpsz
0x18003218f  call    cs:__imp_StringFromGUID2
0x180032195  mov     ebx, 104h
0x18003219a  mov     r8d, ebx; nSize
0x18003219d  lea     rdx, [rsp+318h+Dst]; lpDst
0x1800321a5  mov     rcx, [rsp+318h+lpSrc]; lpSrc
0x1800321aa  call    cs:__imp_ExpandEnvironmentStringsW
0x1800321b0  test    eax, eax
0x1800321b2  jnz     short loc_1800321F0
0x1800321b4  call    cs:__imp_GetLastError
0x1800321ba  test    eax, eax
0x1800321bc  jle     short loc_1800321C6
0x1800321be  movzx   eax, ax
0x1800321c1  or      eax, 80070000h
0x1800321c6  mov     [rsp+318h+var_2B0], eax
0x1800321ca  mov     [rsp+318h+var_298], eax
0x1800321d1  lea     rdx, loc_1800321E7
0x1800321d8  mov     rcx, [rsp+318h+var_290]
0x1800321e0  call    _local_unwind_0
0x1800321e5  nop
0x1800321e6  nop
0x1800321e7  mov     eax, [rsp+318h+var_2B0]
0x1800321eb  jmp     loc_180032338
0x1800321f0  cmp     eax, ebx
0x1800321f2  jbe     short loc_18003221F
0x1800321f4  mov     [rsp+318h+var_294], 8007006Fh
0x1800321ff  lea     rdx, loc_180032215
0x180032206  mov     rcx, [rsp+318h+var_290]
0x18003220e  call    _local_unwind_0
0x180032213  nop
0x180032214  nop
0x180032215  mov     eax, 8007006Fh
0x18003221a  jmp     loc_180032338
0x18003221f  mov     r8d, [rsp+318h+var_2AC]; unsigned int
0x180032224  lea     rdx, [rsp+318h+Dst]; unsigned __int16 *
0x18003222c  lea     rcx, [rsp+318h+sz]; unsigned __int16 *
0x180032234  call    ?FF_RemoveLegacyDump@@YAXPEBG0K@Z; FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)
0x180032239  lea     rcx, [rsp+318h+SystemTime]; lpSystemTime
0x180032241  call    cs:__imp_GetLocalTime
0x180032247  xor     eax, eax
0x180032249  mov     cs:word_180075438, ax
0x180032250  movzx   eax, [rsp+318h+SystemTime.wSecond]
0x180032258  movzx   ecx, [rsp+318h+SystemTime.wMinute]
0x180032260  movzx   r8d, [rsp+318h+SystemTime.wHour]
0x180032269  movzx   r9d, [rsp+318h+SystemTime.wDay]
0x180032272  movzx   r10d, [rsp+318h+SystemTime.wMonth]
0x18003227b  movzx   r11d, [rsp+318h+SystemTime.wYear]
0x180032284  mov     dword ptr [rsp+318h+var_2C8], eax
0x180032288  mov     dword ptr [rsp+318h+var_2D0], ecx
0x18003228c  mov     dword ptr [rsp+318h+var_2D8], r8d
0x180032291  mov     dword ptr [rsp+318h+var_2E0], r9d
0x180032296  mov     dword ptr [rsp+318h+var_2E8], r10d
0x18003229b  mov     dword ptr [rsp+318h+var_2F0], r11d
0x1800322a0  lea     rax, [rsp+318h+sz]
0x1800322a8  mov     [rsp+318h+var_2F8], rax
0x1800322ad  lea     r9, [rsp+318h+Dst]
0x1800322b5  lea     r8, aSS04d02d02d02d; "%s\\%s_%04d_%02d_%02d_%02d_%02d_%02d.dm"...
0x1800322bc  mov     rdx, rbx; unsigned __int64
0x1800322bf  lea     rcx, FileName; unsigned __int16 *
0x1800322c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800322cb  mov     ebx, eax
0x1800322cd  mov     [rsp+318h+var_2B8], eax
0x1800322d1  test    eax, eax
0x1800322d3  js      short loc_18003232F
0x1800322d5  xor     edx, edx; lpSecurityAttributes
0x1800322d7  lea     rcx, [rsp+318h+Dst]; lpPathName
0x1800322df  call    cs:__imp_CreateDirectoryW
0x1800322e5  call    cs:__imp_GetCurrentProcessId
0x1800322eb  mov     r8d, eax
0x1800322ee  lea     r9, FileName
0x1800322f5  lea     rdx, aRundll32Comsvc; "RunDll32 comsvcs.dll,MiniDump"
0x1800322fc  lea     rcx, aSDSFull; "%s %d %s full"
0x180032303  call    ?FF_RunCmd@@YAJPEBGZZ; FF_RunCmd(ushort const *,...)
0x180032308  mov     ebx, eax
0x18003230a  mov     [rsp+318h+var_2B8], eax
0x18003230e  test    eax, eax
0x180032310  js      short loc_18003232F
0x180032312  xor     edx, edx; AccessMode
0x180032314  lea     rcx, FileName; FileName
0x18003231b  call    cs:__imp__waccess
0x180032321  mov     ecx, 80004005h
0x180032326  test    eax, eax
0x180032328  cmovnz  ebx, ecx
0x18003232b  mov     [rsp+318h+var_2B8], ebx
0x18003232f  jmp     short loc_180032336
0x180032331  mov     ebx, 8000FFFFh
0x180032336  mov     eax, ebx
0x180032338  mov     rcx, [rsp+318h+var_18]
0x180032340  xor     rcx, rsp; StackCookie
0x180032343  call    __security_check_cookie
0x180032348  add     rsp, 310h
0x18003234f  pop     rbx
0x180032350  retn
0x180056bd6  push    rbp
0x180056bd8  sub     rsp, 60h
0x180056bdc  mov     rbp, rdx
0x180056bdf  add     rsp, 60h
0x180056be3  pop     rbp
0x180056be4  retn
```
