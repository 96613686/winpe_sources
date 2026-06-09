# NtWin32LiveSystemProvider::QueryTokenInformation(void *,ulong,void *,ulong,ulong *)

- ea: `0x180025ff0`
- end: `0x1800262e1`
- name: `?QueryTokenInformation@NtWin32LiveSystemProvider@@UEAAJPEAXK0KPEAK@Z`
- size: `753`
- prototype: `int(NtWin32LiveSystemProvider *__hidden this, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003424`
- `0x180025ff0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::QueryTokenInformation(
        NtWin32LiveSystemProvider *this,
        void *a2,
        unsigned int a3,
        char *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  char *v12; // rdi
  int v13; // ebx
  unsigned int v14; // ebp
  unsigned int v15; // ebp
  unsigned int v16; // ebp
  unsigned int v17; // ebp
  size_t v18; // r8
  char *v19; // rdx
  char *v20; // rcx
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // r9d
  unsigned int v24; // r10d
  unsigned int v25; // r11d
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  size_t v29; // r8
  const void *v30; // rdx
  char *v31; // rcx
  int v32; // eax
  unsigned int v33; // r8d
  unsigned int v34; // r11d
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  size_t Size; // [rsp+60h] [rbp+8h] BYREF

  v10 = 1;
  if ( !*((_QWORD *)this + 118) || !a2 )
    return v10;
  v11 = a5;
  v12 = 0;
  LODWORD(Size) = 0;
  if ( a4 )
  {
    if ( a5 )
    {
      v12 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(
                      *((_QWORD *)this + 6),
                      a5);
      if ( !v12 )
      {
        v10 = -2147024882;
        goto LABEL_52;
      }
    }
  }
  v13 = (*((__int64 (__fastcall **)(void *, _QWORD, char *, _QWORD, size_t *))this + 118))(a2, a3, v12, v11, &Size);
  if ( v13 >= 0 )
  {
    v10 = 0;
    v14 = a3 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 )
      {
        v17 = Size;
        if ( (unsigned int)Size >= 0x18 )
        {
          v32 = *(_DWORD *)v12;
          v33 = 4;
          v23 = 16 * *(_DWORD *)v12 + 4;
          if ( v23 <= (unsigned int)Size )
          {
            v24 = 8 * v32 + 4;
            if ( v24 <= (unsigned int)Size )
            {
              if ( !a4 || v24 > v11 )
                goto LABEL_17;
              v34 = 0;
              *(_DWORD *)a4 = v32;
              if ( *(_DWORD *)v12 )
              {
                do
                {
                  v35 = v33;
                  v33 += 8;
                  v36 = v34++;
                  v36 *= 2;
                  *(_DWORD *)&a4[v35] = v24 + *(_DWORD *)&v12[8 * v36 + 8] - (_DWORD)v12 - v23;
                  *(_DWORD *)&a4[v35 + 4] = *(_DWORD *)&v12[8 * v36 + 16];
                }
                while ( v34 < *(_DWORD *)v12 );
                v17 = Size;
              }
              if ( v11 <= v17 )
                goto LABEL_17;
              v18 = v17 - v23;
              goto LABEL_29;
            }
          }
        }
        goto LABEL_45;
      }
      v16 = v15 - 3;
      if ( v16 )
      {
        if ( v16 != 6 )
        {
          v17 = Size;
          if ( a4 && (_DWORD)Size && (unsigned int)Size <= v11 )
          {
            v18 = (unsigned int)Size;
            v19 = v12;
            v20 = a4;
LABEL_16:
            memcpy_0(v20, v19, v18);
LABEL_18:
            *a6 = v17;
            goto LABEL_52;
          }
LABEL_17:
          v10 = -2147024662;
          goto LABEL_18;
        }
        v17 = Size;
        v21 = 4;
        if ( (unsigned int)Size >= 4 )
        {
          v22 = *(_DWORD *)v12;
          v23 = 16 * *(_DWORD *)v12 + 4;
          if ( v23 <= (unsigned int)Size )
          {
            v24 = 8 * v22 + 4;
            if ( v24 <= (unsigned int)Size )
            {
              if ( !a4 || v24 > v11 )
                goto LABEL_17;
              v25 = 0;
              *(_DWORD *)a4 = v22;
              if ( *(_DWORD *)v12 )
              {
                do
                {
                  v26 = v21;
                  v21 += 8;
                  v27 = v25++;
                  v27 *= 2;
                  *(_DWORD *)&a4[v26] = v24 + *(_DWORD *)&v12[8 * v27 + 8] - (_DWORD)v12 - v23;
                  *(_DWORD *)&a4[v26 + 4] = *(_DWORD *)&v12[8 * v27 + 16];
                }
                while ( v25 < *(_DWORD *)v12 );
                v17 = Size;
              }
              if ( v11 < v17 )
                goto LABEL_17;
              v18 = v17 - v21;
LABEL_29:
              v19 = &v12[v23];
              v20 = &a4[v24];
              goto LABEL_16;
            }
          }
        }
        goto LABEL_45;
      }
      v28 = (unsigned int)Size;
      if ( (unsigned int)Size >= 8 )
      {
        *a6 = Size - 4;
        if ( a4 && v11 >= (int)v28 - 4 )
        {
          v29 = v28 - 8;
          v30 = v12 + 8;
          *(_DWORD *)a4 = *(_DWORD *)v12 - (_DWORD)v12;
          v31 = a4 + 4;
LABEL_49:
          memcpy_0(v31, v30, v29);
          goto LABEL_52;
        }
LABEL_50:
        v10 = -2147024662;
        goto LABEL_52;
      }
    }
    else
    {
      v37 = (unsigned int)Size;
      if ( (unsigned int)Size >= 0x10 )
      {
        *a6 = Size - 8;
        if ( a4 && v11 >= (int)v37 - 8 )
        {
          *(_DWORD *)a4 = 8;
          v29 = v37 - 16;
          v30 = v12 + 16;
          *((_DWORD *)a4 + 1) = *((_DWORD *)v12 + 2);
          v31 = a4 + 8;
          goto LABEL_49;
        }
        goto LABEL_50;
      }
    }
LABEL_45:
    v10 = -2147024883;
    goto LABEL_52;
  }
  v10 = v13 | 0x10000000;
LABEL_52:
  if ( v12 )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v12);
  return v10;
}

```

