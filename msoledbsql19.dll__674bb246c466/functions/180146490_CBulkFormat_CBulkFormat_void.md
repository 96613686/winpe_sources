# CBulkFormat::CBulkFormat(void)

- ea: `0x180146490`
- end: `0x1801466af`
- name: `??0CBulkFormat@@QEAA@XZ`
- size: `543`
- prototype: `CBulkFormat *__fastcall(CBulkFormat *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180144af0`
- `0x180146070`

## callees

- `0x180003488`
- `0x180003d80`
- `0x180146490`
- `0x1801467d0`
- `0x180147530`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180146569`
- `ole32!CoCreateInstance` at `0x180146569`
- `ole32!CLSIDFromProgID` at `0x18014653f`
- `ole32!CLSIDFromProgID` at `0x18014653f`
- `OLEAUT32!__imp_SysAllocString` at `0x180146581`
- `OLEAUT32!__imp_SysAllocString` at `0x180146581`
- `OLEAUT32!__imp_SysFreeString` at `0x180146618`
- `OLEAUT32!__imp_SysFreeString` at `0x180146618`

## string_xrefs

- `0x180146538`: `Msxml2.DOMDocument.6.0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CBulkFormat *__fastcall CBulkFormat::CBulkFormat(CBulkFormat *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  LPVOID *ppv; // r14
  LPVOID v5; // rcx
  BSTR bstrString[2]; // [rsp+30h] [rbp-78h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-58h]
  CBulkFormat *v10; // [rsp+58h] [rbp-50h]
  __int128 v11; // [rsp+60h] [rbp-48h] BYREF
  __int64 v12; // [rsp+70h] [rbp-38h]
  IID rclsid; // [rsp+80h] [rbp-28h] BYREF

  v10 = this;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *(_QWORD *)this = &CBulkRecord::`vftable';
  *((_QWORD *)this + 8) = 0;
  v2 = (_QWORD *)((char *)this + 72);
  *((_QWORD *)this + 10) = (char *)this + 72;
  *((_QWORD *)this + 9) = (char *)this + 72;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v3 = (_QWORD *)((char *)this + 104);
  *((_QWORD *)this + 14) = (char *)this + 104;
  *((_QWORD *)this + 13) = (char *)this + 104;
  ppv = (LPVOID *)((char *)this + 120);
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  rclsid = 0;
  if ( CLSIDFromProgID(L"Msxml2.DOMDocument.6.0", &rclsid) < 0 )
  {
    CMSXMLLoadException::CMSXMLLoadException(bstrString, 1);
    throw (CMSXMLLoadException *)bstrString;
  }
  if ( CoCreateInstance(&rclsid, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, ppv) < 0 )
  {
    CMSXMLLoadException::CMSXMLLoadException(bstrString, 1);
    throw (CMSXMLLoadException *)bstrString;
  }
  _mm_lfence();
  bstrString[0] = SysAllocString(L"ProhibitDTD");
  pExceptionObject = 0;
  v9 = 0;
  LOWORD(pExceptionObject) = 11;
  WORD4(pExceptionObject) = -1;
  v5 = *ppv;
  v11 = pExceptionObject;
  v12 = 0;
  if ( (*(int (__fastcall **)(LPVOID, BSTR, __int128 *))(*(_QWORD *)v5 + 640LL))(v5, bstrString[0], &v11) < 0 )
  {
    CMSXMLLoadException::CMSXMLLoadException(&pExceptionObject, 1);
    throw (CMSXMLLoadException *)&pExceptionObject;
  }
  _mm_lfence();
  v3[1] = v3;
  *v3 = v3;
  v2[1] = v2;
  *v2 = v2;
  CBulkFormat::Destroy(this);
  v3[1] = v3;
  *v3 = v3;
  v2[1] = v2;
  *v2 = v2;
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return this;
}

```

## disassembly

```asm
0x180146490  mov     r11, rsp
0x180146493  mov     [r11+10h], rbx
0x180146497  mov     [r11+18h], rsi
0x18014649b  mov     [r11+20h], rdi
0x18014649f  push    r14
0x1801464a1  sub     rsp, 0A0h
0x1801464a8  mov     rax, cs:__security_cookie
0x1801464af  xor     rax, rsp
0x1801464b2  mov     [rsp+0A8h+var_18], rax
0x1801464ba  mov     rsi, rcx
0x1801464bd  mov     [r11-50h], rcx
0x1801464c1  xor     ecx, ecx
0x1801464c3  mov     [rsi+8], rcx
0x1801464c7  mov     [rsi+10h], rcx
0x1801464cb  mov     [rsi+18h], rcx
0x1801464cf  mov     [rsi+20h], rcx
0x1801464d3  mov     [rsi+28h], rcx
0x1801464d7  mov     [rsi+30h], rcx
0x1801464db  mov     [rsi+38h], rcx
0x1801464df  lea     rax, ??_7CBulkRecord@@6B@; const CBulkRecord::`vftable'
0x1801464e6  mov     [rsi], rax
0x1801464e9  mov     [rsi+40h], rcx
0x1801464ed  lea     rdi, [rsi+48h]
0x1801464f1  mov     [rdi+8], rdi
0x1801464f5  mov     [rdi], rdi
0x1801464f8  mov     [rsi+58h], rcx
0x1801464fc  mov     [rsi+60h], rcx
0x180146500  lea     rbx, [rsi+68h]
0x180146504  mov     [rbx+8], rbx
0x180146508  mov     [rbx], rbx
0x18014650b  lea     r14, [rsi+78h]
0x18014650f  mov     [r14], rcx
0x180146512  mov     [rsi+80h], rcx
0x180146519  mov     [rsi+88h], cl
0x18014651f  mov     [rsi+90h], rcx
0x180146526  mov     [rsi+98h], ecx
0x18014652c  xorps   xmm0, xmm0
0x18014652f  movups  xmmword ptr [r11-28h], xmm0
0x180146534  lea     rdx, [r11-28h]; lpclsid
0x180146538  lea     rcx, szProgID; "Msxml2.DOMDocument.6.0"
0x18014653f  call    cs:__imp_CLSIDFromProgID
0x180146545  test    eax, eax
0x180146547  js      loc_18014666D
0x18014654d  mov     [rsp+0A8h+ppv], r14; ppv
0x180146552  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180146559  xor     edx, edx; pUnkOuter
0x18014655b  mov     r8d, 1; dwClsContext
0x180146561  lea     rcx, [rsp+0A8h+rclsid]; rclsid
0x180146569  call    cs:__imp_CoCreateInstance
0x18014656f  test    eax, eax
0x180146571  js      loc_18014668E
0x180146577  lfence
0x18014657a  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x180146581  call    cs:__imp_SysAllocString
0x180146587  mov     [rsp+0A8h+bstrString], rax
0x18014658c  xorps   xmm0, xmm0
0x18014658f  xor     ecx, ecx
0x180146591  movups  [rsp+0A8h+pExceptionObject], xmm0
0x180146596  mov     [rsp+0A8h+var_58], rcx
0x18014659b  mov     ecx, 0Bh
0x1801465a0  mov     word ptr [rsp+0A8h+pExceptionObject], cx
0x1801465a5  mov     ecx, 0FFFFFFFFh
0x1801465aa  mov     word ptr [rsp+0A8h+pExceptionObject+8], cx
0x1801465af  mov     rcx, [r14]
0x1801465b2  movups  xmm0, [rsp+0A8h+pExceptionObject]
0x1801465b7  movaps  [rsp+0A8h+var_48], xmm0
0x1801465bc  movsd   xmm1, [rsp+0A8h+var_58]
0x1801465c2  movsd   [rsp+0A8h+var_38], xmm1
0x1801465c8  mov     rdx, [rcx]
0x1801465cb  mov     r9, [rdx+280h]
0x1801465d2  lea     r8, [rsp+0A8h+var_48]
0x1801465d7  mov     rdx, rax
0x1801465da  mov     rax, r9
0x1801465dd  call    cs:__guard_dispatch_icall_fptr
0x1801465e3  test    eax, eax
0x1801465e5  js      short loc_18014664C
0x1801465e7  lfence
0x1801465ea  mov     [rbx+8], rbx
0x1801465ee  mov     [rbx], rbx
0x1801465f1  mov     [rdi+8], rdi
0x1801465f5  mov     [rdi], rdi
0x1801465f8  mov     rcx, rsi; this
0x1801465fb  call    ?Destroy@CBulkFormat@@AEAAXXZ; CBulkFormat::Destroy(void)
0x180146600  mov     [rbx+8], rbx
0x180146604  mov     [rbx], rbx
0x180146607  mov     [rdi+8], rdi
0x18014660b  mov     [rdi], rdi
0x18014660e  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180146613  test    rcx, rcx
0x180146616  jz      short loc_18014661F
0x180146618  call    cs:__imp_SysFreeString
0x18014661e  nop
0x18014661f  mov     rax, rsi
0x180146622  mov     rcx, [rsp+0A8h+var_18]
0x18014662a  xor     rcx, rsp; StackCookie
0x18014662d  call    __security_check_cookie
0x180146632  lea     r11, [rsp+0A8h+var_8]
0x18014663a  mov     rbx, [r11+18h]
0x18014663e  mov     rsi, [r11+20h]
0x180146642  mov     rdi, [r11+28h]
0x180146646  mov     rsp, r11
0x180146649  pop     r14
0x18014664b  retn
0x18014664c  mov     edx, 1
0x180146651  lea     rcx, [rsp+0A8h+pExceptionObject]
0x180146656  call    ??0CMSXMLLoadException@@QEAA@W4EX_CODE@0@@Z; CMSXMLLoadException::CMSXMLLoadException(CMSXMLLoadException::EX_CODE)
0x18014665b  lea     rdx, _TI2?AVCMSXMLLoadException@@; pThrowInfo
0x180146662  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180146667  call    _CxxThrowException_0
0x18014666d  mov     edx, 1
0x180146672  lea     rcx, [rsp+0A8h+bstrString]
0x180146677  call    ??0CMSXMLLoadException@@QEAA@W4EX_CODE@0@@Z; CMSXMLLoadException::CMSXMLLoadException(CMSXMLLoadException::EX_CODE)
0x18014667c  lea     rdx, _TI2?AVCMSXMLLoadException@@; pThrowInfo
0x180146683  lea     rcx, [rsp+0A8h+bstrString]; pExceptionObject
0x180146688  call    _CxxThrowException_0
0x18014668e  mov     edx, 1
0x180146693  lea     rcx, [rsp+0A8h+bstrString]
0x180146698  call    ??0CMSXMLLoadException@@QEAA@W4EX_CODE@0@@Z; CMSXMLLoadException::CMSXMLLoadException(CMSXMLLoadException::EX_CODE)
0x18014669d  lea     rdx, _TI2?AVCMSXMLLoadException@@; pThrowInfo
0x1801466a4  lea     rcx, [rsp+0A8h+bstrString]; pExceptionObject
0x1801466a9  call    _CxxThrowException_0
```
