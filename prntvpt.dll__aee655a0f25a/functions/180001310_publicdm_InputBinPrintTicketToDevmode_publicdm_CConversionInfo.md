# publicdm::InputBinPrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x180001310`
- end: `0x1800014d7`
- name: `?InputBinPrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `455`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001310`
- `0x1800019f0`
- `0x180002084`
- `0x180004b00`
- `0x1800056e0`
- `0x18001b124`
- `0x180020324`
- `0x180023010`

## string_xrefs

- `0x18000133c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::InputBinPrintTicketToDevmode(
        publicdm *this,
        struct publicdm::CConversionInfo *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  struct IXMLDOMElement *v6; // rbx
  struct IXMLDOMElement *v7; // rdx
  int ChildWithName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v9; // rcx
  const unsigned __int16 *v10; // r9
  struct IXMLDOMElement *v11; // rdi
  int NameAttribute; // r14d
  int ChildWithoutName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v14; // rcx
  unsigned __int16 *v15; // r15
  char *v16; // rax
  unsigned int *v17; // r8
  signed __int64 v18; // r15
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rax
  char *v22; // rax
  int v23; // eax
  __int16 v24; // cx
  unsigned int v25; // esi
  struct IXMLDOMElement *v27; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp+48h] BYREF
  struct IXMLDOMElement *v29; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp+58h] BYREF

  v5 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v27 = 0;
  v6 = 0;
  v7 = (struct IXMLDOMElement *)*((_QWORD *)v5 + 3);
  v29 = 0;
  ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                    v5,
                    v7,
                    L"Feature",
                    a4,
                    (char *)L"JobInputBin",
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    &v27);
  v11 = v27;
  NameAttribute = ChildWithName;
  if ( ChildWithName >= 0 )
  {
    if ( !v27
      || (ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                               v9,
                               v27,
                               (char *)L"Option",
                               v10,
                               &v29),
          v6 = v29,
          NameAttribute = ChildWithoutName,
          ChildWithoutName >= 0) )
    {
      if ( v6 )
      {
        v14 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
        String2 = 0;
        v30 = 0;
        LODWORD(v27) = 0;
        NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(v14, v6, &v30, &String2, 0);
        if ( NameAttribute >= 0 )
        {
          v15 = v30;
          if ( !v30 || !String2 )
            goto LABEL_14;
          v16 = (char *)(*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 8LL))(this);
          v18 = (char *)v15 - v16;
          do
          {
            v19 = *(unsigned __int16 *)&v16[v18];
            v20 = *(unsigned __int16 *)v16 - v19;
            if ( v20 )
              break;
            v16 += 2;
          }
          while ( v19 );
          if ( !v20
            && (unsigned int)publicdm::BReadDriverIDFromPrintTicketName(String2, (const unsigned __int16 *)&v27, v17) )
          {
            *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x200u;
            *(_WORD *)(*((_QWORD *)this + 2) + 88LL) = (_WORD)v27;
          }
          else
          {
LABEL_14:
            v21 = *(_QWORD *)this;
            LOWORD(v27) = 0;
            v22 = (char *)(*(__int64 (__fastcall **)(publicdm *))(v21 + 8))(this);
            v23 = publicdm::ReadStandardInputBinOption(
                    *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                    &v29,
                    v22,
                    (__int16 *)&v27);
            v24 = (__int16)v27;
            NameAttribute = v23;
            if ( (_WORD)v27 )
            {
              *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x200u;
              *(_WORD *)(*((_QWORD *)this + 2) + 88LL) = v24;
            }
          }
        }
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v30);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String2);
      }
    }
  }
  v25 = 0;
  if ( NameAttribute < 0 )
    v25 = NameAttribute;
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
  return v25;
}

```

## disassembly

