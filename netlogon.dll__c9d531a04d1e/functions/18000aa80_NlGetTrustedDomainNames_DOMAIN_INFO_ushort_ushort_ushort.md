# NlGetTrustedDomainNames(_DOMAIN_INFO *,ushort *,ushort * *,ushort * *)

- ea: `0x18000aa80`
- end: `0x18000ad2c`
- name: `?NlGetTrustedDomainNames@@YAKPEAU_DOMAIN_INFO@@PEAGPEAPEAG2@Z`
- size: `684`
- prototype: `unsigned int(struct _DOMAIN_INFO *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003c50`

## callees

- `0x180003170`
- `0x180003200`
- `0x180003670`
- `0x18000aa80`
- `0x180082e88`
- `0x18008315c`
- `0x180083250`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000aad9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ab13`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000aad9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ab13`
- `ntdll!RtlLeaveCriticalSection` at `0x18000acd1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ad03`
- `ntdll!RtlLeaveCriticalSection` at `0x18000acd1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ad03`
- `ntdll!RtlEnterCriticalSection` at `0x18000ab42`
- `ntdll!RtlEnterCriticalSection` at `0x18000ac2a`
- `ntdll!RtlEnterCriticalSection` at `0x18000ab42`
- `ntdll!RtlEnterCriticalSection` at `0x18000ac2a`
- `netutils!NetApiBufferFree` at `0x18000acdf`
- `netutils!NetApiBufferFree` at `0x18000acf1`
- `netutils!NetApiBufferFree` at `0x18000acdf`
- `netutils!NetApiBufferFree` at `0x18000acf1`
- `netutils!NetpwNameCompare` at `0x18000ab77`
- `netutils!NetpwNameCompare` at `0x18000ac5e`
- `netutils!NetpwNameCompare` at `0x18000ab77`
- `netutils!NetpwNameCompare` at `0x18000ac5e`

## pseudocode

