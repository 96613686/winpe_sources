# SpQueryApplicationProtocol(CSslUserContext *,_SecPkgContext_ApplicationProtocol *)

- ea: `0x140004760`
- end: `0x1400047f9`
- name: `?SpQueryApplicationProtocol@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_ApplicationProtocol@@@Z`
- size: `153`
- prototype: `int(struct CSslUserContext *, struct _SecPkgContext_ApplicationProtocol *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002f880`

## callees

- `0x140004760`
- `0x1400105c0`

## pseudocode

```c
__int64 __fastcall SpQueryApplicationProtocol(
        struct CSslUserContext *a1,
        struct _SecPkgContext_ApplicationProtocol *a2)
{
  __int128 *v2; // rax
  struct _SecPkgContext_ApplicationProtocol *v3; // r9
  __int64 result; // rax
  __int64 v5; // rcx
  __int128 v6; // xmm0
  __int64 v7; // rcx

  v2 = (__int128 *)*((_QWORD *)a1 + 54);
  v3 = a2;
  if ( v2 )
  {
    v5 = 2;
    do
    {
      v3 = (struct _SecPkgContext_ApplicationProtocol *)((char *)v3 + 128);
      v6 = *v2;
      v2 += 8;
      *((_OWORD *)v3 - 8) = v6;
      *((_OWORD *)v3 - 7) = *(v2 - 7);
      *((_OWORD *)v3 - 6) = *(v2 - 6);
      *((_OWORD *)v3 - 5) = *(v2 - 5);
      *((_OWORD *)v3 - 4) = *(v2 - 4);
      *((_OWORD *)v3 - 3) = *(v2 - 3);
      *((_OWORD *)v3 - 2) = *(v2 - 2);
      *((_OWORD *)v3 - 1) = *(v2 - 1);
      --v5;
    }
    while ( v5 );
    v7 = *(_QWORD *)v2;
    result = 0;
    *(_QWORD *)v3 = v7;
  }
  else
  {
    memset(a2, 0, 0x108u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004760  sub     rsp, 28h
0x140004764  mov     rax, [rcx+1B0h]
0x14000476b  mov     r9, rdx
0x14000476e  test    rax, rax
0x140004771  jnz     short loc_14000478B
0x140004773  xor     edx, edx; Val
0x140004775  mov     r8d, 108h; Size
0x14000477b  mov     rcx, r9; void *
0x14000477e  call    memset
0x140004783  xor     eax, eax
0x140004785  add     rsp, 28h
0x140004789  retn
0x14000478b  mov     ecx, 2
0x140004790  lea     r9, [r9+80h]
0x140004797  movups  xmm0, xmmword ptr [rax]
0x14000479a  lea     rax, [rax+80h]
0x1400047a1  movups  xmmword ptr [r9-80h], xmm0
0x1400047a6  movups  xmm1, xmmword ptr [rax-70h]
0x1400047aa  movups  xmmword ptr [r9-70h], xmm1
0x1400047af  movups  xmm0, xmmword ptr [rax-60h]
0x1400047b3  movups  xmmword ptr [r9-60h], xmm0
0x1400047b8  movups  xmm1, xmmword ptr [rax-50h]
0x1400047bc  movups  xmmword ptr [r9-50h], xmm1
0x1400047c1  movups  xmm0, xmmword ptr [rax-40h]
0x1400047c5  movups  xmmword ptr [r9-40h], xmm0
0x1400047ca  movups  xmm1, xmmword ptr [rax-30h]
0x1400047ce  movups  xmmword ptr [r9-30h], xmm1
0x1400047d3  movups  xmm0, xmmword ptr [rax-20h]
0x1400047d7  movups  xmmword ptr [r9-20h], xmm0
0x1400047dc  movups  xmm1, xmmword ptr [rax-10h]
0x1400047e0  movups  xmmword ptr [r9-10h], xmm1
0x1400047e5  sub     rcx, 1
0x1400047e9  jnz     short loc_140004790
0x1400047eb  mov     rcx, [rax]
0x1400047ee  xor     eax, eax
0x1400047f0  mov     [r9], rcx
0x1400047f3  add     rsp, 28h
0x1400047f7  retn
```
