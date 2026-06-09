# XopGenerateEapConfig(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18003c2e0`
- end: `0x18003c526`
- name: `?XopGenerateEapConfig@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `582`
- prototype: `unsigned int(struct _ONEX_CONNECTION_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bd50`

## callees

- `0x1800030fc`
- `0x18000c4b0`
- `0x180030fa4`
- `0x1800326fc`
- `0x18003aa34`
- `0x18003bcb0`
- `0x18003bd10`
- `0x18003c2e0`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3b4`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18003c46c`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18003c46c`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18003c4e3`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18003c4e3`

## string_xrefs

- `0x18003c31f`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18003c326`: `EAPConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XopGenerateEapConfig(
        struct _ONEX_CONNECTION_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  void *v4; // rdi
  DWORD LastError; // ebx
  char *v6; // r9
  EAP_METHOD_TYPE v7; // xmm6
  __int64 v8; // r9
  __int64 v9; // r10
  __int64 v10; // r9
  __int64 v11; // r10
  DWORD v12; // ebx
  char *v13; // r9
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 v16; // r9
  __int64 v17; // r10
  int v18; // eax
  int v19; // eax
  struct IXMLDOMNode *v21; // [rsp+30h] [rbp-19h] BYREF
  IXMLDOMDocument2 *ppConfigDoc; // [rsp+38h] [rbp-11h] BYREF
  EAP_ERROR *pEapError; // [rsp+40h] [rbp-9h] BYREF
  __int128 v24; // [rsp+50h] [rbp+7h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+60h] [rbp+17h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = 0;
  pEapError = 0;
  ppConfigDoc = 0;
  v21 = 0;
  v26 = 0;
  LastError = XcAddChildElement(
                a2,
                a3,
                (OLECHAR *)L"EAPConfig",
                (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
                0,
                &v21);
  if ( !LastError )
  {
    v6 = (char *)a1 + *((unsigned int *)a1 + 16);
    v7 = *(EAP_METHOD_TYPE *)(v6 + 4);
    if ( (v6[20] & 1) == 0
      || (v24 = *(_OWORD *)(v6 + 4), eapMethodType = v7, (unsigned int)AreDifferentEapTypes(&eapMethodType, &v24))
      || (v9 = *(unsigned int *)(v8 + 28),
          eapMethodType = v7,
          v24 = *(_OWORD *)(v9 + v8),
          (unsigned int)AreDifferentEapTypes(&v24, &eapMethodType)) )
    {
      v12 = 0;
      v4 = 0;
    }
    else
    {
      v12 = *(_DWORD *)(v11 + v10 + 16);
      v4 = Xc_Process_user_allocate(v12);
      if ( !v4 )
      {
        LastError = GetLastError();
        goto LABEL_24;
      }
      v13 = (char *)a1 + *((unsigned int *)a1 + 16);
      if ( (v13[20] & 1) == 0
        || (eapMethodType = v7, v24 = *(_OWORD *)(v13 + 4), (unsigned int)AreDifferentEapTypes(&v24, &eapMethodType))
        || (v15 = *(unsigned int *)(v14 + 28),
            eapMethodType = v7,
            v24 = *(_OWORD *)(v15 + v14),
            (unsigned int)AreDifferentEapTypes(&v24, &eapMethodType)) )
      {
        LastError = 1168;
        goto LABEL_24;
      }
      if ( v12 < *(_DWORD *)(v17 + v16 + 16) )
      {
        LastError = 122;
        goto LABEL_24;
      }
      memcpy_0(v4, (const void *)(v17 + v16 + 20), *(unsigned int *)(v17 + v16 + 16));
    }
    eapMethodType = v7;
    LastError = EapHostPeerConfigBlob2Xml(0x80u, &eapMethodType, v12, (BYTE *)v4, &ppConfigDoc, &pEapError);
    if ( !LastError )
    {
      v18 = ((__int64 (__fastcall *)(IXMLDOMDocument2 *, __int64 *))ppConfigDoc->lpVtbl->get_documentElement)(
              ppConfigDoc,
              &v26);
      LastError = v18;
      if ( v18 >= 0 )
        goto LABEL_20;
      if ( (v18 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v18;
      if ( !LastError )
      {
LABEL_20:
        v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v21->lpVtbl->appendChild)(v21, v26, 0);
        LastError = v19;
        if ( v19 < 0 )
        {
          if ( (v19 & 0x1FFF0000) == 0x70000 )
            LastError = (unsigned __int16)v19;
        }
        else
        {
          LastError = 0;
        }
      }
    }
  }
LABEL_24:
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
  if ( v4 )
    Xc_Process_user_free(v4);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(&v26);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v21);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppConfigDoc);
  return LastError;
}

```

## disassembly

```asm
0x18003c2e0  push    rbp
0x18003c2e2  push    rbx
0x18003c2e3  push    rsi
0x18003c2e4  push    rdi
0x18003c2e5  lea     rbp, [rsp-3Fh]
0x18003c2ea  sub     rsp, 88h
0x18003c2f1  movaps  [rsp+0A0h+var_30], xmm6
0x18003c2f6  mov     rax, r8
0x18003c2f9  mov     r10, rdx
0x18003c2fc  mov     rsi, rcx
0x18003c2ff  xor     edi, edi
0x18003c301  mov     [rbp+57h+pEapError], rdi
0x18003c305  mov     [rbp+57h+var_68], rdi
0x18003c309  mov     [rbp+57h+var_70], rdi
0x18003c30d  mov     [rbp+57h+arg_18], rdi
0x18003c311  lea     rcx, [rbp+57h+var_70]
0x18003c315  mov     [rsp+0A0h+ppEapError], rcx; struct IXMLDOMNode **
0x18003c31a  mov     [rsp+0A0h+ppConfigDoc], rdi; OLECHAR *
0x18003c31f  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18003c326  lea     r8, aEapconfig; "EAPConfig"
0x18003c32d  mov     rdx, rax; struct IXMLDOMNode *
0x18003c330  mov     rcx, r10; struct IXMLDOMDocument2 *
0x18003c333  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18003c338  mov     ebx, eax
0x18003c33a  test    eax, eax
0x18003c33c  jnz     loc_18003C4DA
0x18003c342  mov     r9d, [rsi+40h]
0x18003c346  add     r9, rsi
0x18003c349  movups  xmm6, xmmword ptr [r9+4]
0x18003c34e  test    byte ptr [r9+14h], 1
0x18003c353  jz      loc_18003C442
0x18003c359  movdqu  [rbp+57h+var_50], xmm6
0x18003c35e  movdqu  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18003c363  lea     rdx, [rbp+57h+var_50]
0x18003c367  lea     rcx, [rbp+57h+eapMethodType]
0x18003c36b  call    AreDifferentEapTypes
0x18003c370  test    eax, eax
0x18003c372  jnz     loc_18003C442
0x18003c378  mov     r10d, [r9+1Ch]
0x18003c37c  movdqu  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18003c381  movups  xmm1, xmmword ptr [r10+r9]
0x18003c386  movdqu  [rbp+57h+var_50], xmm1
0x18003c38b  lea     rdx, [rbp+57h+eapMethodType]
0x18003c38f  lea     rcx, [rbp+57h+var_50]
0x18003c393  call    AreDifferentEapTypes
0x18003c398  test    eax, eax
0x18003c39a  jnz     loc_18003C442
0x18003c3a0  mov     ebx, [r10+r9+10h]
0x18003c3a5  mov     ecx, ebx; dwBytes
0x18003c3a7  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18003c3ac  mov     rdi, rax
0x18003c3af  test    rax, rax
0x18003c3b2  jnz     short loc_18003C3C1
0x18003c3b4  call    cs:__imp_GetLastError
0x18003c3ba  mov     ebx, eax
0x18003c3bc  jmp     loc_18003C4DA
0x18003c3c1  mov     r9d, [rsi+40h]
0x18003c3c5  add     r9, rsi
0x18003c3c8  test    byte ptr [r9+14h], 1
0x18003c3cd  jz      short loc_18003C438
0x18003c3cf  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18003c3d4  movups  xmm0, xmmword ptr [r9+4]
0x18003c3d9  movdqu  [rbp+57h+var_50], xmm0
0x18003c3de  lea     rdx, [rbp+57h+eapMethodType]
0x18003c3e2  lea     rcx, [rbp+57h+var_50]
0x18003c3e6  call    AreDifferentEapTypes
0x18003c3eb  test    eax, eax
0x18003c3ed  jnz     short loc_18003C438
0x18003c3ef  mov     r10d, [r9+1Ch]
0x18003c3f3  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18003c3f8  movups  xmm0, xmmword ptr [r10+r9]
0x18003c3fd  movdqu  [rbp+57h+var_50], xmm0
0x18003c402  lea     rdx, [rbp+57h+eapMethodType]
0x18003c406  lea     rcx, [rbp+57h+var_50]
0x18003c40a  call    AreDifferentEapTypes
0x18003c40f  test    eax, eax
0x18003c411  jnz     short loc_18003C438
0x18003c413  cmp     ebx, [r10+r9+10h]
0x18003c418  jnb     short loc_18003C422
0x18003c41a  lea     ebx, [rax+7Ah]
0x18003c41d  jmp     loc_18003C4DA
0x18003c422  mov     r8d, [r10+r9+10h]; Size
0x18003c427  lea     rdx, [r9+14h]
0x18003c42b  add     rdx, r10; Src
0x18003c42e  mov     rcx, rdi; void *
0x18003c431  call    memcpy_0
0x18003c436  jmp     short loc_18003C446
0x18003c438  mov     ebx, 490h
0x18003c43d  jmp     loc_18003C4DA
0x18003c442  xor     ebx, ebx
0x18003c444  xor     edi, edi
0x18003c446  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18003c44b  lea     rax, [rbp+57h+pEapError]
0x18003c44f  mov     [rsp+0A0h+ppEapError], rax; ppEapError
0x18003c454  lea     rax, [rbp+57h+var_68]
0x18003c458  mov     [rsp+0A0h+ppConfigDoc], rax; ppConfigDoc
0x18003c45d  mov     r9, rdi; pConfigIn
0x18003c460  mov     r8d, ebx; dwSizeOfConfigIn
0x18003c463  lea     rdx, [rbp+57h+eapMethodType]; eapMethodType
0x18003c467  mov     ecx, 80h; dwFlags
0x18003c46c  call    cs:__imp_EapHostPeerConfigBlob2Xml
0x18003c472  mov     ebx, eax
0x18003c474  test    eax, eax
0x18003c476  jnz     short loc_18003C4DA
0x18003c478  mov     rcx, [rbp+57h+var_68]
0x18003c47c  mov     rax, [rcx]
0x18003c47f  lea     rdx, [rbp+57h+arg_18]
0x18003c483  mov     rax, [rax+168h]
0x18003c48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c48f  mov     ebx, eax
0x18003c491  mov     esi, 1FFF0000h
0x18003c496  test    eax, eax
0x18003c498  jns     short loc_18003C4AA
0x18003c49a  and     eax, esi
0x18003c49c  cmp     eax, 70000h
0x18003c4a1  jnz     short loc_18003C4A6
0x18003c4a3  movzx   ebx, bx
0x18003c4a6  test    ebx, ebx
0x18003c4a8  jnz     short loc_18003C4DA
0x18003c4aa  mov     rcx, [rbp+57h+var_70]
0x18003c4ae  mov     rax, [rcx]
0x18003c4b1  xor     r8d, r8d
0x18003c4b4  mov     rdx, [rbp+57h+arg_18]
0x18003c4b8  mov     rax, [rax+0A8h]
0x18003c4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4c4  mov     ebx, eax
0x18003c4c6  test    eax, eax
0x18003c4c8  js      short loc_18003C4CE
0x18003c4ca  xor     ebx, ebx
0x18003c4cc  jmp     short loc_18003C4DA
0x18003c4ce  and     eax, esi
0x18003c4d0  cmp     eax, 70000h
0x18003c4d5  jnz     short loc_18003C4DA
0x18003c4d7  movzx   ebx, bx
0x18003c4da  mov     rcx, [rbp+57h+pEapError]; pEapError
0x18003c4de  test    rcx, rcx
0x18003c4e1  jz      short loc_18003C4E9
0x18003c4e3  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18003c4e9  test    rdi, rdi
0x18003c4ec  jz      short loc_18003C4F6
0x18003c4ee  mov     rcx, rdi; lpMem
0x18003c4f1  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18003c4f6  lea     rcx, [rbp+57h+arg_18]
0x18003c4fa  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c4ff  lea     rcx, [rbp+57h+var_70]
0x18003c503  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c508  nop
0x18003c509  lea     rcx, [rbp+57h+var_68]
0x18003c50d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18003c512  nop
0x18003c513  mov     eax, ebx
0x18003c515  movaps  xmm6, [rsp+0A0h+var_30]
0x18003c51a  add     rsp, 88h
0x18003c521  pop     rdi
0x18003c522  pop     rsi
0x18003c523  pop     rbx
0x18003c524  pop     rbp
0x18003c525  retn
```
