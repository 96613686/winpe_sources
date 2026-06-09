# _DoAccessCheck

- ea: `0x18002036c`
- end: `0x180020678`
- name: `_DoAccessCheck`
- size: `780`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, unsigned int, wchar_t *, char, LPVOID HandleId, HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f5c0`

## callees

- `0x1800049ac`
- `0x18001fd70`
- `0x18002036c`
- `0x180020710`
- `0x1800254f4`
- `0x18002f0e0`

## import_xrefs

- `ADVAPI32!AreAllAccessesGranted` at `0x18002059d`
- `ADVAPI32!AreAllAccessesGranted` at `0x18002059d`
- `ADVAPI32!ObjectCloseAuditAlarmW` at `0x1800204a1`
- `ADVAPI32!ObjectCloseAuditAlarmW` at `0x1800204a1`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x180020455`
- `ADVAPI32!AccessCheckAndAuditAlarmW` at `0x180020455`
- `ADVAPI32!AccessCheck` at `0x180020537`
- `ADVAPI32!AccessCheck` at `0x180020537`
- `KERNEL32!GetLastError` at `0x18002045f`
- `KERNEL32!GetLastError` at `0x1800204af`
- `KERNEL32!GetLastError` at `0x180020541`
- `KERNEL32!GetLastError` at `0x1800205dd`
- `KERNEL32!GetLastError` at `0x18002045f`
- `KERNEL32!GetLastError` at `0x1800204af`
- `KERNEL32!GetLastError` at `0x180020541`
- `KERNEL32!GetLastError` at `0x1800205dd`

## string_xrefs

- `0x18002040b`: `msmqConfiguration`

## pseudocode

```c
__int64 __fastcall DoAccessCheck(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned int a2,
        wchar_t *a3,
        DWORD a4,
        LPVOID HandleId,
        HANDLE ClientToken)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOL ObjectCreation; // edx
  WCHAR *v12; // r8
  DWORD LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  struct _GENERIC_MAPPING *ObjectGenericMapping; // rax
  WINBOOL GenerateOnClose; // [rsp+60h] [rbp-29h] BYREF
  WINBOOL AccessStatus; // [rsp+64h] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-21h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-19h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  if ( (unsigned int)MQSec_CanGenerateAudit() && a3 )
  {
    GenerateOnClose = 0;
    GenericMapping = GetObjectGenericMapping(a2);
    switch ( a2 )
    {
      case 1u:
        v12 = (WCHAR *)L"Queue";
        break;
      case 2u:
        v12 = L"msmqConfiguration";
        break;
      case 5u:
        v12 = L"Foreign queue";
        break;
      default:
        v12 = 0;
        break;
    }
    if ( !AccessCheckAndAuditAlarmW(
            L"MSMQ",
            HandleId,
            v12,
            a3,
            pSecurityDescriptor,
            a4,
            GenericMapping,
            ObjectCreation,
            &GrantedAccess,
            &AccessStatus,
            &GenerateOnClose) )
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        return 3222143013LL;
      v15 = 28;
LABEL_22:
      WPP_SF_d(v14[32], v15, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
      return 3222143013LL;
    }
    if ( !ObjectCloseAuditAlarmW(L"MSMQ", HandleId, GenerateOnClose) )
    {
      v16 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, v16);
    }
  }
  else
  {
    GenerateOnClose = 32;
    ObjectGenericMapping = GetObjectGenericMapping(a2);
    if ( !AccessCheck(
            pSecurityDescriptor,
            ClientToken,
            a4,
            ObjectGenericMapping,
            &PrivilegeSet,
            (LPDWORD)&GenerateOnClose,
            &GrantedAccess,
            &AccessStatus) )
    {
      LastError = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        return 3222143013LL;
      v15 = 27;
      goto LABEL_22;
    }
  }
  if ( AccessStatus && AreAllAccessesGranted(GrantedAccess, a4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_dDS(*((_QWORD *)WPP_GLOBAL_Control + 32), a4, a3);
    return 0;
  }
  else
  {
    if ( GetLastError() != 1314 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_dDS(*((_QWORD *)WPP_GLOBAL_Control + 32), a4, a3);
      return 3222143013LL;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_dDS(*((_QWORD *)WPP_GLOBAL_Control + 32), a4, a3);
    return 3222143014LL;
  }
}

```

## disassembly

