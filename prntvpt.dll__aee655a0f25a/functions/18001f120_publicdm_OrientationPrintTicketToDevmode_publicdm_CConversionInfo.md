# publicdm::OrientationPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x18001f120`
- end: `0x18001f2b3`
- name: `?OrientationPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `403`
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
- `0x18001f120`

## string_xrefs

- `0x18001f13b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::OrientationPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v3; // rcx
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rdi
  struct IXMLDOMElement *v6; // rsi
  int Feature; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  int ChildWithoutName; // r9d
  char *v10; // r15
  int v11; // ecx
  int v12; // eax
  unsigned __int16 *v13; // rax
  int v14; // r8d
  int v15; // edx
  char *v16; // rdx
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // ebx
  struct IXMLDOMElement *v21; // [rsp+70h] [rbp+38h] BYREF
  struct IXMLDOMElement *v22; // [rsp+78h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+80h] [rbp+48h] BYREF
  unsigned __int16 *v24; // [rsp+88h] [rbp+50h] BYREF

  v3 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v4 = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v3,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              (const unsigned __int16 *)&stru_180029930,
              &v22);
  ChildWithoutName = Feature;
  if ( Feature >= 0 )
  {
    if ( v22 )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                           v8,
                           v22,
                           (char *)L"Option",
                           (const unsigned __int16 *)(unsigned int)Feature,
                           &v21);
      if ( ChildWithoutName < 0 )
        goto LABEL_24;
      v6 = v21;
    }
    if ( v6 )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                           *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                           v6,
                           &v23,
                           &v24,
                           0);
      if ( ChildWithoutName < 0 )
        goto LABEL_24;
      v4 = v24;
      v5 = v23;
    }
    if ( v4 && v5 )
    {
      v10 = (char *)((char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords" - (char *)v5);
      do
      {
        v11 = *(unsigned __int16 *)&v10[(_QWORD)v5];
        v12 = *v5 - v11;
        if ( v12 )
          break;
        ++v5;
      }
      while ( v11 );
      if ( !v12 )
      {
        v13 = v4;
        do
        {
          v14 = *(unsigned __int16 *)((char *)v13 + (char *)L"Portrait" - (char *)v4);
          v15 = *v13 - v14;
          if ( v15 )
            break;
          ++v13;
        }
        while ( v14 );
        if ( v15 )
        {
          v16 = (char *)((char *)L"Landscape" - (char *)v4);
          do
          {
            v17 = *(unsigned __int16 *)&v16[(_QWORD)v4];
            v18 = *v4 - v17;
            if ( v18 )
              break;
            ++v4;
          }
          while ( v17 );
          if ( !v18 )
          {
            *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 1u;
            *(_WORD *)(*((_QWORD *)this + 2) + 76LL) = 2;
          }
        }
        else
        {
          *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 1u;
          *(_WORD *)(*((_QWORD *)this + 2) + 76LL) = 1;
        }
      }
    }
  }
LABEL_24:
  v19 = 0;
  if ( ChildWithoutName < 0 )
    v19 = ChildWithoutName;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v21);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v22);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v23);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v24);
  return v19;
}

