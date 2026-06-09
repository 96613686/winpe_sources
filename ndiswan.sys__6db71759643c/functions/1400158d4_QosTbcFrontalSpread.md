# QosTbcFrontalSpread

- ea: `0x1400158d4`
- end: `0x140015a7f`
- name: `QosTbcFrontalSpread`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400097f8`

## callees

- `0x140014cf0`
- `0x1400158d4`

## pseudocode

```c
void __fastcall QosTbcFrontalSpread(
        unsigned __int64 a1,
        unsigned __int64 a2,
        int a3,
        unsigned int a4,
        unsigned __int64 *a5,
        _DWORD *a6,
        __int64 a7,
        unsigned int a8,
        _DWORD *a9)
{
  unsigned __int64 *v9; // r15
  int v10; // r10d
  _DWORD *v11; // r8
  unsigned __int64 v12; // rdi
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  _DWORD *v17; // r14
  int v18; // r9d
  __int64 v19; // r13
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rbp
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  bool v27; // cf
  int v28; // [rsp+70h] [rbp+8h]

  v9 = a5;
  v10 = a3;
  v11 = a6;
  v12 = a2;
  v14 = a4;
  v15 = *a5;
  if ( *a5 < a1 )
  {
    v16 = a4 + v15;
    *a6 = v10;
    v15 = a1;
    if ( v16 > a1 )
      v15 = v16;
    *v9 = v15;
  }
  if ( a2 <= v15 )
    v12 = v15
        + (unsigned int)QosgBoundaryPeriod
        - (v15 + (unsigned int)QosgBoundaryPeriod - a2) % (unsigned int)QosgBoundaryPeriod;
  v17 = a9;
  v18 = 0;
  LODWORD(a5) = 0;
  *a9 = 0;
  if ( a8 )
  {
    LODWORD(a9) = 0;
    v19 = 0;
    v20 = (v12 - v15) / v14;
    v21 = v15;
    v28 = v20;
    do
    {
      v22 = a7;
      v23 = 32 * v19;
      if ( *(_QWORD *)(a7 + 32 * v19 + 16) >= v12 )
      {
        if ( v21 >= v12 )
        {
          v15 = v21;
        }
        else
        {
          v15 = v14 + v21;
          *v11 = v10;
          if ( v14 + v21 <= v12 )
            v15 = v12;
          *v9 = v15;
        }
        v12 += (unsigned int)QosgBoundaryPeriod;
        LODWORD(a5) = v18;
        v20 = (v12 - v15) / v14;
        v28 = v20;
      }
      v24 = a4 * (unsigned int)QosAssignSlot(*(_DWORD *)(v22 + v23 + 28), v10, v20, 0, (__int64)&a5, (__int64)v11);
      v25 = a7;
      v26 = v15 + v24;
      v21 = v15 + (unsigned int)a5 * a4;
      *v9 = v21;
      *(_QWORD *)(v25 + v23 + 16) = v26;
      if ( v26 == a1 )
        ++*v17;
      ++v19;
      v10 = a3;
      v27 = (int)a9 + 1 < a8;
      v11 = a6;
      LODWORD(a9) = (_DWORD)a9 + 1;
      LODWORD(v20) = v28;
    }
    while ( v27 );
  }
}

