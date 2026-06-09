# CCatalogServer::AddAccessAllowedACEToSd(_SECURITY_DESCRIPTOR *,void *,ulong)

- ea: `0x18000f048`
- end: `0x18000f194`
- name: `?AddAccessAllowedACEToSd@CCatalogServer@@AEAAJPEAU_SECURITY_DESCRIPTOR@@PEAXK@Z`
- size: `332`
- prototype: `__int64 __fastcall(CCatalogServer *this, struct _SECURITY_DESCRIPTOR *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000cd80`

## callees

- `0x180009098`
- `0x18000f048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f113`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f05f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f05f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000f08e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000f08e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000f0cd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000f0cd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000f109`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000f109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f06b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f06b`

## string_xrefs

- `0x18000f13d`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000f0ec`: `'AddAccessAllowedACEToSd:AddAccessAllowedAce'`
- `0x18000f128`: `AddAccessAllowedACEToSd:SetSecurityDescriptorDacl`
- `0x18000f0ad`: `'AddAccessAllowedACEToSd:InitializeAcl'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::AddAccessAllowedACEToSd(
        CCatalogServer *this,
        struct _SECURITY_DESCRIPTOR *a2,
        void *a3)
{
  signed int v5; // ebx
  struct _ACL *v6; // rax
  struct _ACL *v7; // rdi
  unsigned int v8; // ebx
  signed int v9; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  signed int v12; // eax
  signed int LastError; // eax
  unsigned int v15; // [rsp+20h] [rbp-30h] BYREF
  __int16 v16; // [rsp+24h] [rbp-2Ch]
  int v17; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-20h]
  __int64 v19; // [rsp+38h] [rbp-18h]
  __int64 v20; // [rsp+40h] [rbp-10h]
  int v21; // [rsp+48h] [rbp-8h]
  int v22; // [rsp+4Ch] [rbp-4h]

  v5 = GetLengthSid(a3) + 16;
  v6 = (struct _ACL *)CoTaskMemAlloc(v5);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
LABEL_16:
    CoTaskMemFree(v7);
    return v8;
  }
  if ( InitializeAcl(v6, v5, 2u) )
  {
    if ( AddAccessAllowedAce(v7, 2u, 0x1FFFFFu, a3) )
    {
      v8 = 0;
      if ( SetSecurityDescriptorDacl(a2, 1, v7, 0) )
        return v8;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v10 = L"AddAccessAllowedACEToSd:SetSecurityDescriptorDacl";
      v11 = 752;
    }
    else
    {
      v12 = GetLastError();
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      v10 = L"'AddAccessAllowedACEToSd:AddAccessAllowedAce'";
      v11 = 743;
    }
  }
  else
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    v10 = L"'AddAccessAllowedACEToSd:InitializeAcl'";
    v11 = 735;
  }
  v15 = v8;
  v16 = 22;
  v17 = -1073737001;
  v18 = v10;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 1;
  CError::WriteToLog((CError *)&v15, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v11, v10);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_16;
  return v8;
}

