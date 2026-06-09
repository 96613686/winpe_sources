# CalculateSizeForThreads(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_MINIDUMP_STREAM_INFO *)

- ea: `0x180005700`
- end: `0x1800058ca`
- name: `?CalculateSizeForThreads@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_MINIDUMP_STREAM_INFO@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _MINIDUMP_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058d0`

## callees

- `0x180005700`
- `0x18001766c`
- `0x18001f334`

## pseudocode

```c
__int64 __fastcall CalculateSizeForThreads(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _MINIDUMP_STREAM_INFO *a3)
{
  int v6; // edx
  int v7; // ecx
  char *v8; // rax
  int v9; // r14d
  char *v10; // r12
  int v11; // ebp
  int v12; // esi
  int v13; // r8d
  char *v14; // rdi
  int v15; // eax
  int v16; // eax
  unsigned int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // ebp
  int v22; // [rsp+78h] [rbp+10h]
  int v23; // [rsp+80h] [rbp+18h]
  int v24; // [rsp+88h] [rbp+20h]

  v24 = 0;
  v6 = 0;
  v7 = 0;
  v23 = 0;
  v8 = (char *)a2 + 104;
  v22 = 0;
  *((_DWORD *)a3 + 14) = 48;
  v9 = 0;
  v10 = (char *)*((_QWORD *)a2 + 13);
  v11 = 0;
  v12 = 0;
  v13 = 0;
  while ( v10 != v8 )
  {
    v14 = v10 - 184;
    v10 = *(char **)v10;
    v15 = *((_DWORD *)v14 + 44);
    if ( (v15 & 1) != 0 )
    {
      ++v11;
      if ( (v15 & 4) != 0 )
        v23 = *((_DWORD *)a1 + 35) + v6;
      if ( (v15 & 8) != 0 )
      {
        v16 = *((_DWORD *)v14 + 40);
        if ( v16 )
        {
          v22 = v7 + 1;
          v24 = v16 + v13;
        }
        *((_DWORD *)a3 + 14) = 64;
      }
      if ( (v14[176] & 0x10) != 0 )
      {
        v17 = *((_DWORD *)a1 + 43);
        if ( v17 )
          GenAddMemoryBlock(a1, (__int64)a2, 6u, 0, *((_QWORD *)v14 + 15) - ((unsigned __int64)v17 >> 1), v17);
      }
      if ( ((v14[176] & 0x20) != 0 || *((_DWORD *)a1 + 34) && (*((_DWORD *)a1 + 14) & 0x4000002) == 0)
        && *((_DWORD *)v14 + 26) )
      {
        GenAddTebMemory(a1, a2, (struct _INTERNAL_THREAD *)v14);
      }
      if ( (v14[176] & 0x40) != 0 )
        ++v12;
      v18 = *((_QWORD *)v14 + 26);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(v18 + 2 * v19) );
        *((_DWORD *)a3 + 33) += 2 * v19 + 6;
        ++v9;
      }
      v13 = v24;
      v6 = v23;
      v7 = v22;
    }
    v8 = (char *)a2 + 104;
  }
  *((_DWORD *)a2 + 19) = v11;
  *((_DWORD *)a2 + 20) = v12;
  if ( v9 )
    *((_DWORD *)a3 + 58) = 12 * v9 + 4;
  v20 = *((_DWORD *)a3 + 14) * v11;
  *((_DWORD *)a3 + 36) += v6;
  *((_DWORD *)a3 + 30) += v13;
  *((_DWORD *)a3 + 27) += 16 * v7;
  *((_DWORD *)a3 + 12) += v20 + 4;
  *((_DWORD *)a3 + 16) = (v12 << 6) + 12;
  return 0;
}

```

## disassembly