```asm
0x18002036c  push    rbp
0x18002036e  push    rbx
0x18002036f  push    rsi
0x180020370  push    rdi
0x180020371  push    r12
0x180020373  push    r14
0x180020375  push    r15
0x180020377  lea     rbp, [rsp-17h]
0x18002037c  sub     rsp, 0A0h
0x180020383  mov     rax, cs:__security_cookie
0x18002038a  xor     rax, rsp
0x18002038d  mov     [rbp+47h+var_40], rax
0x180020391  mov     r15, [rbp+47h+HandleId]
0x180020395  mov     edi, r9d
0x180020398  mov     r14, [rbp+47h+ClientToken]
0x18002039c  mov     rsi, r8
0x18002039f  mov     ebx, edx
0x1800203a1  mov     [rbp+47h+var_68], 0
0x1800203a8  mov     r12, rcx
0x1800203ab  mov     [rbp+47h+var_6C], 0
0x1800203b2  call    ?MQSec_CanGenerateAudit@@YAHXZ; MQSec_CanGenerateAudit(void)
0x1800203b7  test    eax, eax
0x1800203b9  jz      loc_1800204F9
0x1800203bf  test    rsi, rsi
0x1800203c2  jz      loc_1800204F9
0x1800203c8  xor     edx, edx
0x1800203ca  mov     [rbp+47h+GenerateOnClose], 0
0x1800203d1  mov     eax, ebx
0x1800203d3  sub     eax, 1
0x1800203d6  jz      short loc_1800203E5
0x1800203d8  sub     eax, 1
0x1800203db  jnz     short loc_1800203E5
0x1800203dd  mov     edx, edi
0x1800203df  shr     edx, 2
0x1800203e2  and     edx, 1
0x1800203e5  mov     ecx, ebx; unsigned int
0x1800203e7  call    ?GetObjectGenericMapping@@YAPEAU_GENERIC_MAPPING@@K@Z; GetObjectGenericMapping(ulong)
0x1800203ec  mov     ecx, ebx
0x1800203ee  sub     ecx, 1
0x1800203f1  jz      short loc_180020414
0x1800203f3  sub     ecx, 1
0x1800203f6  jz      short loc_18002040B
0x1800203f8  cmp     ecx, 3
0x1800203fb  jz      short loc_180020402
0x1800203fd  xor     r8d, r8d
0x180020400  jmp     short loc_18002041B
0x180020402  lea     r8, aForeignQueue; "Foreign queue"
0x180020409  jmp     short loc_18002041B
0x18002040b  lea     r8, aMsmqconfigurat; "msmqConfiguration"
0x180020412  jmp     short loc_18002041B
0x180020414  lea     r8, ObjectTypeName; "Queue"
0x18002041b  lea     rcx, [rbp+47h+GenerateOnClose]
0x18002041f  mov     r9, rsi; ObjectName
0x180020422  mov     [rsp+0D0h+pfGenerateOnClose], rcx; pfGenerateOnClose
0x180020427  lea     rcx, [rbp+47h+var_6C]
0x18002042b  mov     [rsp+0D0h+AccessStatus], rcx; AccessStatus
0x180020430  lea     rcx, [rbp+47h+var_68]
0x180020434  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x180020439  lea     rcx, SubsystemName; "MSMQ"
0x180020440  mov     [rsp+0D0h+ObjectCreation], edx; ObjectCreation
0x180020444  mov     rdx, r15; HandleId
0x180020447  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x18002044c  mov     [rsp+0D0h+DesiredAccess], edi; DesiredAccess
0x180020450  mov     [rsp+0D0h+SecurityDescriptor], r12; SecurityDescriptor
0x180020455  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18002045b  test    eax, eax
0x18002045d  jnz     short loc_180020493
0x18002045f  call    cs:__imp_GetLastError
0x180020465  mov     rcx, cs:WPP_GLOBAL_Control
0x18002046c  lea     rdx, WPP_GLOBAL_Control
0x180020473  cmp     rcx, rdx
0x180020476  jz      loc_180020655
0x18002047c  test    byte ptr [rcx+10Ch], 1
0x180020483  jz      loc_180020655
0x180020489  mov     edx, 1Ch
0x18002048e  jmp     loc_180020570
0x180020493  mov     r8d, [rbp+47h+GenerateOnClose]; GenerateOnClose
0x180020497  lea     rcx, SubsystemName; "MSMQ"
0x18002049e  mov     rdx, r15; HandleId
0x1800204a1  call    cs:__imp_ObjectCloseAuditAlarmW
0x1800204a7  test    eax, eax
0x1800204a9  jnz     loc_18002058B
0x1800204af  call    cs:__imp_GetLastError
0x1800204b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204bc  lea     r14, WPP_GLOBAL_Control
0x1800204c3  cmp     rcx, r14
0x1800204c6  jz      loc_180020592
0x1800204cc  test    byte ptr [rcx+10Ch], 1
0x1800204d3  jz      loc_180020592
0x1800204d9  mov     rcx, [rcx+100h]
0x1800204e0  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x1800204e7  mov     edx, 1Dh
0x1800204ec  mov     r9d, eax
0x1800204ef  call    WPP_SF_d
0x1800204f4  jmp     loc_180020592
0x1800204f9  mov     ecx, ebx; unsigned int
0x1800204fb  mov     [rbp+47h+GenerateOnClose], 20h ; ' '
0x180020502  call    ?GetObjectGenericMapping@@YAPEAU_GENERIC_MAPPING@@K@Z; GetObjectGenericMapping(ulong)
0x180020507  mov     r9, rax; GenericMapping
0x18002050a  mov     r8d, edi; DesiredAccess
0x18002050d  lea     rax, [rbp+47h+var_6C]
0x180020511  mov     rdx, r14; ClientToken
0x180020514  mov     qword ptr [rsp+0D0h+ObjectCreation], rax; AccessStatus
0x180020519  mov     rcx, r12; pSecurityDescriptor
0x18002051c  lea     rax, [rbp+47h+var_68]
0x180020520  mov     [rsp+0D0h+GenericMapping], rax; GrantedAccess
0x180020525  lea     rax, [rbp+47h+GenerateOnClose]
0x180020529  mov     qword ptr [rsp+0D0h+DesiredAccess], rax; PrivilegeSetLength
0x18002052e  lea     rax, [rbp+47h+PrivilegeSet]
0x180020532  mov     [rsp+0D0h+SecurityDescriptor], rax; PrivilegeSet
0x180020537  call    cs:__imp_AccessCheck
0x18002053d  test    eax, eax
0x18002053f  jnz     short loc_18002058B
0x180020541  call    cs:__imp_GetLastError
0x180020547  mov     rcx, cs:WPP_GLOBAL_Control
0x18002054e  lea     rdx, WPP_GLOBAL_Control
0x180020555  cmp     rcx, rdx
0x180020558  jz      loc_180020655
0x18002055e  test    byte ptr [rcx+10Ch], 1
0x180020565  jz      loc_180020655
0x18002056b  mov     edx, 1Bh
0x180020570  mov     rcx, [rcx+100h]
0x180020577  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18002057e  mov     r9d, eax
0x180020581  call    WPP_SF_d
0x180020586  jmp     loc_180020655
0x18002058b  lea     r14, WPP_GLOBAL_Control
0x180020592  cmp     [rbp+47h+var_6C], 0
0x180020596  jz      short loc_1800205DD
0x180020598  mov     ecx, [rbp+47h+var_68]; GrantedAccess
0x18002059b  mov     edx, edi; DesiredAccess
0x18002059d  call    cs:__imp_AreAllAccessesGranted
0x1800205a3  test    eax, eax
0x1800205a5  jz      short loc_1800205DD
0x1800205a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205ae  cmp     rcx, r14
0x1800205b1  jz      short loc_1800205D9
0x1800205b3  test    byte ptr [rcx+10Ch], 4
0x1800205ba  jz      short loc_1800205D9
0x1800205bc  mov     rcx, [rcx+100h]; LoggerHandle
0x1800205c3  mov     edx, 1Eh
0x1800205c8  mov     qword ptr [rsp+0D0h+DesiredAccess], rsi; wchar_t *
0x1800205cd  mov     r9d, ebx
0x1800205d0  mov     dword ptr [rsp+0D0h+SecurityDescriptor], edi; char
0x1800205d4  call    WPP_SF_dDS
0x1800205d9  xor     eax, eax
0x1800205db  jmp     short loc_18002065A
0x1800205dd  call    cs:__imp_GetLastError
0x1800205e3  cmp     eax, 522h
0x1800205e8  jnz     short loc_180020623
0x1800205ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205f1  cmp     rcx, r14
0x1800205f4  jz      short loc_18002061C
0x1800205f6  test    byte ptr [rcx+10Ch], 1
0x1800205fd  jz      short loc_18002061C
0x1800205ff  mov     rcx, [rcx+100h]; LoggerHandle
0x180020606  mov     edx, 1Fh
0x18002060b  mov     qword ptr [rsp+0D0h+DesiredAccess], rsi; wchar_t *
0x180020610  mov     r9d, ebx
0x180020613  mov     dword ptr [rsp+0D0h+SecurityDescriptor], edi; char
0x180020617  call    WPP_SF_dDS
0x18002061c  mov     eax, 0C00E0026h
0x180020621  jmp     short loc_18002065A
0x180020623  mov     rcx, cs:WPP_GLOBAL_Control
0x18002062a  cmp     rcx, r14
0x18002062d  jz      short loc_180020655
0x18002062f  test    byte ptr [rcx+10Ch], 1
0x180020636  jz      short loc_180020655
0x180020638  mov     rcx, [rcx+100h]; LoggerHandle
0x18002063f  mov     edx, 20h ; ' '
0x180020644  mov     qword ptr [rsp+0D0h+DesiredAccess], rsi; wchar_t *
0x180020649  mov     r9d, ebx
0x18002064c  mov     dword ptr [rsp+0D0h+SecurityDescriptor], edi; char
0x180020650  call    WPP_SF_dDS
0x180020655  mov     eax, 0C00E0025h
0x18002065a  mov     rcx, [rbp+47h+var_40]
0x18002065e  xor     rcx, rsp; StackCookie
0x180020661  call    __security_check_cookie
0x180020666  add     rsp, 0A0h
0x18002066d  pop     r15
0x18002066f  pop     r14
0x180020671  pop     r12
0x180020673  pop     rdi
0x180020674  pop     rsi
0x180020675  pop     rbx
0x180020676  pop     rbp
0x180020677  retn
```
