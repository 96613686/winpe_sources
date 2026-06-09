# AllocateReadBufferDescriptors

- ea: `0x14001a6e0`
- end: `0x14001a8c3`
- name: `AllocateReadBufferDescriptors`
- size: `483`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a2b0`
- `0x14002dde0`

## callees

- `0x14001a6e0`
- `0x1400297fc`

## import_xrefs

- `ntoskrnl!MmMdlPageContentsState` at `0x14001a7e1`
- `ntoskrnl!MmMdlPageContentsState` at `0x14001a7e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a73d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a73d`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001a77c`
- `rdbss!RxLowIoGetBufferAddress` at `0x14001a77c`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14001a804`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14001a867`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14001a804`
- `mrxsmb!SmbMmAllocateSmbBuffer` at `0x14001a867`

## pseudocode

```c
__int64 __fastcall AllocateReadBufferDescriptors(__int64 a1, char a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdi
  unsigned int v6; // r14d
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 SmbBuffer; // rax
  __int64 v11; // rax

  v2 = *(_QWORD *)(a1 + 2456);
  v4 = *(_QWORD *)(a1 + 48);
  if ( v2 )
  {
    v6 = *(_DWORD *)(*(_QWORD *)(a1 + 2464) + 12LL);
    if ( (*(_BYTE *)(v2 + 10) & 5) != 0 )
      *(_QWORD *)(a1 + 2488) = *(_QWORD *)(v2 + 24);
    else
      *(_QWORD *)(a1 + 2488) = MmMapLockedPagesSpecifyCache((PMDL)v2, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v6 = *(_DWORD *)(v4 + 568);
    v2 = *(_QWORD *)(v4 + 544);
  }
  if ( ((*(_DWORD *)(a1 + 68) & 0x1000800) != 0 || a2)
    && !*(_QWORD *)(a1 + 2456)
    && !RxLowIoGetBufferAddress((PRX_CONTEXT)v4) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225626LL;
    }
    v8 = 15;
LABEL_14:
    WPP_SF_q(v7->AttachedDevice, v8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1);
    return 3221225626LL;
  }
  if ( (*(_DWORD *)(a1 + 68) & 0x1000800) != 0
    && (unsigned int)MmMdlPageContentsState(v2, 2) != 1
    && !*(_QWORD *)(a1 + 1024) )
  {
    SmbBuffer = SmbMmAllocateSmbBuffer(v6, 1834185554);
    *(_QWORD *)(a1 + 1024) = SmbBuffer;
    if ( !SmbBuffer )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 3221225626LL;
      }
      v8 = 16;
      goto LABEL_14;
    }
  }
  if ( (*(_DWORD *)(a1 + 68) & 0x1000800) != 0 )
  {
    if ( a2 )
    {
      if ( !*(_QWORD *)(a1 + 1032) )
      {
        v11 = SmbMmAllocateSmbBuffer(v6, 1834184018);
        *(_QWORD *)(a1 + 1032) = v11;
        if ( !v11 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return 3221225626LL;
          }
          v8 = 17;
          goto LABEL_14;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001a6e0  push    rbx
0x14001a6e2  push    rbp
0x14001a6e3  push    rsi
0x14001a6e4  push    rdi
0x14001a6e5  push    r14
0x14001a6e7  sub     rsp, 30h
0x14001a6eb  mov     rsi, [rcx+998h]
0x14001a6f2  movzx   ebp, dl
0x14001a6f5  mov     rdi, [rcx+30h]
0x14001a6f9  mov     rbx, rcx
0x14001a6fc  test    rsi, rsi
0x14001a6ff  jz      short loc_14001A752
0x14001a701  test    byte ptr [rsi+0Ah], 5
0x14001a705  mov     rax, [rcx+9A0h]
0x14001a70c  mov     r14d, [rax+0Ch]
0x14001a710  jz      short loc_14001A71F
0x14001a712  mov     rax, [rsi+18h]
0x14001a716  mov     [rcx+9B8h], rax
0x14001a71d  jmp     short loc_14001A760
0x14001a71f  mov     [rsp+58h+Priority], 40000010h; Priority
0x14001a727  xor     r9d, r9d; RequestedAddress
0x14001a72a  xor     edx, edx; AccessMode
0x14001a72c  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001a734  mov     r8d, 1; CacheType
0x14001a73a  mov     rcx, rsi; MemoryDescriptorList
0x14001a73d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001a744  nop     dword ptr [rax+rax+00h]
0x14001a749  mov     [rbx+9B8h], rax
0x14001a750  jmp     short loc_14001A760
0x14001a752  mov     r14d, [rdi+238h]
0x14001a759  mov     rsi, [rdi+220h]
0x14001a760  mov     eax, [rbx+44h]
0x14001a763  test    eax, 1000800h
0x14001a768  jnz     short loc_14001A76F
0x14001a76a  test    bpl, bpl
0x14001a76d  jz      short loc_14001A7CF
0x14001a76f  cmp     qword ptr [rbx+998h], 0
0x14001a777  jnz     short loc_14001A7CF
0x14001a779  mov     rcx, rdi; RxContext
0x14001a77c  call    cs:__imp_RxLowIoGetBufferAddress
0x14001a783  nop     dword ptr [rax+rax+00h]
0x14001a788  test    rax, rax
0x14001a78b  jnz     short loc_14001A7CF
0x14001a78d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a794  lea     rax, WPP_GLOBAL_Control
0x14001a79b  cmp     rcx, rax
0x14001a79e  jz      short loc_14001A7C5
0x14001a7a0  mov     eax, [rcx+2Ch]
0x14001a7a3  test    al, 1
0x14001a7a5  jz      short loc_14001A7C5
0x14001a7a7  cmp     byte ptr [rcx+29h], 1
0x14001a7ab  jb      short loc_14001A7C5
0x14001a7ad  mov     edx, 0Fh
0x14001a7b2  mov     rcx, [rcx+18h]
0x14001a7b6  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14001a7bd  mov     r9, rbx
0x14001a7c0  call    WPP_SF_q
0x14001a7c5  mov     eax, 0C000009Ah
0x14001a7ca  jmp     loc_14001A8B7
0x14001a7cf  mov     eax, [rbx+44h]
0x14001a7d2  test    eax, 1000800h
0x14001a7d7  jz      short loc_14001A846
0x14001a7d9  mov     edx, 2
0x14001a7de  mov     rcx, rsi
0x14001a7e1  call    cs:__imp_MmMdlPageContentsState
0x14001a7e8  nop     dword ptr [rax+rax+00h]
0x14001a7ed  cmp     eax, 1
0x14001a7f0  jz      short loc_14001A846
0x14001a7f2  cmp     qword ptr [rbx+400h], 0
0x14001a7fa  jnz     short loc_14001A846
0x14001a7fc  mov     edx, 6D537352h
0x14001a801  mov     ecx, r14d
0x14001a804  call    cs:__imp_SmbMmAllocateSmbBuffer
0x14001a80b  nop     dword ptr [rax+rax+00h]
0x14001a810  mov     [rbx+400h], rax
0x14001a817  test    rax, rax
0x14001a81a  jnz     short loc_14001A846
0x14001a81c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a823  lea     rax, WPP_GLOBAL_Control
0x14001a82a  cmp     rcx, rax
0x14001a82d  jz      short loc_14001A7C5
0x14001a82f  mov     eax, [rcx+2Ch]
0x14001a832  test    al, 1
0x14001a834  jz      short loc_14001A7C5
0x14001a836  cmp     byte ptr [rcx+29h], 1
0x14001a83a  jb      short loc_14001A7C5
0x14001a83c  mov     edx, 10h
0x14001a841  jmp     loc_14001A7B2
0x14001a846  mov     eax, [rbx+44h]
0x14001a849  test    eax, 1000800h
0x14001a84e  jz      short loc_14001A8B5
0x14001a850  test    bpl, bpl
0x14001a853  jz      short loc_14001A8B5
0x14001a855  cmp     qword ptr [rbx+408h], 0
0x14001a85d  jnz     short loc_14001A8B5
0x14001a85f  mov     edx, 6D536D52h
0x14001a864  mov     ecx, r14d
0x14001a867  call    cs:__imp_SmbMmAllocateSmbBuffer
0x14001a86e  nop     dword ptr [rax+rax+00h]
0x14001a873  mov     [rbx+408h], rax
0x14001a87a  test    rax, rax
0x14001a87d  jnz     short loc_14001A8B5
0x14001a87f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a886  lea     rax, WPP_GLOBAL_Control
0x14001a88d  cmp     rcx, rax
0x14001a890  jz      loc_14001A7C5
0x14001a896  mov     eax, [rcx+2Ch]
0x14001a899  test    al, 1
0x14001a89b  jz      loc_14001A7C5
0x14001a8a1  cmp     byte ptr [rcx+29h], 1
0x14001a8a5  jb      loc_14001A7C5
0x14001a8ab  mov     edx, 11h
0x14001a8b0  jmp     loc_14001A7B2
0x14001a8b5  xor     eax, eax
0x14001a8b7  add     rsp, 30h
0x14001a8bb  pop     r14
0x14001a8bd  pop     rdi
0x14001a8be  pop     rsi
0x14001a8bf  pop     rbp
0x14001a8c0  pop     rbx
0x14001a8c1  retn
```
