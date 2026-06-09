# Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue(bool)

- ea: `0x1801338a0`
- end: `0x180134708`
- name: `?_DrainCompletionQueue@WinsockDCTRioChannelContext@Dct@Basix@Microsoft@@AEAAX_N@Z`
- size: `3688`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *__hidden this, bool)`
- caller_count: `4`
- callee_count: `47`
- tags: `broker_com_uri`

## callers

- `0x18012f4f0`
- `0x180131e00`
- `0x180131f60`
- `0x180132cc0`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180017348`
- `0x180017380`
- `0x180017518`
- `0x180018ea4`
- `0x18001902c`
- `0x180024700`
- `0x180027b84`
- `0x180027bf8`
- `0x180029b1c`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800371cc`
- `0x1800377b4`
- `0x18003d8fc`
- `0x18003f5c0`
- `0x18004569c`
- `0x1800bb210`
- `0x18011963c`
- `0x18012baa0`
- `0x18012c230`
- `0x18012c5fc`
- `0x18012da70`
- `0x18012daa0`
- `0x18012f04c`
- `0x1801338a0`
- `0x180134c48`
- `0x180151be4`
- `0x1801acb74`
- `0x1802e9e58`
- `0x1802ea490`
- `0x1802eb914`
- `0x1802ed54c`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`
- `0x180375cc0`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x1801344a5`
- `WS2_32!__imp_WSAGetLastError` at `0x180134621`
- `WS2_32!__imp_WSAGetLastError` at `0x1801344a5`
- `WS2_32!__imp_WSAGetLastError` at `0x180134621`

## string_xrefs

- `0x180134027`: `Failed in IO Read: Local: `
- `0x180134452`: `Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue`
- `0x1801345ce`: `Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue`
- `0x180133c41`: `_DrainCompletionQueue() incomplete write: bytesTransfered(%d), packetSize=%d`
- `0x180134274`: `Failed in IO Write for peer: `
- `0x18013443d`: `RIODequeueCompletion failed\n    %s(%d): %s()`
- `0x1801344ed`: `RIODequeueCompletion failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=132
void __fastcall Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue(
        Microsoft::Basix::Dct::WinsockDCTRioChannelContext *this,
        char a2)
{
  Microsoft::Basix::Dct::WinsockDCTRioChannelContext *v3; // r14
  Microsoft::Basix::Dct::WinsockDCTRioChannelContext *v4; // r12
  unsigned int v5; // r15d
  Microsoft::Basix::Dct::WinsockDCTRioChannelContext *v6; // rax
  _QWORD *v7; // rcx
  unsigned int v8; // eax
  int v9; // ecx
  __int64 v10; // r13
  int v11; // eax
  __int64 v12; // rbx
  const void *v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int128 *v18; // rcx
  Microsoft::Basix::Containers::FlexOBuffer *v19; // rax
  unsigned __int64 v20; // rax
  int v21; // r9d
  int v22; // ebx
  volatile signed __int32 *v23; // rbx
  __int64 v24; // rax
  volatile signed __int32 *v25; // rbx
  _Mtx_t *i; // rbx
  _Mtx_t *j; // rbx
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  Microsoft::Basix *v32; // rcx
  const struct std::error_category *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  int v39; // r15d
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // ebx
  Microsoft::Basix *v47; // rcx
  const struct std::error_category *v48; // r8
  int v49; // edx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v54; // rax
  const char *v55; // r8
  int v56; // r9d
  int Error; // eax
  signed int v58; // ebx
  Microsoft::Basix *v59; // rcx
  const struct std::error_category *v60; // rax
  __int64 v61; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v62; // rax
  const char *v63; // r8
  int v64; // r9d
  int v65; // eax
  signed int v66; // ebx
  Microsoft::Basix *v67; // rcx
  const struct std::error_category *v68; // rax
  __int64 *Description; // rax
  const char *v70; // r9
  __int64 v71; // rbx
  volatile signed __int32 *v72; // rbx
  __int64 *v73; // rax
  const char *v74; // r9
  __int64 v75; // rbx
  volatile signed __int32 *v76; // rbx
  __int64 *v77; // rax
  const char *v78; // r9
  __int64 v79; // rbx
  volatile signed __int32 *v80; // rbx
  const char *v81; // r9
  volatile signed __int32 *v82; // rbx
  __int64 *v83; // rax
  const char *v84; // r9
  __int64 v85; // rbx
  volatile signed __int32 *v86; // rbx
  __int64 *v87; // rax
  const char *v88; // r9
  __int64 v89; // rbx
  volatile signed __int32 *v90; // rbx
  __int64 *v91; // rax
  const char *v92; // r9
  __int64 v93; // rbx
  volatile signed __int32 *v94; // rbx
  const char *v95; // r9
  volatile signed __int32 *v96; // rbx
  const char *v97; // [rsp+20h] [rbp-548h]
  int v98; // [rsp+28h] [rbp-540h]
  const char *v99; // [rsp+30h] [rbp-538h]
  const char *v100; // [rsp+20h] [rbp-548h]
  int v101; // [rsp+28h] [rbp-540h]
  const char *v102; // [rsp+30h] [rbp-538h]
  const char *v103; // [rsp+20h] [rbp-548h]
  int v104; // [rsp+28h] [rbp-540h]
  const char *v105; // [rsp+30h] [rbp-538h]
  const char *v106; // [rsp+20h] [rbp-548h]
  int v107; // [rsp+28h] [rbp-540h]
  const char *v108; // [rsp+30h] [rbp-538h]
  const char *v109; // [rsp+20h] [rbp-548h]
  int v110; // [rsp+28h] [rbp-540h]
  const char *v111; // [rsp+30h] [rbp-538h]
  const char *v112; // [rsp+20h] [rbp-548h]
  int v113; // [rsp+28h] [rbp-540h]
  const char *v114; // [rsp+30h] [rbp-538h]
  const char *v115; // [rsp+20h] [rbp-548h]
  int v116; // [rsp+28h] [rbp-540h]
  const char *v117; // [rsp+30h] [rbp-538h]
  const char *v118; // [rsp+20h] [rbp-548h]
  int v119; // [rsp+28h] [rbp-540h]
  const char *v120; // [rsp+30h] [rbp-538h]
  const char *v121; // [rsp+20h] [rbp-548h]
  unsigned int v122; // [rsp+40h] [rbp-528h]
  unsigned int v123; // [rsp+44h] [rbp-524h]
  int v124; // [rsp+48h] [rbp-520h]
  unsigned int v125; // [rsp+4Ch] [rbp-51Ch]
  __int64 v126; // [rsp+50h] [rbp-518h] BYREF
  Microsoft::Basix::Dct::WinsockDCTRioChannelContext *v127; // [rsp+58h] [rbp-510h]
  __int64 v128; // [rsp+68h] [rbp-500h]
  __int128 v129; // [rsp+70h] [rbp-4F8h] BYREF
  _BYTE v130[32]; // [rsp+80h] [rbp-4E8h] BYREF
  _OWORD v131[2]; // [rsp+A0h] [rbp-4C8h] BYREF
  _BYTE v132[32]; // [rsp+C0h] [rbp-4A8h] BYREF
  _BYTE v133[8]; // [rsp+E0h] [rbp-488h] BYREF
  volatile signed __int32 *v134; // [rsp+E8h] [rbp-480h]
  Microsoft::Basix::Dct::WinsockDCTRioChannelContext *v135; // [rsp+F0h] [rbp-478h]
  _BYTE v136[32]; // [rsp+F8h] [rbp-470h] BYREF
  _BYTE v137[16]; // [rsp+118h] [rbp-450h] BYREF
  _BYTE v138[32]; // [rsp+128h] [rbp-440h] BYREF
  const boost::exception *v139; // [rsp+148h] [rbp-420h] BYREF
  const Microsoft::Basix::Exception *v140; // [rsp+150h] [rbp-418h] BYREF
  const std::exception *v141; // [rsp+158h] [rbp-410h] BYREF
  const boost::exception *v142; // [rsp+160h] [rbp-408h] BYREF
  _BYTE v143[16]; // [rsp+168h] [rbp-400h] BYREF
  _BYTE v144[16]; // [rsp+178h] [rbp-3F0h] BYREF
  _BYTE v145[32]; // [rsp+188h] [rbp-3E0h] BYREF
  _BYTE v146[32]; // [rsp+1A8h] [rbp-3C0h] BYREF
  const Microsoft::Basix::Exception *v147; // [rsp+1C8h] [rbp-3A0h] BYREF
  _BYTE v148[32]; // [rsp+1D0h] [rbp-398h] BYREF
  const std::exception *v149; // [rsp+1F0h] [rbp-378h] BYREF
  _BYTE v150[16]; // [rsp+1F8h] [rbp-370h] BYREF
  _BYTE v151[32]; // [rsp+208h] [rbp-360h] BYREF
  _BYTE v152[32]; // [rsp+228h] [rbp-340h] BYREF
  _BYTE v153[152]; // [rsp+248h] [rbp-320h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+2E0h] [rbp-288h] BYREF
  _BYTE v155[144]; // [rsp+370h] [rbp-1F8h] BYREF
  __int128 v156; // [rsp+400h] [rbp-168h] BYREF
  __int64 v157; // [rsp+410h] [rbp-158h]
  __int64 v158; // [rsp+418h] [rbp-150h]
  _Mtx_t v159; // [rsp+420h] [rbp-148h] BYREF
  __int128 v160; // [rsp+428h] [rbp-140h] BYREF
  __int64 v161; // [rsp+438h] [rbp-130h]
  __int64 v162; // [rsp+440h] [rbp-128h]
  _QWORD v163[2]; // [rsp+448h] [rbp-120h] BYREF
  __int128 v164; // [rsp+458h] [rbp-110h] BYREF
  __int64 v165; // [rsp+468h] [rbp-100h]
  __int128 v166; // [rsp+470h] [rbp-F8h] BYREF
  __int64 v167; // [rsp+480h] [rbp-E8h]
  _BYTE v168[32]; // [rsp+488h] [rbp-E0h] BYREF
  _BYTE v169[24]; // [rsp+4A8h] [rbp-C0h] BYREF
  int v170; // [rsp+4C0h] [rbp-A8h] BYREF
  size_t Size[15]; // [rsp+4C4h] [rbp-A4h]

  v3 = this;
  v4 = this;
  v127 = this;
  v5 = 0;
  v122 = 0;
  v166 = 0;
  v167 = 0;
  v164 = 0;
  v165 = 0;
  v159 = (_Mtx_t)200;
  std::vector<std::reference_wrapper<Microsoft::Basix::Dct::Rcp::SenderPacketState>>::_Reallocate<0>(&v166, &v159);
  v159 = (_Mtx_t)200;
  if ( (unsigned __int64)((v165 - (__int64)v164) >> 3) < 0xC8 )
    std::vector<std::reference_wrapper<Microsoft::Basix::Dct::Rcp::SenderPacketState>>::_Reallocate<0>(&v164, &v159);
  v159 = (Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 3992);
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v159 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v159 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( a2 )
    *((_BYTE *)v3 + 4536) = 0;
  v6 = (Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 4456);
  v135 = (Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 4456);
  v7 = (_QWORD *)((char *)v3 + 6640);
  for ( v163[0] = (char *)v3 + 6640; ; v7 = (_QWORD *)v163[0] )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64))v6)(*v7, &v170, 5);
    v123 = v8;
    if ( !v8 )
      break;
    if ( v8 == -1 )
      goto LABEL_81;
    v125 = 0;
    while ( 2 )
    {
      if ( v125 < v123 )
      {
        v9 = *(&v170 + 6 * v125);
        v124 = v9;
        v10 = *(size_t *)((char *)&Size[3 * v125 + 1] + 4);
        v126 = v10;
        v11 = *(_DWORD *)(v10 + 284);
        if ( v11 != 1 )
        {
          if ( v11 != 2 )
            goto LABEL_45;
          *((_BYTE *)v3 + *(int *)(v10 + 280) + 6176) = 0;
          *((_DWORD *)v4 + 19) += *((_DWORD *)v3 + 1088);
          _InterlockedIncrement((volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v4 + 80));
          ++*((_DWORD *)v3 + 1595);
          v128 = *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(v10 + 88))
                           + 136);
          v19 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*(Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **)(v10 + 88));
          v20 = Microsoft::Basix::Containers::FlexOBuffer::Size(v19);
          *(_QWORD *)&v160 = v20 - v128;
          if ( LODWORD(Size[3 * v125]) != v20 - v128 )
          {
            v156 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v156);
            if ( (_QWORD)v156 && *(_BYTE *)(v156 + 128) )
            {
              v22 = Size[3 * v125];
              memset(v131, 0, sizeof(v131));
              std::string::_Construct<1,char const *>(
                v131,
                "_DrainCompletionQueue() incomplete write: bytesTransfered(%d), packetSize=%d",
                76,
                v21);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned __int64>(
                (unsigned int)&v156,
                (unsigned int)"NANO_DCT",
                (unsigned int)v131,
                v22,
                v160);
              std::string::_Tidy_deallocate(v131);
            }
            v23 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
            if ( *((_QWORD *)&v156 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
                if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
              }
            }
          }
          v24 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*(_QWORD *)(v10 + 88));
          *(_QWORD *)(v24 + 136) = v128 + LODWORD(Size[3 * v125]);
          if ( !*((_BYTE *)v3 + 4096) )
          {
            if ( !LODWORD(Size[3 * v125]) )
              goto LABEL_45;
            goto LABEL_41;
          }
          if ( !v124 && LODWORD(Size[3 * v125]) )
          {
LABEL_39:
            Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
              v3,
              (const struct std::exception_ptr *)(v10 + 104),
              0);
