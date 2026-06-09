# TargetStatsFromFrameId

- ea: `0x18007f37c`
- end: `0x18007f554`
- name: `TargetStatsFromFrameId`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a3d0`

## callees

- `0x180067d2c`
- `0x180075fa0`
- `0x180076f20`
- `0x18007f37c`

## import_xrefs

- `dcomp!__imp_DCompositionGetFrameId` at `0x18007f4b4`
- `dcomp!__imp_DCompositionGetFrameId` at `0x18007f4b4`
- `dcomp!__imp_DCompositionGetStatistics` at `0x18007f3f8`
- `dcomp!__imp_DCompositionGetStatistics` at `0x18007f3f8`
- `dcomp!__imp_DCompositionGetTargetStatistics` at `0x18007f4e5`
- `dcomp!__imp_DCompositionGetTargetStatistics` at `0x18007f4e5`

## string_xrefs

- `0x18007f410`: `onecoreuap\windows\directx\dxg\dxgi\dll\wrap_dcomp.cpp`
- `0x18007f484`: `onecoreuap\windows\directx\dxg\dxgi\dll\wrap_dcomp.cpp`

## pseudocode

```c
__int64 __fastcall TargetStatsFromFrameId(unsigned __int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int Statistics; // edi
  __int64 v7; // rdx
  __int64 v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  _OWORD v18[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-40h]
  __int128 v20; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v17 = 0;
  v16 = 0;
  memset_0(&v20, 0, 0x1C0u);
  v13 = 0;
  Statistics = DCompositionGetStatistics(a1, &v16, 16, &v20);
  if ( Statistics < 0 )
  {
    v7 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\wrap_dcomp.cpp",
      (const char *)(unsigned int)Statistics,
      (int)&v13);
    return (unsigned int)Statistics;
  }
  memset(v15, 0, 28);
  if ( _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12)) )
  {
    v14 = 0;
    Statistics = DCompositionGetFrameId(1, &v14);
    if ( Statistics < 0 )
    {
      v7 = 132;
      goto LABEL_3;
    }
    while ( 1 )
    {
      if ( a1 > v14 )
        return 2147943568LL;
      memset_0(v18, 0, 0x48u);
      if ( (int)DCompositionGetTargetStatistics(a1, v15, v18) >= 0 )
      {
        v9 = v19;
        if ( v19 )
          break;
      }
      ++a1;
    }
    v10 = v18[1];
    *(_OWORD *)a4 = v18[0];
    v11 = v18[2];
    *(_OWORD *)(a4 + 16) = v10;
    v12 = v18[3];
    *(_OWORD *)(a4 + 32) = v11;
    *(_OWORD *)(a4 + 48) = v12;
    *(_QWORD *)(a4 + 64) = v9;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\wrap_dcomp.cpp",
      (const char *)0x80004005LL,
      (int)&v13);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18007f37c  mov     [rsp-8+arg_8], rbx
