# Win32_BaseService::GetServiceStatus(CInstance const &,CHString &,ulong &,bool &,bool &)

- ea: `0x180098390`
- end: `0x1800986ff`
- name: `?GetServiceStatus@Win32_BaseService@@IEAAJAEBVCInstance@@AEAVCHString@@AEAKAEA_N3@Z`
- size: `879`
- prototype: `__int64 __fastcall(Win32_BaseService *__hidden this, const struct CInstance *, struct CHString *, unsigned int *, bool *, bool *)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180095808`
- `0x180097054`
- `0x1800975d8`
- `0x180097934`
- `0x180097b04`
- `0x180097cbc`
- `0x180097e04`
- `0x180097fb4`

## callees

- `0x180014c58`
- `0x180015c80`
- `0x18003d7b0`
- `0x18005ca14`
- `0x180098390`
- `0x1800fc980`

## import_xrefs

- `framedynos!??0CHString@@QEAA@XZ` at `0x1800983cb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180098515`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800983cb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180098515`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800983f8`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180098532`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18009854f`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800983f8`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180098532`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x18009854f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985b8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985d8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985f8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180098615`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180098632`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009864f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009866c`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985b8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985d8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800985f8`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180098615`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180098632`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009864f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18009866c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800983e8`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800984f3`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800983e8`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800984f3`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800984d5`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800984d5`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800985a3`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800985a3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800983dd`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180098411`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180098434`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800983dd`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180098411`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180098434`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180098471`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180098498`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180098471`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180098498`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18009845f`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180098486`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18009845f`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180098486`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x18009844a`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x18009844a`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180098503`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x180098503`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x18009856b`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x180098587`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x18009856b`
- `framedynos!?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z` at `0x180098587`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984a3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984ae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984b9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984c4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180098687`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986ad`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986c9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986d4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984a3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984ae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984b9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800984c4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180098687`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986ad`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986c9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800986d4`

## string_xrefs

- `0x1800983d2`: `__RELPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Win32_BaseService::GetServiceStatus(
        Win32_BaseService *this,
        const struct CInstance *a2,
        struct CHString *a3,
        unsigned int *a4,
        bool *a5,
        bool *a6)
{
  const unsigned __int16 *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  struct MethodContext *MethodContext; // rbx
  const unsigned __int16 *v15; // rax
  CInstance *v16; // rax
  CInstance *v17; // rax
  CInstance *v18; // rax
  CInstance *v19; // rax
  unsigned int v20; // ebx
  _BYTE v22[8]; // [rsp+20h] [rbp-59h] BYREF
  struct CInstance *v23; // [rsp+28h] [rbp-51h] BYREF
  DWORD nSize; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v25[8]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v26[8]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v27[8]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v29[8]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v30[8]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v32[8]; // [rsp+70h] [rbp-9h] BYREF
  WCHAR Buffer[16]; // [rsp+78h] [rbp-1h] BYREF

  CHString::CHString((CHString *)v25);
  CHString::CHString((CHString *)v29, L"__RELPATH");
  v9 = (const unsigned __int16 *)CHString::operator unsigned short const *(v29);
  if ( CInstance::GetCHString(a2, v9, (struct CHString *)v25) )
  {
    CHString::CHString((CHString *)v28, L"root\\cimv2");
    nSize = 16;
    ProviderGetComputerName(Buffer, &nSize);
    CHString::CHString((CHString *)v27, Buffer);
    v10 = operator+(v32, L"\\\\", v27);
    v11 = operator+(v31, v10, L"\\");
    v12 = operator+(v30, v11, v28);
    v13 = operator+(v22, v12, L":");
    operator+(v26, v13, v25);
    CHString::~CHString((CHString *)v22);
    CHString::~CHString((CHString *)v30);
    CHString::~CHString((CHString *)v31);
    CHString::~CHString((CHString *)v32);
    v23 = 0;
    MethodContext = CInstance::GetMethodContext(a2);
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v23);
    v23 = 0;
    v15 = (const unsigned __int16 *)CHString::operator unsigned short const *(v26);
    if ( (int)CWbemProviderGlue::GetInstanceByPath(v15, &v23, MethodContext) < 0 )
    {
      v20 = -2147217404;
    }
    else
    {
      CHString::CHString((CHString *)v22);
      v16 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v23);
      CInstance::GetCHString(v16, L"Name", a3);
      v17 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v23);
      CInstance::GetCHString(v17, L"State", (struct CHString *)v22);
      v18 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v23);
      CInstance::Getbool(v18, L"AcceptPause", a5);
      v19 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v23);
      CInstance::Getbool(v19, L"AcceptStop", a6);
      if ( !v23 )
        _com_issue_error(-2147467261);
      v20 = 0;
      CInstance::Release(v23);
      v23 = 0;
      if ( CHString::CompareNoCase((CHString *)v22, L"Stopped") )
      {
        if ( CHString::CompareNoCase((CHString *)v22, L"Start Pending") )
        {
          if ( CHString::CompareNoCase((CHString *)v22, L"Stop Pending") )
          {
            if ( CHString::CompareNoCase((CHString *)v22, L"Running") )
            {
              if ( CHString::CompareNoCase((CHString *)v22, L"Continue Pending") )
              {
                if ( CHString::CompareNoCase((CHString *)v22, L"Pause Pending") )
                {
                  if ( CHString::CompareNoCase((CHString *)v22, L"Paused") )
                    v20 = -2147217404;
                  else
                    *a4 = 7;
                }
                else
                {
                  *a4 = 6;
                }
              }
              else
              {
                *a4 = 5;
              }
            }
            else
            {
              *a4 = 4;
            }
          }
          else
          {
            *a4 = 3;
          }
        }
        else
        {
          *a4 = 2;
        }
      }
      else
      {
        *a4 = 1;
      }
      CHString::~CHString((CHString *)v22);
    }
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v23);
    CHString::~CHString((CHString *)v26);
    CHString::~CHString((CHString *)v27);
    CHString::~CHString((CHString *)v28);
  }
  else
  {
    v20 = -2147217407;
  }
  CHString::~CHString((CHString *)v29);
  CHString::~CHString((CHString *)v25);
  return v20;
}

