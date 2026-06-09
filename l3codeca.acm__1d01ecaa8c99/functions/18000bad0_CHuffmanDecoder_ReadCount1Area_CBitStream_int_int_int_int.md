# CHuffmanDecoder::ReadCount1Area(CBitStream &,int *,int,int,int)

- ea: `0x18000bad0`
- end: `0x18000bc88`
- name: `?ReadCount1Area@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHHHH@Z`
- size: `440`
- prototype: `int(CHuffmanDecoder *__hidden this, struct CBitStream *, int *, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f1d0`

## callees

- `0x180001cd4`
- `0x180005630`
- `0x18000bad0`
- `0x180010e20`

## pseudocode

```c
__int64 __fastcall CHuffmanDecoder::ReadCount1Area(
        CHuffmanDecoder *this,
        struct CBitStream *a2,
        int *a3,
        int a4,
        int a5,
        int a6)
{
  int *v6; // r10
  int v10; // ecx
  int i; // eax
  int *v12; // r12
  int v13; // ebx
  int v14; // ebp
  int v15; // esi
  int v16; // ebx
  int v17; // r15d
  int Bits; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // edx
  int v23; // eax
  __int64 j; // rax
  unsigned int v25; // ebx

  v6 = a3;
  *((_DWORD *)this + 4) = a4;
  v10 = a6;
  for ( i = *((_DWORD *)a2 + 8); i < a6; i = *((_DWORD *)a2 + 8) )
  {
    if ( a5 > 572 )
      break;
    v12 = &v6[a5];
    CHuffmanBitObj::ReadFrom((CHuffmanDecoder *)((char *)this + 24), a2);
    v13 = *((_DWORD *)this + 8);
    v14 = (v13 >> 2) & 1;
    v15 = (v13 >> 1) & 1;
    v16 = v13 & 1;
    v17 = (*((int *)this + 8) >> 3) & 1;
    if ( v17 )
    {
      Bits = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
      *((_DWORD *)this + 15) = Bits;
      if ( Bits == 1 )
        v17 = -v17;
    }
    if ( v14 )
    {
      v19 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
      *((_DWORD *)this + 15) = v19;
      if ( v19 == 1 )
        v14 = -v14;
    }
    if ( v15 )
    {
      v20 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
      *((_DWORD *)this + 15) = v20;
      if ( v20 == 1 )
        v15 = -v15;
    }
    if ( v16 )
    {
      v21 = CBitStream::GetBits(a2, *((_DWORD *)this + 14));
      *((_DWORD *)this + 15) = v21;
      if ( v21 == 1 )
        v16 = -v16;
    }
    v10 = a6;
    a5 += 4;
    v6 = a3;
    *v12 = v17;
    v12[1] = v14;
    v12[2] = v15;
    v12[3] = v16;
  }
  v22 = v10 - i;
  if ( v10 - i >= 0 )
  {
    if ( !v22 )
      goto LABEL_22;
  }
  else
  {
    a5 -= 4;
    if ( a5 < 0 )
      a5 = 0;
  }
  v23 = *((_DWORD *)a2 + 5);
  *((_DWORD *)a2 + 6) -= v22;
  *((_DWORD *)a2 + 8) = v10;
  *((_DWORD *)a2 + 9) = (v23 - 1) & (v22 + *((_DWORD *)a2 + 9));
LABEL_22:
  for ( j = (unsigned int)(a5 - 1); (int)j > 0; j = (unsigned int)(j - 1) )
  {
    if ( v6[j] )
      break;
  }
  v25 = j + 1;
  if ( (int)j + 1 < 576 )
    memset_0(&v6[v25], 0, 4LL * (int)(576 - v25));
  return v25;
}

```

## disassembly

