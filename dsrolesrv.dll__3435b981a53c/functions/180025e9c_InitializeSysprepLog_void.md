# InitializeSysprepLog(void)

- ea: `0x180025e9c`
- end: `0x1800260ad`
- name: `?InitializeSysprepLog@@YAKXZ`
- size: `529`
- prototype: `DWORD(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180026914`

## callees

- `0x18001ce20`
- `0x180025890`
- `0x180025e9c`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180025edc`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180025edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026024`
- `WDSCORE!WdsInitialize` at `0x180025f34`
- `WDSCORE!WdsInitialize` at `0x180025f34`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025fc0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002601e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002607c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025fc0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002601e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002607c`
- `WDSCORE!CurrentIP` at `0x180025f62`
- `WDSCORE!CurrentIP` at `0x180025fce`
- `WDSCORE!CurrentIP` at `0x18002602c`
- `WDSCORE!CurrentIP` at `0x180025f62`
- `WDSCORE!CurrentIP` at `0x180025fce`
- `WDSCORE!CurrentIP` at `0x18002602c`

## pseudocode

```c
DWORD InitializeSysprepLog(void)
{
  DWORD v1; // esi
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  unsigned __int16 v11[264]; // [rsp+60h] [rbp-458h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp-248h] BYREF

  if ( dword_18004DDB8 )
    return 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  StringCchPrintfW(v11, 0x104u, L"%ws\\Debug", Buffer);
  if ( (unsigned int)WdsInitialize(0, 0, v11, v11, 50393088, 0, 0) )
  {
    v1 = 0;
    LastError = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(0x4000000, "========================================================");
    WdsSetupLogMessageW(
      v4,
      983040,
      L"D",
      0,
      806,
      L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
      L"InitializeSysprepLog",
      v3,
      LastError,
      0,
      0);
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x4000000, "===    Beginning of a new sysprep run for cloning    ===");
    WdsSetupLogMessageW(
      v7,
      983040,
      L"D",
      0,
      807,
      L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
      L"InitializeSysprepLog",
      v6,
      v5,
      0,
      0);
    v8 = GetLastError();
    v9 = CurrentIP();
    v10 = ConstructPartialMsgW(0x4000000, "========================================================");
    WdsSetupLogMessageW(
      v10,
      983040,
      L"D",
      0,
      808,
      L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
      L"InitializeSysprepLog",
      v9,
      v8,
      0,
      0);
    dword_18004DDB8 = 1;
  }
  else
  {
    v1 = GetLastError();
    if ( !v1 )
      return 14109;
  }
  return v1;
}

