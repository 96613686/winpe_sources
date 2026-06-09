# myGetTemplateAccessRights(void *,void *,ulong,ulong *)

- ea: `0x180010600`
- end: `0x180010970`
- name: `?myGetTemplateAccessRights@@YAJPEAX0KPEAK@Z`
- size: `880`
- prototype: `__int64 __fastcall(HANDLE, void *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029ddc`

## callees

- `0x180008400`
- `0x180010600`
- `0x180010978`
- `0x180012450`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001073b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800107a3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010807`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001073b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800107a3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180010807`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180010883`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180010907`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180010883`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180010907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010941`

## pseudocode

```c
__int64 __fastcall myGetTemplateAccessRights(HANDLE a1, void *a2, int a3, unsigned int *a4)
{
  char v5; // r14
  HANDLE v8; // rsi
  unsigned int v9; // ecx
  int v10; // edx
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  WINBOOL AccessStatus; // [rsp+60h] [rbp-49h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-45h] BYREF
  DWORD PrivilegeSetLength; // [rsp+68h] [rbp-41h] BYREF
  HANDLE ClientToken; // [rsp+70h] [rbp-39h] BYREF
  _OBJECT_TYPE_LIST ObjectTypeList; // [rsp+78h] [rbp-31h] BYREF
  struct _OBJECT_TYPE_LIST v21; // [rsp+88h] [rbp-21h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+98h] [rbp-11h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+A8h] [rbp-1h] BYREF

  PrivilegeSetLength = 20;
  ClientToken = 0;
  GenericMapping.GenericRead = 272;
  *(_QWORD *)&GenericMapping.GenericWrite = 32;
  v5 = a3;
  GenericMapping.GenericAll = 304;
  AccessStatus = 0;
  GrantedAccess = 0;
  v8 = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  v21 = g_objectTypeAutoEnroll;
  ObjectTypeList = g_objectTypeEnroll;
  if ( a4 )
  {
    *a4 = 0;
    if ( (a3 & 0xFFFEFFE0) != 0 )
    {
      v9 = 46006676;
      goto LABEL_3;
    }
    if ( !a2 )
    {
      v11 = -2147024891;
      v9 = 46465428;
      v10 = -2147024891;
      goto LABEL_4;
    }
    v12 = myGetClientToken(a1, (a3 & 0x10000) == 0, &ClientToken);
    v11 = v12;
    if ( v12 )
    {
      CSPrintErrorLineFile(0x2CC0194u, v12);
      v8 = ClientToken;
      goto LABEL_39;
    }
    v8 = ClientToken;
    if ( (v5 & 4) != 0 )
    {
      AccessStatus = 0;
      if ( !AccessCheck(
              a2,
              ClientToken,
              0x10u,
              &GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus) )
      {
        v11 = myHLastError();
        v10 = v11;
        v9 = 48038292;
        goto LABEL_4;
      }
      if ( !AccessStatus )
        goto LABEL_38;
      *a4 |= 4u;
    }
    if ( (v5 & 8) != 0 )
    {
      AccessStatus = 0;
      if ( !AccessCheck(
              a2,
              v8,
              0x40000u,
              &GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus) )
      {
        v11 = myHLastError();
        v10 = v11;
        v9 = 49873300;
        goto LABEL_4;
      }
      if ( AccessStatus )
        *a4 |= 8u;
    }
    if ( (v5 & 0x10) != 0 )
    {
      AccessStatus = 0;
      if ( !AccessCheck(
              a2,
              v8,
              0x80000u,
              &GenericMapping,
              &PrivilegeSet,
              &PrivilegeSetLength,
              &GrantedAccess,
              &AccessStatus) )
      {
        v11 = myHLastError();
        v10 = v11;
        v9 = 51315092;
        goto LABEL_4;
      }
      if ( AccessStatus )
        *a4 |= 0x10u;
    }
    if ( (v5 & 1) == 0 )
      goto LABEL_32;
    AccessStatus = 0;
    if ( !AccessCheckByType(
            a2,
            0,
            v8,
            0x100u,
            &ObjectTypeList,
            1u,
            &GenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
    {
      v13 = myHLastError();
      v11 = v13;
      if ( v13 )
      {
        v10 = v13;
        v9 = 53019028;
        goto LABEL_4;
      }
    }
    if ( AccessStatus )
    {
      *a4 |= 1u;
LABEL_32:
      if ( (v5 & 2) != 0 )
      {
        AccessStatus = 0;
        if ( !AccessCheckByType(
                a2,
                0,
                v8,
                0x100u,
                &v21,
                1u,
                &GenericMapping,
                &PrivilegeSet,
                &PrivilegeSetLength,
                &GrantedAccess,
                &AccessStatus) )
        {
          v14 = myHLastError();
          v11 = v14;
          if ( v14 )
          {
            v10 = v14;
            v9 = 54985108;
            goto LABEL_4;
          }
        }
        if ( AccessStatus )
          *a4 |= 2u;
      }
    }
LABEL_38:
    v11 = 0;
    goto LABEL_39;
  }
  v9 = 45220244;
LABEL_3:
  v10 = -2147024809;
  v11 = -2147024809;
LABEL_4:
  CSPrintErrorLineFile(v9, v10);
LABEL_39:
  if ( v8 != a1 && v8 )
    CloseHandle(v8);
  return v11;
}

```

