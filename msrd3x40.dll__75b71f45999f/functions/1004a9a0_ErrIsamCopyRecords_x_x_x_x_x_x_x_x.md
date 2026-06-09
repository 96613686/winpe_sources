# ErrIsamCopyRecords(x,x,x,x,x,x,x,x)

- ea: `0x1004a9a0`
- end: `0x1004b7f4`
- name: `_ErrIsamCopyRecords@32`
- size: `3668`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1000eb60`
- `0x1002d3b0`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x1004a650`
- `0x1004a9a0`
- `0x1005b1a0`
- `0x1005b290`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f4c1`

## pseudocode

```c
int __stdcall ErrIsamCopyRecords(
        void **a1,
        unsigned int a2,
        _DWORD *a3,
        _DWORD *a4,
        unsigned int a5,
        int a6,
        _DWORD *a7,
        int *a8)
{
  int v8; // eax
  int (__thiscall *v9)(_DWORD *); // esi
  _DWORD *v10; // edi
  int (__thiscall *v11)(_DWORD, void *, unsigned int, int *); // esi
  int v12; // ebx
  unsigned int v13; // ecx
  int *v14; // eax
  _DWORD *v15; // ebx
  _DWORD *v16; // eax
  char v17; // al
  unsigned int v18; // edx
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // edx
  int v22; // ecx
  int v23; // eax
  void *v24; // esi
  void *v25; // edi
  void *v26; // edi
  char v27; // al
  _DWORD *v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  _DWORD *v31; // edi
  char v32; // al
  char v33; // cl
  unsigned int v34; // eax
  unsigned int v35; // ecx
  wchar_t *v36; // edi
  int v37; // edx
  int v38; // ecx
  int v39; // esi
  int v40; // esi
  char v41; // al
  unsigned int v42; // edi
  _DWORD *v43; // ecx
  int v44; // eax
  int v45; // edi
  _DWORD *v46; // edi
  char v47; // al
  unsigned int v48; // eax
  unsigned int v49; // ecx
  wchar_t *v50; // eax
  int v51; // ecx
  char v52; // al
  void (__thiscall *v53)(_DWORD *, unsigned int, wchar_t *, int, _DWORD, unsigned int *); // esi
  unsigned int v54; // edi
  bool v55; // zf
  _DWORD *v56; // edi
  char v57; // al
  char v58; // cl
  unsigned int v59; // eax
  unsigned int v60; // ecx
  int v61; // eax
  int v62; // edi
  wchar_t *v63; // eax
  char v64; // al
  unsigned int v65; // eax
  int v66; // edi
  int v67; // eax
  char v68; // cl
  int v69; // eax
  char v70; // al
  Session *v71; // esi
  int v72; // eax
  int v73; // edi
  int v74; // edx
  void *v75; // ebx
  void *v76; // ecx
  int v78; // [esp+E4h] [ebp-8C0h]
  unsigned int v79; // [esp+FCh] [ebp-8A8h] BYREF
  _DWORD *v80; // [esp+100h] [ebp-8A4h]
  char v81[4]; // [esp+104h] [ebp-8A0h]
  _DWORD *v82; // [esp+108h] [ebp-89Ch]
  void *v83; // [esp+10Ch] [ebp-898h]
  wchar_t *Destination; // [esp+110h] [ebp-894h]
  unsigned int v85; // [esp+114h] [ebp-890h]
  int v86; // [esp+118h] [ebp-88Ch]
  unsigned int v87; // [esp+11Ch] [ebp-888h] BYREF
  int v88; // [esp+120h] [ebp-884h]
  int v89; // [esp+124h] [ebp-880h]
  void *v90; // [esp+128h] [ebp-87Ch]
  void *v91; // [esp+12Ch] [ebp-878h]
  int v92; // [esp+130h] [ebp-874h]
  Session *v93; // [esp+134h] [ebp-870h]
  unsigned int v94; // [esp+138h] [ebp-86Ch]
  int v95; // [esp+13Ch] [ebp-868h]
  _DWORD *v96; // [esp+140h] [ebp-864h]
  int v97; // [esp+144h] [ebp-860h]
  void *v98; // [esp+148h] [ebp-85Ch]
  int v99; // [esp+14Ch] [ebp-858h] BYREF
  unsigned int v100; // [esp+150h] [ebp-854h]
  _DWORD *v101; // [esp+154h] [ebp-850h]
  int v102; // [esp+158h] [ebp-84Ch]
  int *v103; // [esp+15Ch] [ebp-848h]
  int v104; // [esp+160h] [ebp-844h]
  int v105; // [esp+164h] [ebp-840h]
  int v106; // [esp+168h] [ebp-83Ch]
  int v107; // [esp+16Ch] [ebp-838h] BYREF
  int v108; // [esp+170h] [ebp-834h] BYREF
  int v109; // [esp+178h] [ebp-82Ch]
  void *v110; // [esp+17Ch] [ebp-828h]
  void *v111; // [esp+180h] [ebp-824h]
  int v112; // [esp+188h] [ebp-81Ch] BYREF
  int v113; // [esp+18Ch] [ebp-818h]
  int v114; // [esp+190h] [ebp-814h]
  void *Block; // [esp+194h] [ebp-810h]
  void *v116; // [esp+198h] [ebp-80Ch]
  _DWORD v117[513]; // [esp+19Ch] [ebp-808h] BYREF

  v93 = (Session *)a1;
  v101 = a7;
  v103 = a8;
  v102 = 0;
  v97 = 0;
  v8 = *a3;
  v105 = 0;
  v9 = *(int (__thiscall **)(_DWORD *))(v8 + 60);
  v10 = a4;
  v80 = a3;
  v87 = 1;
  v100 = 256;
  v94 = 0;
  v104 = -2;
  v96 = (_DWORD *)v9(a3);
  v86 = 0;
  v83 = a1[53];
  v106 = 0;
  v11 = *(int (__thiscall **)(_DWORD, void *, unsigned int, int *))(pJetInfoBlock + 52);
  *(_DWORD *)v81 = 0;
  v12 = v11(v11, v83, a2, &v99);
  v92 = v12;
  if ( v12 < 0 )
  {
    v80[84] = 1;
    goto LABEL_227;
  }
  v13 = a5;
  if ( (char *)v99 == &vtfndefIsam || (char *)v99 == &vtfndefIsamILB )
  {
    v12 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, int *))(pJetInfoBlock + 28))(
            *(_DWORD *)(pJetInfoBlock + 28),
            v83,
            a2,
            &v107);
    v92 = v12;
    if ( v12 < 0 )
      goto LABEL_223;
    v13 = a5;
    if ( a5 == 1 && *a4 == -1 )
    {
      v12 = ErrIsamCopyBookmarks(v93, v107, v80, a4[1], a6, v101, v103);
      goto LABEL_223;
    }
  }
  if ( v101 )
  {
    v14 = v103;
    if ( v103 )
    {
      if ( *v101 == 134420849 && *v103 == 101718388 )
      {
        *v101 = 0;
        *(_DWORD *)v81 = 1;
        *v14 = 0;
      }
    }
  }
  v95 = 0;
  if ( !v13 )
    goto LABEL_27;
  v15 = v80;
  do
  {
    if ( *v10 == -1 )
      goto LABEL_23;
    if ( *((unsigned __int8 *)v10 + 4) == 255 )
      v16 = 0;
    else
      v16 = (_DWORD *)v96[*((unsigned __int8 *)v10 + 4) + 94];
    v82 = v16;
    v17 = (*(int (__thiscall **)(_DWORD *))(*v16 + 16))(v16);
    if ( v17 != 12 && v17 != 11 )
    {
      if ( (v82[12] & 2) != 0 )
      {
        v104 = v10[1];
        v15[84] = 0;
      }
LABEL_23:
      v18 = v94;
      v19 = v10[1];
      v117[2 * v94] = *v10;
      v117[2 * v18 + 1] = v19;
      v94 = v18 + 1;
      goto LABEL_25;
    }
    v20 = *v10;
    v21 = v100 - 1;
    v22 = v10[1];
    v100 = v21;
    v117[2 * v21] = v20;
    v117[2 * v21 + 1] = v22;
LABEL_25:
    v10 += 2;
    ++v95;
  }
  while ( v95 < a5 );
  v12 = v92;
