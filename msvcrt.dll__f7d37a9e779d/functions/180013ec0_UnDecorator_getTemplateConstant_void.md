# UnDecorator::getTemplateConstant(void)

- ea: `0x180013ec0`
- end: `0x180014229`
- name: `?getTemplateConstant@UnDecorator@@CA?AVDName@@XZ`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180013c5c`

## callees

- `0x180002150`
- `0x18000e3d0`
- `0x18000e4a8`
- `0x18000e4f0`
- `0x18000ebe8`
- `0x18000ecf4`
- `0x18000edd4`
- `0x18000ef94`
- `0x18000f040`
- `0x18001152c`
- `0x180013920`
- `0x1800139a0`
- `0x180013ec0`
- `0x180014bb0`
- `0x180079760`
- `0x18007d020`

## string_xrefs

- `0x18001414c`: ``non-type-template-parameter`
- `0x180014118`: ``template-parameter`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateConstant(DName *a1)
{
  int v2; // esi
  char *v3; // rcx
  __int64 v4; // rdx
  DName *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  char *v9; // r8
  __int64 v10; // rcx
  const char *v11; // rdx
  DName *v12; // rbx
  __int64 v13; // rax
  char *(*v14)(int); // rbx
  unsigned int v15; // eax
  __int64 v16; // rax
  const char *v17; // rdx
  DName *v18; // rax
  __int64 DecoratedName; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 SignedDimension; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  _BYTE v29[8]; // [rsp+20h] [rbp-79h] BYREF
  int v30; // [rsp+28h] [rbp-71h]
  char v31[16]; // [rsp+30h] [rbp-69h] BYREF
  char String[8]; // [rsp+40h] [rbp-59h] BYREF
  int v33; // [rsp+48h] [rbp-51h]
  char v34; // [rsp+50h] [rbp-49h] BYREF
  char v35; // [rsp+51h] [rbp-48h] BYREF
  char v36; // [rsp+52h] [rbp-47h]

  v2 = *UnDecorator::gName;
  v3 = ++UnDecorator::gName;
  if ( v2 > 70 )
  {
    if ( v2 != 71 && v2 != 72 && v2 != 73 && v2 != 74 )
    {
      if ( v2 == 81 )
        goto LABEL_34;
      if ( v2 == 82 )
      {
        UnDecorator::getZName(String, 0);
        UnDecorator::getSignedDimension(v31);
        v13 = *(_QWORD *)String;
        *((_DWORD *)a1 + 2) &= 0xFFFFF000;
        *(_QWORD *)a1 = v13;
        *((_DWORD *)a1 + 2) |= v33 & 0xFFF;
        return a1;
      }
LABEL_13:
      v4 = 1;
LABEL_14:
      DName::DName(a1, v4);
      return a1;
    }
    goto LABEL_41;
  }
  if ( v2 == 70 )
  {
LABEL_41:
    DName::DName((DName *)v29, 123);
    if ( v2 == 72 || (unsigned int)(v2 - 73) <= 1 )
    {
      DecoratedName = UnDecorator::getDecoratedName(v31);
      DName::operator+=(v29, DecoratedName);
      LOBYTE(v20) = 44;
      DName::operator+=(v29, v20);
    }
    if ( v2 != 70 )
    {
      if ( v2 == 71 )
        goto LABEL_48;
      if ( v2 == 72 )
      {
LABEL_50:
        SignedDimension = UnDecorator::getSignedDimension(v31);
        DName::operator+=(v29, SignedDimension);
        LOBYTE(v26) = 125;
        DName::operator+(v29, a1, v26, v27);
        return a1;
      }
      if ( v2 != 73 )
      {
LABEL_48:
        v21 = UnDecorator::getSignedDimension(v31);
        DName::operator+=(v29, v21);
        LOBYTE(v22) = 44;
        DName::operator+=(v29, v22);
      }
    }
    v23 = UnDecorator::getSignedDimension(v31);
    DName::operator+=(v29, v23);
    LOBYTE(v24) = 44;
    DName::operator+=(v29, v24);
    goto LABEL_50;
  }
  if ( !(_BYTE)v2 )
  {
    UnDecorator::gName = v3 - 1;
    goto LABEL_26;
  }
  switch ( v2 )
  {
    case '0':
      UnDecorator::getSignedDimension(a1);
      return a1;
    case '1':
      if ( *v3 == 64 )
      {
        UnDecorator::gName = v3 + 1;
        v11 = "NULL";
LABEL_22:
        DName::DName(a1, v11);
        return a1;
      }
      v12 = DName::DName((DName *)v31, "&");
      v9 = (char *)UnDecorator::getDecoratedName(String);
      v10 = (__int64)v12;
      goto LABEL_19;
    case '2':
      UnDecorator::getSignedDimension(v29);
      UnDecorator::getSignedDimension(String);
      if ( ((v30 << 28 >> 28) & 0xFFFFFFFD) == 0 && ((v33 << 28 >> 28) & 0xFFFFFFFD) == 0 )
      {
        if ( !DName::getString((DName *)v29, &v35, 99) )
          goto LABEL_13;
        v34 = v35;
        if ( v35 == 45 )
        {
          v35 = v36;
          v36 = 46;
        }
        else
        {
          v35 = 46;
        }
        v5 = DName::DName((DName *)v29, &v34);
        LOBYTE(v6) = 101;
        v8 = DName::operator+(v5, v31, v6, v7);
        v9 = String;
        v10 = v8;
LABEL_19:
        DName::operator+(v10, a1, v9);
        return a1;
      }
LABEL_26:
      v4 = 2;
      goto LABEL_14;
  }
  if ( v2 != 68 )
  {
    if ( v2 == 69 )
    {
      UnDecorator::getDecoratedName(a1);
      return a1;
    }
    goto LABEL_13;
  }
LABEL_34:
  UnDecorator::getSignedDimension(v29);
  if ( (UnDecorator::disableFlags & 0x4000) != 0 )
  {
    DName::getString((DName *)v29, String, 16);
    v14 = UnDecorator::m_pGetParameter;
    v15 = atol(String);
    v16 = ((__int64 (__fastcall *)(_QWORD))v14)(v15);
    if ( v16 )
    {
      v11 = (const char *)v16;
      goto LABEL_22;
    }
  }
  if ( (_BYTE)v2 == 68 )
    v17 = "`template-parameter";
  else
    v17 = "`non-type-template-parameter";
  v18 = DName::DName((DName *)v31, v17);
  DName::operator+(v18, String, v29);
  DName::operator+(String, a1, "'");
  return a1;
}

