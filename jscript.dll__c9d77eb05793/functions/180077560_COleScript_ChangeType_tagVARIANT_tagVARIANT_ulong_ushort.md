# COleScript::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)

- ea: `0x180077560`
- end: `0x180077814`
- name: `?ChangeType@COleScript@@UEAAJPEAUtagVARIANT@@0KG@Z`
- size: `692`
- prototype: `int(COleScript *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006ed8`
- `0x18000ad6c`
- `0x18000b130`
- `0x180011c70`
- `0x18001a444`
- `0x180077560`

## import_xrefs

- `msvcrt!_controlfp` at `0x1800775a0`
- `msvcrt!_controlfp` at `0x1800775b3`
- `msvcrt!_controlfp` at `0x1800777f8`
- `msvcrt!_controlfp` at `0x1800775a0`
- `msvcrt!_controlfp` at `0x1800775b3`
- `msvcrt!_controlfp` at `0x1800777f8`
- `OLEAUT32!__imp_VariantClear` at `0x1800775f5`
- `OLEAUT32!__imp_VariantClear` at `0x180077605`
- `OLEAUT32!__imp_VariantClear` at `0x1800775f5`
- `OLEAUT32!__imp_VariantClear` at `0x180077605`
- `OLEAUT32!__imp_VariantCopy` at `0x1800777ea`
- `OLEAUT32!__imp_VariantCopy` at `0x1800777ea`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800775e2`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800775e2`

## pseudocode

