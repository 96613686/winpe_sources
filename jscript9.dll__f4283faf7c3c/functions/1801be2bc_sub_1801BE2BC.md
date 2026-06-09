# sub_1801BE2BC

- ea: `0x1801be2bc`
- end: `0x1801bf710`
- name: `sub_1801BE2BC`
- size: `5204`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, __int64, char, char, int)`
- caller_count: `3`
- callee_count: `28`
- tags: `loader_planting`

## callers

- `0x1801bd7b8`
- `0x1801c1394`
- `0x1802467fc`

## callees

- `0x180016010`
- `0x1800194d0`
- `0x180021e18`
- `0x180022508`
- `0x180054858`
- `0x18005f188`
- `0x180068c64`
- `0x1801524a4`
- `0x1801a8a70`
- `0x1801baa4c`
- `0x1801be2bc`
- `0x1801c09d0`
- `0x1801c1604`
- `0x1801c5558`
- `0x180225494`
- `0x1802262d4`
- `0x18022c278`
- `0x180239204`
- `0x1802456bc`
- `0x18024575c`
- `0x180245b14`
- `0x180245b58`
- `0x1802461e4`
- `0x180246634`
- `0x1802b1ae0`
- `0x1803012a0`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1801be3a7`
- `msvcrt!wcsstr` at `0x1801be3c1`
- `msvcrt!wcsstr` at `0x1801be3a7`
- `msvcrt!wcsstr` at `0x1801be3c1`
- `KERNEL32!LoadLibraryExW` at `0x1801be352`
- `KERNEL32!LoadLibraryExW` at `0x1801be352`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_1801BE2BC(__int64 a1, _QWORD *a2, int a3, __int64 a4, char a5, char a6, int a7)
{
  __int64 v11; // rax
  __int64 v12; // rbx
  const WCHAR *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  const wchar_t *v16; // rbx
  _QWORD *v17; // r14
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  int v20; // ebx
  int v21; // ebx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // ebx
  __int64 v25; // rbx
  int v26; // ebx
  __int64 v27; // rbx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  __int64 v33; // rdx
  int v34; // ebx
  int v35; // ebx
  int v36; // ebx
  __int64 v37; // r8
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  int v42; // eax
  int v43; // ebx
  int v44; // eax
  int v45; // ebx
  int v46; // eax
  int v47; // ebx
  int v48; // eax
  int v49; // ebx
  int v50; // eax
  int v51; // ebx
  int v52; // eax
  int v53; // ebx
  int v54; // eax
  int v55; // ebx
  int v56; // eax
  int v57; // ebx
  int v58; // eax
  int v59; // ebx
  int v60; // eax
  int v61; // ebx
  int v62; // eax
  int v63; // ebx
  int v64; // eax
  int v65; // ebx
  unsigned int v66; // ebx
  char *v67; // rdi
  __int64 v68; // rsi
  __int64 v69; // rax
  int v70; // eax
  int v71; // ebx
  unsigned int v72; // ebx
  char *v73; // rdi
  __int64 v74; // rsi
  __int64 v75; // rax
  int v76; // eax
  int v77; // ebx
  unsigned int v78; // ebx
  char *v79; // rdi
  __int64 v80; // rsi
  __int64 v81; // rax
  int v82; // eax
  int v83; // ebx
  int v84; // eax
  __int64 v85; // rcx
  unsigned int v86; // eax
  unsigned int v88; // [rsp+58h] [rbp-81h] BYREF
  __int64 v89; // [rsp+60h] [rbp-79h] BYREF
  char v90; // [rsp+68h] [rbp-71h]
  char v91; // [rsp+69h] [rbp-70h]
  _BYTE v92[32]; // [rsp+70h] [rbp-69h] BYREF
  int v93; // [rsp+90h] [rbp-49h] BYREF
  int v94; // [rsp+94h] [rbp-45h] BYREF
  __int64 v95; // [rsp+98h] [rbp-41h]
  __int64 v96; // [rsp+A0h] [rbp-39h]
  _OWORD v97[2]; // [rsp+A8h] [rbp-31h] BYREF
  void *retaddr; // [rsp+120h] [rbp+47h]

  v96 = -2;
  v91 = a5;
  v90 = a6;
  v94 = 0;
  v11 = *(_QWORD *)(a1 + 16);
  v12 = *(_QWORD *)(v11 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v11 + 96) + 8424LL) )
  {
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(v11 + 96) + 8408LL);
    *(_QWORD *)(v12 + 8) = LoadLibraryExW(v13, 0, 0x800u);
    *(_BYTE *)(v12 + 16) = 1;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v12 + 40LL))(v12, *a2, &v94);
  v16 = (const wchar_t *)v14;
  v95 = v14;
  if ( (dword_180439CC0 & 8) != 0 )
    sub_180239204(v15, qword_1803BC850, v14);
  v17 = *(_QWORD **)(*(_QWORD *)(a1 + 16) + 112LL);
  v18 = wcsstr(v16, L"Windows.Foundation.IReference`1");
  if ( !v18 || v18 != v16 )
  {
    v19 = wcsstr(v16, L"Windows.Foundation.IReferenceArray`1");
    if ( !v19 || v19 != v16 )
      sub_18005F188(v17, 2148144102LL, v16);
  }
  v93 = 0;
  sub_1801BAA4C(v17);
  sub_180068C64(v97, v17, retaddr);
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a4 + 48LL))(a4, &v93);
  if ( v17 )
    sub_180021E18(v17[148]);
  sub_180022508(v97);
  if ( v20 < 0 )
    sub_1802B1AE0(v17, (unsigned int)v20);
  sub_1801BAA4C(v17);
  v89 = 0;
  if ( v93 > 1025 )
  {
    switch ( v93 )
    {
      case 1026:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v43 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 216LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v43 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v43);
        v44 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 40LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v44 < 0 )
          sub_1801A8A70(v17, (unsigned int)v44);
        goto LABEL_209;
      case 1027:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v45 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 224LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v45 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v45);
        v46 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 88LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v46 < 0 )
          sub_1801A8A70(v17, (unsigned int)v46);
        goto LABEL_209;
      case 1028:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v47 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 232LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v47 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v47);
        v48 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 48LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v48 < 0 )
          sub_1801A8A70(v17, (unsigned int)v48);
        goto LABEL_209;
      case 1029:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v49 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 240LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v49 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v49);
        v50 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 96LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v50 < 0 )
          sub_1801A8A70(v17, (unsigned int)v50);
        goto LABEL_209;
      case 1030:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v51 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 248LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v51 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v51);
        v52 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 56LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v52 < 0 )
          sub_1801A8A70(v17, (unsigned int)v52);
        goto LABEL_209;
      case 1031:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v53 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 256LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v53 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v53);
        v54 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 104LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v54 < 0 )
          sub_1801A8A70(v17, (unsigned int)v54);
        goto LABEL_209;
      case 1032:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v55 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 264LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v55 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v55);
        v56 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 64LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v56 < 0 )
          sub_1801A8A70(v17, (unsigned int)v56);
        goto LABEL_209;
      case 1033:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v57 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 272LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v57 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v57);
        v58 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 72LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v58 < 0 )
          sub_1801A8A70(v17, (unsigned int)v58);
        goto LABEL_209;
      case 1034:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v59 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 280LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v59 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v59);
        v60 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 24LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v60 < 0 )
          sub_1801A8A70(v17, (unsigned int)v60);
        goto LABEL_209;
      case 1035:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v61 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 288LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v61 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v61);
        v62 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 112LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v62 < 0 )
          sub_1801A8A70(v17, (unsigned int)v62);
        goto LABEL_209;
      case 1036:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v63 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 296LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v63 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v63);
        v64 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 80LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v64 < 0 )
          sub_1801A8A70(v17, (unsigned int)v64);
        goto LABEL_209;
      case 1037:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v83 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 304LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v83 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v83);
        v84 = sub_18022C278(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 136LL),
                *(_QWORD *)(a1 + 16),
                *(char **)&v97[0],
                v88,
                v88,
                1,
                &v89,
                1);
        if ( v84 < 0 )
          sub_1801A8A70(v17, (unsigned int)v84);
        goto LABEL_209;
      case 1038:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v65 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 320LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v65 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v65);
        v66 = v88;
        v67 = *(char **)&v97[0];
        v68 = *(_QWORD *)(a1 + 16);
        v69 = sub_1802262D4(*(_QWORD *)(*(_QWORD *)(v68 + 120) + 152LL));
        v70 = sub_18022C278(v69, v68, v67, v66, v66, 1, &v89, 1);
        if ( v70 < 0 )
          sub_1801A8A70(v17, (unsigned int)v70);
        goto LABEL_209;
      case 1039:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v71 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 328LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v71 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v71);
        v72 = v88;
        v73 = *(char **)&v97[0];
        v74 = *(_QWORD *)(a1 + 16);
        v75 = sub_1802262D4(*(_QWORD *)(*(_QWORD *)(v74 + 120) + 160LL));
        v76 = sub_18022C278(v75, v74, v73, v72, v72, 1, &v89, 1);
        if ( v76 < 0 )
          sub_1801A8A70(v17, (unsigned int)v76);
        goto LABEL_209;
      case 1040:
        *(_QWORD *)&v97[0] = 0;
        v88 = 0;
        sub_180068C64(v92, v17, retaddr);
        v77 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 312LL))(a4, &v88, v97);
        if ( v17 )
          sub_180021E18(v17[148]);
        sub_180022508(v92);
        if ( v77 < 0 )
          sub_1802B1AE0(v17, (unsigned int)v77);
        v78 = v88;
        v79 = *(char **)&v97[0];
        v80 = *(_QWORD *)(a1 + 16);
        v81 = sub_1802262D4(*(_QWORD *)(*(_QWORD *)(v80 + 120) + 144LL));
        v82 = sub_18022C278(v81, v80, v79, v78, v78, 1, &v89, 1);
        if ( v82 < 0 )
          sub_1801A8A70(v17, (unsigned int)v82);
        goto LABEL_209;
      default:
        goto LABEL_216;
    }
  }
  if ( v93 == 1025 )
  {
    *(_QWORD *)&v97[0] = 0;
    v88 = 0;
    sub_180068C64(v92, v17, retaddr);
    v41 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _OWORD *))(*(_QWORD *)a4 + 208LL))(a4, &v88, v97);
    if ( v17 )
      sub_180021E18(v17[148]);
    sub_180022508(v92);
    if ( v41 < 0 )
      sub_1802B1AE0(v17, (unsigned int)v41);
    v42 = sub_18022C278(
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 120LL) + 32LL),
            *(_QWORD *)(a1 + 16),
            *(char **)&v97[0],
            v88,
            v88,
            1,
            &v89,
            1);
    if ( v42 < 0 )
      sub_1801A8A70(v17, (unsigned int)v42);
