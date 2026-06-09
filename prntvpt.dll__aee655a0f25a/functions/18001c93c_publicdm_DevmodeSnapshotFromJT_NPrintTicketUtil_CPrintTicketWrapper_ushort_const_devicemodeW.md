# publicdm::DevmodeSnapshotFromJT(NPrintTicketUtil::CPrintTicketWrapper *,ushort const *,_devicemodeW *)

- ea: `0x18001c93c`
- end: `0x18001ca1f`
- name: `?DevmodeSnapshotFromJT@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEBGPEAU_devicemodeW@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(publicdm *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, const unsigned __int16 *, struct _devicemodeW *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000856c`
- `0x18000ea40`
- `0x18001adb4`

## callees

- `0x1800022d0`
- `0x1800056e0`
- `0x180005e70`
- `0x18000a0e0`
- `0x18001c93c`
- `0x18001d878`
- `0x1800225b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9fc`

## pseudocode

```c
__int64 __fastcall publicdm::DevmodeSnapshotFromJT(
        publicdm *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        const unsigned __int16 *a3,
        struct _devicemodeW *a4)
{
  int ParameterInitializer; // edi
  int *v7; // r9
  void *v8; // rbx
  publicdm *v10; // [rsp+30h] [rbp-28h] BYREF
  struct IXMLDOMElement *v11; // [rsp+38h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 *v13; // [rsp+98h] [rbp+40h] BYREF

  v11 = 0;
  v10 = 0;
  ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(
                           this,
                           (const unsigned __int16 *)a2,
                           (const unsigned __int16 *)&stru_180029EA8,
                           &v11);
  if ( !ParameterInitializer )
  {
    pv[0] = 0;
    LODWORD(v13) = 0;
    ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(
                             this,
                             v11,
                             (unsigned __int16 **)&v10,
                             0,
                             0,
                             1);
    if ( ParameterInitializer >= 0 )
    {
      ParameterInitializer = publicdm::FromBase64String(v10, (unsigned __int16 *)pv, &v13, v7);
      if ( ParameterInitializer >= 0 )
      {
        v8 = pv[0];
        if ( pv[0] )
        {
          if ( (_DWORD)v13 == a3[34] + a3[35] && a3[33] == *((_WORD *)pv[0] + 33) )
            memcpy_0((void *)(a3 + 36), (char *)pv[0] + 72, (unsigned int)((_DWORD)v13 - 72));
          CoTaskMemFree(v8);
        }
      }
    }
  }
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v10);
  NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v11);
  return (unsigned int)ParameterInitializer;
}

```

## disassembly

```asm
0x18001c93c  push    rbp
0x18001c93e  push    rbx
0x18001c93f  push    rsi
0x18001c940  push    rdi
0x18001c941  mov     rbp, rsp
0x18001c944  sub     rsp, 58h
0x18001c948  mov     rsi, r8
0x18001c94b  mov     [rbp+var_20], 0
0x18001c953  lea     r8, stru_180029EA8; unsigned __int16 *
0x18001c95a  mov     [rbp+var_28], 0
0x18001c962  lea     r9, [rbp+var_20]; struct IXMLDOMElement **
0x18001c966  mov     rbx, rcx
0x18001c969  call    ?GetParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::GetParameterInitializer(ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c96e  mov     edi, eax
0x18001c970  test    eax, eax
0x18001c972  jnz     loc_18001CA02
0x18001c978  mov     rdx, [rbp+var_20]; struct IXMLDOMElement *
0x18001c97c  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18001c980  mov     [rsp+58h+var_30], 1; int
0x18001c988  xor     r9d, r9d; unsigned __int16 **
0x18001c98b  mov     rcx, rbx; this
0x18001c98e  mov     [rsp+58h+var_38], 0; unsigned __int16 **
0x18001c997  mov     [rbp+pv], 0
0x18001c99f  mov     dword ptr [rbp+arg_18], eax
0x18001c9a2  call    ?GetValueAsBSTR@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEAPEAG11H@Z; NPrintTicketUtil::CPrintTicketWrapper::GetValueAsBSTR(IXMLDOMElement *,ushort * *,ushort * *,ushort * *,int)
0x18001c9a7  mov     edi, eax
0x18001c9a9  test    eax, eax
0x18001c9ab  js      short loc_18001CA02
0x18001c9ad  mov     rcx, [rbp+var_28]; this
0x18001c9b1  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x18001c9b5  lea     rdx, [rbp+pv]; unsigned __int16 *
0x18001c9b9  call    ?FromBase64String@publicdm@@YAJPEAGPEAPEAEPEAH@Z; publicdm::FromBase64String(ushort *,uchar * *,int *)
0x18001c9be  mov     edi, eax
0x18001c9c0  test    eax, eax
0x18001c9c2  js      short loc_18001CA02
0x18001c9c4  mov     rbx, [rbp+pv]
0x18001c9c8  test    rbx, rbx
0x18001c9cb  jz      short loc_18001CA02
0x18001c9cd  movzx   edx, word ptr [rsi+46h]
0x18001c9d1  movzx   eax, word ptr [rsi+44h]
0x18001c9d5  mov     ecx, dword ptr [rbp+arg_18]
0x18001c9d8  add     edx, eax
0x18001c9da  cmp     ecx, edx
0x18001c9dc  jnz     short loc_18001C9F9
0x18001c9de  movzx   eax, word ptr [rbx+42h]
0x18001c9e2  cmp     [rsi+42h], ax
0x18001c9e6  jnz     short loc_18001C9F9
0x18001c9e8  lea     r8d, [rcx-48h]; Size
0x18001c9ec  lea     rcx, [rsi+48h]; void *
0x18001c9f0  lea     rdx, [rbx+48h]; Src
0x18001c9f4  call    memcpy_0
0x18001c9f9  mov     rcx, rbx; pv
0x18001c9fc  call    cs:__imp_CoTaskMemFree
0x18001ca02  lea     rcx, [rbp+var_28]
0x18001ca06  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001ca0b  lea     rcx, [rbp+var_20]
0x18001ca0f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ca14  mov     eax, edi
0x18001ca16  add     rsp, 58h
0x18001ca1a  pop     rdi
0x18001ca1b  pop     rsi
0x18001ca1c  pop     rbx
0x18001ca1d  pop     rbp
0x18001ca1e  retn
```
