# KerbTicklePackage(_KERB_LOGON_SESSION *,_UNICODE_STRING *)

- ea: `0x1800c5640`
- end: `0x1800c597c`
- name: `?KerbTicklePackage@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_UNICODE_STRING@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a5510`

## callees

- `0x180007e80`
- `0x1800627b0`
- `0x18006517c`
- `0x18006d608`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800c4a0c`
- `0x1800c5640`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c586b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c5942`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c586b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c5942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c56a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c56a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c5971`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c5697`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c5697`
- `ntdll!RtlInitUnicodeString` at `0x1800c5713`
- `ntdll!RtlInitUnicodeString` at `0x1800c5713`
- `ntdll!NtOpenThreadToken` at `0x1800c57f0`
- `ntdll!NtOpenThreadToken` at `0x1800c57f0`
- `ntdll!RtlEnterCriticalSection` at `0x1800c58df`
- `ntdll!RtlEnterCriticalSection` at `0x1800c58df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c5905`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c5905`

## string_xrefs

- `0x1800c5810`: `NtOpenThreadToken failed %x\n`
- `0x1800c5875`: `Unable to impersonate the client token handle.\n`
- `0x1800c594c`: `Unable to impersonate the client token handle.\n`
- `0x1800c5856`: `Unable to get the client token handle %#x\n`

## pseudocode

