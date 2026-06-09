# SmbCeAllocateExchangeBuffer

- ea: `0x14001a760`
- end: `0x14001a946`
- name: `SmbCeAllocateExchangeBuffer`
- size: `486`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400093a0`
- `0x14001a760`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a7fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a7fe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a832`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a832`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a858`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a858`
- `ntoskrnl!ExAllocatePool2` at `0x14005e1b0`
- `ntoskrnl!ExAllocatePool2` at `0x14005e1b0`

## pseudocode

```c
unsigned __int64 __fastcall SmbCeAllocateExchangeBuffer(unsigned __int64 pContext, unsigned int a2)
{
  __int64 v3; // rsi
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  unsigned __int64 v6; // rdi
  signed __int32 v8; // r8d
  __int64 v9; // r14
  __int64 v10; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  __int64 Pool2; // rax
  __int64 v13; // rdi

  v3 = a2;
  if ( (*(_DWORD *)(pContext + 68) & 4) == 0 )
    goto LABEL_8;
  if ( (pContext & 0xFFF) < a2 )
    goto LABEL_8;
  _m_prefetchw((const void *)(pContext + 68));
  v4 = *(_DWORD *)(pContext + 68);
  do
  {
    v5 = v4;
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)(pContext + 68), v4 | 0x80000, v4);
  }
  while ( v5 != v4 );
  if ( (v4 & 0x80000) != 0 )
  {
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v6 = pContext & 0xFFFFFFFFFFFFF000uLL;
  if ( (pContext & 0xFFFFFFFFFFFFF000uLL) == 0 )
  {
LABEL_9:
    v8 = _InterlockedIncrement((volatile signed __int32 *)(pContext + 4));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
        pContext,
        v8 - 1,
        v8);
    }
    *(_BYTE *)(pContext + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 24));
    if ( *(_QWORD *)(pContext + 472) )
    {
      if ( *(_QWORD *)(pContext + 480) )
      {
        if ( *(_QWORD *)(pContext + 488) )
        {
          if ( *(_QWORD *)(pContext + 496) )
          {
LABEL_19:
            KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 24), *(_BYTE *)(pContext + 32));
            SmbCeDereferenceExchange(pContext);
            return v6;
          }
          v9 = 496;
        }
        else
        {
          v9 = 488;
        }
      }
      else
      {
        v9 = 480;
      }
    }
    else
    {
      v9 = 472;
    }
    if ( (unsigned int)v3 > 0x4000 )
    {
      if ( (unsigned int)v3 <= 0x9000 )
      {
        v10 = 1;
        v11 = &Lookaside;
      }
      else if ( (unsigned int)v3 > 0x11000 )
      {
        if ( (unsigned int)v3 > 0x101000 )
        {
          if ( (unsigned int)v3 > 0x801000 )
          {
            v10 = 5;
            Pool2 = ExAllocatePool2(66, v3, 1834181464);
            goto LABEL_16;
          }
          v10 = 4;
          v11 = &stru_140070840;
        }
        else
        {
          v10 = 3;
          v11 = &stru_1400707C0;
        }
      }
      else
      {
        v10 = 2;
        v11 = &stru_140070740;
      }
    }
    else
    {
      v10 = 0;
      v11 = &SmbBufferLookasideList;
    }
    Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v11);
LABEL_16:
    v13 = Pool2 | v10;
    if ( !Pool2 )
      v13 = 0;
    *(_QWORD *)(v9 + pContext) = v13;
    v6 = v13 & 0xFFFFFFFFFFFFFFF8uLL;
    goto LABEL_19;
  }
  return v6;
}

