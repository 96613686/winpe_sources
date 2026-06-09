# ETW_TRACE_HANDLER::DeleteTraceUrlList(ushort const *)

- ea: `0x180002238`
- end: `0x180002420`
- name: `?DeleteTraceUrlList@ETW_TRACE_HANDLER@@SAJPEBG@Z`
- size: `488`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000265c`
- `0x180002fa0`

## callees

- `0x180002238`
- `0x180002428`
- `0x180003406`
- `0x180003430`
- `0x180004010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800022c3`
- `msvcrt!wcschr` at `0x1800022c3`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800023ec`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800023ec`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800023cf`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800023cf`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800022df`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800022df`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002293`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002293`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x1800023bb`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x1800023bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023a2`

## pseudocode

```c
__int64 __fastcall ETW_TRACE_HANDLER::DeleteTraceUrlList(const unsigned __int16 *a1)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  int v4; // edi
  const wchar_t *v5; // rsi
  wchar_t *v6; // rax
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rax
  CLKRHashTable *v8; // rcx
  TRACE_URLS_LIST *v9; // rbx
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  TRACE_URLS_LIST *v14; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v16; // [rsp+70h] [rbp-90h]
  unsigned __int16 v17[64]; // [rsp+90h] [rbp-70h] BYREF

  v13 = 0;
  v12 = 0;
  v11 = 0;
  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v15, v17, 0x40u);
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v3 = 0;
  if ( (unsigned int)v2 < 0x18 )
  {
    v4 = 0;
    goto LABEL_12;
  }
  v5 = a1 + 24;
  v6 = wcschr(v5, 0x2Fu);
  if ( v6 )
  {
    v4 = STRU::Copy((STRU *)v15, v5, v6 - v5);
    if ( v4 < 0 )
      goto LABEL_12;
    v5 = v16;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v4 = (**v7)(v7, &IID_INativeConfigurationSystem, &v13);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 56LL))(v13, &v12);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD))(*(_QWORD *)v12 + 48LL))(
             v12,
             v5,
             &v11,
             0);
      if ( v4 >= 0 )
        v3 = v11;
    }
  }