```

## disassembly

```asm
0x180098390  mov     [rsp-8+arg_0], rbx
0x180098395  push    rbp
0x180098396  push    rsi
0x180098397  push    rdi
0x180098398  push    r14
0x18009839a  push    r15
0x18009839c  lea     rbp, [rsp-27h]
0x1800983a1  sub     rsp, 0A0h
0x1800983a8  mov     rax, cs:__security_cookie
0x1800983af  xor     rax, rsp
0x1800983b2  mov     [rbp+47h+var_28], rax
0x1800983b6  mov     rdi, r9
0x1800983b9  mov     rsi, r8
0x1800983bc  mov     rbx, rdx
0x1800983bf  mov     r14, [rbp+47h+arg_20]
0x1800983c3  mov     r15, [rbp+47h+arg_28]
0x1800983c7  lea     rcx, [rbp+47h+var_88]
0x1800983cb  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800983d1  nop
0x1800983d2  lea     rdx, aRelpath; "__RELPATH"
0x1800983d9  lea     rcx, [rbp+47h+var_68]
0x1800983dd  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800983e3  nop
0x1800983e4  lea     rcx, [rbp+47h+var_68]
0x1800983e8  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800983ee  mov     rdx, rax
0x1800983f1  lea     r8, [rbp+47h+var_88]
0x1800983f5  mov     rcx, rbx
0x1800983f8  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800983fe  test    al, al
0x180098400  jz      loc_1800986C0
0x180098406  lea     rdx, aRootCimv2; "root\\cimv2"
0x18009840d  lea     rcx, [rbp+47h+var_70]
0x180098411  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x180098417  nop
0x180098418  mov     [rbp+47h+nSize], 10h
0x18009841f  lea     rdx, [rbp+47h+nSize]; nSize
0x180098423  lea     rcx, [rbp+47h+Buffer]; lpBuffer
0x180098427  call    ?ProviderGetComputerName@@YAHPEAGPEAK@Z; ProviderGetComputerName(ushort *,ulong *)
0x18009842c  lea     rdx, [rbp+47h+Buffer]
0x180098430  lea     rcx, [rbp+47h+var_78]
0x180098434  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x18009843a  nop
0x18009843b  lea     r8, [rbp+47h+var_78]
0x18009843f  lea     rdx, asc_18013E8E4; "\\\\"
0x180098446  lea     rcx, [rbp+47h+var_50]
0x18009844a  call    cs:__imp_??H@YA?AVCHString@@PEBGAEBV0@@Z; operator+(ushort const *,CHString const &)
0x180098450  nop
0x180098451  lea     r8, SubBlock; "\\"
0x180098458  mov     rdx, rax
0x18009845b  lea     rcx, [rbp+47h+var_58]
0x18009845f  call    cs:__imp_??H@YA?AVCHString@@AEBV0@PEBG@Z; operator+(CHString const &,ushort const *)
0x180098465  nop
0x180098466  lea     r8, [rbp+47h+var_70]
0x18009846a  mov     rdx, rax
0x18009846d  lea     rcx, [rbp+47h+var_60]
0x180098471  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x180098477  nop
0x180098478  lea     r8, SubStr; ":"
0x18009847f  mov     rdx, rax
0x180098482  lea     rcx, [rbp+47h+var_A0]
0x180098486  call    cs:__imp_??H@YA?AVCHString@@AEBV0@PEBG@Z; operator+(CHString const &,ushort const *)
0x18009848c  nop
0x18009848d  lea     r8, [rbp+47h+var_88]
0x180098491  mov     rdx, rax
0x180098494  lea     rcx, [rbp+47h+var_80]
0x180098498  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x18009849e  nop
0x18009849f  lea     rcx, [rbp+47h+var_A0]
0x1800984a3  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800984a9  nop
0x1800984aa  lea     rcx, [rbp+47h+var_60]
0x1800984ae  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800984b4  nop
0x1800984b5  lea     rcx, [rbp+47h+var_58]
0x1800984b9  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800984bf  nop
0x1800984c0  lea     rcx, [rbp+47h+var_50]
0x1800984c4  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800984ca  mov     [rbp+47h+var_98], 0
0x1800984d2  mov     rcx, rbx
0x1800984d5  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800984db  mov     rbx, rax
0x1800984de  lea     rcx, [rbp+47h+var_98]
0x1800984e2  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800984e7  mov     [rbp+47h+var_98], 0
0x1800984ef  lea     rcx, [rbp+47h+var_80]
0x1800984f3  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800984f9  mov     r8, rbx
0x1800984fc  lea     rdx, [rbp+47h+var_98]
0x180098500  mov     rcx, rax
0x180098503  call    cs:__imp_?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z; CWbemProviderGlue::GetInstanceByPath(ushort const *,CInstance * *,MethodContext *)
0x180098509  test    eax, eax
0x18009850b  js      loc_18009868F
0x180098511  lea     rcx, [rbp+47h+var_A0]
0x180098515  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18009851b  nop
0x18009851c  lea     rcx, [rbp+47h+var_98]
0x180098520  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180098525  mov     r8, rsi
0x180098528  lea     rdx, aName; "Name"
0x18009852f  mov     rcx, rax
0x180098532  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180098538  lea     rcx, [rbp+47h+var_98]
0x18009853c  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180098541  lea     r8, [rbp+47h+var_A0]
0x180098545  lea     rdx, aState; "State"
0x18009854c  mov     rcx, rax
0x18009854f  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180098555  lea     rcx, [rbp+47h+var_98]
0x180098559  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18009855e  mov     r8, r14
0x180098561  lea     rdx, aAcceptpause; "AcceptPause"
0x180098568  mov     rcx, rax
0x18009856b  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x180098571  lea     rcx, [rbp+47h+var_98]
0x180098575  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18009857a  mov     r8, r15
0x18009857d  lea     rdx, aAcceptstop; "AcceptStop"
0x180098584  mov     rcx, rax
0x180098587  call    cs:__imp_?Getbool@CInstance@@QEBA_NPEBGAEA_N@Z; CInstance::Getbool(ushort const *,bool &)
0x18009858d  mov     rcx, [rbp+47h+var_98]
0x180098591  test    rcx, rcx
0x180098594  jnz     short loc_1800985A1
0x180098596  mov     ecx, 80004003h; int
0x18009859b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800985a1  xor     ebx, ebx
0x1800985a3  call    cs:__imp_?Release@CInstance@@QEAAJXZ; CInstance::Release(void)
0x1800985a9  mov     [rbp+47h+var_98], rbx
0x1800985ad  lea     rdx, aStopped; "Stopped"
0x1800985b4  lea     rcx, [rbp+47h+var_A0]
0x1800985b8  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800985be  test    eax, eax
0x1800985c0  jnz     short loc_1800985CD
0x1800985c2  mov     dword ptr [rdi], 1
0x1800985c8  jmp     loc_180098683
0x1800985cd  lea     rdx, aStartPending; "Start Pending"
0x1800985d4  lea     rcx, [rbp+47h+var_A0]
0x1800985d8  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800985de  test    eax, eax
0x1800985e0  jnz     short loc_1800985ED
0x1800985e2  mov     dword ptr [rdi], 2
0x1800985e8  jmp     loc_180098683
0x1800985ed  lea     rdx, aStopPending; "Stop Pending"
0x1800985f4  lea     rcx, [rbp+47h+var_A0]
0x1800985f8  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800985fe  test    eax, eax
0x180098600  jnz     short loc_18009860A
0x180098602  mov     dword ptr [rdi], 3
0x180098608  jmp     short loc_180098683
0x18009860a  lea     rdx, aRunning; "Running"
0x180098611  lea     rcx, [rbp+47h+var_A0]
0x180098615  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x18009861b  test    eax, eax
0x18009861d  jnz     short loc_180098627
0x18009861f  mov     dword ptr [rdi], 4
0x180098625  jmp     short loc_180098683
0x180098627  lea     rdx, aContinuePendin; "Continue Pending"
0x18009862e  lea     rcx, [rbp+47h+var_A0]
0x180098632  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180098638  test    eax, eax
0x18009863a  jnz     short loc_180098644
0x18009863c  mov     dword ptr [rdi], 5
0x180098642  jmp     short loc_180098683
0x180098644  lea     rdx, aPausePending; "Pause Pending"
0x18009864b  lea     rcx, [rbp+47h+var_A0]
0x18009864f  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180098655  test    eax, eax
0x180098657  jnz     short loc_180098661
0x180098659  mov     dword ptr [rdi], 6
0x18009865f  jmp     short loc_180098683
0x180098661  lea     rdx, aPaused; "Paused"
0x180098668  lea     rcx, [rbp+47h+var_A0]
0x18009866c  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180098672  test    eax, eax
0x180098674  jnz     short loc_18009867E
0x180098676  mov     dword ptr [rdi], 7
0x18009867c  jmp     short loc_180098683
0x18009867e  mov     ebx, 80041004h
0x180098683  lea     rcx, [rbp+47h+var_A0]
0x180098687  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18009868d  jmp     short loc_180098694
0x18009868f  mov     ebx, 80041004h
0x180098694  lea     rcx, [rbp+47h+var_98]
0x180098698  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18009869d  nop
0x18009869e  lea     rcx, [rbp+47h+var_80]
0x1800986a2  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800986a8  nop
0x1800986a9  lea     rcx, [rbp+47h+var_78]
0x1800986ad  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800986b3  nop
0x1800986b4  lea     rcx, [rbp+47h+var_70]
0x1800986b8  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800986be  jmp     short loc_1800986C5
0x1800986c0  mov     ebx, 80041001h
0x1800986c5  lea     rcx, [rbp+47h+var_68]
0x1800986c9  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800986cf  nop
0x1800986d0  lea     rcx, [rbp+47h+var_88]
0x1800986d4  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800986da  mov     eax, ebx
0x1800986dc  mov     rcx, [rbp+47h+var_28]
0x1800986e0  xor     rcx, rsp; StackCookie
0x1800986e3  call    __security_check_cookie
0x1800986e8  mov     rbx, [rsp+0C0h+arg_0]
0x1800986f0  add     rsp, 0A0h
0x1800986f7  pop     r15
0x1800986f9  pop     r14
0x1800986fb  pop     rdi
0x1800986fc  pop     rsi
0x1800986fd  pop     rbp
0x1800986fe  retn
```
