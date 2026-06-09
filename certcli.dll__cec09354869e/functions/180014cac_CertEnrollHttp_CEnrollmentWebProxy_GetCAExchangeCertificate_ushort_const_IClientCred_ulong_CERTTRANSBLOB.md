# CertEnrollHttp::CEnrollmentWebProxy::GetCAExchangeCertificate(ushort const *,IClientCred *,ulong,_CERTTRANSBLOB *)

- ea: `0x180014cac`
- end: `0x180014e60`
- name: `?GetCAExchangeCertificate@CEnrollmentWebProxy@CertEnrollHttp@@SAJPEBGPEAUIClientCred@@KPEAU_CERTTRANSBLOB@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(CertEnrollHttp *this, struct IClientCred *, int, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dcc0`

## callees

- `0x1800149f8`
- `0x180014cac`
- `0x1800156e4`
- `0x1800396f2`

## import_xrefs

- `webservices!WsCreateError` at `0x180014d03`
- `webservices!WsCreateError` at `0x180014d03`
- `webservices!WsCreateHeap` at `0x180014d3d`
- `webservices!WsCreateHeap` at `0x180014d3d`
- `webservices!WsFreeHeap` at `0x180014e39`
- `webservices!WsFreeHeap` at `0x180014e39`
- `webservices!WsFreeError` at `0x180014e48`
- `webservices!WsFreeError` at `0x180014e48`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014e2a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014e2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CertEnrollHttp::CEnrollmentWebProxy::GetCAExchangeCertificate(
        CertEnrollHttp *this,
        struct IClientCred *a2,
        int a3,
        struct _CERTTRANSBLOB *a4)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v10; // edx
  unsigned int v11; // ecx
  HRESULT v12; // eax
  const unsigned __int16 *v13; // rdx
  struct IClientCred *v14; // r9
  unsigned int v15; // eax
  struct _CERTTRANSBLOB *v16; // r8
  __int64 v17; // rcx
  CertEnrollHttp **v18; // rax
  unsigned int v19; // eax
  WS_ERROR *error; // [rsp+40h] [rbp-79h] BYREF
  WS_HEAP *heap; // [rsp+48h] [rbp-71h] BYREF
  __int64 v23; // [rsp+50h] [rbp-69h] BYREF
  __int128 v24; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v26; // [rsp+90h] [rbp-29h]
  __int128 v27; // [rsp+A0h] [rbp-19h]
  __int128 *v28; // [rsp+B0h] [rbp-9h]
  __int64 v29; // [rsp+B8h] [rbp-1h]
  int v30; // [rsp+C8h] [rbp+Fh]
  __int64 v31; // [rsp+D0h] [rbp+17h]

  error = 0;
  memset_0(v25, 0, 0x68u);
  heap = 0;
  v23 = 0;
  v24 = 0;
  v8 = WsCreateError(0, 0, &error);
  v9 = v8;
  if ( v8 )
  {
    v10 = v8;
    v11 = 41487289;
  }
  else
  {
    v12 = WsCreateHeap(0xA00000u, 0x400u, 0, 0, &heap, error);
    v9 = v12;
    if ( v12 )
    {
      v10 = v12;
      v11 = 41749433;
    }
    else
    {
      v28 = &v24;
      LOBYTE(v13) = 1;
      LOBYTE(v14) = (a3 & 0x100000) != 0;
      v31 = 0;
      v30 = 0;
      v29 = 0;
      v27 = *(_OWORD *)&qword_180042548;
      *((_QWORD *)&v24 + 1) = 0;
      v26 = *(_OWORD *)&qword_180042538;
      LODWORD(v24) = 0;
      v15 = CertEnrollHttp::RequestSecurityToken(
              this,
              v13,
              a2,
              v14,
              heap,
              error,
              (struct _WS_ERROR *)v25,
              (struct RequestSecurityTokenType *)&v23);
      v9 = v15;
      if ( v15 )
      {
        v10 = v15;
        v11 = 43125689;
      }
      else
      {
        v17 = *(_QWORD *)(v23 + 48);
        if ( v17 && !*(_DWORD *)v17 && (v18 = *(CertEnrollHttp ***)(v17 + 8)) != 0 && *v18 )
        {
          v19 = CertEnrollHttp::CopyResponse(*v18, (struct BinarySecurityTokenType *)a4, v16);
          v9 = v19;
          if ( !v19 )
            goto LABEL_15;
          v10 = v19;
          v11 = 44043193;
        }
        else
        {
          v9 = -2147024883;
          v11 = 43781049;
          v10 = -2147024883;
        }
      }
    }
  }
  CSPrintErrorLineFile(v11, v10);
