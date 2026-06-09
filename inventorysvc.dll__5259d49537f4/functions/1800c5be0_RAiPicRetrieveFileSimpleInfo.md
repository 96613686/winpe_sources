# RAiPicRetrieveFileSimpleInfo

- ea: `0x1800c5be0`
- end: `0x1800c5e1a`
- name: `RAiPicRetrieveFileSimpleInfo`
- size: `570`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, LPCWSTR lpFileName, _WORD *, _WORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800152d0`
- `0x1800c53d4`
- `0x1800c5be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5c8e`
- `RPCRT4!RpcRevertToSelf` at `0x1800c5c5a`
- `RPCRT4!RpcRevertToSelf` at `0x1800c5c5a`
- `RPCRT4!RpcImpersonateClient` at `0x1800c5c16`
- `RPCRT4!RpcImpersonateClient` at `0x1800c5c16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800c5c52`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800c5c52`
- `AEPIC!PicRetrieveFileInfo` at `0x1800c5cd8`
- `AEPIC!PicRetrieveFileInfo` at `0x1800c5cd8`
- `AEPIC!PicFreeFileInfo` at `0x1800c5e04`
- `AEPIC!PicFreeFileInfo` at `0x1800c5e04`

## string_xrefs

- `0x1800c5d6d`: `StringCchCopyW failed [%#x]`
- `0x1800c5dc9`: `StringCchCopyW failed [%#x]`
- `0x1800c5c22`: `RpcImpersonateClient failed [%d]`

## pseudocode

```c
__int64 __fastcall RAiPicRetrieveFileSimpleInfo(
        RPC_BINDING_HANDLE BindingHandle,
        LPCWSTR lpFileName,
        _WORD *a3,
        _WORD *a4)
{
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // ebx
  unsigned int v10; // ebx
  DWORD FileAttributesW; // ebx
  RPC_STATUS v12; // eax
  signed int LastError; // eax
  int FileInfo; // eax
  const char *v15; // r9
  __int64 v16; // r8
  _WORD **v17; // r11
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  _WORD *v22; // rcx
  _WORD *v23; // rcx
  _WORD *v24; // rax
  _WORD *v25; // rcx
  __int64 v27; // [rsp+20h] [rbp-58h]
  _QWORD v28[9]; // [rsp+30h] [rbp-48h] BYREF

  v28[0] = 0;
  if ( Windows::Compat::Inventory::Service::WinRtHost::singleInstance )
    Windows::Compat::Inventory::Service::WinRtHost::SetTimer(Windows::Compat::Inventory::Service::WinRtHost::singleInstance);
  v8 = RpcImpersonateClient(BindingHandle);
  v9 = v8;
  if ( v8 )
  {
    AslLogCallPrintf(1, "RAiPicRetrieveFileSimpleInfo", 231, "RpcImpersonateClient failed [%d]", v8);
    v10 = v9 | 0x80010000;
    goto LABEL_32;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  v12 = RpcRevertToSelf();
  if ( v12 )
    AslLogCallPrintf(1, "RAiPicRetrieveFileSimpleInfo", 243, "RpcRevertToSelf failed [%d]", v12);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    AslLogCallPrintf(3, "RAiPicRetrieveFileSimpleInfo", 249, "GetFileAttributesW(%ls) failed [%#x]", lpFileName, v10);
    goto LABEL_32;
  }
  FileInfo = PicRetrieveFileInfo(lpFileName, 0x10000, v28);
  v10 = FileInfo;
  if ( FileInfo < 0 )
  {
    LODWORD(v27) = FileInfo;
    v15 = "PicRetrieveFileInfo failed [%#x]";
    v16 = 258;
LABEL_13:
    AslLogCallPrintf(1, "RAiPicRetrieveFileSimpleInfo", v16, v15, v27);
    goto LABEL_32;
  }
  v17 = (_WORD **)v28[0];
  v18 = 2147483646;
  v19 = 45;
  v20 = 2147483646;
  v21 = 45;
  v22 = *(_WORD **)(v28[0] + 8LL);
  do
  {
    if ( !v20 )
      break;
    if ( !*v22 )
      break;
    *a3++ = *v22++;
    --v20;
    --v21;
  }
  while ( v21 );
  v23 = a3 - 1;
  v10 = v21 == 0 ? 0x8007007A : 0;
  if ( v21 )
    v23 = a3;
  *v23 = 0;
  if ( !v21 )
  {
    LODWORD(v27) = -2147024774;
    v15 = "StringCchCopyW failed [%#x]";
    v16 = 265;
    goto LABEL_13;
  }
  v24 = *v17;
  do
  {
    if ( !v18 )
      break;
    if ( !*v24 )
      break;
    *a4++ = *v24++;
    --v18;
    --v19;
  }
  while ( v19 );
  v25 = a4 - 1;
  v10 = v19 == 0 ? 0x8007007A : 0;
  if ( v19 )
    v25 = a4;
  *v25 = 0;
  if ( v19 )
  {
    AslLogCallPrintf(3, "RAiPicRetrieveFileSimpleInfo", 276, "Successfully retrieved PIC info for %ls", lpFileName);
    v10 = 0;
  }
  else
  {
    LODWORD(v27) = -2147024774;
    AslLogCallPrintf(1, "RAiPicRetrieveFileSimpleInfo", 272, "StringCchCopyW failed [%#x]", v27);
  }
LABEL_32:
  if ( v28[0] )
    PicFreeFileInfo();
  return v10;
}

```

