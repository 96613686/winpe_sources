# publicdm::CollatePrintTicketToDevmode(publicdm::CConversionInfo &)

- ea: `0x180001810`
- end: `0x1800019e4`
- name: `?CollatePrintTicketToDevmode@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `468`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ea4c`

## callees

- `0x180001810`
- `0x1800019f0`
- `0x180002084`
- `0x180004b00`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001996`
- `OLEAUT32!__imp_SysFreeString` at `0x1800019a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180001996`
- `OLEAUT32!__imp_SysFreeString` at `0x1800019a4`

## string_xrefs

- `0x18000183a`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall publicdm::CollatePrintTicketToDevmode(
        publicdm *this,
        struct publicdm::CConversionInfo *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  NPrintTicketUtil::CPrintTicketWrapper *v5; // rcx
  const OLECHAR *v6; // r15
  struct IXMLDOMElement *v7; // rdi
  struct IXMLDOMElement *v8; // rdx
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rsi
  int ChildWithName; // eax
  NPrintTicketUtil::CPrintTicketWrapper *v12; // rcx
  struct IXMLDOMElement *v13; // r14
  int v14; // r9d
  int ChildWithoutName; // eax
  int NameAttribute; // eax
  int v17; // ecx
  int v18; // eax
  const unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // ecx
  const unsigned __int16 *v22; // rax
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // r15d
  struct IXMLDOMElement *v27; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v28; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int16 *v29; // [rsp+90h] [rbp+50h] BYREF
  struct IXMLDOMElement *v30; // [rsp+98h] [rbp+58h] BYREF

  v30 = 0;
  v5 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
  v6 = L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords";
  v7 = 0;
  v8 = (struct IXMLDOMElement *)*((_QWORD *)v5 + 3);
  v9 = 0;
  v27 = 0;
  v10 = 0;
  v28 = 0;
  v29 = 0;
  ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                    v5,
                    v8,
                    L"Feature",
                    a4,
                    (char *)L"DocumentCollate",
                    L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                    &v30);
  v13 = v30;
  v14 = ChildWithName;
  if ( ChildWithName >= 0 )
  {
    if ( !v30
      || (ChildWithoutName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(
                               v12,
                               v30,
                               (char *)L"Option",
                               (const unsigned __int16 *)(unsigned int)ChildWithName,
                               &v27),
          v7 = v27,
          v14 = ChildWithoutName,
          ChildWithoutName >= 0) )
    {
      if ( !v7
        || (NameAttribute = NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(
                              *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                              v7,
                              &v29,
                              &v28,
                              0),
            v9 = v28,
            v14 = NameAttribute,
            v10 = v29,
            NameAttribute >= 0) )
      {
        if ( v9 && v10 )
        {
          do
          {
            v17 = *(const OLECHAR *)((char *)v6
                                   + (char *)v10
                                   - (char *)L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords");
            v18 = *v6 - v17;
            if ( v18 )
              break;
            ++v6;
          }
          while ( v17 );
          if ( !v18 )
          {
            v19 = L"Collated";
            do
            {
              v20 = *(const unsigned __int16 *)((char *)v19 + (char *)v9 - (char *)L"Collated");
              v21 = *v19 - v20;
              if ( v21 )
                break;
              ++v19;
            }
            while ( v20 );
            if ( v21 )
            {
              v22 = L"Uncollated";
              do
              {
                v23 = *(const unsigned __int16 *)((char *)v22 + (char *)v9 - (char *)L"Uncollated");
                v24 = *v22 - v23;
                if ( v24 )
                  break;
                ++v22;
              }
              while ( v23 );
              if ( !v24 )
              {
                *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x8000u;
                *(_WORD *)(*((_QWORD *)this + 2) + 100LL) = 0;
              }
            }
            else
            {
              *(_DWORD *)(*((_QWORD *)this + 2) + 72LL) |= 0x8000u;
              *(_WORD *)(*((_QWORD *)this + 2) + 100LL) = 1;
            }
          }
        }
      }
    }
  }
  v25 = 0;
  if ( v14 < 0 )
    v25 = v14;
  if ( v10 )
    SysFreeString(v10);
  if ( v9 )
    SysFreeString(v9);
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v7->lpVtbl->Release)(v7);
  if ( v13 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v13->lpVtbl->Release)(v13);
  return v25;
}

```

## disassembly

