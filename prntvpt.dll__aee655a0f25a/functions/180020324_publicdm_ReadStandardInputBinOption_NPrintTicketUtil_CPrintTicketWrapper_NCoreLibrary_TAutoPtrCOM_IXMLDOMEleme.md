# publicdm::ReadStandardInputBinOption(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,short *)

- ea: `0x180020324`
- end: `0x180020649`
- name: `?ReadStandardInputBinOption@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGPEAF@Z`
- size: `805`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x180004b00`
- `0x1800056e0`
- `0x180020020`
- `0x180020324`

## string_xrefs

- `0x18002048c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::ReadStandardInputBinOption(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement **a2,
        char *a3,
        __int16 *a4)
{
  struct IXMLDOMElement *v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // r15
  int v9; // r10d
  int PrintSchemaPropertyValue; // eax
  __int16 v11; // di
  int v12; // r13d
  int v13; // r10d
  char *v14; // rax
  int v15; // r9d
  char *v16; // r8
  int v17; // ecx
  int v18; // edx
  int v19; // eax
  const OLECHAR *v20; // rax
  int v21; // ecx
  int v22; // edx
  unsigned __int16 *v23; // rax
  int v24; // ecx
  int v25; // edx
  unsigned __int16 *v26; // rax
  bool v27; // zf
  __int64 v28; // r8
  int v29; // ecx
  int v30; // edx
  unsigned __int16 *v31; // rax
  bool v32; // zf
  __int64 v33; // r8
  int v34; // ecx
  int v35; // edx
  unsigned __int16 *v36; // rax
  bool v37; // zf
  __int64 v38; // r8
  int v39; // ecx
  int v40; // edx
  unsigned int v41; // ebx
  unsigned __int16 *v43; // [rsp+38h] [rbp-28h] BYREF
  __int64 v44; // [rsp+40h] [rbp-20h] BYREF
  __int64 v45; // [rsp+48h] [rbp-18h] BYREF
  __int64 v46; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v47; // [rsp+58h] [rbp-8h] BYREF
  int NameAttribute; // [rsp+A8h] [rbp+48h]

  v5 = *a2;
  v6 = 0;
  *a4 = 0;
  v7 = 0;
  v43 = 0;
  v47 = 0;
  v8 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, v5, &v47, &v43, 0);
  v9 = NameAttribute;
  if ( NameAttribute >= 0 )
  {
    NameAttribute = ReadPrintSchemaPropertyValue(this);
    v9 = NameAttribute;
    if ( NameAttribute >= 0 )
    {
      NameAttribute = ReadPrintSchemaPropertyValue(this);
      v9 = NameAttribute;
      if ( NameAttribute >= 0 )
      {
        PrintSchemaPropertyValue = ReadPrintSchemaPropertyValue(this);
        v8 = v46;
        v9 = PrintSchemaPropertyValue;
        NameAttribute = PrintSchemaPropertyValue;
      }
      v7 = v45;
    }
    v6 = v44;
  }
  if ( v9 >= 0 )
  {
    v11 = 0;
    v12 = 0;
    if ( word_180030850[0] )
    {
      v13 = 0;
      while ( 1 )
      {
        v14 = *(char **)&word_180030850[24 * v12 + 8];
        v15 = 0;
        if ( v14 )
        {
          if ( v43 )
          {
            v16 = (char *)((char *)v43 - v14);
            do
            {
              v17 = *(unsigned __int16 *)&v16[(_QWORD)v14];
              v18 = *(unsigned __int16 *)v14 - v17;
              if ( v18 )
                break;
              v14 += 2;
            }
            while ( v17 );
            if ( !v18 )
            {
              v19 = *(_DWORD *)&word_180030850[24 * v12 + 2];
              if ( v19 )
              {
                if ( v19 == 1 && v47 )
                {
                  v23 = (unsigned __int16 *)a3;
                  do
                  {
                    v24 = *(unsigned __int16 *)((char *)v23 + (char *)v47 - a3);
                    v25 = *v23 - v24;
                    if ( v25 )
                      break;
                    ++v23;
                  }
                  while ( v24 );
                  if ( !v25 )
                    v15 = 1;
                }
              }
              else if ( v47 )
              {
                v20 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
                do
                {
                  v21 = *(const OLECHAR *)((char *)v20
                                         + (char *)v47
                                         - (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords");
                  v22 = *v20 - v21;
                  if ( v22 )
                    break;
                  ++v20;
                }
                while ( v21 );
                if ( !v22 )
                  v15 = 1;
              }
            }
          }
        }
        else
        {
          LOBYTE(v15) = v43 == 0;
        }
        v26 = *(unsigned __int16 **)&word_180030850[24 * v12 + 12];
        if ( v26 )
        {
          if ( !v6 )
            goto LABEL_40;
          v28 = v6 - (_QWORD)v26;
          do
          {
            v29 = *(unsigned __int16 *)((char *)v26 + v28);
            v30 = *v26 - v29;
            if ( v30 )
              break;
            ++v26;
          }
          while ( v29 );
          v27 = v30 == 0;
        }
        else
        {
          v27 = v6 == 0;
        }
        if ( v27 )
          ++v15;
LABEL_40:
        v31 = *(unsigned __int16 **)&word_180030850[24 * v12 + 16];
        if ( v31 )
        {
          if ( !v7 )
            goto LABEL_49;
          v33 = v7 - (_QWORD)v31;
          do
          {
            v34 = *(unsigned __int16 *)((char *)v31 + v33);
            v35 = *v31 - v34;
            if ( v35 )
              break;
            ++v31;
          }
          while ( v34 );
          v32 = v35 == 0;
        }
        else
        {
          v32 = v7 == 0;
        }
        if ( v32 )
          ++v15;
LABEL_49:
        v36 = *(unsigned __int16 **)&word_180030850[24 * v12 + 20];
        if ( !v36 )
        {
          v37 = v8 == 0;
          goto LABEL_56;
        }
        if ( v8 )
        {
          v38 = v8 - (_QWORD)v36;
          do
          {
            v39 = *(unsigned __int16 *)((char *)v36 + v38);
            v40 = *v36 - v39;
            if ( v40 )
              break;
            ++v36;
          }
          while ( v39 );
          v37 = v40 == 0;
LABEL_56:
          if ( v37 )
            ++v15;
        }
        if ( v15 > v13 )
        {
          v11 = word_180030850[24 * v12];
          if ( v15 == 4 )
            goto LABEL_62;
          v13 = v15;
        }
        if ( !word_180030850[24 * ++v12] )
        {
LABEL_62:
          v9 = NameAttribute;
          if ( v11 )
            *a4 = v11;
          break;
        }
      }
    }
  }
  v41 = 0;
  if ( v9 < 0 )
    v41 = v9;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v46);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v45);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v44);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v47);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v43);
  return v41;
}

