# CWriterGlobalHelper::EscapeString(ushort const *,ulong,int *,ushort * *,ulong *)

- ea: `0x18002c2d4`
- end: `0x18002c5fe`
- name: `?EscapeString@CWriterGlobalHelper@@QEAAJPEBGKPEAHPEAPEAGPEAK@Z`
- size: `810`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, const unsigned __int16 *, unsigned int, int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002d934`

## callees

- `0x18002c2d4`
- `0x18002cb9c`
- `0x18002d730`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002c57b`
- `ole32!CoTaskMemFree` at `0x18002c5e5`
- `ole32!CoTaskMemFree` at `0x18002c57b`
- `ole32!CoTaskMemFree` at `0x18002c5e5`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::EscapeString(
        CWriterGlobalHelper *this,
        unsigned __int16 *a2,
        __int64 a3,
        int *a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  int v6; // r10d
  unsigned __int16 *v7; // r11
  int v8; // edi
  unsigned int v10; // r15d
  __int64 i; // rbx
  int EscapeType; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // ebp
  __int64 result; // rax
  __int64 v22; // rcx
  __int64 v23; // rsi
  unsigned __int16 *v24; // r8
  __int64 v25; // r9
  int v26; // eax
  __int16 v27; // dx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  bool v35; // sf
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // r9
  __int64 v39; // rax
  unsigned __int16 **v40; // rcx
  unsigned int *v41; // rax
  unsigned __int16 *v42; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v42 = 0;
  v10 = a3;
  for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
  {
    EscapeType = CWriterGlobalHelper::GetEscapeType(this, a2[i], a3, a4);
    if ( EscapeType )
    {
      v14 = EscapeType - 1;
      if ( v14 && (v15 = v14 - 1) != 0 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              if ( v18 != 1 )
                return (unsigned int)-2147024883;
              v6 += 8;
            }
            else
            {
              v6 += 7;
            }
          }
          else
          {
            v6 += 4;
          }
        }
        else
        {
          v6 += 5;
        }
      }
      else
      {
        v6 += 3;
      }
      v8 = 1;
    }
  }
  if ( v8 )
  {
    v20 = v6 + a3;
    result = NewString(v6 + (int)a3, &v42);
    v19 = result;
    if ( (int)result >= 0 )
    {
      v7 = v42;
      v23 = 0;
      v24 = v42;
      v25 = v20;
      while ( 1 )
      {
        if ( (unsigned int)v23 >= v10 )
        {
          v40 = a5;
          *v24 = 0;
          if ( v40 )
          {
            v41 = a6;
            if ( a6 )
            {
              *v40 = v7;
              v7 = 0;
              *v41 = v20;
            }
          }
          goto LABEL_60;
        }
        v26 = CWriterGlobalHelper::GetEscapeType(v22, a2[v23], v24, v25);
        if ( v26 )
        {
          v30 = v26 - 1;
          if ( !v30 )
          {
            v25 = v29 - 4;
            if ( v25 < 0 )
              goto LABEL_55;
            v39 = 0x3B007400670026LL;
            goto LABEL_48;
          }
          v31 = v30 - 1;
          if ( !v31 )
          {
            v25 = v29 - 4;
            if ( v25 < 0 )
              goto LABEL_55;
            v39 = 0x3B0074006C0026LL;
LABEL_48:
            *(_QWORD *)v28 = v39;
            v24 = (unsigned __int16 *)(v28 + 8);
            goto LABEL_51;
          }
          v32 = v31 - 1;
          if ( v32 )
          {
            v33 = v32 - 1;
            if ( v33 )
            {
              v34 = v33 - 1;
              if ( v34 )
              {
                if ( v34 != 1 )
                {
                  if ( v7 )
                  {
                    CoTaskMemFree(v7);
                    v7 = 0;
                  }
                  v19 = -2147024883;
                  goto LABEL_62;
                }
                if ( v29 - 3 < 0 )
                  goto LABEL_55;
                *(_DWORD *)v28 = 2293798;
                *(_WORD *)(v28 + 4) = 120;
                if ( v29 - 4 < 0 )
                  goto LABEL_55;
                v35 = v29 - 6 < 0;
                v36 = v29 - 6;
                *(_WORD *)(v28 + 6) = 49;
                if ( v35 )
                  goto LABEL_55;
                v35 = v36 - 2 < 0;
                v37 = v36 - 2;
                *(_DWORD *)(v28 + 8) = *(_DWORD *)off_180031F60[HIBYTE(a2[v23])];
                if ( v35 )
                  goto LABEL_55;
                v25 = v37 - 1;
                v22 = *(unsigned int *)off_180031F60[LOBYTE(a2[v23])];
                *(_DWORD *)(v28 + 12) = v22;
                if ( v25 < 0 )
                  goto LABEL_55;
                *(_WORD *)(v28 + 16) = 59;
                v24 = (unsigned __int16 *)(v28 + 18);
              }
              else
              {
                if ( v29 - 3 < 0 )
                  goto LABEL_55;
                *(_DWORD *)v28 = 2293798;
                *(_WORD *)(v28 + 4) = 120;
                if ( v29 - 5 < 0
                  || (v35 = v29 - 7 < 0,
                      v38 = v29 - 7,
                      *(_DWORD *)(v28 + 6) = *(_DWORD *)off_180031F60[HIBYTE(a2[v23])],
                      v35)
                  || (v25 = v38 - 1,
                      v22 = *(unsigned int *)off_180031F60[LOBYTE(a2[v23])],
                      *(_DWORD *)(v28 + 10) = v22,
                      v25 < 0) )
                {
LABEL_55:
                  v19 = -2147024774;
                  goto LABEL_62;
                }
                *(_WORD *)(v28 + 14) = 59;
                v24 = (unsigned __int16 *)(v28 + 16);
              }
            }
            else
            {
              v25 = v29 - 5;
              if ( v25 < 0 )
                goto LABEL_55;
              *(_QWORD *)v28 = 0x70006D00610026LL;
              *(_WORD *)(v28 + 8) = 59;
              v24 = (unsigned __int16 *)(v28 + 10);
            }
          }
          else
          {
            v25 = v29 - 6;
            if ( v25 < 0 )
              goto LABEL_55;
            *(_QWORD *)v28 = 0x6F007500710026LL;
            *(_DWORD *)(v28 + 8) = 3866740;
            v24 = (unsigned __int16 *)(v28 + 12);
          }
        }
        else
        {
          v25 = v29 - 1;
          if ( v25 < 0 )
            goto LABEL_55;
          *(_WORD *)v28 = v27;
          v24 = (unsigned __int16 *)(v28 + 2);
        }
LABEL_51:
        v23 = (unsigned int)(v23 + 1);
      }
    }
  }
  else
  {
    v19 = 0;
    *a5 = a2;
    *a6 = v10;
LABEL_60:
    if ( a4 )
      *a4 = v8;
LABEL_62:
    if ( v7 )
      CoTaskMemFree(v7);
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x18002c2d4  mov     [rsp+arg_0], rcx
0x18002c2d9  push    rbx
0x18002c2da  push    rbp
0x18002c2db  push    rsi
0x18002c2dc  push    rdi
0x18002c2dd  push    r12
0x18002c2df  push    r13
0x18002c2e1  push    r14
0x18002c2e3  push    r15
0x18002c2e5  sub     rsp, 28h
0x18002c2e9  xor     r10d, r10d
0x18002c2ec  xor     r11d, r11d
0x18002c2ef  xor     edi, edi
0x18002c2f1  mov     [rsp+68h+arg_0], r11
0x18002c2f6  mov     r12, r9
0x18002c2f9  mov     r15d, r8d
0x18002c2fc  mov     r14, rdx
0x18002c2ff  xor     ebx, ebx
0x18002c301  lea     r13d, [r10+1]
0x18002c305  cmp     ebx, r15d
0x18002c308  jnb     short loc_18002C364
0x18002c30a  movzx   edx, word ptr [r14+rbx*2]
0x18002c30f  call    ?GetEscapeType@CWriterGlobalHelper@@AEAA?AW4eESCAPE@@G@Z; CWriterGlobalHelper::GetEscapeType(ushort)
0x18002c314  test    eax, eax
0x18002c316  jz      short loc_18002C355
0x18002c318  sub     eax, r13d
0x18002c31b  jz      short loc_18002C34E
0x18002c31d  sub     eax, r13d
0x18002c320  jz      short loc_18002C34E
0x18002c322  sub     eax, r13d
0x18002c325  jz      short loc_18002C348
0x18002c327  sub     eax, r13d
0x18002c32a  jz      short loc_18002C342
0x18002c32c  sub     eax, r13d
0x18002c32f  jz      short loc_18002C33C
0x18002c331  cmp     eax, r13d
0x18002c334  jnz     short loc_18002C35A
0x18002c336  add     r10d, 8
0x18002c33a  jmp     short loc_18002C352
0x18002c33c  add     r10d, 7
0x18002c340  jmp     short loc_18002C352
0x18002c342  add     r10d, 4
0x18002c346  jmp     short loc_18002C352
0x18002c348  add     r10d, 5
0x18002c34c  jmp     short loc_18002C352
0x18002c34e  add     r10d, 3
0x18002c352  mov     edi, r13d
0x18002c355  add     ebx, r13d
0x18002c358  jmp     short loc_18002C305
0x18002c35a  mov     ebx, 8007000Dh
0x18002c35f  jmp     loc_18002C5EB
0x18002c364  test    edi, edi
0x18002c366  jz      loc_18002C5BC
0x18002c36c  lea     ebp, [r10+r8]
0x18002c370  mov     ecx, ebp; unsigned int
0x18002c372  lea     rdx, [rsp+68h+arg_0]; unsigned __int16 **
0x18002c377  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002c37c  mov     ebx, eax
0x18002c37e  test    eax, eax
0x18002c380  js      loc_18002C5ED
0x18002c386  mov     r11, [rsp+68h+arg_0]
0x18002c38b  xor     esi, esi
0x18002c38d  mov     r8, r11
0x18002c390  mov     r9d, ebp
0x18002c393  cmp     esi, r15d
0x18002c396  jnb     loc_18002C592
0x18002c39c  movzx   edx, word ptr [r14+rsi*2]
0x18002c3a1  call    ?GetEscapeType@CWriterGlobalHelper@@AEAA?AW4eESCAPE@@G@Z; CWriterGlobalHelper::GetEscapeType(ushort)
0x18002c3a6  test    eax, eax
0x18002c3a8  jz      loc_18002C55E
0x18002c3ae  sub     eax, r13d
0x18002c3b1  jz      loc_18002C545
0x18002c3b7  sub     eax, r13d
0x18002c3ba  jz      loc_18002C533
0x18002c3c0  sub     eax, r13d
0x18002c3c3  jz      loc_18002C510
0x18002c3c9  sub     eax, r13d
0x18002c3cc  jz      loc_18002C4E7
0x18002c3d2  sub     eax, r13d
0x18002c3d5  jz      loc_18002C46E
0x18002c3db  cmp     eax, r13d
0x18002c3de  jnz     loc_18002C573
0x18002c3e4  lea     rax, [r9-3]
0x18002c3e8  test    rax, rax
0x18002c3eb  js      loc_18002C58B
0x18002c3f1  mov     rax, cs:qword_18003D9F0
0x18002c3f8  mov     [r8], eax
0x18002c3fb  movzx   eax, word ptr cs:qword_18003D9F0+4
0x18002c402  mov     [r8+4], ax
0x18002c407  lea     rax, [r9-4]
0x18002c40b  test    rax, rax
0x18002c40e  js      loc_18002C58B
0x18002c414  add     r9, 0FFFFFFFFFFFFFFFAh
0x18002c418  mov     word ptr [r8+6], 31h ; '1'
0x18002c41f  js      loc_18002C58B
0x18002c425  add     r9, 0FFFFFFFFFFFFFFFEh
0x18002c429  movzx   eax, byte ptr [r14+rsi*2+1]
0x18002c42f  lea     rdx, off_180031F60; "00"
0x18002c436  mov     rax, [rdx+rax*8]
0x18002c43a  mov     ecx, [rax]
0x18002c43c  mov     [r8+8], ecx
0x18002c440  js      loc_18002C58B
0x18002c446  sub     r9, r13
0x18002c449  movzx   eax, byte ptr [r14+rsi*2]
0x18002c44e  mov     rax, [rdx+rax*8]
0x18002c452  mov     ecx, [rax]
0x18002c454  mov     [r8+0Ch], ecx
0x18002c458  js      loc_18002C58B
0x18002c45e  mov     word ptr [r8+10h], 3Bh ; ';'
0x18002c465  add     r8, 12h
0x18002c469  jmp     loc_18002C56B
0x18002c46e  lea     rax, [r9-3]
0x18002c472  test    rax, rax
0x18002c475  js      loc_18002C58B
0x18002c47b  mov     rax, cs:qword_18003D9F0
0x18002c482  mov     [r8], eax
0x18002c485  movzx   eax, word ptr cs:qword_18003D9F0+4
0x18002c48c  mov     [r8+4], ax
0x18002c491  lea     rax, [r9-5]
0x18002c495  test    rax, rax
0x18002c498  js      loc_18002C58B
0x18002c49e  add     r9, 0FFFFFFFFFFFFFFF9h
0x18002c4a2  movzx   eax, byte ptr [r14+rsi*2+1]
0x18002c4a8  lea     rdx, off_180031F60; "00"
0x18002c4af  mov     rax, [rdx+rax*8]
0x18002c4b3  mov     ecx, [rax]
0x18002c4b5  mov     [r8+6], ecx
0x18002c4b9  js      loc_18002C58B
0x18002c4bf  sub     r9, r13
0x18002c4c2  movzx   eax, byte ptr [r14+rsi*2]
0x18002c4c7  mov     rax, [rdx+rax*8]
0x18002c4cb  mov     ecx, [rax]
0x18002c4cd  mov     [r8+0Ah], ecx
0x18002c4d1  js      loc_18002C58B
0x18002c4d7  mov     word ptr [r8+0Eh], 3Bh ; ';'
0x18002c4de  add     r8, 10h
0x18002c4e2  jmp     loc_18002C56B
0x18002c4e7  add     r9, 0FFFFFFFFFFFFFFFBh
0x18002c4eb  js      loc_18002C58B
0x18002c4f1  movsd   xmm0, cs:qword_18003D9F8
0x18002c4f9  movsd   qword ptr [r8], xmm0
0x18002c4fe  movzx   eax, cs:word_18003DA00
0x18002c505  mov     [r8+8], ax
0x18002c50a  add     r8, 0Ah
0x18002c50e  jmp     short loc_18002C56B
0x18002c510  add     r9, 0FFFFFFFFFFFFFFFAh
0x18002c514  js      short loc_18002C58B
0x18002c516  movsd   xmm0, cs:qword_18003DA08
0x18002c51e  movsd   qword ptr [r8], xmm0
0x18002c523  mov     eax, cs:dword_18003DA10
0x18002c529  mov     [r8+8], eax
0x18002c52d  add     r8, 0Ch
0x18002c531  jmp     short loc_18002C56B
0x18002c533  add     r9, 0FFFFFFFFFFFFFFFCh
0x18002c537  js      short loc_18002C58B
0x18002c539  mov     rax, 3B0074006C0026h
0x18002c543  jmp     short loc_18002C555
0x18002c545  add     r9, 0FFFFFFFFFFFFFFFCh
0x18002c549  js      short loc_18002C58B
0x18002c54b  mov     rax, 3B007400670026h
0x18002c555  mov     [r8], rax
0x18002c558  add     r8, 8
0x18002c55c  jmp     short loc_18002C56B
0x18002c55e  sub     r9, r13
0x18002c561  js      short loc_18002C58B
0x18002c563  mov     [r8], dx
0x18002c567  add     r8, 2
0x18002c56b  add     esi, r13d
0x18002c56e  jmp     loc_18002C393
0x18002c573  test    r11, r11
0x18002c576  jz      short loc_18002C584
0x18002c578  mov     rcx, r11; pv
0x18002c57b  call    cs:__imp_CoTaskMemFree
0x18002c581  xor     r11d, r11d
0x18002c584  mov     ebx, 8007000Dh
0x18002c589  jmp     short loc_18002C5DD
0x18002c58b  mov     ebx, 8007007Ah
0x18002c590  jmp     short loc_18002C5DD
0x18002c592  mov     rcx, [rsp+68h+arg_20]
0x18002c59a  xor     eax, eax
0x18002c59c  mov     [r8], ax
0x18002c5a0  test    rcx, rcx
0x18002c5a3  jz      short loc_18002C5D4
0x18002c5a5  mov     rax, [rsp+68h+arg_28]
0x18002c5ad  test    rax, rax
0x18002c5b0  jz      short loc_18002C5D4
0x18002c5b2  mov     [rcx], r11
0x18002c5b5  xor     r11d, r11d
0x18002c5b8  mov     [rax], ebp
0x18002c5ba  jmp     short loc_18002C5D4
0x18002c5bc  mov     rax, [rsp+68h+arg_20]
0x18002c5c4  xor     ebx, ebx
0x18002c5c6  mov     [rax], r14
0x18002c5c9  mov     rax, [rsp+68h+arg_28]
0x18002c5d1  mov     [rax], r15d
0x18002c5d4  test    r12, r12
0x18002c5d7  jz      short loc_18002C5DD
0x18002c5d9  mov     [r12], edi
0x18002c5dd  test    r11, r11
0x18002c5e0  jz      short loc_18002C5EB
0x18002c5e2  mov     rcx, r11; pv
0x18002c5e5  call    cs:__imp_CoTaskMemFree
0x18002c5eb  mov     eax, ebx
0x18002c5ed  add     rsp, 28h
0x18002c5f1  pop     r15
0x18002c5f3  pop     r14
0x18002c5f5  pop     r13
0x18002c5f7  pop     r12
0x18002c5f9  pop     rdi
0x18002c5fa  pop     rsi
0x18002c5fb  pop     rbp
0x18002c5fc  pop     rbx
0x18002c5fd  retn
```
