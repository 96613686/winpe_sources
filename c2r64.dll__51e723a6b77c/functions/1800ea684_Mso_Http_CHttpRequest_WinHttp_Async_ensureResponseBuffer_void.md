# Mso::Http::CHttpRequest_WinHttp_Async::ensureResponseBuffer(void)

- ea: `0x1800ea684`
- end: `0x1800ea984`
- name: `?ensureResponseBuffer@CHttpRequest_WinHttp_Async@Http@Mso@@AEAA?AUResult@23@XZ`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1800eb870`

## callees

- `0x18000ffb0`
- `0x180010a84`
- `0x18001c6b4`
- `0x18001c760`
- `0x18002acd8`
- `0x18008cfc4`
- `0x1800da9a8`
- `0x1800dfbf4`
- `0x1800e8744`
- `0x1800ea684`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ea76d`
- `KERNEL32!GetLastError` at `0x1800ea88b`
- `KERNEL32!GetLastError` at `0x1800ea76d`
- `KERNEL32!GetLastError` at `0x1800ea88b`
- `WINHTTP!WinHttpReadData` at `0x1800ea84a`
- `WINHTTP!WinHttpReadData` at `0x1800ea84a`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800ea753`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800ea753`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::Http::CHttpRequest_WinHttp_Async::ensureResponseBuffer(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v6; // rax
  unsigned int i; // r12d
  void *v8; // rcx
  __int64 v9; // rax
  int v10; // r14d
  __int64 v11; // xmm1_8
  int v12; // eax
  int *v13; // rax
  DWORD LastError; // eax
  DWORD v15; // r15d
  void *v16; // rdx
  unsigned __int64 v17; // rbx
  char *v18; // r14
  char *v19; // rax
  size_t v20; // rbx
  int *v21; // rax
  void *v22; // rax
  BOOL v23; // ebx
  DWORD v24; // eax
  __int64 v25; // xmm1_8
  char *v26; // r15
  char *v27; // rax
  size_t v28; // rbx
  void *v30[2]; // [rsp+20h] [rbp-69h] BYREF
  __int64 v31; // [rsp+30h] [rbp-59h]
  __int64 v32; // [rsp+38h] [rbp-51h]
  int v33; // [rsp+40h] [rbp-49h] BYREF
  __int64 v34; // [rsp+48h] [rbp-41h]
  __int64 v35; // [rsp+50h] [rbp-39h]
  _BYTE v36[16]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v37; // [rsp+70h] [rbp-19h]
  _QWORD v38[2]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v39[80]; // [rsp+90h] [rbp+7h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+F0h] [rbp+67h] BYREF
  int v41; // [rsp+100h] [rbp+77h]
  DWORD dwNumberOfBytesRead; // [rsp+108h] [rbp+7Fh] BYREF

  if ( !*(_BYTE *)(a1 + 164) )
  {
    if ( !*(_BYTE *)(a1 + 25) )
    {
      v4 = Mso::Http::Results::InvalidStateError(v36, a2, 42497757);
      Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(a1, a2, v4);
      return a2;
    }
    v5 = a1 + 136;
    v6 = *(_QWORD *)(a1 + 136);
    if ( v6 != *(_QWORD *)(a1 + 144) )
      *(_QWORD *)(a1 + 144) = v6;
    *(_DWORD *)(a1 + 160) = 0;
    *(_OWORD *)v30 = 0;
    v31 = 0;
    for ( i = 0; ; i += dwNumberOfBytesRead )
    {
      dwNumberOfBytesAvailable = 0;
      v8 = *(void **)(a1 + 120);
      if ( v8 )
      {
        if ( WinHttpQueryDataAvailable(v8, &dwNumberOfBytesAvailable) )
        {
          v33 = 0;
          v34 = 0;
          LODWORD(v35) = 0;
          v13 = &v33;
        }
        else
        {
          LastError = GetLastError();
          v13 = (int *)Mso::Http::ConvertDwToResult(v39, LastError, 42296770);
        }
        v37 = *((_QWORD *)v13 + 2);
        v10 = *v13;
        v11 = *((_QWORD *)v13 + 1);
        v12 = v37;
      }
      else
      {
        v9 = Mso::Http::Results::InvalidStateError(v36, a2, 42497758);
        v35 = *(_QWORD *)(v9 + 16);
        v10 = *(_DWORD *)v9;
        v11 = *(_QWORD *)(v9 + 8);
        v12 = v35;
      }
      v41 = v12;
      v32 = v11;
      if ( v10 )
      {
LABEL_38:
        *(_BYTE *)(a1 + 164) = 1;
        *(_DWORD *)(a1 + 264) = v10;
        *(_QWORD *)(a1 + 272) = v32;
        *(_DWORD *)(a1 + 280) = v41;
        Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(a1, a2, a1 + 264);
        std::vector<unsigned char>::~vector<unsigned char>(v30);
        return a2;
      }
      v15 = dwNumberOfBytesAvailable;
      v16 = v30[0];
      if ( !dwNumberOfBytesAvailable )
      {
        v26 = (char *)v30[1];
        if ( (void *)i < (void *)((char *)v30[1] - (char *)v30[0]) )
        {
          v27 = (char *)v30[0] + i;
          goto LABEL_36;
        }
        if ( (void *)i > (void *)((char *)v30[1] - (char *)v30[0]) )
        {
          if ( i <= v31 - (unsigned __int64)v30[0] )
          {
            v28 = i - (unsigned __int64)((char *)v30[1] - (char *)v30[0]);
            memset(v30[1], 0, v28);
            v27 = &v26[v28];
LABEL_36:
            v30[1] = v27;
          }
          else
          {
            _mm_lfence();
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v30);
          }
        }
        std::vector<unsigned char>::operator=(v5, v30);
        *(_DWORD *)(a1 + 160) = i;
        goto LABEL_38;
      }
      v17 = dwNumberOfBytesAvailable + i;
      v18 = (char *)v30[1];
      if ( v17 >= (char *)v30[1] - (char *)v30[0] )
      {
        if ( v17 <= (char *)v30[1] - (char *)v30[0] )
          goto LABEL_23;
        if ( v17 > v31 - (unsigned __int64)v30[0] )
        {
          _mm_lfence();
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v30);
          v15 = dwNumberOfBytesAvailable;
          goto LABEL_23;
        }
        v20 = v17 - ((char *)v30[1] - (char *)v30[0]);
        memset(v30[1], 0, v20);
        v19 = &v18[v20];
        v15 = dwNumberOfBytesAvailable;
      }
      else
      {
        v19 = (char *)v30[0] + dwNumberOfBytesAvailable + i;
      }
      v30[1] = v19;
LABEL_23:
      dwNumberOfBytesRead = 0;
      if ( *(_QWORD *)(a1 + 120) )
      {
        v22 = (void *)std::vector<unsigned char>::operator[](v30, i);
        v23 = WinHttpReadData(*(HINTERNET *)(a1 + 120), v22, v15, &dwNumberOfBytesRead);
        std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
          v38,
          a1 + 168);
        *(_DWORD *)(v38[0] + 20LL) += dwNumberOfBytesRead;
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v38);
        if ( v23 )
        {
          v33 = 0;
          v34 = 0;
          LODWORD(v35) = 0;
          v21 = &v33;
        }
        else
        {
          v24 = GetLastError();
          v21 = (int *)Mso::Http::ConvertDwToResult(v39, v24, 42296771);
        }
      }
      else
      {
        v21 = (int *)Mso::Http::Results::InvalidStateError(v39, v16, 42497759);
      }
      v10 = *v21;
      v25 = *((_QWORD *)v21 + 1);
      v37 = *((_QWORD *)v21 + 2);
      v41 = v37;
      v32 = v25;
      if ( v10 )
        goto LABEL_38;
    }
  }
  *(_OWORD *)a2 = *(_OWORD *)(a1 + 264);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 280);
  return a2;
}

