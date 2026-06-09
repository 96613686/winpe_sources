# publicdm::ResolutionToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x180020bd0`
- end: `0x180020ef1`
- name: `?ResolutionToPrintCapabilities@publicdm@@YAJAEAVCPrintCapsInfo@1@@Z`
- size: `801`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CPrintCapsInfo *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006344`
- `0x180006f80`
- `0x180007660`
- `0x18000b0a0`
- `0x18000e084`
- `0x18000f970`
- `0x1800103e8`
- `0x18001c37c`
- `0x180020bd0`
- `0x180023010`

## string_xrefs

- `0x180020c5a`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180020db8`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall publicdm::ResolutionToPrintCapabilities(publicdm *this, struct publicdm::CPrintCapsInfo *a2)
{
  __int64 v2; // rax
  __int64 v4; // rax
  int Feature; // ebx
  int *v6; // rsi
  const unsigned __int16 *v7; // r9
  int v8; // r8d
  int v9; // eax
  const unsigned __int16 *v10; // rsi
  int v11; // r14d
  int v12; // edx
  struct IXMLDOMElement **v14; // [rsp+20h] [rbp-A9h]
  struct IXMLDOMElement **v15; // [rsp+30h] [rbp-99h]
  struct IXMLDOMElement **v16; // [rsp+38h] [rbp-91h]
  struct IXMLDOMElement *v17; // [rsp+50h] [rbp-79h] BYREF
  __int64 v18; // [rsp+58h] [rbp-71h] BYREF
  struct IXMLDOMElement *v19[2]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int16 v20[64]; // [rsp+70h] [rbp-59h] BYREF

  v2 = *(_QWORD *)this;
  v19[0] = 0;
  v18 = 0;
  v4 = (*(__int64 (__fastcall **)(publicdm *, struct publicdm::CPrintCapsInfo *))(v2 + 16))(this, a2);
  Feature = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 104LL))(
              v4,
              *((_QWORD *)this + 2),
              &v18);
  if ( Feature >= 0 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18) )
  {
    Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                0,
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                L"PageResolution",
                v19);
    if ( Feature >= 0 )
      Feature = publicdm::WriteDisplayNameFromResourceString(
                  *((publicdm **)this + 14),
                  (struct NPrintTicketUtil::CPrintTicketWrapper *)v19[0],
                  *((struct IXMLDOMElement **)this + 12),
                  (HINSTANCE)0xFCE7);
    while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18) )
    {
      v17 = 0;
      v6 = (int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
      v8 = *v6;
      if ( *v6 < 0 )
      {
        v10 = 0;
        v11 = -1;
        v12 = 0;
        while ( !v10 )
        {
          if ( v8 == *((__int16 *)&qword_180025440 + 12 * v12) )
          {
            v10 = (const unsigned __int16 *)*((_QWORD *)&qword_180025440 + 3 * v12 + 1);
            v11 = v12;
          }
          if ( !*(&qword_180025440 + 12 * ++v12) )
          {
            if ( !v10 )
              goto LABEL_24;
            break;
          }
        }
        if ( Feature >= 0 )
        {
          Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                      *((__int64 ***)this + 14),
                      v19[0],
                      (struct IXMLDOMElement *)L"Option",
                      &qword_180025440,
                      &v17);
          if ( Feature >= 0 )
          {
            Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                        *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                        v17,
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        L"QualitativeResolution",
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        v10,
                        1,
                        v16);
            if ( Feature >= 0 )
            {
              v9 = publicdm::WriteDisplayNameFromResourceString(
                     *((publicdm **)this + 14),
                     (struct NPrintTicketUtil::CPrintTicketWrapper *)v17,
                     *((struct IXMLDOMElement **)this + 12),
                     (HINSTANCE)*((unsigned int *)&qword_180025440 + 6 * v11 + 4));
              goto LABEL_23;
            }
          }
        }
      }
      else if ( Feature >= 0 )
      {
        Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(
                    *((__int64 ***)this + 14),
                    v19[0],
                    (struct IXMLDOMElement *)L"Option",
                    v7,
                    &v17);
        if ( Feature >= 0 )
        {
          Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                      *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                      v17,
                      L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                      L"ResolutionX",
                      *v6,
                      1,
                      v15);
          if ( Feature >= 0 )
          {
            Feature = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                        *((NPrintTicketUtil::CPrintTicketWrapper **)this + 14),
                        v17,
                        L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                        L"ResolutionY",
                        v6[1],
                        1,
                        v15);
            if ( Feature >= 0 )
            {
              memset_0(v20, 0, sizeof(v20));
              LODWORD(v14) = v6[1];
              Feature = StringCchPrintfW(v20, 0x40u, L"%u x %u", (unsigned int)*v6, v14);
              if ( Feature >= 0 )
              {
                v16 = (struct IXMLDOMElement **)L"string";
                v15 = (struct IXMLDOMElement **)L"http://www.w3.org/2001/XMLSchema";
                v9 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, unsigned __int16 *, _DWORD))(**((_QWORD **)this + 14) + 8LL))(
                       *((_QWORD *)this + 14),
                       v17,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"DisplayName",
                       v20,
                       0);
