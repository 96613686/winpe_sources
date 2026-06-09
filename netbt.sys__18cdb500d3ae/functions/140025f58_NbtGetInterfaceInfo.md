# NbtGetInterfaceInfo

- ea: `0x140025f58`
- end: `0x1400260eb`
- name: `NbtGetInterfaceInfo`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140047f20`

## callees

- `0x140025f58`
- `0x140031140`
- `0x140031440`
- `0x1400400a4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025f7a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025f7a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400260cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400260cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260a7`
- `ntoskrnl!ExAllocatePool2` at `0x140025fda`
- `ntoskrnl!ExAllocatePool2` at `0x140025fda`
- `TDI!TdiCopyBufferToMdl` at `0x140026094`
- `TDI!TdiCopyBufferToMdl` at `0x140026094`

## pseudocode

```c
__int64 __fastcall NbtGetInterfaceInfo(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v3; // r12
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int *Pool2; // rax
  unsigned int *v7; // r14
  unsigned int v8; // ebp
  __int64 i; // rsi
  __int64 v10; // rdi
  unsigned int v11; // ebx

  v1 = *(_QWORD *)(a1 + 184);
  v3 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( (BYTE1(xmmword_140038420) & 1) != 0 )
    WPP_SF_d(1032, 39, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, (unsigned __int16)word_1400395BA);
  v4 = 1304 * (unsigned __int16)word_1400395BA + 1308;
  if ( v4 > *(_DWORD *)(v1 + 8) )
  {
    v11 = -2147483643;
  }
  else
  {
    v5 = 1304 * (unsigned __int16)word_1400395BA + 1308;
    Pool2 = (unsigned int *)ExAllocatePool2(64, v4, 1349804622);
    v7 = Pool2;
    if ( Pool2 )
    {
      v8 = 0;
      memset(Pool2, 0, v5);
      for ( i = NbtConfig; (__int64 *)i != &NbtConfig; i = *(_QWORD *)i )
      {
        if ( *(_WORD *)(i + 128) < 0x514u )
        {
          v10 = 326LL * v8;
          memmove(&v7[v10 + 2], *(const void **)(i + 136), *(unsigned __int16 *)(i + 128));
          *((_WORD *)&v7[326 * v8 + 2] + ((unsigned __int64)*(unsigned __int16 *)(i + 128) >> 1)) = 0;
          v7[v10 + 1] = v8++;
        }
      }
      *v7 = v8;
      v11 = TdiCopyBufferToMdl(v7, 0, 1304 * v8 + 4, *(PMDL *)(a1 + 8), 0, (PULONG)(a1 + 56));
      ExFreePoolWithTag(v7, 0);
    }
    else
    {
      v11 = -1073741670;
    }
  }
  KeReleaseSpinLock(&SpinLock, v3);
  return v11;
}

