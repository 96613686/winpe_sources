# DeclFactory::EndChildren(IXMLNodeSource *,int,_XML_NODE_INFO *)

- ea: `0x1800d6260`
- end: `0x1800d6b8f`
- name: `?EndChildren@DeclFactory@@UEAAJPEAUIXMLNodeSource@@HPEAU_XML_NODE_INFO@@@Z`
- size: `2351`
- prototype: `int(DeclFactory *__hidden this, struct IXMLNodeSource *, int, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x1800108cc`
- `0x180012000`
- `0x18002ff10`
- `0x18003b4fc`
- `0x18004aa64`
- `0x18004dea4`
- `0x180064034`
- `0x1800d5854`
- `0x1800d6260`
- `0x1800d70d8`
- `0x1800d7320`
- `0x1800d7df8`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800d6ad4`
- `msvcrt!_resetstkoflw` at `0x1800d6ad4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d6b27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d6b27`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d6ac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d6b53`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d6ac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d6b53`

## pseudocode

```c
__int64 __fastcall DeclFactory::EndChildren(
        DeclFactory *this,
        struct IXMLNodeSource *a2,
        __int64 a3,
        struct _XML_NODE_INFO *a4)
{
  int v6; // esi
  ContentFactory *v7; // rcx
  int v8; // eax
  __int64 v9; // rbx
  void *v10; // rax
  _DWORD *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r10
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // r9
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r15
  struct String *v25; // r12
  int i; // r14d
  __int64 v27; // rbx
  struct String *v28; // r13
  int DataType; // eax
  const struct String *const near *v30; // r10
  __int64 v31; // rax
  const struct String *const near *v32; // rcx
  __int64 v33; // rdx
  int v34; // r9d
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // rax
  char v38; // al
  __int64 v39; // rax
  int v40; // ecx
  struct Name *v41; // rax
  __int64 v42; // rbx
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r9
  __int64 v46; // r10
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // rdx
  bool v50; // zf
  __int64 (__fastcall *v51)(__int64, __int64, __int64, const OLECHAR *, _DWORD); // rax
  __int64 v52; // rcx
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, _QWORD, _QWORD, __int64, int, __int64, int, __int64, int); // r14
  int v55; // esi
  __int64 v56; // rcx
  __int64 v57; // r10
  __int64 v58; // rcx
  __int64 v59; // rax
  int v60; // r8d
  __int64 v61; // rdx
  __int64 v62; // rax
  int v63; // ecx
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // rax
  int v67; // r10d
  __int64 v68; // r8
  __int64 v69; // rax
  int v70; // edx
  __int64 v71; // r9
  struct String *v72; // r10
  __int64 v73; // rcx
  struct String *v74; // rdx
  __int64 v75; // rax
  int v76; // ecx
  __int64 v77; // r9
  _BYTE *v78; // rbx
  struct XMLParser *Parser; // rbx
  __int64 v80; // rcx
  __int64 v81; // rcx
  struct String *v83; // [rsp+20h] [rbp-C8h]
  struct String *v84; // [rsp+28h] [rbp-C0h]
  struct String *v85; // [rsp+68h] [rbp-80h] BYREF
  _QWORD v86[2]; // [rsp+70h] [rbp-78h] BYREF
  int v87; // [rsp+80h] [rbp-68h]
  int v88; // [rsp+84h] [rbp-64h]
  __int64 v89; // [rsp+88h] [rbp-60h]
  int v90; // [rsp+90h] [rbp-58h]
  int v91; // [rsp+94h] [rbp-54h]
  __int64 v92; // [rsp+98h] [rbp-50h]
  int v93; // [rsp+A0h] [rbp-48h]
  int v94; // [rsp+A4h] [rbp-44h]
  __int64 v95; // [rsp+A8h] [rbp-40h]
  int v96; // [rsp+B0h] [rbp-38h]
  int v97; // [rsp+B4h] [rbp-34h]

  v6 = 0;
  v85 = 0;
  v7 = (ContentFactory *)(unsigned int)(*((_DWORD *)a4 + 1) - 5);
  if ( *((_DWORD *)a4 + 1) != 5 )
  {
    if ( *((_DWORD *)a4 + 1) == 7 )
    {
      if ( *((_DWORD *)this + 40) == 7 )
      {
        DeclFactory::getEntityName(
          (DeclFactory *)(unsigned int)(*((_DWORD *)a4 + 1) - 7),
          *((struct Entity **)this + 16),
          &v85);
        v44 = *((_QWORD *)this + 16);
        v45 = *(_QWORD *)(v44 + 56);
        if ( v45 )
        {
          v46 = *((_QWORD *)this + 11);
          if ( v46 )
          {
            v47 = *(_DWORD *)(v44 + 96) >> 5;
            v48 = *((unsigned int *)v85 + 4);
            v49 = *((_QWORD *)v85 + 3);
            v50 = (v47 & 1) == 0;
            v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64, const OLECHAR *, _DWORD))(*(_QWORD *)v46 + 40LL);
            if ( v50 )
            {
              v6 = v51(v46, v49, v48, *(const OLECHAR **)(v45 + 24), *(_DWORD *)(v45 + 16));
              if ( v6 < 0 )
                return (unsigned int)v6;
            }
            else
            {
              v6 = v51(v46, v49, v48, &word_18012A048, 0);
              if ( v6 < 0 )
                return (unsigned int)v6;
            }
          }
        }
        else
        {
          v52 = *(_QWORD *)(v44 + 72);
          if ( v52 )
          {
            v53 = *((_QWORD *)this + 9);
            if ( v53 )
            {
              v54 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, __int64, int, __int64, int))(*(_QWORD *)v53 + 32LL);
              v55 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v52 + 40) + 88LL))(*(_QWORD *)(v52 + 40))
                              + 16);
              v56 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 16) + 72LL) + 40LL);
              v57 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 88LL))(v56) + 24);
              v58 = *((_QWORD *)this + 16);
              v59 = *(_QWORD *)(v58 + 32);
              v60 = v59 ? *(_DWORD *)(v59 + 16) : 0;
              v61 = v59 ? *(_QWORD *)(v59 + 24) : 0LL;
              v62 = *(_QWORD *)(v58 + 48);
              v63 = v62 ? *(_DWORD *)(v62 + 16) : 0;
              v64 = v62 ? *(_QWORD *)(v62 + 24) : 0LL;
              v6 = v54(v53, *((_QWORD *)v85 + 3), *((unsigned int *)v85 + 4), v64, v63, v61, v60, v57, v55);
              if ( v6 < 0 )
                return (unsigned int)v6;
            }
          }
          else
          {
            v65 = *((_QWORD *)this + 11);
            if ( v65 )
            {
              v66 = *(_QWORD *)(v44 + 32);
              v67 = v66 ? *(_DWORD *)(v66 + 16) : 0;
              v68 = v66 ? *(_QWORD *)(v66 + 24) : 0LL;
              v69 = *(_QWORD *)(v44 + 48);
              v70 = v69 ? *(_DWORD *)(v69 + 16) : 0;
              v71 = v69 ? *(_QWORD *)(v69 + 24) : 0LL;
              v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, __int64, int))(*(_QWORD *)v65 + 48LL))(
                     v65,
                     *((_QWORD *)v85 + 3),
                     *((unsigned int *)v85 + 4),
                     v71,
                     v70,
                     v68,
                     v67);
              if ( v6 < 0 )
                return (unsigned int)v6;
            }
          }
        }
      }
      assign((struct IUnknown **)this + 16, 0);
      v95 = 0;
      v96 = 0;
      v43 = v97;
      goto LABEL_68;
    }
    if ( *((_DWORD *)a4 + 1) != 8 )
    {
      if ( *((_DWORD *)a4 + 1) == 9 )
      {
        v22 = *((_DWORD *)this + 40);
        if ( v22 == 9 || v22 == 24 )
        {
          DeclFactory::finalizeAttDef(this);
          if ( *((_QWORD *)this + 11) )
          {
            v23 = *((_QWORD *)this + 18);
            v24 = *(_QWORD *)(v23 + 88);
            if ( v24 )
            {
              v25 = Name::toDeclString(*(Name **)(v23 + 16));
              for ( i = 0; i < *(_DWORD *)(v24 + 20) && *((_BYTE *)this + 99); ++i )
              {
                v27 = *(_QWORD *)(*(_QWORD *)(v24 + 32) + 8LL * i);
                if ( !*(_BYTE *)(v27 + 97) )
                {
                  v28 = Name::toDeclString(*(Name **)(v27 + 16));
                  DataType = DTDDecl::getDataType(v27);
                  if ( (unsigned int)(DataType - 9) <= 1 )
                    v30 = *(const struct String *const near **)(v27 + 48);
                  else
                    v30 = (&SAXNames::_cstrings)[DataType + 21];
                  v31 = *(unsigned __int8 *)(v27 + 96);
                  if ( (_BYTE)v31 )
                    v32 = (&SAXNames::_cstrings)[v31 + 31];
                  else
                    v32 = 0;
                  v33 = *(_QWORD *)(v27 + 88);
                  if ( v33 )
                    v34 = *(_DWORD *)(v33 + 16);
                  else
                    v34 = 0;
                  if ( v33 )
                    v35 = *(_QWORD *)(v33 + 24);
                  else
                    v35 = 0;
                  if ( v32 )
                    v36 = *((_DWORD *)v32 + 4);
                  else
                    v36 = 0;
                  if ( v32 )
                    v37 = *((_QWORD *)v32 + 3);
                  else
                    v37 = 0;
                  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, __int64, int, __int64, int))(**((_QWORD **)this + 11) + 32LL))(
                         *((_QWORD *)this + 11),
                         *((_QWORD *)v25 + 3),
                         *((unsigned int *)v25 + 4),
                         *((_QWORD *)v28 + 3),
                         *((_DWORD *)v28 + 4),
                         *((_QWORD *)v30 + 3),
                         *((_DWORD *)v30 + 4),
                         v37,
                         v36,
                         v35,
                         v34);
                  if ( v6 < 0 )
                    return (unsigned int)v6;
                  *(_BYTE *)(v27 + 97) = 1;
                }
              }
            }
          }
        }
        assign((struct IUnknown **)this + 18, 0);
        assign((struct IUnknown **)this + 19, 0);
        *((_QWORD *)this + 20) = 0;
        v89 = 0;
        v90 = 0;
        v21 = v91;
      }
      else
      {
        if ( *((_DWORD *)a4 + 1) != 10 )
        {
          if ( *((_DWORD *)a4 + 1) == 11 )
          {
            v8 = *((_DWORD *)this + 40);
            if ( v8 == 8 )
            {
              StringBuffer::append(*((StringBuffer **)this + 15), 0x29u);
            }
            else if ( v8 == 24 )
            {
              StringBuffer::append(*((StringBuffer **)this + 15), 0x29u);
              v9 = *((_QWORD *)this + 19);
              v10 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 88LL))(*((_QWORD *)this + 15));
              assign((struct IUnknown **)(v9 + 48), v10);
              *(_DWORD *)(*((_QWORD *)this + 15) + 16LL) = 0;
            }
          }
          return (unsigned int)v6;
        }
        v11 = (_DWORD *)((char *)this + 160);
        if ( *((_QWORD *)this + 9) && *v11 == 10 )
        {
          v12 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 24LL) + 40LL);
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 88LL))(v12);
          v85 = (struct String *)v13;
          v14 = *((_QWORD *)this + 17);
          v15 = *(_QWORD *)(v14 + 32);
          v16 = v15 ? *(_DWORD *)(v15 + 16) : 0;
          v17 = v15 ? *(_QWORD *)(v15 + 24) : 0LL;
          v18 = *(_QWORD *)(v14 + 40);
          v19 = v18 ? *(_DWORD *)(v18 + 16) : 0;
          v20 = v18 ? *(_QWORD *)(v18 + 24) : 0LL;
          v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, __int64, int))(**((_QWORD **)this + 9)
                                                                                             + 24LL))(
                 *((_QWORD *)this + 9),
                 *(_QWORD *)(v13 + 24),
                 *(unsigned int *)(v13 + 16),
                 v20,
                 v19,
                 v17,
                 v16);
          if ( v6 < 0 )
            return (unsigned int)v6;
        }
        assign((struct IUnknown **)this + 17, 0);
        *v11 = 0;
        *((_DWORD *)this + 41) = 0;
        v86[1] = 0;
        v87 = 0;
        v21 = v88;
      }
      *((_DWORD *)this + 28) = 0;
      *((_QWORD *)this + 13) = 0;
      *((_DWORD *)this + 29) = v21;
      return (unsigned int)v6;
    }
    if ( *((_DWORD *)this + 40) != 8 || !*((_QWORD *)this + 11) )
    {
LABEL_67:
      assign((struct IUnknown **)this + 18, 0);
      v92 = 0;
      v93 = 0;
      v43 = v94;
LABEL_68:
      *((_DWORD *)this + 28) = 0;
      *((_QWORD *)this + 13) = 0;
      *((_DWORD *)this + 29) = v43;
      goto LABEL_134;
    }
    v38 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 18) + 80LL) + 80LL);
    if ( v38 )
    {
      if ( v38 != 4 )
      {
        v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 88LL))(*((_QWORD *)this + 15));
        *(_DWORD *)(*((_QWORD *)this + 15) + 16LL) = 0;
        goto LABEL_66;
      }
      v40 = 24;
    }
    else
    {
      v40 = 23;
    }
    v41 = XMLNames::name(v40);
    v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v41 + 5) + 88LL))(*((_QWORD *)v41 + 5));
