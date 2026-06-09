# CUserName::Initialize(unsigned __int64,int)

- ea: `0x1800051f0`
- end: `0x1800054f9`
- name: `?Initialize@CUserName@@UEAAJ_KH@Z`
- size: `777`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800334a0`

## callees

- `0x1800051f0`
- `0x180006980`
- `0x1800077a0`
- `0x18004e850`
- `0x18004ec5c`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800053d4`
- `ntdll!NtDuplicateToken` at `0x1800053d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000525c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000525c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000547f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000548e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000547f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000548e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005402`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800054b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800054b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005248`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800052ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005248`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800052ab`

## string_xrefs

- `0x180005314`: `GetTokenInformatino failed: 0x%x`
- `0x180005339`: `Can get the TOKEN_USER length`
- `0x180005432`: `Can get the TOKEN_USER length: 0x%x`
- `0x1800053f6`: `NtDuplicateToken failed: 0x%x in %s`

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
0x1800051f0  mov     [rsp+arg_10], rbx
0x1800051f5  mov     [rsp+arg_18], rbp
0x1800051fa  push    rsi
0x1800051fb  push    rdi
0x1800051fc  push    r14
0x1800051fe  sub     rsp, 90h
0x180005205  mov     rax, cs:__security_cookie
0x18000520c  xor     rax, rsp
0x18000520f  mov     [rsp+0A8h+var_20], rax
0x180005217  xor     edi, edi
0x180005219  xor     r9d, r9d; EffectiveOnly
0x18000521c  mov     rbp, rdx
0x18000521f  mov     rsi, rcx
0x180005222  test    r8d, r8d
0x180005225  jnz     loc_180005371
0x18000522b  lea     rax, [rsp+0A8h+TokenInformationLength]
0x180005230  mov     [rsp+0A8h+TokenInformationLength], edi
0x180005234  xor     r8d, r8d; TokenInformation
0x180005237  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18000523c  mov     edx, 1; TokenInformationClass
0x180005241  mov     [rsp+0A8h+var_64], edi
0x180005245  mov     rcx, rbp; TokenHandle
0x180005248  call    cs:__imp_GetTokenInformation
0x18000524f  nop     dword ptr [rax+rax+00h]
0x180005254  test    eax, eax
0x180005256  jnz     loc_180005339
0x18000525c  call    cs:__imp_GetLastError
0x180005263  nop     dword ptr [rax+rax+00h]
0x180005268  cmp     eax, 7Ah ; 'z'
0x18000526b  jnz     loc_180005420
0x180005271  mov     ecx, [rsp+0A8h+TokenInformationLength]; unsigned __int64
0x180005275  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000527c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005281  mov     [rsi+648h], rax
0x180005288  test    rax, rax
0x18000528b  jz      loc_1800054CF
0x180005291  mov     r9d, [rsp+0A8h+TokenInformationLength]; TokenInformationLength
0x180005296  lea     rcx, [rsp+0A8h+var_64]
0x18000529b  mov     [rsp+0A8h+ReturnLength], rcx; ReturnLength
0x1800052a0  mov     r8, rax; TokenInformation
0x1800052a3  mov     rcx, rbp; TokenHandle
0x1800052a6  mov     edx, 1; TokenInformationClass
0x1800052ab  call    cs:__imp_GetTokenInformation
0x1800052b2  nop     dword ptr [rax+rax+00h]
0x1800052b7  test    eax, eax
0x1800052b9  jz      short loc_180005302
0x1800052bb  mov     rdx, rbp; void *
0x1800052be  mov     rcx, rsi; this
0x1800052c1  call    ?ResolveUserName@CUserName@@AEAAJPEAX@Z; CUserName::ResolveUserName(void *)
0x1800052c6  mov     ebx, eax
0x1800052c8  test    eax, eax
0x1800052ca  js      loc_1800054D9
0x1800052d0  or      dword ptr [rsi+640h], 2
0x1800052d7  mov     eax, edi
0x1800052d9  mov     rcx, [rsp+0A8h+var_20]
0x1800052e1  xor     rcx, rsp; StackCookie
0x1800052e4  call    __security_check_cookie
0x1800052e9  lea     r11, [rsp+0A8h+var_18]
0x1800052f1  mov     rbx, [r11+30h]
0x1800052f5  mov     rbp, [r11+38h]
0x1800052f9  mov     rsp, r11
0x1800052fc  pop     r14
0x1800052fe  pop     rdi
0x1800052ff  pop     rsi
0x180005300  retn
0x180005302  call    cs:__imp_GetLastError
0x180005309  nop     dword ptr [rax+rax+00h]
0x18000530e  mov     ebx, eax
0x180005310  test    eax, eax
0x180005312  jg      short loc_18000532E
0x180005314  lea     rdx, aGettokeninform_1; "GetTokenInformatino failed: 0x%x"
0x18000531b  mov     r8d, ebx
0x18000531e  mov     ecx, 8; int
0x180005323  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005328  test    ebx, ebx
0x18000532a  jns     short loc_1800052D7
0x18000532c  jmp     short loc_18000534F
0x18000532e  movzx   ebx, ax
0x180005331  or      ebx, 80070000h
0x180005337  jmp     short loc_180005314
0x180005339  lea     rdx, aCanGetTheToken; "Can get the TOKEN_USER length"
0x180005340  mov     ecx, 8; int
0x180005345  mov     ebx, 80070057h
0x18000534a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000534f  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x180005356  lea     r9, aCusernameIniti_1; "CUserName::Initialize"
0x18000535d  mov     r8d, ebx
0x180005360  mov     ecx, 8; int
0x180005365  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000536a  mov     eax, ebx
0x18000536c  jmp     loc_1800052D9
0x180005371  lea     r14, [rcx+638h]
0x180005378  mov     [rsp+0A8h+var_28], 1
0x180005383  lea     rax, [rsp+0A8h+var_30]
0x180005388  mov     [rsp+0A8h+NewTokenHandle], r14; NewTokenHandle
0x18000538d  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180005392  mov     dword ptr [rsp+0A8h+ReturnLength], 1; TokenType
0x18000539a  mov     edx, 2000000h; DesiredAccess
0x18000539f  mov     qword ptr [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800053a8  mov     rcx, rbp; ExistingTokenHandle
0x1800053ab  mov     qword ptr [rsp+0A8h+ObjectAttributes.Attributes], rdi
0x1800053b0  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rdi
0x1800053b5  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rdi
0x1800053ba  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rdi
0x1800053bf  mov     [rsp+0A8h+var_30], 0Ch
0x1800053c7  mov     [rsp+0A8h+var_2C], 2
0x1800053cf  mov     [rsp+0A8h+ObjectAttributes.SecurityQualityOfService], rax
0x1800053d4  call    cs:__imp_NtDuplicateToken
0x1800053db  nop     dword ptr [rax+rax+00h]
0x1800053e0  mov     ebx, eax
0x1800053e2  bts     ebx, 1Ch
0x1800053e6  cmp     ebx, 0D0000022h
0x1800053ec  jz      loc_18000547F
0x1800053f2  test    ebx, ebx
0x1800053f4  jns     short loc_180005402
0x1800053f6  lea     rdx, aNtduplicatetok; "NtDuplicateToken failed: 0x%x in %s"
0x1800053fd  jmp     loc_180005356
0x180005402  call    cs:__imp_GetCurrentProcessId
0x180005409  nop     dword ptr [rax+rax+00h]
0x18000540e  or      dword ptr [rsi+640h], 1
0x180005415  mov     [rsi+0A80h], eax
0x18000541b  jmp     loc_1800052D7
0x180005420  call    cs:__imp_GetLastError
0x180005427  nop     dword ptr [rax+rax+00h]
0x18000542c  mov     ebx, eax
0x18000542e  test    eax, eax
0x180005430  jg      short loc_18000543E
0x180005432  lea     rdx, aCanGetTheToken_0; "Can get the TOKEN_USER length: 0x%x"
0x180005439  jmp     loc_18000531B
0x18000543e  movzx   ebx, ax
0x180005441  or      ebx, 80070000h
0x180005447  jmp     short loc_180005432
0x180005449  call    cs:__imp_GetLastError
0x180005450  nop     dword ptr [rax+rax+00h]
0x180005455  mov     ebx, eax
0x180005457  test    eax, eax
0x180005459  jle     short loc_180005464
0x18000545b  movzx   ebx, ax
0x18000545e  or      ebx, 80070000h
0x180005464  mov     r8d, ebx
0x180005467  lea     rdx, aDuplicatehandl_3; "DuplicateHandle failed: 0x%x"
0x18000546e  mov     ecx, 8; int
0x180005473  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005478  mov     eax, ebx
0x18000547a  jmp     loc_1800052D9
0x18000547f  call    cs:__imp_GetCurrentProcess
0x180005486  nop     dword ptr [rax+rax+00h]
0x18000548b  mov     rbx, rax
0x18000548e  call    cs:__imp_GetCurrentProcess
0x180005495  nop     dword ptr [rax+rax+00h]
0x18000549a  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x1800054a2  mov     r9, r14; lpTargetHandle
0x1800054a5  mov     rcx, rax; hSourceProcessHandle
0x1800054a8  mov     dword ptr [rsp+0A8h+NewTokenHandle], edi; bInheritHandle
0x1800054ac  mov     r8, rbx; hTargetProcessHandle
0x1800054af  mov     dword ptr [rsp+0A8h+ReturnLength], edi; dwDesiredAccess
0x1800054b3  mov     rdx, rbp; hSourceHandle
0x1800054b6  call    cs:__imp_DuplicateHandle
0x1800054bd  nop     dword ptr [rax+rax+00h]
0x1800054c2  test    eax, eax
0x1800054c4  jnz     loc_180005402
0x1800054ca  jmp     loc_180005449
0x1800054cf  mov     ebx, 8007000Eh
0x1800054d4  jmp     loc_18000534F
0x1800054d9  lea     r9, aCusernameIniti; "CUserName::InitializeUserName"
0x1800054e0  mov     r8d, eax
0x1800054e3  lea     rdx, aResolveusernam; "ResolveUserName failed: 0x%x in %s"
0x1800054ea  mov     ecx, 8; int
0x1800054ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800054f4  jmp     loc_18000534F
```
