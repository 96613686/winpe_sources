# GetHandleIntegrityLevel(void *,void * *)

- ea: `0x180044850`
- end: `0x180044af6`
- name: `?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z`
- size: `678`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004469c`
- `0x180044724`

## callees

- `0x180044850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004489c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004489c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004495b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044aee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004495b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044aee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800448b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800449d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800448b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800449d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004490d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004490d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800449a0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800449a0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18004488e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800448e4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18004488e`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800448e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800449c8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800449f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800449c8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800449f3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180044a01`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180044a01`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044937`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044a77`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044937`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180044a77`

## pseudocode

```c
__int64 __fastcall GetHandleIntegrityLevel(HANDLE Handle, PSID *Sid)
{
  signed int LastError; // eax
  signed int v5; // ebx
  HLOCAL v6; // rsi
  PACL v7; // rcx
  signed int v8; // eax
  char v10; // r15
  WORD v11; // r14
  char *v12; // r12
  DWORD LengthSid; // eax
  HLOCAL v14; // rax
  void *v15; // rdi
  DWORD v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  PACL pSacl; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+88h] [rbp+48h] BYREF
  WINBOOL bSaclPresent; // [rsp+90h] [rbp+50h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+98h] [rbp+58h] BYREF

  *Sid = 0;
  nLengthNeeded = 0;
  if ( GetKernelObjectSecurity(Handle, 0x10u, 0, 0, &nLengthNeeded) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError == 122 )
  {
    v6 = LocalAlloc(0x40u, nLengthNeeded);
    if ( !v6 )
      return (unsigned int)-2147024882;
    v5 = 0;
    if ( GetKernelObjectSecurity(Handle, 0x10u, v6, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_5;
    LastError = GetLastError();
    v5 = LastError;
  }
  else
  {
    v6 = 0;
  }
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 )
    goto LABEL_12;
LABEL_5:
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_10;
  if ( bSaclPresent )
  {
    v7 = pSacl;
    if ( pSacl )
    {
      if ( pSacl->AceCount )
      {
        v10 = 0;
        v5 = 0;
        v11 = 0;
        while ( 1 )
        {
          if ( v10 )
            goto LABEL_12;
          if ( v11 >= v7->AceCount )
          {
            if ( !ConvertStringSidToSidW(L"ME", Sid) )
            {
              v17 = GetLastError();
              v5 = v17;
              if ( v17 > 0 )
                v5 = (unsigned __int16)v17 | 0x80070000;
            }
            goto LABEL_12;
          }
          pAce = 0;
          if ( !GetAce(v7, v11, &pAce) )
            goto LABEL_37;
          if ( *(_BYTE *)pAce != 17 )
            goto LABEL_25;
          if ( (*((_BYTE *)pAce + 1) & 8) != 0 )
          {
            v5 = -2147023556;
            goto LABEL_12;
          }
          v12 = (char *)pAce + 8;
          LengthSid = GetLengthSid((char *)pAce + 8);
          v14 = LocalAlloc(0x40u, LengthSid);
          v15 = v14;
          if ( v12 )
            break;
          if ( !v14 )
          {
LABEL_40:
            v5 = -2147024882;
            goto LABEL_12;
          }
LABEL_25:
          ++v11;
          if ( v5 < 0 )
            goto LABEL_12;
          v7 = pSacl;
        }
        if ( !v14 )
          goto LABEL_40;
        v16 = GetLengthSid(v12);
        if ( CopySid(v16, v15, v12) )
        {
          *Sid = v15;
          v10 = 1;
          goto LABEL_25;
        }
        LocalFree(v15);
LABEL_37:
        v18 = GetLastError();
        v5 = v18;
        if ( v18 > 0 )
          v5 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_25;
      }
    }
  }
  if ( !ConvertStringSidToSidW(L"ME", Sid) )
  {
LABEL_10:
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
  }
LABEL_12:
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044850  mov     [rsp-38h+arg_0], rbx
0x180044855  push    rbp
0x180044856  push    rsi
0x180044857  push    rdi
0x180044858  push    r12
0x18004485a  push    r13
0x18004485c  push    r14
0x18004485e  push    r15
0x180044860  mov     rbp, rsp
0x180044863  sub     rsp, 40h
0x180044867  xor     r12d, r12d
0x18004486a  lea     rax, [rbp+nLengthNeeded]
0x18004486e  mov     r13, rdx
0x180044871  mov     [rdx], r12
0x180044874  xor     r9d, r9d; nLength
0x180044877  mov     [rbp+nLengthNeeded], r12d
0x18004487b  xor     r8d, r8d; pSecurityDescriptor
0x18004487e  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180044883  lea     r15d, [r12+10h]
0x180044888  mov     rdi, rcx
0x18004488b  mov     edx, r15d; RequestedInformation
0x18004488e  call    cs:__imp_GetKernelObjectSecurity
0x180044894  test    eax, eax
0x180044896  jnz     loc_180044A48
0x18004489c  call    cs:__imp_GetLastError
0x1800448a2  mov     ebx, eax
0x1800448a4  mov     r14d, 80070000h
0x1800448aa  cmp     eax, 7Ah ; 'z'
0x1800448ad  jnz     loc_180044A2E
0x1800448b3  mov     edx, [rbp+nLengthNeeded]; uBytes
0x1800448b6  lea     ecx, [rax-3Ah]; uFlags
0x1800448b9  call    cs:__imp_LocalAlloc
0x1800448bf  mov     rsi, rax
0x1800448c2  test    rax, rax
0x1800448c5  jz      loc_180044AD4
0x1800448cb  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1800448cf  lea     rax, [rbp+nLengthNeeded]
0x1800448d3  mov     r8, rsi; pSecurityDescriptor
0x1800448d6  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800448db  mov     edx, r15d; RequestedInformation
0x1800448de  mov     rcx, rdi; Handle
0x1800448e1  mov     ebx, r12d
0x1800448e4  call    cs:__imp_GetKernelObjectSecurity
0x1800448ea  test    eax, eax
0x1800448ec  jz      loc_180044ADE
0x1800448f2  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x1800448f6  mov     [rbp+pSacl], r12
0x1800448fa  lea     r8, [rbp+pSacl]; pSacl
0x1800448fe  mov     [rbp+bSaclPresent], r12d
0x180044902  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180044906  mov     [rbp+bSaclDefaulted], r12d
0x18004490a  mov     rcx, rsi; pSecurityDescriptor
0x18004490d  call    cs:__imp_GetSecurityDescriptorSacl
0x180044913  test    eax, eax
0x180044915  jz      short loc_180044941
0x180044917  cmp     [rbp+bSaclPresent], r12d
0x18004491b  jz      short loc_18004492D
0x18004491d  mov     rcx, [rbp+pSacl]; pAcl
0x180044921  test    rcx, rcx
0x180044924  jz      short loc_18004492D
0x180044926  cmp     [rcx+4], r12w
0x18004492b  ja      short loc_18004497B
0x18004492d  mov     rdx, r13; Sid
0x180044930  lea     rcx, aMe; "ME"
0x180044937  call    cs:__imp_ConvertStringSidToSidW
0x18004493d  test    eax, eax
0x18004493f  jnz     short loc_180044953
0x180044941  call    cs:__imp_GetLastError
0x180044947  mov     ebx, eax
0x180044949  test    eax, eax
0x18004494b  jle     short loc_180044953
0x18004494d  movzx   ebx, ax
0x180044950  or      ebx, r14d
0x180044953  test    rsi, rsi
0x180044956  jz      short loc_180044961
0x180044958  mov     rcx, rsi; hMem
0x18004495b  call    cs:__imp_LocalFree
0x180044961  mov     eax, ebx
0x180044963  mov     rbx, [rsp+40h+arg_0]
0x18004496b  add     rsp, 40h
0x18004496f  pop     r15
0x180044971  pop     r14
0x180044973  pop     r13
0x180044975  pop     r12
0x180044977  pop     rdi
0x180044978  pop     rsi
0x180044979  pop     rbp
0x18004497a  retn
0x18004497b  mov     r15b, r12b
0x18004497e  mov     ebx, r12d
0x180044981  mov     r14d, r12d
0x180044984  test    r15b, r15b
0x180044987  jnz     short loc_180044953
0x180044989  cmp     r14w, [rcx+4]
0x18004498e  jnb     loc_180044A5C
0x180044994  movzx   edx, r14w; dwAceIndex
0x180044998  lea     r8, [rbp+pAce]; pAce
0x18004499c  mov     [rbp+pAce], r12
0x1800449a0  call    cs:__imp_GetAce
0x1800449a6  test    eax, eax
0x1800449a8  jz      loc_180044AA3
0x1800449ae  mov     rax, [rbp+pAce]
0x1800449b2  cmp     byte ptr [rax], 11h
0x1800449b5  jnz     short loc_180044A19
0x1800449b7  test    byte ptr [rax+1], 8
0x1800449bb  jnz     loc_180044A52
0x1800449c1  lea     r12, [rax+8]
0x1800449c5  mov     rcx, r12; pSid
0x1800449c8  call    cs:__imp_GetLengthSid
0x1800449ce  mov     edx, eax; uBytes
0x1800449d0  mov     ecx, 40h ; '@'; uFlags
0x1800449d5  call    cs:__imp_LocalAlloc
0x1800449db  mov     rdi, rax
0x1800449de  test    r12, r12
0x1800449e1  jz      loc_180044AC1
0x1800449e7  test    rax, rax
0x1800449ea  jz      loc_180044ACA
0x1800449f0  mov     rcx, r12; pSid
0x1800449f3  call    cs:__imp_GetLengthSid
0x1800449f9  mov     r8, r12; pSourceSid
0x1800449fc  mov     rdx, rdi; pDestinationSid
0x1800449ff  mov     ecx, eax; nDestinationSidLength
0x180044a01  call    cs:__imp_CopySid
0x180044a07  xor     r12d, r12d
0x180044a0a  test    eax, eax
0x180044a0c  jz      loc_180044AEB
0x180044a12  mov     [r13+0], rdi
0x180044a16  mov     r15b, 1
0x180044a19  inc     r14w
0x180044a1d  test    ebx, ebx
0x180044a1f  js      loc_180044953
0x180044a25  mov     rcx, [rbp+pSacl]
0x180044a29  jmp     loc_180044984
0x180044a2e  mov     rsi, r12
0x180044a31  test    eax, eax
0x180044a33  jle     short loc_180044A3B
0x180044a35  movzx   ebx, ax
0x180044a38  or      ebx, r14d
0x180044a3b  test    ebx, ebx
0x180044a3d  jnz     loc_180044953
0x180044a43  jmp     loc_1800448F2
0x180044a48  mov     ebx, 8000FFFFh
0x180044a4d  jmp     loc_180044961
0x180044a52  mov     ebx, 8007053Ch
0x180044a57  jmp     loc_180044953
0x180044a5c  test    ebx, ebx
0x180044a5e  js      loc_180044953
0x180044a64  test    r15b, r15b
0x180044a67  jnz     loc_180044953
0x180044a6d  mov     rdx, r13; Sid
0x180044a70  lea     rcx, aMe; "ME"
0x180044a77  call    cs:__imp_ConvertStringSidToSidW
0x180044a7d  test    eax, eax
0x180044a7f  jnz     loc_180044953
0x180044a85  call    cs:__imp_GetLastError
0x180044a8b  mov     ebx, eax
0x180044a8d  test    eax, eax
0x180044a8f  jle     loc_180044953
0x180044a95  movzx   ebx, ax
0x180044a98  or      ebx, 80070000h
0x180044a9e  jmp     loc_180044953
0x180044aa3  call    cs:__imp_GetLastError
0x180044aa9  mov     ebx, eax
0x180044aab  test    eax, eax
0x180044aad  jle     loc_180044A19
0x180044ab3  movzx   ebx, ax
0x180044ab6  or      ebx, 80070000h
0x180044abc  jmp     loc_180044A19
0x180044ac1  test    rdi, rdi
0x180044ac4  jnz     loc_180044A19
0x180044aca  mov     ebx, 8007000Eh
0x180044acf  jmp     loc_180044953
0x180044ad4  mov     ebx, 8007000Eh
0x180044ad9  jmp     loc_180044961
0x180044ade  call    cs:__imp_GetLastError
0x180044ae4  mov     ebx, eax
0x180044ae6  jmp     loc_180044A31
0x180044aeb  mov     rcx, rdi; hMem
0x180044aee  call    cs:__imp_LocalFree
0x180044af4  jmp     short loc_180044AA3
```
