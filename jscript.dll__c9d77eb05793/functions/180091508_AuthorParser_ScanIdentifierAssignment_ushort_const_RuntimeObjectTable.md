# AuthorParser::ScanIdentifierAssignment(ushort const *,RuntimeObjectTable *)

- ea: `0x180091508`
- end: `0x1800916f2`
- name: `?ScanIdentifierAssignment@AuthorParser@@AEAAJPEBGPEAVRuntimeObjectTable@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(AuthorParser *__hidden this, const unsigned __int16 *, struct RuntimeObjectTable *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18009111c`
- `0x1800911c4`
- `0x1800917c8`

## callees

- `0x18008fc48`
- `0x1800910d0`
- `0x180091508`
- `0x1800916f8`
- `0x1800918fc`
- `0x180094276`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800916bd`
- `msvcrt!_wcsnicmp` at `0x1800916bd`

## string_xrefs

- `0x1800916b2`: `CreateObject`

## pseudocode

```c
__int64 __fastcall AuthorParser::ScanIdentifierAssignment(
        AuthorParser *this,
        const unsigned __int16 *a2,
        struct RuntimeObjectTable *a3)
{
  _QWORD *v3; // rax
  unsigned int v7; // edi
  __int64 v8; // r15
  __int64 v9; // rbp
  __int64 v10; // r14
  __int64 v11; // rbp
  unsigned int v12; // r14d
  const unsigned __int16 *v13; // r13
  int v14; // eax
  _QWORD *v15; // rax
  __int64 v16; // rcx
  int v17; // ebp
  const unsigned __int16 *v18; // r15
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rdx

