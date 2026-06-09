# KerbFreeLogonSession(_KERB_LOGON_SESSION *)

- ea: `0x18000a650`
- end: `0x18000aa6e`
- name: `?KerbFreeLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z`
- size: `1054`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `11`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000951c`
- `0x1800097b0`
- `0x18000a630`
- `0x18000b5c0`
- `0x18003a1f0`
- `0x180049400`
- `0x18004f220`
- `0x180058590`
- `0x18005a360`
- `0x18005a3d0`
- `0x18005dbf0`

## callees

- `0x18000a650`
- `0x18002a20c`
- `0x18006517c`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a95e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a7ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a95e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa47`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a868`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a9f5`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a9ff`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a868`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a9f5`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000a9ff`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000a9a9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000a9a9`
- `ntdll!RtlReleaseResource` at `0x18000aa1c`
- `ntdll!RtlReleaseResource` at `0x18000aa1c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a859`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000a859`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a819`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a826`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a830`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a819`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a826`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a830`
- `ntdll!RtlEnterCriticalSection` at `0x18000a747`
- `ntdll!RtlEnterCriticalSection` at `0x18000a747`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a75b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a80a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a75b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a80a`

## string_xrefs

- `0x18000a9b7`: `KerbAgeProcessTable deleted pin kdc entry %p for LUID %#x:%x\n`

## pseudocode