## disassembly

```asm
0x180010600  mov     [rsp-8+arg_10], rbx
0x180010605  push    rbp
0x180010606  push    rsi
0x180010607  push    rdi
0x180010608  push    r12
0x18001060a  push    r13
0x18001060c  push    r14
0x18001060e  push    r15
0x180010610  lea     rbp, [rsp-27h]
0x180010615  sub     rsp, 0D0h
0x18001061c  mov     rax, cs:__security_cookie
0x180010623  xor     rax, rsp
0x180010626  mov     [rbp+57h+var_40], rax
0x18001062a  movups  xmm1, xmmword ptr cs:?g_objectTypeAutoEnroll@@3U_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST g_objectTypeAutoEnroll
0x180010631  xor     r13d, r13d
0x180010634  mov     [rbp+57h+var_98], 14h
0x18001063b  xorps   xmm0, xmm0
0x18001063e  mov     [rbp+57h+ClientToken], r13
0x180010642  xor     eax, eax
0x180010644  mov     [rbp+57h+GenericMapping.GenericRead], 110h
0x18001064b  mov     [rbp+57h+var_58.Privilege.Attributes], eax
0x18001064e  mov     rdi, r9
0x180010651  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], 20h ; ' '
0x180010659  mov     r14d, r8d
0x18001065c  mov     [rbp+57h+GenericMapping.GenericAll], 130h
0x180010663  mov     r15, rdx
0x180010666  mov     [rbp+57h+var_A0], r13d
0x18001066a  mov     r12, rcx
0x18001066d  mov     [rbp+57h+var_9C], r13d
0x180010671  mov     esi, r13d
0x180010674  movups  xmmword ptr [rbp+57h+var_58.PrivilegeCount], xmm0
0x180010678  movups  xmm0, xmmword ptr cs:?g_objectTypeEnroll@@3U_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST g_objectTypeEnroll
0x18001067f  movdqu  xmmword ptr [rbp+57h+var_78.Level], xmm1
0x180010684  movdqu  xmmword ptr [rbp+57h+ObjectTypeList.Level], xmm0
0x180010689  test    r9, r9
0x18001068c  jnz     short loc_1800106A4
0x18001068e  mov     ecx, 2B20194h; unsigned int
0x180010693  mov     edx, 80070057h; int
0x180010698  mov     ebx, edx
0x18001069a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001069f  jmp     loc_180010934
0x1800106a4  mov     [r9], r13d
0x1800106a7  test    r14d, 0FFFEFFE0h
0x1800106ae  jz      short loc_1800106B7
0x1800106b0  mov     ecx, 2BE0194h
0x1800106b5  jmp     short loc_180010693
0x1800106b7  test    r15, r15
0x1800106ba  jnz     short loc_1800106CA
0x1800106bc  mov     ebx, 80070005h
0x1800106c1  mov     ecx, 2C50194h; void *
0x1800106c6  mov     edx, ebx
0x1800106c8  jmp     short loc_18001069A
0x1800106ca  mov     edx, r14d
0x1800106cd  lea     r8, [rbp+57h+ClientToken]; void **
0x1800106d1  shr     edx, 10h
0x1800106d4  not     edx
0x1800106d6  and     edx, 1; int
0x1800106d9  call    ?myGetClientToken@@YAJPEAXHPEAPEAX@Z; myGetClientToken(void *,int,void * *)
0x1800106de  mov     ebx, eax
0x1800106e0  test    eax, eax
0x1800106e2  jz      short loc_1800106F9
0x1800106e4  mov     edx, eax; int
0x1800106e6  mov     ecx, 2CC0194h; unsigned int
0x1800106eb  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800106f0  mov     rsi, [rbp+57h+ClientToken]
0x1800106f4  jmp     loc_180010934
0x1800106f9  mov     rsi, [rbp+57h+ClientToken]
0x1800106fd  test    r14b, 4
0x180010701  jz      short loc_180010765
0x180010703  lea     rax, [rbp+57h+var_A0]
0x180010707  mov     [rbp+57h+var_A0], r13d
0x18001070b  mov     [rsp+100h+AccessStatus], rax; AccessStatus
0x180010710  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180010714  lea     rax, [rbp+57h+var_9C]
0x180010718  mov     r8d, 10h; DesiredAccess
0x18001071e  mov     [rsp+100h+GrantedAccess], rax; GrantedAccess
0x180010723  mov     rdx, rsi; ClientToken
0x180010726  lea     rax, [rbp+57h+var_98]
0x18001072a  mov     rcx, r15; pSecurityDescriptor
0x18001072d  mov     [rsp+100h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180010732  lea     rax, [rbp+57h+var_58]
0x180010736  mov     [rsp+100h+PrivilegeSet], rax; PrivilegeSet
0x18001073b  call    cs:__imp_AccessCheck
0x180010741  test    eax, eax
0x180010743  jnz     short loc_180010758
0x180010745  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001074a  mov     ebx, eax
0x18001074c  mov     edx, eax
0x18001074e  mov     ecx, 2DD0194h
0x180010753  jmp     loc_18001069A
0x180010758  cmp     [rbp+57h+var_A0], r13d
0x18001075c  jz      loc_180010931
0x180010762  or      dword ptr [rdi], 4
0x180010765  test    r14b, 8
0x180010769  jz      short loc_1800107C9
0x18001076b  lea     rax, [rbp+57h+var_A0]
0x18001076f  mov     [rbp+57h+var_A0], r13d
0x180010773  mov     [rsp+100h+AccessStatus], rax; AccessStatus
0x180010778  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001077c  lea     rax, [rbp+57h+var_9C]
0x180010780  mov     r8d, 40000h; DesiredAccess
0x180010786  mov     [rsp+100h+GrantedAccess], rax; GrantedAccess
0x18001078b  mov     rdx, rsi; ClientToken
0x18001078e  lea     rax, [rbp+57h+var_98]
0x180010792  mov     rcx, r15; pSecurityDescriptor
0x180010795  mov     [rsp+100h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001079a  lea     rax, [rbp+57h+var_58]
0x18001079e  mov     [rsp+100h+PrivilegeSet], rax; PrivilegeSet
0x1800107a3  call    cs:__imp_AccessCheck
0x1800107a9  test    eax, eax
0x1800107ab  jnz     short loc_1800107C0
0x1800107ad  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800107b2  mov     ebx, eax
0x1800107b4  mov     edx, eax
0x1800107b6  mov     ecx, 2F90194h
0x1800107bb  jmp     loc_18001069A
0x1800107c0  cmp     [rbp+57h+var_A0], r13d
0x1800107c4  jz      short loc_1800107C9
0x1800107c6  or      dword ptr [rdi], 8
0x1800107c9  test    r14b, 10h
0x1800107cd  jz      short loc_18001082D
0x1800107cf  lea     rax, [rbp+57h+var_A0]
0x1800107d3  mov     [rbp+57h+var_A0], r13d
0x1800107d7  mov     [rsp+100h+AccessStatus], rax; AccessStatus
0x1800107dc  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800107e0  lea     rax, [rbp+57h+var_9C]
0x1800107e4  mov     r8d, 80000h; DesiredAccess
0x1800107ea  mov     [rsp+100h+GrantedAccess], rax; GrantedAccess
0x1800107ef  mov     rdx, rsi; ClientToken
0x1800107f2  lea     rax, [rbp+57h+var_98]
0x1800107f6  mov     rcx, r15; pSecurityDescriptor
0x1800107f9  mov     [rsp+100h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800107fe  lea     rax, [rbp+57h+var_58]
0x180010802  mov     [rsp+100h+PrivilegeSet], rax; PrivilegeSet
0x180010807  call    cs:__imp_AccessCheck
0x18001080d  test    eax, eax
0x18001080f  jnz     short loc_180010824
0x180010811  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010816  mov     ebx, eax
0x180010818  mov     edx, eax
0x18001081a  mov     ecx, 30F0194h
0x18001081f  jmp     loc_18001069A
0x180010824  cmp     [rbp+57h+var_A0], r13d
0x180010828  jz      short loc_18001082D
0x18001082a  or      dword ptr [rdi], 10h
0x18001082d  test    r14b, 1
0x180010831  jz      short loc_1800108B1
0x180010833  lea     rax, [rbp+57h+var_A0]
0x180010837  mov     [rbp+57h+var_A0], r13d
0x18001083b  mov     [rsp+100h+var_B0], rax; AccessStatus
0x180010840  mov     r9d, 100h; DesiredAccess
0x180010846  lea     rax, [rbp+57h+var_9C]
0x18001084a  mov     r8, rsi; ClientToken
0x18001084d  mov     [rsp+100h+var_B8], rax; GrantedAccess
0x180010852  xor     edx, edx; PrincipalSelfSid
0x180010854  lea     rax, [rbp+57h+var_98]
0x180010858  mov     rcx, r15; pSecurityDescriptor
0x18001085b  mov     [rsp+100h+var_C0], rax; PrivilegeSetLength
0x180010860  lea     rax, [rbp+57h+var_58]
0x180010864  mov     [rsp+100h+AccessStatus], rax; PrivilegeSet
0x180010869  lea     rax, [rbp+57h+GenericMapping]
0x18001086d  mov     [rsp+100h+GrantedAccess], rax; GenericMapping
0x180010872  lea     rax, [rbp+57h+ObjectTypeList]
0x180010876  mov     dword ptr [rsp+100h+PrivilegeSetLength], 1; ObjectTypeListLength
0x18001087e  mov     [rsp+100h+PrivilegeSet], rax; ObjectTypeList
0x180010883  call    cs:__imp_AccessCheckByType
0x180010889  test    eax, eax
0x18001088b  jnz     short loc_1800108A4
0x18001088d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010892  mov     ebx, eax
0x180010894  test    eax, eax
0x180010896  jz      short loc_1800108A4
0x180010898  mov     edx, eax
0x18001089a  mov     ecx, 3290194h
0x18001089f  jmp     loc_18001069A
0x1800108a4  cmp     [rbp+57h+var_A0], r13d
0x1800108a8  jz      loc_180010931
0x1800108ae  or      dword ptr [rdi], 1
0x1800108b1  test    r14b, 2
0x1800108b5  jz      short loc_180010931
0x1800108b7  lea     rax, [rbp+57h+var_A0]
0x1800108bb  mov     [rbp+57h+var_A0], r13d
0x1800108bf  mov     [rsp+100h+var_B0], rax; AccessStatus
0x1800108c4  mov     r9d, 100h; DesiredAccess
0x1800108ca  lea     rax, [rbp+57h+var_9C]
0x1800108ce  mov     r8, rsi; ClientToken
0x1800108d1  mov     [rsp+100h+var_B8], rax; GrantedAccess
0x1800108d6  xor     edx, edx; PrincipalSelfSid
0x1800108d8  lea     rax, [rbp+57h+var_98]
0x1800108dc  mov     rcx, r15; pSecurityDescriptor
0x1800108df  mov     [rsp+100h+var_C0], rax; PrivilegeSetLength
0x1800108e4  lea     rax, [rbp+57h+var_58]
0x1800108e8  mov     [rsp+100h+AccessStatus], rax; PrivilegeSet
0x1800108ed  lea     rax, [rbp+57h+GenericMapping]
0x1800108f1  mov     [rsp+100h+GrantedAccess], rax; GenericMapping
0x1800108f6  lea     rax, [rbp+57h+var_78]
0x1800108fa  mov     dword ptr [rsp+100h+PrivilegeSetLength], 1; ObjectTypeListLength
0x180010902  mov     [rsp+100h+PrivilegeSet], rax; ObjectTypeList
0x180010907  call    cs:__imp_AccessCheckByType
0x18001090d  test    eax, eax
0x18001090f  jnz     short loc_180010928
0x180010911  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180010916  mov     ebx, eax
0x180010918  test    eax, eax
0x18001091a  jz      short loc_180010928
0x18001091c  mov     edx, eax
0x18001091e  mov     ecx, 3470194h
0x180010923  jmp     loc_18001069A
0x180010928  cmp     [rbp+57h+var_A0], r13d
0x18001092c  jz      short loc_180010931
0x18001092e  or      dword ptr [rdi], 2
0x180010931  mov     ebx, r13d
0x180010934  cmp     rsi, r12
0x180010937  jz      short loc_180010947
0x180010939  test    rsi, rsi
0x18001093c  jz      short loc_180010947
0x18001093e  mov     rcx, rsi; hObject
0x180010941  call    cs:__imp_CloseHandle
0x180010947  mov     eax, ebx
0x180010949  mov     rcx, [rbp+57h+var_40]
0x18001094d  xor     rcx, rsp; StackCookie
0x180010950  call    __security_check_cookie
0x180010955  mov     rbx, [rsp+100h+arg_10]
0x18001095d  add     rsp, 0D0h
0x180010964  pop     r15
0x180010966  pop     r14
0x180010968  pop     r13
0x18001096a  pop     r12
0x18001096c  pop     rdi
0x18001096d  pop     rsi
0x18001096e  pop     rbp
0x18001096f  retn
```
