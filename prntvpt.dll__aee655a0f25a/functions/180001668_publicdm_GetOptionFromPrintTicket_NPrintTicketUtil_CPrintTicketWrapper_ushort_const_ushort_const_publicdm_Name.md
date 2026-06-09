# publicdm::GetOptionFromPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,ushort const *,publicdm::NamedOption *,ulong,ulong *,ulong *,ulong)

- ea: `0x180001668`
- end: `0x180001807`
- name: `?GetOptionFromPrintTicket@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBG1PEAUNamedOption@1@KPEAK3K@Z`
- size: `415`
- prototype: `__int64 __usercall@<rax>(publicdm *__hidden this@<rcx>, struct NPrintTicketUtil::CPrintTicketWrapper *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, struct publicdm::NamedOption *, unsigned int, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e1f0`
- `0x18001e2f0`

## callees

- `0x180001668`
- `0x1800019f0`
- `0x180002084`
- `0x180004b00`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800017d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017e5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800017e5`

## string_xrefs

- `0x180001694`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::GetOptionFromPrintTicket(
        publicdm *this,
        struct IXMLDOMElement *a2,
        char *a3,
        const unsigned __int16 *a4,
        struct publicdm::NamedOption *a5,
        _DWORD *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  struct IXMLDOMElement *v8; // rdx
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rdi
  struct IXMLDOMElement *v11; // rbx
  int ChildWithName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v15; // rcx
  const unsigned __int16 *v16; // r9
  struct IXMLDOMElement *v17; // r14
  int v18; // edx
  int ChildWithoutName; // eax
  int NameAttribute; // eax
  __int64 i; // rcx
  unsigned __int16 *v22; // rax
  int v23; // r9d
  int v24; // r8d
  unsigned __int16 *v25; // rax
  int v26; // r9d
  int v27; // r8d
  unsigned int v28; // r15d
  struct IXMLDOMElement *v30; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v31; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMElement *v33; // [rsp+98h] [rbp+38h] BYREF

  v33 = a2;
  v8 = (struct IXMLDOMElement *)*((_QWORD *)this + 3);
  v9 = 0;
  v32 = 0;
  v10 = 0;
  v11 = 0;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                    this,
                    v8,
                    L"Feature",
                    a4,
                    a3,
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    &v30);
  v17 = v30;
  v18 = ChildWithName;
  if ( ChildWithName < 0
    || v30
    && (ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                             v15,
                             v30,
                             (char *)L"Option",
                             v16,
                             &v33),
        v11 = v33,
        v18 = ChildWithoutName,
        ChildWithoutName < 0) )
  {
LABEL_6:
    if ( v18 < 0 )
      goto LABEL_21;
    goto LABEL_7;
  }
  if ( v11 )
  {
    NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(this, v11, &v31, &v32, 0);
    v10 = v31;
    v18 = NameAttribute;
    v9 = v32;
    goto LABEL_6;
  }
LABEL_7:
  if ( v9 && v10 )
  {
    for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
    {
      v22 = v9;
      do
      {
        v23 = *(unsigned __int16 *)((char *)v22 + *(_QWORD *)&a4[12 * i + 4] - (_QWORD)v9);
        v24 = *v22 - v23;
        if ( v24 )
          break;
        ++v22;
      }
      while ( v23 );
      if ( !v24 )
      {
        v25 = v10;
        do
        {
          v26 = *(unsigned __int16 *)((char *)v25 + *(_QWORD *)&a4[12 * i] - (_QWORD)v10);
          v27 = *v25 - v26;
          if ( v27 )
            break;
          ++v25;
        }
        while ( v26 );
        if ( !v27 )
        {
          *a6 = *(_DWORD *)&a4[12 * i + 8];
          *a7 |= (unsigned int)a8;
          break;
        }
      }
    }
  }
LABEL_21:
  v28 = 0;
  if ( v18 < 0 )
    v28 = v18;
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v17->lpVtbl->Release)(v17);
  if ( v9 )
    SysFreeString(v9);
  if ( v10 )
    SysFreeString(v10);
  return v28;
}

```

## disassembly

