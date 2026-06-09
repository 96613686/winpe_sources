# GetV1TemplateName(_CERT_INFO *)

- ea: `0x180014518`
- end: `0x18001468b`
- name: `?GetV1TemplateName@@YA?AVCString@WTL@@PEAU_CERT_INFO@@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800140ec`

## callees

- `0x180001f4c`
- `0x180013544`
- `0x180014518`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145a9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001459f`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001459f`
- `CRYPT32!CertFindExtension` at `0x18001455f`
- `CRYPT32!CertFindExtension` at `0x18001455f`
- `certca!__imp_CAFindCertTypeByName` at `0x1800145db`
- `certca!__imp_CAFindCertTypeByName` at `0x1800145db`
- `certca!__imp_CACloseCertType` at `0x180014661`
- `certca!__imp_CACloseCertType` at `0x180014661`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x1800145fc`
- `certca!__imp_CAGetCertTypePropertyEx` at `0x1800145fc`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180014630`
- `certca!__imp_CAFreeCertTypeProperty` at `0x180014630`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WTL::CString *__fastcall GetV1TemplateName(WTL::CString *a1, __int64 a2)
{
  signed int v3; // ebx
  PCERT_EXTENSION Extension; // rax
  signed int LastError; // eax
  int v6; // eax
  unsigned __int16 **v8; // [rsp+48h] [rbp-18h] BYREF
  __int64 pvStructInfo; // [rsp+50h] [rbp-10h] BYREF
  DWORD pcbStructInfo; // [rsp+88h] [rbp+28h] BYREF
  signed int pExceptionObject; // [rsp+90h] [rbp+30h] BYREF
  __int64 v12; // [rsp+98h] [rbp+38h] BYREF

  v3 = 0;
  pcbStructInfo = 0;
  v12 = 0;
  *(_QWORD *)a1 = WTL::_atltmpPchNil;
  Extension = CertFindExtension("1.3.6.1.4.1.311.20.2", *(_DWORD *)(a2 + 192), *(CERT_EXTENSION **)(a2 + 200));
  if ( Extension )
  {
    pvStructInfo = 0;
    if ( CryptDecodeObjectEx(
           1u,
           (LPCSTR)0x18,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0x8000u,
           0,
           &pvStructInfo,
           &pcbStructInfo) )
    {
      v6 = CAFindCertTypeByName(*(_QWORD *)(pvStructInfo + 16), 0, 192, &v12);
      v8 = 0;
      if ( v6 < 0 || (v3 = CAGetCertTypePropertyEx(v12, L"displayName", &v8), v3 < 0) )
      {
        WTL::CString::operator=(a1, *(unsigned __int16 **)(pvStructInfo + 16));
        v3 = *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
      }
      else if ( v8 )
      {
        WTL::CString::operator=(a1, *v8);
        if ( !*(_QWORD *)a1 )
          v3 = -2147024882;
        CAFreeCertTypeProperty(v12, v8);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v12 )
    CACloseCertType();
  if ( v3 < 0 )
  {
    pExceptionObject = v3;
    throw (long *)&pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180014518  mov     [rsp-18h+arg_0], rcx
0x18001451d  push    rbp
0x18001451e  push    rbx
0x18001451f  push    rdi
0x180014520  mov     rbp, rsp
0x180014523  sub     rsp, 60h
0x180014527  mov     rdi, rcx
0x18001452a  mov     [rbp+var_20], 0
0x180014531  xor     ebx, ebx
0x180014533  mov     [rbp+arg_8], ebx
0x180014536  mov     [rbp+arg_18], rbx
0x18001453a  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180014541  mov     [rcx], rax
0x180014544  mov     [rbp+var_20], 1
0x18001454b  mov     r8, [rdx+0C8h]; rgExtensions
0x180014552  mov     edx, [rdx+0C0h]; cExtensions
0x180014558  lea     rcx, a136141311202; "1.3.6.1.4.1.311.20.2"
0x18001455f  call    cs:__imp_CertFindExtension
0x180014565  test    rax, rax
0x180014568  jz      loc_180014658
0x18001456e  mov     [rbp+var_10], rbx
0x180014572  lea     rdx, [rbp+arg_8]
0x180014576  mov     [rsp+60h+pcbStructInfo], rdx; pcbStructInfo
0x18001457b  lea     rdx, [rbp+var_10]
0x18001457f  mov     [rsp+60h+pvStructInfo], rdx; pvStructInfo
0x180014584  mov     [rsp+60h+pDecodePara], rbx; pDecodePara
0x180014589  mov     [rsp+60h+dwFlags], 8000h; dwFlags
0x180014591  mov     r9d, [rax+10h]; cbEncoded
0x180014595  mov     r8, [rax+18h]; pbEncoded
0x180014599  lea     edx, [rbx+18h]; lpszStructType
0x18001459c  lea     ecx, [rbx+1]; dwCertEncodingType
0x18001459f  call    cs:__imp_CryptDecodeObjectEx
0x1800145a5  test    eax, eax
0x1800145a7  jnz     short loc_1800145C7
0x1800145a9  call    cs:__imp_GetLastError
0x1800145af  mov     ebx, eax
0x1800145b1  test    eax, eax
0x1800145b3  jle     loc_180014658
0x1800145b9  movzx   ebx, ax
0x1800145bc  or      ebx, 80070000h
0x1800145c2  jmp     loc_180014658
0x1800145c7  lea     r9, [rbp+arg_18]
0x1800145cb  xor     edx, edx
0x1800145cd  mov     r8d, 0C0h
0x1800145d3  mov     rcx, [rbp+var_10]
0x1800145d7  mov     rcx, [rcx+10h]
0x1800145db  call    cs:__imp_CAFindCertTypeByName
0x1800145e1  mov     [rbp+var_18], 0
0x1800145e9  test    eax, eax
0x1800145eb  js      short loc_180014638
0x1800145ed  lea     r8, [rbp+var_18]
0x1800145f1  lea     rdx, aDisplayname; "displayName"
0x1800145f8  mov     rcx, [rbp+arg_18]
0x1800145fc  call    cs:__imp_CAGetCertTypePropertyEx
0x180014602  mov     ebx, eax
0x180014604  test    eax, eax
0x180014606  js      short loc_180014638
0x180014608  mov     rdx, [rbp+var_18]
0x18001460c  test    rdx, rdx
0x18001460f  jz      short loc_180014658
0x180014611  mov     rdx, [rdx]; unsigned __int16 *
0x180014614  mov     rcx, rdi; this
0x180014617  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x18001461c  mov     ecx, 8007000Eh
0x180014621  cmp     qword ptr [rdi], 0
0x180014625  cmovz   ebx, ecx
0x180014628  mov     rdx, [rbp+var_18]
0x18001462c  mov     rcx, [rbp+arg_18]
0x180014630  call    cs:__imp_CAFreeCertTypeProperty
0x180014636  jmp     short loc_180014658
0x180014638  mov     rdx, [rbp+var_10]
0x18001463c  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180014640  mov     rcx, rdi; this
0x180014643  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x180014648  mov     rax, [rdi]
0x18001464b  neg     rax
0x18001464e  sbb     ebx, ebx
0x180014650  not     ebx
0x180014652  and     ebx, 8007000Eh
0x180014658  mov     rcx, [rbp+arg_18]
0x18001465c  test    rcx, rcx
0x18001465f  jz      short loc_180014667
0x180014661  call    cs:__imp_CACloseCertType
0x180014667  test    ebx, ebx
0x180014669  jns     short loc_18001467F
0x18001466b  mov     [rbp+pExceptionObject], ebx
0x18001466e  lea     rdx, _TI1J; pThrowInfo
0x180014675  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014679  call    _CxxThrowException_0
0x18001467f  mov     rax, rdi
0x180014682  add     rsp, 60h
0x180014686  pop     rdi
0x180014687  pop     rbx
0x180014688  pop     rbp
0x180014689  retn
```
