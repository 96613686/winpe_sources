# CSecConLib::RemoveDependency(ushort const *,ushort const *,ushort const *)

- ea: `0x18000fd64`
- end: `0x180010114`
- name: `?RemoveDependency@CSecConLib@@QEAAJPEBG00@Z`
- size: `944`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, wchar_t *String1, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180009a70`

## callees

- `0x180001048`
- `0x180001054`
- `0x180001988`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18000fd64`
- `0x18001011c`
- `0x1800111a2`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000fe79`
- `msvcrt!_wcsnicmp` at `0x18000fe79`
- `msvcrt!wcscpy_s` at `0x18000fee8`
- `msvcrt!wcscpy_s` at `0x18000ff3c`
- `msvcrt!wcscpy_s` at `0x18000ffaf`
- `msvcrt!wcscpy_s` at `0x18001005c`
- `msvcrt!wcscpy_s` at `0x18000fee8`
- `msvcrt!wcscpy_s` at `0x18000ff3c`
- `msvcrt!wcscpy_s` at `0x18000ffaf`
- `msvcrt!wcscpy_s` at `0x18001005c`

## pseudocode

```c
__int64 __fastcall CSecConLib::RemoveDependency(
        CSecConLib *this,
        wchar_t *String1,
        char *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // r15
  const wchar_t *v7; // r12
  __int64 v8; // r13
  int inited; // ebx
  int MultiSZPropVal; // eax
  void *v11; // rbp
  __int64 v12; // r14
  void *v13; // rsi
  wchar_t *v14; // rax
  const wchar_t *v15; // rdi
  wchar_t *v16; // rbx
  size_t v17; // rax
  wchar_t *v18; // rbx
  __int64 v19; // rax
  rsize_t v20; // rsi
  wchar_t *v21; // rax
  wchar_t *v22; // r12
  wchar_t **v23; // r8
  wchar_t *v24; // rsi
  char v25; // r15
  void *v26; // r12
  __int64 v27; // rax
  wchar_t *v28; // rax
  wchar_t **v29; // r8
  int v30; // ecx
  int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  char v37; // [rsp+30h] [rbp-88h]
  char v38; // [rsp+31h] [rbp-87h]
  unsigned int v39[2]; // [rsp+38h] [rbp-80h] BYREF
  void *Src; // [rsp+40h] [rbp-78h] BYREF
  size_t i; // [rsp+48h] [rbp-70h]
  __int64 v42; // [rsp+50h] [rbp-68h]
  wchar_t *v43; // [rsp+58h] [rbp-60h]
  wchar_t *v44; // [rsp+60h] [rbp-58h]
  void *Block; // [rsp+68h] [rbp-50h]

  Src = 0;
  v5 = -1;
  v39[0] = 0;
  v7 = String1;
  do
    ++v5;
  while ( String1[v5] );
  v42 = v5;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&a3[2 * v8] );
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited >= 0 )
  {
    MultiSZPropVal = CSecConLib::GetMultiSZPropVal(this, a4, 0x877u, (unsigned __int16 **)&Src, v39);
    v11 = Src;
    inited = MultiSZPropVal;
    if ( MultiSZPropVal >= 0 )
    {
      v12 = v39[0];
      Src = (void *)v39[0];
      v13 = (void *)v39[0];
      v14 = (wchar_t *)operator new[](saturated_mul(v39[0], 2u));
      *(_QWORD *)v39 = v14;
      v15 = v14;
      if ( v14 )
      {
        Block = v14;
        v38 = 0;
        v37 = 0;
        memcpy_0(v14, v11, 2 * v12);
        v16 = (wchar_t *)v11;
        if ( !*v15 )
          goto LABEL_51;
        v17 = (unsigned int)v5;
        for ( i = (unsigned int)v5; ; v17 = i )
        {
          if ( _wcsnicmp(v7, v15, v17) || v15[i] != 59 )
          {
            if ( !v16 )
              goto LABEL_45;
            wcscpy_s(v16, (rsize_t)v13 - (((char *)v16 - (_BYTE *)v11) >> 1), v15);
            v33 = -1;
            do
              ++v33;
            while ( v16[v33] );
            v16 += (unsigned int)(v33 + 1);
          }
          else
          {
            v44 = v16;
            v18 = &v16[(unsigned int)(v5 + 1)];
            v19 = -1;
            do
              ++v19;
            while ( v18[v19] );
            v20 = v19 + 1;
            v21 = (wchar_t *)operator new[](saturated_mul(v19 + 1, 2u));
            v43 = v21;
            v22 = v21;
            if ( !v21 )
            {
LABEL_45:
              inited = -2147024882;
              goto LABEL_52;
            }
            wcscpy_s(v21, v20, v18);
            v24 = wcstok_mvcrt_legacy_two_parameter_form(v22, L",", v23);
            if ( v24 )
            {
              v25 = v37;
              v26 = Src;
              do
              {
                if ( v25 )
                {
                  wcscpy_s(v18, (rsize_t)v26 - (((char *)v18 - (_BYTE *)v11) >> 1), L",");
                  v27 = -1;
                  do
                    ++v27;
                  while ( v18[v27] );
                  v18 += (unsigned int)v27;
                }
                v28 = v24;
                v29 = (wchar_t **)(a3 - (char *)v24);
                do
                {
                  v30 = *(unsigned __int16 *)((char *)v29 + (_QWORD)v28);
                  v31 = *v28 - v30;
                  if ( v31 )
                    break;
                  ++v28;
                }
                while ( v30 );
                if ( v31 )
                {
                  v25 = 1;
                  wcscpy_s(v18, (rsize_t)v26 - (((char *)v18 - (_BYTE *)v11) >> 1), v24);
                  v32 = -1;
                  do
                    ++v32;
                  while ( v18[v32] );
                  v18 += (unsigned int)v32;
                }
                else
                {
                  v38 = 1;
                  LODWORD(v12) = -1 - v8 + v12;
                  if ( v25 )
                    *--v18 = 0;
                }
                v24 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v29);
              }
              while ( v24 );
              v15 = *(const wchar_t **)v39;
              v22 = v43;
              v37 = v25;
              LODWORD(v5) = v42;
            }
            operator delete(v22);
            if ( v37 )
            {
              v16 = v18 + 1;
              *v16 = 0;
            }
            else
            {
              v16 = v44;
              LODWORD(v12) = -1 - v5 + v12;
            }
            v7 = String1;
            v13 = Src;
          }
          v34 = -1;
          do
            ++v34;
          while ( v15[v34] );
          v15 += (unsigned int)(v34 + 1);
          *(_QWORD *)v39 = v15;
          if ( !*v15 )
            break;
        }
        if ( v38 )
        {
          *v16 = 0;
          if ( (unsigned int)v12 >= 3 )
            v35 = CSecConLib::SetMultiSZPropVal(this, a4, 0x877u, (unsigned __int16 *)v11, v12);
          else
            v35 = CSecConLib::SetMultiSZPropVal(this, a4, 0x877u, 0, 0);
          inited = v35;
        }
        else
        {
LABEL_51:
          inited = -2146646015;
        }
LABEL_52:
        operator delete(Block);
      }
      else
      {
        inited = -2147024882;
      }
    }
    if ( v11 )
      operator delete(v11);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000fd64  mov     rax, rsp
