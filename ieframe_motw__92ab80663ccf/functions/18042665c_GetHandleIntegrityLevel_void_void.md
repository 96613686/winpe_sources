# GetHandleIntegrityLevel(void *,void * *)

- ea: `0x18042665c`
- end: `0x1804268a1`
- name: `?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z`
- size: `581`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180427208`

## callees

- `0x18042665c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1804266d0`
- `KERNEL32!LocalAlloc` at `0x1804267d6`
- `KERNEL32!LocalAlloc` at `0x1804266d0`
- `KERNEL32!LocalAlloc` at `0x1804267d6`
- `KERNEL32!LocalFree` at `0x18042681e`
- `KERNEL32!LocalFree` at `0x180426872`
- `KERNEL32!LocalFree` at `0x18042681e`
- `KERNEL32!LocalFree` at `0x180426872`
- `KERNEL32!GetLastError` at `0x1804266aa`
- `KERNEL32!GetLastError` at `0x180426719`
- `KERNEL32!GetLastError` at `0x180426852`
- `KERNEL32!GetLastError` at `0x1804266aa`
- `KERNEL32!GetLastError` at `0x180426719`
- `KERNEL32!GetLastError` at `0x180426852`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1804267c3`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1804267f2`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1804267c3`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetLengthSid` at `0x1804267f2`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x180426696`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x180426709`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x180426696`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetKernelObjectSecurity` at `0x180426709`
- `api-ms-win-downlevel-advapi32-l1-1-0!CopySid` at `0x180426806`
- `api-ms-win-downlevel-advapi32-l1-1-0!CopySid` at `0x180426806`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetAce` at `0x180426794`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetAce` at `0x180426794`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetSecurityDescriptorSacl` at `0x180426754`
- `api-ms-win-downlevel-advapi32-l1-1-0!GetSecurityDescriptorSacl` at `0x180426754`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertStringSidToSidW` at `0x180426842`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertStringSidToSidW` at `0x180426842`

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
0x18042665c  mov     [rsp-28h+arg_0], rbx
0x180426661  mov     [rsp-28h+arg_8], rsi
0x180426666  push    rbp
0x180426667  push    rdi
0x180426668  push    r12
0x18042666a  push    r14
0x18042666c  push    r15
0x18042666e  mov     rbp, rsp
0x180426671  sub     rsp, 50h
0x180426675  xor     r12d, r12d
0x180426678  lea     rax, [rbp+nLengthNeeded]
0x18042667c  mov     r15, rdx
0x18042667f  mov     [rbp+nLengthNeeded], r12d
0x180426683  xor     r9d, r9d; nLength
0x180426686  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18042668b  xor     r8d, r8d; pSecurityDescriptor
0x18042668e  mov     rdi, rcx
0x180426691  lea     edx, [r12+10h]; RequestedInformation
0x180426696  call    cs:__imp_GetKernelObjectSecurity
0x18042669d  nop     dword ptr [rax+rax+00h]
0x1804266a2  test    eax, eax
0x1804266a4  jnz     loc_180426880
0x1804266aa  call    cs:__imp_GetLastError
0x1804266b1  nop     dword ptr [rax+rax+00h]
0x1804266b6  mov     ebx, eax
0x1804266b8  mov     r14d, 80070000h
0x1804266be  cmp     eax, 7Ah ; 'z'
0x1804266c1  jz      short loc_1804266C8
0x1804266c3  mov     esi, r12d
0x1804266c6  jmp     short loc_180426727
0x1804266c8  mov     edx, [rbp+nLengthNeeded]; uBytes
0x1804266cb  mov     ecx, 40h ; '@'; uFlags
0x1804266d0  call    cs:__imp_LocalAlloc
0x1804266d7  nop     dword ptr [rax+rax+00h]
0x1804266dc  mov     rsi, rax
0x1804266df  test    rax, rax
0x1804266e2  jnz     short loc_1804266EE
0x1804266e4  mov     ebx, 8007000Eh
0x1804266e9  jmp     loc_180426885
0x1804266ee  mov     r9d, [rbp+nLengthNeeded]; nLength
0x1804266f2  lea     rax, [rbp+nLengthNeeded]
0x1804266f6  mov     r8, rsi; pSecurityDescriptor
0x1804266f9  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1804266fe  mov     edx, 10h; RequestedInformation
0x180426703  mov     rcx, rdi; Handle
0x180426706  mov     ebx, r12d
0x180426709  call    cs:__imp_GetKernelObjectSecurity
0x180426710  nop     dword ptr [rax+rax+00h]
0x180426715  test    eax, eax
0x180426717  jnz     short loc_180426739
0x180426719  call    cs:__imp_GetLastError
0x180426720  nop     dword ptr [rax+rax+00h]
0x180426725  mov     ebx, eax
0x180426727  test    eax, eax
0x180426729  jle     short loc_180426731
0x18042672b  movzx   ebx, ax
0x18042672e  or      ebx, r14d
0x180426731  test    ebx, ebx
0x180426733  jnz     loc_18042686A
0x180426739  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x18042673d  mov     [rbp+pSacl], r12
0x180426741  lea     r8, [rbp+pSacl]; pSacl
0x180426745  mov     [rbp+bSaclPresent], r12d
0x180426749  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18042674d  mov     [rbp+bSaclDefaulted], r12d
0x180426751  mov     rcx, rsi; pSecurityDescriptor
0x180426754  call    cs:__imp_GetSecurityDescriptorSacl
0x18042675b  nop     dword ptr [rax+rax+00h]
0x180426760  test    eax, eax
0x180426762  jz      loc_180426852
0x180426768  cmp     [rbp+bSaclPresent], r12d
0x18042676c  jz      loc_180426838
0x180426772  mov     rcx, [rbp+pSacl]; pAcl
0x180426776  test    rcx, rcx
0x180426779  jz      loc_180426838
0x18042677f  cmp     [rcx+4], r12w
0x180426784  jbe     loc_180426838
0x18042678a  lea     r8, [rbp+pAce]; pAce
0x18042678e  mov     [rbp+pAce], r12
0x180426792  xor     edx, edx; dwAceIndex
0x180426794  call    cs:__imp_GetAce
0x18042679b  nop     dword ptr [rax+rax+00h]
0x1804267a0  test    eax, eax
0x1804267a2  jz      loc_180426852
0x1804267a8  mov     rax, [rbp+pAce]
0x1804267ac  test    byte ptr [rax+1], 8
0x1804267b0  jz      short loc_1804267BC
0x1804267b2  mov     ebx, 8007053Ch
0x1804267b7  jmp     loc_18042686A
0x1804267bc  lea     r14, [rax+8]
0x1804267c0  mov     rcx, r14; pSid
0x1804267c3  call    cs:__imp_GetLengthSid
0x1804267ca  nop     dword ptr [rax+rax+00h]
0x1804267cf  mov     edx, eax; uBytes
0x1804267d1  mov     ecx, 40h ; '@'; uFlags
0x1804267d6  call    cs:__imp_LocalAlloc
0x1804267dd  nop     dword ptr [rax+rax+00h]
0x1804267e2  mov     rdi, rax
0x1804267e5  test    r14, r14
0x1804267e8  jz      short loc_18042682C
0x1804267ea  test    rax, rax
0x1804267ed  jz      short loc_180426831
0x1804267ef  mov     rcx, r14; pSid
0x1804267f2  call    cs:__imp_GetLengthSid
0x1804267f9  nop     dword ptr [rax+rax+00h]
0x1804267fe  mov     r8, r14; pSourceSid
0x180426801  mov     rdx, rdi; pDestinationSid
0x180426804  mov     ecx, eax; nDestinationSidLength
0x180426806  call    cs:__imp_CopySid
0x18042680d  nop     dword ptr [rax+rax+00h]
0x180426812  test    eax, eax
0x180426814  jz      short loc_18042681B
0x180426816  mov     [r15], rdi
0x180426819  jmp     short loc_18042686A
0x18042681b  mov     rcx, rdi; hMem
0x18042681e  call    cs:__imp_LocalFree
0x180426825  nop     dword ptr [rax+rax+00h]
0x18042682a  jmp     short loc_18042686A
0x18042682c  test    rdi, rdi
0x18042682f  jnz     short loc_18042686A
0x180426831  mov     ebx, 8007000Eh
0x180426836  jmp     short loc_18042686A
0x180426838  mov     rdx, r15; Sid
0x18042683b  lea     rcx, StringSid; "ME"
0x180426842  call    cs:__imp_ConvertStringSidToSidW
0x180426849  nop     dword ptr [rax+rax+00h]
0x18042684e  test    eax, eax
0x180426850  jnz     short loc_18042686A
0x180426852  call    cs:__imp_GetLastError
0x180426859  nop     dword ptr [rax+rax+00h]
0x18042685e  mov     ebx, eax
0x180426860  test    eax, eax
0x180426862  jle     short loc_18042686A
0x180426864  movzx   ebx, ax
0x180426867  or      ebx, r14d
0x18042686a  test    rsi, rsi
0x18042686d  jz      short loc_180426885
0x18042686f  mov     rcx, rsi; hMem
0x180426872  call    cs:__imp_LocalFree
0x180426879  nop     dword ptr [rax+rax+00h]
0x18042687e  jmp     short loc_180426885
0x180426880  mov     ebx, 8000FFFFh
0x180426885  lea     r11, [rsp+50h+var_s0]
0x18042688a  mov     eax, ebx
0x18042688c  mov     rbx, [r11+30h]
0x180426890  mov     rsi, [r11+38h]
0x180426894  mov     rsp, r11
0x180426897  pop     r15
0x180426899  pop     r14
0x18042689b  pop     r12
0x18042689d  pop     rdi
0x18042689e  pop     rbp
0x18042689f  retn
```
