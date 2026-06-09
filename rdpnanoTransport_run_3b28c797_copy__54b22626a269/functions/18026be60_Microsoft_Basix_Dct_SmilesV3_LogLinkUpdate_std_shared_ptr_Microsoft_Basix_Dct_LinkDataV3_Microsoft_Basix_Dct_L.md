# Microsoft::Basix::Dct::SmilesV3::LogLinkUpdate(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,Microsoft::Basix::Dct::LinkData::Direction)

- ea: `0x18026be60`
- end: `0x18026c8c5`
- name: `?LogLinkUpdate@SmilesV3@Dct@Basix@Microsoft@@AEAAXV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@W4Direction@LinkData@234@@Z`
- size: `2661`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18026da30`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x18001dad8`
- `0x18001db78`
- `0x180024700`
- `0x180024760`
- `0x1801171b8`
- `0x1801cd974`
- `0x1801cda84`
- `0x180250e48`
- `0x18026be60`
- `0x18027f408`
- `0x18027f490`
- `0x18027f5c0`
- `0x18027f628`
- `0x1802e9b68`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18026c3b3`: `LinkId`
- `0x18026c271`: `LinkType`
- `0x18026c886`: `LogLinkUpdate has null link `
- `0x18026bfe3`: `Checkpoint.SMILES.LinkUpdate(%s):Id=%d, linkType=%s, delay=%f`
- `0x18026c5d6`: `LinkUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall Microsoft::Basix::Dct::SmilesV3::LogLinkUpdate(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v4; // rbx
  double v5; // xmm0_8
  double v6; // xmm6_8
  int v7; // r9d
  _QWORD *v8; // rsi
  int v9; // ebx
  _QWORD *v10; // rdi
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  _QWORD *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  _QWORD *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  volatile signed __int32 *v34; // rbx
  __int64 result; // rax
  volatile signed __int32 *v36; // rbx
  char *v37; // [rsp+20h] [rbp-E0h]
  char *Str; // [rsp+28h] [rbp-D8h]
  _OWORD v39[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v40[2]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v41[2]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v42[2]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v43[2]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v44[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v45[2]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v46[32]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v47[2]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v48[32]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v49[2]; // [rsp+198h] [rbp+98h] BYREF
  _OWORD v50[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _OWORD v51[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _OWORD v52[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD v53[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v54[2]; // [rsp+238h] [rbp+138h] BYREF
  _OWORD v55[2]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD *v56; // [rsp+278h] [rbp+178h]
  __int64 *v57; // [rsp+280h] [rbp+180h]
  __int64 *v58; // [rsp+288h] [rbp+188h]
  __int64 v59[4]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v60[4]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v61[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v62[4]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v63[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v64[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v65[32]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v66[32]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v67[32]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v68[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v69[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v70[32]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v71[32]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v72[32]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v73[32]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v74[32]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v75[32]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v76[32]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v77[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v78[32]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v80[8]; // [rsp+590h] [rbp+490h] BYREF
  _OWORD v81[2]; // [rsp+598h] [rbp+498h] BYREF
  int v82[4]; // [rsp+5B8h] [rbp+4B8h] BYREF
  __int128 v83; // [rsp+5C8h] [rbp+4C8h]
  _QWORD v84[3]; // [rsp+5D8h] [rbp+4D8h] BYREF
  unsigned __int64 v85; // [rsp+5F0h] [rbp+4F0h]
  _QWORD v86[3]; // [rsp+5F8h] [rbp+4F8h] BYREF
  unsigned __int64 v87; // [rsp+610h] [rbp+510h]

  v56 = a2;
  v80[0] = a3;
  if ( (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          a2,
                          0) )
  {
    std::string::string(v48, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\smilesv3.cpp");
    std::string::string(v46, "LogLinkUpdate has null link ");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v46, v48, 633);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::LinkData::Direction>(v84, v80, 0, 6);
  v4 = *a2;
  if ( v80[0] != 1 )
  {
    if ( (int)Microsoft::Basix::Algorithm::SlidingStats<double,5,0,0>::num(*(_QWORD *)(v4 + 200)) <= 0 )
      v5 = DOUBLE_1000_0;
    else
      v5 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(*(_QWORD *)(v4 + 200));
    goto LABEL_9;
  }
  if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v4 + 192)) )
  {
    v5 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::navg(*(_QWORD *)(v4 + 192));
LABEL_9:
    v6 = v5;
    goto LABEL_10;
  }
  v6 = DOUBLE_1000_0;
LABEL_10:
  Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v86, *a2 + 80LL, 0, 6);
  v81[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v81);
  if ( *(_QWORD *)&v81[0] && *(_BYTE *)(*(_QWORD *)&v81[0] + 128LL) )
  {
    v8 = v86;
    if ( v87 > 0xF )
      v8 = (_QWORD *)v86[0];
    v9 = *(_DWORD *)(*a2 + 152LL);
    v10 = v84;
    if ( v85 > 0xF )
      LODWORD(v10) = v84[0];
    *(_OWORD *)v82 = 0;
    v83 = 0;
    std::string::_Construct<1,char const *>(
      v82,
      "Checkpoint.SMILES.LinkUpdate(%s):Id=%d, linkType=%s, delay=%f",
      (const char *)0x3D,
      v7,
      v37,
      *(double *)&Str);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,unsigned int,char const *,int>(
      (unsigned int)v81,
      (unsigned int)"BASIX_DCT",
      (unsigned int)v82,
      (_DWORD)v10,
      v9,
      (__int64)v8,
      (int)v6);
    std::string::_Tidy_deallocate(v82);
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)&v81[0] + 1);
  if ( *((_QWORD *)&v81[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *(_OWORD *)v82 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v82);
  if ( *(_QWORD *)v82 && *(_BYTE *)(*(_QWORD *)v82 + 128LL) )
  {
    std::_Integral_to_string<char,int>(v48, (unsigned int)(int)v6);
    memset(v43, 0, sizeof(v43));
    std::string::_Construct<1,char const *>(v43, ":", 1);
    memset(v45, 0, sizeof(v45));
    std::string::_Construct<1,char const *>(v45, "\"", 1);
    memset(v44, 0, sizeof(v44));
    std::string::_Construct<1,char const *>(v44, "\"", 1);
    v12 = std::operator+<char>(v78, v44, "DelayInMs");
    LOBYTE(v13) = v80[0];
    std::string::string(v46, v13, v12, v45);
    LOBYTE(v14) = v80[0];
    std::string::string(v70, v14, v46, v43);
    LOBYTE(v15) = v80[0];
    std::string::string(v62, v15, v70, v48);
    v57 = v61;
    memset(v42, 0, sizeof(v42));
    std::string::_Construct<1,char const *>(v42, "\"", 1);
    v16 = v86;
    if ( v87 > 0xF )
      v16 = (_QWORD *)v86[0];
    memset(v41, 0, sizeof(v41));
    std::string::_Construct<1,char const *>(v41, "\"", 1);
    memset(v40, 0, sizeof(v40));
    std::string::_Construct<1,char const *>(v40, ":", 1);
    memset(v55, 0, sizeof(v55));
    std::string::_Construct<1,char const *>(v55, "\"", 1);
    memset(v54, 0, sizeof(v54));
    std::string::_Construct<1,char const *>(v54, "\"", 1);
    v17 = std::operator+<char>(v77, v54, "LinkType");
    LOBYTE(v18) = v80[0];
    std::string::string(v69, v18, v17, v55);
    LOBYTE(v19) = v80[0];
    std::string::string(v68, v19, v69, v40);
    LOBYTE(v20) = v80[0];
    std::string::string(v67, v20, v68, v41);
    v21 = std::operator+<char>(v76, v67, v16);
    LOBYTE(v22) = v80[0];
    std::string::string(v61, v22, v21, v42);
    v58 = v60;
    std::_Integral_to_string<char,unsigned int>(v66, *(unsigned int *)(*a2 + 152LL));
    memset(v53, 0, sizeof(v53));
    std::string::_Construct<1,char const *>(v53, ":", 1);
    memset(v52, 0, sizeof(v52));
    std::string::_Construct<1,char const *>(v52, "\"", 1);
    memset(v51, 0, sizeof(v51));
    std::string::_Construct<1,char const *>(v51, "\"", 1);
    v23 = std::operator+<char>(v75, v51, "LinkId");
    LOBYTE(v24) = v80[0];
    std::string::string(v65, v24, v23, v52);
    LOBYTE(v25) = v80[0];
    std::string::string(v64, v25, v65, v53);
    LOBYTE(v26) = v80[0];
    std::string::string(v60, v26, v64, v66);
    memset(v50, 0, sizeof(v50));
    std::string::_Construct<1,char const *>(v50, "\"", 1);
    v27 = v84;
    if ( v85 > 0xF )
      v27 = (_QWORD *)v84[0];
    memset(v49, 0, sizeof(v49));
    std::string::_Construct<1,char const *>(v49, "\"", 1);
    memset(v39, 0, sizeof(v39));
    std::string::_Construct<1,char const *>(v39, ":", 1);
    memset(v81, 0, sizeof(v81));
    std::string::_Construct<1,char const *>(v81, "\"", 1);
    memset(v47, 0, sizeof(v47));
    std::string::_Construct<1,char const *>(v47, "\"", 1);
    v28 = std::operator+<char>(v73, v47, "Direction");
    LOBYTE(v29) = v80[0];
    std::string::string(v63, v29, v28, v81);
    LOBYTE(v30) = v80[0];
    std::string::string(v72, v30, v63, v39);
    LOBYTE(v31) = v80[0];
    std::string::string(v71, v31, v72, v49);
    v32 = std::operator+<char>(v74, v71, v27);
    LOBYTE(v33) = v80[0];
    std::string::string(v59, v33, v32, v50);
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
      (int)v82,
      (int)"RD_CHECKPOINT",
      0,
      (int)"Smiles",
      "LinkUpdate",
      "LinkUpdate",
      (__int64)v59,
      (__int64)v60,
      (__int64)v61,
      (__int64)v62);
    std::string::_Tidy_deallocate(v74);
    std::string::_Tidy_deallocate(v71);
    std::string::_Tidy_deallocate(v72);
    std::string::_Tidy_deallocate(v63);
    std::string::_Tidy_deallocate(v73);
    std::string::_Tidy_deallocate(v47);
    std::string::_Tidy_deallocate(v81);
    std::string::_Tidy_deallocate(v39);
    std::string::_Tidy_deallocate(v49);
    std::string::_Tidy_deallocate(v50);
    std::string::_Tidy_deallocate(v64);
    std::string::_Tidy_deallocate(v65);
    std::string::_Tidy_deallocate(v75);
    std::string::_Tidy_deallocate(v51);
    std::string::_Tidy_deallocate(v52);
    std::string::_Tidy_deallocate(v53);
    std::string::_Tidy_deallocate(v66);
    std::string::_Tidy_deallocate(v76);
    std::string::_Tidy_deallocate(v67);
    std::string::_Tidy_deallocate(v68);
    std::string::_Tidy_deallocate(v69);
    std::string::_Tidy_deallocate(v77);
    std::string::_Tidy_deallocate(v54);
    std::string::_Tidy_deallocate(v55);
    std::string::_Tidy_deallocate(v40);
    std::string::_Tidy_deallocate(v41);
    std::string::_Tidy_deallocate(v42);
    std::string::_Tidy_deallocate(v70);
    std::string::_Tidy_deallocate(v46);
    std::string::_Tidy_deallocate(v78);
    std::string::_Tidy_deallocate(v44);
    std::string::_Tidy_deallocate(v45);
    std::string::_Tidy_deallocate(v43);
    std::string::_Tidy_deallocate(v48);
  }
  v34 = *(volatile signed __int32 **)&v82[2];
  if ( *(_QWORD *)&v82[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v82[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  std::string::_Tidy_deallocate(v86);
  result = std::string::_Tidy_deallocate(v84);
  v36 = (volatile signed __int32 *)a2[1];
  if ( v36 )
  {
    result = (unsigned int)_InterlockedDecrement(v36 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      result = (unsigned int)_InterlockedDecrement(v36 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18026be60  mov     [rsp-8+arg_0], rbx
0x18026be65  mov     [rsp-8+arg_18], rsi
0x18026be6a  push    rbp
0x18026be6b  push    rdi
0x18026be6c  push    r13
0x18026be6e  push    r14
0x18026be70  push    r15
0x18026be72  lea     rbp, [rsp-530h]
0x18026be7a  mov     eax, 630h
0x18026be7f  call    _alloca_probe
0x18026be84  sub     rsp, rax
0x18026be87  movaps  [rsp+650h+var_30], xmm6
0x18026be8f  mov     rax, cs:__security_cookie
0x18026be96  xor     rax, rsp
0x18026be99  mov     [rbp+550h+var_38], rax
0x18026bea0  mov     r14, rdx
0x18026bea3  mov     [rbp+550h+var_3D8], rdx
0x18026beaa  mov     [rbp+550h+var_C0], r8b
0x18026beb1  xor     edx, edx
0x18026beb3  mov     rcx, r14
0x18026beb6  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18026bebb  test    al, al
0x18026bebd  jnz     loc_18026C875
0x18026bec3  mov     edi, 6
0x18026bec8  mov     r9d, edi
0x18026becb  xor     r8d, r8d
0x18026bece  lea     rdx, [rbp+550h+var_C0]
0x18026bed5  lea     rcx, [rbp+550h+var_78]
0x18026bedc  call    ??$ToString@W4Direction@LinkData@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4Direction@LinkData@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::LinkData::Direction>(Microsoft::Basix::Dct::LinkData::Direction const &,int,int)
0x18026bee1  nop
0x18026bee2  lea     r13d, [rdi-5]
0x18026bee6  mov     rbx, [r14]
0x18026bee9  cmp     [rbp+550h+var_C0], r13b
0x18026bef0  jnz     short loc_18026BF1A
0x18026bef2  mov     rcx, [rbx+0C0h]
0x18026bef9  call    ?num@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(void)
0x18026befe  test    eax, eax
0x18026bf00  jz      short loc_18026BF10
0x18026bf02  mov     rcx, [rbx+0C0h]
0x18026bf09  call    ?navg@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::navg(void)
0x18026bf0e  jmp     short loc_18026BF40
0x18026bf10  movsd   xmm6, cs:__real@408f400000000000
0x18026bf18  jmp     short loc_18026BF43
0x18026bf1a  mov     rcx, [rbx+0C8h]
0x18026bf21  call    ?num@?$SlidingStats@N$04$0A@$0A@@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,0,0>::num(void)
0x18026bf26  test    eax, eax
0x18026bf28  jle     short loc_18026BF38
0x18026bf2a  mov     rcx, [rbx+0C8h]
0x18026bf31  call    ?navg@?$SlidingStats@N$04$00$0A@@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(void)
0x18026bf36  jmp     short loc_18026BF40
0x18026bf38  movsd   xmm0, cs:__real@408f400000000000
0x18026bf40  movaps  xmm6, xmm0
0x18026bf43  mov     rdx, [r14]
0x18026bf46  add     rdx, 50h ; 'P'
0x18026bf4a  mov     r9d, edi
0x18026bf4d  xor     r8d, r8d
0x18026bf50  lea     rcx, [rbp+550h+var_58]
0x18026bf57  call    ??$ToString@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4LinkType@ISmiles@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &,int,int)
0x18026bf5c  nop
0x18026bf5d  xorps   xmm0, xmm0
0x18026bf60  movups  [rbp+550h+var_B8], xmm0
0x18026bf67  lea     rcx, [rbp+550h+var_B8]
0x18026bf6e  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18026bf73  nop
0x18026bf74  mov     rax, qword ptr [rbp+550h+var_B8]
0x18026bf7b  test    rax, rax
0x18026bf7e  jz      loc_18026C033
0x18026bf84  cmp     byte ptr [rax+80h], 0
0x18026bf8b  jz      loc_18026C033
0x18026bf91  lea     rsi, [rbp+550h+var_58]
0x18026bf98  cmp     [rbp+550h+var_40], 0Fh
0x18026bfa0  cmova   rsi, [rbp+550h+var_58]
0x18026bfa8  mov     rax, [r14]
0x18026bfab  mov     ebx, [rax+98h]
0x18026bfb1  lea     rdi, [rbp+550h+var_78]
0x18026bfb8  cmp     [rbp+550h+var_60], 0Fh
0x18026bfc0  cmova   rdi, [rbp+550h+var_78]
0x18026bfc8  xorps   xmm0, xmm0
0x18026bfcb  movups  xmmword ptr [rbp+550h+var_98], xmm0
0x18026bfd2  xorps   xmm1, xmm1
0x18026bfd5  movdqu  [rbp+550h+var_88], xmm1
0x18026bfdd  mov     r8d, 3Dh ; '='
0x18026bfe3  lea     rdx, aCheckpointSmil_0; "Checkpoint.SMILES.LinkUpdate(%s):Id=%d,"...
0x18026bfea  lea     rcx, [rbp+550h+var_98]
0x18026bff1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026bff6  nop
0x18026bff7  cvttsd2si eax, xmm6
0x18026bffb  mov     dword ptr [rsp+650h+var_620], eax
0x18026bfff  mov     [rsp+650h+Str], rsi
0x18026c004  mov     dword ptr [rsp+650h+var_630], ebx
0x18026c008  mov     r9, rdi
0x18026c00b  lea     r8, [rbp+550h+var_98]
0x18026c012  lea     rdx, aBasixDct; "BASIX_DCT"
0x18026c019  lea     rcx, [rbp+550h+var_B8]
0x18026c020  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBDIPEBDH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1I1H@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,uint,char const *,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *,uint,char const *,int)
0x18026c025  nop
0x18026c026  lea     rcx, [rbp+550h+var_98]
0x18026c02d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026c032  nop
0x18026c033  or      r15d, 0FFFFFFFFh
0x18026c037  mov     rbx, qword ptr [rbp+550h+var_B8+8]
0x18026c03e  test    rbx, rbx
0x18026c041  jz      short loc_18026C07C
0x18026c043  mov     eax, r15d
0x18026c046  lock xadd [rbx+8], eax
0x18026c04b  add     eax, r15d
0x18026c04e  jnz     short loc_18026C07C
0x18026c050  mov     rax, [rbx]
0x18026c053  mov     rcx, rbx
0x18026c056  mov     rax, [rax]
0x18026c059  call    cs:__guard_dispatch_icall_fptr
0x18026c05f  mov     eax, r15d
0x18026c062  lock xadd [rbx+0Ch], eax
0x18026c067  add     eax, r15d
0x18026c06a  jnz     short loc_18026C07C
0x18026c06c  mov     rax, [rbx]
0x18026c06f  mov     rcx, rbx
0x18026c072  mov     rax, [rax+8]
0x18026c076  call    cs:__guard_dispatch_icall_fptr
0x18026c07c  xorps   xmm0, xmm0
0x18026c07f  movups  xmmword ptr [rbp+550h+var_98], xmm0
0x18026c086  lea     rcx, [rbp+550h+var_98]
0x18026c08d  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18026c092  nop
0x18026c093  mov     rax, qword ptr [rbp+550h+var_98]
0x18026c09a  test    rax, rax
0x18026c09d  jz      loc_18026C7A3
0x18026c0a3  cmp     byte ptr [rax+80h], 0
0x18026c0aa  jz      loc_18026C7A3
0x18026c0b0  lea     rax, [rbp+550h+var_360]
0x18026c0b7  mov     [rsp+650h+var_600], rax
0x18026c0bc  cvttsd2si edx, xmm6
0x18026c0c0  lea     rcx, [rbp+550h+var_4D8]
0x18026c0c4  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x18026c0c9  nop
0x18026c0ca  xorps   xmm0, xmm0
0x18026c0cd  movups  [rbp+550h+var_578], xmm0
0x18026c0d1  xorps   xmm1, xmm1
0x18026c0d4  movdqu  [rbp+550h+var_568], xmm1
0x18026c0d9  mov     r8, r13
0x18026c0dc  lea     rdi, asc_1803D71C4; ":"
0x18026c0e3  mov     rdx, rdi
0x18026c0e6  lea     rcx, [rbp+550h+var_578]
0x18026c0ea  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c0ef  nop
0x18026c0f0  xorps   xmm0, xmm0
0x18026c0f3  movups  [rbp+550h+var_538], xmm0
0x18026c0f7  xorps   xmm1, xmm1
0x18026c0fa  movdqu  [rbp+550h+var_528], xmm1
0x18026c0ff  mov     r8, r13
0x18026c102  lea     rsi, asc_1803D71C8; "\""
0x18026c109  mov     rdx, rsi
0x18026c10c  lea     rcx, [rbp+550h+var_538]
0x18026c110  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c115  nop
0x18026c116  xorps   xmm0, xmm0
0x18026c119  movups  [rbp+550h+var_558], xmm0
0x18026c11d  xorps   xmm1, xmm1
0x18026c120  movdqu  [rbp+550h+var_548], xmm1
0x18026c125  mov     r8, r13
0x18026c128  mov     rdx, rsi
0x18026c12b  lea     rcx, [rbp+550h+var_558]
0x18026c12f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c134  nop
0x18026c135  lea     r8, aDelayinms; "DelayInMs"
0x18026c13c  lea     rdx, [rbp+550h+var_558]
0x18026c140  lea     rcx, [rbp+550h+var_160]
0x18026c147  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18026c14c  nop
0x18026c14d  lea     r9, [rbp+550h+var_538]
0x18026c151  mov     r8, rax
0x18026c154  mov     dl, [rbp+550h+var_C0]
0x18026c15a  lea     rcx, [rbp+550h+var_518]
0x18026c15e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c163  nop
0x18026c164  lea     r9, [rbp+550h+var_578]
0x18026c168  lea     r8, [rbp+550h+var_518]
0x18026c16c  mov     dl, [rbp+550h+var_C0]
0x18026c172  lea     rcx, [rbp+550h+var_260]
0x18026c179  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c17e  nop
0x18026c17f  lea     r9, [rbp+550h+var_4D8]
0x18026c183  lea     r8, [rbp+550h+var_260]
0x18026c18a  mov     dl, [rbp+550h+var_C0]
0x18026c190  lea     rcx, [rbp+550h+var_360]
0x18026c197  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c19c  nop
0x18026c19d  lea     rax, [rbp+550h+var_380]
0x18026c1a4  mov     [rbp+550h+var_3D0], rax
0x18026c1ab  xorps   xmm0, xmm0
0x18026c1ae  movups  [rbp+550h+var_598], xmm0
0x18026c1b2  xorps   xmm1, xmm1
0x18026c1b5  movdqu  [rbp+550h+var_588], xmm1
0x18026c1ba  mov     r8, r13
0x18026c1bd  mov     rdx, rsi
0x18026c1c0  lea     rcx, [rbp+550h+var_598]
0x18026c1c4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c1c9  nop
0x18026c1ca  lea     rbx, [rbp+550h+var_58]
0x18026c1d1  cmp     [rbp+550h+var_40], 0Fh
0x18026c1d9  cmova   rbx, [rbp+550h+var_58]
0x18026c1e1  xorps   xmm0, xmm0
0x18026c1e4  movups  [rbp+550h+var_5B8], xmm0
0x18026c1e8  xorps   xmm1, xmm1
0x18026c1eb  movdqu  [rbp+550h+var_5A8], xmm1
0x18026c1f0  mov     r8, r13
0x18026c1f3  mov     rdx, rsi
0x18026c1f6  lea     rcx, [rbp+550h+var_5B8]
0x18026c1fa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c1ff  nop
0x18026c200  xorps   xmm0, xmm0
0x18026c203  movups  [rsp+650h+var_5D8], xmm0
0x18026c208  xorps   xmm1, xmm1
0x18026c20b  movdqu  [rbp+550h+var_5C8], xmm1
0x18026c210  mov     r8, r13
0x18026c213  mov     rdx, rdi
0x18026c216  lea     rcx, [rsp+650h+var_5D8]
0x18026c21b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c220  nop
0x18026c221  xorps   xmm0, xmm0
0x18026c224  movups  [rbp+550h+var_3F8], xmm0
0x18026c22b  xorps   xmm1, xmm1
0x18026c22e  movdqu  [rbp+550h+var_3E8], xmm1
0x18026c236  mov     r8, r13
0x18026c239  mov     rdx, rsi
0x18026c23c  lea     rcx, [rbp+550h+var_3F8]
0x18026c243  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c248  nop
0x18026c249  xorps   xmm0, xmm0
0x18026c24c  movups  [rbp+550h+var_418], xmm0
0x18026c253  xorps   xmm1, xmm1
0x18026c256  movdqu  [rbp+550h+var_408], xmm1
0x18026c25e  mov     r8, r13
0x18026c261  mov     rdx, rsi
0x18026c264  lea     rcx, [rbp+550h+var_418]
0x18026c26b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c270  nop
0x18026c271  lea     r8, aLinktype; "LinkType"
0x18026c278  lea     rdx, [rbp+550h+var_418]
0x18026c27f  lea     rcx, [rbp+550h+var_180]
0x18026c286  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18026c28b  nop
0x18026c28c  lea     r9, [rbp+550h+var_3F8]
0x18026c293  mov     r8, rax
0x18026c296  mov     dl, [rbp+550h+var_C0]
0x18026c29c  lea     rcx, [rbp+550h+var_280]
0x18026c2a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c2a8  nop
0x18026c2a9  lea     r9, [rsp+650h+var_5D8]
0x18026c2ae  lea     r8, [rbp+550h+var_280]
0x18026c2b5  mov     dl, [rbp+550h+var_C0]
0x18026c2bb  lea     rcx, [rbp+550h+var_2A0]
0x18026c2c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c2c7  nop
0x18026c2c8  lea     r9, [rbp+550h+var_5B8]
0x18026c2cc  lea     r8, [rbp+550h+var_2A0]
0x18026c2d3  mov     dl, [rbp+550h+var_C0]
0x18026c2d9  lea     rcx, [rbp+550h+var_2C0]
0x18026c2e0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c2e5  nop
0x18026c2e6  mov     r8, rbx
0x18026c2e9  lea     rdx, [rbp+550h+var_2C0]
0x18026c2f0  lea     rcx, [rbp+550h+var_1A0]
0x18026c2f7  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18026c2fc  nop
0x18026c2fd  lea     r9, [rbp+550h+var_598]
0x18026c301  mov     r8, rax
0x18026c304  mov     dl, [rbp+550h+var_C0]
0x18026c30a  lea     rcx, [rbp+550h+var_380]
0x18026c311  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026c316  nop
0x18026c317  lea     rax, [rbp+550h+var_3A0]
0x18026c31e  mov     [rbp+550h+var_3C8], rax
0x18026c325  mov     rdx, [r14]
0x18026c328  mov     edx, [rdx+98h]
0x18026c32e  lea     rcx, [rbp+550h+var_2E0]
0x18026c335  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18026c33a  nop
0x18026c33b  xorps   xmm0, xmm0
0x18026c33e  movups  [rbp+550h+var_438], xmm0
0x18026c345  xorps   xmm1, xmm1
0x18026c348  movdqu  [rbp+550h+var_428], xmm1
0x18026c350  mov     r8, r13
0x18026c353  mov     rdx, rdi
0x18026c356  lea     rcx, [rbp+550h+var_438]
0x18026c35d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c362  nop
0x18026c363  xorps   xmm0, xmm0
0x18026c366  movups  [rbp+550h+var_458], xmm0
0x18026c36d  xorps   xmm1, xmm1
0x18026c370  movdqu  [rbp+550h+var_448], xmm1
0x18026c378  mov     r8, r13
0x18026c37b  mov     rdx, rsi
0x18026c37e  lea     rcx, [rbp+550h+var_458]
0x18026c385  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026c38a  nop
0x18026c38b  xorps   xmm0, xmm0
0x18026c38e  movups  [rbp+550h+var_478], xmm0
0x18026c395  xorps   xmm1, xmm1
0x18026c398  movdqu  [rbp+550h+var_468], xmm1
  ... truncated ...
```
