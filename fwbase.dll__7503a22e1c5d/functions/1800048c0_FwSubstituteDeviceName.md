# FwSubstituteDeviceName

- ea: `0x1800048c0`
- end: `0x180004c72`
- name: `FwSubstituteDeviceName`
- size: `946`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003b30`
- `0x180007180`

## callees

- `0x180002c10`
- `0x1800048c0`
- `0x180006f50`
- `0x180017b58`
- `0x18001e1d0`
- `0x18001eb54`
- `0x18002158c`
- `0x18002f38c`
- `0x18002f650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000494d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000494d`
- `ntdll!RtlInitUnicodeString` at `0x18000499a`
- `ntdll!RtlInitUnicodeString` at `0x18000499a`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180004a6d`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180004a6d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180004a0d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180004ad0`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180004a0d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180004ad0`
- `ntdll!NtClose` at `0x180004a7a`
- `ntdll!NtClose` at `0x180004a7a`

## string_xrefs

- `0x180004b36`: `FwWalkSymbolicLinks`
- `0x180004bc0`: `FwWalkSymbolicLinks`
- `0x180004b2b`: `NtQuerySymbolicLinkObject`
- `0x180004a4d`: `NtOpenSymbolicLinkObject`
- `0x180004afd`: `NtOpenSymbolicLinkObject`
- `0x180004a87`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwSubstituteDeviceName(wchar_t *String2, _QWORD *a2)
{
  WCHAR v4; // r15
  __int64 result; // rax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // edi
  _UNKNOWN **v9; // rbx
  bool v10; // zf
  int v11; // r14d
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  _QWORD *v14; // rcx
  NTSTATUS v15; // eax
  int v16; // edx
  int v17; // r8d
  unsigned __int64 v18; // rdi
  void *SymbolicLinkHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+38h] [rbp-C8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SourceString[12]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v24[512]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 65;
  wcscpy(SourceString, L"\\??\\A:");
  DestinationString = 0;
  LinkTarget = 0;
  memset_0(v24, 0, sizeof(v24));
  *a2 = 0;
  if ( !(unsigned int)_o__wcsnicmp(L"\\Device\\Mup\\", String2, 12) )
  {
    result = FwStringBuild(a2, L"\\\\", String2 + 12, 0);
    v8 = result;
    if ( (int)result < 0 )
    {
      v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v10 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    return result;
  }
  v11 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_DWORD *)&LinkTarget.Length = 0x2000000;
  LinkTarget.Buffer = (PWSTR)v24;
  while ( 1 )
  {
    SourceString[4] = v4;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    SymbolicLinkHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v12 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
    v13 = v12;
    if ( v12 == -1073741772 )
    {
      v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v11 = 0;
      goto LABEL_29;
    }
    if ( v12 >= 0 )
    {
      do
      {
        v13 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, 0);
        v15 = NtClose(SymbolicLinkHandle);
        if ( v15 < 0 )
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)v15, 0);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_ssD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v16,
              v17,
              (unsigned int)"FwWalkSymbolicLinks",
              (__int64)"NtQuerySymbolicLinkObject",
              v13);
          goto LABEL_23;
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &LinkTarget;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v12 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
        v13 = v12;
        if ( v12 == -1073741788 )
        {
          v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
          v11 = 1;
          goto LABEL_28;
        }
      }
      while ( v12 >= 0 );
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
LABEL_10:
      WPP_SF_ssD(v14[2], v6, v7, (unsigned int)"FwWalkSymbolicLinks", (__int64)"NtOpenSymbolicLinkObject", v12);
      goto LABEL_23;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      goto LABEL_10;
LABEL_23:
    LODWORD(result) = FwNtStatusToHResult((unsigned int)v13);
    v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v8 = result;
    if ( (int)result < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, (unsigned int)"FwWalkSymbolicLinks", result);
      v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
      LOBYTE(result) = v8;
LABEL_34:
      v10 = v9 == &WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    v8 = result;
    if ( (int)result < 0 )
      goto LABEL_34;
    if ( !v11 )
      goto LABEL_29;
LABEL_28:
    v18 = (unsigned __int64)LinkTarget.Length >> 1;
    if ( !wcsncmp_0(LinkTarget.Buffer, String2, (unsigned int)v18) )
      break;
