# CsrParseServerCommandLine

- ea: `0x180005180`
- end: `0x18000585d`
- name: `CsrParseServerCommandLine`
- size: `1757`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004a20`

## callees

- `0x180001540`
- `0x1800035c0`
- `0x180003f20`
- `0x180005180`
- `0x1800073d0`
- `0x180007b70`
- `0x180007ee0`
- `0x180008190`
- `0x180008ca4`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180005324`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800053f6`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180005324`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800053f6`
- `ntdll!NtCreateDirectoryObject` at `0x180005373`
- `ntdll!NtCreateDirectoryObject` at `0x180005373`
- `ntdll!NtOpenEvent` at `0x180005544`
- `ntdll!NtOpenEvent` at `0x180005544`
- `ntdll!RtlFreeUnicodeString` at `0x180005451`
- `ntdll!RtlFreeUnicodeString` at `0x180005451`
- `ntdll!RtlInitUnicodeString` at `0x18000550a`
- `ntdll!RtlInitUnicodeString` at `0x18000550a`
- `ntdll!_snprintf_s` at `0x1800052d5`
- `ntdll!_snprintf_s` at `0x1800052d5`
- `ntdll!NtClose` at `0x180005646`
- `ntdll!NtClose` at `0x180005646`
- `ntdll!NtCreateEvent` at `0x1800055c6`
- `ntdll!NtCreateEvent` at `0x1800055c6`
- `ntdll!NtSetEvent` at `0x180005635`
- `ntdll!NtSetEvent` at `0x180005635`
- `ntdll!_stricmp` at `0x180005288`
- `ntdll!_stricmp` at `0x18000547e`
- `ntdll!_stricmp` at `0x1800054ca`
- `ntdll!_stricmp` at `0x18000567e`
- `ntdll!_stricmp` at `0x18000572a`
- `ntdll!_stricmp` at `0x180005744`
- `ntdll!_stricmp` at `0x180005771`
- `ntdll!_stricmp` at `0x18000578f`
- `ntdll!_stricmp` at `0x180005288`
- `ntdll!_stricmp` at `0x18000547e`
- `ntdll!_stricmp` at `0x1800054ca`
- `ntdll!_stricmp` at `0x18000567e`
- `ntdll!_stricmp` at `0x18000572a`
- `ntdll!_stricmp` at `0x180005744`
- `ntdll!_stricmp` at `0x180005771`
- `ntdll!_stricmp` at `0x18000578f`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18000543d`
- `ntdll!NtCreateSymbolicLinkObject` at `0x18000543d`
- `ntdll!RtlFreeHeap` at `0x180005604`
- `ntdll!RtlFreeHeap` at `0x180005604`
- `ntdll!RtlInitString` at `0x180005309`
- `ntdll!RtlInitString` at `0x1800053dd`
- `ntdll!RtlInitString` at `0x180005309`
- `ntdll!RtlInitString` at `0x1800053dd`
- `ntdll!RtlCharToInteger` at `0x18000549f`
- `ntdll!RtlCharToInteger` at `0x1800056cf`
- `ntdll!RtlCharToInteger` at `0x18000549f`
- `ntdll!RtlCharToInteger` at `0x1800056cf`
- `ntdll!NtWaitForSingleObject` at `0x180005564`
- `ntdll!NtWaitForSingleObject` at `0x1800055e9`
- `ntdll!NtWaitForSingleObject` at `0x180005564`
- `ntdll!NtWaitForSingleObject` at `0x1800055e9`

## string_xrefs

- `0x180005474`: `MaxRequestThreads`
- `0x18000527e`: `ObjectDirectory`
- `0x180005225`: `CsrParseServerCommandLine`
- `0x1800057a9`: `CsrParseServerCommandLine`
- `0x18000581c`: `CsrParseServerCommandLine`
- `0x180005674`: `ServerDLL`

## pseudocode