```c
__int64 __fastcall COleScript::ChangeType(
        COleScript *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        __int64 a4,
        unsigned __int16 a5)
{
  __int64 result; // rax
  unsigned int v9; // r15d
  bool v10; // zf
  HRESULT v11; // ebx
  unsigned int v12; // r14d
  IRecordInfo *pRecInfo; // xmm1_8
  struct CSession *v14; // rcx
  VARIANTARG *v15; // rax
  int v16; // r9d
  int v17; // eax
  VARIANT pvarDest; // [rsp+38h] [rbp-20h] BYREF
  VARIANTARG *pvargSrc; // [rsp+90h] [rbp+38h] BYREF

  result = COleScript::ValidateBaseThread((COleScript *)((char *)this - 112));
  if ( (int)result >= 0 )
  {
    if ( a2 && a3 )
    {
      v9 = _controlfp(0, 0);
      _controlfp(0x1Fu, 0x30F031Fu);
      v10 = *((_QWORD *)this + 70) == 0;
      pvargSrc = 0;
      if ( v10 )
      {
        v11 = -2147418113;
        goto LABEL_41;
      }
      pvarDest.vt = 0;
      v11 = VariantCopyInd(&pvarDest, a3);
      if ( v11 < 0 )
        goto LABEL_41;
      v11 = VariantClear(a2);
      if ( v11 < 0 )
        goto LABEL_8;
      v12 = a5;
      if ( pvarDest.vt == a5 )
      {
        v11 = 0;
        pRecInfo = pvarDest.pRecInfo;
        *(_OWORD *)&a2->vt = *(_OWORD *)&pvarDest.vt;
        a2->pRecInfo = pRecInfo;
        goto LABEL_41;
      }
      v11 = VAR::Import((VAR *)&pvarDest, *((struct CSession **)this + 70));
      if ( v11 < 0 )
      {
LABEL_8:
        VariantClear(&pvarDest);
        goto LABEL_41;
      }
      pvargSrc = &pvarDest;
      if ( v12 > 0xB )
      {
        if ( v12 != 16 && v12 != 17 )
        {
          v16 = 3;
          if ( v12 != 18 && v12 != 19 && v12 - 22 >= 2 )
            return 2147500033LL;
          goto LABEL_38;
        }
      }
      else
      {
        if ( v12 == 11 )
        {
          v17 = ConvertToScalar(
                  *((struct CSession **)this + 70),
                  (struct VAR *)&pvarDest,
                  (struct VAR *)&pvarDest,
                  11,
                  0);
          goto LABEL_39;
        }
        if ( v12 != 2 && v12 != 3 )
        {
          switch ( v12 )
          {
            case 4u:
              v11 = ConvertToScalar(
                      *((struct CSession **)this + 70),
                      (struct VAR *)&pvarDest,
                      (struct VAR *)&pvarDest,
                      5,
                      1);
              if ( v11 < 0 )
                goto LABEL_41;
              pvargSrc->fltVal = pvargSrc->dblVal;
              goto LABEL_40;
            case 5u:
              v16 = 5;
              break;
            case 7u:
              v16 = 7;
              break;
            case 8u:
              v14 = (struct CSession *)*((_QWORD *)this + 70);
              if ( ((pvarDest.vt - 3) & 0xFFFD) == 0 )
              {
                v11 = ConvertNumberToString(v14, (struct VAR **)&pvargSrc);
                if ( v11 >= 0 )
                {
                  v15 = pvargSrc;
                  a2->vt = 8;
                  a2->llVal = v15->llVal;
                }
                goto LABEL_41;
              }
              v11 = ConvertToString(v14, (struct VAR **)&pvargSrc, (struct VAR *)&pvarDest, 1);
              if ( v11 < 0 )
              {
LABEL_41:
                _controlfp(v9, 0xFFFFFFFF);
                return (unsigned int)v11;
              }
              if ( pvargSrc->vt == 130 )
              {
                pvarDest.vt = 8;
                pvarDest.llVal = pvargSrc->llVal;
                pvargSrc = &pvarDest;
              }
LABEL_40:
              pvargSrc->vt = v12;
              v11 = VariantCopy(a2, pvargSrc);
              goto LABEL_41;
            default:
              return 2147500033LL;
          }
          goto LABEL_38;
        }
      }
      v16 = 3;
LABEL_38:
      v17 = ConvertToScalar(*((struct CSession **)this + 70), (struct VAR *)&pvarDest, (struct VAR *)&pvarDest, v16, 1);
LABEL_39:
      v11 = v17;
      if ( v17 < 0 )
        goto LABEL_41;
      goto LABEL_40;
    }
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180077560  push    rbp
0x180077562  push    rbx
0x180077563  push    rsi
0x180077564  push    rdi
0x180077565  push    r14
0x180077567  push    r15
0x180077569  mov     rbp, rsp
0x18007756c  sub     rsp, 58h
0x180077570  mov     rdi, rcx
0x180077573  mov     rbx, r8
0x180077576  add     rcx, 0FFFFFFFFFFFFFF90h; this
0x18007757a  mov     rsi, rdx
0x18007757d  call    ?ValidateBaseThread@COleScript@@AEAAJXZ; COleScript::ValidateBaseThread(void)
0x180077582  test    eax, eax
0x180077584  js      loc_180077807
0x18007758a  test    rsi, rsi
0x18007758d  jz      loc_180077802
0x180077593  test    rbx, rbx
0x180077596  jz      loc_180077802
0x18007759c  xor     edx, edx; Mask
0x18007759e  xor     ecx, ecx; NewValue
0x1800775a0  call    cs:__imp__controlfp
0x1800775a6  mov     edx, 30F031Fh; Mask
0x1800775ab  mov     ecx, 1Fh; NewValue
0x1800775b0  mov     r15d, eax
0x1800775b3  call    cs:__imp__controlfp
0x1800775b9  cmp     qword ptr [rdi+230h], 0
0x1800775c1  mov     [rbp+pvargSrc], 0
0x1800775c9  jnz     short loc_1800775D5
0x1800775cb  mov     ebx, 8000FFFFh
0x1800775d0  jmp     loc_1800777F2
0x1800775d5  xor     eax, eax
0x1800775d7  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800775db  mov     rdx, rbx; pvargSrc
0x1800775de  mov     word ptr [rbp+pvarDest], ax
0x1800775e2  call    cs:__imp_VariantCopyInd
0x1800775e8  mov     ebx, eax
0x1800775ea  test    eax, eax
0x1800775ec  js      loc_1800777F2
0x1800775f2  mov     rcx, rsi; pvarg
0x1800775f5  call    cs:__imp_VariantClear
0x1800775fb  mov     ebx, eax
0x1800775fd  test    eax, eax
0x1800775ff  jns     short loc_180077610
0x180077601  lea     rcx, [rbp+pvarDest]; pvarg
0x180077605  call    cs:__imp_VariantClear
0x18007760b  jmp     loc_1800777F2
0x180077610  movzx   r14d, [rbp+arg_20]
0x180077615  cmp     word ptr [rbp+pvarDest], r14w
0x18007761a  jnz     short loc_180077634
0x18007761c  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180077620  xor     ebx, ebx
0x180077622  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180077627  movups  xmmword ptr [rsi], xmm0
0x18007762a  movsd   qword ptr [rsi+10h], xmm1
0x18007762f  jmp     loc_1800777F2
0x180077634  mov     rdx, [rdi+230h]; struct CSession *
0x18007763b  lea     rcx, [rbp+pvarDest]; this
0x18007763f  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x180077644  mov     ebx, eax
0x180077646  test    eax, eax
0x180077648  js      short loc_180077601
0x18007764a  mov     r9d, 0Bh
0x180077650  lea     rax, [rbp+pvarDest]
0x180077654  mov     [rbp+pvargSrc], rax
0x180077658  mov     ecx, r14d
0x18007765b  cmp     r14d, r9d
0x18007765e  ja      loc_180077788
0x180077664  jz      loc_18007777E
0x18007766a  sub     ecx, 2
0x18007766d  jz      loc_1800777B3
0x180077673  sub     ecx, 1
0x180077676  jz      loc_1800777B3
0x18007767c  sub     ecx, 1
0x18007767f  jz      loc_18007773E
0x180077685  sub     ecx, 1
0x180077688  jz      loc_180077736
0x18007768e  sub     ecx, 2
0x180077691  jz      loc_18007772B
0x180077697  cmp     ecx, 1
0x18007769a  jnz     loc_1800777AC
0x1800776a0  movzx   eax, word ptr [rbp+pvarDest]
0x1800776a4  lea     rdx, [rbp+pvargSrc]; struct VAR **
0x1800776a8  mov     ecx, 0FFFDh
0x1800776ad  sub     ax, 3
0x1800776b1  test    cx, ax
0x1800776b4  mov     rcx, [rdi+230h]; this
0x1800776bb  jz      short loc_180077706
0x1800776bd  mov     r9d, 1; int
0x1800776c3  lea     r8, [rbp+pvarDest]; struct VAR *
0x1800776c7  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x1800776cc  mov     ebx, eax
0x1800776ce  test    eax, eax
0x1800776d0  js      loc_1800777F2
0x1800776d6  mov     rcx, [rbp+pvargSrc]
0x1800776da  mov     eax, 82h
0x1800776df  cmp     [rcx], ax
0x1800776e2  jnz     loc_1800777DB
0x1800776e8  mov     eax, 8
0x1800776ed  mov     word ptr [rbp+pvarDest], ax
0x1800776f1  mov     rax, [rcx+8]
0x1800776f5  mov     qword ptr [rbp+pvarDest+8], rax
0x1800776f9  lea     rax, [rbp+pvarDest]
0x1800776fd  mov     [rbp+pvargSrc], rax
0x180077701  jmp     loc_1800777DB
0x180077706  call    ?ConvertNumberToString@@YAJPEAVCSession@@PEAPEAVVAR@@@Z; ConvertNumberToString(CSession *,VAR * *)
0x18007770b  mov     ebx, eax
0x18007770d  test    eax, eax
0x18007770f  js      loc_1800777F2
0x180077715  mov     rax, [rbp+pvargSrc]
0x180077719  mov     word ptr [rsi], 8
0x18007771e  mov     rcx, [rax+8]
0x180077722  mov     [rsi+8], rcx
0x180077726  jmp     loc_1800777F2
0x18007772b  mov     r9d, 7
0x180077731  jmp     loc_1800777B9
0x180077736  mov     r9d, 5
0x18007773c  jmp     short loc_1800777B9
0x18007773e  mov     rcx, [rdi+230h]; struct CSession *
0x180077745  lea     r8, [rbp+pvarDest]; struct VAR *
0x180077749  mov     r9d, 5; int
0x18007774f  mov     [rsp+58h+var_38], 1; int
0x180077757  lea     rdx, [rbp+pvarDest]; this
0x18007775b  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x180077760  mov     ebx, eax
0x180077762  test    eax, eax
0x180077764  js      loc_1800777F2
0x18007776a  mov     rax, [rbp+pvargSrc]
0x18007776e  movsd   xmm0, qword ptr [rax+8]
0x180077773  cvtpd2ps xmm0, xmm0
0x180077777  movss   dword ptr [rax+8], xmm0
0x18007777c  jmp     short loc_1800777DB
0x18007777e  mov     [rsp+58h+var_38], 0
0x180077786  jmp     short loc_1800777C1
0x180077788  sub     ecx, 10h
0x18007778b  jz      short loc_1800777B3
0x18007778d  sub     ecx, 1
0x180077790  jz      short loc_1800777B3
0x180077792  mov     r9d, 3
0x180077798  sub     ecx, 1
0x18007779b  jz      short loc_1800777B9
0x18007779d  sub     ecx, 1
0x1800777a0  jz      short loc_1800777B9
0x1800777a2  sub     ecx, r9d
0x1800777a5  jz      short loc_1800777B9
0x1800777a7  cmp     ecx, 1
0x1800777aa  jz      short loc_1800777B9
0x1800777ac  mov     eax, 80004001h
0x1800777b1  jmp     short loc_180077807
0x1800777b3  mov     r9d, 3; int
0x1800777b9  mov     [rsp+58h+var_38], 1; int
0x1800777c1  mov     rcx, [rdi+230h]; struct CSession *
0x1800777c8  lea     r8, [rbp+pvarDest]; struct VAR *
0x1800777cc  lea     rdx, [rbp+pvarDest]; this
0x1800777d0  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x1800777d5  mov     ebx, eax
0x1800777d7  test    eax, eax
0x1800777d9  js      short loc_1800777F2
0x1800777db  mov     rax, [rbp+pvargSrc]
0x1800777df  mov     rcx, rsi; pvargDest
0x1800777e2  mov     [rax], r14w
0x1800777e6  mov     rdx, [rbp+pvargSrc]; pvargSrc
0x1800777ea  call    cs:__imp_VariantCopy
0x1800777f0  mov     ebx, eax
0x1800777f2  or      edx, 0FFFFFFFFh; Mask
0x1800777f5  mov     ecx, r15d; NewValue
0x1800777f8  call    cs:__imp__controlfp
0x1800777fe  mov     eax, ebx
0x180077800  jmp     short loc_180077807
0x180077802  mov     eax, 80004003h
0x180077807  add     rsp, 58h
0x18007780b  pop     r15
0x18007780d  pop     r14
0x18007780f  pop     rdi
0x180077810  pop     rsi
0x180077811  pop     rbx
0x180077812  pop     rbp
0x180077813  retn
```
