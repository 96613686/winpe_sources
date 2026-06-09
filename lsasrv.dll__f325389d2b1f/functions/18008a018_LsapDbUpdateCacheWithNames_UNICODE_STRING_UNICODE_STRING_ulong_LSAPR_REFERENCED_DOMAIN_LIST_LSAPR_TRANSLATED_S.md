# LsapDbUpdateCacheWithNames(_UNICODE_STRING *,_UNICODE_STRING *,ulong,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SID_EX2 *)

- ea: `0x18008a018`
- end: `0x18008a325`
- name: `?LsapDbUpdateCacheWithNames@@YAXPEAU_UNICODE_STRING@@0KPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SID_EX2@@@Z`
- size: `781`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SID_EX2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180091f70`

## callees

- `0x1800371a0`
- `0x18008a018`
- `0x1800f4854`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a0f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a126`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a183`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a21e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a0f5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a126`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a183`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008a21e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008a050`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008a050`
- `ntdll!RtlEqualSid` at `0x18008a1a1`
- `ntdll!RtlEqualSid` at `0x18008a1a1`
- `ntdll!RtlLeaveCriticalSection` at `0x18008a307`
- `ntdll!RtlLeaveCriticalSection` at `0x18008a307`
- `ntdll!RtlEnterCriticalSection` at `0x18008a063`
- `ntdll!RtlEnterCriticalSection` at `0x18008a063`

## pseudocode

```c
void __fastcall LsapDbUpdateCacheWithNames(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        unsigned int a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4,
        struct _LSAPR_TRANSLATED_SID_EX2 *a5)
{
  unsigned int v5; // esi
  unsigned int v6; // r12d
  __int64 v7; // rdi
  int v8; // ecx
  char v9; // dl
  char v10; // bp
  struct _RTL_BALANCED_NODE *v11; // r14
  struct _RTL_BALANCED_NODE *v12; // rbx
  int v13; // eax
  struct _RTL_BALANCED_NODE *v14; // rcx
  char v15; // si
  const WCHAR *lpString2; // [rsp+20h] [rbp-78h]
  int cchCount2; // [rsp+28h] [rbp-70h]
  char v18; // [rsp+40h] [rbp-58h]
  unsigned int v19; // [rsp+44h] [rbp-54h]
  struct _FILETIME v20; // [rsp+48h] [rbp-50h] BYREF

  v5 = a3;
  v20 = 0;
  GetSystemTimeAsFileTime(&v20);
  RtlEnterCriticalSection(&LsapSidCacheLock);
  v19 = 0;
  v6 = 0;
  if ( v5 )
  {
    v7 = 0;
    while ( 1 )
    {
      v18 = 0;
      v8 = *((_DWORD *)a5 + 6 * v7);
      v9 = 0;
      if ( ((v8 - 6) & 0xFFFFFFFD) == 0 || (v10 = 1, v8 == 7) )
        v10 = 0;
      v11 = 0;
      v12 = LsapSidCache;
      if ( LsapSidCache )
        break;
LABEL_28:
      if ( v10 && !v9 )
        LsapDbAddOneSidToCache(
          *((PSID *)a5 + 3 * v7 + 1),
          &a1[v7],
          *((enum _SID_NAME_USE *)a5 + 6 * v7),
          (struct _LSAPR_TRUST_INFORMATION *)(*((_QWORD *)a4 + 1) + 24LL * *((int *)a5 + 6 * v7 + 4)),
          *((_DWORD *)a5 + 6 * v7 + 5),
          1u,
          0);
      ++v6;
      ++v7;
      v19 = v6;
      if ( v6 >= v5 )
        goto LABEL_32;
    }
    while ( 1 )
    {
      cchCount2 = a1[v7].Length >> 1;
      lpString2 = a1[v7].Buffer;
      if ( LODWORD(v12[1].Right) == 3 )
      {
        if ( CompareStringW(
               0x409u,
               0x31003u,
               (PCNZWCH)v12[2].Children[1],
               LOWORD(v12[2].Children[0]) >> 1,
               lpString2,
               cchCount2) != 2 )
          goto LABEL_24;
        if ( !v10 )
          goto LABEL_19;
      }
      else
      {
        v13 = CompareStringW(
                0x409u,
                0x31003u,
                (PCNZWCH)v12[1].Children[0],
                LOWORD(v12->ParentValue) >> 1,
                lpString2,
                cchCount2);
        if ( !v10 )
        {
          if ( v13 != 2
            || a2[v7].Length
            && CompareStringW(
                 0x409u,
                 0x31003u,
                 (PCNZWCH)v12[2].Children[1],
                 LOWORD(v12[2].Children[0]) >> 1,
                 a2[v7].Buffer,
                 a2[v7].Length >> 1) != 2 )
          {
            goto LABEL_24;
          }
          goto LABEL_19;
        }
        if ( v13 != 2
          || CompareStringW(
               0x409u,
               0x31003u,
               (PCNZWCH)v12[2].Children[1],
               LOWORD(v12[2].Children[0]) >> 1,
               *(PCNZWCH *)(*((_QWORD *)a4 + 1) + 24LL * *((int *)a5 + 6 * v7 + 4) + 8),
               *(unsigned __int16 *)(*((_QWORD *)a4 + 1) + 24LL * *((int *)a5 + 6 * v7 + 4)) >> 1) != 2 )
        {
          goto LABEL_24;
        }
      }
      if ( RtlEqualSid(v12->Children[1], *((PSID *)a5 + 3 * v7 + 1)) )
      {
        v12[3].Children[0] = (struct _RTL_BALANCED_NODE *)(LsapSidCacheRefreshTime.QuadPart + *(_QWORD *)&v20);
        v12[2].ParentValue = LsapSidCacheExpiryTime.QuadPart + *(_QWORD *)&v20;
        v18 = 1;
LABEL_24:
        if ( !v12 )
          goto LABEL_27;
        v11 = v12;
        v12 = v12->Children[0];
        goto LABEL_26;
      }
LABEL_19:
      if ( HIDWORD(v12[4].Left) )
        goto LABEL_24;
      v14 = v12;
      v12 = v12->Children[0];
      if ( v11 )
      {
        v11->Children[0] = v12;
        v15 = 0;
        v12 = v11;
      }
      else
      {
        LsapSidCache = v12;
        v15 = 1;
      }
      v11 = 0;
      LsapDbFreeCacheEntry(v14);
      --LsapSidCacheCount;
      if ( !v15 )
        goto LABEL_24;
LABEL_26:
      if ( !v12 )
      {
LABEL_27:
        v6 = v19;
        v5 = a3;
        v9 = v18;
        goto LABEL_28;
      }
    }
  }
LABEL_32:
  RtlLeaveCriticalSection(&LsapSidCacheLock);
}

