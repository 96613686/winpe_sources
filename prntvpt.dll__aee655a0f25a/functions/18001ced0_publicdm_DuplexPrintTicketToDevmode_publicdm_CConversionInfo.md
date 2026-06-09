# publicdm::DuplexPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x18001ced0`
- end: `0x18001d086`
- name: `?DuplexPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `438`
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
- `0x18001ced0`

## string_xrefs

- `0x18001cefd`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::DuplexPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  NPrintTicketUtil::CPrintTicketWrapper *v3; // rcx
  const OLECHAR *v4; // rdi
  int Feature; // r15d
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rbx
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  const unsigned __int16 *v9; // r9
  signed __int64 v10; // rbx
  int v11; // ecx
  int v12; // eax
  int i; // ecx
  char *v14; // rax
  signed __int64 v15; // r9
  int v16; // r8d
  int v17; // edx
  unsigned int v18; // ebx
  struct IXMLDOMElement *v20; // [rsp+70h] [rbp+38h] BYREF
  unsigned __int16 *v21; // [rsp+78h] [rbp+40h] BYREF
  unsigned __int16 *v22; // [rsp+80h] [rbp+48h] BYREF
  struct IXMLDOMElement *v23; // [rsp+88h] [rbp+50h] BYREF

  v20 = 0;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v20);
  v3 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v4 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
  v20 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v3,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"JobDuplexAllDocumentsContiguously",
              &v20);
  if ( Feature >= 0 && v20 )
  {
    v23 = 0;
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v23);
    v23 = 0;
    v22 = 0;
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v22);
    v6 = 0;
    v22 = 0;
    v21 = 0;
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v21);
    v7 = 0;
    v21 = 0;
    Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v8, v20, (char *)L"Option", v9, &v23);
    if ( Feature >= 0 )
    {
      if ( !v23 )
        goto LABEL_7;
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                  *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                  v23,
                  &v21,
                  &v22,
                  0);
      if ( Feature >= 0 )
      {
        v6 = v22;
        v7 = v21;
LABEL_7:
        if ( v7 && v6 )
        {
          v10 = (char *)v7 - (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
          do
          {
            v11 = *(const OLECHAR *)((char *)v4 + v10);
            v12 = *v4 - v11;
            if ( v12 )
              break;
            ++v4;
          }
          while ( v11 );
          if ( !v12 )
          {
            for ( i = 0; ; ++i )
            {
              v14 = (char *)qword_1800254C0[3 * i + 1];
              if ( !v14 )
                break;
              v15 = (char *)v6 - v14;
              do
              {
                v16 = *(unsigned __int16 *)&v14[v15];
                v17 = *(unsigned __int16 *)v14 - v16;
                if ( v17 )
                  break;
                v14 += 2;
              }
              while ( v16 );
              if ( !v17 )
              {
                *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x1000u;
                *(_WORD *)(*((_QWORD *)this + 2) + 94LL) = qword_1800254C0[3 * i];
                break;
              }
            }
          }
        }
      }
    }
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v21);
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v22);
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v23);
  }
  v18 = 0;
  if ( Feature < 0 )
    v18 = Feature;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v20);
  return v18;
}

```

## disassembly

