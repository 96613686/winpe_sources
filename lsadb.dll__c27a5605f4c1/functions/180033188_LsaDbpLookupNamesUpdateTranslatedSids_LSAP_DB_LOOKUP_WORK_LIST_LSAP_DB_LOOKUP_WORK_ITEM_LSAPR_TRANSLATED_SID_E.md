# LsaDbpLookupNamesUpdateTranslatedSids(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *,_LSAPR_TRANSLATED_SID_EX2 *,_LSAPR_REFERENCED_DOMAIN_LIST *)

- ea: `0x180033188`
- end: `0x1800333e7`
- name: `?LsaDbpLookupNamesUpdateTranslatedSids@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSAPR_TRANSLATED_SID_EX2@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *, struct _LSAP_DB_LOOKUP_WORK_ITEM *, struct _LSAPR_TRANSLATED_SID_EX2 *, struct _LSAPR_REFERENCED_DOMAIN_LIST *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800333f0`

## callees

- `0x18000c8ec`
- `0x18000fd40`
- `0x18000fee8`
- `0x180033188`

## import_xrefs

- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x180033354`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x180033354`
- `LSASRV!LsapRpcCopySid` at `0x180033399`
- `LSASRV!LsapRpcCopySid` at `0x180033399`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x1800331c3`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x1800331c3`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800333c7`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800333c7`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180033319`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180033319`
- `ntdll!RtlLeaveCriticalSection` at `0x1800333c1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800333c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800331da`
- `ntdll!RtlEnterCriticalSection` at `0x1800331da`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesUpdateTranslatedSids(
        struct _LSAP_DB_LOOKUP_WORK_LIST *a1,
        struct _LSAP_DB_LOOKUP_WORK_ITEM *a2,
        struct _LSAPR_TRANSLATED_SID_EX2 *a3,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a4)
{
  struct _LSAP_DB_LOOKUP_WORK_LIST *v6; // r12
  NTSTATUS LockTrustedDomainList; // ebx
  __int64 v8; // rcx
  __int64 i; // r15
  __int64 v10; // r9
  __int64 v11; // r14
  __int64 v12; // r13
  char *v13; // r12
  void *v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r14
  int v19; // [rsp+40h] [rbp-48h] BYREF
  int v20; // [rsp+44h] [rbp-44h] BYREF
  __int64 v21; // [rsp+48h] [rbp-40h]

  v19 = 0;
  v6 = a1;
  v21 = *(_QWORD *)(*((_QWORD *)a1 + 15) + 8LL);
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(a1);
  if ( LockTrustedDomainList >= 0 )
  {
    LockTrustedDomainList = RtlEnterCriticalSection(&LookupWorkQueue);
    if ( LockTrustedDomainList >= 0 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 13); i = (unsigned int)(i + 1) )
      {
        v10 = *((unsigned int *)a3 + 6 * i + 4);
        if ( (_DWORD)v10 != -1 || *((_DWORD *)a3 + 6 * i) != 8 )
        {
          v11 = *(unsigned int *)(*((_QWORD *)a2 + 8) + 4 * i);
          v12 = 3 * v11;
          if ( *(_DWORD *)(v21 + 24 * v11) == 8 )
          {
            if ( (_DWORD)v10 == -1 || (unsigned int)v10 < *(_DWORD *)a4 )
            {
              if ( (*((_BYTE *)a2 + 20) & 2) != 0 )
              {
                v13 = (char *)a3 + 24 * i;
                v14 = (void *)*((_QWORD *)v13 + 1);
                if ( v14 )
                {
                  v20 = 0;
                  v15 = LsaDbpSidOnFtInfo((PCUNICODE_STRING)((char *)a2 + 24), v14);
                  v20 = v15;
                  if ( v15 < 0 )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        22,
                        &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
                        (unsigned int)v15);
                    if ( LsapLookupLogLevel )
                      SpmpEventWrite(
                        (const struct _EVENT_DESCRIPTOR *)LSAEVENT_LOOKUP_SID_FILTERED,
                        L"usub",
                        *((_QWORD *)a1 + 14) + 16 * v11,
                        v13 + 8,
                        (char *)a2 + 24,
                        4,
                        &v20);
                    goto LABEL_24;
                  }
                }
                v6 = a1;
              }
              v16 = *((int *)a3 + 6 * i + 4);
              if ( (_DWORD)v16 == -1 )
              {
                v19 = -1;
              }
              else
              {
                LockTrustedDomainList = LsapDbLookupAddListReferencedDomains(
                                          *((_QWORD *)v6 + 9),
                                          *((_QWORD *)a4 + 1) + 24 * v16,
                                          &v19);
                if ( LockTrustedDomainList < 0 )
                  break;
              }
              v17 = v21;
              *(_OWORD *)(v21 + 8 * v12) = *(_OWORD *)((char *)a3 + 24 * i);
              *(_QWORD *)(v17 + 8 * v12 + 16) = *((_QWORD *)a3 + 3 * i + 2);
              *(_DWORD *)(v17 + 8 * v12 + 16) = v19;
              LockTrustedDomainList = LsapRpcCopySid(0, v17 + 8 + 8 * v12, *((_QWORD *)a3 + 3 * i + 1), v10);
              if ( LockTrustedDomainList < 0 )
                break;
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
                v10,
                *(_DWORD *)a4);
            }
          }
        }