```c
__int64 __fastcall CsrParseServerCommandLine(unsigned int a1, __int64 a2, void *a3, __int64 a4)
{
  const char *v4; // r14
  __int64 v6; // rax
  void *v7; // r15
  __int64 v8; // rbx
  NTSTATUS SessionObjectDirectory; // r12d
  unsigned int i; // edi
  const char *v11; // rsi
  _BYTE *j; // rdx
  const char *v13; // rbx
  ULONG v14; // r14d
  char *v15; // rdx
  int ApiPort; // eax
  NTSTATUS v17; // eax
  char v18; // r14
  void *v19; // r15
  const char *v20; // rcx
  char v21; // al
  const char *v22; // r15
  __int64 v24; // [rsp+28h] [rbp-D8h]
  struct _STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Value; // [rsp+50h] [rbp-B0h] BYREF
  void *SymbolicLinkHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  void *v29; // [rsp+70h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES v31; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-28h]
  __int64 v33; // [rsp+E0h] [rbp-20h]
  char DstBuf[256]; // [rsp+F0h] [rbp-10h] BYREF

  CsrMaxApiRequestThreads = 16;
  v4 = 0;
  v32 = a4;
  CsrObjectDirectory = 0;
  memset(&ObjectAttributes, 0, 44);
  Value = 0;
  v6 = *(_QWORD *)&KeGetPcr()->MajorVersion;
  v7 = a3;
  v29 = a3;
  v8 = a2;
  v33 = a2;
  LODWORD(CsrTotalPerProcessDataLength) = 0;
  g_SessionId = *(_DWORD *)(v6 + 704);
  SessionObjectDirectory = CsrCreateSessionObjectDirectory();
  if ( SessionObjectDirectory >= 0 || g_SessionId == ServiceSessionId )
  {
    for ( i = 1; ; ++i )
    {
LABEL_5:
      if ( i >= a1 )
        return (unsigned int)SessionObjectDirectory;
      v11 = 0;
      for ( j = *(_BYTE **)(v8 + 8LL * i); *j; ++j )
      {
        if ( *j == 61 )
        {
          *j = 0;
          v11 = j + 1;
          break;
        }
      }
      v13 = *(const char **)(v8 + 8LL * i);
      if ( !_stricmp(v13, "ObjectDirectory") )
      {
        LODWORD(v24) = g_SessionId;
        DestinationString = 0;
        _snprintf_s(DstBuf, 0x100u, 0xFFu, "%ws\\%ld%s", L"\\Sessions", v24, v11);
        if ( g_SessionId == ServiceSessionId )
        {
          v14 = 208;
          v15 = (char *)v11;
        }
        else
        {
          v14 = 192;
          v15 = DstBuf;
        }
        RtlInitString(&DestinationString, v15);
        SessionObjectDirectory = RtlAnsiStringToUnicodeString(&CsrDirectoryName, &DestinationString, 1u);
        if ( SessionObjectDirectory < 0 )
          return (unsigned int)SessionObjectDirectory;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &CsrDirectoryName;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = v14;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ApiPort = NtCreateDirectoryObject(&CsrObjectDirectory, 0xF000Fu, &ObjectAttributes);
        SessionObjectDirectory = ApiPort;
        if ( ApiPort < 0 )
          goto LABEL_26;
        ApiPort = CsrSetDirectorySecurity();
        SessionObjectDirectory = ApiPort;
        if ( ApiPort < 0 )
          goto LABEL_26;
        ApiPort = CsrServerCreateApiPort(v7);
        SessionObjectDirectory = ApiPort;
        if ( ApiPort < 0 )
          goto LABEL_26;
        if ( g_SessionId == ServiceSessionId )
        {
          SymbolicLinkHandle = 0;
          UnicodeString = 0;
          RtlInitString(&DestinationString, DstBuf);
          RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &UnicodeString;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = v14;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          SessionObjectDirectory = NtCreateSymbolicLinkObject(
                                     &SymbolicLinkHandle,
                                     0xF0001u,
                                     &ObjectAttributes,
                                     &CsrDirectoryName);
          RtlFreeUnicodeString(&UnicodeString);
          if ( SessionObjectDirectory < 0 )
            return (unsigned int)SessionObjectDirectory;
        }
LABEL_21:
        v4 = 0;
        goto LABEL_22;
      }
      if ( _stricmp(v13, "MaxRequestThreads") )
        break;
      if ( v11 )
      {
        ApiPort = RtlCharToInteger(v11, 0, &CsrMaxApiRequestThreads);
        SessionObjectDirectory = ApiPort;
        if ( ApiPort < 0 )
          goto LABEL_26;
      }
LABEL_22:
      v8 = v33;
    }
    if ( !_stricmp(v13, "SharedSection") )
    {
      *(_QWORD *)&DestinationString.Length = 0;
      SymbolicLinkHandle = 0;
      UnicodeString = 0;
      memset(&v31, 0, 44);
      RtlInitUnicodeString(&UnicodeString, L"\\CsrSbSyncEvent");
      v31.Length = 48;
      v31.ObjectName = &UnicodeString;
      v31.RootDirectory = 0;
      v31.Attributes = 0;
      *(_OWORD *)&v31.SecurityDescriptor = 0;
      v17 = NtOpenEvent((PHANDLE)&DestinationString, 0x100000u, &v31);
      SessionObjectDirectory = v17;
      if ( v17 < 0 )
      {
        if ( v17 != -1073741772 )
          return (unsigned int)SessionObjectDirectory;
        ApiPort = CsrCreateLocalSystemSD((struct _ACL **)&SymbolicLinkHandle, 0x100002u);
        SessionObjectDirectory = ApiPort;
        if ( ApiPort < 0 )
        {
LABEL_26:
          CsrpLogModuleFailureString("CsrParseServerCommandLine", ApiPort);
          return (unsigned int)SessionObjectDirectory;
        }
        v19 = SymbolicLinkHandle;
        v31.SecurityDescriptor = SymbolicLinkHandle;
        v31.Attributes = 144;
        v18 = 1;
        SessionObjectDirectory = NtCreateEvent((PHANDLE)&DestinationString, 0x100002u, &v31, NotificationEvent, 0);
        if ( SessionObjectDirectory == 0x40000000 )
        {
          v18 = 0;
          SessionObjectDirectory = NtWaitForSingleObject(*(HANDLE *)&DestinationString.Length, 0, 0);
        }
        RtlFreeHeap(CsrHeap, 0, v19);
        v7 = v29;
      }
      else
      {
        v18 = 0;
        SessionObjectDirectory = NtWaitForSingleObject(*(HANDLE *)&DestinationString.Length, 0, 0);
      }
      if ( SessionObjectDirectory < 0 )
        return (unsigned int)SessionObjectDirectory;
      SessionObjectDirectory = CsrSrvCreateSharedSection(v11);
      if ( v18 )
        NtSetEvent(*(HANDLE *)&DestinationString.Length, 0);
      NtClose(*(HANDLE *)&DestinationString.Length);
      if ( SessionObjectDirectory < 0 )
      {
LABEL_62:
        CsrpLogModuleFailureString("CsrParseServerCommandLine", SessionObjectDirectory);
        return (unsigned int)SessionObjectDirectory;
      }
      SessionObjectDirectory = CsrLoadServerDll("CSRSS", 0, 0);
      goto LABEL_21;
    }
    if ( _stricmp(v13, "ServerDLL") )
    {
      if ( !_stricmp(v13, "Windows") )
      {
        if ( !_stricmp(v11, "Off") )
          SessionFirstProcessImageType = 3;
      }
      else if ( _stricmp(v13, "ProfileControl") && _stricmp(v13, "SubSystemType") )
      {
        SessionObjectDirectory = -1073741811;
        CsrpLogModuleFailureString("CsrParseServerCommandLine", -1073741811);
      }
      goto LABEL_22;
    }
    v20 = v11;
    SessionObjectDirectory = -1073741811;
    while ( 1 )
    {
      while ( 1 )
      {
        v21 = *v20;
        if ( !*v20 )
          goto LABEL_62;
        if ( v21 == 58 )
          break;
LABEL_46:
        v22 = v20++;
        if ( v21 == 44 )
        {
          SessionObjectDirectory = RtlCharToInteger(v20, 0xAu, &Value);
          if ( SessionObjectDirectory >= 0 )
          {
            *v22 = 0;
            SessionObjectDirectory = CsrLoadServerDll(v11, v4, Value);
            if ( SessionObjectDirectory >= 0 )
            {
              v7 = v29;
              v4 = 0;
              v8 = v33;
              ++i;
              goto LABEL_5;
            }
          }
          goto LABEL_62;
        }
      }
      if ( !v4 )
      {
        *v20++ = 0;
        v4 = v20;
        v21 = *v20;
        goto LABEL_46;
      }
      ++v20;
    }
  }
  CsrpLogFailure("CsrParseServerCommandLine");
  return (unsigned int)SessionObjectDirectory;
}

```

