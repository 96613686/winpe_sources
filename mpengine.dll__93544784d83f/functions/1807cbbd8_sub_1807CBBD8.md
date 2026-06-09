# sub_1807CBBD8

- ea: `0x1807cbbd8`
- end: `0x1807cc73a`
- name: `sub_1807CBBD8`
- size: `2914`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1807cc8dc`

## callees

- `0x18001f710`
- `0x18013f000`
- `0x18016034c`
- `0x1801a1648`
- `0x1801a569c`
- `0x1801a9098`
- `0x1801b9684`
- `0x1801b98d0`
- `0x1801b9b6c`
- `0x1801c8638`
- `0x1801d8468`
- `0x1801e3834`
- `0x18024e7a0`
- `0x180255fbc`
- `0x18026744c`
- `0x180267658`
- `0x1802b9450`
- `0x1802bada4`
- `0x1807cb05c`
- `0x1807cb63c`
- `0x1807cbbd8`
- `0x1807cc82c`
- `0x1807cd4a0`
- `0x180b74350`
- `0x180b743d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1807cbe12`
- `KERNEL32!CreateFileW` at `0x1807cbe12`
- `KERNEL32!LoadLibraryExW` at `0x1807cbf6e`
- `KERNEL32!LoadLibraryExW` at `0x1807cbf6e`
- `KERNEL32!GetProcAddress` at `0x1807cbfdc`
- `KERNEL32!GetProcAddress` at `0x1807cc01e`
- `KERNEL32!GetProcAddress` at `0x1807cbfdc`
- `KERNEL32!GetProcAddress` at `0x1807cc01e`
- `KERNEL32!GetLastError` at `0x1807cbfa2`
- `KERNEL32!GetLastError` at `0x1807cbfa2`

## string_xrefs

- `0x1807cbfd2`: `rpf_module_update`

## pseudocode

```c
__int64 __fastcall sub_1807CBBD8(const WCHAR *a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  unsigned int v5; // esi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  volatile signed __int32 *v9; // r12
  volatile signed __int32 *v10; // r15
  __int64 v11; // r13
  __int64 v12; // rax
  HANDLE FileW; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HMODULE Library; // rax
  char LastError; // al
  FARPROC rpf_module_update; // rax
  FARPROC rpf_module_init; // r15
  int v21; // edx
  _BYTE *v22; // r8
  int *v23; // r9
  int v24; // ecx
  char v25; // al
  int v26; // edx
  __int64 v27; // r12
  int v28; // esi
  __int64 v29; // r8
  __int128 *v30; // rdx
  __int64 *v31; // rcx
  __int64 *v32; // r8
  unsigned int v33; // edx
  __int64 *v34; // rax
  unsigned int v35; // esi
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  volatile signed __int32 *v40; // r14
  volatile signed __int32 *v41; // r14
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-2B8h]
  __int64 v45; // [rsp+50h] [rbp-288h] BYREF
  __int128 v46; // [rsp+60h] [rbp-278h] BYREF
  __int64 v47; // [rsp+70h] [rbp-268h] BYREF
  __int128 v48; // [rsp+80h] [rbp-258h] BYREF
  __int128 v49; // [rsp+90h] [rbp-248h] BYREF
  _BYTE *v50; // [rsp+A0h] [rbp-238h]
  __int128 v51; // [rsp+B0h] [rbp-228h]
  _QWORD *v52; // [rsp+C0h] [rbp-218h] BYREF
  volatile signed __int32 *v53; // [rsp+C8h] [rbp-210h]
  int *v54; // [rsp+D0h] [rbp-208h]
  __int64 v55; // [rsp+D8h] [rbp-200h]
  __int128 v56; // [rsp+E0h] [rbp-1F8h]
  unsigned int v57; // [rsp+F0h] [rbp-1E8h]
  __int128 v58; // [rsp+F8h] [rbp-1E0h] BYREF
  __int128 v59; // [rsp+108h] [rbp-1D0h]
  const WCHAR *v60; // [rsp+118h] [rbp-1C0h]
  int v61; // [rsp+120h] [rbp-1B8h] BYREF
  __int64 v62; // [rsp+128h] [rbp-1B0h]
  volatile signed __int32 *v63; // [rsp+130h] [rbp-1A8h]
  __int128 v64; // [rsp+138h] [rbp-1A0h]
  _BYTE v65[32]; // [rsp+158h] [rbp-180h] BYREF
  _BYTE v66[32]; // [rsp+178h] [rbp-160h] BYREF
  __int64 v67; // [rsp+198h] [rbp-140h] BYREF
  __int128 v68; // [rsp+1A0h] [rbp-138h] BYREF
  __int64 v69; // [rsp+1B0h] [rbp-128h]
  unsigned __int64 v70; // [rsp+1B8h] [rbp-120h]
  _BYTE v71[16]; // [rsp+1C0h] [rbp-118h] BYREF
  __int64 v72; // [rsp+1D0h] [rbp-108h]
  __int64 v73; // [rsp+1D8h] [rbp-100h]
  __int128 v74; // [rsp+1E0h] [rbp-F8h] BYREF
  __int64 v75; // [rsp+1F0h] [rbp-E8h]
  __int64 v76; // [rsp+1F8h] [rbp-E0h]
  __int128 v77; // [rsp+200h] [rbp-D8h]
  int v78; // [rsp+210h] [rbp-C8h]
  unsigned __int16 v79; // [rsp+214h] [rbp-C4h]
  _DWORD v80[30]; // [rsp+220h] [rbp-B8h] BYREF

  v47 = a4;
  v50 = a3;
  *(_QWORD *)&v48 = a4;
  v60 = a1;
  v55 = a2;
  v67 = (__int64)a3;
  v54 = (int *)(a4 + 32);
  v5 = 0;
  sub_180B743D0(v80, 0, 104);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)&v56 = a2 + 8;
  *(_QWORD *)(a2 + 8) = -1;
  *(_QWORD *)&v46 = a2 + 16;
  *(_BYTE *)(a2 + 16) = 0;
  v49 = 0;
  v51 = 0;
  LOBYTE(v6) = 1;
  v7 = (__int64 *)sub_18024E7A0(&v52, v6);
  v8 = *v7;
  v9 = (volatile signed __int32 *)v7[1];
  *v7 = 0;
  v7[1] = 0;
  *(_QWORD *)&v49 = v8;
  *((_QWORD *)&v49 + 1) = v9;
  v10 = v53;
  if ( v53 )
  {
    if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = sub_18001F710(32);
  v45 = v11;
  *(_DWORD *)(v11 + 8) = 1;
  *(_DWORD *)(v11 + 12) = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<std::map<unsigned long,std::string>>::`vftable';
  v52 = (_QWORD *)(v11 + 16);
  *(_QWORD *)(v11 + 16) = 0;
  *(_QWORD *)(v11 + 24) = 0;
  _mm_lfence();
  v12 = sub_18001F710(72);
  *(_QWORD *)v12 = v12;
  *(_QWORD *)(v12 + 8) = v12;
  *(_QWORD *)(v12 + 16) = v12;
  *(_WORD *)(v12 + 24) = 257;
  *(_QWORD *)(v11 + 16) = v12;
  *(_QWORD *)&v51 = v11 + 16;
  *((_QWORD *)&v51 + 1) = v11;
  *v50 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *(_QWORD *)v56 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v14 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_10;
    v15 = 26;
LABEL_9:
    sub_1801C8638(v14[2], v15, &stru_180D0F860, a1);
LABEL_10:
    v5 = 32769;
LABEL_11:
    sub_1807CC82C(a2);
    goto LABEL_12;
  }
  if ( *v54 >= 0 && (unsigned int)sub_1802BADA4(FileW) )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801C8638(*((_QWORD *)hDevice + 2), 27, &stru_180D0F860, a1);
    v5 = 40965;
    goto LABEL_11;
  }
  Library = LoadLibraryExW(a1, 0, 0);
  *(_QWORD *)a2 = Library;
  if ( !Library )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      sub_1801A569C(*((_QWORD *)hDevice + 2), 28, (unsigned int)&stru_180D0F860, (_DWORD)a1, LastError);
    }
    goto LABEL_10;
  }
  rpf_module_update = GetProcAddress(Library, "rpf_module_update");
  *(_QWORD *)(a2 + 24) = rpf_module_update;
  if ( !rpf_module_update )
  {
    v14 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_10;
    v15 = 29;
    goto LABEL_9;
  }
  rpf_module_init = GetProcAddress(*(HMODULE *)a2, "rpf_module_init");
  if ( !rpf_module_init )
  {
    v14 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_10;
    v15 = 30;
    goto LABEL_9;
  }
  v67 = sub_1802B9450();
  v21 = ((__int64 (__fastcall *)(_DWORD *, __int64 (__fastcall *)(), __int64 *))rpf_module_init)(
          v80,
          sub_1807CD400,
          &v67);
  if ( (v21 & 0xBFFFFFFF) != (byte_18105B1D9 != 0 ? -2147457608 : 26040) )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1807CD4A0(*((_QWORD *)hDevice + 2), dwCreationDisposition, (__int64)a1);
    v5 = 32782;
    goto LABEL_11;
  }
  if ( (v21 & 0x40000000) != 0 && hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
    sub_1801A1648(*((_QWORD *)hDevice + 2), 32, &stru_180D0F860);
  *(_BYTE *)v46 = 1;
  v22 = v50;
  *v50 = 0;
  v23 = v54;
  v24 = *v54;
  if ( (*v54 & 0x100) != 0 )
    goto LABEL_99;
  v25 = 0;
  v26 = v80[0];
  if ( (v24 & 0x10000) == 0 )
  {
    if ( (v80[0] & 0x10000) == 0 )
    {
      *v22 = 1;
      v24 = *(_DWORD *)(v47 + 32);
      v25 = 1;
    }
    if ( (v26 & 0x2000000) != 0 && (v24 & 0x2000000) == 0 )
    {
      *v22 = 0;
      v25 = 0;
    }
  }
  if ( (*v23 & 0x8000) != 0 && (v26 & 0x8000) != 0 )
  {
    *v22 = 1;
    goto LABEL_59;
  }
  if ( !v25 )
  {
LABEL_99:
    sub_1807CC82C(a2);
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
      sub_1801C8638(*((_QWORD *)hDevice + 2), 33, &stru_180D0F860, a1);
    goto LABEL_12;
  }
LABEL_59:
  *(_QWORD *)&v46 = sub_18001F710(64);
  v27 = sub_1807CB05C(v46, &v49, a2 + 8);
  *(_QWORD *)&v56 = v27 + 16;
  *((_QWORD *)&v56 + 1) = v27;
  sub_180255FBC(*(_QWORD *)(v27 + 32), &v61);
  if ( v61 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801C8638(*((_QWORD *)hDevice + 2), 34, &stru_180D0F860, a1);
    sub_1801A9098(v65, "Failed to attach the exports");
    sub_18016034C(v65, &_TI2_AVMpStdException__);
LABEL_106:
    std::vector<void *>::_Xlen();
  }
  sub_180B743D0(v71, 0, 88);
  v72 = 0;
  v73 = 15;
  v71[0] = 0;
  v74 = 0;
  v75 = 0;
  v76 = 15;
  LOBYTE(v74) = 0;
  v77 = 0;
  v78 = -1;
  v79 = -1;
  v28 = sub_180267658(v62, v71, *(unsigned __int16 *)(v62 + 56));
  while ( !v28 )
  {
    LODWORD(v45) = 0;
    v47 = 0;
    v28 = sub_18026744C(v71, &v47, &v45);
    if ( v28 )
      break;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(v47 + v29) );
    sub_1801E3834(&v68, v47, v29);
    v57 = v78;
    v58 = 0;
    v59 = 0u;
    v30 = &v68;
    if ( v70 > 0xF )
      v30 = (__int128 *)v68;
    sub_1801D8468(&v58, v30, v69);
    v31 = (__int64 *)*v52;
    v32 = *(__int64 **)(*v52 + 8LL);
    v33 = 0;
    v34 = v32;
    v35 = v57;
    while ( !*((_BYTE *)v34 + 25) )
    {
      v32 = v34;
      if ( *((_DWORD *)v34 + 8) >= v57 )
      {
        v33 = 1;
        v31 = v34;
        v34 = (__int64 *)*v34;
      }
      else
      {
        v33 = 0;
        v34 = (__int64 *)v34[2];
      }
    }
    *(_QWORD *)&v64 = v32;
    *((_QWORD *)&v64 + 1) = v33;
    if ( *((_BYTE *)v31 + 25) || v57 < *((_DWORD *)v31 + 8) )
    {
      if ( v52[1] == 0x38E38E38E38E38ELL )
        goto LABEL_106;
      *(_QWORD *)&v46 = *v52;
      v48 = (unsigned __int64)v52;
      _mm_lfence();
      v36 = sub_18001F710(72);
      *(_DWORD *)(v36 + 32) = v35;
      *(_OWORD *)(v36 + 40) = v58;
      *(_OWORD *)(v36 + 56) = v59;
      *(_QWORD *)&v59 = 0;
      *((_QWORD *)&v59 + 1) = 15;
      LOBYTE(v58) = 0;
      v37 = v46;
      *(_QWORD *)v36 = v46;
      *(_QWORD *)(v36 + 8) = v37;
      *(_QWORD *)(v36 + 16) = v37;
      *(_WORD *)(v36 + 24) = 0;
      *((_QWORD *)&v48 + 1) = 0;
      v46 = v64;
      sub_1801B9684(v52, &v46, v36);
    }
    sub_1801B9B6C(&v58);
    v38 = v79;
    if ( *(_WORD *)(v62 + 56) == v79 + 1 )
    {
      v28 = 1;
    }
    else
    {
      LOWORD(v38) = v79 + 1;
      v28 = sub_180267658(v62, v71, v38);
    }
    sub_1801B9B6C(&v68);
  }
  if ( v28 != 1 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801C8638(*((_QWORD *)hDevice + 2), 35, &stru_180D0F860, a1);
    sub_1801A9098(v66, "Failed to enumerate the exports");
    sub_18016034C(v66, &_TI2_AVMpStdException__);
    JUMPOUT(0x1807CC738LL);
  }
  v39 = *(_QWORD *)(a2 + 24);
  v48 = 0;
  if ( v11 )
    _InterlockedAdd((volatile signed __int32 *)(v11 + 8), 1u);
  v48 = v51;
  v46 = 0;
  if ( v27 )
    _InterlockedAdd((volatile signed __int32 *)(v27 + 8), 1u);
  v46 = v56;
  v5 = sub_1807CB63C(&v46, &v48, a2, v39);
  v40 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
  if ( *((_QWORD *)&v77 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  sub_1801B9B6C(&v74);
  sub_1801B9B6C(v71);
  v41 = v63;
  if ( v63 )
  {
    if ( !_InterlockedDecrement(v63 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
      if ( !_InterlockedDecrement(v41 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
    }
  }
  if ( v27 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v27 + 8)) )
    {
      (**(void (__fastcall ***)(__int64))v27)(v27);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v27 + 12)) )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v49 + 1);
  if ( v5 )
    goto LABEL_11;
LABEL_12:
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(__int64))v11)(v11);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 12), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1807cbbd8  push    rbx
0x1807cbbda  push    rsi
0x1807cbbdb  push    rdi
0x1807cbbdc  push    r12
0x1807cbbde  push    r13
0x1807cbbe0  push    r14
0x1807cbbe2  push    r15
0x1807cbbe4  sub     rsp, 2A0h
0x1807cbbeb  mov     rax, cs:__security_cookie
0x1807cbbf2  xor     rax, rsp
0x1807cbbf5  mov     [rsp+2D8h+var_40], rax
0x1807cbbfd  mov     [rsp+2D8h+var_268], r9
0x1807cbc02  mov     rax, r8
0x1807cbc05  mov     [rsp+2D8h+var_238], rax
0x1807cbc0d  mov     r14, rdx
0x1807cbc10  mov     [rsp+2D8h+var_298], rdx
0x1807cbc15  mov     [rsp+2D8h+lpFileName], rcx
0x1807cbc1a  mov     qword ptr [rsp+2D8h+var_258], r9
0x1807cbc22  mov     [rsp+2D8h+var_1C0], rcx
0x1807cbc2a  mov     [rsp+2D8h+var_200], rdx
0x1807cbc32  mov     [rsp+2D8h+var_140], rax
0x1807cbc3a  xor     ebx, ebx
0x1807cbc3c  lea     rax, [r9+20h]
0x1807cbc40  mov     [rsp+2D8h+var_208], rax
0x1807cbc48  mov     esi, ebx
0x1807cbc4a  xor     edx, edx
0x1807cbc4c  lea     r8d, [rbx+68h]
0x1807cbc50  lea     rcx, [rsp+2D8h+var_B8]
0x1807cbc58  call    sub_180B743D0
0x1807cbc5d  mov     [r14], rbx
0x1807cbc60  lea     rax, [r14+8]
0x1807cbc64  mov     qword ptr [rsp+2D8h+var_1F8], rax
0x1807cbc6c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1807cbc70  mov     [rax], rdi
0x1807cbc73  lea     rax, [r14+10h]
0x1807cbc77  mov     qword ptr [rsp+2D8h+var_278], rax
0x1807cbc7c  mov     [rax], bl
0x1807cbc7e  xorps   xmm1, xmm1
0x1807cbc81  movdqu  [rsp+2D8h+var_248], xmm1
0x1807cbc8a  movdqa  [rsp+2D8h+var_228], xmm1
0x1807cbc93  lea     r14d, [rbx+1]
0x1807cbc97  mov     dl, r14b
0x1807cbc9a  lea     rcx, [rsp+2D8h+var_218]
0x1807cbca2  call    sub_18024E7A0
0x1807cbca7  mov     rcx, rax
0x1807cbcaa  mov     rax, [rax]
0x1807cbcad  mov     r12, [rcx+8]
0x1807cbcb1  mov     [rcx], rbx
0x1807cbcb4  mov     [rcx+8], rbx
0x1807cbcb8  mov     qword ptr [rsp+2D8h+var_248], rax
0x1807cbcc0  mov     qword ptr [rsp+2D8h+var_248+8], r12
0x1807cbcc8  mov     r15, [rsp+2D8h+var_210]
0x1807cbcd0  test    r15, r15
0x1807cbcd3  jz      short loc_1807CBD0C
0x1807cbcd5  mov     eax, edi
0x1807cbcd7  lock xadd [r15+8], eax
0x1807cbcdd  add     eax, edi
0x1807cbcdf  jnz     short loc_1807CBD0C
0x1807cbce1  mov     rax, [r15]
0x1807cbce4  mov     rcx, r15
0x1807cbce7  mov     rax, [rax]
0x1807cbcea  call    cs:__guard_dispatch_icall_fptr
0x1807cbcf0  mov     eax, edi
0x1807cbcf2  lock xadd [r15+0Ch], eax
0x1807cbcf8  add     eax, edi
0x1807cbcfa  jnz     short loc_1807CBD0C
0x1807cbcfc  mov     rax, [r15]
0x1807cbcff  mov     rcx, r15
0x1807cbd02  mov     rax, [rax+8]
0x1807cbd06  call    cs:__guard_dispatch_icall_fptr
0x1807cbd0c  mov     ecx, 20h ; ' '
0x1807cbd11  call    sub_18001F710
0x1807cbd16  mov     r13, rax
0x1807cbd19  mov     [rsp+2D8h+var_288], rax
0x1807cbd1e  mov     [rax+8], r14d
0x1807cbd22  mov     [rax+0Ch], r14d
0x1807cbd26  lea     rax, ??_7?$_Ref_count_obj2@V?$map@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::map<ulong,std::string>>::`vftable'
0x1807cbd2d  mov     [r13+0], rax
0x1807cbd31  lea     r15, [r13+10h]
0x1807cbd35  mov     [rsp+2D8h+var_218], r15
0x1807cbd3d  mov     [r15], rbx
0x1807cbd40  mov     [r15+8], rbx
0x1807cbd44  lfence
0x1807cbd47  mov     ecx, 48h ; 'H'
0x1807cbd4c  call    sub_18001F710
0x1807cbd51  mov     [rax], rax
0x1807cbd54  mov     [rax+8], rax
0x1807cbd58  mov     [rax+10h], rax
0x1807cbd5c  mov     word ptr [rax+18h], 101h
0x1807cbd62  mov     [r15], rax
0x1807cbd65  mov     qword ptr [rsp+2D8h+var_228], r15
0x1807cbd6d  mov     qword ptr [rsp+2D8h+var_228+8], r13
0x1807cbd75  mov     r15, [rsp+2D8h+lpFileName]
0x1807cbd7a  mov     rax, [rsp+2D8h+var_238]
0x1807cbd82  jmp     short loc_1807CBDE9
0x1807cbd84  xor     ebx, ebx
0x1807cbd86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1807cbd8a  lea     r14d, [rbx+1]
0x1807cbd8e  mov     esi, dword ptr [rsp+2D8h+var_288]
0x1807cbd92  mov     r12, qword ptr [rsp+2D8h+var_248+8]
0x1807cbd9a  mov     r13, qword ptr [rsp+2D8h+var_228+8]
0x1807cbda2  mov     rcx, qword ptr [rsp+2D8h+var_228]
0x1807cbdaa  mov     [rsp+2D8h+var_218], rcx
0x1807cbdb2  mov     r15, [rsp+2D8h+var_1C0]
0x1807cbdba  mov     [rsp+2D8h+lpFileName], r15
0x1807cbdbf  mov     rax, [rsp+2D8h+var_200]
0x1807cbdc7  mov     [rsp+2D8h+var_298], rax
0x1807cbdcc  mov     rax, qword ptr [rsp+2D8h+var_258]
0x1807cbdd4  mov     [rsp+2D8h+var_268], rax
0x1807cbdd9  mov     rax, [rsp+2D8h+var_140]
0x1807cbde1  mov     [rsp+2D8h+var_238], rax
0x1807cbde9  mov     [rax], bl
0x1807cbdeb  test    esi, esi
0x1807cbded  jnz     short loc_1807CBE62
0x1807cbdef  mov     [rsp+2D8h+hTemplateFile], rbx; hTemplateFile
0x1807cbdf4  mov     [rsp+2D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1807cbdfc  mov     [rsp+2D8h+dwCreationDisposition], 3; int
0x1807cbe04  xor     r9d, r9d; lpSecurityAttributes
0x1807cbe07  mov     r8d, r14d; dwShareMode
0x1807cbe0a  mov     edx, 80000000h; dwDesiredAccess
0x1807cbe0f  mov     rcx, r15; lpFileName
0x1807cbe12  call    cs:__imp_CreateFileW
0x1807cbe18  mov     rcx, qword ptr [rsp+2D8h+var_1F8]
0x1807cbe20  mov     [rcx], rax
0x1807cbe23  cmp     rax, rdi
0x1807cbe26  jnz     loc_1807CBF11
0x1807cbe2c  lea     r15, hDevice
0x1807cbe33  mov     rcx, cs:hDevice
0x1807cbe3a  cmp     rcx, r15
0x1807cbe3d  jz      short loc_1807CBE5D
0x1807cbe3f  test    [rcx+1Ch], r14b
0x1807cbe43  jz      short loc_1807CBE5D
0x1807cbe45  lea     edx, [rsi+1Ah]
0x1807cbe48  mov     r9, [rsp+2D8h+lpFileName]
0x1807cbe4d  lea     r8, stru_180D0F860
0x1807cbe54  mov     rcx, [rcx+10h]
0x1807cbe58  call    sub_1801C8638
0x1807cbe5d  mov     esi, 8001h
0x1807cbe62  mov     rcx, [rsp+2D8h+var_298]
0x1807cbe67  call    sub_1807CC82C
0x1807cbe6c  nop
0x1807cbe6d  test    r13, r13
0x1807cbe70  jz      short loc_1807CBEAC
0x1807cbe72  mov     eax, edi
0x1807cbe74  lock xadd [r13+8], eax
0x1807cbe7a  add     eax, edi
0x1807cbe7c  jnz     short loc_1807CBEAC
0x1807cbe7e  mov     rax, [r13+0]
0x1807cbe82  mov     rcx, r13
0x1807cbe85  mov     rax, [rax]
0x1807cbe88  call    cs:__guard_dispatch_icall_fptr
0x1807cbe8e  mov     eax, edi
0x1807cbe90  lock xadd [r13+0Ch], eax
0x1807cbe96  add     eax, edi
0x1807cbe98  jnz     short loc_1807CBEAC
0x1807cbe9a  mov     rax, [r13+0]
0x1807cbe9e  mov     rcx, r13
0x1807cbea1  mov     rax, [rax+8]
0x1807cbea5  call    cs:__guard_dispatch_icall_fptr
0x1807cbeab  nop
0x1807cbeac  test    r12, r12
0x1807cbeaf  jz      short loc_1807CBEEC
0x1807cbeb1  mov     eax, edi
0x1807cbeb3  lock xadd [r12+8], eax
0x1807cbeba  add     eax, edi
0x1807cbebc  jnz     short loc_1807CBEEC
0x1807cbebe  mov     rax, [r12]
0x1807cbec2  mov     rcx, r12
0x1807cbec5  mov     rax, [rax]
0x1807cbec8  call    cs:__guard_dispatch_icall_fptr
0x1807cbece  mov     edx, edi
0x1807cbed0  lock xadd [r12+0Ch], edx
0x1807cbed7  add     edx, edi
0x1807cbed9  jnz     short loc_1807CBEEC
0x1807cbedb  mov     rdx, [r12]
0x1807cbedf  mov     rcx, r12
0x1807cbee2  mov     rax, [rdx+8]
0x1807cbee6  call    cs:__guard_dispatch_icall_fptr
0x1807cbeec  mov     eax, esi
0x1807cbeee  mov     rcx, [rsp+2D8h+var_40]
0x1807cbef6  xor     rcx, rsp; StackCookie
0x1807cbef9  call    __security_check_cookie
0x1807cbefe  add     rsp, 2A0h
0x1807cbf05  pop     r15
0x1807cbf07  pop     r14
0x1807cbf09  pop     r13
0x1807cbf0b  pop     r12
0x1807cbf0d  pop     rdi
0x1807cbf0e  pop     rsi
0x1807cbf0f  pop     rbx
0x1807cbf10  retn
0x1807cbf11  mov     rcx, [rsp+2D8h+var_208]
0x1807cbf19  cmp     [rcx], ebx
0x1807cbf1b  jl      short loc_1807CBF66
0x1807cbf1d  mov     rcx, rax
0x1807cbf20  call    sub_1802BADA4
0x1807cbf25  test    eax, eax
0x1807cbf27  jz      short loc_1807CBF66
0x1807cbf29  lea     r15, hDevice
0x1807cbf30  mov     rcx, cs:hDevice
0x1807cbf37  cmp     rcx, r15
0x1807cbf3a  jz      short loc_1807CBF5C
0x1807cbf3c  test    [rcx+1Ch], r14b
0x1807cbf40  jz      short loc_1807CBF5C
0x1807cbf42  mov     edx, 1Bh
0x1807cbf47  mov     r9, [rsp+2D8h+lpFileName]
0x1807cbf4c  lea     r8, stru_180D0F860
0x1807cbf53  mov     rcx, [rcx+10h]
0x1807cbf57  call    sub_1801C8638
0x1807cbf5c  mov     esi, 0A005h
0x1807cbf61  jmp     loc_1807CBE62
0x1807cbf66  xor     r8d, r8d; dwFlags
0x1807cbf69  xor     edx, edx; hFile
0x1807cbf6b  mov     rcx, r15; lpLibFileName
0x1807cbf6e  call    cs:LoadLibraryExW
0x1807cbf74  mov     r15, [rsp+2D8h+var_298]
0x1807cbf79  mov     [r15], rax
0x1807cbf7c  test    rax, rax
0x1807cbf7f  jnz     short loc_1807CBFD2
0x1807cbf81  lea     r15, hDevice
0x1807cbf88  mov     rax, cs:hDevice
0x1807cbf8f  cmp     rax, r15
0x1807cbf92  jz      loc_1807CBE5D
0x1807cbf98  test    [rax+1Ch], r14b
0x1807cbf9c  jz      loc_1807CBE5D
0x1807cbfa2  call    cs:__imp_GetLastError
0x1807cbfa8  mov     edx, 1Ch
0x1807cbfad  mov     [rsp+2D8h+dwCreationDisposition], eax
0x1807cbfb1  mov     r9, [rsp+2D8h+lpFileName]
0x1807cbfb6  lea     r8, stru_180D0F860
0x1807cbfbd  mov     rcx, cs:hDevice
0x1807cbfc4  mov     rcx, [rcx+10h]
0x1807cbfc8  call    sub_1801A569C
0x1807cbfcd  jmp     loc_1807CBE5D
0x1807cbfd2  lea     rdx, aRpfModuleUpdat; "rpf_module_update"
0x1807cbfd9  mov     rcx, rax; hModule
0x1807cbfdc  call    cs:GetProcAddress
0x1807cbfe2  mov     [r15+18h], rax
0x1807cbfe6  test    rax, rax
0x1807cbfe9  jnz     short loc_1807CC014
0x1807cbfeb  lea     r15, hDevice
0x1807cbff2  mov     rcx, cs:hDevice
0x1807cbff9  cmp     rcx, r15
0x1807cbffc  jz      loc_1807CBE5D
0x1807cc002  test    [rcx+1Ch], r14b
0x1807cc006  jz      loc_1807CBE5D
0x1807cc00c  lea     edx, [rax+1Dh]
0x1807cc00f  jmp     loc_1807CBE48
0x1807cc014  lea     rdx, aRpfModuleInit; "rpf_module_init"
0x1807cc01b  mov     rcx, [r15]; hModule
0x1807cc01e  call    cs:GetProcAddress
0x1807cc024  mov     r15, rax
0x1807cc027  test    rax, rax
0x1807cc02a  jnz     short loc_1807CC055
0x1807cc02c  lea     r15, hDevice
0x1807cc033  mov     rcx, cs:hDevice
0x1807cc03a  cmp     rcx, r15
0x1807cc03d  jz      loc_1807CBE5D
0x1807cc043  test    [rcx+1Ch], r14b
0x1807cc047  jz      loc_1807CBE5D
0x1807cc04d  lea     edx, [rax+1Eh]
0x1807cc050  jmp     loc_1807CBE48
0x1807cc055  call    sub_1802B9450
0x1807cc05a  mov     [rsp+2D8h+var_140], rax
0x1807cc062  lea     r8, [rsp+2D8h+var_140]
0x1807cc06a  lea     rdx, sub_1807CD400
0x1807cc071  lea     rcx, [rsp+2D8h+var_B8]
0x1807cc079  mov     rax, r15
0x1807cc07c  call    cs:__guard_dispatch_icall_fptr
0x1807cc082  mov     edx, eax
0x1807cc084  mov     al, cs:byte_18105B1D9
0x1807cc08a  neg     al
0x1807cc08c  sbb     ecx, ecx
0x1807cc08e  and     ecx, 80000000h
0x1807cc094  add     ecx, 65B8h
0x1807cc09a  mov     eax, edx
0x1807cc09c  btr     eax, 1Eh
0x1807cc0a0  cmp     eax, ecx
0x1807cc0a2  jz      short loc_1807CC0DD
0x1807cc0a4  lea     r15, hDevice
0x1807cc0ab  mov     rcx, cs:hDevice
0x1807cc0b2  cmp     rcx, r15
0x1807cc0b5  jz      short loc_1807CC0D3
0x1807cc0b7  test    [rcx+1Ch], r14b
0x1807cc0bb  jz      short loc_1807CC0D3
0x1807cc0bd  mov     r9, [rsp+2D8h+lpFileName]
0x1807cc0c2  mov     qword ptr [rsp+2D8h+dwFlagsAndAttributes], r9; __int64
0x1807cc0c7  mov     r9d, edx
0x1807cc0ca  mov     rcx, [rcx+10h]; LoggerHandle
0x1807cc0ce  call    sub_1807CD4A0
0x1807cc0d3  mov     esi, 800Eh
0x1807cc0d8  jmp     loc_1807CBE62
0x1807cc0dd  bt      edx, 1Eh
0x1807cc0e1  jnb     short loc_1807CC113
0x1807cc0e3  lea     r15, hDevice
0x1807cc0ea  mov     rcx, cs:hDevice
0x1807cc0f1  cmp     rcx, r15
0x1807cc0f4  jz      short loc_1807CC11A
0x1807cc0f6  test    byte ptr [rcx+1Ch], 2
0x1807cc0fa  jz      short loc_1807CC11A
  ... truncated ...
```
