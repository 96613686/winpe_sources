# LsaDbrForestTrustFindMatch(void *,ulong,_UNICODE_STRING *,_UNICODE_STRING * *)

- ea: `0x18000d530`
- end: `0x18000d5d3`
- name: `?LsaDbrForestTrustFindMatch@@YAJPEAXKPEAU_UNICODE_STRING@@PEAPEAU1@@Z`
- size: `163`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _UNICODE_STRING *, struct _UNICODE_STRING **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d530`
- `0x180024da0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d54b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d54b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d576`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000d576`

## pseudocode

```c
__int64 __fastcall LsaDbrForestTrustFindMatch(
        void *a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING **a4)
{
  struct _UNICODE_STRING *v7; // rbp
  int Match; // eax
  struct _UNICODE_STRING *v10; // rcx
  unsigned int v11; // edi
  PSID Sid; // [rsp+20h] [rbp-38h] BYREF

  Sid = 0;
  v7 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
  if ( !v7 )
    return 3221225626LL;
  if ( !a2 )
  {
    if ( ConvertStringSidToSidW(a3->Buffer, &Sid) )
    {
      a3 = (struct _UNICODE_STRING *)Sid;
      goto LABEL_7;
    }
    a3 = 0;
  }
  Sid = a3;
LABEL_7:
  if ( a3 )
  {
    Match = LsaDbIForestTrustFindMatch(a2, a3, v7);
    v10 = 0;
    v11 = Match;
    if ( Match >= 0 )
      v10 = v7;
    *a4 = v10;
    a3 = (struct _UNICODE_STRING *)Sid;
  }
  else
  {
    v11 = -1073741811;
  }
  if ( !a2 )
    LocalFree(a3);
  return v11;
}

```

## disassembly

```asm
0x18000d530  push    rbx
0x18000d532  push    rbp
0x18000d533  push    rsi
0x18000d534  push    rdi
0x18000d535  push    r14
0x18000d537  sub     rsp, 30h
0x18000d53b  mov     esi, edx
0x18000d53d  mov     r14, r9
0x18000d540  mov     edx, 10h; uBytes
0x18000d545  mov     rbx, r8
0x18000d548  lea     ecx, [rdx+30h]; uFlags
0x18000d54b  call    cs:__imp_LocalAlloc
0x18000d551  mov     [rsp+58h+Sid], 0
0x18000d55a  mov     rbp, rax
0x18000d55d  test    rax, rax
0x18000d560  jnz     short loc_18000D569
0x18000d562  mov     eax, 0C000009Ah
0x18000d567  jmp     short loc_18000D5C8
0x18000d569  test    esi, esi
0x18000d56b  jnz     short loc_18000D582
0x18000d56d  mov     rcx, [rbx+8]; StringSid
0x18000d571  lea     rdx, [rsp+58h+Sid]; Sid
0x18000d576  call    cs:__imp_ConvertStringSidToSidW
0x18000d57c  test    eax, eax
0x18000d57e  jnz     short loc_18000D5AD
0x18000d580  xor     ebx, ebx
0x18000d582  mov     [rsp+58h+Sid], rbx
0x18000d587  test    rbx, rbx
0x18000d58a  jz      short loc_18000D5B4
0x18000d58c  mov     r8, rbp
0x18000d58f  mov     rdx, rbx
0x18000d592  mov     ecx, esi
0x18000d594  call    ?LsaDbIForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXPEAU_UNICODE_STRING@@@Z; LsaDbIForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,_UNICODE_STRING *)
0x18000d599  xor     ecx, ecx
0x18000d59b  mov     edi, eax
0x18000d59d  test    eax, eax
0x18000d59f  cmovns  rcx, rbp
0x18000d5a3  mov     [r14], rcx
0x18000d5a6  mov     rbx, [rsp+58h+Sid]
0x18000d5ab  jmp     short loc_18000D5B9
0x18000d5ad  mov     rbx, [rsp+58h+Sid]
0x18000d5b2  jmp     short loc_18000D587
0x18000d5b4  mov     edi, 0C000000Dh
0x18000d5b9  test    esi, esi
0x18000d5bb  jnz     short loc_18000D5C6
0x18000d5bd  mov     rcx, rbx; hMem
0x18000d5c0  call    cs:__imp_LocalFree
0x18000d5c6  mov     eax, edi
0x18000d5c8  add     rsp, 30h
0x18000d5cc  pop     r14
0x18000d5ce  pop     rdi
0x18000d5cf  pop     rsi
0x18000d5d0  pop     rbp
0x18000d5d1  pop     rbx
0x18000d5d2  retn
```