```

## disassembly

```asm
0x180013ec0  push    rbp
0x180013ec2  push    rbx
0x180013ec3  push    rsi
0x180013ec4  push    rdi
0x180013ec5  lea     rbp, [rsp-3Fh]
0x180013eca  sub     rsp, 0D8h
0x180013ed1  mov     rax, cs:__security_cookie
0x180013ed8  xor     rax, rsp
0x180013edb  mov     [rbp+57h+var_30], rax
0x180013edf  mov     rdi, rcx
0x180013ee2  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180013ee9  movsx   esi, byte ptr [rcx]
0x180013eec  inc     rcx
0x180013eef  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx; char const * const UnDecorator::gName
0x180013ef6  mov     ebx, esi
0x180013ef8  cmp     esi, 46h ; 'F'
0x180013efb  jg      loc_180014059
0x180013f01  jz      loc_180014155
0x180013f07  test    sil, sil
0x180013f0a  jz      loc_180014044
0x180013f10  sub     ebx, 30h ; '0'
0x180013f13  jz      loc_180014037
0x180013f19  sub     ebx, 1
0x180013f1c  jz      loc_180013FEF
0x180013f22  sub     ebx, 1
0x180013f25  jz      short loc_180013F42
0x180013f27  sub     ebx, 12h
0x180013f2a  jz      loc_1800140BF
0x180013f30  cmp     ebx, 1
0x180013f33  jnz     short loc_180013F93
0x180013f35  mov     rcx, rdi
0x180013f38  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x180013f3d  jmp     loc_18001420E
0x180013f42  lea     rcx, [rbp+57h+var_D0]
0x180013f46  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x180013f4b  lea     rcx, [rbp+57h+String]
0x180013f4f  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x180013f54  mov     eax, [rbp+57h+var_C8]
0x180013f57  mov     ecx, 0FFFFFFFDh
0x180013f5c  shl     eax, 1Ch
0x180013f5f  sar     eax, 1Ch
0x180013f62  test    ecx, eax
0x180013f64  jnz     loc_18001404F
0x180013f6a  mov     eax, [rbp+57h+var_A8]
0x180013f6d  shl     eax, 1Ch
0x180013f70  sar     eax, 1Ch
0x180013f73  test    ecx, eax
0x180013f75  jnz     loc_18001404F
0x180013f7b  mov     r8d, 63h ; 'c'; int
0x180013f81  lea     rdx, [rbp+57h+var_9F]; char *
0x180013f85  lea     rcx, [rbp+57h+var_D0]; this
0x180013f89  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x180013f8e  test    rax, rax
0x180013f91  jnz     short loc_180013FA5
0x180013f93  mov     edx, 1
0x180013f98  mov     rcx, rdi
0x180013f9b  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x180013fa0  jmp     loc_18001420E
0x180013fa5  mov     al, [rbp+57h+var_9F]
0x180013fa8  mov     [rbp+57h+var_A0], al
0x180013fab  cmp     al, 2Dh ; '-'
0x180013fad  jnz     short loc_180013FBB
0x180013faf  mov     al, [rbp+57h+var_9E]
0x180013fb2  mov     [rbp+57h+var_9F], al
0x180013fb5  mov     [rbp+57h+var_9E], 2Eh ; '.'
0x180013fb9  jmp     short loc_180013FBF
0x180013fbb  mov     [rbp+57h+var_9F], 2Eh ; '.'
0x180013fbf  lea     rdx, [rbp+57h+var_A0]; char *
0x180013fc3  lea     rcx, [rbp+57h+var_D0]; this
0x180013fc7  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180013fcc  mov     r8b, 65h ; 'e'
0x180013fcf  lea     rdx, [rbp+57h+var_C0]
0x180013fd3  mov     rcx, rax
0x180013fd6  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x180013fdb  lea     r8, [rbp+57h+String]
0x180013fdf  mov     rcx, rax
0x180013fe2  mov     rdx, rdi
0x180013fe5  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180013fea  jmp     loc_18001420E
0x180013fef  cmp     byte ptr [rcx], 40h ; '@'
0x180013ff2  jnz     short loc_180014013
0x180013ff4  lea     rax, [rcx+1]
0x180013ff8  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x180013fff  lea     rdx, aNull; "NULL"
0x180014006  mov     rcx, rdi; this
0x180014009  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x18001400e  jmp     loc_18001420E
0x180014013  lea     rdx, asc_18008178C; "&"
0x18001401a  lea     rcx, [rbp+57h+var_C0]; this
0x18001401e  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180014023  lea     rcx, [rbp+57h+String]
0x180014027  mov     rbx, rax
0x18001402a  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18001402f  mov     r8, rax
0x180014032  mov     rcx, rbx
0x180014035  jmp     short loc_180013FE2
0x180014037  mov     rcx, rdi
0x18001403a  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18001403f  jmp     loc_18001420E
0x180014044  lea     rax, [rcx-1]
0x180014048  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x18001404f  mov     edx, 2
0x180014054  jmp     loc_180013F98
0x180014059  mov     ecx, ebx
0x18001405b  sub     ecx, 47h ; 'G'
0x18001405e  jz      loc_180014155
0x180014064  sub     ecx, 1
0x180014067  jz      loc_180014155
0x18001406d  sub     ecx, 1
0x180014070  jz      loc_180014155
0x180014076  sub     ecx, 1
0x180014079  jz      loc_180014155
0x18001407f  sub     ecx, 7
0x180014082  jz      short loc_1800140BF
0x180014084  cmp     ecx, 1
0x180014087  jnz     loc_180013F93
0x18001408d  xor     edx, edx
0x18001408f  lea     rcx, [rbp+57h+String]
0x180014093  call    ?getZName@UnDecorator@@CA?AVDName@@_N@Z; UnDecorator::getZName(bool)
0x180014098  lea     rcx, [rbp+57h+var_C0]
0x18001409c  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1800140a1  mov     rax, qword ptr [rbp+57h+String]
0x1800140a5  and     dword ptr [rdi+8], 0FFFFF000h
0x1800140ac  mov     [rdi], rax
0x1800140af  mov     eax, [rbp+57h+var_A8]
0x1800140b2  and     eax, 0FFFh
0x1800140b7  or      [rdi+8], eax
0x1800140ba  jmp     loc_18001420E
0x1800140bf  lea     rcx, [rbp+57h+var_D0]
0x1800140c3  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1800140c8  test    cs:?disableFlags@UnDecorator@@0KA, 4000h; ulong UnDecorator::disableFlags
0x1800140d2  jz      short loc_18001410E
0x1800140d4  mov     r8d, 10h; int
0x1800140da  lea     rdx, [rbp+57h+String]; char *
0x1800140de  lea     rcx, [rbp+57h+var_D0]; this
0x1800140e2  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x1800140e7  mov     rbx, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA; char * (*UnDecorator::m_pGetParameter)(long)
0x1800140ee  lea     rcx, [rbp+57h+String]; String
0x1800140f2  call    atol
0x1800140f7  mov     ecx, eax
0x1800140f9  mov     rax, rbx
0x1800140fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014101  test    rax, rax
0x180014104  jz      short loc_18001410E
0x180014106  mov     rdx, rax
0x180014109  jmp     loc_180014006
0x18001410e  lea     rcx, [rbp+57h+var_C0]; this
0x180014112  cmp     sil, 44h ; 'D'
0x180014116  jnz     short loc_18001414C
0x180014118  lea     rdx, aTemplateParame; "`template-parameter"
0x18001411f  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180014124  lea     r8, [rbp+57h+var_D0]
0x180014128  mov     rcx, rax
0x18001412b  lea     rdx, [rbp+57h+String]
0x18001412f  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180014134  lea     r8, asc_180081CFC; "'"
0x18001413b  mov     rdx, rdi
0x18001413e  lea     rcx, [rbp+57h+String]
0x180014142  call    ??HDName@@QEBA?AV0@PEBD@Z; DName::operator+(char const *)
0x180014147  jmp     loc_18001420E
0x18001414c  lea     rdx, aNonTypeTemplat; "`non-type-template-parameter"
0x180014153  jmp     short loc_18001411F
0x180014155  mov     dl, 7Bh ; '{'; char
0x180014157  lea     rcx, [rbp+57h+var_D0]; this
0x18001415b  call    ??0DName@@QEAA@D@Z; DName::DName(char)
0x180014160  mov     ecx, ebx
0x180014162  sub     ecx, 48h ; 'H'
0x180014165  jz      short loc_180014171
0x180014167  sub     ecx, 1
0x18001416a  jz      short loc_180014171
0x18001416c  cmp     ecx, 1
0x18001416f  jnz     short loc_180014191
0x180014171  lea     rcx, [rbp+57h+var_C0]
0x180014175  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18001417a  mov     rdx, rax
0x18001417d  lea     rcx, [rbp+57h+var_D0]
0x180014181  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x180014186  mov     dl, 2Ch ; ','
0x180014188  lea     rcx, [rbp+57h+var_D0]
0x18001418c  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x180014191  sub     ebx, 46h ; 'F'
0x180014194  jz      short loc_1800141CA
0x180014196  sub     ebx, 1
0x180014199  jz      short loc_1800141AA
0x18001419b  sub     ebx, 1
0x18001419e  jz      short loc_1800141EA
0x1800141a0  sub     ebx, 1
0x1800141a3  jz      short loc_1800141CA
0x1800141a5  cmp     ebx, 1
0x1800141a8  jnz     short loc_1800141FF
0x1800141aa  lea     rcx, [rbp+57h+var_C0]
0x1800141ae  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1800141b3  mov     rdx, rax
0x1800141b6  lea     rcx, [rbp+57h+var_D0]
0x1800141ba  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1800141bf  mov     dl, 2Ch ; ','
0x1800141c1  lea     rcx, [rbp+57h+var_D0]
0x1800141c5  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1800141ca  lea     rcx, [rbp+57h+var_C0]
0x1800141ce  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1800141d3  mov     rdx, rax
0x1800141d6  lea     rcx, [rbp+57h+var_D0]
0x1800141da  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1800141df  mov     dl, 2Ch ; ','
0x1800141e1  lea     rcx, [rbp+57h+var_D0]
0x1800141e5  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1800141ea  lea     rcx, [rbp+57h+var_C0]
0x1800141ee  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1800141f3  mov     rdx, rax
0x1800141f6  lea     rcx, [rbp+57h+var_D0]
0x1800141fa  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1800141ff  mov     r8b, 7Dh ; '}'
0x180014202  lea     rcx, [rbp+57h+var_D0]
0x180014206  mov     rdx, rdi
0x180014209  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18001420e  mov     rax, rdi
0x180014211  mov     rcx, [rbp+57h+var_30]
0x180014215  xor     rcx, rsp; StackCookie
0x180014218  call    __security_check_cookie
0x18001421d  add     rsp, 0D8h
0x180014224  pop     rdi
0x180014225  pop     rsi
0x180014226  pop     rbx
0x180014227  pop     rbp
0x180014228  retn
```
