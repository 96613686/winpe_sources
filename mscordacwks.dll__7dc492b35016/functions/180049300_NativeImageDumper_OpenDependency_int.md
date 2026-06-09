# NativeImageDumper::OpenDependency(int)

- ea: `0x180049300`
- end: `0x180049c3e`
- name: `?OpenDependency@NativeImageDumper@@AEAAPEAUDependency@1@H@Z`
- size: `2366`
- prototype: `struct NativeImageDumper::Dependency *__fastcall(NativeImageDumper *__hidden this, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043098`
- `0x180048870`

## callees

- `0x18000b30c`
- `0x18000bb64`
- `0x18002101c`
- `0x1800210f0`
- `0x180022068`
- `0x180022230`
- `0x180023ea8`
- `0x180042a8c`
- `0x180042ad8`
- `0x180045fa8`
- `0x180049300`
- `0x1800725e8`
- `0x180072664`
- `0x1800731f8`
- `0x18007344c`
- `0x180073a40`
- `0x180076604`
- `0x1800777d0`
- `0x180078074`
- `0x180078128`
- `0x1800785d4`
- `0x1800f0d20`
- `0x1800f3020`
- `0x1800f9348`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004988d`
- `KERNEL32!HeapFree` at `0x1800498da`
- `KERNEL32!HeapFree` at `0x180049bc9`
- `KERNEL32!HeapFree` at `0x18004988d`
- `KERNEL32!HeapFree` at `0x1800498da`
- `KERNEL32!HeapFree` at `0x180049bc9`
- `KERNEL32!GetProcessHeap` at `0x180049878`
- `KERNEL32!GetProcessHeap` at `0x1800498c5`
- `KERNEL32!GetProcessHeap` at `0x180049bb4`
- `KERNEL32!GetProcessHeap` at `0x180049878`
- `KERNEL32!GetProcessHeap` at `0x1800498c5`
- `KERNEL32!GetProcessHeap` at `0x180049bb4`

## string_xrefs

- `0x180049834`: `WARNING Failed to load softbound dependency:\n	%S,Version=%d.%d.0.0,PublicKeyToken=%S.\n	Attempting to continue.  May crash later in due to missing metadata\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
struct NativeImageDumper::Dependency *__fastcall NativeImageDumper::OpenDependency(NativeImageDumper *this, int a2)
{
  __int64 v2; // r15
  PEDecoder *v4; // r14
  struct CORCOMPILE_VERSION_INFO *NativeVersionInfo; // r12
  __int64 v6; // rcx
  struct CORCOMPILE_HEADER *NativeHeader; // rax
  int v8; // ebx
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  unsigned int *v14; // r15
  struct CORCOMPILE_HEADER *v15; // rax
  void *v16; // rsp
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  Module *v19; // rax
  struct CORCOMPILE_HEADER *v20; // rax
  __int64 RvaData; // rax
  __int64 v22; // r14
  __int64 v23; // rax
  bool v24; // bl
  bool v25; // r13
  int v26; // eax
  int v27; // eax
  LPVOID v28; // rbx
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdi
  void *v32; // rbx
  HANDLE v33; // rax
  wchar_t *v34; // rbx
  HANDLE v35; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  unsigned __int64 v39; // rbx
  int *v40; // rax
  int *v41; // rax
  void *v42; // rax
  __int64 v43; // rdx
  unsigned __int64 TargetAddrForHostAddr; // rax
  unsigned int v45; // edx
  int *v46; // rax
  void *v47; // rax
  __int64 v48; // rdx
  int Dispenser; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  struct CORCOMPILE_HEADER *v53; // rax
  void *v54; // rsp
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // r8
  Module *v57; // rax
  unsigned __int64 *Metadata; // rax
  unsigned __int64 v59; // rcx
  unsigned int v60; // ebx
  void *v61; // rax
  int v62; // eax
  wchar_t *v63; // rbx
  HANDLE ProcessHeap; // rax
  bool v65[1488]; // [rsp+40h] [rbp-630h] BYREF
  bool v66[8]; // [rsp+630h] [rbp-40h]
  unsigned int v67; // [rsp+670h] [rbp+0h] BYREF
  unsigned __int8 *TargetVtForHostVt; // [rsp+678h] [rbp+8h] BYREF
  __int64 v69; // [rsp+680h] [rbp+10h] BYREF
  int v70; // [rsp+688h] [rbp+18h]
  int v71; // [rsp+690h] [rbp+20h]
  _QWORD *v72; // [rsp+698h] [rbp+28h] BYREF
  _DWORD v73[2]; // [rsp+6A0h] [rbp+30h] BYREF
  int v74; // [rsp+6A8h] [rbp+38h]
  void *v75; // [rsp+6B0h] [rbp+40h]
  unsigned __int64 v76[2]; // [rsp+6B8h] [rbp+48h] BYREF
  __int128 v77; // [rsp+6C8h] [rbp+58h]
  __int128 v78; // [rsp+6D8h] [rbp+68h]
  __int64 v79; // [rsp+6E8h] [rbp+78h]
  _BYTE v80[4]; // [rsp+6F0h] [rbp+80h] BYREF
  _BYTE v81[4]; // [rsp+6F4h] [rbp+84h] BYREF
  _BYTE v82[8]; // [rsp+6F8h] [rbp+88h] BYREF
  int v83; // [rsp+700h] [rbp+90h]
  int v84; // [rsp+710h] [rbp+A0h] BYREF
  __int64 v85; // [rsp+714h] [rbp+A4h]
  wchar_t *Source; // [rsp+720h] [rbp+B0h]
  __int16 v87; // [rsp+728h] [rbp+B8h] BYREF
  int v88; // [rsp+7B0h] [rbp+140h] BYREF
  __int64 v89; // [rsp+7B4h] [rbp+144h]
  LPVOID lpMem; // [rsp+7C0h] [rbp+150h]
  __int16 v91; // [rsp+7C8h] [rbp+158h] BYREF

