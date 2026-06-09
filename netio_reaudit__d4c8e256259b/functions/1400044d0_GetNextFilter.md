# GetNextFilter

- ea: `0x1400044d0`
- end: `0x140004714`
- name: `GetNextFilter`
- size: `580`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140005a10`
- `0x14001c23c`
- `0x140036ec0`

## callees

- `0x1400044d0`
- `0x140004970`
- `0x14000c210`
- `0x140038dc8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004691`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004691`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400046c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400046c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000466d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000466d`

## pseudocode

```c
__int64 __fastcall GetNextFilter(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // r8
  _QWORD *v3; // rdi
  __int64 v4; // rbx
  __int64 v7; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // r11
  _QWORD *v15; // rbp
  unsigned __int64 v16; // r9
  unsigned __int64 *v17; // rax
  __int64 v18; // r14
  __int64 v19; // rbp
  bool v20; // dl
  signed __int64 v21; // rcx
  void *v22; // rcx
  int v23; // eax

  v2 = (_QWORD *)*a1;
  v3 = 0;
  v4 = 0;
  if ( (_QWORD *)*a1 == a1 )
  {
LABEL_6:
    v4 = 0;
    goto LABEL_7;
  }
  do
  {
    v7 = v2[*((__int16 *)v2 + 13) + 5];
    if ( !v4 )
    {
LABEL_3:
      v4 = v2[*((__int16 *)v2 + 13) + 5];
      v3 = v2;
      goto LABEL_4;
    }
    v13 = *(_DWORD *)(v4 + 60);
    if ( *(_DWORD *)(v7 + 60) > v13 )
    {
      v23 = 1;
      goto LABEL_37;
    }
    if ( *(_DWORD *)(v7 + 60) < v13 )
    {
      v23 = -1;
LABEL_37:
      if ( v23 == 1 )
        goto LABEL_3;
      goto LABEL_4;
    }
    v14 = *(_QWORD *)(v4 + 24);
    v15 = *(_QWORD **)(v7 + 24);
    v16 = **(_QWORD **)(v14 + 16);
    v17 = (unsigned __int64 *)v15[2];
    if ( *v17 >= v16 && (*v17 > v16 || *v15 > *(_QWORD *)v14) )
      goto LABEL_3;
LABEL_4:
    v2 = (_QWORD *)*v2;
  }
  while ( v2 != a1 );
  if ( !v4 )
    goto LABEL_6;
  _InterlockedIncrement64((volatile signed __int64 *)(v4 + 16));
  if ( (__int16)++*((_WORD *)v3 + 13) == *((unsigned __int16 *)v3 + 12) - 1 )
  {
    v9 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v10 = (_QWORD *)v3[1], (_QWORD *)*v10 != v3) )
LABEL_13:
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    *(_OWORD *)v3 = 0;
    v11 = (_QWORD *)v3[2];
    if ( v11 )
    {
      v12 = (_QWORD *)a1[1];
      if ( (_QWORD *)*v12 != a1 )
        goto LABEL_13;
      *v11 = a1;
      v11[1] = v12;
      *v12 = v11;
      a1[1] = v11;
    }
    v18 = 0;
    if ( *((_WORD *)v3 + 12) )
    {
      while ( 2 )
      {
        v19 = v3[v18 + 4];
        v20 = 0;
        _InterlockedIncrement64((volatile signed __int64 *)(v19 + 16));
        v21 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v19 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
        if ( (_DWORD)v21 == HIDWORD(v21) )
        {
          _m_prefetchw((const void *)(v19 + 52));
          v20 = (_InterlockedOr((volatile signed __int32 *)(v19 + 52), 0x10u) & 0x10) == 0;
        }
        if ( (*(_DWORD *)(*(_QWORD *)(v19 + 24) + 40LL) & 0x4000) != 0 && v20 )
        {
          if ( !KeGetCurrentIrql() )
          {
            FeNotifyIntFilterDelete(v19);
            goto LABEL_26;
          }
          NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
        }
        else
        {
LABEL_26:
          if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v19 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
            FreeWFPFilter((PVOID)v19);
        }
        v18 = (unsigned int)(v18 + 1);
        if ( (unsigned int)v18 >= *((unsigned __int16 *)v3 + 12) )
          break;
        continue;
      }
    }
    if ( (*((_DWORD *)v3 + 7) & 1) == 0 )
    {
      v22 = (void *)v3[11];
      if ( v22 )
      {
        ExFreePoolWithTag(v22, 0);
        v3[11] = 0xBADBADFABADBADFAuLL;
      }
      ExFreeToNPagedLookasideList(gWfpGlobal, v3);
    }
  }
