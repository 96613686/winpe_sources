# CIssuanceLicense::ParseRight(CDRMLicense *)

- ea: `0x180014b20`
- end: `0x180015133`
- name: `?ParseRight@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z`
- size: `1555`
- prototype: `int(CIssuanceLicense *__hidden this, struct CDRMLicense *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops`

## callers

- `0x180013d80`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180008260`
- `0x1800082cc`
- `0x18000918c`
- `0x180014b20`
- `0x1800156a0`
- `0x180015e94`
- `0x1800164e4`
- `0x180016a38`
- `0x180016a9c`
- `0x180016b00`
- `0x18001ffd8`
- `0x18003b9bc`
- `0x18003d7ac`
- `0x18003db94`
- `0x18003dcb4`
- `0x18003f554`
- `0x18003f644`
- `0x18003f7a0`
- `0x18003f8f0`
- `0x18003f980`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001503c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001503c`

## string_xrefs

- `0x180014d39`: `access-condition`
- `0x180014d6c`: `access-condition`

## pseudocode

```c
__int64 __fastcall CIssuanceLicense::ParseRight(CIssuanceLicense *this, CRight **a2)
{
  __int64 v2; // r12
  unsigned __int16 **v3; // r15
  char *v4; // r13
  CUser *v5; // r14
  CRight *v7; // rax
  CRight *v8; // rsi
  int RightName; // ebx
  unsigned __int16 **v10; // rax
  void *v11; // rax
  unsigned __int16 **v12; // r13
  unsigned int i; // r15d
  int LicenseObject; // eax
  unsigned int v15; // r15d
  CRight *j; // r13
  unsigned int v17; // r13d
  CUser *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // r15d
  CRight *v22; // r13
  CIssuanceLicense *v23; // r15
  unsigned int k; // esi
  __int64 v25; // rdi
  unsigned __int16 **v27; // [rsp+20h] [rbp-79h]
  unsigned int v28; // [rsp+28h] [rbp-71h] BYREF
  unsigned __int16 *v29; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-61h] BYREF
  void *Block; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-49h] BYREF
  CRight *v34; // [rsp+58h] [rbp-41h]
  unsigned int v35; // [rsp+60h] [rbp-39h]
  void *v36; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v37; // [rsp+70h] [rbp-29h] BYREF
  CIssuanceLicense *v38; // [rsp+78h] [rbp-21h]
  CRight *v39; // [rsp+80h] [rbp-19h]
  struct _SYSTEMTIME v40; // [rsp+88h] [rbp-11h] BYREF
  struct _SYSTEMTIME v41; // [rsp+98h] [rbp-1h] BYREF
  struct _SYSTEMTIME v42; // [rsp+A8h] [rbp+Fh] BYREF

  v38 = this;
  v37 = 0;
  v28 = 0;
  v27 = 0;
  LODWORD(v2) = 0;
  v36 = 0;
  v3 = 0;
  Block = 0;
  v4 = 0;
  v29 = 0;
  v5 = 0;
  v33 = 0;
  v42 = 0;
  v30 = 0;
  v41 = 0;
  v32 = 0;
  v7 = (CRight *)operator new(0xD8u);
  v39 = v7;
  if ( v7 && (v8 = CRight::CRight(v7)) != 0 )
  {
    RightName = CDRMLicense::GetRightName((CDRMLicense *)a2, &v37);
    if ( RightName >= 0 )
    {
      RightName = CRight::SetRightName(v8, v37);
      if ( RightName >= 0 )
      {
        RightName = CDRMLicense::GetLicenseAttributeCount((CDRMLicense *)a2, L"rights-parameter-name", &v28);
        if ( (int)(RightName + 0x80000000) >= 0 && RightName != -2147168490 )
        {
          LODWORD(v2) = v28;
          goto LABEL_55;
        }
        v2 = v28;
        if ( !v28 )
          goto LABEL_17;
        v10 = (unsigned __int16 **)operator new[](saturated_mul(v28, 8u));
        v27 = v10;
        v3 = v10;
        if ( !v10 )
        {
          RightName = -2147024882;
          goto LABEL_55;
        }
        memset_0(v10, 0, 8 * v2);
        v11 = operator new[](saturated_mul((unsigned int)v2, 8u));
        v36 = v11;
        v12 = (unsigned __int16 **)v11;
        if ( !v11 )
        {
          RightName = -2147024882;
          goto LABEL_54;
        }
        memset_0(v11, 0, 8 * v2);
        for ( i = 0; i < (unsigned int)v2; ++i )
        {
          RightName = CDRMLicense::GetRightParameter((CDRMLicense *)a2, i, &v27[i], &v12[i]);
          if ( RightName < 0 )
            goto LABEL_54;
        }
        v3 = v27;
        RightName = CRight::SetExtendedInfo(v8, v2, v27, v12);
        if ( RightName >= 0 )
        {
LABEL_17:
          LicenseObject = CDRMLicense::GetLicenseObject((CDRMLicense *)a2, L"condition-list", 0);
          RightName = LicenseObject;
          if ( LicenseObject != -2147168490 )
          {
            if ( LicenseObject < 0 )
              goto LABEL_55;
            v34 = a2[4];
            v28 = *(_DWORD *)a2;
            RightName = CDRMLicense::GetLicenseObjectCount((CDRMLicense *)a2, L"access-condition", &v30);
            if ( RightName < 0 )
              goto LABEL_55;
            v15 = 0;
            for ( j = v34; v15 < v30; *(_DWORD *)a2 = v19 )
            {
              RightName = CDRMLicense::GetLicenseObject((CDRMLicense *)a2, L"access-condition", v15);
              if ( RightName < 0 )
              {
                v5 = 0;
                goto LABEL_54;
              }
              v39 = a2[4];
              v35 = *(_DWORD *)a2;
              v5 = 0;
              if ( (unsigned int)CDRMLicense::GetLicenseObjectCount((CDRMLicense *)a2, L"principal", &v32) != -2147168490 )
              {
                v17 = 0;
                if ( v32 )
                {
                  while ( 1 )
                  {
                    v5 = 0;
                    RightName = CDRMLicense::GetLicenseObject((CDRMLicense *)a2, L"principal", v17);
                    if ( RightName < 0 )
                      break;
                    operator delete(Block);
                    Block = 0;
                    operator delete(v29);
                    v29 = 0;
                    RightName = CDRMLicense::GetPrincipalID((CDRMLicense *)a2, (unsigned __int16 **)&Block, &v29);
                    if ( RightName < 0 )
                      break;
                    v18 = (CUser *)operator new(0x98u);
                    *(_QWORD *)&v40.wYear = v18;
                    if ( !v18 || (v5 = CUser::CUser(v18)) == 0 )
                    {
                      RightName = -2147024882;
                      break;
                    }
                    RightName = CUser::SetUserIdType(v5, (unsigned __int16 *)Block);
                    if ( RightName < 0 )
                      break;
                    if ( *v29 )
                    {
                      RightName = CNameValue::SetValue(v5, v29);
                      if ( RightName < 0 )
                        break;
                    }
                    operator delete(v33);
                    v33 = 0;
                    if ( CDRMLicense::GetPrincipalName((CDRMLicense *)a2, &v33) != -2147168490 )
                    {
                      RightName = CUser::SetUserName(v5, v33);
                      if ( RightName < 0 )
                        break;
                    }
                    RightName = CIssuanceLicense::AddUserRight(v38, v8, v5);
                    if ( RightName < 0 )
                      break;
                    CDRMCBase::Release(v5);
                    v5 = 0;
                    a2[4] = v39;
                    ++v17;
                    *(_DWORD *)a2 = v35;
                    if ( v17 >= v32 )
                      goto LABEL_35;
                  }
LABEL_54:
                  v3 = v27;
                  goto LABEL_55;
                }
LABEL_35:
                j = v34;
              }
              v19 = v28;
              ++v15;
              a2[4] = j;
            }
            if ( (unsigned int)CDRMLicense::GetLicenseObjectCount((CDRMLicense *)a2, L"rangetime-condition", &v30) != -2147168490 )
            {
              RightName = CDRMLicense::GetLicenseObject((CDRMLicense *)a2, L"rangetime-condition", 0);
              if ( RightName < 0 )
                goto LABEL_54;
              RightName = CDRMLicense::GetRangeTime((CDRMLicense *)a2, &v42, &v41);
              if ( RightName < 0 )
                goto LABEL_54;
              RightName = CRight::SetValidityTime(v8, &v42, &v41);
              if ( RightName < 0 )
                goto LABEL_54;
              v20 = v28;
              a2[4] = j;
              *(_DWORD *)a2 = v20;
            }
            if ( (unsigned int)CDRMLicense::GetLicenseObjectCount((CDRMLicense *)a2, L"intervaltime-condition", &v30) != -2147168490 )
            {
              RightName = CDRMLicense::GetLicenseObject((CDRMLicense *)a2, L"intervaltime-condition", 0);
              if ( RightName < 0 )
                goto LABEL_54;
              v21 = 9;
              v40 = 0;
              if ( *(_DWORD *)a2 == 9 )
              {
                v22 = a2[4];
                RightName = CDRMLicense::ExtractInterval((CDRMLicense *)a2, &v40);
              }
              else
              {
                RightName = -2147168494;
                v22 = 0;
                v21 = 0;
              }
              a2[4] = v22;
              *(_DWORD *)a2 = v21;
              if ( RightName < 0 )
                goto LABEL_54;
              v23 = v38;
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)v38 + 88));
              *((_DWORD *)v23 + 234) = v40.wDay;
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v23 + 88));
              a2[4] = v34;
              *(_DWORD *)a2 = v28;
            }
          }
          RightName = 0;
          goto LABEL_54;
        }
      }
    }
LABEL_55:
    CDRMCBase::Release(v8);
    if ( v5 )
      CDRMCBase::Release(v5);
    v5 = (CUser *)v29;
    v4 = (char *)v36;
  }
  else
  {
    RightName = -2147024882;
  }
  for ( k = 0; k < (unsigned int)v2; ++k )
  {
    v25 = k;
    if ( v3 )
    {
      operator delete(v3[v25]);
      v3[v25] = 0;
    }
    if ( v4 )
    {
      operator delete(*(void **)&v4[v25 * 8]);
      *(_QWORD *)&v4[v25 * 8] = 0;
    }
  }
  operator delete(v3);
  operator delete(v4);
  operator delete(v37);
  operator delete(Block);
  operator delete(v5);
  operator delete(v33);
  return (unsigned int)RightName;
}

```

