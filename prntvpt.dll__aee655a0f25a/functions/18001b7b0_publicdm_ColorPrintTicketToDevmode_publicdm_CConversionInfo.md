# publicdm::ColorPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x18001b7b0`
- end: `0x18001b970`
- name: `?ColorPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `448`
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
- `0x18001b7b0`

## string_xrefs

- `0x18001b7d3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ColorPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v3; // rcx
  const OLECHAR *v4; // r14
  struct IXMLDOMElement *v5; // rsi
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rdi
  int Feature; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  int ChildWithoutName; // r9d
  signed __int64 v11; // rdi
  int v12; // ecx
  int v13; // eax
  const unsigned __int16 *v14; // rax
  int v15; // r8d
  int v16; // edx
  const unsigned __int16 *v17; // rax
  int v18; // r8d
  int v19; // edx
  const wchar_t *v20; // rax
  signed __int64 v21; // rbx
  int v22; // edx
  int v23; // ecx
  unsigned int v24; // ebx
  unsigned __int16 *v26; // [rsp+70h] [rbp+38h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp+40h] BYREF
  struct IXMLDOMElement *v28; // [rsp+80h] [rbp+48h] BYREF
  struct IXMLDOMElement *v29; // [rsp+88h] [rbp+50h] BYREF

  v29 = 0;
  v3 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v4 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
  v5 = 0;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  v26 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v3,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              (const unsigned __int16 *)&stru_18002A1F0,
              &v29);
  ChildWithoutName = Feature;
  if ( Feature >= 0 )
  {
    if ( v29 )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                           v9,
                           v29,
                           (char *)L"Option",
                           (const unsigned __int16 *)(unsigned int)Feature,
                           &v28);
      if ( ChildWithoutName < 0 )
        goto LABEL_28;
      v5 = v28;
    }
    if ( v5 )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                           *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                           v5,
                           &v26,
                           &v27,
                           0);
      if ( ChildWithoutName < 0 )
        goto LABEL_28;
      v6 = v27;
      v7 = v26;
    }
    if ( v7 && v6 )
    {
      v11 = (char *)v7 - (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
      do
      {
        v12 = *(const OLECHAR *)((char *)v4 + v11);
        v13 = *v4 - v12;
        if ( v13 )
          break;
        ++v4;
      }
      while ( v12 );
      if ( !v13 )
      {
        v14 = L"Color";
        do
        {
          v15 = *(const unsigned __int16 *)((char *)v14 + (char *)v6 - (char *)L"Color");
          v16 = *v14 - v15;
          if ( v16 )
            break;
          ++v14;
        }
        while ( v15 );
        if ( v16 )
        {
          v17 = L"Monochrome";
          do
          {
            v18 = *(const unsigned __int16 *)((char *)v17 + (char *)v6 - (char *)L"Monochrome");
            v19 = *v17 - v18;
            if ( v19 )
              break;
            ++v17;
          }
          while ( v18 );
          if ( !v19 )
            goto LABEL_27;
          v20 = L"Grayscale";
          v21 = (char *)v6 - (char *)L"Grayscale";
          do
          {
            v22 = *(const wchar_t *)((char *)v20 + v21);
            v23 = *v20 - v22;
            if ( v23 )
              break;
            ++v20;
          }
          while ( v22 );
          if ( !v23 )
          {
LABEL_27:
            *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x800u;
            *(_WORD *)(*((_QWORD *)this + 2) + 92LL) = 1;
          }
        }
        else
        {
          *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x800u;
          *(_WORD *)(*((_QWORD *)this + 2) + 92LL) = 2;
        }
      }
    }
  }
LABEL_28:
  v24 = 0;
  if ( ChildWithoutName < 0 )
    v24 = ChildWithoutName;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v26);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v27);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v28);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v29);
  return v24;
}