LABEL_41:
            v17 = *((_QWORD *)&v166 + 1);
            if ( *((_QWORD *)&v166 + 1) != v167 )
            {
              **((_QWORD **)&v166 + 1) = v10;
              *((_QWORD *)&v166 + 1) += 8LL;
              goto LABEL_45;
            }
            v18 = &v166;
            goto LABEL_44;
          }
          goto LABEL_71;
        }
        v12 = *(int *)(v10 + 280);
        v128 = v12;
        *((_BYTE *)v3 + v12 + 6432) = 0;
        ++*((_DWORD *)v3 + 1658);
        if ( !LODWORD(Size[3 * v125]) )
          goto LABEL_45;
        if ( !*((_BYTE *)v3 + 4096) )
          goto LABEL_18;
        if ( !v9 )
        {
          v156 = 0;
          __ExceptionPtrCreate(&v156);
          Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
            v3,
            (const struct std::exception_ptr *)&v156,
            1);
          __ExceptionPtrDestroy(&v156);
LABEL_18:
          v13 = (const void *)(*((_QWORD *)v3 + 800) + *((_QWORD *)v3 + 544) * v12);
          v14 = LODWORD(Size[3 * v125]);
          Microsoft::Basix::Containers::FlexIBuffer::Resize(
            (Microsoft::Basix::Containers::FlexIBuffer *)(v10 + 40),
            (unsigned int)v14);
          memmove(*(void **)(v10 + 56), v13, (unsigned int)v14);
          *(_QWORD *)(v10 + 120) = v14;
          v15 = 28 * v128;
          v16 = *((_QWORD *)v3 + 802);
          *(_OWORD *)(v10 + 144) = *(_OWORD *)(28 * v128 + v16);
          *(_QWORD *)(v10 + 160) = *(_QWORD *)(v15 + v16 + 16);
          *(_DWORD *)(v10 + 168) = *(_DWORD *)(v15 + v16 + 24);
          *(_DWORD *)(v10 + 272) = 28;
          v17 = *((_QWORD *)&v164 + 1);
          if ( *((_QWORD *)&v164 + 1) != v165 )
          {
            **((_QWORD **)&v164 + 1) = v10;
            *((_QWORD *)&v164 + 1) += 8LL;
            goto LABEL_45;
          }
          v18 = &v164;