```

## disassembly

```asm
0x180020324  mov     [rsp-38h+arg_18], r9
0x180020329  mov     [rsp-38h+arg_10], r8
0x18002032e  push    rbp
0x18002032f  push    rbx
0x180020330  push    rsi
0x180020331  push    rdi
0x180020332  push    r13
0x180020334  push    r14
0x180020336  push    r15
0x180020338  mov     rbp, rsp
0x18002033b  sub     rsp, 60h
0x18002033f  mov     rdi, rcx
0x180020342  lea     r8, [rbp+var_8]; unsigned __int16 **
0x180020346  xor     ecx, ecx
0x180020348  mov     rbx, rdx
0x18002034b  mov     rdx, [rdx]; struct IXMLDOMElement *
0x18002034e  mov     esi, ecx
0x180020350  mov     [r9], cx
0x180020354  mov     r14d, ecx
0x180020357  mov     [rbp+var_28], rcx
0x18002035b  lea     r9, [rbp+var_28]; unsigned __int16 **
0x18002035f  mov     [rbp+var_8], rcx
0x180020363  mov     r15d, ecx
0x180020366  mov     [rbp+var_20], rcx
0x18002036a  mov     [rbp+var_18], rcx
0x18002036e  mov     [rbp+var_10], rcx
0x180020372  mov     [rsp+60h+var_40], ecx; int
0x180020376  mov     rcx, rdi; this
0x180020379  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x18002037e  xor     r8d, r8d
0x180020381  mov     [rbp+arg_8], eax
0x180020384  mov     r10d, eax
0x180020387  test    eax, eax
0x180020389  js      short loc_1800203FC
0x18002038b  lea     r9, [rbp+var_20]
0x18002038f  mov     rdx, rbx
0x180020392  lea     r8, aBintype; "BinType"
0x180020399  mov     rcx, rdi; this
0x18002039c  call    ?ReadPrintSchemaPropertyValue@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGAEAVTAutoPtrBSTR@4@@Z; ReadPrintSchemaPropertyValue(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x1800203a1  xor     r8d, r8d
0x1800203a4  mov     [rbp+arg_8], eax
0x1800203a7  mov     r10d, eax
0x1800203aa  test    eax, eax
0x1800203ac  js      short loc_1800203F8
0x1800203ae  lea     r9, [rbp+var_18]
0x1800203b2  mov     rdx, rbx
0x1800203b5  lea     r8, aFeedtype; "FeedType"
0x1800203bc  mov     rcx, rdi; this
0x1800203bf  call    ?ReadPrintSchemaPropertyValue@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGAEAVTAutoPtrBSTR@4@@Z; ReadPrintSchemaPropertyValue(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x1800203c4  xor     r8d, r8d
0x1800203c7  mov     [rbp+arg_8], eax
0x1800203ca  mov     r10d, eax
0x1800203cd  test    eax, eax
0x1800203cf  js      short loc_1800203F4
0x1800203d1  lea     r9, [rbp+var_10]
0x1800203d5  mov     rdx, rbx
0x1800203d8  lea     r8, aMediacapacity; "MediaCapacity"
0x1800203df  mov     rcx, rdi; this
0x1800203e2  call    ?ReadPrintSchemaPropertyValue@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGAEAVTAutoPtrBSTR@4@@Z; ReadPrintSchemaPropertyValue(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,NCoreLibrary::TAutoPtrBSTR &)
0x1800203e7  mov     r15, [rbp+var_10]
0x1800203eb  mov     r10d, eax
0x1800203ee  mov     [rbp+arg_8], eax
0x1800203f1  xor     r8d, r8d
0x1800203f4  mov     r14, [rbp+var_18]
0x1800203f8  mov     rsi, [rbp+var_20]
0x1800203fc  test    r10d, r10d
0x1800203ff  js      loc_180020601
0x180020405  cmp     cs:word_180030850, r8w
0x18002040d  mov     edi, r8d
0x180020410  mov     r13d, r8d
0x180020413  jz      loc_180020601
0x180020419  mov     rbx, [rbp+var_8]
0x18002041d  lea     r9, word_180030850
0x180020424  mov     r10d, r8d
0x180020427  movsxd  rax, r13d
0x18002042a  lea     r11, [rax+rax*2]
0x18002042e  add     r11, r11
0x180020431  mov     rax, [r9+r11*8+10h]
0x180020436  mov     r9d, r8d
0x180020439  test    rax, rax
0x18002043c  jnz     short loc_18002044B
0x18002043e  cmp     [rbp+var_28], r8
0x180020442  setz    r9b
0x180020446  jmp     loc_1800204EF
0x18002044b  cmp     [rbp+var_28], r8
0x18002044f  jz      loc_1800204EF
0x180020455  mov     r8, [rbp+var_28]
0x180020459  sub     r8, rax
0x18002045c  movzx   edx, word ptr [rax]
0x18002045f  movzx   ecx, word ptr [rax+r8]
0x180020464  sub     edx, ecx
0x180020466  jnz     short loc_180020470
0x180020468  add     rax, 2
0x18002046c  test    ecx, ecx
0x18002046e  jnz     short loc_18002045C
0x180020470  xor     r8d, r8d
0x180020473  test    edx, edx
0x180020475  jnz     short loc_1800204EF
0x180020477  lea     rax, word_180030850
0x18002047e  mov     eax, [rax+r11*8+4]
0x180020483  test    eax, eax
0x180020485  jnz     short loc_1800204BA
0x180020487  test    rbx, rbx
0x18002048a  jz      short loc_1800204EF
0x18002048c  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180020493  mov     r8, rbx
0x180020496  sub     r8, rax
0x180020499  movzx   edx, word ptr [rax]
0x18002049c  movzx   ecx, word ptr [rax+r8]
0x1800204a1  sub     edx, ecx
0x1800204a3  jnz     short loc_1800204AD
0x1800204a5  add     rax, 2
0x1800204a9  test    ecx, ecx
0x1800204ab  jnz     short loc_180020499
0x1800204ad  xor     r8d, r8d
0x1800204b0  test    edx, edx
0x1800204b2  jnz     short loc_1800204EF
0x1800204b4  lea     r9d, [r8+1]
0x1800204b8  jmp     short loc_1800204EF
0x1800204ba  cmp     eax, 1
0x1800204bd  jnz     short loc_1800204EF
0x1800204bf  test    rbx, rbx
0x1800204c2  jz      short loc_1800204EF
0x1800204c4  mov     rax, [rbp+arg_10]
0x1800204c8  mov     r8, rbx
0x1800204cb  sub     r8, rax
0x1800204ce  movzx   edx, word ptr [rax]
0x1800204d1  movzx   ecx, word ptr [rax+r8]
0x1800204d6  sub     edx, ecx
0x1800204d8  jnz     short loc_1800204E2
0x1800204da  add     rax, 2
0x1800204de  test    ecx, ecx
0x1800204e0  jnz     short loc_1800204CE
0x1800204e2  xor     r8d, r8d
0x1800204e5  test    edx, edx
0x1800204e7  lea     eax, [r8+1]
0x1800204eb  cmovz   r9d, eax
0x1800204ef  lea     rax, word_180030850
0x1800204f6  mov     rax, [rax+r11*8+18h]
0x1800204fb  test    rax, rax
0x1800204fe  jnz     short loc_180020505
0x180020500  test    rsi, rsi
0x180020503  jmp     short loc_180020529
0x180020505  test    rsi, rsi
0x180020508  jz      short loc_18002052E
0x18002050a  mov     r8, rsi
0x18002050d  sub     r8, rax
0x180020510  movzx   edx, word ptr [rax]
0x180020513  movzx   ecx, word ptr [rax+r8]
0x180020518  sub     edx, ecx
0x18002051a  jnz     short loc_180020524
0x18002051c  add     rax, 2
0x180020520  test    ecx, ecx
0x180020522  jnz     short loc_180020510
0x180020524  xor     r8d, r8d
0x180020527  test    edx, edx
0x180020529  jnz     short loc_18002052E
0x18002052b  inc     r9d
0x18002052e  lea     rax, word_180030850
0x180020535  mov     rax, [rax+r11*8+20h]
0x18002053a  test    rax, rax
0x18002053d  jnz     short loc_180020544
0x18002053f  test    r14, r14
0x180020542  jmp     short loc_180020568
0x180020544  test    r14, r14
0x180020547  jz      short loc_18002056D
0x180020549  mov     r8, r14
0x18002054c  sub     r8, rax
0x18002054f  movzx   edx, word ptr [rax]
0x180020552  movzx   ecx, word ptr [rax+r8]
0x180020557  sub     edx, ecx
0x180020559  jnz     short loc_180020563
0x18002055b  add     rax, 2
0x18002055f  test    ecx, ecx
0x180020561  jnz     short loc_18002054F
0x180020563  xor     r8d, r8d
0x180020566  test    edx, edx
0x180020568  jnz     short loc_18002056D
0x18002056a  inc     r9d
0x18002056d  lea     rax, word_180030850
0x180020574  mov     rax, [rax+r11*8+28h]
0x180020579  test    rax, rax
0x18002057c  jnz     short loc_180020583
0x18002057e  test    r15, r15
0x180020581  jmp     short loc_1800205A7
0x180020583  test    r15, r15
0x180020586  jz      short loc_1800205B3
0x180020588  mov     r8, r15
0x18002058b  sub     r8, rax
0x18002058e  movzx   edx, word ptr [rax]
0x180020591  movzx   ecx, word ptr [rax+r8]
0x180020596  sub     edx, ecx
0x180020598  jnz     short loc_1800205A2
0x18002059a  add     rax, 2
0x18002059e  test    ecx, ecx
0x1800205a0  jnz     short loc_18002058E
0x1800205a2  xor     r8d, r8d
0x1800205a5  test    edx, edx
0x1800205a7  jnz     short loc_1800205B3
0x1800205a9  mov     edx, 1
0x1800205ae  add     r9d, edx
0x1800205b1  jmp     short loc_1800205B8
0x1800205b3  mov     edx, 1
0x1800205b8  cmp     r9d, r10d
0x1800205bb  jle     short loc_1800205D2
0x1800205bd  lea     rax, word_180030850
0x1800205c4  movzx   edi, word ptr [rax+r11*8]
0x1800205c9  cmp     r9d, 4
0x1800205cd  jz      short loc_1800205F1
0x1800205cf  mov     r10d, r9d
0x1800205d2  add     r13d, edx
0x1800205d5  lea     r9, word_180030850
0x1800205dc  movsxd  rax, r13d
0x1800205df  lea     rcx, [rax+rax*2]
0x1800205e3  add     rcx, rcx
0x1800205e6  cmp     [r9+rcx*8], r8w
0x1800205eb  jnz     loc_180020427
0x1800205f1  mov     r10d, [rbp+arg_8]
0x1800205f5  test    di, di
0x1800205f8  jz      short loc_180020601
0x1800205fa  mov     rax, [rbp+arg_18]
0x1800205fe  mov     [rax], di
0x180020601  test    r10d, r10d
0x180020604  lea     rcx, [rbp+var_10]
0x180020608  mov     ebx, r8d
0x18002060b  cmovs   ebx, r10d
0x18002060f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180020614  lea     rcx, [rbp+var_18]
0x180020618  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18002061d  lea     rcx, [rbp+var_20]
0x180020621  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180020626  lea     rcx, [rbp+var_8]
0x18002062a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18002062f  lea     rcx, [rbp+var_28]
0x180020633  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180020638  mov     eax, ebx
0x18002063a  add     rsp, 60h
0x18002063e  pop     r15
0x180020640  pop     r14
0x180020642  pop     r13
0x180020644  pop     rdi
0x180020645  pop     rsi
0x180020646  pop     rbx
0x180020647  pop     rbp
0x180020648  retn
```
