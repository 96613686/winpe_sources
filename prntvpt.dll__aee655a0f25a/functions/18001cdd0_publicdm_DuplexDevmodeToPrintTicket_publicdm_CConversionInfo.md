# publicdm::DuplexDevmodeToPrintTicket(publicdm::CConversionInfo &)

- ea: `0x18001cdd0`
- end: `0x18001cec9`
- name: `?DuplexDevmodeToPrintTicket@publicdm@@YAJAEAVCConversionInfo@1@@Z`
- size: `249`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct publicdm::CConversionInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180006c74`
- `0x18000e084`
- `0x18001cdd0`
- `0x180023010`

## string_xrefs

- `0x18001ce71`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001ce8f`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001ce46`: `OneSided`

## pseudocode

```c
__int64 __fastcall publicdm::DuplexDevmodeToPrintTicket(publicdm *this, struct publicdm::CConversionInfo *a2)
{
  __int64 v2; // rdx
  int Option; // edi
  int i; // ecx
  const unsigned __int16 *v6; // rsi
  __int64 v7; // rax
  NPrintTicketUtil::CPrintTicketWrapper *v8; // rcx
  struct IXMLDOMElement *v10; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 2);
  Option = 0;
  if ( (*(_DWORD *)(v2 + 72) & 0x1000) != 0 )
  {
    for ( i = 0; ; ++i )
    {
      v6 = (const unsigned __int16 *)qword_1800254C0[3 * i + 1];
      if ( !v6 )
        break;
      if ( LOWORD(qword_1800254C0[3 * i]) == *(_WORD *)(v2 + 94) )
        goto LABEL_9;
    }
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(publicdm *))(*(_QWORD *)this + 16LL))(this);
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 16LL))(v7, *((_QWORD *)this + 2))
      && !*((_DWORD *)this + 16) )
    {
      v6 = L"OneSided";
LABEL_9:
      v10 = 0;
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v10);
      v8 = (NPrintTicketUtil::CPrintTicketWrapper *)*((_QWORD *)this + 12);
      v10 = 0;
      Option = NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(
                 v8,
                 0,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"JobDuplexAllDocumentsContiguously",
                 &v10);
      if ( Option >= 0 )
        Option = NPrintTicketUtil::CPrintTicketWrapper::CreateOption(
                   *((NPrintTicketUtil::CPrintTicketWrapper **)this + 12),
                   v10,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   v6,
                   0);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v10);
    }
  }
  return (unsigned int)Option;
}

```

## disassembly

```asm
0x18001cdd0  mov     [rsp+arg_8], rbx
0x18001cdd5  mov     [rsp+arg_10], rsi
0x18001cdda  push    rdi
0x18001cddb  sub     rsp, 30h
0x18001cddf  mov     rdx, [rcx+10h]
0x18001cde3  xor     edi, edi
0x18001cde5  mov     rbx, rcx
0x18001cde8  test    dword ptr [rdx+48h], 1000h
0x18001cdef  jz      short loc_18001CE1E
0x18001cdf1  xor     ecx, ecx
0x18001cdf3  lea     r9, qword_1800254C0
0x18001cdfa  movsxd  rax, ecx
0x18001cdfd  lea     r8, [rax+rax*2]
0x18001ce01  mov     rsi, [r9+r8*8+8]
0x18001ce06  test    rsi, rsi
0x18001ce09  jz      loc_18001CEB7
0x18001ce0f  movzx   eax, word ptr [rdx+5Eh]
0x18001ce13  cmp     [r9+r8*8], ax
0x18001ce18  jz      short loc_18001CE4D
0x18001ce1a  inc     ecx
0x18001ce1c  jmp     short loc_18001CDFA
0x18001ce1e  mov     rax, [rcx]
0x18001ce21  mov     rax, [rax+10h]
0x18001ce25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce2a  mov     rdx, [rbx+10h]
0x18001ce2e  mov     rcx, rax
0x18001ce31  mov     rax, [rax]
0x18001ce34  mov     rax, [rax+10h]
0x18001ce38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce3d  test    eax, eax
0x18001ce3f  jz      short loc_18001CEB7
0x18001ce41  cmp     [rbx+40h], edi
0x18001ce44  jnz     short loc_18001CEB7
0x18001ce46  lea     rsi, aOnesided; "OneSided"
0x18001ce4d  lea     rcx, [rsp+38h+arg_0]
0x18001ce52  mov     [rsp+38h+arg_0], rdi
0x18001ce57  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ce5c  mov     rcx, [rbx+60h]; this
0x18001ce60  lea     rax, [rsp+38h+arg_0]
0x18001ce65  lea     r9, aJobduplexalldo; "JobDuplexAllDocumentsContiguously"
0x18001ce6c  mov     [rsp+38h+var_18], rax; struct IXMLDOMElement **
0x18001ce71  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001ce78  mov     [rsp+38h+arg_0], rdi
0x18001ce7d  xor     edx, edx; struct IXMLDOMElement *
0x18001ce7f  call    ?CreateFeature@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateFeature(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ce84  mov     edi, eax
0x18001ce86  test    eax, eax
0x18001ce88  js      short loc_18001CEAD
0x18001ce8a  mov     rdx, [rsp+38h+arg_0]; struct IXMLDOMElement *
0x18001ce8f  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001ce96  mov     rcx, [rbx+60h]; this
0x18001ce9a  mov     r9, rsi; unsigned __int16 *
0x18001ce9d  mov     [rsp+38h+var_18], 0; struct IXMLDOMElement **
0x18001cea6  call    ?CreateOption@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateOption(IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001ceab  mov     edi, eax
0x18001cead  lea     rcx, [rsp+38h+arg_0]
0x18001ceb2  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ceb7  mov     rbx, [rsp+38h+arg_8]
0x18001cebc  mov     eax, edi
0x18001cebe  mov     rsi, [rsp+38h+arg_10]
0x18001cec3  add     rsp, 30h
0x18001cec7  pop     rdi
0x18001cec8  retn
```
