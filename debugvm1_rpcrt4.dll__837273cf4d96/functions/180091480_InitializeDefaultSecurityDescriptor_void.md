# InitializeDefaultSecurityDescriptor(void)

- ea: `0x180091480`
- end: `0x1800915b5`
- name: `?InitializeDefaultSecurityDescriptor@@YAJXZ`
- size: `309`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18002499c`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18004f938`
- `0x180091480`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091502`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009157a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009157a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180091563`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180091563`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180091551`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180091551`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800914f8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800914f8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800914bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800914bb`

## pseudocode

```c
__int64 InitializeDefaultSecurityDescriptor(void)
{
  DWORD v0; // ebx
  struct _ACL *v1; // rsi
  void *v2; // rdi
  DWORD LastError; // eax
  unsigned int v4; // ebx
  _DWORD pSid[4]; // [rsp+20h] [rbp-28h] BYREF

  pSid[0] = 257;
  pSid[1] = 83886080;
  pSid[2] = 7;
  v0 = GetLengthSid(pSid) + 16;
  v1 = (struct _ACL *)AllocWrapper(v0);
  if ( v1 )
  {
    v2 = AllocWrapper(0x28u);
    if ( v2 )
    {
      if ( InitializeAcl(v1, v0, 2u)
        && AddAccessAllowedAce(v1, 2u, 0x80000000, pSid)
        && InitializeSecurityDescriptor(v2, 1u)
        && SetSecurityDescriptorDacl(v2, 1, v1, 0) )
      {
        LastError = RpcpNormalizeSecurityDescriptor(v2, 1u, &gDefaultSecurityDescriptor);
      }
      else
      {
        LastError = GetLastError();
      }
      v4 = LastError;
    }
    else
    {
      v4 = 14;
    }
    FreeWrapper(v1);
    if ( v2 )
      FreeWrapper(v2);
  }
  else
  {
    return 14;
  }
  return v4;
}

```

## disassembly

```asm
0x180091480  mov     [rsp+arg_0], rbx
0x180091485  mov     [rsp+arg_8], rsi
0x18009148a  push    rdi
0x18009148b  sub     rsp, 40h
0x18009148f  mov     rax, cs:__security_cookie
0x180091496  xor     rax, rsp
0x180091499  mov     [rsp+48h+var_18], rax
0x18009149e  lea     rcx, [rsp+48h+pSid]; pSid
0x1800914a3  mov     [rsp+48h+pSid], 101h
0x1800914ab  mov     [rsp+48h+var_24], 5000000h
0x1800914b3  mov     [rsp+48h+var_20], 7
0x1800914bb  call    cs:__imp_GetLengthSid
0x1800914c1  lea     ebx, [rax+10h]
0x1800914c4  mov     ecx, ebx; dwBytes
0x1800914c6  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800914cb  mov     rsi, rax
0x1800914ce  test    rax, rax
0x1800914d1  jz      loc_1800915A1
0x1800914d7  mov     ecx, 28h ; '('; dwBytes
0x1800914dc  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800914e1  mov     rdi, rax
0x1800914e4  test    rax, rax
0x1800914e7  jz      loc_1800915AB
0x1800914ed  mov     r8d, 2; dwAclRevision
0x1800914f3  mov     edx, ebx; nAclLength
0x1800914f5  mov     rcx, rsi; pAcl
0x1800914f8  call    cs:__imp_InitializeAcl
0x1800914fe  test    eax, eax
0x180091500  jnz     short loc_18009153E
0x180091502  call    cs:__imp_GetLastError
0x180091508  mov     ebx, eax
0x18009150a  mov     rcx, rsi; lpMem
0x18009150d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180091512  test    rdi, rdi
0x180091515  jz      short loc_18009151F
0x180091517  mov     rcx, rdi; lpMem
0x18009151a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009151f  mov     eax, ebx
0x180091521  mov     rcx, [rsp+48h+var_18]
0x180091526  xor     rcx, rsp; StackCookie
0x180091529  call    __security_check_cookie
0x18009152e  mov     rbx, [rsp+48h+arg_0]
0x180091533  mov     rsi, [rsp+48h+arg_8]
0x180091538  add     rsp, 40h
0x18009153c  pop     rdi
0x18009153d  retn
0x18009153e  lea     r9, [rsp+48h+pSid]; pSid
0x180091543  mov     edx, 2; dwAceRevision
0x180091548  mov     r8d, 80000000h; AccessMask
0x18009154e  mov     rcx, rsi; pAcl
0x180091551  call    cs:__imp_AddAccessAllowedAce
0x180091557  test    eax, eax
0x180091559  jz      short loc_180091502
0x18009155b  mov     edx, 1; dwRevision
0x180091560  mov     rcx, rdi; pSecurityDescriptor
0x180091563  call    cs:__imp_InitializeSecurityDescriptor
0x180091569  test    eax, eax
0x18009156b  jz      short loc_180091502
0x18009156d  xor     r9d, r9d; bDaclDefaulted
0x180091570  mov     r8, rsi; pDacl
0x180091573  mov     rcx, rdi; pSecurityDescriptor
0x180091576  lea     edx, [r9+1]; bDaclPresent
0x18009157a  call    cs:__imp_SetSecurityDescriptorDacl
0x180091580  test    eax, eax
0x180091582  jz      loc_180091502
0x180091588  lea     r8, ?gDefaultSecurityDescriptor@@3PEAXEA; void **
0x18009158f  mov     edx, 1; AutoInheritFlags
0x180091594  mov     rcx, rdi; CreatorDescriptor
0x180091597  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x18009159c  jmp     loc_180091508
0x1800915a1  mov     ebx, 0Eh
0x1800915a6  jmp     loc_18009151F
0x1800915ab  mov     ebx, 0Eh
0x1800915b0  jmp     loc_18009150A
```
