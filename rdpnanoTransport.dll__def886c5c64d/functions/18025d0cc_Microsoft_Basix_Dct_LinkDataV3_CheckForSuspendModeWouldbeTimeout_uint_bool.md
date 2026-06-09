# Microsoft::Basix::Dct::LinkDataV3::CheckForSuspendModeWouldbeTimeout(uint,bool)

- ea: `0x18025d0cc`
- end: `0x18025dece`
- name: `?CheckForSuspendModeWouldbeTimeout@LinkDataV3@Dct@Basix@Microsoft@@QEAA_NI_N@Z`
- size: `3586`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::LinkDataV3 *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18025e08c`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001dad8`
- `0x18001db78`
- `0x180024760`
- `0x18003c308`
- `0x1801171b8`
- `0x18025d0cc`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18025d574`: `LinkId`
- `0x18025dbdd`: `LinkId`
- `0x18025d2b7`: `firstWouldbeDropedLink`
- `0x18025d913`: `firstWouldbeDropedLink`
- `0x18025d60f`: `Link(In direction) would be timeout 17 seconds after suspension`
- `0x18025d61b`: `LinkWouldbeDropped`
- `0x18025dc8b`: `LinkWouldbeDropped`
- `0x18025dc7f`: `Link(Out direction) would be timeout 17 seconds after suspension`

## pseudocode

```c
// Hidden C++ exception states: #wind=107
char __fastcall Microsoft::Basix::Dct::LinkDataV3::CheckForSuspendModeWouldbeTimeout(
        Microsoft::Basix::Dct::LinkDataV3 *this,
        unsigned int a2,
        char a3)
{
  __int64 v4; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  __int128 v10; // rcx
  unsigned int v11; // r15d
  unsigned int v12; // r12d
  bool v13; // zf
  char v14; // si
  unsigned int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  volatile signed __int32 *v32; // r14
  unsigned int v33; // r14d
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  volatile signed __int32 *v50; // r14
  char v52; // [rsp+50h] [rbp-B0h]
  __int64 *v53; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v54; // [rsp+60h] [rbp-A0h]
  __int128 v55; // [rsp+70h] [rbp-90h] BYREF
  __int128 v56; // [rsp+80h] [rbp-80h]
  __int128 v57; // [rsp+90h] [rbp-70h] BYREF
  __int128 v58; // [rsp+A0h] [rbp-60h]
  __int128 v59; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-40h]
  __int128 v61; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v62; // [rsp+E0h] [rbp-20h]
  __int128 v63; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v64; // [rsp+100h] [rbp+0h]
  __int128 v65; // [rsp+110h] [rbp+10h] BYREF
  __int128 v66; // [rsp+120h] [rbp+20h]
  __int128 v67; // [rsp+130h] [rbp+30h] BYREF
  __int128 v68; // [rsp+140h] [rbp+40h]
  __int128 v69; // [rsp+150h] [rbp+50h] BYREF
  __int128 v70; // [rsp+160h] [rbp+60h]
  __int128 v71; // [rsp+170h] [rbp+70h] BYREF
  __int128 v72; // [rsp+180h] [rbp+80h]
  __int128 v73; // [rsp+190h] [rbp+90h] BYREF
  __int128 v74; // [rsp+1A0h] [rbp+A0h]
  __int128 v75; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v76; // [rsp+1C0h] [rbp+C0h]
  __int128 v77; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v78; // [rsp+1E0h] [rbp+E0h]
  __int64 *v79; // [rsp+1F0h] [rbp+F0h]
  __int64 *v80; // [rsp+1F8h] [rbp+F8h]
  __int64 *v81; // [rsp+200h] [rbp+100h]
  __int64 v82[4]; // [rsp+208h] [rbp+108h] BYREF
  __int64 v83[4]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v84[4]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v85[4]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v86[4]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v87[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v88[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v89[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v90[32]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v91[32]; // [rsp+328h] [rbp+228h] BYREF
  _BYTE v92[32]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v93[32]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v94[32]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v95[4]; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int64 v96[4]; // [rsp+3C8h] [rbp+2C8h] BYREF
  __int64 v97[4]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v98[32]; // [rsp+408h] [rbp+308h] BYREF
  _BYTE v99[32]; // [rsp+428h] [rbp+328h] BYREF
  _BYTE v100[32]; // [rsp+448h] [rbp+348h] BYREF
  _BYTE v101[32]; // [rsp+468h] [rbp+368h] BYREF
  int v102[4]; // [rsp+488h] [rbp+388h] BYREF

  v4 = a2;
  v6 = *(_QWORD *)std::chrono::steady_clock::now(&v53) / 1000000LL;
  v54 = 0;
  v7 = *((_QWORD *)this + 22);
  if ( v7 )
  {
    v8 = *(_DWORD *)(v7 + 8);
    while ( v8 )
    {
      v9 = v8;
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      if ( v9 == v8 )
      {
        *(_QWORD *)&v10 = *((_QWORD *)this + 21);
        *(_QWORD *)&v54 = v10;
        *((_QWORD *)&v10 + 1) = *((_QWORD *)this + 22);
        *((_QWORD *)&v54 + 1) = *((_QWORD *)&v10 + 1);
        goto LABEL_6;
      }
    }
  }
  v10 = v54;
LABEL_6:
  v11 = 0;
  v12 = 0;
  if ( (_QWORD)v10 )
  {
    v11 = *(_DWORD *)(v10 + 1488);
    v12 = *(_DWORD *)(v10 + 1492);
  }
  v13 = a3 == 0;
  v14 = 1;
  if ( !v13 )
  {
    if ( *((_DWORD *)this + 70) == 1 && v6 > *((_QWORD *)this + 33) + v4 && !*((_BYTE *)this + 256) )
    {
      v15 = 0;
      if ( *(_QWORD *)(v10 + 3168) == 0x7FFFFFFFFFFFFFFFLL )
      {
        *(_QWORD *)(v10 + 3168) = v6;
        v15 = 1;
      }
      *(_OWORD *)v102 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v102);
      if ( *(_QWORD *)v102 && *(_BYTE *)(*(_QWORD *)v102 + 128LL) )
      {
        v53 = v83;
        std::_Integral_to_string<char,int>(v82, v15);
        v55 = 0;
        v56 = 0;
        std::string::_Construct<1,char const *>(&v55, ":", 1);
        v77 = 0;
        v78 = 0;
        std::string::_Construct<1,char const *>(&v77, "\"", 1);
        v75 = 0;
        v76 = 0;
        std::string::_Construct<1,char const *>(&v75, "\"", 1);
        v16 = std::operator+<char>(v101, &v75, "firstWouldbeDropedLink");
        LOBYTE(v17) = v52;
        std::string::string(v97, v17, v16, &v77);
        LOBYTE(v18) = v52;
        std::string::string(v96, v18, v97, &v55);
        LOBYTE(v19) = v52;
        std::string::string(v83, v19, v96, v82);
        v79 = v84;
        std::_Integral_to_string<char,unsigned int>(v95, v12);
        v73 = 0;
        v74 = 0;
        std::string::_Construct<1,char const *>(&v73, ":", 1);
        v71 = 0;
        v72 = 0;
        std::string::_Construct<1,char const *>(&v71, "\"", 1);
        v69 = 0;
        v70 = 0;
        std::string::_Construct<1,char const *>(&v69, "\"", 1);
        v20 = std::operator+<char>(v100, &v69, "nonIceDoR");
        LOBYTE(v21) = v52;
        std::string::string(v94, v21, v20, &v71);
        LOBYTE(v22) = v52;
        std::string::string(v93, v22, v94, &v73);
        LOBYTE(v23) = v52;
        std::string::string(v84, v23, v93, v95);
        v80 = v85;
        std::_Integral_to_string<char,unsigned int>(v92, v11);
        v67 = 0;
        v68 = 0;
        std::string::_Construct<1,char const *>(&v67, ":", 1);
        v65 = 0;
        v66 = 0;
        std::string::_Construct<1,char const *>(&v65, "\"", 1);
        v63 = 0;
        v64 = 0;
        std::string::_Construct<1,char const *>(&v63, "\"", 1);
        v24 = std::operator+<char>(v99, &v63, "IceDoR");
        LOBYTE(v25) = v52;
        std::string::string(v91, v25, v24, &v65);
        LOBYTE(v26) = v52;
        std::string::string(v90, v26, v91, &v67);
        LOBYTE(v27) = v52;
        std::string::string(v85, v27, v90, v92);
        std::_Integral_to_string<char,unsigned int>(v89, *((unsigned int *)this + 38));
        v61 = 0;
        v62 = 0;
        std::string::_Construct<1,char const *>(&v61, ":", 1);
        v59 = 0;
        v60 = 0;
        std::string::_Construct<1,char const *>(&v59, "\"", 1);
        v57 = 0;
        v58 = 0;
        std::string::_Construct<1,char const *>(&v57, "\"", 1);
        v28 = std::operator+<char>(v98, &v57, "LinkId");
        LOBYTE(v29) = v52;
        std::string::string(v88, v29, v28, &v59);
        LOBYTE(v30) = v52;
        std::string::string(v87, v30, v88, &v61);
        LOBYTE(v31) = v52;
        std::string::string(v86, v31, v87, v89);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
          (int)v102,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkWouldbeDropped",
          "Link(In direction) would be timeout 17 seconds after suspension",
          (__int64)v86,
          (__int64)v85,
          (__int64)v84,
          (__int64)v83);
        std::string::_Tidy_deallocate(v87);
        std::string::_Tidy_deallocate(v88);
        std::string::_Tidy_deallocate(v98);
        std::string::_Tidy_deallocate(&v57);
        std::string::_Tidy_deallocate(&v59);
        std::string::_Tidy_deallocate(&v61);
        std::string::_Tidy_deallocate(v89);
        std::string::_Tidy_deallocate(v90);
        std::string::_Tidy_deallocate(v91);
        std::string::_Tidy_deallocate(v99);
        std::string::_Tidy_deallocate(&v63);
        std::string::_Tidy_deallocate(&v65);
        std::string::_Tidy_deallocate(&v67);
        std::string::_Tidy_deallocate(v92);
        std::string::_Tidy_deallocate(v93);
        std::string::_Tidy_deallocate(v94);
        std::string::_Tidy_deallocate(v100);
        std::string::_Tidy_deallocate(&v69);
        std::string::_Tidy_deallocate(&v71);
        std::string::_Tidy_deallocate(&v73);
        std::string::_Tidy_deallocate(v95);
        std::string::_Tidy_deallocate(v96);
        std::string::_Tidy_deallocate(v97);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(&v75);
        std::string::_Tidy_deallocate(&v77);
        std::string::_Tidy_deallocate(&v55);
        std::string::_Tidy_deallocate(v82);
      }
      v32 = *(volatile signed __int32 **)&v102[2];
      if ( *(_QWORD *)&v102[2] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v102[2] + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( !_InterlockedDecrement(v32 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
      *((_BYTE *)this + 256) = 1;
      goto LABEL_37;
    }
LABEL_36:
    v14 = 0;
    goto LABEL_37;
  }
  if ( *((_DWORD *)this + 71) != 1 || v6 <= *((_QWORD *)this + 34) + v4 || *((_BYTE *)this + 257) )
    goto LABEL_36;
  v33 = 0;
  if ( *(_QWORD *)(v10 + 3168) == 0x7FFFFFFFFFFFFFFFLL )
  {
    *(_QWORD *)(v10 + 3168) = v6;
    v33 = 1;
  }
  *(_OWORD *)v102 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v102);
  if ( *(_QWORD *)v102 && *(_BYTE *)(*(_QWORD *)v102 + 128LL) )
  {
    v81 = v82;
    std::_Integral_to_string<char,int>(v83, v33);
    v57 = 0;
    v58 = 0;
    std::string::_Construct<1,char const *>(&v57, ":", 1);
    v59 = 0;
    v60 = 0;
    std::string::_Construct<1,char const *>(&v59, "\"", 1);
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&v61, "\"", 1);
    v34 = std::operator+<char>(v98, &v61, "firstWouldbeDropedLink");
    LOBYTE(v35) = v52;
    std::string::string(v84, v35, v34, &v59);
    LOBYTE(v36) = v52;
    std::string::string(v85, v36, v84, &v57);
    LOBYTE(v37) = v52;
    std::string::string(v82, v37, v85, v83);
    v80 = v97;
    std::_Integral_to_string<char,unsigned int>(v86, v12);
    v63 = 0;
    v64 = 0;
    std::string::_Construct<1,char const *>(&v63, ":", 1);
    v65 = 0;
    v66 = 0;
    std::string::_Construct<1,char const *>(&v65, "\"", 1);
    v67 = 0;
    v68 = 0;
    std::string::_Construct<1,char const *>(&v67, "\"", 1);
    v38 = std::operator+<char>(v99, &v67, "nonIceDoR");
    LOBYTE(v39) = v52;
    std::string::string(v87, v39, v38, &v65);
    LOBYTE(v40) = v52;
    std::string::string(v88, v40, v87, &v63);
    LOBYTE(v41) = v52;
    std::string::string(v97, v41, v88, v86);
    v79 = v96;
    std::_Integral_to_string<char,unsigned int>(v89, v11);
    v69 = 0;
    v70 = 0;
    std::string::_Construct<1,char const *>(&v69, ":", 1);
    v71 = 0;
    v72 = 0;
    std::string::_Construct<1,char const *>(&v71, "\"", 1);
    v73 = 0;
    v74 = 0;
    std::string::_Construct<1,char const *>(&v73, "\"", 1);
    v42 = std::operator+<char>(v100, &v73, "IceDoR");
    LOBYTE(v43) = v52;
    std::string::string(v90, v43, v42, &v71);
    LOBYTE(v44) = v52;
    std::string::string(v91, v44, v90, &v69);
    LOBYTE(v45) = v52;
    std::string::string(v96, v45, v91, v89);
    std::_Integral_to_string<char,unsigned int>(v92, *((unsigned int *)this + 38));
    v75 = 0;
    v76 = 0;
    std::string::_Construct<1,char const *>(&v75, ":", 1);
    v77 = 0;
    v78 = 0;
    std::string::_Construct<1,char const *>(&v77, "\"", 1);
    v55 = 0;
    v56 = 0;
    std::string::_Construct<1,char const *>(&v55, "\"", 1);
    v46 = std::operator+<char>(v101, &v55, "LinkId");
    LOBYTE(v47) = v52;
    std::string::string(v93, v47, v46, &v77);
    LOBYTE(v48) = v52;
    std::string::string(v94, v48, v93, &v75);
    LOBYTE(v49) = v52;
    std::string::string(v95, v49, v94, v92);
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
      (int)v102,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Smiles",
      "LinkWouldbeDropped",
      "Link(Out direction) would be timeout 17 seconds after suspension",
      (__int64)v95,
      (__int64)v96,
      (__int64)v97,
      (__int64)v82);
    std::string::_Tidy_deallocate(v94);
    std::string::_Tidy_deallocate(v93);
    std::string::_Tidy_deallocate(v101);
    std::string::_Tidy_deallocate(&v55);
    std::string::_Tidy_deallocate(&v77);
    std::string::_Tidy_deallocate(&v75);
    std::string::_Tidy_deallocate(v92);
    std::string::_Tidy_deallocate(v91);
    std::string::_Tidy_deallocate(v90);
    std::string::_Tidy_deallocate(v100);
    std::string::_Tidy_deallocate(&v73);
    std::string::_Tidy_deallocate(&v71);
    std::string::_Tidy_deallocate(&v69);
    std::string::_Tidy_deallocate(v89);
    std::string::_Tidy_deallocate(v88);
    std::string::_Tidy_deallocate(v87);
    std::string::_Tidy_deallocate(v99);
    std::string::_Tidy_deallocate(&v67);
    std::string::_Tidy_deallocate(&v65);
    std::string::_Tidy_deallocate(&v63);
    std::string::_Tidy_deallocate(v86);
    std::string::_Tidy_deallocate(v85);
    std::string::_Tidy_deallocate(v84);
    std::string::_Tidy_deallocate(v98);
    std::string::_Tidy_deallocate(&v61);
    std::string::_Tidy_deallocate(&v59);
    std::string::_Tidy_deallocate(&v57);
    std::string::_Tidy_deallocate(v83);
  }
  v50 = *(volatile signed __int32 **)&v102[2];
  if ( *(_QWORD *)&v102[2] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v102[2] + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
      if ( !_InterlockedDecrement(v50 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
    }
  }
  *((_BYTE *)this + 257) = 1;
LABEL_37:
  if ( *((_QWORD *)&v10 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL)) )
    {
      (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18025d0cc  mov     rax, rsp
0x18025d0cf  mov     [rax+10h], rbx
0x18025d0d3  mov     [rax+18h], rsi
0x18025d0d7  mov     [rax+20h], rdi
0x18025d0db  push    rbp
0x18025d0dc  push    r12
0x18025d0de  push    r13
0x18025d0e0  push    r14
0x18025d0e2  push    r15
0x18025d0e4  lea     rbp, [rax-3C8h]
0x18025d0eb  mov     eax, 4A0h
0x18025d0f0  call    _alloca_probe
0x18025d0f5  sub     rsp, rax
0x18025d0f8  mov     rax, cs:__security_cookie
0x18025d0ff  xor     rax, rsp
0x18025d102  mov     [rbp+3C0h+var_28], rax
0x18025d109  mov     sil, r8b
0x18025d10c  mov     r14d, edx
0x18025d10f  mov     rdi, rcx
0x18025d112  lea     rcx, [rsp+4C0h+var_468]
0x18025d117  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18025d11c  mov     rcx, [rax]
0x18025d11f  mov     rax, 431BDE82D7B634DBh
0x18025d129  imul    rcx
0x18025d12c  sar     rdx, 12h
0x18025d130  mov     rax, rdx
0x18025d133  shr     rax, 3Fh
0x18025d137  add     rdx, rax
0x18025d13a  xorps   xmm1, xmm1
0x18025d13d  movdqu  [rsp+4C0h+var_468+8], xmm1
0x18025d143  mov     r8, [rdi+0B0h]
0x18025d14a  test    r8, r8
0x18025d14d  jz      short loc_18025D168
0x18025d14f  mov     eax, [r8+8]
0x18025d153  jmp     short loc_18025D164
0x18025d155  lea     ecx, [rax+1]
0x18025d158  lock cmpxchg [r8+8], ecx
0x18025d15e  jz      loc_18025D7ED
0x18025d164  test    eax, eax
0x18025d166  jnz     short loc_18025D155
0x18025d168  mov     rcx, qword ptr [rsp+4C0h+var_468+8]
0x18025d16d  mov     rbx, qword ptr [rsp+4C0h+var_458]
0x18025d172  xor     r15d, r15d
0x18025d175  xor     r12d, r12d
0x18025d178  test    rcx, rcx
0x18025d17b  jz      short loc_18025D18B
0x18025d17d  mov     r15d, [rcx+5D0h]
0x18025d184  mov     r12d, [rcx+5D4h]
0x18025d18b  or      r13d, 0FFFFFFFFh
0x18025d18f  test    sil, sil
0x18025d192  lea     esi, [r13+2]
0x18025d196  jz      loc_18025D80A
0x18025d19c  cmp     [rdi+118h], esi
0x18025d1a2  jnz     loc_18025DE5A
0x18025d1a8  mov     rax, r14
0x18025d1ab  add     rax, [rdi+108h]
0x18025d1b2  cmp     rdx, rax
0x18025d1b5  jle     loc_18025DE5A
0x18025d1bb  cmp     byte ptr [rdi+100h], 0
0x18025d1c2  jnz     loc_18025DE5A
0x18025d1c8  xor     r14d, r14d
0x18025d1cb  mov     rax, 7FFFFFFFFFFFFFFFh
0x18025d1d5  cmp     [rcx+0C60h], rax
0x18025d1dc  jnz     short loc_18025D1E8
0x18025d1de  mov     [rcx+0C60h], rdx
0x18025d1e5  mov     r14d, esi
0x18025d1e8  xorps   xmm0, xmm0
0x18025d1eb  movups  xmmword ptr [rbp+3C0h+var_38], xmm0
0x18025d1f2  lea     rcx, [rbp+3C0h+var_38]
0x18025d1f9  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18025d1fe  nop
0x18025d1ff  mov     rax, qword ptr [rbp+3C0h+var_38]
0x18025d206  test    rax, rax
0x18025d209  jz      loc_18025D79A
0x18025d20f  cmp     byte ptr [rax+80h], 0
0x18025d216  jz      loc_18025D79A
0x18025d21c  lea     rax, [rbp+3C0h+var_298]
0x18025d223  mov     qword ptr [rsp+4C0h+var_468], rax
0x18025d228  mov     edx, r14d
0x18025d22b  lea     rcx, [rbp+3C0h+var_2B8]
0x18025d232  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x18025d237  nop
0x18025d238  xorps   xmm0, xmm0
0x18025d23b  movups  xmmword ptr [rsp+4C0h+var_458+8], xmm0
0x18025d240  xorps   xmm1, xmm1
0x18025d243  movdqu  [rbp+3C0h+var_440], xmm1
0x18025d248  mov     r8, rsi
0x18025d24b  lea     r13, asc_1803D71C4; ":"
0x18025d252  mov     rdx, r13
0x18025d255  lea     rcx, [rsp+4C0h+var_458+8]
0x18025d25a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d25f  nop
0x18025d260  xorps   xmm0, xmm0
0x18025d263  movups  [rbp+3C0h+var_2F0], xmm0
0x18025d26a  xorps   xmm1, xmm1
0x18025d26d  movdqu  [rbp+3C0h+var_2E0], xmm1
0x18025d275  mov     r8, rsi
0x18025d278  lea     r14, asc_1803D71C8; "\""
0x18025d27f  mov     rdx, r14
0x18025d282  lea     rcx, [rbp+3C0h+var_2F0]
0x18025d289  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d28e  nop
0x18025d28f  xorps   xmm0, xmm0
0x18025d292  movups  [rbp+3C0h+var_310], xmm0
0x18025d299  xorps   xmm1, xmm1
0x18025d29c  movdqu  [rbp+3C0h+var_300], xmm1
0x18025d2a4  mov     r8, rsi
0x18025d2a7  mov     rdx, r14
0x18025d2aa  lea     rcx, [rbp+3C0h+var_310]
0x18025d2b1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d2b6  nop
0x18025d2b7  lea     r8, aFirstwouldbedr; "firstWouldbeDropedLink"
0x18025d2be  lea     rdx, [rbp+3C0h+var_310]
0x18025d2c5  lea     rcx, [rbp+3C0h+var_58]
0x18025d2cc  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025d2d1  nop
0x18025d2d2  lea     r9, [rbp+3C0h+var_2F0]
0x18025d2d9  mov     r8, rax
0x18025d2dc  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d2e0  lea     rcx, [rbp+3C0h+var_D8]
0x18025d2e7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d2ec  nop
0x18025d2ed  lea     r9, [rsp+4C0h+var_458+8]
0x18025d2f2  lea     r8, [rbp+3C0h+var_D8]
0x18025d2f9  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d2fd  lea     rcx, [rbp+3C0h+var_F8]
0x18025d304  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d309  nop
0x18025d30a  lea     r9, [rbp+3C0h+var_2B8]
0x18025d311  lea     r8, [rbp+3C0h+var_F8]
0x18025d318  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d31c  lea     rcx, [rbp+3C0h+var_298]
0x18025d323  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d328  nop
0x18025d329  lea     rax, [rbp+3C0h+var_278]
0x18025d330  mov     [rbp+3C0h+var_2D0], rax
0x18025d337  mov     edx, r12d
0x18025d33a  lea     rcx, [rbp+3C0h+var_118]
0x18025d341  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18025d346  nop
0x18025d347  xorps   xmm0, xmm0
0x18025d34a  movups  [rbp+3C0h+var_330], xmm0
0x18025d351  xorps   xmm1, xmm1
0x18025d354  movdqu  [rbp+3C0h+var_320], xmm1
0x18025d35c  mov     r8, rsi
0x18025d35f  mov     rdx, r13
0x18025d362  lea     rcx, [rbp+3C0h+var_330]
0x18025d369  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d36e  nop
0x18025d36f  xorps   xmm0, xmm0
0x18025d372  movups  [rbp+3C0h+var_350], xmm0
0x18025d376  xorps   xmm1, xmm1
0x18025d379  movdqu  [rbp+3C0h+var_340], xmm1
0x18025d381  mov     r8, rsi
0x18025d384  mov     rdx, r14
0x18025d387  lea     rcx, [rbp+3C0h+var_350]
0x18025d38b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d390  nop
0x18025d391  xorps   xmm0, xmm0
0x18025d394  movups  [rbp+3C0h+var_370], xmm0
0x18025d398  xorps   xmm1, xmm1
0x18025d39b  movdqu  [rbp+3C0h+var_360], xmm1
0x18025d3a0  mov     r8, rsi
0x18025d3a3  mov     rdx, r14
0x18025d3a6  lea     rcx, [rbp+3C0h+var_370]
0x18025d3aa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d3af  nop
0x18025d3b0  lea     r8, aNonicedor_0; "nonIceDoR"
0x18025d3b7  lea     rdx, [rbp+3C0h+var_370]
0x18025d3bb  lea     rcx, [rbp+3C0h+var_78]
0x18025d3c2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025d3c7  nop
0x18025d3c8  lea     r9, [rbp+3C0h+var_350]
0x18025d3cc  mov     r8, rax
0x18025d3cf  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d3d3  lea     rcx, [rbp+3C0h+var_138]
0x18025d3da  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d3df  nop
0x18025d3e0  lea     r9, [rbp+3C0h+var_330]
0x18025d3e7  lea     r8, [rbp+3C0h+var_138]
0x18025d3ee  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d3f2  lea     rcx, [rbp+3C0h+var_158]
0x18025d3f9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d3fe  nop
0x18025d3ff  lea     r9, [rbp+3C0h+var_118]
0x18025d406  lea     r8, [rbp+3C0h+var_158]
0x18025d40d  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d411  lea     rcx, [rbp+3C0h+var_278]
0x18025d418  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d41d  nop
0x18025d41e  lea     rax, [rbp+3C0h+var_258]
0x18025d425  mov     [rbp+3C0h+var_2C8], rax
0x18025d42c  mov     edx, r15d
0x18025d42f  lea     rcx, [rbp+3C0h+var_178]
0x18025d436  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18025d43b  nop
0x18025d43c  xorps   xmm0, xmm0
0x18025d43f  movups  [rbp+3C0h+var_390], xmm0
0x18025d443  xorps   xmm1, xmm1
0x18025d446  movdqu  [rbp+3C0h+var_380], xmm1
0x18025d44b  mov     r8, rsi
0x18025d44e  mov     rdx, r13
0x18025d451  lea     rcx, [rbp+3C0h+var_390]
0x18025d455  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d45a  nop
0x18025d45b  xorps   xmm0, xmm0
0x18025d45e  movups  [rbp+3C0h+var_3B0], xmm0
0x18025d462  xorps   xmm1, xmm1
0x18025d465  movdqu  [rbp+3C0h+var_3A0], xmm1
0x18025d46a  mov     r8, rsi
0x18025d46d  mov     rdx, r14
0x18025d470  lea     rcx, [rbp+3C0h+var_3B0]
0x18025d474  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d479  nop
0x18025d47a  xorps   xmm0, xmm0
0x18025d47d  movups  [rbp+3C0h+var_3D0], xmm0
0x18025d481  xorps   xmm1, xmm1
0x18025d484  movdqu  [rbp+3C0h+var_3C0], xmm1
0x18025d489  mov     r8, rsi
0x18025d48c  mov     rdx, r14
0x18025d48f  lea     rcx, [rbp+3C0h+var_3D0]
0x18025d493  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d498  nop
0x18025d499  lea     r8, aIcedor; "IceDoR"
0x18025d4a0  lea     rdx, [rbp+3C0h+var_3D0]
0x18025d4a4  lea     rcx, [rbp+3C0h+var_98]
0x18025d4ab  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025d4b0  nop
0x18025d4b1  lea     r9, [rbp+3C0h+var_3B0]
0x18025d4b5  mov     r8, rax
0x18025d4b8  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d4bc  lea     rcx, [rbp+3C0h+var_198]
0x18025d4c3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d4c8  nop
0x18025d4c9  lea     r9, [rbp+3C0h+var_390]
0x18025d4cd  lea     r8, [rbp+3C0h+var_198]
0x18025d4d4  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d4d8  lea     rcx, [rbp+3C0h+var_1B8]
0x18025d4df  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d4e4  nop
0x18025d4e5  lea     r9, [rbp+3C0h+var_178]
0x18025d4ec  lea     r8, [rbp+3C0h+var_1B8]
0x18025d4f3  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d4f7  lea     rcx, [rbp+3C0h+var_258]
0x18025d4fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d503  nop
0x18025d504  mov     edx, [rdi+98h]
0x18025d50a  lea     rcx, [rbp+3C0h+var_1D8]
0x18025d511  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18025d516  nop
0x18025d517  xorps   xmm0, xmm0
0x18025d51a  movups  [rbp+3C0h+var_3F0], xmm0
0x18025d51e  xorps   xmm1, xmm1
0x18025d521  movdqu  [rbp+3C0h+var_3E0], xmm1
0x18025d526  mov     r8, rsi
0x18025d529  mov     rdx, r13
0x18025d52c  lea     rcx, [rbp+3C0h+var_3F0]
0x18025d530  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d535  nop
0x18025d536  xorps   xmm0, xmm0
0x18025d539  movups  [rbp+3C0h+var_410], xmm0
0x18025d53d  xorps   xmm1, xmm1
0x18025d540  movdqu  [rbp+3C0h+var_400], xmm1
0x18025d545  mov     r8, rsi
0x18025d548  mov     rdx, r14
0x18025d54b  lea     rcx, [rbp+3C0h+var_410]
0x18025d54f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d554  nop
0x18025d555  xorps   xmm0, xmm0
0x18025d558  movups  [rbp+3C0h+var_430], xmm0
0x18025d55c  xorps   xmm1, xmm1
0x18025d55f  movdqu  [rbp+3C0h+var_420], xmm1
0x18025d564  mov     r8, rsi
0x18025d567  mov     rdx, r14
0x18025d56a  lea     rcx, [rbp+3C0h+var_430]
0x18025d56e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025d573  nop
0x18025d574  lea     r8, aLinkid; "LinkId"
0x18025d57b  lea     rdx, [rbp+3C0h+var_430]
0x18025d57f  lea     rcx, [rbp+3C0h+var_B8]
0x18025d586  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025d58b  nop
0x18025d58c  lea     r9, [rbp+3C0h+var_410]
0x18025d590  mov     r8, rax
0x18025d593  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d597  lea     rcx, [rbp+3C0h+var_1F8]
0x18025d59e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d5a3  nop
0x18025d5a4  lea     r9, [rbp+3C0h+var_3F0]
0x18025d5a8  lea     r8, [rbp+3C0h+var_1F8]
0x18025d5af  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d5b3  lea     rcx, [rbp+3C0h+var_218]
0x18025d5ba  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d5bf  nop
0x18025d5c0  lea     r9, [rbp+3C0h+var_1D8]
0x18025d5c7  lea     r8, [rbp+3C0h+var_218]
0x18025d5ce  mov     dl, byte ptr [rsp+4C0h+var_470]
0x18025d5d2  lea     rcx, [rbp+3C0h+var_238]
0x18025d5d9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025d5de  nop
  ... truncated ...
```
