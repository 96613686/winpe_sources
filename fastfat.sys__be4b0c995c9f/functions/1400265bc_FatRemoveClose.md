# FatRemoveClose

- ea: `0x1400265bc`
- end: `0x1400267d6`
- name: `FatRemoveClose`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140026390`

## callees

- `0x1400265bc`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400267bd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400267bd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400265d5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400265d5`

## pseudocode

```c
_QWORD *__fastcall FatRemoveClose(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  char v5; // cl
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rax

  v2 = a1;
  ExAcquireFastMutexUnsafe(&FatCloseQueueMutex);
  if ( a1 )
    goto LABEL_18;
  if ( !a2 )
    goto LABEL_30;
  v5 = byte_140017D4C;
  if ( (byte_140017D4C & 0x20) != 0 )
  {
    if ( dword_140017D54 >= (unsigned int)FatMaxDelayedCloseCount )
      goto LABEL_9;
    v5 = byte_140017D4C & 0xDF;
  }
  else
  {
    if ( dword_140017D54 <= (unsigned int)(2 * FatMaxDelayedCloseCount) )
      goto LABEL_9;
    v5 = byte_140017D4C | 0x20;
  }
  byte_140017D4C = v5;
LABEL_9:
  if ( (v5 & 0x40) != 0 )
  {
    if ( dword_140017D68 >= (unsigned int)FatMaxDelayedCloseCount )
      goto LABEL_15;
    v5 &= ~0x40u;
  }
  else
  {
    if ( dword_140017D68 <= (unsigned int)(2 * FatMaxDelayedCloseCount) )
      goto LABEL_15;
    v5 |= 0x40u;
  }
  byte_140017D4C = v5;
LABEL_15:
  if ( (v5 & 0x20) == 0 && (v5 & 0x40) == 0 )
    goto LABEL_30;
  v2 = a2;
LABEL_18:
  v6 = (_QWORD *)(v2 + 1136);
  v7 = *(_QWORD **)(v2 + 1136);
  if ( v7 != (_QWORD *)(v2 + 1136) )
  {
    if ( (_QWORD *)v7[1] != v6 )
      goto LABEL_43;
    v8 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_43;
    *v6 = v8;
    *(_QWORD *)(v8 + 8) = v6;
    --dword_140017D54;
LABEL_22:
    v9 = v7 - 2;
    v10 = *v9;
    if ( *(_QWORD **)(*v9 + 8LL) == v9 )
    {
      v11 = (_QWORD *)v9[1];
      if ( (_QWORD *)*v11 == v9 )
      {
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        goto LABEL_47;
      }
    }
LABEL_43:
    __fastfail(3u);
  }
  v12 = (_QWORD *)(v2 + 1152);
  v7 = *(_QWORD **)(v2 + 1152);
  if ( v7 != (_QWORD *)(v2 + 1152) )
  {
    if ( (_QWORD *)v7[1] != v12 )
      goto LABEL_43;
    v13 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_43;
    *v12 = v13;
    *(_QWORD *)(v13 + 8) = v12;
    --dword_140017D68;
    goto LABEL_22;
  }
  if ( !a2 )
  {
    v9 = 0;
    goto LABEL_47;
  }
LABEL_30:
  v9 = (_QWORD *)qword_140017D58;
  if ( (__int64 *)qword_140017D58 != &qword_140017D58 )
  {
    if ( *(__int64 **)(qword_140017D58 + 8) != &qword_140017D58 )
      goto LABEL_43;
    v14 = *(_QWORD *)qword_140017D58;
    if ( *(_QWORD *)(*(_QWORD *)qword_140017D58 + 8LL) != qword_140017D58 )
      goto LABEL_43;
    qword_140017D58 = *(_QWORD *)qword_140017D58;
    *(_QWORD *)(v14 + 8) = &qword_140017D58;
    --dword_140017D54;
LABEL_40:
    v16 = v9[2];
    if ( *(_QWORD **)(v16 + 8) == v9 + 2 )
    {
      v17 = (_QWORD *)v9[3];
      if ( (_QWORD *)*v17 == v9 + 2 )
      {
        *v17 = v16;
        *(_QWORD *)(v16 + 8) = v17;
        goto LABEL_47;
      }
    }
    goto LABEL_43;
  }
  v9 = (_QWORD *)qword_140017D70;
  if ( (__int64 *)qword_140017D70 != &qword_140017D70
    && (dword_140017D68 > (unsigned int)FatMaxDelayedCloseCount >> 1 || (byte_140017D4C & 8) != 0) )
  {
    if ( *(__int64 **)(qword_140017D70 + 8) != &qword_140017D70 )
      goto LABEL_43;
    v15 = *(_QWORD *)qword_140017D70;
    if ( *(_QWORD *)(*(_QWORD *)qword_140017D70 + 8LL) != qword_140017D70 )
      goto LABEL_43;
    qword_140017D70 = *(_QWORD *)qword_140017D70;
    *(_QWORD *)(v15 + 8) = &qword_140017D70;
    --dword_140017D68;
    goto LABEL_40;
  }
  v9 = 0;
  if ( !a1 )
    byte_140017D4C &= ~4u;
LABEL_47:
  ExReleaseFastMutexUnsafe(&FatCloseQueueMutex);
  return v9;
}

```