```c
void __fastcall KerbFreeLogonSession(char *hMem)
{
  void *v2; // rcx
  void **v3; // rdi
  void *v4; // rbx
  void **v5; // rax
  void **v6; // rcx
  bool v7; // zf
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rbp
  _DWORD *v12; // r15
  _QWORD *v13; // rbx
  _QWORD *i; // r14
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  _DWORD *v17; // rax
  _QWORD *v18; // rsi
  void *v19; // rcx
  void *v20; // rcx
  _QWORD *v21; // rax

  KerbTracerT::Log(
    10,
    "KerbFreeLogonSession",
    614,
    "FREE logonsess %p for %#x:%#x\n",
    (const void *)WORD1(hMem),
    *((_DWORD *)hMem + 17),
    *((_DWORD *)hMem + 16));
  KerbFreeExtraCredList((struct _EXTRA_CRED_LIST *)(hMem + 840));
  KerbFreePrimaryCredentials((struct _KERB_PRIMARY_CREDENTIAL *)(hMem + 120), 0);
  v2 = (void *)*((_QWORD *)hMem + 88);
  if ( v2 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v2);
  }
  v3 = (void **)(hMem + 8);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    v5 = *(void ***)v4;
    if ( *(_QWORD *)v4 && (v6 = (void **)*((_QWORD *)v4 + 1)) != 0 )
    {
      if ( v5[1] != v4 || *v6 != v4 )
LABEL_68:
        __fastfail(3u);
      *v6 = v5;
      v5[1] = v6;
      *(_QWORD *)v4 = 0;
      *((_QWORD *)v4 + 1) = 0;
    }
    else
    {
      ++*((_DWORD *)v4 + 4);
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 24));
    v7 = (*((_DWORD *)v4 + 4))-- == 1;
    v8 = (struct _RTL_CRITICAL_SECTION *)(hMem + 24);
    if ( v7 )
    {
      RtlLeaveCriticalSection(v8);
      KerbFreePrimaryCredentials(*((struct _KERB_PRIMARY_CREDENTIAL **)v4 + 8), 1u);
      if ( v4 != (void *)-48LL )
      {
        v9 = (void *)*((_QWORD *)v4 + 7);
        if ( v9 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(v9);
        }
        *((_OWORD *)v4 + 3) = 0;
      }
      if ( v4 != (void *)-32LL )
      {
        v10 = (void *)*((_QWORD *)v4 + 5);
        if ( v10 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (*)(void))LsaFunctions->FreeLsaHeap)();
          else
            LocalFree(v10);
        }
        *((_OWORD *)v4 + 2) = 0;
      }
      if ( KerbGlobalPackageState == 1 )
        ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v4);
      else
        LocalFree(v4);
    }
    else
    {
      RtlLeaveCriticalSection(v8);
    }
  }
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 24));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 856));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)hMem + 2);
  if ( hMem[920] && KerbGlobalProcessTableInitialized )
  {
    RtlAcquireResourceExclusive(&KerbGlobalProcessTableLock, 1u);
    v11 = RtlEnumerateGenericTableAvl(&KerbGlobalProcessTable, 1u);
    if ( v11 )
    {
      v12 = hMem + 68;
      do
      {
        v13 = (_QWORD *)v11[1];
        for ( i = v11 + 1; v13 != i; v13 = (_QWORD *)*v13 )
        {
          if ( *((_DWORD *)v13 + 7) == *v12 && *((_DWORD *)v13 + 6) == *((_DWORD *)hMem + 16) )
          {
            v15 = (_QWORD *)*v13;
            v16 = (_QWORD *)v13[1];
            if ( *v13 && v16 )
            {
              if ( (_QWORD *)v15[1] != v13 || (_QWORD *)*v16 != v13 )
                goto LABEL_68;
              *v16 = v15;
              v15[1] = v16;
              v17 = v13 + 2;
              *v13 = 0;
              v13[1] = 0;
            }
            else
            {
              ++*((_DWORD *)v13 + 4);
              v17 = v13 + 2;
            }
            v7 = (*v17)-- == 1;
            v18 = v13;
            v13 = v16;
            if ( v7 )
            {
              if ( v18 != (_QWORD *)-40LL )
              {
                v19 = (void *)v18[6];
                if ( v19 )
                {
                  if ( KerbGlobalPackageState == 1 )
                    ((void (*)(void))LsaFunctions->FreeLsaHeap)();
                  else
                    LocalFree(v19);
                }
                *(_OWORD *)(v18 + 5) = 0;
              }
              if ( v18 != (_QWORD *)-56LL )
              {
                v20 = (void *)v18[8];
                if ( v20 )
                {
                  if ( KerbGlobalPackageState == 1 )
                    ((void (*)(void))LsaFunctions->FreeLsaHeap)();
                  else
                    LocalFree(v20);
                }
                *(_OWORD *)(v18 + 7) = 0;
              }
              if ( KerbGlobalPackageState == 1 )
                ((void (__fastcall *)(_QWORD *))LsaFunctions->FreeLsaHeap)(v18);
              else
                LocalFree(v18);
            }
          }
        }
        if ( (_QWORD *)*i == i )
        {
          if ( !RtlDeleteElementGenericTableAvl(&KerbGlobalProcessTable, v11) )
            break;
          KerbTracerT::Log(
            22,
            "KerbAgeProcessTable",
            1815,
            "KerbAgeProcessTable deleted pin kdc entry %p for LUID %#x:%x\n",
            (const void *)WORD1(v11),
            *v12,
            *((_DWORD *)hMem + 16));
          v21 = RtlEnumerateGenericTableAvl(&KerbGlobalProcessTable, 1u);
        }
        else
        {
          v21 = RtlEnumerateGenericTableAvl(&KerbGlobalProcessTable, 0);
          v12 = hMem + 68;
        }
        v11 = v21;
      }
      while ( v21 );
    }
    RtlReleaseResource(&KerbGlobalProcessTableLock);
  }
  if ( KerbGlobalPackageState == 1 )
    ((void (__fastcall *)(char *))LsaFunctions->FreeLsaHeap)(hMem);
  else
    LocalFree(hMem);
}

```

## disassembly