```

## disassembly

```asm
0x14001a760  mov     [rsp+arg_10], rbx
0x14001a765  mov     [rsp+arg_18], rsi
0x14001a76a  push    rdi
0x14001a76b  sub     rsp, 30h
0x14001a76f  mov     eax, [rcx+44h]
0x14001a772  mov     rbx, rcx
0x14001a775  mov     esi, edx
0x14001a777  test    al, 4
0x14001a779  jz      short loc_14001A7C1
0x14001a77b  mov     eax, ebx
0x14001a77d  and     eax, 0FFFh
0x14001a782  cmp     eax, esi
0x14001a784  jb      short loc_14001A7C1
0x14001a786  prefetchw byte ptr [rcx+44h]
0x14001a78a  mov     eax, [rcx+44h]
0x14001a78d  mov     ecx, eax
0x14001a78f  bts     ecx, 13h
0x14001a793  lock cmpxchg [rbx+44h], ecx
0x14001a798  jnz     short loc_14001A78D
0x14001a79a  bt      eax, 13h
0x14001a79e  jb      short loc_14001A7C1
0x14001a7a0  mov     rdi, rbx
0x14001a7a3  nop
0x14001a7a4  and     rdi, 0FFFFFFFFFFFFF000h
0x14001a7ab  jz      short loc_14001A7C3
0x14001a7ad  mov     rbx, [rsp+38h+arg_10]
0x14001a7b2  mov     rax, rdi
0x14001a7b5  mov     rsi, [rsp+38h+arg_18]
0x14001a7ba  add     rsp, 30h
0x14001a7be  pop     rdi
0x14001a7bf  retn
0x14001a7c1  xor     edi, edi
0x14001a7c3  mov     [rsp+38h+arg_0], rbp
0x14001a7c8  mov     r8d, 1
0x14001a7ce  lock xadd [rbx+4], r8d
0x14001a7d4  inc     r8d
0x14001a7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7de  lea     rax, WPP_GLOBAL_Control
0x14001a7e5  cmp     rcx, rax
0x14001a7e8  jz      short loc_14001A7F5
0x14001a7ea  mov     eax, [rcx+2Ch]
0x14001a7ed  test    al, 10h
0x14001a7ef  jnz     loc_14001A8DC
0x14001a7f5  lea     rcx, [rbx+18h]; SpinLock
0x14001a7f9  mov     [rsp+38h+arg_8], r14
0x14001a7fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a805  nop     dword ptr [rax+rax+00h]
0x14001a80a  mov     [rbx+20h], al
0x14001a80d  cmp     qword ptr [rbx+1D8h], 0
0x14001a815  jnz     loc_14001A8B6
0x14001a81b  mov     r14d, 1D8h
0x14001a821  cmp     esi, 4000h
0x14001a827  ja      short loc_14001A87B
0x14001a829  xor     edi, edi
0x14001a82b  lea     rcx, SmbBufferLookasideList; Lookaside
0x14001a832  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001a839  nop     dword ptr [rax+rax+00h]
0x14001a83e  or      rdi, rax
0x14001a841  test    rax, rax
0x14001a844  cmovz   rdi, rax
0x14001a848  mov     [r14+rbx], rdi
0x14001a84c  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14001a850  movzx   edx, byte ptr [rbx+20h]; NewIrql
0x14001a854  lea     rcx, [rbx+18h]; SpinLock
0x14001a858  call    cs:__imp_KeReleaseSpinLock
0x14001a85f  nop     dword ptr [rax+rax+00h]
0x14001a864  mov     rcx, rbx; pContext
0x14001a867  call    SmbCeDereferenceExchange
0x14001a86c  mov     r14, [rsp+38h+arg_8]
0x14001a871  mov     rbp, [rsp+38h+arg_0]
0x14001a876  jmp     loc_14001A7AD
0x14001a87b  cmp     esi, 9000h
0x14001a881  jbe     short loc_14001A8CB
0x14001a883  cmp     esi, 11000h
0x14001a889  ja      short loc_14001A899
0x14001a88b  mov     edi, 2
0x14001a890  lea     rcx, stru_140070740
0x14001a897  jmp     short loc_14001A832
0x14001a899  cmp     esi, 101000h
0x14001a89f  ja      loc_14001A929
0x14001a8a5  mov     edi, 3
0x14001a8aa  lea     rcx, stru_1400707C0
0x14001a8b1  jmp     loc_14001A832
0x14001a8b6  cmp     qword ptr [rbx+1E0h], 0
0x14001a8be  jnz     short loc_14001A910
0x14001a8c0  mov     r14d, 1E0h
0x14001a8c6  jmp     loc_14001A821
0x14001a8cb  mov     edi, 1
0x14001a8d0  lea     rcx, Lookaside
0x14001a8d7  jmp     loc_14001A832
0x14001a8dc  cmp     byte ptr [rcx+29h], 4
0x14001a8e0  jb      loc_14001A7F5
0x14001a8e6  mov     rcx, [rcx+18h]
0x14001a8ea  lea     eax, [r8-1]
0x14001a8ee  mov     [rsp+38h+var_10], r8d
0x14001a8f3  mov     edx, 21h ; '!'
0x14001a8f8  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x14001a8ff  mov     [rsp+38h+var_18], eax
0x14001a903  mov     r9, rbx
0x14001a906  call    WPP_SF_qDD
0x14001a90b  jmp     loc_14001A7F5
0x14001a910  cmp     qword ptr [rbx+1E8h], 0
0x14001a918  jnz     loc_14005E184
0x14001a91e  mov     r14d, 1E8h
0x14001a924  jmp     loc_14001A821
0x14001a929  cmp     esi, 801000h
0x14001a92f  ja      loc_14005E19D
0x14001a935  mov     edi, 4
0x14001a93a  lea     rcx, stru_140070840
0x14001a941  jmp     loc_14001A832
0x14005e184  cmp     qword ptr [rbx+1F0h], 0
0x14005e18c  jnz     loc_14001A850
0x14005e192  mov     r14d, 1F0h
0x14005e198  jmp     loc_14001A821
0x14005e19d  mov     rdx, rsi
0x14005e1a0  mov     ecx, 42h ; 'B'
0x14005e1a5  mov     r8d, 6D536358h
0x14005e1ab  mov     edi, 5
0x14005e1b0  call    cs:__imp_ExAllocatePool2
0x14005e1b7  nop     dword ptr [rax+rax+00h]
0x14005e1bc  nop
0x14005e1bd  jmp     loc_14001A83E
```
