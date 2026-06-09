# UnDecorator::getTemplateArgumentList(void)

- ea: `0x180013c5c`
- end: `0x180013eba`
- name: `?getTemplateArgumentList@UnDecorator@@CA?AVDName@@XZ`
- size: `606`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x1800125f8`
- `0x180014230`

## callees

- `0x180002150`
- `0x18000e4a8`
- `0x18000e880`
- `0x18000e938`
- `0x18000ebe8`
- `0x18000edd4`
- `0x18000ef94`
- `0x18000f040`
- `0x18000f298`
- `0x180012fc4`
- `0x180013920`
- `0x1800139a0`
- `0x180013c5c`
- `0x180013ec0`
- `0x180079760`
- `0x18007d020`

## string_xrefs

- `0x180013dc6`: ``template-parameter`
- `0x180013dfc`: ``template-parameter`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateArgumentList(__int64 a1, __int64 a2)
{
  int v2; // r14d
  char *v4; // rdi
  __int64 v5; // rax
  char *v6; // rdx
  const char *v7; // rdx
  DName *TemplateConstant; // rax
  char *(*v9)(int); // rbx
  unsigned int v10; // eax
  __int64 v11; // rax
  DName *v12; // rax
  char *v13; // rdx
  _BYTE *v14; // rcx
  DName *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-89h] BYREF
  int v18; // [rsp+28h] [rbp-81h]
  _BYTE v19[16]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h] BYREF
  int v21; // [rsp+48h] [rbp-61h]
  _BYTE v22[16]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-29h] BYREF
  char v26; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v27[16]; // [rsp+A0h] [rbp-9h] BYREF
  char v28; // [rsp+B0h] [rbp+7h] BYREF
  _BYTE v29[16]; // [rsp+C0h] [rbp+17h] BYREF
  char String[16]; // [rsp+D0h] [rbp+27h] BYREF

  *(_DWORD *)(a1 + 8) &= 0xFFFFF000;
  v2 = 1;
  *(_QWORD *)a1 = 0;
  UnDecorator::fGetTemplateArgumentList = 1;
  if ( (*(_BYTE *)(a1 + 8) & 0xF) == 0 )
  {
    while ( 1 )
    {
      v4 = UnDecorator::gName;
      if ( (*UnDecorator::gName & 0xBF) == 0 )
        goto LABEL_31;
      if ( v2 )
      {
        v2 = 0;
      }
      else
      {
        LOBYTE(a2) = 44;
        DName::operator+=(a1, a2);
        v4 = UnDecorator::gName;
      }
      v5 = *v4;
      if ( (unsigned int)(v5 - 48) > 9 )
        break;
      UnDecorator::gName = v4 + 1;
      if ( *(_DWORD *)UnDecorator::pTemplateArgList == -1 || (int)v5 - 48 > *(_DWORD *)UnDecorator::pTemplateArgList )
        v6 = (char *)UnDecorator::pTemplateArgList + 104;
      else
        v6 = (char *)*((_QWORD *)UnDecorator::pTemplateArgList + v5 - 47);
LABEL_30:
      DName::operator+=(a1, v6);
      if ( (*(_BYTE *)(a1 + 8) & 0xF) != 0 )
        goto LABEL_31;
    }
    v18 &= 0xFFFFF000;
    v17 = 0;
    switch ( (_BYTE)v5 )
    {
      case 'X':
        UnDecorator::gName = v4 + 1;
        v7 = "void";
LABEL_13:
        DName::operator=(&v17, v7);
        goto LABEL_26;
      case '$':
        if ( v4[1] != 36 )
        {
          UnDecorator::gName = v4 + 1;
          TemplateConstant = UnDecorator::getTemplateConstant((DName *)v24);
          goto LABEL_25;
        }
        break;
      case '?':
        UnDecorator::getSignedDimension(v19);
        if ( (UnDecorator::disableFlags & 0x4000) != 0 )
        {
          DName::getString((DName *)v19, String, 16);
          v9 = UnDecorator::m_pGetParameter;
          v10 = atol(String);
          v11 = ((__int64 (__fastcall *)(_QWORD))v9)(v10);
          if ( v11 )
          {
            v7 = (const char *)v11;
            goto LABEL_13;
          }
          v12 = DName::DName((DName *)v25, "`template-parameter");
          DName::operator+(v12, v22, v19);
          v13 = &v26;
          v14 = v22;
        }
        else
        {
          v15 = DName::DName((DName *)v27, "`template-parameter");
          DName::operator+(v15, v23, v19);
          v13 = &v28;
          v14 = v23;
        }
        TemplateConstant = (DName *)DName::operator+(v14, v13, "'");
