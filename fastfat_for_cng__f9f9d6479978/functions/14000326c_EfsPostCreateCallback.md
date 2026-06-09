# EfsPostCreateCallback

- ea: `0x14000326c`
- end: `0x14000342d`
- name: `EfsPostCreateCallback`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002c598`

## callees

- `0x14000326c`
- `0x14000c310`
- `0x14000c380`
- `0x14000c680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400033f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400033f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd0d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000333c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000333c`

## pseudocode

```c
__int64 __fastcall EfsPostCreateCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _QWORD *a7)
{
  void *v9; // rdi
  __int64 v10; // r12
  __int16 v11; // r13
  __int64 v12; // rsi
  PVOID PoolWithTag; // rax
  __int16 v14; // ax
  unsigned int v15; // esi
  __int16 v16; // [rsp+50h] [rbp-58h]
  SIZE_T Size; // [rsp+60h] [rbp-48h]

  if ( (byte_140017D4D & 2) == 0 || (_DWORD)xmmword_140017DD8 != 6 || !(_QWORD)xmmword_140017DE8 )
    return 3221225488LL;
  if ( !*a7 )
    return 0;
  v9 = 0;
  v10 = *(_QWORD *)(a4 + 96);
  v11 = *(_WORD *)(a4 + 88);
  v16 = *(_WORD *)(a4 + 90);
  v12 = *(_QWORD *)(a4 + 24);
  if ( v12 && (unsigned __int16)(*(_WORD *)v12 - 1282) <= 1u && *(_QWORD *)(v12 + 536) )
  {
    Size = *(unsigned __int16 *)(v12 + 528);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, Size, 0x6E746146u);
    v9 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, Size);
    memmove(v9, *(const void **)(v12 + 536), *(unsigned __int16 *)(v12 + 528));
    *(_QWORD *)(a4 + 96) = v9;
    v14 = *(_WORD *)(v12 + 528);
    *(_WORD *)(a4 + 90) = v14;
    *(_WORD *)(a4 + 88) = v14;
  }
  v15 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, int, int, __int64, _QWORD, _QWORD *))xmmword_140017DE8)(
          a1,
          a2,
          a3,
          a4,
          a5,
          1,
          a6,
          0,
          a7);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  *(_QWORD *)(a4 + 96) = v10;
  *(_WORD *)(a4 + 88) = v11;
  *(_WORD *)(a4 + 90) = v16;
  return v15;
}