0x18007f381  push    rbp
0x18007f382  push    rsi
0x18007f383  push    rdi
0x18007f384  push    r14
0x18007f386  push    r15
0x18007f388  lea     rbp, [rsp-1A0h]
0x18007f390  sub     rsp, 2A0h
0x18007f397  mov     rax, cs:__security_cookie
0x18007f39e  xor     rax, rsp
0x18007f3a1  mov     [rbp+1C0h+var_30], rax
0x18007f3a8  mov     r14d, r8d
0x18007f3ab  mov     r15d, edx
0x18007f3ae  mov     rbx, rcx
0x18007f3b1  xorps   xmm0, xmm0
0x18007f3b4  xor     eax, eax
0x18007f3b6  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x18007f3ba  xor     edx, edx; Val
0x18007f3bc  mov     [rsp+2C0h+var_250], rax
0x18007f3c1  mov     r8d, 1C0h; Size
0x18007f3c7  mov     rsi, r9
0x18007f3ca  movups  [rsp+2C0h+var_260], xmm0
0x18007f3cf  call    memset_0
0x18007f3d4  lea     rax, [rsp+2C0h+var_290]
0x18007f3d9  mov     [rsp+2C0h+var_290], 0
0x18007f3e1  lea     r9, [rbp+1C0h+var_1F0]
0x18007f3e5  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18007f3ea  mov     r8d, 10h
0x18007f3f0  lea     rdx, [rsp+2C0h+var_260]
0x18007f3f5  mov     rcx, rbx
0x18007f3f8  call    cs:__imp_DCompositionGetStatistics
0x18007f3fe  mov     edi, eax
0x18007f400  test    eax, eax
0x18007f402  jns     short loc_18007F426
0x18007f404  mov     edx, 72h ; 'r'; void *
0x18007f409  mov     rcx, [rbp+1C8h]; this
0x18007f410  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18007f417  mov     r9d, edi; char *
0x18007f41a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f41f  mov     eax, edi
0x18007f421  jmp     loc_18007F507
0x18007f426  mov     r8d, [rsp+2C0h+var_290]
0x18007f42b  xorps   xmm0, xmm0
0x18007f42e  xor     ecx, ecx
0x18007f430  movups  xmmword ptr [rsp+2C0h+var_280], xmm0
0x18007f435  movups  xmmword ptr [rsp+2C0h+var_280+0Ch], xmm0
0x18007f43a  test    r8d, r8d
0x18007f43d  jz      short loc_18007F470
0x18007f43f  mov     eax, ecx
0x18007f441  imul    rdx, rax, 1Ch
0x18007f445  cmp     r15d, [rbp+rdx+1C0h+var_1E0]
0x18007f44a  jnz     short loc_18007F453
0x18007f44c  cmp     r14d, [rbp+rdx+1C0h+var_1DC]
0x18007f451  jz      short loc_18007F45C
0x18007f453  inc     ecx
0x18007f455  cmp     ecx, r8d
0x18007f458  jb      short loc_18007F43F
0x18007f45a  jmp     short loc_18007F470
0x18007f45c  movups  xmm0, [rbp+rdx+1C0h+var_1F0]
0x18007f461  movups  xmmword ptr [rsp+2C0h+var_280], xmm0
0x18007f466  movups  xmm0, [rbp+rdx+1C0h+var_1F0+0Ch]
0x18007f46b  movups  xmmword ptr [rsp+2C0h+var_280+0Ch], xmm0
0x18007f470  psrldq  xmm0, 0Ch
0x18007f475  movd    eax, xmm0
0x18007f479  test    eax, eax
0x18007f47b  jnz     short loc_18007F4A1
0x18007f47d  mov     rcx, [rbp+1C8h]; this
0x18007f484  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18007f48b  mov     ebx, 80004005h
0x18007f490  mov     edx, 81h; void *
0x18007f495  mov     r9d, ebx; char *
0x18007f498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f49d  mov     eax, ebx
0x18007f49f  jmp     short loc_18007F507
0x18007f4a1  lea     rdx, [rsp+2C0h+var_288]
0x18007f4a6  mov     [rsp+2C0h+var_288], 0
0x18007f4af  mov     ecx, 1
0x18007f4b4  call    cs:__imp_DCompositionGetFrameId
0x18007f4ba  mov     edi, eax
0x18007f4bc  test    eax, eax
0x18007f4be  jns     short loc_18007F4FB
0x18007f4c0  mov     edx, 84h
0x18007f4c5  jmp     loc_18007F409
0x18007f4ca  xor     edx, edx; Val
0x18007f4cc  lea     rcx, [rbp+1C0h+var_240]; void *
0x18007f4d0  lea     r8d, [rdx+48h]; Size
0x18007f4d4  call    memset_0
0x18007f4d9  lea     r8, [rbp+1C0h+var_240]
0x18007f4dd  mov     rcx, rbx
0x18007f4e0  lea     rdx, [rsp+2C0h+var_280]
0x18007f4e5  call    cs:__imp_DCompositionGetTargetStatistics
0x18007f4eb  test    eax, eax
0x18007f4ed  js      short loc_18007F4F8
0x18007f4ef  mov     rax, [rbp+1C0h+var_200]
0x18007f4f3  test    rax, rax
0x18007f4f6  jnz     short loc_18007F52D
0x18007f4f8  inc     rbx
0x18007f4fb  cmp     rbx, [rsp+2C0h+var_288]
0x18007f500  jbe     short loc_18007F4CA
0x18007f502  mov     eax, 80070490h
0x18007f507  mov     rcx, [rbp+1C0h+var_30]
0x18007f50e  xor     rcx, rsp; StackCookie
0x18007f511  call    __security_check_cookie
0x18007f516  mov     rbx, [rsp+2C0h+arg_8]
0x18007f51e  add     rsp, 2A0h
0x18007f525  pop     r15
0x18007f527  pop     r14
0x18007f529  pop     rdi
0x18007f52a  pop     rsi
0x18007f52b  pop     rbp
0x18007f52c  retn
0x18007f52d  movaps  xmm0, [rbp+1C0h+var_240]
0x18007f531  movaps  xmm1, [rbp+1C0h+var_230]
0x18007f535  movaps  xmmword ptr [rsi], xmm0
0x18007f538  movaps  xmm0, [rbp+1C0h+var_220]
0x18007f53c  movaps  xmmword ptr [rsi+10h], xmm1
0x18007f540  movaps  xmm1, [rbp+1C0h+var_210]
0x18007f544  movaps  xmmword ptr [rsi+20h], xmm0
0x18007f548  movaps  xmmword ptr [rsi+30h], xmm1
0x18007f54c  mov     [rsi+40h], rax
0x18007f550  xor     eax, eax
0x18007f552  jmp     short loc_18007F507
```