LABEL_44:
          std::vector<Microsoft::Basix::Dct::WinsockDCTIORequest *>::_Emplace_reallocate<Microsoft::Basix::Dct::WinsockDCTIORequest * const &>(
            v18,
            v17,
            &v126);
          goto LABEL_45;
        }
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)v169, 0x10u);
        v28 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _BYTE *))(*(_QWORD *)v3 + 104LL))(
                v3,
                v132);
        std::string::string(v131, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
        v29 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _BYTE *))(*(_QWORD *)v3 + 104LL))(
                v3,
                v148);
        v30 = std::operator+<char>(v146, "Failed in IO Read: Local: ", (char *)v4 + 104);
        v31 = std::operator+<char>(v145, v30, ", channelClassName=");
        LODWORD(v29) = std::operator+<char>(v168, v31, v29);
        v33 = Microsoft::Basix::WindowsCategory(v32);
        v156 = *(_OWORD *)std::error_code::error_code((std::error_code *)v150, v124, v33);
        v34 = Microsoft::Basix::SystemException::SystemException(
                (unsigned int)v153,
                (unsigned int)&v156,
                v29,
                (unsigned int)v131,
                780,
                v28);
        std::make_exception_ptr<Microsoft::Basix::SystemException>(v169, v34);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v168);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v145);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v146);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v148);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v131);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v132);
        Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
          v3,
          (const struct std::exception_ptr *)v169,
          1);
        v35 = std::exception_ptr::exception_ptr((std::exception_ptr *)v143, (const struct std::exception_ptr *)v169);
        try
        {
          std::rethrow_exception(v35);
        }
        catch ( const Microsoft::Basix::Exception *v147 )
        {
          v160 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v160);
          if ( (_QWORD)v160 && *(_BYTE *)(v160 + 128) )
          {
            Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v132, v147);
            v71 = (__int64)Description;
            if ( (unsigned __int64)Description[3] > 0xF )
              v71 = *Description;
            v156 = 0;
            v157 = 0;
            v158 = 0;
            std::string::_Construct<1,char const *>(
              &v156,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v70,
              v118,
              v119,
              v120);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v160,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v156,
              (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
              v71,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              14,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v156);
            std::string::_Tidy_deallocate(v132);
          }
          v72 = (volatile signed __int32 *)*((_QWORD *)&v160 + 1);
          if ( *((_QWORD *)&v160 + 1)
            && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v160 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
            if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
          }
          goto LABEL_17;
        }
        catch ( const std::exception *v149 )
        {
          v160 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v160);
          if ( (_QWORD)v160 && *(_BYTE *)(v160 + 128) )
          {
            v73 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v132, v149);
            v75 = (__int64)v73;
            if ( (unsigned __int64)v73[3] > 0xF )
              v75 = *v73;
            v156 = 0;
            v157 = 0;
            v158 = 0;
            std::string::_Construct<1,char const *>(
              &v156,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v74,
              v115,
              v116,
              v117);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v160,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v156,
              (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
              v75,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              14,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v156);
            std::string::_Tidy_deallocate(v132);
          }
          v76 = (volatile signed __int32 *)*((_QWORD *)&v160 + 1);
          if ( *((_QWORD *)&v160 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v160 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
              if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
            }
          }
          goto LABEL_17;
        }
        catch ( const boost::exception *v139 )
        {
          v160 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v160);
          if ( (_QWORD)v160 && *(_BYTE *)(v160 + 128) )
          {
            v77 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v132, v139);
            v79 = (__int64)v77;
            if ( (unsigned __int64)v77[3] > 0xF )
              v79 = *v77;
            v156 = 0;
            v157 = 0;
            v158 = 0;
            std::string::_Construct<1,char const *>(
              &v156,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v78,
              v112,
              v113,
              v114);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v160,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v156,
              (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
              v79,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              14,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v156);
            std::string::_Tidy_deallocate(v132);
          }
          v80 = (volatile signed __int32 *)*((_QWORD *)&v160 + 1);
          if ( *((_QWORD *)&v160 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v160 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
              if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
            }
          }
          goto LABEL_17;
        }
        catch ( ... )
        {
          v160 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v160);
          if ( (_QWORD)v160 && *(_BYTE *)(v160 + 128) )
          {
            v156 = 0;
            v157 = 0;
            v158 = 0;
            std::string::_Construct<1,char const *>(
              &v156,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v81,
              v109,
              v110,
              v111);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v160,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v156,
              (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
              (__int64)"due to unknown error",
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              14,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v156);
          }
          v82 = (volatile signed __int32 *)*((_QWORD *)&v160 + 1);
          if ( *((_QWORD *)&v160 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v160 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
              if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
            }
          }
