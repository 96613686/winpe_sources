# LogAIKEnrollmentResult(long,bool,bool,ushort const *,EnrollAIKResult const *,_RETRYINFO const *)

- ea: `0x180013310`
- end: `0x180013b00`
- name: `?LogAIKEnrollmentResult@@YAXJ_N0PEBGPEBUEnrollAIKResult@@PEBU_RETRYINFO@@@Z`
- size: `2032`
- prototype: `void __usercall(unsigned int@<ecx>, bool@<dl>, bool@<r8b>, const unsigned __int16 *@<r9>, const struct EnrollAIKResult *, const struct _RETRYINFO *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012274`
- `0x180013b08`

## callees

- `0x18000247c`
- `0x180002548`
- `0x180002a08`
- `0x180008ab0`
- `0x18000ebc0`
- `0x180010310`
- `0x180012f0c`
- `0x180013310`
- `0x180014bcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001335b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001335b`

## string_xrefs

- `0x18001336c`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall LogAIKEnrollmentResult(
        int a1,
        char a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        const struct EnrollAIKResult *a5,
        const struct _RETRYINFO *a6)
{
  int v7; // r14d
  HRESULT Instance; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // ecx
  __int64 v22; // rcx
  int v23; // [rsp+120h] [rbp-80h] BYREF
  int v24; // [rsp+124h] [rbp-7Ch] BYREF
  int v25; // [rsp+128h] [rbp-78h] BYREF
  int v26; // [rsp+12Ch] [rbp-74h] BYREF
  int v27; // [rsp+130h] [rbp-70h] BYREF
  int v28; // [rsp+134h] [rbp-6Ch] BYREF
  int v29; // [rsp+138h] [rbp-68h] BYREF
  int v30; // [rsp+13Ch] [rbp-64h] BYREF
  int v31; // [rsp+140h] [rbp-60h] BYREF
  int v32; // [rsp+144h] [rbp-5Ch] BYREF
  int v33; // [rsp+148h] [rbp-58h] BYREF
  int v34; // [rsp+14Ch] [rbp-54h] BYREF
  int v35; // [rsp+150h] [rbp-50h] BYREF
  int v36; // [rsp+154h] [rbp-4Ch] BYREF
  int v37; // [rsp+158h] [rbp-48h] BYREF
  unsigned __int16 *v38; // [rsp+160h] [rbp-40h] BYREF
  unsigned __int16 *v39; // [rsp+168h] [rbp-38h] BYREF
  __int64 v40; // [rsp+170h] [rbp-30h] BYREF
  __int64 v41; // [rsp+178h] [rbp-28h] BYREF
  __int64 v42; // [rsp+180h] [rbp-20h] BYREF
  __int64 v43; // [rsp+188h] [rbp-18h] BYREF
  __int64 v44; // [rsp+190h] [rbp-10h] BYREF
  __int64 v45; // [rsp+198h] [rbp-8h] BYREF
  __int64 v46; // [rsp+1A0h] [rbp+0h] BYREF
  __int64 v47; // [rsp+1A8h] [rbp+8h] BYREF
  __int64 v48; // [rsp+1B0h] [rbp+10h] BYREF
  __int64 v49; // [rsp+1B8h] [rbp+18h] BYREF
  unsigned __int16 *v50; // [rsp+1C0h] [rbp+20h] BYREF
  const unsigned __int16 *v51; // [rsp+1C8h] [rbp+28h] BYREF
  struct ICertRequest2 *ppv; // [rsp+1D0h] [rbp+30h] BYREF
  const unsigned __int16 *v53; // [rsp+1D8h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+58h]
  int v55; // [rsp+200h] [rbp+60h] BYREF
  int v56; // [rsp+210h] [rbp+70h]

  v7 = a3;
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_98aff3f0_5524_11d0_8812_00a0c903b83c,
               0,
               1u,
               &GUID_a4772988_4a85_4fa9_824e_b5cf5c16405a,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3F0,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)Instance);
  if ( a1 >= 0 )
  {
    if ( (unsigned int)dword_180031038 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      v56 = v7;
      v51 = a4;
      v50 = (unsigned __int16 *)*((_QWORD *)a6 + 2);
      v49 = *((_QWORD *)a6 + 3);
      v55 = *((_DWORD *)a6 + 1);
      v36 = *(_DWORD *)a6;
      v48 = *((_QWORD *)a5 + 9);
      v35 = *((_DWORD *)a5 + 22);
      v34 = *((_DWORD *)a5 + 23);
      v33 = *((_DWORD *)a5 + 34);
      v32 = *((_DWORD *)a5 + 33);
      v31 = *((_DWORD *)a5 + 32);
      v30 = *((_DWORD *)a5 + 31);
      v29 = *((_DWORD *)a5 + 30);
      v28 = *((_DWORD *)a5 + 29);
      v27 = *((_DWORD *)a5 + 28);
      v26 = *((_DWORD *)a5 + 27);
      v25 = *((_DWORD *)a5 + 26);
      v47 = *((_QWORD *)a5 + 12);
      v46 = *((_QWORD *)a5 + 8);
      v45 = *((_QWORD *)a5 + 7);
      v44 = *((_QWORD *)a5 + 6);
      v43 = *((_QWORD *)a5 + 5);
      v42 = *((_QWORD *)a5 + 4);
      v41 = *((_QWORD *)a5 + 3);
      v40 = *((_QWORD *)a5 + 2);
      v21 = *((_DWORD *)a5 + 1);
      v24 = (unsigned __int16)v21;
      v22 = HIWORD(v21);
      v23 = v22;
      v39 = (unsigned __int16 *)*((_QWORD *)a5 + 1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v22,
        (__int64)byte_1800294B5,
        v19,
        v20,
        &v39,
        (__int64)&v23,
        (__int64)&v24,
        &v40,
        &v41,
        &v42,
        &v43,
        &v44,
        &v45,
        &v46,
        &v47,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)&v35,
        &v48,
        (__int64)&v36,
        (__int64)&v55,
        (__int64)&v49,
        (__int64)&v50,
        &v51);
    }
  }
  else
  {
    v38 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    GetErrorSymbol(ppv, (unsigned int)a1, &v38);
    if ( a2 )
    {
      if ( (unsigned int)dword_180031038 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      {
        v56 = a1;
        v55 = v7;
        v53 = a4;
        v39 = v38;
        v40 = *((_QWORD *)a6 + 2);
        v41 = *((_QWORD *)a6 + 3);
        v37 = *((_DWORD *)a6 + 1);
        v23 = *(_DWORD *)a6;
        v42 = *((_QWORD *)a5 + 9);
        v24 = *((_DWORD *)a5 + 22);
        v25 = *((_DWORD *)a5 + 23);
        v26 = *((_DWORD *)a5 + 34);
        v27 = *((_DWORD *)a5 + 33);
        v28 = *((_DWORD *)a5 + 32);
        v29 = *((_DWORD *)a5 + 31);
        v30 = *((_DWORD *)a5 + 30);
        v31 = *((_DWORD *)a5 + 29);
        v32 = *((_DWORD *)a5 + 28);
        v33 = *((_DWORD *)a5 + 27);
        v34 = *((_DWORD *)a5 + 26);
        v43 = *((_QWORD *)a5 + 12);
        v44 = *((_QWORD *)a5 + 8);
        v45 = *((_QWORD *)a5 + 7);
        v46 = *((_QWORD *)a5 + 6);
        v47 = *((_QWORD *)a5 + 5);
        v48 = *((_QWORD *)a5 + 4);
        v49 = *((_QWORD *)a5 + 3);
        v50 = (unsigned __int16 *)*((_QWORD *)a5 + 2);
        v13 = *((_DWORD *)a5 + 1);
        v35 = (unsigned __int16)v13;
        v14 = HIWORD(v13);
        v36 = v14;
        v51 = (const unsigned __int16 *)*((_QWORD *)a5 + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (__int64)word_1800297DA,
          v11,
          v12,
          &v51,
          (__int64)&v36,
          (__int64)&v35,
          &v50,
          &v49,
          &v48,
          &v47,
          &v46,
          &v45,
          &v44,
          &v43,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24,
          &v42,
          (__int64)&v23,
          (__int64)&v37,
          (__int64)&v41,
          (__int64)&v40,
          &v39,
          &v53);
      }
    }
    else if ( (unsigned int)dword_180031038 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      v56 = a1;
      v55 = v7;
      v51 = a4;
      v50 = v38;
      v49 = *((_QWORD *)a6 + 2);
      v48 = *((_QWORD *)a6 + 3);
      v36 = *((_DWORD *)a6 + 1);
      v35 = *(_DWORD *)a6;
      v47 = *((_QWORD *)a5 + 9);
      v34 = *((_DWORD *)a5 + 22);
      v33 = *((_DWORD *)a5 + 23);
      v32 = *((_DWORD *)a5 + 34);
      v31 = *((_DWORD *)a5 + 33);
      v30 = *((_DWORD *)a5 + 32);
      v29 = *((_DWORD *)a5 + 31);
      v28 = *((_DWORD *)a5 + 30);
      v27 = *((_DWORD *)a5 + 29);
      v26 = *((_DWORD *)a5 + 28);
      v25 = *((_DWORD *)a5 + 27);
      v24 = *((_DWORD *)a5 + 26);
      v46 = *((_QWORD *)a5 + 12);
      v45 = *((_QWORD *)a5 + 8);
      v44 = *((_QWORD *)a5 + 7);
      v43 = *((_QWORD *)a5 + 6);
      v42 = *((_QWORD *)a5 + 5);
      v41 = *((_QWORD *)a5 + 4);
      v40 = *((_QWORD *)a5 + 3);
      v39 = (unsigned __int16 *)*((_QWORD *)a5 + 2);
      v17 = *((_DWORD *)a5 + 1);
      v23 = (unsigned __int16)v17;
      v18 = HIWORD(v17);
      v37 = v18;
      v53 = (const unsigned __int16 *)*((_QWORD *)a5 + 1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v18,
        (__int64)&unk_1800292A0,
        v15,
        v16,
        &v53,
        (__int64)&v37,
        (__int64)&v23,
        &v39,
        &v40,
        &v41,
        &v42,
        &v43,
        &v44,
        &v45,
        &v46,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v34,
        &v47,
        (__int64)&v35,
        (__int64)&v36,
        (__int64)&v48,
        (__int64)&v49,
        &v50,
        &v51);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v38);
  }
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&ppv);
}

