# md5Hmac

- ea: `0x14000eef8`
- end: `0x14000f0a2`
- name: `md5Hmac`
- size: `426`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, __int64, int, __int64)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f150`
- `0x14002de70`
- `0x14002df20`
- `0x14002e5e0`
- `0x14002e630`
- `0x14002e7b0`

## callees

- `0x140004ad0`
- `0x140004bb0`
- `0x140004cd0`
- `0x14000eef8`
- `0x140010160`
- `0x1400102c0`
- `0x1400105c0`

## pseudocode

```c
char __fastcall md5Hmac(void *Src, size_t Size, UCHAR *a3, ULONG a4, UCHAR *a5, ULONG a6, _OWORD *a7)
{
  unsigned int v8; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 i; // rax
  __m128 v14; // xmm0
  char result; // al
  BCRYPT_HASH_HANDLE phHash[4]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR v18[64]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v19[5]; // [rsp+C0h] [rbp-40h] BYREF

  v8 = Size;
  memset(phHash, 0, 24);
  memset(v18, 0, sizeof(v18));
  v11 = 64;
  if ( v8 <= 0x40 )
    v11 = v8;
  v12 = v11;
  memmove(v18, Src, v11);
  memset(v17, 0, sizeof(v17));
  memmove(v17, Src, v12);
  for ( i = 0; i != 4; ++i )
  {
    v14 = (__m128)_mm_loadu_si128((const __m128i *)&v17[i]);
    *(__m128 *)&v18[1 * i] = _mm_xor_ps(
                               (__m128)_mm_load_si128((const __m128i *)&_xmm),
                               (__m128)_mm_loadu_si128((const __m128i *)&v18[1 * i]));
    v17[i] = _mm_xor_ps((__m128)_mm_load_si128((const __m128i *)&_xmm), v14);
  }
  CngRsa32Compat_MD5Init(phHash);
  CngRsa32Compat_MD5Update(phHash, v18, 0x40u);
  if ( a4 )
    CngRsa32Compat_MD5Update(phHash, a3, a4);
  if ( a6 )
    CngRsa32Compat_MD5Update(phHash, a5, a6);
  CngRsa32Compat_MD5Final((__int64)phHash);
  v19[0] = v17[0];
  v19[2] = v17[2];
  v19[1] = v17[1];
  v19[4] = *(_OWORD *)&phHash[1];
  v19[3] = v17[3];
  CngRsa32Compat_MD5Init(phHash);
  CngRsa32Compat_MD5Update(phHash, (UCHAR *)v19, 0x50u);
  CngRsa32Compat_MD5Final((__int64)phHash);
  result = 1;
  *a7 = *(_OWORD *)&phHash[1];
  return result;
}

