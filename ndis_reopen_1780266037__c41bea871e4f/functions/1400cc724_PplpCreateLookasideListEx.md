# PplpCreateLookasideListEx

- ea: `0x1400cc724`
- end: `0x1400cc862`
- name: `PplpCreateLookasideListEx`
- size: `318`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, SIZE_T)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400cb874`

## callees

- `0x1400cc724`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400cc769`
- `ntoskrnl!ExAllocatePool3` at `0x1400cc769`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc81b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc81b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cc7a4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cc7a4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400cc7d8`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400cc7d8`

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
0x1400cc724  mov     rax, rsp
0x1400cc727  push    rbx
0x1400cc728  push    rbp
0x1400cc729  push    rsi
0x1400cc72a  push    rdi
0x1400cc72b  push    r12
0x1400cc72d  push    r14
0x1400cc72f  sub     rsp, 58h
0x1400cc733  lea     ebp, [rcx+1]
0x1400cc736  mov     qword ptr [rax-40h], 0
0x1400cc73e  mov     edx, ebp
0x1400cc740  lea     r9, [rax-48h]
0x1400cc744  shl     rdx, 7
0x1400cc748  mov     r12d, 6264444Eh
0x1400cc74e  add     rdx, 40h ; '@'
0x1400cc752  mov     qword ptr [rax-48h], 1
0x1400cc75a  mov     r8d, r12d
0x1400cc75d  mov     dword ptr [rax-68h], 1
0x1400cc764  mov     ecx, 48h ; 'H'
0x1400cc769  call    cs:__imp_ExAllocatePool3
0x1400cc770  nop     dword ptr [rax+rax+00h]
0x1400cc775  mov     rbx, rax
0x1400cc778  test    rax, rax
0x1400cc77b  jz      loc_1400CC827
0x1400cc781  mov     r14, [rsp+88h+arg_30]
0x1400cc789  xor     esi, esi
0x1400cc78b  cmp     esi, ebp
0x1400cc78d  jge     loc_1400CC837
0x1400cc793  movsxd  rdi, esi
0x1400cc796  shl     rdi, 7
0x1400cc79a  add     rdi, rbx
0x1400cc79d  lea     rcx, [rdi+0A8h]; SpinLock
0x1400cc7a4  call    cs:__imp_KeInitializeSpinLock
0x1400cc7ab  nop     dword ptr [rax+rax+00h]
0x1400cc7b0  test    esi, esi
0x1400cc7b2  jnz     short loc_1400CC7FC
0x1400cc7b4  xor     eax, eax
0x1400cc7b6  lea     rcx, [rdi+40h]; Lookaside
0x1400cc7ba  mov     [rsp+88h+Depth], ax; Depth
0x1400cc7bf  mov     r9d, 200h; PoolType
0x1400cc7c5  mov     [rsp+88h+Tag], r12d; Tag
0x1400cc7ca  xor     r8d, r8d; Free
0x1400cc7cd  mov     [rsp+88h+Size], r14; Size
0x1400cc7d2  xor     edx, edx; Allocate
0x1400cc7d4  mov     [rsp+88h+Flags], eax; Flags
0x1400cc7d8  call    cs:__imp_ExInitializeLookasideListEx
0x1400cc7df  nop     dword ptr [rax+rax+00h]
0x1400cc7e4  test    eax, eax
0x1400cc7e6  js      short loc_1400CC815
0x1400cc7e8  mov     qword ptr [rdi+0A0h], 0
0x1400cc7f3  mov     byte ptr [rdi+0B0h], 1
0x1400cc7fa  jmp     short loc_1400CC80E
0x1400cc7fc  lea     rax, [rbx+40h]
0x1400cc800  mov     byte ptr [rdi+0B0h], 0
0x1400cc807  mov     [rdi+0A0h], rax
0x1400cc80e  inc     esi
0x1400cc810  jmp     loc_1400CC78B
0x1400cc815  mov     edx, r12d; Tag
0x1400cc818  mov     rcx, rbx; P
0x1400cc81b  call    cs:__imp_ExFreePoolWithTag
0x1400cc822  nop     dword ptr [rax+rax+00h]
0x1400cc827  xor     eax, eax
0x1400cc829  add     rsp, 58h
0x1400cc82d  pop     r14
0x1400cc82f  pop     r12
0x1400cc831  pop     rdi
0x1400cc832  pop     rsi
0x1400cc833  pop     rbp
0x1400cc834  pop     rbx
0x1400cc835  retn
0x1400cc837  xor     eax, eax
0x1400cc839  mov     [rbx], ebp
0x1400cc83b  mov     [rbx+24h], ax
0x1400cc83f  mov     [rbx+18h], rax
0x1400cc843  mov     rax, rbx
0x1400cc846  mov     dword ptr [rbx+4], 0
0x1400cc84d  mov     [rbx+8], r12d
0x1400cc851  mov     [rbx+0Ch], r12d
0x1400cc855  mov     [rbx+10h], r14
0x1400cc859  mov     dword ptr [rbx+20h], 200h
0x1400cc860  jmp     short loc_1400CC829
```
