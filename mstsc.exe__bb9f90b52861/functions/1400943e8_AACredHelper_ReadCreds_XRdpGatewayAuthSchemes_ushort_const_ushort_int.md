# AACredHelper::ReadCreds(_XRdpGatewayAuthSchemes,ushort const *,ushort * *,int *)

- ea: `0x1400943e8`
- end: `0x14009476e`
- name: `?ReadCreds@AACredHelper@@SAJW4_XRdpGatewayAuthSchemes@@PEBGPEAPEAGPEAH@Z`
- size: `902`
- prototype: `static int __high(enum _XRdpGatewayAuthSchemes, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140093644`

## callees

- `0x14000437c`
- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14001e210`
- `0x140042394`
- `0x1400943e8`
- `0x140113390`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140094654`
- `KERNEL32!LocalAlloc` at `0x140094654`
- `KERNEL32!LocalFree` at `0x140094738`
- `KERNEL32!LocalFree` at `0x140094738`
- `KERNEL32!GetLastError` at `0x140094552`
- `KERNEL32!GetLastError` at `0x140094552`
- `ADVAPI32!CredFree` at `0x14009472a`
- `ADVAPI32!CredFree` at `0x14009472a`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140094548`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140094548`

## string_xrefs

- `0x1400944f5`: `StringCbCopy`
- `0x1400945a6`: `CredReadDomainCredentials`
- `0x1400946f6`: `StringCchCopy`

## pseudocode

