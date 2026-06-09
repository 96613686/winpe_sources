# MspGetCredentialKeyForUser

- ea: `0x180046480`
- end: `0x1800466f0`
- name: `MspGetCredentialKeyForUser`
- size: `624`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054f20`

## callees

- `0x180006c50`
- `0x180007700`
- `0x18001eebc`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18003536c`
- `0x1800461a0`
- `0x180046480`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800465d6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800465d6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800465a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800465a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800466c4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800466c4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800466a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800466b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800466a6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800466b5`

## pseudocode

```c
__int64 __fastcall MspGetCredentialKeyForUser(struct _UNICODE_STRING *a1)
{
  NTSTATUS CredentialKeyWorker; // ebx
  __int128 v3; // xmm0
  int v4; // eax
  struct _UNICODE_STRING v6; // [rsp+30h] [rbp-69h] BYREF
  PLSA_TRANSLATED_SID2 Sids; // [rsp+40h] [rbp-59h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-51h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING v10; // [rsp+58h] [rbp-41h] BYREF
  struct _LSA_UNICODE_STRING Names; // [rsp+68h] [rbp-31h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v13[40]; // [rsp+A8h] [rbp+Fh] BYREF

  PolicyHandle = 0;
  ReferencedDomains = 0;
  v6 = 0;
  Sids = 0;
  *(_QWORD *)&v10.Length = 262146;
  v10.Buffer = (PWSTR)L"\\";
  v6.MaximumLength = a1[1].Length + a1->Length + 4;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v13, 0, sizeof(v13));
  Names = 0;
  v6.Buffer = (PWSTR)NtLmAllocate(v6.MaximumLength);
  if ( v6.Buffer )
  {
    CredentialKeyWorker = RtlUnicodeStringCat(&v6, a1);
    if ( CredentialKeyWorker >= 0 )
    {
      CredentialKeyWorker = RtlUnicodeStringCat(&v6, &v10);
      if ( CredentialKeyWorker >= 0 )
      {
        CredentialKeyWorker = RtlUnicodeStringCat(&v6, a1 + 1);
        if ( CredentialKeyWorker >= 0 )
        {
          v6.Buffer[(unsigned __int64)v6.Length >> 1] = 0;
          Names.Buffer = v6.Buffer;
          Names.Length = v6.Length;
          Names.MaximumLength = v6.MaximumLength;
          CredentialKeyWorker = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
          if ( CredentialKeyWorker >= 0 )
          {
            CredentialKeyWorker = LsaLookupNames2(PolicyHandle, 0, 1u, &Names, &ReferencedDomains, &Sids);
            if ( CredentialKeyWorker >= 0 && Sids )
            {
              CredentialKeyWorker = MspGetCredentialKeyWorker(a1, Sids->Sid, 2, v13);
              if ( CredentialKeyWorker >= 0 )
              {
                v3 = *(_OWORD *)&v13[20];
                v4 = *(_DWORD *)&v13[36];
                BYTE3(a1[2].Buffer) = 1;
                *(_OWORD *)&a1[3].MaximumLength = v3;
                *(_DWORD *)&a1[4].MaximumLength = v4;
                HIDWORD(a1[2].Buffer) = 2;
              }
              else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  11,
                  WPP_01e79bdfac1238d4519298733882f715_Traceguids,
                  (unsigned int)CredentialKeyWorker);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_Zd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  (unsigned int)WPP_01e79bdfac1238d4519298733882f715_Traceguids,
                  (unsigned int)&v6,
                  CredentialKeyWorker);
              }
              if ( CredentialKeyWorker >= 0 )
                CredentialKeyWorker = -1073741726;
            }
          }
        }
      }
    }
  }
  else
  {
    CredentialKeyWorker = -1073741801;
  }
  if ( v6.Buffer )
    NtLmFree(v6.Buffer);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( Sids )
    LsaFreeMemory(Sids);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return (unsigned int)CredentialKeyWorker;
}

