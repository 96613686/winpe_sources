# PplpCreateLookasideListEx

- ea: `0x1400097c8`
- end: `0x14000990a`
- name: `PplpCreateLookasideListEx`
- size: `322`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000a574`

## callees

- `0x1400097c8`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140009843`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009843`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000987a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000987a`
- `ntoskrnl!ExAllocatePool3` at `0x140009808`
- `ntoskrnl!ExAllocatePool3` at `0x140009808`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400098bf`

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
0x1400097c8  mov     rax, rsp
0x1400097cb  push    rbx
0x1400097cc  push    rbp
0x1400097cd  push    rsi
0x1400097ce  push    rdi
0x1400097cf  push    r14
0x1400097d1  sub     rsp, 50h
0x1400097d5  lea     ebp, [rcx+1]
0x1400097d8  mov     qword ptr [rax-30h], 0
0x1400097e0  mov     edx, ebp
0x1400097e2  lea     r9, [rax-38h]
0x1400097e6  shl     rdx, 7
0x1400097ea  mov     ecx, 48h ; 'H'
0x1400097ef  add     rdx, 40h ; '@'
0x1400097f3  mov     qword ptr [rax-38h], 1
0x1400097fb  mov     r8d, 30455646h
0x140009801  mov     dword ptr [rax-58h], 1
0x140009808  call    cs:__imp_ExAllocatePool3
0x14000980f  nop     dword ptr [rax+rax+00h]
0x140009814  mov     rbx, rax
0x140009817  test    rax, rax
0x14000981a  jz      loc_1400098CB
0x140009820  mov     r14, [rsp+78h+arg_30]
0x140009828  xor     esi, esi
0x14000982a  cmp     esi, ebp
0x14000982c  jge     loc_1400098D9
0x140009832  movsxd  rdi, esi
0x140009835  shl     rdi, 7
0x140009839  add     rdi, rbx
0x14000983c  lea     rcx, [rdi+0A8h]; SpinLock
0x140009843  call    cs:__imp_KeInitializeSpinLock
0x14000984a  nop     dword ptr [rax+rax+00h]
0x14000984f  test    esi, esi
0x140009851  jnz     short loc_14000989E
0x140009853  xor     eax, eax
0x140009855  lea     rcx, [rdi+40h]; Lookaside
0x140009859  mov     [rsp+78h+Depth], ax; Depth
0x14000985e  mov     r9d, 200h; PoolType
0x140009864  mov     [rsp+78h+Tag], 70455646h; Tag
0x14000986c  xor     r8d, r8d; Free
0x14000986f  mov     [rsp+78h+Size], r14; Size
0x140009874  xor     edx, edx; Allocate
0x140009876  mov     [rsp+78h+Flags], eax; Flags
0x14000987a  call    cs:__imp_ExInitializeLookasideListEx
0x140009881  nop     dword ptr [rax+rax+00h]
0x140009886  test    eax, eax
0x140009888  js      short loc_1400098B7
0x14000988a  mov     qword ptr [rdi+0A0h], 0
0x140009895  mov     byte ptr [rdi+0B0h], 1
0x14000989c  jmp     short loc_1400098B0
0x14000989e  lea     rax, [rbx+40h]
0x1400098a2  mov     byte ptr [rdi+0B0h], 0
0x1400098a9  mov     [rdi+0A0h], rax
0x1400098b0  inc     esi
0x1400098b2  jmp     loc_14000982A
0x1400098b7  mov     edx, 30455646h; Tag
0x1400098bc  mov     rcx, rbx; P
0x1400098bf  call    cs:__imp_ExFreePoolWithTag
0x1400098c6  nop     dword ptr [rax+rax+00h]
0x1400098cb  xor     eax, eax
0x1400098cd  add     rsp, 50h
0x1400098d1  pop     r14
0x1400098d3  pop     rdi
0x1400098d4  pop     rsi
0x1400098d5  pop     rbp
0x1400098d6  pop     rbx
0x1400098d7  retn
0x1400098d9  xor     eax, eax
0x1400098db  mov     [rbx], ebp
0x1400098dd  mov     [rbx+24h], ax
0x1400098e1  mov     [rbx+18h], rax
0x1400098e5  mov     rax, rbx
0x1400098e8  mov     dword ptr [rbx+4], 0
0x1400098ef  mov     dword ptr [rbx+8], 70455646h
0x1400098f6  mov     dword ptr [rbx+0Ch], 30455646h
0x1400098fd  mov     [rbx+10h], r14
0x140009901  mov     dword ptr [rbx+20h], 200h
0x140009908  jmp     short loc_1400098CD
```
