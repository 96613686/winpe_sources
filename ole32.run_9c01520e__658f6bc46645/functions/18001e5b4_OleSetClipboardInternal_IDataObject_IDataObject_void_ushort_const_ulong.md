# OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)

- ea: `0x18001e5b4`
- end: `0x18001e743`
- name: `?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z`
- size: `399`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, IDataObject *pSourceDataObject, void **ppDataObjectMTAAddress, const wchar_t *pszCallerPackageFullName, unsigned int pid)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d410`
- `0x18001dbc0`

## callees

- `0x18000be3c`
- `0x18001217c`
- `0x18001ad50`
- `0x18001b084`
- `0x18001e5b4`
- `0x18001ecc0`
- `0x18001f3c0`
- `0x180088044`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18001e60b`
- `KERNELBASE!Sleep` at `0x18001e60b`
- `USER32!OpenClipboard` at `0x18001e5f9`
- `USER32!OpenClipboard` at `0x18001e61a`
- `USER32!OpenClipboard` at `0x18001e5f9`
- `USER32!OpenClipboard` at `0x18001e61a`
- `USER32!EmptyClipboard` at `0x18001e655`
- `USER32!EmptyClipboard` at `0x18001e655`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001e636`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001e636`

## string_xrefs

- `0x18001e677`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18001e6ad`: `com\ole32\ole232\clipbrd\clipapi.cpp`

## pseudocode

```c
__int64 __fastcall OleSetClipboardInternal(
        IDataObject *pDataObject,
        IDataObject *pSourceDataObject,
        void **ppDataObjectMTAAddress,
        const wchar_t *pszCallerPackageFullName,
        unsigned int pid)
{
  HWND PrivateClipboardWindow; // rax
  HWND__ *v10; // rbx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // edx
  HRESULT v14; // r9d
  HRESULT v15; // edi
  unsigned int v16; // edx
  int v17; // eax
  int v18; // eax
  OleClipboardLock clipLock; // [rsp+20h] [rbp-18h] BYREF
  void *retaddr; // [rsp+38h] [rbp+0h]

  clipLock.m_locked = 0;
  PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
  v10 = PrivateClipboardWindow;
  if ( PrivateClipboardWindow )
  {
    if ( !OpenClipboard(PrivateClipboardWindow) )
    {
      Sleep(0);
      if ( !OpenClipboard(v10) )
      {
        v11 = -2147221040;
        goto LABEL_6;
      }
    }
    if ( (unsigned int)EdpGetIsManaged(v12) )
      EdpInlSetCurrentThreadPolicyEvaluation(1);
    clipLock.m_locked = 1;
    if ( !EmptyClipboard() )
    {
      v11 = -2147221039;
      v13 = 3741;
      goto LABEL_11;
    }
    if ( pDataObject )
    {
      v15 = SetClipboardOwnerWindowProperty(v10, pszCallerPackageFullName, pid);
      if ( v15 < 0 )
      {
        v16 = 3748;
LABEL_16:
        wil::details::in1diag3::Return_Hr(retaddr, v16, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v15);
        v11 = v15;
        goto LABEL_24;
      }
      v15 = SetClipboardDataObject(v10, pDataObject, pSourceDataObject, ppDataObjectMTAAddress);
      if ( v15 < 0 )
      {
        v16 = 3749;
        goto LABEL_16;
      }
      v17 = SetClipboardFormats(v10, pDataObject);
      v11 = v17;
      if ( v17 < 0 )
      {
        v14 = v17;
        v13 = 3750;
        goto LABEL_12;
      }
    }
    v18 = OleClipboardLock::Release(&clipLock);
    v11 = v18;
    if ( v18 >= 0 )
    {
      v11 = 0;
      goto LABEL_24;
    }
    v14 = v18;
    v13 = 3753;
    goto LABEL_12;
  }
  v11 = -2147467259;
LABEL_6:
  v13 = 3731;
LABEL_11:
  v14 = v11;
LABEL_12:
  wil::details::in1diag3::Return_Hr(retaddr, v13, "com\\ole32\\ole232\\clipbrd\\clipapi.cpp", v14);
LABEL_24:
  OleClipboardLock::Release(&clipLock);
  return v11;
}

