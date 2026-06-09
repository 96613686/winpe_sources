# publicdm::ResolutionPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x180020910`
- end: `0x180020bc7`
- name: `?ResolutionPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `695`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180002084`
- `0x1800056e0`
- `0x180005e70`
- `0x18000e364`
- `0x18001d7c0`
- `0x18001ddc4`
- `0x180020910`

## string_xrefs

- `0x18002094c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ResolutionPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v4; // rcx
  struct IXMLDOMElement *v5; // rsi
  struct IXMLDOMElement *v6; // r14
  NPrintTicketUtil::CPrintTicketWrapper *v7; // rcx
  int Feature; // edi
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r9
  int v11; // r12d
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rcx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r8
  int v15; // edx
  int v16; // ecx
  int v17; // r9d
  char *v18; // rax
  signed __int64 v19; // r10
  int v20; // ecx
  int v21; // edx
  NPrintTicketUtil::CPrintTicketWrapper *v22; // rcx
  const unsigned __int16 *v23; // r8
  __int64 v24; // rax
  __int16 v25; // r14
  __int64 v26; // rax
  unsigned int v27; // ebx
  int v28; // [rsp+20h] [rbp-38h]
  struct IXMLDOMElement *v29; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMElement *v30[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int16 *v31; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+A8h] [rbp+50h] BYREF
  int v33; // [rsp+B0h] [rbp+58h] BYREF
  struct IXMLDOMElement *v34; // [rsp+B8h] [rbp+60h] BYREF

  if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 72LL) & 0x400) == 0 && !*((_DWORD *)this + 16) )
    return 0;
  v4 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v30[0] = 0;
  v29 = 0;
  v34 = 0;
  v5 = 0;
  v6 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v4,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageResolution",
              v30);
  if ( Feature >= 0 )
  {
    if ( v30[0] )
    {
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v7, v30[0], (char *)L"Option", v10, &v29);
      if ( Feature < 0 )
        goto LABEL_35;
      v5 = v29;
    }
    if ( !v5 )
    {
LABEL_11:
      v11 = 0;
      if ( !v6 )
        goto LABEL_40;
      v12 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
      v32 = 0;
      v31 = 0;
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(v12, v6, &v32, &v31, v28);
      if ( Feature >= 0 )
      {
        v13 = v32;
        if ( v32 )
        {
          v14 = v31;
          if ( v31 )
          {
            do
            {
              v15 = *(unsigned __int16 *)((char *)v13
                                        + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"
                                        - (char *)v32);
              v16 = *v13 - v15;
              if ( v16 )
                break;
              ++v13;
            }
            while ( v15 );
            if ( !v16 )
            {
              v17 = 0;
              do
              {
                if ( v11 )
                  break;
                v18 = (char *)*((_QWORD *)&qword_180025440 + 3 * v17 + 1);
                v19 = (char *)v14 - v18;
                do
                {
                  v20 = *(unsigned __int16 *)&v18[v19];
                  v21 = *(unsigned __int16 *)v18 - v20;
                  if ( v21 )
                    break;
                  v18 += 2;
                }
                while ( v20 );
                if ( !v21 )
                {
                  v11 = 1;
                  *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x400u;
                  *(_WORD *)(*((_QWORD *)this + 2) + 90LL) = *(&qword_180025440 + 12 * v17);
                }
                ++v17;
              }
              while ( *(&qword_180025440 + 12 * v17) );
            }
          }
        }
      }
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v32);
      if ( Feature >= 0 )
      {
LABEL_40:
        if ( v5 )
        {
          if ( !v11 )
          {
            v22 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
            LODWORD(v32) = 0;
            v33 = 0;
            LODWORD(v31) = 0;
            Feature = NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
                        v22,
                        v5,
                        v9,
                        L"ResolutionX",
                        (int *)&v32,
                        (int *)&v31);
            if ( Feature >= 0 )
            {
              if ( (_DWORD)v31 )
              {
                v24 = *((_QWORD *)this + 2);
                v25 = (__int16)v32;
                LODWORD(v31) = 0;
                *(_DWORD *)(v24 + 72) |= 0x400u;
                *(_WORD *)(*((_QWORD *)this + 2) + 90LL) = v25;
                Feature = NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
                            *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                            v5,
                            v23,
                            L"ResolutionY",
                            &v33,
                            (int *)&v31);
                if ( Feature >= 0 )
                {
                  v26 = *((_QWORD *)this + 2);
                  if ( (_DWORD)v31 )
                  {
                    *(_DWORD *)(v26 + 72) |= 0x2000u;
                    *(_WORD *)(*((_QWORD *)this + 2) + 96LL) = v33;
                  }
                  else
                  {
                    *(_DWORD *)(v26 + 72) &= ~0x2000u;
                    *(_WORD *)(*((_QWORD *)this + 2) + 96LL) = v25;
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_35;
    }
    Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                v5,
                L"ScoredProperty",
                v10,
                (char *)L"QualitativeResolution",
                L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                &v34);
    if ( Feature >= 0 )
    {
      v6 = v34;
      goto LABEL_11;
    }
  }
LABEL_35:
  v27 = 0;
  if ( Feature < 0 )
    v27 = Feature;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v34);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v29);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v30);
  return v27;
}

```

