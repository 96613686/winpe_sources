# SetClassIdForLocation

- ea: `0x180016adc`
- end: `0x180016cc1`
- name: `SetClassIdForLocation`
- size: `485`
- prototype: `__int64 __fastcall(void *Src, void *, int, const BYTE *, DWORD cbData, DWORD dwType)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002ad18`

## callees

- `0x18000890c`
- `0x18000c740`
- `0x180016adc`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033c4c`
- `0x180034680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016b7e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016b7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016bd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180016c1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180016c1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c7b`

## pseudocode

```c
__int64 __fastcall SetClassIdForLocation(void *Src, void *a2, int a3, const BYTE *a4, DWORD cbData, DWORD dwType)
{
  unsigned int v9; // ebx
  wchar_t *v10; // rdi
  wchar_t *v11; // rsi
  int v12; // ecx
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-40h] BYREF

  Str = 0;
  hKey = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Sqd((_DWORD)Src, 33, (unsigned int)WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, a3, (char)a4, cbData);
  if ( ((dwType - 1) & 0xFFFFFFFD) != 0 )
  {
    v9 = 87;
  }
  else
  {
    v9 = ExpandRegLocationFromValue(Src, a2);
    if ( !v9 )
    {
      v10 = Str;
      v11 = wcsrchr(Str, 0x5Cu);
      if ( v11 )
      {
        *v11 = 0;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_S(1028, 34, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v10);
        v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0xFu, &hKey);
        if ( !v9 )
        {
          if ( a4 )
          {
            if ( (xmmword_1800423E0 & 0x10) != 0 )
              WPP_SF_SS(
                v12,
                36,
                (unsigned int)WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids,
                (_DWORD)v10,
                (__int64)(v11 + 1));
            v9 = RegSetValueExW(hKey, v11 + 1, 0, dwType, a4, cbData);
          }
          else
          {
            if ( (xmmword_1800423E0 & 0x10) != 0 )
              WPP_SF_SS(
                v12,
                35,
                (unsigned int)WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids,
                (_DWORD)v10,
                (__int64)(v11 + 1));
            v9 = RegDeleteValueW(hKey, v11 + 1);
            if ( v9 == 2 )
              v9 = 0;
          }
        }
      }
      else
      {
        v9 = 13;
      }
    }
  }
  RegCloseKey(hKey);
  DhcpFree((LPVOID *)&Str);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 37, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180016adc  mov     rax, rsp