```

## disassembly

```asm
0x1400158d4  mov     [rsp+arg_8], rbx
0x1400158d9  mov     [rsp+arg_18], r9d
0x1400158de  mov     [rsp+arg_10], r8d
0x1400158e3  push    rbp
0x1400158e4  push    rsi
0x1400158e5  push    rdi
0x1400158e6  push    r12
0x1400158e8  push    r13
0x1400158ea  push    r14
0x1400158ec  push    r15
0x1400158ee  sub     rsp, 30h
0x1400158f2  mov     r15, [rsp+68h+arg_20]
0x1400158fa  mov     r10d, r8d
0x1400158fd  mov     r8, [rsp+68h+arg_28]
0x140015905  mov     rdi, rdx
0x140015908  mov     rsi, rcx
0x14001590b  mov     r12d, r9d
0x14001590e  mov     rbx, [r15]
0x140015911  cmp     rbx, rcx
0x140015914  jnb     short loc_14001592A
0x140015916  lea     rax, [r12+rbx]
0x14001591a  mov     [r8], r10d
0x14001591d  cmp     rax, rcx
0x140015920  mov     rbx, rcx
0x140015923  cmova   rbx, rax
0x140015927  mov     [r15], rbx
0x14001592a  cmp     rdx, rbx
0x14001592d  ja      short loc_14001594A
0x14001592f  mov     ecx, cs:QosgBoundaryPeriod
0x140015935  mov     eax, ecx
0x140015937  mov     edi, ecx
0x140015939  sub     rax, rdx
0x14001593c  xor     edx, edx
0x14001593e  add     rax, rbx
0x140015941  div     rcx
0x140015944  sub     rdi, rdx
0x140015947  add     rdi, rbx
0x14001594a  mov     r14, [rsp+68h+arg_40]
0x140015952  xor     r9d, r9d
0x140015955  mov     dword ptr [rsp+68h+arg_20], r9d
0x14001595d  mov     [r14], r9d
0x140015960  cmp     [rsp+68h+arg_38], r9d
0x140015968  jbe     loc_140015A69
0x14001596e  xor     edx, edx
0x140015970  mov     dword ptr [rsp+68h+arg_40], r9d
0x140015978  mov     rax, rdi
0x14001597b  mov     r13d, r9d
0x14001597e  sub     rax, rbx
0x140015981  div     r12
0x140015984  mov     rdx, rbx
0x140015987  mov     [rsp+68h+arg_0], rax
0x14001598c  mov     rcx, [rsp+68h+arg_30]
0x140015994  mov     rbp, r13
0x140015997  shl     rbp, 5
0x14001599b  cmp     [rcx+rbp+10h], rdi
0x1400159a0  jb      short loc_1400159DE
0x1400159a2  cmp     rdx, rdi
0x1400159a5  jnb     short loc_1400159BA
0x1400159a7  lea     rbx, [r12+rdx]
0x1400159ab  mov     [r8], r10d
0x1400159ae  cmp     rbx, rdi
0x1400159b1  cmovbe  rbx, rdi
0x1400159b5  mov     [r15], rbx
0x1400159b8  jmp     short loc_1400159BD
0x1400159ba  mov     rbx, rdx
0x1400159bd  mov     eax, cs:QosgBoundaryPeriod
0x1400159c3  xor     edx, edx
0x1400159c5  add     rdi, rax
0x1400159c8  mov     dword ptr [rsp+68h+arg_20], r9d
0x1400159d0  mov     rax, rdi
0x1400159d3  sub     rax, rbx
0x1400159d6  div     r12
0x1400159d9  mov     [rsp+68h+arg_0], rax
0x1400159de  mov     ecx, [rcx+rbp+1Ch]
0x1400159e2  lea     rdx, [rsp+68h+arg_20]
0x1400159ea  mov     [rsp+68h+var_40], r8
0x1400159ef  xor     r9d, r9d
0x1400159f2  mov     [rsp+68h+var_48], rdx
0x1400159f7  mov     r8d, eax
0x1400159fa  mov     edx, r10d
0x1400159fd  call    QosAssignSlot
0x140015a02  mov     edx, [rsp+68h+arg_18]
0x140015a09  imul    eax, edx
0x140015a0c  imul    edx, dword ptr [rsp+68h+arg_20]
0x140015a14  mov     ecx, eax
0x140015a16  mov     rax, [rsp+68h+arg_30]
0x140015a1e  add     rcx, rbx
0x140015a21  add     rdx, rbx
0x140015a24  mov     [r15], rdx
0x140015a27  mov     [rax+rbp+10h], rcx
0x140015a2c  cmp     rcx, rsi
0x140015a2f  jnz     short loc_140015A34
0x140015a31  inc     dword ptr [r14]
0x140015a34  mov     eax, dword ptr [rsp+68h+arg_40]
0x140015a3b  inc     r13
0x140015a3e  mov     r10d, [rsp+68h+arg_10]
0x140015a46  inc     eax
0x140015a48  cmp     eax, [rsp+68h+arg_38]
0x140015a4f  mov     r8, [rsp+68h+arg_28]
0x140015a57  mov     dword ptr [rsp+68h+arg_40], eax
0x140015a5e  mov     rax, [rsp+68h+arg_0]
0x140015a63  jb      loc_14001598C
0x140015a69  mov     rbx, [rsp+68h+arg_8]
0x140015a6e  add     rsp, 30h
0x140015a72  pop     r15
0x140015a74  pop     r14
0x140015a76  pop     r13
0x140015a78  pop     r12
0x140015a7a  pop     rdi
0x140015a7b  pop     rsi
0x140015a7c  pop     rbp
0x140015a7d  retn
```
