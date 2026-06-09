# CMSMQTriggerSet::DeleteTriggerServiceFromDacl(_ACL *,void *)

- ea: `0x18001108c`
- end: `0x180011150`
- name: `?DeleteTriggerServiceFromDacl@CMSMQTriggerSet@@AEAAJPEAU_ACL@@PEAX@Z`
- size: `196`
- prototype: `int __fastcall(CMSMQTriggerSet *this, struct _ACL *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180012d10`

## callees

- `0x18001108c`
- `0x18001e380`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800110d8`
- `KERNEL32!GetLastError` at `0x1800110d8`
- `ADVAPI32!DeleteAce` at `0x180011127`
- `ADVAPI32!DeleteAce` at `0x180011127`
- `ADVAPI32!EqualSid` at `0x180011114`
- `ADVAPI32!EqualSid` at `0x180011114`
- `ADVAPI32!GetAce` at `0x1800110fe`
- `ADVAPI32!GetAce` at `0x1800110fe`
- `ADVAPI32!GetAclInformation` at `0x1800110ce`
- `ADVAPI32!GetAclInformation` at `0x1800110ce`

## pseudocode

```c
int __fastcall CMSMQTriggerSet::DeleteTriggerServiceFromDacl(CMSMQTriggerSet *this, struct _ACL *a2, void *a3)
{
  int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  int v9; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  pAce = 0;
  if ( GetAclInformation(a2, &v8, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)v8; ++i )
    {
      if ( GetAce(a2, i, &pAce) && EqualSid((char *)pAce + 8, a3) )
      {
        if ( !DeleteAce(a2, i) )
          goto LABEL_2;
        return 0;
      }
    }
    return 0;
  }
  else
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001108c  mov     r11, rsp
0x18001108f  mov     [r11+8], rbx
0x180011093  mov     [r11+20h], rsi
0x180011097  push    rdi
0x180011098  sub     rsp, 40h
0x18001109c  mov     rax, cs:__security_cookie
0x1800110a3  xor     rax, rsp
0x1800110a6  mov     [rsp+48h+var_10], rax
0x1800110ab  xor     eax, eax
0x1800110ad  mov     rdi, rdx
0x1800110b0  mov     rsi, r8
0x1800110b3  mov     [r11-20h], rax
0x1800110b7  lea     rdx, [r11-20h]; pAclInformation
0x1800110bb  mov     [rsp+48h+var_18], eax
0x1800110bf  mov     rcx, rdi; pAcl
0x1800110c2  mov     [r11-28h], rax
0x1800110c6  lea     r9d, [rax+2]; dwAclInformationClass
0x1800110ca  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800110ce  call    cs:__imp_GetAclInformation
0x1800110d4  test    eax, eax
0x1800110d6  jnz     short loc_1800110EC
0x1800110d8  call    cs:__imp_GetLastError
0x1800110de  test    eax, eax
0x1800110e0  jle     short loc_180011133
0x1800110e2  movzx   eax, ax
0x1800110e5  or      eax, 80070000h
0x1800110ea  jmp     short loc_180011133
0x1800110ec  xor     ebx, ebx
0x1800110ee  cmp     ebx, dword ptr [rsp+48h+var_20]
0x1800110f2  jnb     short loc_180011131
0x1800110f4  lea     r8, [rsp+48h+pAce]; pAce
0x1800110f9  mov     edx, ebx; dwAceIndex
0x1800110fb  mov     rcx, rdi; pAcl
0x1800110fe  call    cs:__imp_GetAce
0x180011104  test    eax, eax
0x180011106  jz      short loc_18001111E
0x180011108  mov     rcx, [rsp+48h+pAce]
0x18001110d  mov     rdx, rsi; pSid2
0x180011110  add     rcx, 8; pSid1
0x180011114  call    cs:__imp_EqualSid
0x18001111a  test    eax, eax
0x18001111c  jnz     short loc_180011122
0x18001111e  inc     ebx
0x180011120  jmp     short loc_1800110EE
0x180011122  mov     edx, ebx; dwAceIndex
0x180011124  mov     rcx, rdi; pAcl
0x180011127  call    cs:__imp_DeleteAce
0x18001112d  test    eax, eax
0x18001112f  jz      short loc_1800110D8
0x180011131  xor     eax, eax
0x180011133  mov     rcx, [rsp+48h+var_10]
0x180011138  xor     rcx, rsp; StackCookie
0x18001113b  call    __security_check_cookie
0x180011140  mov     rbx, [rsp+48h+arg_0]
0x180011145  mov     rsi, [rsp+48h+arg_18]
0x18001114a  add     rsp, 40h
0x18001114e  pop     rdi
0x18001114f  retn
```