```c
__int64 __fastcall NlGetTrustedDomainNames(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        LPVOID *a4)
{
  unsigned int v4; // r14d
  bool v6; // zf
  int v10; // eax
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  const char *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int i; // ebp
  char *v17; // rcx
  const char *v18; // rcx
  struct TRUSTED_DOMAIN *v19; // rax
  char *v20; // rcx
  unsigned __int16 *v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  const CHAR *v23; // rcx
  unsigned __int16 *v24; // rax
  struct _RTL_CRITICAL_SECTION *v25; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // rbp
  __int64 v27; // r15
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rcx
  void *v30; // rcx
  unsigned __int16 *v31; // rax
  void *v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int16 *v35; // [rsp+A0h] [rbp+18h] BYREF

  v4 = 0;
  v6 = NlGlobalMemberWorkstation == 0;
  *a3 = 0;
  *a4 = 0;
  if ( v6 )
  {
    v26 = a1 + 10;
    v13 = 0;
    RtlEnterCriticalSection(a1 + 10);
    while ( 1 )
    {
      if ( v4 >= HIDWORD(a1[12].DebugInfo) )
        goto LABEL_40;
      v27 = 56LL * v4;
      v28 = *(_QWORD *)(v27 + a1[11].SpinCount);
      if ( v28 )
      {
        if ( !(unsigned int)NetpwNameCompare(v28, a2, 6) )
          break;
      }
      v29 = *(const unsigned __int16 **)(v27 + a1[11].SpinCount + 8);
      if ( v29 )
      {
        if ( (unsigned int)NlEqualDnsName(v29, a2) )
          break;
      }
      ++v4;
    }
    v30 = *(void **)(v27 + a1[11].SpinCount);
    if ( !v30 || (v31 = (unsigned __int16 *)NetpAllocWStrFromWStr(v30), (*a4 = v31) != 0) )
    {
      v32 = *(void **)(v27 + a1[11].SpinCount + 8);
      if ( !v32 || (v33 = (unsigned __int16 *)NetpAllocWStrFromWStr(v32), (*a3 = v33) != 0) )
      {
LABEL_40:
        v25 = v26;
        goto LABEL_41;
      }
    }
    v22 = v26;
LABEL_35:
    v15 = 8;
    RtlLeaveCriticalSection(v22);
    goto LABEL_36;
  }
  v10 = WideCharToMultiByte(0xFDE9u, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v10;
  if ( !v10 || (lpMultiByteStr = (CHAR *)NetpMemoryAllocate((unsigned int)(v10 + 1)), (v13 = lpMultiByteStr) == 0) )
  {
LABEL_6:
    v13 = 0;
    v15 = 8;
LABEL_36:
    if ( *a3 )
    {
      NetApiBufferFree(*a3);
      *a3 = 0;
    }
    if ( *a4 )
    {
      NetApiBufferFree(*a4);
      *a4 = 0;
    }
    goto LABEL_42;
  }
  v14 = WideCharToMultiByte(0xFDE9u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !v14 )
  {
    NetpMemoryFree(v13);
    goto LABEL_6;
  }
  v13[v14] = 0;
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  for ( i = 0; ; ++i )
  {
    if ( i >= NlGlobalTrustedDomainCount )
      goto LABEL_21;
    v17 = (char *)NlGlobalTrustedDomainList + 40 * i;
    if ( v17 )
    {
      if ( !(unsigned int)NetpwNameCompare(v17, a2, 6) )
        break;
    }
    v18 = (const char *)*((_QWORD *)NlGlobalTrustedDomainList + 5 * i + 4);
    if ( v18 )
    {
      if ( (unsigned int)NlEqualDnsNameUtf8(v18, v13) )
        break;
    }
  }
  v19 = NlGlobalTrustedDomainList;
  v20 = (char *)NlGlobalTrustedDomainList + 40 * i;
  if ( v20 )
  {
    v21 = (unsigned __int16 *)NetpAllocWStrFromWStr(v20);
    *a4 = v21;
    if ( !v21 )
      goto LABEL_16;
    v19 = NlGlobalTrustedDomainList;
  }
  v23 = (const CHAR *)*((_QWORD *)v19 + 5 * i + 4);
  if ( v23 )
  {
    v35 = 0;
    if ( NetpAllocWStrFromUtf8StrAsRequired(v23, 0xFFFFFFFF, 0, 0, &v35) )
    {
      *a3 = 0;
      goto LABEL_16;
    }
    v24 = v35;
    *a3 = v35;
    if ( !v24 )
    {
LABEL_16:
      v22 = &NlGlobalDcDiscoveryCritSect;
      goto LABEL_35;
    }
  }
LABEL_21:
  v25 = &NlGlobalDcDiscoveryCritSect;
LABEL_41:
  RtlLeaveCriticalSection(v25);
  v15 = 0;
LABEL_42:
  if ( v13 )
    NetpMemoryFree(v13);
  return v15;
}

```

## disassembly