```

## disassembly

```asm
0x18001b7b0  push    rbp
0x18001b7b2  push    rbx
0x18001b7b3  push    rsi
0x18001b7b4  push    rdi
0x18001b7b5  push    r14
0x18001b7b7  push    r15
0x18001b7b9  mov     rbp, rsp
0x18001b7bc  sub     rsp, 38h
0x18001b7c0  mov     r15, rcx
0x18001b7c3  mov     [rbp+arg_18], 0
0x18001b7cb  mov     rcx, [rcx+60h]; this
0x18001b7cf  lea     rax, [rbp+arg_18]
0x18001b7d3  lea     r14, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001b7da  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001b7df  xor     esi, esi
0x18001b7e1  lea     r9, stru_18002A1F0; unsigned __int16 *
0x18001b7e8  xor     ebx, ebx
0x18001b7ea  mov     [rbp+arg_10], rsi
0x18001b7ee  xor     edi, edi
0x18001b7f0  mov     [rbp+arg_8], rbx
0x18001b7f4  mov     r8, r14; unsigned __int16 *
0x18001b7f7  mov     [rbp+arg_0], rdi
0x18001b7fb  xor     edx, edx; struct IXMLDOMElement *
0x18001b7fd  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b802  mov     r9d, eax; unsigned __int16 *
0x18001b805  test    eax, eax
0x18001b807  js      loc_18001B934
0x18001b80d  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001b811  test    rdx, rdx
0x18001b814  jz      short loc_18001B83A
0x18001b816  lea     rax, [rbp+arg_10]
0x18001b81a  lea     r8, aOption; "Option"
0x18001b821  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001b826  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001b82b  mov     r9d, eax
0x18001b82e  test    eax, eax
0x18001b830  js      loc_18001B934
0x18001b836  mov     rsi, [rbp+arg_10]
0x18001b83a  test    rsi, rsi
0x18001b83d  jz      short loc_18001B86A
0x18001b83f  mov     rcx, [r15+60h]; this
0x18001b843  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x18001b847  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x18001b84b  mov     dword ptr [rsp+38h+var_18], ebx; int
0x18001b84f  mov     rdx, rsi; struct IXMLDOMElement *
0x18001b852  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001b857  mov     r9d, eax
0x18001b85a  test    eax, eax
0x18001b85c  js      loc_18001B934
0x18001b862  mov     rbx, [rbp+arg_8]
0x18001b866  mov     rdi, [rbp+arg_0]
0x18001b86a  test    rdi, rdi
0x18001b86d  jz      loc_18001B934
0x18001b873  test    rbx, rbx
0x18001b876  jz      loc_18001B934
0x18001b87c  sub     rdi, r14
0x18001b87f  mov     r10d, 2
0x18001b885  movzx   eax, word ptr [r14]
0x18001b889  movzx   ecx, word ptr [r14+rdi]
0x18001b88e  sub     eax, ecx
0x18001b890  jnz     short loc_18001B899
0x18001b892  add     r14, r10
0x18001b895  test    ecx, ecx
0x18001b897  jnz     short loc_18001B885
0x18001b899  test    eax, eax
0x18001b89b  jnz     loc_18001B934
0x18001b8a1  lea     rax, aColor; "Color"
0x18001b8a8  mov     rcx, rbx
0x18001b8ab  sub     rcx, rax
0x18001b8ae  movzx   edx, word ptr [rax]
0x18001b8b1  movzx   r8d, word ptr [rax+rcx]
0x18001b8b6  sub     edx, r8d
0x18001b8b9  jnz     short loc_18001B8C3
0x18001b8bb  add     rax, r10
0x18001b8be  test    r8d, r8d
0x18001b8c1  jnz     short loc_18001B8AE
0x18001b8c3  test    edx, edx
0x18001b8c5  jnz     short loc_18001B8DB
0x18001b8c7  mov     rax, [r15+10h]
0x18001b8cb  bts     dword ptr [rax+48h], 0Bh
0x18001b8d0  mov     rax, [r15+10h]
0x18001b8d4  mov     [rax+5Ch], r10w
0x18001b8d9  jmp     short loc_18001B934
0x18001b8db  lea     rax, aMonochrome; "Monochrome"
0x18001b8e2  mov     rcx, rbx
0x18001b8e5  sub     rcx, rax
0x18001b8e8  movzx   edx, word ptr [rax]
0x18001b8eb  movzx   r8d, word ptr [rax+rcx]
0x18001b8f0  sub     edx, r8d
0x18001b8f3  jnz     short loc_18001B8FD
0x18001b8f5  add     rax, r10
0x18001b8f8  test    r8d, r8d
0x18001b8fb  jnz     short loc_18001B8E8
0x18001b8fd  test    edx, edx
0x18001b8ff  jz      short loc_18001B921
0x18001b901  lea     rax, aGrayscale; "Grayscale"
0x18001b908  sub     rbx, rax
0x18001b90b  movzx   ecx, word ptr [rax]
0x18001b90e  movzx   edx, word ptr [rax+rbx]
0x18001b912  sub     ecx, edx
0x18001b914  jnz     short loc_18001B91D
0x18001b916  add     rax, r10
0x18001b919  test    edx, edx
0x18001b91b  jnz     short loc_18001B90B
0x18001b91d  test    ecx, ecx
0x18001b91f  jnz     short loc_18001B934
0x18001b921  mov     rax, [r15+10h]
0x18001b925  bts     dword ptr [rax+48h], 0Bh
0x18001b92a  mov     rax, [r15+10h]
0x18001b92e  mov     word ptr [rax+5Ch], 1
0x18001b934  xor     ebx, ebx
0x18001b936  lea     rcx, [rbp+arg_0]
0x18001b93a  test    r9d, r9d
0x18001b93d  cmovs   ebx, r9d
0x18001b941  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b946  lea     rcx, [rbp+arg_8]
0x18001b94a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b94f  lea     rcx, [rbp+arg_10]
0x18001b953  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b958  lea     rcx, [rbp+arg_18]
0x18001b95c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b961  mov     eax, ebx
0x18001b963  add     rsp, 38h
0x18001b967  pop     r15
0x18001b969  pop     r14
0x18001b96b  pop     rdi
0x18001b96c  pop     rsi
0x18001b96d  pop     rbx
0x18001b96e  pop     rbp
0x18001b96f  retn
```
