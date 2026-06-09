# nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::dump(nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> const &,bool,bool,uint,uint)

- ea: `0x18002330c`
- end: `0x180023c04`
- name: `?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z`
- size: `2296`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800230a8`
- `0x18002330c`

## callees

- `0x180016610`
- `0x180016724`
- `0x180016898`
- `0x18002330c`
- `0x180023c0c`
- `0x18002402c`
- `0x180025c30`
- `0x180030010`

## pseudocode

```c
void __fastcall nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
        __int64 **a1,
        unsigned __int8 *a2,
        char a3,
        __int64 a4,
        int a5,
        unsigned int a6)
{
  unsigned int v7; // ecx
  unsigned __int8 *v8; // rsi
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  __int64 *v12; // rcx
  void (__fastcall *v13)(__int64 *, const char *, __int64); // rax
  __int64 v14; // r8
  const char *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // r14
  int v20; // ebp
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // r13
  __int64 i; // rbx
  _QWORD **v24; // rdx
  int v25; // r8d
  _QWORD **v26; // rdx
  int v27; // r8d
  __int64 v28; // rdx
  __int64 j; // rbx
  __int64 v30; // rdx
  __int64 v31; // rdx
  _QWORD *v32; // r14
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // r8
  __int64 v35; // rax
  unsigned __int64 v36; // r13
  _QWORD *v37; // rbx
  _QWORD **v38; // rdx
  __int64 v39; // rdx
  int v40; // r8d
  __int64 **v41; // rcx
  __int64 n; // rax
  __int64 *ii; // rcx
  _QWORD **v44; // rdx
  __int64 v45; // rdx
  int v46; // r8d
  __int64 v47; // rdx
  __int64 *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // rax
  unsigned __int64 v53; // r14
  _QWORD *v54; // rbx
  __int64 v55; // rdx
  __int64 **v56; // rcx
  __int64 k; // rax
  __int64 *m; // rcx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  __int64 *v62; // rcx
  void (__fastcall *v63)(__int64 *, const char *, __int64); // rax
  __int64 v64; // r8
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // r12
  _QWORD **v67; // rdx
  __int64 v68; // rax
  _BYTE *v69; // rbx
  _BYTE *v70; // rdx
  _QWORD **v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // rax
  _BYTE *v75; // rbx
  _BYTE *v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rdx
  unsigned __int64 v79; // [rsp+78h] [rbp+10h]
  int v80; // [rsp+88h] [rbp+20h]

  v7 = *a2;
  v8 = a2;
  if ( v7 > 5 )
  {
    v59 = v7 - 6;
    if ( v59 )
    {
      v60 = v59 - 1;
      if ( v60 )
      {
        v61 = v60 - 1;
        if ( !v61 )
        {
          v62 = *a1;
          v63 = *(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8);
          if ( !a3 )
          {
            v63(v62, "{\"bytes\":[", 10);
            v74 = *((_QWORD *)v8 + 1);
            v75 = *(_BYTE **)v74;
            if ( *(_QWORD *)v74 != *(_QWORD *)(v74 + 8) )
            {
              while ( 1 )
              {
                v76 = (_BYTE *)(*(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 1LL);
                if ( v75 == v76 )
                  break;
                LOBYTE(v76) = *v75;
                nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
                  a1,
                  v76);
                LOBYTE(v77) = 44;
                (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v77);
                ++v75;
              }
              LOBYTE(v76) = *v76;
              nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
                a1,
                v76);
            }
            (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "],\"subtype\":", 12);
            v78 = *((_QWORD *)v8 + 1);
            if ( !*(_BYTE *)(v78 + 25) )
            {
              v12 = *a1;
              v15 = "null}";
              v14 = 5;
              v17 = **a1;
              goto LABEL_37;
            }
            LOBYTE(v78) = *(_BYTE *)(v78 + 24);
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
              a1,
              v78);
            goto LABEL_73;
          }
          v63(v62, "{\n", 2);
          v32 = a1 + 76;
          v65 = (unsigned __int64)a1[78];
          v66 = a6 + a5;
          if ( v65 < v66 )
          {
            LOBYTE(v64) = 32;
            std::string::resize(a1 + 76, 2 * v65, v64);
          }
          if ( (unsigned __int64)a1[79] <= 0xF )
            v67 = a1 + 76;
          else
            v67 = (_QWORD **)*v32;
          (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v67, v66);
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\"bytes\": [", 10);
          v68 = *((_QWORD *)v8 + 1);
          v69 = *(_BYTE **)v68;
          if ( *(_QWORD *)v68 != *(_QWORD *)(v68 + 8) )
          {
            while ( 1 )
            {
              v70 = (_BYTE *)(*(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 1LL);
              if ( v69 == v70 )
                break;
              LOBYTE(v70) = *v69;
              nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
                a1,
                v70);
              (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, ", ", 2);
              ++v69;
            }
            LOBYTE(v70) = *v70;
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
              a1,
              v70);
          }
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "],\n", 3);
          if ( (unsigned __int64)a1[79] <= 0xF )
            v71 = a1 + 76;
          else
            v71 = (_QWORD **)*v32;
          (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v71, v66);
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\"subtype\": ", 11);
          v72 = *((_QWORD *)v8 + 1);
          if ( *(_BYTE *)(v72 + 25) )
          {
            LOBYTE(v72) = *(_BYTE *)(v72 + 24);
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned char,0>(
              a1,
              v72);
          }
          else
          {
            (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "null", 4);
          }
          LOBYTE(v73) = 10;
          (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v73);
          v48 = *a1;
          v49 = **a1;
          if ( (unsigned __int64)a1[79] > 0xF )
            v32 = (_QWORD *)*v32;
          v50 = a6;
          goto LABEL_61;
        }
        if ( v61 == 1 )
        {
          v12 = *a1;
          v15 = "<discarded>";
          v14 = 11;
          v17 = **a1;
          goto LABEL_37;
        }
      }
      else
      {
        nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_float(a1);
      }
    }
    else
    {
      nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<unsigned __int64,0>(
        a1,
        *((_QWORD *)a2 + 1));
    }
  }
  else
  {
    if ( v7 != 5 )
    {
      if ( !*a2 )
      {
        v12 = *a1;
        v15 = "null";
        v14 = 4;
        v17 = **a1;
        goto LABEL_37;
      }
      v9 = v7 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 != 1 )
              return;
            v12 = *a1;
            v13 = *(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8);
            if ( a2[8] )
            {
              v14 = 4;
              v15 = "true";
            }
            else
            {
              v14 = 5;
              v15 = "false";
            }
            goto LABEL_38;
          }
          LOBYTE(a2) = 34;
          (*(void (__fastcall **)(__int64 *, unsigned __int8 *))**a1)(*a1, a2);
          nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
            a1,
            *((_QWORD **)v8 + 1));
          LOBYTE(v16) = 34;
          goto LABEL_74;
        }
        v12 = *a1;
        v17 = **a1;
        if ( **((_QWORD **)a2 + 1) == *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) )
        {
          v15 = "[]";
LABEL_36:
          v14 = 2;
LABEL_37:
          v13 = *(void (__fastcall **)(__int64 *, const char *, __int64))(v17 + 8);
LABEL_38:
          v13(v12, v15, v14);
          return;
        }
        if ( a3 )
        {
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(v17 + 8))(v12, "[\n", 2);
          v19 = a1 + 76;
          v20 = a5 + a6;
          v21 = (unsigned __int64)a1[78];
          v22 = a5 + a6;
          if ( v21 < v22 )
          {
            LOBYTE(v18) = 32;
            std::string::resize(a1 + 76, 2 * v21, v18);
          }
          for ( i = **((_QWORD **)v8 + 1); i != *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 16LL; i += 16 )
          {
            if ( (unsigned __int64)a1[79] <= 0xF )
              v24 = a1 + 76;
            else
              v24 = (_QWORD **)*v19;
            (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v24, v22);
            LOBYTE(v25) = 1;
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
              (_DWORD)a1,
              i,
              v25,
              0,
              a5,
              v20);
            (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, ",\n", 2);
          }
          if ( (unsigned __int64)a1[79] <= 0xF )
            v26 = a1 + 76;
          else
            v26 = (_QWORD **)*v19;
          (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v26, v22);
          LOBYTE(v27) = 1;
          nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
            (_DWORD)a1,
            *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 16,
            v27,
            0,
            a5,
            v20);
          LOBYTE(v28) = 10;
          (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v28);
          if ( (unsigned __int64)a1[79] > 0xF )
            v19 = (_QWORD *)*v19;
          (*(void (__fastcall **)(__int64 *, _QWORD *, _QWORD))(**a1 + 8))(*a1, v19, a6);
        }
        else
        {
          LOBYTE(a2) = 91;
          (*(void (__fastcall **)(__int64 *, unsigned __int8 *))v17)(v12, a2);
          for ( j = **((_QWORD **)v8 + 1); ; j += 16 )
          {
            v30 = *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 16LL;
            if ( j == v30 )
              break;
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
              (_DWORD)a1,
              j,
              0,
              0,
              a5,
              a6);
            LOBYTE(v31) = 44;
            (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v31);
          }
          nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
            (_DWORD)a1,
            v30,
            0,
            0,
            a5,
            a6);
        }
        LOBYTE(v16) = 93;
