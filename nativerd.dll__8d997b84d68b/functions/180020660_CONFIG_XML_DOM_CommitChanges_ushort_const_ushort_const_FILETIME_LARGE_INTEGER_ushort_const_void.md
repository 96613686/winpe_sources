# CONFIG_XML_DOM::CommitChanges(ushort const *,ushort const *,_FILETIME *,_LARGE_INTEGER *,ushort const *,void *)

- ea: `0x180020660`
- end: `0x1800208bd`
- name: `?CommitChanges@CONFIG_XML_DOM@@UEAAJPEBG0PEAU_FILETIME@@PEAT_LARGE_INTEGER@@0PEAX@Z`
- size: `605`
- prototype: `__int64 __fastcall(CONFIG_XML_DOM *this, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME *, union _LARGE_INTEGER *, unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001c250`
- `0x180020660`
- `0x18002195c`
- `0x180021ad0`
- `0x1800228ec`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800206c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800206c3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180020731`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180020731`
- `XmlLite!CreateXmlWriter` at `0x1800206d7`
- `XmlLite!CreateXmlWriter` at `0x1800206d7`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180020755`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180020755`

## pseudocode

```c
__int64 __fastcall CONFIG_XML_DOM::CommitChanges(
        CONFIG_XML_DOM *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4,
        union _LARGE_INTEGER *a5,
        unsigned __int16 *a6,
        void *a7)
{
  unsigned __int16 *v11; // r14
  IUnknown *v12; // rbx
  int v13; // edi
  const WCHAR *v14; // r8
  bool v15; // zf
  PREAMBLE_LIST *v16; // rcx
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-20h] BYREF
  struct IXmlWriter *v20; // [rsp+50h] [rbp-18h] BYREF
  void *ppvObject; // [rsp+C0h] [rbp+58h] BYREF

  ppvObject = 0;
  ppOutput = 0;
  ppv = 0;
  if ( a3 && (v11 = a6) != 0 )
  {
    v12 = 0;
    CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage3, &ppv);
    v13 = CreateXmlWriter(&stru_180060850, &ppvObject, 0);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 0, ppv);
      if ( v13 >= 0 )
      {
        v12 = (IUnknown *)operator new(0x40u);
        if ( v12 )
        {
          v12[1].lpVtbl = (struct IUnknownVtbl *)1;
          v12->lpVtbl = (struct IUnknownVtbl *)&XML_WRITE_BUFFER::`vftable';
          BUFFER::BUFFER((BUFFER *)&v12[2]);
          v14 = &szDomain;
          if ( *((_QWORD *)this + 16) )
            v14 = (const WCHAR *)*((_QWORD *)this + 16);
          v13 = CreateXmlWriterOutputWithEncodingName(v12, 0, v14, &ppOutput);
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(
                    ppvObject,
                    ppOutput);
            if ( v13 >= 0 )
            {
              if ( !ppvObject
                || ((v15 = (*((_BYTE *)this + 12) & 4) == 0, v20 = (struct IXmlWriter *)ppvObject, v15)
                 || (v13 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 0),
                     v13 >= 0))
                && (v13 = CONFIG_DOM_NODE::CommitChanges(*((CONFIG_DOM_NODE **)this + 15), (struct XML_WRITER *)&v20, 0),
                    v13 >= 0)
                && ((v16 = (PREAMBLE_LIST *)*((_QWORD *)this + 17)) == 0
                 || (v13 = PREAMBLE_LIST::Write(v16, v20), v13 >= 0)) )
              {
                ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
                ppOutput = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                v13 = CONFIG_XML_DOM::WriteBufferToDisk(
                        (struct XML_WRITE_BUFFER *)v12,
                        a2,
                        a3,
                        a4,
                        a5,
                        v11,
                        (__int64)a7);
              }
            }
          }
        }
        else
        {
          v13 = -2147024888;
          v12 = 0;
        }
      }
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( v12 )
      ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180020660  push    rbp
