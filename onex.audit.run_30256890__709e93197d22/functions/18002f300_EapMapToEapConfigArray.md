# EapMapToEapConfigArray

- ea: `0x18002f300`
- end: `0x18002f644`
- name: `EapMapToEapConfigArray`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002ef1c`

## callees

- `0x18002f23c`
- `0x18002f300`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18002f34f`
- `MobileNetworking!AllocateMemory` at `0x18002f513`
- `MobileNetworking!AllocateMemory` at `0x18002f5b0`
- `MobileNetworking!AllocateMemory` at `0x18002f34f`
- `MobileNetworking!AllocateMemory` at `0x18002f513`
- `MobileNetworking!AllocateMemory` at `0x18002f5b0`

## string_xrefs

- `0x18002f345`: `EapMapToEapConfigArray`
- `0x18002f509`: `EapMapToEapConfigArray`
- `0x18002f5a6`: `EapMapToEapConfigArray`

## pseudocode

```c
__int64 __fastcall EapMapToEapConfigArray(unsigned int a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r12
  unsigned int v5; // edi
  unsigned __int64 v6; // rcx
  _QWORD *v7; // r14
  unsigned int Memory; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rdi
  __int64 v20; // r13
  _WORD *v21; // rcx
  __int64 v23; // rax
  unsigned int v24; // r12d
  __int64 v25; // r13
  __int16 *v26; // rcx
  __int16 v27; // ax
  __int64 v28; // rax
  unsigned int v29; // r12d
  __int128 v31; // [rsp+30h] [rbp-58h] BYREF
  __int16 *v32; // [rsp+40h] [rbp-48h]
  unsigned int v35; // [rsp+A8h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  v6 = 40LL * a1;
  if ( v6 > 0xFFFFFFFF )
  {
    Memory = 87;
  }
  else
  {
    v7 = (_QWORD *)a3 + 1;
    Memory = AllocateMemory(v6, (char *)a3 + 8, "EapMapToEapConfigArray", 93);
    if ( !Memory )
    {
      *((_DWORD *)a3 + 1) = v5;
      v9 = 0;
      while ( 1 )
      {
        v35 = v9;
        if ( v9 >= v5 )
          break;
        v10 = 2580LL * v9;
        *(_QWORD *)&v31 = v10;
        v11 = *(_DWORD *)(v10 + v4);
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  v16 = v15 - 1;
                  if ( v16 )
                  {
                    v17 = v16 - 2;
                    if ( v17 )
                    {
                      v18 = v17 - 1;
                      if ( v18 )
                      {
                        if ( v18 != 1 )
                        {
                          Memory = 13;
                          break;
                        }
                        v19 = 40LL * v9;
                        *(_DWORD *)(v19 + *v7 + 4) = 8;
                      }
                      else
                      {
                        v19 = 40LL * v9;
                        *(_DWORD *)(v19 + *v7 + 4) = 7;
                      }
                    }
                    else
                    {
                      v19 = 40LL * v9;
                      *(_DWORD *)(v19 + *v7 + 4) = 6;
                    }
                  }
                  else
                  {
                    v19 = 40LL * v9;
                    *(_DWORD *)(v19 + *v7 + 4) = 5;
                  }
                }
                else
                {
                  v19 = 40LL * v9;
                  *(_DWORD *)(v19 + *v7 + 4) = 4;
                }
              }
              else
              {
                v19 = 40LL * v9;
                *(_DWORD *)(v19 + *v7 + 4) = 3;
              }
            }
            else
            {
              v19 = 40LL * v9;
              *(_DWORD *)(v19 + *v7 + 4) = 2;
            }
          }
          else
          {
            v19 = 40LL * v9;
            *(_DWORD *)(v19 + *v7 + 4) = 1;
          }
        }
        else
        {
          v19 = 40LL * v9;
          *(_DWORD *)(v19 + *v7 + 4) = 0;
        }
        *(_DWORD *)(*v7 + v19 + 8) = *(_DWORD *)(v10 + v4 + 4);
        v20 = v10 + v4;
        v21 = (_WORD *)(v10 + v4 + 12);
        while ( *v21++ )
          ;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v20 + 2 * v23 + 12) );
        v24 = 2 * v23 + 2;
        Memory = AllocateMemory(v24, v19 + *v7 + 16LL, "EapMapToEapConfigArray", 151);
        if ( Memory )
          break;
        memcpy_0(*(void **)(*v7 + v19 + 16), (const void *)(v20 + 12), v24);
        v25 = v31 + a2;
        v26 = (__int16 *)(v31 + a2 + 524);
        v32 = v26;
        do
        {
          v27 = *v26++;
          v32 = v26;
        }
        while ( v27 );
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v25 + 2 * v28 + 524) );
        if ( (unsigned int)v28 > *(_DWORD *)(v31 + a2 + 2576) || (unsigned int)v28 < *(_DWORD *)(v31 + a2 + 2572) )
        {
          Memory = 24;
          break;
        }
        v29 = 2 * v28 + 2;
        Memory = AllocateMemory(v29, v19 + *v7 + 24LL, "EapMapToEapConfigArray", 181);
        if ( Memory )
          break;
        memcpy_0(*(void **)(*v7 + v19 + 24), (const void *)(v25 + 524), v29);
        v9 = v35 + 1;
        v4 = a2;
        v5 = a1;
      }
    }
  }
  if ( Memory )
  {
    v31 = *a3;
    EapFreeEapConfigArray(&v31);
  }
  return Memory;
}

```

