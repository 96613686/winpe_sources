# CSyncMLCmd::CreateStatusForItem(IXmlWriter *,CSyncMLItem *,int,long)

- ea: `0x18001fee0`
- end: `0x18002010e`
- name: `?CreateStatusForItem@CSyncMLCmd@@IEBAJPEAUIXmlWriter@@PEAVCSyncMLItem@@HJ@Z`
- size: `558`
- prototype: `__int64 __usercall@<rax>(CSyncMLCmd *__hidden this@<rcx>, struct IXmlWriter *@<rdx>, struct CSyncMLItem *@<r8>, int@<r9d>, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e490`

## callees

- `0x180002590`
- `0x180002a00`
- `0x1800034d0`
- `0x1800035b0`
- `0x1800038a0`
- `0x180003b60`
- `0x180003cd0`
- `0x180011a68`
- `0x18001fee0`
- `0x18002085c`
- `0x180020ef4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180020089`
- `OLEAUT32!__imp_SysFreeString` at `0x180020099`
- `OLEAUT32!__imp_SysFreeString` at `0x180020089`
- `OLEAUT32!__imp_SysFreeString` at `0x180020099`

## pseudocode

```c
__int64 __fastcall CSyncMLCmd::CreateStatusForItem(
        const unsigned __int16 **this,
        struct IXmlWriter *a2,
        struct CSyncMLItem *a3,
        unsigned int a4,
        unsigned int a5)
{
  struct IConfigManager2URI *TargetLocURI; // rsi
  struct IConfigManager2URI *SourceLocURI; // rax
  struct IConfigManager2URI *v10; // rdi
  int OriginalQueryPath; // ebx
  CSyncMLCmd *v12; // rcx
  CSyncMLCmd *v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int OmadmStatusCode; // eax
  bool v17; // zf
  const unsigned __int16 *v18; // r13
  unsigned int v19; // r15d
  int v20; // r12d
  const unsigned __int16 *ElementName; // rax
  unsigned int v22; // r8d
  __int64 v23; // r8
  __int64 v24; // r9
  int ItemPreExecHresult; // [rsp+60h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-9h] BYREF
  BSTR v28[10]; // [rsp+70h] [rbp-1h] BYREF

  bstrString = 0;
  v28[0] = 0;
  TargetLocURI = CSyncMLItem::GetTargetLocURI(a3);
  SourceLocURI = CSyncMLItem::GetSourceLocURI(a3);
  v10 = SourceLocURI;
  if ( !TargetLocURI )
  {
    OriginalQueryPath = -2147024809;
    goto LABEL_23;
  }
  OriginalQueryPath = 0;
  if ( !SourceLocURI )
    goto LABEL_13;
  if ( CSyncMLCmd::IsBackCompactWmiQuery((CSyncMLCmd *)this, SourceLocURI) )
    OriginalQueryPath = CSyncMLCmd::GetOriginalQueryPath(v12, v10, &bstrString);
  if ( !bstrString )
    OriginalQueryPath = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v10 + 64LL))(
                          v10,
                          0,
                          0,
                          &bstrString);
  if ( OriginalQueryPath >= 0 )
  {
LABEL_13:
    if ( CSyncMLCmd::IsBackCompactWmiQuery((CSyncMLCmd *)this, TargetLocURI) )
      OriginalQueryPath = CSyncMLCmd::GetOriginalQueryPath(v13, TargetLocURI, v28);
    if ( !v28[0] )
      OriginalQueryPath = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)TargetLocURI + 64LL))(
                            TargetLocURI,
                            0,
                            0,
                            v28);
    if ( OriginalQueryPath >= 0 )
    {
      ItemPreExecHresult = CSyncMLItem::GetItemPreExecHresult(a3);
      v15 = ItemPreExecHresult;
      if ( ItemPreExecHresult >= 0 )
      {
        OriginalQueryPath = CSyncMLItem::GetItemExecHresult(v14, &ItemPreExecHresult);
        if ( OriginalQueryPath < 0 )
          goto LABEL_23;
        v15 = ItemPreExecHresult;
      }
      OmadmStatusCode = GetOmadmStatusCode(v15, *((unsigned int *)this + 23), a4, a5);
      v17 = a4 == 0;
      v18 = v28[0];
      v19 = OmadmStatusCode;
      if ( !v17 )
        v15 = a5;
      v20 = *((_DWORD *)this[10] + 11);
      if ( *((_DWORD *)this + 23) == 73 )
        ElementName = this[14];
      else
        ElementName = (const unsigned __int16 *)GetElementName(*((unsigned int *)this + 23));
      v22 = CSyncMLDPU::s_dwCurrClientCmdID++;
      OriginalQueryPath = AddStatus(
                            a2,
                            v19,
                            v22,
                            CSyncMLDPU::s_dwCurrServerMsgID,
                            this[13],
                            ElementName,
                            bstrString,
                            v18,
                            0,
                            0,
                            v15,
                            v20);
    }
  }
LABEL_23:
  SysFreeString(bstrString);
  SysFreeString(v28[0]);
  if ( TargetLocURI )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)TargetLocURI + 16LL))(TargetLocURI);
  if ( v10 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    ItemPreExecHresult = OriginalQueryPath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_180036991,
      v23,
      v24,
      (__int64)&ItemPreExecHresult);
  }
  return (unsigned int)OriginalQueryPath;
}

```

