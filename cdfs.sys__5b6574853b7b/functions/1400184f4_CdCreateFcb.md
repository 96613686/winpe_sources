# CdCreateFcb

- ea: `0x1400184f4`
- end: `0x14001878a`
- name: `CdCreateFcb`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e1d0`
- `0x14000e544`
- `0x140019a00`

## callees

- `0x1400010e0`
- `0x140001114`
- `0x140003300`
- `0x1400184f4`
- `0x140019238`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001857e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400185ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018633`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001857e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400185ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018633`
- `ntoskrnl!KeBugCheckEx` at `0x14001855f`
- `ntoskrnl!KeBugCheckEx` at `0x14001855f`
- `ntoskrnl!ExInitializeResourceLite` at `0x140018662`
- `ntoskrnl!ExInitializeResourceLite` at `0x140018662`
- `ntoskrnl!KeInitializeEvent` at `0x14001868e`
- `ntoskrnl!KeInitializeEvent` at `0x1400186d4`
- `ntoskrnl!KeInitializeEvent` at `0x14001868e`
- `ntoskrnl!KeInitializeEvent` at `0x1400186d4`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140018737`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140018737`

## pseudocode

```c
__int64 __fastcall CdCreateFcb(__int64 a1, __int64 a2, unsigned __int16 a3, PVOID *a4)
{
  int v4; // r14d
  PVOID *v5; // r15
  __int64 v8; // rdi
  char *v9; // rsi
  char *v10; // rax
  char *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  char v14; // al
  __int64 v15; // rcx
  char *PoolWithTag; // [rsp+80h] [rbp+8h] BYREF

  v4 = a3;
  v5 = (PVOID *)&PoolWithTag;
  if ( a4 )
    v5 = a4;
  v8 = CdLookupFcbTable(a1, *(_QWORD *)(a1 + 16), a2);
  if ( v8 )
  {
    *(_BYTE *)v5 = 1;
  }
  else
  {
    if ( v4 == 771 || v4 == 772 )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, 0x218u, 0x69666443u);
      v9 = PoolWithTag;
      memset(PoolWithTag, 0, 0x218u);
      *((_WORD *)v9 + 1) = 536;
      *((_QWORD *)v9 + 62) = v9 + 488;
      *((_QWORD *)v9 + 61) = v9 + 488;
    }
    else
    {
      if ( v4 != 773 )
        KeBugCheckEx(0x26u, 0x190438u, 0, 0, 0);
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, 0x1E0u, 0x64666443u);
      v9 = PoolWithTag;
      memset(PoolWithTag, 0, 0x1E0u);
      *((_WORD *)v9 + 1) = 480;
    }
    *(_WORD *)v9 = v4;
    v8 = (__int64)v9;
    *((_QWORD *)v9 + 15) = *(_QWORD *)(a1 + 16);
    *((_QWORD *)v9 + 19) = a2;
    *((_QWORD *)v9 + 35) = 1;
    *((_QWORD *)v9 + 36) = v9 + 240;
    v10 = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0xF8u, 0x6E666443u);
    v11 = v10;
    if ( v10 )
    {
      memset(v10 + 4, 0, 0xF4u);
      *(_DWORD *)v11 = 16253702;
      ExInitializeResourceLite((PERESOURCE)(v11 + 32));
      *((_DWORD *)v11 + 34) = 1;
      *((_QWORD *)v11 + 18) = 0;
      *((_DWORD *)v11 + 38) = 0;
      KeInitializeEvent((PRKEVENT)(v11 + 160), SynchronizationEvent, 0);
    }
    *((_QWORD *)v9 + 25) = v11;
    if ( !v11 )
    {
      CdFreePool(&PoolWithTag);
      CdRaiseStatusEx(a1, 3221225626LL, 0, 1638400, 1108);
    }
    *(_BYTE *)v5 = 0;
    v12 = *((_QWORD *)v9 + 25);
    *(_DWORD *)(v12 + 192) = 1;
    *(_QWORD *)(v12 + 200) = 0;
    *(_DWORD *)(v12 + 208) = 0;
    KeInitializeEvent((PRKEVENT)(v12 + 216), SynchronizationEvent, 0);
    v13 = *((_QWORD *)v9 + 25);
    v14 = v9[7];
    v9[4] |= 0x40u;
    v9[6] |= 2u;
    v9[7] = v14 & 0xF | 0x50;
    *((_QWORD *)v9 + 8) = v9 + 56;
    *((_QWORD *)v9 + 7) = v9 + 56;
    v15 = v13 + 192;
    if ( v15 )
      *((_QWORD *)v9 + 6) = v15;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 0;
    *((_QWORD *)v9 + 11) = 0;
    *((_QWORD *)v9 + 12) = 0;
    *((_DWORD *)v9 + 26) = 0;
    *((_QWORD *)v9 + 14) = 0;
    if ( (_WORD)v4 == 773 )
      FsRtlInitializeOplock((POPLOCK)v9 + 11);
  }
  return v8;
}

