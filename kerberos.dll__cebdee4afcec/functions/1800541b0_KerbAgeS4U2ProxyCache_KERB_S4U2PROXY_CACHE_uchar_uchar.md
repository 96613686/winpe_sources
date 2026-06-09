# KerbAgeS4U2ProxyCache(_KERB_S4U2PROXY_CACHE *,uchar,uchar)

- ea: `0x1800541b0`
- end: `0x180054502`
- name: `?KerbAgeS4U2ProxyCache@@YAXPEAU_KERB_S4U2PROXY_CACHE@@EE@Z`
- size: `850`
- prototype: `void __fastcall(struct _KERB_S4U2PROXY_CACHE *, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800566a8`
- `0x18006517c`
- `0x18009ea84`
- `0x1800ac4b4`

## callees

- `0x1800541b0`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800541d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800541d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054445`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005447b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800544a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054445`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005447b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800544a5`
- `ntdll!RtlAvlRemoveNode` at `0x18005435a`
- `ntdll!RtlAvlRemoveNode` at `0x18005435a`
- `ntdll!RtlReleaseResource` at `0x180054243`
- `ntdll!RtlReleaseResource` at `0x180054309`
- `ntdll!RtlReleaseResource` at `0x1800544cc`
- `ntdll!RtlReleaseResource` at `0x180054243`
- `ntdll!RtlReleaseResource` at `0x180054309`
- `ntdll!RtlReleaseResource` at `0x1800544cc`
- `ntdll!RtlAcquireResourceShared` at `0x1800541e8`
- `ntdll!RtlAcquireResourceShared` at `0x1800541e8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180054252`
- `ntdll!RtlAcquireResourceExclusive` at `0x180054318`
- `ntdll!RtlAcquireResourceExclusive` at `0x180054252`
- `ntdll!RtlAcquireResourceExclusive` at `0x180054318`

## string_xrefs

- `0x180054277`: `Reset expired S4U2Proxy cache %p flags for logon session: %#x:%x, Flags %#x, LastStatus %#x, Expiry %lld, RemoveAll %d\n`
- `0x1800542bd`: `KerbAgeS4U2ProxyCache`
- `0x1800543b4`: `KerbAgeS4U2ProxyCache`
- `0x18005436c`: `Removed S4U2Proxy cache entry %p from AVL table for logon session %#x:%x, ServerName %wZ, Flags %#x, LastStatus %#x, Expiry %lld, RemoveAll %d\n`

## pseudocode

