# CClfsLogFcbPhysical::CreateContainerQueue(void)

- ea: `0x140001da0`
- end: `0x1400020f2`
- name: `?CreateContainerQueue@CClfsLogFcbPhysical@@AEAAJXZ`
- size: `850`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400083c0`

## callees

- `0x140001da0`
- `0x1400021b8`
- `0x14000a228`
- `0x14000bc14`
- `0x140017f20`
- `0x140018280`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001e24`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001e24`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140001f47`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140001f74`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140001f47`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140001f74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001ff6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001ff6`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::CreateContainerQueue(CClfsLogFcbPhysical *this)
{
  int v2; // esi
  _QWORD *i; // rdi
  __int64 v4; // r15
  _QWORD *v5; // r8
  _QWORD *j; // rdx
  __int64 v7; // rbx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *k; // r15
  __int64 v11; // rbx
  __int64 v12; // r12
  SIZE_T v13; // rax
  PVOID PoolWithTag; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  _QWORD *v18; // r13
  unsigned int v19; // eax
  __int64 v20; // rdi
  unsigned int *v22; // [rsp+78h] [rbp+10h]
  _QWORD *v23; // [rsp+80h] [rbp+18h]
  __int64 v24; // [rsp+88h] [rbp+20h]

  v2 = 0;
  for ( i = (_QWORD *)**((_QWORD **)this + 119); i != *((_QWORD **)this + 119); i = (_QWORD *)*i )
  {
    v4 = i[2];
    v5 = (_QWORD *)*((_QWORD *)this + 705);
    for ( j = (_QWORD *)*v5; j != v5; j = (_QWORD *)*j )
    {
      v7 = (j[2] - 8LL) & -(__int64)(j[2] != 0);
      if ( *(_DWORD *)(v7 + 0x8C) == *(_DWORD *)(v4 + 192) )
        goto LABEL_8;
    }
    v7 = 0;
LABEL_8:
    if ( !v7 )
    {
      v8 = ExAllocateFromNPagedLookasideList(&CClfsContainerFlushElt::m_laList);
      v7 = (__int64)v8;
      if ( v8 )
      {
        *v8 = &CClfsContainerFlushElt::`vftable'{for `IReference'};
        v8[1] = &CClfsContainerFlushElt::`vftable'{for `IFlushElt'};
        v8[2] = 0;
        v8[3] = 0;
        v8[4] = 0;
        v8[5] = 0;
        v8[6] = 0;
        v8[8] = v8 + 7;
        v8[7] = v8 + 7;
        v8[9] = 0;
        v8[10] = 0;
        *((_DWORD *)v8 + 22) = 0;
        v8[12] = 0;
        v8[13] = 0;
        v8[14] = 0;
        v8[15] = 0;
        v8[16] = 0;
        *((_DWORD *)v8 + 34) = 0;
        v8[19] = v8 + 18;
        v8[18] = v8 + 18;
        v8[20] = 0;
        *((_DWORD *)v8 + 42) = 0;
        *((_DWORD *)v8 + 35) = -1;
        v8[20] = v8 + 1;
      }
      else
      {
        v7 = 0;
      }
      if ( !v7 )
      {
        v2 = -1073741670;
        v9 = 1;
LABEL_14:
        CClfsLogFcbCommon::ReportFlushFailure(v9, 3221225473LL);
        goto LABEL_40;
      }
      (**(void (__fastcall ***)(__int64))v7)(v7);
      v2 = CClfsContainerFlushElt::Initialize((CClfsContainerFlushElt *)v7, this, *(_DWORD *)(v4 + 192));
      if ( v2 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        v9 = 2;
        goto LABEL_14;
      }
      ExInterlockedInsertTailList(*((PLIST_ENTRY *)this + 705), (PLIST_ENTRY)(v7 + 144), *((PKSPIN_LOCK *)this + 706));
    }
    (**(void (__fastcall ***)(__int64))(v4 + 8))(v4 + 8);
    ExInterlockedInsertTailList(*(PLIST_ENTRY *)(v7 + 120), (PLIST_ENTRY)(v4 + 176), *(PKSPIN_LOCK *)(v7 + 128));
    ++*(_DWORD *)(v7 + 136);
  }
  for ( k = (_QWORD *)**((_QWORD **)this + 705); k != *((_QWORD **)this + 705); k = (_QWORD *)*k )
  {
    v11 = k[2];
    v12 = v11 + 128;
    if ( !v11 )
      v12 = 136;
    if ( !*(_DWORD *)v12 )
    {
      v2 = -1073741811;
      break;
    }
    v13 = 8LL * *(unsigned int *)v12;
    if ( !is_mul_ok(*(unsigned int *)v12, 8u) )
      v13 = -1;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v13, 0x73666C43u);
    v15 = v11 + 8;
    if ( !v11 )
      v15 = 16;
    v23 = (_QWORD *)v15;
    *(_QWORD *)v15 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v2 = -1073741670;
      break;
    }
    memset(PoolWithTag, 0, 8LL * *(unsigned int *)v12);
    v16 = v11 + 16;
    if ( !v11 )
      v16 = 24;
    v22 = (unsigned int *)v16;
    *(_DWORD *)v16 = 0;
    v17 = v11 + 112;
    if ( !v11 )
      v17 = 120;
    v24 = v17;
    v18 = **(_QWORD ***)v17;
    v19 = 0;
    while ( v18 != *(_QWORD **)v17 && v19 < *(_DWORD *)v12 )
    {
      v20 = (__int64)(v18 - 21);
      (**(void (__fastcall ***)(__int64))v20)(v20);
      *(_QWORD *)(*v23 + 8LL * (*v22)++) = v20 & -(__int64)(v18 != (_QWORD *)176);
      v19 = *v22;
      v18 = (_QWORD *)*v18;
      v17 = v24;
    }
  }
