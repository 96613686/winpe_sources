# CAceList::_InitFromAcl(_ACL *)

- ea: `0x18000b6f0`
- end: `0x18000bbee`
- name: `?_InitFromAcl@CAceList@@AEAAJPEAU_ACL@@@Z`
- size: `1278`
- prototype: `int(CAceList *__hidden this, struct _ACL *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bea0`
- `0x180033fc0`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000a5f8`
- `0x18000b6f0`
- `0x18000bc00`
- `0x18000f4b0`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x1800254e0`
- `0x1800259bc`
- `0x180026370`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bb04`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b83a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000b83a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000b7ab`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000b7ab`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ba3a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000ba3a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000b77a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000b77a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b877`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b877`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b84b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000bb3d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b84b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000bb3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b860`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b860`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bad4`
- `ntdll!RtlMapGenericMask` at `0x18000b8ad`
- `ntdll!RtlMapGenericMask` at `0x18000b8ad`

## pseudocode

```c
__int64 __fastcall CAceList::_InitFromAcl(CAceList *this, struct _ACL *a2)
{
  struct _ACL *v2; // rbx
  CAceList *v3; // r13
  __int64 result; // rax
  int Error; // edi
  DWORD v6; // r15d
  char *v7; // rsi
  DWORD *v8; // rax
  unsigned int v9; // edx
  DWORD *v10; // rbx
  unsigned __int8 v11; // r12
  char *v12; // rbp
  __int16 v13; // r13
  DWORD v14; // r15d
  HLOCAL v15; // rax
  void *v16; // rsi
  char v17; // cl
  unsigned int v18; // eax
  DWORD v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 (__fastcall *v22)(__int64, __int64, DWORD *); // rax
  __int64 v23; // rdi
  int v24; // eax
  int *v25; // rax
  int v26; // ebp
  int v27; // esi
  __int64 v28; // r14
  __int64 v29; // r14
  bool v30; // cl
  DWORD LengthSid; // eax
  char v32; // [rsp+40h] [rbp-78h]
  DWORD v33; // [rsp+44h] [rbp-74h]
  DWORD v35; // [rsp+50h] [rbp-68h]
  LPVOID pAce; // [rsp+58h] [rbp-60h] BYREF
  CAceList *v37; // [rsp+60h] [rbp-58h]
  __int64 pAclInformation; // [rsp+68h] [rbp-50h] BYREF
  int v39; // [rsp+70h] [rbp-48h]

  v2 = a2;
  v3 = this;
  v37 = this;
  result = CAceList::_Init(this);
  Error = result;
  if ( (int)result >= 0 && v2 )
  {
    pAclInformation = 0;
    v39 = 0;
    GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation);
    v6 = 0;
    v33 = 0;
    while ( v6 < (unsigned int)pAclInformation )
    {
      pAce = 0;
      if ( GetAce(v2, v6, &pAce) )
      {
        v7 = (char *)pAce;
        Error = -2147024882;
        v8 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        v10 = v8;
        if ( !v8 )
          goto LABEL_30;
        *(_QWORD *)v8 = 0x80000;
        *((_QWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 2) = 0;
        *((_QWORD *)v8 + 3) = 0;
        if ( !v7 )
        {
          Error = -2147024809;
          goto LABEL_58;
        }
        v11 = *v7;
        v12 = v7 + 8;
        if ( *v7 == 9 )
        {
          LengthSid = GetLengthSid(v7 + 8);
          Error = CAce::_Init((CAce *)v10, v7 + 8, *((_DWORD *)v7 + 1), v7[1], *v7, *((_WORD *)v7 + 1), &v12[LengthSid]);
        }
        else
        {
          Error = -2147024809;
          if ( v7 != (char *)-8LL )
          {
            v13 = *((_WORD *)v7 + 1);
            v32 = v7[1];
            v35 = *((_DWORD *)v7 + 1);
            if ( IsValidSid(v7 + 8) )
            {
              v14 = GetLengthSid(v7 + 8);
              Error = -2147024882;
              v15 = LocalAlloc(0x40u, v14);
              v16 = v15;
              if ( v15 )
              {
                if ( CopySid(v14, v15, v12) )
                {
                  Error = 0;
LABEL_14:
                  *((_QWORD *)v10 + 1) = v16;
                  *((_BYTE *)v10 + 1) = v32;
                  v10[1] = v35;
                  *(_BYTE *)v10 = v11;
                  *((_WORD *)v10 + 1) = v13;
                  RtlMapGenericMask(v10 + 1, (PGENERIC_MAPPING)&GenericMapping);
                  v17 = *(_BYTE *)v10;
                  v10[7] = 0x80000000;
                  if ( !v17 || (v18 = 0x80000000, v17 == 9) )
                  {
                    v10[7] = -2147483647;
                    v18 = -2147483647;
                  }
                  if ( (*((_BYTE *)v10 + 1) & 0x10) != 0 )
                    v10[7] = v18 | 0x20;
                }
                else
                {
                  Error = ResultFromKnownLastError();
                  if ( Error >= 0 )
                    goto LABEL_14;
                  LocalFree(v16);
                }
              }
            }
            v6 = v33;
            v3 = v37;
          }
        }
        if ( Error < 0 )
          goto LABEL_58;
        v19 = v10[7];
        v20 = v19 & 0x20;
        if ( (v19 & 0x20) != 0 )
        {
          v21 = v19 & 1;
        }
        else
        {
          v21 = v19 & 1;
          if ( !v21 )
          {
            Error = CAceList::_AddExplicitAceToDpa(v20, v3, v10);
            goto LABEL_29;
          }
        }
        if ( (_DWORD)v20 || !v21 )
        {
          v22 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
          v23 = *((_QWORD *)v3 + 2);
          if ( qword_1800959F8 == -1 )
            goto LABEL_56;
          goto LABEL_25;
        }
        v25 = (int *)*((_QWORD *)v3 + 1);
        if ( v25 )
          v26 = *v25;
        else
          v26 = 0;
        v27 = 0;
        while ( 2 )
        {
          if ( v27 >= v26 )
          {
LABEL_55:
            v22 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
            v23 = *((_QWORD *)v3 + 1);
            if ( qword_1800959F8 != -1 )
              goto LABEL_25;
LABEL_56:
            GetProcFromComCtl32(&qword_1800959F8, 334);
            v22 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
LABEL_25:
            if ( v22 )
              v24 = v22(v23, 0x7FFFFFFF, v10);
            else
              v24 = -1;
            Error = 0;
            if ( v24 == -1 )
              Error = -2147024882;
LABEL_29:
            if ( !Error )
            {
LABEL_30:
              v2 = a2;
              goto LABEL_31;
            }
LABEL_58:
            CAce::`scalar deleting destructor'((CAce *)v10, v9);
            goto LABEL_30;
          }
          v28 = *((_QWORD *)v3 + 1);
          if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
          {
            if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
            {
              qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
              goto LABEL_43;
            }
            qword_180095A20 = 0;
          }
          else
          {
LABEL_43:
            if ( qword_180095A20 )
            {
              v29 = qword_180095A20(v28, v27);
              goto LABEL_45;
            }
          }
          v29 = 0;
