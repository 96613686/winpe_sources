# RejectCheck

- ea: `0x18002066c`
- end: `0x180020918`
- name: `RejectCheck`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e830`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002066c`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x18002077a`: `IPCP: Rejecting IP compression`

## pseudocode

```c
__int64 __fastcall RejectCheck(__int64 a1, unsigned __int8 *a2, _BYTE *a3, __int64 a4, _DWORD *a5)
{
  unsigned __int8 *v5; // rbx
  char *v6; // rdi
  unsigned __int16 v9; // r15
  __int64 v10; // rsi
  __int64 v11; // r9
  unsigned __int16 v12; // dx
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  const wchar_t *v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  __int16 v19; // di
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v5 = a2 + 4;
  v6 = a3 + 4;
  v9 = a2[3] - 4 + (a2[2] << 8);
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v10 = *((_QWORD *)&xmmword_18004D860 + 1);
  v11 = 0;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD, int))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: RejectCheck",
      0,
      v20);
    v10 = *((_QWORD *)&xmmword_18004D860 + 1);
    v11 = 0;
  }
  *a5 = 0;
  while ( v9 >= 2u )
  {
    v12 = v5[1];
    if ( v9 < v12 )
      return 722;
    if ( *v5 == 2 )
    {
      if ( (_BYTE)v12 != 6 || (v5[2] << 8) + v5[3] != 45 || !*(_WORD *)(a1 + 172) )
      {
        if ( !v10 )
          goto LABEL_39;
        v13 = L"IPCP: Rejecting IP compression";
        v14 = v10;
LABEL_38:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v14,
          v13,
          v11);
        v10 = *((_QWORD *)&xmmword_18004D860 + 1);
        goto LABEL_39;
      }
    }
    else if ( *(_DWORD *)a1 )
    {
      if ( *v5 != 3 && *v5 != 129 && *v5 != 130 && (unsigned int)*v5 - 131 >= 2 || (_BYTE)v12 != 6 )
        goto LABEL_17;
      if ( !*(_DWORD *)(v5 + 2) )
      {
        if ( *v5 == 0x81 )
        {
          if ( *(_DWORD *)(a1 + 128) )
            goto LABEL_40;
        }
        else if ( (*v5 != 0x82 || *(_DWORD *)(a1 + 120))
               && (*v5 != 0x83 || *(_DWORD *)(a1 + 132))
               && (*v5 != 0x84 || *(_DWORD *)(a1 + 124)) )
        {
          goto LABEL_40;
        }
LABEL_17:
        if ( v10 )
        {
          v15 = L"IPCP: Rejecting $%x";
          goto LABEL_37;
        }
LABEL_39:
        *a5 = 1;
        memcpy_0(v6, v5, v5[1]);
        v6 += v5[1];
        v11 = 0;
      }
    }
    else
    {
      if ( *v5 != 3 || (_BYTE)v12 != 6 )
      {
LABEL_35:
        if ( !v10 )
          goto LABEL_39;
        v15 = L"IPCP: Rejecting %d";
LABEL_37:
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, v15, *v5);
        v14 = *((_QWORD *)&xmmword_18004D860 + 1);
        v13 = (const wchar_t *)&v20;
        goto LABEL_38;
      }
      v16 = *(_DWORD *)(v5 + 2);
      if ( v16 )
      {
        if ( *(_DWORD *)(a1 + 2088) != 2 )
          *(_DWORD *)(a1 + 148) = v16;
      }
      else if ( *(_DWORD *)(a1 + 2088) != 2 )
      {
        goto LABEL_35;
      }
    }
