# GenADTG::SaveTableDescriptor(tagTABLELIST *)

- ea: `0x180009498`
- end: `0x180009670`
- name: `?SaveTableDescriptor@GenADTG@@QEAAXPEAUtagTABLELIST@@@Z`
- size: `472`
- prototype: `void __fastcall(GenADTG *__hidden this, struct tagTABLELIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009394`

## callees

- `0x180001db8`
- `0x180003c38`
- `0x180004384`
- `0x180005bfc`
- `0x18000943c`
- `0x180009498`
- `0x180009678`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GenADTG::SaveTableDescriptor(GenADTG *this, struct tagTABLELIST *a2)
{
  unsigned __int16 v4; // si
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v6; // r13
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int16 v9; // bp
  __int64 v10; // rax
  int v11; // r11d
  int v12; // r12d
  unsigned __int16 v13; // dx
  unsigned __int16 Type; // ax
  __int16 v15; // r11
  __int16 v16; // r10
  BOOL v17; // ecx
  __int16 v18; // ax
  unsigned __int8 v19[8]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v20; // [rsp+28h] [rbp-40h]
  unsigned __int8 v21; // [rsp+78h] [rbp+10h] BYREF
  __int16 v22; // [rsp+80h] [rbp+18h] BYREF
  __int16 v23; // [rsp+88h] [rbp+20h] BYREF

  v21 = 5;
  v4 = 0;
  *(_WORD *)v19 = 0;
  v5 = GenADTG::BuildFullTableName(this, a2);
  v20 = v5;
  v6 = (unsigned __int16 *)((char *)a2 + 26);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v5[v8] );
  do
    ++v7;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v7) );
  v23 = 2 * (*v6 + v8 + 6 + v7);
  GenADTG::SaveToBuffer(this, &v21, 1u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v23, 2u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)a2 + 40, 2u);
  GenADTG::SaveString(this, v5);
  GenADTG::SaveString(this, *(const unsigned __int16 **)a2);
  GenADTG::SaveToBuffer(this, v19, 2u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)a2 + 24, 2u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)a2 + 26, 2u);
  v9 = 0;
  if ( *v6 )
  {
    do
    {
      v10 = *((_QWORD *)a2 + 4);
      v11 = *(unsigned __int16 *)(v10 + 2LL * v9);
      v22 = *(_WORD *)(v10 + 2LL * v9);
      if ( *((_DWORD *)this + 47) && *((_DWORD *)this + 50) )
      {
        v12 = v11 - 1;
        if ( v11 - 1 > 0 )
        {
          do
          {
            CMetaData::mdGetFlags((GenADTG *)((char *)this + 128), v4);
            Type = CMetaData::mdGetType((GenADTG *)((char *)this + 128), v13);
            v17 = (v16 & 0x2000) != 0 || Type == 136;
            v18 = v15 - 1;
            if ( !v17 )
              v18 = v15;
            LOWORD(v11) = v18;
            ++v4;
          }
          while ( v4 < v12 );
          v6 = (unsigned __int16 *)((char *)a2 + 26);
          v4 = 0;
        }
        v22 = v11;
      }
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v22, 2u);
      ++v9;
    }
    while ( v9 < *v6 );
    v5 = v20;
  }
  operator delete((unsigned __int8 *)v5);
}

