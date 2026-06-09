# CertEnrollHttp::FillInRequestElements(ulong,_CERTTRANSBLOB const *,_WS_HEAP *,RequestSecurityTokenType *)

- ea: `0x180014ae8`
- end: `0x180014ca4`
- name: `?FillInRequestElements@CertEnrollHttp@@YAJKPEBU_CERTTRANSBLOB@@PEAU_WS_HEAP@@PEAURequestSecurityTokenType@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CertEnrollHttp *this, unsigned int *, struct _CERTTRANSBLOB *, struct _WS_HEAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001506c`

## callees

- `0x1800148a4`
- `0x180014ae8`
- `0x1800159e0`
- `0x180029be4`

## import_xrefs

- `webservices!WsAlloc` at `0x180014ba1`
- `webservices!WsAlloc` at `0x180014ba1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014b67`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180014b67`

## string_xrefs

- `0x180014c35`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd#base64binary`
- `0x180014bfb`: `http://schemas.microsoft.com/windows/pki/2009/01/enrollment#CHALLENGERESPONSE`
- `0x180014c15`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd#PKCS7`
- `0x180014be5`: `http://schemas.microsoft.com/windows/pki/2009/01/enrollment#PKCS10`

## pseudocode

```c
__int64 __fastcall CertEnrollHttp::FillInRequestElements(
        CertEnrollHttp *this,
        unsigned int *a2,
        struct _CERTTRANSBLOB *a3,
        struct _WS_HEAP *a4)
{
  __int64 result; // rax
  __int16 v8; // di
  BYTE *v9; // rdx
  HRESULT v10; // eax
  HRESULT v11; // ebx
  unsigned int v12; // ecx
  HRESULT v13; // edx
  unsigned int v14; // r10d
  int v15; // edi
  _DWORD *v16; // rax
  wchar_t *v17; // rcx
  _DWORD *v18; // rax
  _DWORD *v19; // rax
  unsigned __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+30h] BYREF
  void *ptr; // [rsp+88h] [rbp+38h] BYREF

  v21 = (unsigned int)this;
  result = 0;
  v8 = (__int16)this;
  if ( a2 )
  {
    v9 = (BYTE *)*((_QWORD *)a2 + 1);
    if ( v9 )
    {
      if ( *a2 )
      {
        if ( ((unsigned __int16)this & 0xFF00) == 0 )
        {
          v10 = PkcsCrackRequestType(*a2, v9, &v21);
          v11 = v10;
          if ( v10 )
          {
            v12 = 11144121;
            goto LABEL_7;
          }
          v8 = v21;
        }
        ptr = 0;
        v11 = ULongLongMult(0x40u, 1u, &v20);
        if ( v11 >= 0 )
          v11 = WsAlloc((WS_HEAP *)a3, v14, &ptr, 0);
        if ( v11 )
        {
          v13 = v11;
          v12 = 11799481;
          goto LABEL_8;
        }
        v15 = v8 & 0xFF00;
        if ( v15 == 768 || v15 == 1024 )
        {
          v16 = ptr;
          *(_DWORD *)ptr = 87;
          v16[1] = 0;
          v17 = aHttpDocsOasisO_7;
        }
        else
        {
          v16 = ptr;
          if ( v15 == 1280 )
          {
            *(_DWORD *)ptr = 77;
            v16[1] = 0;
            v17 = aHttpSchemasMic_4;
          }
          else
          {
            *(_DWORD *)ptr = 66;
            v16[1] = 0;
            v17 = aHttpSchemasMic_3;
          }
        }
        *((_QWORD *)v16 + 1) = v17;
        v18 = ptr;
        *((_DWORD *)ptr + 4) = 94;
        v18[5] = 0;
        *((_QWORD *)v18 + 3) = aHttpDocsOasisO_8;
        v10 = CertEnrollHttp::ByteArrayToBase64WsString(
                *((CertEnrollHttp **)a2 + 1),
                (unsigned __int8 *)*a2,
                (__int64)a3,
                (struct _WS_HEAP *)((char *)ptr + 48));
        v11 = v10;
        if ( !v10 )
        {
          v19 = ptr;
          *((_DWORD *)ptr + 8) = 0;
          v19[9] = 0;
          *((_QWORD *)v19 + 5) = &dword_18006AF64;
          *((_QWORD *)a4 + 9) = ptr;
          *((_QWORD *)a4 + 8) = 0;
          return (unsigned int)v11;
        }
        v12 = 13175737;
LABEL_7:
        v13 = v10;
LABEL_8:
        CSPrintErrorLineFile(v12, v13);
        return (unsigned int)v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014ae8  mov     [rsp-28h+arg_10], rbx
0x180014aed  mov     [rsp-28h+arg_18], rsi
0x180014af2  mov     [rsp-28h+arg_0], ecx
0x180014af6  push    rbp
0x180014af7  push    rdi
0x180014af8  push    r12
0x180014afa  push    r14
0x180014afc  push    r15
0x180014afe  mov     rbp, rsp
0x180014b01  sub     rsp, 50h
0x180014b05  xor     eax, eax
0x180014b07  xor     r15d, r15d
0x180014b0a  mov     [rbp+var_10], rax
0x180014b0e  mov     r14, r9
0x180014b11  mov     [rbp+var_30], rax
0x180014b15  mov     r12, r8
0x180014b18  mov     [rbp+var_20], rax
0x180014b1c  mov     rsi, rdx
0x180014b1f  mov     [rbp+var_28], rax
0x180014b23  mov     edi, ecx
0x180014b25  mov     [rbp+var_18], rax
0x180014b29  test    rdx, rdx
0x180014b2c  jz      loc_180014C8B
0x180014b32  mov     rdx, [rdx+8]; pbData
0x180014b36  test    rdx, rdx
0x180014b39  jz      loc_180014C8B
0x180014b3f  mov     ecx, [rsi]; cbData
0x180014b41  test    ecx, ecx
0x180014b43  jz      loc_180014C8B
0x180014b49  test    edi, 0FF00h
0x180014b4f  jnz     short loc_180014B75
0x180014b51  lea     r8, [rbp+arg_0]; unsigned int *
0x180014b55  call    ?PkcsCrackRequestType@@YAJKPEBEPEAK@Z; PkcsCrackRequestType(ulong,uchar const *,ulong *)
0x180014b5a  mov     ebx, eax
0x180014b5c  test    eax, eax
0x180014b5e  jz      short loc_180014B72
0x180014b60  mov     ecx, 0AA0BB9h
0x180014b65  mov     edx, eax
0x180014b67  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180014b6d  jmp     loc_180014C89
0x180014b72  mov     edi, [rbp+arg_0]
0x180014b75  mov     edx, 1; unsigned __int64
0x180014b7a  mov     [rbp+ptr], r15
0x180014b7e  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180014b82  lea     r10d, [rdx+3Fh]
0x180014b86  mov     ecx, r10d; unsigned __int64
0x180014b89  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180014b8e  mov     ebx, eax
0x180014b90  test    eax, eax
0x180014b92  js      short loc_180014BA9
0x180014b94  xor     r9d, r9d; error
0x180014b97  lea     r8, [rbp+ptr]; ptr
0x180014b9b  mov     edx, r10d; size
0x180014b9e  mov     rcx, r12; heap
0x180014ba1  call    cs:__imp_WsAlloc
0x180014ba7  mov     ebx, eax
0x180014ba9  test    ebx, ebx
0x180014bab  jz      short loc_180014BB6
0x180014bad  mov     edx, ebx
0x180014baf  mov     ecx, 0B40BB9h
0x180014bb4  jmp     short loc_180014B67
0x180014bb6  and     edi, 0FF00h
0x180014bbc  cmp     edi, 300h
0x180014bc2  jz      short loc_180014C04
0x180014bc4  cmp     edi, 400h
0x180014bca  jz      short loc_180014C04
0x180014bcc  mov     rax, [rbp+ptr]
0x180014bd0  cmp     edi, 500h
0x180014bd6  jz      short loc_180014BEE
0x180014bd8  mov     rcx, [rbp+var_30]
0x180014bdc  mov     dword ptr [rax], 42h ; 'B'
0x180014be2  mov     [rax+4], ecx
0x180014be5  lea     rcx, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/pk"...
0x180014bec  jmp     short loc_180014C1C
0x180014bee  mov     rcx, [rbp+var_28]
0x180014bf2  mov     dword ptr [rax], 4Dh ; 'M'
0x180014bf8  mov     [rax+4], ecx
0x180014bfb  lea     rcx, aHttpSchemasMic_4; "http://schemas.microsoft.com/windows/pk"...
0x180014c02  jmp     short loc_180014C1C
0x180014c04  mov     rax, [rbp+ptr]
0x180014c08  mov     rcx, [rbp+var_20]
0x180014c0c  mov     dword ptr [rax], 57h ; 'W'
0x180014c12  mov     [rax+4], ecx
0x180014c15  lea     rcx, aHttpDocsOasisO_7; "http://docs.oasis-open.org/wss/2004/01/"...
0x180014c1c  mov     [rax+8], rcx
0x180014c20  mov     r8, r12; unsigned int
0x180014c23  mov     rax, [rbp+ptr]
0x180014c27  mov     rcx, [rbp+var_18]
0x180014c2b  mov     dword ptr [rax+10h], 5Eh ; '^'
0x180014c32  mov     [rax+14h], ecx
0x180014c35  lea     rcx, aHttpDocsOasisO_8; "http://docs.oasis-open.org/wss/2004/01/"...
0x180014c3c  mov     [rax+18h], rcx
0x180014c40  mov     r9, [rbp+ptr]
0x180014c44  mov     edx, [rsi]; unsigned __int8 *
0x180014c46  add     r9, 30h ; '0'; struct _WS_HEAP *
0x180014c4a  mov     rcx, [rsi+8]; this
0x180014c4e  call    ?ByteArrayToBase64WsString@CertEnrollHttp@@YAJPEAEKPEAU_WS_HEAP@@PEAU_WS_STRING@@@Z; CertEnrollHttp::ByteArrayToBase64WsString(uchar *,ulong,_WS_HEAP *,_WS_STRING *)
0x180014c53  mov     ebx, eax
0x180014c55  test    eax, eax
0x180014c57  jz      short loc_180014C63
0x180014c59  mov     ecx, 0C90BB9h
0x180014c5e  jmp     loc_180014B65
0x180014c63  mov     rax, [rbp+ptr]
0x180014c67  mov     rcx, [rbp+var_10]
0x180014c6b  mov     [rax+20h], r15d
0x180014c6f  mov     [rax+24h], ecx
0x180014c72  lea     rcx, dword_18006AF64
0x180014c79  mov     [rax+28h], rcx
0x180014c7d  mov     rax, [rbp+ptr]
0x180014c81  mov     [r14+48h], rax
0x180014c85  mov     [r14+40h], r15
0x180014c89  mov     eax, ebx
0x180014c8b  lea     r11, [rsp+50h+var_s0]
0x180014c90  mov     rbx, [r11+40h]
0x180014c94  mov     rsi, [r11+48h]
0x180014c98  mov     rsp, r11
0x180014c9b  pop     r15
0x180014c9d  pop     r14
0x180014c9f  pop     r12
0x180014ca1  pop     rdi
0x180014ca2  pop     rbp
0x180014ca3  retn
```
