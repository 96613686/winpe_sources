# LsaDbpRequestAccessTDObject(void *,_LSAP_DB_OBJECT_INFORMATION *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,long *)

- ea: `0x180016090`
- end: `0x180016338`
- name: `?LsaDbpRequestAccessTDObject@@YAJPEAXPEAU_LSAP_DB_OBJECT_INFORMATION@@PEAU_UNICODE_STRING@@2KPEAKPEAJ@Z`
- size: `680`
- prototype: `__int64 __fastcall(void *, struct _LSAP_DB_OBJECT_INFORMATION *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, ACCESS_MASK, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001670`
- `0x180016090`

## import_xrefs

- `LSASRV!LsapDbGetDbObjectTypeName` at `0x18001619e`
- `LSASRV!LsapDbGetDbObjectTypeName` at `0x18001619e`
- `ntdll!RtlAreAllAccessesGranted` at `0x1800162f2`
- `ntdll!RtlAreAllAccessesGranted` at `0x1800162f2`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x180016218`
- `ntdll!NtAccessCheckByTypeResultListAndAuditAlarm` at `0x180016218`

## pseudocode

```c
__int64 __fastcall LsaDbpRequestAccessTDObject(
        void *a1,
        struct _LSAP_DB_OBJECT_INFORMATION *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        ACCESS_MASK a5,
        unsigned int *a6,
        int *a7)
{
  unsigned int v8; // edx
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 *v11; // r15
  unsigned int v12; // r13d
  struct _OBJECT_TYPE_LIST *ObjectTypeList; // r14
  int v14; // eax
  void *SecurityDescriptor; // rbx
  struct _UNICODE_STRING *v16; // rdi
  struct _UNICODE_STRING *DbObjectTypeName; // rax
  ULONG v18; // eax
  ULONG i; // r8d
  unsigned int v20; // r10d
  __int64 v21; // r9
  GUID *ObjectType; // r14
  _QWORD *v23; // rdi
  char v25; // [rsp+80h] [rbp-80h]
  ULONG ObjectTypeListLength; // [rsp+84h] [rbp-7Ch]
  unsigned int v27; // [rsp+88h] [rbp-78h]
  struct _OBJECT_TYPE_LIST *v28; // [rsp+90h] [rbp-70h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+A8h] [rbp-58h] BYREF
  int AccessStatusList[16]; // [rsp+B8h] [rbp-48h] BYREF
  DWORD GrantedAccessList[16]; // [rsp+F8h] [rbp-8h] BYREF

  v8 = *((_DWORD *)a1 + 26);
  v27 = v8;
  *a6 = 0;
  *a7 = -1073741790;
  GenericMapping.GenericRead = 131220;
  GenericMapping.GenericWrite = 131112;
  GenericMapping.GenericExecute = 131200;
  GenericMapping.GenericAll = 983551;
  if ( v8 == 2 )
  {
    v11 = qword_180047200;
    v14 = *((_DWORD *)a1 + 34) & 0x400000;
    if ( !v14 )
      v11 = qword_180047230;
    v12 = v14 != 0 ? 2 : 5;
  }
  else
  {
    v9 = -1073741802;
    if ( v8 != 4 )
      return v9;
    v10 = *((_DWORD *)a1 + 34);
    if ( (v10 & 0x400000) == 0 )
    {
      if ( (v10 & 0x100000) == 0 )
        return v9;
      ObjectTypeList = &GlobalSecretTypeList;
      ObjectTypeListLength = 6;
      v12 = 2;
      v11 = qword_1800470E0;
      goto LABEL_11;
    }
    v11 = qword_180047200;
    v12 = 2;
  }
  ObjectTypeList = (struct _OBJECT_TYPE_LIST *)&TrustedDomainTypeList;
  ObjectTypeListLength = 15;
LABEL_11:
  SecurityDescriptor = (void *)*((_QWORD *)a2 + 5);
  v16 = (struct _UNICODE_STRING *)*((_QWORD *)a2 + 3);
  v28 = ObjectTypeList;
  DbObjectTypeName = (struct _UNICODE_STRING *)LsapDbGetDbObjectTypeName(v8);
  v9 = NtAccessCheckByTypeResultListAndAuditAlarm(
         &LsaDbpSubsystemName,
         a1,
         DbObjectTypeName,
         v16,
         SecurityDescriptor,
         0,
         a5 & 0x1000000 | 0x2000000,
         AuditEventObjectAccess,
         0,
         ObjectTypeList,
         ObjectTypeListLength,
         &GenericMapping,
         0,
         GrantedAccessList,
         AccessStatusList,
         (PBOOLEAN)a1 + 132);
  if ( (v9 & 0x80000000) == 0 && ((v27 - 2) & 0xFFFFFFFD) == 0 )
  {
    v25 = 0;
    *a6 = 0;
    if ( AccessStatusList[0] >= 0 )
      *a6 = GrantedAccessList[0] & 0x11F0000;
    v18 = ObjectTypeListLength;
    for ( i = 0; i < v18; ++i )
    {
      if ( AccessStatusList[i] >= 0 )
      {
        v25 = 1;
        v20 = 0;
        v21 = 0;
        do
        {
          ObjectType = v28[i].ObjectType;
          v23 = (_QWORD *)v11[3 * v21 + 2];
          if ( *v23 == *(_QWORD *)&ObjectType->Data1
            && v23[1] == *(_QWORD *)ObjectType->Data4
            && (HIDWORD(v11[3 * v21]) & GrantedAccessList[i]) != 0 )
          {
            *a6 |= LODWORD(v11[3 * v21]);
          }
          ++v20;
          ++v21;
        }
        while ( v20 < v12 );
        v18 = ObjectTypeListLength;
      }
    }
    if ( v27 == 2 )
      *a6 |= 6u;
    if ( v25 )
    {
      if ( (a5 & 0x2000000) != 0 )
      {
LABEL_31:
        *a7 = 0;
        return v9;
      }
      if ( RtlAreAllAccessesGranted(*a6, a5) )
      {
        *a6 = a5;
        goto LABEL_31;
      }
    }
    *a6 = 0;
    *a7 = -1073741790;
  }
  return v9;
}