LABEL_27:
  Destination = (wchar_t *)operator new[](0x2000u);
  v95 = a6;
  if ( a6 >= 0 )
  {
    v99 = 1;
  }
  else
  {
    v99 = -1;
    if ( a6 == 0x80000000 )
      v95 = 0x7FFFFFFF;
    else
      v95 = -a6;
  }
  if ( *(_DWORD *)(*(_DWORD *)((*(int (__thiscall **)(_DWORD *))(*v80 + 56))(v80) + 16) + 68) != 1 )
  {
    v112 = 1;
    Session::BeginTransaction(v93, 1, &v112);
    v23 = v112;
    v24 = v116;
    v25 = Block;
    if ( (v112 & 1) != 0 )
    {
      v12 = 0;
    }
    else
    {
      if ( (v112 & 8) != 0 && v114 )
      {
        (*(void (__thiscall **)(_DWORD, Session *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
          *(_DWORD *)(pJetInfoBlock + 44),
          v93,
          Block,
          v116,
          0,
          v114,
          0,
          0,
          0);
        v24 = v116;
        v23 = v112;
      }
      v12 = v113;
    }
    if ( (v23 & 0xFFFFFFFE) != 0 )
    {
      if ( v25 )
        operator delete[](v25);
      if ( v24 )
        operator delete[](v24);
    }
    if ( v12 < 0 )
      goto LABEL_222;
    v106 = 1;
  }
  v26 = v83;
  while ( 2 )
  {
    (*(void (__thiscall **)(_DWORD *, _DWORD, unsigned int *))(*v80 + 20))(v80, 0, &v87);
    v27 = v87;
    if ( (v87 & 8) != 0 )
    {
      if ( (v87 & 1) != 0 )
      {
        v12 = 0;
      }
      else
      {
        if ( v89 && v26 )
        {
          (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
            *(_DWORD *)(pJetInfoBlock + 44),
            v26,
            v90,
            v91,
            0,
            v89,
            0,
            0,
            0);
          v27 = v87;
        }
        v12 = v88;
        if ( (v27 & 1) != 0 )
          v12 = 0;
      }
      goto LABEL_173;
    }
    v28 = v117;
    v85 = 0;
    v82 = v117;
    if ( !v94 )
      goto LABEL_80;
    while ( 2 )
    {
      if ( *v28 == -1 )
        v29 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, wchar_t *, int, unsigned int *))(pJetInfoBlock + 4))(
                *(_DWORD *)(pJetInfoBlock + 4),
                v83,
                a2,
                Destination,
                0x2000,
                &v79);
      else
        v29 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, _DWORD, wchar_t *, int, unsigned int *, _DWORD, _DWORD))(pJetInfoBlock + 24))(
                *(_DWORD *)(pJetInfoBlock + 24),
                v83,
                a2,
                *v28,
                Destination,
                0x2000,
                &v79,
                0,
                0);
      v12 = v29;
      if ( v29 < 0 )
      {
        if ( !*(_DWORD *)v81 )
          goto LABEL_173;
        v30 = *((unsigned __int8 *)v28 + 4);
        if ( v30 >= 0xFF )
          v31 = 0;
        else
          v31 = (_DWORD *)v96[v30 + 94];
        v32 = (*(int (__thiscall **)(_DWORD *))(*v31 + 16))(v31);
        v33 = v32;
        v86 = v12;
        v12 = 0;
        if ( v32 == 12 || v32 == 10 )
        {
          v79 = 32;
          v34 = 32;
          if ( v33 == 10 )
          {
            v35 = v31[5];
            if ( v35 < 0x20 )
            {
              v79 = v31[5];
              v34 = v35;
            }
          }
          wcsncpy(Destination, L"################", v34 >> 1);
LABEL_63:
          v36 = Destination;
          v37 = 32;
          goto LABEL_64;
        }
        goto LABEL_79;
      }
      if ( v29 != 1004 )
        goto LABEL_63;
      v36 = 0;
      v37 = 0;
