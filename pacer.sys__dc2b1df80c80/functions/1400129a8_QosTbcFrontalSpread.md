# QosTbcFrontalSpread

- ea: `0x1400129a8`
- end: `0x140012b53`
- name: `QosTbcFrontalSpread`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007260`

## callees

- `0x14001214c`
- `0x1400129a8`

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
0x1400129a8  mov     [rsp+arg_8], rbx
0x1400129ad  mov     [rsp+arg_18], r9d
0x1400129b2  mov     [rsp+arg_10], r8d
0x1400129b7  push    rbp
0x1400129b8  push    rsi
0x1400129b9  push    rdi
0x1400129ba  push    r12
0x1400129bc  push    r13
0x1400129be  push    r14
0x1400129c0  push    r15
0x1400129c2  sub     rsp, 30h
0x1400129c6  mov     r15, [rsp+68h+arg_20]
0x1400129ce  mov     r10d, r8d
0x1400129d1  mov     r8, [rsp+68h+arg_28]
0x1400129d9  mov     rdi, rdx
0x1400129dc  mov     rsi, rcx
0x1400129df  mov     r12d, r9d
0x1400129e2  mov     rbx, [r15]
0x1400129e5  cmp     rbx, rcx
0x1400129e8  jnb     short loc_1400129FE
0x1400129ea  lea     rax, [r12+rbx]
0x1400129ee  mov     [r8], r10d
0x1400129f1  cmp     rax, rcx
0x1400129f4  mov     rbx, rcx
0x1400129f7  cmova   rbx, rax
0x1400129fb  mov     [r15], rbx
0x1400129fe  cmp     rdx, rbx
0x140012a01  ja      short loc_140012A1E
0x140012a03  mov     ecx, cs:QosgBoundaryPeriod
0x140012a09  mov     eax, ecx
0x140012a0b  mov     edi, ecx
0x140012a0d  sub     rax, rdx
0x140012a10  xor     edx, edx
0x140012a12  add     rax, rbx
0x140012a15  div     rcx
0x140012a18  sub     rdi, rdx
0x140012a1b  add     rdi, rbx
0x140012a1e  mov     r14, [rsp+68h+arg_40]
0x140012a26  xor     r9d, r9d
0x140012a29  mov     dword ptr [rsp+68h+arg_20], r9d
0x140012a31  mov     [r14], r9d
0x140012a34  cmp     [rsp+68h+arg_38], r9d
0x140012a3c  jbe     loc_140012B3D
0x140012a42  xor     edx, edx
0x140012a44  mov     dword ptr [rsp+68h+arg_40], r9d
0x140012a4c  mov     rax, rdi
0x140012a4f  mov     r13d, r9d
0x140012a52  sub     rax, rbx
0x140012a55  div     r12
0x140012a58  mov     rdx, rbx
0x140012a5b  mov     [rsp+68h+arg_0], rax
0x140012a60  mov     rcx, [rsp+68h+arg_30]
0x140012a68  mov     rbp, r13
0x140012a6b  shl     rbp, 5
0x140012a6f  cmp     [rcx+rbp+10h], rdi
0x140012a74  jb      short loc_140012AB2
0x140012a76  cmp     rdx, rdi
0x140012a79  jnb     short loc_140012A8E
0x140012a7b  lea     rbx, [r12+rdx]
0x140012a7f  mov     [r8], r10d
0x140012a82  cmp     rbx, rdi
0x140012a85  cmovbe  rbx, rdi
0x140012a89  mov     [r15], rbx
0x140012a8c  jmp     short loc_140012A91
0x140012a8e  mov     rbx, rdx
0x140012a91  mov     eax, cs:QosgBoundaryPeriod
0x140012a97  xor     edx, edx
0x140012a99  add     rdi, rax
0x140012a9c  mov     dword ptr [rsp+68h+arg_20], r9d
0x140012aa4  mov     rax, rdi
0x140012aa7  sub     rax, rbx
0x140012aaa  div     r12
0x140012aad  mov     [rsp+68h+arg_0], rax
0x140012ab2  mov     ecx, [rcx+rbp+1Ch]
0x140012ab6  lea     rdx, [rsp+68h+arg_20]
0x140012abe  mov     [rsp+68h+var_40], r8
0x140012ac3  xor     r9d, r9d
0x140012ac6  mov     [rsp+68h+var_48], rdx
0x140012acb  mov     r8d, eax
0x140012ace  mov     edx, r10d
0x140012ad1  call    QosAssignSlot
0x140012ad6  mov     edx, [rsp+68h+arg_18]
0x140012add  imul    eax, edx
0x140012ae0  imul    edx, dword ptr [rsp+68h+arg_20]
0x140012ae8  mov     ecx, eax
0x140012aea  mov     rax, [rsp+68h+arg_30]
0x140012af2  add     rcx, rbx
0x140012af5  add     rdx, rbx
0x140012af8  mov     [r15], rdx
0x140012afb  mov     [rax+rbp+10h], rcx
0x140012b00  cmp     rcx, rsi
0x140012b03  jnz     short loc_140012B08
0x140012b05  inc     dword ptr [r14]
0x140012b08  mov     eax, dword ptr [rsp+68h+arg_40]
0x140012b0f  inc     r13
0x140012b12  mov     r10d, [rsp+68h+arg_10]
0x140012b1a  inc     eax
0x140012b1c  cmp     eax, [rsp+68h+arg_38]
0x140012b23  mov     r8, [rsp+68h+arg_28]
0x140012b2b  mov     dword ptr [rsp+68h+arg_40], eax
0x140012b32  mov     rax, [rsp+68h+arg_0]
0x140012b37  jb      loc_140012A60
0x140012b3d  mov     rbx, [rsp+68h+arg_8]
0x140012b42  add     rsp, 30h
0x140012b46  pop     r15
0x140012b48  pop     r14
0x140012b4a  pop     r13
0x140012b4c  pop     r12
0x140012b4e  pop     rdi
0x140012b4f  pop     rsi
0x140012b50  pop     rbp
0x140012b51  retn
```
