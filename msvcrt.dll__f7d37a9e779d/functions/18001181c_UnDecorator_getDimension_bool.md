# UnDecorator::getDimension(bool)

- ea: `0x18001181c`
- end: `0x180011a7a`
- name: `?getDimension@UnDecorator@@CA?AVDName@@_N@Z`
- size: `606`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f43c`
- `0x180010420`
- `0x1800125f8`
- `0x180013490`
- `0x180013920`
- `0x180013b44`

## callees

- `0x18000e4a8`
- `0x18000e4f0`
- `0x18000e58c`
- `0x18000e638`
- `0x18000ebe8`
- `0x18001181c`

## string_xrefs

- `0x180011840`: ``non-type-template-parameter`

## pseudocode

```c
__int64 __fastcall UnDecorator::getDimension(__int64 a1, char a2)
{
  char *v2; // r8
  const char *v3; // rsi
  int v6; // ecx
  unsigned __int64 v7; // rdx
  DName *v8; // rbx
  DName *v9; // rax
  DName *v10; // r8
  unsigned int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // ecx
  int v18; // edx
  __int64 v19; // rdx
  DName *v20; // rax
  DName *v21; // rbx
  DName *v22; // rax
  __int64 v23; // rdx
  DName *v24; // rax
  unsigned int v25; // ecx
  int v26; // edx
  int v27; // eax
  int v28; // ecx
  int v29; // edx
  _BYTE v31[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v32[16]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v33[16]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v34[24]; // [rsp+50h] [rbp-18h] BYREF

  v2 = UnDecorator::gName;
  v3 = 0;
  if ( *UnDecorator::gName == 81 )
  {
    v2 = UnDecorator::gName + 1;
    v3 = "`non-type-template-parameter";
    ++UnDecorator::gName;
  }
  v6 = *v2;
  if ( *v2 )
  {
    if ( (unsigned __int8)(v6 - 48) <= 9u )
    {
      v7 = v6 - 47;
      UnDecorator::gName = v2 + 1;
      if ( v3 )
      {
        v8 = DName::DName((DName *)v32, v7);
        v9 = DName::DName((DName *)v33, v3);
        DName::operator+(v9, v31, v8);
        v10 = (DName *)v31;
      }
      else
      {
        v10 = DName::DName((DName *)v34, v7);
      }
      v11 = *((_DWORD *)v10 + 2) ^ (*(_DWORD *)(a1 + 8) ^ *((_DWORD *)v10 + 2)) & 0xFFFFFFF0;
      *(_DWORD *)(a1 + 8) = v11;
      v12 = v11 ^ (*((_DWORD *)v10 + 2) ^ v11) & 0x10;
      *(_DWORD *)(a1 + 8) = v12;
      v13 = v12 ^ (*((_DWORD *)v10 + 2) ^ v12) & 0x20;
      *(_DWORD *)(a1 + 8) = v13;
      v14 = v13 ^ (*((_DWORD *)v10 + 2) ^ v13) & 0x40;
      *(_DWORD *)(a1 + 8) = v14;
      v15 = v14 ^ (*((_DWORD *)v10 + 2) ^ v14) & 0x80;
      *(_DWORD *)(a1 + 8) = v15;
      *(_QWORD *)a1 = *(_QWORD *)v10;
      v16 = v15 ^ (*((_DWORD *)v10 + 2) ^ v15) & 0x100;
      goto LABEL_9;
    }
    v19 = 0;
    while ( (_BYTE)v6 != 64 )
    {
      if ( !(_BYTE)v6 )
        goto LABEL_26;
      if ( (unsigned __int8)(v6 - 65) > 0xFu )
      {
        v23 = 1;
        goto LABEL_27;
      }
      v19 = (char)v6 - 65 + 16 * v19;
      UnDecorator::gName = ++v2;
      LOBYTE(v6) = *v2;
    }
    UnDecorator::gName = v2 + 1;
    if ( a2 )
    {
      if ( v3 )
      {
        v20 = DName::DName((DName *)v34, v19);
LABEL_18:
        v21 = v20;
        v22 = DName::DName((DName *)v33, v3);
        DName::operator+(v22, v31, v21);
        v10 = (DName *)v31;
LABEL_22:
        v25 = *((_DWORD *)v10 + 2) ^ (*(_DWORD *)(a1 + 8) ^ *((_DWORD *)v10 + 2)) & 0xFFFFFFF0;
        *(_DWORD *)(a1 + 8) = v25;
        v26 = v25 ^ (*((_DWORD *)v10 + 2) ^ v25) & 0x10;
        *(_DWORD *)(a1 + 8) = v26;
        v27 = v26 ^ (*((_DWORD *)v10 + 2) ^ v26) & 0x20;
        *(_DWORD *)(a1 + 8) = v27;
        v28 = v27 ^ (*((_DWORD *)v10 + 2) ^ v27) & 0x40;
        *(_DWORD *)(a1 + 8) = v28;
        v29 = v28 ^ (*((_DWORD *)v10 + 2) ^ v28) & 0x80;
        *(_DWORD *)(a1 + 8) = v29;
        *(_QWORD *)a1 = *(_QWORD *)v10;
        v16 = v29 ^ (*((_DWORD *)v10 + 2) ^ v29) & 0x100;
LABEL_9:
        *(_DWORD *)(a1 + 8) = v16;
        v17 = v16 ^ (*((_DWORD *)v10 + 2) ^ v16) & 0x200;
        *(_DWORD *)(a1 + 8) = v17;
        v18 = v17 ^ (*((_DWORD *)v10 + 2) ^ v17) & 0x400;
        *(_DWORD *)(a1 + 8) = v18;
        *(_DWORD *)(a1 + 8) = v18 ^ (*((_DWORD *)v10 + 2) ^ v18) & 0x800;
        return a1;
      }
      v24 = DName::DName((DName *)v32, v19);
    }
    else
    {
      if ( v3 )
      {
        v20 = DName::DName((DName *)v34, v19);
        goto LABEL_18;
      }
      v24 = DName::DName((DName *)v32, v19);
    }
    v10 = v24;
    goto LABEL_22;
  }
