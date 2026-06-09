# CUtils::CreateAppContainerSid(void * *)

- ea: `0x180009490`
- end: `0x18000956e`
- name: `?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z`
- size: `222`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ab80`
- `0x18002f7c0`

## callees

- `0x1800077a0`
- `0x180009490`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000951e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000951e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000950e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000950e`

## string_xrefs

- `0x1800094c5`: `ppAppContainerSid`
- `0x1800094b9`: `CUtils::CreateAppContainerSid`
- `0x18000953d`: `CUtils::CreateAppContainerSid`
- `0x180009547`: `AllocateAndInitializeSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateAppContainerSid(PSID *pSid)
{
  signed int v1; // ebx
  signed int LastError; // eax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( pSid )
  {
    v1 = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, pSid) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
        _DbgPrintMessage(8, "AllocateAndInitializeSid failed: 0x%x in %s", v1, "CUtils::CreateAppContainerSid");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "ppAppContainerSid", "CUtils::CreateAppContainerSid");
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180009490  push    rbx
0x180009492  sub     rsp, 70h
0x180009496  mov     rax, cs:__security_cookie
0x18000949d  xor     rax, rsp
0x1800094a0  mov     [rsp+78h+var_10], rax
0x1800094a5  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x1800094ad  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x1800094b4  test    rcx, rcx
0x1800094b7  jnz     short loc_1800094DF
0x1800094b9  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x1800094c0  mov     ecx, 8; int
0x1800094c5  lea     r8, aPpappcontainer; "ppAppContainerSid"
0x1800094cc  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x1800094d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800094d8  mov     ebx, 80070057h
0x1800094dd  jmp     short loc_180009558
0x1800094df  xor     ebx, ebx
0x1800094e1  mov     [rsp+78h+pSid], rcx; pSid
0x1800094e6  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x1800094ea  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x1800094ef  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x1800094f3  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x1800094f7  lea     r8d, [rbx+2]; nSubAuthority0
0x1800094fb  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x1800094ff  mov     dl, r8b; nSubAuthorityCount
0x180009502  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x180009506  lea     r9d, [rbx+1]; nSubAuthority1
0x18000950a  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x18000950e  call    cs:__imp_AllocateAndInitializeSid
0x180009515  nop     dword ptr [rax+rax+00h]
0x18000951a  test    eax, eax
0x18000951c  jnz     short loc_180009558
0x18000951e  call    cs:__imp_GetLastError
0x180009525  nop     dword ptr [rax+rax+00h]
0x18000952a  mov     ebx, eax
0x18000952c  test    eax, eax
0x18000952e  jle     short loc_180009539
0x180009530  movzx   ebx, ax
0x180009533  or      ebx, 80070000h
0x180009539  test    ebx, ebx
0x18000953b  jns     short loc_180009558
0x18000953d  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x180009544  mov     r8d, ebx
0x180009547  lea     rdx, aAllocateandini_1; "AllocateAndInitializeSid failed: 0x%x i"...
0x18000954e  mov     ecx, 8; int
0x180009553  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009558  mov     eax, ebx
0x18000955a  mov     rcx, [rsp+78h+var_10]
0x18000955f  xor     rcx, rsp; StackCookie
0x180009562  call    __security_check_cookie
0x180009567  add     rsp, 70h
0x18000956b  pop     rbx
0x18000956c  retn
```
