# UnDecorator::getZName(bool)

- ea: `0x180014bb0`
- end: `0x180014ef6`
- name: `?getZName@UnDecorator@@CA?AVDName@@_N@Z`
- size: `838`
- prototype: ``
- caller_count: `7`
- callee_count: `16`
- tags: ``

## callers

- `0x18001152c`
- `0x1800125f8`
- `0x180013490`
- `0x180013810`
- `0x180013c0c`
- `0x180013ec0`
- `0x180014230`

## callees

- `0x180002150`
- `0x18000e2d0`
- `0x18000e4a8`
- `0x18000e880`
- `0x18000e938`
- `0x18000e974`
- `0x18000ebe8`
- `0x18000edd4`
- `0x18000ef94`
- `0x18000f298`
- `0x180013920`
- `0x1800139a0`
- `0x180014230`
- `0x180014bb0`
- `0x180079760`
- `0x18007d020`

## string_xrefs

- `0x180014d2c`: `template-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getZName(__int64 a1, char a2)
{
  __int64 v4; // rcx
  char *v5; // r8
  unsigned int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // edx
  int v11; // eax
  int v12; // ecx
  int v13; // edx
  bool v14; // zf
  __int64 TemplateName; // rax
  char v16; // al
  char *v17; // rcx
  const char *v18; // rsi
  char *v19; // rcx
  const char *v20; // rax
  int v21; // r9d
  char *v22; // r8
  char *v23; // rcx
  const char *v24; // rax
  int v25; // r9d
  char *(*v26)(int); // rbx
  unsigned int v27; // eax
  __int64 v28; // rax
  DName *v29; // rax
  char *v30; // rdx
  DName *v31; // rax
  __int64 v32; // rax
  DName *v33; // rax
  __int64 v34; // rax
  __int64 v36; // [rsp+20h] [rbp-29h] BYREF
  int v37; // [rsp+28h] [rbp-21h]
  _BYTE v38[16]; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v39[16]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v40[16]; // [rsp+50h] [rbp+7h] BYREF
  char v41[16]; // [rsp+60h] [rbp+17h] BYREF
  char String[16]; // [rsp+70h] [rbp+27h] BYREF

  v4 = *UnDecorator::gName;
  if ( (unsigned int)(v4 - 48) <= 9 )
  {
    ++UnDecorator::gName;
    if ( *(_DWORD *)UnDecorator::pZNameList == -1 || (int)v4 - 48 > *(_DWORD *)UnDecorator::pZNameList )
    {
      v5 = (char *)UnDecorator::pZNameList + 104;
    }
    else
    {
      _mm_lfence();
      v5 = (char *)*((_QWORD *)UnDecorator::pZNameList + v4 - 47);
    }
    v6 = *((_DWORD *)v5 + 2) ^ (*(_DWORD *)(a1 + 8) ^ *((_DWORD *)v5 + 2)) & 0xFFFFFFF0;
    *(_DWORD *)(a1 + 8) = v6;
    v7 = v6 ^ (*((_DWORD *)v5 + 2) ^ v6) & 0x10;
    *(_DWORD *)(a1 + 8) = v7;
    v8 = v7 ^ (*((_DWORD *)v5 + 2) ^ v7) & 0x20;
    *(_DWORD *)(a1 + 8) = v8;
    v9 = v8 ^ (*((_DWORD *)v5 + 2) ^ v8) & 0x40;
    *(_DWORD *)(a1 + 8) = v9;
    v10 = v9 ^ (*((_DWORD *)v5 + 2) ^ v9) & 0x80;
    *(_DWORD *)(a1 + 8) = v10;
    *(_QWORD *)a1 = *(_QWORD *)v5;
    v11 = v10 ^ (*((_DWORD *)v5 + 2) ^ v10) & 0x100;
    *(_DWORD *)(a1 + 8) = v11;
    v12 = v11 ^ (*((_DWORD *)v5 + 2) ^ v11) & 0x200;
    *(_DWORD *)(a1 + 8) = v12;
    v13 = v12 ^ (*((_DWORD *)v5 + 2) ^ v12) & 0x400;
    *(_DWORD *)(a1 + 8) = v13;
    *(_DWORD *)(a1 + 8) = v13 ^ (*((_DWORD *)v5 + 2) ^ v13) & 0x800;
    return a1;
  }
  v37 &= 0xFFFFF000;
  v14 = *UnDecorator::gName == 63;
  v36 = 0;
  if ( v14 )
  {
    TemplateName = UnDecorator::getTemplateName(v38, 0);
    DName::operator=(&v36, TemplateName);
    v16 = *UnDecorator::gName;
    v17 = ++UnDecorator::gName;
    if ( v16 != 64 )
    {
      UnDecorator::gName = v17 - 1;
      DName::operator=(&v36, 2 - (unsigned int)(*(v17 - 1) != 0));
    }
    goto LABEL_29;
  }
  v18 = "template-parameter-";
  v19 = UnDecorator::gName;
  v20 = "template-parameter-";
  v21 = 18;
  do
  {
    if ( !*v19 )
      break;
    if ( *v19 != *v20 )
      break;
    ++v19;
    ++v20;
    --v21;
  }
  while ( v21 );
  if ( *v19 == *v20 )
  {
    v22 = UnDecorator::gName + 19;
  }
  else
  {
    v18 = "generic-type-";
    v23 = UnDecorator::gName;
    v24 = "generic-type-";
    v25 = 12;
    do
    {
      if ( !*v23 )
        break;
      if ( *v23 != *v24 )
        break;
      ++v23;
      ++v24;
      --v25;
    }
    while ( v25 );
    if ( *v23 != *v24 )
    {
      v33 = DName::DName((DName *)v40, (const char **)&UnDecorator::gName, 64);
      DName::operator=(&v36, v33);
      goto LABEL_29;
    }
    v22 = UnDecorator::gName + 13;
  }
  UnDecorator::gName = v22;
  UnDecorator::getSignedDimension(v39);
  if ( (UnDecorator::disableFlags & 0x4000) != 0 )
  {
    DName::getString((DName *)v39, String, 16);
    v26 = UnDecorator::m_pGetParameter;
    v27 = atol(String);
    v28 = ((__int64 (__fastcall *)(_QWORD))v26)(v27);
    if ( v28 )
    {
      DName::operator=(&v36, v28);
      goto LABEL_29;
    }
    DName::operator=(&v36, "`");
    v29 = DName::DName((DName *)v41, v18);
    DName::operator+(v29, v38, v39);
    v30 = v40;
  }
  else
  {
    DName::operator=(&v36, "`");
    v31 = DName::DName((DName *)v40, v18);
    DName::operator+(v31, v38, v39);
    v30 = v41;
  }
  v32 = DName::operator+(v38, v30, "'");
  DName::operator+=(&v36, v32);
