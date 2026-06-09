# FindNode(IXmlReader *,IXmlWriter *,ushort const *,ushort const *)

- ea: `0x1800118ac`
- end: `0x180011c80`
- name: `?FindNode@@YAJPEAUIXmlReader@@PEAUIXmlWriter@@PEBG2@Z`
- size: `980`
- prototype: `__int64 __fastcall(struct IXmlReader *, struct IXmlWriter *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010438`
- `0x1800112a4`
- `0x180011e38`
- `0x180012444`

## callees

- `0x180006014`
- `0x1800118ac`
- `0x180018434`
- `0x180019010`

## string_xrefs

- `0x180011a51`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011ab6`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011aff`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011b39`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011b76`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011bb1`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011be8`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011c3a`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011c02`: `    Failed to read node type`
- `0x180011b19`: `    Failed to write element node shallow`
- `0x180011a7a`: `    Failed to write end node shallow`
- `0x180011adf`: `    Failed to write other node shallow`

## pseudocode

```c
__int64 __fastcall FindNode(
        struct IXmlReader *a1,
        struct IXmlWriter *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // r14d
  int v11; // eax
  struct IXmlReaderVtbl *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  struct IXmlReaderVtbl *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // eax
  unsigned int MaxCount; // [rsp+30h] [rbp-20h] BYREF
  unsigned int MaxCount_4; // [rsp+34h] [rbp-1Ch] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *v24; // [rsp+40h] [rbp-10h] BYREF
  int v25; // [rsp+80h] [rbp+30h] BYREF

  while ( !((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEOF)(a1) )
  {
    lpVtbl = a1->lpVtbl;
    v25 = 0;
    v9 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))lpVtbl->Read)(a1, &v25);
    v10 = v9;
    if ( v9 < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "FindNode",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        127,
        v9);
      ProvPackageLog(3, L"    Failed to read node type");
      return v10;
    }
    if ( a3 && v25 == 1 )
    {
      if ( a2 )
      {
        v11 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))a2->lpVtbl->WriteNodeShallow)(
                a2,
                a1,
                0);
        v10 = v11;
        if ( v11 < 0 )
        {
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "FindNode",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
            134,
            v11);
          ProvPackageLog(3, L"    Failed to write element node shallow");
          return v10;
        }
      }
      v12 = a1->lpVtbl;
      String1 = 0;
      MaxCount = 0;
      v13 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, unsigned int *))v12->GetLocalName)(
              a1,
              &String1,
              &MaxCount);
      v10 = v13;
      if ( v13 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "FindNode",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          141,
          v13);
        ProvPackageLog(3, L"    Failed to get element local name");
        return v10;
      }
      if ( String1 )
      {
        v14 = -1;
        do
          ++v14;
        while ( a3[v14] );
        if ( MaxCount == v14 && !wcsncmp_0(String1, a3, MaxCount) )
          return 0;
      }
    }
    else if ( a4 && v25 == 15 )
    {
      v16 = a1->lpVtbl;
      v24 = 0;
      MaxCount_4 = 0;
      v17 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, unsigned int *))v16->GetLocalName)(
              a1,
              &v24,
              &MaxCount_4);
      v10 = v17;
      if ( v17 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "FindNode",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          157,
          v17);
        ProvPackageLog(3, L"    Failed to get end node local name");
        return v10;
      }
      if ( v24 )
      {
        v18 = -1;
        do
          ++v18;
        while ( a4[v18] );
        if ( MaxCount_4 == v18 && !wcsncmp_0(v24, a4, MaxCount_4) )
        {
          if ( a3 )
          {
            ProvPackageLog(
              0,
              L"%hs (%hs:%d): %s",
              "FindNode",
              "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
              166,
              L"No more nodes");
            return 2147943568LL;
          }
          return 0;
        }
      }
      if ( a2 )
      {
        v19 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))a2->lpVtbl->WriteNodeShallow)(
                a2,
                a1,
                0);
        v10 = v19;
        if ( v19 < 0 )
        {
          ProvPackageLog(
            3,
            L"%hs (%hs:%d) - 0x%08x:",
            "FindNode",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
            176,
            v19);
          ProvPackageLog(3, L"    Failed to write end node shallow");
          return v10;
        }
      }
    }
    else if ( a2 )
    {
      v20 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))a2->lpVtbl->WriteNodeShallow)(
              a2,
              a1,
              0);
      v10 = v20;
      if ( v20 < 0 )
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "FindNode",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          184,
          v20);
        ProvPackageLog(3, L"    Failed to write other node shallow");
        return v10;
      }
    }
  }
  if ( !a3 && !a4 )
    return 0;
  ProvPackageLog(
    3,
    L"%hs (%hs:%d) - 0x%08x:",
    "FindNode",
    "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
    191,
    -2147023728);
  ProvPackageLog(3, L"    Node or stop node was not found");
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800118ac  mov     [rsp-28h+arg_8], rbx
0x1800118b1  mov     [rsp-28h+arg_10], rsi
0x1800118b6  push    rbp
0x1800118b7  push    rdi
0x1800118b8  push    r12
0x1800118ba  push    r14
0x1800118bc  push    r15
0x1800118be  mov     rbp, rsp
0x1800118c1  sub     rsp, 50h
0x1800118c5  mov     r15, r9
0x1800118c8  mov     rdi, r8
0x1800118cb  mov     rbx, rdx
0x1800118ce  mov     rsi, rcx
0x1800118d1  xor     r12d, r12d
0x1800118d4  mov     rax, [rsi]
0x1800118d7  mov     rcx, rsi
0x1800118da  mov     rax, [rax+0C8h]
0x1800118e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e6  test    eax, eax
0x1800118e8  jnz     loc_180011C15
0x1800118ee  mov     rax, [rsi]
0x1800118f1  lea     rdx, [rbp+arg_0]
0x1800118f5  mov     rcx, rsi
0x1800118f8  mov     [rbp+arg_0], r12d
0x1800118fc  mov     rax, [rax+30h]
0x180011900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011905  mov     r14d, eax
0x180011908  test    eax, eax
0x18001190a  js      loc_180011BD4
0x180011910  test    rdi, rdi
0x180011913  jz      loc_1800119B4
0x180011919  cmp     [rbp+arg_0], 1
0x18001191d  jnz     loc_1800119B4
0x180011923  test    rbx, rbx
0x180011926  jz      short loc_18001194B
0x180011928  mov     rax, [rbx]
0x18001192b  xor     r8d, r8d
0x18001192e  mov     rdx, rsi
0x180011931  mov     rcx, rbx
0x180011934  mov     rax, [rax+0A8h]
0x18001193b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011940  mov     r14d, eax
0x180011943  test    eax, eax
0x180011945  js      loc_180011AEB
0x18001194b  mov     rax, [rsi]
0x18001194e  lea     r8, [rbp+MaxCount]
0x180011952  lea     rdx, [rbp+String1]
0x180011956  mov     [rbp+String1], r12
0x18001195a  mov     rcx, rsi
0x18001195d  mov     dword ptr [rbp+MaxCount], r12d
0x180011961  mov     rax, [rax+70h]
0x180011965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196a  mov     r14d, eax
0x18001196d  test    eax, eax
0x18001196f  js      loc_180011B25
0x180011975  mov     rcx, [rbp+String1]; String1
0x180011979  test    rcx, rcx
0x18001197c  jz      loc_1800118D4
0x180011982  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180011986  inc     rdx
0x180011989  cmp     [rdi+rdx*2], r12w
0x18001198e  jnz     short loc_180011986
0x180011990  mov     r8d, dword ptr [rbp+MaxCount]; MaxCount
0x180011994  cmp     r8, rdx
0x180011997  jnz     loc_1800118D4
0x18001199d  mov     rdx, rdi; String2
0x1800119a0  call    wcsncmp_0
0x1800119a5  test    eax, eax
0x1800119a7  jnz     loc_1800118D4
0x1800119ad  xor     eax, eax
0x1800119af  jmp     loc_180011C67
0x1800119b4  test    r15, r15
0x1800119b7  jz      loc_180011A86
0x1800119bd  cmp     [rbp+arg_0], 0Fh
0x1800119c1  jnz     loc_180011A86
0x1800119c7  mov     rax, [rsi]
0x1800119ca  lea     r8, [rbp+MaxCount+4]
0x1800119ce  lea     rdx, [rbp+var_10]
0x1800119d2  mov     [rbp+var_10], r12
0x1800119d6  mov     rcx, rsi
0x1800119d9  mov     dword ptr [rbp+MaxCount+4], r12d
0x1800119dd  mov     rax, [rax+70h]
0x1800119e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119e6  mov     r14d, eax
0x1800119e9  test    eax, eax
0x1800119eb  js      loc_180011B9D
0x1800119f1  mov     rcx, [rbp+var_10]; String1
0x1800119f5  test    rcx, rcx
0x1800119f8  jz      short loc_180011A21
0x1800119fa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800119fe  inc     rdx
0x180011a01  cmp     [r15+rdx*2], r12w
0x180011a06  jnz     short loc_1800119FE
0x180011a08  mov     r8d, dword ptr [rbp+MaxCount+4]; MaxCount
0x180011a0c  cmp     r8, rdx
0x180011a0f  jnz     short loc_180011A21
0x180011a11  mov     rdx, r15; String2
0x180011a14  call    wcsncmp_0
0x180011a19  test    eax, eax
0x180011a1b  jz      loc_180011B5F
0x180011a21  test    rbx, rbx
0x180011a24  jz      loc_1800118D4
0x180011a2a  mov     rax, [rbx]
0x180011a2d  xor     r8d, r8d
0x180011a30  mov     rdx, rsi
0x180011a33  mov     rcx, rbx
0x180011a36  mov     rax, [rax+0A8h]
0x180011a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a42  mov     r14d, eax
0x180011a45  test    eax, eax
0x180011a47  jns     loc_1800118D4
0x180011a4d  mov     dword ptr [rsp+50h+var_28], eax
0x180011a51  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011a58  mov     ebx, 3
0x180011a5d  mov     [rsp+50h+var_30], 0B0h
0x180011a65  mov     ecx, ebx
0x180011a67  lea     r8, aFindnode; "FindNode"
0x180011a6e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011a75  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011a7a  lea     rdx, aFailedToWriteE; "    Failed to write end node shallow"
0x180011a81  jmp     loc_180011C09
0x180011a86  test    rbx, rbx
0x180011a89  jz      loc_1800118D4
0x180011a8f  mov     rax, [rbx]
0x180011a92  xor     r8d, r8d
0x180011a95  mov     rdx, rsi
0x180011a98  mov     rcx, rbx
0x180011a9b  mov     rax, [rax+0A8h]
0x180011aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aa7  mov     r14d, eax
0x180011aaa  test    eax, eax
0x180011aac  jns     loc_1800118D4
0x180011ab2  mov     dword ptr [rsp+50h+var_28], eax
0x180011ab6  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011abd  mov     ebx, 3
0x180011ac2  mov     [rsp+50h+var_30], 0B8h
0x180011aca  mov     ecx, ebx
0x180011acc  lea     r8, aFindnode; "FindNode"
0x180011ad3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011ada  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011adf  lea     rdx, aFailedToWriteO; "    Failed to write other node shallow"
0x180011ae6  jmp     loc_180011C09
0x180011aeb  mov     ebx, 3
0x180011af0  mov     dword ptr [rsp+50h+var_28], r14d
0x180011af5  mov     ecx, ebx
0x180011af7  mov     [rsp+50h+var_30], 86h
0x180011aff  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011b06  lea     r8, aFindnode; "FindNode"
0x180011b0d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011b14  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011b19  lea     rdx, aFailedToWriteE_3; "    Failed to write element node shallo"...
0x180011b20  jmp     loc_180011C09
0x180011b25  mov     ebx, 3
0x180011b2a  mov     dword ptr [rsp+50h+var_28], r14d
0x180011b2f  mov     ecx, ebx
0x180011b31  mov     [rsp+50h+var_30], 8Dh
0x180011b39  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011b40  lea     r8, aFindnode; "FindNode"
0x180011b47  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011b4e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011b53  lea     rdx, aFailedToGetEle; "    Failed to get element local name"
0x180011b5a  jmp     loc_180011C09
0x180011b5f  test    rdi, rdi
0x180011b62  jz      loc_1800119AD
0x180011b68  lea     rax, aNoMoreNodes; "No more nodes"
0x180011b6f  xor     ecx, ecx
0x180011b71  mov     [rsp+50h+var_28], rax
0x180011b76  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011b7d  lea     r8, aFindnode; "FindNode"
0x180011b84  mov     [rsp+50h+var_30], 0A6h
0x180011b8c  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x180011b93  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011b98  jmp     loc_180011C62
0x180011b9d  mov     ebx, 3
0x180011ba2  mov     dword ptr [rsp+50h+var_28], r14d
0x180011ba7  mov     ecx, ebx
0x180011ba9  mov     [rsp+50h+var_30], 9Dh
0x180011bb1  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011bb8  lea     r8, aFindnode; "FindNode"
0x180011bbf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011bc6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011bcb  lea     rdx, aFailedToGetEnd; "    Failed to get end node local name"
0x180011bd2  jmp     short loc_180011C09
0x180011bd4  mov     ebx, 3
0x180011bd9  mov     dword ptr [rsp+50h+var_28], r14d
0x180011bde  mov     ecx, ebx
0x180011be0  mov     [rsp+50h+var_30], 7Fh
0x180011be8  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011bef  lea     r8, aFindnode; "FindNode"
0x180011bf6  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011bfd  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011c02  lea     rdx, aFailedToReadNo; "    Failed to read node type"
0x180011c09  mov     ecx, ebx
0x180011c0b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011c10  mov     eax, r14d
0x180011c13  jmp     short loc_180011C67
0x180011c15  test    rdi, rdi
0x180011c18  jnz     short loc_180011C23
0x180011c1a  test    r15, r15
0x180011c1d  jz      loc_1800119AD
0x180011c23  mov     ebx, 3
0x180011c28  mov     dword ptr [rsp+50h+var_28], 80070490h
0x180011c30  mov     ecx, ebx
0x180011c32  mov     [rsp+50h+var_30], 0BFh
0x180011c3a  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011c41  lea     r8, aFindnode; "FindNode"
0x180011c48  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011c4f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011c54  lea     rdx, aNodeOrStopNode; "    Node or stop node was not found"
0x180011c5b  mov     ecx, ebx
0x180011c5d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011c62  mov     eax, 80070490h
0x180011c67  lea     r11, [rsp+50h+var_s0]
0x180011c6c  mov     rbx, [r11+38h]
0x180011c70  mov     rsi, [r11+40h]
0x180011c74  mov     rsp, r11
0x180011c77  pop     r15
0x180011c79  pop     r14
0x180011c7b  pop     r12
0x180011c7d  pop     rdi
0x180011c7e  pop     rbp
0x180011c7f  retn
```
