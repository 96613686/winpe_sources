# CHuffmanDecoder::ReadBigValues(CBitStream &,int *,int const *,int const *)

- ea: `0x18000b870`
- end: `0x18000bac3`
- name: `?ReadBigValues@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHPEBH2@Z`
- size: `595`
- prototype: `int(CHuffmanDecoder *__hidden this, struct CBitStream *, int *, const int *, const int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f1d0`

## callees

- `0x180001cd4`
- `0x180005630`
- `0x18000b870`
- `0x180010e20`

## pseudocode

```c
__int64 __fastcall CHuffmanDecoder::ReadBigValues(
        CHuffmanDecoder *this,
        struct CBitStream *a2,
        int *a3,
        const int *a4,
        const int *a5)
{
  int v5; // ebx
  const int *v6; // r10
  __int64 v7; // r13
  int *v9; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // r14
  int v16; // edi
  int v17; // ebp
  unsigned int v18; // eax
  unsigned int v19; // eax
  const int *v20; // rax
  unsigned int *v21; // r14
  __int64 v22; // r12
  int v23; // edi
  int v24; // ebp
  unsigned int Bits; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // ecx
  __int64 v30; // rdx
  __int64 v32; // [rsp+20h] [rbp-48h]

  v5 = 0;
  v6 = a4;
  v7 = 0;
  v32 = 0;
  v9 = a3;
  do
  {
    v11 = (unsigned int)v6[v7];
    *((_DWORD *)this + 4) = v11;
    v12 = 2 * v11;
    if ( !*((_QWORD *)&CHuffmanTable::ht + v12 + 1) )
    {
      v20 = a5;
      v29 = a5[v7];
      if ( v5 >= v29 )
        goto LABEL_33;
      v30 = v5;
      do
        ++v5;
      while ( v5 < v29 );
      memset_0(&v9[v30], 0, 4LL * (v29 - (int)v30));
      v9 = a3;
      v6 = a4;
LABEL_32:
      v20 = a5;
      goto LABEL_33;
    }
    v13 = *((_DWORD *)&CHuffmanTable::ht + 2 * v12);
    *((_DWORD *)this + 18) = v13;
    v14 = a5[v7];
    if ( v13 )
    {
      if ( v5 >= v14 )
        goto LABEL_32;
      v21 = (unsigned int *)((char *)this + 76);
      do
      {
        v22 = v5;
        CHuffmanBitObj::ReadFrom((CHuffmanDecoder *)((char *)this + 24), a2);
        v23 = *((_DWORD *)this + 8) & 0xF;
        v24 = (*((int *)this + 8) >> 4) & 0xF;
        if ( v24 == 15 )
        {
          Bits = CBitStream::GetBits(a2, *((_DWORD *)this + 18));
          *v21 = Bits;
          v24 = Bits + 15;
        }
        if ( v24 > 0 )
        {
          v26 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
          *((_DWORD *)this + 15) = v26;
          if ( v26 == 1 )
          {
            v24 = -v24;
            v21 = (unsigned int *)((char *)this + 76);
          }
        }
        if ( v23 == 15 )
        {
          v27 = CBitStream::GetBits(a2, *((_DWORD *)this + 18));
          *v21 = v27;
          v23 = v27 + 15;
        }
        else
        {
          v21 = (unsigned int *)((char *)this + 76);
        }
        if ( v23 > 0 )
        {
          v28 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
          *((_DWORD *)this + 15) = v28;
          if ( v28 == 1 )
            v23 = -v23;
        }
        v9 = a3;
        v5 += 2;
        a3[v22] = v24;
        a3[v22 + 1] = v23;
      }
      while ( v5 < a5[v32] );
      v6 = a4;
      v7 = v32;
      v20 = a5;
    }
    else
    {
      if ( v5 >= v14 )
        goto LABEL_32;
      do
      {
        v15 = v5;
        CHuffmanBitObj::ReadFrom((CHuffmanDecoder *)((char *)this + 24), a2);
        v16 = *((_DWORD *)this + 8) & 0xF;
        v17 = (*((int *)this + 8) >> 4) & 0xF;
        if ( v17 )
        {
          v18 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
          *((_DWORD *)this + 15) = v18;
          if ( v18 == 1 )
            v17 = -v17;
        }
        if ( v16 )
        {
          v19 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
          *((_DWORD *)this + 15) = v19;
          if ( v19 == 1 )
            v16 = -v16;
        }
        v9 = a3;
        v5 += 2;
        v20 = a5;
        a3[v15] = v17;
        a3[v15 + 1] = v16;
      }
      while ( v5 < a5[v7] );
      v6 = a4;
    }
LABEL_33:
    v32 = ++v7;
  }
  while ( v7 != 3 );
  return *((unsigned int *)v20 + 2);
}

```