## disassembly

```asm
0x180020910  push    rbp
0x180020912  push    rbx
0x180020913  push    rsi
0x180020914  push    rdi
0x180020915  push    r12
0x180020917  push    r13
0x180020919  push    r14
0x18002091b  push    r15
0x18002091d  mov     rbp, rsp
0x180020920  sub     rsp, 58h
0x180020924  mov     rax, [rcx+10h]
0x180020928  xor     r13d, r13d
0x18002092b  mov     rbx, rcx
0x18002092e  test    dword ptr [rax+48h], 400h
0x180020935  jnz     short loc_180020944
0x180020937  cmp     [rcx+40h], r13d
0x18002093b  jnz     short loc_180020944
0x18002093d  xor     eax, eax
0x18002093f  jmp     loc_180020BB6
0x180020944  mov     rcx, [rcx+60h]; this
0x180020948  lea     rax, [rbp+var_10]
0x18002094c  lea     r15, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020953  mov     [rbp+var_10], r13
0x180020957  mov     r8, r15; unsigned __int16 *
0x18002095a  mov     [rbp+var_18], r13
0x18002095e  lea     r9, aPageresolution; "PageResolution"
0x180020965  mov     [rbp+arg_18], r13
0x180020969  xor     edx, edx; struct IXMLDOMElement *
0x18002096b  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x180020970  mov     rsi, r13
0x180020973  mov     r14, r13
0x180020976  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002097b  mov     edi, eax
0x18002097d  test    eax, eax
0x18002097f  js      loc_180020B91
0x180020985  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x180020989  test    rdx, rdx
0x18002098c  jz      short loc_1800209B1
0x18002098e  lea     rax, [rbp+var_18]
0x180020992  lea     r8, aOption; "Option"
0x180020999  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18002099e  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800209a3  mov     edi, eax
0x1800209a5  test    eax, eax
0x1800209a7  js      loc_180020B91
0x1800209ad  mov     rsi, [rbp+var_18]
0x1800209b1  test    rsi, rsi
0x1800209b4  jz      short loc_1800209F1
0x1800209b6  mov     rcx, [rbx+60h]; this
0x1800209ba  lea     rax, [rbp+arg_18]
0x1800209be  mov     [rsp+58h+var_28], rax; struct IXMLDOMElement **
0x1800209c3  lea     r8, aScoredproperty_0; "ScoredProperty"
0x1800209ca  lea     rax, aQualitativeres; "QualitativeResolution"
0x1800209d1  mov     [rsp+58h+var_30], r15; unsigned __int16 *
0x1800209d6  mov     rdx, rsi; struct IXMLDOMElement *
0x1800209d9  mov     [rsp+58h+var_38], rax; int
0x1800209de  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800209e3  mov     edi, eax
0x1800209e5  test    eax, eax
0x1800209e7  js      loc_180020B91
0x1800209ed  mov     r14, [rbp+arg_18]
0x1800209f1  mov     r12d, r13d
0x1800209f4  test    r14, r14
0x1800209f7  jz      loc_180020AD2
0x1800209fd  mov     rcx, [rbx+60h]; this
0x180020a01  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x180020a05  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180020a09  mov     [rbp+arg_8], r13
0x180020a0d  mov     rdx, r14; struct IXMLDOMElement *
0x180020a10  mov     [rbp+arg_0], r13
0x180020a14  call    ?GetValueAsQName@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsQName(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180020a19  mov     edi, eax
0x180020a1b  test    eax, eax
0x180020a1d  js      loc_180020AB8
0x180020a23  mov     rax, [rbp+arg_8]
0x180020a27  test    rax, rax
0x180020a2a  jz      loc_180020AB8
0x180020a30  mov     r8, [rbp+arg_0]
0x180020a34  test    r8, r8
0x180020a37  jz      short loc_180020AB8
0x180020a39  sub     r15, rax
0x180020a3c  movzx   ecx, word ptr [rax]
0x180020a3f  movzx   edx, word ptr [rax+r15]
0x180020a44  sub     ecx, edx
0x180020a46  jnz     short loc_180020A50
0x180020a48  add     rax, 2
0x180020a4c  test    edx, edx
0x180020a4e  jnz     short loc_180020A3C
0x180020a50  test    ecx, ecx
0x180020a52  jnz     short loc_180020AB8
0x180020a54  mov     r9d, r13d
0x180020a57  lea     r14, qword_180025440
0x180020a5e  test    r12d, r12d
0x180020a61  jnz     short loc_180020AB8
0x180020a63  movsxd  rax, r9d
0x180020a66  mov     r10, r8
0x180020a69  lea     r11, [rax+rax*2]
0x180020a6d  mov     rax, [r14+r11*8+8]
0x180020a72  sub     r10, rax
0x180020a75  movzx   edx, word ptr [rax]
0x180020a78  movzx   ecx, word ptr [rax+r10]
0x180020a7d  sub     edx, ecx
0x180020a7f  jnz     short loc_180020A89
0x180020a81  add     rax, 2
0x180020a85  test    ecx, ecx
0x180020a87  jnz     short loc_180020A75
0x180020a89  test    edx, edx
0x180020a8b  jnz     short loc_180020AA7
0x180020a8d  mov     rax, [rbx+10h]
0x180020a91  lea     r12d, [rdx+1]
0x180020a95  bts     dword ptr [rax+48h], 0Ah
0x180020a9a  mov     rcx, [rbx+10h]
0x180020a9e  movzx   eax, word ptr [r14+r11*8]
0x180020aa3  mov     [rcx+5Ah], ax
0x180020aa7  inc     r9d
0x180020aaa  movsxd  rax, r9d
0x180020aad  lea     rcx, [rax+rax*2]
0x180020ab1  cmp     [r14+rcx*8], r13w
0x180020ab6  jnz     short loc_180020A5E
0x180020ab8  lea     rcx, [rbp+arg_0]
0x180020abc  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180020ac1  lea     rcx, [rbp+arg_8]
0x180020ac5  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180020aca  test    edi, edi
0x180020acc  js      loc_180020B91
0x180020ad2  test    rsi, rsi
0x180020ad5  jz      loc_180020B91
0x180020adb  test    r12d, r12d
0x180020ade  jnz     loc_180020B91
0x180020ae4  mov     rcx, [rbx+60h]; this
0x180020ae8  lea     rax, [rbp+arg_0]
0x180020aec  mov     [rsp+58h+var_30], rax; int *
0x180020af1  lea     r9, aResolutionx; "ResolutionX"
0x180020af8  lea     rax, [rbp+arg_8]
0x180020afc  mov     dword ptr [rbp+arg_8], r13d
0x180020b00  mov     rdx, rsi; struct IXMLDOMElement *
0x180020b03  mov     [rsp+58h+var_38], rax; int *
0x180020b08  mov     [rbp+arg_10], r13d
0x180020b0c  mov     dword ptr [rbp+arg_0], r13d
0x180020b10  call    ?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)
0x180020b15  mov     edi, eax
0x180020b17  test    eax, eax
0x180020b19  js      short loc_180020B91
0x180020b1b  cmp     dword ptr [rbp+arg_0], r13d
0x180020b1f  jz      short loc_180020B91
0x180020b21  mov     rax, [rbx+10h]
0x180020b25  lea     r9, aResolutiony; "ResolutionY"
0x180020b2c  mov     r14d, dword ptr [rbp+arg_8]
0x180020b30  mov     rdx, rsi; struct IXMLDOMElement *
0x180020b33  mov     dword ptr [rbp+arg_0], r13d
0x180020b37  bts     dword ptr [rax+48h], 0Ah
0x180020b3c  mov     rax, [rbx+10h]
0x180020b40  mov     [rax+5Ah], r14w
0x180020b45  lea     rax, [rbp+arg_0]
0x180020b49  mov     rcx, [rbx+60h]; this
0x180020b4d  mov     [rsp+58h+var_30], rax; int *
0x180020b52  lea     rax, [rbp+arg_10]
0x180020b56  mov     [rsp+58h+var_38], rax; int *
0x180020b5b  call    ?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)
0x180020b60  mov     edi, eax
0x180020b62  test    eax, eax
0x180020b64  js      short loc_180020B91
0x180020b66  mov     rax, [rbx+10h]
0x180020b6a  cmp     dword ptr [rbp+arg_0], r13d
0x180020b6e  jz      short loc_180020B83
0x180020b70  bts     dword ptr [rax+48h], 0Dh
0x180020b75  mov     rcx, [rbx+10h]
0x180020b79  movzx   eax, word ptr [rbp+arg_10]
0x180020b7d  mov     [rcx+60h], ax
0x180020b81  jmp     short loc_180020B91
0x180020b83  btr     dword ptr [rax+48h], 0Dh
0x180020b88  mov     rax, [rbx+10h]
0x180020b8c  mov     [rax+60h], r14w
0x180020b91  test    edi, edi
0x180020b93  lea     rcx, [rbp+arg_18]
0x180020b97  mov     ebx, r13d
0x180020b9a  cmovs   ebx, edi
0x180020b9d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020ba2  lea     rcx, [rbp+var_18]
0x180020ba6  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020bab  lea     rcx, [rbp+var_10]
0x180020baf  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020bb4  mov     eax, ebx
0x180020bb6  add     rsp, 58h
0x180020bba  pop     r15
0x180020bbc  pop     r14
0x180020bbe  pop     r13
0x180020bc0  pop     r12
0x180020bc2  pop     rdi
0x180020bc3  pop     rsi
0x180020bc4  pop     rbx
0x180020bc5  pop     rbp
0x180020bc6  retn
```
