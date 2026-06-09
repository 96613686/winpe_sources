# LsapOpenTokenByLogonIdEx(_LUID *,_SECURITY_IMPERSONATION_LEVEL,void * *)

- ea: `0x180008340`
- end: `0x18000856f`
- name: `?LsapOpenTokenByLogonIdEx@@YAJPEAU_LUID@@W4_SECURITY_IMPERSONATION_LEVEL@@PEAPEAX@Z`
- size: `559`
- prototype: `int(struct _LUID *, enum _SECURITY_IMPERSONATION_LEVEL, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800077f0`
- `0x18000b7d0`
- `0x18007b49c`
- `0x18007ef50`
- `0x180081810`
- `0x1800cd378`

## callees

- `0x180007880`
- `0x180008340`
- `0x1800093b0`
- `0x180009410`
- `0x1800b86d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008510`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008510`
- `ntdll!NtImpersonateAnonymousToken` at `0x1800084d7`
- `ntdll!NtImpersonateAnonymousToken` at `0x1800084d7`
- `ntdll!NtClose` at `0x18000854d`
- `ntdll!NtClose` at `0x18000855e`
- `ntdll!NtClose` at `0x18000854d`
- `ntdll!NtClose` at `0x18000855e`
- `ntdll!NtDuplicateToken` at `0x180008407`
- `ntdll!NtDuplicateToken` at `0x180008407`
- `ntdll!NtSetInformationThread` at `0x180008532`
- `ntdll!NtSetInformationThread` at `0x180008532`
- `ntdll!NtOpenThreadToken` at `0x1800084af`
- `ntdll!NtOpenThreadToken` at `0x1800084fb`
- `ntdll!NtOpenThreadToken` at `0x1800084af`
- `ntdll!NtOpenThreadToken` at `0x1800084fb`

## pseudocode

```c
__int64 __fastcall LsapOpenTokenByLogonIdEx(struct _LUID *a1, enum _SECURITY_IMPERSONATION_LEVEL a2, void **a3)
{
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  struct _LSAP_LOGON_SESSION *v7; // rdi
  void *v8; // rcx
  NTSTATUS v9; // ebx
  NTSTATUS v11; // eax
  void *TokenHandle; // [rsp+30h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  __int64 v15; // [rsp+70h] [rbp+17h] BYREF
  int v16; // [rsp+78h] [rbp+1Fh]

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v15 = 0;
  v16 = 0;
  Handle = 0;
  TokenHandle = 0;
  LogonSession = LsapLocateLogonSession(a1);
  v7 = LogonSession;
  if ( LogonSession )
  {
    v8 = (void *)*((_QWORD *)LogonSession + 36);
    if ( v8 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.SecurityQualityOfService = &v15;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      ObjectAttributes.SecurityDescriptor = 0;
      LODWORD(v15) = 12;
      HIDWORD(v15) = a2;
      LOWORD(v16) = 0;
      v9 = NtDuplicateToken(v8, 0xF01FFu, &ObjectAttributes, 0, TokenImpersonation, &Handle);
      if ( v9 >= 0 )
      {
        v9 = LsapAdjustTokenObjectIntegrity(Handle);
        if ( v9 >= 0 )
        {
          v9 = 0;
          *a3 = Handle;
          Handle = 0;
        }
      }
    }
    else
    {
      v9 = -1073741700;
    }
  }
  else
  {
    if ( a1->LowPart != LsapAnonymousLogonId.LowPart || a1->HighPart != LsapAnonymousLogonId.HighPart )
    {
      v9 = -1073741729;
      goto LABEL_6;
    }
    v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x1Cu, 1u, &TokenHandle);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( v11 != -1073741700 )
        goto LABEL_6;
      TokenHandle = 0;
    }
    v9 = NtImpersonateAnonymousToken((HANDLE)0xFFFFFFFFFFFFFFFELL);
    if ( v9 >= 0 )
    {
      v9 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xF01FFu, 1u, a3);
      if ( TokenHandle )
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
      else
        RevertToSelf();
    }
  }
