# JsonReader::ParseSimpleValue(JSON_PARSER_TOKEN)

- ea: `0x14002410c`
- end: `0x1400244cd`
- name: `?ParseSimpleValue@JsonReader@@AEAAPEAVJsonPrimitive@@W4JSON_PARSER_TOKEN@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400239a4`
- `0x140023b80`
- `0x140023e64`

## callees

- `0x140001814`
- `0x140001b60`
- `0x1400032ec`
- `0x14001c644`
- `0x14001c78c`
- `0x14002401c`
- `0x14002410c`
- `0x1400244d4`
- `0x14002c3e8`

## string_xrefs

- `0x14002416f`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x140024202`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x1400242c6`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x140024385`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`
- `0x140024413`: `onecore\ds\security\dsreg\win32\adal.native\jsonreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_DWORD *__fastcall JsonReader::ParseSimpleValue(__int64 a1, int a2)
{
  char v3; // si
  int v4; // edx
  int v5; // edx
  int v6; // edx
  __int64 v7; // rdx
  _DWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rdx
  __int16 v16; // r9
  _DWORD *v17; // rax
  _DWORD *v18; // rcx
  int v19; // ecx
  __int64 v20; // r10
  __int64 v21; // r11
  __int64 v22; // rdx
  __int16 v23; // r9
  int v24; // ecx
  __int64 v25; // r10
  __int64 v26; // r11
  __int64 v27; // rdx
  __int16 v28; // r9
  _QWORD pExceptionObject[2]; // [rsp+20h] [rbp-40h] BYREF
  int v30; // [rsp+30h] [rbp-30h]
  char *v31[4]; // [rsp+38h] [rbp-28h] BYREF

  v3 = 0;
  v30 = 0;
  v4 = a2 - 1;
  if ( !v4 )
  {
    v24 = 3;
    LODWORD(v25) = 0;
    v26 = *(_QWORD *)(a1 + 40);
    v27 = *(unsigned int *)(a1 + 48);
    v28 = *(_WORD *)(v26 + 2 * v27);
    if ( v28 != aUll[0] )
      goto LABEL_46;
    while ( 1 )
    {
      --v24;
      if ( !v28 )
        break;
      v27 = (unsigned int)(v27 + 1);
      *(_DWORD *)(a1 + 48) = v27;
      if ( !v24 )
        goto LABEL_41;
      v25 = (unsigned int)(v25 + 1);
      v28 = *(_WORD *)(v26 + 2 * v27);
      if ( v28 != aUll[v25] )
        goto LABEL_46;
    }
    if ( v24 )
    {
LABEL_46:
      JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
      throw (JsonException *)pExceptionObject;
    }
LABEL_41:
    v17 = operator new(0x40u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    v18 = v17;
    pExceptionObject[0] = v17;
    if ( v17 )
    {
      v17[2] = 6;
      *(_QWORD *)v17 = &JsonPrimitive::`vftable';
      *((_BYTE *)v17 + 16) = 0;
      goto LABEL_24;
    }
    return 0;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v19 = 4;
    LODWORD(v20) = 0;
    v21 = *(_QWORD *)(a1 + 40);
    v22 = *(unsigned int *)(a1 + 48);
    v23 = *(_WORD *)(v21 + 2 * v22);
    if ( v23 != aAlse[0] )
      goto LABEL_45;
    while ( 1 )
    {
      --v19;
      if ( !v23 )
        break;
      v22 = (unsigned int)(v22 + 1);
      *(_DWORD *)(a1 + 48) = v22;
      if ( !v19 )
        goto LABEL_33;
      v20 = (unsigned int)(v20 + 1);
      v23 = *(_WORD *)(v21 + 2 * v22);
      if ( v23 != aAlse[v20] )
        goto LABEL_45;
    }
    if ( v19 )
    {
LABEL_45:
      JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
      throw (JsonException *)pExceptionObject;
    }