```asm
0x180001310  push    rbp
0x180001312  push    rbx
0x180001313  push    rsi
0x180001314  push    rdi
0x180001315  push    r13
0x180001317  push    r14
0x180001319  push    r15
0x18000131b  mov     rbp, rsp
0x18000131e  sub     rsp, 40h
0x180001322  lea     rax, [rbp+arg_0]
0x180001326  mov     rsi, rcx
0x180001329  mov     rcx, [rcx+60h]; this
0x18000132d  lea     r8, aFeature; "Feature"
0x180001334  mov     [rsp+40h+var_10], rax; struct IXMLDOMElement **
0x180001339  xor     r13d, r13d
0x18000133c  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180001343  mov     [rbp+arg_0], r13
0x180001347  mov     [rsp+40h+var_18], rax; unsigned __int16 *
0x18000134c  mov     ebx, r13d
0x18000134f  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x180001353  lea     rax, aJobinputbin; "JobInputBin"
0x18000135a  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18000135f  mov     [rbp+arg_10], rbx
0x180001363  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180001368  mov     rdi, [rbp+arg_0]
0x18000136c  mov     r14d, eax
0x18000136f  test    eax, eax
0x180001371  js      loc_180001494
0x180001377  test    rdi, rdi
0x18000137a  jz      short loc_1800013A3
0x18000137c  lea     rax, [rbp+arg_10]
0x180001380  mov     rdx, rdi; struct IXMLDOMElement *
0x180001383  lea     r8, aOption; "Option"
0x18000138a  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18000138f  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180001394  mov     rbx, [rbp+arg_10]
0x180001398  mov     r14d, eax
0x18000139b  test    eax, eax
0x18000139d  js      loc_180001494
0x1800013a3  test    rbx, rbx
0x1800013a6  jz      loc_180001494
0x1800013ac  mov     rcx, [rsi+60h]; this
0x1800013b0  lea     r9, [rbp+String2]; unsigned __int16 **
0x1800013b4  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800013b8  mov     [rbp+String2], r13
0x1800013bc  mov     rdx, rbx; struct IXMLDOMElement *
0x1800013bf  mov     [rbp+arg_18], r13
0x1800013c3  mov     dword ptr [rbp+arg_0], r13d
0x1800013c7  mov     dword ptr [rsp+40h+var_20], r13d; int
0x1800013cc  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800013d1  mov     r14d, eax
0x1800013d4  test    eax, eax
0x1800013d6  js      loc_180001482
0x1800013dc  mov     r15, [rbp+arg_18]
0x1800013e0  test    r15, r15
0x1800013e3  jz      short loc_18000143D
0x1800013e5  cmp     [rbp+String2], r13
0x1800013e9  jz      short loc_18000143D
0x1800013eb  mov     rax, [rsi]
0x1800013ee  mov     rcx, rsi
0x1800013f1  mov     rax, [rax+8]
0x1800013f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013fa  sub     r15, rax
0x1800013fd  movzx   ecx, word ptr [rax]
0x180001400  movzx   edx, word ptr [rax+r15]
0x180001405  sub     ecx, edx
0x180001407  jnz     short loc_180001411
0x180001409  add     rax, 2
0x18000140d  test    edx, edx
0x18000140f  jnz     short loc_1800013FD
0x180001411  test    ecx, ecx
0x180001413  jnz     short loc_18000143D
0x180001415  mov     rcx, [rbp+String2]; String2
0x180001419  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x18000141d  call    ?BReadDriverIDFromPrintTicketName@publicdm@@YAHPEBGPEAK@Z; publicdm::BReadDriverIDFromPrintTicketName(ushort const *,ulong *)
0x180001422  test    eax, eax
0x180001424  jz      short loc_18000143D
0x180001426  mov     rax, [rsi+10h]
0x18000142a  bts     dword ptr [rax+48h], 9
0x18000142f  mov     rcx, [rsi+10h]
0x180001433  movzx   eax, word ptr [rbp+arg_0]
0x180001437  mov     [rcx+58h], ax
0x18000143b  jmp     short loc_180001482
0x18000143d  mov     rax, [rsi]
0x180001440  mov     rcx, rsi
0x180001443  mov     word ptr [rbp+arg_0], r13w
0x180001448  mov     rax, [rax+8]
0x18000144c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001451  mov     rcx, [rsi+60h]; this
0x180001455  lea     r9, [rbp+arg_0]
0x180001459  mov     r8, rax
0x18000145c  lea     rdx, [rbp+arg_10]
0x180001460  call    ?ReadStandardInputBinOption@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@PEBGPEAF@Z; publicdm::ReadStandardInputBinOption(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &,ushort const *,short *)
0x180001465  movzx   ecx, word ptr [rbp+arg_0]
0x180001469  mov     r14d, eax
0x18000146c  test    cx, cx
0x18000146f  jz      short loc_180001482
0x180001471  mov     rax, [rsi+10h]
0x180001475  bts     dword ptr [rax+48h], 9
0x18000147a  mov     rax, [rsi+10h]
0x18000147e  mov     [rax+58h], cx
0x180001482  lea     rcx, [rbp+arg_18]
0x180001486  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000148b  lea     rcx, [rbp+String2]
0x18000148f  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180001494  test    r14d, r14d
0x180001497  mov     esi, r13d
0x18000149a  cmovs   esi, r14d
0x18000149e  test    rbx, rbx
0x1800014a1  jz      short loc_1800014B2
0x1800014a3  mov     rax, [rbx]
0x1800014a6  mov     rcx, rbx
0x1800014a9  mov     rax, [rax+10h]
0x1800014ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014b2  test    rdi, rdi
0x1800014b5  jz      short loc_1800014C6
0x1800014b7  mov     rdx, [rdi]
0x1800014ba  mov     rcx, rdi
0x1800014bd  mov     rax, [rdx+10h]
0x1800014c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014c6  mov     eax, esi
0x1800014c8  add     rsp, 40h
0x1800014cc  pop     r15
0x1800014ce  pop     r14
0x1800014d0  pop     r13
0x1800014d2  pop     rdi
0x1800014d3  pop     rsi
0x1800014d4  pop     rbx
0x1800014d5  pop     rbp
0x1800014d6  retn
```