LABEL_64:
      v92 = v37;
      v38 = v82[1];
      if ( v38 == v104 && v36 )
      {
        v39 = v97;
        if ( *(_DWORD *)v36 > v97 )
          v39 = *(_DWORD *)v36;
        v97 = v39;
      }
      v40 = *v80;
      v98 = (void *)(unsigned __int8)v38;
      (*(void (__thiscall **)(_DWORD *, _DWORD, wchar_t *, unsigned int, int, unsigned int *))(v40 + 100))(
        v80,
        (unsigned __int8)v38,
        v36,
        v79,
        v37,
        &v87);
      v41 = v87;
      if ( (v87 & 1) == 0 && v88 == -1047 && v79 == 2 )
      {
        if ( (v87 & 0xFFFFFFFE) != 0 )
        {
          if ( v90 )
            operator delete[](v90);
          if ( v91 )
            operator delete[](v91);
        }
        v87 = 1;
        *(_DWORD *)Destination = (__int16)*Destination;
        v79 = 4;
        (*(void (__thiscall **)(_DWORD *, void *, wchar_t *, int, int, unsigned int *))(*v80 + 100))(
          v80,
          v98,
          v36,
          4,
          v92,
          &v87);
        v41 = v87;
      }
      if ( (v41 & 8) == 0 )
      {
LABEL_79:
        v28 = v82 + 2;
        ++v85;
        v82 += 2;
        if ( v85 >= v94 )
          goto LABEL_80;
        continue;
      }
      break;
    }
    if ( (v41 & 1) != 0 )
    {
      v12 = 0;
    }
    else
    {
      if ( v89 && v83 )
      {
        (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
          *(_DWORD *)(pJetInfoBlock + 44),
          v83,
          v90,
          v91,
          0,
          v89,
          0,
          0,
          0);
        v41 = v87;
      }
      v12 = v88;
      if ( (v41 & 1) != 0 )
        v12 = 0;
    }
    if ( *(_DWORD *)v81 )
    {
      v86 = v12;
      goto LABEL_81;
    }
LABEL_80:
    if ( v12 < 0 )
      goto LABEL_173;
