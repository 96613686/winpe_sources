# std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>)

- ea: `0x18001a0ac`
- end: `0x18001a186`
- name: `?erase@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z`
- size: `218`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001884c`
- `0x18001e041`

## callees

- `0x1800014d0`
- `0x1800184f8`
- `0x18001a0ac`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        int *a3)
{
  int v5; // ecx
  int v7; // edx
  unsigned __int64 v8; // r8
  int v9; // ecx
  int v10; // eax
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rsi

  v5 = 16807 * a3[4];
  v7 = (unsigned __int64)(2202930015LL * a3[4]) >> 32;
  v8 = a1[8];
  v9 = v5 - 0x7FFFFFFF * (((unsigned int)v7 >> 31) + (v7 >> 16));
  v10 = v9 + 0x7FFFFFFF;
  if ( v9 >= 0 )
    v10 = v9;
  v11 = v8 & v10;
  if ( a1[9] <= v11 )
    v11 = v11 - (v8 >> 1) - 1;
  v12 = a1[4];
  v13 = 2 * v11;
  if ( *(int **)(v12 + 8 * v13 + 8) == a3 )
  {
    if ( *(int **)(v12 + 8 * v13) == a3 )
    {
      *(_QWORD *)(v12 + 8 * v13) = a1[1];
      v12 = a1[4];
      v14 = a1[1];
    }
    else
    {
      v14 = *((_QWORD *)a3 + 1);
    }
    *(_QWORD *)(v12 + 8 * v13 + 8) = v14;
  }
  else if ( *(int **)(v12 + 8 * v13) == a3 )
  {
    *(_QWORD *)(v12 + 8 * v13) = *(_QWORD *)a3;
  }
  v15 = *(_QWORD *)a3;
  if ( a3 != (int *)a1[1] )
  {
    **((_QWORD **)a3 + 1) = v15;
    *(_QWORD *)(*(_QWORD *)a3 + 8LL) = *((_QWORD *)a3 + 1);
    VisibleDock::~VisibleDock((VisibleDock *)(a3 + 8));
    operator delete(a3);
    --a1[2];
  }
  *a2 = v15;
  return a2;
}

```

## disassembly

```asm
0x18001a0ac  push    rbx
0x18001a0ae  push    rsi
0x18001a0af  push    rdi
0x18001a0b0  push    r14
0x18001a0b2  sub     rsp, 28h
0x18001a0b6  mov     r14, rdx
0x18001a0b9  mov     rdi, rcx
0x18001a0bc  imul    ecx, [r8+10h], 41A7h
0x18001a0c4  mov     eax, 834E0B5Fh
0x18001a0c9  imul    dword ptr [r8+10h]
0x18001a0cd  mov     rbx, r8
0x18001a0d0  add     edx, [r8+10h]
0x18001a0d4  mov     r8, [rdi+40h]
0x18001a0d8  sar     edx, 10h
0x18001a0db  mov     eax, edx
0x18001a0dd  shr     eax, 1Fh
0x18001a0e0  add     edx, eax
0x18001a0e2  imul    eax, edx, 7FFFFFFFh
0x18001a0e8  sub     ecx, eax
0x18001a0ea  lea     eax, [rcx+7FFFFFFFh]
0x18001a0f0  cmovns  eax, ecx
0x18001a0f3  movsxd  rdx, eax
0x18001a0f6  and     rdx, r8
0x18001a0f9  cmp     [rdi+48h], rdx
0x18001a0fd  ja      short loc_18001A108
0x18001a0ff  shr     r8, 1
0x18001a102  sub     rdx, r8
0x18001a105  dec     rdx
0x18001a108  mov     rcx, [rdi+20h]
0x18001a10c  add     rdx, rdx
0x18001a10f  cmp     [rcx+rdx*8+8], rbx
0x18001a114  jnz     short loc_18001A139
0x18001a116  cmp     [rcx+rdx*8], rbx
0x18001a11a  jnz     short loc_18001A12E
0x18001a11c  mov     rax, [rdi+8]
0x18001a120  mov     [rcx+rdx*8], rax
0x18001a124  mov     rcx, [rdi+20h]
0x18001a128  mov     rax, [rdi+8]
0x18001a12c  jmp     short loc_18001A132
0x18001a12e  mov     rax, [rbx+8]
0x18001a132  mov     [rcx+rdx*8+8], rax
0x18001a137  jmp     short loc_18001A146
0x18001a139  cmp     [rcx+rdx*8], rbx
0x18001a13d  jnz     short loc_18001A146
0x18001a13f  mov     rax, [rbx]
0x18001a142  mov     [rcx+rdx*8], rax
0x18001a146  mov     rsi, [rbx]
0x18001a149  cmp     rbx, [rdi+8]
0x18001a14d  jz      short loc_18001A176
0x18001a14f  mov     rax, [rbx+8]
0x18001a153  mov     [rax], rsi
0x18001a156  mov     rcx, [rbx]
0x18001a159  mov     rax, [rbx+8]
0x18001a15d  mov     [rcx+8], rax
0x18001a161  lea     rcx, [rbx+20h]; this
0x18001a165  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x18001a16a  mov     rcx, rbx; Block
0x18001a16d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a172  dec     qword ptr [rdi+10h]
0x18001a176  mov     [r14], rsi
0x18001a179  mov     rax, r14
0x18001a17c  add     rsp, 28h
0x18001a180  pop     r14
0x18001a182  pop     rdi
0x18001a183  pop     rsi
0x18001a184  pop     rbx
0x18001a185  retn
```
