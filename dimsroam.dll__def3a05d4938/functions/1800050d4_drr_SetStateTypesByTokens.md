# _drr_SetStateTypesByTokens

- ea: `0x1800050d4`
- end: `0x1800052a3`
- name: `_drr_SetStateTypesByTokens`
- size: `463`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006230`

## callees

- `0x1800050d4`
- `0x18000d110`
- `0x18000d886`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005163`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005204`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005163`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005284`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005284`

## pseudocode

```c
__int64 __fastcall drr_SetStateTypesByTokens(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  __int64 v6; // rbx
  _OWORD *v7; // rsi
  _WORD *v8; // rbp
  int v9; // eax
  _OWORD *v10; // rax
  __int64 v11; // rbp
  void *v12; // rsi

  result = *(unsigned int *)(a2 + 8);
  if ( !(_DWORD)result )
    return result;
  v5 = 0;
  v6 = 0;
  while ( (unsigned int)v5 < *(_DWORD *)(a1 + 8) )
  {
    v7 = *(_OWORD **)(*(_QWORD *)a2 + 8 * v6);
    v8 = *(_WORD **)(*(_QWORD *)a1 + 8 * v5);
    v9 = memcmp_0(v7, v8, 0x60u);
    if ( v9 )
    {
      if ( v9 < 0 )
      {
        if ( (*((_BYTE *)v7 + 104) & 0x10) != 0 )
        {
          v10 = LocalAlloc(0, 0x84u);
          if ( v10 )
          {
            *v10 = *v7;
            v10[1] = v7[1];
            v10[2] = v7[2];
            v10[3] = v7[3];
            v10[4] = v7[4];
            v10[5] = v7[5];
            v10[6] = v7[6];
            v10[7] = v7[7];
            *((_DWORD *)v10 + 32) = *((_DWORD *)v7 + 32);
            *((_WORD *)v10 + 52) |= 8u;
            *((_DWORD *)v10 + 32) = 0;
            if ( !(unsigned int)DRR_InsertGrowableArray(a1, (unsigned int)v5, v10) )
              v5 = (unsigned int)(v5 + 1);
          }
        }
        v6 = (unsigned int)(v6 + 1);
        goto LABEL_10;
      }
    }
    else
    {
      if ( (*((_BYTE *)v7 + 104) & 0x10) != 0 && (v8[52] & 0x10) == 0 )
        v8[52] ^= (*((_WORD *)v7 + 52) ^ v8[52]) & 0x30;
      v6 = (unsigned int)(v6 + 1);
    }
    v5 = (unsigned int)(v5 + 1);
LABEL_10:
    result = *(unsigned int *)(a2 + 8);
    if ( (unsigned int)v6 >= (unsigned int)result )
      return result;
  }
  if ( (unsigned int)v6 < (unsigned int)result )
  {
    do
    {
      result = *(_QWORD *)a2;
      v11 = *(_QWORD *)(*(_QWORD *)a2 + 8 * v6);
      if ( (*(_BYTE *)(v11 + 104) & 0x10) != 0 )
      {
        result = (__int64)LocalAlloc(0, 0x84u);
        v12 = (void *)result;
        if ( result )
        {
          *(_OWORD *)result = *(_OWORD *)v11;
          *(_OWORD *)(result + 16) = *(_OWORD *)(v11 + 16);
          *(_OWORD *)(result + 32) = *(_OWORD *)(v11 + 32);
          *(_OWORD *)(result + 48) = *(_OWORD *)(v11 + 48);
          *(_OWORD *)(result + 64) = *(_OWORD *)(v11 + 64);
          *(_OWORD *)(result + 80) = *(_OWORD *)(v11 + 80);
          *(_OWORD *)(result + 96) = *(_OWORD *)(v11 + 96);
          *(_OWORD *)(result + 112) = *(_OWORD *)(v11 + 112);
          *(_DWORD *)(result + 128) = *(_DWORD *)(v11 + 128);
          *(_WORD *)(result + 104) |= 8u;
          *(_DWORD *)(result + 128) = 0;
          result = DRR_InsertGrowableArray(a1, (unsigned int)v5, result);
          if ( (_DWORD)result )
            result = (__int64)LocalFree(v12);
          else
            LODWORD(v5) = v5 + 1;
        }
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *(_DWORD *)(a2 + 8) );
  }
  return result;
}

```

## disassembly

