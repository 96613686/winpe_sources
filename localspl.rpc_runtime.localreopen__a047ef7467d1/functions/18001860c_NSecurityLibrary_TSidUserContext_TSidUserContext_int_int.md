# NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)

- ea: `0x18001860c`
- end: `0x1800187a2`
- name: `??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z`
- size: `406`
- prototype: `_QWORD(NSecurityLibrary::TSidUserContext *__hidden this, int, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800132a4`
- `0x180018504`
- `0x18003fe8c`
- `0x18004f67c`
- `0x1800528f0`
- `0x1800bb038`

## callees

- `0x1800159d8`
- `0x180015e28`
- `0x18001860c`
- `0x180046bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018754`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001866b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001866b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018761`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018761`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001876f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001876f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800186d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018731`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800186d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018731`

## pseudocode

```c
NSecurityLibrary::TSidUserContext *__fastcall NSecurityLibrary::TSidUserContext::TSidUserContext(
        NSecurityLibrary::TSidUserContext *this,
        int a2,
        BOOL a3)
{
  void **v3; // r14
  signed int LastErrorAsFailHRNoBreak; // edi
  HANDLE CurrentThread; // rax
  BOOL v8; // eax
  int v9; // ecx
  int LastErrorAsHResult; // eax
  void *v11; // rbx
  signed int LastError; // eax
  void *v13; // rax
  NCoreLibrary *v14; // rcx
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = &NSecurityLibrary::TUserContext::`vftable';
  v3 = (void **)((char *)this + 16);
  *((_DWORD *)this + 2) = 1685222261;
  *((_QWORD *)this + 2) = 0;
  LastErrorAsFailHRNoBreak = -2147467259;
  *((_DWORD *)this + 7) = a2 != 0 ? 4 : 0;
  *((_DWORD *)this + 6) = -2147467259;
  *((_QWORD *)this + 4) = 0;
  CurrentThread = GetCurrentThread();
  v8 = OpenThreadToken(CurrentThread, 8u, a3, v3);
  v9 = *((_DWORD *)this + 7);
  if ( v8 )
  {
    *((_DWORD *)this + 7) = v9 & 0xFFFFFFFB;
LABEL_3:
    LastErrorAsHResult = 0;
    goto LABEL_4;
  }
  if ( (v9 & 4) != 0 && GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, v3) )
      goto LABEL_3;
  }
  LastErrorAsHResult = GetLastErrorAsHResult();
LABEL_4:
  *((_DWORD *)this + 6) = LastErrorAsHResult;
  *(_QWORD *)this = &NSecurityLibrary::TSidUserContext::`vftable';
  *((_DWORD *)this + 10) = 1684302195;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = LastErrorAsHResult;
  if ( LastErrorAsHResult >= 0 )
  {
    v11 = *v3;
    ReturnLength = 0;
    TokenInformationLength = 0;
    if ( !GetTokenInformation(v11, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      LastErrorAsFailHRNoBreak = LastError;
      if ( LastError == 122 )
      {
        v13 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&NCoreLibrary::nothrow);
        *((_QWORD *)this + 6) = v13;
        LastErrorAsFailHRNoBreak = v13 == 0 ? 0x8007000E : 0;
      }
      else if ( LastError > 0 )
      {
        LastErrorAsFailHRNoBreak = (unsigned __int16)LastError | 0x80070000;
      }
      if ( LastErrorAsFailHRNoBreak >= 0
        && !GetTokenInformation(v11, TokenUser, *((LPVOID *)this + 6), TokenInformationLength, &ReturnLength) )
      {
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v14);
      }
    }
    *((_DWORD *)this + 14) = LastErrorAsFailHRNoBreak;
  }
  return this;
}

```

## disassembly

