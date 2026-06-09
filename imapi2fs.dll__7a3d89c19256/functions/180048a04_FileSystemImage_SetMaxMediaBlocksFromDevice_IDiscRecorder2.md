# FileSystemImage::SetMaxMediaBlocksFromDevice(IDiscRecorder2 *)

- ea: `0x180048a04`
- end: `0x180048ddd`
- name: `?SetMaxMediaBlocksFromDevice@FileSystemImage@@QEAAXPEAUIDiscRecorder2@@@Z`
- size: `985`
- prototype: `void __fastcall(FileSystemImage *__hidden this, struct IDiscRecorder2 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057d10`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000960c`
- `0x18001f27c`
- `0x1800251dc`
- `0x180028568`
- `0x180028798`
- `0x180028ca8`
- `0x18002d4e4`
- `0x180048534`
- `0x180048a04`
- `0x180088010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180048adf`
- `ole32!CoCreateInstance` at `0x180048adf`
- `ole32!CoTaskMemFree` at `0x180048c9b`
- `ole32!CoTaskMemFree` at `0x180048c9b`
- `OLEAUT32!__imp_VariantClear` at `0x180048be1`
- `OLEAUT32!__imp_VariantClear` at `0x180048c41`
- `OLEAUT32!__imp_VariantClear` at `0x180048be1`
- `OLEAUT32!__imp_VariantClear` at `0x180048c41`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180048c73`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180048c73`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180048b93`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180048b93`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180048b7e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180048b7e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180048bc3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180048bc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FileSystemImage::SetMaxMediaBlocksFromDevice(FileSystemImage *this, struct IDiscRecorder2 *a2)
{
  FileSystemImage *v3; // rdi
  int v4; // esi
  unsigned int v5; // r12d
  HRESULT v6; // ebx
  int v7; // r14d
  int v8; // r13d
  unsigned int v9; // r15d
  int v10; // edx
  int v11; // edx
  int v12; // ecx
  CIMAPIException *v13; // rax
  CIMAPIException *v14; // rax
  CIMAPIException *v15; // rax
  LONG plUbound; // [rsp+30h] [rbp-89h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-81h] BYREF
  LONG plLbound; // [rsp+40h] [rbp-79h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-71h] BYREF
  LPVOID v20; // [rsp+50h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-61h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h] BYREF
  VARIANTARG pv; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v24[144]; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v26; // [rsp+130h] [rbp+77h] BYREF
  CIMAPIException *rgIndices; // [rsp+138h] [rbp+7Fh] BYREF

  v3 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  v4 = 0;
  v22 = 0;
  v20 = 0;
  v26 = 0;
  psa = 0;
  ppv = 0;
  v5 = 0;
  v6 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
         &v22);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, unsigned int *))(*(_QWORD *)v22 + 128LL))(
           v22,
           0,
           &v20,
           &v26);
    if ( v6 >= 0 )
    {
      v6 = CoCreateInstance(&CLSID_MsftDiscFormat2Data, 0, 0x17u, &GUID_27354153_9f64_5b0f_8f00_5d77afbe261e, &ppv);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, SAFEARRAY **))(*(_QWORD *)ppv + 88LL))(ppv, &psa);
        if ( v6 >= 0 )
        {
          v7 = 0;
          pExceptionObject = 0;
          v8 = 0;
          v9 = 0;
          if ( v26 )
          {
            do
            {
              v10 = *((_DWORD *)v20 + v9);
              if ( v10 == 2 )
              {
                pExceptionObject = 1;
              }
              else
              {
                while ( dword_180098A20[4 * v4] != v10 )
                {
                  if ( (unsigned int)++v4 >= 0x13 )
                    goto LABEL_28;
                }
                plLbound = 0;
                plUbound = 0;
                SafeArrayGetLBound(psa, 1u, &plLbound);
                SafeArrayGetUBound(psa, 1u, &plUbound);
                LODWORD(rgIndices) = plLbound;
                if ( plLbound <= plUbound )
                {
                  while ( 1 )
                  {
                    memset(&pv, 0, sizeof(pv));
                    SafeArrayGetElement(psa, (LONG *)&rgIndices, &pv);
                    v11 = dword_180098A28[4 * v4];
                    if ( pv.lVal == v11 )
                      break;
                    VariantClear(&pv);
                    LODWORD(rgIndices) = (_DWORD)rgIndices + 1;
                    if ( (int)rgIndices > plUbound )
                      goto LABEL_28;
                  }
                  if ( dword_180098A24[4 * v4] )
                    v8 = 1;
                  v12 = 0;
                  while ( dword_180098930[5 * v12] != v11 )
                  {
                    if ( (unsigned int)++v12 >= 0xC )
                      goto LABEL_27;
                  }
                  if ( dword_180098938[5 * v12] > v5 )
                    v5 = dword_180098938[5 * v12];
LABEL_27:
                  VariantClear(&pv);
                }
LABEL_28:
                if ( v4 == 19 )
                  v7 = 1;
                v4 = 0;
              }
              ++v9;
            }
            while ( v9 < v26 );
            v3 = this;
          }
          SafeArrayDestroy(psa);
          psa = 0;
          if ( pExceptionObject && (!v7 || !v8) )
            v5 = 0;
        }
      }
    }
  }
  CoTaskMemFree(v20);
  v20 = 0;
  v26 = 0;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
    }
    v13 = (CIMAPIException *)operator new(0x58u);
    rgIndices = v13;
    if ( v13 )
      v14 = CIMAPIException::CIMAPIException(v13, -1062555392);
    else
      v14 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&rgIndices, v14);
    if ( rgIndices && *(_QWORD *)rgIndices )
    {
      v15 = (CIMAPIException *)SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(&rgIndices);
      CIMAPIException::SetCodeRefInfo(v15, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 332);
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&pExceptionObject, &rgIndices);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v24, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v24;
  }
  FileSystemImage::SetFreeMediaBlocks(v3, v5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
}

```

