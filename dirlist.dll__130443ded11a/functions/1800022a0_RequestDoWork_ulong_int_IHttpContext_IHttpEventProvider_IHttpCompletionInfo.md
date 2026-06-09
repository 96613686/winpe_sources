# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800022a0`
- end: `0x1800023bd`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, void (__fastcall ***)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a80`
- `0x180001c20`

## callees

- `0x1800022a0`
- `0x180002968`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000233c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000233c`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, void (__fastcall ***a4)(_QWORD, __int64))
{
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // ebp

  if ( a1 != 128 )
    return 0;
  if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3) )
    return 0;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3);
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6) & 0x10) == 0 )
    return 0;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(a3, 1088);
  if ( v7 )
  {
    *(_QWORD *)v7 = &DIR_LISTING_HANDLER::`vftable';
    STRA::STRA((STRA *)(v7 + 1032), (char *)(v7 + 8), 0x400u);
    v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v8 + 8LL))(v8, v7, g_pDirListingModuleContext);
    if ( v9 >= 0 )
      return DIR_LISTING_HANDLER::DoWork(v7, a3);
    (**(void (__fastcall ***)(__int64))v7)(v7);
    (**a4)(a4, (unsigned int)v9);
  }
  else
  {
    (**a4)(a4, 2147942408LL);
  }
  return 2;
}

```

## disassembly

```asm
0x1800022a0  push    rbx
0x1800022a2  push    rbp
0x1800022a3  push    rsi
0x1800022a4  push    rdi
0x1800022a5  sub     rsp, 28h
0x1800022a9  mov     rsi, r9
0x1800022ac  mov     rbx, r8
0x1800022af  cmp     ecx, 80h
0x1800022b5  jnz     loc_1800023B2
0x1800022bb  mov     rax, [r8]
0x1800022be  mov     rcx, rbx
0x1800022c1  mov     rax, [rax+0D0h]
0x1800022c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022cd  test    rax, rax
0x1800022d0  jz      loc_1800023B2
0x1800022d6  mov     rax, [rbx]
0x1800022d9  mov     rcx, rbx
0x1800022dc  mov     rax, [rax+0D0h]
0x1800022e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e8  mov     rdx, rax
0x1800022eb  mov     rcx, [rax]
0x1800022ee  mov     rax, [rcx+38h]
0x1800022f2  mov     rcx, rdx
0x1800022f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fa  test    al, 10h
0x1800022fc  jz      loc_1800023B2
0x180002302  mov     rax, [rbx]
0x180002305  mov     edx, 440h
0x18000230a  mov     rcx, rbx
0x18000230d  mov     rax, [rax+90h]
0x180002314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002319  mov     rdi, rax
0x18000231c  test    rax, rax
0x18000231f  jz      short loc_180002398
0x180002321  lea     rax, ??_7DIR_LISTING_HANDLER@@6B@; const DIR_LISTING_HANDLER::`vftable'
0x180002328  mov     r8d, 400h
0x18000232e  lea     rdx, [rdi+8]
0x180002332  mov     [rdi], rax
0x180002335  lea     rcx, [rdi+408h]
0x18000233c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002342  mov     rcx, [rbx]
0x180002345  mov     rax, [rcx+38h]
0x180002349  mov     rcx, rbx
0x18000234c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002351  mov     r8, cs:?g_pDirListingModuleContext@@3PEAXEA; void * g_pDirListingModuleContext
0x180002358  mov     r9, rax
0x18000235b  mov     rdx, rdi
0x18000235e  mov     rcx, [rax]
0x180002361  mov     rax, [rcx+8]
0x180002365  mov     rcx, r9
0x180002368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000236d  mov     ebp, eax
0x18000236f  test    eax, eax
0x180002371  jns     short loc_18000238B
0x180002373  mov     rcx, [rdi]
0x180002376  mov     rax, [rcx]
0x180002379  mov     rcx, rdi
0x18000237c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002381  mov     rcx, [rsi]
0x180002384  mov     edx, ebp
0x180002386  mov     rax, [rcx]
0x180002389  jmp     short loc_1800023A3
0x18000238b  mov     rdx, rbx
0x18000238e  mov     rcx, rdi
0x180002391  call    ?DoWork@DIR_LISTING_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@@Z; DIR_LISTING_HANDLER::DoWork(IHttpContext *)
0x180002396  jmp     short loc_1800023B4
0x180002398  mov     rax, [rsi]
0x18000239b  mov     edx, 80070008h
0x1800023a0  mov     rax, [rax]
0x1800023a3  mov     rcx, rsi
0x1800023a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ab  mov     eax, 2
0x1800023b0  jmp     short loc_1800023B4
0x1800023b2  xor     eax, eax
0x1800023b4  add     rsp, 28h
0x1800023b8  pop     rdi
0x1800023b9  pop     rsi
0x1800023ba  pop     rbp
0x1800023bb  pop     rbx
0x1800023bc  retn
```
