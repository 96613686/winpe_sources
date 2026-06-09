# sub_1407CCFE8

- ea: `0x1407ccfe8`
- end: `0x1407cd216`
- name: `sub_1407CCFE8`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14073e734`

## callees

- `0x140204b38`
- `0x140210ee0`
- `0x140210f70`
- `0x1402121a0`
- `0x1406e80f0`
- `0x1406f4880`
- `0x1407ccfe8`
- `0x1407cd320`

## import_xrefs

- `ext-ms-win-accel-api-km-l1-1-1!AccelShareAddressSpaceWithResource` at `0x1407cd040`
- `ext-ms-win-accel-api-km-l1-1-1!AccelShareAddressSpaceWithResource` at `0x1407cd040`
- `ext-ms-win-accel-api-km-l1-1-1!AccelStopSharingAddressSpaceWithResource` at `0x1407cd1e2`
- `ext-ms-win-accel-api-km-l1-1-1!AccelStopSharingAddressSpaceWithResource` at `0x1407cd1e2`

## pseudocode

```c
__int64 __fastcall sub_1407CCFE8(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v3; // r12
  __int64 v4; // rsi
  unsigned __int8 v6; // al
  __int64 v7; // rdx
  int v8; // r14d
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r15
  unsigned __int64 v16; // rbx
  char *v17; // rax
  char *v18; // rbp
  unsigned __int64 v19; // r14
  char *v20; // rdx
  char *v21; // r14
  struct _SLIST_ENTRY *v22; // r15
  struct _SLIST_ENTRY *v23; // rbx
  unsigned __int64 v24; // r12
  unsigned __int64 v26; // [rsp+20h] [rbp-58h]
  char *v27; // [rsp+20h] [rbp-58h]
  ULONG Count; // [rsp+28h] [rbp-50h]
  struct _SLIST_ENTRY *List; // [rsp+30h] [rbp-48h]
  __int64 v31; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int64 v32; // [rsp+98h] [rbp+20h]

  v3 = a2 + 32;
  v4 = a3;
  v31 = 0;
  v6 = sub_1402121A0(a2 + 32);
  v8 = v6;
  if ( !v6 )
  {
    v9 = -1073741431;
    goto LABEL_14;
  }
  if ( (_DWORD)v4 )
  {
    v10 = v4;
  }
  else
  {
    LOBYTE(v7) = 1;
    v9 = AccelShareAddressSpaceWithResource(*(_QWORD *)(a2 + 16), v7, &v31);
    if ( v9 < 0 )
      goto LABEL_14;
    v10 = 0;
  }
  v11 = *(unsigned int *)(a2 + 64);
  v12 = *(unsigned int *)(a2 + 4 * v10 + 56);
  v13 = *(_DWORD *)(a2 + 4 * v10 + 48) - 1;
  v14 = *(unsigned int *)(a2 + 44);
  v15 = ((int)v11 + v13) / (unsigned int)v11;
  LODWORD(v14) = v14 | 0x80000000;
  Count = ((int)v11 + v13) / (unsigned int)v11;
  v16 = (v15 * v11 * v12 + 95) & 0xFFFFFFFFFFFFFFF0uLL;
  v32 = ((unsigned int)(*(_DWORD *)(a2 + 40) * *(_DWORD *)(a2 + 64)) + 47LL) & 0xFFFFFFFFFFFFFFF0uLL;
  v26 = v32 * (unsigned int)v15;
  v17 = (char *)sub_140204B38(v16 + v26, 1665232243, v14);
  v18 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 0x50u);
    v19 = v32;
    v20 = &v18[v16 + v26];
    *((_DWORD *)v18 + 14) = v15;
    v21 = &v18[v16 + v19];
    *((_QWORD *)v18 + 4) = a2;
    v22 = (struct _SLIST_ENTRY *)(v18 + 80);
    *((_DWORD *)v18 + 15) = v4;
    v23 = (struct _SLIST_ENTRY *)&v18[v16];
    *((_QWORD *)v18 + 5) = v31;
    *((_QWORD *)v18 + 6) = 0;
    List = v23;
    v27 = v20;
    if ( v21 < v20 )
    {
      v24 = v32;
      do
      {
        v23->Next = (struct _SLIST_ENTRY *)v21;
        *((_QWORD *)&v23->Next + 1) = v18;
        v23[1].Next = v22;
        sub_1407CD320(v23, a2, (unsigned int)v4);
        v23 = (struct _SLIST_ENTRY *)v21;
        v21 += v24;
        v22 = (struct _SLIST_ENTRY *)((char *)v22 + (unsigned int)(*(_DWORD *)(a2 + 64) * *(_DWORD *)(a2 + 4 * v4 + 56)));
      }
      while ( v21 < v27 );
      v3 = a2 + 32;
    }
    v23->Next = 0;
    *((_QWORD *)&v23->Next + 1) = v18;
    v23[1].Next = v22;
    sub_1407CD320(v23, a2, (unsigned int)v4);
    InterlockedPushListSList((PSLIST_HEADER)v18 + 1, List, v23, Count);
    ExAcquireRundownProtectionEx((PEX_RUNDOWN_REF)v18 + 6, Count);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v18 + 4) + 68LL));
    v8 = 0;
    v31 = 0;
    v9 = 0;
    *a1 = v18;
  }
  else
  {
    v9 = -1073741670;
  }
