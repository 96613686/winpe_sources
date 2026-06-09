# AACredHelper::ReadCreds(_XRdpGatewayAuthSchemes,ushort const *,ushort * *,int *)

- ea: `0x140092278`
- end: `0x1400925fe`
- name: `?ReadCreds@AACredHelper@@SAJW4_XRdpGatewayAuthSchemes@@PEBGPEAPEAGPEAH@Z`
- size: `902`
- prototype: `static int __high(enum _XRdpGatewayAuthSchemes, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400914d4`

## callees

- `0x14000437c`
- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14001e210`
- `0x1400403d0`
- `0x140092278`
- `0x140111220`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400924e4`
- `KERNEL32!LocalAlloc` at `0x1400924e4`
- `KERNEL32!LocalFree` at `0x1400925c8`
- `KERNEL32!LocalFree` at `0x1400925c8`
- `KERNEL32!GetLastError` at `0x1400923e2`
- `KERNEL32!GetLastError` at `0x1400923e2`
- `ADVAPI32!CredFree` at `0x1400925ba`
- `ADVAPI32!CredFree` at `0x1400925ba`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x1400923d8`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x1400923d8`

## string_xrefs

- `0x140092385`: `StringCbCopy`
- `0x140092436`: `CredReadDomainCredentials`
- `0x140092586`: `StringCchCopy`

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
                14);
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
0x140092278  mov     [rsp-8+arg_0], rbx
0x14009227d  push    rbp
0x14009227e  push    rsi
0x14009227f  push    rdi
0x140092280  push    r12
0x140092282  push    r13
0x140092284  push    r14
0x140092286  push    r15
0x140092288  lea     rbp, [rsp-1C0h]
0x140092290  sub     rsp, 2C0h
0x140092297  mov     rax, cs:__security_cookie
0x14009229e  xor     rax, rsp
0x1400922a1  mov     [rbp+1F0h+var_40], rax
0x1400922a8  xor     r13d, r13d
0x1400922ab  mov     r12, r9
0x1400922ae  mov     ebx, r13d
0x1400922b1  mov     [rsp+2F0h+Credential], r13
0x1400922b6  mov     r15d, r13d
0x1400922b9  mov     [rsp+2F0h+Count], r13d
0x1400922be  mov     r14, rdx
0x1400922c1  mov     edi, ecx
0x1400922c3  mov     rax, cs:WPP_GLOBAL_Control
0x1400922ca  lea     r11, WPP_GLOBAL_Control
0x1400922d1  cmp     rax, r11
0x1400922d4  jz      short loc_140092311
0x1400922d6  test    byte ptr [rax+1Ch], 1
0x1400922da  jz      short loc_140092311
0x1400922dc  cmp     byte ptr [rax+19h], 5
0x1400922e0  jb      short loc_140092311
0x1400922e2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400922e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400922ee  lea     edx, [r13+12h]
0x1400922f2  mov     r9d, eax
0x1400922f5  mov     [rsp+2F0h+var_2D0], r14
0x1400922fa  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140092301  mov     rcx, [rcx+10h]
0x140092305  call    WPP_SF_DS
0x14009230a  lea     r11, WPP_GLOBAL_Control
0x140092311  mov     [rsp+2F0h+var_2B0], 2
0x140092319  cmp     edi, 4
0x14009231c  jnz     short loc_140092326
0x14009231e  lea     esi, [rdi-3]
0x140092321  jmp     loc_1400925B0
0x140092326  cmp     edi, 0Ah
0x140092329  ja      short loc_14009233D
0x14009232b  mov     eax, 68Ah
0x140092330  bt      eax, edi
0x140092333  jnb     short loc_14009233D
0x140092335  mov     esi, r13d
0x140092338  jmp     loc_1400925B0
0x14009233d  mov     r8, r14; unsigned __int16 *
0x140092340  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x140092344  mov     edx, 20Ah; unsigned __int64
0x140092349  mov     esi, r13d
0x14009234c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140092351  mov     ebx, eax
0x140092353  test    eax, eax
0x140092355  jns     short loc_140092391
0x140092357  mov     rax, cs:WPP_GLOBAL_Control
0x14009235e  cmp     rax, r11
0x140092361  jz      loc_1400925B0
0x140092367  test    byte ptr [rax+1Ch], 8
0x14009236b  jz      loc_1400925B0
0x140092371  cmp     byte ptr [rax+19h], 2
0x140092375  jb      loc_1400925B0
0x14009237b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092380  mov     edx, 13h
0x140092385  lea     rcx, aStringcbcopy; "StringCbCopy"
0x14009238c  jmp     loc_14009258D
0x140092391  xor     edx, edx; Val
0x140092393  lea     rcx, [rsp+2F0h+TargetInfo]; void *
0x140092398  lea     r8d, [rdx+48h]; Size
0x14009239c  call    memset_0
0x1400923a1  lea     rax, [rbp+1F0h+var_250]
0x1400923a5  mov     edi, 1
0x1400923aa  mov     [rsp+2F0h+TargetInfo.TargetName], rax
0x1400923af  lea     r9, [rsp+2F0h+Credential]; Credential
0x1400923b4  lea     rax, [rsp+2F0h+var_2B0]
0x1400923b9  mov     [rbp+1F0h+TargetInfo.CredTypeCount], edi
0x1400923bc  mov     [rbp+1F0h+TargetInfo.CredTypes], rax
0x1400923c0  lea     r8, [rsp+2F0h+Count]; Count
0x1400923c5  lea     rax, [rbp+1F0h+var_250]
0x1400923c9  mov     [rbp+1F0h+TargetInfo.Flags], edi
0x1400923cc  xor     edx, edx; Flags
0x1400923ce  mov     [rsp+2F0h+TargetInfo.DnsServerName], rax
0x1400923d3  lea     rcx, [rsp+2F0h+TargetInfo]; TargetInfo
0x1400923d8  call    cs:__imp_CredReadDomainCredentialsW
0x1400923de  test    eax, eax
0x1400923e0  jnz     short loc_140092442
0x1400923e2  call    cs:__imp_GetLastError
0x1400923e8  mov     ebx, eax
0x1400923ea  test    eax, eax
0x1400923ec  jle     short loc_1400923F7
0x1400923ee  movzx   ebx, ax
0x1400923f1  or      ebx, 80070000h
0x1400923f7  test    ebx, ebx
0x1400923f9  mov     eax, 80004005h
0x1400923fe  cmovns  ebx, eax
0x140092401  mov     rax, cs:WPP_GLOBAL_Control
0x140092408  lea     rcx, WPP_GLOBAL_Control
0x14009240f  cmp     rax, rcx
0x140092412  jz      loc_1400925B0
0x140092418  test    byte ptr [rax+1Ch], 8
0x14009241c  jz      loc_1400925B0
0x140092422  cmp     byte ptr [rax+19h], 2
0x140092426  jb      loc_1400925B0
0x14009242c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092431  mov     edx, 14h
0x140092436  lea     rcx, aCredreaddomain_0; "CredReadDomainCredentials"
0x14009243d  jmp     loc_14009258D
0x140092442  mov     rax, cs:WPP_GLOBAL_Control
0x140092449  lea     rcx, WPP_GLOBAL_Control
0x140092450  cmp     rax, rcx
0x140092453  jz      short loc_140092485
0x140092455  test    [rax+1Ch], dil
0x140092459  jz      short loc_140092485
0x14009245b  cmp     byte ptr [rax+19h], 5
0x14009245f  jb      short loc_140092485
0x140092461  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092466  mov     rcx, cs:WPP_GLOBAL_Control
0x14009246d  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140092474  mov     edx, 15h
0x140092479  mov     r9d, eax
0x14009247c  mov     rcx, [rcx+10h]
0x140092480  call    WPP_SF_d
0x140092485  mov     edi, r13d
0x140092488  cmp     edi, [rsp+2F0h+Count]
0x14009248c  jnb     loc_1400925B0
0x140092492  mov     rax, [rsp+2F0h+Credential]
0x140092497  mov     rcx, [rsp+2F0h+TargetInfo.TargetName]; String1
0x14009249c  mov     r14d, edi
0x14009249f  mov     rdx, [rax+r14*8]
0x1400924a3  mov     rdx, [rdx+8]; String2
0x1400924a7  call    _wcsicmp_0
0x1400924ac  test    eax, eax
0x1400924ae  jz      short loc_1400924B4
0x1400924b0  inc     edi
0x1400924b2  jmp     short loc_140092488
0x1400924b4  lfence
0x1400924b7  mov     rax, [rsp+2F0h+Credential]
0x1400924bc  mov     esi, 1
0x1400924c1  mov     rcx, [rax+r14*8]
0x1400924c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400924c9  mov     rdx, [rcx+48h]
0x1400924cd  inc     rax
0x1400924d0  cmp     [rdx+rax*2], r13w
0x1400924d5  jnz     short loc_1400924CD
0x1400924d7  inc     eax
0x1400924d9  mov     ecx, 40h ; '@'; uFlags
0x1400924de  mov     ebx, eax
0x1400924e0  lea     rdx, [rax+rax]; uBytes
0x1400924e4  call    cs:__imp_LocalAlloc
0x1400924ea  mov     r15, rax
0x1400924ed  test    rax, rax
0x1400924f0  jnz     short loc_14009253C
0x1400924f2  mov     ebx, 8007000Eh
0x1400924f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400924fe  lea     rax, WPP_GLOBAL_Control
0x140092505  cmp     rcx, rax
0x140092508  jz      loc_1400925B0
0x14009250e  test    byte ptr [rcx+1Ch], 8
0x140092512  jz      loc_1400925B0
0x140092518  cmp     byte ptr [rcx+19h], 2
0x14009251c  jb      loc_1400925B0
0x140092522  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092527  lea     edx, [r15+16h]
0x14009252b  mov     [rsp+2F0h+var_2C8], 8007000Eh
0x140092533  lea     rcx, aAllocateMemory_1; "allocate memory for userName"
0x14009253a  jmp     short loc_140092591
0x14009253c  lfence
0x14009253f  mov     rax, [rsp+2F0h+Credential]
0x140092544  mov     rdx, rbx; unsigned __int64
0x140092547  mov     rcx, r15; unsigned __int16 *
0x14009254a  mov     r8, [rax+r14*8]
0x14009254e  mov     r8, [r8+48h]; unsigned __int16 *
0x140092552  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140092557  mov     ebx, eax
0x140092559  test    eax, eax
0x14009255b  jns     short loc_1400925B0
0x14009255d  mov     rax, cs:WPP_GLOBAL_Control
0x140092564  lea     rcx, WPP_GLOBAL_Control
0x14009256b  cmp     rax, rcx
0x14009256e  jz      short loc_1400925B0
0x140092570  test    byte ptr [rax+1Ch], 8
0x140092574  jz      short loc_1400925B0
0x140092576  cmp     byte ptr [rax+19h], 2
0x14009257a  jb      short loc_1400925B0
0x14009257c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092581  mov     edx, 17h
0x140092586  lea     rcx, aStringcchcopy; "StringCchCopy"
0x14009258d  mov     [rsp+2F0h+var_2C8], ebx
0x140092591  mov     [rsp+2F0h+var_2D0], rcx
0x140092596  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x14009259d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400925a4  mov     r9d, eax
0x1400925a7  mov     rcx, [rcx+10h]
0x1400925ab  call    WPP_SF_DsD
0x1400925b0  mov     rcx, [rsp+2F0h+Credential]; Buffer
0x1400925b5  test    rcx, rcx
0x1400925b8  jz      short loc_1400925C0
0x1400925ba  call    cs:__imp_CredFree
0x1400925c0  test    r15, r15
0x1400925c3  jz      short loc_1400925CE
0x1400925c5  mov     rcx, r15; hMem
0x1400925c8  call    cs:__imp_LocalFree
0x1400925ce  mov     [r12], esi
0x1400925d2  mov     eax, ebx
0x1400925d4  mov     rcx, [rbp+1F0h+var_40]
0x1400925db  xor     rcx, rsp; StackCookie
0x1400925de  call    __security_check_cookie
0x1400925e3  mov     rbx, [rsp+2F0h+arg_0]
0x1400925eb  add     rsp, 2C0h
0x1400925f2  pop     r15
0x1400925f4  pop     r14
0x1400925f6  pop     r13
0x1400925f8  pop     r12
0x1400925fa  pop     rdi
0x1400925fb  pop     rsi
0x1400925fc  pop     rbp
0x1400925fd  retn
```