## disassembly

```asm
0x1800c5be0  push    rbx
0x1800c5be2  push    rbp
0x1800c5be3  push    rsi
0x1800c5be4  push    r12
0x1800c5be6  push    r14
0x1800c5be8  push    r15
0x1800c5bea  sub     rsp, 48h
0x1800c5bee  xor     r12d, r12d
0x1800c5bf1  mov     rbx, rcx
0x1800c5bf4  mov     rcx, cs:?singleInstance@WinRtHost@Service@Inventory@Compat@Windows@@0PEAV12345@EA; this
0x1800c5bfb  mov     r14, r9
0x1800c5bfe  mov     [rsp+78h+var_48], r12
0x1800c5c03  mov     r15, r8
0x1800c5c06  mov     rbp, rdx
0x1800c5c09  test    rcx, rcx
0x1800c5c0c  jz      short loc_1800C5C13
0x1800c5c0e  call    ?SetTimer@WinRtHost@Service@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::Service::WinRtHost::SetTimer(void)
0x1800c5c13  mov     rcx, rbx; BindingHandle
0x1800c5c16  call    cs:__imp_RpcImpersonateClient
0x1800c5c1c  mov     ebx, eax
0x1800c5c1e  test    eax, eax
0x1800c5c20  jz      short loc_1800C5C4F
0x1800c5c22  lea     r9, aRpcimpersonate; "RpcImpersonateClient failed [%d]"
0x1800c5c29  mov     dword ptr [rsp+78h+var_58], eax
0x1800c5c2d  mov     r8d, 0E7h
0x1800c5c33  lea     rdx, aRaipicretrieve; "RAiPicRetrieveFileSimpleInfo"
0x1800c5c3a  mov     ecx, 1
0x1800c5c3f  call    AslLogCallPrintf
0x1800c5c44  or      ebx, 80010000h
0x1800c5c4a  jmp     loc_1800C5DFA
0x1800c5c4f  mov     rcx, rbp; lpFileName
0x1800c5c52  call    cs:__imp_GetFileAttributesW
0x1800c5c58  mov     ebx, eax
0x1800c5c5a  call    cs:__imp_RpcRevertToSelf
0x1800c5c60  lea     rsi, aRaipicretrieve; "RAiPicRetrieveFileSimpleInfo"
0x1800c5c67  test    eax, eax
0x1800c5c69  jz      short loc_1800C5C89
0x1800c5c6b  lea     r9, aRpcreverttosel; "RpcRevertToSelf failed [%d]"
0x1800c5c72  mov     dword ptr [rsp+78h+var_58], eax
0x1800c5c76  mov     r8d, 0F3h
0x1800c5c7c  mov     rdx, rsi
0x1800c5c7f  mov     ecx, 1
0x1800c5c84  call    AslLogCallPrintf
0x1800c5c89  cmp     ebx, 0FFFFFFFFh
0x1800c5c8c  jnz     short loc_1800C5CCB
0x1800c5c8e  call    cs:__imp_GetLastError
0x1800c5c94  mov     ebx, eax
0x1800c5c96  test    eax, eax
0x1800c5c98  jle     short loc_1800C5CA3
0x1800c5c9a  movzx   ebx, ax
0x1800c5c9d  or      ebx, 80070000h
0x1800c5ca3  mov     [rsp+78h+var_50], ebx
0x1800c5ca7  lea     r9, aGetfileattribu_3; "GetFileAttributesW(%ls) failed [%#x]"
0x1800c5cae  mov     r8d, 0F9h
0x1800c5cb4  mov     [rsp+78h+var_58], rbp
0x1800c5cb9  mov     rdx, rsi
0x1800c5cbc  mov     ecx, 3
0x1800c5cc1  call    AslLogCallPrintf
0x1800c5cc6  jmp     loc_1800C5DFA
0x1800c5ccb  lea     r8, [rsp+78h+var_48]
0x1800c5cd0  mov     edx, 10000h
0x1800c5cd5  mov     rcx, rbp
0x1800c5cd8  call    cs:__imp_PicRetrieveFileInfo
0x1800c5cde  mov     ebx, eax
0x1800c5ce0  test    eax, eax
0x1800c5ce2  jns     short loc_1800C5D07
0x1800c5ce4  mov     dword ptr [rsp+78h+var_58], eax
0x1800c5ce8  lea     r9, aPicretrievefil_0; "PicRetrieveFileInfo failed [%#x]"
0x1800c5cef  mov     r8d, 102h
0x1800c5cf5  mov     rdx, rsi
0x1800c5cf8  mov     ecx, 1
0x1800c5cfd  call    AslLogCallPrintf
0x1800c5d02  jmp     loc_1800C5DFA
0x1800c5d07  mov     r11, [rsp+78h+var_48]
0x1800c5d0c  mov     r9d, 7FFFFFFEh
0x1800c5d12  mov     edx, 2Dh ; '-'
0x1800c5d17  mov     eax, r9d
0x1800c5d1a  mov     r8d, edx
0x1800c5d1d  mov     rcx, [r11+8]
0x1800c5d21  test    rax, rax
0x1800c5d24  jz      short loc_1800C5D45
0x1800c5d26  movzx   r10d, word ptr [rcx]
0x1800c5d2a  test    r10w, r10w
0x1800c5d2e  jz      short loc_1800C5D45
0x1800c5d30  mov     [r15], r10w
0x1800c5d34  add     rcx, 2
0x1800c5d38  add     r15, 2
0x1800c5d3c  dec     rax
0x1800c5d3f  sub     r8, 1
0x1800c5d43  jnz     short loc_1800C5D21
0x1800c5d45  mov     rax, r8
0x1800c5d48  lea     rcx, [r15-2]
0x1800c5d4c  neg     rax
0x1800c5d4f  mov     r10d, 8007007Ah
0x1800c5d55  sbb     ebx, ebx
0x1800c5d57  not     ebx
0x1800c5d59  and     ebx, r10d
0x1800c5d5c  test    r8, r8
0x1800c5d5f  cmovnz  rcx, r15
0x1800c5d63  mov     [rcx], r12w
0x1800c5d67  jnz     short loc_1800C5D7F
0x1800c5d69  mov     dword ptr [rsp+78h+var_58], ebx
0x1800c5d6d  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x1800c5d74  mov     r8d, 109h
0x1800c5d7a  jmp     loc_1800C5CF5
0x1800c5d7f  mov     rax, [r11]
0x1800c5d82  test    r9, r9
0x1800c5d85  jz      short loc_1800C5DA4
0x1800c5d87  movzx   ecx, word ptr [rax]
0x1800c5d8a  test    cx, cx
0x1800c5d8d  jz      short loc_1800C5DA4
0x1800c5d8f  mov     [r14], cx
0x1800c5d93  add     rax, 2
0x1800c5d97  add     r14, 2
0x1800c5d9b  dec     r9
0x1800c5d9e  sub     rdx, 1
0x1800c5da2  jnz     short loc_1800C5D82
0x1800c5da4  mov     rax, rdx
0x1800c5da7  lea     rcx, [r14-2]
0x1800c5dab  neg     rax
0x1800c5dae  sbb     ebx, ebx
0x1800c5db0  not     ebx
0x1800c5db2  and     ebx, r10d
0x1800c5db5  test    rdx, rdx
0x1800c5db8  mov     rdx, rsi
0x1800c5dbb  cmovnz  rcx, r14
0x1800c5dbf  mov     [rcx], r12w
0x1800c5dc3  jnz     short loc_1800C5DDB
0x1800c5dc5  mov     dword ptr [rsp+78h+var_58], ebx
0x1800c5dc9  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x1800c5dd0  mov     r8d, 110h
0x1800c5dd6  jmp     loc_1800C5CF8
0x1800c5ddb  lea     r9, aSuccessfullyRe; "Successfully retrieved PIC info for %ls"
0x1800c5de2  mov     [rsp+78h+var_58], rbp
0x1800c5de7  mov     r8d, 114h
0x1800c5ded  mov     ecx, 3
0x1800c5df2  call    AslLogCallPrintf
0x1800c5df7  mov     ebx, r12d
0x1800c5dfa  mov     rcx, [rsp+78h+var_48]
0x1800c5dff  test    rcx, rcx
0x1800c5e02  jz      short loc_1800C5E0A
0x1800c5e04  call    cs:__imp_PicFreeFileInfo
0x1800c5e0a  mov     eax, ebx
0x1800c5e0c  add     rsp, 48h
0x1800c5e10  pop     r15
0x1800c5e12  pop     r14
0x1800c5e14  pop     r12
0x1800c5e16  pop     rsi
0x1800c5e17  pop     rbp
0x1800c5e18  pop     rbx
0x1800c5e19  retn
```
