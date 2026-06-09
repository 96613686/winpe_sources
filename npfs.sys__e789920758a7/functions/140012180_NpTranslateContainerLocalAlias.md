# NpTranslateContainerLocalAlias

- ea: `0x140012180`
- end: `0x14001272a`
- name: `NpTranslateContainerLocalAlias`
- size: `1450`
- prototype: `NTSTATUS __fastcall(struct _UNICODE_STRING *, void *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011f60`

## callees

- `0x1400018f4`
- `0x140001e10`
- `0x140002240`
- `0x140012180`

## import_xrefs

- `ntoskrnl!RtlGetAppContainerSidType` at `0x14001248d`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x14001248d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001250f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001252a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012545`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012560`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001250f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001252a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012545`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140012560`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400124db`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400125b9`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140012607`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400124db`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400125b9`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140012607`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012458`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400126b5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400126cb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012719`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012458`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400126b5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400126cb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012719`
- `ntoskrnl!SeQueryInformationToken` at `0x14001221e`
- `ntoskrnl!SeQueryInformationToken` at `0x14001223d`
- `ntoskrnl!SeQueryInformationToken` at `0x140012268`
- `ntoskrnl!SeQueryInformationToken` at `0x140012293`
- `ntoskrnl!SeQueryInformationToken` at `0x1400125e3`
- `ntoskrnl!SeQueryInformationToken` at `0x14001221e`
- `ntoskrnl!SeQueryInformationToken` at `0x14001223d`
- `ntoskrnl!SeQueryInformationToken` at `0x140012268`
- `ntoskrnl!SeQueryInformationToken` at `0x140012293`
- `ntoskrnl!SeQueryInformationToken` at `0x1400125e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400123c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400123c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012704`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400126f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012704`
- `ntoskrnl!RtlGetAppContainerParent` at `0x1400124ba`
- `ntoskrnl!RtlGetAppContainerParent` at `0x1400124ba`

## pseudocode

```c
NTSTATUS __fastcall NpTranslateContainerLocalAlias(struct _UNICODE_STRING *a1, void *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  char v7; // r15
  NTSTATUS AppContainerSidType; // ebx
  PVOID v9; // r8
  PWSTR Buffer; // rcx
  USHORT Length; // dx
  char v12; // di
  USHORT v13; // dx
  int v14; // r8d
  unsigned int v15; // eax
  WCHAR *Pool2; // rax
  NTSTATUS v17; // eax
  PWSTR v18; // rax
  ULONG v19; // esi
  ULONG v20; // edi
  ULONG v21; // ebx
  PULONG v22; // rax
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v26; // [rsp+60h] [rbp-A0h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-90h] BYREF
  PVOID v29; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v30; // [rsp+88h] [rbp-78h] BYREF
  PVOID v31; // [rsp+98h] [rbp-68h] BYREF
  PSID Sid; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v33; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v34; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v35[512]; // [rsp+D0h] [rbp-30h] BYREF

  P = 0;
  v25 = 0;
  Sid = 0;
  v34 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v30 = 0;
  memset(v35, 0, sizeof(v35));
  v26 = 0;
  v31 = 0;
  *a3 = 0;
  TokenInformation = 0;
  v33 = 0;
  v29 = 0;
  result = SeQueryInformationToken(a2, TokenIsAppContainer, &TokenInformation);
  if ( result >= 0 )
  {
    result = SeQueryInformationToken(a2, TokenIsRestricted|TokenGroups, &v26);
    if ( result >= 0 )
    {
      if ( !TokenInformation && !v26 )
        return 0;
      result = SeQueryInformationToken(a2, TokenSessionId, &v29);
      if ( result < 0 )
        return result;
      v7 = 0;
      if ( TokenInformation )
      {
        AppContainerSidType = SeQueryInformationToken(a2, TokenAppContainerSid, &P);
        if ( AppContainerSidType >= 0 )
        {
          AppContainerSidType = RtlGetAppContainerSidType(*(_QWORD *)P, &v25);
          if ( AppContainerSidType >= 0 )
          {
            if ( v25 == 1 )
            {
              AppContainerSidType = RtlGetAppContainerParent(*(_QWORD *)P, &Sid);
              if ( AppContainerSidType >= 0 )
              {
                AppContainerSidType = RtlConvertSidToUnicodeString(&v34, Sid, 1u);
                if ( AppContainerSidType >= 0 )
                {
                  UnicodeString.Buffer = (PWSTR)v35;
                  *(_DWORD *)&UnicodeString.Length = 0x2000000;
                  v19 = *RtlSubAuthoritySid(*(PSID *)P, 0xBu);
                  v20 = *RtlSubAuthoritySid(*(PSID *)P, 0xAu);
                  v21 = *RtlSubAuthoritySid(*(PSID *)P, 9u);
                  v22 = RtlSubAuthoritySid(*(PSID *)P, 8u);
                  AppContainerSidType = RtlUnicodeStringPrintf(
                                          &UnicodeString,
                                          L"%wZ\\%lu-%lu-%lu-%lu",
                                          &v34,
                                          *v22,
                                          v21,
                                          v20,
                                          v19);
                  if ( AppContainerSidType >= 0 )
                    goto LABEL_23;
                }
              }
            }
            else
            {
              UnicodeString = 0;
              AppContainerSidType = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)P, 1u);
              if ( AppContainerSidType >= 0 )
              {
                v7 = 1;
                goto LABEL_23;
              }
            }
          }
        }
LABEL_7:
        if ( v33.Buffer )
          RtlFreeUnicodeString(&v33);
        if ( AppContainerSidType < 0 )
          RtlFreeUnicodeString(&DestinationString);
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v31 )
          ExFreePoolWithTag(v31, 0);
        if ( Sid )
          ExFreePoolWithTag(Sid, 0);
        if ( v34.Buffer )
          RtlFreeUnicodeString(&v34);
        return 0;
      }