LABEL_45:
          if ( (v10[7] & 0x80000000) != 0 && *(int *)(v29 + 28) < 0 )
          {
            v30 = EqualSid(*((PSID *)v10 + 1), *(PSID *)(v29 + 8))
               && v10[7] == *(_DWORD *)(v29 + 28)
               && v10[1] == *(_DWORD *)(v29 + 4)
               && *((_BYTE *)v10 + 1) == *(_BYTE *)(v29 + 1)
               && *(_BYTE *)v10 == *(_BYTE *)v29
               && v10[6] == *(_DWORD *)(v29 + 24);
            v9 = 0;
            if ( *(_QWORD *)(v29 + 16) )
              v9 = v30;
            if ( v9 )
            {
              if ( !memcmp_0(*(const void **)(v29 + 16), *((const void **)v10 + 2), *(unsigned int *)(v29 + 24)) )
              {
LABEL_54:
                if ( v29 )
                {
                  Error = 1;
                  *(_DWORD *)(v29 + 4) |= v10[1];
                  goto LABEL_29;
                }
                goto LABEL_55;
              }
            }
            else if ( v30 )
            {
              goto LABEL_54;
            }
          }
          ++v27;
          continue;
        }
      }
      Error = ResultFromKnownLastError();
LABEL_31:
      v33 = ++v6;
      if ( Error < 0 )
        return (unsigned int)Error;
    }
    return (unsigned int)Error;
  }
  return result;
}

