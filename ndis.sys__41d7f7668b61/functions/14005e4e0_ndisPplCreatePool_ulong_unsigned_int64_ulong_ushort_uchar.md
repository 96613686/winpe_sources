# ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)

- ea: `0x14005e4e0`
- end: `0x14005e7ae`
- name: `?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z`
- size: `718`
- prototype: `struct PPL_POOL_HANDLE__ *(unsigned int, unsigned __int64, unsigned int, unsigned __int16, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14005dee0`
- `0x14005e1a0`

## callees

- `0x14005e4e0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14005e562`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e5e6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e6f9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e562`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e5e6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e6f9`
- `ntoskrnl!ExAllocatePool2` at `0x14005e535`
- `ntoskrnl!ExAllocatePool2` at `0x14005e535`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005e6ab`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005e799`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005e6ab`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005e799`
- `ntoskrnl!InitializeSListHead` at `0x14005e626`
- `ntoskrnl!InitializeSListHead` at `0x14005e739`
- `ntoskrnl!InitializeSListHead` at `0x14005e626`
- `ntoskrnl!InitializeSListHead` at `0x14005e739`

## pseudocode

```c
struct PPL_POOL_HANDLE__ *__fastcall ndisPplCreatePool(
        __int64 a1,
        SIZE_T a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5)
{
  ULONG Tag; // r15d
  unsigned __int64 v7; // rax
  unsigned int v8; // ebp
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  struct PPL_POOL_HANDLE__ *result; // rax
  struct PPL_POOL_HANDLE__ *v12; // r14
  char *v13; // rbx
  unsigned int v14; // esi

  Tag = a3;
  v7 = ndisMaxNumberOfProcessors + 1;
  if ( ndisMaxNumberOfProcessors <= 1 )
    v7 = ndisMaxNumberOfProcessors;
  v8 = v7;
  v10 = v7;
  v9 = v7 << 8;
  if ( !is_mul_ok(0x100u, v10) || v9 + 128 < v9 )
    return 0;
  result = (struct PPL_POOL_HANDLE__ *)ExAllocatePool2(72, v9 + 128, a3);
  v12 = result;
  if ( result )
  {
    *((_OWORD *)result + 1) = 0;
    *((_QWORD *)result + 4) = 0;
    *(_QWORD *)result = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)result + 1);
    if ( v8 )
    {
      v13 = (char *)v12 + 128;
      v14 = 0;
      if ( a5 )
      {
        do
        {
          if ( v13 )
          {
            *(_OWORD *)(v13 + 216) = 0;
            *(_OWORD *)(v13 + 232) = 0;
            *((_QWORD *)v13 + 31) = 0;
            memset(v13, 0, 0xD0u);
            KeInitializeSpinLock((PKSPIN_LOCK)v13 + 26);
            *(_DWORD *)(v13 + 217) = 0;
            *(_WORD *)(v13 + 221) = 0;
            v13[223] = 0;
            *((_OWORD *)v13 + 14) = 0;
            *((_OWORD *)v13 + 15) = 0;
          }
          if ( !v14 )
          {
            ExInitializeLookasideListEx(
              (PLOOKASIDE_LIST_EX)v13,
              ndisAllocateFromNPagedPool,
              ndisFreeNblToNPagedPool,
              NonPagedPoolNx,
              0,
              a2,
              Tag,
              0x400u);
            v13[216] = 1;
          }
          InitializeSListHead((PSLIST_HEADER)v13 + 8);
          *((_QWORD *)v13 + 24) = v13;
          ++v14;
          *((_QWORD *)v13 + 25) = v13 + 128;
          v13 += 256;
        }
        while ( v14 < v8 );
      }
      else
      {
        do
        {
          if ( v13 )
          {
            *(_OWORD *)(v13 + 216) = 0;
            *(_OWORD *)(v13 + 232) = 0;
            *((_QWORD *)v13 + 31) = 0;
            memset(v13, 0, 0xD0u);
            KeInitializeSpinLock((PKSPIN_LOCK)v13 + 26);
            *(_DWORD *)(v13 + 217) = 0;
            *(_WORD *)(v13 + 221) = 0;
            v13[223] = 0;
            *((_OWORD *)v13 + 14) = 0;
            *((_OWORD *)v13 + 15) = 0;
          }
          if ( !v14 )
          {
            ExInitializeLookasideListEx(
              (PLOOKASIDE_LIST_EX)v13,
              ndisAllocateFromNPagedPool,
              ndisFreeToNPagedPool,
              NonPagedPoolNx,
              0,
              a2,
              Tag,
              0x400u);
            v13[216] = 1;
          }
          InitializeSListHead((PSLIST_HEADER)v13 + 8);
          *((_QWORD *)v13 + 24) = v13;
          ++v14;
          *((_QWORD *)v13 + 25) = v13 + 128;
          v13 += 256;
        }
        while ( v14 < v8 );
      }
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x14005e4e0  push    rbp
0x14005e4e2  push    r13
0x14005e4e4  push    r15
0x14005e4e6  sub     rsp, 60h
0x14005e4ea  mov     ecx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x14005e4f0  xor     r9d, r9d
0x14005e4f3  cmp     ecx, 1
0x14005e4f6  mov     r13, rdx
0x14005e4f9  mov     r15d, r8d
0x14005e4fc  lea     eax, [rcx+1]
0x14005e4ff  cmovbe  eax, ecx
0x14005e502  mov     ecx, 100h
0x14005e507  mov     ebp, eax
0x14005e509  mul     rcx
0x14005e50c  test    rdx, rdx
0x14005e50f  jz      short loc_14005E51F
0x14005e511  mov     rax, r9
0x14005e514  add     rsp, 60h
0x14005e518  pop     r15
0x14005e51a  pop     r13
0x14005e51c  pop     rbp
0x14005e51d  retn
0x14005e51f  lea     rdx, [rax+80h]
0x14005e526  cmp     rdx, rax
0x14005e529  jb      short loc_14005E511
0x14005e52b  mov     ecx, 48h ; 'H'
0x14005e530  mov     [rsp+78h+var_28], r14
0x14005e535  call    cs:__imp_ExAllocatePool2
0x14005e53c  nop     dword ptr [rax+rax+00h]
0x14005e541  mov     r14, rax
0x14005e544  test    rax, rax
0x14005e547  jz      loc_14005E671
0x14005e54d  xor     eax, eax
0x14005e54f  lea     rcx, [r14+8]; SpinLock
0x14005e553  xorps   xmm0, xmm0
0x14005e556  movups  xmmword ptr [r14+10h], xmm0
0x14005e55b  mov     [r14+20h], rax
0x14005e55f  mov     [r14], rax
0x14005e562  call    cs:__imp_KeInitializeSpinLock
0x14005e569  nop     dword ptr [rax+rax+00h]
0x14005e56e  test    ebp, ebp
0x14005e570  jz      loc_14005E66E
0x14005e576  mov     [rsp+78h+arg_0], rbx
0x14005e57e  lea     rbx, [r14+80h]
0x14005e585  mov     [rsp+78h+arg_8], rsi
0x14005e58d  xor     esi, esi
0x14005e58f  mov     [rsp+78h+arg_10], rdi
0x14005e597  mov     [rsp+78h+var_20], r12
0x14005e59c  cmp     [rsp+78h+arg_20], sil
0x14005e5a4  jz      loc_14005E6C3
0x14005e5aa  nop     word ptr [rax+rax+00h]
0x14005e5b0  test    rbx, rbx
0x14005e5b3  jz      short loc_14005E618
0x14005e5b5  xorps   xmm0, xmm0
0x14005e5b8  xor     eax, eax
0x14005e5ba  movups  xmmword ptr [rbx+0D8h], xmm0
0x14005e5c1  xor     edx, edx; Val
0x14005e5c3  mov     r8d, 0D0h; Size
0x14005e5c9  movups  xmmword ptr [rbx+0E8h], xmm0
0x14005e5d0  mov     rcx, rbx; void *
0x14005e5d3  mov     [rbx+0F8h], rax
0x14005e5da  call    memset
0x14005e5df  lea     rcx, [rbx+0D0h]; SpinLock
0x14005e5e6  call    cs:__imp_KeInitializeSpinLock
0x14005e5ed  nop     dword ptr [rax+rax+00h]
0x14005e5f2  xor     eax, eax
0x14005e5f4  xorps   xmm0, xmm0
0x14005e5f7  mov     [rbx+0D9h], eax
0x14005e5fd  mov     [rbx+0DDh], ax
0x14005e604  mov     [rbx+0DFh], al
0x14005e60a  movups  xmmword ptr [rbx+0E0h], xmm0
0x14005e611  movups  xmmword ptr [rbx+0F0h], xmm0
0x14005e618  test    esi, esi
0x14005e61a  jz      short loc_14005E67B
0x14005e61c  lea     rdi, [rbx+80h]
0x14005e623  mov     rcx, rdi; SListHead
0x14005e626  call    cs:__imp_InitializeSListHead
0x14005e62d  nop     dword ptr [rax+rax+00h]
0x14005e632  mov     [rbx+0C0h], rbx
0x14005e639  inc     esi
0x14005e63b  mov     [rbx+0C8h], rdi
0x14005e642  add     rbx, 100h
0x14005e649  cmp     esi, ebp
0x14005e64b  jb      loc_14005E5B0
0x14005e651  mov     r12, [rsp+78h+var_20]
0x14005e656  mov     rdi, [rsp+78h+arg_10]
0x14005e65e  mov     rsi, [rsp+78h+arg_8]
0x14005e666  mov     rbx, [rsp+78h+arg_0]
0x14005e66e  mov     rax, r14
0x14005e671  mov     r14, [rsp+78h+var_28]
0x14005e676  jmp     loc_14005E514
0x14005e67b  mov     [rsp+78h+Depth], 400h; Depth
0x14005e682  lea     r8, ndisFreeNblToNPagedPool; Free
0x14005e689  mov     [rsp+78h+Tag], r15d; Tag
0x14005e68e  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14005e695  mov     [rsp+78h+Size], r13; Size
0x14005e69a  mov     r9d, 200h; PoolType
0x14005e6a0  mov     rcx, rbx; Lookaside
0x14005e6a3  mov     [rsp+78h+Flags], 0; Flags
0x14005e6ab  call    cs:__imp_ExInitializeLookasideListEx
0x14005e6b2  nop     dword ptr [rax+rax+00h]
0x14005e6b7  mov     byte ptr [rbx+0D8h], 1
0x14005e6be  jmp     loc_14005E61C
0x14005e6c3  test    rbx, rbx
0x14005e6c6  jz      short loc_14005E72B
0x14005e6c8  xorps   xmm0, xmm0
0x14005e6cb  xor     eax, eax
0x14005e6cd  movups  xmmword ptr [rbx+0D8h], xmm0
0x14005e6d4  xor     edx, edx; Val
0x14005e6d6  mov     r8d, 0D0h; Size
0x14005e6dc  movups  xmmword ptr [rbx+0E8h], xmm0
0x14005e6e3  mov     rcx, rbx; void *
0x14005e6e6  mov     [rbx+0F8h], rax
0x14005e6ed  call    memset
0x14005e6f2  lea     rcx, [rbx+0D0h]; SpinLock
0x14005e6f9  call    cs:__imp_KeInitializeSpinLock
0x14005e700  nop     dword ptr [rax+rax+00h]
0x14005e705  xor     eax, eax
0x14005e707  xorps   xmm0, xmm0
0x14005e70a  mov     [rbx+0D9h], eax
0x14005e710  mov     [rbx+0DDh], ax
0x14005e717  mov     [rbx+0DFh], al
0x14005e71d  movups  xmmword ptr [rbx+0E0h], xmm0
0x14005e724  movups  xmmword ptr [rbx+0F0h], xmm0
0x14005e72b  test    esi, esi
0x14005e72d  jz      short loc_14005E769
0x14005e72f  lea     rdi, [rbx+80h]
0x14005e736  mov     rcx, rdi; SListHead
0x14005e739  call    cs:__imp_InitializeSListHead
0x14005e740  nop     dword ptr [rax+rax+00h]
0x14005e745  mov     [rbx+0C0h], rbx
0x14005e74c  inc     esi
0x14005e74e  mov     [rbx+0C8h], rdi
0x14005e755  add     rbx, 100h
0x14005e75c  cmp     esi, ebp
0x14005e75e  jb      loc_14005E6C3
0x14005e764  jmp     loc_14005E651
0x14005e769  mov     [rsp+78h+Depth], 400h; Depth
0x14005e770  lea     r8, ndisFreeToNPagedPool; Free
0x14005e777  mov     [rsp+78h+Tag], r15d; Tag
0x14005e77c  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14005e783  mov     [rsp+78h+Size], r13; Size
0x14005e788  mov     r9d, 200h; PoolType
0x14005e78e  mov     rcx, rbx; Lookaside
0x14005e791  mov     [rsp+78h+Flags], 0; Flags
0x14005e799  call    cs:__imp_ExInitializeLookasideListEx
0x14005e7a0  nop     dword ptr [rax+rax+00h]
0x14005e7a5  mov     byte ptr [rbx+0D8h], 1
0x14005e7ac  jmp     short loc_14005E72F
```
