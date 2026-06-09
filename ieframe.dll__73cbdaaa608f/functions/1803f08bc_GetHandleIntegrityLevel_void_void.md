# GetHandleIntegrityLevel(void *,void * *)

- ea: `0x1803f08bc`
- end: `0x1803f0aa6`
- name: `?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z`
- size: `490`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803f1344`

## callees

- `0x1803f08bc`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1803f0924`
- `KERNEL32!LocalAlloc` at `0x1803f0a06`
- `KERNEL32!LocalAlloc` at `0x1803f0924`
- `KERNEL32!LocalAlloc` at `0x1803f0a06`
- `KERNEL32!LocalFree` at `0x1803f0a3c`
- `KERNEL32!LocalFree` at `0x1803f0a7e`
- `KERNEL32!LocalFree` at `0x1803f0a3c`
- `KERNEL32!LocalFree` at `0x1803f0a7e`
- `KERNEL32!GetLastError` at `0x1803f0904`
- `KERNEL32!GetLastError` at `0x1803f0961`
- `KERNEL32!GetLastError` at `0x1803f0a64`
- `KERNEL32!GetLastError` at `0x1803f0904`
- `KERNEL32!GetLastError` at `0x1803f0961`
- `KERNEL32!GetLastError` at `0x1803f0a64`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1803f09f9`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1803f0a1c`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1803f09f9`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1803f0a1c`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x1803f08f6`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x1803f0957`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x1803f08f6`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x1803f0957`
- `api-ms-win-downlevel-advapi32-l1-1-0!CopySid` at `0x1803f0a2a`
- `api-ms-win-downlevel-advapi32-l1-1-0!CopySid` at `0x1803f0a2a`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetAce` at `0x1803f09d0`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetAce` at `0x1803f09d0`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetSecurityDescriptorSacl` at `0x1803f0996`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetSecurityDescriptorSacl` at `0x1803f0996`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertStringSidToSidW` at `0x1803f0a5a`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertStringSidToSidW` at `0x1803f0a5a`

## pseudocode