```

## disassembly

```asm
0x14000eef8  push    rbp
0x14000eefa  push    rbx
0x14000eefb  push    rsi
0x14000eefc  push    rdi
0x14000eefd  push    r12
0x14000eeff  push    r13
0x14000ef01  push    r14
0x14000ef03  push    r15
0x14000ef05  lea     rbp, [rsp-28h]
0x14000ef0a  sub     rsp, 128h
0x14000ef11  mov     rax, cs:__security_cookie
0x14000ef18  xor     rax, rsp
0x14000ef1b  mov     [rbp+60h+var_50], rax
0x14000ef1f  mov     r14, [rbp+60h+arg_20]
0x14000ef26  xor     eax, eax
0x14000ef28  mov     r12, [rbp+60h+arg_30]
0x14000ef2f  mov     r15, r8
0x14000ef32  mov     ebx, edx
0x14000ef34  mov     [rsp+160h+var_130], rax
0x14000ef39  mov     rdi, rcx
0x14000ef3c  xorps   xmm0, xmm0
0x14000ef3f  lea     r13d, [rax+40h]
0x14000ef43  xor     edx, edx; Val
0x14000ef45  mov     r8d, r13d; Size
0x14000ef48  lea     rcx, [rbp+60h+var_E0]; void *
0x14000ef4c  mov     esi, r9d
0x14000ef4f  movups  xmmword ptr [rsp+160h+phHash], xmm0
0x14000ef54  call    memset
0x14000ef59  cmp     ebx, r13d
0x14000ef5c  lea     rcx, [rbp+60h+var_E0]; void *
0x14000ef60  mov     eax, r13d
0x14000ef63  mov     rdx, rdi; Src
0x14000ef66  cmovbe  eax, ebx
0x14000ef69  mov     r8d, eax; Size
0x14000ef6c  mov     ebx, eax
0x14000ef6e  call    memmove
0x14000ef73  mov     r8d, r13d; Size
0x14000ef76  lea     rcx, [rsp+160h+var_120]; void *
0x14000ef7b  xor     edx, edx; Val
0x14000ef7d  call    memset
0x14000ef82  mov     r8d, ebx; Size
0x14000ef85  lea     rcx, [rsp+160h+var_120]; void *
0x14000ef8a  mov     rdx, rdi; Src
0x14000ef8d  call    memmove
0x14000ef92  xor     eax, eax
0x14000ef94  movdqu  xmm0, xmmword ptr [rbp+rax*4+60h+var_E0]
0x14000ef9a  movdqa  xmm1, cs:__xmm@36363636363636363636363636363636
0x14000efa2  xorps   xmm1, xmm0
0x14000efa5  movdqu  xmm0, [rsp+rax*4+160h+var_120]
0x14000efab  movdqu  xmmword ptr [rbp+rax*4+60h+var_E0], xmm1
0x14000efb1  movdqa  xmm1, cs:__xmm@5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c
0x14000efb9  xorps   xmm1, xmm0
0x14000efbc  movdqu  [rsp+rax*4+160h+var_120], xmm1
0x14000efc2  add     rax, 4
0x14000efc6  cmp     rax, 10h
0x14000efca  jnz     short loc_14000EF94
0x14000efcc  lea     rcx, [rsp+160h+phHash]; phHash
0x14000efd1  call    CngRsa32Compat_MD5Init
0x14000efd6  mov     r8d, r13d
0x14000efd9  lea     rdx, [rbp+60h+var_E0]
0x14000efdd  lea     rcx, [rsp+160h+phHash]
0x14000efe2  call    CngRsa32Compat_MD5Update
0x14000efe7  test    esi, esi
0x14000efe9  jz      short loc_14000EFFB
0x14000efeb  mov     r8d, esi
0x14000efee  lea     rcx, [rsp+160h+phHash]
0x14000eff3  mov     rdx, r15
0x14000eff6  call    CngRsa32Compat_MD5Update
0x14000effb  mov     r8d, [rbp+60h+arg_28]
0x14000f002  test    r8d, r8d
0x14000f005  jz      short loc_14000F014
0x14000f007  mov     rdx, r14
0x14000f00a  lea     rcx, [rsp+160h+phHash]
0x14000f00f  call    CngRsa32Compat_MD5Update
0x14000f014  lea     rcx, [rsp+160h+phHash]
0x14000f019  call    CngRsa32Compat_MD5Final
0x14000f01e  movups  xmm0, [rsp+160h+var_120]
0x14000f023  lea     rcx, [rsp+160h+phHash]; phHash
0x14000f028  movups  xmm1, [rsp+160h+var_110]
0x14000f02d  movups  [rbp+60h+var_A0], xmm0
0x14000f031  movups  xmm0, [rsp+160h+var_100]
0x14000f036  movups  [rbp+60h+var_80], xmm0
0x14000f03a  movups  xmm0, xmmword ptr [rsp+160h+phHash+8]
0x14000f03f  movups  [rbp+60h+var_90], xmm1
0x14000f043  movups  xmm1, [rsp+160h+var_F0]
0x14000f048  movdqu  [rbp+60h+var_60], xmm0
0x14000f04d  movups  [rbp+60h+var_70], xmm1
0x14000f051  call    CngRsa32Compat_MD5Init
0x14000f056  mov     r8d, 50h ; 'P'
0x14000f05c  lea     rdx, [rbp+60h+var_A0]
0x14000f060  lea     rcx, [rsp+160h+phHash]
0x14000f065  call    CngRsa32Compat_MD5Update
0x14000f06a  lea     rcx, [rsp+160h+phHash]
0x14000f06f  call    CngRsa32Compat_MD5Final
0x14000f074  movups  xmm0, xmmword ptr [rsp+160h+phHash+8]
0x14000f079  mov     al, 1
0x14000f07b  movdqu  xmmword ptr [r12], xmm0
0x14000f081  mov     rcx, [rbp+60h+var_50]
0x14000f085  xor     rcx, rsp; StackCookie
0x14000f088  call    __security_check_cookie
0x14000f08d  add     rsp, 128h
0x14000f094  pop     r15
0x14000f096  pop     r14
0x14000f098  pop     r13
0x14000f09a  pop     r12
0x14000f09c  pop     rdi
0x14000f09d  pop     rsi
0x14000f09e  pop     rbx
0x14000f09f  pop     rbp
0x14000f0a0  retn
```