LABEL_33:
    v17 = operator new(0x40u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    v18 = v17;
    pExceptionObject[0] = v17;
    if ( v17 )
    {
      *((_BYTE *)v17 + 16) = 0;
      goto LABEL_23;
    }
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v12 = 3;
    LODWORD(v13) = 0;
    v14 = *(_QWORD *)(a1 + 40);
    v15 = *(unsigned int *)(a1 + 48);
    v16 = *(_WORD *)(v14 + 2 * v15);
    if ( v16 != aRue[0] )
      goto LABEL_44;
    while ( 1 )
    {
      --v12;
      if ( !v16 )
        break;
      v15 = (unsigned int)(v15 + 1);
      *(_DWORD *)(a1 + 48) = v15;
      if ( !v12 )
        goto LABEL_21;
      v13 = (unsigned int)(v13 + 1);
      v16 = *(_WORD *)(v14 + 2 * v15);
      if ( v16 != aRue[v13] )
        goto LABEL_44;
    }
    if ( v12 )
    {
LABEL_44:
      JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
      throw (JsonException *)pExceptionObject;
    }
LABEL_21:
    v17 = operator new(0x40u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    v18 = v17;
    pExceptionObject[0] = v17;
    if ( v17 )
    {
      *((_BYTE *)v17 + 16) = 1;
LABEL_23:
      *(_QWORD *)v17 = &JsonPrimitive::`vftable';
      v17[2] = 5;
LABEL_24:
      *((_QWORD *)v17 + 3) = 0;
      *((_OWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 6) = 0;
      *((_QWORD *)v17 + 7) = 7;
      *((_WORD *)v17 + 16) = 0;
      return v18;
    }
    return 0;
  }
  v7 = (unsigned int)(v6 - 1);
  if ( (_DWORD)v7 )
  {
    if ( (_DWORD)v7 != 1 )
    {
      JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
      throw (JsonException *)pExceptionObject;
    }
    v8 = operator new(0x40u, v7, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    pExceptionObject[0] = v8;
    if ( v8 )
    {
      v9 = JsonReader::ParseString(a1, v31);
      v3 = 1;
      v30 = 1;
      v8[2] = 3;
      *(_QWORD *)v8 = &JsonPrimitive::`vftable';
      *((_BYTE *)v8 + 16) = 0;
      *((_QWORD *)v8 + 3) = 0;
      std::wstring::wstring(v8 + 8, v9);
    }
    else
    {
      v8 = 0;
    }
    if ( (v3 & 1) != 0 )
      std::wstring::~wstring(v31);
  }
  else
  {
    v8 = operator new(0x40u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jsonreader.cpp");
    pExceptionObject[0] = v8;
    if ( v8 )
    {
      v11 = JsonReader::ParseNumber((JsonReader *)a1);
      v8[2] = 4;
      *(_QWORD *)v8 = &JsonPrimitive::`vftable';
      *((_BYTE *)v8 + 16) = 0;
      *((_QWORD *)v8 + 3) = v11;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 7) = 7;
      *((_WORD *)v8 + 16) = 0;
    }
    else
    {
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14002410c  mov     [rsp-18h+arg_8], rbx
0x140024111  mov     [rsp-18h+arg_10], rsi
0x140024116  push    rbp
0x140024117  push    rdi
0x140024118  push    r14
0x14002411a  mov     rbp, rsp
0x14002411d  sub     rsp, 60h
0x140024121  mov     rax, cs:__security_cookie
0x140024128  xor     rax, rsp
0x14002412b  mov     [rbp+var_8], rax
0x14002412f  mov     rdi, rcx
0x140024132  xor     r14d, r14d
0x140024135  mov     esi, r14d
0x140024138  mov     [rbp+var_30], r14d
0x14002413c  sub     edx, 1
0x14002413f  jz      loc_1400243B2
0x140024145  sub     edx, 1
0x140024148  jz      loc_140024324
0x14002414e  sub     edx, 1
0x140024151  jz      loc_140024265
0x140024157  sub     edx, 1; int
0x14002415a  jz      loc_1400241FC
0x140024160  cmp     edx, 1
0x140024163  jnz     loc_140024451
0x140024169  mov     r9d, 108h; int
0x14002416f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140024176  lea     ecx, [rdx+3Fh]; unsigned __int64
0x140024179  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002417e  mov     rbx, rax
0x140024181  mov     [rbp+pExceptionObject], rax
0x140024185  test    rax, rax
0x140024188  jz      short loc_1400241C6
0x14002418a  lea     rdx, [rbp+var_28]
0x14002418e  mov     rcx, rdi
0x140024191  call    ?ParseString@JsonReader@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; JsonReader::ParseString(void)
0x140024196  nop
0x140024197  lea     esi, [r14+1]
0x14002419b  mov     [rbp+var_30], esi
0x14002419e  mov     dword ptr [rbx+8], 3
0x1400241a5  lea     rdx, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x1400241ac  mov     [rbx], rdx
0x1400241af  mov     [rbx+10h], r14b
0x1400241b3  mov     [rbx+18h], r14
0x1400241b7  lea     rcx, [rbx+20h]
0x1400241bb  mov     rdx, rax
0x1400241be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400241c3  nop
0x1400241c4  jmp     short loc_1400241C9
0x1400241c6  mov     rbx, r14
0x1400241c9  test    sil, 1
0x1400241cd  jz      short loc_1400241D8
0x1400241cf  lea     rcx, [rbp+var_28]
0x1400241d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400241d8  mov     rax, rbx
0x1400241db  mov     rcx, [rbp+var_8]
0x1400241df  xor     rcx, rsp; StackCookie
0x1400241e2  call    __security_check_cookie
0x1400241e7  lea     r11, [rsp+60h+var_s0]
0x1400241ec  mov     rbx, [r11+28h]
0x1400241f0  mov     rsi, [r11+30h]
0x1400241f4  mov     rsp, r11
0x1400241f7  pop     r14
0x1400241f9  pop     rdi
0x1400241fa  pop     rbp
0x1400241fb  retn
0x1400241fc  mov     r9d, 10Dh; int
0x140024202  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140024209  mov     edx, 1; int
0x14002420e  lea     ecx, [rdx+3Fh]; unsigned __int64
0x140024211  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140024216  mov     rbx, rax
0x140024219  mov     [rbp+pExceptionObject], rax
0x14002421d  test    rax, rax
0x140024220  jz      short loc_14002425D
0x140024222  mov     rcx, rdi; this
0x140024225  call    ?ParseNumber@JsonReader@@AEAA_JXZ; JsonReader::ParseNumber(void)
0x14002422a  mov     dword ptr [rbx+8], 4
0x140024231  lea     rdx, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x140024238  mov     [rbx], rdx
0x14002423b  mov     [rbx+10h], r14b
0x14002423f  mov     [rbx+18h], rax
0x140024243  xorps   xmm0, xmm0
0x140024246  movups  xmmword ptr [rbx+20h], xmm0
0x14002424a  mov     [rbx+30h], r14
0x14002424e  mov     qword ptr [rbx+38h], 7
0x140024256  mov     [rbx+20h], r14w
0x14002425b  jmp     short loc_140024260
0x14002425d  mov     rbx, r14
0x140024260  jmp     loc_1400241D8
0x140024265  mov     ecx, 3
0x14002426a  mov     r10d, r14d
0x14002426d  mov     r11, [rdi+28h]
0x140024271  mov     edx, [rdi+30h]
0x140024274  movzx   r9d, word ptr [r11+rdx*2]
0x140024279  cmp     r9w, word ptr cs:aRue; "rue"
0x140024281  jnz     loc_140024470
0x140024287  lea     r8, cs:140000000h
0x14002428e  dec     ecx
0x140024290  test    r9w, r9w
0x140024294  jz      short loc_1400242B8
0x140024296  inc     edx
0x140024298  mov     [rdi+30h], edx
0x14002429b  test    ecx, ecx
0x14002429d  jz      short loc_1400242C0
0x14002429f  inc     r10d
0x1400242a2  movzx   r9d, word ptr [r11+rdx*2]
0x1400242a7  cmp     r9w, word ptr ds:rva aRue[r8+r10*2]; "rue" ...
0x1400242b0  jnz     loc_140024470
0x1400242b6  jmp     short loc_14002428E
0x1400242b8  test    ecx, ecx
0x1400242ba  jnz     loc_140024470
0x1400242c0  mov     r9d, 113h; int
0x1400242c6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x1400242cd  mov     edx, 1; int
0x1400242d2  lea     ecx, [rdx+3Fh]; unsigned __int64
0x1400242d5  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x1400242da  mov     rcx, rax
0x1400242dd  mov     [rbp+pExceptionObject], rax
0x1400242e1  test    rax, rax
0x1400242e4  jz      short loc_140024319
0x1400242e6  mov     byte ptr [rax+10h], 1
0x1400242ea  lea     rdx, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x1400242f1  mov     [rax], rdx
0x1400242f4  mov     dword ptr [rax+8], 5
0x1400242fb  mov     [rax+18h], r14
0x1400242ff  xorps   xmm0, xmm0
0x140024302  movups  xmmword ptr [rax+20h], xmm0
0x140024306  mov     [rax+30h], r14
0x14002430a  mov     qword ptr [rax+38h], 7
0x140024312  mov     [rax+20h], r14w
0x140024317  jmp     short loc_14002431C
0x140024319  mov     rcx, r14
0x14002431c  mov     rax, rcx
0x14002431f  jmp     loc_1400241DB
0x140024324  mov     ecx, 4
0x140024329  mov     r10d, r14d
0x14002432c  mov     r11, [rdi+28h]
0x140024330  mov     edx, [rdi+30h]
0x140024333  movzx   r9d, word ptr [r11+rdx*2]
0x140024338  cmp     r9w, word ptr cs:aAlse; "alse"
0x140024340  jnz     loc_14002448F
0x140024346  lea     r8, cs:140000000h
0x14002434d  dec     ecx
0x14002434f  test    r9w, r9w
0x140024353  jz      short loc_140024377
0x140024355  inc     edx
0x140024357  mov     [rdi+30h], edx
0x14002435a  test    ecx, ecx
0x14002435c  jz      short loc_14002437F
0x14002435e  inc     r10d
0x140024361  movzx   r9d, word ptr [r11+rdx*2]
0x140024366  cmp     r9w, word ptr ds:rva aAlse[r8+r10*2]; "alse" ...
0x14002436f  jnz     loc_14002448F
0x140024375  jmp     short loc_14002434D
0x140024377  test    ecx, ecx
0x140024379  jnz     loc_14002448F
0x14002437f  mov     r9d, 11Bh; int
0x140024385  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002438c  mov     edx, 1; int
0x140024391  lea     ecx, [rdx+3Fh]; unsigned __int64
0x140024394  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140024399  mov     rcx, rax
0x14002439c  mov     [rbp+pExceptionObject], rax
0x1400243a0  test    rax, rax
0x1400243a3  jz      loc_140024319
0x1400243a9  mov     [rax+10h], r14b
0x1400243ad  jmp     loc_1400242EA
0x1400243b2  mov     ecx, 3
0x1400243b7  mov     r10d, r14d
0x1400243ba  mov     r11, [rdi+28h]
0x1400243be  mov     edx, [rdi+30h]
0x1400243c1  movzx   r9d, word ptr [r11+rdx*2]
0x1400243c6  cmp     r9w, word ptr cs:aUll; "ull"
0x1400243ce  jnz     loc_1400244AE
0x1400243d4  lea     r8, cs:140000000h
0x1400243db  dec     ecx
0x1400243dd  test    r9w, r9w
0x1400243e1  jz      short loc_140024405
0x1400243e3  inc     edx
0x1400243e5  mov     [rdi+30h], edx
0x1400243e8  test    ecx, ecx
0x1400243ea  jz      short loc_14002440D
0x1400243ec  inc     r10d
0x1400243ef  movzx   r9d, word ptr [r11+rdx*2]
0x1400243f4  cmp     r9w, word ptr ds:rva aUll[r8+r10*2]; "ull" ...
0x1400243fd  jnz     loc_1400244AE
0x140024403  jmp     short loc_1400243DB
0x140024405  test    ecx, ecx
0x140024407  jnz     loc_1400244AE
0x14002440d  mov     r9d, 123h; int
0x140024413  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002441a  mov     edx, 1; int
0x14002441f  lea     ecx, [rdx+3Fh]; unsigned __int64
0x140024422  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140024427  mov     rcx, rax
0x14002442a  mov     [rbp+pExceptionObject], rax
0x14002442e  test    rax, rax
0x140024431  jz      loc_140024319
0x140024437  mov     dword ptr [rax+8], 6
0x14002443e  lea     rdx, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x140024445  mov     [rax], rdx
0x140024448  mov     [rax+10h], r14b
0x14002444c  jmp     loc_1400242FB
0x140024451  mov     edx, 0CAA60007h; int
0x140024456  lea     rcx, [rbp+pExceptionObject]; this
0x14002445a  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002445f  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140024466  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14002446a  call    _CxxThrowException_0
0x140024470  mov     edx, 0CAA60007h; int
0x140024475  lea     rcx, [rbp+pExceptionObject]; this
0x140024479  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002447e  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140024485  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140024489  call    _CxxThrowException_0
0x14002448f  mov     edx, 0CAA60007h; int
0x140024494  lea     rcx, [rbp+pExceptionObject]; this
0x140024498  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002449d  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400244a4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400244a8  call    _CxxThrowException_0
0x1400244ae  mov     edx, 0CAA60007h; int
0x1400244b3  lea     rcx, [rbp+pExceptionObject]; this
0x1400244b7  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x1400244bc  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x1400244c3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400244c7  call    _CxxThrowException_0
```