LABEL_29:
  if ( a2 && *(_DWORD *)UnDecorator::pZNameList != 9 )
    Replicator::operator+=(UnDecorator::pZNameList, &v36);
  v34 = v36;
  *(_DWORD *)(a1 + 8) &= 0xFFFFF000;
  *(_QWORD *)a1 = v34;
  *(_DWORD *)(a1 + 8) |= v37 & 0xFFF;
  return a1;
}

```

## disassembly

```asm
0x180014bb0  mov     [rsp-8+arg_8], rbx
0x180014bb5  mov     [rsp-8+arg_10], rsi
0x180014bba  push    rbp
0x180014bbb  push    rdi
0x180014bbc  push    r14
0x180014bbe  lea     rbp, [rsp-47h]
0x180014bc3  sub     rsp, 90h
0x180014bca  mov     rax, cs:__security_cookie
0x180014bd1  xor     rax, rsp
0x180014bd4  mov     [rbp+57h+var_20], rax
0x180014bd8  mov     r8, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180014bdf  mov     rdi, rcx
0x180014be2  mov     r14b, dl
0x180014be5  movsx   rcx, byte ptr [r8]
0x180014be9  lea     eax, [rcx-30h]
0x180014bec  cmp     eax, 9
0x180014bef  ja      loc_180014CC3
0x180014bf5  inc     r8
0x180014bf8  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x180014bff  mov     r8, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pZNameList
0x180014c06  cmp     dword ptr [r8], 0FFFFFFFFh
0x180014c0a  jz      short loc_180014C25
0x180014c0c  cmp     eax, [r8]
0x180014c0f  jg      short loc_180014C25
0x180014c11  lfence
0x180014c14  mov     rax, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pZNameList
0x180014c1b  mov     r8, [rax+rcx*8-178h]
0x180014c23  jmp     short loc_180014C29
0x180014c25  add     r8, 68h ; 'h'
0x180014c29  mov     eax, [r8+8]
0x180014c2d  xor     eax, [rdi+8]
0x180014c30  and     eax, 0FFFFFFF0h
0x180014c33  xor     eax, [r8+8]
0x180014c37  mov     [rdi+8], eax
0x180014c3a  mov     ecx, eax
0x180014c3c  xor     ecx, [r8+8]
0x180014c40  and     ecx, 10h
0x180014c43  xor     ecx, eax
0x180014c45  mov     [rdi+8], ecx
0x180014c48  mov     eax, ecx
0x180014c4a  xor     eax, [r8+8]
0x180014c4e  and     eax, 20h
0x180014c51  xor     eax, ecx
0x180014c53  mov     [rdi+8], eax
0x180014c56  mov     ecx, eax
0x180014c58  xor     ecx, [r8+8]
0x180014c5c  and     ecx, 40h
0x180014c5f  xor     ecx, eax
0x180014c61  mov     [rdi+8], ecx
0x180014c64  mov     edx, ecx
0x180014c66  xor     edx, [r8+8]
0x180014c6a  and     edx, 80h
0x180014c70  xor     edx, ecx
0x180014c72  mov     [rdi+8], edx
0x180014c75  mov     rax, [r8]
0x180014c78  mov     [rdi], rax
0x180014c7b  mov     eax, edx
0x180014c7d  xor     eax, [r8+8]
0x180014c81  and     eax, 100h
0x180014c86  xor     eax, edx
0x180014c88  mov     [rdi+8], eax
0x180014c8b  mov     ecx, eax
0x180014c8d  xor     ecx, [r8+8]
0x180014c91  and     ecx, 200h
0x180014c97  xor     ecx, eax
0x180014c99  mov     [rdi+8], ecx
0x180014c9c  mov     edx, ecx
0x180014c9e  xor     edx, [r8+8]
0x180014ca2  and     edx, 400h
0x180014ca8  xor     edx, ecx
0x180014caa  mov     [rdi+8], edx
0x180014cad  mov     ecx, edx
0x180014caf  xor     ecx, [r8+8]
0x180014cb3  and     ecx, 800h
0x180014cb9  xor     ecx, edx
0x180014cbb  mov     [rdi+8], ecx
0x180014cbe  jmp     loc_180014ECF
0x180014cc3  and     [rbp+57h+var_78], 0FFFFF000h
0x180014cca  cmp     byte ptr [r8], 3Fh ; '?'
0x180014cce  mov     [rbp+57h+var_80], 0
0x180014cd6  jnz     short loc_180014D2C
0x180014cd8  xor     edx, edx
0x180014cda  lea     rcx, [rbp+57h+var_70]
0x180014cde  call    ?getTemplateName@UnDecorator@@CA?AVDName@@_N@Z; UnDecorator::getTemplateName(bool)
0x180014ce3  mov     rdx, rax
0x180014ce6  lea     rcx, [rbp+57h+var_80]
0x180014cea  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x180014cef  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x180014cf6  mov     al, [rcx]
0x180014cf8  inc     rcx
0x180014cfb  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx; char const * const UnDecorator::gName
0x180014d02  cmp     al, 40h ; '@'
0x180014d04  jz      loc_180014E9C
0x180014d0a  lea     rax, [rcx-1]
0x180014d0e  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x180014d15  lea     rcx, [rbp+57h+var_80]
0x180014d19  mov     al, [rax]
0x180014d1b  neg     al
0x180014d1d  sbb     edx, edx
0x180014d1f  add     edx, 2
0x180014d22  call    ??4DName@@QEAAAEAV0@W4DNameStatus@@@Z; DName::operator=(DNameStatus)
0x180014d27  jmp     loc_180014E9C
0x180014d2c  lea     rsi, aTemplateParame_0; "template-parameter-"
0x180014d33  mov     rcx, r8
0x180014d36  mov     rax, rsi
0x180014d39  mov     r9d, 12h
0x180014d3f  or      r10d, 0FFFFFFFFh
0x180014d43  mov     dl, [rcx]
0x180014d45  test    dl, dl
0x180014d47  jz      short loc_180014D58
0x180014d49  cmp     dl, [rax]
0x180014d4b  jnz     short loc_180014D58
0x180014d4d  inc     rcx
0x180014d50  inc     rax
0x180014d53  add     r9d, r10d
0x180014d56  jnz     short loc_180014D43
0x180014d58  movzx   ecx, byte ptr [rcx]
0x180014d5b  movzx   eax, byte ptr [rax]
0x180014d5e  cmp     ecx, eax
0x180014d60  jnz     short loc_180014D68
0x180014d62  add     r8, 13h
0x180014d66  jmp     short loc_180014DA2
0x180014d68  lea     rsi, aGenericType; "generic-type-"
0x180014d6f  mov     rcx, r8
0x180014d72  mov     rax, rsi
0x180014d75  mov     r9d, 0Ch
0x180014d7b  mov     dl, [rcx]
0x180014d7d  test    dl, dl
0x180014d7f  jz      short loc_180014D90
0x180014d81  cmp     dl, [rax]
0x180014d83  jnz     short loc_180014D90
0x180014d85  inc     rcx
0x180014d88  inc     rax
0x180014d8b  add     r9d, r10d
0x180014d8e  jnz     short loc_180014D7B
0x180014d90  movzx   ecx, byte ptr [rcx]
0x180014d93  movzx   eax, byte ptr [rax]
0x180014d96  cmp     ecx, eax
0x180014d98  jnz     loc_180014E7D
0x180014d9e  add     r8, 0Dh
0x180014da2  lea     rcx, [rbp+57h+var_60]
0x180014da6  mov     cs:?gName@UnDecorator@@0PEBDEB, r8; char const * const UnDecorator::gName
0x180014dad  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x180014db2  test    cs:?disableFlags@UnDecorator@@0KA, 4000h; ulong UnDecorator::disableFlags
0x180014dbc  jz      short loc_180014E2F
0x180014dbe  mov     r8d, 10h; int
0x180014dc4  lea     rdx, [rbp+57h+String]; char *
0x180014dc8  lea     rcx, [rbp+57h+var_60]; this
0x180014dcc  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x180014dd1  mov     rbx, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA; char * (*UnDecorator::m_pGetParameter)(long)
0x180014dd8  lea     rcx, [rbp+57h+String]; String
0x180014ddc  call    atol
0x180014de1  mov     ecx, eax
0x180014de3  mov     rax, rbx
0x180014de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014deb  lea     rcx, [rbp+57h+var_80]
0x180014def  test    rax, rax
0x180014df2  jz      short loc_180014E01
0x180014df4  mov     rdx, rax
0x180014df7  call    ??4DName@@QEAAAEAV0@PEBD@Z; DName::operator=(char const *)
0x180014dfc  jmp     loc_180014E9C
0x180014e01  lea     rdx, asc_180081CF8; "`"
0x180014e08  call    ??4DName@@QEAAAEAV0@PEBD@Z; DName::operator=(char const *)
0x180014e0d  mov     rdx, rsi; char *
0x180014e10  lea     rcx, [rbp+57h+var_40]; this
0x180014e14  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180014e19  lea     r8, [rbp+57h+var_60]
0x180014e1d  mov     rcx, rax
0x180014e20  lea     rdx, [rbp+57h+var_70]
0x180014e24  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180014e29  lea     rdx, [rbp+57h+var_50]
0x180014e2d  jmp     short loc_180014E5F
0x180014e2f  lea     rdx, asc_180081CF8; "`"
0x180014e36  lea     rcx, [rbp+57h+var_80]
0x180014e3a  call    ??4DName@@QEAAAEAV0@PEBD@Z; DName::operator=(char const *)
0x180014e3f  mov     rdx, rsi; char *
0x180014e42  lea     rcx, [rbp+57h+var_50]; this
0x180014e46  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x180014e4b  lea     r8, [rbp+57h+var_60]
0x180014e4f  mov     rcx, rax
0x180014e52  lea     rdx, [rbp+57h+var_70]
0x180014e56  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x180014e5b  lea     rdx, [rbp+57h+var_40]
0x180014e5f  lea     r8, asc_180081CFC; "'"
0x180014e66  lea     rcx, [rbp+57h+var_70]
0x180014e6a  call    ??HDName@@QEBA?AV0@PEBD@Z; DName::operator+(char const *)
0x180014e6f  mov     rdx, rax
0x180014e72  lea     rcx, [rbp+57h+var_80]
0x180014e76  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x180014e7b  jmp     short loc_180014E9C
0x180014e7d  mov     r8b, 40h ; '@'; char
0x180014e80  lea     rdx, ?gName@UnDecorator@@0PEBDEB; char **
0x180014e87  lea     rcx, [rbp+57h+var_50]; this
0x180014e8b  call    ??0DName@@QEAA@AEAPEBDD@Z; DName::DName(char const * &,char)
0x180014e90  mov     rdx, rax
0x180014e93  lea     rcx, [rbp+57h+var_80]
0x180014e97  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x180014e9c  test    r14b, r14b
0x180014e9f  jz      short loc_180014EB6
0x180014ea1  mov     rcx, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA; Replicator * UnDecorator::pZNameList
0x180014ea8  cmp     dword ptr [rcx], 9
0x180014eab  jz      short loc_180014EB6
0x180014ead  lea     rdx, [rbp+57h+var_80]
0x180014eb1  call    ??YReplicator@@QEAAAEAV0@AEBVDName@@@Z; Replicator::operator+=(DName const &)
0x180014eb6  mov     rax, [rbp+57h+var_80]
0x180014eba  and     dword ptr [rdi+8], 0FFFFF000h
0x180014ec1  mov     [rdi], rax
0x180014ec4  mov     eax, [rbp+57h+var_78]
0x180014ec7  and     eax, 0FFFh
0x180014ecc  or      [rdi+8], eax
0x180014ecf  mov     rax, rdi
0x180014ed2  mov     rcx, [rbp+57h+var_20]
0x180014ed6  xor     rcx, rsp; StackCookie
0x180014ed9  call    __security_check_cookie
0x180014ede  lea     r11, [rsp+0A0h+var_10]
0x180014ee6  mov     rbx, [r11+28h]
0x180014eea  mov     rsi, [r11+30h]
0x180014eee  mov     rsp, r11
0x180014ef1  pop     r14
0x180014ef3  pop     rdi
0x180014ef4  pop     rbp
0x180014ef5  retn
```
