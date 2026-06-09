# HHMakePathInheritAcl(char *)

- ea: `0x18004eff4`
- end: `0x18004f17e`
- name: `?HHMakePathInheritAcl@@YAJPEAD@Z`
- size: `394`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004ed7c`
- `0x18004f3cc`

## callees

- `0x1800095c8`
- `0x18004eff4`
- `0x18004f560`
- `0x18004f5e4`
- `0x18004f794`
- `0x180075c90`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004f0fc`
- `KERNEL32!LocalFree` at `0x18004f107`
- `KERNEL32!LocalFree` at `0x18004f0fc`
- `KERNEL32!LocalFree` at `0x18004f107`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x18004f0b3`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x18004f0b3`
- `ADVAPI32!SetNamedSecurityInfoA` at `0x18004f0eb`
- `ADVAPI32!SetNamedSecurityInfoA` at `0x18004f14f`
- `ADVAPI32!SetNamedSecurityInfoA` at `0x18004f0eb`
- `ADVAPI32!SetNamedSecurityInfoA` at `0x18004f14f`
- `ADVAPI32!InitializeAcl` at `0x18004f11d`
- `ADVAPI32!InitializeAcl` at `0x18004f11d`

## pseudocode

```c
__int64 __fastcall HHMakePathInheritAcl(char *a1)
{
  __int64 result; // rax
  __int64 v3; // rdx
  _BYTE *v4; // rax
  unsigned int v5; // ebx
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-C0h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-B8h] BYREF
  CHAR pObjectName[272]; // [rsp+50h] [rbp-B0h] BYREF

  result = IsNT();
  if ( (_DWORD)result )
  {
    StringCchCopyA(pObjectName, 0x104u, a1);
    LOBYTE(v3) = 92;
    v4 = (_BYTE *)StrRChr(pObjectName, v3);
    if ( v4 )
    {
      v5 = -2147467259;
      *v4 = 0;
      hMem = 0;
      if ( (unsigned int)IsNT4OrLess() )
      {
        pDacl = 0;
        if ( !GetNamedSecurityInfoA(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pDacl, 0, &hMem) )
        {
          v5 = SetNamedSecurityInfoA(a1, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0) != 0 ? 0x80004005 : 0;
          LocalFree(pDacl);
          LocalFree(hMem);
        }
      }
      else
      {
        InitializeAcl((PACL)&hMem, 8u, 2u);
        return SetNamedSecurityInfoA(a1, SE_FILE_OBJECT, 0x20000004u, 0, 0, (PACL)&hMem, 0) != 0 ? 0x80004005 : 0;
      }
      return v5;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004eff4  mov     [rsp-8+arg_8], rbx
0x18004eff9  mov     [rsp-8+arg_10], rdi
0x18004effe  push    rbp
0x18004efff  lea     rbp, [rsp-70h]
0x18004f004  sub     rsp, 170h
0x18004f00b  mov     rax, cs:__security_cookie
0x18004f012  xor     rax, rsp
0x18004f015  mov     [rbp+70h+var_10], rax
0x18004f019  mov     rdi, rcx
0x18004f01c  call    ?IsNT@@YAHXZ; IsNT(void)
0x18004f021  test    eax, eax
0x18004f023  jz      loc_18004F15D
0x18004f029  mov     r8, rdi; char *
0x18004f02c  lea     rcx, [rsp+170h+pObjectName]; char *
0x18004f031  mov     edx, 104h; unsigned __int64
0x18004f036  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18004f03b  mov     dl, 5Ch ; '\'
0x18004f03d  lea     rcx, [rsp+170h+pObjectName]
0x18004f042  call    StrRChr
0x18004f047  test    rax, rax
0x18004f04a  jnz     short loc_18004F056
0x18004f04c  mov     eax, 80004005h
0x18004f051  jmp     loc_18004F15D
0x18004f056  mov     ebx, 80004005h
0x18004f05b  mov     byte ptr [rax], 0
0x18004f05e  call    ?IsNT4OrLess@@YAHXZ; IsNT4OrLess(void)
0x18004f063  mov     [rsp+170h+hMem], 0
0x18004f06c  test    eax, eax
0x18004f06e  jz      loc_18004F10F
0x18004f074  xor     r9d, r9d; ppsidOwner
0x18004f077  mov     [rsp+170h+pDacl], 0
0x18004f080  lea     rax, [rsp+170h+hMem]
0x18004f085  mov     [rsp+170h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18004f08a  lea     rcx, [rsp+170h+pObjectName]; pObjectName
0x18004f08f  lea     rax, [rsp+170h+pDacl]
0x18004f094  mov     [rsp+170h+ppSacl], 0; ppSacl
0x18004f09d  mov     [rsp+170h+ppDacl], rax; ppDacl
0x18004f0a2  lea     edx, [r9+1]; ObjectType
0x18004f0a6  lea     r8d, [r9+4]; SecurityInfo
0x18004f0aa  mov     [rsp+170h+ppsidGroup], 0; ppsidGroup
0x18004f0b3  call    cs:__imp_GetNamedSecurityInfoA
0x18004f0b9  test    eax, eax
0x18004f0bb  jnz     loc_18004F15B
0x18004f0c1  mov     rax, [rsp+170h+pDacl]
0x18004f0c6  xor     r9d, r9d; psidOwner
0x18004f0c9  mov     [rsp+170h+ppSacl], 0; pSacl
0x18004f0d2  mov     rcx, rdi; pObjectName
0x18004f0d5  mov     [rsp+170h+ppDacl], rax; pDacl
0x18004f0da  mov     [rsp+170h+ppsidGroup], 0; psidGroup
0x18004f0e3  lea     edx, [r9+1]; ObjectType
0x18004f0e7  lea     r8d, [r9+4]; SecurityInfo
0x18004f0eb  call    cs:__imp_SetNamedSecurityInfoA
0x18004f0f1  neg     eax
0x18004f0f3  sbb     ecx, ecx
0x18004f0f5  and     ebx, ecx
0x18004f0f7  mov     rcx, [rsp+170h+pDacl]; hMem
0x18004f0fc  call    cs:__imp_LocalFree
0x18004f102  mov     rcx, [rsp+170h+hMem]; hMem
0x18004f107  call    cs:__imp_LocalFree
0x18004f10d  jmp     short loc_18004F15B
0x18004f10f  mov     edx, 8; nAclLength
0x18004f114  lea     rcx, [rsp+170h+hMem]; pAcl
0x18004f119  lea     r8d, [rdx-6]; dwAclRevision
0x18004f11d  call    cs:__imp_InitializeAcl
0x18004f123  xor     r9d, r9d; psidOwner
0x18004f126  mov     [rsp+170h+ppSacl], 0; pSacl
0x18004f12f  lea     rax, [rsp+170h+hMem]
0x18004f134  mov     r8d, 20000004h; SecurityInfo
0x18004f13a  mov     [rsp+170h+ppDacl], rax; pDacl
0x18004f13f  mov     rcx, rdi; pObjectName
0x18004f142  mov     [rsp+170h+ppsidGroup], 0; psidGroup
0x18004f14b  lea     edx, [r9+1]; ObjectType
0x18004f14f  call    cs:__imp_SetNamedSecurityInfoA
0x18004f155  neg     eax
0x18004f157  sbb     ecx, ecx
0x18004f159  and     ebx, ecx
0x18004f15b  mov     eax, ebx
0x18004f15d  mov     rcx, [rbp+70h+var_10]
0x18004f161  xor     rcx, rsp; StackCookie
0x18004f164  call    __security_check_cookie
0x18004f169  lea     r11, [rsp+170h+var_s0]
0x18004f171  mov     rbx, [r11+18h]
0x18004f175  mov     rdi, [r11+20h]
0x18004f179  mov     rsp, r11
0x18004f17c  pop     rbp
0x18004f17d  retn
```
