# ISAPI_DLL::AccessCheck(void *,void *)

- ea: `0x1800050fc`
- end: `0x1800051da`
- name: `?AccessCheck@ISAPI_DLL@@QEAAHPEAX0@Z`
- size: `222`
- prototype: `_BOOL8 __fastcall(ISAPI_DLL *this, void *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005224`
- `0x180005640`

## callees

- `0x1800050fc`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000514d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000514d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000519f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000519f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000515e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000515e`

## pseudocode

```c
_BOOL8 __fastcall ISAPI_DLL::AccessCheck(ISAPI_DLL *this, void *a2, void *a3)
{
  void *v5; // rdx
  void *Ptr; // rax
  _BOOL8 result; // rax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-1B8h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-1B4h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-1B0h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+50h] [rbp-1A8h] BYREF

  GrantedAccess = 0;
  PrivilegeSetLength = 400;
  AccessStatus = 0;
  result = 1;
  if ( !a3 || (v5 = (void *)*((_QWORD *)this + 31)) == 0 || !EqualSid(a3, v5) )
  {
    Ptr = BUFFER::QueryPtr((ISAPI_DLL *)((char *)this + 200));
    if ( !AccessCheck(
            Ptr,
            a2,
            0x1200A0u,
            &g_FileGenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus)
      || !AccessStatus )
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800050fc  mov     [rsp+arg_18], rbx
0x180005101  push    rdi
0x180005102  sub     rsp, 1F0h
0x180005109  mov     rax, cs:__security_cookie
0x180005110  xor     rax, rsp
0x180005113  mov     [rsp+1F8h+var_18], rax
0x18000511b  mov     [rsp+1F8h+var_1B4], 0
0x180005123  mov     rdi, rdx
0x180005126  mov     [rsp+1F8h+var_1B0], 190h
0x18000512e  mov     rbx, rcx
0x180005131  mov     [rsp+1F8h+var_1B8], 0
0x180005139  test    r8, r8
0x18000513c  jz      short loc_180005157
0x18000513e  mov     rdx, [rcx+0F8h]; pSid2
0x180005145  test    rdx, rdx
0x180005148  jz      short loc_180005157
0x18000514a  mov     rcx, r8; pSid1
0x18000514d  call    cs:__imp_EqualSid
0x180005153  test    eax, eax
0x180005155  jnz     short loc_1800051B0
0x180005157  lea     rcx, [rbx+0C8h]
0x18000515e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005164  lea     rcx, [rsp+1F8h+var_1B8]
0x180005169  mov     r8d, 1200A0h; DesiredAccess
0x18000516f  mov     [rsp+1F8h+AccessStatus], rcx; AccessStatus
0x180005174  lea     r9, ?g_FileGenericMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000517b  lea     rcx, [rsp+1F8h+var_1B4]
0x180005180  mov     rdx, rdi; ClientToken
0x180005183  mov     [rsp+1F8h+GrantedAccess], rcx; GrantedAccess
0x180005188  lea     rcx, [rsp+1F8h+var_1B0]
0x18000518d  mov     [rsp+1F8h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x180005192  lea     rcx, [rsp+1F8h+var_1A8]
0x180005197  mov     [rsp+1F8h+PrivilegeSet], rcx; PrivilegeSet
0x18000519c  mov     rcx, rax; pSecurityDescriptor
0x18000519f  call    cs:__imp_AccessCheck
0x1800051a5  test    eax, eax
0x1800051a7  jz      short loc_1800051B7
0x1800051a9  cmp     [rsp+1F8h+var_1B8], 0
0x1800051ae  jz      short loc_1800051B7
0x1800051b0  mov     eax, 1
0x1800051b5  jmp     short loc_1800051B9
0x1800051b7  xor     eax, eax
0x1800051b9  mov     rcx, [rsp+1F8h+var_18]
0x1800051c1  xor     rcx, rsp; StackCookie
0x1800051c4  call    __security_check_cookie
0x1800051c9  mov     rbx, [rsp+1F8h+arg_18]
0x1800051d1  add     rsp, 1F0h
0x1800051d8  pop     rdi
0x1800051d9  retn
```
