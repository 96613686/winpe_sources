# SetHandleIntegrityLevel(void *,_SE_OBJECT_TYPE,void *,bool *,ulong)

- ea: `0x180044474`
- end: `0x180044693`
- name: `?SetHandleIntegrityLevel@@YAJPEAXW4_SE_OBJECT_TYPE@@0PEA_NK@Z`
- size: `543`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, enum _SE_OBJECT_TYPE@<edx>, void *@<r8>, bool *@<r9>, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800443d0`
- `0x180044400`
- `0x180064648`
- `0x1800649b0`
- `0x180065d80`

## callees

- `0x180044474`
- `0x18004469c`
- `0x1800647c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800445c8`
- `msvcrt!memcpy_s` at `0x1800445c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800445e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004465d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800445e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004465d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800445fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800445fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044604`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800444e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044596`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800444e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044596`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004455a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004455a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800445b0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800445b0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180044506`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180044506`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18004461a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18004461a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180044573`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180044573`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x180044527`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x180044527`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800445dc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800445dc`

## pseudocode

```c
__int64 __fastcall SetHandleIntegrityLevel(void *a1, enum _SE_OBJECT_TYPE a2, void *a3, bool *a4, unsigned int a5)
{
  signed int LastError; // ebx
  DWORD v9; // r14d
  bool v10; // sf
  struct _ACL *v12; // rax
  struct _ACL *v13; // rdi
  unsigned __int16 *v14; // rbp
  DWORD LengthSid; // eax
  struct _ACL *v16; // rax
  struct _ACL *v17; // rdi
  signed int v18; // eax
  signed int v19; // eax

  if ( a5 && GetMandatoryPolicy(a1) != (a5 | 1) || !IsIntegrityAlreadySet(a1, a3) )
  {
    v14 = 0;
    if ( IsValidSid(a3) )
    {
      LengthSid = GetLengthSid(a3);
      if ( LengthSid + 12 >= LengthSid && (v9 = LengthSid + 20, LengthSid + 20 >= LengthSid + 12) )
      {
        v12 = (struct _ACL *)LocalAlloc(0, v9);
        v13 = v12;
        if ( v12 )
        {
          if ( InitializeAcl(v12, v9, 4u) && AddMandatoryAce(v13, 4u, 3u, a5 | 1, a3) )
          {
            LastError = 0;
            v14 = (unsigned __int16 *)v13;
            goto LABEL_7;
          }
          LastError = GetLastError();
          v10 = LastError < 0;
          if ( !LastError )
          {
LABEL_8:
            if ( v10 )
              return (unsigned int)LastError;
            v16 = (struct _ACL *)LocalAlloc(0x40u, v14[1] + 40LL);
            v17 = v16;
            if ( !v16 )
            {
              LastError = -2147024882;
              goto LABEL_26;
            }
            if ( InitializeSecurityDescriptor(v16, 1u)
              && (memcpy_s(&v17[5], v14[1], v14, v14[1]), SetSecurityDescriptorSacl(v17, 1, v17 + 5, 0)) )
            {
              if ( SetKernelObjectSecurity(a1, 0x10u, v17) )
              {
                LastError = 0;
              }
              else
              {
                v19 = GetLastError();
                LastError = v19;
                if ( v19 > 0 )
                  LastError = (unsigned __int16)v19 | 0x80070000;
                if ( LastError < 0 )
                  goto LABEL_25;
              }
              if ( a4 )
                *a4 = 1;
            }
            else
            {
              v18 = GetLastError();
              LastError = v18;
              if ( v18 > 0 )
                LastError = (unsigned __int16)v18 | 0x80070000;
            }
LABEL_25:
            LocalFree(v17);
LABEL_26:
            LocalFree(v14);
            return (unsigned int)LastError;
          }
          LocalFree(v13);
        }
        else
        {
          LastError = GetLastError();
        }
        if ( LastError <= 0 )
          goto LABEL_7;
      }
      else
      {
        LOWORD(LastError) = 534;
      }
    }
    else
    {
      LOWORD(LastError) = 87;
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
    v10 = LastError < 0;
    goto LABEL_8;
  }
  return 0;
}

```