  v3 = (_QWORD *)*((_QWORD *)this + 34);
  v7 = 1;
  v8 = v3[2];
  v9 = v3[4];
  v10 = v3[5];
  AuthorParser::Scan(this);
  if ( *((_DWORD *)this + 72) != 82 )
    return v7;
  v11 = (v9 - v8) >> 1;
  v12 = ((v10 - v8) >> 1) - v11;
  v13 = &a2[(int)v11];
  AuthorParser::Scan(this);
  v14 = *((_DWORD *)this + 72);
  if ( v14 == 44 )
  {
    AuthorParser::Scan(this);
    if ( *((_DWORD *)this + 72) != 75 )
      return v7;
    v15 = (_QWORD *)*((_QWORD *)this + 34);
    v16 = (__int64)(v15[4] - v15[2]) >> 1;
    v17 = ((__int64)(v15[5] - v15[2]) >> 1) - v16;
    v18 = &a2[(int)v16];
    if ( v17 != 13 || memcmp_0(L"ActiveXObject", &a2[(int)v16], 0x1Au) )
    {
      v7 = RuntimeObjectTable::Add(a3, v13, v12, v18, v17, 1);
      if ( (v7 & 0x80000000) == 0 )
      {
        AuthorParser::Scan(this);
        AuthorParser::SkipArgList(this);
      }
      return v7;
    }
    return (unsigned int)AuthorParser::ScanProgId(this, a2, v13, v12, a3);
  }
  if ( v14 == 75 )
  {
    v19 = (_QWORD *)*((_QWORD *)this + 34);
    v20 = v19[2];
    v21 = (v19[4] - v20) >> 1;
    if ( (unsigned int)((v19[5] - v20) >> 1) - (_DWORD)v21 == 6 )
    {
      v22 = 0x76007200650053LL - *(_QWORD *)&a2[(int)v21];
      if ( *(_QWORD *)&a2[(int)v21] == 0x76007200650053LL )
        v22 = 7471205LL - *(unsigned int *)&a2[(int)v21 + 4];
      if ( !v22 )
      {
        AuthorParser::Scan(this);
        if ( *((_DWORD *)this + 72) == 123 )
        {
          AuthorParser::Scan(this);
          if ( *((_DWORD *)this + 72) == 75 )
          {
            v23 = (_QWORD *)*((_QWORD *)this + 34);
            v24 = (__int64)(v23[4] - v23[2]) >> 1;
            if ( (unsigned int)((__int64)(v23[5] - v23[2]) >> 1) - (_DWORD)v24 == 12
              && !_wcsnicmp(L"CreateObject", &a2[(int)v24], 0xCu) )
            {
              return (unsigned int)AuthorParser::ScanProgId(this, a2, v13, v12, a3);
            }
          }
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180091508  push    rbx
0x18009150a  push    rbp
0x18009150b  push    rsi
0x18009150c  push    rdi
0x18009150d  push    r12
0x18009150f  push    r13
0x180091511  push    r14
0x180091513  push    r15
0x180091515  sub     rsp, 38h
0x180091519  mov     rax, [rcx+110h]
0x180091520  mov     r12, r8
0x180091523  mov     rsi, rdx
0x180091526  mov     rbx, rcx
0x180091529  mov     edi, 1
0x18009152e  mov     r15, [rax+10h]
0x180091532  mov     rbp, [rax+20h]
0x180091536  mov     r14, [rax+28h]
0x18009153a  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18009153f  cmp     dword ptr [rbx+120h], 52h ; 'R'
0x180091546  jnz     loc_1800916DF
0x18009154c  sub     r14, r15
0x18009154f  sub     rbp, r15
0x180091552  sar     rbp, 1
0x180091555  mov     rcx, rbx; this
0x180091558  movsxd  rax, ebp
0x18009155b  sar     r14, 1
0x18009155e  sub     r14d, ebp
0x180091561  lea     r13, [rsi+rax*2]
0x180091565  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18009156a  mov     eax, [rbx+120h]
0x180091570  cmp     eax, 2Ch ; ','
0x180091573  jnz     loc_18009160C
0x180091579  mov     rcx, rbx; this
0x18009157c  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180091581  cmp     dword ptr [rbx+120h], 4Bh ; 'K'
0x180091588  jnz     loc_1800916DF
0x18009158e  mov     rax, [rbx+110h]
0x180091595  mov     rcx, [rax+20h]
0x180091599  sub     rcx, [rax+10h]
0x18009159d  mov     rbp, [rax+28h]
0x1800915a1  sub     rbp, [rax+10h]
0x1800915a5  sar     rcx, 1
0x1800915a8  sar     rbp, 1
0x1800915ab  movsxd  rax, ecx
0x1800915ae  sub     ebp, ecx
0x1800915b0  lea     r15, [rsi+rax*2]
0x1800915b4  cmp     ebp, 0Dh
0x1800915b7  jnz     short loc_1800915D4
0x1800915b9  lea     r8d, [rdi+19h]; Size
0x1800915bd  mov     rdx, r15; Buf2
0x1800915c0  lea     rcx, aActivexobject; "ActiveXObject"
0x1800915c7  call    memcmp_0
0x1800915cc  test    eax, eax
0x1800915ce  jz      loc_1800916C7
0x1800915d4  mov     [rsp+78h+var_50], edi
0x1800915d8  mov     r9, r15
0x1800915db  mov     r8d, r14d
0x1800915de  mov     dword ptr [rsp+78h+var_58], ebp
0x1800915e2  mov     rdx, r13
0x1800915e5  mov     rcx, r12
0x1800915e8  call    ?Add@RuntimeObjectTable@@QEAAJPEBGJ0IW4rtotType@@@Z; RuntimeObjectTable::Add(ushort const *,long,ushort const *,uint,rtotType)
0x1800915ed  mov     edi, eax
0x1800915ef  test    eax, eax
0x1800915f1  js      loc_1800916DF
0x1800915f7  mov     rcx, rbx; this
0x1800915fa  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x1800915ff  mov     rcx, rbx; this
0x180091602  call    ?SkipArgList@AuthorParser@@AEAAXXZ; AuthorParser::SkipArgList(void)
0x180091607  jmp     loc_1800916DF
0x18009160c  cmp     eax, 4Bh ; 'K'
0x18009160f  jnz     loc_1800916DF
0x180091615  mov     rax, [rbx+110h]
0x18009161c  mov     rcx, [rax+10h]
0x180091620  mov     rdx, [rax+20h]
0x180091624  mov     rax, [rax+28h]
0x180091628  sub     rdx, rcx
0x18009162b  sub     rax, rcx
0x18009162e  sar     rdx, 1
0x180091631  sar     rax, 1
0x180091634  sub     eax, edx
0x180091636  cmp     eax, 6
0x180091639  jnz     loc_1800916DF
0x18009163f  movsxd  rax, edx
0x180091642  mov     rcx, 76007200650053h
0x18009164c  sub     rcx, [rsi+rax*2]
0x180091650  jnz     short loc_18009165E
0x180091652  mov     eax, [rsi+rax*2+8]
0x180091656  mov     ecx, 720065h
0x18009165b  sub     rcx, rax
0x18009165e  test    rcx, rcx
0x180091661  jnz     short loc_1800916DF
0x180091663  mov     rcx, rbx; this
0x180091666  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18009166b  cmp     dword ptr [rbx+120h], 7Bh ; '{'
0x180091672  jnz     short loc_1800916DF
0x180091674  mov     rcx, rbx; this
0x180091677  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x18009167c  cmp     dword ptr [rbx+120h], 4Bh ; 'K'
0x180091683  jnz     short loc_1800916DF
0x180091685  mov     rax, [rbx+110h]
0x18009168c  mov     r8d, 0Ch; MaxCount
0x180091692  mov     rdx, [rax+20h]
0x180091696  sub     rdx, [rax+10h]
0x18009169a  mov     rcx, [rax+28h]
0x18009169e  sub     rcx, [rax+10h]
0x1800916a2  sar     rdx, 1
0x1800916a5  sar     rcx, 1
0x1800916a8  sub     ecx, edx
0x1800916aa  cmp     ecx, r8d
0x1800916ad  jnz     short loc_1800916DF
0x1800916af  movsxd  rax, edx
0x1800916b2  lea     rcx, aCreateobject; "CreateObject"
0x1800916b9  lea     rdx, [rsi+rax*2]; String2
0x1800916bd  call    cs:__imp__wcsnicmp
0x1800916c3  test    eax, eax
0x1800916c5  jnz     short loc_1800916DF
0x1800916c7  mov     r9d, r14d; unsigned int
0x1800916ca  mov     [rsp+78h+var_58], r12; struct RuntimeObjectTable *
0x1800916cf  mov     r8, r13; unsigned __int16 *
0x1800916d2  mov     rdx, rsi; unsigned __int16 *
0x1800916d5  mov     rcx, rbx; this
0x1800916d8  call    ?ScanProgId@AuthorParser@@AEAAJPEBG0KPEAVRuntimeObjectTable@@@Z; AuthorParser::ScanProgId(ushort const *,ushort const *,ulong,RuntimeObjectTable *)
0x1800916dd  mov     edi, eax
0x1800916df  mov     eax, edi
0x1800916e1  add     rsp, 38h
0x1800916e5  pop     r15
0x1800916e7  pop     r14
0x1800916e9  pop     r13
0x1800916eb  pop     r12
0x1800916ed  pop     rdi
0x1800916ee  pop     rsi
0x1800916ef  pop     rbp
0x1800916f0  pop     rbx
0x1800916f1  retn
```
