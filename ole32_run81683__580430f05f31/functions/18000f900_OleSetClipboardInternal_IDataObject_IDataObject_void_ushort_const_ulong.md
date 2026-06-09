# OleSetClipboardInternal(IDataObject *,IDataObject *,void * *,ushort const *,ulong)

- ea: `0x18000f900`
- end: `0x18000fa56`
- name: `?OleSetClipboardInternal@@YAJPEAUIDataObject@@0PEAPEAXPEBGK@Z`
- size: `342`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, IDataObject *pSourceDataObject, void **ppDataObjectMTAAddress, const wchar_t *pszCallerPackageFullName, unsigned int pid)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104b0`
- `0x180032ee0`

## callees

- `0x18000d38c`
- `0x18000ebc8`
- `0x18000f900`
- `0x1800110e0`
- `0x180011330`
- `0x180011958`
- `0x1800185ec`
- `0x1800405d4`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000f944`
- `KERNELBASE!Sleep` at `0x18000f944`
- `USER32!OpenClipboard` at `0x18000f938`
- `USER32!OpenClipboard` at `0x18000f94d`
- `USER32!OpenClipboard` at `0x18000f938`
- `USER32!OpenClipboard` at `0x18000f94d`
- `USER32!EmptyClipboard` at `0x18000f97c`
- `USER32!EmptyClipboard` at `0x18000f97c`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000f963`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000f963`

## string_xrefs

- `0x18000f998`: `com\ole32\ole232\clipbrd\clipapi.cpp`
- `0x18000f9d1`: `com\ole32\ole232\clipbrd\clipapi.cpp`

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
  OleClipboardLock clipLock; // [rsp+20h] [rbp-38h] BYREF
  void *retaddr; // [rsp+58h] [rbp+0h]

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
0x18000f900  push    rbx
0x18000f902  push    rbp
0x18000f903  push    rsi
0x18000f904  push    rdi
0x18000f905  push    r14
0x18000f907  sub     rsp, 30h
0x18000f90b  mov     rsi, pDataObject
0x18000f90e  mov     [rsp+58h+clipLock.m_locked], 0
0x18000f913  mov     ecx, 1; fFlags
0x18000f918  mov     rdi, pszCallerPackageFullName
0x18000f91b  mov     rbp, ppDataObjectMTAAddress
0x18000f91e  mov     r14, pSourceDataObject
0x18000f921  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000f926  mov     rbx, rax
0x18000f929  test    rax, rax
0x18000f92c  jnz     short loc_18000F935
0x18000f92e  mov     ebx, 80004005h
0x18000f933  jmp     short loc_18000F95C
0x18000f935  mov     pDataObject, rbx; hWndNewOwner
0x18000f938  call    cs:__imp_OpenClipboard
0x18000f93e  test    eax, eax
0x18000f940  jnz     short loc_18000F963
0x18000f942  xor     ecx, ecx; dwMilliseconds
0x18000f944  call    cs:__imp_Sleep
0x18000f94a  mov     pDataObject, rbx; hWndNewOwner
0x18000f94d  call    cs:__imp_OpenClipboard
0x18000f953  test    eax, eax
0x18000f955  jnz     short loc_18000F963
0x18000f957  mov     ebx, 800401D0h
0x18000f95c  mov     edx, 0E93h
0x18000f961  jmp     short loc_18000F990
0x18000f963  call    cs:__imp_EdpGetIsManaged
0x18000f969  test    eax, eax
0x18000f96b  jz      short loc_18000F977
0x18000f96d  mov     ecx, 1; EvaluationDisabled
0x18000f972  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000f977  mov     [rsp+58h+clipLock.m_locked], 1
0x18000f97c  call    cs:__imp_EmptyClipboard
0x18000f982  test    eax, eax
0x18000f984  jnz     short loc_18000F9A9
0x18000f986  mov     ebx, 800401D1h
0x18000f98b  mov     edx, 0E9Dh; lineNumber
0x18000f990  mov     r9d, ebx; hr
0x18000f993  mov     pDataObject, [rsp+58h]; callerReturnAddress
0x18000f998  lea     ppDataObjectMTAAddress, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18000f99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f9a4  jmp     loc_18000FA3F
0x18000f9a9  test    rsi, rsi
0x18000f9ac  jz      short loc_18000FA20
0x18000f9ae  mov     r8d, [rsp+58h+arg_20]; pid
0x18000f9b6  mov     pSourceDataObject, rdi; pszPackageFulllName
0x18000f9b9  mov     pDataObject, rbx; hClipWnd
0x18000f9bc  call    ?SetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEBGK@Z; SetClipboardOwnerWindowProperty(HWND__ *,ushort const *,ulong)
0x18000f9c1  mov     edi, eax
0x18000f9c3  test    eax, eax
0x18000f9c5  jns     short loc_18000F9E4
0x18000f9c7  mov     edx, 0EA4h; lineNumber
0x18000f9cc  mov     pDataObject, [rsp+58h]; callerReturnAddress
0x18000f9d1  lea     ppDataObjectMTAAddress, aComOle32Ole232_8; "com\\ole32\\ole232\\clipbrd\\clipapi.cp"...
0x18000f9d8  mov     r9d, edi; hr
0x18000f9db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f9e0  mov     ebx, edi
0x18000f9e2  jmp     short loc_18000FA3F
0x18000f9e4  mov     pszCallerPackageFullName, rbp; ppDataObjectMTAAddress
0x18000f9e7  mov     ppDataObjectMTAAddress, r14; pSourceDataObject
0x18000f9ea  mov     pSourceDataObject, rsi; pDataObject
0x18000f9ed  mov     pDataObject, rbx; hClipWnd
0x18000f9f0  call    ?SetClipboardDataObject@@YAJPEAUHWND__@@PEAUIDataObject@@1PEAPEAX@Z; SetClipboardDataObject(HWND__ *,IDataObject *,IDataObject *,void * *)
0x18000f9f5  mov     edi, eax
0x18000f9f7  test    eax, eax
0x18000f9f9  jns     short loc_18000FA02
0x18000f9fb  mov     edx, 0EA5h
0x18000fa00  jmp     short loc_18000F9CC
0x18000fa02  mov     pSourceDataObject, rsi; pDataObj
0x18000fa05  mov     pDataObject, rbx; hClipWnd
0x18000fa08  call    ?SetClipboardFormats@@YAJPEAUHWND__@@PEAUIDataObject@@@Z; SetClipboardFormats(HWND__ *,IDataObject *)
0x18000fa0d  mov     ebx, eax
0x18000fa0f  test    eax, eax
0x18000fa11  jns     short loc_18000FA20
0x18000fa13  mov     r9d, eax
0x18000fa16  mov     edx, 0EA6h
0x18000fa1b  jmp     loc_18000F993
0x18000fa20  lea     pDataObject, [rsp+58h+clipLock]; this
0x18000fa25  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000fa2a  mov     ebx, eax
0x18000fa2c  test    eax, eax
0x18000fa2e  jns     short loc_18000FA3D
0x18000fa30  mov     r9d, eax
0x18000fa33  mov     edx, 0EA9h
0x18000fa38  jmp     loc_18000F993
0x18000fa3d  xor     ebx, ebx
0x18000fa3f  lea     pDataObject, [rsp+58h+clipLock]; this
0x18000fa44  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000fa49  mov     eax, ebx
0x18000fa4b  add     rsp, 30h
0x18000fa4f  pop     r14
0x18000fa51  pop     rdi
0x18000fa52  pop     rsi
0x18000fa53  pop     rbp
0x18000fa54  pop     rbx
0x18000fa55  retn
```
