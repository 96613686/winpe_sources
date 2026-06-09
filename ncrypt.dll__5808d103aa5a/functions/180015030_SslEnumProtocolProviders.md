# SslEnumProtocolProviders

- ea: `0x180015030`
- end: `0x1800152c0`
- name: `SslEnumProtocolProviders`
- size: `656`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000c8e0`
- `0x18000e120`
- `0x180015030`
- `0x18001f15d`

## import_xrefs

- `bcrypt!BCryptResolveProviders` at `0x1800150a5`
- `bcrypt!BCryptResolveProviders` at `0x1800150a5`
- `bcrypt!BCryptFreeBuffer` at `0x1800152b5`
- `bcrypt!BCryptFreeBuffer` at `0x1800152b5`

## string_xrefs

- `0x180015290`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslEnumProtocolProviders(
        unsigned int *a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        PBYTE a5,
        DWORD *a6,
        DWORD *a7)
{
  NTSTATUS v9; // ebx
  int v10; // esi
  int v11; // ebx
  unsigned int v12; // ebx
  __int64 v13; // rax
  NCryptKeyName **v14; // r8
  NCryptAlgorithmName **v15; // r9
  __int64 v16; // rsi
  _QWORD *v17; // rdx
  unsigned int v18; // r14d
  unsigned int v19; // edi
  char *v20; // rbp
  __int64 v21; // r11
  unsigned __int16 *v22; // rax
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // rax
  size_t v26; // rbx
  unsigned int v28; // edx
  __int64 v29; // r14
  unsigned int i; // r8d
  unsigned __int16 *v31; // rax
  int v32; // ecx
  int v33; // r10d
  __int64 v34; // rax
  __int64 v35; // r9
  ULONG v36; // [rsp+80h] [rbp+8h] BYREF
  PVOID pvBuffer; // [rsp+98h] [rbp+20h] BYREF

  pvBuffer = 0;
  v36 = 0;
  if ( !a1 || !a2 )
  {
    v9 = -2146893785;
    v35 = 1591;
    goto LABEL_41;
  }
  if ( a3 )
  {
    v9 = -2146893815;
    v35 = 1599;
LABEL_41:
    DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v35);
    v17 = pvBuffer;
    goto LABEL_20;
  }
  *a1 = 0;
  *a2 = 0;
  v9 = BCryptResolveProviders(0, 0x10002u, 0, 0, 1u, 3u, &v36, (PCRYPT_PROVIDER_REFS *)&pvBuffer);
  if ( v9 < 0 )
  {
    v35 = 1623;
    goto LABEL_41;
  }
  v10 = 0;
  v11 = 0;
  if ( *(_DWORD *)pvBuffer )
  {
    v28 = 0;
    do
    {
      if ( !v28 )
        goto LABEL_34;
      v29 = *((_QWORD *)pvBuffer + 1);
      for ( i = 0; i < v28; ++i )
      {
        v31 = *(unsigned __int16 **)(*(_QWORD *)(v29 + 8LL * v28) + 16LL);
        do
        {
          v32 = *(unsigned __int16 *)((char *)v31
                                    + *(_QWORD *)(*(_QWORD *)(v29 + 8LL * i) + 16LL)
                                    - *(_QWORD *)(*(_QWORD *)(v29 + 8LL * v28) + 16LL));
          v33 = *v31 - v32;
          if ( v33 )
            break;
          ++v31;
        }
        while ( v32 );
        if ( !v33 )
          break;
      }
      if ( i >= v28 )
      {
LABEL_34:
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v28) + 16LL) + 2 * v34) );
        v10 += 2 * v34 + 2;
        ++v11;
      }
      ++v28;
    }
    while ( v28 < *(_DWORD *)pvBuffer );
  }
  v12 = 16 * v11;
  v13 = SafeAllocaAllocateFromHeap(v12 + v10);
  v16 = v13;
  if ( !v13 )
  {
    v9 = -2146893810;
    v35 = 1669;
    goto LABEL_41;
  }
  v17 = pvBuffer;
  v18 = 0;
  v19 = 0;
  v20 = (char *)(v13 + v12);
  if ( *(_DWORD *)pvBuffer )
  {
    do
    {
      if ( v19 )
      {
        v21 = v17[1];
        v14 = 0;
        while ( 1 )
        {
          v22 = *(unsigned __int16 **)(*(_QWORD *)(v21 + 8LL * v19) + 16LL);
          do
          {
            v23 = *(unsigned __int16 *)((char *)v22
                                      + *(_QWORD *)(*(_QWORD *)(v21 + 8LL * (unsigned int)v14) + 16LL)
                                      - *(_QWORD *)(*(_QWORD *)(v21 + 8LL * v19) + 16LL));
            v15 = (NCryptAlgorithmName **)((unsigned int)*v22 - v23);
            if ( (_DWORD)v15 )
              break;
            ++v22;
          }
          while ( v23 );
          if ( !(_DWORD)v15 )
            break;
          v14 = (NCryptKeyName **)(unsigned int)((_DWORD)v14 + 1);
          if ( (unsigned int)v14 >= v19 )
            goto LABEL_15;
        }
      }
      else
      {
LABEL_15:
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v17[1] + 8LL * v19) + 16LL) + 2 * v24) );
        v25 = 2LL * v18;
        v26 = 2LL * (unsigned int)(v24 + 1);
        *(_QWORD *)(v16 + 8 * v25) = v20;
        *(_QWORD *)(v16 + 8 * v25 + 8) = 0;
        memcpy_0(v20, *(const void **)(*(_QWORD *)(*((_QWORD *)pvBuffer + 1) + 8LL * v19) + 16LL), v26);
        v17 = pvBuffer;
        v20 += v26;
        ++v18;
      }
      ++v19;
    }
    while ( v19 < *(_DWORD *)v17 );
  }
  *a1 = v18;
  v9 = 0;
  *a2 = v16;
LABEL_20:
  if ( v17 )
    BCryptFreeBuffer(v17);
  return NormalizeNteStatus((unsigned int)v9, v17, v14, v15, a5, a6, a7);
}

```

