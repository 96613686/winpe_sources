# TxfCreateTxfFcb

- ea: `0x140196ad0`
- end: `0x140196e27`
- name: `TxfCreateTxfFcb`
- size: `855`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140192470`
- `0x1401934c0`
- `0x140195b14`
- `0x140196850`
- `0x1401982b0`
- `0x14019dc78`
- `0x140294b1c`

## callees

- `0x140029140`
- `0x14002b990`
- `0x1400596c0`
- `0x140196ad0`
- `0x140196e30`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140196c7c`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140196c7c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402ac25b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402ac25b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196ba1`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196ba1`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140196b1a`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x140196b1a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2c4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2e3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2af`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2c4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac2e3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196bdc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196cf0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196dbc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196bdc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196cf0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140196dbc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196d66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196dfe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ac30b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196d66`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196dfe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402ac30b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196b7b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196b7b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140196d9a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140196d9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140196e19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac20a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140196e19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac20a`

## pseudocode

```c
_WORD *__fastcall TxfCreateTxfFcb(__int64 a1, __int64 a2, _QWORD *a3, __int16 a4, int a5, int a6)
{
  struct _RTL_AVL_TABLE *v10; // rdi
  _WORD *v12; // r13
  char v13; // bl
  _WORD **v14; // rax
  char v15; // di
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  PVOID v21; // rax
  unsigned __int8 NewElement[3]; // [rsp+25h] [rbp-53h] BYREF
  _WORD *v23; // [rsp+28h] [rbp-50h]
  PVOID inserted; // [rsp+30h] [rbp-48h]
  __int128 Buffer; // [rsp+38h] [rbp-40h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+48h] [rbp-30h]

  Buffer = 0;
  NewElement[0] = 0;
  v10 = (struct _RTL_AVL_TABLE *)(a1 + 6072);
  if ( a6 && !RtlNumberGenericTableElementsAvl(v10) )
    return 0;
  inserted = 0;
  v12 = 0;
  v23 = 0;
  FastMutex = (PFAST_MUTEX)(a1 + 6176);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 6176));
  v13 = 1;
  *(_QWORD *)&Buffer = *a3;
  BYTE8(Buffer) = 1;
  v14 = (_WORD **)RtlLookupElementGenericTableAvl(v10, &Buffer);
  inserted = v14;
  if ( v14 )
  {
    v12 = *v14;
    v23 = v12;
    ++v12[8];
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)v12 + 5) + 16LL) + 6176LL));
    v13 = 0;
    if ( a5 && !*((_QWORD *)v12 + 6) )
    {
      ExAcquireResourceExclusiveLite(*((PERESOURCE *)v12 + 17), 1u);
      v15 = 1;
      if ( !*((_QWORD *)v12 + 6) )
      {
        v21 = ExAllocateFromLookasideListEx(&TxfFcbExtensionLookasideList);
        *((_QWORD *)v12 + 6) = v21;
        memset(v21, 0, 0x50u);
        *(CLFS_LSN *)(*((_QWORD *)v12 + 6) + 40LL) = CLFS_LSN_INVALID_EXT;
      }
      goto LABEL_21;
    }
  }
  else if ( !a6 )
  {
    if ( a5 )
    {
      v12 = ExAllocateFromLookasideListEx(&TxfLargeFcbLookasideList);
      v23 = v12;
      memset(v12, 0, 0xF0u);
      v12[1] = 240;
      *((_DWORD *)v12 + 1) |= 2u;
      v17 = v12 + 80;
      *((_QWORD *)v12 + 6) = v12 + 80;
      *((CLFS_LSN *)v12 + 25) = CLFS_LSN_INVALID_EXT;
      v20 = (_QWORD *)(*((_QWORD *)v12 + 6) + 64LL);
      v20[1] = v20;
      *v20 = v20;
    }
    else
    {
      v12 = ExAllocateFromLookasideListEx(&TxfFcbLookasideList);
      v23 = v12;
      memset(v12, 0, 0xA0u);
      v12[1] = 160;
    }
    *v12 = 1812;
    *((_QWORD *)v12 + 17) = NtfsAllocateEresourcePriv(v17, v16, v18);
    *((_QWORD *)v12 + 1) = *a3;
    v12[8] = 1;
    *((_QWORD *)v12 + 10) = v12 + 36;
    *((_QWORD *)v12 + 9) = v12 + 36;
    *((_QWORD *)v12 + 12) = v12 + 44;
    *((_QWORD *)v12 + 11) = v12 + 44;
    *((_QWORD *)v12 + 14) = v12 + 52;
    *((_QWORD *)v12 + 13) = v12 + 52;
    *((CLFS_LSN *)v12 + 15) = CLFS_LSN_INVALID_EXT;
    BYTE8(Buffer) = 0;
    *(_QWORD *)&Buffer = v12;
    inserted = RtlInsertElementGenericTableAvl(v10, &Buffer, 0x10u, NewElement);
    if ( a2 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 64));
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 32));
    }
    v19 = *((_QWORD *)v12 + 5);
    if ( v19 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v19 + 32));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)v12 + 5) + 64LL), 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*((char **)v12 + 5));
    }
    *((_QWORD *)v12 + 5) = a2;
    if ( (a4 & 0x400) != 0 )
    {
      *((_DWORD *)v12 + 1) |= 0x1000000u;
      v15 = 0;
      goto LABEL_21;
    }
  }
  v15 = 0;
LABEL_21:
  if ( v15 )
    ExReleaseResourceLite(*((PERESOURCE *)v12 + 17));
  if ( v13 )
    ExReleaseFastMutexUnsafe(FastMutex);
  return v12;
}

```

