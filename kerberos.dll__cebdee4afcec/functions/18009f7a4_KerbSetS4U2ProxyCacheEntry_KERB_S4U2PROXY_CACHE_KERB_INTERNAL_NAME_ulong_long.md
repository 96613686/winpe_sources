# KerbSetS4U2ProxyCacheEntry(_KERB_S4U2PROXY_CACHE *,_KERB_INTERNAL_NAME *,ulong,long)

- ea: `0x18009f7a4`
- end: `0x18009fa41`
- name: `?KerbSetS4U2ProxyCacheEntry@@YAJPEAU_KERB_S4U2PROXY_CACHE@@PEAU_KERB_INTERNAL_NAME@@KJ@Z`
- size: `669`
- prototype: `int(struct _KERB_S4U2PROXY_CACHE *, struct _KERB_INTERNAL_NAME *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800566a8`

## callees

- `0x180031ef4`
- `0x18008b70c`
- `0x18009e040`
- `0x18009e254`
- `0x18009f7a4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009f7e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009f7e5`
- `ntdll!RtlAvlInsertNodeEx` at `0x18009f991`
- `ntdll!RtlAvlInsertNodeEx` at `0x18009f991`
- `ntdll!RtlReleaseResource` at `0x18009f93a`
- `ntdll!RtlReleaseResource` at `0x18009fa1f`
- `ntdll!RtlReleaseResource` at `0x18009f93a`
- `ntdll!RtlReleaseResource` at `0x18009fa1f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009f7f4`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009f7f4`

## string_xrefs

- `0x18009f8e5`: `Update S4U2Proxy cache entry %p for logon session %#x:%x, ServerName %wZ, Flags %#x, LastStatus %#x, Expiry %lld\n`
- `0x18009f922`: `KerbSetS4U2ProxyCacheEntry`
- `0x18009fa0c`: `KerbSetS4U2ProxyCacheEntry`
- `0x18009f911`: `KerbCreateS4U2ProxyCacheEntry failed: %#x\n`
- `0x18009f9b8`: `Create S4U2Proxy cache entry %p for logon session: %#x:%x, ServerName %wZ, Flags %#x, LastStatus %#x, Expiry %lld\n`

## pseudocode