```asm
0x18000aa80  mov     rax, rsp
0x18000aa83  push    rbx
0x18000aa84  push    rbp
0x18000aa85  push    rsi
0x18000aa86  push    rdi
0x18000aa87  push    r12
0x18000aa89  push    r13
0x18000aa8b  push    r14
0x18000aa8d  push    r15
0x18000aa8f  sub     rsp, 48h
0x18000aa93  xor     r14d, r14d
0x18000aa96  mov     r12, r9
0x18000aa99  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x18000aaa0  mov     rsi, r8
0x18000aaa3  mov     r13, rdx
0x18000aaa6  mov     [r8], r14
0x18000aaa9  mov     rbx, rcx
0x18000aaac  mov     [r9], r14
0x18000aaaf  jz      loc_18000AC1D
0x18000aab5  mov     [rax-50h], r14
0x18000aab9  mov     r8, rdx; lpWideCharStr
0x18000aabc  mov     [rax-58h], r14
0x18000aac0  or      ebp, 0FFFFFFFFh
0x18000aac3  mov     [rax-60h], r14d
0x18000aac7  mov     r15d, 0FDE9h
0x18000aacd  mov     r9d, ebp; cchWideChar
0x18000aad0  mov     [rax-68h], r14
0x18000aad4  mov     ecx, r15d; CodePage
0x18000aad7  xor     edx, edx; dwFlags
0x18000aad9  call    cs:__imp_WideCharToMultiByte
0x18000aadf  mov     ebx, eax
0x18000aae1  test    eax, eax
0x18000aae3  jz      short loc_18000AB25
0x18000aae5  lea     ecx, [rax+1]
0x18000aae8  call    NetpMemoryAllocate
0x18000aaed  mov     rdi, rax
0x18000aaf0  test    rax, rax
0x18000aaf3  jz      short loc_18000AB25
0x18000aaf5  mov     [rsp+88h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000aafa  mov     r9d, ebp; cchWideChar
0x18000aafd  mov     [rsp+88h+lpDefaultChar], r14; lpDefaultChar
0x18000ab02  mov     r8, r13; lpWideCharStr
0x18000ab05  mov     [rsp+88h+cbMultiByte], ebx; cbMultiByte
0x18000ab09  xor     edx, edx; dwFlags
0x18000ab0b  mov     ecx, r15d; CodePage
0x18000ab0e  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x18000ab13  call    cs:__imp_WideCharToMultiByte
0x18000ab19  test    eax, eax
0x18000ab1b  jnz     short loc_18000AB32
0x18000ab1d  mov     rcx, rdi
0x18000ab20  call    NetpMemoryFree
0x18000ab25  mov     rdi, r14
0x18000ab28  mov     ebx, 8
0x18000ab2d  jmp     loc_18000ACD7
0x18000ab32  cdqe
0x18000ab34  lea     r15, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x18000ab3b  mov     rcx, r15; CriticalSection
0x18000ab3e  mov     [rax+rdi], r14b
0x18000ab42  call    cs:__imp_RtlEnterCriticalSection
0x18000ab48  mov     ebp, r14d
0x18000ab4b  cmp     ebp, cs:?NlGlobalTrustedDomainCount@@3KA; ulong NlGlobalTrustedDomainCount
0x18000ab51  jnb     loc_18000AC10
0x18000ab57  mov     eax, ebp
0x18000ab59  lea     rbx, [rax+rax*4]
0x18000ab5d  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000ab64  lea     rcx, [rax+rbx*8]
0x18000ab68  test    rcx, rcx
0x18000ab6b  jz      short loc_18000AB81
0x18000ab6d  xor     r9d, r9d
0x18000ab70  mov     rdx, r13
0x18000ab73  lea     r8d, [r9+6]
0x18000ab77  call    cs:__imp_NetpwNameCompare
0x18000ab7d  test    eax, eax
0x18000ab7f  jz      short loc_18000ABA2
0x18000ab81  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000ab88  mov     rcx, [rax+rbx*8+20h]; char *
0x18000ab8d  test    rcx, rcx
0x18000ab90  jz      short loc_18000AB9E
0x18000ab92  mov     rdx, rdi; char *
0x18000ab95  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18000ab9a  test    eax, eax
0x18000ab9c  jnz     short loc_18000ABA2
0x18000ab9e  inc     ebp
0x18000aba0  jmp     short loc_18000AB4B
0x18000aba2  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000aba9  lea     rcx, [rax+rbx*8]; Src
0x18000abad  test    rcx, rcx
0x18000abb0  jz      short loc_18000ABCF
0x18000abb2  call    NetpAllocWStrFromWStr
0x18000abb7  mov     [r12], rax
0x18000abbb  test    rax, rax
0x18000abbe  jnz     short loc_18000ABC8
0x18000abc0  mov     rcx, r15
0x18000abc3  jmp     loc_18000ACCC
0x18000abc8  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000abcf  mov     rcx, [rax+rbx*8+20h]; lpMultiByteStr
0x18000abd4  test    rcx, rcx
0x18000abd7  jz      short loc_18000AC10
0x18000abd9  lea     rax, [rsp+88h+arg_10]
0x18000abe1  mov     [rsp+88h+arg_10], r14
0x18000abe9  xor     r9d, r9d; unsigned __int16 *
0x18000abec  mov     [rsp+88h+lpMultiByteStr], rax; unsigned __int16 **
0x18000abf1  xor     r8d, r8d; unsigned int
0x18000abf4  or      edx, 0FFFFFFFFh; cbMultiByte
0x18000abf7  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18000abfc  test    eax, eax
0x18000abfe  jnz     short loc_18000AC18
0x18000ac00  mov     rax, [rsp+88h+arg_10]
0x18000ac08  mov     [rsi], rax
0x18000ac0b  test    rax, rax
0x18000ac0e  jz      short loc_18000ABC0
0x18000ac10  mov     rcx, r15
0x18000ac13  jmp     loc_18000AD03
0x18000ac18  mov     [rsi], r14
0x18000ac1b  jmp     short loc_18000ABC0
0x18000ac1d  lea     rbp, [rcx+190h]
0x18000ac24  mov     rdi, r14
0x18000ac27  mov     rcx, rbp; CriticalSection
0x18000ac2a  call    cs:__imp_RtlEnterCriticalSection
0x18000ac30  cmp     r14d, [rbx+1E4h]
0x18000ac37  jnb     loc_18000ACFD
0x18000ac3d  mov     eax, r14d
0x18000ac40  imul    r15, rax, 38h ; '8'
0x18000ac44  mov     rax, [rbx+1D8h]
0x18000ac4b  mov     rcx, [r15+rax]
0x18000ac4f  test    rcx, rcx
0x18000ac52  jz      short loc_18000AC68
0x18000ac54  xor     r9d, r9d
0x18000ac57  mov     rdx, r13
0x18000ac5a  lea     r8d, [r9+6]
0x18000ac5e  call    cs:__imp_NetpwNameCompare
0x18000ac64  test    eax, eax
0x18000ac66  jz      short loc_18000AC8A
0x18000ac68  mov     rax, [rbx+1D8h]
0x18000ac6f  mov     rcx, [r15+rax+8]; unsigned __int16 *
0x18000ac74  test    rcx, rcx
0x18000ac77  jz      short loc_18000AC85
0x18000ac79  mov     rdx, r13; unsigned __int16 *
0x18000ac7c  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18000ac81  test    eax, eax
0x18000ac83  jnz     short loc_18000AC8A
0x18000ac85  inc     r14d
0x18000ac88  jmp     short loc_18000AC30
0x18000ac8a  mov     rax, [rbx+1D8h]
0x18000ac91  xor     r14d, r14d
0x18000ac94  mov     rcx, [r15+rax]; Src
0x18000ac98  test    rcx, rcx
0x18000ac9b  jz      short loc_18000ACAB
0x18000ac9d  call    NetpAllocWStrFromWStr
0x18000aca2  mov     [r12], rax
0x18000aca6  test    rax, rax
0x18000aca9  jz      short loc_18000ACC9
0x18000acab  mov     rax, [rbx+1D8h]
0x18000acb2  mov     rcx, [r15+rax+8]; Src
0x18000acb7  test    rcx, rcx
0x18000acba  jz      short loc_18000AD00
0x18000acbc  call    NetpAllocWStrFromWStr
0x18000acc1  mov     [rsi], rax
0x18000acc4  test    rax, rax
0x18000acc7  jnz     short loc_18000AD00
0x18000acc9  mov     rcx, rbp; CriticalSection
0x18000accc  mov     ebx, 8
0x18000acd1  call    cs:__imp_RtlLeaveCriticalSection
0x18000acd7  mov     rcx, [rsi]; Buffer
0x18000acda  test    rcx, rcx
0x18000acdd  jz      short loc_18000ACE8
0x18000acdf  call    cs:__imp_NetApiBufferFree
0x18000ace5  mov     [rsi], r14
0x18000ace8  mov     rcx, [r12]; Buffer
0x18000acec  test    rcx, rcx
0x18000acef  jz      short loc_18000AD0C
0x18000acf1  call    cs:__imp_NetApiBufferFree
0x18000acf7  mov     [r12], r14
0x18000acfb  jmp     short loc_18000AD0C
0x18000acfd  xor     r14d, r14d
0x18000ad00  mov     rcx, rbp; CriticalSection
0x18000ad03  call    cs:__imp_RtlLeaveCriticalSection
0x18000ad09  mov     ebx, r14d
0x18000ad0c  test    rdi, rdi
0x18000ad0f  jz      short loc_18000AD19
0x18000ad11  mov     rcx, rdi
0x18000ad14  call    NetpMemoryFree
0x18000ad19  mov     eax, ebx
0x18000ad1b  add     rsp, 48h
0x18000ad1f  pop     r15
0x18000ad21  pop     r14
0x18000ad23  pop     r13
0x18000ad25  pop     r12
0x18000ad27  pop     rdi
0x18000ad28  pop     rsi
0x18000ad29  pop     rbp
0x18000ad2a  pop     rbx
0x18000ad2b  retn
```