LABEL_209:
    v25 = v89;
    goto LABEL_210;
  }
  if ( v93 > 8 )
  {
    if ( v93 != 9 )
    {
      switch ( v93 )
      {
        case 10:
          LOWORD(v88) = 0;
          sub_180068C64(v92, v17, retaddr);
          v39 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 136LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v39 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v39);
          v22 = sub_180016010(&v88, 1, v17);
          goto LABEL_40;
        case 11:
          LOBYTE(v88) = 0;
          sub_180068C64(v92, v17, retaddr);
          v38 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 144LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v38 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v38);
          v25 = *(_QWORD *)(*v17 + (-(__int64)((_BYTE)v88 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 992);
          goto LABEL_210;
        case 12:
          v89 = 0;
          sub_180068C64(v92, v17, retaddr);
          v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 152LL))(a4, &v89);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v36 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v36);
          LOBYTE(v37) = 1;
          sub_180246634(a1, v89, v37);
          v22 = sub_1802456BC(a1, &v89);
          goto LABEL_40;
        case 13:
          sub_18005F188(v17, 2148139021LL, 0);
        case 14:
          v89 = 0;
          sub_180068C64(v92, v17, retaddr);
          v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 168LL))(a4, &v89);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v35 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v35);
          v22 = sub_180245B14(a1, &v89, 8);
          goto LABEL_40;
        case 15:
          v89 = 0;
          sub_180068C64(v92, v17, retaddr);
          v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 176LL))(a4, &v89);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v34 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v34);
          v22 = sub_180245B58(a1, &v89, 8);
          goto LABEL_40;
        case 16:
          v97[0] = 0;
          sub_180068C64(v92, v17, retaddr);
          v32 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a4 + 160LL))(a4, v97);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v92);
          if ( v32 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v32);
          LOBYTE(v33) = 1;
          v22 = sub_18024575C(a1, v33, v97, 16);
          goto LABEL_40;
      }
      goto LABEL_216;
    }
    v89 = 0;
    sub_180068C64(v92, v17, retaddr);
    v40 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 128LL))(a4, &v89);
    if ( v17 )
      sub_180021E18(v17[148]);
    sub_180022508(v92);
    if ( v40 < 0 )
      sub_1802B1AE0(v17, (unsigned int)v40);
  }
  else
  {
    if ( v93 != 8 )
    {
      switch ( v93 )
      {
        case 0:
          v25 = *(_QWORD *)(*v17 + 1064LL);
          goto LABEL_210;
        case 1:
          LOBYTE(v88) = 0;
          sub_180068C64(v97, v17, retaddr);
          v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 64LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v30 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v30);
          v27 = (unsigned __int8)v88;
          break;
        case 2:
          LOWORD(v88) = 0;
          sub_180068C64(v97, v17, retaddr);
          v29 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 72LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v29 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v29);
          v27 = (unsigned int)(__int16)v88;
          break;
        case 3:
          LOWORD(v88) = 0;
          sub_180068C64(v97, v17, retaddr);
          v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 80LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v28 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v28);
          v27 = (unsigned __int16)v88;
          break;
        case 4:
          v88 = 0;
          sub_180068C64(v97, v17, retaddr);
          v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 88LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v26 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v26);
          v27 = v88;
          break;
        case 5:
          v88 = 0;
          sub_180068C64(v97, v17, retaddr);
          v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 96LL))(a4, &v88);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v24 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v24);
          v22 = sub_1800194D0(v88);
          goto LABEL_40;
        case 6:
          v89 = 0;
          sub_180068C64(v97, v17, retaddr);
          v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 104LL))(a4, &v89);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v23 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v23);
          v22 = sub_1801C5558(v89, v17);
          goto LABEL_40;
        case 7:
          v89 = 0;
          sub_180068C64(v97, v17, retaddr);
          v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 112LL))(a4, &v89);
          if ( v17 )
            sub_180021E18(v17[148]);
          sub_180022508(v97);
          if ( v21 < 0 )
            sub_1802B1AE0(v17, (unsigned int)v21);
          v22 = sub_1803012A0(v89, v17);
          goto LABEL_40;
        default:
LABEL_216:
          v25 = sub_1802461E4(a1, (_DWORD)a2, a3, a4, v91, v90, 0, a7, 0);
          goto LABEL_217;
      }
      v25 = v27 | 0x1000000000000LL;
      goto LABEL_210;
    }
    v88 = 0;
    sub_180068C64(v97, v17, retaddr);
    v31 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 120LL))(a4, &v88);
    if ( v17 )
      sub_180021E18(v17[148]);
    sub_180022508(v97);
    if ( v31 < 0 )
      sub_1802B1AE0(v17, (unsigned int)v31);
  }
  v22 = sub_1801524A4();
LABEL_40:
  v25 = v22;
LABEL_210:
  sub_1801C09D0(*(_QWORD *)(a1 + 16));
  if ( v91 )
    sub_1801C1604(*(_QWORD *)(a1 + 16), a4);
  if ( !v90 && (unsigned __int8)sub_180054858(v25) && !*(_DWORD *)(*(_QWORD *)(a1 + 16) + 56LL) )
  {
    v86 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 376LL))(v25);
    sub_180225494(v86);
  }
LABEL_217:
  if ( (dword_180439CC0 & 8) != 0 )
    sub_180239204(v85, qword_1803BD070, v95);
  return v25;
}

```

## disassembly

```asm
0x1801be2bc  mov     rax, rsp
0x1801be2bf  mov     [rax+20h], r9
0x1801be2c3  mov     [rax+18h], r8
0x1801be2c7  mov     [rax+10h], rdx
0x1801be2cb  mov     [rax+8], rcx
0x1801be2cf  push    rbp
0x1801be2d0  push    rbx
0x1801be2d1  push    rsi
0x1801be2d2  push    rdi
0x1801be2d3  push    r12
0x1801be2d5  push    r13
0x1801be2d7  push    r14
0x1801be2d9  push    r15
0x1801be2db  lea     rbp, [rax-47h]
0x1801be2df  sub     rsp, 0D8h
0x1801be2e6  mov     [rbp+3Fh+var_78], 0FFFFFFFFFFFFFFFEh
0x1801be2ee  mov     rax, cs:__security_cookie
0x1801be2f5  xor     rax, rsp
0x1801be2f8  mov     [rbp+3Fh+var_50], rax
0x1801be2fc  mov     r13, [rbp+3Fh+arg_0]
0x1801be300  mov     rdi, [rbp+3Fh+arg_8]
0x1801be304  mov     rsi, [rbp+3Fh+arg_10]
0x1801be308  mov     r15, [rbp+3Fh+arg_18]
0x1801be30c  mov     al, [rbp+3Fh+arg_20]
0x1801be30f  mov     [rbp+3Fh+var_AF], al
0x1801be312  mov     al, [rbp+3Fh+arg_28]
0x1801be315  mov     [rbp+3Fh+var_B0], al
0x1801be318  mov     r12d, [rbp+3Fh+arg_30]
0x1801be31c  mov     [rbp+3Fh+var_84], 0
0x1801be323  mov     rax, [r13+10h]
0x1801be327  mov     rbx, [rax+60h]
0x1801be32b  add     rbx, 20D8h
0x1801be332  cmp     byte ptr [rbx+10h], 0
0x1801be336  jnz     short loc_1801BE360
0x1801be338  mov     rax, [rbx]
0x1801be33b  mov     rcx, rbx
0x1801be33e  mov     rax, [rax+8]
0x1801be342  call    j_j__guard_dispatch_icall_nop
0x1801be347  mov     rcx, rax; lpLibFileName
0x1801be34a  xor     edx, edx; hFile
0x1801be34c  mov     r8d, 800h; dwFlags
0x1801be352  call    cs:LoadLibraryExW
0x1801be358  mov     [rbx+8], rax
0x1801be35c  mov     byte ptr [rbx+10h], 1
0x1801be360  mov     rax, [rbx]
0x1801be363  lea     r8, [rbp+3Fh+var_84]
0x1801be367  mov     rdx, [rdi]
0x1801be36a  mov     rcx, rbx
0x1801be36d  mov     rax, [rax+28h]
0x1801be371  call    j_j__guard_dispatch_icall_nop
0x1801be376  mov     rbx, rax
0x1801be379  mov     [rbp+3Fh+var_80], rax
0x1801be37d  test    byte ptr cs:dword_180439CC0, 8
0x1801be384  jz      short loc_1801BE395
0x1801be386  mov     r8, rax
0x1801be389  lea     rdx, qword_1803BC850
0x1801be390  call    sub_180239204
0x1801be395  mov     rcx, [r13+10h]
0x1801be399  mov     r14, [rcx+70h]
0x1801be39d  lea     rdx, aWindowsFoundat; "Windows.Foundation.IReference`1"
0x1801be3a4  mov     rcx, rbx; Str
0x1801be3a7  call    cs:wcsstr
0x1801be3ad  test    rax, rax
0x1801be3b0  jz      short loc_1801BE3B7
0x1801be3b2  cmp     rax, rbx
0x1801be3b5  jz      short loc_1801BE3D9
0x1801be3b7  lea     rdx, aWindowsFoundat_0; "Windows.Foundation.IReferenceArray`1"
0x1801be3be  mov     rcx, rbx; Str
0x1801be3c1  call    cs:wcsstr
0x1801be3c7  test    rax, rax
0x1801be3ca  jz      loc_1801BF6C1
0x1801be3d0  cmp     rax, rbx
0x1801be3d3  jnz     loc_1801BF6C1
0x1801be3d9  mov     [rbp+3Fh+var_88], 0
0x1801be3e0  mov     rcx, r14
0x1801be3e3  call    sub_1801BAA4C
0x1801be3e8  mov     r8, [rbp+47h]
0x1801be3ec  mov     rdx, r14
0x1801be3ef  lea     rcx, [rbp+3Fh+var_70]
0x1801be3f3  call    sub_180068C64
0x1801be3f8  nop
0x1801be3f9  mov     rax, [r15]
0x1801be3fc  lea     rdx, [rbp+3Fh+var_88]
0x1801be400  mov     rcx, r15
0x1801be403  mov     rax, [rax+30h]
0x1801be407  call    j_j__guard_dispatch_icall_nop
0x1801be40c  mov     ebx, eax
0x1801be40e  test    r14, r14
0x1801be411  jz      short loc_1801BE420
0x1801be413  mov     rcx, [r14+4A0h]
0x1801be41a  call    sub_180021E18
0x1801be41f  nop
0x1801be420  lea     rcx, [rbp+3Fh+var_70]
0x1801be424  call    sub_180022508
0x1801be429  mov     rcx, r14
0x1801be42c  test    ebx, ebx
0x1801be42e  jns     short loc_1801BE438
0x1801be430  mov     edx, ebx
0x1801be432  call    sub_1802B1AE0
0x1801be438  call    sub_1801BAA4C
0x1801be43d  xor     r8d, r8d
0x1801be440  mov     [rbp+3Fh+var_B8], r8
0x1801be444  mov     ecx, [rbp+3Fh+var_88]
0x1801be447  mov     eax, 401h
0x1801be44c  cmp     ecx, eax
0x1801be44e  jg      loc_1801BEBEA
0x1801be454  jz      loc_1801BEB44
0x1801be45a  cmp     ecx, 8
0x1801be45d  jg      loc_1801BE7DF
0x1801be463  jz      loc_1801BE776
0x1801be469  test    ecx, ecx
0x1801be46b  jz      loc_1801BE767
0x1801be471  sub     ecx, 1
0x1801be474  jz      loc_1801BE6FA
0x1801be47a  sub     ecx, 1
0x1801be47d  jz      loc_1801BE69B
0x1801be483  sub     ecx, 1
0x1801be486  jz      loc_1801BE639
0x1801be48c  sub     ecx, 1
0x1801be48f  jz      loc_1801BE5DA
0x1801be495  sub     ecx, 1
0x1801be498  jz      loc_1801BE573
0x1801be49e  sub     ecx, 1
0x1801be4a1  jz      short loc_1801BE511
0x1801be4a3  cmp     ecx, 1
0x1801be4a6  jnz     def_1801BEC0D; jumptable 00000001801BEC0D default case
0x1801be4ac  mov     [rbp+3Fh+var_B8], r8
0x1801be4b0  mov     r8, [rbp+47h]
0x1801be4b4  mov     rdx, r14
0x1801be4b7  lea     rcx, [rbp+3Fh+var_70]
0x1801be4bb  call    sub_180068C64
0x1801be4c0  nop
0x1801be4c1  mov     rax, [r15]
0x1801be4c4  lea     rdx, [rbp+3Fh+var_B8]
0x1801be4c8  mov     rcx, r15
0x1801be4cb  mov     rax, [rax+70h]
0x1801be4cf  call    j_j__guard_dispatch_icall_nop
0x1801be4d4  mov     ebx, eax
0x1801be4d6  test    r14, r14
0x1801be4d9  jz      short loc_1801BE4E8
0x1801be4db  mov     rcx, [r14+4A0h]
0x1801be4e2  call    sub_180021E18
0x1801be4e7  nop
0x1801be4e8  lea     rcx, [rbp+3Fh+var_70]
0x1801be4ec  call    sub_180022508
0x1801be4f1  test    ebx, ebx
0x1801be4f3  jns     short loc_1801BE500
0x1801be4f5  mov     edx, ebx
0x1801be4f7  mov     rcx, r14
0x1801be4fa  call    sub_1802B1AE0
0x1801be500  mov     rdx, r14
0x1801be503  mov     rcx, [rbp+3Fh+var_B8]
0x1801be507  call    sub_1803012A0
0x1801be50c  jmp     loc_1801BE5D2
0x1801be511  mov     [rbp+3Fh+var_B8], r8
0x1801be515  mov     r8, [rbp+47h]
0x1801be519  mov     rdx, r14
0x1801be51c  lea     rcx, [rbp+3Fh+var_70]
0x1801be520  call    sub_180068C64
0x1801be525  nop
0x1801be526  mov     rax, [r15]
0x1801be529  lea     rdx, [rbp+3Fh+var_B8]
0x1801be52d  mov     rcx, r15
0x1801be530  mov     rax, [rax+68h]
0x1801be534  call    j_j__guard_dispatch_icall_nop
0x1801be539  mov     ebx, eax
0x1801be53b  test    r14, r14
0x1801be53e  jz      short loc_1801BE54D
0x1801be540  mov     rcx, [r14+4A0h]
0x1801be547  call    sub_180021E18
0x1801be54c  nop
0x1801be54d  lea     rcx, [rbp+3Fh+var_70]
0x1801be551  call    sub_180022508
0x1801be556  test    ebx, ebx
0x1801be558  jns     short loc_1801BE565
0x1801be55a  mov     edx, ebx
0x1801be55c  mov     rcx, r14
0x1801be55f  call    sub_1802B1AE0
0x1801be565  mov     rdx, r14
0x1801be568  mov     rcx, [rbp+3Fh+var_B8]
0x1801be56c  call    sub_1801C5558
0x1801be571  jmp     short loc_1801BE5D2
0x1801be573  mov     [rsp+110h+var_C0], r8d
0x1801be578  mov     r8, [rbp+47h]
0x1801be57c  mov     rdx, r14
0x1801be57f  lea     rcx, [rbp+3Fh+var_70]
0x1801be583  call    sub_180068C64
0x1801be588  nop
0x1801be589  mov     rax, [r15]
0x1801be58c  lea     rdx, [rsp+110h+var_C0]
0x1801be591  mov     rcx, r15
0x1801be594  mov     rax, [rax+60h]
0x1801be598  call    j_j__guard_dispatch_icall_nop
0x1801be59d  mov     ebx, eax
0x1801be59f  test    r14, r14
0x1801be5a2  jz      short loc_1801BE5B1
0x1801be5a4  mov     rcx, [r14+4A0h]
0x1801be5ab  call    sub_180021E18
0x1801be5b0  nop
0x1801be5b1  lea     rcx, [rbp+3Fh+var_70]
0x1801be5b5  call    sub_180022508
0x1801be5ba  test    ebx, ebx
0x1801be5bc  jns     short loc_1801BE5C9
0x1801be5be  mov     edx, ebx
0x1801be5c0  mov     rcx, r14
0x1801be5c3  call    sub_1802B1AE0
0x1801be5c9  mov     ecx, [rsp+110h+var_C0]
0x1801be5cd  call    sub_1800194D0
0x1801be5d2  mov     rbx, rax
0x1801be5d5  jmp     loc_1801BF602
0x1801be5da  mov     [rsp+110h+var_C0], r8d
0x1801be5df  mov     r8, [rbp+47h]
0x1801be5e3  mov     rdx, r14
0x1801be5e6  lea     rcx, [rbp+3Fh+var_70]
0x1801be5ea  call    sub_180068C64
0x1801be5ef  nop
0x1801be5f0  mov     rax, [r15]
0x1801be5f3  lea     rdx, [rsp+110h+var_C0]
0x1801be5f8  mov     rcx, r15
0x1801be5fb  mov     rax, [rax+58h]
0x1801be5ff  call    j_j__guard_dispatch_icall_nop
0x1801be604  mov     ebx, eax
0x1801be606  test    r14, r14
0x1801be609  jz      short loc_1801BE618
0x1801be60b  mov     rcx, [r14+4A0h]
0x1801be612  call    sub_180021E18
0x1801be617  nop
0x1801be618  lea     rcx, [rbp+3Fh+var_70]
0x1801be61c  call    sub_180022508
0x1801be621  test    ebx, ebx
0x1801be623  jns     short loc_1801BE630
0x1801be625  mov     edx, ebx
0x1801be627  mov     rcx, r14
0x1801be62a  call    sub_1802B1AE0
0x1801be630  mov     ebx, [rsp+110h+var_C0]
0x1801be634  jmp     loc_1801BE755
0x1801be639  xor     eax, eax
0x1801be63b  mov     word ptr [rsp+110h+var_C0], ax
0x1801be640  mov     r8, [rbp+47h]
0x1801be644  mov     rdx, r14
0x1801be647  lea     rcx, [rbp+3Fh+var_70]
0x1801be64b  call    sub_180068C64
0x1801be650  nop
0x1801be651  mov     rax, [r15]
0x1801be654  lea     rdx, [rsp+110h+var_C0]
0x1801be659  mov     rcx, r15
0x1801be65c  mov     rax, [rax+50h]
0x1801be660  call    j_j__guard_dispatch_icall_nop
0x1801be665  mov     ebx, eax
0x1801be667  test    r14, r14
0x1801be66a  jz      short loc_1801BE679
0x1801be66c  mov     rcx, [r14+4A0h]
0x1801be673  call    sub_180021E18
0x1801be678  nop
0x1801be679  lea     rcx, [rbp+3Fh+var_70]
0x1801be67d  call    sub_180022508
0x1801be682  test    ebx, ebx
0x1801be684  jns     short loc_1801BE691
0x1801be686  mov     edx, ebx
0x1801be688  mov     rcx, r14
0x1801be68b  call    sub_1802B1AE0
0x1801be691  movzx   ebx, word ptr [rsp+110h+var_C0]
0x1801be696  jmp     loc_1801BE755
0x1801be69b  xor     eax, eax
0x1801be69d  mov     word ptr [rsp+110h+var_C0], ax
0x1801be6a2  mov     r8, [rbp+47h]
0x1801be6a6  mov     rdx, r14
0x1801be6a9  lea     rcx, [rbp+3Fh+var_70]
0x1801be6ad  call    sub_180068C64
0x1801be6b2  nop
0x1801be6b3  mov     rax, [r15]
0x1801be6b6  lea     rdx, [rsp+110h+var_C0]
0x1801be6bb  mov     rcx, r15
0x1801be6be  mov     rax, [rax+48h]
0x1801be6c2  call    j_j__guard_dispatch_icall_nop
0x1801be6c7  mov     ebx, eax
0x1801be6c9  test    r14, r14
0x1801be6cc  jz      short loc_1801BE6DB
0x1801be6ce  mov     rcx, [r14+4A0h]
0x1801be6d5  call    sub_180021E18
0x1801be6da  nop
0x1801be6db  lea     rcx, [rbp+3Fh+var_70]
0x1801be6df  call    sub_180022508
0x1801be6e4  test    ebx, ebx
0x1801be6e6  jns     short loc_1801BE6F3
0x1801be6e8  mov     edx, ebx
0x1801be6ea  mov     rcx, r14
0x1801be6ed  call    sub_1802B1AE0
0x1801be6f3  movsx   ebx, word ptr [rsp+110h+var_C0]
0x1801be6f8  jmp     short loc_1801BE755
0x1801be6fa  mov     byte ptr [rsp+110h+var_C0], r8b
0x1801be6ff  mov     r8, [rbp+47h]
0x1801be703  mov     rdx, r14
0x1801be706  lea     rcx, [rbp+3Fh+var_70]
0x1801be70a  call    sub_180068C64
0x1801be70f  nop
0x1801be710  mov     rax, [r15]
0x1801be713  lea     rdx, [rsp+110h+var_C0]
0x1801be718  mov     rcx, r15
0x1801be71b  mov     rax, [rax+40h]
  ... truncated ...
```