```c
__int64 __fastcall KerbSetS4U2ProxyCacheEntry(
        struct _KERB_S4U2PROXY_CACHE *a1,
        struct _KERB_INTERNAL_NAME *a2,
        unsigned int a3,
        int a4)
{
  unsigned int v8; // r13d
  struct _KERB_S4U2PROXY_CACHE_ENTRY *v9; // r15
  struct _RTL_BALANCED_NODE **v10; // r14
  __int64 *v11; // rbx
  int v12; // eax
  struct _KERB_S4U2PROXY_CACHE *v13; // rax
  struct _KERB_S4U2PROXY_CACHE ***v14; // rcx
  __int64 v15; // rdx
  struct _KERB_S4U2PROXY_CACHE **v16; // r8
  struct _KERB_S4U2PROXY_CACHE **v17; // r8
  char *v18; // rcx
  __int64 v19; // r8
  int v20; // eax
  const char *v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // r8
  struct _RTL_BALANCED_NODE *v25; // rbx
  struct _KERB_S4U2PROXY_CACHE_ENTRY *v26; // rdi
  struct _RTL_BALANCED_NODE *v27; // rax
  struct _KERB_S4U2PROXY_CACHE **v28; // rdx
  int v30; // [rsp+48h] [rbp-70h]
  __int64 v31; // [rsp+50h] [rbp-68h]
  struct _KERB_S4U2PROXY_CACHE_ENTRY *v32; // [rsp+60h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-50h] BYREF

  SystemTimeAsFileTime = 0;
  v32 = 0;
  v8 = 0;
  v9 = 0;
  if ( !KerbGlobalS4UCacheTimeout.QuadPart )
    goto LABEL_35;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RtlAcquireResourceExclusive(&KerbGlobalS4U2ProxyCacheLock, 1u);
  if ( !*(_BYTE *)a1 )
    goto LABEL_34;
  v10 = (struct _RTL_BALANCED_NODE **)((char *)a1 + 32);
  v11 = (__int64 *)*((_QWORD *)a1 + 4);
  if ( v11 )
  {
    do
    {
      v12 = KerbS4U2ProxyCacheEntryCompare(a2, (struct _RTL_BALANCED_NODE *)v11);
      if ( v12 >= 0 )
      {
        if ( v12 <= 0 )
          break;
        v11 = (__int64 *)v11[1];
      }
      else
      {
        v11 = (__int64 *)*v11;
      }
    }
    while ( v11 );
    if ( v11 )
    {
      if ( !a3 || *((_DWORD *)v11 + 18) != a3 || *((_DWORD *)v11 + 19) != a4 )
      {
        v13 = (struct _KERB_S4U2PROXY_CACHE *)(v11 + 3);
        *((_DWORD *)v11 + 18) = a3;
        *((_DWORD *)v11 + 19) = a4;
        v11[10] = KerbGlobalS4UCacheTimeout.QuadPart + *(_QWORD *)&SystemTimeAsFileTime;
        v14 = (struct _KERB_S4U2PROXY_CACHE ***)(v11 + 4);
        v15 = v11[3];
        if ( v15 && (v16 = *v14) != 0 )
        {
          if ( *(struct _KERB_S4U2PROXY_CACHE **)(v15 + 8) != v13 || *v16 != v13 )
            goto LABEL_31;
          *v16 = (struct _KERB_S4U2PROXY_CACHE *)v15;
          *(_QWORD *)(v15 + 8) = v16;
          *(_QWORD *)v13 = 0;
          *v14 = 0;
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)v11 + 10);
        }
        v17 = (struct _KERB_S4U2PROXY_CACHE **)*((_QWORD *)a1 + 6);
        if ( *v17 != (struct _KERB_S4U2PROXY_CACHE *)((char *)a1 + 40) )
          goto LABEL_31;
        *v14 = v17;
        v18 = (char *)(v11 + 7);
        *(_QWORD *)v13 = (char *)a1 + 40;
        *v17 = v13;
        v19 = 609;
        *((_QWORD *)a1 + 6) = v13;
        v31 = v11[10];
        v30 = *((_DWORD *)v11 + 19);
        v20 = *((_DWORD *)v11 + 18);
        v21 = "Update S4U2Proxy cache entry %p for logon session %#x:%x, ServerName %wZ, Flags %#x, LastStatus %#x, Expiry %lld\n";
        v22 = WORD1(v11);
        goto LABEL_33;
      }
      goto LABEL_34;
    }
  }
  v23 = KerbCreateS4U2ProxyCacheEntry(a2, a3, a4, &v32);
  v8 = v23;
  if ( v23 < 0 )
  {
    KerbTracerT::Log(1, "KerbSetS4U2ProxyCacheEntry", 627, "KerbCreateS4U2ProxyCacheEntry failed: %#x\n", v23);
    RtlReleaseResource(&KerbGlobalS4U2ProxyCacheLock);
    v9 = v32;
    goto LABEL_35;
  }
  v25 = *v10;
  LOBYTE(v24) = 0;
  v26 = v32;
  if ( !*v10 )
    goto LABEL_30;
  while ( (int)KerbS4U2ProxyCacheEntryCompare((char *)v26 + 48, v25) >= 0 )
  {
    v27 = v25->Children[1];
    if ( !v27 )
    {
      LOBYTE(v24) = 1;
      goto LABEL_30;
    }
LABEL_28:
    v25 = v27;
  }
  v27 = v25->Children[0];
  if ( v25->Children[0] )
    goto LABEL_28;
  LOBYTE(v24) = 0;
LABEL_30:
  RtlAvlInsertNodeEx((char *)a1 + 32, v25, v24, v26);
  v28 = (struct _KERB_S4U2PROXY_CACHE **)*((_QWORD *)a1 + 6);
  if ( *v28 != (struct _KERB_S4U2PROXY_CACHE *)((char *)a1 + 40) )
LABEL_31:
    __fastfail(3u);
  v19 = 642;
  *((_QWORD *)v26 + 3) = (char *)a1 + 40;
  v21 = "Create S4U2Proxy cache entry %p for logon session: %#x:%x, ServerName %wZ, Flags %#x, LastStatus %#x, Expiry %lld\n";
  *((_QWORD *)v26 + 4) = v28;
  *v28 = (struct _KERB_S4U2PROXY_CACHE_ENTRY *)((char *)v26 + 24);
  *((_QWORD *)a1 + 6) = (char *)v26 + 24;
  v18 = (char *)v26 + 56;
  v22 = WORD1(v26);
  v31 = *((_QWORD *)v26 + 10);
  v30 = *((_DWORD *)v26 + 19);
  v20 = *((_DWORD *)v26 + 18);
LABEL_33:
  KerbTracerT::Log(
    21,
    "KerbSetS4U2ProxyCacheEntry",
    v19,
    v21,
    v22,
    *((_DWORD *)a1 + 2),
    *((_DWORD *)a1 + 1),
    v18,
    v20,
    v30,
    v31);
LABEL_34:
  RtlReleaseResource(&KerbGlobalS4U2ProxyCacheLock);
LABEL_35:
  KerbFreeS4U2ProxyCacheEntry(v9);
  return v8;
}

```