```

## disassembly

```asm
0x180013310  mov     [rsp-8+arg_8], rbx
0x180013315  mov     [rsp-8+arg_18], rsi
0x18001331a  push    rbp
0x18001331b  push    rdi
0x18001331c  push    r14
0x18001331e  lea     rbp, [rsp-40h]
0x180013323  sub     rsp, 1E0h
0x18001332a  mov     rsi, r9
0x18001332d  movzx   r14d, r8b
0x180013331  mov     dil, dl
0x180013334  mov     ebx, ecx
0x180013336  mov     [rbp+50h+var_20], 0
0x18001333e  lea     rax, [rbp+50h+var_20]
0x180013342  mov     [rsp+1F0h+ppv], rax; int
0x180013347  lea     r9, _GUID_a4772988_4a85_4fa9_824e_b5cf5c16405a; riid
0x18001334e  xor     edx, edx; pUnkOuter
0x180013350  lea     r8d, [rdx+1]; dwClsContext
0x180013354  lea     rcx, _GUID_98aff3f0_5524_11d0_8812_00a0c903b83c; rclsid
0x18001335b  call    cs:__imp_CoCreateInstance
0x180013361  mov     rcx, [rbp+58h]; this
0x180013365  test    eax, eax
0x180013367  jns     short loc_18001337D
0x180013369  mov     r9d, eax; char *
0x18001336c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013373  mov     edx, 3F0h; void *
0x180013378  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001337d  test    ebx, ebx
0x18001337f  jns     loc_180013892
0x180013385  mov     [rbp+50h+var_90], 0
0x18001338d  xor     edx, edx
0x18001338f  lea     rcx, [rbp+50h+var_90]
0x180013393  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180013398  lea     r8, [rbp+50h+var_90]; unsigned __int16 **
0x18001339c  mov     edx, ebx; unsigned int
0x18001339e  mov     rcx, [rbp+50h+var_20]; struct ICertRequest2 *
0x1800133a2  call    ?GetErrorSymbol@@YAXPEAUICertRequest2@@KPEAPEAG@Z; GetErrorSymbol(ICertRequest2 *,ulong,ushort * *)
0x1800133a7  mov     eax, cs:dword_180031038
0x1800133ad  test    dil, dil
0x1800133b0  jz      loc_18001361A
0x1800133b6  cmp     eax, 2
0x1800133b9  jbe     loc_180013884
0x1800133bf  mov     rdx, 400000000000h
0x1800133c9  lea     rcx, dword_180031038
0x1800133d0  call    _tlgKeywordOn
0x1800133d5  test    al, al
0x1800133d7  jz      loc_180013884
0x1800133dd  mov     [rbp+50h+arg_10], ebx
0x1800133e0  mov     [rbp+50h+arg_0], r14d
0x1800133e4  mov     [rbp+50h+var_18], rsi
0x1800133e8  mov     rax, [rbp+50h+var_90]
0x1800133ec  mov     [rbp+50h+var_88], rax
0x1800133f0  mov     rcx, [rbp+50h+arg_28]
0x1800133f7  mov     rax, [rcx+10h]
0x1800133fb  mov     [rbp+50h+var_80], rax
0x1800133ff  mov     rax, [rcx+18h]
0x180013403  mov     [rbp+50h+var_78], rax
0x180013407  mov     eax, [rcx+4]
0x18001340a  mov     [rbp+50h+var_98], eax
0x18001340d  mov     eax, [rcx]
0x18001340f  mov     [rbp+50h+var_D0], eax
0x180013412  mov     rdx, [rbp+50h+arg_20]
0x180013419  mov     rax, [rdx+48h]
0x18001341d  mov     [rbp+50h+var_70], rax
0x180013421  mov     eax, [rdx+58h]
0x180013424  mov     [rbp+50h+var_CC], eax
0x180013427  mov     eax, [rdx+5Ch]
0x18001342a  mov     [rbp+50h+var_C8], eax
0x18001342d  mov     eax, [rdx+88h]
0x180013433  mov     [rbp+50h+var_C4], eax
0x180013436  mov     eax, [rdx+84h]
0x18001343c  mov     [rbp+50h+var_C0], eax
0x18001343f  mov     eax, [rdx+80h]
0x180013445  mov     [rbp+50h+var_BC], eax
0x180013448  mov     eax, [rdx+7Ch]
0x18001344b  mov     [rbp+50h+var_B8], eax
0x18001344e  mov     eax, [rdx+78h]
0x180013451  mov     [rbp+50h+var_B4], eax
0x180013454  mov     eax, [rdx+74h]
0x180013457  mov     [rbp+50h+var_B0], eax
0x18001345a  mov     eax, [rdx+70h]
0x18001345d  mov     [rbp+50h+var_AC], eax
0x180013460  mov     eax, [rdx+6Ch]
0x180013463  mov     [rbp+50h+var_A8], eax
0x180013466  mov     eax, [rdx+68h]
0x180013469  mov     [rbp+50h+var_A4], eax
0x18001346c  mov     rax, [rdx+60h]
0x180013470  mov     [rbp+50h+var_68], rax
0x180013474  mov     rax, [rdx+40h]
0x180013478  mov     [rbp+50h+var_60], rax
0x18001347c  mov     rax, [rdx+38h]
0x180013480  mov     [rbp+50h+var_58], rax
0x180013484  mov     rax, [rdx+30h]
0x180013488  mov     [rbp+50h+var_50], rax
0x18001348c  mov     rax, [rdx+28h]
0x180013490  mov     [rbp+50h+var_48], rax
0x180013494  mov     rax, [rdx+20h]
0x180013498  mov     [rbp+50h+var_40], rax
0x18001349c  mov     rax, [rdx+18h]
0x1800134a0  mov     [rbp+50h+var_38], rax
0x1800134a4  mov     rax, [rdx+10h]
0x1800134a8  mov     [rbp+50h+var_30], rax
0x1800134ac  mov     ecx, [rdx+4]
0x1800134af  movzx   eax, cx
0x1800134b2  mov     [rbp+50h+var_A0], eax
0x1800134b5  shr     ecx, 10h
0x1800134b8  mov     [rbp+50h+var_9C], ecx
0x1800134bb  mov     rax, [rdx+8]
0x1800134bf  mov     [rbp+50h+var_28], rax
0x1800134c3  lea     rax, [rbp+50h+arg_10]
0x1800134c7  mov     [rsp+1F0h+var_E0], rax
0x1800134cf  lea     rax, [rbp+50h+arg_0]
0x1800134d3  mov     [rsp+1F0h+var_E8], rax
0x1800134db  lea     rax, [rbp+50h+var_18]
0x1800134df  mov     [rsp+1F0h+var_F0], rax
0x1800134e7  lea     rax, [rbp+50h+var_88]
0x1800134eb  mov     [rsp+1F0h+var_F8], rax
0x1800134f3  lea     rax, [rbp+50h+var_80]
0x1800134f7  mov     [rsp+1F0h+var_100], rax
0x1800134ff  lea     rax, [rbp+50h+var_78]
0x180013503  mov     [rsp+1F0h+var_108], rax
0x18001350b  lea     rax, [rbp+50h+var_98]
0x18001350f  mov     [rsp+1F0h+var_110], rax
0x180013517  lea     rax, [rbp+50h+var_D0]
0x18001351b  mov     [rsp+1F0h+var_118], rax
0x180013523  lea     rax, [rbp+50h+var_70]
0x180013527  mov     [rsp+1F0h+var_120], rax
0x18001352f  lea     rax, [rbp+50h+var_CC]
0x180013533  mov     [rsp+1F0h+var_128], rax
0x18001353b  lea     rax, [rbp+50h+var_C8]
0x18001353f  mov     [rsp+1F0h+var_130], rax
0x180013547  lea     rax, [rbp+50h+var_C4]
0x18001354b  mov     [rsp+1F0h+var_138], rax
0x180013553  lea     rax, [rbp+50h+var_C0]
0x180013557  mov     [rsp+1F0h+var_140], rax
0x18001355f  lea     rax, [rbp+50h+var_BC]
0x180013563  mov     [rsp+1F0h+var_148], rax
0x18001356b  lea     rax, [rbp+50h+var_B8]
0x18001356f  mov     [rsp+1F0h+var_150], rax
0x180013577  lea     rax, [rbp+50h+var_B4]
0x18001357b  mov     [rsp+1F0h+var_158], rax
0x180013583  lea     rax, [rbp+50h+var_B0]
0x180013587  mov     [rsp+1F0h+var_160], rax
0x18001358f  lea     rax, [rbp+50h+var_AC]
0x180013593  mov     [rsp+1F0h+var_168], rax
0x18001359b  lea     rax, [rbp+50h+var_A8]
0x18001359f  mov     [rsp+1F0h+var_170], rax
0x1800135a7  lea     rax, [rbp+50h+var_A4]
0x1800135ab  mov     [rsp+1F0h+var_178], rax
0x1800135b0  lea     rax, [rbp+50h+var_68]
0x1800135b4  mov     [rsp+1F0h+var_180], rax
0x1800135b9  lea     rax, [rbp+50h+var_60]
0x1800135bd  mov     [rsp+1F0h+var_188], rax
0x1800135c2  lea     rax, [rbp+50h+var_58]
0x1800135c6  mov     [rsp+1F0h+var_190], rax
0x1800135cb  lea     rax, [rbp+50h+var_50]
0x1800135cf  mov     [rsp+1F0h+var_198], rax
0x1800135d4  lea     rax, [rbp+50h+var_48]
0x1800135d8  mov     [rsp+1F0h+var_1A0], rax
0x1800135dd  lea     rax, [rbp+50h+var_40]
0x1800135e1  mov     [rsp+1F0h+var_1A8], rax
0x1800135e6  lea     rax, [rbp+50h+var_38]
0x1800135ea  mov     [rsp+1F0h+var_1B0], rax
0x1800135ef  lea     rax, [rbp+50h+var_30]
0x1800135f3  mov     [rsp+1F0h+var_1B8], rax
0x1800135f8  lea     rax, [rbp+50h+var_A0]
0x1800135fc  mov     [rsp+1F0h+var_1C0], rax
0x180013601  lea     rax, [rbp+50h+var_9C]
0x180013605  mov     [rsp+1F0h+var_1C8], rax
0x18001360a  lea     rax, [rbp+50h+var_28]
0x18001360e  lea     rdx, word_1800297DA
0x180013615  jmp     loc_180013879
0x18001361a  cmp     eax, 2
0x18001361d  jbe     loc_180013884
0x180013623  mov     rdx, 400000000000h
0x18001362d  lea     rcx, dword_180031038
0x180013634  call    _tlgKeywordOn
0x180013639  test    al, al
0x18001363b  jz      loc_180013884
0x180013641  mov     [rbp+50h+arg_10], ebx
0x180013644  mov     [rbp+50h+arg_0], r14d
0x180013648  mov     [rbp+50h+var_28], rsi
0x18001364c  mov     rax, [rbp+50h+var_90]
0x180013650  mov     [rbp+50h+var_30], rax
0x180013654  mov     rcx, [rbp+50h+arg_28]
0x18001365b  mov     rax, [rcx+10h]
0x18001365f  mov     [rbp+50h+var_38], rax
0x180013663  mov     rax, [rcx+18h]
0x180013667  mov     [rbp+50h+var_40], rax
0x18001366b  mov     eax, [rcx+4]
0x18001366e  mov     [rbp+50h+var_9C], eax
0x180013671  mov     eax, [rcx]
0x180013673  mov     [rbp+50h+var_A0], eax
0x180013676  mov     rdx, [rbp+50h+arg_20]
0x18001367d  mov     rax, [rdx+48h]
0x180013681  mov     [rbp+50h+var_48], rax
0x180013685  mov     eax, [rdx+58h]
0x180013688  mov     [rbp+50h+var_A4], eax
0x18001368b  mov     eax, [rdx+5Ch]
0x18001368e  mov     [rbp+50h+var_A8], eax
0x180013691  mov     eax, [rdx+88h]
0x180013697  mov     [rbp+50h+var_AC], eax
0x18001369a  mov     eax, [rdx+84h]
0x1800136a0  mov     [rbp+50h+var_B0], eax
0x1800136a3  mov     eax, [rdx+80h]
0x1800136a9  mov     [rbp+50h+var_B4], eax
0x1800136ac  mov     eax, [rdx+7Ch]
0x1800136af  mov     [rbp+50h+var_B8], eax
0x1800136b2  mov     eax, [rdx+78h]
0x1800136b5  mov     [rbp+50h+var_BC], eax
0x1800136b8  mov     eax, [rdx+74h]
0x1800136bb  mov     [rbp+50h+var_C0], eax
0x1800136be  mov     eax, [rdx+70h]
0x1800136c1  mov     [rbp+50h+var_C4], eax
0x1800136c4  mov     eax, [rdx+6Ch]
0x1800136c7  mov     [rbp+50h+var_C8], eax
0x1800136ca  mov     eax, [rdx+68h]
0x1800136cd  mov     [rbp+50h+var_CC], eax
0x1800136d0  mov     rax, [rdx+60h]
0x1800136d4  mov     [rbp+50h+var_50], rax
0x1800136d8  mov     rax, [rdx+40h]
0x1800136dc  mov     [rbp+50h+var_58], rax
0x1800136e0  mov     rax, [rdx+38h]
0x1800136e4  mov     [rbp+50h+var_60], rax
0x1800136e8  mov     rax, [rdx+30h]
0x1800136ec  mov     [rbp+50h+var_68], rax
0x1800136f0  mov     rax, [rdx+28h]
0x1800136f4  mov     [rbp+50h+var_70], rax
0x1800136f8  mov     rax, [rdx+20h]
0x1800136fc  mov     [rbp+50h+var_78], rax
0x180013700  mov     rax, [rdx+18h]
0x180013704  mov     [rbp+50h+var_80], rax
0x180013708  mov     rax, [rdx+10h]
0x18001370c  mov     [rbp+50h+var_88], rax
0x180013710  mov     ecx, [rdx+4]
0x180013713  movzx   eax, cx
0x180013716  mov     [rbp+50h+var_D0], eax
0x180013719  shr     ecx, 10h
0x18001371c  mov     [rbp+50h+var_98], ecx
0x18001371f  mov     rax, [rdx+8]
0x180013723  mov     [rbp+50h+var_18], rax
0x180013727  lea     rax, [rbp+50h+arg_10]
0x18001372b  mov     [rsp+1F0h+var_E0], rax
0x180013733  lea     rax, [rbp+50h+arg_0]
0x180013737  mov     [rsp+1F0h+var_E8], rax
0x18001373f  lea     rax, [rbp+50h+var_28]
0x180013743  mov     [rsp+1F0h+var_F0], rax
0x18001374b  lea     rax, [rbp+50h+var_30]
0x18001374f  mov     [rsp+1F0h+var_F8], rax
0x180013757  lea     rax, [rbp+50h+var_38]
0x18001375b  mov     [rsp+1F0h+var_100], rax
0x180013763  lea     rax, [rbp+50h+var_40]
0x180013767  mov     [rsp+1F0h+var_108], rax
0x18001376f  lea     rax, [rbp+50h+var_9C]
0x180013773  mov     [rsp+1F0h+var_110], rax
0x18001377b  lea     rax, [rbp+50h+var_A0]
0x18001377f  mov     [rsp+1F0h+var_118], rax
0x180013787  lea     rax, [rbp+50h+var_48]
0x18001378b  mov     [rsp+1F0h+var_120], rax
0x180013793  lea     rax, [rbp+50h+var_A4]
0x180013797  mov     [rsp+1F0h+var_128], rax
0x18001379f  lea     rax, [rbp+50h+var_A8]
0x1800137a3  mov     [rsp+1F0h+var_130], rax
0x1800137ab  lea     rax, [rbp+50h+var_AC]
0x1800137af  mov     [rsp+1F0h+var_138], rax
0x1800137b7  lea     rax, [rbp+50h+var_B0]
0x1800137bb  mov     [rsp+1F0h+var_140], rax
0x1800137c3  lea     rax, [rbp+50h+var_B4]
0x1800137c7  mov     [rsp+1F0h+var_148], rax
0x1800137cf  lea     rax, [rbp+50h+var_B8]
0x1800137d3  mov     [rsp+1F0h+var_150], rax
0x1800137db  lea     rax, [rbp+50h+var_BC]
0x1800137df  mov     [rsp+1F0h+var_158], rax
0x1800137e7  lea     rax, [rbp+50h+var_C0]
0x1800137eb  mov     [rsp+1F0h+var_160], rax
0x1800137f3  lea     rax, [rbp+50h+var_C4]
0x1800137f7  mov     [rsp+1F0h+var_168], rax
0x1800137ff  lea     rax, [rbp+50h+var_C8]
0x180013803  mov     [rsp+1F0h+var_170], rax
0x18001380b  lea     rax, [rbp+50h+var_CC]
0x18001380f  mov     [rsp+1F0h+var_178], rax
0x180013814  lea     rax, [rbp+50h+var_50]
0x180013818  mov     [rsp+1F0h+var_180], rax
0x18001381d  lea     rax, [rbp+50h+var_58]
0x180013821  mov     [rsp+1F0h+var_188], rax
0x180013826  lea     rax, [rbp+50h+var_60]
0x18001382a  mov     [rsp+1F0h+var_190], rax
0x18001382f  lea     rax, [rbp+50h+var_68]
0x180013833  mov     [rsp+1F0h+var_198], rax
0x180013838  lea     rax, [rbp+50h+var_70]
0x18001383c  mov     [rsp+1F0h+var_1A0], rax
0x180013841  lea     rax, [rbp+50h+var_78]
0x180013845  mov     [rsp+1F0h+var_1A8], rax
0x18001384a  lea     rax, [rbp+50h+var_80]
0x18001384e  mov     [rsp+1F0h+var_1B0], rax
0x180013853  lea     rax, [rbp+50h+var_88]
0x180013857  mov     [rsp+1F0h+var_1B8], rax
0x18001385c  lea     rax, [rbp+50h+var_D0]
0x180013860  mov     [rsp+1F0h+var_1C0], rax
0x180013865  lea     rax, [rbp+50h+var_98]
0x180013869  mov     [rsp+1F0h+var_1C8], rax
  ... truncated ...
```
