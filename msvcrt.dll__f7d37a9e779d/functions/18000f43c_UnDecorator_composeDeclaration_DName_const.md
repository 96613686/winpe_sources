# UnDecorator::composeDeclaration(DName const &)

- ea: `0x18000f43c`
- end: `0x180010116`
- name: `?composeDeclaration@UnDecorator@@CA?AVDName@@AEBV2@@Z`
- size: `3290`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18001152c`

## callees

- `0x18000e3d0`
- `0x18000e4a8`
- `0x18000e4f0`
- `0x18000e880`
- `0x18000ebe8`
- `0x18000ecf4`
- `0x18000edd4`
- `0x18000ef94`
- `0x18000f0f4`
- `0x18000f3a0`
- `0x18000f43c`
- `0x18001031c`
- `0x18001067c`
- `0x180010b98`
- `0x180010c90`
- `0x18001181c`
- `0x180011eec`
- `0x1800124dc`
- `0x180013454`
- `0x18001446c`
- `0x180014520`
- `0x180014840`
- `0x180014938`
- `0x180014f9c`

## string_xrefs

- `0x18000feed`: ``template static data member constructor helper'`
- `0x18000ff15`: ``template static data member destructor helper'`

## pseudocode

```c
__int64 __fastcall UnDecorator::composeDeclaration(__int64 a1, __int64 a2)
{
  BOOL v4; // r15d
  __int64 v5; // rdx
  int TypeEncoding; // edi
  __int64 v7; // r9
  _DWORD *v8; // r8
  __int64 v9; // rax
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  int v15; // eax
  int v16; // ecx
  int v17; // edx
  int v18; // r12d
  int v19; // r13d
  int v20; // r12d
  int v21; // ecx
  __int64 v22; // rbx
  DName *v23; // rax
  __int64 BasedType; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  DName *v30; // rax
  __int64 v31; // rax
  DName *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  BOOL v37; // eax
  DName *v38; // rax
  DName *v39; // rax
  BOOL v40; // ecx
  const char *v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 CallingConvention; // rax
  DName *v46; // rax
  __int64 ReturnType; // rbx
  DName *v48; // rax
  __int64 v49; // r8
  __int64 v50; // r9
  _DWORD *v51; // r14
  _DWORD *Memory; // rax
  __int64 v53; // rax
  int v54; // ecx
  DName *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  _BYTE *v66; // rdx
  _BYTE *v67; // rcx
  DName *v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 ArgumentTypes; // rbx
  DName *v72; // rax
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 ThrowTypes; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rbx
  __int64 v81; // rax
  BOOL v82; // eax
  int v83; // edx
  const char *v84; // rdx
  int v85; // edx
  DName *v86; // rax
  _BYTE *ExternalDataType; // rdx
  BOOL v88; // ecx
  BOOL v89; // eax
  DName *v90; // rax
  BOOL v91; // eax
  DName *v92; // rax
  DName *v93; // rax
  __int64 v95; // [rsp+30h] [rbp-D0h] BYREF
  int v96; // [rsp+38h] [rbp-C8h]
  _BYTE v97[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v98; // [rsp+50h] [rbp-B0h] BYREF
  int v99; // [rsp+58h] [rbp-A8h]
  __int64 v100; // [rsp+60h] [rbp-A0h] BYREF
  int v101; // [rsp+68h] [rbp-98h]
  _BYTE v102[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v103; // [rsp+80h] [rbp-80h] BYREF
  int v104; // [rsp+88h] [rbp-78h]
  __int64 v105; // [rsp+90h] [rbp-70h] BYREF
  int v106; // [rsp+98h] [rbp-68h]
  __int64 v107; // [rsp+A0h] [rbp-60h] BYREF
  int v108; // [rsp+A8h] [rbp-58h]
  __int64 v109; // [rsp+B0h] [rbp-50h] BYREF
  int v110; // [rsp+B8h] [rbp-48h]
  __int64 v111; // [rsp+C0h] [rbp-40h] BYREF
  int v112; // [rsp+C8h] [rbp-38h]
  _BYTE v113[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v114[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v115[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v116[80]; // [rsp+100h] [rbp+0h] BYREF
  int v117; // [rsp+168h] [rbp+68h]

  v96 &= 0xFFFFF000;
  v95 = 0;
  v4 = 1;
  TypeEncoding = UnDecorator::getTypeEncoding();
  if ( *(_QWORD *)a2 && (!(unsigned int)DName::status(a2) || (unsigned int)DName::status(a2) == 2) )
  {
    v8 = (_DWORD *)(a2 + 8);
    if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
    {
      v117 = 1;
      goto LABEL_8;
    }
  }
  else
  {
    v8 = (_DWORD *)(a2 + 8);
  }
  v117 = 0;
LABEL_8:
  if ( TypeEncoding != 0xFFFF )
  {
    if ( TypeEncoding == 65534 )
    {
      v9 = DName::DName(v97, 2);
      DName::operator+(v9, a1, a2);
      return a1;
    }
    if ( TypeEncoding == 65533 )
    {
      v10 = *v8 ^ (*(_DWORD *)(a1 + 8) ^ *v8) & 0xFFFFFFF0;
      *(_DWORD *)(a1 + 8) = v10;
      v11 = v10 ^ (*v8 ^ v10) & 0x10;
      *(_DWORD *)(a1 + 8) = v11;
      v12 = v11 ^ (*v8 ^ v11) & 0x20;
      *(_DWORD *)(a1 + 8) = v12;
      v13 = v12 ^ (*v8 ^ v12) & 0x40;
      *(_DWORD *)(a1 + 8) = v13;
      v14 = v13 ^ (*v8 ^ v13) & 0x80;
      *(_DWORD *)(a1 + 8) = v14;
      *(_QWORD *)a1 = *(_QWORD *)a2;
      v15 = v14 ^ (*v8 ^ v14) & 0x100;
      *(_DWORD *)(a1 + 8) = v15;
      v16 = v15 ^ (*v8 ^ v15) & 0x200;
      *(_DWORD *)(a1 + 8) = v16;
      v17 = v16 ^ (*v8 ^ v16) & 0x400;
      *(_DWORD *)(a1 + 8) = v17;
      *(_DWORD *)(a1 + 8) = v17 ^ (*v8 ^ v17) & 0x800;
      return a1;
    }
    if ( (TypeEncoding & 0x8000) != 0 )
    {
      v18 = 4096;
      v19 = TypeEncoding & 0x1800;
      if ( v19 == 2048 )
        v18 = 1024;
      v20 = TypeEncoding & v18;
      if ( !v20 || (v21 = TypeEncoding & 0x1B00, ((v21 - 4096) & 0xFFFFFCFF) != 0) || v21 == 4864 )
      {
        if ( (TypeEncoding & 0x4000) != 0 )
        {
          if ( (UnDecorator::disableFlags & 0xA) != 0 )
          {
            BasedType = UnDecorator::getBasedType(v97);
            DName::operator|=(&v95, BasedType);
          }
          else
          {
            v22 = UnDecorator::getBasedType(v97);
            v23 = DName::DName((DName *)&v100, 32);
            DName::operator+(v23, &v98, v22);
            DName::operator=(&v95, &v98);
          }
        }
        if ( v20 && v19 == 6144 )
        {
          LOBYTE(v8) = 123;
          v25 = DName::operator+(a2, v97, v8, v7);
          UnDecorator::getDimension(&v98, 0);
          v26 = DName::operator+(v25, &v100, &v98);
          DName::operator+=(&v95, v26);
          if ( *UnDecorator::gName )
          {
            if ( *UnDecorator::gName == 65 )
            {
              ++UnDecorator::gName;
              DName::DName((DName *)&v100, "{flat}");
LABEL_32:
              if ( (UnDecorator::disableFlags & 0x1000) == 0 )
              {
                v30 = DName::DName((DName *)v97, 44);
                DName::operator+(v30, &v98, &v100);
                v31 = DName::operator+(&v98, &v105, "}' ");
                DName::operator+=(&v95, v31);
              }
              DName::operator+=(&v95, "}'", v28, v29);
              UnDecorator::getCallingConvention(&v98);
              if ( (UnDecorator::disableFlags & 0x1012) == 0 )
              {
                v32 = DName::DName((DName *)v97, 32);
                DName::operator+(v32, &v100, &v98);
                LOBYTE(v33) = 32;
                v35 = DName::operator+(&v100, &v105, v33, v34);
                v36 = DName::operator+(v35, &v109, &v95);
                DName::operator=(&v95, v36);
              }
              goto LABEL_36;
            }
            v27 = 1;
          }
          else
          {
            v27 = 2;
          }
          DName::DName(&v100, v27);
          goto LABEL_32;
        }
        v111 = 0;
        v112 &= 0xFFFFF000;
        v110 &= 0xFFFFF000;
        v104 &= 0xFFFFF000;
        v106 &= 0xFFFFF000;
        v108 &= 0xFFFFF000;
        v109 = 0;
        v103 = 0;
        v105 = 0;
        v107 = 0;
        if ( !v20 )
        {
LABEL_63:
          if ( (TypeEncoding & 0x1800) == 0x800 && (TypeEncoding & 0x700) != 0x200 )
          {
            v101 &= 0xFFFFF000;
            v99 &= 0xFFFFF000;
            v100 = 0;
            v98 = 0;
            if ( (UnDecorator::disableFlags & 0x60) == 0x60 )
            {
              UnDecorator::getDataIndirectType(v97, &v100, 0, &v98, 1);
              DName::operator|=(&v107, v97);
            }
            else
            {
              UnDecorator::getDataIndirectType(v97, &v98, 0, &v100, 1);
              DName::operator=(&v107, v97);
            }
          }
          if ( (UnDecorator::disableFlags & 2) != 0 || (UnDecorator::disableFlags & 0x10) != 0 )
          {
            CallingConvention = UnDecorator::getCallingConvention(v97);
            DName::operator|=(&v95, CallingConvention);
          }
          else
          {
            v43 = UnDecorator::getCallingConvention(v97);
            v44 = DName::operator+(v43, &v98, &v95);
            DName::operator=(&v95, v44);
          }
          if ( *(_QWORD *)a2 && (((int)(*(_DWORD *)(a2 + 8) << 28) >> 28) & 0xFFFFFFFD) == 0 )
          {
            if ( !v95 || ((v96 << 28 >> 28) & 0xFFFFFFFD) != 0 || (UnDecorator::disableFlags & 0x1000) != 0 )
            {
              DName::operator=(&v95, a2);
            }
            else
            {
              v46 = DName::DName((DName *)&v98, 32);
              DName::operator+(v46, v97, a2);
              DName::operator+=(&v95, v97);
            }
          }
          v100 = 0;
          v101 &= 0xFFFFF000;
          if ( v117 )
          {
            ReturnType = UnDecorator::getReturnType(&v98, 0);
            v48 = DName::DName((DName *)v114, " ");
            DName::operator+(v48, v97, ReturnType);
            DName::operator+=(&v95, v97);
            if ( (UnDecorator::disableFlags & 0x1000) != 0 )
            {
              *(_DWORD *)(a1 + 8) &= 0xFFFFF000;
LABEL_150:
              *(_QWORD *)a1 = v95;
              *(_DWORD *)(a1 + 8) |= v96 & 0xFFF;
              return a1;
            }
            v51 = 0;
          }
          else
          {
            Memory = HeapManager::getMemory((HeapManager *)&qword_18009E1A0, 0x10u, 0);
            v51 = Memory;
            if ( Memory )
            {
              Memory[2] &= 0xFFFFF000;
              *(_QWORD *)Memory = 0;
            }
            else
            {
              v51 = 0;
            }
            v53 = UnDecorator::getReturnType(v114, v51);
            DName::operator=(&v100, v53);
          }
          v54 = 4096;
          if ( (TypeEncoding & 0x1800) == 0x800 )
            v54 = 1024;
          if ( (v54 & TypeEncoding) == 0 )
            goto LABEL_98;
          if ( (TypeEncoding & 0x1800) == 0x800 )
          {
            if ( (TypeEncoding & 0x700) == 0x600 )
            {
              v55 = DName::DName((DName *)v114, "`vtordispex{");
              DName::operator+(v55, v97, &v111);
              LOBYTE(v56) = 44;
              v58 = DName::operator+(v97, &v98, v56, v57);
              v59 = DName::operator+(v58, v116, &v109);
              LOBYTE(v60) = 44;
              v62 = DName::operator+(v59, v115, v60, v61);
              v63 = DName::operator+(v62, v113, &v103);
              v66 = v102;
              v67 = (_BYTE *)v63;
LABEL_95:
              LOBYTE(v64) = 44;
              v69 = DName::operator+(v67, v66, v64, v65);
              DName::operator+=(&v95, v69);
LABEL_97:
              v70 = DName::operator+(&v105, v102, "}' ");
              DName::operator+=(&v95, v70);
LABEL_98:
              ArgumentTypes = UnDecorator::getArgumentTypes(v102);
              v72 = DName::DName((DName *)v113, 40);
              DName::operator+(v72, v97, ArgumentTypes);
              LOBYTE(v73) = 41;
              v75 = DName::operator+(v97, v115, v73, v74);
              DName::operator+=(&v95, v75);
              if ( (TypeEncoding & 0x1800) == 0x800 && (TypeEncoding & 0x700) != 0x200 )
                DName::operator+=(&v95, &v107);
              if ( (UnDecorator::disableFlags & 0x100) != 0 )
              {
                ThrowTypes = UnDecorator::getThrowTypes(v102);
                DName::operator|=(&v95, ThrowTypes);
              }
              else
              {
                v76 = UnDecorator::getThrowTypes(v102);
                DName::operator+=(&v95, v76);
              }
              if ( (UnDecorator::disableFlags & 4) == 0 && v51 )
              {
                DName::operator=(v51, &v95);
                DName::operator=(&v95, &v100);
              }
LABEL_36:
              v37 = (TypeEncoding & 0x6000) == 0;
              if ( (TypeEncoding & 0x8000) != 0 )
                v37 = (TypeEncoding & 0x1800) == 2048;
              if ( !v37 )
                goto LABEL_142;
              if ( (UnDecorator::disableFlags & 0x200) == 0 )
              {
                if ( (TypeEncoding & 0x8000) != 0 )
                  v4 = (TypeEncoding & 0x700) == 512;
                if ( v4 )
                {
                  v38 = DName::DName((DName *)v102, "static ");
                  DName::operator+(v38, v97, &v95);
                  DName::operator=(&v95, v97);
                }
                if ( (TypeEncoding & 0x8000) != 0 && (TypeEncoding & 0x700) == 0x100
                  || (TypeEncoding & 0x400) != 0
                  && ((TypeEncoding & 0x700) == 0x500
                   || (TypeEncoding & 0x700) == 0x600
                   || (TypeEncoding & 0x700) == 0x400) )
                {
                  v39 = DName::DName((DName *)v102, "virtual ");
                  DName::operator+(v39, v97, &v95);
                  DName::operator=(&v95, v97);
                }
              }
              if ( (UnDecorator::disableFlags & 0x80u) != 0 )
                goto LABEL_142;
              v40 = (TypeEncoding & 0x1800) == 2048;
              if ( (TypeEncoding & 0x8000) != 0 )
                v40 = (TypeEncoding & 0xC0) == 64;
              if ( v40 )
              {
                v41 = "private: ";
              }
              else
              {
                v88 = (TypeEncoding & 0x1800) == 4096;
                if ( (TypeEncoding & 0x8000) != 0 )
                  v88 = (TypeEncoding & 0xC0) == 0x80;
                if ( v88 )
                {
                  v41 = "protected: ";
                }
                else
                {
                  v89 = (TypeEncoding & 0x1800) == 0;
                  if ( (TypeEncoding & 0x8000) != 0 )
                    v89 = (TypeEncoding & 0xC0) == 0;
                  if ( !v89 )
                    goto LABEL_142;
                  v41 = "public: ";
                }
              }
              v90 = DName::DName((DName *)v102, v41);
              DName::operator+(v90, v97, &v95);
              DName::operator=(&v95, v97);
LABEL_142:
              v91 = (TypeEncoding & 0x6000) == 0;
              if ( (TypeEncoding & 0x8000) != 0 )
                v91 = (TypeEncoding & 0x1800) == 2048;
              if ( ((v91 ? 1024 : 4096) & TypeEncoding) != 0 && (UnDecorator::disableFlags & 0x1000) == 0 )
              {
                v92 = DName::DName((DName *)v102, "[thunk]:");
                DName::operator+(v92, v97, &v95);
                DName::operator=(&v95, v97);
              }
              if ( (TypeEncoding & 0x10000) != 0 )
              {
                v93 = DName::DName((DName *)v102, "extern \"C\" ");
                DName::operator+(v93, v97, &v95);
                DName::operator=(&v95, v97);
              }
              goto LABEL_149;
            }
            if ( (TypeEncoding & 0x700) == 0x500 )
            {
              v68 = DName::DName((DName *)v102, "`vtordisp{");
              DName::operator+(v68, v97, &v103);
              v66 = v113;
              v67 = v97;
              goto LABEL_95;
            }
          }
          DName::operator+=(&v95, "`adjustor{", v49, v50);
          goto LABEL_97;
        }
        if ( v19 == 2048 )
        {
          if ( (TypeEncoding & 0x700) == 0x600 )
          {
            LOBYTE(v5) = 1;
            UnDecorator::getDimension(&v98, v5);
            DName::operator=(&v111, &v98);
            LOBYTE(v42) = 1;
            UnDecorator::getDimension(&v98, v42);
            DName::operator=(&v109, &v98);
LABEL_61:
            LOBYTE(v5) = 1;
            UnDecorator::getDimension(&v98, v5);
            DName::operator=(&v103, &v98);
            goto LABEL_62;
          }
          if ( (TypeEncoding & 0x700) == 0x500 )
            goto LABEL_61;
        }
