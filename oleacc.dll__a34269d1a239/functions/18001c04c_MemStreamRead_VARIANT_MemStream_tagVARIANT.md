# MemStreamRead_VARIANT(MemStream &,tagVARIANT *)

- ea: `0x18001c04c`
- end: `0x18001c2e2`
- name: `?MemStreamRead_VARIANT@@YAHAEAVMemStream@@PEAUtagVARIANT@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(struct MemStream *this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000f940`

## callees

- `0x180010300`
- `0x180017324`
- `0x18001c04c`
- `0x180047ff8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c22f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c22f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c25f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c25f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c142`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001c142`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18001c166`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18001c166`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001c134`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001c134`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c1b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c1c5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c1b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001c1c5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001c118`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001c118`

## pseudocode

```c
__int64 __fastcall MemStreamRead_VARIANT(struct MemStream *this, struct tagVARIANT *a2)
{
  __int64 v4; // rcx
  __int64 *v5; // rcx
  unsigned __int64 v6; // rbx
  __int64 v7; // rax
  SAFEARRAY *Vector; // rax
  HRESULT v9; // eax
  SAFEARRAY *parray; // rcx
  UINT Elemsize; // eax
  void *v13; // rbp
  __int64 v14; // rbx
  int **v15; // rcx
  int *v16; // rax
  int v17; // ecx
  __int64 *v18; // rcx
  __int64 v19; // r14
  __int64 v20; // rax
  BSTR v21; // rax
  BSTR v22; // rbp
  int v23; // ebx
  LONGLONG **v24; // rcx
  LONG **v25; // rcx
  unsigned __int64 v26; // [rsp+60h] [rbp+18h] BYREF
  void *ppvData; // [rsp+68h] [rbp+20h] BYREF

  if ( !(unsigned int)MemStream::Check(this, 2u, 1) )
    return 0;
  a2->vt = **(_WORD **)v4;
  *(_QWORD *)v4 += 2LL;
  *(_QWORD *)(v4 + 8) -= 2LL;
  if ( a2->vt )
  {
    switch ( a2->vt )
    {
      case 3u:
        if ( !(unsigned int)MemStream::Check((MemStream *)v4, 4u, 1) )
          return 0;
        a2->lVal = **v25;
        *(_QWORD *)this += 4LL;
        *((_QWORD *)this + 1) -= 4LL;
        break;
      case 5u:
        if ( !(unsigned int)MemStream::Check((MemStream *)v4, 8u, 1) )
          return 0;
        a2->llVal = **v24;
        *(_QWORD *)this += 8LL;
        *((_QWORD *)this + 1) -= 8LL;
        break;
      case 8u:
        if ( !(unsigned int)MemStream::Check((MemStream *)v4, 4u, 1) )
          return 0;
        v19 = *(unsigned int *)*v18;
        v20 = *v18 + 4;
        v18[1] -= 4;
        *v18 = v20;
        v21 = SysAllocStringLen(0, v19);
        a2->llVal = (LONGLONG)v21;
        v22 = v21;
        if ( !v21 )
          return 0;
        v23 = 2 * v19;
        if ( !(unsigned int)MemStream::Check(this, 1u, 2 * (int)v19) )
        {
          SysFreeString(a2->bstrVal);
          return 0;
        }
        memcpy_0(v22, *(const void **)this, v23);
        *(_QWORD *)this += v23;
        *((_QWORD *)this + 1) -= v23;
        *(_WORD *)(a2->llVal + 2 * v19) = 0;
        break;
      case 0xBu:
        if ( !(unsigned int)MemStream::Check((MemStream *)v4, 4u, 1) )
          return 0;
        v16 = *v15;
        v17 = **v15;
        *((_QWORD *)this + 1) -= 4LL;
        *(_QWORD *)this = v16 + 1;
        a2->iVal = v17;
        break;
      case 0x1Bu:
      case 0x1Fu:
        if ( !(unsigned int)MemStream::Check((MemStream *)v4, 4u, 1) )
          return 0;
        v6 = *(unsigned int *)*v5;
        v7 = *v5 + 4;
        v5[1] -= 4;
        *v5 = v7;
        if ( (unsigned int)v6 > 0x10000 )
          return 0;
        Vector = SafeArrayCreateVector(a2->vt & 0xFFE4, 0, v6);
        a2->llVal = (LONGLONG)Vector;
        if ( !Vector )
          return 0;
        ppvData = 0;
        v9 = SafeArrayAccessData(Vector, &ppvData);
        parray = a2->parray;
        if ( v9 < 0 )
          goto LABEL_13;
        v26 = 0;
        Elemsize = SafeArrayGetElemsize(parray);
        if ( (int)ULongLongMult(v6, Elemsize, &v26) < 0
          || (v13 = ppvData, !(unsigned int)MemStream::Check(this, 1u, v26)) )
        {
          SafeArrayUnaccessData(a2->parray);
          parray = a2->parray;
LABEL_13:
          SafeArrayDestroy(parray);
          return 0;
        }
        v14 = (int)v26;
        memcpy_0(v13, *(const void **)this, (int)v26);
        *(_QWORD *)this += v14;
        *((_QWORD *)this + 1) -= v14;
        SafeArrayUnaccessData(a2->parray);
        break;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001c04c  mov     [rsp+arg_0], rbx
0x18001c051  mov     [rsp+arg_8], rbp
0x18001c056  push    rsi
0x18001c057  push    rdi
0x18001c058  push    r12
0x18001c05a  push    r14
0x18001c05c  push    r15
0x18001c05e  sub     rsp, 20h
0x18001c062  mov     r12d, 1
0x18001c068  mov     rsi, rdx
0x18001c06b  mov     r8d, r12d; int
0x18001c06e  mov     rdi, rcx
0x18001c071  lea     edx, [r12+1]; unsigned __int64
0x18001c076  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c07b  xor     r15d, r15d
0x18001c07e  test    eax, eax
0x18001c080  jz      loc_18001C148
0x18001c086  mov     rax, [rcx]
0x18001c089  movzx   edx, word ptr [rax]
0x18001c08c  mov     [rsi], dx
0x18001c08f  add     qword ptr [rcx], 2
0x18001c093  add     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFEh
0x18001c098  cmp     [rsi], r15w
0x18001c09c  jz      loc_18001C2DA
0x18001c0a2  cmp     word ptr [rsi], 3
0x18001c0a6  jz      loc_18001C2B4
0x18001c0ac  cmp     word ptr [rsi], 5
0x18001c0b0  lea     ebx, [r12+7]
0x18001c0b5  jz      loc_18001C28D
0x18001c0bb  cmp     [rsi], bx
0x18001c0be  jz      loc_18001C203
0x18001c0c4  cmp     word ptr [rsi], 0Bh
0x18001c0c8  jz      loc_18001C1D4
0x18001c0ce  cmp     word ptr [rsi], 1Bh
0x18001c0d2  jz      short loc_18001C0DE
0x18001c0d4  cmp     word ptr [rsi], 1Fh
0x18001c0d8  jnz     loc_18001C2DA
0x18001c0de  mov     r8d, r12d; int
0x18001c0e1  mov     edx, 4; unsigned __int64
0x18001c0e6  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c0eb  test    eax, eax
0x18001c0ed  jz      short loc_18001C148
0x18001c0ef  mov     rax, [rcx]
0x18001c0f2  mov     ebx, [rax]
0x18001c0f4  add     rax, 4
0x18001c0f8  add     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFCh
0x18001c0fd  mov     [rcx], rax
0x18001c100  cmp     ebx, 10000h
0x18001c106  ja      short loc_18001C148
0x18001c108  movzx   ecx, word ptr [rsi]
0x18001c10b  mov     eax, 0FFE4h
0x18001c110  and     cx, ax; vt
0x18001c113  mov     r8d, ebx; cElements
0x18001c116  xor     edx, edx; lLbound
0x18001c118  call    cs:__imp_SafeArrayCreateVector
0x18001c11e  mov     [rsi+8], rax
0x18001c122  test    rax, rax
0x18001c125  jz      short loc_18001C148
0x18001c127  lea     rdx, [rsp+48h+ppvData]; ppvData
0x18001c12c  mov     [rsp+48h+ppvData], r15
0x18001c131  mov     rcx, rax; psa
0x18001c134  call    cs:__imp_SafeArrayAccessData
0x18001c13a  mov     rcx, [rsi+8]; psa
0x18001c13e  test    eax, eax
0x18001c140  jns     short loc_18001C161
0x18001c142  call    cs:__imp_SafeArrayDestroy
0x18001c148  xor     eax, eax
0x18001c14a  mov     rbx, [rsp+48h+arg_0]
0x18001c14f  mov     rbp, [rsp+48h+arg_8]
0x18001c154  add     rsp, 20h
0x18001c158  pop     r15
0x18001c15a  pop     r14
0x18001c15c  pop     r12
0x18001c15e  pop     rdi
0x18001c15f  pop     rsi
0x18001c160  retn
0x18001c161  mov     [rsp+48h+arg_10], r15
0x18001c166  call    cs:__imp_SafeArrayGetElemsize
0x18001c16c  mov     edx, eax; unsigned __int64
0x18001c16e  mov     rcx, rbx; unsigned __int64
0x18001c171  lea     r8, [rsp+48h+arg_10]; unsigned __int64 *
0x18001c176  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001c17b  test    eax, eax
0x18001c17d  js      short loc_18001C1C1
0x18001c17f  mov     r8d, dword ptr [rsp+48h+arg_10]; int
0x18001c184  mov     rdx, r12; unsigned __int64
0x18001c187  mov     rbp, [rsp+48h+ppvData]
0x18001c18c  mov     rcx, rdi; this
0x18001c18f  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c194  test    eax, eax
0x18001c196  jz      short loc_18001C1C1
0x18001c198  movsxd  rbx, dword ptr [rsp+48h+arg_10]
0x18001c19d  mov     rcx, rbp; void *
0x18001c1a0  mov     rdx, [rdi]; Src
0x18001c1a3  mov     r8, rbx; Size
0x18001c1a6  call    memcpy_0
0x18001c1ab  add     [rdi], rbx
0x18001c1ae  sub     [rdi+8], rbx
0x18001c1b2  mov     rcx, [rsi+8]; psa
0x18001c1b6  call    cs:__imp_SafeArrayUnaccessData
0x18001c1bc  jmp     loc_18001C2DA
0x18001c1c1  mov     rcx, [rsi+8]; psa
0x18001c1c5  call    cs:__imp_SafeArrayUnaccessData
0x18001c1cb  mov     rcx, [rsi+8]
0x18001c1cf  jmp     loc_18001C142
0x18001c1d4  mov     r8d, r12d; int
0x18001c1d7  mov     edx, 4; unsigned __int64
0x18001c1dc  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c1e1  test    eax, eax
0x18001c1e3  jz      loc_18001C148
0x18001c1e9  mov     rax, [rcx]
0x18001c1ec  mov     ecx, [rax]
0x18001c1ee  add     rax, 4
0x18001c1f2  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFCh
0x18001c1f7  mov     [rdi], rax
0x18001c1fa  mov     [rsi+8], cx
0x18001c1fe  jmp     loc_18001C2DA
0x18001c203  mov     r8d, r12d; int
0x18001c206  mov     edx, 4; unsigned __int64
0x18001c20b  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c210  test    eax, eax
0x18001c212  jz      loc_18001C148
0x18001c218  mov     rax, [rcx]
0x18001c21b  mov     r14d, [rax]
0x18001c21e  add     rax, 4
0x18001c222  add     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFCh
0x18001c227  mov     edx, r14d; ui
0x18001c22a  mov     [rcx], rax
0x18001c22d  xor     ecx, ecx; strIn
0x18001c22f  call    cs:__imp_SysAllocStringLen
0x18001c235  mov     [rsi+8], rax
0x18001c239  mov     rbp, rax
0x18001c23c  test    rax, rax
0x18001c23f  jz      loc_18001C148
0x18001c245  lea     ebx, [r14+r14]
0x18001c249  mov     rdx, r12; unsigned __int64
0x18001c24c  mov     r8d, ebx; int
0x18001c24f  mov     rcx, rdi; this
0x18001c252  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c257  test    eax, eax
0x18001c259  jnz     short loc_18001C26A
0x18001c25b  mov     rcx, [rsi+8]; bstrString
0x18001c25f  call    cs:__imp_SysFreeString
0x18001c265  jmp     loc_18001C148
0x18001c26a  mov     rdx, [rdi]; Src
0x18001c26d  mov     rcx, rbp; void *
0x18001c270  movsxd  rbx, ebx
0x18001c273  mov     r8, rbx; Size
0x18001c276  call    memcpy_0
0x18001c27b  add     [rdi], rbx
0x18001c27e  sub     [rdi+8], rbx
0x18001c282  mov     rdx, [rsi+8]
0x18001c286  mov     [rdx+r14*2], r15w
0x18001c28b  jmp     short loc_18001C2DA
0x18001c28d  mov     r8d, r12d; int
0x18001c290  mov     rdx, rbx; unsigned __int64
0x18001c293  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c298  test    eax, eax
0x18001c29a  jz      loc_18001C148
0x18001c2a0  mov     rax, [rcx]
0x18001c2a3  mov     rcx, [rax]
0x18001c2a6  mov     [rsi+8], rcx
0x18001c2aa  add     [rdi], rbx
0x18001c2ad  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFF8h
0x18001c2b2  jmp     short loc_18001C2DA
0x18001c2b4  mov     r8d, r12d; int
0x18001c2b7  mov     edx, 4; unsigned __int64
0x18001c2bc  call    ?Check@MemStream@@AEAAH_KH@Z; MemStream::Check(unsigned __int64,int)
0x18001c2c1  test    eax, eax
0x18001c2c3  jz      loc_18001C148
0x18001c2c9  mov     rcx, [rcx]
0x18001c2cc  mov     edx, [rcx]
0x18001c2ce  mov     [rsi+8], edx
0x18001c2d1  add     qword ptr [rdi], 4
0x18001c2d5  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFCh
0x18001c2da  mov     eax, r12d
0x18001c2dd  jmp     loc_18001C14A
```
