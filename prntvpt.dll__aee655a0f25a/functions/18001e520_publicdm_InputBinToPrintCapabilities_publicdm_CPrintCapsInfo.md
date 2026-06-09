# publicdm::InputBinToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18001e520`
- end: `0x18001e7e5`
- name: `?InputBinToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `709`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800056e0`
- `0x180005e70`
- `0x180006344`
- `0x180006c74`
- `0x18000e084`
- `0x18000f370`
- `0x18001c514`
- `0x18001e520`
- `0x180023010`

## string_xrefs

- `0x18001e60c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001e778`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001e77f`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall publicdm::InputBinToPrintCapabilities(publicdm *this, struct publicdm::CPrintCapsInfo *a2)
{
  __int64 v2; // rax
  __int64 v4; // rax
  int PrintTicketNameFromDriverID; // r14d
  __int64 v6; // rax
  __int64 v7; // rsi
  unsigned int (__fastcall *v8)(__int64); // rdi
  int v9; // ebx
  int Feature; // eax
  struct IXMLDOMElement *v11; // r12
  unsigned int v12; // ebx
  unsigned __int16 **v13; // r8
  const unsigned __int16 *v14; // rsi
  int i; // edx
  struct IXMLDOMElement *v16; // rdi
  const unsigned __int16 *v17; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v18; // rbx
  const unsigned __int16 *v19; // rax
  unsigned int v21; // [rsp+20h] [rbp-48h]
  struct IXMLDOMElement *v22[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v23; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+50h] BYREF
  struct IXMLDOMElement *v25; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int16 *v26; // [rsp+C8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)this;
  v22[0] = 0;
  v23 = 0;
  v24 = 0;
  v4 = (*(__int64 (__fastcall **)(publicdm *, struct publicdm::CPrintCapsInfo *))(v2 + 16))(this, a2);
  PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 48LL))(
                                  v4,
                                  *((_QWORD *)this + 2),
                                  &v23);
  if ( PrintTicketNameFromDriverID >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
    PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 56LL))(
                                    v6,
                                    *((_QWORD *)this + 2),
                                    &v24);
    if ( PrintTicketNameFromDriverID >= 0 )
    {
      v7 = v23;
      v8 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL);
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 40LL))(v24);
      if ( v8(v7) != v9 )
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v24);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 48LL))(v23) )
      {
        Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                    *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                    0,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    L"JobInputBin",
                    v22);
        v11 = v22[0];
        PrintTicketNameFromDriverID = Feature;
        if ( Feature >= 0 )
          PrintTicketNameFromDriverID = publicdm::WriteDisplayNameFromResourceString(
                                          *((publicdm **)this + 14),
                                          (struct NPrintTicketUtil::CPrintTicketWrapper *)v22[0],
                                          *((struct IXMLDOMElement **)this + 12),
                                          (HINSTANCE)0xFCE5,
                                          v21);
        while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 48LL))(v23) )
        {
          v12 = *(__int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
          if ( v24 )
            v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
          else
            v14 = 0;
          v25 = 0;
          if ( (unsigned __int16)(v12 - 1) > 0xEu )
          {
            v26 = 0;
            PrintTicketNameFromDriverID = publicdm::CreatePrintTicketNameFromDriverID(
                                            (publicdm *)v12,
                                            (unsigned int)&v26,
                                            v13);
            if ( PrintTicketNameFromDriverID >= 0 )
            {
              v18 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 14);
              v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
              PrintTicketNameFromDriverID = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                                              v18,
                                              v11,
                                              v19,
                                              v26,
                                              &v25);
              if ( PrintTicketNameFromDriverID >= 0 )
                PrintTicketNameFromDriverID = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, const unsigned __int16 *, _DWORD, const char *, const char *, _QWORD))(**((_QWORD **)this + 14) + 8LL))(
                                                *((_QWORD *)this + 14),
                                                v25,
                                                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                                L"DisplayName",
                                                v14,
                                                0,
                                                L"http://www.w3.org/2001/XMLSchema",
                                                L"string",
                                                0);
            }
            NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v26);
          }
          else
          {
            for ( i = 0; ; ++i )
            {
              v16 = (struct IXMLDOMElement *)&word_180030850[24 * i];
              if ( SLOWORD(v16->lpVtbl) <= 0 )
                break;
              if ( LOWORD(v16->lpVtbl) == (_WORD)v12 )
              {
                v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
                PrintTicketNameFromDriverID = CreateStandardInputBinOption(
                                                *((struct NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                                                v16,
                                                *((HINSTANCE *)this + 12),
                                                v14,
                                                v17,
                                                v11,
                                                &v25);
                break;
              }
            }
          }
          NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v25);
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v24);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v23);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v22);
  return (unsigned int)PrintTicketNameFromDriverID;
}

```

## disassembly