```

## disassembly

```asm
0x18001f120  push    rbp
0x18001f122  push    rbx
0x18001f123  push    rsi
0x18001f124  push    rdi
0x18001f125  push    r14
0x18001f127  push    r15
0x18001f129  mov     rbp, rsp
0x18001f12c  sub     rsp, 38h
0x18001f130  mov     r14, rcx
0x18001f133  lea     rax, [rbp+arg_8]
0x18001f137  mov     rcx, [rcx+60h]; this
0x18001f13b  lea     r15, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001f142  xor     ebx, ebx
0x18001f144  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001f149  xor     edi, edi
0x18001f14b  mov     [rbp+arg_18], rbx
0x18001f14f  xor     esi, esi
0x18001f151  mov     [rbp+arg_10], rdi
0x18001f155  mov     r8, r15; unsigned __int16 *
0x18001f158  mov     [rbp+arg_8], rbx
0x18001f15c  lea     r9, stru_180029930; unsigned __int16 *
0x18001f163  mov     [rbp+arg_0], rsi
0x18001f167  xor     edx, edx; struct IXMLDOMElement *
0x18001f169  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f16e  mov     r9d, eax; unsigned __int16 *
0x18001f171  test    eax, eax
0x18001f173  js      loc_18001F277
0x18001f179  mov     rdx, [rbp+arg_8]; struct IXMLDOMElement *
0x18001f17d  test    rdx, rdx
0x18001f180  jz      short loc_18001F1A6
0x18001f182  lea     rax, [rbp+arg_0]
0x18001f186  lea     r8, aOption; "Option"
0x18001f18d  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001f192  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001f197  mov     r9d, eax
0x18001f19a  test    eax, eax
0x18001f19c  js      loc_18001F277
0x18001f1a2  mov     rsi, [rbp+arg_0]
0x18001f1a6  test    rsi, rsi
0x18001f1a9  jz      short loc_18001F1D6
0x18001f1ab  mov     rcx, [r14+60h]; this
0x18001f1af  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18001f1b3  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18001f1b7  mov     dword ptr [rsp+38h+var_18], ebx; int
0x18001f1bb  mov     rdx, rsi; struct IXMLDOMElement *
0x18001f1be  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001f1c3  mov     r9d, eax
0x18001f1c6  test    eax, eax
0x18001f1c8  js      loc_18001F277
0x18001f1ce  mov     rbx, [rbp+arg_18]
0x18001f1d2  mov     rdi, [rbp+arg_10]
0x18001f1d6  test    rbx, rbx
0x18001f1d9  jz      loc_18001F277
0x18001f1df  test    rdi, rdi
0x18001f1e2  jz      loc_18001F277
0x18001f1e8  sub     r15, rdi
0x18001f1eb  mov     r10d, 2
0x18001f1f1  movzx   eax, word ptr [rdi]
0x18001f1f4  movzx   ecx, word ptr [rdi+r15]
0x18001f1f9  sub     eax, ecx
0x18001f1fb  jnz     short loc_18001F204
0x18001f1fd  add     rdi, r10
0x18001f200  test    ecx, ecx
0x18001f202  jnz     short loc_18001F1F1
0x18001f204  test    eax, eax
0x18001f206  jnz     short loc_18001F277
0x18001f208  lea     rcx, aPortrait; "Portrait"
0x18001f20f  mov     rax, rbx
0x18001f212  sub     rcx, rbx
0x18001f215  movzx   edx, word ptr [rax]
0x18001f218  movzx   r8d, word ptr [rax+rcx]
0x18001f21d  sub     edx, r8d
0x18001f220  jnz     short loc_18001F22A
0x18001f222  add     rax, r10
0x18001f225  test    r8d, r8d
0x18001f228  jnz     short loc_18001F215
0x18001f22a  test    edx, edx
0x18001f22c  jnz     short loc_18001F242
0x18001f22e  mov     rax, [r14+10h]
0x18001f232  lea     ecx, [rdx+1]
0x18001f235  or      [rax+48h], ecx
0x18001f238  mov     rax, [r14+10h]
0x18001f23c  mov     [rax+4Ch], cx
0x18001f240  jmp     short loc_18001F277
0x18001f242  lea     rdx, aLandscape; "Landscape"
0x18001f249  sub     rdx, rbx
0x18001f24c  movzx   eax, word ptr [rbx]
0x18001f24f  movzx   ecx, word ptr [rbx+rdx]
0x18001f253  sub     eax, ecx
0x18001f255  jnz     short loc_18001F25E
0x18001f257  add     rbx, r10
0x18001f25a  test    ecx, ecx
0x18001f25c  jnz     short loc_18001F24C
0x18001f25e  test    eax, eax
0x18001f260  jnz     short loc_18001F277
0x18001f262  mov     rax, [r14+10h]
0x18001f266  mov     ecx, 1
0x18001f26b  or      [rax+48h], ecx
0x18001f26e  mov     rax, [r14+10h]
0x18001f272  mov     [rax+4Ch], r10w
0x18001f277  xor     ebx, ebx
0x18001f279  lea     rcx, [rbp+arg_0]
0x18001f27d  test    r9d, r9d
0x18001f280  cmovs   ebx, r9d
0x18001f284  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f289  lea     rcx, [rbp+arg_8]
0x18001f28d  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001f292  lea     rcx, [rbp+arg_10]
0x18001f296  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001f29b  lea     rcx, [rbp+arg_18]
0x18001f29f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001f2a4  mov     eax, ebx
0x18001f2a6  add     rsp, 38h
0x18001f2aa  pop     r15
0x18001f2ac  pop     r14
0x18001f2ae  pop     rdi
0x18001f2af  pop     rsi
0x18001f2b0  pop     rbx
0x18001f2b1  pop     rbp
0x18001f2b2  retn
```
