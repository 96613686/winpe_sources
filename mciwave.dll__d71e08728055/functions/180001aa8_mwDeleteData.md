# mwDeleteData

- ea: `0x180001aa8`
- end: `0x180001db0`
- name: `mwDeleteData`
- size: `776`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005170`

## callees

- `0x180001424`
- `0x180001aa8`
- `0x180001db8`
- `0x180003e60`

## pseudocode

```c
__int64 __fastcall mwDeleteData(__int64 a1)
{
  unsigned int v1; // esi
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 result; // rax
  int *v6; // rdi
  int v7; // ebp
  unsigned int v8; // r9d
  unsigned int v9; // r14d
  int v10; // r15d
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // r9d
  int v16; // r15d
  unsigned int v17; // r10d
  unsigned int AnyFreeBlockNode; // r13d
  int v19; // r12d
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r10d
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r9d
  int v26; // ecx
  unsigned int v27; // ecx
  __int64 AnyFreeDataNode; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned int v31; // r10d
  __int64 v32; // rdx
  int v33; // r8d
  __int64 v34; // rax
  SIZE_T dwBytes; // [rsp+28h] [rbp-50h]
  unsigned int v36; // [rsp+80h] [rbp+8h]

  v1 = *(_DWORD *)(a1 + 72) - *(_DWORD *)(a1 + 68);
  v3 = *(unsigned int *)(a1 + 120);
  v4 = *(_QWORD *)(a1 + 104);
  if ( v1 == *(_DWORD *)(a1 + 76) )
  {
    result = mwFindAnyFreeDataNode(a1, 1u);
    if ( (_DWORD)result == -1 )
      return result;
    *(_DWORD *)(*(_QWORD *)(a1 + 104) + 16LL * (unsigned int)result + 4) = -1;
  }
  v6 = (int *)(v4 + 16 * v3);
  v7 = *(_DWORD *)(a1 + 124);
  if ( v1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v8 = v6[1];
        v9 = v1;
        v10 = *(_DWORD *)(a1 + 68);
        if ( v1 >= v7 + v8 - v10 )
          v9 = v7 + v6[1] - v10;
        if ( v9 )
          break;
        v7 += v8;
        v6 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * (unsigned int)v6[3]);
LABEL_9:
        if ( !v1 )
          goto LABEL_10;
      }
      if ( *v6 >= 0 )
        break;
      if ( v8 + v7 > v10 + v1 )
      {
        v16 = v10 - v7;
        v17 = v16 + v9 + *(_DWORD *)(a1 + 148) - (v16 + v9 + *(_DWORD *)(a1 + 148) - 1) % *(_DWORD *)(a1 + 148) - 1;
        if ( v17 >= v8 )
          v17 = v6[1];
        v36 = v17;
        if ( v17 >= v8 )
        {
          AnyFreeBlockNode = -1;
        }
        else
        {
          AnyFreeBlockNode = mwFindAnyFreeBlockNode(a1);
          if ( AnyFreeBlockNode == -1 )
            goto LABEL_10;
          v17 = v36;
        }
        v19 = v17 - v9 - v16;
        if ( v17 - v9 != v16 )
        {
          LODWORD(dwBytes) = v17 - v9 - v16;
          if ( !(unsigned int)CopyBlockData(a1, v6, v6, v9 + v16, v16, dwBytes) )
            goto LABEL_10;
          v17 = v36;
        }
        if ( AnyFreeBlockNode != -1 )
        {
          v20 = *(_QWORD *)(a1 + 104);
          v21 = 2LL * AnyFreeBlockNode;
          *(_DWORD *)(v20 + 8 * v21) = v17 + *v6;
          *(_DWORD *)(v20 + 8 * v21 + 4) = v6[1] - v17;
          *(_DWORD *)(v20 + 8 * v21 + 8) = v6[2] - v17;
          *(_DWORD *)(v20 + 8 * v21 + 12) = v6[3];
          v6[3] = AnyFreeBlockNode;
          v6[2] = v17;
        }
        v15 = v19 + v16;
      }
      else
      {
        v15 = v8 - v9;
      }