```

## disassembly

```asm
0x180016090  mov     [rsp-8+arg_10], rbx
0x180016095  push    rbp
0x180016096  push    rsi
0x180016097  push    rdi
0x180016098  push    r12
0x18001609a  push    r13
0x18001609c  push    r14
0x18001609e  push    r15
0x1800160a0  lea     rbp, [rsp-40h]
0x1800160a5  sub     rsp, 140h
0x1800160ac  mov     rax, cs:__security_cookie
0x1800160b3  xor     rax, rsp
0x1800160b6  mov     [rbp+70h+var_38], rax
0x1800160ba  mov     r12, [rbp+70h+arg_30]
0x1800160c1  mov     rdi, rdx
0x1800160c4  mov     edx, [rcx+68h]
0x1800160c7  mov     r8d, 2
0x1800160cd  mov     rsi, [rbp+70h+arg_28]
0x1800160d4  mov     [rbp+70h+HandleId], rcx
0x1800160d8  mov     [rbp+70h+var_D0], r12
0x1800160dc  mov     [rbp+70h+var_E8], edx
0x1800160df  mov     dword ptr [rsi], 0
0x1800160e5  mov     dword ptr [r12], 0C0000022h
0x1800160ed  mov     [rbp+70h+var_C8.GenericRead], 20094h
0x1800160f4  mov     [rbp+70h+var_C8.GenericWrite], 20028h
0x1800160fb  mov     [rbp+70h+var_C8.GenericExecute], 20080h
0x180016102  mov     [rbp+70h+var_C8.GenericAll], 0F01FFh
0x180016109  cmp     edx, r8d
0x18001610c  jz      short loc_180016158
0x18001610e  mov     ebx, 0C0000016h
0x180016113  cmp     edx, 4
0x180016116  jnz     loc_18001630F
0x18001611c  mov     ecx, [rcx+88h]
0x180016122  bt      ecx, 16h
0x180016126  jnb     short loc_180016134
0x180016128  lea     r15, qword_180047200
0x18001612f  mov     r13d, r8d
0x180016132  jmp     short loc_180016182
0x180016134  bt      ecx, 14h
0x180016138  jnb     loc_18001630F
0x18001613e  lea     r14, ?GlobalSecretTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * GlobalSecretTypeList
0x180016145  mov     [rbp+70h+var_EC], 6
0x18001614c  mov     r13d, r8d
0x18001614f  lea     r15, qword_1800470E0
0x180016156  jmp     short loc_180016190
0x180016158  mov     eax, [rcx+88h]
0x18001615e  lea     r15, qword_180047200
0x180016165  and     eax, 400000h
0x18001616a  lea     rcx, qword_180047230
0x180016171  cmovz   r15, rcx
0x180016175  neg     eax
0x180016177  sbb     r13d, r13d
0x18001617a  and     r13d, 0FFFFFFFDh
0x18001617e  add     r13d, 5
0x180016182  lea     r14, ?TrustedDomainTypeList@@3PAU_OBJECT_TYPE_LIST@@A; _OBJECT_TYPE_LIST near * TrustedDomainTypeList
0x180016189  mov     [rbp+70h+var_EC], 0Fh
0x180016190  mov     rbx, [rdi+28h]
0x180016194  mov     ecx, edx
0x180016196  mov     rdi, [rdi+18h]
0x18001619a  mov     [rbp+70h+var_E0], r14
0x18001619e  call    cs:__imp_LsapDbGetDbObjectTypeName
0x1800161a4  mov     rdx, [rbp+70h+HandleId]; HandleId
0x1800161a8  mov     r9, rdi; ObjectName
0x1800161ab  mov     ecx, [rbp+70h+arg_20]
0x1800161b1  mov     r8, rax; ObjectTypeName
0x1800161b4  and     ecx, 1000000h
0x1800161ba  bts     ecx, 19h
0x1800161be  lea     rax, [rdx+84h]
0x1800161c5  mov     [rsp+170h+GenerateOnClose], rax; GenerateOnClose
0x1800161ca  lea     rax, [rbp+70h+var_B8]
0x1800161ce  mov     [rsp+170h+AccessStatusList], rax; AccessStatusList
0x1800161d3  lea     rax, [rbp+70h+var_78]
0x1800161d7  mov     [rsp+170h+GrantedAccessList], rax; GrantedAccessList
0x1800161dc  lea     rax, [rbp+70h+var_C8]
0x1800161e0  mov     [rsp+170h+ObjectCreation], 0; ObjectCreation
0x1800161e5  mov     [rsp+170h+GenericMapping], rax; GenericMapping
0x1800161ea  mov     eax, [rbp+70h+var_EC]
0x1800161ed  mov     [rsp+170h+ObjectTypeListLength], eax; ObjectTypeListLength
0x1800161f1  mov     [rsp+170h+ObjectTypeList], r14; ObjectTypeList
0x1800161f6  xor     r14d, r14d
0x1800161f9  mov     [rsp+170h+Flags], r14d; Flags
0x1800161fe  mov     [rsp+170h+AuditType], r14d; AuditType
0x180016203  mov     [rsp+170h+DesiredAccess], ecx; DesiredAccess
0x180016207  lea     rcx, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; SubsystemName
0x18001620e  mov     [rsp+170h+PrincipalSelfSid], r14; PrincipalSelfSid
0x180016213  mov     [rsp+170h+SecurityDescriptor], rbx; SecurityDescriptor
0x180016218  call    cs:__imp_NtAccessCheckByTypeResultListAndAuditAlarm
0x18001621e  mov     ebx, eax
0x180016220  test    eax, eax
0x180016222  js      loc_18001630F
0x180016228  mov     ecx, [rbp+70h+var_E8]
0x18001622b  add     ecx, 0FFFFFFFEh
0x18001622e  test    ecx, 0FFFFFFFDh
0x180016234  jnz     loc_18001630F
0x18001623a  mov     [rbp+70h+var_F0], r14b
0x18001623e  mov     [rsi], r14d
0x180016241  cmp     [rbp+70h+var_B8], r14d
0x180016245  jl      short loc_180016251
0x180016247  mov     eax, [rbp+70h+var_78]
0x18001624a  and     eax, 11F0000h
0x18001624f  mov     [rsi], eax
0x180016251  mov     eax, [rbp+70h+var_EC]
0x180016254  mov     r8d, r14d
0x180016257  mov     rdx, [rbp+70h+var_E0]
0x18001625b  mov     ecx, r8d
0x18001625e  cmp     [rbp+rcx*4+70h+var_B8], r14d
0x180016263  jl      short loc_1800162C4
0x180016265  mov     r9b, 1
0x180016268  mov     [rbp+70h+var_F0], r9b
0x18001626c  test    r13d, r13d
0x18001626f  jz      short loc_1800162C8
0x180016271  lea     rax, [rbp+70h+var_78]
0x180016275  mov     r10d, r14d
0x180016278  lea     r12, [rax+rcx*4]
0x18001627c  mov     r9, r14
0x18001627f  add     rcx, rcx
0x180016282  mov     r14, [rdx+rcx*8+8]
0x180016287  lea     r11, [r9+r9*2]
0x18001628b  mov     rdi, [r15+r11*8+10h]
0x180016290  mov     rax, [rdi]
0x180016293  cmp     rax, [r14]
0x180016296  jnz     short loc_1800162B3
0x180016298  mov     rax, [rdi+8]
0x18001629c  cmp     rax, [r14+8]
0x1800162a0  jnz     short loc_1800162B3
0x1800162a2  mov     eax, [r15+r11*8+4]
0x1800162a7  test    [r12], eax
0x1800162ab  jz      short loc_1800162B3
0x1800162ad  mov     eax, [r15+r11*8]
0x1800162b1  or      [rsi], eax
0x1800162b3  inc     r10d
0x1800162b6  inc     r9
0x1800162b9  cmp     r10d, r13d
0x1800162bc  jb      short loc_180016282
0x1800162be  mov     eax, [rbp+70h+var_EC]
0x1800162c1  xor     r14d, r14d
0x1800162c4  mov     r9b, [rbp+70h+var_F0]
0x1800162c8  inc     r8d
0x1800162cb  cmp     r8d, eax
0x1800162ce  jb      short loc_18001625B
0x1800162d0  cmp     [rbp+70h+var_E8], 2
0x1800162d4  mov     r12, [rbp+70h+var_D0]
0x1800162d8  jnz     short loc_1800162DD
0x1800162da  or      dword ptr [rsi], 6
0x1800162dd  test    r9b, r9b
0x1800162e0  jz      short loc_180016304
0x1800162e2  mov     edi, [rbp+70h+arg_20]
0x1800162e8  bt      edi, 19h
0x1800162ec  jb      short loc_1800162FE
0x1800162ee  mov     ecx, [rsi]; GrantedAccess
0x1800162f0  mov     edx, edi; DesiredAccess
0x1800162f2  call    cs:__imp_RtlAreAllAccessesGranted
0x1800162f8  test    al, al
0x1800162fa  jz      short loc_180016304
0x1800162fc  mov     [rsi], edi
0x1800162fe  mov     [r12], r14d
0x180016302  jmp     short loc_18001630F
0x180016304  mov     [rsi], r14d
0x180016307  mov     dword ptr [r12], 0C0000022h
0x18001630f  mov     eax, ebx
0x180016311  mov     rcx, [rbp+70h+var_38]
0x180016315  xor     rcx, rsp; StackCookie
0x180016318  call    __security_check_cookie
0x18001631d  mov     rbx, [rsp+170h+arg_10]
0x180016325  add     rsp, 140h
0x18001632c  pop     r15
0x18001632e  pop     r14
0x180016330  pop     r13
0x180016332  pop     r12
0x180016334  pop     rdi
0x180016335  pop     rsi
0x180016336  pop     rbp
0x180016337  retn
```
