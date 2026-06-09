# Microsoft::HostGuardian::Client::HgServiceController::UnwrapKeyProtector(wchar_t * const,HgBlob * const,HgUnwrapKeyProtectorFlag,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgUnwrapKeyProtectorResultFlag *)

- ea: `0x18000e100`
- end: `0x18000e669`
- name: `?UnwrapKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXQEA_WQEAUHgBlob@@W4HgUnwrapKeyProtectorFlag@@PEAU5@333PEAW4HgUnwrapKeyProtectorResultFlag@@@Z`
- size: `1385`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, OLECHAR *, __int128 *, char, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b260`

## callees

- `0x180001770`
- `0x180003d0c`
- `0x180004274`
- `0x1800077a0`
- `0x180007878`
- `0x180008760`
- `0x18000b4c4`
- `0x18000bfc0`
- `0x18000c45c`
- `0x18000c7f0`
- `0x18000cfcc`
- `0x18000e0b0`
- `0x18000e100`
- `0x180011600`
- `0x180011e90`
- `0x180014318`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000e1c0`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e1c0`

## string_xrefs

- `0x18000e452`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000e657`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000e231`: `Trying cached encrypted results as the plugin failed to unwrap the key protector.`
- `0x18000e3a2`: `Returning cached encrypted payload from the cache.`
- `0x18000e443`: `Failed to unwrap the key protector & retrieve any cached results: %0x08`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServiceController::UnwrapKeyProtector(
        RTL_SRWLOCK *a1,
        OLECHAR *a2,
        __int128 *a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  char v13; // si
  UINT v14; // r12d
  __int64 v15; // rcx
  unsigned int v16; // r15d
  __int64 v17; // rdi
  __int64 v18; // r8
  char v19; // bl
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r8
  wil::details::in1diag3 *v27; // rcx
  _QWORD *v28; // rbx
  __int64 v29; // rsi
  _QWORD *v30; // r15
  _QWORD *v31; // r12
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // r8
  int v39; // [rsp+20h] [rbp-E0h]
  char *v40; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h]
  __int128 v45; // [rsp+70h] [rbp-90h] BYREF
  __int128 v46; // [rsp+80h] [rbp-80h] BYREF
  __int128 v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-20h]
  __int128 v55; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v56; // [rsp+F8h] [rbp-8h]
  __int128 v57; // [rsp+100h] [rbp+0h] BYREF
  __int64 v58; // [rsp+110h] [rbp+10h]
  __int128 v59; // [rsp+118h] [rbp+18h] BYREF
  __int64 v60; // [rsp+128h] [rbp+28h]
  _DWORD *v61; // [rsp+130h] [rbp+30h]
  _QWORD v62[5]; // [rsp+138h] [rbp+38h] BYREF
  char v63; // [rsp+160h] [rbp+60h]
  int v64[4]; // [rsp+168h] [rbp+68h] BYREF
  __int128 v65; // [rsp+178h] [rbp+78h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v41 = (__int64)a3;
  v48 = a5;
  v49 = a6;
  v50 = a7;
  v51 = a8;
  v61 = a9;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v52 = 0;
  v62[0] = &v45;
  v62[1] = &v46;
  v62[2] = &v47;
  v62[3] = &v52;
  v62[4] = a1;
  v13 = 1;
  v63 = 1;
  v14 = SysStringLen(a2);
  v43 = *a3;
  v16 = Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector(a1, &v43, &v45, &v46, &v47, &v52);
  v17 = -1;
  if ( v16 == -2147012889 && v14 && (a4 & 1) != 0 )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v15,
        ServiceDebugWarning,
        L"Trying cached encrypted results as the plugin failed to unwrap the key protector.",
        2147954407LL);
    v59 = 0;
    v60 = 0;
    v57 = 0;
    v58 = 0;
    v55 = 0;
    v56 = 0;
    v53 = 0;
    v54 = 0;
    v43 = 0;
    v44 = 0;
    *(_OWORD *)v64 = 0;
    v65 = 0;
    v18 = -1;
    do
      ++v18;
    while ( a2[v18] );
    std::wstring::_Construct<1,wchar_t const *>(v64, a2, v18);
    v19 = Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get(
            a1 + 20,
            v64,
            (__int64)&v59,
            (__int64)&v57,
            (__int64)&v55,
            (__int64)&v53,
            (__int64)&v43);
    std::wstring::~wstring(v64);
    if ( v19 )
    {
      std::vector<unsigned char>::operator=(&v43, &v59);
      v41 = (unsigned int)(DWORD2(v57) - v57);
      v42 = v57;
      Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v57, &v41, v20, v48);
      v41 = (unsigned int)(DWORD2(v55) - v55);
      v42 = v55;
      Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v55, &v41, v21, v49);
      v41 = (unsigned int)(DWORD2(v53) - v53);
      v42 = v53;
      Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v53, &v41, v22, v50);
      v41 = (unsigned int)(DWORD2(v43) - v43);
      v42 = v43;
      Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v43, &v41, v23, v51);
      *v61 = 1;
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
      {
        *(_QWORD *)&v65 = L"Returning cached encrypted payload from the cache.";
        *((_QWORD *)&v65 + 1) = 102;
        McGenEventWrite_EventWriteTransfer(v24, ServiceDebugInformational, v25, 2, v64);
      }
      std::vector<unsigned char>::~vector<unsigned char>(&v43);
      std::vector<unsigned char>::~vector<unsigned char>(&v53);
      std::vector<unsigned char>::~vector<unsigned char>(&v55);
      std::vector<unsigned char>::~vector<unsigned char>(&v57);
      std::vector<unsigned char>::~vector<unsigned char>(&v59);
      return wil::details::lambda_call__lambda_1bd5765b4407f89a7ea1f37faccf3a54___::_lambda_call__lambda_1bd5765b4407f89a7ea1f37faccf3a54___(v62);
    }
    std::vector<unsigned char>::~vector<unsigned char>(&v43);
    std::vector<unsigned char>::~vector<unsigned char>(&v53);
    std::vector<unsigned char>::~vector<unsigned char>(&v55);
    std::vector<unsigned char>::~vector<unsigned char>(&v57);
    std::vector<unsigned char>::~vector<unsigned char>(&v59);
  }
  LODWORD(v40) = v16;
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x109,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
    (const char *)v16,
    (int)"Failed to unwrap the key protector & retrieve any cached results: %0x08",
    v40);
  v26 = 0;
  if ( (_DWORD)v45
    && *((_QWORD *)&v45 + 1)
    && (_DWORD)v46
    && *((_QWORD *)&v46 + 1)
    && (_DWORD)v47
    && *((_QWORD *)&v47 + 1)
    && (_DWORD)v52
    && *((_QWORD *)&v52 + 1) )
  {
    v13 = 0;
  }
  v27 = retaddr;
  if ( v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x8000FFFFLL,
      v39);
  if ( v14 )
  {
    v28 = (_QWORD *)std::vector<unsigned char>::vector<unsigned char>(
                      &v43,
                      *((_QWORD *)&v52 + 1),
                      *((_QWORD *)&v52 + 1) + (unsigned int)v52);
    v29 = std::vector<unsigned char>::vector<unsigned char>(
            &v53,
            *((_QWORD *)&v47 + 1),
            *((_QWORD *)&v47 + 1) + (unsigned int)v47);
    v30 = (_QWORD *)std::vector<unsigned char>::vector<unsigned char>(
                      &v55,
                      *((_QWORD *)&v46 + 1),
                      *((_QWORD *)&v46 + 1) + (unsigned int)v46);
    v31 = (_QWORD *)std::vector<unsigned char>::vector<unsigned char>(
                      &v57,
                      *((_QWORD *)&v45 + 1),
                      *((_QWORD *)&v45 + 1) + (unsigned int)v45);
    v41 = std::vector<unsigned char>::vector<unsigned char>(
            &v59,
            *(_QWORD *)(v41 + 8),
            *(_QWORD *)(v41 + 8) + *(unsigned int *)v41);
    *(_OWORD *)v64 = 0;
    v65 = 0;
    do
      ++v17;
    while ( a2[v17] );
    std::wstring::_Construct<1,wchar_t const *>(v64, a2, v17);
    Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set(a1 + 20, (__int64)v64, v41, v31, v30, v29, v28);
    std::wstring::~wstring(v64);
    std::vector<unsigned char>::~vector<unsigned char>(&v59);
    std::vector<unsigned char>::~vector<unsigned char>(&v57);
    std::vector<unsigned char>::~vector<unsigned char>(&v55);
    std::vector<unsigned char>::~vector<unsigned char>(&v53);
    std::vector<unsigned char>::~vector<unsigned char>(&v43);
  }
  v43 = v45;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v27, &v43, v26, v48);
  v43 = v46;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v32, &v43, v33, v49);
  v43 = v47;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v34, &v43, v35, v50);
  v43 = v52;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v36, &v43, v37, v51);
  return wil::details::lambda_call__lambda_1bd5765b4407f89a7ea1f37faccf3a54___::_lambda_call__lambda_1bd5765b4407f89a7ea1f37faccf3a54___(v62);
}

```

