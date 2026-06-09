# RefreshTask::DownloadXml(IStream * *)

- ea: `0x18003b068`
- end: `0x18003b2d1`
- name: `?DownloadXml@RefreshTask@@AEAAJPEAPEAUIStream@@@Z`
- size: `617`
- prototype: `HRESULT __fastcall(RefreshTask *this, IStream **ppStream)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b2d8`

## callees

- `0x180002790`
- `0x18000b178`
- `0x18000b2f4`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180017b60`
- `0x18001a0d4`
- `0x18003af80`
- `0x18003b068`
- `0x18004b898`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003b188`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003b188`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RefreshTask::DownloadXml(RefreshTask *this, IStream **ppStream)
{
  const wchar_t *v4; // rax
  __int64 v5; // r10
  const std::wstring *v6; // rax
  std::vector<unsigned char> *v7; // rax
  HRESULT StreamOnHGlobal; // ebx
  unsigned __int8 *Mylast; // rdi
  WPP_PROJECT_CONTROL_BLOCK *v10; // rcx
  IStream *p; // rax
  std::vector<unsigned char> v13; // [rsp+30h] [rbp-29h] BYREF
  std::wstring result; // [rsp+48h] [rbp-11h] BYREF
  unsigned int bytesWritten; // [rsp+68h] [rbp+Fh] BYREF
  ATL::CComPtr<IStream> spXmlStream; // [rsp+70h] [rbp+17h] BYREF
  std::vector<unsigned char> xmlBytes; // [rsp+78h] [rbp+1Fh] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  }
  memset(&xmlBytes, 0, sizeof(xmlBytes));
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&xmlBytes);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_url._Mypair._Myval2);
    WPP_SF_S(*(_QWORD *)(v5 + 16), 0x13u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids, v4);
  }
  v6 = WcmCommon::Crypto::UnprotectString(&result, &this->m_encryptedPassword);
  v7 = DownloadBytesFromURL(&v13, &this->m_url, &this->m_username, v6);
  std::vector<unsigned char>::operator=(&xmlBytes, v7);
  std::vector<unsigned char>::_Tidy((std::vector<char> *)&v13);
  std::wstring::_Tidy_deallocate(&result);
  spXmlStream.p = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 0, &spXmlStream.p);
  if ( StreamOnHGlobal < 0 )
    goto LABEL_20;
  bytesWritten = 0;
  Mylast = xmlBytes._Mypair._Myval2._Mylast;
  StreamOnHGlobal = spXmlStream.p->Write(
                      spXmlStream.p,
                      xmlBytes._Mypair._Myval2._Myfirst,
                      LODWORD(xmlBytes._Mypair._Myval2._Mylast) - LODWORD(xmlBytes._Mypair._Myval2._Myfirst),
                      &bytesWritten);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x15u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids, bytesWritten);
    v10 = WPP_GLOBAL_Control;
  }
  if ( StreamOnHGlobal < 0 )
    goto LABEL_22;
  if ( (unsigned __int8 *)bytesWritten != (unsigned __int8 *)(Mylast - xmlBytes._Mypair._Myval2._Myfirst)
    || (StreamOnHGlobal = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))spXmlStream.p->Seek)(
                            spXmlStream.p,
                            0,
                            0,
                            0),
        StreamOnHGlobal >= 0) )
  {
    p = spXmlStream.p;
    spXmlStream.p = 0;
    *ppStream = p;
    v10 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    goto LABEL_25;
  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x16u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids);
LABEL_20:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_22:
  if ( v10 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v10->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v10->Control.Logger, 0x17u, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids, StreamOnHGlobal);
LABEL_25:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spXmlStream);
  std::vector<unsigned char>::_Tidy((std::vector<char> *)&xmlBytes);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18003b068  mov     [rsp-8+arg_10], rbx
0x18003b06d  mov     [rsp-8+arg_18], rdi
0x18003b072  push    rbp
0x18003b073  push    r12
0x18003b075  push    r14
0x18003b077  lea     rbp, [rsp-47h]
0x18003b07c  sub     rsp, 0A0h
0x18003b083  mov     rax, cs:__security_cookie
0x18003b08a  xor     rax, rsp
0x18003b08d  mov     [rbp+57h+var_20], rax
0x18003b091  mov     r14, ppStream
0x18003b094  mov     rbx, this
0x18003b097  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b09e  lea     r12, WPP_1f7a12ece28b3f7df5d80b077063c1af_Traceguids
0x18003b0a5  mov     this, cs:WPP_GLOBAL_Control
0x18003b0ac  cmp     this, rax
0x18003b0af  jz      short loc_18003B0C8
0x18003b0b1  test    byte ptr [this+1Ch], 10h
0x18003b0b5  jz      short loc_18003B0C8
0x18003b0b7  mov     edx, 12h; id
0x18003b0bc  mov     r8, r12; TraceGuid
0x18003b0bf  mov     this, [this+10h]; Logger
0x18003b0c3  call    WPP_SF_
0x18003b0c8  xorps   xmm0, xmm0
0x18003b0cb  xor     eax, eax
0x18003b0cd  movups  xmmword ptr [rbp+57h+xmlBytes._Mypair._Myval2._Myfirst], xmm0
0x18003b0d1  mov     [rbp+57h+xmlBytes._Mypair._Myval2._Myend], rax
0x18003b0d5  lea     this, [rbp+57h+xmlBytes]; this
0x18003b0d9  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18003b0de  nop
0x18003b0df  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b0e6  lea     rdi, WPP_GLOBAL_Control
0x18003b0ed  cmp     r10, rdi
0x18003b0f0  jz      short loc_18003B115
0x18003b0f2  test    byte ptr [r10+1Ch], 10h
0x18003b0f7  jz      short loc_18003B115
0x18003b0f9  mov     this, rbx; this
0x18003b0fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003b101  mov     edx, 13h; id
0x18003b106  mov     r9, rax; _a1
0x18003b109  mov     r8, r12; TraceGuid
0x18003b10c  mov     this, [r10+10h]; Logger
0x18003b110  call    WPP_SF_S
0x18003b115  lea     ppStream, [rbx+40h]; CipherText
0x18003b119  lea     this, [rbp+57h+result]; result
0x18003b11d  call    ?UnprotectString@Crypto@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; WcmCommon::Crypto::UnprotectString(std::vector<uchar> const &)
0x18003b122  nop
0x18003b123  lea     r8, [rbx+20h]; Username
0x18003b127  mov     r9, rax; Password
0x18003b12a  mov     ppStream, rbx; Url
0x18003b12d  lea     this, [rbp+57h+var_80]; result
0x18003b131  call    ?DownloadBytesFromURL@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@00@Z; DownloadBytesFromURL(std::wstring const &,std::wstring const &,std::wstring const &)
0x18003b136  mov     ppStream, rax; _Right
0x18003b139  lea     this, [rbp+57h+xmlBytes]; this
0x18003b13d  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18003b142  lea     this, [rbp+57h+var_80]; this
0x18003b146  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003b14b  nop
0x18003b14c  lea     this, [rbp+57h+result]; this
0x18003b150  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b155  mov     [rbp+57h+spXmlStream.p], 0
0x18003b15d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b164  cmp     this, rdi
0x18003b167  jz      short loc_18003B180
0x18003b169  test    byte ptr [this+1Ch], 10h
0x18003b16d  jz      short loc_18003B180
0x18003b16f  mov     edx, 14h; id
0x18003b174  mov     r8, r12; TraceGuid
0x18003b177  mov     this, [this+10h]; Logger
0x18003b17b  call    WPP_SF_
0x18003b180  lea     r8, [rbp+57h+spXmlStream]; ppstm
0x18003b184  xor     edx, edx; fDeleteOnRelease
0x18003b186  xor     ecx, ecx; hGlobal
0x18003b188  call    cs:__imp_CreateStreamOnHGlobal
0x18003b18e  mov     ebx, eax
0x18003b190  test    eax, eax
0x18003b192  js      loc_18003B251
0x18003b198  mov     [rbp+57h+bytesWritten], 0
0x18003b19f  mov     this, [rbp+57h+spXmlStream.p]
0x18003b1a3  mov     rdi, [rbp+57h+xmlBytes._Mypair._Myval2._Mylast]
0x18003b1a7  mov     rax, [this]
0x18003b1aa  mov     r8d, edi
0x18003b1ad  sub     r8d, dword ptr [rbp+57h+xmlBytes._Mypair._Myval2._Myfirst]
0x18003b1b1  lea     r9, [rbp+57h+bytesWritten]
0x18003b1b5  mov     ppStream, [rbp+57h+xmlBytes._Mypair._Myval2._Myfirst]
0x18003b1b9  mov     rax, [rax+20h]
0x18003b1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1c2  mov     ebx, eax
0x18003b1c4  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b1cb  lea     rax, WPP_GLOBAL_Control
0x18003b1d2  cmp     this, rax
0x18003b1d5  jz      short loc_18003B1F9
0x18003b1d7  test    byte ptr [this+1Ch], 10h
0x18003b1db  jz      short loc_18003B1F9
0x18003b1dd  mov     edx, 15h; id
0x18003b1e2  mov     r9d, [rbp+57h+bytesWritten]; _a1
0x18003b1e6  mov     r8, r12; TraceGuid
0x18003b1e9  mov     this, [this+10h]; Logger
0x18003b1ed  call    WPP_SF_d
0x18003b1f2  mov     this, cs:WPP_GLOBAL_Control
0x18003b1f9  test    ebx, ebx
0x18003b1fb  js      short loc_18003B270
0x18003b1fd  sub     rdi, [rbp+57h+xmlBytes._Mypair._Myval2._Myfirst]
0x18003b201  mov     eax, [rbp+57h+bytesWritten]
0x18003b204  cmp     rax, rdi
0x18003b207  jnz     short loc_18003B25A
0x18003b209  mov     this, [rbp+57h+spXmlStream.p]
0x18003b20d  xor     edx, edx
0x18003b20f  mov     rax, [this]
0x18003b212  xor     r9d, r9d
0x18003b215  xor     r8d, r8d
0x18003b218  mov     rax, [rax+28h]
0x18003b21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b221  mov     ebx, eax
0x18003b223  test    eax, eax
0x18003b225  jns     short loc_18003B25A
0x18003b227  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003b22e  lea     rdi, WPP_GLOBAL_Control
0x18003b235  cmp     this, rdi
0x18003b238  jz      short loc_18003B297
0x18003b23a  test    byte ptr [this+1Ch], 2
0x18003b23e  jz      short loc_18003B277
0x18003b240  mov     edx, 16h; id
0x18003b245  mov     r8, r12; TraceGuid
0x18003b248  mov     this, [this+10h]; Logger
0x18003b24c  call    WPP_SF_
0x18003b251  mov     this, cs:WPP_GLOBAL_Control
0x18003b258  jmp     short loc_18003B277
0x18003b25a  mov     rax, [rbp+57h+spXmlStream.p]
0x18003b25e  mov     [rbp+57h+spXmlStream.p], 0
0x18003b266  mov     [r14], rax
0x18003b269  mov     this, cs:WPP_GLOBAL_Control
0x18003b270  lea     rdi, WPP_GLOBAL_Control
0x18003b277  cmp     this, rdi; __annotation("TMF:",
0x18003b27a  jz      short loc_18003B297
0x18003b27c  test    byte ptr [this+1Ch], 10h
0x18003b280  jz      short loc_18003B297
0x18003b282  mov     edx, 17h; id
0x18003b287  mov     r9d, ebx; _a1
0x18003b28a  mov     r8, r12; TraceGuid
0x18003b28d  mov     this, [this+10h]; Logger
0x18003b291  call    WPP_SF_d
0x18003b296  nop
0x18003b297  lea     this, [rbp+57h+spXmlStream]; this
0x18003b29b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003b2a0  nop
0x18003b2a1  lea     this, [rbp+57h+xmlBytes]; this
0x18003b2a5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003b2aa  mov     eax, ebx
0x18003b2ac  mov     this, [rbp+57h+var_20]
0x18003b2b0  xor     this, rsp; StackCookie
0x18003b2b3  call    __security_check_cookie
0x18003b2b8  lea     r11, [rsp+0B0h+var_10]
0x18003b2c0  mov     rbx, [r11+30h]
0x18003b2c4  mov     rdi, [r11+38h]
0x18003b2c8  mov     rsp, r11
0x18003b2cb  pop     r14
0x18003b2cd  pop     r12
0x18003b2cf  pop     rbp
0x18003b2d0  retn
```