LABEL_7:
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x1400044d0  mov     [rsp+arg_8], rbx
0x1400044d5  mov     [rsp+arg_10], rbp
0x1400044da  push    rsi
0x1400044db  push    rdi
0x1400044dc  push    r15
0x1400044de  sub     rsp, 20h
0x1400044e2  mov     r8, [rcx]
0x1400044e5  xor     edi, edi
0x1400044e7  xor     ebx, ebx
0x1400044e9  mov     rsi, rdx
0x1400044ec  mov     rdx, rcx
0x1400044ef  cmp     r8, rcx
0x1400044f2  jz      short loc_14000451C
0x1400044f4  mov     r15d, 1
0x1400044fa  movsx   rax, word ptr [r8+1Ah]
0x1400044ff  mov     rcx, [r8+rax*8+28h]
0x140004504  test    rbx, rbx
0x140004507  jnz     short loc_140004586
0x140004509  mov     rbx, rcx
0x14000450c  mov     rdi, r8
0x14000450f  mov     r8, [r8]
0x140004512  cmp     r8, rdx
0x140004515  jnz     short loc_1400044FA
0x140004517  test    rbx, rbx
0x14000451a  jnz     short loc_140004537
0x14000451c  xor     ebx, ebx
0x14000451e  mov     [rsi], rbx
0x140004521  xor     eax, eax
0x140004523  mov     rbx, [rsp+38h+arg_8]
0x140004528  mov     rbp, [rsp+38h+arg_10]
0x14000452d  add     rsp, 20h
0x140004531  pop     r15
0x140004533  pop     rdi
0x140004534  pop     rsi
0x140004535  retn
0x140004537  lock inc qword ptr [rbx+10h]
0x14000453c  inc     word ptr [rdi+1Ah]
0x140004540  movzx   ecx, word ptr [rdi+18h]
0x140004544  movsx   eax, word ptr [rdi+1Ah]
0x140004548  dec     ecx
0x14000454a  cmp     eax, ecx
0x14000454c  jnz     short loc_14000451E
0x14000454e  mov     rax, [rdi]
0x140004551  cmp     [rax+8], rdi
0x140004555  jnz     short loc_14000457F
0x140004557  mov     rcx, [rdi+8]
0x14000455b  cmp     [rcx], rdi
0x14000455e  jnz     short loc_14000457F
0x140004560  mov     [rcx], rax
0x140004563  xorps   xmm0, xmm0
0x140004566  mov     [rax+8], rcx
0x14000456a  movups  xmmword ptr [rdi], xmm0
0x14000456d  mov     rcx, [rdi+10h]
0x140004571  test    rcx, rcx
0x140004574  jz      short loc_1400045DA
0x140004576  mov     rax, [rdx+8]
0x14000457a  cmp     [rax], rdx
0x14000457d  jz      short loc_1400045CC
0x14000457f  mov     ecx, 3
0x140004584  int     29h; Win8: RtlFailFast(ecx)
0x140004586  mov     eax, [rbx+3Ch]
0x140004589  cmp     [rcx+3Ch], eax
0x14000458c  ja      loc_1400046FC
0x140004592  jb      loc_14000470D
0x140004598  mov     r11, [rbx+18h]
0x14000459c  mov     rbp, [rcx+18h]
0x1400045a0  mov     rax, [r11+10h]
0x1400045a4  mov     r9, [rax]
0x1400045a7  mov     rax, [rbp+10h]
0x1400045ab  cmp     [rax], r9
0x1400045ae  jb      loc_14000450F
0x1400045b4  ja      loc_140004509
0x1400045ba  mov     rax, [r11]
0x1400045bd  cmp     [rbp+0], rax
0x1400045c1  jbe     loc_14000450F
0x1400045c7  jmp     loc_140004509
0x1400045cc  mov     [rcx], rdx
0x1400045cf  mov     [rcx+8], rax
0x1400045d3  mov     [rax], rcx
0x1400045d6  mov     [rdx+8], rcx
0x1400045da  mov     [rsp+38h+arg_0], r14
0x1400045df  xor     eax, eax
0x1400045e1  xor     r14d, r14d
0x1400045e4  cmp     ax, [rdi+18h]
0x1400045e8  jnb     short loc_140004651
0x1400045ea  mov     rbp, [rdi+r14*8+20h]
0x1400045ef  xor     dl, dl
0x1400045f1  lock inc qword ptr [rbp+10h]
0x1400045f6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400045fd  lock xadd [rbp+10h], rcx
0x140004603  sub     rcx, 2
0x140004607  mov     rax, rcx
0x14000460a  shr     rax, 20h
0x14000460e  cmp     ecx, eax
0x140004610  jz      loc_1400046A2
0x140004616  mov     rax, [rbp+18h]
0x14000461a  test    dword ptr [rax+28h], 4000h
0x140004621  jz      short loc_14000462B
0x140004623  test    dl, dl
0x140004625  jnz     loc_1400046C3
0x14000462b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004632  lock xadd [rbp+10h], rax
0x140004638  cmp     rax, r15
0x14000463b  jnz     short loc_140004645
0x14000463d  mov     rcx, rbp; P
0x140004640  call    FreeWFPFilter
0x140004645  movzx   eax, word ptr [rdi+18h]
0x140004649  inc     r14d
0x14000464c  cmp     r14d, eax
0x14000464f  jb      short loc_1400045EA
0x140004651  mov     eax, [rdi+1Ch]
0x140004654  mov     r14, [rsp+38h+arg_0]
0x140004659  test    r15b, al
0x14000465c  jnz     loc_14000451E
0x140004662  mov     rcx, [rdi+58h]; P
0x140004666  test    rcx, rcx
0x140004669  jz      short loc_140004687
0x14000466b  xor     edx, edx; Tag
0x14000466d  call    cs:__imp_ExFreePoolWithTag
0x140004674  nop     dword ptr [rax+rax+00h]
0x140004679  mov     rax, 0BADBADFABADBADFAh
0x140004683  mov     [rdi+58h], rax
0x140004687  mov     rcx, cs:gWfpGlobal; Lookaside
0x14000468e  mov     rdx, rdi; Entry
0x140004691  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004698  nop     dword ptr [rax+rax+00h]
0x14000469d  jmp     loc_14000451E
0x1400046a2  prefetchw byte ptr [rbp+34h]
0x1400046a6  mov     eax, [rbp+34h]
0x1400046a9  mov     ecx, eax
0x1400046ab  or      ecx, 10h
0x1400046ae  lock cmpxchg [rbp+34h], ecx
0x1400046b3  jnz     short loc_1400046A9
0x1400046b5  test    al, 10h
0x1400046b7  movzx   edx, dl
0x1400046ba  cmovz   edx, r15d
0x1400046be  jmp     loc_140004616
0x1400046c3  call    cs:__imp_KeGetCurrentIrql
0x1400046ca  nop     dword ptr [rax+rax+00h]
0x1400046cf  test    al, al
0x1400046d1  jnz     short loc_1400046E0
0x1400046d3  mov     rcx, rbp
0x1400046d6  call    FeNotifyIntFilterDelete
0x1400046db  jmp     loc_14000462B
0x1400046e0  mov     rcx, cs:gWfpGlobal
0x1400046e7  lea     rdx, [rbp+28h]
0x1400046eb  add     rcx, 538h; Context
0x1400046f2  call    NetioInsertWorkQueue
0x1400046f7  jmp     loc_140004645
0x1400046fc  mov     eax, r15d
0x1400046ff  cmp     eax, r15d
0x140004702  jnz     loc_14000450F
0x140004708  jmp     loc_140004509
0x14000470d  mov     eax, 0FFFFFFFFh
0x140004712  jmp     short loc_1400046FF
```
