# publicdm::TrueTypePrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x180021a90`
- end: `0x180021d99`
- name: `?TrueTypePrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `777`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002084`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x18000e364`
- `0x180021a90`

## string_xrefs

- `0x180021ab6`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::TrueTypePrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v3; // rcx
  struct IXMLDOMElement *v4; // rbx
  struct IXMLDOMElement *v5; // rsi
  NPrintTicketUtil::CPrintTicketWrapper *v6; // rcx
  int Feature; // edi
  const unsigned __int16 *v8; // r9
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  int v10; // r14d
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // eax
  __int16 v17; // bx
  NPrintTicketUtil::CPrintTicketWrapper *v18; // rcx
  const unsigned __int16 *v19; // r9
  NPrintTicketUtil::CPrintTicketWrapper *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rax
  int v23; // r8d
  int v24; // edx
  unsigned __int16 *v25; // rcx
  int v26; // r9d
  int v27; // edx
  unsigned __int16 *v28; // rcx
  int v29; // r9d
  int v30; // edx
  int v31; // edx
  int v32; // ecx
  unsigned int v33; // ebx
  struct IXMLDOMElement *v35; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMElement *v36[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int16 *v37; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int16 *v38; // [rsp+98h] [rbp+50h] BYREF
  struct IXMLDOMElement *v39; // [rsp+A0h] [rbp+58h] BYREF
  struct IXMLDOMElement *v40; // [rsp+A8h] [rbp+60h] BYREF

  v36[0] = 0;
  v3 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v4 = 0;
  v35 = 0;
  v39 = 0;
  v40 = 0;
  v5 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v3,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageDeviceFontSubstitution",
              &v35);
  if ( Feature < 0 )
    goto LABEL_17;
  if ( !v35 )
    goto LABEL_5;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v6, v35, (char *)L"Option", v8, &v39);
  if ( Feature < 0 )
  {
LABEL_17:
    v17 = 0;
    if ( Feature < 0 )
      goto LABEL_46;
    goto LABEL_18;
  }
  v4 = v39;
LABEL_5:
  if ( v4 )
  {
    v9 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
    v38 = 0;
    v37 = 0;
    v10 = 0;
    Feature = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(v9, v4, &v37, &v38, 0);
    if ( Feature >= 0 )
    {
      v11 = v37;
      if ( v37 )
      {
        v12 = v38;
        if ( v38 )
        {
          do
          {
            v13 = *(unsigned __int16 *)((char *)v11
                                      + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"
                                      - (char *)v37);
            v14 = *v11 - v13;
            if ( v14 )
              break;
            ++v11;
          }
          while ( v13 );
          if ( !v14 )
          {
            do
            {
              v15 = *(unsigned __int16 *)((char *)v12 + (char *)L"On" - (char *)v38);
              v16 = *v12 - v15;
              if ( v16 )
                break;
              ++v12;
            }
            while ( v15 );
            if ( !v16 )
            {
              v10 = 1;
              *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x4000u;
              *(_WORD *)(*((_QWORD *)this + 2) + 98LL) = 3;
            }
          }
        }
      }
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v37);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v38);
    if ( v10 )
      goto LABEL_46;
    goto LABEL_17;
  }
  v17 = 0;
LABEL_18:
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageTrueTypeFontMode",
              v36);
  if ( Feature < 0 )
    goto LABEL_46;
  if ( v36[0] )
  {
    Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v18, v36[0], (char *)L"Option", v19, &v40);
    if ( Feature < 0 )
      goto LABEL_46;
    v5 = v40;
  }
  if ( v5 )
  {
    v20 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
    v38 = 0;
    v37 = 0;
    Feature = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(v20, v5, &v37, &v38, 0);
    if ( Feature >= 0 )
    {
      v21 = v37;
      if ( v37 )
      {
        v22 = v38;
        if ( v38 )
        {
          do
          {
            v23 = *(unsigned __int16 *)((char *)v21
                                      + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"
                                      - (char *)v37);
            v24 = *v21 - v23;
            if ( v24 )
              break;
            ++v21;
          }
          while ( v23 );
          if ( !v24 )
          {
            v25 = v38;
            do
            {
              v26 = *(unsigned __int16 *)((char *)v25 + (char *)L"RenderAsBitmap" - (char *)v38);
              v27 = *v25 - v26;
              if ( v27 )
                break;
              ++v25;
            }
            while ( v26 );
            if ( v27 )
            {
              v28 = v38;
              do
              {
                v29 = *(unsigned __int16 *)((char *)v28 + (char *)L"DownloadAsRasterFont" - (char *)v38);
                v30 = *v28 - v29;
                if ( v30 )
                  break;
                ++v28;
              }
              while ( v29 );
              if ( v30 )
              {
                do
                {
                  v31 = *(unsigned __int16 *)((char *)v22 + (char *)L"DownloadAsOutlineFont" - (char *)v38);
                  v32 = *v22 - v31;
                  if ( v32 )
                    break;
                  ++v22;
                }
                while ( v31 );
                if ( !v32 )
                  v17 = 4;
              }
              else
              {
                v17 = 2;
              }
            }
            else
            {
              v17 = 1;
            }
          }
        }
      }
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v37);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v38);
    if ( v17 )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x4000u;
      *(_WORD *)(*((_QWORD *)this + 2) + 98LL) = v17;
    }
  }
LABEL_46:
  v33 = 0;
  if ( Feature < 0 )
    v33 = Feature;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v39);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v40);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v35);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)v36);
  return v33;
}

```

