# UnDecorator::getTemplateName(bool)

- ea: `0x180014230`
- end: `0x180014464`
- name: `?getTemplateName@UnDecorator@@CA?AVDName@@_N@Z`
- size: `564`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x18000ea20`
- `0x18001152c`
- `0x180013c0c`
- `0x180014bb0`

## callees

- `0x18000e3d0`
- `0x18000e4f0`
- `0x18000e880`
- `0x18000ebe8`
- `0x18000ef94`
- `0x18000f040`
- `0x180012404`
- `0x1800125f8`
- `0x180013c5c`
- `0x180014230`
- `0x180014bb0`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateName(__int64 a1, char a2)
{
  struct Replicator *v4; // r14
  struct Replicator *v5; // r15
  struct Replicator *v6; // r12
  char v7; // bl
  __int64 v8; // rdx
  __int64 OperatorName; // rax
  __int64 v10; // rdx
  __int64 ZName; // rax
  __int64 TemplateArgumentList; // rbx
  DName *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+28h] [rbp-D8h]
  _BYTE v19[16]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v24[24]; // [rsp+C8h] [rbp-38h] BYREF
  int v25; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v26[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v27[24]; // [rsp+148h] [rbp+48h] BYREF
  int v28; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v29[16]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v30[24]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v31; // [rsp+220h] [rbp+120h] BYREF

  if ( *UnDecorator::gName == 63 && UnDecorator::gName[1] == 36 )
  {
    v4 = UnDecorator::pArgList;
    v5 = UnDecorator::pZNameList;
    v6 = UnDecorator::pTemplateArgList;
    UnDecorator::gName += 2;
    DName::DName(v23, 3);
    DName::DName(v24, 1);
    v7 = 0;
    v22 = -1;
    DName::DName(v26, 3);
    DName::DName(v27, 1);
    v25 = -1;
    DName::DName(v29, 3);
    DName::DName(v30, 1);
    v18 &= 0xFFFFF000;
    UnDecorator::pArgList = (struct Replicator *)&v22;
    v28 = -1;
    UnDecorator::pZNameList = (struct Replicator *)&v25;
    v17 = 0;
    UnDecorator::pTemplateArgList = (struct Replicator *)&v28;
    LOBYTE(v8) = 1;
    v31 = 0;
    if ( *UnDecorator::gName == 63 )
    {
      ++UnDecorator::gName;
      OperatorName = UnDecorator::getOperatorName(v19, v8, &v31);
      DName::operator=(&v17, OperatorName);
      v7 = v31;
    }
    else
    {
      ZName = UnDecorator::getZName((__int64)v19, 1);
      DName::operator=(&v17, ZName);
    }
    if ( !v17 || ((v18 << 28 >> 28) & 0xFFFFFFFD) != 0 )
      UnDecorator::fExplicitTemplateParams = 1;
    if ( !v7 )
    {
      TemplateArgumentList = UnDecorator::getTemplateArgumentList((__int64)v20, v10);
      v13 = DName::DName((DName *)v21, 60);
      DName::operator+(v13, v19, TemplateArgumentList);
      DName::operator+=(&v17, v19);
      if ( DName::getLastChar((DName *)&v17) == 62 )
      {
        LOBYTE(v14) = 32;
        DName::operator+=(&v17, v14);
      }
      LOBYTE(v14) = 62;
      DName::operator+=(&v17, v14);
      if ( a2 )
        ++UnDecorator::gName;
    }
    v15 = v17;
    UnDecorator::pArgList = v4;
    UnDecorator::pZNameList = v5;
    UnDecorator::pTemplateArgList = v6;
    *(_DWORD *)(a1 + 8) &= 0xFFFFF000;
    *(_QWORD *)a1 = v15;
    *(_DWORD *)(a1 + 8) |= v18 & 0xFFF;
  }
  else
  {
    DName::DName(a1, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x180014230  mov     [rsp-8+arg_0], rbx
0x180014235  mov     [rsp-8+arg_8], rsi
0x18001423a  push    rbp
0x18001423b  push    rdi
0x18001423c  push    r12
0x18001423e  push    r14
0x180014240  push    r15
0x180014242  lea     rbp, [rsp-0E0h]
0x18001424a  sub     rsp, 1E0h
0x180014251  mov     rax, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180014258  mov     sil, dl
0x18001425b  mov     rdi, rcx
0x18001425e  cmp     byte ptr [rax], 3Fh ; '?'
0x180014261  jnz     loc_18001443B
0x180014267  cmp     byte ptr [rax+1], 24h ; '$'
0x18001426b  jnz     loc_18001443B
0x180014271  mov     r14, cs:?pArgList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pArgList
0x180014278  lea     rcx, [rbp+100h+var_148]
0x18001427c  mov     r15, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pZNameList
0x180014283  add     rax, 2
0x180014287  mov     r12, cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pTemplateArgList
0x18001428e  mov     edx, 3
0x180014293  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x18001429a  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x18001429f  mov     edx, 1
0x1800142a4  lea     rcx, [rbp+100h+var_138]
0x1800142a8  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x1800142ad  or      ebx, 0FFFFFFFFh
0x1800142b0  lea     rcx, [rbp+100h+var_C8]
0x1800142b4  mov     [rsp+200h+var_1A0], ebx
0x1800142b8  lea     edx, [rbx+4]
0x1800142bb  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x1800142c0  lea     edx, [rbx+2]
0x1800142c3  lea     rcx, [rbp+100h+var_B8]
0x1800142c7  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x1800142cc  lea     edx, [rbx+4]
0x1800142cf  mov     [rbp+100h+var_120], ebx
0x1800142d2  lea     rcx, [rbp+100h+var_48]
0x1800142d9  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x1800142de  lea     edx, [rbx+2]
0x1800142e1  lea     rcx, [rbp+100h+var_38]
0x1800142e8  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x1800142ed  and     [rsp+200h+var_1D8], 0FFFFF000h
0x1800142f5  lea     rax, [rsp+200h+var_1A0]
0x1800142fa  mov     cs:?pArgList@UnDecorator@@0PEAVReplicator@@EA, rax; Replicator * UnDecorator::pArgList
0x180014301  lea     rcx, [rsp+200h+var_1D0]
0x180014306  lea     rax, [rbp+100h+var_120]
0x18001430a  mov     [rbp+100h+var_A0], ebx
0x18001430d  mov     cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA, rax; Replicator * UnDecorator::pZNameList
0x180014314  xor     bl, bl
0x180014316  lea     rax, [rbp+100h+var_A0]
0x18001431a  mov     [rsp+200h+var_1E0], 0
0x180014323  mov     cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA, rax; Replicator * UnDecorator::pTemplateArgList
0x18001432a  mov     dl, 1
0x18001432c  mov     rax, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180014333  mov     [rbp+100h+arg_10], bl
0x180014339  cmp     byte ptr [rax], 3Fh ; '?'
0x18001433c  jnz     short loc_180014369
0x18001433e  inc     rax
0x180014341  lea     r8, [rbp+100h+arg_10]
0x180014348  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x18001434f  call    ?getOperatorName@UnDecorator@@CA?AVDName@@_NPEA_N@Z; UnDecorator::getOperatorName(bool,bool *)
0x180014354  mov     rdx, rax
0x180014357  lea     rcx, [rsp+200h+var_1E0]
0x18001435c  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x180014361  mov     bl, [rbp+100h+arg_10]
0x180014367  jmp     short loc_18001437B
0x180014369  call    ?getZName@UnDecorator@@CA?AVDName@@_N@Z; UnDecorator::getZName(bool)
0x18001436e  mov     rdx, rax
0x180014371  lea     rcx, [rsp+200h+var_1E0]
0x180014376  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18001437b  cmp     [rsp+200h+var_1E0], 0
0x180014381  jz      short loc_180014394
0x180014383  mov     eax, [rsp+200h+var_1D8]
0x180014387  shl     eax, 1Ch
0x18001438a  sar     eax, 1Ch
0x18001438d  test    eax, 0FFFFFFFDh
0x180014392  jz      short loc_18001439B
0x180014394  mov     cs:?fExplicitTemplateParams@UnDecorator@@0_NA, 1; bool UnDecorator::fExplicitTemplateParams
0x18001439b  test    bl, bl
0x18001439d  jnz     short loc_180014409
0x18001439f  lea     rcx, [rsp+200h+var_1C0]
0x1800143a4  call    ?getTemplateArgumentList@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getTemplateArgumentList(void)
0x1800143a9  mov     dl, 3Ch ; '<'; char
0x1800143ab  lea     rcx, [rsp+200h+var_1B0]; this
0x1800143b0  mov     rbx, rax
0x1800143b3  call    ??0DName@@QEAA@D@Z; DName::DName(char)
0x1800143b8  mov     r8, rbx
0x1800143bb  lea     rdx, [rsp+200h+var_1D0]
0x1800143c0  mov     rcx, rax
0x1800143c3  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1800143c8  lea     rdx, [rsp+200h+var_1D0]
0x1800143cd  lea     rcx, [rsp+200h+var_1E0]
0x1800143d2  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1800143d7  lea     rcx, [rsp+200h+var_1E0]; this
0x1800143dc  call    ?getLastChar@DName@@QEBADXZ; DName::getLastChar(void)
0x1800143e1  cmp     al, 3Eh ; '>'
0x1800143e3  jnz     short loc_1800143F1
0x1800143e5  mov     dl, 20h ; ' '
0x1800143e7  lea     rcx, [rsp+200h+var_1E0]
0x1800143ec  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1800143f1  mov     dl, 3Eh ; '>'
0x1800143f3  lea     rcx, [rsp+200h+var_1E0]
0x1800143f8  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1800143fd  test    sil, sil
0x180014400  jz      short loc_180014409
0x180014402  inc     cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180014409  mov     rax, [rsp+200h+var_1E0]
0x18001440e  mov     cs:?pArgList@UnDecorator@@0PEAVReplicator@@EA, r14; Replicator * UnDecorator::pArgList
0x180014415  mov     cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA, r15; Replicator * UnDecorator::pZNameList
0x18001441c  mov     cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA, r12; Replicator * UnDecorator::pTemplateArgList
0x180014423  and     dword ptr [rdi+8], 0FFFFF000h
0x18001442a  mov     [rdi], rax
0x18001442d  mov     eax, [rsp+200h+var_1D8]
0x180014431  and     eax, 0FFFh
0x180014436  or      [rdi+8], eax
0x180014439  jmp     short loc_180014445
0x18001443b  mov     edx, 1
0x180014440  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x180014445  lea     r11, [rsp+200h+var_20]
0x18001444d  mov     rax, rdi
0x180014450  mov     rbx, [r11+30h]
0x180014454  mov     rsi, [r11+38h]
0x180014458  mov     rsp, r11
0x18001445b  pop     r15
0x18001445d  pop     r14
0x18001445f  pop     r12
0x180014461  pop     rdi
0x180014462  pop     rbp
0x180014463  retn
```