## disassembly

```asm
0x180014b20  mov     [rsp-8+arg_10], rbx
0x180014b25  push    rbp
0x180014b26  push    rsi
0x180014b27  push    rdi
0x180014b28  push    r12
0x180014b2a  push    r13
0x180014b2c  push    r14
0x180014b2e  push    r15
0x180014b30  lea     rbp, [rsp-27h]
0x180014b35  sub     rsp, 0C0h
0x180014b3c  mov     rax, cs:__security_cookie
0x180014b43  xor     rax, rsp
0x180014b46  mov     [rbp+57h+var_38], rax
0x180014b4a  xor     ebx, ebx
0x180014b4c  mov     [rbp+57h+var_78], rcx
0x180014b50  xorps   xmm0, xmm0
0x180014b53  mov     [rbp+57h+var_80], rbx
0x180014b57  xorps   xmm1, xmm1
0x180014b5a  mov     [rbp+57h+var_C8], ebx
0x180014b5d  mov     ecx, 0D8h; Size
0x180014b62  mov     [rbp+57h+var_D0], rbx
0x180014b66  mov     r12d, ebx
0x180014b69  mov     [rbp+57h+var_88], rbx
0x180014b6d  mov     r15d, ebx
0x180014b70  mov     [rbp+57h+Block], rbx
0x180014b74  mov     r13d, ebx
0x180014b77  mov     [rbp+57h+var_C0], rbx
0x180014b7b  mov     r14d, ebx
0x180014b7e  mov     [rbp+57h+var_A0], rbx
0x180014b82  movups  xmmword ptr [rbp+57h+var_48.wYear], xmm0
0x180014b86  mov     [rbp+57h+var_B8], ebx
0x180014b89  mov     rdi, rdx
0x180014b8c  movups  xmmword ptr [rbp+57h+var_58.wYear], xmm1
0x180014b90  mov     [rbp+57h+var_A8], ebx
0x180014b93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014b98  mov     [rbp+57h+var_70], rax
0x180014b9c  test    rax, rax
0x180014b9f  jz      loc_180015127
0x180014ba5  mov     rcx, rax; this
0x180014ba8  call    ??0CRight@@QEAA@XZ; CRight::CRight(void)
0x180014bad  mov     rsi, rax
0x180014bb0  test    rax, rax
0x180014bb3  jz      loc_180015127
0x180014bb9  lea     rdx, [rbp+57h+var_80]; unsigned __int16 **
0x180014bbd  mov     rcx, rdi; this
0x180014bc0  call    ?GetRightName@CDRMLicense@@QEAAJPEAPEAG@Z; CDRMLicense::GetRightName(ushort * *)
0x180014bc5  mov     ebx, eax
0x180014bc7  test    eax, eax
0x180014bc9  js      loc_18001506A
0x180014bcf  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180014bd3  mov     rcx, rsi; this
0x180014bd6  call    ?SetRightName@CRight@@QEAAJPEAG@Z; CRight::SetRightName(ushort *)
0x180014bdb  mov     ebx, eax
0x180014bdd  test    eax, eax
0x180014bdf  js      loc_18001506A
0x180014be5  lea     r8, [rbp+57h+var_C8]; unsigned int *
0x180014be9  mov     rcx, rdi; this
0x180014bec  lea     rdx, aRightsParamete_0; "rights-parameter-name"
0x180014bf3  call    ?GetLicenseAttributeCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseAttributeCount(ushort const *,uint *)
0x180014bf8  mov     ecx, 80000000h
0x180014bfd  mov     ebx, eax
0x180014bff  add     eax, ecx
0x180014c01  test    ecx, eax
0x180014c03  jnz     short loc_180014C16
0x180014c05  cmp     ebx, 8004CF16h
0x180014c0b  jz      short loc_180014C16
0x180014c0d  mov     r12d, [rbp+57h+var_C8]
0x180014c11  jmp     loc_18001506A
0x180014c16  mov     r12d, [rbp+57h+var_C8]
0x180014c1a  test    r12d, r12d
0x180014c1d  jz      loc_180014D06
0x180014c23  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014c2a  mov     eax, 8
0x180014c2f  mul     r12
0x180014c32  mov     ebx, r12d
0x180014c35  cmovb   rax, rcx
0x180014c39  mov     rcx, rax; unsigned __int64
0x180014c3c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014c41  mov     [rbp+57h+var_D0], rax
0x180014c45  mov     r15, rax
0x180014c48  test    rax, rax
0x180014c4b  jnz     short loc_180014C57
0x180014c4d  mov     ebx, 8007000Eh
0x180014c52  jmp     loc_18001506A
0x180014c57  lea     r15, ds:0[r12*8]
0x180014c5f  xor     edx, edx; Val
0x180014c61  mov     r8, r15; Size
0x180014c64  mov     rcx, rax; void *
0x180014c67  call    memset_0
0x180014c6c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014c73  mov     eax, 8
0x180014c78  mul     rbx
0x180014c7b  cmovb   rax, rcx
0x180014c7f  mov     rcx, rax; unsigned __int64
0x180014c82  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014c87  xor     ebx, ebx
0x180014c89  mov     [rbp+57h+var_88], rax
0x180014c8d  mov     r13, rax
0x180014c90  test    rax, rax
0x180014c93  jnz     short loc_180014C9F
0x180014c95  mov     ebx, 8007000Eh
0x180014c9a  jmp     loc_180015066
0x180014c9f  mov     r8, r15; Size
0x180014ca2  xor     edx, edx; Val
0x180014ca4  mov     rcx, r13; void *
0x180014ca7  call    memset_0
0x180014cac  mov     r15d, ebx
0x180014caf  test    r12d, r12d
0x180014cb2  jz      short loc_180014CE7
0x180014cb4  mov     rcx, [rbp+57h+var_D0]
0x180014cb8  mov     edx, r15d; unsigned int
0x180014cbb  mov     eax, r15d
0x180014cbe  lea     r9, ds:0[rax*8]
0x180014cc6  lea     r8, [rcx+rax*8]; unsigned __int16 **
0x180014cca  add     r9, r13; unsigned __int16 **
0x180014ccd  mov     rcx, rdi; this
0x180014cd0  call    ?GetRightParameter@CDRMLicense@@QEAAJIPEAPEAG0@Z; CDRMLicense::GetRightParameter(uint,ushort * *,ushort * *)
0x180014cd5  mov     ebx, eax
0x180014cd7  test    eax, eax
0x180014cd9  js      loc_180015066
0x180014cdf  inc     r15d
0x180014ce2  cmp     r15d, r12d
0x180014ce5  jb      short loc_180014CB4
0x180014ce7  mov     r15, [rbp+57h+var_D0]
0x180014ceb  mov     r9, r13; unsigned __int16 **
0x180014cee  mov     r8, r15; unsigned __int16 **
0x180014cf1  mov     edx, r12d; unsigned int
0x180014cf4  mov     rcx, rsi; this
0x180014cf7  call    ?SetExtendedInfo@CRight@@QEAAJIPEAPEAG0@Z; CRight::SetExtendedInfo(uint,ushort * *,ushort * *)
0x180014cfc  mov     ebx, eax
0x180014cfe  test    eax, eax
0x180014d00  js      loc_18001506A
0x180014d06  xor     r8d, r8d; unsigned int
0x180014d09  lea     rdx, aConditionList; "condition-list"
0x180014d10  mov     rcx, rdi; this
0x180014d13  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180014d18  mov     ebx, eax
0x180014d1a  cmp     eax, 8004CF16h
0x180014d1f  jz      loc_180015064
0x180014d25  test    eax, eax
0x180014d27  js      loc_18001506A
0x180014d2d  mov     rax, [rdi+20h]
0x180014d31  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x180014d35  mov     [rbp+57h+var_98], rax
0x180014d39  lea     rdx, aAccessConditio; "access-condition"
0x180014d40  mov     eax, [rdi]
0x180014d42  mov     rcx, rdi; this
0x180014d45  mov     [rbp+57h+var_C8], eax
0x180014d48  call    ?GetLicenseObjectCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseObjectCount(ushort const *,uint *)
0x180014d4d  mov     ebx, eax
0x180014d4f  xor     eax, eax
0x180014d51  test    ebx, ebx
0x180014d53  js      loc_18001506A
0x180014d59  mov     r15d, eax
0x180014d5c  mov     r13, [rbp+57h+var_98]
0x180014d60  cmp     [rbp+57h+var_B8], eax
0x180014d63  jbe     loc_180014F1B
0x180014d69  mov     r8d, r15d; unsigned int
0x180014d6c  lea     rdx, aAccessConditio; "access-condition"
0x180014d73  mov     rcx, rdi; this
0x180014d76  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180014d7b  mov     ebx, eax
0x180014d7d  xor     eax, eax
0x180014d7f  test    ebx, ebx
0x180014d81  js      loc_180015012
0x180014d87  mov     rax, [rdi+20h]
0x180014d8b  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x180014d8f  mov     [rbp+57h+var_70], rax
0x180014d93  lea     rdx, aPrincipal; "principal"
0x180014d9a  mov     eax, [rdi]
0x180014d9c  xor     ebx, ebx
0x180014d9e  mov     rcx, rdi; this
0x180014da1  mov     [rbp+57h+var_90], eax
0x180014da4  mov     r14d, ebx
0x180014da7  call    ?GetLicenseObjectCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseObjectCount(ushort const *,uint *)
0x180014dac  cmp     eax, 8004CF16h
0x180014db1  jz      loc_180014F05
0x180014db7  mov     r13d, ebx
0x180014dba  cmp     [rbp+57h+var_A8], ebx
0x180014dbd  jbe     loc_180014F01
0x180014dc3  mov     r8d, r13d; unsigned int
0x180014dc6  lea     rdx, aPrincipal; "principal"
0x180014dcd  mov     rcx, rdi; this
0x180014dd0  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180014dd5  xor     r14d, r14d
0x180014dd8  mov     ebx, eax
0x180014dda  test    eax, eax
0x180014ddc  js      loc_180015066
0x180014de2  mov     rcx, [rbp+57h+Block]; Block
0x180014de6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014deb  mov     rcx, [rbp+57h+var_C0]; Block
0x180014def  mov     [rbp+57h+Block], r14
0x180014df3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014df8  lea     r8, [rbp+57h+var_C0]; unsigned __int16 **
0x180014dfc  mov     [rbp+57h+var_C0], r14
0x180014e00  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x180014e04  mov     rcx, rdi; this
0x180014e07  call    ?GetPrincipalID@CDRMLicense@@QEAAJPEAPEAG0@Z; CDRMLicense::GetPrincipalID(ushort * *,ushort * *)
0x180014e0c  mov     ebx, eax
0x180014e0e  test    eax, eax
0x180014e10  js      loc_180015000
0x180014e16  mov     ecx, 98h; Size
0x180014e1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e20  mov     qword ptr [rbp+57h+var_68.wYear], rax
0x180014e24  test    rax, rax
0x180014e27  jz      loc_180014FE9
0x180014e2d  mov     rcx, rax; this
0x180014e30  call    ??0CUser@@QEAA@XZ; CUser::CUser(void)
0x180014e35  mov     r14, rax
0x180014e38  test    rax, rax
0x180014e3b  jz      loc_180014FE9
0x180014e41  mov     rax, [rbp+57h+Block]
0x180014e45  mov     rcx, r14; this
0x180014e48  mov     rdx, rax; unsigned __int16 *
0x180014e4b  mov     [rbp+57h+Block], rax
0x180014e4f  call    ?SetUserIdType@CUser@@QEAAJPEAG@Z; CUser::SetUserIdType(ushort *)
0x180014e54  xor     ecx, ecx
0x180014e56  mov     ebx, eax
0x180014e58  test    eax, eax
0x180014e5a  js      loc_180014FF6
0x180014e60  mov     rax, [rbp+57h+var_C0]
0x180014e64  mov     [rbp+57h+var_C0], rax
0x180014e68  cmp     [rax], cx
0x180014e6b  jz      short loc_180014E82
0x180014e6d  mov     rdx, rax; unsigned __int16 *
0x180014e70  mov     rcx, r14; this
0x180014e73  call    ?SetValue@CNameValue@@QEAAJPEAG@Z; CNameValue::SetValue(ushort *)
0x180014e78  mov     ebx, eax
0x180014e7a  test    eax, eax
0x180014e7c  js      loc_180015066
0x180014e82  mov     rcx, [rbp+57h+var_A0]; Block
0x180014e86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014e8b  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x180014e8f  mov     [rbp+57h+var_A0], 0
0x180014e97  mov     rcx, rdi; this
0x180014e9a  call    ?GetPrincipalName@CDRMLicense@@QEAAJPEAPEAG@Z; CDRMLicense::GetPrincipalName(ushort * *)
0x180014e9f  mov     rcx, [rbp+57h+var_A0]
0x180014ea3  mov     [rbp+57h+var_A0], rcx
0x180014ea7  cmp     eax, 8004CF16h
0x180014eac  jz      short loc_180014EC3
0x180014eae  mov     rdx, rcx; unsigned __int16 *
0x180014eb1  mov     rcx, r14; this
0x180014eb4  call    ?SetUserName@CUser@@QEAAJPEAG@Z; CUser::SetUserName(ushort *)
0x180014eb9  mov     ebx, eax
0x180014ebb  test    eax, eax
0x180014ebd  js      loc_180015066
0x180014ec3  mov     rcx, [rbp+57h+var_78]; this
0x180014ec7  mov     r8, r14; struct CUser *
0x180014eca  mov     rdx, rsi; struct CRight *
0x180014ecd  call    ?AddUserRight@CIssuanceLicense@@QEAAJPEAVCRight@@PEAVCUser@@@Z; CIssuanceLicense::AddUserRight(CRight *,CUser *)
0x180014ed2  mov     ebx, eax
0x180014ed4  test    eax, eax
0x180014ed6  js      loc_180015066
0x180014edc  mov     rcx, r14; this
0x180014edf  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180014ee4  mov     rax, [rbp+57h+var_70]
0x180014ee8  xor     r14d, r14d
0x180014eeb  mov     [rdi+20h], rax
0x180014eef  inc     r13d
0x180014ef2  mov     eax, [rbp+57h+var_90]
0x180014ef5  mov     [rdi], eax
0x180014ef7  cmp     r13d, [rbp+57h+var_A8]
0x180014efb  jb      loc_180014DC3
0x180014f01  mov     r13, [rbp+57h+var_98]
0x180014f05  mov     eax, [rbp+57h+var_C8]
0x180014f08  inc     r15d
0x180014f0b  mov     [rdi+20h], r13
0x180014f0f  mov     [rdi], eax
0x180014f11  cmp     r15d, [rbp+57h+var_B8]
0x180014f15  jb      loc_180014D69
0x180014f1b  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x180014f1f  mov     rcx, rdi; this
0x180014f22  lea     rdx, aRangetimeCondi; "rangetime-condition"
0x180014f29  call    ?GetLicenseObjectCount@CDRMLicense@@QEAAJPEBGPEAI@Z; CDRMLicense::GetLicenseObjectCount(ushort const *,uint *)
0x180014f2e  cmp     eax, 8004CF16h
0x180014f33  jz      short loc_180014F8E
0x180014f35  xor     r8d, r8d; unsigned int
0x180014f38  lea     rdx, aRangetimeCondi; "rangetime-condition"
0x180014f3f  mov     rcx, rdi; this
0x180014f42  call    ?GetLicenseObject@CDRMLicense@@QEAAJPEBGI@Z; CDRMLicense::GetLicenseObject(ushort const *,uint)
0x180014f47  mov     ebx, eax
0x180014f49  test    eax, eax
0x180014f4b  js      loc_180015066
0x180014f51  lea     r8, [rbp+57h+var_58]; struct _SYSTEMTIME *
0x180014f55  mov     rcx, rdi; this
0x180014f58  lea     rdx, [rbp+57h+var_48]; struct _SYSTEMTIME *
0x180014f5c  call    ?GetRangeTime@CDRMLicense@@QEAAJPEAU_SYSTEMTIME@@0@Z; CDRMLicense::GetRangeTime(_SYSTEMTIME *,_SYSTEMTIME *)
0x180014f61  mov     ebx, eax
0x180014f63  test    eax, eax
0x180014f65  js      loc_180015066
0x180014f6b  lea     r8, [rbp+57h+var_58]; struct _SYSTEMTIME *
0x180014f6f  mov     rcx, rsi; this
0x180014f72  lea     rdx, [rbp+57h+var_48]; struct _SYSTEMTIME *
0x180014f76  call    ?SetValidityTime@CRight@@QEAAJPEAU_SYSTEMTIME@@0@Z; CRight::SetValidityTime(_SYSTEMTIME *,_SYSTEMTIME *)
0x180014f7b  mov     ebx, eax
0x180014f7d  test    eax, eax
0x180014f7f  js      loc_180015066
0x180014f85  mov     eax, [rbp+57h+var_C8]
0x180014f88  mov     [rdi+20h], r13
0x180014f8c  mov     [rdi], eax
  ... truncated ...
```