LABEL_66:
    v42 = v39;
    v85 = Name::toDeclString(*(Name **)(*((_QWORD *)this + 18) + 16LL));
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 11) + 24LL))(
           *((_QWORD *)this + 11),
           *((_QWORD *)v85 + 3),
           *((unsigned int *)v85 + 4),
           *(_QWORD *)(v42 + 24),
           *(_DWORD *)(v42 + 16));
    if ( v6 < 0 )
      return (unsigned int)v6;
    goto LABEL_67;
  }
  if ( *((_QWORD *)this + 10)
    && *((_BYTE *)this + 172)
    && !*((_BYTE *)this + 171)
    && (!*((_QWORD *)this + 22) || !*((_BYTE *)this + 97)) )
  {
    v72 = Name::toDeclString(*(Name **)(*(_QWORD *)(*((_QWORD *)this + 5) + 152LL) + 16LL));
    v85 = v72;
    v73 = *((_QWORD *)this + 22);
    v74 = v73 ? *(struct String **)(v73 + 24) : 0LL;
    v75 = *((_QWORD *)this + 23);
    v76 = v75 ? *(_DWORD *)(v75 + 16) : 0;
    v77 = v75 ? *(_QWORD *)(v75 + 24) : 0LL;
    v84 = v74;
    LODWORD(v83) = v76;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 10) + 24LL))(
           *((_QWORD *)this + 10),
           *((_QWORD *)v72 + 3),
           *((unsigned int *)v72 + 4),
           v77);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  v78 = (char *)this + 99;
  if ( !*((_QWORD *)this + 22) || !*v78 )
  {
LABEL_130:
    v81 = *((_QWORD *)this + 10);
    if ( v81 )
    {
      if ( *((_BYTE *)this + 172) )
      {
        if ( *v78 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 32LL))(v81);
          if ( v6 < 0 )
            return (unsigned int)v6;
        }
      }
    }
