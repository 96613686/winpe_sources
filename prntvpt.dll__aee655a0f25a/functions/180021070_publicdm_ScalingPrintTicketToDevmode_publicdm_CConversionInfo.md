# publicdm::ScalingPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x180021070`
- end: `0x180021253`
- name: `?ScalingPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `483`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002084`
- `0x180004b00`
- `0x1800056e0`
- `0x180005e70`
- `0x18000e364`
- `0x18001d7c0`
- `0x180021070`

## string_xrefs

- `0x1800210ad`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ScalingPrintTicketToDevmode(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  unsigned __int16 *v3; // rdi
  struct IXMLDOMElement *v4; // r14
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  const OLECHAR *v6; // rsi
  unsigned __int16 *v7; // rbx
  int Feature; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  const unsigned __int16 *v10; // r9
  unsigned __int64 v11; // r8
  int ChildWithoutName; // eax
  int NameAttribute; // eax
  signed __int64 v14; // rdi
  int v15; // ecx
  int v16; // eax
  const unsigned __int16 *v17; // rax
  int v18; // r9d
  int v19; // ecx
  __int16 v20; // cx
  const unsigned __int16 *v21; // rax
  signed __int64 v22; // rbx
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // ebx
  struct IXMLDOMElement *v27; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMElement *v28[2]; // [rsp+38h] [rbp-10h] BYREF
  int v29; // [rsp+80h] [rbp+38h] BYREF
  int v30; // [rsp+88h] [rbp+40h] BYREF
  unsigned __int16 *v31; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+98h] [rbp+50h] BYREF

  v28[0] = 0;
  v3 = 0;
  v4 = 0;
  v32 = 0;
  v27 = 0;
  v31 = 0;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
  v5 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v6 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
  v7 = 0;
  v31 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              v5,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageScaling",
              v28);
  v11 = (unsigned int)Feature;
  if ( Feature >= 0 )
  {
    if ( v28[0] )
    {
      ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                           v9,
                           v28[0],
                           (char *)L"Option",
                           v10,
                           &v27);
      v11 = (unsigned int)ChildWithoutName;
      if ( ChildWithoutName < 0 )
        goto LABEL_27;
      v4 = v27;
    }
    if ( v4 )
    {
      NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                        *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                        v4,
                        &v32,
                        &v31,
                        0);
      v11 = (unsigned int)NameAttribute;
      if ( NameAttribute < 0 )
        goto LABEL_27;
      v3 = v32;
      v7 = v31;
    }
    if ( v3 && v7 )
    {
      v14 = (char *)v3 - (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
      do
      {
        v15 = *(const OLECHAR *)((char *)v6 + v14);
        v16 = *v6 - v15;
        if ( v16 )
          break;
        ++v6;
      }
      while ( v15 );
      if ( !v16 )
      {
        v17 = L"CustomSquare";
        do
        {
          v18 = *(const unsigned __int16 *)((char *)v17 + (char *)v7 - (char *)L"CustomSquare");
          v19 = *v17 - v18;
          if ( v19 )
            break;
          ++v17;
        }
        while ( v18 );
        if ( v19 )
        {
          v21 = L"None";
          v22 = (char *)v7 - (char *)L"None";
          do
          {
            v23 = *(const unsigned __int16 *)((char *)v21 + v22);
            v24 = *v21 - v23;
            if ( v24 )
              break;
            ++v21;
          }
          while ( v23 );
          if ( !v24 )
          {
            *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x10u;
            *(_WORD *)(*((_QWORD *)this + 2) + 84LL) = 100;
          }
        }
        else
        {
          v30 = 0;
          v29 = 0;
          LODWORD(v11) = NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
                           *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                           v4,
                           (const unsigned __int16 *)v11,
                           L"Scale",
                           &v30,
                           &v29);
          if ( (v11 & 0x80000000) == 0LL )
          {
            if ( v29 )
            {
              v20 = v30;
              if ( v30 <= 0xFFFF )
              {
                *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x10u;
                *(_WORD *)(*((_QWORD *)this + 2) + 84LL) = v20;
              }
            }
          }
        }
      }
    }
  }
LABEL_27:
  v25 = 0;
  if ( (v11 & 0x80000000) != 0LL )
    v25 = v11;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v32);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)&v27);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset((__int64 *)v28);
  return v25;
}

