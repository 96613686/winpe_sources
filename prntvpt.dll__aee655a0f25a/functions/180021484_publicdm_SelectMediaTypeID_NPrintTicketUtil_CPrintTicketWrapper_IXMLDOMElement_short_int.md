# publicdm::SelectMediaTypeID(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,short *,int *)

- ea: `0x180021484`
- end: `0x180021732`
- name: `?SelectMediaTypeID@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAFPEAH@Z`
- size: `686`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct IXMLDOMElement *, struct IXMLDOMElement *, __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ee20`

## callees

- `0x180004b00`
- `0x1800056e0`
- `0x180021484`
- `0x180021738`

## string_xrefs

- `0x180021504`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::SelectMediaTypeID(
        publicdm *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        __int16 *a4)
{
  int NameAttribute; // r14d
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v10; // rbx
  int v11; // edx
  int v12; // eax
  unsigned __int16 *v13; // rax
  int v14; // edx
  int v15; // ecx
  unsigned __int16 *v16; // rax
  int v17; // edx
  int v18; // ecx
  unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // ecx
  unsigned __int16 *v22; // rax
  int v23; // edx
  int v24; // ecx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rcx
  int v27; // r9d
  int v28; // edx
  unsigned __int16 *v29; // rcx
  int v30; // r9d
  int v31; // edx
  int v32; // edx
  int v33; // ecx
  char *v34; // rdx
  int v35; // ecx
  int v36; // eax
  unsigned int v37; // ebx
  unsigned __int16 *v39; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v40; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 *v41; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v42; // [rsp+88h] [rbp+48h] BYREF

  LOWORD(a3->lpVtbl) = 1;
  *(_DWORD *)a4 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v42 = 0;
  NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, a2, &v42, &v41, 0);
  if ( NameAttribute < 0 )
    goto LABEL_8;
  v9 = v42;
  if ( !v42 )
    goto LABEL_8;
  v10 = v41;
  if ( v41 )
  {
    do
    {
      v11 = *(unsigned __int16 *)((char *)v9
                                + (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords"
                                - (char *)v42);
      v12 = *v9 - v11;
      if ( v12 )
        break;
      ++v9;
    }
    while ( v11 );
    if ( v12 )
    {
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v41);
LABEL_8:
      v10 = v41;
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v42);
  if ( NameAttribute >= 0 )
  {
    NameAttribute = SelectValueInProperty(this, a2, L"BackCoating", &v40);
    if ( NameAttribute >= 0 )
    {
      NameAttribute = SelectValueInProperty(this, a2, L"Material", &v39);
      if ( NameAttribute >= 0 )
      {
        if ( v10 )
        {
          v13 = v10;
          do
          {
            v14 = *(unsigned __int16 *)((char *)v13 + (char *)L"Transparency" - (char *)v10);
            v15 = *v13 - v14;
            if ( v15 )
              break;
            ++v13;
          }
          while ( v14 );
          if ( !v15 )
            goto LABEL_21;
        }
        v16 = v39;
        if ( v39 )
        {
          do
          {
            v17 = *(unsigned __int16 *)((char *)v16 + (char *)L"Transparency" - (char *)v39);
            v18 = *v16 - v17;
            if ( v18 )
              break;
            ++v16;
          }
          while ( v17 );
          if ( !v18 )
          {
LABEL_21:
            LOWORD(a3->lpVtbl) = 2;
LABEL_44:
            *(_DWORD *)a4 = 1;
            goto LABEL_51;
          }
        }
        if ( v10 )
        {
          v19 = v10;
          do
          {
            v20 = *(unsigned __int16 *)((char *)v19 + (char *)L"PhotographicGlossy" - (char *)v10);
            v21 = *v19 - v20;
            if ( v21 )
              break;
            ++v19;
          }
          while ( v20 );
          if ( !v21 )
            goto LABEL_43;
          v22 = v10;
          do
          {
            v23 = *(unsigned __int16 *)((char *)v22 + (char *)L"PhotographicHighGloss" - (char *)v10);
            v24 = *v22 - v23;
            if ( v24 )
              break;
            ++v22;
          }
          while ( v23 );
          if ( !v24 )
            goto LABEL_43;
        }
        v25 = v40;
        if ( v40 )
        {
          v26 = v40;
          do
          {
            v27 = *(unsigned __int16 *)((char *)v26 + (char *)L"Glossy" - (char *)v40);
            v28 = *v26 - v27;
            if ( v28 )
              break;
            ++v26;
          }
          while ( v27 );
          if ( !v28 )
            goto LABEL_43;
          v29 = v40;
          do
          {
            v30 = *(unsigned __int16 *)((char *)v29 + (char *)L"HighGloss" - (char *)v40);
            v31 = *v29 - v30;
            if ( v31 )
              break;
            ++v29;
          }
          while ( v30 );
          if ( !v31 )
            goto LABEL_43;
          do
          {
            v32 = *(unsigned __int16 *)((char *)v25 + (char *)L"SemiGloss" - (char *)v40);
            v33 = *v25 - v32;
            if ( v33 )
              break;
            ++v25;
          }
          while ( v32 );
          if ( !v33 )
          {
LABEL_43:
            LOWORD(a3->lpVtbl) = 3;
            goto LABEL_44;
          }
        }
        if ( v10 )
        {
          v34 = (char *)((char *)L"Plain" - (char *)v10);
          do
          {
            v35 = *(unsigned __int16 *)&v34[(_QWORD)v10];
            v36 = *v10 - v35;
            if ( v36 )
              break;
            ++v10;
          }
          while ( v35 );
          if ( !v36 )
          {
            LOWORD(a3->lpVtbl) = 1;
            *(_DWORD *)a4 = 1;
          }
        }
      }
    }
  }
LABEL_51:
  v37 = 0;
  if ( NameAttribute < 0 )
    v37 = NameAttribute;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v39);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v40);
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v41);
  return v37;
}

```