```

## disassembly

```asm
0x14000326c  mov     rax, rsp
0x14000326f  mov     [rax+20h], r9
0x140003273  mov     [rax+18h], r8
0x140003277  mov     [rax+10h], rdx
0x14000327b  mov     [rax+8], rcx
0x14000327f  push    rbx
0x140003280  push    rsi
0x140003281  push    rdi
0x140003282  push    r12
0x140003284  push    r13
0x140003286  push    r14
0x140003288  push    r15
0x14000328a  sub     rsp, 70h
0x14000328e  mov     rbx, r9
0x140003291  test    cs:byte_140017D4D, 2
0x140003298  jz      loc_140003417
0x14000329e  cmp     dword ptr cs:xmmword_140017DD8, 6
0x1400032a5  jnz     loc_140003417
0x1400032ab  cmp     qword ptr cs:xmmword_140017DE8, 0
0x1400032b3  jz      loc_140003417
0x1400032b9  mov     r14, [rsp+0A8h+arg_30]
0x1400032c1  cmp     qword ptr [r14], 0
0x1400032c5  jnz     short loc_1400032CE
0x1400032c7  xor     eax, eax
0x1400032c9  jmp     loc_14000341C
0x1400032ce  xor     edi, edi
0x1400032d0  mov     [rsp+0A8h+var_50], rdi
0x1400032d5  mov     r12, [r9+60h]
0x1400032d9  mov     [rsp+0A8h+var_40], r12
0x1400032de  movzx   r13d, word ptr [r9+58h]
0x1400032e3  mov     [rsp+0A8h+var_56], r13w
0x1400032e9  movzx   eax, word ptr [r9+5Ah]
0x1400032ee  mov     [rsp+0A8h+var_58], ax
0x1400032f3  mov     [rsp+0A8h+var_54], ax
0x1400032f8  mov     rsi, [r9+18h]
0x1400032fc  lea     r15d, [rdi+1]
0x140003300  test    rsi, rsi
0x140003303  jz      loc_140003397
0x140003309  mov     ecx, 502h
0x14000330e  movzx   eax, word ptr [rsi]
0x140003311  sub     ax, cx
0x140003314  cmp     ax, r15w
0x140003318  ja      short loc_140003397
0x14000331a  cmp     [rsi+218h], rdi
0x140003321  jz      short loc_140003397
0x140003323  movzx   eax, word ptr [rsi+210h]
0x14000332a  mov     [rsp+0A8h+Size], rax
0x14000332f  mov     r8d, 6E746146h; Tag
0x140003335  mov     edx, eax; NumberOfBytes
0x140003337  mov     ecx, 411h; PoolType
0x14000333c  call    cs:__imp_ExAllocatePoolWithTag
0x140003343  nop     dword ptr [rax+rax+00h]
0x140003348  mov     rdi, rax
0x14000334b  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140003352  jnz     short loc_140003368
0x140003354  test    rax, rax
0x140003357  jz      short loc_140003368
0x140003359  mov     r8, [rsp+0A8h+Size]; Size
0x14000335e  xor     edx, edx; Val
0x140003360  mov     rcx, rax; void *
0x140003363  call    memset
0x140003368  mov     [rsp+0A8h+var_50], rdi
0x14000336d  movzx   r8d, word ptr [rsi+210h]; Size
0x140003375  mov     rdx, [rsi+218h]; Src
0x14000337c  mov     rcx, rdi; void *
0x14000337f  call    memmove
0x140003384  mov     [rbx+60h], rdi
0x140003388  movzx   eax, word ptr [rsi+210h]
0x14000338f  mov     [rbx+5Ah], ax
0x140003393  mov     [rbx+58h], ax
0x140003397  mov     rax, qword ptr cs:xmmword_140017DE8
0x14000339e  mov     [rsp+0A8h+var_68], r14
0x1400033a3  mov     [rsp+0A8h+var_70], 0
0x1400033ac  mov     rcx, [rsp+0A8h+arg_28]
0x1400033b4  mov     [rsp+0A8h+var_78], rcx
0x1400033b9  mov     [rsp+0A8h+var_80], r15d
0x1400033be  mov     ecx, [rsp+0A8h+arg_20]
0x1400033c5  mov     [rsp+0A8h+var_88], ecx
0x1400033c9  mov     r9, rbx
0x1400033cc  mov     r8, [rsp+0A8h+arg_10]
0x1400033d4  mov     rdx, [rsp+0A8h+arg_8]
0x1400033dc  mov     rcx, [rsp+0A8h+arg_0]
0x1400033e4  call    _guard_dispatch_icall
0x1400033e9  mov     esi, eax
0x1400033eb  test    rdi, rdi
0x1400033ee  jz      short loc_140003401
0x1400033f0  xor     edx, edx; Tag
0x1400033f2  mov     rcx, rdi; P
0x1400033f5  call    cs:__imp_ExFreePoolWithTag
0x1400033fc  nop     dword ptr [rax+rax+00h]
0x140003401  mov     [rbx+60h], r12
0x140003405  mov     [rbx+58h], r13w
0x14000340a  movzx   eax, [rsp+0A8h+var_58]
0x14000340f  mov     [rbx+5Ah], ax
0x140003413  mov     eax, esi
0x140003415  jmp     short loc_14000341C
0x140003417  mov     eax, 0C0000010h
0x14000341c  add     rsp, 70h
0x140003420  pop     r15
0x140003422  pop     r14
0x140003424  pop     r13
0x140003426  pop     r12
0x140003428  pop     rdi
0x140003429  pop     rsi
0x14000342a  pop     rbx
0x14000342b  retn
0x14000ccf9  push    rbp
0x14000ccfb  sub     rsp, 50h
0x14000ccff  mov     rbp, rdx
0x14000cd02  mov     rcx, [rbp+58h]; P
0x14000cd06  test    rcx, rcx
0x14000cd09  jz      short loc_14000CD1A
0x14000cd0b  xor     edx, edx; Tag
0x14000cd0d  call    cs:__imp_ExFreePoolWithTag
0x14000cd14  nop     dword ptr [rax+rax+00h]
0x14000cd19  nop
0x14000cd1a  mov     rax, [rbp+68h]
0x14000cd1e  mov     rcx, [rbp+0C8h]
0x14000cd25  mov     [rcx+60h], rax
0x14000cd29  movzx   eax, word ptr [rbp+52h]
0x14000cd2d  mov     [rcx+58h], ax
0x14000cd31  movzx   eax, word ptr [rbp+54h]
0x14000cd35  mov     [rcx+5Ah], ax
0x14000cd39  add     rsp, 50h
0x14000cd3d  pop     rbp
0x14000cd3e  retn
```
