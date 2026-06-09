# CreateBalloonRgn

- ea: `0x18004c7cc`
- end: `0x18004c9ba`
- name: `CreateBalloonRgn`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004ca94`

## callees

- `0x1800115f0`
- `0x18004c7cc`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004c990`
- `GDI32!DeleteObject` at `0x18004c990`
- `GDI32!CreateRoundRectRgn` at `0x18004c82d`
- `GDI32!CreateRoundRectRgn` at `0x18004c82d`
- `GDI32!CreatePolygonRgn` at `0x18004c96a`
- `GDI32!CreatePolygonRgn` at `0x18004c96a`
- `GDI32!CombineRgn` at `0x18004c987`
- `GDI32!CombineRgn` at `0x18004c987`

## pseudocode

```c
HRGN __fastcall CreateBalloonRgn(signed int a1, int a2, int a3, int a4, int y1, int a6, int a7)
{
  int v8; // r14d
  int v10; // r9d
  int v13; // edx
  HRGN RoundRectRgn; // rsi
  int v15; // r10d
  int v16; // r9d
  LONG v17; // r8d
  int v18; // ecx
  LONG v19; // edx
  LONG v20; // ecx
  signed int v21; // r8d
  int v22; // eax
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  signed int v29; // ebx
  HRGN v30; // rax
  HRGN v31; // rbx
  POINT pptl; // [rsp+30h] [rbp-48h] BYREF
  signed int v34; // [rsp+38h] [rbp-40h]
  LONG v35; // [rsp+3Ch] [rbp-3Ch]
  signed int v36; // [rsp+40h] [rbp-38h]
  int v37; // [rsp+44h] [rbp-34h]

  v8 = a4 - y1;
  v10 = a4 - y1;
  if ( !a6 )
    v10 = a4;
  v13 = 0;
  if ( !a6 )
    v13 = y1;
  RoundRectRgn = CreateRoundRectRgn(0, v13, a3, v10, 13, 13);
  if ( RoundRectRgn && a3 >= 30 )
  {
    v15 = y1 + 1;
    if ( a1 == (unsigned int)a3 >> 1 || a3 < y1 + 33 )
    {
      v16 = a7;
      v17 = (a3 - v15) / 2;
      if ( a7 )
        goto LABEL_25;
    }
    else
    {
      v16 = a7;
      if ( a1 <= (int)((unsigned int)a3 >> 1) )
      {
        if ( a7 )
        {
          v17 = a3 - 16;
          goto LABEL_25;
        }
        v17 = 16;
      }
      else
      {
        if ( a7 )
        {
          v17 = y1 + 17;
LABEL_25:
          v24 = -(a1 + v17 - a3);
          if ( a1 + v17 - a3 > 0 )
            v24 = a1 + v17 - a3;
          if ( v24 <= 2 )
            v17 = a3 - a1;
LABEL_17:
          v19 = v8 - 2;
          v20 = v17;
          if ( !a6 )
            v19 = y1 + 2;
          pptl.x = v17;
          pptl.y = v19;
          if ( v16 )
          {
            v21 = v17 - v15;
            v22 = v15 + v20;
            v23 = v21;
          }
          else
          {
            v21 = v15 + v17;
            v22 = v21;
            v23 = v20 - v15;
          }
          if ( v16 )
          {
            v25 = a1 + v23 - a3;
            v26 = -v25;
            if ( v25 > 0 )
              v26 = v25;
            if ( v26 <= 2 )
              v21 = a3 - a1;
          }
          else
          {
            v27 = v22 - a1;
            v28 = a1 - v22;
            if ( v27 > 0 )
              v28 = v27;
            if ( v28 <= 2 )
              v21 = a1;
          }
          v34 = v21;
          v35 = v19;
          if ( v16 )
            v29 = a3 - a1;
          else
            v29 = a1;
          v36 = v29;
          v37 = a2;
          v30 = CreatePolygonRgn(&pptl, 3, 1);
          v31 = v30;
          if ( v30 )
          {
            CombineRgn(RoundRectRgn, RoundRectRgn, v30, 2);
            DeleteObject(v31);
          }
          return RoundRectRgn;
        }
        v17 = a3 - v15 - 16;
      }
    }
    v18 = a1 - v17;
    if ( a1 - v17 < 0 )
      v18 = v17 - a1;
    if ( v18 <= 2 )
      v17 = a1;
    goto LABEL_17;
  }
  return RoundRectRgn;
}

```

