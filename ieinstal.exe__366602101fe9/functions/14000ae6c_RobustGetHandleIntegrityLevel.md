# RobustGetHandleIntegrityLevel

- ea: `0x14000ae6c`
- end: `0x14000b0ce`
- name: `RobustGetHandleIntegrityLevel`
- size: `610`
- prototype: `__int64 __fastcall(HANDLE Handle, PSID *Sid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009900`
- `0x14000a4b0`

## callees

- `0x14000ae6c`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14000afdc`
- `ADVAPI32!GetLengthSid` at `0x14000b006`
- `ADVAPI32!GetLengthSid` at `0x14000afdc`
- `ADVAPI32!GetLengthSid` at `0x14000b006`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000aea7`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000af1b`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000aea7`
- `ADVAPI32!GetKernelObjectSecurity` at `0x14000af1b`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000b070`
- `ADVAPI32!ConvertStringSidToSidW` at `0x14000b070`
- `ADVAPI32!CopySid` at `0x14000b01a`
- `ADVAPI32!CopySid` at `0x14000b01a`
- `ADVAPI32!GetAce` at `0x14000afa6`
- `ADVAPI32!GetAce` at `0x14000afa6`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000af66`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000af66`
- `KERNEL32!LocalAlloc` at `0x14000aee4`
- `KERNEL32!LocalAlloc` at `0x14000afef`
- `KERNEL32!LocalAlloc` at `0x14000aee4`
- `KERNEL32!LocalAlloc` at `0x14000afef`
- `KERNEL32!LocalFree` at `0x14000b04a`
- `KERNEL32!LocalFree` at `0x14000b0a0`
- `KERNEL32!LocalFree` at `0x14000b04a`
- `KERNEL32!LocalFree` at `0x14000b0a0`
- `KERNEL32!GetLastError` at `0x14000aebe`
- `KERNEL32!GetLastError` at `0x14000af2b`
- `KERNEL32!GetLastError` at `0x14000b02f`
- `KERNEL32!GetLastError` at `0x14000b080`
- `KERNEL32!GetLastError` at `0x14000aebe`
- `KERNEL32!GetLastError` at `0x14000af2b`
- `KERNEL32!GetLastError` at `0x14000b02f`
- `KERNEL32!GetLastError` at `0x14000b080`

## pseudocode

```c
__int64 __fastcall RobustGetHandleIntegrityLevel(HANDLE Handle, PSID *Sid)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rdi
  char *v7; // r14
  DWORD LengthSid; // eax
  HLOCAL v9; // rsi
  DWORD v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  WINBOOL bSaclDefaulted; // [rsp+30h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+A0h] [rbp+50h] BYREF
  WINBOOL bSaclPresent; // [rsp+A8h] [rbp+58h] BYREF

  nLengthNeeded = 0;
  if ( GetKernelObjectSecurity(Handle, 0x10u, 0, 0, &nLengthNeeded) )
    return (unsigned int)-2147418113;
  *Sid = 0;
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
    goto LABEL_30;