LABEL_12:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  STRU::~STRU((STRU *)v15);
  if ( v4 >= 0 )
  {
    v8 = (struct HTTP_TRACING_TABLE *)((char *)ETW_TRACE_HANDLER::sm_pHttpTracingTable + 8);
    if ( v3 )
    {
      v14 = 0;
      if ( !(unsigned int)CLKRHashTable::FindKey(v8, v3, &v14) )
      {
        v9 = v14;
        CLKRHashTable::DeleteRecord((char *)ETW_TRACE_HANDLER::sm_pHttpTracingTable + 8, v14);
        TRACE_URLS_LIST::Dereference(v9);
      }
    }
    else
    {
      CLKRHashTable::Clear(v8);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002238  mov     [rsp-8+arg_8], rbx
0x18000223d  mov     [rsp-8+arg_10], rsi
0x180002242  push    rbp
0x180002243  push    rdi
0x180002244  push    r14
0x180002246  lea     rbp, [rsp-20h]
0x18000224b  sub     rsp, 120h
0x180002252  mov     rax, cs:__security_cookie
0x180002259  xor     rax, rsp
0x18000225c  mov     [rbp+30h+var_20], rax
0x180002260  xor     r14d, r14d
0x180002263  mov     rsi, rcx
0x180002266  lea     rcx, [rbp+30h+var_A0]; void *
0x18000226a  mov     [rsp+130h+var_F0], r14
0x18000226f  xor     edx, edx; Val
0x180002271  mov     [rsp+130h+var_F8], r14
0x180002276  mov     r8d, 80h; Size
0x18000227c  mov     [rsp+130h+var_100], r14d
0x180002281  call    memset_0
0x180002286  lea     r8d, [r14+40h]
0x18000228a  lea     rdx, [rbp+30h+var_A0]
0x18000228e  lea     rcx, [rsp+130h+var_E0]
0x180002293  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002299  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000229d  inc     rax
0x1800022a0  cmp     [rsi+rax*2], r14w
0x1800022a5  jnz     short loc_18000229D
0x1800022a7  mov     ebx, r14d
0x1800022aa  cmp     eax, 18h
0x1800022ad  jnb     short loc_1800022B7
0x1800022af  mov     edi, r14d
0x1800022b2  jmp     loc_180002367
0x1800022b7  add     rsi, 30h ; '0'
0x1800022bb  mov     edx, 2Fh ; '/'; Ch
0x1800022c0  mov     rcx, rsi; Str
0x1800022c3  call    cs:__imp_wcschr
0x1800022c9  test    rax, rax
0x1800022cc  jz      short loc_1800022F0
0x1800022ce  sub     rax, rsi
0x1800022d1  lea     rcx, [rsp+130h+var_E0]
0x1800022d6  sar     rax, 1
0x1800022d9  mov     rdx, rsi
0x1800022dc  mov     r8d, eax
0x1800022df  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800022e5  mov     edi, eax
0x1800022e7  test    eax, eax
0x1800022e9  js      short loc_180002367
0x1800022eb  mov     rsi, [rsp+130h+var_C0]
0x1800022f0  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800022f7  mov     rax, [rcx]
0x1800022fa  mov     rax, [rax+38h]
0x1800022fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002303  mov     r9, rax
0x180002306  lea     r8, [rsp+130h+var_F0]
0x18000230b  lea     rdx, IID_INativeConfigurationSystem
0x180002312  mov     rcx, [rax]
0x180002315  mov     rax, [rcx]
0x180002318  mov     rcx, r9
0x18000231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002320  mov     edi, eax
0x180002322  test    eax, eax
0x180002324  js      short loc_180002367
0x180002326  mov     rcx, [rsp+130h+var_F0]
0x18000232b  lea     rdx, [rsp+130h+var_F8]
0x180002330  mov     rax, [rcx]
0x180002333  mov     rax, [rax+38h]
0x180002337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233c  mov     edi, eax
0x18000233e  test    eax, eax
0x180002340  js      short loc_180002367
0x180002342  mov     rcx, [rsp+130h+var_F8]
0x180002347  lea     r8, [rsp+130h+var_100]
0x18000234c  xor     r9d, r9d
0x18000234f  mov     rdx, rsi
0x180002352  mov     rax, [rcx]
0x180002355  mov     rax, [rax+30h]
0x180002359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235e  test    eax, eax
0x180002360  mov     edi, eax
0x180002362  cmovns  ebx, [rsp+130h+var_100]
0x180002367  mov     rcx, [rsp+130h+var_F8]
0x18000236c  test    rcx, rcx
0x18000236f  jz      short loc_180002382
0x180002371  mov     rax, [rcx]
0x180002374  mov     rax, [rax+10h]
0x180002378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000237d  mov     [rsp+130h+var_F8], r14
0x180002382  mov     rcx, [rsp+130h+var_F0]
0x180002387  test    rcx, rcx
0x18000238a  jz      short loc_18000239D
0x18000238c  mov     rax, [rcx]
0x18000238f  mov     rax, [rax+10h]
0x180002393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002398  mov     [rsp+130h+var_F0], r14
0x18000239d  lea     rcx, [rsp+130h+var_E0]
0x1800023a2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800023a8  test    edi, edi
0x1800023aa  js      short loc_1800023FA
0x1800023ac  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x1800023b3  add     rcx, 8
0x1800023b7  test    ebx, ebx
0x1800023b9  jnz     short loc_1800023C3
0x1800023bb  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x1800023c1  jmp     short loc_1800023FA
0x1800023c3  mov     edx, ebx
0x1800023c5  lea     r8, [rsp+130h+var_E8]
0x1800023ca  mov     [rsp+130h+var_E8], r14
0x1800023cf  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800023d5  test    eax, eax
0x1800023d7  jnz     short loc_1800023FA
0x1800023d9  mov     rbx, [rsp+130h+var_E8]
0x1800023de  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x1800023e5  mov     rdx, rbx
0x1800023e8  add     rcx, 8
0x1800023ec  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x1800023f2  mov     rcx, rbx; this
0x1800023f5  call    ?Dereference@TRACE_URLS_LIST@@QEAAXXZ; TRACE_URLS_LIST::Dereference(void)
0x1800023fa  mov     eax, edi
0x1800023fc  mov     rcx, [rbp+30h+var_20]
0x180002400  xor     rcx, rsp; StackCookie
0x180002403  call    __security_check_cookie
0x180002408  lea     r11, [rsp+130h+var_10]
0x180002410  mov     rbx, [r11+28h]
0x180002414  mov     rsi, [r11+30h]
0x180002418  mov     rsp, r11
0x18000241b  pop     r14
0x18000241d  pop     rdi
0x18000241e  pop     rbp
0x18000241f  retn
```
