# NlpMatchCacheEntry(_LOGON_CACHE_ENTRY *,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong,int *)

- ea: `0x1800428a8`
- end: `0x180042b9c`
- name: `?NlpMatchCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@KPEBU_UNICODE_STRING@@1KPEAH@Z`
- size: `756`
- prototype: `int(struct _LOGON_CACHE_ENTRY *, unsigned int, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180041d88`
- `0x180042664`
- `0x180042dac`

## callees

- `0x18000cba0`
- `0x180042040`
- `0x1800428a8`
- `0x180042ba4`
- `0x180043968`
- `0x18004588c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004295f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004295f`
- `ntdll!RtlEqualDomainName` at `0x180042a0c`
- `ntdll!RtlEqualDomainName` at `0x180042a55`
- `ntdll!RtlEqualDomainName` at `0x180042a0c`
- `ntdll!RtlEqualDomainName` at `0x180042a55`
- `ntdll!RtlEqualUnicodeString` at `0x1800429f6`
- `ntdll!RtlEqualUnicodeString` at `0x180042a20`
- `ntdll!RtlEqualUnicodeString` at `0x180042a3f`
- `ntdll!RtlEqualUnicodeString` at `0x180042a76`
- `ntdll!RtlEqualUnicodeString` at `0x1800429f6`
- `ntdll!RtlEqualUnicodeString` at `0x180042a20`
- `ntdll!RtlEqualUnicodeString` at `0x180042a3f`
- `ntdll!RtlEqualUnicodeString` at `0x180042a76`

## pseudocode

```c
__int64 __fastcall NlpMatchCacheEntry(
        struct _LOGON_CACHE_ENTRY *a1,
        __int64 a2,
        const struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        int *hMem)
{
  int *v6; // rsi
  int AccountNamesInCacheEntry; // r14d
  int v11; // eax
  int v12; // r8d
  int *v13; // rbx
  int v14; // eax
  BOOLEAN v15; // di
  struct _UNICODE_STRING *p_DomainName2; // rdx
  const UNICODE_STRING *v17; // rcx
  BOOLEAN v18; // r8
  BOOLEAN matched; // al
  int v20; // eax
  struct _UNICODE_STRING DomainName2; // [rsp+60h] [rbp-59h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp-49h] BYREF
  UNICODE_STRING v24; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING v25; // [rsp+90h] [rbp-29h] BYREF
  struct _UNICODE_STRING v26; // [rsp+A0h] [rbp-19h] BYREF
  UNICODE_STRING v27; // [rsp+B0h] [rbp-9h] BYREF

  v6 = hMem;
  *hMem = 0;
  hMem = 0;
  String2 = 0;
  DomainName2 = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  AccountNamesInCacheEntry = NlpGetAccountNamesInCacheEntry(a1, &String2, &DomainName2, &v24, &v25);
  if ( AccountNamesInCacheEntry >= 0 )
  {
    v11 = NlpBuildAccountInfo((unsigned __int16 *)a1, &hMem);
    v13 = hMem;
    AccountNamesInCacheEntry = v11;
    if ( v11 >= 0 )
    {
      AccountNamesInCacheEntry = NtLmDuplicateUnicodeString(&v27, hMem + 12);
      if ( AccountNamesInCacheEntry >= 0 )
        AccountNamesInCacheEntry = NtLmDuplicateUnicodeString(&v26, v13 + 52);
    }
    if ( v13 )
      LocalFree(v13);
    if ( AccountNamesInCacheEntry >= 0 )
    {
      v14 = *((_DWORD *)a1 + 35);
      v15 = (v14 & 1) == 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        WPP_SF_ZZZZZZDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          v12,
          (unsigned int)&String2,
          (__int64)&DomainName2,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v27,
          (__int64)&v26,
          v14,
          a5);
      if ( !a4->Length )
      {
        if ( RtlEqualUnicodeString(a3, &v25, v15) )
        {
LABEL_23:
          *v6 = 1;
          goto LABEL_24;
        }
        if ( !DomainName2.Length )
        {
          matched = NlpMatchScardUserName(a3, &String2, v15);
LABEL_22:
          if ( !matched )
            goto LABEL_24;
          goto LABEL_23;
        }
LABEL_24:
        if ( !*v6 )
          goto LABEL_39;
LABEL_30:
        if ( *((_DWORD *)a1 + 10) >= 0x10004u
          && ((v20 = *((_DWORD *)a1 + 35), (v20 & 8) != 0) || (v20 & 0x41) == 0 && *((_DWORD *)a1 + 33)) )
        {
          if ( (a5 & 0xF0000000) != 0 )
          {
            if ( a4->Length )
              *v6 = (a5 >> 29) & 1;
            goto LABEL_39;
          }
        }
        else if ( (a5 & 0x40000000) == 0 )
        {
          goto LABEL_39;
        }
        *v6 = 0;
        goto LABEL_39;
      }
      if ( !RtlEqualUnicodeString(a3, &String2, v15) )
      {
LABEL_18:
        if ( *v6 )
          goto LABEL_30;
        if ( RtlEqualUnicodeString(a3, &v27, v15) && v15 )
        {
          matched = RtlEqualDomainName(a4, &v26);
          goto LABEL_22;
        }
        goto LABEL_24;
      }
      p_DomainName2 = &DomainName2;
      v17 = a4;
      if ( v15 )
      {
        if ( RtlEqualDomainName(a4, &DomainName2) )
        {
LABEL_17:
          *v6 = 1;
          goto LABEL_18;
        }
        v18 = 1;
        p_DomainName2 = &v24;
        v17 = a4;
      }
      else
      {
        v18 = 0;
      }
      if ( !RtlEqualUnicodeString(v17, p_DomainName2, v18) )
        goto LABEL_18;
      goto LABEL_17;
    }
  }
LABEL_39:
  if ( String2.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( DomainName2.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v24.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v25.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v26.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( v27.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  return (unsigned int)AccountNamesInCacheEntry;
}

```

