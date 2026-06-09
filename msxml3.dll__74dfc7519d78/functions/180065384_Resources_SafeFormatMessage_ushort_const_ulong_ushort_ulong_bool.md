# Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)

- ea: `0x180065384`
- end: `0x1800654e4`
- name: `?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z`
- size: `352`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, DWORD dwMessageId@<edx>, LPWSTR lpBuffer@<r8>, unsigned int@<r9d>, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800384a8`

## callees

- `0x180042064`
- `0x180065384`
- `0x1800654ec`
- `0x180102d20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065464`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065464`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800654b8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800654b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065447`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180065447`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006549e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006549e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800653d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800653d7`

## pseudocode

```c
__int64 __fastcall Resources::SafeFormatMessage(
        const unsigned __int16 *a1,
        DWORD dwMessageId,
        LPWSTR lpBuffer,
        __int64 a4,
        bool a5)
{
  DWORD v8; // edi
  HMODULE v9; // rbx
  DWORD v10; // r8d
  DWORD nSize; // [rsp+28h] [rbp-270h]
  unsigned __int64 Library; // [rsp+40h] [rbp-258h] BYREF
  DWORD v14; // [rsp+48h] [rbp-250h]
  unsigned __int16 *v15; // [rsp+50h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-238h] BYREF

  v15 = 0;
  Library = 0;
  v8 = 0;
  v14 = 0;
  Buffer[0] = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102
    || (int)StringCchCatExW(Buffer, 0x104u, L"\\", &v15, &Library, nSize) < 0
    || StringCchCopyW(v15, Library, a1) < 0 )
  {
    return v8;
  }
  if ( a5 )
  {
    v9 = 0;
    Library = 0;
    if ( !GetModuleHandleW(Buffer) )
      goto LABEL_9;
    v10 = 0;
  }
  else
  {
    v10 = 2;
  }
  Library = (unsigned __int64)LoadLibraryExW(Buffer, 0, v10);
  v9 = (HMODULE)Library;
LABEL_9:
  if ( v9 )
  {
    v8 = FormatMessageW(0x800u, v9, dwMessageId, 0x400u, lpBuffer, 0x1000u, 0);
    v14 = v8;
    FreeLibrary(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180065384  mov     [rsp+arg_18], rbx
0x180065389  push    rsi
0x18006538a  push    rdi
0x18006538b  push    r14
0x18006538d  sub     rsp, 280h
0x180065394  mov     rax, cs:__security_cookie
0x18006539b  xor     rax, rsp
0x18006539e  mov     [rsp+298h+var_28], rax
0x1800653a6  mov     r14, r8
0x1800653a9  mov     esi, edx
0x1800653ab  mov     rbx, rcx
0x1800653ae  mov     [rsp+298h+var_248], 0
0x1800653b7  mov     [rsp+298h+var_258], 0
0x1800653c0  xor     edi, edi
0x1800653c2  mov     [rsp+298h+var_250], edi
0x1800653c6  xor     eax, eax
0x1800653c8  mov     [rsp+298h+Buffer], ax
0x1800653cd  mov     edx, 104h; uSize
0x1800653d2  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x1800653d7  call    cs:__imp_GetSystemDirectoryW
0x1800653dd  dec     eax
0x1800653df  cmp     eax, 102h
0x1800653e4  ja      loc_1800654BE
0x1800653ea  lea     rax, [rsp+298h+var_258]
0x1800653ef  mov     [rsp+298h+lpBuffer], rax; unsigned __int64 *
0x1800653f4  lea     r9, [rsp+298h+var_248]; unsigned __int16 **
0x1800653f9  lea     r8, asc_18012E030; "\\"
0x180065400  mov     edx, 104h; unsigned __int64
0x180065405  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x18006540a  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18006540f  test    eax, eax
0x180065411  js      loc_1800654BE
0x180065417  mov     r8, rbx; unsigned __int16 *
0x18006541a  mov     rdx, [rsp+298h+var_258]; unsigned __int64
0x18006541f  mov     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x180065424  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180065429  test    eax, eax
0x18006542b  js      loc_1800654BE
0x180065431  lea     rcx, [rsp+298h+Buffer]; lpLibFileName
0x180065436  cmp     [rsp+298h+arg_20], dil
0x18006543e  jz      short loc_18006545C
0x180065440  xor     ebx, ebx
0x180065442  mov     [rsp+298h+var_258], rbx
0x180065447  call    cs:__imp_GetModuleHandleW
0x18006544d  test    rax, rax
0x180065450  jz      short loc_180065472
0x180065452  xor     r8d, r8d
0x180065455  lea     rcx, [rsp+298h+Buffer]
0x18006545a  jmp     short loc_180065462
0x18006545c  mov     r8d, 2; dwFlags
0x180065462  xor     edx, edx; hFile
0x180065464  call    cs:__imp_LoadLibraryExW
0x18006546a  mov     [rsp+298h+var_258], rax
0x18006546f  mov     rbx, rax
0x180065472  test    rbx, rbx
0x180065475  jz      short loc_1800654BE
0x180065477  mov     [rsp+298h+Arguments], 0; Arguments
0x180065480  mov     [rsp+298h+nSize], 1000h; nSize
0x180065488  mov     [rsp+298h+lpBuffer], r14; lpBuffer
0x18006548d  mov     r9d, 400h; dwLanguageId
0x180065493  mov     r8d, esi; dwMessageId
0x180065496  mov     rdx, rbx; lpSource
0x180065499  mov     ecx, 800h; dwFlags
0x18006549e  call    cs:__imp_FormatMessageW
0x1800654a4  mov     edi, eax
0x1800654a6  mov     [rsp+298h+var_250], eax
0x1800654aa  jmp     short loc_1800654B5
0x1800654ac  mov     edi, [rsp+298h+var_250]
0x1800654b0  mov     rbx, [rsp+298h+var_258]
0x1800654b5  mov     rcx, rbx; hLibModule
0x1800654b8  call    cs:__imp_FreeLibrary
0x1800654be  mov     eax, edi
0x1800654c0  mov     rcx, [rsp+298h+var_28]
0x1800654c8  xor     rcx, rsp; StackCookie
0x1800654cb  call    __security_check_cookie
0x1800654d0  mov     rbx, [rsp+298h+arg_18]
0x1800654d8  add     rsp, 280h
0x1800654df  pop     r14
0x1800654e1  pop     rdi
0x1800654e2  pop     rsi
0x1800654e3  retn
```
