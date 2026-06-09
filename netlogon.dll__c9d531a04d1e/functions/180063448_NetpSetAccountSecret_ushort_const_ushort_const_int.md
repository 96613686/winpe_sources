# NetpSetAccountSecret(ushort const *,ushort const *,int)

- ea: `0x180063448`
- end: `0x180063678`
- name: `?NetpSetAccountSecret@@YAJPEBG0H@Z`
- size: `560`
- prototype: `__int64 __fastcall(PCWSTR SourceString, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180060fa4`

## callees

- `0x18000e270`
- `0x1800615f0`
- `0x180061dc4`
- `0x180063448`

## import_xrefs

- `LSASRV!LsarClose` at `0x180063633`
- `LSASRV!LsarClose` at `0x180063633`
- `LSASRV!LsarCreateSecret` at `0x180063536`
- `LSASRV!LsarCreateSecret` at `0x180063536`
- `LSASRV!LsarSetSecret` at `0x1800635f8`
- `LSASRV!LsarSetSecret` at `0x1800635f8`
- `LSASRV!LsarDeleteObject` at `0x180063627`
- `LSASRV!LsarDeleteObject` at `0x180063627`
- `LSASRV!LsarOpenSecret` at `0x18006350b`
- `LSASRV!LsarOpenSecret` at `0x18006350b`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180063647`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180063647`
- `LSASRV!LsarQuerySecret` at `0x180063596`
- `LSASRV!LsarQuerySecret` at `0x180063596`
- `ntdll!RtlLeaveCriticalSection` at `0x18006354a`
- `ntdll!RtlLeaveCriticalSection` at `0x18006354a`
- `ntdll!RtlEnterCriticalSection` at `0x1800634e9`
- `ntdll!RtlEnterCriticalSection` at `0x1800634e9`
- `ntdll!RtlInitUnicodeString` at `0x1800634dc`
- `ntdll!RtlInitUnicodeString` at `0x1800634dc`
- `netutils!NetApiBufferFree` at `0x18006360f`
- `netutils!NetApiBufferFree` at `0x18006360f`

## pseudocode

