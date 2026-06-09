# LKRhash::CLKRLinearHashTable::_DeleteKey(unsigned __int64,ulong)

- ea: `0x180019de8`
- end: `0x180019f93`
- name: `?_DeleteKey@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@_KK@Z`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000f9d8`

## callees

- `0x180002d60`
- `0x1800037e0`
- `0x180003f40`
- `0x180004010`
- `0x180004150`
- `0x180004790`
- `0x180019de8`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_DeleteKey(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // ebp
  unsigned int v7; // eax
  unsigned __int64 v8; // r15
  struct LKRhash::CNodeClump *v9; // rsi
  struct LKRhash::CNodeClump *v10; // rax
  int v11; // edi
  int v12; // eax
  int i; // ecx
  __int64 v14; // rax
  double v15; // xmm6_8
  int v16; // eax
  struct LKRhash::CNodeClump *v18; // [rsp+30h] [rbp-48h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF
  struct LKRhash::CNodeClump *v20; // [rsp+98h] [rbp+20h] BYREF

  LKRhash::CLKRLinearHashTable::WriteLock((LKRhash::CLKRLinearHashTable *)a1);
  if ( *(_DWORD *)(a1 + 20) )
  {
    LKRhash::CLKRLinearHashTable::WriteUnlock((LKRhash::CLKRLinearHashTable *)a1);
    return *(unsigned int *)(a1 + 20);
  }
  else
  {
    v6 = 2;
    v7 = *(_DWORD *)(a1 + 88) & a3;
    if ( v7 < *(_DWORD *)(a1 + 96) )
      v7 = a3 & *(_DWORD *)(a1 + 92);
    v8 = ((unsigned __int64)(v7 & *(_DWORD *)(a1 + 76)) << 6)
       + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v7 >> *(_DWORD *)(a1 + 68)));
    LKRhash::CLKRLinearHashTable::_BucketWriteLock((LKRhash::CLKRLinearHashTable *)a1, (struct LKRhash::CBucket *)v8);
    LKRhash::CLKRLinearHashTable::WriteUnlock((LKRhash::CLKRLinearHashTable *)a1);
    v9 = (struct LKRhash::CNodeClump *)(v8 + 8);
    v20 = 0;
    v18 = (struct LKRhash::CNodeClump *)(v8 + 8);
    v10 = (struct LKRhash::CNodeClump *)(v8 + 8);
LABEL_5:
    if ( v10 )
    {
      v11 = 0;
      v19 = 0;
      v12 = 0;
      for ( i = 0; ; i = v11 )
      {
        if ( v11 >= 4 )
        {
          v10 = (struct LKRhash::CNodeClump *)*((_QWORD *)v9 + 2);
          v20 = v9;
          v9 = v10;
          v18 = v10;
          goto LABEL_5;
        }
        if ( *((_DWORD *)v9 + v12) == 31678523 )
          goto LABEL_15;
        if ( a3 == *((_DWORD *)v9 + v12) )
        {
          v14 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 32))(*((_QWORD *)v9 + i + 3));
          if ( a2 == v14 || (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(a2, v14) )
            break;
        }
        v19 = ++v11;
        v12 = v11;
      }
      LKRhash::CLKRLinearHashTable::_DeleteNode(
        (LKRhash::CLKRLinearHashTable *)a1,
        (struct LKRhash::CBucket *)v8,
        &v18,
        &v20,
        &v19);
      v6 = 0;
    }
LABEL_15:
    LKRhash::CLKRLinearHashTable::_BucketWriteUnlock((LKRhash::CLKRLinearHashTable *)a1, (struct LKRhash::CBucket *)v8);
    if ( !v6 )
    {
      v15 = (double)(*(_DWORD *)(a1 + 120) + (*(_DWORD *)(a1 + 120) >> 4));
      do
        v16 = *(_DWORD *)(a1 + 124);
      while ( (double)v16 * *(double *)(a1 + 80) > v15
           && (unsigned int)v16 > *(_DWORD *)(a1 + 72)
           && !(unsigned int)LKRhash::CLKRLinearHashTable::_Contract(a1) );
    }
    return v6;
  }
}

```

## disassembly

