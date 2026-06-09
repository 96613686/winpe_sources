# VARY_BY_CACHE_ENTRY::SetFileMonitor(IHttpContext *)

- ea: `0x18000770c`
- end: `0x180007879`
- name: `?SetFileMonitor@VARY_BY_CACHE_ENTRY@@QEAAJPEAVIHttpContext@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(VARY_BY_CACHE_ENTRY *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004220`

## callees

- `0x18000770c`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall VARY_BY_CACHE_ENTRY::SetFileMonitor(VARY_BY_CACHE_ENTRY *this, struct IHttpContext *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // rax
  unsigned int v12; // edi
  signed __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 85) )
    return 0;
  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6) )
  {
    v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9);
  }
  else
  {
    v7 = 0;
  }
  v13 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64, __int64, signed __int64 *))(*(_QWORD *)g_pGlobalInfo
                                                                                               + 192LL))(
             g_pGlobalInfo,
             v5,
             v7,
             &v13);
  if ( (int)result >= 0 )
  {
    v11 = (**(__int64 (__fastcall ***)(signed __int64))v13)(v13);
    v12 = (*(__int64 (__fastcall **)(__int64, void *, void *))(*(_QWORD *)v11 + 8LL))(
            v11,
            g_pMonitorStoredContext,
            g_pModuleId);
    if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147024811 )
    {
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v13 + 8LL))(v13);
      return v12;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 85, v13, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v13 + 8LL))(v13);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000770c  mov     [rsp+arg_8], rbx
0x180007711  mov     [rsp+arg_10], rsi
0x180007716  push    rdi
0x180007717  sub     rsp, 30h
0x18000771b  cmp     qword ptr [rcx+2A8h], 0
0x180007723  mov     rdi, rdx
0x180007726  mov     rbx, rcx
0x180007729  jnz     loc_180007867
0x18000772f  mov     rax, [rdx]
0x180007732  mov     rcx, rdx
0x180007735  mov     rax, [rax+0A0h]
0x18000773c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007741  mov     rcx, rax
0x180007744  mov     rdx, [rax]
0x180007747  mov     rax, [rdx+8]
0x18000774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007750  mov     rcx, [rdi]
0x180007753  mov     rsi, rax
0x180007756  mov     rax, [rcx+0A0h]
0x18000775d  mov     rcx, rdi
0x180007760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007765  mov     rdx, rax
0x180007768  mov     rcx, [rax]
0x18000776b  mov     rax, [rcx+10h]
0x18000776f  mov     rcx, rdx
0x180007772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007777  test    rax, rax
0x18000777a  jnz     short loc_180007781
0x18000777c  xor     r8d, r8d
0x18000777f  jmp     short loc_1800077BA
0x180007781  mov     rax, [rdi]
0x180007784  mov     rcx, rdi
0x180007787  mov     rax, [rax+0A0h]
0x18000778e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007793  mov     rdx, rax
0x180007796  mov     rcx, [rax]
0x180007799  mov     rax, [rcx+10h]
0x18000779d  mov     rcx, rdx
0x1800077a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a5  mov     rdx, rax
0x1800077a8  mov     rcx, [rax]
0x1800077ab  mov     rax, [rcx+38h]
0x1800077af  mov     rcx, rdx
0x1800077b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b7  mov     r8, rax
0x1800077ba  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800077c1  lea     r9, [rsp+38h+arg_0]
0x1800077c6  mov     [rsp+38h+arg_0], 0
0x1800077cf  mov     rdx, [rcx]
0x1800077d2  mov     rax, [rdx+0C0h]
0x1800077d9  mov     rdx, rsi
0x1800077dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e1  test    eax, eax
0x1800077e3  js      loc_180007869
0x1800077e9  mov     rcx, [rsp+38h+arg_0]
0x1800077ee  mov     rax, [rcx]
0x1800077f1  mov     rax, [rax]
0x1800077f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f9  mov     r8, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x180007800  mov     r9, rax
0x180007803  mov     rdx, cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA; MonitorStoredContext * g_pMonitorStoredContext
0x18000780a  mov     rcx, [rax]
0x18000780d  mov     rax, [rcx+8]
0x180007811  mov     rcx, r9
0x180007814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007819  mov     edi, eax
0x18000781b  mov     eax, 80000000h
0x180007820  lea     ecx, [rdi+rax]
0x180007823  test    eax, ecx
0x180007825  jnz     short loc_180007844
0x180007827  cmp     edi, 80070055h
0x18000782d  jz      short loc_180007844
0x18000782f  mov     rcx, [rsp+38h+arg_0]
0x180007834  mov     rdx, [rcx]
0x180007837  mov     rax, [rdx+8]
0x18000783b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007840  mov     eax, edi
0x180007842  jmp     short loc_180007869
0x180007844  mov     rcx, [rsp+38h+arg_0]
0x180007849  xor     eax, eax
0x18000784b  lock cmpxchg [rbx+2A8h], rcx
0x180007854  jz      short loc_180007867
0x180007856  mov     rcx, [rsp+38h+arg_0]
0x18000785b  mov     rax, [rcx]
0x18000785e  mov     rax, [rax+8]
0x180007862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007867  xor     eax, eax
0x180007869  mov     rbx, [rsp+38h+arg_8]
0x18000786e  mov     rsi, [rsp+38h+arg_10]
0x180007873  add     rsp, 30h
0x180007877  pop     rdi
0x180007878  retn
```