```asm
0x180005700  mov     [rsp+arg_0], rbx
0x180005705  push    rbp
0x180005706  push    rsi
0x180005707  push    rdi
0x180005708  push    r12
0x18000570a  push    r13
0x18000570c  push    r14
0x18000570e  push    r15
0x180005710  sub     rsp, 30h
0x180005714  xor     r9d, r9d
0x180005717  mov     r13, rdx
0x18000571a  mov     rbx, r8
0x18000571d  mov     [rsp+68h+arg_18], r9d
0x180005725  mov     r15, rcx
0x180005728  mov     edx, r9d
0x18000572b  mov     ecx, r9d
0x18000572e  mov     [rsp+68h+arg_10], edx
0x180005735  lea     rax, [r13+68h]
0x180005739  mov     [rsp+68h+arg_8], ecx
0x18000573d  mov     dword ptr [rbx+38h], 30h ; '0'
0x180005744  mov     r14d, r9d
0x180005747  mov     r12, [rax]
0x18000574a  mov     ebp, r9d
0x18000574d  mov     esi, r9d
0x180005750  mov     r8d, r9d
0x180005753  jmp     loc_180005869
0x180005758  lea     rdi, [r12-0B8h]
0x180005760  mov     r12, [r12]
0x180005764  mov     eax, [rdi+0B0h]
0x18000576a  test    al, 1
0x18000576c  jz      loc_180005865
0x180005772  inc     ebp
0x180005774  test    al, 4
0x180005776  jz      short loc_180005786
0x180005778  add     edx, [r15+8Ch]
0x18000577f  mov     [rsp+68h+arg_10], edx
0x180005786  test    al, 8
0x180005788  jz      short loc_1800057AC
0x18000578a  mov     eax, [rdi+0A0h]
0x180005790  test    eax, eax
0x180005792  jz      short loc_1800057A5
0x180005794  inc     ecx
0x180005796  add     r8d, eax
0x180005799  mov     [rsp+68h+arg_8], ecx
0x18000579d  mov     [rsp+68h+arg_18], r8d
0x1800057a5  mov     dword ptr [rbx+38h], 40h ; '@'
0x1800057ac  test    byte ptr [rdi+0B0h], 10h
0x1800057b3  jz      short loc_1800057EA
0x1800057b5  mov     edx, [r15+0ACh]
0x1800057bc  test    edx, edx
0x1800057be  jz      short loc_1800057EA
0x1800057c0  mov     rcx, [rdi+78h]
0x1800057c4  mov     eax, edx
0x1800057c6  mov     [rsp+68h+var_40], edx
0x1800057ca  xor     r9d, r9d
0x1800057cd  shr     rax, 1
0x1800057d0  mov     rdx, r13
0x1800057d3  sub     rcx, rax
0x1800057d6  mov     [rsp+68h+var_48], rcx
0x1800057db  mov     rcx, r15
0x1800057de  lea     r8d, [r9+6]
0x1800057e2  call    ?GenAddMemoryBlock@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@W4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@_KK@Z; GenAddMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,unsigned __int64,ulong)
0x1800057e7  xor     r9d, r9d
0x1800057ea  test    byte ptr [rdi+0B0h], 20h
0x1800057f1  jnz     short loc_180005806
0x1800057f3  cmp     [r15+88h], r9d
0x1800057fa  jz      short loc_18000581D
0x1800057fc  test    dword ptr [r15+38h], 4000002h
0x180005804  jnz     short loc_18000581D
0x180005806  cmp     [rdi+68h], r9d
0x18000580a  jz      short loc_18000581D
0x18000580c  mov     r8, rdi; struct _INTERNAL_THREAD *
0x18000580f  mov     rdx, r13; struct _INTERNAL_PROCESS *
0x180005812  mov     rcx, r15; struct _MINIDUMP_STATE *
0x180005815  call    ?GenAddTebMemory@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@@Z; GenAddTebMemory(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *)
0x18000581a  xor     r9d, r9d
0x18000581d  test    byte ptr [rdi+0B0h], 40h
0x180005824  jz      short loc_180005828
0x180005826  inc     esi
0x180005828  mov     rcx, [rdi+0D0h]
0x18000582f  test    rcx, rcx
0x180005832  jz      short loc_180005852
0x180005834  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005838  inc     rax
0x18000583b  cmp     [rcx+rax*2], r9w
0x180005840  jnz     short loc_180005838
0x180005842  lea     eax, ds:6[rax*2]
0x180005849  add     [rbx+84h], eax
0x18000584f  inc     r14d
0x180005852  mov     r8d, [rsp+68h+arg_18]
0x18000585a  mov     edx, [rsp+68h+arg_10]
0x180005861  mov     ecx, [rsp+68h+arg_8]
0x180005865  lea     rax, [r13+68h]
0x180005869  cmp     r12, rax
0x18000586c  jnz     loc_180005758
0x180005872  mov     [r13+4Ch], ebp
0x180005876  mov     [r13+50h], esi
0x18000587a  test    r14d, r14d
0x18000587d  jz      short loc_180005890
0x18000587f  lea     eax, [r14+r14*2]
0x180005883  lea     eax, ds:4[rax*4]
0x18000588a  mov     [rbx+0E8h], eax
0x180005890  imul    ebp, [rbx+38h]
0x180005894  add     [rbx+90h], edx
0x18000589a  add     [rbx+78h], r8d
0x18000589e  shl     esi, 6
0x1800058a1  shl     ecx, 4
0x1800058a4  add     esi, 0Ch
0x1800058a7  add     [rbx+6Ch], ecx
0x1800058aa  add     ebp, 4
0x1800058ad  add     [rbx+30h], ebp
0x1800058b0  mov     [rbx+40h], esi
0x1800058b3  xor     eax, eax
0x1800058b5  mov     rbx, [rsp+68h+arg_0]
0x1800058ba  add     rsp, 30h
0x1800058be  pop     r15
0x1800058c0  pop     r14
0x1800058c2  pop     r13
0x1800058c4  pop     r12
0x1800058c6  pop     rdi
0x1800058c7  pop     rsi
0x1800058c8  pop     rbp
0x1800058c9  retn
```
