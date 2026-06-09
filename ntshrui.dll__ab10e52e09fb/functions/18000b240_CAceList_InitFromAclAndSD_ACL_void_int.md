# CAceList::_InitFromAclAndSD(_ACL *,void *,int)

- ea: `0x18000b240`
- end: `0x18000b658`
- name: `?_InitFromAclAndSD@CAceList@@AEAAJPEAU_ACL@@PEAXH@Z`
- size: `1048`
- prototype: `int(CAceList *__hidden this, struct _ACL *, void *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d380`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000a5f8`
- `0x18000b240`
- `0x18000bc00`
- `0x18000f4b0`
- `0x18000f7f0`
- `0x1800254e0`
- `0x1800259bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5cf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b399`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b399`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000b30b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000b30b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b510`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b510`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000b2d6`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000b2d6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b3d6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b3d6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b3aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b5ed`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b3aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b5ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b5c4`
- `ntdll!RtlMapGenericMask` at `0x18000b40c`
- `ntdll!RtlMapGenericMask` at `0x18000b40c`

## pseudocode

```c
int __fastcall CAceList::_InitFromAclAndSD(CAceList *this, struct _ACL *a2, void *a3, DWORD a4)
{
  DWORD v4; // ebp
  struct _ACL *v5; // rbx
  void *v6; // rsi
  CAceList *v7; // r13
  int Error; // edi
  DWORD v9; // r15d
  char *v10; // rsi
  _QWORD *v11; // rax
  unsigned int v12; // edx
  DWORD *v13; // rbx
  unsigned __int8 v14; // r12
  char *v15; // rbp
  __int16 v16; // r13
  DWORD v17; // r15d
  HLOCAL v18; // rax
  void *v19; // rsi
  char v20; // al
  char v21; // cl
  unsigned int v22; // eax
  DWORD v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 (__fastcall *v26)(__int64, __int64, DWORD *); // rax
  __int64 v27; // rdi
  int v28; // eax
  int result; // eax
  DWORD LengthSid; // eax
  WORD pControl[2]; // [rsp+40h] [rbp-88h] BYREF
  DWORD dwRevision; // [rsp+44h] [rbp-84h] BYREF
  DWORD v33; // [rsp+48h] [rbp-80h]
  struct _ACL *v34; // [rsp+50h] [rbp-78h]
  _QWORD *v35; // [rsp+58h] [rbp-70h]
  LPVOID pAce; // [rsp+60h] [rbp-68h] BYREF
  CAceList *v37; // [rsp+68h] [rbp-60h]
  void *v38; // [rsp+70h] [rbp-58h]
  __int64 pAclInformation; // [rsp+78h] [rbp-50h] BYREF
  int v40; // [rsp+80h] [rbp-48h]

  v4 = a4;
  v5 = a2;
  dwRevision = a4;
  v6 = a3;
  v38 = a3;
  v34 = a2;
  v7 = this;
  v37 = this;
  Error = CAceList::_Init(this);
  if ( Error >= 0 && v5 )
  {
    pAclInformation = 0;
    v40 = 0;
    GetAclInformation(v5, &pAclInformation, 0xCu, AclSizeInformation);
    v9 = 0;
    v33 = 0;
    while ( 1 )
    {
      if ( v9 >= (unsigned int)pAclInformation )
      {
LABEL_33:
        v6 = v38;
        v4 = dwRevision;
        goto LABEL_34;
      }
      pAce = 0;
      if ( !GetAce(v5, v9, &pAce) )
      {
        Error = ResultFromKnownLastError();
        goto LABEL_32;
      }
      v10 = (char *)pAce;
      Error = -2147024882;
      v11 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
      v35 = v11;
      v13 = (DWORD *)v11;
      if ( !v11 )
        goto LABEL_31;
      *v11 = 0x80000;
      v11[1] = 0;
      v11[2] = 0;
      v11[3] = 0;
      if ( !v10 )
      {
        Error = -2147024809;
LABEL_48:
        CAce::`scalar deleting destructor'((CAce *)v13, v12);
        goto LABEL_31;
      }
      v14 = *v10;
      v15 = v10 + 8;
      if ( *v10 != 9 )
        break;
      LengthSid = GetLengthSid(v10 + 8);
      Error = CAce::_Init(
                (CAce *)v13,
                v10 + 8,
                *((_DWORD *)v10 + 1),
                v10[1],
                *v10,
                *((_WORD *)v10 + 1),
                &v15[LengthSid]);
LABEL_19:
      if ( Error < 0 )
        goto LABEL_48;
      v23 = v13[7];
      v24 = v23 & 0x20;
      if ( (v23 & 0x20) != 0 )
      {
        v25 = v23 & 1;
      }
      else
      {
        v25 = v23 & 1;
        if ( !v25 )
        {
          Error = CAceList::_AddExplicitAceToDpa(v24, v7, v13);
          goto LABEL_30;
        }
      }
      if ( !(_DWORD)v24 && v25 )
      {
        Error = CAceList::_AddExplicitAceToDpa(v24, (char *)v7 + 8, v13);
      }
      else
      {
        v26 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        v27 = *((_QWORD *)v7 + 2);
        if ( qword_1800959F8 == -1 )
        {
          GetProcFromComCtl32(&qword_1800959F8, 334);
          v26 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        }
        if ( v26 )
          v28 = v26(v27, 0x7FFFFFFF, v13);
        else
          v28 = -1;
        Error = 0;
        if ( v28 == -1 )
          Error = -2147024882;
      }
LABEL_30:
      if ( Error )
        goto LABEL_48;
LABEL_31:
      v5 = v34;
LABEL_32:
      v33 = ++v9;
      if ( Error < 0 )
        goto LABEL_33;
    }
    Error = -2147024809;
    if ( v10 == (char *)-8LL )
      goto LABEL_19;
    v16 = *((_WORD *)v10 + 1);
    LOBYTE(pControl[0]) = v10[1];
    LODWORD(v35) = *((_DWORD *)v10 + 1);
    if ( IsValidSid(v10 + 8) )
    {
      v17 = GetLengthSid(v10 + 8);
      Error = -2147024882;
      v18 = LocalAlloc(0x40u, v17);
      v19 = v18;
      if ( v18 )
      {
        if ( CopySid(v17, v18, v15) )
        {
          Error = 0;
          goto LABEL_14;
        }
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
        {
LABEL_14:
          v20 = pControl[0];
          *((_QWORD *)v13 + 1) = v19;
          *((_BYTE *)v13 + 1) = v20;
          v13[1] = (unsigned int)v35;
          *(_BYTE *)v13 = v14;
          *((_WORD *)v13 + 1) = v16;
          RtlMapGenericMask(v13 + 1, (PGENERIC_MAPPING)&GenericMapping);
          v21 = *(_BYTE *)v13;
          v13[7] = 0x80000000;
          if ( !v21 || (v22 = 0x80000000, v21 == 9) )
          {
            v13[7] = -2147483647;
            v22 = -2147483647;
          }
          if ( (*((_BYTE *)v13 + 1) & 0x10) != 0 )
            v13[7] = v22 | 0x20;
          goto LABEL_18;
        }
        LocalFree(v19);
      }
    }
LABEL_18:
    v9 = v33;
    v7 = v37;
    goto LABEL_19;
  }
LABEL_34:
  if ( Error < 0 || !v6 )
    return Error;
  pControl[0] = 0;
  dwRevision = 0;
  if ( GetSecurityDescriptorControl(v6, pControl, &dwRevision) )
  {
    if ( (pControl[0] & 0x1000) != 0 )
      *((_DWORD *)v7 + 6) = 0;
    *((_DWORD *)v7 + 7) = v4;
    return Error;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b240  push    rbp
0x18000b242  push    rsi
0x18000b243  push    rdi
0x18000b244  push    r12
0x18000b246  push    r13
0x18000b248  sub     rsp, 0A0h
0x18000b24f  mov     rax, cs:__security_cookie
0x18000b256  xor     rax, rsp
0x18000b259  mov     [rsp+0C8h+var_40], rax
0x18000b261  mov     [rsp+0C8h+arg_18], rbx
0x18000b269  mov     ebp, r9d
0x18000b26c  mov     rbx, rdx
0x18000b26f  mov     [rsp+0C8h+dwRevision], r9d
0x18000b274  mov     rsi, r8
0x18000b277  mov     [rsp+0C8h+var_58], r8
0x18000b27c  mov     [rsp+0C8h+var_78], rdx
0x18000b281  mov     r13, rcx
0x18000b284  mov     [rsp+0C8h+var_60], rcx
0x18000b289  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000b28e  xor     r12d, r12d
0x18000b291  mov     edi, eax
0x18000b293  test    eax, eax
0x18000b295  js      loc_18000B4E7
0x18000b29b  test    rbx, rbx
0x18000b29e  jz      loc_18000B4E7
0x18000b2a4  xor     eax, eax
0x18000b2a6  mov     [rsp+0C8h+var_30], r14
0x18000b2ae  mov     r9d, 2; dwAclInformationClass
0x18000b2b4  mov     [rsp+0C8h+pAclInformation], rax
0x18000b2b9  mov     r8d, 0Ch; nAclInformationLength
0x18000b2bf  mov     [rsp+0C8h+var_48], eax
0x18000b2c6  lea     rdx, [rsp+0C8h+pAclInformation]; pAclInformation
0x18000b2cb  mov     [rsp+0C8h+var_38], r15
0x18000b2d3  mov     rcx, rbx; pAcl
0x18000b2d6  call    cs:__imp_GetAclInformation
0x18000b2dc  mov     r15d, r12d
0x18000b2df  mov     [rsp+0C8h+var_80], r12d
0x18000b2e4  mov     ebp, 8007000Eh
0x18000b2e9  nop     dword ptr [rax+00000000h]
0x18000b2f0  cmp     r15d, dword ptr [rsp+0C8h+pAclInformation]
0x18000b2f5  jnb     loc_18000B4CE
0x18000b2fb  lea     r8, [rsp+0C8h+pAce]; pAce
0x18000b300  mov     [rsp+0C8h+pAce], r12
0x18000b305  mov     edx, r15d; dwAceIndex
0x18000b308  mov     rcx, rbx; pAcl
0x18000b30b  call    cs:__imp_GetAce
0x18000b311  test    eax, eax
0x18000b313  jz      loc_18000B5A6
0x18000b319  mov     rsi, [rsp+0C8h+pAce]
0x18000b31e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b325  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b32a  mov     edi, ebp
0x18000b32c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b331  mov     [rsp+0C8h+var_70], rax
0x18000b336  mov     rbx, rax
0x18000b339  test    rax, rax
0x18000b33c  jz      loc_18000B4AE
0x18000b342  mov     qword ptr [rax], 80000h
0x18000b349  mov     [rax+8], r12
0x18000b34d  mov     [rax+10h], r12
0x18000b351  mov     qword ptr [rax+18h], 0
0x18000b359  test    rsi, rsi
0x18000b35c  jz      loc_18000B594
0x18000b362  movzx   r12d, byte ptr [rsi]
0x18000b366  lea     rbp, [rsi+8]
0x18000b36a  cmp     r12b, 9
0x18000b36e  jz      loc_18000B5EA
0x18000b374  mov     edi, 80070057h
0x18000b379  test    rbp, rbp
0x18000b37c  jz      loc_18000B446
0x18000b382  movzx   eax, byte ptr [rsi+1]
0x18000b386  mov     rcx, rbp; pSid
0x18000b389  movzx   r13d, word ptr [rsi+2]
0x18000b38e  mov     byte ptr [rsp+0C8h+pControl], al
0x18000b392  mov     eax, [rsi+4]
0x18000b395  mov     dword ptr [rsp+0C8h+var_70], eax
0x18000b399  call    cs:__imp_IsValidSid
0x18000b39f  test    eax, eax
0x18000b3a1  jz      loc_18000B43C
0x18000b3a7  mov     rcx, rbp; pSid
0x18000b3aa  call    cs:__imp_GetLengthSid
0x18000b3b0  mov     edx, eax; uBytes
0x18000b3b2  mov     ecx, 40h ; '@'; uFlags
0x18000b3b7  mov     r15d, eax
0x18000b3ba  mov     edi, 8007000Eh
0x18000b3bf  call    cs:__imp_LocalAlloc
0x18000b3c5  mov     rsi, rax
0x18000b3c8  test    rax, rax
0x18000b3cb  jz      short loc_18000B43C
0x18000b3cd  mov     r8, rbp; pSourceSid
0x18000b3d0  mov     rdx, rax; pDestinationSid
0x18000b3d3  mov     ecx, r15d; nDestinationSidLength
0x18000b3d6  call    cs:__imp_CopySid
0x18000b3dc  test    eax, eax
0x18000b3de  jz      loc_18000B5B2
0x18000b3e4  xor     edi, edi
0x18000b3e6  movzx   eax, byte ptr [rsp+0C8h+pControl]
0x18000b3eb  lea     rdx, GenericMapping; GenericMapping
0x18000b3f2  mov     [rbx+8], rsi
0x18000b3f6  lea     rcx, [rbx+4]; AccessMask
0x18000b3fa  mov     [rbx+1], al
0x18000b3fd  mov     eax, dword ptr [rsp+0C8h+var_70]
0x18000b401  mov     [rbx+4], eax
0x18000b404  mov     [rbx], r12b
0x18000b407  mov     [rbx+2], r13w
0x18000b40c  call    cs:__imp_RtlMapGenericMask
0x18000b412  movzx   ecx, byte ptr [rbx]
0x18000b415  mov     dword ptr [rbx+1Ch], 80000000h
0x18000b41c  test    cl, cl
0x18000b41e  jnz     loc_18000B553
0x18000b424  mov     dword ptr [rbx+1Ch], 80000001h
0x18000b42b  mov     eax, 80000001h
0x18000b430  test    byte ptr [rbx+1], 10h
0x18000b434  jz      short loc_18000B43C
0x18000b436  or      eax, 20h
0x18000b439  mov     [rbx+1Ch], eax
0x18000b43c  mov     r15d, [rsp+0C8h+var_80]
0x18000b441  mov     r13, [rsp+0C8h+var_60]
0x18000b446  test    edi, edi
0x18000b448  js      loc_18000B599
0x18000b44e  mov     eax, [rbx+1Ch]
0x18000b451  mov     ecx, eax
0x18000b453  and     ecx, 20h
0x18000b456  jz      loc_18000B566
0x18000b45c  and     eax, 1
0x18000b45f  test    ecx, ecx
0x18000b461  jnz     short loc_18000B46B
0x18000b463  test    eax, eax
0x18000b465  jnz     loc_18000B581
0x18000b46b  mov     rax, cs:qword_1800959F8
0x18000b472  mov     rdi, [r13+10h]
0x18000b476  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b47a  jz      loc_18000B628
0x18000b480  test    rax, rax
0x18000b483  jz      loc_18000B645
0x18000b489  mov     r8, rbx
0x18000b48c  mov     edx, 7FFFFFFFh
0x18000b491  mov     rcx, rdi
0x18000b494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b499  xor     edi, edi
0x18000b49b  cmp     eax, 0FFFFFFFFh
0x18000b49e  mov     eax, 8007000Eh
0x18000b4a3  cmovz   edi, eax
0x18000b4a6  test    edi, edi
0x18000b4a8  jnz     loc_18000B599
0x18000b4ae  mov     rbx, [rsp+0C8h+var_78]
0x18000b4b3  inc     r15d
0x18000b4b6  mov     ebp, 8007000Eh
0x18000b4bb  mov     [rsp+0C8h+var_80], r15d
0x18000b4c0  mov     r12d, 0
0x18000b4c6  test    edi, edi
0x18000b4c8  jns     loc_18000B2F0
0x18000b4ce  mov     rsi, [rsp+0C8h+var_58]
0x18000b4d3  mov     ebp, [rsp+0C8h+dwRevision]
0x18000b4d7  mov     r15, [rsp+0C8h+var_38]
0x18000b4df  mov     r14, [rsp+0C8h+var_30]
0x18000b4e7  mov     rbx, [rsp+0C8h+arg_18]
0x18000b4ef  test    edi, edi
0x18000b4f1  js      short loc_18000B532
0x18000b4f3  test    rsi, rsi
0x18000b4f6  jz      short loc_18000B532
0x18000b4f8  lea     r8, [rsp+0C8h+dwRevision]; lpdwRevision
0x18000b4fd  mov     [rsp+0C8h+pControl], r12w
0x18000b503  lea     rdx, [rsp+0C8h+pControl]; pControl
0x18000b508  mov     [rsp+0C8h+dwRevision], r12d
0x18000b50d  mov     rcx, rsi; pSecurityDescriptor
0x18000b510  call    cs:__imp_GetSecurityDescriptorControl
0x18000b516  test    eax, eax
0x18000b518  jz      loc_18000B5CF
0x18000b51e  mov     eax, 1000h
0x18000b523  test    [rsp+0C8h+pControl], ax
0x18000b528  jnz     loc_18000B64F
0x18000b52e  mov     [r13+1Ch], ebp
0x18000b532  mov     eax, edi
0x18000b534  mov     rcx, [rsp+0C8h+var_40]
0x18000b53c  xor     rcx, rsp; StackCookie
0x18000b53f  call    __security_check_cookie
0x18000b544  add     rsp, 0A0h
0x18000b54b  pop     r13
0x18000b54d  pop     r12
0x18000b54f  pop     rdi
0x18000b550  pop     rsi
0x18000b551  pop     rbp
0x18000b552  retn
0x18000b553  mov     eax, 80000000h
0x18000b558  cmp     cl, 9
0x18000b55b  jnz     loc_18000B430
0x18000b561  jmp     loc_18000B424
0x18000b566  and     eax, 1
0x18000b569  jnz     loc_18000B45F
0x18000b56f  mov     r8, rbx
0x18000b572  mov     rdx, r13
0x18000b575  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000b57a  mov     edi, eax
0x18000b57c  jmp     loc_18000B4A6
0x18000b581  lea     rdx, [r13+8]
0x18000b585  mov     r8, rbx
0x18000b588  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000b58d  mov     edi, eax
0x18000b58f  jmp     loc_18000B4A6
0x18000b594  mov     edi, 80070057h
0x18000b599  mov     rcx, rbx; this
0x18000b59c  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000b5a1  jmp     loc_18000B4AE
0x18000b5a6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b5ab  mov     edi, eax
0x18000b5ad  jmp     loc_18000B4B3
0x18000b5b2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b5b7  mov     edi, eax
0x18000b5b9  test    eax, eax
0x18000b5bb  jns     loc_18000B3E6
0x18000b5c1  mov     rcx, rsi; hMem
0x18000b5c4  call    cs:__imp_LocalFree
0x18000b5ca  jmp     loc_18000B43C
0x18000b5cf  call    cs:__imp_GetLastError
0x18000b5d5  test    eax, eax
0x18000b5d7  jle     loc_18000B534
0x18000b5dd  movzx   eax, ax
0x18000b5e0  or      eax, 80070000h
0x18000b5e5  jmp     loc_18000B534
0x18000b5ea  mov     rcx, rbp; pSid
0x18000b5ed  call    cs:__imp_GetLengthSid
0x18000b5f3  movzx   r9d, byte ptr [rsi+1]; unsigned __int8
0x18000b5f8  mov     rdx, rbp; void *
0x18000b5fb  mov     r8d, [rsi+4]; unsigned int
0x18000b5ff  mov     ecx, eax
0x18000b601  movzx   eax, word ptr [rsi+2]
0x18000b605  add     rcx, rbp
0x18000b608  mov     [rsp+0C8h+var_98], rcx; void *
0x18000b60d  mov     rcx, rbx; this
0x18000b610  mov     [rsp+0C8h+var_A0], ax; unsigned __int16
0x18000b615  movzx   eax, byte ptr [rsi]
0x18000b618  mov     [rsp+0C8h+var_A8], al; unsigned __int8
0x18000b61c  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x18000b621  mov     edi, eax
0x18000b623  jmp     loc_18000B446
0x18000b628  mov     edx, 14Eh
0x18000b62d  lea     rcx, qword_1800959F8
0x18000b634  call    _GetProcFromComCtl32
0x18000b639  mov     rax, cs:qword_1800959F8
0x18000b640  jmp     loc_18000B480
0x18000b645  mov     eax, 0FFFFFFFFh
0x18000b64a  jmp     loc_18000B499
0x18000b64f  mov     [r13+18h], r12d
0x18000b653  jmp     loc_18000B52E
```