## disassembly

```asm
0x18001fee0  mov     [rsp-8+arg_8], rdx
0x18001fee5  push    rbp
0x18001fee6  push    rbx
0x18001fee7  push    rsi
0x18001fee8  push    rdi
0x18001fee9  push    r12
0x18001feeb  push    r13
0x18001feed  push    r14
0x18001feef  push    r15
0x18001fef1  lea     rbp, [rsp-17h]
0x18001fef6  sub     rsp, 88h
0x18001fefd  mov     r14, rcx
0x18001ff00  xor     r12d, r12d
0x18001ff03  mov     rcx, r8; this
0x18001ff06  mov     [rbp+4Fh+bstrString], r12
0x18001ff0a  mov     [rbp+4Fh+var_50], r12
0x18001ff0e  mov     r13d, r9d
0x18001ff11  mov     r15, r8
0x18001ff14  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18001ff19  mov     rcx, r15; this
0x18001ff1c  mov     rsi, rax
0x18001ff1f  call    ?GetSourceLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetSourceLocURI(void)
0x18001ff24  mov     rdi, rax
0x18001ff27  test    rsi, rsi
0x18001ff2a  jnz     short loc_18001FF36
0x18001ff2c  mov     ebx, 80070057h
0x18001ff31  jmp     loc_180020085
0x18001ff36  mov     ebx, r12d
0x18001ff39  test    rdi, rdi
0x18001ff3c  jz      short loc_18001FF83
0x18001ff3e  mov     rdx, rdi; struct IConfigManager2URI *
0x18001ff41  mov     rcx, r14; this
0x18001ff44  call    ?IsBackCompactWmiQuery@CSyncMLCmd@@IEBAHPEAUIConfigManager2URI@@@Z; CSyncMLCmd::IsBackCompactWmiQuery(IConfigManager2URI *)
0x18001ff49  test    eax, eax
0x18001ff4b  jz      short loc_18001FF5B
0x18001ff4d  lea     r8, [rbp+4Fh+bstrString]; unsigned __int16 **
0x18001ff51  mov     rdx, rdi; struct IConfigManager2URI *
0x18001ff54  call    ?GetOriginalQueryPath@CSyncMLCmd@@IEBAJPEAUIConfigManager2URI@@PEAPEAG@Z; CSyncMLCmd::GetOriginalQueryPath(IConfigManager2URI *,ushort * *)
0x18001ff59  mov     ebx, eax
0x18001ff5b  cmp     [rbp+4Fh+bstrString], r12
0x18001ff5f  jnz     short loc_18001FF7B
0x18001ff61  mov     rax, [rdi]
0x18001ff64  lea     r9, [rbp+4Fh+bstrString]
0x18001ff68  xor     r8d, r8d
0x18001ff6b  xor     edx, edx
0x18001ff6d  mov     rcx, rdi
0x18001ff70  mov     rax, [rax+40h]
0x18001ff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff79  mov     ebx, eax
0x18001ff7b  test    ebx, ebx
0x18001ff7d  js      loc_180020085
0x18001ff83  mov     rdx, rsi; struct IConfigManager2URI *
0x18001ff86  mov     rcx, r14; this
0x18001ff89  call    ?IsBackCompactWmiQuery@CSyncMLCmd@@IEBAHPEAUIConfigManager2URI@@@Z; CSyncMLCmd::IsBackCompactWmiQuery(IConfigManager2URI *)
0x18001ff8e  test    eax, eax
0x18001ff90  jz      short loc_18001FFA0
0x18001ff92  lea     r8, [rbp+4Fh+var_50]; unsigned __int16 **
0x18001ff96  mov     rdx, rsi; struct IConfigManager2URI *
0x18001ff99  call    ?GetOriginalQueryPath@CSyncMLCmd@@IEBAJPEAUIConfigManager2URI@@PEAPEAG@Z; CSyncMLCmd::GetOriginalQueryPath(IConfigManager2URI *,ushort * *)
0x18001ff9e  mov     ebx, eax
0x18001ffa0  cmp     [rbp+4Fh+var_50], r12
0x18001ffa4  jnz     short loc_18001FFC0
0x18001ffa6  mov     rax, [rsi]
0x18001ffa9  lea     r9, [rbp+4Fh+var_50]
0x18001ffad  xor     r8d, r8d
0x18001ffb0  xor     edx, edx
0x18001ffb2  mov     rcx, rsi
0x18001ffb5  mov     rax, [rax+40h]
0x18001ffb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffbe  mov     ebx, eax
0x18001ffc0  test    ebx, ebx
0x18001ffc2  js      loc_180020085
0x18001ffc8  mov     rcx, r15; this
0x18001ffcb  call    ?GetItemPreExecHresult@CSyncMLItem@@QEBAJXZ; CSyncMLItem::GetItemPreExecHresult(void)
0x18001ffd0  mov     [rbp+4Fh+var_60], eax
0x18001ffd3  mov     ebx, eax
0x18001ffd5  test    eax, eax
0x18001ffd7  js      short loc_18001FFEF
0x18001ffd9  lea     rdx, [rbp+4Fh+var_60]; int *
0x18001ffdd  call    ?GetItemExecHresult@CSyncMLItem@@QEAAJPEAJ@Z; CSyncMLItem::GetItemExecHresult(long *)
0x18001ffe2  mov     ebx, eax
0x18001ffe4  test    eax, eax
0x18001ffe6  js      loc_180020085
0x18001ffec  mov     ebx, [rbp+4Fh+var_60]
0x18001ffef  mov     r9d, [rbp+4Fh+arg_20]
0x18001fff3  mov     r8d, r13d
0x18001fff6  mov     edx, [r14+5Ch]
0x18001fffa  mov     ecx, ebx
0x18001fffc  call    GetOmadmStatusCode
0x180020001  mov     rcx, [r14+50h]
0x180020005  test    r13d, r13d
0x180020008  mov     r13, [rbp+4Fh+var_50]
0x18002000c  mov     r15d, eax
0x18002000f  cmovnz  ebx, [rbp+4Fh+arg_20]
0x180020013  cmp     dword ptr [r14+5Ch], 49h ; 'I'
0x180020018  mov     r12d, [rcx+2Ch]
0x18002001c  jnz     short loc_180020024
0x18002001e  mov     rax, [r14+70h]
0x180020022  jmp     short loc_18002002D
0x180020024  mov     ecx, [r14+5Ch]
0x180020028  call    GetElementName
0x18002002d  mov     r8d, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; unsigned int
0x180020034  mov     edx, r15d; unsigned int
0x180020037  mov     r9d, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; unsigned int
0x18002003e  mov     [rsp+0C0h+var_68], r12d; int
0x180020043  xor     r12d, r12d
0x180020046  mov     [rsp+0C0h+var_70], ebx; int
0x18002004a  mov     [rsp+0C0h+var_78], r12d; unsigned int
0x18002004f  lea     ecx, [r8+1]
0x180020053  mov     [rsp+0C0h+var_80], r12; struct CSyncMLItem **
0x180020058  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, ecx; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x18002005e  mov     rcx, [rbp+4Fh+bstrString]
0x180020062  mov     [rsp+0C0h+var_88], r13; unsigned __int16 *
0x180020067  mov     [rsp+0C0h+var_90], rcx; unsigned __int16 *
0x18002006c  mov     rcx, [rbp+4Fh+arg_8]; struct IXmlWriter *
0x180020070  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x180020075  mov     rax, [r14+68h]
0x180020079  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18002007e  call    ?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z; AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)
0x180020083  mov     ebx, eax
0x180020085  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180020089  call    cs:__imp_SysFreeString
0x180020090  nop     dword ptr [rax+rax+00h]
0x180020095  mov     rcx, [rbp+4Fh+var_50]; bstrString
0x180020099  call    cs:__imp_SysFreeString
0x1800200a0  nop     dword ptr [rax+rax+00h]
0x1800200a5  test    rsi, rsi
0x1800200a8  jz      short loc_1800200B9
0x1800200aa  mov     rax, [rsi]
0x1800200ad  mov     rcx, rsi
0x1800200b0  mov     rax, [rax+10h]
0x1800200b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200b9  test    rdi, rdi
0x1800200bc  jz      short loc_1800200CD
0x1800200be  mov     rax, [rdi]
0x1800200c1  mov     rcx, rdi
0x1800200c4  mov     rax, [rax+10h]
0x1800200c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200cd  mov     eax, cs:dword_18003E048
0x1800200d3  cmp     eax, 5
0x1800200d6  jbe     short loc_1800200F7
0x1800200d8  lea     rax, [rbp+4Fh+var_60]
0x1800200dc  mov     [rbp+4Fh+var_60], ebx
0x1800200df  lea     rdx, byte_180036991
0x1800200e6  mov     [rsp+0C0h+var_A0], rax
0x1800200eb  lea     rcx, dword_18003E048
0x1800200f2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800200f7  mov     eax, ebx
0x1800200f9  add     rsp, 88h
0x180020100  pop     r15
0x180020102  pop     r14
0x180020104  pop     r13
0x180020106  pop     r12
0x180020108  pop     rdi
0x180020109  pop     rsi
0x18002010a  pop     rbx
0x18002010b  pop     rbp
0x18002010c  retn
```