```c
void __fastcall KerbAgeS4U2ProxyCache(struct _KERB_S4U2PROXY_CACHE *a1, unsigned __int8 a2, char a3)
{
  int v4; // r15d
  char v6; // bl
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 **v10; // rsi
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 **v13; // r14
  __int64 v14; // rax
  volatile signed __int32 **v15; // rcx
  HLOCAL *v16; // rbx
  void *v17; // rcx
  __int64 v18; // [rsp+28h] [rbp-60h]
  __int64 v19; // [rsp+30h] [rbp-58h]
  __int64 v20; // [rsp+40h] [rbp-48h]
  __int64 v21; // [rsp+48h] [rbp-40h]
  __int64 v22; // [rsp+58h] [rbp-30h]
  __int64 v23; // [rsp+90h] [rbp+8h] BYREF

  v4 = a2;
  v23 = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&v23);
  if ( a3 )
    RtlAcquireResourceShared(&KerbGlobalS4U2ProxyCacheLock, 1u);
  if ( *(_BYTE *)a1 )
  {
    v6 = 0;
    if ( (_BYTE)v4 || (v7 = *((_QWORD *)a1 + 3)) != 0 && v7 < v23 )
    {
      if ( a3 )
      {
        RtlReleaseResource(&KerbGlobalS4U2ProxyCacheLock);
        RtlAcquireResourceExclusive(&KerbGlobalS4U2ProxyCacheLock, 1u);
        v6 = 1;
      }
      if ( (_BYTE)v4 || (v8 = *((_QWORD *)a1 + 3)) != 0 && v8 < v23 )
      {
        KerbTracerT::Log(
          21,
          "KerbAgeS4U2ProxyCache",
          291,
          "Reset expired S4U2Proxy cache %p flags for logon session: %#x:%x, Flags %#x, LastStatus %#x, Expiry %lld, RemoveAll %d\n",
          (const void *)WORD1(a1),
          *((_DWORD *)a1 + 2),
          *((_DWORD *)a1 + 1),
          *((_DWORD *)a1 + 3),
          *((_DWORD *)a1 + 4),
          *((_QWORD *)a1 + 3),
          v4);
        *(_QWORD *)((char *)a1 + 12) = 0;
        *((_QWORD *)a1 + 3) = 0;
      }
    }
    v9 = *((_QWORD *)a1 + 5);
    v10 = (volatile signed __int32 **)((char *)a1 + 40);
    if ( (struct _KERB_S4U2PROXY_CACHE *)v9 != (struct _KERB_S4U2PROXY_CACHE *)((char *)a1 + 40) )
    {
      if ( !(_BYTE)v4 && *(_QWORD *)(v9 + 56) > v23 )
        goto LABEL_50;
      if ( a3 && !v6 )
      {
        RtlReleaseResource(&KerbGlobalS4U2ProxyCacheLock);
        RtlAcquireResourceExclusive(&KerbGlobalS4U2ProxyCacheLock, 1u);
      }
      v11 = *v10;
      if ( *v10 != (volatile signed __int32 *)v10 )
      {
        do
        {
          v12 = v11 - 6;
          if ( (_BYTE)v4 )
          {
            v13 = (volatile signed __int32 **)*((_QWORD *)v11 + 1);
          }
          else
          {
            if ( *((_QWORD *)v12 + 10) > v23 )
              goto LABEL_50;
            v13 = (volatile signed __int32 **)*((_QWORD *)v11 + 1);
            RtlAvlRemoveNode((char *)a1 + 32, v11 - 6);
            LODWORD(v22) = 0;
            LODWORD(v21) = *((_DWORD *)v12 + 19);
            LODWORD(v20) = *((_DWORD *)v12 + 18);
            LODWORD(v19) = *((_DWORD *)a1 + 1);
            LODWORD(v18) = *((_DWORD *)a1 + 2);
            KerbTracerT::Log(
              21,
              "KerbAgeS4U2ProxyCache",
              367,
              "Removed S4U2Proxy cache entry %p from AVL table for logon session %#x:%x, ServerName %wZ, Flags %#x, LastS"
              "tatus %#x, Expiry %lld, RemoveAll %d\n",
              WORD1(v12),
              v18,
              v19,
              v12 + 14,
              v20,
              v21,
              *((_QWORD *)v12 + 10),
              v22);
          }
          v14 = *(_QWORD *)v11;
          if ( *(_QWORD *)v11 && (v15 = (volatile signed __int32 **)*((_QWORD *)v11 + 1)) != 0 )
          {
            if ( *(volatile signed __int32 **)(v14 + 8) != v11 || *v15 != v11 )
              __fastfail(3u);
            *v15 = (volatile signed __int32 *)v14;
            *(_QWORD *)(v14 + 8) = v15;
            *(_QWORD *)v11 = 0;
            *((_QWORD *)v11 + 1) = 0;
          }
          else
          {
            _InterlockedIncrement(v11 + 4);
          }
          if ( _InterlockedExchangeAdd(v11 + 4, 0xFFFFFFFF) == 1 && v11 != (volatile signed __int32 *)24 )
          {
            v16 = (HLOCAL *)(v12 + 12);
            if ( v12 != (volatile signed __int32 *)-48LL && *v16 )
            {
              if ( KerbGlobalPackageState == 1 )
                ((void (*)(void))LsaFunctions->FreeLsaHeap)();
              else
                LocalFree(*v16);
              *v16 = 0;
            }
            if ( v12 != (volatile signed __int32 *)-56LL )
            {
              v17 = (void *)*((_QWORD *)v12 + 8);
              if ( v17 )
              {
                if ( KerbGlobalPackageState == 1 )
                  ((void (*)(void))LsaFunctions->FreeLsaHeap)();
                else
                  LocalFree(v17);
              }
              *(_OWORD *)(v12 + 14) = 0;
            }
            if ( KerbGlobalPackageState == 1 )
              ((void (__fastcall *)(volatile signed __int32 *))LsaFunctions->FreeLsaHeap)(v12);
            else
              LocalFree((HLOCAL)v12);
          }
          v11 = *v13;
        }
        while ( *v13 != (volatile signed __int32 *)v10 );
      }
    }
    if ( (_BYTE)v4 )
      *((_QWORD *)a1 + 4) = 0;
  }
LABEL_50:
  if ( a3 )
    RtlReleaseResource(&KerbGlobalS4U2ProxyCacheLock);
}

```

