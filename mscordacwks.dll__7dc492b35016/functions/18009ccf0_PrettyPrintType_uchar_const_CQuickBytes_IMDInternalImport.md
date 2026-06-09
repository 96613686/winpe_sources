# PrettyPrintType(uchar const *,CQuickBytes *,IMDInternalImport *)

- ea: `0x18009ccf0`
- end: `0x18009d70d`
- name: `?PrettyPrintType@@YAPEBEPEBEPEAVCQuickBytes@@PEAUIMDInternalImport@@@Z`
- size: `2589`
- prototype: `const unsigned __int8 *(const unsigned __int8 *, struct CQuickBytes *, struct IMDInternalImport *)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18009ca4c`
- `0x18009ccf0`
- `0x18009d710`

## callees

- `0x18000c968`
- `0x18000cdac`
- `0x1800210f0`
- `0x18002127c`
- `0x180040d24`
- `0x180081de0`
- `0x180082c58`
- `0x18009c818`
- `0x18009c874`
- `0x18009c8dc`
- `0x18009c920`
- `0x18009c9b0`
- `0x18009ca4c`
- `0x18009ccf0`
- `0x18009d710`
- `0x18009db50`
- `0x1800f0d20`
- `0x1800f3020`
- `0x180105e80`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18009d69e`
- `KERNEL32!HeapFree` at `0x18009d6d6`
- `KERNEL32!HeapFree` at `0x18009d69e`
- `KERNEL32!HeapFree` at `0x18009d6d6`
- `KERNEL32!GetProcessHeap` at `0x18009d689`
- `KERNEL32!GetProcessHeap` at `0x18009d6c1`
- `KERNEL32!GetProcessHeap` at `0x18009d689`
- `KERNEL32!GetProcessHeap` at `0x18009d6c1`

## string_xrefs

- `0x18009d5df`: `[ERROR! NIL TOKEN]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const unsigned __int8 *__fastcall PrettyPrintType(
        const unsigned __int8 *a1,
        struct CQuickBytes *a2,
        struct IMDInternalImport *a3)
{
  struct CQuickBytes *v4; // rsi
  unsigned int v6; // r15d
  const unsigned __int8 *v7; // rbx
  unsigned int v8; // r9d
  const char *v9; // rax
  const char *v10; // r12
  unsigned int v11; // r8d
  unsigned int v12; // edi
  unsigned int v13; // edi
  char *v14; // rdx
  const char *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r15
  void *v18; // rax
  unsigned __int64 *MethodTable; // rax
  MethodTable *v20; // rax
  unsigned int v21; // r8d
  MethodTable *v22; // r14
  unsigned __int64 *Module; // rax
  Module *v24; // rax
  struct IMDInternalImport *MDImport; // rbx
  unsigned int TypeDefRid_NoLogging; // eax
  const char *v27; // rdx
  MethodTable *v28; // rax
  unsigned __int64 *v29; // rax
  Module *v30; // rax
  struct IMDInternalImport *v31; // rbx
  unsigned int v32; // eax
  unsigned __int8 v33; // al
  const unsigned __int8 *v34; // rdi
  unsigned int v35; // r8d
  int v36; // ebx
  int v37; // eax
  int v38; // ebx
  char v39; // al
  const unsigned __int8 *v40; // rax
  const unsigned __int8 *v41; // rdi
  __int64 v42; // rbx
  int v43; // eax
  unsigned int v44; // ebx
  unsigned __int64 v45; // rax
  void *v46; // rsp
  unsigned int *v47; // r13
  unsigned int v48; // r15d
  const unsigned __int8 *v49; // rdi
  int v50; // eax
  int v51; // r15d
  unsigned int *v52; // rdx
  __int64 v53; // r8
  int v54; // ecx
  int v55; // eax
  int v56; // ecx
  unsigned int v57; // r14d
  int v58; // eax
  int v59; // r14d
  unsigned int *v60; // r12
  __int64 v61; // rsi
  unsigned int v62; // edx
  char v63; // al
  unsigned int v64; // ecx
  unsigned int v65; // r8d
  unsigned int v66; // r12d
  unsigned int v67; // r8d
  unsigned int v68; // edx
  unsigned int v69; // edx
  struct CQuickBytes *v70; // rcx
  const char *v71; // rax
  unsigned int v72; // r8d
  void *v73; // rbx
  HANDLE ProcessHeap; // rax
  void *v75; // rbx
  HANDLE v76; // rax
  unsigned int v78[2]; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v79[2]; // [rsp+48h] [rbp+8h] BYREF
  unsigned int *v80; // [rsp+50h] [rbp+10h]
  unsigned int *v81; // [rsp+58h] [rbp+18h] BYREF
  struct CQuickBytes *v82; // [rsp+60h] [rbp+20h] BYREF
  LPVOID v83; // [rsp+70h] [rbp+30h] BYREF
  __int64 v84; // [rsp+78h] [rbp+38h]
  __int64 v85; // [rsp+80h] [rbp+40h]
  LPVOID lpMem[68]; // [rsp+290h] [rbp+250h] BYREF
  char Buffer[64]; // [rsp+4B0h] [rbp+470h] BYREF

