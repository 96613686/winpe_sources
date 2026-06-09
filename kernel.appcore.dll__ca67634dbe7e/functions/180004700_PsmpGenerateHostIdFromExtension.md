# PsmpGenerateHostIdFromExtension

- ea: `0x180004700`
- end: `0x1800049b5`
- name: `PsmpGenerateHostIdFromExtension`
- size: `693`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800038d0`

## callees

- `0x180004700`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18000493c`
- `ntdll!NtOpenThreadToken` at `0x18000493c`
- `ntdll!NtSetInformationThread` at `0x180004987`
- `ntdll!NtSetInformationThread` at `0x180004987`
- `ntdll!NtClose` at `0x1800048ee`
- `ntdll!NtClose` at `0x1800048ee`
- `ntdll!NtQueryInformationToken` at `0x18000479e`
- `ntdll!NtQueryInformationToken` at `0x1800047d7`
- `ntdll!NtQueryInformationToken` at `0x18000479e`
- `ntdll!NtQueryInformationToken` at `0x1800047d7`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180004811`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180004811`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x180004965`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x180004965`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004871`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180004871`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180004881`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180004881`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x180004863`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x180004863`

## pseudocode

```c
__int64 __fastcall PsmpGenerateHostIdFromExtension(
        HANDLE TokenHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        _QWORD *a7)
{
  NTSTATUS InformationToken; // ebx
  unsigned int v12; // edi
  __int64 v13; // rsi
  int v14; // eax
  ULONG TokenInformation[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v19[1056]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v20[12]; // [rsp+478h] [rbp+370h] BYREF
  _BYTE v21[464]; // [rsp+4D8h] [rbp+3D0h] BYREF

  v18 = 0;
  TokenInformation[1] = 0;
  TokenInformation[0] = 0;
  memset_0(v19, 0, 0x418u);
  Handle = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    InformationToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &Handle);
    if ( InformationToken < 0 )
      goto LABEL_16;
  }
  InformationToken = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation[1], 4u, TokenInformation);
  if ( InformationToken < 0 )
    goto LABEL_16;
  v12 = 1;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, v20, 0x54u, TokenInformation);
  if ( InformationToken < 0 )
    goto LABEL_16;
  v13 = v20[0];
  TokenInformation[0] = 464;
  v14 = a4 ? PsmCreateKeyWithDynamicId(a2, a3, a4, v21, TokenInformation) : PsmCreateKey(a2, a3, v21, TokenInformation);
  InformationToken = v14;
  if ( v14 < 0 )
    goto LABEL_16;
  if ( (a6 & 0x10000000) != 0 )
  {
    if ( a5 != 1 )
    {
      InformationToken = -1073741776;
      goto LABEL_16;
    }
    v12 = 3;
  }
  else if ( a5 != 2 )
  {
    if ( a5 > 1 )
    {
      if ( a5 != 3 )
      {
        InformationToken = -1073741581;
        goto LABEL_16;
      }
      v12 = 2;
    }
    else
    {
      v12 = 0;
    }
  }
  HamHostIdInitializeKey(v21, v13, TokenInformation[1], v12, 0, v19, *(_QWORD *)TokenInformation);
  if ( Handle )
    RevertToSelf();
  InformationToken = HamHostIdFindOrCreate(v19, &v18);
  if ( Handle )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
  if ( InformationToken >= 0 )
  {
    InformationToken = 0;
    *a7 = v18;
  }
LABEL_16:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x180004700  mov     r11, rsp
0x180004703  push    rbp
0x180004704  push    rbx
0x180004705  lea     rbp, [r11-5F8h]
0x18000470c  sub     rsp, 6E8h
0x180004713  mov     rax, cs:__security_cookie
0x18000471a  xor     rax, rsp
0x18000471d  mov     [rbp+5F0h+var_50], rax
0x180004724  mov     [r11-18h], rsi
0x180004728  xor     ebx, ebx
0x18000472a  mov     [r11-28h], r12
0x18000472e  mov     rsi, rcx
0x180004731  mov     [r11-30h], r13
0x180004735  lea     rcx, [rsp+6F0h+var_6A0]; void *
0x18000473a  mov     r13, [rbp+5F0h+arg_30]
0x180004741  mov     r12, r8
0x180004744  mov     [r11-38h], r14
0x180004748  mov     r8d, 418h; Size
0x18000474e  mov     [r11-40h], r15
0x180004752  mov     r14, r9
0x180004755  mov     r15, rdx
0x180004758  mov     [rsp+6F0h+var_6B0], rbx
0x18000475d  xor     edx, edx; Val
0x18000475f  mov     [rsp+6F0h+TokenInformation+4], ebx
0x180004763  mov     [rsp+6F0h+TokenInformation], ebx
0x180004767  call    memset_0
0x18000476c  mov     [rsp+6F0h+Handle], rbx
0x180004771  mov     eax, gs:179Ch
0x180004779  test    eax, eax
0x18000477b  jnz     loc_180004928
0x180004781  lea     rax, [rsp+6F0h+TokenInformation]
0x180004786  mov     r9d, 4; TokenInformationLength
0x18000478c  lea     r8, [rsp+6F0h+TokenInformation+4]; TokenInformation
0x180004791  mov     [rsp+6F0h+ReturnLength], rax; ReturnLength
0x180004796  mov     edx, 0Ch; TokenInformationClass
0x18000479b  mov     rcx, rsi; TokenHandle
0x18000479e  call    cs:__imp_NtQueryInformationToken
0x1800047a4  mov     ebx, eax
0x1800047a6  test    eax, eax
0x1800047a8  js      loc_1800048A1
0x1800047ae  lea     rax, [rsp+6F0h+TokenInformation]
0x1800047b3  mov     [rsp+6F0h+var_18], rdi
0x1800047bb  mov     edi, 1
0x1800047c0  mov     [rsp+6F0h+ReturnLength], rax; ReturnLength
0x1800047c5  mov     edx, edi; TokenInformationClass
0x1800047c7  lea     r8, [rbp+5F0h+var_280]; TokenInformation
0x1800047ce  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800047d4  mov     rcx, rsi; TokenHandle
0x1800047d7  call    cs:__imp_NtQueryInformationToken
0x1800047dd  mov     ebx, eax
0x1800047df  test    eax, eax
0x1800047e1  js      loc_180004899
0x1800047e7  mov     rsi, [rbp+5F0h+var_280]
0x1800047ee  mov     rdx, r12
0x1800047f1  mov     [rsp+6F0h+TokenInformation], 1D0h
0x1800047f9  mov     rcx, r15
0x1800047fc  test    r14, r14
0x1800047ff  jnz     loc_180004951
0x180004805  lea     r9, [rsp+6F0h+TokenInformation]
0x18000480a  lea     r8, [rbp+5F0h+var_220]
0x180004811  call    cs:__imp_PsmCreateKey
0x180004817  mov     ebx, eax
0x180004819  test    eax, eax
0x18000481b  js      short loc_180004899
0x18000481d  test    [rbp+5F0h+arg_28], 10000000h
0x180004827  jz      loc_1800048F6
0x18000482d  cmp     [rbp+5F0h+arg_20], edi
0x180004833  jnz     loc_180004992
0x180004839  mov     edi, 3
0x18000483e  mov     r8d, [rsp+6F0h+TokenInformation+4]
0x180004843  lea     rax, [rsp+6F0h+var_6A0]
0x180004848  mov     qword ptr [rsp+6F0h+var_6C8], rax
0x18000484d  lea     rcx, [rbp+5F0h+var_220]
0x180004854  mov     r9d, edi
0x180004857  mov     [rsp+6F0h+ReturnLength], 0
0x180004860  mov     rdx, rsi
0x180004863  call    cs:__imp_HamHostIdInitializeKey
0x180004869  cmp     [rsp+6F0h+Handle], 0
0x18000486f  jz      short loc_180004877
0x180004871  call    cs:__imp_RevertToSelf
0x180004877  lea     rdx, [rsp+6F0h+var_6B0]
0x18000487c  lea     rcx, [rsp+6F0h+var_6A0]
0x180004881  call    cs:__imp_HamHostIdFindOrCreate
0x180004887  cmp     [rsp+6F0h+Handle], 0
0x18000488d  mov     ebx, eax
0x18000488f  jnz     loc_180004970
0x180004895  test    ebx, ebx
0x180004897  jns     short loc_180004918
0x180004899  mov     rdi, [rsp+6F0h+var_18]
0x1800048a1  mov     rcx, [rsp+6F0h+Handle]; Handle
0x1800048a6  mov     r15, [rsp+6F0h+var_38]
0x1800048ae  mov     r14, [rsp+6F0h+var_30]
0x1800048b6  mov     r13, [rsp+6F0h+var_28]
0x1800048be  mov     r12, [rsp+6F0h+var_20]
0x1800048c6  mov     rsi, [rsp+6E0h]
0x1800048ce  test    rcx, rcx
0x1800048d1  jnz     short loc_1800048EE
0x1800048d3  mov     eax, ebx
0x1800048d5  mov     rcx, [rbp+5F0h+var_50]
0x1800048dc  xor     rcx, rsp; StackCookie
0x1800048df  call    __security_check_cookie
0x1800048e4  add     rsp, 6E8h
0x1800048eb  pop     rbx
0x1800048ec  pop     rbp
0x1800048ed  retn
0x1800048ee  call    cs:__imp_NtClose
0x1800048f4  jmp     short loc_1800048D3
0x1800048f6  mov     ecx, [rbp+5F0h+arg_20]
0x1800048fc  cmp     ecx, 2
0x1800048ff  jz      loc_18000483E
0x180004905  test    ecx, ecx
0x180004907  jz      short loc_180004911
0x180004909  sub     ecx, edi
0x18000490b  jnz     loc_18000499C
0x180004911  xor     edi, edi
0x180004913  jmp     loc_18000483E
0x180004918  mov     rax, [rsp+6F0h+var_6B0]
0x18000491d  xor     ebx, ebx
0x18000491f  mov     [r13+0], rax
0x180004923  jmp     loc_180004899
0x180004928  lea     r9, [rsp+6F0h+Handle]; TokenHandle
0x18000492d  mov     r8b, 1; OpenAsSelf
0x180004930  mov     edx, 0Ch; DesiredAccess
0x180004935  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000493c  call    cs:__imp_NtOpenThreadToken
0x180004942  mov     ebx, eax
0x180004944  test    eax, eax
0x180004946  jns     loc_180004781
0x18000494c  jmp     loc_1800048A1
0x180004951  lea     rax, [rsp+6F0h+TokenInformation]
0x180004956  mov     r8, r14
0x180004959  lea     r9, [rbp+5F0h+var_220]
0x180004960  mov     [rsp+6F0h+ReturnLength], rax
0x180004965  call    cs:__imp_PsmCreateKeyWithDynamicId
0x18000496b  jmp     loc_180004817
0x180004970  mov     r9d, 8; ThreadInformationLength
0x180004976  lea     r8, [rsp+6F0h+Handle]; ThreadInformation
0x18000497b  mov     edx, 5; ThreadInformationClass
0x180004980  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180004987  call    cs:__imp_NtSetInformationThread
0x18000498d  jmp     loc_180004895
0x180004992  mov     ebx, 0C0000030h
0x180004997  jmp     loc_180004899
0x18000499c  cmp     ecx, 2
0x18000499f  jz      short loc_1800049AB
0x1800049a1  mov     ebx, 0C00000F3h
0x1800049a6  jmp     loc_180004899
0x1800049ab  mov     edi, 2
0x1800049b0  jmp     loc_18000483E
```
