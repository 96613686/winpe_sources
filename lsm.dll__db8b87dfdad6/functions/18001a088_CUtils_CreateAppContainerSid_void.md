# CUtils::CreateAppContainerSid(void * *)

- ea: `0x18001a088`
- end: `0x18001a159`
- name: `?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(PSID *pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019dc8`
- `0x18002d804`

## callees

- `0x1800074c0`
- `0x18001a088`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a110`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a106`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a106`

## string_xrefs

- `0x18001a0b1`: `CUtils::CreateAppContainerSid`
- `0x18001a129`: `CUtils::CreateAppContainerSid`
- `0x18001a133`: `AllocateAndInitializeSid failed: 0x%x in %s`
- `0x18001a0bd`: `ppAppContainerSid`

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
0x18001a088  push    rbx
0x18001a08a  sub     rsp, 70h
0x18001a08e  mov     rax, cs:__security_cookie
0x18001a095  xor     rax, rsp
0x18001a098  mov     [rsp+78h+var_10], rax
0x18001a09d  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x18001a0a5  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x18001a0ac  test    rcx, rcx
0x18001a0af  jnz     short loc_18001A0D7
0x18001a0b1  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x18001a0b8  mov     ecx, 8; int
0x18001a0bd  lea     r8, aPpappcontainer; "ppAppContainerSid"
0x18001a0c4  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18001a0cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a0d0  mov     ebx, 80070057h
0x18001a0d5  jmp     short loc_18001A144
0x18001a0d7  xor     ebx, ebx
0x18001a0d9  mov     [rsp+78h+pSid], rcx; pSid
0x18001a0de  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x18001a0e2  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x18001a0e7  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x18001a0eb  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x18001a0ef  lea     r8d, [rbx+2]; nSubAuthority0
0x18001a0f3  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x18001a0f7  mov     dl, r8b; nSubAuthorityCount
0x18001a0fa  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x18001a0fe  lea     r9d, [rbx+1]; nSubAuthority1
0x18001a102  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x18001a106  call    cs:__imp_AllocateAndInitializeSid
0x18001a10c  test    eax, eax
0x18001a10e  jnz     short loc_18001A144
0x18001a110  call    cs:__imp_GetLastError
0x18001a116  mov     ebx, eax
0x18001a118  test    eax, eax
0x18001a11a  jle     short loc_18001A125
0x18001a11c  movzx   ebx, ax
0x18001a11f  or      ebx, 80070000h
0x18001a125  test    ebx, ebx
0x18001a127  jns     short loc_18001A144
0x18001a129  lea     r9, aCutilsCreateap_1; "CUtils::CreateAppContainerSid"
0x18001a130  mov     r8d, ebx
0x18001a133  lea     rdx, aAllocateandini_1; "AllocateAndInitializeSid failed: 0x%x i"...
0x18001a13a  mov     ecx, 8; int
0x18001a13f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001a144  mov     eax, ebx
0x18001a146  mov     rcx, [rsp+78h+var_10]
0x18001a14b  xor     rcx, rsp; StackCookie
0x18001a14e  call    __security_check_cookie
0x18001a153  add     rsp, 70h
0x18001a157  pop     rbx
0x18001a158  retn
```
