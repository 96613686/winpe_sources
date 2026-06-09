# std::_Tree<std::_Tmap_traits<SidHandle,ulong,CSidSorter,std::allocator<std::pair<SidHandle const,ulong>>,0>>::_Find_lower_bound<SidHandle>(SidHandle const &)

- ea: `0x18003df90`
- end: `0x18003e0e7`
- name: `??$_Find_lower_bound@VSidHandle@@@?$_Tree@V?$_Tmap_traits@VSidHandle@@KVCSidSorter@@V?$allocator@U?$pair@$$CBVSidHandle@@K@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVSidHandle@@K@std@@PEAX@std@@@1@AEBVSidHandle@@@Z`
- size: `343`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, PSID *)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036504`
- `0x18003dd08`
- `0x180090978`
- `0x180090a10`
- `0x180093b14`
- `0x180097b8c`

## callees

- `0x18003df90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e056`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e065`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e0b2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e0c1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e056`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e065`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e0b2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003e0c1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003dffe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e00a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e01a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e026`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e03d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003dffe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e00a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e01a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e026`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003e03d`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<SidHandle,unsigned long,CSidSorter,std::allocator<std::pair<SidHandle const,unsigned long>>,0>>::_Find_lower_bound<SidHandle>(
        __int64 a1,
        _QWORD *a2,
        PSID *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  PSID v7; // rbp
  PSID v8; // r14
  PUCHAR SidSubAuthorityCount; // rdi
  PUCHAR v10; // rdi
  UCHAR i; // r12
  PDWORD SidSubAuthority; // rdi
  int v13; // eax
  PDWORD v15; // rdi

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (PSID)v6[4];
    v8 = *a3;
    if ( v7 && v8 )
    {
      SidSubAuthorityCount = GetSidSubAuthorityCount(*a3);
      if ( *GetSidSubAuthorityCount(v7) >= *SidSubAuthorityCount )
      {
        v10 = GetSidSubAuthorityCount(v8);
        if ( *GetSidSubAuthorityCount(v7) <= *v10 )
        {
          for ( i = 0; i < *GetSidSubAuthorityCount(v7); ++i )
          {
            SidSubAuthority = GetSidSubAuthority(v8, i);
            if ( *GetSidSubAuthority(v7, i) < *SidSubAuthority )
              goto LABEL_9;
            v15 = GetSidSubAuthority(v8, i);
            if ( *GetSidSubAuthority(v7, i) > *v15 )
              break;
          }
        }
LABEL_13:
        a2[2] = v6;
        v13 = 1;
        goto LABEL_10;
      }
    }
    else if ( (__int64)v7 >= (__int64)v8 )
    {
      goto LABEL_13;
    }
LABEL_9:
    v6 += 2;
    v13 = 0;
LABEL_10:
    *((_DWORD *)a2 + 2) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x18003df90  push    rbx
0x18003df92  push    rsi
0x18003df93  push    r15
0x18003df95  sub     rsp, 30h
0x18003df99  mov     rax, [rcx]
0x18003df9c  mov     r15, r8
0x18003df9f  mov     rsi, rdx
0x18003dfa2  mov     r9, [rax+8]
0x18003dfa6  mov     [rdx], r9
0x18003dfa9  mov     rbx, r9
0x18003dfac  mov     qword ptr [rdx+8], 0
0x18003dfb4  mov     rax, [rcx]
0x18003dfb7  mov     [rdx+10h], rax
0x18003dfbb  cmp     byte ptr [r9+19h], 0
0x18003dfc0  jnz     loc_18003E0A0
0x18003dfc6  mov     [rsp+48h+arg_0], rbp
0x18003dfcb  mov     [rsp+48h+arg_8], rdi
0x18003dfd0  mov     [rsp+48h+arg_10], r12
0x18003dfd5  mov     [rsp+48h+var_20], r13
0x18003dfda  mov     [rsp+48h+var_28], r14
0x18003dfdf  mov     [rsi], rbx
0x18003dfe2  mov     rbp, [rbx+20h]
0x18003dfe6  mov     r14, [r15]
0x18003dfe9  test    rbp, rbp
0x18003dfec  jz      loc_18003E0E0
0x18003dff2  test    r14, r14
0x18003dff5  jz      loc_18003E0E0
0x18003dffb  mov     rcx, r14; pSid
0x18003dffe  call    cs:__imp_GetSidSubAuthorityCount
0x18003e004  mov     rcx, rbp; pSid
0x18003e007  mov     rdi, rax
0x18003e00a  call    cs:__imp_GetSidSubAuthorityCount
0x18003e010  movzx   ecx, byte ptr [rdi]
0x18003e013  cmp     [rax], cl
0x18003e015  jb      short loc_18003E071
0x18003e017  mov     rcx, r14; pSid
0x18003e01a  call    cs:__imp_GetSidSubAuthorityCount
0x18003e020  mov     rcx, rbp; pSid
0x18003e023  mov     rdi, rax
0x18003e026  call    cs:__imp_GetSidSubAuthorityCount
0x18003e02c  movzx   ecx, byte ptr [rdi]
0x18003e02f  cmp     [rax], cl
0x18003e031  ja      loc_18003E0CD
0x18003e037  xor     r12b, r12b
0x18003e03a  mov     rcx, rbp; pSid
0x18003e03d  call    cs:__imp_GetSidSubAuthorityCount
0x18003e043  cmp     r12b, [rax]
0x18003e046  jnb     loc_18003E0CD
0x18003e04c  movzx   r13d, r12b
0x18003e050  mov     rcx, r14; pSid
0x18003e053  mov     edx, r13d; nSubAuthority
0x18003e056  call    cs:__imp_GetSidSubAuthority
0x18003e05c  mov     edx, r13d; nSubAuthority
0x18003e05f  mov     rcx, rbp; pSid
0x18003e062  mov     rdi, rax
0x18003e065  call    cs:__imp_GetSidSubAuthority
0x18003e06b  mov     ecx, [rdi]
0x18003e06d  cmp     [rax], ecx
0x18003e06f  jnb     short loc_18003E0AC
0x18003e071  add     rbx, 10h
0x18003e075  xor     eax, eax
0x18003e077  mov     [rsi+8], eax
0x18003e07a  mov     rbx, [rbx]
0x18003e07d  cmp     byte ptr [rbx+19h], 0
0x18003e081  jz      loc_18003DFDF
0x18003e087  mov     r14, [rsp+48h+var_28]
0x18003e08c  mov     r13, [rsp+48h+var_20]
0x18003e091  mov     r12, [rsp+48h+arg_10]
0x18003e096  mov     rdi, [rsp+48h+arg_8]
0x18003e09b  mov     rbp, [rsp+48h+arg_0]
0x18003e0a0  mov     rax, rsi
0x18003e0a3  add     rsp, 30h
0x18003e0a7  pop     r15
0x18003e0a9  pop     rsi
0x18003e0aa  pop     rbx
0x18003e0ab  retn
0x18003e0ac  mov     edx, r13d; nSubAuthority
0x18003e0af  mov     rcx, r14; pSid
0x18003e0b2  call    cs:__imp_GetSidSubAuthority
0x18003e0b8  mov     edx, r13d; nSubAuthority
0x18003e0bb  mov     rcx, rbp; pSid
0x18003e0be  mov     rdi, rax
0x18003e0c1  call    cs:__imp_GetSidSubAuthority
0x18003e0c7  mov     ecx, [rdi]
0x18003e0c9  cmp     [rax], ecx
0x18003e0cb  jbe     short loc_18003E0D8
0x18003e0cd  mov     [rsi+10h], rbx
0x18003e0d1  mov     eax, 1
0x18003e0d6  jmp     short loc_18003E077
0x18003e0d8  inc     r12b
0x18003e0db  jmp     loc_18003E03A
0x18003e0e0  cmp     rbp, r14
0x18003e0e3  jge     short loc_18003E0CD
0x18003e0e5  jmp     short loc_18003E071
```