```c
__int64 __fastcall KerbTicklePackage(struct _RTL_CRITICAL_SECTION *a1, struct _UNICODE_STRING *a2)
{
  struct _KERB_CREDMAN_CRED *v2; // r14
  void *p_TokenHandle; // rdi
  NTSTATUS v6; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  _DWORD *v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // [rsp+0h] [rbp-30h] BYREF
  struct _UNICODE_STRING *v21; // [rsp+20h] [rbp-10h]
  struct _KERB_CREDMAN_CRED *v22; // [rsp+30h] [rbp+0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+10h] BYREF
  struct _KERB_PRIMARY_CREDENTIAL *v25; // [rsp+48h] [rbp+18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+20h] BYREF

  v2 = 0;
  v25 = 0;
  v22 = 0;
  TokenHandle = 0;
  hObject = 0;
  DestinationString = 0;
  if ( (a2->MaximumLength & 1) != 0 )
  {
    p_TokenHandle = 0;
    v6 = -1073741811;
LABEL_3:
    RevertToSelf();
    goto LABEL_4;
  }
  RtlInitUnicodeString(&DestinationString, L"*Session");
  p_TokenHandle = 0;
  v11 = a2->MaximumLength + 2LL;
  if ( v11 > g_ulMaxStackAllocSize )
    goto LABEL_45;
  v12 = v11 + g_ulAdditionalProbeSize + 8;
  if ( v12 < v11 || !(unsigned int)VerifyStackAvailable(v12, v8, v9, v10) )
    goto LABEL_45;
  v13 = v11 + 23;
  if ( v11 + 23 <= v11 + 8 )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  p_TokenHandle = &v22;
  if ( &v20 == (__int64 *)-48LL || (LODWORD(v22) = 1801679955, (p_TokenHandle = &TokenHandle) == 0) )
  {
LABEL_45:
    if ( v11 + 8 >= v11 )
    {
      v17 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_TokenHandle = v17;
      if ( v17 )
      {
        *v17 = 1885431112;
        p_TokenHandle = v17 + 2;
      }
    }
  }
  if ( p_TokenHandle )
  {
    memset_0(p_TokenHandle, 0, a2->MaximumLength + 2LL);
    memcpy_0(p_TokenHandle, a2->Buffer, a2->Length);
    v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741700 )
    {
      v18 = ((__int64 (__fastcall *)(HANDLE *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(
              &a1[1].LockSemaphore,
              &hObject);
      v6 = v18;
      if ( v18 >= 0 )
      {
        if ( SetThreadToken(0, hObject) )
        {
          v19 = KerbConvertCertCredential(
                  (struct _KERB_LOGON_SESSION *)a1,
                  (const unsigned __int16 *)p_TokenHandle,
                  0x10u,
                  0,
                  &DestinationString,
                  &v25);
          v6 = v19;
          if ( v19 >= 0 )
          {
            RtlEnterCriticalSection(a1 + 2);
            v6 = KerbAddCredmanCredToLogonSession((struct _KERB_LOGON_SESSION *)a1, 0, &v25, 1u, &v22);
            RtlLeaveCriticalSection(a1 + 2);
            if ( v6 < 0 )
              KerbTracerT::Log(1, "KerbTicklePackage", 3492, "Failed to add credman cred %x\n", v6);
            v2 = v22;
          }
          else
          {
            LODWORD(v21) = v19;
            KerbTracerT::Log(1, "KerbTicklePackage", 3474, "Failed to convert cert cred %x\n", v21);
          }
        }
        else
        {
          KerbTracerT::Log(1, "KerbTicklePackage", 3458, "Unable to impersonate the client token handle.\n");
          v6 = -1073741555;
        }
      }
      else
      {
        LODWORD(v21) = v18;
        KerbTracerT::Log(1, "KerbTicklePackage", 3452, "Unable to get the client token handle %#x\n", v21);
      }
    }
    else
    {
      LODWORD(v21) = v6;
      KerbTracerT::Log(1, "KerbTicklePackage", 3441, "NtOpenThreadToken failed %x\n", v21);
    }
  }
  else
  {
    v6 = -1073741801;
  }
  if ( !TokenHandle )
    goto LABEL_3;
  if ( !SetThreadToken(0, TokenHandle) )
  {
    KerbTracerT::Log(1, "KerbTicklePackage", 3502, "Unable to impersonate the client token handle.\n");
    v6 = -1073741555;
  }
  CloseHandle(TokenHandle);
LABEL_4:
  if ( hObject )
    CloseHandle(hObject);
  if ( p_TokenHandle && *((_DWORD *)p_TokenHandle - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v2 )
    KerbDereferenceCredmanCred(v2, (struct _KERBEROS_LIST *)&a1->LockCount);
  if ( v25 )
    KerbFreePrimaryCredentials(v25, 1u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c5640  push    rbp
0x1800c5642  push    rbx
0x1800c5643  push    rsi
0x1800c5644  push    rdi
0x1800c5645  push    r13
0x1800c5647  push    r14
0x1800c5649  push    r15
0x1800c564b  sub     rsp, 70h
0x1800c564f  lea     rbp, [rsp+30h]
0x1800c5654  mov     rax, cs:__security_cookie
0x1800c565b  xor     rax, rbp
0x1800c565e  mov     [rbp+70h+var_38], rax
0x1800c5662  xor     r14d, r14d
0x1800c5665  mov     [rbp+70h+var_58], 0
0x1800c566d  xorps   xmm0, xmm0
0x1800c5670  mov     [rbp+70h+var_70], r14
0x1800c5674  mov     rsi, rdx
0x1800c5677  mov     [rbp+70h+TokenHandle], r14
0x1800c567b  mov     r15, rcx
0x1800c567e  mov     [rbp+70h+hObject], r14
0x1800c5682  lea     r13d, [r14+1]
0x1800c5686  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1800c568a  test    [rdx+2], r13b
0x1800c568e  jz      short loc_1800C5708
0x1800c5690  xor     edi, edi
0x1800c5692  mov     esi, 0C000000Dh
0x1800c5697  call    cs:__imp_RevertToSelf
0x1800c569d  mov     rcx, [rbp+70h+hObject]; hObject
0x1800c56a1  test    rcx, rcx
0x1800c56a4  jz      short loc_1800C56AC
0x1800c56a6  call    cs:__imp_CloseHandle
0x1800c56ac  test    rdi, rdi
0x1800c56af  jz      short loc_1800C56C9
0x1800c56b1  lea     rcx, [rdi-8]
0x1800c56b5  cmp     dword ptr [rcx], 70616548h
0x1800c56bb  jnz     short loc_1800C56C9
0x1800c56bd  mov     rax, cs:g_pfnFree
0x1800c56c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c56c9  test    r14, r14
0x1800c56cc  jz      short loc_1800C56DA
0x1800c56ce  lea     rdx, [r15+8]; struct _KERBEROS_LIST *
0x1800c56d2  mov     rcx, r14; struct _KERB_CREDMAN_CRED *
0x1800c56d5  call    ?KerbDereferenceCredmanCred@@YAXPEAU_KERB_CREDMAN_CRED@@PEAU_KERBEROS_LIST@@@Z; KerbDereferenceCredmanCred(_KERB_CREDMAN_CRED *,_KERBEROS_LIST *)
0x1800c56da  mov     rcx, [rbp+70h+var_58]; this
0x1800c56de  test    rcx, rcx
0x1800c56e1  jz      short loc_1800C56EB
0x1800c56e3  mov     dl, r13b; unsigned __int8
0x1800c56e6  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x1800c56eb  mov     eax, esi
0x1800c56ed  mov     rcx, [rbp+70h+var_38]
0x1800c56f1  xor     rcx, rbp; StackCookie
0x1800c56f4  call    __security_check_cookie
0x1800c56f9  lea     rsp, [rbp+40h]
0x1800c56fd  pop     r15
0x1800c56ff  pop     r14
0x1800c5701  pop     r13
0x1800c5703  pop     rdi
0x1800c5704  pop     rsi
0x1800c5705  pop     rbx
0x1800c5706  pop     rbp
0x1800c5707  retn
0x1800c5708  lea     rdx, aSession; "*Session"
0x1800c570f  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800c5713  call    cs:__imp_RtlInitUnicodeString
0x1800c5719  movzx   ebx, word ptr [rsi+2]
0x1800c571d  xor     edi, edi
0x1800c571f  add     rbx, 2
0x1800c5723  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800c572a  ja      short loc_1800C5784
0x1800c572c  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800c5733  add     rcx, 8
0x1800c5737  add     rcx, rbx
0x1800c573a  cmp     rcx, rbx
0x1800c573d  jb      short loc_1800C5784
0x1800c573f  call    VerifyStackAvailable
0x1800c5744  test    eax, eax
0x1800c5746  jz      short loc_1800C5784
0x1800c5748  lea     rax, [rbx+8]
0x1800c574c  lea     rcx, [rax+0Fh]
0x1800c5750  cmp     rcx, rax
0x1800c5753  ja      short loc_1800C575F
0x1800c5755  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c575f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c5763  mov     rax, rcx
0x1800c5766  call    _alloca_probe
0x1800c576b  sub     rsp, rcx
0x1800c576e  lea     rdi, [rsp+0A0h+var_70]
0x1800c5773  test    rdi, rdi
0x1800c5776  jz      short loc_1800C5784
0x1800c5778  mov     dword ptr [rdi], 6B637453h
0x1800c577e  add     rdi, 8
0x1800c5782  jnz     short loc_1800C57AB
0x1800c5784  lea     rcx, [rbx+8]
0x1800c5788  cmp     rcx, rbx
0x1800c578b  jb      short loc_1800C57AB
0x1800c578d  mov     rax, cs:g_pfnAllocate
0x1800c5794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5799  mov     rdi, rax
0x1800c579c  test    rax, rax
0x1800c579f  jz      short loc_1800C57AB
0x1800c57a1  mov     dword ptr [rax], 70616548h
0x1800c57a7  add     rdi, 8
0x1800c57ab  test    rdi, rdi
0x1800c57ae  jnz     short loc_1800C57BA
0x1800c57b0  mov     esi, 0C0000017h
0x1800c57b5  jmp     loc_1800C5933
0x1800c57ba  movzx   r8d, word ptr [rsi+2]
0x1800c57bf  xor     edx, edx; Val
0x1800c57c1  add     r8, 2; Size
0x1800c57c5  mov     rcx, rdi; void *
0x1800c57c8  call    memset_0
0x1800c57cd  movzx   r8d, word ptr [rsi]; Size
0x1800c57d1  mov     rcx, rdi; void *
0x1800c57d4  mov     rdx, [rsi+8]; Src
0x1800c57d8  call    memcpy_0
0x1800c57dd  lea     r9, [rbp+70h+TokenHandle]; TokenHandle
0x1800c57e1  mov     r8b, r13b; OpenAsSelf
0x1800c57e4  mov     edx, 0Ch; DesiredAccess
0x1800c57e9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c57f0  call    cs:__imp_NtOpenThreadToken
0x1800c57f6  mov     esi, eax
0x1800c57f8  mov     eax, 80000000h
0x1800c57fd  lea     ecx, [rsi+rax]
0x1800c5800  test    eax, ecx
0x1800c5802  jnz     short loc_1800C5831
0x1800c5804  cmp     esi, 0C000007Ch
0x1800c580a  jz      short loc_1800C5831
0x1800c580c  mov     dword ptr [rsp+0A0h+var_80], esi
0x1800c5810  lea     r9, aNtopenthreadto; "NtOpenThreadToken failed %x\n"
0x1800c5817  mov     r8d, 0D71h
0x1800c581d  lea     rdx, aKerbticklepack; "KerbTicklePackage"
0x1800c5824  mov     ecx, r13d
0x1800c5827  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c582c  jmp     loc_1800C5933
0x1800c5831  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800c5838  lea     rcx, [r15+40h]
0x1800c583c  lea     rdx, [rbp+70h+hObject]
0x1800c5840  mov     rax, [rax+170h]
0x1800c5847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c584c  mov     esi, eax
0x1800c584e  test    eax, eax
0x1800c5850  jns     short loc_1800C5865
0x1800c5852  mov     dword ptr [rsp+0A0h+var_80], eax
0x1800c5856  lea     r9, aUnableToGetThe_0; "Unable to get the client token handle %"...
0x1800c585d  mov     r8d, 0D7Ch
0x1800c5863  jmp     short loc_1800C581D
0x1800c5865  mov     rdx, [rbp+70h+hObject]; Token
0x1800c5869  xor     ecx, ecx; Thread
0x1800c586b  call    cs:__imp_SetThreadToken
0x1800c5871  test    eax, eax
0x1800c5873  jnz     short loc_1800C589B
0x1800c5875  lea     r9, aUnableToImpers_3; "Unable to impersonate the client token "...
0x1800c587c  mov     r8d, 0D82h
0x1800c5882  lea     rdx, aKerbticklepack; "KerbTicklePackage"
0x1800c5889  mov     ecx, r13d
0x1800c588c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c5891  mov     esi, 0C000010Dh
0x1800c5896  jmp     loc_1800C5933
0x1800c589b  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800c589e  lea     rax, [rbp+70h+var_58]
0x1800c58a2  mov     [rsp+0A0h+var_78], rax; struct _KERB_PRIMARY_CREDENTIAL **
0x1800c58a7  mov     rdx, rdi; unsigned __int16 *
0x1800c58aa  lea     rax, [rbp+70h+DestinationString]
0x1800c58ae  mov     rcx, r15; struct _KERB_LOGON_SESSION *
0x1800c58b1  mov     [rsp+0A0h+var_80], rax; struct _UNICODE_STRING *
0x1800c58b6  lea     r8d, [r9+10h]; unsigned int
0x1800c58ba  call    ?KerbConvertCertCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEBGKPEAU_UNICODE_STRING@@2PEAPEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbConvertCertCredential(_KERB_LOGON_SESSION *,ushort const *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PRIMARY_CREDENTIAL * *)
0x1800c58bf  mov     esi, eax
0x1800c58c1  test    eax, eax
0x1800c58c3  jns     short loc_1800C58DB
0x1800c58c5  mov     dword ptr [rsp+0A0h+var_80], eax
0x1800c58c9  lea     r9, aFailedToConver_11; "Failed to convert cert cred %x\n"
0x1800c58d0  mov     r8d, 0D92h
0x1800c58d6  jmp     loc_1800C581D
0x1800c58db  lea     rcx, [r15+50h]; CriticalSection
0x1800c58df  call    cs:__imp_RtlEnterCriticalSection
0x1800c58e5  lea     rax, [rbp+70h+var_70]
0x1800c58e9  mov     r9d, r13d; unsigned int
0x1800c58ec  lea     r8, [rbp+70h+var_58]; struct _KERB_PRIMARY_CREDENTIAL **
0x1800c58f0  mov     [rsp+0A0h+var_80], rax; struct _KERB_CREDMAN_CRED **
0x1800c58f5  xor     edx, edx; struct _KERB_CREDENTIAL *
0x1800c58f7  mov     rcx, r15; struct _KERB_LOGON_SESSION *
0x1800c58fa  call    ?KerbAddCredmanCredToLogonSession@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAPEAU_KERB_PRIMARY_CREDENTIAL@@KPEAPEAU_KERB_CREDMAN_CRED@@@Z; KerbAddCredmanCredToLogonSession(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_PRIMARY_CREDENTIAL * *,ulong,_KERB_CREDMAN_CRED * *)
0x1800c58ff  lea     rcx, [r15+50h]; CriticalSection
0x1800c5903  mov     esi, eax
0x1800c5905  call    cs:__imp_RtlLeaveCriticalSection
0x1800c590b  test    esi, esi
0x1800c590d  jns     short loc_1800C592F
0x1800c590f  lea     r9, aFailedToAddCre; "Failed to add credman cred %x\n"
0x1800c5916  mov     dword ptr [rsp+0A0h+var_80], esi
0x1800c591a  mov     r8d, 0DA4h
0x1800c5920  lea     rdx, aKerbticklepack; "KerbTicklePackage"
0x1800c5927  mov     ecx, r13d
0x1800c592a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c592f  mov     r14, [rbp+70h+var_70]
0x1800c5933  mov     rdx, [rbp+70h+TokenHandle]; Token
0x1800c5937  test    rdx, rdx
0x1800c593a  jz      loc_1800C5697
0x1800c5940  xor     ecx, ecx; Thread
0x1800c5942  call    cs:__imp_SetThreadToken
0x1800c5948  test    eax, eax
0x1800c594a  jnz     short loc_1800C596D
0x1800c594c  lea     r9, aUnableToImpers_3; "Unable to impersonate the client token "...
0x1800c5953  mov     r8d, 0DAEh
0x1800c5959  lea     rdx, aKerbticklepack; "KerbTicklePackage"
0x1800c5960  mov     ecx, r13d
0x1800c5963  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c5968  mov     esi, 0C000010Dh
0x1800c596d  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x1800c5971  call    cs:__imp_CloseHandle
0x1800c5977  jmp     loc_1800C569D
```
