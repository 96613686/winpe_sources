# CWordWheelCompiler::Initialize(void)

- ea: `0x180074e14`
- end: `0x180075522`
- name: `?Initialize@CWordWheelCompiler@@QEAAJXZ`
- size: `1806`
- prototype: `__int64 __fastcall(CWordWheelCompiler *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800729f0`
- `0x180072b54`

## callees

- `0x180001728`
- `0x1800095c8`
- `0x18002a670`
- `0x18002aa24`
- `0x18002ae50`
- `0x18004f538`
- `0x180065438`
- `0x180073638`
- `0x180074e14`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180074f23`
- `KERNEL32!DeleteFileA` at `0x180074f23`
- `KERNEL32!GetTempPath2A` at `0x180074ed2`
- `KERNEL32!GetTempPath2A` at `0x180074ed2`
- `KERNEL32!GetSystemDefaultLCID` at `0x180075203`
- `KERNEL32!GetSystemDefaultLCID` at `0x180075203`
- `KERNEL32!GetTempFileNameA` at `0x180074f0e`
- `KERNEL32!GetTempFileNameA` at `0x180074f0e`
- `KERNEL32!GetLocaleInfoA` at `0x180075221`
- `KERNEL32!GetLocaleInfoA` at `0x180075221`
- `ole32!CoCreateInstance` at `0x180074fab`
- `ole32!CoCreateInstance` at `0x180075033`
- `ole32!CoCreateInstance` at `0x18007505c`
- `ole32!CoCreateInstance` at `0x180075085`
- `ole32!CoCreateInstance` at `0x180074fab`
- `ole32!CoCreateInstance` at `0x180075033`
- `ole32!CoCreateInstance` at `0x18007505c`
- `ole32!CoCreateInstance` at `0x180075085`

## pseudocode

```c
__int64 __fastcall CWordWheelCompiler::Initialize(CWordWheelCompiler *this)
{
  _WORD *v3; // rax
  _WORD *v4; // rax
  const char *v5; // r8
  const CHAR *v6; // rbx
  _QWORD *v7; // rax
  int v8; // r15d
  _QWORD *v9; // r13
  __int64 v10; // rcx
  HRESULT Instance; // r12d
  LCID SystemDefaultLCID; // eax
  unsigned int v13; // esi
  __int64 v14; // rcx
  __int128 v15; // xmm15
  __int128 v16; // xmm14
  __int128 v17; // xmm13
  __int128 v18; // xmm12
  __int128 v19; // xmm11
  __int128 v20; // xmm10
  __int128 v21; // xmm9
  __int128 v22; // xmm8
  __int128 v23; // xmm7
  __int128 v24; // xmm6
  int v25; // edi
  int v26; // ebx
  __int64 v27; // r8
  void (__fastcall *v28)(__int64, _QWORD, __int64, _QWORD, int, __m256i *, __m256i *); // rax
  int v29; // edx
  __int64 *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  int v33; // edx
  void (__fastcall *v34)(__int64 *, _QWORD, __int64, _QWORD, int, __m256i *, __m256i *); // rax
  unsigned int v35; // [rsp+48h] [rbp-C0h] BYREF
  __m256i v36; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+78h] [rbp-90h]
  __int128 v38; // [rsp+88h] [rbp-80h]
  __int128 v39; // [rsp+98h] [rbp-70h]
  __int128 v40; // [rsp+A8h] [rbp-60h]
  __int128 v41; // [rsp+B8h] [rbp-50h]
  __int128 v42; // [rsp+C8h] [rbp-40h]
  __int128 v43; // [rsp+D8h] [rbp-30h]
  __int128 v44; // [rsp+E8h] [rbp-20h]
  int v45; // [rsp+F8h] [rbp-10h]
  __m256i v46; // [rsp+108h] [rbp+0h] BYREF
  __int128 v47; // [rsp+128h] [rbp+20h]
  __int128 v48; // [rsp+138h] [rbp+30h]
  __int128 v49; // [rsp+148h] [rbp+40h]
  __int128 v50; // [rsp+158h] [rbp+50h]
  __int128 v51; // [rsp+168h] [rbp+60h]
  __int128 v52; // [rsp+178h] [rbp+70h]
  __int128 v53; // [rsp+188h] [rbp+80h]
  __int128 v54; // [rsp+198h] [rbp+90h]
  int v55; // [rsp+1A8h] [rbp+A0h]
  __m256i v56; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v57; // [rsp+1D8h] [rbp+D0h]
  __int128 v58; // [rsp+1E8h] [rbp+E0h]
  __int128 v59; // [rsp+1F8h] [rbp+F0h]
  __int128 v60; // [rsp+208h] [rbp+100h]
  __int128 v61; // [rsp+218h] [rbp+110h]
  __int128 v62; // [rsp+228h] [rbp+120h]
  __int128 v63; // [rsp+238h] [rbp+130h]
  __int128 v64; // [rsp+248h] [rbp+140h]
  int v65; // [rsp+258h] [rbp+150h]
  _QWORD *v66; // [rsp+268h] [rbp+160h]
  __m256i v67; // [rsp+278h] [rbp+170h] BYREF
  __int128 v68; // [rsp+298h] [rbp+190h]
  __int128 v69; // [rsp+2A8h] [rbp+1A0h]
  __int128 v70; // [rsp+2B8h] [rbp+1B0h]
  __int128 v71; // [rsp+2C8h] [rbp+1C0h]
  __int128 v72; // [rsp+2D8h] [rbp+1D0h]
  __int128 v73; // [rsp+2E8h] [rbp+1E0h]
  __int128 v74; // [rsp+2F8h] [rbp+1F0h]
  __int128 v75; // [rsp+308h] [rbp+200h]
  int v76; // [rsp+318h] [rbp+210h]
  CHAR LCData[5]; // [rsp+328h] [rbp+220h] BYREF
  __int64 v78; // [rsp+32Dh] [rbp+225h]
  int v79; // [rsp+335h] [rbp+22Dh]
  __int16 v80; // [rsp+339h] [rbp+231h]
  char v81; // [rsp+33Bh] [rbp+233h]
  CHAR PathName[272]; // [rsp+348h] [rbp+240h] BYREF
  unsigned __int16 v83[264]; // [rsp+458h] [rbp+350h] BYREF
  unsigned __int16 v84[264]; // [rsp+668h] [rbp+560h] BYREF

  if ( *((_DWORD *)this + 6) )
    return 0;
  v3 = (_WORD *)*((_QWORD *)this + 5);
  if ( !v3 )
    return 1;
  if ( !*v3 )
    return 1;
  v4 = (_WORD *)*((_QWORD *)this + 6);
  if ( !v4 || !*v4 )
    return 1;
  GetTempPath2A(260, PathName);
  v5 = (const char *)*((_QWORD *)this + 4);
  if ( v5 && *v5 )
  {
    v6 = (char *)this + 60;
    StringCchCopyA((char *)this + 60, 0x104u, v5);
  }
  else
  {
    v6 = (char *)this + 60;
    GetTempFileNameA(PathName, "TFS", 0, (LPSTR)this + 60);
  }
  if ( (unsigned int)IsFile(v6) )
    DeleteFileA(v6);
  v7 = operator new(0x118u);
  v66 = v7;
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = 0;
    *((_BYTE *)v7 + 16) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 40) = v7;
  if ( !v7
    || (int)CFileSystem::Init((CFileSystem *)v7) < 0
    || CFileSystem::CreateUncompressed(*((CFileSystem **)this + 40), v6) < 0 )
  {
    return 1;
  }
  v8 = 1;
  v9 = (_QWORD *)((char *)this + 328);
  if ( CoCreateInstance(&CLSID_IITDatabaseLocal, 0, 1u, &IID_IITDatabase, (LPVOID *)this + 41) >= 0
    && (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v9)(*v9, &IID_IPersistStorage, (char *)this + 336) >= 0
    && (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 42) + 40LL))(
         *((_QWORD *)this + 42),
         *(_QWORD *)(*((_QWORD *)this + 40) + 8LL)) >= 0 )
  {
    *((_DWORD *)this + 6) = 1;
  }
  v10 = *v9;
  v35 = 0;
  (*(void (__fastcall **)(__int64, GUID *, unsigned int *))(*(_QWORD *)v10 + 40LL))(v10, &CLSID_HHSysSort, &v35);
  Instance = CoCreateInstance(&CLSID_IITWordWheelUpdate, 0, 1u, &IID_IITBuildCollect, (LPVOID *)this);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_IITWordWheelUpdate, 0, 1u, &IID_IITBuildCollect, (LPVOID *)this + 1);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(&CLSID_IITPropList, 0, 1u, &IID_IITPropList, (LPVOID *)this + 2);
      if ( Instance >= 0 )
        *((_DWORD *)this + 6) = 1;
    }
  }
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v83, 0);
  StringCbCatW(v83, 0x208u, *((const unsigned __int16 **)this + 5));
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**(_QWORD **)(*((_QWORD *)this + 40) + 8LL) + 40LL))(
    *(_QWORD *)(*((_QWORD *)this + 40) + 8LL),
    v83,
    18);
  (***(void (__fastcall ****)(_QWORD, GUID *, char *))this)(*(_QWORD *)this, &IID_IPersistStorage, (char *)this + 360);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 45) + 40LL))(
    *((_QWORD *)this + 45),
    *((_QWORD *)this + 43));
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(
    *((_QWORD *)this + 1),
    v84,
    0);
  StringCbCatW(v84, 0x208u, *((const unsigned __int16 **)this + 6));
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *, __int64, _QWORD, _DWORD, char *))(**(_QWORD **)(*((_QWORD *)this + 40) + 8LL)
                                                                                      + 40LL))(
    *(_QWORD *)(*((_QWORD *)this + 40) + 8LL),
    v84,
    18,
    0,
    0,
    (char *)this + 352);
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 1))(
    *((_QWORD *)this + 1),
    &IID_IPersistStorage,
    (char *)this + 368);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 46) + 40LL))(
    *((_QWORD *)this + 46),
    *((_QWORD *)this + 44));
  strcpy(LCData, "1252");
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  SystemDefaultLCID = *((_DWORD *)this + 14);
  if ( SystemDefaultLCID == -1 )
  {
    SystemDefaultLCID = GetSystemDefaultLCID();
    *((_DWORD *)this + 14) = SystemDefaultLCID;
  }
  GetLocaleInfoA(SystemDefaultLCID, 0x1004u, LCData, 20);
  v13 = Atoi(LCData);
  memset_0((char *)&v67.m256i_u64[2] + 4, 0, 0x90u);
  v67.m256i_i32[0] = 2;
  *(_OWORD *)((char *)v67.m256i_i64 + 4) = 0x272Fu;
  memset_0(&v56, 0, 0xA4u);
  v14 = *(_QWORD *)this;
  v15 = *(_OWORD *)v67.m256i_i8;
  v16 = *(_OWORD *)&v67.m256i_u64[2];
  v17 = v68;
  v18 = v69;
  v19 = v70;
  v20 = v71;
  v21 = v72;
  v22 = v73;
  v23 = v74;
  v24 = v75;
  v25 = v65;
  v26 = v76;
  v27 = *v9;
  v28 = *(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, __m256i *, __m256i *))(**(_QWORD **)this + 32LL);
  v36 = v56;
  v29 = *((_DWORD *)this + 14);
  v37 = v57;
  v38 = v58;
  v45 = v65;
  v39 = v59;
  v55 = v76;
  v40 = v60;
  v41 = v61;
  v42 = v62;
  v43 = v63;
  v44 = v64;
  v46 = v67;
  v47 = v68;
  v48 = v69;
  v49 = v70;
  v50 = v71;
  v51 = v72;
  v52 = v73;
  v53 = v74;
  v54 = v75;
  v28(v14, v35, v27, v13, v29, &v46, &v36);
  v46 = v56;
  v30 = (__int64 *)*((_QWORD *)this + 1);
  v31 = *v9;
  v47 = v57;
  v32 = *v30;
  v48 = v58;
  v33 = *((_DWORD *)this + 14);
  v34 = *(void (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int, __m256i *, __m256i *))(v32 + 32);
  v49 = v59;
  v50 = v60;
  v55 = v25;
  v51 = v61;
  v45 = v26;
  v52 = v62;
  v53 = v63;
  v54 = v64;
  *(_OWORD *)v36.m256i_i8 = v15;
  *(_OWORD *)&v36.m256i_u64[2] = v16;
  v37 = v17;
  v38 = v18;
  v39 = v19;
  v40 = v20;
  v41 = v21;
  v42 = v22;
  v43 = v23;
  v44 = v24;
  v34(v30, v35, v31, v13, v33, &v36, &v46);
  if ( Instance < 0 )
  {
    CWordWheelCompiler::Free(this);
    v8 = 0;
  }
  *((_DWORD *)this + 6) = v8;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180074e14  mov     rax, rsp