0x18000fd67  mov     [rax+20h], r9
0x18000fd6b  mov     [rax+18h], r8
0x18000fd6f  mov     [rax+10h], rdx
0x18000fd73  mov     [rax+8], rcx
0x18000fd77  push    rbx
0x18000fd78  push    rbp
0x18000fd79  push    rsi
0x18000fd7a  push    rdi
0x18000fd7b  push    r12
0x18000fd7d  push    r13
0x18000fd7f  push    r14
0x18000fd81  push    r15
0x18000fd83  sub     rsp, 78h
0x18000fd87  xor     ebp, ebp
0x18000fd89  mov     rdi, rcx
0x18000fd8c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fd90  mov     [rax-78h], rbp
0x18000fd94  mov     r15, rcx
0x18000fd97  mov     [rax-80h], ebp
0x18000fd9a  mov     rsi, r9
0x18000fd9d  mov     r12, rdx
0x18000fda0  inc     r15
0x18000fda3  cmp     [rdx+r15*2], bp
0x18000fda8  jnz     short loc_18000FDA0
0x18000fdaa  mov     [rsp+0B8h+var_68], r15
0x18000fdaf  mov     r13, rcx
0x18000fdb2  inc     r13
0x18000fdb5  cmp     [r8+r13*2], bp
0x18000fdba  jnz     short loc_18000FDB2
0x18000fdbc  mov     rcx, rdi; this
0x18000fdbf  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000fdc4  mov     ebx, eax
0x18000fdc6  test    eax, eax
0x18000fdc8  js      loc_180010101
0x18000fdce  lea     rax, [rsp+0B8h+var_80]
0x18000fdd3  mov     r8d, 877h; unsigned int
0x18000fdd9  lea     r9, [rsp+0B8h+Src]; unsigned __int16 **
0x18000fdde  mov     [rsp+0B8h+var_98], rax; unsigned int *
0x18000fde3  mov     rdx, rsi; unsigned __int16 *
0x18000fde6  mov     rcx, rdi; this
0x18000fde9  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000fdee  mov     rbp, [rsp+0B8h+Src]
0x18000fdf3  mov     ebx, eax
0x18000fdf5  test    eax, eax
0x18000fdf7  js      loc_1800100F4
0x18000fdfd  mov     r14d, [rsp+0B8h+var_80]
0x18000fe02  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fe09  mov     eax, 2
0x18000fe0e  mov     [rsp+0B8h+Src], r14
0x18000fe13  mul     r14
0x18000fe16  mov     esi, r14d
0x18000fe19  cmovb   rax, rcx
0x18000fe1d  mov     rcx, rax; unsigned __int64
0x18000fe20  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fe25  xor     ebx, ebx
0x18000fe27  mov     qword ptr [rsp+0B8h+var_80], rax
0x18000fe2c  mov     rdi, rax
0x18000fe2f  test    rax, rax
0x18000fe32  jnz     short loc_18000FE3E
0x18000fe34  mov     ebx, 8007000Eh
0x18000fe39  jmp     loc_1800100F4
0x18000fe3e  lea     r8, [r14+r14]; Size
0x18000fe42  mov     [rsp+0B8h+Block], rdi
0x18000fe47  mov     rdx, rbp; Src
0x18000fe4a  mov     [rsp+0B8h+var_87], bl
0x18000fe4e  mov     rcx, rdi; void *
0x18000fe51  mov     [rsp+0B8h+var_88], bl
0x18000fe55  call    memcpy_0
0x18000fe5a  xor     edx, edx
0x18000fe5c  mov     rbx, rbp
0x18000fe5f  cmp     [rdi], dx
0x18000fe62  jz      loc_1800100E5
0x18000fe68  mov     eax, r15d
0x18000fe6b  mov     [rsp+0B8h+var_70], rax
0x18000fe70  mov     r8, rax; MaxCount
0x18000fe73  mov     rdx, rdi; String2
0x18000fe76  mov     rcx, r12; String1
0x18000fe79  call    cs:__imp__wcsnicmp
0x18000fe7f  xor     edx, edx
0x18000fe81  test    eax, eax
0x18000fe83  jnz     loc_180010042
0x18000fe89  mov     rax, [rsp+0B8h+var_70]
0x18000fe8e  cmp     word ptr [rdi+rax*2], 3Bh ; ';'
0x18000fe93  jnz     loc_180010042
0x18000fe99  lea     eax, [r15+1]
0x18000fe9d  mov     [rsp+0B8h+var_58], rbx
0x18000fea2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fea6  lea     rbx, [rbx+rax*2]
0x18000feaa  mov     rax, rcx
0x18000fead  inc     rax
0x18000feb0  cmp     [rbx+rax*2], dx
0x18000feb4  jnz     short loc_18000FEAD
0x18000feb6  lea     rsi, [rax+1]
0x18000feba  mov     eax, 2
0x18000febf  mul     rsi
0x18000fec2  cmovb   rax, rcx
0x18000fec6  mov     rcx, rax; unsigned __int64
0x18000fec9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fece  mov     [rsp+0B8h+var_60], rax
0x18000fed3  mov     r12, rax
0x18000fed6  test    rax, rax
0x18000fed9  jz      loc_18001009E
0x18000fedf  mov     r8, rbx; Source
0x18000fee2  mov     rdx, rsi; SizeInWords
0x18000fee5  mov     rcx, rax; Destination
0x18000fee8  call    cs:__imp_wcscpy_s
0x18000feee  lea     rdx, Delimiter; ","
0x18000fef5  mov     rcx, r12; String
0x18000fef8  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000fefd  xor     r9d, r9d
0x18000ff00  mov     rsi, rax
0x18000ff03  test    rax, rax
0x18000ff06  jz      loc_18000FFFB
0x18000ff0c  mov     r15b, [rsp+0B8h+var_88]
0x18000ff11  mov     r12, [rsp+0B8h+Src]
0x18000ff16  mov     rdi, [rsp+0B8h+arg_10]
0x18000ff1e  test    r15b, r15b
0x18000ff21  jz      short loc_18000FF59
0x18000ff23  mov     rcx, rbx
0x18000ff26  lea     r8, Delimiter; ","
0x18000ff2d  sub     rcx, rbp
0x18000ff30  mov     rdx, r12
0x18000ff33  sar     rcx, 1
0x18000ff36  sub     rdx, rcx; SizeInWords
0x18000ff39  mov     rcx, rbx; Destination
0x18000ff3c  call    cs:__imp_wcscpy_s
0x18000ff42  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ff46  xor     r9d, r9d
0x18000ff49  inc     rax
0x18000ff4c  cmp     [rbx+rax*2], r9w
0x18000ff51  jnz     short loc_18000FF49
0x18000ff53  mov     eax, eax
0x18000ff55  lea     rbx, [rbx+rax*2]
0x18000ff59  mov     r8, rdi
0x18000ff5c  mov     rax, rsi
0x18000ff5f  sub     r8, rsi
0x18000ff62  movzx   edx, word ptr [rax]
0x18000ff65  movzx   ecx, word ptr [rax+r8]
0x18000ff6a  sub     edx, ecx
0x18000ff6c  jnz     short loc_18000FF76
0x18000ff6e  add     rax, 2
0x18000ff72  test    ecx, ecx
0x18000ff74  jnz     short loc_18000FF62
0x18000ff76  test    edx, edx
0x18000ff78  jnz     short loc_18000FF97
0x18000ff7a  or      eax, 0FFFFFFFFh
0x18000ff7d  mov     [rsp+0B8h+var_87], 1
0x18000ff82  sub     eax, r13d
0x18000ff85  add     r14d, eax
0x18000ff88  test    r15b, r15b
0x18000ff8b  jz      short loc_18000FFCA
0x18000ff8d  sub     rbx, 2
0x18000ff91  mov     [rbx], r9w
0x18000ff95  jmp     short loc_18000FFCA
0x18000ff97  mov     rax, rbx
0x18000ff9a  mov     rdx, r12
0x18000ff9d  sub     rax, rbp
0x18000ffa0  mov     r8, rsi; Source
0x18000ffa3  sar     rax, 1
0x18000ffa6  mov     rcx, rbx; Destination
0x18000ffa9  sub     rdx, rax; SizeInWords
0x18000ffac  mov     r15b, 1
0x18000ffaf  call    cs:__imp_wcscpy_s
0x18000ffb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ffb9  xor     ecx, ecx
0x18000ffbb  inc     rax
0x18000ffbe  cmp     [rbx+rax*2], cx
0x18000ffc2  jnz     short loc_18000FFBB
0x18000ffc4  mov     eax, eax
0x18000ffc6  lea     rbx, [rbx+rax*2]
0x18000ffca  lea     rdx, Delimiter; ","
0x18000ffd1  xor     ecx, ecx; String
0x18000ffd3  call    wcstok_mvcrt_legacy_two_parameter_form
0x18000ffd8  xor     r9d, r9d
0x18000ffdb  mov     rsi, rax
0x18000ffde  test    rax, rax
0x18000ffe1  jnz     loc_18000FF1E
0x18000ffe7  mov     rdi, qword ptr [rsp+0B8h+var_80]
0x18000ffec  mov     r12, [rsp+0B8h+var_60]
0x18000fff1  mov     [rsp+0B8h+var_88], r15b
0x18000fff6  mov     r15, [rsp+0B8h+var_68]
0x18000fffb  mov     al, [rsp+0B8h+var_87]
0x18000ffff  mov     rcx, r12; Block
0x180010002  mov     [rsp+0B8h+var_87], al
0x180010006  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001000b  mov     sil, [rsp+0B8h+var_88]
0x180010010  xor     edx, edx
0x180010012  test    sil, sil
0x180010015  jnz     short loc_180010027
0x180010017  mov     rbx, [rsp+0B8h+var_58]
0x18001001c  or      eax, 0FFFFFFFFh
0x18001001f  sub     eax, r15d
0x180010022  add     r14d, eax
0x180010025  jmp     short loc_18001002E
0x180010027  add     rbx, 2
0x18001002b  mov     [rbx], dx
0x18001002e  mov     r12, [rsp+0B8h+arg_8]
0x180010036  mov     [rsp+0B8h+var_88], sil
0x18001003b  mov     rsi, [rsp+0B8h+Src]
0x180010040  jmp     short loc_180010077
0x180010042  test    rbx, rbx
0x180010045  jz      short loc_18001009E
0x180010047  mov     rax, rbx
0x18001004a  mov     rdx, rsi
0x18001004d  sub     rax, rbp
0x180010050  mov     r8, rdi; Source
0x180010053  sar     rax, 1
0x180010056  mov     rcx, rbx; Destination
0x180010059  sub     rdx, rax; SizeInWords
0x18001005c  call    cs:__imp_wcscpy_s
0x180010062  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010066  xor     edx, edx
0x180010068  inc     rax
0x18001006b  cmp     [rbx+rax*2], dx
0x18001006f  jnz     short loc_180010068
0x180010071  inc     eax
0x180010073  lea     rbx, [rbx+rax*2]
0x180010077  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001007b  inc     rax
0x18001007e  cmp     [rdi+rax*2], dx
0x180010082  jnz     short loc_18001007B
0x180010084  inc     eax
0x180010086  lea     rdi, [rdi+rax*2]
0x18001008a  mov     qword ptr [rsp+0B8h+var_80], rdi
0x18001008f  cmp     [rdi], dx
0x180010092  jz      short loc_1800100A5
0x180010094  mov     rax, [rsp+0B8h+var_70]
0x180010099  jmp     loc_18000FE70
0x18001009e  mov     ebx, 8007000Eh
0x1800100a3  jmp     short loc_1800100EA
0x1800100a5  cmp     [rsp+0B8h+var_87], 0
0x1800100aa  jz      short loc_1800100E5
0x1800100ac  mov     rcx, [rsp+0B8h+arg_0]; this
0x1800100b4  mov     r8d, 877h; unsigned int
0x1800100ba  mov     [rbx], dx
0x1800100bd  cmp     r14d, 3
0x1800100c1  jnb     short loc_1800100DB
0x1800100c3  mov     dword ptr [rsp+0B8h+var_98], edx; unsigned int
0x1800100c7  xor     r9d, r9d; unsigned __int16 *
0x1800100ca  mov     rdx, [rsp+0B8h+arg_18]; unsigned __int16 *
0x1800100d2  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x1800100d7  mov     ebx, eax
0x1800100d9  jmp     short loc_1800100EA
0x1800100db  mov     dword ptr [rsp+0B8h+var_98], r14d
0x1800100e0  mov     r9, rbp
0x1800100e3  jmp     short loc_1800100CA
0x1800100e5  mov     ebx, 800CC801h
0x1800100ea  mov     rcx, [rsp+0B8h+Block]; Block
0x1800100ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800100f4  test    rbp, rbp
0x1800100f7  jz      short loc_180010101
0x1800100f9  mov     rcx, rbp; Block
0x1800100fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010101  mov     eax, ebx
0x180010103  add     rsp, 78h
0x180010107  pop     r15
0x180010109  pop     r14
0x18001010b  pop     r13
0x18001010d  pop     r12
0x18001010f  pop     rdi
0x180010110  pop     rsi
0x180010111  pop     rbp
0x180010112  pop     rbx
0x180010113  retn
```