```asm
0x1800050d4  push    rbx
0x1800050d6  push    rbp
0x1800050d7  push    rsi
0x1800050d8  push    rdi
0x1800050d9  push    r14
0x1800050db  push    r15
0x1800050dd  sub     rsp, 28h
0x1800050e1  mov     eax, [rdx+8]
0x1800050e4  mov     r14, rdx
0x1800050e7  mov     r15, rcx
0x1800050ea  test    eax, eax
0x1800050ec  jz      loc_180005296
0x1800050f2  xor     edi, edi
0x1800050f4  xor     ebx, ebx
0x1800050f6  cmp     edi, [r15+8]
0x1800050fa  jnb     loc_1800051E4
0x180005100  mov     rax, [r14]
0x180005103  mov     r8d, 60h ; '`'; Size
0x180005109  mov     rsi, [rax+rbx*8]
0x18000510d  mov     rax, [r15]
0x180005110  mov     rcx, rsi; Buf1
0x180005113  mov     rbp, [rax+rdi*8]
0x180005117  mov     rdx, rbp; Buf2
0x18000511a  call    memcmp_0
0x18000511f  test    eax, eax
0x180005121  jnz     short loc_180005150
0x180005123  test    byte ptr [rsi+68h], 10h
0x180005127  jz      short loc_18000513F
0x180005129  test    byte ptr [rbp+68h], 10h
0x18000512d  jnz     short loc_18000513F
0x18000512f  movzx   eax, word ptr [rbp+68h]
0x180005133  xor     ax, [rsi+68h]
0x180005137  and     ax, 30h
0x18000513b  xor     [rbp+68h], ax
0x18000513f  inc     ebx
0x180005141  inc     edi
0x180005143  mov     eax, [r14+8]
0x180005147  cmp     ebx, eax
0x180005149  jb      short loc_1800050F6
0x18000514b  jmp     loc_180005296
0x180005150  jns     short loc_180005141
0x180005152  test    byte ptr [rsi+68h], 10h
0x180005156  jz      loc_1800051DD
0x18000515c  mov     edx, 84h; uBytes
0x180005161  xor     ecx, ecx; uFlags
0x180005163  call    cs:__imp_LocalAlloc
0x180005169  mov     r8, rax
0x18000516c  test    rax, rax
0x18000516f  jz      short loc_1800051DD
0x180005171  movups  xmm0, xmmword ptr [rsi]
0x180005174  mov     edx, edi
0x180005176  mov     rcx, r15
0x180005179  movups  xmmword ptr [rax], xmm0
0x18000517c  movups  xmm1, xmmword ptr [rsi+10h]
0x180005180  movups  xmmword ptr [rax+10h], xmm1
0x180005184  movups  xmm0, xmmword ptr [rsi+20h]
0x180005188  movups  xmmword ptr [rax+20h], xmm0
0x18000518c  movups  xmm1, xmmword ptr [rsi+30h]
0x180005190  movups  xmmword ptr [rax+30h], xmm1
0x180005194  movups  xmm0, xmmword ptr [rsi+40h]
0x180005198  movups  xmmword ptr [rax+40h], xmm0
0x18000519c  movups  xmm1, xmmword ptr [rsi+50h]
0x1800051a0  movups  xmmword ptr [rax+50h], xmm1
0x1800051a4  movups  xmm0, xmmword ptr [rsi+60h]
0x1800051a8  movups  xmmword ptr [rax+60h], xmm0
0x1800051ac  movups  xmm1, xmmword ptr [rsi+70h]
0x1800051b0  movups  xmmword ptr [rax+70h], xmm1
0x1800051b4  mov     eax, [rsi+80h]
0x1800051ba  mov     [r8+80h], eax
0x1800051c1  or      word ptr [r8+68h], 8
0x1800051c7  mov     dword ptr [r8+80h], 0
0x1800051d2  call    DRR_InsertGrowableArray
0x1800051d7  test    eax, eax
0x1800051d9  jnz     short loc_1800051DD
0x1800051db  inc     edi
0x1800051dd  inc     ebx
0x1800051df  jmp     loc_180005143
0x1800051e4  cmp     ebx, eax
0x1800051e6  jnb     loc_180005296
0x1800051ec  mov     rax, [r14]
0x1800051ef  mov     rbp, [rax+rbx*8]
0x1800051f3  test    byte ptr [rbp+68h], 10h
0x1800051f7  jz      loc_18000528A
0x1800051fd  mov     edx, 84h; uBytes
0x180005202  xor     ecx, ecx; uFlags
0x180005204  call    cs:__imp_LocalAlloc
0x18000520a  mov     rsi, rax
0x18000520d  test    rax, rax
0x180005210  jz      short loc_18000528A
0x180005212  movups  xmm0, xmmword ptr [rbp+0]
0x180005216  mov     r8, rsi
0x180005219  mov     edx, edi
0x18000521b  mov     rcx, r15
0x18000521e  movups  xmmword ptr [rax], xmm0
0x180005221  movups  xmm1, xmmword ptr [rbp+10h]
0x180005225  movups  xmmword ptr [rax+10h], xmm1
0x180005229  movups  xmm0, xmmword ptr [rbp+20h]
0x18000522d  movups  xmmword ptr [rax+20h], xmm0
0x180005231  movups  xmm1, xmmword ptr [rbp+30h]
0x180005235  movups  xmmword ptr [rax+30h], xmm1
0x180005239  movups  xmm0, xmmword ptr [rbp+40h]
0x18000523d  movups  xmmword ptr [rax+40h], xmm0
0x180005241  movups  xmm1, xmmword ptr [rbp+50h]
0x180005245  movups  xmmword ptr [rax+50h], xmm1
0x180005249  movups  xmm0, xmmword ptr [rbp+60h]
0x18000524d  movups  xmmword ptr [rax+60h], xmm0
0x180005251  movups  xmm1, xmmword ptr [rbp+70h]
0x180005255  movups  xmmword ptr [rax+70h], xmm1
0x180005259  mov     eax, [rbp+80h]
0x18000525f  mov     [rsi+80h], eax
0x180005265  or      word ptr [rsi+68h], 8
0x18000526a  mov     dword ptr [rsi+80h], 0
0x180005274  call    DRR_InsertGrowableArray
0x180005279  test    eax, eax
0x18000527b  jnz     short loc_180005281
0x18000527d  inc     edi
0x18000527f  jmp     short loc_18000528A
0x180005281  mov     rcx, rsi; hMem
0x180005284  call    cs:__imp_LocalFree
0x18000528a  inc     ebx
0x18000528c  cmp     ebx, [r14+8]
0x180005290  jb      loc_1800051EC
0x180005296  add     rsp, 28h
0x18000529a  pop     r15
0x18000529c  pop     r14
0x18000529e  pop     rdi
0x18000529f  pop     rsi
0x1800052a0  pop     rbp
0x1800052a1  pop     rbx
0x1800052a2  retn
```