## disassembly

```asm
0x180048a04  mov     [rsp-8+arg_8], rbx
0x180048a09  mov     [rsp-8+arg_0], rcx
0x180048a0e  push    rbp
0x180048a0f  push    rsi
0x180048a10  push    rdi
0x180048a11  push    r12
0x180048a13  push    r13
0x180048a15  push    r14
0x180048a17  push    r15
0x180048a19  lea     rbp, [rsp-27h]
0x180048a1e  sub     rsp, 0E0h
0x180048a25  mov     rbx, rdx
0x180048a28  mov     rdi, rcx
0x180048a2b  lea     r14, WPP_GLOBAL_Control
0x180048a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a39  cmp     rcx, r14
0x180048a3c  jz      short loc_180048A5F
0x180048a3e  test    byte ptr [rcx+44h], 8
0x180048a42  jz      short loc_180048A5F
0x180048a44  cmp     byte ptr [rcx+41h], 5
0x180048a48  jb      short loc_180048A5F
0x180048a4a  mov     edx, 0Dh
0x180048a4f  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x180048a56  mov     rcx, [rcx+38h]
0x180048a5a  call    WPP_SF_
0x180048a5f  xor     esi, esi
0x180048a61  mov     [rbp+57h+var_B0], rsi
0x180048a65  mov     [rbp+57h+var_C0], rsi
0x180048a69  mov     [rbp+57h+arg_10], esi
0x180048a6c  mov     [rsp+110h+psa], rsi
0x180048a71  mov     [rbp+57h+var_B8], rsi
0x180048a75  mov     r12d, esi
0x180048a78  mov     rax, [rbx]
0x180048a7b  lea     r8, [rbp+57h+var_B0]
0x180048a7f  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180048a86  mov     rcx, rbx
0x180048a89  mov     rax, [rax]
0x180048a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a91  mov     ebx, eax
0x180048a93  test    eax, eax
0x180048a95  js      loc_180048C97
0x180048a9b  mov     rcx, [rbp+57h+var_B0]
0x180048a9f  mov     rax, [rcx]
0x180048aa2  lea     r9, [rbp+57h+arg_10]
0x180048aa6  lea     r8, [rbp+57h+var_C0]
0x180048aaa  xor     edx, edx
0x180048aac  mov     rax, [rax+80h]
0x180048ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ab8  mov     ebx, eax
0x180048aba  test    eax, eax
0x180048abc  js      loc_180048C97
0x180048ac2  lea     rax, [rbp+57h+var_B8]
0x180048ac6  mov     [rsp+110h+ppv], rax; ppv
0x180048acb  lea     r9, _GUID_27354153_9f64_5b0f_8f00_5d77afbe261e; riid
0x180048ad2  xor     edx, edx; pUnkOuter
0x180048ad4  lea     r8d, [rsi+17h]; dwClsContext
0x180048ad8  lea     rcx, CLSID_MsftDiscFormat2Data; rclsid
0x180048adf  call    cs:__imp_CoCreateInstance
0x180048ae5  mov     ebx, eax
0x180048ae7  test    eax, eax
0x180048ae9  js      loc_180048C97
0x180048aef  mov     rcx, [rbp+57h+var_B8]
0x180048af3  mov     rax, [rcx]
0x180048af6  lea     rdx, [rsp+110h+psa]
0x180048afb  mov     rax, [rax+58h]
0x180048aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b04  mov     ebx, eax
0x180048b06  test    eax, eax
0x180048b08  js      loc_180048C97
0x180048b0e  mov     r14d, esi
0x180048b11  mov     [rbp+57h+pExceptionObject], esi
0x180048b14  mov     r13d, esi
0x180048b17  mov     r15d, esi
0x180048b1a  cmp     [rbp+57h+arg_10], esi
0x180048b1d  jbe     loc_180048C6E
0x180048b23  lea     r9d, [rsi+1]
0x180048b27  lea     r8, cs:180000000h
0x180048b2e  mov     ecx, r15d
0x180048b31  mov     rax, [rbp+57h+var_C0]
0x180048b35  mov     edx, [rax+rcx*4]
0x180048b38  cmp     edx, 2
0x180048b3b  jnz     short loc_180048B46
0x180048b3d  mov     [rbp+57h+pExceptionObject], r9d
0x180048b41  jmp     loc_180048C5D
0x180048b46  movsxd  rdi, esi
0x180048b49  add     rdi, rdi
0x180048b4c  cmp     ds:rva dword_180098A20[r8+rdi*8], edx
0x180048b54  jz      short loc_180048B63
0x180048b56  add     esi, r9d
0x180048b59  cmp     esi, 13h
0x180048b5c  jb      short loc_180048B46
0x180048b5e  jmp     loc_180048C54
0x180048b63  mov     [rbp+57h+plLbound], 0
0x180048b6a  mov     [rsp+110h+plUbound], 0
0x180048b72  lea     r8, [rbp+57h+plLbound]; plLbound
0x180048b76  mov     edx, r9d; nDim
0x180048b79  mov     rcx, [rsp+110h+psa]; psa
0x180048b7e  call    cs:__imp_SafeArrayGetLBound
0x180048b84  lea     r8, [rsp+110h+plUbound]; plUbound
0x180048b89  mov     edx, 1; nDim
0x180048b8e  mov     rcx, [rsp+110h+psa]; psa
0x180048b93  call    cs:__imp_SafeArrayGetUBound
0x180048b99  mov     eax, [rbp+57h+plLbound]
0x180048b9c  mov     dword ptr [rbp+57h+rgIndices], eax
0x180048b9f  cmp     eax, [rsp+110h+plUbound]
0x180048ba3  jg      loc_180048C47
0x180048ba9  xorps   xmm0, xmm0
0x180048bac  xor     eax, eax
0x180048bae  movups  [rbp+57h+pv], xmm0
0x180048bb2  mov     [rbp+57h+var_98], rax
0x180048bb6  lea     r8, [rbp+57h+pv]; pv
0x180048bba  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180048bbe  mov     rcx, [rsp+110h+psa]; psa
0x180048bc3  call    cs:__imp_SafeArrayGetElement
0x180048bc9  lea     r8, cs:180000000h
0x180048bd0  mov     edx, ds:rva dword_180098A28[r8+rdi*8]
0x180048bd8  cmp     dword ptr [rbp+57h+pv+8], edx
0x180048bdb  jz      short loc_180048BFE
0x180048bdd  lea     rcx, [rbp+57h+pv]; pvarg
0x180048be1  call    cs:__imp_VariantClear
0x180048be7  mov     eax, dword ptr [rbp+57h+rgIndices]
0x180048bea  mov     r9d, 1
0x180048bf0  add     eax, r9d
0x180048bf3  mov     dword ptr [rbp+57h+rgIndices], eax
0x180048bf6  cmp     eax, [rsp+110h+plUbound]
0x180048bfa  jle     short loc_180048BA9
0x180048bfc  jmp     short loc_180048C4D
0x180048bfe  cmp     ds:rva dword_180098A24[r8+rdi*8], 0
0x180048c07  mov     r9d, 1
0x180048c0d  cmovnz  r13d, r9d
0x180048c11  xor     ecx, ecx
0x180048c13  movsxd  rax, ecx
0x180048c16  lea     rax, [rax+rax*4]
0x180048c1a  cmp     ds:rva dword_180098930[r8+rax*4], edx
0x180048c22  jz      short loc_180048C2E
0x180048c24  add     ecx, r9d
0x180048c27  cmp     ecx, 0Ch
0x180048c2a  jb      short loc_180048C13
0x180048c2c  jmp     short loc_180048C3D
0x180048c2e  mov     eax, ds:rva dword_180098938[r8+rax*4]
0x180048c36  cmp     eax, r12d
0x180048c39  cmova   r12d, eax
0x180048c3d  lea     rcx, [rbp+57h+pv]; pvarg
0x180048c41  call    cs:__imp_VariantClear
0x180048c47  mov     r9d, 1
0x180048c4d  lea     r8, cs:180000000h
0x180048c54  cmp     esi, 13h
0x180048c57  cmovz   r14d, r9d
0x180048c5b  xor     esi, esi
0x180048c5d  add     r15d, r9d
0x180048c60  cmp     r15d, [rbp+57h+arg_10]
0x180048c64  jb      loc_180048B2E
0x180048c6a  mov     rdi, [rbp+57h+arg_0]
0x180048c6e  mov     rcx, [rsp+110h+psa]; psa
0x180048c73  call    cs:__imp_SafeArrayDestroy
0x180048c79  mov     [rsp+110h+psa], rsi
0x180048c7e  cmp     [rbp+57h+pExceptionObject], esi
0x180048c81  jz      short loc_180048C90
0x180048c83  test    r14d, r14d
0x180048c86  jz      short loc_180048C8D
0x180048c88  test    r13d, r13d
0x180048c8b  jnz     short loc_180048C90
0x180048c8d  mov     r12d, esi
0x180048c90  lea     r14, WPP_GLOBAL_Control
0x180048c97  mov     rcx, [rbp+57h+var_C0]; pv
0x180048c9b  call    cs:__imp_CoTaskMemFree
0x180048ca1  mov     [rbp+57h+var_C0], rsi
0x180048ca5  mov     [rbp+57h+arg_10], esi
0x180048ca8  test    ebx, ebx
0x180048caa  js      short loc_180048D13
0x180048cac  mov     edx, r12d; unsigned int
0x180048caf  mov     rcx, rdi; this
0x180048cb2  call    ?SetFreeMediaBlocks@FileSystemImage@@QEAAXK@Z; FileSystemImage::SetFreeMediaBlocks(ulong)
0x180048cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180048cbe  cmp     rcx, r14
0x180048cc1  jz      short loc_180048CE5
0x180048cc3  test    byte ptr [rcx+44h], 8
0x180048cc7  jz      short loc_180048CE5
0x180048cc9  cmp     byte ptr [rcx+41h], 5
0x180048ccd  jb      short loc_180048CE5
0x180048ccf  mov     edx, 0Fh
0x180048cd4  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x180048cdb  mov     rcx, [rcx+38h]
0x180048cdf  call    WPP_SF_
0x180048ce4  nop
0x180048ce5  lea     rcx, [rbp+57h+var_B8]
0x180048ce9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048cee  nop
0x180048cef  lea     rcx, [rbp+57h+var_B0]
0x180048cf3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048cf8  mov     rbx, [rsp+110h+arg_8]
0x180048d00  add     rsp, 0E0h
0x180048d07  pop     r15
0x180048d09  pop     r14
0x180048d0b  pop     r13
0x180048d0d  pop     r12
0x180048d0f  pop     rdi
0x180048d10  pop     rsi
0x180048d11  pop     rbp
0x180048d12  retn
0x180048d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d1a  cmp     rcx, r14
0x180048d1d  jz      short loc_180048D40
0x180048d1f  test    byte ptr [rcx+44h], 4
0x180048d23  jz      short loc_180048D40
0x180048d25  cmp     byte ptr [rcx+41h], 2
0x180048d29  jb      short loc_180048D40
0x180048d2b  mov     edx, 0Eh
0x180048d30  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x180048d37  mov     rcx, [rcx+38h]
0x180048d3b  call    WPP_SF_
0x180048d40  mov     ecx, 58h ; 'X'; unsigned __int64
0x180048d45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048d4a  mov     [rbp+57h+rgIndices], rax
0x180048d4e  test    rax, rax
0x180048d51  jz      short loc_180048D62
0x180048d53  mov     edx, 0C0AAB100h; int
0x180048d58  mov     rcx, rax; this
0x180048d5b  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180048d60  jmp     short loc_180048D65
0x180048d62  mov     rax, rsi
0x180048d65  mov     rdx, rax
0x180048d68  lea     rcx, [rbp+57h+rgIndices]
0x180048d6c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180048d71  nop
0x180048d72  mov     rax, [rbp+57h+rgIndices]
0x180048d76  test    rax, rax
0x180048d79  jz      short loc_180048DBC
0x180048d7b  cmp     [rax], rsi
0x180048d7e  jz      short loc_180048DBC
0x180048d80  lea     rcx, [rbp+57h+rgIndices]
0x180048d84  call    ??C?$SmartClassPtr@VCIMAPIException@@V1@@@QEBAPEAVCIMAPIException@@XZ; SmartClassPtr<CIMAPIException,CIMAPIException>::operator->(void)
0x180048d89  mov     rcx, rax; this
0x180048d8c  mov     r8d, 14Ch; int
0x180048d92  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x180048d99  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180048d9e  lea     rdx, [rbp+57h+rgIndices]
0x180048da2  lea     rcx, [rbp+57h+pExceptionObject]
0x180048da6  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@AEBV0@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(SmartPtr<CIMAPIException> const &)
0x180048dab  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180048db2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180048db6  call    _CxxThrowException_0
0x180048dbc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180048dc3  lea     rcx, [rbp+57h+var_90]; this
0x180048dc7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180048dcc  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180048dd3  lea     rcx, [rbp+57h+var_90]; pExceptionObject
0x180048dd7  call    _CxxThrowException_0
```
