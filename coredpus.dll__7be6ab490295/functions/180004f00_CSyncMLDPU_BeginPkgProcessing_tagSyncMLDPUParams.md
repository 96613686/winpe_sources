# CSyncMLDPU::BeginPkgProcessing(tagSyncMLDPUParams *)

- ea: `0x180004f00`
- end: `0x180005368`
- name: `?BeginPkgProcessing@CSyncMLDPU@@AEAAJPEAUtagSyncMLDPUParams@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, struct tagSyncMLDPUParams *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007820`

## callees

- `0x180002c90`
- `0x180004f00`
- `0x180011940`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004fcf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005340`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004fcf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005340`
- `OLEAUT32!__imp_SysAllocString` at `0x1800051f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180005213`
- `OLEAUT32!__imp_SysAllocString` at `0x1800051f8`
- `OLEAUT32!__imp_SysAllocString` at `0x180005213`
- `OLEAUT32!__imp_SysFreeString` at `0x180005284`
- `OLEAUT32!__imp_SysFreeString` at `0x180005284`
- `OLEAUT32!__imp_VariantInit` at `0x180004fdf`
- `OLEAUT32!__imp_VariantInit` at `0x180004fdf`
- `OLEAUT32!__imp_VariantClear` at `0x180005275`
- `OLEAUT32!__imp_VariantClear` at `0x180005275`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800050ae`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800050ae`
- `XmlLite!CreateXmlWriter` at `0x180005079`
- `XmlLite!CreateXmlWriter` at `0x180005079`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800051d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800051d6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000504f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000504f`

## string_xrefs

- `0x180005170`: `xmlns`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::BeginPkgProcessing(CSyncMLDPU *this, struct tagSyncMLDPUParams *a2)
{
  OLECHAR *v2; // r14
  int v5; // eax
  HRESULT StreamOnHGlobal; // ebx
  _QWORD *v7; // rsi
  __int64 v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  _DWORD v12[4]; // [rsp+38h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-39h] BYREF
  IRecordInfo *pRecInfo; // [rsp+58h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-1h] BYREF
  __int16 *v17; // [rsp+90h] [rbp+Fh]
  int v18; // [rsp+98h] [rbp+17h]
  int v19; // [rsp+9Ch] [rbp+1Bh]
  _DWORD *v20; // [rsp+A0h] [rbp+1Fh]
  __int64 v21; // [rsp+A8h] [rbp+27h]

  v2 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v17 = word_180035D1A;
    UserData.Reserved = 2;
    v18 = 22;
    v19 = 1;
    v12[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  VariantInit(&pvarg);
  CSyncMLDPU::FreePerPkgState(this);
  *((_DWORD *)this + 7) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 58) = *((_DWORD *)a2 + 3);
  *(_QWORD *)((char *)this + 236) = 0;
  *((_DWORD *)this + 61) = 0;
  *((_DWORD *)this + 106) = 4;
  *((_QWORD *)this + 55) = 0;
  v5 = *((_DWORD *)a2 + 11) & 1;
  CSyncMLDPU::s_dwCurrClientCmdID = 2;
  *((_DWORD *)this + 11) = v5;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)this + 36);
  if ( StreamOnHGlobal >= 0 )
  {
    v7 = (_QWORD *)((char *)this + 256);
    StreamOnHGlobal = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, (void **)this + 32, 0);
    if ( StreamOnHGlobal >= 0 )
    {
      StreamOnHGlobal = CreateXmlWriterOutputWithEncodingName(
                          *((IUnknown **)this + 36),
                          0,
                          L"UTF-16",
                          (IXmlWriterOutput **)this + 33);
      if ( StreamOnHGlobal >= 0 )
      {
        StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 24LL))(
                            *v7,
                            *((_QWORD *)this + 33));
        if ( StreamOnHGlobal >= 0 )
        {
          StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v7 + 40LL))(*v7, 2, 0);
          if ( StreamOnHGlobal >= 0 )
          {
            StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v7 + 40LL))(*v7, 3, 1);
            if ( StreamOnHGlobal >= 0 )
            {
              StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)*v7 + 216LL))(
                                  *v7,
                                  0,
                                  L"Temp",
                                  0);
              if ( StreamOnHGlobal >= 0 )
              {
                if ( !*((_DWORD *)this + 11)
                  || (StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, _QWORD, const unsigned __int16 *))(*(_QWORD *)*v7 + 56LL))(
                                          *v7,
                                          L"xmlns",
                                          L"msft",
                                          0,
                                          L"Microsoft"),
                      StreamOnHGlobal >= 0) )
                {
                  std::for_each<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ALERTINFORESULT>>>,void (*)(ALERTINFORESULT &)>(*((struct ALERTINFORESULT **)this + 38));
                  v8 = *((_QWORD *)this + 38);
                  if ( v8 != *((_QWORD *)this + 39) )
                    *((_QWORD *)this + 39) = v8;
                  StreamOnHGlobal = CoCreateInstance(
                                      &GUID_66d0db14_5638_475f_a386_629522d8c461,
                                      0,
                                      1u,
                                      &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                                      (LPVOID *)this + 7);
                  if ( StreamOnHGlobal >= 0 && *((_QWORD *)this + 41) )
                  {
                    v2 = SysAllocString(L"OMADM::ServerID");
                    if ( v2 && (pvarg.llVal = (LONGLONG)SysAllocString(*((const OLECHAR **)this + 41))) != 0 )
                    {
                      v9 = (__int64 *)*((_QWORD *)this + 7);
                      pvarg.vt = 8;
                      v10 = *v9;
                      pRecInfo = pvarg.pRecInfo;
                      EventDescriptor = *(EVENT_DESCRIPTOR *)&pvarg.vt;
                      StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, EVENT_DESCRIPTOR *))(v10 + 104))(
                                          v9,
                                          v2,
                                          &EventDescriptor);
                    }
                    else
                    {
                      StreamOnHGlobal = -2147024882;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  VariantClear(&pvarg);
  SysFreeString(v2);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v12[0] = StreamOnHGlobal;
    v20 = v12;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v21 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v17 = word_180036172;
    UserData.Reserved = 2;
    v18 = 31;
    v19 = 1;
    v12[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180004f00  mov     r11, rsp
0x180004f03  push    rbp
0x180004f04  push    rbx
0x180004f05  push    rsi
0x180004f06  push    r13
0x180004f08  lea     rbp, [r11-5Fh]
0x180004f0c  sub     rsp, 0B8h
0x180004f13  mov     rax, cs:__security_cookie
0x180004f1a  xor     rax, rsp
0x180004f1d  mov     [rbp+57h+var_28], rax
0x180004f21  mov     [r11+10h], rdi
0x180004f25  lea     r13, _TraceLoggingMetadataEnd
0x180004f2c  xor     eax, eax
0x180004f2e  mov     [r11+18h], r12
0x180004f32  mov     [r11+20h], r14
0x180004f36  lea     rsi, _TraceLoggingMetadata
0x180004f3d  xor     r14d, r14d
0x180004f40  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180004f44  mov     eax, cs:dword_18003E048
0x180004f4a  xorps   xmm0, xmm0
0x180004f4d  mov     rbx, rdx
0x180004f50  mov     rdi, rcx
0x180004f53  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180004f57  cmp     eax, 5
0x180004f5a  jbe     short loc_180004FDB
0x180004f5c  movzx   eax, cs:word_180035D10
0x180004f63  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180004f67  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180004f6a  xor     r9d, r9d; RelatedActivityId
0x180004f6d  mov     rax, cs:off_18003E050
0x180004f74  xor     r8d, r8d; ActivityId
0x180004f77  mov     [rbp+57h+UserData.Ptr], rax
0x180004f7b  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180004f82  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180004f86  movzx   eax, word ptr [rax]
0x180004f89  mov     [rbp+57h+UserData.Size], eax
0x180004f8c  lea     rax, word_180035D1A
0x180004f93  mov     [rbp+57h+var_48], rax
0x180004f97  mov     rax, r13
0x180004f9a  sub     eax, esi
0x180004f9c  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x180004fa3  mov     [rbp+57h+var_40], 16h
0x180004faa  mov     [rbp+57h+var_3C], 1
0x180004fb1  mov     [rbp+57h+var_A0], eax
0x180004fb4  mov     eax, [rbp+57h+var_A0]
0x180004fb7  mov     rcx, cs:RegHandle; RegHandle
0x180004fbe  lea     rax, [rbp+57h+UserData]
0x180004fc2  mov     [rsp+28h], rax; UserData
0x180004fc7  mov     [rsp+0D0h+UserDataCount], 2; UserDataCount
0x180004fcf  call    cs:__imp_EventWriteTransfer
0x180004fd6  nop     dword ptr [rax+rax+00h]
0x180004fdb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180004fdf  call    cs:__imp_VariantInit
0x180004fe6  nop     dword ptr [rax+rax+00h]
0x180004feb  mov     rcx, rdi; this
0x180004fee  call    ?FreePerPkgState@CSyncMLDPU@@AEAAXXZ; CSyncMLDPU::FreePerPkgState(void)
0x180004ff3  mov     [rdi+1Ch], r14d
0x180004ff7  lea     r8, [rdi+120h]; ppstm
0x180004ffe  mov     [rdi+24h], r14
0x180005002  mov     edx, 1; fDeleteOnRelease
0x180005007  mov     [rdi+30h], r14d
0x18000500b  xor     ecx, ecx; hGlobal
0x18000500d  mov     [rdi+0E0h], r14d
0x180005014  mov     eax, [rbx+0Ch]
0x180005017  mov     [rdi+0E8h], eax
0x18000501d  mov     [rdi+0ECh], r14
0x180005024  mov     [rdi+0F4h], r14d
0x18000502b  mov     dword ptr [rdi+1A8h], 4
0x180005035  mov     [rdi+1B8h], r14
0x18000503c  mov     eax, [rbx+2Ch]
0x18000503f  and     eax, 1
0x180005042  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, 2; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x18000504c  mov     [rdi+2Ch], eax
0x18000504f  call    cs:__imp_CreateStreamOnHGlobal
0x180005056  nop     dword ptr [rax+rax+00h]
0x18000505b  mov     ebx, eax
0x18000505d  test    eax, eax
0x18000505f  js      loc_180005271
0x180005065  lea     rsi, [rdi+100h]
0x18000506c  xor     r8d, r8d; pMalloc
0x18000506f  mov     rdx, rsi; ppvObject
0x180005072  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180005079  call    cs:__imp_CreateXmlWriter
0x180005080  nop     dword ptr [rax+rax+00h]
0x180005085  mov     ebx, eax
0x180005087  test    eax, eax
0x180005089  js      loc_18000526A
0x18000508f  mov     rcx, [rdi+120h]; pOutputStream
0x180005096  lea     r9, [rdi+108h]; ppOutput
0x18000509d  lea     r8, pwszEncodingName; "UTF-16"
0x1800050a4  mov     [rsp+0B0h], r15
0x1800050ac  xor     edx, edx; pMalloc
0x1800050ae  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x1800050b5  nop     dword ptr [rax+rax+00h]
0x1800050ba  mov     ebx, eax
0x1800050bc  test    eax, eax
0x1800050be  js      loc_180005262
0x1800050c4  mov     rcx, [rsi]
0x1800050c7  mov     rdx, [rdi+108h]
0x1800050ce  mov     rax, [rcx]
0x1800050d1  mov     rax, [rax+18h]
0x1800050d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050da  mov     ebx, eax
0x1800050dc  test    eax, eax
0x1800050de  js      loc_180005262
0x1800050e4  mov     rcx, [rsi]
0x1800050e7  xor     r8d, r8d
0x1800050ea  mov     edx, 2
0x1800050ef  mov     rax, [rcx]
0x1800050f2  mov     rax, [rax+28h]
0x1800050f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fb  mov     ebx, eax
0x1800050fd  test    eax, eax
0x1800050ff  js      loc_180005262
0x180005105  mov     rcx, [rsi]
0x180005108  mov     edx, 3
0x18000510d  mov     r8d, 1
0x180005113  mov     rax, [rcx]
0x180005116  mov     rax, [rax+28h]
0x18000511a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000511f  mov     ebx, eax
0x180005121  test    eax, eax
0x180005123  js      loc_180005262
0x180005129  mov     rcx, [rsi]
0x18000512c  lea     r8, aTemp; "Temp"
0x180005133  xor     r9d, r9d
0x180005136  xor     edx, edx
0x180005138  mov     rax, [rcx]
0x18000513b  mov     rax, [rax+0D8h]
0x180005142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005147  mov     ebx, eax
0x180005149  test    eax, eax
0x18000514b  js      loc_180005262
0x180005151  cmp     [rdi+2Ch], r14d
0x180005155  jz      short loc_18000518D
0x180005157  mov     rcx, [rsi]
0x18000515a  lea     rdx, ?gc_szOrginalErrorMicrosoft@@3QBGB; "Microsoft"
0x180005161  mov     qword ptr [rsp+0D0h+UserDataCount], rdx
0x180005166  lea     r8, ?gc_szOrginalErrorNamespace@@3QBGB; "msft"
0x18000516d  xor     r9d, r9d
0x180005170  lea     rdx, ?gc_szOrginalErrorxmlns@@3QBGB; "xmlns"
0x180005177  mov     rax, [rcx]
0x18000517a  mov     rax, [rax+38h]
0x18000517e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005183  mov     ebx, eax
0x180005185  test    eax, eax
0x180005187  js      loc_180005262
0x18000518d  mov     rdx, [rdi+138h]
0x180005194  mov     rcx, [rdi+130h]; struct ALERTINFORESULT *
0x18000519b  call    ??$for_each@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UALERTINFORESULT@@@std@@@std@@@std@@P6AXAEAUALERTINFORESULT@@@Z@std@@YAP6AXAEAUALERTINFORESULT@@@ZV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UALERTINFORESULT@@@std@@@std@@@0@1P6AX0@Z@Z; std::for_each<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ALERTINFORESULT>>>,void (*)(ALERTINFORESULT &)>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ALERTINFORESULT>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ALERTINFORESULT>>>,void (*)(ALERTINFORESULT &))
0x1800051a0  mov     rax, [rdi+130h]
0x1800051a7  cmp     rax, [rdi+138h]
0x1800051ae  jz      short loc_1800051B7
0x1800051b0  mov     [rdi+138h], rax
0x1800051b7  lea     rsi, [rdi+38h]
0x1800051bb  xor     edx, edx; pUnkOuter
0x1800051bd  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800051c4  mov     qword ptr [rsp+0D0h+UserDataCount], rsi; ppv
0x1800051c9  mov     r8d, 1; dwClsContext
0x1800051cf  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800051d6  call    cs:__imp_CoCreateInstance
0x1800051dd  nop     dword ptr [rax+rax+00h]
0x1800051e2  mov     ebx, eax
0x1800051e4  test    eax, eax
0x1800051e6  js      short loc_180005262
0x1800051e8  cmp     [rdi+148h], r14
0x1800051ef  jz      short loc_180005262
0x1800051f1  lea     rcx, aOmadmServerid; "OMADM::ServerID"
0x1800051f8  call    cs:__imp_SysAllocString
0x1800051ff  nop     dword ptr [rax+rax+00h]
0x180005204  mov     r14, rax
0x180005207  test    rax, rax
0x18000520a  jz      short loc_18000525D
0x18000520c  mov     rcx, [rdi+148h]; psz
0x180005213  call    cs:__imp_SysAllocString
0x18000521a  nop     dword ptr [rax+rax+00h]
0x18000521f  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180005223  test    rax, rax
0x180005226  jz      short loc_18000525D
0x180005228  mov     rcx, [rsi]
0x18000522b  lea     r8, [rbp+57h+EventDescriptor]
0x18000522f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180005234  mov     eax, 8
0x180005239  mov     word ptr [rbp+57h+pvarg], ax
0x18000523d  mov     rdx, r14
0x180005240  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180005244  mov     rax, [rcx]
0x180005247  movsd   [rbp+57h+var_80], xmm1
0x18000524c  movaps  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x180005250  mov     rax, [rax+68h]
0x180005254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005259  mov     ebx, eax
0x18000525b  jmp     short loc_180005262
0x18000525d  mov     ebx, 8007000Eh
0x180005262  mov     r15, [rsp+0B0h]
0x18000526a  lea     rsi, _TraceLoggingMetadata
0x180005271  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180005275  call    cs:__imp_VariantClear
0x18000527c  nop     dword ptr [rax+rax+00h]
0x180005281  mov     rcx, r14; bstrString
0x180005284  call    cs:__imp_SysFreeString
0x18000528b  nop     dword ptr [rax+rax+00h]
0x180005290  mov     eax, cs:dword_18003E048
0x180005296  mov     r14, [rsp+0D0h+arg_18]
0x18000529e  mov     r12, [rsp+0D0h+arg_10]
0x1800052a6  mov     rdi, [rsp+0D0h+arg_8]
0x1800052ae  cmp     eax, 5
0x1800052b1  jbe     loc_18000534C
0x1800052b7  lea     rax, [rbp+57h+var_A0]
0x1800052bb  mov     [rbp+57h+var_A0], ebx
0x1800052be  mov     [rbp+57h+var_38], rax
0x1800052c2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800052c6  movzx   eax, cs:word_180036168
0x1800052cd  sub     r13d, esi
0x1800052d0  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800052d3  xor     r9d, r9d; RelatedActivityId
0x1800052d6  mov     rax, cs:off_18003E050
0x1800052dd  xor     r8d, r8d; ActivityId
0x1800052e0  mov     [rbp+57h+UserData.Ptr], rax
0x1800052e4  mov     [rbp+57h+var_30], 4
0x1800052ec  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800052f3  mov     [rbp+57h+EventDescriptor.Keyword], 0
0x1800052fb  movzx   eax, word ptr [rax]
0x1800052fe  mov     [rbp+57h+UserData.Size], eax
0x180005301  lea     rax, word_180036172
0x180005308  mov     [rbp+57h+var_48], rax
0x18000530c  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x180005313  mov     [rbp+57h+var_40], 1Fh
0x18000531a  mov     [rbp+57h+var_3C], 1
0x180005321  mov     [rbp+57h+var_9C], r13d
0x180005325  mov     eax, [rbp+57h+var_9C]
0x180005328  mov     rcx, cs:RegHandle; RegHandle
0x18000532f  lea     rax, [rbp+57h+UserData]
0x180005333  mov     [rsp+28h], rax; UserData
0x180005338  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x180005340  call    cs:__imp_EventWriteTransfer
0x180005347  nop     dword ptr [rax+rax+00h]
0x18000534c  mov     eax, ebx
0x18000534e  mov     rcx, [rbp+57h+var_28]
0x180005352  xor     rcx, rsp; StackCookie
0x180005355  call    __security_check_cookie
0x18000535a  add     rsp, 0B8h
0x180005361  pop     r13
0x180005363  pop     rsi
0x180005364  pop     rbx
0x180005365  pop     rbp
0x180005366  retn
```
