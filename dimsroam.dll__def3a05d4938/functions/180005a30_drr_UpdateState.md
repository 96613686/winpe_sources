# _drr_UpdateState

- ea: `0x180005a30`
- end: `0x180005bfa`
- name: `_drr_UpdateState`
- size: `458`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005c00`
- `0x180006230`

## callees

- `0x180005a30`
- `0x18000cde8`
- `0x18000d054`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005aa0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005aa0`

## pseudocode

```c
__int64 __fastcall drr_UpdateState(__int64 a1, __int64 *a2, __int64 *a3, _QWORD *a4)
{
  __int64 v4; // r15
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  __int64 i; // rsi
  __int64 v9; // rdi
  __int64 v10; // r12
  _OWORD *RoamingTokenFromSet; // rbx
  _OWORD *v12; // rax
  _OWORD *v13; // rax
  __int64 v15; // [rsp+60h] [rbp+8h]

  v15 = a1;
  v4 = *a2;
  v6 = *((_DWORD *)a2 + 2);
  v7 = 0;
  while ( 1 )
  {
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      v9 = *(_QWORD *)(v4 + 8 * i);
      if ( *(_DWORD *)v9 > 1u || *(_DWORD *)(v9 + 4) )
      {
        v10 = a1 + 112;
        RoamingTokenFromSet = (_OWORD *)DRR_GetRoamingTokenFromSet(a1 + 112, *(_QWORD *)(v9 + 8));
        if ( !RoamingTokenFromSet )
        {
          RoamingTokenFromSet = LocalAlloc(0, 0x84u);
          if ( !RoamingTokenFromSet )
            return 14;
          v12 = *(_OWORD **)(v9 + 8);
          *RoamingTokenFromSet = *v12;
          RoamingTokenFromSet[1] = v12[1];
          RoamingTokenFromSet[2] = v12[2];
          RoamingTokenFromSet[3] = v12[3];
          RoamingTokenFromSet[4] = v12[4];
          RoamingTokenFromSet[5] = v12[5];
          RoamingTokenFromSet[6] = v12[6];
          RoamingTokenFromSet[7] = v12[7];
          *((_DWORD *)RoamingTokenFromSet + 32) = 0;
          v7 = DRR_AddRoamingTokenToSet(v10, RoamingTokenFromSet, 1);
          if ( v7 )
            return v7;
        }
        if ( *(_DWORD *)(v9 + 4) == 1 )
        {
          a1 = v15;
          if ( (unsigned int)(*(_DWORD *)v9 - 4) <= 1 )
          {
            if ( (*((_BYTE *)RoamingTokenFromSet + 104) & 1) == 0 )
            {
              *((_QWORD *)RoamingTokenFromSet + 12) = *a4;
              *((_WORD *)RoamingTokenFromSet + 52) = 1;
            }
          }
          else
          {
            v13 = *(_OWORD **)(v9 + 8);
            *RoamingTokenFromSet = *v13;
            RoamingTokenFromSet[1] = v13[1];
            RoamingTokenFromSet[2] = v13[2];
            RoamingTokenFromSet[3] = v13[3];
            RoamingTokenFromSet[4] = v13[4];
            RoamingTokenFromSet[5] = v13[5];
            RoamingTokenFromSet[6] = v13[6];
            RoamingTokenFromSet[7] = v13[7];
            *((_DWORD *)RoamingTokenFromSet + 32) = 0;
          }
        }
        else
        {
          if ( (*(_BYTE *)(v9 + 4) & 2) != 0 )
          {
            if ( *(_DWORD *)v9 == 4 )
              *((_WORD *)RoamingTokenFromSet + 52) |= 1u;
            *((_WORD *)RoamingTokenFromSet + 52) |= 4u;
          }
          a1 = v15;
        }
      }
    }
    if ( v4 == *a3 )
      break;
    v4 = *a3;
    v6 = *((_DWORD *)a3 + 2);
  }
  return v7;
}

```

## disassembly