```asm
0x180001668  mov     r11, rsp
0x18000166b  mov     [r11+8], rbx
0x18000166f  mov     [r11+18h], rsi
0x180001673  mov     [r11+10h], rdx
0x180001677  push    rbp
0x180001678  push    rdi
0x180001679  push    r12
0x18000167b  push    r14
0x18000167d  push    r15
0x18000167f  mov     rbp, rsp
0x180001682  sub     rsp, 60h
0x180001686  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x18000168a  lea     rax, [rbp+var_20]
0x18000168e  mov     [r11-58h], rax
0x180001692  xor     esi, esi
0x180001694  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18000169b  mov     [rbp+var_10], rsi
0x18000169f  mov     [r11-60h], rax
0x1800016a3  xor     edi, edi
0x1800016a5  mov     [r11-68h], r8
0x1800016a9  xor     ebx, ebx
0x1800016ab  lea     r8, aFeature; "Feature"
0x1800016b2  mov     [rbp+var_18], rdi
0x1800016b6  mov     r12, r9
0x1800016b9  mov     [rbp+var_20], rsi
0x1800016bd  mov     r15, rcx
0x1800016c0  mov     [rbp+arg_8], rbx
0x1800016c4  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800016c9  mov     r14, [rbp+var_20]
0x1800016cd  mov     edx, eax
0x1800016cf  test    eax, eax
0x1800016d1  js      short loc_180001720
0x1800016d3  test    r14, r14
0x1800016d6  jz      short loc_1800016FA
0x1800016d8  lea     rax, [rbp+arg_8]
0x1800016dc  mov     rdx, r14; struct IXMLDOMElement *
0x1800016df  lea     r8, aOption; "Option"
0x1800016e6  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement **
0x1800016eb  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800016f0  mov     rbx, [rbp+arg_8]
0x1800016f4  mov     edx, eax
0x1800016f6  test    eax, eax
0x1800016f8  js      short loc_180001720
0x1800016fa  test    rbx, rbx
0x1800016fd  jz      short loc_180001724
0x1800016ff  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180001703  mov     dword ptr [rsp+60h+var_40], esi; int
0x180001707  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000170b  mov     rdx, rbx; struct IXMLDOMElement *
0x18000170e  mov     rcx, r15; this
0x180001711  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x180001716  mov     rdi, [rbp+var_18]
0x18000171a  mov     edx, eax
0x18000171c  mov     rsi, [rbp+var_10]
0x180001720  test    edx, edx
0x180001722  js      short loc_18000179E
0x180001724  test    rsi, rsi
0x180001727  jz      short loc_18000179E
0x180001729  test    rdi, rdi
0x18000172c  jz      short loc_18000179E
0x18000172e  xor     ecx, ecx
0x180001730  cmp     ecx, 4
0x180001733  jnb     short loc_18000179E
0x180001735  lea     r11, [rcx+rcx*2]
0x180001739  mov     rax, rsi
0x18000173c  mov     r10, [r12+r11*8+8]
0x180001741  sub     r10, rsi
0x180001744  movzx   r8d, word ptr [rax]
0x180001748  movzx   r9d, word ptr [rax+r10]
0x18000174d  sub     r8d, r9d
0x180001750  jnz     short loc_18000175B
0x180001752  add     rax, 2
0x180001756  test    r9d, r9d
0x180001759  jnz     short loc_180001744
0x18000175b  test    r8d, r8d
0x18000175e  jnz     short loc_180001786
0x180001760  mov     r10, [r12+r11*8]
0x180001764  mov     rax, rdi
0x180001767  sub     r10, rdi
0x18000176a  movzx   r8d, word ptr [rax]
0x18000176e  movzx   r9d, word ptr [rax+r10]
0x180001773  sub     r8d, r9d
0x180001776  jnz     short loc_180001781
0x180001778  add     rax, 2
0x18000177c  test    r9d, r9d
0x18000177f  jnz     short loc_18000176A
0x180001781  test    r8d, r8d
0x180001784  jz      short loc_18000178A
0x180001786  inc     ecx
0x180001788  jmp     short loc_180001730
0x18000178a  mov     ecx, [r12+r11*8+10h]
0x18000178f  mov     rax, [rbp+arg_28]
0x180001793  mov     [rax], ecx
0x180001795  mov     rcx, [rbp+arg_30]
0x180001799  mov     eax, dword ptr [rbp+arg_38]
0x18000179c  or      [rcx], eax
0x18000179e  xor     r15d, r15d
0x1800017a1  test    edx, edx
0x1800017a3  cmovs   r15d, edx
0x1800017a7  test    rbx, rbx
0x1800017aa  jz      short loc_1800017BB
0x1800017ac  mov     rax, [rbx]
0x1800017af  mov     rcx, rbx
0x1800017b2  mov     rax, [rax+10h]
0x1800017b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017bb  test    r14, r14
0x1800017be  jz      short loc_1800017CF
0x1800017c0  mov     rax, [r14]
0x1800017c3  mov     rcx, r14
0x1800017c6  mov     rax, [rax+10h]
0x1800017ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017cf  test    rsi, rsi
0x1800017d2  jz      short loc_1800017DD
0x1800017d4  mov     rcx, rsi; bstrString
0x1800017d7  call    cs:__imp_SysFreeString
0x1800017dd  test    rdi, rdi
0x1800017e0  jz      short loc_1800017EB
0x1800017e2  mov     rcx, rdi; bstrString
0x1800017e5  call    cs:__imp_SysFreeString
0x1800017eb  lea     r11, [rsp+60h+var_s0]
0x1800017f0  mov     eax, r15d
0x1800017f3  mov     rbx, [r11+30h]
0x1800017f7  mov     rsi, [r11+40h]
0x1800017fb  mov     rsp, r11
0x1800017fe  pop     r15
0x180001800  pop     r14
0x180001802  pop     r12
0x180001804  pop     rdi
0x180001805  pop     rbp
0x180001806  retn
```
