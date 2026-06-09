# CSharedMemoryMarshalingSecurityDescriptor::Init(ulong)

- ea: `0x180020044`
- end: `0x180020170`
- name: `?Init@CSharedMemoryMarshalingSecurityDescriptor@@QEAAJK@Z`
- size: `300`
- prototype: `__int64 __fastcall(CSharedMemoryMarshalingSecurityDescriptor *__hidden this, DWORD AccessMask)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fbb4`
- `0x18001fd94`
- `0x1800362a4`
- `0x1800367e8`

## callees

- `0x180020044`
- `0x18003f62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002009b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002009b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800200fe`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800200fe`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800200e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800200e7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800200d4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800200d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002007d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002007d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800200b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800200b7`

## string_xrefs

- `0x18002013f`: `onecoreuap\com\coml2\stg\h\df32.hxx`

## pseudocode

```c
__int64 __fastcall CSharedMemoryMarshalingSecurityDescriptor::Init(
        CSharedMemoryMarshalingSecurityDescriptor *this,
        DWORD AccessMask)
{
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF

  ReturnLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, this, 0x54u, &ReturnLength) )
  {
    if ( InitializeAcl((PACL)this + 11, 0x58u, 2u) )
    {
      if ( AddAccessAllowedAce((PACL)this + 11, 2u, AccessMask, *(PSID *)this) )
      {
        if ( InitializeSecurityDescriptor((char *)this + 176, 1u) )
        {
          if ( SetSecurityDescriptorOwner((char *)this + 176, *(PSID *)this, 0) )
          {
            if ( SetSecurityDescriptorDacl((char *)this + 176, 1, (PACL)this + 11, 0) )
            {
              *((_DWORD *)this + 110) = 24;
              result = 0;
              *((_QWORD *)this + 56) = (char *)this + 176;
              *((_DWORD *)this + 114) = 0;
              return result;
            }
            v6 = 87;
          }
          else
          {
            v6 = 86;
          }
        }
        else
        {
          v6 = 85;
        }
      }
      else
      {
        v6 = 83;
      }
    }
    else
    {
      v6 = 79;
    }
  }
  else
  {
    v6 = 75;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v6,
           (unsigned int)"onecoreuap\\com\\coml2\\stg\\h\\df32.hxx",
           v4);
}

```

## disassembly

```asm
0x180020044  mov     rax, rsp
0x180020047  mov     [rax+10h], rbx
0x18002004b  mov     [rax+18h], rsi
0x18002004f  push    rdi
0x180020050  sub     rsp, 30h
0x180020054  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18002005a  mov     dword ptr [rax+8], 0
0x180020061  mov     edi, edx
0x180020063  lea     rax, [rax+8]
0x180020067  mov     rbx, rcx
0x18002006a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002006f  mov     r8, rcx; TokenInformation
0x180020072  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180020079  lea     edx, [r9-53h]; TokenInformationClass
0x18002007d  call    cs:__imp_GetTokenInformation
0x180020083  test    eax, eax
0x180020085  jz      loc_180020135
0x18002008b  mov     edx, 58h ; 'X'; nAclLength
0x180020090  lea     rsi, [rbx+58h]
0x180020094  mov     rcx, rsi; pAcl
0x180020097  lea     r8d, [rdx-56h]; dwAclRevision
0x18002009b  call    cs:__imp_InitializeAcl
0x1800200a1  test    eax, eax
0x1800200a3  jz      loc_18002015B
0x1800200a9  mov     r9, [rbx]; pSid
0x1800200ac  mov     r8d, edi; AccessMask
0x1800200af  mov     edx, 2; dwAceRevision
0x1800200b4  mov     rcx, rsi; pAcl
0x1800200b7  call    cs:__imp_AddAccessAllowedAce
0x1800200bd  test    eax, eax
0x1800200bf  jz      loc_180020162
0x1800200c5  lea     rdi, [rbx+0B0h]
0x1800200cc  mov     edx, 1; dwRevision
0x1800200d1  mov     rcx, rdi; pSecurityDescriptor
0x1800200d4  call    cs:__imp_InitializeSecurityDescriptor
0x1800200da  test    eax, eax
0x1800200dc  jz      short loc_180020154
0x1800200de  mov     rdx, [rbx]; pOwner
0x1800200e1  xor     r8d, r8d; bOwnerDefaulted
0x1800200e4  mov     rcx, rdi; pSecurityDescriptor
0x1800200e7  call    cs:__imp_SetSecurityDescriptorOwner
0x1800200ed  test    eax, eax
0x1800200ef  jz      short loc_18002014D
0x1800200f1  xor     r9d, r9d; bDaclDefaulted
0x1800200f4  mov     r8, rsi; pDacl
0x1800200f7  mov     rcx, rdi; pSecurityDescriptor
0x1800200fa  lea     edx, [r9+1]; bDaclPresent
0x1800200fe  call    cs:__imp_SetSecurityDescriptorDacl
0x180020104  test    eax, eax
0x180020106  jz      short loc_180020169
0x180020108  mov     dword ptr [rbx+1B8h], 18h
0x180020112  xor     eax, eax
0x180020114  mov     [rbx+1C0h], rdi
0x18002011b  mov     dword ptr [rbx+1C8h], 0
0x180020125  mov     rbx, [rsp+38h+arg_8]
0x18002012a  mov     rsi, [rsp+38h+arg_10]
0x18002012f  add     rsp, 30h
0x180020133  pop     rdi
0x180020134  retn
0x180020135  mov     edx, 4Bh ; 'K'; void *
0x18002013a  mov     rcx, [rsp+38h]; this
0x18002013f  lea     r8, aOnecoreuapComC_0; "onecoreuap\\com\\coml2\\stg\\h\\df32.hx"...
0x180020146  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002014b  jmp     short loc_180020125
0x18002014d  mov     edx, 56h ; 'V'
0x180020152  jmp     short loc_18002013A
0x180020154  mov     edx, 55h ; 'U'
0x180020159  jmp     short loc_18002013A
0x18002015b  mov     edx, 4Fh ; 'O'
0x180020160  jmp     short loc_18002013A
0x180020162  mov     edx, 53h ; 'S'
0x180020167  jmp     short loc_18002013A
0x180020169  mov     edx, 57h ; 'W'
0x18002016e  jmp     short loc_18002013A
```