LABEL_24:
        v6 = a1;
      }
      RtlLeaveCriticalSection(&LookupWorkQueue);
    }
    LsapDbExpReleaseLockTrustedDomainList(v8);
  }
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x180033188  mov     rax, rsp
0x18003318b  mov     [rax+10h], rbx
0x18003318f  mov     [rax+20h], r9
0x180033193  mov     [rax+8], rcx
0x180033197  push    rbp
0x180033198  push    rsi
0x180033199  push    rdi
0x18003319a  push    r12
0x18003319c  push    r13
0x18003319e  push    r14
0x1800331a0  push    r15
0x1800331a2  sub     rsp, 50h
0x1800331a6  mov     dword ptr [rax-48h], 0
0x1800331ad  mov     rsi, r8
0x1800331b0  mov     rax, [rcx+78h]
0x1800331b4  mov     rbp, rdx
0x1800331b7  mov     r12, rcx
0x1800331ba  mov     rax, [rax+8]
0x1800331be  mov     [rsp+88h+var_40], rax
0x1800331c3  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x1800331c9  mov     ebx, eax
0x1800331cb  test    eax, eax
0x1800331cd  js      loc_1800333CD
0x1800331d3  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800331da  call    cs:__imp_RtlEnterCriticalSection
0x1800331e0  mov     ebx, eax
0x1800331e2  test    eax, eax
0x1800331e4  js      loc_1800333C7
0x1800331ea  xor     r15d, r15d
0x1800331ed  cmp     [rbp+34h], r15d
0x1800331f1  jbe     loc_1800333BA
0x1800331f7  lea     rdi, [r15+r15*2]
0x1800331fb  mov     r9d, [rsi+rdi*8+10h]
0x180033200  cmp     r9d, 0FFFFFFFFh
0x180033204  jnz     short loc_180033210
0x180033206  cmp     dword ptr [rsi+rdi*8], 8
0x18003320a  jz      loc_1800333A5
0x180033210  mov     rax, [rbp+40h]
0x180033214  mov     r14d, [rax+r15*4]
0x180033218  mov     rax, [rsp+88h+var_40]
0x18003321d  lea     r13, [r14+r14*2]
0x180033221  cmp     dword ptr [rax+r13*8], 8
0x180033226  jnz     loc_1800333A5
0x18003322c  cmp     r9d, 0FFFFFFFFh
0x180033230  jz      short loc_180033270
0x180033232  mov     rax, [rsp+88h+arg_18]
0x18003323a  mov     eax, [rax]
0x18003323c  cmp     r9d, eax
0x18003323f  jb      short loc_180033270
0x180033241  mov     rcx, cs:WPP_GLOBAL_Control
0x180033248  test    byte ptr [rcx+1Ch], 20h
0x18003324c  jz      loc_1800333A5
0x180033252  mov     rcx, [rcx+10h]
0x180033256  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x18003325d  mov     edx, 15h
0x180033262  mov     dword ptr [rsp+88h+var_68], eax
0x180033266  call    WPP_SF_dd
0x18003326b  jmp     loc_1800333A5
0x180033270  test    byte ptr [rbp+14h], 2
0x180033274  jz      loc_18003332C
0x18003327a  lea     r12, [rsi+rdi*8]
0x18003327e  mov     rdx, [r12+8]; void *
0x180033283  test    rdx, rdx
0x180033286  jz      loc_180033324
0x18003328c  lea     rcx, [rbp+18h]; String1
0x180033290  mov     [rsp+88h+var_44], 0
0x180033298  call    ?LsaDbpSidOnFtInfo@@YAJPEAU_UNICODE_STRING@@PEAX@Z; LsaDbpSidOnFtInfo(_UNICODE_STRING *,void *)
0x18003329d  mov     [rsp+88h+var_44], eax
0x1800332a1  test    eax, eax
0x1800332a3  jns     short loc_180033324
0x1800332a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332ac  test    byte ptr [rcx+1Ch], 20h
0x1800332b0  jz      short loc_1800332CA
0x1800332b2  mov     rcx, [rcx+10h]
0x1800332b6  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x1800332bd  mov     edx, 16h
0x1800332c2  mov     r9d, eax
0x1800332c5  call    WPP_SF_d
0x1800332ca  cmp     cs:?LsapLookupLogLevel@@3KA, 1; ulong LsapLookupLogLevel
0x1800332d1  jb      loc_1800333A5
0x1800332d7  mov     rax, [rsp+88h+arg_0]
0x1800332df  lea     r9, [r12+8]
0x1800332e4  shl     r14, 4
0x1800332e8  lea     rdx, aUsub; "usub"
0x1800332ef  lea     rcx, LSAEVENT_LOOKUP_SID_FILTERED
0x1800332f6  add     r14, [rax+70h]
0x1800332fa  lea     rax, [rsp+88h+var_44]
0x1800332ff  mov     [rsp+88h+var_58], rax
0x180033304  mov     r8, r14
0x180033307  lea     rax, [rbp+18h]
0x18003330b  mov     [rsp+88h+var_60], 4
0x180033314  mov     [rsp+88h+var_68], rax
0x180033319  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x18003331f  jmp     loc_1800333A5
0x180033324  mov     r12, [rsp+88h+arg_0]
0x18003332c  movsxd  rax, dword ptr [rsi+rdi*8+10h]
0x180033331  cmp     eax, 0FFFFFFFFh
0x180033334  jz      short loc_180033362
0x180033336  lea     rcx, [rax+rax*2]
0x18003333a  mov     rax, [rsp+88h+arg_18]
0x180033342  lea     r8, [rsp+88h+var_48]
0x180033347  mov     rax, [rax+8]
0x18003334b  lea     rdx, [rax+rcx*8]
0x18003334f  mov     rcx, [r12+48h]
0x180033354  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x18003335a  mov     ebx, eax
0x18003335c  test    eax, eax
0x18003335e  js      short loc_1800333BA
0x180033360  jmp     short loc_180033366
0x180033362  mov     [rsp+88h+var_48], eax
0x180033366  mov     r14, [rsp+88h+var_40]
0x18003336b  xor     ecx, ecx
0x18003336d  movups  xmm0, xmmword ptr [rsi+rdi*8]
0x180033371  movups  xmmword ptr [r14+r13*8], xmm0
0x180033376  lea     rdx, [r14+8]
0x18003337a  movsd   xmm1, qword ptr [rsi+rdi*8+10h]
0x180033380  lea     rdx, [rdx+r13*8]
0x180033384  movsd   qword ptr [r14+r13*8+10h], xmm1
0x18003338b  mov     eax, [rsp+88h+var_48]
0x18003338f  mov     [r14+r13*8+10h], eax
0x180033394  mov     r8, [rsi+rdi*8+8]
0x180033399  call    cs:__imp_LsapRpcCopySid
0x18003339f  mov     ebx, eax
0x1800333a1  test    eax, eax
0x1800333a3  js      short loc_1800333BA
0x1800333a5  mov     r12, [rsp+88h+arg_0]
0x1800333ad  inc     r15d
0x1800333b0  cmp     r15d, [rbp+34h]
0x1800333b4  jb      loc_1800331F7
0x1800333ba  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800333c1  call    cs:__imp_RtlLeaveCriticalSection
0x1800333c7  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x1800333cd  mov     eax, ebx
0x1800333cf  mov     rbx, [rsp+88h+arg_8]
0x1800333d7  add     rsp, 50h
0x1800333db  pop     r15
0x1800333dd  pop     r14
0x1800333df  pop     r13
0x1800333e1  pop     r12
0x1800333e3  pop     rdi
0x1800333e4  pop     rsi
0x1800333e5  pop     rbp
0x1800333e6  retn
```
