# Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)

- ea: `0x180402690`
- end: `0x180402902`
- name: `?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z`
- size: `626`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1803fd800`
- `0x18040c890`

## callees

- `0x1800f2ba8`
- `0x180400dd4`
- `0x180401098`
- `0x180401fe4`
- `0x180402690`
- `0x180402908`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18040281a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18040283b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18040281a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18040283b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804028af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804028bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804028af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804028bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180402898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180402898`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18040279f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18040279f`

## string_xrefs

- `0x180402834`: `mscordaccore.dll`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::VerifyModuleIsTrusted(
        __int64 (__fastcall **this)(const unsigned __int16 *, signed int *),
        const unsigned __int16 *a2,
        void **a3)
{
  __int64 result; // rax
  signed int v7; // ebx
  __int64 (__fastcall *v8)(const unsigned __int16 *, signed int *); // rax
  unsigned int v9; // eax
  unsigned int v10; // r14d
  signed int LastError; // eax
  __int64 v12; // r15
  HANDLE FileW; // rsi
  wchar_t *v14; // rax
  Win32LiveSystemProvider *v15; // rcx
  signed int v16; // eax
  int v17; // [rsp+40h] [rbp-38h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-30h] BYREF
  signed int v19; // [rsp+98h] [rbp+20h] BYREF

  result = Win32LiveSystemProvider::LoadVersion((Win32LiveSystemProvider *)this);
  v7 = result;
  if ( !(_DWORD)result )
  {
    v8 = this[68];
    if ( v8 && this[70] && this[71] )
    {
      v19 = v7;
      v9 = v8(a2, &v19);
      v10 = v9;
      if ( !v9 )
        goto LABEL_6;
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)this[6] + 8LL))(this[6], v9);
      if ( !v12 )
        return 2147942414LL;
      String2 = 0;
      v17 = 0;
      FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
LABEL_6:
        if ( GetLastError() )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          return (unsigned int)-2147467259;
        }
        return (unsigned int)v7;
      }
      if ( ((unsigned int (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD, __int64))this[70])(a2, 0, v10, v12)
        && ((unsigned int (__fastcall *)(__int64, const wchar_t *, wchar_t **, int *))this[72])(
             v12,
             L"\\StringFileInfo\\040904b0\\OriginalFilename",
             &String2,
             &v17) )
      {
        v14 = wcsrchr(a2, 0x5Cu);
        if ( !String2 || !_wcsicmp(v14 + 1, String2) || !String2 || !_wcsicmp(L"mscordaccore.dll", String2) )
        {
LABEL_21:
          (*(void (__fastcall **)(__int64 (__fastcall *)(const unsigned __int16 *, signed int *), __int64))(*(_QWORD *)this[6] + 24LL))(
            this[6],
            v12);
          if ( v7 < 0 )
            goto LABEL_26;
          if ( (unsigned int)Win32LiveSystemProvider::ShouldVerifySignature(v15) )
          {
            v7 = Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature((Win32LiveSystemProvider *)this, a2);
            if ( v7 == -2147467263 )
              v7 = Win32LiveSystemProvider::NtVerifyMicrosoftSignature((Win32LiveSystemProvider *)this, FileW);
            if ( v7 < 0 )
            {
LABEL_26:
              CloseHandle(FileW);
              FileW = 0;
            }
          }
          *a3 = FileW;
          return (unsigned int)v7;
        }
      }
      else if ( GetLastError() )
      {
        v16 = GetLastError();
        v7 = v16;
        if ( v16 > 0 )
          v7 = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_21;
      }
      v7 = -2147467259;
      goto LABEL_21;
    }
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180402690  mov     [rsp+arg_0], rbx
0x180402695  mov     [rsp+arg_8], rbp
0x18040269a  push    rsi
0x18040269b  push    rdi
0x18040269c  push    r12
0x18040269e  push    r14
0x1804026a0  push    r15
0x1804026a2  sub     rsp, 50h
0x1804026a6  mov     r12, r8
0x1804026a9  mov     rbp, rdx
0x1804026ac  mov     rdi, rcx
0x1804026af  call    ?LoadVersion@Win32LiveSystemProvider@@IEAAJXZ; Win32LiveSystemProvider::LoadVersion(void)
0x1804026b4  mov     ebx, eax
0x1804026b6  test    eax, eax
0x1804026b8  jnz     loc_1804028E8
0x1804026be  mov     rax, [rdi+220h]
0x1804026c5  test    rax, rax
0x1804026c8  jz      loc_1804028E3
0x1804026ce  cmp     qword ptr [rdi+230h], 0
0x1804026d6  jz      loc_1804028E3
0x1804026dc  cmp     qword ptr [rdi+238h], 0
0x1804026e4  jz      loc_1804028E3
0x1804026ea  lea     rdx, [rsp+78h+arg_18]
0x1804026f2  mov     [rsp+78h+arg_18], ebx
0x1804026f9  mov     rcx, rbp
0x1804026fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402701  mov     r14d, eax
0x180402704  test    eax, eax
0x180402706  jnz     short loc_180402741
0x180402708  call    cs:__imp_GetLastError
0x18040270f  nop     dword ptr [rax+rax+00h]
0x180402714  test    eax, eax
0x180402716  jz      short loc_180402735
0x180402718  call    cs:__imp_GetLastError
0x18040271f  nop     dword ptr [rax+rax+00h]
0x180402724  mov     ebx, eax
0x180402726  test    eax, eax
0x180402728  jle     short loc_18040273A
0x18040272a  movzx   ebx, ax
0x18040272d  or      ebx, 80070000h
0x180402733  jmp     short loc_18040273A
0x180402735  mov     ebx, 80004005h
0x18040273a  mov     eax, ebx
0x18040273c  jmp     loc_1804028E8
0x180402741  mov     rcx, [rdi+30h]
0x180402745  mov     edx, r14d
0x180402748  mov     rax, [rcx]
0x18040274b  mov     rax, [rax+8]
0x18040274f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402754  mov     r15, rax
0x180402757  test    rax, rax
0x18040275a  jnz     short loc_180402766
0x18040275c  mov     eax, 8007000Eh
0x180402761  jmp     loc_1804028E8
0x180402766  xor     r9d, r9d; lpSecurityAttributes
0x180402769  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180402772  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18040277a  mov     edx, 80000000h; dwDesiredAccess
0x18040277f  mov     rcx, rbp; lpFileName
0x180402782  mov     [rsp+78h+String2], 0
0x18040278b  mov     [rsp+78h+var_38], 0
0x180402793  lea     r8d, [r9+1]; dwShareMode
0x180402797  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18040279f  call    cs:__imp_CreateFileW
0x1804027a6  nop     dword ptr [rax+rax+00h]
0x1804027ab  mov     rsi, rax
0x1804027ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804027b2  jz      loc_180402708
0x1804027b8  mov     rax, [rdi+230h]
0x1804027bf  mov     r9, r15
0x1804027c2  mov     r8d, r14d
0x1804027c5  xor     edx, edx
0x1804027c7  mov     rcx, rbp
0x1804027ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804027cf  test    eax, eax
0x1804027d1  jz      loc_1804028AF
0x1804027d7  mov     rax, [rdi+240h]
0x1804027de  lea     r9, [rsp+78h+var_38]
0x1804027e3  lea     r8, [rsp+78h+String2]
0x1804027e8  mov     rcx, r15
0x1804027eb  lea     rdx, aStringfileinfo; "\\StringFileInfo\\040904b0\\OriginalFil"...
0x1804027f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804027f7  test    eax, eax
0x1804027f9  jz      loc_1804028AF
0x1804027ff  mov     edx, 5Ch ; '\'; Ch
0x180402804  mov     rcx, rbp; Str
0x180402807  call    wcsrchr
0x18040280c  mov     rdx, [rsp+78h+String2]; String2
0x180402811  test    rdx, rdx
0x180402814  jz      short loc_180402850
0x180402816  lea     rcx, [rax+2]; String1
0x18040281a  call    cs:__imp__wcsicmp
0x180402821  nop     dword ptr [rax+rax+00h]
0x180402826  test    eax, eax
0x180402828  jz      short loc_180402850
0x18040282a  mov     rdx, [rsp+78h+String2]; String2
0x18040282f  test    rdx, rdx
0x180402832  jz      short loc_180402850
0x180402834  lea     rcx, aMscordaccoreDl; "mscordaccore.dll"
0x18040283b  call    cs:__imp__wcsicmp
0x180402842  nop     dword ptr [rax+rax+00h]
0x180402847  test    eax, eax
0x180402849  jz      short loc_180402850
0x18040284b  mov     ebx, 80004005h
0x180402850  mov     rcx, [rdi+30h]
0x180402854  mov     rdx, r15
0x180402857  mov     rax, [rcx]
0x18040285a  mov     rax, [rax+18h]
0x18040285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402863  test    ebx, ebx
0x180402865  js      short loc_180402895
0x180402867  call    ?ShouldVerifySignature@Win32LiveSystemProvider@@AEAAHXZ; Win32LiveSystemProvider::ShouldVerifySignature(void)
0x18040286c  test    eax, eax
0x18040286e  jz      short loc_1804028A6
0x180402870  mov     rdx, rbp; unsigned __int16 *
0x180402873  mov     rcx, rdi; this
0x180402876  call    ?WintrustVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEBG@Z; Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature(ushort const *)
0x18040287b  mov     ebx, eax
0x18040287d  cmp     eax, 80004001h
0x180402882  jnz     short loc_180402891
0x180402884  mov     rdx, rsi; void *
0x180402887  mov     rcx, rdi; this
0x18040288a  call    ?NtVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEAX@Z; Win32LiveSystemProvider::NtVerifyMicrosoftSignature(void *)
0x18040288f  mov     ebx, eax
0x180402891  test    ebx, ebx
0x180402893  jns     short loc_1804028A6
0x180402895  mov     rcx, rsi; hObject
0x180402898  call    cs:__imp_CloseHandle
0x18040289f  nop     dword ptr [rax+rax+00h]
0x1804028a4  xor     esi, esi
0x1804028a6  mov     [r12], rsi
0x1804028aa  jmp     loc_18040273A
0x1804028af  call    cs:__imp_GetLastError
0x1804028b6  nop     dword ptr [rax+rax+00h]
0x1804028bb  test    eax, eax
0x1804028bd  jz      short loc_18040284B
0x1804028bf  call    cs:__imp_GetLastError
0x1804028c6  nop     dword ptr [rax+rax+00h]
0x1804028cb  mov     ebx, eax
0x1804028cd  test    eax, eax
0x1804028cf  jle     loc_180402850
0x1804028d5  movzx   ebx, ax
0x1804028d8  or      ebx, 80070000h
0x1804028de  jmp     loc_180402850
0x1804028e3  mov     eax, 80004001h
0x1804028e8  lea     r11, [rsp+78h+var_28]
0x1804028ed  mov     rbx, [r11+30h]
0x1804028f1  mov     rbp, [r11+38h]
0x1804028f5  mov     rsp, r11
0x1804028f8  pop     r15
0x1804028fa  pop     r14
0x1804028fc  pop     r12
0x1804028fe  pop     rdi
0x1804028ff  pop     rsi
0x180402900  retn
```