## disassembly

```asm
0x1800428a8  push    rbp
0x1800428aa  push    rbx
0x1800428ab  push    rsi
0x1800428ac  push    rdi
0x1800428ad  push    r12
0x1800428af  push    r13
0x1800428b1  push    r14
0x1800428b3  push    r15
0x1800428b5  lea     rbp, [rsp-0Fh]
0x1800428ba  sub     rsp, 0C8h
0x1800428c1  mov     rsi, [rbp+47h+hMem]
0x1800428c5  lea     rax, [rbp+47h+var_70]
0x1800428c9  xorps   xmm0, xmm0
0x1800428cc  mov     [rsp+100h+var_E0], rax; struct _UNICODE_STRING *
0x1800428d1  xorps   xmm1, xmm1
0x1800428d4  lea     rdx, [rbp+47h+String2]; struct _UNICODE_STRING *
0x1800428d8  mov     r15, r9
0x1800428db  mov     r12, r8
0x1800428de  xor     edi, edi
0x1800428e0  lea     r9, [rbp+47h+var_80]; struct _UNICODE_STRING *
0x1800428e4  lea     r8, [rbp+47h+DomainName2]; struct _UNICODE_STRING *
0x1800428e8  mov     [rsi], edi
0x1800428ea  mov     r13, rcx
0x1800428ed  mov     [rbp+47h+hMem], rdi
0x1800428f1  movups  xmmword ptr [rbp+47h+String2.Length], xmm0
0x1800428f5  movups  xmmword ptr [rbp+47h+DomainName2.Length], xmm1
0x1800428f9  movups  xmmword ptr [rbp+47h+var_80.Length], xmm0
0x1800428fd  movups  xmmword ptr [rbp+47h+var_70.Length], xmm1
0x180042901  movups  xmmword ptr [rbp+47h+var_50.Length], xmm0
0x180042905  movups  xmmword ptr [rbp+47h+var_60.Length], xmm1
0x180042909  call    ?NlpGetAccountNamesInCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@PEAU_UNICODE_STRING@@111@Z; NlpGetAccountNamesInCacheEntry(_LOGON_CACHE_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18004290e  mov     r14d, eax
0x180042911  test    eax, eax
0x180042913  js      loc_180042ADD
0x180042919  lea     rdx, [rbp+47h+hMem]
0x18004291d  mov     rcx, r13
0x180042920  call    NlpBuildAccountInfo
0x180042925  mov     rbx, [rbp+47h+hMem]
0x180042929  mov     r14d, eax
0x18004292c  test    eax, eax
0x18004292e  js      short loc_180042957
0x180042930  lea     rdx, [rbx+30h]
0x180042934  lea     rcx, [rbp+47h+var_50]
0x180042938  call    NtLmDuplicateUnicodeString
0x18004293d  mov     r14d, eax
0x180042940  test    eax, eax
0x180042942  js      short loc_180042957
0x180042944  lea     rdx, [rbx+0D0h]
0x18004294b  lea     rcx, [rbp+47h+var_60]
0x18004294f  call    NtLmDuplicateUnicodeString
0x180042954  mov     r14d, eax
0x180042957  test    rbx, rbx
0x18004295a  jz      short loc_180042965
0x18004295c  mov     rcx, rbx; hMem
0x18004295f  call    cs:__imp_LocalFree
0x180042965  test    r14d, r14d
0x180042968  js      loc_180042ADD
0x18004296e  mov     eax, [r13+8Ch]
0x180042975  mov     dil, al
0x180042978  not     dil
0x18004297b  and     dil, 1
0x18004297f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042986  lea     rdx, WPP_GLOBAL_Control
0x18004298d  mov     ebx, [rbp+47h+arg_20]
0x180042990  cmp     rcx, rdx
0x180042993  jz      short loc_1800429E0
0x180042995  test    dword ptr [rcx+1Ch], 4000h
0x18004299c  jz      short loc_1800429E0
0x18004299e  mov     rcx, [rcx+10h]
0x1800429a2  lea     r9, [rbp+47h+String2]
0x1800429a6  mov     [rsp+100h+var_B0], ebx
0x1800429aa  mov     [rsp+100h+var_B8], eax
0x1800429ae  lea     rax, [rbp+47h+var_60]
0x1800429b2  mov     [rsp+100h+var_C0], rax
0x1800429b7  lea     rax, [rbp+47h+var_50]
0x1800429bb  mov     [rsp+100h+var_C8], rax
0x1800429c0  lea     rax, [rbp+47h+var_70]
0x1800429c4  mov     [rsp+100h+var_D0], rax
0x1800429c9  lea     rax, [rbp+47h+var_80]
0x1800429cd  mov     [rsp+100h+var_D8], rax
0x1800429d2  lea     rax, [rbp+47h+DomainName2]
0x1800429d6  mov     [rsp+100h+var_E0], rax
0x1800429db  call    WPP_SF_ZZZZZZDD
0x1800429e0  xor     eax, eax
0x1800429e2  mov     r8b, dil; CaseInsensitive
0x1800429e5  mov     rcx, r12; String1
0x1800429e8  cmp     [r15], ax
0x1800429ec  jz      loc_180042A72
0x1800429f2  lea     rdx, [rbp+47h+String2]; String2
0x1800429f6  call    cs:__imp_RtlEqualUnicodeString
0x1800429fc  test    al, al
0x1800429fe  jz      short loc_180042A30
0x180042a00  lea     rdx, [rbp+47h+DomainName2]; DomainName2
0x180042a04  mov     rcx, r15; DomainName1
0x180042a07  test    dil, dil
0x180042a0a  jz      short loc_180042A6D
0x180042a0c  call    cs:__imp_RtlEqualDomainName
0x180042a12  test    al, al
0x180042a14  jnz     short loc_180042A2A
0x180042a16  mov     r8b, 1; CaseInsensitive
0x180042a19  lea     rdx, [rbp+47h+var_80]; String2
0x180042a1d  mov     rcx, r15; String1
0x180042a20  call    cs:__imp_RtlEqualUnicodeString
0x180042a26  test    al, al
0x180042a28  jz      short loc_180042A30
0x180042a2a  mov     dword ptr [rsi], 1
0x180042a30  cmp     dword ptr [rsi], 0
0x180042a33  jnz     short loc_180042A99
0x180042a35  mov     r8b, dil; CaseInsensitive
0x180042a38  lea     rdx, [rbp+47h+var_50]; String2
0x180042a3c  mov     rcx, r12; String1
0x180042a3f  call    cs:__imp_RtlEqualUnicodeString
0x180042a45  test    al, al
0x180042a47  jz      short loc_180042A65
0x180042a49  test    dil, dil
0x180042a4c  jz      short loc_180042A65
0x180042a4e  lea     rdx, [rbp+47h+var_60]; DomainName2
0x180042a52  mov     rcx, r15; DomainName1
0x180042a55  call    cs:__imp_RtlEqualDomainName
0x180042a5b  test    al, al
0x180042a5d  jz      short loc_180042A65
0x180042a5f  mov     dword ptr [rsi], 1
0x180042a65  xor     edi, edi
0x180042a67  cmp     [rsi], edi
0x180042a69  jz      short loc_180042ADD
0x180042a6b  jmp     short loc_180042A9B
0x180042a6d  xor     r8d, r8d
0x180042a70  jmp     short loc_180042A20
0x180042a72  lea     rdx, [rbp+47h+var_70]; String2
0x180042a76  call    cs:__imp_RtlEqualUnicodeString
0x180042a7c  xor     ecx, ecx
0x180042a7e  test    al, al
0x180042a80  jnz     short loc_180042A5F
0x180042a82  cmp     [rbp+47h+DomainName2.Length], cx
0x180042a86  jnz     short loc_180042A65
0x180042a88  mov     r8b, dil; unsigned __int8
0x180042a8b  lea     rdx, [rbp+47h+String2]; struct _UNICODE_STRING *
0x180042a8f  mov     rcx, r12; struct _UNICODE_STRING *
0x180042a92  call    ?NlpMatchScardUserName@@YA_NPEBU_UNICODE_STRING@@0E@Z; NlpMatchScardUserName(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x180042a97  jmp     short loc_180042A5B
0x180042a99  xor     edi, edi
0x180042a9b  cmp     dword ptr [r13+28h], 10004h
0x180042aa3  jb      short loc_180042AD5
0x180042aa5  mov     eax, [r13+8Ch]
0x180042aac  test    al, 8
0x180042aae  jnz     short loc_180042ABD
0x180042ab0  test    al, 41h
0x180042ab2  jnz     short loc_180042AD5
0x180042ab4  cmp     [r13+84h], edi
0x180042abb  jz      short loc_180042AD5
0x180042abd  test    ebx, 0F0000000h
0x180042ac3  jz      short loc_180042ADB
0x180042ac5  cmp     [r15], di
0x180042ac9  jz      short loc_180042ADD
0x180042acb  shr     ebx, 1Dh
0x180042ace  and     ebx, 1
0x180042ad1  mov     [rsi], ebx
0x180042ad3  jmp     short loc_180042ADD
0x180042ad5  bt      ebx, 1Eh
0x180042ad9  jnb     short loc_180042ADD
0x180042adb  mov     [rsi], edi
0x180042add  mov     rcx, [rbp+47h+String2.Buffer]
0x180042ae1  test    rcx, rcx
0x180042ae4  jz      short loc_180042AF9
0x180042ae6  mov     rax, cs:LsaFunctions
0x180042aed  mov     rax, [rax+188h]
0x180042af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af9  mov     rcx, [rbp+47h+DomainName2.Buffer]
0x180042afd  test    rcx, rcx
0x180042b00  jz      short loc_180042B15
0x180042b02  mov     rax, cs:LsaFunctions
0x180042b09  mov     rax, [rax+188h]
0x180042b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b15  mov     rcx, [rbp+47h+var_80.Buffer]
0x180042b19  test    rcx, rcx
0x180042b1c  jz      short loc_180042B31
0x180042b1e  mov     rax, cs:LsaFunctions
0x180042b25  mov     rax, [rax+188h]
0x180042b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b31  mov     rcx, [rbp+47h+var_70.Buffer]
0x180042b35  test    rcx, rcx
0x180042b38  jz      short loc_180042B4D
0x180042b3a  mov     rax, cs:LsaFunctions
0x180042b41  mov     rax, [rax+188h]
0x180042b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b4d  mov     rcx, [rbp+47h+var_60.Buffer]
0x180042b51  test    rcx, rcx
0x180042b54  jz      short loc_180042B69
0x180042b56  mov     rax, cs:LsaFunctions
0x180042b5d  mov     rax, [rax+188h]
0x180042b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b69  mov     rcx, [rbp+47h+var_50.Buffer]
0x180042b6d  test    rcx, rcx
0x180042b70  jz      short loc_180042B85
0x180042b72  mov     rax, cs:LsaFunctions
0x180042b79  mov     rax, [rax+188h]
0x180042b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b85  mov     eax, r14d
0x180042b88  add     rsp, 0C8h
0x180042b8f  pop     r15
0x180042b91  pop     r14
0x180042b93  pop     r13
0x180042b95  pop     r12
0x180042b97  pop     rdi
0x180042b98  pop     rsi
0x180042b99  pop     rbx
0x180042b9a  pop     rbp
0x180042b9b  retn
```