## disassembly

```asm
0x18009f7a4  push    rbx
0x18009f7a6  push    rbp
0x18009f7a7  push    rsi
0x18009f7a8  push    rdi
0x18009f7a9  push    r12
0x18009f7ab  push    r13
0x18009f7ad  push    r14
0x18009f7af  push    r15
0x18009f7b1  sub     rsp, 78h
0x18009f7b5  xor     ebx, ebx
0x18009f7b7  mov     ebp, r9d
0x18009f7ba  cmp     cs:?KerbGlobalS4UCacheTimeout@@3T_LARGE_INTEGER@@A, rbx; _LARGE_INTEGER KerbGlobalS4UCacheTimeout
0x18009f7c1  mov     edi, r8d
0x18009f7c4  mov     r12, rdx
0x18009f7c7  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18009f7cc  mov     rsi, rcx
0x18009f7cf  mov     [rsp+0B8h+var_58], rbx
0x18009f7d4  mov     r13d, ebx
0x18009f7d7  mov     r15d, ebx
0x18009f7da  jz      loc_18009FA25
0x18009f7e0  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009f7e5  call    cs:__imp_GetSystemTimeAsFileTime
0x18009f7eb  mov     dl, 1; Wait
0x18009f7ed  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18009f7f4  call    cs:__imp_RtlAcquireResourceExclusive
0x18009f7fa  cmp     [rsi], bl
0x18009f7fc  jz      loc_18009FA18
0x18009f802  lea     r14, [rsi+20h]
0x18009f806  mov     rbx, [r14]
0x18009f809  test    rbx, rbx
0x18009f80c  jz      loc_18009F8F8
0x18009f812  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18009f815  mov     rcx, r12; void *
0x18009f818  call    ?KerbS4U2ProxyCacheEntryCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; KerbS4U2ProxyCacheEntryCompare(void *,_RTL_BALANCED_NODE *)
0x18009f81d  test    eax, eax
0x18009f81f  jns     short loc_18009F826
0x18009f821  mov     rbx, [rbx]
0x18009f824  jmp     short loc_18009F82C
0x18009f826  jle     short loc_18009F831
0x18009f828  mov     rbx, [rbx+8]
0x18009f82c  test    rbx, rbx
0x18009f82f  jnz     short loc_18009F812
0x18009f831  test    rbx, rbx
0x18009f834  jz      loc_18009F8F8
0x18009f83a  test    edi, edi
0x18009f83c  jz      short loc_18009F84C
0x18009f83e  cmp     [rbx+48h], edi
0x18009f841  jnz     short loc_18009F84C
0x18009f843  cmp     [rbx+4Ch], ebp
0x18009f846  jz      loc_18009FA18
0x18009f84c  lea     rax, [rbx+18h]
0x18009f850  lea     r9, [rbx+48h]
0x18009f854  mov     [r9], edi
0x18009f857  lea     r10, [rbx+4Ch]
0x18009f85b  mov     [r10], ebp
0x18009f85e  lea     r11, [rbx+50h]
0x18009f862  mov     rcx, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x18009f867  add     rcx, cs:?KerbGlobalS4UCacheTimeout@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalS4UCacheTimeout
0x18009f86e  mov     [r11], rcx
0x18009f871  lea     rcx, [rax+8]
0x18009f875  mov     rdx, [rax]
0x18009f878  test    rdx, rdx
0x18009f87b  jz      short loc_18009F8A7
0x18009f87d  mov     r8, [rcx]
0x18009f880  test    r8, r8
0x18009f883  jz      short loc_18009F8A7
0x18009f885  cmp     [rdx+8], rax
0x18009f889  jnz     loc_18009F9A4
0x18009f88f  cmp     [r8], rax
0x18009f892  jnz     loc_18009F9A4
0x18009f898  mov     [r8], rdx
0x18009f89b  mov     [rdx+8], r8
0x18009f89f  mov     [rax], r13
0x18009f8a2  mov     [rcx], r13
0x18009f8a5  jmp     short loc_18009F8AB
0x18009f8a7  lock inc dword ptr [rax+10h]
0x18009f8ab  lea     rdx, [rsi+28h]
0x18009f8af  mov     r8, [rdx+8]
0x18009f8b3  cmp     [r8], rdx
0x18009f8b6  jnz     loc_18009F9A4
0x18009f8bc  mov     [rcx], r8
0x18009f8bf  lea     rcx, [rbx+38h]
0x18009f8c3  mov     [rax], rdx
0x18009f8c6  mov     [r8], rax
0x18009f8c9  mov     r8d, 261h
0x18009f8cf  mov     [rdx+8], rax
0x18009f8d3  mov     rax, [r11]
0x18009f8d6  mov     [rsp+0B8h+var_68], rax
0x18009f8db  mov     eax, [r10]
0x18009f8de  mov     [rsp+0B8h+var_70], eax
0x18009f8e2  mov     eax, [r9]
0x18009f8e5  lea     r9, aUpdateS4u2prox; "Update S4U2Proxy cache entry %p for log"...
0x18009f8ec  shr     rbx, 10h
0x18009f8f0  movzx   edx, bx
0x18009f8f3  jmp     loc_18009F9EB
0x18009f8f8  lea     r9, [rsp+0B8h+var_58]; struct _KERB_S4U2PROXY_CACHE_ENTRY **
0x18009f8fd  mov     r8d, ebp; int
0x18009f900  mov     edx, edi; unsigned int
0x18009f902  mov     rcx, r12; struct _KERB_INTERNAL_NAME *
0x18009f905  call    ?KerbCreateS4U2ProxyCacheEntry@@YAJPEAU_KERB_INTERNAL_NAME@@KJPEAPEAU_KERB_S4U2PROXY_CACHE_ENTRY@@@Z; KerbCreateS4U2ProxyCacheEntry(_KERB_INTERNAL_NAME *,ulong,long,_KERB_S4U2PROXY_CACHE_ENTRY * *)
0x18009f90a  mov     r13d, eax
0x18009f90d  test    eax, eax
0x18009f90f  jns     short loc_18009F94A
0x18009f911  lea     r9, aKerbcreates4u2_0; "KerbCreateS4U2ProxyCacheEntry failed: %"...
0x18009f918  mov     dword ptr [rsp+0B8h+var_98], eax
0x18009f91c  mov     r8d, 273h
0x18009f922  lea     rdx, aKerbsets4u2pro_0; "KerbSetS4U2ProxyCacheEntry"
0x18009f929  mov     ecx, 1
0x18009f92e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009f933  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18009f93a  call    cs:__imp_RtlReleaseResource
0x18009f940  mov     r15, [rsp+0B8h+var_58]
0x18009f945  jmp     loc_18009FA25
0x18009f94a  mov     rbx, [r14]
0x18009f94d  xor     r8b, r8b
0x18009f950  mov     rdi, [rsp+0B8h+var_58]
0x18009f955  test    rbx, rbx
0x18009f958  jz      short loc_18009F988
0x18009f95a  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18009f95d  lea     rcx, [rdi+30h]; void *
0x18009f961  call    ?KerbS4U2ProxyCacheEntryCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; KerbS4U2ProxyCacheEntryCompare(void *,_RTL_BALANCED_NODE *)
0x18009f966  test    eax, eax
0x18009f968  js      short loc_18009F978
0x18009f96a  mov     rax, [rbx+8]
0x18009f96e  test    rax, rax
0x18009f971  jnz     short loc_18009F980
0x18009f973  mov     r8b, 1
0x18009f976  jmp     short loc_18009F988
0x18009f978  mov     rax, [rbx]
0x18009f97b  test    rax, rax
0x18009f97e  jz      short loc_18009F985
0x18009f980  mov     rbx, rax
0x18009f983  jmp     short loc_18009F95A
0x18009f985  xor     r8b, r8b
0x18009f988  mov     r9, rdi
0x18009f98b  mov     rdx, rbx
0x18009f98e  mov     rcx, r14
0x18009f991  call    cs:__imp_RtlAvlInsertNodeEx
0x18009f997  lea     rcx, [rsi+28h]
0x18009f99b  mov     rdx, [rcx+8]
0x18009f99f  cmp     [rdx], rcx
0x18009f9a2  jz      short loc_18009F9AB
0x18009f9a4  mov     ecx, 3
0x18009f9a9  int     29h; Win8: RtlFailFast(ecx)
0x18009f9ab  lea     rax, [rdi+18h]
0x18009f9af  mov     r8d, 282h
0x18009f9b5  mov     [rax], rcx
0x18009f9b8  lea     r9, aCreateS4u2prox; "Create S4U2Proxy cache entry %p for log"...
0x18009f9bf  mov     [rax+8], rdx
0x18009f9c3  mov     [rdx], rax
0x18009f9c6  mov     [rcx+8], rax
0x18009f9ca  mov     rax, rdi
0x18009f9cd  shr     rax, 10h
0x18009f9d1  lea     rcx, [rdi+38h]
0x18009f9d5  movzx   edx, ax
0x18009f9d8  mov     rax, [rdi+50h]
0x18009f9dc  mov     [rsp+0B8h+var_68], rax
0x18009f9e1  mov     eax, [rdi+4Ch]
0x18009f9e4  mov     [rsp+0B8h+var_70], eax
0x18009f9e8  mov     eax, [rdi+48h]
0x18009f9eb  mov     [rsp+0B8h+var_78], eax
0x18009f9ef  mov     eax, [rsi+4]
0x18009f9f2  mov     [rsp+0B8h+var_80], rcx
0x18009f9f7  mov     ecx, 15h
0x18009f9fc  mov     [rsp+0B8h+var_88], eax
0x18009fa00  mov     eax, [rsi+8]
0x18009fa03  mov     [rsp+0B8h+var_90], eax
0x18009fa07  mov     [rsp+0B8h+var_98], rdx
0x18009fa0c  lea     rdx, aKerbsets4u2pro_0; "KerbSetS4U2ProxyCacheEntry"
0x18009fa13  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009fa18  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18009fa1f  call    cs:__imp_RtlReleaseResource
0x18009fa25  mov     rcx, r15; struct _KERB_S4U2PROXY_CACHE_ENTRY *
0x18009fa28  call    ?KerbFreeS4U2ProxyCacheEntry@@YAXPEAU_KERB_S4U2PROXY_CACHE_ENTRY@@@Z; KerbFreeS4U2ProxyCacheEntry(_KERB_S4U2PROXY_CACHE_ENTRY *)
0x18009fa2d  mov     eax, r13d
0x18009fa30  add     rsp, 78h
0x18009fa34  pop     r15
0x18009fa36  pop     r14
0x18009fa38  pop     r13
0x18009fa3a  pop     r12
0x18009fa3c  pop     rdi
0x18009fa3d  pop     rsi
0x18009fa3e  pop     rbp
0x18009fa3f  pop     rbx
0x18009fa40  retn
```