```

## disassembly

```asm
0x180025e9c  push    rbx
0x180025e9e  push    rsi
0x180025e9f  push    rdi
0x180025ea0  push    r13
0x180025ea2  push    r15
0x180025ea4  sub     rsp, 490h
0x180025eab  mov     rax, cs:__security_cookie
0x180025eb2  xor     rax, rsp
0x180025eb5  mov     [rsp+4B8h+var_38], rax
0x180025ebd  cmp     cs:dword_18004DDB8, 0
0x180025ec4  jz      short loc_180025ECD
0x180025ec6  xor     eax, eax
0x180025ec8  jmp     loc_18002608E
0x180025ecd  mov     ebx, 104h
0x180025ed2  lea     rcx, [rsp+4B8h+Buffer]; lpBuffer
0x180025eda  mov     edx, ebx; uSize
0x180025edc  call    cs:__imp_GetWindowsDirectoryW
0x180025ee2  test    eax, eax
0x180025ee4  jnz     short loc_180025EF1
0x180025ee6  call    cs:__imp_GetLastError
0x180025eec  jmp     loc_18002608E
0x180025ef1  lea     r9, [rsp+4B8h+Buffer]
0x180025ef9  mov     rdx, rbx; unsigned __int64
0x180025efc  lea     r8, aWsDebug; "%ws\\Debug"
0x180025f03  lea     rcx, [rsp+4B8h+var_458]; unsigned __int16 *
0x180025f08  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025f0d  mov     [rsp+4B8h+var_488], 0
0x180025f16  lea     r9, [rsp+4B8h+var_458]
0x180025f1b  mov     dword ptr [rsp+4B8h+var_490], 0
0x180025f23  lea     r8, [rsp+4B8h+var_458]
0x180025f28  xor     edx, edx
0x180025f2a  mov     [rsp+4B8h+var_498], 300F000h
0x180025f32  xor     ecx, ecx
0x180025f34  call    cs:__imp_WdsInitialize
0x180025f3a  test    eax, eax
0x180025f3c  jnz     short loc_180025F58
0x180025f3e  call    cs:__imp_GetLastError
0x180025f44  mov     esi, eax
0x180025f46  test    eax, eax
0x180025f48  jnz     loc_18002608C
0x180025f4e  mov     esi, 371Dh
0x180025f53  jmp     loc_18002608C
0x180025f58  xor     esi, esi
0x180025f5a  call    cs:__imp_GetLastError
0x180025f60  mov     edi, eax
0x180025f62  call    cs:__imp_CurrentIP
0x180025f68  lea     rdx, asc_180043120; "======================================="...
0x180025f6f  mov     ecx, 4000000h; unsigned int
0x180025f74  mov     rbx, rax
0x180025f77  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025f7c  mov     [rsp+4B8h+var_468], esi
0x180025f80  lea     r13, aInitializesysp; "InitializeSysprepLog"
0x180025f87  mov     [rsp+4B8h+var_470], rsi
0x180025f8c  lea     r15, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025f93  mov     [rsp+4B8h+var_478], edi
0x180025f97  lea     r8, aD_0; "D"
0x180025f9e  mov     [rsp+4B8h+var_480], rbx
0x180025fa3  xor     r9d, r9d
0x180025fa6  mov     [rsp+4B8h+var_488], r13
0x180025fab  mov     edx, 0F0000h
0x180025fb0  mov     [rsp+4B8h+var_490], r15
0x180025fb5  mov     rcx, rax
0x180025fb8  mov     [rsp+4B8h+var_498], 326h
0x180025fc0  call    cs:__imp_WdsSetupLogMessageW
0x180025fc6  call    cs:__imp_GetLastError
0x180025fcc  mov     edi, eax
0x180025fce  call    cs:__imp_CurrentIP
0x180025fd4  lea     rdx, aBeginningOfANe; "===    Beginning of a new sysprep run f"...
0x180025fdb  mov     ecx, 4000000h; unsigned int
0x180025fe0  mov     rbx, rax
0x180025fe3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180025fe8  mov     [rsp+4B8h+var_468], esi
0x180025fec  lea     r8, aD_0; "D"
0x180025ff3  mov     [rsp+4B8h+var_470], rsi
0x180025ff8  xor     r9d, r9d
0x180025ffb  mov     [rsp+4B8h+var_478], edi
0x180025fff  mov     edx, 0F0000h
0x180026004  mov     [rsp+4B8h+var_480], rbx
0x180026009  mov     rcx, rax
0x18002600c  mov     [rsp+4B8h+var_488], r13
0x180026011  mov     [rsp+4B8h+var_490], r15
0x180026016  mov     [rsp+4B8h+var_498], 327h
0x18002601e  call    cs:__imp_WdsSetupLogMessageW
0x180026024  call    cs:__imp_GetLastError
0x18002602a  mov     edi, eax
0x18002602c  call    cs:__imp_CurrentIP
0x180026032  lea     rdx, asc_180043120; "======================================="...
0x180026039  mov     ecx, 4000000h; unsigned int
0x18002603e  mov     rbx, rax
0x180026041  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180026046  mov     [rsp+4B8h+var_468], esi
0x18002604a  lea     r8, aD_0; "D"
0x180026051  mov     [rsp+4B8h+var_470], rsi
0x180026056  xor     r9d, r9d
0x180026059  mov     [rsp+4B8h+var_478], edi
0x18002605d  mov     edx, 0F0000h
0x180026062  mov     [rsp+4B8h+var_480], rbx
0x180026067  mov     rcx, rax
0x18002606a  mov     [rsp+4B8h+var_488], r13
0x18002606f  mov     [rsp+4B8h+var_490], r15
0x180026074  mov     [rsp+4B8h+var_498], 328h
0x18002607c  call    cs:__imp_WdsSetupLogMessageW
0x180026082  mov     cs:dword_18004DDB8, 1
0x18002608c  mov     eax, esi
0x18002608e  mov     rcx, [rsp+4B8h+var_38]
0x180026096  xor     rcx, rsp; StackCookie
0x180026099  call    __security_check_cookie
0x18002609e  add     rsp, 490h
0x1800260a5  pop     r15
0x1800260a7  pop     r13
0x1800260a9  pop     rdi
0x1800260aa  pop     rsi
0x1800260ab  pop     rbx
0x1800260ac  retn
```
