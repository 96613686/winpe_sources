# XopParseEapConfig(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)

- ea: `0x18003c694`
- end: `0x18003c999`
- name: `?XopParseEapConfig@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z`
- size: `773`
- prototype: `unsigned int(unsigned int, struct IXMLDOMNode *, struct _ONEX_CONNECTION_PROFILE **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bf70`

## callees

- `0x1800025f0`
- `0x1800030fc`
- `0x180030fd8`
- `0x1800326fc`
- `0x18003ba24`
- `0x18003bcb0`
- `0x18003bd10`
- `0x18003c694`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7e9`
- `eappcfg!EapHostPeerFreeMemory` at `0x18003c95b`
- `eappcfg!EapHostPeerFreeMemory` at `0x18003c95b`
- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18003c76f`
- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18003c76f`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18003c94c`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18003c94c`

## string_xrefs

- `0x18003c6ce`: `OneX:EAPConfig`

## pseudocode

```c
__int64 __fastcall XopParseEapConfig(
        __int64 a1,
        struct IXMLDOMNode *a2,
        struct _ONEX_CONNECTION_PROFILE **a3,
        unsigned int *a4)
{
  unsigned int SingleNode; // eax
  DWORD LastError; // ebx
  int v7; // eax
  char *v8; // rcx
  __int64 v9; // rax
  DWORD v10; // ebx
  DWORD v11; // esi
  _OWORD *v12; // rdi
  char *v13; // rax
  __int64 v14; // r8
  EAP_METHOD_TYPE v15; // xmm2
  __int64 v16; // r9
  unsigned int *v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r10d
  __int64 v21; // r11
  unsigned int v22; // ebx
  unsigned int *v23; // rdx
  int v24; // r8d
  __int64 v25; // r9
  size_t v26; // r10
  const void *v27; // r11
  __int64 v28; // rax
  __int64 v29; // r9
  DWORD pdwSizeOfConfigOut; // [rsp+30h] [rbp-50h] BYREF
  BYTE *ppConfigOut; // [rsp+38h] [rbp-48h] BYREF
  EAP_ERROR *pEapError; // [rsp+40h] [rbp-40h] BYREF
  IXMLDOMNode *pConfigDoc; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMNode *v35[2]; // [rsp+50h] [rbp-30h] BYREF
  EAP_METHOD_TYPE pEapMethodType; // [rsp+60h] [rbp-20h] BYREF

  v35[0] = 0;
  *(_WORD *)(&pEapMethodType.eapType.type + 1) = 0;
  *(&pEapMethodType.eapType.type + 3) = 0;
  *(_QWORD *)&pEapMethodType.eapType.dwVendorId = 0;
  pEapMethodType.dwAuthorId = 0;
  pdwSizeOfConfigOut = 0;
  ppConfigOut = 0;
  pEapError = 0;
  pConfigDoc = 0;
  pEapMethodType.eapType.type = 0;
  SingleNode = XcGetSingleNode(a2, L"OneX:EAPConfig", v35);
  LastError = SingleNode;
  if ( SingleNode == 1168 )
  {
    LastError = 1206;
    goto LABEL_42;
  }
  if ( SingleNode )
    goto LABEL_42;
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, IXMLDOMNode **))v35[0]->lpVtbl->get_firstChild)(
         v35[0],
         &pConfigDoc);
  LastError = v7;
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v7;
    if ( LastError )
      goto LABEL_42;
  }
  if ( EapHostPeerConfigXml2Blob(0x80u, pConfigDoc, &pdwSizeOfConfigOut, &ppConfigOut, &pEapMethodType, &pEapError) )
  {
    LastError = 1206;
    if ( !pEapError )
      goto LABEL_44;
    goto LABEL_42;
  }
  v8 = (char *)*a3;
  v9 = *((unsigned int *)*a3 + 16);
  *(_DWORD *)&v8[v9 + 20] &= ~1u;
  *(EAP_METHOD_TYPE *)&v8[v9 + 4] = pEapMethodType;
  if ( *a3 )
  {
    v10 = 104;
    v11 = 104;
    if ( ppConfigOut )
    {
      if ( pdwSizeOfConfigOut )
      {
        if ( pdwSizeOfConfigOut >= 0xFFFFFFEC || (v11 = pdwSizeOfConfigOut + 124, pdwSizeOfConfigOut + 124 < 0x68) )
        {
          LastError = 534;
          goto LABEL_42;
        }
      }
    }
    v12 = Xc_Process_user_allocate(v11);
    if ( !v12 )
    {
      LastError = GetLastError();
      goto LABEL_42;
    }
    v13 = (char *)*a3;
    if ( !*a3 )
    {
      LastError = 87;
      goto LABEL_40;
    }
    v14 = 0;
    if ( ppConfigOut && pdwSizeOfConfigOut )
    {
      v14 = pdwSizeOfConfigOut + 20;
      if ( pdwSizeOfConfigOut >= 0xFFFFFFEC || pdwSizeOfConfigOut + 124 < 0x68 )
        goto LABEL_35;
      v10 = pdwSizeOfConfigOut + 124;
    }
    if ( v11 < v10 )
    {
      LastError = 122;
      goto LABEL_40;
    }
    v15 = pEapMethodType;
    *v12 = *(_OWORD *)v13;
    v12[1] = *((_OWORD *)v13 + 1);
    v12[2] = *((_OWORD *)v13 + 2);
    v12[3] = *((_OWORD *)v13 + 3);
    v12[4] = *((_OWORD *)v13 + 4);
    v12[5] = *((_OWORD *)v13 + 5);
    *((_QWORD *)v12 + 12) = *((_QWORD *)v13 + 12);
    v16 = *((unsigned int *)v12 + 16);
    *((_DWORD *)v12 + 1) = v10;
    *(EAP_METHOD_TYPE *)((char *)v12 + v16 + 4) = v15;
    LastError = GetAlignedSize(32, (char *)v12 + 60, v14);
    if ( LastError )
      goto LABEL_40;
    v22 = *v17 + v18;
    if ( v22 >= *v17 )
    {
      *v17 = v22;
      if ( v21 && v20 )
      {
        *(_DWORD *)(v19 + 20) |= 1u;
        LastError = GetAlignedSize(32, v19 + 28, v18);
        if ( !LastError )
        {
          v28 = *v23;
          *(_DWORD *)(v25 + 24) = v24;
          *(_DWORD *)(v28 + v25 + 16) = v26;
          *(EAP_METHOD_TYPE *)(v28 + v25) = v15;
          memcpy_0((void *)(v25 + v28 + 20), v27, v26);
LABEL_37:
          Xc_Process_user_free(*a3);
          *a3 = (struct _ONEX_CONNECTION_PROFILE *)v12;
          goto LABEL_42;
        }
      }
      else
      {
        *(_DWORD *)(v19 + 20) &= ~1u;
        LastError = GetAlignedSize(32, v19 + 28, v18);
        if ( !LastError )
        {
          *(_DWORD *)(v29 + 24) = 0;
          goto LABEL_37;
        }
      }
      goto LABEL_40;
    }
    *v17 = -1;
LABEL_35:
    LastError = 534;
LABEL_40:
    Xc_Process_user_free(v12);
    goto LABEL_42;
  }
  LastError = 87;
