# CCatalogServer::ExtractEventClassData(ISimpleTableRead *,ushort * *,ushort * *,ushort * *,ushort * *,ulong *)

- ea: `0x180021484`
- end: `0x180021751`
- name: `?ExtractEventClassData@CCatalogServer@@AEAAJPEAUISimpleTableRead@@PEAPEAG111PEAK@Z`
- size: `717`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, struct ISimpleTableRead *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022040`

## callees

- `0x18000a01c`
- `0x180021484`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002153b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800215b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800216c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002153b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800215b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800216c6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002150b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800216a3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002150b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800216a3`

## pseudocode

```c
__int64 __fastcall CCatalogServer::ExtractEventClassData(
        CCatalogServer *this,
        struct ISimpleTableRead *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned int *a7)
{
  __int64 v9; // rax
  __int64 (__fastcall *v11)(struct ISimpleTableRead *, _QWORD, _QWORD, _QWORD, GUID **); // rax
  int v12; // ecx
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  GUID *rguid; // [rsp+38h] [rbp-69h] BYREF
  unsigned int *v21; // [rsp+40h] [rbp-61h]
  unsigned __int16 **v22; // [rsp+48h] [rbp-59h]
  OLECHAR sz[40]; // [rsp+50h] [rbp-51h] BYREF

  v22 = a6;
  v9 = *(_QWORD *)a2;
  rguid = 0;
  v11 = *(__int64 (__fastcall **)(struct ISimpleTableRead *, _QWORD, _QWORD, _QWORD, GUID **))(v9 + 64);
  v21 = 0;
  v12 = v11(a2, 0, 0, 0, &rguid);
  if ( v12 >= 0 )
  {
    if ( !StringFromGUID2(rguid, sz, 40) )
      return (unsigned int)-2147418113;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( sz[v14] );
    v15 = v14 + 1;
    v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v14 + 1));
    *a3 = v16;
    if ( !v16 )
      return (unsigned int)-2147024882;
    v12 = StringCchCopyW(v16, v15, sz);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 3, 0);
      if ( v12 >= 0 )
      {
        *a4 = 0;
        v12 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 4, 0);
        if ( v12 >= 0 )
        {
          *a5 = 0;
          v12 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 9, 0);
          if ( v12 >= 0 )
          {
            if ( !StringFromGUID2(rguid, sz, 40) )
              return (unsigned int)-2147418113;
            do
              ++v13;
            while ( sz[v13] );
            v17 = v13 + 1;
            v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17);
            *v22 = v18;
            if ( !v18 )
              return (unsigned int)-2147024882;
            v12 = StringCchCopyW(v18, v17, sz);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(
                      a2,
                      54,
                      0);
              if ( v12 >= 0 )
              {
                if ( v21 )
                  *a7 = *v21;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180021484  mov     [rsp-8+arg_0], rbx
0x180021489  push    rbp
0x18002148a  push    rsi
0x18002148b  push    rdi
0x18002148c  push    r12
0x18002148e  push    r13
0x180021490  push    r14
0x180021492  push    r15
0x180021494  lea     rbp, [rsp-0Fh]
0x180021499  sub     rsp, 0B0h
0x1800214a0  mov     rax, cs:__security_cookie
0x1800214a7  xor     rax, rsp
0x1800214aa  mov     [rbp+3Fh+var_40], rax
0x1800214ae  mov     rax, [rbp+3Fh+arg_28]
0x1800214b2  lea     rcx, [rbp+3Fh+rguid]
0x1800214b6  mov     r12, [rbp+3Fh+arg_20]
0x1800214ba  mov     rdi, rdx
0x1800214bd  mov     r13, [rbp+3Fh+arg_30]
0x1800214c1  xor     esi, esi
0x1800214c3  mov     [rbp+3Fh+var_98], rax
0x1800214c7  mov     r14, r9
0x1800214ca  mov     rax, [rdx]
0x1800214cd  mov     r15, r8
0x1800214d0  mov     [rsp+0E0h+var_C0], rcx
0x1800214d5  xor     r9d, r9d
0x1800214d8  xor     r8d, r8d
0x1800214db  mov     [rbp+3Fh+rguid], rsi
0x1800214df  xor     edx, edx
0x1800214e1  mov     [rbp+3Fh+var_B0], rsi
0x1800214e5  mov     rax, [rax+40h]
0x1800214e9  mov     rcx, rdi
0x1800214ec  mov     [rbp+3Fh+var_A0], rsi
0x1800214f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f5  mov     ecx, eax
0x1800214f7  test    eax, eax
0x1800214f9  js      loc_180021728
0x1800214ff  mov     rcx, [rbp+3Fh+rguid]; rguid
0x180021503  lea     r8d, [rsi+28h]; cchMax
0x180021507  lea     rdx, [rbp+3Fh+sz]; lpsz
0x18002150b  call    cs:__imp_StringFromGUID2
0x180021511  test    eax, eax
0x180021513  jnz     short loc_18002151F
0x180021515  mov     ecx, 8000FFFFh
0x18002151a  jmp     loc_180021728
0x18002151f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021523  lea     rcx, [rbp+3Fh+sz]
0x180021527  mov     rax, rbx
0x18002152a  inc     rax
0x18002152d  cmp     [rcx+rax*2], si
0x180021531  jnz     short loc_18002152A
0x180021533  lea     rsi, [rax+1]
0x180021537  lea     rcx, [rsi+rsi]; cb
0x18002153b  call    cs:__imp_CoTaskMemAlloc
0x180021541  mov     [r15], rax
0x180021544  xor     r15d, r15d
0x180021547  test    rax, rax
0x18002154a  jnz     short loc_180021556
0x18002154c  mov     ecx, 8007000Eh
0x180021551  jmp     loc_180021728
0x180021556  lea     r8, [rbp+3Fh+sz]; unsigned __int16 *
0x18002155a  mov     rdx, rsi; unsigned __int64
0x18002155d  mov     rcx, rax; unsigned __int16 *
0x180021560  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021565  mov     ecx, eax
0x180021567  test    eax, eax
0x180021569  js      loc_180021728
0x18002156f  mov     rax, [rdi]
0x180021572  lea     rcx, [rbp+3Fh+var_B0]
0x180021576  xor     r9d, r9d
0x180021579  mov     [rsp+0E0h+var_C0], rcx
0x18002157e  xor     r8d, r8d
0x180021581  mov     rcx, rdi
0x180021584  mov     rax, [rax+40h]
0x180021588  lea     edx, [r9+3]
0x18002158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021591  mov     ecx, eax
0x180021593  test    eax, eax
0x180021595  js      loc_180021728
0x18002159b  mov     rcx, [rbp+3Fh+var_B0]
0x18002159f  test    rcx, rcx
0x1800215a2  jz      short loc_1800215E2
0x1800215a4  mov     rax, rbx
0x1800215a7  inc     rax
0x1800215aa  cmp     [rcx+rax*2], r15w
0x1800215af  jnz     short loc_1800215A7
0x1800215b1  lea     rsi, [rax+1]
0x1800215b5  lea     rcx, [rsi+rsi]; cb
0x1800215b9  call    cs:__imp_CoTaskMemAlloc
0x1800215bf  mov     [r14], rax
0x1800215c2  test    rax, rax
0x1800215c5  jz      short loc_18002154C
0x1800215c7  mov     r8, [rbp+3Fh+var_B0]; unsigned __int16 *
0x1800215cb  mov     rdx, rsi; unsigned __int64
0x1800215ce  mov     rcx, rax; unsigned __int16 *
0x1800215d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800215d6  mov     ecx, eax
0x1800215d8  test    eax, eax
0x1800215da  js      loc_180021728
0x1800215e0  jmp     short loc_1800215E5
0x1800215e2  mov     [r14], r15
0x1800215e5  mov     rax, [rdi]
0x1800215e8  lea     rcx, [rbp+3Fh+var_B0]
0x1800215ec  xor     r9d, r9d
0x1800215ef  mov     [rsp+0E0h+var_C0], rcx
0x1800215f4  xor     r8d, r8d
0x1800215f7  mov     [rbp+3Fh+var_B0], r15
0x1800215fb  mov     rcx, rdi
0x1800215fe  mov     rax, [rax+40h]
0x180021602  lea     edx, [r9+4]
0x180021606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002160b  mov     ecx, eax
0x18002160d  test    eax, eax
0x18002160f  js      loc_180021728
0x180021615  mov     rcx, [rbp+3Fh+var_B0]
0x180021619  test    rcx, rcx
0x18002161c  jz      short loc_180021661
0x18002161e  mov     rax, rbx
0x180021621  inc     rax
0x180021624  cmp     [rcx+rax*2], r15w
0x180021629  jnz     short loc_180021621
0x18002162b  lea     rsi, [rax+1]
0x18002162f  lea     rcx, [rsi+rsi]; cb
0x180021633  call    cs:__imp_CoTaskMemAlloc
0x180021639  mov     [r12], rax
0x18002163d  test    rax, rax
0x180021640  jz      loc_18002154C
0x180021646  mov     r8, [rbp+3Fh+var_B0]; unsigned __int16 *
0x18002164a  mov     rdx, rsi; unsigned __int64
0x18002164d  mov     rcx, rax; unsigned __int16 *
0x180021650  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021655  mov     ecx, eax
0x180021657  test    eax, eax
0x180021659  js      loc_180021728
0x18002165f  jmp     short loc_180021665
0x180021661  mov     [r12], r15
0x180021665  mov     rax, [rdi]
0x180021668  lea     rcx, [rbp+3Fh+rguid]
0x18002166c  xor     r9d, r9d
0x18002166f  mov     [rsp+0E0h+var_C0], rcx
0x180021674  xor     r8d, r8d
0x180021677  mov     [rbp+3Fh+var_B0], r15
0x18002167b  mov     rcx, rdi
0x18002167e  mov     rax, [rax+40h]
0x180021682  lea     edx, [r9+9]
0x180021686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002168b  mov     ecx, eax
0x18002168d  test    eax, eax
0x18002168f  js      loc_180021728
0x180021695  mov     rcx, [rbp+3Fh+rguid]; rguid
0x180021699  lea     rdx, [rbp+3Fh+sz]; lpsz
0x18002169d  mov     r8d, 28h ; '('; cchMax
0x1800216a3  call    cs:__imp_StringFromGUID2
0x1800216a9  test    eax, eax
0x1800216ab  jz      loc_180021515
0x1800216b1  lea     rax, [rbp+3Fh+sz]
0x1800216b5  inc     rbx
0x1800216b8  cmp     [rax+rbx*2], r15w
0x1800216bd  jnz     short loc_1800216B5
0x1800216bf  inc     rbx
0x1800216c2  lea     rcx, [rbx+rbx]; cb
0x1800216c6  call    cs:__imp_CoTaskMemAlloc
0x1800216cc  mov     rcx, [rbp+3Fh+var_98]
0x1800216d0  mov     [rcx], rax
0x1800216d3  test    rax, rax
0x1800216d6  jz      loc_18002154C
0x1800216dc  lea     r8, [rbp+3Fh+sz]; unsigned __int16 *
0x1800216e0  mov     rdx, rbx; unsigned __int64
0x1800216e3  mov     rcx, rax; unsigned __int16 *
0x1800216e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800216eb  mov     ecx, eax
0x1800216ed  test    eax, eax
0x1800216ef  js      short loc_180021728
0x1800216f1  mov     rax, [rdi]
0x1800216f4  lea     rcx, [rbp+3Fh+var_A0]
0x1800216f8  xor     r9d, r9d
0x1800216fb  mov     [rsp+0E0h+var_C0], rcx
0x180021700  xor     r8d, r8d
0x180021703  mov     rcx, rdi
0x180021706  mov     rax, [rax+40h]
0x18002170a  lea     edx, [r9+36h]
0x18002170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021713  mov     ecx, eax
0x180021715  test    eax, eax
0x180021717  js      short loc_180021728
0x180021719  mov     rax, [rbp+3Fh+var_A0]
0x18002171d  test    rax, rax
0x180021720  jz      short loc_180021728
0x180021722  mov     eax, [rax]
0x180021724  mov     [r13+0], eax
0x180021728  mov     eax, ecx
0x18002172a  mov     rcx, [rbp+3Fh+var_40]
0x18002172e  xor     rcx, rsp; StackCookie
0x180021731  call    __security_check_cookie
0x180021736  mov     rbx, [rsp+0E0h+arg_0]
0x18002173e  add     rsp, 0B0h
0x180021745  pop     r15
0x180021747  pop     r14
0x180021749  pop     r13
0x18002174b  pop     r12
0x18002174d  pop     rdi
0x18002174e  pop     rsi
0x18002174f  pop     rbp
0x180021750  retn
```