```asm
0x180019de8  mov     [rsp+arg_8], rbx
0x180019ded  mov     [rsp+arg_10], rbp
0x180019df2  push    rsi
0x180019df3  push    rdi
0x180019df4  push    r12
0x180019df6  push    r14
0x180019df8  push    r15
0x180019dfa  sub     rsp, 50h
0x180019dfe  movaps  [rsp+78h+var_38], xmm6
0x180019e03  mov     r14d, r8d
0x180019e06  mov     r12, rdx
0x180019e09  mov     rbx, rcx
0x180019e0c  call    ?WriteLock@CLKRLinearHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRLinearHashTable::WriteLock(void)
0x180019e11  cmp     dword ptr [rbx+14h], 0
0x180019e15  jnz     loc_180019F6A
0x180019e1b  mov     eax, r14d
0x180019e1e  mov     ebp, 2
0x180019e23  and     eax, [rbx+58h]
0x180019e26  cmp     eax, [rbx+60h]
0x180019e29  jnb     short loc_180019E31
0x180019e2b  mov     eax, [rbx+5Ch]
0x180019e2e  and     eax, r14d
0x180019e31  mov     ecx, [rbx+44h]
0x180019e34  mov     edx, [rbx+4Ch]
0x180019e37  and     rdx, rax
0x180019e3a  mov     r8d, eax
0x180019e3d  shr     r8, cl
0x180019e40  mov     rcx, [rbx+68h]
0x180019e44  shl     rdx, 6
0x180019e48  mov     r15, [rcx+r8*8]
0x180019e4c  mov     rcx, rbx; this
0x180019e4f  add     r15, rdx
0x180019e52  mov     rdx, r15; struct LKRhash::CBucket *
0x180019e55  call    ?_BucketWriteLock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z; LKRhash::CLKRLinearHashTable::_BucketWriteLock(LKRhash::CBucket *)
0x180019e5a  mov     rcx, rbx; this
0x180019e5d  call    ?WriteUnlock@CLKRLinearHashTable@LKRhash@@QEBAXXZ; LKRhash::CLKRLinearHashTable::WriteUnlock(void)
0x180019e62  lea     rsi, [r15+8]
0x180019e66  mov     [rsp+78h+arg_18], 0
0x180019e72  mov     [rsp+78h+var_48], rsi
0x180019e77  mov     rax, rsi
0x180019e7a  test    rax, rax
0x180019e7d  jz      loc_180019F1F
0x180019e83  xor     edi, edi
0x180019e85  mov     [rsp+78h+arg_0], 0
0x180019e90  xor     eax, eax
0x180019e92  xor     ecx, ecx
0x180019e94  cmp     edi, 4
0x180019e97  jge     short loc_180019EE2
0x180019e99  cdqe
0x180019e9b  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x180019ea2  jz      short loc_180019F1F
0x180019ea4  cmp     r14d, [rsi+rax*4]
0x180019ea8  jnz     short loc_180019ED3
0x180019eaa  mov     rax, [rbx+20h]
0x180019eae  movsxd  rcx, ecx
0x180019eb1  mov     rcx, [rsi+rcx*8+18h]
0x180019eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ebb  cmp     r12, rax
0x180019ebe  jz      short loc_180019EF8
0x180019ec0  mov     rdx, rax
0x180019ec3  mov     rcx, r12
0x180019ec6  mov     rax, [rbx+30h]
0x180019eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ecf  test    al, al
0x180019ed1  jnz     short loc_180019EF8
0x180019ed3  inc     edi
0x180019ed5  mov     [rsp+78h+arg_0], edi
0x180019edc  mov     eax, edi
0x180019ede  mov     ecx, edi
0x180019ee0  jmp     short loc_180019E94
0x180019ee2  mov     rax, [rsi+10h]
0x180019ee6  mov     [rsp+78h+arg_18], rsi
0x180019eee  mov     rsi, rax
0x180019ef1  mov     [rsp+78h+var_48], rax
0x180019ef6  jmp     short loc_180019E7A
0x180019ef8  lea     rax, [rsp+78h+arg_0]
0x180019f00  mov     rdx, r15; struct LKRhash::CBucket *
0x180019f03  lea     r9, [rsp+78h+arg_18]; struct LKRhash::CNodeClump **
0x180019f0b  mov     [rsp+78h+var_58], rax; int *
0x180019f10  lea     r8, [rsp+78h+var_48]; struct LKRhash::CNodeClump **
0x180019f15  mov     rcx, rbx; this
0x180019f18  call    ?_DeleteNode@CLKRLinearHashTable@LKRhash@@AEAA_NPEAVCBucket@2@AEAPEAVCNodeClump@2@1AEAH@Z; LKRhash::CLKRLinearHashTable::_DeleteNode(LKRhash::CBucket *,LKRhash::CNodeClump * &,LKRhash::CNodeClump * &,int &)
0x180019f1d  xor     ebp, ebp
0x180019f1f  mov     rdx, r15; struct LKRhash::CBucket *
0x180019f22  mov     rcx, rbx; this
0x180019f25  call    ?_BucketWriteUnlock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z; LKRhash::CLKRLinearHashTable::_BucketWriteUnlock(LKRhash::CBucket *)
0x180019f2a  test    ebp, ebp
0x180019f2c  jnz     short loc_180019F66
0x180019f2e  mov     eax, [rbx+78h]
0x180019f31  xorps   xmm6, xmm6
0x180019f34  shr     eax, 4
0x180019f37  add     eax, [rbx+78h]
0x180019f3a  cvtsi2sd xmm6, rax
0x180019f3f  mov     eax, [rbx+7Ch]
0x180019f42  xorps   xmm0, xmm0
0x180019f45  cvtsi2sd xmm0, rax
0x180019f4a  mulsd   xmm0, qword ptr [rbx+50h]
0x180019f4f  comisd  xmm0, xmm6
0x180019f53  jbe     short loc_180019F66
0x180019f55  cmp     eax, [rbx+48h]
0x180019f58  jbe     short loc_180019F66
0x180019f5a  mov     rcx, rbx
0x180019f5d  call    ?_Contract@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@XZ; LKRhash::CLKRLinearHashTable::_Contract(void)
0x180019f62  test    eax, eax
0x180019f64  jz      short loc_180019F3F
0x180019f66  mov     eax, ebp
0x180019f68  jmp     short loc_180019F75
0x180019f6a  mov     rcx, rbx; this
0x180019f6d  call    ?WriteUnlock@CLKRLinearHashTable@LKRhash@@QEBAXXZ; LKRhash::CLKRLinearHashTable::WriteUnlock(void)
0x180019f72  mov     eax, [rbx+14h]
0x180019f75  movaps  xmm6, [rsp+78h+var_38]
0x180019f7a  lea     r11, [rsp+78h+var_28]
0x180019f7f  mov     rbx, [r11+38h]
0x180019f83  mov     rbp, [r11+40h]
0x180019f87  mov     rsp, r11
0x180019f8a  pop     r15
0x180019f8c  pop     r14
0x180019f8e  pop     r12
0x180019f90  pop     rdi
0x180019f91  pop     rsi
0x180019f92  retn
```