```

## disassembly

```asm
0x18001e5b4  mov     rax, rsp
0x18001e5b7  mov     [rax+8], rbx
0x18001e5bb  mov     [rax+10h], rbp
0x18001e5bf  mov     [rax+18h], rsi
0x18001e5c3  mov     [rax+20h], rdi
0x18001e5c7  push    r14
0x18001e5c9  sub     rsp, 30h
0x18001e5cd  mov     rsi, pDataObject
0x18001e5d0  mov     byte ptr [rax-18h], 0
0x18001e5d4  mov     ecx, 1; fFlags
0x18001e5d9  mov     rdi, pszCallerPackageFullName
0x18001e5dc  mov     rbp, ppDataObjectMTAAddress
0x18001e5df  mov     r14, pSourceDataObject
0x18001e5e2  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18001e5e7  mov     rbx, rax
0x18001e5ea  test    rax, rax
0x18001e5ed  jnz     short loc_18001E5F6
0x18001e5ef  mov     ebx, 80004005h
0x18001e5f4  jmp     short loc_18001E62F
0x18001e5f6  mov     pDataObject, rbx; hWndNewOwner
0x18001e5f9  call    cs:__imp_OpenClipboard
0x18001e600  nop     dword ptr [rax+rax+00h]
0x18001e605  test    eax, eax
0x18001e607  jnz     short loc_18001E636
0x18001e609  xor     ecx, ecx; dwMilliseconds
0x18001e60b  call    cs:__imp_Sleep
0x18001e612  nop     dword ptr [rax+rax+00h]
0x18001e617  mov     pDataObject, rbx; hWndNewOwner
0x18001e61a  call    cs:__imp_OpenClipboard
0x18001e621  nop     dword ptr [rax+rax+00h]
0x18001e626  test    eax, eax
0x18001e628  jnz     short loc_18001E636
0x18001e62a  mov     ebx, 800401D0h
0x18001e62f  mov     edx, 0E93h
0x18001e634  jmp     short loc_18001E66F
0x18001e636  call    cs:__imp_EdpGetIsManaged
0x18001e63d  nop     dword ptr [rax+rax+00h]
0x18001e642  test    eax, eax
0x18001e644  jz      short loc_18001E650
0x18001e646  mov     ecx, 1; EvaluationDisabled
0x18001e64b  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18001e650  mov     [rsp+38h+clipLock.m_locked], 1
0x18001e655  call    cs:__imp_EmptyClipboard
0x18001e65c  nop     dword ptr [rax+rax+00h]
0x18001e661  test    eax, eax
0x18001e663  jnz     short loc_18001E688
0x18001e665  mov     ebx, 800401D1h
0x18001e66a  mov     edx, 0E9Dh; lineNumber
0x18001e66f  mov     r9d, ebx; hr
0x18001e672  mov     pDataObject, [rsp+38h]; callerReturnAddress
0x18001e677  lea     ppDataObjectMTAAddress, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18001e67e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e683  jmp     loc_18001E71B
0x18001e688  test    rsi, rsi
0x18001e68b  jz      short loc_18001E6FC
0x18001e68d  mov     r8d, [rsp+38h+arg_20]; pid
0x18001e692  mov     pSourceDataObject, rdi; pszPackageFulllName
0x18001e695  mov     pDataObject, rbx; hClipWnd
0x18001e698  call    ?SetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEBGK@Z; SetClipboardOwnerWindowProperty(HWND__ *,ushort const *,ulong)
0x18001e69d  mov     edi, eax
0x18001e69f  test    eax, eax
0x18001e6a1  jns     short loc_18001E6C0
0x18001e6a3  mov     edx, 0EA4h; lineNumber
0x18001e6a8  mov     pDataObject, [rsp+38h]; callerReturnAddress
0x18001e6ad  lea     ppDataObjectMTAAddress, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18001e6b4  mov     r9d, edi; hr
0x18001e6b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6bc  mov     ebx, edi
0x18001e6be  jmp     short loc_18001E71B
0x18001e6c0  mov     pszCallerPackageFullName, rbp; ppDataObjectMTAAddress
0x18001e6c3  mov     ppDataObjectMTAAddress, r14; pSourceDataObject
0x18001e6c6  mov     pSourceDataObject, rsi; pDataObject
0x18001e6c9  mov     pDataObject, rbx; hClipWnd
0x18001e6cc  call    ?SetClipboardDataObject@@YAJPEAUHWND__@@PEAUIDataObject@@1PEAPEAX@Z; SetClipboardDataObject(HWND__ *,IDataObject *,IDataObject *,void * *)
0x18001e6d1  mov     edi, eax
0x18001e6d3  test    eax, eax
0x18001e6d5  jns     short loc_18001E6DE
0x18001e6d7  mov     edx, 0EA5h
0x18001e6dc  jmp     short loc_18001E6A8
0x18001e6de  mov     pSourceDataObject, rsi; pDataObj
0x18001e6e1  mov     pDataObject, rbx; hClipWnd
0x18001e6e4  call    ?SetClipboardFormats@@YAJPEAUHWND__@@PEAUIDataObject@@@Z; SetClipboardFormats(HWND__ *,IDataObject *)
0x18001e6e9  mov     ebx, eax
0x18001e6eb  test    eax, eax
0x18001e6ed  jns     short loc_18001E6FC
0x18001e6ef  mov     r9d, eax
0x18001e6f2  mov     edx, 0EA6h
0x18001e6f7  jmp     loc_18001E672
0x18001e6fc  lea     pDataObject, [rsp+38h+clipLock]; this
0x18001e701  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18001e706  mov     ebx, eax
0x18001e708  test    eax, eax
0x18001e70a  jns     short loc_18001E719
0x18001e70c  mov     r9d, eax
0x18001e70f  mov     edx, 0EA9h
0x18001e714  jmp     loc_18001E672
0x18001e719  xor     ebx, ebx
0x18001e71b  lea     pDataObject, [rsp+38h+clipLock]; this
0x18001e720  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18001e725  mov     rbp, [rsp+38h+arg_8]
0x18001e72a  mov     eax, ebx
0x18001e72c  mov     rbx, [rsp+38h+arg_0]
0x18001e731  mov     rsi, [rsp+38h+arg_10]
0x18001e736  mov     rdi, [rsp+38h+arg_18]
0x18001e73b  add     rsp, 30h
0x18001e73f  pop     r14
0x18001e741  retn
```