LABEL_81:
    v42 = v100;
    v85 = v100;
    v43 = &v117[2 * v100];
    v82 = v43;
    if ( v100 >= 0x100 )
      goto LABEL_134;
    while ( 2 )
    {
      v44 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, _DWORD, wchar_t *, int, unsigned int *, _DWORD, _DWORD))(pJetInfoBlock + 24))(
              *(_DWORD *)(pJetInfoBlock + 24),
              v83,
              a2,
              *v43,
              Destination,
              0x2000,
              &v79,
              0,
              0);
      v12 = v44;
      if ( v44 < 0 )
      {
        v45 = *(_DWORD *)v81;
        if ( !*(_DWORD *)v81 )
          goto LABEL_174;
        if ( *((unsigned __int8 *)v82 + 4) == 255 )
          v46 = 0;
        else
          v46 = (_DWORD *)v96[*((unsigned __int8 *)v82 + 4) + 94];
        v47 = (*(int (__thiscall **)(_DWORD *))(*v46 + 16))(v46);
        v86 = v12;
        v12 = 0;
        if ( v47 == 12 )
        {
          v79 = 32;
          v48 = 32;
          goto LABEL_103;
        }
        if ( v47 == 10 )
        {
          v79 = 32;
          v48 = 32;
          v49 = v46[5];
          if ( v49 < 0x20 )
          {
            v79 = v46[5];
            v48 = v49;
          }
LABEL_103:
          wcsncpy(Destination, L"################", v48 >> 1);
          v42 = v85;
LABEL_104:
          v50 = Destination;
          v51 = 32;
          goto LABEL_105;
        }
LABEL_130:
        v42 = v85;
        goto LABEL_131;
      }
      if ( v44 != 1006 )
      {
        if ( v44 != 1004 )
          goto LABEL_104;
        v50 = 0;
        v51 = 0;
LABEL_105:
        (*(void (__thiscall **)(_DWORD *, _DWORD, wchar_t *, unsigned int, int, unsigned int *))(*v80 + 100))(
          v80,
          *((unsigned __int8 *)v82 + 4),
          v50,
          v79,
          v51,
          &v87);
        v52 = v87;
        if ( (v87 & 8) != 0 )
          break;
        goto LABEL_131;
      }
      v92 = 1;
      v53 = *(void (__thiscall **)(_DWORD *, unsigned int, wchar_t *, int, _DWORD, unsigned int *))(*v80 + 100);
      v54 = (unsigned __int8)v82[1];
      v98 = (void *)v54;
      v53(v80, v54, Destination, 0x2000, 0, &v87);
      v52 = v87;
      if ( (v87 & 8) == 0 )
      {
        v55 = v79 == 0x2000;
        v112 = 16;
        v113 = 0x2000;
        v114 = 0;
        Block = 0;
        v79 -= 0x2000;
        if ( v55 )
          goto LABEL_130;
        while ( 1 )
        {
          v12 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, _DWORD, wchar_t *, int, unsigned int *, _DWORD, int *))(pJetInfoBlock + 24))(
                  *(_DWORD *)(pJetInfoBlock + 24),
                  v83,
                  a2,
                  *v82,
                  Destination,
                  0x2000,
                  &v79,
                  0,
                  &v112);
          if ( v12 >= 0 )
          {
            v61 = v92;
          }
          else
          {
            if ( !*(_DWORD *)v81 )
              goto LABEL_130;
            v56 = v54 >= 0xFF ? 0 : (_DWORD *)v96[v54 + 94];
            v57 = (*(int (__thiscall **)(_DWORD *))(*v56 + 16))(v56);
            v58 = v57;
            v86 = v12;
            v12 = 0;
            if ( v57 != 12 && v57 != 10 )
              goto LABEL_130;
            v79 = 32;
            v59 = 32;
            if ( v58 == 10 )
            {
              v60 = v56[5];
              if ( v60 < 0x20 )
              {
                v79 = v56[5];
                v59 = v60;
              }
            }
            wcsncpy(Destination, L"################", v59 >> 1);
            v61 = 0;
            v92 = 0;
          }
          v62 = v79;
          if ( v79 > 0x2000 )
            v62 = 0x2000;
          v78 = v61;
          v63 = Destination;
          if ( !v62 )
            v63 = 0;
          (*(void (__thiscall **)(_DWORD *, void *, wchar_t *, int, int, unsigned int *))(*v80 + 100))(
            v80,
            v98,
            v63,
            v62,
            v78,
            &v87);
          v64 = v87;
          if ( (v87 & 8) != 0 )
            break;
          if ( v92 )
          {
            v113 += v62;
            v65 = v79 - v62;
            v54 = (unsigned int)v98;
            v79 = v65;
            if ( v65 )
              continue;
          }
          goto LABEL_130;
        }
        if ( (v87 & 1) != 0 )
        {
          v12 = 0;
        }
        else
        {
          if ( v89 && v83 )
          {
            (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
              *(_DWORD *)(pJetInfoBlock + 44),
              v83,
              v90,
              v91,
              0,
              v89,
              0,
              0,
              0);
            v64 = v87;
          }
          v12 = v88;
          if ( (v64 & 1) != 0 )
            v12 = 0;
        }
        v42 = v85;
        if ( *(_DWORD *)v81 )
        {
          v86 = v12;
          v12 = 0;
        }
LABEL_131:
        ++v42;
        v43 = v82 + 2;
        v85 = v42;
        v82 += 2;
        if ( v42 >= 0x100 )
        {
          v45 = *(_DWORD *)v81;
          goto LABEL_133;
        }
        continue;
      }
      break;
    }
    if ( (v52 & 1) != 0 )
    {
      v12 = 0;
    }
    else
    {
      if ( v89 && v83 )
      {
        (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
          *(_DWORD *)(pJetInfoBlock + 44),
          v83,
          v90,
          v91,
          0,
          v89,
          0,
          0,
          0);
        v52 = v87;
      }
      v12 = v88;
      if ( (v52 & 1) != 0 )
        v12 = 0;
    }
    v45 = *(_DWORD *)v81;
    if ( *(_DWORD *)v81 )
    {
      v66 = v12;
      v86 = v12;
      goto LABEL_135;
    }
LABEL_133:
    if ( v12 < 0 )
      goto LABEL_174;
LABEL_134:
    v66 = v86;