LABEL_62:
        LOBYTE(v5) = 1;
        UnDecorator::getDimension(&v98, v5);
        DName::operator=(&v105, &v98);
        goto LABEL_63;
      }
    }
    DName::operator+=(&v95, a2);
    v79 = 31744;
    if ( (TypeEncoding & 0x8000) == 0 )
    {
      if ( (TypeEncoding & 0x7C00) == 0x6800 || (TypeEncoding & 0x7C00) == 0x7000 )
      {
        UnDecorator::getVfTableType(a1, &v95, v78, 31744);
        return a1;
      }
      if ( (TypeEncoding & 0x7C00) == 0x6000 )
      {
        LOBYTE(v78) = 123;
        v80 = DName::operator+(&v95, v102, v78, 31744);
        UnDecorator::getDimension(v97, 0);
        v81 = DName::operator+(v80, v113, v97);
        DName::operator+(v81, a1, "}'");
        return a1;
      }
    }
    if ( (TypeEncoding & 0xFC00) == 0x7C00 )
    {
      UnDecorator::getVdispMapType(a1, &v95, v78, 31744);
      return a1;
    }
    v82 = (TypeEncoding & 0x6000) == 0;
    if ( (TypeEncoding & 0x8000) != 0 )
      v82 = (TypeEncoding & 0x1800) == 2048;
    v83 = TypeEncoding & (v82 ? 1024 : 4096);
    if ( v83 )
    {
      v78 = TypeEncoding & 0x1B00;
      if ( (TypeEncoding & 0x8000) != 0 && (_DWORD)v78 == 4096 )
      {
        DName::operator+=(&v95, "`local static destructor helper'", v78, 31744);
LABEL_128:
        v85 = TypeEncoding & 0x1B00;
        if ( (TypeEncoding & 0x8000) != 0 && v85 == 4352 || (TypeEncoding & 0x8000) != 0 && v85 == 4608 )
          goto LABEL_130;
LABEL_132:
        ExternalDataType = (_BYTE *)UnDecorator::getExternalDataType(v102, &v95, v78, v79);
        goto LABEL_131;
      }
      if ( (TypeEncoding & 0x8000) != 0 && (_DWORD)v78 == 4352 )
      {
        v84 = "`template static data member constructor helper'";
LABEL_122:
        DName::operator+=(&v95, v84, v78, 31744);
LABEL_130:
        v86 = DName::DName((DName *)v102, " ");
        DName::operator+(v86, v97, &v95);
        ExternalDataType = v97;
LABEL_131:
        DName::operator=(&v95, ExternalDataType);
        goto LABEL_36;
      }
      if ( (TypeEncoding & 0x8000) != 0 && (_DWORD)v78 == 4608 )
      {
        v84 = "`template static data member destructor helper'";
        goto LABEL_122;
      }
    }
    if ( (TypeEncoding & 0x8000) == 0 && (TypeEncoding & 0x7C00) == 0x7800 )
    {
LABEL_149:
      *(_DWORD *)(a1 + 8) &= 0xFFFFF000;
      goto LABEL_150;
    }
    if ( !v83 )
      goto LABEL_132;
    goto LABEL_128;
  }
  DName::DName(a1, 1);
  return a1;
}

