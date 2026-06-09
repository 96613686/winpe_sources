# TokenCache::CheckIfTokenValid(TokenCache::Item const &,ILogContext *)

- ea: `0x14000f380`
- end: `0x14000f4ee`
- name: `?CheckIfTokenValid@TokenCache@@MEAA_NAEBVItem@1@PEAVILogContext@@@Z`
- size: `366`
- prototype: `char __fastcall(TokenCache *this, const struct TokenCache::Item *, struct ILogContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000c384`
- `0x14000f380`
- `0x14000f4f4`
- `0x14001413c`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x14000f3c0`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x14000f3c0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14000f3b0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14000f3b0`

## pseudocode

```c
char __fastcall TokenCache::CheckIfTokenValid(
        TokenCache *this,
        const struct TokenCache::Item *a2,
        struct ILogContext *a3)
{
  __time64_t v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  __int64 v10; // [rsp+30h] [rbp-20h]
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  __int64 v13; // [rsp+48h] [rbp-8h] BYREF
  __time64_t Time; // [rsp+78h] [rbp+28h] BYREF
  __time64_t v15; // [rsp+88h] [rbp+38h] BYREF

  if ( !*(_DWORD *)(*((_QWORD *)a2 + 1) - 16LL) )
    return 0;
  if ( *((_QWORD *)a2 + 2) )
  {
    v5 = _time64(0);
    if ( _o__difftime64(*((_QWORD *)a2 + 2), v5) <= 3.0 )
    {
      if ( a3 )
      {
        v15 = v5;
        Time = *((_QWORD *)a2 + 2);
        ResourceMsg::ResourceMsg((ResourceMsg *)&v13, 0x4AAE0015u);
        ATL::CTime::FormatGmt(&Time);
        ResourceMsg::ResourceMsg((ResourceMsg *)&v11, 0x4AAE0015u);
        ATL::CTime::FormatGmt(&v15);
        Log::InfoInternal(a3, 1252589577, 1252917249);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
        v6 = (_QWORD *)(v11 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
        v7 = (_QWORD *)(v12 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
        v8 = (_QWORD *)(v13 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
      }
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000f380  mov     [rsp-18h+arg_0], rbx
0x14000f385  push    rbp
0x14000f386  push    rsi
0x14000f387  push    rdi
0x14000f388  mov     rbp, rsp
0x14000f38b  sub     rsp, 50h
0x14000f38f  mov     rdi, r8
0x14000f392  mov     rbx, rdx
0x14000f395  mov     rax, [rdx+8]
0x14000f399  cmp     dword ptr [rax-10h], 0
0x14000f39d  jz      loc_14000F4DB
0x14000f3a3  cmp     qword ptr [rdx+10h], 0
0x14000f3a8  jz      loc_14000F4EA
0x14000f3ae  xor     ecx, ecx; Time
0x14000f3b0  call    cs:__imp__time64
0x14000f3b6  mov     rsi, rax
0x14000f3b9  mov     rdx, rax
0x14000f3bc  mov     rcx, [rbx+10h]
0x14000f3c0  call    cs:__imp__o__difftime64
0x14000f3c6  comisd  xmm0, cs:__real@4008000000000000
0x14000f3ce  ja      loc_14000F4EA
0x14000f3d4  test    rdi, rdi
0x14000f3d7  jz      loc_14000F4DB
0x14000f3dd  mov     [rbp+arg_18], rsi
0x14000f3e1  mov     rax, [rbx+10h]
0x14000f3e5  mov     [rbp+Time], rax
0x14000f3e9  mov     esi, 4AAE0015h
0x14000f3ee  mov     edx, esi; unsigned int
0x14000f3f0  lea     rcx, [rbp+var_8]; this
0x14000f3f4  call    ??0ResourceMsg@@QEAA@K@Z; ResourceMsg::ResourceMsg(ulong)
0x14000f3f9  nop
0x14000f3fa  mov     r8, [rax]
0x14000f3fd  lea     rdx, [rbp+var_10]
0x14000f401  lea     rcx, [rbp+Time]; Time
0x14000f405  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x14000f40a  nop
0x14000f40b  mov     rbx, [rax]
0x14000f40e  mov     edx, esi; unsigned int
0x14000f410  lea     rcx, [rbp+var_18]; this
0x14000f414  call    ??0ResourceMsg@@QEAA@K@Z; ResourceMsg::ResourceMsg(ulong)
0x14000f419  nop
0x14000f41a  mov     r8, [rax]
0x14000f41d  lea     rdx, [rbp+var_20]
0x14000f421  lea     rcx, [rbp+arg_18]; Time
0x14000f425  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x14000f42a  nop
0x14000f42b  lea     r8d, [rsi-14h]
0x14000f42f  mov     [rsp+50h+var_30], rbx
0x14000f434  mov     r9, [rax]
0x14000f437  mov     edx, 4AA90009h
0x14000f43c  mov     rcx, rdi
0x14000f43f  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x14000f444  nop
0x14000f445  mov     rdx, [rbp+var_20]
0x14000f449  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f44d  or      ebx, 0FFFFFFFFh
0x14000f450  mov     eax, ebx
0x14000f452  lock xadd [rdx+10h], eax
0x14000f457  add     eax, ebx
0x14000f459  test    eax, eax
0x14000f45b  jg      short loc_14000F46D
0x14000f45d  mov     rcx, [rdx]
0x14000f460  mov     rax, [rcx]
0x14000f463  mov     rax, [rax+8]
0x14000f467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f46c  nop
0x14000f46d  mov     rdx, [rbp+var_18]
0x14000f471  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f475  mov     eax, ebx
0x14000f477  lock xadd [rdx+10h], eax
0x14000f47c  add     eax, ebx
0x14000f47e  test    eax, eax
0x14000f480  jg      short loc_14000F492
0x14000f482  mov     rcx, [rdx]
0x14000f485  mov     rax, [rcx]
0x14000f488  mov     rax, [rax+8]
0x14000f48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f491  nop
0x14000f492  mov     rdx, [rbp+var_10]
0x14000f496  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f49a  mov     eax, ebx
0x14000f49c  lock xadd [rdx+10h], eax
0x14000f4a1  add     eax, ebx
0x14000f4a3  test    eax, eax
0x14000f4a5  jg      short loc_14000F4B7
0x14000f4a7  mov     rcx, [rdx]
0x14000f4aa  mov     rax, [rcx]
0x14000f4ad  mov     rax, [rax+8]
0x14000f4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4b6  nop
0x14000f4b7  mov     rdx, [rbp+var_8]
0x14000f4bb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000f4bf  mov     eax, ebx
0x14000f4c1  lock xadd [rdx+10h], eax
0x14000f4c6  add     eax, ebx
0x14000f4c8  test    eax, eax
0x14000f4ca  jg      short loc_14000F4DB
0x14000f4cc  mov     rcx, [rdx]
0x14000f4cf  mov     rax, [rcx]
0x14000f4d2  mov     rax, [rax+8]
0x14000f4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4db  xor     al, al
0x14000f4dd  mov     rbx, [rsp+50h+arg_0]
0x14000f4e2  add     rsp, 50h
0x14000f4e6  pop     rdi
0x14000f4e7  pop     rsi
0x14000f4e8  pop     rbp
0x14000f4e9  retn
0x14000f4ea  mov     al, 1
0x14000f4ec  jmp     short loc_14000F4DD
```
