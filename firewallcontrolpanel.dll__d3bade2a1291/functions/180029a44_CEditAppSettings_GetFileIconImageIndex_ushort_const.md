# CEditAppSettings::GetFileIconImageIndex(ushort const *)

- ea: `0x180029a44`
- end: `0x180029b57`
- name: `?GetFileIconImageIndex@CEditAppSettings@@AEAAHPEBG@Z`
- size: `275`
- prototype: `int(CEditAppSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029c4c`

## callees

- `0x180029a44`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029a97`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029ad3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029a97`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180029ad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029aaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029aaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b33`
- `SHELL32!SHGetFileInfoW` at `0x180029b1a`
- `SHELL32!SHGetFileInfoW` at `0x180029b1a`

## pseudocode

```c
__int64 __fastcall CEditAppSettings::GetFileIconImageIndex(CEditAppSettings *this, WCHAR *p_Dst)
{
  WCHAR *v3; // rbx
  DWORD v4; // eax
  DWORD v5; // ebp
  SIZE_T v6; // rsi
  WCHAR *v7; // rax
  DWORD_PTR v8; // rax
  unsigned int iIcon; // edi
  SHFILEINFOW psfi; // [rsp+30h] [rbp-508h] BYREF
  WCHAR Dst; // [rsp+2F0h] [rbp-248h] BYREF
  _BYTE v13[526]; // [rsp+2F2h] [rbp-246h] BYREF

  Dst = 0;
  memset_0(v13, 0, 0x206u);
  v3 = 0;
  v4 = ExpandEnvironmentStringsW(p_Dst, &Dst, 0x104u);
  if ( v4 < 0x104 )
    goto LABEL_5;
  v5 = v4 + 1;
  v6 = 2LL * (v4 + 1);
  v7 = (WCHAR *)CoTaskMemAlloc(v6);
  v3 = v7;
  if ( !v7 )
    goto LABEL_7;
  memset_0(v7, 0, v6);
  v4 = ExpandEnvironmentStringsW(p_Dst, v3, v5);
  if ( v4 < 0x104 )
  {
LABEL_5:
    if ( v4 )
      p_Dst = &Dst;
  }
  else
  {
    p_Dst = v3;
  }
LABEL_7:
  memset_0(&psfi, 0, sizeof(psfi));
  v8 = SHGetFileInfoW(p_Dst, 0, &psfi, 0x2B8u, 0x4001u);
  iIcon = -1;
  if ( v8 )
    iIcon = psfi.iIcon;
  if ( v3 )
    CoTaskMemFree(v3);
  return iIcon;
}

```

## disassembly

```asm
0x180029a44  push    rbx
0x180029a46  push    rbp
0x180029a47  push    rsi
0x180029a48  push    rdi
0x180029a49  sub     rsp, 518h
0x180029a50  mov     rax, cs:__security_cookie
0x180029a57  xor     rax, rsp
0x180029a5a  mov     [rsp+538h+var_38], rax
0x180029a62  mov     rdi, rdx
0x180029a65  lea     rcx, [rsp+538h+var_246]; void *
0x180029a6d  xor     eax, eax
0x180029a6f  xor     edx, edx; Val
0x180029a71  mov     r8d, 206h; Size
0x180029a77  mov     [rsp+538h+Dst], ax
0x180029a7f  call    memset_0
0x180029a84  mov     r8d, 104h; nSize
0x180029a8a  lea     rdx, [rsp+538h+Dst]; lpDst
0x180029a92  mov     rcx, rdi; lpSrc
0x180029a95  xor     ebx, ebx
0x180029a97  call    cs:__imp_ExpandEnvironmentStringsW
0x180029a9d  cmp     eax, 104h
0x180029aa2  jb      short loc_180029AE5
0x180029aa4  lea     ebp, [rax+1]
0x180029aa7  mov     esi, ebp
0x180029aa9  add     rsi, rsi
0x180029aac  mov     rcx, rsi; cb
0x180029aaf  call    cs:__imp_CoTaskMemAlloc
0x180029ab5  mov     rbx, rax
0x180029ab8  test    rax, rax
0x180029abb  jz      short loc_180029AF1
0x180029abd  mov     r8, rsi; Size
0x180029ac0  xor     edx, edx; Val
0x180029ac2  mov     rcx, rax; void *
0x180029ac5  call    memset_0
0x180029aca  mov     r8d, ebp; nSize
0x180029acd  mov     rdx, rbx; lpDst
0x180029ad0  mov     rcx, rdi; lpSrc
0x180029ad3  call    cs:__imp_ExpandEnvironmentStringsW
0x180029ad9  cmp     eax, 104h
0x180029ade  jb      short loc_180029AE5
0x180029ae0  mov     rdi, rbx
0x180029ae3  jmp     short loc_180029AF1
0x180029ae5  test    eax, eax
0x180029ae7  jz      short loc_180029AF1
0x180029ae9  lea     rdi, [rsp+538h+Dst]
0x180029af1  mov     esi, 2B8h
0x180029af6  lea     rcx, [rsp+538h+psfi]; void *
0x180029afb  mov     r8d, esi; Size
0x180029afe  xor     edx, edx; Val
0x180029b00  call    memset_0
0x180029b05  mov     r9d, esi; cbFileInfo
0x180029b08  mov     [rsp+538h+uFlags], 4001h; uFlags
0x180029b10  lea     r8, [rsp+538h+psfi]; psfi
0x180029b15  xor     edx, edx; dwFileAttributes
0x180029b17  mov     rcx, rdi; pszPath
0x180029b1a  call    cs:__imp_SHGetFileInfoW
0x180029b20  or      edi, 0FFFFFFFFh
0x180029b23  test    rax, rax
0x180029b26  cmovnz  edi, [rsp+538h+psfi.iIcon]
0x180029b2b  test    rbx, rbx
0x180029b2e  jz      short loc_180029B39
0x180029b30  mov     rcx, rbx; pv
0x180029b33  call    cs:__imp_CoTaskMemFree
0x180029b39  mov     eax, edi
0x180029b3b  mov     rcx, [rsp+538h+var_38]
0x180029b43  xor     rcx, rsp; StackCookie
0x180029b46  call    __security_check_cookie
0x180029b4b  add     rsp, 518h
0x180029b52  pop     rdi
0x180029b53  pop     rsi
0x180029b54  pop     rbp
0x180029b55  pop     rbx
0x180029b56  retn
```
