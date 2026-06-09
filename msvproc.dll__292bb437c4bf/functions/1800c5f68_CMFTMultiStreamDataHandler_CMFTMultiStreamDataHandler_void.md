# CMFTMultiStreamDataHandler::~CMFTMultiStreamDataHandler(void)

- ea: `0x1800c5f68`
- end: `0x1800c603f`
- name: `??1CMFTMultiStreamDataHandler@@UEAA@XZ`
- size: `215`
- prototype: `void __fastcall(CMFTMultiStreamDataHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002404c`
- `0x1800c6370`

## callees

- `0x1800c5f68`
- `0x1800c91e4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5f87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6001`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c600a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c600a`

## pseudocode

```c
void __fastcall CMFTMultiStreamDataHandler::~CMFTMultiStreamDataHandler(CMFTMultiStreamDataHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  *(_QWORD *)this = &CMFTMultiStreamDataHandler::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v3 = (__int64 *)((char *)this + 16);
  v4 = *((_QWORD *)this + 2);
  if ( (*((_QWORD *)this + 3) - v4) >> 3 )
  {
    v5 = 0;
    do
    {
      v6 = *(_QWORD *)(v4 + 8 * v5);
      if ( v6 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        *(_QWORD *)(*v3 + 8 * v5) = 0;
      }
      v4 = *v3;
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < (unsigned __int64)((__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 3) );
  }
  *((_QWORD *)this + 3) = v4;
  v7 = *((_QWORD *)this + 11);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 11) = 0;
  }
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit((char *)this + 64);
  utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit((char *)this + 40);
  utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit((char *)this + 16);
  *(_QWORD *)this = &CMFTDataHandler::`vftable';
}

```

## disassembly

```asm
0x1800c5f68  push    rbx
0x1800c5f6a  push    rbp
0x1800c5f6b  push    rsi
0x1800c5f6c  push    rdi
0x1800c5f6d  push    r14
0x1800c5f6f  sub     rsp, 20h
0x1800c5f73  lea     rax, ??_7CMFTMultiStreamDataHandler@@6B@; const CMFTMultiStreamDataHandler::`vftable'
0x1800c5f7a  mov     rbx, rcx
0x1800c5f7d  lea     rbp, [rcx+60h]
0x1800c5f81  mov     [rcx], rax
0x1800c5f84  mov     rcx, rbp; lpCriticalSection
0x1800c5f87  call    cs:__imp_EnterCriticalSection
0x1800c5f8d  lea     rdi, [rbx+10h]
0x1800c5f91  mov     rdx, [rdi]
0x1800c5f94  mov     rax, [rdi+8]
0x1800c5f98  sub     rax, rdx
0x1800c5f9b  sar     rax, 3
0x1800c5f9f  test    rax, rax
0x1800c5fa2  jz      short loc_1800C5FDD
0x1800c5fa4  xor     esi, esi
0x1800c5fa6  mov     rcx, [rdx+rsi*8]
0x1800c5faa  test    rcx, rcx
0x1800c5fad  jz      short loc_1800C5FC6
0x1800c5faf  mov     rax, [rcx]
0x1800c5fb2  mov     rax, [rax+10h]
0x1800c5fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5fbb  mov     rax, [rdi]
0x1800c5fbe  mov     qword ptr [rax+rsi*8], 0
0x1800c5fc6  mov     rdx, [rdi]
0x1800c5fc9  inc     esi
0x1800c5fcb  mov     rcx, [rdi+8]
0x1800c5fcf  sub     rcx, rdx
0x1800c5fd2  mov     eax, esi
0x1800c5fd4  sar     rcx, 3
0x1800c5fd8  cmp     rax, rcx
0x1800c5fdb  jb      short loc_1800C5FA6
0x1800c5fdd  mov     [rdi+8], rdx
0x1800c5fe1  mov     rcx, [rbx+58h]
0x1800c5fe5  test    rcx, rcx
0x1800c5fe8  jz      short loc_1800C5FFE
0x1800c5fea  mov     rax, [rcx]
0x1800c5fed  mov     rax, [rax+10h]
0x1800c5ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5ff6  mov     qword ptr [rbx+58h], 0
0x1800c5ffe  mov     rcx, rbp; lpCriticalSection
0x1800c6001  call    cs:__imp_LeaveCriticalSection
0x1800c6007  mov     rcx, rbp; lpCriticalSection
0x1800c600a  call    cs:__imp_DeleteCriticalSection
0x1800c6010  lea     rcx, [rbx+40h]
0x1800c6014  call    ?_Uninit@?$vector@PEAUIMFSample@@V?$allocator@PEAUIMFSample@@@utl@@@utl@@AEAAXXZ; utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit(void)
0x1800c6019  lea     rcx, [rbx+28h]
0x1800c601d  call    ?_Uninit@?$vector@PEAUIMFSample@@V?$allocator@PEAUIMFSample@@@utl@@@utl@@AEAAXXZ; utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit(void)
0x1800c6022  mov     rcx, rdi
0x1800c6025  call    ?_Uninit@?$vector@PEAUIMFSample@@V?$allocator@PEAUIMFSample@@@utl@@@utl@@AEAAXXZ; utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit(void)
0x1800c602a  lea     rax, ??_7CMFTDataHandler@@6B@; const CMFTDataHandler::`vftable'
0x1800c6031  mov     [rbx], rax
0x1800c6034  add     rsp, 20h
0x1800c6038  pop     r14
0x1800c603a  pop     rdi
0x1800c603b  pop     rsi
0x1800c603c  pop     rbp
0x1800c603d  pop     rbx
0x1800c603e  retn
```
