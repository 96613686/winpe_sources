# LogServerTransaction(ushort const * const,TRANSACTION_TYPE,int)

- ea: `0x18002bcdc`
- end: `0x18002be37`
- name: `?LogServerTransaction@@YAJQEBGW4TRANSACTION_TYPE@@H@Z`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f1c4`
- `0x18002f6bc`

## callees

- `0x180019ec0`
- `0x18002ba18`
- `0x18002bcdc`
- `0x18002e7dc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bd8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bd8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bd7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be17`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bd7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be17`

## string_xrefs

- `0x18002bd3d`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:p='http://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy' xmlns:s='http://www.w3.org/2003/05/soap-envelope' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' `
- `0x18002bd30`: `/s:Envelope/s:Header/wsse:Security | /s:Envelope/s:Body/wst:RequestSecurityToken/wsse:BinarySecurityToken`
- `0x18002bd29`: `/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LogServerTransaction(OLECHAR *a1, int a2, int a3)
{
  BSTR v4; // rdi
  int inited; // ebx
  const unsigned __int16 *v6; // rdx
  struct IXMLDOMDocument2 *v7; // r14
  HRESULT (__stdcall *get_xml)(IXMLDOMDocument2 *, BSTR *); // r15
  OLECHAR *v9; // rbp
  DWORD LastError; // ebx
  __int64 *v11; // rdx
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMDocument2 *v14; // [rsp+68h] [rbp+20h] BYREF

  v4 = a1;
  bstrString = 0;
  if ( !a3 || (inited = 0, a2 != 1) )
  {
    v14 = 0;
    inited = InitXMLDOMDoc(a1, 0, (LPVOID *)&v14);
    if ( inited >= 0 )
    {
      v6 = L"/s:Envelope/s:Header/wsse:Security | /s:Envelope/s:Body/wst:RequestSecurityToken/wsse:BinarySecurityToken";
      if ( a2 )
        v6 = L"/s:Envelope/s:Body/wst:RequestSecurityTokenResponseCollection/wst:RequestSecurityTokenResponse/wst:RequestedSecurityToken";
      inited = CMachineEnroller::RemoveProvXMLNode(
                 v14,
                 v6,
                 L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss"
                  "/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xm"
                  "lns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:p='ht"
                  "tp://schemas.microsoft.com/windows/pki/2009/01/enrollmentpolicy' xmlns:s='http://www.w3.org/2003/05/so"
                  "ap-envelope' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' ");
      if ( inited >= 0 )
      {
        v7 = v14;
        get_xml = v14->lpVtbl->get_xml;
        v9 = bstrString;
        if ( bstrString )
        {
          LastError = GetLastError();
          SysFreeString(v9);
          SetLastError(LastError);
        }
        bstrString = 0;
        inited = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR *))get_xml)(v7, &bstrString);
        if ( inited >= 0 )
          v4 = bstrString;
      }
    }
    if ( v14 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->Release)(v14);
    if ( !a2 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) == 0 )
        goto LABEL_20;
      v11 = SoapRequestMessage;
      goto LABEL_19;
    }
    if ( a2 != 1 )
      goto LABEL_20;
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) == 0 )
    goto LABEL_20;
  v11 = SoapResponseMessage;
LABEL_19:
  McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, v11, v4);
LABEL_20:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002bcdc  mov     [rsp+arg_8], rbx
0x18002bce1  push    rbp
0x18002bce2  push    rsi
0x18002bce3  push    rdi
0x18002bce4  push    r14
0x18002bce6  push    r15
0x18002bce8  sub     rsp, 20h
0x18002bcec  mov     esi, edx
0x18002bcee  mov     rdi, rcx
0x18002bcf1  mov     [rsp+48h+bstrString], 0
0x18002bcfa  test    r8d, r8d
0x18002bcfd  jz      short loc_18002BD0A
0x18002bcff  xor     ebx, ebx
0x18002bd01  cmp     edx, 1
0x18002bd04  jz      loc_18002BDED
0x18002bd0a  mov     [rsp+48h+arg_18], 0
0x18002bd13  lea     r8, [rsp+48h+arg_18]; ppv
0x18002bd18  xor     edx, edx; OLECHAR *
0x18002bd1a  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x18002bd1f  mov     ebx, eax
0x18002bd21  test    eax, eax
0x18002bd23  js      loc_18002BDBB
0x18002bd29  lea     rax, aSEnvelopeSBody; "/s:Envelope/s:Body/wst:RequestSecurityT"...
0x18002bd30  lea     rdx, aSEnvelopeSHead; "/s:Envelope/s:Header/wsse:Security | /s"...
0x18002bd37  test    esi, esi
0x18002bd39  cmovnz  rdx, rax; unsigned __int16 *
0x18002bd3d  lea     r8, aXmlnsWstHttpDo_0; "xmlns:wst='http://docs.oasis-open.org/w"...
0x18002bd44  mov     rcx, [rsp+48h+arg_18]; struct IXMLDOMDocument2 *
0x18002bd49  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x18002bd4e  mov     ebx, eax
0x18002bd50  test    eax, eax
0x18002bd52  js      short loc_18002BDBB
0x18002bd54  mov     r14, [rsp+48h+arg_18]
0x18002bd59  mov     rax, [r14]
0x18002bd5c  mov     r15, [rax+110h]
0x18002bd63  mov     rbp, [rsp+48h+bstrString]
0x18002bd68  test    rbp, rbp
0x18002bd6b  jz      short loc_18002BD98
0x18002bd6d  call    cs:__imp_GetLastError
0x18002bd74  nop     dword ptr [rax+rax+00h]
0x18002bd79  mov     ebx, eax
0x18002bd7b  mov     rcx, rbp; bstrString
0x18002bd7e  call    cs:__imp_SysFreeString
0x18002bd85  nop     dword ptr [rax+rax+00h]
0x18002bd8a  mov     ecx, ebx; dwErrCode
0x18002bd8c  call    cs:__imp_SetLastError
0x18002bd93  nop     dword ptr [rax+rax+00h]
0x18002bd98  mov     [rsp+48h+bstrString], 0
0x18002bda1  lea     rdx, [rsp+48h+bstrString]
0x18002bda6  mov     rcx, r14
0x18002bda9  mov     rax, r15
0x18002bdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdb1  mov     ebx, eax
0x18002bdb3  test    eax, eax
0x18002bdb5  cmovns  rdi, [rsp+48h+bstrString]
0x18002bdbb  mov     rcx, [rsp+48h+arg_18]
0x18002bdc0  test    rcx, rcx
0x18002bdc3  jz      short loc_18002BDD2
0x18002bdc5  mov     rax, [rcx]
0x18002bdc8  mov     rax, [rax+10h]
0x18002bdcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdd1  nop
0x18002bdd2  test    esi, esi
0x18002bdd4  jnz     short loc_18002BDE8
0x18002bdd6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002bddd  jz      short loc_18002BE0D
0x18002bddf  lea     rdx, SoapRequestMessage
0x18002bde6  jmp     short loc_18002BDFD
0x18002bde8  cmp     esi, 1
0x18002bdeb  jnz     short loc_18002BE0D
0x18002bded  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18002bdf4  jz      short loc_18002BE0D
0x18002bdf6  lea     rdx, SoapResponseMessage
0x18002bdfd  mov     r8, rdi
0x18002be00  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002be07  call    McTemplateU0z_EventWriteTransfer
0x18002be0c  nop
0x18002be0d  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18002be12  test    rcx, rcx
0x18002be15  jz      short loc_18002BE23
0x18002be17  call    cs:__imp_SysFreeString
0x18002be1e  nop     dword ptr [rax+rax+00h]
0x18002be23  mov     eax, ebx
0x18002be25  mov     rbx, [rsp+48h+arg_8]
0x18002be2a  add     rsp, 20h
0x18002be2e  pop     r15
0x18002be30  pop     r14
0x18002be32  pop     rdi
0x18002be33  pop     rsi
0x18002be34  pop     rbp
0x18002be35  retn
```