```

## disassembly

```asm
0x18008a018  mov     rax, rsp
0x18008a01b  mov     [rax+20h], r9
0x18008a01f  mov     [rax+18h], r8d
0x18008a023  mov     [rax+10h], rdx
0x18008a027  mov     [rax+8], rcx
0x18008a02b  push    rbx
0x18008a02c  push    rbp
0x18008a02d  push    rsi
0x18008a02e  push    rdi
0x18008a02f  push    r12
0x18008a031  push    r13
0x18008a033  push    r14
0x18008a035  push    r15
0x18008a037  sub     rsp, 58h
0x18008a03b  mov     r15, [rsp+98h+arg_20]
0x18008a043  lea     rcx, [rax-50h]; lpSystemTimeAsFileTime
0x18008a047  xor     ebx, ebx
0x18008a049  mov     esi, r8d
0x18008a04c  mov     [rax-50h], rbx
0x18008a050  call    cs:__imp_GetSystemTimeAsFileTime
0x18008a057  nop     dword ptr [rax+rax+00h]
0x18008a05c  lea     rcx, ?LsapSidCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008a063  call    cs:__imp_RtlEnterCriticalSection
0x18008a06a  nop     dword ptr [rax+rax+00h]
0x18008a06f  mov     [rsp+98h+var_54], ebx
0x18008a073  mov     r12d, ebx
0x18008a076  test    esi, esi
0x18008a078  jz      loc_18008A300
0x18008a07e  mov     edi, ebx
0x18008a080  lea     r13, [rdi+rdi*2]
0x18008a084  mov     [rsp+98h+var_58], bl
0x18008a088  mov     ecx, [r15+r13*8]
0x18008a08c  mov     dl, bl
0x18008a08e  lea     eax, [rcx-6]
0x18008a091  test    eax, 0FFFFFFFDh
0x18008a096  jz      short loc_18008A0A0
0x18008a098  mov     bpl, 1
0x18008a09b  cmp     ecx, 7
0x18008a09e  jnz     short loc_18008A0A3
0x18008a0a0  mov     bpl, bl
0x18008a0a3  mov     r14, rbx
0x18008a0a6  mov     rbx, cs:?LsapSidCache@@3PEAU_LSAP_DB_SID_CACHE_ENTRY@@EA; _LSAP_DB_SID_CACHE_ENTRY * LsapSidCache
0x18008a0ad  test    rbx, rbx
0x18008a0b0  jz      loc_18008A28D
0x18008a0b6  mov     r12, [rsp+98h+arg_0]
0x18008a0be  mov     rsi, rdi
0x18008a0c1  mov     edx, 31003h; dwCmpFlags
0x18008a0c6  add     rsi, rsi
0x18008a0c9  mov     rcx, [r12+rsi*8+8]
0x18008a0ce  movzx   eax, word ptr [r12+rsi*8]
0x18008a0d3  shr     eax, 1
0x18008a0d5  cmp     dword ptr [rbx+20h], 3
0x18008a0d9  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18008a0dd  mov     [rsp+98h+lpString2], rcx; lpString2
0x18008a0e2  mov     ecx, 409h; Locale
0x18008a0e7  jnz     short loc_18008A11A
0x18008a0e9  movzx   r9d, word ptr [rbx+30h]
0x18008a0ee  mov     r8, [rbx+38h]; lpString1
0x18008a0f2  shr     r9d, 1; cchCount1
0x18008a0f5  call    cs:__imp_CompareStringW
0x18008a0fc  nop     dword ptr [rax+rax+00h]
0x18008a101  cmp     eax, 2
0x18008a104  jnz     loc_18008A269
0x18008a10a  xor     eax, eax
0x18008a10c  test    bpl, bpl
0x18008a10f  jnz     loc_18008A198
0x18008a115  jmp     loc_18008A231
0x18008a11a  movzx   r9d, word ptr [rbx+10h]
0x18008a11f  mov     r8, [rbx+18h]; lpString1
0x18008a123  shr     r9d, 1; cchCount1
0x18008a126  call    cs:__imp_CompareStringW
0x18008a12d  nop     dword ptr [rax+rax+00h]
0x18008a132  test    bpl, bpl
0x18008a135  jz      loc_18008A1DB
0x18008a13b  cmp     eax, 2
0x18008a13e  jnz     loc_18008A269
0x18008a144  movsxd  rax, dword ptr [r15+r13*8+10h]
0x18008a149  movzx   r9d, word ptr [rbx+30h]
0x18008a14e  mov     r8, [rbx+38h]; lpString1
0x18008a152  shr     r9d, 1; cchCount1
0x18008a155  lea     rdx, [rax+rax*2]
0x18008a159  mov     rax, [rsp+98h+arg_18]
0x18008a161  mov     rcx, [rax+8]
0x18008a165  movzx   eax, word ptr [rcx+rdx*8]
0x18008a169  shr     eax, 1
0x18008a16b  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18008a16f  mov     rax, [rcx+rdx*8+8]
0x18008a174  mov     edx, 31003h; dwCmpFlags
0x18008a179  mov     ecx, 409h; Locale
0x18008a17e  mov     [rsp+98h+lpString2], rax; lpString2
0x18008a183  call    cs:__imp_CompareStringW
0x18008a18a  nop     dword ptr [rax+rax+00h]
0x18008a18f  cmp     eax, 2
0x18008a192  jnz     loc_18008A269
0x18008a198  mov     rdx, [r15+r13*8+8]; Sid2
0x18008a19d  mov     rcx, [rbx+8]; Sid1
0x18008a1a1  call    cs:__imp_RtlEqualSid
0x18008a1a8  nop     dword ptr [rax+rax+00h]
0x18008a1ad  test    al, al
0x18008a1af  jz      short loc_18008A22F
0x18008a1b1  mov     rcx, [rsp+98h+var_50]
0x18008a1b6  add     rcx, cs:?LsapSidCacheRefreshTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LsapSidCacheRefreshTime
0x18008a1bd  mov     [rbx+48h], rcx
0x18008a1c1  mov     rcx, [rsp+98h+var_50]
0x18008a1c6  add     rcx, cs:?LsapSidCacheExpiryTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LsapSidCacheExpiryTime
0x18008a1cd  mov     [rbx+40h], rcx
0x18008a1d1  mov     [rsp+98h+var_58], 1
0x18008a1d6  jmp     loc_18008A269
0x18008a1db  cmp     eax, 2
0x18008a1de  jnz     loc_18008A269
0x18008a1e4  mov     rcx, [rsp+98h+arg_8]
0x18008a1ec  xor     eax, eax
0x18008a1ee  cmp     [rcx+rsi*8], ax
0x18008a1f2  jz      short loc_18008A231
0x18008a1f4  movzx   eax, word ptr [rcx+rsi*8]
0x18008a1f8  mov     edx, 31003h; dwCmpFlags
0x18008a1fd  movzx   r9d, word ptr [rbx+30h]
0x18008a202  mov     r8, [rbx+38h]; lpString1
0x18008a206  shr     eax, 1
0x18008a208  mov     [rsp+98h+cchCount2], eax; cchCount2
0x18008a20c  mov     rax, [rcx+rsi*8+8]
0x18008a211  mov     ecx, 409h; Locale
0x18008a216  shr     r9d, 1; cchCount1
0x18008a219  mov     [rsp+98h+lpString2], rax; lpString2
0x18008a21e  call    cs:__imp_CompareStringW
0x18008a225  nop     dword ptr [rax+rax+00h]
0x18008a22a  cmp     eax, 2
0x18008a22d  jnz     short loc_18008A269
0x18008a22f  xor     eax, eax
0x18008a231  cmp     [rbx+64h], eax
0x18008a234  jnz     short loc_18008A269
0x18008a236  mov     rcx, rbx; struct _RTL_BALANCED_NODE *
0x18008a239  mov     rbx, [rbx]
0x18008a23c  test    r14, r14
0x18008a23f  jz      short loc_18008A24C
0x18008a241  mov     [r14], rbx
0x18008a244  mov     sil, al
0x18008a247  mov     rbx, r14
0x18008a24a  jmp     short loc_18008A256
0x18008a24c  mov     cs:?LsapSidCache@@3PEAU_LSAP_DB_SID_CACHE_ENTRY@@EA, rbx; _LSAP_DB_SID_CACHE_ENTRY * LsapSidCache
0x18008a253  mov     sil, 1
0x18008a256  mov     r14, rax
0x18008a259  call    ?LsapDbFreeCacheEntry@@YAXPEAU_LSAP_DB_SID_CACHE_ENTRY@@@Z; LsapDbFreeCacheEntry(_LSAP_DB_SID_CACHE_ENTRY *)
0x18008a25e  dec     cs:?LsapSidCacheCount@@3KA; ulong LsapSidCacheCount
0x18008a264  test    sil, sil
0x18008a267  jnz     short loc_18008A274
0x18008a269  test    rbx, rbx
0x18008a26c  jz      short loc_18008A27D
0x18008a26e  mov     r14, rbx
0x18008a271  mov     rbx, [rbx]
0x18008a274  test    rbx, rbx
0x18008a277  jnz     loc_18008A0BE
0x18008a27d  mov     r12d, [rsp+98h+var_54]
0x18008a282  mov     esi, [rsp+98h+arg_10]
0x18008a289  mov     dl, [rsp+98h+var_58]
0x18008a28d  xor     ebx, ebx
0x18008a28f  test    bpl, bpl
0x18008a292  jz      short loc_18008A2EC
0x18008a294  test    dl, dl
0x18008a296  jnz     short loc_18008A2EC
0x18008a298  movsxd  rax, dword ptr [r15+r13*8+10h]
0x18008a29d  lea     r8, [rdi+rdi*2]
0x18008a2a1  mov     r8d, [r15+r8*8]; enum _SID_NAME_USE
0x18008a2a5  mov     rdx, rdi
0x18008a2a8  shl     rdx, 4
0x18008a2ac  add     rdx, [rsp+98h+arg_0]; String1
0x18008a2b4  lea     rcx, [rax+rax*2]
0x18008a2b8  mov     [rsp+98h+var_68], rbx; struct _LSAP_DB_SID_CACHE_ENTRY **
0x18008a2bd  mov     rax, [rsp+98h+arg_18]
0x18008a2c5  mov     [rsp+98h+cchCount2], 1; unsigned int
0x18008a2cd  mov     rax, [rax+8]
0x18008a2d1  lea     r9, [rax+rcx*8]; struct _LSAPR_TRUST_INFORMATION *
0x18008a2d5  mov     eax, [r15+r13*8+14h]
0x18008a2da  lea     rcx, [rdi+rdi*2]
0x18008a2de  mov     dword ptr [rsp+98h+lpString2], eax; unsigned int
0x18008a2e2  mov     rcx, [r15+rcx*8+8]; Sid2
0x18008a2e7  call    ?LsapDbAddOneSidToCache@@YAJPEAXPEAU_UNICODE_STRING@@W4_SID_NAME_USE@@PEAU_LSAPR_TRUST_INFORMATION@@KKPEAPEAU_LSAP_DB_SID_CACHE_ENTRY@@@Z; LsapDbAddOneSidToCache(void *,_UNICODE_STRING *,_SID_NAME_USE,_LSAPR_TRUST_INFORMATION *,ulong,ulong,_LSAP_DB_SID_CACHE_ENTRY * *)
0x18008a2ec  inc     r12d
0x18008a2ef  inc     rdi
0x18008a2f2  mov     [rsp+98h+var_54], r12d
0x18008a2f7  cmp     r12d, esi
0x18008a2fa  jb      loc_18008A080
0x18008a300  lea     rcx, ?LsapSidCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008a307  call    cs:__imp_RtlLeaveCriticalSection
0x18008a30e  nop     dword ptr [rax+rax+00h]
0x18008a313  add     rsp, 58h
0x18008a317  pop     r15
0x18008a319  pop     r14
0x18008a31b  pop     r13
0x18008a31d  pop     r12
0x18008a31f  pop     rdi
0x18008a320  pop     rsi
0x18008a321  pop     rbp
0x18008a322  pop     rbx
0x18008a323  retn
```