```c
__int64 __fastcall NetpSetAccountSecret(PCWSTR SourceString, const unsigned __int16 *a2, int a3)
{
  int v4; // edi
  int v5; // r15d
  __int64 v8; // rdx
  int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int128 *v12; // r8
  __int64 v14; // [rsp+30h] [rbp-39h] BYREF
  __int128 *v15; // [rsp+38h] [rbp-31h] BYREF
  PCWSTR SourceStringa; // [rsp+40h] [rbp-29h] BYREF
  __int128 v17; // [rsp+48h] [rbp-21h] BYREF
  __int128 v18; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int16 v20[16]; // [rsp+78h] [rbp+Fh] BYREF

  v15 = 0;
  v14 = 0;
  SourceStringa = 0;
  v4 = 0;
  v5 = 0;
  v17 = 0;
  v18 = 0;
  DestinationString = 0;
  v9 = NetpConcatenate(
         0,
         (unsigned __int16 **)&SourceStringa,
         3u,
         L"_SC_{262E99C9-6160-4871-ACEC-4E61736B6F21}_",
         SourceString,
         L"$");
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceStringa);
    RtlEnterCriticalSection(&NlGlobalDomainCritSect);
    v9 = LsarOpenSecret(*((_QWORD *)NlGlobalDomainInfo + 49), &DestinationString, 3, &v14);
    if ( v9 == -1073741772 )
    {
      v9 = LsarCreateSecret(*((_QWORD *)NlGlobalDomainInfo + 49), &DestinationString, 983043, &v14);
      v4 = 1;
    }
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    if ( v9 >= 0 )
    {
      v10 = -1;
      *((_QWORD *)&v17 + 1) = a2;
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      LODWORD(v17) = 2 * v11;
      DWORD1(v17) = 2 * v11;
      if ( a3 )
      {
        if ( !v4 )
        {
          v9 = -1073741725;
          goto LABEL_19;
        }
        NetpGenerateDefaultPassword(SourceString, v20);
        *((_QWORD *)&v18 + 1) = v20;
        do
          ++v10;
        while ( v20[v10] );
        DWORD1(v18) = 2 * v10;
        v12 = &v18;
        LODWORD(v18) = 2 * v10;
      }
      else
      {
        if ( !v4 )
        {
          v9 = LsarQuerySecret(v14, &v15, 0, 0, 0);
          if ( v9 < 0 )
            goto LABEL_19;
          v12 = v15;
          v5 = 1;
          goto LABEL_18;
        }
        v12 = &v17;
      }
      v15 = v12;
LABEL_18:
      v9 = LsarSetSecret(v14, &v17, v12);
    }
  }
LABEL_19:
  if ( SourceStringa )
    NetApiBufferFree((LPVOID)SourceStringa);
  if ( v14 )
  {
    if ( v4 && v9 < 0 )
      LsarDeleteObject(&v14);
    else
      LsarClose(&v14);
  }
  if ( v15 && v5 )
    LsaIFree_LSAPR_CR_CIPHER_VALUE(v15, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180063448  mov     [rsp-8+arg_10], rbx
0x18006344d  mov     [rsp-8+arg_18], rdi
0x180063452  push    rbp
0x180063453  push    r12
0x180063455  push    r13
0x180063457  push    r14
0x180063459  push    r15
0x18006345b  lea     rbp, [rsp-37h]
0x180063460  sub     rsp, 0A0h
0x180063467  mov     rax, cs:__security_cookie
0x18006346e  xor     rax, rsp
0x180063471  mov     [rbp+57h+var_28], rax
0x180063475  xor     eax, eax
0x180063477  lea     r9, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x18006347e  xorps   xmm0, xmm0
0x180063481  mov     [rbp+57h+var_88], rax
0x180063485  mov     r13d, r8d
0x180063488  mov     [rbp+57h+var_90], rax
0x18006348c  mov     [rbp+57h+SourceString], rax
0x180063490  mov     edi, eax
0x180063492  lea     r8d, [rax+3]; unsigned __int16
0x180063496  mov     r15d, eax
0x180063499  lea     rax, asc_1800A5A84; "$"
0x1800634a0  mov     r14, rdx
0x1800634a3  mov     [rsp+0C0h+var_98], rax
0x1800634a8  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x1800634ac  mov     [rsp+0C0h+var_A0], rcx
0x1800634b1  mov     r12, rcx
0x1800634b4  xorps   xmm1, xmm1
0x1800634b7  xor     ecx, ecx; int
0x1800634b9  movups  [rbp+57h+var_78], xmm0
0x1800634bd  movups  [rbp+57h+var_68], xmm1
0x1800634c1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800634c5  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x1800634ca  mov     ebx, eax
0x1800634cc  test    eax, eax
0x1800634ce  js      loc_180063602
0x1800634d4  mov     rdx, [rbp+57h+SourceString]; SourceString
0x1800634d8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800634dc  call    cs:__imp_RtlInitUnicodeString
0x1800634e2  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800634e9  call    cs:__imp_RtlEnterCriticalSection
0x1800634ef  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x1800634f6  lea     r9, [rbp+57h+var_90]
0x1800634fa  mov     r8d, 3
0x180063500  lea     rdx, [rbp+57h+DestinationString]
0x180063504  mov     rcx, [rcx+188h]
0x18006350b  call    cs:__imp_LsarOpenSecret
0x180063511  mov     ebx, eax
0x180063513  cmp     eax, 0C0000034h
0x180063518  jnz     short loc_180063543
0x18006351a  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180063521  lea     r9, [rbp+57h+var_90]
0x180063525  mov     r8d, 0F0003h
0x18006352b  lea     rdx, [rbp+57h+DestinationString]
0x18006352f  mov     rcx, [rcx+188h]
0x180063536  call    cs:__imp_LsarCreateSecret
0x18006353c  mov     ebx, eax
0x18006353e  mov     edi, 1
0x180063543  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006354a  call    cs:__imp_RtlLeaveCriticalSection
0x180063550  xor     ecx, ecx
0x180063552  test    ebx, ebx
0x180063554  js      loc_180063602
0x18006355a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006355e  mov     qword ptr [rbp+57h+var_78+8], r14
0x180063562  mov     rax, rbx
0x180063565  inc     rax
0x180063568  cmp     [r14+rax*2], cx
0x18006356d  jnz     short loc_180063565
0x18006356f  add     eax, eax
0x180063571  xor     r14d, r14d
0x180063574  mov     dword ptr [rbp+57h+var_78], eax
0x180063577  mov     dword ptr [rbp+57h+var_78+4], eax
0x18006357a  test    r13d, r13d
0x18006357d  jnz     short loc_1800635B2
0x18006357f  test    edi, edi
0x180063581  jnz     short loc_1800635AC
0x180063583  mov     rcx, [rbp+57h+var_90]
0x180063587  lea     rdx, [rbp+57h+var_88]
0x18006358b  xor     r9d, r9d
0x18006358e  mov     [rsp+0C0h+var_A0], r14
0x180063593  xor     r8d, r8d
0x180063596  call    cs:__imp_LsarQuerySecret
0x18006359c  mov     ebx, eax
0x18006359e  test    eax, eax
0x1800635a0  js      short loc_180063605
0x1800635a2  mov     r8, [rbp+57h+var_88]
0x1800635a6  lea     r15d, [r14+1]
0x1800635aa  jmp     short loc_1800635F0
0x1800635ac  lea     r8, [rbp+57h+var_78]
0x1800635b0  jmp     short loc_1800635EC
0x1800635b2  test    edi, edi
0x1800635b4  jnz     short loc_1800635BD
0x1800635b6  mov     ebx, 0C0000063h
0x1800635bb  jmp     short loc_180063605
0x1800635bd  lea     rdx, [rbp+57h+var_48]; unsigned __int16 *
0x1800635c1  mov     rcx, r12; SourceString
0x1800635c4  call    ?NetpGenerateDefaultPassword@@YAXPEBGPEAG@Z; NetpGenerateDefaultPassword(ushort const *,ushort *)
0x1800635c9  lea     rax, [rbp+57h+var_48]
0x1800635cd  mov     qword ptr [rbp+57h+var_68+8], rax
0x1800635d1  lea     rax, [rbp+57h+var_48]
0x1800635d5  inc     rbx
0x1800635d8  cmp     [rax+rbx*2], r14w
0x1800635dd  jnz     short loc_1800635D5
0x1800635df  lea     eax, [rbx+rbx]
0x1800635e2  mov     dword ptr [rbp+57h+var_68+4], eax
0x1800635e5  lea     r8, [rbp+57h+var_68]
0x1800635e9  mov     dword ptr [rbp+57h+var_68], eax
0x1800635ec  mov     [rbp+57h+var_88], r8
0x1800635f0  mov     rcx, [rbp+57h+var_90]
0x1800635f4  lea     rdx, [rbp+57h+var_78]
0x1800635f8  call    cs:__imp_LsarSetSecret
0x1800635fe  mov     ebx, eax
0x180063600  jmp     short loc_180063605
0x180063602  xor     r14d, r14d
0x180063605  cmp     [rbp+57h+SourceString], r14
0x180063609  jz      short loc_180063615
0x18006360b  mov     rcx, [rbp+57h+SourceString]; Buffer
0x18006360f  call    cs:__imp_NetApiBufferFree
0x180063615  cmp     [rbp+57h+var_90], r14
0x180063619  jz      short loc_180063639
0x18006361b  test    edi, edi
0x18006361d  jz      short loc_18006362F
0x18006361f  test    ebx, ebx
0x180063621  jns     short loc_18006362F
0x180063623  lea     rcx, [rbp+57h+var_90]
0x180063627  call    cs:__imp_LsarDeleteObject
0x18006362d  jmp     short loc_180063639
0x18006362f  lea     rcx, [rbp+57h+var_90]
0x180063633  call    cs:__imp_LsarClose
0x180063639  mov     rcx, [rbp+57h+var_88]
0x18006363d  test    rcx, rcx
0x180063640  jz      short loc_18006364D
0x180063642  test    r15d, r15d
0x180063645  jz      short loc_18006364D
0x180063647  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x18006364d  mov     eax, ebx
0x18006364f  mov     rcx, [rbp+57h+var_28]
0x180063653  xor     rcx, rsp; StackCookie
0x180063656  call    __security_check_cookie
0x18006365b  lea     r11, [rsp+0C0h+var_20]
0x180063663  mov     rbx, [r11+40h]
0x180063667  mov     rdi, [r11+48h]
0x18006366b  mov     rsp, r11
0x18006366e  pop     r15
0x180063670  pop     r14
0x180063672  pop     r13
0x180063674  pop     r12
0x180063676  pop     rbp
0x180063677  retn
```