LABEL_11:
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(v6, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_28;
  if ( bSaclPresent && pSacl && pSacl->AceCount )
  {
    pAce = 0;
    if ( GetAce(pSacl, 0, &pAce) )
    {
      if ( (*((_BYTE *)pAce + 1) & 8) != 0 )
      {
        v5 = -2147023556;
      }
      else
      {
        v7 = (char *)pAce + 8;
        if ( pAce == (LPVOID)-8LL )
        {
          v5 = -2147467259;
        }
        else
        {
          LengthSid = GetLengthSid(v7);
          v9 = LocalAlloc(0x40u, LengthSid);
          if ( v9 )
          {
            v10 = GetLengthSid(v7);
            if ( CopySid(v10, v9, v7) )
            {
              *Sid = v9;
            }
            else
            {
              v11 = GetLastError();
              v5 = v11;
              if ( v11 > 0 )
                v5 = (unsigned __int16)v11 | 0x80070000;
              LocalFree(v9);
            }
          }
          else
          {
            v5 = -2147024882;
          }
        }
      }
      goto LABEL_30;
    }
LABEL_28:
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_30;
  }
  if ( !ConvertStringSidToSidW(L"ME", Sid) )
    goto LABEL_28;
LABEL_30:
  if ( v6 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x14000ae6c  mov     [rsp-38h+arg_0], rbx
0x14000ae71  push    rbp
0x14000ae72  push    rsi
0x14000ae73  push    rdi
0x14000ae74  push    r12
0x14000ae76  push    r13
0x14000ae78  push    r14
0x14000ae7a  push    r15
0x14000ae7c  mov     rbp, rsp
0x14000ae7f  sub     rsp, 50h
0x14000ae83  xor     r12d, r12d
0x14000ae86  lea     rax, [rbp+nLengthNeeded]
0x14000ae8a  mov     r15, rdx
0x14000ae8d  mov     [rbp+nLengthNeeded], r12d
0x14000ae91  xor     r9d, r9d; nLength
0x14000ae94  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000ae99  xor     r8d, r8d; pSecurityDescriptor
0x14000ae9c  mov     rsi, rcx
0x14000ae9f  lea     r14d, [r12+10h]
0x14000aea4  mov     edx, r14d; RequestedInformation
0x14000aea7  call    cs:__imp_GetKernelObjectSecurity
0x14000aeae  nop     dword ptr [rax+rax+00h]
0x14000aeb3  test    eax, eax
0x14000aeb5  jnz     loc_14000B0AE
0x14000aebb  mov     [r15], r12
0x14000aebe  call    cs:__imp_GetLastError
0x14000aec5  nop     dword ptr [rax+rax+00h]
0x14000aeca  mov     ebx, eax
0x14000aecc  mov     r13d, 80070000h
0x14000aed2  cmp     eax, 7Ah ; 'z'
0x14000aed5  jz      short loc_14000AEDC
0x14000aed7  mov     edi, r12d
0x14000aeda  jmp     short loc_14000AF39
0x14000aedc  mov     edx, [rbp+nLengthNeeded]; uBytes
0x14000aedf  mov     ecx, 40h ; '@'; uFlags
0x14000aee4  call    cs:__imp_LocalAlloc
0x14000aeeb  nop     dword ptr [rax+rax+00h]
0x14000aef0  mov     rdi, rax
0x14000aef3  test    rax, rax
0x14000aef6  jnz     short loc_14000AF02
0x14000aef8  mov     ebx, 8007000Eh
0x14000aefd  jmp     loc_14000B0B3
0x14000af02  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14000af06  lea     rax, [rbp+nLengthNeeded]
0x14000af0a  mov     r8, rdi; pSecurityDescriptor
0x14000af0d  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14000af12  mov     edx, r14d; RequestedInformation
0x14000af15  mov     rcx, rsi; Handle
0x14000af18  mov     ebx, r12d
0x14000af1b  call    cs:__imp_GetKernelObjectSecurity
0x14000af22  nop     dword ptr [rax+rax+00h]
0x14000af27  test    eax, eax
0x14000af29  jnz     short loc_14000AF4B
0x14000af2b  call    cs:__imp_GetLastError
0x14000af32  nop     dword ptr [rax+rax+00h]
0x14000af37  mov     ebx, eax
0x14000af39  test    eax, eax
0x14000af3b  jle     short loc_14000AF43
0x14000af3d  movzx   ebx, ax
0x14000af40  or      ebx, r13d
0x14000af43  test    ebx, ebx
0x14000af45  jnz     loc_14000B098
0x14000af4b  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x14000af4f  mov     [rbp+pSacl], r12
0x14000af53  lea     r8, [rbp+pSacl]; pSacl
0x14000af57  mov     [rbp+bSaclPresent], r12d
0x14000af5b  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x14000af5f  mov     [rbp+bSaclDefaulted], r12d
0x14000af63  mov     rcx, rdi; pSecurityDescriptor
0x14000af66  call    cs:__imp_GetSecurityDescriptorSacl
0x14000af6d  nop     dword ptr [rax+rax+00h]
0x14000af72  test    eax, eax
0x14000af74  jz      loc_14000B080
0x14000af7a  cmp     [rbp+bSaclPresent], r12d
0x14000af7e  jz      loc_14000B066
0x14000af84  mov     rcx, [rbp+pSacl]; pAcl
0x14000af88  test    rcx, rcx
0x14000af8b  jz      loc_14000B066
0x14000af91  cmp     [rcx+4], r12w
0x14000af96  jz      loc_14000B066
0x14000af9c  lea     r8, [rbp+pAce]; pAce
0x14000afa0  mov     [rbp+pAce], r12
0x14000afa4  xor     edx, edx; dwAceIndex
0x14000afa6  call    cs:__imp_GetAce
0x14000afad  nop     dword ptr [rax+rax+00h]
0x14000afb2  test    eax, eax
0x14000afb4  jz      loc_14000B080
0x14000afba  mov     r14, [rbp+pAce]
0x14000afbe  test    byte ptr [r14+1], 8
0x14000afc3  jz      short loc_14000AFCF
0x14000afc5  mov     ebx, 8007053Ch
0x14000afca  jmp     loc_14000B098
0x14000afcf  add     r14, 8
0x14000afd3  jz      loc_14000B05F
0x14000afd9  mov     rcx, r14; pSid
0x14000afdc  call    cs:__imp_GetLengthSid
0x14000afe3  nop     dword ptr [rax+rax+00h]
0x14000afe8  mov     edx, eax; uBytes
0x14000afea  mov     ecx, 40h ; '@'; uFlags
0x14000afef  call    cs:__imp_LocalAlloc
0x14000aff6  nop     dword ptr [rax+rax+00h]
0x14000affb  mov     rsi, rax
0x14000affe  test    rax, rax
0x14000b001  jz      short loc_14000B058
0x14000b003  mov     rcx, r14; pSid
0x14000b006  call    cs:__imp_GetLengthSid
0x14000b00d  nop     dword ptr [rax+rax+00h]
0x14000b012  mov     r8, r14; pSourceSid
0x14000b015  mov     rdx, rsi; pDestinationSid
0x14000b018  mov     ecx, eax; nDestinationSidLength
0x14000b01a  call    cs:__imp_CopySid
0x14000b021  nop     dword ptr [rax+rax+00h]
0x14000b026  test    eax, eax
0x14000b028  jz      short loc_14000B02F
0x14000b02a  mov     [r15], rsi
0x14000b02d  jmp     short loc_14000B098
0x14000b02f  call    cs:__imp_GetLastError
0x14000b036  nop     dword ptr [rax+rax+00h]
0x14000b03b  mov     ebx, eax
0x14000b03d  test    eax, eax
0x14000b03f  jle     short loc_14000B047
0x14000b041  movzx   ebx, ax
0x14000b044  or      ebx, r13d
0x14000b047  mov     rcx, rsi; hMem
0x14000b04a  call    cs:__imp_LocalFree
0x14000b051  nop     dword ptr [rax+rax+00h]
0x14000b056  jmp     short loc_14000B098
0x14000b058  mov     ebx, 8007000Eh
0x14000b05d  jmp     short loc_14000B098
0x14000b05f  mov     ebx, 80004005h
0x14000b064  jmp     short loc_14000B098
0x14000b066  mov     rdx, r15; Sid
0x14000b069  lea     rcx, aMe; "ME"
0x14000b070  call    cs:__imp_ConvertStringSidToSidW
0x14000b077  nop     dword ptr [rax+rax+00h]
0x14000b07c  test    eax, eax
0x14000b07e  jnz     short loc_14000B098
0x14000b080  call    cs:__imp_GetLastError
0x14000b087  nop     dword ptr [rax+rax+00h]
0x14000b08c  mov     ebx, eax
0x14000b08e  test    eax, eax
0x14000b090  jle     short loc_14000B098
0x14000b092  movzx   ebx, ax
0x14000b095  or      ebx, r13d
0x14000b098  test    rdi, rdi
0x14000b09b  jz      short loc_14000B0B3
0x14000b09d  mov     rcx, rdi; hMem
0x14000b0a0  call    cs:__imp_LocalFree
0x14000b0a7  nop     dword ptr [rax+rax+00h]
0x14000b0ac  jmp     short loc_14000B0B3
0x14000b0ae  mov     ebx, 8000FFFFh
0x14000b0b3  mov     eax, ebx
0x14000b0b5  mov     rbx, [rsp+50h+arg_0]
0x14000b0bd  add     rsp, 50h
0x14000b0c1  pop     r15
0x14000b0c3  pop     r14
0x14000b0c5  pop     r13
0x14000b0c7  pop     r12
0x14000b0c9  pop     rdi
0x14000b0ca  pop     rsi
0x14000b0cb  pop     rbp
0x14000b0cc  retn
```
