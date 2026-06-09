# XdrEncodeNfsFileHandleUnsafe

- ea: `0x14000fa80`
- end: `0x14000fb39`
- name: `XdrEncodeNfsFileHandleUnsafe`
- size: `185`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x14000fa80`
- `0x140010870`
- `0x140011960`
- `0x14003b0c0`

## pseudocode

```c
_QWORD *__fastcall XdrEncodeNfsFileHandleUnsafe(__int64 a1, int *a2, char a3)
{
  __int64 v3; // rax
  _BYTE *v4; // r9
  _OWORD *v5; // rax
  __int64 v6; // rdx
  _BYTE *v7; // r10
  __int64 v8; // rax
  char v9; // r8
  _QWORD *result; // rax
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  __int64 v13; // rcx

  if ( a3 )
  {
    v11 = *a2;
    if ( (unsigned int)*a2 > 0x40 )
    {
      v11 = 0;
      *a2 = 0;
    }
    XdrEncodeIntUnsafe(a1, v11);
    return (_QWORD *)XdrEncodeOpaqueUnsafe(v13, v12);
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 72);
    v4 = 0;
    if ( v3 )
      v5 = *(_OWORD **)(v3 + 64);
    else
      v5 = 0;
    *v5 = *(_OWORD *)(a2 + 1);
    v5[1] = *(_OWORD *)(a2 + 5);
    *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += 32LL;
    v6 = *(_QWORD *)(a1 + 72);
    if ( v6 )
    {
      v8 = *(_QWORD *)(v6 + 56);
      v7 = *(_BYTE **)(v6 + 64);
      v9 = (char)v7;
    }
    else
    {
      v7 = 0;
      LOBYTE(v8) = 0;
      v9 = 0;
    }
    *(_QWORD *)(v6 + 64) += ((_BYTE)v8 - v9) & 3;
    result = *(_QWORD **)(a1 + 72);
    if ( result )
      v4 = (_BYTE *)result[8];
    if ( v7 != v4 )
      return memset(v7, 0, v4 - v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000fa80  sub     rsp, 28h
0x14000fa84  mov     r10, rdx
0x14000fa87  test    r8b, r8b
0x14000fa8a  jnz     loc_14000FB10
0x14000fa90  mov     rax, [rcx+48h]
0x14000fa94  xor     r9d, r9d
0x14000fa97  test    rax, rax
0x14000fa9a  jnz     short loc_14000FAA1
0x14000fa9c  mov     eax, r9d
0x14000fa9f  jmp     short loc_14000FAA5
0x14000faa1  mov     rax, [rax+40h]
0x14000faa5  movups  xmm0, xmmword ptr [rdx+4]
0x14000faa9  movups  xmmword ptr [rax], xmm0
0x14000faac  movups  xmm1, xmmword ptr [rdx+14h]
0x14000fab0  movups  xmmword ptr [rax+10h], xmm1
0x14000fab4  mov     rax, [rcx+48h]
0x14000fab8  add     qword ptr [rax+40h], 20h ; ' '
0x14000fabd  mov     rdx, [rcx+48h]
0x14000fac1  mov     r11, [rdx+40h]
0x14000fac5  test    rdx, rdx
0x14000fac8  jnz     short loc_14000FAD5
0x14000faca  mov     r10, r9
0x14000facd  mov     rax, r9
0x14000fad0  mov     r8, r9
0x14000fad3  jmp     short loc_14000FADF
0x14000fad5  mov     rax, [rdx+38h]
0x14000fad9  mov     r10, r11
0x14000fadc  mov     r8, r11
0x14000fadf  sub     rax, r8
0x14000fae2  and     eax, 3
0x14000fae5  add     rax, r11
0x14000fae8  mov     [rdx+40h], rax
0x14000faec  mov     rax, [rcx+48h]
0x14000faf0  test    rax, rax
0x14000faf3  jz      short loc_14000FAF9
0x14000faf5  mov     r9, [rax+40h]
0x14000faf9  cmp     r10, r9
0x14000fafc  jz      short loc_14000FB33
0x14000fafe  sub     r9, r10
0x14000fb01  xor     edx, edx; Val
0x14000fb03  mov     r8, r9; Size
0x14000fb06  mov     rcx, r10; void *
0x14000fb09  call    memset
0x14000fb0e  jmp     short loc_14000FB33
0x14000fb10  mov     r9d, [rdx]
0x14000fb13  cmp     r9d, 40h ; '@'
0x14000fb17  jbe     short loc_14000FB1F
0x14000fb19  xor     r9d, r9d
0x14000fb1c  mov     [rdx], r9d
0x14000fb1f  mov     edx, r9d
0x14000fb22  call    XdrEncodeIntUnsafe
0x14000fb27  mov     edx, r9d
0x14000fb2a  lea     r8, [r10+4]
0x14000fb2e  call    XdrEncodeOpaqueUnsafe
0x14000fb33  add     rsp, 28h
0x14000fb37  retn
```