```c
__int64 __fastcall AACredHelper::ReadCreds(unsigned int a1, const unsigned __int16 *a2, __int64 a3, int *a4)
{
  signed int v5; // ebx
  unsigned __int16 *v6; // r15
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // esi
  int v11; // eax
  PVOID v12; // r11
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  signed int LastError; // eax
  unsigned int v17; // eax
  DWORD i; // edi
  __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  DWORD Count; // [rsp+30h] [rbp-D0h] BYREF
  PCREDENTIALW *Credential; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  struct _CREDENTIAL_TARGET_INFORMATIONW TargetInfo; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v27[264]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = 0;
  Credential = 0;
  v6 = 0;
  Count = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)a2);
  }
  v25 = 2;
  if ( a1 == 4 )
  {
    v10 = 1;
    goto LABEL_45;
  }
  if ( a1 <= 0xA )
  {
    v11 = 1674;
    if ( _bittest(&v11, a1) )
    {
      v10 = 0;
      goto LABEL_45;
    }
  }
  v10 = 0;
  v5 = StringCbCopyW(v27, 0x20Au, a2);
  if ( v5 >= 0 )
  {
    memset_0(&TargetInfo, 0, sizeof(TargetInfo));
    TargetInfo.TargetName = v27;
    TargetInfo.CredTypeCount = 1;
    TargetInfo.CredTypes = (LPDWORD)&v25;
    TargetInfo.Flags = 1;
    TargetInfo.DnsServerName = v27;
    if ( CredReadDomainCredentialsW(&TargetInfo, 0, &Count, &Credential) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v17);
      }
      for ( i = 0; i < Count; ++i )
      {
        if ( !wcsicmp_0(TargetInfo.TargetName, Credential[i]->TargetName) )
        {
          _mm_lfence();
          v10 = 1;
          v19 = -1;
          do
            ++v19;
          while ( Credential[i]->UserName[v19] );
          v20 = (unsigned int)(v19 + 1);
          v6 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v20);
          if ( v6 )
          {
            _mm_lfence();
            v5 = StringCchCopyW(v6, v20, Credential[i]->UserName);
            if ( v5 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = RdpWppGetCurrentThreadActivityIdPrefix();
              v14 = 23;
              v15 = "StringCchCopy";
              goto LABEL_44;
            }
          }
          else
          {
            v5 = -2147024882;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v21 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
                v21,
                (__int64)"allocate memory for userName",
                -2147024882);
            }
          }
          break;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 20;
        v15 = "CredReadDomainCredentials";
        goto LABEL_44;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != v12
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 19;
    v15 = "StringCbCopy";
LABEL_44:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      v13,
      (__int64)v15,
      v5);
  }
LABEL_45:
  if ( Credential )
    CredFree(Credential);
  if ( v6 )
    LocalFree(v6);
  *a4 = v10;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400943e8  mov     [rsp-8+arg_0], rbx
0x1400943ed  push    rbp
0x1400943ee  push    rsi
0x1400943ef  push    rdi
0x1400943f0  push    r12
0x1400943f2  push    r13
0x1400943f4  push    r14
0x1400943f6  push    r15
0x1400943f8  lea     rbp, [rsp-1C0h]
0x140094400  sub     rsp, 2C0h
0x140094407  mov     rax, cs:__security_cookie
0x14009440e  xor     rax, rsp
0x140094411  mov     [rbp+1F0h+var_40], rax
0x140094418  xor     r13d, r13d
0x14009441b  mov     r12, r9
0x14009441e  mov     ebx, r13d
0x140094421  mov     [rsp+2F0h+Credential], r13
0x140094426  mov     r15d, r13d
0x140094429  mov     [rsp+2F0h+Count], r13d
0x14009442e  mov     r14, rdx
0x140094431  mov     edi, ecx
0x140094433  mov     rax, cs:WPP_GLOBAL_Control
0x14009443a  lea     r11, WPP_GLOBAL_Control
0x140094441  cmp     rax, r11
0x140094444  jz      short loc_140094481
0x140094446  test    byte ptr [rax+1Ch], 1
0x14009444a  jz      short loc_140094481
0x14009444c  cmp     byte ptr [rax+19h], 5
0x140094450  jb      short loc_140094481
0x140094452  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094457  mov     rcx, cs:WPP_GLOBAL_Control
0x14009445e  lea     edx, [r13+12h]
0x140094462  mov     r9d, eax
0x140094465  mov     [rsp+2F0h+var_2D0], r14
0x14009446a  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140094471  mov     rcx, [rcx+10h]
0x140094475  call    WPP_SF_DS
0x14009447a  lea     r11, WPP_GLOBAL_Control
0x140094481  mov     [rsp+2F0h+var_2B0], 2
0x140094489  cmp     edi, 4
0x14009448c  jnz     short loc_140094496
0x14009448e  lea     esi, [rdi-3]
0x140094491  jmp     loc_140094720
0x140094496  cmp     edi, 0Ah
0x140094499  ja      short loc_1400944AD
0x14009449b  mov     eax, 68Ah
0x1400944a0  bt      eax, edi
0x1400944a3  jnb     short loc_1400944AD
0x1400944a5  mov     esi, r13d
0x1400944a8  jmp     loc_140094720
0x1400944ad  mov     r8, r14; unsigned __int16 *
0x1400944b0  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x1400944b4  mov     edx, 20Ah; unsigned __int64
0x1400944b9  mov     esi, r13d
0x1400944bc  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400944c1  mov     ebx, eax
0x1400944c3  test    eax, eax
0x1400944c5  jns     short loc_140094501
0x1400944c7  mov     rax, cs:WPP_GLOBAL_Control
0x1400944ce  cmp     rax, r11
0x1400944d1  jz      loc_140094720
0x1400944d7  test    byte ptr [rax+1Ch], 8
0x1400944db  jz      loc_140094720
0x1400944e1  cmp     byte ptr [rax+19h], 2
0x1400944e5  jb      loc_140094720
0x1400944eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400944f0  mov     edx, 13h
0x1400944f5  lea     rcx, aStringcbcopy; "StringCbCopy"
0x1400944fc  jmp     loc_1400946FD
0x140094501  xor     edx, edx; Val
0x140094503  lea     rcx, [rsp+2F0h+TargetInfo]; void *
0x140094508  lea     r8d, [rdx+48h]; Size
0x14009450c  call    memset_0
0x140094511  lea     rax, [rbp+1F0h+var_250]
0x140094515  mov     edi, 1
0x14009451a  mov     [rsp+2F0h+TargetInfo.TargetName], rax
0x14009451f  lea     r9, [rsp+2F0h+Credential]; Credential
0x140094524  lea     rax, [rsp+2F0h+var_2B0]
0x140094529  mov     [rbp+1F0h+TargetInfo.CredTypeCount], edi
0x14009452c  mov     [rbp+1F0h+TargetInfo.CredTypes], rax
0x140094530  lea     r8, [rsp+2F0h+Count]; Count
0x140094535  lea     rax, [rbp+1F0h+var_250]
0x140094539  mov     [rbp+1F0h+TargetInfo.Flags], edi
0x14009453c  xor     edx, edx; Flags
0x14009453e  mov     [rsp+2F0h+TargetInfo.DnsServerName], rax
0x140094543  lea     rcx, [rsp+2F0h+TargetInfo]; TargetInfo
0x140094548  call    cs:__imp_CredReadDomainCredentialsW
0x14009454e  test    eax, eax
0x140094550  jnz     short loc_1400945B2
0x140094552  call    cs:__imp_GetLastError
0x140094558  mov     ebx, eax
0x14009455a  test    eax, eax
0x14009455c  jle     short loc_140094567
0x14009455e  movzx   ebx, ax
0x140094561  or      ebx, 80070000h
0x140094567  test    ebx, ebx
0x140094569  mov     eax, 80004005h
0x14009456e  cmovns  ebx, eax
0x140094571  mov     rax, cs:WPP_GLOBAL_Control
0x140094578  lea     rcx, WPP_GLOBAL_Control
0x14009457f  cmp     rax, rcx
0x140094582  jz      loc_140094720
0x140094588  test    byte ptr [rax+1Ch], 8
0x14009458c  jz      loc_140094720
0x140094592  cmp     byte ptr [rax+19h], 2
0x140094596  jb      loc_140094720
0x14009459c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400945a1  mov     edx, 14h
0x1400945a6  lea     rcx, aCredreaddomain_0; "CredReadDomainCredentials"
0x1400945ad  jmp     loc_1400946FD
0x1400945b2  mov     rax, cs:WPP_GLOBAL_Control
0x1400945b9  lea     rcx, WPP_GLOBAL_Control
0x1400945c0  cmp     rax, rcx
0x1400945c3  jz      short loc_1400945F5
0x1400945c5  test    [rax+1Ch], dil
0x1400945c9  jz      short loc_1400945F5
0x1400945cb  cmp     byte ptr [rax+19h], 5
0x1400945cf  jb      short loc_1400945F5
0x1400945d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400945d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400945dd  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1400945e4  mov     edx, 15h
0x1400945e9  mov     r9d, eax
0x1400945ec  mov     rcx, [rcx+10h]
0x1400945f0  call    WPP_SF_d
0x1400945f5  mov     edi, r13d
0x1400945f8  cmp     edi, [rsp+2F0h+Count]
0x1400945fc  jnb     loc_140094720
0x140094602  mov     rax, [rsp+2F0h+Credential]
0x140094607  mov     rcx, [rsp+2F0h+TargetInfo.TargetName]; String1
0x14009460c  mov     r14d, edi
0x14009460f  mov     rdx, [rax+r14*8]
0x140094613  mov     rdx, [rdx+8]; String2
0x140094617  call    _wcsicmp_0
0x14009461c  test    eax, eax
0x14009461e  jz      short loc_140094624
0x140094620  inc     edi
0x140094622  jmp     short loc_1400945F8
0x140094624  lfence
0x140094627  mov     rax, [rsp+2F0h+Credential]
0x14009462c  mov     esi, 1
0x140094631  mov     rcx, [rax+r14*8]
0x140094635  or      rax, 0FFFFFFFFFFFFFFFFh
0x140094639  mov     rdx, [rcx+48h]
0x14009463d  inc     rax
0x140094640  cmp     [rdx+rax*2], r13w
0x140094645  jnz     short loc_14009463D
0x140094647  inc     eax
0x140094649  mov     ecx, 40h ; '@'; uFlags
0x14009464e  mov     ebx, eax
0x140094650  lea     rdx, [rax+rax]; uBytes
0x140094654  call    cs:__imp_LocalAlloc
0x14009465a  mov     r15, rax
0x14009465d  test    rax, rax
0x140094660  jnz     short loc_1400946AC
0x140094662  mov     ebx, 8007000Eh
0x140094667  mov     rcx, cs:WPP_GLOBAL_Control
0x14009466e  lea     rax, WPP_GLOBAL_Control
0x140094675  cmp     rcx, rax
0x140094678  jz      loc_140094720
0x14009467e  test    byte ptr [rcx+1Ch], 8
0x140094682  jz      loc_140094720
0x140094688  cmp     byte ptr [rcx+19h], 2
0x14009468c  jb      loc_140094720
0x140094692  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094697  lea     edx, [r15+16h]
0x14009469b  mov     [rsp+2F0h+var_2C8], 8007000Eh
0x1400946a3  lea     rcx, aAllocateMemory_1; "allocate memory for userName"
0x1400946aa  jmp     short loc_140094701
0x1400946ac  lfence
0x1400946af  mov     rax, [rsp+2F0h+Credential]
0x1400946b4  mov     rdx, rbx; unsigned __int64
0x1400946b7  mov     rcx, r15; unsigned __int16 *
0x1400946ba  mov     r8, [rax+r14*8]
0x1400946be  mov     r8, [r8+48h]; unsigned __int16 *
0x1400946c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400946c7  mov     ebx, eax
0x1400946c9  test    eax, eax
0x1400946cb  jns     short loc_140094720
0x1400946cd  mov     rax, cs:WPP_GLOBAL_Control
0x1400946d4  lea     rcx, WPP_GLOBAL_Control
0x1400946db  cmp     rax, rcx
0x1400946de  jz      short loc_140094720
0x1400946e0  test    byte ptr [rax+1Ch], 8
0x1400946e4  jz      short loc_140094720
0x1400946e6  cmp     byte ptr [rax+19h], 2
0x1400946ea  jb      short loc_140094720
0x1400946ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400946f1  mov     edx, 17h
0x1400946f6  lea     rcx, aStringcchcopy; "StringCchCopy"
0x1400946fd  mov     [rsp+2F0h+var_2C8], ebx
0x140094701  mov     [rsp+2F0h+var_2D0], rcx
0x140094706  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x14009470d  mov     rcx, cs:WPP_GLOBAL_Control
0x140094714  mov     r9d, eax
0x140094717  mov     rcx, [rcx+10h]
0x14009471b  call    WPP_SF_DsD
0x140094720  mov     rcx, [rsp+2F0h+Credential]; Buffer
0x140094725  test    rcx, rcx
0x140094728  jz      short loc_140094730
0x14009472a  call    cs:__imp_CredFree
0x140094730  test    r15, r15
0x140094733  jz      short loc_14009473E
0x140094735  mov     rcx, r15; hMem
0x140094738  call    cs:__imp_LocalFree
0x14009473e  mov     [r12], esi
0x140094742  mov     eax, ebx
0x140094744  mov     rcx, [rbp+1F0h+var_40]
0x14009474b  xor     rcx, rsp; StackCookie
0x14009474e  call    __security_check_cookie
0x140094753  mov     rbx, [rsp+2F0h+arg_0]
0x14009475b  add     rsp, 2C0h
0x140094762  pop     r15
0x140094764  pop     r14
0x140094766  pop     r13
0x140094768  pop     r12
0x14009476a  pop     rdi
0x14009476b  pop     rsi
0x14009476c  pop     rbp
0x14009476d  retn
```
