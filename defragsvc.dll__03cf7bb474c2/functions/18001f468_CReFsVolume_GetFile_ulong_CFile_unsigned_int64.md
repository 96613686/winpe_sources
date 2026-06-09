# CReFsVolume::_GetFile(ulong *,_CFile *,unsigned __int64 *)

- ea: `0x18001f468`
- end: `0x18001fcf7`
- name: `?_GetFile@CReFsVolume@@AEAAJPEAKPEAU_CFile@@PEA_K@Z`
- size: `2191`
- prototype: `__int64 __fastcall(CReFsVolume *__hidden this, unsigned int *, struct _CFile *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f380`
- `0x18003d0b0`

## callees

- `0x180006400`
- `0x180008530`
- `0x18000ad50`
- `0x180010bc0`
- `0x1800156a0`
- `0x1800157fc`
- `0x180017e34`
- `0x18001913c`
- `0x180019228`
- `0x18001f468`
- `0x18001fd00`
- `0x18001fed8`
- `0x18001ff18`
- `0x18002e944`
- `0x18003835c`
- `0x18003905c`
- `0x180040760`
- `0x1800630ac`
- `0x180063370`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001f928`
- `msvcrt!_wcsicmp` at `0x18001f941`
- `msvcrt!_wcsicmp` at `0x18001f928`
- `msvcrt!_wcsicmp` at `0x18001f941`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f71e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f71e`
- `ntdll!NtQueryDirectoryFile` at `0x18001f801`
- `ntdll!NtQueryDirectoryFile` at `0x18001f801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f734`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f773`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f734`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f773`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fa09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f675`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fa09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc21`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CReFsVolume::_GetFile(CReFsVolume *this, unsigned int *a2, struct _CFile *a3, unsigned __int64 *a4)
{
  __int64 v7; // rbx
  struct _QUEUED_REFS_DIR *v8; // r12
  unsigned __int16 *v9; // r14
  unsigned int *v10; // rax
  __int64 v11; // rcx
  struct _CFile *v12; // rax
  bool v13; // zf
  __int16 v14; // ax
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // r13d
  __int16 v18; // ax
  _QWORD *v19; // rcx
  __int64 v20; // r14
  __int64 v21; // r14
  __int64 v22; // rcx
  _BYTE *v23; // rax
  LPVOID v24; // rax
  int v25; // r13d
  struct _QUEUED_DIR *v26; // rax
  char *FileW; // r15
  CFatVolume *v28; // rcx
  void *v29; // rcx
  _QWORD *v30; // r13
  NTSTATUS v31; // eax
  __int64 v32; // rcx
  unsigned int *v33; // rcx
  unsigned __int64 v34; // rax
  _DWORD *v35; // rdx
  int v36; // r15d
  char *v37; // rcx
  __int16 v38; // ax
  __int64 v39; // r15
  unsigned int v40; // r13d
  unsigned __int16 v41; // dx
  unsigned __int16 v42; // dx
  unsigned __int16 **v43; // rdx
  __int64 v44; // rcx
  unsigned __int16 **v45; // rax
  __int64 v46; // rdx
  unsigned int v47; // edx
  int HandleToFile; // r15d
  CReFsVolume *v49; // rcx
  unsigned int v50; // esi
  DWORD dwCreationDisposition[2]; // [rsp+28h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+30h] [rbp-D8h]
  unsigned int v54; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+6Ch] [rbp-9Ch]
  int v56; // [rsp+70h] [rbp-98h]
  int v57; // [rsp+78h] [rbp-90h] BYREF
  __int16 v58; // [rsp+7Ch] [rbp-8Ch]
  __int16 v59; // [rsp+7Eh] [rbp-8Ah]
  wchar_t *String1[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v61; // [rsp+C0h] [rbp-48h]
  unsigned int v62; // [rsp+C4h] [rbp-44h] BYREF
  unsigned __int16 *v63[2]; // [rsp+C8h] [rbp-40h] BYREF
  struct _QUEUED_DIR *v64; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v65; // [rsp+E0h] [rbp-28h]
  void *v66; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int16 *v67[4]; // [rsp+F0h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v57, "CReFsVolume::_GetFile", 1000, 1);
  v54 = 0;
  v7 = -1;
  v66 = (void *)-1LL;
  v62 = 0;
  v8 = 0;
  v67[2] = (unsigned __int16 *)&qword_18006F470;
  v67[3] = 0;
  v65 = -1;
  IoStatusBlock = 0;
  v9 = (unsigned __int16 *)&qword_18006F470;
  String1[0] = (wchar_t *)&qword_18006F470;
  String1[1] = 0;
  v63[0] = (unsigned __int16 *)&qword_18006F470;
  v63[1] = 0;
  v67[0] = (unsigned __int16 *)&qword_18006F470;
  v67[1] = 0;
  v10 = a2;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
  {
    v11 = 16;
    v12 = a3;
    do
    {
      *(_BYTE *)v12 = 0;
      v12 = (struct _CFile *)((char *)v12 + 1);
      --v11;
    }
    while ( v11 );
    v10 = a2;
  }
  if ( a4 )
    *a4 = 0;
  v13 = v10 == 0;
  v14 = 1028;
  if ( v13 || (v58 = 1028, v14 = 1029, !a3) || (v58 = 1029, v14 = 1030, !a4) )
  {
    v57 = -2147024809;
    goto LABEL_104;
  }
  v57 = 0;
  v58 = 1030;
  v57 = CBulkAllocator<_CExtent>::Alloc(*((_QWORD *)this + 135), &v54);
  v17 = v54;
  v18 = 1032;
  if ( v57 < 0 )
    goto LABEL_99;
  v58 = 1032;
  v14 = 1033;
  if ( !v54 )
  {
    v57 = -2147024882;
LABEL_104:
    v59 = v14;
    goto LABEL_105;
  }
  v57 = 0;
  v58 = 1033;
  v15 = *((_QWORD *)this + 135);
  if ( !*(_DWORD *)(v15 + 28) )
  {
    v57 = -2147467259;
LABEL_98:
    v18 = 1035;
    goto LABEL_99;
  }
  if ( (v54 & 0xF0000000) != *(_DWORD *)(v15 + 28)
    || (v16 = ((unsigned __int16)v54 - 1) & (unsigned int)-((unsigned __int16)v54 != 0),
        (v19 = *(_QWORD **)(*(_QWORD *)(v15 + 8) + 8 * (((unsigned __int64)v54 >> 16) & 0xFFF))) == 0)
    || (unsigned int)v16 >= *(_DWORD *)(v15 + 20) )
  {
    v57 = -2147024809;
    goto LABEL_98;
  }
  v20 = *(_QWORD *)(v15 + 32) * (unsigned int)v16;
  v13 = *v19 + v20 == 0;
  v21 = *v19 + v20;
  v58 = 1035;
  v18 = 1036;
  if ( v13 )
  {
    v57 = -2147024882;
    goto LABEL_89;
  }
  v57 = 0;
  v58 = 1036;
  v22 = 24;
  v23 = (_BYTE *)v21;
  do
  {
    *v23++ = 0;
    --v22;
  }
  while ( v22 );
  if ( !*((_QWORD *)this + 132) )
  {
    v24 = CoTaskMemAlloc(0x40000u);
    *((_QWORD *)this + 132) = v24;
    v22 = 1045;
    if ( !v24 )
    {
      v57 = -2147024882;
      v59 = 1045;
LABEL_43:
      v9 = String1[0];
      goto LABEL_100;
    }
    v57 = 0;
    v58 = 1045;
    *((_QWORD *)this + 133) = v24;
    *((_DWORD *)this + 268) = 0x40000;
  }
  v16 = 0;
  v55 = 0;
  v25 = 0;
  v56 = 0;
  while ( *((_QWORD *)this + 129) )
  {
    if ( (_DWORD)v16 )
      goto LABEL_81;
    v26 = CReFsVolume::PopDir(this);
    v8 = v26;
    v64 = v26;
    FileW = (char *)*((_QWORD *)this + 131);
    v22 = (__int64)(FileW - 1);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      FileW = (char *)CreateFileW(*(LPCWSTR *)v26, 0x89u, 1u, 0, 3u, 0x2000000u, 0);
      v65 = (__int64)FileW;
      if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        CFatVolume::FreeDir(v28, &v64);
        v8 = CReFsVolume::PopDir(this);
        v64 = v8;
      }
      v22 = *((_QWORD *)this + 131);
      if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle((HANDLE)v22);
        *((_QWORD *)this + 131) = -1;
      }
      *((_QWORD *)this + 131) = FileW;
      v65 = -1;
      v16 = v55;
    }
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_74;
    v29 = (void *)*((_QWORD *)this + 132);
    v30 = (_QWORD *)((char *)this + 1064);
    if ( v29 == *((void **)this + 133) )
    {
      v61 = 1;
      v31 = NtQueryDirectoryFile(
              FileW,
              0,
              0,
              0,
              &IoStatusBlock,
              v29,
              *((_DWORD *)this + 268),
              FileBothDirectoryInformation,
              0,
              &CReFsVolume::s_ustrFileMask,
              0);
      if ( (unsigned int)IsNtStatusBufferTooSmall(v31) )
      {
        v33 = (unsigned int *)*((_QWORD *)this + 132);
        v34 = *v33;
        if ( (_DWORD)v34 )
        {
          do
          {
            v35 = v33;
            v33 += v34 >> 2;
            v34 = *v33;
          }
          while ( (_DWORD)v34 );
          if ( v35 )
            *v35 = 0;
        }
        v36 = v61;
        goto LABEL_50;
      }
      if ( (_DWORD)v32 == -2147483642 || (_DWORD)v32 == -1073741809 )
      {
        *v30 = *((_QWORD *)this + 132);
        v37 = (char *)*((_QWORD *)this + 131);
        if ( (unsigned __int64)(v37 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(v37);
          *((_QWORD *)this + 131) = -1;
        }
        CFatVolume::FreeDir((CFatVolume *)v37, &v64);
        v8 = CReFsVolume::PopDir(this);
        v36 = 0;
LABEL_50:
        v32 = 0;
      }
      else
      {
        v36 = v61;
      }
      v57 = HRESULTFromNTSTATUS(v32);
      v38 = 1151;
      if ( v57 < 0 )
        goto LABEL_78;
      v58 = 1151;
      if ( !v36 )
        goto LABEL_73;
    }
    if ( *(_DWORD *)*v30 )
      v39 = *v30 + *(unsigned int *)*v30;
    else
      v39 = *((_QWORD *)this + 132);
    *v30 = v39;
    v57 = CBsString::Set((CBsString *)String1, (const unsigned __int16 *)(v39 + 94), *(_DWORD *)(v39 + 60) >> 1);
    v38 = 1179;
    if ( v57 < 0 )
      goto LABEL_78;
    v58 = 1179;
    v40 = *(_DWORD *)(v39 + 56);
    v62 = v40;
    if ( !_wcsicmp(String1[0], L"..") || !_wcsicmp(String1[0], L".") )
    {
LABEL_73:
      v16 = v55;
      v25 = v56;
      goto LABEL_74;
    }
    v57 = CBsString::Set((CBsString *)v63, *(const unsigned __int16 **)v8);
    v38 = 1191;
    if ( v57 < 0 )
      goto LABEL_78;
    v58 = 1191;
    v57 = CBsString::Trailing((CBsString *)v63, v41);
    v38 = 1192;
    if ( v57 < 0 )
      goto LABEL_78;
    v58 = 1192;
    v57 = CBsString::Append((CBsString *)v63, String1[0]);
    v38 = 1193;
    if ( v57 < 0 )
      goto LABEL_78;
    v58 = 1193;
    if ( (v40 & 0x10) != 0 )
    {
      v57 = CBsString::Trailing((CBsString *)v63, v42);
      v38 = 1200;
      if ( v57 < 0 )
        goto LABEL_78;
      v58 = 1200;
      v57 = CBsString::Set((CBsString *)v67, v63[0]);
      v38 = 1201;
      if ( v57 < 0 )
        goto LABEL_78;
      v58 = 1201;
      v43 = (unsigned __int16 **)CoTaskMemAlloc(0x10u);
      v38 = 1206;
      if ( !v43 )
      {
        v57 = -2147024882;
LABEL_78:
        v59 = v38;
        v17 = v54;
LABEL_94:
        if ( v8 )
        {
          CoTaskMemFree(*(LPVOID *)v8);
          *(_QWORD *)v8 = 0;
          CoTaskMemFree(v8);
        }
        goto LABEL_43;
      }
      v57 = 0;
      v58 = 1206;
      v44 = 16;
      v45 = v43;
      do
      {
        *(_BYTE *)v45 = 0;
        v45 = (unsigned __int16 **)((char *)v45 + 1);
        --v44;
      }
      while ( v44 );
      CBsString::Detach((CBsString *)v67, v43);
      *(_QWORD *)(v46 + 8) = *((_QWORD *)this + 129);
      *((_QWORD *)this + 129) = v46;
      v25 = 1;
    }
    else
    {
      v47 = *((_DWORD *)this + 122);
      if ( v47 )
        *((_QWORD *)this + 130) += (*(unsigned int *)(v39 + 48) | (unsigned __int64)((__int64)*(int *)(v39 + 52) << 32))
                                 / v47;
      v25 = 0;
    }
    v56 = v25;
    v55 = 1;
    CBsString::Detach((CBsString *)v63, (unsigned __int16 **)(v21 + 16));
LABEL_74:
    if ( v8 )
      *((_QWORD *)v8 + 1) = *((_QWORD *)this + 129);
    *((_QWORD *)this + 129) = v8;
    v8 = 0;
  }
  if ( !(_DWORD)v16 )
  {
    v57 = 1;
    v58 = 1240;
    v17 = v54;
    goto LABEL_43;
  }
LABEL_81:
  HandleToFile = CReFsVolume::_GetHandleToFile((CReFsVolume *)v22, (struct CReFsFile *)v21, &v66);
  v7 = (__int64)v66;
  if ( HandleToFile >= 0 )
  {
    v17 = v54;
    v57 = CReFsVolume::_ScanFileFromHandle(this, v66, &v62, (struct CReFsFile *)v21, v54);
    v18 = 1267;
    if ( v57 < 0 )
      goto LABEL_89;
    v58 = 1267;
  }
  else
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_4e29b8698edf3a105c9a10e57668ab3f_Traceguids,
        *(_QWORD *)(v21 + 16));
    }
    *(_DWORD *)(v21 + 4) |= 0x41u;
    if ( v25 )
      *(_DWORD *)(v21 + 4) |= 4u;
    v17 = v54;
    if ( HandleToFile != -1996488674 )
    {
      v57 = HandleToFile;
      v18 = 1261;
      goto LABEL_89;
    }
  }
  v57 = CReFsVolume::_SetSystemFlags(v49, String1[0], (struct CReFsFile *)v21);
  v18 = 1271;
  if ( v57 >= 0 )
  {
    v58 = 1271;
    *a4 = *((_QWORD *)this + 130);
    *(_OWORD *)a3 = *(_OWORD *)v21;
    *a2 = v17;
    v17 = 0;
    v54 = 0;
    v57 = 0;
    goto LABEL_94;
  }
LABEL_89:
  v9 = String1[0];
LABEL_99:
  v59 = v18;
LABEL_100:
  if ( v17 )
    CBulkAllocator<_CExtent>::Free(
      *((_QWORD *)this + 135),
      &v54,
      v15,
      v16,
      *(_QWORD *)dwCreationDisposition,
      *(_QWORD *)dwFlagsAndAttributes);
LABEL_105:
  v50 = v57;
  CBsString::_FreeData(v67[0]);
  CBsString::_FreeData(v63[0]);
  CBsString::_FreeData(v9);
  CBsString::_FreeData((unsigned __int16 *)&qword_18006F470);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v57);
  return v50;
}

```

