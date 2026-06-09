# LsapNotifyInitializationFinish(long)

- ea: `0x1800957b8`
- end: `0x180095b99`
- name: `?LsapNotifyInitializationFinish@@YAXJ@Z`
- size: `993`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ad714`

## callees

- `0x180011278`
- `0x1800957b8`
- `0x1800ada18`
- `0x1800b1cc8`
- `0x1800b86d0`
- `0x1800dbdd4`
- `0x1800dbe80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009595f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009595f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009597b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009597b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095a14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095a14`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180095a04`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180095a04`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800959cd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800959cd`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180095945`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180095945`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800959e9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800959e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180095a20`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180095a20`
- `ntdll!NtClose` at `0x18009592f`
- `ntdll!NtClose` at `0x18009592f`
- `ntdll!NtShutdownSystem` at `0x180095b32`
- `ntdll!NtShutdownSystem` at `0x180095b32`
- `ntdll!RtlAdjustPrivilege` at `0x180095b00`
- `ntdll!RtlAdjustPrivilege` at `0x180095b70`
- `ntdll!RtlAdjustPrivilege` at `0x180095b00`
- `ntdll!RtlAdjustPrivilege` at `0x180095b70`
- `ntdll!NtRaiseHardError` at `0x180095a81`
- `ntdll!NtRaiseHardError` at `0x180095a81`
- `ntdll!NtSetEvent` at `0x1800958f1`
- `ntdll!NtSetEvent` at `0x1800958f1`
- `ntdll!NtOpenEvent` at `0x1800958a8`
- `ntdll!NtOpenEvent` at `0x1800958a8`
- `ntdll!NtCreateEvent` at `0x180095887`
- `ntdll!NtCreateEvent` at `0x180095887`
- `ntdll!RtlInitUnicodeString` at `0x180095846`
- `ntdll!RtlInitUnicodeString` at `0x180095846`

## string_xrefs

- `0x18009583b`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
void __fastcall LsapNotifyInitializationFinish(int a1)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // eax
  WINBOOL v4; // edi
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned __int8 OldValue[4]; // [rsp+60h] [rbp-59h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp-55h] BYREF
  void *EventHandle; // [rsp+68h] [rbp-51h] BYREF
  ULONG Response; // [rsp+70h] [rbp-49h] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int64 Parameters; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+17h] BYREF

  Response = 0;
  DestinationString = 0;
  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, (unsigned int)a1);
  if ( a1 < 0 )
  {
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      v4 = 0;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        IsMember = 0;
        SidToCheck = 0;
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
        {
          if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
            v4 = IsMember;
          if ( SidToCheck )
            FreeSid(SidToCheck);
        }
        CloseHandle(TokenHandle);
      }
      RevertToSelf();
      if ( v4 )
      {
        Parameters = 65552;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
        v6 = NtRaiseHardError(a1 | 0x10000000, 1u, 0, &Parameters, 1u, &Response);
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v6);
        if ( SpmpIsSetupPass() && !SpmpIsMiniSetupPass() )
        {
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
          LsapMarkBootGood();
        }
        OldValue[0] = 0;
        RtlAdjustPrivilege(0x13u, 1u, 0, OldValue);
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
        v7 = NtShutdownSystem(ShutdownReboot);
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v7);
        RtlAdjustPrivilege(0x13u, OldValue[0], 0, OldValue);
      }
    }
  }
  else
  {
    LsapMarkBootGood();
    RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtCreateEvent(&EventHandle, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
    if ( v2 >= 0 || v2 == -1073741771 && (v2 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes), v2 >= 0) )
    {
      v3 = NtSetEvent(EventHandle, 0);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
            (unsigned int)v3);
        NtClose(EventHandle);
      }
    }
    else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v2);
    }
  }
}