## disassembly

```asm
0x18000e100  mov     [rsp-8+arg_18], rbx
0x18000e105  push    rbp
0x18000e106  push    rsi
0x18000e107  push    rdi
0x18000e108  push    r12
0x18000e10a  push    r13
0x18000e10c  push    r14
0x18000e10e  push    r15
0x18000e110  lea     rbp, [rsp-90h]
0x18000e118  sub     rsp, 190h
0x18000e11f  mov     rax, cs:__security_cookie
0x18000e126  xor     rax, rsp
0x18000e129  mov     [rbp+0C0h+var_38], rax
0x18000e130  mov     ebx, r9d
0x18000e133  mov     rdi, r8
0x18000e136  mov     [rsp+1C0h+var_180], r8
0x18000e13b  mov     r14, rdx
0x18000e13e  mov     r13, rcx
0x18000e141  mov     rax, [rbp+0C0h+arg_20]
0x18000e148  mov     [rbp+0C0h+var_120], rax
0x18000e14c  mov     rax, [rbp+0C0h+arg_28]
0x18000e153  mov     [rbp+0C0h+var_118], rax
0x18000e157  mov     rax, [rbp+0C0h+arg_30]
0x18000e15e  mov     [rbp+0C0h+var_110], rax
0x18000e162  mov     rax, [rbp+0C0h+arg_38]
0x18000e169  mov     [rbp+0C0h+var_108], rax
0x18000e16d  mov     rax, [rbp+0C0h+arg_40]
0x18000e174  mov     [rbp+0C0h+var_90], rax
0x18000e178  xorps   xmm0, xmm0
0x18000e17b  movups  [rsp+1C0h+var_150], xmm0
0x18000e180  xorps   xmm1, xmm1
0x18000e183  movups  [rbp+0C0h+var_140], xmm1
0x18000e187  movups  [rbp+0C0h+var_130], xmm0
0x18000e18b  movups  [rbp+0C0h+var_100], xmm1
0x18000e18f  lea     rax, [rsp+1C0h+var_150]
0x18000e194  mov     [rbp+0C0h+var_88], rax
0x18000e198  lea     rax, [rbp+0C0h+var_140]
0x18000e19c  mov     [rbp+0C0h+var_80], rax
0x18000e1a0  lea     rax, [rbp+0C0h+var_130]
0x18000e1a4  mov     [rbp+0C0h+var_78], rax
0x18000e1a8  lea     rax, [rbp+0C0h+var_100]
0x18000e1ac  mov     [rbp+0C0h+var_70], rax
0x18000e1b0  mov     [rbp+0C0h+var_68], rcx
0x18000e1b4  mov     esi, 1
0x18000e1b9  mov     [rbp+0C0h+var_60], sil
0x18000e1bd  mov     rcx, rdx; pbstr
0x18000e1c0  call    cs:__imp_SysStringLen
0x18000e1c6  mov     r12d, eax
0x18000e1c9  movups  xmm0, xmmword ptr [rdi]
0x18000e1cc  movdqu  [rsp+1C0h+var_170], xmm0
0x18000e1d2  lea     rax, [rbp+0C0h+var_100]
0x18000e1d6  mov     [rsp+1C0h+var_198], rax
0x18000e1db  lea     rax, [rbp+0C0h+var_130]
0x18000e1df  mov     [rsp+1C0h+var_1A0], rax
0x18000e1e4  lea     r9, [rbp+0C0h+var_140]
0x18000e1e8  lea     r8, [rsp+1C0h+var_150]
0x18000e1ed  lea     rdx, [rsp+1C0h+var_170]
0x18000e1f2  mov     rcx, r13
0x18000e1f5  call    ?UnwrapKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@PEAU5@111@Z; Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector(HgBlob,HgBlob *,HgBlob *,HgBlob *,HgBlob *)
0x18000e1fa  mov     r15d, eax
0x18000e1fd  xor     eax, eax
0x18000e1ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e203  cmp     r15d, 80072EE7h
0x18000e20a  jnz     loc_18000E437
0x18000e210  test    r12d, r12d
0x18000e213  jz      loc_18000E437
0x18000e219  test    sil, bl
0x18000e21c  jz      loc_18000E437
0x18000e222  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 4
0x18000e229  jz      short loc_18000E246
0x18000e22b  mov     r9d, 80072EE7h
0x18000e231  lea     r8, aTryingCachedEn; "Trying cached encrypted results as the "...
0x18000e238  lea     rdx, ServiceDebugWarning
0x18000e23f  call    McTemplateU0zq_EventWriteTransfer
0x18000e244  xor     eax, eax
0x18000e246  xorps   xmm0, xmm0
0x18000e249  movdqu  [rbp+0C0h+var_A8], xmm0
0x18000e24e  mov     [rbp+0C0h+var_98], rax
0x18000e252  movdqu  [rbp+0C0h+var_C0], xmm0
0x18000e257  mov     [rbp+0C0h+var_B0], rax
0x18000e25b  movdqu  [rbp+0C0h+var_D8], xmm0
0x18000e260  mov     [rbp+0C0h+var_C8], rax
0x18000e264  movdqu  [rbp+0C0h+var_F0], xmm0
0x18000e269  mov     [rbp+0C0h+var_E0], rax
0x18000e26d  movdqu  [rsp+1C0h+var_170], xmm0
0x18000e273  mov     [rsp+1C0h+var_160], rax
0x18000e278  movups  xmmword ptr [rbp+0C0h+var_58], xmm0
0x18000e27c  xorps   xmm1, xmm1
0x18000e27f  movdqu  [rbp+0C0h+var_48], xmm1
0x18000e284  mov     r8, rdi
0x18000e287  inc     r8
0x18000e28a  cmp     [r14+r8*2], ax
0x18000e28f  jnz     short loc_18000E287
0x18000e291  mov     rdx, r14
0x18000e294  lea     rcx, [rbp+0C0h+var_58]
0x18000e298  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000e29d  nop
0x18000e29e  lea     rcx, [r13+0A0h]
0x18000e2a5  lea     rax, [rsp+1C0h+var_170]
0x18000e2aa  mov     [rsp+1C0h+var_190], rax
0x18000e2af  lea     rax, [rbp+0C0h+var_F0]
0x18000e2b3  mov     [rsp+1C0h+var_198], rax
0x18000e2b8  lea     rax, [rbp+0C0h+var_D8]
0x18000e2bc  mov     [rsp+1C0h+var_1A0], rax
0x18000e2c1  lea     r9, [rbp+0C0h+var_C0]
0x18000e2c5  lea     r8, [rbp+0C0h+var_A8]
0x18000e2c9  lea     rdx, [rbp+0C0h+var_58]
0x18000e2cd  call    ?Get@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@6@1111@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Get(std::wstring const &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &)
0x18000e2d2  mov     bl, al
0x18000e2d4  lea     rcx, [rbp+0C0h+var_58]
0x18000e2d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2dd  test    bl, bl
0x18000e2df  jz      loc_18000E405
0x18000e2e5  lea     rdx, [rbp+0C0h+var_A8]
0x18000e2e9  lea     rcx, [rsp+1C0h+var_170]
0x18000e2ee  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x18000e2f3  mov     eax, dword ptr [rbp+0C0h+var_C0+8]
0x18000e2f6  mov     rcx, qword ptr [rbp+0C0h+var_C0]
0x18000e2fa  sub     eax, ecx
0x18000e2fc  xor     edx, edx
0x18000e2fe  mov     dword ptr [rsp+1C0h+var_180], eax
0x18000e302  mov     dword ptr [rsp+1C0h+var_180+4], edx
0x18000e306  mov     [rsp+1C0h+var_178], rcx
0x18000e30b  mov     r9, [rbp+0C0h+var_120]
0x18000e30f  lea     rdx, [rsp+1C0h+var_180]
0x18000e314  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000e319  mov     eax, dword ptr [rbp+0C0h+var_D8+8]
0x18000e31c  mov     rcx, qword ptr [rbp+0C0h+var_D8]
0x18000e320  sub     eax, ecx
0x18000e322  xor     edx, edx
0x18000e324  mov     dword ptr [rsp+1C0h+var_180], eax
0x18000e328  mov     dword ptr [rsp+1C0h+var_180+4], edx
0x18000e32c  mov     [rsp+1C0h+var_178], rcx
0x18000e331  mov     r9, [rbp+0C0h+var_118]
0x18000e335  lea     rdx, [rsp+1C0h+var_180]
0x18000e33a  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000e33f  mov     eax, dword ptr [rbp+0C0h+var_F0+8]
0x18000e342  mov     rcx, qword ptr [rbp+0C0h+var_F0]
0x18000e346  sub     eax, ecx
0x18000e348  xor     edx, edx
0x18000e34a  mov     dword ptr [rsp+1C0h+var_180], eax
0x18000e34e  mov     dword ptr [rsp+1C0h+var_180+4], edx
0x18000e352  mov     [rsp+1C0h+var_178], rcx
0x18000e357  mov     r9, [rbp+0C0h+var_110]
0x18000e35b  lea     rdx, [rsp+1C0h+var_180]
0x18000e360  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000e365  mov     eax, dword ptr [rsp+1C0h+var_170+8]
0x18000e369  mov     rcx, qword ptr [rsp+1C0h+var_170]
0x18000e36e  sub     eax, ecx
0x18000e370  xor     edx, edx
0x18000e372  mov     dword ptr [rsp+1C0h+var_180], eax
0x18000e376  mov     dword ptr [rsp+1C0h+var_180+4], edx
0x18000e37a  mov     [rsp+1C0h+var_178], rcx
0x18000e37f  mov     r9, [rbp+0C0h+var_108]
0x18000e383  lea     rdx, [rsp+1C0h+var_180]
0x18000e388  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000e38d  mov     rax, [rbp+0C0h+var_90]
0x18000e391  mov     [rax], esi
0x18000e393  mov     r9d, 2
0x18000e399  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x18000e3a0  jz      short loc_18000E3CE
0x18000e3a2  lea     rax, aReturningCache; "Returning cached encrypted payload from"...
0x18000e3a9  mov     qword ptr [rbp+0C0h+var_48], rax
0x18000e3ad  mov     qword ptr [rbp+0C0h+var_48+8], 66h ; 'f'
0x18000e3b8  lea     rax, [rbp+0C0h+var_58]
0x18000e3bc  mov     [rsp+1C0h+var_1A0], rax
0x18000e3c1  lea     rdx, ServiceDebugInformational
0x18000e3c8  call    McGenEventWrite_EventWriteTransfer
0x18000e3cd  nop
0x18000e3ce  lea     rcx, [rsp+1C0h+var_170]
0x18000e3d3  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e3d8  nop
0x18000e3d9  lea     rcx, [rbp+0C0h+var_F0]
0x18000e3dd  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e3e2  nop
0x18000e3e3  lea     rcx, [rbp+0C0h+var_D8]
0x18000e3e7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e3ec  nop
0x18000e3ed  lea     rcx, [rbp+0C0h+var_C0]
0x18000e3f1  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e3f6  nop
0x18000e3f7  lea     rcx, [rbp+0C0h+var_A8]
0x18000e3fb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e400  jmp     loc_18000E61E
0x18000e405  lea     rcx, [rsp+1C0h+var_170]
0x18000e40a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e40f  nop
0x18000e410  lea     rcx, [rbp+0C0h+var_F0]
0x18000e414  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e419  nop
0x18000e41a  lea     rcx, [rbp+0C0h+var_D8]
0x18000e41e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e423  nop
0x18000e424  lea     rcx, [rbp+0C0h+var_C0]
0x18000e428  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e42d  nop
0x18000e42e  lea     rcx, [rbp+0C0h+var_A8]
0x18000e432  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e437  mov     rcx, [rbp+0C8h]; this
0x18000e43e  mov     dword ptr [rsp+1C0h+var_198], r15d; char *
0x18000e443  lea     rax, aFailedToUnwrap; "Failed to unwrap the key protector & re"...
0x18000e44a  mov     [rsp+1C0h+var_1A0], rax; int
0x18000e44f  mov     r9d, r15d; char *
0x18000e452  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000e459  mov     edx, 109h; void *
0x18000e45e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e463  mov     rdx, qword ptr [rbp+0C0h+var_100+8]
0x18000e467  mov     eax, dword ptr [rbp+0C0h+var_100]
0x18000e46a  xor     r8d, r8d
0x18000e46d  cmp     dword ptr [rsp+1C0h+var_150], r8d
0x18000e472  jbe     short loc_18000E49F
0x18000e474  cmp     qword ptr [rsp+1C0h+var_150+8], r8
0x18000e479  jz      short loc_18000E49F
0x18000e47b  cmp     dword ptr [rbp+0C0h+var_140], r8d
0x18000e47f  jbe     short loc_18000E49F
0x18000e481  cmp     qword ptr [rbp+0C0h+var_140+8], r8
0x18000e485  jz      short loc_18000E49F
0x18000e487  cmp     dword ptr [rbp+0C0h+var_130], r8d
0x18000e48b  jbe     short loc_18000E49F
0x18000e48d  cmp     qword ptr [rbp+0C0h+var_130+8], r8
0x18000e491  jz      short loc_18000E49F
0x18000e493  test    eax, eax
0x18000e495  jz      short loc_18000E49F
0x18000e497  test    rdx, rdx
0x18000e49a  jz      short loc_18000E49F
0x18000e49c  mov     sil, r8b
0x18000e49f  mov     rcx, [rbp+0C8h]; this
0x18000e4a6  test    sil, sil
0x18000e4a9  jnz     loc_18000E651
0x18000e4af  test    r12d, r12d
0x18000e4b2  jz      loc_18000E5BC
0x18000e4b8  lea     r8, [rdx+rax]
0x18000e4bc  lea     rcx, [rsp+1C0h+var_170]
0x18000e4c1  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000e4c6  mov     rbx, rax
0x18000e4c9  mov     r8d, dword ptr [rbp+0C0h+var_130]
0x18000e4cd  mov     rdx, qword ptr [rbp+0C0h+var_130+8]
0x18000e4d1  add     r8, rdx
0x18000e4d4  lea     rcx, [rbp+0C0h+var_F0]
0x18000e4d8  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000e4dd  mov     rsi, rax
0x18000e4e0  mov     r8d, dword ptr [rbp+0C0h+var_140]
0x18000e4e4  mov     rdx, qword ptr [rbp+0C0h+var_140+8]
0x18000e4e8  add     r8, rdx
0x18000e4eb  lea     rcx, [rbp+0C0h+var_D8]
0x18000e4ef  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000e4f4  mov     r15, rax
0x18000e4f7  mov     r8d, dword ptr [rsp+1C0h+var_150]
0x18000e4fc  mov     rdx, qword ptr [rsp+1C0h+var_150+8]
0x18000e501  add     r8, rdx
0x18000e504  lea     rcx, [rbp+0C0h+var_C0]
0x18000e508  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000e50d  mov     r12, rax
0x18000e510  mov     rax, [rsp+1C0h+var_180]
0x18000e515  mov     rdx, [rax+8]
0x18000e519  mov     r8d, [rax]
0x18000e51c  add     r8, rdx
0x18000e51f  lea     rcx, [rbp+0C0h+var_A8]
0x18000e523  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18000e528  mov     [rsp+1C0h+var_180], rax
0x18000e52d  xorps   xmm0, xmm0
0x18000e530  movups  xmmword ptr [rbp+0C0h+var_58], xmm0
0x18000e534  xorps   xmm1, xmm1
0x18000e537  movdqu  [rbp+0C0h+var_48], xmm1
0x18000e53c  xor     eax, eax
0x18000e53e  inc     rdi
0x18000e541  cmp     [r14+rdi*2], ax
0x18000e546  jnz     short loc_18000E53E
0x18000e548  mov     r8, rdi
0x18000e54b  mov     rdx, r14
0x18000e54e  lea     rcx, [rbp+0C0h+var_58]
0x18000e552  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000e557  nop
0x18000e558  lea     rcx, [r13+0A0h]; int
0x18000e55f  mov     [rsp+1C0h+var_190], rbx; __int64
0x18000e564  mov     [rsp+1C0h+var_198], rsi; __int64
0x18000e569  mov     [rsp+1C0h+var_1A0], r15; __int64
0x18000e56e  mov     r9, r12
0x18000e571  mov     r8, [rsp+1C0h+var_180]
0x18000e576  lea     rdx, [rbp+0C0h+var_58]; int
0x18000e57a  call    ?Set@HgEncryptedPayloadCache@Client@HostGuardian@Microsoft@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@6@1111@Z; Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::Set(std::wstring const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> const &)
0x18000e57f  nop
0x18000e580  lea     rcx, [rbp+0C0h+var_58]
0x18000e584  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e589  nop
0x18000e58a  lea     rcx, [rbp+0C0h+var_A8]
0x18000e58e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e593  nop
0x18000e594  lea     rcx, [rbp+0C0h+var_C0]
0x18000e598  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e59d  nop
0x18000e59e  lea     rcx, [rbp+0C0h+var_D8]
0x18000e5a2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e5a7  nop
0x18000e5a8  lea     rcx, [rbp+0C0h+var_F0]
0x18000e5ac  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e5b1  nop
0x18000e5b2  lea     rcx, [rsp+1C0h+var_170]
0x18000e5b7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000e5bc  movaps  xmm0, [rsp+1C0h+var_150]
  ... truncated ...
```
