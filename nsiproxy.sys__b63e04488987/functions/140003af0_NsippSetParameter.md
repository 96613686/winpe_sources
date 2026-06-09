# NsippSetParameter

- ea: `0x140003af0`
- end: `0x140003e0f`
- name: `NsippSetParameter`
- size: `799`
- prototype: `__int64 __fastcall(void *Src, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140003af0`
- `0x1400043d0`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140003b48`
- `ntoskrnl!IoIs32bitProcess` at `0x140003b48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003df4`
- `NETIO!NsiSetParameterEx` at `0x140003ce2`
- `NETIO!NsiSetParameterEx` at `0x140003ce2`

## pseudocode

```c
__int64 __fastcall NsippSetParameter(void *Src, unsigned int a2, unsigned __int8 a3)
{
  BOOLEAN v6; // al
  int v7; // ebx
  _DWORD *v8; // rdi
  PVOID P; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 v11; // [rsp+D8h] [rbp-E0h] BYREF
  char *v12; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+E8h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v15; // [rsp+100h] [rbp-B8h]
  __int128 v16; // [rsp+110h] [rbp-A8h]
  _QWORD v17[10]; // [rsp+120h] [rbp-98h] BYREF
  __m128i v18; // [rsp+170h] [rbp-48h] BYREF
  _QWORD v19[7]; // [rsp+180h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+1D8h] [rbp+20h] BYREF

  P = 0;
  v18 = 0;
  v20 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  memset(v17, 0, sizeof(v17));
  v6 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v6 )
  {
    if ( a2 >= 0x30 )
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      if ( a3 )
        RtlCopyFromUser(&v14, Src, 0x30u);
      else
        RtlCopyVolatileMemory(&v14, Src, 0x30u);
      v17[5] = DWORD2(v15);
      LODWORD(v17[6]) = HIDWORD(v15);
      v17[2] = DWORD2(v14);
      LODWORD(v17[1]) = DWORD1(v14);
      LODWORD(v17[3]) = HIDWORD(v14);
      v17[8] = DWORD1(v16);
      v17[9] = *((_QWORD *)&v16 + 1);
      LODWORD(v17[7]) = v16;
      v17[4] = v15;
      v17[0] = (int)v14;
      goto LABEL_7;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x50 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v17, Src, 0x50u);
  else
    RtlCopyVolatileMemory(v17, Src, 0x50u);