LABEL_134:
    *((_QWORD *)this + 20) = 0;
    return (unsigned int)v6;
  }
  v85 = (struct String *)&SAXNames::s_cstrSaxDtd;
  if ( !*((_BYTE *)this + 97) )
  {
    v80 = *((_QWORD *)this + 8);
    if ( v80 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 near *const, _QWORD))(*(_QWORD *)v80 + 104LL))(
             v80,
             off_1801452B8,
             (unsigned int)qword_1801452B0);
      if ( v6 < 0 )
        return (unsigned int)v6;
    }
    goto LABEL_130;
  }
  v86[0] = 0;
  Parser = ContentFactory::getParser(v7, a2);
  (*(void (__fastcall **)(struct IXMLNodeSource *, _QWORD *))(*(_QWORD *)a2 + 104LL))(a2, v86);
  v6 = (*(__int64 (__fastcall **)(struct XMLParser *, _QWORD, _QWORD))(*(_QWORD *)Parser + 144LL))(
         Parser,
         v86[0],
         *(_QWORD *)(*((_QWORD *)this + 22) + 24LL));
  (*(void (__fastcall **)(struct XMLParser *))(*(_QWORD *)Parser + 16LL))(Parser);
  if ( v6 < 0 )
    Exception::throwHR(v6, -1072898008, (struct String *)&SAXNames::s_cstrSaxDtd, 0, v83, v84);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d6260  mov     rax, rsp
