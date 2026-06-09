# LsaDbpLookupProcessWorkItem(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)

- ea: `0x1800333f0`
- end: `0x18003387d`
- name: `?LsaDbpLookupProcessWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(struct _LSAP_DB_LOOKUP_WORK_LIST *, struct _LSAP_DB_LOOKUP_WORK_ITEM *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001b8dc`
- `0x180033abc`

## callees

- `0x18000fd40`
- `0x18001c088`
- `0x18002b63c`
- `0x18002c0f8`
- `0x180032d38`
- `0x180033144`
- `0x180033188`
- `0x1800333f0`
- `0x180033898`
- `0x180033cb8`
- `0x180033d1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033584`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003380b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003381a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033848`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800337fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003380b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003381a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033848`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033862`
- `LSASRV!LsaDbLookupSidChainRequest` at `0x1800334eb`
- `LSASRV!LsaDbLookupSidChainRequest` at `0x1800334eb`
- `LSASRV!LsapDbLookupNameChainRequest` at `0x180033641`
- `LSASRV!LsapDbLookupNameChainRequest` at `0x180033641`
- `ntdll!RtlLeaveCriticalSection` at `0x1800336d7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800337de`
- `ntdll!RtlLeaveCriticalSection` at `0x1800337eb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800336d7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800337de`
- `ntdll!RtlLeaveCriticalSection` at `0x1800337eb`
- `ntdll!RtlEnterCriticalSection` at `0x1800336b9`
- `ntdll!RtlEnterCriticalSection` at `0x1800336f3`
- `ntdll!RtlEnterCriticalSection` at `0x18003374f`
- `ntdll!RtlEnterCriticalSection` at `0x1800336b9`
- `ntdll!RtlEnterCriticalSection` at `0x1800336f3`
- `ntdll!RtlEnterCriticalSection` at `0x18003374f`
- `ntdll!NtSetEvent` at `0x180033777`
- `ntdll!NtSetEvent` at `0x180033777`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupProcessWorkItem(
        struct _LSAP_DB_LOOKUP_WORK_LIST *a1,
        struct _LSAP_DB_LOOKUP_WORK_ITEM *a2)
{
  __int64 v2; // rax
  int v3; // r15d
  struct _UNICODE_STRING *v4; // r13
  __int128 v7; // xmm0
  SIZE_T v8; // rdi
  _QWORD *v9; // r10
  __int64 i; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r14d
  bool v14; // zf
  unsigned int v15; // r13d
  __int64 v16; // r14
  struct _UNICODE_STRING *v17; // r15
  struct _UNICODE_STRING *v18; // rcx
  unsigned int *v19; // r8
  struct _UNICODE_STRING *v20; // rcx
  char v21; // al
  __int64 v22; // r14
  _BYTE *v23; // rax
  __int64 v24; // r8
  NTSTATUS v25; // r14d
  char v26; // si
  NTSTATUS v27; // edi
  NTSTATUS v28; // eax
  int v30; // [rsp+28h] [rbp-41h]
  HLOCAL v31; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL v32; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING *v33; // [rsp+50h] [rbp-19h]
  HLOCAL hMem; // [rsp+58h] [rbp-11h]
  _OWORD v35[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v36; // [rsp+80h] [rbp+17h]
  int v37; // [rsp+D0h] [rbp+67h] BYREF
  int v38; // [rsp+D8h] [rbp+6Fh]
  HLOCAL v39; // [rsp+E0h] [rbp+77h] BYREF
  HLOCAL v40; // [rsp+E8h] [rbp+7Fh]

  v2 = *((_QWORD *)a2 + 5);
  v3 = 0;
  v38 = 0;
  v4 = 0;
  v37 = 0;
  v36 = 0;
  v35[0] = 0;
  v39 = 0;
  v7 = *(_OWORD *)((char *)a2 + 24);
  v32 = 0;
  v31 = 0;
  v35[1] = v7;
  v40 = 0;
  *(_QWORD *)&v36 = v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids, a1, a2);
  v8 = *((unsigned int *)a2 + 13);
  if ( *((_DWORD *)a1 + 10) == 1 )
  {
    hMem = LocalAlloc(0x40u, 8LL * (unsigned int)v8);
    v9 = hMem;
    if ( hMem )
    {
      for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
        v9[i] = *(_QWORD *)(*((_QWORD *)a1 + 14) + 8LL * *(unsigned int *)(*((_QWORD *)a2 + 8) + 4 * i));
      v37 = 0;
      v13 = LsaDbLookupSidChainRequest(v35, (unsigned int)v8, v9, &v39, &v31, *((_DWORD *)a1 + 17), &v37);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, a1, a2, v8);
      if ( (int)(v13 + 0x80000000) < 0 || v13 == -1073741709 )
        LsaDbpLookupSidsUpdateTranslatedNames(
          a1,
          a2,
          (struct _LSA_TRANSLATED_NAME_EX *)v31,
          (struct _LSAPR_REFERENCED_DOMAIN_LIST *)v39);
      else
        v3 = v13;
    }
  }
  else
  {
    v14 = *((_DWORD *)a1 + 10) == 2;
    hMem = 0;
    if ( v14 )
    {
      v33 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 16 * v8);
      v4 = v33;
      if ( v33 )
      {
        v40 = LocalAlloc(0x40u, v8);
        if ( v40 )
        {
          v15 = 0;
          if ( (_DWORD)v8 )
          {
            v16 = 0;
            do
            {
              v17 = &v33[v16];
              *v17 = *(struct _UNICODE_STRING *)(*((_QWORD *)a1 + 14)
                                               + 16LL * *(unsigned int *)(*((_QWORD *)a2 + 8) + 4 * v16));
              if ( *((_DWORD *)a1 + 17) == 3
                && (unsigned int)LsaDbpLookupNameContainsDelimiter(v17, 0x40u, 0)
                && !(unsigned int)LsaDbpLookupNameContainsDelimiter(v18, (unsigned __int16)v19 + 92, v19) )
              {
                LsaDbpLookupConvertNameFormat(v20, 0x40u, 0x5Cu);
                v21 = 1;
              }
              else
              {
                v21 = 0;
              }
              ++v15;
              *((_BYTE *)v40 + v16++) = v21;
            }
            while ( v15 < (unsigned int)v8 );
          }
          v4 = v33;
          v30 = *((_DWORD *)a1 + 17);
          v37 = 0;
          v22 = 0;
          v3 = LsapDbLookupNameChainRequest(v35, (unsigned int)v8, v33, &v39, &v32, v30, &v37);
          if ( (_DWORD)v8 )
          {
            v23 = v40;
            do
            {
              if ( v23[v22] )
              {
                LsaDbpLookupConvertNameFormat(&v4[(unsigned int)v22], 0x5Cu, 0x40u);
                v23 = v40;
              }
              v22 = (unsigned int)(v22 + 1);
            }
            while ( (unsigned int)v22 < (unsigned int)v8 );
          }
          if ( (int)(v3 + 0x80000000) < 0 || v3 == -1073741709 )
          {
            LsaDbpLookupNamesUpdateTranslatedSids(
              a1,
              a2,
              (struct _LSAPR_TRANSLATED_SID_EX2 *)v32,
              (struct _LSAPR_REFERENCED_DOMAIN_LIST *)v39);
            v3 = v38;
          }
        }
      }
    }
  }
  do
  {
    if ( v3 < 0 && RtlEnterCriticalSection(&LookupWorkQueue) >= 0 )
    {
      if ( *((int *)a1 + 25) >= 0 )
        *((_DWORD *)a1 + 25) = -1073741428;
      RtlLeaveCriticalSection(&LookupWorkQueue);
    }
    *((_DWORD *)a2 + 4) = 3;
    LsaDbpUpdateMappedCountsWorkList(a1);
    v25 = RtlEnterCriticalSection(&LookupWorkQueue);
  }
  while ( v25 < 0 );
  ++*((_DWORD *)a1 + 15);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qql(*((_QWORD *)WPP_GLOBAL_Control + 2), *((unsigned int *)a1 + 15), v24, a1, a2, *((_DWORD *)a1 + 15));
  if ( *((_DWORD *)a1 + 9) != 3 && *((_DWORD *)a1 + 15) == *((_DWORD *)a1 + 14) )
  {
    *((_DWORD *)a1 + 9) = 3;
    v26 = 0;
    v27 = RtlEnterCriticalSection(&LookupWorkQueue);
    if ( v27 >= 0 )
    {
      v26 = 1;
      if ( *((int *)a1 + 8) < 0 || (v27 = -1073741480, *((_DWORD *)a1 + 15) == *((_DWORD *)a1 + 14)) )
      {
        v28 = NtSetEvent(*((HANDLE *)a1 + 13), 0);
        v27 = v28;
        if ( v28 < 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
          {
LABEL_50:
            if ( v26 )
              RtlLeaveCriticalSection(&LookupWorkQueue);
            goto LABEL_52;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
            (unsigned int)v28);
        }
      }
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_Dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids,
        (unsigned int)v27);
    goto LABEL_50;
  }
LABEL_52:
  RtlLeaveCriticalSection(&LookupWorkQueue);
  if ( hMem )
    LocalFree(hMem);
  if ( v4 )
    LocalFree(v4);
  if ( v39 )
  {
    LocalFree(v39);
    v39 = 0;
  }
  if ( v31 )
  {
    LocalFree(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    LocalFree(v32);
    v32 = 0;
  }
  if ( v40 )
    LocalFree(v40);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800333f0  push    rbp
0x1800333f2  push    rbx
0x1800333f3  push    rsi
0x1800333f4  push    rdi
0x1800333f5  push    r13
0x1800333f7  push    r14
0x1800333f9  push    r15
0x1800333fb  lea     rbp, [rsp-27h]
0x180033400  sub     rsp, 90h
0x180033407  mov     rax, [rdx+28h]
0x18003340b  xor     r15d, r15d
0x18003340e  xorps   xmm0, xmm0
0x180033411  mov     [rbp+57h+arg_8], r15d
0x180033415  xor     r13d, r13d
0x180033418  mov     [rbp+57h+arg_0], r15d
0x18003341c  movups  [rbp+57h+var_40], xmm0
0x180033420  mov     rsi, rdx
0x180033423  mov     rbx, rcx
0x180033426  movups  [rbp+57h+var_60], xmm0
0x18003342a  mov     [rbp+57h+arg_10], r15
0x18003342e  movups  xmm0, xmmword ptr [rdx+18h]
0x180033432  mov     [rbp+57h+var_78], r13
0x180033436  mov     [rbp+57h+var_80], r13
0x18003343a  movdqu  [rbp+57h+var_50], xmm0
0x18003343f  mov     [rbp+57h+arg_18], r13
0x180033443  mov     qword ptr [rbp+57h+var_40], rax
0x180033447  mov     rcx, cs:WPP_GLOBAL_Control
0x18003344e  test    byte ptr [rcx+1Ch], 20h
0x180033452  jz      short loc_180033470
0x180033454  mov     rcx, [rcx+10h]
0x180033458  lea     edx, [r15+12h]
0x18003345c  mov     r9, rbx
0x18003345f  mov     [rsp+0C0h+var_A0], rsi
0x180033464  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x18003346b  call    WPP_SF_qq
0x180033470  cmp     dword ptr [rbx+28h], 1
0x180033474  mov     edi, [rsi+34h]
0x180033477  jnz     loc_18003354C
0x18003347d  mov     edx, edi
0x18003347f  mov     ecx, 40h ; '@'; uFlags
0x180033484  shl     rdx, 3; uBytes
0x180033488  call    cs:__imp_LocalAlloc
0x18003348e  mov     [rbp+57h+hMem], rax
0x180033492  mov     r10, rax
0x180033495  test    rax, rax
0x180033498  jz      loc_1800336AD
0x18003349e  xor     r8d, r8d
0x1800334a1  test    edi, edi
0x1800334a3  jz      short loc_1800334C1
0x1800334a5  mov     rax, [rsi+40h]
0x1800334a9  mov     ecx, [rax+r8*4]
0x1800334ad  mov     rax, [rbx+70h]
0x1800334b1  mov     rcx, [rax+rcx*8]
0x1800334b5  mov     [r10+r8*8], rcx
0x1800334b9  inc     r8d
0x1800334bc  cmp     r8d, edi
0x1800334bf  jb      short loc_1800334A5
0x1800334c1  lea     rax, [rbp+57h+arg_0]
0x1800334c5  mov     [rbp+57h+arg_0], r13d
0x1800334c9  mov     [rsp+0C0h+var_90], rax
0x1800334ce  lea     r9, [rbp+57h+arg_10]
0x1800334d2  mov     eax, [rbx+44h]
0x1800334d5  lea     rcx, [rbp+57h+var_60]
0x1800334d9  mov     [rsp+0C0h+var_98], eax
0x1800334dd  mov     r8, r10
0x1800334e0  lea     rax, [rbp+57h+var_80]
0x1800334e4  mov     edx, edi
0x1800334e6  mov     [rsp+0C0h+var_A0], rax
0x1800334eb  call    cs:__imp_LsaDbLookupSidChainRequest
0x1800334f1  mov     r14d, eax
0x1800334f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334fb  test    byte ptr [rcx+1Ch], 20h
0x1800334ff  jz      short loc_180033516
0x180033501  mov     rcx, [rcx+10h]
0x180033505  mov     r9, rbx
0x180033508  mov     [rsp+0C0h+var_98], edi
0x18003350c  mov     [rsp+0C0h+var_A0], rsi
0x180033511  call    WPP_SF_qqD
0x180033516  mov     ecx, 80000000h
0x18003351b  lea     eax, [r14+rcx]
0x18003351f  test    ecx, eax
0x180033521  jnz     short loc_180033534
0x180033523  cmp     r14d, 0C0000073h
0x18003352a  jz      short loc_180033534
0x18003352c  mov     r15d, r14d
0x18003352f  jmp     loc_1800336AD
0x180033534  mov     r9, [rbp+57h+arg_10]; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x180033538  mov     rdx, rsi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18003353b  mov     r8, [rbp+57h+var_80]; struct _LSA_TRANSLATED_NAME_EX *
0x18003353f  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x180033542  call    ?LsaDbpLookupSidsUpdateTranslatedNames@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSA_TRANSLATED_NAME_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@@Z; LsaDbpLookupSidsUpdateTranslatedNames(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *,_LSA_TRANSLATED_NAME_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *)
0x180033547  jmp     loc_1800336AD
0x18003354c  cmp     dword ptr [rbx+28h], 2
0x180033550  mov     [rbp+57h+hMem], r13
0x180033554  jnz     loc_1800336AD
0x18003355a  mov     rdx, rdi
0x18003355d  mov     ecx, 40h ; '@'; uFlags
0x180033562  shl     rdx, 4; uBytes
0x180033566  call    cs:__imp_LocalAlloc
0x18003356c  mov     [rbp+57h+var_70], rax
0x180033570  mov     r13, rax
0x180033573  test    rax, rax
0x180033576  jz      loc_1800336AD
0x18003357c  mov     rdx, rdi; uBytes
0x18003357f  mov     ecx, 40h ; '@'; uFlags
0x180033584  call    cs:__imp_LocalAlloc
0x18003358a  mov     [rbp+57h+arg_18], rax
0x18003358e  test    rax, rax
0x180033591  jz      loc_1800336AD
0x180033597  xor     r13d, r13d
0x18003359a  test    edi, edi
0x18003359c  jz      short loc_180033610
0x18003359e  xor     r14d, r14d
0x1800335a1  mov     rax, [rsi+40h]
0x1800335a5  mov     r15, r14
0x1800335a8  shl     r15, 4
0x1800335ac  add     r15, [rbp+57h+var_70]
0x1800335b0  mov     ecx, [rax+r14*4]
0x1800335b4  mov     rax, [rbx+70h]
0x1800335b8  add     rcx, rcx
0x1800335bb  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800335bf  movdqu  xmmword ptr [r15], xmm0
0x1800335c4  cmp     dword ptr [rbx+44h], 3
0x1800335c8  jnz     short loc_1800335FB
0x1800335ca  mov     edx, 40h ; '@'; unsigned __int16
0x1800335cf  xor     r8d, r8d; unsigned int *
0x1800335d2  mov     rcx, r15; struct _UNICODE_STRING *
0x1800335d5  call    ?LsaDbpLookupNameContainsDelimiter@@YAHPEAU_UNICODE_STRING@@GPEAK@Z; LsaDbpLookupNameContainsDelimiter(_UNICODE_STRING *,ushort,ulong *)
0x1800335da  test    eax, eax
0x1800335dc  jz      short loc_1800335FB
0x1800335de  lea     edx, [r8+5Ch]; unsigned __int16
0x1800335e2  call    ?LsaDbpLookupNameContainsDelimiter@@YAHPEAU_UNICODE_STRING@@GPEAK@Z; LsaDbpLookupNameContainsDelimiter(_UNICODE_STRING *,ushort,ulong *)
0x1800335e7  test    eax, eax
0x1800335e9  jnz     short loc_1800335FB
0x1800335eb  lea     edx, [rax+40h]; unsigned __int16
0x1800335ee  lea     r8d, [rax+5Ch]; unsigned __int16
0x1800335f2  call    ?LsaDbpLookupConvertNameFormat@@YAXPEAU_UNICODE_STRING@@GG@Z; LsaDbpLookupConvertNameFormat(_UNICODE_STRING *,ushort,ushort)
0x1800335f7  mov     al, 1
0x1800335f9  jmp     short loc_1800335FD
0x1800335fb  xor     al, al
0x1800335fd  mov     rcx, [rbp+57h+arg_18]
0x180033601  inc     r13d
0x180033604  mov     [rcx+r14], al
0x180033608  inc     r14
0x18003360b  cmp     r13d, edi
0x18003360e  jb      short loc_1800335A1
0x180033610  mov     r13, [rbp+57h+var_70]
0x180033614  lea     rax, [rbp+57h+arg_0]
0x180033618  mov     [rsp+0C0h+var_90], rax
0x18003361d  lea     r9, [rbp+57h+arg_10]
0x180033621  mov     eax, [rbx+44h]
0x180033624  lea     rcx, [rbp+57h+var_60]
0x180033628  mov     [rsp+0C0h+var_98], eax
0x18003362c  mov     r8, r13
0x18003362f  lea     rax, [rbp+57h+var_78]
0x180033633  mov     [rbp+57h+arg_0], 0
0x18003363a  mov     edx, edi
0x18003363c  mov     [rsp+0C0h+var_A0], rax
0x180033641  call    cs:__imp_LsapDbLookupNameChainRequest
0x180033647  xor     r14d, r14d
0x18003364a  mov     r15d, eax
0x18003364d  test    edi, edi
0x18003364f  jz      short loc_180033680
0x180033651  mov     rax, [rbp+57h+arg_18]
0x180033655  cmp     byte ptr [r14+rax], 0
0x18003365a  mov     ecx, r14d
0x18003365d  jz      short loc_180033678
0x18003365f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180033664  shl     rcx, 4
0x180033668  add     rcx, r13; struct _UNICODE_STRING *
0x18003366b  lea     r8d, [rdx-1Ch]; unsigned __int16
0x18003366f  call    ?LsaDbpLookupConvertNameFormat@@YAXPEAU_UNICODE_STRING@@GG@Z; LsaDbpLookupConvertNameFormat(_UNICODE_STRING *,ushort,ushort)
0x180033674  mov     rax, [rbp+57h+arg_18]
0x180033678  inc     r14d
0x18003367b  cmp     r14d, edi
0x18003367e  jb      short loc_180033655
0x180033680  mov     ecx, 80000000h
0x180033685  lea     eax, [r15+rcx]
0x180033689  test    ecx, eax
0x18003368b  jnz     short loc_180033696
0x18003368d  cmp     r15d, 0C0000073h
0x180033694  jnz     short loc_1800336AD
0x180033696  mov     r9, [rbp+57h+arg_10]; struct _LSAPR_REFERENCED_DOMAIN_LIST *
0x18003369a  mov     rdx, rsi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18003369d  mov     r8, [rbp+57h+var_78]; struct _LSAPR_TRANSLATED_SID_EX2 *
0x1800336a1  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x1800336a4  call    ?LsaDbpLookupNamesUpdateTranslatedSids@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@PEAU_LSAPR_TRANSLATED_SID_EX2@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@@Z; LsaDbpLookupNamesUpdateTranslatedSids(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *,_LSAPR_TRANSLATED_SID_EX2 *,_LSAPR_REFERENCED_DOMAIN_LIST *)
0x1800336a9  mov     r15d, [rbp+57h+arg_8]
0x1800336ad  test    r15d, r15d
0x1800336b0  jns     short loc_1800336DD
0x1800336b2  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800336b9  call    cs:__imp_RtlEnterCriticalSection
0x1800336bf  test    eax, eax
0x1800336c1  js      short loc_1800336DD
0x1800336c3  cmp     dword ptr [rbx+64h], 0
0x1800336c7  jl      short loc_1800336D0
0x1800336c9  mov     dword ptr [rbx+64h], 0C000018Ch
0x1800336d0  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800336d7  call    cs:__imp_RtlLeaveCriticalSection
0x1800336dd  mov     rcx, rbx; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x1800336e0  mov     dword ptr [rsi+10h], 3
0x1800336e7  call    ?LsaDbpUpdateMappedCountsWorkList@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpUpdateMappedCountsWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x1800336ec  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800336f3  call    cs:__imp_RtlEnterCriticalSection
0x1800336f9  mov     r14d, eax
0x1800336fc  test    eax, eax
0x1800336fe  js      short loc_1800336AD
0x180033700  inc     dword ptr [rbx+3Ch]
0x180033703  mov     edx, [rbx+3Ch]
0x180033706  mov     rcx, cs:WPP_GLOBAL_Control
0x18003370d  test    byte ptr [rcx+1Ch], 20h
0x180033711  jz      short loc_180033728
0x180033713  mov     rcx, [rcx+10h]
0x180033717  mov     r9, rbx
0x18003371a  mov     [rsp+0C0h+var_98], edx
0x18003371e  mov     [rsp+0C0h+var_A0], rsi
0x180033723  call    WPP_SF_qql
0x180033728  cmp     dword ptr [rbx+24h], 3
0x18003372c  jz      loc_1800337E4
0x180033732  mov     eax, [rbx+38h]
0x180033735  cmp     [rbx+3Ch], eax
0x180033738  jnz     loc_1800337E4
0x18003373e  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x180033745  mov     dword ptr [rbx+24h], 3
0x18003374c  xor     sil, sil
0x18003374f  call    cs:__imp_RtlEnterCriticalSection
0x180033755  mov     edi, eax
0x180033757  test    eax, eax
0x180033759  js      short loc_1800337A8
0x18003375b  cmp     dword ptr [rbx+20h], 0
0x18003375f  mov     sil, 1
0x180033762  jl      short loc_180033771
0x180033764  mov     eax, [rbx+38h]
0x180033767  mov     edi, 0C0000158h
0x18003376c  cmp     [rbx+3Ch], eax
0x18003376f  jnz     short loc_1800337A8
0x180033771  mov     rcx, [rbx+68h]; EventHandle
0x180033775  xor     edx, edx; PreviousState
0x180033777  call    cs:__imp_NtSetEvent
0x18003377d  mov     edi, eax
0x18003377f  test    eax, eax
0x180033781  jns     short loc_1800337A8
0x180033783  mov     rcx, cs:WPP_GLOBAL_Control
0x18003378a  test    byte ptr [rcx+1Ch], 20h
0x18003378e  jz      short loc_1800337D2
0x180033790  mov     rcx, [rcx+10h]
0x180033794  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x18003379b  mov     edx, 0Dh
0x1800337a0  mov     r9d, eax
0x1800337a3  call    WPP_SF_d
0x1800337a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800337af  test    byte ptr [rcx+1Ch], 20h
0x1800337b3  jz      short loc_1800337D2
0x1800337b5  mov     rcx, [rcx+10h]
0x1800337b9  lea     r8, WPP_8a52dcb151a73685fc4479e4bb277ef7_Traceguids
0x1800337c0  mov     edx, 0Eh
0x1800337c5  mov     [rsp+0C0h+var_A0], rbx
0x1800337ca  mov     r9d, edi
0x1800337cd  call    WPP_SF_Dq
0x1800337d2  test    sil, sil
0x1800337d5  jz      short loc_1800337E4
0x1800337d7  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800337de  call    cs:__imp_RtlLeaveCriticalSection
0x1800337e4  lea     rcx, ?LookupWorkQueue@@3U_LSAP_DB_LOOKUP_WORK_QUEUE@@A; CriticalSection
0x1800337eb  call    cs:__imp_RtlLeaveCriticalSection
0x1800337f1  mov     rax, [rbp+57h+hMem]
0x1800337f5  test    rax, rax
0x1800337f8  jz      short loc_180033803
0x1800337fa  mov     rcx, rax; hMem
0x1800337fd  call    cs:__imp_LocalFree
0x180033803  test    r13, r13
0x180033806  jz      short loc_180033811
0x180033808  mov     rcx, r13; hMem
0x18003380b  call    cs:__imp_LocalFree
0x180033811  mov     rcx, [rbp+57h+arg_10]; hMem
0x180033815  test    rcx, rcx
0x180033818  jz      short loc_180033828
0x18003381a  call    cs:__imp_LocalFree
0x180033820  mov     [rbp+57h+arg_10], 0
0x180033828  mov     rcx, [rbp+57h+var_80]; hMem
0x18003382c  test    rcx, rcx
0x18003382f  jz      short loc_18003383F
0x180033831  call    cs:__imp_LocalFree
0x180033837  mov     [rbp+57h+var_80], 0
0x18003383f  mov     rcx, [rbp+57h+var_78]; hMem
0x180033843  test    rcx, rcx
0x180033846  jz      short loc_180033856
0x180033848  call    cs:__imp_LocalFree
0x18003384e  mov     [rbp+57h+var_78], 0
0x180033856  mov     rax, [rbp+57h+arg_18]
0x18003385a  test    rax, rax
0x18003385d  jz      short loc_180033868
0x18003385f  mov     rcx, rax; hMem
0x180033862  call    cs:__imp_LocalFree
0x180033868  mov     eax, r14d
0x18003386b  add     rsp, 90h
0x180033872  pop     r15
0x180033874  pop     r14
0x180033876  pop     r13
0x180033878  pop     rdi
  ... truncated ...
```