```

## disassembly

```asm
0x180046480  mov     [rsp-8+arg_8], rbx
0x180046485  mov     [rsp-8+arg_10], rsi
0x18004648a  push    rbp
0x18004648b  push    rdi
0x18004648c  push    r15
0x18004648e  lea     rbp, [rsp-47h]
0x180046493  sub     rsp, 0E0h
0x18004649a  mov     rax, cs:__security_cookie
0x1800464a1  xor     rax, rsp
0x1800464a4  mov     [rbp+57h+var_20], rax
0x1800464a8  xor     eax, eax
0x1800464aa  mov     [rbp+57h+PolicyHandle], 0
0x1800464b2  xorps   xmm0, xmm0
0x1800464b5  mov     [rbp+57h+var_28], rax
0x1800464b9  mov     rdi, rcx
0x1800464bc  mov     [rbp+57h+var_A0], 0
0x1800464c4  movups  xmmword ptr [rbp+57h+var_C0.Length], xmm0
0x1800464c8  lea     ecx, [rax+4]
0x1800464cb  mov     [rbp+57h+var_B0], 0
0x1800464d3  lea     r15d, [rax+2]
0x1800464d7  mov     qword ptr [rbp+57h+var_98.Length], 40002h
0x1800464df  lea     rax, asc_180072468; "\\"
0x1800464e6  mov     [rbp+57h+var_98.Buffer], rax
0x1800464ea  movzx   eax, word ptr [rdi]
0x1800464ed  add     ax, [rdi+10h]
0x1800464f1  add     ax, cx
0x1800464f4  movzx   ecx, ax; uBytes
0x1800464f7  mov     [rbp+57h+var_C0.MaximumLength], cx
0x1800464fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800464ff  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180046503  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180046507  movups  [rbp+57h+var_48], xmm0
0x18004650b  movups  [rbp+57h+var_38], xmm0
0x18004650f  movups  xmmword ptr [rbp+57h+Names.Length], xmm0
0x180046513  call    NtLmAllocate
0x180046518  mov     [rbp+57h+var_C0.Buffer], rax
0x18004651c  test    rax, rax
0x18004651f  jnz     short loc_18004652B
0x180046521  mov     ebx, 0C0000017h
0x180046526  jmp     loc_18004668F
0x18004652b  mov     rdx, rdi; struct _UNICODE_STRING *
0x18004652e  lea     rcx, [rbp+57h+var_C0]; struct _UNICODE_STRING *
0x180046532  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x180046537  mov     ebx, eax
0x180046539  test    eax, eax
0x18004653b  js      loc_18004668F
0x180046541  lea     rdx, [rbp+57h+var_98]; struct _UNICODE_STRING *
0x180046545  lea     rcx, [rbp+57h+var_C0]; struct _UNICODE_STRING *
0x180046549  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x18004654e  mov     ebx, eax
0x180046550  test    eax, eax
0x180046552  js      loc_18004668F
0x180046558  lea     rdx, [rdi+10h]; struct _UNICODE_STRING *
0x18004655c  lea     rcx, [rbp+57h+var_C0]; struct _UNICODE_STRING *
0x180046560  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x180046565  mov     ebx, eax
0x180046567  test    eax, eax
0x180046569  js      loc_18004668F
0x18004656f  movzx   edx, [rbp+57h+var_C0.Length]
0x180046573  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180046577  mov     rax, [rbp+57h+var_C0.Buffer]
0x18004657b  xor     ecx, ecx; SystemName
0x18004657d  shr     rdx, 1
0x180046580  mov     r8d, 800h; DesiredAccess
0x180046586  mov     [rax+rdx*2], cx
0x18004658a  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004658e  mov     rax, [rbp+57h+var_C0.Buffer]
0x180046592  mov     [rbp+57h+Names.Buffer], rax
0x180046596  movzx   eax, [rbp+57h+var_C0.Length]
0x18004659a  mov     [rbp+57h+Names.Length], ax
0x18004659e  movzx   eax, [rbp+57h+var_C0.MaximumLength]
0x1800465a2  mov     [rbp+57h+Names.MaximumLength], ax
0x1800465a6  call    cs:__imp_LsaOpenPolicy
0x1800465ac  mov     ebx, eax
0x1800465ae  test    eax, eax
0x1800465b0  js      loc_18004668F
0x1800465b6  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800465ba  lea     rax, [rbp+57h+var_B0]
0x1800465be  mov     [rsp+0F0h+Sids], rax; Sids
0x1800465c3  lea     r9, [rbp+57h+Names]; Names
0x1800465c7  xor     edx, edx; Flags
0x1800465c9  lea     rax, [rbp+57h+var_A0]
0x1800465cd  mov     [rsp+0F0h+ReferencedDomains], rax; ReferencedDomains
0x1800465d2  lea     r8d, [rdx+1]; Count
0x1800465d6  call    cs:__imp_LsaLookupNames2
0x1800465dc  mov     ebx, eax
0x1800465de  test    eax, eax
0x1800465e0  js      short loc_18004664F
0x1800465e2  mov     rcx, [rbp+57h+var_B0]
0x1800465e6  test    rcx, rcx
0x1800465e9  jz      short loc_18004664F
0x1800465eb  mov     rdx, [rcx+8]
0x1800465ef  lea     r9, [rbp+57h+var_48]
0x1800465f3  mov     rcx, rdi
0x1800465f6  mov     r8d, r15d
0x1800465f9  call    MspGetCredentialKeyWorker
0x1800465fe  mov     ebx, eax
0x180046600  test    eax, eax
0x180046602  jns     short loc_180046637
0x180046604  mov     rcx, cs:WPP_GLOBAL_Control
0x18004660b  lea     rax, WPP_GLOBAL_Control
0x180046612  cmp     rcx, rax
0x180046615  jz      short loc_18004668F
0x180046617  test    [rcx+1Ch], r15b
0x18004661b  jz      short loc_18004668F
0x18004661d  mov     rcx, [rcx+10h]
0x180046621  lea     r8, WPP_01e79bdfac1238d4519298733882f715_Traceguids
0x180046628  mov     edx, 0Bh
0x18004662d  mov     r9d, ebx
0x180046630  call    WPP_SF_d
0x180046635  jmp     short loc_18004668F
0x180046637  movups  xmm0, [rbp+57h+var_38+4]
0x18004663b  mov     eax, dword ptr [rbp+57h+var_28+4]
0x18004663e  mov     byte ptr [rdi+2Bh], 1
0x180046642  movups  xmmword ptr [rdi+32h], xmm0
0x180046646  mov     [rdi+42h], eax
0x180046649  mov     [rdi+2Ch], r15d
0x18004664d  jmp     short loc_18004668F
0x18004664f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046656  lea     rax, WPP_GLOBAL_Control
0x18004665d  cmp     rcx, rax
0x180046660  jz      short loc_180046685
0x180046662  test    [rcx+1Ch], r15b
0x180046666  jz      short loc_180046685
0x180046668  mov     rcx, [rcx+10h]
0x18004666c  lea     r9, [rbp+57h+var_C0]
0x180046670  mov     edx, 0Ah
0x180046675  mov     dword ptr [rsp+0F0h+ReferencedDomains], ebx
0x180046679  lea     r8, WPP_01e79bdfac1238d4519298733882f715_Traceguids
0x180046680  call    WPP_SF_Zd
0x180046685  test    ebx, ebx
0x180046687  mov     eax, 0C0000062h
0x18004668c  cmovns  ebx, eax
0x18004668f  mov     rcx, [rbp+57h+var_C0.Buffer]
0x180046693  test    rcx, rcx
0x180046696  jz      short loc_18004669D
0x180046698  call    NtLmFree
0x18004669d  mov     rcx, [rbp+57h+var_A0]; Buffer
0x1800466a1  test    rcx, rcx
0x1800466a4  jz      short loc_1800466AC
0x1800466a6  call    cs:__imp_LsaFreeMemory
0x1800466ac  mov     rcx, [rbp+57h+var_B0]; Buffer
0x1800466b0  test    rcx, rcx
0x1800466b3  jz      short loc_1800466BB
0x1800466b5  call    cs:__imp_LsaFreeMemory
0x1800466bb  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1800466bf  test    rcx, rcx
0x1800466c2  jz      short loc_1800466CA
0x1800466c4  call    cs:__imp_LsaClose
0x1800466ca  mov     eax, ebx
0x1800466cc  mov     rcx, [rbp+57h+var_20]
0x1800466d0  xor     rcx, rsp; StackCookie
0x1800466d3  call    __security_check_cookie
0x1800466d8  lea     r11, [rsp+0F0h+var_10]
0x1800466e0  mov     rbx, [r11+28h]
0x1800466e4  mov     rsi, [r11+30h]
0x1800466e8  mov     rsp, r11
0x1800466eb  pop     r15
0x1800466ed  pop     rdi
0x1800466ee  pop     rbp
0x1800466ef  retn
```