```asm
0x18001e520  push    rbp
0x18001e522  push    rbx
0x18001e523  push    rsi
0x18001e524  push    rdi
0x18001e525  push    r12
0x18001e527  push    r13
0x18001e529  push    r14
0x18001e52b  push    r15
0x18001e52d  mov     rbp, rsp
0x18001e530  sub     rsp, 68h
0x18001e534  mov     rax, [rcx]
0x18001e537  xor     r13d, r13d
0x18001e53a  mov     r15, rcx
0x18001e53d  mov     [rbp+var_18], r13
0x18001e541  mov     [rbp+arg_0], r13
0x18001e545  mov     [rbp+arg_8], r13
0x18001e549  mov     rax, [rax+10h]
0x18001e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e552  mov     rdx, [r15+10h]
0x18001e556  lea     r8, [rbp+arg_0]
0x18001e55a  mov     r9, rax
0x18001e55d  mov     rcx, [rax]
0x18001e560  mov     rax, [rcx+30h]
0x18001e564  mov     rcx, r9
0x18001e567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e56c  mov     r14d, eax
0x18001e56f  test    eax, eax
0x18001e571  js      loc_18001E7B6
0x18001e577  mov     rax, [r15]
0x18001e57a  mov     rcx, r15
0x18001e57d  mov     rax, [rax+10h]
0x18001e581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e586  mov     rdx, [r15+10h]
0x18001e58a  lea     r8, [rbp+arg_8]
0x18001e58e  mov     r9, rax
0x18001e591  mov     rcx, [rax]
0x18001e594  mov     rax, [rcx+38h]
0x18001e598  mov     rcx, r9
0x18001e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a0  mov     r14d, eax
0x18001e5a3  test    eax, eax
0x18001e5a5  js      loc_18001E7B6
0x18001e5ab  mov     rsi, [rbp+arg_0]
0x18001e5af  mov     rcx, [rbp+arg_8]
0x18001e5b3  mov     rax, [rsi]
0x18001e5b6  mov     rdx, [rcx]
0x18001e5b9  mov     rdi, [rax+28h]
0x18001e5bd  mov     rax, [rdx+28h]
0x18001e5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5c6  mov     ebx, eax
0x18001e5c8  mov     rcx, rsi
0x18001e5cb  mov     rax, rdi
0x18001e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5d3  cmp     eax, ebx
0x18001e5d5  jz      short loc_18001E5E0
0x18001e5d7  lea     rcx, [rbp+arg_8]
0x18001e5db  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e5e0  mov     rcx, [rbp+arg_0]
0x18001e5e4  mov     rax, [rcx]
0x18001e5e7  mov     rax, [rax+30h]
0x18001e5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5f0  test    eax, eax
0x18001e5f2  jz      loc_18001E7B6
0x18001e5f8  mov     rcx, [r15+70h]; this
0x18001e5fc  lea     rax, [rbp+var_18]
0x18001e600  lea     r9, aJobinputbin; "JobInputBin"
0x18001e607  mov     [rsp+68h+var_48], rax; unsigned int
0x18001e60c  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001e613  xor     edx, edx; struct IXMLDOMElement *
0x18001e615  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001e61a  mov     r12, [rbp+var_18]
0x18001e61e  mov     r14d, eax
0x18001e621  test    eax, eax
0x18001e623  js      short loc_18001E63E
0x18001e625  mov     r8, [r15+60h]; struct IXMLDOMElement *
0x18001e629  mov     r9d, 0FCE5h; HINSTANCE
0x18001e62f  mov     rcx, [r15+70h]; this
0x18001e633  mov     rdx, r12; struct NPrintTicketUtil::CPrintTicketWrapper *
0x18001e636  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x18001e63b  mov     r14d, eax
0x18001e63e  mov     edi, 1
0x18001e643  mov     rcx, [rbp+arg_0]
0x18001e647  mov     rax, [rcx]
0x18001e64a  mov     rax, [rax+30h]
0x18001e64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e653  test    eax, eax
0x18001e655  jz      loc_18001E7B6
0x18001e65b  mov     rcx, [rbp+arg_0]
0x18001e65f  mov     rax, [rcx]
0x18001e662  mov     rax, [rax+20h]
0x18001e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e66b  mov     rcx, [rbp+arg_8]
0x18001e66f  movsx   ebx, word ptr [rax]
0x18001e672  test    rcx, rcx
0x18001e675  jz      short loc_18001E688
0x18001e677  mov     rax, [rcx]
0x18001e67a  mov     rax, [rax+20h]
0x18001e67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e683  mov     rsi, rax
0x18001e686  jmp     short loc_18001E68B
0x18001e688  mov     rsi, r13
0x18001e68b  movzx   eax, bx
0x18001e68e  mov     [rbp+arg_10], r13
0x18001e692  sub     ax, di
0x18001e695  cmp     ax, 0Eh
0x18001e699  ja      short loc_18001E70D
0x18001e69b  mov     edx, r13d
0x18001e69e  movsxd  rax, edx
0x18001e6a1  lea     rdi, [rax+rax*2]
0x18001e6a5  shl     rdi, 4
0x18001e6a9  lea     rax, word_180030850
0x18001e6b0  add     rdi, rax
0x18001e6b3  cmp     [rdi], r13w
0x18001e6b7  jle     short loc_18001E6FA
0x18001e6b9  cmp     [rdi], bx
0x18001e6bc  jz      short loc_18001E6C2
0x18001e6be  inc     edx
0x18001e6c0  jmp     short loc_18001E69E
0x18001e6c2  mov     rax, [r15]
0x18001e6c5  mov     rcx, r15
0x18001e6c8  mov     rax, [rax+8]
0x18001e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d1  mov     r8, [r15+60h]; HINSTANCE
0x18001e6d5  lea     rcx, [rbp+arg_10]
0x18001e6d9  mov     [rsp+68h+var_38], rcx; struct IXMLDOMElement **
0x18001e6de  mov     r9, rsi; unsigned __int16 *
0x18001e6e1  mov     rcx, [r15+70h]; this
0x18001e6e5  mov     rdx, rdi; struct IXMLDOMElement *
0x18001e6e8  mov     [rsp+68h+var_40], r12; struct IXMLDOMElement *
0x18001e6ed  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e6f2  call    ?CreateStandardInputBinOption@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUBinMappingEntry@publicdm@@PEAUHINSTANCE__@@PEBG3PEAUIXMLDOMElement@@PEAPEAU6@@Z; CreateStandardInputBinOption(NPrintTicketUtil::CPrintTicketWrapper *,publicdm::BinMappingEntry *,HINSTANCE__ *,ushort const *,ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18001e6f7  mov     r14d, eax
0x18001e6fa  mov     edi, 1
0x18001e6ff  lea     rcx, [rbp+arg_10]
0x18001e703  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e708  jmp     loc_18001E643
0x18001e70d  mov     ecx, ebx; this
0x18001e70f  mov     [rbp+arg_18], r13
0x18001e713  lea     rdx, [rbp+arg_18]; unsigned int
0x18001e717  call    ?CreatePrintTicketNameFromDriverID@publicdm@@YAJKPEAPEAG@Z; publicdm::CreatePrintTicketNameFromDriverID(ulong,ushort * *)
0x18001e71c  mov     r14d, eax
0x18001e71f  test    eax, eax
0x18001e721  js      loc_18001E7A8
0x18001e727  mov     rax, [r15]
0x18001e72a  mov     rcx, r15
0x18001e72d  mov     rbx, [r15+70h]
0x18001e731  mov     rax, [rax+8]
0x18001e735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e73a  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x18001e73e  lea     rcx, [rbp+arg_10]
0x18001e742  mov     [rsp+68h+var_48], rcx; struct IXMLDOMElement **
0x18001e747  mov     r8, rax; unsigned __int16 *
0x18001e74a  mov     rcx, rbx; this
0x18001e74d  mov     rdx, r12; struct IXMLDOMElement *
0x18001e750  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001e755  mov     r14d, eax
0x18001e758  test    eax, eax
0x18001e75a  js      short loc_18001E7A8
0x18001e75c  mov     rcx, [r15+70h]
0x18001e760  lea     rdx, aString; "string"
0x18001e767  mov     [rsp+68h+var_28], r13
0x18001e76c  lea     r9, aDisplayname; "DisplayName"
0x18001e773  mov     [rsp+68h+var_30], rdx
0x18001e778  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001e77f  lea     rdx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001e786  mov     rax, [rcx]
0x18001e789  mov     [rsp+68h+var_38], rdx
0x18001e78e  mov     rdx, [rbp+arg_10]
0x18001e792  mov     dword ptr [rsp+68h+var_40], r13d
0x18001e797  mov     rax, [rax+8]
0x18001e79b  mov     [rsp+68h+var_48], rsi
0x18001e7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7a5  mov     r14d, eax
0x18001e7a8  lea     rcx, [rbp+arg_18]
0x18001e7ac  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001e7b1  jmp     loc_18001E6FF
0x18001e7b6  lea     rcx, [rbp+arg_8]
0x18001e7ba  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e7bf  lea     rcx, [rbp+arg_0]
0x18001e7c3  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e7c8  lea     rcx, [rbp+var_18]
0x18001e7cc  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001e7d1  mov     eax, r14d
0x18001e7d4  add     rsp, 68h
0x18001e7d8  pop     r15
0x18001e7da  pop     r14
0x18001e7dc  pop     r13
0x18001e7de  pop     r12
0x18001e7e0  pop     rdi
0x18001e7e1  pop     rsi
0x18001e7e2  pop     rbx
0x18001e7e3  pop     rbp
0x18001e7e4  retn
```