0x180074e17  push    rbp
0x180074e18  push    rbx
0x180074e19  push    rsi
0x180074e1a  push    rdi
0x180074e1b  push    r12
0x180074e1d  push    r13
0x180074e1f  push    r14
0x180074e21  push    r15
0x180074e23  lea     rbp, [rax-868h]
0x180074e2a  sub     rsp, 928h
0x180074e31  movaps  xmmword ptr [rax-58h], xmm6
0x180074e35  movaps  xmmword ptr [rax-68h], xmm7
0x180074e39  movaps  xmmword ptr [rax-78h], xmm8
0x180074e3e  movaps  xmmword ptr [rax-88h], xmm9
0x180074e46  movaps  xmmword ptr [rax-98h], xmm10
0x180074e4e  movaps  xmmword ptr [rax-0A8h], xmm11
0x180074e56  movaps  xmmword ptr [rax-0B8h], xmm12
0x180074e5e  movaps  xmmword ptr [rax-0C8h], xmm13
0x180074e66  movaps  xmmword ptr [rax-0D8h], xmm14
0x180074e6e  movaps  xmmword ptr [rax-0E8h], xmm15
0x180074e76  mov     rax, cs:__security_cookie
0x180074e7d  xor     rax, rsp
0x180074e80  mov     [rbp+860h+var_F0], rax
0x180074e87  xor     esi, esi
0x180074e89  mov     r14, rcx
0x180074e8c  cmp     [rcx+18h], esi
0x180074e8f  jz      short loc_180074E98
0x180074e91  xor     eax, eax
0x180074e93  jmp     loc_1800754C0
0x180074e98  mov     rax, [rcx+28h]
0x180074e9c  test    rax, rax
0x180074e9f  jz      loc_1800754BB
0x180074ea5  cmp     [rax], si
0x180074ea8  jz      loc_1800754BB
0x180074eae  mov     rax, [rcx+30h]
0x180074eb2  test    rax, rax
0x180074eb5  jz      loc_1800754BB
0x180074ebb  cmp     [rax], si
0x180074ebe  jz      loc_1800754BB
0x180074ec4  mov     edi, 104h
0x180074ec9  lea     rdx, [rbp+860h+PathName]
0x180074ed0  mov     ecx, edi
0x180074ed2  call    cs:__imp_GetTempPath2A
0x180074ed8  mov     r8, [r14+20h]; char *
0x180074edc  test    r8, r8
0x180074edf  jz      short loc_180074EF6
0x180074ee1  cmp     [r8], sil
0x180074ee4  jz      short loc_180074EF6
0x180074ee6  lea     rbx, [r14+3Ch]
0x180074eea  mov     edx, edi; unsigned __int64
0x180074eec  mov     rcx, rbx; char *
0x180074eef  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180074ef4  jmp     short loc_180074F14
0x180074ef6  lea     rbx, [r14+3Ch]
0x180074efa  xor     r8d, r8d; uUnique
0x180074efd  mov     r9, rbx; lpTempFileName
0x180074f00  lea     rdx, aTfs; "TFS"
0x180074f07  lea     rcx, [rbp+860h+PathName]; lpPathName
0x180074f0e  call    cs:__imp_GetTempFileNameA
0x180074f14  mov     rcx, rbx; char *
0x180074f17  call    ?IsFile@@YAHPEBD@Z; IsFile(char const *)
0x180074f1c  test    eax, eax
0x180074f1e  jz      short loc_180074F29
0x180074f20  mov     rcx, rbx; lpFileName
0x180074f23  call    cs:__imp_DeleteFileA
0x180074f29  mov     ecx, 118h; Size
0x180074f2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074f33  mov     [rbp+860h+var_700], rax
0x180074f3a  test    rax, rax
0x180074f3d  jz      short loc_180074F4C
0x180074f3f  mov     [rax], rsi
0x180074f42  mov     [rax+8], rsi
0x180074f46  mov     [rax+10h], sil
0x180074f4a  jmp     short loc_180074F4F
0x180074f4c  mov     rax, rsi
0x180074f4f  mov     [r14+140h], rax
0x180074f56  test    rax, rax
0x180074f59  jz      loc_1800754BB
0x180074f5f  mov     rcx, rax; this
0x180074f62  call    ?Init@CFileSystem@@QEAAJXZ; CFileSystem::Init(void)
0x180074f67  test    eax, eax
0x180074f69  js      loc_1800754BB
0x180074f6f  mov     rcx, [r14+140h]; this
0x180074f76  mov     rdx, rbx; char *
0x180074f79  call    ?CreateUncompressed@CFileSystem@@QEAAJPEBD@Z; CFileSystem::CreateUncompressed(char const *)
0x180074f7e  test    eax, eax
0x180074f80  js      loc_1800754BB
0x180074f86  mov     r15d, 1
0x180074f8c  lea     r13, [r14+148h]
0x180074f93  mov     r8d, r15d; dwClsContext
0x180074f96  mov     [rsp+960h+ppv], r13; ppv
0x180074f9b  lea     r9, IID_IITDatabase; riid
0x180074fa2  xor     edx, edx; pUnkOuter
0x180074fa4  lea     rcx, CLSID_IITDatabaseLocal; rclsid
0x180074fab  call    cs:__imp_CoCreateInstance
0x180074fb1  test    eax, eax
0x180074fb3  js      short loc_180074FFB
0x180074fb5  mov     rcx, [r13+0]
0x180074fb9  lea     rbx, [r14+150h]
0x180074fc0  mov     r8, rbx
0x180074fc3  lea     rdx, IID_IPersistStorage
0x180074fca  mov     rax, [rcx]
0x180074fcd  mov     rax, [rax]
0x180074fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fd5  test    eax, eax
0x180074fd7  js      short loc_180074FFB
0x180074fd9  mov     rcx, [rbx]
0x180074fdc  mov     rdx, [r14+140h]
0x180074fe3  mov     rax, [rcx]
0x180074fe6  mov     rdx, [rdx+8]
0x180074fea  mov     rax, [rax+28h]
0x180074fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ff3  test    eax, eax
0x180074ff5  js      short loc_180074FFB
0x180074ff7  mov     [r14+18h], r15d
0x180074ffb  mov     rcx, [r13+0]
0x180074fff  lea     r8, [rsp+960h+var_920]
0x180075004  mov     [rsp+960h+var_920], esi
0x180075008  lea     rdx, CLSID_HHSysSort
0x18007500f  mov     rax, [rcx]
0x180075012  mov     rax, [rax+28h]
0x180075016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007501b  lea     r9, IID_IITBuildCollect; riid
0x180075022  mov     [rsp+960h+ppv], r14; ppv
0x180075027  mov     r8d, r15d; dwClsContext
0x18007502a  lea     rcx, CLSID_IITWordWheelUpdate; rclsid
0x180075031  xor     edx, edx; pUnkOuter
0x180075033  call    cs:__imp_CoCreateInstance
0x180075039  mov     r12d, eax
0x18007503c  test    eax, eax
0x18007503e  js      short loc_180075096
0x180075040  lea     rax, [r14+8]
0x180075044  mov     r8d, r15d; dwClsContext
0x180075047  lea     r9, IID_IITBuildCollect; riid
0x18007504e  mov     [rsp+960h+ppv], rax; ppv
0x180075053  xor     edx, edx; pUnkOuter
0x180075055  lea     rcx, CLSID_IITWordWheelUpdate; rclsid
0x18007505c  call    cs:__imp_CoCreateInstance
0x180075062  mov     r12d, eax
0x180075065  test    eax, eax
0x180075067  js      short loc_180075096
0x180075069  lea     rax, [r14+10h]
0x18007506d  mov     r8d, r15d; dwClsContext
0x180075070  lea     r9, IID_IITPropList; riid
0x180075077  mov     [rsp+960h+ppv], rax; ppv
0x18007507c  xor     edx, edx; pUnkOuter
0x18007507e  lea     rcx, CLSID_IITPropList; rclsid
0x180075085  call    cs:__imp_CoCreateInstance
0x18007508b  mov     r12d, eax
0x18007508e  test    eax, eax
0x180075090  js      short loc_180075096
0x180075092  mov     [r14+18h], r15d
0x180075096  mov     rcx, [r14]
0x180075099  lea     rdx, [rbp+860h+var_510]
0x1800750a0  xor     r8d, r8d
0x1800750a3  mov     rax, [rcx]
0x1800750a6  mov     rax, [rax+38h]
0x1800750aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750af  mov     r8, [r14+28h]; unsigned __int16 *
0x1800750b3  lea     rcx, [rbp+860h+var_510]; unsigned __int16 *
0x1800750ba  mov     edx, 208h; unsigned __int64
0x1800750bf  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800750c4  mov     rax, [r14+140h]
0x1800750cb  lea     rdi, [r14+158h]
0x1800750d2  xor     r9d, r9d
0x1800750d5  mov     [rsp+960h+var_938], rdi
0x1800750da  mov     dword ptr [rsp+960h+ppv], esi
0x1800750de  lea     rdx, [rbp+860h+var_510]
0x1800750e5  mov     rcx, [rax+8]
0x1800750e9  lea     esi, [r9+12h]
0x1800750ed  mov     r8d, esi
0x1800750f0  mov     rax, [rcx]
0x1800750f3  mov     rax, [rax+28h]
0x1800750f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800750fc  mov     rcx, [r14]
0x1800750ff  lea     rbx, [r14+168h]
0x180075106  mov     r8, rbx
0x180075109  lea     rdx, IID_IPersistStorage
0x180075110  mov     rax, [rcx]
0x180075113  mov     rax, [rax]
0x180075116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007511b  mov     rcx, [rbx]
0x18007511e  mov     rdx, [rdi]
0x180075121  mov     rax, [rcx]
0x180075124  mov     rax, [rax+28h]
0x180075128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007512d  mov     rcx, [r14+8]
0x180075131  lea     rdx, [rbp+860h+var_300]
0x180075138  xor     r8d, r8d
0x18007513b  mov     rax, [rcx]
0x18007513e  mov     rax, [rax+38h]
0x180075142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075147  mov     r8, [r14+30h]; unsigned __int16 *
0x18007514b  lea     rcx, [rbp+860h+var_300]; unsigned __int16 *
0x180075152  mov     edx, 208h; unsigned __int64
0x180075157  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18007515c  mov     rax, [r14+140h]
0x180075163  lea     rdi, [r14+160h]
0x18007516a  mov     [rsp+960h+var_938], rdi
0x18007516f  lea     rdx, [rbp+860h+var_300]
0x180075176  xor     r9d, r9d
0x180075179  mov     dword ptr [rsp+960h+ppv], 0
0x180075181  mov     r8d, esi
0x180075184  mov     rcx, [rax+8]
0x180075188  mov     rax, [rcx]
0x18007518b  mov     rax, [rax+28h]
0x18007518f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075194  mov     rcx, [r14+8]
0x180075198  lea     rbx, [r14+170h]
0x18007519f  mov     r8, rbx
0x1800751a2  lea     rdx, IID_IPersistStorage
0x1800751a9  mov     rax, [rcx]
0x1800751ac  mov     rax, [rax]
0x1800751af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751b4  mov     rcx, [rbx]
0x1800751b7  mov     rdx, [rdi]
0x1800751ba  mov     rax, [rcx]
0x1800751bd  mov     rax, [rax+28h]
0x1800751c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751c6  mov     eax, dword ptr cs:a1252; "1252"
0x1800751cc  mov     dword ptr [rbp+860h+LCData], eax
0x1800751d2  mov     al, byte ptr cs:a1252+4; ""
0x1800751d8  mov     [rbp+860h+var_63C], al
0x1800751de  xor     eax, eax
0x1800751e0  mov     [rbp+860h+var_63B], rax
0x1800751e7  mov     [rbp+860h+var_633], eax
0x1800751ed  mov     [rbp+860h+var_62F], ax
0x1800751f4  mov     [rbp+860h+var_62D], al
0x1800751fa  mov     eax, [r14+38h]
0x1800751fe  cmp     eax, 0FFFFFFFFh
0x180075201  jnz     short loc_18007520D
0x180075203  call    cs:__imp_GetSystemDefaultLCID
0x180075209  mov     [r14+38h], eax
0x18007520d  mov     r9d, 14h; cchData
0x180075213  lea     r8, [rbp+860h+LCData]; lpLCData
0x18007521a  mov     edx, 1004h; LCType
0x18007521f  mov     ecx, eax; Locale
0x180075221  call    cs:__imp_GetLocaleInfoA
0x180075227  lea     rcx, [rbp+860h+LCData]; char *
0x18007522e  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180075233  xor     edx, edx; Val
0x180075235  lea     rcx, [rbp+860h+var_6DC]; void *
0x18007523c  mov     r8d, 90h; Size
0x180075242  mov     esi, eax
0x180075244  call    memset_0
0x180075249  xor     edx, edx; Val
0x18007524b  mov     dword ptr [rbp+860h+var_6F0], 2
0x180075255  mov     r8d, 0A4h; Size
0x18007525b  mov     qword ptr [rbp+860h+var_6F0+4], 272Fh
0x180075266  lea     rcx, [rbp+860h+var_7B0]; void *
0x18007526d  mov     qword ptr [rbp+860h+var_6F0+0Ch], 0
0x180075278  call    memset_0
0x18007527d  movaps  xmm0, [rbp+860h+var_7B0]
0x180075284  lea     rdx, [rsp+960h+var_918+8]
0x180075289  mov     rcx, [r14]
0x18007528c  mov     r9d, esi
0x18007528f  movaps  xmm15, xmmword ptr [rbp+860h+var_6F0]
0x180075297  movaps  xmm14, xmmword ptr [rbp+180h]
0x18007529f  movaps  xmm13, [rbp+860h+var_6D0]
0x1800752a7  mov     rax, [rcx]
0x1800752aa  movaps  xmm12, [rbp+860h+var_6C0]
0x1800752b2  movaps  xmm11, [rbp+860h+var_6B0]
0x1800752ba  movaps  xmm10, [rbp+860h+var_6A0]
0x1800752c2  movaps  xmm9, [rbp+860h+var_690]
0x1800752ca  movaps  xmm8, [rbp+860h+var_680]
0x1800752d2  movaps  xmm7, [rbp+860h+var_670]
0x1800752d9  movaps  xmm6, [rbp+860h+var_660]
0x1800752e0  mov     edi, [rbp+860h+var_710]
0x1800752e6  mov     ebx, [rbp+860h+var_650]
0x1800752ec  mov     r8, [r13+0]
0x1800752f0  mov     rax, [rax+20h]
0x1800752f4  movups  [rsp+960h+var_918+8], xmm0
0x1800752f9  mov     [rsp+960h+var_930], rdx
0x1800752fe  lea     rdx, [rbp+860h+var_860]
0x180075302  movaps  xmm0, [rbp+860h+var_7A0]
0x180075309  movups  [rsp+960h+var_908+8], xmm0
0x18007530e  mov     [rsp+960h+var_938], rdx
0x180075313  movaps  xmm0, [rbp+860h+var_790]
0x18007531a  mov     edx, [r14+38h]
0x18007531e  movups  xmmword ptr [rsp+960h+var_8F8+8], xmm0
0x180075323  mov     dword ptr [rsp+960h+ppv], edx
0x180075327  movaps  xmm0, [rbp+860h+var_780]
0x18007532e  mov     edx, [rsp+960h+var_920]
0x180075332  movups  [rbp+860h+var_8E0], xmm0
0x180075336  mov     [rbp+860h+var_870], edi
0x180075339  movaps  xmm0, [rbp+860h+var_770]
0x180075340  movups  [rbp+860h+var_8D0], xmm0
0x180075344  mov     [rbp+860h+var_7C0], ebx
0x18007534a  movaps  xmm0, [rbp+860h+var_760]
0x180075351  movups  [rbp+860h+var_8C0], xmm0
0x180075355  movaps  xmm0, [rbp+860h+var_750]
0x18007535c  movups  [rbp+860h+var_8B0], xmm0
0x180075360  movaps  xmm0, [rbp+860h+var_740]
0x180075367  movups  [rbp+860h+var_8A0], xmm0
0x18007536b  movaps  xmm0, [rbp+860h+var_730]
0x180075372  movups  [rbp+860h+var_890], xmm0
0x180075376  movaps  xmm0, [rbp+860h+var_720]
0x18007537d  movups  [rbp+860h+var_880], xmm0
0x180075381  movups  [rbp+860h+var_860], xmm15
  ... truncated ...
```