## disassembly

```asm
0x18001f468  mov     rax, rsp
0x18001f46b  mov     [rax+8], rbx
0x18001f46f  mov     [rax+20h], r9
0x18001f473  mov     [rax+18h], r8
0x18001f477  mov     [rax+10h], rdx
0x18001f47b  push    rbp
0x18001f47c  push    rsi
0x18001f47d  push    rdi
0x18001f47e  push    r12
0x18001f480  push    r13
0x18001f482  push    r14
0x18001f484  push    r15
0x18001f486  lea     rbp, [rax-58h]
0x18001f48a  sub     rsp, 120h
0x18001f491  mov     r15, r9
0x18001f494  mov     r13, r8
0x18001f497  mov     rsi, rcx
0x18001f49a  mov     r9d, 1; unsigned __int16
0x18001f4a0  mov     r8d, 3E8h; unsigned __int16
0x18001f4a6  lea     rdx, aCrefsvolumeGet_3; "CReFsVolume::_GetFile"
0x18001f4ad  lea     rcx, [rsp+150h+var_E0]; this
0x18001f4b2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f4b7  nop
0x18001f4b8  xor     edx, edx; unsigned int
0x18001f4ba  mov     [rsp+150h+var_F0], edx
0x18001f4be  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001f4c2  mov     [rbp+50h+var_70], rbx
0x18001f4c6  mov     [rbp+50h+var_94], edx
0x18001f4c9  mov     r12d, edx
0x18001f4cc  lea     rax, qword_18006F470
0x18001f4d3  mov     [rbp+50h+var_58], rax
0x18001f4d7  mov     [rbp+50h+var_50], rdx
0x18001f4db  mov     rdi, rbx
0x18001f4de  mov     [rbp+50h+var_78], rbx
0x18001f4e2  xorps   xmm0, xmm0
0x18001f4e5  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18001f4e9  mov     r14, rax
0x18001f4ec  mov     [rbp+50h+String1], rax
0x18001f4f0  mov     [rbp+50h+var_A0], rdx
0x18001f4f4  mov     [rbp+50h+var_90], rax
0x18001f4f8  mov     [rbp+50h+var_88], rdx
0x18001f4fc  mov     [rbp+50h+var_68], rax
0x18001f500  mov     [rbp+50h+var_60], rdx
0x18001f504  mov     rax, [rbp+50h+arg_8]
0x18001f508  test    rax, rax
0x18001f50b  jz      short loc_18001F50F
0x18001f50d  mov     [rax], edx
0x18001f50f  test    r13, r13
0x18001f512  jz      short loc_18001F52B
0x18001f514  mov     ecx, 10h
0x18001f519  mov     rax, r13
0x18001f51c  mov     [rax], dl
0x18001f51e  inc     rax
0x18001f521  sub     rcx, 1
0x18001f525  jnz     short loc_18001F51C
0x18001f527  mov     rax, [rbp+50h+arg_8]
0x18001f52b  test    r15, r15
0x18001f52e  jz      short loc_18001F533
0x18001f530  mov     [r15], rdx
0x18001f533  test    rax, rax
0x18001f536  mov     eax, 404h
0x18001f53b  jz      loc_18001FC6D
0x18001f541  mov     [rsp+150h+var_DC], ax
0x18001f546  mov     eax, 405h
0x18001f54b  test    r13, r13
0x18001f54e  jz      loc_18001FC6D
0x18001f554  mov     [rsp+150h+var_DC], ax
0x18001f559  mov     eax, 406h
0x18001f55e  test    r15, r15
0x18001f561  jz      loc_18001FC6D
0x18001f567  mov     [rsp+150h+var_E0], edx
0x18001f56b  mov     [rsp+150h+var_DC], ax
0x18001f570  lea     rdx, [rsp+150h+var_F0]
0x18001f575  mov     rcx, [rsi+438h]
0x18001f57c  call    ?Alloc@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Alloc(ulong *)
0x18001f581  mov     [rsp+150h+var_E0], eax
0x18001f585  mov     r13d, [rsp+150h+var_F0]
0x18001f58a  test    eax, eax
0x18001f58c  mov     eax, 408h
0x18001f591  js      loc_18001FC46
0x18001f597  mov     [rsp+150h+var_DC], ax
0x18001f59c  mov     eax, 409h
0x18001f5a1  test    r13d, r13d
0x18001f5a4  jz      loc_18001FC63
0x18001f5aa  mov     [rsp+150h+var_E0], 0
0x18001f5b2  mov     [rsp+150h+var_DC], ax
0x18001f5b7  mov     r8, [rsi+438h]
0x18001f5be  cmp     dword ptr [r8+1Ch], 0
0x18001f5c3  ja      short loc_18001F5D2
0x18001f5c5  mov     [rsp+150h+var_E0], 80004005h
0x18001f5cd  jmp     loc_18001FC41
0x18001f5d2  mov     edx, r13d
0x18001f5d5  mov     eax, r13d
0x18001f5d8  and     eax, 0F0000000h
0x18001f5dd  cmp     eax, [r8+1Ch]
0x18001f5e1  jnz     loc_18001FC39
0x18001f5e7  test    edx, edx
0x18001f5e9  jz      loc_18001FC39
0x18001f5ef  movzx   eax, dx
0x18001f5f2  lea     ecx, [rax-1]
0x18001f5f5  neg     eax
0x18001f5f7  sbb     r9d, r9d
0x18001f5fa  and     r9d, ecx
0x18001f5fd  shr     rdx, 10h
0x18001f601  and     edx, 0FFFh
0x18001f607  mov     rax, [r8+8]
0x18001f60b  mov     rcx, [rax+rdx*8]
0x18001f60f  test    rcx, rcx
0x18001f612  jz      loc_18001FC39
0x18001f618  cmp     r9d, [r8+14h]
0x18001f61c  jnb     loc_18001FC39
0x18001f622  mov     r14d, r9d
0x18001f625  imul    r14, [r8+20h]
0x18001f62a  add     r14, [rcx]
0x18001f62d  mov     eax, 40Bh
0x18001f632  mov     [rsp+150h+var_DC], ax
0x18001f637  mov     eax, 40Ch
0x18001f63c  jz      loc_18001FC2C
0x18001f642  mov     [rsp+150h+var_E0], 0
0x18001f64a  mov     [rsp+150h+var_DC], ax
0x18001f64f  mov     ecx, 18h
0x18001f654  mov     rax, r14
0x18001f657  mov     byte ptr [rax], 0
0x18001f65a  inc     rax
0x18001f65d  sub     rcx, 1
0x18001f661  jnz     short loc_18001F657
0x18001f663  cmp     [rsi+420h], rcx
0x18001f66a  jnz     short loc_18001F6AB
0x18001f66c  mov     r15d, 40000h
0x18001f672  mov     ecx, r15d; cb
0x18001f675  call    cs:__imp_CoTaskMemAlloc
0x18001f67b  mov     [rsi+420h], rax
0x18001f682  mov     ecx, 415h; this
0x18001f687  test    rax, rax
0x18001f68a  jz      loc_18001F83D
0x18001f690  mov     [rsp+150h+var_E0], 0
0x18001f698  mov     [rsp+150h+var_DC], cx
0x18001f69d  mov     [rsi+428h], rax
0x18001f6a4  mov     [rsi+430h], r15d
0x18001f6ab  xor     r9d, r9d
0x18001f6ae  mov     [rsp+150h+var_EC], r9d
0x18001f6b3  xor     r13d, r13d
0x18001f6b6  mov     [rsp+150h+var_E8], r13d
0x18001f6bb  cmp     qword ptr [rsi+408h], 0
0x18001f6c3  jz      loc_18001FAEC
0x18001f6c9  test    r9d, r9d
0x18001f6cc  jnz     loc_18001FB0D
0x18001f6d2  mov     rcx, rsi; this
0x18001f6d5  call    ?PopDir@CReFsVolume@@AEAAPEAU_QUEUED_REFS_DIR@@XZ; CReFsVolume::PopDir(void)
0x18001f6da  mov     r12, rax
0x18001f6dd  mov     [rbp+50h+var_80], rax
0x18001f6e1  mov     r15, [rsi+418h]
0x18001f6e8  lea     rcx, [r15-1]
0x18001f6ec  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001f6f0  jbe     loc_18001F793
0x18001f6f6  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x18001f6ff  mov     [rsp+150h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001f707  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x18001f70f  xor     r9d, r9d; lpSecurityAttributes
0x18001f712  mov     edx, 89h; dwDesiredAccess
0x18001f717  lea     r8d, [r9+1]; dwShareMode
0x18001f71b  mov     rcx, [rax]; lpFileName
0x18001f71e  call    cs:__imp_CreateFileW
0x18001f724  mov     r15, rax
0x18001f727  lea     rax, [rdi-1]
0x18001f72b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f72f  ja      short loc_18001F73A
0x18001f731  mov     rcx, rdi; hObject
0x18001f734  call    cs:__imp_CloseHandle
0x18001f73a  mov     [rbp+50h+var_78], r15
0x18001f73e  lea     rax, [r15+1]
0x18001f742  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001f748  jnz     short loc_18001F762
0x18001f74a  lea     rdx, [rbp+50h+var_80]; struct _QUEUED_DIR **
0x18001f74e  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x18001f753  mov     rcx, rsi; this
0x18001f756  call    ?PopDir@CReFsVolume@@AEAAPEAU_QUEUED_REFS_DIR@@XZ; CReFsVolume::PopDir(void)
0x18001f75b  mov     r12, rax
0x18001f75e  mov     [rbp+50h+var_80], rax
0x18001f762  mov     rcx, [rsi+418h]; hObject
0x18001f769  lea     rax, [rcx-1]
0x18001f76d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f771  ja      short loc_18001F780
0x18001f773  call    cs:__imp_CloseHandle
0x18001f779  mov     [rsi+418h], rbx
0x18001f780  mov     [rsi+418h], r15
0x18001f787  mov     rdi, rbx
0x18001f78a  mov     [rbp+50h+var_78], rbx
0x18001f78e  mov     r9d, [rsp+150h+var_EC]
0x18001f793  lea     rax, [r15-1]
0x18001f797  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f79b  ja      loc_18001FAB5
0x18001f7a1  mov     rcx, [rsi+420h]
0x18001f7a8  lea     r13, [rsi+428h]
0x18001f7af  cmp     rcx, [r13+0]
0x18001f7b3  jnz     loc_18001F8CF
0x18001f7b9  mov     [rbp+50h+var_98], 1
0x18001f7c0  mov     byte ptr [rsp+50h], 0; RestartScan
0x18001f7c5  lea     rax, ?s_ustrFileMask@CReFsVolume@@0U_UNICODE_STRING@@A; _UNICODE_STRING CReFsVolume::s_ustrFileMask
0x18001f7cc  mov     [rsp+150h+FileName], rax; FileName
0x18001f7d1  mov     [rsp+150h+ReturnSingleEntry], 0; ReturnSingleEntry
0x18001f7d6  mov     [rsp+150h+FileInformationClass], 3; FileInformationClass
0x18001f7de  mov     eax, [rsi+430h]
0x18001f7e4  mov     dword ptr [rsp+150h+hTemplateFile], eax; Length
0x18001f7e8  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rcx; FileInformation
0x18001f7ed  lea     rax, [rbp+50h+IoStatusBlock]
0x18001f7f1  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; IoStatusBlock
0x18001f7f6  xor     r9d, r9d; ApcContext
0x18001f7f9  xor     r8d, r8d; ApcRoutine
0x18001f7fc  xor     edx, edx; Event
0x18001f7fe  mov     rcx, r15; FileHandle
0x18001f801  call    cs:__imp_NtQueryDirectoryFile
0x18001f807  mov     ecx, eax; int
0x18001f809  call    ?IsNtStatusBufferTooSmall@@YAHJ@Z; IsNtStatusBufferTooSmall(long)
0x18001f80e  test    eax, eax
0x18001f810  jz      short loc_18001F853
0x18001f812  mov     rcx, [rsi+420h]
0x18001f819  mov     eax, [rcx]
0x18001f81b  test    eax, eax
0x18001f81d  jz      short loc_18001F837
0x18001f81f  mov     rdx, rcx
0x18001f822  shr     rax, 2
0x18001f826  lea     rcx, [rcx+rax*4]
0x18001f82a  mov     eax, [rcx]
0x18001f82c  test    eax, eax
0x18001f82e  jnz     short loc_18001F81F
0x18001f830  test    rdx, rdx
0x18001f833  jz      short loc_18001F837
0x18001f835  mov     [rdx], eax
0x18001f837  mov     r15d, [rbp+50h+var_98]
0x18001f83b  jmp     short loc_18001F8A9
0x18001f83d  mov     [rsp+150h+var_E0], 8007000Eh
0x18001f845  mov     [rsp+150h+var_DA], cx
0x18001f84a  mov     r14, [rbp+50h+String1]
0x18001f84e  jmp     loc_18001FC4B
0x18001f853  cmp     ecx, 80000006h
0x18001f859  jz      short loc_18001F869
0x18001f85b  cmp     ecx, 0C000000Fh
0x18001f861  jz      short loc_18001F869
0x18001f863  mov     r15d, [rbp+50h+var_98]
0x18001f867  jmp     short loc_18001F8AB
0x18001f869  mov     rax, [rsi+420h]
0x18001f870  mov     [r13+0], rax
0x18001f874  mov     rcx, [rsi+418h]; hObject
0x18001f87b  lea     rax, [rcx-1]
0x18001f87f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f883  ja      short loc_18001F892
0x18001f885  call    cs:__imp_CloseHandle
0x18001f88b  mov     [rsi+418h], rbx
0x18001f892  lea     rdx, [rbp+50h+var_80]; struct _QUEUED_DIR **
0x18001f896  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x18001f89b  mov     rcx, rsi; this
0x18001f89e  call    ?PopDir@CReFsVolume@@AEAAPEAU_QUEUED_REFS_DIR@@XZ; CReFsVolume::PopDir(void)
0x18001f8a3  mov     r12, rax
0x18001f8a6  xor     r15d, r15d
0x18001f8a9  xor     ecx, ecx
0x18001f8ab  call    HRESULTFromNTSTATUS
0x18001f8b0  mov     [rsp+150h+var_E0], eax
0x18001f8b4  test    eax, eax
0x18001f8b6  mov     eax, 47Fh
0x18001f8bb  js      loc_18001FADD
0x18001f8c1  mov     [rsp+150h+var_DC], ax
0x18001f8c6  test    r15d, r15d
0x18001f8c9  jz      loc_18001FAAB
0x18001f8cf  mov     rax, [r13+0]
0x18001f8d3  cmp     dword ptr [rax], 0
0x18001f8d6  jz      short loc_18001F8E0
0x18001f8d8  mov     r15d, [rax]
0x18001f8db  add     r15, rax
0x18001f8de  jmp     short loc_18001F8E7
0x18001f8e0  mov     r15, [rsi+420h]
0x18001f8e7  mov     [r13+0], r15
0x18001f8eb  mov     r8d, [r15+3Ch]
0x18001f8ef  shr     r8d, 1; unsigned int
0x18001f8f2  lea     rdx, [r15+5Eh]; unsigned __int16 *
0x18001f8f6  lea     rcx, [rbp+50h+String1]; this
0x18001f8fa  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x18001f8ff  mov     [rsp+150h+var_E0], eax
0x18001f903  test    eax, eax
0x18001f905  mov     eax, 49Bh
0x18001f90a  js      loc_18001FADD
0x18001f910  mov     [rsp+150h+var_DC], ax
0x18001f915  mov     r13d, [r15+38h]
0x18001f919  mov     [rbp+50h+var_94], r13d
0x18001f91d  lea     rdx, asc_1800704C8; ".."
0x18001f924  mov     rcx, [rbp+50h+String1]; String1
0x18001f928  call    cs:__imp__wcsicmp
0x18001f92e  test    eax, eax
0x18001f930  jz      loc_18001FAAB
0x18001f936  lea     rdx, asc_1800704DC; "."
0x18001f93d  mov     rcx, [rbp+50h+String1]; String1
0x18001f941  call    cs:__imp__wcsicmp
0x18001f947  test    eax, eax
0x18001f949  jz      loc_18001FAAB
0x18001f94f  mov     rdx, [r12]; unsigned __int16 *
0x18001f953  lea     rcx, [rbp+50h+var_90]; this
0x18001f957  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001f95c  mov     [rsp+150h+var_E0], eax
0x18001f960  test    eax, eax
0x18001f962  mov     eax, 4A7h
  ... truncated ...
```
