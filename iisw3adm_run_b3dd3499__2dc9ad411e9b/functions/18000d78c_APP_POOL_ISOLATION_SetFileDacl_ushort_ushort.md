# APP_POOL_ISOLATION::SetFileDacl(ushort *,ushort *)

- ea: `0x18000d78c`
- end: `0x18000d89d`
- name: `?SetFileDacl@APP_POOL_ISOLATION@@AEAAJPEAG0@Z`
- size: `273`
- prototype: `int(APP_POOL_ISOLATION *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000c0dc`

## callees

- `0x18000d78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d848`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000d83e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000d83e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d80a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d80a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d882`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000d882`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d7e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d7e2`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::SetFileDacl(
        APP_POOL_ISOLATION *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v4; // rcx
  PSECURITY_DESCRIPTOR *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  PACL pDacl; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v11; // [rsp+58h] [rbp-8h]
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+10h] BYREF
  int v13; // [rsp+74h] [rbp+14h]
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+28h] BYREF

  v13 = HIDWORD(this);
  v11 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  v4 = 24;
  v5 = SecurityDescriptor;
  *(_OWORD *)SecurityDescriptor = 0;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (PSECURITY_DESCRIPTOR *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, &SecurityDescriptor[1], 0) )
  {
LABEL_4:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError <= 0 )
      goto LABEL_6;
    goto LABEL_5;
  }
  LODWORD(SecurityDescriptor[0]) = 24;
  LODWORD(v11) = 0;
  if ( GetSecurityDescriptorDacl(SecurityDescriptor[1], &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v7 = 0;
    if ( bDaclPresent )
    {
      LastError = SetNamedSecurityInfoW(a3, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
      if ( LastError )
      {
        if ( LastError > 0 )
        {
LABEL_5:
          v7 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_6;
        }
        v7 = LastError;
      }
    }
  }
  else
  {
    if ( GetLastError() )
      goto LABEL_4;
    v7 = -2147467259;
  }
LABEL_6:
  if ( SecurityDescriptor[1] )
    LocalFree(SecurityDescriptor[1]);
  return v7;
}

```

## disassembly

```asm
0x18000d78c  mov     [rsp-8+arg_8], rbx
0x18000d791  mov     [rsp-8+arg_10], rdi
0x18000d796  mov     qword ptr [rsp-8+bDaclPresent], rcx
0x18000d79b  push    rbp
0x18000d79c  mov     rbp, rsp
0x18000d79f  sub     rsp, 60h
0x18000d7a3  xor     eax, eax
0x18000d7a5  xorps   xmm0, xmm0
0x18000d7a8  mov     [rbp+var_8], rax
0x18000d7ac  mov     rdi, r8
0x18000d7af  mov     [rbp+bDaclPresent], eax
0x18000d7b2  mov     r10, rdx
0x18000d7b5  mov     [rbp+bDaclDefaulted], eax
0x18000d7b8  lea     ebx, [rax+18h]
0x18000d7bb  mov     [rbp+pDacl], rax
0x18000d7bf  mov     ecx, ebx
0x18000d7c1  lea     rax, [rbp+SecurityDescriptor]
0x18000d7c5  movups  xmmword ptr [rbp+SecurityDescriptor], xmm0
0x18000d7c9  mov     byte ptr [rax], 0
0x18000d7cc  inc     rax
0x18000d7cf  sub     rcx, 1
0x18000d7d3  jnz     short loc_18000D7C9
0x18000d7d5  lea     edx, [rcx+1]; StringSDRevision
0x18000d7d8  xor     r9d, r9d; SecurityDescriptorSize
0x18000d7db  mov     rcx, r10; StringSecurityDescriptor
0x18000d7de  lea     r8, [rbp+SecurityDescriptor+8]; SecurityDescriptor
0x18000d7e2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000d7e8  test    eax, eax
0x18000d7ea  jnz     short loc_18000D824
0x18000d7ec  call    cs:__imp_GetLastError
0x18000d7f2  mov     ebx, eax
0x18000d7f4  test    eax, eax
0x18000d7f6  jle     short loc_18000D801
0x18000d7f8  movzx   ebx, ax
0x18000d7fb  or      ebx, 80070000h
0x18000d801  mov     rcx, [rbp+SecurityDescriptor+8]; hMem
0x18000d805  test    rcx, rcx
0x18000d808  jz      short loc_18000D810
0x18000d80a  call    cs:__imp_LocalFree
0x18000d810  lea     r11, [rsp+60h+var_s0]
0x18000d815  mov     eax, ebx
0x18000d817  mov     rbx, [r11+18h]
0x18000d81b  mov     rdi, [r11+20h]
0x18000d81f  mov     rsp, r11
0x18000d822  pop     rbp
0x18000d823  retn
0x18000d824  mov     rcx, [rbp+SecurityDescriptor+8]; pSecurityDescriptor
0x18000d828  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000d82c  lea     r8, [rbp+pDacl]; pDacl
0x18000d830  mov     dword ptr [rbp+SecurityDescriptor], ebx
0x18000d833  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000d837  mov     dword ptr [rbp+var_8], 0
0x18000d83e  call    cs:__imp_GetSecurityDescriptorDacl
0x18000d844  test    eax, eax
0x18000d846  jnz     short loc_18000D859
0x18000d848  call    cs:__imp_GetLastError
0x18000d84e  test    eax, eax
0x18000d850  jnz     short loc_18000D7EC
0x18000d852  mov     ebx, 80004005h
0x18000d857  jmp     short loc_18000D801
0x18000d859  xor     ebx, ebx
0x18000d85b  cmp     [rbp+bDaclPresent], ebx
0x18000d85e  jz      short loc_18000D801
0x18000d860  mov     rax, [rbp+pDacl]
0x18000d864  lea     edx, [rbx+1]; ObjectType
0x18000d867  mov     [rsp+60h+pSacl], rbx; pSacl
0x18000d86c  xor     r9d, r9d; psidOwner
0x18000d86f  mov     [rsp+60h+var_38], rax; pDacl
0x18000d874  mov     r8d, 80000004h; SecurityInfo
0x18000d87a  mov     rcx, rdi; pObjectName
0x18000d87d  mov     [rsp+60h+psidGroup], rbx; psidGroup
0x18000d882  call    cs:__imp_SetNamedSecurityInfoW
0x18000d888  test    eax, eax
0x18000d88a  jz      loc_18000D801
0x18000d890  jg      loc_18000D7F8
0x18000d896  mov     ebx, eax
0x18000d898  jmp     loc_18000D801
```
