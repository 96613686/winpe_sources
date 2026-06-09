# LsaDbpLookupSidsUpdateTranslatedNames(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *,_LSA_TRANSLATED_NAME_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *)

- ea: `0x180033898`
- end: `0x1800339cb`
- name: `?LsaDbpLookupSidsUpdateTranslatedNames@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSA_TRANSLATED_NAME_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *, struct _LSAP_DB_LOOKUP_WORK_ITEM *, struct _LSA_TRANSLATED_NAME_EX *, struct _LSAPR_REFERENCED_DOMAIN_LIST *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800333f0`

## callees

- `0x180033898`

## import_xrefs

- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18003393e`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18003393e`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x180033979`
- `LSASRV!LsapRpcCopyUnicodeString` at `0x180033979`
- `ntdll!RtlLeaveCriticalSection` at `0x1800339ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800339ae`
- `ntdll!RtlEnterCriticalSection` at `0x1800338cb`
- `ntdll!RtlEnterCriticalSection` at `0x1800338cb`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsUpdateTranslatedNames(
        struct _LSAP_DB_LOOKUP_WORK_LIST *a1,
        struct _LSAP_DB_LOOKUP_WORK_ITEM *a2,
        struct _LSA_TRANSLATED_NAME_EX *a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4)
{
  __int64 v6; // r12
  NTSTATUS v7; // edi
  __int64 i; // r14
  __int64 v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r13
  int v14; // eax
  __int64 v15; // rcx
  int v17[18]; // [rsp+20h] [rbp-48h] BYREF

  v6 = *(_QWORD *)(*((_QWORD *)a1 + 15) + 8LL);
  v7 = RtlEnterCriticalSection(&LookupWorkQueue);
  if ( v7 >= 0 )
  {
    for ( i = 0;
          (unsigned int)i < *((_DWORD *)a2 + 13);
          *(_DWORD *)(32LL * *(unsigned int *)(*((_QWORD *)a2 + 8) + v9) + v6 + 28) = *(_DWORD *)((char *)a3 + v10 + 28) )
    {
      v9 = 4 * i;
      v10 = 32LL * (unsigned int)i;
      if ( *(_DWORD *)((char *)a3 + v10) != 8 )
      {
        v11 = *((_QWORD *)a2 + 8);
        v12 = *(int *)((char *)a3 + v10 + 24);
        v17[0] = 0;
        v13 = *(unsigned int *)(v9 + v11);
        if ( (_DWORD)v12 == -1 )
        {
          v17[0] = -1;
        }
        else
        {
          v7 = LsapDbLookupAddListReferencedDomains(*((_QWORD *)a1 + 9), *((_QWORD *)a4 + 1) + 24 * v12, v17);
          if ( v7 < 0 )
            break;
          LODWORD(v12) = v17[0];
        }
        v14 = *(_DWORD *)((char *)a3 + v10);
        v15 = 32 * v13;
        *(_DWORD *)(v15 + v6 + 24) = v12;
        *(_DWORD *)(v15 + v6) = v14;
        v7 = LsapRpcCopyUnicodeString(0, 32 * v13 + v6 + 8, (char *)a3 + v10 + 8);
        if ( v7 < 0 )
          break;
      }
      i = (unsigned int)(i + 1);
    }
    RtlLeaveCriticalSection(&LookupWorkQueue);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033898  mov     [rsp+arg_8], rbx
0x18003389d  mov     [rsp+arg_18], r9
0x1800338a2  mov     [rsp+arg_0], rcx
0x1800338a7  push    rbp
0x1800338a8  push    rsi
0x1800338a9  push    rdi
0x1800338aa  push    r12
0x1800338ac  push    r13
0x1800338ae  push    r14
0x1800338b0  push    r15
0x1800338b2  sub     rsp, 30h
0x1800338b6  mov     rax, [rcx+78h]
0x1800338ba  mov     r15, r8
0x1800338bd  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800338c4  mov     rbp, rdx
0x1800338c7  mov     r12, [rax+8]
0x1800338cb  call    cs:__imp_RtlEnterCriticalSection
0x1800338d1  mov     edi, eax
0x1800338d3  test    eax, eax
0x1800338d5  js      loc_1800339B4
0x1800338db  xor     r14d, r14d
0x1800338de  cmp     [rbp+34h], r14d
0x1800338e2  jbe     loc_1800339A7
0x1800338e8  mov     ebx, r14d
0x1800338eb  lea     rsi, ds:0[r14*4]
0x1800338f3  shl     rbx, 5
0x1800338f7  cmp     dword ptr [rbx+r15], 8
0x1800338fc  jz      loc_180033985
0x180033902  mov     rax, [rbp+40h]
0x180033906  movsxd  rdx, dword ptr [rbx+r15+18h]
0x18003390b  mov     [rsp+68h+var_48], 0
0x180033913  mov     r13d, [rsi+rax]
0x180033917  cmp     edx, 0FFFFFFFFh
0x18003391a  jz      short loc_180033950
0x18003391c  mov     rax, [rsp+68h+arg_18]
0x180033924  lea     rcx, [rdx+rdx*2]
0x180033928  lea     r8, [rsp+68h+var_48]
0x18003392d  mov     rax, [rax+8]
0x180033931  lea     rdx, [rax+rcx*8]
0x180033935  mov     rax, [rsp+68h+arg_0]
0x18003393a  mov     rcx, [rax+48h]
0x18003393e  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x180033944  mov     edi, eax
0x180033946  test    eax, eax
0x180033948  js      short loc_1800339A7
0x18003394a  mov     edx, [rsp+68h+var_48]
0x18003394e  jmp     short loc_180033954
0x180033950  mov     [rsp+68h+var_48], edx
0x180033954  mov     eax, [rbx+r15]
0x180033958  lea     r8, [r15+8]
0x18003395c  mov     rcx, r13
0x18003395f  add     r8, rbx
0x180033962  shl     rcx, 5
0x180033966  mov     [rcx+r12+18h], edx
0x18003396b  lea     rdx, [r12+8]
0x180033970  add     rdx, rcx
0x180033973  mov     [rcx+r12], eax
0x180033977  xor     ecx, ecx
0x180033979  call    cs:__imp_LsapRpcCopyUnicodeString
0x18003397f  mov     edi, eax
0x180033981  test    eax, eax
0x180033983  js      short loc_1800339A7
0x180033985  mov     rax, [rbp+40h]
0x180033989  inc     r14d
0x18003398c  mov     edx, [rax+rsi]
0x18003398f  mov     eax, [rbx+r15+1Ch]
0x180033994  shl     rdx, 5
0x180033998  mov     [rdx+r12+1Ch], eax
0x18003399d  cmp     r14d, [rbp+34h]
0x1800339a1  jb      loc_1800338E8
0x1800339a7  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800339ae  call    cs:__imp_RtlLeaveCriticalSection
0x1800339b4  mov     rbx, [rsp+68h+arg_8]
0x1800339b9  mov     eax, edi
0x1800339bb  add     rsp, 30h
0x1800339bf  pop     r15
0x1800339c1  pop     r14
0x1800339c3  pop     r13
0x1800339c5  pop     r12
0x1800339c7  pop     rdi
0x1800339c8  pop     rsi
0x1800339c9  pop     rbp
0x1800339ca  retn
```