```

## disassembly

```asm
0x1800ea684  mov     [rsp-8+arg_8], rbx
0x1800ea689  push    rbp
0x1800ea68a  push    rsi
0x1800ea68b  push    rdi
0x1800ea68c  push    r12
0x1800ea68e  push    r13
0x1800ea690  push    r14
0x1800ea692  push    r15
0x1800ea694  lea     rbp, [rsp-27h]
0x1800ea699  sub     rsp, 0B0h
0x1800ea6a0  mov     rsi, rdx
0x1800ea6a3  mov     rdi, rcx
0x1800ea6a6  xor     ebx, ebx
0x1800ea6a8  cmp     [rcx+0A4h], bl
0x1800ea6ae  jz      short loc_1800EA6CC
0x1800ea6b0  movups  xmm0, xmmword ptr [rcx+108h]
0x1800ea6b7  movups  xmmword ptr [rdx], xmm0
0x1800ea6ba  movsd   xmm1, qword ptr [rcx+118h]
0x1800ea6c2  movsd   qword ptr [rdx+10h], xmm1
0x1800ea6c7  jmp     loc_1800EA966
0x1800ea6cc  cmp     [rcx+19h], bl
0x1800ea6cf  jnz     short loc_1800EA6F3
0x1800ea6d1  mov     r8d, 28876DDh
0x1800ea6d7  lea     rcx, [rbp+57h+var_80]
0x1800ea6db  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800ea6e0  mov     r8, rax
0x1800ea6e3  mov     rdx, rsi
0x1800ea6e6  mov     rcx, rdi
0x1800ea6e9  call    ?HandleResult@CHttpRequest_WinHttp_Async@Http@Mso@@QEAA?AUResult@23@AEBU423@@Z; Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(Mso::Http::Result const &)
0x1800ea6ee  jmp     loc_1800EA966
0x1800ea6f3  lea     r13, [rcx+88h]
0x1800ea6fa  mov     rax, [r13+0]
0x1800ea6fe  cmp     rax, [r13+8]
0x1800ea702  jz      short loc_1800EA708
0x1800ea704  mov     [r13+8], rax
0x1800ea708  mov     [rcx+0A0h], ebx
0x1800ea70e  xorps   xmm0, xmm0
0x1800ea711  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800ea716  mov     [rbp+57h+var_B0], rbx
0x1800ea71a  mov     r12d, ebx
0x1800ea71d  mov     [rbp+57h+dwNumberOfBytesAvailable], ebx
0x1800ea720  mov     rcx, [rdi+78h]; hRequest
0x1800ea724  test    rcx, rcx
0x1800ea727  jnz     short loc_1800EA74F
0x1800ea729  mov     r8d, 28876DEh
0x1800ea72f  lea     rcx, [rbp+57h+var_80]
0x1800ea733  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800ea738  movsd   xmm0, qword ptr [rax+10h]
0x1800ea73d  movsd   [rbp+57h+var_90], xmm0
0x1800ea742  mov     r14d, [rax]
0x1800ea745  movq    xmm1, qword ptr [rax+8]
0x1800ea74a  mov     eax, dword ptr [rbp+57h+var_90]
0x1800ea74d  jmp     short loc_1800EA799
0x1800ea74f  lea     rdx, [rbp+57h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800ea753  call    cs:__imp_WinHttpQueryDataAvailable
0x1800ea759  test    eax, eax
0x1800ea75b  jz      short loc_1800EA76D
0x1800ea75d  mov     [rbp+57h+var_A0], ebx
0x1800ea760  mov     [rbp+57h+var_98], rbx
0x1800ea764  mov     dword ptr [rbp+57h+var_90], ebx
0x1800ea767  lea     rax, [rbp+57h+var_A0]
0x1800ea76b  jmp     short loc_1800EA784
0x1800ea76d  call    cs:__imp_GetLastError
0x1800ea773  mov     r8d, 28565C2h
0x1800ea779  mov     edx, eax
0x1800ea77b  lea     rcx, [rbp+57h+var_50]
0x1800ea77f  call    ?ConvertDwToResult@Http@Mso@@YA?AUResult@12@KI@Z; Mso::Http::ConvertDwToResult(ulong,uint)
0x1800ea784  movsd   xmm0, qword ptr [rax+10h]
0x1800ea789  movsd   [rbp+57h+var_70], xmm0
0x1800ea78e  mov     r14d, [rax]
0x1800ea791  movq    xmm1, qword ptr [rax+8]
0x1800ea796  mov     eax, dword ptr [rbp+57h+var_70]
0x1800ea799  mov     [rbp+57h+arg_10], eax
0x1800ea79c  movq    [rbp+57h+var_A8], xmm1
0x1800ea7a1  test    r14d, r14d
0x1800ea7a4  jnz     loc_1800EA931
0x1800ea7aa  mov     r15d, [rbp+57h+dwNumberOfBytesAvailable]
0x1800ea7ae  mov     rdx, [rbp+57h+var_C0]
0x1800ea7b2  test    r15d, r15d
0x1800ea7b5  jz      loc_1800EA8CF
0x1800ea7bb  lea     eax, [r15+r12]
0x1800ea7bf  mov     ebx, eax
0x1800ea7c1  mov     r14, [rbp+57h+var_C0+8]
0x1800ea7c5  mov     rcx, r14
0x1800ea7c8  sub     rcx, rdx
0x1800ea7cb  cmp     rbx, rcx
0x1800ea7ce  jnb     short loc_1800EA7D5
0x1800ea7d0  add     rax, rdx
0x1800ea7d3  jmp     short loc_1800EA810
0x1800ea7d5  jbe     short loc_1800EA814
0x1800ea7d7  mov     rax, [rbp+57h+var_B0]
0x1800ea7db  sub     rax, rdx
0x1800ea7de  cmp     rbx, rax
0x1800ea7e1  jbe     short loc_1800EA7F8
0x1800ea7e3  lfence
0x1800ea7e6  mov     rdx, rbx
0x1800ea7e9  lea     rcx, [rbp+57h+var_C0]
0x1800ea7ed  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ea7f2  mov     r15d, [rbp+57h+dwNumberOfBytesAvailable]
0x1800ea7f6  jmp     short loc_1800EA814
0x1800ea7f8  sub     rbx, rcx
0x1800ea7fb  mov     r8, rbx; Size
0x1800ea7fe  xor     edx, edx; Val
0x1800ea800  mov     rcx, r14; void *
0x1800ea803  call    memset
0x1800ea808  lea     rax, [r14+rbx]
0x1800ea80c  mov     r15d, [rbp+57h+dwNumberOfBytesAvailable]
0x1800ea810  mov     [rbp+57h+var_C0+8], rax
0x1800ea814  xor     ebx, ebx
0x1800ea816  mov     [rbp+57h+dwNumberOfBytesRead], ebx
0x1800ea819  cmp     [rdi+78h], rbx
0x1800ea81d  jnz     short loc_1800EA830
0x1800ea81f  mov     r8d, 28876DFh
0x1800ea825  lea     rcx, [rbp+57h+var_50]
0x1800ea829  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800ea82e  jmp     short loc_1800EA8A4
0x1800ea830  mov     edx, r12d
0x1800ea833  lea     rcx, [rbp+57h+var_C0]
0x1800ea837  call    ??A?$vector@EV?$allocator@E@std@@@std@@QEAAAEAE_K@Z; std::vector<uchar>::operator[](unsigned __int64)
0x1800ea83c  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800ea840  mov     r8d, r15d; dwNumberOfBytesToRead
0x1800ea843  mov     rdx, rax; lpBuffer
0x1800ea846  mov     rcx, [rdi+78h]; hRequest
0x1800ea84a  call    cs:__imp_WinHttpReadData
0x1800ea850  mov     ebx, eax
0x1800ea852  lea     rdx, [rdi+0A8h]
0x1800ea859  lea     rcx, [rbp+57h+var_60]
0x1800ea85d  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x1800ea862  mov     rdx, [rbp+57h+var_60]
0x1800ea866  mov     ecx, [rbp+57h+dwNumberOfBytesRead]
0x1800ea869  add     [rdx+14h], ecx
0x1800ea86c  lea     rcx, [rbp+57h+var_60]; void *
0x1800ea870  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800ea875  test    ebx, ebx
0x1800ea877  jz      short loc_1800EA88B
0x1800ea879  xor     ebx, ebx
0x1800ea87b  mov     [rbp+57h+var_A0], ebx
0x1800ea87e  mov     [rbp+57h+var_98], rbx
0x1800ea882  mov     dword ptr [rbp+57h+var_90], ebx
0x1800ea885  lea     rax, [rbp+57h+var_A0]
0x1800ea889  jmp     short loc_1800EA8A4
0x1800ea88b  call    cs:__imp_GetLastError
0x1800ea891  mov     r8d, 28565C3h
0x1800ea897  mov     edx, eax
0x1800ea899  lea     rcx, [rbp+57h+var_50]
0x1800ea89d  call    ?ConvertDwToResult@Http@Mso@@YA?AUResult@12@KI@Z; Mso::Http::ConvertDwToResult(ulong,uint)
0x1800ea8a2  xor     ebx, ebx
0x1800ea8a4  movsd   xmm0, qword ptr [rax+10h]
0x1800ea8a9  mov     r14d, [rax]
0x1800ea8ac  movq    xmm1, qword ptr [rax+8]
0x1800ea8b1  movsd   [rbp+57h+var_70], xmm0
0x1800ea8b6  mov     eax, dword ptr [rbp+57h+var_70]
0x1800ea8b9  mov     [rbp+57h+arg_10], eax
0x1800ea8bc  movq    [rbp+57h+var_A8], xmm1
0x1800ea8c1  test    r14d, r14d
0x1800ea8c4  jnz     short loc_1800EA931
0x1800ea8c6  add     r12d, [rbp+57h+dwNumberOfBytesRead]
0x1800ea8ca  jmp     loc_1800EA71D
0x1800ea8cf  mov     ebx, r12d
0x1800ea8d2  mov     r15, [rbp+57h+var_C0+8]
0x1800ea8d6  mov     rcx, r15
0x1800ea8d9  sub     rcx, rdx
0x1800ea8dc  cmp     rbx, rcx
0x1800ea8df  jnb     short loc_1800EA8E7
0x1800ea8e1  lea     rax, [rdx+rbx]
0x1800ea8e5  jmp     short loc_1800EA91A
0x1800ea8e7  jbe     short loc_1800EA91E
0x1800ea8e9  mov     rax, [rbp+57h+var_B0]
0x1800ea8ed  sub     rax, rdx
0x1800ea8f0  cmp     rbx, rax
0x1800ea8f3  jbe     short loc_1800EA906
0x1800ea8f5  lfence
0x1800ea8f8  mov     rdx, rbx
0x1800ea8fb  lea     rcx, [rbp+57h+var_C0]
0x1800ea8ff  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ea904  jmp     short loc_1800EA91E
0x1800ea906  sub     rbx, rcx
0x1800ea909  mov     r8, rbx; Size
0x1800ea90c  xor     edx, edx; Val
0x1800ea90e  mov     rcx, r15; void *
0x1800ea911  call    memset
0x1800ea916  lea     rax, [rbx+r15]
0x1800ea91a  mov     [rbp+57h+var_C0+8], rax
0x1800ea91e  lea     rdx, [rbp+57h+var_C0]
0x1800ea922  mov     rcx, r13
0x1800ea925  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800ea92a  mov     [rdi+0A0h], r12d
0x1800ea931  mov     byte ptr [rdi+0A4h], 1
0x1800ea938  lea     r8, [rdi+108h]
0x1800ea93f  mov     [r8], r14d
0x1800ea942  mov     rax, [rbp+57h+var_A8]
0x1800ea946  mov     [r8+8], rax
0x1800ea94a  mov     eax, [rbp+57h+arg_10]
0x1800ea94d  mov     [r8+10h], eax
0x1800ea951  mov     rdx, rsi
0x1800ea954  mov     rcx, rdi
0x1800ea957  call    ?HandleResult@CHttpRequest_WinHttp_Async@Http@Mso@@QEAA?AUResult@23@AEBU423@@Z; Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(Mso::Http::Result const &)
0x1800ea95c  nop
0x1800ea95d  lea     rcx, [rbp+57h+var_C0]
0x1800ea961  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800ea966  mov     rax, rsi
0x1800ea969  mov     rbx, [rsp+0E0h+arg_8]
0x1800ea971  add     rsp, 0B0h
0x1800ea978  pop     r15
0x1800ea97a  pop     r14
0x1800ea97c  pop     r13
0x1800ea97e  pop     r12
0x1800ea980  pop     rdi
0x1800ea981  pop     rsi
0x1800ea982  pop     rbp
0x1800ea983  retn
```
