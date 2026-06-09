# RejectCheck

- ea: `0x18001faa4`
- end: `0x18001fd4f`
- name: `RejectCheck`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001dd10`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001faa4`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x18001fbb2`: `IPCP: Rejecting IP compression`

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
  v10 = *((_QWORD *)&xmmword_18004C860 + 1);
  v11 = 0;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *, _QWORD, int))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: RejectCheck",
      0,
      v20);
    v10 = *((_QWORD *)&xmmword_18004C860 + 1);
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
        v10 = *((_QWORD *)&xmmword_18004C860 + 1);
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
        v14 = *((_QWORD *)&xmmword_18004C860 + 1);
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
0x18001faa4  mov     [rsp-8+arg_18], rbx
0x18001faa9  push    rbp
0x18001faaa  push    rsi
0x18001faab  push    rdi
0x18001faac  push    r12
0x18001faae  push    r13
0x18001fab0  push    r14
0x18001fab2  push    r15
0x18001fab4  lea     rbp, [rsp-730h]
0x18001fabc  sub     rsp, 830h
0x18001fac3  mov     rax, cs:__security_cookie
0x18001faca  xor     rax, rsp
0x18001facd  mov     [rbp+760h+var_40], rax
0x18001fad4  movzx   r15d, byte ptr [rdx+2]
0x18001fad9  lea     rbx, [rdx+4]
0x18001fadd  mov     r12, [rbp+760h+arg_20]
0x18001fae4  lea     rdi, [r8+4]
0x18001fae8  mov     eax, 100h
0x18001faed  mov     r13, r8
0x18001faf0  imul    r15d, eax
0x18001faf4  mov     r14, rcx
0x18001faf7  movzx   eax, byte ptr [rdx+3]
0x18001fafb  lea     rcx, [rsp+860h+var_83C]; void *
0x18001fb00  sub     ax, 4
0x18001fb04  xor     edx, edx; Val
0x18001fb06  mov     r8d, 7FCh; Size
0x18001fb0c  add     r15w, ax
0x18001fb10  xor     eax, eax
0x18001fb12  mov     [rsp+860h+var_840], eax
0x18001fb16  call    memset_0
0x18001fb1b  mov     rsi, qword ptr cs:xmmword_18004C860+8
0x18001fb22  xor     r9d, r9d
0x18001fb25  test    rsi, rsi
0x18001fb28  jz      short loc_18001FB51
0x18001fb2a  mov     rcx, cs:gRasIpcpEtwContext
0x18001fb31  lea     r8, aIpcpRejectchec; "IPCP: RejectCheck"
0x18001fb38  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fb3f  mov     rdx, rsi
0x18001fb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb47  mov     rsi, qword ptr cs:xmmword_18004C860+8
0x18001fb4e  xor     r9d, r9d
0x18001fb51  mov     [r12], r9d
0x18001fb55  mov     ecx, 2
0x18001fb5a  cmp     r15w, cx
0x18001fb5e  jb      loc_18001FD05
0x18001fb64  movzx   edx, byte ptr [rbx+1]
0x18001fb68  cmp     r15w, dx
0x18001fb6c  jb      loc_18001FCFE
0x18001fb72  cmp     [rbx], cl
0x18001fb74  jnz     short loc_18001FBC1
0x18001fb76  cmp     dl, 6
0x18001fb79  jnz     short loc_18001FBA9
0x18001fb7b  movzx   edx, byte ptr [rbx+2]
0x18001fb7f  mov     ecx, 100h
0x18001fb84  movzx   r8d, byte ptr [rbx+3]
0x18001fb89  mov     eax, 2Dh ; '-'
0x18001fb8e  imul    edx, ecx
0x18001fb91  add     r8w, dx
0x18001fb95  cmp     ax, r8w
0x18001fb99  jnz     short loc_18001FBA9
0x18001fb9b  cmp     [r14+0ACh], r9w
0x18001fba3  jnz     loc_18001FCCA
0x18001fba9  test    rsi, rsi
0x18001fbac  jz      loc_18001FCA8
0x18001fbb2  lea     r8, aIpcpRejectingI; "IPCP: Rejecting IP compression"
0x18001fbb9  mov     rdx, rsi
0x18001fbbc  jmp     loc_18001FC8E
0x18001fbc1  cmp     [r14], r9d
0x18001fbc4  jz      short loc_18001FC44
0x18001fbc6  movzx   ecx, byte ptr [rbx]
0x18001fbc9  sub     ecx, 3
0x18001fbcc  jz      short loc_18001FBF4
0x18001fbce  sub     ecx, 7Eh ; '~'
0x18001fbd1  jz      short loc_18001FBF4
0x18001fbd3  sub     ecx, 1
0x18001fbd6  jz      short loc_18001FBF4
0x18001fbd8  sub     ecx, 1
0x18001fbdb  jz      short loc_18001FBF4
0x18001fbdd  cmp     ecx, 1
0x18001fbe0  jz      short loc_18001FBF4
0x18001fbe2  test    rsi, rsi
0x18001fbe5  jz      loc_18001FCA8
0x18001fbeb  lea     rdx, aIpcpRejectingX; "IPCP: Rejecting $%x"
0x18001fbf2  jmp     short loc_18001FC6E
0x18001fbf4  cmp     dl, 6
0x18001fbf7  jnz     short loc_18001FBE2
0x18001fbf9  cmp     [rbx+2], r9d
0x18001fbfd  jnz     loc_18001FCCA
0x18001fc03  cmp     byte ptr [rbx], 81h
0x18001fc06  jnz     short loc_18001FC16
0x18001fc08  cmp     [r14+80h], r9d
0x18001fc0f  jz      short loc_18001FBE2
0x18001fc11  jmp     loc_18001FCCA
0x18001fc16  cmp     byte ptr [rbx], 82h
0x18001fc19  jnz     short loc_18001FC21
0x18001fc1b  cmp     [r14+78h], r9d
0x18001fc1f  jz      short loc_18001FBE2
0x18001fc21  cmp     byte ptr [rbx], 83h
0x18001fc24  jnz     short loc_18001FC2F
0x18001fc26  cmp     [r14+84h], r9d
0x18001fc2d  jz      short loc_18001FBE2
0x18001fc2f  cmp     byte ptr [rbx], 84h
0x18001fc32  jnz     loc_18001FCCA
0x18001fc38  cmp     [r14+7Ch], r9d
0x18001fc3c  jnz     loc_18001FCCA
0x18001fc42  jmp     short loc_18001FBE2
0x18001fc44  cmp     byte ptr [rbx], 3
0x18001fc47  jnz     short loc_18001FC62
0x18001fc49  cmp     dl, 6
0x18001fc4c  jnz     short loc_18001FC62
0x18001fc4e  mov     eax, [rbx+2]
0x18001fc51  test    eax, eax
0x18001fc53  jnz     loc_18001FCE1
0x18001fc59  cmp     [r14+828h], ecx
0x18001fc60  jz      short loc_18001FCCA
0x18001fc62  test    rsi, rsi
0x18001fc65  jz      short loc_18001FCA8
0x18001fc67  lea     rdx, aIpcpRejectingD; "IPCP: Rejecting %d"
0x18001fc6e  mov     word ptr [rsp+860h+var_840], r9w
0x18001fc74  lea     rcx, [rsp+860h+var_840]
0x18001fc79  movzx   r8d, byte ptr [rbx]
0x18001fc7d  call    FormatRRASErrorString
0x18001fc82  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fc89  lea     r8, [rsp+860h+var_840]
0x18001fc8e  mov     rcx, cs:gRasIpcpEtwContext
0x18001fc95  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fca1  mov     rsi, qword ptr cs:xmmword_18004C860+8
0x18001fca8  mov     dword ptr [r12], 1
0x18001fcb0  mov     rdx, rbx; Src
0x18001fcb3  movzx   r8d, byte ptr [rbx+1]; Size
0x18001fcb8  mov     rcx, rdi; void *
0x18001fcbb  call    memcpy_0
0x18001fcc0  movzx   eax, byte ptr [rbx+1]
0x18001fcc4  add     rdi, rax
0x18001fcc7  xor     r9d, r9d
0x18001fcca  movzx   ecx, byte ptr [rbx+1]
0x18001fcce  test    cl, cl
0x18001fcd0  jz      short loc_18001FCF3
0x18001fcd2  movzx   eax, cx
0x18001fcd5  cmp     cx, r15w
0x18001fcd9  jnb     short loc_18001FCF3
0x18001fcdb  sub     r15w, ax
0x18001fcdf  jmp     short loc_18001FCF6
0x18001fce1  cmp     [r14+828h], ecx
0x18001fce8  jz      short loc_18001FCCA
0x18001fcea  mov     [r14+94h], eax
0x18001fcf1  jmp     short loc_18001FCCA
0x18001fcf3  mov     r15d, r9d
0x18001fcf6  add     rbx, rcx
0x18001fcf9  jmp     loc_18001FB55
0x18001fcfe  mov     eax, 2D2h
0x18001fd03  jmp     short loc_18001FD25
0x18001fd05  cmp     [r12], r9d
0x18001fd09  jz      short loc_18001FD23
0x18001fd0b  sub     di, r13w
0x18001fd0f  mov     byte ptr [r13+0], 4
0x18001fd14  movzx   eax, di
0x18001fd17  mov     [r13+3], dil
0x18001fd1b  shr     ax, 8
0x18001fd1f  mov     [r13+2], al
0x18001fd23  xor     eax, eax
0x18001fd25  mov     rcx, [rbp+760h+var_40]
0x18001fd2c  xor     rcx, rsp; StackCookie
0x18001fd2f  call    __security_check_cookie
0x18001fd34  mov     rbx, [rsp+860h+arg_18]
0x18001fd3c  add     rsp, 830h
0x18001fd43  pop     r15
0x18001fd45  pop     r14
0x18001fd47  pop     r13
0x18001fd49  pop     r12
0x18001fd4b  pop     rdi
0x18001fd4c  pop     rsi
0x18001fd4d  pop     rbp
0x18001fd4e  retn
```
