# basessp::_DecodePin(void * (*)(unsigned __int64),void (*)(void *),ushort *,void *,_UNICODE_STRING *)

- ea: `0x18001e5f0`
- end: `0x18001e8b8`
- name: `?_DecodePin@basessp@@YAJP6APEAX_K@ZP6AXPEAX@ZPEAG2PEAU_UNICODE_STRING@@@Z`
- size: `712`
- prototype: `int(basessp *__hidden this, void *(*)(unsigned __int64), void (*)(void *), unsigned __int16 *, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e2b4`

## callees

- `0x18000ef54`
- `0x18000f09c`
- `0x18001e5f0`
- `0x18001ece2`
- `0x18001ecee`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001e694`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001e694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6d0`
- `ntdll!RtlInitUnicodeString` at `0x18001e759`
- `ntdll!RtlInitUnicodeString` at `0x18001e759`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e872`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e872`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18001e6c6`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18001e726`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18001e6c6`
- `api-ms-win-security-credentials-l1-1-0!CredUnprotectW` at `0x18001e726`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18001e65b`
- `api-ms-win-security-credentials-l1-1-0!CredIsProtectedW` at `0x18001e65b`

## pseudocode

```c
__int64 __fastcall basessp::_DecodePin(
        basessp *this,
        void (__fastcall *a2)(void (*)(void *)),
        void (*a3)(void *),
        unsigned __int16 *a4,
        USHORT *a5)
{
  unsigned int v10; // ebx
  __int64 v11; // rbx
  char v12; // r12
  void (*v13)(void *); // rdi
  DWORD v14; // r15d
  DWORD v15; // ebx
  const char *v16; // rcx
  USHORT Length; // ax
  unsigned __int16 v18; // ax
  const char *v19; // r8
  _WORD *v20; // rax
  const char *v21; // rcx
  _WORD *v22; // r15
  const char *v23; // r8
  size_t v24; // rbx
  const char *v25; // r8
  __int64 v26; // rcx
  void (*v27)(void *); // rax
  DWORD pcchMaxChars; // [rsp+30h] [rbp-28h] BYREF
  CRED_PROTECTION_TYPE pProtectionType; // [rsp+34h] [rbp-24h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-20h] BYREF
  DWORD v32; // [rsp+C0h] [rbp+68h]

  pcchMaxChars = 0;
  pProtectionType = CredUnprotected;
  DestinationString = 0;
  if ( !a5 )
    return 3221225485LL;
  *(_OWORD *)a5 = 0;
  if ( a3 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)a3 + v11) );
    if ( !CredIsProtectedW((LPWSTR)a3, &pProtectionType) )
      return (unsigned int)-1073741811;
    v12 = 0;
    v32 = 0;
    switch ( pProtectionType )
    {
      case CredUnprotected:
        goto LABEL_12;
      case CredUserProtection:
        if ( !SetThreadToken(0, a4) )
          return (unsigned int)-1073741555;
        v12 = 1;
        break;
      case CredTrustedProtection:
        break;
      default:
LABEL_12:
        v13 = a3;
        goto LABEL_25;
    }
    v13 = 0;
    v14 = v11 + 1;
    if ( CredUnprotectW(0, (LPWSTR)a3, v11 + 1, 0, &pcchMaxChars) )
      goto LABEL_25;
    if ( GetLastError() == 122 && pcchMaxChars )
    {
      v32 = 2 * pcchMaxChars;
      v15 = 2 * pcchMaxChars;
      v13 = (void (*)(void *))((__int64 (__fastcall *)(_QWORD))this)(2 * pcchMaxChars);
      memset_0(v13, 0, v15);
      if ( !v13 )
      {
        v10 = -1073741670;
LABEL_36:
        if ( v12 )
          RevertToSelf();
        if ( v13 && v13 != a3 )
        {
          v26 = v32;
          v27 = v13;
          if ( v32 )
          {
            do
            {
              *(_BYTE *)v27 = 0;
              v27 = (void (*)(void *))((char *)v27 + 1);
              --v26;
            }
            while ( v26 );
          }
          a2(v13);
        }
        return v10;
      }
      if ( CredUnprotectW(0, (LPWSTR)a3, v14, (LPWSTR)v13, &pcchMaxChars)
        && (!pcchMaxChars || !*((_WORD *)v13 + pcchMaxChars - 1)) )
      {
LABEL_25:
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v13);
        *(_OWORD *)a5 = 0;
        if ( DestinationString.Buffer && DestinationString.MaximumLength )
        {
          Length = DestinationString.Length;
          if ( DestinationString.Length > DestinationString.MaximumLength || (DestinationString.Length & 1) != 0 )
          {
            v10 = -1073741811;
            v25 = _DBG_BASENAME(v16);
            WPPTraceLogA("0x%08x %s:%u : %s:%ws", 3221225485LL, v25, 131, "Malformed source string", &dword_180021D0C);
          }
          else
          {
            *a5 = DestinationString.Length;
            v18 = Length + 2;
            a5[1] = v18;
            if ( v18 >= 2u )
            {
              v20 = (_WORD *)((__int64 (__fastcall *)(_QWORD))this)(v18);
              *((_QWORD *)a5 + 1) = v20;
              v22 = v20;
              if ( v20 )
              {
                v24 = *a5;
                memcpy_0(v20, DestinationString.Buffer, v24);
                v22[v24 >> 1] = 0;
                v10 = 0;
              }
              else
              {
                v10 = -1073741801;
                v23 = _DBG_BASENAME(v21);
                WPPTraceLogA("0x%08x %s:%u : %s:%ws", 3221225495LL, v23, 145, "AllocateLsaHeap", &dword_180021D0C);
              }
            }
            else
            {
              v10 = -2147483643;
              v19 = _DBG_BASENAME(v16);
              WPPTraceLogA("0x%08x %s:%u : %s:%ws", 2147483653LL, v19, 139, "Buffer Overflow", &dword_180021D0C);
            }
          }
        }
        else
        {
          v10 = 0;
        }
        goto LABEL_36;
      }
    }
    v10 = -1073741811;
    goto LABEL_36;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e5f0  mov     [rsp-40h+arg_8], rdx
0x18001e5f5  push    rbp
0x18001e5f6  push    rbx
0x18001e5f7  push    rsi
0x18001e5f8  push    rdi
0x18001e5f9  push    r12
0x18001e5fb  push    r13
0x18001e5fd  push    r14
0x18001e5ff  push    r15
0x18001e601  mov     rbp, rsp
0x18001e604  sub     rsp, 58h
0x18001e608  mov     rsi, [rbp+arg_20]
0x18001e60c  xor     r15d, r15d
0x18001e60f  mov     [rbp+var_28], r15d
0x18001e613  xorps   xmm0, xmm0
0x18001e616  mov     [rbp+pProtectionType], r15d
0x18001e61a  mov     rdi, r9
0x18001e61d  mov     r14, r8
0x18001e620  mov     r13, rcx
0x18001e623  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001e627  test    rsi, rsi
0x18001e62a  jnz     short loc_18001E636
0x18001e62c  mov     eax, 0C000000Dh
0x18001e631  jmp     loc_18001E8A7
0x18001e636  movups  xmmword ptr [rsi], xmm0
0x18001e639  test    r14, r14
0x18001e63c  jnz     short loc_18001E646
0x18001e63e  mov     ebx, r15d
0x18001e641  jmp     loc_18001E8A5
0x18001e646  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e64a  inc     rbx
0x18001e64d  cmp     [r8+rbx*2], r15w
0x18001e652  jnz     short loc_18001E64A
0x18001e654  lea     rdx, [rbp+pProtectionType]; pProtectionType
0x18001e658  mov     rcx, r14; pszProtectedCredentials
0x18001e65b  call    cs:__imp_CredIsProtectedW
0x18001e661  test    eax, eax
0x18001e663  jnz     short loc_18001E66F
0x18001e665  mov     ebx, 0C000000Dh
0x18001e66a  jmp     loc_18001E8A5
0x18001e66f  mov     ecx, [rbp+pProtectionType]
0x18001e672  mov     r12b, r15b
0x18001e675  mov     dword ptr [rbp+arg_20], r15d
0x18001e679  test    ecx, ecx
0x18001e67b  jz      short loc_18001E687
0x18001e67d  sub     ecx, 1
0x18001e680  jz      short loc_18001E68F
0x18001e682  cmp     ecx, 1
0x18001e685  jz      short loc_18001E6AB
0x18001e687  mov     rdi, r14
0x18001e68a  jmp     loc_18001E752
0x18001e68f  mov     rdx, rdi; Token
0x18001e692  xor     ecx, ecx; Thread
0x18001e694  call    cs:__imp_SetThreadToken
0x18001e69a  test    eax, eax
0x18001e69c  jnz     short loc_18001E6A8
0x18001e69e  mov     ebx, 0C000010Dh
0x18001e6a3  jmp     loc_18001E8A5
0x18001e6a8  mov     r12b, 1
0x18001e6ab  lea     rax, [rbp+var_28]
0x18001e6af  mov     rdi, r15
0x18001e6b2  lea     r15d, [rbx+1]
0x18001e6b6  mov     [rsp+58h+pcchMaxChars], rax; pcchMaxChars
0x18001e6bb  mov     r8d, r15d; cchProtectedCredentials
0x18001e6be  xor     r9d, r9d; pszCredentials
0x18001e6c1  mov     rdx, r14; pszProtectedCredentials
0x18001e6c4  xor     ecx, ecx; fAsSelf
0x18001e6c6  call    cs:__imp_CredUnprotectW
0x18001e6cc  test    eax, eax
0x18001e6ce  jnz     short loc_18001E74F
0x18001e6d0  call    cs:__imp_GetLastError
0x18001e6d6  cmp     eax, 7Ah ; 'z'
0x18001e6d9  jnz     short loc_18001E733
0x18001e6db  mov     eax, [rbp+var_28]
0x18001e6de  test    eax, eax
0x18001e6e0  jz      short loc_18001E733
0x18001e6e2  add     eax, eax
0x18001e6e4  mov     dword ptr [rbp+arg_20], eax
0x18001e6e7  mov     ebx, eax
0x18001e6e9  mov     ecx, eax
0x18001e6eb  mov     rax, r13
0x18001e6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f3  mov     r8d, ebx; Size
0x18001e6f6  xor     edx, edx; Val
0x18001e6f8  mov     rcx, rax; void *
0x18001e6fb  mov     rdi, rax
0x18001e6fe  call    memset_0
0x18001e703  test    rdi, rdi
0x18001e706  jnz     short loc_18001E712
0x18001e708  mov     ebx, 0C000009Ah
0x18001e70d  jmp     loc_18001E86B
0x18001e712  lea     rax, [rbp+var_28]
0x18001e716  mov     r9, rdi; pszCredentials
0x18001e719  mov     r8d, r15d; cchProtectedCredentials
0x18001e71c  mov     [rsp+58h+pcchMaxChars], rax; pcchMaxChars
0x18001e721  mov     rdx, r14; pszProtectedCredentials
0x18001e724  xor     ecx, ecx; fAsSelf
0x18001e726  call    cs:__imp_CredUnprotectW
0x18001e72c  xor     r15d, r15d
0x18001e72f  test    eax, eax
0x18001e731  jnz     short loc_18001E73D
0x18001e733  mov     ebx, 0C000000Dh
0x18001e738  jmp     loc_18001E86B
0x18001e73d  mov     eax, [rbp+var_28]
0x18001e740  test    eax, eax
0x18001e742  jz      short loc_18001E752
0x18001e744  dec     eax
0x18001e746  cmp     [rdi+rax*2], r15w
0x18001e74b  jz      short loc_18001E752
0x18001e74d  jmp     short loc_18001E733
0x18001e74f  xor     r15d, r15d
0x18001e752  mov     rdx, rdi; SourceString
0x18001e755  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001e759  call    cs:__imp_RtlInitUnicodeString
0x18001e75f  xorps   xmm0, xmm0
0x18001e762  movups  xmmword ptr [rsi], xmm0
0x18001e765  cmp     [rbp+DestinationString.Buffer], r15
0x18001e769  jz      loc_18001E868
0x18001e76f  cmp     r15w, [rbp+DestinationString.MaximumLength]
0x18001e774  jz      loc_18001E868
0x18001e77a  movzx   eax, [rbp+DestinationString.Length]
0x18001e77e  cmp     ax, [rbp+DestinationString.MaximumLength]
0x18001e782  ja      loc_18001E82D
0x18001e788  test    al, 1
0x18001e78a  jnz     loc_18001E82D
0x18001e790  mov     [rsi], ax
0x18001e793  add     ax, 2
0x18001e797  mov     [rsi+2], ax
0x18001e79b  cmp     ax, 2
0x18001e79f  jnb     short loc_18001E7CC
0x18001e7a1  mov     ebx, 80000005h
0x18001e7a6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e7ab  mov     r8, rax
0x18001e7ae  mov     r9d, 8Bh
0x18001e7b4  lea     rax, dword_180021D0C
0x18001e7bb  mov     [rsp+58h+var_30], rax
0x18001e7c0  lea     rax, aBufferOverflow; "Buffer Overflow"
0x18001e7c7  jmp     loc_18001E853
0x18001e7cc  movzx   ecx, ax
0x18001e7cf  mov     rax, r13
0x18001e7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7d7  xor     r13d, r13d
0x18001e7da  mov     [rsi+8], rax
0x18001e7de  mov     r15, rax
0x18001e7e1  test    rax, rax
0x18001e7e4  jnz     short loc_18001E80E
0x18001e7e6  mov     ebx, 0C0000017h
0x18001e7eb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e7f0  mov     r8, rax
0x18001e7f3  mov     r9d, 91h
0x18001e7f9  lea     rax, dword_180021D0C
0x18001e800  mov     [rsp+58h+var_30], rax
0x18001e805  lea     rax, aAllocatelsahea; "AllocateLsaHeap"
0x18001e80c  jmp     short loc_18001E853
0x18001e80e  movzx   ebx, word ptr [rsi]
0x18001e811  mov     rcx, r15; void *
0x18001e814  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x18001e818  mov     r8d, ebx; Size
0x18001e81b  call    memcpy_0
0x18001e820  shr     rbx, 1
0x18001e823  mov     [r15+rbx*2], r13w
0x18001e828  mov     ebx, r13d
0x18001e82b  jmp     short loc_18001E86B
0x18001e82d  mov     ebx, 0C000000Dh
0x18001e832  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001e837  mov     r8, rax
0x18001e83a  mov     r9d, 83h
0x18001e840  lea     rax, dword_180021D0C
0x18001e847  mov     [rsp+58h+var_30], rax
0x18001e84c  lea     rax, aMalformedSourc; "Malformed source string"
0x18001e853  mov     edx, ebx
0x18001e855  mov     [rsp+58h+pcchMaxChars], rax
0x18001e85a  lea     rcx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001e861  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001e866  jmp     short loc_18001E86B
0x18001e868  mov     ebx, r15d
0x18001e86b  xor     esi, esi
0x18001e86d  test    r12b, r12b
0x18001e870  jz      short loc_18001E878
0x18001e872  call    cs:__imp_RevertToSelf
0x18001e878  test    rdi, rdi
0x18001e87b  jz      short loc_18001E8A5
0x18001e87d  cmp     rdi, r14
0x18001e880  jz      short loc_18001E8A5
0x18001e882  mov     ecx, dword ptr [rbp+arg_20]
0x18001e885  mov     rax, rdi
0x18001e888  test    rcx, rcx
0x18001e88b  jz      short loc_18001E899
0x18001e88d  mov     [rax], sil
0x18001e890  inc     rax
0x18001e893  sub     rcx, 1
0x18001e897  jnz     short loc_18001E88D
0x18001e899  mov     rax, [rbp+arg_8]
0x18001e89d  mov     rcx, rdi
0x18001e8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8a5  mov     eax, ebx
0x18001e8a7  add     rsp, 58h
0x18001e8ab  pop     r15
0x18001e8ad  pop     r14
0x18001e8af  pop     r13
0x18001e8b1  pop     r12
0x18001e8b3  pop     rdi
0x18001e8b4  pop     rsi
0x18001e8b5  pop     rbx
0x18001e8b6  pop     rbp
0x18001e8b7  retn
```
