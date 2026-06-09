# PplpCreateLookasideListEx

- ea: `0x14003b8ec`
- end: `0x14003ba35`
- name: `PplpCreateLookasideListEx`
- size: `329`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T, ULONG, int, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003b830`

## callees

- `0x14003b8ec`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x14003b932`
- `ntoskrnl!ExAllocatePool3` at `0x14003b932`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b9a9`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14003b9a9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003b975`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003b975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b9ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b9ec`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        SIZE_T Size,
        ULONG Tag,
        int a9,
        ULONG a10)
{
  int v10; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v13; // rdi
  _DWORD *result; // rax
  _QWORD v15[9]; // [rsp+40h] [rbp-48h] BYREF

  v15[1] = 0;
  v15[0] = 1;
  v10 = a1 + 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, a10, v15, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v10; ++i )
  {
    v13 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v13 + 21);
    if ( i )
    {
      *((_BYTE *)v13 + 176) = 0;
      *((_QWORD *)v13 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 16), 0, 0, (POOL_TYPE)512, 0, Size, Tag, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, a10);
        return 0;
      }
      *((_QWORD *)v13 + 20) = 0;
      *((_BYTE *)v13 + 176) = 1;
    }
  }
  *Pool3 = v10;
  *((_WORD *)Pool3 + 18) = 0;
  *((_QWORD *)Pool3 + 3) = 0;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = Tag;
  Pool3[3] = a10;
  *((_QWORD *)Pool3 + 2) = Size;
  Pool3[8] = 512;
  return result;
}

```

## disassembly

```asm
0x14003b8ec  push    rbx
0x14003b8ee  push    rbp
0x14003b8ef  push    rsi
0x14003b8f0  push    rdi
0x14003b8f1  push    r12
0x14003b8f3  push    r14
0x14003b8f5  push    r15
0x14003b8f7  sub     rsp, 50h
0x14003b8fb  mov     r14d, [rsp+88h+arg_48]
0x14003b903  lea     r9, [rsp+88h+var_48]
0x14003b908  mov     eax, 1
0x14003b90d  mov     [rsp+88h+var_40], 0
0x14003b916  mov     r8d, r14d
0x14003b919  mov     [rsp+88h+var_48], rax
0x14003b91e  mov     [rsp+88h+Flags], eax
0x14003b922  lea     ebp, [rax+rcx]
0x14003b925  mov     edx, ebp
0x14003b927  lea     ecx, [rax+47h]
0x14003b92a  shl     rdx, 7
0x14003b92e  add     rdx, 40h ; '@'
0x14003b932  call    cs:__imp_ExAllocatePool3
0x14003b939  nop     dword ptr [rax+rax+00h]
0x14003b93e  mov     rbx, rax
0x14003b941  test    rax, rax
0x14003b944  jz      loc_14003B9F8
0x14003b94a  mov     r15d, [rsp+88h+arg_38]
0x14003b952  xor     esi, esi
0x14003b954  mov     r12, [rsp+88h+arg_30]
0x14003b95c  cmp     esi, ebp
0x14003b95e  jge     loc_14003BA0A
0x14003b964  movsxd  rdi, esi
0x14003b967  shl     rdi, 7
0x14003b96b  add     rdi, rbx
0x14003b96e  lea     rcx, [rdi+0A8h]; SpinLock
0x14003b975  call    cs:__imp_KeInitializeSpinLock
0x14003b97c  nop     dword ptr [rax+rax+00h]
0x14003b981  test    esi, esi
0x14003b983  jnz     short loc_14003B9CD
0x14003b985  xor     eax, eax
0x14003b987  lea     rcx, [rdi+40h]; Lookaside
0x14003b98b  mov     [rsp+88h+Depth], ax; Depth
0x14003b990  mov     r9d, 200h; PoolType
0x14003b996  mov     [rsp+88h+Tag], r15d; Tag
0x14003b99b  xor     r8d, r8d; Free
0x14003b99e  mov     [rsp+88h+Size], r12; Size
0x14003b9a3  xor     edx, edx; Allocate
0x14003b9a5  mov     [rsp+88h+Flags], eax; Flags
0x14003b9a9  call    cs:__imp_ExInitializeLookasideListEx
0x14003b9b0  nop     dword ptr [rax+rax+00h]
0x14003b9b5  test    eax, eax
0x14003b9b7  js      short loc_14003B9E6
0x14003b9b9  mov     qword ptr [rdi+0A0h], 0
0x14003b9c4  mov     byte ptr [rdi+0B0h], 1
0x14003b9cb  jmp     short loc_14003B9DF
0x14003b9cd  lea     rax, [rbx+40h]
0x14003b9d1  mov     byte ptr [rdi+0B0h], 0
0x14003b9d8  mov     [rdi+0A0h], rax
0x14003b9df  inc     esi
0x14003b9e1  jmp     loc_14003B95C
0x14003b9e6  mov     edx, r14d; Tag
0x14003b9e9  mov     rcx, rbx; P
0x14003b9ec  call    cs:__imp_ExFreePoolWithTag
0x14003b9f3  nop     dword ptr [rax+rax+00h]
0x14003b9f8  xor     eax, eax
0x14003b9fa  add     rsp, 50h
0x14003b9fe  pop     r15
0x14003ba00  pop     r14
0x14003ba02  pop     r12
0x14003ba04  pop     rdi
0x14003ba05  pop     rsi
0x14003ba06  pop     rbp
0x14003ba07  pop     rbx
0x14003ba08  retn
0x14003ba0a  xor     eax, eax
0x14003ba0c  mov     [rbx], ebp
0x14003ba0e  mov     [rbx+24h], ax
0x14003ba12  mov     [rbx+18h], rax
0x14003ba16  mov     rax, rbx
0x14003ba19  mov     dword ptr [rbx+4], 0
0x14003ba20  mov     [rbx+8], r15d
0x14003ba24  mov     [rbx+0Ch], r14d
0x14003ba28  mov     [rbx+10h], r12
0x14003ba2c  mov     dword ptr [rbx+20h], 200h
0x14003ba33  jmp     short loc_14003B9FA
```