LABEL_23:
      v9 = v26;
      if ( v26 )
      {
        AppContainerSidType = SeQueryInformationToken(a2, TokenUser, &v31);
        if ( AppContainerSidType < 0
          || (AppContainerSidType = RtlConvertSidToUnicodeString(&v33, *(PSID *)v31, 1u), AppContainerSidType < 0) )
        {
LABEL_42:
          if ( v7 )
            RtlFreeUnicodeString(&UnicodeString);
          goto LABEL_7;
        }
        v9 = v26;
      }
      Buffer = a1->Buffer;
      v30 = *a1;
      Length = v30.Length;
      if ( *Buffer == 92 )
      {
        ++Buffer;
        v12 = 1;
        Length = v30.Length - 2;
      }
      else
      {
        v12 = 0;
      }
      DestinationString.Length = 0;
      v13 = Length - 12;
      v30.Length = v13;
      v30.MaximumLength = v13;
      v30.Buffer = Buffer + 6;
      if ( v9 )
      {
        if ( TokenInformation )
          v14 = v33.Length + UnicodeString.Length + 120;
        else
          v14 = v33.Length + 96;
      }
      else
      {
        v14 = UnicodeString.Length + 112;
      }
      v15 = v14 + v13 + 2;
      if ( !v12 )
        v15 = v14 + v13;
      if ( v15 > 0xFFFE )
      {
        AppContainerSidType = -1073741562;
      }
      else
      {
        DestinationString.MaximumLength = v15;
        Pool2 = (WCHAR *)ExAllocatePool2(256, (unsigned __int16)v15, 1850110030);
        DestinationString.Buffer = Pool2;
        if ( Pool2 )
        {
          if ( v12 )
          {
            DestinationString.MaximumLength -= 2;
            DestinationString.Buffer = Pool2 + 1;
          }
          if ( v26 )
          {
            if ( TokenInformation )
              v17 = RtlUnicodeStringPrintf(
                      &DestinationString,
                      L"Sessions\\%ld\\AppContainerNamedObjects\\%wZ\\%wZ\\%wZ",
                      (unsigned int)v29,
                      &v33,
                      &UnicodeString,
                      &v30);
            else
              v17 = RtlUnicodeStringPrintf(
                      &DestinationString,
                      L"Sessions\\%ld\\BaseNamedObjects\\%wZ\\%wZ",
                      (unsigned int)v29,
                      &v33,
                      &v30);
          }
          else
          {
            v17 = RtlUnicodeStringPrintf(
                    &DestinationString,
                    L"Sessions\\%ld\\AppContainerNamedObjects\\%wZ\\%wZ",
                    (unsigned int)v29,
                    &UnicodeString,
                    &v30);
          }
          AppContainerSidType = v17;
          v18 = DestinationString.Buffer;
          if ( v12 )
          {
            v18 = DestinationString.Buffer - 1;
            DestinationString.MaximumLength += 2;
            --DestinationString.Buffer;
          }
          if ( AppContainerSidType >= 0 )
          {
            if ( v12 )
            {
              *v18 = 92;
              DestinationString.Length += 2;
            }
            *a1 = DestinationString;
            *a3 = 1;
          }
        }
        else
        {
          AppContainerSidType = -1073741670;
        }
      }
      goto LABEL_42;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012180  mov     [rsp-8+arg_18], rbx