0x1800d6263  mov     [rax+8], rbx
0x1800d6267  mov     [rax+18h], rsi
0x1800d626b  mov     [rax+10h], rdx
0x1800d626f  push    rdi
0x1800d6270  push    r12
0x1800d6272  push    r13
0x1800d6274  push    r14
0x1800d6276  push    r15
0x1800d6278  sub     rsp, 0C0h
0x1800d627f  mov     r15, rdx
0x1800d6282  mov     rdi, rcx
0x1800d6285  xor     r13d, r13d
0x1800d6288  mov     esi, r13d
0x1800d628b  mov     [rax-80h], r13
0x1800d628f  mov     ecx, [r9+4]
0x1800d6293  sub     ecx, 5
0x1800d6296  jz      loc_1800D68E5
0x1800d629c  sub     ecx, 2; this
0x1800d629f  jz      loc_1800D66B6
0x1800d62a5  sub     ecx, 1
0x1800d62a8  jz      loc_1800D65CD
0x1800d62ae  sub     ecx, 1
0x1800d62b1  jz      loc_1800D6414
0x1800d62b7  sub     ecx, 1
0x1800d62ba  jz      short loc_1800D6326
0x1800d62bc  cmp     ecx, 1
0x1800d62bf  jnz     loc_1800D6AB7
0x1800d62c5  mov     eax, [rdi+0A0h]
0x1800d62cb  cmp     eax, 8
0x1800d62ce  jnz     short loc_1800D62E1
0x1800d62d0  lea     edx, [rcx+28h]; unsigned __int16
0x1800d62d3  mov     rcx, [rdi+78h]; this
0x1800d62d7  call    ?append@StringBuffer@@QEAAPEAV1@G@Z; StringBuffer::append(ushort)
0x1800d62dc  jmp     loc_1800D6AB7
0x1800d62e1  cmp     eax, 18h
0x1800d62e4  jnz     loc_1800D6AB7
0x1800d62ea  lea     edx, [rax+11h]; unsigned __int16
0x1800d62ed  mov     rcx, [rdi+78h]; this
0x1800d62f1  call    ?append@StringBuffer@@QEAAPEAV1@G@Z; StringBuffer::append(ushort)
0x1800d62f6  mov     rbx, [rdi+98h]
0x1800d62fd  mov     rcx, [rdi+78h]
0x1800d6301  mov     rax, [rcx]
0x1800d6304  mov     rax, [rax+58h]
0x1800d6308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d630d  lea     rcx, [rbx+30h]; struct IUnknown **
0x1800d6311  mov     rdx, rax; void *
0x1800d6314  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d6319  mov     rax, [rdi+78h]
0x1800d631d  mov     [rax+10h], r13d
0x1800d6321  jmp     loc_1800D6AB7
0x1800d6326  lea     rbx, [rdi+0A0h]
0x1800d632d  cmp     [rdi+48h], r13
0x1800d6331  jz      loc_1800D63E3
0x1800d6337  cmp     dword ptr [rbx], 0Ah
0x1800d633a  jnz     loc_1800D63E3
0x1800d6340  mov     rax, [rdi+88h]
0x1800d6347  mov     rcx, [rax+18h]
0x1800d634b  mov     rcx, [rcx+28h]
0x1800d634f  mov     rax, [rcx]
0x1800d6352  mov     rax, [rax+58h]
0x1800d6356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d635b  mov     r10, rax
0x1800d635e  mov     [rsp+0E8h+var_80], rax
0x1800d6363  mov     r11, [rdi+48h]
0x1800d6367  mov     rax, [r11]
0x1800d636a  mov     rsi, [rax+18h]
0x1800d636e  mov     rax, [rdi+88h]
0x1800d6375  mov     rcx, [rax+20h]
0x1800d6379  test    rcx, rcx
0x1800d637c  jz      short loc_1800D6384
0x1800d637e  mov     r8d, [rcx+10h]
0x1800d6382  jmp     short loc_1800D6387
0x1800d6384  mov     r8d, r13d
0x1800d6387  test    rcx, rcx
0x1800d638a  jz      short loc_1800D6392
0x1800d638c  mov     rdx, [rcx+18h]
0x1800d6390  jmp     short loc_1800D6395
0x1800d6392  mov     rdx, r13
0x1800d6395  mov     rax, [rax+28h]
0x1800d6399  test    rax, rax
0x1800d639c  jz      short loc_1800D63A3
0x1800d639e  mov     ecx, [rax+10h]
0x1800d63a1  jmp     short loc_1800D63A6
0x1800d63a3  mov     ecx, r13d
0x1800d63a6  test    rax, rax
0x1800d63a9  jz      short loc_1800D63B1
0x1800d63ab  mov     r9, [rax+18h]
0x1800d63af  jmp     short loc_1800D63B4
0x1800d63b1  mov     r9, r13
0x1800d63b4  mov     [rsp+0E8h+var_B8], r8d
0x1800d63b9  mov     [rsp+0E8h+var_C0], rdx
0x1800d63be  mov     dword ptr [rsp+0E8h+var_C8], ecx
0x1800d63c2  mov     r8d, [r10+10h]
0x1800d63c6  mov     rdx, [r10+18h]
0x1800d63ca  mov     rcx, r11
0x1800d63cd  mov     rax, rsi
0x1800d63d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d63d5  mov     esi, eax
0x1800d63d7  mov     [rsp+0E8h+var_88], eax
0x1800d63db  test    eax, eax
0x1800d63dd  js      loc_1800D6B70
0x1800d63e3  lea     rcx, [rdi+88h]; struct IUnknown **
0x1800d63ea  xor     edx, edx; void *
0x1800d63ec  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d63f1  mov     [rbx], r13d
0x1800d63f4  mov     [rdi+0A4h], r13d
0x1800d63fb  mov     [rsp+0E8h+var_70], r13
0x1800d6400  mov     [rsp+0E8h+var_68], r13d
0x1800d6408  mov     eax, [rsp+0E8h+var_64]
0x1800d640f  jmp     loc_1800D65BD
0x1800d6414  mov     eax, [rdi+0A0h]
0x1800d641a  cmp     eax, 9
0x1800d641d  jz      short loc_1800D6428
0x1800d641f  cmp     eax, 18h
0x1800d6422  jnz     loc_1800D657F
0x1800d6428  mov     rcx, rdi; this
0x1800d642b  call    ?finalizeAttDef@DeclFactory@@AEAAXXZ; DeclFactory::finalizeAttDef(void)
0x1800d6430  cmp     [rdi+58h], r13
0x1800d6434  jz      loc_1800D657F
0x1800d643a  mov     rcx, [rdi+90h]
0x1800d6441  mov     r15, [rcx+58h]
0x1800d6445  test    r15, r15
0x1800d6448  jz      loc_1800D657F
0x1800d644e  mov     rcx, [rcx+10h]; this
0x1800d6452  call    ?toDeclString@Name@@QEAAPEAVString@@XZ; Name::toDeclString(void)
0x1800d6457  mov     r12, rax
0x1800d645a  mov     r14d, r13d
0x1800d645d  mov     [rsp+0E8h+var_84], r13d
0x1800d6462  cmp     r14d, [r15+14h]
0x1800d6466  jge     loc_1800D657F
0x1800d646c  cmp     [rdi+63h], r13b
0x1800d6470  jz      loc_1800D657F
0x1800d6476  movsxd  rdx, r14d
0x1800d6479  mov     rcx, [r15+20h]
0x1800d647d  mov     rbx, [rcx+rdx*8]
0x1800d6481  cmp     [rbx+61h], r13b
0x1800d6485  jz      short loc_1800D648C
0x1800d6487  jmp     loc_1800D6572
0x1800d648c  mov     rcx, [rbx+10h]; this
0x1800d6490  call    ?toDeclString@Name@@QEAAPEAVString@@XZ; Name::toDeclString(void)
0x1800d6495  mov     r13, rax
0x1800d6498  mov     rcx, rbx
0x1800d649b  call    ?getDataType@DTDDecl@@QEAA?AW4DataType@@XZ; DTDDecl::getDataType(void)
0x1800d64a0  lea     ecx, [rax-9]
0x1800d64a3  lea     rdx, ?_cstrings@SAXNames@@2QBQEBVString@@B; String const * const near * const SAXNames::_cstrings
0x1800d64aa  cmp     ecx, 1
0x1800d64ad  jbe     short loc_1800D64BC
0x1800d64af  movsxd  rcx, eax
0x1800d64b2  mov     r10, [rdx+rcx*8+0A8h]
0x1800d64ba  jmp     short loc_1800D64C0
0x1800d64bc  mov     r10, [rbx+30h]
0x1800d64c0  movzx   eax, byte ptr [rbx+60h]
0x1800d64c4  test    al, al
0x1800d64c6  jnz     short loc_1800D64CC
0x1800d64c8  xor     ecx, ecx
0x1800d64ca  jmp     short loc_1800D64D4
0x1800d64cc  mov     rcx, [rdx+rax*8+0F8h]
0x1800d64d4  mov     rdx, [rbx+58h]
0x1800d64d8  mov     r11, [rdi+58h]
0x1800d64dc  mov     rax, [r11]
0x1800d64df  mov     rsi, [rax+20h]
0x1800d64e3  test    rdx, rdx
0x1800d64e6  jz      short loc_1800D64EE
0x1800d64e8  mov     r9d, [rdx+10h]
0x1800d64ec  jmp     short loc_1800D64F1
0x1800d64ee  xor     r9d, r9d
0x1800d64f1  test    rdx, rdx
0x1800d64f4  jz      short loc_1800D64FC
0x1800d64f6  mov     r8, [rdx+18h]
0x1800d64fa  jmp     short loc_1800D64FF
0x1800d64fc  xor     r8d, r8d
0x1800d64ff  test    rcx, rcx
0x1800d6502  jz      short loc_1800D6509
0x1800d6504  mov     edx, [rcx+10h]
0x1800d6507  jmp     short loc_1800D650B
0x1800d6509  xor     edx, edx
0x1800d650b  test    rcx, rcx
0x1800d650e  jz      short loc_1800D6516
0x1800d6510  mov     rax, [rcx+18h]
0x1800d6514  jmp     short loc_1800D6518
0x1800d6516  xor     eax, eax
0x1800d6518  mov     [rsp+0E8h+var_98], r9d
0x1800d651d  mov     [rsp+0E8h+var_A0], r8
0x1800d6522  mov     [rsp+0E8h+var_A8], edx
0x1800d6526  mov     [rsp+0E8h+var_B0], rax
0x1800d652b  mov     edx, [r10+10h]
0x1800d652f  mov     [rsp+0E8h+var_B8], edx
0x1800d6533  mov     rdx, [r10+18h]
0x1800d6537  mov     [rsp+0E8h+var_C0], rdx
0x1800d653c  mov     edx, [r13+10h]
0x1800d6540  mov     dword ptr [rsp+0E8h+var_C8], edx
0x1800d6544  mov     r9, [r13+18h]
0x1800d6548  mov     r8d, [r12+10h]
0x1800d654d  mov     rdx, [r12+18h]
0x1800d6552  mov     rcx, r11
0x1800d6555  mov     rax, rsi
0x1800d6558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d655d  mov     esi, eax
0x1800d655f  mov     [rsp+0E8h+var_88], eax
0x1800d6563  xor     r13d, r13d
0x1800d6566  test    eax, eax
0x1800d6568  js      loc_1800D6B70
0x1800d656e  mov     byte ptr [rbx+61h], 1
0x1800d6572  inc     r14d
0x1800d6575  mov     [rsp+0E8h+var_84], r14d
0x1800d657a  jmp     loc_1800D6462
0x1800d657f  lea     rcx, [rdi+90h]; struct IUnknown **
0x1800d6586  xor     edx, edx; void *
0x1800d6588  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d658d  lea     rcx, [rdi+98h]; struct IUnknown **
0x1800d6594  xor     edx, edx; void *
0x1800d6596  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d659b  mov     qword ptr [rdi+0A0h], 0
0x1800d65a6  mov     [rsp+0E8h+var_60], r13
0x1800d65ae  mov     [rsp+0E8h+var_58], r13d
0x1800d65b6  mov     eax, [rsp+0E8h+var_54]
0x1800d65bd  mov     [rdi+70h], r13d
0x1800d65c1  mov     [rdi+68h], r13
0x1800d65c5  mov     [rdi+74h], eax
0x1800d65c8  jmp     loc_1800D6AB7
0x1800d65cd  cmp     dword ptr [rdi+0A0h], 8
0x1800d65d4  jnz     loc_1800D6681
0x1800d65da  cmp     [rdi+58h], r13
0x1800d65de  jz      loc_1800D6681
0x1800d65e4  mov     rax, [rdi+90h]
0x1800d65eb  mov     rcx, [rax+50h]
0x1800d65ef  mov     al, [rcx+50h]
0x1800d65f2  test    al, al
0x1800d65f4  jz      short loc_1800D661B
0x1800d65f6  cmp     al, 4
0x1800d65f8  jz      short loc_1800D6614
0x1800d65fa  mov     rcx, [rdi+78h]
0x1800d65fe  mov     rax, [rcx]
0x1800d6601  mov     rax, [rax+58h]
0x1800d6605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d660a  mov     rcx, [rdi+78h]
0x1800d660e  mov     [rcx+10h], r13d
0x1800d6612  jmp     short loc_1800D6635
0x1800d6614  mov     ecx, 18h
0x1800d6619  jmp     short loc_1800D6620
0x1800d661b  mov     ecx, 17h; int
0x1800d6620  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x1800d6625  mov     rcx, [rax+28h]
0x1800d6629  mov     rax, [rcx]
0x1800d662c  mov     rax, [rax+58h]
0x1800d6630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6635  mov     rbx, rax
0x1800d6638  mov     rcx, [rdi+90h]
0x1800d663f  mov     rcx, [rcx+10h]; this
0x1800d6643  call    ?toDeclString@Name@@QEAAPEAVString@@XZ; Name::toDeclString(void)
0x1800d6648  mov     r10, rax
0x1800d664b  mov     [rsp+0E8h+var_80], rax
0x1800d6650  mov     rcx, [rdi+58h]
0x1800d6654  mov     rdx, [rcx]
0x1800d6657  mov     rax, [rdx+18h]
0x1800d665b  mov     edx, [rbx+10h]
0x1800d665e  mov     dword ptr [rsp+0E8h+var_C8], edx
0x1800d6662  mov     r9, [rbx+18h]
0x1800d6666  mov     r8d, [r10+10h]
0x1800d666a  mov     rdx, [r10+18h]
0x1800d666e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6673  mov     esi, eax
0x1800d6675  mov     [rsp+0E8h+var_88], eax
0x1800d6679  test    eax, eax
0x1800d667b  js      loc_1800D6B70
0x1800d6681  lea     rcx, [rdi+90h]; struct IUnknown **
0x1800d6688  xor     edx, edx; void *
0x1800d668a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800d668f  mov     [rsp+0E8h+var_50], r13
0x1800d6697  mov     [rsp+0E8h+var_48], r13d
0x1800d669f  mov     eax, [rsp+0E8h+var_44]
0x1800d66a6  mov     [rdi+70h], r13d
0x1800d66aa  mov     [rdi+68h], r13
0x1800d66ae  mov     [rdi+74h], eax
0x1800d66b1  jmp     loc_1800D6AB0
0x1800d66b6  cmp     dword ptr [rdi+0A0h], 7
0x1800d66bd  jnz     loc_1800D68BB
0x1800d66c3  lea     r8, [rsp+0E8h+var_80]; struct String **
0x1800d66c8  mov     rdx, [rdi+80h]; struct Entity *
0x1800d66cf  call    ?getEntityName@DeclFactory@@AEAAXPEAVEntity@@PEAPEAVString@@@Z; DeclFactory::getEntityName(Entity *,String * *)
0x1800d66d4  mov     rdx, [rdi+80h]
0x1800d66db  mov     r9, [rdx+38h]
0x1800d66df  test    r9, r9
0x1800d66e2  jz      short loc_1800D6760
0x1800d66e4  mov     r10, [rdi+58h]
0x1800d66e8  test    r10, r10
0x1800d66eb  jz      loc_1800D68BB
0x1800d66f1  mov     rax, [r10]
0x1800d66f4  mov     r11, [rax+28h]
0x1800d66f8  mov     eax, [rdx+60h]
0x1800d66fb  shr     eax, 5
0x1800d66fe  mov     rdx, [rsp+0E8h+var_80]
0x1800d6703  mov     r8d, [rdx+10h]
0x1800d6707  mov     rdx, [rdx+18h]
0x1800d670b  test    al, 1
0x1800d670d  mov     rax, r11
0x1800d6710  jz      short loc_1800D6739
0x1800d6712  mov     dword ptr [rsp+0E8h+var_C8], r13d
0x1800d6717  lea     r9, word_18012A048
  ... truncated ...
```