LABEL_40:
    v17 = v5[1];
    if ( (_BYTE)v17 && (unsigned __int16)v17 < v9 )
      v9 -= v17;
    else
      v9 = 0;
    v5 += v17;
  }
  if ( *a5 )
  {
    v19 = (_WORD)v6 - (_WORD)a3;
    *a3 = 4;
    a3[3] = v19;
    a3[2] = HIBYTE(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18002066c  mov     [rsp-8+arg_18], rbx
0x180020671  push    rbp
0x180020672  push    rsi
0x180020673  push    rdi
0x180020674  push    r12
0x180020676  push    r13
0x180020678  push    r14
0x18002067a  push    r15
0x18002067c  lea     rbp, [rsp-730h]
0x180020684  sub     rsp, 830h
0x18002068b  mov     rax, cs:__security_cookie
0x180020692  xor     rax, rsp
0x180020695  mov     [rbp+760h+var_40], rax
0x18002069c  movzx   r15d, byte ptr [rdx+2]
0x1800206a1  lea     rbx, [rdx+4]
0x1800206a5  mov     r12, [rbp+760h+arg_20]
0x1800206ac  lea     rdi, [r8+4]
0x1800206b0  mov     eax, 100h
0x1800206b5  mov     r13, r8
0x1800206b8  imul    r15d, eax
0x1800206bc  mov     r14, rcx
0x1800206bf  movzx   eax, byte ptr [rdx+3]
0x1800206c3  lea     rcx, [rsp+860h+var_83C]; void *
0x1800206c8  sub     ax, 4
0x1800206cc  xor     edx, edx; Val
0x1800206ce  mov     r8d, 7FCh; Size
0x1800206d4  add     r15w, ax
0x1800206d8  xor     eax, eax
0x1800206da  mov     [rsp+860h+var_840], eax
0x1800206de  call    memset_0
0x1800206e3  mov     rsi, qword ptr cs:xmmword_18004D860+8
0x1800206ea  xor     r9d, r9d
0x1800206ed  test    rsi, rsi
0x1800206f0  jz      short loc_180020719
0x1800206f2  mov     rcx, cs:gRasIpcpEtwContext
0x1800206f9  lea     r8, aIpcpRejectchec; "IPCP: RejectCheck"
0x180020700  mov     rax, cs:gRasIpcpTemplateFunc
0x180020707  mov     rdx, rsi
0x18002070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002070f  mov     rsi, qword ptr cs:xmmword_18004D860+8
0x180020716  xor     r9d, r9d
0x180020719  mov     [r12], r9d
0x18002071d  mov     ecx, 2
0x180020722  cmp     r15w, cx
0x180020726  jb      loc_1800208CD
0x18002072c  movzx   edx, byte ptr [rbx+1]
0x180020730  cmp     r15w, dx
0x180020734  jb      loc_1800208C6
0x18002073a  cmp     [rbx], cl
0x18002073c  jnz     short loc_180020789
0x18002073e  cmp     dl, 6
0x180020741  jnz     short loc_180020771
0x180020743  movzx   edx, byte ptr [rbx+2]
0x180020747  mov     ecx, 100h
0x18002074c  movzx   r8d, byte ptr [rbx+3]
0x180020751  mov     eax, 2Dh ; '-'
0x180020756  imul    edx, ecx
0x180020759  add     r8w, dx
0x18002075d  cmp     ax, r8w
0x180020761  jnz     short loc_180020771
0x180020763  cmp     [r14+0ACh], r9w
0x18002076b  jnz     loc_180020892
0x180020771  test    rsi, rsi
0x180020774  jz      loc_180020870
0x18002077a  lea     r8, aIpcpRejectingI; "IPCP: Rejecting IP compression"
0x180020781  mov     rdx, rsi
0x180020784  jmp     loc_180020856
0x180020789  cmp     [r14], r9d
0x18002078c  jz      short loc_18002080C
0x18002078e  movzx   ecx, byte ptr [rbx]
0x180020791  sub     ecx, 3
0x180020794  jz      short loc_1800207BC
0x180020796  sub     ecx, 7Eh ; '~'
0x180020799  jz      short loc_1800207BC
0x18002079b  sub     ecx, 1
0x18002079e  jz      short loc_1800207BC
0x1800207a0  sub     ecx, 1
0x1800207a3  jz      short loc_1800207BC
0x1800207a5  cmp     ecx, 1
0x1800207a8  jz      short loc_1800207BC
0x1800207aa  test    rsi, rsi
0x1800207ad  jz      loc_180020870
0x1800207b3  lea     rdx, aIpcpRejectingX; "IPCP: Rejecting $%x"
0x1800207ba  jmp     short loc_180020836
0x1800207bc  cmp     dl, 6
0x1800207bf  jnz     short loc_1800207AA
0x1800207c1  cmp     [rbx+2], r9d
0x1800207c5  jnz     loc_180020892
0x1800207cb  cmp     byte ptr [rbx], 81h
0x1800207ce  jnz     short loc_1800207DE
0x1800207d0  cmp     [r14+80h], r9d
0x1800207d7  jz      short loc_1800207AA
0x1800207d9  jmp     loc_180020892
0x1800207de  cmp     byte ptr [rbx], 82h
0x1800207e1  jnz     short loc_1800207E9
0x1800207e3  cmp     [r14+78h], r9d
0x1800207e7  jz      short loc_1800207AA
0x1800207e9  cmp     byte ptr [rbx], 83h
0x1800207ec  jnz     short loc_1800207F7
0x1800207ee  cmp     [r14+84h], r9d
0x1800207f5  jz      short loc_1800207AA
0x1800207f7  cmp     byte ptr [rbx], 84h
0x1800207fa  jnz     loc_180020892
0x180020800  cmp     [r14+7Ch], r9d
0x180020804  jnz     loc_180020892
0x18002080a  jmp     short loc_1800207AA
0x18002080c  cmp     byte ptr [rbx], 3
0x18002080f  jnz     short loc_18002082A
0x180020811  cmp     dl, 6
0x180020814  jnz     short loc_18002082A
0x180020816  mov     eax, [rbx+2]
0x180020819  test    eax, eax
0x18002081b  jnz     loc_1800208A9
0x180020821  cmp     [r14+828h], ecx
0x180020828  jz      short loc_180020892
0x18002082a  test    rsi, rsi
0x18002082d  jz      short loc_180020870
0x18002082f  lea     rdx, aIpcpRejectingD; "IPCP: Rejecting %d"
0x180020836  mov     word ptr [rsp+860h+var_840], r9w
0x18002083c  lea     rcx, [rsp+860h+var_840]
0x180020841  movzx   r8d, byte ptr [rbx]
0x180020845  call    FormatRRASErrorString
0x18002084a  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x180020851  lea     r8, [rsp+860h+var_840]
0x180020856  mov     rcx, cs:gRasIpcpEtwContext
0x18002085d  mov     rax, cs:gRasIpcpTemplateFunc
0x180020864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020869  mov     rsi, qword ptr cs:xmmword_18004D860+8
0x180020870  mov     dword ptr [r12], 1
0x180020878  mov     rdx, rbx; Src
0x18002087b  movzx   r8d, byte ptr [rbx+1]; Size
0x180020880  mov     rcx, rdi; void *
0x180020883  call    memcpy_0
0x180020888  movzx   eax, byte ptr [rbx+1]
0x18002088c  add     rdi, rax
0x18002088f  xor     r9d, r9d
0x180020892  movzx   ecx, byte ptr [rbx+1]
0x180020896  test    cl, cl
0x180020898  jz      short loc_1800208BB
0x18002089a  movzx   eax, cx
0x18002089d  cmp     cx, r15w
0x1800208a1  jnb     short loc_1800208BB
0x1800208a3  sub     r15w, ax
0x1800208a7  jmp     short loc_1800208BE
0x1800208a9  cmp     [r14+828h], ecx
0x1800208b0  jz      short loc_180020892
0x1800208b2  mov     [r14+94h], eax
0x1800208b9  jmp     short loc_180020892
0x1800208bb  mov     r15d, r9d
0x1800208be  add     rbx, rcx
0x1800208c1  jmp     loc_18002071D
0x1800208c6  mov     eax, 2D2h
0x1800208cb  jmp     short loc_1800208ED
0x1800208cd  cmp     [r12], r9d
0x1800208d1  jz      short loc_1800208EB
0x1800208d3  sub     di, r13w
0x1800208d7  mov     byte ptr [r13+0], 4
0x1800208dc  movzx   eax, di
0x1800208df  mov     [r13+3], dil
0x1800208e3  shr     ax, 8
0x1800208e7  mov     [r13+2], al
0x1800208eb  xor     eax, eax
0x1800208ed  mov     rcx, [rbp+760h+var_40]
0x1800208f4  xor     rcx, rsp; StackCookie
0x1800208f7  call    __security_check_cookie
0x1800208fc  mov     rbx, [rsp+860h+arg_18]
0x180020904  add     rsp, 830h
0x18002090b  pop     r15
0x18002090d  pop     r14
0x18002090f  pop     r13
0x180020911  pop     r12
0x180020913  pop     rdi
0x180020914  pop     rsi
0x180020915  pop     rbp
0x180020916  retn
```