LABEL_74:
        (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v16);
        return;
      }
      v12 = *a1;
      v17 = **a1;
      if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) )
      {
        v15 = "{}";
        goto LABEL_36;
      }
      if ( !a3 )
      {
        LOBYTE(a2) = 123;
        (*(void (__fastcall **)(__int64 *, unsigned __int8 *))v17)(v12, a2);
        v52 = *((_QWORD *)v8 + 1);
        v53 = 0;
        v54 = **(_QWORD ***)v52;
        if ( *(_QWORD *)(v52 + 8) != 1 )
        {
          do
          {
            LOBYTE(v51) = 34;
            (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v51);
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
              a1,
              v54 + 4);
            (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\":", 2);
            nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
              (_DWORD)a1,
              (_DWORD)v54 + 64,
              0,
              0,
              a5,
              a6);
            LOBYTE(v55) = 44;
            (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v55);
            v56 = (__int64 **)v54[2];
            ++v53;
            if ( *((_BYTE *)v56 + 25) )
            {
              for ( k = v54[1]; !*(_BYTE *)(k + 25) && v54 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
                v54 = (_QWORD *)k;
              v54 = (_QWORD *)k;
            }
            else
            {
              v54 = (_QWORD *)v54[2];
              for ( m = *v56; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                v54 = m;
            }
          }
          while ( v53 < *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 1LL );
        }
        LOBYTE(v51) = 34;
        (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v51);
        nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
          a1,
          v54 + 4);
        (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\":", 2);
        nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
          (_DWORD)a1,
          (_DWORD)v54 + 64,
          0,
          0,
          a5,
          a6);
        goto LABEL_73;
      }
      (*(void (__fastcall **)(__int64 *, const char *, __int64))(v17 + 8))(v12, "{\n", 2);
      v32 = a1 + 76;
      v33 = (unsigned __int64)a1[78];
      v34 = a5 + a6;
      v80 = a5 + a6;
      v79 = v34;
      if ( v33 < v34 )
      {
        LOBYTE(v34) = 32;
        std::string::resize(a1 + 76, 2 * v33, v34);
        v34 = v79;
      }
      v35 = *((_QWORD *)v8 + 1);
      v36 = 0;
      v37 = **(_QWORD ***)v35;
      if ( *(_QWORD *)(v35 + 8) != 1 )
      {
        do
        {
          if ( (unsigned __int64)a1[79] <= 0xF )
            v38 = a1 + 76;
          else
            v38 = (_QWORD **)*v32;
          (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v38, v34);
          LOBYTE(v39) = 34;
          (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v39);
          nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
            a1,
            v37 + 4);
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\": ", 3);
          LOBYTE(v40) = 1;
          nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
            (_DWORD)a1,
            (_DWORD)v37 + 64,
            v40,
            0,
            a5,
            v80);
          (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, ",\n", 2);
          v41 = (__int64 **)v37[2];
          ++v36;
          if ( *((_BYTE *)v41 + 25) )
          {
            for ( n = v37[1]; !*(_BYTE *)(n + 25) && v37 == *(_QWORD **)(n + 16); n = *(_QWORD *)(n + 8) )
              v37 = (_QWORD *)n;
            v37 = (_QWORD *)n;
          }
          else
          {
            v37 = (_QWORD *)v37[2];
            for ( ii = *v41; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
              v37 = ii;
          }
          v34 = v79;
        }
        while ( v36 < *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL) - 1LL );
      }
      if ( (unsigned __int64)a1[79] <= 0xF )
        v44 = a1 + 76;
      else
        v44 = (_QWORD **)*v32;
      (*(void (__fastcall **)(__int64 *, _QWORD **, unsigned __int64))(**a1 + 8))(*a1, v44, v79);
      LOBYTE(v45) = 34;
      (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v45);
      nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_escaped(
        a1,
        v37 + 4);
      (*(void (__fastcall **)(__int64 *, const char *, __int64))(**a1 + 8))(*a1, "\": ", 3);
      LOBYTE(v46) = 1;
      nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump(
        (_DWORD)a1,
        (_DWORD)v37 + 64,
        v46,
        0,
        a5,
        v80);
      LOBYTE(v47) = 10;
      (*(void (__fastcall **)(__int64 *, __int64))**a1)(*a1, v47);
      v48 = *a1;
      v49 = **a1;
      if ( (unsigned __int64)a1[79] > 0xF )
        v32 = (_QWORD *)*v32;
      v50 = a6;