LABEL_42:
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
LABEL_44:
  if ( ppConfigOut )
    EapHostPeerFreeMemory(ppConfigOut);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&pConfigDoc);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)v35);
  return LastError;
}

```

## disassembly

```asm
0x18003c694  mov     [rsp-18h+arg_0], rbx
0x18003c699  mov     [rsp-18h+arg_18], rsi
0x18003c69e  push    rbp
0x18003c69f  push    rdi
0x18003c6a0  push    r14
0x18003c6a2  mov     rbp, rsp
0x18003c6a5  sub     rsp, 80h
0x18003c6ac  mov     rax, cs:__security_cookie
0x18003c6b3  xor     rax, rsp
0x18003c6b6  mov     [rbp+var_10], rax
0x18003c6ba  xor     ecx, ecx
0x18003c6bc  mov     [rbp+var_30], 0
0x18003c6c4  mov     rax, rdx
0x18003c6c7  mov     word ptr [rbp+var_20.eapType+1], cx
0x18003c6cb  mov     byte ptr [rbp+var_20.eapType+3], cl
0x18003c6ce  lea     rdx, aOnexEapconfig; "OneX:EAPConfig"
0x18003c6d5  mov     qword ptr [rbp+var_20.eapType.dwVendorId], rcx
0x18003c6d9  mov     r14, r8
0x18003c6dc  mov     [rbp+var_20.dwAuthorId], ecx
0x18003c6df  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x18003c6e3  mov     [rbp+pdwSizeOfConfigOut], ecx
0x18003c6e6  mov     [rbp+ppConfigOut], rcx
0x18003c6ea  mov     [rbp+pEapError], rcx
0x18003c6ee  mov     rcx, rax; struct IXMLDOMNode *
0x18003c6f1  mov     [rbp+pConfigDoc], 0
0x18003c6f9  mov     [rbp+var_20.eapType.type], 0
0x18003c6fd  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18003c702  mov     ebx, eax
0x18003c704  cmp     eax, 490h
0x18003c709  jnz     short loc_18003C713
0x18003c70b  lea     ebx, [rax+26h]
0x18003c70e  jmp     loc_18003C943
0x18003c713  test    eax, eax
0x18003c715  jnz     loc_18003C943
0x18003c71b  mov     rcx, [rbp+var_30]
0x18003c71f  lea     rdx, [rbp+pConfigDoc]
0x18003c723  mov     rax, [rcx]
0x18003c726  mov     rax, [rax+68h]
0x18003c72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c72f  mov     ebx, eax
0x18003c731  test    eax, eax
0x18003c733  jns     short loc_18003C74C
0x18003c735  and     eax, 1FFF0000h
0x18003c73a  cmp     eax, 70000h
0x18003c73f  jnz     short loc_18003C744
0x18003c741  movzx   ebx, bx
0x18003c744  test    ebx, ebx
0x18003c746  jnz     loc_18003C943
0x18003c74c  mov     rdx, [rbp+pConfigDoc]; pConfigDoc
0x18003c750  lea     rax, [rbp+pEapError]
0x18003c754  mov     [rsp+80h+ppEapError], rax; ppEapError
0x18003c759  lea     r9, [rbp+ppConfigOut]; ppConfigOut
0x18003c75d  lea     rax, [rbp+var_20]
0x18003c761  mov     ecx, 80h; dwFlags
0x18003c766  lea     r8, [rbp+pdwSizeOfConfigOut]; pdwSizeOfConfigOut
0x18003c76a  mov     [rsp+80h+pEapMethodType], rax; pEapMethodType
0x18003c76f  call    cs:__imp_EapHostPeerConfigXml2Blob
0x18003c775  test    eax, eax
0x18003c777  jz      short loc_18003C78E
0x18003c779  cmp     [rbp+pEapError], 0
0x18003c77e  mov     ebx, 4B6h
0x18003c783  jnz     loc_18003C943
0x18003c789  jmp     loc_18003C952
0x18003c78e  mov     rcx, [r14]
0x18003c791  mov     eax, [rcx+40h]
0x18003c794  and     dword ptr [rax+rcx+14h], 0FFFFFFFEh
0x18003c799  movaps  xmm0, xmmword ptr [rbp+var_20.eapType.type]
0x18003c79d  movdqu  xmmword ptr [rax+rcx+4], xmm0
0x18003c7a3  cmp     qword ptr [r14], 0
0x18003c7a7  jz      loc_18003C93E
0x18003c7ad  cmp     [rbp+ppConfigOut], 0
0x18003c7b2  mov     ebx, 68h ; 'h'
0x18003c7b7  mov     esi, ebx
0x18003c7b9  jz      short loc_18003C7DA
0x18003c7bb  mov     eax, [rbp+pdwSizeOfConfigOut]
0x18003c7be  test    eax, eax
0x18003c7c0  jz      short loc_18003C7DA
0x18003c7c2  lea     esi, [rax+14h]
0x18003c7c5  cmp     esi, 14h
0x18003c7c8  jb      short loc_18003C7D0
0x18003c7ca  add     esi, ebx
0x18003c7cc  cmp     esi, ebx
0x18003c7ce  jnb     short loc_18003C7DA
0x18003c7d0  mov     ebx, 216h
0x18003c7d5  jmp     loc_18003C943
0x18003c7da  mov     ecx, esi; dwBytes
0x18003c7dc  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18003c7e1  mov     rdi, rax
0x18003c7e4  test    rax, rax
0x18003c7e7  jnz     short loc_18003C7F6
0x18003c7e9  call    cs:__imp_GetLastError
0x18003c7ef  mov     ebx, eax
0x18003c7f1  jmp     loc_18003C943
0x18003c7f6  mov     rax, [r14]
0x18003c7f9  test    rax, rax
0x18003c7fc  jz      loc_18003C92F
0x18003c802  mov     r11, [rbp+ppConfigOut]
0x18003c806  xor     r8d, r8d
0x18003c809  mov     r10d, [rbp+pdwSizeOfConfigOut]
0x18003c80d  test    r11, r11
0x18003c810  jz      short loc_18003C833
0x18003c812  test    r10d, r10d
0x18003c815  jz      short loc_18003C833
0x18003c817  lea     r8d, [r10+14h]
0x18003c81b  cmp     r8d, 14h
0x18003c81f  jb      loc_18003C910
0x18003c825  lea     ecx, [r8+68h]
0x18003c829  cmp     ecx, ebx
0x18003c82b  jb      loc_18003C910
0x18003c831  mov     ebx, ecx
0x18003c833  cmp     esi, ebx
0x18003c835  jb      loc_18003C928
0x18003c83b  movups  xmm0, xmmword ptr [rax]
0x18003c83e  lea     rdx, [rdi+3Ch]
0x18003c842  mov     esi, 20h ; ' '
0x18003c847  movaps  xmm2, xmmword ptr [rbp+var_20.eapType.type]
0x18003c84b  mov     ecx, esi
0x18003c84d  movups  xmmword ptr [rdi], xmm0
0x18003c850  movups  xmm1, xmmword ptr [rax+10h]
0x18003c854  movups  xmmword ptr [rdi+10h], xmm1
0x18003c858  movups  xmm0, xmmword ptr [rax+20h]
0x18003c85c  movups  xmmword ptr [rdi+20h], xmm0
0x18003c860  movups  xmm1, xmmword ptr [rax+30h]
0x18003c864  movups  xmmword ptr [rdi+30h], xmm1
0x18003c868  movups  xmm0, xmmword ptr [rax+40h]
0x18003c86c  movups  xmmword ptr [rdi+40h], xmm0
0x18003c870  movups  xmm1, xmmword ptr [rax+50h]
0x18003c874  movups  xmmword ptr [rdi+50h], xmm1
0x18003c878  movsd   xmm0, qword ptr [rax+60h]
0x18003c87d  movsd   qword ptr [rdi+60h], xmm0
0x18003c882  mov     r9d, [rdi+40h]
0x18003c886  mov     [rdi+4], ebx
0x18003c889  add     r9, rdi
0x18003c88c  movdqu  xmmword ptr [r9+4], xmm2
0x18003c892  call    GetAlignedSize
0x18003c897  mov     ebx, eax
0x18003c899  test    eax, eax
0x18003c89b  jnz     short loc_18003C917
0x18003c89d  mov     eax, [rdx]
0x18003c89f  lea     ebx, [rax+r8]
0x18003c8a3  cmp     ebx, eax
0x18003c8a5  jb      short loc_18003C90A
0x18003c8a7  mov     [rdx], ebx
0x18003c8a9  test    r11, r11
0x18003c8ac  jz      short loc_18003C8EE
0x18003c8ae  test    r10d, r10d
0x18003c8b1  jz      short loc_18003C8EE
0x18003c8b3  or      dword ptr [r9+14h], 1
0x18003c8b8  lea     rdx, [r9+1Ch]
0x18003c8bc  mov     ecx, esi
0x18003c8be  call    GetAlignedSize
0x18003c8c3  mov     ebx, eax
0x18003c8c5  test    eax, eax
0x18003c8c7  jnz     short loc_18003C917
0x18003c8c9  mov     eax, [rdx]
0x18003c8cb  mov     rdx, r11; Src
0x18003c8ce  mov     [r9+18h], r8d
0x18003c8d2  mov     r8, r10; Size
0x18003c8d5  lea     rcx, [rax+14h]
0x18003c8d9  mov     [rax+r9+10h], r10d
0x18003c8de  add     rcx, r9; void *
0x18003c8e1  movdqu  xmmword ptr [rax+r9], xmm2
0x18003c8e7  call    memcpy_0
0x18003c8ec  jmp     short loc_18003C91B
0x18003c8ee  and     dword ptr [r9+14h], 0FFFFFFFEh
0x18003c8f3  lea     rdx, [r9+1Ch]
0x18003c8f7  mov     ecx, esi
0x18003c8f9  call    GetAlignedSize
0x18003c8fe  mov     ebx, eax
0x18003c900  test    eax, eax
0x18003c902  jnz     short loc_18003C917
0x18003c904  mov     [r9+18h], eax
0x18003c908  jmp     short loc_18003C91B
0x18003c90a  mov     dword ptr [rdx], 0FFFFFFFFh
0x18003c910  mov     ebx, 216h
0x18003c915  jmp     short loc_18003C934
0x18003c917  test    ebx, ebx
0x18003c919  jnz     short loc_18003C934
0x18003c91b  mov     rcx, [r14]; lpMem
0x18003c91e  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18003c923  mov     [r14], rdi
0x18003c926  jmp     short loc_18003C943
0x18003c928  mov     ebx, 7Ah ; 'z'
0x18003c92d  jmp     short loc_18003C934
0x18003c92f  mov     ebx, 57h ; 'W'
0x18003c934  mov     rcx, rdi; lpMem
0x18003c937  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18003c93c  jmp     short loc_18003C943
0x18003c93e  mov     ebx, 57h ; 'W'
0x18003c943  mov     rcx, [rbp+pEapError]; pEapError
0x18003c947  test    rcx, rcx
0x18003c94a  jz      short loc_18003C952
0x18003c94c  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18003c952  mov     rcx, [rbp+ppConfigOut]; pData
0x18003c956  test    rcx, rcx
0x18003c959  jz      short loc_18003C961
0x18003c95b  call    cs:__imp_EapHostPeerFreeMemory
0x18003c961  lea     rcx, [rbp+pConfigDoc]
0x18003c965  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c96a  lea     rcx, [rbp+var_30]
0x18003c96e  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c973  mov     eax, ebx
0x18003c975  mov     rcx, [rbp+var_10]
0x18003c979  xor     rcx, rsp; StackCookie
0x18003c97c  call    __security_check_cookie
0x18003c981  lea     r11, [rsp+80h+var_s0]
0x18003c989  mov     rbx, [r11+20h]
0x18003c98d  mov     rsi, [r11+38h]
0x18003c991  mov     rsp, r11
0x18003c994  pop     r14
0x18003c996  pop     rdi
0x18003c997  pop     rbp
0x18003c998  retn
```