```

## disassembly

```asm
0x180021070  push    rbp
0x180021072  push    rbx
0x180021073  push    rsi
0x180021074  push    rdi
0x180021075  push    r14
0x180021077  push    r15
0x180021079  mov     rbp, rsp
0x18002107c  sub     rsp, 48h
0x180021080  mov     r15, rcx
0x180021083  mov     [rbp+var_10], 0
0x18002108b  xor     edi, edi
0x18002108d  lea     rcx, [rbp+arg_10]
0x180021091  xor     r14d, r14d
0x180021094  mov     [rbp+arg_18], rdi
0x180021098  mov     [rbp+var_18], r14
0x18002109c  mov     [rbp+arg_10], rdi
0x1800210a0  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x1800210a5  mov     rcx, [r15+60h]; this
0x1800210a9  lea     rax, [rbp+var_10]
0x1800210ad  lea     rsi, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x1800210b4  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x1800210b9  xor     ebx, ebx
0x1800210bb  lea     r9, aPagescaling; "PageScaling"
0x1800210c2  mov     r8, rsi; unsigned __int16 *
0x1800210c5  mov     [rbp+arg_10], rbx
0x1800210c9  xor     edx, edx; struct IXMLDOMElement *
0x1800210cb  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800210d0  mov     r8d, eax
0x1800210d3  test    eax, eax
0x1800210d5  js      loc_180021217
0x1800210db  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x1800210df  test    rdx, rdx
0x1800210e2  jz      short loc_180021108
0x1800210e4  lea     rax, [rbp+var_18]
0x1800210e8  lea     r8, aOption; "Option"
0x1800210ef  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x1800210f4  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800210f9  mov     r8d, eax
0x1800210fc  test    eax, eax
0x1800210fe  js      loc_180021217
0x180021104  mov     r14, [rbp+var_18]
0x180021108  test    r14, r14
0x18002110b  jz      short loc_180021138
0x18002110d  mov     rcx, [r15+60h]; this
0x180021111  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x180021115  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x180021119  mov     dword ptr [rsp+48h+var_28], ebx; int
0x18002111d  mov     rdx, r14; struct IXMLDOMElement *
0x180021120  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180021125  mov     r8d, eax; unsigned __int16 *
0x180021128  test    eax, eax
0x18002112a  js      loc_180021217
0x180021130  mov     rdi, [rbp+arg_18]
0x180021134  mov     rbx, [rbp+arg_10]
0x180021138  test    rdi, rdi
0x18002113b  jz      loc_180021217
0x180021141  test    rbx, rbx
0x180021144  jz      loc_180021217
0x18002114a  sub     rdi, rsi
0x18002114d  movzx   eax, word ptr [rsi]
0x180021150  movzx   ecx, word ptr [rsi+rdi]
0x180021154  sub     eax, ecx
0x180021156  jnz     short loc_180021160
0x180021158  add     rsi, 2
0x18002115c  test    ecx, ecx
0x18002115e  jnz     short loc_18002114D
0x180021160  test    eax, eax
0x180021162  jnz     loc_180021217
0x180021168  lea     rax, aCustomsquare; "CustomSquare"
0x18002116f  mov     rdx, rbx
0x180021172  sub     rdx, rax
0x180021175  movzx   ecx, word ptr [rax]
0x180021178  movzx   r9d, word ptr [rax+rdx]
0x18002117d  sub     ecx, r9d
0x180021180  jnz     short loc_18002118B
0x180021182  add     rax, 2
0x180021186  test    r9d, r9d
0x180021189  jnz     short loc_180021175
0x18002118b  test    ecx, ecx
0x18002118d  jnz     short loc_1800211E4
0x18002118f  lea     rax, [rbp+arg_0]
0x180021193  mov     [rbp+arg_8], ecx
0x180021196  mov     [rsp+48h+var_20], rax; int *
0x18002119b  lea     r9, aScale; "Scale"
0x1800211a2  lea     rax, [rbp+arg_8]
0x1800211a6  mov     [rbp+arg_0], ecx
0x1800211a9  mov     rcx, [r15+60h]; this
0x1800211ad  mov     rdx, r14; struct IXMLDOMElement *
0x1800211b0  mov     [rsp+48h+var_28], rax; int *
0x1800211b5  call    ?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)
0x1800211ba  mov     r8d, eax
0x1800211bd  test    eax, eax
0x1800211bf  js      short loc_180021217
0x1800211c1  cmp     [rbp+arg_0], 0
0x1800211c5  jz      short loc_180021217
0x1800211c7  mov     ecx, [rbp+arg_8]
0x1800211ca  cmp     ecx, 0FFFFh
0x1800211d0  jg      short loc_180021217
0x1800211d2  mov     rax, [r15+10h]
0x1800211d6  or      dword ptr [rax+48h], 10h
0x1800211da  mov     rax, [r15+10h]
0x1800211de  mov     [rax+54h], cx
0x1800211e2  jmp     short loc_180021217
0x1800211e4  lea     rax, aNone; "None"
0x1800211eb  sub     rbx, rax
0x1800211ee  movzx   ecx, word ptr [rax]
0x1800211f1  movzx   edx, word ptr [rax+rbx]
0x1800211f5  sub     ecx, edx
0x1800211f7  jnz     short loc_180021201
0x1800211f9  add     rax, 2
0x1800211fd  test    edx, edx
0x1800211ff  jnz     short loc_1800211EE
0x180021201  test    ecx, ecx
0x180021203  jnz     short loc_180021217
0x180021205  mov     rax, [r15+10h]
0x180021209  or      dword ptr [rax+48h], 10h
0x18002120d  mov     rax, [r15+10h]
0x180021211  mov     word ptr [rax+54h], 64h ; 'd'
0x180021217  xor     ebx, ebx
0x180021219  lea     rcx, [rbp+arg_10]
0x18002121d  test    r8d, r8d
0x180021220  cmovs   ebx, r8d
0x180021224  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021229  lea     rcx, [rbp+arg_18]
0x18002122d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021232  lea     rcx, [rbp+var_18]
0x180021236  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002123b  lea     rcx, [rbp+var_10]
0x18002123f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180021244  mov     eax, ebx
0x180021246  add     rsp, 48h
0x18002124a  pop     r15
0x18002124c  pop     r14
0x18002124e  pop     rdi
0x18002124f  pop     rsi
0x180021250  pop     rbx
0x180021251  pop     rbp
0x180021252  retn
```