  v4 = a2;
  v82 = a2;
  v83 = 0;
  v84 = 0;
  v85 = 512;
  lpMem[0] = 0;
  lpMem[1] = 0;
  lpMem[2] = (LPVOID)512;
  v6 = -1;
  while ( 1 )
  {
    while ( 1 )
    {
      v7 = a1;
      v8 = *a1++;
      if ( v8 > 0x11 )
        break;
      if ( (_BYTE)v8 == 17 )
      {
        v15 = "valuetype ";
LABEL_153:
        appendStr(v4, v15, (unsigned int)a3);
        v79[0] = 0;
        if ( (int)CorSigUncompressData(a1, 0xFFu, v78, v79) >= 0 )
        {
          v6 = v79[0];
          v68 = v78[0];
        }
        else
        {
          v68 = 0;
        }
        v69 = *((_DWORD *)&g_tkCorEncodeToken + (v68 & 3)) | (v68 >> 2);
        a1 = &v7[v6 + 1];
        v70 = v4;
        if ( (v69 & 0xFFFFFF) != 0 )
        {
          PrettyPrintClass(v4, v69, a3);
          goto LABEL_164;
        }
        v14 = "[ERROR! NIL TOKEN]";
        goto LABEL_163;
      }
      if ( (unsigned __int8)v8 <= 8u )
      {
        if ( (_BYTE)v8 == 8 )
        {
          v14 = "int32";
          goto LABEL_162;
        }
        switch ( v8 )
        {
          case 0u:
            goto LABEL_160;
          case 1u:
            v14 = "void";
            break;
          case 2u:
            v14 = "bool";
            break;
          case 3u:
            v14 = "char";
            break;
          case 4u:
            v14 = "int8";
            break;
          case 5u:
            v14 = "uint8";
            break;
          case 6u:
            v14 = "int16";
            break;
          default:
            v14 = "uint16";
            break;
        }
        goto LABEL_162;
      }
      switch ( v8 )
      {
        case 9u:
          v14 = "uint32";
          goto LABEL_162;
        case 0xAu:
          v14 = "int64";
          goto LABEL_162;
        case 0xBu:
          v14 = "uint64";
          goto LABEL_162;
        case 0xCu:
          v14 = "float32";
          goto LABEL_162;
        case 0xDu:
          v14 = "float64";
          goto LABEL_162;
        case 0xEu:
          v14 = "string";
          goto LABEL_162;
        case 0xFu:
          v9 = "*";
          break;
        default:
          v9 = "&";
          break;
      }
LABEL_31:
      insertStr((struct CQuickBytes *)lpMem, v9);
      a1 = v7 + 1;
    }
    if ( (unsigned __int8)v8 > 0x41u )
    {
      if ( (_BYTE)v8 != 69 )
        goto LABEL_160;
      v9 = " pinned";
      goto LABEL_31;
    }
    if ( (_BYTE)v8 == 65 )
      goto LABEL_160;
    if ( (unsigned __int8)v8 <= 0x1Bu )
      break;
    if ( v8 == 28 )
    {
      v14 = "object";
      goto LABEL_162;
    }
    if ( v8 != 29 )
    {
      if ( v8 != 30 )
      {
        if ( v8 == 31 )
        {
          v10 = " modreq(";
          goto LABEL_24;
        }
        if ( v8 == 32 )
        {
          v10 = " modopt(";
LABEL_24:
          v78[0] = 0;
          if ( (int)CorSigUncompressData(a1, 0xFFu, v79, v78) >= 0 )
          {
            v6 = v78[0];
            v12 = v79[0];
          }
          else
          {
            v12 = 0;
          }
          v13 = *((_DWORD *)&g_tkCorEncodeToken + (v12 & 3)) | (v12 >> 2);
          v79[0] = v13;
          v84 = 0;
          appendStr((struct CQuickBytes *)&v83, v10, v11);
          PrettyPrintClass((struct CQuickBytes *)&v83, v13, a3);
          appendChar((struct CQuickBytes *)&v83, 41);
          v9 = asString((struct CQuickBytes *)&v83);
          v7 += v6;
          v6 = -1;
          goto LABEL_31;
        }
        if ( v8 != 33 )
          goto LABEL_160;
        v16 = *(_QWORD *)a1;
        a1 = v7 + 9;
        if ( (v16 & 2) != 0 )
        {
          v17 = v16 - 2;
          v18 = DacInstantiateTypeByAddressHelper(v16 - 2, 4u, 1, 1);
          MethodTable = (unsigned __int64 *)TypeDesc::GetMethodTable(v18, &v81);
          v20 = (MethodTable *)DacInstantiateTypeByAddressHelper(*MethodTable, 0x40u, 1, 1);
          v22 = v20;
          if ( v20 )
          {
            Module = (unsigned __int64 *)MethodTable::GetModule(v20, &v82);
            v24 = (Module *)DacInstantiateClassByVTable(*Module);
            MDImport = Module::GetMDImport(v24);
            TypeDefRid_NoLogging = MethodTable::GetTypeDefRid_NoLogging(v22);
            PrettyPrintClass(v4, TypeDefRid_NoLogging | 0x2000000, MDImport);
            if ( *(_BYTE *)DacInstantiateTypeByAddressHelper(v17, 4u, 1, 1) == 17 )
            {
              v27 = "_NativeValueType";
              goto LABEL_63;
            }
            goto LABEL_64;
          }
        }
        else
        {
          v28 = (MethodTable *)DacInstantiateTypeByAddressHelper(v16, 0x40u, 1, 1);
          v22 = v28;
          if ( v28 )
          {
            v29 = (unsigned __int64 *)MethodTable::GetModule(v28, &v81);
            v30 = (Module *)DacInstantiateClassByVTable(*v29);
            v31 = Module::GetMDImport(v30);
            v32 = MethodTable::GetTypeDefRid_NoLogging(v22);
            PrettyPrintClass(v4, v32 | 0x2000000, v31);
            goto LABEL_64;
          }
        }
        v27 = "(null)";
LABEL_63:
        appendStr(v4, v27, v21);
LABEL_64:
        sprintf_s(Buffer, 0x20u, " /* MT: 0x%p */", v22);
        v14 = Buffer;
        goto LABEL_162;
      }
      appendChar(v4, 33);
      appendChar(v4, 33);
      if ( *(char *)a1 < 0 )
      {
        v33 = *a1;
LABEL_149:
        a1 = v7 + 2;
        if ( (v33 & 0xC0) != 0x80 )
          a1 = v7 + 4;
      }
      goto LABEL_151;
    }
    insertStr((struct CQuickBytes *)lpMem, "[]");
  }
  if ( (_BYTE)v8 == 27 )
  {
    appendStr(v4, "method ", (unsigned int)a3);
    a1 = PrettyPrintSignature(a1, 0x7FFFu, "*", v4, a3, 0, 0);
    goto LABEL_164;
  }
  switch ( v8 )
  {
    case 0x12u:
      v15 = "class ";
      goto LABEL_153;
    case 0x13u:
      appendChar(v4, 33);
      if ( *(char *)a1 < 0 )
      {
        v33 = *a1;
        goto LABEL_149;
      }
LABEL_151:
      appendStrNum(v4);
      ++a1;
      goto LABEL_164;
    case 0x14u:
      v40 = PrettyPrintType(a1, v4, a3);
      v41 = v40;
      v42 = *v40;
      if ( (v42 & 0x80u) != 0LL )
      {
        v41 = v40 + 1;
        v43 = v40[1];
        if ( (v42 & 0xC0) == 0x80 )
        {
          v44 = (v42 & 0x3F) << 8;
        }
        else
        {
          v44 = (v41[1] << 8) | ((v43 | ((v42 & 0x1F) << 8)) << 16);
          v41 += 2;
          v43 = *v41;
        }
        v42 = v43 | v44;
      }
      a1 = v41 + 1;
      if ( !(_DWORD)v42 )
      {
        v14 = "[BAD: RANK == 0!]";
        goto LABEL_162;
      }
      v45 = 8 * v42 + 15;
      if ( v45 <= 8 * v42 )
        v45 = 0xFFFFFFFFFFFFFF0LL;
      v46 = alloca(v45 & 0xFFFFFFFFFFFFFFF0uLL);
      v47 = v78;
      v81 = v78;
      v80 = &v78[v42];
      memset(v78, 0, 8 * v42);
      v48 = *a1;
      v49 = a1 + 1;
      if ( (v48 & 0x80u) != 0 )
      {
        v50 = *v49;
        if ( (v48 & 0xC0) == 0x80 )
        {
          v51 = (v48 & 0x3F) << 8;
        }
        else
        {
          v51 = (v49[1] << 8) | ((v50 | ((v48 & 0x1F) << 8)) << 16);
          v49 += 2;
          v50 = *v49;
        }
        v48 = v50 | v51;
        ++v49;
      }
      if ( v48 )
      {
        v52 = &v78[v42];
        v53 = v48;
        do
        {
          v54 = *v49++;
          if ( (v54 & 0x80u) != 0 )
          {
            v55 = *v49;
            if ( (v54 & 0xC0) == 0x80 )
            {
              v56 = (v54 & 0x3F) << 8;
            }
            else
            {
              v56 = (v49[1] << 8) | ((v55 | ((v54 & 0x1F) << 8)) << 16);
              v49 += 2;
              v55 = *v49;
            }
            v54 = v55 | v56;
            ++v49;
          }
          *v52++ = v54;
          --v53;
        }
        while ( v53 );
      }
      v57 = *v49;
      a1 = v49 + 1;
      *(_QWORD *)v79 = a1;
      if ( (v57 & 0x80u) != 0 )
      {
        v58 = *a1;
        if ( (v57 & 0xC0) == 0x80 )
        {
          v59 = (v57 & 0x3F) << 8;
        }
        else
        {
          v59 = (a1[1] << 8) | ((v58 | ((v57 & 0x1F) << 8)) << 16);
          a1 += 2;
          v58 = *a1;
        }
        v57 = v58 | v59;
        *(_QWORD *)v79 = ++a1;
      }
      if ( v57 )
      {
        v60 = v78;
        v61 = v57;
        do
        {
          v79[0] = 0;
          if ( (int)CorSigUncompressData(a1, 0xFFu, v78, v79) >= 0 )
          {
            v62 = v79[0];
            if ( v79[0] != -1 )
            {
              v63 = v78[0];
              v64 = v78[0] >> 1;
              v78[0] >>= 1;
              if ( (v63 & 1) != 0 )
              {
                if ( v79[0] == 1 )
                {
                  v64 |= 0xFFFFFFC0;
                }
                else if ( v79[0] == 2 )
                {
                  v64 |= 0xFFFFE000;
                }
                else
                {
                  v64 |= 0xF0000000;
                }
                v78[0] = v64;
              }
              *v60 = v64;
            }
          }
          else
          {
            v78[0] = 0;
            v62 = -1;
          }
          a1 += v62;
          ++v60;
          --v61;
        }
        while ( v61 );
        *(_QWORD *)v79 = a1;
        v4 = v82;
        v47 = v81;
      }
      appendChar(v4, 91);
      if ( (_DWORD)v42 != 1 || v48 || v57 )
      {
        v66 = 0;
        v80 = (unsigned int *)((char *)v80 - (__int64)v47);
        do
        {
          if ( !*v47 && v66 < v48 || v66 < v57 && (appendStrNum(v4), appendStr(v4, "...", v67), v66 < v48) )
            appendStrNum(v4);
          if ( v66 < (int)v42 - 1 )
            appendChar(v4, 44);
          ++v66;
          ++v47;
        }
        while ( v66 < (unsigned int)v42 );
        a1 = *(const unsigned __int8 **)v79;
      }
      else
      {
        appendStr(v4, "...", v65);
      }
      appendChar(v4, 93);
      goto LABEL_164;
    case 0x15u:
      v34 = PrettyPrintType(a1, v4, a3);
      appendStr(v4, "<", v35);
      v36 = *v34;
      if ( (v36 & 0x80u) != 0 )
      {
        v37 = *++v34;
        if ( (v36 & 0xC0) == 0x80 )
        {
          v38 = (v36 & 0x3F) << 8;
        }
        else
        {
          v38 = (v34[1] << 8) | ((v37 | ((v36 & 0x1F) << 8)) << 16);
          v34 += 2;
          v37 = *v34;
        }
        v36 = v37 | v38;
      }
      a1 = v34 + 1;
      v39 = 0;
      while ( v36 )
      {
        --v36;
        if ( v39 )
          appendChar(v4, 44);
        a1 = PrettyPrintType(a1, v4, a3);
        v39 = 1;
      }
      v14 = ">";
LABEL_162:
      v70 = v4;
LABEL_163:
      appendStr(v70, v14, (unsigned int)a3);
      goto LABEL_164;
    case 0x16u:
      v14 = "typedref";
      goto LABEL_162;
    case 0x18u:
      v14 = "native int";
      goto LABEL_162;
    case 0x19u:
      v14 = "native uint";
      goto LABEL_162;
  }
LABEL_160:
  if ( (_BYTE)v8 )
  {
    sprintf_s(Buffer, 0x40u, "/* UNKNOWN TYPE (0x%X)*/", v8);
    v14 = Buffer;
    goto LABEL_162;
  }
LABEL_164:
  v71 = asString((struct CQuickBytes *)lpMem);
  appendStr(v4, v71, v72);
  v73 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v73);
    lpMem[0] = 0;
  }
  v75 = v83;
  if ( v83 )
  {
    v76 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v76 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v76;
    }
    HeapFree(v76, 0, v75);
    v83 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18009ccf0  push    rbp