0x140012185  push    rbp
0x140012186  push    rsi
0x140012187  push    rdi
0x140012188  push    r12
0x14001218a  push    r13
0x14001218c  push    r14
0x14001218e  push    r15
0x140012190  lea     rbp, [rsp-1E0h]
0x140012198  sub     rsp, 2E0h
0x14001219f  mov     rax, cs:__security_cookie
0x1400121a6  xor     rax, rsp
0x1400121a9  mov     [rbp+210h+var_40], rax
0x1400121b0  xorps   xmm0, xmm0
0x1400121b3  xor     esi, esi
0x1400121b5  xor     eax, eax
0x1400121b7  mov     [rsp+310h+P], rsi
0x1400121bc  mov     r13, r8
0x1400121bf  mov     dword ptr [rbp+210h+var_258+4], eax
0x1400121c2  mov     r14, rdx
0x1400121c5  mov     [rsp+310h+var_2B8], esi
0x1400121c9  mov     r12, rcx
0x1400121cc  mov     [rbp+210h+Sid], rsi
0x1400121d0  xorps   xmm1, xmm1
0x1400121d3  lea     rcx, [rbp+210h+var_240]; void *
0x1400121d7  xor     edx, edx; Val
0x1400121d9  mov     r8d, 200h; Size
0x1400121df  movups  xmmword ptr [rbp-48h], xmm0
0x1400121e3  movups  xmmword ptr [rsp+310h+UnicodeString.Length], xmm0
0x1400121e8  movups  xmmword ptr [rsp+310h+DestinationString.Length], xmm0
0x1400121ed  movups  [rbp+210h+var_288], xmm1
0x1400121f1  call    memset
0x1400121f6  xorps   xmm0, xmm0
0x1400121f9  mov     [rsp+310h+var_2B0], rsi
0x1400121fe  lea     r8, [rsp+310h+TokenInformation]; TokenInformation
0x140012203  mov     [rbp+210h+var_278], rsi
0x140012207  lea     edx, [rsi+1Dh]; TokenInformationClass
0x14001220a  mov     [r13+0], esi
0x14001220e  mov     rcx, r14; Token
0x140012211  mov     [rsp+310h+TokenInformation], rsi
0x140012216  movups  xmmword ptr [rbp+210h+var_268.Length], xmm0
0x14001221a  mov     [rbp+210h+var_290], rsi
0x14001221e  call    cs:__imp_SeQueryInformationToken
0x140012225  nop     dword ptr [rax+rax+00h]
0x14001222a  test    eax, eax
0x14001222c  js      loc_1400122EF
0x140012232  lea     r8, [rsp+310h+var_2B0]; TokenInformation
0x140012237  mov     rcx, r14; Token
0x14001223a  lea     edx, [rsi+2Ah]; TokenInformationClass
0x14001223d  call    cs:__imp_SeQueryInformationToken
0x140012244  nop     dword ptr [rax+rax+00h]
0x140012249  test    eax, eax
0x14001224b  js      loc_1400122EF
0x140012251  cmp     [rsp+310h+TokenInformation], rsi
0x140012256  jz      loc_14001231A
0x14001225c  lea     r8, [rbp+210h+var_290]; TokenInformation
0x140012260  mov     edx, 0Ch; TokenInformationClass
0x140012265  mov     rcx, r14; Token
0x140012268  call    cs:__imp_SeQueryInformationToken
0x14001226f  nop     dword ptr [rax+rax+00h]
0x140012274  test    eax, eax
0x140012276  js      short loc_1400122EF
0x140012278  mov     r15b, sil
0x14001227b  cmp     [rsp+310h+TokenInformation], rsi
0x140012280  jz      loc_140012327
0x140012286  lea     r8, [rsp+310h+P]; TokenInformation
0x14001228b  mov     edx, 1Fh; TokenInformationClass
0x140012290  mov     rcx, r14; Token
0x140012293  call    cs:__imp_SeQueryInformationToken
0x14001229a  nop     dword ptr [rax+rax+00h]
0x14001229f  mov     ebx, eax
0x1400122a1  test    eax, eax
0x1400122a3  jns     loc_140012480
0x1400122a9  cmp     [rbp+210h+var_268.Buffer], rsi
0x1400122ad  jnz     loc_1400126B1
0x1400122b3  test    ebx, ebx
0x1400122b5  js      loc_1400126C6
0x1400122bb  mov     rcx, [rsp+310h+P]; P
0x1400122c0  test    rcx, rcx
0x1400122c3  jnz     loc_1400126DC
0x1400122c9  mov     rcx, [rbp+210h+var_278]; P
0x1400122cd  test    rcx, rcx
0x1400122d0  jnz     loc_1400126EF
0x1400122d6  mov     rcx, [rbp+210h+Sid]; P
0x1400122da  test    rcx, rcx
0x1400122dd  jnz     loc_140012702
0x1400122e3  cmp     [rbp+210h+var_258.Buffer], rsi
0x1400122e7  jnz     loc_140012715
0x1400122ed  xor     eax, eax
0x1400122ef  mov     rcx, [rbp+210h+var_40]
0x1400122f6  xor     rcx, rsp; StackCookie
0x1400122f9  call    __security_check_cookie
0x1400122fe  mov     rbx, [rsp+310h+arg_18]
0x140012306  add     rsp, 2E0h
0x14001230d  pop     r15
0x14001230f  pop     r14
0x140012311  pop     r13
0x140012313  pop     r12
0x140012315  pop     rdi
0x140012316  pop     rsi
0x140012317  pop     rbp
0x140012318  retn
0x14001231a  cmp     [rsp+310h+var_2B0], rsi
0x14001231f  jnz     loc_14001225C
0x140012325  jmp     short loc_1400122ED
0x140012327  mov     r8, [rsp+310h+var_2B0]
0x14001232c  test    r8, r8
0x14001232f  jnz     loc_1400125D7
0x140012335  movups  xmm0, xmmword ptr [r12]
0x14001233a  mov     rcx, [r12+8]
0x14001233f  mov     eax, 5Ch ; '\'
0x140012344  mov     ebx, 0FFFEh
0x140012349  movups  [rbp+210h+var_288], xmm0
0x14001234d  movzx   edx, word ptr [rbp+210h+var_288]
0x140012351  lea     r14d, [rax-5Ah]
0x140012355  cmp     ax, [rcx]
0x140012358  jz      loc_140012627
0x14001235e  mov     dil, sil
0x140012361  mov     r9d, 0Ch
0x140012367  mov     [rsp+310h+DestinationString.Length], si
0x14001236c  sub     dx, r9w
0x140012370  movzx   eax, r9w
0x140012374  shr     rax, 1
0x140012377  mov     word ptr [rbp+210h+var_288], dx
0x14001237b  mov     word ptr [rbp+210h+var_288+2], dx
0x14001237f  lea     rax, [rcx+rax*2]
0x140012383  mov     qword ptr [rbp+210h+var_288+8], rax
0x140012387  test    r8, r8
0x14001238a  jnz     loc_140012635
0x140012390  movzx   r8d, [rsp+310h+UnicodeString.Length]
0x140012396  add     r8d, 70h ; 'p'
0x14001239a  movzx   ecx, dx
0x14001239d  add     ecx, r8d
0x1400123a0  test    dil, dil
0x1400123a3  lea     eax, [rcx+2]
0x1400123a6  cmovz   eax, ecx
0x1400123a9  cmp     eax, ebx
0x1400123ab  ja      loc_140012469
0x1400123b1  movzx   edx, ax
0x1400123b4  mov     ecx, 100h
0x1400123b9  mov     r8d, 6E46704Eh
0x1400123bf  mov     [rsp+310h+DestinationString.MaximumLength], dx
0x1400123c4  call    cs:__imp_ExAllocatePool2
0x1400123cb  nop     dword ptr [rax+rax+00h]
0x1400123d0  mov     [rsp+310h+DestinationString.Buffer], rax
0x1400123d5  test    rax, rax
0x1400123d8  jz      loc_140012660
0x1400123de  test    dil, dil
0x1400123e1  jz      short loc_1400123F0
0x1400123e3  add     rax, r14
0x1400123e6  add     [rsp+310h+DestinationString.MaximumLength], bx
0x1400123eb  mov     [rsp+310h+DestinationString.Buffer], rax
0x1400123f0  lea     rax, [rbp+210h+var_288]
0x1400123f4  mov     r8d, dword ptr [rbp+210h+var_290]
0x1400123f8  lea     rcx, [rsp+310h+DestinationString]; DestinationString
0x1400123fd  cmp     [rsp+310h+var_2B0], rsi
0x140012402  jnz     loc_14001266A
0x140012408  lea     r9, [rsp+310h+UnicodeString]
0x14001240d  lea     rdx, aSessionsLdAppc_0; "Sessions\\%ld\\AppContainerNamedObjects"...
0x140012414  mov     [rsp+310h+var_2F0], rax
0x140012419  call    RtlUnicodeStringPrintf
0x14001241e  mov     ebx, eax
0x140012420  mov     rax, [rsp+310h+DestinationString.Buffer]
0x140012425  test    dil, dil
0x140012428  jnz     short loc_140012470
0x14001242a  test    ebx, ebx
0x14001242c  js      short loc_14001244A
0x14001242e  test    dil, dil
0x140012431  jnz     loc_1400126A1
0x140012437  movups  xmm0, xmmword ptr [rsp+310h+DestinationString.Length]
0x14001243c  movdqu  xmmword ptr [r12], xmm0
0x140012442  mov     dword ptr [r13+0], 1
0x14001244a  test    r15b, r15b
0x14001244d  jz      loc_1400122A9
0x140012453  lea     rcx, [rsp+310h+UnicodeString]; UnicodeString
0x140012458  call    cs:__imp_RtlFreeUnicodeString
0x14001245f  nop     dword ptr [rax+rax+00h]
0x140012464  jmp     loc_1400122A9
0x140012469  mov     ebx, 0C0000106h
0x14001246e  jmp     short loc_14001244A
0x140012470  sub     rax, r14
0x140012473  add     [rsp+310h+DestinationString.MaximumLength], r14w
0x140012479  mov     [rsp+310h+DestinationString.Buffer], rax
0x14001247e  jmp     short loc_14001242A
0x140012480  mov     rcx, [rsp+310h+P]
0x140012485  lea     rdx, [rsp+310h+var_2B8]
0x14001248a  mov     rcx, [rcx]
0x14001248d  call    cs:__imp_RtlGetAppContainerSidType
0x140012494  nop     dword ptr [rax+rax+00h]
0x140012499  mov     ebx, eax
0x14001249b  test    eax, eax
0x14001249d  js      loc_1400122A9
0x1400124a3  cmp     [rsp+310h+var_2B8], 1
0x1400124a8  jnz     loc_1400125A1
0x1400124ae  mov     rcx, [rsp+310h+P]
0x1400124b3  lea     rdx, [rbp+210h+Sid]
0x1400124b7  mov     rcx, [rcx]
0x1400124ba  call    cs:__imp_RtlGetAppContainerParent
0x1400124c1  nop     dword ptr [rax+rax+00h]
0x1400124c6  mov     ebx, eax
0x1400124c8  test    eax, eax
0x1400124ca  js      loc_1400122A9
0x1400124d0  mov     rdx, [rbp+210h+Sid]; Sid
0x1400124d4  lea     rcx, [rbp+210h+var_258]; UnicodeString
0x1400124d8  mov     r8b, 1; AllocateDestinationString
0x1400124db  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400124e2  nop     dword ptr [rax+rax+00h]
0x1400124e7  mov     ebx, eax
0x1400124e9  test    eax, eax
0x1400124eb  js      loc_1400122A9
0x1400124f1  mov     rcx, [rsp+310h+P]
0x1400124f6  lea     rax, [rbp+210h+var_240]
0x1400124fa  mov     [rsp+310h+UnicodeString.Buffer], rax
0x1400124ff  mov     edx, 0Bh; SubAuthority
0x140012504  mov     dword ptr [rsp+310h+UnicodeString.Length], 2000000h
0x14001250c  mov     rcx, [rcx]; Sid
0x14001250f  call    cs:__imp_RtlSubAuthoritySid
0x140012516  nop     dword ptr [rax+rax+00h]
0x14001251b  mov     rcx, [rsp+310h+P]
0x140012520  mov     edx, 0Ah; SubAuthority
0x140012525  mov     esi, [rax]
0x140012527  mov     rcx, [rcx]; Sid
0x14001252a  call    cs:__imp_RtlSubAuthoritySid
0x140012531  nop     dword ptr [rax+rax+00h]
0x140012536  mov     rcx, [rsp+310h+P]
0x14001253b  mov     edx, 9; SubAuthority
0x140012540  mov     edi, [rax]
0x140012542  mov     rcx, [rcx]; Sid
0x140012545  call    cs:__imp_RtlSubAuthoritySid
0x14001254c  nop     dword ptr [rax+rax+00h]
0x140012551  mov     rcx, [rsp+310h+P]
0x140012556  mov     edx, 8; SubAuthority
0x14001255b  mov     ebx, [rax]
0x14001255d  mov     rcx, [rcx]; Sid
0x140012560  call    cs:__imp_RtlSubAuthoritySid
0x140012567  nop     dword ptr [rax+rax+00h]
0x14001256c  mov     [rsp+310h+var_2E0], esi
0x140012570  lea     r8, [rbp+210h+var_258]
0x140012574  mov     dword ptr [rsp+310h+var_2E8], edi
0x140012578  lea     rdx, aWzLuLuLuLu; "%wZ\\%lu-%lu-%lu-%lu"
0x14001257f  lea     rcx, [rsp+310h+UnicodeString]; DestinationString
0x140012584  mov     dword ptr [rsp+310h+var_2F0], ebx
0x140012588  mov     r9d, [rax]
0x14001258b  call    RtlUnicodeStringPrintf
0x140012590  xor     esi, esi
0x140012592  mov     ebx, eax
0x140012594  test    eax, eax
0x140012596  js      loc_1400122A9
0x14001259c  jmp     loc_140012327
0x1400125a1  mov     rdx, [rsp+310h+P]
0x1400125a6  lea     rcx, [rsp+310h+UnicodeString]; UnicodeString
0x1400125ab  xorps   xmm0, xmm0
0x1400125ae  mov     r8b, 1; AllocateDestinationString
0x1400125b1  movups  xmmword ptr [rsp+310h+UnicodeString.Length], xmm0
0x1400125b6  mov     rdx, [rdx]; Sid
0x1400125b9  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400125c0  nop     dword ptr [rax+rax+00h]
0x1400125c5  mov     ebx, eax
0x1400125c7  test    eax, eax
0x1400125c9  js      loc_1400122A9
0x1400125cf  mov     r15b, 1
0x1400125d2  jmp     loc_140012327
0x1400125d7  lea     r8, [rbp+210h+var_278]; TokenInformation
0x1400125db  mov     edx, 1; TokenInformationClass
0x1400125e0  mov     rcx, r14; Token
0x1400125e3  call    cs:__imp_SeQueryInformationToken
0x1400125ea  nop     dword ptr [rax+rax+00h]
0x1400125ef  mov     ebx, eax
0x1400125f1  test    eax, eax
0x1400125f3  js      loc_14001244A
0x1400125f9  mov     rdx, [rbp+210h+var_278]
0x1400125fd  lea     rcx, [rbp+210h+var_268]; UnicodeString
0x140012601  mov     r8b, 1; AllocateDestinationString
0x140012604  mov     rdx, [rdx]; Sid
0x140012607  call    cs:__imp_RtlConvertSidToUnicodeString
0x14001260e  nop     dword ptr [rax+rax+00h]
0x140012613  mov     ebx, eax
0x140012615  test    eax, eax
0x140012617  js      loc_14001244A
0x14001261d  mov     r8, [rsp+310h+var_2B0]
0x140012622  jmp     loc_140012335
0x140012627  add     rcx, r14
0x14001262a  mov     dil, 1
0x14001262d  add     dx, bx
0x140012630  jmp     loc_140012361
0x140012635  cmp     [rsp+310h+TokenInformation], rsi
0x14001263a  jz      short loc_140012652
0x14001263c  movzx   r8d, [rsp+310h+UnicodeString.Length]
0x140012642  movzx   ecx, [rbp+210h+var_268.Length]
0x140012646  add     r8d, 78h ; 'x'
0x14001264a  add     r8d, ecx
0x14001264d  jmp     loc_14001239A
0x140012652  movzx   r8d, [rbp+210h+var_268.Length]
0x140012657  add     r8d, 60h ; '`'
0x14001265b  jmp     loc_14001239A
0x140012660  mov     ebx, 0C000009Ah
0x140012665  jmp     loc_14001244A
0x14001266a  lea     r9, [rbp+210h+var_268]
0x14001266e  cmp     [rsp+310h+TokenInformation], rsi
0x140012673  jz      short loc_140012695
  ... truncated ...
```
