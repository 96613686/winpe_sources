# VIDMM_EXISTINGSYSMEM_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x140119a70`
- end: `0x140119c79`
- name: `?AllocateGlobal@VIDMM_EXISTINGSYSMEM_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `521`
- prototype: `int __high(struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned int, enum VIDMM_HEAP_ALLOCATE_FLAGS, void *, enum VIDMM_PROCESS_HEAP_MAPPING, struct VIDMM_HEAP_ALLOC **, void **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140058760`
- `0x140119a70`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x140119b1a`
- `ntoskrnl!MmIsUserAddress` at `0x140119b1a`
- `ntoskrnl!ProbeForRead` at `0x140119b52`
- `ntoskrnl!ProbeForRead` at `0x140119b52`
- `ntoskrnl!ProbeForWrite` at `0x140119b60`
- `ntoskrnl!ProbeForWrite` at `0x140119b60`
- `watchdog!WdLogSingleEntry1` at `0x140119ac6`
- `watchdog!WdLogSingleEntry1` at `0x140119b7c`
- `watchdog!WdLogSingleEntry1` at `0x140119ac6`
- `watchdog!WdLogSingleEntry1` at `0x140119b7c`

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
    if ( (**(_DWORD **)(a2 + 384) & 0x10) != 0 )
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
    _InterlockedIncrement(&dword_1400868A0);
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
0x140119a70  mov     [rsp+arg_10], rsi
0x140119a75  mov     [rsp+arg_0], rcx
0x140119a7a  push    rdi
0x140119a7b  push    r12
0x140119a7d  push    r13
0x140119a7f  push    r14
0x140119a81  push    r15
0x140119a83  sub     rsp, 50h
0x140119a87  mov     rsi, r8
0x140119a8a  mov     r15, rdx
0x140119a8d  mov     r14, rcx
0x140119a90  mov     r12d, [rdx+18h]
0x140119a94  mov     edx, 66316956h
0x140119a99  mov     ecx, 28h ; '('
0x140119a9e  mov     r8d, 100h
0x140119aa4  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140119aa9  mov     rdi, rax
0x140119aac  mov     [rsp+78h+arg_8], rax
0x140119ab4  test    rax, rax
0x140119ab7  jnz     short loc_140119B0B
0x140119ab9  lock inc cs:dword_1400868A0
0x140119ac0  mov     rdx, r15
0x140119ac3  lea     ecx, [rax+6]
0x140119ac6  call    cs:__imp_WdLogSingleEntry1
0x140119acd  nop     dword ptr [rax+rax+00h]
0x140119ad2  mov     cs:WdLogGlobalForLineNumber, 21Bh
0x140119adc  mov     [rsp+78h+var_40], rdi
0x140119ae1  mov     [rsp+78h+var_48], rdi
0x140119ae6  mov     [rsp+78h+var_50], rdi
0x140119aeb  mov     [rsp+78h+var_58], r15
0x140119af0  lea     r9, aFailedToAlloca_1; "Failed to allocate VIDMM_EXISTINGSYSMEM"...
0x140119af7  mov     edx, 40001h
0x140119afc  call    DxgkLogInternalTriageEvent
0x140119b01  mov     esi, 0C0000017h
0x140119b06  jmp     loc_140119BD3
0x140119b0b  and     r12d, 40h
0x140119b0f  mov     r14, [rsp+78h+Address]
0x140119b17  mov     rcx, r14
0x140119b1a  call    cs:__imp_MmIsUserAddress
0x140119b21  nop     dword ptr [rax+rax+00h]
0x140119b26  xor     r13d, r13d
0x140119b29  test    al, al
0x140119b2b  setnz   r13b
0x140119b2f  mov     rax, [r15+180h]
0x140119b36  mov     ecx, [rax]
0x140119b38  test    cl, 10h
0x140119b3b  jz      loc_140119C21
0x140119b41  mov     r8d, 1; Alignment
0x140119b47  mov     rdx, rsi; Length
0x140119b4a  mov     rcx, r14; Address
0x140119b4d  test    r12d, r12d
0x140119b50  jz      short loc_140119B60
0x140119b52  call    cs:__imp_ProbeForRead
0x140119b59  nop     dword ptr [rax+rax+00h]
0x140119b5e  jmp     short loc_140119B6C
0x140119b60  call    cs:__imp_ProbeForWrite
0x140119b67  nop     dword ptr [rax+rax+00h]
0x140119b6c  jmp     loc_140119C21
0x140119b71  movsxd  rsi, eax
0x140119b74  mov     rdx, rsi
0x140119b77  mov     ecx, 1
0x140119b7c  call    cs:__imp_WdLogSingleEntry1
0x140119b83  nop     dword ptr [rax+rax+00h]
0x140119b88  mov     cs:WdLogGlobalForLineNumber, 23Eh
0x140119b92  mov     [rsp+78h+var_40], 0
0x140119b9b  mov     [rsp+78h+var_48], 0
0x140119ba4  mov     [rsp+78h+var_50], 0
0x140119bad  mov     [rsp+78h+var_58], rsi
0x140119bb2  lea     r9, aExceptionOccur_3; "Exception occurred trying to use existi"...
0x140119bb9  mov     edx, 40000h
0x140119bbe  call    DxgkLogInternalTriageEvent
0x140119bc3  mov     r14, [rsp+78h+arg_0]
0x140119bcb  mov     rdi, [rsp+78h+arg_8]
0x140119bd3  test    rdi, rdi
0x140119bd6  jz      short loc_140119BF4
0x140119bd8  mov     rax, [r14]
0x140119bdb  mov     rax, [rax+88h]
0x140119be2  xor     r9d, r9d
0x140119be5  mov     r8, [rdi+8]
0x140119be9  mov     rdx, rdi
0x140119bec  mov     rcx, r14
0x140119bef  call    _guard_dispatch_icall
0x140119bf4  mov     rcx, [rsp+78h+arg_48]
0x140119bfc  mov     byte ptr [rcx], 0
0x140119bff  mov     rcx, [rsp+78h+arg_38]
0x140119c07  mov     qword ptr [rcx], 0
0x140119c0e  mov     rcx, [rsp+78h+arg_40]
0x140119c16  mov     qword ptr [rcx], 0
0x140119c1d  mov     eax, esi
0x140119c1f  jmp     short loc_140119C62
0x140119c21  mov     eax, [rdi+20h]
0x140119c24  and     eax, 0FFFFFFFEh
0x140119c27  or      eax, r13d
0x140119c2a  mov     [rdi+20h], eax
0x140119c2d  mov     [rdi+8], r14
0x140119c31  mov     rax, [rsp+78h+arg_48]
0x140119c39  mov     byte ptr [rax], 1
0x140119c3c  mov     rax, [rsp+78h+arg_38]
0x140119c44  mov     [rax], rdi
0x140119c47  mov     eax, [rdi+20h]
0x140119c4a  test    al, 1
0x140119c4c  jnz     short loc_140119C5D
0x140119c4e  mov     rcx, [rdi+8]
0x140119c52  mov     rax, [rsp+78h+arg_40]
0x140119c5a  mov     [rax], rcx
0x140119c5d  mov     [rdi], rsi
0x140119c60  xor     eax, eax
0x140119c62  mov     rsi, [rsp+78h+arg_10]
0x140119c6a  add     rsp, 50h
0x140119c6e  pop     r15
0x140119c70  pop     r14
0x140119c72  pop     r13
0x140119c74  pop     r12
0x140119c76  pop     rdi
0x140119c77  retn
```