## disassembly

```asm
0x180005180  push    rbp
0x180005182  push    rbx
0x180005183  push    r12
0x180005185  push    r13
0x180005187  push    r14
0x180005189  push    r15
0x18000518b  lea     rbp, [rsp-108h]
0x180005193  sub     rsp, 208h
0x18000519a  mov     rax, cs:__security_cookie
0x1800051a1  xor     rax, rsp
0x1800051a4  mov     [rbp+130h+var_40], rax
0x1800051ab  xorps   xmm0, xmm0
0x1800051ae  mov     cs:CsrMaxApiRequestThreads, 10h
0x1800051b8  movups  xmmword ptr [rbp+130h+ObjectAttributes.ObjectName], xmm0
0x1800051bc  xor     r14d, r14d
0x1800051bf  mov     [rbp+130h+var_158], r9
0x1800051c3  movups  xmmword ptr [rbp+130h+ObjectAttributes+1Ch], xmm0
0x1800051c7  mov     cs:CsrObjectDirectory, r14
0x1800051ce  xor     eax, eax
0x1800051d0  movups  xmmword ptr [rsp+230h+ObjectAttributes.Length], xmm0
0x1800051d5  mov     [rsp+230h+Value], r14d
0x1800051da  mov     r13d, ecx
0x1800051dd  mov     rax, gs:60h
0x1800051e6  mov     r15, r8
0x1800051e9  mov     [rsp+230h+var_1C0], r8
0x1800051ee  mov     rbx, rdx
0x1800051f1  mov     [rbp+130h+var_150], rdx
0x1800051f5  mov     cs:CsrTotalPerProcessDataLength, r14d
0x1800051fc  mov     ecx, [rax+2C0h]
0x180005202  mov     cs:g_SessionId, ecx
0x180005208  call    CsrCreateSessionObjectDirectory
0x18000520d  mov     r12d, eax
0x180005210  test    eax, eax
0x180005212  jns     short loc_18000523B
0x180005214  mov     ecx, cs:ServiceSessionId
0x18000521a  cmp     cs:g_SessionId, ecx
0x180005220  jz      short loc_18000523B
0x180005222  mov     r8d, eax
0x180005225  lea     rcx, aCsrparseserver; "CsrParseServerCommandLine"
0x18000522c  mov     edx, 240h
0x180005231  call    CsrpLogFailure
0x180005236  jmp     loc_180005838
0x18000523b  mov     [rsp+230h+var_30], rdi
0x180005243  mov     edi, 1
0x180005248  mov     [rsp+230h+arg_0], rsi
0x180005250  cmp     edi, r13d
0x180005253  jnb     loc_180005828
0x180005259  mov     eax, edi
0x18000525b  mov     rsi, r14
0x18000525e  mov     rdx, [rbx+rax*8]
0x180005262  movzx   ecx, byte ptr [rdx]
0x180005265  test    cl, cl
0x180005267  jz      short loc_18000527A
0x180005269  cmp     cl, 3Dh ; '='
0x18000526c  jz      short loc_180005273
0x18000526e  inc     rdx
0x180005271  jmp     short loc_180005262
0x180005273  mov     byte ptr [rdx], 0
0x180005276  lea     rsi, [rdx+1]
0x18000527a  mov     rbx, [rbx+rax*8]
0x18000527e  lea     rdx, Str2; "ObjectDirectory"
0x180005285  mov     rcx, rbx; Str1
0x180005288  call    cs:__imp__stricmp
0x18000528f  nop     dword ptr [rax+rax+00h]
0x180005294  test    eax, eax
0x180005296  jnz     loc_180005474
0x18000529c  mov     eax, cs:g_SessionId
0x1800052a2  lea     r9, aWsLdS; "%ws\\%ld%s"
0x1800052a9  mov     [rsp+230h+var_200], rsi
0x1800052ae  lea     rcx, [rbp+130h+DstBuf]; DstBuf
0x1800052b2  mov     dword ptr [rsp+230h+var_208], eax
0x1800052b6  xorps   xmm0, xmm0
0x1800052b9  lea     rax, aSessions; "\\Sessions"
0x1800052c0  mov     edx, 100h; SizeInBytes
0x1800052c5  mov     r8d, 0FFh; MaxCount
0x1800052cb  mov     qword ptr [rsp+230h+InitialState], rax
0x1800052d0  movups  xmmword ptr [rsp+230h+DestinationString.Length], xmm0
0x1800052d5  call    cs:__imp__snprintf_s
0x1800052dc  nop     dword ptr [rax+rax+00h]
0x1800052e1  mov     eax, cs:ServiceSessionId
0x1800052e7  lea     rcx, [rsp+230h+DestinationString]; DestinationString
0x1800052ec  cmp     cs:g_SessionId, eax
0x1800052f2  jnz     short loc_1800052FF
0x1800052f4  mov     r14d, 0D0h
0x1800052fa  mov     rdx, rsi
0x1800052fd  jmp     short loc_180005309
0x1800052ff  mov     r14d, 0C0h
0x180005305  lea     rdx, [rbp+130h+DstBuf]; SourceString
0x180005309  call    cs:__imp_RtlInitString
0x180005310  nop     dword ptr [rax+rax+00h]
0x180005315  mov     r8b, 1; AllocateDestinationString
0x180005318  lea     rdx, [rsp+230h+DestinationString]; SourceString
0x18000531d  lea     rcx, CsrDirectoryName; DestinationString
0x180005324  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000532b  nop     dword ptr [rax+rax+00h]
0x180005330  mov     r12d, eax
0x180005333  test    eax, eax
0x180005335  js      loc_180005828
0x18000533b  lea     rax, CsrDirectoryName
0x180005342  mov     [rsp+230h+ObjectAttributes.Length], 30h ; '0'
0x18000534a  xorps   xmm0, xmm0
0x18000534d  mov     [rbp+130h+ObjectAttributes.ObjectName], rax
0x180005351  lea     r8, [rsp+230h+ObjectAttributes]; ObjectAttributes
0x180005356  mov     [rbp+130h+ObjectAttributes.RootDirectory], 0
0x18000535e  mov     edx, 0F000Fh; DesiredAccess
0x180005363  mov     [rbp+130h+ObjectAttributes.Attributes], r14d
0x180005367  lea     rcx, CsrObjectDirectory; DirectoryHandle
0x18000536e  movdqu  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005373  call    cs:__imp_NtCreateDirectoryObject
0x18000537a  nop     dword ptr [rax+rax+00h]
0x18000537f  mov     r12d, eax
0x180005382  test    eax, eax
0x180005384  js      loc_1800057E0
0x18000538a  call    CsrSetDirectorySecurity
0x18000538f  mov     r12d, eax
0x180005392  test    eax, eax
0x180005394  js      loc_1800057D5
0x18000539a  mov     rdx, [rbp+130h+var_158]
0x18000539e  mov     rcx, r15; Reserved6
0x1800053a1  call    CsrServerCreateApiPort
0x1800053a6  mov     r12d, eax
0x1800053a9  test    eax, eax
0x1800053ab  js      loc_1800057CA
0x1800053b1  mov     eax, cs:ServiceSessionId
0x1800053b7  cmp     cs:g_SessionId, eax
0x1800053bd  jnz     loc_180005466
0x1800053c3  xorps   xmm0, xmm0
0x1800053c6  mov     [rsp+230h+SymbolicLinkHandle], 0
0x1800053cf  lea     rdx, [rbp+130h+DstBuf]; SourceString
0x1800053d3  lea     rcx, [rsp+230h+DestinationString]; DestinationString
0x1800053d8  movups  xmmword ptr [rsp+230h+UnicodeString.Length], xmm0
0x1800053dd  call    cs:__imp_RtlInitString
0x1800053e4  nop     dword ptr [rax+rax+00h]
0x1800053e9  mov     r8b, 1; AllocateDestinationString
0x1800053ec  lea     rdx, [rsp+230h+DestinationString]; SourceString
0x1800053f1  lea     rcx, [rsp+230h+UnicodeString]; DestinationString
0x1800053f6  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800053fd  nop     dword ptr [rax+rax+00h]
0x180005402  lea     rax, [rsp+230h+UnicodeString]
0x180005407  mov     [rsp+230h+ObjectAttributes.Length], 30h ; '0'
0x18000540f  xorps   xmm0, xmm0
0x180005412  mov     [rbp+130h+ObjectAttributes.ObjectName], rax
0x180005416  lea     r9, CsrDirectoryName; Name
0x18000541d  mov     [rbp+130h+ObjectAttributes.RootDirectory], 0
0x180005425  lea     r8, [rsp+230h+ObjectAttributes]; ObjectAttributes
0x18000542a  mov     [rbp+130h+ObjectAttributes.Attributes], r14d
0x18000542e  mov     edx, 0F0001h; DesiredAccess
0x180005433  lea     rcx, [rsp+230h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180005438  movdqu  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000543d  call    cs:__imp_NtCreateSymbolicLinkObject
0x180005444  nop     dword ptr [rax+rax+00h]
0x180005449  lea     rcx, [rsp+230h+UnicodeString]; UnicodeString
0x18000544e  mov     r12d, eax
0x180005451  call    cs:__imp_RtlFreeUnicodeString
0x180005458  nop     dword ptr [rax+rax+00h]
0x18000545d  test    r12d, r12d
0x180005460  js      loc_180005828
0x180005466  xor     r14d, r14d
0x180005469  mov     rbx, [rbp+130h+var_150]
0x18000546d  inc     edi
0x18000546f  jmp     loc_180005250
0x180005474  lea     rdx, aMaxrequestthre; "MaxRequestThreads"
0x18000547b  mov     rcx, rbx; Str1
0x18000547e  call    cs:__imp__stricmp
0x180005485  nop     dword ptr [rax+rax+00h]
0x18000548a  test    eax, eax
0x18000548c  jnz     short loc_1800054C0
0x18000548e  test    rsi, rsi
0x180005491  jz      short loc_180005469
0x180005493  lea     r8, CsrMaxApiRequestThreads; Value
0x18000549a  xor     edx, edx; Base
0x18000549c  mov     rcx, rsi; String
0x18000549f  call    cs:__imp_RtlCharToInteger
0x1800054a6  nop     dword ptr [rax+rax+00h]
0x1800054ab  mov     r12d, eax
0x1800054ae  test    eax, eax
0x1800054b0  jns     short loc_180005469
0x1800054b2  mov     dword ptr [rsp+230h+InitialState], eax
0x1800054b6  mov     edx, 2DCh
0x1800054bb  jmp     loc_180005816
0x1800054c0  lea     rdx, aSharedsection_0; "SharedSection"
0x1800054c7  mov     rcx, rbx; Str1
0x1800054ca  call    cs:__imp__stricmp
0x1800054d1  nop     dword ptr [rax+rax+00h]
0x1800054d6  test    eax, eax
0x1800054d8  jnz     loc_180005674
0x1800054de  xorps   xmm0, xmm0
0x1800054e1  mov     qword ptr [rsp+230h+DestinationString.Length], r14
0x1800054e6  movups  xmmword ptr [rbp+130h+var_188.ObjectName], xmm0
0x1800054ea  xor     eax, eax
0x1800054ec  mov     [rsp+230h+SymbolicLinkHandle], r14
0x1800054f1  lea     rdx, aCsrsbsyncevent; "\\CsrSbSyncEvent"
0x1800054f8  lea     rcx, [rsp+230h+UnicodeString]; DestinationString
0x1800054fd  movups  xmmword ptr [rbp+130h+var_188+1Ch], xmm0
0x180005501  movups  xmmword ptr [rsp+230h+UnicodeString.Length], xmm0
0x180005506  movups  xmmword ptr [rbp+130h+var_188.Length], xmm0
0x18000550a  call    cs:__imp_RtlInitUnicodeString
0x180005511  nop     dword ptr [rax+rax+00h]
0x180005516  lea     rax, [rsp+230h+UnicodeString]
0x18000551b  mov     [rbp+130h+var_188.Length], 30h ; '0'
0x180005522  xorps   xmm0, xmm0
0x180005525  mov     [rbp+130h+var_188.ObjectName], rax
0x180005529  lea     r8, [rbp+130h+var_188]; ObjectAttributes
0x18000552d  mov     [rbp+130h+var_188.RootDirectory], r14
0x180005531  mov     edx, 100000h; DesiredAccess
0x180005536  mov     [rbp+130h+var_188.Attributes], r14d
0x18000553a  lea     rcx, [rsp+230h+DestinationString]; EventHandle
0x18000553f  movdqu  xmmword ptr [rbp+130h+var_188.SecurityDescriptor], xmm0
0x180005544  call    cs:__imp_NtOpenEvent
0x18000554b  nop     dword ptr [rax+rax+00h]
0x180005550  mov     r12d, eax
0x180005553  test    eax, eax
0x180005555  js      short loc_180005578
0x180005557  mov     rcx, qword ptr [rsp+230h+DestinationString.Length]; Object
0x18000555c  xor     r14b, r14b
0x18000555f  xor     r8d, r8d; Timeout
0x180005562  xor     edx, edx; Alertable
0x180005564  call    cs:__imp_NtWaitForSingleObject
0x18000556b  nop     dword ptr [rax+rax+00h]
0x180005570  mov     r12d, eax
0x180005573  jmp     loc_180005615
0x180005578  cmp     eax, 0C0000034h
0x18000557d  jnz     loc_180005828
0x180005583  mov     edx, 100002h
0x180005588  lea     rcx, [rsp+230h+SymbolicLinkHandle]
0x18000558d  call    CsrCreateLocalSystemSD
0x180005592  mov     r12d, eax
0x180005595  test    eax, eax
0x180005597  js      loc_1800057F2
0x18000559d  mov     r15, [rsp+230h+SymbolicLinkHandle]
0x1800055a2  lea     r8, [rbp+130h+var_188]; ObjectAttributes
0x1800055a6  xor     r9d, r9d; EventType
0x1800055a9  mov     [rbp+130h+var_188.SecurityDescriptor], r15
0x1800055ad  mov     edx, 100002h; DesiredAccess
0x1800055b2  mov     [rbp+130h+var_188.Attributes], 90h
0x1800055b9  lea     rcx, [rsp+230h+DestinationString]; EventHandle
0x1800055be  mov     [rsp+230h+InitialState], 0; InitialState
0x1800055c3  mov     r14b, 1
0x1800055c6  call    cs:__imp_NtCreateEvent
0x1800055cd  nop     dword ptr [rax+rax+00h]
0x1800055d2  mov     r12d, eax
0x1800055d5  cmp     eax, 40000000h
0x1800055da  jnz     short loc_1800055F8
0x1800055dc  mov     rcx, qword ptr [rsp+230h+DestinationString.Length]; Object
0x1800055e1  xor     r14b, r14b
0x1800055e4  xor     r8d, r8d; Timeout
0x1800055e7  xor     edx, edx; Alertable
0x1800055e9  call    cs:__imp_NtWaitForSingleObject
0x1800055f0  nop     dword ptr [rax+rax+00h]
0x1800055f5  mov     r12d, eax
0x1800055f8  mov     rcx, cs:CsrHeap; HeapHandle
0x1800055ff  mov     r8, r15; BaseAddress
0x180005602  xor     edx, edx; Flags
0x180005604  call    cs:__imp_RtlFreeHeap
0x18000560b  nop     dword ptr [rax+rax+00h]
0x180005610  mov     r15, [rsp+230h+var_1C0]
0x180005615  test    r12d, r12d
0x180005618  js      loc_180005828
0x18000561e  mov     rcx, rsi
0x180005621  call    CsrSrvCreateSharedSection
0x180005626  mov     r12d, eax
0x180005629  test    r14b, r14b
0x18000562c  jz      short loc_180005641
0x18000562e  mov     rcx, qword ptr [rsp+230h+DestinationString.Length]; EventHandle
0x180005633  xor     edx, edx; PreviousState
0x180005635  call    cs:__imp_NtSetEvent
0x18000563c  nop     dword ptr [rax+rax+00h]
0x180005641  mov     rcx, qword ptr [rsp+230h+DestinationString.Length]; Handle
0x180005646  call    cs:__imp_NtClose
0x18000564d  nop     dword ptr [rax+rax+00h]
0x180005652  test    r12d, r12d
0x180005655  js      loc_1800057EB
0x18000565b  xor     r8d, r8d
0x18000565e  lea     rcx, aCsrss_0; "CSRSS"
0x180005665  xor     edx, edx; PCSZ
0x180005667  call    CsrLoadServerDll
0x18000566c  mov     r12d, eax
0x18000566f  jmp     loc_180005466
0x180005674  lea     rdx, aServerdll; "ServerDLL"
0x18000567b  mov     rcx, rbx; Str1
0x18000567e  call    cs:__imp__stricmp
0x180005685  nop     dword ptr [rax+rax+00h]
0x18000568a  test    eax, eax
0x18000568c  jnz     loc_180005720
0x180005692  mov     rcx, rsi
0x180005695  mov     r12d, 0C000000Dh
0x18000569b  movzx   eax, byte ptr [rcx]
0x18000569e  test    al, al
0x1800056a0  jz      loc_18000580C
0x1800056a6  cmp     al, 3Ah ; ':'
0x1800056a8  jnz     short loc_1800056BB
0x1800056aa  test    r14, r14
0x1800056ad  jnz     short loc_180005718
0x1800056af  mov     [rcx], r14b
0x1800056b2  inc     rcx
0x1800056b5  mov     r14, rcx
0x1800056b8  movzx   eax, byte ptr [rcx]
0x1800056bb  mov     r15, rcx
0x1800056be  inc     rcx; String
0x1800056c1  cmp     al, 2Ch ; ','
  ... truncated ...
```
