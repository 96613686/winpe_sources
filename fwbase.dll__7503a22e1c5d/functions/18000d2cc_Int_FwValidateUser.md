# Int_FwValidateUser

- ea: `0x18000d2cc`
- end: `0x18000d35c`
- name: `Int_FwValidateUser`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d490`

## callees

- `0x18000ccd4`
- `0x18000d2cc`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d327`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d327`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d2f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d2f2`

## pseudocode

```c
__int64 __fastcall Int_FwValidateUser(const WCHAR *a1)
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 277, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, LastError);
    }
    if ( Sid )
      LocalFree(Sid);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d2cc  push    rbx
0x18000d2ce  sub     rsp, 30h
0x18000d2d2  mov     rax, cs:__security_cookie
0x18000d2d9  xor     rax, rsp
0x18000d2dc  mov     [rsp+38h+var_10], rax
0x18000d2e1  xor     ebx, ebx
0x18000d2e3  mov     [rsp+38h+Sid], rbx
0x18000d2e8  test    rcx, rcx
0x18000d2eb  jz      short loc_18000D32D
0x18000d2ed  lea     rdx, [rsp+38h+Sid]; Sid
0x18000d2f2  call    cs:__imp_ConvertStringSidToSidW
0x18000d2f8  test    eax, eax
0x18000d2fa  jz      short loc_18000D31D
0x18000d2fc  call    cs:__imp_GetLastError
0x18000d302  mov     ebx, eax
0x18000d304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d30b  lea     rax, WPP_GLOBAL_Control
0x18000d312  cmp     rcx, rax
0x18000d315  jz      short loc_18000D31D
0x18000d317  test    byte ptr [rcx+1Ch], 1
0x18000d31b  jnz     short loc_18000D342
0x18000d31d  mov     rcx, [rsp+38h+Sid]; hMem
0x18000d322  test    rcx, rcx
0x18000d325  jz      short loc_18000D32D
0x18000d327  call    cs:__imp_LocalFree
0x18000d32d  mov     eax, ebx
0x18000d32f  mov     rcx, [rsp+38h+var_10]
0x18000d334  xor     rcx, rsp; StackCookie
0x18000d337  call    __security_check_cookie
0x18000d33c  add     rsp, 30h
0x18000d340  pop     rbx
0x18000d341  retn
0x18000d342  mov     rcx, [rcx+10h]
0x18000d346  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000d34d  mov     edx, 115h
0x18000d352  mov     r9d, ebx
0x18000d355  call    WPP_SF_d
0x18000d35a  jmp     short loc_18000D31D
```
