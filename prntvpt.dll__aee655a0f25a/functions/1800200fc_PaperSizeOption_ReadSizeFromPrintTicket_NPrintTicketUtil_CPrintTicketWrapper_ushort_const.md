# PaperSizeOption::ReadSizeFromPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *)

- ea: `0x1800200fc`
- end: `0x18002031d`
- name: `?ReadSizeFromPrintTicket@PaperSizeOption@@QEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(unsigned __int16 **this, struct NPrintTicketUtil::CPrintTicketWrapper *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f630`

## callees

- `0x180002084`
- `0x180004b00`
- `0x180005e70`
- `0x18000e364`
- `0x18001b0d8`
- `0x18001b124`
- `0x18001d7c0`
- `0x1800200fc`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002021e`
- `OLEAUT32!__imp_SysStringLen` at `0x18002022f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002021e`
- `OLEAUT32!__imp_SysStringLen` at `0x18002022f`

## string_xrefs

- `0x18002012a`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall PaperSizeOption::ReadSizeFromPrintTicket(
        unsigned __int16 **this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        char *a3)
{
  struct IXMLDOMElement *v6; // rbx
  NPrintTicketUtil::CPrintTicketWrapper *v7; // rcx
  int Feature; // esi
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r8
  unsigned __int16 **v12; // r14
  struct publicdm::PaperSizeEntry **v13; // r9
  BSTR v14; // rax
  unsigned __int16 *v15; // rcx
  unsigned int *v16; // r8
  int v17; // edx
  struct publicdm::PaperSizeEntry *v18; // rdx
  struct publicdm::PaperSizeEntry **v19; // r9
  bool v20; // zf
  _WORD *v21; // rcx
  char *v22; // r12
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // ebx
  int v27; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 v28[4]; // [rsp+38h] [rbp-20h] BYREF
  struct IXMLDOMElement *v29; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMElement *v30[2]; // [rsp+48h] [rbp-10h] BYREF
  int v31; // [rsp+B8h] [rbp+60h] BYREF

  v30[0] = 0;
  v6 = 0;
  v29 = 0;
  Feature = NPrintTicketUtil::CPrintTicketWrapper::GetFeature(
              a2,
              0,
              L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
              L"PageMediaSize",
              v30);
  if ( Feature >= 0 )
  {
    if ( v30[0] )
    {
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(v7, v30[0], (char *)L"Option", v10, &v29);
      if ( Feature < 0 )
        goto LABEL_26;
      v6 = v29;
    }
    if ( v6 )
    {
      v31 = 0;
      v27 = 0;
      Feature = NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
                  a2,
                  v6,
                  v9,
                  L"MediaSizeWidth",
                  (int *)this + 6,
                  &v31);
      if ( Feature >= 0 )
      {
        Feature = NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
                    a2,
                    v6,
                    v11,
                    L"MediaSizeHeight",
                    (int *)this + 7,
                    &v27);
        if ( Feature >= 0 )
        {
          v12 = this + 1;
          Feature = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(a2, v6, this + 1, this, 0);
          if ( Feature >= 0 && SysStringLen(*v12) && SysStringLen(*this) )
          {
            v14 = *v12;
            v15 = *v12;
            do
            {
              v16 = (unsigned int *)*(unsigned __int16 *)((char *)v15
                                                        + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/"
                                                                   "printschemakeywords"
                                                        - (char *)*v12);
              v17 = *v15 - (_DWORD)v16;
              if ( v17 )
                break;
              ++v15;
            }
            while ( (_DWORD)v16 );
            if ( v17 )
            {
              v22 = (char *)(a3 - (char *)v14);
              do
              {
                v23 = *(unsigned __int16 *)&v22[(_QWORD)v14];
                v24 = *v14 - v23;
                if ( v24 )
                  break;
                ++v14;
              }
              while ( v23 );
              if ( !v24 )
              {
                v31 = 0;
                if ( (unsigned int)publicdm::BReadDriverIDFromPrintTicketName(
                                     *this,
                                     (const unsigned __int16 *)&v31,
                                     v16) )
                  *((_WORD *)this + 16) = v31;
              }
            }
            else
            {
              v18 = (struct publicdm::PaperSizeEntry *)*this;
              *(_QWORD *)v28 = 0;
              if ( (unsigned int)publicdm::BFindPaperByName((publicdm *)&qword_180030B50, v18, v28, v13)
                || (unsigned int)publicdm::BFindPaperByName(
                                   (publicdm *)&qword_1800301C0,
                                   (struct publicdm::PaperSizeEntry *)*this,
                                   v28,
                                   v19) )
              {
                v20 = v31 == 0;
                v21 = *(_WORD **)v28;
                *((_WORD *)this + 16) = **(_WORD **)v28;
                if ( v20 || !v27 )
                {
                  *((_DWORD *)this + 7) = *((_DWORD *)v21 + 5);
                  *((_DWORD *)this + 6) = *((_DWORD *)v21 + 4);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_26:
  v25 = 0;
  if ( Feature < 0 )
    v25 = Feature;
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v29);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(v30);
  return v25;
}

```