```

## disassembly

```asm
0x18000f048  push    rbp
0x18000f04a  push    rbx
0x18000f04b  push    rsi
0x18000f04c  push    rdi
0x18000f04d  push    r14
0x18000f04f  mov     rbp, rsp
0x18000f052  sub     rsp, 50h
0x18000f056  mov     rcx, r8; pSid
0x18000f059  mov     rsi, r8
0x18000f05c  mov     r14, rdx
0x18000f05f  call    cs:__imp_GetLengthSid
0x18000f065  lea     ebx, [rax+10h]
0x18000f068  movsxd  rcx, ebx; cb
0x18000f06b  call    cs:__imp_CoTaskMemAlloc
0x18000f071  mov     rdi, rax
0x18000f074  test    rax, rax
0x18000f077  jnz     short loc_18000F083
0x18000f079  mov     ebx, 8007000Eh
0x18000f07e  jmp     loc_18000F17E
0x18000f083  mov     r8d, 2; dwAclRevision
0x18000f089  mov     edx, ebx; nAclLength
0x18000f08b  mov     rcx, rdi; pAcl
0x18000f08e  call    cs:__imp_InitializeAcl
0x18000f094  test    eax, eax
0x18000f096  jnz     short loc_18000F0BC
0x18000f098  call    cs:__imp_GetLastError
0x18000f09e  mov     ebx, eax
0x18000f0a0  test    eax, eax
0x18000f0a2  jle     short loc_18000F0AD
0x18000f0a4  movzx   ebx, ax
0x18000f0a7  or      ebx, 80070000h
0x18000f0ad  lea     r9, aAddaccessallow; "'AddAccessAllowedACEToSd:InitializeAcl'"
0x18000f0b4  mov     r8d, 2DFh
0x18000f0ba  jmp     short loc_18000F135
0x18000f0bc  mov     r9, rsi; pSid
0x18000f0bf  mov     edx, 2; dwAceRevision
0x18000f0c4  mov     r8d, 1FFFFFh; AccessMask
0x18000f0ca  mov     rcx, rdi; pAcl
0x18000f0cd  call    cs:__imp_AddAccessAllowedAce
0x18000f0d3  test    eax, eax
0x18000f0d5  jnz     short loc_18000F0FB
0x18000f0d7  call    cs:__imp_GetLastError
0x18000f0dd  mov     ebx, eax
0x18000f0df  test    eax, eax
0x18000f0e1  jle     short loc_18000F0EC
0x18000f0e3  movzx   ebx, ax
0x18000f0e6  or      ebx, 80070000h
0x18000f0ec  lea     r9, aAddaccessallow_0; "'AddAccessAllowedACEToSd:AddAccessAllow"...
0x18000f0f3  mov     r8d, 2E7h
0x18000f0f9  jmp     short loc_18000F135
0x18000f0fb  xor     ebx, ebx
0x18000f0fd  xor     r9d, r9d; bDaclDefaulted
0x18000f100  mov     r8, rdi; pDacl
0x18000f103  mov     rcx, r14; pSecurityDescriptor
0x18000f106  lea     edx, [rbx+1]; bDaclPresent
0x18000f109  call    cs:__imp_SetSecurityDescriptorDacl
0x18000f10f  test    eax, eax
0x18000f111  jnz     short loc_18000F187
0x18000f113  call    cs:__imp_GetLastError
0x18000f119  mov     ebx, eax
0x18000f11b  test    eax, eax
0x18000f11d  jle     short loc_18000F128
0x18000f11f  movzx   ebx, ax
0x18000f122  or      ebx, 80070000h
0x18000f128  lea     r9, aAddaccessallow_1; "AddAccessAllowedACEToSd:SetSecurityDesc"...
0x18000f12f  mov     r8d, 2F0h; unsigned int
0x18000f135  mov     eax, 16h
0x18000f13a  mov     [rbp+var_30], ebx
0x18000f13d  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000f144  mov     [rbp+var_2C], ax
0x18000f148  lea     rcx, [rbp+var_30]; this
0x18000f14c  mov     [rbp+var_28], 0C00012D7h
0x18000f153  mov     [rbp+var_20], r9
0x18000f157  mov     [rbp+var_18], 0
0x18000f15f  mov     [rbp+var_10], 0
0x18000f167  mov     [rbp+var_8], 0
0x18000f16e  mov     [rbp+var_4], 1
0x18000f175  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000f17a  test    ebx, ebx
0x18000f17c  jns     short loc_18000F187
0x18000f17e  mov     rcx, rdi; pv
0x18000f181  call    cs:__imp_CoTaskMemFree
0x18000f187  mov     eax, ebx
0x18000f189  add     rsp, 50h
0x18000f18d  pop     r14
0x18000f18f  pop     rdi
0x18000f190  pop     rsi
0x18000f191  pop     rbx
0x18000f192  pop     rbp
0x18000f193  retn
```