## disassembly

```asm
0x18000b870  mov     [rsp+arg_0], rbx
0x18000b875  mov     [rsp+arg_18], r9
0x18000b87a  mov     [rsp+arg_10], r8
0x18000b87f  push    rbp
0x18000b880  push    rsi
0x18000b881  push    rdi
0x18000b882  push    r12
0x18000b884  push    r13
0x18000b886  push    r14
0x18000b888  push    r15
0x18000b88a  sub     rsp, 30h
0x18000b88e  xor     ebx, ebx
0x18000b890  mov     r10, r9
0x18000b893  xor     r13d, r13d
0x18000b896  mov     rsi, rcx
0x18000b899  mov     [rsp+68h+var_48], r13
0x18000b89e  lea     rcx, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x18000b8a5  mov     r9, r8
0x18000b8a8  mov     r15, rdx
0x18000b8ab  nop     dword ptr [rax+rax+00h]
0x18000b8b0  mov     eax, [r10+r13*4]
0x18000b8b4  mov     [rsi+10h], eax
0x18000b8b7  add     rax, rax
0x18000b8ba  cmp     qword ptr [rcx+rax*8+8], 0
0x18000b8c0  jz      loc_18000BA47
0x18000b8c6  mov     eax, [rcx+rax*8]
0x18000b8c9  mov     rcx, [rsp+68h+arg_20]
0x18000b8d1  mov     [rsi+48h], eax
0x18000b8d4  mov     ecx, [rcx+r13*4]
0x18000b8d8  test    eax, eax
0x18000b8da  jnz     loc_18000B974
0x18000b8e0  cmp     ebx, ecx
0x18000b8e2  jge     loc_18000BA8A
0x18000b8e8  nop     dword ptr [rax+rax+00000000h]
0x18000b8f0  movsxd  rax, ebx
0x18000b8f3  lea     rcx, [rsi+18h]; this
0x18000b8f7  mov     rdx, r15; struct CBitStream *
0x18000b8fa  lea     r14, ds:0[rax*4]
0x18000b902  call    ?ReadFrom@CHuffmanBitObj@@QEAA_NAEAVCBitStream@@@Z; CHuffmanBitObj::ReadFrom(CBitStream &)
0x18000b907  mov     edi, [rsi+20h]
0x18000b90a  mov     ebp, edi
0x18000b90c  sar     ebp, 4
0x18000b90f  and     edi, 0Fh
0x18000b912  and     ebp, 0Fh
0x18000b915  jz      short loc_18000B92C
0x18000b917  mov     edx, [rsi+38h]; unsigned int
0x18000b91a  mov     rcx, r15; this
0x18000b91d  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000b922  mov     [rsi+3Ch], eax
0x18000b925  cmp     eax, 1
0x18000b928  jnz     short loc_18000B92C
0x18000b92a  neg     ebp
0x18000b92c  test    edi, edi
0x18000b92e  jz      short loc_18000B945
0x18000b930  mov     edx, [rsi+38h]; unsigned int
0x18000b933  mov     rcx, r15; this
0x18000b936  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000b93b  mov     [rsi+3Ch], eax
0x18000b93e  cmp     eax, 1
0x18000b941  jnz     short loc_18000B945
0x18000b943  neg     edi
0x18000b945  mov     r9, [rsp+68h+arg_10]
0x18000b94d  add     ebx, 2
0x18000b950  mov     rax, [rsp+68h+arg_20]
0x18000b958  mov     [r14+r9], ebp
0x18000b95c  mov     [r14+r9+4], edi
0x18000b961  cmp     ebx, [rax+r13*4]
0x18000b965  jl      short loc_18000B8F0
0x18000b967  mov     r10, [rsp+68h+arg_18]
0x18000b96f  jmp     loc_18000BA92
0x18000b974  cmp     ebx, ecx
0x18000b976  jge     loc_18000BA8A
0x18000b97c  lea     r14, [rsi+4Ch]
0x18000b980  movsxd  rax, ebx
0x18000b983  lea     rcx, [rsi+18h]; this
0x18000b987  mov     rdx, r15; struct CBitStream *
0x18000b98a  lea     r12, ds:0[rax*4]
0x18000b992  call    ?ReadFrom@CHuffmanBitObj@@QEAA_NAEAVCBitStream@@@Z; CHuffmanBitObj::ReadFrom(CBitStream &)
0x18000b997  mov     edi, [rsi+20h]
0x18000b99a  mov     ebp, edi
0x18000b99c  sar     ebp, 4
0x18000b99f  and     edi, 0Fh
0x18000b9a2  and     ebp, 0Fh
0x18000b9a5  cmp     ebp, 0Fh
0x18000b9a8  jnz     short loc_18000B9BB
0x18000b9aa  mov     edx, [rsi+48h]; unsigned int
0x18000b9ad  mov     rcx, r15; this
0x18000b9b0  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000b9b5  mov     [r14], eax
0x18000b9b8  lea     ebp, [rax+0Fh]
0x18000b9bb  test    ebp, ebp
0x18000b9bd  jle     short loc_18000B9D8
0x18000b9bf  mov     edx, [rsi+38h]; unsigned int
0x18000b9c2  mov     rcx, r15; this
0x18000b9c5  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000b9ca  mov     [rsi+3Ch], eax
0x18000b9cd  cmp     eax, 1
0x18000b9d0  jnz     short loc_18000B9D8
0x18000b9d2  neg     ebp
0x18000b9d4  lea     r14, [rsi+4Ch]
0x18000b9d8  cmp     edi, 0Fh
0x18000b9db  jnz     short loc_18000B9F0
0x18000b9dd  mov     edx, [rsi+48h]; unsigned int
0x18000b9e0  mov     rcx, r15; this
0x18000b9e3  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000b9e8  mov     [r14], eax
0x18000b9eb  lea     edi, [rax+0Fh]
0x18000b9ee  jmp     short loc_18000B9F4
0x18000b9f0  lea     r14, [rsi+4Ch]
0x18000b9f4  test    edi, edi
0x18000b9f6  jle     short loc_18000BA0D
0x18000b9f8  mov     edx, [rsi+38h]; unsigned int
0x18000b9fb  mov     rcx, r15; this
0x18000b9fe  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000ba03  mov     [rsi+3Ch], eax
0x18000ba06  cmp     eax, 1
0x18000ba09  jnz     short loc_18000BA0D
0x18000ba0b  neg     edi
0x18000ba0d  mov     r9, [rsp+68h+arg_10]
0x18000ba15  add     ebx, 2
0x18000ba18  mov     rax, [rsp+68h+var_48]
0x18000ba1d  mov     rcx, [rsp+68h+arg_20]
0x18000ba25  mov     [r12+r9], ebp
0x18000ba29  mov     [r12+r9+4], edi
0x18000ba2e  cmp     ebx, [rcx+rax*4]
0x18000ba31  jl      loc_18000B980
0x18000ba37  mov     r10, [rsp+68h+arg_18]
0x18000ba3f  mov     r13, rax
0x18000ba42  mov     rax, rcx
0x18000ba45  jmp     short loc_18000BA92
0x18000ba47  mov     rax, [rsp+68h+arg_20]
0x18000ba4f  mov     ecx, [rax+r13*4]
0x18000ba53  cmp     ebx, ecx
0x18000ba55  jge     short loc_18000BA92
0x18000ba57  movsxd  rdx, ebx
0x18000ba5a  nop     word ptr [rax+rax+00h]
0x18000ba60  inc     ebx
0x18000ba62  cmp     ebx, ecx
0x18000ba64  jl      short loc_18000BA60
0x18000ba66  sub     ecx, edx
0x18000ba68  movsxd  r8, ecx
0x18000ba6b  lea     rcx, [r9+rdx*4]; void *
0x18000ba6f  shl     r8, 2; Size
0x18000ba73  xor     edx, edx; Val
0x18000ba75  call    memset_0
0x18000ba7a  mov     r9, [rsp+68h+arg_10]
0x18000ba82  mov     r10, [rsp+68h+arg_18]
0x18000ba8a  mov     rax, [rsp+68h+arg_20]
0x18000ba92  inc     r13
0x18000ba95  lea     rcx, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x18000ba9c  mov     [rsp+68h+var_48], r13
0x18000baa1  cmp     r13, 3
0x18000baa5  jnz     loc_18000B8B0
0x18000baab  mov     eax, [rax+8]
0x18000baae  mov     rbx, [rsp+68h+arg_0]
0x18000bab3  add     rsp, 30h
0x18000bab7  pop     r15
0x18000bab9  pop     r14
0x18000babb  pop     r13
0x18000babd  pop     r12
0x18000babf  pop     rdi
0x18000bac0  pop     rsi
0x18000bac1  pop     rbp
0x18000bac2  retn
```
