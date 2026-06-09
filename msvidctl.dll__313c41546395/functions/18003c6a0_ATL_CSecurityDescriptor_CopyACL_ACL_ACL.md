# ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)

- ea: `0x18003c6a0`
- end: `0x18003c77b`
- name: `?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z`
- size: `219`
- prototype: `__int64 __fastcall(PACL pAcl, PACL)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003acc0`

## callees

- `0x180004640`
- `0x18003c6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003c700`
- `KERNEL32!GetLastError` at `0x18003c700`
- `ADVAPI32!AddAce` at `0x18003c74a`
- `ADVAPI32!AddAce` at `0x18003c74a`
- `ADVAPI32!GetAce` at `0x18003c726`
- `ADVAPI32!GetAce` at `0x18003c726`
- `ADVAPI32!GetAclInformation` at `0x18003c6f6`
- `ADVAPI32!GetAclInformation` at `0x18003c6f6`

## pseudocode

```c
signed int __fastcall ATL::CSecurityDescriptor::CopyACL(PACL pAcl, PACL a2)
{
  signed int result; // eax
  DWORD v5; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+40h] [rbp-18h]

  pAclInformation = 0;
  v8 = 0;
  pAce = 0;
  if ( !pAcl )
    return -2147467261;
  if ( !a2 )
    return 0;
  if ( GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    v5 = 0;
    if ( (_DWORD)pAclInformation )
    {
      while ( GetAce(a2, v5, &pAce) && AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        if ( ++v5 >= (unsigned int)pAclInformation )
          return 0;
      }
      goto LABEL_5;
    }
    return 0;
  }
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003c6a0  mov     r11, rsp
0x18003c6a3  mov     [r11+18h], rbx
0x18003c6a7  mov     [r11+20h], rsi
0x18003c6ab  push    rdi
0x18003c6ac  sub     rsp, 50h
0x18003c6b0  mov     rax, cs:__security_cookie
0x18003c6b7  xor     rax, rsp
0x18003c6ba  mov     [rsp+58h+var_10], rax
0x18003c6bf  xor     eax, eax
0x18003c6c1  mov     rdi, rdx
0x18003c6c4  mov     [r11-20h], rax
0x18003c6c8  mov     rsi, rcx
0x18003c6cb  mov     [rsp+58h+var_18], eax
0x18003c6cf  mov     [r11-28h], rax
0x18003c6d3  test    rcx, rcx
0x18003c6d6  jnz     short loc_18003C6DF
0x18003c6d8  mov     eax, 80004003h
0x18003c6dd  jmp     short loc_18003C75E
0x18003c6df  test    rdi, rdi
0x18003c6e2  jz      short loc_18003C75C
0x18003c6e4  mov     r9d, 2; dwAclInformationClass
0x18003c6ea  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x18003c6ef  mov     rcx, rdi; pAcl
0x18003c6f2  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18003c6f6  call    cs:__imp_GetAclInformation
0x18003c6fc  test    eax, eax
0x18003c6fe  jnz     short loc_18003C714
0x18003c700  call    cs:__imp_GetLastError
0x18003c706  test    eax, eax
0x18003c708  jle     short loc_18003C75E
0x18003c70a  movzx   eax, ax
0x18003c70d  or      eax, 80070000h
0x18003c712  jmp     short loc_18003C75E
0x18003c714  xor     ebx, ebx
0x18003c716  cmp     dword ptr [rsp+58h+pAclInformation], ebx
0x18003c71a  jbe     short loc_18003C75C
0x18003c71c  lea     r8, [rsp+58h+pAce]; pAce
0x18003c721  mov     edx, ebx; dwAceIndex
0x18003c723  mov     rcx, rdi; pAcl
0x18003c726  call    cs:__imp_GetAce
0x18003c72c  test    eax, eax
0x18003c72e  jz      short loc_18003C700
0x18003c730  mov     r9, [rsp+58h+pAce]; pAceList
0x18003c735  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18003c739  mov     edx, 2; dwAceRevision
0x18003c73e  mov     rcx, rsi; pAcl
0x18003c741  movzx   eax, word ptr [r9+2]
0x18003c746  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x18003c74a  call    cs:__imp_AddAce
0x18003c750  test    eax, eax
0x18003c752  jz      short loc_18003C700
0x18003c754  inc     ebx
0x18003c756  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x18003c75a  jb      short loc_18003C71C
0x18003c75c  xor     eax, eax
0x18003c75e  mov     rcx, [rsp+58h+var_10]
0x18003c763  xor     rcx, rsp; StackCookie
0x18003c766  call    __security_check_cookie
0x18003c76b  mov     rbx, [rsp+58h+arg_10]
0x18003c770  mov     rsi, [rsp+58h+arg_18]
0x18003c775  add     rsp, 50h
0x18003c779  pop     rdi
0x18003c77a  retn
```