0x180020662  push    rbx
0x180020663  push    rsi
0x180020664  push    rdi
0x180020665  push    r12
0x180020667  push    r13
0x180020669  push    r14
0x18002066b  push    r15
0x18002066d  mov     rbp, rsp
0x180020670  sub     rsp, 68h
0x180020674  xor     eax, eax
0x180020676  mov     r12, r9
0x180020679  mov     [rbp+ppvObject], rax
0x18002067d  mov     r15, r8
0x180020680  mov     [rbp+ppOutput], rax
0x180020684  mov     r13, rdx
0x180020687  mov     [rbp+var_20], rax
0x18002068b  mov     rsi, rcx
0x18002068e  test    r8, r8
0x180020691  jz      loc_1800208A5
0x180020697  mov     r14, [rbp+arg_28]
0x18002069b  test    r14, r14
0x18002069e  jz      loc_1800208A5
0x1800206a4  mov     ebx, eax
0x1800206a6  lea     r9, IID_IMultiLanguage3; riid
0x1800206ad  lea     rax, [rbp+var_20]
0x1800206b1  xor     edx, edx; pUnkOuter
0x1800206b3  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1800206ba  mov     [rsp+68h+ppv], rax; ppv
0x1800206bf  lea     r8d, [rbx+1]; dwClsContext
0x1800206c3  call    cs:__imp_CoCreateInstance
0x1800206c9  xor     r8d, r8d; pMalloc
0x1800206cc  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800206d0  lea     rcx, stru_180060850; riid
0x1800206d7  call    cs:__imp_CreateXmlWriter
0x1800206dd  mov     edi, eax
0x1800206df  test    eax, eax
0x1800206e1  js      loc_180020840
0x1800206e7  mov     rcx, [rbp+ppvObject]
0x1800206eb  xor     edx, edx
0x1800206ed  mov     r8, [rbp+var_20]
0x1800206f1  mov     rax, [rcx]
0x1800206f4  mov     rax, [rax+28h]
0x1800206f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206fd  mov     edi, eax
0x1800206ff  test    eax, eax
0x180020701  js      loc_180020840
0x180020707  lea     ecx, [rbx+40h]; Size
0x18002070a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002070f  mov     rbx, rax
0x180020712  test    rax, rax
0x180020715  jz      loc_180020839
0x18002071b  lea     rax, ??_7XML_WRITE_BUFFER@@6B@; const XML_WRITE_BUFFER::`vftable'
0x180020722  mov     qword ptr [rbx+8], 1
0x18002072a  lea     rcx, [rbx+10h]
0x18002072e  mov     [rbx], rax
0x180020731  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180020737  mov     rax, [rsi+80h]
0x18002073e  lea     r8, szDomain
0x180020745  test    rax, rax
0x180020748  lea     r9, [rbp+ppOutput]; ppOutput
0x18002074c  mov     rcx, rbx; pOutputStream
0x18002074f  cmovnz  r8, rax; pwszEncodingName
0x180020753  xor     edx, edx; pMalloc
0x180020755  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18002075b  mov     edi, eax
0x18002075d  test    eax, eax
0x18002075f  js      loc_180020840
0x180020765  mov     rcx, [rbp+ppvObject]
0x180020769  mov     rdx, [rbp+ppOutput]
0x18002076d  mov     rax, [rcx]
0x180020770  mov     rax, [rax+18h]
0x180020774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020779  mov     edi, eax
0x18002077b  test    eax, eax
0x18002077d  js      loc_180020840
0x180020783  mov     rcx, [rbp+ppvObject]
0x180020787  test    rcx, rcx
0x18002078a  jz      short loc_1800207E2
0x18002078c  test    byte ptr [rsi+0Ch], 4
0x180020790  mov     [rbp+var_18], rcx
0x180020794  jz      short loc_1800207B1
0x180020796  mov     rax, [rcx]
0x180020799  xor     edx, edx
0x18002079b  mov     rax, [rax+0D0h]
0x1800207a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207a7  mov     edi, eax
0x1800207a9  test    eax, eax
0x1800207ab  js      loc_180020840
0x1800207b1  mov     rcx, [rsi+78h]; this
0x1800207b5  lea     rdx, [rbp+var_18]; struct XML_WRITER *
0x1800207b9  xor     r8d, r8d; unsigned __int16
0x1800207bc  call    ?CommitChanges@CONFIG_DOM_NODE@@QEAAJPEAVXML_WRITER@@G@Z; CONFIG_DOM_NODE::CommitChanges(XML_WRITER *,ushort)
0x1800207c1  mov     edi, eax
0x1800207c3  test    eax, eax
0x1800207c5  js      short loc_180020840
0x1800207c7  mov     rcx, [rsi+88h]; this
0x1800207ce  test    rcx, rcx
0x1800207d1  jz      short loc_1800207E2
0x1800207d3  mov     rdx, [rbp+var_18]; struct IXmlWriter *
0x1800207d7  call    ?Write@PREAMBLE_LIST@@QEAAJPEAUIXmlWriter@@@Z; PREAMBLE_LIST::Write(IXmlWriter *)
0x1800207dc  mov     edi, eax
0x1800207de  test    eax, eax
0x1800207e0  js      short loc_180020840
0x1800207e2  mov     rcx, [rbp+ppOutput]
0x1800207e6  mov     rax, [rcx]
0x1800207e9  mov     rax, [rax+10h]
0x1800207ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207f2  mov     rcx, [rbp+ppvObject]
0x1800207f6  mov     [rbp+ppOutput], 0
0x1800207fe  mov     rax, [rcx]
0x180020801  mov     rax, [rax+0F8h]
0x180020808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002080d  mov     rax, [rbp+arg_30]
0x180020811  mov     r9, r12; struct _FILETIME *
0x180020814  mov     [rsp+68h+var_38], rax; void *
0x180020819  mov     r8, r15; unsigned __int16 *
0x18002081c  mov     rax, [rbp+arg_20]
0x180020820  mov     rdx, r13; unsigned __int16 *
0x180020823  mov     [rsp+68h+var_40], r14; unsigned __int16 *
0x180020828  mov     rcx, rbx; struct XML_WRITE_BUFFER *
0x18002082b  mov     [rsp+68h+ppv], rax; union _LARGE_INTEGER *
0x180020830  call    ?WriteBufferToDisk@CONFIG_XML_DOM@@SAJPEAVXML_WRITE_BUFFER@@PEBG1PEAU_FILETIME@@PEAT_LARGE_INTEGER@@1PEAX@Z; CONFIG_XML_DOM::WriteBufferToDisk(XML_WRITE_BUFFER *,ushort const *,ushort const *,_FILETIME *,_LARGE_INTEGER *,ushort const *,void *)
0x180020835  mov     edi, eax
0x180020837  jmp     short loc_180020840
0x180020839  mov     edi, 80070008h
0x18002083e  xor     ebx, ebx
0x180020840  mov     rcx, [rbp+var_20]
0x180020844  test    rcx, rcx
0x180020847  jz      short loc_18002085D
0x180020849  mov     rax, [rcx]
0x18002084c  mov     rax, [rax+10h]
0x180020850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020855  mov     [rbp+var_20], 0
0x18002085d  mov     rcx, [rbp+ppvObject]
0x180020861  test    rcx, rcx
0x180020864  jz      short loc_18002087A
0x180020866  mov     rax, [rcx]
0x180020869  mov     rax, [rax+10h]
0x18002086d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020872  mov     [rbp+ppvObject], 0
0x18002087a  test    rbx, rbx
0x18002087d  jz      short loc_18002088E
0x18002087f  mov     rax, [rbx]
0x180020882  mov     rcx, rbx
0x180020885  mov     rax, [rax+10h]
0x180020889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002088e  mov     rcx, [rbp+ppOutput]
0x180020892  test    rcx, rcx
0x180020895  jz      short loc_1800208AA
0x180020897  mov     rax, [rcx]
0x18002089a  mov     rax, [rax+10h]
0x18002089e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a3  jmp     short loc_1800208AA
0x1800208a5  mov     edi, 80070057h
0x1800208aa  mov     eax, edi
0x1800208ac  add     rsp, 68h
0x1800208b0  pop     r15
0x1800208b2  pop     r14
0x1800208b4  pop     r13
0x1800208b6  pop     r12
0x1800208b8  pop     rdi
0x1800208b9  pop     rsi
0x1800208ba  pop     rbx
0x1800208bb  pop     rbp
0x1800208bc  retn
```