  v2 = a2;
  v71 = 0;
  v4 = (NativeImageDumper *)((char *)this + 64);
  NativeVersionInfo = PEDecoder::GetNativeVersionInfo((NativeImageDumper *)((char *)this + 64));
  v6 = *((_QWORD *)this + 33);
  if ( !v6 )
  {
    NativeHeader = PEDecoder::GetNativeHeader(v4);
    v8 = *((_DWORD *)NativeHeader + 13) >> 6;
    PEDecoder::GetRvaData(v4, *((unsigned int *)NativeHeader + 12), 0);
    v9 = v8 + 1;
    *((_DWORD *)this + 68) = v9;
    TargetVtForHostVt = (unsigned __int8 *)v9;
    v10 = operator new(saturated_mul(v9, 0x150u));
    v72 = v10;
    if ( v10 )
    {
      v11 = v9;
      v12 = v10 + 4;
      do
      {
        *v12 = -1;
        v12 += 42;
        --v11;
      }
      while ( v11 );
    }
    else
    {
      v10 = 0;
    }
    *((_QWORD *)this + 33) = v10;
    memset(v10, 0, 336LL * v9);
    v6 = *((_QWORD *)this + 33);
  }
  v13 = 336 * v2;
  if ( *(_QWORD *)(336 * v2 + v6) )
    return (struct NativeImageDumper::Dependency *)(v13 + v6);
  if ( !(_DWORD)v2 )
  {
    v14 = (unsigned int *)((char *)this + 296);
    *((_DWORD *)this + 74) = 536870913;
    *((_DWORD *)this + 75) = 536870913;
    *((_OWORD *)this + 19) = *((_OWORD *)NativeVersionInfo + 2);
    *((_QWORD *)this + 40) = *((_QWORD *)NativeVersionInfo + 6);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 31) + 80LL))(
      *((_QWORD *)this + 31),
      0,
      0,
      0,
      (char *)this + 328);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 16) = *((_QWORD *)this + 15);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 8) = *((_QWORD *)PEDecoder::GetNativeHeader(v4) + 13);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 24) = *((_QWORD *)this + 16);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 40) = *((_QWORD *)this + 29);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 48) = *((_QWORD *)this + 65);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 56) = *((_QWORD *)this + 64);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 64) = *((unsigned int *)this + 132);
    v15 = PEDecoder::GetNativeHeader(v4);
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 32) = PEDecoder::GetRvaData(v4, *((unsigned int *)v15 + 16), 0);
    *(_BYTE *)(v13 + *((_QWORD *)this + 33) + 73) = 1;
    v16 = alloca(1584);
    v19 = Module::Module((Module *)v65, v17, v18);
    TargetVtForHostVt = (unsigned __int8 *)DacGetTargetVtForHostVt(*(_QWORD *)v19);
    DacWriteAll(*(_QWORD *)(v13 + *((_QWORD *)this + 33) + 32), &TargetVtForHostVt, 8, 0);