## disassembly

```asm
0x180025ff0  mov     [rsp+arg_8], rbx
0x180025ff5  mov     [rsp+arg_10], rbp
0x180025ffa  push    rsi
0x180025ffb  push    rdi
0x180025ffc  push    r13
0x180025ffe  push    r14
0x180026000  push    r15
0x180026002  sub     rsp, 30h
0x180026006  cmp     qword ptr [rcx+3B0h], 0
0x18002600e  mov     rsi, r9
0x180026011  mov     ebp, r8d
0x180026014  mov     r15, rdx
0x180026017  mov     r13, rcx
0x18002601a  mov     ebx, 1
0x18002601f  jz      loc_1800262C8
0x180026025  test    rdx, rdx
0x180026028  jz      loc_1800262C8
0x18002602e  mov     r14d, [rsp+58h+arg_20]
0x180026036  xor     edi, edi
0x180026038  mov     dword ptr [rsp+58h+Size], edi
0x18002603c  test    r9, r9
0x18002603f  jz      short loc_18002606B
0x180026041  test    r14d, r14d
0x180026044  jz      short loc_18002606B
0x180026046  mov     rcx, [rcx+30h]
0x18002604a  mov     edx, r14d
0x18002604d  mov     rax, [rcx]
0x180026050  mov     rax, [rax+8]
0x180026054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026059  mov     rdi, rax
0x18002605c  test    rax, rax
0x18002605f  jnz     short loc_18002606B
0x180026061  mov     ebx, 8007000Eh
0x180026066  jmp     loc_1800262B0
0x18002606b  lea     rax, [rsp+58h+Size]
0x180026070  mov     r9d, r14d
0x180026073  mov     [rsp+58h+var_38], rax
0x180026078  mov     r8, rdi
0x18002607b  mov     rax, [r13+3B0h]
0x180026082  mov     edx, ebp
0x180026084  mov     rcx, r15
0x180026087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002608c  mov     ebx, eax
0x18002608e  test    eax, eax
0x180026090  js      loc_1800262AC
0x180026096  xor     ebx, ebx
0x180026098  sub     ebp, 1
0x18002609b  jz      loc_18002625F
0x1800260a1  sub     ebp, 1
0x1800260a4  jz      loc_1800261CF
0x1800260aa  sub     ebp, 3
0x1800260ad  jz      loc_18002618C
0x1800260b3  cmp     ebp, 6
0x1800260b6  jz      short loc_1800260EE
0x1800260b8  mov     ebp, dword ptr [rsp+58h+Size]
0x1800260bc  test    rsi, rsi
0x1800260bf  jz      short loc_1800260DA
0x1800260c1  test    ebp, ebp
0x1800260c3  jz      short loc_1800260DA
0x1800260c5  cmp     ebp, r14d
0x1800260c8  ja      short loc_1800260DA
0x1800260ca  mov     r8d, ebp; Size
0x1800260cd  mov     rdx, rdi; Src
0x1800260d0  mov     rcx, rsi; void *
0x1800260d3  call    memcpy_0
0x1800260d8  jmp     short loc_1800260DF
0x1800260da  mov     ebx, 800700EAh
0x1800260df  mov     rax, [rsp+58h+arg_28]
0x1800260e7  mov     [rax], ebp
0x1800260e9  jmp     loc_1800262B0
0x1800260ee  mov     ebp, dword ptr [rsp+58h+Size]
0x1800260f2  mov     r8d, 4
0x1800260f8  cmp     ebp, r8d
0x1800260fb  jb      loc_180026268
0x180026101  mov     eax, [rdi]
0x180026103  mov     r9d, eax
0x180026106  shl     r9d, 4
0x18002610a  add     r9d, r8d
0x18002610d  cmp     r9d, ebp
0x180026110  ja      loc_180026268
0x180026116  lea     r10d, ds:4[rax*8]
0x18002611e  cmp     r10d, ebp
0x180026121  ja      loc_180026268
0x180026127  test    rsi, rsi
0x18002612a  jz      short loc_1800260DA
0x18002612c  cmp     r10d, r14d
0x18002612f  ja      short loc_1800260DA
0x180026131  xor     r11d, r11d
0x180026134  mov     [rsi], eax
0x180026136  cmp     [rdi], ebx
0x180026138  jbe     short loc_18002616A
0x18002613a  mov     ecx, r8d
0x18002613d  add     r8d, 8
0x180026141  mov     edx, r11d
0x180026144  inc     r11d
0x180026147  add     rdx, rdx
0x18002614a  mov     eax, [rdi+rdx*8+8]
0x18002614e  sub     eax, edi
0x180026150  sub     eax, r9d
0x180026153  add     eax, r10d
0x180026156  mov     [rcx+rsi], eax
0x180026159  mov     eax, [rdi+rdx*8+10h]
0x18002615d  mov     [rcx+rsi+4], eax
0x180026161  cmp     r11d, [rdi]
0x180026164  jb      short loc_18002613A
0x180026166  mov     ebp, dword ptr [rsp+58h+Size]
0x18002616a  cmp     r14d, ebp
0x18002616d  jb      loc_1800260DA
0x180026173  mov     eax, ebp
0x180026175  sub     eax, r8d
0x180026178  mov     r8d, eax
0x18002617b  mov     edx, r9d
0x18002617e  add     rdx, rdi
0x180026181  mov     ecx, r10d
0x180026184  add     rcx, rsi
0x180026187  jmp     loc_1800260D3
0x18002618c  mov     ecx, dword ptr [rsp+58h+Size]
0x180026190  cmp     ecx, 8
0x180026193  jb      loc_180026268
0x180026199  mov     rax, [rsp+58h+arg_28]
0x1800261a1  lea     edx, [rcx-4]
0x1800261a4  mov     [rax], edx
0x1800261a6  test    rsi, rsi
0x1800261a9  jz      loc_1800262A5
0x1800261af  cmp     r14d, edx
0x1800261b2  jb      loc_1800262A5
0x1800261b8  mov     eax, [rdi]
0x1800261ba  lea     r8, [rcx-8]
0x1800261be  sub     eax, edi
0x1800261c0  lea     rdx, [rdi+8]
0x1800261c4  mov     [rsi], eax
0x1800261c6  lea     rcx, [rsi+4]
0x1800261ca  jmp     loc_18002629E
0x1800261cf  mov     ebp, dword ptr [rsp+58h+Size]
0x1800261d3  cmp     ebp, 18h
0x1800261d6  jb      loc_180026268
0x1800261dc  mov     eax, [rdi]
0x1800261de  mov     r8d, 4
0x1800261e4  mov     r9d, eax
0x1800261e7  shl     r9d, 4
0x1800261eb  add     r9d, r8d
0x1800261ee  cmp     r9d, ebp
0x1800261f1  ja      short loc_180026268
0x1800261f3  lea     r10d, ds:4[rax*8]
0x1800261fb  cmp     r10d, ebp
0x1800261fe  ja      short loc_180026268
0x180026200  test    rsi, rsi
0x180026203  jz      loc_1800260DA
0x180026209  cmp     r10d, r14d
0x18002620c  ja      loc_1800260DA
0x180026212  xor     r11d, r11d
0x180026215  mov     [rsi], eax
0x180026217  cmp     [rdi], ebx
0x180026219  jbe     short loc_18002624B
0x18002621b  mov     ecx, r8d
0x18002621e  add     r8d, 8
0x180026222  mov     edx, r11d
0x180026225  inc     r11d
0x180026228  add     rdx, rdx
0x18002622b  mov     eax, [rdi+rdx*8+8]
0x18002622f  sub     eax, edi
0x180026231  sub     eax, r9d
0x180026234  add     eax, r10d
0x180026237  mov     [rcx+rsi], eax
0x18002623a  mov     eax, [rdi+rdx*8+10h]
0x18002623e  mov     [rcx+rsi+4], eax
0x180026242  cmp     r11d, [rdi]
0x180026245  jb      short loc_18002621B
0x180026247  mov     ebp, dword ptr [rsp+58h+Size]
0x18002624b  cmp     r14d, ebp
0x18002624e  jbe     loc_1800260DA
0x180026254  mov     r8d, ebp
0x180026257  sub     r8d, r9d
0x18002625a  jmp     loc_18002617B
0x18002625f  mov     ecx, dword ptr [rsp+58h+Size]
0x180026263  cmp     ecx, 10h
0x180026266  jnb     short loc_18002626F
0x180026268  mov     ebx, 8007000Dh
0x18002626d  jmp     short loc_1800262B0
0x18002626f  mov     rax, [rsp+58h+arg_28]
0x180026277  lea     edx, [rcx-8]
0x18002627a  mov     [rax], edx
0x18002627c  test    rsi, rsi
0x18002627f  jz      short loc_1800262A5
0x180026281  cmp     r14d, edx
0x180026284  jb      short loc_1800262A5
0x180026286  mov     dword ptr [rsi], 8
0x18002628c  lea     r8, [rcx-10h]; Size
0x180026290  mov     eax, [rdi+8]
0x180026293  lea     rdx, [rdi+10h]; Src
0x180026297  mov     [rsi+4], eax
0x18002629a  lea     rcx, [rsi+8]; void *
0x18002629e  call    memcpy_0
0x1800262a3  jmp     short loc_1800262B0
0x1800262a5  mov     ebx, 800700EAh
0x1800262aa  jmp     short loc_1800262B0
0x1800262ac  bts     ebx, 1Ch
0x1800262b0  test    rdi, rdi
0x1800262b3  jz      short loc_1800262C8
0x1800262b5  mov     rcx, [r13+30h]
0x1800262b9  mov     rdx, rdi
0x1800262bc  mov     r8, [rcx]
0x1800262bf  mov     rax, [r8+18h]
0x1800262c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262c8  mov     rbp, [rsp+58h+arg_10]
0x1800262cd  mov     eax, ebx
0x1800262cf  mov     rbx, [rsp+58h+arg_8]
0x1800262d4  add     rsp, 30h
0x1800262d8  pop     r15
0x1800262da  pop     r14
0x1800262dc  pop     r13
0x1800262de  pop     rdi
0x1800262df  pop     rsi
0x1800262e0  retn
```
