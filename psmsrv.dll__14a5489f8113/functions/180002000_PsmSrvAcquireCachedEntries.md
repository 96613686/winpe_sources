# PsmSrvAcquireCachedEntries

- ea: `0x180002000`
- end: `0x1800022dd`
- name: `PsmSrvAcquireCachedEntries`
- size: `733`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000191c`
- `0x180001fdc`
- `0x180002000`
- `0x180003700`
- `0x1800037f4`
- `0x18000436c`
- `0x180009b40`
- `0x180022640`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180002159`
- `ntdll!RtlLengthSid` at `0x180002159`

## pseudocode

```c
__int64 __fastcall PsmSrvAcquireCachedEntries(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v3; // r14
  unsigned int v4; // r13d
  char *v5; // rbp
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 NextUserContext; // rdi
  __int64 i; // r8
  volatile signed __int32 *NextApplicationToCache; // rbx
  unsigned int v12; // esi
  char *v13; // rax
  char *v14; // r12
  PVOID Heap; // r12
  int v16; // esi
  size_t v17; // rsi
  PVOID v18; // rax
  int v19; // edx
  __int64 v20; // r12
  WCHAR *v21; // rbx
  void *v22; // rdi
  PVOID v24; // [rsp+30h] [rbp-58h]
  size_t Size; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v26; // [rsp+98h] [rbp+10h]
  _DWORD *v27; // [rsp+A0h] [rbp+18h]
  size_t v28; // [rsp+A8h] [rbp+20h]

  v27 = a3;
  v26 = a2;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v7 = *(_QWORD *)(a1 + 56);
  v8 = 0;
LABEL_2:
  NextUserContext = PsmpGetNextUserContext(v7, v8);
  if ( !NextUserContext )
  {
    if ( !(_DWORD)v3 && v5 )
    {
      PsmpFreeHeap(v5);
      v5 = 0;
    }
    v16 = 0;
    goto LABEL_31;
  }
  for ( i = 0; ; i = (__int64)NextApplicationToCache )
  {
    NextApplicationToCache = PsmpGetNextApplicationToCache(a1, NextUserContext, i);
    if ( !NextApplicationToCache )
    {
      v7 = *(_QWORD *)(a1 + 56);
      v8 = NextUserContext;
      goto LABEL_2;
    }
    if ( (_DWORD)v3 == v4 )
      break;
LABEL_12:
    Size = *((_QWORD *)NextApplicationToCache + 2);
    Heap = PsmpAllocateHeap(Size);
    if ( !Heap )
      goto LABEL_22;
    v28 = 80 * v3;
    v16 = PsmpSetApplicationCache(0, 0, 0, NextApplicationToCache, a1, (__int64)&v5[80 * v3 + 16]);
    if ( v16 >= 0 )
    {
      memcpy_0(Heap, *((const void **)NextApplicationToCache + 1), Size);
      v17 = v28;
      *(_QWORD *)&v5[v28 + 8] = Heap;
      LODWORD(Size) = RtlLengthSid(*(PSID *)(*((_QWORD *)NextApplicationToCache + 39) + 40LL));
      v28 = (unsigned int)Size;
      v18 = PsmpAllocateHeap((unsigned int)Size);
      v24 = v18;
      if ( !v18 )
      {
        v16 = -1073741670;
        PsmpFreeHeap(Heap);
        goto LABEL_23;
      }
      memcpy_0(v18, *(const void **)(*((_QWORD *)NextApplicationToCache + 39) + 40LL), v28);
      v3 = (unsigned int)(v3 + 1);
      v19 = *(_DWORD *)(*((_QWORD *)NextApplicationToCache + 39) + 4LL);
      *(_QWORD *)&v5[v17 + 72] = v24;
      *(_DWORD *)&v5[v17 + 64] = Size;
      *(_DWORD *)&v5[v17] = v19;
    }
    else
    {
      PsmpFreeHeap(Heap);
      if ( v16 != -1073741772 )
        goto LABEL_23;
    }
  }
  v12 = v4 + 8;
  if ( v4 + 8 < v4 || (Size = 0, !is_mul_ok(v12, 0x50u)) )
  {
    v16 = -1073741675;
    goto LABEL_23;
  }
  v13 = (char *)PsmpAllocateHeap(80LL * v12);
  v14 = v13;
  if ( v13 )
  {
    v4 += 8;
    if ( v5 )
    {
      memcpy_0(v13, v5, 80 * v3);
      PsmpFreeHeap(v5);
    }
    v5 = v14;
    goto LABEL_12;
  }
LABEL_22:
  v16 = -1073741670;
LABEL_23:
  PsmpDereferenceApplicationEx((__int64)NextApplicationToCache, 0);
  if ( (_DWORD)v3 )
  {
    v20 = (unsigned int)v3;
    do
    {
      --v20;
      v21 = *(WCHAR **)&v5[80 * v20 + 8];
      v22 = *(void **)&v5[80 * v20 + 72];
      LODWORD(Size) = *(_DWORD *)&v5[80 * v20];
      PsmpSetApplicationCache((int *)&Size, v22, v21, 0, a1, 0);
      PsmpFreeHeap(v21);
      PsmpFreeHeap(v22);
      LODWORD(v3) = v3 - 1;
    }
    while ( (_DWORD)v3 );
  }
  PsmpFreeHeap(v5);
  LODWORD(v3) = 0;
  v5 = 0;
LABEL_31:
  *v26 = v5;
  *v27 = v3;
  if ( v16 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids,
      *(unsigned int *)(a1 + 24),
      v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180002000  mov     [rsp+arg_10], r8
0x180002005  mov     [rsp+arg_8], rdx
0x18000200a  push    rbx
0x18000200b  push    rbp
0x18000200c  push    rsi
0x18000200d  push    rdi
0x18000200e  push    r12
0x180002010  push    r13
0x180002012  push    r14
0x180002014  push    r15
0x180002016  sub     rsp, 48h
0x18000201a  xor     r14d, r14d
0x18000201d  xor     r13d, r13d
0x180002020  xor     ebp, ebp
0x180002022  mov     r15, rcx
0x180002025  mov     rcx, [rcx+38h]
0x180002029  xor     edx, edx
0x18000202b  call    PsmpGetNextUserContext
0x180002030  mov     rdi, rax
0x180002033  test    rax, rax
0x180002036  jz      loc_18000226A
0x18000203c  xor     r8d, r8d
0x18000203f  mov     rdx, rdi
0x180002042  mov     rcx, r15
0x180002045  call    PsmpGetNextApplicationToCache
0x18000204a  mov     rbx, rax
0x18000204d  test    rax, rax
0x180002050  jz      loc_1800021C9
0x180002056  cmp     r14d, r13d
0x180002059  jnz     short loc_1800020C1
0x18000205b  lea     esi, [r13+8]
0x18000205f  cmp     esi, r13d
0x180002062  jb      loc_1800021D5
0x180002068  mov     ecx, esi
0x18000206a  mov     eax, 50h ; 'P'
0x18000206f  mul     rcx
0x180002072  mov     [rsp+88h+Size], 0
0x18000207e  test    rdx, rdx
0x180002081  jnz     loc_1800021D5
0x180002087  mov     rcx, rax
0x18000208a  call    PsmpAllocateHeap
0x18000208f  mov     r12, rax
0x180002092  test    rax, rax
0x180002095  jz      loc_1800021EB
0x18000209b  mov     r13d, esi
0x18000209e  test    rbp, rbp
0x1800020a1  jz      short loc_1800020BE
0x1800020a3  lea     r8, [r14+r14*4]
0x1800020a7  mov     rdx, rbp; Src
0x1800020aa  shl     r8, 4; Size
0x1800020ae  mov     rcx, rax; void *
0x1800020b1  call    memcpy_0
0x1800020b6  mov     rcx, rbp
0x1800020b9  call    PsmpFreeHeap
0x1800020be  mov     rbp, r12
0x1800020c1  mov     rax, [rbx+10h]
0x1800020c5  mov     rcx, rax
0x1800020c8  mov     [rsp+88h+Size], rax
0x1800020d0  call    PsmpAllocateHeap
0x1800020d5  mov     r12, rax
0x1800020d8  test    rax, rax
0x1800020db  jz      loc_1800021EB
0x1800020e1  lea     rax, [r14+r14*4]
0x1800020e5  mov     r9, rbx
0x1800020e8  shl     rax, 4
0x1800020ec  xor     r8d, r8d
0x1800020ef  xor     edx, edx
0x1800020f1  mov     [rsp+88h+arg_18], rax
0x1800020f9  lea     rcx, [rax+10h]
0x1800020fd  add     rcx, rbp
0x180002100  mov     [rsp+88h+var_60], rcx
0x180002105  xor     ecx, ecx
0x180002107  mov     [rsp+88h+var_68], r15
0x18000210c  call    PsmpSetApplicationCache
0x180002111  mov     esi, eax
0x180002113  mov     rcx, r12; void *
0x180002116  test    eax, eax
0x180002118  jns     short loc_180002130
0x18000211a  call    PsmpFreeHeap
0x18000211f  cmp     esi, 0C0000034h
0x180002125  jnz     loc_1800021F0
0x18000212b  jmp     loc_1800021C1
0x180002130  mov     r8, [rsp+88h+Size]; Size
0x180002138  mov     rdx, [rbx+8]; Src
0x18000213c  call    memcpy_0
0x180002141  mov     rsi, [rsp+88h+arg_18]
0x180002149  mov     [rsi+rbp+8], r12
0x18000214e  mov     rcx, [rbx+138h]
0x180002155  mov     rcx, [rcx+28h]; Sid
0x180002159  call    cs:__imp_RtlLengthSid
0x18000215f  mov     dword ptr [rsp+88h+Size], eax
0x180002166  mov     eax, eax
0x180002168  mov     ecx, eax
0x18000216a  mov     [rsp+88h+arg_18], rax
0x180002172  call    PsmpAllocateHeap
0x180002177  mov     [rsp+88h+var_58], rax
0x18000217c  test    rax, rax
0x18000217f  jz      short loc_1800021DC
0x180002181  mov     rdx, [rbx+138h]
0x180002188  mov     rcx, rax; void *
0x18000218b  mov     r8, [rsp+88h+arg_18]; Size
0x180002193  mov     rdx, [rdx+28h]; Src
0x180002197  call    memcpy_0
0x18000219c  mov     rcx, [rbx+138h]
0x1800021a3  inc     r14d
0x1800021a6  mov     rax, [rsp+88h+var_58]
0x1800021ab  mov     edx, [rcx+4]
0x1800021ae  mov     [rsi+rbp+48h], rax
0x1800021b3  mov     eax, dword ptr [rsp+88h+Size]
0x1800021ba  mov     [rsi+rbp+40h], eax
0x1800021be  mov     [rsi+rbp], edx
0x1800021c1  mov     r8, rbx
0x1800021c4  jmp     loc_18000203F
0x1800021c9  mov     rcx, [r15+38h]
0x1800021cd  mov     rdx, rdi
0x1800021d0  jmp     loc_18000202B
0x1800021d5  mov     esi, 0C0000095h
0x1800021da  jmp     short loc_1800021F0
0x1800021dc  mov     rcx, r12
0x1800021df  mov     esi, 0C000009Ah
0x1800021e4  call    PsmpFreeHeap
0x1800021e9  jmp     short loc_1800021F0
0x1800021eb  mov     esi, 0C000009Ah
0x1800021f0  xor     edx, edx
0x1800021f2  mov     rcx, rbx
0x1800021f5  call    PsmpDereferenceApplicationEx
0x1800021fa  test    r14d, r14d
0x1800021fd  jz      short loc_18000225B
0x1800021ff  mov     r12d, r14d
0x180002202  dec     r12
0x180002205  mov     [rsp+88h+var_60], 0
0x18000220e  xor     r9d, r9d
0x180002211  mov     [rsp+88h+var_68], r15
0x180002216  lea     rcx, [rsp+88h+Size]
0x18000221e  lea     rax, [r12+r12*4]
0x180002222  add     rax, rax
0x180002225  mov     rbx, [rbp+rax*8+8]
0x18000222a  mov     rdi, [rbp+rax*8+48h]
0x18000222f  mov     r8, rbx
0x180002232  mov     eax, [rbp+rax*8+0]
0x180002236  mov     rdx, rdi
0x180002239  mov     dword ptr [rsp+88h+Size], eax
0x180002240  call    PsmpSetApplicationCache
0x180002245  mov     rcx, rbx
0x180002248  call    PsmpFreeHeap
0x18000224d  mov     rcx, rdi
0x180002250  call    PsmpFreeHeap
0x180002255  add     r14d, 0FFFFFFFFh
0x180002259  jnz     short loc_180002202
0x18000225b  mov     rcx, rbp
0x18000225e  call    PsmpFreeHeap
0x180002263  xor     r14d, r14d
0x180002266  xor     ebp, ebp
0x180002268  jmp     short loc_180002280
0x18000226a  test    r14d, r14d
0x18000226d  jnz     short loc_18000227E
0x18000226f  test    rbp, rbp
0x180002272  jz      short loc_18000227E
0x180002274  mov     rcx, rbp
0x180002277  call    PsmpFreeHeap
0x18000227c  xor     ebp, ebp
0x18000227e  xor     esi, esi
0x180002280  mov     rax, [rsp+88h+arg_8]
0x180002288  mov     [rax], rbp
0x18000228b  mov     rax, [rsp+88h+arg_10]
0x180002293  mov     [rax], r14d
0x180002296  test    esi, esi
0x180002298  jns     short loc_1800022CA
0x18000229a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022a1  test    byte ptr [rcx+1Ch], 2
0x1800022a5  jz      short loc_1800022CA
0x1800022a7  cmp     byte ptr [rcx+19h], 2
0x1800022ab  jb      short loc_1800022CA
0x1800022ad  mov     r9d, [r15+18h]
0x1800022b1  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x1800022b8  mov     rcx, [rcx+10h]
0x1800022bc  mov     edx, 0Bh
0x1800022c1  mov     dword ptr [rsp+88h+var_68], esi
0x1800022c5  call    WPP_SF_Dd
0x1800022ca  mov     eax, esi
0x1800022cc  add     rsp, 48h
0x1800022d0  pop     r15
0x1800022d2  pop     r14
0x1800022d4  pop     r13
0x1800022d6  pop     r12
0x1800022d8  pop     rdi
0x1800022d9  pop     rsi
0x1800022da  pop     rbp
0x1800022db  pop     rbx
0x1800022dc  retn
```