## disassembly

```asm
0x18004c7cc  mov     [rsp+arg_0], rbx
0x18004c7d1  push    rbp
0x18004c7d2  push    rsi
0x18004c7d3  push    rdi
0x18004c7d4  push    r12
0x18004c7d6  push    r14
0x18004c7d8  sub     rsp, 50h
0x18004c7dc  mov     rax, cs:__security_cookie
0x18004c7e3  xor     rax, rsp
0x18004c7e6  mov     [rsp+78h+var_30], rax
0x18004c7eb  mov     ebp, [rsp+78h+y1]
0x18004c7f2  mov     r14d, r9d
0x18004c7f5  mov     eax, r9d
0x18004c7f8  sub     r14d, ebp
0x18004c7fb  cmp     [rsp+78h+arg_28], 0
0x18004c803  mov     r12d, edx
0x18004c806  mov     r9d, r14d
0x18004c809  mov     edi, ecx
0x18004c80b  cmovz   r9d, eax; y2
0x18004c80f  mov     ebx, r8d
0x18004c812  xor     edx, edx
0x18004c814  mov     eax, 0Dh
0x18004c819  cmp     [rsp+78h+arg_28], edx
0x18004c820  mov     [rsp+78h+h], eax; h
0x18004c824  cmovz   edx, ebp; y1
0x18004c827  mov     [rsp+78h+w], eax; w
0x18004c82b  xor     ecx, ecx; x1
0x18004c82d  call    cs:__imp_CreateRoundRectRgn
0x18004c833  mov     rsi, rax
0x18004c836  test    rax, rax
0x18004c839  jz      loc_18004C996
0x18004c83f  cmp     ebx, 1Eh
0x18004c842  jl      loc_18004C996
0x18004c848  mov     ecx, ebx
0x18004c84a  lea     r10d, [rbp+1]
0x18004c84e  shr     ecx, 1
0x18004c850  cmp     edi, ecx
0x18004c852  jz      short loc_18004C8D1
0x18004c854  lea     eax, [r10+20h]
0x18004c858  cmp     ebx, eax
0x18004c85a  jl      short loc_18004C8D1
0x18004c85c  mov     r9d, [rsp+78h+arg_30]
0x18004c864  cmp     edi, ecx
0x18004c866  jle     short loc_18004C8BE
0x18004c868  test    r9d, r9d
0x18004c86b  jz      short loc_18004C873
0x18004c86d  lea     r8d, [r10+10h]
0x18004c871  jmp     short loc_18004C8EB
0x18004c873  mov     r8d, ebx
0x18004c876  sub     r8d, r10d
0x18004c879  sub     r8d, 10h
0x18004c87d  mov     eax, r8d
0x18004c880  sub     eax, edi
0x18004c882  mov     ecx, eax
0x18004c884  neg     ecx
0x18004c886  cmovs   ecx, eax
0x18004c889  cmp     ecx, 2
0x18004c88c  cmovle  r8d, edi
0x18004c890  cmp     [rsp+78h+arg_28], 0
0x18004c898  lea     edx, [r14-2]
0x18004c89c  mov     ecx, r8d
0x18004c89f  jnz     short loc_18004C8A4
0x18004c8a1  lea     edx, [rbp+2]
0x18004c8a4  mov     [rsp+78h+pptl.x], r8d
0x18004c8a9  mov     [rsp+78h+pptl.y], edx
0x18004c8ad  test    r9d, r9d
0x18004c8b0  jz      short loc_18004C906
0x18004c8b2  sub     r8d, r10d
0x18004c8b5  lea     eax, [r10+rcx]
0x18004c8b9  mov     ecx, r8d
0x18004c8bc  jmp     short loc_18004C90F
0x18004c8be  test    r9d, r9d
0x18004c8c1  jz      short loc_18004C8C9
0x18004c8c3  lea     r8d, [rbx-10h]
0x18004c8c7  jmp     short loc_18004C8EB
0x18004c8c9  mov     r8d, 10h
0x18004c8cf  jmp     short loc_18004C87D
0x18004c8d1  mov     r9d, [rsp+78h+arg_30]
0x18004c8d9  mov     eax, ebx
0x18004c8db  sub     eax, r10d
0x18004c8de  cdq
0x18004c8df  sub     eax, edx
0x18004c8e1  sar     eax, 1
0x18004c8e3  mov     r8d, eax
0x18004c8e6  test    r9d, r9d
0x18004c8e9  jz      short loc_18004C87D
0x18004c8eb  mov     edx, r8d
0x18004c8ee  sub     edx, ebx
0x18004c8f0  add     edx, edi
0x18004c8f2  mov     ecx, edx
0x18004c8f4  neg     ecx
0x18004c8f6  cmovs   ecx, edx
0x18004c8f9  cmp     ecx, 2
0x18004c8fc  jg      short loc_18004C890
0x18004c8fe  mov     r8d, ebx
0x18004c901  sub     r8d, edi
0x18004c904  jmp     short loc_18004C890
0x18004c906  add     r8d, r10d
0x18004c909  mov     eax, r8d
0x18004c90c  sub     ecx, r10d
0x18004c90f  test    r9d, r9d
0x18004c912  cmovz   ecx, eax
0x18004c915  jz      short loc_18004C92F
0x18004c917  sub     ecx, ebx
0x18004c919  add     ecx, edi
0x18004c91b  mov     eax, ecx
0x18004c91d  neg     eax
0x18004c91f  cmovs   eax, ecx
0x18004c922  cmp     eax, 2
0x18004c925  jg      short loc_18004C93F
0x18004c927  mov     r8d, ebx
0x18004c92a  sub     r8d, edi
0x18004c92d  jmp     short loc_18004C93F
0x18004c92f  sub     ecx, edi
0x18004c931  mov     eax, ecx
0x18004c933  neg     eax
0x18004c935  cmovs   eax, ecx
0x18004c938  cmp     eax, 2
0x18004c93b  cmovle  r8d, edi
0x18004c93f  mov     [rsp+78h+var_40], r8d
0x18004c944  mov     [rsp+78h+var_3C], edx
0x18004c948  test    r9d, r9d
0x18004c94b  jz      short loc_18004C951
0x18004c94d  sub     ebx, edi
0x18004c94f  jmp     short loc_18004C953
0x18004c951  mov     ebx, edi
0x18004c953  mov     edx, 3; cPoint
0x18004c958  mov     [rsp+78h+var_38], ebx
0x18004c95c  lea     rcx, [rsp+78h+pptl]; pptl
0x18004c961  mov     [rsp+78h+var_34], r12d
0x18004c966  lea     r8d, [rdx-2]; iMode
0x18004c96a  call    cs:__imp_CreatePolygonRgn
0x18004c970  mov     rbx, rax
0x18004c973  test    rax, rax
0x18004c976  jz      short loc_18004C996
0x18004c978  mov     r9d, 2; iMode
0x18004c97e  mov     r8, rax; hrgnSrc2
0x18004c981  mov     rdx, rsi; hrgnSrc1
0x18004c984  mov     rcx, rsi; hrgnDst
0x18004c987  call    cs:__imp_CombineRgn
0x18004c98d  mov     rcx, rbx; ho
0x18004c990  call    cs:__imp_DeleteObject
0x18004c996  mov     rax, rsi
0x18004c999  mov     rcx, [rsp+78h+var_30]
0x18004c99e  xor     rcx, rsp; StackCookie
0x18004c9a1  call    __security_check_cookie
0x18004c9a6  mov     rbx, [rsp+78h+arg_0]
0x18004c9ae  add     rsp, 50h
0x18004c9b2  pop     r14
0x18004c9b4  pop     r12
0x18004c9b6  pop     rdi
0x18004c9b7  pop     rsi
0x18004c9b8  pop     rbp
0x18004c9b9  retn
```