LABEL_25:
        DName::operator=(&v17, TemplateConstant);
LABEL_26:
        if ( UnDecorator::gName - v4 > 1 && *(_DWORD *)UnDecorator::pTemplateArgList != 9 )
          Replicator::operator+=(UnDecorator::pTemplateArgList, &v17);
        v6 = (char *)&v17;
        goto LABEL_30;
    }
    v21 &= 0xFFFFF000;
    v20 = 0;
    TemplateConstant = (DName *)UnDecorator::getPrimaryDataType(v29, &v20);
    goto LABEL_25;
  }
LABEL_31:
  UnDecorator::fGetTemplateArgumentList = 0;
  return a1;
}

```

## disassembly

```asm
0x180013c5c  mov     [rsp-8+arg_8], rbx
0x180013c61  mov     [rsp-8+arg_10], rsi
0x180013c66  push    rbp
0x180013c67  push    rdi
0x180013c68  push    r14
0x180013c6a  lea     rbp, [rsp-47h]
0x180013c6f  sub     rsp, 0F0h
0x180013c76  mov     rax, cs:__security_cookie
0x180013c7d  xor     rax, rsp
0x180013c80  mov     [rbp+57h+var_20], rax
0x180013c84  and     dword ptr [rcx+8], 0FFFFF000h
0x180013c8b  mov     r14d, 1
0x180013c91  mov     qword ptr [rcx], 0
0x180013c98  mov     rsi, rcx
0x180013c9b  mov     cs:?fGetTemplateArgumentList@UnDecorator@@0_NA, r14b; bool UnDecorator::fGetTemplateArgumentList
0x180013ca2  test    byte ptr [rcx+8], 0Fh
0x180013ca6  jnz     loc_180013E8C
0x180013cac  mov     rdi, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180013cb3  test    byte ptr [rdi], 0BFh
0x180013cb6  jz      loc_180013E8C
0x180013cbc  test    r14d, r14d
0x180013cbf  jz      short loc_180013CC6
0x180013cc1  xor     r14d, r14d
0x180013cc4  jmp     short loc_180013CD7
0x180013cc6  mov     dl, 2Ch ; ','
0x180013cc8  mov     rcx, rsi
0x180013ccb  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x180013cd0  mov     rdi, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180013cd7  movsx   rax, byte ptr [rdi]
0x180013cdb  lea     edx, [rax-30h]
0x180013cde  cmp     edx, 9
0x180013ce1  ja      short loc_180013D13
0x180013ce3  mov     rcx, cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pTemplateArgList
0x180013cea  inc     rdi
0x180013ced  mov     cs:?gName@UnDecorator@@0PEBDEB, rdi; char const * const UnDecorator::gName
0x180013cf4  cmp     dword ptr [rcx], 0FFFFFFFFh
0x180013cf7  jz      short loc_180013D0A
0x180013cf9  cmp     edx, [rcx]
0x180013cfb  jg      short loc_180013D0A
0x180013cfd  mov     rdx, [rcx+rax*8-178h]
0x180013d05  jmp     loc_180013E7A
0x180013d0a  lea     rdx, [rcx+68h]
0x180013d0e  jmp     loc_180013E7A
0x180013d13  and     [rsp+100h+var_D8], 0FFFFF000h
0x180013d1b  mov     [rsp+100h+var_E0], 0
0x180013d24  cmp     al, 58h ; 'X'
0x180013d26  jnz     short loc_180013D49
0x180013d28  lea     rax, [rdi+1]
0x180013d2c  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x180013d33  lea     rdx, aVoid_0; "void"
0x180013d3a  lea     rcx, [rsp+100h+var_E0]
0x180013d3f  call    ??4DName@@QEAAAEAV0@PEBD@Z; DName::operator=(char const *)
0x180013d44  jmp     loc_180013E4F
0x180013d49  cmp     al, 24h ; '$'
0x180013d4b  jnz     short loc_180013D6F
0x180013d4d  cmp     [rdi+1], al
0x180013d50  jz      loc_180013E26
0x180013d56  lea     rax, [rdi+1]
0x180013d5a  lea     rcx, [rbp+57h+var_90]
0x180013d5e  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x180013d65  call    ?getTemplateConstant@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getTemplateConstant(void)
0x180013d6a  jmp     loc_180013E42
0x180013d6f  cmp     al, 3Fh ; '?'
0x180013d71  jnz     loc_180013E26
0x180013d77  lea     rcx, [rbp+57h+var_D0]
0x180013d7b  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x180013d80  test    cs:?disableFlags@UnDecorator@@0KA, 4000h; ulong UnDecorator::disableFlags
0x180013d8a  jz      short loc_180013DFC
0x180013d8c  mov     r8d, 10h; int
0x180013d92  lea     rdx, [rbp+57h+String]; char *
0x180013d96  lea     rcx, [rbp+57h+var_D0]; this
0x180013d9a  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x180013d9f  mov     rbx, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA; char * (*UnDecorator::m_pGetParameter)(long)
0x180013da6  lea     rcx, [rbp+57h+String]; String
0x180013daa  call    atol
0x180013daf  mov     ecx, eax
0x180013db1  mov     rax, rbx
0x180013db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db9  test    rax, rax
0x180013dbc  jz      short loc_180013DC6
0x180013dbe  mov     rdx, rax
0x180013dc1  jmp     loc_180013D3A
0x180013dc6  lea     rdx, aTemplateParame; "`template-parameter"
0x180013dcd  lea     rcx, [rbp+57h+var_80]; this
0x180013dd1  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180013dd6  lea     r8, [rbp+57h+var_D0]
0x180013dda  mov     rcx, rax
0x180013ddd  lea     rdx, [rbp+57h+var_B0]
0x180013de1  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180013de6  lea     rdx, [rbp+57h+var_70]
0x180013dea  lea     rcx, [rbp+57h+var_B0]
0x180013dee  lea     r8, asc_180081CFC; "'"
0x180013df5  call    ??HDName@@QEBA?AV0@PEBD@Z; DName::operator+(char const *)
0x180013dfa  jmp     short loc_180013E42
0x180013dfc  lea     rdx, aTemplateParame; "`template-parameter"
0x180013e03  lea     rcx, [rbp+57h+var_60]; this
0x180013e07  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180013e0c  lea     r8, [rbp+57h+var_D0]
0x180013e10  mov     rcx, rax
0x180013e13  lea     rdx, [rbp+57h+var_A0]
0x180013e17  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180013e1c  lea     rdx, [rbp+57h+var_50]
0x180013e20  lea     rcx, [rbp+57h+var_A0]
0x180013e24  jmp     short loc_180013DEE
0x180013e26  and     [rbp+57h+var_B8], 0FFFFF000h
0x180013e2d  lea     rdx, [rbp+57h+var_C0]
0x180013e31  lea     rcx, [rbp+57h+var_40]
0x180013e35  mov     [rbp+57h+var_C0], 0
0x180013e3d  call    ?getPrimaryDataType@UnDecorator@@CA?AVDName@@AEBV2@@Z; UnDecorator::getPrimaryDataType(DName const &)
0x180013e42  mov     rdx, rax
0x180013e45  lea     rcx, [rsp+100h+var_E0]
0x180013e4a  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x180013e4f  mov     rax, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180013e56  sub     rax, rdi
0x180013e59  cmp     rax, 1
0x180013e5d  jle     short loc_180013E75
0x180013e5f  mov     rcx, cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pTemplateArgList
0x180013e66  cmp     dword ptr [rcx], 9
0x180013e69  jz      short loc_180013E75
0x180013e6b  lea     rdx, [rsp+100h+var_E0]
0x180013e70  call    ??YReplicator@@QEAAAEAV0@AEBVDName@@@Z; Replicator::operator+=(DName const &)
0x180013e75  lea     rdx, [rsp+100h+var_E0]
0x180013e7a  mov     rcx, rsi
0x180013e7d  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x180013e82  test    byte ptr [rsi+8], 0Fh
0x180013e86  jz      loc_180013CAC
0x180013e8c  mov     cs:?fGetTemplateArgumentList@UnDecorator@@0_NA, 0; bool UnDecorator::fGetTemplateArgumentList
0x180013e93  mov     rax, rsi
0x180013e96  mov     rcx, [rbp+57h+var_20]
0x180013e9a  xor     rcx, rsp; StackCookie
0x180013e9d  call    __security_check_cookie
0x180013ea2  lea     r11, [rsp+100h+var_10]
0x180013eaa  mov     rbx, [r11+28h]
0x180013eae  mov     rsi, [r11+30h]
0x180013eb2  mov     rsp, r11
0x180013eb5  pop     r14
0x180013eb7  pop     rdi
0x180013eb8  pop     rbp
0x180013eb9  retn
```