## disassembly

```asm
0x1400265bc  push    rbx
0x1400265be  push    rbp
0x1400265bf  push    rsi
0x1400265c0  push    rdi
0x1400265c1  sub     rsp, 28h
0x1400265c5  mov     rdi, rcx
0x1400265c8  mov     rbp, rcx
0x1400265cb  lea     rcx, FatCloseQueueMutex; FastMutex
0x1400265d2  mov     rsi, rdx
0x1400265d5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400265dc  nop     dword ptr [rax+rax+00h]
0x1400265e1  test    rbp, rbp
0x1400265e4  jnz     short loc_14002665E
0x1400265e6  test    rsi, rsi
0x1400265e9  jz      loc_1400266F9
0x1400265ef  mov     cl, cs:byte_140017D4C
0x1400265f5  mov     r10b, 20h ; ' '
0x1400265f8  mov     edx, cs:FatMaxDelayedCloseCount
0x1400265fe  test    r10b, cl
0x140026601  jnz     short loc_140026613
0x140026603  lea     eax, [rdx+rdx]
0x140026606  cmp     cs:dword_140017D54, eax
0x14002660c  jbe     short loc_140026624
0x14002660e  or      cl, r10b
0x140026611  jmp     short loc_14002661E
0x140026613  cmp     cs:dword_140017D54, edx
0x140026619  jnb     short loc_140026624
0x14002661b  and     cl, 0DFh
0x14002661e  mov     cs:byte_140017D4C, cl
0x140026624  mov     r9b, 40h ; '@'
0x140026627  test    r9b, cl
0x14002662a  jnz     short loc_14002663C
0x14002662c  lea     eax, [rdx+rdx]
0x14002662f  cmp     cs:dword_140017D68, eax
0x140026635  jbe     short loc_14002664D
0x140026637  or      cl, r9b
0x14002663a  jmp     short loc_140026647
0x14002663c  cmp     cs:dword_140017D68, edx
0x140026642  jnb     short loc_14002664D
0x140026644  and     cl, 0BFh
0x140026647  mov     cs:byte_140017D4C, cl
0x14002664d  test    r10b, cl
0x140026650  jnz     short loc_14002665B
0x140026652  test    r9b, cl
0x140026655  jz      loc_1400266F9
0x14002665b  mov     rdi, rsi
0x14002665e  lea     rax, [rdi+470h]
0x140026665  mov     rbx, [rax]
0x140026668  cmp     rbx, rax
0x14002666b  jz      short loc_1400266BB
0x14002666d  cmp     [rbx+8], rax
0x140026671  jnz     loc_14002679D
0x140026677  mov     rcx, [rbx]
0x14002667a  cmp     [rcx+8], rbx
0x14002667e  jnz     loc_14002679D
0x140026684  mov     [rax], rcx
0x140026687  mov     [rcx+8], rax
0x14002668b  dec     cs:dword_140017D54
0x140026691  add     rbx, 0FFFFFFFFFFFFFFF0h
0x140026695  mov     rcx, [rbx]
0x140026698  cmp     [rcx+8], rbx
0x14002669c  jnz     loc_14002679D
0x1400266a2  mov     rax, [rbx+8]
0x1400266a6  cmp     [rax], rbx
0x1400266a9  jnz     loc_14002679D
0x1400266af  mov     [rax], rcx
0x1400266b2  mov     [rcx+8], rax
0x1400266b6  jmp     loc_1400267B6
0x1400266bb  lea     rax, [rdi+480h]
0x1400266c2  mov     rbx, [rax]
0x1400266c5  cmp     rbx, rax
0x1400266c8  jz      short loc_1400266F0
0x1400266ca  cmp     [rbx+8], rax
0x1400266ce  jnz     loc_14002679D
0x1400266d4  mov     rcx, [rbx]
0x1400266d7  cmp     [rcx+8], rbx
0x1400266db  jnz     loc_14002679D
0x1400266e1  mov     [rax], rcx
0x1400266e4  mov     [rcx+8], rax
0x1400266e8  dec     cs:dword_140017D68
0x1400266ee  jmp     short loc_140026691
0x1400266f0  test    rsi, rsi
0x1400266f3  jz      loc_1400267B4
0x1400266f9  mov     rbx, cs:qword_140017D58
0x140026700  lea     rcx, qword_140017D58
0x140026707  cmp     rbx, rcx
0x14002670a  jz      short loc_140026732
0x14002670c  cmp     [rbx+8], rcx
0x140026710  jnz     loc_14002679D
0x140026716  mov     rax, [rbx]
0x140026719  cmp     [rax+8], rbx
0x14002671d  jnz     short loc_14002679D
0x14002671f  mov     cs:qword_140017D58, rax
0x140026726  mov     [rax+8], rcx
0x14002672a  dec     cs:dword_140017D54
0x140026730  jmp     short loc_14002677E
0x140026732  mov     rbx, cs:qword_140017D70
0x140026739  lea     rcx, qword_140017D70
0x140026740  cmp     rbx, rcx
0x140026743  jz      short loc_1400267A4
0x140026745  mov     eax, cs:FatMaxDelayedCloseCount
0x14002674b  shr     eax, 1
0x14002674d  cmp     cs:dword_140017D68, eax
0x140026753  ja      short loc_14002675E
0x140026755  test    cs:byte_140017D4C, 8
0x14002675c  jz      short loc_1400267A4
0x14002675e  cmp     [rbx+8], rcx
0x140026762  jnz     short loc_14002679D
0x140026764  mov     rax, [rbx]
0x140026767  cmp     [rax+8], rbx
0x14002676b  jnz     short loc_14002679D
0x14002676d  mov     cs:qword_140017D70, rax
0x140026774  mov     [rax+8], rcx
0x140026778  dec     cs:dword_140017D68
0x14002677e  lea     rcx, [rbx+10h]
0x140026782  mov     rdx, [rcx]
0x140026785  cmp     [rdx+8], rcx
0x140026789  jnz     short loc_14002679D
0x14002678b  mov     rax, [rcx+8]
0x14002678f  cmp     [rax], rcx
0x140026792  jnz     short loc_14002679D
0x140026794  mov     [rax], rdx
0x140026797  mov     [rdx+8], rax
0x14002679b  jmp     short loc_1400267B6
0x14002679d  mov     ecx, 3
0x1400267a2  int     29h; Win8: RtlFailFast(ecx)
0x1400267a4  xor     ebx, ebx
0x1400267a6  test    rbp, rbp
0x1400267a9  jnz     short loc_1400267B6
0x1400267ab  and     cs:byte_140017D4C, 0FBh
0x1400267b2  jmp     short loc_1400267B6
0x1400267b4  xor     ebx, ebx
0x1400267b6  lea     rcx, FatCloseQueueMutex; FastMutex
0x1400267bd  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400267c4  nop     dword ptr [rax+rax+00h]
0x1400267c9  mov     rax, rbx
0x1400267cc  add     rsp, 28h
0x1400267d0  pop     rdi
0x1400267d1  pop     rsi
0x1400267d2  pop     rbp
0x1400267d3  pop     rbx
0x1400267d4  retn
```