0x18009ccf2  push    rsi
0x18009ccf3  push    rdi
0x18009ccf4  push    r12
0x18009ccf6  push    r13
0x18009ccf8  push    r14
0x18009ccfa  push    r15
0x18009ccfc  sub     rsp, 500h
0x18009cd03  lea     rbp, [rsp+40h]
0x18009cd08  mov     [rbp+4F0h+arg_18], rbx
0x18009cd0f  mov     rax, cs:__security_cookie
0x18009cd16  xor     rax, rbp
0x18009cd19  mov     [rbp+4F0h+var_40], rax
0x18009cd20  mov     r14, r8
0x18009cd23  mov     rsi, rdx
0x18009cd26  mov     [rbp+4F0h+var_4D0], rdx
0x18009cd2a  mov     rdi, rcx
0x18009cd2d  and     [rbp+4F0h+var_4C0], 0
0x18009cd32  and     [rbp+4F0h+var_4B8], 0
0x18009cd37  mov     eax, 200h
0x18009cd3c  mov     [rbp+4F0h+var_4B0], rax
0x18009cd40  and     [rbp+4F0h+lpMem], 0
0x18009cd48  and     [rbp+4F0h+var_298], 0
0x18009cd50  mov     [rbp+4F0h+var_290], rax
0x18009cd57  or      r15d, 0FFFFFFFFh
0x18009cd5b  lea     r13, ?g_tkCorEncodeToken@@3QBIB; uint const near * const g_tkCorEncodeToken
0x18009cd62  mov     rbx, rdi
0x18009cd65  movzx   r9d, byte ptr [rdi]
0x18009cd69  inc     rdi
0x18009cd6c  cmp     r9d, 11h
0x18009cd70  ja      short loc_18009CDE5
0x18009cd72  cmp     r9b, 11h
0x18009cd76  jz      loc_18009CFD4
0x18009cd7c  cmp     r9b, 8
0x18009cd80  jbe     loc_18009CF3B
0x18009cd86  mov     ecx, r9d
0x18009cd89  sub     ecx, 9
0x18009cd8c  jz      loc_18009CF2F
0x18009cd92  sub     ecx, 1
0x18009cd95  jz      loc_18009CF23
0x18009cd9b  sub     ecx, 1
0x18009cd9e  jz      loc_18009CF17
0x18009cda4  sub     ecx, 1
0x18009cda7  jz      loc_18009CF0B
0x18009cdad  sub     ecx, 1
0x18009cdb0  jz      loc_18009CEFF
0x18009cdb6  sub     ecx, 1
0x18009cdb9  jz      loc_18009CEF3
0x18009cdbf  sub     ecx, 1
0x18009cdc2  jz      short loc_18009CDD9
0x18009cdc4  cmp     ecx, 1
0x18009cdc7  jnz     loc_18009D62D
0x18009cdcd  lea     rax, asc_180141680; "&"
0x18009cdd4  jmp     loc_18009CEDB
0x18009cdd9  lea     rax, asc_180141628; "*"
0x18009cde0  jmp     loc_18009CEDB
0x18009cde5  cmp     r9b, 41h ; 'A'
0x18009cde9  ja      loc_18009CECA
0x18009cdef  jz      loc_18009D62D
0x18009cdf5  cmp     r9b, 1Bh
0x18009cdf9  jbe     loc_18009D15A
0x18009cdff  mov     ecx, r9d
0x18009ce02  sub     ecx, 1Ch
0x18009ce05  jz      loc_18009D14E
0x18009ce0b  sub     ecx, 1
0x18009ce0e  jz      loc_18009CEB2
0x18009ce14  sub     ecx, 1
0x18009ce17  jz      loc_18009D126
0x18009ce1d  sub     ecx, 1
0x18009ce20  jz      short loc_18009CE34
0x18009ce22  sub     ecx, 1
0x18009ce25  jnz     loc_18009CFE0
0x18009ce2b  lea     r12, aModopt; " modopt("
0x18009ce32  jmp     short loc_18009CE3B
0x18009ce34  lea     r12, aModreq; " modreq("
0x18009ce3b  and     [rbp+4F0h+var_4F0], 0
0x18009ce3f  lea     r9, [rbp+4F0h+var_4F0]; unsigned int *
0x18009ce43  lea     r8, [rbp+4F0h+var_4E8]; unsigned int *
0x18009ce47  mov     edx, 0FFh; unsigned int
0x18009ce4c  mov     rcx, rdi; unsigned __int8 *
0x18009ce4f  call    ?CorSigUncompressData@@YAJPEBEKPEAK1@Z; CorSigUncompressData(uchar const *,ulong,ulong *,ulong *)
0x18009ce54  test    eax, eax
0x18009ce56  jns     short loc_18009CE5C
0x18009ce58  xor     edi, edi
0x18009ce5a  jmp     short loc_18009CE63
0x18009ce5c  mov     r15d, [rbp+4F0h+var_4F0]
0x18009ce60  mov     edi, [rbp+4F0h+var_4E8]
0x18009ce63  mov     eax, edi
0x18009ce65  and     eax, 3
0x18009ce68  shr     edi, 2
0x18009ce6b  or      edi, [r13+rax*4+0]
0x18009ce70  mov     [rbp+4F0h+var_4E8], edi
0x18009ce73  and     [rbp+4F0h+var_4B8], 0
0x18009ce78  mov     rdx, r12; char *
0x18009ce7b  lea     rcx, [rbp+4F0h+var_4C0]; struct CQuickBytes *
0x18009ce7f  call    ?appendStr@@YAXPEAVCQuickBytes@@PEBDI@Z; appendStr(CQuickBytes *,char const *,uint)
0x18009ce84  mov     r8, r14; struct IMDInternalImport *
0x18009ce87  mov     edx, edi; unsigned int
0x18009ce89  lea     rcx, [rbp+4F0h+var_4C0]; struct CQuickBytes *
0x18009ce8d  call    ?PrettyPrintClass@@YAPEBDPEAVCQuickBytes@@IPEAUIMDInternalImport@@@Z; PrettyPrintClass(CQuickBytes *,uint,IMDInternalImport *)
0x18009ce92  mov     dl, 29h ; ')'; char
0x18009ce94  lea     rcx, [rbp+4F0h+var_4C0]; struct CQuickBytes *
0x18009ce98  call    ?appendChar@@YAXPEAVCQuickBytes@@D@Z; appendChar(CQuickBytes *,char)
0x18009ce9d  lea     rcx, [rbp+4F0h+var_4C0]; struct CQuickBytes *
0x18009cea1  call    ?asString@@YAPEADPEAVCQuickBytes@@@Z; asString(CQuickBytes *)
0x18009cea6  mov     ecx, r15d
0x18009cea9  add     rbx, rcx
0x18009ceac  or      r15d, 0FFFFFFFFh
0x18009ceb0  jmp     short loc_18009CEDB
0x18009ceb2  lea     rdx, asc_18014162C; "[]"
0x18009ceb9  lea     rcx, [rbp+4F0h+lpMem]; struct CQuickBytes *
0x18009cec0  call    ?insertStr@@YAXPEAVCQuickBytes@@PEBD@Z; insertStr(CQuickBytes *,char const *)
0x18009cec5  jmp     loc_18009CD62
0x18009ceca  cmp     r9b, 45h ; 'E'
0x18009cece  jnz     loc_18009D62D
0x18009ced4  lea     rax, aPinned_1; " pinned"
0x18009cedb  mov     rdx, rax; char *
0x18009cede  lea     rcx, [rbp+4F0h+lpMem]; struct CQuickBytes *
0x18009cee5  call    ?insertStr@@YAXPEAVCQuickBytes@@PEBD@Z; insertStr(CQuickBytes *,char const *)
0x18009ceea  lea     rdi, [rbx+1]
0x18009ceee  jmp     loc_18009CD62
0x18009cef3  lea     rdx, aString_1; "string"
0x18009cefa  jmp     loc_18009D651
0x18009ceff  lea     rdx, aFloat64; "float64"
0x18009cf06  jmp     loc_18009D651
0x18009cf0b  lea     rdx, aFloat32; "float32"
0x18009cf12  jmp     loc_18009D651
0x18009cf17  lea     rdx, aUint64; "uint64"
0x18009cf1e  jmp     loc_18009D651
0x18009cf23  lea     rdx, aInt64_0; "int64"
0x18009cf2a  jmp     loc_18009D651
0x18009cf2f  lea     rdx, aUint32_0; "uint32"
0x18009cf36  jmp     loc_18009D651
0x18009cf3b  jz      loc_18009CFC8
0x18009cf41  mov     ecx, r9d
0x18009cf44  test    r9d, r9d
0x18009cf47  jz      loc_18009D62D
0x18009cf4d  sub     ecx, 1
0x18009cf50  jz      short loc_18009CFBC
0x18009cf52  sub     ecx, 1
0x18009cf55  jz      short loc_18009CFB0
0x18009cf57  sub     ecx, 1
0x18009cf5a  jz      short loc_18009CFA4
0x18009cf5c  sub     ecx, 1
0x18009cf5f  jz      short loc_18009CF98
0x18009cf61  sub     ecx, 1
0x18009cf64  jz      short loc_18009CF8C
0x18009cf66  sub     ecx, 1
0x18009cf69  jz      short loc_18009CF80
0x18009cf6b  cmp     ecx, 1
0x18009cf6e  jnz     loc_18009D62D
0x18009cf74  lea     rdx, aUint16_0; "uint16"
0x18009cf7b  jmp     loc_18009D651
0x18009cf80  lea     rdx, aInt16; "int16"
0x18009cf87  jmp     loc_18009D651
0x18009cf8c  lea     rdx, aUint8; "uint8"
0x18009cf93  jmp     loc_18009D651
0x18009cf98  lea     rdx, aInt8; "int8"
0x18009cf9f  jmp     loc_18009D651
0x18009cfa4  lea     rdx, aChar_0; "char"
0x18009cfab  jmp     loc_18009D651
0x18009cfb0  lea     rdx, aBool; "bool"
0x18009cfb7  jmp     loc_18009D651
0x18009cfbc  lea     rdx, aVoid_0; "void"
0x18009cfc3  jmp     loc_18009D651
0x18009cfc8  lea     rdx, aInt32; "int32"
0x18009cfcf  jmp     loc_18009D651
0x18009cfd4  lea     rdx, aValuetype; "valuetype "
0x18009cfdb  jmp     loc_18009D58D
0x18009cfe0  cmp     ecx, 1
0x18009cfe3  jnz     loc_18009D62D
0x18009cfe9  mov     rcx, [rdi]; unsigned __int64
0x18009cfec  lea     rdi, [rbx+9]
0x18009cff0  mov     r9b, 1; bool
0x18009cff3  mov     r8b, r9b; bool
0x18009cff6  test    cl, 2
0x18009cff9  jz      loc_18009D09C
0x18009cfff  lea     r15, [rcx-2]
0x18009d003  mov     edx, 4; unsigned int
0x18009d008  mov     rcx, r15; unsigned __int64
0x18009d00b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18009d010  lea     rdx, [rbp+4F0h+var_4D8]
0x18009d014  mov     rcx, rax
0x18009d017  call    ?GetMethodTable@TypeDesc@@QEAA?AV?$__DPtr@VMethodTable@@@@XZ; TypeDesc::GetMethodTable(void)
0x18009d01c  mov     r9b, 1; bool
0x18009d01f  mov     r8b, r9b; bool
0x18009d022  mov     edx, 40h ; '@'; unsigned int
0x18009d027  mov     rcx, [rax]; unsigned __int64
0x18009d02a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18009d02f  mov     r14, rax
0x18009d032  test    rax, rax
0x18009d035  jz      loc_18009D0F0
0x18009d03b  lea     rdx, [rbp+4F0h+var_4D0]
0x18009d03f  mov     rcx, rax
0x18009d042  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x18009d047  mov     r8b, 1
0x18009d04a  mov     edx, 628h
0x18009d04f  mov     rcx, [rax]; unsigned __int64
0x18009d052  call    DacInstantiateClassByVTable
0x18009d057  mov     rcx, rax; this
0x18009d05a  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x18009d05f  mov     rbx, rax
0x18009d062  mov     rcx, r14; this
0x18009d065  call    ?GetTypeDefRid_NoLogging@MethodTable@@QEAAIXZ; MethodTable::GetTypeDefRid_NoLogging(void)
0x18009d06a  bts     eax, 19h
0x18009d06e  mov     r8, rbx; struct IMDInternalImport *
0x18009d071  mov     edx, eax; unsigned int
0x18009d073  mov     rcx, rsi; struct CQuickBytes *
0x18009d076  call    ?PrettyPrintClass@@YAPEBDPEAVCQuickBytes@@IPEAUIMDInternalImport@@@Z; PrettyPrintClass(CQuickBytes *,uint,IMDInternalImport *)
0x18009d07b  mov     r9b, 1; bool
0x18009d07e  mov     r8b, r9b; bool
0x18009d081  mov     edx, 4; unsigned int
0x18009d086  mov     rcx, r15; unsigned __int64
0x18009d089  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18009d08e  cmp     byte ptr [rax], 11h
0x18009d091  jnz     short loc_18009D0FF
0x18009d093  lea     rdx, aNativevaluetyp; "_NativeValueType"
0x18009d09a  jmp     short loc_18009D0F7
0x18009d09c  mov     edx, 40h ; '@'; unsigned int
0x18009d0a1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18009d0a6  mov     r14, rax
0x18009d0a9  test    rax, rax
0x18009d0ac  jz      short loc_18009D0F0
0x18009d0ae  lea     rdx, [rbp+4F0h+var_4D8]
0x18009d0b2  mov     rcx, rax
0x18009d0b5  call    ?GetModule@MethodTable@@QEAA?AV?$__VPtr@VModule@@@@XZ; MethodTable::GetModule(void)
0x18009d0ba  mov     r8b, 1
0x18009d0bd  mov     edx, 628h
0x18009d0c2  mov     rcx, [rax]; unsigned __int64
0x18009d0c5  call    DacInstantiateClassByVTable
0x18009d0ca  mov     rcx, rax; this
0x18009d0cd  call    ?GetMDImport@Module@@QEBAPEAUIMDInternalImport@@XZ; Module::GetMDImport(void)
0x18009d0d2  mov     rbx, rax
0x18009d0d5  mov     rcx, r14; this
0x18009d0d8  call    ?GetTypeDefRid_NoLogging@MethodTable@@QEAAIXZ; MethodTable::GetTypeDefRid_NoLogging(void)
0x18009d0dd  bts     eax, 19h
0x18009d0e1  mov     r8, rbx; struct IMDInternalImport *
0x18009d0e4  mov     edx, eax; unsigned int
0x18009d0e6  mov     rcx, rsi; struct CQuickBytes *
0x18009d0e9  call    ?PrettyPrintClass@@YAPEBDPEAVCQuickBytes@@IPEAUIMDInternalImport@@@Z; PrettyPrintClass(CQuickBytes *,uint,IMDInternalImport *)
0x18009d0ee  jmp     short loc_18009D0FF
0x18009d0f0  lea     rdx, aNull; "(null)"
0x18009d0f7  mov     rcx, rsi; struct CQuickBytes *
0x18009d0fa  call    ?appendStr@@YAXPEAVCQuickBytes@@PEBDI@Z; appendStr(CQuickBytes *,char const *,uint)
0x18009d0ff  mov     r9, r14
0x18009d102  lea     r8, aMt0xP; " /* MT: 0x%p */"
0x18009d109  mov     edx, 20h ; ' '; BufferCount
0x18009d10e  lea     rcx, [rbp+4F0h+Buffer]; Buffer
0x18009d115  call    sprintf_s
0x18009d11a  lea     rdx, [rbp+4F0h+Buffer]
0x18009d121  jmp     loc_18009D651
0x18009d126  mov     dl, 21h ; '!'; char
0x18009d128  mov     rcx, rsi; struct CQuickBytes *
0x18009d12b  call    ?appendChar@@YAXPEAVCQuickBytes@@D@Z; appendChar(CQuickBytes *,char)
0x18009d130  mov     dl, 21h ; '!'; char
0x18009d132  mov     rcx, rsi; struct CQuickBytes *
0x18009d135  call    ?appendChar@@YAXPEAVCQuickBytes@@D@Z; appendChar(CQuickBytes *,char)
0x18009d13a  movzx   ecx, byte ptr [rdi]
0x18009d13d  mov     edx, ecx
0x18009d13f  test    cl, cl
0x18009d141  jns     loc_18009D576
0x18009d147  mov     al, cl
0x18009d149  jmp     loc_18009D544
0x18009d14e  lea     rdx, aObject_0; "object"
0x18009d155  jmp     loc_18009D651
0x18009d15a  jz      loc_18009D5F2
0x18009d160  mov     ecx, r9d
0x18009d163  sub     ecx, 12h
0x18009d166  jz      loc_18009D586
0x18009d16c  sub     ecx, 1
0x18009d16f  jz      loc_18009D531
0x18009d175  sub     ecx, 1
0x18009d178  jz      loc_18009D24F
0x18009d17e  sub     ecx, 1
0x18009d181  jz      short loc_18009D1BA
0x18009d183  sub     ecx, 1
0x18009d186  jz      short loc_18009D1AE
0x18009d188  sub     ecx, 2
0x18009d18b  jz      short loc_18009D1A2
0x18009d18d  cmp     ecx, 1
0x18009d190  jnz     loc_18009D62D
0x18009d196  lea     rdx, aNativeUint; "native uint"
0x18009d19d  jmp     loc_18009D651
0x18009d1a2  lea     rdx, aNativeInt; "native int"
0x18009d1a9  jmp     loc_18009D651
0x18009d1ae  lea     rdx, aTypedref; "typedref"
0x18009d1b5  jmp     loc_18009D651
0x18009d1ba  mov     r8, r14; struct IMDInternalImport *
0x18009d1bd  mov     rdx, rsi; struct CQuickBytes *
0x18009d1c0  mov     rcx, rdi; unsigned __int8 *
0x18009d1c3  call    ?PrettyPrintType@@YAPEBEPEBEPEAVCQuickBytes@@PEAUIMDInternalImport@@@Z; PrettyPrintType(uchar const *,CQuickBytes *,IMDInternalImport *)
0x18009d1c8  mov     rdi, rax
0x18009d1cb  lea     rdx, asc_180141520; "<"
0x18009d1d2  mov     rcx, rsi; struct CQuickBytes *
0x18009d1d5  call    ?appendStr@@YAXPEAVCQuickBytes@@PEBDI@Z; appendStr(CQuickBytes *,char const *,uint)
0x18009d1da  movzx   ebx, byte ptr [rdi]
0x18009d1dd  test    bl, bl
0x18009d1df  jns     short loc_18009D214
0x18009d1e1  inc     rdi
0x18009d1e4  mov     al, bl
  ... truncated ...
```
