# RidToSid

- ea: `0x180010a28`
- end: `0x180010b01`
- name: `RidToSid`
- size: `217`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180072cd4`

## callees

- `0x180010a28`
- `0x180011ac0`
- `0x180072b6c`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a90`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010a86`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010a86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010adb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180010adb`

## string_xrefs

- `0x180010aab`: `com\complus\dtc\shared\util\security.cpp`
- `0x180010ab2`: `InstallDTC: AllocateAndInitializeSid failed`

## pseudocode

```c
__int64 __fastcall RidToSid(DWORD nSubAuthority0, __int64 a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  pSid = 0;
  *(_DWORD *)v7.Value = 0;
  if ( AllocateAndInitializeSid(&v7, 1u, nSubAuthority0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = DynCopySid(a2, pSid);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    TraceFile(
      v4,
      "InstallDTC: AllocateAndInitializeSid failed",
      "com\\complus\\dtc\\shared\\util\\security.cpp",
      0x1C0u);
  }
  if ( pSid )
    FreeSid(pSid);
  return v4;
}

```

## disassembly

```asm
0x180010a28  mov     r11, rsp
0x180010a2b  mov     [r11+18h], rbx
0x180010a2f  push    rdi
0x180010a30  sub     rsp, 80h
0x180010a37  mov     rax, cs:__security_cookie
0x180010a3e  xor     rax, rsp
0x180010a41  mov     [rsp+88h+var_18], rax
0x180010a46  xor     edi, edi
0x180010a48  mov     [rsp+88h+var_1C], 500h
0x180010a4f  lea     rax, [r11-28h]
0x180010a53  mov     [r11-28h], rdi
0x180010a57  mov     [r11-38h], rax
0x180010a5b  mov     rbx, rdx
0x180010a5e  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180010a62  mov     r8d, ecx; nSubAuthority0
0x180010a65  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180010a69  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180010a6d  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180010a71  xor     r9d, r9d; nSubAuthority1
0x180010a74  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180010a78  mov     dl, 1; nSubAuthorityCount
0x180010a7a  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180010a7e  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x180010a82  mov     [rsp+88h+var_20], edi
0x180010a86  call    cs:__imp_AllocateAndInitializeSid
0x180010a8c  test    eax, eax
0x180010a8e  jnz     short loc_180010AC2
0x180010a90  call    cs:__imp_GetLastError
0x180010a96  mov     ebx, eax
0x180010a98  test    eax, eax
0x180010a9a  jle     short loc_180010AA5
0x180010a9c  movzx   ebx, ax
0x180010a9f  or      ebx, 80070000h
0x180010aa5  mov     r9d, 1C0h; unsigned int
0x180010aab  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x180010ab2  lea     rdx, aInstalldtcAllo; "InstallDTC: AllocateAndInitializeSid fa"...
0x180010ab9  mov     ecx, ebx; int
0x180010abb  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010ac0  jmp     short loc_180010AD1
0x180010ac2  mov     rdx, [rsp+88h+pSid]
0x180010ac7  mov     rcx, rbx
0x180010aca  call    DynCopySid
0x180010acf  mov     ebx, eax
0x180010ad1  mov     rcx, [rsp+88h+pSid]; pSid
0x180010ad6  test    rcx, rcx
0x180010ad9  jz      short loc_180010AE1
0x180010adb  call    cs:__imp_FreeSid
0x180010ae1  mov     eax, ebx
0x180010ae3  mov     rcx, [rsp+88h+var_18]
0x180010ae8  xor     rcx, rsp; StackCookie
0x180010aeb  call    __security_check_cookie
0x180010af0  mov     rbx, [rsp+88h+arg_10]
0x180010af8  add     rsp, 80h
0x180010aff  pop     rdi
0x180010b00  retn
```
