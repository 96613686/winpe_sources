# CDirectMusicFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d1e0`
- end: `0x18000d31f`
- name: `?CreateInstance@CDirectMusicFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(CDirectMusicFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012c4`
- `0x18000d1e0`
- `0x1800125bc`
- `0x1800138f0`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d221`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d221`

## pseudocode

```c
__int64 __fastcall CDirectMusicFactory::CreateInstance(
        CDirectMusicFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CDirectMusic *v7; // rax
  CDirectMusic *v8; // rdi
  int v9; // esi
  unsigned int v10; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = (CDirectMusic *)malloc(0x98u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *((_DWORD *)v7 + 6) = 1;
  *(_QWORD *)v7 = &CDirectMusic::`vftable'{for `IDirectMusic8'};
  *((_QWORD *)v7 + 1) = &CDirectMusic::`vftable'{for `IDirectMusicPortNotify'};
  *((_QWORD *)v7 + 2) = &CDirectMusic::`vftable'{for `IDirectMusicPrivate'};
  *((_QWORD *)v7 + 4) = &CList<IDirectMusicPort *>::`vftable';
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_DWORD *)v7 + 14) = 0;
  *((_QWORD *)v7 + 8) = &CList<IDirectMusicPort *>::`vftable';
  *((_QWORD *)v7 + 9) = 0;
  *((_QWORD *)v7 + 10) = 0;
  *((_DWORD *)v7 + 22) = 0;
  *((_QWORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 13) = 0;
  *((_DWORD *)v7 + 28) = 0;
  *((_QWORD *)v7 + 15) = 0;
  *((_DWORD *)v7 + 36) = 7;
  _InterlockedIncrement(&g_cComponent);
  _InterlockedIncrement(&CDirectMusic::m_lInstanceCount);
  v9 = CDirectMusic::Init(v7);
  if ( v9 >= 0 )
  {
    v10 = (**(__int64 (__fastcall ***)(CDirectMusic *, const struct _GUID *, void **))v8)(v8, a3, a4);
    (*(void (__fastcall **)(CDirectMusic *))(*(_QWORD *)v8 + 16LL))(v8);
    return v10;
  }
  else
  {
    CDirectMusic::~CDirectMusic(v8);
    operator delete(v8);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18000d1e0  mov     [rsp+arg_0], rbx
0x18000d1e5  mov     [rsp+arg_8], rbp
0x18000d1ea  push    rsi
0x18000d1eb  push    rdi
0x18000d1ec  push    r14
0x18000d1ee  sub     rsp, 20h
0x18000d1f2  xor     r14d, r14d
0x18000d1f5  mov     rbx, r9
0x18000d1f8  mov     rbp, r8
0x18000d1fb  test    r9, r9
0x18000d1fe  jnz     short loc_18000D20A
0x18000d200  mov     eax, 80004003h
0x18000d205  jmp     loc_18000D30C
0x18000d20a  mov     [r9], r14
0x18000d20d  test    rdx, rdx
0x18000d210  jz      short loc_18000D21C
0x18000d212  mov     eax, 80040110h
0x18000d217  jmp     loc_18000D30C
0x18000d21c  mov     ecx, 98h; Size
0x18000d221  call    cs:__imp_malloc
0x18000d227  mov     [rsp+38h+arg_18], rax
0x18000d22c  mov     rdi, rax
0x18000d22f  test    rax, rax
0x18000d232  jz      loc_18000D307
0x18000d238  mov     dword ptr [rdi+18h], 1
0x18000d23f  lea     rax, ??_7CDirectMusic@@6BIDirectMusic8@@@; const CDirectMusic::`vftable'{for `IDirectMusic8'}
0x18000d246  mov     [rdi], rax
0x18000d249  lea     rax, ??_7CDirectMusic@@6BIDirectMusicPortNotify@@@; const CDirectMusic::`vftable'{for `IDirectMusicPortNotify'}
0x18000d250  mov     [rdi+8], rax
0x18000d254  lea     rax, ??_7CDirectMusic@@6BIDirectMusicPrivate@@@; const CDirectMusic::`vftable'{for `IDirectMusicPrivate'}
0x18000d25b  mov     [rdi+10h], rax
0x18000d25f  lea     rax, ??_7?$CList@PEAUIDirectMusicPort@@@@6B@; const CList<IDirectMusicPort *>::`vftable'
0x18000d266  mov     [rdi+20h], rax
0x18000d26a  lea     rax, ??_7?$CList@PEAUIDirectMusicPort@@@@6B@; const CList<IDirectMusicPort *>::`vftable'
0x18000d271  mov     [rdi+28h], r14
0x18000d275  mov     [rdi+30h], r14
0x18000d279  mov     [rdi+38h], r14d
0x18000d27d  mov     [rdi+40h], rax
0x18000d281  mov     [rdi+48h], r14
0x18000d285  mov     [rdi+50h], r14
0x18000d289  mov     [rdi+58h], r14d
0x18000d28d  mov     [rdi+60h], r14
0x18000d291  mov     [rdi+68h], r14
0x18000d295  mov     [rdi+70h], r14d
0x18000d299  mov     [rdi+78h], r14
0x18000d29d  mov     dword ptr [rdi+90h], 7
0x18000d2a7  lock inc cs:?g_cComponent@@3JA; long g_cComponent
0x18000d2ae  lock inc cs:?m_lInstanceCount@CDirectMusic@@0JA; long CDirectMusic::m_lInstanceCount
0x18000d2b5  test    rdi, rdi
0x18000d2b8  jz      short loc_18000D307
0x18000d2ba  mov     rcx, rdi; this
0x18000d2bd  call    ?Init@CDirectMusic@@QEAAJXZ; CDirectMusic::Init(void)
0x18000d2c2  mov     esi, eax
0x18000d2c4  mov     rcx, rdi; this
0x18000d2c7  test    eax, eax
0x18000d2c9  jns     short loc_18000D2E1
0x18000d2cb  call    ??1CDirectMusic@@QEAA@XZ; CDirectMusic::~CDirectMusic(void)
0x18000d2d0  mov     edx, 98h; unsigned __int64
0x18000d2d5  mov     rcx, rdi; void *
0x18000d2d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d2dd  mov     eax, esi
0x18000d2df  jmp     short loc_18000D30C
0x18000d2e1  mov     rax, [rdi]
0x18000d2e4  mov     r8, rbx
0x18000d2e7  mov     rdx, rbp
0x18000d2ea  mov     rax, [rax]
0x18000d2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f2  mov     rcx, [rdi]
0x18000d2f5  mov     ebx, eax
0x18000d2f7  mov     rax, [rcx+10h]
0x18000d2fb  mov     rcx, rdi
0x18000d2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d303  mov     eax, ebx
0x18000d305  jmp     short loc_18000D30C
0x18000d307  mov     eax, 8007000Eh
0x18000d30c  mov     rbx, [rsp+38h+arg_0]
0x18000d311  mov     rbp, [rsp+38h+arg_8]
0x18000d316  add     rsp, 20h
0x18000d31a  pop     r14
0x18000d31c  pop     rdi
0x18000d31d  pop     rsi
0x18000d31e  retn
```