LABEL_61:
      (*(void (__fastcall **)(__int64 *, _QWORD *, __int64))(v49 + 8))(v48, v32, v50);
LABEL_73:
      LOBYTE(v16) = 125;
      goto LABEL_74;
    }
    nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::dump_integer<__int64,0>(
      a1,
      *((_QWORD *)a2 + 1));
  }
}

```

## disassembly

```asm
0x18002330c  mov     [rsp+arg_0], rbx
0x180023311  mov     byte ptr [rsp+arg_18], r9b
0x180023316  push    rbp
0x180023317  push    rsi
0x180023318  push    rdi
0x180023319  push    r12
0x18002331b  push    r13
0x18002331d  push    r14
0x18002331f  push    r15
0x180023321  sub     rsp, 30h
0x180023325  mov     rdi, rcx
0x180023328  mov     r14d, 5
0x18002332e  movzx   ecx, byte ptr [rdx]
0x180023331  mov     rsi, rdx
0x180023334  cmp     ecx, r14d
0x180023337  ja      loc_180023966
0x18002333d  jz      loc_180023955
0x180023343  xor     ebp, ebp
0x180023345  test    ecx, ecx
0x180023347  jz      loc_18002393D
0x18002334d  sub     ecx, 1
0x180023350  jz      loc_18002358A
0x180023356  sub     ecx, 1
0x180023359  jz      short loc_1800233BB
0x18002335b  sub     ecx, 1
0x18002335e  jz      short loc_180023398
0x180023360  cmp     ecx, 1
0x180023363  jnz     loc_180023BEF
0x180023369  mov     rcx, [rdi]
0x18002336c  mov     rax, [rcx]
0x18002336f  mov     rax, [rax+8]
0x180023373  cmp     [rdx+8], bpl
0x180023377  jz      short loc_180023389
0x180023379  lea     r8d, [r14-1]
0x18002337d  lea     rdx, aTrue; "true"
0x180023384  jmp     loc_1800235AB
0x180023389  mov     r8, r14
0x18002338c  lea     rdx, aFalse; "false"
0x180023393  jmp     loc_1800235AB
0x180023398  mov     rcx, [rdi]
0x18002339b  mov     dl, 22h ; '"'
0x18002339d  mov     rax, [rcx]
0x1800233a0  mov     rax, [rax]
0x1800233a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233a8  mov     rdx, [rsi+8]
0x1800233ac  mov     rcx, rdi
0x1800233af  call    ?dump_escaped@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump_escaped(std::string const &,bool)
0x1800233b4  mov     dl, 22h ; '"'
0x1800233b6  jmp     loc_18002392A
0x1800233bb  mov     rcx, [rdx+8]
0x1800233bf  mov     rax, [rcx+8]
0x1800233c3  cmp     [rcx], rax
0x1800233c6  mov     rcx, [rdi]
0x1800233c9  mov     rax, [rcx]
0x1800233cc  jnz     short loc_1800233DA
0x1800233ce  lea     rdx, asc_18003334C; "[]"
0x1800233d5  jmp     loc_1800235A1
0x1800233da  test    r8b, r8b
0x1800233dd  jz      loc_180023522
0x1800233e3  mov     rax, [rax+8]
0x1800233e7  lea     rdx, asc_180033350; "[\n"
0x1800233ee  mov     r15d, 2
0x1800233f4  mov     r8d, r15d
0x1800233f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233fc  mov     ebp, [rsp+68h+arg_28]
0x180023403  lea     r14, [rdi+260h]
0x18002340a  mov     r12d, [rsp+68h+arg_20]
0x180023412  add     ebp, r12d
0x180023415  mov     rdx, [r14+10h]
0x180023419  mov     r13d, ebp
0x18002341c  cmp     rdx, r13
0x18002341f  jnb     short loc_18002342F
0x180023421  add     rdx, rdx
0x180023424  mov     r8b, 20h ; ' '
0x180023427  mov     rcx, r14
0x18002342a  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x18002342f  mov     rbx, [rsi+8]
0x180023433  mov     rbx, [rbx]
0x180023436  mov     r9, [rdi]
0x180023439  mov     rax, [r9]
0x18002343c  mov     r10, [rax+8]
0x180023440  mov     rax, [rsi+8]
0x180023444  mov     rcx, [rax+8]
0x180023448  sub     rcx, 10h
0x18002344c  cmp     rbx, rcx
0x18002344f  jz      short loc_1800234A7
0x180023451  cmp     qword ptr [r14+18h], 0Fh
0x180023456  jbe     short loc_18002345D
0x180023458  mov     rdx, [r14]
0x18002345b  jmp     short loc_180023460
0x18002345d  mov     rdx, r14
0x180023460  mov     r8, r13
0x180023463  mov     rcx, r9
0x180023466  mov     rax, r10
0x180023469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002346e  xor     r9d, r9d
0x180023471  mov     [rsp+68h+var_40], ebp
0x180023475  mov     r8b, 1
0x180023478  mov     [rsp+68h+var_48], r12d
0x18002347d  mov     rdx, rbx
0x180023480  mov     rcx, rdi
0x180023483  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x180023488  mov     rcx, [rdi]
0x18002348b  lea     rdx, asc_180033344; ",\n"
0x180023492  mov     r8, r15
0x180023495  mov     rax, [rcx]
0x180023498  mov     rax, [rax+8]
0x18002349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234a1  add     rbx, 10h
0x1800234a5  jmp     short loc_180023436
0x1800234a7  cmp     qword ptr [r14+18h], 0Fh
0x1800234ac  jbe     short loc_1800234B3
0x1800234ae  mov     rdx, [r14]
0x1800234b1  jmp     short loc_1800234B6
0x1800234b3  mov     rdx, r14
0x1800234b6  mov     r8, r13
0x1800234b9  mov     rcx, r9
0x1800234bc  mov     rax, r10
0x1800234bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c4  mov     rax, [rsi+8]
0x1800234c8  xor     r9d, r9d
0x1800234cb  mov     [rsp+68h+var_40], ebp
0x1800234cf  mov     r8b, 1
0x1800234d2  mov     rcx, rdi
0x1800234d5  mov     [rsp+68h+var_48], r12d
0x1800234da  mov     rdx, [rax+8]
0x1800234de  sub     rdx, 10h
0x1800234e2  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x1800234e7  mov     rcx, [rdi]
0x1800234ea  mov     dl, 0Ah
0x1800234ec  mov     rax, [rcx]
0x1800234ef  mov     rax, [rax]
0x1800234f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f7  cmp     qword ptr [r14+18h], 0Fh
0x1800234fc  mov     rcx, [rdi]
0x1800234ff  mov     rax, [rcx]
0x180023502  jbe     short loc_180023507
0x180023504  mov     r14, [r14]
0x180023507  mov     r8d, [rsp+68h+arg_28]
0x18002350f  mov     rdx, r14
0x180023512  mov     rax, [rax+8]
0x180023516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002351b  mov     dl, 5Dh ; ']'
0x18002351d  jmp     loc_18002392A
0x180023522  mov     rax, [rax]
0x180023525  mov     dl, 5Bh ; '['
0x180023527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002352c  mov     rbx, [rsi+8]
0x180023530  mov     ebp, [rsp+68h+arg_28]
0x180023537  mov     r14d, [rsp+68h+arg_20]
0x18002353f  mov     rbx, [rbx]
0x180023542  mov     rax, [rsi+8]
0x180023546  xor     r9d, r9d
0x180023549  xor     r8d, r8d
0x18002354c  mov     [rsp+68h+var_40], ebp
0x180023550  mov     rcx, rdi
0x180023553  mov     [rsp+68h+var_48], r14d
0x180023558  mov     rdx, [rax+8]
0x18002355c  add     rdx, 0FFFFFFFFFFFFFFF0h
0x180023560  cmp     rbx, rdx
0x180023563  jz      short loc_180023583
0x180023565  mov     rdx, rbx
0x180023568  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x18002356d  mov     rcx, [rdi]
0x180023570  mov     dl, 2Ch ; ','
0x180023572  mov     rax, [rcx]
0x180023575  mov     rax, [rax]
0x180023578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002357d  add     rbx, 10h
0x180023581  jmp     short loc_180023542
0x180023583  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x180023588  jmp     short loc_18002351B
0x18002358a  mov     rax, [rdx+8]
0x18002358e  mov     rcx, [rdi]
0x180023591  cmp     [rax+8], rbp
0x180023595  mov     rax, [rcx]
0x180023598  jnz     short loc_1800235B5
0x18002359a  lea     rdx, asc_180033338; "{}"
0x1800235a1  mov     r8d, 2
0x1800235a7  mov     rax, [rax+8]
0x1800235ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235b0  jmp     loc_180023BEF
0x1800235b5  test    r8b, r8b
0x1800235b8  jz      loc_1800237E4
0x1800235be  mov     rax, [rax+8]
0x1800235c2  lea     rdx, asc_18003333C; "{\n"
0x1800235c9  mov     r15d, 2
0x1800235cf  mov     r8d, r15d
0x1800235d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235d7  mov     eax, [rsp+68h+arg_28]
0x1800235de  lea     r14, [rdi+260h]
0x1800235e5  add     eax, [rsp+68h+arg_20]
0x1800235ec  mov     rdx, [r14+10h]
0x1800235f0  mov     r8d, eax
0x1800235f3  mov     [rsp+68h+arg_18], eax
0x1800235fa  mov     [rsp+68h+arg_8], r8
0x1800235ff  cmp     rdx, r8
0x180023602  jnb     short loc_180023617
0x180023604  add     rdx, rdx
0x180023607  mov     r8b, 20h ; ' '
0x18002360a  mov     rcx, r14
0x18002360d  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180023612  mov     r8, [rsp+68h+arg_8]
0x180023617  mov     rax, [rsi+8]
0x18002361b  mov     r13, rbp
0x18002361e  mov     r12d, 3
0x180023624  cmp     qword ptr [rax+8], 1
0x180023629  mov     rbx, [rax]
0x18002362c  mov     rbx, [rbx]
0x18002362f  jz      loc_18002372B
0x180023635  cmp     qword ptr [rdi+278h], 0Fh
0x18002363d  mov     rcx, [rdi]
0x180023640  mov     rax, [rcx]
0x180023643  jbe     short loc_18002364A
0x180023645  mov     rdx, [r14]
0x180023648  jmp     short loc_18002364D
0x18002364a  mov     rdx, r14
0x18002364d  mov     rax, [rax+8]
0x180023651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023656  mov     rcx, [rdi]
0x180023659  mov     dl, 22h ; '"'
0x18002365b  mov     rax, [rcx]
0x18002365e  mov     rax, [rax]
0x180023661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023666  lea     rdx, [rbx+20h]
0x18002366a  mov     rcx, rdi
0x18002366d  call    ?dump_escaped@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump_escaped(std::string const &,bool)
0x180023672  mov     rcx, [rdi]
0x180023675  lea     rdx, asc_180033340; "\": "
0x18002367c  mov     r8, r12
0x18002367f  mov     rax, [rcx]
0x180023682  mov     rax, [rax+8]
0x180023686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002368b  mov     eax, [rsp+68h+arg_18]
0x180023692  lea     rdx, [rbx+40h]
0x180023696  mov     [rsp+68h+var_40], eax
0x18002369a  xor     r9d, r9d
0x18002369d  mov     eax, [rsp+68h+arg_20]
0x1800236a4  mov     r8b, 1
0x1800236a7  mov     rcx, rdi
0x1800236aa  mov     [rsp+68h+var_48], eax
0x1800236ae  call    ?dump@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@_N1II@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,bool,bool,uint,uint)
0x1800236b3  mov     rcx, [rdi]
0x1800236b6  lea     rdx, asc_180033344; ",\n"
0x1800236bd  mov     r8, r15
0x1800236c0  mov     rax, [rcx]
0x1800236c3  mov     rax, [rax+8]
0x1800236c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236cc  mov     rcx, [rbx+10h]
0x1800236d0  inc     r13
0x1800236d3  cmp     [rcx+19h], bpl
0x1800236d7  jz      short loc_1800236F7
0x1800236d9  mov     rax, [rbx+8]
0x1800236dd  jmp     short loc_1800236EC
0x1800236df  cmp     rbx, [rax+10h]
0x1800236e3  jnz     short loc_1800236F2
0x1800236e5  mov     rbx, rax
0x1800236e8  mov     rax, [rax+8]
0x1800236ec  cmp     [rax+19h], bpl
0x1800236f0  jz      short loc_1800236DF
0x1800236f2  mov     rbx, rax
0x1800236f5  jmp     short loc_180023712
0x1800236f7  mov     rbx, rcx
0x1800236fa  mov     rcx, [rcx]
0x1800236fd  cmp     [rcx+19h], bpl
0x180023701  jnz     short loc_180023712
0x180023703  mov     rax, [rcx]
0x180023706  mov     rbx, rcx
0x180023709  mov     rcx, rax
0x18002370c  cmp     [rax+19h], bpl
0x180023710  jz      short loc_180023703
0x180023712  mov     rax, [rsi+8]
0x180023716  mov     r8, [rsp+68h+arg_8]
0x18002371b  mov     rcx, [rax+8]
0x18002371f  dec     rcx
0x180023722  cmp     r13, rcx
0x180023725  jb      loc_180023635
0x18002372b  cmp     qword ptr [r14+18h], 0Fh
0x180023730  mov     rcx, [rdi]
0x180023733  mov     rax, [rcx]
0x180023736  jbe     short loc_18002373D
0x180023738  mov     rdx, [r14]
0x18002373b  jmp     short loc_180023740
0x18002373d  mov     rdx, r14
0x180023740  mov     r8, [rsp+68h+arg_8]
0x180023745  mov     rax, [rax+8]
0x180023749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002374e  mov     rcx, [rdi]
0x180023751  mov     dl, 22h ; '"'
0x180023753  mov     rax, [rcx]
0x180023756  mov     rax, [rax]
0x180023759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002375e  lea     rdx, [rbx+20h]
0x180023762  mov     rcx, rdi
0x180023765  call    ?dump_escaped@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; nlohmann::detail::serializer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::dump_escaped(std::string const &,bool)
0x18002376a  mov     rcx, [rdi]
0x18002376d  lea     rdx, asc_180033340; "\": "
0x180023774  mov     r8, r12
0x180023777  mov     rax, [rcx]
0x18002377a  mov     rax, [rax+8]
  ... truncated ...
```