LABEL_6:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v7 )
    LsapReleaseLogonSession(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008340  push    rbp
0x180008342  push    rbx
0x180008343  push    rsi
0x180008344  push    rdi
0x180008345  push    r14
0x180008347  lea     rbp, [rsp-37h]
0x18000834c  sub     rsp, 90h
0x180008353  mov     rax, cs:__security_cookie
0x18000835a  xor     rax, rsp
0x18000835d  mov     [rbp+57h+var_30], rax
0x180008361  xor     eax, eax
0x180008363  xorps   xmm0, xmm0
0x180008366  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000836a  mov     [rbp+57h+var_40], rax
0x18000836e  mov     rsi, r8
0x180008371  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180008375  mov     [rbp+57h+var_38], eax
0x180008378  mov     r14d, edx
0x18000837b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000837f  mov     [rbp+57h+Handle], rax
0x180008383  mov     rbx, rcx
0x180008386  mov     [rbp+57h+TokenHandle], rax
0x18000838a  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x18000838f  mov     rdi, rax
0x180008392  test    rax, rax
0x180008395  jz      loc_18000847D
0x18000839b  mov     rcx, [rax+120h]; ExistingTokenHandle
0x1800083a2  test    rcx, rcx
0x1800083a5  jz      loc_180008543
0x1800083ab  lea     rax, [rbp+57h+var_40]
0x1800083af  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800083b6  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x1800083ba  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800083be  lea     rax, [rbp+57h+Handle]
0x1800083c2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800083ca  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x1800083cf  xor     r9d, r9d; EffectiveOnly
0x1800083d2  mov     edx, 0F01FFh; DesiredAccess
0x1800083d7  mov     [rsp+0B0h+TokenType], 2; TokenType
0x1800083df  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800083e6  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800083ee  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x1800083f6  mov     dword ptr [rbp+57h+var_40], 0Ch
0x1800083fd  mov     dword ptr [rbp+57h+var_40+4], r14d
0x180008401  mov     word ptr [rbp+57h+var_38], 0
0x180008407  call    cs:__imp_NtDuplicateToken
0x18000840e  nop     dword ptr [rax+rax+00h]
0x180008413  mov     ebx, eax
0x180008415  test    eax, eax
0x180008417  js      short loc_180008439
0x180008419  mov     rcx, [rbp+57h+Handle]; Handle
0x18000841d  call    LsapAdjustTokenObjectIntegrity
0x180008422  mov     ebx, eax
0x180008424  test    eax, eax
0x180008426  js      short loc_180008439
0x180008428  mov     rax, [rbp+57h+Handle]
0x18000842c  xor     ebx, ebx
0x18000842e  mov     [rsi], rax
0x180008431  mov     [rbp+57h+Handle], 0
0x180008439  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18000843d  test    rcx, rcx
0x180008440  jnz     loc_18000854D
0x180008446  mov     rcx, [rbp+57h+Handle]; Handle
0x18000844a  test    rcx, rcx
0x18000844d  jnz     loc_18000855E
0x180008453  test    rdi, rdi
0x180008456  jz      short loc_180008460
0x180008458  mov     rcx, rdi; struct _LSAP_LOGON_SESSION *
0x18000845b  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x180008460  mov     eax, ebx
0x180008462  mov     rcx, [rbp+57h+var_30]
0x180008466  xor     rcx, rsp; StackCookie
0x180008469  call    __security_check_cookie
0x18000846e  add     rsp, 90h
0x180008475  pop     r14
0x180008477  pop     rdi
0x180008478  pop     rsi
0x180008479  pop     rbx
0x18000847a  pop     rbp
0x18000847b  retn
0x18000847d  mov     ecx, cs:?LsapAnonymousLogonId@@3U_LUID@@A.LowPart; _LUID LsapAnonymousLogonId ...
0x180008483  cmp     [rbx], ecx
0x180008485  jz      short loc_18000848E
0x180008487  mov     ebx, 0C000005Fh
0x18000848c  jmp     short loc_180008439
0x18000848e  mov     ecx, cs:?LsapAnonymousLogonId@@3U_LUID@@A.HighPart; _LUID LsapAnonymousLogonId ...
0x180008494  cmp     [rbx+4], ecx
0x180008497  jnz     short loc_180008487
0x180008499  mov     r14, 0FFFFFFFFFFFFFFFEh
0x1800084a0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800084a4  mov     rcx, r14; ThreadHandle
0x1800084a7  mov     r8b, 1; OpenAsSelf
0x1800084aa  mov     edx, 1Ch; DesiredAccess
0x1800084af  call    cs:__imp_NtOpenThreadToken
0x1800084b6  nop     dword ptr [rax+rax+00h]
0x1800084bb  mov     ebx, eax
0x1800084bd  test    eax, eax
0x1800084bf  jns     short loc_1800084D4
0x1800084c1  cmp     eax, 0C000007Ch
0x1800084c6  jnz     loc_180008439
0x1800084cc  mov     [rbp+57h+TokenHandle], 0
0x1800084d4  mov     rcx, r14; Thread
0x1800084d7  call    cs:__imp_NtImpersonateAnonymousToken
0x1800084de  nop     dword ptr [rax+rax+00h]
0x1800084e3  mov     ebx, eax
0x1800084e5  test    eax, eax
0x1800084e7  js      loc_180008439
0x1800084ed  mov     r9, rsi; TokenHandle
0x1800084f0  mov     r8b, 1; OpenAsSelf
0x1800084f3  mov     edx, 0F01FFh; DesiredAccess
0x1800084f8  mov     rcx, r14; ThreadHandle
0x1800084fb  call    cs:__imp_NtOpenThreadToken
0x180008502  nop     dword ptr [rax+rax+00h]
0x180008507  cmp     [rbp+57h+TokenHandle], 0
0x18000850c  mov     ebx, eax
0x18000850e  jnz     short loc_180008521
0x180008510  call    cs:__imp_RevertToSelf
0x180008517  nop     dword ptr [rax+rax+00h]
0x18000851c  jmp     loc_180008439
0x180008521  mov     r9d, 8; ThreadInformationLength
0x180008527  lea     r8, [rbp+57h+TokenHandle]; ThreadInformation
0x18000852b  mov     rcx, r14; ThreadHandle
0x18000852e  lea     edx, [r9-3]; ThreadInformationClass
0x180008532  call    cs:__imp_NtSetInformationThread
0x180008539  nop     dword ptr [rax+rax+00h]
0x18000853e  jmp     loc_180008439
0x180008543  mov     ebx, 0C000007Ch
0x180008548  jmp     loc_180008439
0x18000854d  call    cs:__imp_NtClose
0x180008554  nop     dword ptr [rax+rax+00h]
0x180008559  jmp     loc_180008446
0x18000855e  call    cs:__imp_NtClose
0x180008565  nop     dword ptr [rax+rax+00h]
0x18000856a  jmp     loc_180008453
```
