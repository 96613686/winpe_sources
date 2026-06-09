# CMapiOutOfProcHandler::CreateIStorageFromMessage(IMessage *,IStorage * *)

- ea: `0x18002777c`
- end: `0x180027a3b`
- name: `?CreateIStorageFromMessage@CMapiOutOfProcHandler@@CAJPEAUIMessage@@PEAPEAUIStorage@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(LPMAPIPROP lpMapiProp, struct IStorage **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027d40`
- `0x180027e20`

## callees

- `0x180005210`
- `0x180006270`
- `0x18001d404`
- `0x18002777c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002795e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002795e`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180027821`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180027821`
- `api-ms-win-core-com-l2-1-1!StgCreateStorageEx` at `0x1800277dc`
- `api-ms-win-core-com-l2-1-1!StgCreateStorageEx` at `0x1800277dc`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateBuffer` at `0x180027871`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateBuffer` at `0x1800278c4`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateMore` at `0x18002786a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateMore` at `0x1800278bd`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180027994`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180027863`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x1800278b6`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180027994`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIGetDefaultMalloc` at `0x1800277e4`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIGetDefaultMalloc` at `0x1800277e4`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180027974`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrGetOneProp` at `0x180027974`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrSetOneProp` at `0x180027988`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_HrSetOneProp` at `0x180027988`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgSession` at `0x18002780a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgSession` at `0x18002780a`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_CloseIMsgSession` at `0x1800279fc`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_CloseIMsgSession` at `0x1800279fc`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x18002787c`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x1800278cf`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x18002787c`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x1800278cf`

## string_xrefs

- `0x180027957`: `RTFHTML.dll`

## pseudocode

