# JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)

- ea: `0x180006934`
- end: `0x180006c39`
- name: `?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z`
- size: `773`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005a6c`
- `0x180005ef4`

## callees

- `0x1800027d6`
- `0x180006934`
- `0x180007f8c`
- `0x1800191f0`

## import_xrefs

- `msvcrt!_wtoi` at `0x180006bac`
- `msvcrt!_wtoi` at `0x180006bac`
- `KERNEL32!HeapAlloc` at `0x180006bfa`
- `KERNEL32!HeapAlloc` at `0x180006bfa`
- `KERNEL32!GetProcessHeap` at `0x180006972`
- `KERNEL32!GetProcessHeap` at `0x1800069d2`
- `KERNEL32!GetProcessHeap` at `0x180006beb`
- `KERNEL32!GetProcessHeap` at `0x180006972`
- `KERNEL32!GetProcessHeap` at `0x1800069d2`
- `KERNEL32!GetProcessHeap` at `0x180006beb`
- `KERNEL32!HeapFree` at `0x1800069cc`
- `KERNEL32!HeapFree` at `0x180006a24`
- `KERNEL32!HeapFree` at `0x1800069cc`
- `KERNEL32!HeapFree` at `0x180006a24`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
        JsonHelpersInternal::JsonReader *this,
        const unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v5; // r10
  __int64 v6; // r8
  __int16 v7; // r9
  void *v8; // r8
  __int64 v9; // rcx
  __int16 v10; // dx
  int v11; // ebx
  unsigned __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  wchar_t v28; // r8
  wchar_t v29; // r8
  wchar_t v30; // r8
  wchar_t v31; // cx
  __int16 v32; // ax
  size_t v33; // rdi
  HANDLE v34; // rax
  unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rbx
  __int16 v37; // [rsp+20h] [rbp-60h] BYREF
  HANDLE hHeap[4]; // [rsp+28h] [rbp-58h] BYREF
  LPVOID lpMem[2]; // [rsp+48h] [rbp-38h]
  wchar_t String[8]; // [rsp+58h] [rbp-28h] BYREF

  memset(hHeap, 0, sizeof(hHeap));
  ProcessHeap = GetProcessHeap();
  v5 = *((_QWORD *)this + 1);
  while ( 1 )
  {
    v6 = *(_QWORD *)this;
    v7 = *(_WORD *)(v5 + 2LL * *(_QWORD *)this);
    if ( v7 != 9
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v6 + 1;
    if ( !v7 )
      *(_QWORD *)this = v6;
  }
  v8 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v8 )
    HeapFree(ProcessHeap, 0, v8);
  hHeap[3] = (HANDLE)4096;
  hHeap[0] = GetProcessHeap();
  *(_OWORD *)&hHeap[1] = 0;
  *(_OWORD *)lpMem = 0;
  v9 = *(_QWORD *)this;
  v10 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
  if ( v10 )
  {
    if ( v10 != 34 )
      goto LABEL_12;
    while ( 1 )
    {
      v13 = *(_QWORD *)this;
      v14 = *((_QWORD *)this + 1);
      v15 = *(_QWORD *)this + 1LL;
      v16 = *(unsigned __int16 *)(v14 + 2LL * *(_QWORD *)this);
      *(_QWORD *)this = v15;
      if ( (_WORD)v16 )
        v13 = v15;
      else
        *(_QWORD *)this = v13;
      v37 = v16;
      if ( !v16 )
        goto LABEL_12;
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_12;
      v18 = v17 - 33;
      if ( !v18 )
      {
        v33 = (size_t)hHeap[1];
        v34 = GetProcessHeap();
        v35 = (unsigned __int16 *)HeapAlloc(v34, 0, v33 + 2);
        v36 = v35;
        if ( v35 )
        {
          if ( v33 )
            memcpy_0(v35, lpMem[1], v33);
          v36[v33 >> 1] = 0;
          *a2 = v36;
          v11 = 0;
        }
        else
        {
          v11 = -2147024882;
        }
        goto LABEL_13;
      }
      if ( v18 == 58 )
      {
        v19 = *(unsigned __int16 *)(v14 + 2 * v13);
        v15 = v13 + 1;
        *(_QWORD *)this = v13 + 1;
        if ( (_WORD)v19 )
          ++v13;
        else
          *(_QWORD *)this = v13;
        v37 = v19;
        v20 = v19 - 34;
        if ( v20 )
        {
          v21 = v20 - 13;
          if ( v21 )
          {
            v22 = v21 - 45;
            if ( v22 )
            {
              v23 = v22 - 6;
              if ( !v23 )
              {
                v37 = 8;
                goto LABEL_24;
              }
              v24 = v23 - 4;
              if ( !v24 )
              {
                v32 = 12;
                goto LABEL_54;
              }
              v25 = v24 - 8;
              if ( !v25 )
              {
                v32 = 10;
LABEL_54:
                v37 = v32;
                goto LABEL_24;
              }
              v26 = v25 - 4;
              if ( v26 )
              {
                v27 = v26 - 2;
                if ( v27 )
                {
                  if ( v27 != 1 )
                    goto LABEL_12;
                  v28 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v28 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[0] = v28;
                  v29 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v29 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[1] = v29;
                  v30 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v30 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[2] = v30;
                  v31 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( !v31 )
                    *(_QWORD *)this = v13;
                  String[3] = v31;
                  String[4] = 0;
                  v32 = _wtoi(String);
                  goto LABEL_54;
                }
                v37 = 9;
              }
              else
              {
                v37 = 13;
              }
            }
          }
        }
      }
LABEL_24:
      v11 = RtlMemoryStream::Write((RtlMemoryStream *)hHeap, &v37, v15);
      if ( v11 < 0 )
        goto LABEL_13;
    }
  }
  *(_QWORD *)this = v9;
LABEL_12:
  v11 = -2147024883;
LABEL_13:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006934  mov     [rsp-38h+arg_10], rbx
0x180006939  push    rbp
0x18000693a  push    rsi
0x18000693b  push    rdi
0x18000693c  push    r12
0x18000693e  push    r13
0x180006940  push    r14
0x180006942  push    r15
0x180006944  mov     rbp, rsp
0x180006947  sub     rsp, 80h
0x18000694e  movaps  [rsp+80h+var_10], xmm6
0x180006953  mov     rax, cs:__security_cookie
0x18000695a  xor     rax, rsp
0x18000695d  mov     [rbp+var_18], rax
0x180006961  xorps   xmm6, xmm6
0x180006964  mov     rsi, rdx
0x180006967  movups  xmmword ptr [rbp+hHeap], xmm6
0x18000696b  mov     rdi, rcx
0x18000696e  movups  [rbp+var_48], xmm6
0x180006972  call    cs:__imp_GetProcessHeap
0x180006978  mov     r10, [rdi+8]
0x18000697c  mov     r13d, 9
0x180006982  mov     r11, rax
0x180006985  mov     r8, [rdi]
0x180006988  movzx   r9d, word ptr [r10+r8*2]
0x18000698d  mov     edx, r9d
0x180006990  sub     edx, r13d
0x180006993  jz      short loc_1800069A4
0x180006995  sub     edx, 1
0x180006998  jz      short loc_1800069A4
0x18000699a  sub     edx, 3
0x18000699d  jz      short loc_1800069A4
0x18000699f  cmp     edx, 13h
0x1800069a2  jnz     short loc_1800069B8
0x1800069a4  lea     rax, [r8+1]
0x1800069a8  mov     [rdi], rax
0x1800069ab  xor     eax, eax
0x1800069ad  cmp     ax, r9w
0x1800069b1  jnz     short loc_180006985
0x1800069b3  mov     [rdi], r8
0x1800069b6  jmp     short loc_180006985
0x1800069b8  psrldq  xmm6, 8
0x1800069bd  movq    r8, xmm6; lpMem
0x1800069c2  test    r8, r8
0x1800069c5  jz      short loc_1800069D2
0x1800069c7  xor     edx, edx; dwFlags
0x1800069c9  mov     rcx, r11; hHeap
0x1800069cc  call    cs:__imp_HeapFree
0x1800069d2  call    cs:__imp_GetProcessHeap
0x1800069d8  xorps   xmm0, xmm0
0x1800069db  mov     qword ptr [rbp+var_48+8], 1000h
0x1800069e3  xorps   xmm1, xmm1
0x1800069e6  mov     [rbp+hHeap], rax
0x1800069ea  movdqu  xmmword ptr [rbp+hHeap+8], xmm0
0x1800069ef  movdqu  xmmword ptr [rbp+lpMem], xmm1
0x1800069f4  mov     rcx, [rdi]
0x1800069f7  mov     rax, [rdi+8]
0x1800069fb  movzx   edx, word ptr [rax+rcx*2]
0x1800069ff  lea     rax, [rcx+1]
0x180006a03  mov     [rdi], rax
0x180006a06  xor     eax, eax
0x180006a08  cmp     ax, dx
0x180006a0b  jnz     short loc_180006A58
0x180006a0d  mov     [rdi], rcx
0x180006a10  mov     ebx, 8007000Dh
0x180006a15  mov     r8, [rbp+lpMem+8]; lpMem
0x180006a19  test    r8, r8
0x180006a1c  jz      short loc_180006A2A
0x180006a1e  mov     rcx, [rbp+hHeap]; hHeap
0x180006a22  xor     edx, edx; dwFlags
0x180006a24  call    cs:__imp_HeapFree
0x180006a2a  mov     eax, ebx
0x180006a2c  mov     rcx, [rbp+var_18]
0x180006a30  xor     rcx, rsp; StackCookie
0x180006a33  call    __security_check_cookie
0x180006a38  mov     rbx, [rsp+80h+arg_10]
0x180006a40  movaps  xmm6, [rsp+80h+var_10]
0x180006a45  add     rsp, 80h
0x180006a4c  pop     r15
0x180006a4e  pop     r14
0x180006a50  pop     r13
0x180006a52  pop     r12
0x180006a54  pop     rdi
0x180006a55  pop     rsi
0x180006a56  pop     rbp
0x180006a57  retn
0x180006a58  mov     r12d, 22h ; '"'
0x180006a5e  cmp     r12w, dx
0x180006a62  jnz     short loc_180006A10
0x180006a64  lea     r14d, [r12-15h]
0x180006a69  lea     r15d, [r12-1Ah]
0x180006a6e  mov     rdx, [rdi]
0x180006a71  xor     eax, eax
0x180006a73  mov     r9, [rdi+8]
0x180006a77  lea     r8, [rdx+1]; unsigned __int64
0x180006a7b  movzx   ecx, word ptr [r9+rdx*2]
0x180006a80  mov     [rdi], r8
0x180006a83  cmp     ax, cx
0x180006a86  jnz     short loc_180006A8D
0x180006a88  mov     [rdi], rdx
0x180006a8b  jmp     short loc_180006A90
0x180006a8d  mov     rdx, r8
0x180006a90  mov     [rbp+var_60], cx
0x180006a94  test    ecx, ecx
0x180006a96  jz      loc_180006A10
0x180006a9c  sub     ecx, 1
0x180006a9f  jz      loc_180006A10
0x180006aa5  sub     ecx, 21h ; '!'
0x180006aa8  jz      loc_180006BE7
0x180006aae  cmp     ecx, 3Ah ; ':'
0x180006ab1  jz      short loc_180006ACB
0x180006ab3  lea     rdx, [rbp+var_60]; void *
0x180006ab7  lea     rcx, [rbp+hHeap]; this
0x180006abb  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x180006ac0  mov     ebx, eax
0x180006ac2  test    eax, eax
0x180006ac4  jns     short loc_180006A6E
0x180006ac6  jmp     loc_180006A15
0x180006acb  movzx   ecx, word ptr [r9+rdx*2]
0x180006ad0  lea     r8, [rdx+1]
0x180006ad4  mov     [rdi], r8
0x180006ad7  cmp     ax, cx
0x180006ada  jnz     short loc_180006AE1
0x180006adc  mov     [rdi], rdx
0x180006adf  jmp     short loc_180006AE4
0x180006ae1  mov     rdx, r8
0x180006ae4  mov     [rbp+var_60], cx
0x180006ae8  sub     ecx, r12d
0x180006aeb  jz      short loc_180006AB3
0x180006aed  sub     ecx, r14d
0x180006af0  jz      short loc_180006AB3
0x180006af2  sub     ecx, 2Dh ; '-'
0x180006af5  jz      short loc_180006AB3
0x180006af7  sub     ecx, 6
0x180006afa  jz      loc_180006BDD
0x180006b00  sub     ecx, 4
0x180006b03  jz      loc_180006BCF
0x180006b09  sub     ecx, r15d
0x180006b0c  jz      loc_180006BC8
0x180006b12  sub     ecx, 4
0x180006b15  jz      loc_180006BBE
0x180006b1b  sub     ecx, 2
0x180006b1e  jz      loc_180006BB4
0x180006b24  cmp     ecx, 1
0x180006b27  jnz     loc_180006A10
0x180006b2d  movzx   r8d, word ptr [r9+rdx*2]
0x180006b32  lea     rcx, [rdx+1]
0x180006b36  mov     [rdi], rcx
0x180006b39  cmp     ax, r8w
0x180006b3d  jnz     short loc_180006B44
0x180006b3f  mov     [rdi], rdx
0x180006b42  jmp     short loc_180006B47
0x180006b44  mov     rdx, rcx
0x180006b47  mov     [rbp+String], r8w
0x180006b4c  lea     rcx, [rdx+1]
0x180006b50  movzx   r8d, word ptr [r9+rdx*2]
0x180006b55  mov     [rdi], rcx
0x180006b58  cmp     ax, r8w
0x180006b5c  jnz     short loc_180006B63
0x180006b5e  mov     [rdi], rdx
0x180006b61  jmp     short loc_180006B66
0x180006b63  mov     rdx, rcx
0x180006b66  mov     [rbp+var_26], r8w
0x180006b6b  lea     rcx, [rdx+1]
0x180006b6f  movzx   r8d, word ptr [r9+rdx*2]
0x180006b74  mov     [rdi], rcx
0x180006b77  cmp     ax, r8w
0x180006b7b  jnz     short loc_180006B82
0x180006b7d  mov     [rdi], rdx
0x180006b80  jmp     short loc_180006B85
0x180006b82  mov     rdx, rcx
0x180006b85  lea     rax, [rdx+1]
0x180006b89  mov     [rbp+var_24], r8w
0x180006b8e  movzx   ecx, word ptr [r9+rdx*2]
0x180006b93  mov     [rdi], rax
0x180006b96  xor     eax, eax
0x180006b98  cmp     ax, cx
0x180006b9b  jnz     short loc_180006BA0
0x180006b9d  mov     [rdi], rdx
0x180006ba0  mov     [rbp+var_22], cx
0x180006ba4  lea     rcx, [rbp+String]; String
0x180006ba8  mov     [rbp+var_20], ax
0x180006bac  call    cs:__imp__wtoi
0x180006bb2  jmp     short loc_180006BD4
0x180006bb4  mov     [rbp+var_60], r13w
0x180006bb9  jmp     loc_180006AB3
0x180006bbe  mov     [rbp+var_60], r14w
0x180006bc3  jmp     loc_180006AB3
0x180006bc8  mov     eax, 0Ah
0x180006bcd  jmp     short loc_180006BD4
0x180006bcf  mov     eax, 0Ch
0x180006bd4  mov     [rbp+var_60], ax
0x180006bd8  jmp     loc_180006AB3
0x180006bdd  mov     [rbp+var_60], r15w
0x180006be2  jmp     loc_180006AB3
0x180006be7  mov     rdi, [rbp+hHeap+8]
0x180006beb  call    cs:__imp_GetProcessHeap
0x180006bf1  lea     r8, [rdi+2]; dwBytes
0x180006bf5  xor     edx, edx; dwFlags
0x180006bf7  mov     rcx, rax; hHeap
0x180006bfa  call    cs:__imp_HeapAlloc
0x180006c00  mov     rbx, rax
0x180006c03  test    rax, rax
0x180006c06  jnz     short loc_180006C12
0x180006c08  mov     ebx, 8007000Eh
0x180006c0d  jmp     loc_180006A15
0x180006c12  test    rdi, rdi
0x180006c15  jz      short loc_180006C26
0x180006c17  mov     rdx, [rbp+lpMem+8]; Src
0x180006c1b  mov     r8, rdi; Size
0x180006c1e  mov     rcx, rbx; void *
0x180006c21  call    memcpy_0
0x180006c26  shr     rdi, 1
0x180006c29  xor     eax, eax
0x180006c2b  mov     [rbx+rdi*2], ax
0x180006c2f  mov     [rsi], rbx
0x180006c32  xor     ebx, ebx
0x180006c34  jmp     loc_180006A15
```