LABEL_7:
  v7 = NsippProbeAndAllocateParameters(
         v17,
         0x50u,
         (__int64)&v17[1],
         (__m128i *)&v17[5],
         (__int64)&v17[7],
         0,
         0,
         0,
         a3,
         1u,
         1,
         &v18,
         &v11,
         v19,
         &v20,
         &v13,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         &v12,
         &P);
  v8 = P;
  if ( v7 >= 0 )
  {
    *((_QWORD *)P + 5) = v11;
    v8[12] = v18.m128i_i32[2];
    *((_QWORD *)v8 + 2) = v12;
    *((_QWORD *)v8 + 8) = v13;
    v8[18] = v20;
    v7 = NsiSetParameterEx(v8);
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140003af0  mov     rax, rsp
0x140003af3  push    rbx
0x140003af4  push    rsi
0x140003af5  push    rdi
0x140003af6  push    r14
0x140003af8  sub     rsp, 198h
0x140003aff  movzx   edi, r8b
0x140003b03  mov     esi, edx
0x140003b05  mov     rbx, rcx
0x140003b08  xor     r14d, r14d
0x140003b0b  mov     [rax-0E8h], r14
0x140003b12  xorps   xmm0, xmm0
0x140003b15  movups  xmmword ptr [rax-48h], xmm0
0x140003b19  mov     [rax+20h], r14d
0x140003b1d  mov     [rax-0E0h], r14
0x140003b24  mov     [rax-0D0h], r14
0x140003b2b  mov     [rax-0D8h], r14
0x140003b32  xor     edx, edx; Val
0x140003b34  mov     r8d, 50h ; 'P'; Size
0x140003b3a  lea     rcx, [rax-98h]; void *
0x140003b41  call    memset
0x140003b46  xor     ecx, ecx; Irp
0x140003b48  call    cs:__imp_IoIs32bitProcess
0x140003b4f  nop     dword ptr [rax+rax+00h]
0x140003b54  test    rbx, rbx
0x140003b57  jz      loc_140003E05
0x140003b5d  test    al, al
0x140003b5f  jnz     loc_140003DCA
0x140003b65  cmp     esi, 50h ; 'P'
0x140003b68  jb      loc_140003E05
0x140003b6e  mov     r8d, 50h ; 'P'; Size
0x140003b74  mov     rdx, rbx; Src
0x140003b77  lea     rcx, [rsp+1B8h+var_98]; void *
0x140003b7f  test    dil, dil
0x140003b82  jz      short loc_140003B8B
0x140003b84  call    RtlCopyFromUser
0x140003b89  jmp     short loc_140003B90
0x140003b8b  call    RtlCopyVolatileMemory
0x140003b90  jmp     short loc_140003B97
0x140003b92  jmp     loc_140003C99
0x140003b97  lea     rax, [rsp+1B8h+P]
0x140003b9f  mov     [rsp+1B8h+var_F8], rax
0x140003ba7  lea     rax, [rsp+1B8h+var_D8]
0x140003baf  mov     [rsp+1B8h+var_100], rax
0x140003bb7  mov     [rsp+1B8h+var_108], r14
0x140003bbf  mov     [rsp+1B8h+var_110], r14
0x140003bc7  mov     [rsp+1B8h+var_118], r14
0x140003bcf  mov     [rsp+1B8h+var_120], r14
0x140003bd7  mov     [rsp+1B8h+var_128], r14
0x140003bdf  mov     [rsp+1B8h+var_130], r14
0x140003be7  mov     [rsp+1B8h+var_138], r14
0x140003bef  lea     rax, [rsp+1B8h+var_D0]
0x140003bf7  mov     [rsp+1B8h+var_140], rax
0x140003bfc  lea     rax, [rsp+1B8h+arg_18]
0x140003c04  mov     [rsp+1B8h+var_148], rax
0x140003c09  lea     rax, [rsp+1B8h+var_38]
0x140003c11  mov     [rsp+1B8h+var_150], rax
0x140003c16  lea     rax, [rsp+1B8h+var_E0]
0x140003c1e  mov     [rsp+1B8h+var_158], rax
0x140003c23  lea     rax, [rsp+1B8h+var_48]
0x140003c2b  mov     [rsp+1B8h+var_160], rax
0x140003c30  mov     [rsp+1B8h+var_168], 1
0x140003c35  mov     [rsp+1B8h+var_170], 1
0x140003c3d  mov     [rsp+1B8h+var_178], dil
0x140003c42  mov     [rsp+1B8h+var_180], r14
0x140003c47  mov     [rsp+1B8h+var_188], r14
0x140003c4c  mov     [rsp+1B8h+var_190], r14
0x140003c51  lea     rax, [rsp+1B8h+var_60]
0x140003c59  mov     [rsp+1B8h+var_198], rax
0x140003c5e  lea     r9, [rsp+1B8h+var_70]
0x140003c66  lea     r8, [rsp+1B8h+var_90]
0x140003c6e  mov     edx, 50h ; 'P'
0x140003c73  lea     rcx, [rsp+1B8h+var_98]
0x140003c7b  call    NsippProbeAndAllocateParameters
0x140003c80  mov     ebx, eax
0x140003c82  mov     rdi, [rsp+1B8h+P]
0x140003c8a  test    eax, eax
0x140003c8c  jns     short loc_140003CA7
0x140003c8e  test    rdi, rdi
0x140003c91  jnz     loc_140003DEF
0x140003c97  mov     eax, ebx
0x140003c99  add     rsp, 198h
0x140003ca0  pop     r14
0x140003ca2  pop     rdi
0x140003ca3  pop     rsi
0x140003ca4  pop     rbx
0x140003ca5  retn
0x140003ca7  mov     rax, [rsp+1B8h+var_E0]
0x140003caf  mov     [rdi+28h], rax
0x140003cb3  mov     eax, [rsp+1B8h+var_40]
0x140003cba  mov     [rdi+30h], eax
0x140003cbd  mov     rax, [rsp+1B8h+var_D8]
0x140003cc5  mov     [rdi+10h], rax
0x140003cc9  mov     rax, [rsp+1B8h+var_D0]
0x140003cd1  mov     [rdi+40h], rax
0x140003cd5  mov     eax, [rsp+1B8h+arg_18]
0x140003cdc  mov     [rdi+48h], eax
0x140003cdf  mov     rcx, rdi
0x140003ce2  call    cs:__imp_NsiSetParameterEx
0x140003ce9  nop     dword ptr [rax+rax+00h]
0x140003cee  mov     ebx, eax
0x140003cf0  jmp     short loc_140003C8E
0x140003cf2  mov     r8d, 30h ; '0'; Size
0x140003cf8  mov     rdx, rbx; Src
0x140003cfb  lea     rcx, [rsp+1B8h+var_C8]; void *
0x140003d03  test    dil, dil
0x140003d06  jz      short loc_140003D0F
0x140003d08  call    RtlCopyFromUser
0x140003d0d  jmp     short loc_140003D14
0x140003d0f  call    RtlCopyVolatileMemory
0x140003d14  jmp     short loc_140003D18
0x140003d16  jmp     short loc_140003C99
0x140003d18  mov     eax, dword ptr [rsp+1B8h+var_B8+4]
0x140003d1f  mov     dword ptr [rsp+1B8h+var_78+4], eax
0x140003d26  mov     eax, dword ptr [rsp+1B8h+var_B8+8]
0x140003d2d  mov     [rsp+1B8h+var_70], rax
0x140003d35  mov     eax, dword ptr [rsp+1B8h+var_B8+0Ch]
0x140003d3c  mov     [rsp+1B8h+var_68], eax
0x140003d43  mov     eax, dword ptr [rsp+1B8h+var_C8+8]
0x140003d4a  mov     [rsp+1B8h+var_88], rax
0x140003d52  mov     eax, dword ptr [rsp+1B8h+var_C8+4]
0x140003d59  mov     [rsp+1B8h+var_90], eax
0x140003d60  mov     eax, dword ptr [rsp+1B8h+var_C8+0Ch]
0x140003d67  mov     [rsp+1B8h+var_80], eax
0x140003d6e  mov     eax, dword ptr [rsp+1B8h+var_A8+4]
0x140003d75  mov     [rsp+1B8h+var_58], rax
0x140003d7d  mov     eax, dword ptr [rsp+1B8h+var_A8+8]
0x140003d84  mov     dword ptr [rsp+1B8h+var_50], eax
0x140003d8b  mov     eax, dword ptr [rsp+1B8h+var_A8+0Ch]
0x140003d92  mov     dword ptr [rsp+1B8h+var_50+4], eax
0x140003d99  mov     eax, dword ptr [rsp+1B8h+var_A8]
0x140003da0  mov     [rsp+1B8h+var_60], eax
0x140003da7  mov     eax, dword ptr [rsp+1B8h+var_B8]
0x140003dae  mov     dword ptr [rsp+1B8h+var_78], eax
0x140003db5  movsxd  rax, dword ptr [rsp+1B8h+var_C8]
0x140003dbd  mov     [rsp+1B8h+var_98], rax
0x140003dc5  jmp     loc_140003B97
0x140003dca  cmp     esi, 30h ; '0'
0x140003dcd  jb      short loc_140003E05
0x140003dcf  xorps   xmm0, xmm0
0x140003dd2  movups  [rsp+1B8h+var_C8], xmm0
0x140003dda  movups  [rsp+1B8h+var_B8], xmm0
0x140003de2  movups  [rsp+1B8h+var_A8], xmm0
0x140003dea  jmp     loc_140003CF2
0x140003def  xor     edx, edx; Tag
0x140003df1  mov     rcx, rdi; P
0x140003df4  call    cs:__imp_ExFreePoolWithTag
0x140003dfb  nop     dword ptr [rax+rax+00h]
0x140003e00  jmp     loc_140003C97
0x140003e05  mov     eax, 0C000000Dh
0x140003e0a  jmp     loc_140003C99
```