LABEL_60:
    *(_QWORD *)(v13 + *((_QWORD *)this + 33)) = v14;
    v6 = *((_QWORD *)this + 33);
    return (struct NativeImageDumper::Dependency *)(v13 + v6);
  }
  v20 = PEDecoder::GetNativeHeader(v4);
  RvaData = PEDecoder::GetRvaData(v4, *((unsigned int *)v20 + 12), 0);
  v14 = (unsigned int *)DacInstantiateTypeByAddressHelper(RvaData + ((__int64)((int)v2 - 1) << 6), 0x40u, 1, 1);
  v85 = 128;
  Source = (wchar_t *)&v87;
  v84 = 2;
  v87 = 0;
  v22 = *((_QWORD *)this + 33);
  NativeImageDumper::AppendTokenName(this, *v14, (struct SString *)&v84, *((struct IMetaDataImport2 **)this + 31), 1);
  v23 = *((_QWORD *)v14 + 4) - INVALID_NGEN_SIGNATURE;
  if ( !v23 )
    v23 = *((_QWORD *)v14 + 5) + 0x5E2E6A8126EB0C63LL;
  v24 = v23 != 0;
  v73[0] = 18;
  v73[1] = 18;
  v75 = (void *)L"mscorlib";
  v74 = 276;
  v25 = (unsigned int)SString::Compare((SString *)&v84, (const struct SString *)v73) == 0;
  *(_BYTE *)(v13 + v22 + 73) = v24;
  SString::ConvertToUnicode((SString *)&v84);
  wcscpy_s((wchar_t *)(v13 + v22 + 74), 0x80u, Source);
  if ( v24 )
  {
    SString::ConvertToUnicode((SString *)&v84);
    v26 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, unsigned int *, _QWORD **))(**((_QWORD **)this + 18) + 24LL))(
            *((_QWORD *)this + 18),
            Source,
            v14 + 8,
            &v72);
    if ( v26 < 0 )
      ThrowHR(v26);
    *(_QWORD *)(v13 + v22 + 16) = v72;
    goto LABEL_35;
  }
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 **, unsigned int *, unsigned __int16 *, int, _BYTE *, unsigned __int64 *, _QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 32) + 32LL))(
          *((_QWORD *)this + 32),
          *v14,
          &TargetVtForHostVt,
          &v67,
          &qword_180164020,
          0x2000,
          v81,
          v76,
          0,
          0,
          v80);
  if ( v27 < 0 )
    ThrowHR(v27);
  SString::ConvertToUnicode((SString *)&v84);
  if ( (*(int (__fastcall **)(_QWORD, wchar_t *, unsigned __int64 *, unsigned __int8 *, unsigned int, _QWORD **))(**((_QWORD **)this + 18) + 32LL))(
         *((_QWORD *)this + 18),
         Source,
         v76,
         TargetVtForHostVt,
         v67,
         &v72) >= 0 )
  {
    *(_QWORD *)(v13 + *((_QWORD *)this + 33) + 16) = v72;
LABEL_35:
    PEDecoder::PEDecoder(v76, v72);
    if ( v24 )
    {
      *(_QWORD *)(v13 + v22 + 8) = *((_QWORD *)PEDecoder::GetNativeHeader((PEDecoder *)v76) + 13);
      v39 = v76[0];
      v40 = (int *)DacInstantiateTypeByAddressHelper(v76[0], 0x40u, 1, 1);
      if ( *((_WORD *)DacInstantiateTypeByAddressHelper(v39 + v40[15], 0x108u, 1, 1) + 12) == 267 )
      {
        v41 = (int *)DacInstantiateTypeByAddressHelper(v39, 0x40u, 1, 1);
        v42 = DacInstantiateTypeByAddressHelper(v39 + v41[15], 0x108u, 1, 1);
        LOBYTE(v43) = 1;
        TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v42, v43);
        v45 = 248;
      }
      else
      {
        v46 = (int *)DacInstantiateTypeByAddressHelper(v39, 0x40u, 1, 1);
        v47 = DacInstantiateTypeByAddressHelper(v39 + v46[15], 0x108u, 1, 1);
        LOBYTE(v48) = 1;
        TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v47, v48);
        v45 = 264;
      }
      v38 = *((unsigned int *)DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, v45, 1, 1) + 20);
      *(_QWORD *)(v13 + v22 + 24) = v38;
    }
    v70 = 0;
    TargetVtForHostVt = (unsigned __int8 *)&v69;
    v69 = 0;
    v71 = 1;
    Dispenser = MetaDataGetDispenser(v38, v37, &v69);
    if ( Dispenser < 0 )
      ThrowHR(Dispenser);
    v71 = 0;
    v50 = v70;
    if ( v69 )
      v50 = 1;
    v70 = v50;
    v51 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v69 + 56LL))(
            v69,
            &MetaDataCheckDuplicatesFor,
            v82);
    if ( v51 < 0 )
      ThrowHR(v51);
    v83 |= 0x18000u;
    v52 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v69 + 48LL))(
            v69,
            &MetaDataCheckDuplicatesFor,
            v82);
    if ( v52 < 0 )
      ThrowHR(v52);
    if ( (unsigned int)PEDecoder::HasNativeHeader((PEDecoder *)v76) )
    {
      v53 = PEDecoder::GetNativeHeader((PEDecoder *)v76);
      *(_QWORD *)(v13 + v22 + 32) = PEDecoder::GetRvaData(v76, *((unsigned int *)v53 + 16), 0);
      v54 = alloca(1584);
      v57 = Module::Module((Module *)v65, v55, v56);
      TargetVtForHostVt = (unsigned __int8 *)DacGetTargetVtForHostVt(*(_QWORD *)v57);
      DacWriteAll(*(_QWORD *)(v13 + *((_QWORD *)this + 33) + 32), &TargetVtForHostVt, 8, 0);
    }
    else
    {
      *(_QWORD *)(v13 + v22 + 32) = 0;
    }
    Metadata = (unsigned __int64 *)PEDecoder::GetMetadata(v76, &TargetVtForHostVt, &v67);
    v59 = *Metadata;
    *(_QWORD *)(v13 + v22 + 48) = *Metadata;
    v60 = v67;
    *(_QWORD *)(v13 + v22 + 64) = v67;
    v61 = DacInstantiateTypeByAddressHelper(v59, v60, 1, 1);
    *(_QWORD *)(v13 + v22 + 56) = v61;
    v62 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD, GUID *, __int64))(*(_QWORD *)v69 + 40LL))(
            v69,
            v61,
            v60,
            0,
            &IID_IMetaDataImport2,
            v13 + v22 + 40);
    if ( v62 < 0 )
      ThrowHR(v62);
    *(_BYTE *)(v13 + v22 + 72) = v25;
    if ( v70 )
    {
      if ( v69 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      v70 = 0;
    }
    if ( (v74 & 8) != 0 )
      operator delete(v75);
    if ( (v85 & 0x800000000LL) != 0 )
    {
      v63 = Source;
      if ( Source )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v63);
      }
    }
    goto LABEL_60;
  }
  v89 = 128;
  lpMem = &v91;
  v88 = 2;
  v91 = 0;
  if ( v67 )
    appendByteArray((struct SString *)&v88, TargetVtForHostVt, v67);
  else
    SString::Set((SString *)&v88, L"<No Hash>");
  SString::ConvertToUnicode((SString *)&v88);
  v28 = lpMem;
  SString::ConvertToUnicode((SString *)&v84);
  v29 = (__int64 *)*((_QWORD *)this + 17);
  v30 = *v29;
  *(_DWORD *)v66 = WORD1(v76[0]);
  (*(void (**)(__int64 *, const char *, ...))(v30 + 24))(
    v29,
    "WARNING Failed to load softbound dependency:\n"
    "\t%S,Version=%d.%d.0.0,PublicKeyToken=%S.\n"
    "\tAttempting to continue.  May crash later in due to missing metadata\n",
    Source,
    LOWORD(v76[0]),
    *(_QWORD *)v66,
    v28);
  *(_QWORD *)(v13 + *((_QWORD *)this + 33)) = v14;
  v31 = *((_QWORD *)this + 33) + v13;
  if ( (v89 & 0x800000000LL) != 0 )
  {
    v32 = lpMem;
    if ( lpMem )
    {
      v33 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v33 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v33;
      }
      HeapFree(v33, 0, v32);
    }
  }
  if ( (v74 & 8) != 0 )
    operator delete(v75);
  if ( (v85 & 0x800000000LL) != 0 )
  {
    v34 = Source;
    if ( Source )
    {
      v35 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v35 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v35;
      }
      HeapFree(v35, 0, v34);
    }
  }
  return (struct NativeImageDumper::Dependency *)v31;
}

