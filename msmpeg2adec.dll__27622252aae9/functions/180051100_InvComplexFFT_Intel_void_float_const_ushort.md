# InvComplexFFT_Intel(void *,float * const,ushort)

- ea: `0x180051100`
- end: `0x1800511bb`
- name: `?InvComplexFFT_Intel@@YAJPEAXQEAMG@Z`
- size: `187`
- prototype: `__int64 __fastcall(void *, float *const, unsigned __int16)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180051100`

## import_xrefs

- `mfperfhelper!__imp_ippsFFTInv_PermToR_32f_I` at `0x180051183`
- `mfperfhelper!__imp_ippsFFTInv_PermToR_32f_I` at `0x180051183`

## pseudocode

```c
__int64 __fastcall InvComplexFFT_Intel(unsigned int *a1, float *const a2, unsigned __int16 a3)
{
  unsigned __int16 i; // ax
  unsigned int v6; // edx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8

  for ( i = 0; a3 > 1u; ++i )
    a3 >>= 1;
  if ( !a1 )
    return 2147942487LL;
  v6 = *a1;
  v7 = i;
  if ( i < v6 )
    return 2147942487LL;
  if ( i > a1[1] )
    return 2147942487LL;
  v8 = *((_QWORD *)a1 + 1);
  v9 = 32LL * (int)(v7 - v6);
  if ( !*(_QWORD *)(v9 + v8) )
    return 2147942487LL;
  v10 = *(_QWORD *)(v9 + v8 + 16);
  if ( !v10 )
    return 2147942487LL;
  if ( (v10 & 0x1F) != 0 || ((unsigned __int8)a2 & 0x1F) != 0 )
    return 2147500037LL;
  if ( (int)ippsFFTInv_PermToR_32f_I(a2) >= 0 )
    return 0;
  return 2147500037LL;
}

```

## disassembly

```asm
0x180051100  sub     rsp, 28h
0x180051104  xor     eax, eax
0x180051106  mov     r10, rdx
0x180051109  mov     r9, rcx
0x18005110c  cmp     r8w, 1
0x180051111  jbe     short loc_18005112E
0x180051113  nop     dword ptr [rax+00h]
0x180051117  nop     word ptr [rax+rax+00000000h]
0x180051120  shr     r8w, 1
0x180051124  inc     ax
0x180051127  cmp     r8w, 1
0x18005112c  ja      short loc_180051120
0x18005112e  test    r9, r9
0x180051131  jz      short loc_1800511B0
0x180051133  mov     edx, [rcx]
0x180051135  movzx   ecx, ax
0x180051138  cmp     ecx, edx
0x18005113a  jb      short loc_1800511B0
0x18005113c  cmp     ecx, [r9+4]
0x180051140  ja      short loc_1800511B0
0x180051142  mov     rax, [r9+8]
0x180051146  sub     ecx, edx
0x180051148  movsxd  rcx, ecx
0x18005114b  shl     rcx, 5
0x18005114f  mov     rdx, [rcx+rax]
0x180051153  test    rdx, rdx
0x180051156  jz      short loc_1800511B0
0x180051158  mov     r8, [rcx+rax+10h]
0x18005115d  test    r8, r8
0x180051160  jz      short loc_1800511B0
0x180051162  test    r8b, 1Fh
0x180051166  jnz     short loc_18005116E
0x180051168  test    r10b, 1Fh
0x18005116c  jz      short loc_180051179
0x18005116e  mov     eax, 80004005h
0x180051173  add     rsp, 28h
0x180051177  retn
0x180051179  mov     [rsp+28h+var_8], rbx
0x18005117e  mov     rcx, r10
0x180051181  xor     ebx, ebx
0x180051183  call    cs:__imp_ippsFFTInv_PermToR_32f_I
0x18005118a  nop     dword ptr [rax+rax+00h]
0x18005118f  test    eax, eax
0x180051191  jns     short loc_1800511A3
0x180051193  mov     rbx, [rsp+28h+var_8]
0x180051198  mov     eax, 80004005h
0x18005119d  add     rsp, 28h
0x1800511a1  retn
0x1800511a3  mov     eax, ebx
0x1800511a5  mov     rbx, [rsp+28h+var_8]
0x1800511aa  add     rsp, 28h
0x1800511ae  retn
0x1800511b0  mov     eax, 80070057h
0x1800511b5  add     rsp, 28h
0x1800511b9  retn
```
