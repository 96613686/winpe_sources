# Int_FwValidatePackageId

- ea: `0x18000d364`
- end: `0x18000d3f4`
- name: `Int_FwValidatePackageId`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d490`

## callees

- `0x18000ccd4`
- `0x18000d364`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d394`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d38a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d38a`

## pseudocode

```c
__int64 __fastcall Int_FwValidatePackageId(const WCHAR *a1)
{
  DWORD LastError; // ebx
  PSID Sid; // [rsp+20h] [rbp-18h] BYREF

  LastError = 0;
  Sid = 0;
  if ( a1 )
  {
    if ( ConvertStringSidToSidW(a1, &Sid) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, LastError);
    }
    if ( Sid )
      LocalFree(Sid);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d364  push    rbx
0x18000d366  sub     rsp, 30h
0x18000d36a  mov     rax, cs:__security_cookie
0x18000d371  xor     rax, rsp
0x18000d374  mov     [rsp+38h+var_10], rax
0x18000d379  xor     ebx, ebx
0x18000d37b  mov     [rsp+38h+Sid], rbx
0x18000d380  test    rcx, rcx
0x18000d383  jz      short loc_18000D3C5
0x18000d385  lea     rdx, [rsp+38h+Sid]; Sid
0x18000d38a  call    cs:__imp_ConvertStringSidToSidW
0x18000d390  test    eax, eax
0x18000d392  jz      short loc_18000D3B5
0x18000d394  call    cs:__imp_GetLastError
0x18000d39a  mov     ebx, eax
0x18000d39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3a3  lea     rax, WPP_GLOBAL_Control
0x18000d3aa  cmp     rcx, rax
0x18000d3ad  jz      short loc_18000D3B5
0x18000d3af  test    byte ptr [rcx+1Ch], 1
0x18000d3b3  jnz     short loc_18000D3DA
0x18000d3b5  mov     rcx, [rsp+38h+Sid]; hMem
0x18000d3ba  test    rcx, rcx
0x18000d3bd  jz      short loc_18000D3C5
0x18000d3bf  call    cs:__imp_LocalFree
0x18000d3c5  mov     eax, ebx
0x18000d3c7  mov     rcx, [rsp+38h+var_10]
0x18000d3cc  xor     rcx, rsp; StackCookie
0x18000d3cf  call    __security_check_cookie
0x18000d3d4  add     rsp, 30h
0x18000d3d8  pop     rbx
0x18000d3d9  retn
0x18000d3da  mov     rcx, [rcx+10h]
0x18000d3de  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000d3e5  mov     edx, 116h
0x18000d3ea  mov     r9d, ebx
0x18000d3ed  call    WPP_SF_d
0x18000d3f2  jmp     short loc_18000D3B5
```
