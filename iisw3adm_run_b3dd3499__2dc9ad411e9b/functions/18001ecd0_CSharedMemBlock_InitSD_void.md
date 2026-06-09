# CSharedMemBlock::InitSD(void)

- ea: `0x18001ecd0`
- end: `0x18001ef0a`
- name: `?InitSD@CSharedMemBlock@@QEAAJXZ`
- size: `570`
- prototype: `__int64 __fastcall(CSharedMemBlock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e7b0`
- `0x18001ebcc`

## callees

- `0x18001dd84`
- `0x18001ecd0`

## import_xrefs

- `msvcrt!malloc` at `0x18001ed93`
- `msvcrt!malloc` at `0x18001ed93`
- `msvcrt!free` at `0x18001eeef`
- `msvcrt!free` at `0x18001eeef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee81`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001edbb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001edbb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001ee61`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001ee61`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001ee77`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001ee77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eeb0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eebf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eece`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eedd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eeb0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eebf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eece`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001eedd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001eddf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001edfd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee17`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee31`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee4b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001eddf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001edfd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee17`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee31`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001ee4b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed4c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed59`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed66`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed73`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed80`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed4c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed59`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed66`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed73`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eea1`

## pseudocode

```c
__int64 __fastcall CSharedMemBlock::InitSD(CSharedMemBlock *this)
{
  bool v1; // zf
  struct _ACL *v4; // rbx
  signed int v5; // edi
  DWORD LengthSid; // r12d
  DWORD v7; // r12d
  DWORD v8; // r12d
  DWORD v9; // r12d
  DWORD v10; // r12d
  struct _ACL *v11; // rax
  struct _ACL *v12; // rsi
  signed int LastError; // eax
  PSID pSid; // [rsp+30h] [rbp-18h] BYREF
  PSID hMem; // [rsp+80h] [rbp+38h] BYREF
  PSID v16; // [rsp+88h] [rbp+40h] BYREF
  PSID v17; // [rsp+90h] [rbp+48h] BYREF
  PSID v18; // [rsp+98h] [rbp+50h] BYREF

  v1 = *((_QWORD *)this + 3) == 0;
  hMem = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  pSid = 0;
  if ( !v1 )
    return 0;
  v4 = 0;
  v5 = CSharedMemBlock::CreateSids(this, &v16, &v17, &hMem, &v18, &pSid);
  if ( v5 >= 0 )
  {
    LengthSid = GetLengthSid(pSid);
    v7 = GetLengthSid(v18) + LengthSid;
    v8 = GetLengthSid(v17) + v7;
    v9 = GetLengthSid(v16) + v8;
    v10 = GetLengthSid(hMem) + 48 + v9;
    v11 = (struct _ACL *)malloc(v10 + 40LL);
    v4 = v11;
    if ( v11 )
    {
      v12 = v11 + 5;
      if ( !InitializeAcl(v11 + 5, v10, 2u)
        || !AddAccessAllowedAce(v12, 2u, 0xC0100000, hMem)
        || !AddAccessAllowedAce(v12, 2u, 0xC0100000, v17)
        || !AddAccessAllowedAce(v12, 2u, 0xC0100000, v16)
        || !AddAccessAllowedAce(v12, 2u, 0x80100000, v18)
        || !AddAccessAllowedAce(v12, 2u, 0x80100000, pSid)
        || !InitializeSecurityDescriptor(v4, 1u)
        || !SetSecurityDescriptorDacl(v4, 1, v12, 0) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v16 )
    FreeSid(v16);
  if ( v17 )
    FreeSid(v17);
  if ( v18 )
    FreeSid(v18);
  if ( pSid )
    FreeSid(pSid);
  if ( v5 < 0 )
  {
    if ( v4 )
    {
      free(v4);
      v4 = 0;
    }
  }
  *((_QWORD *)this + 3) = v4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ecd0  push    rbp
0x18001ecd2  push    rbx
0x18001ecd3  push    rsi
0x18001ecd4  push    rdi
0x18001ecd5  push    r12
0x18001ecd7  push    r15
0x18001ecd9  mov     rbp, rsp
0x18001ecdc  sub     rsp, 48h
0x18001ece0  cmp     qword ptr [rcx+18h], 0
0x18001ece5  mov     r15, rcx
0x18001ece8  mov     [rbp+hMem], 0
0x18001ecf0  mov     [rbp+arg_8], 0
0x18001ecf8  mov     [rbp+arg_10], 0
0x18001ed00  mov     [rbp+arg_18], 0
0x18001ed08  mov     [rbp+pSid], 0
0x18001ed10  jz      short loc_18001ED19
0x18001ed12  xor     eax, eax
0x18001ed14  jmp     loc_18001EEFD
0x18001ed19  lea     rax, [rbp+pSid]
0x18001ed1d  xor     ebx, ebx
0x18001ed1f  mov     [rsp+48h+var_20], rax; void **
0x18001ed24  lea     r9, [rbp+hMem]; void **
0x18001ed28  lea     rax, [rbp+arg_18]
0x18001ed2c  lea     r8, [rbp+arg_10]; void **
0x18001ed30  mov     [rsp+48h+var_28], rax; void **
0x18001ed35  lea     rdx, [rbp+arg_8]; void **
0x18001ed39  call    ?CreateSids@CSharedMemBlock@@AEAAJPEAPEAX0000@Z; CSharedMemBlock::CreateSids(void * *,void * *,void * *,void * *,void * *)
0x18001ed3e  mov     edi, eax
0x18001ed40  test    eax, eax
0x18001ed42  js      loc_18001EE96
0x18001ed48  mov     rcx, [rbp+pSid]; pSid
0x18001ed4c  call    cs:__imp_GetLengthSid
0x18001ed52  mov     rcx, [rbp+arg_18]; pSid
0x18001ed56  mov     r12d, eax
0x18001ed59  call    cs:__imp_GetLengthSid
0x18001ed5f  mov     rcx, [rbp+arg_10]; pSid
0x18001ed63  add     r12d, eax
0x18001ed66  call    cs:__imp_GetLengthSid
0x18001ed6c  mov     rcx, [rbp+arg_8]; pSid
0x18001ed70  add     r12d, eax
0x18001ed73  call    cs:__imp_GetLengthSid
0x18001ed79  mov     rcx, [rbp+hMem]; pSid
0x18001ed7d  add     r12d, eax
0x18001ed80  call    cs:__imp_GetLengthSid
0x18001ed86  add     eax, 30h ; '0'
0x18001ed89  add     r12d, eax
0x18001ed8c  mov     ecx, r12d
0x18001ed8f  add     rcx, 28h ; '('; Size
0x18001ed93  call    cs:__imp_malloc
0x18001ed99  mov     rbx, rax
0x18001ed9c  test    rax, rax
0x18001ed9f  jnz     short loc_18001EDAB
0x18001eda1  mov     edi, 8007000Eh
0x18001eda6  jmp     loc_18001EE96
0x18001edab  lea     rsi, [rax+28h]
0x18001edaf  mov     r8d, 2; dwAclRevision
0x18001edb5  mov     rcx, rsi; pAcl
0x18001edb8  mov     edx, r12d; nAclLength
0x18001edbb  call    cs:__imp_InitializeAcl
0x18001edc1  test    eax, eax
0x18001edc3  jz      loc_18001EE81
0x18001edc9  mov     r9, [rbp+hMem]; pSid
0x18001edcd  mov     r12d, 2
0x18001edd3  mov     edx, r12d; dwAceRevision
0x18001edd6  mov     r8d, 0C0100000h; AccessMask
0x18001eddc  mov     rcx, rsi; pAcl
0x18001eddf  call    cs:__imp_AddAccessAllowedAce
0x18001ede5  test    eax, eax
0x18001ede7  jz      loc_18001EE81
0x18001eded  mov     r9, [rbp+arg_10]; pSid
0x18001edf1  mov     r8d, 0C0100000h; AccessMask
0x18001edf7  mov     edx, r12d; dwAceRevision
0x18001edfa  mov     rcx, rsi; pAcl
0x18001edfd  call    cs:__imp_AddAccessAllowedAce
0x18001ee03  test    eax, eax
0x18001ee05  jz      short loc_18001EE81
0x18001ee07  mov     r9, [rbp+arg_8]; pSid
0x18001ee0b  mov     r8d, 0C0100000h; AccessMask
0x18001ee11  mov     edx, r12d; dwAceRevision
0x18001ee14  mov     rcx, rsi; pAcl
0x18001ee17  call    cs:__imp_AddAccessAllowedAce
0x18001ee1d  test    eax, eax
0x18001ee1f  jz      short loc_18001EE81
0x18001ee21  mov     r9, [rbp+arg_18]; pSid
0x18001ee25  mov     r8d, 80100000h; AccessMask
0x18001ee2b  mov     edx, r12d; dwAceRevision
0x18001ee2e  mov     rcx, rsi; pAcl
0x18001ee31  call    cs:__imp_AddAccessAllowedAce
0x18001ee37  test    eax, eax
0x18001ee39  jz      short loc_18001EE81
0x18001ee3b  mov     r9, [rbp+pSid]; pSid
0x18001ee3f  mov     r8d, 80100000h; AccessMask
0x18001ee45  mov     edx, r12d; dwAceRevision
0x18001ee48  mov     rcx, rsi; pAcl
0x18001ee4b  call    cs:__imp_AddAccessAllowedAce
0x18001ee51  test    eax, eax
0x18001ee53  jz      short loc_18001EE81
0x18001ee55  mov     r12d, 1
0x18001ee5b  mov     rcx, rbx; pSecurityDescriptor
0x18001ee5e  mov     edx, r12d; dwRevision
0x18001ee61  call    cs:__imp_InitializeSecurityDescriptor
0x18001ee67  test    eax, eax
0x18001ee69  jz      short loc_18001EE81
0x18001ee6b  xor     r9d, r9d; bDaclDefaulted
0x18001ee6e  mov     r8, rsi; pDacl
0x18001ee71  mov     edx, r12d; bDaclPresent
0x18001ee74  mov     rcx, rbx; pSecurityDescriptor
0x18001ee77  call    cs:__imp_SetSecurityDescriptorDacl
0x18001ee7d  test    eax, eax
0x18001ee7f  jnz     short loc_18001EE96
0x18001ee81  call    cs:__imp_GetLastError
0x18001ee87  mov     edi, eax
0x18001ee89  test    eax, eax
0x18001ee8b  jle     short loc_18001EE96
0x18001ee8d  movzx   edi, ax
0x18001ee90  or      edi, 80070000h
0x18001ee96  cmp     [rbp+hMem], 0
0x18001ee9b  jz      short loc_18001EEA7
0x18001ee9d  mov     rcx, [rbp+hMem]; hMem
0x18001eea1  call    cs:__imp_LocalFree
0x18001eea7  mov     rcx, [rbp+arg_8]; pSid
0x18001eeab  test    rcx, rcx
0x18001eeae  jz      short loc_18001EEB6
0x18001eeb0  call    cs:__imp_FreeSid
0x18001eeb6  mov     rcx, [rbp+arg_10]; pSid
0x18001eeba  test    rcx, rcx
0x18001eebd  jz      short loc_18001EEC5
0x18001eebf  call    cs:__imp_FreeSid
0x18001eec5  mov     rcx, [rbp+arg_18]; pSid
0x18001eec9  test    rcx, rcx
0x18001eecc  jz      short loc_18001EED4
0x18001eece  call    cs:__imp_FreeSid
0x18001eed4  mov     rcx, [rbp+pSid]; pSid
0x18001eed8  test    rcx, rcx
0x18001eedb  jz      short loc_18001EEE3
0x18001eedd  call    cs:__imp_FreeSid
0x18001eee3  test    edi, edi
0x18001eee5  jns     short loc_18001EEF7
0x18001eee7  test    rbx, rbx
0x18001eeea  jz      short loc_18001EEF7
0x18001eeec  mov     rcx, rbx; Block
0x18001eeef  call    cs:__imp_free
0x18001eef5  xor     ebx, ebx
0x18001eef7  mov     [r15+18h], rbx
0x18001eefb  mov     eax, edi
0x18001eefd  add     rsp, 48h
0x18001ef01  pop     r15
0x18001ef03  pop     r12
0x18001ef05  pop     rdi
0x18001ef06  pop     rsi
0x18001ef07  pop     rbx
0x18001ef08  pop     rbp
0x18001ef09  retn
```