```

## disassembly

```asm
0x1400184f4  mov     rax, rsp
0x1400184f7  push    rbx
0x1400184f8  push    rbp
0x1400184f9  push    rsi
0x1400184fa  push    rdi
0x1400184fb  push    r12
0x1400184fd  push    r13
0x1400184ff  push    r14
0x140018501  push    r15
0x140018503  sub     rsp, 38h
0x140018507  movzx   r14d, r8w
0x14001850b  lea     r15, [rax+8]
0x14001850f  mov     rbx, rdx
0x140018512  mov     r8, rdx
0x140018515  mov     rdx, [rcx+10h]
0x140018519  xor     r12d, r12d
0x14001851c  test    r9, r9
0x14001851f  mov     r13, rcx
0x140018522  cmovnz  r15, r9
0x140018526  call    CdLookupFcbTable
0x14001852b  mov     rdi, rax
0x14001852e  test    rax, rax
0x140018531  jnz     loc_140018745
0x140018537  mov     ecx, r14d
0x14001853a  sub     ecx, 303h
0x140018540  jz      short loc_1400185A8
0x140018542  sub     ecx, 1
0x140018545  jz      short loc_1400185A8
0x140018547  cmp     ecx, 1
0x14001854a  jz      short loc_14001856C
0x14001854c  xor     r9d, r9d; BugCheckParameter3
0x14001854f  mov     [rsp+78h+BugCheckParameter4], r12; BugCheckParameter4
0x140018554  xor     r8d, r8d; BugCheckParameter2
0x140018557  lea     ecx, [rax+26h]; BugCheckCode
0x14001855a  mov     edx, 190438h; BugCheckParameter1
0x14001855f  call    cs:__imp_KeBugCheckEx
0x14001856c  mov     edi, 1E0h
0x140018571  mov     r8d, 64666443h; Tag
0x140018577  mov     edx, edi; NumberOfBytes
0x140018579  mov     ecx, 411h; PoolType
0x14001857e  call    cs:__imp_ExAllocatePoolWithTag
0x140018585  nop     dword ptr [rax+rax+00h]
0x14001858a  mov     r8d, edi; Size
0x14001858d  xor     edx, edx; Val
0x14001858f  mov     rcx, rax; void *
0x140018592  mov     [rsp+78h+arg_0], rax
0x14001859a  mov     rsi, rax
0x14001859d  call    memset
0x1400185a2  mov     [rsi+2], di
0x1400185a6  jmp     short loc_1400185F0
0x1400185a8  mov     edi, 218h
0x1400185ad  mov     r8d, 69666443h; Tag
0x1400185b3  mov     edx, edi; NumberOfBytes
0x1400185b5  mov     ecx, 411h; PoolType
0x1400185ba  call    cs:__imp_ExAllocatePoolWithTag
0x1400185c1  nop     dword ptr [rax+rax+00h]
0x1400185c6  mov     r8d, edi; Size
0x1400185c9  xor     edx, edx; Val
0x1400185cb  mov     rcx, rax; void *
0x1400185ce  mov     [rsp+78h+arg_0], rax
0x1400185d6  mov     rsi, rax
0x1400185d9  call    memset
0x1400185de  lea     rax, [rsi+1E8h]
0x1400185e5  mov     [rsi+2], di
0x1400185e9  mov     [rax+8], rax
0x1400185ed  mov     [rax], rax
0x1400185f0  mov     [rsi], r14w
0x1400185f4  mov     rdi, rsi
0x1400185f7  mov     rax, [r13+10h]
0x1400185fb  mov     rbp, rsi
0x1400185fe  mov     [rsi+78h], rax
0x140018602  mov     edx, 0F8h; NumberOfBytes
0x140018607  mov     [rsi+98h], rbx
0x14001860e  mov     ecx, 600h; PoolType
0x140018613  lea     rax, [rdi+0F0h]
0x14001861a  mov     esi, 1
0x14001861f  mov     r8d, 6E666443h; Tag
0x140018625  mov     [rdi+118h], rsi
0x14001862c  mov     [rdi+120h], rax
0x140018633  call    cs:__imp_ExAllocatePoolWithTag
0x14001863a  nop     dword ptr [rax+rax+00h]
0x14001863f  mov     rbx, rax
0x140018642  test    rax, rax
0x140018645  jz      short loc_14001869A
0x140018647  lea     rcx, [rax+4]; void *
0x14001864b  xor     edx, edx; Val
0x14001864d  mov     r8d, 0F4h; Size
0x140018653  call    memset
0x140018658  lea     rcx, [rbx+20h]; Resource
0x14001865c  mov     dword ptr [rbx], 0F80306h
0x140018662  call    cs:__imp_ExInitializeResourceLite
0x140018669  nop     dword ptr [rax+rax+00h]
0x14001866e  lea     rcx, [rbx+0A0h]; Event
0x140018675  mov     [rbx+88h], esi
0x14001867b  xor     r8d, r8d; State
0x14001867e  mov     [rbx+90h], r12
0x140018685  mov     edx, esi; Type
0x140018687  mov     [rbx+98h], r12d
0x14001868e  call    cs:__imp_KeInitializeEvent
0x140018695  nop     dword ptr [rax+rax+00h]
0x14001869a  mov     [rbp+0C8h], rbx
0x1400186a1  test    rbx, rbx
0x1400186a4  jz      loc_14001875E
0x1400186aa  mov     [r15], r12b
0x1400186ad  xor     r8d, r8d; State
0x1400186b0  mov     rcx, [rbp+0C8h]
0x1400186b7  mov     edx, esi; Type
0x1400186b9  mov     [rcx+0C0h], esi
0x1400186bf  mov     [rcx+0C8h], r12
0x1400186c6  mov     [rcx+0D0h], r12d
0x1400186cd  add     rcx, 0D8h; Event
0x1400186d4  call    cs:__imp_KeInitializeEvent
0x1400186db  nop     dword ptr [rax+rax+00h]
0x1400186e0  mov     rcx, [rbp+0C8h]
0x1400186e7  mov     al, [rdi+7]
0x1400186ea  or      byte ptr [rdi+4], 40h
0x1400186ee  and     al, 0Fh
0x1400186f0  or      byte ptr [rdi+6], 2
0x1400186f4  or      al, 50h
0x1400186f6  mov     [rdi+7], al
0x1400186f9  lea     rax, [rdi+38h]
0x1400186fd  mov     [rax+8], rax
0x140018701  mov     [rax], rax
0x140018704  add     rcx, 0C0h
0x14001870b  jz      short loc_140018711
0x14001870d  mov     [rdi+30h], rcx
0x140018711  mov     eax, 305h
0x140018716  mov     [rdi+48h], r12
0x14001871a  mov     [rdi+50h], r12
0x14001871e  lea     rcx, [rdi+58h]; Oplock
0x140018722  mov     [rcx], r12
0x140018725  mov     [rdi+60h], r12
0x140018729  mov     [rdi+68h], r12d
0x14001872d  mov     [rdi+70h], r12
0x140018731  cmp     r14w, ax
0x140018735  jnz     short loc_140018749
0x140018737  call    cs:__imp_FsRtlInitializeOplock
0x14001873e  nop     dword ptr [rax+rax+00h]
0x140018743  jmp     short loc_140018749
0x140018745  mov     byte ptr [r15], 1
0x140018749  mov     rax, rdi
0x14001874c  add     rsp, 38h
0x140018750  pop     r15
0x140018752  pop     r14
0x140018754  pop     r13
0x140018756  pop     r12
0x140018758  pop     rdi
0x140018759  pop     rsi
0x14001875a  pop     rbp
0x14001875b  pop     rbx
0x14001875c  retn
0x14001875e  lea     rcx, [rsp+78h+arg_0]
0x140018766  call    CdFreePool
0x14001876b  mov     r9d, 190000h
0x140018771  mov     dword ptr [rsp+78h+BugCheckParameter4], 454h
0x140018779  xor     r8d, r8d
0x14001877c  mov     edx, 0C000009Ah
0x140018781  mov     rcx, r13
0x140018784  call    CdRaiseStatusEx
```
