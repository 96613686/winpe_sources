# CopySecDesc(_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR * *)

- ea: `0x180129f20`
- end: `0x18012a2f1`
- name: `?CopySecDesc@@YAJPEAU_SECURITY_DESCRIPTOR@@PEAPEAU1@@Z`
- size: `977`
- prototype: `HRESULT __fastcall(_SECURITY_DESCRIPTOR *pOrig, _SECURITY_DESCRIPTOR **pCopy)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180111200`

## callees

- `0x1800865f4`
- `0x18008db2c`
- `0x180129f20`
- `0x1801457c0`
- `0x18014d5f4`
- `0x1801b2228`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a1ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012a2b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012a2b7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18012a2a3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18012a2a3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a1e3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a1e3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180129f63`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180129f63`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18012a0ac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18012a0ac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18012a138`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18012a138`

## string_xrefs

- `0x180129fb3`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012a00d`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012a07b`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012a1c3`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18012a272`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180129fac`: `CopySecDesc`
- `0x18012a002`: `CopySecDesc`
- `0x18012a06f`: `CopySecDesc`
- `0x18012a1bc`: `CopySecDesc`
- `0x18012a265`: `CopySecDesc`
- `0x18012a11b`: `No Owner Sid`
- `0x18012a1a7`: `No Group Sid`
- `0x18012a27c`: `AclRevision:%d`

## pseudocode

```c
__int64 __fastcall CopySecDesc(_SECURITY_DESCRIPTOR *pOrig, _SECURITY_DESCRIPTOR **pCopy)
{
  signed int LastError; // ebx
  int v5; // r8d
  const wchar_t *format; // rax
  int v8; // r8d
  _ACL *v9; // rax
  SIZE_T SecurityDescriptorLength; // rdi
  _SECURITY_DESCRIPTOR *v11; // rax
  int fDefaulted; // [rsp+40h] [rbp-20h] BYREF
  int fAclPresent; // [rsp+44h] [rbp-1Ch] BYREF
  int fAclDefaulted; // [rsp+48h] [rbp-18h] BYREF
  void *pSid; // [rsp+50h] [rbp-10h] BYREF
  _ACL *pAcl; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int16 control; // [rsp+90h] [rbp+30h] BYREF
  unsigned int dwRevision; // [rsp+98h] [rbp+38h] BYREF

  pSid = 0;
  fDefaulted = 0;
  fAclPresent = 0;
  fAclDefaulted = 0;
  pAcl = 0;
  dwRevision = 0;
  control = 0;
  if ( !GetSecurityDescriptorControl(pOrig, &control, &dwRevision) )
  {
    LastError = GetLastError();
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      v5 = 3698;
LABEL_6:
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CopySecDesc",
        v5,
        ERRORS,
        L"%!WINERROR!",
        LastError);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  if ( dwRevision != 1 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CopySecDesc",
        3709,
        ERRORS,
        L"SD Revision:%d",
        dwRevision);
    return 2147942487LL;
  }
  if ( (control & 0x8000) == 0 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
      ComTraceMessageT<unsigned short>(
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CopySecDesc",
        3714,
        ERRORS,
        L"SD control:%x",
        control);
    return 2147942487LL;
  }
  if ( GetSecurityDescriptorOwner(pOrig, &pSid, &fDefaulted) )
  {
    if ( pSid )
    {
      if ( !GetSecurityDescriptorGroup(pOrig, &pSid, &fDefaulted) )
      {
        LastError = GetLastError();
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        {
          v5 = 3741;
          goto LABEL_6;
        }
        goto LABEL_7;
      }
      if ( pSid )
      {
        if ( !GetSecurityDescriptorDacl(pOrig, &fAclPresent, &pAcl, &fAclDefaulted) )
        {
          LastError = GetLastError();
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          {
            v5 = 3757;
            goto LABEL_6;
          }
          goto LABEL_7;
        }
        if ( fAclPresent )
        {
          v9 = pAcl;
        }
        else
        {
          v9 = 0;
          pAcl = 0;
        }
        if ( !v9 || v9->AclRevision <= 4u )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(pOrig);
          v11 = (_SECURITY_DESCRIPTOR *)HeapAlloc(g_hHeap, 0, SecurityDescriptorLength);
          *pCopy = v11;
          if ( !v11 )
            return 2147942414LL;
          memcpy_0(v11, pOrig, SecurityDescriptorLength);
          return 0;
        }
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessage(
            -1,
            "onecore\\com\\combase\\dcomrem\\security.cxx",
            "CopySecDesc",
            3766,
            ERRORS,
            L"AclRevision:%d",
            pAcl->AclRevision);
        return 2147942487LL;
      }
      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
        return 2147942487LL;
      format = L"No Group Sid";
      v8 = 3746;
    }
    else
    {
      if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
        return 2147942487LL;
      format = L"No Owner Sid";
      v8 = 3730;
    }
    ComTraceMessageT<>("onecore\\com\\combase\\dcomrem\\security.cxx", "CopySecDesc", v8, ERRORS, format);
    return 2147942487LL;
  }
  LastError = GetLastError();
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    v5 = 3725;
    goto LABEL_6;
  }