0x180016adf  push    rbx
0x180016ae0  push    rbp
0x180016ae1  push    rsi
0x180016ae2  push    rdi
0x180016ae3  push    r13
0x180016ae5  push    r14
0x180016ae7  push    r15
0x180016ae9  sub     rsp, 40h
0x180016aed  mov     rbp, r9
0x180016af0  mov     qword ptr [rax-40h], 0
0x180016af8  mov     rbx, r8
0x180016afb  mov     qword ptr [rax-48h], 0
0x180016b03  mov     rdi, rdx
0x180016b06  mov     rsi, rcx
0x180016b09  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016b10  lea     r13, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180016b17  mov     r15d, [rsp+78h+arg_20]
0x180016b1f  jz      short loc_180016B39
0x180016b21  mov     [rax-50h], r15d
0x180016b25  mov     edx, 21h ; '!'
0x180016b2a  mov     [rax-58h], r9
0x180016b2e  mov     r8, r13
0x180016b31  mov     r9, rbx
0x180016b34  call    WPP_SF_Sqd
0x180016b39  mov     r14d, [rsp+78h+dwType]
0x180016b41  lea     eax, [r14-1]
0x180016b45  test    eax, 0FFFFFFFDh
0x180016b4a  jz      short loc_180016B56
0x180016b4c  mov     ebx, 57h ; 'W'
0x180016b51  jmp     loc_180016C76
0x180016b56  lea     r9, [rsp+78h+Str]
0x180016b5b  mov     r8, rbx
0x180016b5e  mov     rdx, rdi; void *
0x180016b61  mov     rcx, rsi; Src
0x180016b64  call    ExpandRegLocationFromValue
0x180016b69  mov     ebx, eax
0x180016b6b  test    eax, eax
0x180016b6d  jnz     loc_180016C76
0x180016b73  mov     rdi, [rsp+78h+Str]
0x180016b78  lea     edx, [rax+5Ch]; Ch
0x180016b7b  mov     rcx, rdi; Str
0x180016b7e  call    cs:__imp_wcsrchr
0x180016b85  nop     dword ptr [rax+rax+00h]
0x180016b8a  mov     rsi, rax
0x180016b8d  test    rax, rax
0x180016b90  jnz     short loc_180016B9A
0x180016b92  lea     ebx, [rax+0Dh]
0x180016b95  jmp     loc_180016C76
0x180016b9a  xor     eax, eax
0x180016b9c  mov     [rsi], ax
0x180016b9f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016ba6  jz      short loc_180016BBB
0x180016ba8  lea     edx, [rax+22h]
0x180016bab  mov     ecx, 404h
0x180016bb0  mov     r9, rdi
0x180016bb3  mov     r8, r13
0x180016bb6  call    WPP_SF_S
0x180016bbb  lea     rax, [rsp+78h+hKey]
0x180016bc0  mov     r9d, 0Fh; samDesired
0x180016bc6  xor     r8d, r8d; ulOptions
0x180016bc9  mov     [rsp+78h+phkResult], rax; phkResult
0x180016bce  mov     rdx, rdi; lpSubKey
0x180016bd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016bd8  call    cs:__imp_RegOpenKeyExW
0x180016bdf  nop     dword ptr [rax+rax+00h]
0x180016be4  mov     ebx, eax
0x180016be6  test    eax, eax
0x180016be8  jnz     loc_180016C76
0x180016bee  lea     rbx, [rsi+2]
0x180016bf2  test    rbp, rbp
0x180016bf5  jnz     short loc_180016C32
0x180016bf7  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016bfe  jz      short loc_180016C13
0x180016c00  lea     edx, [rax+23h]
0x180016c03  mov     [rsp+78h+phkResult], rbx
0x180016c08  mov     r9, rdi
0x180016c0b  mov     r8, r13
0x180016c0e  call    WPP_SF_SS
0x180016c13  mov     rcx, [rsp+78h+hKey]; hKey
0x180016c18  mov     rdx, rbx; lpValueName
0x180016c1b  call    cs:__imp_RegDeleteValueW
0x180016c22  nop     dword ptr [rax+rax+00h]
0x180016c27  mov     ebx, eax
0x180016c29  cmp     eax, 2
0x180016c2c  jnz     short loc_180016C76
0x180016c2e  xor     ebx, ebx
0x180016c30  jmp     short loc_180016C76
0x180016c32  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016c39  jz      short loc_180016C50
0x180016c3b  mov     edx, 24h ; '$'
0x180016c40  mov     [rsp+78h+phkResult], rbx
0x180016c45  mov     r9, rdi
0x180016c48  mov     r8, r13
0x180016c4b  call    WPP_SF_SS
0x180016c50  mov     rcx, [rsp+78h+hKey]; hKey
0x180016c55  mov     r9d, r14d; dwType
0x180016c58  mov     [rsp+78h+cbData], r15d; cbData
0x180016c5d  xor     r8d, r8d; Reserved
0x180016c60  mov     rdx, rbx; lpValueName
0x180016c63  mov     [rsp+78h+phkResult], rbp; lpData
0x180016c68  call    cs:__imp_RegSetValueExW
0x180016c6f  nop     dword ptr [rax+rax+00h]
0x180016c74  mov     ebx, eax
0x180016c76  mov     rcx, [rsp+78h+hKey]; hKey
0x180016c7b  call    cs:__imp_RegCloseKey
0x180016c82  nop     dword ptr [rax+rax+00h]
0x180016c87  lea     rcx, [rsp+78h+Str]
0x180016c8c  call    DhcpFree
0x180016c91  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016c98  jz      short loc_180016CAF
0x180016c9a  mov     edx, 25h ; '%'
0x180016c9f  mov     ecx, 404h
0x180016ca4  mov     r9d, ebx
0x180016ca7  mov     r8, r13
0x180016caa  call    WPP_SF_D
0x180016caf  mov     eax, ebx
0x180016cb1  add     rsp, 40h
0x180016cb5  pop     r15
0x180016cb7  pop     r14
0x180016cb9  pop     r13
0x180016cbb  pop     rdi
0x180016cbc  pop     rsi
0x180016cbd  pop     rbp
0x180016cbe  pop     rbx
0x180016cbf  retn
```