LABEL_17:
          __ExceptionPtrDestroy(v169);
          v5 = v122;
          v4 = v127;
          v3 = v127;
LABEL_45:
          ++v125;
          continue;
        }
LABEL_71:
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)v133, 0x10u);
        std::shared_ptr<Microsoft::Basix::Dct::SockaddrStorage>::shared_ptr<Microsoft::Basix::Dct::SockaddrStorage>(
          v133,
          v10 + 128);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                v133,
                                v36) )
        {
          v37 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v133);
          v38 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 8LL))(v37, v148);
          v39 = v5 | 1;
        }
        else
        {
          v38 = std::string::string(v132, (const char *)&Str1);
          v39 = v5 | 2;
        }
        v122 = v39;
        std::string::string(v168, v38);
        if ( (v39 & 2) != 0 )
        {
          v39 &= ~2u;
          v122 = v39;
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v132);
        }
        if ( (v39 & 1) != 0 )
        {
          v122 = v39 & 0xFFFFFFFE;
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v148);
        }
        v40 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _BYTE *))(*(_QWORD *)v3 + 104LL))(
                v3,
                v130);
        std::string::string(v131, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
        v41 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _BYTE *))(*(_QWORD *)v3 + 104LL))(
                v3,
                v136);
        v42 = std::operator+<char>(v138, "Failed in IO Write for peer: ", v168);
        v43 = std::operator+<char>(v152, v42, ", local: ");
        v44 = std::operator+<char>(v151, v43, (char *)v4 + 104);
        v45 = std::operator+<char>(v145, v44, ", channelClassName=");
        v46 = std::operator+<char>(v146, v45, v41);
        v48 = Microsoft::Basix::WindowsCategory(v47);
        v49 = 4306;
        if ( v124 )
          v49 = v124;
        v156 = *(_OWORD *)std::error_code::error_code((std::error_code *)v137, v49, v48);
        v50 = Microsoft::Basix::SystemException::SystemException(
                (unsigned int)v153,
                (unsigned int)&v156,
                v46,
                (unsigned int)v131,
                826,
                v40);
        v51 = std::make_exception_ptr<Microsoft::Basix::SystemException>(v144, v50);
        std::exception_ptr::operator=(v10 + 104, v51);
        std::exception_ptr::~exception_ptr((std::exception_ptr *)v144);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v146);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v145);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v151);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v152);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v138);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v136);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v131);
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v130);
        v52 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)&v129,
                (const struct std::exception_ptr *)(v10 + 104));
        try
        {
          std::rethrow_exception(v52);
        }
        catch ( const Microsoft::Basix::Exception *v140 )
        {
          v156 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v156);
          if ( (_QWORD)v156 && *(_BYTE *)(v156 + 128) )
          {
            v83 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v130, v140);
            v85 = (__int64)v83;
            if ( (unsigned __int64)v83[3] > 0xF )
              v85 = *v83;
            v160 = 0;
            v161 = 0;
            v162 = 0;
            std::string::_Construct<1,char const *>(
              &v160,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v84,
              v106,
              v107,
              v108);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v156,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v160,
              (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
              v85,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              59,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v160);
            std::string::_Tidy_deallocate(v130);
          }
          v86 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
          if ( *((_QWORD *)&v156 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
              if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
            }
          }
          goto LABEL_34;
        }
        catch ( const std::exception *v141 )
        {
          v156 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v156);
          if ( (_QWORD)v156 && *(_BYTE *)(v156 + 128) )
          {
            v87 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v130, v141);
            v89 = (__int64)v87;
            if ( (unsigned __int64)v87[3] > 0xF )
              v89 = *v87;
            v160 = 0;
            v161 = 0;
            v162 = 0;
            std::string::_Construct<1,char const *>(
              &v160,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v88,
              v103,
              v104,
              v105);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v156,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v160,
              (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
              v89,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              59,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v160);
            std::string::_Tidy_deallocate(v130);
          }
          v90 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
          if ( *((_QWORD *)&v156 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
              if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
            }
          }
          goto LABEL_34;
        }
        catch ( const boost::exception *v142 )
        {
          v156 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v156);
          if ( (_QWORD)v156 && *(_BYTE *)(v156 + 128) )
          {
            v91 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v130, v142);
            v93 = (__int64)v91;
            if ( (unsigned __int64)v91[3] > 0xF )
              v93 = *v91;
            v160 = 0;
            v161 = 0;
            v162 = 0;
            std::string::_Construct<1,char const *>(
              &v160,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v92,
              v100,
              v101,
              v102);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v156,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v160,
              (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
              v93,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              59,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v160);
            std::string::_Tidy_deallocate(v130);
          }
          v94 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
          if ( *((_QWORD *)&v156 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
              if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
            }
          }
          goto LABEL_34;
        }
        catch ( ... )
        {
          v156 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v156);
          if ( (_QWORD)v156 && *(_BYTE *)(v156 + 128) )
          {
            v160 = 0;
            v161 = 0;
            v162 = 0;
            std::string::_Construct<1,char const *>(
              &v160,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v95,
              v97,
              v98,
              v99);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v156,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v160,
              (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
              (__int64)"due to unknown error",
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              59,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            std::string::_Tidy_deallocate(&v160);
          }
          v96 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
          if ( *((_QWORD *)&v156 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
              if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
            }
          }
LABEL_34:
          std::string::_Tidy_deallocate(v168);
          v25 = v134;
          if ( v134 )
          {
            if ( _InterlockedExchangeAdd(v134 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
              if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          v4 = v127;
          v10 = v126;
          v5 = v122;
          v3 = v127;
          goto LABEL_39;
        }
LABEL_81:
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)v163, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v163);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                v163,
                                v53) )
        {
          v54 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v163);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v54) )
          {
            std::string::string(v168, "RIODequeueCompletion failed\n    %s(%d): %s()", v55, v56, v121);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)v163,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v168,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              80,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v168);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v163);
        Error = WSAGetLastError();
        v58 = (unsigned __int16)Error | 0x80070000;
        if ( Error <= 0 )
          v58 = Error;
        if ( v58 >= 0 )
          v58 = -2147467259;
        std::string::string(v130, (const char *)&Str1);
        std::string::string(v136, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
        std::string::string(v138, "RIODequeueCompletion failed");
        v60 = Microsoft::Basix::WindowsCategory(v59);
        v129 = *(_OWORD *)std::error_code::error_code((std::error_code *)v137, v58, v60);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v129,
          (unsigned int)v138,
          (unsigned int)v136,
          848,
          (__int64)v130);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
      break;
    }
    v6 = v135;
  }
  if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v3 + 16) != 34
    && !*((_BYTE *)v3 + 4536) )
  {
    if ( (*((unsigned int (__fastcall **)(_QWORD))v4 + 559))(*((_QWORD *)v3 + 830)) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)v163, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v163);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              v163,
                              v61) )
      {
        v62 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v163);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v62) )
        {
          std::string::string(v168, "RIONotify failed\n    %s(%d): %s()", v63, v64, v121);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)v163,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v168,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
            85,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_DrainCompletionQueue");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v168);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v163);
      v65 = WSAGetLastError();
      v66 = (unsigned __int16)v65 | 0x80070000;
      if ( v65 <= 0 )
        v66 = v65;
      if ( v66 >= 0 )
        v66 = -2147467259;
      std::string::string(v130, (const char *)&Str1);
      std::string::string(v136, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
      std::string::string(v138, "RIONotify failed");
      v68 = Microsoft::Basix::WindowsCategory(v67);
      v129 = *(_OWORD *)std::error_code::error_code((std::error_code *)v137, v66, v68);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)v155,
        (unsigned int)&v129,
        (unsigned int)v138,
        (unsigned int)v136,
        853,
        (__int64)v130);
      throw (Microsoft::Basix::SystemException *)v155;
    }
    *((_BYTE *)v3 + 4536) = 1;
  }
  Mtx_unlock(v159);
  for ( i = (_Mtx_t *)v166; i != *((_Mtx_t **)&v166 + 1); ++i )
  {
    v159 = *i;
    (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _Mtx_t *))(*(_QWORD *)v3 + 184LL))(
      v3,
      &v159);
    if ( v159 )
      (**(void (__fastcall ***)(_Mtx_t, __int64))v159)(v159, 1);
  }
  for ( j = (_Mtx_t *)v164; j != *((_Mtx_t **)&v164 + 1); ++j )
  {
    v159 = *j;
    (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTRioChannelContext *, _Mtx_t *, __int64))(*(_QWORD *)v3 + 176LL))(
      v3,
      &v159,
      1);
    if ( v159 )
      (**(void (__fastcall ***)(_Mtx_t, __int64))v159)(v159, 1);
  }
  v163[0] = (char *)v3 + 3992;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v3 + 1017) == 0x7FFFFFFF )
  {
    *((_DWORD *)v3 + 1017) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v3 + 16) != 34
    && *((_QWORD *)v3 + 497)
    && *((int *)v3 + 1658) >= 10 )
  {
    Microsoft::Basix::Dct::WinsockDCTRioChannelContext::_PostSocketRead(v3);
  }
  Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTRioChannelContext *)((char *)v3 + 3992));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>>>>>::_Tidy(&v164);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned short const,Microsoft::Basix::Dct::Rcp::UDPRateControllerHost::SequencerReader::CRCInfo>>>>>>::_Tidy(&v166);
}