```

## disassembly

```asm
0x18000b6f0  push    rbx
0x18000b6f2  push    rdi
0x18000b6f3  push    r13
0x18000b6f5  sub     rsp, 0A0h
0x18000b6fc  mov     rax, cs:__security_cookie
0x18000b703  xor     rax, rsp
0x18000b706  mov     [rsp+0B8h+var_40], rax
0x18000b70b  mov     rbx, rdx
0x18000b70e  mov     [rsp+0B8h+var_70], rdx
0x18000b713  mov     r13, rcx
0x18000b716  mov     [rsp+0B8h+var_58], rcx
0x18000b71b  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000b720  mov     edi, eax
0x18000b722  test    eax, eax
0x18000b724  js      loc_18000B999
0x18000b72a  test    rbx, rbx
0x18000b72d  jz      loc_18000B999
0x18000b733  mov     [rsp+0B8h+arg_10], rbp
0x18000b73b  lea     rdx, [rsp+0B8h+pAclInformation]; pAclInformation
0x18000b740  mov     [rsp+0B8h+var_20], rsi
0x18000b748  xor     eax, eax
0x18000b74a  mov     [rsp+0B8h+var_28], r12
0x18000b752  mov     r9d, 2; dwAclInformationClass
0x18000b758  mov     [rsp+0B8h+var_30], r14
0x18000b760  mov     r8d, 0Ch; nAclInformationLength
0x18000b766  mov     rcx, rbx; pAcl
0x18000b769  mov     [rsp+0B8h+var_38], r15
0x18000b771  mov     [rsp+0B8h+pAclInformation], rax
0x18000b776  mov     [rsp+0B8h+var_48], eax
0x18000b77a  call    cs:__imp_GetAclInformation
0x18000b780  xor     ebp, ebp
0x18000b782  mov     r14d, 8007000Eh
0x18000b788  mov     r15d, ebp
0x18000b78b  mov     [rsp+0B8h+var_74], ebp
0x18000b78f  nop
0x18000b790  cmp     r15d, dword ptr [rsp+0B8h+pAclInformation]
0x18000b795  jnb     loc_18000B96F
0x18000b79b  lea     r8, [rsp+0B8h+pAce]; pAce
0x18000b7a0  mov     [rsp+0B8h+pAce], rbp
0x18000b7a5  mov     edx, r15d; dwAceIndex
0x18000b7a8  mov     rcx, rbx; pAcl
0x18000b7ab  call    cs:__imp_GetAce
0x18000b7b1  test    eax, eax
0x18000b7b3  jz      loc_18000BAB6
0x18000b7b9  mov     rsi, [rsp+0B8h+pAce]
0x18000b7be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b7c5  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b7ca  mov     edi, r14d
0x18000b7cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b7d2  mov     [rsp+0B8h+var_68], rax
0x18000b7d7  mov     rbx, rax
0x18000b7da  test    rax, rax
0x18000b7dd  jz      loc_18000B94F
0x18000b7e3  mov     qword ptr [rax], 80000h
0x18000b7ea  mov     [rax+8], rbp
0x18000b7ee  mov     [rax+10h], rbp
0x18000b7f2  mov     qword ptr [rax+18h], 0
0x18000b7fa  test    rsi, rsi
0x18000b7fd  jz      loc_18000BAA4
0x18000b803  movzx   r12d, byte ptr [rsi]
0x18000b807  lea     rbp, [rsi+8]
0x18000b80b  cmp     r12b, 9
0x18000b80f  jz      loc_18000BB3A
0x18000b815  mov     edi, 80070057h
0x18000b81a  test    rbp, rbp
0x18000b81d  jz      loc_18000B8E7
0x18000b823  movzx   eax, byte ptr [rsi+1]
0x18000b827  mov     rcx, rbp; pSid
0x18000b82a  movzx   r13d, word ptr [rsi+2]
0x18000b82f  mov     [rsp+0B8h+var_78], al
0x18000b833  mov     eax, [rsi+4]
0x18000b836  mov     dword ptr [rsp+0B8h+var_68], eax
0x18000b83a  call    cs:__imp_IsValidSid
0x18000b840  test    eax, eax
0x18000b842  jz      loc_18000B8DD
0x18000b848  mov     rcx, rbp; pSid
0x18000b84b  call    cs:__imp_GetLengthSid
0x18000b851  mov     edx, eax; uBytes
0x18000b853  mov     ecx, 40h ; '@'; uFlags
0x18000b858  mov     r15d, eax
0x18000b85b  mov     edi, 8007000Eh
0x18000b860  call    cs:__imp_LocalAlloc
0x18000b866  mov     rsi, rax
0x18000b869  test    rax, rax
0x18000b86c  jz      short loc_18000B8DD
0x18000b86e  mov     r8, rbp; pSourceSid
0x18000b871  mov     rdx, rax; pDestinationSid
0x18000b874  mov     ecx, r15d; nDestinationSidLength
0x18000b877  call    cs:__imp_CopySid
0x18000b87d  test    eax, eax
0x18000b87f  jz      loc_18000BAC2
0x18000b885  xor     edi, edi
0x18000b887  movzx   eax, [rsp+0B8h+var_78]
0x18000b88c  lea     rdx, GenericMapping; GenericMapping
0x18000b893  mov     [rbx+8], rsi
0x18000b897  lea     rcx, [rbx+4]; AccessMask
0x18000b89b  mov     [rbx+1], al
0x18000b89e  mov     eax, dword ptr [rsp+0B8h+var_68]
0x18000b8a2  mov     [rbx+4], eax
0x18000b8a5  mov     [rbx], r12b
0x18000b8a8  mov     [rbx+2], r13w
0x18000b8ad  call    cs:__imp_RtlMapGenericMask
0x18000b8b3  movzx   ecx, byte ptr [rbx]
0x18000b8b6  mov     dword ptr [rbx+1Ch], 80000000h
0x18000b8bd  test    cl, cl
0x18000b8bf  jnz     loc_18000B9B2
0x18000b8c5  mov     dword ptr [rbx+1Ch], 80000001h
0x18000b8cc  mov     eax, 80000001h
0x18000b8d1  test    byte ptr [rbx+1], 10h
0x18000b8d5  jz      short loc_18000B8DD
0x18000b8d7  or      eax, 20h
0x18000b8da  mov     [rbx+1Ch], eax
0x18000b8dd  mov     r15d, [rsp+0B8h+var_74]
0x18000b8e2  mov     r13, [rsp+0B8h+var_58]
0x18000b8e7  test    edi, edi
0x18000b8e9  js      loc_18000BAA9
0x18000b8ef  mov     eax, [rbx+1Ch]
0x18000b8f2  mov     ecx, eax
0x18000b8f4  and     ecx, 20h
0x18000b8f7  jz      loc_18000B9C5
0x18000b8fd  and     eax, 1
0x18000b900  test    ecx, ecx
0x18000b902  jnz     short loc_18000B90C
0x18000b904  test    eax, eax
0x18000b906  jnz     loc_18000B9E0
0x18000b90c  mov     rax, cs:qword_1800959F8
0x18000b913  mov     rdi, [r13+10h]
0x18000b917  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b91b  jz      loc_18000BA87
0x18000b921  test    rax, rax
0x18000b924  jz      loc_18000BBE4
0x18000b92a  mov     r8, rbx
0x18000b92d  mov     edx, 7FFFFFFFh
0x18000b932  mov     rcx, rdi
0x18000b935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b93a  xor     edi, edi
0x18000b93c  cmp     eax, 0FFFFFFFFh
0x18000b93f  mov     eax, 8007000Eh
0x18000b944  cmovz   edi, eax
0x18000b947  test    edi, edi
0x18000b949  jnz     loc_18000BAA9
0x18000b94f  mov     rbx, [rsp+0B8h+var_70]
0x18000b954  inc     r15d
0x18000b957  mov     ebp, 0
0x18000b95c  mov     [rsp+0B8h+var_74], r15d
0x18000b961  mov     r14d, 8007000Eh
0x18000b967  test    edi, edi
0x18000b969  jns     loc_18000B790
0x18000b96f  mov     r14, [rsp+0B8h+var_30]
0x18000b977  mov     eax, edi
0x18000b979  mov     r12, [rsp+0B8h+var_28]
0x18000b981  mov     rsi, [rsp+0B8h+var_20]
0x18000b989  mov     rbp, [rsp+0B8h+arg_10]
0x18000b991  mov     r15, [rsp+0B8h+var_38]
0x18000b999  mov     rcx, [rsp+0B8h+var_40]
0x18000b99e  xor     rcx, rsp; StackCookie
0x18000b9a1  call    __security_check_cookie
0x18000b9a6  add     rsp, 0A0h
0x18000b9ad  pop     r13
0x18000b9af  pop     rdi
0x18000b9b0  pop     rbx
0x18000b9b1  retn
0x18000b9b2  mov     eax, 80000000h
0x18000b9b7  cmp     cl, 9
0x18000b9ba  jnz     loc_18000B8D1
0x18000b9c0  jmp     loc_18000B8C5
0x18000b9c5  and     eax, 1
0x18000b9c8  jnz     loc_18000B900
0x18000b9ce  mov     r8, rbx
0x18000b9d1  mov     rdx, r13
0x18000b9d4  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000b9d9  mov     edi, eax
0x18000b9db  jmp     loc_18000B947
0x18000b9e0  mov     rax, [r13+8]
0x18000b9e4  test    rax, rax
0x18000b9e7  jz      loc_18000BB78
0x18000b9ed  mov     ebp, [rax]
0x18000b9ef  xor     esi, esi
0x18000b9f1  cmp     esi, ebp
0x18000b9f3  jge     short loc_18000BA72
0x18000b9f5  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000b9fd  mov     r14, [r13+8]
0x18000ba01  jz      loc_18000BADF
0x18000ba07  mov     rax, cs:qword_180095A20
0x18000ba0e  test    rax, rax
0x18000ba11  jz      loc_18000BB21
0x18000ba17  movsxd  rdx, esi
0x18000ba1a  mov     rcx, r14
0x18000ba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba22  mov     r14, rax
0x18000ba25  cmp     dword ptr [rbx+1Ch], 0
0x18000ba29  jge     short loc_18000BA65
0x18000ba2b  cmp     dword ptr [r14+1Ch], 0
0x18000ba30  jge     short loc_18000BA65
0x18000ba32  mov     rdx, [r14+8]; pSid2
0x18000ba36  mov     rcx, [rbx+8]; pSid1
0x18000ba3a  call    cs:__imp_EqualSid
0x18000ba40  test    eax, eax
0x18000ba42  jnz     loc_18000BB7F
0x18000ba48  xor     cl, cl
0x18000ba4a  mov     r9, [r14+10h]
0x18000ba4e  xor     edx, edx
0x18000ba50  test    r9, r9
0x18000ba53  movzx   eax, cl
0x18000ba56  cmovnz  edx, eax
0x18000ba59  test    edx, edx
0x18000ba5b  jnz     loc_18000BBC7
0x18000ba61  test    cl, cl
0x18000ba63  jnz     short loc_18000BA69
0x18000ba65  inc     esi
0x18000ba67  jmp     short loc_18000B9F1
0x18000ba69  test    r14, r14
0x18000ba6c  jnz     loc_18000BB29
0x18000ba72  mov     rax, cs:qword_1800959F8
0x18000ba79  mov     rdi, [r13+8]
0x18000ba7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba81  jnz     loc_18000B921
0x18000ba87  mov     edx, 14Eh
0x18000ba8c  lea     rcx, qword_1800959F8
0x18000ba93  call    _GetProcFromComCtl32
0x18000ba98  mov     rax, cs:qword_1800959F8
0x18000ba9f  jmp     loc_18000B921
0x18000baa4  mov     edi, 80070057h
0x18000baa9  mov     rcx, rbx; this
0x18000baac  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000bab1  jmp     loc_18000B94F
0x18000bab6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000babb  mov     edi, eax
0x18000babd  jmp     loc_18000B954
0x18000bac2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bac7  mov     edi, eax
0x18000bac9  test    eax, eax
0x18000bacb  jns     loc_18000B887
0x18000bad1  mov     rcx, rsi; hMem
0x18000bad4  call    cs:__imp_LocalFree
0x18000bada  jmp     loc_18000B8DD
0x18000badf  cmp     cs:g_hinstCC, 0
0x18000bae7  jnz     short loc_18000BAF8
0x18000bae9  call    DelayLoadCC
0x18000baee  cmp     cs:g_hinstCC, 0
0x18000baf6  jz      short loc_18000BB16
0x18000baf8  mov     rcx, cs:g_hinstCC; hModule
0x18000baff  mov     edx, 14Ch; lpProcName
0x18000bb04  call    cs:__imp_GetProcAddress
0x18000bb0a  mov     cs:qword_180095A20, rax
0x18000bb11  jmp     loc_18000BA07
0x18000bb16  mov     cs:qword_180095A20, 0
0x18000bb21  xor     r14d, r14d
0x18000bb24  jmp     loc_18000BA25
0x18000bb29  mov     eax, [rbx+4]
0x18000bb2c  mov     edi, 1
0x18000bb31  or      [r14+4], eax
0x18000bb35  jmp     loc_18000B947
0x18000bb3a  mov     rcx, rbp; pSid
0x18000bb3d  call    cs:__imp_GetLengthSid
0x18000bb43  movzx   r9d, byte ptr [rsi+1]; unsigned __int8
0x18000bb48  mov     rdx, rbp; void *
0x18000bb4b  mov     r8d, [rsi+4]; unsigned int
0x18000bb4f  mov     ecx, eax
0x18000bb51  movzx   eax, word ptr [rsi+2]
0x18000bb55  add     rcx, rbp
0x18000bb58  mov     [rsp+0B8h+var_88], rcx; void *
0x18000bb5d  mov     rcx, rbx; this
0x18000bb60  mov     [rsp+0B8h+var_90], ax; unsigned __int16
0x18000bb65  movzx   eax, byte ptr [rsi]
0x18000bb68  mov     [rsp+0B8h+var_98], al; unsigned __int8
0x18000bb6c  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x18000bb71  mov     edi, eax
0x18000bb73  jmp     loc_18000B8E7
0x18000bb78  xor     ebp, ebp
0x18000bb7a  jmp     loc_18000B9EF
0x18000bb7f  mov     eax, [r14+1Ch]
0x18000bb83  cmp     [rbx+1Ch], eax
0x18000bb86  jnz     loc_18000BA48
0x18000bb8c  mov     eax, [r14+4]
0x18000bb90  cmp     [rbx+4], eax
0x18000bb93  jnz     loc_18000BA48
0x18000bb99  movzx   eax, byte ptr [r14+1]
0x18000bb9e  cmp     [rbx+1], al
0x18000bba1  jnz     loc_18000BA48
0x18000bba7  movzx   eax, byte ptr [r14]
0x18000bbab  cmp     [rbx], al
0x18000bbad  jnz     loc_18000BA48
0x18000bbb3  mov     eax, [r14+18h]
0x18000bbb7  cmp     [rbx+18h], eax
0x18000bbba  jnz     loc_18000BA48
0x18000bbc0  mov     cl, 1
0x18000bbc2  jmp     loc_18000BA4A
0x18000bbc7  mov     r8d, [r14+18h]; Size
0x18000bbcb  mov     rcx, r9; Buf1
0x18000bbce  mov     rdx, [rbx+10h]; Buf2
0x18000bbd2  call    memcmp_0
0x18000bbd7  test    eax, eax
0x18000bbd9  jz      loc_18000BA69
0x18000bbdf  jmp     loc_18000BA65
0x18000bbe4  mov     eax, 0FFFFFFFFh
0x18000bbe9  jmp     loc_18000B93A
```
