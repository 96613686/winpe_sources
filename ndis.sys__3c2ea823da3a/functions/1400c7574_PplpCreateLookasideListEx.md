# PplpCreateLookasideListEx

- ea: `0x1400c7574`
- end: `0x1400c76b2`
- name: `PplpCreateLookasideListEx`
- size: `318`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400c66c4`

## callees

- `0x1400c7574`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400c75b9`
- `ntoskrnl!ExAllocatePool3` at `0x1400c75b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c766b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c766b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400c75f4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400c75f4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400c7628`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400c7628`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(int a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, SIZE_T Size)
{
  int v7; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v10; // rdi
  _DWORD *result; // rax
  _QWORD v12[9]; // [rsp+40h] [rbp-48h] BYREF

  v7 = a1 + 1;
  v12[1] = 0;
  v12[0] = 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, 1650738254, v12, 1);
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
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 16), 0, 0, NonPagedPoolNx, 0, Size, 0x6264444Eu, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, 0x6264444Eu);
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
  Pool3[2] = 1650738254;
  Pool3[3] = 1650738254;
  *((_QWORD *)Pool3 + 2) = Size;
  Pool3[8] = 512;
  return result;
}

```

## disassembly

```asm
0x1400c7574  mov     rax, rsp
0x1400c7577  push    rbx
0x1400c7578  push    rbp
0x1400c7579  push    rsi
0x1400c757a  push    rdi
0x1400c757b  push    r12
0x1400c757d  push    r14
0x1400c757f  sub     rsp, 58h
0x1400c7583  lea     ebp, [rcx+1]
0x1400c7586  mov     qword ptr [rax-40h], 0
0x1400c758e  mov     edx, ebp
0x1400c7590  lea     r9, [rax-48h]
0x1400c7594  shl     rdx, 7
0x1400c7598  mov     r12d, 6264444Eh
0x1400c759e  add     rdx, 40h ; '@'
0x1400c75a2  mov     qword ptr [rax-48h], 1
0x1400c75aa  mov     r8d, r12d
0x1400c75ad  mov     dword ptr [rax-68h], 1
0x1400c75b4  mov     ecx, 48h ; 'H'
0x1400c75b9  call    cs:__imp_ExAllocatePool3
0x1400c75c0  nop     dword ptr [rax+rax+00h]
0x1400c75c5  mov     rbx, rax
0x1400c75c8  test    rax, rax
0x1400c75cb  jz      loc_1400C7677
0x1400c75d1  mov     r14, [rsp+88h+arg_30]
0x1400c75d9  xor     esi, esi
0x1400c75db  cmp     esi, ebp
0x1400c75dd  jge     loc_1400C7687
0x1400c75e3  movsxd  rdi, esi
0x1400c75e6  shl     rdi, 7
0x1400c75ea  add     rdi, rbx
0x1400c75ed  lea     rcx, [rdi+0A8h]; SpinLock
0x1400c75f4  call    cs:__imp_KeInitializeSpinLock
0x1400c75fb  nop     dword ptr [rax+rax+00h]
0x1400c7600  test    esi, esi
0x1400c7602  jnz     short loc_1400C764C
0x1400c7604  xor     eax, eax
0x1400c7606  lea     rcx, [rdi+40h]; Lookaside
0x1400c760a  mov     [rsp+88h+Depth], ax; Depth
0x1400c760f  mov     r9d, 200h; PoolType
0x1400c7615  mov     [rsp+88h+Tag], r12d; Tag
0x1400c761a  xor     r8d, r8d; Free
0x1400c761d  mov     [rsp+88h+Size], r14; Size
0x1400c7622  xor     edx, edx; Allocate
0x1400c7624  mov     [rsp+88h+Flags], eax; Flags
0x1400c7628  call    cs:__imp_ExInitializeLookasideListEx
0x1400c762f  nop     dword ptr [rax+rax+00h]
0x1400c7634  test    eax, eax
0x1400c7636  js      short loc_1400C7665
0x1400c7638  mov     qword ptr [rdi+0A0h], 0
0x1400c7643  mov     byte ptr [rdi+0B0h], 1
0x1400c764a  jmp     short loc_1400C765E
0x1400c764c  lea     rax, [rbx+40h]
0x1400c7650  mov     byte ptr [rdi+0B0h], 0
0x1400c7657  mov     [rdi+0A0h], rax
0x1400c765e  inc     esi
0x1400c7660  jmp     loc_1400C75DB
0x1400c7665  mov     edx, r12d; Tag
0x1400c7668  mov     rcx, rbx; P
0x1400c766b  call    cs:__imp_ExFreePoolWithTag
0x1400c7672  nop     dword ptr [rax+rax+00h]
0x1400c7677  xor     eax, eax
0x1400c7679  add     rsp, 58h
0x1400c767d  pop     r14
0x1400c767f  pop     r12
0x1400c7681  pop     rdi
0x1400c7682  pop     rsi
0x1400c7683  pop     rbp
0x1400c7684  pop     rbx
0x1400c7685  retn
0x1400c7687  xor     eax, eax
0x1400c7689  mov     [rbx], ebp
0x1400c768b  mov     [rbx+24h], ax
0x1400c768f  mov     [rbx+18h], rax
0x1400c7693  mov     rax, rbx
0x1400c7696  mov     dword ptr [rbx+4], 0
0x1400c769d  mov     [rbx+8], r12d
0x1400c76a1  mov     [rbx+0Ch], r12d
0x1400c76a5  mov     [rbx+10h], r14
0x1400c76a9  mov     dword ptr [rbx+20h], 200h
0x1400c76b0  jmp     short loc_1400C7679
```
