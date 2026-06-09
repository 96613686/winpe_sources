# CJobManager::GetErrorDescription(long,ulong,ushort * *)

- ea: `0x180084418`
- end: `0x1800845e4`
- name: `?GetErrorDescription@CJobManager@@QEAAJJKPEAPEAG@Z`
- size: `460`
- prototype: `int __fastcall(CJobManager *this, DWORD, DWORD, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800ae054`
- `0x1800f1524`
- `0x1800f1640`

## callees

- `0x1800791a4`
- `0x180084418`
- `0x1800a3420`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800844f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800844f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800844a3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180084532`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008456f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800844a3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180084532`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008456f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800844b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008453c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800844b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008453c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800845aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800845aa`

## string_xrefs

- `0x1800844f0`: `winhttp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CJobManager::GetErrorDescription(CJobManager *this, DWORD a2, DWORD a3, unsigned __int16 **a4)
{
  DWORD v6; // ebx
  CJobManager *v7; // rsi
  int v8; // ecx
  HMODULE Library; // rax
  int result; // eax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-A8h] BYREF

  v6 = a2;
  v7 = g_Manager;
  *(_QWORD *)Buffer = 0;
  if ( a2 + 2147220992 <= 0x17 && (v8 = 16712703, _bittest(&v8, a2 + 2147220992)) || a2 + 2147220224 <= 1 )
    v6 = -2145386427;
  if ( FormatMessageW(0xB00u, g_hInstance, v6, a3, Buffer, 0, 0) )
    goto LABEL_17;
  if ( GetLastError() == 14 )
    return -2147024882;
  if ( (v6 & 0x1FFF0000) == 0x70000 && (unsigned int)(unsigned __int16)v6 - 12000 <= 0x3E7 )
  {
    Library = (HMODULE)*((_QWORD *)v7 + 85);
    if ( Library || (Library = LoadLibraryExW(L"winhttp.dll", 0, 2u), (*((_QWORD *)v7 + 85) = Library) != 0) )
    {
      if ( FormatMessageW(0xB00u, Library, (unsigned __int16)v6, a3, Buffer, 0, 0) )
      {
LABEL_17:
        *a4 = MidlCopyString(*(const unsigned __int16 **)Buffer, 0xFFFFFFFFFFFFFFFFuLL);
        LocalFree(*(HLOCAL *)Buffer);
        return *a4 == 0 ? 0x8007000E : 0;
      }
      if ( GetLastError() == 14 )
        return -2147024882;
    }
  }
  if ( FormatMessageW(0x1300u, 0, v6, a3, Buffer, 0, 0) )
    goto LABEL_17;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180084418  push    rbx
0x18008441a  push    rsi
0x18008441b  push    rdi
0x18008441c  push    r14
0x18008441e  push    r15
0x180084420  sub     rsp, 0C0h
0x180084427  mov     rax, cs:__security_cookie
0x18008442e  xor     rax, rsp
0x180084431  mov     [rsp+0E8h+var_38], rax
0x180084439  mov     r15, r9
0x18008443c  mov     r14d, r8d
0x18008443f  mov     ebx, edx
0x180084441  mov     rsi, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180084448  mov     qword ptr [rsp+0E8h+Buffer], 0
0x180084451  lea     eax, [rdx+7FFBFE00h]
0x180084457  cmp     eax, 17h
0x18008445a  ja      short loc_180084466
0x18008445c  mov     ecx, 0FF03FFh
0x180084461  bt      ecx, eax
0x180084464  jb      short loc_180084471
0x180084466  lea     eax, [rdx+7FFBFB00h]
0x18008446c  cmp     eax, 1
0x18008446f  ja      short loc_180084476
0x180084471  mov     ebx, 80200045h
0x180084476  mov     [rsp+0E8h+Arguments], 0; Arguments
0x18008447f  mov     [rsp+0E8h+nSize], 0; nSize
0x180084487  lea     rax, [rsp+0E8h+Buffer]
0x18008448c  mov     [rsp+0E8h+lpBuffer], rax; lpBuffer
0x180084491  mov     r9d, r14d; dwLanguageId
0x180084494  mov     r8d, ebx; dwMessageId
0x180084497  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18008449e  mov     ecx, 0B00h; dwFlags
0x1800844a3  call    cs:__imp_FormatMessageW
0x1800844a9  test    eax, eax
0x1800844ab  jnz     loc_180084594
0x1800844b1  call    cs:__imp_GetLastError
0x1800844b7  cmp     eax, 0Eh
0x1800844ba  jz      loc_18008458D
0x1800844c0  mov     eax, ebx
0x1800844c2  and     eax, 1FFF0000h
0x1800844c7  cmp     eax, 70000h
0x1800844cc  jnz     short loc_180084547
0x1800844ce  movzx   edi, bx
0x1800844d1  lea     eax, [rdi-2EE0h]
0x1800844d7  cmp     eax, 3E7h
0x1800844dc  ja      short loc_180084547
0x1800844de  mov     rax, [rsi+2A8h]
0x1800844e5  test    rax, rax
0x1800844e8  jnz     short loc_180084509
0x1800844ea  xor     edx, edx; hFile
0x1800844ec  lea     r8d, [rax+2]; dwFlags
0x1800844f0  lea     rcx, aWinhttpDll_0; "winhttp.dll"
0x1800844f7  call    cs:__imp_LoadLibraryExW
0x1800844fd  mov     [rsi+2A8h], rax
0x180084504  test    rax, rax
0x180084507  jz      short loc_180084547
0x180084509  mov     [rsp+0E8h+Arguments], 0; Arguments
0x180084512  mov     [rsp+0E8h+nSize], 0; nSize
0x18008451a  lea     rdx, [rsp+0E8h+Buffer]
0x18008451f  mov     [rsp+0E8h+lpBuffer], rdx; lpBuffer
0x180084524  mov     r9d, r14d; dwLanguageId
0x180084527  mov     r8d, edi; dwMessageId
0x18008452a  mov     rdx, rax; lpSource
0x18008452d  mov     ecx, 0B00h; dwFlags
0x180084532  call    cs:__imp_FormatMessageW
0x180084538  test    eax, eax
0x18008453a  jnz     short loc_180084594
0x18008453c  call    cs:__imp_GetLastError
0x180084542  cmp     eax, 0Eh
0x180084545  jz      short loc_18008458D
0x180084547  mov     [rsp+0E8h+Arguments], 0; Arguments
0x180084550  mov     [rsp+0E8h+nSize], 0; nSize
0x180084558  lea     rax, [rsp+0E8h+Buffer]
0x18008455d  mov     [rsp+0E8h+lpBuffer], rax; lpBuffer
0x180084562  mov     r9d, r14d; dwLanguageId
0x180084565  mov     r8d, ebx; dwMessageId
0x180084568  xor     edx, edx; lpSource
0x18008456a  mov     ecx, 1300h; dwFlags
0x18008456f  call    cs:__imp_FormatMessageW
0x180084575  test    eax, eax
0x180084577  jnz     short loc_180084594
0x180084579  call    cs:__imp_GetLastError
0x18008457f  test    eax, eax
0x180084581  jle     short loc_1800845C5
0x180084583  movzx   eax, ax
0x180084586  or      eax, 80070000h
0x18008458b  jmp     short loc_1800845C5
0x18008458d  mov     eax, 8007000Eh
0x180084592  jmp     short loc_1800845C5
0x180084594  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180084598  mov     rcx, qword ptr [rsp+0E8h+Buffer]; unsigned __int16 *
0x18008459d  call    ?MidlCopyString@@YAPEAGPEBG_K@Z; MidlCopyString(ushort const *,unsigned __int64)
0x1800845a2  mov     [r15], rax
0x1800845a5  mov     rcx, qword ptr [rsp+0E8h+Buffer]; hMem
0x1800845aa  call    cs:__imp_LocalFree
0x1800845b0  mov     rax, [r15]
0x1800845b3  neg     rax
0x1800845b6  sbb     eax, eax
0x1800845b8  not     eax
0x1800845ba  and     eax, 8007000Eh
0x1800845bf  jmp     short loc_1800845C5
0x1800845c1  mov     eax, [rsp+0E8h+var_A0]
0x1800845c5  mov     rcx, [rsp+0E8h+var_38]
0x1800845cd  xor     rcx, rsp; StackCookie
0x1800845d0  call    __security_check_cookie
0x1800845d5  add     rsp, 0C0h
0x1800845dc  pop     r15
0x1800845de  pop     r14
0x1800845e0  pop     rdi
0x1800845e1  pop     rsi
0x1800845e2  pop     rbx
0x1800845e3  retn
```