```asm
0x18000bad0  mov     rax, rsp
0x18000bad3  mov     [rax+18h], r8
0x18000bad7  push    rbx
0x18000bad8  sub     rsp, 40h
0x18000badc  mov     [rax+8], rbp
0x18000bae0  mov     r10, r8
0x18000bae3  mov     [rax+10h], rsi
0x18000bae7  mov     [rax+20h], rdi
0x18000baeb  mov     rdi, rcx
0x18000baee  mov     [rax-10h], r12
0x18000baf2  mov     [rax-18h], r13
0x18000baf6  mov     r13d, [rsp+48h+arg_20]
0x18000bafb  mov     [rax-20h], r14
0x18000baff  mov     r14, rdx
0x18000bb02  mov     [rcx+10h], r9d
0x18000bb06  mov     ecx, [rsp+48h+arg_28]
0x18000bb0a  mov     [rax-28h], r15
0x18000bb0e  mov     eax, [rdx+20h]
0x18000bb11  cmp     eax, ecx
0x18000bb13  jge     loc_18000BBEF
0x18000bb19  nop     dword ptr [rax+00000000h]
0x18000bb20  cmp     r13d, 23Ch
0x18000bb27  jg      loc_18000BBEF
0x18000bb2d  movsxd  rax, r13d
0x18000bb30  lea     rcx, [rdi+18h]; this
0x18000bb34  mov     rdx, r14; struct CBitStream *
0x18000bb37  lea     r12, [r10+rax*4]
0x18000bb3b  call    ?ReadFrom@CHuffmanBitObj@@QEAA_NAEAVCBitStream@@@Z; CHuffmanBitObj::ReadFrom(CBitStream &)
0x18000bb40  mov     ebx, [rdi+20h]
0x18000bb43  mov     ebp, ebx
0x18000bb45  mov     esi, ebx
0x18000bb47  sar     ebp, 2
0x18000bb4a  sar     esi, 1
0x18000bb4c  mov     r15d, ebx
0x18000bb4f  and     ebp, 1
0x18000bb52  sar     r15d, 3
0x18000bb56  and     esi, 1
0x18000bb59  and     ebx, 1
0x18000bb5c  and     r15d, 1
0x18000bb60  jz      short loc_18000BB78
0x18000bb62  mov     edx, [rdi+38h]; unsigned int
0x18000bb65  mov     rcx, r14; this
0x18000bb68  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000bb6d  mov     [rdi+3Ch], eax
0x18000bb70  cmp     eax, 1
0x18000bb73  jnz     short loc_18000BB78
0x18000bb75  neg     r15d
0x18000bb78  test    ebp, ebp
0x18000bb7a  jz      short loc_18000BB91
0x18000bb7c  mov     edx, [rdi+38h]; unsigned int
0x18000bb7f  mov     rcx, r14; this
0x18000bb82  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000bb87  mov     [rdi+3Ch], eax
0x18000bb8a  cmp     eax, 1
0x18000bb8d  jnz     short loc_18000BB91
0x18000bb8f  neg     ebp
0x18000bb91  test    esi, esi
0x18000bb93  jz      short loc_18000BBAA
0x18000bb95  mov     edx, [rdi+38h]; unsigned int
0x18000bb98  mov     rcx, r14; this
0x18000bb9b  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000bba0  mov     [rdi+3Ch], eax
0x18000bba3  cmp     eax, 1
0x18000bba6  jnz     short loc_18000BBAA
0x18000bba8  neg     esi
0x18000bbaa  test    ebx, ebx
0x18000bbac  jz      short loc_18000BBC3
0x18000bbae  mov     edx, [rdi+38h]; unsigned int
0x18000bbb1  mov     rcx, r14; this
0x18000bbb4  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x18000bbb9  mov     [rdi+3Ch], eax
0x18000bbbc  cmp     eax, 1
0x18000bbbf  jnz     short loc_18000BBC3
0x18000bbc1  neg     ebx
0x18000bbc3  mov     ecx, [rsp+48h+arg_28]
0x18000bbc7  add     r13d, 4
0x18000bbcb  mov     r10, [rsp+48h+arg_10]
0x18000bbd0  mov     [r12], r15d
0x18000bbd4  mov     [r12+4], ebp
0x18000bbd9  mov     [r12+8], esi
0x18000bbde  mov     [r12+0Ch], ebx
0x18000bbe3  mov     eax, [r14+20h]
0x18000bbe7  cmp     eax, ecx
0x18000bbe9  jl      loc_18000BB20
0x18000bbef  mov     r15, [rsp+48h+var_28]
0x18000bbf4  mov     edx, ecx
0x18000bbf6  sub     edx, eax
0x18000bbf8  mov     r12, [rsp+48h+var_10]
0x18000bbfd  mov     rdi, [rsp+48h+arg_18]
0x18000bc02  mov     rsi, [rsp+48h+arg_8]
0x18000bc07  mov     rbp, [rsp+48h+arg_0]
0x18000bc0c  jns     short loc_18000BC20
0x18000bc0e  lea     eax, [r13-4]
0x18000bc12  xor     r8d, r8d
0x18000bc15  test    eax, eax
0x18000bc17  mov     r13d, eax
0x18000bc1a  cmovs   r13d, r8d
0x18000bc1e  jmp     short loc_18000BC24
0x18000bc20  test    edx, edx
0x18000bc22  jz      short loc_18000BC3E
0x18000bc24  mov     eax, [r14+14h]
0x18000bc28  sub     [r14+18h], edx
0x18000bc2c  dec     eax
0x18000bc2e  mov     [r14+20h], ecx
0x18000bc32  mov     ecx, [r14+24h]
0x18000bc36  add     ecx, edx
0x18000bc38  and     ecx, eax
0x18000bc3a  mov     [r14+24h], ecx
0x18000bc3e  mov     r14, [rsp+48h+var_20]
0x18000bc43  lea     eax, [r13-1]
0x18000bc47  mov     r13, [rsp+48h+var_18]
0x18000bc4c  test    eax, eax
0x18000bc4e  jle     short loc_18000BC5D
0x18000bc50  cmp     dword ptr [r10+rax*4], 0
0x18000bc55  jnz     short loc_18000BC5D
0x18000bc57  dec     eax
0x18000bc59  test    eax, eax
0x18000bc5b  jg      short loc_18000BC50
0x18000bc5d  lea     ebx, [rax+1]
0x18000bc60  mov     eax, 240h
0x18000bc65  cmp     ebx, eax
0x18000bc67  jge     short loc_18000BC80
0x18000bc69  sub     eax, ebx
0x18000bc6b  movsxd  rcx, ebx
0x18000bc6e  movsxd  r8, eax
0x18000bc71  xor     edx, edx; Val
0x18000bc73  shl     r8, 2; Size
0x18000bc77  lea     rcx, [r10+rcx*4]; void *
0x18000bc7b  call    memset_0
0x18000bc80  mov     eax, ebx
0x18000bc82  add     rsp, 40h
0x18000bc86  pop     rbx
0x18000bc87  retn
```