```asm
0x180005a30  mov     [rsp+arg_8], rbx
0x180005a35  mov     [rsp+arg_18], r9
0x180005a3a  mov     [rsp+arg_0], rcx
0x180005a3f  push    rbp
0x180005a40  push    rsi
0x180005a41  push    rdi
0x180005a42  push    r12
0x180005a44  push    r13
0x180005a46  push    r14
0x180005a48  push    r15
0x180005a4a  sub     rsp, 20h
0x180005a4e  mov     r15, [rdx]
0x180005a51  mov     r13, r8
0x180005a54  mov     r14d, [rdx+8]
0x180005a58  xor     ebp, ebp
0x180005a5a  xor     esi, esi
0x180005a5c  test    r14d, r14d
0x180005a5f  jz      loc_180005B91
0x180005a65  mov     rdi, [r15+rsi*8]
0x180005a69  cmp     dword ptr [rdi], 0
0x180005a6c  jz      short loc_180005A73
0x180005a6e  cmp     dword ptr [rdi], 1
0x180005a71  jnz     short loc_180005A7D
0x180005a73  cmp     dword ptr [rdi+4], 0
0x180005a77  jz      loc_180005B81
0x180005a7d  mov     rdx, [rdi+8]
0x180005a81  lea     r12, [rcx+70h]
0x180005a85  mov     rcx, r12
0x180005a88  call    DRR_GetRoamingTokenFromSet
0x180005a8d  mov     rbx, rax
0x180005a90  test    rax, rax
0x180005a93  jnz     loc_180005B19
0x180005a99  mov     edx, 84h; uBytes
0x180005a9e  xor     ecx, ecx; uFlags
0x180005aa0  call    cs:__imp_LocalAlloc
0x180005aa6  mov     rbx, rax
0x180005aa9  test    rax, rax
0x180005aac  jz      loc_180005BDE
0x180005ab2  mov     rax, [rdi+8]
0x180005ab6  mov     r8d, 1
0x180005abc  mov     rdx, rbx
0x180005abf  mov     rcx, r12
0x180005ac2  movups  xmm0, xmmword ptr [rax]
0x180005ac5  movups  xmmword ptr [rbx], xmm0
0x180005ac8  movups  xmm1, xmmword ptr [rax+10h]
0x180005acc  movups  xmmword ptr [rbx+10h], xmm1
0x180005ad0  movups  xmm0, xmmword ptr [rax+20h]
0x180005ad4  movups  xmmword ptr [rbx+20h], xmm0
0x180005ad8  movups  xmm1, xmmword ptr [rax+30h]
0x180005adc  movups  xmmword ptr [rbx+30h], xmm1
0x180005ae0  movups  xmm0, xmmword ptr [rax+40h]
0x180005ae4  movups  xmmword ptr [rbx+40h], xmm0
0x180005ae8  movups  xmm1, xmmword ptr [rax+50h]
0x180005aec  movups  xmmword ptr [rbx+50h], xmm1
0x180005af0  movups  xmm0, xmmword ptr [rax+60h]
0x180005af4  movups  xmmword ptr [rbx+60h], xmm0
0x180005af8  movups  xmm1, xmmword ptr [rax+70h]
0x180005afc  movups  xmmword ptr [rbx+70h], xmm1
0x180005b00  mov     dword ptr [rbx+80h], 0
0x180005b0a  call    DRR_AddRoamingTokenToSet
0x180005b0f  mov     ebp, eax
0x180005b11  test    eax, eax
0x180005b13  jnz     loc_180005BE3
0x180005b19  mov     eax, 1
0x180005b1e  cmp     [rdi+4], eax
0x180005b21  jnz     loc_180005BC0
0x180005b27  mov     ecx, [rdi]
0x180005b29  sub     ecx, 4
0x180005b2c  cmp     ecx, eax
0x180005b2e  mov     rcx, [rsp+58h+arg_0]
0x180005b33  jbe     short loc_180005BA4
0x180005b35  mov     rax, [rdi+8]
0x180005b39  movups  xmm0, xmmword ptr [rax]
0x180005b3c  movups  xmmword ptr [rbx], xmm0
0x180005b3f  movups  xmm1, xmmword ptr [rax+10h]
0x180005b43  movups  xmmword ptr [rbx+10h], xmm1
0x180005b47  movups  xmm0, xmmword ptr [rax+20h]
0x180005b4b  movups  xmmword ptr [rbx+20h], xmm0
0x180005b4f  movups  xmm1, xmmword ptr [rax+30h]
0x180005b53  movups  xmmword ptr [rbx+30h], xmm1
0x180005b57  movups  xmm0, xmmword ptr [rax+40h]
0x180005b5b  movups  xmmword ptr [rbx+40h], xmm0
0x180005b5f  movups  xmm1, xmmword ptr [rax+50h]
0x180005b63  movups  xmmword ptr [rbx+50h], xmm1
0x180005b67  movups  xmm0, xmmword ptr [rax+60h]
0x180005b6b  movups  xmmword ptr [rbx+60h], xmm0
0x180005b6f  movups  xmm1, xmmword ptr [rax+70h]
0x180005b73  movups  xmmword ptr [rbx+70h], xmm1
0x180005b77  mov     dword ptr [rbx+80h], 0
0x180005b81  mov     eax, 1
0x180005b86  add     esi, eax
0x180005b88  cmp     esi, r14d
0x180005b8b  jb      loc_180005A65
0x180005b91  cmp     r15, [r13+0]
0x180005b95  jz      short loc_180005BE3
0x180005b97  mov     r15, [r13+0]
0x180005b9b  mov     r14d, [r13+8]
0x180005b9f  jmp     loc_180005A5A
0x180005ba4  test    [rbx+68h], al
0x180005ba7  jnz     short loc_180005B86
0x180005ba9  mov     rax, [rsp+58h+arg_18]
0x180005bae  mov     rax, [rax]
0x180005bb1  mov     [rbx+60h], rax
0x180005bb5  mov     eax, 1
0x180005bba  mov     [rbx+68h], ax
0x180005bbe  jmp     short loc_180005B86
0x180005bc0  test    byte ptr [rdi+4], 2
0x180005bc4  jz      short loc_180005BD7
0x180005bc6  mov     edx, 4
0x180005bcb  cmp     [rdi], edx
0x180005bcd  jnz     short loc_180005BD3
0x180005bcf  or      [rbx+68h], ax
0x180005bd3  or      [rbx+68h], dx
0x180005bd7  mov     rcx, [rsp+58h+arg_0]
0x180005bdc  jmp     short loc_180005B86
0x180005bde  mov     ebp, 0Eh
0x180005be3  mov     rbx, [rsp+58h+arg_8]
0x180005be8  mov     eax, ebp
0x180005bea  add     rsp, 20h
0x180005bee  pop     r15
0x180005bf0  pop     r14
0x180005bf2  pop     r13
0x180005bf4  pop     r12
0x180005bf6  pop     rdi
0x180005bf7  pop     rsi
0x180005bf8  pop     rbp
0x180005bf9  retn
```
