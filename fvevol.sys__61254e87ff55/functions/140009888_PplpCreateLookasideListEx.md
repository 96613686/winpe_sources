# PplpCreateLookasideListEx

- ea: `0x140009888`
- end: `0x1400099ca`
- name: `PplpCreateLookasideListEx`
- size: `322`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000a634`

## callees

- `0x140009888`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140009903`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009903`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000993a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000993a`
- `ntoskrnl!ExAllocatePool3` at `0x1400098c8`
- `ntoskrnl!ExAllocatePool3` at `0x1400098c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000997f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000997f`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(int a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, SIZE_T Size)
{
  int v7; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v10; // rdi
  _DWORD *result; // rax
  _QWORD v12[7]; // [rsp+40h] [rbp-38h] BYREF

  v7 = a1 + 1;
  v12[1] = 0;
  v12[0] = 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, 809850438, v12, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v7; ++i )
  {
    v10 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v10 + 21);
    if ( i )
    {
      *((_BYTE *)v10 + 176) = 0;
      *((_QWORD *)v10 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 16), 0, 0, (POOL_TYPE)512, 0, Size, 0x70455646u, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, 0x30455646u);
        return 0;
      }
      *((_QWORD *)v10 + 20) = 0;
      *((_BYTE *)v10 + 176) = 1;
    }
  }
  *Pool3 = v7;
  *((_WORD *)Pool3 + 18) = 0;
  *((_QWORD *)Pool3 + 3) = 0;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = 1883592262;
  Pool3[3] = 809850438;
  *((_QWORD *)Pool3 + 2) = Size;
  Pool3[8] = 512;
  return result;
}

```

## disassembly

```asm
0x140009888  mov     rax, rsp
0x14000988b  push    rbx
0x14000988c  push    rbp
0x14000988d  push    rsi
0x14000988e  push    rdi
0x14000988f  push    r14
0x140009891  sub     rsp, 50h
0x140009895  lea     ebp, [rcx+1]
0x140009898  mov     qword ptr [rax-30h], 0
0x1400098a0  mov     edx, ebp
0x1400098a2  lea     r9, [rax-38h]
0x1400098a6  shl     rdx, 7
0x1400098aa  mov     ecx, 48h ; 'H'
0x1400098af  add     rdx, 40h ; '@'
0x1400098b3  mov     qword ptr [rax-38h], 1
0x1400098bb  mov     r8d, 30455646h
0x1400098c1  mov     dword ptr [rax-58h], 1
0x1400098c8  call    cs:__imp_ExAllocatePool3
0x1400098cf  nop     dword ptr [rax+rax+00h]
0x1400098d4  mov     rbx, rax
0x1400098d7  test    rax, rax
0x1400098da  jz      loc_14000998B
0x1400098e0  mov     r14, [rsp+78h+arg_30]
0x1400098e8  xor     esi, esi
0x1400098ea  cmp     esi, ebp
0x1400098ec  jge     loc_140009999
0x1400098f2  movsxd  rdi, esi
0x1400098f5  shl     rdi, 7
0x1400098f9  add     rdi, rbx
0x1400098fc  lea     rcx, [rdi+0A8h]; SpinLock
0x140009903  call    cs:__imp_KeInitializeSpinLock
0x14000990a  nop     dword ptr [rax+rax+00h]
0x14000990f  test    esi, esi
0x140009911  jnz     short loc_14000995E
0x140009913  xor     eax, eax
0x140009915  lea     rcx, [rdi+40h]; Lookaside
0x140009919  mov     [rsp+78h+Depth], ax; Depth
0x14000991e  mov     r9d, 200h; PoolType
0x140009924  mov     [rsp+78h+Tag], 70455646h; Tag
0x14000992c  xor     r8d, r8d; Free
0x14000992f  mov     [rsp+78h+Size], r14; Size
0x140009934  xor     edx, edx; Allocate
0x140009936  mov     [rsp+78h+Flags], eax; Flags
0x14000993a  call    cs:__imp_ExInitializeLookasideListEx
0x140009941  nop     dword ptr [rax+rax+00h]
0x140009946  test    eax, eax
0x140009948  js      short loc_140009977
0x14000994a  mov     qword ptr [rdi+0A0h], 0
0x140009955  mov     byte ptr [rdi+0B0h], 1
0x14000995c  jmp     short loc_140009970
0x14000995e  lea     rax, [rbx+40h]
0x140009962  mov     byte ptr [rdi+0B0h], 0
0x140009969  mov     [rdi+0A0h], rax
0x140009970  inc     esi
0x140009972  jmp     loc_1400098EA
0x140009977  mov     edx, 30455646h; Tag
0x14000997c  mov     rcx, rbx; P
0x14000997f  call    cs:__imp_ExFreePoolWithTag
0x140009986  nop     dword ptr [rax+rax+00h]
0x14000998b  xor     eax, eax
0x14000998d  add     rsp, 50h
0x140009991  pop     r14
0x140009993  pop     rdi
0x140009994  pop     rsi
0x140009995  pop     rbp
0x140009996  pop     rbx
0x140009997  retn
0x140009999  xor     eax, eax
0x14000999b  mov     [rbx], ebp
0x14000999d  mov     [rbx+24h], ax
0x1400099a1  mov     [rbx+18h], rax
0x1400099a5  mov     rax, rbx
0x1400099a8  mov     dword ptr [rbx+4], 0
0x1400099af  mov     dword ptr [rbx+8], 70455646h
0x1400099b6  mov     dword ptr [rbx+0Ch], 30455646h
0x1400099bd  mov     [rbx+10h], r14
0x1400099c1  mov     dword ptr [rbx+20h], 200h
0x1400099c8  jmp     short loc_14000998D
```