LABEL_29:
    if ( ++v4 > 0x5Au )
    {
      v8 = -2147024894;
      if ( v9 == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)v9 + 28) & 1) != 0 )
      {
        WPP_SF_sD((unsigned int)v9[2], v6, v7, (unsigned int)"FwSubstituteDeviceName", 2);
        goto LABEL_38;
      }
      goto LABEL_39;
    }
  }
  result = FwStringBuild(a2, &SourceString[4], &String2[v18], 0);
  v8 = result;
  if ( (int)result >= 0 )
    return result;
  v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
LABEL_35:
  if ( !v10 )
  {
    if ( (*((_BYTE *)v9 + 28) & 1) != 0 )
    {
      WPP_SF_sD((unsigned int)v9[2], v6, v7, (unsigned int)"FwSubstituteDeviceName", result);
LABEL_38:
      v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
LABEL_39:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_sD((unsigned int)v9[2], v6, v7, (unsigned int)"FwSubstituteDeviceName", v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800048c0  mov     [rsp-8+arg_10], rbx
0x1800048c5  push    rbp
0x1800048c6  push    rsi
0x1800048c7  push    rdi
0x1800048c8  push    r12
0x1800048ca  push    r13
0x1800048cc  push    r14
0x1800048ce  push    r15
0x1800048d0  lea     rbp, [rsp-1B0h]
0x1800048d8  sub     rsp, 2B0h
0x1800048df  mov     rax, cs:__security_cookie
0x1800048e6  xor     rax, rsp
0x1800048e9  mov     [rbp+1E0h+var_40], rax
0x1800048f0  mov     r13, rdx
0x1800048f3  mov     [rbp+1E0h+var_24E], 3Ah ; ':'
0x1800048fa  mov     r12, rcx
0x1800048fd  xorps   xmm0, xmm0
0x180004900  xorps   xmm1, xmm1
0x180004903  lea     rcx, [rbp+1E0h+var_240]; void *
0x180004907  mov     rax, 5C003F003F005Ch
0x180004911  mov     r15d, 41h ; 'A'
0x180004917  xor     edx, edx; Val
0x180004919  mov     qword ptr [rbp+1E0h+SourceString], rax
0x18000491d  mov     r8d, 200h; Size
0x180004923  mov     [rbp+1E0h+var_250], r15w
0x180004928  movups  xmmword ptr [rsp+2E0h+DestinationString.Length], xmm0
0x18000492d  movups  xmmword ptr [rsp+2E0h+LinkTarget.Length], xmm1
0x180004932  call    memset_0
0x180004937  xor     edi, edi
0x180004939  lea     rcx, aDeviceMup; "\\Device\\Mup\\"
0x180004940  mov     r8d, 0Ch
0x180004946  mov     [r13+0], rdi
0x18000494a  mov     rdx, r12
0x18000494d  call    cs:__imp__o__wcsnicmp
0x180004953  test    eax, eax
0x180004955  jnz     short loc_18000498E
0x180004957  lea     r8, [r12+18h]
0x18000495c  xor     r9d, r9d
0x18000495f  lea     rdx, asc_180033DDC; "\\\\"
0x180004966  mov     rcx, r13
0x180004969  call    FwStringBuild
0x18000496e  mov     edi, eax
0x180004970  test    eax, eax
0x180004972  jns     loc_180004C20
0x180004978  mov     rbx, cs:WPP_GLOBAL_Control
0x18000497f  lea     rsi, WPP_GLOBAL_Control
0x180004986  cmp     rbx, rsi
0x180004989  jmp     loc_180004BDC
0x18000498e  lea     rdx, [rbp+1E0h+SourceString]; SourceString
0x180004992  mov     r14d, edi
0x180004995  lea     rcx, [rsp+2E0h+DestinationString]; DestinationString
0x18000499a  call    cs:__imp_RtlInitUnicodeString
0x1800049a0  lea     rax, [rbp+1E0h+var_240]
0x1800049a4  mov     dword ptr [rsp+2E0h+LinkTarget.Length], 2000000h
0x1800049ac  mov     [rsp+2E0h+LinkTarget.Buffer], rax
0x1800049b1  lea     rsi, WPP_GLOBAL_Control
0x1800049b8  nop     dword ptr [rax+rax+00000000h]
0x1800049c0  movzx   eax, r15w
0x1800049c4  mov     byte ptr [rbp+1E0h+var_250], r15b
0x1800049c8  shr     ax, 8
0x1800049cc  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x1800049d1  mov     byte ptr [rbp+1E0h+var_250+1], al
0x1800049d4  lea     rcx, [rsp+2E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800049d9  lea     rax, [rsp+2E0h+DestinationString]
0x1800049de  mov     qword ptr [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x1800049e7  xorps   xmm0, xmm0
0x1800049ea  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x1800049ef  mov     edx, 1; DesiredAccess
0x1800049f4  mov     qword ptr [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800049fd  mov     [rsp+2E0h+SymbolicLinkHandle], rdi
0x180004a02  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x180004a07  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004a0d  call    cs:__imp_NtOpenSymbolicLinkObject
0x180004a13  mov     ebx, eax
0x180004a15  cmp     eax, 0C0000034h
0x180004a1a  jnz     short loc_180004A2B
0x180004a1c  mov     rbx, cs:WPP_GLOBAL_Control
0x180004a23  mov     r14d, edi
0x180004a26  jmp     loc_180004B93
0x180004a2b  test    eax, eax
0x180004a2d  jns     short loc_180004A60
0x180004a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a36  cmp     rcx, rsi
0x180004a39  jz      loc_180004B47
0x180004a3f  test    byte ptr [rcx+1Ch], 1
0x180004a43  jz      loc_180004B47
0x180004a49  mov     [rsp+2E0h+var_2B8], eax
0x180004a4d  lea     rax, aNtopensymbolic; "NtOpenSymbolicLinkObject"
0x180004a54  jmp     loc_180004B32
0x180004a60  mov     rcx, [rsp+2E0h+SymbolicLinkHandle]; SymLinkObjHandle
0x180004a65  lea     rdx, [rsp+2E0h+LinkTarget]; LinkTarget
0x180004a6a  xor     r8d, r8d; DataWritten
0x180004a6d  call    cs:__imp_NtQuerySymbolicLinkObject
0x180004a73  mov     rcx, [rsp+2E0h+SymbolicLinkHandle]; Handle
0x180004a78  mov     ebx, eax
0x180004a7a  call    cs:__imp_NtClose
0x180004a80  test    eax, eax
0x180004a82  jns     short loc_180004A95
0x180004a84  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "NT_SUCCESS(closeStatus)", "NtClose failed")
0x180004a87  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180004a8e  mov     edx, eax
0x180004a90  call    MicrosoftTelemetryAssertTriggeredArgs
0x180004a95  test    ebx, ebx
0x180004a97  js      short loc_180004B15
0x180004a99  lea     rax, [rsp+2E0h+LinkTarget]
0x180004a9e  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180004aa6  xorps   xmm0, xmm0
0x180004aa9  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180004aae  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180004ab3  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], rdi
0x180004ab8  mov     edx, 1; DesiredAccess
0x180004abd  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180004ac5  lea     rcx, [rsp+2E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180004aca  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004ad0  call    cs:__imp_NtOpenSymbolicLinkObject
0x180004ad6  mov     ebx, eax
0x180004ad8  cmp     eax, 0C0000024h
0x180004add  jz      short loc_180004B06
0x180004adf  test    eax, eax
0x180004ae1  jns     loc_180004A60
0x180004ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aee  cmp     rcx, rsi
0x180004af1  jz      short loc_180004B47
0x180004af3  test    byte ptr [rcx+1Ch], 1
0x180004af7  jz      short loc_180004B47
0x180004af9  mov     [rsp+2E0h+var_2B8], eax
0x180004afd  lea     rax, aNtopensymbolic; "NtOpenSymbolicLinkObject"
0x180004b04  jmp     short loc_180004B32
0x180004b06  mov     rbx, cs:WPP_GLOBAL_Control
0x180004b0d  mov     r14d, 1
0x180004b13  jmp     short loc_180004B71
0x180004b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b1c  cmp     rcx, rsi
0x180004b1f  jz      short loc_180004B47
0x180004b21  test    byte ptr [rcx+1Ch], 1
0x180004b25  jz      short loc_180004B47
0x180004b27  mov     [rsp+2E0h+var_2B8], ebx
0x180004b2b  lea     rax, aNtquerysymboli; "NtQuerySymbolicLinkObject"
0x180004b32  mov     rcx, [rcx+10h]
0x180004b36  lea     r9, aFwwalksymbolic; "FwWalkSymbolicLinks"
0x180004b3d  mov     [rsp+2E0h+var_2C0], rax
0x180004b42  call    WPP_SF_ssD
0x180004b47  mov     ecx, ebx
0x180004b49  call    FwNtStatusToHResult
0x180004b4e  mov     rbx, cs:WPP_GLOBAL_Control
0x180004b55  mov     edi, eax
0x180004b57  test    eax, eax
0x180004b59  jns     short loc_180004B66
0x180004b5b  cmp     rbx, rsi
0x180004b5e  jz      short loc_180004B66
0x180004b60  test    byte ptr [rbx+1Ch], 1
0x180004b64  jnz     short loc_180004BBC
0x180004b66  mov     edi, eax
0x180004b68  test    eax, eax
0x180004b6a  js      short loc_180004BD9
0x180004b6c  test    r14d, r14d
0x180004b6f  jz      short loc_180004B91
0x180004b71  movzx   edi, [rsp+2E0h+LinkTarget.Length]
0x180004b76  mov     rdx, r12; String2
0x180004b79  mov     rcx, [rsp+2E0h+LinkTarget.Buffer]; String1
0x180004b7e  shr     rdi, 1
0x180004b81  mov     r8d, edi; MaxCount
0x180004b84  call    wcsncmp_0
0x180004b89  test    eax, eax
0x180004b8b  jz      loc_180004C4A
0x180004b91  xor     edi, edi
0x180004b93  inc     r15w
0x180004b97  cmp     r15w, 5Ah ; 'Z'
0x180004b9c  jbe     loc_1800049C0
0x180004ba2  mov     edi, 80070002h
0x180004ba7  cmp     rbx, rsi
0x180004baa  jz      short loc_180004C1E
0x180004bac  test    byte ptr [rbx+1Ch], 1
0x180004bb0  jz      short loc_180004BFF
0x180004bb2  mov     dword ptr [rsp+2E0h+var_2C0], 80070002h
0x180004bba  jmp     short loc_180004BE8
0x180004bbc  mov     rcx, [rbx+10h]
0x180004bc0  lea     r9, aFwwalksymbolic; "FwWalkSymbolicLinks"
0x180004bc7  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x180004bcb  call    WPP_SF_sD
0x180004bd0  mov     rbx, cs:WPP_GLOBAL_Control
0x180004bd7  mov     eax, edi
0x180004bd9  cmp     rbx, rsi
0x180004bdc  jz      short loc_180004C1E
0x180004bde  test    byte ptr [rbx+1Ch], 1
0x180004be2  jz      short loc_180004BFF
0x180004be4  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x180004be8  mov     rcx, [rbx+10h]
0x180004bec  lea     r9, aFwsubstitutede_0; "FwSubstituteDeviceName"
0x180004bf3  call    WPP_SF_sD
0x180004bf8  mov     rbx, cs:WPP_GLOBAL_Control
0x180004bff  cmp     rbx, rsi
0x180004c02  jz      short loc_180004C1E
0x180004c04  test    byte ptr [rbx+1Ch], 1
0x180004c08  jz      short loc_180004C1E
0x180004c0a  mov     rcx, [rbx+10h]
0x180004c0e  lea     r9, aFwsubstitutede_0; "FwSubstituteDeviceName"
0x180004c15  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x180004c19  call    WPP_SF_sD
0x180004c1e  mov     eax, edi
0x180004c20  mov     rcx, [rbp+1E0h+var_40]
0x180004c27  xor     rcx, rsp; StackCookie
0x180004c2a  call    __security_check_cookie
0x180004c2f  mov     rbx, [rsp+2E0h+arg_10]
0x180004c37  add     rsp, 2B0h
0x180004c3e  pop     r15
0x180004c40  pop     r14
0x180004c42  pop     r13
0x180004c44  pop     r12
0x180004c46  pop     rdi
0x180004c47  pop     rsi
0x180004c48  pop     rbp
0x180004c49  retn
0x180004c4a  lea     r8, [r12+rdi*2]
0x180004c4e  xor     r9d, r9d
0x180004c51  lea     rdx, [rbp+1E0h+var_250]
0x180004c55  mov     rcx, r13
0x180004c58  call    FwStringBuild
0x180004c5d  mov     edi, eax
0x180004c5f  test    eax, eax
0x180004c61  jns     short loc_180004C20
0x180004c63  mov     rbx, cs:WPP_GLOBAL_Control
0x180004c6a  cmp     rbx, rsi
0x180004c6d  jmp     loc_180004BDC
```
