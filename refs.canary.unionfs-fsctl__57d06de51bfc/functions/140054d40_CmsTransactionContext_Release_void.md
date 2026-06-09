# CmsTransactionContext::Release(void)

- ea: `0x140054d40`
- end: `0x140055048`
- name: `?Release@CmsTransactionContext@@QEAAXXZ`
- size: `776`
- prototype: `void __fastcall(CmsTransactionContext *__hidden this)`
- caller_count: `41`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013bec`
- `0x140013dc4`
- `0x140013ee4`
- `0x140014060`
- `0x140014130`
- `0x140014428`
- `0x140014510`
- `0x1400145f4`
- `0x1400523d0`
- `0x140056ee0`
- `0x14005b1a0`
- `0x140064250`
- `0x140065c34`
- `0x14007141c`
- `0x1400821b0`
- `0x140083174`
- `0x1400ac0c0`
- `0x1400bf27c`
- `0x1400d0490`
- `0x1400d26b8`
- `0x1400d3b58`
- `0x1401184a0`
- `0x1401184f0`
- `0x1401186f0`
- `0x140121058`
- `0x140125fd8`
- `0x14012a85c`
- `0x14012ac60`
- `0x14013b660`
- `0x14013b960`
- `0x14013e3ec`
- `0x14013f1d8`
- `0x14014b4c8`
- `0x14014b564`
- `0x14014beec`
- `0x140153770`
- `0x14015e270`
- `0x1401696ec`
- `0x14016b060`
- `0x14016b608`
- `0x14016d860`

## callees

- `0x14002b110`
- `0x140054d40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140054f85`
- `ntoskrnl!KeSetEvent` at `0x140054f85`
- `ntoskrnl!KdDebuggerEnabled` at `0x140054eea`
- `ntoskrnl!KdDebuggerEnabled` at `0x140054fab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054ebc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054ebc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140054edc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140054edc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f4753`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f4753`
- `ntoskrnl!ExReleasePushLockEx` at `0x140054f9a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140054f9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ddd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055037`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054ddd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055037`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055005`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055005`

## pseudocode

```c
void __fastcall CmsTransactionContext::Release(CmsTransactionContext *this)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  unsigned __int8 i; // dl
  __int64 v5; // rax
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  struct _SLIST_ENTRY *v9; // r8
  __int64 v10; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  unsigned int j; // ecx
  __int64 v13; // rdi
  __int64 v14; // rcx
  signed __int32 v15; // ett
  __int64 v16; // rcx
  int v17; // [rsp+24h] [rbp-24h]

  v2 = *((_QWORD *)this + 1);
  v3 = *(_DWORD *)this & 0x10000000;
  if ( (*((_QWORD *)this + 37) || *((_DWORD *)this + 88) || *((_DWORD *)this + 89)) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  for ( i = 0; i < *((_BYTE *)this + 128); *((_DWORD *)this + 22 * v5 + 285) &= ~1u )
    v5 = i++;
  v6 = (void *)*((_QWORD *)this + 424);
  *((_BYTE *)this + 128) = 0;
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)this + 424) = 0;
    *((_DWORD *)this + 850) = 0;
  }
  if ( (*((_BYTE *)this + 3336) & 1) != 0 )
  {
    v7 = (void *)*((_QWORD *)this + 416);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
  }
  *((_DWORD *)this + 835) = 32;
  *((_QWORD *)this + 416) = (char *)this + 3344;
  *((_DWORD *)this + 829) = v17;
  *((_OWORD *)this + 206) = 0;
  *((_DWORD *)this + 828) = 0;
  *((_QWORD *)this + 415) = 0;
  *((_BYTE *)this + 3336) = 0;
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 3216));
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 3136));
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 3056));
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 2976));
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 2896));
  CmsRowWithBuffer::Reset((CmsTransactionContext *)((char *)this + 2816));
  if ( *((_QWORD *)this + 128) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  v8 = (void *)*((_QWORD *)this + 108);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)this + 108) = 0;
  }
  if ( !v3 )
  {
    v9 = (struct _SLIST_ENTRY *)((char *)this - 16);
    v10 = *((_QWORD *)this - 2);
    if ( v10 )
    {
      if ( *(_BYTE *)(v10 + 8) )
      {
        v11 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
        if ( *(_BYTE *)(v10 + 9) )
          ExFreeToNPagedLookasideList(v11, v9);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v11, v9);
        return;
      }
      v16 = *(_QWORD *)(v10 + 88);
      if ( (int)v16 < *(_DWORD *)(v10 + 80) || SHIDWORD(v16) >= (int)v16 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v9);
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
        return;
      }
    }
    ExFreePoolWithTag(v9, 0);
    return;
  }
  if ( *(_DWORD *)(v2 + 172) )
  {
    for ( j = 0; j < *(_DWORD *)(v2 + 168); ++j )
    {
      v13 = 16LL * j;
      if ( *(CmsTransactionContext **)(v13 + *(_QWORD *)(v2 + 160)) == this )
      {
        if ( *(_BYTE *)(v2 + 216) )
          ExAcquirePushLockExclusiveEx(v2 + 208, 0);
        v14 = *(_QWORD *)(v2 + 160);
        _m_prefetchw((const void *)(v13 + v14 + 8));
        do
          v15 = *(_DWORD *)(v13 + v14 + 8);
        while ( v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v13 + v14 + 8), v15 & 0xFFFFFFFE, v15) );
        _InterlockedDecrement((volatile signed __int32 *)(v2 + 172));
        if ( *(_BYTE *)(v2 + 216) )
        {
          KeSetEvent((PRKEVENT)(v2 + 184), 0, 0);
          ExReleasePushLockEx(v2 + 208, 0);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x140054d40  mov     [rsp+arg_8], rbx
0x140054d45  mov     [rsp+arg_10], rbp
0x140054d4a  push    rsi
0x140054d4b  push    rdi
0x140054d4c  push    r14
0x140054d4e  sub     rsp, 30h
0x140054d52  mov     edi, [rcx]
0x140054d54  mov     rbx, rcx
0x140054d57  mov     rbp, [rcx+8]
0x140054d5b  and     edi, 10000000h
0x140054d61  cmp     qword ptr [rcx+128h], 0
0x140054d69  jnz     loc_140054EEA
0x140054d6f  cmp     dword ptr [rcx+160h], 0
0x140054d76  jnz     loc_140054EEA
0x140054d7c  cmp     dword ptr [rcx+164h], 0
0x140054d83  jnz     loc_140054EEA
0x140054d89  xor     dl, dl
0x140054d8b  cmp     [rcx+80h], dl
0x140054d91  jbe     short loc_140054DAC
0x140054d93  movzx   eax, dl
0x140054d96  inc     dl
0x140054d98  imul    rcx, rax, 58h ; 'X'
0x140054d9c  and     dword ptr [rcx+rbx+474h], 0FFFFFFFEh
0x140054da4  cmp     dl, [rbx+80h]
0x140054daa  jb      short loc_140054D93
0x140054dac  mov     rcx, [rbx+0D40h]; P
0x140054db3  xor     r14d, r14d
0x140054db6  mov     byte ptr [rbx+80h], 0
0x140054dbd  test    rcx, rcx
0x140054dc0  jnz     loc_140054FC1
0x140054dc6  test    byte ptr [rbx+0D08h], 1
0x140054dcd  jz      short loc_140054DE9
0x140054dcf  mov     rcx, [rbx+0D00h]; P
0x140054dd6  test    rcx, rcx
0x140054dd9  jz      short loc_140054DE9
0x140054ddb  xor     edx, edx; Tag
0x140054ddd  call    cs:__imp_ExFreePoolWithTag
0x140054de4  nop     dword ptr [rax+rax+00h]
0x140054de9  lea     rax, [rbx+0D10h]
0x140054df0  mov     dword ptr [rbx+0D0Ch], 20h ; ' '
0x140054dfa  mov     [rbx+0D00h], rax
0x140054e01  lea     rcx, [rbx+0C90h]; this
0x140054e08  mov     eax, [rsp+48h+var_24]
0x140054e0c  xorps   xmm0, xmm0
0x140054e0f  mov     [rbx+0CF4h], eax
0x140054e15  movups  xmmword ptr [rbx+0CE0h], xmm0
0x140054e1c  mov     [rbx+0CF0h], r14d
0x140054e23  mov     [rbx+0CF8h], r14
0x140054e2a  mov     [rbx+0D08h], r14b
0x140054e31  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e36  lea     rcx, [rbx+0C40h]; this
0x140054e3d  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e42  lea     rcx, [rbx+0BF0h]; this
0x140054e49  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e4e  lea     rcx, [rbx+0BA0h]; this
0x140054e55  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e5a  lea     rcx, [rbx+0B50h]; this
0x140054e61  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e66  lea     rcx, [rbx+0B00h]; this
0x140054e6d  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140054e72  cmp     [rbx+400h], r14
0x140054e79  jnz     loc_140054FAB
0x140054e7f  mov     rcx, [rbx+360h]; P
0x140054e86  test    rcx, rcx
0x140054e89  jnz     loc_140054FE2
0x140054e8f  test    rdi, rdi
0x140054e92  jnz     short loc_140054F00
0x140054e94  lea     r8, [rbx-10h]
0x140054e98  mov     rbx, [rbx-10h]
0x140054e9c  test    rbx, rbx
0x140054e9f  jz      loc_140055032
0x140054ea5  cmp     [rbx+8], r14b
0x140054ea9  jz      loc_140055016
0x140054eaf  lea     rcx, [rbx+40h]; Lookaside
0x140054eb3  mov     rdx, r8; Entry
0x140054eb6  cmp     [rbx+9], r14b
0x140054eba  jz      short loc_140054EDC
0x140054ebc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054ec3  nop     dword ptr [rax+rax+00h]
0x140054ec8  mov     rbx, [rsp+48h+arg_8]
0x140054ecd  mov     rbp, [rsp+48h+arg_10]
0x140054ed2  add     rsp, 30h
0x140054ed6  pop     r14
0x140054ed8  pop     rdi
0x140054ed9  pop     rsi
0x140054eda  retn
0x140054edc  call    cs:__imp_ExFreeToPagedLookasideList
0x140054ee3  nop     dword ptr [rax+rax+00h]
0x140054ee8  jmp     short loc_140054EC8
0x140054eea  mov     rax, cs:KdDebuggerEnabled
0x140054ef1  cmp     byte ptr [rax], 0
0x140054ef4  jz      loc_140054D89
0x140054efa  int     3; Trap to Debugger
0x140054efb  jmp     loc_140054D89
0x140054f00  mov     eax, [rbp+0ACh]
0x140054f06  test    eax, eax
0x140054f08  jz      short loc_140054EC8
0x140054f0a  mov     edx, [rbp+0A8h]
0x140054f10  mov     ecx, r14d
0x140054f13  cmp     ecx, edx
0x140054f15  jnb     short loc_140054EC8
0x140054f17  mov     rax, [rbp+0A0h]
0x140054f1e  mov     edi, ecx
0x140054f20  shl     rdi, 4
0x140054f24  cmp     [rdi+rax], rbx
0x140054f28  jz      short loc_140054F2E
0x140054f2a  inc     ecx
0x140054f2c  jmp     short loc_140054F13
0x140054f2e  cmp     [rbp+0D8h], r14b
0x140054f35  jnz     loc_140054FFC
0x140054f3b  mov     rcx, [rbp+0A0h]
0x140054f42  prefetchw byte ptr [rdi+rcx+8]
0x140054f47  nop     word ptr [rax+rax+00000000h]
0x140054f50  mov     eax, [rdi+rcx+8]
0x140054f54  mov     edx, eax
0x140054f56  and     edx, 0FFFFFFFEh
0x140054f59  nop
0x140054f5a  lock cmpxchg [rdi+rcx+8], edx
0x140054f60  nop
0x140054f61  jnz     short loc_140054F50
0x140054f63  nop
0x140054f64  lock dec dword ptr [rbp+0ACh]
0x140054f6b  nop
0x140054f6c  cmp     [rbp+0D8h], r14b
0x140054f73  jz      loc_140054EC8
0x140054f79  lea     rcx, [rbp+0B8h]; Event
0x140054f80  xor     r8d, r8d; Wait
0x140054f83  xor     edx, edx; Increment
0x140054f85  call    cs:__imp_KeSetEvent
0x140054f8c  nop     dword ptr [rax+rax+00h]
0x140054f91  lea     rcx, [rbp+0D0h]
0x140054f98  xor     edx, edx
0x140054f9a  call    cs:__imp_ExReleasePushLockEx
0x140054fa1  nop     dword ptr [rax+rax+00h]
0x140054fa6  jmp     loc_140054EC8
0x140054fab  mov     rax, cs:KdDebuggerEnabled
0x140054fb2  cmp     [rax], r14b
0x140054fb5  jz      loc_140054E7F
0x140054fbb  int     3; Trap to Debugger
0x140054fbc  jmp     loc_140054E7F
0x140054fc1  xor     edx, edx; Tag
0x140054fc3  call    cs:__imp_ExFreePoolWithTag
0x140054fca  nop     dword ptr [rax+rax+00h]
0x140054fcf  mov     [rbx+0D40h], r14
0x140054fd6  mov     [rbx+0D48h], r14d
0x140054fdd  jmp     loc_140054DC6
0x140054fe2  xor     edx, edx; Tag
0x140054fe4  call    cs:__imp_ExFreePoolWithTag
0x140054feb  nop     dword ptr [rax+rax+00h]
0x140054ff0  mov     [rbx+360h], r14
0x140054ff7  jmp     loc_140054E8F
0x140054ffc  lea     rcx, [rbp+0D0h]
0x140055003  xor     edx, edx
0x140055005  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005500c  nop     dword ptr [rax+rax+00h]
0x140055011  jmp     loc_140054F3B
0x140055016  mov     rcx, [rbx+58h]
0x14005501a  cmp     ecx, [rbx+50h]
0x14005501d  jl      loc_1401F474C
0x140055023  mov     rax, rcx
0x140055026  shr     rax, 20h
0x14005502a  cmp     eax, ecx
0x14005502c  jge     loc_1401F474C
0x140055032  xor     edx, edx; Tag
0x140055034  mov     rcx, r8; P
0x140055037  call    cs:__imp_ExFreePoolWithTag
0x14005503e  nop     dword ptr [rax+rax+00h]
0x140055043  jmp     loc_140054EC8
0x1401f474c  lea     rcx, [rbx+40h]; ListHead
0x1401f4750  mov     rdx, r8; ListEntry
0x1401f4753  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f475a  nop     dword ptr [rax+rax+00h]
0x1401f475f  nop
0x1401f4760  lock inc dword ptr [rbx+58h]
0x1401f4764  nop
0x1401f4765  jmp     loc_140054EC8
```
