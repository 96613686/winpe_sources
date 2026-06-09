# MergeSecurityDescriptorAnyClient

- ea: `0x180121330`
- end: `0x1801218e1`
- name: `MergeSecurityDescriptorAnyClient`
- size: `1457`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005a0c4`
- `0x1800c279c`
- `0x1800cad10`
- `0x18022b2c4`
- `0x1803a37fc`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x1800f80e0`
- `0x1800f8280`
- `0x180105bb4`
- `0x18011cddc`
- `0x18011d6b4`
- `0x180121330`
- `0x180122de4`
- `0x1801236d4`
- `0x180123918`
- `0x180126014`
- `0x1801275ac`
- `0x18016ae88`
- `0x180172b30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180121501`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180121501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801214ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801214ea`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180121660`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180121660`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180121861`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180121861`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorRMControl` at `0x1801217df`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorRMControl` at `0x1801217df`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18012182a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityWithMultipleInheritance` at `0x18012182a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorRMControl` at `0x180121850`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorRMControl` at `0x180121850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012150b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012166a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012150b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012166a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801215f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012189a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801215f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012189a`
- `ntdll!RtlAllocateHeap` at `0x180121413`
- `ntdll!RtlAllocateHeap` at `0x180121413`
- `ntdll!RtlFreeHeap` at `0x1801218b9`
- `ntdll!RtlFreeHeap` at `0x1801218b9`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180121872`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180121872`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1801213e6`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180121447`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1801213e6`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180121447`
- `ntdll!RtlEqualSid` at `0x1801216b1`
- `ntdll!RtlEqualSid` at `0x180121746`
- `ntdll!RtlEqualSid` at `0x1801216b1`
- `ntdll!RtlEqualSid` at `0x180121746`
- `ntdll!RtlLengthSid` at `0x18012167c`
- `ntdll!RtlLengthSid` at `0x18012167c`

## pseudocode

```c
__int64 __fastcall MergeSecurityDescriptorAnyClient(
        __int64 a1,
        void *a2,
        ULONG a3,
        void *a4,
        ULONG SecurityDescriptorLength,
        SECURITY_INFORMATION SecurityInformation,
        char a7,
        GUID **a8,
        ULONG GuidCount,
        void *a10,
        unsigned int a11,
        PSECURITY_DESCRIPTOR *a12,
        ULONG *a13)
{
  PVOID v13; // r15
  PVOID Heap; // rax
  DWORD LastError; // ebx
  int v19; // r14d
  ULONG AutoInheritFlags; // edi
  int v21; // esi
  HANDLE CurrentThread; // rax
  bool v23; // zf
  void *v24; // rcx
  int v25; // esi
  DWORD v26; // eax
  ULONG v27; // eax
  UCHAR RMControl[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  PSID pOwner; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+78h] [rbp-88h] BYREF
  int v35; // [rsp+80h] [rbp-80h] BYREF
  ULONG v36; // [rsp+84h] [rbp-7Ch]
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR ParentDescriptor; // [rsp+98h] [rbp-68h]
  _OWORD *v40; // [rsp+A0h] [rbp-60h] BYREF
  GUID **ObjectTypes; // [rsp+A8h] [rbp-58h]
  ULONG *v42; // [rsp+B0h] [rbp-50h]
  PSECURITY_DESCRIPTOR *v43; // [rsp+B8h] [rbp-48h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD Sid2[2]; // [rsp+D0h] [rbp-30h] BYREF

  v13 = a4;
  Src = a10;
  ObjectTypes = a8;
  v36 = a3;
  ParentDescriptor = a2;
  v43 = a12;
  v42 = a13;
  P = 0;
  v35 = 0;
  NewDescriptor = 0;
  GenericMapping.GenericRead = 131220;
  GenericMapping.GenericWrite = 131112;
  GenericMapping.GenericExecute = 131076;
  GenericMapping.GenericAll = 983551;
  TokenHandle = 0;
  if ( a2 )
  {
    if ( !a4 )
    {
LABEL_11:
      if ( RtlValidRelativeSecurityDescriptor(a2, v36, 0) )
      {
LABEL_13:
        LastError = 0;
        v32 = 1;
        v19 = (a7 & 4) != 0 ? 4123 : 3;
        if ( (a7 & 2) != 0 )
        {
          TokenHandle = 0;
          AutoInheritFlags = v19 | ((a7 & 4) != 0 ? 4216 : 4120);
          if ( (a7 & 0x10) != 0 )
            AutoInheritFlags |= 0x40u;
          v21 = a7 & 1;
LABEL_63:
          if ( v21 )
          {
LABEL_64:
            RMControl[0] = 0;
            v25 = 0;
            if ( !GetSecurityDescriptorRMControl(v13, RMControl) )
            {
              v25 = 1;
              RMControl[0] &= 1u;
            }
            if ( !CreatePrivateObjectSecurityWithMultipleInheritance(
                    ParentDescriptor,
                    v13,
                    &NewDescriptor,
                    ObjectTypes,
                    GuidCount,
                    1,
                    AutoInheritFlags,
                    TokenHandle,
                    &GenericMapping) )
              LastError = GetLastError();
            if ( v25 )
            {
              if ( LastError )
                goto LABEL_74;
              v26 = SetSecurityDescriptorRMControl(NewDescriptor, RMControl);
              if ( v26 )
              {
                LastError = v26;
                DestroyPrivateObjectSecurity(&NewDescriptor);
                goto LABEL_74;
              }
LABEL_73:
              v27 = RtlLengthSecurityDescriptor(NewDescriptor);
              *v42 = v27;
              *v43 = NewDescriptor;
              goto LABEL_74;
            }
LABEL_72:
            if ( LastError )
              goto LABEL_74;
            goto LABEL_73;
          }
          goto LABEL_27;
        }
        if ( (*(_DWORD *)(a1 + 5612) & 0x200000) != 0 )
        {
          TokenHandle = (void *)ADAMGetProxyToken(a1);
          v32 = 0;
        }
        else
        {
          pOwner = 0;
          AssignAuthzClientContext(&pOwner, *(_QWORD *)(a1 + 5960));
          LastError = ImpersonateAnyClient();
          if ( !LastError )
          {
            CurrentThread = GetCurrentThread();
            if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
              LastError = GetLastError();
            UnImpersonateAnyClient();
          }
          AssignAuthzClientContext(a1 + 5960, pOwner);
          AssignAuthzClientContext(&pOwner, 0);
          if ( LastError )
            return LastError;
        }
        v21 = a7 & 1;
        if ( (a7 & 1) == 0 && (SecurityInformation & 1) == 0 )
        {
          AutoInheritFlags = (a7 & 4) != 0 ? 4123 : 3;
          goto LABEL_27;
        }
        LastError = SetDefaultOwner(a1, v13, SecurityDescriptorLength, TokenHandle, Src, a11, &P, &v35);
        if ( LastError )
        {
          if ( TokenHandle && v32 )
            CloseHandle(TokenHandle);
          return LastError;
        }
        if ( v35 )
        {
          v13 = P;
          AutoInheritFlags = v19 | 0x10;
          goto LABEL_63;
        }
        if ( (*(_DWORD *)(a1 + 5612) & 0x200000) == 0 || TokenHandle || (v19 & 0x10) != 0 )
        {
          AutoInheritFlags = (a7 & 4) != 0 ? 4123 : 3;
          goto LABEL_63;
        }
        pOwner = 0;
        memset(Sid2, 0, 28);
        bOwnerDefaulted = 0;
        v29 = 0;
        if ( !GetSecurityDescriptorOwner(v13, &pOwner, &bOwnerDefaulted) )
        {
          LastError = GetLastError();
          goto LABEL_74;
        }
        RtlLengthSid(pOwner);
        LastError = SidMatchesUserSidInToken(pOwner);
        if ( LastError )
        {
LABEL_74:
          if ( TokenHandle && v32 )
            CloseHandle(TokenHandle);
          if ( P )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          return LastError;
        }
        if ( RtlEqualSid(pOwner, gpEnterpriseAdminSid) )
        {
          v23 = (unsigned int)UserIsEnterpriseAdmin(a1) == 0;
        }
        else
        {
          if ( Src && *((_QWORD *)Src + 5) )
          {
            v24 = (void *)(*(_QWORD *)Src + 24LL);
          }
          else
          {
            Src = 0;
            if ( a11 == dword_18052B288 || a11 == dword_18052B2F8 || (unsigned int)NCLGetSID(a11, 0, &v40, &Src) )
            {
LABEL_57:
              LastError = 1307;
              goto LABEL_74;
            }
            v24 = Src;
          }
          v40 = Sid2;
          MakeSid(v24);
          if ( !RtlEqualSid(pOwner, Sid2) )
          {
LABEL_55:
            LastError = CheckPrivilegeAnyClient(18, &v29);
            if ( LastError )
              goto LABEL_74;
            if ( !v29 )
              goto LABEL_57;
LABEL_58:
            AutoInheritFlags = (a7 & 4) != 0 ? 4123 : 3;
            if ( (a7 & 1) != 0 )
            {
              AutoInheritFlags = v19 | 0x10;
              goto LABEL_64;
            }
            if ( (SecurityInformation & 8) == 0 )
              AutoInheritFlags = v19 | 8;
LABEL_27:
            if ( !(unsigned int)SetPrivateObjectSecurityLocalEx(
                                  SecurityInformation,
                                  ParentDescriptor,
                                  v36,
                                  v13,
                                  &NewDescriptor,
                                  AutoInheritFlags,
                                  &GenericMapping,
                                  TokenHandle) )
            {
              LastError = GetLastError();
              if ( !LastError )
                LastError = 8;
              goto LABEL_74;
            }
            goto LABEL_72;
          }
          LastError = CheckGroupMembershipAnyClient(a1, 0, &v40, 1, &v29);
          if ( LastError )
            goto LABEL_74;
          v23 = v29 == 0;
        }
        if ( !v23 )
          goto LABEL_58;
        goto LABEL_55;
      }
      return 1338;
    }
  }
  else if ( !a4 )
  {
    return 1338;
  }
  if ( !RtlValidRelativeSecurityDescriptor(a4, SecurityDescriptorLength, 0) )
    return 1338;
  if ( a2 )
    goto LABEL_11;
  if ( (a7 & 0xA) != 2 )
    goto LABEL_13;
  *a13 = SecurityDescriptorLength;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, SecurityDescriptorLength);
  *a12 = Heap;
  if ( !Heap )
    return 8;
  memcpy_0(Heap, v13, SecurityDescriptorLength);
  return 0;
}