LABEL_38:
      v1 -= v9;
      v6[1] = v15;
      if ( v15 )
        goto LABEL_9;
      if ( !v1 )
        goto LABEL_10;
      v6 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * (unsigned int)v6[3]);
    }
    if ( v7 == v10 )
    {
      *v6 += v9;
    }
    else if ( v8 + v7 > v10 + v1 )
    {
      v22 = mwFindAnyFreeBlockNode(a1);
      if ( v22 == -1 )
        goto LABEL_10;
      v23 = *(_QWORD *)(a1 + 104);
      v24 = 2LL * v22;
      v25 = *(_DWORD *)(a1 + 68);
      v26 = v9 + v25;
      v15 = v25 - v7;
      *(_DWORD *)(v23 + 8 * v24) = v26;
      v27 = v6[1] - v9 - v15;
      *(_DWORD *)(v23 + 8 * v24 + 4) = v27;
      *(_DWORD *)(v23 + 8 * v24 + 8) = v27;
      *(_DWORD *)(v23 + 8 * v24 + 12) = v6[3];
      v6[3] = v22;
      goto LABEL_37;
    }
    v15 = v8 - v9;
LABEL_37:
    v6[2] = v15;
    goto LABEL_38;
  }
LABEL_10:
  v11 = *(unsigned int *)(a1 + 116);
  *(_DWORD *)(a1 + 76) += *(_DWORD *)(a1 + 68) - *(_DWORD *)(a1 + 72) - v1;
  v12 = 0;
  while ( 1 )
  {
    v13 = *(_QWORD *)(a1 + 104) + 16 * v11;
    if ( !*(_DWORD *)(v13 + 4) )
    {
      v14 = *(_DWORD *)(a1 + 120);
      if ( v12 )
      {
        if ( v14 == *(_DWORD *)(v12 + 12) )
          *(_DWORD *)(a1 + 120) = *(_DWORD *)(v13 + 12);
        *(_DWORD *)(v12 + 12) = *(_DWORD *)(v13 + 12);
      }
      else
      {
        if ( v14 == *(_DWORD *)(a1 + 116) )
          *(_DWORD *)(a1 + 120) = *(_DWORD *)(v13 + 12);
        *(_DWORD *)(a1 + 116) = *(_DWORD *)(v13 + 12);
      }
      *(_DWORD *)(v13 + 4) = -1;
    }
    result = *(unsigned int *)(v13 + 12);
    if ( (_DWORD)result == -1 )
      break;
    v12 = v13;
    v11 = (unsigned int)result;
  }
  if ( *(_DWORD *)(a1 + 76) )
  {
    if ( *(_DWORD *)(a1 + 120) == -1 )
    {
      v29 = *(unsigned int *)(a1 + 116);
      v30 = *(_QWORD *)(a1 + 104);
      v31 = *(_DWORD *)(a1 + 68);
      *(_DWORD *)(a1 + 120) = v29;
      v32 = v30 + 16 * v29;
      *(_DWORD *)(a1 + 124) = 0;
      if ( v31 > *(_DWORD *)(v32 + 4) )
      {
        v33 = 0;
        do
        {
          v33 += *(_DWORD *)(v32 + 4);
          *(_DWORD *)(a1 + 124) = v33;
          v34 = *(unsigned int *)(v32 + 12);
          *(_DWORD *)(a1 + 120) = v34;
          result = 2 * v34;
          v32 = v30 + 8 * result;
        }
        while ( v31 > v33 + *(_DWORD *)(v32 + 4) );
      }
    }
  }
  else
  {
    AnyFreeDataNode = (unsigned int)mwFindAnyFreeDataNode(a1, 1u);
    result = *(_QWORD *)(a1 + 104);
    *(_DWORD *)(a1 + 116) = AnyFreeDataNode;
    *(_DWORD *)(a1 + 120) = AnyFreeDataNode;
    *(_DWORD *)(result + 16 * AnyFreeDataNode + 12) = -1;
  }
  return result;
}

