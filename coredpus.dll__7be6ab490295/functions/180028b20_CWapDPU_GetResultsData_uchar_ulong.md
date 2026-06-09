# CWapDPU::GetResultsData(uchar *,ulong)

- ea: `0x180028b20`
- end: `0x180028e3a`
- name: `?GetResultsData@CWapDPU@@UEAAJPEAEK@Z`
- size: `794`
- prototype: `__int64 __fastcall(CWapDPU *this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180028a50`
- `0x180028b20`
- `0x180029098`
- `0x18002e4e0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180028d91`
- `OLEAUT32!__imp_SysAllocString` at `0x180028d91`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180028ce8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180028ce8`
- `OLEAUT32!__imp_SysFreeString` at `0x180028dae`
- `OLEAUT32!__imp_SysFreeString` at `0x180028de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180028dae`
- `OLEAUT32!__imp_SysFreeString` at `0x180028de2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028e1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028e1c`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180028bed`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180028bed`
- `XmlLite!CreateXmlWriter` at `0x180028bc6`
- `XmlLite!CreateXmlWriter` at `0x180028bc6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028ba2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028ba2`

## pseudocode

```c
__int64 __fastcall CWapDPU::GetResultsData(CWapDPU *this, unsigned __int8 *a2, int a3)
{
  IXmlWriterOutput *v6; // r15
  HRESULT XmlWriterOutputWithEncodingName; // ebx
  int v8; // r12d
  struct IDomNode *v9; // r8
  BSTR v10; // rax
  __int64 v11; // r14
  BSTR v12; // rax
  struct IDomNode *v13; // rdx
  LPSTREAM ppstm; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h]
  IXmlWriterOutput *ppOutput[2]; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+90h] [rbp+40h] BYREF
  void *ppvObject; // [rsp+98h] [rbp+48h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+58h] BYREF

  v6 = (IXmlWriterOutput *)((char *)this + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ppOutput[1] = v6;
  ppstm = 0;
  ppvObject = 0;
  ppOutput[0] = 0;
  v16 = 0;
  v20 = 0;
  v18 = 0;
  if ( a2 && a3 == 24 )
  {
    XmlWriterOutputWithEncodingName = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( XmlWriterOutputWithEncodingName >= 0 )
    {
      XmlWriterOutputWithEncodingName = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      if ( XmlWriterOutputWithEncodingName >= 0 )
      {
        XmlWriterOutputWithEncodingName = CreateXmlWriterOutputWithEncodingName(
                                            (IUnknown *)ppstm,
                                            0,
                                            L"UTF-16",
                                            ppOutput);
        if ( XmlWriterOutputWithEncodingName >= 0 )
        {
          XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject
                                                                                                  + 24LL))(
                                              ppvObject,
                                              ppOutput[0]);
          if ( XmlWriterOutputWithEncodingName >= 0 )
          {
            XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject
                                                                                                  + 40LL))(
                                                ppvObject,
                                                3,
                                                1);
            if ( XmlWriterOutputWithEncodingName >= 0 )
            {
              XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvObject + 40LL))(
                                                  ppvObject,
                                                  2,
                                                  0);
              if ( XmlWriterOutputWithEncodingName >= 0 )
              {
                v8 = 0;
                v9 = (struct IDomNode *)*((_QWORD *)this + 2);
                if ( !v9 )
                  goto LABEL_13;
                XmlWriterOutputWithEncodingName = CWapDPU::PrintNodes(this, (struct IXmlWriter *)ppvObject, v9);
                if ( XmlWriterOutputWithEncodingName >= 0 )
                {
                  v8 = 1;
LABEL_13:
                  XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                  if ( XmlWriterOutputWithEncodingName >= 0 )
                  {
                    XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, __int64 *))(*(_QWORD *)ppstm + 40LL))(
                                                        ppstm,
                                                        v16,
                                                        1,
                                                        &v20);
                    if ( XmlWriterOutputWithEncodingName >= 0 )
                    {
                      if ( HIDWORD(v20) )
                      {
LABEL_16:
                        XmlWriterOutputWithEncodingName = 122;
                        goto LABEL_29;
                      }
                      *(_QWORD *)a2 = 0;
                      v10 = SysAllocStringLen(0, (unsigned int)v20 >> 1);
                      *(_QWORD *)a2 = v10;
                      if ( !v10 )
                        goto LABEL_18;
                      XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                                                          ppstm,
                                                          v16,
                                                          0,
                                                          0);
                      if ( XmlWriterOutputWithEncodingName >= 0 )
                      {
                        XmlWriterOutputWithEncodingName = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, int *))(*(_QWORD *)ppstm + 24LL))(
                                                            ppstm,
                                                            *(_QWORD *)a2,
                                                            (unsigned int)v20,
                                                            &v18);
                        if ( XmlWriterOutputWithEncodingName >= 0 )
                        {
                          if ( (_DWORD)v20 != v18 )
                            goto LABEL_16;
                          *((_DWORD *)a2 + 2) = *((_DWORD *)this + 10);
                          *((_QWORD *)a2 + 2) = 0;
                          v11 = *((_QWORD *)this + 7);
                          if ( v11 )
                          {
                            if ( *(_WORD *)v11 )
                            {
                              if ( !wcsncmp_0(*((const wchar_t **)this + 7), L"/wap-provisioningdoc/", 0x15u) )
                              {
                                v12 = SysAllocString((const OLECHAR *)(v11 + 42));
                                *((_QWORD *)a2 + 2) = v12;
                                if ( !v12 )
                                {
LABEL_18:
                                  XmlWriterOutputWithEncodingName = -2147024882;
                                  goto LABEL_29;
                                }
                                SysFreeString(*((BSTR *)this + 7));
                              }
                              else
                              {
                                *((_QWORD *)a2 + 2) = v11;
                              }
                              *((_QWORD *)this + 7) = 0;
                            }
                          }
                        }
                      }
                    }
                  }