## disassembly

```asm
0x140196ad0  mov     [rsp+arg_8], rbx
0x140196ad5  mov     [rsp+arg_10], rsi
0x140196ada  mov     [rsp+arg_0], rcx
0x140196adf  push    rdi
0x140196ae0  push    r12
0x140196ae2  push    r13
0x140196ae4  push    r14
0x140196ae6  push    r15
0x140196ae8  sub     rsp, 50h
0x140196aec  mov     r12d, r9d
0x140196aef  mov     r14, r8
0x140196af2  mov     r15, rdx
0x140196af5  mov     rbx, rcx
0x140196af8  xorps   xmm0, xmm0
0x140196afb  movups  [rsp+78h+Buffer], xmm0
0x140196b00  mov     [rsp+78h+NewElement], 0
0x140196b05  lea     rdi, [rcx+17B8h]
0x140196b0c  mov     esi, [rsp+78h+arg_28]
0x140196b13  test    esi, esi
0x140196b15  jz      short loc_140196B47
0x140196b17  mov     rcx, rdi; Table
0x140196b1a  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x140196b21  nop     dword ptr [rax+rax+00h]
0x140196b26  test    eax, eax
0x140196b28  jnz     short loc_140196B47
0x140196b2a  xor     eax, eax
0x140196b2c  lea     r11, [rsp+78h+var_28]
0x140196b31  mov     rbx, [r11+38h]
0x140196b35  mov     rsi, [r11+40h]
0x140196b39  mov     rsp, r11
0x140196b3c  pop     r15
0x140196b3e  pop     r14
0x140196b40  pop     r13
0x140196b42  pop     r12
0x140196b44  pop     rdi
0x140196b45  retn
0x140196b47  mov     [rsp+78h+var_58], 0
0x140196b4c  mov     [rsp+78h+var_57], 0
0x140196b51  mov     [rsp+78h+var_55], 0
0x140196b56  mov     [rsp+78h+var_56], 0
0x140196b5b  mov     [rsp+78h+var_48], 0
0x140196b64  xor     r13d, r13d
0x140196b67  mov     [rsp+78h+var_50], r13
0x140196b6c  lea     rax, [rbx+1820h]
0x140196b73  mov     [rsp+78h+FastMutex], rax
0x140196b78  mov     rcx, rax; FastMutex
0x140196b7b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140196b82  nop     dword ptr [rax+rax+00h]
0x140196b87  mov     bl, 1
0x140196b89  mov     [rsp+78h+var_54], bl
0x140196b8d  mov     rax, [r14]
0x140196b90  mov     qword ptr [rsp+78h+Buffer], rax
0x140196b95  mov     byte ptr [rsp+78h+Buffer+8], bl
0x140196b99  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140196b9e  mov     rcx, rdi; Table
0x140196ba1  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140196ba8  nop     dword ptr [rax+rax+00h]
0x140196bad  mov     [rsp+78h+var_48], rax
0x140196bb2  test    rax, rax
0x140196bb5  jnz     loc_140196D4A
0x140196bbb  test    esi, esi
0x140196bbd  jz      short loc_140196BC7
0x140196bbf  xor     dil, dil
0x140196bc2  jmp     loc_140196DF0
0x140196bc7  cmp     [rsp+78h+arg_20], 0
0x140196bcf  jnz     loc_140196CE9
0x140196bd5  lea     rcx, TxfFcbLookasideList; Lookaside
0x140196bdc  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196be3  nop     dword ptr [rax+rax+00h]
0x140196be8  mov     r13, rax
0x140196beb  mov     [rsp+78h+var_50], rax
0x140196bf0  mov     esi, 0A0h
0x140196bf5  mov     r8d, esi; Size
0x140196bf8  xor     edx, edx; Val
0x140196bfa  mov     rcx, rax; void *
0x140196bfd  call    memset
0x140196c02  mov     [r13+2], si
0x140196c07  mov     [rsp+78h+var_57], 1
0x140196c0c  mov     eax, 714h
0x140196c11  mov     [r13+0], ax
0x140196c16  call    NtfsAllocateEresourcePriv
0x140196c1b  mov     [r13+88h], rax
0x140196c22  mov     rax, [r14]
0x140196c25  mov     [r13+8], rax
0x140196c29  mov     eax, 1
0x140196c2e  mov     [r13+10h], ax
0x140196c33  lea     rax, [r13+48h]
0x140196c37  mov     [rax+8], rax
0x140196c3b  mov     [rax], rax
0x140196c3e  lea     rax, [r13+58h]
0x140196c42  mov     [rax+8], rax
0x140196c46  mov     [rax], rax
0x140196c49  lea     rax, [r13+68h]
0x140196c4d  mov     [rax+8], rax
0x140196c51  mov     [rax], rax
0x140196c54  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196c5b  mov     [r13+78h], rax
0x140196c5f  mov     byte ptr [rsp+78h+Buffer+8], 0
0x140196c64  mov     qword ptr [rsp+78h+Buffer], r13
0x140196c69  lea     r9, [rsp+78h+NewElement]; NewElement
0x140196c6e  mov     r8d, 10h; BufferSize
0x140196c74  lea     rdx, [rsp+78h+Buffer]; Buffer
0x140196c79  mov     rcx, rdi; Table
0x140196c7c  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140196c83  nop     dword ptr [rax+rax+00h]
0x140196c88  mov     [rsp+78h+var_48], rax
0x140196c8d  mov     [rsp+78h+var_56], 1
0x140196c92  test    r15, r15
0x140196c95  jz      short loc_140196CA1
0x140196c97  lock inc dword ptr [r15+40h]
0x140196c9c  lock inc dword ptr [r15+20h]
0x140196ca1  mov     rax, [r13+28h]
0x140196ca5  test    rax, rax
0x140196ca8  jz      short loc_140196CCA
0x140196caa  lock dec dword ptr [rax+20h]
0x140196cae  mov     rcx, [r13+28h]
0x140196cb2  mov     eax, 0FFFFFFFFh
0x140196cb7  lock xadd [rcx+40h], eax
0x140196cbc  cmp     eax, 1
0x140196cbf  jnz     short loc_140196CCA
0x140196cc1  mov     rcx, [r13+28h]; P
0x140196cc5  call    TxfDeleteTxfRmcb
0x140196cca  mov     [r13+28h], r15
0x140196cce  bt      r12d, 0Ah
0x140196cd3  jnb     loc_140196BBF
0x140196cd9  or      dword ptr [r13+4], 1000000h
0x140196ce1  xor     dil, dil
0x140196ce4  jmp     loc_140196DF0
0x140196ce9  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x140196cf0  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196cf7  nop     dword ptr [rax+rax+00h]
0x140196cfc  mov     r13, rax
0x140196cff  mov     [rsp+78h+var_50], rax
0x140196d04  mov     esi, 0F0h
0x140196d09  mov     r8d, esi; Size
0x140196d0c  xor     edx, edx; Val
0x140196d0e  mov     rcx, rax; void *
0x140196d11  call    memset
0x140196d16  mov     [r13+2], si
0x140196d1b  or      dword ptr [r13+4], 2
0x140196d20  lea     rcx, [r13+0A0h]
0x140196d27  mov     [r13+30h], rcx
0x140196d2b  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196d32  mov     [rcx+28h], rax
0x140196d36  mov     rax, [r13+30h]
0x140196d3a  add     rax, 40h ; '@'
0x140196d3e  mov     [rax+8], rax
0x140196d42  mov     [rax], rax
0x140196d45  jmp     loc_140196C07
0x140196d4a  mov     r13, [rax]
0x140196d4d  mov     [rsp+78h+var_50], r13
0x140196d52  inc     word ptr [r13+10h]
0x140196d57  mov     rax, [r13+28h]
0x140196d5b  mov     rcx, [rax+10h]
0x140196d5f  add     rcx, 1820h; FastMutex
0x140196d66  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196d6d  nop     dword ptr [rax+rax+00h]
0x140196d72  xor     bl, bl
0x140196d74  mov     [rsp+78h+var_54], bl
0x140196d78  cmp     [rsp+78h+arg_20], 0
0x140196d80  jz      loc_140196BBF
0x140196d86  cmp     qword ptr [r13+30h], 0
0x140196d8b  jnz     loc_140196BBF
0x140196d91  mov     dl, 1; Wait
0x140196d93  mov     rcx, [r13+88h]; Resource
0x140196d9a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140196da1  nop     dword ptr [rax+rax+00h]
0x140196da6  mov     dil, 1
0x140196da9  mov     [rsp+78h+var_58], dil
0x140196dae  cmp     qword ptr [r13+30h], 0
0x140196db3  jnz     short loc_140196DF0
0x140196db5  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x140196dbc  call    cs:__imp_ExAllocateFromLookasideListEx
0x140196dc3  nop     dword ptr [rax+rax+00h]
0x140196dc8  mov     [r13+30h], rax
0x140196dcc  mov     [rsp+78h+var_55], dil
0x140196dd1  xor     edx, edx; Val
0x140196dd3  mov     r8d, 50h ; 'P'; Size
0x140196dd9  mov     rcx, rax; void *
0x140196ddc  call    memset
0x140196de1  mov     rcx, [r13+30h]
0x140196de5  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x140196dec  mov     [rcx+28h], rax
0x140196df0  test    dil, dil
0x140196df3  jnz     short loc_140196E12
0x140196df5  test    bl, bl
0x140196df7  jz      short loc_140196E0A
0x140196df9  mov     rcx, [rsp+78h+FastMutex]; FastMutex
0x140196dfe  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196e05  nop     dword ptr [rax+rax+00h]
0x140196e0a  mov     rax, r13
0x140196e0d  jmp     loc_140196B2C
0x140196e12  mov     rcx, [r13+88h]; Resource
0x140196e19  call    cs:__imp_ExReleaseResourceLite
0x140196e20  nop     dword ptr [rax+rax+00h]
0x140196e25  jmp     short loc_140196DF5
0x1402ac1e0  push    rbx
0x1402ac1e2  push    rbp
0x1402ac1e3  push    rdi
0x1402ac1e4  sub     rsp, 20h
0x1402ac1e8  mov     rbp, rdx
0x1402ac1eb  movzx   edi, cl
0x1402ac1ee  test    cl, cl
0x1402ac1f0  jz      short loc_1402AC1F9
0x1402ac1f2  movzx   eax, cs:NtfsStatusDebugFlags
0x1402ac1f9  mov     rbx, [rbp+28h]
0x1402ac1fd  cmp     byte ptr [rbp+20h], 0
0x1402ac201  jz      short loc_1402AC217
0x1402ac203  mov     rcx, [rbx+88h]; Resource
0x1402ac20a  call    cs:__imp_ExReleaseResourceLite
0x1402ac211  nop     dword ptr [rax+rax+00h]
0x1402ac216  nop
0x1402ac217  mov     eax, edi
0x1402ac219  test    dil, dil
0x1402ac21c  jz      loc_1402AC2F7
0x1402ac222  cmp     byte ptr [rbp+21h], 0
0x1402ac226  jz      loc_1402AC2D2
0x1402ac22c  cmp     qword ptr [rbx+88h], 0
0x1402ac234  jz      short loc_1402AC243
0x1402ac236  mov     rcx, [rbx+88h]; P
0x1402ac23d  call    NtfsFreeEresource
0x1402ac242  nop
0x1402ac243  cmp     byte ptr [rbp+22h], 0
0x1402ac247  jz      short loc_1402AC268
0x1402ac249  mov     rcx, [rbp+80h]
0x1402ac250  add     rcx, 17B8h; Table
0x1402ac257  mov     rdx, [rbp+30h]; Buffer
0x1402ac25b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1402ac262  nop     dword ptr [rax+rax+00h]
0x1402ac267  nop
0x1402ac268  cmp     qword ptr [rbx+28h], 0
0x1402ac26d  jz      short loc_1402AC294
0x1402ac26f  mov     rax, [rbx+28h]
0x1402ac273  lock dec dword ptr [rax+20h]
0x1402ac277  mov     rcx, [rbx+28h]
0x1402ac27b  mov     eax, 0FFFFFFFFh
0x1402ac280  lock xadd [rcx+40h], eax
0x1402ac285  sub     eax, 1
0x1402ac288  jnz     short loc_1402AC294
0x1402ac28a  mov     rcx, [rbx+28h]; P
0x1402ac28e  call    TxfDeleteTxfRmcb
0x1402ac293  nop
0x1402ac294  mov     qword ptr [rbx+28h], 0
0x1402ac29c  mov     rdx, rbx; Entry
0x1402ac29f  cmp     dword ptr [rbp+0A0h], 0
0x1402ac2a6  jz      short loc_1402AC2BD
0x1402ac2a8  lea     rcx, TxfLargeFcbLookasideList; Lookaside
0x1402ac2af  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac2b6  nop     dword ptr [rax+rax+00h]
0x1402ac2bb  jmp     short loc_1402AC2F7
0x1402ac2bd  lea     rcx, TxfFcbLookasideList; Lookaside
0x1402ac2c4  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac2cb  nop     dword ptr [rax+rax+00h]
0x1402ac2d0  jmp     short loc_1402AC2F7
0x1402ac2d2  cmp     byte ptr [rbp+23h], 0
0x1402ac2d6  jz      short loc_1402AC2F7
0x1402ac2d8  mov     rdx, [rbx+30h]; Entry
0x1402ac2dc  lea     rcx, TxfFcbExtensionLookasideList; Lookaside
0x1402ac2e3  call    cs:__imp_ExFreeToLookasideListEx
0x1402ac2ea  nop     dword ptr [rax+rax+00h]
0x1402ac2ef  mov     qword ptr [rbx+30h], 0
0x1402ac2f7  cmp     byte ptr [rbp+24h], 0
0x1402ac2fb  jz      short loc_1402AC318
0x1402ac2fd  mov     rcx, [rbp+80h]
0x1402ac304  add     rcx, 1820h; FastMutex
0x1402ac30b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1402ac312  nop     dword ptr [rax+rax+00h]
0x1402ac317  nop
0x1402ac318  add     rsp, 20h
0x1402ac31c  pop     rdi
0x1402ac31d  pop     rbp
0x1402ac31e  pop     rbx
0x1402ac31f  retn
```
