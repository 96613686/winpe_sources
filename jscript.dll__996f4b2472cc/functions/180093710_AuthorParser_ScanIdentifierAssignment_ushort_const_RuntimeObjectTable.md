# AuthorParser::ScanIdentifierAssignment(ushort const *,RuntimeObjectTable *)

- ea: `0x180093710`
- end: `0x180093905`
- name: `?ScanIdentifierAssignment@AuthorParser@@AEAAJPEBGPEAVRuntimeObjectTable@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(AuthorParser *__hidden this, const unsigned __int16 *, struct RuntimeObjectTable *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180093324`
- `0x1800933cc`
- `0x1800939dc`

## callees

- `0x180091e2c`
- `0x1800932d8`
- `0x180093710`
- `0x18009390c`
- `0x180093b14`
- `0x180096686`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800938c9`
- `msvcrt!_wcsnicmp` at `0x1800938c9`

## string_xrefs

- `0x1800938be`: `CreateObject`

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
0x180093710  push    rbx
0x180093712  push    rbp
0x180093713  push    rsi
0x180093714  push    rdi
0x180093715  push    r12
0x180093717  push    r13
0x180093719  push    r14
0x18009371b  push    r15
0x18009371d  sub     rsp, 38h
0x180093721  mov     rax, [rcx+110h]
0x180093728  mov     r12, r8
0x18009372b  mov     rsi, rdx
0x18009372e  mov     rbx, rcx
0x180093731  mov     edi, 1
0x180093736  mov     r15, [rax+10h]
0x18009373a  mov     rbp, [rax+20h]
0x18009373e  mov     r14, [rax+28h]
0x180093742  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093747  cmp     dword ptr [rbx+120h], 52h ; 'R'
0x18009374e  jnz     loc_1800938F1
0x180093754  sub     r14, r15
0x180093757  sub     rbp, r15
0x18009375a  sar     rbp, 1
0x18009375d  mov     rcx, rbx; this
0x180093760  movsxd  rax, ebp
0x180093763  sar     r14, 1
0x180093766  sub     r14d, ebp
0x180093769  lea     r13, [rsi+rax*2]
0x18009376d  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093772  mov     eax, [rbx+120h]
0x180093778  cmp     eax, 2Ch ; ','
0x18009377b  jnz     loc_180093814
0x180093781  mov     rcx, rbx; this
0x180093784  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093789  cmp     dword ptr [rbx+120h], 4Bh ; 'K'
0x180093790  jnz     loc_1800938F1
0x180093796  mov     rax, [rbx+110h]
0x18009379d  mov     rcx, [rax+20h]
0x1800937a1  sub     rcx, [rax+10h]
0x1800937a5  mov     rbp, [rax+28h]
0x1800937a9  sub     rbp, [rax+10h]
0x1800937ad  sar     rcx, 1
0x1800937b0  sar     rbp, 1
0x1800937b3  movsxd  rax, ecx
0x1800937b6  sub     ebp, ecx
0x1800937b8  lea     r15, [rsi+rax*2]
0x1800937bc  cmp     ebp, 0Dh
0x1800937bf  jnz     short loc_1800937DC
0x1800937c1  lea     r8d, [rdi+19h]; Size
0x1800937c5  mov     rdx, r15; Buf2
0x1800937c8  lea     rcx, aActivexobject; "ActiveXObject"
0x1800937cf  call    memcmp_0
0x1800937d4  test    eax, eax
0x1800937d6  jz      loc_1800938D9
0x1800937dc  mov     [rsp+78h+var_50], edi
0x1800937e0  mov     r9, r15
0x1800937e3  mov     r8d, r14d
0x1800937e6  mov     dword ptr [rsp+78h+var_58], ebp
0x1800937ea  mov     rdx, r13
0x1800937ed  mov     rcx, r12
0x1800937f0  call    ?Add@RuntimeObjectTable@@QEAAJPEBGJ0IW4rtotType@@@Z; RuntimeObjectTable::Add(ushort const *,long,ushort const *,uint,rtotType)
0x1800937f5  mov     edi, eax
0x1800937f7  test    eax, eax
0x1800937f9  js      loc_1800938F1
0x1800937ff  mov     rcx, rbx; this
0x180093802  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093807  mov     rcx, rbx; this
0x18009380a  call    ?SkipArgList@AuthorParser@@AEAAXXZ; AuthorParser::SkipArgList(void)
0x18009380f  jmp     loc_1800938F1
0x180093814  cmp     eax, 4Bh ; 'K'
0x180093817  jnz     loc_1800938F1
0x18009381d  mov     rax, [rbx+110h]
0x180093824  mov     rcx, [rax+10h]
0x180093828  mov     rdx, [rax+20h]
0x18009382c  mov     rax, [rax+28h]
0x180093830  sub     rdx, rcx
0x180093833  sub     rax, rcx
0x180093836  sar     rdx, 1
0x180093839  sar     rax, 1
0x18009383c  sub     eax, edx
0x18009383e  cmp     eax, 6
0x180093841  jnz     loc_1800938F1
0x180093847  movsxd  rax, edx
0x18009384a  mov     rcx, 76007200650053h
0x180093854  sub     rcx, [rsi+rax*2]
0x180093858  jnz     short loc_180093866
0x18009385a  mov     eax, [rsi+rax*2+8]
0x18009385e  mov     ecx, 720065h
0x180093863  sub     rcx, rax
0x180093866  test    rcx, rcx
0x180093869  jnz     loc_1800938F1
0x18009386f  mov     rcx, rbx; this
0x180093872  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093877  cmp     dword ptr [rbx+120h], 7Bh ; '{'
0x18009387e  jnz     short loc_1800938F1
0x180093880  mov     rcx, rbx; this
0x180093883  call    ?Scan@AuthorParser@@AEAAXXZ; AuthorParser::Scan(void)
0x180093888  cmp     dword ptr [rbx+120h], 4Bh ; 'K'
0x18009388f  jnz     short loc_1800938F1
0x180093891  mov     rax, [rbx+110h]
0x180093898  mov     r8d, 0Ch; MaxCount
0x18009389e  mov     rdx, [rax+20h]
0x1800938a2  sub     rdx, [rax+10h]
0x1800938a6  mov     rcx, [rax+28h]
0x1800938aa  sub     rcx, [rax+10h]
0x1800938ae  sar     rdx, 1
0x1800938b1  sar     rcx, 1
0x1800938b4  sub     ecx, edx
0x1800938b6  cmp     ecx, r8d
0x1800938b9  jnz     short loc_1800938F1
0x1800938bb  movsxd  rax, edx
0x1800938be  lea     rcx, aCreateobject; "CreateObject"
0x1800938c5  lea     rdx, [rsi+rax*2]; String2
0x1800938c9  call    cs:__imp__wcsnicmp
0x1800938d0  nop     dword ptr [rax+rax+00h]
0x1800938d5  test    eax, eax
0x1800938d7  jnz     short loc_1800938F1
0x1800938d9  mov     r9d, r14d; unsigned int
0x1800938dc  mov     [rsp+78h+var_58], r12; struct RuntimeObjectTable *
0x1800938e1  mov     r8, r13; unsigned __int16 *
0x1800938e4  mov     rdx, rsi; unsigned __int16 *
0x1800938e7  mov     rcx, rbx; this
0x1800938ea  call    ?ScanProgId@AuthorParser@@AEAAJPEBG0KPEAVRuntimeObjectTable@@@Z; AuthorParser::ScanProgId(ushort const *,ushort const *,ulong,RuntimeObjectTable *)
0x1800938ef  mov     edi, eax
0x1800938f1  mov     eax, edi
0x1800938f3  add     rsp, 38h
0x1800938f7  pop     r15
0x1800938f9  pop     r14
0x1800938fb  pop     r13
0x1800938fd  pop     r12
0x1800938ff  pop     rdi
0x180093900  pop     rsi
0x180093901  pop     rbp
0x180093902  pop     rbx
0x180093903  retn
```