## disassembly

```asm
0x1800541b0  mov     rax, rsp
0x1800541b3  push    rbp
0x1800541b4  push    r12
0x1800541b6  push    r13
0x1800541b8  push    r15
0x1800541ba  sub     rsp, 68h
0x1800541be  mov     rbp, rcx
0x1800541c1  movzx   r15d, dl
0x1800541c5  xor     r13d, r13d
0x1800541c8  lea     rcx, [rax+8]; lpSystemTimeAsFileTime
0x1800541cc  mov     [rax+8], r13
0x1800541d0  movzx   r12d, r8b
0x1800541d4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800541da  test    r12b, r12b
0x1800541dd  jz      short loc_1800541EE
0x1800541df  mov     dl, 1; Wait
0x1800541e1  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800541e8  call    cs:__imp_RtlAcquireResourceShared
0x1800541ee  mov     [rsp+88h+arg_8], rbx
0x1800541f6  mov     [rsp+88h+arg_10], rsi
0x1800541fe  mov     [rsp+88h+arg_18], rdi
0x180054206  mov     [rsp+88h+var_28], r14
0x18005420b  cmp     [rbp+0], r13b
0x18005420f  jz      loc_1800544C0
0x180054215  xor     bl, bl
0x180054217  test    r15b, r15b
0x18005421a  jnz     short loc_180054237
0x18005421c  mov     rax, [rbp+18h]
0x180054220  test    rax, rax
0x180054223  jz      loc_1800542D1
0x180054229  cmp     rax, [rsp+88h+arg_0]
0x180054231  jge     loc_1800542D1
0x180054237  test    r12b, r12b
0x18005423a  jz      short loc_18005425A
0x18005423c  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180054243  call    cs:__imp_RtlReleaseResource
0x180054249  mov     dl, 1; Wait
0x18005424b  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180054252  call    cs:__imp_RtlAcquireResourceExclusive
0x180054258  mov     bl, 1
0x18005425a  test    r15b, r15b
0x18005425d  jnz     short loc_180054272
0x18005425f  mov     rax, [rbp+18h]
0x180054263  test    rax, rax
0x180054266  jz      short loc_1800542D1
0x180054268  cmp     rax, [rsp+88h+arg_0]
0x180054270  jge     short loc_1800542D1
0x180054272  mov     dword ptr [rsp+88h+var_38], r15d
0x180054277  lea     r9, aResetExpiredS4; "Reset expired S4U2Proxy cache %p flags "...
0x18005427e  mov     rax, rbp
0x180054281  mov     r8d, 123h
0x180054287  shr     rax, 10h
0x18005428b  mov     ecx, 15h
0x180054290  movzx   edx, ax
0x180054293  mov     rax, [rbp+18h]
0x180054297  mov     [rsp+88h+var_40], rax
0x18005429c  mov     eax, [rbp+10h]
0x18005429f  mov     dword ptr [rsp+88h+var_48], eax
0x1800542a3  mov     eax, [rbp+0Ch]
0x1800542a6  mov     dword ptr [rsp+88h+var_50], eax
0x1800542aa  mov     eax, [rbp+4]
0x1800542ad  mov     dword ptr [rsp+88h+var_58], eax
0x1800542b1  mov     eax, [rbp+8]
0x1800542b4  mov     dword ptr [rsp+88h+var_60], eax
0x1800542b8  mov     [rsp+88h+var_68], rdx
0x1800542bd  lea     rdx, aKerbages4u2pro; "KerbAgeS4U2ProxyCache"
0x1800542c4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800542c9  mov     [rbp+0Ch], r13
0x1800542cd  mov     [rbp+18h], r13
0x1800542d1  mov     rcx, [rbp+28h]
0x1800542d5  lea     rsi, [rbp+28h]
0x1800542d9  cmp     rcx, rsi
0x1800542dc  jz      loc_1800544B7
0x1800542e2  test    r15b, r15b
0x1800542e5  jnz     short loc_1800542F9
0x1800542e7  mov     rax, [rsp+88h+arg_0]
0x1800542ef  cmp     [rcx+38h], rax
0x1800542f3  jg      loc_1800544C0
0x1800542f9  test    r12b, r12b
0x1800542fc  jz      short loc_18005431E
0x1800542fe  test    bl, bl
0x180054300  jnz     short loc_18005431E
0x180054302  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180054309  call    cs:__imp_RtlReleaseResource
0x18005430f  mov     dl, 1; Wait
0x180054311  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180054318  call    cs:__imp_RtlAcquireResourceExclusive
0x18005431e  mov     rbx, [rsi]
0x180054321  cmp     rbx, rsi
0x180054324  jz      loc_1800544B7
0x18005432a  nop     word ptr [rax+rax+00h]
0x180054330  lea     rdi, [rbx-18h]
0x180054334  test    r15b, r15b
0x180054337  jnz     loc_1800543C2
0x18005433d  mov     rax, [rsp+88h+arg_0]
0x180054345  cmp     [rdi+50h], rax
0x180054349  jg      loc_1800544C0
0x18005434f  mov     r14, [rbx+8]
0x180054353  lea     rcx, [rbp+20h]
0x180054357  mov     rdx, rdi
0x18005435a  call    cs:__imp_RtlAvlRemoveNode
0x180054360  mov     dword ptr [rsp+88h+var_30], r13d
0x180054365  lea     rcx, [rdi+38h]
0x180054369  mov     rax, rdi
0x18005436c  lea     r9, aRemovedS4u2pro; "Removed S4U2Proxy cache entry %p from A"...
0x180054373  shr     rax, 10h
0x180054377  mov     r8d, 16Fh
0x18005437d  movzx   edx, ax
0x180054380  mov     rax, [rdi+50h]
0x180054384  mov     [rsp+88h+var_38], rax
0x180054389  mov     eax, [rdi+4Ch]
0x18005438c  mov     dword ptr [rsp+88h+var_40], eax
0x180054390  mov     eax, [rdi+48h]
0x180054393  mov     dword ptr [rsp+88h+var_48], eax
0x180054397  mov     eax, [rbp+4]
0x18005439a  mov     [rsp+88h+var_50], rcx
0x18005439f  mov     ecx, 15h
0x1800543a4  mov     dword ptr [rsp+88h+var_58], eax
0x1800543a8  mov     eax, [rbp+8]
0x1800543ab  mov     dword ptr [rsp+88h+var_60], eax
0x1800543af  mov     [rsp+88h+var_68], rdx
0x1800543b4  lea     rdx, aKerbages4u2pro; "KerbAgeS4U2ProxyCache"
0x1800543bb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800543c0  jmp     short loc_1800543C6
0x1800543c2  mov     r14, [rbx+8]
0x1800543c6  mov     rax, [rbx]
0x1800543c9  test    rax, rax
0x1800543cc  jz      short loc_1800543FA
0x1800543ce  mov     rcx, [rbx+8]
0x1800543d2  test    rcx, rcx
0x1800543d5  jz      short loc_1800543FA
0x1800543d7  cmp     [rax+8], rbx
0x1800543db  jnz     loc_1800544FB
0x1800543e1  cmp     [rcx], rbx
0x1800543e4  jnz     loc_1800544FB
0x1800543ea  mov     [rcx], rax
0x1800543ed  mov     [rax+8], rcx
0x1800543f1  mov     [rbx], r13
0x1800543f4  mov     [rbx+8], r13
0x1800543f8  jmp     short loc_1800543FE
0x1800543fa  lock inc dword ptr [rbx+10h]
0x1800543fe  mov     eax, 0FFFFFFFFh
0x180054403  lock xadd [rbx+10h], eax
0x180054408  cmp     eax, 1
0x18005440b  jnz     loc_1800544AB
0x180054411  test    rdi, rdi
0x180054414  jz      loc_1800544AB
0x18005441a  lea     rbx, [rdi+30h]
0x18005441e  test    rbx, rbx
0x180054421  jz      short loc_18005444E
0x180054423  mov     rcx, [rbx]; hMem
0x180054426  test    rcx, rcx
0x180054429  jz      short loc_18005444E
0x18005442b  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, eax; KerberosState KerbGlobalPackageState
0x180054431  jnz     short loc_180054445
0x180054433  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005443a  mov     rax, [rax+30h]
0x18005443e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054443  jmp     short loc_18005444B
0x180054445  call    cs:__imp_LocalFree
0x18005444b  mov     [rbx], r13
0x18005444e  lea     rbx, [rdi+38h]
0x180054452  test    rbx, rbx
0x180054455  jz      short loc_180054487
0x180054457  mov     rcx, [rbx+8]; hMem
0x18005445b  test    rcx, rcx
0x18005445e  jz      short loc_180054481
0x180054460  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180054467  jnz     short loc_18005447B
0x180054469  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180054470  mov     rax, [rax+30h]
0x180054474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054479  jmp     short loc_180054481
0x18005447b  call    cs:__imp_LocalFree
0x180054481  xorps   xmm0, xmm0
0x180054484  movups  xmmword ptr [rbx], xmm0
0x180054487  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18005448e  mov     rcx, rdi; hMem
0x180054491  jnz     short loc_1800544A5
0x180054493  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005449a  mov     rax, [rax+30h]
0x18005449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544a3  jmp     short loc_1800544AB
0x1800544a5  call    cs:__imp_LocalFree
0x1800544ab  mov     rbx, [r14]
0x1800544ae  cmp     rbx, rsi
0x1800544b1  jnz     loc_180054330
0x1800544b7  test    r15b, r15b
0x1800544ba  jz      short loc_1800544C0
0x1800544bc  mov     [rbp+20h], r13
0x1800544c0  test    r12b, r12b
0x1800544c3  jz      short loc_1800544D2
0x1800544c5  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800544cc  call    cs:__imp_RtlReleaseResource
0x1800544d2  mov     r14, [rsp+88h+var_28]
0x1800544d7  mov     rdi, [rsp+88h+arg_18]
0x1800544df  mov     rsi, [rsp+88h+arg_10]
0x1800544e7  mov     rbx, [rsp+88h+arg_8]
0x1800544ef  add     rsp, 68h
0x1800544f3  pop     r15
0x1800544f5  pop     r13
0x1800544f7  pop     r12
0x1800544f9  pop     rbp
0x1800544fa  retn
0x1800544fb  mov     ecx, 3
0x180054500  int     29h; Win8: RtlFailFast(ecx)
```
