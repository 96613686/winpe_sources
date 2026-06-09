# GetGCSearchPointer

- ea: `0x180079b58`
- end: `0x180079d52`
- name: `GetGCSearchPointer`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007a050`

## callees

- `0x18001aea4`
- `0x180078bbc`
- `0x180078e98`
- `0x180079b58`
- `0x1800a5010`

## import_xrefs

- `ACTIVEDS!__imp_ADsBuildEnumerator` at `0x180079c11`
- `ACTIVEDS!__imp_ADsBuildEnumerator` at `0x180079c11`
- `ACTIVEDS!__imp_ADsFreeEnumerator` at `0x180079d15`
- `ACTIVEDS!__imp_ADsFreeEnumerator` at `0x180079d15`
- `ACTIVEDS!__imp_ADsEnumerateNext` at `0x180079c63`
- `ACTIVEDS!__imp_ADsEnumerateNext` at `0x180079c63`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180079bb3`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180079bb3`
- `OLEAUT32!__imp_VariantInit` at `0x180079b7b`
- `OLEAUT32!__imp_VariantInit` at `0x180079b7b`
- `OLEAUT32!__imp_VariantClear` at `0x180079d26`
- `OLEAUT32!__imp_VariantClear` at `0x180079d26`

## string_xrefs

- `0x180079be9`: `"ADsOpenObject"`
- `0x180079cfb`: `"pDispatch->QueryInterface IID_IDirectorySearch"`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetGCSearchPointer(_QWORD *a1)
{
  struct IUnknown *v2; // rbx
  HRESULT v3; // edi
  _QWORD *v4; // rcx
  int v5; // edx
  const wchar_t *v6; // r9
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  ULONG pcElementsFetched; // [rsp+80h] [rbp+28h] BYREF
  IEnumVARIANT *ppEnumVariant; // [rsp+88h] [rbp+30h] BYREF
  struct IUnknown *v11; // [rsp+90h] [rbp+38h] BYREF
  IADsContainer *pADsContainer; // [rsp+98h] [rbp+40h] BYREF

  pADsContainer = 0;
  ppEnumVariant = 0;
  v2 = 0;
  v11 = 0;
  VariantInit(&pvarg);
  pcElementsFetched = 0;
  *a1 = 0;
  v3 = ADsOpenObject(L"GC:", 0, 0, 1u, &IID_IADsContainer, (void **)&pADsContainer);
  if ( v3 >= 0 )
  {
    v3 = ADsBuildEnumerator(pADsContainer, &ppEnumVariant);
    if ( v3 >= 0 )
    {
      v3 = ADsEnumerateNext(ppEnumVariant, 1u, &pvarg, &pcElementsFetched);
      if ( v3 >= 0 )
      {
        if ( pcElementsFetched == 1 )
        {
          if ( pvarg.llVal )
          {
            ATL::AtlComPtrAssign(&v11, pvarg.punkVal);
            v2 = v11;
          }
          v3 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))v2->lpVtbl->QueryInterface)(
                 v2,
                 &IID_IDirectorySearch,
                 a1);
          if ( v3 < 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v5 = 99;
              v6 = L"\"pDispatch->QueryInterface IID_IDirectorySearch\"";
              goto LABEL_5;
            }
          }
        }
        else
        {
          v3 = -2147467259;
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 98;
          v6 = L"\"ADsEnumerateNext\"";
          goto LABEL_5;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 97;
        v6 = L"\"ADsBuildEnumerator\"";
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 96;
      v6 = L"\"ADsOpenObject\"";
LABEL_5:
      WPP_SF_SD(v4[2], v5, (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (_DWORD)v6, v3);
    }
  }
  if ( ppEnumVariant )
    ADsFreeEnumerator(ppEnumVariant);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&v11);
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&pADsContainer);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180079b58  push    rbp
0x180079b5a  push    rbx
0x180079b5b  push    rsi
0x180079b5c  push    rdi
0x180079b5d  mov     rbp, rsp
0x180079b60  sub     rsp, 58h
0x180079b64  mov     rsi, rcx
0x180079b67  and     [rbp+pADsContainer], 0
0x180079b6c  and     [rbp+ppEnumVariant], 0
0x180079b71  xor     ebx, ebx
0x180079b73  mov     [rbp+arg_10], rbx
0x180079b77  lea     rcx, [rbp+pvarg]; pvarg
0x180079b7b  call    cs:__imp_VariantInit
0x180079b82  nop     dword ptr [rax+rax+00h]
0x180079b87  nop
0x180079b88  and     [rbp+pcElementsFetched], ebx
0x180079b8b  and     [rsi], rbx
0x180079b8e  lea     rax, [rbp+pADsContainer]
0x180079b92  mov     [rsp+58h+ppObject], rax; ppObject
0x180079b97  lea     rax, IID_IADsContainer
0x180079b9e  mov     [rsp+58h+riid], rax; riid
0x180079ba3  lea     r9d, [rbx+1]; dwReserved
0x180079ba7  xor     r8d, r8d; lpszPassword
0x180079baa  xor     edx, edx; lpszUserName
0x180079bac  lea     rcx, szPathName; "GC:"
0x180079bb3  call    cs:__imp_ADsOpenObject
0x180079bba  nop     dword ptr [rax+rax+00h]
0x180079bbf  mov     edi, eax
0x180079bc1  test    eax, eax
0x180079bc3  jns     short loc_180079C09
0x180079bc5  lea     rax, WPP_GLOBAL_Control
0x180079bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180079bd3  cmp     rcx, rax
0x180079bd6  jz      loc_180079D0C
0x180079bdc  cmp     byte ptr [rcx+19h], 2
0x180079be0  jb      loc_180079D0C
0x180079be6  lea     edx, [rbx+60h]
0x180079be9  lea     r9, aAdsopenobject; "\"ADsOpenObject\""
0x180079bf0  mov     dword ptr [rsp+58h+riid], edi
0x180079bf4  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x180079bfb  mov     rcx, [rcx+10h]
0x180079bff  call    WPP_SF_SD
0x180079c04  jmp     loc_180079D0C
0x180079c09  lea     rdx, [rbp+ppEnumVariant]; ppEnumVariant
0x180079c0d  mov     rcx, [rbp+pADsContainer]; pADsContainer
0x180079c11  call    cs:__imp_ADsBuildEnumerator
0x180079c18  nop     dword ptr [rax+rax+00h]
0x180079c1d  mov     edi, eax
0x180079c1f  test    eax, eax
0x180079c21  jns     short loc_180079C52
0x180079c23  lea     rax, WPP_GLOBAL_Control
0x180079c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c31  cmp     rcx, rax
0x180079c34  jz      loc_180079D0C
0x180079c3a  cmp     byte ptr [rcx+19h], 2
0x180079c3e  jb      loc_180079D0C
0x180079c44  mov     edx, 61h ; 'a'
0x180079c49  lea     r9, aAdsbuildenumer; "\"ADsBuildEnumerator\""
0x180079c50  jmp     short loc_180079BF0
0x180079c52  lea     r9, [rbp+pcElementsFetched]; pcElementsFetched
0x180079c56  lea     r8, [rbp+pvarg]; pvar
0x180079c5a  mov     edx, 1; cElements
0x180079c5f  mov     rcx, [rbp+ppEnumVariant]; pEnumVariant
0x180079c63  call    cs:__imp_ADsEnumerateNext
0x180079c6a  nop     dword ptr [rax+rax+00h]
0x180079c6f  mov     edi, eax
0x180079c71  test    eax, eax
0x180079c73  jns     short loc_180079CA3
0x180079c75  lea     rax, WPP_GLOBAL_Control
0x180079c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c83  cmp     rcx, rax
0x180079c86  jz      loc_180079D0C
0x180079c8c  cmp     byte ptr [rcx+19h], 2
0x180079c90  jb      short loc_180079D0C
0x180079c92  mov     edx, 62h ; 'b'
0x180079c97  lea     r9, aAdsenumeratene; "\"ADsEnumerateNext\""
0x180079c9e  jmp     loc_180079BF0
0x180079ca3  cmp     [rbp+pcElementsFetched], 1
0x180079ca7  jnz     short loc_180079D07
0x180079ca9  mov     rdx, qword ptr [rbp+pvarg+8]; struct IUnknown *
0x180079cad  test    rdx, rdx
0x180079cb0  jz      short loc_180079CBF
0x180079cb2  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x180079cb6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180079cbb  mov     rbx, [rbp+arg_10]
0x180079cbf  mov     rax, [rbx]
0x180079cc2  mov     r8, rsi
0x180079cc5  lea     rdx, IID_IDirectorySearch
0x180079ccc  mov     rcx, rbx
0x180079ccf  mov     rax, [rax]
0x180079cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cd7  mov     edi, eax
0x180079cd9  test    eax, eax
0x180079cdb  jns     short loc_180079D0C
0x180079cdd  lea     rax, WPP_GLOBAL_Control
0x180079ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ceb  cmp     rcx, rax
0x180079cee  jz      short loc_180079D0C
0x180079cf0  cmp     byte ptr [rcx+19h], 2
0x180079cf4  jb      short loc_180079D0C
0x180079cf6  mov     edx, 63h ; 'c'
0x180079cfb  lea     r9, aPdispatchQuery; "\"pDispatch->QueryInterface IID_IDirect"...
0x180079d02  jmp     loc_180079BF0
0x180079d07  mov     edi, 80004005h
0x180079d0c  mov     rcx, [rbp+ppEnumVariant]; pEnumVariant
0x180079d10  test    rcx, rcx
0x180079d13  jz      short loc_180079D22
0x180079d15  call    cs:__imp_ADsFreeEnumerator
0x180079d1c  nop     dword ptr [rax+rax+00h]
0x180079d21  nop
0x180079d22  lea     rcx, [rbp+pvarg]; pvarg
0x180079d26  call    cs:__imp_VariantClear
0x180079d2d  nop     dword ptr [rax+rax+00h]
0x180079d32  nop
0x180079d33  lea     rcx, [rbp+arg_10]
0x180079d37  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x180079d3c  nop
0x180079d3d  lea     rcx, [rbp+pADsContainer]
0x180079d41  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x180079d46  mov     eax, edi
0x180079d48  add     rsp, 58h
0x180079d4c  pop     rdi
0x180079d4d  pop     rsi
0x180079d4e  pop     rbx
0x180079d4f  pop     rbp
0x180079d50  retn
```