```

## disassembly

```asm
0x180001aa8  push    rbx
0x180001aaa  push    rbp
0x180001aab  push    rsi
0x180001aac  push    rdi
0x180001aad  push    r12
0x180001aaf  push    r13
0x180001ab1  push    r14
0x180001ab3  push    r15
0x180001ab5  sub     rsp, 38h
0x180001ab9  mov     esi, [rcx+48h]
0x180001abc  or      r12d, 0FFFFFFFFh
0x180001ac0  sub     esi, [rcx+44h]
0x180001ac3  mov     rbx, rcx
0x180001ac6  mov     edi, [rcx+78h]
0x180001ac9  mov     rbp, [rcx+68h]
0x180001acd  cmp     esi, [rcx+4Ch]
0x180001ad0  jnz     short loc_180001AF3
0x180001ad2  mov     edx, 1
0x180001ad7  call    mwFindAnyFreeDataNode
0x180001adc  cmp     eax, r12d
0x180001adf  jz      loc_180001D9F
0x180001ae5  mov     ecx, eax
0x180001ae7  mov     rax, [rbx+68h]
0x180001aeb  add     rcx, rcx
0x180001aee  mov     [rax+rcx*8+4], r12d
0x180001af3  shl     rdi, 4
0x180001af7  add     rdi, rbp
0x180001afa  mov     ebp, [rbx+7Ch]
0x180001afd  test    esi, esi
0x180001aff  jz      short loc_180001B35
0x180001b01  mov     r9d, [rdi+4]
0x180001b05  mov     r14d, esi
0x180001b08  mov     r15d, [rbx+44h]
0x180001b0c  mov     ecx, r9d
0x180001b0f  sub     ecx, r15d
0x180001b12  add     ecx, ebp
0x180001b14  cmp     esi, ecx
0x180001b16  cmovnb  r14d, ecx
0x180001b1a  test    r14d, r14d
0x180001b1d  jnz     short loc_180001B79
0x180001b1f  mov     edi, [rdi+0Ch]
0x180001b22  add     ebp, r9d
0x180001b25  shl     rdi, 4
0x180001b29  add     rdi, [rbx+68h]
0x180001b2d  test    esi, esi
0x180001b2f  jnz     short loc_180001B01
0x180001b31  or      r12d, 0FFFFFFFFh
0x180001b35  mov     eax, [rbx+44h]
0x180001b38  sub     eax, [rbx+48h]
0x180001b3b  mov     ecx, [rbx+74h]
0x180001b3e  sub     eax, esi
0x180001b40  add     [rbx+4Ch], eax
0x180001b43  xor     edx, edx
0x180001b45  shl     rcx, 4
0x180001b49  add     rcx, [rbx+68h]
0x180001b4d  cmp     dword ptr [rcx+4], 0
0x180001b51  jnz     loc_180001D17
0x180001b57  mov     eax, [rbx+78h]
0x180001b5a  test    rdx, rdx
0x180001b5d  jz      loc_180001D02
0x180001b63  cmp     eax, [rdx+0Ch]
0x180001b66  jnz     short loc_180001B6E
0x180001b68  mov     eax, [rcx+0Ch]
0x180001b6b  mov     [rbx+78h], eax
0x180001b6e  mov     eax, [rcx+0Ch]
0x180001b71  mov     [rdx+0Ch], eax
0x180001b74  jmp     loc_180001D13
0x180001b79  mov     eax, [rdi]
0x180001b7b  test    eax, eax
0x180001b7d  jns     loc_180001C6E
0x180001b83  lea     ecx, [r9+rbp]
0x180001b87  lea     eax, [r15+rsi]
0x180001b8b  cmp     ecx, eax
0x180001b8d  ja      short loc_180001B97
0x180001b8f  sub     r9d, r14d
0x180001b92  jmp     loc_180001CDA
0x180001b97  mov     ecx, [rbx+94h]
0x180001b9d  sub     r15d, ebp
0x180001ba0  xor     edx, edx
0x180001ba2  lea     eax, [rcx-1]
0x180001ba5  add     eax, r14d
0x180001ba8  add     eax, r15d
0x180001bab  div     ecx
0x180001bad  sub     ecx, edx
0x180001baf  lea     r10d, [r14+rcx]
0x180001bb3  dec     r10d
0x180001bb6  add     r10d, r15d
0x180001bb9  cmp     r10d, r9d
0x180001bbc  cmovnb  r10d, r9d
0x180001bc0  mov     [rsp+78h+arg_0], r10d
0x180001bc8  cmp     r10d, r9d
0x180001bcb  jnb     short loc_180001BEB
0x180001bcd  mov     rcx, rbx
0x180001bd0  call    mwFindAnyFreeBlockNode
0x180001bd5  mov     r13d, eax
0x180001bd8  cmp     eax, r12d
0x180001bdb  jz      loc_180001B31
0x180001be1  mov     r10d, [rsp+78h+arg_0]
0x180001be9  jmp     short loc_180001BEE
0x180001beb  mov     r13d, r12d
0x180001bee  mov     r12d, r10d
0x180001bf1  sub     r12d, r14d
0x180001bf4  sub     r12d, r15d
0x180001bf7  jz      short loc_180001C25
0x180001bf9  lea     r9d, [r14+r15]; int
0x180001bfd  mov     dword ptr [rsp+78h+dwBytes], r12d; dwBytes
0x180001c02  mov     r8, rdi; int
0x180001c05  mov     [rsp+78h+var_58], r15d; int
0x180001c0a  mov     rdx, rdi; int
0x180001c0d  mov     rcx, rbx; int
0x180001c10  call    CopyBlockData
0x180001c15  test    eax, eax
0x180001c17  jz      loc_180001B31
0x180001c1d  mov     r10d, [rsp+78h+arg_0]
0x180001c25  cmp     r13d, 0FFFFFFFFh
0x180001c29  jz      short loc_180001C64
0x180001c2b  mov     rdx, [rbx+68h]
0x180001c2f  mov     ecx, [rdi]
0x180001c31  add     ecx, r10d
0x180001c34  mov     r8d, r13d
0x180001c37  add     r8, r8
0x180001c3a  mov     [rdx+r8*8], ecx
0x180001c3e  mov     eax, [rdi+4]
0x180001c41  sub     eax, r10d
0x180001c44  mov     [rdx+r8*8+4], eax
0x180001c49  mov     eax, [rdi+8]
0x180001c4c  sub     eax, r10d
0x180001c4f  mov     [rdx+r8*8+8], eax
0x180001c54  mov     eax, [rdi+0Ch]
0x180001c57  mov     [rdx+r8*8+0Ch], eax
0x180001c5c  mov     [rdi+0Ch], r13d
0x180001c60  mov     [rdi+8], r10d
0x180001c64  lea     r9d, [r12+r15]
0x180001c68  or      r12d, 0FFFFFFFFh
0x180001c6c  jmp     short loc_180001CDA
0x180001c6e  cmp     ebp, r15d
0x180001c71  jnz     short loc_180001C7D
0x180001c73  add     eax, r14d
0x180001c76  mov     [rdi], eax
0x180001c78  sub     r9d, r14d
0x180001c7b  jmp     short loc_180001CD6
0x180001c7d  lea     ecx, [r9+rbp]
0x180001c81  lea     eax, [r15+rsi]
0x180001c85  cmp     ecx, eax
0x180001c87  jbe     short loc_180001C78
0x180001c89  mov     rcx, rbx
0x180001c8c  call    mwFindAnyFreeBlockNode
0x180001c91  mov     r10d, eax
0x180001c94  cmp     eax, r12d
0x180001c97  jz      loc_180001B31
0x180001c9d  mov     ecx, [rbx+44h]
0x180001ca0  mov     r8d, r10d
0x180001ca3  mov     rdx, [rbx+68h]
0x180001ca7  add     r8, r8
0x180001caa  mov     r9d, ecx
0x180001cad  add     ecx, r14d
0x180001cb0  sub     r9d, ebp
0x180001cb3  mov     [rdx+r8*8], ecx
0x180001cb7  mov     ecx, [rdi+4]
0x180001cba  sub     ecx, r14d
0x180001cbd  sub     ecx, r9d
0x180001cc0  mov     [rdx+r8*8+4], ecx
0x180001cc5  mov     [rdx+r8*8+8], ecx
0x180001cca  mov     eax, [rdi+0Ch]
0x180001ccd  mov     [rdx+r8*8+0Ch], eax
0x180001cd2  mov     [rdi+0Ch], r10d
0x180001cd6  mov     [rdi+8], r9d
0x180001cda  sub     esi, r14d
0x180001cdd  mov     [rdi+4], r9d
0x180001ce1  test    r9d, r9d
0x180001ce4  jnz     loc_180001B2D
0x180001cea  test    esi, esi
0x180001cec  jz      loc_180001B31
0x180001cf2  mov     edi, [rdi+0Ch]
0x180001cf5  shl     rdi, 4
0x180001cf9  add     rdi, [rbx+68h]
0x180001cfd  jmp     loc_180001B01
0x180001d02  cmp     eax, [rbx+74h]
0x180001d05  jnz     short loc_180001D0D
0x180001d07  mov     eax, [rcx+0Ch]
0x180001d0a  mov     [rbx+78h], eax
0x180001d0d  mov     eax, [rcx+0Ch]
0x180001d10  mov     [rbx+74h], eax
0x180001d13  mov     [rcx+4], r12d
0x180001d17  mov     eax, [rcx+0Ch]
0x180001d1a  cmp     eax, r12d
0x180001d1d  jz      short loc_180001D29
0x180001d1f  mov     rdx, rcx
0x180001d22  mov     ecx, eax
0x180001d24  jmp     loc_180001B45
0x180001d29  cmp     dword ptr [rbx+4Ch], 0
0x180001d2d  jnz     short loc_180001D52
0x180001d2f  mov     edx, 1
0x180001d34  mov     rcx, rbx
0x180001d37  call    mwFindAnyFreeDataNode
0x180001d3c  mov     ecx, eax
0x180001d3e  mov     rax, [rbx+68h]
0x180001d42  mov     [rbx+74h], ecx
0x180001d45  mov     [rbx+78h], ecx
0x180001d48  add     rcx, rcx
0x180001d4b  mov     [rax+rcx*8+0Ch], r12d
0x180001d50  jmp     short loc_180001D9F
0x180001d52  cmp     [rbx+78h], r12d
0x180001d56  jnz     short loc_180001D9F
0x180001d58  mov     edx, [rbx+74h]
0x180001d5b  mov     r9, [rbx+68h]
0x180001d5f  mov     r10d, [rbx+44h]
0x180001d63  mov     [rbx+78h], edx
0x180001d66  shl     rdx, 4
0x180001d6a  add     rdx, r9
0x180001d6d  mov     dword ptr [rbx+7Ch], 0
0x180001d74  cmp     r10d, [rdx+4]
0x180001d78  jbe     short loc_180001D9F
0x180001d7a  xor     r8d, r8d
0x180001d7d  add     r8d, [rdx+4]
0x180001d81  mov     [rbx+7Ch], r8d
0x180001d85  mov     eax, [rdx+0Ch]
0x180001d88  mov     [rbx+78h], eax
0x180001d8b  add     rax, rax
0x180001d8e  mov     ecx, [r9+rax*8+4]
0x180001d93  lea     rdx, [r9+rax*8]
0x180001d97  add     ecx, r8d
0x180001d9a  cmp     r10d, ecx
0x180001d9d  ja      short loc_180001D7D
0x180001d9f  add     rsp, 38h
0x180001da3  pop     r15
0x180001da5  pop     r14
0x180001da7  pop     r13
0x180001da9  pop     r12
0x180001dab  pop     rdi
0x180001dac  pop     rsi
0x180001dad  pop     rbp
0x180001dae  pop     rbx
0x180001daf  retn
```