```c
__int64 __fastcall CMapiOutOfProcHandler::CreateIStorageFromMessage(LPMAPIPROP lpMapiProp, struct IStorage **a2)
{
  HRESULT Storage; // ebx
  IMalloc *v5; // rax
  IMalloc *v6; // rdi
  struct IStorage *v7; // rax
  LPSTORAGE pStg; // [rsp+60h] [rbp-19h] BYREF
  LPMESSAGE pMsg; // [rsp+68h] [rbp-11h] BYREF
  LPMSGSESS pMsgSess; // [rsp+70h] [rbp-9h] BYREF
  LPSPropValue pProp; // [rsp+78h] [rbp-1h] BYREF
  _DWORD v13[8]; // [rsp+80h] [rbp+7h] BYREF

  pStg = 0;
  Storage = StgCreateStorageEx(0, 0x4110002u, 5u, 0, 0, 0, &GUID_0000000b_0000_0000_c000_000000000046, (void **)&pStg);
  v5 = MAPIGetDefaultMalloc();
  v6 = v5;
  pMsgSess = 0;
  if ( v5 )
  {
    if ( Storage >= 0 )
    {
      Storage = OpenIMsgSession(v5, 0, &pMsgSess);
      if ( Storage >= 0 )
        Storage = WriteClassStg(pStg, &GUID_00020d0b_0000_0000_c000_000000000046);
    }
  }
  else
  {
    Storage = -2147024882;
  }
  pMsg = 0;
  if ( Storage >= 0 )
  {
    Storage = OpenIMsgOnIStg(
                pMsgSess,
                MAPIAllocateBuffer,
                MAPIAllocateMore,
                MAPIFreeBuffer,
                v6,
                0,
                pStg,
                0,
                0,
                0x80000000,
                &pMsg);
    if ( Storage == -2147221242 )
      Storage = OpenIMsgOnIStg(
                  pMsgSess,
                  MAPIAllocateBuffer,
                  MAPIAllocateMore,
                  MAPIFreeBuffer,
                  v6,
                  0,
                  pStg,
                  0,
                  0,
                  0,
                  &pMsg);
    if ( Storage >= 0 )
    {
      v13[0] = 6;
      v13[1] = 267649027;
      v13[2] = 268894211;
      v13[3] = 268828675;
      v13[4] = 268959775;
      v13[5] = 269484035;
      v13[6] = 269549571;
      Storage = ((__int64 (__fastcall *)(LPMAPIPROP, _QWORD, _QWORD, _DWORD *, _DWORD, _QWORD, GUID *, LPMESSAGE, _DWORD, _QWORD))lpMapiProp->lpVtbl->CopyTo)(
                  lpMapiProp,
                  0,
                  0,
                  v13,
                  0,
                  0,
                  &GUID_00020307_0000_0000_c000_000000000046,
                  pMsg,
                  0,
                  0);
      if ( Storage >= 0 )
      {
        LoadLibraryW(L"RTFHTML.dll");
        pProp = 0;
        Storage = HrGetOneProp(lpMapiProp, 0xE080003u, &pProp);
        if ( Storage >= 0 )
        {
          Storage = HrSetOneProp((LPMAPIPROP)pMsg, pProp);
          MAPIFreeBuffer(pProp);
          if ( Storage >= 0 )
          {
            ((void (__fastcall *)(LPMESSAGE, __int64))pMsg->lpVtbl->SaveChanges)(pMsg, 2);
            Storage = ((__int64 (__fastcall *)(LPSTORAGE, _QWORD))pStg->lpVtbl->Commit)(pStg, 0);
            if ( Storage >= 0 )
            {
              v7 = pStg;
              pStg = 0;
              *a2 = v7;
            }
          }
        }
      }
    }
  }
  if ( v6 )
    ((void (__fastcall *)(IMalloc *))v6->lpVtbl->Release)(v6);
  ATL::CComPtrBase<IPreviewHandlerFrame>::Release(&pMsg);
  if ( pMsgSess )
    CloseIMsgSession(pMsgSess);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pMsg);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pStg);
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x18002777c  mov     [rsp-8+arg_10], rbx
0x180027781  push    rbp
0x180027782  push    rsi
0x180027783  push    rdi
0x180027784  push    r14
0x180027786  push    r15
0x180027788  lea     rbp, [rsp-37h]
0x18002778d  sub     rsp, 0B0h
0x180027794  mov     rax, cs:__security_cookie
0x18002779b  xor     rax, rsp
0x18002779e  mov     [rbp+57h+var_30], rax
0x1800277a2  mov     r14, rdx
0x1800277a5  mov     rsi, rcx
0x1800277a8  xor     r15d, r15d
0x1800277ab  mov     [rbp+57h+pStg], r15
0x1800277af  lea     rax, [rbp+57h+pStg]
0x1800277b3  mov     [rsp+0D0h+ppObjectOpen], rax; ppObjectOpen
0x1800277b8  lea     rax, _GUID_0000000b_0000_0000_c000_000000000046
0x1800277bf  mov     [rsp+0D0h+riid], rax; riid
0x1800277c4  mov     [rsp+0D0h+pSecurityDescriptor], r15; pSecurityDescriptor
0x1800277c9  mov     [rsp+0D0h+pStgOptions], r15; pStgOptions
0x1800277ce  xor     r9d, r9d; grfAttrs
0x1800277d1  mov     edx, 4110002h; grfMode
0x1800277d6  xor     ecx, ecx; pwcsName
0x1800277d8  lea     r8d, [r15+5]; stgfmt
0x1800277dc  call    cs:__imp_StgCreateStorageEx
0x1800277e2  mov     ebx, eax
0x1800277e4  call    cs:__imp_MAPIGetDefaultMalloc
0x1800277ea  mov     rdi, rax
0x1800277ed  mov     [rbp+57h+pMsgSess], r15
0x1800277f1  test    rax, rax
0x1800277f4  jnz     short loc_1800277FD
0x1800277f6  mov     ebx, 8007000Eh
0x1800277fb  jmp     short loc_180027829
0x1800277fd  test    ebx, ebx
0x1800277ff  js      short loc_180027829
0x180027801  lea     r8, [rbp+57h+pMsgSess]; lppMsgSess
0x180027805  xor     edx, edx; ulFlags
0x180027807  mov     rcx, rdi; lpMalloc
0x18002780a  call    cs:__imp_OpenIMsgSession
0x180027810  mov     ebx, eax
0x180027812  test    eax, eax
0x180027814  js      short loc_180027829
0x180027816  lea     rdx, _GUID_00020d0b_0000_0000_c000_000000000046; rclsid
0x18002781d  mov     rcx, [rbp+57h+pStg]; pStg
0x180027821  call    cs:__imp_WriteClassStg
0x180027827  mov     ebx, eax
0x180027829  mov     [rbp+57h+pMsg], r15
0x18002782d  test    ebx, ebx
0x18002782f  js      loc_1800279D6
0x180027835  mov     rax, [rbp+57h+pStg]
0x180027839  lea     rcx, [rbp+57h+pMsg]
0x18002783d  mov     [rsp+0D0h+lppMsg], rcx; lppMsg
0x180027842  mov     [rsp+0D0h+ulFlags], 80000000h; ulFlags
0x18002784a  mov     [rsp+0D0h+ulCallerData], r15d; ulCallerData
0x18002784f  mov     [rsp+0D0h+ppObjectOpen], r15; lpfMsgCallRelease
0x180027854  mov     [rsp+0D0h+riid], rax; lpStg
0x180027859  mov     [rsp+0D0h+pSecurityDescriptor], r15; lpMapiSup
0x18002785e  mov     [rsp+0D0h+pStgOptions], rdi; lpMalloc
0x180027863  mov     r9, cs:__imp_MAPIFreeBuffer; lpFreeBuffer
0x18002786a  mov     r8, cs:__imp_MAPIAllocateMore; lpAllocateMore
0x180027871  mov     rdx, cs:__imp_MAPIAllocateBuffer; lpAllocateBuffer
0x180027878  mov     rcx, [rbp+57h+pMsgSess]; lpMsgSess
0x18002787c  call    cs:__imp_OpenIMsgOnIStg
0x180027882  mov     ebx, eax
0x180027884  cmp     eax, 80040106h
0x180027889  jnz     short loc_1800278D7
0x18002788b  mov     rax, [rbp+57h+pStg]
0x18002788f  lea     rcx, [rbp+57h+pMsg]
0x180027893  mov     [rsp+0D0h+lppMsg], rcx; lppMsg
0x180027898  mov     [rsp+0D0h+ulFlags], r15d; ulFlags
0x18002789d  mov     [rsp+0D0h+ulCallerData], r15d; ulCallerData
0x1800278a2  mov     [rsp+0D0h+ppObjectOpen], r15; lpfMsgCallRelease
0x1800278a7  mov     [rsp+0D0h+riid], rax; lpStg
0x1800278ac  mov     [rsp+0D0h+pSecurityDescriptor], r15; lpMapiSup
0x1800278b1  mov     [rsp+0D0h+pStgOptions], rdi; lpMalloc
0x1800278b6  mov     r9, cs:__imp_MAPIFreeBuffer; lpFreeBuffer
0x1800278bd  mov     r8, cs:__imp_MAPIAllocateMore; lpAllocateMore
0x1800278c4  mov     rdx, cs:__imp_MAPIAllocateBuffer; lpAllocateBuffer
0x1800278cb  mov     rcx, [rbp+57h+pMsgSess]; lpMsgSess
0x1800278cf  call    cs:__imp_OpenIMsgOnIStg
0x1800278d5  mov     ebx, eax
0x1800278d7  test    ebx, ebx
0x1800278d9  js      loc_1800279D6
0x1800278df  mov     [rbp+57h+var_50], 6
0x1800278e6  mov     [rbp+57h+var_4C], 0FF40003h
0x1800278ed  mov     [rbp+57h+var_48], 10070003h
0x1800278f4  mov     [rbp+57h+var_44], 10060003h
0x1800278fb  mov     [rbp+57h+var_40], 1008001Fh
0x180027902  mov     [rbp+57h+var_3C], 10100003h
0x180027909  mov     [rbp+57h+var_38], 10110003h
0x180027910  mov     rcx, [rbp+57h+pMsg]
0x180027914  mov     rax, [rsi]
0x180027917  mov     qword ptr [rsp+0D0h+ulFlags], r15
0x18002791c  mov     [rsp+0D0h+ulCallerData], r15d
0x180027921  mov     [rsp+0D0h+ppObjectOpen], rcx
0x180027926  lea     rcx, _GUID_00020307_0000_0000_c000_000000000046
0x18002792d  mov     [rsp+0D0h+riid], rcx
0x180027932  mov     [rsp+0D0h+pSecurityDescriptor], r15
0x180027937  mov     dword ptr [rsp+0D0h+pStgOptions], r15d
0x18002793c  lea     r9, [rbp+57h+var_50]
0x180027940  xor     r8d, r8d
0x180027943  xor     edx, edx
0x180027945  mov     rcx, rsi
0x180027948  mov     rax, [rax+50h]
0x18002794c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027951  mov     ebx, eax
0x180027953  test    eax, eax
0x180027955  js      short loc_1800279D6
0x180027957  lea     rcx, aRtfhtmlDll; "RTFHTML.dll"
0x18002795e  call    cs:__imp_LoadLibraryW
0x180027964  mov     [rbp+57h+pProp], r15
0x180027968  lea     r8, [rbp+57h+pProp]; lppProp
0x18002796c  mov     edx, 0E080003h; ulPropTag
0x180027971  mov     rcx, rsi; lpMapiProp
0x180027974  call    cs:__imp_HrGetOneProp
0x18002797a  mov     ebx, eax
0x18002797c  test    eax, eax
0x18002797e  js      short loc_1800279D6
0x180027980  mov     rdx, [rbp+57h+pProp]; lpProp
0x180027984  mov     rcx, [rbp+57h+pMsg]; lpMapiProp
0x180027988  call    cs:__imp_HrSetOneProp
0x18002798e  mov     ebx, eax
0x180027990  mov     rcx, [rbp+57h+pProp]; pv
0x180027994  call    cs:__imp_MAPIFreeBuffer
0x18002799a  test    ebx, ebx
0x18002799c  js      short loc_1800279D6
0x18002799e  mov     rcx, [rbp+57h+pMsg]
0x1800279a2  mov     rax, [rcx]
0x1800279a5  mov     edx, 2
0x1800279aa  mov     rax, [rax+20h]
0x1800279ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279b3  mov     rcx, [rbp+57h+pStg]
0x1800279b7  mov     rax, [rcx]
0x1800279ba  xor     edx, edx
0x1800279bc  mov     rax, [rax+48h]
0x1800279c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279c5  mov     ebx, eax
0x1800279c7  test    eax, eax
0x1800279c9  js      short loc_1800279D6
0x1800279cb  mov     rax, [rbp+57h+pStg]
0x1800279cf  mov     [rbp+57h+pStg], r15
0x1800279d3  mov     [r14], rax
0x1800279d6  test    rdi, rdi
0x1800279d9  jz      short loc_1800279EA
0x1800279db  mov     rax, [rdi]
0x1800279de  mov     rcx, rdi
0x1800279e1  mov     rax, [rax+10h]
0x1800279e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ea  lea     rcx, [rbp+57h+pMsg]
0x1800279ee  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x1800279f3  mov     rcx, [rbp+57h+pMsgSess]; lpMsgSess
0x1800279f7  test    rcx, rcx
0x1800279fa  jz      short loc_180027A03
0x1800279fc  call    cs:__imp_CloseIMsgSession
0x180027a02  nop
0x180027a03  lea     rcx, [rbp+57h+pMsg]
0x180027a07  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180027a0c  nop
0x180027a0d  lea     rcx, [rbp+57h+pStg]
0x180027a11  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180027a16  mov     eax, ebx
0x180027a18  mov     rcx, [rbp+57h+var_30]
0x180027a1c  xor     rcx, rsp; StackCookie
0x180027a1f  call    __security_check_cookie
0x180027a24  mov     rbx, [rsp+0D0h+arg_10]
0x180027a2c  add     rsp, 0B0h
0x180027a33  pop     r15
0x180027a35  pop     r14
0x180027a37  pop     rdi
0x180027a38  pop     rsi
0x180027a39  pop     rbp
0x180027a3a  retn
```