## disassembly

```asm
0x180021a90  push    rbp
0x180021a92  push    rbx
0x180021a93  push    rsi
0x180021a94  push    rdi
0x180021a95  push    r12
0x180021a97  push    r13
0x180021a99  push    r14
0x180021a9b  push    r15
0x180021a9d  mov     rbp, rsp
0x180021aa0  sub     rsp, 48h
0x180021aa4  xor     r12d, r12d
0x180021aa7  lea     rax, [rbp+var_18]
0x180021aab  mov     r13, rcx
0x180021aae  mov     [rbp+var_10], r12
0x180021ab2  mov     rcx, [rcx+60h]; this
0x180021ab6  lea     r15, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180021abd  mov     ebx, r12d
0x180021ac0  mov     [rbp+var_18], r12
0x180021ac4  lea     r9, aPagedevicefont; "PageDeviceFontSubstitution"
0x180021acb  mov     [rbp+arg_10], rbx
0x180021acf  mov     r8, r15; unsigned __int16 *
0x180021ad2  mov     [rbp+arg_18], r12
0x180021ad6  xor     edx, edx; struct IXMLDOMElement *
0x180021ad8  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180021add  mov     esi, r12d
0x180021ae0  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021ae5  lea     r14d, [r12+2]
0x180021aea  mov     edi, eax
0x180021aec  test    eax, eax
0x180021aee  js      loc_180021BE2
0x180021af4  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x180021af8  test    rdx, rdx
0x180021afb  jz      short loc_180021B20
0x180021afd  lea     rax, [rbp+arg_10]
0x180021b01  lea     r8, aOption; "Option"
0x180021b08  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180021b0d  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021b12  mov     edi, eax
0x180021b14  test    eax, eax
0x180021b16  js      loc_180021BE2
0x180021b1c  mov     rbx, [rbp+arg_10]
0x180021b20  test    rbx, rbx
0x180021b23  jz      loc_180021CDA
0x180021b29  mov     rcx, [r13+60h]; this
0x180021b2d  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x180021b31  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180021b35  mov     [rbp+arg_8], r12
0x180021b39  mov     rdx, rbx; struct IXMLDOMElement *
0x180021b3c  mov     [rbp+arg_0], r12
0x180021b40  mov     r14d, r12d
0x180021b43  mov     dword ptr [rsp+48h+var_28], r12d; int
0x180021b48  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180021b4d  mov     edi, eax
0x180021b4f  test    eax, eax
0x180021b51  js      short loc_180021BC1
0x180021b53  mov     rax, [rbp+arg_0]
0x180021b57  test    rax, rax
0x180021b5a  jz      short loc_180021BC1
0x180021b5c  mov     rcx, [rbp+arg_8]
0x180021b60  test    rcx, rcx
0x180021b63  jz      short loc_180021BC1
0x180021b65  mov     r9, r15
0x180021b68  sub     r9, rax
0x180021b6b  movzx   r8d, word ptr [rax]
0x180021b6f  movzx   edx, word ptr [rax+r9]
0x180021b74  sub     r8d, edx
0x180021b77  jnz     short loc_180021B81
0x180021b79  add     rax, 2
0x180021b7d  test    edx, edx
0x180021b7f  jnz     short loc_180021B6B
0x180021b81  test    r8d, r8d
0x180021b84  jnz     short loc_180021BC1
0x180021b86  lea     r8, aOn; "On"
0x180021b8d  sub     r8, rcx
0x180021b90  movzx   eax, word ptr [rcx]
0x180021b93  movzx   edx, word ptr [rcx+r8]
0x180021b98  sub     eax, edx
0x180021b9a  jnz     short loc_180021BA4
0x180021b9c  add     rcx, 2
0x180021ba0  test    edx, edx
0x180021ba2  jnz     short loc_180021B90
0x180021ba4  test    eax, eax
0x180021ba6  jnz     short loc_180021BC1
0x180021ba8  mov     rax, [r13+10h]
0x180021bac  mov     r14d, 1
0x180021bb2  bts     dword ptr [rax+48h], 0Eh
0x180021bb7  mov     rax, [r13+10h]
0x180021bbb  mov     word ptr [rax+62h], 3
0x180021bc1  lea     rcx, [rbp+arg_0]
0x180021bc5  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021bca  lea     rcx, [rbp+arg_8]
0x180021bce  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021bd3  test    r14d, r14d
0x180021bd6  jnz     loc_180021D5A
0x180021bdc  mov     r14d, 2
0x180021be2  mov     ebx, r12d
0x180021be5  test    edi, edi
0x180021be7  js      loc_180021D5A
0x180021bed  mov     rcx, [r13+60h]; this
0x180021bf1  lea     rax, [rbp+var_10]
0x180021bf5  lea     r9, aPagetruetypefo; "PageTrueTypeFontMode"
0x180021bfc  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180021c01  mov     r8, r15; unsigned __int16 *
0x180021c04  xor     edx, edx; struct IXMLDOMElement *
0x180021c06  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021c0b  mov     edi, eax
0x180021c0d  test    eax, eax
0x180021c0f  js      loc_180021D5A
0x180021c15  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x180021c19  test    rdx, rdx
0x180021c1c  jz      short loc_180021C41
0x180021c1e  lea     rax, [rbp+arg_18]
0x180021c22  lea     r8, aOption; "Option"
0x180021c29  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180021c2e  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021c33  mov     edi, eax
0x180021c35  test    eax, eax
0x180021c37  js      loc_180021D5A
0x180021c3d  mov     rsi, [rbp+arg_18]
0x180021c41  test    rsi, rsi
0x180021c44  jz      loc_180021D5A
0x180021c4a  mov     rcx, [r13+60h]; this
0x180021c4e  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x180021c52  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180021c56  mov     [rbp+arg_8], r12
0x180021c5a  mov     rdx, rsi; struct IXMLDOMElement *
0x180021c5d  mov     [rbp+arg_0], r12
0x180021c61  mov     dword ptr [rsp+48h+var_28], r12d; int
0x180021c66  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180021c6b  mov     edi, eax
0x180021c6d  test    eax, eax
0x180021c6f  js      loc_180021D32
0x180021c75  mov     rcx, [rbp+arg_0]
0x180021c79  test    rcx, rcx
0x180021c7c  jz      loc_180021D32
0x180021c82  mov     rax, [rbp+arg_8]
0x180021c86  test    rax, rax
0x180021c89  jz      loc_180021D32
0x180021c8f  sub     r15, rcx
0x180021c92  movzx   edx, word ptr [rcx]
0x180021c95  movzx   r8d, word ptr [rcx+r15]
0x180021c9a  sub     edx, r8d
0x180021c9d  jnz     short loc_180021CA7
0x180021c9f  add     rcx, r14
0x180021ca2  test    r8d, r8d
0x180021ca5  jnz     short loc_180021C92
0x180021ca7  test    edx, edx
0x180021ca9  jnz     loc_180021D32
0x180021caf  lea     r8, aRenderasbitmap; "RenderAsBitmap"
0x180021cb6  mov     rcx, rax
0x180021cb9  sub     r8, rax
0x180021cbc  movzx   edx, word ptr [rcx]
0x180021cbf  movzx   r9d, word ptr [rcx+r8]
0x180021cc4  sub     edx, r9d
0x180021cc7  jnz     short loc_180021CD1
0x180021cc9  add     rcx, r14
0x180021ccc  test    r9d, r9d
0x180021ccf  jnz     short loc_180021CBC
0x180021cd1  test    edx, edx
0x180021cd3  jnz     short loc_180021CE2
0x180021cd5  lea     ebx, [rdx+1]
0x180021cd8  jmp     short loc_180021D32
0x180021cda  mov     ebx, r12d
0x180021cdd  jmp     loc_180021BED
0x180021ce2  lea     r8, aDownloadasrast; "DownloadAsRasterFont"
0x180021ce9  mov     rcx, rax
0x180021cec  sub     r8, rax
0x180021cef  movzx   edx, word ptr [rcx]
0x180021cf2  movzx   r9d, word ptr [rcx+r8]
0x180021cf7  sub     edx, r9d
0x180021cfa  jnz     short loc_180021D04
0x180021cfc  add     rcx, r14
0x180021cff  test    r9d, r9d
0x180021d02  jnz     short loc_180021CEF
0x180021d04  test    edx, edx
0x180021d06  jnz     short loc_180021D0E
0x180021d08  movzx   ebx, r14w
0x180021d0c  jmp     short loc_180021D32
0x180021d0e  lea     r8, aDownloadasoutl; "DownloadAsOutlineFont"
0x180021d15  sub     r8, rax
0x180021d18  movzx   ecx, word ptr [rax]
0x180021d1b  movzx   edx, word ptr [rax+r8]
0x180021d20  sub     ecx, edx
0x180021d22  jnz     short loc_180021D2B
0x180021d24  add     rax, r14
0x180021d27  test    edx, edx
0x180021d29  jnz     short loc_180021D18
0x180021d2b  test    ecx, ecx
0x180021d2d  jnz     short loc_180021D32
0x180021d2f  lea     ebx, [rcx+4]
0x180021d32  lea     rcx, [rbp+arg_0]
0x180021d36  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021d3b  lea     rcx, [rbp+arg_8]
0x180021d3f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021d44  test    bx, bx
0x180021d47  jz      short loc_180021D5A
0x180021d49  mov     rax, [r13+10h]
0x180021d4d  bts     dword ptr [rax+48h], 0Eh
0x180021d52  mov     rax, [r13+10h]
0x180021d56  mov     [rax+62h], bx
0x180021d5a  test    edi, edi
0x180021d5c  lea     rcx, [rbp+arg_10]
0x180021d60  mov     ebx, r12d
0x180021d63  cmovs   ebx, edi
0x180021d66  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021d6b  lea     rcx, [rbp+arg_18]
0x180021d6f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021d74  lea     rcx, [rbp+var_18]
0x180021d78  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021d7d  lea     rcx, [rbp+var_10]
0x180021d81  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021d86  mov     eax, ebx
0x180021d88  add     rsp, 48h
0x180021d8c  pop     r15
0x180021d8e  pop     r14
0x180021d90  pop     r13
0x180021d92  pop     r12
0x180021d94  pop     rdi
0x180021d95  pop     rsi
0x180021d96  pop     rbx
0x180021d97  pop     rbp
0x180021d98  retn
```