```

## disassembly

```asm
0x1800957b8  push    rbp
0x1800957ba  push    rbx
0x1800957bb  push    rsi
0x1800957bc  push    rdi
0x1800957bd  push    r12
0x1800957bf  push    r15
0x1800957c1  lea     rbp, [rsp-2Fh]
0x1800957c6  sub     rsp, 0E8h
0x1800957cd  mov     rax, cs:__security_cookie
0x1800957d4  xor     rax, rsp
0x1800957d7  mov     [rbp+57h+var_38], rax
0x1800957db  xorps   xmm1, xmm1
0x1800957de  xor     esi, esi
0x1800957e0  xorps   xmm0, xmm0
0x1800957e3  mov     [rbp+57h+Response], esi
0x1800957e6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800957ea  mov     [rbp+57h+EventHandle], rsi
0x1800957ee  mov     ebx, ecx
0x1800957f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800957f4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800957f8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800957fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180095803  lea     r12, WPP_GLOBAL_Control
0x18009580a  lea     r15, WPP_fbab38a9e468344a0955481828104e3b_Traceguids
0x180095811  cmp     rcx, r12
0x180095814  jz      short loc_18009582E
0x180095816  test    byte ptr [rcx+1Ch], 80h
0x18009581a  jz      short loc_18009582E
0x18009581c  mov     rcx, [rcx+10h]
0x180095820  lea     edx, [rsi+34h]
0x180095823  mov     r9d, ebx
0x180095826  mov     r8, r15
0x180095829  call    WPP_SF_d
0x18009582e  test    ebx, ebx
0x180095830  js      loc_180095940
0x180095836  call    ?LsapMarkBootGood@@YAXXZ; LsapMarkBootGood(void)
0x18009583b  lea     rdx, SourceString; "\\SAM_SERVICE_STARTED"
0x180095842  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180095846  call    cs:__imp_RtlInitUnicodeString
0x18009584d  nop     dword ptr [rax+rax+00h]
0x180095852  lea     rax, [rbp+57h+DestinationString]
0x180095856  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18009585d  xorps   xmm0, xmm0
0x180095860  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180095864  mov     ebx, 100002h
0x180095869  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18009586d  mov     edx, ebx; DesiredAccess
0x18009586f  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180095872  xor     r9d, r9d; EventType
0x180095875  mov     [rsp+110h+InitialState], sil; InitialState
0x18009587a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18009587e  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180095882  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180095887  call    cs:__imp_NtCreateEvent
0x18009588e  nop     dword ptr [rax+rax+00h]
0x180095893  test    eax, eax
0x180095895  jns     short loc_1800958EB
0x180095897  cmp     eax, 0C0000035h
0x18009589c  jnz     short loc_1800958B8
0x18009589e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800958a2  mov     edx, ebx; DesiredAccess
0x1800958a4  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x1800958a8  call    cs:__imp_NtOpenEvent
0x1800958af  nop     dword ptr [rax+rax+00h]
0x1800958b4  test    eax, eax
0x1800958b6  jns     short loc_1800958EB
0x1800958b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800958bf  cmp     rcx, r12
0x1800958c2  jz      loc_180095B7C
0x1800958c8  test    byte ptr [rcx+1Ch], 80h
0x1800958cc  jz      loc_180095B7C
0x1800958d2  mov     rcx, [rcx+10h]
0x1800958d6  mov     edx, 35h ; '5'
0x1800958db  mov     r9d, eax
0x1800958de  mov     r8, r15
0x1800958e1  call    WPP_SF_d
0x1800958e6  jmp     loc_180095B7C
0x1800958eb  mov     rcx, [rbp+57h+EventHandle]; EventHandle
0x1800958ef  xor     edx, edx; PreviousState
0x1800958f1  call    cs:__imp_NtSetEvent
0x1800958f8  nop     dword ptr [rax+rax+00h]
0x1800958fd  test    eax, eax
0x1800958ff  jns     loc_180095B7C
0x180095905  mov     rcx, cs:WPP_GLOBAL_Control
0x18009590c  cmp     rcx, r12
0x18009590f  jz      short loc_18009592B
0x180095911  test    byte ptr [rcx+1Ch], 80h
0x180095915  jz      short loc_18009592B
0x180095917  mov     rcx, [rcx+10h]
0x18009591b  mov     edx, 36h ; '6'
0x180095920  mov     r9d, eax
0x180095923  mov     r8, r15
0x180095926  call    WPP_SF_d
0x18009592b  mov     rcx, [rbp+57h+EventHandle]; Handle
0x18009592f  call    cs:__imp_NtClose
0x180095936  nop     dword ptr [rax+rax+00h]
0x18009593b  jmp     loc_180095B7C
0x180095940  mov     ecx, 2; ImpersonationLevel
0x180095945  call    cs:__imp_ImpersonateSelf
0x18009594c  nop     dword ptr [rax+rax+00h]
0x180095951  test    eax, eax
0x180095953  jz      loc_180095B7C
0x180095959  mov     edi, esi
0x18009595b  mov     [rbp+57h+TokenHandle], rsi
0x18009595f  call    cs:__imp_GetCurrentThread
0x180095966  nop     dword ptr [rax+rax+00h]
0x18009596b  mov     edx, 8; DesiredAccess
0x180095970  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180095974  mov     rcx, rax; ThreadHandle
0x180095977  lea     r8d, [rdx-7]; OpenAsSelf
0x18009597b  call    cs:__imp_OpenThreadToken
0x180095982  nop     dword ptr [rax+rax+00h]
0x180095987  test    eax, eax
0x180095989  jz      loc_180095A20
0x18009598f  lea     rax, [rbp+57h+SidToCheck]
0x180095993  mov     [rbp+57h+IsMember], esi
0x180095996  mov     [rsp+110h+pSid], rax; pSid
0x18009599b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18009599f  mov     [rsp+110h+nSubAuthority7], esi; nSubAuthority7
0x1800959a3  xor     r9d, r9d; nSubAuthority1
0x1800959a6  mov     [rsp+110h+nSubAuthority6], esi; nSubAuthority6
0x1800959aa  mov     dl, 1; nSubAuthorityCount
0x1800959ac  mov     [rsp+110h+nSubAuthority5], esi; nSubAuthority5
0x1800959b0  mov     [rsp+110h+nSubAuthority4], esi; nSubAuthority4
0x1800959b4  mov     [rsp+110h+nSubAuthority3], esi; nSubAuthority3
0x1800959b8  lea     r8d, [r9+12h]; nSubAuthority0
0x1800959bc  mov     dword ptr [rsp+110h+InitialState], esi; nSubAuthority2
0x1800959c0  mov     [rbp+57h+SidToCheck], rsi
0x1800959c4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800959c7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800959cd  call    cs:__imp_AllocateAndInitializeSid
0x1800959d4  nop     dword ptr [rax+rax+00h]
0x1800959d9  test    eax, eax
0x1800959db  jz      short loc_180095A10
0x1800959dd  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800959e1  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800959e5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800959e9  call    cs:__imp_CheckTokenMembership
0x1800959f0  nop     dword ptr [rax+rax+00h]
0x1800959f5  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1800959f9  test    eax, eax
0x1800959fb  cmovnz  edi, [rbp+57h+IsMember]
0x1800959ff  test    rcx, rcx
0x180095a02  jz      short loc_180095A10
0x180095a04  call    cs:__imp_FreeSid
0x180095a0b  nop     dword ptr [rax+rax+00h]
0x180095a10  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180095a14  call    cs:__imp_CloseHandle
0x180095a1b  nop     dword ptr [rax+rax+00h]
0x180095a20  call    cs:__imp_RevertToSelf
0x180095a27  nop     dword ptr [rax+rax+00h]
0x180095a2c  test    edi, edi
0x180095a2e  jz      loc_180095B7C
0x180095a34  mov     [rbp+57h+Parameters], 10010h
0x180095a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a43  cmp     rcx, r12
0x180095a46  jz      short loc_180095A5F
0x180095a48  test    byte ptr [rcx+1Ch], 80h
0x180095a4c  jz      short loc_180095A5F
0x180095a4e  mov     rcx, [rcx+10h]
0x180095a52  mov     edx, 37h ; '7'
0x180095a57  mov     r8, r15
0x180095a5a  call    WPP_SF_
0x180095a5f  xor     r8d, r8d; UnicodeStringParameterMask
0x180095a62  lea     rax, [rbp+57h+Response]
0x180095a66  bts     ebx, 1Ch
0x180095a6a  mov     qword ptr [rsp+110h+nSubAuthority3], rax; Response
0x180095a6f  lea     r9, [rbp+57h+Parameters]; Parameters
0x180095a73  mov     dword ptr [rsp+110h+InitialState], 1; ValidResponseOptions
0x180095a7b  mov     ecx, ebx; ErrorStatus
0x180095a7d  lea     edx, [r8+1]; NumberOfParameters
0x180095a81  call    cs:__imp_NtRaiseHardError
0x180095a88  nop     dword ptr [rax+rax+00h]
0x180095a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a94  cmp     rcx, r12
0x180095a97  jz      short loc_180095AB3
0x180095a99  test    byte ptr [rcx+1Ch], 80h
0x180095a9d  jz      short loc_180095AB3
0x180095a9f  mov     rcx, [rcx+10h]
0x180095aa3  mov     edx, 38h ; '8'
0x180095aa8  mov     r9d, eax
0x180095aab  mov     r8, r15
0x180095aae  call    WPP_SF_d
0x180095ab3  call    ?SpmpIsSetupPass@@YAEXZ; SpmpIsSetupPass(void)
0x180095ab8  test    al, al
0x180095aba  jz      short loc_180095AED
0x180095abc  call    ?SpmpIsMiniSetupPass@@YAEXZ; SpmpIsMiniSetupPass(void)
0x180095ac1  test    al, al
0x180095ac3  jnz     short loc_180095AED
0x180095ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180095acc  cmp     rcx, r12
0x180095acf  jz      short loc_180095AE8
0x180095ad1  test    byte ptr [rcx+1Ch], 80h
0x180095ad5  jz      short loc_180095AE8
0x180095ad7  mov     rcx, [rcx+10h]
0x180095adb  mov     edx, 39h ; '9'
0x180095ae0  mov     r8, r15
0x180095ae3  call    WPP_SF_
0x180095ae8  call    ?LsapMarkBootGood@@YAXXZ; LsapMarkBootGood(void)
0x180095aed  xor     r8d, r8d; ForThread
0x180095af0  mov     [rbp+57h+OldValue], sil
0x180095af4  lea     r9, [rbp+57h+OldValue]; OldValue
0x180095af8  mov     dl, 1; NewValue
0x180095afa  lea     ebx, [r8+13h]
0x180095afe  mov     ecx, ebx; Privilege
0x180095b00  call    cs:__imp_RtlAdjustPrivilege
0x180095b07  nop     dword ptr [rax+rax+00h]
0x180095b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b13  cmp     rcx, r12
0x180095b16  jz      short loc_180095B2D
0x180095b18  test    byte ptr [rcx+1Ch], 80h
0x180095b1c  jz      short loc_180095B2D
0x180095b1e  mov     rcx, [rcx+10h]
0x180095b22  lea     edx, [rbx+27h]
0x180095b25  mov     r8, r15
0x180095b28  call    WPP_SF_
0x180095b2d  mov     ecx, 1; Action
0x180095b32  call    cs:__imp_NtShutdownSystem
0x180095b39  nop     dword ptr [rax+rax+00h]
0x180095b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b45  cmp     rcx, r12
0x180095b48  jz      short loc_180095B64
0x180095b4a  test    byte ptr [rcx+1Ch], 80h
0x180095b4e  jz      short loc_180095B64
0x180095b50  mov     rcx, [rcx+10h]
0x180095b54  mov     edx, 3Bh ; ';'
0x180095b59  mov     r9d, eax
0x180095b5c  mov     r8, r15
0x180095b5f  call    WPP_SF_d
0x180095b64  mov     dl, [rbp+57h+OldValue]; NewValue
0x180095b67  lea     r9, [rbp+57h+OldValue]; OldValue
0x180095b6b  xor     r8d, r8d; ForThread
0x180095b6e  mov     ecx, ebx; Privilege
0x180095b70  call    cs:__imp_RtlAdjustPrivilege
0x180095b77  nop     dword ptr [rax+rax+00h]
0x180095b7c  mov     rcx, [rbp+57h+var_38]
0x180095b80  xor     rcx, rsp; StackCookie
0x180095b83  call    __security_check_cookie
0x180095b88  add     rsp, 0E8h
0x180095b8f  pop     r15
0x180095b91  pop     r12
0x180095b93  pop     rdi
0x180095b94  pop     rsi
0x180095b95  pop     rbx
0x180095b96  pop     rbp
0x180095b97  retn
```
