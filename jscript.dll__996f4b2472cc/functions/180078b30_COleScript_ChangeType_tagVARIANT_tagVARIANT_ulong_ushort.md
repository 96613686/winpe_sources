# COleScript::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)

- ea: `0x180078b30`
- end: `0x180078e0f`
- name: `?ChangeType@COleScript@@UEAAJPEAUtagVARIANT@@0KG@Z`
- size: `735`
- prototype: `int(COleScript *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000599c`
- `0x180007e9c`
- `0x18000826c`
- `0x18000eea4`
- `0x1800174b4`
- `0x180078b30`

## import_xrefs

- `msvcrt!_controlfp` at `0x180078b70`
- `msvcrt!_controlfp` at `0x180078b89`
- `msvcrt!_controlfp` at `0x180078dec`
- `msvcrt!_controlfp` at `0x180078b70`
- `msvcrt!_controlfp` at `0x180078b89`
- `msvcrt!_controlfp` at `0x180078dec`
- `OLEAUT32!__imp_VariantClear` at `0x180078bd7`
- `OLEAUT32!__imp_VariantClear` at `0x180078bed`
- `OLEAUT32!__imp_VariantClear` at `0x180078bd7`
- `OLEAUT32!__imp_VariantClear` at `0x180078bed`
- `OLEAUT32!__imp_VariantCopy` at `0x180078dd8`
- `OLEAUT32!__imp_VariantCopy` at `0x180078dd8`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180078bbe`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180078bbe`

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
  int v11; // ebx
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
      v11 = VAR::Import(&pvarDest, *((struct CSession **)this + 70));
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
              v11 = ConvertToString(v14, (struct IDispatch ***)&pvargSrc, &pvarDest, 1);
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
0x180078b30  push    rbp
0x180078b32  push    rbx
0x180078b33  push    rsi
0x180078b34  push    rdi
0x180078b35  push    r14
0x180078b37  push    r15
0x180078b39  mov     rbp, rsp
0x180078b3c  sub     rsp, 58h
0x180078b40  mov     rdi, rcx
0x180078b43  mov     rbx, r8
0x180078b46  add     rcx, 0FFFFFFFFFFFFFF90h; this
0x180078b4a  mov     rsi, rdx
0x180078b4d  call    ?ValidateBaseThread@COleScript@@AEAAJXZ; COleScript::ValidateBaseThread(void)
0x180078b52  test    eax, eax
0x180078b54  js      loc_180078E01
0x180078b5a  test    rsi, rsi
0x180078b5d  jz      loc_180078DFC
0x180078b63  test    rbx, rbx
0x180078b66  jz      loc_180078DFC
0x180078b6c  xor     edx, edx; Mask
0x180078b6e  xor     ecx, ecx; NewValue
0x180078b70  call    cs:__imp__controlfp
0x180078b77  nop     dword ptr [rax+rax+00h]
0x180078b7c  mov     edx, 30F031Fh; Mask
0x180078b81  mov     ecx, 1Fh; NewValue
0x180078b86  mov     r15d, eax
0x180078b89  call    cs:__imp__controlfp
0x180078b90  nop     dword ptr [rax+rax+00h]
0x180078b95  cmp     qword ptr [rdi+230h], 0
0x180078b9d  mov     [rbp+pvargSrc], 0
0x180078ba5  jnz     short loc_180078BB1
0x180078ba7  mov     ebx, 8000FFFFh
0x180078bac  jmp     loc_180078DE6
0x180078bb1  xor     eax, eax
0x180078bb3  lea     rcx, [rbp+pvarDest]; pvarDest
0x180078bb7  mov     rdx, rbx; pvargSrc
0x180078bba  mov     word ptr [rbp+pvarDest], ax
0x180078bbe  call    cs:__imp_VariantCopyInd
0x180078bc5  nop     dword ptr [rax+rax+00h]
0x180078bca  mov     ebx, eax
0x180078bcc  test    eax, eax
0x180078bce  js      loc_180078DE6
0x180078bd4  mov     rcx, rsi; pvarg
0x180078bd7  call    cs:__imp_VariantClear
0x180078bde  nop     dword ptr [rax+rax+00h]
0x180078be3  mov     ebx, eax
0x180078be5  test    eax, eax
0x180078be7  jns     short loc_180078BFE
0x180078be9  lea     rcx, [rbp+pvarDest]; pvarg
0x180078bed  call    cs:__imp_VariantClear
0x180078bf4  nop     dword ptr [rax+rax+00h]
0x180078bf9  jmp     loc_180078DE6
0x180078bfe  movzx   r14d, [rbp+arg_20]
0x180078c03  cmp     word ptr [rbp+pvarDest], r14w
0x180078c08  jnz     short loc_180078C22
0x180078c0a  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180078c0e  xor     ebx, ebx
0x180078c10  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180078c15  movups  xmmword ptr [rsi], xmm0
0x180078c18  movsd   qword ptr [rsi+10h], xmm1
0x180078c1d  jmp     loc_180078DE6
0x180078c22  mov     rdx, [rdi+230h]; struct CSession *
0x180078c29  lea     rcx, [rbp+pvarDest]; this
0x180078c2d  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x180078c32  mov     ebx, eax
0x180078c34  test    eax, eax
0x180078c36  js      short loc_180078BE9
0x180078c38  mov     r9d, 0Bh
0x180078c3e  lea     rax, [rbp+pvarDest]
0x180078c42  mov     [rbp+pvargSrc], rax
0x180078c46  mov     ecx, r14d
0x180078c49  cmp     r14d, r9d
0x180078c4c  ja      loc_180078D76
0x180078c52  jz      loc_180078D6C
0x180078c58  sub     ecx, 2
0x180078c5b  jz      loc_180078DA1
0x180078c61  sub     ecx, 1
0x180078c64  jz      loc_180078DA1
0x180078c6a  sub     ecx, 1
0x180078c6d  jz      loc_180078D2C
0x180078c73  sub     ecx, 1
0x180078c76  jz      loc_180078D24
0x180078c7c  sub     ecx, 2
0x180078c7f  jz      loc_180078D19
0x180078c85  cmp     ecx, 1
0x180078c88  jnz     loc_180078D9A
0x180078c8e  movzx   eax, word ptr [rbp+pvarDest]
0x180078c92  lea     rdx, [rbp+pvargSrc]; struct VAR **
0x180078c96  mov     ecx, 0FFFDh
0x180078c9b  sub     ax, 3
0x180078c9f  test    cx, ax
0x180078ca2  mov     rcx, [rdi+230h]; struct CSession *
0x180078ca9  jz      short loc_180078CF4
0x180078cab  mov     r9d, 1; int
0x180078cb1  lea     r8, [rbp+pvarDest]; struct VAR *
0x180078cb5  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180078cba  mov     ebx, eax
0x180078cbc  test    eax, eax
0x180078cbe  js      loc_180078DE6
0x180078cc4  mov     rcx, [rbp+pvargSrc]
0x180078cc8  mov     eax, 82h
0x180078ccd  cmp     [rcx], ax
0x180078cd0  jnz     loc_180078DC9
0x180078cd6  mov     eax, 8
0x180078cdb  mov     word ptr [rbp+pvarDest], ax
0x180078cdf  mov     rax, [rcx+8]
0x180078ce3  mov     qword ptr [rbp+pvarDest+8], rax
0x180078ce7  lea     rax, [rbp+pvarDest]
0x180078ceb  mov     [rbp+pvargSrc], rax
0x180078cef  jmp     loc_180078DC9
0x180078cf4  call    ?ConvertNumberToString@@YAJPEAVCSession@@PEAPEAVVAR@@@Z; ConvertNumberToString(CSession *,VAR * *)
0x180078cf9  mov     ebx, eax
0x180078cfb  test    eax, eax
0x180078cfd  js      loc_180078DE6
0x180078d03  mov     rax, [rbp+pvargSrc]
0x180078d07  mov     word ptr [rsi], 8
0x180078d0c  mov     rcx, [rax+8]
0x180078d10  mov     [rsi+8], rcx
0x180078d14  jmp     loc_180078DE6
0x180078d19  mov     r9d, 7
0x180078d1f  jmp     loc_180078DA7
0x180078d24  mov     r9d, 5
0x180078d2a  jmp     short loc_180078DA7
0x180078d2c  mov     rcx, [rdi+230h]; struct CSession *
0x180078d33  lea     r8, [rbp+pvarDest]; struct VAR *
0x180078d37  mov     r9d, 5; int
0x180078d3d  mov     [rsp+58h+var_38], 1; int
0x180078d45  lea     rdx, [rbp+pvarDest]; this
0x180078d49  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x180078d4e  mov     ebx, eax
0x180078d50  test    eax, eax
0x180078d52  js      loc_180078DE6
0x180078d58  mov     rax, [rbp+pvargSrc]
0x180078d5c  movsd   xmm0, qword ptr [rax+8]
0x180078d61  cvtpd2ps xmm0, xmm0
0x180078d65  movss   dword ptr [rax+8], xmm0
0x180078d6a  jmp     short loc_180078DC9
0x180078d6c  mov     [rsp+58h+var_38], 0
0x180078d74  jmp     short loc_180078DAF
0x180078d76  sub     ecx, 10h
0x180078d79  jz      short loc_180078DA1
0x180078d7b  sub     ecx, 1
0x180078d7e  jz      short loc_180078DA1
0x180078d80  mov     r9d, 3
0x180078d86  sub     ecx, 1
0x180078d89  jz      short loc_180078DA7
0x180078d8b  sub     ecx, 1
0x180078d8e  jz      short loc_180078DA7
0x180078d90  sub     ecx, r9d
0x180078d93  jz      short loc_180078DA7
0x180078d95  cmp     ecx, 1
0x180078d98  jz      short loc_180078DA7
0x180078d9a  mov     eax, 80004001h
0x180078d9f  jmp     short loc_180078E01
0x180078da1  mov     r9d, 3; int
0x180078da7  mov     [rsp+58h+var_38], 1; int
0x180078daf  mov     rcx, [rdi+230h]; struct CSession *
0x180078db6  lea     r8, [rbp+pvarDest]; struct VAR *
0x180078dba  lea     rdx, [rbp+pvarDest]; this
0x180078dbe  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x180078dc3  mov     ebx, eax
0x180078dc5  test    eax, eax
0x180078dc7  js      short loc_180078DE6
0x180078dc9  mov     rax, [rbp+pvargSrc]
0x180078dcd  mov     rcx, rsi; pvargDest
0x180078dd0  mov     [rax], r14w
0x180078dd4  mov     rdx, [rbp+pvargSrc]; pvargSrc
0x180078dd8  call    cs:__imp_VariantCopy
0x180078ddf  nop     dword ptr [rax+rax+00h]
0x180078de4  mov     ebx, eax
0x180078de6  or      edx, 0FFFFFFFFh; Mask
0x180078de9  mov     ecx, r15d; NewValue
0x180078dec  call    cs:__imp__controlfp
0x180078df3  nop     dword ptr [rax+rax+00h]
0x180078df8  mov     eax, ebx
0x180078dfa  jmp     short loc_180078E01
0x180078dfc  mov     eax, 80004003h
0x180078e01  add     rsp, 58h
0x180078e05  pop     r15
0x180078e07  pop     r14
0x180078e09  pop     rdi
0x180078e0a  pop     rsi
0x180078e0b  pop     rbx
0x180078e0c  pop     rbp
0x180078e0d  retn
```