## disassembly

```asm
0x18002f300  mov     [rsp+arg_10], r8
0x18002f305  mov     [rsp+arg_8], rdx
0x18002f30a  mov     [rsp+arg_0], ecx
0x18002f30e  push    rbx
0x18002f30f  push    rsi
0x18002f310  push    rdi
0x18002f311  push    r12
0x18002f313  push    r13
0x18002f315  push    r14
0x18002f317  push    r15
0x18002f319  sub     rsp, 50h
0x18002f31d  mov     r15, r8
0x18002f320  mov     r12, rdx
0x18002f323  mov     edi, ecx
0x18002f325  lea     rcx, [rdi+rdi*4]
0x18002f329  shl     rcx, 3
0x18002f32d  mov     eax, 0FFFFFFFFh
0x18002f332  cmp     rcx, rax
0x18002f335  ja      loc_18002F615
0x18002f33b  lea     r14, [r8+8]
0x18002f33f  mov     r9d, 5Dh ; ']'
0x18002f345  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x18002f34c  mov     rdx, r14
0x18002f34f  call    cs:__imp_AllocateMemory
0x18002f355  mov     ebx, eax
0x18002f357  xor     esi, esi
0x18002f359  test    eax, eax
0x18002f35b  jnz     loc_18002F61A
0x18002f361  mov     [r15+4], edi
0x18002f365  mov     eax, esi
0x18002f367  mov     [rsp+88h+arg_18], eax
0x18002f36e  cmp     eax, edi
0x18002f370  jnb     loc_18002F61A
0x18002f376  mov     edx, eax
0x18002f378  imul    r8, rdx, 0A14h
0x18002f37f  mov     qword ptr [rsp+88h+var_58], r8
0x18002f384  mov     ecx, [r8+r12]
0x18002f388  test    ecx, ecx
0x18002f38a  jz      loc_18002F4A3
0x18002f390  sub     ecx, 1
0x18002f393  jz      loc_18002F48A
0x18002f399  sub     ecx, 1
0x18002f39c  jz      loc_18002F471
0x18002f3a2  sub     ecx, 1
0x18002f3a5  jz      loc_18002F458
0x18002f3ab  sub     ecx, 1
0x18002f3ae  jz      loc_18002F43F
0x18002f3b4  sub     ecx, 1
0x18002f3b7  jz      short loc_18002F426
0x18002f3b9  sub     ecx, 2
0x18002f3bc  jz      short loc_18002F40A
0x18002f3be  sub     ecx, 1
0x18002f3c1  jz      short loc_18002F3EE
0x18002f3c3  cmp     ecx, 1
0x18002f3c6  jz      short loc_18002F3D2
0x18002f3c8  mov     ebx, 0Dh
0x18002f3cd  jmp     loc_18002F61A
0x18002f3d2  lea     rax, [rdx+rdx*4]
0x18002f3d6  lea     rdi, ds:0[rax*8]
0x18002f3de  mov     rax, [r14]
0x18002f3e1  mov     dword ptr [rdi+rax+4], 8
0x18002f3e9  jmp     loc_18002F4B6
0x18002f3ee  lea     rax, [rdx+rdx*4]
0x18002f3f2  lea     rdi, ds:0[rax*8]
0x18002f3fa  mov     rax, [r14]
0x18002f3fd  mov     dword ptr [rdi+rax+4], 7
0x18002f405  jmp     loc_18002F4B6
0x18002f40a  lea     rax, [rdx+rdx*4]
0x18002f40e  lea     rdi, ds:0[rax*8]
0x18002f416  mov     rax, [r14]
0x18002f419  mov     dword ptr [rdi+rax+4], 6
0x18002f421  jmp     loc_18002F4B6
0x18002f426  lea     rax, [rdx+rdx*4]
0x18002f42a  lea     rdi, ds:0[rax*8]
0x18002f432  mov     rax, [r14]
0x18002f435  mov     dword ptr [rdi+rax+4], 5
0x18002f43d  jmp     short loc_18002F4B6
0x18002f43f  lea     rax, [rdx+rdx*4]
0x18002f443  lea     rdi, ds:0[rax*8]
0x18002f44b  mov     rax, [r14]
0x18002f44e  mov     dword ptr [rdi+rax+4], 4
0x18002f456  jmp     short loc_18002F4B6
0x18002f458  lea     rax, [rdx+rdx*4]
0x18002f45c  lea     rdi, ds:0[rax*8]
0x18002f464  mov     rax, [r14]
0x18002f467  mov     dword ptr [rdi+rax+4], 3
0x18002f46f  jmp     short loc_18002F4B6
0x18002f471  lea     rax, [rdx+rdx*4]
0x18002f475  lea     rdi, ds:0[rax*8]
0x18002f47d  mov     rax, [r14]
0x18002f480  mov     dword ptr [rdi+rax+4], 2
0x18002f488  jmp     short loc_18002F4B6
0x18002f48a  lea     rax, [rdx+rdx*4]
0x18002f48e  lea     rdi, ds:0[rax*8]
0x18002f496  mov     rax, [r14]
0x18002f499  mov     dword ptr [rdi+rax+4], 1
0x18002f4a1  jmp     short loc_18002F4B6
0x18002f4a3  lea     rax, [rdx+rdx*4]
0x18002f4a7  lea     rdi, ds:0[rax*8]
0x18002f4af  mov     rax, [r14]
0x18002f4b2  mov     [rdi+rax+4], esi
0x18002f4b6  mov     rcx, [r14]
0x18002f4b9  mov     eax, [r8+r12+4]
0x18002f4be  mov     [rcx+rdi+8], eax
0x18002f4c2  lea     r13, [r8+r12]
0x18002f4c6  lea     rcx, [r13+0Ch]
0x18002f4ca  mov     [rsp+88h+var_68], rcx
0x18002f4cf  movzx   eax, word ptr [rcx]
0x18002f4d2  add     rcx, 2
0x18002f4d6  mov     [rsp+88h+var_68], rcx
0x18002f4db  test    ax, ax
0x18002f4de  jz      short loc_18002F4E2
0x18002f4e0  jmp     short loc_18002F4CF
0x18002f4e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f4e6  inc     rax
0x18002f4e9  cmp     [r13+rax*2+0Ch], si
0x18002f4ef  jnz     short loc_18002F4E6
0x18002f4f1  lea     r12d, ds:2[rax*2]
0x18002f4f9  mov     rdx, [r14]
0x18002f4fc  add     rdx, 10h
0x18002f500  add     rdx, rdi
0x18002f503  mov     r9d, 97h
0x18002f509  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x18002f510  mov     ecx, r12d
0x18002f513  call    cs:__imp_AllocateMemory
0x18002f519  mov     ebx, eax
0x18002f51b  test    eax, eax
0x18002f51d  jnz     loc_18002F61A
0x18002f523  mov     r8d, r12d; Size
0x18002f526  mov     rcx, [r14]
0x18002f529  lea     rdx, [r13+0Ch]; Src
0x18002f52d  mov     rcx, [rcx+rdi+10h]; void *
0x18002f532  call    memcpy_0
0x18002f537  nop
0x18002f538  mov     rdx, qword ptr [rsp+88h+var_58]
0x18002f53d  mov     r8, [rsp+88h+arg_8]
0x18002f545  lea     r13, [rdx+r8]
0x18002f549  lea     rcx, [r13+20Ch]
0x18002f550  mov     [rsp+88h+var_48], rcx
0x18002f555  movzx   eax, word ptr [rcx]
0x18002f558  add     rcx, 2
0x18002f55c  mov     [rsp+88h+var_48], rcx
0x18002f561  test    ax, ax
0x18002f564  jz      short loc_18002F568
0x18002f566  jmp     short loc_18002F555
0x18002f568  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f56c  inc     rax
0x18002f56f  cmp     [r13+rax*2+20Ch], si
0x18002f578  jnz     short loc_18002F56C
0x18002f57a  cmp     eax, [rdx+r8+0A10h]
0x18002f582  ja      short loc_18002F5F0
0x18002f584  cmp     eax, [rdx+r8+0A0Ch]
0x18002f58c  jb      short loc_18002F5F0
0x18002f58e  lea     r12d, ds:2[rax*2]
0x18002f596  mov     rdx, [r14]
0x18002f599  add     rdx, 18h
0x18002f59d  add     rdx, rdi
0x18002f5a0  mov     r9d, 0B5h
0x18002f5a6  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x18002f5ad  mov     ecx, r12d
0x18002f5b0  call    cs:__imp_AllocateMemory
0x18002f5b6  mov     ebx, eax
0x18002f5b8  test    eax, eax
0x18002f5ba  jnz     short loc_18002F61A
0x18002f5bc  mov     r8d, r12d; Size
0x18002f5bf  mov     rcx, [r14]
0x18002f5c2  lea     rdx, [r13+20Ch]; Src
0x18002f5c9  mov     rcx, [rcx+rdi+18h]; void *
0x18002f5ce  call    memcpy_0
0x18002f5d3  mov     eax, [rsp+88h+arg_18]
0x18002f5da  inc     eax
0x18002f5dc  mov     r12, [rsp+88h+arg_8]
0x18002f5e4  mov     edi, [rsp+88h+arg_0]
0x18002f5eb  jmp     loc_18002F367
0x18002f5f0  mov     ebx, 18h
0x18002f5f5  jmp     short loc_18002F61A
0x18002f5f7  mov     ebx, 57h ; 'W'
0x18002f5fc  mov     r15, [rsp+88h+arg_10]
0x18002f604  jmp     short loc_18002F61A
0x18002f606  mov     ebx, 57h ; 'W'
0x18002f60b  mov     r15, [rsp+88h+arg_10]
0x18002f613  jmp     short loc_18002F61A
0x18002f615  mov     ebx, 57h ; 'W'
0x18002f61a  test    ebx, ebx
0x18002f61c  jz      short loc_18002F632
0x18002f61e  movups  xmm0, xmmword ptr [r15]
0x18002f622  movdqu  [rsp+88h+var_58], xmm0
0x18002f628  lea     rcx, [rsp+88h+var_58]
0x18002f62d  call    EapFreeEapConfigArray
0x18002f632  mov     eax, ebx
0x18002f634  add     rsp, 50h
0x18002f638  pop     r15
0x18002f63a  pop     r14
0x18002f63c  pop     r13
0x18002f63e  pop     r12
0x18002f640  pop     rdi
0x18002f641  pop     rsi
0x18002f642  pop     rbx
0x18002f643  retn
```
