# VerifyAccessToExclusion

- ea: `0x14005bd30`
- end: `0x14005bf4f`
- name: `VerifyAccessToExclusion`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005bcdc`

## callees

- `0x14005bd30`
- `0x14005e9cc`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005bf20`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005bf20`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005bf0c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005bf0c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005befc`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005befc`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005beec`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005beec`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005bdf0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005bdf0`
- `ntoskrnl!SeAccessCheck` at `0x14005be39`
- `ntoskrnl!SeAccessCheck` at `0x14005be39`
- `ntoskrnl!SeLockSubjectContext` at `0x14005bde4`
- `ntoskrnl!SeLockSubjectContext` at `0x14005bde4`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005bdd4`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005bdd4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be52`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be69`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be52`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be69`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005be9f`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x14005bd88`
- `NETIO!NsiReferenceDefaultObjectSecurity` at `0x14005bd88`

## pseudocode

```c
__int64 __fastcall VerifyAccessToExclusion(__int64 a1, struct _KPROCESS *a2)
{
  __int64 result; // rax
  struct _KPROCESS *v4; // rdx
  void *v6; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v8; // bl
  ACCESS_MASK PreviouslyGrantedAccess[2]; // [rsp+20h] [rbp-89h]
  int AccessStatus; // [rsp+48h] [rbp-61h]
  _BYTE v11[4]; // [rsp+60h] [rbp-49h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-45h] BYREF
  int v13; // [rsp+68h] [rbp-41h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v15; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING v16; // [rsp+A0h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp+7h] BYREF
  wchar_t pszDest[20]; // [rsp+C0h] [rbp+17h] BYREF

  result = 0;
  v4 = *(struct _KPROCESS **)(a1 + 40);
  v13 = 0;
  if ( a2 != v4 )
  {
    if ( a2 )
    {
      if ( v4 )
      {
        return 3221225506LL;
      }
      else
      {
        v6 = (void *)NsiReferenceDefaultObjectSecurity();
        if ( v6 )
        {
          v11[0] = 0;
          GrantedAccess = 0;
          v15 = 0;
          v16 = 0;
          memset(&SubjectContext, 0, sizeof(SubjectContext));
          DestinationString = 0;
          SeCaptureSubjectContextEx(0, a2, &SubjectContext);
          SeLockSubjectContext(&SubjectContext);
          GenericMapping = IoGetFileObjectGenericMapping();
          v8 = SeAccessCheck(v6, &SubjectContext, 1u, 3u, 0, 0, GenericMapping, 1, &GrantedAccess, &v13);
          RtlInitUnicodeString(&DestinationString, L"TCP/IP");
          RtlInitUnicodeString(&v16, L"InternetPortReservation");
          PreviouslyGrantedAccess[0] = *(unsigned __int16 *)(a1 + 10);
          RtlStringCbPrintfW(
            pszDest,
            0x28u,
            L"Ports %u-%u",
            *(unsigned __int16 *)(a1 + 8),
            *(_QWORD *)PreviouslyGrantedAccess);
          RtlInitUnicodeString(&v15, pszDest);
          LOBYTE(AccessStatus) = v8;
          SeOpenObjectAuditAlarmForNonObObject(
            &DestinationString,
            0,
            &v16,
            &v15,
            v6,
            &SubjectContext,
            3,
            GrantedAccess,
            0,
            AccessStatus,
            v11);
          SeUnlockSubjectContext(&SubjectContext);
          SeReleaseSubjectContext(&SubjectContext);
          ObDereferenceSecurityDescriptor(v6, 1);
          return (unsigned int)v13;
        }
        else
        {
          return 3221225687LL;
        }
      }
    }
    else
    {
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14005bd30  mov     [rsp-8+arg_10], rbx
0x14005bd35  push    rbp
0x14005bd36  push    rsi
0x14005bd37  push    rdi
0x14005bd38  lea     rbp, [rsp-47h]
0x14005bd3d  sub     rsp, 0F0h
0x14005bd44  mov     rax, cs:__security_cookie
0x14005bd4b  xor     rax, rsp
0x14005bd4e  mov     [rbp+57h+var_18], rax
0x14005bd52  mov     rbx, rdx
0x14005bd55  xor     eax, eax
0x14005bd57  mov     rdx, [rcx+28h]
0x14005bd5b  mov     rsi, rcx
0x14005bd5e  mov     [rbp+57h+var_98], eax
0x14005bd61  cmp     rbx, rdx
0x14005bd64  jz      loc_14005BF2F
0x14005bd6a  test    rbx, rbx
0x14005bd6d  jnz     short loc_14005BD79
0x14005bd6f  mov     eax, 0C000000Dh
0x14005bd74  jmp     loc_14005BF2F
0x14005bd79  test    rdx, rdx
0x14005bd7c  jz      short loc_14005BD88
0x14005bd7e  mov     eax, 0C0000022h
0x14005bd83  jmp     loc_14005BF2F
0x14005bd88  call    cs:__imp_NsiReferenceDefaultObjectSecurity
0x14005bd8f  nop     dword ptr [rax+rax+00h]
0x14005bd94  mov     rdi, rax
0x14005bd97  test    rax, rax
0x14005bd9a  jnz     short loc_14005BDA6
0x14005bd9c  mov     eax, 0C00000D7h
0x14005bda1  jmp     loc_14005BF2F
0x14005bda6  xorps   xmm0, xmm0
0x14005bda9  mov     [rbp+57h+var_A0], 0
0x14005bdad  xorps   xmm1, xmm1
0x14005bdb0  mov     [rbp+57h+var_9C], 0
0x14005bdb7  lea     r8, [rbp+57h+SubjectContext]; SubjectContext
0x14005bdbb  mov     rdx, rbx; Process
0x14005bdbe  xor     ecx, ecx; Thread
0x14005bdc0  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x14005bdc4  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x14005bdc8  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14005bdcc  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14005bdd0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005bdd4  call    cs:__imp_SeCaptureSubjectContextEx
0x14005bddb  nop     dword ptr [rax+rax+00h]
0x14005bde0  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005bde4  call    cs:__imp_SeLockSubjectContext
0x14005bdeb  nop     dword ptr [rax+rax+00h]
0x14005bdf0  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005bdf7  nop     dword ptr [rax+rax+00h]
0x14005bdfc  lea     rcx, [rbp+57h+var_98]
0x14005be00  mov     r9d, 3; DesiredAccess
0x14005be06  mov     [rsp+100h+AccessStatus], rcx; AccessStatus
0x14005be0b  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x14005be0f  lea     rcx, [rbp+57h+var_9C]
0x14005be13  mov     r8b, 1; SubjectContextLocked
0x14005be16  mov     [rsp+100h+GrantedAccess], rcx; GrantedAccess
0x14005be1b  mov     rcx, rdi; SecurityDescriptor
0x14005be1e  mov     [rsp+100h+AccessMode], 1; AccessMode
0x14005be23  mov     [rsp+100h+GenericMapping], rax; GenericMapping
0x14005be28  mov     [rsp+100h+Privileges], 0; Privileges
0x14005be31  mov     [rsp+100h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14005be39  call    cs:__imp_SeAccessCheck
0x14005be40  nop     dword ptr [rax+rax+00h]
0x14005be45  lea     rdx, SourceString; "TCP/IP"
0x14005be4c  mov     bl, al
0x14005be4e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005be52  call    cs:__imp_RtlInitUnicodeString
0x14005be59  nop     dword ptr [rax+rax+00h]
0x14005be5e  lea     rdx, aInternetportre; "InternetPortReservation"
0x14005be65  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14005be69  call    cs:__imp_RtlInitUnicodeString
0x14005be70  nop     dword ptr [rax+rax+00h]
0x14005be75  movzx   eax, word ptr [rsi+0Ah]
0x14005be79  lea     r8, aPortsUU; "Ports %u-%u"
0x14005be80  movzx   r9d, word ptr [rsi+8]
0x14005be85  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14005be89  mov     edx, 28h ; '('; cbDest
0x14005be8e  mov     [rsp+100h+PreviouslyGrantedAccess], eax
0x14005be92  call    RtlStringCbPrintfW
0x14005be97  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14005be9b  lea     rcx, [rbp+57h+var_70]; DestinationString
0x14005be9f  call    cs:__imp_RtlInitUnicodeString
0x14005bea6  nop     dword ptr [rax+rax+00h]
0x14005beab  lea     rax, [rbp+57h+var_A0]
0x14005beaf  xor     edx, edx
0x14005beb1  mov     [rsp+100h+var_B0], rax
0x14005beb6  lea     r9, [rbp+57h+var_70]
0x14005beba  mov     eax, [rbp+57h+var_9C]
0x14005bebd  lea     r8, [rbp+57h+var_60]
0x14005bec1  mov     byte ptr [rsp+100h+AccessStatus], bl
0x14005bec5  lea     rcx, [rbp+57h+DestinationString]
0x14005bec9  mov     [rsp+100h+GrantedAccess], 0
0x14005bed2  mov     dword ptr [rsp+100h+AccessMode], eax
0x14005bed6  lea     rax, [rbp+57h+SubjectContext]
0x14005beda  mov     dword ptr [rsp+100h+GenericMapping], 3
0x14005bee2  mov     [rsp+100h+Privileges], rax
0x14005bee7  mov     qword ptr [rsp+100h+PreviouslyGrantedAccess], rdi
0x14005beec  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x14005bef3  nop     dword ptr [rax+rax+00h]
0x14005bef8  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005befc  call    cs:__imp_SeUnlockSubjectContext
0x14005bf03  nop     dword ptr [rax+rax+00h]
0x14005bf08  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005bf0c  call    cs:__imp_SeReleaseSubjectContext
0x14005bf13  nop     dword ptr [rax+rax+00h]
0x14005bf18  mov     edx, 1
0x14005bf1d  mov     rcx, rdi
0x14005bf20  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14005bf27  nop     dword ptr [rax+rax+00h]
0x14005bf2c  mov     eax, [rbp+57h+var_98]
0x14005bf2f  mov     rcx, [rbp+57h+var_18]
0x14005bf33  xor     rcx, rsp; StackCookie
0x14005bf36  call    __security_check_cookie
0x14005bf3b  mov     rbx, [rsp+100h+arg_10]
0x14005bf43  add     rsp, 0F0h
0x14005bf4a  pop     rdi
0x14005bf4b  pop     rsi
0x14005bf4c  pop     rbp
0x14005bf4d  retn
```