```asm
0x18001860c  mov     [rsp+arg_10], rbx
0x180018611  push    rsi
0x180018612  push    rdi
0x180018613  push    r14
0x180018615  sub     rsp, 30h
0x180018619  lea     rax, ??_7TUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TUserContext::`vftable'
0x180018620  neg     edx
0x180018622  mov     [rcx], rax
0x180018625  lea     r14, [rcx+10h]
0x180018629  mov     dword ptr [rcx+8], 64727375h
0x180018630  sbb     eax, eax
0x180018632  and     eax, 4
0x180018635  mov     qword ptr [r14], 0
0x18001863c  mov     edi, 80004005h
0x180018641  mov     [rcx+1Ch], eax
0x180018644  mov     ebx, r8d
0x180018647  mov     [rcx+18h], edi
0x18001864a  mov     rsi, rcx
0x18001864d  mov     qword ptr [rcx+20h], 0
0x180018655  call    cs:__imp_GetCurrentThread
0x18001865b  mov     r8d, ebx; OpenAsSelf
0x18001865e  mov     r9, r14; TokenHandle
0x180018661  mov     ebx, 8
0x180018666  mov     rcx, rax; ThreadHandle
0x180018669  mov     edx, ebx; DesiredAccess
0x18001866b  call    cs:__imp_OpenThreadToken
0x180018671  mov     ecx, [rsi+1Ch]
0x180018674  test    eax, eax
0x180018676  jz      loc_18001874F
0x18001867c  and     ecx, 0FFFFFFFBh
0x18001867f  mov     [rsi+1Ch], ecx
0x180018682  xor     eax, eax
0x180018684  mov     [rsi+18h], eax
0x180018687  lea     rcx, ??_7TSidUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TSidUserContext::`vftable'
0x18001868e  mov     [rsi], rcx
0x180018691  mov     dword ptr [rsi+28h], 64646973h
0x180018698  mov     qword ptr [rsi+30h], 0
0x1800186a0  mov     [rsi+38h], eax
0x1800186a3  test    eax, eax
0x1800186a5  js      loc_18001873E
0x1800186ab  mov     rbx, [r14]
0x1800186ae  lea     rax, [rsp+48h+TokenInformationLength]
0x1800186b3  xor     r9d, r9d; TokenInformationLength
0x1800186b6  mov     [rsp+48h+arg_0], 0
0x1800186be  xor     r8d, r8d; TokenInformation
0x1800186c1  mov     [rsp+48h+TokenInformationLength], 0
0x1800186c9  mov     rcx, rbx; TokenHandle
0x1800186cc  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800186d1  lea     r14d, [r9+1]
0x1800186d5  mov     edx, r14d; TokenInformationClass
0x1800186d8  call    cs:__imp_GetTokenInformation
0x1800186de  test    eax, eax
0x1800186e0  jnz     short loc_18001873B
0x1800186e2  call    cs:__imp_GetLastError
0x1800186e8  mov     edi, eax
0x1800186ea  cmp     eax, 7Ah ; 'z'
0x1800186ed  jnz     loc_180018787
0x1800186f3  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1800186f7  lea     rdx, ?nothrow@NCoreLibrary@@3Unothrow_t@std@@B; struct std::nothrow_t *
0x1800186fe  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018703  mov     [rsi+30h], rax
0x180018707  neg     rax
0x18001870a  sbb     edi, edi
0x18001870c  not     edi
0x18001870e  and     edi, 8007000Eh
0x180018714  test    edi, edi
0x180018716  js      short loc_18001873B
0x180018718  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001871d  lea     rax, [rsp+48h+arg_0]
0x180018722  mov     r8, [rsi+30h]; TokenInformation
0x180018726  mov     edx, r14d; TokenInformationClass
0x180018729  mov     rcx, rbx; TokenHandle
0x18001872c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180018731  call    cs:__imp_GetTokenInformation
0x180018737  test    eax, eax
0x180018739  jz      short loc_180018799
0x18001873b  mov     [rsi+38h], edi
0x18001873e  mov     rbx, [rsp+48h+arg_10]
0x180018743  mov     rax, rsi
0x180018746  add     rsp, 30h
0x18001874a  pop     r14
0x18001874c  pop     rdi
0x18001874d  pop     rsi
0x18001874e  retn
0x18001874f  test    cl, 4
0x180018752  jz      short loc_18001877D
0x180018754  call    cs:__imp_GetLastError
0x18001875a  cmp     eax, 3F0h
0x18001875f  jnz     short loc_18001877D
0x180018761  call    cs:__imp_GetCurrentProcess
0x180018767  mov     r8, r14; TokenHandle
0x18001876a  mov     edx, ebx; DesiredAccess
0x18001876c  mov     rcx, rax; ProcessHandle
0x18001876f  call    cs:__imp_OpenProcessToken
0x180018775  test    eax, eax
0x180018777  jnz     loc_180018682
0x18001877d  call    GetLastErrorAsHResult
0x180018782  jmp     loc_180018684
0x180018787  test    eax, eax
0x180018789  jle     short loc_180018714
0x18001878b  movzx   edi, ax
0x18001878e  or      edi, 80070000h
0x180018794  jmp     loc_180018714
0x180018799  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x18001879e  mov     edi, eax
0x1800187a0  jmp     short loc_18001873B
```