LABEL_26:
  v23 = 2;
LABEL_27:
  DName::DName(a1, v23);
  return a1;
}

```

## disassembly

```asm
0x18001181c  push    rbp
0x18001181e  push    rbx
0x18001181f  push    rsi
0x180011820  push    rdi
0x180011821  mov     rbp, rsp
0x180011824  sub     rsp, 68h
0x180011828  mov     r8, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x18001182f  xor     esi, esi
0x180011831  mov     r9b, dl
0x180011834  mov     rdi, rcx
0x180011837  cmp     byte ptr [r8], 51h ; 'Q'
0x18001183b  jnz     short loc_18001184E
0x18001183d  inc     r8
0x180011840  lea     rsi, aNonTypeTemplat; "`non-type-template-parameter"
0x180011847  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x18001184e  movsx   ecx, byte ptr [r8]
0x180011852  test    cl, cl
0x180011854  jz      loc_180011A61
0x18001185a  lea     eax, [rcx-30h]
0x18001185d  cmp     al, 9
0x18001185f  ja      loc_18001194C
0x180011865  inc     r8
0x180011868  lea     eax, [rcx-2Fh]
0x18001186b  movsxd  rdx, eax; unsigned __int64
0x18001186e  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x180011875  test    rsi, rsi
0x180011878  jz      short loc_1800118A7
0x18001187a  lea     rcx, [rbp+var_38]; this
0x18001187e  call    ??0DName@@QEAA@_K@Z; DName::DName(unsigned __int64)
0x180011883  mov     rdx, rsi; char *
0x180011886  lea     rcx, [rbp+var_28]; this
0x18001188a  mov     rbx, rax
0x18001188d  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180011892  mov     r8, rbx
0x180011895  lea     rdx, [rbp+var_48]
0x180011899  mov     rcx, rax
0x18001189c  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1800118a1  lea     r8, [rbp+var_48]
0x1800118a5  jmp     short loc_1800118B3
0x1800118a7  lea     rcx, [rbp+var_18]; this
0x1800118ab  call    ??0DName@@QEAA@_K@Z; DName::DName(unsigned __int64)
0x1800118b0  mov     r8, rax
0x1800118b3  mov     ecx, [r8+8]
0x1800118b7  xor     ecx, [rdi+8]
0x1800118ba  and     ecx, 0FFFFFFF0h
0x1800118bd  xor     ecx, [r8+8]
0x1800118c1  mov     [rdi+8], ecx
0x1800118c4  mov     eax, ecx
0x1800118c6  xor     eax, [r8+8]
0x1800118ca  and     eax, 10h
0x1800118cd  xor     eax, ecx
0x1800118cf  mov     [rdi+8], eax
0x1800118d2  mov     ecx, eax
0x1800118d4  xor     ecx, [r8+8]
0x1800118d8  and     ecx, 20h
0x1800118db  xor     ecx, eax
0x1800118dd  mov     [rdi+8], ecx
0x1800118e0  mov     eax, ecx
0x1800118e2  xor     eax, [r8+8]
0x1800118e6  and     eax, 40h
0x1800118e9  xor     eax, ecx
0x1800118eb  mov     [rdi+8], eax
0x1800118ee  mov     ecx, eax
0x1800118f0  xor     ecx, [r8+8]
0x1800118f4  and     ecx, 80h
0x1800118fa  xor     ecx, eax
0x1800118fc  mov     [rdi+8], ecx
0x1800118ff  mov     rax, [r8]
0x180011902  mov     [rdi], rax
0x180011905  mov     eax, ecx
0x180011907  xor     eax, [r8+8]
0x18001190b  and     eax, 100h
0x180011910  xor     eax, ecx
0x180011912  mov     [rdi+8], eax
0x180011915  mov     ecx, eax
0x180011917  xor     ecx, [r8+8]
0x18001191b  and     ecx, 200h
0x180011921  xor     ecx, eax
0x180011923  mov     [rdi+8], ecx
0x180011926  mov     edx, ecx
0x180011928  xor     edx, [r8+8]
0x18001192c  and     edx, 400h
0x180011932  xor     edx, ecx
0x180011934  mov     [rdi+8], edx
0x180011937  mov     eax, edx
0x180011939  xor     eax, [r8+8]
0x18001193d  and     eax, 800h
0x180011942  xor     eax, edx
0x180011944  mov     [rdi+8], eax
0x180011947  jmp     loc_180011A6E
0x18001194c  xor     edx, edx
0x18001194e  jmp     short loc_18001197C
0x180011950  test    cl, cl
0x180011952  jz      loc_180011A61
0x180011958  lea     eax, [rcx-41h]
0x18001195b  cmp     al, 0Fh
0x18001195d  ja      short loc_1800119C6
0x18001195f  movsx   eax, cl
0x180011962  sub     eax, 41h ; 'A'
0x180011965  shl     rdx, 4
0x180011969  movsxd  rcx, eax
0x18001196c  add     rdx, rcx; unsigned __int64
0x18001196f  inc     r8
0x180011972  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x180011979  mov     cl, [r8]
0x18001197c  cmp     cl, 40h ; '@'
0x18001197f  jnz     short loc_180011950
0x180011981  inc     r8
0x180011984  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x18001198b  test    r9b, r9b
0x18001198e  jz      loc_180011A40
0x180011994  test    rsi, rsi
0x180011997  jz      short loc_1800119D0
0x180011999  lea     rcx, [rbp+var_18]; this
0x18001199d  call    ??0DName@@QEAA@_J@Z; DName::DName(__int64)
0x1800119a2  mov     rdx, rsi; char *
0x1800119a5  lea     rcx, [rbp+var_28]; this
0x1800119a9  mov     rbx, rax
0x1800119ac  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x1800119b1  mov     r8, rbx
0x1800119b4  lea     rdx, [rbp+var_48]
0x1800119b8  mov     rcx, rax
0x1800119bb  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1800119c0  lea     r8, [rbp+var_48]
0x1800119c4  jmp     short loc_1800119DC
0x1800119c6  mov     edx, 1
0x1800119cb  jmp     loc_180011A66
0x1800119d0  lea     rcx, [rbp+var_38]; this
0x1800119d4  call    ??0DName@@QEAA@_J@Z; DName::DName(__int64)
0x1800119d9  mov     r8, rax
0x1800119dc  mov     ecx, [r8+8]
0x1800119e0  xor     ecx, [rdi+8]
0x1800119e3  and     ecx, 0FFFFFFF0h
0x1800119e6  xor     ecx, [r8+8]
0x1800119ea  mov     [rdi+8], ecx
0x1800119ed  mov     edx, ecx
0x1800119ef  xor     edx, [r8+8]
0x1800119f3  and     edx, 10h
0x1800119f6  xor     edx, ecx
0x1800119f8  mov     [rdi+8], edx
0x1800119fb  mov     eax, edx
0x1800119fd  xor     eax, [r8+8]
0x180011a01  and     eax, 20h
0x180011a04  xor     eax, edx
0x180011a06  mov     [rdi+8], eax
0x180011a09  mov     ecx, eax
0x180011a0b  xor     ecx, [r8+8]
0x180011a0f  and     ecx, 40h
0x180011a12  xor     ecx, eax
0x180011a14  mov     [rdi+8], ecx
0x180011a17  mov     edx, ecx
0x180011a19  xor     edx, [r8+8]
0x180011a1d  and     edx, 80h
0x180011a23  xor     edx, ecx
0x180011a25  mov     [rdi+8], edx
0x180011a28  mov     rax, [r8]
0x180011a2b  mov     [rdi], rax
0x180011a2e  mov     eax, edx
0x180011a30  xor     eax, [r8+8]
0x180011a34  and     eax, 100h
0x180011a39  xor     eax, edx
0x180011a3b  jmp     loc_180011912
0x180011a40  test    rsi, rsi
0x180011a43  jz      short loc_180011A53
0x180011a45  lea     rcx, [rbp+var_18]; this
0x180011a49  call    ??0DName@@QEAA@_K@Z; DName::DName(unsigned __int64)
0x180011a4e  jmp     loc_1800119A2
0x180011a53  lea     rcx, [rbp+var_38]; this
0x180011a57  call    ??0DName@@QEAA@_K@Z; DName::DName(unsigned __int64)
0x180011a5c  jmp     loc_1800119D9
0x180011a61  mov     edx, 2
0x180011a66  mov     rcx, rdi
0x180011a69  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x180011a6e  mov     rax, rdi
0x180011a71  add     rsp, 68h
0x180011a75  pop     rdi
0x180011a76  pop     rsi
0x180011a77  pop     rbx
0x180011a78  pop     rbp
0x180011a79  retn
```