```asm
0x18001ced0  push    rbp
0x18001ced2  push    rbx
0x18001ced3  push    rdi
0x18001ced4  push    r13
0x18001ced6  push    r14
0x18001ced8  push    r15
0x18001ceda  mov     rbp, rsp
0x18001cedd  sub     rsp, 38h
0x18001cee1  mov     r13, rcx
0x18001cee4  mov     [rbp+arg_0], 0
0x18001ceec  lea     rcx, [rbp+arg_0]
0x18001cef0  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001cef5  mov     rcx, [r13+60h]; this
0x18001cef9  lea     rax, [rbp+arg_0]
0x18001cefd  lea     rdi, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001cf04  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001cf09  mov     r8, rdi; unsigned __int16 *
0x18001cf0c  mov     [rbp+arg_0], 0
0x18001cf14  lea     r9, aJobduplexalldo; "JobDuplexAllDocumentsContiguously"
0x18001cf1b  xor     edx, edx; struct IXMLDOMElement *
0x18001cf1d  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001cf22  mov     r15d, eax
0x18001cf25  test    eax, eax
0x18001cf27  js      loc_18001D064
0x18001cf2d  cmp     [rbp+arg_0], 0
0x18001cf32  jz      loc_18001D064
0x18001cf38  lea     rcx, [rbp+arg_18]
0x18001cf3c  mov     [rbp+arg_18], 0
0x18001cf44  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001cf49  lea     rcx, [rbp+arg_10]
0x18001cf4d  mov     [rbp+arg_18], 0
0x18001cf55  mov     [rbp+arg_10], 0
0x18001cf5d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cf62  xor     r14d, r14d
0x18001cf65  lea     rcx, [rbp+arg_8]
0x18001cf69  mov     [rbp+arg_10], r14
0x18001cf6d  mov     [rbp+arg_8], r14
0x18001cf71  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001cf76  mov     rdx, [rbp+arg_0]; struct IXMLDOMElement *
0x18001cf7a  lea     rax, [rbp+arg_18]
0x18001cf7e  xor     ebx, ebx
0x18001cf80  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001cf85  lea     r8, aOption; "Option"
0x18001cf8c  mov     [rbp+arg_8], rbx
0x18001cf90  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001cf95  mov     r15d, eax
0x18001cf98  test    eax, eax
0x18001cf9a  js      loc_18001D049
0x18001cfa0  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001cfa4  test    rdx, rdx
0x18001cfa7  jz      short loc_18001CFD1
0x18001cfa9  mov     rcx, [r13+60h]; this
0x18001cfad  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x18001cfb1  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x18001cfb5  mov     dword ptr [rsp+38h+var_18], ebx; int
0x18001cfb9  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18001cfbe  mov     r15d, eax
0x18001cfc1  test    eax, eax
0x18001cfc3  js      loc_18001D049
0x18001cfc9  mov     r14, [rbp+arg_10]
0x18001cfcd  mov     rbx, [rbp+arg_8]
0x18001cfd1  test    rbx, rbx
0x18001cfd4  jz      short loc_18001D049
0x18001cfd6  test    r14, r14
0x18001cfd9  jz      short loc_18001D049
0x18001cfdb  sub     rbx, rdi
0x18001cfde  movzx   eax, word ptr [rdi]
0x18001cfe1  movzx   ecx, word ptr [rdi+rbx]
0x18001cfe5  sub     eax, ecx
0x18001cfe7  jnz     short loc_18001CFF1
0x18001cfe9  add     rdi, 2
0x18001cfed  test    ecx, ecx
0x18001cfef  jnz     short loc_18001CFDE
0x18001cff1  test    eax, eax
0x18001cff3  jnz     short loc_18001D049
0x18001cff5  xor     ecx, ecx
0x18001cff7  lea     r11, qword_1800254C0
0x18001cffe  movsxd  rax, ecx
0x18001d001  lea     r10, [rax+rax*2]
0x18001d005  mov     rax, [r11+r10*8+8]
0x18001d00a  test    rax, rax
0x18001d00d  jz      short loc_18001D049
0x18001d00f  mov     r9, r14
0x18001d012  sub     r9, rax
0x18001d015  movzx   edx, word ptr [rax]
0x18001d018  movzx   r8d, word ptr [rax+r9]
0x18001d01d  sub     edx, r8d
0x18001d020  jnz     short loc_18001D02B
0x18001d022  add     rax, 2
0x18001d026  test    r8d, r8d
0x18001d029  jnz     short loc_18001D015
0x18001d02b  test    edx, edx
0x18001d02d  jz      short loc_18001D033
0x18001d02f  inc     ecx
0x18001d031  jmp     short loc_18001CFFE
0x18001d033  mov     rax, [r13+10h]
0x18001d037  bts     dword ptr [rax+48h], 0Ch
0x18001d03c  mov     rcx, [r13+10h]
0x18001d040  movzx   eax, word ptr [r11+r10*8]
0x18001d045  mov     [rcx+5Eh], ax
0x18001d049  lea     rcx, [rbp+arg_8]
0x18001d04d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d052  lea     rcx, [rbp+arg_10]
0x18001d056  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001d05b  lea     rcx, [rbp+arg_18]
0x18001d05f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d064  xor     ebx, ebx
0x18001d066  lea     rcx, [rbp+arg_0]
0x18001d06a  test    r15d, r15d
0x18001d06d  cmovs   ebx, r15d
0x18001d071  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d076  mov     eax, ebx
0x18001d078  add     rsp, 38h
0x18001d07c  pop     r15
0x18001d07e  pop     r14
0x18001d080  pop     r13
0x18001d082  pop     rdi
0x18001d083  pop     rbx
0x18001d084  pop     rbp
0x18001d085  retn
```