## disassembly

```asm
0x180015030  mov     r11, rsp
0x180015033  mov     [r11+10h], rbx
0x180015037  push    rbp
0x180015038  push    rsi
0x180015039  push    rdi
0x18001503a  push    r12
0x18001503c  push    r13
0x18001503e  push    r14
0x180015040  push    r15
0x180015042  sub     rsp, 40h
0x180015046  xor     r13d, r13d
0x180015049  mov     r15, rdx
0x18001504c  mov     [r11+20h], r13
0x180015050  mov     r12, rcx
0x180015053  mov     [r11+8], r13d
0x180015057  test    rcx, rcx
0x18001505a  jz      loc_180015285
0x180015060  test    rdx, rdx
0x180015063  jz      loc_180015285
0x180015069  test    r8d, r8d
0x18001506c  jnz     loc_180015263
0x180015072  lea     rax, [r11+20h]
0x180015076  mov     [rcx], r13d
0x180015079  mov     [r11-40h], rax
0x18001507d  xor     r9d, r9d; pszProvider
0x180015080  lea     rax, [r11+8]
0x180015084  mov     [rdx], r13
0x180015087  mov     [r11-48h], rax
0x18001508b  xor     r8d, r8d; pszFunction
0x18001508e  mov     [rsp+78h+dwFlags], 3; dwFlags
0x180015096  mov     edx, 10002h; dwInterface
0x18001509b  xor     ecx, ecx; pszContext
0x18001509d  mov     [rsp+78h+dwMode], 1; dwMode
0x1800150a5  call    cs:__imp_BCryptResolveProviders
0x1800150ab  mov     ebx, eax
0x1800150ad  test    eax, eax
0x1800150af  js      loc_180015270
0x1800150b5  mov     rdi, [rsp+78h+pvBuffer]
0x1800150bd  mov     esi, r13d
0x1800150c0  mov     ebx, r13d
0x1800150c3  cmp     [rdi], r13d
0x1800150c6  ja      loc_1800151E2
0x1800150cc  shl     ebx, 4
0x1800150cf  lea     ecx, [rbx+rsi]
0x1800150d2  call    SafeAllocaAllocateFromHeap
0x1800150d7  mov     rsi, rax
0x1800150da  test    rax, rax
0x1800150dd  jz      loc_180015278
0x1800150e3  mov     rdx, [rsp+78h+pvBuffer]
0x1800150eb  mov     r14d, r13d
0x1800150ee  mov     ebp, ebx
0x1800150f0  mov     edi, r13d
0x1800150f3  add     rbp, rax
0x1800150f6  cmp     [rdx], r13d
0x1800150f9  jbe     loc_1800151B1
0x1800150ff  test    edi, edi
0x180015101  jz      short loc_180015148
0x180015103  mov     r11, [rdx+8]
0x180015107  mov     r8d, r13d
0x18001510a  mov     eax, edi
0x18001510c  mov     rcx, [r11+rax*8]
0x180015110  mov     rbx, [rcx+10h]
0x180015114  mov     eax, r8d
0x180015117  mov     rcx, [r11+rax*8]
0x18001511b  mov     rax, rbx
0x18001511e  mov     r10, [rcx+10h]
0x180015122  sub     r10, rbx
0x180015125  movzx   r9d, word ptr [rax]
0x180015129  movzx   ecx, word ptr [rax+r10]
0x18001512e  sub     r9d, ecx
0x180015131  jnz     short loc_18001513B
0x180015133  add     rax, 2
0x180015137  test    ecx, ecx
0x180015139  jnz     short loc_180015125
0x18001513b  test    r9d, r9d
0x18001513e  jz      short loc_1800151A7
0x180015140  inc     r8d
0x180015143  cmp     r8d, edi
0x180015146  jb      short loc_180015114
0x180015148  mov     rax, [rdx+8]
0x18001514c  mov     r8d, edi
0x18001514f  mov     rcx, [rax+r8*8]
0x180015153  mov     rax, [rcx+10h]
0x180015157  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001515b  inc     rcx
0x18001515e  cmp     [rax+rcx*2], r13w
0x180015163  jnz     short loc_18001515B
0x180015165  lea     ebx, [rcx+1]
0x180015168  mov     eax, r14d
0x18001516b  add     rax, rax
0x18001516e  add     rbx, rbx
0x180015171  mov     [rsi+rax*8], rbp
0x180015175  mov     [rsi+rax*8+8], r13
0x18001517a  mov     rax, [rsp+78h+pvBuffer]
0x180015182  mov     rcx, [rax+8]
0x180015186  mov     rdx, [rcx+r8*8]
0x18001518a  mov     r8, rbx; Size
0x18001518d  mov     rcx, rbp; void *
0x180015190  mov     rdx, [rdx+10h]; Src
0x180015194  call    memcpy_0
0x180015199  mov     rdx, [rsp+78h+pvBuffer]
0x1800151a1  add     rbp, rbx
0x1800151a4  inc     r14d
0x1800151a7  inc     edi
0x1800151a9  cmp     edi, [rdx]
0x1800151ab  jb      loc_1800150FF
0x1800151b1  mov     [r12], r14d
0x1800151b5  mov     ebx, r13d
0x1800151b8  mov     [r15], rsi
0x1800151bb  test    rdx, rdx
0x1800151be  jnz     loc_1800152B2
0x1800151c4  mov     ecx, ebx
0x1800151c6  mov     rbx, [rsp+78h+arg_8]
0x1800151ce  add     rsp, 40h
0x1800151d2  pop     r15
0x1800151d4  pop     r14
0x1800151d6  pop     r13
0x1800151d8  pop     r12
0x1800151da  pop     rdi
0x1800151db  pop     rsi
0x1800151dc  pop     rbp
0x1800151dd  jmp     NormalizeNteStatus
0x1800151e2  mov     edx, r13d
0x1800151e5  mov     r9d, edx
0x1800151e8  test    edx, edx
0x1800151ea  jz      short loc_18001523F
0x1800151ec  mov     r14, [rdi+8]
0x1800151f0  mov     r8d, r13d
0x1800151f3  mov     rax, [r14+r9*8]
0x1800151f7  mov     rbp, [rax+10h]
0x1800151fb  mov     eax, r8d
0x1800151fe  mov     rcx, [r14+rax*8]
0x180015202  mov     rax, rbp
0x180015205  mov     r11, [rcx+10h]
0x180015209  sub     r11, rbp
0x18001520c  movzx   r10d, word ptr [rax]
0x180015210  movzx   ecx, word ptr [rax+r11]
0x180015215  sub     r10d, ecx
0x180015218  jnz     short loc_180015222
0x18001521a  add     rax, 2
0x18001521e  test    ecx, ecx
0x180015220  jnz     short loc_18001520C
0x180015222  test    r10d, r10d
0x180015225  jz      short loc_18001522F
0x180015227  inc     r8d
0x18001522a  cmp     r8d, edx
0x18001522d  jb      short loc_1800151FB
0x18001522f  cmp     r8d, edx
0x180015232  jnb     short loc_18001523F
0x180015234  inc     edx
0x180015236  cmp     edx, [rdi]
0x180015238  jb      short loc_1800151E5
0x18001523a  jmp     loc_1800150CC
0x18001523f  mov     rax, [rdi+8]
0x180015243  mov     rcx, [rax+r9*8]
0x180015247  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001524b  mov     r8, [rcx+10h]
0x18001524f  inc     rax
0x180015252  cmp     [r8+rax*2], r13w
0x180015257  jnz     short loc_18001524F
0x180015259  lea     esi, [rsi+rax*2]
0x18001525c  add     esi, 2
0x18001525f  inc     ebx
0x180015261  jmp     short loc_180015234
0x180015263  mov     ebx, 80090009h
0x180015268  mov     r9d, 63Fh
0x18001526e  jmp     short loc_180015290
0x180015270  mov     r9d, 657h
0x180015276  jmp     short loc_180015290
0x180015278  mov     ebx, 8009000Eh
0x18001527d  mov     r9d, 685h
0x180015283  jmp     short loc_180015290
0x180015285  mov     ebx, 80090027h
0x18001528a  mov     r9d, 637h
0x180015290  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015297  mov     ecx, ebx
0x180015299  lea     rdx, aStatus; "Status"
0x1800152a0  call    DebugTraceError
0x1800152a5  mov     rdx, [rsp+78h+pvBuffer]
0x1800152ad  jmp     loc_1800151BB
0x1800152b2  mov     rcx, rdx; pvBuffer
0x1800152b5  call    cs:__imp_BCryptFreeBuffer
0x1800152bb  jmp     loc_1800151C4
```