```

## disassembly

```asm
0x180009498  mov     [rsp+arg_0], rbx
0x18000949d  push    rbp
0x18000949e  push    rsi
0x18000949f  push    rdi
0x1800094a0  push    r12
0x1800094a2  push    r13
0x1800094a4  push    r14
0x1800094a6  push    r15
0x1800094a8  sub     rsp, 30h
0x1800094ac  mov     r14, rdx
0x1800094af  mov     rdi, rcx
0x1800094b2  mov     [rsp+68h+arg_8], 5
0x1800094b7  xor     esi, esi
0x1800094b9  mov     word ptr [rsp+68h+var_48], si
0x1800094be  call    ?BuildFullTableName@GenADTG@@AEAAPEAGPEAUtagTABLELIST@@@Z; GenADTG::BuildFullTableName(tagTABLELIST *)
0x1800094c3  mov     rbx, rax
0x1800094c6  mov     [rsp+68h+var_40], rax
0x1800094cb  lea     r13, [r14+1Ah]
0x1800094cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800094d3  mov     rcx, rax
0x1800094d6  inc     rcx
0x1800094d9  cmp     [rbx+rcx*2], si
0x1800094dd  jnz     short loc_1800094D6
0x1800094df  mov     rdx, [r14]
0x1800094e2  inc     rax
0x1800094e5  cmp     [rdx+rax*2], si
0x1800094e9  jnz     short loc_1800094E2
0x1800094eb  add     cx, 6
0x1800094ef  add     ax, cx
0x1800094f2  add     ax, [r13+0]
0x1800094f7  add     ax, ax
0x1800094fa  mov     [rsp+68h+arg_18], ax
0x180009502  mov     r8d, 1; unsigned int
0x180009508  lea     rdx, [rsp+68h+arg_8]; unsigned __int8 *
0x18000950d  mov     rcx, rdi; this
0x180009510  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180009515  mov     ebp, 2
0x18000951a  mov     r8d, ebp; unsigned int
0x18000951d  lea     rdx, [rsp+68h+arg_18]; unsigned __int8 *
0x180009525  mov     rcx, rdi; this
0x180009528  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000952d  lea     rdx, [r14+28h]; unsigned __int8 *
0x180009531  mov     r8d, ebp; unsigned int
0x180009534  mov     rcx, rdi; this
0x180009537  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000953c  mov     rdx, rbx; unsigned __int16 *
0x18000953f  mov     rcx, rdi; this
0x180009542  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180009547  mov     rdx, [r14]; unsigned __int16 *
0x18000954a  mov     rcx, rdi; this
0x18000954d  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180009552  mov     r8d, ebp; unsigned int
0x180009555  lea     rdx, [rsp+68h+var_48]; unsigned __int8 *
0x18000955a  mov     rcx, rdi; this
0x18000955d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180009562  lea     rdx, [r14+18h]; unsigned __int8 *
0x180009566  mov     r8d, ebp; unsigned int
0x180009569  mov     rcx, rdi; this
0x18000956c  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180009571  mov     r8d, ebp; unsigned int
0x180009574  mov     rdx, r13; unsigned __int8 *
0x180009577  mov     rcx, rdi; this
0x18000957a  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000957f  mov     ebp, esi
0x180009581  cmp     si, [r13+0]
0x180009586  jnb     loc_180009652
0x18000958c  lea     r15, [rdi+80h]
0x180009593  mov     ebx, 1
0x180009598  movzx   ecx, bp
0x18000959b  mov     rax, [r14+20h]
0x18000959f  movzx   r11d, word ptr [rax+rcx*2]
0x1800095a4  mov     [rsp+68h+arg_10], r11w
0x1800095ad  cmp     [r15+3Ch], esi
0x1800095b1  jz      short loc_180009629
0x1800095b3  cmp     [rdi+0C8h], esi
0x1800095b9  jz      short loc_180009629
0x1800095bb  lea     r12d, [r11-1]
0x1800095bf  test    r12d, r12d
0x1800095c2  jle     short loc_180009620
0x1800095c4  mov     r13d, 1
0x1800095ca  movzx   edx, si; unsigned __int16
0x1800095cd  mov     rcx, r15; this
0x1800095d0  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x1800095d5  mov     r10d, eax
0x1800095d8  mov     rcx, r15; this
0x1800095db  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x1800095e0  bt      r10d, 0Dh
0x1800095e5  jb      short loc_1800095F5
0x1800095e7  mov     ecx, 88h
0x1800095ec  cmp     ax, cx
0x1800095ef  jz      short loc_1800095F5
0x1800095f1  xor     ecx, ecx
0x1800095f3  jmp     short loc_1800095F8
0x1800095f5  mov     ecx, r13d
0x1800095f8  movzx   eax, r11w
0x1800095fc  sub     ax, r13w
0x180009600  test    ecx, ecx
0x180009602  cmovz   ax, r11w
0x180009607  movzx   r11d, ax
0x18000960b  add     si, r13w
0x18000960f  movzx   eax, si
0x180009612  cmp     eax, r12d
0x180009615  jl      short loc_1800095CA
0x180009617  lea     r13, [r14+1Ah]
0x18000961b  xor     esi, esi
0x18000961d  lea     ebx, [rsi+1]
0x180009620  mov     [rsp+68h+arg_10], r11w
0x180009629  mov     r8d, 2; unsigned int
0x18000962f  lea     rdx, [rsp+68h+arg_10]; unsigned __int8 *
0x180009637  mov     rcx, rdi; this
0x18000963a  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x18000963f  add     bp, bx
0x180009642  cmp     bp, [r13+0]
0x180009647  jb      loc_180009598
0x18000964d  mov     rbx, [rsp+68h+var_40]
0x180009652  mov     rcx, rbx; void *
0x180009655  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000965a  mov     rbx, [rsp+68h+arg_0]
0x18000965f  add     rsp, 30h
0x180009663  pop     r15
0x180009665  pop     r14
0x180009667  pop     r13
0x180009669  pop     r12
0x18000966b  pop     rdi
0x18000966c  pop     rsi
0x18000966d  pop     rbp
0x18000966e  retn
```