```c
__int64 __fastcall GetHandleIntegrityLevel(HANDLE Handle, PSID *Sid)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rsi
  char *v7; // r14
  DWORD LengthSid; // eax
  HLOCAL v9; // rax
  void *v10; // rdi
  DWORD v11; // eax
  signed int v12; // eax
  WINBOOL bSaclDefaulted; // [rsp+30h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+90h] [rbp+40h] BYREF
  WINBOOL bSaclPresent; // [rsp+98h] [rbp+48h] BYREF

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
      goto LABEL_11;
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
    goto LABEL_28;
LABEL_11:
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_26;
  if ( !bSaclPresent || !pSacl || !pSacl->AceCount )
  {
    if ( ConvertStringSidToSidW(L"ME", Sid) )
      goto LABEL_28;
LABEL_26:
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_28;
  }
  pAce = 0;
  if ( !GetAce(pSacl, 0, &pAce) )
    goto LABEL_26;
  if ( (*((_BYTE *)pAce + 1) & 8) != 0 )
  {
    v5 = -2147023556;
    goto LABEL_28;
  }
  v7 = (char *)pAce + 8;
  LengthSid = GetLengthSid((char *)pAce + 8);
  v9 = LocalAlloc(0x40u, LengthSid);
  v10 = v9;
  if ( !v7 )
  {
    if ( v9 )
      goto LABEL_28;
    goto LABEL_24;
  }
  if ( !v9 )
  {
LABEL_24:
    v5 = -2147024882;
    goto LABEL_28;
  }
  v11 = GetLengthSid(v7);
  if ( CopySid(v11, v10, v7) )
    *Sid = v10;
  else
    LocalFree(v10);
LABEL_28:
  if ( v6 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1803f08bc  mov     [rsp-28h+arg_0], rbx
0x1803f08c1  mov     [rsp-28h+arg_8], rsi
0x1803f08c6  push    rbp
0x1803f08c7  push    rdi
0x1803f08c8  push    r12
0x1803f08ca  push    r14
0x1803f08cc  push    r15
0x1803f08ce  mov     rbp, rsp
0x1803f08d1  sub     rsp, 50h
0x1803f08d5  xor     r12d, r12d
0x1803f08d8  lea     rax, [rbp+nLengthNeeded]
0x1803f08dc  mov     r15, rdx
0x1803f08df  mov     [rbp+nLengthNeeded], r12d
0x1803f08e3  xor     r9d, r9d; nLength
0x1803f08e6  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1803f08eb  xor     r8d, r8d; pSecurityDescriptor
0x1803f08ee  mov     rdi, rcx
0x1803f08f1  lea     edx, [r12+10h]; RequestedInformation
0x1803f08f6  call    cs:__imp_GetKernelObjectSecurity
0x1803f08fc  test    eax, eax
0x1803f08fe  jnz     loc_1803F0A86
0x1803f0904  call    cs:__imp_GetLastError
0x1803f090a  mov     ebx, eax
0x1803f090c  mov     r14d, 80070000h
0x1803f0912  cmp     eax, 7Ah ; 'z'
0x1803f0915  jz      short loc_1803F091C
0x1803f0917  mov     esi, r12d
0x1803f091a  jmp     short loc_1803F0969
0x1803f091c  mov     edx, [rbp+nLengthNeeded]; uBytes
0x1803f091f  mov     ecx, 40h ; '@'; uFlags
0x1803f0924  call    cs:__imp_LocalAlloc
0x1803f092a  mov     rsi, rax
0x1803f092d  test    rax, rax
0x1803f0930  jnz     short loc_1803F093C
0x1803f0932  mov     ebx, 8007000Eh
0x1803f0937  jmp     loc_1803F0A8B
0x1803f093c  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1803f0940  lea     rax, [rbp+nLengthNeeded]
0x1803f0944  mov     r8, rsi; pSecurityDescriptor
0x1803f0947  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1803f094c  mov     edx, 10h; RequestedInformation
0x1803f0951  mov     rcx, rdi; Handle
0x1803f0954  mov     ebx, r12d
0x1803f0957  call    cs:__imp_GetKernelObjectSecurity
0x1803f095d  test    eax, eax
0x1803f095f  jnz     short loc_1803F097B
0x1803f0961  call    cs:__imp_GetLastError
0x1803f0967  mov     ebx, eax
0x1803f0969  test    eax, eax
0x1803f096b  jle     short loc_1803F0973
0x1803f096d  movzx   ebx, ax
0x1803f0970  or      ebx, r14d
0x1803f0973  test    ebx, ebx
0x1803f0975  jnz     loc_1803F0A76
0x1803f097b  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x1803f097f  mov     [rbp+pSacl], r12
0x1803f0983  lea     r8, [rbp+pSacl]; pSacl
0x1803f0987  mov     [rbp+bSaclPresent], r12d
0x1803f098b  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x1803f098f  mov     [rbp+bSaclDefaulted], r12d
0x1803f0993  mov     rcx, rsi; pSecurityDescriptor
0x1803f0996  call    cs:__imp_GetSecurityDescriptorSacl
0x1803f099c  test    eax, eax
0x1803f099e  jz      loc_1803F0A64
0x1803f09a4  cmp     [rbp+bSaclPresent], r12d
0x1803f09a8  jz      loc_1803F0A50
0x1803f09ae  mov     rcx, [rbp+pSacl]; pAcl
0x1803f09b2  test    rcx, rcx
0x1803f09b5  jz      loc_1803F0A50
0x1803f09bb  cmp     [rcx+4], r12w
0x1803f09c0  jbe     loc_1803F0A50
0x1803f09c6  lea     r8, [rbp+pAce]; pAce
0x1803f09ca  mov     [rbp+pAce], r12
0x1803f09ce  xor     edx, edx; dwAceIndex
0x1803f09d0  call    cs:__imp_GetAce
0x1803f09d6  test    eax, eax
0x1803f09d8  jz      loc_1803F0A64
0x1803f09de  mov     rax, [rbp+pAce]
0x1803f09e2  test    byte ptr [rax+1], 8
0x1803f09e6  jz      short loc_1803F09F2
0x1803f09e8  mov     ebx, 8007053Ch
0x1803f09ed  jmp     loc_1803F0A76
0x1803f09f2  lea     r14, [rax+8]
0x1803f09f6  mov     rcx, r14; pSid
0x1803f09f9  call    cs:__imp_GetLengthSid
0x1803f09ff  mov     edx, eax; uBytes
0x1803f0a01  mov     ecx, 40h ; '@'; uFlags
0x1803f0a06  call    cs:__imp_LocalAlloc
0x1803f0a0c  mov     rdi, rax
0x1803f0a0f  test    r14, r14
0x1803f0a12  jz      short loc_1803F0A44
0x1803f0a14  test    rax, rax
0x1803f0a17  jz      short loc_1803F0A49
0x1803f0a19  mov     rcx, r14; pSid
0x1803f0a1c  call    cs:__imp_GetLengthSid
0x1803f0a22  mov     r8, r14; pSourceSid
0x1803f0a25  mov     rdx, rdi; pDestinationSid
0x1803f0a28  mov     ecx, eax; nDestinationSidLength
0x1803f0a2a  call    cs:__imp_CopySid
0x1803f0a30  test    eax, eax
0x1803f0a32  jz      short loc_1803F0A39
0x1803f0a34  mov     [r15], rdi
0x1803f0a37  jmp     short loc_1803F0A76
0x1803f0a39  mov     rcx, rdi; hMem
0x1803f0a3c  call    cs:__imp_LocalFree
0x1803f0a42  jmp     short loc_1803F0A76
0x1803f0a44  test    rdi, rdi
0x1803f0a47  jnz     short loc_1803F0A76
0x1803f0a49  mov     ebx, 8007000Eh
0x1803f0a4e  jmp     short loc_1803F0A76
0x1803f0a50  mov     rdx, r15; Sid
0x1803f0a53  lea     rcx, StringSid; "ME"
0x1803f0a5a  call    cs:__imp_ConvertStringSidToSidW
0x1803f0a60  test    eax, eax
0x1803f0a62  jnz     short loc_1803F0A76
0x1803f0a64  call    cs:__imp_GetLastError
0x1803f0a6a  mov     ebx, eax
0x1803f0a6c  test    eax, eax
0x1803f0a6e  jle     short loc_1803F0A76
0x1803f0a70  movzx   ebx, ax
0x1803f0a73  or      ebx, r14d
0x1803f0a76  test    rsi, rsi
0x1803f0a79  jz      short loc_1803F0A8B
0x1803f0a7b  mov     rcx, rsi; hMem
0x1803f0a7e  call    cs:__imp_LocalFree
0x1803f0a84  jmp     short loc_1803F0A8B
0x1803f0a86  mov     ebx, 8000FFFFh
0x1803f0a8b  lea     r11, [rsp+50h+var_s0]
0x1803f0a90  mov     eax, ebx
0x1803f0a92  mov     rbx, [r11+30h]
0x1803f0a96  mov     rsi, [r11+38h]
0x1803f0a9a  mov     rsp, r11
0x1803f0a9d  pop     r15
0x1803f0a9f  pop     r14
0x1803f0aa1  pop     r12
0x1803f0aa3  pop     rdi
0x1803f0aa4  pop     rbp
0x1803f0aa5  retn
```