```

## disassembly

```asm
0x180121330  push    rbp
0x180121332  push    rbx
0x180121333  push    rsi
0x180121334  push    rdi
0x180121335  push    r12
0x180121337  push    r13
0x180121339  push    r14
0x18012133b  push    r15
0x18012133d  lea     rbp, [rsp-8]
0x180121342  sub     rsp, 108h
0x180121349  mov     rax, cs:__security_cookie
0x180121350  xor     rax, rsp
0x180121353  mov     [rbp+40h+var_50], rax
0x180121357  mov     rax, [rbp+40h+arg_48]
0x18012135e  mov     r15, r9
0x180121361  mov     r14, [rbp+40h+arg_58]
0x180121368  mov     rbx, rdx
0x18012136b  mov     r12, [rbp+40h+arg_60]
0x180121372  mov     r13, rcx
0x180121375  mov     edi, [rbp+40h+SecurityDescriptorLength]
0x180121378  mov     esi, dword ptr [rbp+40h+arg_30]
0x18012137e  mov     [rsp+140h+Src], rax
0x180121383  mov     rax, [rbp+40h+arg_38]
0x18012138a  mov     [rbp+40h+ObjectTypes], rax
0x18012138e  xor     eax, eax
0x180121390  mov     [rbp+40h+var_BC], r8d
0x180121394  mov     [rbp+40h+ParentDescriptor], rdx
0x180121398  mov     [rbp+40h+var_88], r14
0x18012139c  mov     [rbp+40h+var_90], r12
0x1801213a0  mov     [rbp+40h+P], rax
0x1801213a4  mov     [rbp+40h+var_C0], eax
0x1801213a7  mov     [rsp+140h+NewDescriptor], rax
0x1801213ac  mov     [rbp+40h+var_80.GenericRead], 20094h
0x1801213b3  mov     [rbp+40h+var_80.GenericWrite], 20028h
0x1801213ba  mov     [rbp+40h+var_80.GenericExecute], 20004h
0x1801213c1  mov     [rbp+40h+var_80.GenericAll], 0F01FFh
0x1801213c8  mov     [rsp+140h+TokenHandle], rax
0x1801213cd  test    rdx, rdx
0x1801213d0  jnz     short loc_1801213D9
0x1801213d2  test    r9, r9
0x1801213d5  jz      short loc_180121451
0x1801213d7  jmp     short loc_1801213DE
0x1801213d9  test    r15, r15
0x1801213dc  jz      short loc_18012143E
0x1801213de  xor     r8d, r8d; RequiredInformation
0x1801213e1  mov     edx, edi; SecurityDescriptorLength
0x1801213e3  mov     rcx, r15; SecurityDescriptorInput
0x1801213e6  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1801213ec  test    al, al
0x1801213ee  jz      short loc_180121451
0x1801213f0  test    rbx, rbx
0x1801213f3  jnz     short loc_18012143E
0x1801213f5  mov     eax, esi
0x1801213f7  and     al, 0Ah
0x1801213f9  cmp     al, 2
0x1801213fb  jnz     short loc_18012145B
0x1801213fd  mov     [r12], edi
0x180121401  mov     r8, rdi; Size
0x180121404  mov     rcx, gs:60h
0x18012140d  xor     edx, edx; Flags
0x18012140f  mov     rcx, [rcx+30h]; HeapHandle
0x180121413  call    cs:__imp_RtlAllocateHeap
0x180121419  mov     [r14], rax
0x18012141c  test    rax, rax
0x18012141f  jnz     short loc_180121429
0x180121421  lea     eax, [rbx+8]
0x180121424  jmp     loc_1801218C1
0x180121429  mov     r8, rdi; Size
0x18012142c  mov     rdx, r15; Src
0x18012142f  mov     rcx, rax; void *
0x180121432  call    memcpy_0
0x180121437  xor     eax, eax
0x180121439  jmp     loc_1801218C1
0x18012143e  mov     edx, [rbp+40h+var_BC]; SecurityDescriptorLength
0x180121441  xor     r8d, r8d; RequiredInformation
0x180121444  mov     rcx, rbx; SecurityDescriptorInput
0x180121447  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18012144d  test    al, al
0x18012144f  jnz     short loc_18012145B
0x180121451  mov     eax, 53Ah
0x180121456  jmp     loc_1801218C1
0x18012145b  xor     ebx, ebx
0x18012145d  mov     [rsp+140h+var_D8], 1
0x180121465  mov     ecx, esi
0x180121467  and     ecx, 4
0x18012146a  mov     eax, ecx
0x18012146c  neg     eax
0x18012146e  mov     eax, 1018h
0x180121473  sbb     r14d, r14d
0x180121476  and     r14d, eax
0x180121479  add     r14d, 3
0x18012147d  test    sil, 2
0x180121481  jz      short loc_1801214A5
0x180121483  neg     ecx
0x180121485  mov     [rsp+140h+TokenHandle], rbx
0x18012148a  sbb     edi, edi
0x18012148c  and     edi, 60h
0x18012148f  add     edi, eax
0x180121491  or      edi, r14d
0x180121494  test    sil, 10h
0x180121498  jz      short loc_18012149D
0x18012149a  or      edi, 40h
0x18012149d  and     esi, 1
0x1801214a0  jmp     loc_1801217C8
0x1801214a5  test    dword ptr [r13+15ECh], 200000h
0x1801214b0  jz      short loc_1801214C5
0x1801214b2  mov     rcx, r13
0x1801214b5  call    ADAMGetProxyToken
0x1801214ba  mov     [rsp+140h+TokenHandle], rax
0x1801214bf  mov     [rsp+140h+var_D8], ebx
0x1801214c3  jmp     short loc_180121539
0x1801214c5  lea     r12, [r13+1748h]
0x1801214cc  mov     [rsp+140h+pOwner], rbx
0x1801214d1  mov     rdx, [r12]
0x1801214d5  lea     rcx, [rsp+140h+pOwner]
0x1801214da  call    AssignAuthzClientContext
0x1801214df  call    ImpersonateAnyClient
0x1801214e4  mov     ebx, eax
0x1801214e6  test    eax, eax
0x1801214e8  jnz     short loc_180121518
0x1801214ea  call    cs:__imp_GetCurrentThread
0x1801214f0  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x1801214f5  mov     edx, 20008h; DesiredAccess
0x1801214fa  mov     rcx, rax; ThreadHandle
0x1801214fd  lea     r8d, [rbx+1]; OpenAsSelf
0x180121501  call    cs:__imp_OpenThreadToken
0x180121507  test    eax, eax
0x180121509  jnz     short loc_180121513
0x18012150b  call    cs:__imp_GetLastError
0x180121511  mov     ebx, eax
0x180121513  call    UnImpersonateAnyClient
0x180121518  mov     rdx, [rsp+140h+pOwner]
0x18012151d  mov     rcx, r12
0x180121520  call    AssignAuthzClientContext
0x180121525  xor     edx, edx
0x180121527  lea     rcx, [rsp+140h+pOwner]
0x18012152c  call    AssignAuthzClientContext
0x180121531  test    ebx, ebx
0x180121533  jnz     loc_1801218BF
0x180121539  and     esi, 1
0x18012153c  jnz     short loc_18012159D
0x18012153e  test    byte ptr [rbp+40h+SecurityInformation], 1
0x180121542  jnz     short loc_18012159D
0x180121544  mov     edi, r14d
0x180121547  mov     rax, [rsp+140h+TokenHandle]
0x18012154c  mov     r9, r15; ModificationDescriptor
0x18012154f  mov     r8d, [rbp+40h+var_BC]; Size
0x180121553  mov     rdx, [rbp+40h+ParentDescriptor]; Src
0x180121557  mov     ecx, [rbp+40h+SecurityInformation]; SecurityInformation
0x18012155a  mov     [rsp+140h+Token], rax; HANDLE
0x18012155f  lea     rax, [rbp+40h+var_80]
0x180121563  mov     qword ptr [rsp+140h+AutoInheritFlags], rax; PGENERIC_MAPPING
0x180121568  lea     rax, [rsp+140h+NewDescriptor]
0x18012156d  mov     [rsp+140h+IsContainerObject], edi; AutoInheritFlags
0x180121571  mov     qword ptr [rsp+140h+GuidCount], rax; ObjectsSecurityDescriptor
0x180121576  call    SetPrivateObjectSecurityLocalEx
0x18012157b  xor     edi, edi
0x18012157d  test    eax, eax
0x18012157f  jnz     loc_180121869
0x180121585  call    cs:__imp_GetLastError
0x18012158b  mov     ebx, eax
0x18012158d  test    eax, eax
0x18012158f  jnz     loc_18012188A
0x180121595  lea     ebx, [rdi+8]
0x180121598  jmp     loc_18012188A
0x18012159d  mov     r12d, [rbp+40h+arg_50]
0x1801215a4  lea     rax, [rbp+40h+var_C0]
0x1801215a8  mov     r9, [rsp+140h+TokenHandle]
0x1801215ad  mov     r8d, edi
0x1801215b0  mov     [rsp+140h+Token], rax
0x1801215b5  mov     rdx, r15
0x1801215b8  lea     rax, [rbp+40h+P]
0x1801215bc  mov     rcx, r13
0x1801215bf  mov     qword ptr [rsp+140h+AutoInheritFlags], rax
0x1801215c4  mov     rax, [rsp+140h+Src]
0x1801215c9  mov     [rsp+140h+IsContainerObject], r12d
0x1801215ce  mov     qword ptr [rsp+140h+GuidCount], rax
0x1801215d3  call    SetDefaultOwner
0x1801215d8  xor     edi, edi
0x1801215da  mov     ebx, eax
0x1801215dc  test    eax, eax
0x1801215de  jz      short loc_180121603
0x1801215e0  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x1801215e5  test    rcx, rcx
0x1801215e8  jz      loc_1801218BF
0x1801215ee  cmp     [rsp+140h+var_D8], edi
0x1801215f2  jz      loc_1801218BF
0x1801215f8  call    cs:__imp_CloseHandle
0x1801215fe  jmp     loc_1801218BF
0x180121603  cmp     [rbp+40h+var_C0], edi
0x180121606  jz      short loc_180121617
0x180121608  mov     r15, [rbp+40h+P]
0x18012160c  mov     edi, r14d
0x18012160f  or      edi, 10h
0x180121612  jmp     loc_1801217C8
0x180121617  test    dword ptr [r13+15ECh], 200000h
0x180121622  jz      loc_1801217C5
0x180121628  cmp     [rsp+140h+TokenHandle], rdi
0x18012162d  jnz     loc_1801217C5
0x180121633  test    r14b, 10h
0x180121637  jnz     loc_1801217C5
0x18012163d  xorps   xmm0, xmm0
0x180121640  mov     [rsp+140h+pOwner], rdi
0x180121645  movups  [rbp+40h+Sid2], xmm0
0x180121649  lea     r8, [rbp+40h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18012164d  mov     [rbp+40h+bOwnerDefaulted], edi
0x180121650  lea     rdx, [rsp+140h+pOwner]; pOwner
0x180121655  mov     [rsp+140h+var_EC], edi
0x180121659  mov     rcx, r15; pSecurityDescriptor
0x18012165c  movups  [rbp+40h+Sid2+0Ch], xmm0
0x180121660  call    cs:__imp_GetSecurityDescriptorOwner
0x180121666  test    eax, eax
0x180121668  jnz     short loc_180121677
0x18012166a  call    cs:__imp_GetLastError
0x180121670  mov     ebx, eax
0x180121672  jmp     loc_18012188A
0x180121677  mov     rcx, [rsp+140h+pOwner]; Sid
0x18012167c  call    cs:__imp_RtlLengthSid
0x180121682  mov     rcx, [rsp+140h+pOwner]; Sid2
0x180121687  lea     r8, [rsp+140h+var_EC]
0x18012168c  call    SidMatchesUserSidInToken
0x180121691  mov     ebx, eax
0x180121693  test    eax, eax
0x180121695  jnz     loc_18012188A
0x18012169b  cmp     [rsp+140h+var_EC], edi
0x18012169f  jnz     loc_1801217A7
0x1801216a5  mov     rdx, cs:gpEnterpriseAdminSid; Sid2
0x1801216ac  mov     rcx, [rsp+140h+pOwner]; Sid1
0x1801216b1  call    cs:__imp_RtlEqualSid
0x1801216b7  test    al, al
0x1801216b9  jz      short loc_1801216CA
0x1801216bb  mov     rcx, r13
0x1801216be  call    UserIsEnterpriseAdmin
0x1801216c3  test    eax, eax
0x1801216c5  jmp     loc_18012177C
0x1801216ca  mov     rax, [rsp+140h+Src]
0x1801216cf  test    rax, rax
0x1801216d2  jz      short loc_1801216E3
0x1801216d4  cmp     [rax+28h], rdi
0x1801216d8  jz      short loc_1801216E3
0x1801216da  mov     rcx, [rax]
0x1801216dd  add     rcx, 18h
0x1801216e1  jmp     short loc_180121722
0x1801216e3  cmp     r12d, cs:dword_18052B288
0x1801216ea  mov     [rsp+140h+Src], rdi
0x1801216ef  jz      loc_18012179D
0x1801216f5  cmp     r12d, cs:dword_18052B2F8
0x1801216fc  jz      loc_18012179D
0x180121702  lea     r9, [rsp+140h+Src]
0x180121707  xor     edx, edx
0x180121709  lea     r8, [rbp+40h+var_A0]
0x18012170d  mov     ecx, r12d
0x180121710  call    NCLGetSID
0x180121715  test    eax, eax
0x180121717  jnz     loc_18012179D
0x18012171d  mov     rcx, [rsp+140h+Src]; Src
0x180121722  lea     rax, [rbp+40h+Sid2]
0x180121726  mov     edx, 200h
0x18012172b  lea     r9, [rsp+140h+Src]
0x180121730  mov     [rbp+40h+var_A0], rax
0x180121734  lea     r8, [rbp+40h+Sid2]
0x180121738  call    MakeSid
0x18012173d  mov     rcx, [rsp+140h+pOwner]; Sid1
0x180121742  lea     rdx, [rbp+40h+Sid2]; Sid2
0x180121746  call    cs:__imp_RtlEqualSid
0x18012174c  test    al, al
0x18012174e  jz      short loc_18012177E
0x180121750  lea     rax, [rsp+140h+var_EC]
0x180121755  mov     r9d, 1
0x18012175b  lea     r8, [rbp+40h+var_A0]
0x18012175f  mov     qword ptr [rsp+140h+GuidCount], rax
0x180121764  xor     edx, edx
0x180121766  mov     rcx, r13
0x180121769  call    CheckGroupMembershipAnyClient
0x18012176e  mov     ebx, eax
0x180121770  test    eax, eax
0x180121772  jnz     loc_18012188A
0x180121778  cmp     [rsp+140h+var_EC], edi
0x18012177c  jnz     short loc_1801217A7
0x18012177e  lea     rdx, [rsp+140h+var_EC]
0x180121783  mov     ecx, 12h
0x180121788  call    CheckPrivilegeAnyClient
0x18012178d  mov     ebx, eax
0x18012178f  test    eax, eax
0x180121791  jnz     loc_18012188A
0x180121797  cmp     [rsp+140h+var_EC], edi
0x18012179b  jnz     short loc_1801217A7
0x18012179d  mov     ebx, 51Bh
0x1801217a2  jmp     loc_18012188A
0x1801217a7  mov     edi, r14d
0x1801217aa  test    esi, esi
0x1801217ac  jz      short loc_1801217B3
0x1801217ae  or      edi, 10h
0x1801217b1  jmp     short loc_1801217D0
0x1801217b3  test    byte ptr [rbp+40h+SecurityInformation], 8
0x1801217b7  jnz     loc_180121547
0x1801217bd  or      edi, 8
0x1801217c0  jmp     loc_180121547
0x1801217c5  mov     edi, r14d
0x1801217c8  test    esi, esi
  ... truncated ...
```