LABEL_14:
  if ( v31 )
    AccelStopSharingAddressSpaceWithResource();
  if ( v8 )
    sub_140210EE0(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1407ccfe8  mov     rax, rsp
0x1407ccfeb  mov     [rax+18h], rbx
0x1407ccfef  mov     [rax+8], rcx
0x1407ccff3  push    rbp
0x1407ccff4  push    rsi
0x1407ccff5  push    rdi
0x1407ccff6  push    r12
0x1407ccff8  push    r13
0x1407ccffa  push    r14
0x1407ccffc  push    r15
0x1407ccffe  sub     rsp, 40h
0x1407cd002  lea     r12, [rdx+20h]
0x1407cd006  movsxd  rsi, r8d
0x1407cd009  mov     rcx, r12
0x1407cd00c  mov     qword ptr [rax+10h], 0
0x1407cd014  mov     rdi, rdx
0x1407cd017  call    sub_1402121A0
0x1407cd01c  movzx   r14d, al
0x1407cd020  test    al, al
0x1407cd022  jnz     short loc_1407CD02E
0x1407cd024  mov     ebx, 0C0000189h
0x1407cd029  jmp     loc_1407CD1D5
0x1407cd02e  test    esi, esi
0x1407cd030  jnz     short loc_1407CD05B
0x1407cd032  mov     rcx, [rdi+10h]
0x1407cd036  lea     r8, [rsp+78h+arg_8]
0x1407cd03e  mov     dl, 1
0x1407cd040  call    cs:AccelShareAddressSpaceWithResource
0x1407cd047  nop     dword ptr [rax+rax+00h]
0x1407cd04c  mov     ebx, eax
0x1407cd04e  test    eax, eax
0x1407cd050  js      loc_1407CD1D5
0x1407cd056  xor     r8d, r8d
0x1407cd059  jmp     short loc_1407CD05E
0x1407cd05b  mov     r8, rsi
0x1407cd05e  mov     ecx, [rdi+40h]
0x1407cd061  xor     edx, edx
0x1407cd063  mov     eax, [rdi+r8*4+30h]
0x1407cd068  mov     r13, rsi
0x1407cd06b  mov     ebx, [rdi+r8*4+38h]
0x1407cd070  dec     eax
0x1407cd072  mov     r8d, [rdi+2Ch]
0x1407cd076  add     eax, ecx
0x1407cd078  div     ecx
0x1407cd07a  imul    rbx, rcx
0x1407cd07e  mov     r15d, eax
0x1407cd081  bts     r8d, 1Fh
0x1407cd086  mov     eax, ecx
0x1407cd088  mov     qword ptr [rsp+78h+Count], r15
0x1407cd08d  imul    eax, [rdi+28h]
0x1407cd091  mov     ecx, r15d
0x1407cd094  imul    rbx, r15
0x1407cd098  add     rax, 2Fh ; '/'
0x1407cd09c  mov     edx, 63416D73h
0x1407cd0a1  and     rax, 0FFFFFFFFFFFFFFF0h
0x1407cd0a5  add     rbx, 5Fh ; '_'
0x1407cd0a9  imul    rcx, rax
0x1407cd0ad  and     rbx, 0FFFFFFFFFFFFFFF0h
0x1407cd0b1  mov     [rsp+78h+arg_18], rax
0x1407cd0b9  mov     [rsp+78h+var_58], rcx
0x1407cd0be  add     rcx, rbx
0x1407cd0c1  call    sub_140204B38
0x1407cd0c6  mov     rbp, rax
0x1407cd0c9  test    rax, rax
0x1407cd0cc  jnz     short loc_1407CD0D8
0x1407cd0ce  mov     ebx, 0C000009Ah
0x1407cd0d3  jmp     loc_1407CD1D5
0x1407cd0d8  xor     edx, edx; Val
0x1407cd0da  mov     rcx, rbp; void *
0x1407cd0dd  lea     r8d, [rdx+50h]; Size
0x1407cd0e1  call    memset_0
0x1407cd0e6  mov     rdx, [rsp+78h+var_58]
0x1407cd0eb  lea     rcx, [rbx+rbp]
0x1407cd0ef  mov     r14, [rsp+78h+arg_18]
0x1407cd0f7  add     rdx, rcx
0x1407cd0fa  mov     [rbp+38h], r15d
0x1407cd0fe  add     r14, rcx
0x1407cd101  mov     [rbp+20h], rdi
0x1407cd105  lea     r15, [rbp+50h]
0x1407cd109  mov     [rbp+3Ch], esi
0x1407cd10c  mov     rbx, rcx
0x1407cd10f  mov     rax, [rsp+78h+arg_8]
0x1407cd117  mov     [rbp+28h], rax
0x1407cd11b  mov     qword ptr [rbp+30h], 0
0x1407cd123  mov     [rsp+78h+List], rcx
0x1407cd128  mov     [rsp+78h+var_58], rdx
0x1407cd12d  cmp     r14, rdx
0x1407cd130  jnb     short loc_1407CD170
0x1407cd132  mov     r12, [rsp+78h+arg_18]
0x1407cd13a  mov     r8d, esi
0x1407cd13d  mov     [rbx], r14
0x1407cd140  mov     rdx, rdi
0x1407cd143  mov     [rbx+8], rbp
0x1407cd147  mov     rcx, rbx
0x1407cd14a  mov     [rbx+10h], r15
0x1407cd14e  call    sub_1407CD320
0x1407cd153  mov     eax, [rdi+r13*4+38h]
0x1407cd158  mov     rbx, r14
0x1407cd15b  imul    eax, [rdi+40h]
0x1407cd15f  add     r14, r12
0x1407cd162  add     r15, rax
0x1407cd165  cmp     r14, [rsp+78h+var_58]
0x1407cd16a  jb      short loc_1407CD13A
0x1407cd16c  lea     r12, [rdi+20h]
0x1407cd170  mov     r8d, esi
0x1407cd173  mov     qword ptr [rbx], 0
0x1407cd17a  mov     rdx, rdi
0x1407cd17d  mov     [rbx+8], rbp
0x1407cd181  mov     rcx, rbx
0x1407cd184  mov     [rbx+10h], r15
0x1407cd188  call    sub_1407CD320
0x1407cd18d  mov     rdi, qword ptr [rsp+78h+Count]
0x1407cd192  lea     rcx, [rbp+10h]; ListHead
0x1407cd196  mov     rdx, [rsp+78h+List]; List
0x1407cd19b  mov     r9d, edi; Count
0x1407cd19e  mov     r8, rbx; ListEnd
0x1407cd1a1  call    InterlockedPushListSList
0x1407cd1a6  mov     edx, edi; Count
0x1407cd1a8  lea     rcx, [rbp+30h]; RunRef
0x1407cd1ac  call    ExAcquireRundownProtectionEx
0x1407cd1b1  mov     rax, [rbp+20h]
0x1407cd1b5  lock inc dword ptr [rax+44h]
0x1407cd1b9  mov     rax, [rsp+78h+arg_0]
0x1407cd1c1  xor     r14d, r14d
0x1407cd1c4  mov     [rsp+78h+arg_8], 0
0x1407cd1d0  xor     ebx, ebx
0x1407cd1d2  mov     [rax], rbp
0x1407cd1d5  mov     rcx, [rsp+78h+arg_8]
0x1407cd1dd  test    rcx, rcx
0x1407cd1e0  jz      short loc_1407CD1EE
0x1407cd1e2  call    cs:AccelStopSharingAddressSpaceWithResource
0x1407cd1e9  nop     dword ptr [rax+rax+00h]
0x1407cd1ee  test    r14d, r14d
0x1407cd1f1  jz      short loc_1407CD1FB
0x1407cd1f3  mov     rcx, r12
0x1407cd1f6  call    sub_140210EE0
0x1407cd1fb  mov     eax, ebx
0x1407cd1fd  mov     rbx, [rsp+78h+arg_10]
0x1407cd205  add     rsp, 40h
0x1407cd209  pop     r15
0x1407cd20b  pop     r14
0x1407cd20d  pop     r13
0x1407cd20f  pop     r12
0x1407cd211  pop     rdi
0x1407cd212  pop     rsi
0x1407cd213  pop     rbp
0x1407cd214  retn
```