LABEL_135:
    v67 = (*(int (__thiscall **)(_DWORD *, unsigned int *))(*v80 + 28))(v80, &v87);
    v68 = v87;
    v105 = v67;
    if ( (v87 & 1) != 0 )
    {
      v12 = 0;
LABEL_162:
      if ( ++v102 >= v95 )
        goto LABEL_173;
      if ( v66 < 0 )
        goto LABEL_173;
      v26 = v83;
      v12 = (*(int (__thiscall **)(_DWORD, void *, unsigned int, int, _DWORD))(pJetInfoBlock + 76))(
              *(_DWORD *)(pJetInfoBlock + 76),
              v83,
              a2,
              v99,
              0);
      if ( v12 < 0 )
        goto LABEL_173;
      continue;
    }
    break;
  }
  if ( (v87 & 8) != 0 && v89 && v83 )
  {
    (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
      *(_DWORD *)(pJetInfoBlock + 44),
      v83,
      v90,
      v91,
      0,
      v89,
      0,
      0,
      0);
    v68 = v87;
  }
  if ( (v68 & 1) != 0 )
  {
    v12 = 0;
    goto LABEL_162;
  }
  v12 = v88;
  if ( v88 >= 0 )
    goto LABEL_162;
LABEL_173:
  v45 = *(_DWORD *)v81;
LABEL_174:
  if ( !v97 )
    goto LABEL_188;
  if ( v12 >= 0 || v12 == -1603 )
  {
    v69 = (*(int (__thiscall **)(_DWORD *))(*v80 + 56))(v80);
    v113 = 0;
    v55 = v96[12] == 2;
    v112 = v96[10];
    v114 = 0;
    if ( v55 )
      TblPage::NextRecordNumber(&v112, v69, &v87, v97, 0);
    else
      TblPage::NextRecordNumber(&v112, v96[9], &v87, v97, 0);
    v70 = v87;
    if ( (v87 & 1) != 0 )
    {
      v12 = 0;
      goto LABEL_190;
    }
    if ( (v87 & 8) != 0 && v89 && v83 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        v83,
        v90,
        v91,
        0,
        v89,
        0,
        0,
        0);
      v70 = v87;
    }
    v12 = v88;
    if ( (v70 & 1) != 0 )
      v12 = 0;
