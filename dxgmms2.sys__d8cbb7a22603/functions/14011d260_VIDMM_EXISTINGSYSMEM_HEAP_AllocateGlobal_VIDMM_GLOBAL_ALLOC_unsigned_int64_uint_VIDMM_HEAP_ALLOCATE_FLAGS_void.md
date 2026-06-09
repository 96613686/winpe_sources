# VIDMM_EXISTINGSYSMEM_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x14011d260`
- end: `0x14011d469`
- name: `?AllocateGlobal@VIDMM_EXISTINGSYSMEM_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `521`
- prototype: `int __high(struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned int, enum VIDMM_HEAP_ALLOCATE_FLAGS, void *, enum VIDMM_PROCESS_HEAP_MAPPING, struct VIDMM_HEAP_ALLOC **, void **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003490`
- `0x140004268`
- `0x140059030`
- `0x14011d260`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x14011d30a`
- `ntoskrnl!MmIsUserAddress` at `0x14011d30a`
- `ntoskrnl!ProbeForRead` at `0x14011d342`
- `ntoskrnl!ProbeForRead` at `0x14011d342`
- `ntoskrnl!ProbeForWrite` at `0x14011d350`
- `ntoskrnl!ProbeForWrite` at `0x14011d350`
- `watchdog!WdLogSingleEntry1` at `0x14011d2b6`
- `watchdog!WdLogSingleEntry1` at `0x14011d36c`
- `watchdog!WdLogSingleEntry1` at `0x14011d2b6`
- `watchdog!WdLogSingleEntry1` at `0x14011d36c`

## pseudocode

```c
__int64 __fastcall VIDMM_EXISTINGSYSMEM_HEAP::AllocateGlobal(
        __int64 a1,
        __int64 a2,
        SIZE_T a3,
        __int64 a4,
        __int64 a5,
        volatile void *Address,
        __int64 a7,
        __int64 *a8,
        _QWORD *a9,
        _BYTE *a10)
{
  int v12; // r12d
  __int64 v13; // rdi
  int v14; // ecx
  int v15; // r8d
  int v16; // r12d
  BOOL v17; // r13d

  v12 = *(_DWORD *)(a2 + 24);
  v13 = operator new(40, 1714514262, 256);
  if ( v13 )
  {
    v16 = v12 & 0x40;
    v17 = (unsigned __int8)MmIsUserAddress(Address) != 0;
    if ( (**(_DWORD **)(a2 + 392) & 0x10) != 0 )
    {
      if ( v16 )
        ProbeForRead(Address, a3, 1u);
      else
        ProbeForWrite(Address, a3, 1u);
    }
    *(_DWORD *)(v13 + 32) = v17 | *(_DWORD *)(v13 + 32) & 0xFFFFFFFE;
    *(_QWORD *)(v13 + 8) = Address;
    *a10 = 1;
    *a8 = v13;
    if ( (*(_DWORD *)(v13 + 32) & 1) == 0 )
      *a9 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)v13 = a3;
    return 0;
  }
  else
  {
    _InterlockedIncrement(&dword_140087880);
    WdLogSingleEntry1(6, a2);
    WdLogGlobalForLineNumber = 539;
    DxgkLogInternalTriageEvent(
      v14,
      262145,
      v15,
      (unsigned int)L"Failed to allocate VIDMM_EXISTINGSYSMEM_HEAP_ALLOC for global alloc 0x%.16x",
      a2,
      0,
      0,
      0);
    *a10 = 0;
    *a8 = 0;
    *a9 = 0;
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14011d260  mov     [rsp+arg_10], rsi
0x14011d265  mov     [rsp+arg_0], rcx
0x14011d26a  push    rdi
0x14011d26b  push    r12
0x14011d26d  push    r13
0x14011d26f  push    r14
0x14011d271  push    r15
0x14011d273  sub     rsp, 50h
0x14011d277  mov     rsi, r8
0x14011d27a  mov     r15, rdx
0x14011d27d  mov     r14, rcx
0x14011d280  mov     r12d, [rdx+18h]
0x14011d284  mov     edx, 66316956h
0x14011d289  mov     ecx, 28h ; '('
0x14011d28e  mov     r8d, 100h
0x14011d294  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011d299  mov     rdi, rax
0x14011d29c  mov     [rsp+78h+arg_8], rax
0x14011d2a4  test    rax, rax
0x14011d2a7  jnz     short loc_14011D2FB
0x14011d2a9  lock inc cs:dword_140087880
0x14011d2b0  mov     rdx, r15
0x14011d2b3  lea     ecx, [rax+6]
0x14011d2b6  call    cs:__imp_WdLogSingleEntry1
0x14011d2bd  nop     dword ptr [rax+rax+00h]
0x14011d2c2  mov     cs:WdLogGlobalForLineNumber, 21Bh
0x14011d2cc  mov     [rsp+78h+var_40], rdi
0x14011d2d1  mov     [rsp+78h+var_48], rdi
0x14011d2d6  mov     [rsp+78h+var_50], rdi
0x14011d2db  mov     [rsp+78h+var_58], r15
0x14011d2e0  lea     r9, aFailedToAlloca_1; "Failed to allocate VIDMM_EXISTINGSYSMEM"...
0x14011d2e7  mov     edx, 40001h
0x14011d2ec  call    DxgkLogInternalTriageEvent
0x14011d2f1  mov     esi, 0C0000017h
0x14011d2f6  jmp     loc_14011D3C3
0x14011d2fb  and     r12d, 40h
0x14011d2ff  mov     r14, [rsp+78h+Address]
0x14011d307  mov     rcx, r14
0x14011d30a  call    cs:__imp_MmIsUserAddress
0x14011d311  nop     dword ptr [rax+rax+00h]
0x14011d316  xor     r13d, r13d
0x14011d319  test    al, al
0x14011d31b  setnz   r13b
0x14011d31f  mov     rax, [r15+188h]
0x14011d326  mov     ecx, [rax]
0x14011d328  test    cl, 10h
0x14011d32b  jz      loc_14011D411
0x14011d331  mov     r8d, 1; Alignment
0x14011d337  mov     rdx, rsi; Length
0x14011d33a  mov     rcx, r14; Address
0x14011d33d  test    r12d, r12d
0x14011d340  jz      short loc_14011D350
0x14011d342  call    cs:__imp_ProbeForRead
0x14011d349  nop     dword ptr [rax+rax+00h]
0x14011d34e  jmp     short loc_14011D35C
0x14011d350  call    cs:__imp_ProbeForWrite
0x14011d357  nop     dword ptr [rax+rax+00h]
0x14011d35c  jmp     loc_14011D411
0x14011d361  movsxd  rsi, eax
0x14011d364  mov     rdx, rsi
0x14011d367  mov     ecx, 1
0x14011d36c  call    cs:__imp_WdLogSingleEntry1
0x14011d373  nop     dword ptr [rax+rax+00h]
0x14011d378  mov     cs:WdLogGlobalForLineNumber, 23Eh
0x14011d382  mov     [rsp+78h+var_40], 0
0x14011d38b  mov     [rsp+78h+var_48], 0
0x14011d394  mov     [rsp+78h+var_50], 0
0x14011d39d  mov     [rsp+78h+var_58], rsi
0x14011d3a2  lea     r9, aExceptionOccur_3; "Exception occurred trying to use existi"...
0x14011d3a9  mov     edx, 40000h
0x14011d3ae  call    DxgkLogInternalTriageEvent
0x14011d3b3  mov     r14, [rsp+78h+arg_0]
0x14011d3bb  mov     rdi, [rsp+78h+arg_8]
0x14011d3c3  test    rdi, rdi
0x14011d3c6  jz      short loc_14011D3E4
0x14011d3c8  mov     rax, [r14]
0x14011d3cb  mov     rax, [rax+88h]
0x14011d3d2  xor     r9d, r9d
0x14011d3d5  mov     r8, [rdi+8]
0x14011d3d9  mov     rdx, rdi
0x14011d3dc  mov     rcx, r14
0x14011d3df  call    _guard_dispatch_icall
0x14011d3e4  mov     rcx, [rsp+78h+arg_48]
0x14011d3ec  mov     byte ptr [rcx], 0
0x14011d3ef  mov     rcx, [rsp+78h+arg_38]
0x14011d3f7  mov     qword ptr [rcx], 0
0x14011d3fe  mov     rcx, [rsp+78h+arg_40]
0x14011d406  mov     qword ptr [rcx], 0
0x14011d40d  mov     eax, esi
0x14011d40f  jmp     short loc_14011D452
0x14011d411  mov     eax, [rdi+20h]
0x14011d414  and     eax, 0FFFFFFFEh
0x14011d417  or      eax, r13d
0x14011d41a  mov     [rdi+20h], eax
0x14011d41d  mov     [rdi+8], r14
0x14011d421  mov     rax, [rsp+78h+arg_48]
0x14011d429  mov     byte ptr [rax], 1
0x14011d42c  mov     rax, [rsp+78h+arg_38]
0x14011d434  mov     [rax], rdi
0x14011d437  mov     eax, [rdi+20h]
0x14011d43a  test    al, 1
0x14011d43c  jnz     short loc_14011D44D
0x14011d43e  mov     rcx, [rdi+8]
0x14011d442  mov     rax, [rsp+78h+arg_40]
0x14011d44a  mov     [rax], rcx
0x14011d44d  mov     [rdi], rsi
0x14011d450  xor     eax, eax
0x14011d452  mov     rsi, [rsp+78h+arg_10]
0x14011d45a  add     rsp, 50h
0x14011d45e  pop     r15
0x14011d460  pop     r14
0x14011d462  pop     r13
0x14011d464  pop     r12
0x14011d466  pop     rdi
0x14011d467  retn
```
