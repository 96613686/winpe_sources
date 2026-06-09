# NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(IXMLDOMElement *,ushort const *,ushort const *,long *,int *)

- ea: `0x18001d7c0`
- end: `0x18001d86f`
- name: `?GetScoredPropertyAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAJPEAH@Z`
- size: `175`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil::CPrintTicketWrapper *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800200fc`
- `0x180020910`
- `0x180021070`

## callees

- `0x1800019f0`
- `0x180005e70`
- `0x18001d7c0`
- `0x18001dc8c`

## string_xrefs

- `0x18001d80c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::GetScoredPropertyAsLong(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        int *a6)
{
  int *v7; // rbx
  int ChildWithName; // eax
  int v9; // r8d
  unsigned int v10; // ebx
  struct IXMLDOMElement *v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  if ( a2 && a4 && (v7 = a6) != 0 && a5 )
  {
    *a6 = 0;
    ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(
                      this,
                      a2,
                      L"ScoredProperty",
                      a4,
                      (char *)a4,
                      L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                      &v12);
    if ( ChildWithName >= 0 && v12 )
      ChildWithName = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(this, v12, v9, a5, v7);
    v10 = 0;
    if ( ChildWithName < 0 )
      v10 = ChildWithName;
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
    return v10;
  }
  else
  {
    NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v12);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001d7c0  mov     r11, rsp
0x18001d7c3  mov     [r11+8], rbx
0x18001d7c7  mov     [r11+18h], r8
0x18001d7cb  push    rsi
0x18001d7cc  sub     rsp, 40h
0x18001d7d0  mov     qword ptr [r11+18h], 0
0x18001d7d8  mov     rsi, rcx
0x18001d7db  test    rdx, rdx
0x18001d7de  jz      short loc_18001D855
0x18001d7e0  test    r9, r9
0x18001d7e3  jz      short loc_18001D855
0x18001d7e5  mov     rbx, [rsp+48h+arg_28]
0x18001d7ea  test    rbx, rbx
0x18001d7ed  jz      short loc_18001D855
0x18001d7ef  cmp     [rsp+48h+arg_20], 0
0x18001d7f5  jz      short loc_18001D855
0x18001d7f7  lea     rax, [r11+18h]
0x18001d7fb  mov     dword ptr [rbx], 0
0x18001d801  mov     [r11-18h], rax
0x18001d805  lea     r8, aScoredproperty_0; "ScoredProperty"
0x18001d80c  lea     rax, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001d813  mov     [r11-20h], rax
0x18001d817  mov     [r11-28h], r9
0x18001d81b  call    ?GetChildWithName@CPrintTicketWrapper@NPrintTicketUtil@@AEAAJPEAUIXMLDOMElement@@PEBG111PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetChildWithName(IXMLDOMElement *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d820  test    eax, eax
0x18001d822  js      short loc_18001D840
0x18001d824  mov     rdx, [rsp+48h+arg_10]; struct IXMLDOMElement *
0x18001d829  test    rdx, rdx
0x18001d82c  jz      short loc_18001D840
0x18001d82e  mov     r9, [rsp+48h+arg_20]; int *
0x18001d833  mov     rcx, rsi; this
0x18001d836  mov     [rsp+48h+var_28], rbx; int *
0x18001d83b  call    ?GetValueAsLong@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@HPEAJPEAH@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsLong(IXMLDOMElement *,int,long *,int *)
0x18001d840  xor     ebx, ebx
0x18001d842  lea     rcx, [rsp+48h+arg_10]
0x18001d847  test    eax, eax
0x18001d849  cmovs   ebx, eax
0x18001d84c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d851  mov     eax, ebx
0x18001d853  jmp     short loc_18001D864
0x18001d855  lea     rcx, [rsp+48h+arg_10]
0x18001d85a  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001d85f  mov     eax, 80070057h
0x18001d864  mov     rbx, [rsp+48h+arg_0]
0x18001d869  add     rsp, 40h
0x18001d86d  pop     rsi
0x18001d86e  retn
```