LABEL_15:
  if ( heap )
    WsFreeHeap(heap);
  if ( error )
    WsFreeError(error);
  return v9;
}

```

## disassembly

```asm
0x180014cac  push    rbp
0x180014cae  push    rbx
0x180014caf  push    rsi
0x180014cb0  push    rdi
0x180014cb1  push    r14
0x180014cb3  push    r15
0x180014cb5  lea     rbp, [rsp-2Fh]
0x180014cba  sub     rsp, 0E8h
0x180014cc1  mov     r14, rdx
0x180014cc4  mov     [rbp+57h+error], 0
0x180014ccc  xor     edx, edx; Val
0x180014cce  mov     edi, r8d
0x180014cd1  mov     r15, rcx
0x180014cd4  mov     rsi, r9
0x180014cd7  lea     rcx, [rbp+57h+var_A0]; void *
0x180014cdb  lea     r8d, [rdx+68h]; Size
0x180014cdf  call    memset_0
0x180014ce4  xorps   xmm0, xmm0
0x180014ce7  mov     [rbp+57h+var_C8], 0
0x180014cef  lea     r8, [rbp+57h+error]; error
0x180014cf3  mov     [rbp+57h+var_C0], 0
0x180014cfb  xor     edx, edx; propertyCount
0x180014cfd  xor     ecx, ecx; properties
0x180014cff  movups  [rbp+57h+var_B8], xmm0
0x180014d03  call    cs:__imp_WsCreateError
0x180014d09  mov     ebx, eax
0x180014d0b  test    eax, eax
0x180014d0d  jz      short loc_180014D1B
0x180014d0f  mov     edx, eax
0x180014d11  mov     ecx, 2790BB9h
0x180014d16  jmp     loc_180014E2A
0x180014d1b  mov     rax, [rbp+57h+error]
0x180014d1f  xor     r9d, r9d; propertyCount
0x180014d22  mov     [rsp+110h+var_E8], rax; error
0x180014d27  xor     r8d, r8d; properties
0x180014d2a  lea     rax, [rbp+57h+var_C8]
0x180014d2e  mov     edx, 400h; trimSize
0x180014d33  mov     ecx, 0A00000h; maxSize
0x180014d38  mov     [rsp+110h+heap], rax; heap
0x180014d3d  call    cs:__imp_WsCreateHeap
0x180014d43  mov     ebx, eax
0x180014d45  test    eax, eax
0x180014d47  jz      short loc_180014D55
0x180014d49  mov     edx, eax
0x180014d4b  mov     ecx, 27D0BB9h
0x180014d50  jmp     loc_180014E2A
0x180014d55  mov     rcx, [rbp+57h+var_C8]
0x180014d59  lea     rax, [rbp+57h+var_B8]
0x180014d5d  movups  xmm0, xmmword ptr cs:qword_180042548
0x180014d64  mov     [rbp+57h+var_60], rax
0x180014d68  lea     rax, [rbp+57h+var_C0]
0x180014d6c  movups  xmm1, xmmword ptr cs:qword_180042538
0x180014d73  mov     [rsp+110h+var_D8], rax; struct RequestSecurityTokenType *
0x180014d78  mov     dl, 1; unsigned __int16 *
0x180014d7a  lea     rax, [rbp+57h+var_A0]
0x180014d7e  shr     edi, 14h
0x180014d81  mov     [rsp+110h+var_E0], rax; struct _WS_ERROR *
0x180014d86  and     dil, dl
0x180014d89  mov     rax, [rbp+57h+error]
0x180014d8d  mov     r9b, dil; struct IClientCred *
0x180014d90  mov     [rsp+110h+var_E8], rax; struct _WS_HEAP *
0x180014d95  mov     r8, r14; bool
0x180014d98  mov     [rsp+110h+heap], rcx; heap
0x180014d9d  mov     rcx, r15; this
0x180014da0  mov     [rbp+57h+var_40], 0
0x180014da8  mov     [rbp+57h+var_48], 0
0x180014daf  mov     [rbp+57h+var_58], 0
0x180014db7  movdqu  [rbp+57h+var_70], xmm0
0x180014dbc  mov     qword ptr [rbp+57h+var_B8+8], 0
0x180014dc4  movdqu  [rbp+57h+var_80], xmm1
0x180014dc9  mov     dword ptr [rbp+57h+var_B8], 0
0x180014dd0  call    ?RequestSecurityToken@CertEnrollHttp@@YAJPEBG_NPEAUIClientCred@@1PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAURequestSecurityTokenType@@PEAPEAURequestSecurityTokenResponseType@@@Z; CertEnrollHttp::RequestSecurityToken(ushort const *,bool,IClientCred *,bool,_WS_HEAP *,_WS_ERROR *,RequestSecurityTokenType *,RequestSecurityTokenResponseType * *)
0x180014dd5  mov     ebx, eax
0x180014dd7  test    eax, eax
0x180014dd9  jz      short loc_180014DE4
0x180014ddb  mov     edx, eax
0x180014ddd  mov     ecx, 2920BB9h
0x180014de2  jmp     short loc_180014E2A
0x180014de4  mov     rax, [rbp+57h+var_C0]
0x180014de8  mov     rcx, [rax+30h]
0x180014dec  test    rcx, rcx
0x180014def  jz      short loc_180014E1E
0x180014df1  cmp     dword ptr [rcx], 0
0x180014df4  jnz     short loc_180014E1E
0x180014df6  mov     rax, [rcx+8]
0x180014dfa  test    rax, rax
0x180014dfd  jz      short loc_180014E1E
0x180014dff  mov     rcx, [rax]; this
0x180014e02  test    rcx, rcx
0x180014e05  jz      short loc_180014E1E
0x180014e07  mov     rdx, rsi; struct BinarySecurityTokenType *
0x180014e0a  call    ?CopyResponse@CertEnrollHttp@@YAJPEAUBinarySecurityTokenType@@PEAU_CERTTRANSBLOB@@@Z; CertEnrollHttp::CopyResponse(BinarySecurityTokenType *,_CERTTRANSBLOB *)
0x180014e0f  mov     ebx, eax
0x180014e11  test    eax, eax
0x180014e13  jz      short loc_180014E30
0x180014e15  mov     edx, eax
0x180014e17  mov     ecx, 2A00BB9h
0x180014e1c  jmp     short loc_180014E2A
0x180014e1e  mov     ebx, 8007000Dh
0x180014e23  mov     ecx, 29C0BB9h
0x180014e28  mov     edx, ebx
0x180014e2a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180014e30  mov     rcx, [rbp+57h+var_C8]; heap
0x180014e34  test    rcx, rcx
0x180014e37  jz      short loc_180014E3F
0x180014e39  call    cs:__imp_WsFreeHeap
0x180014e3f  mov     rcx, [rbp+57h+error]; error
0x180014e43  test    rcx, rcx
0x180014e46  jz      short loc_180014E4E
0x180014e48  call    cs:__imp_WsFreeError
0x180014e4e  mov     eax, ebx
0x180014e50  add     rsp, 0E8h
0x180014e57  pop     r15
0x180014e59  pop     r14
0x180014e5b  pop     rdi
0x180014e5c  pop     rsi
0x180014e5d  pop     rbx
0x180014e5e  pop     rbp
0x180014e5f  retn
```
