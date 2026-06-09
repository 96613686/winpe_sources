# WERReport::Create(ushort const *,ushort const *)

- ea: `0x180026b60`
- end: `0x180026d0f`
- name: `?Create@WERReport@@UEAAJPEBG0@Z`
- size: `431`
- prototype: `__int64 __fastcall(HREPORT *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006fa0`
- `0x180026b60`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026bec`
- `KERNEL32!GetLastError` at `0x180026c2a`
- `KERNEL32!GetLastError` at `0x180026c82`
- `KERNEL32!GetLastError` at `0x180026bec`
- `KERNEL32!GetLastError` at `0x180026c2a`
- `KERNEL32!GetLastError` at `0x180026c82`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180026c78`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180026c78`
- `USER32!LoadStringW` at `0x180026be2`
- `USER32!LoadStringW` at `0x180026c20`
- `USER32!LoadStringW` at `0x180026be2`
- `USER32!LoadStringW` at `0x180026c20`
- `wer!WerReportCreate` at `0x180026ce7`
- `wer!WerReportCreate` at `0x180026ce7`

## string_xrefs

- `0x180026c71`: `%systemroot%\system32\netdiagfx.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WERReport::Create(HREPORT *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  signed int v7; // ebx
  _WER_REPORT_INFORMATION *p_pReportInformation; // rax
  __int64 v9; // rcx
  signed int LastError; // eax
  signed int v11; // eax
  __int64 v12; // rcx
  WCHAR *v13; // rax
  signed int v14; // eax
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+20h] [rbp-AE8h] BYREF
  WCHAR Dst[264]; // [rsp+8C0h] [rbp-248h] BYREF

  if ( !a2 )
    return 2147942487LL;
  memset_0(&pReportInformation, 0, sizeof(pReportInformation));
  v7 = 0;
  p_pReportInformation = &pReportInformation;
  v9 = 2208;
  do
  {
    LOBYTE(p_pReportInformation->dwSize) = 0;
    p_pReportInformation = (_WER_REPORT_INFORMATION *)((char *)p_pReportInformation + 1);
    --v9;
  }
  while ( v9 );
  pReportInformation.dwSize = 2208;
  if ( LoadStringW(hInstance, 0x6Eu, pReportInformation.wzFriendlyEventName, 128) )
    goto LABEL_12;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_12:
    if ( LoadStringW(hInstance, 0x6Fu, pReportInformation.wzApplicationName, 128) )
      goto LABEL_13;
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 >= 0 )
    {
LABEL_13:
      v12 = 520;
      v13 = Dst;
      do
      {
        *(_BYTE *)v13 = 0;
        v13 = (WCHAR *)((char *)v13 + 1);
        --v12;
      }
      while ( v12 );
      if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\netdiagfx.dll", Dst, 0x104u) )
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
      }
      if ( v7 >= 0 )
      {
        v7 = StringCchCopyW(pReportInformation.wzApplicationPath, 0x104u, Dst);
        if ( v7 >= 0 )
        {
          if ( !a3 )
            return (unsigned int)WerReportCreate(a2, WerReportNonCritical, &pReportInformation, this + 1);
          v7 = StringCchCopyW(pReportInformation.wzDescription, 0x200u, a3);
          if ( v7 >= 0 )
            return (unsigned int)WerReportCreate(a2, WerReportNonCritical, &pReportInformation, this + 1);
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026b60  push    rbx
0x180026b62  push    rbp
0x180026b63  push    rsi
0x180026b64  push    rdi
0x180026b65  push    r14
0x180026b67  sub     rsp, 0AE0h
0x180026b6e  mov     rax, cs:__security_cookie
0x180026b75  xor     rax, rsp
0x180026b78  mov     [rsp+0B08h+var_38], rax
0x180026b80  mov     rdi, r8
0x180026b83  mov     rsi, rdx
0x180026b86  mov     rbp, rcx
0x180026b89  test    rdx, rdx
0x180026b8c  jnz     short loc_180026B98
0x180026b8e  mov     eax, 80070057h
0x180026b93  jmp     loc_180026CF1
0x180026b98  mov     r14d, 8A0h
0x180026b9e  lea     rcx, [rsp+0B08h+pReportInformation]; void *
0x180026ba3  mov     r8d, r14d; Size
0x180026ba6  xor     edx, edx; Val
0x180026ba8  call    memset_0
0x180026bad  xor     ebx, ebx
0x180026baf  lea     rax, [rsp+0B08h+pReportInformation]
0x180026bb4  mov     ecx, r14d
0x180026bb7  mov     [rax], bl
0x180026bb9  inc     rax
0x180026bbc  sub     rcx, 1
0x180026bc0  jnz     short loc_180026BB7
0x180026bc2  mov     [rsp+0B08h+pReportInformation.dwSize], r14d
0x180026bc7  lea     edx, [rcx+6Eh]; uID
0x180026bca  mov     rcx, cs:hInstance; hInstance
0x180026bd1  lea     r8, [rsp+0B08h+pReportInformation.wzFriendlyEventName]; lpBuffer
0x180026bd9  mov     r14d, 80h
0x180026bdf  mov     r9d, r14d; cchBufferMax
0x180026be2  call    cs:__imp_LoadStringW
0x180026be8  test    eax, eax
0x180026bea  jnz     short loc_180026C09
0x180026bec  call    cs:__imp_GetLastError
0x180026bf2  mov     ebx, eax
0x180026bf4  test    eax, eax
0x180026bf6  jle     short loc_180026C01
0x180026bf8  movzx   ebx, ax
0x180026bfb  or      ebx, 80070000h
0x180026c01  test    ebx, ebx
0x180026c03  js      loc_180026CEF
0x180026c09  mov     rcx, cs:hInstance; hInstance
0x180026c10  lea     r8, [rsp+0B08h+pReportInformation.wzApplicationName]; lpBuffer
0x180026c18  mov     r9d, r14d; cchBufferMax
0x180026c1b  mov     edx, 6Fh ; 'o'; uID
0x180026c20  call    cs:__imp_LoadStringW
0x180026c26  test    eax, eax
0x180026c28  jnz     short loc_180026C47
0x180026c2a  call    cs:__imp_GetLastError
0x180026c30  mov     ebx, eax
0x180026c32  test    eax, eax
0x180026c34  jle     short loc_180026C3F
0x180026c36  movzx   ebx, ax
0x180026c39  or      ebx, 80070000h
0x180026c3f  test    ebx, ebx
0x180026c41  js      loc_180026CEF
0x180026c47  mov     ecx, 208h
0x180026c4c  lea     rax, [rsp+0B08h+Dst]
0x180026c54  mov     byte ptr [rax], 0
0x180026c57  inc     rax
0x180026c5a  sub     rcx, 1
0x180026c5e  jnz     short loc_180026C54
0x180026c60  mov     r14d, 104h
0x180026c66  lea     rdx, [rsp+0B08h+Dst]; lpDst
0x180026c6e  mov     r8d, r14d; nSize
0x180026c71  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\netdiagfx.dll"
0x180026c78  call    cs:__imp_ExpandEnvironmentStringsW
0x180026c7e  test    eax, eax
0x180026c80  jnz     short loc_180026C97
0x180026c82  call    cs:__imp_GetLastError
0x180026c88  mov     ebx, eax
0x180026c8a  test    eax, eax
0x180026c8c  jle     short loc_180026C97
0x180026c8e  movzx   ebx, ax
0x180026c91  or      ebx, 80070000h
0x180026c97  test    ebx, ebx
0x180026c99  js      short loc_180026CEF
0x180026c9b  lea     r8, [rsp+0B08h+Dst]; unsigned __int16 *
0x180026ca3  mov     rdx, r14; unsigned __int64
0x180026ca6  lea     rcx, [rsp+0B08h+pReportInformation.wzApplicationPath]; unsigned __int16 *
0x180026cae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026cb3  mov     ebx, eax
0x180026cb5  test    eax, eax
0x180026cb7  js      short loc_180026CEF
0x180026cb9  test    rdi, rdi
0x180026cbc  jz      short loc_180026CD9
0x180026cbe  mov     r8, rdi; unsigned __int16 *
0x180026cc1  lea     rcx, [rsp+0B08h+pReportInformation.wzDescription]; unsigned __int16 *
0x180026cc9  mov     edx, 200h; unsigned __int64
0x180026cce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026cd3  mov     ebx, eax
0x180026cd5  test    eax, eax
0x180026cd7  js      short loc_180026CEF
0x180026cd9  lea     r9, [rbp+8]; phReportHandle
0x180026cdd  xor     edx, edx; repType
0x180026cdf  lea     r8, [rsp+0B08h+pReportInformation]; pReportInformation
0x180026ce4  mov     rcx, rsi; pwzEventType
0x180026ce7  call    cs:__imp_WerReportCreate
0x180026ced  mov     ebx, eax
0x180026cef  mov     eax, ebx
0x180026cf1  mov     rcx, [rsp+0B08h+var_38]
0x180026cf9  xor     rcx, rsp; StackCookie
0x180026cfc  call    __security_check_cookie
0x180026d01  add     rsp, 0AE0h
0x180026d08  pop     r14
0x180026d0a  pop     rdi
0x180026d0b  pop     rsi
0x180026d0c  pop     rbp
0x180026d0d  pop     rbx
0x180026d0e  retn
```
