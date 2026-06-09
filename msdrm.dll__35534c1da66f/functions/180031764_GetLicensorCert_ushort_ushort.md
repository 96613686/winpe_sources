# GetLicensorCert(ushort *,ushort * *)

- ea: `0x180031764`
- end: `0x180031b54`
- name: `?GetLicensorCert@@YAJPEAGPEAPEAG@Z`
- size: `1008`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180005fc0`
- `0x18002cb38`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004654`
- `0x180017210`
- `0x180031764`
- `0x1800472d4`
- `0x180047678`
- `0x1800476f0`
- `0x180047c38`
- `0x180048b20`
- `0x180048edc`
- `0x180049250`
- `0x18004ab54`
- `0x18004ac50`
- `0x18004ba58`
- `0x18005bd72`

## string_xrefs

- `0x18003187b`: `http://microsoft.com/DRM/ServerService`
- `0x180031858`: `ServerService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLicensorCert(unsigned __int16 *a1, unsigned __int16 **a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r12
  int Request; // ebx
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // r14d
  unsigned int v17; // esi
  void *v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // r13
  unsigned __int16 *v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  bool v24; // zf
  unsigned __int16 *v25; // r14
  unsigned int v26; // esi
  void *v27; // rcx
  __int16 v28; // r11
  __int64 v29; // rax
  _BYTE v31[272]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+198h] [rbp+90h] BYREF
  void *Block; // [rsp+1A0h] [rbp+98h] BYREF

  if ( (unsigned __int8)DRMIsValidStringT<unsigned short>(a1, 0, a3, a4) && a2 )
  {
    CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v31);
    v32 = 0;
    Block = 0;
    *a2 = 0;
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = v6 + 13;
    v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 13, 2u));
    v9 = v8;
    if ( v8 )
    {
      Request = StringCchCopyW(v8, v7, a1);
      if ( Request >= 0 )
      {
        Request = StringCchCatW(v9, v7, L"/server.asmx");
        if ( Request >= 0 )
        {
          Request = CHttpBase::SetServerInfo((CHttpBase *)v31, v9, 0, v11);
          if ( Request >= 0 )
          {
            Request = CDRMSoapRequest::SetServerMethod(
                        (CDRMSoapRequest *)v31,
                        L"ServerService",
                        L"GetLicensorCertificate");
            if ( Request >= 0 )
            {
              Request = CDRMSoapRequest::CreateRequest(
                          (CDRMSoapRequest *)v31,
                          L"GetLicensorCertificate",
                          0,
                          L"http://microsoft.com/DRM/ServerService",
                          1u);
              if ( Request >= 0 )
              {
                Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v31, v12, v13);
                if ( Request >= 0 )
                {
                  Request = CDRMSoapRequest::AddHeaderParameter(v31, v14, L"MinimumVersion");
                  if ( Request >= 0 )
                  {
                    Request = CDRMSoapRequest::AddHeaderParameter(v31, v15, L"MaximumVersion");
                    if ( Request >= 0 )
                    {
                      Request = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v31, 0, 0);
                      if ( Request >= 0 )
                      {
                        Request = CDRMSoapRequest::GetParameterValueCount(
                                    (CDRMSoapRequest *)v31,
                                    0,
                                    L"CertificateChain",
                                    &v32);
                        if ( Request >= 0 )
                        {
                          v16 = 0;
                          v17 = 0;
                          if ( v32 )
                          {
                            v18 = Block;
                            while ( 1 )
                            {
                              operator delete(v18);
                              Block = 0;
                              Request = CDRMSoapRequest::GetParameterValue(
                                          (CDRMSoapRequest *)v31,
                                          0,
                                          L"CertificateChain",
                                          v17,
                                          (unsigned __int16 **)&Block);
                              if ( Request < 0 )
                                break;
                              v18 = Block;
                              v19 = -1;
                              do
                                ++v19;
                              while ( *((_WORD *)Block + v19) );
                              v16 += v19;
                              if ( ++v17 >= v32 )
                                goto LABEL_23;
                            }
                          }
                          else
                          {
LABEL_23:
                            v20 = (unsigned int)(v16 + 1);
                            v21 = (unsigned __int16 *)operator new(saturated_mul(v20, 2u));
                            *a2 = v21;
                            if ( v21 )
                            {
                              memset_0(v21, 0, 2 * v20);
                              v25 = *a2;
                              v26 = 0;
                              if ( !v32 )
                                goto LABEL_48;
                              v27 = Block;
                              while ( 1 )
                              {
                                operator delete(v27);
                                Block = 0;
                                Request = CDRMSoapRequest::GetParameterValue(
                                            (CDRMSoapRequest *)v31,
                                            0,
                                            L"CertificateChain",
                                            v26,
                                            (unsigned __int16 **)&Block);
                                if ( Request < 0 )
                                  break;
                                Request = StringCchCopyW(v25, v20 - (v25 - *a2), (const unsigned __int16 *)Block);
                                if ( Request < 0 )
                                  break;
                                v27 = Block;
                                v29 = -1;
                                do
                                  ++v29;
                                while ( *((_WORD *)Block + v29) != v28 );
                                v25 += v29;
                                if ( ++v26 >= v32 )
                                  goto LABEL_48;
                              }
                            }
                            else
                            {
                              Request = -2147024882;
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
    operator delete(*a2);
    *a2 = 0;
    if ( Request <= -2147168421 )
    {
      v22 = (unsigned int)(Request + 2147168453);
      if ( (unsigned int)v22 <= 0x20 )
      {
        v23 = 0x100000041LL;
        if ( _bittest64(&v23, v22) )
          goto LABEL_48;
      }
      if ( Request != -2147168444 )
      {
        if ( Request != -2147168441 )
        {
          v24 = Request == -2147168438;
          goto LABEL_44;
        }
        goto LABEL_47;
      }
LABEL_46:
      Request = -2147168444;
      goto LABEL_48;
    }
    if ( Request != -2147168420 )
    {
      if ( Request == -2147168304 )
      {
LABEL_47:
        Request = -2147168441;
        goto LABEL_48;
      }
      if ( Request == -2147168300 )
        goto LABEL_46;
      if ( Request != -2147024882 )
      {
        v24 = Request == -2147024809;
LABEL_44:
        if ( !v24 )
          Request = -2147467259;
      }
    }
LABEL_48:
    operator delete(v9);
    operator delete(Block);
    CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v31);
    return (unsigned int)Request;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180031764  mov     rax, rsp
0x180031767  push    rbp
0x180031768  push    rdi
0x180031769  push    r12
0x18003176b  push    r13
0x18003176d  push    r14
0x18003176f  lea     rbp, [rax-78h]
0x180031773  sub     rsp, 150h
0x18003177a  mov     [rsp+170h+var_140], 0FFFFFFFFFFFFFFFEh
0x180031783  mov     [rax+8], rbx
0x180031787  mov     [rax+10h], rsi
0x18003178b  mov     rdi, rdx
0x18003178e  mov     rbx, rcx
0x180031791  xor     edx, edx
0x180031793  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031798  xor     r13d, r13d
0x18003179b  test    al, al
0x18003179d  jz      loc_180031B33
0x1800317a3  test    rdi, rdi
0x1800317a6  jz      loc_180031B33
0x1800317ac  lea     rcx, [rsp+170h+var_130]; this
0x1800317b1  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x1800317b6  nop
0x1800317b7  mov     [rbp+70h+arg_10], r13d
0x1800317be  mov     [rbp+70h+Block], r13
0x1800317c5  mov     [rdi], r13
0x1800317c8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800317cc  mov     rax, rcx
0x1800317cf  inc     rax
0x1800317d2  cmp     [rbx+rax*2], r13w
0x1800317d7  jnz     short loc_1800317CF
0x1800317d9  lea     rsi, [rax+0Dh]
0x1800317dd  mov     eax, 2
0x1800317e2  mul     rsi
0x1800317e5  cmovb   rax, rcx
0x1800317e9  mov     rcx, rax; Size
0x1800317ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800317f1  mov     r12, rax
0x1800317f4  test    rax, rax
0x1800317f7  jnz     short loc_180031803
0x1800317f9  mov     ebx, 8007000Eh
0x1800317fe  jmp     loc_1800319C5
0x180031803  mov     r8, rbx; unsigned __int16 *
0x180031806  mov     rdx, rsi; unsigned __int64
0x180031809  mov     rcx, r12; unsigned __int16 *
0x18003180c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031811  mov     ebx, eax
0x180031813  test    eax, eax
0x180031815  js      loc_1800319C5
0x18003181b  lea     r8, ?g_wszPUB_ServerServicePadding@@3QBGB; "/server.asmx"
0x180031822  mov     rdx, rsi; unsigned __int64
0x180031825  mov     rcx, r12; unsigned __int16 *
0x180031828  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003182d  mov     ebx, eax
0x18003182f  test    eax, eax
0x180031831  js      loc_1800319C5
0x180031837  xor     r8d, r8d; unsigned int
0x18003183a  mov     rdx, r12; unsigned __int16 *
0x18003183d  lea     rcx, [rsp+170h+var_130]; this
0x180031842  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x180031847  mov     ebx, eax
0x180031849  test    eax, eax
0x18003184b  js      loc_1800319C5
0x180031851  lea     r8, ?g_wszPUB_GetLicensorCert@@3QBGB; "GetLicensorCertificate"
0x180031858  lea     rdx, ?g_wszPUB_ServerService@@3QBGB; "ServerService"
0x18003185f  lea     rcx, [rsp+170h+var_130]; this
0x180031864  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x180031869  mov     ebx, eax
0x18003186b  test    eax, eax
0x18003186d  js      loc_1800319C5
0x180031873  mov     dword ptr [rsp+170h+var_150], 1; unsigned int
0x18003187b  lea     r9, ?g_wszPUB_ServerServiceNamespace@@3QBGB; "http://microsoft.com/DRM/ServerService"
0x180031882  xor     r8d, r8d; unsigned __int16 *
0x180031885  lea     rdx, ?g_wszPUB_GetLicensorCert@@3QBGB; "GetLicensorCertificate"
0x18003188c  lea     rcx, [rsp+170h+var_130]; this
0x180031891  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x180031896  mov     ebx, eax
0x180031898  test    eax, eax
0x18003189a  js      loc_1800319C5
0x1800318a0  lea     rcx, [rsp+170h+var_130]; this
0x1800318a5  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x1800318aa  mov     ebx, eax
0x1800318ac  test    eax, eax
0x1800318ae  js      loc_1800319C5
0x1800318b4  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x1800318bb  lea     rcx, [rsp+170h+var_130]
0x1800318c0  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800318c5  mov     ebx, eax
0x1800318c7  test    eax, eax
0x1800318c9  js      loc_1800319C5
0x1800318cf  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x1800318d6  lea     rcx, [rsp+170h+var_130]
0x1800318db  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800318e0  mov     ebx, eax
0x1800318e2  test    eax, eax
0x1800318e4  js      loc_1800319C5
0x1800318ea  xor     r8d, r8d; unsigned int
0x1800318ed  xor     edx, edx; unsigned __int8 *
0x1800318ef  lea     rcx, [rsp+170h+var_130]; this
0x1800318f4  call    ?DispatchRequest@CDRMSoapRequest@@UEAAJPEAEI@Z; CDRMSoapRequest::DispatchRequest(uchar *,uint)
0x1800318f9  mov     ebx, eax
0x1800318fb  test    eax, eax
0x1800318fd  js      loc_1800319C5
0x180031903  lea     r9, [rbp+70h+arg_10]; unsigned int *
0x18003190a  lea     r8, ?g_wszPUB_CertificateChain@@3QBGB; "CertificateChain"
0x180031911  xor     edx, edx; unsigned __int16 *
0x180031913  lea     rcx, [rsp+170h+var_130]; this
0x180031918  call    ?GetParameterValueCount@CDRMSoapRequest@@QEAAJPEBG0PEAI@Z; CDRMSoapRequest::GetParameterValueCount(ushort const *,ushort const *,uint *)
0x18003191d  mov     ebx, eax
0x18003191f  test    eax, eax
0x180031921  js      loc_1800319C5
0x180031927  mov     r14d, r13d
0x18003192a  mov     esi, r13d
0x18003192d  cmp     [rbp+70h+arg_10], r13d
0x180031934  jbe     short loc_180031996
0x180031936  mov     rax, [rbp+70h+Block]
0x18003193d  mov     rcx, rax; Block
0x180031940  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031945  mov     [rbp+70h+Block], r13
0x18003194c  lea     rax, [rbp+70h+Block]
0x180031953  mov     [rsp+170h+var_150], rax; unsigned __int16 **
0x180031958  mov     r9d, esi; unsigned int
0x18003195b  lea     r8, ?g_wszPUB_CertificateChain@@3QBGB; "CertificateChain"
0x180031962  xor     edx, edx; unsigned __int16 *
0x180031964  lea     rcx, [rsp+170h+var_130]; this
0x180031969  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x18003196e  mov     ebx, eax
0x180031970  test    eax, eax
0x180031972  js      short loc_1800319C5
0x180031974  mov     rax, [rbp+70h+Block]
0x18003197b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003197f  inc     rcx
0x180031982  cmp     [rax+rcx*2], r13w
0x180031987  jnz     short loc_18003197F
0x180031989  add     r14d, ecx
0x18003198c  inc     esi
0x18003198e  cmp     esi, [rbp+70h+arg_10]
0x180031994  jb      short loc_18003193D
0x180031996  lea     r13d, [r14+1]
0x18003199a  mov     eax, 2
0x18003199f  mul     r13
0x1800319a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800319a9  cmovb   rax, rcx
0x1800319ad  mov     rcx, rax; Size
0x1800319b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800319b5  mov     [rdi], rax
0x1800319b8  test    rax, rax
0x1800319bb  jnz     short loc_180031A20
0x1800319bd  mov     ebx, 8007000Eh
0x1800319c2  xor     r13d, r13d
0x1800319c5  mov     rcx, [rdi]; Block
0x1800319c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800319cd  mov     [rdi], r13
0x1800319d0  mov     edx, 8004CF47h
0x1800319d5  lea     r8d, [rdx-3]
0x1800319d9  cmp     ebx, 8004CF5Bh
0x1800319df  jg      loc_180031ADA
0x1800319e5  lea     eax, [rbx+7FFB30C5h]
0x1800319eb  cmp     eax, 20h ; ' '
0x1800319ee  ja      short loc_180031A04
0x1800319f0  mov     rcx, 100000041h
0x1800319fa  bt      rcx, rax
0x1800319fe  jb      loc_180031B10
0x180031a04  cmp     ebx, r8d
0x180031a07  jz      loc_180031B09
0x180031a0d  cmp     ebx, edx
0x180031a0f  jz      loc_180031B0E
0x180031a15  cmp     ebx, 8004CF4Ah
0x180031a1b  jmp     loc_180031B00
0x180031a20  lea     r8, ds:0[r13*2]; Size
0x180031a28  xor     edx, edx; Val
0x180031a2a  mov     rcx, rax; void *
0x180031a2d  call    memset_0
0x180031a32  mov     r14, [rdi]
0x180031a35  xor     esi, esi
0x180031a37  cmp     [rbp+70h+arg_10], esi
0x180031a3d  jbe     loc_180031B10
0x180031a43  mov     rcx, [rbp+70h+Block]; Block
0x180031a4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031a4f  mov     [rbp+70h+Block], 0
0x180031a5a  lea     rax, [rbp+70h+Block]
0x180031a61  mov     [rsp+170h+var_150], rax; unsigned __int16 **
0x180031a66  mov     r9d, esi; unsigned int
0x180031a69  lea     r8, ?g_wszPUB_CertificateChain@@3QBGB; "CertificateChain"
0x180031a70  xor     edx, edx; unsigned __int16 *
0x180031a72  lea     rcx, [rsp+170h+var_130]; this
0x180031a77  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x180031a7c  mov     ebx, eax
0x180031a7e  xor     r11d, r11d
0x180031a81  test    eax, eax
0x180031a83  js      loc_1800319C2
0x180031a89  mov     rax, r14
0x180031a8c  sub     rax, [rdi]
0x180031a8f  sar     rax, 1
0x180031a92  mov     rdx, r13
0x180031a95  sub     rdx, rax; unsigned __int64
0x180031a98  mov     r8, [rbp+70h+Block]; unsigned __int16 *
0x180031a9f  mov     rcx, r14; unsigned __int16 *
0x180031aa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031aa7  mov     ebx, eax
0x180031aa9  test    eax, eax
0x180031aab  js      loc_1800319C2
0x180031ab1  mov     rcx, [rbp+70h+Block]
0x180031ab8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031abc  inc     rax
0x180031abf  cmp     [rcx+rax*2], r11w
0x180031ac4  jnz     short loc_180031ABC
0x180031ac6  lea     r14, [r14+rax*2]
0x180031aca  inc     esi
0x180031acc  cmp     esi, [rbp+70h+arg_10]
0x180031ad2  jb      loc_180031A4A
0x180031ad8  jmp     short loc_180031B10
0x180031ada  cmp     ebx, 8004CF5Ch
0x180031ae0  jz      short loc_180031B10
0x180031ae2  cmp     ebx, 8004CFD0h
0x180031ae8  jz      short loc_180031B0E
0x180031aea  cmp     ebx, 8004CFD4h
0x180031af0  jz      short loc_180031B09
0x180031af2  cmp     ebx, 8007000Eh
0x180031af8  jz      short loc_180031B10
0x180031afa  cmp     ebx, 80070057h
0x180031b00  jz      short loc_180031B10
0x180031b02  mov     ebx, 80004005h
0x180031b07  jmp     short loc_180031B10
0x180031b09  mov     ebx, r8d
0x180031b0c  jmp     short loc_180031B10
0x180031b0e  mov     ebx, edx
0x180031b10  mov     rcx, r12; Block
0x180031b13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031b18  mov     rcx, [rbp+70h+Block]; Block
0x180031b1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031b24  nop
0x180031b25  lea     rcx, [rsp+170h+var_130]; this
0x180031b2a  call    ??1CDRMSoapRequest@@UEAA@XZ; CDRMSoapRequest::~CDRMSoapRequest(void)
0x180031b2f  mov     eax, ebx
0x180031b31  jmp     short loc_180031B38
0x180031b33  mov     eax, 80070057h
0x180031b38  lea     r11, [rsp+170h+var_20]
0x180031b40  mov     rbx, [r11+30h]
0x180031b44  mov     rsi, [r11+38h]
0x180031b48  mov     rsp, r11
0x180031b4b  pop     r14
0x180031b4d  pop     r13
0x180031b4f  pop     r12
0x180031b51  pop     rdi
0x180031b52  pop     rbp
0x180031b53  retn
```
