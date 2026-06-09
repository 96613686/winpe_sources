# CAceList::CreateInstance(_ACL *,void *,CAceList * *,int)

- ea: `0x18000a800`
- end: `0x18000ac7b`
- name: `?CreateInstance@CAceList@@SAJPEAU_ACL@@PEAXPEAPEAV1@H@Z`
- size: `1147`
- prototype: `__int64 __fastcall(PACL pAcl, void *, struct CAceList **, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180056f7c`
- `0x18006de1c`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000a5f8`
- `0x18000a800`
- `0x18000bc00`
- `0x18000d1f0`
- `0x18000f4b0`
- `0x18000f7f0`
- `0x1800254e0`
- `0x1800259bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abdf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000aa73`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000aa73`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000a9db`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000a9db`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000a909`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000a909`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000a9ac`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000a9ac`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000aab0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000aab0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000aa84`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ac0e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000aa84`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ac0e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abd4`
- `ntdll!RtlMapGenericMask` at `0x18000aaea`
- `ntdll!RtlMapGenericMask` at `0x18000aaea`

## pseudocode

```c
__int64 __fastcall CAceList::CreateInstance(PACL pAcl, void *a2, struct CAceList **a3, int a4)
{
  PSECURITY_DESCRIPTOR v4; // r14
  struct _ACL *v5; // rbp
  struct CAceList **v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 (__fastcall *v11)(__int64, __int64, DWORD *); // rax
  __int64 v12; // rdi
  int v13; // eax
  signed int Error; // edi
  DWORD v15; // r12d
  char *v16; // r14
  _QWORD *v17; // rax
  DWORD *v18; // rsi
  unsigned __int8 v19; // r13
  char *v20; // rbp
  DWORD v21; // r12d
  HLOCAL v22; // rax
  void *v23; // r14
  char v24; // al
  char v25; // cl
  unsigned int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  signed int LastError; // eax
  DWORD LengthSid; // eax
  unsigned int v32; // edx
  WORD pControl[2]; // [rsp+40h] [rbp-88h] BYREF
  __int16 v34; // [rsp+44h] [rbp-84h]
  DWORD v35; // [rsp+48h] [rbp-80h]
  _QWORD *dwRevision; // [rsp+50h] [rbp-78h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-70h] BYREF
  struct CAceList **v38; // [rsp+60h] [rbp-68h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-60h]
  PACL pAcla; // [rsp+70h] [rbp-58h]
  __int64 pAclInformation; // [rsp+78h] [rbp-50h] BYREF
  int v42; // [rsp+80h] [rbp-48h]

  v4 = a2;
  pSecurityDescriptor = a2;
  v5 = pAcl;
  pAcla = pAcl;
  v38 = a3;
  v7 = a3;
  v8 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  pAce = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  v8[3] = 1;
  Error = CAceList::_Init((CAceList *)v8);
  if ( Error >= 0 && v5 )
  {
    pAclInformation = 0;
    v42 = 0;
    GetAclInformation(v5, &pAclInformation, 0xCu, AclSizeInformation);
    v15 = 0;
    v35 = 0;
    while ( 1 )
    {
      if ( v15 >= (unsigned int)pAclInformation )
      {
LABEL_12:
        v4 = pSecurityDescriptor;
        v7 = v38;
        goto LABEL_13;
      }
      pAce = 0;
      if ( !GetAce(v5, v15, &pAce) )
      {
        Error = ResultFromKnownLastError();
        goto LABEL_11;
      }
      v16 = (char *)pAce;
      Error = -2147024882;
      v17 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
      dwRevision = v17;
      v18 = (DWORD *)v17;
      if ( !v17 )
        goto LABEL_11;
      *v17 = 0x80000;
      v17[1] = 0;
      v17[2] = 0;
      v17[3] = 0;
      if ( !v16 )
      {
        Error = -2147024809;
LABEL_51:
        CAce::`scalar deleting destructor'((CAce *)v18, v32);
        goto LABEL_11;
      }
      v19 = *v16;
      v20 = v16 + 8;
      if ( *v16 != 9 )
        break;
      LengthSid = GetLengthSid(v16 + 8);
      Error = CAce::_Init(
                (CAce *)v18,
                v16 + 8,
                *((_DWORD *)v16 + 1),
                v16[1],
                *v16,
                *((_WORD *)v16 + 1),
                &v20[LengthSid]);
LABEL_39:
      if ( Error < 0 )
        goto LABEL_51;
      v27 = v18[7];
      v28 = v27 & 0x20;
      if ( (v27 & 0x20) != 0 )
      {
        v29 = v27 & 1;
      }
      else
      {
        v29 = v27 & 1;
        if ( !v29 )
        {
          Error = CAceList::_AddExplicitAceToDpa(v28, v9, v18);
          goto LABEL_10;
        }
      }
      if ( !(_DWORD)v28 && v29 )
      {
        Error = CAceList::_AddExplicitAceToDpa(v28, v9 + 1, v18);
      }
      else
      {
        v11 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        v12 = v9[2];
        if ( qword_1800959F8 == -1 )
        {
          GetProcFromComCtl32(&qword_1800959F8, 334);
          v11 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        }
        if ( v11 )
          v13 = v11(v12, 0x7FFFFFFF, v18);
        else
          v13 = -1;
        Error = 0;
        if ( v13 == -1 )
          Error = -2147024882;
      }
LABEL_10:
      if ( Error )
        goto LABEL_51;
LABEL_11:
      v5 = pAcla;
      v35 = ++v15;
      if ( Error < 0 )
        goto LABEL_12;
    }
    Error = -2147024809;
    if ( v16 == (char *)-8LL )
      goto LABEL_39;
    v34 = *((_WORD *)v16 + 1);
    LOBYTE(pControl[0]) = v16[1];
    LODWORD(dwRevision) = *((_DWORD *)v16 + 1);
    if ( IsValidSid(v16 + 8) )
    {
      v21 = GetLengthSid(v16 + 8);
      Error = -2147024882;
      v22 = LocalAlloc(0x40u, v21);
      v23 = v22;
      if ( v22 )
      {
        if ( CopySid(v21, v22, v20) )
        {
          Error = 0;
          goto LABEL_34;
        }
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
        {
LABEL_34:
          v24 = pControl[0];
          *((_QWORD *)v18 + 1) = v23;
          *((_BYTE *)v18 + 1) = v24;
          *((_WORD *)v18 + 1) = v34;
          v18[1] = (unsigned int)dwRevision;
          *(_BYTE *)v18 = v19;
          RtlMapGenericMask(v18 + 1, (PGENERIC_MAPPING)&GenericMapping);
          v25 = *(_BYTE *)v18;
          v18[7] = 0x80000000;
          if ( !v25 || (v26 = 0x80000000, v25 == 9) )
          {
            v18[7] = -2147483647;
            v26 = -2147483647;
          }
          if ( (*((_BYTE *)v18 + 1) & 0x10) != 0 )
            v18[7] = v26 | 0x20;
          goto LABEL_38;
        }
        LocalFree(v23);
      }
    }
LABEL_38:
    v15 = v35;
    goto LABEL_39;
  }
LABEL_13:
  if ( Error < 0 )
    goto LABEL_58;
  if ( v4 )
  {
    pControl[0] = 0;
    LODWORD(dwRevision) = 0;
    if ( GetSecurityDescriptorControl(v4, pControl, (LPDWORD)&dwRevision) )
    {
      if ( (pControl[0] & 0x1000) != 0 )
        *((_DWORD *)v9 + 6) = 0;
      *((_DWORD *)v9 + 7) = a4;
      goto LABEL_19;
    }
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Error < 0 )
  {
LABEL_58:
    CAceList::`scalar deleting destructor'((CAceList *)v9, v32);
    return (unsigned int)Error;
  }
LABEL_19:
  *v7 = (struct CAceList *)v9;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a800  push    rbx
0x18000a802  push    rbp
0x18000a803  push    rsi
0x18000a804  push    r14
0x18000a806  push    r15
0x18000a808  sub     rsp, 0A0h
0x18000a80f  mov     rax, cs:__security_cookie
0x18000a816  xor     rax, rsp
0x18000a819  mov     [rsp+0C8h+var_40], rax
0x18000a821  mov     r14, rdx
0x18000a824  mov     [rsp+0C8h+pSecurityDescriptor], rdx
0x18000a829  mov     rbp, rcx
0x18000a82c  mov     [rsp+0C8h+pAcl], rcx
0x18000a831  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a838  mov     [rsp+0C8h+var_68], r8
0x18000a83d  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a842  mov     r15d, r9d
0x18000a845  mov     rsi, r8
0x18000a848  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a84d  mov     [rsp+0C8h+pAce], rax
0x18000a852  mov     rbx, rax
0x18000a855  test    rax, rax
0x18000a858  jnz     loc_18000AB49
0x18000a85e  mov     eax, 8007000Eh
0x18000a863  jmp     loc_18000A940
0x18000a868  test    eax, eax
0x18000a86a  jnz     loc_18000AB91
0x18000a870  mov     rax, cs:qword_1800959F8
0x18000a877  mov     rdi, [rbx+10h]
0x18000a87b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a87f  jz      loc_18000AC4B
0x18000a885  test    rax, rax
0x18000a888  jz      loc_18000AC68
0x18000a88e  mov     r8, rsi
0x18000a891  mov     edx, 7FFFFFFFh
0x18000a896  mov     rcx, rdi
0x18000a899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89e  xor     edi, edi
0x18000a8a0  cmp     eax, 0FFFFFFFFh
0x18000a8a3  mov     eax, 8007000Eh
0x18000a8a8  cmovz   edi, eax
0x18000a8ab  test    edi, edi
0x18000a8ad  jnz     loc_18000ABA9
0x18000a8b3  mov     rbp, [rsp+0C8h+pAcl]
0x18000a8b8  inc     r12d
0x18000a8bb  mov     [rsp+0C8h+var_80], r12d
0x18000a8c0  mov     r13d, 0
0x18000a8c6  test    edi, edi
0x18000a8c8  jns     loc_18000A9C0
0x18000a8ce  mov     r14, [rsp+0C8h+pSecurityDescriptor]
0x18000a8d3  mov     rsi, [rsp+0C8h+var_68]
0x18000a8d8  mov     r12, [rsp+0C8h+var_30]
0x18000a8e0  test    edi, edi
0x18000a8e2  js      loc_18000ABF3
0x18000a8e8  test    r14, r14
0x18000a8eb  jz      loc_18000ABEB
0x18000a8f1  lea     r8, [rsp+0C8h+dwRevision]; lpdwRevision
0x18000a8f6  mov     [rsp+0C8h+pControl], r13w
0x18000a8fc  lea     rdx, [rsp+0C8h+pControl]; pControl
0x18000a901  mov     dword ptr [rsp+0C8h+dwRevision], r13d
0x18000a906  mov     rcx, r14; pSecurityDescriptor
0x18000a909  call    cs:__imp_GetSecurityDescriptorControl
0x18000a90f  test    eax, eax
0x18000a911  jz      loc_18000ABDF
0x18000a917  mov     eax, 1000h
0x18000a91c  test    [rsp+0C8h+pControl], ax
0x18000a921  jnz     loc_18000AC72
0x18000a927  mov     [rbx+1Ch], r15d
0x18000a92b  mov     [rsi], rbx
0x18000a92e  mov     eax, edi
0x18000a930  mov     rdi, [rsp+0C8h+arg_18]
0x18000a938  mov     r13, [rsp+0C8h+var_38]
0x18000a940  mov     rcx, [rsp+0C8h+var_40]
0x18000a948  xor     rcx, rsp; StackCookie
0x18000a94b  call    __security_check_cookie
0x18000a950  add     rsp, 0A0h
0x18000a957  pop     r15
0x18000a959  pop     r14
0x18000a95b  pop     rsi
0x18000a95c  pop     rbp
0x18000a95d  pop     rbx
0x18000a95e  retn
0x18000a95f  mov     rcx, rbx; this
0x18000a962  mov     [rsp+0C8h+arg_18], rdi
0x18000a96a  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000a96f  mov     edi, eax
0x18000a971  test    eax, eax
0x18000a973  js      loc_18000A8E0
0x18000a979  test    rbp, rbp
0x18000a97c  jz      loc_18000A8E0
0x18000a982  xor     eax, eax
0x18000a984  mov     [rsp+0C8h+var_30], r12
0x18000a98c  mov     r9d, 2; dwAclInformationClass
0x18000a992  mov     [rsp+0C8h+pAclInformation], rax
0x18000a997  mov     r8d, 0Ch; nAclInformationLength
0x18000a99d  mov     [rsp+0C8h+var_48], eax
0x18000a9a4  lea     rdx, [rsp+0C8h+pAclInformation]; pAclInformation
0x18000a9a9  mov     rcx, rbp; pAcl
0x18000a9ac  call    cs:__imp_GetAclInformation
0x18000a9b2  mov     r12d, r13d
0x18000a9b5  mov     [rsp+0C8h+var_80], r13d
0x18000a9ba  nop     word ptr [rax+rax+00h]
0x18000a9c0  cmp     r12d, dword ptr [rsp+0C8h+pAclInformation]
0x18000a9c5  jnb     loc_18000A8CE
0x18000a9cb  lea     r8, [rsp+0C8h+pAce]; pAce
0x18000a9d0  mov     [rsp+0C8h+pAce], r13
0x18000a9d5  mov     edx, r12d; dwAceIndex
0x18000a9d8  mov     rcx, rbp; pAcl
0x18000a9db  call    cs:__imp_GetAce
0x18000a9e1  test    eax, eax
0x18000a9e3  jz      loc_18000ABB6
0x18000a9e9  mov     r14, [rsp+0C8h+pAce]
0x18000a9ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a9f5  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a9fa  mov     edi, 8007000Eh
0x18000a9ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aa04  mov     [rsp+0C8h+dwRevision], rax
0x18000aa09  mov     rsi, rax
0x18000aa0c  test    rax, rax
0x18000aa0f  jz      loc_18000A8B3
0x18000aa15  mov     qword ptr [rax], 80000h
0x18000aa1c  mov     [rax+8], r13
0x18000aa20  mov     [rax+10h], r13
0x18000aa24  mov     qword ptr [rax+18h], 0
0x18000aa2c  test    r14, r14
0x18000aa2f  jz      loc_18000ABA4
0x18000aa35  movzx   r13d, byte ptr [r14]
0x18000aa39  lea     rbp, [r14+8]
0x18000aa3d  cmp     r13b, 9
0x18000aa41  jz      loc_18000AC0B
0x18000aa47  mov     edi, 80070057h
0x18000aa4c  test    rbp, rbp
0x18000aa4f  jz      loc_18000AB1B
0x18000aa55  movzx   eax, word ptr [r14+2]
0x18000aa5a  mov     rcx, rbp; pSid
0x18000aa5d  mov     [rsp+0C8h+var_84], ax
0x18000aa62  movzx   eax, byte ptr [r14+1]
0x18000aa67  mov     byte ptr [rsp+0C8h+pControl], al
0x18000aa6b  mov     eax, [r14+4]
0x18000aa6f  mov     dword ptr [rsp+0C8h+dwRevision], eax
0x18000aa73  call    cs:__imp_IsValidSid
0x18000aa79  test    eax, eax
0x18000aa7b  jz      loc_18000AB16
0x18000aa81  mov     rcx, rbp; pSid
0x18000aa84  call    cs:__imp_GetLengthSid
0x18000aa8a  mov     edx, eax; uBytes
0x18000aa8c  mov     ecx, 40h ; '@'; uFlags
0x18000aa91  mov     r12d, eax
0x18000aa94  mov     edi, 8007000Eh
0x18000aa99  call    cs:__imp_LocalAlloc
0x18000aa9f  mov     r14, rax
0x18000aaa2  test    rax, rax
0x18000aaa5  jz      short loc_18000AB16
0x18000aaa7  mov     r8, rbp; pSourceSid
0x18000aaaa  mov     rdx, rax; pDestinationSid
0x18000aaad  mov     ecx, r12d; nDestinationSidLength
0x18000aab0  call    cs:__imp_CopySid
0x18000aab6  test    eax, eax
0x18000aab8  jz      loc_18000ABC2
0x18000aabe  xor     edi, edi
0x18000aac0  movzx   eax, byte ptr [rsp+0C8h+pControl]
0x18000aac5  lea     rdx, GenericMapping; GenericMapping
0x18000aacc  mov     [rsi+8], r14
0x18000aad0  lea     rcx, [rsi+4]; AccessMask
0x18000aad4  mov     [rsi+1], al
0x18000aad7  movzx   eax, [rsp+0C8h+var_84]
0x18000aadc  mov     [rsi+2], ax
0x18000aae0  mov     eax, dword ptr [rsp+0C8h+dwRevision]
0x18000aae4  mov     [rsi+4], eax
0x18000aae7  mov     [rsi], r13b
0x18000aaea  call    cs:__imp_RtlMapGenericMask
0x18000aaf0  movzx   ecx, byte ptr [rsi]
0x18000aaf3  mov     dword ptr [rsi+1Ch], 80000000h
0x18000aafa  test    cl, cl
0x18000aafc  jnz     short loc_18000AB3D
0x18000aafe  mov     dword ptr [rsi+1Ch], 80000001h
0x18000ab05  mov     eax, 80000001h
0x18000ab0a  test    byte ptr [rsi+1], 10h
0x18000ab0e  jz      short loc_18000AB16
0x18000ab10  or      eax, 20h
0x18000ab13  mov     [rsi+1Ch], eax
0x18000ab16  mov     r12d, [rsp+0C8h+var_80]
0x18000ab1b  test    edi, edi
0x18000ab1d  js      loc_18000ABA9
0x18000ab23  mov     eax, [rsi+1Ch]
0x18000ab26  mov     ecx, eax
0x18000ab28  and     ecx, 20h
0x18000ab2b  jz      short loc_18000AB7A
0x18000ab2d  and     eax, 1
0x18000ab30  test    ecx, ecx
0x18000ab32  jnz     loc_18000A870
0x18000ab38  jmp     loc_18000A868
0x18000ab3d  mov     eax, 80000000h
0x18000ab42  cmp     cl, 9
0x18000ab45  jnz     short loc_18000AB0A
0x18000ab47  jmp     short loc_18000AAFE
0x18000ab49  mov     [rsp+0C8h+var_38], r13
0x18000ab51  xor     r13d, r13d
0x18000ab54  mov     [rax], r13
0x18000ab57  mov     [rax+8], r13
0x18000ab5b  mov     [rax+10h], r13
0x18000ab5f  mov     qword ptr [rax+18h], 1
0x18000ab67  test    rbx, rbx
0x18000ab6a  jnz     loc_18000A95F
0x18000ab70  mov     eax, 8007000Eh
0x18000ab75  jmp     loc_18000A938
0x18000ab7a  and     eax, 1
0x18000ab7d  jnz     short loc_18000AB30
0x18000ab7f  mov     r8, rsi
0x18000ab82  mov     rdx, rbx
0x18000ab85  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000ab8a  mov     edi, eax
0x18000ab8c  jmp     loc_18000A8AB
0x18000ab91  lea     rdx, [rbx+8]
0x18000ab95  mov     r8, rsi
0x18000ab98  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000ab9d  mov     edi, eax
0x18000ab9f  jmp     loc_18000A8AB
0x18000aba4  mov     edi, 80070057h
0x18000aba9  mov     rcx, rsi; this
0x18000abac  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000abb1  jmp     loc_18000A8B3
0x18000abb6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000abbb  mov     edi, eax
0x18000abbd  jmp     loc_18000A8B3
0x18000abc2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000abc7  mov     edi, eax
0x18000abc9  test    eax, eax
0x18000abcb  jns     loc_18000AAC0
0x18000abd1  mov     rcx, r14; hMem
0x18000abd4  call    cs:__imp_LocalFree
0x18000abda  jmp     loc_18000AB16
0x18000abdf  call    cs:__imp_GetLastError
0x18000abe5  mov     edi, eax
0x18000abe7  test    eax, eax
0x18000abe9  jg      short loc_18000AC00
0x18000abeb  test    edi, edi
0x18000abed  jns     loc_18000A92B
0x18000abf3  mov     rcx, rbx; this
0x18000abf6  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000abfb  jmp     loc_18000A92E
0x18000ac00  movzx   edi, ax
0x18000ac03  or      edi, 80070000h
0x18000ac09  jmp     short loc_18000ABEB
0x18000ac0b  mov     rcx, rbp; pSid
0x18000ac0e  call    cs:__imp_GetLengthSid
0x18000ac14  movzx   r9d, byte ptr [r14+1]; unsigned __int8
0x18000ac19  mov     rdx, rbp; void *
0x18000ac1c  mov     r8d, [r14+4]; unsigned int
0x18000ac20  mov     ecx, eax
0x18000ac22  movzx   eax, word ptr [r14+2]
0x18000ac27  add     rcx, rbp
0x18000ac2a  mov     [rsp+0C8h+var_98], rcx; void *
0x18000ac2f  mov     rcx, rsi; this
0x18000ac32  mov     [rsp+0C8h+var_A0], ax; unsigned __int16
0x18000ac37  movzx   eax, byte ptr [r14]
0x18000ac3b  mov     [rsp+0C8h+var_A8], al; unsigned __int8
0x18000ac3f  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x18000ac44  mov     edi, eax
0x18000ac46  jmp     loc_18000AB1B
0x18000ac4b  mov     edx, 14Eh
0x18000ac50  lea     rcx, qword_1800959F8
0x18000ac57  call    _GetProcFromComCtl32
0x18000ac5c  mov     rax, cs:qword_1800959F8
0x18000ac63  jmp     loc_18000A885
0x18000ac68  mov     eax, 0FFFFFFFFh
0x18000ac6d  jmp     loc_18000A89E
0x18000ac72  mov     [rbx+18h], r13d
0x18000ac76  jmp     loc_18000A927
```