```

## disassembly

```asm
0x18000f43c  push    rbp
0x18000f43e  push    rbx
0x18000f43f  push    rsi
0x18000f440  push    rdi
0x18000f441  push    r12
0x18000f443  push    r13
0x18000f445  push    r14
0x18000f447  push    r15
0x18000f449  lea     rbp, [rsp-18h]
0x18000f44e  sub     rsp, 118h
0x18000f455  and     [rsp+150h+var_118], 0FFFFF000h
0x18000f45d  xor     ebx, ebx
0x18000f45f  mov     [rsp+150h+var_120], rbx
0x18000f464  mov     r14, rdx
0x18000f467  mov     rsi, rcx
0x18000f46a  call    ?getTypeEncoding@UnDecorator@@CAHXZ; UnDecorator::getTypeEncoding(void)
0x18000f46f  lea     r15d, [rbx+1]
0x18000f473  mov     edi, eax
0x18000f475  cmp     [r14], rbx
0x18000f478  jz      short loc_18000F4A3
0x18000f47a  mov     rcx, r14
0x18000f47d  call    ?status@DName@@QEBA?AW4DNameStatus@@XZ; DName::status(void)
0x18000f482  test    eax, eax
0x18000f484  jz      short loc_18000F493
0x18000f486  mov     rcx, r14
0x18000f489  call    ?status@DName@@QEBA?AW4DNameStatus@@XZ; DName::status(void)
0x18000f48e  cmp     eax, 2
0x18000f491  jnz     short loc_18000F4A3
0x18000f493  lea     r8, [r14+8]
0x18000f497  test    byte ptr [r8], 20h
0x18000f49b  jz      short loc_18000F4A7
0x18000f49d  mov     [rbp+50h+arg_8], r15d
0x18000f4a1  jmp     short loc_18000F4AA
0x18000f4a3  lea     r8, [r14+8]
0x18000f4a7  mov     [rbp+50h+arg_8], ebx
0x18000f4aa  cmp     edi, 0FFFFh
0x18000f4b0  jnz     short loc_18000F4C2
0x18000f4b2  mov     edx, r15d
0x18000f4b5  mov     rcx, rsi
0x18000f4b8  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x18000f4bd  jmp     loc_1800100FF
0x18000f4c2  cmp     edi, 0FFFEh
0x18000f4c8  jnz     short loc_18000F4EC
0x18000f4ca  mov     edx, 2
0x18000f4cf  lea     rcx, [rsp+150h+var_110]
0x18000f4d4  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x18000f4d9  mov     r8, r14
0x18000f4dc  mov     rdx, rsi
0x18000f4df  mov     rcx, rax
0x18000f4e2  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f4e7  jmp     loc_1800100FF
0x18000f4ec  cmp     edi, 0FFFDh
0x18000f4f2  jnz     loc_18000F58E
0x18000f4f8  mov     eax, [r8]
0x18000f4fb  mov     r13d, 400h
0x18000f501  xor     eax, [rsi+8]
0x18000f504  mov     r12d, 800h
0x18000f50a  and     eax, 0FFFFFFF0h
0x18000f50d  xor     eax, [r8]
0x18000f510  mov     [rsi+8], eax
0x18000f513  mov     ecx, eax
0x18000f515  xor     ecx, [r8]
0x18000f518  and     ecx, 10h
0x18000f51b  xor     ecx, eax
0x18000f51d  mov     [rsi+8], ecx
0x18000f520  mov     eax, ecx
0x18000f522  xor     eax, [r8]
0x18000f525  and     eax, 20h
0x18000f528  xor     eax, ecx
0x18000f52a  mov     [rsi+8], eax
0x18000f52d  mov     ecx, eax
0x18000f52f  xor     ecx, [r8]
0x18000f532  and     ecx, 40h
0x18000f535  xor     ecx, eax
0x18000f537  mov     [rsi+8], ecx
0x18000f53a  mov     edx, ecx
0x18000f53c  xor     edx, [r8]
0x18000f53f  and     edx, 80h
0x18000f545  xor     edx, ecx
0x18000f547  mov     [rsi+8], edx
0x18000f54a  mov     rax, [r14]
0x18000f54d  mov     [rsi], rax
0x18000f550  mov     eax, edx
0x18000f552  xor     eax, [r8]
0x18000f555  and     eax, 100h
0x18000f55a  xor     eax, edx
0x18000f55c  mov     [rsi+8], eax
0x18000f55f  mov     ecx, eax
0x18000f561  xor     ecx, [r8]
0x18000f564  and     ecx, 200h
0x18000f56a  xor     ecx, eax
0x18000f56c  mov     [rsi+8], ecx
0x18000f56f  mov     edx, ecx
0x18000f571  xor     edx, [r8]
0x18000f574  and     edx, r13d
0x18000f577  xor     edx, ecx
0x18000f579  mov     [rsi+8], edx
0x18000f57c  mov     eax, edx
0x18000f57e  xor     eax, [r8]
0x18000f581  and     eax, r12d
0x18000f584  xor     eax, edx
0x18000f586  mov     [rsi+8], eax
0x18000f589  jmp     loc_1800100FF
0x18000f58e  mov     ebx, edi
0x18000f590  mov     r13d, 8000h
0x18000f596  mov     eax, 400h
0x18000f59b  and     ebx, r13d
0x18000f59e  jz      loc_18000FDA7
0x18000f5a4  mov     r13d, edi
0x18000f5a7  mov     r12d, 1000h
0x18000f5ad  and     r13d, 1800h
0x18000f5b4  cmp     r13d, 800h
0x18000f5bb  cmovz   r12d, eax
0x18000f5bf  and     r12d, edi
0x18000f5c2  jz      short loc_18000F5E5
0x18000f5c4  mov     ecx, edi
0x18000f5c6  and     ecx, 1B00h
0x18000f5cc  lea     eax, [rcx-1000h]
0x18000f5d2  test    eax, 0FFFFFCFFh
0x18000f5d7  jnz     short loc_18000F5E5
0x18000f5d9  cmp     ecx, 1300h
0x18000f5df  jnz     loc_18000FDA1
0x18000f5e5  bt      edi, 0Eh
0x18000f5e9  jnb     short loc_18000F640
0x18000f5eb  test    byte ptr cs:?disableFlags@UnDecorator@@0KA, 0Ah; ulong UnDecorator::disableFlags
0x18000f5f2  lea     rcx, [rsp+150h+var_110]
0x18000f5f7  jnz     short loc_18000F62E
0x18000f5f9  call    ?getBasedType@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getBasedType(void)
0x18000f5fe  mov     dl, 20h ; ' '; char
0x18000f600  lea     rcx, [rsp+150h+var_F0]; this
0x18000f605  mov     rbx, rax
0x18000f608  call    ??0DName@@QEAA@D@Z; DName::DName(char)
0x18000f60d  mov     r8, rbx
0x18000f610  lea     rdx, [rsp+150h+var_100]
0x18000f615  mov     rcx, rax
0x18000f618  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f61d  lea     rdx, [rsp+150h+var_100]
0x18000f622  lea     rcx, [rsp+150h+var_120]
0x18000f627  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18000f62c  jmp     short loc_18000F640
0x18000f62e  call    ?getBasedType@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getBasedType(void)
0x18000f633  mov     rdx, rax
0x18000f636  lea     rcx, [rsp+150h+var_120]
0x18000f63b  call    ??_5DName@@QEAAAEAV0@AEBV0@@Z; DName::operator|=(DName const &)
0x18000f640  xor     ebx, ebx
0x18000f642  test    r12d, r12d
0x18000f645  jz      loc_18000F8DD
0x18000f64b  cmp     r13d, 1800h
0x18000f652  jnz     loc_18000F8DD
0x18000f658  mov     r8b, 7Bh ; '{'
0x18000f65b  lea     rdx, [rsp+150h+var_110]
0x18000f660  mov     rcx, r14
0x18000f663  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18000f668  xor     edx, edx
0x18000f66a  lea     rcx, [rsp+150h+var_100]
0x18000f66f  mov     rbx, rax
0x18000f672  call    ?getDimension@UnDecorator@@CA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x18000f677  lea     r8, [rsp+150h+var_100]
0x18000f67c  mov     rcx, rbx
0x18000f67f  lea     rdx, [rsp+150h+var_F0]
0x18000f684  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f689  mov     rdx, rax
0x18000f68c  lea     rcx, [rsp+150h+var_120]
0x18000f691  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18000f696  mov     rax, cs:?gName@UnDecorator@@0PEBDEB; char const * const UnDecorator::gName
0x18000f69d  lea     rcx, [rsp+150h+var_F0]; this
0x18000f6a2  cmp     byte ptr [rax], 0
0x18000f6a5  jz      short loc_18000F6C9
0x18000f6a7  cmp     byte ptr [rax], 41h ; 'A'
0x18000f6aa  jz      short loc_18000F6B1
0x18000f6ac  mov     edx, r15d
0x18000f6af  jmp     short loc_18000F6CE
0x18000f6b1  add     rax, r15
0x18000f6b4  lea     rdx, aFlat; "{flat}"
0x18000f6bb  mov     cs:?gName@UnDecorator@@0PEBDEB, rax; char const * const UnDecorator::gName
0x18000f6c2  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x18000f6c7  jmp     short loc_18000F6D3
0x18000f6c9  mov     edx, 2
0x18000f6ce  call    ??0DName@@QEAA@W4DNameStatus@@@Z; DName::DName(DNameStatus)
0x18000f6d3  test    cs:?disableFlags@UnDecorator@@0KA, 1000h; ulong UnDecorator::disableFlags
0x18000f6dd  jnz     short loc_18000F71F
0x18000f6df  mov     dl, 2Ch ; ','; char
0x18000f6e1  lea     rcx, [rsp+150h+var_110]; this
0x18000f6e6  call    ??0DName@@QEAA@D@Z; DName::DName(char)
0x18000f6eb  lea     r8, [rsp+150h+var_F0]
0x18000f6f0  mov     rcx, rax
0x18000f6f3  lea     rdx, [rsp+150h+var_100]
0x18000f6f8  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f6fd  lea     r8, asc_180081D64; "}' "
0x18000f704  lea     rdx, [rbp+50h+var_C0]
0x18000f708  lea     rcx, [rsp+150h+var_100]
0x18000f70d  call    ??HDName@@QEBA?AV0@PEBD@Z; DName::operator+(char const *)
0x18000f712  mov     rdx, rax
0x18000f715  lea     rcx, [rsp+150h+var_120]
0x18000f71a  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18000f71f  lea     rdx, asc_180081D68; "}'"
0x18000f726  lea     rcx, [rsp+150h+var_120]
0x18000f72b  call    ??YDName@@QEAAAEAV0@PEBD@Z; DName::operator+=(char const *)
0x18000f730  lea     rcx, [rsp+150h+var_100]
0x18000f735  call    ?getCallingConvention@UnDecorator@@CA?AVDName@@XZ; UnDecorator::getCallingConvention(void)
0x18000f73a  test    cs:?disableFlags@UnDecorator@@0KA, 1012h; ulong UnDecorator::disableFlags
0x18000f744  jnz     short loc_18000F793
0x18000f746  mov     dl, 20h ; ' '; char
0x18000f748  lea     rcx, [rsp+150h+var_110]; this
0x18000f74d  call    ??0DName@@QEAA@D@Z; DName::DName(char)
0x18000f752  lea     r8, [rsp+150h+var_100]
0x18000f757  mov     rcx, rax
0x18000f75a  lea     rdx, [rsp+150h+var_F0]
0x18000f75f  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f764  mov     r8b, 20h ; ' '
0x18000f767  lea     rdx, [rbp+50h+var_C0]
0x18000f76b  lea     rcx, [rsp+150h+var_F0]
0x18000f770  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18000f775  lea     r8, [rsp+150h+var_120]
0x18000f77a  mov     rcx, rax
0x18000f77d  lea     rdx, [rbp+50h+var_A0]
0x18000f781  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f786  mov     rdx, rax
0x18000f789  lea     rcx, [rsp+150h+var_120]
0x18000f78e  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18000f793  mov     r12d, 800h
0x18000f799  mov     r13d, 400h
0x18000f79f  xor     ecx, ecx
0x18000f7a1  mov     eax, edi
0x18000f7a3  and     eax, 1800h
0x18000f7a8  cmp     eax, r12d
0x18000f7ab  mov     eax, 0
0x18000f7b0  setz    cl
0x18000f7b3  test    edi, 6000h
0x18000f7b9  setz    al
0x18000f7bc  bt      edi, 0Fh
0x18000f7c0  cmovb   eax, ecx
0x18000f7c3  test    eax, eax
0x18000f7c5  jz      loc_18001003A
0x18000f7cb  test    cs:?disableFlags@UnDecorator@@0KA, 200h; ulong UnDecorator::disableFlags
0x18000f7d5  jnz     loc_18000F897
0x18000f7db  xor     eax, eax
0x18000f7dd  mov     ebx, edi
0x18000f7df  mov     edx, 700h
0x18000f7e4  and     ebx, edx
0x18000f7e6  cmp     ebx, 200h
0x18000f7ec  setz    al
0x18000f7ef  bt      edi, 0Fh
0x18000f7f3  cmovb   r15d, eax
0x18000f7f7  test    r15d, r15d
0x18000f7fa  jz      short loc_18000F833
0x18000f7fc  lea     rdx, aStatic; "static "
0x18000f803  lea     rcx, [rsp+150h+var_E0]; this
0x18000f808  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x18000f80d  lea     r8, [rsp+150h+var_120]
0x18000f812  mov     rcx, rax
0x18000f815  lea     rdx, [rsp+150h+var_110]
0x18000f81a  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f81f  lea     rdx, [rsp+150h+var_110]
0x18000f824  lea     rcx, [rsp+150h+var_120]
0x18000f829  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18000f82e  mov     edx, 700h
0x18000f833  bt      edi, 0Fh
0x18000f837  jnb     short loc_18000F841
0x18000f839  cmp     ebx, 100h
0x18000f83f  jz      short loc_18000F865
0x18000f841  test    r13d, edi
0x18000f844  jz      short loc_18000F897
0x18000f846  mov     eax, edi
0x18000f848  and     eax, edx
0x18000f84a  cmp     eax, 500h
0x18000f84f  jz      short loc_18000F865
0x18000f851  mov     eax, edi
0x18000f853  and     eax, edx
0x18000f855  cmp     eax, 600h
0x18000f85a  jz      short loc_18000F865
0x18000f85c  mov     eax, edi
0x18000f85e  and     eax, edx
0x18000f860  cmp     eax, r13d
0x18000f863  jnz     short loc_18000F897
0x18000f865  lea     rdx, aVirtual; "virtual "
0x18000f86c  lea     rcx, [rsp+150h+var_E0]; this
0x18000f871  call    ??0DName@@QEAA@PEBD@Z; DName::DName(char const *)
0x18000f876  lea     r8, [rsp+150h+var_120]
0x18000f87b  mov     rcx, rax
0x18000f87e  lea     rdx, [rsp+150h+var_110]
0x18000f883  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18000f888  lea     rdx, [rsp+150h+var_110]
0x18000f88d  lea     rcx, [rsp+150h+var_120]
0x18000f892  call    ??4DName@@QEAAAEAV0@AEBV0@@Z; DName::operator=(DName const &)
0x18000f897  test    byte ptr cs:?disableFlags@UnDecorator@@0KA, 80h; ulong UnDecorator::disableFlags
0x18000f89e  jnz     loc_18001003A
0x18000f8a4  xor     edx, edx
0x18000f8a6  mov     eax, edi
0x18000f8a8  mov     r9b, 0C0h
0x18000f8ab  and     al, r9b
0x18000f8ae  cmp     al, 40h ; '@'
0x18000f8b0  mov     eax, edi
0x18000f8b2  setz    dl
0x18000f8b5  xor     ecx, ecx
0x18000f8b7  and     eax, 1800h
0x18000f8bc  cmp     eax, r12d
0x18000f8bf  setz    cl
0x18000f8c2  bt      edi, 0Fh
0x18000f8c6  cmovb   ecx, edx
  ... truncated ...
```
