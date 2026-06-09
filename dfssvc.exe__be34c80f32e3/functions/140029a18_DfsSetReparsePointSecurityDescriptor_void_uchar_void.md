# DfsSetReparsePointSecurityDescriptor(void *,uchar,void *)

- ea: `0x140029a18`
- end: `0x140029bc2`
- name: `?DfsSetReparsePointSecurityDescriptor@@YAKPEAXE0@Z`
- size: `426`
- prototype: `unsigned int __fastcall(HANDLE handle, unsigned __int8, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400296d8`

## callees

- `0x140005a94`
- `0x140029a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029a7a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140029a6a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140029a6a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140029a96`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140029a96`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140029aba`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140029aba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140029b5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140029b5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140029ae4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x140029ae4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140029b47`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140029b47`

## pseudocode

```c
__int64 __fastcall DfsSetReparsePointSecurityDescriptor(HANDLE handle, char a2, void *a3)
{
  DWORD LastError; // eax
  SECURITY_INFORMATION v7; // r8d
  DWORD v8; // ebx
  WINBOOL bDaclDefaulted; // [rsp+40h] [rbp-20h] BYREF
  DWORD dwRevision; // [rsp+44h] [rbp-1Ch] BYREF
  PACL pDacl; // [rsp+48h] [rbp-18h] BYREF
  PSID Sid; // [rsp+50h] [rbp-10h] BYREF
  struct _ACL pAcl; // [rsp+58h] [rbp-8h] BYREF
  WORD pControl; // [rsp+90h] [rbp+30h] BYREF
  WINBOOL bDaclPresent; // [rsp+98h] [rbp+38h] BYREF

  pControl = 0;
  dwRevision = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pAcl = 0;
  pDacl = 0;
  Sid = 0;
  if ( a3 )
  {
    if ( !GetSecurityDescriptorDacl(a3, &bDaclPresent, &pDacl, &bDaclDefaulted)
      || !GetSecurityDescriptorControl(a3, &pControl, &dwRevision) )
    {
      goto LABEL_3;
    }
  }
  else if ( a2 )
  {
    if ( !InitializeAcl(&pAcl, 8u, 2u) )
    {
LABEL_3:
      LastError = GetLastError();
      goto LABEL_18;
    }
    bDaclPresent = 1;
    pDacl = &pAcl;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-3588172797-86763527-1375198215-2167056557-2705436887", &Sid) )
    goto LABEL_3;
  v7 = 1;
  if ( a3 || a2 )
  {
    if ( bDaclPresent )
      v7 = 5;
    if ( (pControl & 0x1000) != 0 )
      v7 |= 0x80000000;
    else
      v7 |= 0x20000000u;
  }
  LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, v7, Sid, 0, pDacl, 0);
LABEL_18:
  v8 = LastError;
  if ( Sid )
    LocalFree(Sid);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 92, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140029a18  mov     [rsp-18h+arg_0], rbx
0x140029a1d  mov     [rsp-18h+arg_8], rsi
0x140029a22  push    rbp
0x140029a23  push    rdi
0x140029a24  push    r14
0x140029a26  mov     rbp, rsp
0x140029a29  sub     rsp, 60h
0x140029a2d  xor     r14d, r14d
0x140029a30  mov     rbx, r8
0x140029a33  mov     [rbp+pControl], r14w
0x140029a38  mov     dil, dl
0x140029a3b  mov     [rbp+dwRevision], r14d
0x140029a3f  mov     rsi, rcx
0x140029a42  mov     [rbp+bDaclPresent], r14d
0x140029a46  mov     [rbp+bDaclDefaulted], r14d
0x140029a4a  mov     qword ptr [rbp+pAcl.AclRevision], r14
0x140029a4e  mov     [rbp+pDacl], r14
0x140029a52  mov     [rbp+Sid], r14
0x140029a56  test    r8, r8
0x140029a59  jz      short loc_140029AA8
0x140029a5b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x140029a5f  mov     rcx, rbx; pSecurityDescriptor
0x140029a62  lea     r8, [rbp+pDacl]; pDacl
0x140029a66  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140029a6a  call    cs:__imp_GetSecurityDescriptorDacl
0x140029a71  nop     dword ptr [rax+rax+00h]
0x140029a76  test    eax, eax
0x140029a78  jnz     short loc_140029A8B
0x140029a7a  call    cs:__imp_GetLastError
0x140029a81  nop     dword ptr [rax+rax+00h]
0x140029a86  jmp     loc_140029B53
0x140029a8b  lea     r8, [rbp+dwRevision]; lpdwRevision
0x140029a8f  mov     rcx, rbx; pSecurityDescriptor
0x140029a92  lea     rdx, [rbp+pControl]; pControl
0x140029a96  call    cs:__imp_GetSecurityDescriptorControl
0x140029a9d  nop     dword ptr [rax+rax+00h]
0x140029aa2  test    eax, eax
0x140029aa4  jnz     short loc_140029AD9
0x140029aa6  jmp     short loc_140029A7A
0x140029aa8  test    dil, dil
0x140029aab  jz      short loc_140029AD9
0x140029aad  mov     edx, 8; nAclLength
0x140029ab2  lea     rcx, [rbp+pAcl]; pAcl
0x140029ab6  lea     r8d, [rdx-6]; dwAclRevision
0x140029aba  call    cs:__imp_InitializeAcl
0x140029ac1  nop     dword ptr [rax+rax+00h]
0x140029ac6  test    eax, eax
0x140029ac8  jz      short loc_140029A7A
0x140029aca  lea     rax, [rbp+pAcl]
0x140029ace  mov     [rbp+bDaclPresent], 1
0x140029ad5  mov     [rbp+pDacl], rax
0x140029ad9  lea     rdx, [rbp+Sid]; Sid
0x140029add  lea     rcx, StringSid; "S-1-5-80-3588172797-86763527-1375198215"...
0x140029ae4  call    cs:__imp_ConvertStringSidToSidW
0x140029aeb  nop     dword ptr [rax+rax+00h]
0x140029af0  test    eax, eax
0x140029af2  jz      short loc_140029A7A
0x140029af4  mov     r8d, 1
0x140029afa  test    rbx, rbx
0x140029afd  jnz     short loc_140029B04
0x140029aff  test    dil, dil
0x140029b02  jz      short loc_140029B28
0x140029b04  cmp     [rbp+bDaclPresent], r14d
0x140029b08  mov     eax, 5
0x140029b0d  cmovnz  r8d, eax
0x140029b11  mov     eax, 1000h
0x140029b16  test    [rbp+pControl], ax
0x140029b1a  jz      short loc_140029B23
0x140029b1c  bts     r8d, 1Fh
0x140029b21  jmp     short loc_140029B28
0x140029b23  bts     r8d, 1Dh; SecurityInfo
0x140029b28  mov     rax, [rbp+pDacl]
0x140029b2c  mov     edx, 1; ObjectType
0x140029b31  mov     r9, [rbp+Sid]; psidOwner
0x140029b35  mov     rcx, rsi; handle
0x140029b38  mov     [rsp+60h+pSacl], r14; pSacl
0x140029b3d  mov     [rsp+60h+var_38], rax; pDacl
0x140029b42  mov     [rsp+60h+psidGroup], r14; psidGroup
0x140029b47  call    cs:__imp_SetSecurityInfo
0x140029b4e  nop     dword ptr [rax+rax+00h]
0x140029b53  mov     ebx, eax
0x140029b55  mov     rcx, [rbp+Sid]; hMem
0x140029b59  test    rcx, rcx
0x140029b5c  jz      short loc_140029B6A
0x140029b5e  call    cs:__imp_LocalFree
0x140029b65  nop     dword ptr [rax+rax+00h]
0x140029b6a  lea     rax, WPP_GLOBAL_Control
0x140029b71  cmp     cs:WPP_GLOBAL_Control, rax
0x140029b78  jz      short loc_140029BAA
0x140029b7a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140029b81  test    rcx, rcx
0x140029b84  jz      short loc_140029BAA
0x140029b86  test    byte ptr [rcx+1Ch], 20h
0x140029b8a  jz      short loc_140029BAA
0x140029b8c  cmp     byte ptr [rcx+19h], 2
0x140029b90  jb      short loc_140029BAA
0x140029b92  mov     rcx, [rcx+10h]
0x140029b96  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140029b9d  mov     edx, 5Ch ; '\'
0x140029ba2  mov     r9d, ebx
0x140029ba5  call    WPP_SF_D
0x140029baa  lea     r11, [rsp+60h+var_s0]
0x140029baf  mov     eax, ebx
0x140029bb1  mov     rbx, [r11+20h]
0x140029bb5  mov     rsi, [r11+28h]
0x140029bb9  mov     rsp, r11
0x140029bbc  pop     r14
0x140029bbe  pop     rdi
0x140029bbf  pop     rbp
0x140029bc0  retn
```