```

## disassembly

```asm
0x1801338a0  mov     [rsp+arg_8], rbx
0x1801338a5  mov     [rsp+arg_10], rdi
0x1801338aa  mov     [rsp+arg_18], r12
0x1801338af  push    r13
0x1801338b1  push    r14
0x1801338b3  push    r15
0x1801338b5  mov     eax, 550h
0x1801338ba  call    _alloca_probe
0x1801338bf  sub     rsp, rax
0x1801338c2  mov     rax, cs:__security_cookie
0x1801338c9  xor     rax, rsp
0x1801338cc  mov     [rsp+568h+var_28], rax
0x1801338d4  mov     bl, dl
0x1801338d6  mov     r14, rcx
0x1801338d9  mov     r12, rcx
0x1801338dc  mov     [rsp+568h+var_510], rcx
0x1801338e1  xor     r15d, r15d
0x1801338e4  mov     [rsp+568h+var_528], r15d
0x1801338e9  xor     eax, eax
0x1801338eb  xorps   xmm1, xmm1
0x1801338ee  movdqu  [rsp+568h+var_F8], xmm1
0x1801338f7  mov     [rsp+568h+var_E8], rax
0x1801338ff  movdqu  [rsp+568h+var_110], xmm1
0x180133908  mov     [rsp+568h+var_100], rax
0x180133910  mov     edi, 0C8h
0x180133915  mov     [rsp+568h+var_148], rdi
0x18013391d  lea     rdx, [rsp+568h+var_148]
0x180133925  lea     rcx, [rsp+568h+var_F8]
0x18013392d  call    ??$_Reallocate@$0A@@?$vector@V?$reference_wrapper@USenderPacketState@Rcp@Dct@Basix@Microsoft@@@std@@V?$allocator@V?$reference_wrapper@USenderPacketState@Rcp@Dct@Basix@Microsoft@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::reference_wrapper<Microsoft::Basix::Dct::Rcp::SenderPacketState>>::_Reallocate<0>(unsigned __int64 &)
0x180133932  mov     [rsp+568h+var_148], rdi
0x18013393a  mov     rax, [rsp+568h+var_100]
0x180133942  sub     rax, qword ptr [rsp+568h+var_110]
0x18013394a  sar     rax, 3
0x18013394e  cmp     rax, rdi
0x180133951  jnb     short loc_180133968
0x180133953  lea     rdx, [rsp+568h+var_148]
0x18013395b  lea     rcx, [rsp+568h+var_110]
0x180133963  call    ??$_Reallocate@$0A@@?$vector@V?$reference_wrapper@USenderPacketState@Rcp@Dct@Basix@Microsoft@@@std@@V?$allocator@V?$reference_wrapper@USenderPacketState@Rcp@Dct@Basix@Microsoft@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::reference_wrapper<Microsoft::Basix::Dct::Rcp::SenderPacketState>>::_Reallocate<0>(unsigned __int64 &)
0x180133968  lea     rcx, [r14+0F98h]; _Mtx_t
0x18013396f  mov     [rsp+568h+var_148], rcx
0x180133977  call    _Mtx_lock
0x18013397c  test    eax, eax
0x18013397e  jnz     loc_180133FAA
0x180133984  mov     rax, [rsp+568h+var_148]
0x18013398c  cmp     dword ptr [rax+4Ch], 7FFFFFFFh
0x180133993  jz      loc_180133FB5
0x180133999  test    bl, bl
0x18013399b  jz      short loc_1801339A5
0x18013399d  mov     byte ptr [r14+11B8h], 0
0x1801339a5  lea     rax, [r14+1168h]
0x1801339ac  mov     [rsp+568h+var_478], rax
0x1801339b4  lea     rcx, [r14+19F0h]
0x1801339bb  mov     [rsp+568h+var_120], rcx
0x1801339c3  mov     r8d, 5
0x1801339c9  lea     rdx, [rsp+568h+var_A8]
0x1801339d1  mov     rcx, [rcx]
0x1801339d4  mov     rax, [rax]
0x1801339d7  call    cs:__guard_dispatch_icall_fptr
0x1801339dd  mov     [rsp+568h+var_524], eax
0x1801339e1  test    eax, eax
0x1801339e3  jz      loc_180133DF1
0x1801339e9  cmp     eax, 0FFFFFFFFh
0x1801339ec  jz      loc_1801343F3
0x1801339f2  mov     [rsp+568h+var_51C], 0
0x1801339fa  mov     eax, [rsp+568h+var_51C]
0x1801339fe  cmp     eax, [rsp+568h+var_524]
0x180133a02  jnb     loc_180133DDC
0x180133a08  lea     rdi, [rax+rax*2]
0x180133a0c  mov     ecx, [rsp+rdi*8+568h+var_A8]
0x180133a13  mov     [rsp+568h+var_520], ecx
0x180133a17  mov     r13, [rsp+rdi*8+568h+var_98]
0x180133a1f  mov     [rsp+568h+var_518], r13
0x180133a24  mov     eax, [r13+11Ch]
0x180133a2b  cmp     eax, 1
0x180133a2e  jnz     loc_180133B72
0x180133a34  movsxd  rbx, dword ptr [r13+118h]
0x180133a3b  mov     [rsp+568h+var_500], rbx
0x180133a40  mov     byte ptr [rbx+r14+1920h], 0
0x180133a49  inc     dword ptr [r14+19E8h]
0x180133a50  cmp     dword ptr [rsp+rdi*8+568h+Size], 0
0x180133a58  jz      loc_180133DD3
0x180133a5e  cmp     byte ptr [r14+1000h], 0
0x180133a66  jz      short loc_180133AD0
0x180133a68  test    ecx, ecx
0x180133a6a  jnz     loc_180133FC7
0x180133a70  jmp     short loc_180133A95
0x180133a72  lea     rcx, [rsp+568h+var_C0]; void *
0x180133a7a  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180133a7f  mov     r15d, [rsp+568h+var_528]
0x180133a84  mov     r12, [rsp+568h+var_510]
0x180133a89  mov     r14, r12
0x180133a8c  jmp     loc_180133DD3
0x180133a91  jmp     short loc_180133A72
0x180133a93  jmp     short loc_180133A72
0x180133a95  xorps   xmm0, xmm0
0x180133a98  movdqu  [rsp+568h+var_168], xmm0
0x180133aa1  lea     rcx, [rsp+568h+var_168]; void *
0x180133aa9  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180133aae  nop
0x180133aaf  mov     r8b, 1; bool
0x180133ab2  lea     rdx, [rsp+568h+var_168]; struct std::exception_ptr *
0x180133aba  mov     rcx, r14; this
0x180133abd  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x180133ac2  nop
0x180133ac3  lea     rcx, [rsp+568h+var_168]; void *
0x180133acb  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180133ad0  imul    rbx, [r14+1100h]
0x180133ad8  add     rbx, [r14+1900h]
0x180133adf  mov     edi, dword ptr [rsp+rdi*8+568h+Size]
0x180133ae6  lea     rcx, [r13+28h]; this
0x180133aea  mov     edx, edi; unsigned __int64
0x180133aec  call    ?Resize@FlexIBuffer@Containers@Basix@Microsoft@@QEAAX_K@Z; Microsoft::Basix::Containers::FlexIBuffer::Resize(unsigned __int64)
0x180133af1  mov     r8d, edi; Size
0x180133af4  mov     rdx, rbx; Src
0x180133af7  mov     rcx, [r13+38h]; void *
0x180133afb  call    memmove
0x180133b00  mov     [r13+78h], rdi
0x180133b04  imul    rcx, [rsp+568h+var_500], 1Ch
0x180133b0a  mov     rax, [r14+1910h]
0x180133b11  movups  xmm0, xmmword ptr [rcx+rax]
0x180133b15  movups  xmmword ptr [r13+90h], xmm0
0x180133b1d  movsd   xmm1, qword ptr [rcx+rax+10h]
0x180133b23  movsd   qword ptr [r13+0A0h], xmm1
0x180133b2c  mov     eax, [rcx+rax+18h]
0x180133b30  mov     [r13+0A8h], eax
0x180133b37  mov     dword ptr [r13+110h], 1Ch
0x180133b42  mov     rdx, qword ptr [rsp+568h+var_110+8]
0x180133b4a  cmp     rdx, [rsp+568h+var_100]
0x180133b52  jz      short loc_180133B65
0x180133b54  mov     [rdx], r13
0x180133b57  add     qword ptr [rsp+568h+var_110+8], 8
0x180133b60  jmp     loc_180133DD3
0x180133b65  lea     rcx, [rsp+568h+var_110]
0x180133b6d  jmp     loc_180133DC9
0x180133b72  cmp     eax, 2
0x180133b75  jnz     loc_180133DD3
0x180133b7b  movsxd  rax, dword ptr [r13+118h]
0x180133b82  mov     byte ptr [rax+r14+1820h], 0
0x180133b8b  mov     eax, [r14+1100h]
0x180133b92  add     [r12+4Ch], eax
0x180133b97  lea     rcx, [r12+50h]
0x180133b9c  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180133ba1  lock inc dword ptr [rax]
0x180133ba4  inc     dword ptr [r14+18ECh]
0x180133bab  mov     rcx, [r13+58h]
0x180133baf  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180133bb4  mov     rax, [rax+88h]
0x180133bbb  mov     [rsp+568h+var_500], rax
0x180133bc0  mov     rcx, [r13+58h]; this
0x180133bc4  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x180133bc9  mov     rcx, rax; this
0x180133bcc  call    ?Size@FlexOBuffer@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::FlexOBuffer::Size(void)
0x180133bd1  sub     rax, [rsp+568h+var_500]
0x180133bd6  mov     qword ptr [rsp+568h+var_140], rax
0x180133bde  mov     ecx, dword ptr [rsp+rdi*8+568h+Size]
0x180133be5  cmp     rcx, rax
0x180133be8  jz      loc_180133CD7
0x180133bee  xorps   xmm0, xmm0
0x180133bf1  movups  [rsp+568h+var_168], xmm0
0x180133bf9  lea     rcx, [rsp+568h+var_168]
0x180133c01  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180133c06  nop
0x180133c07  mov     rax, qword ptr [rsp+568h+var_168]
0x180133c0f  test    rax, rax
0x180133c12  jz      short loc_180133C91
0x180133c14  cmp     byte ptr [rax+80h], 0
0x180133c1b  jz      short loc_180133C91
0x180133c1d  mov     ebx, dword ptr [rsp+rdi*8+568h+Size]
0x180133c24  xorps   xmm0, xmm0
0x180133c27  movups  [rsp+568h+var_4C8], xmm0
0x180133c2f  xorps   xmm1, xmm1
0x180133c32  movdqu  [rsp+568h+var_4B8], xmm1
0x180133c3b  mov     r8d, 4Ch ; 'L'
0x180133c41  lea     rdx, aDraincompletio; "_DrainCompletionQueue() incomplete writ"...
0x180133c48  lea     rcx, [rsp+568h+var_4C8]
0x180133c50  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180133c55  nop
0x180133c56  mov     rax, qword ptr [rsp+568h+var_140]
0x180133c5e  mov     [rsp+568h+var_548], rax
0x180133c63  mov     r9d, ebx
0x180133c66  lea     r8, [rsp+568h+var_4C8]
0x180133c6e  lea     rdx, aNanoDct; "NANO_DCT"
0x180133c75  lea     rcx, [rsp+568h+var_168]
0x180133c7d  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@I_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@I_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,unsigned __int64)
0x180133c82  nop
0x180133c83  lea     rcx, [rsp+568h+var_4C8]
0x180133c8b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180133c90  nop
0x180133c91  mov     rbx, qword ptr [rsp+568h+var_168+8]
0x180133c99  test    rbx, rbx
0x180133c9c  jz      short loc_180133CD7
0x180133c9e  or      eax, 0FFFFFFFFh
0x180133ca1  lock xadd [rbx+8], eax
0x180133ca6  cmp     eax, 1
0x180133ca9  jnz     short loc_180133CD7
0x180133cab  mov     rax, [rbx]
0x180133cae  mov     rcx, rbx
0x180133cb1  mov     rax, [rax]
0x180133cb4  call    cs:__guard_dispatch_icall_fptr
0x180133cba  or      eax, 0FFFFFFFFh
0x180133cbd  lock xadd [rbx+0Ch], eax
0x180133cc2  cmp     eax, 1
0x180133cc5  jnz     short loc_180133CD7
0x180133cc7  mov     rax, [rbx]
0x180133cca  mov     rcx, rbx
0x180133ccd  mov     rax, [rax+8]
0x180133cd1  call    cs:__guard_dispatch_icall_fptr
0x180133cd7  mov     rcx, [r13+58h]
0x180133cdb  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180133ce0  mov     ecx, dword ptr [rsp+rdi*8+568h+Size]
0x180133ce7  add     rcx, [rsp+568h+var_500]
0x180133cec  mov     [rax+88h], rcx
0x180133cf3  cmp     byte ptr [r14+1000h], 0
0x180133cfb  jz      loc_180133D97
0x180133d01  cmp     [rsp+568h+var_520], 0
0x180133d06  jnz     loc_180134153
0x180133d0c  cmp     dword ptr [rsp+rdi*8+568h+Size], 0
0x180133d14  jz      loc_180134153
0x180133d1a  jmp     short loc_180133D82
0x180133d1c  lea     rcx, [rsp+568h+var_E0]
0x180133d24  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180133d29  nop
0x180133d2a  mov     rbx, [rsp+568h+var_480]
0x180133d32  test    rbx, rbx
0x180133d35  jz      short loc_180133D70
0x180133d37  or      eax, 0FFFFFFFFh
0x180133d3a  lock xadd [rbx+8], eax
0x180133d3f  cmp     eax, 1
0x180133d42  jnz     short loc_180133D70
0x180133d44  mov     rax, [rbx]
0x180133d47  mov     rcx, rbx
0x180133d4a  mov     rax, [rax]
0x180133d4d  call    cs:__guard_dispatch_icall_fptr
0x180133d53  or      eax, 0FFFFFFFFh
0x180133d56  lock xadd [rbx+0Ch], eax
0x180133d5b  cmp     eax, 1
0x180133d5e  jnz     short loc_180133D70
0x180133d60  mov     rax, [rbx]
0x180133d63  mov     rcx, rbx
0x180133d66  mov     rax, [rax+8]
0x180133d6a  call    cs:__guard_dispatch_icall_fptr
0x180133d70  mov     r12, [rsp+568h+var_510]
0x180133d75  mov     r13, [rsp+568h+var_518]
0x180133d7a  mov     r15d, [rsp+568h+var_528]
0x180133d7f  mov     r14, r12
0x180133d82  lea     rdx, [r13+68h]; struct std::exception_ptr *
0x180133d86  xor     r8d, r8d; bool
0x180133d89  mov     rcx, r14; this
0x180133d8c  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x180133d91  jmp     short loc_180133DA1
0x180133d93  jmp     short loc_180133D1C
0x180133d95  jmp     short loc_180133D1C
0x180133d97  cmp     dword ptr [rsp+rdi*8+568h+Size], 0
0x180133d9f  jz      short loc_180133DD3
0x180133da1  mov     rdx, qword ptr [rsp+568h+var_F8+8]
0x180133da9  cmp     rdx, [rsp+568h+var_E8]
0x180133db1  jz      short loc_180133DC1
0x180133db3  mov     [rdx], r13
0x180133db6  add     qword ptr [rsp+568h+var_F8+8], 8
0x180133dbf  jmp     short loc_180133DD3
0x180133dc1  lea     rcx, [rsp+568h+var_F8]
0x180133dc9  lea     r8, [rsp+568h+var_518]
0x180133dce  call    ??$_Emplace_reallocate@AEBQEAVWinsockDCTIORequest@Dct@Basix@Microsoft@@@?$vector@PEAVWinsockDCTIORequest@Dct@Basix@Microsoft@@V?$allocator@PEAVWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@AEAAPEAPEAVWinsockDCTIORequest@Dct@Basix@Microsoft@@QEAPEAV2345@AEBQEAV2345@@Z; std::vector<Microsoft::Basix::Dct::WinsockDCTIORequest *>::_Emplace_reallocate<Microsoft::Basix::Dct::WinsockDCTIORequest * const &>(Microsoft::Basix::Dct::WinsockDCTIORequest * * const,Microsoft::Basix::Dct::WinsockDCTIORequest * const &)
0x180133dd3  inc     [rsp+568h+var_51C]
0x180133dd7  jmp     loc_1801339FA
0x180133ddc  mov     rax, [rsp+568h+var_478]
0x180133de4  mov     rcx, [rsp+568h+var_120]
0x180133dec  jmp     loc_1801339C3
0x180133df1  lea     rcx, [r14+10h]
0x180133df5  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180133dfa  mov     ecx, [rax]
0x180133dfc  nop
0x180133dfd  cmp     ecx, 22h ; '"'
0x180133e00  jz      short loc_180133E31
0x180133e02  cmp     byte ptr [r14+11B8h], 0
0x180133e0a  jnz     short loc_180133E31
0x180133e0c  mov     rcx, [r14+19F0h]
0x180133e13  mov     rax, [r12+1178h]
0x180133e1b  call    cs:__guard_dispatch_icall_fptr
0x180133e21  test    eax, eax
0x180133e23  jnz     loc_18013456F
0x180133e29  mov     byte ptr [r14+11B8h], 1
0x180133e31  mov     rcx, [rsp+568h+var_148]; _Mtx_t
0x180133e39  call    _Mtx_unlock
0x180133e3e  mov     rbx, qword ptr [rsp+568h+var_F8]
0x180133e46  jmp     short loc_180133E91
0x180133e48  mov     rax, [rbx]
0x180133e4b  mov     [rsp+568h+var_148], rax
0x180133e53  mov     rax, [r14]
0x180133e56  lea     rdx, [rsp+568h+var_148]
0x180133e5e  mov     rcx, r14
0x180133e61  mov     rax, [rax+0B8h]
0x180133e68  call    cs:__guard_dispatch_icall_fptr
0x180133e6e  nop
0x180133e6f  mov     rcx, [rsp+568h+var_148]
0x180133e77  test    rcx, rcx
0x180133e7a  jz      short loc_180133E8D
0x180133e7c  mov     rax, [rcx]
0x180133e7f  mov     edx, 1
0x180133e84  mov     rax, [rax]
  ... truncated ...
```
