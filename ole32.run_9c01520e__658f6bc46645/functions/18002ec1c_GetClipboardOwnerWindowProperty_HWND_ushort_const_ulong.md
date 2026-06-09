# GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)

- ea: `0x18002ec1c`
- end: `0x18002ed01`
- name: `?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z`
- size: `229`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, const wchar_t **pszPackageId, unsigned int *pdwProcessId)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a828`
- `0x18002e7a0`
- `0x18002e9dc`

## callees

- `0x18002ec1c`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18002eca2`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18002eca2`
- `USER32!GetPropW` at `0x18002ec4c`
- `USER32!GetPropW` at `0x18002ec65`
- `USER32!GetPropW` at `0x18002ec4c`
- `USER32!GetPropW` at `0x18002ec65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ecde`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002ecf3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002ecf3`

## pseudocode

```c
__int64 __fastcall GetClipboardOwnerWindowProperty(HWND hWnd, wchar_t **pszPackageId, unsigned int *pdwProcessId)
{
  unsigned int v3; // edi
  unsigned int PropW; // ebp
  unsigned __int16 v8; // ax
  ATOM v9; // si
  WCHAR *v10; // rax
  wchar_t *v11; // rbx
  __int64 v13; // rcx

  v3 = 0;
  *pszPackageId = 0;
  *pdwProcessId = 0;
  PropW = (unsigned int)GetPropW(hWnd, L"OleClipProcessOwner");
  v8 = (unsigned __int16)GetPropW(hWnd, L"OLEClipPackgeOwner");
  v9 = v8;
  if ( PropW && v8 )
  {
    v10 = (WCHAR *)CoTaskMemAlloc(0x200u);
    v11 = v10;
    if ( v10 )
    {
      if ( GlobalGetAtomNameW(v9, v10, 256) )
      {
        *pszPackageId = v11;
        *pdwProcessId = PropW;
        return v3;
      }
      CoTaskMemFree(v11);
      v13 = 2147549183LL;
    }
    else
    {
      v13 = 2147942414LL;
    }
    v3 = v13;
    RoOriginateError(v13, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x18002ec1c  mov     [rsp+arg_0], rbx
0x18002ec21  mov     [rsp+arg_8], rbp
0x18002ec26  mov     [rsp+arg_10], rsi
0x18002ec2b  push    rdi
0x18002ec2c  push    r14
0x18002ec2e  push    r15
0x18002ec30  sub     rsp, 20h
0x18002ec34  xor     edi, edi
0x18002ec36  mov     r15, pszPackageId
0x18002ec39  mov     [pszPackageId], rdi
0x18002ec3c  mov     r14, pdwProcessId
0x18002ec3f  lea     pszPackageId, aOleclipprocess; "OleClipProcessOwner"
0x18002ec46  mov     [pdwProcessId], edi
0x18002ec49  mov     rbx, hWnd
0x18002ec4c  call    cs:__imp_GetPropW
0x18002ec53  nop     dword ptr [rax+rax+00h]
0x18002ec58  lea     pszPackageId, aOleclippackgeo; "OLEClipPackgeOwner"
0x18002ec5f  mov     hWnd, rbx; hWnd
0x18002ec62  mov     rbp, rax
0x18002ec65  call    cs:__imp_GetPropW
0x18002ec6c  nop     dword ptr [rax+rax+00h]
0x18002ec71  mov     rsi, rax
0x18002ec74  test    ebp, ebp
0x18002ec76  jz      short loc_18002ECB8
0x18002ec78  test    si, si
0x18002ec7b  jz      short loc_18002ECB8
0x18002ec7d  mov     ecx, 200h; cb
0x18002ec82  call    cs:__imp_CoTaskMemAlloc
0x18002ec89  nop     dword ptr [rax+rax+00h]
0x18002ec8e  mov     rbx, rax
0x18002ec91  test    rax, rax
0x18002ec94  jz      short loc_18002ECD4
0x18002ec96  mov     r8d, 100h; nSize
0x18002ec9c  mov     pszPackageId, rax; lpBuffer
0x18002ec9f  movzx   ecx, si; nAtom
0x18002eca2  call    cs:__imp_GlobalGetAtomNameW
0x18002eca9  nop     dword ptr [rax+rax+00h]
0x18002ecae  test    eax, eax
0x18002ecb0  jz      short loc_18002ECDB
0x18002ecb2  mov     [r15], rbx
0x18002ecb5  mov     [r14], ebp
0x18002ecb8  mov     rbx, [rsp+38h+arg_0]
0x18002ecbd  mov     eax, edi
0x18002ecbf  mov     rbp, [rsp+38h+arg_8]
0x18002ecc4  mov     rsi, [rsp+38h+arg_10]
0x18002ecc9  add     rsp, 20h
0x18002eccd  pop     r15
0x18002eccf  pop     r14
0x18002ecd1  pop     rdi
0x18002ecd2  retn
0x18002ecd4  mov     ecx, 8007000Eh
0x18002ecd9  jmp     short loc_18002ECEF
0x18002ecdb  mov     hWnd, rbx; pv
0x18002ecde  call    cs:__imp_CoTaskMemFree
0x18002ece5  nop     dword ptr [rax+rax+00h]
0x18002ecea  mov     ecx, 8000FFFFh
0x18002ecef  xor     edx, edx
0x18002ecf1  mov     edi, ecx
0x18002ecf3  call    cs:__imp_RoOriginateError
0x18002ecfa  nop     dword ptr [rax+rax+00h]
0x18002ecff  jmp     short loc_18002ECB8
```