```asm
0x180001810  push    rbp
0x180001812  push    rbx
0x180001813  push    rsi
0x180001814  push    rdi
0x180001815  push    r13
0x180001817  push    r14
0x180001819  push    r15
0x18000181b  mov     rbp, rsp
0x18000181e  sub     rsp, 40h
0x180001822  mov     r13, rcx
0x180001825  mov     [rbp+arg_18], 0
0x18000182d  mov     rcx, [rcx+60h]; this
0x180001831  lea     rax, [rbp+arg_18]
0x180001835  mov     [rsp+40h+var_10], rax; struct IXMLDOMElement **
0x18000183a  lea     r15, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180001841  lea     rax, aDocumentcollat; "DocumentCollate"
0x180001848  mov     [rsp+40h+var_18], r15; unsigned __int16 *
0x18000184d  xor     edi, edi
0x18000184f  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180001854  mov     rdx, [rcx+18h]; struct IXMLDOMElement *
0x180001858  lea     r8, aFeature; "Feature"
0x18000185f  xor     ebx, ebx
0x180001861  mov     [rbp+arg_0], rdi
0x180001865  xor     esi, esi
0x180001867  mov     [rbp+arg_8], rbx
0x18000186b  mov     [rbp+arg_10], rsi
0x18000186f  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180001874  mov     r14, [rbp+arg_18]
0x180001878  mov     r9d, eax; unsigned __int16 *
0x18000187b  test    eax, eax
0x18000187d  js      loc_180001984
0x180001883  test    r14, r14
0x180001886  jz      short loc_1800018AF
0x180001888  lea     rax, [rbp+arg_0]
0x18000188c  mov     rdx, r14; struct IXMLDOMElement *
0x18000188f  lea     r8, aOption; "Option"
0x180001896  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x18000189b  call    ?GetChildWithoutName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithoutName(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800018a0  mov     rdi, [rbp+arg_0]
0x1800018a4  mov     r9d, eax
0x1800018a7  test    eax, eax
0x1800018a9  js      loc_180001984
0x1800018af  test    rdi, rdi
0x1800018b2  jz      short loc_1800018DF
0x1800018b4  mov     rcx, [r13+60h]; this
0x1800018b8  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x1800018bc  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x1800018c0  mov     dword ptr [rsp+40h+var_20], ebx; int
0x1800018c4  mov     rdx, rdi; struct IXMLDOMElement *
0x1800018c7  call    ?GetNameAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG1H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetNameAttribute(IXMLDOMElement *,ushort * *,ushort * *,int)
0x1800018cc  mov     rbx, [rbp+arg_8]
0x1800018d0  mov     r9d, eax
0x1800018d3  mov     rsi, [rbp+arg_10]
0x1800018d7  test    eax, eax
0x1800018d9  js      loc_180001984
0x1800018df  test    rbx, rbx
0x1800018e2  jz      loc_180001984
0x1800018e8  test    rsi, rsi
0x1800018eb  jz      loc_180001984
0x1800018f1  mov     rdx, rsi
0x1800018f4  sub     rdx, r15
0x1800018f7  movzx   eax, word ptr [r15]
0x1800018fb  movzx   ecx, word ptr [r15+rdx]
0x180001900  sub     eax, ecx
0x180001902  jnz     short loc_18000190C
0x180001904  add     r15, 2
0x180001908  test    ecx, ecx
0x18000190a  jnz     short loc_1800018F7
0x18000190c  test    eax, eax
0x18000190e  jnz     short loc_180001984
0x180001910  lea     rax, aCollated; "Collated"
0x180001917  mov     rdx, rbx
0x18000191a  sub     rdx, rax
0x18000191d  movzx   ecx, word ptr [rax]
0x180001920  movzx   r8d, word ptr [rax+rdx]
0x180001925  sub     ecx, r8d
0x180001928  jnz     short loc_180001933
0x18000192a  add     rax, 2
0x18000192e  test    r8d, r8d
0x180001931  jnz     short loc_18000191D
0x180001933  test    ecx, ecx
0x180001935  jnz     short loc_18000194C
0x180001937  mov     rax, [r13+10h]
0x18000193b  bts     dword ptr [rax+48h], 0Fh
0x180001940  mov     rax, [r13+10h]
0x180001944  mov     word ptr [rax+64h], 1
0x18000194a  jmp     short loc_180001984
0x18000194c  lea     rax, aUncollated; "Uncollated"
0x180001953  mov     r8, rbx
0x180001956  sub     r8, rax
0x180001959  movzx   ecx, word ptr [rax]
0x18000195c  movzx   edx, word ptr [rax+r8]
0x180001961  sub     ecx, edx
0x180001963  jnz     short loc_18000196D
0x180001965  add     rax, 2
0x180001969  test    edx, edx
0x18000196b  jnz     short loc_180001959
0x18000196d  test    ecx, ecx
0x18000196f  jnz     short loc_180001984
0x180001971  mov     rax, [r13+10h]
0x180001975  bts     dword ptr [rax+48h], 0Fh
0x18000197a  mov     rcx, [r13+10h]
0x18000197e  xor     eax, eax
0x180001980  mov     [rcx+64h], ax
0x180001984  xor     r15d, r15d
0x180001987  test    r9d, r9d
0x18000198a  cmovs   r15d, r9d
0x18000198e  test    rsi, rsi
0x180001991  jz      short loc_18000199C
0x180001993  mov     rcx, rsi; bstrString
0x180001996  call    cs:__imp_SysFreeString
0x18000199c  test    rbx, rbx
0x18000199f  jz      short loc_1800019AA
0x1800019a1  mov     rcx, rbx; bstrString
0x1800019a4  call    cs:__imp_SysFreeString
0x1800019aa  test    rdi, rdi
0x1800019ad  jz      short loc_1800019BE
0x1800019af  mov     rax, [rdi]
0x1800019b2  mov     rcx, rdi
0x1800019b5  mov     rax, [rax+10h]
0x1800019b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019be  test    r14, r14
0x1800019c1  jz      short loc_1800019D2
0x1800019c3  mov     rdx, [r14]
0x1800019c6  mov     rcx, r14
0x1800019c9  mov     rax, [rdx+10h]
0x1800019cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019d2  mov     eax, r15d
0x1800019d5  add     rsp, 40h
0x1800019d9  pop     r15
0x1800019db  pop     r14
0x1800019dd  pop     r13
0x1800019df  pop     rdi
0x1800019e0  pop     rsi
0x1800019e1  pop     rbx
0x1800019e2  pop     rbp
0x1800019e3  retn
```