LABEL_7:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180129f20  mov     [rsp-18h+arg_0], rbx
0x180129f25  mov     [rsp-18h+arg_8], rsi
0x180129f2a  push    rbp
0x180129f2b  push    rdi
0x180129f2c  push    r14
0x180129f2e  mov     rbp, rsp
0x180129f31  sub     rsp, 60h
0x180129f35  xor     r14d, r14d
0x180129f38  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180129f3c  mov     rsi, pCopy
0x180129f3f  mov     [rbp+pSid], r14
0x180129f43  lea     pCopy, [rbp+control]; pControl
0x180129f47  mov     [rbp+fDefaulted], r14d
0x180129f4b  mov     [rbp+fAclPresent], r14d
0x180129f4f  mov     rbx, pOrig
0x180129f52  mov     [rbp+fAclDefaulted], r14d
0x180129f56  mov     [rbp+pAcl], r14
0x180129f5a  mov     [rbp+dwRevision], r14d
0x180129f5e  mov     [rbp+control], r14w
0x180129f63  call    cs:__imp_GetSecurityDescriptorControl
0x180129f69  test    eax, eax
0x180129f6b  jnz     short loc_180129FD3
0x180129f6d  call    cs:__imp_GetLastError
0x180129f73  mov     ebx, eax
0x180129f75  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180129f7b  test    eax, eax
0x180129f7d  jnz     short loc_180129F93
0x180129f7f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180129f86  jz      short loc_180129FBF
0x180129f88  xor     ecx, ecx; level
0x180129f8a  call    IsWppLevelEnabled
0x180129f8f  test    al, al
0x180129f91  jz      short loc_180129FBF
0x180129f93  mov     r8d, 0E72h; line
0x180129f99  lea     rax, aWinerror; "%!WINERROR!"
0x180129fa0  mov     dword ptr [rsp+60h+var_38], ebx; <args_0>
0x180129fa4  xor     r9d, r9d; level
0x180129fa7  mov     [rsp+60h+format], rax; format
0x180129fac  lea     pCopy, aCopysecdesc; "CopySecDesc"
0x180129fb3  lea     pOrig, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180129fba  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x180129fbf  test    ebx, ebx
0x180129fc1  jle     short loc_180129FCC
0x180129fc3  movzx   ebx, bx
0x180129fc6  or      ebx, 80070000h
0x180129fcc  mov     eax, ebx
0x180129fce  jmp     loc_18012A2DC
0x180129fd3  cmp     [rbp+dwRevision], 1
0x180129fd7  jz      short loc_18012A033
0x180129fd9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180129fdf  test    eax, eax
0x180129fe1  jnz     short loc_180129FFF
0x180129fe3  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x180129fea  jz      loc_18012A299
0x180129ff0  xor     ecx, ecx; level
0x180129ff2  call    IsWppLevelEnabled
0x180129ff7  test    al, al
0x180129ff9  jz      loc_18012A299
0x180129fff  mov     eax, [rbp+dwRevision]
0x18012a002  lea     pCopy, aCopysecdesc; "CopySecDesc"
0x18012a009  mov     dword ptr [rsp+60h+var_38], eax; <args_0>
0x18012a00d  lea     pOrig, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18012a014  lea     rax, aSdRevisionD; "SD Revision:%d"
0x18012a01b  xor     r9d, r9d; level
0x18012a01e  mov     r8d, 0E7Dh; line
0x18012a024  mov     [rsp+60h+format], rax; format
0x18012a029  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18012a02e  jmp     loc_18012A299
0x18012a033  movzx   ecx, [rbp+control]
0x18012a037  mov     eax, 8000h
0x18012a03c  and     cx, ax
0x18012a03f  cmp     r14w, cx
0x18012a043  jnz     short loc_18012A0A1
0x18012a045  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a04b  test    eax, eax
0x18012a04d  jnz     short loc_18012A06B
0x18012a04f  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a056  jz      loc_18012A299
0x18012a05c  xor     ecx, ecx; level
0x18012a05e  call    IsWppLevelEnabled
0x18012a063  test    al, al
0x18012a065  jz      loc_18012A299
0x18012a06b  movzx   eax, [rbp+control]
0x18012a06f  lea     pCopy, aCopysecdesc; "CopySecDesc"
0x18012a076  mov     word ptr [rsp+60h+var_38], ax; <args_0>
0x18012a07b  lea     pOrig, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18012a082  lea     rax, aSdControlX; "SD control:%x"
0x18012a089  xor     r9d, r9d; level
0x18012a08c  mov     r8d, 0E82h; line
0x18012a092  mov     [rsp+60h+format], rax; format
0x18012a097  call    ??$ComTraceMessageT@G@@YAXPEBD0HW4TraceLevel@@PEBGG@Z; ComTraceMessageT<ushort>(char const *,char const *,int,TraceLevel,ushort const *,ushort)
0x18012a09c  jmp     loc_18012A299
0x18012a0a1  lea     r8, [rbp+fDefaulted]; lpbOwnerDefaulted
0x18012a0a5  mov     pOrig, rbx; pSecurityDescriptor
0x18012a0a8  lea     pCopy, [rbp+pSid]; pOwner
0x18012a0ac  call    cs:__imp_GetSecurityDescriptorOwner
0x18012a0b2  test    eax, eax
0x18012a0b4  jnz     short loc_18012A0EF
0x18012a0b6  call    cs:__imp_GetLastError
0x18012a0bc  mov     ebx, eax
0x18012a0be  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a0c4  test    eax, eax
0x18012a0c6  jnz     short loc_18012A0E4
0x18012a0c8  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a0cf  jz      loc_180129FBF
0x18012a0d5  xor     ecx, ecx; level
0x18012a0d7  call    IsWppLevelEnabled
0x18012a0dc  test    al, al
0x18012a0de  jz      loc_180129FBF
0x18012a0e4  mov     r8d, 0E8Dh
0x18012a0ea  jmp     loc_180129F99
0x18012a0ef  cmp     [rbp+pSid], r14
0x18012a0f3  jnz     short loc_18012A12D
0x18012a0f5  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a0fb  test    eax, eax
0x18012a0fd  jnz     short loc_18012A11B
0x18012a0ff  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a106  jz      loc_18012A299
0x18012a10c  xor     ecx, ecx; level
0x18012a10e  call    IsWppLevelEnabled
0x18012a113  test    al, al
0x18012a115  jz      loc_18012A299
0x18012a11b  lea     rax, aNoOwnerSid; "No Owner Sid"
0x18012a122  mov     r8d, 0E92h
0x18012a128  jmp     loc_18012A1B4
0x18012a12d  lea     r8, [rbp+fDefaulted]; lpbGroupDefaulted
0x18012a131  mov     pOrig, rbx; pSecurityDescriptor
0x18012a134  lea     pCopy, [rbp+pSid]; pGroup
0x18012a138  call    cs:__imp_GetSecurityDescriptorGroup
0x18012a13e  test    eax, eax
0x18012a140  jnz     short loc_18012A17B
0x18012a142  call    cs:__imp_GetLastError
0x18012a148  mov     ebx, eax
0x18012a14a  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a150  test    eax, eax
0x18012a152  jnz     short loc_18012A170
0x18012a154  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a15b  jz      loc_180129FBF
0x18012a161  xor     ecx, ecx; level
0x18012a163  call    IsWppLevelEnabled
0x18012a168  test    al, al
0x18012a16a  jz      loc_180129FBF
0x18012a170  mov     r8d, 0E9Dh
0x18012a176  jmp     loc_180129F99
0x18012a17b  cmp     [rbp+pSid], r14
0x18012a17f  jnz     short loc_18012A1D4
0x18012a181  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a187  test    eax, eax
0x18012a189  jnz     short loc_18012A1A7
0x18012a18b  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a192  jz      loc_18012A299
0x18012a198  xor     ecx, ecx; level
0x18012a19a  call    IsWppLevelEnabled
0x18012a19f  test    al, al
0x18012a1a1  jz      loc_18012A299
0x18012a1a7  lea     rax, aNoGroupSid; "No Group Sid"
0x18012a1ae  mov     r8d, 0EA2h; line
0x18012a1b4  xor     r9d, r9d; level
0x18012a1b7  mov     [rsp+60h+format], rax; format
0x18012a1bc  lea     pCopy, aCopysecdesc; "CopySecDesc"
0x18012a1c3  lea     pOrig, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18012a1ca  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18012a1cf  jmp     loc_18012A299
0x18012a1d4  lea     r9, [rbp+fAclDefaulted]; lpbDaclDefaulted
0x18012a1d8  mov     pOrig, rbx; pSecurityDescriptor
0x18012a1db  lea     r8, [rbp+pAcl]; pDacl
0x18012a1df  lea     pCopy, [rbp+fAclPresent]; lpbDaclPresent
0x18012a1e3  call    cs:__imp_GetSecurityDescriptorDacl
0x18012a1e9  test    eax, eax
0x18012a1eb  jnz     short loc_18012A226
0x18012a1ed  call    cs:__imp_GetLastError
0x18012a1f3  mov     ebx, eax
0x18012a1f5  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a1fb  test    eax, eax
0x18012a1fd  jnz     short loc_18012A21B
0x18012a1ff  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a206  jz      loc_180129FBF
0x18012a20c  xor     ecx, ecx; level
0x18012a20e  call    IsWppLevelEnabled
0x18012a213  test    al, al
0x18012a215  jz      loc_180129FBF
0x18012a21b  mov     r8d, 0EADh
0x18012a221  jmp     loc_180129F99
0x18012a226  cmp     [rbp+fAclPresent], r14d
0x18012a22a  jnz     short loc_18012A235
0x18012a22c  mov     rax, r14
0x18012a22f  mov     [rbp+pAcl], rax
0x18012a233  jmp     short loc_18012A239
0x18012a235  mov     rax, [rbp+pAcl]
0x18012a239  test    rax, rax
0x18012a23c  jz      short loc_18012A2A0
0x18012a23e  cmp     byte ptr [rax], 4
0x18012a241  jbe     short loc_18012A2A0
0x18012a243  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18012a249  test    eax, eax
0x18012a24b  jnz     short loc_18012A261
0x18012a24d  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x18012a254  jz      short loc_18012A299
0x18012a256  xor     ecx, ecx; level
0x18012a258  call    IsWppLevelEnabled
0x18012a25d  test    al, al
0x18012a25f  jz      short loc_18012A299
0x18012a261  mov     rax, [rbp+pAcl]
0x18012a265  lea     r8, aCopysecdesc; "CopySecDesc"
0x18012a26c  mov     r9d, 0EB6h; line
0x18012a272  lea     pCopy, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18012a279  movzx   ecx, byte ptr [rax]
0x18012a27c  lea     rax, aAclrevisionD; "AclRevision:%d"
0x18012a283  mov     [rsp+60h+var_30], ecx
0x18012a287  or      ecx, 0FFFFFFFFh; hr
0x18012a28a  mov     [rsp+60h+var_38], rax; format
0x18012a28f  mov     dword ptr [rsp+60h+format], r14d; level
0x18012a294  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18012a299  mov     eax, 80070057h
0x18012a29e  jmp     short loc_18012A2DC
0x18012a2a0  mov     pOrig, rbx; pSecurityDescriptor
0x18012a2a3  call    cs:__imp_GetSecurityDescriptorLength
0x18012a2a9  mov     pOrig, cs:?g_hHeap@@3QEAXEA; hHeap
0x18012a2b0  xor     edx, edx; dwFlags
0x18012a2b2  mov     r8d, eax; dwBytes
0x18012a2b5  mov     edi, eax
0x18012a2b7  call    cs:__imp_HeapAlloc
0x18012a2bd  mov     [rsi], rax
0x18012a2c0  test    rax, rax
0x18012a2c3  jnz     short loc_18012A2CC
0x18012a2c5  mov     eax, 8007000Eh
0x18012a2ca  jmp     short loc_18012A2DC
0x18012a2cc  mov     r8, rdi; Size
0x18012a2cf  mov     pCopy, rbx; Src
0x18012a2d2  mov     pOrig, rax; void *
0x18012a2d5  call    memcpy_0
0x18012a2da  xor     eax, eax
0x18012a2dc  lea     r11, [rsp+60h+var_s0]
0x18012a2e1  mov     rbx, [r11+20h]
0x18012a2e5  mov     rsi, [r11+28h]
0x18012a2e9  mov     rsp, r11
0x18012a2ec  pop     r14
0x18012a2ee  pop     rdi
0x18012a2ef  pop     rbp
0x18012a2f0  retn
```