```

## disassembly

```asm
0x180049300  push    rbp
0x180049302  push    rsi
0x180049303  push    rdi
0x180049304  push    r12
0x180049306  push    r13
0x180049308  push    r14
0x18004930a  push    r15
0x18004930c  sub     rsp, 250h
0x180049313  lea     rbp, [rsp+60h]
0x180049318  mov     [rbp+220h+arg_10], rbx
0x18004931f  mov     rax, cs:__security_cookie
0x180049326  xor     rax, rbp
0x180049329  mov     [rbp+220h+var_40], rax
0x180049330  movsxd  r15, edx
0x180049333  mov     rsi, rcx
0x180049336  xor     r13d, r13d
0x180049339  mov     [rbp+220h+var_200], r13d
0x18004933d  lea     r14, [rcx+40h]
0x180049341  mov     rcx, r14; this
0x180049344  call    ?GetNativeVersionInfo@PEDecoder@@QEBAPEAUCORCOMPILE_VERSION_INFO@@XZ; PEDecoder::GetNativeVersionInfo(void)
0x180049349  mov     r12, rax
0x18004934c  mov     rcx, [rsi+108h]
0x180049353  lea     ebx, [r13+1]
0x180049357  test    rcx, rcx
0x18004935a  jnz     loc_1800493E9
0x180049360  mov     rcx, r14; this
0x180049363  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x180049368  mov     ebx, [rax+34h]
0x18004936b  shr     ebx, 6
0x18004936e  xor     r8d, r8d
0x180049371  mov     edx, [rax+30h]
0x180049374  mov     rcx, r14
0x180049377  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18004937c  inc     ebx
0x18004937e  mov     edi, ebx
0x180049380  mov     [rsi+110h], ebx
0x180049386  mov     [rbp+220h+var_218], rdi
0x18004938a  mov     eax, 150h
0x18004938f  mul     rdi
0x180049392  lea     rcx, [r13-1]
0x180049396  cmovo   rax, rcx
0x18004939a  mov     rcx, rax; dwBytes
0x18004939d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800493a2  mov     [rbp+220h+var_1F8], rax
0x1800493a6  lea     ebx, [r13+1]
0x1800493aa  test    rax, rax
0x1800493ad  jz      short loc_1800493C7
0x1800493af  mov     ecx, edi
0x1800493b1  lea     rdx, [rax+20h]
0x1800493b5  or      qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1800493b9  lea     rdx, [rdx+150h]
0x1800493c0  sub     rcx, rbx
0x1800493c3  jnz     short loc_1800493B5
0x1800493c5  jmp     short loc_1800493CA
0x1800493c7  mov     rax, r13
0x1800493ca  mov     [rsi+108h], rax
0x1800493d1  imul    r8, rdi, 150h; Size
0x1800493d8  xor     edx, edx; Val
0x1800493da  mov     rcx, rax; void *
0x1800493dd  call    memset
0x1800493e2  mov     rcx, [rsi+108h]
0x1800493e9  imul    rdi, r15, 150h
0x1800493f0  cmp     [rdi+rcx], r13
0x1800493f4  jnz     loc_180049BE1
0x1800493fa  test    r15d, r15d
0x1800493fd  jnz     loc_180049553
0x180049403  lea     r15, [rsi+128h]
0x18004940a  mov     eax, 20000001h
0x18004940f  mov     [r15], eax
0x180049412  mov     [rsi+12Ch], eax
0x180049418  movups  xmm0, xmmword ptr [r12+20h]
0x18004941e  movups  xmmword ptr [rsi+130h], xmm0
0x180049425  movsd   xmm1, qword ptr [r12+30h]
0x18004942c  movsd   qword ptr [rsi+140h], xmm1
0x180049434  mov     rcx, [rsi+0F8h]
0x18004943b  mov     rax, [rcx]
0x18004943e  lea     rdx, [rsi+148h]
0x180049445  mov     qword ptr [rsp+280h+var_260], rdx
0x18004944a  xor     r9d, r9d
0x18004944d  xor     r8d, r8d
0x180049450  xor     edx, edx
0x180049452  mov     rax, [rax+50h]
0x180049456  call    cs:__guard_dispatch_icall_fptr
0x18004945c  mov     rcx, [rsi+108h]
0x180049463  mov     rax, [rsi+78h]
0x180049467  mov     [rdi+rcx+10h], rax
0x18004946c  mov     rcx, r14; this
0x18004946f  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x180049474  mov     rcx, [rax+68h]
0x180049478  mov     rax, [rsi+108h]
0x18004947f  mov     [rdi+rax+8], rcx
0x180049484  mov     rcx, [rsi+108h]
0x18004948b  mov     rax, [rsi+80h]
0x180049492  mov     [rdi+rcx+18h], rax
0x180049497  mov     rcx, [rsi+108h]
0x18004949e  mov     rax, [rsi+0E8h]
0x1800494a5  mov     [rdi+rcx+28h], rax
0x1800494aa  mov     rcx, [rsi+108h]
0x1800494b1  mov     rax, [rsi+208h]
0x1800494b8  mov     [rdi+rcx+30h], rax
0x1800494bd  mov     rcx, [rsi+108h]
0x1800494c4  mov     rax, [rsi+200h]
0x1800494cb  mov     [rdi+rcx+38h], rax
0x1800494d0  mov     ecx, [rsi+210h]
0x1800494d6  mov     rax, [rsi+108h]
0x1800494dd  mov     [rdi+rax+40h], rcx
0x1800494e2  mov     rcx, r14; this
0x1800494e5  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x1800494ea  xor     r8d, r8d
0x1800494ed  mov     edx, [rax+40h]
0x1800494f0  mov     rcx, r14
0x1800494f3  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x1800494f8  mov     rcx, [rsi+108h]
0x1800494ff  mov     [rdi+rcx+20h], rax
0x180049504  mov     rax, [rsi+108h]
0x18004950b  mov     [rdi+rax+49h], bl
0x18004950f  mov     eax, [rsp+280h+var_280]
0x180049512  mov     eax, 630h
0x180049517  sub     rsp, rax
0x18004951a  lea     rcx, [rsp+8B0h+var_850]; this
0x18004951f  mov     eax, [rcx]
0x180049521  call    ??0Module@@QEAA@_K0@Z; Module::Module(unsigned __int64,unsigned __int64)
0x180049526  mov     rcx, [rax]
0x180049529  call    DacGetTargetVtForHostVt
0x18004952e  mov     [rbp+220h+var_218], rax
0x180049532  mov     rcx, [rsi+108h]
0x180049539  xor     r9d, r9d
0x18004953c  lea     r8d, [r9+8]
0x180049540  lea     rdx, [rbp+220h+var_218]
0x180049544  mov     rcx, [rdi+rcx+20h]
0x180049549  call    DacWriteAll
0x18004954e  jmp     loc_180049BCF
0x180049553  mov     rcx, r14; this
0x180049556  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x18004955b  xor     r8d, r8d
0x18004955e  mov     edx, [rax+30h]
0x180049561  mov     rcx, r14
0x180049564  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x180049569  lea     ecx, [r15-1]
0x18004956d  movsxd  rcx, ecx
0x180049570  shl     rcx, 6
0x180049574  add     rcx, rax; unsigned __int64
0x180049577  mov     r9b, bl; bool
0x18004957a  mov     r8b, bl; bool
0x18004957d  mov     edx, 40h ; '@'; unsigned int
0x180049582  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180049587  mov     r15, rax
0x18004958a  mov     [rbp+220h+var_180], r13
0x180049591  mov     [rbp+220h+var_180+4], 80h
0x18004959c  mov     [rbp+220h+Source], r13
0x1800495a3  lea     rax, [rbp+220h+var_168]
0x1800495aa  mov     [rbp+220h+Source], rax
0x1800495b1  mov     dword ptr [rbp+220h+var_180], 2
0x1800495bb  mov     rcx, [rbp+220h+Source]
0x1800495c2  mov     [rcx], r13w
0x1800495c6  mov     r14, [rsi+108h]
0x1800495cd  mov     [rsp+280h+var_260], bl; bool
0x1800495d1  mov     r9, [rsi+0F8h]; struct IMetaDataImport2 *
0x1800495d8  lea     r8, [rbp+220h+var_180]; struct SString *
0x1800495df  mov     edx, [r15]; unsigned int
0x1800495e2  mov     rcx, rsi; this
0x1800495e5  call    ?AppendTokenName@NativeImageDumper@@QEAAXIAEAVSString@@PEAUIMetaDataImport2@@_N@Z; NativeImageDumper::AppendTokenName(uint,SString &,IMetaDataImport2 *,bool)
0x1800495ea  mov     rax, [r15+20h]
0x1800495ee  sub     rax, cs:INVALID_NGEN_SIGNATURE
0x1800495f5  jnz     short loc_180049602
0x1800495f7  mov     rax, [r15+28h]
0x1800495fb  sub     rax, cs:qword_180135128
0x180049602  test    rax, rax
0x180049605  setnz   bl
0x180049608  mov     eax, 12h
0x18004960d  mov     [rbp+220h+var_1F0], eax
0x180049610  mov     [rbp+220h+var_1EC], eax
0x180049613  mov     [rbp+220h+var_1E8], 10h
0x18004961a  lea     rax, aMscorlib_0; "mscorlib"
0x180049621  mov     [rbp+220h+var_1E0], rax
0x180049625  mov     ecx, [rbp+220h+var_1E8]
0x180049628  and     ecx, 0FFFFFFF8h
0x18004962b  mov     [rbp+220h+var_1E8], ecx
0x18004962e  mov     eax, ecx
0x180049630  or      eax, 4
0x180049633  mov     [rbp+220h+var_1E8], eax
0x180049636  or      ecx, 104h
0x18004963c  mov     [rbp+220h+var_1E8], ecx
0x18004963f  lea     rdx, [rbp+220h+var_1F0]; struct SString *
0x180049643  lea     rcx, [rbp+220h+var_180]; this
0x18004964a  call    ?Compare@SString@@QEBAHAEBV1@@Z; SString::Compare(SString const &)
0x18004964f  test    eax, eax
0x180049651  setz    r13b
0x180049655  mov     [rdi+r14+49h], bl
0x18004965a  lea     rcx, [rbp+220h+var_180]; this
0x180049661  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180049666  lea     rcx, [r14+4Ah]
0x18004966a  add     rcx, rdi; Destination
0x18004966d  mov     r8, [rbp+220h+Source]; Source
0x180049674  mov     edx, 80h; SizeInWords
0x180049679  call    wcscpy_s
0x18004967e  test    bl, bl
0x180049680  jz      short loc_1800496CA
0x180049682  lea     rcx, [rbp+220h+var_180]; this
0x180049689  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18004968e  mov     rcx, [rsi+90h]
0x180049695  mov     rax, [rcx]
0x180049698  lea     r9, [rbp+220h+var_1F8]
0x18004969c  lea     r8, [r15+20h]
0x1800496a0  mov     rdx, [rbp+220h+Source]
0x1800496a7  mov     rax, [rax+18h]
0x1800496ab  call    cs:__guard_dispatch_icall_fptr
0x1800496b1  xor     r12d, r12d
0x1800496b4  test    eax, eax
0x1800496b6  js      loc_180049C16
0x1800496bc  mov     rax, [rbp+220h+var_1F8]
0x1800496c0  mov     [rdi+r14+10h], rax
0x1800496c5  jmp     loc_1800498F8
0x1800496ca  xorps   xmm0, xmm0
0x1800496cd  xor     eax, eax
0x1800496cf  movups  xmmword ptr [rbp+220h+var_1D8], xmm0
0x1800496d3  movups  [rbp+220h+var_1C8], xmm0
0x1800496d7  movups  [rbp+220h+var_1B8], xmm0
0x1800496db  mov     [rbp+220h+var_1A8], rax
0x1800496df  mov     rcx, [rsi+100h]
0x1800496e6  mov     rax, [rcx]
0x1800496e9  lea     rdx, [rbp+220h+var_1A0]
0x1800496f0  mov     [rsp+280h+var_230], rdx
0x1800496f5  xor     r12d, r12d
0x1800496f8  mov     [rsp+280h+var_238], r12
0x1800496fd  mov     [rsp+280h+var_240], r12
0x180049702  lea     rdx, [rbp+220h+var_1D8]
0x180049706  mov     [rsp+280h+var_248], rdx
0x18004970b  lea     rdx, [rbp+220h+var_19C]
0x180049712  mov     [rsp+280h+var_250], rdx
0x180049717  mov     dword ptr [rsp+280h+var_258], 2000h
0x18004971f  lea     rdx, qword_180164020
0x180049726  mov     qword ptr [rsp+280h+var_260], rdx
0x18004972b  lea     r9, [rbp+220h+var_220]
0x18004972f  lea     r8, [rbp+220h+var_218]
0x180049733  mov     edx, [r15]
0x180049736  mov     rax, [rax+20h]
0x18004973a  call    cs:__guard_dispatch_icall_fptr
0x180049740  test    eax, eax
0x180049742  js      loc_180049C1E
0x180049748  lea     rcx, [rbp+220h+var_180]; this
0x18004974f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180049754  mov     rcx, [rsi+90h]
0x18004975b  mov     rax, [rcx]
0x18004975e  lea     rdx, [rbp+220h+var_1F8]
0x180049762  mov     [rsp+280h+var_258], rdx
0x180049767  mov     edx, [rbp+220h+var_220]
0x18004976a  mov     dword ptr [rsp+280h+var_260], edx
0x18004976e  mov     r9, [rbp+220h+var_218]
0x180049772  lea     r8, [rbp+220h+var_1D8]
0x180049776  mov     rdx, [rbp+220h+Source]
0x18004977d  mov     rax, [rax+20h]
0x180049781  call    cs:__guard_dispatch_icall_fptr
0x180049787  test    eax, eax
0x180049789  jns     loc_1800498E8
0x18004978f  mov     [rbp+220h+var_E0], r12
0x180049796  mov     [rbp+220h+var_E0+4], 80h
0x1800497a1  mov     [rbp+220h+lpMem], r12
0x1800497a8  lea     rax, [rbp+220h+var_C8]
0x1800497af  mov     [rbp+220h+lpMem], rax
0x1800497b6  mov     dword ptr [rbp+220h+var_E0], 2
0x1800497c0  mov     rax, [rbp+220h+lpMem]
0x1800497c7  mov     [rax], r12w
0x1800497cb  mov     r8d, [rbp+220h+var_220]; unsigned int
0x1800497cf  lea     rcx, [rbp+220h+var_E0]; this
0x1800497d6  test    r8d, r8d
0x1800497d9  jz      short loc_1800497E6
0x1800497db  mov     rdx, [rbp+220h+var_218]; unsigned __int8 *
0x1800497df  call    ?appendByteArray@@YAXAEAVSString@@PEBEK@Z; appendByteArray(SString &,uchar const *,ulong)
0x1800497e4  jmp     short loc_1800497F2
0x1800497e6  lea     rdx, aNoHash; "<No Hash>"
0x1800497ed  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1800497f2  lea     rcx, [rbp+220h+var_E0]; this
0x1800497f9  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800497fe  mov     rbx, [rbp+220h+lpMem]
0x180049805  lea     rcx, [rbp+220h+var_180]; this
0x18004980c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180049811  mov     rcx, [rsi+88h]
0x180049818  mov     rax, [rcx]
0x18004981b  movzx   edx, word ptr [rbp+220h+var_1D8+2]
0x18004981f  movzx   r9d, word ptr [rbp+220h+var_1D8]
0x180049824  mov     [rsp+280h+var_258], rbx
0x180049829  mov     dword ptr [rsp+280h+var_260], edx
0x18004982d  mov     r8, [rbp+220h+Source]
0x180049834  lea     rdx, aWarningFailedT; "WARNING Failed to load softbound depend"...
0x18004983b  mov     rax, [rax+18h]
0x18004983f  call    cs:__guard_dispatch_icall_fptr
0x180049845  mov     rax, [rsi+108h]
0x18004984c  mov     [rdi+rax], r15
0x180049850  add     rdi, [rsi+108h]
0x180049857  test    [rbp+220h+var_D8], 8
0x18004985e  jz      short loc_180049894
0x180049860  mov     rbx, [rbp+220h+lpMem]
0x180049867  test    rbx, rbx
0x18004986a  jz      short loc_180049894
0x18004986c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180049873  test    rax, rax
0x180049876  jnz     short loc_180049885
0x180049878  call    cs:__imp_GetProcessHeap
0x18004987e  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
  ... truncated ...
```