```

## disassembly

```asm
0x140025f58  push    rbx
0x140025f5a  push    rbp
0x140025f5b  push    rsi
0x140025f5c  push    rdi
0x140025f5d  push    r12
0x140025f5f  push    r13
0x140025f61  push    r14
0x140025f63  push    r15
0x140025f65  sub     rsp, 38h
0x140025f69  mov     rbx, [rcx+0B8h]
0x140025f70  mov     r15, rcx
0x140025f73  lea     rcx, SpinLock; SpinLock
0x140025f7a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025f81  nop     dword ptr [rax+rax+00h]
0x140025f86  mov     r12b, al
0x140025f89  test    byte ptr cs:xmmword_140038420+1, 1
0x140025f90  jz      short loc_140025FB0
0x140025f92  movzx   r9d, cs:word_1400395BA
0x140025f9a  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140025fa1  mov     edx, 27h ; '''
0x140025fa6  mov     ecx, 408h
0x140025fab  call    WPP_SF_d
0x140025fb0  movzx   ecx, cs:word_1400395BA
0x140025fb7  imul    eax, ecx, 518h
0x140025fbd  add     eax, 51Ch
0x140025fc2  cmp     eax, [rbx+8]
0x140025fc5  ja      loc_1400260BC
0x140025fcb  mov     r8d, 5074624Eh
0x140025fd1  mov     edx, eax
0x140025fd3  mov     ecx, 40h ; '@'
0x140025fd8  mov     ebx, eax
0x140025fda  call    cs:__imp_ExAllocatePool2
0x140025fe1  nop     dword ptr [rax+rax+00h]
0x140025fe6  mov     r14, rax
0x140025fe9  test    rax, rax
0x140025fec  jz      loc_1400260B5
0x140025ff2  xor     ebp, ebp
0x140025ff4  mov     r8d, ebx; Size
0x140025ff7  xor     edx, edx; Val
0x140025ff9  mov     rcx, rax; void *
0x140025ffc  call    memset
0x140026001  mov     rsi, cs:NbtConfig
0x140026008  lea     r13, NbtConfig
0x14002600f  jmp     short loc_140026067
0x140026011  movzx   eax, word ptr [rsi+80h]
0x140026018  mov     ecx, 514h
0x14002601d  cmp     ax, cx
0x140026020  jnb     short loc_140026064
0x140026022  mov     rdx, [rsi+88h]; Src
0x140026029  lea     rcx, [r14+8]
0x14002602d  mov     ebx, ebp
0x14002602f  mov     r8d, eax; Size
0x140026032  imul    rdi, rbx, 518h
0x140026039  add     rcx, rdi; void *
0x14002603c  call    memmove
0x140026041  movzx   ecx, word ptr [rsi+80h]
0x140026048  imul    rax, rbx, 28Ch
0x14002604f  shr     rcx, 1
0x140026052  add     rcx, rax
0x140026055  xor     eax, eax
0x140026057  mov     [r14+rcx*2+8], ax
0x14002605d  mov     [rdi+r14+4], ebp
0x140026062  inc     ebp
0x140026064  mov     rsi, [rsi]
0x140026067  cmp     rsi, r13
0x14002606a  jnz     short loc_140026011
0x14002606c  imul    r8d, ebp, 518h
0x140026073  lea     rax, [r15+38h]
0x140026077  mov     [r14], ebp
0x14002607a  xor     edx, edx; SourceOffset
0x14002607c  mov     r9, [r15+8]; DestinationMdlChain
0x140026080  mov     rcx, r14; SourceBuffer
0x140026083  mov     [rsp+78h+BytesCopied], rax; BytesCopied
0x140026088  mov     [rsp+78h+DestinationOffset], 0; DestinationOffset
0x140026090  add     r8d, 4; SourceBytesToCopy
0x140026094  call    cs:__imp_TdiCopyBufferToMdl
0x14002609b  nop     dword ptr [rax+rax+00h]
0x1400260a0  xor     edx, edx; Tag
0x1400260a2  mov     rcx, r14; P
0x1400260a5  mov     ebx, eax
0x1400260a7  call    cs:__imp_ExFreePoolWithTag
0x1400260ae  nop     dword ptr [rax+rax+00h]
0x1400260b3  jmp     short loc_1400260C1
0x1400260b5  mov     ebx, 0C000009Ah
0x1400260ba  jmp     short loc_1400260C1
0x1400260bc  mov     ebx, 80000005h
0x1400260c1  mov     dl, r12b; NewIrql
0x1400260c4  lea     rcx, SpinLock; SpinLock
0x1400260cb  call    cs:__imp_KeReleaseSpinLock
0x1400260d2  nop     dword ptr [rax+rax+00h]
0x1400260d7  mov     eax, ebx
0x1400260d9  add     rsp, 38h
0x1400260dd  pop     r15
0x1400260df  pop     r14
0x1400260e1  pop     r13
0x1400260e3  pop     r12
0x1400260e5  pop     rdi
0x1400260e6  pop     rsi
0x1400260e7  pop     rbp
0x1400260e8  pop     rbx
0x1400260e9  retn
```
