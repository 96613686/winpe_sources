# CMapiOutOfProcHandler::GetStreamByUrl(wchar_t const *,IStream * *)

- ea: `0x180027e20`
- end: `0x180028042`
- name: `?GetStreamByUrl@CMapiOutOfProcHandler@@UEAAJPEB_WPEAPEAUIStream@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(CMapiOutOfProcHandler *this, const wchar_t *, struct IStream **)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005210`
- `0x180006270`
- `0x180006dcc`
- `0x180018808`
- `0x180018b34`
- `0x1800275b4`
- `0x18002777c`
- `0x180027e20`
- `0x180028254`
- `0x180028374`
- `0x1800314c0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fef`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027f43`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180027f43`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180027fe3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180027fe3`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180027ed8`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180027ed8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMapiOutOfProcHandler::GetStreamByUrl(
        CMapiOutOfProcHandler *this,
        const wchar_t *a2,
        struct IStream **a3)
{
  HRESULT MapiManager; // edi
  CMapiOutOfProcHandler *v6; // rcx
  CMapiOutOfProcHandler *v7; // rcx
  int v8; // r9d
  struct IMessage *v9; // r8
  struct IMAPIProp *v10; // rbx
  __int64 v11; // rcx
  struct IStorage *v12; // rbx
  LPMAPIPROP lpMapiProp; // [rsp+30h] [rbp-D0h] BYREF
  struct IStorage *v15; // [rsp+38h] [rbp-C8h] BYREF
  struct CMapiManager *v16; // [rsp+40h] [rbp-C0h] BYREF
  LPSPropValue pProp; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[72]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+98h] [rbp-68h]
  LPCWSTR pszFile[10]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR String2[16]; // [rsp+100h] [rbp+0h] BYREF

  *a3 = 0;
  v16 = 0;
  MapiManager = CMapiManager::GetMapiManager(&v16, 1u);
  if ( MapiManager >= 0 )
  {
    CMapiUrl::CMapiUrl((CMapiUrl *)v18, a2);
    lpMapiProp = 0;
    MapiManager = CMapiOutOfProcHandler::_GetMessage(v6, (struct CMapiUrl *)v18, v16, (struct IMessage **)&lpMapiProp);
    if ( MapiManager >= 0 )
    {
      if ( *(int *)(v19 - 16) > 0 )
      {
        v8 = 0;
        v9 = (struct IMessage *)lpMapiProp;
LABEL_11:
        MapiManager = CMapiOutOfProcHandler::_GetAttachmentStream(v7, (struct CMapiUrl *)v18, v9, v8, a3);
        goto LABEL_18;
      }
      pProp = 0;
      v10 = lpMapiProp;
      MapiManager = HrGetOneProp(lpMapiProp, 0x1A001Eu, &pProp);
      if ( MapiManager >= 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_BYTE *)(pProp->Value.cur.int64 + v11) );
        strcpy(String2, "IPM.Document.");
        if ( (unsigned int)v11 < 0xD || CompareStringA(0x7Fu, 1u, pProp->Value.lpszA, 13, String2, 13) != 2 )
        {
          v15 = 0;
          MapiManager = CMapiOutOfProcHandler::CreateIStorageFromMessage(v10, &v15);
          if ( MapiManager >= 0 )
          {
            v12 = v15;
            if ( v15 )
            {
              memset_0(pszFile, 0, sizeof(pszFile));
              MapiManager = ((__int64 (__fastcall *)(struct IStorage *, LPCWSTR *, _QWORD))v12->lpVtbl->Stat)(
                              v12,
                              pszFile,
                              0);
              if ( MapiManager >= 0 )
              {
                MapiManager = SHCreateStreamOnFileEx(pszFile[0], 0x4000040u, 0, 0, 0, a3);
                CoTaskMemFree((LPVOID)pszFile[0]);
              }
            }
            else
            {
              MapiManager = -2147024894;
            }
          }
          ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v15);
          goto LABEL_18;
        }
        v8 = 1;
        v9 = (struct IMessage *)v10;
        goto LABEL_11;
      }
    }
LABEL_18:
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&lpMapiProp);
    CMapiUrl::~CMapiUrl((CMapiUrl *)v18);
  }
  MapiManagerHelper::~MapiManagerHelper((MapiManagerHelper *)&v16);
  return (unsigned int)MapiManager;
}

