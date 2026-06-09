# FindServiceLocationRequest(ushort const *,ushort *,ushort * *,bool)

- ea: `0x180025728`
- end: `0x180025a07`
- name: `?FindServiceLocationRequest@@YAJPEBGPEAGPEAPEAG_N@Z`
- size: `735`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180026568`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x180017210`
- `0x180025728`
- `0x1800472d4`
- `0x180047678`
- `0x1800476f0`
- `0x180047c38`
- `0x180047c68`
- `0x180048764`
- `0x180048b20`
- `0x180048edc`
- `0x180049250`
- `0x18004ab54`
- `0x18004ba58`

## string_xrefs

- `0x180025991`: `ServiceLocationResponse`
- `0x1800259ee`: `ServiceLocationResponse`
- `0x180025905`: `ServiceLocationRequest`
- `0x180025934`: `ServiceLocationRequest`
- `0x180025896`: `ServiceNames`
- `0x18002588f`: `http://microsoft.com/DRM/ServiceLocatorService`
- `0x18002586d`: `ServiceLocatorService`
- `0x180025866`: `FindServiceLocationsForUser`
- `0x18002589d`: `FindServiceLocationsForUser`
- `0x18002582e`: `/ServiceLocator.asmx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindServiceLocationRequest(char *a1, unsigned __int16 *a2, unsigned __int16 **a3, char a4)
{
  unsigned __int16 *v7; // r14
  int Request; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned __int64 v12; // r12
  unsigned __int16 *v13; // rax
  __int64 v14; // rax
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // edx
  int v21; // eax
  unsigned __int16 *v22; // rax
  signed __int64 v23; // r15
  int v24; // edx
  int v25; // ecx
  _BYTE v26[40]; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+68h] [rbp-98h]
  void *Block; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 **v29; // [rsp+1A0h] [rbp+A0h]

  v29 = a3;
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v26);
  Block = 0;
  if ( a2 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = v11 + 21;
    v13 = (unsigned __int16 *)operator new[](saturated_mul(v11 + 21, 2u));
    v7 = v13;
    if ( v13 )
    {
      Request = StringCchCopyW(v13, v12, a2);
      if ( Request >= 0 )
      {
        do
          ++v10;
        while ( a2[v10] );
        if ( (unsigned int)v10 > 1 )
        {
          v14 = (unsigned int)(v10 - 1);
          if ( a2[v14] == 47 )
            a2[v14] = 0;
        }
        Request = StringCchCatW(v7, v12, L"/ServiceLocator.asmx");
        if ( Request >= 0 )
        {
          Request = CHttpBase::SetServerInfo((CHttpBase *)v26, v7, 0, v15);
          if ( Request >= 0 )
          {
            Request = CDRMSoapRequest::SetServerMethod(
                        (CDRMSoapRequest *)v26,
                        L"ServiceLocatorService",
                        L"FindServiceLocationsForUser");
            if ( Request >= 0 )
            {
              Request = CDRMSoapRequest::CreateRequest(
                          (CDRMSoapRequest *)v26,
                          L"FindServiceLocationsForUser",
                          L"ServiceNames",
                          L"http://microsoft.com/DRM/ServiceLocatorService",
                          1u);
              if ( Request >= 0 )
              {
                Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v26, v16, v17);
                if ( Request >= 0 )
                {
                  Request = CDRMSoapRequest::AddHeaderParameter(v26, v18, L"MinimumVersion");
                  if ( Request >= 0 )
                  {
                    Request = CDRMSoapRequest::AddHeaderParameter(v26, v19, L"MaximumVersion");
                    if ( Request >= 0 )
                    {
                      Request = CDRMSoapRequest::AddStruct((CDRMSoapRequest *)v26, v20, L"ServiceLocationRequest", 1u);
                      if ( Request >= 0 )
                      {
                        Request = CDRMSoapRequest::AddParam(v26, 1, L"ServiceLocationRequest", L"Type", 3, a1);
                        if ( Request >= 0 )
                        {
                          v21 = v27;
                          if ( a4 )
                            v21 = 16;
                          v27 = v21;
                          Request = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v26, 0, 0);
                          if ( Request >= 0 )
                          {
                            Request = CDRMSoapRequest::GetParameterValue(
                                        (CDRMSoapRequest *)v26,
                                        L"ServiceLocationResponse",
                                        L"Type",
                                        0,
                                        (unsigned __int16 **)&Block);
                            if ( Request >= 0 )
                            {
                              v22 = (unsigned __int16 *)Block;
                              v23 = a1 - (_BYTE *)Block;
                              do
                              {
                                v24 = *(unsigned __int16 *)((char *)v22 + v23);
                                v25 = *v22 - v24;
                                if ( v25 )
                                  break;
                                ++v22;
                              }
                              while ( v24 );
                              if ( v25 )
                                Request = -2147168441;
                              else
                                Request = CDRMSoapRequest::GetParameterValue(
                                            (CDRMSoapRequest *)v26,
                                            L"ServiceLocationResponse",
                                            L"URL",
                                            0,
                                            v29);
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
        }
      }
    }
    else
    {
      Request = -2147024882;
    }
  }
  else
  {
    v7 = 0;
    Request = -2147024809;
  }
  operator delete(v7);
  operator delete(Block);
  Block = 0;
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v26);
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x180025728  mov     rax, rsp
0x18002572b  mov     [rax+18h], r8
0x18002572f  push    rbp
0x180025730  push    rsi
0x180025731  push    rdi
0x180025732  push    r12
0x180025734  push    r13
0x180025736  push    r14
0x180025738  push    r15
0x18002573a  lea     rbp, [rsp-50h]
0x18002573f  sub     rsp, 150h
0x180025746  mov     [rsp+180h+var_150], 0FFFFFFFFFFFFFFFEh
0x18002574f  mov     [rax+8], rbx
0x180025753  mov     r13b, r9b
0x180025756  mov     rsi, rdx
0x180025759  mov     r15, rcx
0x18002575c  lea     rcx, [rsp+180h+var_140]; this
0x180025761  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x180025766  nop
0x180025767  xor     ebx, ebx
0x180025769  mov     [rbp+80h+Block], rbx
0x180025770  test    rsi, rsi
0x180025773  jnz     short loc_1800257C1
0x180025775  mov     r14d, ebx
0x180025778  mov     ebx, 80070057h
0x18002577d  xor     esi, esi
0x18002577f  mov     rcx, r14; Block
0x180025782  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025787  mov     rcx, [rbp+80h+Block]; Block
0x18002578e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025793  mov     [rbp+80h+Block], rsi
0x18002579a  lea     rcx, [rsp+180h+var_140]; this
0x18002579f  call    ??1CDRMSoapRequest@@UEAA@XZ; CDRMSoapRequest::~CDRMSoapRequest(void)
0x1800257a4  mov     eax, ebx
0x1800257a6  mov     rbx, [rsp+180h+arg_0]
0x1800257ae  add     rsp, 150h
0x1800257b5  pop     r15
0x1800257b7  pop     r14
0x1800257b9  pop     r13
0x1800257bb  pop     r12
0x1800257bd  pop     rdi
0x1800257be  pop     rsi
0x1800257bf  pop     rbp
0x1800257c0  retn
0x1800257c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800257c5  mov     rax, rdi
0x1800257c8  inc     rax
0x1800257cb  cmp     [rsi+rax*2], bx
0x1800257cf  jnz     short loc_1800257C8
0x1800257d1  lea     r12, [rax+15h]
0x1800257d5  mov     eax, 2
0x1800257da  mul     r12
0x1800257dd  cmovb   rax, rdi
0x1800257e1  mov     rcx, rax; unsigned __int64
0x1800257e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800257e9  mov     r14, rax
0x1800257ec  test    rax, rax
0x1800257ef  jnz     short loc_1800257F8
0x1800257f1  mov     ebx, 8007000Eh
0x1800257f6  jmp     short loc_18002577D
0x1800257f8  mov     r8, rsi; unsigned __int16 *
0x1800257fb  mov     rdx, r12; unsigned __int64
0x1800257fe  mov     rcx, r14; unsigned __int16 *
0x180025801  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025806  mov     ebx, eax
0x180025808  xor     edx, edx
0x18002580a  test    eax, eax
0x18002580c  js      loc_18002577D
0x180025812  inc     rdi
0x180025815  cmp     [rsi+rdi*2], dx
0x180025819  jnz     short loc_180025812
0x18002581b  cmp     edi, 1
0x18002581e  jbe     short loc_18002582E
0x180025820  lea     eax, [rdi-1]
0x180025823  cmp     word ptr [rsi+rax*2], 2Fh ; '/'
0x180025828  jnz     short loc_18002582E
0x18002582a  mov     [rsi+rax*2], dx
0x18002582e  lea     r8, ?g_wszPUB_ServiceLocatorPadding@@3QBGB; "/ServiceLocator.asmx"
0x180025835  mov     rdx, r12; unsigned __int64
0x180025838  mov     rcx, r14; unsigned __int16 *
0x18002583b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025840  mov     ebx, eax
0x180025842  xor     esi, esi
0x180025844  test    eax, eax
0x180025846  js      loc_18002577F
0x18002584c  xor     r8d, r8d; unsigned int
0x18002584f  mov     rdx, r14; unsigned __int16 *
0x180025852  lea     rcx, [rsp+180h+var_140]; this
0x180025857  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x18002585c  mov     ebx, eax
0x18002585e  test    eax, eax
0x180025860  js      loc_18002577F
0x180025866  lea     r8, ?g_wszPUB_FindServiceLocations@@3QBGB; "FindServiceLocationsForUser"
0x18002586d  lea     rdx, ?g_wszPUB_ServiceLocator@@3QBGB; "ServiceLocatorService"
0x180025874  lea     rcx, [rsp+180h+var_140]; this
0x180025879  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x18002587e  mov     ebx, eax
0x180025880  test    eax, eax
0x180025882  js      loc_18002577F
0x180025888  lea     edi, [rsi+1]
0x18002588b  mov     dword ptr [rsp+180h+var_160], edi; unsigned int
0x18002588f  lea     r9, ?g_wszPUB_ServiceLocatorNamespace@@3QBGB; "http://microsoft.com/DRM/ServiceLocator"...
0x180025896  lea     r8, ?g_wszPUB_ServiceNames@@3QBGB; "ServiceNames"
0x18002589d  lea     rdx, ?g_wszPUB_FindServiceLocations@@3QBGB; "FindServiceLocationsForUser"
0x1800258a4  lea     rcx, [rsp+180h+var_140]; this
0x1800258a9  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x1800258ae  mov     ebx, eax
0x1800258b0  test    eax, eax
0x1800258b2  js      loc_18002577F
0x1800258b8  lea     rcx, [rsp+180h+var_140]; this
0x1800258bd  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x1800258c2  mov     ebx, eax
0x1800258c4  test    eax, eax
0x1800258c6  js      loc_18002577F
0x1800258cc  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x1800258d3  lea     rcx, [rsp+180h+var_140]
0x1800258d8  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800258dd  mov     ebx, eax
0x1800258df  test    eax, eax
0x1800258e1  js      loc_18002577F
0x1800258e7  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x1800258ee  lea     rcx, [rsp+180h+var_140]
0x1800258f3  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800258f8  mov     ebx, eax
0x1800258fa  test    eax, eax
0x1800258fc  js      loc_18002577F
0x180025902  mov     r9d, edi; unsigned int
0x180025905  lea     r8, ?g_wszPUB_ServiceLocationRequest@@3QBGB; "ServiceLocationRequest"
0x18002590c  lea     rcx, [rsp+180h+var_140]; this
0x180025911  call    ?AddStruct@CDRMSoapRequest@@IEAAJHPEBGI@Z; CDRMSoapRequest::AddStruct(int,ushort const *,uint)
0x180025916  mov     ebx, eax
0x180025918  test    eax, eax
0x18002591a  js      loc_18002577F
0x180025920  mov     [rsp+180h+var_158], r15
0x180025925  mov     dword ptr [rsp+180h+var_160], 3
0x18002592d  lea     r9, ?g_wszPUB_Type@@3QBGB; "Type"
0x180025934  lea     r8, ?g_wszPUB_ServiceLocationRequest@@3QBGB; "ServiceLocationRequest"
0x18002593b  mov     edx, edi
0x18002593d  lea     rcx, [rsp+180h+var_140]
0x180025942  call    ?AddParam@CDRMSoapRequest@@IEAAJHPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddParam(int,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x180025947  mov     ebx, eax
0x180025949  test    eax, eax
0x18002594b  js      loc_18002577F
0x180025951  mov     eax, [rsp+180h+var_118]
0x180025955  lea     ecx, [rsi+10h]
0x180025958  test    r13b, r13b
0x18002595b  cmovnz  eax, ecx
0x18002595e  mov     [rsp+180h+var_118], eax
0x180025962  xor     r8d, r8d; unsigned int
0x180025965  xor     edx, edx; unsigned __int8 *
0x180025967  lea     rcx, [rsp+180h+var_140]; this
0x18002596c  call    ?DispatchRequest@CDRMSoapRequest@@UEAAJPEAEI@Z; CDRMSoapRequest::DispatchRequest(uchar *,uint)
0x180025971  mov     ebx, eax
0x180025973  test    eax, eax
0x180025975  js      loc_18002577F
0x18002597b  lea     rax, [rbp+80h+Block]
0x180025982  mov     [rsp+180h+var_160], rax; unsigned __int16 **
0x180025987  xor     r9d, r9d; unsigned int
0x18002598a  lea     r8, ?g_wszPUB_Type@@3QBGB; "Type"
0x180025991  lea     rdx, ?g_wszPUB_ServiceLocationResponse@@3QBGB; "ServiceLocationResponse"
0x180025998  lea     rcx, [rsp+180h+var_140]; this
0x18002599d  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x1800259a2  mov     ebx, eax
0x1800259a4  test    eax, eax
0x1800259a6  js      loc_18002577F
0x1800259ac  mov     rax, [rbp+80h+Block]
0x1800259b3  sub     r15, rax
0x1800259b6  movzx   ecx, word ptr [rax]
0x1800259b9  movzx   edx, word ptr [rax+r15]
0x1800259be  sub     ecx, edx
0x1800259c0  jnz     short loc_1800259CA
0x1800259c2  add     rax, 2
0x1800259c6  test    edx, edx
0x1800259c8  jnz     short loc_1800259B6
0x1800259ca  test    ecx, ecx
0x1800259cc  jz      short loc_1800259D8
0x1800259ce  mov     ebx, 8004CF47h
0x1800259d3  jmp     loc_18002577F
0x1800259d8  mov     rax, [rbp+80h+arg_10]
0x1800259df  mov     [rsp+180h+var_160], rax; unsigned __int16 **
0x1800259e4  xor     r9d, r9d; unsigned int
0x1800259e7  lea     r8, ?g_wszPUB_URL@@3QBGB; "URL"
0x1800259ee  lea     rdx, ?g_wszPUB_ServiceLocationResponse@@3QBGB; "ServiceLocationResponse"
0x1800259f5  lea     rcx, [rsp+180h+var_140]; this
0x1800259fa  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x1800259ff  mov     ebx, eax
0x180025a01  jmp     loc_18002577F
```