```asm
0x18000a650  push    rbx
0x18000a652  push    rbp
0x18000a653  push    rdi
0x18000a654  push    r12
0x18000a656  push    r13
0x18000a658  sub     rsp, 40h
0x18000a65c  mov     rax, rcx
0x18000a65f  lea     r9, aFreeLogonsessP; "FREE logonsess %p for %#x:%#x\n"
0x18000a666  shr     rax, 10h
0x18000a66a  mov     r13, rcx
0x18000a66d  movzx   edx, ax
0x18000a670  mov     r8d, 266h
0x18000a676  mov     eax, [rcx+40h]
0x18000a679  mov     [rsp+68h+var_38], eax
0x18000a67d  mov     eax, [rcx+44h]
0x18000a680  mov     ecx, 0Ah
0x18000a685  mov     [rsp+68h+var_40], eax
0x18000a689  mov     [rsp+68h+var_48], rdx
0x18000a68e  lea     rdx, aKerbfreelogons; "KerbFreeLogonSession"
0x18000a695  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000a69a  lea     rcx, [r13+348h]; struct _EXTRA_CRED_LIST *
0x18000a6a1  call    ?KerbFreeExtraCredList@@YAXPEAU_EXTRA_CRED_LIST@@@Z; KerbFreeExtraCredList(_EXTRA_CRED_LIST *)
0x18000a6a6  lea     rcx, [r13+78h]; this
0x18000a6aa  xor     edx, edx; unsigned __int8
0x18000a6ac  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x18000a6b1  mov     rcx, [r13+2C0h]; hMem
0x18000a6b8  test    rcx, rcx
0x18000a6bb  jz      short loc_18000A6DE
0x18000a6bd  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a6c4  jnz     short loc_18000A6D8
0x18000a6c6  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a6cd  mov     rax, [rax+30h]
0x18000a6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d6  jmp     short loc_18000A6DE
0x18000a6d8  call    cs:__imp_LocalFree
0x18000a6de  mov     [rsp+68h+arg_8], rsi
0x18000a6e3  lea     rdi, [r13+8]
0x18000a6e7  mov     [rsp+68h+arg_10], r14
0x18000a6ef  xor     r12d, r12d
0x18000a6f2  mov     [rsp+68h+arg_18], r15
0x18000a6fa  nop     word ptr [rax+rax+00h]
0x18000a700  mov     rbx, [rdi]
0x18000a703  cmp     rbx, rdi
0x18000a706  jz      loc_18000A815
0x18000a70c  mov     rax, [rbx]
0x18000a70f  test    rax, rax
0x18000a712  jz      short loc_18000A740
0x18000a714  mov     rcx, [rbx+8]
0x18000a718  test    rcx, rcx
0x18000a71b  jz      short loc_18000A740
0x18000a71d  cmp     [rax+8], rbx
0x18000a721  jnz     loc_18000AA40
0x18000a727  cmp     [rcx], rbx
0x18000a72a  jnz     loc_18000AA40
0x18000a730  mov     [rcx], rax
0x18000a733  mov     [rax+8], rcx
0x18000a737  mov     [rbx], r12
0x18000a73a  mov     [rbx+8], r12
0x18000a73e  jmp     short loc_18000A743
0x18000a740  inc     dword ptr [rbx+10h]
0x18000a743  lea     rcx, [rdi+10h]; CriticalSection
0x18000a747  call    cs:__imp_RtlEnterCriticalSection
0x18000a74d  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x18000a751  lea     rcx, [rdi+10h]; CriticalSection
0x18000a755  jnz     loc_18000A80A
0x18000a75b  call    cs:__imp_RtlLeaveCriticalSection
0x18000a761  mov     rcx, [rbx+40h]; this
0x18000a765  mov     dl, 1; unsigned __int8
0x18000a767  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x18000a76c  lea     rsi, [rbx+30h]
0x18000a770  test    rsi, rsi
0x18000a773  jz      short loc_18000A7A5
0x18000a775  mov     rcx, [rsi+8]; hMem
0x18000a779  test    rcx, rcx
0x18000a77c  jz      short loc_18000A79F
0x18000a77e  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a785  jnz     short loc_18000A799
0x18000a787  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a78e  mov     rax, [rax+30h]
0x18000a792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a797  jmp     short loc_18000A79F
0x18000a799  call    cs:__imp_LocalFree
0x18000a79f  xorps   xmm0, xmm0
0x18000a7a2  movups  xmmword ptr [rsi], xmm0
0x18000a7a5  lea     rsi, [rbx+20h]
0x18000a7a9  test    rsi, rsi
0x18000a7ac  jz      short loc_18000A7DE
0x18000a7ae  mov     rcx, [rsi+8]; hMem
0x18000a7b2  test    rcx, rcx
0x18000a7b5  jz      short loc_18000A7D8
0x18000a7b7  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a7be  jnz     short loc_18000A7D2
0x18000a7c0  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a7c7  mov     rax, [rax+30h]
0x18000a7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d0  jmp     short loc_18000A7D8
0x18000a7d2  call    cs:__imp_LocalFree
0x18000a7d8  xorps   xmm0, xmm0
0x18000a7db  movups  xmmword ptr [rsi], xmm0
0x18000a7de  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a7e5  mov     rcx, rbx; hMem
0x18000a7e8  jnz     short loc_18000A7FF
0x18000a7ea  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a7f1  mov     rax, [rax+30h]
0x18000a7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7fa  jmp     loc_18000A700
0x18000a7ff  call    cs:__imp_LocalFree
0x18000a805  jmp     loc_18000A700
0x18000a80a  call    cs:__imp_RtlLeaveCriticalSection
0x18000a810  jmp     loc_18000A700
0x18000a815  lea     rcx, [rdi+10h]; CriticalSection
0x18000a819  call    cs:__imp_RtlDeleteCriticalSection
0x18000a81f  lea     rcx, [r13+358h]; CriticalSection
0x18000a826  call    cs:__imp_RtlDeleteCriticalSection
0x18000a82c  lea     rcx, [r13+50h]; CriticalSection
0x18000a830  call    cs:__imp_RtlDeleteCriticalSection
0x18000a836  cmp     [r13+398h], r12b
0x18000a83d  jz      loc_18000AA22
0x18000a843  cmp     cs:?KerbGlobalProcessTableInitialized@@3EA, r12b; uchar KerbGlobalProcessTableInitialized
0x18000a84a  jz      loc_18000AA22
0x18000a850  mov     dl, 1; Wait
0x18000a852  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18000a859  call    cs:__imp_RtlAcquireResourceExclusive
0x18000a85f  mov     dl, 1; Restart
0x18000a861  lea     rcx, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; Table
0x18000a868  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000a86e  mov     rbp, rax
0x18000a871  test    rax, rax
0x18000a874  jz      loc_18000AA15
0x18000a87a  lea     r15, [r13+44h]
0x18000a87e  xchg    ax, ax
0x18000a880  mov     rbx, [rbp+8]
0x18000a884  lea     r14, [rbp+8]
0x18000a888  cmp     rbx, r14
0x18000a88b  jz      loc_18000A99A
0x18000a891  mov     eax, [r15]
0x18000a894  cmp     [rbx+1Ch], eax
0x18000a897  jnz     loc_18000A98E
0x18000a89d  mov     eax, [r13+40h]
0x18000a8a1  cmp     [rbx+18h], eax
0x18000a8a4  jnz     loc_18000A98E
0x18000a8aa  mov     rax, [rbx]
0x18000a8ad  mov     rcx, [rbx+8]
0x18000a8b1  test    rax, rax
0x18000a8b4  jz      short loc_18000A8E2
0x18000a8b6  test    rcx, rcx
0x18000a8b9  jz      short loc_18000A8E2
0x18000a8bb  cmp     [rax+8], rbx
0x18000a8bf  jnz     loc_18000AA40
0x18000a8c5  cmp     [rcx], rbx
0x18000a8c8  jnz     loc_18000AA40
0x18000a8ce  mov     [rcx], rax
0x18000a8d1  mov     [rax+8], rcx
0x18000a8d5  lea     rax, [rbx+10h]
0x18000a8d9  mov     [rbx], r12
0x18000a8dc  mov     [rbx+8], r12
0x18000a8e0  jmp     short loc_18000A8E9
0x18000a8e2  inc     dword ptr [rbx+10h]
0x18000a8e5  lea     rax, [rbx+10h]
0x18000a8e9  add     dword ptr [rax], 0FFFFFFFFh
0x18000a8ec  mov     rsi, rbx
0x18000a8ef  mov     rbx, rcx
0x18000a8f2  jnz     loc_18000A98E
0x18000a8f8  lea     rdi, [rsi+28h]
0x18000a8fc  test    rdi, rdi
0x18000a8ff  jz      short loc_18000A931
0x18000a901  mov     rcx, [rdi+8]; hMem
0x18000a905  test    rcx, rcx
0x18000a908  jz      short loc_18000A92B
0x18000a90a  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a911  jnz     short loc_18000A925
0x18000a913  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a91a  mov     rax, [rax+30h]
0x18000a91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a923  jmp     short loc_18000A92B
0x18000a925  call    cs:__imp_LocalFree
0x18000a92b  xorps   xmm0, xmm0
0x18000a92e  movups  xmmword ptr [rdi], xmm0
0x18000a931  lea     rdi, [rsi+38h]
0x18000a935  test    rdi, rdi
0x18000a938  jz      short loc_18000A96A
0x18000a93a  mov     rcx, [rdi+8]; hMem
0x18000a93e  test    rcx, rcx
0x18000a941  jz      short loc_18000A964
0x18000a943  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a94a  jnz     short loc_18000A95E
0x18000a94c  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a953  mov     rax, [rax+30h]
0x18000a957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95c  jmp     short loc_18000A964
0x18000a95e  call    cs:__imp_LocalFree
0x18000a964  xorps   xmm0, xmm0
0x18000a967  movups  xmmword ptr [rdi], xmm0
0x18000a96a  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000a971  mov     rcx, rsi; hMem
0x18000a974  jnz     short loc_18000A988
0x18000a976  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000a97d  mov     rax, [rax+30h]
0x18000a981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a986  jmp     short loc_18000A98E
0x18000a988  call    cs:__imp_LocalFree
0x18000a98e  mov     rbx, [rbx]
0x18000a991  cmp     rbx, r14
0x18000a994  jnz     loc_18000A891
0x18000a99a  lea     rcx, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; Table
0x18000a9a1  cmp     [r14], r14
0x18000a9a4  jnz     short loc_18000A9FD
0x18000a9a6  mov     rdx, rbp; Buffer
0x18000a9a9  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000a9af  test    al, al
0x18000a9b1  jz      short loc_18000AA15
0x18000a9b3  mov     eax, [r13+40h]
0x18000a9b7  lea     r9, aKerbageprocess_0; "KerbAgeProcessTable deleted pin kdc ent"...
0x18000a9be  mov     [rsp+68h+var_38], eax
0x18000a9c2  lea     rdx, aKerbageprocess; "KerbAgeProcessTable"
0x18000a9c9  mov     eax, [r15]
0x18000a9cc  mov     r8d, 717h
0x18000a9d2  mov     [rsp+68h+var_40], eax
0x18000a9d6  shr     rbp, 10h
0x18000a9da  movzx   ecx, bp
0x18000a9dd  mov     [rsp+68h+var_48], rcx
0x18000a9e2  mov     ecx, 16h
0x18000a9e7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000a9ec  mov     dl, 1; Restart
0x18000a9ee  lea     rcx, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; Table
0x18000a9f5  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000a9fb  jmp     short loc_18000AA09
0x18000a9fd  xor     edx, edx; Restart
0x18000a9ff  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000aa05  lea     r15, [r13+44h]
0x18000aa09  mov     rbp, rax
0x18000aa0c  test    rax, rax
0x18000aa0f  jnz     loc_18000A880
0x18000aa15  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18000aa1c  call    cs:__imp_RtlReleaseResource
0x18000aa22  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18000aa29  mov     rcx, r13; hMem
0x18000aa2c  jnz     short loc_18000AA47
0x18000aa2e  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18000aa35  mov     rax, [rax+30h]
0x18000aa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3e  jmp     short loc_18000AA4D
0x18000aa40  mov     ecx, 3
0x18000aa45  int     29h; Win8: RtlFailFast(ecx)
0x18000aa47  call    cs:__imp_LocalFree
0x18000aa4d  mov     r15, [rsp+68h+arg_18]
0x18000aa55  mov     r14, [rsp+68h+arg_10]
0x18000aa5d  mov     rsi, [rsp+68h+arg_8]
0x18000aa62  add     rsp, 40h
0x18000aa66  pop     r13
0x18000aa68  pop     r12
0x18000aa6a  pop     rdi
0x18000aa6b  pop     rbp
0x18000aa6c  pop     rbx
0x18000aa6d  retn
```