## disassembly

```asm
0x1800200fc  push    rbp
0x1800200fe  push    rbx
0x1800200ff  push    rsi
0x180020100  push    rdi
0x180020101  push    r12
0x180020103  push    r13
0x180020105  push    r14
0x180020107  push    r15
0x180020109  mov     rbp, rsp
0x18002010c  sub     rsp, 58h
0x180020110  mov     r15, rdx
0x180020113  mov     [rbp+var_10], 0
0x18002011b  mov     r12, r8
0x18002011e  lea     rax, [rbp+var_10]
0x180020122  mov     rdi, rcx
0x180020125  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18002012a  lea     r13, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020131  xor     ebx, ebx
0x180020133  mov     r8, r13; unsigned __int16 *
0x180020136  mov     [rbp+var_18], rbx
0x18002013a  mov     rcx, r15; this
0x18002013d  lea     r9, aPagemediasize; "PageMediaSize"
0x180020144  xor     edx, edx; struct IXMLDOMElement *
0x180020146  call    ?GetFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18002014b  mov     esi, eax
0x18002014d  test    eax, eax
0x18002014f  js      loc_1800202F1
0x180020155  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x180020159  test    rdx, rdx
0x18002015c  jz      short loc_180020181
0x18002015e  lea     rax, [rbp+var_18]
0x180020162  lea     r8, aOption; "Option"
0x180020169  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18002016e  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180020173  mov     esi, eax
0x180020175  test    eax, eax
0x180020177  js      loc_1800202F1
0x18002017d  mov     rbx, [rbp+var_18]
0x180020181  test    rbx, rbx
0x180020184  jz      loc_1800202F1
0x18002018a  lea     rcx, [rbp+arg_18]
0x18002018e  mov     [rbp+arg_18], 0
0x180020195  mov     [rsp+58h+var_30], rcx; int *
0x18002019a  lea     rax, [rdi+18h]
0x18002019e  mov     rcx, r15; this
0x1800201a1  mov     [rbp+var_28], 0
0x1800201a8  lea     r9, aMediasizewidth; "MediaSizeWidth"
0x1800201af  mov     [rsp+58h+var_38], rax; int *
0x1800201b4  mov     rdx, rbx; struct IXMLDOMElement *
0x1800201b7  call    ?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)
0x1800201bc  mov     esi, eax
0x1800201be  test    eax, eax
0x1800201c0  js      loc_1800202F1
0x1800201c6  lea     rcx, [rbp+var_28]
0x1800201ca  mov     rdx, rbx; struct IXMLDOMElement *
0x1800201cd  mov     [rsp+58h+var_30], rcx; int *
0x1800201d2  lea     rax, [rdi+1Ch]
0x1800201d6  mov     rcx, r15; this
0x1800201d9  mov     [rsp+58h+var_38], rax; int *
0x1800201de  lea     r9, aMediasizeheigh; "MediaSizeHeight"
0x1800201e5  call    ?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)
0x1800201ea  mov     esi, eax
0x1800201ec  test    eax, eax
0x1800201ee  js      loc_1800202F1
0x1800201f4  lea     r14, [rdi+8]
0x1800201f8  mov     dword ptr [rsp+58h+var_38], 0; int
0x180020200  mov     r8, r14; unsigned __int16 **
0x180020203  mov     r9, rdi; unsigned __int16 **
0x180020206  mov     rdx, rbx; struct IXMLDOMElement *
0x180020209  mov     rcx, r15; this
0x18002020c  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180020211  mov     esi, eax
0x180020213  test    eax, eax
0x180020215  js      loc_1800202F1
0x18002021b  mov     rcx, [r14]; pbstr
0x18002021e  call    cs:__imp_SysStringLen
0x180020224  test    eax, eax
0x180020226  jz      loc_1800202F1
0x18002022c  mov     rcx, [rdi]; pbstr
0x18002022f  call    cs:__imp_SysStringLen
0x180020235  test    eax, eax
0x180020237  jz      loc_1800202F1
0x18002023d  mov     rax, [r14]
0x180020240  mov     rcx, rax
0x180020243  sub     r13, rax
0x180020246  movzx   edx, word ptr [rcx]
0x180020249  movzx   r8d, word ptr [rcx+r13]; unsigned int *
0x18002024e  sub     edx, r8d
0x180020251  jnz     short loc_18002025C
0x180020253  add     rcx, 2
0x180020257  test    r8d, r8d
0x18002025a  jnz     short loc_180020246
0x18002025c  test    edx, edx
0x18002025e  jnz     short loc_1800202BB
0x180020260  mov     rdx, [rdi]; struct publicdm::PaperSizeEntry *
0x180020263  lea     r8, [rbp+var_20]; unsigned __int16 *
0x180020267  lea     rcx, qword_180030B50; this
0x18002026e  mov     qword ptr [rbp+var_20], 0
0x180020276  call    ?BFindPaperByName@publicdm@@YAHPEAUPaperSizeEntry@1@PEBGPEAPEAU21@@Z; publicdm::BFindPaperByName(publicdm::PaperSizeEntry *,ushort const *,publicdm::PaperSizeEntry * *)
0x18002027b  test    eax, eax
0x18002027d  jnz     short loc_180020296
0x18002027f  mov     rdx, [rdi]; struct publicdm::PaperSizeEntry *
0x180020282  lea     r8, [rbp+var_20]; unsigned __int16 *
0x180020286  lea     rcx, qword_1800301C0; this
0x18002028d  call    ?BFindPaperByName@publicdm@@YAHPEAUPaperSizeEntry@1@PEBGPEAPEAU21@@Z; publicdm::BFindPaperByName(publicdm::PaperSizeEntry *,ushort const *,publicdm::PaperSizeEntry * *)
0x180020292  test    eax, eax
0x180020294  jz      short loc_1800202F1
0x180020296  cmp     [rbp+arg_18], 0
0x18002029a  mov     rcx, qword ptr [rbp+var_20]
0x18002029e  movzx   eax, word ptr [rcx]
0x1800202a1  mov     [rdi+20h], ax
0x1800202a5  jz      short loc_1800202AD
0x1800202a7  cmp     [rbp+var_28], 0
0x1800202ab  jnz     short loc_1800202F1
0x1800202ad  mov     eax, [rcx+14h]
0x1800202b0  mov     [rdi+1Ch], eax
0x1800202b3  mov     eax, [rcx+10h]
0x1800202b6  mov     [rdi+18h], eax
0x1800202b9  jmp     short loc_1800202F1
0x1800202bb  sub     r12, rax
0x1800202be  movzx   ecx, word ptr [rax]
0x1800202c1  movzx   edx, word ptr [rax+r12]
0x1800202c6  sub     ecx, edx
0x1800202c8  jnz     short loc_1800202D2
0x1800202ca  add     rax, 2
0x1800202ce  test    edx, edx
0x1800202d0  jnz     short loc_1800202BE
0x1800202d2  test    ecx, ecx
0x1800202d4  jnz     short loc_1800202F1
0x1800202d6  mov     [rbp+arg_18], ecx
0x1800202d9  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x1800202dd  mov     rcx, [rdi]; String2
0x1800202e0  call    ?BReadDriverIDFromPrintTicketName@publicdm@@YAHPEBGPEAK@Z; publicdm::BReadDriverIDFromPrintTicketName(ushort const *,ulong *)
0x1800202e5  test    eax, eax
0x1800202e7  jz      short loc_1800202F1
0x1800202e9  movzx   eax, word ptr [rbp+arg_18]
0x1800202ed  mov     [rdi+20h], ax
0x1800202f1  xor     ebx, ebx
0x1800202f3  lea     rcx, [rbp+var_18]
0x1800202f7  test    esi, esi
0x1800202f9  cmovs   ebx, esi
0x1800202fc  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x180020301  lea     rcx, [rbp+var_10]
0x180020305  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18002030a  mov     eax, ebx
0x18002030c  add     rsp, 58h
0x180020310  pop     r15
0x180020312  pop     r14
0x180020314  pop     r13
0x180020316  pop     r12
0x180020318  pop     rdi
0x180020319  pop     rsi
0x18002031a  pop     rbx
0x18002031b  pop     rbp
0x18002031c  retn
```
