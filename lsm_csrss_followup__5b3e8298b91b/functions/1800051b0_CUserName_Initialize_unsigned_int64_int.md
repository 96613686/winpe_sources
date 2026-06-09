# CUserName::Initialize(unsigned __int64,int)

- ea: `0x1800051b0`
- end: `0x18000546f`
- name: `?Initialize@CUserName@@UEAAJ_KH@Z`
- size: `703`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031400`

## callees

- `0x1800051b0`
- `0x1800067f0`
- `0x1800074c0`
- `0x18004b460`
- `0x18004b86c`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18000537b`
- `ntdll!NtDuplicateToken` at `0x18000537b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000540a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000540a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000539f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000539f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005435`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005435`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005208`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000525f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005208`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000525f`

## string_xrefs

- `0x1800052bb`: `GetTokenInformatino failed: 0x%x`
- `0x1800052e0`: `Can get the TOKEN_USER length`
- `0x1800053c3`: `Can get the TOKEN_USER length: 0x%x`
- `0x180005393`: `NtDuplicateToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::Initialize(CUserName *this, void *a2, int a3)
{
  void *v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  signed int v9; // eax
  HANDLE *v10; // r14
  NTSTATUS v11; // eax
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v14; // eax
  unsigned int v15; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-68h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-64h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-60h] BYREF
  _DWORD v21[4]; // [rsp+78h] [rbp-30h] BYREF

  if ( !a3 )
  {
    TokenInformationLength = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v7 = -2147024809;
      _DbgPrintMessage(8, "Can get the TOKEN_USER length");
    }
    else
    {
      if ( GetLastError() != 122 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "Can get the TOKEN_USER length: 0x%x", v7);
LABEL_12:
        if ( (v7 & 0x80000000) == 0 )
          return 0;
        goto LABEL_15;
      }
      v5 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 201) = v5;
      if ( v5 )
      {
        if ( GetTokenInformation(a2, TokenUser, v5, TokenInformationLength, &ReturnLength) )
        {
          v6 = CUserName::ResolveUserName((PSID **)this, a2);
          v7 = v6;
          if ( v6 >= 0 )
          {
            *((_DWORD *)this + 400) |= 2u;
            return 0;
          }
          _DbgPrintMessage(8, "ResolveUserName failed: 0x%x in %s", v6, "CUserName::InitializeUserName");
          goto LABEL_15;
        }
        v9 = GetLastError();
        v7 = v9;
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
        _DbgPrintMessage(8, "GetTokenInformatino failed: 0x%x", v7);
        goto LABEL_12;
      }
      v7 = -2147024882;
    }
LABEL_15:
    _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v7, "CUserName::Initialize");
    return v7;
  }
  v10 = (HANDLE *)((char *)this + 1592);
  v21[2] = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v21[0] = 12;
  v21[1] = 2;
  ObjectAttributes.SecurityQualityOfService = v21;
  v11 = NtDuplicateToken(a2, 0x2000000u, &ObjectAttributes, 0, TokenPrimary, (PHANDLE)this + 199);
  v7 = v11 | 0x10000000;
  if ( (v11 | 0x10000000) != 0xD0000022 )
  {
    if ( v11 < 0 )
    {
      _DbgPrintMessage(8, "NtDuplicateToken failed: 0x%x in %s", v7, "CUserName::Initialize");
      return v7;
    }
LABEL_20:
    CurrentProcessId = GetCurrentProcessId();
    *((_DWORD *)this + 400) |= 1u;
    *((_DWORD *)this + 672) = CurrentProcessId;
    return 0;
  }
  CurrentProcess = GetCurrentProcess();
  v17 = GetCurrentProcess();
  if ( DuplicateHandle(v17, a2, CurrentProcess, v10, 0, 0, 2u) )
    goto LABEL_20;
  v14 = GetLastError();
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  _DbgPrintMessage(8, "DuplicateHandle failed: 0x%x", v15);
  return v15;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_10], rbx
0x1800051b5  mov     [rsp+arg_18], rbp
0x1800051ba  push    rsi
0x1800051bb  push    rdi
0x1800051bc  push    r14
0x1800051be  sub     rsp, 90h
0x1800051c5  mov     rax, cs:__security_cookie
0x1800051cc  xor     rax, rsp
0x1800051cf  mov     [rsp+0A8h+var_20], rax
0x1800051d7  xor     edi, edi
0x1800051d9  xor     r9d, r9d; EffectiveOnly
0x1800051dc  mov     rbp, rdx
0x1800051df  mov     rsi, rcx
0x1800051e2  test    r8d, r8d
0x1800051e5  jnz     loc_180005318
0x1800051eb  lea     rax, [rsp+0A8h+TokenInformationLength]
0x1800051f0  mov     [rsp+0A8h+TokenInformationLength], edi
0x1800051f4  xor     r8d, r8d; TokenInformation
0x1800051f7  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x1800051fc  mov     edx, 1; TokenInformationClass
0x180005201  mov     [rsp+0A8h+var_64], edi
0x180005205  mov     rcx, rbp; TokenHandle
0x180005208  call    cs:__imp_GetTokenInformation
0x18000520e  test    eax, eax
0x180005210  jnz     loc_1800052E0
0x180005216  call    cs:__imp_GetLastError
0x18000521c  cmp     eax, 7Ah ; 'z'
0x18000521f  jnz     loc_1800053B7
0x180005225  mov     ecx, [rsp+0A8h+TokenInformationLength]; unsigned __int64
0x180005229  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005230  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005235  mov     [rsi+648h], rax
0x18000523c  test    rax, rax
0x18000523f  jz      loc_180005445
0x180005245  mov     r9d, [rsp+0A8h+TokenInformationLength]; TokenInformationLength
0x18000524a  lea     rcx, [rsp+0A8h+var_64]
0x18000524f  mov     [rsp+0A8h+ReturnLength], rcx; ReturnLength
0x180005254  mov     r8, rax; TokenInformation
0x180005257  mov     rcx, rbp; TokenHandle
0x18000525a  mov     edx, 1; TokenInformationClass
0x18000525f  call    cs:__imp_GetTokenInformation
0x180005265  test    eax, eax
0x180005267  jz      short loc_1800052AF
0x180005269  mov     rdx, rbp; void *
0x18000526c  mov     rcx, rsi; this
0x18000526f  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x180005274  mov     ebx, eax
0x180005276  test    eax, eax
0x180005278  js      loc_18000544F
0x18000527e  or      dword ptr [rsi+640h], 2
0x180005285  mov     eax, edi
0x180005287  mov     rcx, [rsp+0A8h+var_20]
0x18000528f  xor     rcx, rsp; StackCookie
0x180005292  call    __security_check_cookie
0x180005297  lea     r11, [rsp+0A8h+var_18]
0x18000529f  mov     rbx, [r11+30h]
0x1800052a3  mov     rbp, [r11+38h]
0x1800052a7  mov     rsp, r11
0x1800052aa  pop     r14
0x1800052ac  pop     rdi
0x1800052ad  pop     rsi
0x1800052ae  retn
0x1800052af  call    cs:__imp_GetLastError
0x1800052b5  mov     ebx, eax
0x1800052b7  test    eax, eax
0x1800052b9  jg      short loc_1800052D5
0x1800052bb  lea     rdx, aGettokeninform_1; "GetTokenInformatino failed: 0x%x"
0x1800052c2  mov     r8d, ebx
0x1800052c5  mov     ecx, 8; int
0x1800052ca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800052cf  test    ebx, ebx
0x1800052d1  jns     short loc_180005285
0x1800052d3  jmp     short loc_1800052F6
0x1800052d5  movzx   ebx, ax
0x1800052d8  or      ebx, 80070000h
0x1800052de  jmp     short loc_1800052BB
0x1800052e0  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x1800052e7  mov     ecx, 8; int
0x1800052ec  mov     ebx, 80070057h
0x1800052f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800052f6  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x1800052fd  lea     r9, aCusernameIniti_1; "CUserName::Initialize"
0x180005304  mov     r8d, ebx
0x180005307  mov     ecx, 8; int
0x18000530c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005311  mov     eax, ebx
0x180005313  jmp     loc_180005287
0x180005318  lea     r14, [rcx+638h]
0x18000531f  mov     [rsp+0A8h+var_28], 1
0x18000532a  lea     rax, [rsp+0A8h+var_30]
0x18000532f  mov     [rsp+0A8h+NewTokenHandle], r14; NewTokenHandle
0x180005334  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180005339  mov     dword ptr [rsp+0A8h+ReturnLength], 1; TokenType
0x180005341  mov     edx, 2000000h; DesiredAccess
0x180005346  mov     qword ptr [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18000534f  mov     rcx, rbp; ExistingTokenHandle
0x180005352  mov     qword ptr [rsp+0A8h+ObjectAttributes.Attributes], rdi
0x180005357  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rdi
0x18000535c  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rdi
0x180005361  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rdi
0x180005366  mov     [rsp+0A8h+var_30], 0Ch
0x18000536e  mov     [rsp+0A8h+var_2C], 2
0x180005376  mov     [rsp+0A8h+ObjectAttributes.SecurityQualityOfService], rax
0x18000537b  call    cs:__imp_NtDuplicateToken
0x180005381  mov     ebx, eax
0x180005383  bts     ebx, 1Ch
0x180005387  cmp     ebx, 0D0000022h
0x18000538d  jz      short loc_18000540A
0x18000538f  test    ebx, ebx
0x180005391  jns     short loc_18000539F
0x180005393  lea     rdx, aNtduplicatetok; "NtDuplicateToken failed: 0x%x in %s"
0x18000539a  jmp     loc_1800052FD
0x18000539f  call    cs:__imp_GetCurrentProcessId
0x1800053a5  or      dword ptr [rsi+640h], 1
0x1800053ac  mov     [rsi+0A80h], eax
0x1800053b2  jmp     loc_180005285
0x1800053b7  call    cs:__imp_GetLastError
0x1800053bd  mov     ebx, eax
0x1800053bf  test    eax, eax
0x1800053c1  jg      short loc_1800053CF
0x1800053c3  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x1800053ca  jmp     loc_1800052C2
0x1800053cf  movzx   ebx, ax
0x1800053d2  or      ebx, 80070000h
0x1800053d8  jmp     short loc_1800053C3
0x1800053da  call    cs:__imp_GetLastError
0x1800053e0  mov     ebx, eax
0x1800053e2  test    eax, eax
0x1800053e4  jle     short loc_1800053EF
0x1800053e6  movzx   ebx, ax
0x1800053e9  or      ebx, 80070000h
0x1800053ef  mov     r8d, ebx
0x1800053f2  lea     rdx, aDuplicatehandl_3; "DuplicateHandle failed: 0x%x"
0x1800053f9  mov     ecx, 8; int
0x1800053fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005403  mov     eax, ebx
0x180005405  jmp     loc_180005287
0x18000540a  call    cs:__imp_GetCurrentProcess
0x180005410  mov     rbx, rax
0x180005413  call    cs:__imp_GetCurrentProcess
0x180005419  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x180005421  mov     r9, r14; lpTargetHandle
0x180005424  mov     rcx, rax; hSourceProcessHandle
0x180005427  mov     dword ptr [rsp+0A8h+NewTokenHandle], edi; bInheritHandle
0x18000542b  mov     r8, rbx; hTargetProcessHandle
0x18000542e  mov     dword ptr [rsp+0A8h+ReturnLength], edi; dwDesiredAccess
0x180005432  mov     rdx, rbp; hSourceHandle
0x180005435  call    cs:__imp_DuplicateHandle
0x18000543b  test    eax, eax
0x18000543d  jnz     loc_18000539F
0x180005443  jmp     short loc_1800053DA
0x180005445  mov     ebx, 8007000Eh
0x18000544a  jmp     loc_1800052F6
0x18000544f  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x180005456  mov     r8d, eax
0x180005459  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x180005460  mov     ecx, 8; int
0x180005465  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000546a  jmp     loc_1800052F6
```
