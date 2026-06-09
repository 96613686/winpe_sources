# FTCache::MatchSpn(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)

- ea: `0x180029928`
- end: `0x180029c43`
- name: `?MatchSpn@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z`
- size: `795`
- prototype: `__int64 __usercall@<rax>(FTCache *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, unsigned __int8 *@<r8>, struct _UNICODE_STRING *@<r9>, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18002901c`

## callees

- `0x180001670`
- `0x18000fd18`
- `0x180022210`
- `0x180022278`
- `0x180024cd4`
- `0x1800294ac`
- `0x1800295ac`
- `0x180029928`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029c15`
- `DSPARSE!DsCrackSpn3W` at `0x1800299e2`
- `DSPARSE!DsCrackSpn3W` at `0x1800299e2`

## pseudocode

```c
__int64 __fastcall FTCache::MatchSpn(
        FTCache *this,
        struct _UNICODE_STRING *a2,
        unsigned __int8 *a3,
        struct _UNICODE_STRING *a4,
        void **a5)
{
  unsigned int Length; // edx
  const WCHAR *Buffer; // rcx
  DWORD v11; // eax
  unsigned int v12; // ebx
  struct FTCache::TLN_ENTRY *v13; // r13
  struct _UNICODE_STRING *v14; // r8
  struct FTCache::TLN_ENTRY *v15; // rax
  __int64 v16; // rdx
  void *v17; // r14
  int matched; // eax
  DWORD pcInstanceName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcDomainName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcRealmName; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v23; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v24; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v25; // [rsp+90h] [rbp-70h] BYREF
  WCHAR InstanceName[256]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR DomainName[256]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR RealmName[256]; // [rsp+4A0h] [rbp+3A0h] BYREF

  Length = a2->Length;
  pcInstanceName = 256;
  pcDomainName = 256;
  pcRealmName = 256;
  Buffer = a2->Buffer;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v11 = DsCrackSpn3W(
          Buffer,
          Length >> 1,
          0,
          0,
          &pcInstanceName,
          InstanceName,
          0,
          &pcDomainName,
          DomainName,
          &pcRealmName,
          RealmName);
  v12 = v11;
  if ( v11 == 87 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v12 = -1073741811;
    goto LABEL_35;
  }
  if ( v11 == 111 )
  {
    v12 = -2147483643;
    goto LABEL_35;
  }
  if ( v11 )
  {
LABEL_35:
    if ( !a4 )
      goto LABEL_37;
    goto LABEL_36;
  }
  --pcInstanceName;
  --pcDomainName;
  --pcRealmName;
  v23.Length = 2 * pcInstanceName;
  v24.Length = 2 * pcDomainName;
  v25.Length = 2 * pcRealmName;
  v23.MaximumLength = 2 * pcInstanceName + 2;
  v23.Buffer = InstanceName;
  v24.MaximumLength = 2 * pcDomainName + 2;
  v24.Buffer = DomainName;
  v25.MaximumLength = 2 * pcRealmName + 2;
  v25.Buffer = RealmName;
  if ( !(2 * (_WORD)pcRealmName) )
  {
    if ( 2 * (_WORD)pcDomainName )
    {
      matched = FTCache::MatchNamespace(this, &v24, a3, a4, a5);
    }
    else
    {
      if ( !(2 * (_WORD)pcInstanceName) )
        goto LABEL_34;
      v12 = FTCache::MatchNamespace(this, &v23, a3, a4, a5);
      if ( v12 != -1073741198 )
      {
LABEL_32:
        if ( (v12 & 0x80000000) == 0 )
          return v12;
        goto LABEL_35;
      }
      matched = FTCache::MatchNetbiosName(this, &v23, a3, a4, a5);
    }
    v12 = matched;
    goto LABEL_32;
  }
  v13 = FTCache::LongestSubstringMatchTln(this, a3, &v25);
  if ( !v13 )
    goto LABEL_34;
  if ( !v24.Length )
  {
    if ( v23.Length )
    {
      v14 = &v23;
      goto LABEL_14;
    }
LABEL_34:
    v12 = -1073741198;
    goto LABEL_35;
  }
  v14 = &v24;
LABEL_14:
  v15 = FTCache::LongestSubstringMatchTln(this, a3, v14);
  if ( !v15 )
    goto LABEL_34;
  v16 = *((_QWORD *)v13 + 6);
  if ( v16 != *((_QWORD *)v15 + 6) )
    goto LABEL_34;
  v17 = *(void **)(v16 + 16);
  if ( !a4 || FtcCopyUnicodeString(a4, (PCUNICODE_STRING)v16, 0) )
  {
    if ( !a5 || FtcCopySid(a5, v17) )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v12 = -1073741670;
    goto LABEL_35;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  v12 = -1073741670;
LABEL_36:
  LocalFree(a4->Buffer);
  *a4 = 0;
LABEL_37:
  if ( a5 )
  {
    LocalFree(*a5);
    *a5 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180029928  push    rbp
0x18002992a  push    rbx
0x18002992b  push    rsi
0x18002992c  push    rdi
0x18002992d  push    r12
0x18002992f  push    r13
0x180029931  push    r14
0x180029933  push    r15
0x180029935  lea     rbp, [rsp-5B8h]
0x18002993d  sub     rsp, 6B8h
0x180029944  mov     rax, cs:__security_cookie
0x18002994b  xor     rax, rsp
0x18002994e  mov     [rbp+5F0h+var_50], rax
0x180029955  mov     rdi, [rbp+5F0h+arg_20]
0x18002995c  mov     r14, rcx
0x18002995f  mov     ecx, 100h
0x180029964  mov     rax, rdx
0x180029967  movzx   edx, word ptr [rdx]
0x18002996a  xorps   xmm0, xmm0
0x18002996d  mov     [rsp+6F0h+var_690], ecx
0x180029971  mov     rsi, r9
0x180029974  mov     [rsp+6F0h+var_68C], ecx
0x180029978  mov     r15, r8
0x18002997b  mov     [rsp+6F0h+var_688], ecx
0x18002997f  xorps   xmm1, xmm1
0x180029982  lea     rcx, [rbp+5F0h+var_250]
0x180029989  shr     edx, 1; cSpn
0x18002998b  mov     [rsp+6F0h+RealmName], rcx; RealmName
0x180029990  xor     r12d, r12d
0x180029993  lea     rcx, [rsp+6F0h+var_688]
0x180029998  xor     r9d, r9d; HostName
0x18002999b  mov     [rsp+6F0h+pcRealmName], rcx; pcRealmName
0x1800299a0  xor     r8d, r8d; pcHostName
0x1800299a3  lea     rcx, [rbp+5F0h+var_450]
0x1800299aa  mov     [rsp+6F0h+DomainName], rcx; DomainName
0x1800299af  lea     rcx, [rsp+6F0h+var_68C]
0x1800299b4  mov     [rsp+6F0h+pcDomainName], rcx; pcDomainName
0x1800299b9  lea     rcx, [rbp+5F0h+var_650]
0x1800299bd  mov     [rsp+6F0h+pPortNumber], r12; pPortNumber
0x1800299c2  mov     [rsp+6F0h+InstanceName], rcx; InstanceName
0x1800299c7  lea     rcx, [rsp+6F0h+var_690]
0x1800299cc  mov     [rsp+6F0h+pcInstanceName], rcx; pcInstanceName
0x1800299d1  mov     rcx, [rax+8]; pszSpn
0x1800299d5  movups  xmmword ptr [rsp+6F0h+var_680.Length], xmm0
0x1800299da  movups  xmmword ptr [rbp+5F0h+var_670.Length], xmm1
0x1800299de  movups  xmmword ptr [rbp+5F0h+var_660.Length], xmm0
0x1800299e2  call    cs:__imp_DsCrackSpn3W
0x1800299e8  mov     ebx, eax
0x1800299ea  cmp     eax, 57h ; 'W'
0x1800299ed  jnz     short loc_180029A1B
0x1800299ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299f6  test    byte ptr [rcx+1Ch], 8
0x1800299fa  jz      short loc_180029A11
0x1800299fc  mov     rcx, [rcx+10h]
0x180029a00  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180029a07  mov     edx, 0E4h
0x180029a0c  call    WPP_SF_
0x180029a11  mov     ebx, 0C000000Dh
0x180029a16  jmp     loc_180029BF8
0x180029a1b  cmp     eax, 6Fh ; 'o'
0x180029a1e  jnz     short loc_180029A2A
0x180029a20  mov     ebx, 80000005h
0x180029a25  jmp     loc_180029BF8
0x180029a2a  test    eax, eax
0x180029a2c  jnz     loc_180029BF8
0x180029a32  mov     edx, [rsp+6F0h+var_690]
0x180029a36  or      eax, 0FFFFFFFFh
0x180029a39  mov     r8d, [rsp+6F0h+var_68C]
0x180029a3e  add     edx, eax
0x180029a40  mov     ecx, [rsp+6F0h+var_688]
0x180029a44  add     r8d, eax
0x180029a47  add     ecx, eax
0x180029a49  mov     [rsp+6F0h+var_690], edx
0x180029a4d  add     dx, dx
0x180029a50  mov     [rsp+6F0h+var_68C], r8d
0x180029a55  add     r8w, r8w
0x180029a59  mov     [rsp+6F0h+var_688], ecx
0x180029a5d  add     cx, cx
0x180029a60  mov     [rsp+6F0h+var_680.Length], dx
0x180029a65  mov     [rbp+5F0h+var_670.Length], r8w
0x180029a6a  lea     eax, [rdx+2]
0x180029a6d  mov     [rbp+5F0h+var_660.Length], cx
0x180029a71  mov     [rsp+6F0h+var_680.MaximumLength], ax
0x180029a76  lea     rax, [rbp+5F0h+var_650]
0x180029a7a  mov     [rsp+6F0h+var_680.Buffer], rax
0x180029a7f  lea     eax, [r8+2]
0x180029a83  mov     [rbp+5F0h+var_670.MaximumLength], ax
0x180029a87  lea     rax, [rbp+5F0h+var_450]
0x180029a8e  mov     [rbp+5F0h+var_670.Buffer], rax
0x180029a92  lea     eax, [rcx+2]
0x180029a95  mov     [rbp+5F0h+var_660.MaximumLength], ax
0x180029a99  lea     rax, [rbp+5F0h+var_250]
0x180029aa0  mov     [rbp+5F0h+var_660.Buffer], rax
0x180029aa4  jz      loc_180029B8E
0x180029aaa  lea     r8, [rbp+5F0h+var_660]; struct _UNICODE_STRING *
0x180029aae  mov     rdx, r15; unsigned __int8 *
0x180029ab1  mov     rcx, r14; this
0x180029ab4  call    ?LongestSubstringMatchTln@FTCache@@AEAAPEAUTLN_ENTRY@1@PEAEPEAU_UNICODE_STRING@@@Z; FTCache::LongestSubstringMatchTln(uchar *,_UNICODE_STRING *)
0x180029ab9  mov     r13, rax
0x180029abc  test    rax, rax
0x180029abf  jz      loc_180029BF3
0x180029ac5  cmp     [rbp+5F0h+var_670.Length], r12w
0x180029aca  jbe     short loc_180029AD2
0x180029acc  lea     r8, [rbp+5F0h+var_670]
0x180029ad0  jmp     short loc_180029AE3
0x180029ad2  cmp     [rsp+6F0h+var_680.Length], r12w
0x180029ad8  jbe     loc_180029BF3
0x180029ade  lea     r8, [rsp+6F0h+var_680]; struct _UNICODE_STRING *
0x180029ae3  mov     rdx, r15; unsigned __int8 *
0x180029ae6  mov     rcx, r14; this
0x180029ae9  call    ?LongestSubstringMatchTln@FTCache@@AEAAPEAUTLN_ENTRY@1@PEAEPEAU_UNICODE_STRING@@@Z; FTCache::LongestSubstringMatchTln(uchar *,_UNICODE_STRING *)
0x180029aee  test    rax, rax
0x180029af1  jz      loc_180029BF3
0x180029af7  mov     rdx, [r13+30h]; SourceString
0x180029afb  cmp     rdx, [rax+30h]
0x180029aff  jnz     loc_180029BF3
0x180029b05  mov     r14, [rdx+10h]
0x180029b09  test    rsi, rsi
0x180029b0c  jz      short loc_180029B49
0x180029b0e  xor     r8d, r8d; unsigned __int16 *
0x180029b11  mov     rcx, rsi; DestinationString
0x180029b14  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x180029b19  test    al, al
0x180029b1b  jnz     short loc_180029B49
0x180029b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b24  test    byte ptr [rcx+1Ch], 8
0x180029b28  jz      short loc_180029B3F
0x180029b2a  mov     rcx, [rcx+10h]
0x180029b2e  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180029b35  mov     edx, 0E5h
0x180029b3a  call    WPP_SF_
0x180029b3f  mov     ebx, 0C000009Ah
0x180029b44  jmp     loc_180029BFD
0x180029b49  test    rdi, rdi
0x180029b4c  jz      loc_180029C1E
0x180029b52  mov     rdx, r14; void *
0x180029b55  mov     rcx, rdi; void **
0x180029b58  call    ?FtcCopySid@@YAEPEAPEAXPEAX@Z; FtcCopySid(void * *,void *)
0x180029b5d  test    al, al
0x180029b5f  jnz     loc_180029C1E
0x180029b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b6c  test    byte ptr [rcx+1Ch], 8
0x180029b70  jz      short loc_180029B87
0x180029b72  mov     rcx, [rcx+10h]
0x180029b76  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180029b7d  mov     edx, 0E6h
0x180029b82  call    WPP_SF_
0x180029b87  mov     ebx, 0C000009Ah
0x180029b8c  jmp     short loc_180029BF8
0x180029b8e  test    r8w, r8w
0x180029b92  jz      short loc_180029BAD
0x180029b94  mov     r9, rsi; struct _UNICODE_STRING *
0x180029b97  mov     [rsp+6F0h+pcInstanceName], rdi; void **
0x180029b9c  mov     r8, r15; unsigned __int8 *
0x180029b9f  lea     rdx, [rbp+5F0h+var_670]; struct _UNICODE_STRING *
0x180029ba3  mov     rcx, r14; this
0x180029ba6  call    ?MatchNamespace@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchNamespace(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029bab  jmp     short loc_180029BEB
0x180029bad  test    dx, dx
0x180029bb0  jz      short loc_180029BF3
0x180029bb2  mov     r9, rsi; struct _UNICODE_STRING *
0x180029bb5  mov     [rsp+6F0h+pcInstanceName], rdi; void **
0x180029bba  mov     r8, r15; unsigned __int8 *
0x180029bbd  lea     rdx, [rsp+6F0h+var_680]; struct _UNICODE_STRING *
0x180029bc2  mov     rcx, r14; this
0x180029bc5  call    ?MatchNamespace@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchNamespace(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029bca  mov     ebx, eax
0x180029bcc  cmp     eax, 0C0000272h
0x180029bd1  jnz     short loc_180029BED
0x180029bd3  mov     r9, rsi; struct _UNICODE_STRING *
0x180029bd6  mov     [rsp+6F0h+pcInstanceName], rdi; void **
0x180029bdb  mov     r8, r15; unsigned __int8 *
0x180029bde  lea     rdx, [rsp+6F0h+var_680]; struct _UNICODE_STRING *
0x180029be3  mov     rcx, r14; this
0x180029be6  call    ?MatchNetbiosName@FTCache@@AEAAJPEAU_UNICODE_STRING@@PEAE0PEAPEAX@Z; FTCache::MatchNetbiosName(_UNICODE_STRING *,uchar *,_UNICODE_STRING *,void * *)
0x180029beb  mov     ebx, eax
0x180029bed  test    ebx, ebx
0x180029bef  jns     short loc_180029C1E
0x180029bf1  jmp     short loc_180029BF8
0x180029bf3  mov     ebx, 0C0000272h
0x180029bf8  test    rsi, rsi
0x180029bfb  jz      short loc_180029C0D
0x180029bfd  mov     rcx, [rsi+8]; hMem
0x180029c01  call    cs:__imp_LocalFree
0x180029c07  xorps   xmm0, xmm0
0x180029c0a  movups  xmmword ptr [rsi], xmm0
0x180029c0d  test    rdi, rdi
0x180029c10  jz      short loc_180029C1E
0x180029c12  mov     rcx, [rdi]; hMem
0x180029c15  call    cs:__imp_LocalFree
0x180029c1b  mov     [rdi], r12
0x180029c1e  mov     eax, ebx
0x180029c20  mov     rcx, [rbp+5F0h+var_50]
0x180029c27  xor     rcx, rsp; StackCookie
0x180029c2a  call    __security_check_cookie
0x180029c2f  add     rsp, 6B8h
0x180029c36  pop     r15
0x180029c38  pop     r14
0x180029c3a  pop     r13
0x180029c3c  pop     r12
0x180029c3e  pop     rdi
0x180029c3f  pop     rsi
0x180029c40  pop     rbx
0x180029c41  pop     rbp
0x180029c42  retn
```
