# EapMapToEapConfigArray

- ea: `0x1800391b0`
- end: `0x1800394f4`
- name: `EapMapToEapConfigArray`
- size: `836`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038f5c`

## callees

- `0x1800030fc`
- `0x1800390ec`
- `0x1800391b0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x1800391ff`
- `MobileNetworking!AllocateMemory` at `0x1800393c3`
- `MobileNetworking!AllocateMemory` at `0x180039460`
- `MobileNetworking!AllocateMemory` at `0x1800391ff`
- `MobileNetworking!AllocateMemory` at `0x1800393c3`
- `MobileNetworking!AllocateMemory` at `0x180039460`

## string_xrefs

- `0x1800391f5`: `EapMapToEapConfigArray`
- `0x1800393b9`: `EapMapToEapConfigArray`
- `0x180039456`: `EapMapToEapConfigArray`

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
0x1800391b0  mov     [rsp+arg_10], r8
0x1800391b5  mov     [rsp+arg_8], rdx
0x1800391ba  mov     [rsp+arg_0], ecx
0x1800391be  push    rbx
0x1800391bf  push    rsi
0x1800391c0  push    rdi
0x1800391c1  push    r12
0x1800391c3  push    r13
0x1800391c5  push    r14
0x1800391c7  push    r15
0x1800391c9  sub     rsp, 50h
0x1800391cd  mov     r15, r8
0x1800391d0  mov     r12, rdx
0x1800391d3  mov     edi, ecx
0x1800391d5  lea     rcx, [rdi+rdi*4]
0x1800391d9  shl     rcx, 3
0x1800391dd  mov     eax, 0FFFFFFFFh
0x1800391e2  cmp     rcx, rax
0x1800391e5  ja      loc_1800394C5
0x1800391eb  lea     r14, [r8+8]
0x1800391ef  mov     r9d, 5Dh ; ']'
0x1800391f5  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x1800391fc  mov     rdx, r14
0x1800391ff  call    cs:__imp_AllocateMemory
0x180039205  mov     ebx, eax
0x180039207  xor     esi, esi
0x180039209  test    eax, eax
0x18003920b  jnz     loc_1800394CA
0x180039211  mov     [r15+4], edi
0x180039215  mov     eax, esi
0x180039217  mov     [rsp+88h+arg_18], eax
0x18003921e  cmp     eax, edi
0x180039220  jnb     loc_1800394CA
0x180039226  mov     edx, eax
0x180039228  imul    r8, rdx, 0A14h
0x18003922f  mov     qword ptr [rsp+88h+var_58], r8
0x180039234  mov     ecx, [r8+r12]
0x180039238  test    ecx, ecx
0x18003923a  jz      loc_180039353
0x180039240  sub     ecx, 1
0x180039243  jz      loc_18003933A
0x180039249  sub     ecx, 1
0x18003924c  jz      loc_180039321
0x180039252  sub     ecx, 1
0x180039255  jz      loc_180039308
0x18003925b  sub     ecx, 1
0x18003925e  jz      loc_1800392EF
0x180039264  sub     ecx, 1
0x180039267  jz      short loc_1800392D6
0x180039269  sub     ecx, 2
0x18003926c  jz      short loc_1800392BA
0x18003926e  sub     ecx, 1
0x180039271  jz      short loc_18003929E
0x180039273  cmp     ecx, 1
0x180039276  jz      short loc_180039282
0x180039278  mov     ebx, 0Dh
0x18003927d  jmp     loc_1800394CA
0x180039282  lea     rax, [rdx+rdx*4]
0x180039286  lea     rdi, ds:0[rax*8]
0x18003928e  mov     rax, [r14]
0x180039291  mov     dword ptr [rdi+rax+4], 8
0x180039299  jmp     loc_180039366
0x18003929e  lea     rax, [rdx+rdx*4]
0x1800392a2  lea     rdi, ds:0[rax*8]
0x1800392aa  mov     rax, [r14]
0x1800392ad  mov     dword ptr [rdi+rax+4], 7
0x1800392b5  jmp     loc_180039366
0x1800392ba  lea     rax, [rdx+rdx*4]
0x1800392be  lea     rdi, ds:0[rax*8]
0x1800392c6  mov     rax, [r14]
0x1800392c9  mov     dword ptr [rdi+rax+4], 6
0x1800392d1  jmp     loc_180039366
0x1800392d6  lea     rax, [rdx+rdx*4]
0x1800392da  lea     rdi, ds:0[rax*8]
0x1800392e2  mov     rax, [r14]
0x1800392e5  mov     dword ptr [rdi+rax+4], 5
0x1800392ed  jmp     short loc_180039366
0x1800392ef  lea     rax, [rdx+rdx*4]
0x1800392f3  lea     rdi, ds:0[rax*8]
0x1800392fb  mov     rax, [r14]
0x1800392fe  mov     dword ptr [rdi+rax+4], 4
0x180039306  jmp     short loc_180039366
0x180039308  lea     rax, [rdx+rdx*4]
0x18003930c  lea     rdi, ds:0[rax*8]
0x180039314  mov     rax, [r14]
0x180039317  mov     dword ptr [rdi+rax+4], 3
0x18003931f  jmp     short loc_180039366
0x180039321  lea     rax, [rdx+rdx*4]
0x180039325  lea     rdi, ds:0[rax*8]
0x18003932d  mov     rax, [r14]
0x180039330  mov     dword ptr [rdi+rax+4], 2
0x180039338  jmp     short loc_180039366
0x18003933a  lea     rax, [rdx+rdx*4]
0x18003933e  lea     rdi, ds:0[rax*8]
0x180039346  mov     rax, [r14]
0x180039349  mov     dword ptr [rdi+rax+4], 1
0x180039351  jmp     short loc_180039366
0x180039353  lea     rax, [rdx+rdx*4]
0x180039357  lea     rdi, ds:0[rax*8]
0x18003935f  mov     rax, [r14]
0x180039362  mov     [rdi+rax+4], esi
0x180039366  mov     rcx, [r14]
0x180039369  mov     eax, [r8+r12+4]
0x18003936e  mov     [rcx+rdi+8], eax
0x180039372  lea     r13, [r8+r12]
0x180039376  lea     rcx, [r13+0Ch]
0x18003937a  mov     [rsp+88h+var_68], rcx
0x18003937f  movzx   eax, word ptr [rcx]
0x180039382  add     rcx, 2
0x180039386  mov     [rsp+88h+var_68], rcx
0x18003938b  test    ax, ax
0x18003938e  jz      short loc_180039392
0x180039390  jmp     short loc_18003937F
0x180039392  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039396  inc     rax
0x180039399  cmp     [r13+rax*2+0Ch], si
0x18003939f  jnz     short loc_180039396
0x1800393a1  lea     r12d, ds:2[rax*2]
0x1800393a9  mov     rdx, [r14]
0x1800393ac  add     rdx, 10h
0x1800393b0  add     rdx, rdi
0x1800393b3  mov     r9d, 97h
0x1800393b9  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x1800393c0  mov     ecx, r12d
0x1800393c3  call    cs:__imp_AllocateMemory
0x1800393c9  mov     ebx, eax
0x1800393cb  test    eax, eax
0x1800393cd  jnz     loc_1800394CA
0x1800393d3  mov     r8d, r12d; Size
0x1800393d6  mov     rcx, [r14]
0x1800393d9  lea     rdx, [r13+0Ch]; Src
0x1800393dd  mov     rcx, [rcx+rdi+10h]; void *
0x1800393e2  call    memcpy_0
0x1800393e7  nop
0x1800393e8  mov     rdx, qword ptr [rsp+88h+var_58]
0x1800393ed  mov     r8, [rsp+88h+arg_8]
0x1800393f5  lea     r13, [rdx+r8]
0x1800393f9  lea     rcx, [r13+20Ch]
0x180039400  mov     [rsp+88h+var_48], rcx
0x180039405  movzx   eax, word ptr [rcx]
0x180039408  add     rcx, 2
0x18003940c  mov     [rsp+88h+var_48], rcx
0x180039411  test    ax, ax
0x180039414  jz      short loc_180039418
0x180039416  jmp     short loc_180039405
0x180039418  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003941c  inc     rax
0x18003941f  cmp     [r13+rax*2+20Ch], si
0x180039428  jnz     short loc_18003941C
0x18003942a  cmp     eax, [rdx+r8+0A10h]
0x180039432  ja      short loc_1800394A0
0x180039434  cmp     eax, [rdx+r8+0A0Ch]
0x18003943c  jb      short loc_1800394A0
0x18003943e  lea     r12d, ds:2[rax*2]
0x180039446  mov     rdx, [r14]
0x180039449  add     rdx, 18h
0x18003944d  add     rdx, rdi
0x180039450  mov     r9d, 0B5h
0x180039456  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x18003945d  mov     ecx, r12d
0x180039460  call    cs:__imp_AllocateMemory
0x180039466  mov     ebx, eax
0x180039468  test    eax, eax
0x18003946a  jnz     short loc_1800394CA
0x18003946c  mov     r8d, r12d; Size
0x18003946f  mov     rcx, [r14]
0x180039472  lea     rdx, [r13+20Ch]; Src
0x180039479  mov     rcx, [rcx+rdi+18h]; void *
0x18003947e  call    memcpy_0
0x180039483  mov     eax, [rsp+88h+arg_18]
0x18003948a  inc     eax
0x18003948c  mov     r12, [rsp+88h+arg_8]
0x180039494  mov     edi, [rsp+88h+arg_0]
0x18003949b  jmp     loc_180039217
0x1800394a0  mov     ebx, 18h
0x1800394a5  jmp     short loc_1800394CA
0x1800394a7  mov     ebx, 57h ; 'W'
0x1800394ac  mov     r15, [rsp+88h+arg_10]
0x1800394b4  jmp     short loc_1800394CA
0x1800394b6  mov     ebx, 57h ; 'W'
0x1800394bb  mov     r15, [rsp+88h+arg_10]
0x1800394c3  jmp     short loc_1800394CA
0x1800394c5  mov     ebx, 57h ; 'W'
0x1800394ca  test    ebx, ebx
0x1800394cc  jz      short loc_1800394E2
0x1800394ce  movups  xmm0, xmmword ptr [r15]
0x1800394d2  movdqu  [rsp+88h+var_58], xmm0
0x1800394d8  lea     rcx, [rsp+88h+var_58]
0x1800394dd  call    EapFreeEapConfigArray
0x1800394e2  mov     eax, ebx
0x1800394e4  add     rsp, 50h
0x1800394e8  pop     r15
0x1800394ea  pop     r14
0x1800394ec  pop     r13
0x1800394ee  pop     r12
0x1800394f0  pop     rdi
0x1800394f1  pop     rsi
0x1800394f2  pop     rbx
0x1800394f3  retn
```