LABEL_188:
    if ( v12 >= 0 || v12 == -1603 )
    {
LABEL_190:
      if ( v101 )
        *v101 = v102;
      if ( v103 )
        *v103 = v105;
    }
  }
  if ( v106 )
  {
    if ( v12 >= 0 || v12 == -1603 || v45 )
    {
      v71 = v93;
      v112 = 1;
      Session::CommitTransaction(v93, (void **)&v112, 0);
      v72 = v112;
      if ( (v112 & 1) != 0 )
      {
        v73 = 0;
      }
      else
      {
        if ( (v112 & 8) != 0 && v114 )
        {
          (*(void (__thiscall **)(_DWORD, Session *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
            *(_DWORD *)(pJetInfoBlock + 44),
            v93,
            Block,
            v116,
            0,
            v114,
            0,
            0,
            0);
          v72 = v112;
          v71 = v93;
        }
        v73 = v113;
        if ( (v72 & 1) != 0 )
          v73 = 0;
      }
      if ( (v72 & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v116 )
          operator delete[](v116);
      }
      if ( v73 < 0 )
      {
        v108 = 1;
        Session::AbortTransaction(v71, (struct Err *)&v108);
        v74 = v108;
        v75 = v111;
        v76 = v110;
        if ( (v108 & 9) == 8 && (v108 & 1) == 0 && v109 )
        {
          (*(void (__thiscall **)(_DWORD, Session *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
            *(_DWORD *)(pJetInfoBlock + 44),
            v93,
            v110,
            v111,
            0,
            v109,
            0,
            0,
            0);
          v76 = v110;
          v74 = v108;
        }
        if ( (v74 & 0xFFFFFFFE) != 0 )
        {
          if ( v76 )
            operator delete[](v76);
          if ( v75 )
            operator delete[](v75);
        }
        v12 = v73;
        v86 = 0;
      }
    }
    else
    {
      ErrIsamRollback(v93, 0);
    }
  }
LABEL_222:
  operator delete[](Destination);
LABEL_223:
  v80[84] = 1;
  if ( v12 >= 0 && v86 < 0 )
    v12 = v86;
LABEL_227:
  if ( (v87 & 0xFFFFFFFE) != 0 )
  {
    if ( v90 )
      operator delete[](v90);
    if ( v91 )
      operator delete[](v91);
  }
  return v12;
}

```

## disassembly

```asm
0x1004a9a0  mov     edi, edi
0x1004a9a2  push    ebp
0x1004a9a3  mov     ebp, esp
0x1004a9a5  and     esp, 0FFFFFFF8h
0x1004a9a8  sub     esp, 8ACh
0x1004a9ae  mov     eax, ___security_cookie
0x1004a9b3  xor     eax, esp
0x1004a9b5  mov     [esp+8ACh+var_4], eax
0x1004a9bc  mov     eax, [ebp+arg_0]
0x1004a9bf  xor     ecx, ecx
0x1004a9c1  mov     [esp+8ACh+var_870], eax
0x1004a9c5  mov     eax, [ebp+arg_18]
0x1004a9c8  push    ebx
0x1004a9c9  mov     ebx, [ebp+arg_8]
0x1004a9cc  mov     [esp+8B0h+var_850], eax
0x1004a9d0  mov     eax, [ebp+arg_1C]
0x1004a9d3  mov     [esp+8B0h+var_848], eax
0x1004a9d7  xor     eax, eax
0x1004a9d9  mov     [esp+8B0h+var_84C], eax
0x1004a9dd  mov     [esp+8B0h+var_860], eax
0x1004a9e1  mov     eax, [ebx]
0x1004a9e3  push    esi; unsigned int
0x1004a9e4  mov     [esp+8B4h+var_840], ecx
0x1004a9e8  push    edi; void *
0x1004a9e9  mov     esi, [eax+3Ch]
0x1004a9ec  mov     ecx, esi
0x1004a9ee  mov     edi, [ebp+arg_C]
0x1004a9f1  mov     [esp+8B8h+var_8A4], ebx
0x1004a9f5  mov     [esp+8B8h+var_888], 1
0x1004a9fd  mov     [esp+8B8h+var_854], 100h
0x1004aa05  mov     [esp+8B8h+var_86C], 0
0x1004aa0d  mov     [esp+8B8h+var_844], 0FFFFFFFEh
0x1004aa15  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004aa1b  mov     ecx, ebx
0x1004aa1d  call    esi
0x1004aa1f  mov     ecx, [esp+8B8h+var_870]
0x1004aa23  mov     [esp+8B8h+var_864], eax
0x1004aa27  xor     eax, eax
0x1004aa29  mov     [esp+8B8h+var_88C], eax
0x1004aa2d  mov     eax, _pJetInfoBlock
0x1004aa32  mov     ecx, [ecx+0D4h]
0x1004aa38  mov     [esp+8B8h+var_898], ecx
0x1004aa3c  mov     [esp+8B8h+var_83C], 0
0x1004aa44  mov     esi, [eax+34h]
0x1004aa47  lea     eax, [esp+8B8h+var_858]
0x1004aa4b  push    eax
0x1004aa4c  push    [ebp+arg_4]; unsigned int
0x1004aa4f  mov     dword ptr [esp+8C0h+var_8A0], 0
0x1004aa57  push    ecx; void *
0x1004aa58  mov     ecx, esi
0x1004aa5a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004aa60  call    esi
0x1004aa62  mov     ebx, eax
0x1004aa64  mov     [esp+8B8h+var_874], eax
0x1004aa68  test    ebx, ebx
0x1004aa6a  js      loc_1004B7A1
0x1004aa70  mov     eax, [esp+8B8h+var_858]
0x1004aa74  mov     ecx, [ebp+arg_10]
0x1004aa77  cmp     eax, offset _vtfndefIsam
0x1004aa7c  jz      short loc_1004AA85
0x1004aa7e  cmp     eax, offset _vtfndefIsamILB
0x1004aa83  jnz     short loc_1004AAEC
0x1004aa85  mov     eax, _pJetInfoBlock
0x1004aa8a  mov     esi, [eax+1Ch]
0x1004aa8d  lea     eax, [esp+8B8h+var_838]
0x1004aa94  push    eax
0x1004aa95  push    [ebp+arg_4]; unsigned int
0x1004aa98  mov     ecx, esi
0x1004aa9a  push    [esp+8C0h+var_898]; void *
0x1004aa9e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004aaa4  call    esi
0x1004aaa6  mov     ebx, eax
0x1004aaa8  mov     [esp+8B8h+var_874], ebx
0x1004aaac  test    ebx, ebx
0x1004aaae  js      loc_1004B783
0x1004aab4  mov     ecx, [ebp+arg_10]
0x1004aab7  cmp     ecx, 1
0x1004aaba  jnz     short loc_1004AAEC
0x1004aabc  cmp     dword ptr [edi], 0FFFFFFFFh
0x1004aabf  jnz     short loc_1004AAEC
0x1004aac1  push    [esp+8B8h+var_848]
0x1004aac5  mov     ecx, [esp+8BCh+var_850]
0x1004aac9  mov     esi, [esp+8BCh+var_8A4]
0x1004aacd  mov     edx, [esp+8BCh+var_838]
0x1004aad4  push    ecx
0x1004aad5  push    [ebp+arg_14]
0x1004aad8  mov     ecx, [esp+8C4h+var_870]
0x1004aadc  push    dword ptr [edi+4]
0x1004aadf  push    esi
0x1004aae0  call    ErrIsamCopyBookmarks
0x1004aae5  mov     ebx, eax
0x1004aae7  jmp     loc_1004B783
0x1004aaec  mov     edx, [esp+8B8h+var_850]
0x1004aaf0  test    edx, edx
0x1004aaf2  jz      short loc_1004AB20
0x1004aaf4  mov     eax, [esp+8B8h+var_848]
0x1004aaf8  test    eax, eax
0x1004aafa  jz      short loc_1004AB20
0x1004aafc  cmp     dword ptr [edx], 8031971h
0x1004ab02  jnz     short loc_1004AB20
0x1004ab04  cmp     dword ptr [eax], 6101974h
0x1004ab0a  jnz     short loc_1004AB20
0x1004ab0c  mov     dword ptr [edx], 0
0x1004ab12  mov     dword ptr [esp+8B8h+var_8A0], 1
0x1004ab1a  mov     dword ptr [eax], 0
0x1004ab20  mov     [esp+8B8h+var_868], 0
0x1004ab28  test    ecx, ecx
0x1004ab2a  jz      loc_1004ABE0
0x1004ab30  mov     ebx, [esp+8B8h+var_8A4]
0x1004ab34  cmp     dword ptr [edi], 0FFFFFFFFh
0x1004ab37  jz      short loc_1004AB8D
0x1004ab39  movzx   eax, byte ptr [edi+4]
0x1004ab3d  cmp     eax, 0FFh
0x1004ab42  jnb     short loc_1004AB51
0x1004ab44  mov     ecx, [esp+8B8h+var_864]
0x1004ab48  mov     eax, [ecx+eax*4+178h]
0x1004ab4f  jmp     short loc_1004AB53
0x1004ab51  xor     eax, eax
0x1004ab53  mov     [esp+8B8h+var_89C], eax
0x1004ab57  mov     eax, [eax]
0x1004ab59  mov     esi, [eax+10h]
0x1004ab5c  mov     ecx, esi
0x1004ab5e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ab64  mov     ecx, [esp+8B8h+var_89C]
0x1004ab68  call    esi
0x1004ab6a  cmp     al, 0Ch
0x1004ab6c  jz      short loc_1004ABAB
0x1004ab6e  cmp     al, 0Bh
0x1004ab70  jz      short loc_1004ABAB
0x1004ab72  mov     eax, [esp+8B8h+var_89C]
0x1004ab76  test    byte ptr [eax+30h], 2
0x1004ab7a  jz      short loc_1004AB8D
0x1004ab7c  mov     eax, [edi+4]
0x1004ab7f  mov     [esp+8B8h+var_844], eax
0x1004ab83  mov     dword ptr [ebx+150h], 0
0x1004ab8d  mov     edx, [esp+8B8h+var_86C]
0x1004ab91  mov     eax, [edi]
0x1004ab93  mov     ecx, [edi+4]
0x1004ab96  mov     [esp+edx*8+8B8h+var_808], eax
0x1004ab9d  mov     [esp+edx*8+8B8h+var_804], ecx
0x1004aba4  inc     edx
0x1004aba5  mov     [esp+8B8h+var_86C], edx
0x1004aba9  jmp     short loc_1004ABC7
0x1004abab  mov     edx, [esp+8B8h+var_854]
0x1004abaf  mov     eax, [edi]
0x1004abb1  dec     edx
0x1004abb2  mov     ecx, [edi+4]
0x1004abb5  mov     [esp+8B8h+var_854], edx
0x1004abb9  mov     [esp+edx*8+8B8h+var_808], eax
0x1004abc0  mov     [esp+edx*8+8B8h+var_804], ecx
0x1004abc7  mov     eax, [esp+8B8h+var_868]
0x1004abcb  add     edi, 8
0x1004abce  inc     eax
0x1004abcf  mov     [esp+8B8h+var_868], eax
0x1004abd3  cmp     eax, [ebp+arg_10]
0x1004abd6  jb      loc_1004AB34
0x1004abdc  mov     ebx, [esp+8B8h+var_874]
0x1004abe0  push    2000h; unsigned int
0x1004abe5  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004abea  mov     [esp+8BCh+Destination], eax
0x1004abee  add     esp, 4
0x1004abf1  mov     eax, [ebp+arg_14]
0x1004abf4  mov     [esp+8B8h+var_868], eax
0x1004abf8  test    eax, eax
0x1004abfa  jns     short loc_1004AC1D
0x1004abfc  mov     [esp+8B8h+var_858], 0FFFFFFFFh
0x1004ac04  cmp     eax, 80000000h
0x1004ac09  jnz     short loc_1004AC15
0x1004ac0b  mov     [esp+8B8h+var_868], 7FFFFFFFh
0x1004ac13  jmp     short loc_1004AC25
0x1004ac15  neg     eax
0x1004ac17  mov     [esp+8B8h+var_868], eax
0x1004ac1b  jmp     short loc_1004AC25
0x1004ac1d  mov     [esp+8B8h+var_858], 1
0x1004ac25  mov     edi, [esp+8B8h+var_8A4]
0x1004ac29  mov     eax, [edi]
0x1004ac2b  mov     esi, [eax+38h]
0x1004ac2e  mov     ecx, esi
0x1004ac30  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ac36  mov     ecx, edi
0x1004ac38  call    esi
0x1004ac3a  mov     eax, [eax+10h]
0x1004ac3d  cmp     dword ptr [eax+44h], 1
0x1004ac41  jz      loc_1004ACFD
0x1004ac47  mov     ebx, [esp+8B8h+var_870]
0x1004ac4b  lea     eax, [esp+8B8h+var_81C]
0x1004ac52  push    eax
0x1004ac53  push    1
0x1004ac55  mov     ecx, ebx
0x1004ac57  mov     [esp+8C0h+var_81C], 1
0x1004ac62  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x1004ac67  mov     eax, [esp+8B8h+var_81C]
0x1004ac6e  mov     esi, [esp+8B8h+var_80C]
0x1004ac75  mov     edi, [esp+8B8h+Block]
0x1004ac7c  test    al, 1
0x1004ac7e  jz      short loc_1004AC84
0x1004ac80  xor     ebx, ebx
0x1004ac82  jmp     short loc_1004ACCC
0x1004ac84  test    al, 8
0x1004ac86  jz      short loc_1004ACC5
0x1004ac88  mov     ecx, [esp+8B8h+var_814]
0x1004ac8f  test    ecx, ecx
0x1004ac91  jz      short loc_1004ACC5
0x1004ac93  mov     eax, _pJetInfoBlock
0x1004ac98  push    0
0x1004ac9a  push    0
0x1004ac9c  push    0
0x1004ac9e  mov     esi, [eax+2Ch]
0x1004aca1  push    ecx
0x1004aca2  push    0
0x1004aca4  push    [esp+8CCh+var_80C]
0x1004acab  mov     ecx, esi
0x1004acad  push    edi; unsigned int
0x1004acae  push    ebx; void *
0x1004acaf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004acb5  call    esi
0x1004acb7  mov     esi, [esp+8B8h+var_80C]
0x1004acbe  mov     eax, [esp+8B8h+var_81C]
0x1004acc5  mov     ebx, [esp+8B8h+var_818]
0x1004accc  test    eax, 0FFFFFFFEh
0x1004acd1  jz      short loc_1004ACED
0x1004acd3  test    edi, edi
0x1004acd5  jz      short loc_1004ACE0
0x1004acd7  push    edi; Block
0x1004acd8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004acdd  add     esp, 4
0x1004ace0  test    esi, esi
0x1004ace2  jz      short loc_1004ACED
0x1004ace4  push    esi; Block
0x1004ace5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004acea  add     esp, 4
0x1004aced  test    ebx, ebx
0x1004acef  js      loc_1004B777
0x1004acf5  mov     [esp+8B8h+var_83C], 1
0x1004acfd  mov     edi, [esp+8B8h+var_898]
0x1004ad01  mov     eax, [esp+8B8h+var_8A4]
0x1004ad05  lea     ecx, [esp+8B8h+var_888]
0x1004ad09  push    ecx; unsigned int
0x1004ad0a  push    0; void *
0x1004ad0c  mov     eax, [eax]
0x1004ad0e  mov     esi, [eax+14h]
0x1004ad11  mov     ecx, esi
0x1004ad13  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ad19  mov     ecx, [esp+8C0h+var_8A4]
0x1004ad1d  call    esi
0x1004ad1f  mov     eax, [esp+8B8h+var_888]
0x1004ad23  test    al, 8
0x1004ad25  jnz     loc_1004B496
0x1004ad2b  cmp     [esp+8B8h+var_86C], 0
0x1004ad30  lea     edi, [esp+8B8h+var_808]
0x1004ad37  mov     [esp+8B8h+var_890], 0
0x1004ad3f  mov     [esp+8B8h+var_89C], edi
0x1004ad43  jbe     loc_1004AF32
0x1004ad49  nop     dword ptr [eax+00000000h]
0x1004ad50  mov     ecx, [edi]
0x1004ad52  mov     eax, _pJetInfoBlock
0x1004ad57  cmp     ecx, 0FFFFFFFFh
0x1004ad5a  jnz     short loc_1004AD80
0x1004ad5c  mov     esi, [eax+4]
0x1004ad5f  lea     eax, [esp+8B8h+var_8A8]
0x1004ad63  push    eax
0x1004ad64  push    2000h
0x1004ad69  push    [esp+8C0h+Destination]
0x1004ad6d  mov     ecx, esi
0x1004ad6f  push    [ebp+arg_4]; unsigned int
0x1004ad72  push    [esp+8C8h+var_898]; void *
0x1004ad76  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ad7c  call    esi
0x1004ad7e  jmp     short loc_1004ADA7
0x1004ad80  mov     esi, [eax+18h]
0x1004ad83  lea     eax, [esp+8B8h+var_8A8]
0x1004ad87  push    0
0x1004ad89  push    0
0x1004ad8b  push    eax
0x1004ad8c  push    2000h
0x1004ad91  push    [esp+8C8h+Destination]
0x1004ad95  push    ecx
0x1004ad96  push    [ebp+arg_4]; unsigned int
0x1004ad99  mov     ecx, esi
0x1004ad9b  push    [esp+8D4h+var_898]; void *
0x1004ad9f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ada5  call    esi
0x1004ada7  mov     ebx, eax
0x1004ada9  test    ebx, ebx
0x1004adab  jns     loc_1004AFC4
0x1004adb1  cmp     dword ptr [esp+8B8h+var_8A0], 0
0x1004adb6  jz      loc_1004B4E0
0x1004adbc  movzx   edi, byte ptr [edi+4]
0x1004adc0  cmp     edi, 0FFh
0x1004adc6  jnb     short loc_1004ADD5
0x1004adc8  mov     eax, [esp+8B8h+var_864]
0x1004adcc  mov     edi, [eax+edi*4+178h]
0x1004add3  jmp     short loc_1004ADD7
0x1004add5  xor     edi, edi
0x1004add7  mov     eax, [edi]
0x1004add9  mov     esi, [eax+10h]
0x1004addc  mov     ecx, esi
0x1004adde  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004ade4  mov     ecx, edi
0x1004ade6  call    esi
  ... truncated ...
```