```

## disassembly

```asm
0x180027e20  mov     [rsp-8+arg_0], rbx
0x180027e25  push    rbp
0x180027e26  push    rsi
0x180027e27  push    rdi
0x180027e28  lea     rbp, [rsp-20h]
0x180027e2d  sub     rsp, 120h
0x180027e34  mov     rax, cs:__security_cookie
0x180027e3b  xor     rax, rsp
0x180027e3e  mov     [rbp+30h+var_20], rax
0x180027e42  mov     rsi, r8
0x180027e45  mov     rbx, rdx
0x180027e48  mov     qword ptr [r8], 0
0x180027e4f  mov     [rsp+130h+var_F0], 0
0x180027e58  mov     edx, 1; unsigned int
0x180027e5d  lea     rcx, [rsp+130h+var_F0]; struct CMapiManager **
0x180027e62  call    ?GetMapiManager@CMapiManager@@SAJPEAPEAV1@K@Z; CMapiManager::GetMapiManager(CMapiManager * *,ulong)
0x180027e67  mov     edi, eax
0x180027e69  test    eax, eax
0x180027e6b  js      loc_180028017
0x180027e71  mov     rdx, rbx; wchar_t *
0x180027e74  lea     rcx, [rsp+130h+var_E0]; this
0x180027e79  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x180027e7e  nop
0x180027e7f  mov     [rsp+130h+lpMapiProp], 0
0x180027e88  lea     r9, [rsp+130h+lpMapiProp]; struct IMessage **
0x180027e8d  mov     r8, [rsp+130h+var_F0]; struct CMapiManager *
0x180027e92  lea     rdx, [rsp+130h+var_E0]; struct CMapiUrl *
0x180027e97  call    ?_GetMessage@CMapiOutOfProcHandler@@AEAAJPEAVCMapiUrl@@PEAVCMapiManager@@PEAPEAUIMessage@@@Z; CMapiOutOfProcHandler::_GetMessage(CMapiUrl *,CMapiManager *,IMessage * *)
0x180027e9c  mov     edi, eax
0x180027e9e  test    eax, eax
0x180027ea0  js      loc_180028001
0x180027ea6  mov     rax, [rbp+30h+var_98]
0x180027eaa  cmp     dword ptr [rax-10h], 0
0x180027eae  jle     short loc_180027EBD
0x180027eb0  xor     r9d, r9d
0x180027eb3  mov     r8, [rsp+130h+lpMapiProp]
0x180027eb8  jmp     loc_180027F55
0x180027ebd  mov     [rsp+130h+pProp], 0
0x180027ec6  lea     r8, [rsp+130h+pProp]; lppProp
0x180027ecb  mov     edx, 1A001Eh; ulPropTag
0x180027ed0  mov     rbx, [rsp+130h+lpMapiProp]
0x180027ed5  mov     rcx, rbx; lpMapiProp
0x180027ed8  call    cs:__imp_HrGetOneProp
0x180027ede  mov     edi, eax
0x180027ee0  test    eax, eax
0x180027ee2  js      loc_180028001
0x180027ee8  mov     r8, [rsp+130h+pProp]
0x180027eed  mov     rax, [r8+8]
0x180027ef1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180027ef5  inc     rcx
0x180027ef8  cmp     byte ptr [rax+rcx], 0
0x180027efc  jnz     short loc_180027EF5
0x180027efe  movsd   xmm0, qword ptr cs:aIpmDocument_0; "IPM.Document."
0x180027f06  movsd   qword ptr [rbp+30h+String2], xmm0
0x180027f0b  mov     eax, dword ptr cs:aIpmDocument_0+8; "ment."
0x180027f11  mov     [rbp+30h+var_28], eax
0x180027f14  movzx   eax, word ptr cs:aIpmDocument_0+0Ch; "."
0x180027f1b  mov     [rbp+30h+var_24], ax
0x180027f1f  mov     r9d, 0Dh; cchCount1
0x180027f25  cmp     ecx, r9d
0x180027f28  jb      short loc_180027F6B
0x180027f2a  mov     [rsp+130h+cchCount2], r9d; cchCount2
0x180027f2f  lea     rax, [rbp+30h+String2]
0x180027f33  mov     [rsp+130h+lpString2], rax; lpString2
0x180027f38  mov     r8, [r8+8]; lpString1
0x180027f3c  lea     edx, [r9-0Ch]; dwCmpFlags
0x180027f40  lea     ecx, [rdx+7Eh]; Locale
0x180027f43  call    cs:__imp_CompareStringA
0x180027f49  cmp     eax, 2
0x180027f4c  jnz     short loc_180027F6B
0x180027f4e  lea     r9d, [rax-1]; int
0x180027f52  mov     r8, rbx; struct IMessage *
0x180027f55  mov     [rsp+130h+lpString2], rsi; struct IStream **
0x180027f5a  lea     rdx, [rsp+130h+var_E0]; struct CMapiUrl *
0x180027f5f  call    ?_GetAttachmentStream@CMapiOutOfProcHandler@@AEAAJPEAVCMapiUrl@@PEAUIMessage@@HPEAPEAUIStream@@@Z; CMapiOutOfProcHandler::_GetAttachmentStream(CMapiUrl *,IMessage *,int,IStream * *)
0x180027f64  mov     edi, eax
0x180027f66  jmp     loc_180028001
0x180027f6b  mov     [rsp+130h+var_F8], 0
0x180027f74  lea     rdx, [rsp+130h+var_F8]; struct IStorage **
0x180027f79  mov     rcx, rbx; lpMapiProp
0x180027f7c  call    ?CreateIStorageFromMessage@CMapiOutOfProcHandler@@CAJPEAUIMessage@@PEAPEAUIStorage@@@Z; CMapiOutOfProcHandler::CreateIStorageFromMessage(IMessage *,IStorage * *)
0x180027f81  mov     edi, eax
0x180027f83  test    eax, eax
0x180027f85  js      short loc_180027FF6
0x180027f87  mov     rbx, [rsp+130h+var_F8]
0x180027f8c  test    rbx, rbx
0x180027f8f  jnz     short loc_180027F98
0x180027f91  mov     edi, 80070002h
0x180027f96  jmp     short loc_180027FF6
0x180027f98  xor     edx, edx; Val
0x180027f9a  lea     r8d, [rdx+50h]; Size
0x180027f9e  lea     rcx, [rbp+30h+pszFile]; void *
0x180027fa2  call    memset_0
0x180027fa7  mov     rax, [rbx]
0x180027faa  xor     r8d, r8d
0x180027fad  lea     rdx, [rbp+30h+pszFile]
0x180027fb1  mov     rcx, rbx
0x180027fb4  mov     rax, [rax+88h]
0x180027fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fc0  mov     edi, eax
0x180027fc2  test    eax, eax
0x180027fc4  js      short loc_180027FF6
0x180027fc6  mov     qword ptr [rsp+130h+cchCount2], rsi; ppstm
0x180027fcb  mov     [rsp+130h+lpString2], 0; pstmTemplate
0x180027fd4  xor     r9d, r9d; fCreate
0x180027fd7  xor     r8d, r8d; dwAttributes
0x180027fda  mov     edx, 4000040h; grfMode
0x180027fdf  mov     rcx, [rbp+30h+pszFile]; pszFile
0x180027fe3  call    cs:__imp_SHCreateStreamOnFileEx
0x180027fe9  mov     edi, eax
0x180027feb  mov     rcx, [rbp+30h+pszFile]; pv
0x180027fef  call    cs:__imp_CoTaskMemFree
0x180027ff5  nop
0x180027ff6  lea     rcx, [rsp+130h+var_F8]
0x180027ffb  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180028000  nop
0x180028001  lea     rcx, [rsp+130h+lpMapiProp]
0x180028006  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002800b  nop
0x18002800c  lea     rcx, [rsp+130h+var_E0]; this
0x180028011  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x180028016  nop
0x180028017  lea     rcx, [rsp+130h+var_F0]; this
0x18002801c  call    ??1MapiManagerHelper@@QEAA@XZ; MapiManagerHelper::~MapiManagerHelper(void)
0x180028021  mov     eax, edi
0x180028023  mov     rcx, [rbp+30h+var_20]
0x180028027  xor     rcx, rsp; StackCookie
0x18002802a  call    __security_check_cookie
0x18002802f  mov     rbx, [rsp+130h+arg_0]
0x180028037  add     rsp, 120h
0x18002803e  pop     rdi
0x18002803f  pop     rsi
0x180028040  pop     rbp
0x180028041  retn
```
