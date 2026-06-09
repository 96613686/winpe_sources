# CFveApi::GetDefaultDescription(_FVE_DATUM_UNICODE * *)

- ea: `0x18001f324`
- end: `0x18001f5cf`
- name: `?GetDefaultDescription@CFveApi@@QEAAJPEAPEAU_FVE_DATUM_UNICODE@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, struct _FVE_DATUM_UNICODE **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f044`
- `0x1800ca618`

## callees

- `0x180005410`
- `0x180018b10`
- `0x18001f324`
- `0x18004e554`
- `0x1800600c0`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f57d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180120259`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001f57d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180120259`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f53a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001f53a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f42e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f42e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001f4ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001f4ad`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001f47e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001f47e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f498`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001f498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012026f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012026f`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18001f4d7`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x18001f4d7`

## pseudocode

```c
__int64 __fastcall CFveApi::GetDefaultDescription(CFveApi *this, struct _FVE_DATUM_UNICODE **a2)
{
  WCHAR *v4; // rdi
  WCHAR *v5; // rax
  int LastHresultError; // ebx
  WCHAR *lpDateStr; // r15
  va_list v8; // r12
  const void *v9; // r13
  DWORD v10; // eax
  FILETIME *v11; // rcx
  int v12; // eax
  WCHAR Buffer[4]; // [rsp+48h] [rbp-80h] BYREF
  DWORD nSize; // [rsp+50h] [rbp-78h] BYREF
  FILETIME FileTime; // [rsp+58h] [rbp-70h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+60h] [rbp-68h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-60h] BYREF
  va_list Arguments[4]; // [rsp+78h] [rbp-50h] BYREF

  SystemTime = 0;
  FileTime = 0;
  LocalFileTime = 0;
  nSize = 0;
  v4 = 0;
  *(_QWORD *)Buffer = 0;
  *a2 = 0;
  if ( *((_BYTE *)this + 1156) && *((_QWORD *)this + 146) )
  {
    v5 = (WCHAR *)operator new[](0x820u, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v5;
    if ( !v5 )
    {
      LastHresultError = -2147024882;
      goto LABEL_20;
    }
    lpDateStr = v5 + 130;
    v8 = (va_list)(v5 + 260);
    v9 = v5 + 390;
    v10 = (*(__int64 (__fastcall **)(CFveApi *, __int64, __int64, WCHAR *))(*(_QWORD *)this + 304LL))(
            this,
            1001,
            260,
            v5 + 390);
    nSize = v10;
    if ( v10 > 0x104 )
    {
      LastHresultError = -2147467259;
      goto LABEL_20;
    }
    if ( !v10 )
      goto LABEL_8;
    nSize = 260;
    if ( !GetComputerNameExW(ComputerNameNetBIOS, v4, &nSize) )
      goto LABEL_8;
    LastHresultError = (*(__int64 (__fastcall **)(CFveApi *, va_list, __int64))(*(_QWORD *)this + 120LL))(this, v8, 260);
    if ( LastHresultError < 0 )
      goto LABEL_20;
    v11 = (FILETIME *)*((_QWORD *)this + 146);
    FileTime = v11[5];
    if ( !*(_QWORD *)&v11[5]
      || !FileTimeToLocalFileTime(&FileTime, &LocalFileTime)
      || !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
    {
      GetLocalTime(&SystemTime);
    }
    nSize = GetDateFormatW(0x400u, 1u, &SystemTime, 0, lpDateStr, 260);
    if ( !nSize
      || (Arguments[0] = (va_list)v4,
          Arguments[1] = v8,
          Arguments[2] = (va_list)lpDateStr,
          Arguments[3] = 0,
          (nSize = FormatMessageW(0x2500u, v9, 0, 0, Buffer, 0, Arguments)) == 0) )
    {
LABEL_8:
      LastHresultError = GetLastHresultError();
      goto LABEL_20;
    }
    v12 = FveDatumUnicodeCreate(*(_QWORD *)Buffer, a2);
    LastHresultError = FromNtStatus(v12);
    if ( LastHresultError >= 0 )
      LastHresultError = 0;
  }
  else
  {
    LastHresultError = -2147024786;
  }
LABEL_20:
  if ( v4 )
    operator delete[](v4);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18001f324  mov     r11, rsp
0x18001f327  mov     [r11+18h], rbx
0x18001f32b  mov     [r11+20h], rsi
0x18001f32f  push    rdi
0x18001f330  push    r12
0x18001f332  push    r13
0x18001f334  push    r14
0x18001f336  push    r15
0x18001f338  sub     rsp, 0A0h
0x18001f33f  mov     rax, cs:__security_cookie
0x18001f346  xor     rax, rsp
0x18001f349  mov     [rsp+0C8h+var_30], rax
0x18001f351  mov     r14, rdx
0x18001f354  mov     rsi, rcx
0x18001f357  xorps   xmm0, xmm0
0x18001f35a  movups  xmmword ptr [rsp+0C8h+SystemTime.wYear], xmm0
0x18001f35f  mov     qword ptr [r11-70h], 0
0x18001f367  mov     qword ptr [r11-68h], 0
0x18001f36f  mov     [rsp+0C8h+nSize], 0
0x18001f377  xor     edi, edi
0x18001f379  mov     [rsp+0C8h+var_88], rdi
0x18001f37e  mov     [r11-80h], rdi
0x18001f382  mov     [rdx], rdi
0x18001f385  cmp     [rcx+484h], dil
0x18001f38c  jz      loc_18001F570
0x18001f392  cmp     [rcx+490h], rdi
0x18001f399  jz      loc_18001F570
0x18001f39f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f3a6  mov     ecx, 820h; unsigned __int64
0x18001f3ab  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f3b0  mov     rdi, rax
0x18001f3b3  mov     [rsp+0C8h+var_88], rax
0x18001f3b8  test    rax, rax
0x18001f3bb  jnz     short loc_18001F3C7
0x18001f3bd  mov     ebx, 8007000Eh
0x18001f3c2  jmp     loc_18001F575
0x18001f3c7  lea     r15, [rax+104h]
0x18001f3ce  lea     r12, [rax+208h]
0x18001f3d5  lea     r13, [rax+30Ch]
0x18001f3dc  mov     rax, [rsi]
0x18001f3df  mov     r9, r13
0x18001f3e2  mov     ebx, 104h
0x18001f3e7  mov     r8d, ebx
0x18001f3ea  mov     edx, 3E9h
0x18001f3ef  mov     rcx, rsi
0x18001f3f2  mov     rax, [rax+130h]
0x18001f3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3fe  mov     [rsp+0C8h+nSize], eax
0x18001f402  cmp     eax, ebx
0x18001f404  jbe     short loc_18001F410
0x18001f406  mov     ebx, 80004005h
0x18001f40b  jmp     loc_18001F575
0x18001f410  test    eax, eax
0x18001f412  jnz     short loc_18001F420
0x18001f414  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18001f419  mov     ebx, eax
0x18001f41b  jmp     loc_18001F575
0x18001f420  mov     [rsp+0C8h+nSize], ebx
0x18001f424  lea     r8, [rsp+0C8h+nSize]; nSize
0x18001f429  mov     rdx, rdi; lpBuffer
0x18001f42c  xor     ecx, ecx; NameType
0x18001f42e  call    cs:__imp_GetComputerNameExW
0x18001f435  nop     dword ptr [rax+rax+00h]
0x18001f43a  test    eax, eax
0x18001f43c  jz      short loc_18001F414
0x18001f43e  mov     rax, [rsi]
0x18001f441  mov     r8, rbx
0x18001f444  mov     rdx, r12
0x18001f447  mov     rcx, rsi
0x18001f44a  mov     rax, [rax+78h]
0x18001f44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f453  mov     ebx, eax
0x18001f455  test    eax, eax
0x18001f457  js      loc_18001F575
0x18001f45d  mov     rcx, [rsi+490h]
0x18001f464  mov     rax, [rcx+28h]
0x18001f468  mov     qword ptr [rsp+0C8h+FileTime.dwLowDateTime], rax
0x18001f46d  cmp     qword ptr [rcx+28h], 0
0x18001f472  jz      short loc_18001F4A8
0x18001f474  lea     rdx, [rsp+0C8h+LocalFileTime]; lpLocalFileTime
0x18001f479  lea     rcx, [rsp+0C8h+FileTime]; lpFileTime
0x18001f47e  call    cs:__imp_FileTimeToLocalFileTime
0x18001f485  nop     dword ptr [rax+rax+00h]
0x18001f48a  test    eax, eax
0x18001f48c  jz      short loc_18001F4A8
0x18001f48e  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x18001f493  lea     rcx, [rsp+0C8h+LocalFileTime]; lpFileTime
0x18001f498  call    cs:__imp_FileTimeToSystemTime
0x18001f49f  nop     dword ptr [rax+rax+00h]
0x18001f4a4  test    eax, eax
0x18001f4a6  jnz     short loc_18001F4B9
0x18001f4a8  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x18001f4ad  call    cs:__imp_GetLocalTime
0x18001f4b4  nop     dword ptr [rax+rax+00h]
0x18001f4b9  mov     [rsp+0C8h+cchDate], 104h; cchDate
0x18001f4c1  mov     [rsp+0C8h+lpDateStr], r15; lpDateStr
0x18001f4c6  xor     r9d, r9d; lpFormat
0x18001f4c9  lea     r8, [rsp+0C8h+SystemTime]; lpDate
0x18001f4ce  lea     edx, [r9+1]; dwFlags
0x18001f4d2  mov     ecx, 400h; Locale
0x18001f4d7  call    cs:__imp_GetDateFormatW
0x18001f4de  nop     dword ptr [rax+rax+00h]
0x18001f4e3  mov     [rsp+0C8h+nSize], eax
0x18001f4e7  test    eax, eax
0x18001f4e9  jz      loc_18001F414
0x18001f4ef  mov     [rsp+0C8h+var_50], rdi
0x18001f4f4  mov     [rsp+0C8h+var_48], r12
0x18001f4fc  mov     [rsp+0C8h+var_40], r15
0x18001f504  mov     [rsp+0C8h+var_38], 0
0x18001f510  lea     rax, [rsp+0C8h+var_50]
0x18001f515  mov     [rsp+0C8h+Arguments], rax; Arguments
0x18001f51a  mov     [rsp+0C8h+cchDate], 0; nSize
0x18001f522  lea     rax, [rsp+0C8h+Buffer]
0x18001f527  mov     [rsp+0C8h+lpDateStr], rax; lpBuffer
0x18001f52c  xor     r9d, r9d; dwLanguageId
0x18001f52f  xor     r8d, r8d; dwMessageId
0x18001f532  mov     rdx, r13; lpSource
0x18001f535  mov     ecx, 2500h; dwFlags
0x18001f53a  call    cs:__imp_FormatMessageW
0x18001f541  nop     dword ptr [rax+rax+00h]
0x18001f546  mov     [rsp+0C8h+nSize], eax
0x18001f54a  test    eax, eax
0x18001f54c  jz      loc_18001F414
0x18001f552  mov     rdx, r14
0x18001f555  mov     rcx, qword ptr [rsp+0C8h+Buffer]
0x18001f55a  call    FveDatumUnicodeCreate
0x18001f55f  mov     ecx, eax; int
0x18001f561  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001f566  mov     ebx, eax
0x18001f568  test    eax, eax
0x18001f56a  js      short loc_18001F575
0x18001f56c  xor     ebx, ebx
0x18001f56e  jmp     short loc_18001F575
0x18001f570  mov     ebx, 8007006Eh
0x18001f575  test    rdi, rdi
0x18001f578  jz      short loc_18001F589
0x18001f57a  mov     rcx, rdi
0x18001f57d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001f584  nop     dword ptr [rax+rax+00h]
0x18001f589  mov     rcx, qword ptr [rsp+0C8h+Buffer]; hMem
0x18001f58e  test    rcx, rcx
0x18001f591  jz      short loc_18001F59F
0x18001f593  call    cs:__imp_LocalFree
0x18001f59a  nop     dword ptr [rax+rax+00h]
0x18001f59f  mov     eax, ebx
0x18001f5a1  mov     rcx, [rsp+0C8h+var_30]
0x18001f5a9  xor     rcx, rsp; StackCookie
0x18001f5ac  call    __security_check_cookie
0x18001f5b1  lea     r11, [rsp+0C8h+var_28]
0x18001f5b9  mov     rbx, [r11+40h]
0x18001f5bd  mov     rsi, [r11+48h]
0x18001f5c1  mov     rsp, r11
0x18001f5c4  pop     r15
0x18001f5c6  pop     r14
0x18001f5c8  pop     r13
0x18001f5ca  pop     r12
0x18001f5cc  pop     rdi
0x18001f5cd  retn
0x180120247  push    rbp
0x180120249  sub     rsp, 40h
0x18012024d  mov     rbp, rdx
0x180120250  mov     rcx, [rbp+40h]
0x180120254  test    rcx, rcx
0x180120257  jz      short loc_180120266
0x180120259  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180120260  nop     dword ptr [rax+rax+00h]
0x180120265  nop
0x180120266  mov     rcx, [rbp+48h]; hMem
0x18012026a  test    rcx, rcx
0x18012026d  jz      short loc_18012027C
0x18012026f  call    cs:__imp_LocalFree
0x180120276  nop     dword ptr [rax+rax+00h]
0x18012027b  nop
0x18012027c  add     rsp, 40h
0x180120280  pop     rbp
0x180120281  retn
```