## disassembly

```asm
0x180021484  mov     [rsp-28h+arg_0], rbx
0x180021489  mov     [rsp-28h+arg_8], rsi
0x18002148e  push    rbp
0x18002148f  push    rdi
0x180021490  push    r12
0x180021492  push    r14
0x180021494  push    r15
0x180021496  mov     rbp, rsp
0x180021499  sub     rsp, 40h
0x18002149d  mov     r15, r9
0x1800214a0  mov     word ptr [r8], 1
0x1800214a6  mov     r12, r8
0x1800214a9  mov     dword ptr [r9], 0
0x1800214b0  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x1800214b4  mov     [rbp+arg_10], 0
0x1800214bc  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800214c0  mov     [rbp+var_8], 0
0x1800214c8  mov     rdi, rdx
0x1800214cb  mov     [rbp+var_10], 0
0x1800214d3  mov     rsi, rcx
0x1800214d6  mov     [rbp+arg_18], 0
0x1800214de  mov     [rsp+40h+var_20], 0; int
0x1800214e6  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800214eb  mov     r14d, eax
0x1800214ee  test    eax, eax
0x1800214f0  js      short loc_18002152F
0x1800214f2  mov     rcx, [rbp+arg_18]
0x1800214f6  test    rcx, rcx
0x1800214f9  jz      short loc_18002152F
0x1800214fb  mov     rbx, [rbp+arg_10]
0x1800214ff  test    rbx, rbx
0x180021502  jz      short loc_180021533
0x180021504  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18002150b  sub     r8, rcx
0x18002150e  movzx   eax, word ptr [rcx]
0x180021511  movzx   edx, word ptr [rcx+r8]
0x180021516  sub     eax, edx
0x180021518  jnz     short loc_180021522
0x18002151a  add     rcx, 2
0x18002151e  test    edx, edx
0x180021520  jnz     short loc_18002150E
0x180021522  test    eax, eax
0x180021524  jz      short loc_180021533
0x180021526  lea     rcx, [rbp+arg_10]
0x18002152a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18002152f  mov     rbx, [rbp+arg_10]
0x180021533  lea     rcx, [rbp+arg_18]
0x180021537  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18002153c  test    r14d, r14d
0x18002153f  js      loc_1800216F5
0x180021545  lea     r9, [rbp+var_8]; unsigned __int16 **
0x180021549  mov     rdx, rdi; struct IXMLDOMElement *
0x18002154c  lea     r8, aBackcoating; "BackCoating"
0x180021553  mov     rcx, rsi; this
0x180021556  call    ?SelectValueInProperty@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEBGPEAPEAG@Z; SelectValueInProperty(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort * *)
0x18002155b  mov     r14d, eax
0x18002155e  test    eax, eax
0x180021560  js      loc_1800216F5
0x180021566  lea     r9, [rbp+var_10]; unsigned __int16 **
0x18002156a  mov     rdx, rdi; struct IXMLDOMElement *
0x18002156d  lea     r8, aMaterial; "Material"
0x180021574  mov     rcx, rsi; this
0x180021577  call    ?SelectValueInProperty@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEBGPEAPEAG@Z; SelectValueInProperty(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort * *)
0x18002157c  mov     r14d, eax
0x18002157f  test    eax, eax
0x180021581  js      loc_1800216F5
0x180021587  mov     r10d, 2
0x18002158d  test    rbx, rbx
0x180021590  jz      short loc_1800215B6
0x180021592  lea     r8, aTransparency; "Transparency"
0x180021599  mov     rax, rbx
0x18002159c  sub     r8, rbx
0x18002159f  movzx   ecx, word ptr [rax]
0x1800215a2  movzx   edx, word ptr [rax+r8]
0x1800215a7  sub     ecx, edx
0x1800215a9  jnz     short loc_1800215B2
0x1800215ab  add     rax, r10
0x1800215ae  test    edx, edx
0x1800215b0  jnz     short loc_18002159F
0x1800215b2  test    ecx, ecx
0x1800215b4  jz      short loc_1800215E0
0x1800215b6  mov     rax, [rbp+var_10]
0x1800215ba  test    rax, rax
0x1800215bd  jz      short loc_1800215EA
0x1800215bf  lea     r8, aTransparency_0; "Transparency"
0x1800215c6  sub     r8, rax
0x1800215c9  movzx   ecx, word ptr [rax]
0x1800215cc  movzx   edx, word ptr [rax+r8]
0x1800215d1  sub     ecx, edx
0x1800215d3  jnz     short loc_1800215DC
0x1800215d5  add     rax, r10
0x1800215d8  test    edx, edx
0x1800215da  jnz     short loc_1800215C9
0x1800215dc  test    ecx, ecx
0x1800215de  jnz     short loc_1800215EA
0x1800215e0  mov     [r12], r10w
0x1800215e5  jmp     loc_1800216BA
0x1800215ea  test    rbx, rbx
0x1800215ed  jz      short loc_18002163D
0x1800215ef  lea     rdx, aPhotographicgl; "PhotographicGlossy"
0x1800215f6  mov     rax, rbx
0x1800215f9  sub     rdx, rbx
0x1800215fc  movzx   ecx, word ptr [rax]
0x1800215ff  movzx   r8d, word ptr [rax+rdx]
0x180021604  sub     ecx, r8d
0x180021607  jnz     short loc_180021611
0x180021609  add     rax, r10
0x18002160c  test    r8d, r8d
0x18002160f  jnz     short loc_1800215FC
0x180021611  test    ecx, ecx
0x180021613  jz      loc_1800216B3
0x180021619  lea     r8, aPhotographichi; "PhotographicHighGloss"
0x180021620  mov     rax, rbx
0x180021623  sub     r8, rbx
0x180021626  movzx   ecx, word ptr [rax]
0x180021629  movzx   edx, word ptr [rax+r8]
0x18002162e  sub     ecx, edx
0x180021630  jnz     short loc_180021639
0x180021632  add     rax, r10
0x180021635  test    edx, edx
0x180021637  jnz     short loc_180021626
0x180021639  test    ecx, ecx
0x18002163b  jz      short loc_1800216B3
0x18002163d  mov     rax, [rbp+var_8]
0x180021641  test    rax, rax
0x180021644  jz      short loc_1800216C3
0x180021646  lea     r8, aGlossy; "Glossy"
0x18002164d  mov     rcx, rax
0x180021650  sub     r8, rax
0x180021653  movzx   edx, word ptr [rcx]
0x180021656  movzx   r9d, word ptr [rcx+r8]
0x18002165b  sub     edx, r9d
0x18002165e  jnz     short loc_180021668
0x180021660  add     rcx, r10
0x180021663  test    r9d, r9d
0x180021666  jnz     short loc_180021653
0x180021668  test    edx, edx
0x18002166a  jz      short loc_1800216B3
0x18002166c  lea     r8, aHighgloss; "HighGloss"
0x180021673  mov     rcx, rax
0x180021676  sub     r8, rax
0x180021679  movzx   edx, word ptr [rcx]
0x18002167c  movzx   r9d, word ptr [rcx+r8]
0x180021681  sub     edx, r9d
0x180021684  jnz     short loc_18002168E
0x180021686  add     rcx, r10
0x180021689  test    r9d, r9d
0x18002168c  jnz     short loc_180021679
0x18002168e  test    edx, edx
0x180021690  jz      short loc_1800216B3
0x180021692  lea     r8, aSemigloss; "SemiGloss"
0x180021699  sub     r8, rax
0x18002169c  movzx   ecx, word ptr [rax]
0x18002169f  movzx   edx, word ptr [rax+r8]
0x1800216a4  sub     ecx, edx
0x1800216a6  jnz     short loc_1800216AF
0x1800216a8  add     rax, r10
0x1800216ab  test    edx, edx
0x1800216ad  jnz     short loc_18002169C
0x1800216af  test    ecx, ecx
0x1800216b1  jnz     short loc_1800216C3
0x1800216b3  mov     word ptr [r12], 3
0x1800216ba  mov     dword ptr [r15], 1
0x1800216c1  jmp     short loc_1800216F5
0x1800216c3  test    rbx, rbx
0x1800216c6  jz      short loc_1800216F5
0x1800216c8  lea     rdx, aPlain; "Plain"
0x1800216cf  sub     rdx, rbx
0x1800216d2  movzx   eax, word ptr [rbx]
0x1800216d5  movzx   ecx, word ptr [rbx+rdx]
0x1800216d9  sub     eax, ecx
0x1800216db  jnz     short loc_1800216E4
0x1800216dd  add     rbx, r10
0x1800216e0  test    ecx, ecx
0x1800216e2  jnz     short loc_1800216D2
0x1800216e4  test    eax, eax
0x1800216e6  jnz     short loc_1800216F5
0x1800216e8  mov     eax, 1
0x1800216ed  mov     [r12], ax
0x1800216f2  mov     [r15], eax
0x1800216f5  xor     ebx, ebx
0x1800216f7  lea     rcx, [rbp+var_10]
0x1800216fb  test    r14d, r14d
0x1800216fe  cmovs   ebx, r14d
0x180021702  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021707  lea     rcx, [rbp+var_8]
0x18002170b  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021710  lea     rcx, [rbp+arg_10]
0x180021714  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180021719  mov     rsi, [rsp+40h+arg_8]
0x18002171e  mov     eax, ebx
0x180021720  mov     rbx, [rsp+40h+arg_0]
0x180021725  add     rsp, 40h
0x180021729  pop     r15
0x18002172b  pop     r14
0x18002172d  pop     r12
0x18002172f  pop     rdi
0x180021730  pop     rbp
0x180021731  retn
```
