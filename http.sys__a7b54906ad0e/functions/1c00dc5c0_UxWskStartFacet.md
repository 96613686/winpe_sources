# UxWskStartFacet

- ea: `0x1c00dc5c0`
- end: `0x1c00dc737`
- name: `UxWskStartFacet`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1c001b900`
- `0x1c00dc5c0`

## import_xrefs

- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1c00dc5ed`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1c00dc5ed`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1c00dc6e1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1c00dc6e1`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1c00fed08`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1c00fed08`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00dc64a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00dc64a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fed23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fed23`

## pseudocode

```c
__int64 __fastcall UxWskStartFacet(_QWORD *a1)
{
  unsigned __int16 v2; // r14
  __int64 v3; // rbp
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rax
  _DWORD *PoolWithTagPriority; // rax
  _DWORD *v7; // rbx
  char *v8; // rsi
  _QWORD *v9; // r14
  unsigned int v10; // r15d
  NTSTATUS v11; // ebp
  __int64 v12; // rsi
  PLOOKASIDE_LIST_EX *v13; // r14
  PLOOKASIDE_LIST_EX v14; // r13
  PLOOKASIDE_LIST_EX *v16; // rdi

  a1[951] = a1 + 950;
  a1[950] = a1 + 950;
  v2 = KeQueryHighestNodeNumber() + 1;
  v3 = v2;
  v4 = (8LL * v2 + 71) & 0xFFFFFFFFFFFFFFC0uLL;
  if ( 0xFFFFFFFFFFFFFFFFuLL / v2 < 0x80 )
  {
    v7 = 0;
  }
  else
  {
    v5 = (unsigned __int64)v2 << 7;
    if ( v5 + v4 < v5 )
      return (unsigned int)-1073741670;
    PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)516, v5 + v4, 0x53576C55u, LowPoolPriority);
    v7 = PoolWithTagPriority;
    if ( !PoolWithTagPriority )
      return (unsigned int)-1073741670;
    v8 = (char *)PoolWithTagPriority + v4;
    *PoolWithTagPriority = v2;
    if ( v2 )
    {
      v9 = PoolWithTagPriority + 2;
      do
      {
        memset(v8, 0, 0x70u);
        *v9 = v8;
        v8 += 128;
        ++v9;
        --v3;
      }
      while ( v3 );
    }
  }
  if ( !v7 )
    return (unsigned int)-1073741670;
  v10 = *v7;
  v11 = 0;
  v12 = 0;
  if ( *v7 )
  {
    v13 = (PLOOKASIDE_LIST_EX *)(v7 + 2);
    while ( 1 )
    {
      v14 = *v13;
      v11 = ExInitializeLookasideListEx(
              *v13,
              UxTlAllocateConnectionForLookaside,
              UxTlFreeConnectionFromLookaside,
              (POOL_TYPE)512,
              0,
              0x220u,
              0x43546C55u,
              0);
      if ( v11 < 0 )
        break;
      v12 = (unsigned int)(v12 + 1);
      v14[1].L.ListHead.Alignment = (ULONGLONG)a1;
      ++v13;
      if ( (unsigned int)v12 >= v10 )
        goto LABEL_12;
    }
  }
  else
  {
LABEL_12:
    a1[949] = v7;
    v7 = 0;
  }
  if ( v7 )
  {
    if ( (_DWORD)v12 )
    {
      v16 = (PLOOKASIDE_LIST_EX *)(v7 + 2);
      do
      {
        ExDeleteLookasideListEx(*v16++);
        --v12;
      }
      while ( v12 );
    }
    ExFreePoolWithTag(v7, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1c00dc5c0  mov     [rsp+arg_0], rbx
0x1c00dc5c5  mov     [rsp+arg_8], rbp
0x1c00dc5ca  mov     [rsp+arg_10], rsi
0x1c00dc5cf  push    rdi
0x1c00dc5d0  push    r12
0x1c00dc5d2  push    r13
0x1c00dc5d4  push    r14
0x1c00dc5d6  push    r15
0x1c00dc5d8  sub     rsp, 40h
0x1c00dc5dc  lea     rax, [rcx+1DB0h]
0x1c00dc5e3  mov     r12, rcx
0x1c00dc5e6  mov     [rax+8], rax
0x1c00dc5ea  mov     [rax], rax
0x1c00dc5ed  call    cs:__imp_KeQueryHighestNodeNumber
0x1c00dc5f4  nop     dword ptr [rax+rax+00h]
0x1c00dc5f9  mov     r15d, 1
0x1c00dc5ff  xor     edx, edx
0x1c00dc601  lea     r14d, [r15+rax]
0x1c00dc605  or      rax, 0FFFFFFFFFFFFFFFFh
0x1c00dc609  movzx   ebp, r14w
0x1c00dc60d  lea     r13d, [r15+7Fh]
0x1c00dc611  div     rbp
0x1c00dc614  lea     rsi, ds:47h[rbp*8]
0x1c00dc61c  and     rsi, 0FFFFFFFFFFFFFFC0h
0x1c00dc620  cmp     rax, r13
0x1c00dc623  jb      loc_1C00FECEA
0x1c00dc629  mov     eax, ebp
0x1c00dc62b  shl     rax, 7
0x1c00dc62f  lea     rdx, [rax+rsi]; NumberOfBytes
0x1c00dc633  cmp     rdx, rax
0x1c00dc636  jb      loc_1C00FECF3
0x1c00dc63c  xor     r9d, r9d; Priority
0x1c00dc63f  mov     ecx, 204h; PoolType
0x1c00dc644  mov     r8d, 53576C55h; Tag
0x1c00dc64a  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00dc651  nop     dword ptr [rax+rax+00h]
0x1c00dc656  xor     edi, edi
0x1c00dc658  mov     rbx, rax
0x1c00dc65b  test    rax, rax
0x1c00dc65e  jz      loc_1C00FECF3
0x1c00dc664  add     rsi, rbx
0x1c00dc667  movzx   eax, r14w
0x1c00dc66b  mov     [rbx], eax
0x1c00dc66d  cmp     di, r14w
0x1c00dc671  jnb     short loc_1C00DC694
0x1c00dc673  lea     r14, [rbx+8]
0x1c00dc677  xor     edx, edx; Val
0x1c00dc679  mov     rcx, rsi; void *
0x1c00dc67c  lea     r8d, [rdx+70h]; Size
0x1c00dc680  call    memset
0x1c00dc685  mov     [r14], rsi
0x1c00dc688  add     rsi, r13
0x1c00dc68b  lea     r14, [r14+8]
0x1c00dc68f  sub     rbp, r15
0x1c00dc692  jnz     short loc_1C00DC677
0x1c00dc694  test    rbx, rbx
0x1c00dc697  jz      loc_1C00FECF3
0x1c00dc69d  mov     r15d, [rbx]
0x1c00dc6a0  mov     ebp, edi
0x1c00dc6a2  mov     esi, edi
0x1c00dc6a4  test    r15d, r15d
0x1c00dc6a7  jz      short loc_1C00DC702
0x1c00dc6a9  lea     r14, [rbx+8]
0x1c00dc6ad  mov     r13, [r14]
0x1c00dc6b0  lea     r8, UxTlFreeConnectionFromLookaside; Free
0x1c00dc6b7  mov     [rsp+68h+Depth], di; Depth
0x1c00dc6bc  lea     rdx, UxTlAllocateConnectionForLookaside; Allocate
0x1c00dc6c3  mov     [rsp+68h+Tag], 43546C55h; Tag
0x1c00dc6cb  mov     rcx, r13; Lookaside
0x1c00dc6ce  mov     [rsp+68h+Size], 220h; Size
0x1c00dc6d7  mov     r9d, 200h; PoolType
0x1c00dc6dd  mov     [rsp+68h+Flags], edi; Flags
0x1c00dc6e1  call    cs:__imp_ExInitializeLookasideListEx
0x1c00dc6e8  nop     dword ptr [rax+rax+00h]
0x1c00dc6ed  mov     ebp, eax
0x1c00dc6ef  test    eax, eax
0x1c00dc6f1  js      short loc_1C00DC70D
0x1c00dc6f3  inc     esi
0x1c00dc6f5  mov     [r13+60h], r12
0x1c00dc6f9  add     r14, 8
0x1c00dc6fd  cmp     esi, r15d
0x1c00dc700  jb      short loc_1C00DC6AD
0x1c00dc702  mov     [r12+1DA8h], rbx
0x1c00dc70a  mov     rbx, rdi
0x1c00dc70d  test    rbx, rbx
0x1c00dc710  jnz     loc_1C00FECFD
0x1c00dc716  lea     r11, [rsp+68h+var_28]
0x1c00dc71b  mov     eax, ebp
0x1c00dc71d  mov     rbx, [r11+30h]
0x1c00dc721  mov     rbp, [r11+38h]
0x1c00dc725  mov     rsi, [r11+40h]
0x1c00dc729  mov     rsp, r11
0x1c00dc72c  pop     r15
0x1c00dc72e  pop     r14
0x1c00dc730  pop     r13
0x1c00dc732  pop     r12
0x1c00dc734  pop     rdi
0x1c00dc735  retn
0x1c00fecea  xor     edi, edi
0x1c00fecec  mov     ebx, edi
0x1c00fecee  jmp     loc_1C00DC694
0x1c00fecf3  mov     ebp, 0C000009Ah
0x1c00fecf8  jmp     loc_1C00DC716
0x1c00fecfd  test    esi, esi
0x1c00fecff  jz      short loc_1C00FED1E
0x1c00fed01  lea     rdi, [rbx+8]
0x1c00fed05  mov     rcx, [rdi]; Lookaside
0x1c00fed08  call    cs:__imp_ExDeleteLookasideListEx
0x1c00fed0f  nop     dword ptr [rax+rax+00h]
0x1c00fed14  lea     rdi, [rdi+8]
0x1c00fed18  sub     rsi, 1
0x1c00fed1c  jnz     short loc_1C00FED05
0x1c00fed1e  xor     edx, edx; Tag
0x1c00fed20  mov     rcx, rbx; P
0x1c00fed23  call    cs:__imp_ExFreePoolWithTag
0x1c00fed2a  nop     dword ptr [rax+rax+00h]
0x1c00fed2f  nop
0x1c00fed30  jmp     loc_1C00DC716
```