LABEL_29:
                  if ( v8 )
                    goto LABEL_32;
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
    XmlWriterOutputWithEncodingName = -2147024809;
  }
  v13 = (struct IDomNode *)*((_QWORD *)this + 2);
  if ( v13 )
    CWapDPU::ClearNodeResultTrackers(this, v13);
LABEL_32:
  SysFreeString(*((BSTR *)this + 7));
  *((_QWORD *)this + 7) = 0;
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(ppOutput);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppvObject);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppstm);
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return (unsigned int)XmlWriterOutputWithEncodingName;
}

```

## disassembly

```asm
0x180028b20  push    rbp
0x180028b22  push    rbx
0x180028b23  push    rsi
0x180028b24  push    rdi
0x180028b25  push    r12
0x180028b27  push    r14
0x180028b29  push    r15
0x180028b2b  mov     rbp, rsp
0x180028b2e  sub     rsp, 50h
0x180028b32  mov     ebx, r8d
0x180028b35  mov     rsi, rdx
0x180028b38  mov     rdi, rcx
0x180028b3b  lea     r15, [rcx+48h]
0x180028b3f  mov     rcx, r15; lpCriticalSection
0x180028b42  call    cs:__imp_EnterCriticalSection
0x180028b49  nop     dword ptr [rax+rax+00h]
0x180028b4e  mov     [rbp+var_8], r15
0x180028b52  mov     [rbp+ppstm], 0
0x180028b5a  mov     [rbp+ppvObject], 0
0x180028b62  mov     [rbp+ppOutput], 0
0x180028b6a  mov     [rbp+var_18], 0
0x180028b72  mov     [rbp+arg_18], 0
0x180028b7a  mov     [rbp+arg_0], 0
0x180028b81  test    rsi, rsi
0x180028b84  jnz     short loc_180028B90
0x180028b86  mov     ebx, 80070057h
0x180028b8b  jmp     loc_180028DCD
0x180028b90  cmp     ebx, 18h
0x180028b93  jnz     short loc_180028B86
0x180028b95  lea     r8, [rbp+ppstm]; ppstm
0x180028b99  lea     r14d, [rbx-17h]
0x180028b9d  mov     edx, r14d; fDeleteOnRelease
0x180028ba0  xor     ecx, ecx; hGlobal
0x180028ba2  call    cs:__imp_CreateStreamOnHGlobal
0x180028ba9  nop     dword ptr [rax+rax+00h]
0x180028bae  mov     ebx, eax
0x180028bb0  test    eax, eax
0x180028bb2  js      loc_180028DCD
0x180028bb8  xor     r8d, r8d; pMalloc
0x180028bbb  lea     rdx, [rbp+ppvObject]; ppvObject
0x180028bbf  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180028bc6  call    cs:__imp_CreateXmlWriter
0x180028bcd  nop     dword ptr [rax+rax+00h]
0x180028bd2  mov     ebx, eax
0x180028bd4  test    eax, eax
0x180028bd6  js      loc_180028DCD
0x180028bdc  lea     r9, [rbp+ppOutput]; ppOutput
0x180028be0  lea     r8, pwszEncodingName; "UTF-16"
0x180028be7  xor     edx, edx; pMalloc
0x180028be9  mov     rcx, [rbp+ppstm]; pOutputStream
0x180028bed  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x180028bf4  nop     dword ptr [rax+rax+00h]
0x180028bf9  mov     ebx, eax
0x180028bfb  test    eax, eax
0x180028bfd  js      loc_180028DCD
0x180028c03  mov     rcx, [rbp+ppvObject]
0x180028c07  mov     rax, [rcx]
0x180028c0a  mov     rdx, [rbp+ppOutput]
0x180028c0e  mov     rax, [rax+18h]
0x180028c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c17  mov     ebx, eax
0x180028c19  test    eax, eax
0x180028c1b  js      loc_180028DCD
0x180028c21  mov     rcx, [rbp+ppvObject]
0x180028c25  mov     rax, [rcx]
0x180028c28  mov     r8d, r14d
0x180028c2b  lea     edx, [r14+2]
0x180028c2f  mov     rax, [rax+28h]
0x180028c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c38  mov     ebx, eax
0x180028c3a  test    eax, eax
0x180028c3c  js      loc_180028DCD
0x180028c42  mov     rcx, [rbp+ppvObject]
0x180028c46  mov     rax, [rcx]
0x180028c49  xor     r8d, r8d
0x180028c4c  lea     edx, [r14+1]
0x180028c50  mov     rax, [rax+28h]
0x180028c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c59  mov     ebx, eax
0x180028c5b  test    eax, eax
0x180028c5d  js      loc_180028DCD
0x180028c63  xor     r12d, r12d
0x180028c66  mov     r8, [rdi+10h]; struct IDomNode *
0x180028c6a  test    r8, r8
0x180028c6d  jz      short loc_180028C88
0x180028c6f  mov     rdx, [rbp+ppvObject]; struct IXmlWriter *
0x180028c73  mov     rcx, rdi; this
0x180028c76  call    ?PrintNodes@CWapDPU@@AEAAJPEAUIXmlWriter@@PEAUIDomNode@@@Z; CWapDPU::PrintNodes(IXmlWriter *,IDomNode *)
0x180028c7b  mov     ebx, eax
0x180028c7d  test    eax, eax
0x180028c7f  js      loc_180028DCD
0x180028c85  mov     r12d, r14d
0x180028c88  mov     rcx, [rbp+ppvObject]
0x180028c8c  mov     rax, [rcx]
0x180028c8f  mov     rax, [rax+0F8h]
0x180028c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c9b  mov     ebx, eax
0x180028c9d  test    eax, eax
0x180028c9f  js      loc_180028DC8
0x180028ca5  mov     rcx, [rbp+ppstm]
0x180028ca9  mov     rax, [rcx]
0x180028cac  lea     r9, [rbp+arg_18]
0x180028cb0  mov     r8d, r14d
0x180028cb3  mov     rdx, [rbp+var_18]
0x180028cb7  mov     rax, [rax+28h]
0x180028cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cc0  mov     ebx, eax
0x180028cc2  test    eax, eax
0x180028cc4  js      loc_180028DC8
0x180028cca  cmp     dword ptr [rbp+arg_18+4], 0
0x180028cce  jz      short loc_180028CDA
0x180028cd0  mov     ebx, 7Ah ; 'z'
0x180028cd5  jmp     loc_180028DC8
0x180028cda  mov     qword ptr [rsi], 0
0x180028ce1  mov     edx, dword ptr [rbp+arg_18]
0x180028ce4  shr     edx, 1; ui
0x180028ce6  xor     ecx, ecx; strIn
0x180028ce8  call    cs:__imp_SysAllocStringLen
0x180028cef  nop     dword ptr [rax+rax+00h]
0x180028cf4  mov     [rsi], rax
0x180028cf7  test    rax, rax
0x180028cfa  jnz     short loc_180028D06
0x180028cfc  mov     ebx, 8007000Eh
0x180028d01  jmp     loc_180028DC8
0x180028d06  mov     rcx, [rbp+ppstm]
0x180028d0a  mov     rax, [rcx]
0x180028d0d  xor     r9d, r9d
0x180028d10  xor     r8d, r8d
0x180028d13  mov     rdx, [rbp+var_18]
0x180028d17  mov     rax, [rax+28h]
0x180028d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d20  mov     ebx, eax
0x180028d22  test    eax, eax
0x180028d24  js      loc_180028DC8
0x180028d2a  mov     rcx, [rbp+ppstm]
0x180028d2e  mov     rax, [rcx]
0x180028d31  lea     r9, [rbp+arg_0]
0x180028d35  mov     r8d, dword ptr [rbp+arg_18]
0x180028d39  mov     rdx, [rsi]
0x180028d3c  mov     rax, [rax+18h]
0x180028d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d45  mov     ebx, eax
0x180028d47  test    eax, eax
0x180028d49  js      short loc_180028DC8
0x180028d4b  mov     eax, [rbp+arg_0]
0x180028d4e  cmp     dword ptr [rbp+arg_18], eax
0x180028d51  jnz     loc_180028CD0
0x180028d57  mov     eax, [rdi+28h]
0x180028d5a  mov     [rsi+8], eax
0x180028d5d  mov     qword ptr [rsi+10h], 0
0x180028d65  mov     r14, [rdi+38h]
0x180028d69  test    r14, r14
0x180028d6c  jz      short loc_180028DC8
0x180028d6e  xor     eax, eax
0x180028d70  cmp     ax, [r14]
0x180028d74  jz      short loc_180028DC8
0x180028d76  lea     r8d, [rax+15h]; MaxCount
0x180028d7a  lea     rdx, aWapProvisionin_1; "/wap-provisioningdoc/"
0x180028d81  mov     rcx, r14; String1
0x180028d84  call    wcsncmp_0
0x180028d89  test    eax, eax
0x180028d8b  jnz     short loc_180028DBC
0x180028d8d  lea     rcx, [r14+2Ah]; psz
0x180028d91  call    cs:__imp_SysAllocString
0x180028d98  nop     dword ptr [rax+rax+00h]
0x180028d9d  mov     [rsi+10h], rax
0x180028da1  test    rax, rax
0x180028da4  jz      loc_180028CFC
0x180028daa  mov     rcx, [rdi+38h]; bstrString
0x180028dae  call    cs:__imp_SysFreeString
0x180028db5  nop     dword ptr [rax+rax+00h]
0x180028dba  jmp     short loc_180028DC0
0x180028dbc  mov     [rsi+10h], r14
0x180028dc0  mov     qword ptr [rdi+38h], 0
0x180028dc8  test    r12d, r12d
0x180028dcb  jnz     short loc_180028DDE
0x180028dcd  mov     rdx, [rdi+10h]; struct IDomNode *
0x180028dd1  test    rdx, rdx
0x180028dd4  jz      short loc_180028DDE
0x180028dd6  mov     rcx, rdi; this
0x180028dd9  call    ?ClearNodeResultTrackers@CWapDPU@@AEAAJPEAUIDomNode@@@Z; CWapDPU::ClearNodeResultTrackers(IDomNode *)
0x180028dde  mov     rcx, [rdi+38h]; bstrString
0x180028de2  call    cs:__imp_SysFreeString
0x180028de9  nop     dword ptr [rax+rax+00h]
0x180028dee  mov     qword ptr [rdi+38h], 0
0x180028df6  lea     rcx, [rbp+ppOutput]
0x180028dfa  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180028dff  nop
0x180028e00  lea     rcx, [rbp+ppvObject]
0x180028e04  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180028e09  nop
0x180028e0a  lea     rcx, [rbp+ppstm]
0x180028e0e  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180028e13  nop
0x180028e14  test    r15, r15
0x180028e17  jz      short loc_180028E28
0x180028e19  mov     rcx, r15; lpCriticalSection
0x180028e1c  call    cs:__imp_LeaveCriticalSection
0x180028e23  nop     dword ptr [rax+rax+00h]
0x180028e28  mov     eax, ebx
0x180028e2a  add     rsp, 50h
0x180028e2e  pop     r15
0x180028e30  pop     r14
0x180028e32  pop     r12
0x180028e34  pop     rdi
0x180028e35  pop     rsi
0x180028e36  pop     rbx
0x180028e37  pop     rbp
0x180028e38  retn
```