LABEL_23:
                Feature = v9;
              }
            }
          }
        }
      }
LABEL_24:
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
    }
  }
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v19);
  return (unsigned int)Feature;
}

```

## disassembly

```asm
0x180020bd0  mov     [rsp-8+arg_8], rbx
0x180020bd5  mov     [rsp-8+arg_10], rsi
0x180020bda  push    rbp
0x180020bdb  push    rdi
0x180020bdc  push    r12
0x180020bde  push    r13
0x180020be0  push    r14
0x180020be2  lea     rbp, [rsp-37h]
0x180020be7  sub     rsp, 100h
0x180020bee  mov     rax, cs:__security_cookie
0x180020bf5  xor     rax, rsp
0x180020bf8  mov     [rbp+57h+var_30], rax
0x180020bfc  mov     rax, [rcx]
0x180020bff  xor     r12d, r12d
0x180020c02  mov     rdi, rcx
0x180020c05  mov     [rbp+57h+var_C0], r12
0x180020c09  mov     [rbp+57h+var_C8], r12
0x180020c0d  mov     rax, [rax+10h]
0x180020c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c16  mov     rdx, [rdi+10h]
0x180020c1a  lea     r8, [rbp+57h+var_C8]
0x180020c1e  mov     r9, rax
0x180020c21  mov     rcx, [rax]
0x180020c24  mov     rax, [rcx+68h]
0x180020c28  mov     rcx, r9
0x180020c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c30  mov     ebx, eax
0x180020c32  test    eax, eax
0x180020c34  js      loc_180020EB5
0x180020c3a  mov     rcx, [rbp+57h+var_C8]
0x180020c3e  mov     rdx, [rcx]
0x180020c41  mov     rax, [rdx+30h]
0x180020c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c4a  test    eax, eax
0x180020c4c  jz      loc_180020EB5
0x180020c52  mov     rcx, [rdi+70h]; this
0x180020c56  lea     rax, [rbp+57h+var_C0]
0x180020c5a  lea     r13, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020c61  mov     [rsp+120h+var_100], rax; unsigned int
0x180020c66  mov     r8, r13; unsigned __int16 *
0x180020c69  lea     r9, aPageresolution; "PageResolution"
0x180020c70  xor     edx, edx; struct IXMLDOMElement *
0x180020c72  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020c77  mov     ebx, eax
0x180020c79  test    eax, eax
0x180020c7b  js      short loc_180020C96
0x180020c7d  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x180020c81  mov     r9d, 0FCE7h; HINSTANCE
0x180020c87  mov     rdx, [rbp+57h+var_C0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180020c8b  mov     rcx, [rdi+70h]; this
0x180020c8f  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180020c94  mov     ebx, eax
0x180020c96  mov     rcx, [rbp+57h+var_C8]
0x180020c9a  mov     rax, [rcx]
0x180020c9d  mov     rax, [rax+30h]
0x180020ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca6  test    eax, eax
0x180020ca8  jz      loc_180020EB5
0x180020cae  mov     rcx, [rbp+57h+var_C8]
0x180020cb2  mov     [rbp+57h+var_D0], r12
0x180020cb6  mov     rax, [rcx]
0x180020cb9  mov     rax, [rax+20h]
0x180020cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cc2  mov     rsi, rax
0x180020cc5  mov     r8d, [rax]
0x180020cc8  test    r8d, r8d
0x180020ccb  js      loc_180020DE7
0x180020cd1  test    ebx, ebx
0x180020cd3  js      loc_180020EA7
0x180020cd9  mov     rdx, [rbp+57h+var_C0]; struct IXMLDOMElement *
0x180020cdd  lea     rax, [rbp+57h+var_D0]
0x180020ce1  mov     rcx, [rdi+70h]; this
0x180020ce5  lea     r8, aOption; "Option"
0x180020cec  mov     [rsp+120h+var_100], rax; struct IXMLDOMElement **
0x180020cf1  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020cf6  mov     ebx, eax
0x180020cf8  test    eax, eax
0x180020cfa  js      loc_180020EA7
0x180020d00  mov     eax, [rsi]
0x180020d02  lea     r9, aResolutionx; "ResolutionX"
0x180020d09  mov     rdx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x180020d0d  mov     r8, r13; unsigned __int16 *
0x180020d10  mov     rcx, [rdi+70h]; this
0x180020d14  mov     dword ptr [rsp+120h+var_F8], 1; int
0x180020d1c  mov     dword ptr [rsp+120h+var_100], eax; int
0x180020d20  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x180020d25  mov     ebx, eax
0x180020d27  test    eax, eax
0x180020d29  js      loc_180020EA7
0x180020d2f  mov     eax, [rsi+4]
0x180020d32  lea     r9, aResolutiony; "ResolutionY"
0x180020d39  mov     rdx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x180020d3d  mov     r8, r13; unsigned __int16 *
0x180020d40  mov     rcx, [rdi+70h]; this
0x180020d44  mov     dword ptr [rsp+120h+var_F8], 1; int
0x180020d4c  mov     dword ptr [rsp+120h+var_100], eax; int
0x180020d50  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x180020d55  mov     ebx, eax
0x180020d57  test    eax, eax
0x180020d59  js      loc_180020EA7
0x180020d5f  xor     edx, edx; Val
0x180020d61  lea     rcx, [rbp+57h+var_B0]; void *
0x180020d65  mov     r8d, 80h; Size
0x180020d6b  call    memset_0
0x180020d70  mov     eax, [rsi+4]
0x180020d73  lea     r8, aUXU; "%u x %u"
0x180020d7a  mov     r9d, [rsi]
0x180020d7d  lea     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180020d81  mov     edx, 40h ; '@'; unsigned __int64
0x180020d86  mov     dword ptr [rsp+120h+var_100], eax
0x180020d8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020d8f  mov     ebx, eax
0x180020d91  test    eax, eax
0x180020d93  js      loc_180020EA7
0x180020d99  mov     rcx, [rdi+70h]
0x180020d9d  lea     rdx, aString; "string"
0x180020da4  mov     [rsp+120h+var_E0], r12
0x180020da9  lea     r9, aDisplayname; "DisplayName"
0x180020db0  mov     [rsp+120h+var_E8], rdx
0x180020db5  mov     r8, r13
0x180020db8  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x180020dbf  mov     rax, [rcx]
0x180020dc2  mov     qword ptr [rsp+120h+var_F0], rdx
0x180020dc7  lea     rdx, [rbp+57h+var_B0]
0x180020dcb  mov     dword ptr [rsp+120h+var_F8], r12d
0x180020dd0  mov     [rsp+120h+var_100], rdx
0x180020dd5  mov     rax, [rax+8]
0x180020dd9  mov     rdx, [rbp+57h+var_D0]
0x180020ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020de2  jmp     loc_180020EA5
0x180020de7  mov     rsi, r12
0x180020dea  lea     r9, qword_180025440; unsigned __int16 *
0x180020df1  or      r14d, 0FFFFFFFFh
0x180020df5  mov     edx, r12d
0x180020df8  test    rsi, rsi
0x180020dfb  jnz     short loc_180020E2B
0x180020dfd  movsxd  rax, edx
0x180020e00  lea     rcx, [rax+rax*2]
0x180020e04  movsx   eax, word ptr [r9+rcx*8]
0x180020e09  cmp     r8d, eax
0x180020e0c  jnz     short loc_180020E16
0x180020e0e  mov     rsi, [r9+rcx*8+8]
0x180020e13  mov     r14d, edx
0x180020e16  inc     edx
0x180020e18  movsxd  rax, edx
0x180020e1b  lea     rcx, [rax+rax*2]
0x180020e1f  cmp     [r9+rcx*8], r12w
0x180020e24  jnz     short loc_180020DF8
0x180020e26  test    rsi, rsi
0x180020e29  jz      short loc_180020EA7
0x180020e2b  test    ebx, ebx
0x180020e2d  js      short loc_180020EA7
0x180020e2f  mov     rdx, [rbp+57h+var_C0]; struct IXMLDOMElement *
0x180020e33  lea     rax, [rbp+57h+var_D0]
0x180020e37  mov     rcx, [rdi+70h]; this
0x180020e3b  lea     r8, aOption; "Option"
0x180020e42  mov     [rsp+120h+var_100], rax; struct IXMLDOMElement **
0x180020e47  call    ?CreateXMLElement@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateXMLElement(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020e4c  mov     ebx, eax
0x180020e4e  test    eax, eax
0x180020e50  js      short loc_180020EA7
0x180020e52  mov     rdx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x180020e56  lea     r9, aQualitativeres; "QualitativeResolution"
0x180020e5d  mov     rcx, [rdi+70h]; this
0x180020e61  mov     r8, r13; unsigned __int16 *
0x180020e64  mov     [rsp+120h+var_F0], 1; int
0x180020e6c  mov     [rsp+120h+var_F8], rsi; unsigned __int16 *
0x180020e71  mov     [rsp+120h+var_100], r13; unsigned int
0x180020e76  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG111HPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x180020e7b  mov     ebx, eax
0x180020e7d  test    eax, eax
0x180020e7f  js      short loc_180020EA7
0x180020e81  mov     r8, [rdi+60h]; struct IXMLDOMElement *
0x180020e85  lea     r9, qword_180025440
0x180020e8c  mov     rdx, [rbp+57h+var_D0]; struct NPrintTicketUtil::CPrintTicketWrapper *
0x180020e90  movsxd  rax, r14d
0x180020e93  lea     rcx, [rax+rax*2]
0x180020e97  mov     r9d, [r9+rcx*8+10h]; HINSTANCE
0x180020e9c  mov     rcx, [rdi+70h]; this
0x180020ea0  call    ?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z; publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)
0x180020ea5  mov     ebx, eax
0x180020ea7  lea     rcx, [rbp+57h+var_D0]
0x180020eab  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020eb0  jmp     loc_180020C96
0x180020eb5  lea     rcx, [rbp+57h+var_C8]
0x180020eb9  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020ebe  lea     rcx, [rbp+57h+var_C0]
0x180020ec2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020ec7  mov     eax, ebx
0x180020ec9  mov     rcx, [rbp+57h+var_30]
0x180020ecd  xor     rcx, rsp; StackCookie
0x180020ed0  call    __security_check_cookie
0x180020ed5  lea     r11, [rsp+120h+var_20]
0x180020edd  mov     rbx, [r11+38h]
0x180020ee1  mov     rsi, [r11+40h]
0x180020ee5  mov     rsp, r11
0x180020ee8  pop     r14
0x180020eea  pop     r13
0x180020eec  pop     r12
0x180020eee  pop     rdi
0x180020eef  pop     rbp
0x180020ef0  retn
```
