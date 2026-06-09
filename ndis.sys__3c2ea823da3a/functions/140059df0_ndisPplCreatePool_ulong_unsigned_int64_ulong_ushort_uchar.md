# ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)

- ea: `0x140059df0`
- end: `0x14005a0be`
- name: `?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z`
- size: `718`
- prototype: `struct PPL_POOL_HANDLE__ *(unsigned int, unsigned __int64, unsigned int, unsigned __int16, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400597f0`
- `0x140059ab0`

## callees

- `0x140059df0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140059e72`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059ef6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005a009`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059e72`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059ef6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005a009`
- `ntoskrnl!ExAllocatePool2` at `0x140059e45`
- `ntoskrnl!ExAllocatePool2` at `0x140059e45`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140059fbb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005a0a9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140059fbb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005a0a9`
- `ntoskrnl!InitializeSListHead` at `0x140059f36`
- `ntoskrnl!InitializeSListHead` at `0x14005a049`
- `ntoskrnl!InitializeSListHead` at `0x140059f36`
- `ntoskrnl!InitializeSListHead` at `0x14005a049`

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
0x140059df0  push    rbp
0x140059df2  push    r13
0x140059df4  push    r15
0x140059df6  sub     rsp, 60h
0x140059dfa  mov     ecx, cs:?ndisMaxNumberOfProcessors@@3KA; ulong ndisMaxNumberOfProcessors
0x140059e00  xor     r9d, r9d
0x140059e03  cmp     ecx, 1
0x140059e06  mov     r13, rdx
0x140059e09  mov     r15d, r8d
0x140059e0c  lea     eax, [rcx+1]
0x140059e0f  cmovbe  eax, ecx
0x140059e12  mov     ecx, 100h
0x140059e17  mov     ebp, eax
0x140059e19  mul     rcx
0x140059e1c  test    rdx, rdx
0x140059e1f  jz      short loc_140059E2F
0x140059e21  mov     rax, r9
0x140059e24  add     rsp, 60h
0x140059e28  pop     r15
0x140059e2a  pop     r13
0x140059e2c  pop     rbp
0x140059e2d  retn
0x140059e2f  lea     rdx, [rax+80h]
0x140059e36  cmp     rdx, rax
0x140059e39  jb      short loc_140059E21
0x140059e3b  mov     ecx, 48h ; 'H'
0x140059e40  mov     [rsp+78h+var_28], r14
0x140059e45  call    cs:__imp_ExAllocatePool2
0x140059e4c  nop     dword ptr [rax+rax+00h]
0x140059e51  mov     r14, rax
0x140059e54  test    rax, rax
0x140059e57  jz      loc_140059F81
0x140059e5d  xor     eax, eax
0x140059e5f  lea     rcx, [r14+8]; SpinLock
0x140059e63  xorps   xmm0, xmm0
0x140059e66  movups  xmmword ptr [r14+10h], xmm0
0x140059e6b  mov     [r14+20h], rax
0x140059e6f  mov     [r14], rax
0x140059e72  call    cs:__imp_KeInitializeSpinLock
0x140059e79  nop     dword ptr [rax+rax+00h]
0x140059e7e  test    ebp, ebp
0x140059e80  jz      loc_140059F7E
0x140059e86  mov     [rsp+78h+arg_0], rbx
0x140059e8e  lea     rbx, [r14+80h]
0x140059e95  mov     [rsp+78h+arg_8], rsi
0x140059e9d  xor     esi, esi
0x140059e9f  mov     [rsp+78h+arg_10], rdi
0x140059ea7  mov     [rsp+78h+var_20], r12
0x140059eac  cmp     [rsp+78h+arg_20], sil
0x140059eb4  jz      loc_140059FD3
0x140059eba  nop     word ptr [rax+rax+00h]
0x140059ec0  test    rbx, rbx
0x140059ec3  jz      short loc_140059F28
0x140059ec5  xorps   xmm0, xmm0
0x140059ec8  xor     eax, eax
0x140059eca  movups  xmmword ptr [rbx+0D8h], xmm0
0x140059ed1  xor     edx, edx; Val
0x140059ed3  mov     r8d, 0D0h; Size
0x140059ed9  movups  xmmword ptr [rbx+0E8h], xmm0
0x140059ee0  mov     rcx, rbx; void *
0x140059ee3  mov     [rbx+0F8h], rax
0x140059eea  call    memset
0x140059eef  lea     rcx, [rbx+0D0h]; SpinLock
0x140059ef6  call    cs:__imp_KeInitializeSpinLock
0x140059efd  nop     dword ptr [rax+rax+00h]
0x140059f02  xor     eax, eax
0x140059f04  xorps   xmm0, xmm0
0x140059f07  mov     [rbx+0D9h], eax
0x140059f0d  mov     [rbx+0DDh], ax
0x140059f14  mov     [rbx+0DFh], al
0x140059f1a  movups  xmmword ptr [rbx+0E0h], xmm0
0x140059f21  movups  xmmword ptr [rbx+0F0h], xmm0
0x140059f28  test    esi, esi
0x140059f2a  jz      short loc_140059F8B
0x140059f2c  lea     rdi, [rbx+80h]
0x140059f33  mov     rcx, rdi; SListHead
0x140059f36  call    cs:__imp_InitializeSListHead
0x140059f3d  nop     dword ptr [rax+rax+00h]
0x140059f42  mov     [rbx+0C0h], rbx
0x140059f49  inc     esi
0x140059f4b  mov     [rbx+0C8h], rdi
0x140059f52  add     rbx, 100h
0x140059f59  cmp     esi, ebp
0x140059f5b  jb      loc_140059EC0
0x140059f61  mov     r12, [rsp+78h+var_20]
0x140059f66  mov     rdi, [rsp+78h+arg_10]
0x140059f6e  mov     rsi, [rsp+78h+arg_8]
0x140059f76  mov     rbx, [rsp+78h+arg_0]
0x140059f7e  mov     rax, r14
0x140059f81  mov     r14, [rsp+78h+var_28]
0x140059f86  jmp     loc_140059E24
0x140059f8b  mov     [rsp+78h+Depth], 400h; Depth
0x140059f92  lea     r8, ndisFreeNblToNPagedPool; Free
0x140059f99  mov     [rsp+78h+Tag], r15d; Tag
0x140059f9e  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140059fa5  mov     [rsp+78h+Size], r13; Size
0x140059faa  mov     r9d, 200h; PoolType
0x140059fb0  mov     rcx, rbx; Lookaside
0x140059fb3  mov     [rsp+78h+Flags], 0; Flags
0x140059fbb  call    cs:__imp_ExInitializeLookasideListEx
0x140059fc2  nop     dword ptr [rax+rax+00h]
0x140059fc7  mov     byte ptr [rbx+0D8h], 1
0x140059fce  jmp     loc_140059F2C
0x140059fd3  test    rbx, rbx
0x140059fd6  jz      short loc_14005A03B
0x140059fd8  xorps   xmm0, xmm0
0x140059fdb  xor     eax, eax
0x140059fdd  movups  xmmword ptr [rbx+0D8h], xmm0
0x140059fe4  xor     edx, edx; Val
0x140059fe6  mov     r8d, 0D0h; Size
0x140059fec  movups  xmmword ptr [rbx+0E8h], xmm0
0x140059ff3  mov     rcx, rbx; void *
0x140059ff6  mov     [rbx+0F8h], rax
0x140059ffd  call    memset
0x14005a002  lea     rcx, [rbx+0D0h]; SpinLock
0x14005a009  call    cs:__imp_KeInitializeSpinLock
0x14005a010  nop     dword ptr [rax+rax+00h]
0x14005a015  xor     eax, eax
0x14005a017  xorps   xmm0, xmm0
0x14005a01a  mov     [rbx+0D9h], eax
0x14005a020  mov     [rbx+0DDh], ax
0x14005a027  mov     [rbx+0DFh], al
0x14005a02d  movups  xmmword ptr [rbx+0E0h], xmm0
0x14005a034  movups  xmmword ptr [rbx+0F0h], xmm0
0x14005a03b  test    esi, esi
0x14005a03d  jz      short loc_14005A079
0x14005a03f  lea     rdi, [rbx+80h]
0x14005a046  mov     rcx, rdi; SListHead
0x14005a049  call    cs:__imp_InitializeSListHead
0x14005a050  nop     dword ptr [rax+rax+00h]
0x14005a055  mov     [rbx+0C0h], rbx
0x14005a05c  inc     esi
0x14005a05e  mov     [rbx+0C8h], rdi
0x14005a065  add     rbx, 100h
0x14005a06c  cmp     esi, ebp
0x14005a06e  jb      loc_140059FD3
0x14005a074  jmp     loc_140059F61
0x14005a079  mov     [rsp+78h+Depth], 400h; Depth
0x14005a080  lea     r8, ndisFreeToNPagedPool; Free
0x14005a087  mov     [rsp+78h+Tag], r15d; Tag
0x14005a08c  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14005a093  mov     [rsp+78h+Size], r13; Size
0x14005a098  mov     r9d, 200h; PoolType
0x14005a09e  mov     rcx, rbx; Lookaside
0x14005a0a1  mov     [rsp+78h+Flags], 0; Flags
0x14005a0a9  call    cs:__imp_ExInitializeLookasideListEx
0x14005a0b0  nop     dword ptr [rax+rax+00h]
0x14005a0b5  mov     byte ptr [rbx+0D8h], 1
0x14005a0bc  jmp     short loc_14005A03F
```