## disassembly

```asm
0x180044474  push    rbx
0x180044476  push    rbp
0x180044477  push    rsi
0x180044478  push    rdi
0x180044479  push    r12
0x18004447b  push    r13
0x18004447d  push    r14
0x18004447f  push    r15
0x180044481  sub     rsp, 38h
0x180044485  mov     esi, [rsp+78h+arg_20]
0x18004448c  mov     r12, r9
0x18004448f  mov     rbx, r8
0x180044492  mov     r15, rcx
0x180044495  test    esi, esi
0x180044497  jnz     loc_180044646
0x18004449d  mov     rdx, rbx; void *
0x1800444a0  mov     rcx, r15; void *
0x1800444a3  call    ?IsIntegrityAlreadySet@@YAHPEAX0@Z; IsIntegrityAlreadySet(void *,void *)
0x1800444a8  test    eax, eax
0x1800444aa  jz      loc_180044557
0x1800444b0  xor     ebx, ebx
0x1800444b2  jmp     short loc_1800444D0
0x1800444b4  lea     r14d, [rcx+8]
0x1800444b8  cmp     r14d, ecx
0x1800444bb  jnb     short loc_1800444E3
0x1800444bd  mov     ebx, 216h
0x1800444c2  movzx   ebx, bx
0x1800444c5  or      ebx, r13d
0x1800444c8  test    ebx, ebx
0x1800444ca  jns     loc_180044589
0x1800444d0  mov     eax, ebx
0x1800444d2  add     rsp, 38h
0x1800444d6  pop     r15
0x1800444d8  pop     r14
0x1800444da  pop     r13
0x1800444dc  pop     r12
0x1800444de  pop     rdi
0x1800444df  pop     rsi
0x1800444e0  pop     rbp
0x1800444e1  pop     rbx
0x1800444e2  retn
0x1800444e3  mov     edx, r14d; uBytes
0x1800444e6  xor     ecx, ecx; uFlags
0x1800444e8  call    cs:__imp_LocalAlloc
0x1800444ee  mov     rdi, rax
0x1800444f1  test    rax, rax
0x1800444f4  jz      loc_18004465D
0x1800444fa  mov     r8d, 4; dwAclRevision
0x180044500  mov     edx, r14d; nAclLength
0x180044503  mov     rcx, rax; pAcl
0x180044506  call    cs:__imp_InitializeAcl
0x18004450c  test    eax, eax
0x18004450e  jz      short loc_180044535
0x180044510  mov     edx, 4; dwAceRevision
0x180044515  mov     [rsp+78h+pLabelSid], rbx; pLabelSid
0x18004451a  or      esi, 1
0x18004451d  mov     rcx, rdi; pAcl
0x180044520  mov     r9d, esi; MandatoryPolicy
0x180044523  lea     r8d, [rdx-1]; AceFlags
0x180044527  call    cs:__imp_AddMandatoryAce
0x18004452d  test    eax, eax
0x18004452f  jnz     loc_18004463C
0x180044535  call    cs:__imp_GetLastError
0x18004453b  mov     ebx, eax
0x18004453d  test    eax, eax
0x18004453f  jz      short loc_1800444CA
0x180044541  mov     rcx, rdi; hMem
0x180044544  call    cs:__imp_LocalFree
0x18004454a  test    ebx, ebx
0x18004454c  jg      loc_1800444C2
0x180044552  jmp     loc_1800444C8
0x180044557  mov     rcx, rbx; pSid
0x18004455a  call    cs:__imp_IsValidSid
0x180044560  xor     ebp, ebp
0x180044562  mov     r13d, 80070000h
0x180044568  test    eax, eax
0x18004456a  jz      loc_18004466A
0x180044570  mov     rcx, rbx; pSid
0x180044573  call    cs:__imp_GetLengthSid
0x180044579  lea     ecx, [rax+0Ch]
0x18004457c  cmp     ecx, eax
0x18004457e  jb      loc_1800444BD
0x180044584  jmp     loc_1800444B4
0x180044589  movzx   edx, word ptr [rbp+2]
0x18004458d  mov     ecx, 40h ; '@'; uFlags
0x180044592  add     rdx, 28h ; '('; uBytes
0x180044596  call    cs:__imp_LocalAlloc
0x18004459c  mov     rdi, rax
0x18004459f  test    rax, rax
0x1800445a2  jz      loc_180044689
0x1800445a8  mov     edx, 1; dwRevision
0x1800445ad  mov     rcx, rax; pSecurityDescriptor
0x1800445b0  call    cs:__imp_InitializeSecurityDescriptor
0x1800445b6  test    eax, eax
0x1800445b8  jz      short loc_1800445E6
0x1800445ba  movzx   edx, word ptr [rbp+2]; DestinationSize
0x1800445be  lea     rcx, [rdi+28h]; Destination
0x1800445c2  mov     r9d, edx; SourceSize
0x1800445c5  mov     r8, rbp; Source
0x1800445c8  call    cs:__imp_memcpy_s
0x1800445ce  xor     r9d, r9d; bSaclDefaulted
0x1800445d1  lea     r8, [rdi+28h]; pSacl
0x1800445d5  mov     rcx, rdi; pSecurityDescriptor
0x1800445d8  lea     edx, [r9+1]; bSaclPresent
0x1800445dc  call    cs:__imp_SetSecurityDescriptorSacl
0x1800445e2  test    eax, eax
0x1800445e4  jnz     short loc_18004460F
0x1800445e6  call    cs:__imp_GetLastError
0x1800445ec  mov     ebx, eax
0x1800445ee  test    eax, eax
0x1800445f0  jle     short loc_1800445F8
0x1800445f2  movzx   ebx, ax
0x1800445f5  or      ebx, r13d
0x1800445f8  mov     rcx, rdi; hMem
0x1800445fb  call    cs:__imp_LocalFree
0x180044601  mov     rcx, rbp; hMem
0x180044604  call    cs:__imp_LocalFree
0x18004460a  jmp     loc_1800444D0
0x18004460f  mov     r8, rdi; SecurityDescriptor
0x180044612  mov     edx, 10h; SecurityInformation
0x180044617  mov     rcx, r15; Handle
0x18004461a  call    cs:__imp_SetKernelObjectSecurity
0x180044620  test    eax, eax
0x180044622  jnz     short loc_180044674
0x180044624  call    cs:__imp_GetLastError
0x18004462a  mov     ebx, eax
0x18004462c  test    eax, eax
0x18004462e  jle     short loc_180044636
0x180044630  movzx   ebx, ax
0x180044633  or      ebx, r13d
0x180044636  test    ebx, ebx
0x180044638  js      short loc_1800445F8
0x18004463a  jmp     short loc_180044676
0x18004463c  xor     ebx, ebx
0x18004463e  mov     rbp, rdi
0x180044641  jmp     loc_1800444C8
0x180044646  call    ?GetMandatoryPolicy@@YAKPEAX@Z; GetMandatoryPolicy(void *)
0x18004464b  mov     edx, esi
0x18004464d  or      edx, 1
0x180044650  cmp     eax, edx
0x180044652  jnz     loc_180044557
0x180044658  jmp     loc_18004449D
0x18004465d  call    cs:__imp_GetLastError
0x180044663  mov     ebx, eax
0x180044665  jmp     loc_18004454A
0x18004466a  mov     ebx, 57h ; 'W'
0x18004466f  jmp     loc_1800444C2
0x180044674  xor     ebx, ebx
0x180044676  test    r12, r12
0x180044679  jz      loc_1800445F8
0x18004467f  mov     byte ptr [r12], 1
0x180044684  jmp     loc_1800445F8
0x180044689  mov     ebx, 8007000Eh
0x18004468e  jmp     loc_180044601
```
