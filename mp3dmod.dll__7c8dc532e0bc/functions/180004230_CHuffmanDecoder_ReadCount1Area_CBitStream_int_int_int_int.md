# CHuffmanDecoder::ReadCount1Area(CBitStream &,int *,int,int,int)

- ea: `0x180004230`
- end: `0x1800042ea`
- name: `?ReadCount1Area@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHHHH@Z`
- size: `186`
- prototype: `__int64 __fastcall(CHuffmanDecoder *this, struct CBitStream *, int *, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003e80`

## callees

- `0x180004230`
- `0x180009c10`
- `0x18000efc8`

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
  int i; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rax
  unsigned int v14; // ebx

  *((_DWORD *)this + 4) = a4;
  for ( i = *((_DWORD *)a2 + 8); i < a6; a5 += 4 )
  {
    if ( a5 > 572 )
      break;
    CHuffmanDecoder::ReadHuffmanQuad(this, a2, &a3[a5]);
    i = *((_DWORD *)a2 + 8);
  }
  v10 = a6 - i;
  if ( a6 - i >= 0 )
  {
    if ( !v10 )
      goto LABEL_10;
  }
  else
  {
    a5 -= 4;
    if ( a5 < 0 )
      a5 = 0;
  }
  v11 = *((_DWORD *)a2 + 5);
  v12 = v10 + *((_DWORD *)a2 + 9);
  *((_DWORD *)a2 + 6) -= v10;
  *((_DWORD *)a2 + 8) = a6;
  *((_DWORD *)a2 + 9) = (v11 - 1) & v12;
LABEL_10:
  v13 = (unsigned int)(a5 - 1);
  if ( a5 - 1 > 0 )
  {
    do
    {
      if ( a3[v13] )
        break;
      v13 = (unsigned int)(v13 - 1);
    }
    while ( (int)v13 > 0 );
  }
  v14 = v13 + 1;
  if ( (int)v13 + 1 < 576 )
    memset_0(&a3[v14], 0, 4LL * (int)(576 - v14));
  return v14;
}

```

## disassembly

```asm
0x180004230  push    rbx
0x180004232  push    rbp
0x180004233  push    rsi
0x180004234  push    rdi
0x180004235  sub     rsp, 28h
0x180004239  mov     esi, [rsp+48h+arg_28]
0x18000423d  mov     rdi, r8
0x180004240  mov     ebx, [rsp+48h+arg_20]
0x180004244  mov     rbp, rcx
0x180004247  mov     [rcx+10h], r9d
0x18000424b  mov     eax, [rdx+20h]
0x18000424e  cmp     eax, esi
0x180004250  jge     short loc_180004273
0x180004252  cmp     ebx, 23Ch
0x180004258  jg      short loc_180004273
0x18000425a  movsxd  rax, ebx
0x18000425d  mov     rcx, rbp; this
0x180004260  lea     r8, [rdi+rax*4]; int *
0x180004264  call    ?ReadHuffmanQuad@CHuffmanDecoder@@AEAA_NAEAVCBitStream@@PEAH@Z; CHuffmanDecoder::ReadHuffmanQuad(CBitStream &,int *)
0x180004269  mov     eax, [rdx+20h]
0x18000426c  add     ebx, 4
0x18000426f  cmp     eax, esi
0x180004271  jl      short loc_180004252
0x180004273  mov     r8d, esi
0x180004276  sub     r8d, eax
0x180004279  jns     short loc_180004289
0x18000427b  lea     eax, [rbx-4]
0x18000427e  xor     ecx, ecx
0x180004280  test    eax, eax
0x180004282  mov     ebx, eax
0x180004284  cmovs   ebx, ecx
0x180004287  jmp     short loc_18000428E
0x180004289  test    r8d, r8d
0x18000428c  jz      short loc_1800042A5
0x18000428e  mov     ecx, [rdx+24h]
0x180004291  mov     eax, [rdx+14h]
0x180004294  add     ecx, r8d
0x180004297  sub     [rdx+18h], r8d
0x18000429b  dec     eax
0x18000429d  and     ecx, eax
0x18000429f  mov     [rdx+20h], esi
0x1800042a2  mov     [rdx+24h], ecx
0x1800042a5  lea     eax, [rbx-1]
0x1800042a8  test    eax, eax
0x1800042aa  jle     short loc_1800042BC
0x1800042ac  nop     dword ptr [rax+00h]
0x1800042b0  cmp     dword ptr [rdi+rax*4], 0
0x1800042b4  jnz     short loc_1800042BC
0x1800042b6  dec     eax
0x1800042b8  test    eax, eax
0x1800042ba  jg      short loc_1800042B0
0x1800042bc  lea     ebx, [rax+1]
0x1800042bf  mov     eax, 240h
0x1800042c4  cmp     ebx, eax
0x1800042c6  jge     short loc_1800042DF
0x1800042c8  sub     eax, ebx
0x1800042ca  movsxd  rcx, ebx
0x1800042cd  movsxd  r8, eax
0x1800042d0  xor     edx, edx; Val
0x1800042d2  shl     r8, 2; Size
0x1800042d6  lea     rcx, [rdi+rcx*4]; void *
0x1800042da  call    memset_0
0x1800042df  mov     eax, ebx
0x1800042e1  add     rsp, 28h
0x1800042e5  pop     rdi
0x1800042e6  pop     rsi
0x1800042e7  pop     rbp
0x1800042e8  pop     rbx
0x1800042e9  retn
```