LABEL_40:
  if ( v2 < 0 )
    CClfsLogFcbPhysical::ClearContainerQueue(this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140001da0  mov     [rsp+arg_0], rcx
0x140001da5  push    rbx
0x140001da6  push    rsi
0x140001da7  push    rdi
0x140001da8  push    r12
0x140001daa  push    r13
0x140001dac  push    r14
0x140001dae  push    r15
0x140001db0  sub     rsp, 30h
0x140001db4  mov     r14, rcx
0x140001db7  xor     r13d, r13d
0x140001dba  mov     esi, r13d
0x140001dbd  mov     [rsp+68h+var_48], r13d
0x140001dc2  mov     rax, [rcx+3B8h]
0x140001dc9  mov     rdi, [rax]
0x140001dcc  cmp     rdi, [r14+3B8h]
0x140001dd3  jz      loc_140001F8E
0x140001dd9  mov     r15, [rdi+10h]
0x140001ddd  mov     r8, [r14+1608h]
0x140001de4  mov     rdx, [r8]
0x140001de7  cmp     rdx, r8
0x140001dea  jz      short loc_140001E11
0x140001dec  mov     rax, [rdx+10h]
0x140001df0  lea     rcx, [rax-8]
0x140001df4  neg     rax
0x140001df7  sbb     rbx, rbx
0x140001dfa  and     rbx, rcx
0x140001dfd  mov     eax, [r15+0C0h]
0x140001e04  cmp     [rbx+8Ch], eax
0x140001e0a  jz      short loc_140001E14
0x140001e0c  mov     rdx, [rdx]
0x140001e0f  jmp     short loc_140001DE7
0x140001e11  mov     rbx, r13
0x140001e14  test    rbx, rbx
0x140001e17  jnz     loc_140001F53
0x140001e1d  lea     rcx, ?m_laList@CClfsContainerFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140001e24  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001e2b  nop     dword ptr [rax+rax+00h]
0x140001e30  mov     rbx, rax
0x140001e33  test    rax, rax
0x140001e36  jz      loc_140001ECF
0x140001e3c  lea     rax, ??_7CClfsContainerFlushElt@@6BIReference@@@; const CClfsContainerFlushElt::`vftable'{for `IReference'}
0x140001e43  mov     [rbx], rax
0x140001e46  lea     rcx, [rbx+8]
0x140001e4a  lea     rax, ??_7CClfsContainerFlushElt@@6BIFlushElt@@@; const CClfsContainerFlushElt::`vftable'{for `IFlushElt'}
0x140001e51  mov     [rcx], rax
0x140001e54  mov     [rbx+10h], r13
0x140001e58  mov     [rbx+18h], r13
0x140001e5c  mov     [rbx+20h], r13
0x140001e60  mov     [rbx+28h], r13
0x140001e64  mov     [rbx+30h], r13
0x140001e68  lea     rax, [rbx+38h]
0x140001e6c  mov     [rbx+40h], rax
0x140001e70  mov     [rax], rax
0x140001e73  mov     [rbx+48h], r13
0x140001e77  mov     [rbx+50h], r13
0x140001e7b  mov     [rbx+58h], r13d
0x140001e7f  mov     [rbx+60h], r13
0x140001e83  mov     [rbx+68h], r13
0x140001e87  mov     [rbx+70h], r13
0x140001e8b  mov     [rbx+78h], r13
0x140001e8f  mov     [rbx+80h], r13
0x140001e96  mov     [rbx+88h], r13d
0x140001e9d  lea     rax, [rbx+90h]
0x140001ea4  mov     [rbx+98h], rax
0x140001eab  mov     [rax], rax
0x140001eae  mov     [rbx+0A0h], r13
0x140001eb5  mov     [rbx+0A8h], r13d
0x140001ebc  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x140001ec6  mov     [rbx+0A0h], rcx
0x140001ecd  jmp     short loc_140001ED2
0x140001ecf  mov     rbx, r13
0x140001ed2  test    rbx, rbx
0x140001ed5  jnz     short loc_140001EF2
0x140001ed7  mov     esi, 0C000009Ah
0x140001edc  mov     [rsp+68h+var_48], esi
0x140001ee0  lea     ecx, [rbx+1]
0x140001ee3  mov     edx, 0C0000001h
0x140001ee8  call    ?ReportFlushFailure@CClfsLogFcbCommon@@SAXW4_CLFS_FLUSH_FAILURE@@J@Z; CClfsLogFcbCommon::ReportFlushFailure(_CLFS_FLUSH_FAILURE,long)
0x140001eed  jmp     loc_1400020D3
0x140001ef2  mov     rax, [rbx]
0x140001ef5  mov     rax, [rax]
0x140001ef8  mov     rcx, rbx
0x140001efb  call    _guard_dispatch_icall
0x140001f00  mov     r8d, [r15+0C0h]; unsigned int
0x140001f07  mov     rdx, r14; struct CClfsLogFcbPhysical *
0x140001f0a  mov     rcx, rbx; this
0x140001f0d  call    ?Initialize@CClfsContainerFlushElt@@QEAAJPEAVCClfsLogFcbPhysical@@K@Z; CClfsContainerFlushElt::Initialize(CClfsLogFcbPhysical *,ulong)
0x140001f12  mov     esi, eax
0x140001f14  mov     [rsp+68h+var_48], eax
0x140001f18  test    eax, eax
0x140001f1a  jns     short loc_140001F32
0x140001f1c  mov     rdx, [rbx]
0x140001f1f  mov     rax, [rdx+8]
0x140001f23  mov     rcx, rbx
0x140001f26  call    _guard_dispatch_icall
0x140001f2b  mov     ecx, 2
0x140001f30  jmp     short loc_140001EE3
0x140001f32  lea     rdx, [rbx+90h]; ListEntry
0x140001f39  mov     r8, [r14+1610h]; Lock
0x140001f40  mov     rcx, [r14+1608h]; ListHead
0x140001f47  call    cs:__imp_ExInterlockedInsertTailList
0x140001f4e  nop     dword ptr [rax+rax+00h]
0x140001f53  lea     rcx, [r15+8]
0x140001f57  mov     rax, [rcx]
0x140001f5a  mov     rax, [rax]
0x140001f5d  call    _guard_dispatch_icall
0x140001f62  lea     rdx, [r15+0B0h]; ListEntry
0x140001f69  mov     r8, [rbx+80h]; Lock
0x140001f70  mov     rcx, [rbx+78h]; ListHead
0x140001f74  call    cs:__imp_ExInterlockedInsertTailList
0x140001f7b  nop     dword ptr [rax+rax+00h]
0x140001f80  inc     dword ptr [rbx+88h]
0x140001f86  mov     rdi, [rdi]
0x140001f89  jmp     loc_140001DCC
0x140001f8e  mov     rax, [r14+1608h]
0x140001f95  mov     r15, [rax]
0x140001f98  cmp     r15, [r14+1608h]
0x140001f9f  jz      loc_1400020D3
0x140001fa5  mov     rbx, [r15+10h]
0x140001fa9  lea     r12, [rbx+80h]
0x140001fb0  mov     eax, 88h
0x140001fb5  test    rbx, rbx
0x140001fb8  cmovz   r12, rax
0x140001fbc  mov     eax, [r12]
0x140001fc0  test    eax, eax
0x140001fc2  jnz     short loc_140001FD2
0x140001fc4  mov     esi, 0C000000Dh
0x140001fc9  mov     [rsp+68h+var_48], esi
0x140001fcd  jmp     loc_1400020D3
0x140001fd2  mov     rcx, rax
0x140001fd5  mov     eax, 8
0x140001fda  mul     rcx
0x140001fdd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140001fe4  cmovb   rax, rcx
0x140001fe8  mov     r8d, 73666C43h; Tag
0x140001fee  mov     rdx, rax; NumberOfBytes
0x140001ff1  mov     ecx, 200h; PoolType
0x140001ff6  call    cs:__imp_ExAllocatePoolWithTag
0x140001ffd  nop     dword ptr [rax+rax+00h]
0x140002002  mov     rcx, rax; void *
0x140002005  lea     rax, [rbx+8]
0x140002009  mov     edx, 10h
0x14000200e  test    rbx, rbx
0x140002011  cmovz   rax, rdx
0x140002015  mov     [rsp+68h+arg_10], rax
0x14000201d  mov     [rax], rcx
0x140002020  test    rcx, rcx
0x140002023  jnz     short loc_14000202C
0x140002025  mov     esi, 0C000009Ah
0x14000202a  jmp     short loc_140001FC9
0x14000202c  mov     r8d, [r12]
0x140002030  shl     r8, 3; Size
0x140002034  xor     edx, edx; Val
0x140002036  call    memset
0x14000203b  lea     r8, [rbx+10h]
0x14000203f  mov     eax, 18h
0x140002044  test    rbx, rbx
0x140002047  cmovz   r8, rax
0x14000204b  mov     [rsp+68h+arg_8], r8
0x140002050  mov     [r8], r13d
0x140002053  lea     rcx, [rbx+70h]
0x140002057  mov     eax, 78h ; 'x'
0x14000205c  cmovz   rcx, rax
0x140002060  mov     [rsp+68h+arg_18], rcx
0x140002068  mov     rax, [rcx]
0x14000206b  mov     r13, [rax]
0x14000206e  xor     eax, eax
0x140002070  cmp     r13, [rcx]
0x140002073  jz      short loc_1400020C8
0x140002075  cmp     eax, [r12]
0x140002079  jnb     short loc_1400020C8
0x14000207b  lea     rbx, [r13-0B0h]
0x140002082  lea     rdi, [rbx+8]
0x140002086  mov     rax, [rdi]
0x140002089  mov     rax, [rax]
0x14000208c  mov     rcx, rdi
0x14000208f  call    _guard_dispatch_icall
0x140002094  neg     rbx
0x140002097  sbb     rdx, rdx
0x14000209a  and     rdx, rdi
0x14000209d  mov     r8, [rsp+68h+arg_8]
0x1400020a2  mov     ecx, [r8]
0x1400020a5  mov     rax, [rsp+68h+arg_10]
0x1400020ad  mov     rax, [rax]
0x1400020b0  mov     [rax+rcx*8], rdx
0x1400020b4  inc     dword ptr [r8]
0x1400020b7  mov     eax, [r8]
0x1400020ba  mov     r13, [r13+0]
0x1400020be  mov     rcx, [rsp+68h+arg_18]
0x1400020c6  jmp     short loc_140002070
0x1400020c8  mov     r15, [r15]
0x1400020cb  xor     r13d, r13d
0x1400020ce  jmp     loc_140001F98
0x1400020d3  test    esi, esi
0x1400020d5  jns     short loc_1400020DF
0x1400020d7  mov     rcx, r14; this
0x1400020da  call    ?ClearContainerQueue@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::ClearContainerQueue(void)
0x1400020df  mov     eax, esi
0x1400020e1  add     rsp, 30h
0x1400020e5  pop     r15
0x1400020e7  pop     r14
0x1400020e9  pop     r13
0x1400020eb  pop     r12
0x1400020ed  pop     rdi
0x1400020ee  pop     rsi
0x1400020ef  pop     rbx
0x1400020f0  retn
0x1400198af  push    rbp
0x1400198b1  sub     rsp, 20h
0x1400198b5  mov     rbp, rdx
0x1400198b8  cmp     dword ptr [rbp+20h], 0
0x1400198bc  jge     short loc_1400198C8
0x1400198be  mov     rcx, [rbp+70h]; this
0x1400198c2  call    ?ClearContainerQueue@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::ClearContainerQueue(void)
0x1400198c7  nop
0x1400198c8  add     rsp, 20h
0x1400198cc  pop     rbp
0x1400198cd  retn
```
